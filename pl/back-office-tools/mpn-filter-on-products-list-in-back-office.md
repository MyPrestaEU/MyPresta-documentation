---
title: "Filtr MPN na liście produktów w panelu administracyjnym - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Filtr MPN na liście produktów w panelu administracyjnym” od MyPresta.eu."
sidebar:
  label: "Filtr MPN na liście produktów w panelu administracyjnym - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł MPN filter on products list in back office na MyPresta.eu](https://mypresta.eu/modules/administration-tools/mpn-filter-on-products-list-in-back-office.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/mpn-filter-on-products-list-in-back-office/)
>
> ---


# Filtr MPN na liście produktów w panelu administracyjnym

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i domyślnie włączone w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Ten moduł jest zaprojektowany jako plug-and-play. Nie posiada dedykowanego ekranu konfiguracji z ustawieniami do dostosowania. Po instalacji moduł automatycznie integruje kolumnę MPN i możliwości filtrowania z listą produktów.

Po instalacji zobaczysz standardowy przycisk „Konfiguruj”, ale kliknięcie go zazwyczaj wyświetli prostą wiadomość informującą, że moduł jest aktywny i nie wymaga dalszej konfiguracji.

**Jak korzystać z modułu po instalacji:**

1. Przejdź do **Katalog > Produkty** w panelu administracyjnym PrestaShop.
2. Zobaczysz teraz nową kolumnę z etykietą „MPN” na liście produktów.
3. Możesz kliknąć nagłówek kolumny „MPN”, aby posortować produkty według MPN w kolejności rosnącej lub malejącej.
4. Nad listą produktów, w sekcji filtrów, znajdziesz nowe pole wprowadzania pod kolumną „MPN”. Możesz wpisać MPN (lub jego część) w to pole i nacisnąć Enter lub kliknąć przycisk „Filtruj”, aby przefiltrować listę produktów według tego MPN.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | (Brak konfigurowalnych ustawień) | N/A | Moduł działa automatycznie po instalacji, dodając kolumnę MPN i filtr do Katalog > Produkty. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zainstalowałem moduł, ale nie widzę kolumny MPN na liście produktów.**
O: Najpierw upewnij się, że przeglądasz stronę „Katalog > Produkty” w panelu administracyjnym PrestaShop. Jeśli nadal nie jest widoczna, spróbuj wyczyścić pamięć podręczną PrestaShop:
1. Przejdź do **Zaawansowane > Wydajność**.
2. Kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
3. Wyczyść również pamięć podręczną przeglądarki.
4. Jeśli problem nadal występuje, upewnij się, że moduł jest włączony w Menedżerze modułów.

**P: Czy mogę użyć tego modułu do dodania MPN do front-office dla klientów?**
O: Nie, ten moduł jest przeznaczony wyłącznie do administracji w panelu administracyjnym. Nie modyfikuje front-office ani nie wyświetla MPN klientom. Do wyświetlania MPN w front-office potrzebny byłby oddzielny moduł lub niestandardowe rozwiązanie.

**P: Czy ten moduł tworzy nowe pola bazy danych dla MPN?**
O: Nie, PrestaShop ma już pole `mpn` w tabeli `ps_product`. Ten moduł po prostu sprawia, że to istniejące pole jest widoczne i możliwe do filtrowania na liście produktów w panelu administracyjnym. Nie dodaje nowych tabel ani pól bazy danych.

**P: Filtr nie działa lub kolumna nie sortuje się poprawnie.**
O: Może to być problem z pamięcią podręczną lub konflikt z innym modułem, który modyfikuje listę produktów.
1. Wyczyść pamięć podręczną PrestaShop (jak opisano powyżej).
2. Jeśli masz inne moduły, które mocno dostosowują stronę „Katalog > Produkty”, spróbuj tymczasowo wyłączyć je jeden po drugim, aby zidentyfikować konflikt.
3. Upewnij się, że Twoja wersja PrestaShop jest w pełni kompatybilna z pobraną wersją modułu.

**P: Jak wprowadzić lub edytować MPN dla produktu?**
O: MPN edytujesz bezpośrednio na stronie edycji produktu:
1. Przejdź do **Katalog > Produkty**.
2. Kliknij „Edytuj” obok produktu, który chcesz zmodyfikować.
3. Przejdź do zakładki „Ilości” (lub „Ustawienia podstawowe” w starszych wersjach).
4. Znajdziesz tam pole „MPN (Numer Części Producenta)”. Wprowadź lub zaktualizuj wartość i zapisz produkt. Nowy MPN pojawi się wtedy na liście produktów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Filtr MPN na liście produktów w panelu administracyjnym” to lekki moduł PrestaShop, zaprojektowany głównie w celu rozszerzenia istniejącej funkcjonalności listy produktów w panelu administracyjnym. Osiąga to poprzez nadpisywanie konkretnych szablonów Twig odpowiedzialnych za renderowanie strony katalogu produktów w PrestaShop 1.7.x, 8.x i 9.x. Nie wprowadza nowych kontrolerów, modeli ani złożonych zasobów JavaScript/CSS. Jego podstawową funkcją jest wstrzyknięcie kolumny MPN i powiązanego z nią filtra do standardowego widoku listy produktów.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Cała jego funkcjonalność jest osiągana poprzez nadpisywanie szablonów i podstawowe mechanizmy modułów PrestaShop.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas PHP ani definicji `ObjectModel`. Wykorzystuje istniejący `ObjectModel` `Product` i jego pole `mpn`.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Funkcjonalność filtrowania i sortowania dla nowej kolumny MPN jest obsługiwana przez istniejącą implementację DataTables.js w PrestaShop dla listy produktów, która automatycznie dostosowuje się do nowych kolumn.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Stylizacja nowej kolumny MPN i pola filtra będzie dziedziczona bezpośrednio z Twojego motywu panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Głównym mechanizmem modułu jest nadpisywanie podstawowych szablonów Twig panelu administracyjnego PrestaShop w celu wstrzyknięcia kolumny MPN.

- **`mpnmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`**:
  - **Cel**: Ten szablon jest bezpośrednim nadpisaniem podstawowego szablonu listy produktów PrestaShop (`admin-dev/themes/new-theme/template/catalog/products/list.html.twig` lub podobna ścieżka w zależności od wersji PS).
  - **Funkcjonalność**: Modyfikuje strukturę listy produktów, aby uwzględnić nagłówek kolumny MPN i odpowiadające mu pole wprowadzania filtra. Zapewnia, że pole MPN jest rozpoznawane jako kolumna sortowalna i filtrowalna w konfiguracji DataTables.
- **`mpnmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`**:
  - **Cel**: Ten szablon jest bezpośrednim nadpisaniem podstawowego szablonu tabeli produktów PrestaShop (`admin-dev/themes/new-theme/template/catalog/products/products_table.html.twig` lub podobna ścieżka).
  - **Funkcjonalność**: Modyfikuje wiersze tabeli, aby wyświetlać rzeczywistą wartość MPN dla każdego produktu w nowo dodanej kolumnie. Dostęp do właściwości `product.mpn` z danych produktu przekazanych do szablonu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**: Ten moduł nie tworzy żadnych nowych tabel bazy danych. Opiera się na istniejącej kolumnie `mpn` w tabeli `ps_product` (lub `ps_product_shop` dla MPN specyficznych dla sklepu, choć zazwyczaj znajduje się w `ps_product`).
- **Tabela zarejestrowanych hooków**: Ten moduł nie rejestruje jawnie żadnych nowych hooków. Jego funkcjonalność jest osiągana poprzez nadpisywanie szablonów. Chociaż nie używa `displayHeader`, `displayRightColumn`, `actionValidateOrder` itp., w swojej metodzie `install()` prawdopodobnie rejestruje się do nadpisywania szablonów, co jest niejawną formą włączania się w proces renderowania.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkich zapytań dotyczących modułu „Filtr MPN na liście produktów w panelu administracyjnym”, prosimy o zapoznanie się z kontem klienta MyPresta.eu. Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.

- **MyPresta.eu Historia zamówień i pobieranie**: <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Kontakt z pomocą techniczną**: <https://mypresta.eu/contact>
