---
title: "Kanał Google Merchant Center - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Google merchant center feed” od MyPresta.eu."
sidebar:
  label: "Kanał Google Merchant Center - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Google merchant center feed na MyPresta.eu](https://mypresta.eu/modules/social-networks/google-merchant-center-feed.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/google-merchant-center-feed/)
>
> ---


# Kanał Google Merchant Center

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Wystarczające zasoby serwera (CPU, RAM) mogą być wymagane do generowania bardzo dużych kanałów produktów, zwłaszcza dla sklepów z dziesiątkami tysięcy produktów.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu, dostępny natychmiast po instalacji lub po kliknięciu „Konfiguruj” w Menedżerze modułów.

-   **Co robi to ustawienie:** Ta opcja kontroluje, czy selektor drzewa kategorii jest wyświetlany na ekranie eksportu produktów, umożliwiając włączanie lub wyłączanie produktów na podstawie ich kategorii.
-   **Wpływ zmiany tego ustawienia:**
    *   *Gdy włączone (zaznaczone):* Na ekranie eksportu produktów (`AdminExportProductsFeedGoogle`) zobaczysz wizualne drzewo kategorii Twojego sklepu. Pozwala to łatwo wybrać, które kategorie produktów powinny być uwzględnione lub wykluczone z Twojego kanału Google Merchant Center. Jest to kluczowe do filtrowania kanału, aby zawierał tylko odpowiednie produkty lub wykluczał konkretne kategorie, których nie chcesz reklamować w Google.
    *   *Gdy wyłączone (odznaczone):* Selektor drzewa kategorii nie pojawi się na ekranie eksportu. Oznacza to, że nie będziesz mógł filtrować produktów według kategorii bezpośrednio w interfejsie modułu. Wówczas eksportowałbyś wszystkie produkty lub polegał na innych dostępnych opcjach filtrowania (np. wykluczenia specyficzne dla produktu).
-   **Zalecana wartość:** **TAK (zaznaczone)**.
-   **Scenariusz/przykład dla sprzedawcy:** Sprzedajesz zarówno odzież, jak i pliki do pobrania. Chcesz reklamować tylko swoje produkty odzieżowe w Google Shopping. Włączając „Pokaż drzewo kategorii”, możesz łatwo wybrać tylko kategorie „Odzież” do włączenia do kanału, wykluczając kategorię „Pliki do pobrania”.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### AdminExportProductsFeedGoogleController (Panel Administracyjny > Moduły > Google merchant center feed > Eksportuj kanał produktów)

Jest to główny ekran, na którym będziesz generować i zarządzać kanałami produktów Google Merchant Center. Dostęp do niego uzyskujesz, przechodząc do **Moduły > Menedżer modułów**, znajdując „Google merchant center feed”, a następnie klikając link „Eksportuj kanał produktów” (lub podobny, w zależności od wersji PrestaShop, może to być element podmenu pod głównym wpisem modułu).

Ten ekran pozwala zdefiniować zawartość i format Twojego kanału produktów.

**Dostępne akcje i ustawienia:**

Ekran przedstawia formularz z różnymi polami odpowiadającymi atrybutom wymaganym przez Google Merchant Center. Wypełnisz je, aby dostosować swój kanał.

-   **ID:**
    *   **Cel:** Jest to unikalny identyfikator dla każdego produktu w Twoim kanale. Google używa go do dopasowania Twojego produktu do jego danych.
    *   **Wpływ zmian:** Zapewnia, że każdy produkt ma odrębny identyfikator, co jest kluczowe dla prawidłowego przetwarzania Twojego kanału przez Google.
    *   **Zalecana wartość:** Zazwyczaj mapuje się na wewnętrzny identyfikator lub referencję Twojego produktu.
-   **GTIN (Globalny Numer Jednostki Handlowej):**
    *   **Cel:** Globalne Numery Jednostek Handlowych (takie jak EAN, UPC, ISBN) to unikalne identyfikatory produktów używane globalnie. Google wymaga ich dla większości produktów.
    *   **Wpływ zmian:** Włączenie prawidłowych numerów GTIN pomaga Google dokładnie zidentyfikować Twoje produkty, poprawiając widoczność i zaufanie. Brakujące lub nieprawidłowe numery GTIN mogą prowadzić do odrzucenia produktów.
    *   **Zalecana wartość:** Mapuj na pole EAN/UPC Twojego produktu.
-   **Identifier\_exists:**
    *   **Cel:** Wskazuje, czy dla produktu istnieje unikalny identyfikator produktu (taki jak GTIN, marka, MPN).
    *   **Wpływ zmian:** Jeśli sprzedajesz produkty niestandardowe lub produkty bez standardowych identyfikatorów, ustawienie tej wartości na „nie” (lub „fałsz”) może zapobiec odrzuceniom. Dla większości standardowych produktów powinno być „tak”.
    *   **Zalecana wartość:** Zazwyczaj „tak”, jeśli podano numery GTIN.
-   **Tytuł:**
    *   **Cel:** Nazwa Twojego produktu, tak jak pojawi się w Google Shopping. Jest to kluczowe pole do przyciągania kliknięć.
    *   **Wpływ zmian:** Jasny, opisowy tytuł z odpowiednimi słowami kluczowymi poprawia widoczność w wyszukiwaniu i współczynniki klikalności.
    *   **Zalecana wartość:** Nazwa Twojego produktu, potencjalnie wzbogacona o kluczowe atrybuty (np. „Czerwona koszulka – Rozmiar M – Bawełna”).
-   **Dostępność:**
    *   **Cel:** Wskazuje, czy produkt jest dostępny w magazynie, niedostępny w magazynie, czy dostępny w przedsprzedaży.
    *   **Wpływ zmian:** Dokładna dostępność zapobiega klikaniu przez klientów niedostępnych pozycji, poprawiając doświadczenie użytkownika i zmniejszając marnotrawstwo wydatków na reklamy.
    *   **Zalecana wartość:** Automatycznie pobierana ze statusu magazynowego Twojego produktu.
-   **Availability\_date:**
    *   **Cel:** Data, kiedy produkt zamówiony w przedsprzedaży stanie się dostępny.
    *   **Wpływ zmian:** Zapewnia przejrzystość dla klientów zainteresowanych produktami w przedsprzedaży.
    *   **Zalecana wartość:** Ustaw, jeśli oferujesz przedsprzedaż.
-   **Inwentarz:**
    *   **Cel:** Ilość produktu aktualnie dostępna w magazynie.
    *   **Wpływ zmian:** Utrzymuje synchronizację Twoich ofert Google z rzeczywistymi poziomami zapasów, zapobiegając nadmiernej sprzedaży.
    *   **Zalecana wartość:** Automatycznie pobierana z ilości magazynowej Twojego produktu.
-   **Marka:**
    *   **Cel:** Nazwa marki Twojego produktu.
    *   **Wpływ zmian:** Pomaga klientom identyfikować znane marki i poprawia kategoryzację produktów w Google.
    *   **Zalecana wartość:** Marka/producent Twojego produktu.
-   **Link:**
    *   **Cel:** Bezpośredni adres URL do strony Twojego produktu w Twoim sklepie.
    *   **Wpływ zmian:** Niezbędny do kierowania klientów z Google na Twoją stronę internetową.
    *   **Zalecana wartość:** Kanoniczny adres URL Twojego produktu.
-   **Link do obrazu:**
    *   **Cel:** Adres URL głównego obrazu Twojego produktu.
    *   **Wpływ zmian:** Wysokiej jakości, wyraźne obrazy są kluczowe do przyciągania kliknięć w Google Shopping.
    *   **Zalecana wartość:** Adres URL głównego obrazu Twojego produktu.
-   **Additional\_image\_link:**
    *   **Cel:** Adresy URL dodatkowych obrazów Twojego produktu.
    *   **Wpływ zmian:** Zapewnia więcej informacji wizualnych potencjalnym klientom, pomagając im w podejmowaniu decyzji zakupowych.
    *   **Zalecana wartość:** Adresy URL dodatkowych obrazów produktu.
-   **Podtytuł pozycji:**
    *   **Cel:** Opcjonalny, krótszy opis lub dodatkowy szczegół produktu.
    *   **Wpływ zmian:** Może być używany do podkreślania kluczowych cech lub promocji.
    *   **Zalecana wartość:** Opcjonalnie, użyj dla krótkich, wpływowych szczegółów.
-   **Opis:**
    *   **Cel:** Szczegółowy opis Twojego produktu.
    *   **Wpływ zmian:** Zapewnia kompleksowe informacje klientom i pomaga Google zrozumieć trafność Twojego produktu.
    *   **Zalecana wartość:** Pełny opis Twojego produktu.
-   **Typ produktu:**
    *   **Cel:** Twoja własna kategoryzacja produktu w Twoim sklepie.
    *   **Wpływ zmian:** Pomaga Google zrozumieć Twoją hierarchię produktów i może być używany do targetowania kampanii.
    *   **Zalecana wartość:** Twoja wewnętrzna ścieżka kategorii (np. „Odzież > Koszulki > Koszulki męskie”).
-   **Stan:**
    *   **Cel:** Stan produktu (np. nowy, używany, odnowiony).
    *   **Wpływ zmian:** Dokładne informacje o stanie są kluczowe dla zaufania klientów i zasad Google.
    *   **Zalecana wartość:** Zazwyczaj „nowy” dla większości sklepów e-commerce.
-   **Cena:**
    *   **Cel:** Aktualna cena sprzedaży Twojego produktu.
    *   **Wpływ zmian:** Dokładne ceny są najważniejsze. Niezgodności między Twoim kanałem a Twoją stroną internetową mogą prowadzić do odrzuceń.
    *   **Zalecana wartość:** Aktualna cena Twojego produktu.
-   **Cena promocyjna:**
    *   **Cel:** Obniżona cena Twojego produktu, jeśli jest w promocji.
    *   **Wpływ zmian:** Podkreśla promocje i przyciąga klientów szukających okazji.
    *   **Zalecana wartość:** Konkretna cena Twojego produktu.
-   **Stawka podatku:**
    *   **Cel:** Stawka podatku mająca zastosowanie do produktu.
    *   **Wpływ zmian:** Zapewnia dokładne informacje o cenach, zwłaszcza w regionach, gdzie podatek jest obliczany przy kasie.
    *   **Zalecana wartość:** Obowiązująca stawka podatku w Twoim sklepie.
-   **Słowa kluczowe kontekstowe:**
    *   **Cel:** Dodatkowe słowa kluczowe, które pomagają Google zrozumieć Twój produkt.
    *   **Wpływ zmian:** Może poprawić trafność Twojego produktu w wynikach wyszukiwania.
    *   **Zalecana wartość:** Odpowiednie terminy wyszukiwania, których nie ma jeszcze w tytule lub opisie.
-   **Kategoria produktu Google:**
    *   **Cel:** Standaryzowana kategoryzacja produktów Google. Jest to kluczowe pole dla Google, aby zrozumieć, co sprzedajesz.
    *   **Wpływ zmian:** Prawidłowe kategoryzowanie produktów zgodnie z taksonomią Google poprawia widoczność i zapewnia, że Twoje produkty pojawiają się w odpowiednich wyszukiwaniach. Nieprawidłowe kategorie mogą prowadzić do odrzuceń.
    *   **Zalecana wartość:** Wybierz najbardziej szczegółową kategorię produktu Google, która ma zastosowanie do Twojego produktu.

**Inne ustawienia i opcje:**

-   **Eksportuj atrybut rozmiaru:**
    *   **Cel:** Określa, czy atrybuty rozmiaru produktu powinny być uwzględnione w kanale, co jest ważne dla odzieży i innych produktów zależnych od rozmiaru.
    *   **Wpływ zmian:**
        *   *Gdy włączone:* Rozmiary produktów (np. S, M, L) zostaną wyeksportowane, umożliwiając Google wyświetlanie informacji o rozmiarach i opcji filtrowania.
        *   *Gdy wyłączone:* Informacje o rozmiarach nie zostaną uwzględnione.
    *   **Zalecana wartość:** **TAK** dla sklepów odzieżowych, **NIE** dla innych typów produktów.
-   **Eksportuj wykluczone kategorie:**
    *   **Cel:** Pozwala wybrać konkretne kategorie, których produkty powinny być *wykluczone* z kanału. Działa to w połączeniu z ustawieniem „Pokaż drzewo kategorii” z głównej konfiguracji.
    *   **Wpływ zmian:** Produkty należące do wybranych kategorii nie pojawią się w wygenerowanym kanale.
    *   **Zalecana wartość:** Użyj tej opcji, aby odfiltrować produkty, których nie chcesz reklamować w Google (np. kategorie niedostępne w magazynie, usługi lub produkty o niskiej marży).
-   **Eksportuj datę dostępności:**
    *   **Cel:** Kontroluje, czy atrybut `availability_date` jest uwzględniony w kanale.
    *   **Wpływ zmian:**
        *   *Gdy włączone:* Data, kiedy produkt stanie się dostępny (dla przedsprzedaży), zostanie uwzględniona.
        *   *Gdy wyłączone:* Ta informacja zostanie pominięta.
    *   **Zalecana wartość:** **TAK**, jeśli używasz funkcji przedsprzedaży PrestaShop i chcesz przekazywać daty dostępności do Google.
-   **Przycisk Generuj kanał:**
    *   **Cel:** Inicjuje proces generowania kanału produktów XML/CSV na podstawie wszystkich wybranych opcji.
    *   **Wpływ zmian:** Tworzy plik kanału, który możesz następnie pobrać lub podać adres URL do Google Merchant Center w celu zaplanowanych pobrań.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

1.  **Początkowa konfiguracja:** Starannie zmapuj wszystkie atrybuty Google Merchant Center do pól produktów w PrestaShop. Zwróć szczególną uwagę na GTIN, Markę i Kategorię produktu Google.
2.  **Filtrowanie kategorii:** Użyj opcji „Eksportuj wykluczone kategorie”, aby precyzyjnie dostosować, które produkty są wysyłane do Google.
3.  **Generuj i testuj:** Wygeneruj kanał i prześlij go do Google Merchant Center. Monitoruj swoje konto Google Merchant Center pod kątem błędów lub ostrzeżeń.
4.  **Zaplanowane pobieranie:** Po zatwierdzeniu kanału, skonfiguruj zaplanowane pobieranie w Google Merchant Center, używając adresu URL dostarczonego przez moduł. Zapewnia to, że Google zawsze ma najnowsze dane produktów.
5.  **Regularny przegląd:** Okresowo przeglądaj diagnostykę Google Merchant Center pod kątem wszelkich odrzuceń lub ostrzeżeń i odpowiednio dostosuj ustawienia modułu lub dane produktów w PrestaShop.

#### index.php (gmfeed/controllers/admin/index.php)

Ten plik prawdopodobnie służy jako symbol zastępczy lub przekierowanie w strukturze kontrolera administracyjnego modułu i nie reprezentuje odrębnego, konfigurowalnego ekranu dla sprzedawcy. Główna konfiguracja i zarządzanie odbywa się za pośrednictwem `AdminExportProductsFeedGoogleController`.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Pokaż drzewo kategorii | TAK | Włącza filtrowanie kategorii na ekranie eksportu dla precyzyjnego wyboru produktów. |
| **AdminExportProductsFeedGoogle** | ID | ID produktu | Unikalny identyfikator dla każdego produktu w kanale. |
| | GTIN | EAN/UPC produktu | Globalny Numer Jednostki Handlowej do identyfikacji produktu. |
| | Identifier\_exists | Tak | Wskazuje, czy istnieją unikalne identyfikatory. |
| | Tytuł | Nazwa produktu | Tytuł produktu dla Google Shopping. |
| | Dostępność | Automatycznie wykrywana | Status magazynowy produktu (dostępny, niedostępny). |
| | Availability\_date | Automatycznie wykrywana | Data dostępności dla przedsprzedaży. |
| | Inwentarz | Automatycznie wykrywany | Aktualna ilość w magazynie. |
| | Marka | Producent produktu | Nazwa marki produktu. |
| | Link | URL produktu | Bezpośredni link do strony produktu. |
| | Link do obrazu | URL głównego obrazu produktu | URL głównego obrazu produktu. |
| | Additional\_image\_link | URL-e dodatkowych obrazów produktu | URL-e dodatkowych obrazów produktu. |
| | Podtytuł pozycji | Opcjonalnie | Krótki, dodatkowy szczegół produktu. |
| | Opis | Opis produktu | Szczegółowy opis produktu. |
| | Typ produktu | Twoja ścieżka kategorii | Twoja wewnętrzna kategoryzacja produktu. |
| | Stan | Nowy | Stan produktu (nowy, używany, odnowiony). |
| | Cena | Cena produktu | Aktualna cena sprzedaży. |
| | Cena promocyjna | Specyficzna cena produktu | Obniżona cena, jeśli jest w promocji. |
| | Stawka podatku | Stawka podatku w sklepie | Obowiązująca stawka podatku. |
| | Słowa kluczowe kontekstowe | Opcjonalnie | Dodatkowe słowa kluczowe dla trafności produktu. |
| | Kategoria produktu Google | Wybierz z taksonomii Google | Standaryzowana kategoria produktu Google. |
| | Eksportuj atrybut rozmiaru | TAK (dla odzieży) | Uwzględnia atrybuty rozmiaru produktu w kanale. |
| | Eksportuj wykluczone kategorie | Wybierz według potrzeb | Wyklucza produkty z wybranych kategorii. |
| | Eksportuj datę dostępności | TAK (dla przedsprzedaży) | Uwzględnia atrybut `availability_date`. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje produkty nie pojawiają się w Google Shopping lub otrzymuję odrzucenia. Co powinienem sprawdzić w pierwszej kolejności?**
O1:

-   **Konto Google Merchant Center (GMC):** Zaloguj się do swojego konta GMC i sprawdź sekcję „Diagnostyka”. To tam Google zgłasza konkretne błędy lub ostrzeżenia dotyczące Twoich produktów i kanału.
-   **Przetwarzanie kanału:** Upewnij się, że Twój kanał został pomyślnie przetworzony przez Google. Sprawdź sekcję „Kanały” w GMC.
-   **Wymagane atrybuty:** Zweryfikuj, czy wszystkie obowiązkowe atrybuty Google (ID, Tytuł, Link, Link do obrazu, Cena, Opis, GTIN/Marka/MPN, Dostępność, Kategoria produktu Google) są poprawnie zmapowane i wypełnione w ustawieniach eksportu modułu.
-   **Niezgodności danych:** Google jest bardzo rygorystyczne w kwestii zgodności cen i dostępności między Twoim kanałem a Twoją stroną internetową. Upewnij się, że dane produktów w PrestaShop są dokładne i że Google pobiera najnowszy kanał.
-   **Kategoria produktu Google:** Upewnij się, że wybrałeś najbardziej dokładną kategorię produktu Google dla swoich produktów.

**P2: Wprowadziłem zmiany w moich produktach w PrestaShop, ale nie aktualizują się one w Google Shopping.**
O2:

-   **Wygeneruj nowy kanał:** Po wprowadzeniu zmian w PrestaShop musisz wygenerować nowy kanał za pomocą przycisku „Generuj kanał” w module.
-   **Zaplanowane pobieranie Google:** Google Merchant Center musi pobrać ten zaktualizowany kanał. Jeśli masz skonfigurowane zaplanowane pobieranie, zaktualizuje się ono automatycznie w następnym zaplanowanym czasie. Możesz również ręcznie uruchomić pobieranie na swoim koncie Google Merchant Center w sekcji „Kanały” > „Pobierz teraz”.
-   **Buforowanie:** Wyczyść pamięć podręczną Smarty w PrestaShop (Parametry zaawansowane > Wydajność) i pamięć podręczną przeglądarki, aby upewnić się, że widzisz najnowszą wersję konfiguracji modułu i wygenerowanego kanału.

**P3: Jak wykluczyć niektóre produkty lub kategorie z kanału Google?**
O3:

-   Na głównym ekranie konfiguracji modułu upewnij się, że opcja „Pokaż drzewo kategorii” jest włączona.
-   Następnie, na ekranie `AdminExportProductsFeedGoogle`, użyj opcji „Eksportuj wykluczone kategorie”. Zobaczysz drzewo swoich kategorii. Wybierz kategorie, których produkty chcesz wykluczyć z kanału.
-   Wygeneruj nowy kanał po dokonaniu tych wyborów.

**P4: Proces generowania kanału trwa bardzo długo lub przekracza limit czasu dla mojego dużego sklepu.**
O4:

-   **Zasoby serwera:** Generowanie dużych kanałów może być zasobochłonne. Skontaktuj się z dostawcą hostingu, aby upewnić się, że Twój serwer ma wystarczający limit pamięci PHP, czas wykonania i zasoby procesora.
-   **Ustawienia PHP:** Zwiększ `max_execution_time` i `memory_limit` w pliku `php.ini` (lub za pośrednictwem panelu sterowania hostingu).
-   **Filtruj produkty:** Jeśli to możliwe, spróbuj segmentować swój kanał, wykluczając mniej ważne kategorie lub produkty, aby zmniejszyć rozmiar kanału.
-   **Aktualizacje modułu:** Upewnij się, że używasz najnowszej wersji modułu, ponieważ ulepszenia wydajności są często uwzględniane w aktualizacjach.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł `Google merchant center feed` przestrzega standardowej architektury modułów PrestaShop, głównie wykorzystując kontrolery Panelu Administracyjnego do konfiguracji i generowania kanałów. Wykorzystuje kontroler frontowy do udostępniania wygenerowanego adresu URL kanału dla zaplanowanych pobrań Google. Moduł nie rozszerza `ObjectModel` dla niestandardowych tabel bazy danych, ale opiera się na klasie `Configuration` PrestaShop do przechowywania ustawień. Integruje bibliotekę narzędzi wyszukiwania innych firm dla funkcji autouzupełniania.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front Office

-   `controllers/front/feed.php`
    *   **Nazwa klasy:** `GmfeedFeedModuleFrontController`
    *   **Klasa nadrzędna:** `ModuleFrontController`
    *   **Odpowiedzialność:** Ten kontroler jest odpowiedzialny za dostarczanie wygenerowanego kanału produktów XML/CSV do Google Merchant Center. Kiedy Google wykonuje zaplanowane pobieranie, trafia na adres URL obsługiwany przez ten kontroler. Kontroler pobiera najnowsze wygenerowane dane kanału i wyprowadza je, zazwyczaj z odpowiednimi nagłówkami do pobierania plików lub bezpośredniego wyświetlania.
-   `controllers/front/index.php`
    *   **Nazwa klasy:** `GmfeedIndexModuleFrontController`
    *   **Klasa nadrzędna:** `ModuleFrontController`
    *   **Odpowiedzialność:** Jest to prawdopodobnie symbol zastępczy lub domyślny kontroler frontowy, który może przekierowywać lub po prostu wyświetlać pustą stronę. Nie wydaje się mieć bezpośredniej roli funkcjonalnej w generowaniu lub wyświetlaniu kanału na podstawie dostarczonych informacji.

#### Kontrolery administracyjne Panelu Administracyjnego

-   `controllers/admin/AdminExportProductsFeedGoogle.php`
    *   **Nazwa klasy:** `AdminExportProductsFeedGoogleController`
    *   **Klasa nadrzędna:** `ModuleAdminController`
    *   **Nazwa zakładki:** „Eksportuj kanał produktów” (lub podobna, połączona z głównej konfiguracji modułu)
    *   **Zarządzana encja:** Generowanie kanału produktów.
    *   **Odpowiedzialność:** Jest to główny kontroler administracyjny do zarządzania i generowania kanału Google Merchant Center. Obsługuje wyświetlanie formularza konfiguracji dla atrybutów kanału (GTIN, Tytuł, Cena itp.), przetwarza przesłane formularze i uruchamia logikę generowania kanału. Współpracuje z danymi produktów, kategorii i atrybutów PrestaShop w celu skompilowania kanału. Zarządza również wykluczaniem kategorii (`gm_export_exclude_categories`) i innymi ustawieniami specyficznymi dla kanału.
-   `controllers/admin/index.php`
    *   **Nazwa klasy:** `GmfeedIndexModuleAdminController`
    *   **Klasa nadrzędna:** `ModuleAdminController`
    *   **Nazwa zakładki:** (Prawdopodobnie nie jest to bezpośrednia zakładka, ale część wewnętrznego routingu modułu)
    *   **Odpowiedzialność:** Podobnie jak jego odpowiednik front-office, jest to prawdopodobnie symbol zastępczy lub domyślny kontroler administracyjny. Nie wydaje się zarządzać konkretną encją ani zapewniać odrębnego interfejsu użytkownika.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dostarczone informacje wskazują, że w katalogu `classes/` nie ma niestandardowych klas ani modeli. Moduł prawdopodobnie wykonuje swoje operacje bezpośrednio w głównym pliku modułu (`gmfeed.php`) i jego kontrolerach, wykorzystując istniejące klasy `ObjectModel` PrestaShop (takie jak `Product`, `Category`, `Manufacturer`, `AttributeGroup`, `Attribute`) oraz klasę `Configuration` do przechowywania ustawień.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `gmfeed/lib/searchTool/views/js/autocomplete.js`
    *   **Zakres:** Prawdopodobnie Panel Administracyjny.
    *   **Szczegóły:** Ten skrypt jest częścią biblioteki narzędzi wyszukiwania, prawdopodobnie używanej do funkcji autouzupełniania w formularzach konfiguracji administracyjnej, takich jak wybieranie kategorii produktów Google lub wykluczanie konkretnych produktów/kategorii. Wiązałby się z polami wejściowymi, wykonywałby żądania AJAX do punktu końcowego backendu (prawdopodobnie obsługiwanego przez jeden z kontrolerów administracyjnych) w celu pobrania sugestii i wyświetlałby je użytkownikowi.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `gmfeed/lib/searchTool/views/css/autocomplete.css`
    *   **Zakres:** Stylizacja formularza administracyjnego Panelu Administracyjnego.
    *   **Szczegóły:** Zapewnia stylizację sugestii autouzupełniania i pól wejściowych, zapewniając spójny i przyjazny dla użytkownika wygląd narzędzia wyszukiwania w interfejsie administracyjnym modułu.
    *   **Kluczowe selektory CSS:** Prawdopodobnie zawiera klasy dla kontenera autouzupełniania, listy sugestii, aktywnej sugestii i pola wejściowego.
-   `gmfeed/views/admin-theme.css`
    *   **Zakres:** Stylizacja formularza administracyjnego Panelu Administracyjnego.
    *   **Szczegóły:** Zawiera ogólne reguły stylizacji specyficzne dla stron konfiguracji modułu w Panelu Administracyjnym PrestaShop. Może to obejmować dostosowania układu, stylizację przycisków, stylizację elementów formularza lub specyficzne wskazówki wizualne dla interfejsu modułu.
    *   **Kluczowe selektory CSS:** Identyfikatory lub klasy kontenerów specyficzne dla modułu, klasy elementów formularza.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

Dossier modułu wskazuje `actionAdminControllerSetMedia` jako hook front-office, co jest niezwykłe, ponieważ jest to hook administracyjny. Bardziej prawdopodobne jest, że moduł używa `actionAdminControllerSetMedia` do ładowania swoich zasobów JS/CSS w panelu administracyjnym, a poniższe szablony są renderowane w kontekście administracyjnym.

#### Szablony administracyjne (`views/templates/admin/`)

-   `gmfeed/lib/searchTool/views/scripts.tpl`
    *   **Cel:** Prawdopodobnie zawiera kod JavaScript lub inicjalizuje funkcję autouzupełniania. Ten szablon byłby renderowany w Panelu Administracyjnym w celu skonfigurowania narzędzia wyszukiwania.
-   `gmfeed/views/categories-fancybox.tpl`
    *   **Cel:** Ten szablon służy do wyświetlania drzewa kategorii do wyboru/wykluczenia, prawdopodobnie w wyskakującym okienku Fancybox (lub podobnym modalnym). Renderowałby hierarchiczną listę kategorii.
-   `gmfeed/views/exclude-products.tpl`
    *   **Cel:** Ten szablon wyświetlałby interfejs do wybierania produktów do wykluczenia z kanału, potencjalnie za pomocą narzędzia wyszukiwania i drzewa kategorii.
-   `gmfeed/views/google_lang_links.tpl`
    *   **Cel:** Ten szablon może być używany do wyświetlania linków lub informacji związanych z Google Merchant Center dla różnych języków, prawdopodobnie prowadząc sprzedawcę do konfiguracji kanałów dla różnych języków sklepu.
-   `gmfeed/views/returnAlert.tpl`
    *   **Cel:** Ogólny szablon do wyświetlania alertów lub wiadomości dla użytkownika w Panelu Administracyjnym, takich jak komunikaty o sukcesie po wygenerowaniu kanału lub powiadomienia o błędach.
-   `gmfeed/views/script-fancybox.tpl`
    *   **Cel:** Ten szablon prawdopodobnie zawiera kod JavaScript do inicjalizacji i konfiguracji biblioteki Fancybox (lub podobnego modalnego), używanej do wyświetlania wyskakujących okienek, takich jak drzewo kategorii.
-   `gmfeed/views/script.tpl`
    *   **Cel:** Ogólny szablon skryptu dla Panelu Administracyjnego modułu, potencjalnie zawierający różne funkcje JavaScript, słuchacze zdarzeń lub wywołania AJAX związane z procesem konfiguracji i generowania kanału.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Moduł nie wydaje się tworzyć niestandardowych tabel SQL na podstawie dostarczonych informacji (brak `classes/` z `ObjectModel` lub plików SQL `install/uninstall`).
    *   Ustawienia konfiguracji (np. `pf_tree`, `gm_export_size_attribute`, `gm_export_exclude_categories`, `gm_export_availability_date`) są przechowywane w tabeli `ps_configuration`. Wartość `gm_export_exclude_categories` byłaby prawdopodobnie serializowaną tablicą identyfikatorów kategorii.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny jest inicjowany, a jego media (JS/CSS) są ustawiane. | Używany przez moduł do ładowania jego specyficznych plików JavaScript i CSS (np. `autocomplete.js`, `admin-theme.css`) do Panelu Administracyjnego dla jego ekranów konfiguracji. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i najnowszych wersji modułu „Google merchant center feed”, prosimy odwołać się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu i jego integracji z Twoim sklepem PrestaShop.
