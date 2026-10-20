---
title: "Waluta i język według kraju - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Waluta i język według kraju” od MyPresta.eu."
sidebar:
  label: "Waluta i język według kraju - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Currency and language by country na MyPresta.eu](https://mypresta.eu/modules/front-office-features/currency-and-language-by-country.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/currency-and-language-by-country/)
>
> ---


# Waluta i język według kraju

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zazwyczaj dostępne w każdym nowoczesnym środowisku hostingowym. Dla tego modułu nie są potrzebne żadne specjalne rozszerzenia.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu „Waluta i język według kraju”. Znajdziesz tu wszystkie ustawienia, aby zdefiniować, jak Twój sklep dostosowuje się do odwiedzających z określonych krajów.

**Dostęp:** Panel administracyjny > Moduły > Menedżer modułów > Wyszukaj „Waluta i język według kraju” > Kliknij „Konfiguruj”.

#### **1. Wybierz kraj**

- **Co robi to ustawienie:** Ta lista rozwijana pozwala wybrać konkretny kraj, dla którego chcesz zastosować automatyczne zmiany języka i waluty.
- **Efekt zmiany tego ustawienia:** Po wybraniu kraju (np. „Francja”), moduł zastosuje ustawienia języka i waluty zdefiniowane poniżej *tylko* dla odwiedzających wykrytych jako pochodzących z tego kraju. Jeśli nie wybierzesz kraju, moduł nie zastosuje żadnych reguł geolokalizacji.
- **Zalecana wartość:** Najpierw wybierz kraj, który chcesz docelować. W tej darmowej wersji możesz skonfigurować tylko jeden kraj naraz.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby odwiedzający z Niemiec widzieli Twój sklep w języku niemieckim z walutą euro, wybierz tutaj „Niemcy”.

#### **2. Włącz zmianę języka przez odwiedzającego**

- **Co robi to ustawienie:** Ten przełącznik kontroluje, czy moduł powinien automatycznie zmieniać język sklepu dla odwiedzających z wybranego kraju.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone („Włączone”):* Moduł spróbuje przełączyć język front-office sklepu na ten, który określisz w ustawieniu „Wybierz język” poniżej, dla odwiedzających z wybranego kraju.
  - *Gdy wyłączone („Wyłączone”):* Język nie zostanie automatycznie zmieniony, nawet jeśli wybrałeś język poniżej. Odwiedzający zobaczy sklep w Twoim domyślnym języku lub preferowanym języku przeglądarki (jeśli domyślne zachowanie PrestaShop na to pozwala).
- **Zalecana wartość:** „Włączone”, jeśli chcesz zapewnić zlokalizowane doświadczenie językowe.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli wybrałeś „Francję” jako kraj, włączenie tego ustawienia oznacza, że możesz następnie wybrać „Francuski” jako język dla francuskich odwiedzających.

#### **3. Wybierz język**

- **Co robi to ustawienie:** Ta lista rozwijana pojawia się tylko wtedy, gdy „Włącz zmianę języka przez odwiedzającego” jest włączone. Pozwala wybrać, który język zostanie ustawiony dla odwiedzających z wybranego kraju.
- **Efekt zmiany tego ustawienia:** Język front-office sklepu automatycznie przełączy się na wybrany język dla odwiedzających z wybranego kraju. Upewnij się, że ten język jest już zainstalowany i włączony w Twoim sklepie PrestaShop (Panel administracyjny > Lokalizacja > Języki).
- **Zalecana wartość:** Oficjalny język wybranego kraju.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli wybrałeś „Hiszpanię” jako kraj i włączyłeś zmianę języka, wybierz tutaj „Hiszpański”.

#### **4. Włącz zmianę waluty przez odwiedzającego**

- **Co robi to ustawienie:** Ten przełącznik kontroluje, czy moduł powinien automatycznie zmieniać walutę sklepu dla odwiedzających z wybranego kraju.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone („Włączone”):* Moduł spróbuje przełączyć walutę front-office sklepu na tę, którą określisz w ustawieniu „Wybierz walutę” poniżej, dla odwiedzających z wybranego kraju.
  - *Gdy wyłączone („Wyłączone”):* Waluta nie zostanie automatycznie zmieniona. Ceny będą wyświetlane w domyślnej walucie Twojego sklepu lub walucie ręcznie wybranej przez klienta.
- **Zalecana wartość:** „Włączone”, jeśli chcesz wyświetlać ceny w lokalnej walucie.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli wybrałeś „Stany Zjednoczone” jako kraj, włączenie tego ustawienia oznacza, że możesz następnie wybrać „Dolar amerykański” jako walutę dla odwiedzających z USA.

#### **5. Wybierz walutę**

- **Co robi to ustawienie:** Ta lista rozwijana pojawia się tylko wtedy, gdy „Włącz zmianę waluty przez odwiedzającego” jest włączone. Pozwala wybrać, która waluta zostanie ustawiona dla odwiedzających z wybranego kraju.
- **Efekt zmiany tego ustawienia:** Wszystkie ceny w front-office sklepu automatycznie przełączą się na wybraną walutę dla odwiedzających z wybranego kraju. Upewnij się, że ta waluta jest już zainstalowana i włączona w Twoim sklepie PrestaShop (Panel administracyjny > Lokalizacja > Waluty).
- **Zalecana wartość:** Oficjalna waluta wybranego kraju.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli wybrałeś „Japonię” jako kraj i włączyłeś zmianę waluty, wybierz tutaj „Jen japoński”.

#### **Ważna uwaga dotycząca nadpisywania (override):**

Ten moduł wykorzystuje system nadpisywania PrestaShop do modyfikowania podstawowego zachowania waluty i języka. Jeśli masz inne moduły, które również używają nadpisywania dla `Currency.php` lub `Language.php`, mogą wystąpić konflikty. Zawsze dokładnie testuj po instalacji.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wybierz kraj | Twój kraj docelowy | Definiuje kraj, dla którego obowiązują zasady. |
| Konfiguracja modułu | Włącz zmianę języka przez odwiedzającego | Włączone | Aktywuje automatyczne przełączanie języka dla wybranego kraju. |
| Konfiguracja modułu | Wybierz język | Oficjalny język kraju | Ustawia konkretny język dla odwiedzających z wybranego kraju. |
| Konfiguracja modułu | Włącz zmianę waluty przez odwiedzającego | Włączone | Aktywuje automatyczne przełączanie waluty dla wybranego kraju. |
| Konfiguracja modułu | Wybierz walutę | Oficjalna waluta kraju | Ustawia konkretną walutę dla odwiedzających z wybranego kraju. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Język/waluta nie zmienia się dla odwiedzających z wybranego kraju. Co powinienem sprawdzić?**
O:

1.  **Moduł włączony:** Upewnij się, że moduł „Waluta i język według kraju” jest zainstalowany i włączony w Menedżerze modułów.
2.  **Konfiguracja zapisana:** Sprawdź dwukrotnie, czy wybrałeś kraj, włączyłeś odpowiednie opcje zmiany języka/waluty, wybrałeś prawidłowy język/walutę i kliknąłeś „Zapisz” na stronie konfiguracji modułu.
3.  **Język/waluta zainstalowane i włączone:** Zweryfikuj, czy docelowy język i waluta są zainstalowane i włączone w Panelu administracyjnym PrestaShop (Lokalizacja > Języki i Lokalizacja > Waluty).
4.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) i pamięć podręczną przeglądarki.
5.  **Dokładność geolokalizacji:** Usługi geolokalizacyjne nie zawsze są w 100% dokładne. Testuj za pomocą VPN, aby upewnić się, że Twój adres IP jest poprawnie identyfikowany jako pochodzący z kraju docelowego.

**P: Czy mogę skonfigurować różne języki/waluty dla wielu krajów?**
O: Darmowy moduł „Waluta i język według kraju” pozwala na konfigurację reguł tylko dla jednego kraju naraz. Jeśli potrzebujesz zaawansowanego targetowania wielu krajów, rozważ uaktualnienie do modułu „Geolocation Pro” od MyPresta.eu, który oferuje bardziej rozbudowane funkcje.

**P: Mój domyślny język/waluta sklepu nadal się wyświetla nawet po konfiguracji.**
O: Ten moduł jest przeznaczony specjalnie dla odwiedzających z *wybranego* kraju. Dla wszystkich innych odwiedzających zastosowany zostanie domyślny język i waluta Twojego sklepu lub preferowane ustawienia ich przeglądarki, jeśli PrestaShop jest skonfigurowany tak, aby je respektować. Upewnij się, że testujesz z dokładnie tego kraju, który skonfigurowałeś.

**P: Zainstalowałem inny moduł, a teraz przełączanie języka/waluty nie działa.**
O: Ten moduł wykorzystuje system nadpisywania PrestaShop. Jeśli inny moduł również nadpisuje `classes/Currency.php` lub `classes/Language.php`, może wystąpić konflikt. Sprawdź swój `app/config/parameters.php` (dla PS 1.7+) lub `config/settings.inc.php` (dla PS 1.6) pod kątem `_PS_MODE_DEV_` i ustaw go na `true`, aby zobaczyć komunikaty o błędach. Może być konieczne skontaktowanie się z pomocą techniczną w celu rozwiązania konfliktów nadpisywania.

**P: Jak moduł wykrywa kraj odwiedzającego?**
O: Moduł wykorzystuje adres IP odwiedzającego do określenia jego lokalizacji geograficznej. Jest to standardowa metoda geolokalizacji.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem „Waluta i język według kraju”.

### 4.1 Przegląd architektury

Moduł „Waluta i język według kraju” (`freegeo`) to lekki moduł PrestaShop zaprojektowany przede wszystkim do modyfikowania domyślnego języka i waluty na podstawie adresu IP odwiedzającego. Osiąga to poprzez wykorzystanie systemu nadpisywania PrestaShop dla podstawowych klas `Currency` i `Language` oraz poprzez podłączenie się do zdarzenia `actionDispatcherBefore` w celu wykonania logiki geolokalizacji przed renderowaniem głównej zawartości strony. Konfiguracja modułu jest obsługiwana za pomocą standardowej metody `getContent()` w głównym pliku modułu.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów Front-Office ani Back-Office. Jego logika jest wykonywana głównie za pośrednictwem hooków i nadpisywania klas.

### 4.3 Podstawowe klasy i modele (`classes/`)

Moduł wykorzystuje system nadpisywania PrestaShop do wstrzykiwania swojej logiki w podstawowe funkcjonalności.

-   **`freegeo/override/classes/Currency.php`**

    -   **Nazwa klasy:** `Currency` (nadpisuje podstawową klasę `Currency`)
    -   **Klasa nadrzędna:** `CurrencyCore`
    -   **Odpowiedzialność:** To nadpisanie jest kluczowe dla ustawiania waluty na podstawie geolokalizacji. Modyfikuje ono sposób określania aktywnej waluty. Logika modułu w tym nadpisaniu sprawdzi, czy ustawienie `FREEGEO_CURRENCY_ON` jest włączone i czy kraj odwiedzającego odpowiada skonfigurowanemu `FREEGEO_COUNTRY`. Jeśli tak, spróbuje wymusić walutę na `FREEGEO_CURRENCY`.
    -   **Kluczowe metody:** Nadpisanie prawdopodobnie modyfikuje metody związane z `getCurrent()` lub `getCurrency()` w celu wstrzyknięcia identyfikatora waluty z geolokalizacji.
-   **`freegeo/override/classes/Language.php`**

    -   **Nazwa klasy:** `Language` (nadpisuje podstawową klasę `Language`)
    -   **Klasa nadrzędna:** `LanguageCore`
    -   **Odpowiedzialność:** Podobnie jak nadpisanie `Currency`, ta klasa jest odpowiedzialna za ustawianie języka na podstawie geolokalizacji. Sprawdza `FREEGEO_LANGUAGE_ON` i `FREEGEO_COUNTRY` i, jeśli warunki są spełnione, wymusza język na `FREEGEO_LANGUAGE`.
    -   **Kluczowe metody:** Nadpisanie prawdopodobnie modyfikuje metody związane z `getCurrentLanguage()` lub `getLanguage()` w celu wstrzyknięcia identyfikatora języka z geolokalizacji.
-   **`freegeo/override/classes/index.php`**

    -   **Cel:** Jest to standardowy pusty plik `index.php`, zazwyczaj umieszczany w katalogach w celu zapobiegania listowaniu katalogów na serwerach WWW, co zwiększa bezpieczeństwo. Nie ma on funkcjonalnego wpływu na logikę modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Cała jego funkcjonalność jest obsługiwana po stronie serwera.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Jego funkcjonalność nie obejmuje żadnego specyficznego stylu front-office.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`freegeo/views/advert.tpl`**
    -   **Zakres:** Back-office (strona konfiguracji modułu).
    -   **Cel:** Ten szablon jest prawdopodobnie używany do wyświetlania reklamy lub komunikatu promocyjnego dla modułu „Geolocation Pro” od MyPresta.eu na stronie konfiguracji modułu. Służy jako element marketingowy w interfejsie administratora.
    -   **Hook:** Ten szablon jest renderowany w metodzie `getContent()` głównego pliku modułu, zazwyczaj przed lub po głównym formularzu konfiguracji.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoje ustawienia konfiguracyjne bezpośrednio w tabeli `ps_configuration` PrestaShop.
-   **Rekordy konfiguracji w `ps_configuration`**:

    -   `FREEGEO_CURRENCY_ON`: Przechowuje wartość logiczną (0 lub 1) wskazującą, czy zmiana waluty jest włączona.
    -   `FREEGEO_LANGUAGE_ON`: Przechowuje wartość logiczną (0 lub 1) wskazującą, czy zmiana języka jest włączona.
    -   `FREEGEO_CURRENCY`: Przechowuje ID waluty do ustawienia (np. `id_currency`).
    -   `FREEGEO_LANGUAGE`: Przechowuje ID języka do ustawienia (np. `id_lang`).
    -   `FREEGEO_COUNTRY`: Przechowuje kod ISO lub ID kraju docelowego.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administratora ustawia swoje zasoby multimedialne (JS/CSS). | Chociaż wymieniony, ten moduł prawdopodobnie używa go minimalnie lub do ładowania określonych skryptów/stylów po stronie administratora, jeśli takie były obecne (nie wykryto w inwentarzu). |
| `actionDispatcherBefore` | Wykonywany bardzo wcześnie w cyklu życia żądania PrestaShop, zanim dispatcher przetworzy URL. | **KRYTYCZNY HOOK:** To tutaj znajduje się podstawowa logika geolokalizacji modułu. Służy do wykrywania adresu IP odwiedzającego, określania jego kraju, a następnie, na podstawie ustawień modułu, potencjalnego nadpisywania `Context::getContext()->language` i `Context::getContext()->currency` przed renderowaniem strony. |
| `actionFrontControllerAfterInit` | Wykonywany po zainicjowaniu kontrolera Front-Office. | Ten hook może być używany do wykonywania dodatkowych sprawdzeń lub dostosowań po skonfigurowaniu głównego kontrolera, ale przed renderowaniem. Może służyć jako punkt awaryjny lub uzupełniający dla dostosowań języka/waluty, jeśli `actionDispatcherBefore` nie jest wystarczający we wszystkich scenariuszach. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Waluta i język według kraju”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
