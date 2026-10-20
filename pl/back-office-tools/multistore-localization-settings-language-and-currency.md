---
title: "Ustawienia lokalizacji Multistore - język i waluta - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dotyczące modułu PrestaShop „Ustawienia lokalizacji Multistore - język i waluta” od MyPresta.eu."
sidebar:
  label: "Ustawienia lokalizacji Multistore - język i waluta - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Multistore localization settings - language and currency na MyPresta.eu](https://mypresta.eu/modules/administration-tools/multistore-localization-settings-language-and-currency.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/multistore-localization-settings-language-and-currency/)
>
> ---


# Ustawienia lokalizacji Multistore - język i waluta

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Twoje środowisko hostingowe musi obsługiwać funkcję PrestaShop Multistore.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Ten moduł wprowadza nową pozycję menu w Twoim Panelu administracyjnym PrestaShop do zarządzania regułami lokalizacji dla każdego z Twoich sklepów.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Gdy po raz pierwszy klikniesz „Konfiguruj” po instalacji, znajdziesz się na podstawowej stronie konfiguracji. Ta strona służy przede wszystkim jako punkt wejścia do głównego interfejsu zarządzania.

- **Co robi to ustawienie:** Ten ekran prawdopodobnie będzie zawierał prostą wiadomość lub przycisk kierujący Cię do dedykowanego obszaru zarządzania regułami lokalizacji Multistore. Może również zawierać informacje o wersji modułu lub link do wsparcia.
- **Efekt zmiany tego ustawienia:** Kliknięcie dowolnego przycisku lub linku tutaj przeniesie Cię do głównego interfejsu, gdzie zdefiniujesz reguły języka i waluty specyficzne dla Twojego sklepu.
- **Zalecana wartość:** Postępuj zgodnie z instrukcjami na ekranie, zazwyczaj klikając przycisk, aby przejść do głównej konfiguracji.
- **Scenariusz sprzedawcy / przykład:** Po instalacji zobaczysz wiadomość typu „Kliknij tutaj, aby zarządzać regułami lokalizacji Multistore”. Klikniesz to, aby uzyskać dostęp do podstawowej funkcjonalności.

### 2.2 Dedykowany ekran administracyjny: Reguły lokalizacji Multistore (Panel administracyjny > Reguły lokalizacji Multistore)

To jest główny panel sterowania modułu. Znajdziesz tę nową pozycję menu w **Parametry sklepu > Reguły lokalizacji Multistore** (lub podobnie, w zależności od Twojej wersji PrestaShop i struktury menu).

Po wejściu na ten ekran zobaczysz listę (siatkę) Twoich istniejących sklepów. Dla każdego sklepu będziesz mógł zdefiniować jego specyficzne ustawienia języka i waluty.

**Dostępne działania i ustawienia:**

1. **Lista sklepów / Widok siatki:**

   - **Cel:** Ta tabela wyświetla wszystkie sklepy, które skonfigurowałeś w swojej konfiguracji PrestaShop Multistore.
   - **Kolumny:** Zazwyczaj zobaczysz kolumny takie jak „Nazwa sklepu” i potencjalnie „Akcje” lub „Konfiguruj”.
   - **Efekt zmian:** Ten widok pozwala szybko zobaczyć, które sklepy są skonfigurowane i stanowi punkt wejścia do edycji ich ustawień lokalizacji.
2. **Przycisk Edytuj/Konfiguruj dla każdego sklepu:**

   - **Co robi ten przycisk:** Kliknięcie tego przycisku (często ikona ołówka) obok nazwy sklepu otworzy szczegółowy formularz konfiguracji specjalnie dla tego sklepu.
   - **Efekt zmiany tego ustawienia:** Tutaj definiujesz konkretne języki i waluty dla wybranego sklepu.

**Wewnątrz formularza konfiguracji specyficznego dla sklepu:**

Po kliknięciu, aby edytować sklep, zobaczysz dwie główne sekcje: **Języki** i **Waluty**.

#### 2.2.1 Konfiguracja języków dla [Nazwa sklepu]

- **Lista dostępnych języków:**

  - **Co robi to ustawienie:** Ta sekcja przedstawia listę wszystkich języków zainstalowanych w Twoim sklepie PrestaShop. Dla każdego języka zazwyczaj zobaczysz pole wyboru.
  - **Efekt zmiany tego ustawienia:**
    - *Po zaznaczeniu:* Język będzie dostępny do wyboru przez klientów w front office tego konkretnego sklepu.
    - *Po odznaczeniu:* Język NIE będzie wyświetlany w selektorze języka dla tego sklepu, a klienci nie będą mogli na niego przełączyć.
  - **Zalecana wartość:** Zaznacz tylko języki istotne dla docelowej grupy odbiorców tego konkretnego sklepu.
  - **Scenariusz sprzedawcy / przykład:** Dla Twojego „Sklepu Francuskiego” zaznaczyłbyś „Français (French)” i odznaczył wszystkie inne języki.
- **Domyślny język dla [Nazwa sklepu]:**

  - **Co robi to ustawienie:** Rozwijana lista lub wybór przycisku radiowego umożliwiający wybranie jednego z *włączonych* języków jako domyślnego dla tego sklepu.
  - **Efekt zmiany tego ustawienia:** Gdy klient po raz pierwszy odwiedzi ten sklep, automatycznie załaduje się on w wybranym domyślnym języku. Jeśli klient wcześniej wybrał język, jego preferencje mogą zostać zapamiętane, ale dla nowych odwiedzających obowiązuje ten domyślny język.
  - **Zalecana wartość:** Ustaw podstawowy język dla docelowej grupy odbiorców sklepu.
  - **Scenariusz sprzedawcy / przykład:** Dla Twojego „Sklepu Francuskiego” ustawiłbyś „Français (French)” jako domyślny język.

#### 2.2.2 Konfiguracja walut dla [Nazwa sklepu]

- **Lista dostępnych walut:**

  - **Co robi to ustawienie:** Ta sekcja przedstawia listę wszystkich walut zainstalowanych w Twoim sklepie PrestaShop. Dla każdej waluty zazwyczaj zobaczysz pole wyboru.
  - **Efekt zmiany tego ustawienia:**
    - *Po zaznaczeniu:* Waluta będzie dostępna do wyboru przez klientów w front office tego konkretnego sklepu. Ceny będą wyświetlane w tej walucie, jeśli zostanie wybrana.
    - *Po odznaczeniu:* Waluta NIE będzie wyświetlana w selektorze waluty dla tego sklepu, a klienci nie będą mogli przeglądać cen w niej.
  - **Zalecana wartość:** Zaznacz tylko waluty istotne dla docelowej grupy odbiorców tego konkretnego sklepu.
  - **Scenariusz sprzedawcy / przykład:** Dla Twojego „Sklepu USA” zaznaczyłbyś „US Dollar ($)” i odznaczył „Euro (€)” oraz inne waluty.
- **Domyślna waluta dla [Nazwa sklepu]:**

  - **Co robi to ustawienie:** Rozwijana lista lub wybór przycisku radiowego umożliwiający wybranie jednej z *włączonych* walut jako domyślnej dla tego sklepu.
  - **Efekt zmiany tego ustawienia:** Gdy klient po raz pierwszy odwiedzi ten sklep, wszystkie ceny automatycznie zostaną wyświetlone w wybranej domyślnej walucie.
  - **Zalecana wartość:** Ustaw podstawową walutę dla docelowej grupy odbiorców sklepu.
  - **Scenariusz sprzedawcy / przykład:** Dla Twojego „Sklepu USA” ustawiłbyś „US Dollar ($)” jako domyślną walutę.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

1. Przejdź do **Parametry sklepu > Reguły lokalizacji Multistore**.
2. Zidentyfikuj sklep, który chcesz skonfigurować z listy.
3. Kliknij przycisk „Edytuj” lub „Konfiguruj” obok tego sklepu.
4. W sekcji „Języki” zaznacz wszystkie języki, które chcesz, aby były dostępne dla tego konkretnego sklepu.
5. Wybierz jeden z *zaznaczonych* języków jako „Domyślny język” dla tego sklepu.
6. W sekcji „Waluty” zaznacz wszystkie waluty, które chcesz, aby były dostępne dla tego konkretnego sklepu.
7. Wybierz jedną z *zaznaczonych* walut jako „Domyślna waluta” dla tego sklepu.
8. Kliknij „Zapisz”, aby zastosować zmiany.
9. Powtórz dla wszystkich innych sklepów w Twojej konfiguracji Multistore.
10. **Zawsze wyczyść pamięć podręczną PrestaShop** (Zaawansowane > Wydajność) po wprowadzeniu zmian, aby upewnić się, że są one natychmiast widoczne w front office.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Reguły lokalizacji Multistore (Widok listy)** | Przycisk Edytuj/Konfiguruj | N/A | Dostęp do szczegółowych ustawień języka/waluty dla konkretnego sklepu. |
| **Konfiguracja specyficzna dla sklepu (Języki)** | Dostępne języki (pola wyboru) | Zaznacz odpowiednie | Kontroluje, które języki pojawiają się w selektorze front office dla tego sklepu. |
| **Konfiguracja specyficzna dla sklepu (Języki)** | Domyślny język | Podstawowy język dla odbiorców sklepu | Ustawia początkowy język dla nowych odwiedzających ten sklep. |
| **Konfiguracja specyficzna dla sklepu (Waluty)** | Dostępne waluty (pola wyboru) | Zaznacz odpowiednie | Kontroluje, które waluty pojawiają się w selektorze front office dla tego sklepu. |
| **Konfiguracja specyficzna dla sklepu (Waluty)** | Domyślna waluta | Podstawowa waluta dla odbiorców sklepu | Ustawia początkową walutę dla nowych odwiedzających ten sklep. |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P: Skonfigurowałem języki/waluty, ale nie zmieniają się one w moim front office.**
O: Najczęstszą przyczyną jest pamięć podręczna. Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” i „Wyczyść pamięć podręczną” dla wszystkich pamięci podręcznych). Spróbuj również wyczyścić pamięć podręczną przeglądarki.

**P: Mój niestandardowy motyw wydaje się nie respektować ustawień modułu dla selektorów języka/waluty.**
O: Ten moduł kontroluje, *które* opcje są dostępne, ale Twój motyw dyktuje, *jak* te opcje są wyświetlane. Jeśli Twój motyw ma mocno dostosowane selektory języka/waluty, może on nadpisywać standardowe zachowanie PrestaShop.
\* **Rozwiązanie:** Sprawdź dokumentację swojego motywu lub skontaktuj się z jego twórcą. Może być konieczne wprowadzenie drobnych zmian w plikach `.tpl` Twojego motywu, aby upewnić się, że używają one standardowych zmiennych PrestaShop `languages` i `currencies`, które ten moduł modyfikuje.

**P: Czy mogę ustawić różne domyślne języki/waluty dla różnych grup klientów?**
O: Nie, ten moduł ustawia domyślny język i walutę *dla każdego sklepu*, a nie dla każdej grupy klientów. Domyślne ustawienie dotyczy wszystkich odwiedzających ten konkretny sklep. Klienci mogą następnie ręcznie je zmienić, jeśli dostępne są inne opcje.

**P: Co się stanie, jeśli wyłączę język/walutę, która jest obecnie ustawiona jako domyślna dla sklepu?**
O: Moduł powinien uniemożliwić Ci to lub automatycznie przywrócić następny dostępny język/walutę. Zawsze upewnij się, że wybrana domyślna opcja jest jedną z *włączonych* opcji dla tego sklepu. Jeśli napotkasz problemy, ponownie włącz odpowiednią domyślną opcję i wyczyść pamięć podręczną.

**P: Mam tylko jeden sklep. Czy potrzebuję tego modułu?**
O: Nie, ten moduł jest specjalnie zaprojektowany dla funkcji Multistore w PrestaShop. Jeśli masz tylko jeden sklep, domyślne ustawienia lokalizacji PrestaShop (w sekcji Międzynarodowe > Lokalizacja) są wystarczające.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowe informacje na temat technicznej implementacji modułu „Ustawienia lokalizacji Multistore - język i waluta” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł przede wszystkim rozszerza podstawowe zachowanie lokalizacji PrestaShop poprzez nadpisywanie klas `Currency` i `Language`. Wprowadza niestandardowy kontroler administracyjny (`AdminMultirulesController`) do zarządzania regułami lokalizacji specyficznymi dla sklepu, które są przechowywane w niestandardowej tabeli bazy danych. Moduł wykorzystuje wzorzec MVC PrestaShop dla swojego interfejsu Panelu administracyjnego i używa nadpisań do wstrzykiwania swojej logiki do procesu wyboru języka i waluty w front office.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Ten moduł nie zawiera żadnych dedykowanych kontrolerów front-office. Jego logika front-office jest wstrzykiwana za pomocą nadpisań klas i hooków.
- **Kontrolery administracyjne Back-Office**:

  - `multishoplang/controllers/admin/AdminMultirules.php`
    - **Nazwa klasy i klasa nadrzędna**: `AdminMultirulesController` rozszerza `ModuleAdminController`.
    - **Odpowiedzialność**: Ten kontroler zarządza listowaniem i edycją reguł lokalizacji dla każdego sklepu. Jest odpowiedzialny za wyświetlanie siatki sklepów, obsługę formularza do wyboru dostępnych języków i walut dla konkretnego sklepu oraz zapisywanie tych ustawień w bazie danych. Prawdopodobnie używa `HelperList` dla siatki sklepów i `HelperForm` dla konfiguracji specyficznej dla sklepu.
    - **Nazwa zakładki**: „Reguły lokalizacji Multistore” (lub podobna, zdefiniowana w metodzie `installTab()`).
  - `multishoplang/controllers/admin/index.php`
    - **Nazwa klasy i klasa nadrzędna**: Jest to zazwyczaj pusty plik lub plik zawierający instrukcję bezpieczeństwa `die()`, aby zapobiec bezpośredniemu dostępowi do katalogu. Nie reprezentuje aktywnego kontrolera.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł w dużym stopniu opiera się na nadpisywaniu, aby modyfikować podstawowe zachowanie PrestaShop.

- `multishoplang/override/classes/Currency.php`
  - **Nazwa klasy i klasa nadrzędna**: `Currency` (nadpisuje podstawową klasę `Currency` PrestaShop).
  - **Odpowiedzialność**: To nadpisanie przechwytuje wywołania związane z pobieraniem i wyborem waluty. Modyfikuje metody takie jak `getCurrencies()` lub `getDefaultCurrency()`, aby filtrować listę dostępnych walut na podstawie konfiguracji bieżącego sklepu zdefiniowanej przez moduł. Zapewnia, że tylko waluty włączone dla aktywnego sklepu są prezentowane w front office.
- `multishoplang/override/classes/Language.php`
  - **Nazwa klasy i klasa nadrzędna**: `Language` (nadpisuje podstawową klasę `Language` PrestaShop).
  - **Odpowiedzialność**: Podobnie jak nadpisanie `Currency`, ta klasa przechwytuje wywołania związane z językiem. Modyfikuje metody takie jak `getLanguages()` lub `getDefaultLanguage()`, aby filtrować listę dostępnych języków na podstawie konfiguracji bieżącego sklepu. Zapewnia, że tylko języki włączone dla aktywnego sklepu są prezentowane w front office.
- `multishoplang/override/classes/index.php`
  - **Nazwa klasy i klasa nadrzędna**: Jest to zazwyczaj pusty plik lub plik zawierający instrukcję bezpieczeństwa `die()`, aby zapobiec bezpośredniemu dostępowi do katalogu. Nie reprezentuje aktywnej klasy.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł nie zawiera żadnych niestandardowych plików JavaScript. Wszystkie interakcje w Panelu administracyjnym są obsługiwane przez standardowy JavaScript `HelperForm` i `HelperList` PrestaShop, a zachowanie front-office jest zarządzane przez nadpisania klas.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie zawiera żadnych niestandardowych plików CSS. Jego interfejs Panelu administracyjnego opiera się na domyślnej stylizacji motywu administracyjnego PrestaShop. Wyświetlanie w front-office jest kontrolowane przez aktywny motyw.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**: Brak jawnie wymienionych, ale logika modułu działa przede wszystkim poprzez nadpisania klas, a nie bezpośrednie szablony hooków.
- **Szablony administracyjne (`views/templates/admin/`)**:
  - `multishoplang/views/advert.tpl`
    - **Cel**: Prawdopodobnie szablon do wyświetlania komunikatów promocyjnych lub informacji o innych modułach MyPresta.eu w interfejsie konfiguracji modułu.
  - `multishoplang/views/currenciesForm.tpl`
    - **Cel**: Ten szablon jest używany w `AdminMultirulesController` do renderowania sekcji formularza do konfigurowania dostępnych walut i domyślnej waluty dla konkretnego sklepu. Będzie zawierał pola wyboru dla walut i rozwijaną listę dla domyślnej waluty.
  - `multishoplang/views/languagesForm.tpl`
    - **Cel**: Ten szablon jest używany w `AdminMultirulesController` do renderowania sekcji formularza do konfigurowania dostępnych języków i domyślnego języka dla konkretnego sklepu. Będzie zawierał pola wyboru dla języków i rozwijaną listę dla domyślnego języka.
- **Szablony front-office (`views/templates/front/`)**: Brak.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - `ps_multirule`: Jest to niestandardowa tabela utworzona przez moduł do przechowywania reguł lokalizacji. Prawdopodobnie zawiera pola takie jak:
    - `id_shop`: Klucz obcy odwołujący się do `ps_shop.id_shop`.
    - `id_lang_default`: Identyfikator domyślnego języka dla tego sklepu.
    - `id_currency_default`: Identyfikator domyślnej waluty dla tego sklepu.
    - `available_languages`: Zserializowana tablica lub ciąg znaków oddzielonych przecinkami wartości `id_lang` włączonych dla sklepu.
    - `available_currencies`: Zserializowana tablica lub ciąg znaków oddzielonych przecinkami wartości `id_currency` włączonych dla sklepu.
  - Rekordy konfiguracji są przechowywane w `ps_configuration` dla ogólnych ustawień modułu (jeśli takie istnieją).
- **Tabela zarejestrowanych hooków**:
  Moduł działa przede wszystkim poprzez nadpisania klas, a nie bezpośrednie wykonanie hooków w front office. Jednak zarejestruje standardowe hooki Panelu administracyjnego dla swojego interfejsu administracyjnego.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Po załadowaniu kontrolera administracyjnego | Do ładowania CSS/JS specyficznych dla modułu (chociaż w tym module ich nie ma). |
| `displayBackOfficeHeader` | W nagłówku Panelu administracyjnego | Potencjalnie do wyświetlania alertów lub powiadomień specyficznych dla modułu. |
| `moduleRoutes` | Podczas inicjalizacji routingu URL | Jeśli moduł zdefiniował niestandardowe trasy front-office (nie dotyczy tutaj). |
| `actionObjectLanguageAddAfter` | Po dodaniu nowego języka | Potencjalnie do aktualizacji wewnętrznych danych modułu dla nowych języków. |
| `actionObjectCurrencyAddAfter` | Po dodaniu nowej waluty | Potencjalnie do aktualizacji wewnętrznych danych modułu dla nowych walut. |
| `actionShopDataDuplication` | Po zduplikowaniu sklepu | Aby upewnić się, że reguły lokalizacji są kopiowane dla nowego sklepu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie płynnego działania i ciągłego ulepszania Twoich modułów PrestaShop.
"""
