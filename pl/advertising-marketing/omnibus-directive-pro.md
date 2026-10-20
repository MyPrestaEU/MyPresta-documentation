---
title: "Omnibus Directive Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop Omnibus Directive Pro od MyPresta.eu."
sidebar:
  label: "Omnibus Directive Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Omnibus Directive Pro na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/omnibus-directive-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/omnibus-directive-pro/)
>
> ---


# Omnibus Directive Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Omnibus Directive Pro)

Jest to główny ekran konfiguracji, na którym kontrolujesz podstawowe zachowanie i opcje wyświetlania modułu Omnibus Directive Pro.

#### Ustawienia ogólne

- **Włącz moduł:**

  - **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji całej funkcjonalności modułu.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Moduł rozpocznie śledzenie cen, wyświetlanie informacji o najniższej cenie, a wszystkie inne skonfigurowane funkcje staną się aktywne.
    - *Po wyłączeniu:* Moduł zatrzyma wszystkie swoje operacje, w tym śledzenie cen i wyświetlanie w front-office. Nie będą wyświetlane żadne informacje o najniższej cenie.
  - **Zalecana wartość:** TAK
  - **Scenariusz / przykład sprzedawcy:** Włącz to po instalacji, aby rozpocząć przestrzeganie dyrektywy. Wyłącz to tylko, jeśli musisz tymczasowo wstrzymać jego funkcjonalność w celu konserwacji lub konkretnych testów.
- **Wyświetl najniższą cenę na stronie produktu:**

  - **Co robi to ustawienie:** Kontroluje, czy plakietka lub tekst „najniższa cena z ostatnich 30 dni” pojawia się na poszczególnych stronach produktów, gdy produkt jest w promocji.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Informacje o najniższej cenie będą widoczne dla klientów na każdej stronie produktu, gdzie aktywna jest obniżka ceny.
    - *Po wyłączeniu:* Informacje o najniższej cenie NIE będą wyświetlane na stronach produktów, nawet jeśli produkt jest w promocji.
  - **Zalecana wartość:** TAK (Wysoce zalecane dla zgodności).
  - **Scenariusz / przykład sprzedawcy:** Musisz to włączyć, aby zachować zgodność z Dyrektywą Omnibus. Jeśli to wyłączysz, Twoje strony produktów nie będą wyświetlać wymaganych informacji podczas wyprzedaży.
- **Wyświetl najniższą cenę na listach produktów (Kategoria, Wyszukiwanie itp.):**

  - **Co robi to ustawienie:** Określa, czy informacje o najniższej cenie są wyświetlane na kartach produktów na listach (np. strony kategorii, wyniki wyszukiwania, strony producentów).
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Plakietka z najniższą ceną pojawi się na kartach produktów w widokach list, zapewniając wczesną przejrzystość klientom.
    - *Po wyłączeniu:* Informacje o najniższej cenie pojawią się tylko na indywidualnej stronie produktu, a nie na listach.
  - **Zalecana wartość:** TAK (Zalecane dla maksymalnej przejrzystości i widoczności zgodności).
  - **Scenariusz / przykład sprzedawcy:** Włączenie tego pomaga klientom szybko zidentyfikować zgodne z przepisami wyprzedaże bezpośrednio ze stron kategorii, potencjalnie zwiększając współczynnik klikalności na strony produktów.
- **Włącz wykres cen na stronie produktu:**

  - **Co robi to ustawienie:** Aktywuje interaktywny wykres na stronie produktu, który wizualnie wyświetla historię cen produktu w czasie.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Wykres zostanie osadzony na stronie produktu, umożliwiając klientom zobaczenie przeszłych wahań cen.
    - *Po wyłączeniu:* Wykres cen nie będzie wyświetlany.
  - **Zalecana wartość:** TAK (Zwiększa przejrzystość i zaufanie klientów).
  - **Scenariusz / przykład sprzedawcy:** Klienci wrażliwi na ceny lub chcący zweryfikować legalność wyprzedaży mogą skorzystać z tego wykresu. Dodaje to dodatkową warstwę zaufania.
- **URL Crona do czyszczenia historii cen:**

  - **Co robi to ustawienie:** Udostępnia unikalny URL, który po wywołaniu uruchamia automatyczny proces modułu do czyszczenia starych danych historii cen. Dzięki temu baza danych jest zoptymalizowana.
  - **Efekt zmiany tego ustawienia:** Jest to pole tylko do odczytu. Musisz skonfigurować zadanie cron na swoim serwerze, aby regularnie odwiedzać ten URL.
  - **Zalecana wartość:** Skopiuj ten URL i skonfiguruj zadanie cron.
  - **Scenariusz / przykład sprzedawcy:** Skonfiguruj zadanie cron, aby uruchamiać ten URL raz dziennie (np. o 3 rano), aby zapewnić, że baza danych historii cen pozostaje szczupła i wydajna, zapobiegając jej nadmiernemu rozrostowi w czasie.
- **Włącz dziennik audytu CSV:**

  - **Co robi to ustawienie:** Jeśli włączone, moduł wygeneruje plik CSV zawierający szczegółowy dziennik zmian cen i obliczeń najniższej ceny, co może być przydatne do audytu i weryfikacji zgodności.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Plik CSV zostanie wygenerowany i zaktualizowany o informacje audytowe.
    - *Po wyłączeniu:* Dziennik audytu nie zostanie utworzony ani utrzymany.
  - **Zalecana wartość:** NIE (Chyba że jest to specjalnie wymagane do wewnętrznego audytu lub celów prawnych, ponieważ może zużywać miejsce na dysku).
  - **Scenariusz / przykład sprzedawcy:** Jeśli Twój zespół prawny lub audytorzy wymagają weryfikowalnego zapisu Twoich działań związanych ze zgodnością, włącz to. W przeciwnym razie, zazwyczaj nie jest to potrzebne do codziennej pracy.

#### Studio Plakietek

Ta sekcja pozwala dostosować wygląd wizualny plakietki „najniższej ceny” wyświetlanej w Twoim sklepie.

- **Typ plakietki:**

  - **Co robi to ustawienie:** Wybierz między „Inteligentną plakietką” (wysoce konfigurowalną z ikonami, kolorami i tekstem) a wyświetlaniem „Prostego tekstu”.
  - **Efekt zmiany tego ustawienia:**
    - *Inteligentna plakietka:* Odblokowuje dalsze opcje dostosowywania dla wizualnie bogatej plakietki.
    - *Prosty tekst:* Wyświetla tylko zwykły tekst bez zaawansowanego stylu.
  - **Zalecana wartość:** Inteligentna plakietka (Oferuje większą kontrolę i lepszą integrację z Twoim motywem).
  - **Scenariusz / przykład sprzedawcy:** Jeśli chcesz widoczną, markową plakietkę, wybierz „Inteligentna plakietka”. Jeśli wolisz minimalistyczne podejście, „Prosty tekst” może być lepszy.
- **Pozycja plakietki (strona produktu):**

  - **Co robi to ustawienie:** Wybierz, gdzie plakietka pojawia się na stronie produktu. Opcje zazwyczaj obejmują „Obok ceny”, „Pod ceną”, „Niestandardowy hook” itp.
  - **Efekt zmiany tego ustawienia:** Zmienia wizualne umiejscowienie plakietki na stronie produktu.
  - **Zalecana wartość:** Obok ceny (Najczęstsze i prawnie jasne umiejscowienie).
  - **Scenariusz / przykład sprzedawcy:** Przetestuj różne pozycje, aby zobaczyć, co najlepiej integruje się z Twoim motywem i jest najbardziej widoczne dla klientów, nie będąc inwazyjnym.
- **Pozycja plakietki (listy produktów):**

  - **Co robi to ustawienie:** Wybierz, gdzie plakietka pojawia się na kartach produktów na stronach list. Opcje zazwyczaj obejmują „Pod nazwą produktu”, „Pod ceną”, „Niestandardowy hook” itp.
  - **Efekt zmiany tego ustawienia:** Zmienia wizualne umiejscowienie plakietki na kartach produktów.
  - **Zalecana wartość:** Pod ceną (Jasne i spójne z umiejscowieniem na stronie produktu).
  - **Scenariusz / przykład sprzedawcy:** Upewnij się, że plakietka nie nakłada się na inne elementy na kartach produktów, zwłaszcza na urządzeniach mobilnych.
- **Tekst plakietki:**

  - **Co robi to ustawienie:** Dostosuj rzeczywisty tekst wyświetlany w plakietce. Możesz użyć symboli zastępczych, takich jak `{lowest_price}` dla rzeczywistej wartości najniższej ceny.
  - **Efekt zmiany tego ustawienia:** Zmienia wiadomość, którą czytają klienci.
  - **Zalecana wartość:** „Najniższa cena w ciągu ostatnich 30 dni: {lowest\_price}” (Jasne i zgodne z przepisami).
  - **Scenariusz / przykład sprzedawcy:** Możesz przetłumaczyć ten tekst na różne języki lub nieco go przeformułować, aby pasował do tonu Twojej marki, o ile znaczenie pozostaje jasne i zgodne z przepisami.
- **Kolor tła plakietki:**

  - **Co robi to ustawienie:** Ustawia kolor tła Inteligentnej plakietki.
  - **Efekt zmiany tego ustawienia:** Zmienia wizualne tło plakietki.
  - **Zalecana wartość:** Kolor, który dobrze kontrastuje z tekstem i motywem, np. jasnoszary lub kolor akcentu marki.
  - **Scenariusz / przykład sprzedawcy:** Wybierz kolor, który sprawia, że plakietka się wyróżnia, ale nadal wygląda profesjonalnie i integruje się z projektem Twojego sklepu.
- **Kolor tekstu plakietki:**

  - **Co robi to ustawienie:** Ustawia kolor tekstu w Inteligentnej plakietce.
  - **Efekt zmiany tego ustawienia:** Zmienia wizualny kolor tekstu.
  - **Zalecana wartość:** Kolor, który jest bardzo czytelny na wybranym kolorze tła, np. czarny lub ciemnoszary.
  - **Scenariusz / przykład sprzedawcy:** Zapewnij wysoki kontrast dla dostępności i czytelności.
- **Ikona plakietki:**

  - **Co robi to ustawienie:** Pozwala wybrać ikonę do wyświetlenia obok tekstu w Inteligentnej plakietce.
  - **Efekt zmiany tego ustawienia:** Dodaje wizualną ikonę do plakietki.
  - **Zalecana wartość:** Odpowiednia ikona, taka jak ikona „etykiety” lub „informacji”.
  - **Scenariusz / przykład sprzedawcy:** Mała, wyraźna ikona może zwrócić uwagę na plakietkę i sprawić, że jej cel będzie bardziej intuicyjny.

#### Panel analityczny

Ta sekcja dostarcza informacji na temat wydajności modułu i statusu zgodności.

- **Wyświetl analizy:**
  - **Co robi to ustawienie:** Ten przycisk otwiera dedykowany panel w Twoim Panelu administracyjnym, wyświetlający statystyki związane ze śledzeniem cen, produktami w promocji i statusem zgodności.
  - **Efekt zmiany tego ustawienia:** Kliknięcie tego przycisku przenosi Cię do pulpitu nawigacyjnego analiz.
  - **Zalecana wartość:** Regularnie to sprawdzaj.
  - **Scenariusz / przykład sprzedawcy:** Użyj panelu analitycznego, aby monitorować, ile produktów aktualnie wyświetla najniższą cenę, identyfikować potencjalne problemy lub przeglądać ogólny status zgodności Twojego sklepu.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz moduł | TAK | Aktywuje/dezaktywuje wszystkie funkcje modułu. |
|  | Wyświetl najniższą cenę na stronie produktu | TAK | Pokazuje najniższą cenę z 30 dni na stronach produktów podczas wyprzedaży. |
|  | Wyświetl najniższą cenę na listach produktów | TAK | Pokazuje najniższą cenę z 30 dni na stronach kategorii/wyszukiwania podczas wyprzedaży. |
|  | Włącz wykres cen na stronie produktu | TAK | Wyświetla interaktywny wykres historii cen na stronach produktów. |
|  | URL Crona do czyszczenia historii cen | (Skopiuj i skonfiguruj) | URL do automatycznego czyszczenia bazy danych. Uruchamiaj codziennie. |
|  | Włącz dziennik audytu CSV | NIE | Tworzy szczegółowy dziennik zmian cen do celów audytu. |
| **Studio Plakietek** | Typ plakietki | Inteligentna plakietka | Wybierz między konfigurowalną plakietką a prostym tekstem. |
|  | Pozycja plakietki (strona produktu) | Obok ceny | Ustawia umiejscowienie plakietki na poszczególnych stronach produktów. |
|  | Pozycja plakietki (listy produktów) | Pod ceną | Ustawia umiejscowienie plakietki na kartach produktów na listach. |
|  | Tekst plakietki | „Najniższa cena w ciągu ostatnich 30 dni: {lowest\_price}” | Konfigurowalny tekst dla plakietki. |
|  | Kolor tła plakietki | (Zależny od motywu) | Ustawia kolor tła Inteligentnej plakietki. |
|  | Kolor tekstu plakietki | (Zależny od motywu) | Ustawia kolor tekstu Inteligentnej plakietki. |
|  | Ikona plakietki | (Odpowiednia ikona) | Dodaje wizualną ikonę do Inteligentnej plakietki. |
| **Panel analityczny** | Wyświetl analizy | (Kliknij przycisk) | Otwiera pulpit nawigacyjny dla statystyk zgodności i śledzenia cen. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Plakietka z najniższą ceną nie pojawia się na moich stronach produktów, mimo że ją włączyłem.**
O:

1.  **Sprawdź status modułu:** Upewnij się, że ustawienie „Włącz moduł” jest ustawione na TAK.
2.  **Produkt w promocji?** Plakietka pojawia się tylko dla produktów, które są aktualnie w promocji (mają zastosowaną konkretną cenę lub rabat). Upewnij się, że testowany produkt ma aktywną obniżkę ceny.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i wyczyść pamięć podręczną Smarty, pamięć podręczną przeglądarki oraz wszelkie inne pamięci podręczne (np. pamięć podręczną CDN), których możesz używać.
4.  **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany z myślą o szerokiej kompatybilności, bardzo mocno dostosowane motywy mogą wymagać drobnych korekt. Jeśli problem nadal występuje, skontaktuj się z pomocą techniczną MyPresta.eu.

**P2: Wykres historii cen nie wyświetla żadnych danych lub wygląda na niekompletny.**
O:

1.  **Moduł włączony:** Upewnij się, że „Włącz wykres cen na stronie produktu” jest ustawione na TAK.
2.  **Zmiany cen:** Wykres będzie wyświetlał dane tylko wtedy, gdy produkt miał zarejestrowane zmiany cen od momentu zainstalowania i aktywowania modułu. Jeśli cena produktu nigdy się nie zmieniła, nie będzie historii do pokazania.
3.  **Czas na zebranie danych:** Moduł potrzebuje czasu na zebranie historii cen. Jeśli właśnie go zainstalowałeś, dane będą gromadzone w miarę zmian cen w ciągu dni/tygodni.

**P3: Jak często powinienem uruchamiać zadanie Crona do czyszczenia historii cen?**
O: Zalecamy uruchamianie zadania cron raz na 24 godziny. Ta częstotliwość jest wystarczająca, aby utrzymać bazę danych w optymalnym stanie bez nadmiernego obciążania serwera.

**P4: Stylizacja mojego niestandardowego motywu koliduje z plakietką modułu. Jak to naprawić?**
O: „Studio Plakietek” oferuje szerokie możliwości dostosowywania kolorów, tekstu i ikon. Spróbuj najpierw dostosować te ustawienia, aby pasowały do Twojego motywu. Jeśli nadal występują konflikty stylów, może być konieczne, aby webmaster zastosował niestandardowe nadpisania CSS. Pliki CSS modułu są zaprojektowane tak, aby można je było łatwo nadpisać przez arkusz stylów Twojego motywu.

**P5: Co się stanie, jeśli wyłączę moduł? Czy usunie on moje dane historii cen?**
O: Wyłączenie modułu zatrzyma jego wyświetlanie w front-office i procesy w tle, ale zazwyczaj nie usuwa zebranych danych historii cen. Jeśli włączysz go ponownie później, dane powinny być nadal dostępne. Jednak w celu całkowitego usunięcia danych, musiałbyś odinstalować moduł i wybrać opcję usunięcia jego danych.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis architektury technicznej modułu Omnibus Directive Pro, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł Omnibus Directive Pro stosuje standardowy wzorzec PrestaShop MVC (Model-View-Controller), z naciskiem na hooki sterowane zdarzeniami do integracji. Głównie rozszerza `Module` dla swojej podstawowej funkcjonalności i konfiguracji, używa `ModuleFrontController` dla specyficznych działań front-office (takich jak czyszczenie cronem) i wykorzystuje szablony Smarty do renderowania. Historia cen jest zarządzana poprzez bezpośrednią interakcję z bazą danych i wartości `Configuration`. Moduł integruje „Studio Plakietek” i „Panel Analityczny” w Panelu administracyjnym w celu zwiększenia kontroli sprzedawcy i uzyskania wglądu.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

- `omnipro/controllers/front/cleanupcron.php`
  - **Nazwa klasy i klasa nadrzędna:** `OmniproCleanupcronModuleFrontController` rozszerza `ModuleFrontController`.
  - **Odpowiedzialność:** Ten kontroler jest przeznaczony do dostępu za pośrednictwem zadania cron. Po wywołaniu wykonuje wewnętrzną logikę czyszczenia danych historii cen modułu, zazwyczaj usuwając stare rekordy w celu utrzymania wydajności bazy danych. Nie renderuje żadnego wizualnego wyjścia do przeglądarki, zazwyczaj zwracając prosty komunikat o sukcesie lub błędzie.
- `omnipro/controllers/front/index.php`
  - **Nazwa klasy i klasa nadrzędna:** `OmniproIndexModuleFrontController` rozszerza `ModuleFrontController`.
  - **Odpowiedzialność:** Ten kontroler prawdopodobnie służy jako rezerwowy lub ogólny punkt wejścia dla działań modułu w front-office, które nie wymagają specyficznego routingu, lub może być miejscem zastępczym. Biorąc pod uwagę podstawową funkcję modułu, jest mniej prawdopodobne, aby bezpośrednio obsługiwał złożone interakcje użytkownika, ale mógłby być używany do prostego pobierania danych lub sprawdzania statusu.

#### Kontrolery administracyjne Back-Office

Nie zidentyfikowano dedykowanych kontrolerów administracyjnych (`controllers/admin/`), co sugeruje, że cała konfiguracja i analityka Back Office są obsługiwane bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Nie zidentyfikowano żadnych niestandardowych klas rozszerzających `ObjectModel` w katalogu `classes/`. Wskazuje to, że dane historii cen są prawdopodobnie przechowywane bezpośrednio w `ps_configuration` lub niestandardowej tabeli zarządzanej przez główny plik modułu (`omnipro/index.php`) bez dedykowanej otoczki `ObjectModel`.

### 4.4 Zasoby JavaScript (`views/js/`)

- `omnipro/views/js/admin-analytics.js`
  - **Zakres:** Back-office.
  - **Opis:** Ten skrypt jest odpowiedzialny za obsługę interaktywnych elementów i wizualizacji danych w „Panelu Analitycznym” modułu w Panelu administracyjnym. Prawdopodobnie obsługuje żądania AJAX w celu pobierania danych analitycznych, renderuje wykresy (np. przy użyciu Chart.js lub podobnych bibliotek) i aktualizuje interfejs użytkownika na podstawie interakcji użytkownika w panelu analitycznym.
- `omnipro/views/js/admin-badge-studio.js`
  - **Zakres:** Back-office.
  - **Opis:** Ten skrypt zapewnia interaktywną funkcjonalność dla ekranu konfiguracji „Studio Plakietek”. Zarządza podglądami plakietki w czasie rzeczywistym, gdy sprzedawca dostosowuje kolory, tekst, ikony i pozycje. Prawdopodobnie obsługuje selektory kolorów, aktualizacje pól wejściowych i dynamiczne renderowanie podglądu plakietki.
- `omnipro/views/js/admin-config.js`
  - **Zakres:** Back-office.
  - **Opis:** Ogólny skrypt dla głównej strony konfiguracji modułu. Może obsługiwać walidację formularzy, warunkowe wyświetlanie ustawień na podstawie innych wyborów (np. pokazywanie dostosowywania plakietki tylko, jeśli wybrano „Inteligentna plakietka”) oraz ogólne ulepszenia interfejsu użytkownika dla formularza konfiguracji.
- `omnipro/views/js/front-chart.js`
  - **Zakres:** Front-office.
  - **Opis:** Ten skrypt jest odpowiedzialny za renderowanie interaktywnego wykresu historii cen na stronie produktu. Prawdopodobnie pobiera dane cenowe za pośrednictwem AJAX (ewentualnie z dedykowanego kontrolera front-office lub hooka), inicjuje bibliotekę do tworzenia wykresów (np. Chart.js) i wizualnie wyświetla ewolucję cen klientowi.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `omnipro/views/css/admin-analytics.css`
  - **Zakres:** Stylizacja administracyjna Back-office.
  - **Opis:** Arkusze stylów specjalnie dla układu i wyglądu „Panelu Analitycznego” w konfiguracji modułu w Panelu administracyjnym.
- `omnipro/views/css/admin-badge-studio.css`
  - **Zakres:** Stylizacja administracyjna Back-office.
  - **Opis:** Arkusze stylów dla interfejsu „Studio Plakietek”, w tym stylizacja selektorów kolorów, elementów podglądu i układu opcji dostosowywania.
- `omnipro/views/css/admin-config.css`
  - **Zakres:** Stylizacja administracyjna Back-office.
  - **Opis:** Ogólna stylizacja dla głównego formularza konfiguracji modułu w Panelu administracyjnym, zapewniająca spójny i przyjazny dla użytkownika interfejs.
- `omnipro/views/css/omnibus-classic.css`
  - **Zakres:** Stylizacja klienta Front-office.
  - **Opis:** Zapewnia domyślną stylizację dla plakietki najniższej ceny i potencjalnie wykresu cen, specjalnie dostosowaną do starszych motywów PrestaShop „Classic” lub motywów, które naśladują ich strukturę.
- `omnipro/views/css/omnibus-hummingbird.css`
  - **Zakres:** Stylizacja klienta Front-office.
  - **Opis:** Zapewnia domyślną stylizację dla plakietki najniższej ceny i potencjalnie wykresu cen, specjalnie zoptymalizowaną dla nowszego motywu PrestaShop „Hummingbird”.
- `omnipro/views/css/omnibus.css`
  - **Zakres:** Stylizacja klienta Front-office.
  - **Opis:** Podstawowe style front-office dla plakietki najniższej ceny i wykresu cen, mające zastosowanie w różnych motywach. Prawdopodobnie zawiera podstawowe zasady wizualne, a `omnibus-classic.css` i `omnibus-hummingbird.css` dostarczają nadpisań lub dodatków specyficznych dla motywu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- `omnipro/lib/searchTool/views/scripts.tpl`
  - **Zakres:** Niejasny bez kontekstu, ale `lib` sugeruje bibliotekę zewnętrzną lub wewnętrzne narzędzie. `scripts.tpl` często zawiera zasoby JS lub CSS.
  - **Opis:** Ten szablon prawdopodobnie zawiera pliki JavaScript lub CSS wymagane przez wewnętrzne narzędzie wyszukiwania lub narzędzie używane przez moduł, być może do przetwarzania danych lub specyficznych komponentów interfejsu użytkownika w panelu administracyjnym.
- `omnipro/views/templates/admin/analytics-panel.tpl`
  - **Zakres:** Szablon administracyjny.
  - **Opis:** Renderuje strukturę HTML dla „Panelu Analitycznego” w Panelu administracyjnym, w tym miejsca na wykresy, statystyki i tabele danych.
- `omnipro/views/templates/admin/badge-studio.tpl`
  - **Zakres:** Szablon administracyjny.
  - **Opis:** Renderuje formularz HTML i obszar podglądu dla konfiguracji „Studio Plakietek”, umożliwiając sprzedawcom dostosowanie wyglądu plakietki najniższej ceny.
- `omnipro/views/templates/admin/configure.tpl`
  - **Zakres:** Szablon administracyjny.
  - **Opis:** Główny szablon konfiguracji modułu, renderowany przez `getContent()` w `omnipro/index.php`. Zawiera wszystkie ogólne ustawienia i prawdopodobnie zawiera `analytics-panel.tpl` i `badge-studio.tpl` lub linki do nich.
- `omnipro/views/templates/hook/omnibus-badge.tpl`
  - **Zakres:** Szablon hooka (Front-office).
  - **Opis:** Ten szablon jest renderowany w różnych hookach front-office (np. `displayProductPriceBlock`, `displayProductListFunctionalButtons`) w celu wyświetlenia kodu HTML dla plakietki najniższej ceny na stronach produktów i listach. Otrzymuje zmienne zawierające najniższą cenę i inne opcje dostosowywania plakietki.
- `omnipro/views/templates/hook/omnibus.tpl`
  - **Zakres:** Szablon hooka (Front-office).
  - **Opis:** Bardziej ogólny szablon hooka, potencjalnie używany do osadzania wykresu cen (`front-chart.js`) lub innych treści związanych z modułem na stronie produktu, lub do ogólnej inicjalizacji modułu w `displayHeader` lub `displayFooter`.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł prawdopodobnie przechowuje swoje główne ustawienia konfiguracyjne w `ps_configuration` (np. `OMNIPRO_ENABLED`, `OMNIPRO_DISPLAY_PRODUCT_PAGE`).
  - Biorąc pod uwagę funkcję „historii cen” i „czyszczenia cronem”, jest bardzo prawdopodobne, że moduł tworzy co najmniej jedną niestandardową tabelę bazy danych (np. `ps_omnipro_price_history`) do przechowywania rekordów cen produktów w czasie. Tabela ta zazwyczaj zawierałaby pola `id_product`, `id_product_attribute`, `id_shop`, `id_currency`, `price` i `date_add`.
  - Jeśli włączony jest „Dziennik audytu CSV”, może przechowywać odniesienia do wygenerowanych plików CSV lub wpisów dziennika w dedykowanej tabeli.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykiwanie zasobów CSS/JS dla front-office, inicjalizacja zmiennych JS dla całego modułu. |
| `displayProductPriceBlock` | W pobliżu ceny produktu na stronie produktu. | Renderowanie plakietki najniższej ceny (`omnibus-badge.tpl`) na stronie produktu. |
| `displayProductListFunctionalButtons` | W listach produktów (kategoria, wyszukiwanie itp.). | Renderowanie plakietki najniższej ceny (`omnibus-badge.tpl`) na kartach produktów. |
| `displayFooterProduct` | Na dole strony produktu. | Potencjalnie renderowanie wykresu cen (`omnibus.tpl` z `front-chart.js`). |
| `actionProductUpdate` | Po zaktualizowaniu produktu w Panelu administracyjnym. | Wyzwolenie rejestrowania historii cen dla zaktualizowanego produktu. |
| `actionProductAdd` | Po dodaniu nowego produktu. | Inicjalizacja rejestrowania historii cen dla nowego produktu. |
| `actionProductDelete` | Po usunięciu produktu. | Czyszczenie powiązanych danych historii cen. |
| `actionUpdateQuantity` | Po zmianie ilości produktu. | (Mniej prawdopodobne dla historii cen, ale możliwe dla powiązanej logiki). |
| `actionUpdateSpecificPrice` | Po dodaniu/zaktualizowaniu ceny specyficznej (rabatu). | Kluczowe dla wyzwolenia obliczeń najniższej ceny i logiki wyświetlania. |
| `actionFrontControllerSetMedia` | Przed renderowaniem wyjścia przez kontroler front-office. | Warunkowe dodawanie CSS/JS front-office na podstawie kontekstu strony. |
| `actionAdminControllerSetMedia` | Przed renderowaniem wyjścia przez kontroler administracyjny. | Warunkowe dodawanie CSS/JS back-office dla stron konfiguracji. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji, poprawek błędów i oficjalnego wsparcia dla modułu Omnibus Directive Pro, prosimy o zapoznanie się z kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
