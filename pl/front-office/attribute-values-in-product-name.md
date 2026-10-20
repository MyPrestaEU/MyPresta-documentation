---
title: "Wartości atrybutów w nazwie produktu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów dla modułu PrestaShop „Wartości atrybutów w nazwie produktu” od MyPresta.eu."
sidebar:
  label: "Wartości atrybutów w nazwie produktu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Attribute values in product name na MyPresta.eu](https://mypresta.eu/modules/front-office-features/attribute-values-in-product-name.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/attribute-values-in-product-name/)
>
> ---


# Wartości atrybutów w nazwie produktu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po zainstalowaniu modułu kliknij „Konfiguruj”, aby uzyskać dostęp do jego ustawień.

#### Klasa CSS nazwy produktu

- **Co robi to ustawienie:** To pole pozwala określić klasę CSS elementu HTML, który wyświetla nazwę produktu na stronach produktów. Moduł musi znać tę klasę, aby mógł poprawnie zidentyfikować i zmodyfikować element nazwy produktu, gdy klient wybierze nową kombinację atrybutów.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy wprowadzono poprawną klasę CSS:* Moduł pomyślnie zlokalizuje nazwę produktu na stronie i dynamicznie dołączy do niej wybrane wartości atrybutów.
  - *Gdy wprowadzono niepoprawną lub brak klasy CSS:* Moduł nie będzie w stanie znaleźć elementu nazwy produktu, a zatem wartości atrybutów nie zostaną dodane do nazwy produktu. Nazwa produktu pozostanie statyczna.
- **Zalecana wartość:** Ta wartość zależy od Twojego motywu PrestaShop.
  - Dla **domyślnych motywów PrestaShop (Classic)**, wspólną klasą dla nazwy produktu jest `h1.product-detail-name` lub `h1[itemprop="name"]`. Może być konieczne sprawdzenie strony produktu za pomocą narzędzi deweloperskich przeglądarki, aby znaleźć dokładną klasę lub ID tagu `<h1>` zawierającego nazwę produktu.
  - Jeśli nie jesteś pewien, spróbuj najpierw `h1.product-detail-name`. Jeśli to nie zadziała, będziesz musiał skonsultować się z deweloperem motywu lub użyć narzędzi deweloperskich przeglądarki (kliknij prawym przyciskiem myszy na nazwę produktu, wybierz „Zbadaj”), aby znaleźć prawidłowy selektor CSS dla głównego nagłówka nazwy produktu.
- **Scenariusz/przykład dla sprzedawcy:**
  - Zainstalowałeś niestandardowy motyw, a nazwa produktu jest zawarta w tagu `<h2>` z klasą `my-custom-product-title`. Wprowadziłbyś `h2.my-custom-product-title` w tym polu.
  - Jeśli Twój motyw używa standardowej struktury motywu PrestaShop Classic, wprowadzenie `h1.product-detail-name` powinno działać idealnie, zapewniając, że gdy klient wybierze „Niebieski” dla koszuli, tytuł zmieni się z „T-Shirt” na „T-Shirt (Niebieski)”.

#### Inne klucze konfiguracyjne (wewnętrzne)

Możesz zobaczyć inne klucze konfiguracyjne, takie jak `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `mypresta_updates`, `update_`, `updatev_`. Są to wewnętrzne ustawienia używane przez PrestaShop i MyPresta.eu do zarządzania aktualizacjami modułów i preferencjami językowymi. Nie musisz z nimi wchodzić w interakcje.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Klasa CSS nazwy produktu | `h1.product-detail-name` (dla motywu Classic) | Określa selektor CSS dla elementu nazwy produktu. Niezbędne, aby moduł mógł zidentyfikować i zmodyfikować tytuł produktu na stronie produktu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Nazwa produktu nie zmienia się po wybraniu atrybutów. Co jest nie tak?**
O: Najczęstszą przyczyną jest nieprawidłowe ustawienie „Klasa CSS nazwy produktu”.
- **Rozwiązanie**:
1. Przejdź do strony produktu w przeglądarce.
2. Kliknij prawym przyciskiem myszy na nazwę produktu i wybierz „Zbadaj” (lub „Zbadaj element”).
3. Poszukaj tagu `<h1>` lub `<h2>`, który zawiera nazwę produktu. Zapisz jego klasę (np. `class="product-detail-name"`) lub ID (np. `id="product_name"`).
4. Wprowadź prawidłowy selektor CSS do konfiguracji modułu. Na przykład, jeśli tag to `<h1 class="my-product-title">`, wprowadź `h1.my-product-title`. Jeśli to `<h2 id="product_heading">`, wprowadź `h2#product_heading`.
5. Zapisz konfigurację modułu i wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).

**P: Moduł działał początkowo, ale po aktualizacji motywu przestał działać.**
O: Aktualizacje motywów często zmieniają strukturę HTML i klasy CSS.
- **Rozwiązanie**: Ponownie sprawdź ustawienie „Klasa CSS nazwy produktu” zgodnie z powyższym opisem. Twój nowy motyw może używać innej klasy lub ID dla nazwy produktu.

**P: Czy ten moduł wpłynie na moje SEO?**
O: Nie, ten moduł zmienia nazwę produktu dynamicznie tylko po stronie klienta (w przeglądarce klienta) za pomocą JavaScriptu. Nie zmienia oryginalnej nazwy produktu przechowywanej w Twojej bazie danych ani tagu `<h1>`, który zazwyczaj indeksują wyszukiwarki. Twoje SEO pozostaje nienaruszone.

**P: Czy ten moduł obsługuje wiele języków?**
O: Tak, moduł działa z wartościami atrybutów tak, jak są skonfigurowane w panelu administracyjnym PrestaShop, które są już kompatybilne z wieloma językami. Moduł po prostu dołącza aktualnie wybrane wartości atrybutów w aktywnym języku do nazwy produktu.

**P: Widzę wartości atrybutów, ale są one niepoprawnie ostylowane (np. zła czcionka, kolor).**
O: Moduł dołącza tekst do istniejącego elementu HTML. Jego stylizacja będzie dziedziczona z CSS Twojego motywu dla tego elementu nazwy produktu.
- **Rozwiązanie**: Jeśli chcesz inaczej ostylować dołączone wartości atrybutów, będziesz potrzebować niestandardowego CSS. Możesz celować w element nazwy produktu i potencjalnie użyć pseudo-elementów lub specyficznych selektorów, jeśli moduł opakowuje dołączony tekst w unikalny `<span>` (chociaż ten moduł zazwyczaj po prostu dołącza tekst). Deweloper stron internetowych może pomóc Ci z niestandardowym CSS.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla deweloperów, webmasterów i agencji.

### 4.1 Przegląd architektury

Moduł „Wartości atrybutów w nazwie produktu” (`anpn`) to lekki moduł PrestaShop, skupiający się głównie na manipulacji po stronie klienta w front-office. Wykorzystuje system hooków PrestaShop do wstrzykiwania swojego JavaScriptu do nagłówka strony produktu. Główna logika znajduje się w pojedynczym pliku JavaScript, który nasłuchuje zmian w wyborach atrybutów produktu i dynamicznie aktualizuje zawartość tekstową nazwy produktu. Nie wprowadza nowych tabel baz danych ani złożonej logiki po stronie serwera poza swoją konfiguracją.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Cała funkcjonalność front-office jest obsługiwana za pomocą JavaScriptu wstrzykiwanego przez hooki.
- **Kontrolery Back-Office Admin**: Brak. Konfiguracja jest zarządzana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

- Nie zdefiniowano żadnych niestandardowych klas ani instancji `ObjectModel`. Moduł działa bezpośrednio na wartościach konfiguracyjnych i manipulacji DOM w front-office.

### 4.4 Zasoby JavaScript (`views/js/`)

- **`anpn/views/js/anpn.js`**
  - **Zakres**: Front-office (strona produktu).
  - **Cel**: Ten skrypt jest odpowiedzialny za dynamiczną aktualizację nazwy produktu.
  - **Funkcjonalność**:
    1.  **DOM Ready / `prestashop.on`**: Czeka na pełne załadowanie DOM i nasłuchuje zdarzenia `updatedProduct` wywoływanego przez podstawowy JavaScript PrestaShop, gdy kombinacja produktu zostanie zmieniona (np. poprzez wybranie innego rozmiaru lub koloru).
    2.  **Identyfikacja nazwy produktu**: Pobiera selektor CSS dla nazwy produktu z konfiguracji modułu (przekazany za pośrednictwem globalnej zmiennej `anpn_pn_class` lub podobnego mechanizmu). Następnie używa tego selektora do znalezienia docelowego elementu HTML na stronie.
    3.  **Ekstrakcja wartości atrybutów**: Gdy `updatedProduct` zostanie wywołane, uzyskuje dostęp do danych bieżącej kombinacji produktu (które obejmują wybrane wartości atrybutów) z ładunku zdarzenia.
    4.  **Dynamiczna aktualizacja**: Tworzy ciąg znaków z wybranych wartości atrybutów (np. „(M, Niebieski)”) i dołącza go do oryginalnej nazwy produktu (którą zazwyczaj przechowuje przy początkowym ładowaniu lub pobiera z atrybutu danych).
    5.  **Manipulacja DOM**: Skrypt aktualizuje `textContent` lub `innerText` zidentyfikowanego elementu nazwy produktu nowym, połączonym ciągiem znaków.
  - **Zależności**: Opiera się na jQuery (jeśli PrestaShop 1.7.x) lub natywnych API DOM oraz systemie zdarzeń `prestashop.on` PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

- Moduł nie dostarcza żadnych niestandardowych plików CSS. Dołączone wartości atrybutów dziedziczą stylizację istniejącego elementu nazwy produktu w motywie.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- Moduł nie dostarcza żadnych niestandardowych plików szablonów. Cała generacja danych wyjściowych jest obsługiwana przez główny plik modułu (`anpn.php`) dla konfiguracji oraz JavaScript dla wyświetlania w front-office.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  - Moduł nie tworzy żadnych niestandardowych tabel baz danych.
  - Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration`:
    - `ANPN_PN_CLASS`: Przechowuje klasę/selektor CSS dla elementu nazwy produktu.
- **Tabela zarejestrowanych hooków**:

  | Nazwa hooka | Czas wykonania | Cel techniczny |
  | --- | --- | --- |
  | `displayHeader` | W sekcji `<head>` każdej strony front-office. | Służy do rejestrowania JavaScriptu modułu (`anpn.js`) i przekazywania wartości konfiguracyjnej `ANPN_PN_CLASS` do skryptu front-end. |
  | `displayProductAdditionalInfo` | Na stronie produktu, zazwyczaj poniżej głównych informacji o produkcie. | Chociaż nie jest wyraźnie używany do wizualnego wyświetlania w tym module, jest to powszechny hook dla modułów do wstrzykiwania treści lub skryptów na stronie produktu. W kontekście tego modułu może być używany do zapewnienia, że JS jest ładowany we właściwym czasie, lub może być to dziedziczna rejestracja hooka. Główna interakcja odbywa się za pośrednictwem `displayHeader` i zdarzenia `updatedProduct`. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Wartości atrybutów w nazwie produktu”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
"""
