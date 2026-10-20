---
title: "Filtr UPC na liście produktów w panelu administracyjnym - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Filtr UPC na liście produktów w panelu administracyjnym” od MyPresta.eu."
sidebar:
  label: "Filtr UPC na liście produktów w panelu administracyjnym - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł UPC filter on products list in back office na MyPresta.eu](https://mypresta.eu/modules/administration-tools/upc-filter-on-products-list-in-back-office.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/upc-filter-on-products-list-in-back-office/)
>
> ---


# Filtr UPC na liście produktów w panelu administracyjnym

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Ten moduł został zaprojektowany jako plug-and-play. Nie posiada dedykowanego ekranu konfiguracji z ustawieniami do dostosowania. Po zainstalowaniu moduł automatycznie integruje kolumnę UPC i filtr z listą produktów w panelu administracyjnym.

Nową funkcjonalność znajdziesz, przechodząc do:
**Panel administracyjny > Katalog > Produkty**

Na tej stronie zobaczysz teraz:

- Nową kolumnę oznaczoną „UPC” wyświetlającą kod UPC dla każdego produktu.
- Nowe pole filtra na górze kolumny „UPC”, umożliwiające wpisanie kodu UPC (lub jego części) w celu filtrowania listy produktów.

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zainstalowałem moduł, ale nie widzę kolumny UPC ani filtra na liście produktów.**
O:
\* **Wyczyść pamięć podręczną:** Najczęstszym rozwiązaniem jest wyczyszczenie pamięci podręcznej PrestaShop. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
\* **Sprawdź status modułu:** Upewnij się, że moduł jest włączony. Przejdź do **Moduły > Menedżer modułów**, wyszukaj „Filtr UPC na liście produktów w panelu administracyjnym” i sprawdź, czy jest aktywny.
\* **Kompatybilność z motywem:** Chociaż rzadko zdarza się to w przypadku modułów panelu administracyjnego, wysoce dostosowany motyw administracyjny *może* potencjalnie zakłócać działanie. Jeśli wyczyszczenie pamięci podręcznej nie zadziała, tymczasowo przełącz się na domyślny motyw administracyjny PrestaShop, aby sprawdzić, czy kolumna się pojawi.
\* **Pozycja modułu:** Ten moduł modyfikuje istniejące szablony. Upewnij się, że moduł jest poprawnie zainstalowany i nie wyświetla żadnych błędów podczas instalacji.

**P: Kolumna UPC jest widoczna, ale niektóre produkty nie wyświetlają kodu UPC.**
O: Ten moduł po prostu wyświetla kod UPC, który jest już przechowywany w informacjach o produkcie. Jeśli produkt nie wyświetla kodu UPC, oznacza to, że pole UPC dla tego konkretnego produktu w Twoim katalogu PrestaShop jest puste. Musisz edytować produkt (Katalog > Produkty > Edytuj produkt > zakładka Ilości) i tam wprowadzić kod UPC.

**P: Czy mogę zmienić pozycję kolumny UPC?**
O: Moduł integruje kolumnę UPC w określonej pozycji w tabeli listy produktów. W module nie ma opcji konfiguracji, aby zmienić jej pozycję. Wymagałoby to niestandardowych modyfikacji szablonu (patrz Przewodnik dla programistów).

**P: Czy ten moduł dodaje pola UPC do produktów, jeśli ich nie ma?**
O: Nie, ten moduł zakłada, że Twoja instalacja PrestaShop ma już standardowe pole UPC dostępne dla produktów (co jest domyślne). Wyświetla i filtruje tylko na podstawie danych, które już wprowadziłeś do tego pola.

**P: Czy ten moduł spowolni mój panel administracyjny?**
O: Moduł jest wysoce zoptymalizowany. Wykorzystuje istniejące mechanizmy filtrowania PrestaShop i dodaje tylko proste wyświetlanie kolumny. Nie powinien zauważalnie wpływać na wydajność listy produktów w panelu administracyjnym.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów, którzy chcą zrozumieć, debugować lub rozszerzyć moduł „Filtr UPC na liście produktów w panelu administracyjnym”.

### 4.1 Przegląd architektury

Moduł działa głównie poprzez nadpisywanie określonych szablonów Twig używanych dla listy katalogu produktów w panelu administracyjnym PrestaShop. Wstrzykuje niezbędny kod HTML dla nagłówka kolumny UPC i pola filtra, a następnie modyfikuje szablon wiersza produktu, aby wyświetlić wartość UPC. Logika filtrowania jest obsługiwana przez natywny kontroler `AdminProducts` PrestaShop, który automatycznie rozpoznaje pole `upc` do filtrowania, gdy jest ono obecne w szablonie.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Jego funkcjonalność jest osiągana poprzez nadpisywanie szablonów i wykorzystywanie istniejącej logiki kontrolera PrestaShop.

### 4.3 Klasy i modele rdzenia (`classes/`)

Ten moduł **nie** wprowadza żadnych niestandardowych klas PHP ani definicji `ObjectModel`. Bezpośrednio współdziała z istniejącymi danymi produktów PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript. Funkcjonalność filtrowania jest obsługiwana po stronie serwera przez kontroler `AdminProducts` PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików CSS. Opiera się na domyślnych stylach panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł wykorzystuje nowy silnik szablonów Twig wprowadzony w PrestaShop 1.7+ dla stron panelu administracyjnego. Nadpisuje dwa podstawowe szablony listy produktów:

- **`upcmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/list.html.twig`**

  - **Cel:** Ten szablon jest odpowiedzialny za renderowanie głównej strony katalogu produktów, w tym nagłówka tabeli i formularza wyszukiwania/filtrowania.
  - **Modyfikacja:** Moduł wstrzykuje nowy element `<th>` dla kolumny „UPC” do nagłówka tabeli i odpowiadające mu pole wejściowe do filtrowania do formularza wyszukiwania. Pozwala to na rozpoznanie pola `upc` przez kontroler `AdminProducts` do filtrowania.
- **`upcmypresta/views/PrestaShop/Admin/Product/CatalogPage/Lists/products_table.html.twig`**

  - **Cel:** Ten szablon jest odpowiedzialny za renderowanie poszczególnych wierszy tabeli listy produktów.
  - **Modyfikacja:** Moduł dodaje nowy element `<td>` w pętli produktów, aby wyświetlić wartość `product.upc` dla każdego produktu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**: Ten moduł **nie** tworzy żadnych niestandardowych tabel bazy danych. Odczytuje pole `upc` ze standardowej tabeli `ps_product`.
- **Tabela zarejestrowanych hooków**: Ten moduł **nie** rejestruje żadnych specyficznych hooków w tradycyjnym sensie PrestaShop (np. `displayHeader`, `actionValidateOrder`). Jego integracja jest osiągana wyłącznie poprzez nadpisywanie szablonów Twig, które są formą niejawnego „zahaczania” w proces renderowania.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Filtr UPC na liście produktów w panelu administracyjnym”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu.
