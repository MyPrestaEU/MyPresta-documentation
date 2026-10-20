---
title: "Darmowe hreflang i kanoniczne adresy URL - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Darmowe hreflang i kanoniczne adresy URL” od MyPresta.eu."
sidebar:
  label: "Darmowe hreflang i kanoniczne adresy URL - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Free hreflang & canonical urls na MyPresta.eu](https://mypresta.eu/modules/seo/free-hreflang-canonical-urls.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/seo/free-hreflang-canonical-urls/)
>
> ---


# Darmowe hreflang i kanoniczne adresy URL

## 1. Wymagania i kompatybilność

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 7.1 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i zazwyczaj preinstalowane w większości środowisk hostingowych. Nie są wymagane żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po zainstalowaniu modułu przejdź do **Moduły > Menedżer modułów**, wyszukaj „Darmowe hreflang i kanoniczne adresy URL” i kliknij „Konfiguruj”. Zostanie wyświetlony główny ekran konfiguracji modułu.

#### **Opcje konfiguracji:**

-   **Włącz tagi hreflang:**

    -   **Co robi to ustawienie:** Ten główny przełącznik kontroluje, czy moduł będzie generował i dodawał tagi `hreflang` do nagłówka HTML Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Moduł będzie aktywnie generował i wstawiał tagi `hreflang` dla wszystkich dostępnych wersji językowych Twoich stron (strony produktów, strony kategorii, strony CMS itp.). Jest to kluczowe dla międzynarodowego SEO.
        -   *Gdy wyłączone (NIE):* Ten moduł nie doda żadnych tagów `hreflang`. Jeśli masz sklep wielojęzyczny, wyszukiwarki mogą traktować Twoje różne wersje językowe jako zduplikowaną treść, potencjalnie szkodząc Twoim międzynarodowym rankingom.
    -   **Zalecana wartość:** **TAK**. Zawsze włączaj tę opcję, jeśli Twój sklep obsługuje wiele języków lub celuje w różne regiony.
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz produkty zarówno w języku angielskim, jak i hiszpańskim, włączenie tej opcji zapewnia, że hiszpańskojęzyczny klient wyszukujący w Google zobaczy hiszpańską wersję strony produktu, a anglojęzyczny klient zobaczy angielską wersję.
-   **Włącz kanoniczne adresy URL:**

    -   **Co robi to ustawienie:** Ten główny przełącznik kontroluje, czy moduł będzie generował i dodawał tagi `canonical` URL do nagłówka HTML Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Moduł będzie aktywnie generował i wstawiał tagi `canonical` dla wszystkich stron, wskazując preferowaną wersję każdej strony. Pomaga to konsolidować sygnały SEO i zapobiega problemom z duplikowaniem treści.
        -   *Gdy wyłączone (NIE):* Ten moduł nie doda żadnych tagów `canonical`. Twój sklep może cierpieć z powodu problemów z duplikowaniem treści, jeśli ta sama treść jest dostępna za pośrednictwem wielu adresów URL (np. z lub bez ukośników na końcu, z różnymi parametrami lub poprzez różne ścieżki kategorii).
    -   **Zalecana wartość:** **TAK**. Tagi kanoniczne są fundamentalne dla dobrego SEO na prawie każdej stronie internetowej.
    -   **Scenariusz/przykład dla sprzedawcy:** Strona produktu może być dostępna pod adresem `twojsklep.com/nazwa-produktu`, a także `twojsklep.com/kategoria/nazwa-produktu`. Włączenie kanonicznych adresów URL informuje Google, że `twojsklep.com/nazwa-produktu` jest główną wersją, zapewniając, że cały kredyt SEO trafia do tego jednego adresu URL.
-   **Użyj x-default hreflang:**

    -   **Co robi to ustawienie:** Atrybut `x-default` hreflang określa domyślną stronę, która powinna być wyświetlana użytkownikom, gdy żaden inny język/region nie pasuje do ich ustawień przeglądarki lub lokalizacji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Moduł doda tag `x-default` hreflang, zazwyczaj wskazujący na domyślny język Twojego sklepu lub ogólną wersję międzynarodową. Jest to przydatne dla użytkowników, których język lub region nie jest wyraźnie docelowy przez Twoje inne tagi hreflang.
        -   *Gdy wyłączone (NIE):* Nie zostanie dodany żaden tag `x-default` hreflang. Użytkownikom, których język/region nie pasuje do żadnego konkretnego hreflang, może zostać wyświetlona mniej trafna strona, lub wyszukiwarki mogą musieć zgadywać, którą stronę wyświetlić.
    -   **Zalecana wartość:** **TAK**. Ogólnie dobrą praktyką jest włączenie `x-default` dla kompleksowego międzynarodowego SEO, zwłaszcza jeśli masz globalną publiczność.
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli masz wersje angielską (USA), angielską (UK) i francuską, ale użytkownik z Niemiec szuka w języku angielskim, `x-default` może skierować go na Twoją ogólną stronę angielską (USA), zapewniając, że nadal otrzyma odpowiednią treść.
-   **Użyj tylko kodu języka (np. „en” zamiast „en-us”):**

    -   **Co robi to ustawienie:** Kontroluje format kodów językowych używanych w tagach `hreflang`.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Moduł będzie używał tylko dwuliterowego kodu języka ISO (np. `en`, `fr`, `de`). Jest to prostsze i odpowiednie, jeśli celujesz w język globalnie, a nie w konkretne regiony.
        -   *Gdy wyłączone (NIE):* Moduł będzie używał zarówno kodu języka, jak i regionu (np. `en-US`, `en-GB`, `fr-CA`). Jest to bardziej precyzyjne i zalecane, jeśli masz różne treści lub ceny dla konkretnych krajów w ramach tego samego języka.
    -   **Zalecana wartość:**
        -   **NIE**, jeśli masz specyficzne targetowanie regionalne (np. różne treści angielskie dla USA vs. UK).
        -   **TAK**, jeśli Twoje różne wersje językowe są ogólne i nie są specyficzne dla kraju (np. jedna wersja „angielska” dla wszystkich anglojęzycznych użytkowników).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz w języku angielskim i masz jedną angielską wersję dla wszystkich krajów, wybierz TAK. Jeśli masz oddzielne treści/ceny angielskie dla USA i Wielkiej Brytanii, wybierz NIE, aby używać `en-US` i `en-GB`.

#### **Zapisywanie ustawień:**

Po dokonaniu wyboru kliknij przycisk **„Zapisz”** na dole strony konfiguracji, aby zastosować zmiany.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz tagi hreflang | TAK | Aktywuje tagi hreflang dla międzynarodowego SEO. |
| Konfiguracja modułu | Włącz kanoniczne adresy URL | TAK | Aktywuje tagi kanoniczne, aby zapobiec duplikowaniu treści. |
| Konfiguracja modułu | Użyj x-default hreflang | TAK | Zapewnia stronę awaryjną dla użytkowników o niedopasowanym języku/regionie. |
| Konfiguracja modułu | Użyj tylko kodu języka (np. „en” zamiast „en-us”) | NIE (zależy od strategii) | Określa, czy hreflang używa tylko języka (`en`) czy języka-regionu (`en-US`). |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Włączyłem moduł, ale nie widzę żadnych wizualnych zmian na mojej stronie. Czy działa?**
O1: Tak, działa zgodnie z przeznaczeniem! Ten moduł działa całkowicie w tle. Dodaje specjalny kod (tagi hreflang i kanoniczne) do sekcji `<head>` kodu HTML Twojej witryny, który jest widoczny dla wyszukiwarek, ale nie dla Twoich klientów. Aby sprawdzić, czy działa, możesz kliknąć prawym przyciskiem myszy na dowolnej stronie swojego sklepu, wybrać „Wyświetl źródło strony” (lub podobne) i wyszukać „hreflang” lub „canonical”. Powinieneś zobaczyć tam te tagi.

**P2: Po włączeniu modułu moje rankingi w wyszukiwarkach nie poprawiły się natychmiast. Czego powinienem się spodziewać?**
O2: Zmiany w SEO, zwłaszcza te związane z indeksowaniem, potrzebują czasu, aby odzwierciedlić się w wynikach wyszukiwania. Google i inne wyszukiwarki muszą ponownie zaindeksować Twoją witrynę, przetworzyć nowe tagi i zaktualizować swój indeks. Ten proces może trwać od kilku dni do kilku tygodni, a nawet miesięcy. Kontynuuj monitorowanie Google Search Console pod kątem wszelkich zmian w indeksowaniu lub raportach dotyczących targetowania międzynarodowego.

**P3: Mój niestandardowy motyw ma unikalne struktury adresów URL. Czy ten moduł nadal będzie działał poprawnie?**
O3: Moduł jest zaprojektowany do integracji z podstawowymi mechanizmami generowania adresów URL PrestaShop. W większości przypadków powinien działać bezproblemowo z niestandardowymi motywami. Jednak jeśli Twój motyw znacznie modyfikuje standardowe routowanie adresów URL PrestaShop lub renderowanie stron, istnieje niewielka szansa na konflikt. Jeśli podejrzewasz problem, najpierw wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**). Jeśli problemy nadal występują, skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły dotyczące Twojego motywu i wszelkich konkretnych stron, na których występują problemy.

**P4: Mam sklep wielojęzyczny, ale niektóre strony nie mają tłumaczeń na wszystkie języki. Jak moduł sobie z tym radzi?**
O4: Moduł zazwyczaj generuje tagi `hreflang` tylko dla języków, które faktycznie mają dostępną treść dla danej strony. Jeśli produkt lub kategoria nie jest przetłumaczona na określony język, moduł nie powinien generować tagu `hreflang` dla tego nieistniejącego tłumaczenia. Upewnij się, że Twoje tłumaczenia PrestaShop są poprawnie zarządzane w Panelu administracyjnym.

**P5: Widzę wiele tagów kanonicznych lub niepoprawne tagi hreflang. Co może być nie tak?**
O5: Zazwyczaj wskazuje to na konflikt z innym modułem SEO lub Twoim motywem, który również może próbować dodawać tagi kanoniczne lub hreflang.
1.  **Sprawdź inne moduły SEO:** Wyłączaj inne moduły SEO jeden po drugim, aby zidentyfikować ten, który powoduje konflikt.
2.  **Sprawdź swój motyw:** Niektóre motywy mogą mieć na stałe zakodowane tagi kanoniczne.
3.  **Wyczyść pamięć podręczną:** Zawsze wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**) po wprowadzeniu jakichkolwiek zmian w module.
Jeśli problem nadal występuje, skontaktuj się z pomocą techniczną MyPresta.eu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Darmowe hreflang i kanoniczne adresy URL” (`myhreflang`) to lekki moduł PrestaShop zaprojektowany głównie do wstrzykiwania meta tagów `hreflang` i `canonical` do sekcji `<head>` stron front-office. Przestrzega standardowej architektury modułów PrestaShop, wykorzystując hooki do integracji swojej funkcjonalności bez modyfikowania plików rdzenia. Logika modułu znajduje się głównie w jego głównym pliku PHP, `index.php`, który obsługuje konfigurację, instalację, deinstalację i podstawową logikę generowania tagów. Wykorzystuje klasy `Context` i `Link` PrestaShop do określania bieżącej strony, dostępnych języków i generowania poprawnych adresów URL.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała logika jest obsługiwana w głównym pliku modułu i jego metodach podłączonych do hooków.

### 4.3 Klasy rdzenia i modele (`classes/`)

Ten moduł **nie** definiuje żadnych niestandardowych klas ani `ObjectModel` w katalogu `classes/`. Cała podstawowa logika jest zawarta w klasie `myhreflang` w `index.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript. Jego funkcjonalność to wyłącznie generowanie tagów HTML po stronie serwera.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików CSS. Jego funkcjonalność to wyłącznie generowanie tagów HTML po stronie serwera i nie ma wpływu wizualnego.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa pojedynczego szablonu Smarty do renderowania tagów `hreflang` i `canonical`.

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `myhreflang/views/templates/hook/hreflang.tpl`: Ten szablon jest odpowiedzialny za wyprowadzanie rzeczywistych tagów `<link rel="alternate" hreflang="..." href="..." />` i `<link rel="canonical" href="..." />`.
        -   **Renderowany w hooku**: `displayHeader`
        -   **Cel**: Otrzymuje tablicę `hreflang_links` i `canonical_link` z metody `hookDisplayHeader` modułu. Następnie iteruje przez nie, aby wygenerować niezbędne tagi HTML `<link>`.
        -   **Dostępne zmienne**:
            -   `$hreflang_links`: Tablica tablic asocjacyjnych, z których każda zawiera `lang_code` (np. „en”, „en-US”, „x-default”) i `url`.
            -   `$canonical_link`: Ciąg znaków zawierający kanoniczny adres URL dla bieżącej strony.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Ten moduł **nie** tworzy żadnych niestandardowych tabel SQL. Przechowuje swoje ustawienia konfiguracyjne bezpośrednio w tabeli `ps_configuration` za pomocą standardowych metod PrestaShop `Configuration::get()` i `Configuration::updateValue()`.

    -   Klucze konfiguracyjne przechowywane w `ps_configuration`:
        -   `MYHREFLANG_HREFLANG_ENABLED` (boolean)
        -   `MYHREFLANG_CANONICAL_ENABLED` (boolean)
        -   `MYHREFLANG_XDEFAULT_ENABLED` (boolean)
        -   `MYHREFLANG_LANG_CODE_ONLY` (boolean)
-   **Tabela zarejestrowanych hooków**:

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `displayHeader` | Wykonywany w sekcji `<head>` każdej strony front-office. | Jest to główny hook używany przez moduł. Wywołuje metodę `hookDisplayHeader()`, aby wygenerować i wstrzyknąć tagi `<link>` `hreflang` i `canonical` do sekcji `<head>` HTML strony. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnego wsparcia, aktualizacji modułu i wszelkiej dalszej pomocy z modułem „Darmowe hreflang i kanoniczne adresy URL” prosimy odwiedzić swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich pytań lub problemów technicznych, które mogą się pojawić.
