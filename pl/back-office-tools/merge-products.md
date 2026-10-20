---
title: "Łączenie produktów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Łączenie produktów” od MyPresta.eu."
sidebar:
  label: "Łączenie produktów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Merge Products na MyPresta.eu](https://mypresta.eu/modules/administration-tools/merge-products.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/merge-products/)
>
> ---


# Łączenie produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł Łączenie produktów oferuje dedykowany ekran administracyjny do zarządzania procesem łączenia, dostępny z Twojego panelu administracyjnego PrestaShop.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po pierwszym kliknięciu „Konfiguruj” po instalacji, zostaniesz przeniesiony na stronę przypominającą pulpit nawigacyjny. Ta strona służy głównie jako punkt wejścia do głównego narzędzia do łączenia.

- **Co robi ten ekran:** Ta początkowa strona konfiguracji zawiera krótki przegląd i bezpośredni link do głównego narzędzia „Łączenie produktów”. Nie zawiera ona samych konkretnych ustawień, ale prowadzi Cię do miejsca, gdzie faktycznie odbywa się łączenie.
- **Wpływ zmiany tego ustawienia:** Na tym początkowym ekranie nie ma bezpośrednich ustawień do zmiany.
- **Zalecana wartość:** N/A
- **Scenariusz / przykład sprzedawcy:** To jest Twój punkt wyjścia. Stąd klikniesz przycisk lub link, aby uzyskać dostęp do podstawowej funkcjonalności modułu.

### 2.2 Dedykowany ekran administracyjny: Narzędzie Łączenie produktów (Panel administracyjny > Katalog > Łączenie produktów)

To jest główny interfejs, w którym będziesz wykonywać wszystkie operacje łączenia produktów. Możesz go znaleźć, przechodząc do **Katalog > Łączenie produktów** w menu Panelu administracyjnego PrestaShop.

Ten ekran jest podzielony na kilka sekcji, aby poprowadzić Cię przez proces łączenia:

#### Krok 1: Wybierz produkt główny

- **Co robi ta sekcja:** Tutaj definiujesz produkt „główny”. Jest to produkt, do którego wszystkie inne wybrane produkty „źródłowe” zostaną połączone, stając się jego kombinacjami.
- **Pole wprowadzania: „Szukaj produktu”**
  - **Co robi to ustawienie:** Pozwala wyszukać istniejący produkt w Twoim katalogu, aby wyznaczyć go jako produkt główny. Możesz wyszukiwać według nazwy produktu, ID, EAN lub referencji.
  - **Wpływ zmiany tego ustawienia:** Podczas pisania pojawi się lista autouzupełniania. Wybranie produktu wypełni obszar „Produkt główny” jego szczegółami. Ten produkt będzie podstawą dla nowych kombinacji.
  - **Zalecana wartość:** Wybierz produkt, który najlepiej reprezentuje skonsolidowaną listę. Na przykład, jeśli łączysz „Czerwony T-shirt S”, „Czerwony T-shirt M”, „Czerwony T-shirt L” w jeden, możesz wybrać „Czerwony T-shirt S” jako główny, a pozostałe staną się jego kombinacjami.
  - **Scenariusz / przykład sprzedawcy:** Masz „iPhone 13 (Nowy)” i „iPhone 13 (Odnowiony)” jako oddzielne produkty. Wyszukasz i wybierzesz „iPhone 13 (Nowy)” jako swój produkt główny.

#### Krok 2: Wybierz produkty źródłowe

- **Co robi ta sekcja:** Tutaj wybierasz produkty, które zostaną przekonwertowane na kombinacje i dodane do produktu głównego.
- **Pole wprowadzania: „Szukaj produktów do połączenia”**
  - **Co robi to ustawienie:** Podobnie jak w wyszukiwaniu produktu głównego, to pole pozwala znaleźć i wybrać wiele produktów, które staną się kombinacjami.
  - **Wpływ zmiany tego ustawienia:** Każdy wybrany produkt jest dodawany do listy poniżej. Są to produkty, których dane (cena, stan magazynowy, atrybuty) zostaną przeniesione do produktu głównego jako nowe kombinacje.
  - **Zalecana wartość:** Wybierz wszystkie produkty, które są wariantami wybranego produktu głównego i powinny zostać skonsolidowane.
  - **Scenariusz / przykład sprzedawcy:** Kontynuując przykład z iPhone'em, wyszukasz i wybierzesz tutaj „iPhone 13 (Odnowiony)”. Jeśli masz również „iPhone 13 (Używany - Klasa A)”, również go wybierzesz.

#### Krok 3: Skonfiguruj opcje łączenia

Ta sekcja zawiera krytyczne ustawienia, które kontrolują sposób wykonywania operacji łączenia.

- **Opcja: Tryb łączenia**

  - **Co robi to ustawienie:** Określa, w jaki sposób atrybuty produktów źródłowych są obsługiwane podczas tworzenia kombinacji.
  - **Wpływ zmiany tego ustawienia:**
    - *Dodaj nową grupę atrybutów:* Moduł utworzy nową grupę atrybutów (np. „Stan”) i atrybut dla każdego produktu źródłowego (np. „Nowy”, „Odnowiony”, „Używany”). Jest to idealne rozwiązanie, gdy produkty źródłowe różnią się cechą, która nie jest już objęta istniejącymi atrybutami.
    - *Użyj istniejącej grupy atrybutów:* Jeśli Twoje produkty źródłowe już współdzielą wspólną grupę atrybutów (np. „Rozmiar” lub „Kolor”) i chcesz je połączyć na tej podstawie, możesz to wybrać. Jest to mniej powszechne w przypadku łączenia całkowicie oddzielnych produktów, ale przydatne do konsolidacji wariantów w ramach istniejącej struktury atrybutów.
  - **Zalecana wartość:** **„Dodaj nową grupę atrybutów”** jest ogólnie zalecane do łączenia odrębnych produktów, ponieważ zapewnia jasny sposób rozróżniania nowych kombinacji.
  - **Scenariusz / przykład sprzedawcy:** Łączysz „Produkt X - Nowy” i „Produkt X - Używany”. Wybranie „Dodaj nową grupę atrybutów” utworzy grupę atrybutów „Stan” z atrybutami „Nowy” i „Używany” dla kombinacji.
- **Pole wprowadzania: Nazwa nowej grupy atrybutów (widoczne tylko, jeśli wybrano „Dodaj nową grupę atrybutów”)**

  - **Co robi to ustawienie:** Określa nazwę dla nowej grupy atrybutów, która zostanie utworzona w celu rozróżnienia połączonych kombinacji.
  - **Wpływ zmiany tego ustawienia:** Ta nazwa pojawi się na stronie Twojego produktu (np. „Stan”, „Klasa”, „Wersja”).
  - **Zalecana wartość:** Opisowa nazwa, taka jak „Stan”, „Status”, „Typ” lub „Klasa”.
  - **Scenariusz / przykład sprzedawcy:** Jeśli łączysz produkty „Nowy” i „Używany”, możesz wpisać „Stan”.
- **Opcja: Zasada produktu głównego**

  - **Co robi to ustawienie:** Definiuje, jak sam produkt główny jest traktowany podczas łączenia.
  - **Wpływ zmiany tego ustawienia:**
    - *Zachowaj jako produkt główny:* Produkt główny pozostaje produktem domyślnym, a produkty źródłowe stają się jego kombinacjami. Jego istniejące kombinacje (jeśli istnieją) są zachowywane.
    - *Konwertuj na kombinację:* Sam produkt główny jest również konwertowany na kombinację w ramach własnej listy. Jest to przydatne, jeśli chcesz, aby wszystkie warianty, w tym oryginalny produkt główny, były wybierane za pomocą nowej grupy atrybutów.
  - **Zalecana wartość:** **„Zachowaj jako produkt główny”** jest często wystarczające. Wybierz „Konwertuj na kombinację”, jeśli chcesz, aby oryginalny stan produktu głównego był wyraźnie wybieralny jako kombinacja.
  - **Scenariusz / przykład sprzedawcy:** Jeśli „iPhone 13 (Nowy)” jest Twoim produktem głównym, a łączysz z nim „iPhone 13 (Odnowiony)”, „Zachowaj jako produkt główny” oznacza, że „iPhone 13 (Nowy)” jest domyślny. Jeśli wybierzesz „Konwertuj na kombinację”, wówczas „Nowy” stanie się opcją do wyboru obok „Odnowiony”.
- **Opcja: Akcja produktu źródłowego**

  - **Co robi to ustawienie:** Określa, co dzieje się z oryginalnymi produktami źródłowymi po ich połączeniu z produktem głównym jako kombinacje.
  - **Wpływ zmiany tego ustawienia:**
    - *Dezaktywuj:* Oryginalne strony produktów źródłowych zostaną wyłączone, co uniemożliwi klientom dostęp do nich. Jest to zazwyczaj najbezpieczniejsza opcja.
    - *Usuń:* Oryginalne strony produktów źródłowych zostaną trwale usunięte z Twojego katalogu. Używaj ostrożnie, ponieważ ta akcja jest nieodwracalna.
    - *Nie rób nic:* Oryginalne strony produktów źródłowych pozostają aktywne. Jest to ogólnie niezalecane, ponieważ może prowadzić do duplikowania treści i zamieszania.
  - **Zalecana wartość:** **„Dezaktywuj”** jest najbezpieczniejszym i najczęstszym wyborem. Jeśli jesteś pewien swojego połączenia i przekierowań, „Usuń” może uporządkować Twój katalog, ale upewnij się, że masz kopie zapasowe.
  - **Scenariusz / przykład sprzedawcy:** Po połączeniu „iPhone 13 (Odnowiony)” z „iPhone 13 (Nowy)”, zazwyczaj wybierzesz „Dezaktywuj”, aby uniemożliwić klientom znalezienie starej strony produktu „Odnowiony”.
- **Opcja: Utwórz przekierowania 301**

  - **Co robi to ustawienie:** Jeśli włączone, moduł utworzy stałe (301) przekierowania ze starych adresów URL produktów źródłowych na nowy adres URL produktu głównego.
  - **Wpływ zmiany tego ustawienia:**
    - *Włączone:* Każdy klient lub wyszukiwarka próbująca uzyskać dostęp do starego adresu URL produktu źródłowego zostanie automatycznie przekierowana na stronę produktu głównego. Jest to kluczowe dla SEO, zachowania wartości linków i zapobiegania uszkodzonym linkom.
    - *Wyłączone:* Stare adresy URL produktów źródłowych doprowadzą do błędu „strona nie znaleziona”, jeśli produkt źródłowy zostanie dezaktywowany lub usunięty.
  - **Zalecana wartość:** **TAK (Włączone)**. Jest to wysoce zalecane dla SEO i doświadczenia użytkownika.
  - **Scenariusz / przykład sprzedawcy:** Klient dodał do zakładek starą stronę „iPhone 13 (Odnowiony)”. Z włączonymi przekierowaniami, automatycznie trafi na główną stronę „iPhone 13”.
- **Opcja: Rozmiar partii**

  - **Co robi to ustawienie:** Kontroluje, ile produktów jest przetwarzanych w jednej partii podczas operacji łączenia. Jest to ustawienie techniczne, aby zapobiec przekroczeniu limitu czasu serwera dla dużych połączeń.
  - **Wpływ zmiany tego ustawienia:** Niższa liczba zmniejsza obciążenie serwera, ale wydłuża proces. Wyższa liczba przyspiesza go, ale może powodować problemy na mniej wydajnych hostingach.
  - **Zalecana wartość:** Pozostaw domyślną, chyba że doświadczasz przekroczenia limitu czasu. Jeśli tak, spróbuj ją zmniejszyć.
  - **Scenariusz / przykład sprzedawcy:** Jeśli łączysz setki produktów i proces się nie powodzi, zmniejszenie rozmiaru partii może pomóc.
- **Opcja: Tylko aktywne produkty**

  - **Co robi to ustawienie:** Jeśli włączone, tylko aktywne produkty źródłowe będą brane pod uwagę do połączenia.
  - **Wpływ zmiany tego ustawienia:**
    - *Włączone:* Zapobiega łączeniu nieaktywnych produktów, co może uprościć proces i uniknąć tworzenia kombinacji dla produktów, których nie zamierzasz sprzedawać.
    - *Wyłączone:* Wszystkie produkty, aktywne lub nieaktywne, mogą być łączone.
  - **Zalecana wartość:** **TAK (Włączone)**, chyba że konkretnie potrzebujesz połączyć nieaktywne produkty.
  - **Scenariusz / przykład sprzedawcy:** Chcesz połączyć tylko produkty, które są aktualnie widoczne i dostępne do zakupu w Twoim sklepie.
- **Opcja: Wyklucz pakiety**

  - **Co robi to ustawienie:** Jeśli włączone, produkty skonfigurowane jako „pakiety” (zestawy innych produktów) zostaną wykluczone z wyboru produktów źródłowych.
  - **Wpływ zmiany tego ustawienia:** Zapobiega przypadkowemu łączeniu pakietów produktów, które mają złożone relacje i mogą nie zachowywać się zgodnie z oczekiwaniami po przekształceniu w kombinacje.
  - **Zalecana wartość:** **TAK (Włączone)**. Łączenie pakietów może prowadzić do nieoczekiwanego zachowania.
  - **Scenariusz / przykład sprzedawcy:** Masz pakiet „Zestaw startowy”. Nie chcesz, aby został on połączony jako kombinacja z innym produktem.
- **Opcja: Wyklucz produkty wirtualne**

  - **Co robi to ustawienie:** Jeśli włączone, produkty wirtualne (np. pliki do pobrania, usługi) zostaną wykluczone z wyboru produktów źródłowych.
  - **Wpływ zmiany tego ustawienia:** Zapobiega przypadkowemu łączeniu produktów wirtualnych, które zazwyczaj nie mają fizycznych atrybutów ani stanów magazynowych i mogą nie nadawać się do konwersji na kombinacje.
  - **Zalecana wartość:** **TAK (Włączone)**. Produkty wirtualne zazwyczaj nie są dobrymi kandydatami do łączenia w kombinacje produktów fizycznych.
  - **Scenariusz / przykład sprzedawcy:** Sprzedajesz e-book do pobrania. Nie chcesz, aby został on połączony jako kombinacja z fizycznym produktem książkowym.
- **Opcja: Minimalny rozmiar grupy**

  - **Co robi to ustawienie:** Ustawia minimalną liczbę produktów źródłowych wymaganą do utworzenia nowej grupy atrybutów.
  - **Wpływ zmiany tego ustawienia:** Jest to zabezpieczenie. Jeśli wybierzesz „Dodaj nową grupę atrybutów”, ale połączysz tylko jeden produkt źródłowy, to ustawienie może zapobiec utworzeniu niepotrzebnej grupy atrybutów z tylko jedną opcją.
  - **Zalecana wartość:** Pozostaw domyślną (zazwyczaj 2).
  - **Scenariusz / przykład sprzedawcy:** Jeśli przypadkowo wybierzesz tylko jeden produkt źródłowy, może to zapobiec utworzeniu przez moduł grupy atrybutów z tylko jedną opcją, co jest zbędne.
- **Opcja: Grupa atrybutów do użycia (widoczne tylko, jeśli wybrano „Użyj istniejącej grupy atrybutów”)**

  - **Co robi to ustawienie:** Pozwala wybrać istniejącą grupę atrybutów z Twojego sklepu, aby skategoryzować nowe kombinacje.
  - **Wpływ zmiany tego ustawienia:** Moduł spróbuje przypisać produkty źródłowe do atrybutów w ramach tej wybranej grupy. Wymaga to starannego planowania, aby upewnić się, że Twoje produkty źródłowe logicznie pasują do istniejącej struktury atrybutów.
  - **Zalecana wartość:** Używaj tylko, jeśli masz bardzo specyficzny scenariusz, w którym produkty źródłowe są już wariantami istniejącego atrybutu. W przeciwnym razie „Dodaj nową grupę atrybutów” jest bezpieczniejsze.
  - **Scenariusz / przykład sprzedawcy:** Masz produkty „Koszula - Niebieska” i „Koszula - Czerwona” jako oddzielne produkty i chcesz je połączyć w główny produkt „Koszula”, używając istniejącej grupy atrybutów „Kolor”.

#### Krok 4: Przegląd i łączenie

- **Przycisk: „Połącz produkty”**
  - **Co robi ten przycisk:** Inicjuje faktyczny proces łączenia na podstawie Twoich wyborów i konfiguracji.
  - **Wpływ kliknięcia:** Moduł przetworzy wybrane produkty źródłowe, przekształci je w kombinacje, przypisze je do produktu głównego, zaktualizuje stany magazynowe i ceny oraz wykona przekierowania/dezaktywacje zgodnie z konfiguracją. Zostanie wyświetlony pasek postępu lub komunikat o sukcesie.
  - **Zalecana akcja:** Dokładnie przejrzyj wszystkie swoje wybory przed kliknięciem. Upewnij się, że masz kopię zapasową swojego sklepu.
  - **Scenariusz / przykład sprzedawcy:** Po wybraniu „iPhone 13 (Nowy)” jako głównego, „iPhone 13 (Odnowiony)” jako źródłowego, ustawieniu „Stan” jako nowej grupy atrybutów i włączeniu przekierowań 301, klikasz „Połącz produkty”, aby wykonać konsolidację.

#### Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Narzędzie Łączenie produktów** | **Wyszukiwanie produktu głównego** | N/A | Wybiera główny produkt, do którego zostaną połączone inne. |
|  | **Wyszukiwanie produktów źródłowych** | N/A | Wybiera produkty do przekształcenia w kombinacje pod produktem głównym. |
|  | **Tryb łączenia** | Dodaj nową grupę atrybutów | Określa, czy zostanie utworzona nowa grupa atrybutów, czy użyta istniejąca dla kombinacji. |
|  | **Nazwa nowej grupy atrybutów** | Opisowa nazwa (np. „Stan”) | Nazwa grupy atrybutów utworzonej w celu rozróżnienia połączonych kombinacji. |
|  | **Zasada produktu głównego** | Zachowaj jako produkt główny | Definiuje, czy sam produkt główny staje się kombinacją, czy pozostaje domyślny. |
|  | **Akcja produktu źródłowego** | Dezaktywuj | Co dzieje się z oryginalnymi stronami produktów źródłowych po połączeniu (Dezaktywuj, Usuń, Nie rób nic). |
|  | **Utwórz przekierowania 301** | TAK | Tworzy stałe przekierowania ze starych adresów URL źródłowych na nowy adres URL główny. Kluczowe dla SEO. |
|  | **Rozmiar partii** | Domyślny (np. 10) | Liczba produktów przetwarzanych w partii. Dostosuj do wydajności serwera. |
|  | **Tylko aktywne produkty** | TAK | Ogranicza wybór produktów źródłowych tylko do aktywnych produktów. |
|  | **Wyklucz pakiety** | TAK | Zapobiega wybieraniu pakietów produktów jako produktów źródłowych. |
|  | **Wyklucz produkty wirtualne** | TAK | Zapobiega wybieraniu produktów wirtualnych jako produktów źródłowych. |
|  | **Minimalny rozmiar grupy** | Domyślny (np. 2) | Minimalna liczba produktów źródłowych do utworzenia nowej grupy atrybutów. |
|  | **Grupa atrybutów do użycia** | N/A (tylko w trybie „Użyj istniejącej…”) | Wybiera istniejącą grupę atrybutów do mapowania kombinacji. |
|  | **Przycisk Połącz produkty** | Kliknij po przeglądzie | Wykonuje operację łączenia. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Po połączeniu nie widzę nowych kombinacji na stronie mojego produktu.**
O1: Najpierw wyczyść pamięć podręczną PrestaShop. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Jeśli problem nadal występuje, sprawdź produkt główny w swoim Panelu administracyjnym, aby upewnić się, że kombinacje zostały utworzone poprawnie i są aktywne. Sprawdź również, czy grupa atrybutów utworzona przez moduł jest włączona i powiązana z produktem głównym.

**P2: Moje stare adresy URL produktów pokazują błędy „Strona nie znaleziona”.**
O2: Zazwyczaj oznacza to, że przekierowania 301 nie zostały utworzone lub nie działają.
1. Wróć do narzędzia „Łączenie produktów” (**Katalog > Łączenie produktów**).
2. Sprawdź, czy opcja „Utwórz przekierowania 301” była włączona podczas łączenia. Jeśli nie, będziesz musiał ręcznie skonfigurować przekierowania lub ponownie połączyć (po przywróceniu kopii zapasowej, jeśli usunąłeś produkty źródłowe).
3. Upewnij się, że plik `.htaccess` Twojego serwera jest poprawnie skonfigurowany do obsługi przyjaznych adresów URL i przekierowań PrestaShop. Czasami konfiguracje serwera mogą zakłócać działanie.

**P3: Moduł wydaje się zawieszać lub przekraczać limit czasu podczas procesu łączenia.**
O3: Może się to zdarzyć przy dużej liczbie produktów lub na serwerach o ograniczonych zasobach.
1. Spróbuj zmniejszyć ustawienie **„Rozmiar partii”** w sekcji „Konfiguruj opcje łączenia” modułu. Mniejszy rozmiar partii (np. 5 lub 10) przetworzy mniej produktów naraz, zmniejszając obciążenie serwera.
2. Sprawdź ustawienia PHP `max_execution_time` i `memory_limit` na swoim serwerze. Może być konieczne tymczasowe zwiększenie tych wartości (skontaktuj się z dostawcą hostingu, jeśli nie jesteś pewien).

**P4: Czy mogę cofnąć operację łączenia?**
O4: Moduł nie posiada przycisku „cofnij”. Dlatego **kopie zapasowe są absolutnie kluczowe**. Jeśli musisz przywrócić poprzedni stan, musisz przywrócić swój sklep z kopii zapasowej wykonanej *przed* połączeniem. Jeśli tylko dezaktywowałeś produkty źródłowe i ich nie usunąłeś, możesz ręcznie je ponownie aktywować i usunąć nowo utworzone kombinacje z produktu głównego, ale jest to złożony proces ręczny.

**P5: Co jeśli mój niestandardowy motyw nie wyświetla poprawnie nowej grupy atrybutów?**
O5: Moduł tworzy standardowe grupy atrybutów i kombinacje PrestaShop. Jeśli Twój motyw nie wyświetla ich poprawnie, prawdopodobnie jest to problem z CSS lub szablonem Smarty w Twoim motywie.
1. Sprawdź, czy domyślne motywy PrestaShop (np. Classic) wyświetlają kombinacje poprawnie. Jeśli tak, problem leży w Twoim niestandardowym motywie.
2. Może być konieczne skonsultowanie się z programistą internetowym w celu dostosowania pliku `product.tpl` Twojego motywu lub powiązanego CSS, aby poprawnie renderować nowe selektory atrybutów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Merge Products` stosuje standardowy wzorzec MVC PrestaShop dla swoich komponentów Back Office. Wykorzystuje `ObjectModel` PrestaShop do manipulacji danymi (chociaż głównie bezpośrednio wchodzi w interakcje z podstawowymi obiektami `Product` i `Combination`, a nie z niestandardowymi modelami specyficznymi dla modułu). Podstawowa logika znajdowania, budowania i łączenia produktów i ich kombinacji jest hermetyzowana w dedykowanych klasach usług. Moduł używa niestandardowego kontrolera Admin dla swojego głównego interfejsu, zapewniając przyjazną dla użytkownika siatkę i formularz do procesu łączenia. Implementuje również mechanizm logowania do śledzenia operacji łączenia.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front Office**: Brak. Moduł jest wyłącznie narzędziem administracyjnym Back Office.
- **Kontrolery Admin Back Office**:

  - `controllers/admin/AdminMyMergeProductsController.php`

    - **Nazwa klasy**: `AdminMyMergeProductsController`
    - **Klasa nadrzędna**: `ModuleAdminController`
    - **Odpowiedzialność**: Jest to główny kontroler interfejsu administracyjnego modułu. Obsługuje wyświetlanie narzędzia do łączenia, w tym wyszukiwanie produktów (autouzupełnianie), opcje konfiguracji i inicjowanie procesu łączenia. Koordynuje wywołania do podstawowych klas usług (`MmpFinder`, `MmpMergeEngine`, `MmpLogger`, `MmpRedirector`) w celu wykonania faktycznego łączenia. Zarządza przesyłaniem formularzy i wyświetla informacje zwrotne dla użytkownika.
    - **Nazwa zakładki**: „Łączenie produktów” (w menu Katalog)
    - **Zarządzana encja**: Produkty i ich kombinacje, atrybuty.
  - `controllers/admin/index.php`

    - **Nazwa klasy**: N/A (pusty plik)
    - **Klasa nadrzędna**: N/A
    - **Odpowiedzialność**: Jest to standardowy pusty plik `index.php`, często umieszczany w katalogach, aby zapobiec listowaniu katalogów na serwerach WWW. Nie pełni żadnej roli funkcjonalnej w logice modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

- `classes/index.php`

  - **Odpowiedzialność**: Standardowy pusty plik `index.php` zapobiegający listowaniu katalogów.
- `classes/MmpCombinationBuilder.php`

  - **Nazwa klasy**: `MmpCombinationBuilder`
  - **Klasa nadrzędna**: Brak (samodzielna klasa usług)
  - **Odpowiedzialność**: Ta klasa jest odpowiedzialna za złożoną logikę tworzenia nowych kombinacji produktów na podstawie produktów źródłowych. Obsługuje:
    - Mapowanie danych produktów źródłowych (cena, ilość, EAN, referencja) do nowych kombinacji.
    - Tworzenie nowych atrybutów i grup atrybutów, jeśli `MMP_MERGE_MODE` jest ustawiony na „Dodaj nową grupę atrybutów”.
    - Przypisywanie istniejących atrybutów do nowych kombinacji.
    - Obsługę obrazów dla kombinacji.
    - Zapewnienie prawidłowego stosowania zasad dotyczących stanów magazynowych i cen do nowych kombinacji.
- `classes/MmpFinder.php`

  - **Nazwa klasy**: `MmpFinder`
  - **Klasa nadrzędna**: Brak (samodzielna klasa usług)
  - **Odpowiedzialność**: Udostępnia metody wyszukiwania i pobierania produktów na podstawie różnych kryteriów (ID, nazwa, EAN, referencja). Ta klasa jest używana przez `AdminMyMergeProductsController` do funkcji wyszukiwania autouzupełniania dla produktów głównych i źródłowych. Filtruje również produkty na podstawie konfiguracji modułu (np. `MMP_ACTIVE_ONLY`, `MMP_EXCLUDE_PACKS`, `MMP_EXCLUDE_VIRTUAL`).
- `classes/MmpLogger.php`

  - **Nazwa klasy**: `MmpLogger`
  - **Klasa nadrzędna**: Brak (samodzielna klasa usług)
  - **Odpowiedzialność**: Obsługuje logowanie operacji łączenia. Rejestruje szczegóły każdego połączenia, w tym produkt główny, produkty źródłowe i użyte ustawienia konfiguracji. Jest to kluczowe dla debugowania i audytu. Prawdopodobnie przechowuje logi w niestandardowej tabeli bazy danych lub pliku.
- `classes/MmpMergeEngine.php`

  - **Nazwa klasy**: `MmpMergeEngine`
  - **Klasa nadrzędna**: Brak (samodzielna klasa usług)
  - **Odpowiedzialność**: Jest to centralny koordynator procesu łączenia. Przyjmuje produkt główny i produkty źródłowe wraz z ustawieniami konfiguracji i koordynuje działania:
    - Wywołuje `MmpCombinationBuilder` w celu utworzenia kombinacji.
    - Aktualizuje produkt główny.
    - Obsługuje `MMP_SOURCE_ACTION` (dezaktywacja lub usuwanie produktów źródłowych).
    - Zarządza przetwarzaniem wsadowym (`MMP_BATCH_SIZE`).
    - Współpracuje z `MmpRedirector` w celu przekierowań 301.
    - Wykorzystuje `MmpLogger` do rejestrowania operacji.
- `classes/MmpRedirector.php`

  - **Nazwa klasy**: `MmpRedirector`
  - **Klasa nadrzędna**: Brak (samodzielna klasa usług)
  - **Odpowiedzialność**: Zarządza tworzeniem przekierowań 301. Gdy `MMP_REDIRECT` jest włączone, ta klasa tworzy wpisy w tabeli `ps_product_redirect` PrestaShop (lub podobnym mechanizmie) w celu przekierowania starych adresów URL produktów źródłowych na nowy adres URL produktu głównego.

### 4.4 Zasoby JavaScript (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`

  - **Zakres**: Back Office.
  - **Odpowiedzialność**: Udostępnia logikę JavaScript dla pól wyszukiwania produktów z autouzupełnianiem używanych w `AdminMyMergeProductsController`. Prawdopodobnie używa AJAX do wysyłania zapytań do `MmpFinder` w celu uzyskania sugestii produktów podczas pisania przez użytkownika, wyświetlając wyniki w rozwijanej liście. Obsługuje wybór i wypełnianie odpowiednich pól produktu.
- `views/js/admin.js`

  - **Zakres**: Back Office.
  - **Odpowiedzialność**: Zawiera ogólne funkcjonalności JavaScript dla interfejsu administracyjnego modułu. Może to obejmować:
    - Warunkowe wyświetlanie pól konfiguracji (np. `Nazwa nowej grupy atrybutów` widoczna tylko, jeśli wybrano „Dodaj nową grupę atrybutów”).
    - Walidację formularzy.
    - Wywołania AJAX do inicjowania procesu łączenia i wyświetlania postępu.
    - Nasłuchiwanie zdarzeń dla przycisków i zmian w formularzach.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`

  - **Zakres**: Stylizacja panelu administracyjnego Back Office.
  - **Odpowiedzialność**: Stylizuje rozwijane menu autouzupełniania i pola wprowadzania wyszukiwania, zapewniając ich spójność wizualną i łatwość obsługi w Panelu administracyjnym PrestaShop.
- `views/css/admin.css`

  - **Zakres**: Stylizacja panelu administracyjnego Back Office.
  - **Odpowiedzialność**: Zapewnia specyficzną stylizację dla interfejsu `AdminMyMergeProductsController`, w tym układ sekcji, stylizację list produktów i ogólne ulepszenia wizualne strony konfiguracji modułu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- `lib/searchTool/views/scripts.tpl`

  - **Zakres**: Back Office.
  - **Odpowiedzialność**: Ten szablon prawdopodobnie zawiera niezbędne pliki JavaScript i CSS dla narzędzia wyszukiwania autouzupełniania, zapewniając ich załadowanie na odpowiednich stronach administracyjnych. Może zawierać tagi `script` i `link`.
- `views/templates/admin/configure_shell.tpl`

  - **Zakres**: Panel administracyjny Back Office.
  - **Odpowiedzialność**: Ten szablon służy jako otoczka lub powłoka dla głównej zawartości konfiguracji modułu. Może zawierać wspólne elementy nagłówka/stopki, nawigację lub ogólną strukturę układu dla stron administracyjnych modułu. Prawdopodobnie zawiera `dashboard.tpl`.
- `views/templates/admin/dashboard.tpl`

  - **Zakres**: Panel administracyjny Back Office.
  - **Odpowiedzialność**: Jest to główny szablon dla widoku `AdminMyMergeProductsController`. Renderuje cały interfejs narzędzia do łączenia, w tym:
    - Obszar wyboru produktu głównego.
    - Obszar wyboru produktów źródłowych.
    - Formularz opcji konfiguracji łączenia (ze wszystkimi ustawieniami, takimi jak `MMP_MERGE_MODE`, `MMP_REDIRECT`, itp.).
    - Przycisk „Połącz produkty”.
    - Wszelkie komunikaty o statusie lub wskaźniki postępu podczas łączenia.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł głównie wchodzi w interakcje z istniejącymi podstawowymi tabelami PrestaShop:
    - `ps_product`: Do pobierania informacji o produkcie i aktualizowania statusu produktu (aktywny/nieaktywny).
    - `ps_product_attribute`: Do tworzenia i zarządzania kombinacjami produktów.
    - `ps_product_attribute_shop`: Do danych kombinacji specyficznych dla sklepu.
    - `ps_product_attribute_combination`: Łączy kombinacje z atrybutami.
    - `ps_attribute_group`, `ps_attribute_group_lang`, `ps_attribute_group_shop`: Do tworzenia nowych grup atrybutów.
    - `ps_attribute`, `ps_attribute_lang`, `ps_attribute_shop`: Do tworzenia nowych atrybutów.
    - `ps_stock_available`: Do aktualizowania ilości magazynowych dla kombinacji.
    - `ps_product_lang`: Do nazw i opisów produktów.
    - `ps_product_shop`: Do danych produktów specyficznych dla sklepu.
    - `ps_url_rewrite`: Do zarządzania przyjaznymi adresami URL.
    - `ps_configuration`: Przechowuje ustawienia konfiguracji modułu (np. `MMP_MERGE_MODE`, `MMP_MASTER_RULE`, `MMP_SOURCE_ACTION`, `MMP_REDIRECT`, `MMP_BATCH_SIZE`, `MMP_ACTIVE_ONLY`, `MMP_EXCLUDE_PACKS`, `MMP_EXCLUDE_VIRTUAL`, `MMP_MIN_GROUP`, `MMP_ATTRIBUTE_GROUP`, `MMP_ATTRIBUTE_GROUP_NAME`).
  - Moduł może tworzyć niestandardową tabelę do logowania operacji łączenia (np. `ps_mmp_log` lub podobną), chociaż nie jest to wyraźnie wyszczególnione w dostarczonym spisie. Jeśli istnieje, przechowywałaby rekordy każdego zdarzenia łączenia.
  - W przypadku przekierowań 301, prawdopodobnie używa tabeli `ps_product_redirect` PrestaShop (lub podobnego mechanizmu, jeśli moduł implementuje własny handler przekierowań).
- **Tabela zarejestrowanych hooków**:
  Moduł nie rejestruje jawnie żadnych hooków Front Office (takich jak `displayHeader`, `displayProductButtons` itp.), ponieważ jest narzędziem Back Office. Jego główna interakcja z systemem hooków PrestaShop dotyczyłaby:

  - `actionAdminControllerSetMedia`: Do ładowania jego specyficznych plików CSS i JS w Back Office.
  - `actionProductUpdate` / `actionProductAdd` / `actionProductDelete`: Chociaż nie są jawnie wymienione, wewnętrzna logika modułu do modyfikowania produktów może wywoływać te podstawowe hooki PrestaShop, których inne moduły mogą nasłuchiwać.
  - `actionObjectProductAddAfter`, `actionObjectProductUpdateAfter`, `actionObjectProductDeleteAfter`: Hooki ObjectModel, które byłyby wywoływane, gdy moduł tworzy, aktualizuje lub usuwa obiekty `Product` lub `ProductAttribute`.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Łączenie produktów”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
