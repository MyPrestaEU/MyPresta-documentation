---
title: "Stylight - piksel śledzenia sprzedaży - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Stylight - piksel śledzenia sprzedaży” od MyPresta.eu."
sidebar:
  label: "Stylight - piksel śledzenia sprzedaży"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Stylight - sales tracking pixel na MyPresta.eu](https://mypresta.eu/modules/ordering-process/stylight-sales-tracking-pixel.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/stylight-sales-tracking-pixel/)
>
> ---


# Stylight - piksel śledzenia sprzedaży

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) zazwyczaj dostępne w większości środowisk hostingowych kompatybilnych z PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Moduł „Stylight - piksel śledzenia sprzedaży” został zaprojektowany tak, aby był niezwykle prosty w konfiguracji, nie wymagając żadnych specyficznych ustawień od sprzedawcy. Jego funkcjonalność jest przede wszystkim samodzielna, automatycznie wykrywając i przesyłając niezbędne dane zamówienia.

Po przejściu na stronę konfiguracji modułu (Panel administracyjny > Moduły > Menedżer modułów > Stylight - piksel śledzenia sprzedaży > Konfiguruj) zazwyczaj znajdziesz komunikat potwierdzający, że moduł jest zainstalowany i aktywny.

-   **Co robi ten ekran:** Ta strona służy jako potwierdzenie, że moduł jest poprawnie zainstalowany i gotowy do śledzenia sprzedaży. Nie ma żadnych pól wejściowych ani przełączników do regulacji. Moduł automatycznie łączy się z procesem potwierdzenia zamówienia i zbiera wszystkie wymagane dane (całkowita kwota, waluta, liczba pozycji, numery SKU, identyfikator zamówienia) bezpośrednio ze szczegółów zamówienia PrestaShop.
-   **Wpływ zmiany tego ustawienia:** Ponieważ nie ma konfigurowalnych ustawień, nie ma nic do zmiany. Moduł działa od razu po zainstalowaniu.
-   **Zalecana wartość:** Nie wymaga działania.
-   **Scenariusz / przykład sprzedawcy:** Po zainstalowaniu modułu po prostu odwiedzasz tę stronę, aby potwierdzić jego obecność. Nie musisz wprowadzać żadnych identyfikatorów ani kluczy Stylight, ponieważ sam piksel jest ogólny i zaprojektowany do współpracy z systemem Stylight poprzez wysyłanie standardowych danych e-commerce.

### 2.2 Tabela szybkiego odniesienia konfiguracji
| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Strona konfiguracji modułu | *(Brak ustawień konfigurowalnych przez użytkownika)* | N/A | Moduł automatycznie śledzi dane sprzedaży (całkowita kwota, waluta, liczba pozycji, SKU, identyfikator zamówienia) na stronie potwierdzenia zamówienia dla Stylight.com. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zainstalowałem moduł, ale nie widzę żadnych zgłoszonych sprzedaży na moim koncie Stylight. Co powinienem zrobić?**
O: Najpierw upewnij się, że moduł jest włączony w Panelu administracyjnym PrestaShop. Następnie spróbuj wyczyścić pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną). Jeśli problem nadal występuje, samodzielnie złóż zamówienie testowe. Jeśli nadal nie ma danych, skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojej wersji PrestaShop i wszelkie inne ostatnio zainstalowane moduły.

**P: Czy ten moduł spowalnia moją stronę potwierdzenia zamówienia?**
O: Piksel śledzenia jest bardzo lekki i ładuje się asynchronicznie, co oznacza, że zazwyczaj nie wpływa znacząco na czasy ładowania strony ani doświadczenie klienta. Jego wpływ na wydajność jest minimalny.

**P: Czy muszę wprowadzić jakiś identyfikator Stylight lub klucz API do modułu?**
O: Nie, ten moduł jest zaprojektowany do działania od razu po wyjęciu z pudełka. Implementuje standardowy piksel śledzenia Stylight, który automatycznie wysyła niezbędne dane zamówienia bez konieczności wprowadzania przez sprzedawcę konkretnych identyfikatorów w samej konfiguracji modułu. Twoje konto Stylight jest połączone z Twoją domeną, a ich system identyfikuje Twój sklep na podstawie miejsca pochodzenia piksela.

**P: Czy ten moduł jest kompatybilny z niestandardowymi motywami?**
O: Tak, moduł łączy się ze standardowym hookiem PrestaShop (`displayOrderConfirmation`), który jest zazwyczaj obecny we wszystkich dobrze zakodowanych motywach. Nie opiera się na konkretnych elementach motywu, więc powinien działać bezproblemowo z większością niestandardowych motywów.

**P: Mam wiele języków/walut. Czy moduł śledzi je poprawnie?**
O: Tak, moduł jest zaprojektowany do automatycznego przechwytywania całkowitej kwoty zamówienia i waluty przetwarzanej przez PrestaShop, zapewniając dokładne śledzenie dla sklepów wielowalutowych i wielojęzycznych.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury
Moduł „Stylight - piksel śledzenia sprzedaży” to prosty moduł PrestaShop, skupiający się głównie na hookowaniu zdarzeń w front-office. Wykorzystuje hook `displayOrderConfirmation` do wstrzykiwania piksela śledzenia opartego na JavaScript na końcowej stronie potwierdzenia zamówienia. Logika modułu znajduje się w jego głównym pliku PHP, `index.php`, który obsługuje instalację, deinstalację i rejestrację hooka. Zbieranie danych jest dynamiczne, pobierając szczegóły zamówienia bezpośrednio z obiektów `Order` i `Product` dostępnych w kontekście strony potwierdzenia zamówienia.

### 4.2 Kontrolery (`controllers/`)
-   **Kontrolery Front-Office**: Brak. Funkcjonalność front-office modułu jest w całości obsługiwana przez hookowanie do `displayOrderConfirmation` i renderowanie szablonu Smarty.
-   **Kontrolery Back-Office Admin**: Brak. Moduł nie ma dedykowanego interfejsu administracyjnego poza standardową stroną konfiguracji modułu (`getContent()`).

### 4.3 Klasy i modele rdzenia (`classes/`)
-   Brak. Moduł nie definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Cała logika znajduje się w głównym pliku `stylightpixel/index.php`.

### 4.4 Zasoby JavaScript (`views/js/`)
-   Brak. Kod piksela śledzenia jest bezpośrednio osadzony w szablonie Smarty (`displayOrderConfirmation.tpl`), aby zapewnić jego natychmiastowe uruchomienie po załadowaniu strony.

### 4.5 Arkusze stylów CSS (`views/css/`)
-   Brak. Moduł jest czysto funkcjonalny i nie ma żadnych komponentów wizualnych ani wymagań dotyczących stylizacji.

### 4.6 Struktura szablonów Smarty (`views/templates/`)
-   **Szablony hooków (`views/templates/hook/`)**:
    *   `stylightpixel/views/templates/hook/displayOrderConfirmation.tpl`
        *   **Hook**: `displayOrderConfirmation`
        *   **Cel**: Ten szablon jest renderowany na stronie potwierdzenia zamówienia po udanym zakupie. Zawiera kod JavaScript dla piksela śledzenia Stylight.
        *   **Dostępne dane**: Szablon otrzymuje `$order` (obiekt `Order`) i `$products` (tablicę obiektów `Product` powiązanych z zamówieniem) z metody `hookDisplayOrderConfirmation`.
        *   **Wynik**: Wyświetla blok `<script>`, który konstruuje URL piksela śledzenia Stylight z dynamicznymi parametrami, takimi jak `order_id`, `total_amount`, `currency`, `item_count` i `sku` dla każdego produktu.

### 4.7 Schemat bazy danych i mapa hooków
-   **Tabele bazy danych**: Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Opiera się na standardowych tabelach PrestaShop (`ps_orders`, `ps_order_detail`, `ps_product` itp.) w celu pobierania informacji o zamówieniu.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `displayOrderConfirmation` | Wykonywany na końcowej stronie potwierdzenia zamówienia po udanym zakupie. | Wstrzykuje kod JavaScript piksela śledzenia Stylight do strony, aby wysłać dane konwersji (identyfikator zamówienia, suma, waluta, SKU produktów, liczba pozycji) do Stylight. |

## 5. Oficjalne wsparcie i aktualizacje
W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkiej dalszej pomocy z modułem „Stylight - piksel śledzenia sprzedaży” prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w zapytaniach związanych z modułem i zapewnić prawidłowe działanie piksela śledzenia.
