---
title: "Kolumna i wyszukiwanie numeru faktury na liście zamówień - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop „Kolumna i wyszukiwanie numeru faktury na liście zamówień” od MyPresta.eu."
sidebar:
  label: "Kolumna i wyszukiwanie numeru faktury na liście zamówień - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Order List Invoice Column & Search na MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-list-invoice-column-search.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/order-list-invoice-column-search/)
>
> ---


# Kolumna i wyszukiwanie numeru faktury na liście zamówień

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Brak specjalnych wymagań hostingowych poza standardową konfiguracją PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu „Kolumna i wyszukiwanie numeru faktury na liście zamówień”. Ten moduł ma bardzo prostą i bezpośrednią konfigurację, ponieważ jego podstawową funkcjonalnością jest ulepszenie istniejącej listy zamówień.

Strona konfiguracji modułu „Kolumna i wyszukiwanie numeru faktury na liście zamówień” jest prosta. Służy głównie do włączania lub wyłączania funkcjonalności modułu.

-   **Nazwa ustawienia:** Włącz kolumnę i wyszukiwanie numeru faktury
-   **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji funkcji modułu. Po włączeniu moduł doda kolumnę „Numer faktury” do listy zamówień i zintegruje funkcję wyszukiwania. Po wyłączeniu lista zamówień powróci do domyślnego wyglądu PrestaShop.
-   **Efekt zmiany tego ustawienia:**
    -   *Po włączeniu (TAK):* Nowa kolumna zatytułowana „Numer faktury” pojawi się w Twoim panelu administracyjnym w sekcji **Zamówienia > Zamówienia**. Ta kolumna wyświetli numer faktury dla każdego zamówienia (jeśli faktura została wygenerowana). Dodatkowo, pasek wyszukiwania na stronie Zamówienia umożliwi teraz wyszukiwanie według numeru faktury.
    -   *Po wyłączeniu (NIE):* Kolumna „Numer faktury” zostanie usunięta z listy zamówień, a możliwość wyszukiwania według numeru faktury zostanie dezaktywowana. Twoja lista zamówień będzie wyglądać dokładnie tak, jak przed zainstalowaniem tego modułu.
-   **Zalecana wartość:** **TAK**. Aby korzystać z funkcji modułu, należy go włączyć.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz szybko znaleźć wszystkie zamówienia związane z konkretną fakturą (np. „INV00123”), włączysz to ustawienie. Następnie przejdziesz do **Zamówienia > Zamówienia**, wpiszesz „INV00123” w pasku wyszukiwania, a system przefiltruje listę, aby wyświetlić tylko to zamówienie. Jeśli wyłączysz tę funkcję, będziesz musiał ręcznie klikać każde zamówienie, aby sprawdzić jego numer faktury, co jest bardzo czasochłonne.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz kolumnę i wyszukiwanie numeru faktury | TAK | Aktywuje/dezaktywuje kolumnę numeru faktury i funkcję wyszukiwania na liście zamówień w panelu administracyjnym. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Włączyłem moduł, ale nie widzę kolumny „Numer faktury” lub wyszukiwanie nie działa.**
O:

1.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Czasami PrestaShop potrzebuje odświeżenia pamięci podręcznej, aby wyświetlić nowe elementy.
2.  **Sprawdź status modułu:** Upewnij się, że moduł jest rzeczywiście „Włączony” na stronie konfiguracji.
3.  **Wersja PrestaShop:** Upewnij się, że Twoja wersja PrestaShop jest kompatybilna z modułem (1.7.x, 8.x, 9.x).
4.  **Pamięć podręczna przeglądarki:** Spróbuj wyczyścić pamięć podręczną przeglądarki lub użyć okna incognito, aby wykluczyć problemy specyficzne dla przeglądarki.

**P: Numery faktur pokazują „N/A” lub są puste dla niektórych zamówień.**
O: Zazwyczaj oznacza to, że faktura nie została jeszcze wygenerowana dla tych konkretnych zamówień w PrestaShop. Moduł wyświetla numer faktury tylko wtedy, gdy istnieje on w bazie danych PrestaShop. Będziesz musiał ręcznie wygenerować fakturę dla tych zamówień poprzez standardowy proces zarządzania zamówieniami PrestaShop.

**P: Czy ten moduł spowolni mój panel administracyjny?**
O: Nie, moduł został zaprojektowany tak, aby był lekki i wydajny. Głównie rozszerza istniejącą funkcję PrestaShop (listę zamówień), zamiast dodawać ciężkie nowe procesy. Jego wpływ na wydajność powinien być znikomy.

**P: Czy mogę dostosować pozycję kolumny „Numer faktury”?**
O: Moduł umieszcza kolumnę w logicznej pozycji na liście zamówień. Bezpośrednie dostosowanie kolejności kolumn nie jest wbudowaną funkcją tego modułu. W przypadku zaawansowanych zmian układu, zazwyczaj potrzebne byłoby niestandardowe tworzenie motywu lub inny specjalistyczny moduł.

**P: Czy ten moduł tworzy nowe faktury?**
O: Nie, ten moduł nie generuje faktur. Wyświetla i umożliwia wyszukiwanie tylko według numerów faktur, które zostały już wygenerowane przez podstawową funkcjonalność PrestaShop.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Kolumna i wyszukiwanie numeru faktury na liście zamówień” (`olistinv`) to klasyczny moduł PrestaShop, który rozszerza podstawową funkcjonalność poprzez podłączenie się do istniejących punktów wyświetlania i akcji w panelu administracyjnym. Głównie modyfikuje widok listy kontrolera `AdminOrders`, aby dodać nową kolumnę i ulepsza możliwości wyszukiwania bez wprowadzania nowych tabel bazy danych ani złożonych interakcji z front-office. Jego prostota polega na wykorzystaniu systemu hooków PrestaShop i nadpisywaniu logiki szablonów, gdzie jest to konieczne.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Cała jego logika zawarta jest w głównym pliku modułu, `olistinv/index.php`, i wykonywana za pośrednictwem hooków.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani `ObjectModel`. Bezpośrednio współdziała z istniejącymi podstawowymi klasami PrestaShop i strukturami bazy danych.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Funkcjonalność wyszukiwania jest zintegrowana poprzez modyfikację zachowania istniejącego formularza wyszukiwania, co jest obsługiwane przez podstawowy JS PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Nowa kolumna odziedziczy stylizację istniejących tabel panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie zawiera żadnych niestandardowych plików szablonów Smarty. Osiąga swoją funkcjonalność poprzez dynamiczne wstrzykiwanie treści do istniejących szablonów PrestaShop za pośrednictwem hooków, w szczególności poprzez modyfikację wyświetlania listy `AdminOrders`.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Ten moduł nie tworzy żadnych nowych tabel bazy danych. Odczytuje dane z tabeli `ps_orders` (konkretnie pola `invoice_number`) i potencjalnie `ps_order_invoice` dla szczegółów faktury, a swoją konfigurację przechowuje w `ps_configuration`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayAdminOrderListHeader` | Renderuje się przed nagłówkiem tabeli listy zamówień w panelu administracyjnym. | Służy do dodawania nagłówka kolumny „Numer faktury” do listy zamówień. |
| `displayAdminOrderList` | Renderuje się dla każdego wiersza (zamówienia) w tabeli listy zamówień w panelu administracyjnym. | Służy do wyświetlania rzeczywistego numeru faktury dla każdego zamówienia w nowo dodanej kolumnie. |
| `actionAdminOrdersListingFieldsModifier` | Modyfikuje tablicę pól używaną do budowania zapytania i wyświetlania listy zamówień. | Służy do dodawania pola `invoice_number` do listy pól możliwych do wyszukiwania i wyświetlania dla kontrolera `AdminOrders`. Jest to kluczowe zarówno dla wyświetlania kolumny, jak i włączania wyszukiwania. |
| `actionAdminOrdersFilterModifier` | Modyfikuje zapytanie filtrujące dla listy zamówień. | Służy do rozszerzenia funkcjonalności wyszukiwania o pole `invoice_number` po przesłaniu zapytania wyszukiwania. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji, poprawek błędów i oficjalnego wsparcia dla modułu „Kolumna i wyszukiwanie numeru faktury na liście zamówień”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu.
