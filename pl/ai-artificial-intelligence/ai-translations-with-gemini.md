---
title: My AI Claude - AI content generation - dokumentacja i instrukcja obsługi
description: Przewodnik po konfiguracji, codziennej pracy i rozwiązywaniu problemów dla właścicieli sklepów, którzy mają już zainstalowany moduł My AI Claude i chcą połączyć go z kontem Anthropic Claude.
sidebar:
  label: My AI Claude - AI content generation - dokumentacja i instrukcja obsługi
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł AI Translations with Gemini na MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-gemini.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ai-artificial-intelligence/ai-translations-with-gemini/)
>
> ---


## 1. Wymagania

My AI Claude działa w panelu administracyjnym PrestaShop. Wysyła Twoje polecenia (prompty) do Anthropic Claude i zapisuje wyniki w sklepie. Do działania potrzebujesz następujących elementów.

| Element | Wymaganie | Uwagi |
|---|---|---|
| PrestaShop | 1.6, 1.7, 8 i 9 (od 1.6 do 9.99.99) | Działa w klasycznej i w nowej stronie produktu. |
| PHP | 7.0 lub nowszy | Na starszej wersji instalacja zatrzymuje się i pokazuje komunikat z wersją PHP Twojego serwera. |
| Rozszerzenia PHP | cURL, JSON, mbstring, DOM, fileinfo, GD | Standard na większości hostingów. cURL łączy się z Claude, DOM odczytuje stronę źródłową w **New product**, a GD zmienia rozmiar importowanych zdjęć. |
| Ustawienie PHP | Włączone `allow_url_fopen` | Potrzebne tylko w **New product** (odczyt adresu strony źródłowej). |
| Inne moduły | Brak | Nie musisz instalować żadnego innego modułu. |
| Baza danych | Bez dodatkowych wymagań | Moduł korzysta z MySQL lub MariaDB, na której już działa PrestaShop. |
| Konto poza sklepem | Konto Anthropic z dostępem do API i środkami | Klucz utworzysz pod adresem https://console.anthropic.com/settings/keys. Anthropic nalicza opłaty za każdą generację według zużytych tokenów. |
| Sieć | Serwer może otwierać połączenia HTTPS | Sklep łączy się z `api.anthropic.com` przy każdej generacji. Sprawdzanie aktualizacji łączy się z serwerem MyPresta.eu. Funkcja Images otwiera publiczne strony internetowe. |
| Przeglądarka | Włączony JavaScript | Wszystkie przyciski modułu działają w przeglądarce, w panelu administracyjnym. |

**Czas i pamięć.** Jedna generacja to jedno zapytanie do Claude. Trwa od kilku sekund do około minuty. Limit oczekiwania ustawisz w **Settings → General**, w polu **API timeout (seconds)**. Domyślnie wynosi 120 sekund, a możesz wpisać wartość od 10 do 600. Limit czasu PHP na serwerze ustaw wyżej niż tę wartość. Uruchomienie zbiorcze wysyła jedno zapytanie na każdy produkt, pole i język, po kolei. Działa tylko wtedy, gdy strona pozostaje otwarta w przeglądarce. Moduł nie uruchamia procesów w tle i nie potrzebuje więcej pamięci niż zwykła strona panelu.

## 2. Instalacja

### 2.1 Wgranie i instalacja

1. Otwórz **Modules → Module Manager** (w PrestaShop 1.6: **Modules and Services**).
2. Kliknij **Upload a module** (w PrestaShop 1.6: **Add a new module**).
3. Wybierz plik ZIP modułu i poczekaj, aż się wgra.
4. Kliknij **Install**, gdy PrestaShop o to poprosi.
5. Poczekaj na potwierdzenie. Instalacja tworzy pozycję w menu, dwie tabele w bazie danych i gotowe szablony promptów (patrz 3.6).

Instalator nie czyści pamięci podręcznej. Jeśli pozycja menu się nie pojawi, otwórz **Advanced Parameters → Performance**, kliknij **Clear cache** i odśwież stronę.

Po instalacji moduł nic nie robi, dopóki nie wpiszesz klucza Anthropic. Zrób to zgodnie z rozdziałem 3, sekcja 3.1.

### 2.2 Gdzie pojawia się moduł

Moduł dodaje w sekcji **Modules** pozycję menu **AI Content Generator**. Kliknij ją, aby otworzyć moduł na ekranie **Dashboard**. Pozostałe ekrany otwierasz z poziomego menu u góry strony modułu:

**Dashboard**, **Settings** (z podstronami **General**, **Claude**, **Studio**, **Prompt templates** i **Playground**), **Generate**, **New product**, **Cron**, **History**, **Images** i **Updates**.

Moduł pojawia się też w innych miejscach: jako panel **Modules → My AI Claude** na każdej stronie produktu, jako małe przyciski **Generate with AI** przy polach tekstowych w formularzach produktów i kategorii, jako skrót na górnym pasku panelu oraz jako przycisk **My AI Claude** nad listą produktów. Sekcje 3.16 i 3.17 opisują każde z tych miejsc.

Jeśli pracownik, który nie jest superadministratorem, nie widzi pozycji menu, nadaj jego profilowi dostęp do ekranów modułu w **Advanced Parameters → Team → Permissions**.

### 2.3 Wyłączanie i odinstalowanie

- **Wyłączenie** modułu w Module Managerze ukrywa jego ekrany. Dopóki moduł jest wyłączony, każdy jego adres przenosi na główny dashboard PrestaShop. Dane zostają.
- **Odinstalowanie** usuwa pozycje menu, tabelę z szablonami promptów, tabelę z historią generacji i wszystkie ustawienia modułu (klucz API, model, reguły Studio, ustawienia cron i sekrety cron). Historia znika razem z punktami przywracania, a liczby na Dashboard się zerują.
- Odinstalowanie nie usuwa tego, co moduł już zapisał w sklepie: tekstów produktów i kategorii, zaimportowanych zdjęć ani produktów utworzonych przez **New product**.
- Odinstalowanie zostawia też kilka zapamiętanych wyborów z filtrów **Generate** oraz ustawienia sprawdzania aktualizacji MyPresta.
- **Ponowna instalacja** zaczyna od zera. Klucz API jest pusty, sekrety są nowe (adresy cron się zmieniają, więc zaktualizuj harmonogram na serwerze), History jest pusta, a gotowe szablony wracają do pierwotnej treści.

## 3. Konfiguracja i codzienna praca w panelu administracyjnym

### 3.1 Cały proces krok po kroku

1. Utwórz klucz API Anthropic pod adresem https://console.anthropic.com/settings/keys i sprawdź, czy konto ma środki.
2. Otwórz **AI Content Generator → Settings → Claude**. Wklej klucz w polu **Anthropic Claude API KEY**, wybierz **Model** i kliknij **Save**.
3. Otwórz **Settings → Playground**, wpisz krótkie pytanie i kliknij **Generate**. Jeśli na stronie pojawi się odpowiedź, klucz działa.
4. Opcjonalnie otwórz **Settings → Studio** i opisz głos marki, odbiorców, ton, preferowane terminy i słowa zakazane. Te reguły są dodawane do każdej generacji.
5. Otwórz **Settings → Prompt templates** i przeczytaj gotowe szablony. Edytuj te, które chcesz zachować, a pozostałe wyłącz.
6. Otwórz jeden produkt, przejdź do **Modules → My AI Claude** i kliknij **Try** na karcie opisu. Zobaczysz wynik bez zmieniania produktu. Jeśli wynik Ci odpowiada, kliknij **Fill**, aby zapisać go w produkcie.
7. Otwórz **History** i sprawdź wpis. Jeśli chcesz przywrócić stary tekst, kliknij **Restore** w panelu produktu.
8. Przy wielu produktach otwórz **Generate → Products**, ustaw filtr, napisz lub wybierz prompt i kliknij **Run on the list below**. Najpierw sprawdź działanie na małej liście.
9. Do automatycznych uruchomień na serwerze skonfiguruj **Cron** (sekcja 3.12).
10. Kontroluj koszty i liczbę generacji na **Dashboard** i w **History**. Aby ograniczyć zużycie, ustaw **Monthly generation budget** w **Studio**.

### 3.2 Otwieranie modułu i poruszanie się po nim

Kliknij **AI Content Generator** w sekcji **Modules**. Górne menu modułu zawiera: **Dashboard**, **Settings**, **Generate**, **New product**, **Cron**, **History**, **Images** i **Updates**. Niektóre strony mają drugi rząd zakładek. **Settings** ma **General**, **Claude**, **Studio**, **Prompt templates** i **Playground**, a **Generate** ma **Products** i **Categories**.

Nazwy w pogrubieniu to etykiety z angielskiej wersji panelu administracyjnego, a zrzuty ekranu w tej instrukcji pokazują właśnie ten panel. Jeśli Twój panel jest w innym języku, szukaj tych pozycji w tym samym miejscu.

Każda strona modułu ma okrągły przycisk **Help** w prawym dolnym rogu. Otwiera on panel boczny z krótkim opisem strony, na której jesteś.

### 3.3 Dashboard

![My AI Claude dashboard with request and token cards and three charts](https://mypresta.eu/docs/images/docs/myaiclaude-dashboard.webp)

Dashboard pokazuje, jak intensywnie korzystasz z modułu. Pierwszy wiersz informuje o aktywnej usłudze i modelu.

Okres wybierzesz jednym z przycisków **Today**, **7 days**, **30 days**, **90 days**, **This month** lub **All time**. Możesz też wpisać własne daty w polach **From** i **To** i kliknąć **Apply**. Strona otwiera się z okresem **30 days**.

| Element | Znaczenie | Uwagi |
|---|---|---|
| Requests | Liczba wywołań Claude w wybranym okresie | Liczy każdy wiersz z History: uruchomienia zbiorcze, panel produktu, Playground, górny pasek i cron. |
| Success | Wywołania, które zwróciły tekst | |
| Errors | Wywołania zakończone błędem | Przyczyna jest zapisana w wierszu History. |
| Tokens sent | Tokeny w Twoich promptach | Tokeny to jednostka, według której Anthropic nalicza opłaty. |
| Tokens received | Tokeny w odpowiedziach | |
| Requests and errors | Wykres dzienny | Długie okresy są grupowane po tygodniach. |
| Tokens sent and received | Wykres dzienny | |
| Requests by model | Wykres | Pokazuje, które modele wykonały pracę. |

Moduł dodaje też blok na głównym dashboardzie PrestaShop. Pełne dane i wykresy znajdziesz na tej stronie.

### 3.4 Settings – General

![Settings General page with switches and the image search prompt](https://mypresta.eu/docs/images/docs/myaiclaude-settings-general.webp)

Otwórz **Settings → General**, zmień pola i kliknij **Save**. Komunikat **Settings Updated** potwierdza zapis.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Live mode | No | Etykieta informująca, że sklep działa produkcyjnie. Nie włącza ani nie wyłącza żadnej funkcji. |
| Debug mode | No | Zapisuje w logu PrestaShop (**Advanced Parameters → Logs**) techniczne wpisy o nieudanych wywołaniach. Włącz go, gdy pomoc techniczna poprosi o szczegóły, a potem wyłącz. |
| API timeout (seconds) | 120 | Jak długo sklep czeka na odpowiedź Claude, zanim przerwie próbę. Wartości poniżej 10 zmieniają się na 10, powyżej 600 na 600, a puste lub nieprawidłowe na 120. Zwiększ ją przy długich opisach. |
| Product Edit History | Yes | Pokazuje zakładkę **History** w panelu produktu, w której możesz przywrócić wcześniejszy tekst. Po wyłączeniu zakładka znika. Generacje nadal trafiają do głównej History. |
| Admin Top Bar CTA | Yes | Pokazuje ikonę My AI Claude na górnym pasku panelu administracyjnego (sekcja 3.17). |
| Product edit page Form | Yes | Pokazuje panel **Modules → My AI Claude** na stronie produktu. Gdy ten przełącznik i **Product Edit History** są wyłączone, panel jest pusty. |
| AI Image Finder | Yes | Włącza zakładkę **Photos** na stronie produktu. Ten sam przełącznik znajduje się na stronie **Images**. |
| AI Image Search Prompt | Gotowy tekst | Instrukcja używana do wyszukiwania stron ze zdjęciami produktu. To samo pole jest na stronie **Images** (sekcja 3.14). |

### 3.5 Settings – Claude

![Settings Claude page with API key, model and sampling fields](https://mypresta.eu/docs/images/docs/myaiclaude-settings-claude.webp)

Ta strona łączy sklep z Twoim kontem Claude. Przy pierwszym otwarciu moduł może poinformować, że z pola klucza usunięto spacje. To normalne.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Anthropic Claude API KEY | Puste | Sekret, który pozwala sklepowi wywoływać Twoje konto Claude. Wklej klucz z https://console.anthropic.com/settings/keys. Spacje są usuwane przy zapisie. Zostaw pole nietknięte, aby zachować zapisany klucz. Brak klucza powoduje błąd każdego wywołania, a błąd pojawia się w **History**. |
| Model | claude-sonnet-4-5 | Model Claude, który pisze tekst. Wbudowane nazwy to: claude-sonnet-4-5, claude-opus-4-5, claude-haiku-4-5, claude-3-5-sonnet-latest, claude-3-5-haiku-latest i claude-3-opus-latest, a także nazwy, które dodasz sam. Model, z którego Twój klucz nie może korzystać, zwraca błąd zamiast tekstu. |
| Add a Claude model | Puste | Wpisz dokładną nazwę modelu z konta Claude i kliknij **Add model**. Nazwa pojawi się na liście **Model**. Obok każdej dodanej nazwy jest link **Remove**. Wbudowanych nazw nie można usunąć. |
| Max Tokens | 3200 | Górny limit długości odpowiedzi, liczony w tokenach. Dla meta opisu wystarczy około 256, a dla pełnego opisu warto ustawić 1000 lub więcej. Zbyt niska wartość ucina odpowiedź. Puste pole zostaje zastąpione wartością 256. |
| Temperature | 0.7 | Jak różnorodne jest słownictwo, w skali od 0 do 1. Niższa wartość daje bardziej przewidywalny styl, wyższa bardziej kreatywny. Chcąc uzyskać najbardziej stabilny styl, wpisz 0.1, bo samo 0 jest odczytywane jako wartość domyślna 0.7. |
| Top P | 1 | Zapisywane razem z pozostałymi polami, ale My AI Claude nie wysyła go do Claude. Zmiana nie ma efektu. |
| Frequency Penalty Value | 0 | Zapisywane, ale nie wysyłane do Claude. Zmiana nie ma efektu. |
| Presence Penalty Value | 0 | Zapisywane, ale nie wysyłane do Claude. Zmiana nie ma efektu. |

Kliknij **Save** na dole formularza. Potwierdzenie pojawia się, gdy wartości są poprawne. Komunikat **Anthropic Claude API KEY field is invalid!** oznacza, że pole klucza jest puste i żaden klucz nie jest jeszcze zapisany.

Jeśli model odrzuci jedno z ustawień (na przykład temperaturę), moduł usunie to ustawienie, ponowi zapytanie i zapamięta tę decyzję dla danego modelu. Nie musisz nic robić.

Wartości próbkowania (Max Tokens, Temperature) używają uruchomienia zbiorcze, panel produktu, Playground, górny pasek i cron. **Images** korzysta z własnych, stałych wartości.

### 3.6 Settings – Prompt templates

![Prompt templates list with title, prompt, status and actions](https://mypresta.eu/docs/images/docs/myaiclaude-settings-templates.webp)

Szablon to zapisana instrukcja, którą możesz wybrać w uruchomieniu zbiorczym, w panelu produktu, na górnym pasku i w cronie. Instalacja tworzy 16 szablonów, wszystkie włączone.

| Szablon | Cel | Uwagi |
|---|---|---|
| Product name 1, Product name 2 | Krótsze lub lepsze nazwy produktów | Name 2 uwzględnia markę i kategorię domyślną. |
| Product description 1 do 6 | Opisy produktów | Description 1 buduje układ HTML z nagłówkami i prosi o celowe błędy ortograficzne. Usuń to zdanie, zanim użyjesz szablonu. Description 3 prosi też o propozycje H1, słów kluczowych, meta tytułu i meta opisu, które wszystkie trafiają do pola opisu. |
| Product description 7 - using product images | Opis z osadzonymi zdjęciami | Używa linków do zdjęć produktu. |
| Product meta title 1 do 3 | Meta tytuły | Meta title 1 prosi o język angielski i 60 znaków. |
| Product meta description 1 do 3 | Meta opisy | Meta description 1 prosi o język angielski i 160 znaków. Meta description 2 i 3 są identyczne i wspominają o smartwatchu, więc przepisz je pod własne produkty. |
| Product tags | Pięć tagów w jednym wierszu | Prosi o język angielski. |

Kilka szablonów prosi o angielski w samej treści. Jeśli sprzedajesz w innym języku, edytuj te szablony i usuń ten wiersz.

Lista pokazuje **ID**, **Title**, **Prompt**, **Status** (kliknij przełącznik, aby włączyć lub wyłączyć szablon), **Timestamp** oraz akcje w wierszu: edycję lub usunięcie. Zaznacz kilka wierszy i użyj zbiorczej akcji **Delete**. Pytanie **Are you sure you want to delete the selected prompts?** poprosi o potwierdzenie. Najnowsze szablony są na górze, a na stronie widać 50 wierszy.

Aby utworzyć szablon, kliknij przycisk **new** na pasku narzędzi. Aby zmienić istniejący szablon, kliknij akcję edycji w jego wierszu.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Status | Enabled dla nowego szablonu | W selektorach modułu pojawiają się tylko włączone szablony. |
| Prompt title | Puste (wymagane) | Nazwa, którą widzisz w selektorach i na liście. |
| Prompt content | Puste (wymagane) | Instrukcja wysyłana do Claude. Możesz używać zmiennych, takich jak `{product_name}` (sekcja 3.18). Podwójne cudzysłowy są zamieniane na pojedyncze przy zapisie. |

Kliknij **Save Prompt**, aby zapisać szablon. Komunikaty to **Prompt template successfully added!** i **Prompt template successfully updated!**. Usunięty szablon pokazuje **Prompt template removed.**. Aby wyjść z formularza bez zapisu, kliknij **Go Back to Module Settings**.

Szablon mówi Claude, co ma napisać. Moduł dodaje też reguły z **Studio** oraz język uruchomienia (reguły Studio opisuje sekcja 3.8).

### 3.7 Settings – Playground

![Playground with a text box and the Generate button](https://mypresta.eu/docs/images/docs/myaiclaude-settings-playground.webp)

Playground to wolne pole tekstowe, w którym możesz przetestować prompt. Wpisz prompt i kliknij **Generate**. Odpowiedź pojawi się na stronie. Nic nie jest zapisywane w żadnym produkcie ani kategorii.

Wywołanie zapisuje się w History jako generacja ogólna, więc wlicza się do Dashboard i do miesięcznego budżetu. Playground służy do sprawdzenia klucza API, modelu i działania reguł Studio.

### 3.8 Settings – Studio

![Studio page with brand voice, audience, tone, glossary and forbidden words](https://mypresta.eu/docs/images/docs/myaiclaude-settings-studio.webp)

Studio zawiera reguły dodawane do każdej generacji: uruchomień zbiorczych, panelu produktu, kategorii, cronu, Playground i górnego paska. Nawet gdy wszystkie pola Studio są puste, moduł informuje Claude, w jakim języku pisać (w języku danego uruchomienia).

| Pole | Domyślnie | Co robi |
|---|---|---|
| Brand voice | Puste | Opisuje, jak brzmi Twój sklep. Claude stosuje to w każdym tekście. |
| Audience | Puste | Opisuje klienta, do którego piszesz. |
| Tone | Puste | Nastrój tekstu, na przykład ciepły, techniczny lub neutralny. |
| Glossary | Puste | Terminy, które Claude ma zachować dokładnie tak, jak je zapiszesz. Jeden w wierszu. |
| Forbidden words | Puste | Słowa, których Claude nie może używać. Jedno w wierszu. Claude dostaje polecenie, by ich nie używał, a gdy bramka jakości jest włączona, odpowiedź zawierająca któreś z tych słów zostaje odrzucona. |
| Monthly generation budget | 0 | Maksymalna liczba udanych generacji w bieżącym miesiącu kalendarzowym. 0 oznacza brak limitu. Po osiągnięciu limitu nowe wywołania zatrzymują się z komunikatem **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** Nieudane wywołania się nie liczą. |
| Quality gate | Yes | Sprawdza każdą odpowiedź pod kątem zakazanych słów przed zapisem. Odrzucona odpowiedź nie jest zapisywana, a pojawia się komunikat **The reply was rejected because it contains a forbidden word from the studio settings.** |

Kliknij **Save studio**. Komunikat **Studio settings saved.** potwierdza zapis.

Budżet liczy wszystkie udane wiersze z History w danym miesiącu: uruchomienia zbiorcze, panel produktu (łącznie z **Try**), Playground, górny pasek i cron. **New product** się nie wlicza.

### 3.9 Generate – Products

![Generate Products filter form](https://mypresta.eu/docs/images/docs/myaiclaude-generate-products.webp)

Otwórz **Generate → Products**. Strona działa w dwóch krokach. Najpierw filtr wybiera produkty, a potem panel uruchamia Claude na tej liście.

**Krok 1 – filtr.** Wypełnij pola i kliknij **Go to next step**. Formularz zawsze otwiera się z wartościami, które były ustawione ostatnio.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Product Categories | Nic nie zaznaczono | Zaznacz kategorie, aby ograniczyć listę do produktów z nich. Puste pole oznacza wszystkie kategorie. |
| Brand | All | Ogranicza listę do jednej marki. |
| Product status | Active | Active, Disabled lub Both. |
| Product stock | All products | **Only in stock products** zostawia produkty z ilością powyżej zera. |
| Update only | Update all | Trzy opcje: tylko produkty, które nie mają jeszcze wpisu w History, tylko produkty, które już mają wpis, albo wszystkie produkty. Liczy się każdy wpis, także nieudane wywołania i uruchomienia **Try**. |
| Product IDs | Puste | Lista ID produktów. |
| Product Reference | Puste | Ogranicza listę do produktów o tym numerze referencyjnym. |
| Product Add Date From, Product Add Date To | Puste | Ogranicza listę według daty dodania produktu. |
| Minimum product ID, Maximum product ID | Puste | Ogranicza listę do zakresu ID. |
| Product Limit | Puste | Maksymalna liczba produktów na liście. |

**Krok 2 – panel Mass product generation.** Pasujące produkty pojawiają się w tabeli z kolumnami **ID**, **Reference** i **Result**. Nad tabelą ustawiasz uruchomienie.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Template | Nic nie wybrano | Wybiera włączony szablon i kopiuje jego treść do pola promptu. Tekst możesz potem edytować. |
| Prompt | Puste | Instrukcja dla Claude, ze zmiennymi, takimi jak `{product_name}`. Gdy pole jest puste, moduł używa wbudowanego zlecenia dla każdego pola: opis HTML ze wstępem i listą cech, krótkie podsumowanie bez formatowania poniżej 400 znaków, meta tytuł o długości około 70 znaków i meta opis o długości około 160 znaków. |
| What to generate | Descriptions | **Descriptions** (opis długi i krótki), **Meta title and meta description** lub **Descriptions and meta together**. |
| Existing text | Replace | **Replace**, **Skip if filled**, **Add above** lub **Add below**. |
| Languages | Zaznaczony bieżący język | Zaznacz każdy język, w którym ma powstać tekst. |

Kliknij **Run on the list below**. Wiersz stanu pokazuje postęp (na przykład `3 / 40` z nazwą pola) i kończy się komunikatem **Finished N products.** Każdy wiersz pokazuje pole, wynik i komunikat, na przykład **Content successfully generated and updated to product.** albo **Product skipped.**

Zasady uruchomienia:

- Uruchomienie wysyła jedno zapytanie na każdy produkt, pole i język, po kolei. Przed startem policz zapytania, bo każde z nich jest płatne.
- Zostaw stronę otwartą. Zamknięcie lub odświeżenie strony zatrzymuje uruchomienie. Produkty, które zostały już zapisane, pozostają zapisane.
- Błąd w jednym wierszu nie zatrzymuje pozostałych. Przyczyna jest w wierszu i w **History**.
- Limity przy zapisie: nazwa produktu 128 znaków, krótki opis 800, meta tytuł 69, meta opis 159. Dłuższy tekst zostaje obcięty.
- Tekst zapisuje się bezpośrednio w produkcie. Jeśli chcesz przywrócić wcześniejszy tekst, użyj panelu produktu (sekcja 3.16).

### 3.10 Generate – Categories

![Generate Categories filter form](https://mypresta.eu/docs/images/docs/myaiclaude-generate-categories.webp)

Otwórz **Generate → Categories**. Pierwszy formularz zawiera pola **Categories** (drzewo kategorii, puste oznacza wszystkie) i **Category status** (Active, Disabled lub Both; domyślnie Active). Kliknij **Go to next step**. Lista może zawierać kategorie Root i Home, więc zaznacz tylko te, które chcesz.

Pod filtrem pojawia się panel **Run on the categories below** z tabelą, w której są kolumny **ID** i **Result**.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Prompt | Puste | Instrukcja dla Claude. Użyj zmiennych kategorii, takich jak `{category_name}`, `{category_description}` i `{category_parent_name}`. Zmienne produktu tutaj nie są wypełniane. |
| Field | Description | **Description**, **Name**, **Meta title**, **Meta description** lub **Additional description**. |
| Existing text | Replace | **Replace** lub **Skip if filled**. |
| Language | Bieżący język | Jeden język na jedno uruchomienie. |

Kliknij **Run on the categories below**. Każdy wiersz pokazuje wynik, na przykład **Content successfully generated and updated to category.** albo **Category skipped.**

Pod panelem strona pokazuje drugi formularz o nazwie **Generate category content**. Jego przycisk nie uruchamia generacji. Używaj **Run on the categories below** i zignoruj drugi formularz. Przycisk **Go Back to Category Filter** wraca do filtra.

Limity przy zapisie są takie same jak dla produktów: nazwa 128 znaków, meta tytuł 69, meta opis 159. Pole **Additional description** istnieje tylko w tych wersjach PrestaShop, które je mają. W pozostałych wiersz pokaże błąd.

### 3.11 New product

![New product page with the product brief and the generated draft](https://mypresta.eu/docs/images/docs/myaiclaude-new-product.webp)

**New product** tworzy kompletny produkt na podstawie krótkiego opisu. Claude pisze wersję roboczą, Ty ją czytasz, a dopiero potem moduł tworzy produkt w katalogu.

| Pole | Domyślnie | Co robi |
|---|---|---|
| What is the product? | Puste | Opisz produkt w kilku zdaniach: czym jest, dla kogo jest i jakie ma główne cechy. To jedyne wymagane pole. Tekst zostaje obcięty po 8000 znakach. |
| Optional source URL | Puste | Adres strony z opisem produktu. Moduł odczytuje jej tytuł, meta opis i cenę, a następnie przekazuje je Claude. |
| Language | Domyślny język sklepu | Język wersji roboczej. |
| Default category ID | 2 | ID kategorii, w której produkt zostanie umieszczony. 2 to kategoria Home w standardowym sklepie. |

1. Wypełnij pola i kliknij **Generate data**. Wersja robocza pojawi się na stronie jako blok danych: nazwa, opisy, pola meta, tagi, cechy i cena. Nic jeszcze nie zostaje zapisane.
2. Przeczytaj wersję roboczą. Jeśli jest nietrafiona, zmień opis i ponownie kliknij **Generate data**.
3. Kliknij **Create product** dopiero wtedy, gdy akceptujesz wersję roboczą. Strona pokaże **Product #** i numer nowego produktu. Produkt znajdziesz w **Catalog → Products**.

Nowy produkt powstaje z następującymi ustawieniami: aktywny, dostępny do zamówienia, cena widoczna, widoczny w katalogu i wyszukiwarce, stan nowy, pierwsza reguła podatkowa sklepu, stan magazynowy 100 sztuk oraz cena z wersji roboczej (0, jeśli wersja robocza jej nie zawiera). Claude wypełnia też nazwę, opisy, pola meta, tagi, cechy i numer referencyjny (maksymalnie 32 znaki). Potem otwórz produkt, sprawdź cenę, podatek, stan magazynowy i zdjęcia. Zdjęcia dodasz w zakładce **Photos** w panelu produktu.

Jeśli klucz nie jest zapisany, strona pokaże **Add an API key in the module settings first.** Ta strona nie stosuje reguł Studio ani miesięcznego budżetu, a jej wywołania nie pojawiają się w **History** ani na **Dashboard**.

### 3.12 Cron

![Cron page with enable switch, secret and product cron form](https://mypresta.eu/docs/images/docs/myaiclaude-cron.webp)

Cron pozwala serwerowi generować teksty według harmonogramu, bez klikania. Strona buduje adres, który serwer ma otwierać. Sama strona nie uruchamia harmonogramu. Zaplanowane zadanie tworzysz u swojego hostingu lub na serwerze. Każde wywołanie przetwarza jedną partię i kończy działanie.

Strona ma dwa formularze: cron produktów i cron kategorii. Formularz produktów opisujemy poniżej. Formularz kategorii działa tak samo, ma jednak własny sekret i własne ustawienia.

Pod opisem każdego formularza strona pokazuje adres crona. Adres produktów wygląda tak: `https://your-shop/module/myaiclaude/cron?secret=...`. Adres kategorii kończy się na `&entity=category`.

**Uzupełnij adres, zanim go użyjesz.** Dodaj `&action=generateProductContent` na końcu adresu produktów albo `&action=generateCategoryContent` na końcu adresu kategorii. Bez tego adres odpowie **Invalid action!** i nic nie zrobi.

Przykład dla produktów:

`https://your-shop/module/myaiclaude/cron?secret=YOUR_SECRET&action=generateProductContent`

Adres korzysta z wyborów zapisanych w formularzu: pola, celu, liczby produktów, języka i szablonu. Wartości te możesz nadpisać w adresie (parametry wymienia sekcja 6.3).

**Formularz crona produktów**

| Pole | Domyślnie | Co robi |
|---|---|---|
| Enable Cron Feature | No | Główny przełącznik obu adresów cron (produktów i kategorii). Gdy jest wyłączony, adres odpowiada **Cron Job feature is disabled. You can enable it from the module settings.** |
| Cron Job Secret Token | Losowy tekst | Długie hasło w adresie. Bez właściwego sekretu adres odpowiada **The token does not exist or it's wrong!** Przycisk **Generate Token** w tej wersji nie działa (sekcja 5.5). Wpisz własny sekret złożony z co najmniej 24 liter i cyfr, zapisz i skopiuj nowy adres do harmonogramu. |
| Update Field | description | Jedno pole, które zapisuje ten adres: name, description, description_short, meta_title, meta_description lub tags. Dla kilku pól utwórz kilka zadań. |
| Selected Products | pendingClaude | **pendingClaude** wybiera produkty, które nie mają jeszcze udanej generacji My AI Claude (dla dowolnego pola). **pendingField** wybiera produkty bez udanej generacji dla tego konkretnego pola, dzięki czemu możesz uruchomić jedno zadanie dla opisu i drugie dla nazwy na tych samych produktach. **emptyField** wybiera produkty, w których wybrane pole jest puste. |
| Product Categories | Nic nie zaznaczono | Ogranicza uruchomienie do produktów w zaznaczonych kategoriach. |
| Product ID list | Puste | Tylko te ID produktów, oddzielone przecinkami. Litery są usuwane przy zapisie. |
| Language | Domyślny język sklepu | Wersja językowa, która zostanie zapisana. Inne języki wymagają osobnego zadania. |
| Product to update | 5 | Ile produktów przetwarza jedno wywołanie. Zacznij od 5 lub 10, aby wolna odpowiedź nie przekroczyła limitu czasu serwera. Następne wywołanie kontynuuje na produktach, które nadal pasują. |
| Prompt Template | Nic nie zapisano | Zapisana instrukcja używana dla każdego produktu w uruchomieniu. Wybierz ją i kliknij **Save**. Bez zapisanego szablonu adres odpowiada **All must include all mandatory parameters!** |
| Enable Debug | No | Po otwarciu adresu w przeglądarce pokazuje plan, zapytanie do bazy i końcowy prompt, niczego przy tym nie zapisując. Wyłącz to, zanim harmonogram zacznie używać adresu. |
| CRON JOB interval | Every Hour | Notatka dla Ciebie o rytmie harmonogramu (od co minutę do co 6 godzin). Niczego nie planuje i nie zmienia adresu. |
| Product Cron Job command | Adres | Adres crona. Dodaj część `&action=` zgodnie z opisem powyżej. |

Kliknij **Save** pod formularzem. Formularz kategorii ma pola **Enable Debug**, **CRON JOB interval**, **Language**, **Prompt Template**, **Selected categories**, **Update Field** (name, description, meta_title, meta_description), **Categories to update** oraz sekret, a także własny przycisk **Save**.

Co robi każde wywołanie:

- Zastępuje wybrane pole. Cron nie ma opcji zachowania ani dopisania tekstu.
- Stosuje reguły Studio i miesięczny budżet. Gdy budżet się wyczerpie, wywołanie odpowiada **Error!Monthly generation budget reached.**
- Zapisuje wiersz w History dla każdego tekstu, dzięki czemu możesz go przywrócić lub przejrzeć.
- Oba sekrety otwierają obie akcje. Cron pozostaje wyłączony, dopóki **Enable Cron Feature** nie ma wartości **Yes**.

Przetestuj z ustawieniem **Enable Debug** na **Yes** i adresem otwartym w przeglądarce. Gdy plan wygląda dobrze, ustaw **No**, zapisz i utwórz zadanie.

### 3.13 History

![History page with filters, cards, breakdown panels and the prompt list](https://mypresta.eu/docs/images/docs/myaiclaude-history.webp)

History to dziennik wszystkiego, co zostało wysłane do Claude. Strona otwiera się z okresem **This month**.

**Filtry.** Szybkie przyciski: **Today**, **7 days**, **30 days**, **This month**, **All time**. Pola: **From**, **To**, **Model**, **Type**, **Status**, **Language**, **Employee**, **Product / category ID** oraz **Prompt or reply contains**. Kliknij **Filter**.

**Karty.** **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total** i **Average time**.

**Panele zestawień.** **By day**, **By model**, **By type**, **By language**, **By employee**. Każdy pokazuje wywołania, tokeny wysłane, tokeny odebrane i sumę. Wiersze bez pracownika (wszystkie wywołania cron) pojawiają się jako Unknown.

**Lista historii promptów.**

| Kolumna | Znaczenie | Uwagi |
|---|---|---|
| ID | Numer wiersza | |
| Status | Znacznik **Success** lub **Error** | |
| Prompt | Wysłany tekst | Na liście obcięty do 180 znaków. |
| Reply / Error | Odpowiedź lub komunikat błędu | Na liście obcięte do 180 znaków. |
| Provider | Usługa, model, kod statusu błędu (jeśli Claude go zwrócił) oraz czas w sekundach | |
| Sent, Received, Total | Tokeny | |
| Entity ID | Produkt lub kategoria | Puste dla wywołań z Playground i górnego paska. |
| Type | Co zostało wygenerowane | Patrz następna tabela. |
| Timestamp | Data i godzina | |

Kliknij akcję podglądu w wierszu, aby zobaczyć pełny prompt i odpowiedź oraz link **Back to the list**. Lista pokazuje 50 wierszy na stronę.

| Type | Znaczenie | Uwagi |
|---|---|---|
| general | Playground i górny pasek | Bez produktu i kategorii. |
| product_name, product_description, product_description_short, product_meta_title, product_meta_description, product_tags | Jedno pole produktu | Zapisywane przez uruchomienia zbiorcze, panel produktu, przyciski z logo i cron. |
| product_seo_pack | Pakiet SEO z panelu produktu | Nazwa, opisy i pola meta w jednym zapytaniu. |
| category_name, category_description, category_meta_title, category_meta_description, category_additional_description | Jedno pole kategorii | |
| error | Nieudane wywołanie | Przyczyna jest w **Reply / Error**. |

**Clear list** na pasku narzędzi usuwa **wszystkie** wiersze po potwierdzeniu i pokazuje **Log list successfully deleted.** Tej operacji nie można cofnąć. Usuwa też punkty przywracania wszystkich produktów, zeruje Dashboard i licznik miesięcznego budżetu oraz zmienia to, które produkty uchodzą za już przetworzone w filtrze **Update only** i w celach cron. Zanim wyczyścisz listę, wyeksportuj dane lub zanotuj to, czego potrzebujesz.

Gdy w wybranym okresie nie ma wierszy, strona pokazuje **No generations in this range.**

### 3.14 Images

![Images page with the image finder switch and search prompt](https://mypresta.eu/docs/images/docs/myaiclaude-images.webp)

Ta strona steruje zakładką **Photos** na stronie produktu. Formularz nazywa się **AI Image Finder**.

| Pole | Domyślnie | Co robi |
|---|---|---|
| AI Image Finder | Yes | Włącza zakładkę **Photos** na stronie produktu. Gdy jest wyłączone, zakładka informuje, że trzeba je włączyć w **Settings → General**. |
| AI Image Search Prompt | Gotowy tekst | Instrukcja wysyłana do Claude, aby znalazł strony internetowe pokazujące produkt. Użyj `{product_name}` i `{product_description}` jako zmiennych. Zachowaj prośbę o dokładnie pięć adresów stron, zwróconych jako lista, ponieważ moduł czyta właśnie tę listę. |

Gotowy prompt prosi o dokładnie pięć adresów stron, które pokazują produkt, zwróconych jako lista JSON. Wykorzystuje nazwę i opis produktu.

Kliknij **Save**. Komunikat **Settings saved.** potwierdza zapis. Ta strona i zakładka w **Settings → General** współdzielą ten sam przełącznik i ten sam prompt.

### 3.15 Updates

![Updates page with manual check and automatic notifications](https://mypresta.eu/docs/images/docs/myaiclaude-updates.webp)

Strona **Updates** sprawdza, czy istnieje nowsza wersja My AI Claude. Sprawdzenie wysyła na serwer MyPresta.eu nazwę modułu, jego wersję i adres sklepu.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Manual Check | Przycisk **Check Now** | Uruchamia sprawdzenie od razu. Odpowiedź to **Module is up to date!** albo **New version available!** |
| Automatic Notifications | Enabled | Gdy jest włączone, moduł sprawdza mniej więcej co trzy dni i pokazuje w panelu administracyjnym informację, gdy dostępna jest nowa wersja. |
| Product Page | Link | Otwiera stronę modułu na MyPresta.eu. |

Kliknij **Save**. Komunikat **Update settings saved.** potwierdza zapis.

### 3.16 Strona produktu – Modules → My AI Claude

![Product page with the My AI Claude panel and field cards](https://mypresta.eu/docs/images/docs/myaiclaude-product-edit.webp)

Otwórz dowolny produkt, przejdź do zakładki **Modules** i znajdź **My AI Claude**. Panel ma zakładki **Generate**, **Simulate**, **Photos** i **History**. Zapisz nowy produkt przed użyciem panelu, bo panel działa na zapisanym produkcie.

**Generate i Simulate.**

1. Wybierz znacznik języka lub **Every language**. Domyślnie zaznaczony jest pierwszy język sklepu.
2. W polu **If the field already has text** wybierz **Replace**, **Add above**, **Add below** lub **Skip if filled**. Domyślnie zaznaczone jest **Replace**.
3. Kliknij **Fill** na karcie: **Description**, **Short description**, **Name**, **Meta title**, **Meta description** lub **Tags**. Tekst zostaje zapisany bezpośrednio w produkcie.
4. Karta **SEO pack** ma przycisk **Fill all**. Jedno zapytanie zwraca nazwę, oba opisy i oba pola meta. Nadpisuje ono te pola, łącznie z nazwą. Komunikat **SEO pack saved. Refresh the product to see it.** potwierdza zapis. Jeśli Claude nie zwróci użytecznego pakietu, panel pokaże **The model did not return a usable SEO pack.**
5. Otwórz **Use your own instruction or a saved prompt**, aby przefiltrować i wybrać **Standard brief** albo włączony szablon. Możesz też wpisać własną instrukcję w polu **Instruction**. Gdy pole jest puste, używane jest standardowe zlecenie dla danej karty.
6. Odpowiedź i liczba tokenów pojawiają się pod kartami.

W zakładce **Simulate** te same karty mają przycisk **Try**. **Try** pokazuje odpowiedź, ale nie zmienia produktu. Mimo to wywołanie zapisuje się w History i wlicza do budżetu, a produkt uchodzi przez to za już przetworzony w filtrze **Update only** i w cronie.

**Po Fill odśwież stronę produktu.** Otwarty formularz nadal zawiera stary tekst. Jeśli klikniesz **Save** w PrestaShop bez odświeżenia, PrestaShop nadpisze nowy tekst starym.

**Photos.**

![Photos tab with found photos ready to be added](https://mypresta.eu/docs/images/docs/myaiclaude-product-photos.webp)

1. Otwórz zakładkę **Photos** i kliknij **Find pages**. Pojawią się komunikaty **Looking for photos…** i **Reading photos…**.
2. Zaznacz zdjęcia, które chcesz dodać. Strona pokazuje komunikat **Tick the photos you want, then add them to this product.**
3. Kliknij **Add selected to this product**. Pojawi się komunikat **Adding the photos to this product…**, a po chwili liczba zaimportowanych obrazów.
4. Odśwież stronę produktu, aby zobaczyć zdjęcia.

Wyszukiwarka przegląda do 5 stron i proponuje do 24 zdjęć. Pierwsze zaznaczone zdjęcie staje się okładką produktu. Zdjęcia są pobierane do sklepu i skalowane do wszystkich rozmiarów obrazów w sklepie. Upewnij się, że masz prawo z nich korzystać. Gdy wyszukiwarka jest wyłączona, zakładka prosi o włączenie jej w **Settings → General**.

**History.** Zakładka pokazuje kolumny **When**, **Type** i **Status** oraz przycisk **Restore** dla ostatnich 50 wpisów tego produktu. Wiersz wprowadzenia brzmi: **Earlier writes for this product. Restore puts the previous text back…** Jeśli wpisów nie ma, pojawia się komunikat **No generations for this product yet.** Aby przywrócić tekst, kliknij **Restore** i potwierdź. Pojawi się komunikat **Content successfully restored. Refresh this page to see changes.** Wiersz bez poprzedniej wartości pokazuje **Error! This log entry has no previous value to restore.** Zakładka pojawia się tylko wtedy, gdy **Product Edit History** jest włączone.

### 3.17 Inne miejsca, w których pojawia się moduł

**Przyciski Generate with AI przy polach.** Mały przycisk z logo pojawia się obok tych pól:

| Miejsce | Pola | Co się dzieje |
|---|---|---|
| Formularz produktu | Description, Short description, Meta title, Meta description | Claude wpisuje tekst do otwartego formularza. |
| Formularz kategorii | Description, Additional description, Meta title, Meta description | Claude wpisuje tekst do otwartego formularza. |

Jeśli sklep ma więcej niż jeden język, przycisk pyta, czy pisać w bieżącym języku, czy we wszystkich. Tekst pojawia się w polu, ale nie zostaje zapisany. Przypomina o tym notatka **Text is in the field. Save the product to keep it.** (dla kategorii: **Save the category**). Przy nowym, niezapisanym elemencie przycisk pokazuje **Save the product once before generating.** (dla kategorii: **Save the category once…**). Każde użycie zapisuje się w History i sprawia, że produkt uchodzi za już przetworzony.

**Skrót na górnym pasku.** Ikona magii na górnym pasku panelu otwiera małe okno **My AI Claude** z listą **Template**, polem tekstowym, przyciskiem **Generate** i przyciskiem zamknięcia. Działa jak Playground i niczego nie zapisuje. Przełącznikiem steruje **Admin Top Bar CTA** w **Settings → General**.

**Lista produktów.** Przycisk **My AI Claude** na pasku narzędzi nad listą produktów otwiera **Generate → Products**.

### 3.18 Zmienne w promptach

Zmienne to słowa w nawiasach klamrowych, które moduł zamienia na prawdziwe dane, zanim wyśle prompt. Działają w szablonach, w polu promptu uruchomień zbiorczych, w panelu produktu i w cronie.

| Zmienna | Działa dla | Zastępowana przez |
|---|---|---|
| `{product_name}`, `{product_description}`, `{product_description_short}`, `{product_tags}` | Produkty | Bieżąca nazwa, opis, krótki opis i tagi w języku uruchomienia. |
| `{product_reference}`, `{product_ean13}`, `{product_weight}` | Produkty | Numer referencyjny, kod EAN-13 i wagę. |
| `{product_brand}`, `{product_default_category}`, `{product_category_description}`, `{product_categories}` | Produkty | Markę, kategorię domyślną wraz z jej opisem oraz wszystkie kategorie. |
| `{product_attributes}`, `{product_features}`, `{product_feature_values}` | Produkty | Kombinacje, nazwy cech i wartości cech. |
| `{product_images}` | Produkty | Linki do zdjęć produktu. |
| `{category_name}`, `{category_description}`, `{category_parent_name}` | Kategorie | Nazwę, opis i nazwę kategorii nadrzędnej. |
| `{shop_name}`, `{shop_url}`, `{shop_language}`, `{shop_country}`, `{shop_currency}` | Wszędzie | Nazwę sklepu, adres, język, kraj i walutę. |

Zmienna, dla której brak danych, zostaje zastąpiona pustym tekstem.

## 4. Sklep dla klientów

My AI Claude nie dodaje niczego, co Twoi klienci mogą zobaczyć lub z czego mogą korzystać. Nie ma strony w front office, bloku, widżetu ani ustawienia dla klienta. Teksty, które moduł pisze, stają się widoczne dopiero wtedy, gdy zostaną zapisane w Twoich produktach i kategoriach. Widzisz je przez swój zwykły motyw.

Moduł ma dwa adresy należące do domeny sklepu, ale przeznaczone nie dla klientów.

| Adres | Kto go używa | Co zwraca |
|---|---|---|
| `…/module/myaiclaude/cron?secret=…&action=…` | Harmonogram na Twoim serwerze | Odpowiedź w postaci zwykłego tekstu, na przykład **N products have been updated.**, **N categories have been updated.**, **No products to update.**, **No categories to update.** albo jeden z komunikatów z poniższej tabeli. |
| `…/module/myaiclaude/ajax` | Własne ekrany modułu w panelu administracyjnym | Nic użytecznego po ręcznym otwarciu. Odpowiada tylko na żądania zawierające sekret ekranów. |

| Komunikat z adresu cron | Znaczenie | Co zrobić |
|---|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | **Enable Cron Feature** ma wartość **No**. | Ustaw **Yes** i zapisz. |
| The token does not exist or it's wrong! | Sekret w adresie nie pasuje do zapisanego sekretu. | Skopiuj adres ponownie ze strony **Cron**. |
| Invalid action! | Brakuje części `&action=` albo jest ona błędnie zapisana. | Dodaj `&action=generateProductContent` lub `&action=generateCategoryContent`. |
| All must include all mandatory parameters! | Brakuje wymaganego wyboru, najczęściej szablonu promptu. | Wybierz szablon w formularzu i kliknij **Save**. |
| updatedField parameter is wrong! | Pole nie jest jednym z dozwolonych pól. | Wybierz pole w formularzu i zapisz. |
| productTarget parameter is wrong! Allowed values: pendingClaude, pendingField, emptyField. | Cel w adresie jest błędnie zapisany. | Użyj jednej z trzech dozwolonych wartości. |
| No valid product IDs provided. | Pole **Product ID list** nie zawiera liczb. | Popraw listę albo ją opróżnij. |
| Error!… | Claude lub sklep zwrócił błąd. Tekst po słowie Error go wyjaśnia. | Przeczytaj go i zajrzyj do rozdziału 5. |

Haki modułu w front office są puste, więc moduł nie dodaje żadnych danych wyjściowych na strony sklepu.

## 5. Rozwiązywanie problemów

### 5.1 Menu i ekrany

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| **AI Content Generator** nie ma w menu. | Pamięć podręczna nie została wyczyszczona, moduł jest wyłączony albo pracownik nie ma dostępu. | Kliknij **Advanced Parameters → Performance → Clear cache**. Sprawdź **Modules → Module Manager**. Sprawdź **Advanced Parameters → Team → Permissions**. |
| Każdy adres modułu przenosi na główny dashboard. | Moduł jest wyłączony. | Włącz go w **Module Manager**. |
| Panel **Modules → My AI Claude** na stronie produktu jest pusty. | Przełączniki **Product edit page Form** i **Product Edit History** są oba wyłączone. | Włącz co najmniej jeden z nich w **Settings → General**. |
| Panel produktu nie działa na nowym produkcie. | Produkt nie jest jeszcze zapisany. | Zapisz produkt, a potem użyj panelu. |
| Brakuje zakładki **History** w panelu produktu. | **Product Edit History** jest wyłączone. | Włącz je w **Settings → General**. |
| Blok My AI Claude na głównym dashboardzie PrestaShop pokazuje puste lub zerowe wartości. | Blok na stronie głównej nie zawiera danych raportu. | Otwórz **AI Content Generator → Dashboard**, aby zobaczyć prawdziwe dane. |

### 5.2 Połączenie z Claude

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| Komunikat mówi, że klucz API Anthropic Claude nie jest ustawiony (**The Anthropic Claude API key is not set. Add it in the module settings.**). | Nie zapisano żadnego klucza. | Otwórz **Settings → Claude**, wklej klucz w polu **Anthropic Claude API KEY** i kliknij **Save**. |
| **Anthropic Claude API KEY field is invalid!** | Pole klucza jest puste i nie ma zapisanego klucza. | Wklej klucz i zapisz. |
| Komunikat zaczyna się od **Anthropic Claude API Error**, a po nim następuje tekst od Anthropic. | Claude odrzucił wywołanie. Typowe przyczyny to zły klucz, model, z którego Twoje konto nie może korzystać, brak środków lub zbyt wiele zapytań. | Przeczytaj tekst po dwukropku. Sprawdź klucz, środki i model na koncie Anthropic. Wybierz inny **Model**. |
| **Claude request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.** | Claude odpowiadał zbyt wolno. | Zwiększ **API timeout (seconds)** w **Settings → General** (maksymalnie do 600) lub zmniejsz **Max Tokens**. Spróbuj ponownie później. |
| Komunikat zaczynający się od **cURL Error** | Serwer nie może połączyć się z Claude albo blokuje to zapora. | Poproś hosting o zezwolenie na wychodzące połączenia HTTPS do `api.anthropic.com`. |
| Nowego modelu Claude nie ma na liście **Model**. | Lista zawiera tylko nazwy wbudowane i te, które sam dodałeś. | Wpisz dokładną nazwę w **Add a Claude model** i kliknij **Add model**. |
| Po **Remove** na liście **Model** widać model, który nie należy do Claude. | Usunięcie aktywnego dodanego modelu przełącza sklep na zastępczą nazwę, której Claude nie zna. | Wybierz model Claude w polu **Model** i kliknij **Save**. |
| Moduł pokazuje **OpenAi Settings Updated** lub **OpenAi Model field is invalid!**, kolumna **Provider** w History pokazuje `openai`, pomoc strony mówi o koncie OpenAI, a przykład w **Add a Claude model** wspomina nazwę GPT. | To pozostałości tekstów ze starszej wersji modułu. | Nic nie rób. Moduł komunikuje się wyłącznie z Claude. Traktuj te teksty jako odnoszące się do Claude. |
| Przycisk **Module settings** w formularzach filtrów **Generate** otwiera niewłaściwą stronę. | Przycisk wskazuje ustawienia innego modułu (My ChatGPT), a nie My AI Claude. | Otwórz **Settings** w górnym menu modułu. |
| Log PrestaShop zapełnia się wierszami z listą modeli. | Włączony jest **Debug mode**. | Wyłącz **Debug mode** w **Settings → General**. |

### 5.3 Problemy z generowaniem

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| **Error! Prompt is missing or too short!** | Prompt ma mniej niż 4 znaki. | Napisz dłuższy prompt albo wybierz szablon. |
| **Error! Product not found!** | Produkt już nie istnieje. | Odśwież listę. |
| **The model hit the token limit … Increase "Max Tokens" …** | Odpowiedź zużyła wszystkie tokeny, zanim powstał jakikolwiek tekst. | Zwiększ **Max Tokens** w **Settings → Claude**. |
| **The model returned an empty response.** | Claude nie zwrócił tekstu. | Spróbuj ponownie, sformułuj prompt inaczej albo zwiększ **Max Tokens**. |
| **The response was blocked by the provider content filter…** | Claude odmówił ze względu na temat. | Przeformułuj prompt. |
| Tekst urywa się w środku zdania. | **Max Tokens** jest zbyt niskie. | Zwiększ **Max Tokens**. Dla pełnego opisu użyj wartości 1000 lub wyższej. |
| Opis zawiera błędy ortograficzne, niechciane nagłówki, propozycje H1 albo listy słów kluczowych. | Gotowy szablon o to prosi. | Edytuj szablon w **Settings → Prompt templates** (sekcja 3.6). |
| Tekst jest po angielsku, mimo że sklep działa w innym języku. | Gotowy szablon prosi o angielski albo wybrano zły język. | Edytuj szablon i zaznacz właściwy język w uruchomieniu. |
| **The reply was rejected because it contains a forbidden word from the studio settings.** | **Quality gate** znalazła słowo z listy **Forbidden words**. | Uruchom ponownie, usuń to słowo ze **Studio** albo wyłącz **Quality gate**. |
| **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** | Liczba generacji w tym miesiącu osiągnęła **Monthly generation budget**. | Zwiększ wartość w **Settings → Studio** albo ustaw 0. |
| **Error! The generated content could not be saved to the product.** | PrestaShop odrzucił tekst, na przykład nazwę produktu zawierającą niedozwolone znaki. | Przeczytaj szczegóły w wierszu i w **History**. Popraw prompt i uruchom ponownie. |
| **Error! This PrestaShop version does not support the category Additional Description field.** | Twoja wersja PrestaShop nie ma tego pola. | Wybierz inne pole. |
| Wiersz pokazuje **Product skipped.** lub **Category skipped.** | Wybrano **Skip if filled**, a pole ma już tekst. | Wybierz **Replace**, aby nadpisać tekst. |
| Po **Fill** wraca stary tekst. | Formularz został zapisany bez odświeżenia strony. | Odświeżaj stronę produktu po każdym **Fill**, a dopiero potem kontynuuj. |
| Uruchomienie zbiorcze się zatrzymało. | Strona została zamknięta albo odświeżona. | Zacznij od nowa, ustawiając **Update only** na opcję dla produktów, które jeszcze nie zostały zaktualizowane. Nieudane wywołania liczą się tam jako zaktualizowane. |
| Strona kategorii ma drugi formularz z przyciskiem **Generate content**, który nic nie robi. | Ten formularz nie jest podłączony. | Użyj **Run on the categories below**. |
| **Error! This log entry has no previous value to restore.** | Wiersz History nie ma wcześniejszego tekstu. | Edytuj pole ręcznie. |
| Wynik **Try** nie pojawia się w produkcie, mimo że wiersz w History istnieje. | **Try** nigdy nie zapisuje tekstu w produkcie. | Kliknij **Fill**, aby zapisać. |

### 5.4 Zdjęcia i nowe produkty

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| Zakładka **Photos** prosi o włączenie wyszukiwarki. | **AI Image Finder** jest wyłączone. | Włącz je w **Settings → General** albo na stronie **Images**. |
| **Claude API key is not configured. Please check module settings.** | Nie zapisano żadnego klucza. | Otwórz **Settings → Claude**. |
| **The search failed.** | Claude albo sieć nie odpowiedziały. | Kliknij ponownie **Find pages**, sprawdź klucz i limit czasu. |
| **No photos were found on the suggested pages.** | Strony nie zawierały użytecznych zdjęć. | Zmień nazwę lub opis produktu albo edytuj **AI Image Search Prompt**. |
| **URL not allowed (private network).** | Adres wskazuje sieć prywatną lub lokalną. | Używaj tylko publicznych stron internetowych. |
| **No images selected** | Nic nie zaznaczono. | Zaznacz co najmniej jedno zdjęcie. |
| **No images could be imported. Details: …** | Zdjęć nie udało się pobrać albo nie były prawidłowymi obrazami. | Przeczytaj szczegóły. Spróbuj innych zdjęć. |
| Zdjęcie okładkowe się zmieniło. | Pierwsze zaznaczone zdjęcie staje się okładką. | Zmień kolejność zdjęć na stronie produktu. |
| **Add an API key in the module settings first.** (**New product**) | Nie zapisano żadnego klucza. | Otwórz **Settings → Claude**. |
| **Failed to parse AI response. Please try again.** | Claude zwrócił tekst, który nie jest prawidłową wersją roboczą. | Kliknij ponownie **Generate data**. Opisz produkt dokładniej. |
| **Prompt is required**, **Invalid product data**, **Failed to create product** | Opis jest pusty, wersja robocza jest niekompletna albo PrestaShop nie mógł zapisać produktu. | Wypełnij **What is the product?**, wygeneruj ponownie i sprawdź ID kategorii. |

### 5.5 Problemy z cronem

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| Adres odpowiada **Invalid action!** | Adres skopiowany ze strony nie zawiera części `&action=`. | Dodaj `&action=generateProductContent` (produkty) lub `&action=generateCategoryContent` (kategorie). |
| Adres odpowiada **Cron Job feature is disabled…** | **Enable Cron Feature** jest wyłączone. | Ustaw **Yes** i kliknij **Save**. |
| Przycisk **Generate Token** nic nie robi. | Przycisk nie jest podłączony w tej wersji. | Wpisz sekret z co najmniej 24 liter i cyfr w polu **Cron Job Secret Token** i kliknij **Save**. Krótszy sekret zostanie zastąpiony losowym przy następnym otwarciu strony administratora. |
| Adres odpowiada **All must include all mandatory parameters!** | Formularz nigdy nie został zapisany, więc nie ma zapisanego szablonu. | Wybierz **Prompt Template**, a potem kliknij **Save**. |
| Adres odpowiada **No products to update.**, mimo że produkty wymagają tekstu. | **Selected Products** je wyklucza. **pendingClaude** pomija każdy produkt z udaną generacją, łącznie z uruchomieniami **Try**. | Użyj **emptyField** lub **pendingField**, albo ustaw **Product ID list**. |
| Tekst produktu został napisany ponownie. | Cron zawsze zastępuje pole. | Użyj **emptyField**, aby zmieniać tylko puste pola. |
| **Error!Monthly generation budget reached.** | Miesięczny budżet został wykorzystany. | Zwiększ go w **Settings → Studio**. |
| **Error! Could not save product N: … (X product(s) updated before this one.)** | PrestaShop odrzucił tekst dla produktu N. | Napraw ten produkt albo go wyklucz, a potem uruchom ponownie. |
| Polecenie na stronie nie zmienia się po zmianie formularza. | Polecenie pokazuje tylko adres podstawowy. | Dodaj `&action=` samodzielnie. Wartości z formularza są odczytywane z zapisanych ustawień. |
| Interwał w formularzu nie ma żadnego efektu. | To tylko notatka dla Ciebie. | Utwórz harmonogram w panelu hostingu. |

### 5.6 History i dane

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| Dashboard i History są puste po użyciu **Clear list**. | **Clear list** usuwa wszystkie wiersze. | Nie ma czego przywracać. Przed czyszczeniem zaplanuj eksport danych. |
| **This log entry no longer exists.** | Wiersz został usunięty. | Wróć do listy. |
| **Update only** nie pokazuje żadnych produktów. | Filtr korzysta z wpisów History, a każdy produkt ma już wpis. | Wybierz **Update all**. |
| Niektóre produkty są pomijane w **Update only**. | Nieudane wywołania i uruchomienia **Try** też liczą się jako wpisy. | Wybierz **Update all**. |

## 6. Dla programistów

### 6.1 Przegląd

My AI Claude (`myaiclaude`, wersja 1.1.0, autor MyPresta.eu) to moduł PrestaShop dla zakładki `front_office_features`. Obsługuje PrestaShop od wersji 1.6 do 9.99.99 i PHP 7.0 lub nowszy. Wywołuje Messages API Anthropic Claude pod adresem `https://api.anthropic.com/v1` (endpoint `/messages`) i zapisuje wyniki w produktach i kategoriach.

- Klasa `myaiclaude` w `myaiclaude.php` odpowiada za instalację, odinstalowanie, strony konfiguracji i hooki.
- Klasa `MyAIClaude\OpenAIService` (`src/OpenAIService.php`) to klient API. Wysyła `model`, `max_tokens`, `messages`, opcjonalnie `system` i opcjonalnie `temperature`, z nagłówkami `x-api-key` i `anthropic-version: 2023-06-01`. Top P i dwie kary są zapisywane, ale nie wysyłane. Klient mapuje `input_tokens` i `output_tokens` na tokeny wysłane i odebrane. Metoda `listModels()` zawsze zwraca listę z katalogu modułu, czyli zestaw wbudowany plus nazwy zachowane w `EXTRA_MODELS`. Limit czasu jest ograniczany do przedziału 10–600 sekund. Gdy API odpowiada kodem 400 i wskazuje konkretny parametr, klient pomija ten parametr, ponawia zapytanie i zapamiętuje tę decyzję dla modelu w `MODEL_CAPS`.
- Klasa `MyAIClaude\Studio` (`src/Studio.php`) opakowuje prompty wierszem języka, głosem, odbiorcami, tonem, glosariuszem i zakazanymi terminami. Stosuje miesięczny budżet i bramkę zakazanych słów oraz buduje prompt pakietu SEO.
- Zakładki strony konfiguracji używają parametrów URL `mac_tab` (`dashboard`, `settings`, `updates`) i `mac_sub` (`general`, `openai`, `studio`, `templates`, `playground`). Wartość `openai` parametru `mac_sub` otwiera zakładkę Claude. Dashboard korzysta z parametru `mcg_preset` oraz dat `mac_from` i `mac_to`.
- Klasy CSS panelu administracyjnego mają prefiks `.mac-`.
- Zadania zbiorcze wykonują jedną pozycję na jedno żądanie AJAX z pliku `back.js`.

### 6.2 Pliki

| Ścieżka | Cel | Uwagi |
|---|---|---|
| `myaiclaude.php` | Klasa modułu | Instalacja, odinstalowanie, formularze, hooki, umiejscowienie zakładki. |
| `autoload.php` | Loader dla przestrzeni nazw `MyAIClaude\` | |
| `src/OpenAIService.php`, `src/Studio.php` | Klient API i reguły Studio | |
| `controllers/admin/AdminMyAIClaude*.php` | Kontrolery panelu administracyjnego | Patrz 6.3. |
| `controllers/front/ajax.php`, `controllers/front/cron.php` | Kontrolery front | AJAX i cron. |
| `lib/updateChecker.php` | Sprawdzanie aktualizacji MyPresta | Łączy się z `dev.mypresta.eu/update/get.php`. |
| `lib/sectionHelp.php` | Teksty panelu **Help** | |
| `lib/prestashop9compatibility.php` | Funkcje pomocnicze zgodności | |
| `lib/searchTool` | Pomocnik autouzupełniania dla formularzy administracyjnych | |
| `views/templates/` | Szablony Smarty | Hooki, strony administracyjne, panele zbiorcze. |
| `views/js/` | `back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `dashboard.js`, `admin-help.js`, `chart.min.js` | |
| `views/css/` | Style z prefiksem `.mac-` | |
| `translations/` | 34 pliki językowe | |
| `upgrade/index.php` | Plik zastępczy | Moduł nie ma skryptów aktualizacji. |

### 6.3 Kontrolery

| Kontroler | Menu lub trasa | Rola |
|---|---|---|
| AdminMyAIClaudeMain | **AI Content Generator** w sekcji **Modules** | Przekierowuje na Dashboard. Rodzic ukrytych zakładek. |
| AdminMyAIClaude | Ukryta zakładka **Mass Content Creator** | Generate: produkty i kategorie. |
| AdminMyAIClaudeProductCreator | Ukryta zakładka **AI Product Creator** | New product. |
| AdminMyAIClaudeSettings | Ukryta zakładka **Module Settings** | Przekierowuje na zakładkę Settings. |
| AdminMyAIClaudeCron | Ukryta zakładka **Cron Job Settings** | Dwa formularze cron. |
| AdminMyAIClaudeUsage | Ukryta zakładka **Module Log and Usage** | History. |
| AdminMyAIClaudeImageFinder | Ukryta zakładka **AI Image Finder** | Images. |
| Front `ajax` | `module/myaiclaude/ajax` | Akcje `initiatePrompt`, `updateProduct`, `updateCategory`, `initiateProductRestore`, `updateSettings`, `generateAltTexts`, `generateSeoPack`. Wymaga `secret_token` równego `TOKEN`. Nie jest powiązany z sesją pracownika. Żaden ekran w tej wersji nie wywołuje `generateAltTexts`. |
| Front `cron` | `module/myaiclaude/cron` | Wymaga `secret` równego `SECRET` lub `CAT_SECRET` oraz `ENABLE_CRON=1`. Parametry: `action` (`generateProductContent`, `generateCategoryContent`), `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`, `categoryTarget`, `categoriesToUpdate`. Brakujące parametry są odczytywane z zapisanych ustawień. |

Zakładki podrzędne są tworzone z `active=0` pod `AdminMyAIClaudeMain`. W `displayBackOfficeHeader` moduł umieszcza główną zakładkę pod zakładką nadrzędną Modules, zmienia jej nazwę i regeneruje sekrety krótsze niż 24 znaki. Klasa ikony to `icon-openai`. Zakładka Image Finder jest rejestrowana na żądanie i oznaczana przez `IMAGEFINDER_TAB_OK`.

Cron produktów akceptuje cele `pendingClaude`, `pendingField` i `emptyField` i liczy tylko wiersze logu o statusie innym niż `error`. Filtr **Update only** w Generate liczy każdy wiersz logu. Wiersze logu crona używają metody `cron`.

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

Moduł nie ma metody `enable()` ani `disable()`. Metoda `displayCustomTop` i szablon `top.tpl` istnieją, ale nie są wywoływane.

### 6.5 Nadpisania (overrides)

Moduł nie ma katalogu `override` i nie zmienia żadnego pliku rdzenia. Zdjęcia produktów zapisuje klasami obrazów PrestaShop, a produkty i kategorie zapisuje obiektami PrestaShop (`Product`, `Category`, `Tag::addTags`).

### 6.6 Baza danych

Tabele (z prefiksem Twojego sklepu, silnik jak w PrestaShop):

| Tabela | Kolumny | Uwagi |
|---|---|---|
| `myaiclaude_prompt` | `id_prompt` (klucz główny), `status`, `title`, `prompt`, `date_generated` | Zawiera 16 zainstalowanych szablonów oraz Twoje własne. |
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
| `MODEL`, `EXTRA_MODELS`, `MODEL_CAPS` | `claude-sonnet-4-5`, puste, puste | Aktywny model, dodane modele, zapamiętana obsługa parametrów. |
| `TEMPERATURE`, `MAX_TOKENS`, `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 0.7, 3200, 1, 0, 0 | Pola próbkowania. Ostatnie trzy nie są wysyłane. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | Puste | Pola tekstowe Studio. |
| `BUDGET`, `QUALITY` | 0, 1 | Miesięczny budżet i bramka jakości. |
| `TOKEN` | Losowe 32 znaki | Sekret AJAX. |
| `SECRET`, `CAT_SECRET` | Losowe 32 znaki | Sekrety cron produktów i kategorii. |
| `ENABLE_CRON` | 0 | Przełącznik crona. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Notatki o interwale. |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList` | description, pendingClaude, 5, puste, język domyślny, puste, 0, puste | Zapisany formularz cron produktów. |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug`, `categories` | description, pendingClaude, 5, puste, język domyślny, 0, puste | Zapisany formularz cron kategorii. |

Ekrany Generate zapisują też ostatnie wybory filtrów w kluczach takich jak `FIELD`, `LANGUAGE`, `CONTENT`, `DELAY`, `EXISTING`, `HISTORY`, `STATUS`, `STOCK`, `CATEGORIES`, `BRANDS`, `CATEGORIESC` oraz kilku kluczach `PROD_*`. Odinstalowanie ich nie usuwa, podobnie jak `mypresta_updates`, `update_myaiclaude` i `updatev_myaiclaude` ze sprawdzania aktualizacji. Odinstalowanie usuwa pozostałe klucze oraz starsze klucze poprzedniego dostawcy.

Teksty pomocy przy polach formularzy buduje metoda `fieldHelp()` w trzech częściach: **What it does**, **How to configure** i **Effect**. Ciągi przechodzą przez system tłumaczeń PrestaShop (domeny tłumaczeń modułu i kontrolera). Nowy język dodasz, umieszczając plik `translations/<iso>.php`. Teksty panelu Help pochodzą z `lib/sectionHelp.php`. Odpowiedzi crona, prompty Studio i domyślne prompty to zwykłe angielskie ciągi w kodzie.

### 6.8 Rozszerzanie

- Modele dodasz polem **Add a Claude model** albo dopisując identyfikator do `EXTRA_MODELS`.
- Prompty dodasz jako szablony albo wyślesz własny tekst przez akcje `ajax` z sekretem.
- Zmienne są zastępowane w `controllers/front/ajax.php`. Zmienne `{cms_title}`, `{brand_name}`, `{brand_description}` i `{brand_short_description}` są rozpoznawane, gdy żądanie zawiera ID strony CMS lub marki. Żaden ekran w tej wersji nie wysyła tych ID.
- Własny harmonogram zbudujesz na podstawie adresu crona i jego parametrów (sekcja 6.3).
- Moduł nie renderuje żadnego szablonu storefront, więc motyw nie ma czego nadpisywać.

## 7. Pomoc

Strona modułu: https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-claude-ai.html

Aby uzyskać wsparcie:

1. Zaloguj się na mypresta.eu.
2. Przejdź do **contact**.
3. Wybierz **Support for paid modules**.
4. Podaj nazwę modułu (My AI Claude), jego wersję (1.1.0), wersje PrestaShop i PHP oraz opisz, co robiłeś, zanim pojawił się problem. Dołącz tekst widocznego komunikatu.
