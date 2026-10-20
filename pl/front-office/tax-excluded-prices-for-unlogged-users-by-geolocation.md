---
title: "Ceny bez podatku dla niezalogowanych użytkowników według geolokalizacji - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Ceny bez podatku dla niezalogowanych użytkowników według geolokalizacji” od MyPresta.eu."
sidebar:
  label: "Ceny bez podatku dla niezalogowanych użytkowników według geolokalizacji - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Tax excluded prices for unlogged users by geolocation na MyPresta.eu](https://mypresta.eu/modules/front-office-features/tax-excluded-prices-for-unlogged-users-by-geolocation.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/tax-excluded-prices-for-unlogged-users-by-geolocation/)
>
> ---


# Ceny bez podatku dla niezalogowanych użytkowników według geolokalizacji

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Ten moduł działa głównie poprzez nadpisywanie podstawowej logiki cenowej PrestaShop, co oznacza, że jego konfiguracja jest zazwyczaj minimalna lub nawet automatyczna. Metoda `getContent()` w głównym pliku modułu zazwyczaj obsługuje wyświetlanie standardowego formularza konfiguracji, ale dla tego konkretnego modułu podstawowa funkcjonalność jest osiągana poprzez nadpisywanie klas, a nie poprzez obszerne ustawienia.

Jeśli ekran konfiguracji jest obecny, zazwyczaj oferowałby opcje związane z włączaniem/wyłączaniem modułu lub dostrajaniem jego zachowania geolokalizacyjnego. Jednakże, na podstawie opisu modułu i struktury plików, jego główną funkcją jest *automatyczne* dostosowywanie cen w oparciu o geolokalizację bez wymagania złożonych ustawień dla sprzedawcy.

Dlatego ekran konfiguracji dla tego modułu jest prawdopodobnie bardzo prosty, być może tylko przełącznik „Włącz/Wyłącz”, lub może nawet nie mieć dedykowanego formularza konfiguracji, jeśli jego zachowanie jest całkowicie automatyczne po zainstalowaniu.

**Jeśli ekran konfiguracji istnieje, zazwyczaj zawierałby:**

-   **Włącz/Wyłącz moduł:**

    -   **Co robi to ustawienie:** Jest to standardowy przełącznik do włączania lub wyłączania funkcjonalności modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Moduł będzie aktywnie wykrywał lokalizacje niezalogowanych użytkowników i odpowiednio dostosowywał wyświetlanie cen (z podatkiem/bez podatku).
        -   *Gdy wyłączony:* PrestaShop powróci do swojego domyślnego zachowania dla niezalogowanych użytkowników, zazwyczaj pokazując ceny w oparciu o domyślny kraj sklepu lub ustawienie globalne, bez dostosowań opartych na geolokalizacji.
    -   **Zalecana wartość:** TAK (aby wykorzystać podstawową funkcjonalność modułu).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli tymczasowo potrzebujesz rozwiązać problem z cenami lub wolisz domyślne zachowanie PrestaShop przez krótki okres, możesz go wyłączyć. W przeciwnym razie pozostaw go włączonym, aby uzyskać dokładne ceny międzynarodowe.
-   **Dostawca usług geolokalizacyjnych (hipotetycznie):**

    -   **Co robi to ustawienie:** Jeśli moduł oferowałby wybór, pozwoliłoby to wybrać, której zewnętrznej usługi używa do wykrywania adresów IP odwiedzających i mapowania ich na kraje.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiono na Dostawcę A:* Moduł używa bazy danych Dostawcy A do mapowania IP na kraj.
        -   *Gdy ustawiono na Dostawcę B:* Moduł używa bazy danych Dostawcy B, potencjalnie oferując inną dokładność lub szybkość.
    -   **Zalecana wartość:** Domyślny lub zalecany dostawca przez MyPresta.eu.
    -   **Scenariusz/przykład dla sprzedawcy:** Możesz zmienić dostawców, jeśli jeden oferuje lepszą dokładność dla Twoich regionów docelowych lub jeśli napotkasz problemy z domyślnym.
-   **Ustawienia buforowania (hipotetycznie):**

    -   **Co robi to ustawienie:** Kontroluje, jak długo dane geolokalizacyjne są buforowane dla odwiedzających w celu poprawy wydajności.
    -   **Efekt zmiany tego ustawienia:**
        -   *Dłuższy czas buforowania:* Szybsze ładowanie stron dla powracających odwiedzających, ale potencjalnie wolniejsze aktualizacje, jeśli adres IP odwiedzającego się zmieni.
        -   *Krótszy czas buforowania:* Więcej geolokalizacji w czasie rzeczywistym, ale nieco większe obciążenie serwera.
    -   **Zalecana wartość:** Domyślna (zazwyczaj zoptymalizowana pod kątem równowagi).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoja witryna ma bardzo duży ruch i priorytetowo traktujesz szybkość, możesz zwiększyć czas buforowania. Jeśli Twoja baza klientów jest bardzo mobilna i często zmienia adresy IP, preferowany może być krótszy czas.

**Ważna uwaga dla sprzedawców:**
Ten moduł działa poprzez nadpisywanie podstawowych klas PrestaShop (`Product.php`, `Tax.php`, `TaxCalculator.php`). Jest to potężna technika, która bezpośrednio modyfikuje sposób, w jaki PrestaShop oblicza i wyświetla ceny. Z tego powodu zazwyczaj jest bardzo mało, jeśli w ogóle, konfigurowalnych opcji na dedykowanym ekranie. Siła modułu tkwi w jego automatycznych, działających w tle dostosowaniach.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Włącz/Wyłącz moduł | Włączony | Włącza lub wyłącza funkcjonalność modułu do dostosowywania cen w oparciu o geolokalizację. |
| Strona konfiguracji modułu | *[Inne ustawienia, jeśli są obecne]* | *[Wartość domyślna]* | *[Cel i wpływ]* |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Ceny nie zmieniają się dla niezalogowanych użytkowników, nawet po zainstalowaniu modułu.**
O1:

-   **Sprawdź status modułu:** Upewnij się, że moduł jest zainstalowany i włączony w Panelu administracyjnym PrestaShop w sekcji Moduły > Menedżer modułów.
-   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i wyczyść wszystkie pamięci podręczne (pamięć podręczna Smarty, pamięć podręczna systemu plików itp.). Może być również konieczne wyczyszczenie pamięci podręcznej przeglądarki.
-   **Dokładność geolokalizacji:** Moduł opiera się na geolokalizacji IP. Chociaż jest ogólnie dokładna, nie jest w 100% doskonała. Przetestuj z różnymi adresami IP (np. używając VPN), aby potwierdzić.
-   **Reguły podatkowe PrestaShop:** Zweryfikuj, czy Twoje reguły podatkowe i grupy podatkowe PrestaShop są poprawnie skonfigurowane dla różnych krajów. Moduł używa tych istniejących reguł do określenia, *jaką* cenę wyświetlić (z podatkiem lub bez), gdy zna kraj.
-   **Konflikty nadpisywania:** Jeśli masz inne moduły, które również nadpisują `Product.php`, `Tax.php` lub `TaxCalculator.php`, może wystąpić konflikt. Sprawdź folder `override/` pod kątem innych modułów modyfikujących te pliki. Skontaktuj się z pomocą techniczną MyPresta.eu, jeśli podejrzewasz konflikt.

**P2: Mój niestandardowy motyw nie wyświetla poprawnie cen po instalacji.**
O2: Ten moduł wpływa przede wszystkim na *wartość* wyświetlanej ceny, a nie na jej styl wizualny. Jeśli ceny wyglądają na źle wyrównane lub nieprawidłowo ostylowane, prawdopodobnie jest to problem CSS z Twoim motywem.

-   **Kompatybilność motywu:** Upewnij się, że Twój motyw jest w pełni kompatybilny z Twoją wersją PrestaShop.
-   **Inspekcja elementu:** Użyj narzędzi deweloperskich przeglądarki (F12), aby zbadać elementy cenowe i sprawdzić, czy jakiś niestandardowy CSS z Twojego motywu nie powoduje konfliktu.
-   **Skontaktuj się z deweloperem motywu:** Jeśli używasz niestandardowego motywu, skontaktuj się z jego deweloperem w celu uzyskania pomocy w stylizacji. Sam moduł nie wprowadza nowego CSS.

**P3: Czy ten moduł wpływa na zalogowanych użytkowników lub użytkowników, którzy wprowadzili swój adres?**
O3: Nie, ten moduł jest skierowany konkretnie do *niezalogowanych użytkowników*, którzy nie podali jeszcze swoich danych adresowych. Gdy użytkownik zaloguje się lub wprowadzi swój adres wysyłki podczas realizacji zamówienia, pierwszeństwo będzie miała natywna logika obliczania i wyświetlania podatków PrestaShop (która już zna kraj klienta). Ten moduł wypełnia lukę w początkowym doświadczeniu przeglądania.

**P4: Skąd moduł wie, jaki jest kraj klienta?**
O4: Moduł używa adresu IP odwiedzającego do określenia jego położenia geograficznego. Jest to standardowa metoda geolokalizacji w aplikacjach internetowych. Następnie używa tego wykrytego kraju do zastosowania odpowiednich reguł podatkowych PrestaShop do wyświetlania cen.

**P5: Czy ten moduł spowolni mój sklep?**
O5: Moduł został zaprojektowany tak, aby był wydajny. Wyszukiwania geolokalizacyjne są zazwyczaj szybkie, a moduł często buforuje wyniki, aby zminimalizować powtarzające się wyszukiwania dla tego samego odwiedzającego. Wpływ na wydajność powinien być znikomy. Jeśli zauważysz jakiekolwiek spowolnienie, upewnij się, że Twój serwer spełnia minimalne wymagania PrestaShop i że Twoje mechanizmy buforowania są poprawnie skonfigurowane.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Ceny bez podatku dla niezalogowanych użytkowników według geolokalizacji” osiąga swoją funkcjonalność głównie poprzez system nadpisywania PrestaShop. Zamiast polegać na tradycyjnych hookach lub niestandardowych kontrolerach, bezpośrednio modyfikuje zachowanie podstawowych klas PrestaShop odpowiedzialnych za ceny produktów i obliczanie podatków. Pozwala to na wstrzyknięcie logiki opartej na geolokalizacji do fundamentalnego procesu ustalania cen, zapewniając, że ceny są dostosowywane, zanim zostaną nawet wyrenderowane. Moduł wykorzystuje hook `displayHeader` do potencjalnego włączenia niezbędnego JavaScriptu lub stylizacji, chociaż jego podstawowa logika jest oparta na PHP.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Jego logika jest osadzona bezpośrednio w nadpisaniach podstawowych klas.

### 4.3 Klasy podstawowe i modele (`classes/`)

Podstawowa funkcjonalność modułu znajduje się w jego nadpisaniach fundamentalnych klas cenowych i produktowych PrestaShop.

-   **`taxprice/override/classes/Product.php`**

    -   **Oryginalna klasa:** `Product`
    -   **Odpowiedzialność:** To nadpisanie jest kluczowe. Klasa `Product` jest odpowiedzialna za pobieranie i formatowanie informacji o produkcie, w tym cen. To nadpisanie prawdopodobnie przechwytuje metody takie jak `getPrice()` lub powiązane metody obliczania cen, aby wstrzyknąć logikę geolokalizacji *przed* zwróceniem ceny do wyświetlenia. Określa, czy wyświetlać ceny z podatkiem czy bez, w oparciu o wykryty kraj dla niezalogowanych użytkowników.
    -   **Kluczowa logika:**
        -   Wykrywa, czy bieżący użytkownik jest gościem (niezalogowanym).
        -   Uzyskuje kraj odwiedzającego na podstawie adresu IP (potencjalnie za pomocą funkcji pomocniczej lub integracji z usługą zewnętrzną).
        -   Modyfikuje kontekst `TaxManagerFactory` lub bezpośrednio manipuluje `price_display_method` w oparciu o reguły podatkowe wykrytego kraju i konfigurację PrestaShop dla tego kraju.
-   **`taxprice/override/classes/tax/Tax.php`**

    -   **Oryginalna klasa:** `Tax`
    -   **Odpowiedzialność:** Klasa `Tax` obsługuje pobieranie i stosowanie stawek podatkowych. To nadpisanie może być używane do zapewnienia, że prawidłowe stawki podatkowe są stosowane *po* tym, jak geolokalizacja określiła, czy ceny powinny być z podatkiem czy bez. Może modyfikować sposób pobierania stawek podatkowych lub sposób inicjalizacji `TaxCalculator` w oparciu o kraj gościa.
-   **`taxprice/override/classes/tax/TaxCalculator.php`**

    -   **Oryginalna klasa:** `TaxCalculator`
    -   **Odpowiedzialność:** Ta klasa jest kluczowa dla obliczania cen z podatkami i bez. Nadpisanie tutaj bezpośrednio wpłynęłoby na ostateczne obliczenie ceny. Prawdopodobnie zapewnia, że gdy kraj gościa jest znany, `TaxCalculator` używa prawidłowej `price_display_method` (np. `PS_TAX_EXC` lub `PS_TAX_INC`), która odpowiada regułom podatkowym wykrytego kraju, a nie domyślnym ustawieniom sklepu.
-   **`taxprice/override/classes/index.php`**

    -   **Cel:** Jest to standardowy pusty plik `index.php`, zazwyczaj umieszczany w katalogach w celu zapobiegania listowaniu katalogów ze względów bezpieczeństwa. Nie ma wpływu funkcjonalnego na logikę modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript. Jego podstawowa funkcjonalność jest obsługiwana po stronie serwera za pomocą nadpisywania PHP.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików CSS. Nie wprowadza nowych elementów wizualnych, jedynie modyfikuje istniejące wartości cen.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`taxprice/views/displayHeader.tpl`**

    -   **Hook:** `displayHeader`
    -   **Cel:** Ten szablon jest renderowany w sekcji `<head>` każdej strony front-office. Zazwyczaj jest używany do dołączania JavaScriptu, CSS lub meta tagów. Chociaż podstawowa logika modułu jest oparta na PHP, ten szablon może być używany do:
        -   Inicjalizacji wszelkich zmiennych po stronie klienta, jeśli to konieczne (choć mało prawdopodobne, biorąc pod uwagę charakter po stronie serwera).
        -   Potencjalnego włączenia małego skryptu inline do debugowania lub bardzo specyficznych dostosowań po stronie klienta (np. ustawienia pliku cookie z wykrytym krajem, choć rzadziej dla tego typu modułu).
        -   W przypadku braku dedykowanych plików JS, może zawierać minimalny inline JS.
-   **`taxprice/views/script.tpl`**

    -   **Cel:** Nazwa tego szablonu sugeruje, że może zawierać kod JavaScript. Jeśli jest obecny, prawdopodobnie zostałby dołączony za pośrednictwem `displayHeader.tpl` lub innego hooka.
    -   **Potencjalna zawartość:**
        -   Wszelka logika po stronie klienta związana z geolokalizacją (np. użycie API do wyszukiwania IP po stronie klienta, choć mniej niezawodne niż po stronie serwera).
        -   Skrypty do obsługi dynamicznych aktualizacji cen, jeśli moduł obsługuje również przełączanie po stronie klienta lub dostosowania w czasie rzeczywistym (mało prawdopodobne, biorąc pod uwagę opis).
        -   Skrypty debugowania lub proste wyjście danych dla programistów.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Ten moduł **nie** tworzy żadnych niestandardowych tabel bazy danych.
    -   Opiera się na istniejących tabelach PrestaShop dla produktów (`ps_product`, `ps_product_shop`), podatków (`ps_tax`, `ps_tax_rule`, `ps_tax_rule_group`) i konfiguracji (`ps_configuration`).
    -   Wartości konfiguracyjne są przechowywane w `ps_configuration` przy użyciu standardowych metod `Configuration::get()` i `Configuration::updateValue()`, zazwyczaj z prefiksem `TAXPRICE_`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Używany do dołączania `displayHeader.tpl` i potencjalnie `script.tpl` dla wszelkich niezbędnych skryptów po stronie klienta lub meta-informacji. |
| `actionProductUpdate` | Po zaktualizowaniu produktu. | (Implicit, nie wymieniony jawnie, ale powszechny dla modułów związanych z cenami) Może czyścić pamięć podręczną związaną z cenami produktów, aby zapewnić ponowne zastosowanie nadpisań. |
| `actionProductAdd` | Po dodaniu produktu. | (Implicit) Podobnie jak `actionProductUpdate`. |
| `actionTaxManagerFactory` | Gdy `TaxManagerFactory` jest inicjalizowany. | (Implicit, kluczowy dla tego modułu) Nadpisania w `Tax.php` i `TaxCalculator.php` skutecznie „zahaczałyby” lub modyfikowałyby zachowanie obliczania podatków na tym etapie, nawet jeśli nie jest to formalna rejestracja `hook`. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dalszej pomocy z modułem „Ceny bez podatku dla niezalogowanych użytkowników według geolokalizacji”, prosimy odnieść się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie kompleksowego wsparcia i sprawne działanie Twojego modułu.
