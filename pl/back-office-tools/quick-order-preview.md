---
title: "Szybki Podgląd Zamówienia - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów dla modułu PrestaShop Szybki Podgląd Zamówienia od MyPresta.eu."
sidebar:
  label: "Szybki Podgląd Zamówienia - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Quick Order Preview na MyPresta.eu](https://mypresta.eu/modules/administration-tools/quick-order-preview.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/quick-order-preview/)
>
> ---


# Szybki Podgląd Zamówienia

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 9.x, 8.x, 1.7.7.x - 1.7.8.x, 1.7.0.0 - 1.7.6.x, 1.6.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Szybki Podgląd Zamówienia”. Spowoduje to przejście do jego głównego ekranu konfiguracji.

Na tym ekranie nie ma żadnych konkretnych opcji konfiguracji dla modułu „Szybki Podgląd Zamówienia”. Moduł działa od razu po instalacji, rozszerzając istniejącą funkcjonalność strony „Zamówienia”. Jego główną funkcją jest wstrzykiwanie niezbędnego kodu JavaScript i szablonów, aby umożliwić funkcję szybkiego podglądu bezpośrednio na liście zamówień.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### AdminPreviewOrderController (Panel administracyjny > Zamówienia > Lista zamówień)

Ten moduł nie dodaje nowej pozycji menu do panelu administracyjnego PrestaShop. Zamiast tego, rozszerza istniejącą stronę listy **„Zamówienia”** (znajdującą się w **Panelu administracyjnym > Zamówienia > Zamówienia**).

-   **Nazwa ekranu i lokalizacja w menu:** Dostęp do tej rozszerzonej funkcjonalności uzyskujesz, przechodząc do **Zamówienia > Zamówienia** w panelu administracyjnym PrestaShop.
-   **Dostępne działania i ustawienia:**
    -   **Funkcjonalność szybkiego podglądu:** Gdy jesteś na stronie listy „Zamówienia”, po prostu kliknij dowolny wiersz zamówienia. Zamiast zostać przekierowanym na pełną stronę szczegółów zamówienia, moduł rozwinie wiersz zamówienia, aby wyświetlić kluczowe informacje bezpośrednio pod nim. Obejmuje to:
        -   **Adres klienta:** Adresy rozliczeniowy i wysyłkowy.
        -   **Zamówione produkty:** Lista zakupionych pozycji, w tym ilości i ceny.
        -   **Notatka klienta:** Jeśli klient zostawił notatkę podczas składania zamówienia, będzie ona widoczna tutaj.
    -   **Przycisk „Wyświetl zamówienie”:** W rozwiniętym podglądzie nadal znajdziesz przycisk „Wyświetl zamówienie” (lub podobny link), który pozwala przejść do pełnej, tradycyjnej strony szczegółów zamówienia, jeśli musisz wykonać działania takie jak zmiana statusu zamówienia, dodawanie produktów lub generowanie faktur.
    -   **Zapisywanie notatki klienta:** Moduł zawiera również funkcjonalność do zapisywania notatek klienta bezpośrednio z tego szybkiego podglądu. Jest to zarządzane przez skrypt `save-customer-note.js`.
-   **Efekt zmian:**
    -   Kliknięcie wiersza zamówienia teraz przełącza wyświetlanie jego szczegółowych informacji bezpośrednio na stronie listy zamówień.
    -   Możesz szybko przeglądać istotne dane zamówienia bez opuszczania głównej listy, znacznie przyspieszając proces realizacji zamówień.
    -   Możliwość zapisywania notatek klienta bezpośrednio z podglądu usprawnia komunikację i prowadzenie dokumentacji.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Przejdź do **Zamówienia > Zamówienia**.
    2.  Aby szybko sprawdzić, co zamówił klient lub jego adres wysyłki, po prostu kliknij wiersz zamówienia na liście.
    3.  Szczegóły rozwiną się pod zamówieniem. Przejrzyj informacje.
    4.  Jeśli musisz zmienić status zamówienia, wydrukować fakturę lub wykonać inne zaawansowane działania, kliknij przycisk „Wyświetl zamówienie” w rozwiniętym podglądzie, aby przejść do pełnej strony szczegółów zamówienia.
    5.  Jeśli musisz dodać szybką notatkę o kliencie lub zamówieniu, użyj pola notatki klienta w podglądzie i zapisz ją.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Lista zamówień | Kliknij wiersz zamówienia | N/A | Rozwija szczegóły zamówienia (produkty, adresy, notatki) bezpośrednio na stronie listy, oszczędzając czas nawigacji. |
| Lista zamówień | Pole notatki klienta | N/A | Umożliwia zapisywanie notatek bezpośrednio z szybkiego podglądu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Szczegóły zamówienia nie rozwijają się, gdy klikam wiersz zamówienia. Co jest nie tak?**
O:

1.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Czasami stare pliki pamięci podręcznej uniemożliwiają ładowanie nowych skryptów modułu.
2.  **Moduł włączony:** Upewnij się, że moduł „Szybki Podgląd Zamówienia” jest włączony w **Moduły > Menedżer modułów**.
3.  **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany tak, aby był kompatybilny, bardzo mocno dostosowane motywy mogą czasami powodować zakłócenia. Sprawdź konsolę deweloperską przeglądarki (F12) pod kątem błędów JavaScript. Jeśli widzisz błędy związane z modułem, skontaktuj się z pomocą techniczną MyPresta.eu.
4.  **Wersja PrestaShop:** Upewnij się, że pobrałeś i zainstalowałeś poprawną wersję modułu dla Twojej konkretnej instalacji PrestaShop.

**P: Czy mogę dostosować, jakie informacje są wyświetlane w szybkim podglądzie?**
O: Moduł wyświetla podstawowe informacje, takie jak produkty i adresy. Dostosowanie wyświetlanych pól wymagałoby bezpośredniej modyfikacji plików szablonów modułu (`address.tpl`, `products.tpl`). Jest to zadanie na poziomie deweloperskim.

**P: Czy ten moduł wpływa na wydajność mojego sklepu?**
O: Nie, moduł jest zaprojektowany tak, aby był lekki. Ładuje dodatkową zawartość tylko wtedy, gdy wyraźnie klikniesz wiersz zamówienia w panelu administracyjnym. Nie dodaje żadnego obciążenia do Twojego front-office ani ogólnego przeglądania panelu administracyjnego.

**P: Używam starszej wersji PrestaShop 1.6, czy to będzie działać?**
O: Tak, moduł jest kompatybilny z PrestaShop 1.6.x. Upewnij się, że pobrałeś poprawny pakiet dla Twojej wersji PrestaShop ze swojego konta MyPresta.eu.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Szybki Podgląd Zamówienia” (`qov`) jest przede wszystkim modułem rozszerzającym Panel Administracyjny. Wykorzystuje mechanizm nadpisywania `AdminController` PrestaShop i szablony Smarty do wstrzykiwania dynamicznej zawartości do istniejącej listy „Zamówienia”. Używa JavaScript do obsługi żądań AJAX i manipulacji DOM w celu rozwijania/zwijania szczegółów zamówienia. Moduł nie wprowadza nowych tabel bazy danych ani złożonych struktur `ObjectModel`, skupiając się zamiast tego na rozszerzaniu istniejącej funkcjonalności PrestaShop.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Ten moduł jest wyłącznie narzędziem Panelu Administracyjnego.
-   **Kontrolery administracyjne Back-Office**:

    -   `qov/controllers/admin/AdminPreviewOrder.php`
        -   **Nazwa klasy i klasa nadrzędna**: `AdminPreviewOrderController` rozszerza `AdminOrdersController`.
        -   **Odpowiedzialność**: Ten kontroler nadpisuje domyślny `AdminOrdersController`, aby wstrzyknąć niezbędny JavaScript i potencjalnie zmodyfikować metodę `renderList()` w celu włączenia funkcji szybkiego podglądu. Jest odpowiedzialny za obsługę żądań AJAX, które pobierają szczegóły zamówienia (produkty, adresy) po kliknięciu wiersza zamówienia, oraz renderowanie szablonów `address.tpl` i `products.tpl` z pobranymi danymi. Zarządza również kluczem konfiguracji `QOV_TRACKING_EMAIL`, chociaż jego bezpośrednie użycie nie jest widoczne z dostarczonych informacji.

### 4.3 Klasy podstawowe i modele (`classes/`)

Brak. Moduł nie definiuje niestandardowych klas `ObjectModel` ani złożonych klas logiki biznesowej. Głównie współdziała z istniejącymi klasami podstawowymi PrestaShop, takimi jak `Order`, `Address`, `Product` itp., za pośrednictwem swojego kontrolera.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `qov/views/js/177-expand-all-imm.js`

    -   **Zakres**: Panel administracyjny (lista zamówień, PrestaShop 1.7.7+).
    -   **Opis**: Ten skrypt prawdopodobnie obsługuje natychmiastowe rozwijanie wszystkich szczegółów zamówienia na stronie listy zamówień, być może dla konkretnego widoku lub działania. Wiązałby zdarzenia kliknięcia z wierszami zamówień i wyzwalał wywołania AJAX w celu pobrania i wyświetlenia szczegółów dla wielu zamówień jednocześnie.
-   `qov/views/js/177-expand-all.js`

    -   **Zakres**: Panel administracyjny (lista zamówień, PrestaShop 1.7.7+).
    -   **Opis**: Podobnie jak `177-expand-all-imm.js`, ten skrypt jest odpowiedzialny za funkcję „rozwiń wszystko”. Słuchałby określonego wyzwalacza (np. kliknięcia przycisku), aby rozwinąć wszystkie widoczne szczegóły zamówienia na bieżącej stronie, wykonując żądania AJAX dla każdego zamówienia.
-   `qov/views/js/177orders-multiple.js`

    -   **Zakres**: Panel administracyjny (lista zamówień, PrestaShop 1.7.7+).
    -   **Opis**: Jest to podstawowy skrypt umożliwiający funkcję szybkiego podglądu. Wiąże zdarzenia kliknięcia z poszczególnymi wierszami zamówień na liście `AdminOrders`. Po kliknięciu wiersza zamówienia, zapobiega domyślnej nawigacji do pełnej strony zamówienia. Zamiast tego, wykonuje żądanie AJAX do `AdminPreviewOrderController` (lub podobnego punktu końcowego) w celu pobrania produktów, adresów i innych szczegółów zamówienia. Następnie dynamicznie wstrzykuje wyrenderowany kod HTML (z `address.tpl` i `products.tpl`) do nowego wiersza lub rozwiniętej sekcji pod klikniętym wierszem zamówienia. Obsługuje również zwijanie szczegółów po ponownym kliknięciu wiersza.
-   `qov/views/js/save-customer-note.js`

    -   **Zakres**: Panel administracyjny (lista zamówień, w szczególności w szybkim podglądzie).
    -   **Opis**: Ten skrypt obsługuje funkcjonalność zapisywania notatek klienta bezpośrednio z szybkiego podglądu zamówienia. Wiąże się z polami wejściowymi lub przyciskami w rozwiniętych szczegółach zamówienia. Gdy notatka zostanie wprowadzona lub zaktualizowana, wysyła żądanie AJAX do punktu końcowego panelu administracyjnego (prawdopodobnie `AdminPreviewOrderController` lub domyślnego `AdminOrdersController` z określoną akcją), aby utrwalić notatkę w bazie danych, zazwyczaj w tabeli `ps_order_note` lub podobnej.

### 4.5 Arkusze stylów CSS (`views/css/`)

Brak. Moduł nie zawiera niestandardowych plików CSS. Prawdopodobnie opiera się na istniejących stylach panelu administracyjnego PrestaShop lub stylach inline dla rozwiniętych szczegółów zamówienia. Deweloperzy, którzy chcą stylizować podgląd, powinni celować w dynamicznie wstrzykiwane elementy HTML.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `qov/views/templates/admin/address.tpl`
        -   **Opis**: Ten szablon służy do renderowania szczegółów adresu rozliczeniowego i wysyłkowego klienta w szybkim podglądzie zamówienia. Otrzymuje dane adresowe z `AdminPreviewOrderController` i formatuje je do wyświetlenia.
    -   `qov/views/templates/admin/products.tpl`
        -   **Opis**: Ten szablon jest odpowiedzialny za renderowanie listy produktów zamówionych przez klienta w szybkim podglądzie zamówienia. Otrzymuje dane produktów (nazwa, ilość, cena itp.) i wyświetla je w przejrzystym formacie tabelarycznym lub listowym.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Odczytuje i potencjalnie zapisuje (dla notatek klienta) do standardowych tabel PrestaShop, takich jak `ps_orders`, `ps_order_detail`, `ps_address`, `ps_customer` i `ps_order_note`.
    -   Wartości konfiguracyjne są przechowywane w `ps_configuration`, w szczególności `QOV_TRACKING_EMAIL`.
-   **Tabela zarejestrowanych hooków**:
    Moduł nie rejestruje jawnie żadnych hooków front-office (takich jak `displayHeader`, `displayRightColumn`, `displayProduct`, `displayFooter`), ponieważ jest to moduł back-office. Jego funkcjonalność jest głównie wstrzykiwana poprzez nadpisanie `AdminOrdersController` i dodanie JavaScriptu oraz szablonów do istniejącej strony „Zamówienia” w Panelu Administracyjnym.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje zasoby multimedialne. | Używany przez `AdminPreviewOrderController` do kolejkowania plików JavaScript (`177-expand-all-imm.js`, `177-expand-all.js`, `177orders-multiple.js`, `save-customer-note.js`) dla strony `AdminOrders`. |
| `displayAdminOrder` | Wykonywany na stronie zamówienia administracyjnego. | Chociaż nie jest jawnie wymieniony jako hook, podstawowa funkcjonalność modułu jest osiągana poprzez nadpisanie `AdminOrdersController` i modyfikację jego metody `renderList()` lub poprzez wstrzykiwanie treści za pomocą JavaScript do istniejącej listy zamówień. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Szybki Podgląd Zamówienia”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich pytań lub problemów, które mogą się pojawić.
"""
