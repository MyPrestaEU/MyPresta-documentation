---
title: "Usuń kod ISO języka z adresów URL - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów dla modułu PrestaShop „Usuń kod ISO języka z adresów URL” od MyPresta.eu."
sidebar:
  label: "Usuń kod ISO języka z adresów URL - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Remove language ISO code from urls na MyPresta.eu](https://mypresta.eu/modules/seo/remove-language-iso-code-from-urls.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/seo/remove-language-iso-code-from-urls/)
>
> ---


# Usuń kod ISO języka z adresów URL

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera poza tymi, których wymaga sam PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu „Usuń kod ISO języka z adresów URL”, aby uzyskać dostęp do jego ustawień.

Strona konfiguracji tego modułu jest celowo prosta, ponieważ jego podstawowa funkcja jest nieskomplikowana.

**Nazwa ekranu:** Konfiguracja modułu „Usuń kod ISO języka z adresów URL”
**Lokalizacja w menu:** Panel administracyjny > Moduły > Menedżer modułów > Usuń kod ISO języka z adresów URL > Konfiguruj

Na tym ekranie zazwyczaj znajdziesz jedno, kluczowe ustawienie:

- **Nazwa ustawienia:** Włącz / Wyłącz moduł
  - **Co robi to ustawienie:** Jest to główny przełącznik funkcjonalności modułu. Kontroluje, czy moduł aktywnie usuwa kod ISO języka z adresów URL Twojego domyślnego języka, czy nie.
  - **Efekt zmiany tego ustawienia:**
    - **Gdy włączony (TAK):** Moduł stanie się aktywny. Dla domyślnego języka Twojego sklepu, kod ISO języka (np. `/en/`, jeśli angielski jest domyślny) zostanie usunięty ze wszystkich generowanych adresów URL. Adresy URL dla innych języków pozostaną bez zmian.
    - **Gdy wyłączony (NIE):** Moduł będzie nieaktywny. Wszystkie adresy URL, w tym te dla Twojego domyślnego języka, będą nadal wyświetlać kod ISO języka (np. `/en/`, `/fr/`).
  - **Zalecana wartość:** **TAK**. Głównym celem instalacji tego modułu jest wykorzystanie jego funkcjonalności, dlatego włączenie go jest standardową rekomendacją.
  - **Scenariusz / przykład dla sprzedawcy:**
    - Właśnie zainstalowałeś moduł i chcesz, aby Twoje angielskie (domyślne) adresy URL wyglądały jak `www.twojskep.com/moj-produkt`. Ustawisz to na **TAK**.
    - Jeśli później zdecydujesz, że wolisz, aby kod ISO języka był obecny we wszystkich adresach URL z jakiegoś powodu (np. zmiana konkretnej strategii SEO), możesz ustawić to na **NIE**, aby przywrócić zachowanie bez odinstalowywania modułu.

**Ważna uwaga po konfiguracji:**
Po włączeniu lub wyłączeniu modułu, zdecydowanie zaleca się:

1. **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
2. **Wygeneruj ponownie plik `.htaccess`:** Przejdź do **Parametry sklepu > Ruch i SEO**, przewiń do sekcji „Ustawienia adresów URL” i kliknij „Zapisz” (nawet jeśli nic nie zmieniasz). Zapewnia to prawidłową aktualizację reguł przepisywania adresów URL.
3. **Przetestuj swoje adresy URL:** Przeglądaj swój sklep w domyślnym języku i sprawdź, czy kod ISO języka został faktycznie usunięty z adresów URL. Przetestuj również inne języki, aby upewnić się, że ich adresy URL nadal zawierają kod ISO.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz / Wyłącz moduł | TAK | Kontroluje, czy moduł usuwa kod ISO języka z adresów URL domyślnego języka. **TAK** dla czystszych adresów URL, **NIE** aby zachować kody ISO dla wszystkich języków. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Włączyłem moduł, ale kod ISO języka nadal wyświetla się w adresach URL mojego domyślnego języka. Co powinienem zrobić?**
O: Zazwyczaj jest to problem z pamięcią podręczną lub nieprawidłowym ponownym wygenerowaniem pliku `.htaccess`.
1. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.
2. Przejdź do **Parametry sklepu > Ruch i SEO**, przewiń do „Ustawienia adresów URL” i kliknij „Zapisz”.
3. Sprawdź również pamięć podręczną przeglądarki lub spróbuj przeglądać w oknie incognito/prywatnym.

**P: Czy ten moduł wpłynie na adresy URL moich języków innych niż domyślny?**
O: Nie, moduł jest specjalnie zaprojektowany, aby usuwać kod ISO języka tylko dla Twojego *domyślnego* języka. Wszystkie inne wersje językowe będą nadal wyświetlać swoje odpowiednie kody ISO (np. `/fr/`, `/de/`).

**P: Czy ten moduł zepsuje moje istniejące SEO lub spowoduje błędy 404 dla starych adresów URL?**
O: Moduł działa poprzez nadpisywanie podstawowego generowania i wysyłania adresów URL PrestaShop. Powinien obsługiwać przekierowania wewnętrznie. Jednak dla maksymalnego bezpieczeństwa, zwłaszcza w przypadku istniejących sklepów, zawsze warto:
1. **Wykonaj kopię zapasową bazy danych i plików** przed instalacją.
2. **Dokładnie przetestuj** najpierw w środowisku testowym.
3. Po włączeniu monitoruj logi dostępu do serwera i Google Search Console pod kątem błędów 404. Jeśli znajdziesz jakieś, może być konieczne ręczne dodanie przekierowań 301 dla konkretnych starych adresów URL do ich nowych, czystszych wersji w pliku `.htaccess`, chociaż rzadko jest to potrzebne w przypadku tego modułu.

**P: Mój niestandardowy motyw ma pewne problemy po zainstalowaniu modułu. Co może być nie tak?**
O: Ten moduł wpływa głównie na generowanie i routing adresów URL, a nie na wyświetlanie wizualne. Jest mało prawdopodobne, aby bezpośrednio powodował problemy z motywem. Jednakże, jeśli Twój motyw ma bardzo specyficzne, zakodowane na stałe struktury URL lub opiera się na JavaScript, który analizuje adresy URL w nietypowy sposób, istnieje bardzo mała szansa na konflikt.
\* Najpierw wyczyść pamięć podręczną Smarty (**Zaawansowane > Wydajność**).
\* Jeśli problem nadal występuje, tymczasowo wyłącz moduł, aby sprawdzić, czy problem zniknie. Jeśli tak, skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły problemu.

**P: Czy ten moduł obsługuje wszystkie języki zainstalowane w PrestaShop?**
O: Tak, obsługuje wszystkie języki. Identyfikuje Twój *domyślny* język i usuwa jego kod ISO, pozostawiając kody ISO dla wszystkich innych zainstalowanych języków bez zmian.

## 4. Przewodnik dla deweloperów i webmasterów (architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis technicznej implementacji modułu „Usuń kod ISO języka z adresów URL”, przeznaczony dla deweloperów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł „Usuń kod ISO języka z adresów URL” osiąga swoją funkcjonalność poprzez nadpisywanie podstawowych klas PrestaShop odpowiedzialnych za generowanie adresów URL (`Link`) i wysyłanie adresów URL (`Dispatcher`). Pozwala to na przechwytywanie i modyfikowanie sposobu, w jaki adresy URL są konstruowane i interpretowane przez PrestaShop, w szczególności ukierunkowane na usunięcie kodu ISO języka dla języka domyślnego. Wykorzystuje system nadpisywania PrestaShop do wstrzykiwania niestandardowej logiki bez bezpośredniej modyfikacji plików rdzenia.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Jego logika jest głównie implementowana poprzez nadpisywanie klas.

### 4.3 Klasy rdzenia i modele (`classes/`)

Podstawowa funkcjonalność modułu znajduje się w jego nadpisaniach klas. Pliki te są umieszczane w `removeiso/override/classes/`, aby system nadpisywania PrestaShop je wykrył.

- **`removeiso/override/classes/Dispatcher.php`**
  - **Nazwa klasy:** `Dispatcher` (nadpisuje podstawową klasę `Dispatcher` PrestaShop)
  - **Klasa nadrzędna:** `DispatcherCore`
  - **Odpowiedzialność:** To nadpisanie jest kluczowe dla sposobu, w jaki PrestaShop *interpretuje* przychodzące adresy URL. Modyfikuje metodę `dispatch()` (lub powiązaną metodę) w celu prawidłowego routingu żądań, które nie zawierają już domyślnego kodu ISO języka. Gdy przychodzi adres URL taki jak `www.twojskep.com/moj-produkt`, ten nadpisany `Dispatcher` zapewnia, że PrestaShop rozumie, że należy on do języka domyślnego, nawet bez segmentu `/en/`. Prawdopodobnie obsługuje również logikę, aby upewnić się, że jeśli domyślny kod ISO języka *jest* obecny (np. `www.twojskep.com/en/moj-produkt`), jest on przekierowywany do czystszego adresu URL.
- **`removeiso/override/classes/Link.php`**
  - **Nazwa klasy:** `Link` (nadpisuje podstawową klasę `Link` PrestaShop)
  - **Klasa nadrzędna:** `LinkCore`
  - **Odpowiedzialność:** To nadpisanie jest odpowiedzialne za sposób, w jaki PrestaShop *generuje* wychodzące adresy URL. Modyfikuje metody takie jak `getLanguageLink()`, `getProductLink()`, `getCategoryLink()` itp., aby zapobiec włączaniu kodu ISO języka, gdy język docelowy jest domyślnym językiem sklepu. Zapewnia to, że wszystkie linki generowane przez PrestaShop (np. w szablonach, modułach) dla języka domyślnego są czyste.
- **`removeiso/override/classes/Tools.php`**
  - **Nazwa klasy:** `Tools` (nadpisuje podstawową klasę `Tools` PrestaShop)
  - **Klasa nadrzędna:** `ToolsCore`
  - **Odpowiedzialność:** Klasa `Tools` zawiera wiele funkcji narzędziowych. To nadpisanie może być użyte do modyfikacji sposobu obsługi niektórych globalnych parametrów lub ciągów związanych z adresami URL, prawdopodobnie w połączeniu z nadpisaniami `Dispatcher` i `Link`, aby zapewnić spójność w różnych zadaniach manipulacji adresami URL. Może na przykład wpływać na sposób interpretacji `$_SERVER['REQUEST_URI']` lub na zachowanie `Tools::redirect()` w określonych scenariuszach związanych z kodami języków.
- **`removeiso/override/classes/index.php`**
  - **Nazwa klasy:** N/A (pusty plik)
  - **Klasa nadrzędna:** N/A
  - **Odpowiedzialność:** Jest to standardowa praktyka bezpieczeństwa w modułach PrestaShop, aby zapobiec listowaniu katalogów, jeśli plik `index.php` jest dostępny bezpośrednio. Nie zawiera kodu wykonywalnego.

### 4.4 Zasoby JavaScript (`views/js/`)

- **`removeiso/views/js/removeiso.js`**
  - **Zakres:** Panel administracyjny (prawdopodobnie ładowany na stronie konfiguracji modułu).
  - **Odpowiedzialność:** Biorąc pod uwagę funkcję modułu, ten plik JS jest prawdopodobnie minimalny. Może zawierać:
    - Proste słuchacze zdarzeń dla formularza konfiguracji (np. kliknięcie przycisku „Zapisz”).
    - Wywołania AJAX do zapisywania ustawień konfiguracji, jeśli formularz używa asynchronicznego przesyłania.
    - Podstawowe ulepszenia interfejsu użytkownika lub walidację dla pojedynczego przełącznika „Włącz/Wyłącz”.
    - Nie wydaje się mieć żadnych obowiązków front-office ani złożonej logiki po stronie klienta związanej z manipulacją adresami URL, ponieważ jest to obsługiwane po stronie serwera przez nadpisania PHP.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie zawiera żadnych niestandardowych plików CSS. Wskazuje to, że jego interfejs konfiguracyjny opiera się na domyślnej stylizacji Panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **`removeiso/views/templates/admin/removeiso.tpl`**
  - **Zakres:** Szablon administracyjny dla strony konfiguracji modułu.
  - **Odpowiedzialność:** Ten szablon renderuje formularz konfiguracji modułu w Panelu administracyjnym PrestaShop. Będzie zawierał strukturę HTML dla przełącznika „Włącz / Wyłącz moduł” i standardowe elementy formularza PrestaShop (np. przycisk `submit`, komunikaty `alert`). Jest zazwyczaj renderowany przez metodę `getContent()` głównej klasy modułu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  - Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych.
  - Jego ustawienia konfiguracyjne (np. status „Włącz/Wyłącz”) są przechowywane w tabeli `ps_configuration`, używając kluczy zazwyczaj poprzedzonych prefiksem `REMOVEISO_` lub podobnym (np. `PS_REMOVEISO_ENABLED`).
- **Tabela zarejestrowanych hooków**:
  Ten moduł nie rejestruje się jawnie do wielu standardowych hooków PrestaShop dla swojej podstawowej funkcjonalności, ponieważ jego głównym mechanizmem jest nadpisywanie klas. Metoda `install()` modułu może rejestrować się do `actionModuleInstall` lub `actionModuleUninstall` w celu czyszczenia, ale jego zachowanie w czasie wykonywania jest napędzane przez nadpisane klasy.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` stron front-office. | Chociaż nie jest bezpośrednio używany do podstawowej logiki URL, moduł może się tutaj zaczepić, aby załadować JS/CSS lub wykonać wstępne sprawdzenia. (Nie jest bezpośrednio używany przez ten moduł do jego podstawowej funkcji). |
| `displayRightColumn` / `displayLeftColumn` | Renderuje zawartość w bocznych kolumnach. | (Nie jest bezpośrednio używany przez ten moduł). |
| `displayProduct` | Renderuje zawartość na stronie produktu. | (Nie jest bezpośrednio używany przez ten moduł). |
| `displayFooter` | Renderuje zawartość w sekcji stopki. | (Nie jest bezpośrednio używany przez ten moduł). |
| `actionDispatcherBefore` | Przed przetworzeniem żądania przez dispatcher. | Nadpisana klasa `Dispatcher` niejawnie to obsługuje, ale moduł mógłby również użyć tego hooka do logiki przed wysłaniem. |
| `actionDispatcherAfter` | Po przetworzeniu żądania przez dispatcher. | (Nie jest bezpośrednio używany przez ten moduł). |
| `actionModuleInstall` | Wykonywane podczas instalacji modułu. | Aby wykonać zadania konfiguracyjne, takie jak rejestrowanie nadpisań, dodawanie konfiguracji do `ps_configuration`. |
| `actionModuleUninstall` | Wykonywane podczas odinstalowywania modułu. | Aby wykonać zadania czyszczenia, takie jak usuwanie nadpisań, usuwanie konfiguracji z `ps_configuration`. |

Rdzeniem działania tego modułu są jego nadpisania klas, które są ładowane automatycznie przez system autoloader PrestaShop, gdy moduł jest włączony, zamiast polegać na jawnych rejestracjach hooków dla jego głównej manipulacji adresami URL.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Usuń kod ISO języka z adresów URL”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
