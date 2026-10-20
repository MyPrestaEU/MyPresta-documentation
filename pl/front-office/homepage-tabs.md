---
title: "Zakładki na stronie głównej - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Zakładki na stronie głównej” od MyPresta.eu."
sidebar:
  label: "Zakładki na stronie głównej - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Homepage tabs na MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tabs.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/homepage-tabs/)
>
> ---


# Zakładki na stronie głównej

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne nietypowe konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Zakładki na stronie głównej” w Menedżerze modułów. Spowoduje to przejście do głównego ekranu konfiguracji.

Strona konfiguracji modułu jest prosta, skupia się głównie na zapewnieniu, że moduł może otrzymywać aktualizacje.

- **Co robi to ustawienie:** Ta sekcja zarządza zdolnością modułu do sprawdzania i otrzymywania aktualizacji z MyPresta.eu. Utrzymywanie modułów w aktualności jest kluczowe dla bezpieczeństwa, wydajności i kompatybilności z nowymi wersjami PrestaShop.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (domyślnie):* Moduł będzie okresowo sprawdzał MyPresta.eu pod kątem nowych wersji. Jeśli aktualizacja jest dostępna, zostaniesz powiadomiony w panelu administracyjnym PrestaShop, co pozwoli Ci łatwo pobrać i zainstalować najnowszą wersję. Zapewnia to, że Twój moduł pozostaje kompatybilny i korzysta z najnowszych funkcji i poprawek błędów.
  - *Gdy wyłączone:* Moduł nie będzie sprawdzał aktualizacji. Nie zostaniesz powiadomiony o nowych wersjach, potencjalnie tracąc ważne ulepszenia, poprawki bezpieczeństwa lub poprawki kompatybilności. Musiałbyś ręcznie sprawdzać aktualizacje na MyPresta.eu.
- **Zalecana wartość:** **TAK (Włączone)**. Zdecydowanie zaleca się pozostawienie tego ustawienia włączonego, aby zapewnić, że Twój moduł jest zawsze aktualny i bezpieczny.
- **Scenariusz/przykład sprzedawcy:** Wyobraź sobie, że PrestaShop wydaje nową mniejszą wersję (np. 8.1.5). Może zostać wydana aktualizacja modułu „Zakładki na stronie głównej”, aby zapewnić pełną kompatybilność. Przy włączonych aktualizacjach zostaniesz powiadomiony i będziesz mógł łatwo zaktualizować, zapobiegając wszelkim potencjalnym problemom. Jeśli wyłączone, Twoje zakładki mogą przestać działać poprawnie po aktualizacji PrestaShop, a Ty nie będziesz wiedział dlaczego, dopóki ręcznie nie sprawdzisz aktualizacji modułu.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Sprawdzanie aktualizacji (mypresta\_updates, update\_, updatev\_) | TAK (Włączone) | Włącza automatyczne sprawdzanie aktualizacji modułu z MyPresta.eu, zapewniając kompatybilność, bezpieczeństwo i dostęp do nowych funkcji. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje zakładki na stronie głównej nie wyświetlają się po instalacji.**
O:

1. **Sprawdź pozycję modułu:** Przejdź do **Wygląd > Pozycje** w panelu administracyjnym PrestaShop. Wyszukaj `displayHome`. Upewnij się, że moduł „Zakładki na stronie głównej” jest podpięty do `displayHome`. Jeśli go tam nie ma, użyj przycisku „Przeszczep moduł”, aby go dodać.
2. **Wyczyść pamięć podręczną:** Zawsze czyść pamięć podręczną PrestaShop po zainstalowaniu lub skonfigurowaniu modułów. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
3. **Sprawdź konflikty z motywem:** Niektóre niestandardowe motywy mogą nadpisywać hook `displayHome` lub mieć specyficzne style, które ukrywają moduł. Tymczasowo przełącz się na domyślny motyw PrestaShop (Classic), aby sprawdzić, czy zakładki się pojawiają. Jeśli tak, Twój motyw wymaga niestandardowych dostosowań CSS lub szablonu.

**P: Produkty w zakładkach nie wyglądają prawidłowo (np. zły rozmiar, niewyrównane).**
O: Jest to zazwyczaj problem ze stylizacją związany z motywem Twojego sklepu. Sam moduł dostarcza dane produktów, ale Twój motyw decyduje o tym, jak wyświetlane są listy produktów.

1. **Wyczyść pamięć podręczną:** Ponownie wyczyść pamięć podręczną PrestaShop.
2. **CSS motywu:** CSS Twojego motywu może kolidować z domyślną stylizacją modułu. Deweloper stron internetowych może zbadać elementy za pomocą narzędzi deweloperskich przeglądarki i zastosować niestandardowe nadpisania CSS w pliku `custom.css` Twojego motywu, aby poprawić wygląd.

**P: Czy mogę zmienić kolejność zakładek lub produkty, które się w nich pojawiają?**
O: Ten moduł przywraca *funkcjonalność* zakładek na stronie głównej (Popularne, Nowe, Bestsellery, W promocji). Konkretne typy produktów wyświetlane (np. „Popularne produkty”) są określane przez podstawową logikę PrestaShop dla tych kategorii. Ten moduł nie oferuje opcji ręcznego wyboru produktów dla każdej zakładki ani zmiany kolejności samych zakładek poprzez swoją konfigurację. W przypadku zaawansowanych dostosowań, takich jak niestandardowe wybory produktów lub kolejność zakładek, zazwyczaj potrzebny byłby bardziej zaawansowany moduł lub niestandardowe opracowanie.

**P: Moduł jest zainstalowany, ale nie widzę żadnych opcji konfiguracji poza ustawieniami aktualizacji.**
O: Ten moduł został zaprojektowany w celu ponownego włączenia podstawowej funkcji zakładek na stronie głównej PrestaShop, która została usunięta. Jego główną funkcją jest ponowne wyświetlanie zakładek, wykorzystując domyślną logikę PrestaShop dla produktów „Popularne”, „Nowe”, „Bestsellery” i „W promocji”. Dlatego nie posiada on rozbudowanych opcji konfiguracji do zarządzania treścią w samych zakładkach, ponieważ ta logika jest obsługiwana przez rdzeń PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Zakładki na stronie głównej” (`homepagetabs`) to lekki moduł PrestaShop zaprojektowany w celu ponownego włączenia podstawowej funkcji front-office, która została usunięta w nowszych wersjach PrestaShop. Działa głównie poprzez podpięcie się do `displayHome` w celu renderowania zakładek produktów i `displayHeader` w celu dołączenia niezbędnych zasobów. Wykorzystuje istniejące mechanizmy pobierania produktów PrestaShop dla produktów „Popularne”, „Nowe”, „Bestsellery” i „W promocji”, skutecznie działając jako most do przywrócenia komponentu wizualnego. Moduł stosuje standardowy wzorzec MVC PrestaShop, choć jego główna logika znajduje się w głównej klasie modułu (`homepagetabs.php`) do renderowania.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Logika wyświetlania front-office modułu jest w całości obsługiwana przez plik modułu `homepagetabs.php` za pośrednictwem hooków.
- **Kontrolery Back-Office Admin**: Brak. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównej klasy modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

- Brak. Moduł nie definiuje żadnych niestandardowych klas ani instancji `ObjectModel`. Opiera się na podstawowych klasach PrestaShop do pobierania danych produktów.

### 4.4 Zasoby JavaScript (`views/js/`)

- `homepagetabs/views/js/homepagetabs.js`
  - **Zakres**: Front-office.
  - **Odpowiedzialność**: Ten skrypt jest odpowiedzialny za interaktywne zachowanie zakładek na stronie głównej. Prawdopodobnie obsługuje:
    - Wiązanie słuchaczy zdarzeń kliknięcia z nagłówkami zakładek.
    - Przełączanie widoczności bloków treści produktów na podstawie aktywnej zakładki.
    - Dodawanie/usuwanie aktywnych klas CSS do nagłówków i treści zakładek.
    - Potencjalnie obsługę żądań AJAX, jeśli treść produktu jest ładowana dynamicznie (chociaż dla tego modułu jest to bardziej prawdopodobne, że jest to prosty mechanizm pokazywania/ukrywania wstępnie renderowanej treści).
    - Zapewnienie prawidłowego działania zakładek na różnych rozmiarach ekranu i urządzeniach.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `homepagetabs/views/css/homepagetabs.css`
  - **Zakres**: Stylizacja klienta front-office.
  - **Odpowiedzialność**: Ten arkusz stylów zapewnia domyślną prezentację wizualną zakładek na stronie głównej i ich zawartości. Definiuje style dla:
    - Samego kontenera zakładek.
    - Poszczególnych nagłówków zakładek (np. `ul.home-tabs li a`).
    - Stanu aktywnej zakładki (np. `ul.home-tabs li.active a`).
    - Kontenera siatki produktów dla każdej zakładki (np. `.tab-content`).
    - Podstawowych dostosowań responsywnych dla różnych rozmiarów ekranu.
  - **Kluczowe selektory klas CSS, które programiści mogą nadpisać**: Programiści mogą celować w klasy takie jak `.home-tabs`, `.home-tabs li`, `.home-tabs li.active`, `.tab-content` i elementy siatki produktów w `.tab-content`, aby bezproblemowo zintegrować wygląd modułu z ich niestandardowym motywem.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:
  - `homepagetabs/views/templates/hook/homepagetabs.tpl`
    - **Hook**: `displayHome`
    - **Cel**: Jest to główny szablon front-office odpowiedzialny za renderowanie całego bloku zakładek na stronie głównej. Będzie zawierał strukturę HTML dla nagłówków zakładek (np. `<ul>` dla tytułów zakładek) i odpowiadających im obszarów treści (np. `<div>` dla list produktów). Iteruje przez dane produktów przekazane mu przez metodę `hookDisplayHome()` modułu, wyświetlając produkty „Popularne”, „Nowe”, „Bestsellery” i „W promocji” w ich odpowiednich obszarach treści zakładek. Ten szablon jest miejscem, w którym renderowane są karty produktów (obrazy, nazwy, ceny, przyciski dodawania do koszyka) dla każdego typu produktu.
- **Szablony administracyjne (`views/templates/admin/`)**:
  - `homepagetabs/views/templates/admin/homepagetabs.tpl`
    - **Cel**: Ten szablon renderuje formularz konfiguracji modułu w panelu administracyjnym PrestaShop. Wyświetla ustawienia związane ze sprawdzaniem aktualizacji (`mypresta_updates`, `update_`, `updatev_`) i wszelkie inne standardowe elementy konfiguracji modułu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**: Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoje ustawienia konfiguracyjne (np. `mypresta_updates`) w standardowej tabeli `ps_configuration`.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHome` | Renderuje zawartość na stronie głównej sklepu. | Ten hook jest używany do wyprowadzania całej struktury HTML zakładek na stronie głównej, w tym nagłówków zakładek i list produktów. |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony front-office. | Ten hook jest używany do dołączania plików CSS (`homepagetabs.css`) i JavaScript (`homepagetabs.js`) modułu, zapewniając prawidłową stylizację i interaktywną funkcjonalność zakładek. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dalszej pomocy z modułem „Zakładki na stronie głównej” prosimy odwiedzić swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich pytań lub problemów, które mogą się pojawić.
"""
