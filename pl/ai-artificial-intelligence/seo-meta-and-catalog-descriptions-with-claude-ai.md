---
title: My AI Claude - AI content generation - dokumentacja i instrukcja obsługi
description: Przewodnik po konfiguracji, codziennej pracy i rozwiązywaniu problemów dla właścicieli sklepów, którzy mają już zainstalowany My AI Claude i chcą połączyć go z kontem Anthropic Claude oraz pracować na swoim katalogu.
sidebar:
  label: My AI Claude - AI content generation - dokumentacja i instrukcja obsługi
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł SEO meta and catalog descriptions with Claude AI na MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai/)
>
> ---


## 1. Wymagania

My AI Claude działa w panelu administracyjnym PrestaShop i wysyła Twoje prompty do Anthropic Claude. Potrzebuje następujących elementów.

| Element | Wymaganie | Uwagi |
|---|---|---|
| PrestaShop | 1.6, 1.7, 8 i 9 (od 1.6 do 9.99.99) | Działa w klasycznej i w nowej stronie produktu. |
| PHP | 7.0 lub nowszy | Na niższej wersji instalacja zatrzymuje się i pokazuje komunikat z wersją PHP Twojego serwera. |
| Rozszerzenia PHP | cURL, JSON, mbstring, DOM, fileinfo, GD | Standard na większości hostingów. cURL komunikuje się z Claude, DOM czyta stronę źródłową w **New product**, GD zmienia rozmiar importowanych zdjęć. |
| Ustawienie PHP | włączone `allow_url_fopen` | Potrzebne tylko dla **New product** (odczyt adresu strony źródłowej). |
| Inne moduły | Brak | Nie trzeba instalować żadnego innego modułu. |
| Baza danych | Bez dodatkowych wymagań | Moduł korzysta z wersji MySQL lub MariaDB, na której już działa PrestaShop. |
| Konto poza sklepem | Konto Anthropic z dostępem do API i środkami | Klucz utworzysz pod adresem https://console.anthropic.com/settings/keys. Każda generacja jest rozliczana przez Anthropic według zużytych tokenów. |
| Sieć | Serwer może otwierać połączenia HTTPS | Sklep łączy się z `api.anthropic.com` przy każdej generacji. Sprawdzanie aktualizacji łączy się z serwerem MyPresta.eu. Funkcja Images otwiera publiczne strony internetowe. |
| Przeglądarka | Włączony JavaScript | Wszystkie przyciski w module to skrypty działające w panelu administracyjnym. |

**Czas i pamięć.** Jedna generacja to jedno zapytanie do Claude i trwa od kilku sekund do około minuty. Limit oczekiwania ustawisz w **Settings, General** w polu **API timeout (seconds)** (na początku 120 sekund, dowolna wartość od 10 do 600). Ustaw limit czasu PHP na serwerze wyżej niż ta wartość. Uruchomienie masowe wysyła jedno zapytanie na produkt, pole i język, jedno po drugim, i działa tylko wtedy, gdy jego strona pozostaje otwarta w przeglądarce. Moduł nie uruchamia żadnego procesu w tle i nie potrzebuje więcej pamięci niż zwykła strona panelu administracyjnego.

## 2. Instalacja

### 2.1 Wgranie i instalacja

1. Otwórz **Modules → Module Manager** (PrestaShop 1.6: **Modules and Services**).
2. Kliknij **Upload a module** (PrestaShop 1.6: **Add a new module**).
3. Wybierz plik ZIP modułu i poczekaj na zakończenie wgrywania.
4. Kliknij **Install**, gdy PrestaShop to zaproponuje.
5. Poczekaj na potwierdzenie. Instalacja tworzy pozycję w menu, dwie tabele w bazie danych oraz gotowe szablony promptów (patrz 3.6).

Instalator nie czyści pamięci podręcznej. Jeśli pozycja menu się nie pojawi, otwórz **Advanced Parameters → Performance**, kliknij **Clear cache** i odśwież stronę.

Po instalacji moduł nic nie robi, dopóki nie wpiszesz klucza Anthropic. Przejdź do rozdziału 3, sekcja 3.1.

### 2.2 Gdzie pojawia się moduł

Moduł dodaje jedną pozycję menu o nazwie **AI Content Generator** w sekcji **Modules**. Kliknij ją, aby otworzyć moduł na ekranie **Dashboard**. Każdy inny ekran otwierasz z poziomego menu u góry strony modułu:

**Dashboard**, **Settings** (z podstronami **General**, **Claude**, **Studio**, **Prompt templates**, **Playground**), **Generate**, **New product**, **Cron**, **History**, **Images**, **Updates**.

Moduł dodaje też panel **Modules → My AI Claude** na każdej stronie produktu, małe przyciski **Generate with AI** obok pól tekstowych w formularzach produktu i kategorii, skrót na górnym pasku panelu administracyjnego oraz przycisk **My AI Claude** nad listą produktów. Sekcje 3.16 i 3.17 opisują każde z tych miejsc.

Jeśli pracownik, który nie jest superadministratorem, nie może otworzyć pozycji menu, nadaj profilowi tego pracownika dostęp do ekranów modułu w **Advanced Parameters → Team → Permissions**.

### 2.3 Wyłączanie i odinstalowanie

- **Wyłączenie** modułu w Module Manager ukrywa jego ekrany. Dopóki jest wyłączony, każdy adres modułu odsyła na główny dashboard PrestaShop. Wszystkie dane zostają.
- **Odinstalowanie** usuwa pozycje menu, tabelę z szablonami promptów, tabelę z historią generacji oraz wszystkie ustawienia modułu (klucz API, model, reguły Studio, ustawienia cron i sekrety cron). Historia znika razem z punktami przywracania, znikają też liczby na Dashboard.
- Odinstalowanie zostawia wszystko, co moduł już zapisał w Twoim sklepie: teksty produktów i kategorii, zaimportowane zdjęcia oraz produkty utworzone przez **New product**.
- Odinstalowanie zostawia także kilka zapisanych wyborów ekranów z filtrów **Generate** oraz ustawienia sprawdzania aktualizacji MyPresta.
- **Ponowna instalacja** zaczyna od zera: klucz API jest pusty, sekrety są nowe (adresy cron się zmieniają, więc zaktualizuj harmonogram na serwerze), History jest pusta, a gotowe szablony wracają do pierwotnego brzmienia.

## 3. Konfiguracja i codzienna praca w panelu administracyjnym

### 3.1 Cały proces krok po kroku

1. Utwórz klucz API Anthropic pod adresem https://console.anthropic.com/settings/keys i upewnij się, że konto ma środki.
2. Otwórz **AI Content Generator → Settings → Claude**. Wklej klucz w polu **Anthropic Claude API KEY**, wybierz **Model** i kliknij **Save**.
3. Otwórz **Settings → Playground**, wpisz krótkie pytanie i kliknij **Generate**. Odpowiedź na stronie potwierdza, że klucz działa.
4. Opcjonalnie: otwórz **Settings → Studio** i opisz głos marki, odbiorców, ton, preferowane terminy i zakazane słowa. Te reguły są dodawane do każdej generacji.
5. Otwórz **Settings → Prompt templates** i przeczytaj gotowe szablony. Edytuj te, które chcesz zachować, a pozostałe wyłącz.
6. Otwórz jeden produkt, przejdź do **Modules → My AI Claude**, naciśnij **Try** na karcie opisu, aby zobaczyć wynik bez zmiany produktu, a następnie naciśnij **Fill**, aby zapisać go w produkcie.
7. Otwórz **History** i sprawdź wpis. Naciśnij **Restore** w panelu produktu, jeśli chcesz odzyskać stary tekst.
8. Dla wielu produktów otwórz **Generate → Products**, przefiltruj listę, napisz lub wybierz prompt i kliknij **Run on the list below**. Najpierw przetestuj na małej liście.
9. Dla automatycznych uruchomień przez serwer skonfiguruj **Cron** (sekcja 3.12).
10. Obserwuj koszty i wolumen na **Dashboard** i w **History**. Ustaw **Monthly generation budget** w **Studio**, aby ograniczyć zużycie.

### 3.2 Otwieranie modułu i poruszanie się po nim

Kliknij **AI Content Generator** w sekcji **Modules**. Górne menu modułu zawiera **Dashboard**, **Settings**, **Generate**, **New product**, **Cron**, **History**, **Images** i **Updates**. Niektóre strony mają drugi rząd: **Settings** ma **General**, **Claude**, **Studio**, **Prompt templates** i **Playground**; **Generate** ma **Products** i **Categories**.

Nazwy w pogrubieniu to etykiety angielskiego panelu administracyjnego, a zrzuty ekranu w tej instrukcji pokazują angielski panel administracyjny. Jeśli Twój panel jest w innym języku, szukaj odpowiednich pozycji w tym samym miejscu.

Każda strona modułu ma okrągły przycisk **Help** w prawym dolnym rogu. Otwiera on panel boczny z krótkim objaśnieniem strony, na której jesteś.

### 3.3 Dashboard

![My AI Claude dashboard with request and token cards and three charts](https://mypresta.eu/docs/images/docs/myaiclaude-dashboard.webp)

Dashboard pokazuje, jak intensywnie używano modułu. Pierwszy wiersz informuje o aktywnej usłudze i modelu.

Okres wybierzesz jednym z przycisków **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time** albo wpisz własne daty w **From** i **To** i kliknij **Apply**. Strona otwiera się z **30 days**.

| Element | Znaczenie | Uwagi |
|---|---|---|
| Requests | Liczba wywołań Claude w okresie | Liczy każdy wiersz z History: uruchomienia masowe, panel produktu, Playground, górny pasek, cron. |
| Success | Wywołania, które zwróciły tekst | |
| Errors | Wywołania zakończone błędem | Przyczyna jest zapisana w wierszu History. |
| Tokens sent | Tokeny w Twoich promptach | Tokeny to jednostka, według której rozlicza Anthropic. |
| Tokens received | Tokeny w odpowiedziach | |
| Requests and errors | Wykres dzienny | Długie okresy są grupowane tygodniami. |
| Tokens sent and received | Wykres dzienny | |
| Requests by model | Wykres | Pokazuje, które modele wykonały pracę. |

Moduł dodaje też blok na głównym dashboardzie PrestaShop. Pełne dane i wykresy są na tej stronie.

### 3.4 Settings – General

![Settings General page with switches and the image search prompt](https://mypresta.eu/docs/images/docs/myaiclaude-settings-general.webp)

Otwórz **Settings → General**, zmień pola i kliknij **Save**. Komunikat **Settings Updated** potwierdza zapis.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Live mode | No | Etykieta dla Ciebie, oznaczająca, że sklep działa produkcyjnie. Nie włącza ani nie wyłącza żadnej funkcji. |
| Debug mode | No | Zapisuje w logu PrestaShop (**Advanced Parameters → Logs**) techniczne wiersze o nieudanych wywołaniach. Włącz go, gdy pomoc techniczna poprosi o szczegóły, a potem wyłącz. |
| API timeout (seconds) | 120 | Jak długo sklep czeka na Claude, zanim się podda. Wartości poniżej 10 stają się 10, powyżej 600 stają się 600, a puste lub nieprawidłowe stają się 120. Zwiększ ją przy długich opisach. |
| Product Edit History | Yes | Pokazuje zakładkę **History** w panelu produktu i pozwala tam przywracać wcześniejszy tekst. Gdy jest wyłączone, zakładka znika. Generacje nadal są zapisywane w głównej History. |
| Admin Top Bar CTA | Yes | Pokazuje małą ikonę My AI Claude na górnym pasku panelu administracyjnego (sekcja 3.17). |
| Product edit page Form | Yes | Pokazuje panel **Modules → My AI Claude** na stronie produktu. Gdy ten przełącznik i **Product Edit History** są wyłączone, panel jest pusty. |
| AI Image Finder | Yes | Włącza zakładkę **Photos** na stronie produktu. Ten sam przełącznik jest na stronie **Images**. |
| AI Image Search Prompt | Gotowy tekst | Instrukcja używana do wyszukiwania stron ze zdjęciami produktu. To samo pole jest na stronie **Images** (sekcja 3.14). |

### 3.5 Settings – Claude

![Settings Claude page with API key, model and sampling fields](https://mypresta.eu/docs/images/docs/myaiclaude-settings-claude.webp)

Ta strona łączy sklep z Twoim kontem Claude. Przy pierwszym otwarciu moduł może pokazać informację, że z pola klucza usunięto spacje. To normalne.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Anthropic Claude API KEY | Puste | Sekret, który pozwala sklepowi wywoływać Twoje konto Claude. Wklej klucz z https://console.anthropic.com/settings/keys. Spacje są usuwane przy zapisie. Zostaw pole nietknięte, aby zachować zapisany klucz. Brak klucza powoduje błąd każdego wywołania, a błąd pojawia się w **History**. |
| Model | claude-sonnet-4-5 | Model Claude, który pisze tekst. Wbudowane nazwy: claude-sonnet-4-5, claude-opus-4-5, claude-haiku-4-5, claude-3-5-sonnet-latest, claude-3-5-haiku-latest, claude-3-opus-latest oraz nazwy, które dodasz. Model, którego Twój klucz nie może użyć, zwraca błąd zamiast tekstu. |
| Add a Claude model | Puste | Wpisz dokładną nazwę modelu z konta Claude i kliknij **Add model**. Nazwa pojawi się na liście **Model**. Obok każdej dodanej nazwy jest link **Remove**. Wbudowanych nazw nie można usunąć. |
| Max Tokens | 3200 | Górny limit długości odpowiedzi, liczony w tokenach. Użyj około 256 dla meta opisu i 1000 lub więcej dla pełnego opisu. Zbyt niska wartość ucina odpowiedź. Pusta wartość jest zastępowana przez 256. |
| Temperature | 0.7 | Jak zróżnicowane jest słownictwo, od 0 do 1. Niższa wartość jest bardziej stabilna, wyższa bardziej kreatywna. Wpisz 0.1 dla najbardziej stabilnego stylu, ponieważ samo 0 jest odczytywane jako wartość początkowa 0.7. |
| Top P | 1 | Zapisywane razem z innymi polami, ale My AI Claude nie wysyła go do Claude. Zmiana nie ma efektu. |
| Frequency Penalty Value | 0 | Zapisywane, ale niewysyłane do Claude. Zmiana nie ma efektu. |
| Presence Penalty Value | 0 | Zapisywane, ale niewysyłane do Claude. Zmiana nie ma efektu. |

Kliknij **Save** na dole formularza. Potwierdzenie pojawia się, gdy wartości są poprawne. Komunikat **Anthropic Claude API KEY field is invalid!** oznacza, że pole klucza jest puste i żaden klucz nie jest jeszcze zapisany.

Jeśli model odrzuci jedno z ustawień (na przykład temperaturę), moduł usuwa to ustawienie, próbuje ponownie i zapamiętuje to dla danego modelu. Nie musisz nic robić.

Wartości próbkowania (Max Tokens, Temperature) są używane przez uruchomienia masowe, panel produktu, Playground, górny pasek i cron. **Images** używa własnych, stałych wartości.

### 3.6 Settings – Prompt templates

![Prompt templates list with title, prompt, status and actions](https://mypresta.eu/docs/images/docs/myaiclaude-settings-templates.webp)

Szablon to zapisana instrukcja, którą możesz wybrać w uruchomieniach masowych, w panelu produktu, na górnym pasku i w cron. Instalacja tworzy 16 szablonów, wszystkie włączone.

| Szablon | Cel | Uwagi |
|---|---|---|
| Product name 1, Product name 2 | Krótsze lub lepsze nazwy produktów | Name 2 używa marki i kategorii domyślnej. |
| Product description 1 to 6 | Opisy produktów | Description 1 buduje układ HTML z nagłówkami i prosi o celowe błędy ortograficzne. Usuń to zdanie, zanim go użyjesz. Description 3 prosi też o pomysły na H1, słowa kluczowe, meta tytuł i meta opis, które wszystkie trafiają do pola opisu. |
| Product description 7 - using product images | Opis z osadzonymi zdjęciami | Używa linków do zdjęć produktu. |
| Product meta title 1 to 3 | Meta tytuły | Meta title 1 prosi o język angielski i 60 znaków. |
| Product meta description 1 to 3 | Meta opisy | Meta description 1 prosi o język angielski i 160 znaków. Meta descriptions 2 i 3 są identyczne i wspominają o smartwatchu, więc przepisz je pod własne produkty. |
| Product tags | Pięć tagów w jednym wierszu | Prosi o język angielski. |

Kilka szablonów prosi o angielski w samej treści. Jeśli sprzedajesz w innym języku, edytuj te szablony i usuń ten wiersz.

Lista pokazuje **ID**, **Title**, **Prompt**, **Status** (kliknij przełącznik, aby włączyć lub wyłączyć), **Timestamp** oraz akcje wiersza do edycji lub usunięcia. Zaznacz kilka wierszy i użyj akcji zbiorczej **Delete** (pytanie **Are you sure you want to delete the selected prompts?** prosi o potwierdzenie). Najnowsze szablony są na górze, a lista pokazuje 50 wierszy na stronę.

Aby utworzyć szablon, kliknij przycisk **new** na pasku narzędzi. Aby zmienić istniejący, kliknij akcję edycji w jego wierszu.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Status | Enabled dla nowego szablonu | Tylko włączone szablony pojawiają się w selektorach modułu. |
| Prompt title | Puste (wymagane) | Nazwa, którą widzisz w selektorach i na liście. |
| Prompt content | Puste (wymagane) | Instrukcja wysyłana do Claude. Możesz używać zmiennych takich jak `{product_name}` (sekcja 3.18). Podwójne cudzysłowy są zamieniane na pojedyncze przy zapisie. |

Kliknij **Save Prompt**, aby zapisać szablon. Komunikaty to **Prompt template successfully added!** i **Prompt template successfully updated!**. Usunięty szablon pokazuje **Prompt template removed.**. Kliknij **Go Back to Module Settings**, aby wyjść z formularza bez zapisu.

Szablon mówi Claude, co ma napisać. Moduł dodaje też reguły ze **Studio** oraz język uruchomienia (reguły Studio opisuje sekcja 3.8).

### 3.7 Settings – Playground

![Playground with a text box and the Generate button](https://mypresta.eu/docs/images/docs/myaiclaude-settings-playground.webp)

Playground to wolne pole tekstowe do wypróbowania promptu. Wpisz prompt i kliknij **Generate**. Odpowiedź pojawia się na stronie. Nic nie jest zapisywane w żadnym produkcie ani kategorii.

Wywołanie jest zapisywane w History jako generacja ogólna, więc liczy się na Dashboard i do miesięcznego budżetu. Użyj Playground, aby sprawdzić klucz API, model i efekt reguł Studio.

### 3.8 Settings – Studio

![Studio page with brand voice, audience, tone, glossary and forbidden words](https://mypresta.eu/docs/images/docs/myaiclaude-settings-studio.webp)

Studio zawiera reguły dodawane do każdej generacji: uruchomień masowych, panelu produktu, kategorii, cron, Playground i górnego paska. Nawet gdy wszystkie pola Studio są puste, moduł mówi Claude, w jakim języku pisać (w języku danego uruchomienia).

| Pole | Domyślnie | Co robi |
|---|---|---|
| Brand voice | Puste | Opisuje, jak brzmi Twój sklep. Claude stosuje to w każdym tekście. |
| Audience | Puste | Opisuje klienta, dla którego piszesz. |
| Tone | Puste | Nastrój tekstu, na przykład ciepły, techniczny lub neutralny. |
| Glossary | Puste | Terminy, które Claude musi zachować dokładnie tak, jak je zapiszesz. Jeden w wierszu. |
| Forbidden words | Puste | Słowa, których Claude nie może używać. Jedno w wierszu. Claude dostaje polecenie, by ich nie używać, a gdy bramka jakości jest włączona, odpowiedź, która nadal któreś zawiera, jest odrzucana. |
| Monthly generation budget | 0 | Maksymalna liczba udanych generacji w bieżącym miesiącu kalendarzowym. 0 oznacza brak limitu. Gdy liczba zostanie osiągnięta, nowe wywołania zatrzymują się z komunikatem **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** Nieudane wywołania nie są liczone. |
| Quality gate | Yes | Sprawdza każdą odpowiedź pod kątem zakazanych słów przed zapisem. Odrzucona odpowiedź nie jest zapisywana i pokazuje **The reply was rejected because it contains a forbidden word from the studio settings.** |

Kliknij **Save studio**. Komunikat **Studio settings saved.** potwierdza zapis.

Budżet liczy wszystkie udane wiersze z History w danym miesiącu: uruchomienia masowe, panel produktu (łącznie z **Try**), Playground, górny pasek i cron. **New product** nie jest liczony.

### 3.9 Generate – Products

![Generate Products filter form](https://mypresta.eu/docs/images/docs/myaiclaude-generate-products.webp)

Otwórz **Generate → Products**. Strona działa w dwóch krokach: najpierw filtr wybiera produkty, potem panel uruchamia Claude na tej liście.

**Krok 1 – filtr.** Wypełnij pola i kliknij **Go to next step**. Formularz zawsze otwiera się z wartościami pokazanymi poniżej.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Product Categories | Nic nie zaznaczono | Zaznacz kategorie, aby ograniczyć listę do produktów w nich. Puste oznacza wszystkie kategorie. |
| Brand | All | Ogranicza listę do jednej marki. |
| Product status | Active | Active, Disabled lub Both. |
| Product stock | All products | **Only in stock products** zostawia produkty z ilością powyżej zera. |
| Update only | Update all | Trzy opcje: tylko produkty, które nie mają jeszcze wpisu w History, tylko produkty, które już go mają, albo wszystkie produkty. Liczy się każdy wpis, także nieudane wywołania i uruchomienia **Try**. |
| Product IDs | Puste | Lista ID produktów. |
| Product Reference | Puste | Ogranicza listę do produktów z tym numerem referencyjnym. |
| Product Add Date From, Product Add Date To | Puste | Ogranicza listę według daty utworzenia produktu. |
| Minimum product ID, Maximum product ID | Puste | Ogranicza listę do zakresu ID. |
| Product Limit | Puste | Maksymalna liczba produktów na liście. |

**Krok 2 – panel Mass product generation.** Pasujące produkty pojawiają się w tabeli z kolumnami **ID**, **Reference** i **Result**. Nad tabelą ustawiasz uruchomienie.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Template | Nic nie wybrano | Wybiera włączony szablon i kopiuje jego tekst do pola promptu. Tekst możesz potem edytować. |
| Prompt | Puste | Instrukcja dla Claude, ze zmiennymi takimi jak `{product_name}`. Gdy pole jest puste, moduł używa wbudowanego zlecenia dla każdego pola: opis HTML ze wstępem i listą cech, krótkie podsumowanie bez formatowania poniżej 400 znaków, meta tytuł o długości około 70 znaków i meta opis o długości około 160 znaków. |
| What to generate | Descriptions | **Descriptions** (opis długi i krótki), **Meta title and meta description** lub **Descriptions and meta together**. |
| Existing text | Replace | **Replace**, **Skip if filled**, **Add above** lub **Add below**. |
| Languages | Zaznaczony bieżący język | Zaznacz każdy język, w którym ma powstać tekst. |

Kliknij **Run on the list below**. Wiersz stanu pokazuje postęp (na przykład `3 / 40` z nazwą pola) i kończy się komunikatem **Finished N products.** Każdy wiersz pokazuje pole, wynik i komunikat, na przykład **Content successfully generated and updated to product.** lub **Product skipped.**

Zasady uruchomienia:

- Uruchomienie wysyła jedno zapytanie na produkt, pole i język, jedno po drugim. Policz zapytania przed startem, bo każde z nich jest płatne.
- Zostaw stronę otwartą. Zamknięcie lub odświeżenie zatrzymuje uruchomienie. Produkty już zapisane pozostają zapisane.
- Błąd w jednym wierszu nie zatrzymuje pozostałych. Przyczyna jest w wierszu i w **History**.
- Limity przy zapisie: nazwa produktu 128 znaków, opis krótki 800, meta tytuł 69, meta opis 159. Dłuższy tekst jest obcinany.
- Tekst jest zapisywany bezpośrednio w produkcie. Użyj panelu produktu (sekcja 3.16), aby przywrócić wcześniejszy tekst.

### 3.10 Generate – Categories

![Generate Categories filter form](https://mypresta.eu/docs/images/docs/myaiclaude-generate-categories.webp)

Otwórz **Generate → Categories**. Pierwszy formularz zawiera **Categories** (drzewo, puste oznacza wszystkie) i **Category status** (Active, Disabled lub Both, na początku Active). Kliknij **Go to next step**. Lista może zawierać kategorie Root i Home, więc zaznacz kategorie, które chcesz.

Pod filtrem pojawia się panel **Run on the categories below** z tabelą kolumn **ID** i **Result**.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Prompt | Puste | Instrukcja dla Claude. Użyj zmiennych kategorii, takich jak `{category_name}`, `{category_description}` i `{category_parent_name}`. Zmienne produktu nie są tu wypełniane. |
| Field | Description | **Description**, **Name**, **Meta title**, **Meta description** lub **Additional description**. |
| Existing text | Replace | **Replace** lub **Skip if filled**. |
| Language | Bieżący język | Jeden język na uruchomienie. |

Kliknij **Run on the categories below**. Każdy wiersz pokazuje wynik, na przykład **Content successfully generated and updated to category.** lub **Category skipped.**

Pod panelem strona pokazuje drugi formularz o nazwie **Generate category content**. Jego przycisk nie uruchamia generacji. Użyj **Run on the categories below** i zignoruj drugi formularz. Przycisk **Go Back to Category Filter** wraca do filtra.

Limity przy zapisie są takie same jak dla produktów: nazwa 128 znaków, meta tytuł 69, meta opis 159. Pole **Additional description** istnieje tylko w wersjach PrestaShop, które je mają. W przeciwnym razie wiersz pokazuje błąd.

### 3.11 New product

![New product page with the product brief and the generated draft](https://mypresta.eu/docs/images/docs/myaiclaude-new-product.webp)

**New product** tworzy kompletny produkt na podstawie krótkiego opisu. Claude pisze wersję roboczą, Ty ją czytasz, a potem moduł tworzy produkt w Twoim katalogu.

| Pole | Domyślnie | Co robi |
|---|---|---|
| What is the product? | Puste | Opisz produkt w kilku zdaniach: czym jest, dla kogo, jakie ma główne cechy. To jedyne wymagane pole. Tekst jest obcinany po 8000 znaków. |
| Optional source URL | Puste | Adres strony o produkcie. Moduł odczytuje jej tytuł, meta opis i cenę i przekazuje je Claude. |
| Language | Domyślny język sklepu | Język wersji roboczej. |
| Default category ID | 2 | ID kategorii, w której produkt zostanie umieszczony. 2 to kategoria Home standardowego sklepu. |

1. Wypełnij pola i kliknij **Generate data**. Wersja robocza pojawia się na stronie jako blok danych (nazwa, opisy, pola meta, tagi, cechy, cena). Nic nie jest jeszcze zapisane.
2. Przeczytaj wersję roboczą. Jeśli jest nietrafiona, zmień opis i kliknij **Generate data** ponownie.
3. Kliknij **Create product** dopiero wtedy, gdy akceptujesz wersję roboczą. Strona pokaże wtedy **Product #** i numer nowego produktu. Znajdziesz produkt w **Catalog → Products**.

Nowy produkt jest tworzony z takimi ustawieniami: aktywny, dostępny do zamówienia, cena widoczna, widoczny w katalogu i wyszukiwarce, stan nowy, pierwsza reguła podatkowa sklepu, stan magazynowy 100 sztuk i cena z wersji roboczej (0, gdy wersja robocza jej nie ma). Claude wypełnia też nazwę, opisy, pola meta, tagi, cechy i numer referencyjny (maksymalnie 32 znaki). Potem otwórz produkt, sprawdź cenę, podatek, stan magazynowy i zdjęcia, a zdjęcia dodaj zakładką **Photos** w panelu produktu.

Jeśli klucz nie jest zapisany, strona pokazuje **Add an API key in the module settings first.** Ta strona nie stosuje reguł Studio ani miesięcznego budżetu, a jej wywołania nie pojawiają się w **History** ani na **Dashboard**.

### 3.12 Cron

![Cron page with enable switch, secret and product cron form](https://mypresta.eu/docs/images/docs/myaiclaude-cron.webp)

Cron pozwala serwerowi generować tekst według harmonogramu, bez klikania. Strona buduje adres, który serwer ma otworzyć. Nie uruchamia żadnego harmonogramu. Zaplanowane zadanie tworzysz na swoim hostingu lub serwerze, a każde wywołanie przetwarza jedną partię i kończy działanie.

Strona ma dwa formularze: cron produktów i cron kategorii. Formularz produktów opisano poniżej. Formularz kategorii ma tę samą logikę, z własnym sekretem i własnymi ustawieniami.

Pod wstępem każdego formularza strona pokazuje adres cron. Adres produktów wygląda tak: `https://your-shop/module/myaiclaude/cron?secret=...`. Adres kategorii kończy się na `&entity=category`.

**Uzupełnij adres, zanim go użyjesz.** Dodaj `&action=generateProductContent` na końcu adresu produktów i `&action=generateCategoryContent` na końcu adresu kategorii. Bez tego adres odpowiada **Invalid action!** i nic nie robi.

Przykład dla produktów:

`https://your-shop/module/myaiclaude/cron?secret=YOUR_SECRET&action=generateProductContent`

Adres korzysta z wyborów zapisanych w formularzu: pole, cel, liczba produktów, język i szablon. Możesz je nadpisać w adresie (sekcja 6.3 wymienia parametry).

**Formularz crona produktów**

| Pole | Domyślnie | Co robi |
|---|---|---|
| Enable Cron Feature | No | Główny przełącznik obu adresów cron (produktów i kategorii). Gdy jest wyłączony, adres odpowiada **Cron Job feature is disabled. You can enable it from the module settings.** |
| Cron Job Secret Token | Losowy tekst | Długie hasło w adresie. Bez właściwego adres odpowiada **The token does not exist or it's wrong!** Przycisk **Generate Token** w tej wersji nie działa (sekcja 5.5). Wpisz własny sekret złożony z co najmniej 24 liter i cyfr, zapisz i skopiuj nowy adres do harmonogramu. |
| Update Field | description | Jedno pole zapisywane przez ten adres: name, description, description_short, meta_title, meta_description lub tags. Dla kilku pól utwórz kilka zadań. |
| Selected Products | pendingClaude | **pendingClaude** wybiera produkty, które nie mają jeszcze udanej generacji My AI Claude (dowolne pole). **pendingField** wybiera produkty bez udanej generacji dla tego pola, dzięki czemu możesz uruchomić jedno zadanie dla opisu i drugie dla nazwy na tych samych produktach. **emptyField** wybiera produkty, których wybrane pole jest puste. |
| Product Categories | Nic nie zaznaczono | Ogranicza uruchomienie do produktów w zaznaczonych kategoriach. |
| Product ID list | Puste | Tylko te ID produktów, oddzielone przecinkami. Litery są usuwane przy zapisie. |
| Language | Domyślny język sklepu | Wersja językowa, która jest zapisywana. Inne języki wymagają własnego zadania. |
| Product to update | 5 | Ile produktów przetwarza jedno wywołanie. Zacznij od 5 lub 10, aby wolna odpowiedź nie przekroczyła limitu czasu serwera. Następne wywołanie kontynuuje na produktach, które nadal pasują. |
| Prompt Template | Nic nie zapisano | Zapisana instrukcja używana dla każdego produktu w uruchomieniu. Wybierz ją i kliknij **Save**. Bez zapisanego szablonu adres odpowiada **All must include all mandatory parameters!** |
| Enable Debug | No | Po otwarciu adresu w przeglądarce pokazuje plan, zapytanie do bazy i końcowy prompt i niczego nie zapisuje. Wyłącz to, zanim harmonogram zacznie używać adresu. |
| CRON JOB interval | Every Hour | Notatka dla Ciebie o rytmie harmonogramu (od co minutę do co 6 godzin). Niczego nie planuje i nie zmienia adresu. |
| Product Cron Job command | Adres | Adres cron. Dodaj część `&action=` zgodnie z opisem powyżej. |

Kliknij **Save** pod formularzem. Formularz kategorii ma pola **Enable Debug**, **CRON JOB interval**, **Language**, **Prompt Template**, **Selected categories**, **Update Field** (name, description, meta_title, meta_description), **Categories to update** i sekret, oraz własny przycisk **Save**.

Co robi każde wywołanie:

- Zastępuje wybrane pole. Cron nie ma opcji zachowania ani dopisania tekstu.
- Stosuje reguły Studio i miesięczny budżet. Gdy budżet zostanie osiągnięty, wywołanie odpowiada **Error!Monthly generation budget reached.**
- Zapisuje wiersz w History dla każdego tekstu, więc możesz go przywrócić lub przejrzeć.
- Oba sekrety otwierają obie akcje. Cron pozostaje wyłączony, dopóki **Enable Cron Feature** nie ma wartości **Yes**.

Przetestuj z **Enable Debug** ustawionym na **Yes** i adresem otwartym w przeglądarce. Gdy plan wygląda dobrze, ustaw **No**, zapisz i utwórz zadanie.

### 3.13 History

![History page with filters, cards, breakdown panels and the prompt list](https://mypresta.eu/docs/images/docs/myaiclaude-history.webp)

History to dziennik wszystkiego, co zostało wysłane do Claude. Strona otwiera się na **This month**.

**Filtry.** Szybkie przyciski: **Today**, **7 days**, **30 days**, **This month**, **All time**. Pola: **From**, **To**, **Model**, **Type**, **Status**, **Language**, **Employee**, **Product / category ID**, **Prompt or reply contains**. Kliknij **Filter**.

**Karty.** **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time**.

**Panele zestawień.** **By day**, **By model**, **By type**, **By language**, **By employee**. Każdy pokazuje wywołania, tokeny wysłane, tokeny odebrane i sumę. Wiersze bez pracownika (wszystkie wywołania cron) pojawiają się jako Unknown.

**Lista historii promptów.**

| Kolumna | Znaczenie | Uwagi |
|---|---|---|
| ID | Numer wiersza | |
| Status | Znaczek **Success** lub **Error** | |
| Prompt | Wysłany tekst | Na liście obcięty do 180 znaków. |
| Reply / Error | Odpowiedź lub komunikat błędu | Na liście obcięte do 180 znaków. |
| Provider | Usługa, model, numer statusu błędu, jeśli Claude go zwrócił, oraz czas w sekundach | |
| Sent, Received, Total | Tokeny | |
| Entity ID | Produkt lub kategoria | Puste dla wywołań z Playground i górnego paska. |
| Type | Co zostało wygenerowane | Patrz następna tabela. |
| Timestamp | Data i godzina | |

Kliknij akcję podglądu w wierszu, aby zobaczyć pełny prompt i odpowiedź oraz link **Back to the list**. Lista pokazuje 50 wierszy na stronę.

| Type | Znaczenie | Uwagi |
|---|---|---|
| general | Playground i górny pasek | Bez produktu i kategorii. |
| product_name, product_description, product_description_short, product_meta_title, product_meta_description, product_tags | Jedno pole produktu | Zapisywane przez uruchomienia masowe, panel produktu, przyciski z logo i cron. |
| product_seo_pack | Pakiet SEO z panelu produktu | Nazwa, opisy i pola meta w jednym zapytaniu. |
| category_name, category_description, category_meta_title, category_meta_description, category_additional_description | Jedno pole kategorii | |
| error | Nieudane wywołanie | Przyczyna jest w **Reply / Error**. |

**Clear list** na pasku narzędzi usuwa **wszystkie** wiersze po potwierdzeniu i pokazuje **Log list successfully deleted.** Tego nie można cofnąć. Usuwa też punkty przywracania wszystkich produktów, opróżnia Dashboard, zeruje licznik miesięcznego budżetu i zmienia to, które produkty uchodzą za już przetworzone w **Update only** oraz w celach cron. Najpierw wyeksportuj lub zanotuj, czego potrzebujesz.

Gdy w wybranym okresie nie ma wierszy, strona pokazuje **No generations in this range.**

### 3.14 Images

![Images page with the image finder switch and search prompt](https://mypresta.eu/docs/images/docs/myaiclaude-images.webp)

Ta strona steruje zakładką **Photos** na stronie produktu. Formularz nazywa się **AI Image Finder**.

| Pole | Domyślnie | Co robi |
|---|---|---|
| AI Image Finder | Yes | Włącza zakładkę **Photos** na stronie produktu. Gdy jest wyłączone, zakładka informuje, by włączyć je w **Settings → General**. |
| AI Image Search Prompt | Gotowy tekst | Instrukcja wysyłana do Claude w celu znalezienia stron internetowych pokazujących produkt. Użyj `{product_name}` i `{product_description}` jako zmiennych. Zachowaj prośbę o dokładnie pięć adresów stron zwróconych jako lista, ponieważ moduł czyta tę listę. |

Gotowy prompt prosi o dokładnie pięć adresów stron, które pokazują produkt, jako listę JSON, z użyciem nazwy i opisu produktu.

Kliknij **Save**. Komunikat **Settings saved.** potwierdza zapis. Strona i zakładka w **Settings → General** współdzielą ten sam przełącznik i prompt.

### 3.15 Updates

![Updates page with manual check and automatic notifications](https://mypresta.eu/docs/images/docs/myaiclaude-updates.webp)

Strona **Updates** sprawdza, czy istnieje nowsza wersja My AI Claude. Sprawdzenie wysyła nazwę modułu, jego wersję i adres sklepu na serwer MyPresta.eu.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Manual Check | Przycisk **Check Now** | Uruchamia sprawdzenie od razu. Odpowiedź to **Module is up to date!** lub **New version available!** |
| Automatic Notifications | Enabled | Gdy jest włączone, moduł sprawdza mniej więcej co trzy dni i pokazuje w panelu administracyjnym informację, gdy istnieje nowa wersja. |
| Product Page | Link | Otwiera stronę modułu na MyPresta.eu. |

Kliknij **Save**. Komunikat **Update settings saved.** potwierdza zapis.

### 3.16 Strona produktu – Modules → My AI Claude

![Product page with the My AI Claude panel and field cards](https://mypresta.eu/docs/images/docs/myaiclaude-product-edit.webp)

Otwórz dowolny produkt, przejdź do zakładki **Modules** i znajdź **My AI Claude**. Panel ma zakładki **Generate**, **Simulate**, **Photos** i **History**. Zapisz nowy produkt raz, zanim użyjesz panelu, ponieważ panel działa na zapisanym produkcie.

**Generate i Simulate.**

1. Wybierz znacznik języka lub **Every language**. Na początku zaznaczony jest pierwszy język sklepu.
2. W polu **If the field already has text** wybierz **Replace**, **Add above**, **Add below** lub **Skip if filled**. Na początku zaznaczone jest **Replace**.
3. Naciśnij **Fill** na karcie: **Description**, **Short description**, **Name**, **Meta title**, **Meta description** lub **Tags**. Tekst jest zapisywany bezpośrednio w produkcie.
4. Karta **SEO pack** ma **Fill all**. Jedno zapytanie zwraca nazwę, oba opisy i oba pola meta. Nadpisuje te pola, łącznie z nazwą. Komunikat **SEO pack saved. Refresh the product to see it.** to potwierdza. Jeśli Claude nie zwróci użytecznego pakietu, panel pokazuje **The model did not return a usable SEO pack.**
5. Otwórz **Use your own instruction or a saved prompt**, aby przefiltrować i wybrać **Standard brief** lub włączony szablon, albo wpisz własny tekst w polu **Instruction**. Przy pustym polu używane jest standardowe zlecenie dla danej karty.
6. Odpowiedź i liczba tokenów pojawiają się pod kartami.

W zakładce **Simulate** te same karty mają **Try**. **Try** pokazuje odpowiedź i nie zmienia produktu. Mimo to jest zapisywane w History i liczone do budżetu, a produkt uchodzi przez to za już przetworzony dla **Update only** i dla cron.

**Po Fill odśwież stronę produktu.** Otwarty formularz nadal zawiera stary tekst. Jeśli naciśniesz **Save** w PrestaShop bez odświeżenia, PrestaShop nadpisze nowy tekst starym.

**Photos.**

![Photos tab with found photos ready to be added](https://mypresta.eu/docs/images/docs/myaiclaude-product-photos.webp)

1. Otwórz zakładkę **Photos** i kliknij **Find pages**. Komunikaty: **Looking for photos…** i **Reading photos…**.
2. Zaznacz zdjęcia, które chcesz. Strona pokazuje **Tick the photos you want, then add them to this product.**
3. Kliknij **Add selected to this product**. Pojawia się komunikat **Adding the photos to this product…**, a potem liczba zaimportowanych obrazów.
4. Odśwież stronę produktu, aby zobaczyć zdjęcia.

Wyszukiwarka czyta do 5 stron i oferuje do 24 zdjęć. Pierwsze zaznaczone zdjęcie staje się okładką produktu. Zdjęcia są pobierane do Twojego sklepu i skalowane do wszystkich rozmiarów obrazów sklepu. Upewnij się, że masz prawo z nich korzystać. Gdy wyszukiwarka jest wyłączona, zakładka prosi o włączenie jej w **Settings → General**.

**History.** Zakładka pokazuje **When**, **Type**, **Status** i przycisk **Restore** dla ostatnich 50 wpisów tego produktu. Wiersz wprowadzenia brzmi **Earlier writes for this product. Restore puts the previous text back…** Bez wpisów jest komunikat **No generations for this product yet.** Kliknij **Restore** i potwierdź. Pojawia się komunikat **Content successfully restored. Refresh this page to see changes.** Wiersz bez poprzedniej wartości pokazuje **Error! This log entry has no previous value to restore.** Zakładka pojawia się tylko wtedy, gdy **Product Edit History** jest włączone.

### 3.17 Inne miejsca, w których pojawia się moduł

**Przyciski Generate with AI obok pól.** Mały przycisk z logo pojawia się obok tych pól.

| Miejsce | Pola | Co się dzieje |
|---|---|---|
| Formularz produktu | Description, Short description, Meta title, Meta description | Claude pisze w polu otwartego formularza. |
| Formularz kategorii | Description, Additional description, Meta title, Meta description | Claude pisze w polu otwartego formularza. |

Jeśli sklep ma więcej niż jeden język, przycisk pyta, czy pisać w bieżącym języku, czy we wszystkich. Tekst pojawia się w polu, ale nie jest zapisany. Przypomina o tym notatka **Text is in the field. Save the product to keep it.** (dla kategorii: **Save the category**). Na nowym, niezapisanym elemencie przycisk pokazuje **Save the product once before generating.** (dla kategorii: **Save the category once…**). Każde użycie jest zapisywane w History i sprawia, że produkt uchodzi za już przetworzony.

**Skrót na górnym pasku.** Ikona magii na górnym pasku panelu administracyjnego otwiera małe okno **My AI Claude** z listą **Template**, polem tekstowym, **Generate** i przyciskiem zamknięcia. Działa jak Playground i niczego nie zapisuje. Przełącznik to **Admin Top Bar CTA** w **Settings → General**.

**Lista produktów.** Przycisk **My AI Claude** na pasku narzędzi nad listą produktów otwiera **Generate → Products**.

### 3.18 Zmienne w promptach

Zmienne to słowa w nawiasach klamrowych, które moduł zastępuje prawdziwymi danymi, zanim wyśle prompt. Działają w szablonach, w polu promptu uruchomień masowych, w panelu produktu i w cron.

| Zmienna | Działa dla | Zastępowana przez |
|---|---|---|
| `{product_name}`, `{product_description}`, `{product_description_short}`, `{product_tags}` | Produkty | Bieżąca nazwa, opis, krótki opis i tagi w języku uruchomienia. |
| `{product_reference}`, `{product_ean13}`, `{product_weight}` | Produkty | Numer referencyjny, kod EAN-13 i waga. |
| `{product_brand}`, `{product_default_category}`, `{product_category_description}`, `{product_categories}` | Produkty | Marka, kategoria domyślna wraz z opisem oraz wszystkie kategorie. |
| `{product_attributes}`, `{product_features}`, `{product_feature_values}` | Produkty | Kombinacje, nazwy cech i wartości cech. |
| `{product_images}` | Produkty | Linki do zdjęć produktu. |
| `{category_name}`, `{category_description}`, `{category_parent_name}` | Kategorie | Nazwa, opis i nazwa kategorii nadrzędnej. |
| `{shop_name}`, `{shop_url}`, `{shop_language}`, `{shop_country}`, `{shop_currency}` | Wszędzie | Nazwa sklepu, adres, język, kraj i waluta. |

Zmienna, która nie ma danych, jest zastępowana pustym tekstem.

## 4. Sklep dla klientów

My AI Claude nie dodaje niczego, co Twoi klienci mogą zobaczyć lub z czego mogą korzystać. Nie ma strony we front office, bloku, widżetu ani ustawienia dla klienta. Teksty, które pisze, stają się widoczne tylko dlatego, że są zapisane w Twoich produktach i kategoriach, a widzisz je przez swój zwykły motyw.

Moduł ma dwa adresy należące do domeny sklepu, ale nieprzeznaczone dla klientów.

| Adres | Kto go używa | Co zwraca |
|---|---|---|
| `…/module/myaiclaude/cron?secret=…&action=…` | Harmonogram na Twoim serwerze | Odpowiedź w postaci zwykłego tekstu, na przykład **N products have been updated.**, **N categories have been updated.**, **No products to update.**, **No categories to update.** albo jeden z komunikatów z następnej tabeli. |
| `…/module/myaiclaude/ajax` | Własne ekrany modułu w panelu administracyjnym | Nic użytecznego po ręcznym otwarciu. Odpowiada tylko na żądania zawierające sekret ekranów. |

| Komunikat z adresu cron | Znaczenie | Co zrobić |
|---|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | **Enable Cron Feature** ma wartość **No**. | Ustaw **Yes** i zapisz. |
| The token does not exist or it's wrong! | Sekret w adresie nie pasuje do zapisanego sekretu. | Skopiuj adres ponownie ze strony **Cron**. |
| Invalid action! | Części `&action=` brakuje lub jest błędnie zapisana. | Dodaj `&action=generateProductContent` lub `&action=generateCategoryContent`. |
| All must include all mandatory parameters! | Brakuje wymaganego wyboru, najczęściej szablonu promptu. | Wybierz szablon w formularzu i kliknij **Save**. |
| updatedField parameter is wrong! | Pole nie jest jednym z dozwolonych pól. | Wybierz pole w formularzu i zapisz. |
| productTarget parameter is wrong! Allowed values: pendingClaude, pendingField, emptyField. | Cel w adresie jest błędnie zapisany. | Użyj jednej z trzech wartości. |
| No valid product IDs provided. | **Product ID list** nie zawiera liczb. | Popraw listę lub ją opróżnij. |
| Error!… | Claude lub sklep zwrócił błąd. Tekst po słowie Error go wyjaśnia. | Przeczytaj tekst, zobacz rozdział 5. |

Haki modułu we front office są puste, więc moduł nie dodaje żadnych danych wyjściowych do stron sklepu.

## 5. Rozwiązywanie problemów

### 5.1 Menu i ekrany

| Objaw | Przyczyna | Co kliknąć |
|---|---|---|
| **AI Content Generator** nie ma w menu. | Pamięć podręczna nie została wyczyszczona, moduł jest wyłączony albo pracownik nie ma dostępu. | **Advanced Parameters → Performance → Clear cache**. Sprawdź **Modules → Module Manager**. Sprawdź **Advanced Parameters → Team → Permissions**. |
| Każdy adres modułu wraca na główny dashboard. | Moduł jest wyłączony. | Włącz go w **Module Manager**. |
| Panel **Modules → My AI Claude** na stronie produktu jest pusty. | **Product edit page Form** i **Product Edit History** są oba wyłączone. | Włącz co najmniej jedno w **Settings → General**. |
| Panel produktu nie działa na nowym produkcie. | Produkt nie jest jeszcze zapisany. | Zapisz produkt raz, potem użyj panelu. |
| Brakuje zakładki **History** w panelu produktu. | **Product Edit History** jest wyłączone. | Włącz w **Settings → General**. |
| Blok My AI Claude na głównym dashboardzie PrestaShop pokazuje puste lub zerowe wartości. | Blok na stronie głównej nie zawiera danych raportu. | Otwórz **AI Content Generator → Dashboard**, aby zobaczyć prawdziwe dane. |

### 5.2 Połączenie z Claude

| Objaw | Przyczyna | Co kliknąć |
|---|---|---|
| Komunikat mówi, że klucz API Anthropic Claude nie jest ustawiony (**The Anthropic Claude API key is not set. Add it in the module settings.**). | Żaden klucz nie jest zapisany. | **Settings → Claude**, wklej klucz w **Anthropic Claude API KEY**, **Save**. |
| **Anthropic Claude API KEY field is invalid!** | Pole klucza jest puste i żaden klucz nie jest zapisany. | Wklej klucz i zapisz. |
| Komunikat zaczyna się od **Anthropic Claude API Error**, po którym następuje tekst od Anthropic. | Claude odrzucił wywołanie. Typowe przyczyny to zły klucz, model, którego Twoje konto nie może użyć, brak środków lub zbyt wiele zapytań. | Przeczytaj tekst po dwukropku. Sprawdź klucz, środki i model na koncie Anthropic. Wybierz inny **Model**. |
| **Claude request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.** | Claude odpowiedział zbyt wolno. | Zwiększ **API timeout (seconds)** w **Settings → General** (maksymalnie 600) lub zmniejsz **Max Tokens**. Spróbuj później. |
| Komunikat zaczynający się od **cURL Error** | Serwer nie może połączyć się z Claude lub blokuje to zapora. | Poproś hosting o zezwolenie na wychodzące HTTPS do `api.anthropic.com`. |
| Nowego modelu Claude brakuje na liście **Model**. | Lista zawiera tylko nazwy wbudowane i te, które dodałeś. | Wpisz dokładną nazwę w **Add a Claude model** i kliknij **Add model**. |
| Po **Remove** lista **Model** pokazuje model, który nie należy do Claude. | Usunięcie aktywnego dodanego modelu przełącza sklep na nazwę zastępczą, której Claude nie zna. | Wybierz model Claude w **Model** i kliknij **Save**. |
| Moduł pokazuje **OpenAi Settings Updated** lub **OpenAi Model field is invalid!**, kolumna **Provider** w History pokazuje `openai`, pomoc strony mówi o koncie OpenAI, a przykład w **Add a Claude model** wspomina nazwę GPT. | To pozostałości tekstów ze starszej wersji modułu. | Nic. Moduł rozmawia tylko z Claude. Czytaj te teksty jako dotyczące Claude. |
| Przycisk **Module settings** w formularzach filtrów **Generate** otwiera niewłaściwą stronę. | Przycisk wskazuje ustawienia innego modułu (My ChatGPT), a nie My AI Claude. | Otwórz **Settings** w górnym menu modułu. |
| Log PrestaShop zapełnia się wierszami o liście modeli. | **Debug mode** jest włączony. | Wyłącz **Debug mode** w **Settings → General**. |

### 5.3 Problemy z generowaniem

| Objaw | Przyczyna | Co kliknąć |
|---|---|---|
| **Error! Prompt is missing or too short!** | Prompt ma mniej niż 4 znaki. | Napisz dłuższy prompt lub wybierz szablon. |
| **Error! Product not found!** | Produkt już nie istnieje. | Odśwież listę. |
| **The model hit the token limit … Increase "Max Tokens" …** | Odpowiedź zużyła wszystkie tokeny, zanim powstał jakikolwiek tekst. | Zwiększ **Max Tokens** w **Settings → Claude**. |
| **The model returned an empty response.** | Claude nie zwrócił tekstu. | Spróbuj ponownie, przeformułuj prompt lub zwiększ **Max Tokens**. |
| **The response was blocked by the provider content filter…** | Claude odmówił z powodu tematu. | Przeformułuj prompt. |
| Tekst urywa się w środku zdania. | **Max Tokens** jest zbyt niskie. | Zwiększ **Max Tokens**. Użyj 1000 lub więcej dla pełnego opisu. |
| Opis zawiera błędy ortograficzne, niechciane nagłówki, pomysły na H1 lub listy słów kluczowych. | Gotowy szablon o to prosi. | Edytuj szablon w **Settings → Prompt templates** (sekcja 3.6). |
| Tekst jest po angielsku, chociaż sklep jest w innym języku. | Gotowy szablon prosi o angielski albo wybrano zły język. | Edytuj szablon i zaznacz właściwy język w uruchomieniu. |
| **The reply was rejected because it contains a forbidden word from the studio settings.** | **Quality gate** znalazła słowo z **Forbidden words**. | Uruchom ponownie, usuń słowo ze **Studio** lub wyłącz **Quality gate**. |
| **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** | Liczba generacji w tym miesiącu osiągnęła **Monthly generation budget**. | Zwiększ wartość w **Settings → Studio** lub ustaw 0. |
| **Error! The generated content could not be saved to the product.** | PrestaShop odrzucił tekst, na przykład nazwę produktu ze znakami, które nie są dozwolone. | Przeczytaj szczegóły w wierszu i w **History**. Edytuj prompt i uruchom ponownie. |
| **Error! This PrestaShop version does not support the category Additional Description field.** | Twoja wersja PrestaShop nie ma takiego pola. | Wybierz inne pole. |
| Wiersz mówi **Product skipped.** lub **Category skipped.** | Wybrano **Skip if filled**, a pole ma już tekst. | Wybierz **Replace**, aby nadpisać. |
| Po **Fill** wraca stary tekst. | Formularz został zapisany bez odświeżenia strony. | Odświeżaj stronę produktu po każdym **Fill**, a dopiero potem kontynuuj. |
| Uruchomienie masowe się zatrzymało. | Strona została zamknięta lub odświeżona. | Zacznij od nowa, ustawiając **Update only** na opcję dla produktów jeszcze niezaktualizowanych. Nieudane wywołania są tam liczone jako zaktualizowane. |
| Strona kategorii ma drugi formularz z **Generate content**, który nic nie robi. | Ten formularz nie jest podłączony. | Użyj **Run on the categories below**. |
| **Error! This log entry has no previous value to restore.** | Wiersz History nie ma wcześniejszego tekstu. | Edytuj pole ręcznie. |
| Wynik **Try** nie pojawia się w produkcie, ale wiersz History istnieje. | **Try** nigdy nie zapisuje w produkcie. | Naciśnij **Fill**, aby zapisać. |

### 5.4 Zdjęcia i nowe produkty

| Objaw | Przyczyna | Co kliknąć |
|---|---|---|
| Zakładka **Photos** prosi o włączenie wyszukiwarki. | **AI Image Finder** jest wyłączone. | Włącz w **Settings → General** lub na **Images**. |
| **Claude API key is not configured. Please check module settings.** | Żaden klucz nie jest zapisany. | **Settings → Claude**. |
| **The search failed.** | Claude lub sieć nie odpowiedziały. | Kliknij **Find pages** ponownie, sprawdź klucz i limit czasu. |
| **No photos were found on the suggested pages.** | Strony nie miały użytecznych zdjęć. | Zmień nazwę lub opis produktu albo edytuj **AI Image Search Prompt**. |
| **URL not allowed (private network).** | Adres wskazuje sieć prywatną lub lokalną. | Używaj tylko publicznych stron internetowych. |
| **No images selected** | Nic nie zaznaczono. | Zaznacz co najmniej jedno zdjęcie. |
| **No images could be imported. Details: …** | Zdjęć nie udało się pobrać lub nie były prawidłowymi obrazami. | Przeczytaj szczegóły. Spróbuj innych zdjęć. |
| Zdjęcie okładkowe się zmieniło. | Pierwsze zaznaczone zdjęcie staje się okładką. | Zmień kolejność zdjęć na stronie produktu. |
| **Add an API key in the module settings first.** (**New product**) | Żaden klucz nie jest zapisany. | **Settings → Claude**. |
| **Failed to parse AI response. Please try again.** | Claude zwrócił tekst, który nie jest prawidłową wersją roboczą. | Kliknij **Generate data** ponownie. Opisz produkt dokładniej. |
| **Prompt is required**, **Invalid product data**, **Failed to create product** | Opis jest pusty, wersja robocza jest niekompletna albo PrestaShop nie mógł zapisać produktu. | Wypełnij **What is the product?**, wygeneruj ponownie, sprawdź ID kategorii. |

### 5.5 Problemy z cron

| Objaw | Przyczyna | Co kliknąć |
|---|---|---|
| Adres odpowiada **Invalid action!** | Adres cron skopiowany ze strony nie ma części `&action=`. | Dodaj `&action=generateProductContent` (produkty) lub `&action=generateCategoryContent` (kategorie). |
| Adres odpowiada **Cron Job feature is disabled…** | **Enable Cron Feature** jest wyłączone. | Ustaw **Yes** i **Save**. |
| **Generate Token** nic nie robi. | Przycisk nie jest podłączony w tej wersji. | Wpisz sekret z co najmniej 24 liter i cyfr w **Cron Job Secret Token** i **Save**. Krótszy sekret jest zastępowany losowym przy następnym otwarciu strony administratora. |
| Adres odpowiada **All must include all mandatory parameters!** | Formularz nigdy nie został zapisany, więc żaden szablon nie jest zapisany. | Wybierz **Prompt Template**, potem **Save**. |
| Adres odpowiada **No products to update.**, chociaż produkty wymagają tekstu. | **Selected Products** je wyklucza. **pendingClaude** pomija każdy produkt z udaną generacją, łącznie z uruchomieniami **Try**. | Użyj **emptyField** lub **pendingField** albo ustaw **Product ID list**. |
| Tekst produktu został napisany ponownie. | Cron zawsze zastępuje pole. | Użyj **emptyField**, aby dotykać tylko pustych pól. |
| **Error!Monthly generation budget reached.** | Miesięczny budżet został wykorzystany. | Zwiększ go w **Settings → Studio**. |
| **Error! Could not save product N: … (X product(s) updated before this one.)** | PrestaShop odrzucił tekst dla produktu N. | Napraw ten produkt lub go wyklucz, uruchom ponownie. |
| Polecenie na stronie nie zmienia się po zmianie formularza. | Polecenie pokazuje tylko adres podstawowy. | Dodaj `&action=` samodzielnie. Wartości formularza są odczytywane z zapisanych ustawień. |
| Interwał w formularzu nie ma efektu. | To notatka dla Ciebie. | Utwórz harmonogram w panelu hostingu. |

### 5.6 History i dane

| Objaw | Przyczyna | Co kliknąć |
|---|---|---|
| Dashboard i History są puste po **Clear list**. | **Clear list** usuwa wszystkie wiersze. | Nie ma czego przywracać. Zaplanuj eksport przed czyszczeniem. |
| **This log entry no longer exists.** | Wiersz został usunięty. | Wróć do listy. |
| **Update only** nie pokazuje produktów. | Filtr korzysta z wpisów History, a każdy produkt ma już wpis. | Wybierz **Update all**. |
| Niektóre produkty są pomijane w **Update only**. | Nieudane wywołania i uruchomienia **Try** także liczą się jako wpisy. | Wybierz **Update all**. |

## 6. Dla programistów

### 6.1 Przegląd

My AI Claude (`myaiclaude`, wersja 1.1.0, autor MyPresta.eu) to moduł PrestaShop dla zakładki `front_office_features`. Obsługuje PrestaShop od 1.6 do 9.99.99 i PHP 7.0 oraz nowszy. Wywołuje Anthropic Claude Messages API pod adresem `https://api.anthropic.com/v1` (endpoint `/messages`) i zapisuje wyniki w produktach i kategoriach.

- Klasa `myaiclaude` w `myaiclaude.php` zawiera instalację, odinstalowanie, strony konfiguracji i hooki.
- Klasa `MyAIClaude\OpenAIService` (`src/OpenAIService.php`) to klient. Wysyła `model`, `max_tokens`, `messages`, opcjonalne `system` i opcjonalne `temperature`, z nagłówkami `x-api-key` i `anthropic-version: 2023-06-01`. Top P i dwie kary są zapisywane, ale nie wysyłane. Mapuje `input_tokens` i `output_tokens` na tokeny wysłane i odebrane. `listModels()` zawsze odpowiada, że listę modeli zapewnia katalog modułu, więc lista modeli to zestaw wbudowany plus nazwy zachowane w `EXTRA_MODELS`. Limit czasu jest ograniczany do 10–600 sekund. Gdy API odpowiada 400 i wskazuje parametr, klient pomija ten parametr, ponawia próbę i zapamiętuje decyzję dla modelu w `MODEL_CAPS`.
- Klasa `MyAIClaude\Studio` (`src/Studio.php`) opakowuje prompty wierszem języka, głosem, odbiorcami, tonem, glosariuszem i zakazanymi terminami, stosuje miesięczny budżet i bramkę zakazanych słów oraz buduje prompt pakietu SEO.
- Zakładki strony konfiguracji używają parametrów URL `mac_tab` (`dashboard`, `settings`, `updates`) i `mac_sub` (`general`, `openai`, `studio`, `templates`, `playground`). Wartość `openai` parametru `mac_sub` otwiera zakładkę Claude. Dashboard używa `mcg_preset` oraz dat `mac_from` i `mac_to`.
- Klasy CSS panelu administracyjnego mają prefiks `.mac-`.
- Zadania masowe wykonują jedną pozycję na żądanie AJAX z `back.js`.

### 6.2 Pliki

| Ścieżka | Cel | Uwagi |
|---|---|---|
| `myaiclaude.php` | Klasa modułu | Instalacja, odinstalowanie, formularze, hooki, umiejscowienie zakładki. |
| `autoload.php` | Loader dla przestrzeni nazw `MyAIClaude\` | |
| `src/OpenAIService.php`, `src/Studio.php` | Klient API i reguły Studio | |
| `controllers/admin/AdminMyAIClaude*.php` | Kontrolery panelu administracyjnego | Patrz 6.3. |
| `controllers/front/ajax.php`, `controllers/front/cron.php` | Kontrolery front | AJAX i cron. |
| `lib/updateChecker.php` | Sprawdzanie aktualizacji MyPresta | Łączy się z `dev.mypresta.eu/update/get.php`. |
| `lib/sectionHelp.php` | Teksty szuflady **Help** | |
| `lib/prestashop9compatibility.php` | Funkcje pomocnicze zgodności | |
| `lib/searchTool` | Pomocnik autouzupełniania dla formularzy administracyjnych | |
| `views/templates/` | Szablony Smarty | Hooki, strony administracyjne, panele masowe. |
| `views/js/` | `back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `dashboard.js`, `admin-help.js`, `chart.min.js` | |
| `views/css/` | Style z prefiksem `.mac-` | |
| `translations/` | 34 pliki językowe | |
| `upgrade/index.php` | Zastępczy plik | Moduł nie ma skryptów aktualizacji. |

### 6.3 Kontrolery

| Kontroler | Menu lub trasa | Rola |
|---|---|---|
| AdminMyAIClaudeMain | **AI Content Generator** w sekcji **Modules** | Przekierowuje do Dashboard. Rodzic ukrytych zakładek. |
| AdminMyAIClaude | Ukryta zakładka **Mass Content Creator** | Generate: produkty i kategorie. |
| AdminMyAIClaudeProductCreator | Ukryta zakładka **AI Product Creator** | New product. |
| AdminMyAIClaudeSettings | Ukryta zakładka **Module Settings** | Przekierowuje do zakładki Settings. |
| AdminMyAIClaudeCron | Ukryta zakładka **Cron Job Settings** | Dwa formularze cron. |
| AdminMyAIClaudeUsage | Ukryta zakładka **Module Log and Usage** | History. |
| AdminMyAIClaudeImageFinder | Ukryta zakładka **AI Image Finder** | Images. |
| Front `ajax` | `module/myaiclaude/ajax` | Akcje `initiatePrompt`, `updateProduct`, `updateCategory`, `initiateProductRestore`, `updateSettings`, `generateAltTexts`, `generateSeoPack`. Wymaga `secret_token` równego `TOKEN`. Nie jest powiązany z sesją pracownika. Żaden ekran tej wersji nie wywołuje `generateAltTexts`. |
| Front `cron` | `module/myaiclaude/cron` | Wymaga `secret` równego `SECRET` lub `CAT_SECRET` oraz `ENABLE_CRON=1`. Parametry: `action` (`generateProductContent`, `generateCategoryContent`), `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`, `categoryTarget`, `categoriesToUpdate`. Brakujące parametry są odczytywane z zapisanych ustawień. |

Zakładki podrzędne są tworzone z `active=0` pod `AdminMyAIClaudeMain`. W `displayBackOfficeHeader` moduł umieszcza główną zakładkę pod zakładką nadrzędną Modules, zmienia jej nazwę i regeneruje sekrety krótsze niż 24 znaki. Klasa ikony to `icon-openai`. Zakładka Image Finder jest rejestrowana na żądanie i oznaczana przez `IMAGEFINDER_TAB_OK`.

Cron produktów akceptuje cele `pendingClaude`, `pendingField` i `emptyField` i liczy tylko wiersze logu o statusie innym niż `error`. Filtr **Update only** w Generate liczy każdy wiersz logu. Wiersze logu cron używają metody `cron`.

### 6.4 Hooki

| Hook | Zachowanie | Uwagi |
|---|---|---|
| `displayAdminProductsExtra` | Renderuje panel **Modules → My AI Claude** | Zakładki Generate, Simulate, Photos, History. |
| `displayBackOfficeHeader` | Ładuje zasoby, umieszcza menu, regeneruje krótkie sekrety | Działa na każdej stronie administracyjnej. |
| `displayBackOfficeTop` | Renderuje skrót na górnym pasku | |
| `dashboardZoneTwo` | Renderuje `dashboard.tpl` na dashboardzie PrestaShop | Szablon jest renderowany bez zmiennych raportu. |
| `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom` | Zarejestrowane, zwracają pusty ciąg | |
| `actionProductFormBuilderModifier` | Zarejestrowany, nic nie robi | |
| `displayHeader`, `displayFooter` | Zarejestrowane, puste | Sklep nie otrzymuje żadnych danych wyjściowych. |

Moduł nie ma metody `enable()` ani `disable()`. `displayCustomTop` i `top.tpl` istnieją, ale nie są wywoływane.

### 6.5 Nadpisania (overrides)

Moduł nie ma katalogu `override` i nie zmienia żadnego pliku rdzenia. Zdjęcia produktów są zapisywane klasami obrazów PrestaShop, a produkty i kategorie moduł zapisuje obiektami PrestaShop (`Product`, `Category`, `Tag::addTags`).

### 6.6 Baza danych

Tabele (prefiks jak w Twoim sklepie, silnik jak w PrestaShop):

| Tabela | Kolumny | Uwagi |
|---|---|---|
| `myaiclaude_prompt` | `id_prompt` (klucz główny), `status`, `title`, `prompt`, `date_generated` | Zawiera 16 zainstalowanych szablonów i Twoje własne. |
| `myaiclaude_log` | Prompt, odpowiedź, status, typ, model, ID produktu lub kategorii, język, pracownik, liczby tokenów, czas trwania, data | Jeden wiersz na wywołanie. Kolumny tokenów są dodawane na żądanie w starszych instalacjach. |

Zapisy produktów i kategorii dotykają tabel rdzenia edytowanych danych (`product`, `product_lang`, `category_lang`, `tag`, `image` i powiązane tabele). Odinstalowanie usuwa obie tabele modułu.

### 6.7 Klucze i tłumaczenia

Klucze konfiguracji mają prefiks `MYPRESTA_MYAICLAUDE_`.

| Klucz (po prefiksie) | Domyślnie | Znaczenie |
|---|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | 0 | Etykieta i logowanie debugowania. |
| `TIMEOUT` | 120 | Limit czasu API. |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT`, `IMAGEFINDER_ENABLE` | 1 | Przełączniki strony General. |
| `IMAGEFINDER_PROMPT` | Gotowy tekst | Używa `{product_name}` i `{product_description}`. |
| `API_KEY` | Pojedyncza spacja | Klucz Anthropic. |
| `MODEL`, `EXTRA_MODELS`, `MODEL_CAPS` | `claude-sonnet-4-5`, puste, puste | Aktywny model, dodane modele, poznana obsługa parametrów. |
| `TEMPERATURE`, `MAX_TOKENS`, `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 0.7, 3200, 1, 0, 0 | Pola próbkowania. Ostatnie trzy nie są wysyłane. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | Puste | Pola tekstowe Studio. |
| `BUDGET`, `QUALITY` | 0, 1 | Miesięczny budżet i bramka jakości. |
| `TOKEN` | Losowe 32 znaki | Sekret AJAX. |
| `SECRET`, `CAT_SECRET` | Losowe 32 znaki | Sekrety cron produktów i kategorii. |
| `ENABLE_CRON` | 0 | Przełącznik cron. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Notatki o interwale. |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList` | description, pendingClaude, 5, puste, język domyślny, puste, 0, puste | Zapisany formularz cron produktów. |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug`, `categories` | description, pendingClaude, 5, puste, język domyślny, 0, puste | Zapisany formularz cron kategorii. |

Ekrany Generate zapisują też ostatnie wybory filtrów w kluczach takich jak `FIELD`, `LANGUAGE`, `CONTENT`, `DELAY`, `EXISTING`, `HISTORY`, `STATUS`, `STOCK`, `CATEGORIES`, `BRANDS`, `CATEGORIESC` oraz kilku kluczach `PROD_*`. Odinstalowanie ich nie usuwa, podobnie jak `mypresta_updates`, `update_myaiclaude` i `updatev_myaiclaude` ze sprawdzania aktualizacji. Odinstalowanie usuwa pozostałe klucze oraz starsze klucze poprzedniego dostawcy.

Teksty pomocy pól formularzy są budowane przez `fieldHelp()` w trzy części: **What it does**, **How to configure** i **Effect**. Ciągi przechodzą przez system tłumaczeń PrestaShop (domeny tłumaczeń modułu i kontrolera). Język dodasz, umieszczając plik `translations/<iso>.php`. Teksty szuflady Help pochodzą z `lib/sectionHelp.php`. Odpowiedzi cron, prompty Studio i domyślne teksty promptów to zwykłe angielskie ciągi w kodzie.

### 6.8 Rozszerzanie

- Dodawaj modele polem **Add a Claude model** albo dopisując identyfikator do `EXTRA_MODELS`.
- Dodawaj prompty jako szablony albo wysyłaj własny tekst przez akcje `ajax` z sekretem.
- Zmienne są zastępowane w `controllers/front/ajax.php`. Zmienne `{cms_title}`, `{brand_name}`, `{brand_description}` i `{brand_short_description}` są rozpoznawane, gdy żądanie niesie ID strony CMS lub marki. Żaden ekran tej wersji nie wysyła tych ID.
- Zbuduj własny harmonogram z adresem cron i jego parametrami (sekcja 6.3).
- Moduł nie renderuje żadnego szablonu storefront, więc motyw nie ma czego nadpisywać.

## 7. Pomoc

Strona modułu: https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai.html

Aby uzyskać wsparcie:

1. Zaloguj się na mypresta.eu.
2. Przejdź do **contact**.
3. Wybierz **Support for paid modules**.
4. Podaj nazwę modułu (My AI Claude), jego wersję (1.1.0), wersje PrestaShop i PHP oraz co robiłeś, zanim pojawił się problem. Dodaj tekst widocznego komunikatu.
