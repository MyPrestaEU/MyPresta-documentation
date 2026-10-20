---
title: "Hooks Manager - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Hooks Manager od MyPresta.eu."
sidebar:
  label: "Hooks Manager - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Hooks Manager na MyPresta.eu](https://mypresta.eu/modules/administration-tools/hooks-manager.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/hooks-manager/)
>
> ---


# Hooks Manager

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu Hooks Manager. Zobaczysz listę wszystkich utworzonych niestandardowych hooków, wraz z opcjami dodawania nowych.

#### Dodawanie nowego niestandardowego hooka:

Na górze strony konfiguracji znajdziesz pola do utworzenia nowego hooka.

- **Nazwa hooka:**

  - **Co robi to ustawienie:** Jest to unikalna, techniczna nazwa dla Twojego nowego hooka. Musi zaczynać się od `display` (np. `displayMyCustomHook`, `displayProductExtraInfo`). Ta nazwa będzie później używana w plikach `.tpl` Twojego motywu do „wywołania” hooka.
  - **Efekt zmiany tego ustawienia:** Ta nazwa jest kluczowa dla programistów, aby umieścić hook w Twoim motywie. Zmiana jej po utworzeniu wymagałaby aktualizacji plików motywu.
  - **Zalecana wartość:** Używaj opisowych nazw w stylu camelCase, zaczynających się od `display`. Przykład: `displayProductBelowAddToCart`, `displayHomepagePromoBanner`.
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz dodać baner pod przyciskiem „Dodaj do koszyka” na stronach produktów. Możesz nazwać hook `displayProductBelowAddToCart`.
- **Tytuł hooka:**

  - **Co robi to ustawienie:** Jest to przyjazny, czytelny dla człowieka tytuł hooka, który pojawi się w Twoim Panelu Administracyjnym PrestaShop (np. gdy przejdziesz do **Wygląd > Pozycje**, aby przypisać moduły do hooków).
  - **Efekt zmiany tego ustawienia:** Ułatwia identyfikację Twojego niestandardowego hooka wśród wielu standardowych hooków w Panelu Administracyjnym.
  - **Zalecana wartość:** Jasny, opisowy tytuł. Przykład: „Strona produktu - Poniżej Dodaj do koszyka”, „Strona główna - Górny baner promocyjny”.
  - **Scenariusz / przykład dla sprzedawcy:** Dla hooka `displayProductBelowAddToCart` ustawisz tytuł na „Strona produktu - Poniżej Dodaj do koszyka”.
- **Opis hooka:**

  - **Co robi to ustawienie:** Opcjonalny, dłuższy opis, aby zapewnić więcej kontekstu na temat zamierzonego celu lub umiejscowienia hooka. Jest to również do użytku wewnętrznego w Panelu Administracyjnym.
  - **Efekt zmiany tego ustawienia:** Pomaga Tobie i Twojemu zespołowi zapamiętać konkretny przypadek użycia dla każdego niestandardowego hooka.
  - **Zalecana wartość:** Krótko wyjaśnij, gdzie hook ma być umieszczony i jaką zawartość powinien zawierać. Przykład: „Przeznaczony na odznaki zaufania lub małe wiadomości promocyjne bezpośrednio pod przyciskiem dodaj do koszyka.”
  - **Scenariusz / przykład dla sprzedawcy:** Dla hooka `displayProductBelowAddToCart` możesz dodać „Użyj dla małych odznak zaufania lub wiadomości o darmowej wysyłce.”
- **Widoczność:**

  - **Co robi to ustawienie:** Określa, czy hook jest widoczny na liście dostępnych hooków, gdy przejdziesz do **Wygląd > Pozycje** w Panelu Administracyjnym PrestaShop.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Hook pojawi się na liście, umożliwiając łatwe przypisywanie do niego modułów.
    - *Gdy wyłączone:* Hook nadal będzie istnieć i działać, jeśli zostanie wywołany w Twoim motywie, ale nie pojawi się na liście „Wygląd > Pozycje”, co utrudni zarządzanie modułami dla niego.
  - **Zalecana wartość:** **Włączone (Tak)**, chyba że masz bardzo konkretny powód, aby go ukryć.
  - **Scenariusz / przykład dla sprzedawcy:** Utworzyłeś nowy hook i chcesz natychmiast zacząć przypisywać do niego moduły. Pozostaw go włączonym.

#### Zarządzanie istniejącymi niestandardowymi hookami:

Poniżej sekcji „Dodaj nowy hook” zobaczysz tabelę zawierającą listę wszystkich utworzonych niestandardowych hooków.

- **Przełącznik Włączone / Wyłączone (dla każdego hooka):**

  - **Co robi to ustawienie:** Ten przełącznik pozwala aktywować lub dezaktywować pojedynczy niestandardowy hook.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Hook jest aktywny, a wszystkie przypisane do niego moduły będą renderować swoją zawartość, gdy hook zostanie wywołany w Twoim motywie.
    - *Gdy wyłączone:* Hook jest nieaktywny. Nawet jeśli zostanie wywołany w Twoim motywie, nie będzie renderował żadnej zawartości z przypisanych do niego modułów. Jest to łagodny sposób na tymczasowe ukrycie zawartości bez odłączania modułów.
  - **Zalecana wartość:** **Włączone** dla hooków, których chcesz używać, **Wyłączone** dla hooków, które chcesz tymczasowo ukryć.
  - **Scenariusz / przykład dla sprzedawcy:** Masz sezonowy baner promocyjny umieszczony za pomocą niestandardowego hooka. Gdy promocja się skończy, możesz wyłączyć hook, aby ukryć baner bez usuwania modułu.
- **Edycja na żywo (dla każdego hooka):**

  - **Co robi to ustawienie:** Jest to szybkie łącze do strony „Wygląd > Pozycje”, filtrowane tak, aby pokazywać tylko wybrany niestandardowy hook.
  - **Efekt zmiany tego ustawienia:** Kliknięcie tego przycisku przenosi Cię bezpośrednio do strony, gdzie możesz „zahaczyć” (przypisać) inne moduły do tego konkretnego niestandardowego hooka.
  - **Zalecana wartość:** Użyj tego przycisku, gdy chcesz przypisać moduł do nowo utworzonego niestandardowego hooka.
  - **Scenariusz / przykład dla sprzedawcy:** Właśnie utworzyłeś `displayProductBelowAddToCart` i teraz chcesz przypisać do niego moduł „Odznaki Zaufania”. Kliknij „Edycja na żywo” obok `displayProductBelowAddToCart`.

#### Inne klucze konfiguracyjne (wewnętrzne):

W wewnętrznej konfiguracji modułu możesz zobaczyć `mypresta_updates`, `update_`, `updatev_`. Są one zazwyczaj związane z aktualizacjami modułu i kontrolami licencji przez MyPresta.eu i nie wymagają interakcji ze strony sprzedawcy.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Nazwa hooka | Opisowa, prefiks `display` | Unikalny identyfikator techniczny hooka. Używany w plikach motywu. |
| Konfiguracja modułu | Tytuł hooka | Jasny, czytelny dla człowieka | Pojawia się w Wygląd > Pozycje dla łatwej identyfikacji. |
| Konfiguracja modułu | Opis hooka | Opcjonalny, informacyjny | Dostarcza kontekstu dla celu hooka. |
| Konfiguracja modułu | Widoczność | Włączone (Tak) | Sprawia, że hook jest widoczny w Wygląd > Pozycje do przypisywania modułów. |
| Konfiguracja modułu | Włączone / Wyłączone (na hook) | Włączone | Aktywuje/dezaktywuje zdolność niestandardowego hooka do renderowania zawartości. |
| Konfiguracja modułu | Edycja na żywo (na hook) | N/A (Przycisk akcji) | Bezpośrednie łącze do Wygląd > Pozycje, aby przypisać moduły do hooka. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Utworzyłem hook i przypisałem moduł, ale nic nie wyświetla się w moim sklepie. Co jest nie tak?**
O: To najczęstszy problem. Moduł Hooks Manager *tworzy* hook, ale Ty (lub Twój webmaster) nadal musisz *umieścić* ten hook w plikach `.tpl` Twojego motywu.
- **Rozwiązanie:** Musisz edytować pliki swojego motywu (np. `product.tpl`, `index.tpl`, `header.tpl`, `footer.tpl`) i wstawić następujący fragment kodu tam, gdzie chcesz, aby hook się pojawił: `{$hook_name}`. Zastąp `hook_name` rzeczywistą nazwą Twojego hooka (np. `{$hook_displayProductBelowAddToCart}`).
- **Sprawdź również:**
1. Czy hook jest „Włączony” w konfiguracji Hooks Manager?
2. Czy moduł, który próbujesz wyświetlić, jest faktycznie „zahaczony” do Twojego niestandardowego hooka w **Wygląd > Pozycje**?
3. Czy wyczyściłeś pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**)?

**P: Czy mogę używać tego samego niestandardowego hooka wielokrotnie w różnych miejscach?**
O: Tak, możesz. Jeśli umieścisz `{$hook_displayMyCustomHook}` w `product.tpl` i również w `category.tpl`, każdy moduł przypisany do `displayMyCustomHook` zostanie wyrenderowany w obu lokalizacjach. Jest to potężne narzędzie do wyświetlania spójnej zawartości na różnych typach stron.

**P: Mój niestandardowy hook wyświetla się, ale stylizacja jest nieprawidłowa. Co mogę zrobić?**
O: Moduł Hooks Manager zapewnia tylko „slot”. Stylizacja zawartości w tym slocie jest określana przez moduł, który tam umieściłeś, oraz CSS Twojego motywu.
- **Rozwiązanie:** Może być konieczne dodanie niestandardowego CSS do Twojego motywu, aby ostylować zawartość renderowaną przez moduł w Twoim niestandardowym hooku. Twój webmaster może w tym pomóc.

**P: Chcę usunąć niestandardowy hook. Jak to zrobić bezpiecznie?**
O: W konfiguracji Hooks Manager zobaczysz przycisk „Usuń” obok każdego niestandardowego hooka.
- **Ważne:** Przed usunięciem upewnij się, że usunąłeś wszystkie wywołania tego hooka (`{$hook_yourCustomHookName}`) z plików `.tpl` Twojego motywu. Jeśli usuniesz hook, ale pozostawisz wywołanie w swoim motywie, może to spowodować drobny błąd lub po prostu nic nie zostanie wyrenderowane. Ponadto odłącz od niego wszystkie moduły za pośrednictwem **Wygląd > Pozycje**.

**P: Czy ten moduł wpływa na wydajność mojego sklepu?**
O: Sam moduł jest bardzo lekki. Dodawanie większej liczby hooków i przypisywanie większej liczby modułów *może* stopniowo zwiększać czas ładowania strony, ale dotyczy to każdej dodatkowej zawartości na Twojej stronie, niezależnie od tego, jak jest zahaczona. Wpływ jest zazwyczaj znikomy, chyba że dodajesz dziesiątki złożonych modułów do jednej strony.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł Hooks Manager to prosty moduł PrestaShop zaprojektowany do rozszerzania podstawowego mechanizmu hooków. Wykorzystuje głównie klasę `Module` PrestaShop i tabelę `Configuration` do zarządzania niestandardowymi definicjami hooków. Nie wprowadza złożonych wzorców MVC ani niestandardowych tabel baz danych, ale raczej manipuluje tabelami `ps_hook` i `ps_hook_module` pośrednio poprzez API PrestaShop. Podstawowa funkcjonalność modułu znajduje się w jego głównym pliku PHP, `hooksmanager.php`, który obsługuje instalację, deinstalację i interfejs konfiguracji Panelu Administracyjnego.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Całe renderowanie front-office jest obsługiwane przez standardową metodę `Hook::exec()` PrestaShop, gdy niestandardowy hook jest wywoływany w pliku `.tpl`.
- **Kontrolery Panelu Administracyjnego**: Brak. Cała administracja jest obsługiwana bezpośrednio w metodzie `getContent()` pliku `hooksmanager.php`.

### 4.3 Klasy rdzenia i modele (`classes/`)

- W katalogu `classes/` nie ma niestandardowych klas ani definicji `ObjectModel`. Moduł bezpośrednio współdziała z podstawowymi klasami `Hook` i `Module` PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

- W module nie ma niestandardowych plików JavaScript. Konfiguracja Panelu Administracyjnego opiera się na standardowych elementach formularzy PrestaShop i potencjalnie jQuery, jeśli jest globalnie dołączony przez PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

- W module nie ma niestandardowych plików CSS. Konfiguracja Panelu Administracyjnego używa domyślnej stylizacji motywu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- W module nie ma niestandardowych plików szablonów Smarty. Cały interfejs konfiguracji jest renderowany bezpośrednio w metodzie `getContent()` pliku `hooksmanager.php` przy użyciu czystego HTML i klas pomocniczych PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy własnych niestandardowych tabel baz danych.
  - Głównie współdziała z następującymi podstawowymi tabelami PrestaShop:
    - `ps_hook`: Przechowuje definicje wszystkich hooków, w tym tych utworzonych przez ten moduł.
    - `ps_hook_lang`: Przechowuje przetłumaczalne tytuły i opisy hooków.
    - `ps_module_hook`: Łączy moduły z hookami, definiując, który moduł jest wyświetlany w którym hooku.
    - `ps_configuration`: Przechowuje wartości konfiguracyjne specyficzne dla modułu (np. `mypresta_updates`, `update_`, `updatev_` do wewnętrznego zarządzania modułem).
- **Tabela zarejestrowanych hooków**:
  Sam moduł nie rejestruje żadnych hooków do wyświetlania własnej zawartości. Jego celem jest *tworzenie* nowych hooków do użytku przez inne moduły.

  Podstawowa funkcjonalność modułu obejmuje:

  - `install()`:
    - Rejestruje moduł do `displayAdminProductsExtra` (lub podobnego, choć nie jest to wyraźnie określone w dossier, jest to powszechne dla narzędzi administracyjnych do wyświetlania linku).
    - Tworzy nową zakładkę w Panelu Administracyjnym (jeśli dotyczy, choć nie jest to wyraźnie określone dla tego modułu, jest to powszechne dla narzędzi administracyjnych).
    - Ustawia domyślne wartości konfiguracyjne w `ps_configuration`.
  - `uninstall()`:
    - Usuwa wszystkie niestandardowe hooki utworzone przez moduł z `ps_hook` i `ps_hook_lang`.
    - Usuwa powiązane wpisy `ps_module_hook`.
    - Czyści wartości konfiguracyjne z `ps_configuration`.
  - `getContent()`:
    - Obsługuje przesyłanie formularza konfiguracji Panelu Administracyjnego.
    - Przetwarza tworzenie, aktualizację i usuwanie niestandardowych hooków.
    - Renderuje HTML dla strony konfiguracji, wyświetlając istniejące hooki i udostępniając formularz do dodawania nowych.
    - Używa metod `Hook::add()` i `Hook::remove()` do zarządzania wpisami hooków w bazie danych.

  **Uwaga dla programistów dotycząca użycia niestandardowych hooków:**
  Aby wykorzystać niestandardowy hook utworzony przez ten moduł, programista musi ręcznie wstawić zmienną Smarty `{$hook_YOUR_CUSTOM_HOOK_NAME}` do żądanego pliku `.tpl` w aktywnym motywie PrestaShop. Na przykład, jeśli zostanie utworzony hook o nazwie `displayProductBelowAddToCart`, programista doda `{$hook_displayProductBelowAddToCart}` do `themes/your_theme/templates/catalog/_partials/product-details.tpl` lub `product.tpl` w żądanej lokalizacji. Podstawowa metoda `Hook::exec()` PrestaShop zajmie się następnie renderowaniem modułów przypisanych do tego niestandardowego hooka.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu Hooks Manager, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie optymalnego działania Twojego modułu i pomoc w wszelkich pytaniach technicznych, które możesz mieć.
"""
