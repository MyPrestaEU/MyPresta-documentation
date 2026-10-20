---
title: "Komentarze do produktów - Rich snippet recenzji - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Komentarze do produktów - Rich snippet recenzji” od MyPresta.eu."
sidebar:
  label: "Komentarze do produktów - Rich snippet recenzji - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product Comments - Reviews rich snippet na MyPresta.eu](https://mypresta.eu/modules/seo/product-comments-reviews-rich-snippet.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/seo/product-comments-reviews-rich-snippet/)
>
> ---


# Komentarze do produktów - Rich snippet recenzji

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).
- **Zależność**: Ten moduł rozszerza funkcjonalność **darmowego modułu Komentarze do produktów PrestaShop**. Musisz mieć zainstalowany i aktywny oficjalny moduł Komentarze do produktów PrestaShop, aby ten moduł działał poprawnie.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Ten moduł ma prostą stronę konfiguracji, skupioną głównie na włączaniu lub wyłączaniu jego podstawowej funkcjonalności oraz wyborze miejsca, w którym dane rich snippet powinny być wstrzykiwane.

**Aby uzyskać dostęp:** Przejdź do **Moduły > Menedżer modułów**, wyszukaj „Komentarze do produktów - Rich snippet recenzji” i kliknij „Konfiguruj”.

#### **Włącz / Wyłącz Rich Snippets**

- **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji podstawowej funkcjonalności modułu. Po włączeniu moduł zacznie dodawać niezbędne dane strukturalne do stron Twoich produktów.
- **Efekt zmiany tego ustawienia:**
  - *Po włączeniu:* Moduł wstrzyknie kod rich snippet do stron Twoich produktów, umożliwiając Google wyświetlanie ocen gwiazdkowych i liczby recenzji w wynikach wyszukiwania.
  - *Po wyłączeniu:* Moduł przestanie wstrzykiwać kod rich snippet. Twoje oferty produktów w wynikach wyszukiwania Google powrócą do standardowego tekstu, bez gwiazdek i liczby recenzji.
- **Zalecana wartość:** **TAK** (Włączone). Głównym celem tego modułu jest wyświetlanie rich snippets, więc powinien być prawie zawsze włączony.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli testujesz moduł lub tymczasowo chcesz ukryć dane recenzji z wyników wyszukiwania (np. podczas dużej przebudowy witryny), możesz go wyłączyć. W przeciwnym razie pozostaw go włączonego, aby zmaksymalizować widoczność.

#### **Wyświetl Rich Snippets w Hooku**

- **Co robi to ustawienie:** Ta opcja pozwala wybrać, *gdzie* na stronie produktu moduł powinien wstrzykiwać dane strukturalne. Chociaż dane są niewidoczne dla klienta, ich umiejscowienie może czasami wpływać na kompatybilność z motywami lub innymi modułami.
- **Efekt zmiany tego ustawienia:**
  - *Po ustawieniu na „Nagłówek” (Header):* Dane rich snippet zostaną umieszczone w sekcji `<head>` kodu HTML strony Twojego produktu. Jest to zazwyczaj najczęstsza i zalecana lokalizacja dla danych strukturalnych.
  - *Po ustawieniu na „Produkt” (Product):* Dane rich snippet zostaną umieszczone w głównym obszarze treści produktu.
  - *Po ustawieniu na „Kolumny” (Columns):* Dane rich snippet zostaną umieszczone w jednej z bocznych kolumn Twojego sklepu (lewej lub prawej, w zależności od układu Twojego motywu).
  - *Po ustawieniu na „Stopka” (Footer):* Dane rich snippet zostaną umieszczone w sekcji `<footer>` kodu HTML strony Twojego produktu.
- **Zalecana wartość:** **Nagłówek (Header)**. Jest to najbardziej standardowa i solidna lokalizacja dla danych strukturalnych, ponieważ są one przetwarzane wcześnie przez roboty wyszukiwarek i rzadziej kolidują z elementami wizualnymi lub innymi skryptami na Twojej stronie.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli po włączeniu rich snippets doświadczysz nieoczekiwanych problemów z układem strony produktu lub innymi modułami, możesz spróbować zmienić ten hook na „Produkt” lub „Stopka” jako krok rozwiązywania problemów. Jednak „Nagłówek” jest zazwyczaj najbezpieczniejszym wyborem.

#### **Wyświetl krótkie Rich Snippets (tylko gwiazdki)**

- **Co robi to ustawienie:** Ta opcja pozwala wybrać, czy wyświetlać pełny rich snippet (gwiazdki + liczba recenzji) czy „krótką” wersję, która pokazuje tylko gwiazdki, bez liczby recenzji.
- **Efekt zmiany tego ustawienia:**
  - *Po włączeniu:* Google wyświetli tylko ocenę gwiazdkową (np. ”★★★★★ 4.5”) w wynikach wyszukiwania, pomijając część „(X recenzji)”.
  - *Po wyłączeniu:* Google wyświetli zarówno ocenę gwiazdkową, jak i liczbę recenzji (np. ”★★★★★ 4.5 (12 recenzji)”).
- **Zalecana wartość:** **NIE** (Wyłączone). Wyświetlanie zarówno gwiazdek, jak i liczby recenzji dostarcza pełniejszych informacji i często buduje większe zaufanie, zwłaszcza jeśli masz dużą liczbę recenzji.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli masz bardzo mało recenzji dla wielu produktów i uważasz, że wyświetlanie „1 recenzja” może wyglądać mniej imponująco niż same gwiazdki, możesz włączyć tę opcję. Jednak dla większości sklepów z rozsądną liczbą recenzji, wyświetlanie liczby jest korzystne.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz / Wyłącz Rich Snippets | TAK (Włączone) | Aktywuje/dezaktywuje wstrzykiwanie kodu rich snippet dla wyników wyszukiwania Google. |
| Konfiguracja modułu | Wyświetl Rich Snippets w Hooku | Nagłówek (Header) | Określa, gdzie niewidoczny kod rich snippet jest umieszczany na stronie produktu. „Nagłówek” jest zazwyczaj najlepszy dla kompatybilności. |
| Konfiguracja modułu | Wyświetl krótkie Rich Snippets (tylko gwiazdki) | NIE (Wyłączone) | Kontroluje, czy w wynikach wyszukiwania Google wyświetlane są tylko gwiazdki, czy gwiazdki + liczba recenzji. Zaleca się wyświetlanie obu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zainstalowałem moduł, ale nie widzę gwiazdek w wynikach wyszukiwania Google. Co jest nie tak?**
O: Może być kilka czynników:
1. **Czas indeksowania przez Google:** Google potrzebuje czasu na ponowne zaindeksowanie Twojej witryny i zaktualizowanie swojego indeksu. Może to trwać od kilku dni do kilku tygodni, zwłaszcza w przypadku nowych stron lub znaczących zmian.
2. **Pamięć podręczna:** Po konfiguracji wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).
3. **Google Search Console:** Sprawdź Google Search Console pod kątem „Fragmentów recenzji” w sekcji „Ulepszenia”. Jeśli występują błędy, Google może nie wyświetlać fragmentów.
4. **Brak recenzji:** Upewnij się, że produkt faktycznie ma zatwierdzone recenzje w Twoim sklepie. Google nie wyświetli gwiazdek, jeśli nie ma recenzji.
5. **Moduł Komentarze do produktów:** Sprawdź, czy oficjalny moduł Komentarze do produktów PrestaShop jest zainstalowany i aktywny. Ten moduł na nim polega.
6. **Decyzja Google:** Chociaż moduł dostarcza dane, Google ostatecznie decyduje, czy wyświetlać rich snippets. Mogą zdecydować się ich nie wyświetlać, jeśli uznają treść za nieistotną lub niskiej jakości.

**P: Moja strona produktu wygląda na uszkodzoną po zainstalowaniu modułu.**
O: Jest to bardzo mało prawdopodobne, ponieważ moduł wstrzykuje tylko niewidoczne dane strukturalne. Jeśli jednak tak się stanie:
1. **Wyłącz moduł:** Przejdź do Menedżera modułów i wyłącz „Komentarze do produktów - Rich snippet recenzji”. Jeśli strona wróci do normy, moduł może być przyczyną.
2. **Zmień ustawienie „Wyświetl Rich Snippets w Hooku”:** Spróbuj zmienić hook z „Nagłówek” na „Produkt” lub „Stopka”. Czasami mogą wystąpić konflikty motywu z określonymi miejscami hooków.
3. **Wyczyść pamięć podręczną:** Zawsze wyczyść pamięć podręczną PrestaShop po wprowadzeniu zmian.

**P: Czy ten moduł wpływa na szybkość ładowania mojej witryny?**
O: Nie, wpływ na szybkość ładowania jest znikomy. Moduł dodaje tylko mały blok tekstu (dane strukturalne) do kodu HTML Twojej strony, który jest bardzo lekki i szybko przetwarzany przez przeglądarki i wyszukiwarki.

**P: Czy mogę dostosować wygląd gwiazdek w wynikach wyszukiwania Google?**
O: Nie, wygląd gwiazdek i liczby recenzji w wynikach wyszukiwania Google jest całkowicie kontrolowany przez interfejs Google. Ten moduł dostarcza dane; Google je renderuje. Nie możesz zmienić koloru, rozmiaru ani stylu gwiazdek w wynikach wyszukiwania.

**P: Czy ten moduł będzie działał z niestandardowymi motywami?**
O: Tak, ten moduł jest zaprojektowany do działania niezależnie od wizualnego stylu Twojego motywu. Wstrzykuje dane strukturalne do kodu HTML, co jest standardową praktyką. Dopóki Twój niestandardowy motyw poprawnie implementuje system hooków PrestaShop, moduł powinien działać bez problemów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd architektury technicznej modułu „Komentarze do produktów - Rich snippet recenzji”, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł `prrs` (Product Reviews Rich Snippet) to lekki moduł PrestaShop zaprojektowany do wstrzykiwania danych strukturalnych Schema.org `AggregateRating` na strony produktów. Wykorzystuje on istniejące dane z oficjalnego modułu `productcomments`. Moduł działa głównie poprzez podłączenie się do punktu wyświetlania (konfigurowalnego przez sprzedawcę) i renderowanie szablonu Smarty zawierającego dane strukturalne JSON-LD. Przestrzega standardowej struktury modułu PrestaShop, z główną klasą modułu i kilkoma pomocniczymi zasobami.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office. Cała logika jest obsługiwana w głównym pliku modułu `index.php` i powiązanych z nim szablonach.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Opiera się głównie na istniejących podstawowych funkcjonalnościach PrestaShop i danych modułu `productcomments`.

### 4.4 Zasoby JavaScript (`views/js/`)

- **`prrs/lib/searchTool/views/js/autocomplete.js`**
  - **Zakres:** Panel administracyjny (prawdopodobnie dla wewnętrznego narzędzia wyszukiwania, choć nie jest bezpośrednio używany przez główną funkcjonalność rich snippet modułu).
  - **Odpowiedzialność:** Ten skrypt wydaje się być częścią ogólnego narzędzia autouzupełniania. Prawdopodobnie obsługuje żądania AJAX dotyczące sugestii wyszukiwania, aktualizuje pola wejściowe i zarządza wyświetlaniem wyników wyszukiwania w rozwijanej liście. Biorąc pod uwagę główną funkcję modułu, może to być pozostałość lub zależność od współdzielonej biblioteki. Nie jest bezpośrednio zaangażowany w generowanie rich snippet.

### 4.5 Arkusze stylów CSS (`views/css/`)

- **`prrs/lib/searchTool/views/css/autocomplete.css`**
  - **Zakres:** Panel administracyjny.
  - **Odpowiedzialność:** Zapewnia stylizację dla wspomnianego powyżej narzędzia wyszukiwania autouzupełniania. Obejmowałoby to style dla pola wyszukiwania, sugestii rozwijanych, podświetlonych wyników itp. Nieistotne dla wyświetlania w front-office.
- **`prrs/views/css/prrs.css`**
  - **Zakres:** Front-office.
  - **Odpowiedzialność:** Ten arkusz stylów jest prawdopodobnie minimalny lub pusty, ponieważ główną funkcją modułu jest wstrzykiwanie niewidocznych danych strukturalnych. Jeśli zawiera jakiekolwiek style, byłyby one przeznaczone dla bardzo subtelnych, nieinwazyjnych elementów lub potencjalnie dla wizualnego rozwiązania awaryjnego, gdyby same dane strukturalne miały widoczny komponent (czego zazwyczaj nie mają w przypadku rich snippets). Programiści powinni sprawdzić ten plik pod kątem wszelkich nieoczekiwanych wyników wizualnych.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **`prrs/lib/searchTool/views/scripts.tpl`**
  - **Zakres:** Panel administracyjny.
  - **Cel:** Ten szablon prawdopodobnie zawiera JavaScript dla narzędzia wyszukiwania autouzupełniania (`autocomplete.js`) i potencjalnie inne powiązane skrypty lub konfiguracje skryptów inline. Byłby renderowany w kontekście administratora.
- **`prrs/views/templates/prrs-json.tpl`**
  - **Zakres:** Front-office (strona produktu).
  - **Cel:** To jest główny szablon odpowiedzialny za generowanie danych strukturalnych JSON-LD dla rich snippet `AggregateRating`. Dynamicznie pobiera średnią ocenę produktu i liczbę recenzji z modułu `productcomments` i formatuje je zgodnie ze specyfikacjami Schema.org. Ten szablon jest renderowany, gdy opcja „Wyświetl krótkie Rich Snippets” jest wyłączona.
  - **Kluczowe punkty danych:** `product.id_product`, `product.name`, `product.link_rewrite`, `product.link`, `product.cover.bySize.home_default.url`, `average_grade`, `nb_comments`.
- **`prrs/views/templates/prrs.tpl`**
  - **Zakres:** Front-office (strona produktu).
  - **Cel:** Ten szablon jest prawdopodobnie opakowaniem lub alternatywą dla `prrs-json.tpl`, potencjalnie używanym dla starszych wersji PrestaShop lub specyficznych integracji hooków. Generuje również dane rich snippet. Ważne jest, aby zweryfikować, który szablon jest aktywnie używany na podstawie logiki `getContent()` modułu i rejestracji hooków.
- **`prrs/views/templates/shortprrs.tpl`**
  - **Zakres:** Front-office (strona produktu).
  - **Cel:** Ten szablon generuje uproszczony fragment danych strukturalnych JSON-LD, zazwyczaj zawierający tylko średnią ocenę gwiazdkową bez jawnej liczby recenzji. Jest renderowany, gdy opcja „Wyświetl krótkie Rich Snippets” jest włączona.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych.
  - Opiera się na tabeli `ps_configuration` do przechowywania swoich ustawień (np. `PRRS_ENABLED`, `PRRS_HOOK`, `PRRS_SHORT`).
  - Pobiera dane recenzji z tabel utworzonych przez oficjalny moduł `productcomments` (np. `ps_product_comment`, `ps_product_comment_criterion`).
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas / Kontekst wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` strony. | Wstrzykuje dane strukturalne JSON-LD dla rich snippets wcześnie podczas ładowania strony. Konfigurowalne za pomocą ustawień modułu. |
| `displayProductAdditionalInfo` | Renderuje się na stronie produktu, zazwyczaj poniżej głównych szczegółów produktu. | Alternatywny hook do wstrzykiwania danych strukturalnych JSON-LD. Konfigurowalne za pomocą ustawień modułu. |
| `displayLeftColumn` / `displayRightColumn` | Renderuje się w odpowiednich kolumnach bocznych. | Mniej powszechne, ale dostępne jako alternatywny hook do wstrzykiwania danych strukturalnych JSON-LD. Konfigurowalne za pomocą ustawień modułu. |
| `displayFooter` | Renderuje się w sekcji `<footer>` strony. | Alternatywny hook do wstrzykiwania danych strukturalnych JSON-LD, zazwyczaj na końcu strony. Konfigurowalne za pomocą ustawień modułu. |
| `actionFrontControllerSetMedia` | Wykonywane, gdy kontroler front-office ustawia swoje zasoby multimedialne. | Używane do rejestrowania plików CSS i JavaScript dla front-office. |
| `actionAdminControllerSetMedia` | Wykonywane, gdy kontroler administracyjny ustawia swoje zasoby multimedialne. | Używane do rejestrowania plików CSS i JavaScript dla panelu administracyjnego (np. `autocomplete.js`, `autocomplete.css`). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu „Komentarze do produktów - Rich snippet recenzji”.
"""
