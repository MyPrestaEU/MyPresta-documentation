---
title: "AI Translations with DeepSeek – dokumentacja i instrukcja użytkownika (user manual)"
sidebar:
  label: "AI Translations with DeepSeek – dokumentacja i instrukcja użytkownika (user manual)"
description: "Instrukcja konfiguracji i rozwiązywania problemów modułu AI Translations with DeepSeek dla osób, które moduł już mają."
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł AI Translations with DeepSeek na MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-deepseek.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ai-artificial-intelligence/ai-translations-with-deepseek/)
>
> ---


## 1. Wymagania

Moduł działa w sklepie PrestaShop 1.7.0.0 lub nowszym i potrzebuje klucza API z własnego konta DeepSeek.

- **PrestaShop:** wersja 1.7.0.0 lub nowsza.
- **PHP:** moduł nie podaje własnej minimalnej wersji PHP. Serwer musi obsługiwać PHP wymagane przez wybraną wersję PrestaShop.
- **Rozszerzenia PHP:** cURL (połączenie z DeepSeek), mbstring (liczenie znaków w tekstach), OpenSSL (szyfrowanie klucza API) oraz JSON (zapis wysyłanych i odebranych danych).
- **Inne moduły:** moduł nie wymaga żadnych innych modułów.
- **Poza sklepem:** własne konto w DeepSeek z kluczem API. Bez klucza moduł niczego nie przetłumaczy.
- **Cron na serwerze:** potrzebny tylko wtedy, gdy zadania masowe mają działać bez klikania. Opis znajdziesz w punkcie 3.1.
- **Duży katalog:** zadanie masowe dzieli się na porcje, a każda porcja to jedno wywołanie DeepSeek. Duże zakresy trwają długo, dlatego przed startem sprawdź je przyciskiem **Estimate**.

## 2. Instalacja

1. Wgraj plik ZIP modułu w **Module Manager** przyciskiem **Upload a module** i kliknij **Install**.
2. Po instalacji w menu pojawi się pozycja **International → AI Translations with DeepSeek**. Ta pozycja otwiera panel modułu.
3. Instalacja nie czyści cache sklepu. Jeśli nowa pozycja w menu się nie pokazuje, przejdź do **Zaawansowane → Wydajność** i kliknij **Wyczyść cache**.

Po instalacji panel jest pusty: nie ma klucza API, a ustawienia mają wartości startowe opisane w punkcie 3.1.

**Odinstalowanie** usuwa pozycję w menu, zadania masowe wraz z ich historią, glosariusz, listę wykluczeń, pamięć tłumaczeń, kopie zapasowe używane do **Rollback**, historię wywołań i błędów, kolejkę przeglądu, listę z zakładki **Catalog** oraz wszystkie ustawienia, w tym klucz API i adres cron.

Odinstalowanie **nie usuwa** tłumaczeń już zapisanych w sklepie: produktów, kategorii, stron CMS i napisów na stronie International → Translations zostają takie, jakie były. Po odinstalowaniu nie da się już cofnąć tych tłumaczeń przyciskiem **Rollback**, bo kopie znikają razem z modułem.

Ponowna instalacja **nie przywraca** usuniętych danych. Tabele powstają puste, a ustawienia wracają do wartości startowych. Nowy jest też adres cron, więc skopiuj go na nowo z **Settings** i zaktualizuj harmonogram na serwerze.

## 3. Konfiguracja i praca w zapleczu

Ekrany w panelu są po angielsku. W tej instrukcji nazwy pól, zakładek i przycisków podaję dokładnie tak, jak je widzisz.

**Kto zaczyna:** zawsze pracownik sklepu w panelu. Klient nie uruchamia tłumaczeń.

**Proces od początku do końca:**

1. W **Settings** wklej klucz DeepSeek, wybierz model i kliknij **Save**. Potem kliknij **Test connection**, żeby sprawdzić klucz.
2. Ustaw **Source locale** (język oryginału) i sprawdź, czy **Allow publish / save** jest włączone.
3. Wybierz, co tłumaczyć. Pojedyncze domeny i ciągi tłumaczysz na **Manual**. Duże zakresy zlecasz przez **Bulk**. Pola produktów, kategorii i stron CMS tłumaczysz na **Catalog**. Przyciski przy polach formularzy sklepu i na stronie International → Translations działają od razu w miejscu, w którym pracujesz.
4. Na **Manual** i przy przyciskach w polach najpierw dostajesz propozycję tłumaczenia. Zapisujesz ją osobnym krokiem: przyciskiem **Save approved** na **Manual**, zaznaczeniem **Save now (skip review)** albo przyciskiem **Save** PrestaShop na formularzu.
5. Na **Bulk** klikasz **Estimate**. Nic nie jest wysyłane ani zapisywane. Jeśli szacunek jest w porządku, klikasz **Start job**. Zadanie trafia do **Jobs** i czeka. Nie uruchamia się samo: klikasz **Process slice** albo **Auto-process**, albo porcje wywołuje cron na serwerze.
6. Tłumaczenia, których kontrola jakości nie przepuściła, trafiają do **Review**. Przycisk **Approve** tylko zmienia status wiersza. Nie wpisuje tekstu do sklepu.
7. **Glossary** i **Excludes** wpływają na kolejne tłumaczenia. Tłumaczenia już zapisane się nie zmieniają.
8. **Dashboard** pokazuje braki i koszty, a **History** każde wywołanie DeepSeek.

**Czym kończy się praca:** zadanie masowe kończy się statusem **completed** (wszystko przetłumaczone) albo **completed_with_errors** (były błędy). Wtedy wysyłany jest e-mail, jeśli go włączono. Ręczne tłumaczenie kończy się zapisem wybranych wierszy w sklepie.

### 3.1 Settings (ustawienia modułu)

Wejście: **Moduły** → **Module Manager** → nazwa modułu → **Konfiguruj**. Przycisk **Konfiguruj** otwiera panel modułu, a zakładka **Settings** jest w pasku u góry.

![Zakładka Settings](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings.webp)

Kolejne fragmenty tego samego formularza:

![Settings – przełączniki przycisków tłumaczenia i język źródłowy](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-buttons.webp)

![Settings – limity, budżet i temperatura](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-limits.webp)

![Settings – e-mail, zapis i adres cron z przyciskami Test connection i Save](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-settings-publish.webp)

Zapisanie formularza przyciskiem **Save** nie zmienia gotowych tłumaczeń. Gdy pole **DeepSeek API key** jest puste, a klucz nie był wcześniej zapisany, pojawia się komunikat: „Settings saved. No API key is stored, so nothing can be translated until you paste one.”

| Pole | Na starcie | Co robi |
|---|---|---|
| **DeepSeek API key** | puste | Klucz z Twojego konta DeepSeek. Puste pole zostawia klucz już zapisany, a wpisana wartość go zastępuje. Puste pole nie usuwa klucza. Pod polem widać zapisany klucz zamaskowany. Zapytania idą na api.deepseek.com. |
| **Model** | deepseek-flash | Model DeepSeek, który pisze tłumaczenie. Na liście są modele wbudowane: deepseek-flash, deepseek-v4-pro, deepseek-v4-flash, deepseek-chat i deepseek-reasoner. Model, do którego konto nie ma dostępu, kończy się błędem zapisanym w **History**. |
| **Add a DeepSeek model** | puste | Dodaje identyfikator modelu, którego nie ma na liście. Wpisz go dokładnie tak, jak w koncie DeepSeek, i kliknij **Add model**. Dodany model od razu staje się aktywnym modelem. **Remove** usuwa tylko modele dodane tutaj. Wbudowanych nie da się usunąć. |
| **Tone** | Formal | Styl dopisywany do każdego polecenia dla modelu. **Formal** to wersja do sklepu i back office, **Casual** jest lżejsza, a **Brand** działa razem z polem **Brand voice**. Nowe tłumaczenia przyjmują styl. Zapisane zostają bez zmian, dopóki ich nie przetłumaczysz ponownie. |
| **Brand voice** | puste | Kilka zdań o tym, jak ma brzmieć sklep. Pole pojawia się przy **Tone** ustawionym na **Brand**. Tekst trafia do kolejnego polecenia i nie przepisuje zapisanych tłumaczeń. Puste pole oznacza brak dodatkowego tonu. |
| **Source locale** | puste (—) | Język traktowany jako oryginał, zwykle English (en-US). Myślnik „—” oznacza, że ekran, na którym tłumaczysz, sam podaje język źródłowy. Ręczne i masowe tłumaczenia oraz przyciski na stronie International → Translations wysyłają ten język jako źródło. Domyślny język sklepu się nie zmienia. |
| **Individual field buttons — shop forms** | Yes | Przycisk przy każdym polu wielojęzycznym formularzy sklepu: produkt, kategoria, CMS i inne formularze. Przycisk tłumaczy tylko to jedno pole. **No** ukrywa te przyciski w całym sklepie. Nie wpływa na stronę International → Translations. |
| **Individual field checkboxes — shop forms** | Yes | Pole wyboru przy polach formularzy sklepu i pasek na dole, który tłumaczy zaznaczone pola. **No** ukrywa pola wyboru i pasek. Przyciski z poprzedniego wiersza mają własny przełącznik. |
| **Individual field buttons — International → Translations** | Yes | Przycisk przy każdym polu na stronie International → Translations. **No** ukrywa te przyciski tylko na tej stronie. Formularze sklepu się nie zmieniają. |
| **Individual field checkboxes — International → Translations** | Yes | Pola wyboru i pasek na stronie International → Translations. Pasek tłumaczy zaznaczone pola jedno po drugim. **No** ukrywa pola wyboru i pasek na tej stronie. |
| **Batch size** | 25 | Ile ciągów idzie w jednym wywołaniu DeepSeek. Dozwolone wartości to od 1 do 100. Na pierwsze uruchomienie wybierz od 10 do 25. Większa paczka kończy zadanie w mniejszej liczbie wywołań, ale po błędzie powtarza się większa część. |
| **Dry-run sample** | 10 | Ile przykładowych ciągów pokazuje **Estimate** przed zadaniem masowym. Dozwolone wartości to od 1 do 50. **Estimate** nie zapisuje tłumaczeń. |
| **Max tokens (0 = default)** | 0 | Limit długości jednej odpowiedzi. 0 oznacza domyślny limit DeepSeek. Ustaw liczbę, jeśli odpowiedzi są ucinane albo za długie. Limit działa tylko na kolejne wywołania. |
| **Budget USD / month** | 0 | Miesięczny limit w dolarach liczony z zapisanego zużycia. 0 oznacza brak limitu. Po osiągnięciu limitu nowe tłumaczenia się zatrzymują, a już zapisane zostają. |
| **Rate limit / min** | 60 | Ile wywołań sklep może wykonać w ciągu minuty. 0 wyłącza ten limit. Wywołania ponad limit są pomijane i zapisywane w **History**. DeepSeek może stosować też własny limit. |
| **Log retention days** | 30 | Ile dni trzymać wpisy w **History**. Minimum to 1 dzień. Starsze wpisy są usuwane. Zadania, glosariusz i zapisane tłumaczenia nie są kasowane. |
| **Temperature** | 0.2 | Jak swobodnie model przeformułowuje tekst. Wartość około 0,2 trzyma się oryginału, a wartości bliżej 1 zmieniają zdania bardziej. Dozwolony zakres to od 0 do 1. Placeholdery i HTML są sprawdzane po każdym tłumaczeniu. |
| **Email notify on complete** | No | Wysyła jeden e-mail, gdy zadanie masowe się skończy. Samo zadanie działa tak samo, zmienia się tylko wysyłka. |
| **Notify email** | puste | Adres, na który przychodzi e-mail o zakończonym zadaniu. Pole działa tylko przy włączonym **Email notify on complete**. Puste pole oznacza e-mail sklepu z ustawień firmy. Sam zapis adresu nie wysyła wiadomości. Temat i treść są po angielsku, np. „myaitranslationsdeepseek job #41 completed”, a w treści są liczby: wykonane, błędne i pominięte. |
| **Allow publish / save** | Yes | Czy moduł może zapisywać tłumaczenia w sklepie. Przy **No** zapis jest zablokowany na **Manual**, w zadaniach masowych i na **Catalog**. Przyciski na stronie International → Translations tylko wypełniają formularz, a zapisuje go przycisk **Save** PrestaShop. |
| **CRON URL** | wygenerowany adres | Adres dla harmonogramu serwera. Każde wywołanie przetwarza jedną porcję jednego czekającego zadania i kończy się. Nie publikuj tego adresu, bo każdy, kto go zna, może uruchomić porcję. Samo otwarcie **Settings** nie uruchamia zadania. |

Przyciski na dole formularza: **Save** zapisuje ustawienia. **Test connection** sprawdza klucz i nie zapisuje żadnego tłumaczenia.

Zalecany start: wklej klucz, wybierz model, ustaw **Source locale**, kliknij **Save**, a potem **Test connection**. Reszta liczb może zostać na wartościach startowych, dopóki zadanie nie zachowuje się tak, jak chcesz.

### 3.2 Dashboard

Dashboard pokazuje, ile tekstów brakuje w każdej części katalogu dla wybranego języka, oraz zużycie DeepSeek. Otwarcie **Dashboard** nie wysyła żadnego zapytania i nie zmienia tłumaczeń.

![Dashboard](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-dashboard.webp)

- **Locale** to język, którego braki są liczone. Pierwszy raz wybierany jest pierwszy język sklepu z listy. Zmień język i kliknij **Show**, żeby przeliczyć tabelę.
- **Tabela pokrycia** ma kolumny **Section**, **Done**, **Missing** i **Total**. Każdy wiersz to jedna część katalogu: back office, motywy, moduły, e-maile albo inne. Pasek pokazuje, jaka część jest już przetłumaczona.
- **Karty i wykresy** liczą wywołania z wybranego zakresu. Pola filtra to daty (presety oraz **From** i **To**), a dalej **Model**, typ, status, język, pracownik i fragment tekstu w prompcie lub odpowiedzi. Przycisk **Filter** stosuje filtr. Karty pokazują liczbę wywołań, tokeny wysłane i odebrane, średni czas oraz szacowany koszt. Koszt to lokalne oszacowanie, nie faktura.
- **Latest prompts** to dziesięć najnowszych wywołań. **View** otwiera prompt i odpowiedź w oknie. **See all** przenosi do **History**.
- Pod tabelą jest adres cron. To ten sam sekret co w **Settings**.

![Dashboard – wykresy i zestawienia](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-dashboard-charts.webp)

Pusta tabela pokrycia oznacza, że sklep nie ma jeszcze katalogu dla tego języka. Katalog tworzy zakładka International → Translations.

### 3.3 Manual

**Manual** tłumaczy wybraną domenę, kilka ciągów naraz. **Filter** tylko ładuje listę i niczego nie zapisuje.

![Manual](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-manual.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Section** | Back office | Wybiera katalog PrestaShop do odczytu: **Back office**, **Themes**, **Installed modules**, **Emails** albo **Others**. Zmiana sekcji przeładowuje formularz i nie wywołuje DeepSeek. |
| **Theme** | — | Pojawia się tylko dla **Themes**. Ogranicza listę do jednego motywu. |
| **Module** | — | Pojawia się tylko dla **Installed modules**. Ogranicza listę do jednego modułu. Moduł bez domen ładuje od razu wszystkie napisy. |
| **Source** | Source locale z **Settings** (en-US) | Język, z którego pobierane są teksty. Wybierz ten, który już ma wiarygodne tłumaczenie. Język docelowy się nie zmienia. |
| **Target** | pierwszy język sklepu z listy | Język, który chcesz uzupełnić. Musi istnieć w International → Localization → Languages. Lista i późniejszy zapis dotyczą tylko tego języka. |
| **Domain** | — | Domena tłumaczeń, czyli te same grupy co na International → Translations. Naciśnij **Filter**, żeby lista się zapełniła, wybierz domenę i naciśnij **Filter** ponownie. Nie pojawia się przy module bez domen. |
| **Only empty** | Yes | Ukrywa ciągi, które już mają tłumaczenie. **No** pokazuje wszystkie ciągi. Tabela się zmienia, zapisane tłumaczenia nie są kasowane. |
| **Search** | puste | Zostawia tylko ciągi, których źródło zawiera wpisane słowo. Katalog się nie zmienia. |

**Jak tłumaczyć:**

1. Zaznacz wiersze albo kliknij **Check all** (zaznacza widoczne), a **Uncheck all** odznacza.
2. Kliknij **Translate selected (review)**. Moduł wysyła zaznaczone ciągi i pokazuje tabelę do przeglądu. Jeszcze nic nie zostaje zapisane.
3. W tabeli przeglądu odznacz wiersz, jeśli nie chcesz go zapisać, i popraw propozycję w polu **AI proposal**.
4. Kliknij **Save approved**. Zapisywane są zaznaczone wiersze.

Jeśli zaznaczysz **Save now (skip review)** przed tłumaczeniem, zaakceptowane wiersze zapisują się od razu, bez tabeli przeglądu.

Tabela wyników ma kolumny **Source**, **Current** (obecne tłumaczenie), **AI proposal**, **Status** (**empty** albo **filled**), **Tokens** i **Warnings**. Wiersz z uszkodzonym placeholderem albo HTML-em nie zostanie zapisany.

Komunikaty, które zobaczysz:

- „No strings match this filter. Nothing was sent to DeepSeek.” — filtr nie znalazł ciągów. Nic nie zostało wysłane.
- „Review is ready. Nothing is saved until you press Save approved.” — propozycje czekają w tabeli. Dopiero **Save approved** je zapisuje.
- „Saved. The approved strings were written for the target language.” — zaznaczone wiersze zapisane.
- „Not saved because of broken placeholders or HTML: N.” — N wierszy nie zapisano, bo model zmienił placeholder albo znacznik HTML. Popraw je w tabeli albo odznacz.

### 3.4 Bulk

**Bulk** tworzy jedno zadanie dla wielu domen i języków. Zadanie nie wykonuje się w tym miejscu. Czeka na **Jobs**.

![Bulk](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-bulk.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Section** | Back office | Katalog, który czyta zadanie. Motyw pojawia się tylko dla **Themes**, a moduł tylko dla **Installed modules**. Ciągi spoza wybranej sekcji nie są w zadaniu. |
| **Source** | Source locale z **Settings** (en-US) | Język, który zadanie traktuje jako oryginał. Każdy cel jest tłumaczony z niego. |
| **Targets** | puste | Języki, które zadanie uzupełni. Możesz wybrać kilka: przytrzymaj Ctrl albo Cmd i klikaj. Zadanie tworzy osobne ciągi dla każdego wybranego języka. |
| **Domains** | puste | Domeny, które wchodzą do zadania. Domen, których nie wybierzesz, zadanie nie tłumaczy. |
| **Policy** | Fill empty | **Fill empty** pomija ciągi, które mają już tłumaczenie. **Overwrite all** wysyła wszystkie, także przetłumaczone, i może je nadpisać. **Outdated if equals source** wysyła ciągi, których tłumaczenie jest identyczne z oryginałem. |
| **Dry-run job** | No | Zadanie wywołuje model i zapisuje wynik w historii zadania, ale nie zapisuje tłumaczeń w sklepie. Przy **No** zadanie zapisuje wyniki, jeśli **Allow publish / save** jest włączone. |

**Estimate** pokazuje liczbę ciągów, szacunkowe tokeny i koszt oraz przykładowe ciągi. Nic nie jest wysyłane ani zapisywane. Komunikat: „Estimate only: N strings, ~N tokens, ~$… Nothing was sent to DeepSeek and nothing was saved.”

**Start job** tworzy zadanie i przenosi do **Jobs** z otwartym nowym zadaniem. Komunikat: „Job #N is waiting (N strings, est. $…). It has not run yet.”

Komunikaty przy błędach, które zatrzymują start:

- „Nothing was started. Select at least one target language.” — nie wybrano języka docelowego.
- „Nothing was started. Pick a theme.” albo „Nothing was started. Pick a module.” — w sekcji **Themes** lub **Installed modules** nie wybrano motywu albo modułu.
- „Nothing was started. There is no DeepSeek API key. Open Settings and paste the key. No job was created.” — brak klucza. Żadne zadanie nie powstało.

### 3.5 Jobs

**Jobs** to kolejka zadań masowych. Samo otwarcie listy nie wywołuje DeepSeek. Katalog zmienia się tylko wtedy, gdy zadanie jest przetwarzane i nie jest dry-runem.

![Jobs](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-jobs.webp)

**Lista zadań** ma kolumny **ID**, **Status**, **Locales**, **Progress**, **Cost**, **Employee** i **Date**. Kliknij zadanie, żeby zobaczyć jego ciągi. Filtr **Failed only** pokazuje tylko błędy, a **Error CSV** pobiera listę błędów do pliku.

Statusy zadania, dokładnie tak, jak pojawiają się w kolumnie **Status**: **pending** (czeka), **running** (w toku), **paused** (wstrzymane), **completed** (gotowe), **completed_with_errors** (gotowe z błędami), **cancelled** (anulowane) i **failed** (zakończone błędem). Statusy wierszy w szczegółach: **pending**, **processing**, **done**, **failed**, **skipped** i **rolled_back**. Oznaczenie **dry-run** pokazuje zadanie próbne.

**Przyciski w zadaniu:**

- **Process slice** wysyła następną porcję (tyle ciągów, ile wynosi **Batch size**) i kończy działanie. Po kliknięciu widać, które wiersze zapisano, pominięto albo odrzucono.
- **Auto-process** wysyła porcje jedna po drugiej, aż zadanie się skończy albo się nie powiedzie. Zostaw kartę otwartą, bo pasek postępu odświeża się sam.
- **Pause** wstrzymuje zadanie. Nie tłumaczy kolejnych ciągów, dopóki go nie wznowisz.
- **Resume** wraca do kolejki. Zadanie nie rusza samo: klikasz **Process slice**, **Auto-process** albo czeka na cron.
- **Retry failed** zmienia błędne ciągi z powrotem na oczekujące.
- **Rollback** przywraca poprzednie tłumaczenia tam, gdzie moduł zapisał kopię przed zmianą. Przed kliknięciem pojawia się pytanie „Roll back this job?”. Komunikat po wykonaniu: „Rollback: restored N translations.”
- **Error CSV** pobiera listę błędnych wierszy.

W tej wersji modułu na ekranie zadania **nie ma przycisku anulowania**. Zadania, którego nie chcesz dokończyć, nie anuluj tutaj. Wstrzymaj je przyciskiem **Pause** i nie wznawiaj.

Jeżeli DeepSeek odrzuci zbyt wiele wywołań, zadanie zatrzyma się samo. W jego błędzie pojawi się: „Rate limit — job auto-paused. Resume later.”

### 3.6 Review

**Review** to kolejka tłumaczeń, które kontrola jakości zatrzymała. Trafiają tu wiersze z błędem placeholdera lub HTML-u, z bardzo długim albo bardzo krótkim tłumaczeniem albo z wynikiem poniżej 70 punktów.

![Review](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-review.webp)

| Kolumna | Co pokazuje |
|---|---|
| **ID** | Numer wiersza w kolejce. |
| **Domain** | Domena, z której pochodzi tekst. |
| **Source** | Oryginalny tekst. |
| **AI** | Propozycja modelu. |
| **Score** | Automatyczna ocena jakości od 0 do 100. |
| **Flags** | Powody zatrzymania, opisane poniżej. |

**Flagi:**

- **validation_failed** — brakuje placeholdera albo znacznika HTML, albo zostały zmienione.
- **length_explosion** — tłumaczenie ma ponad 2,5 raza więcej znaków niż oryginał.
- **too_short** — tłumaczenie ma mniej niż 30% długości oryginału, a oryginał ma ponad 20 znaków.
- **possible_untranslated** — w tłumaczeniu zostały angielskie słowa, np. „the”, „and”, „with”.
- **warning** — ostrzeżenie kontroli, które obniża ocenę.

**Approve** oznacza wiersz jako zaakceptowany, a **Reject** jako odrzucony. Żaden z tych przycisków nie zapisuje tekstu w sklepie. Pusta kolejka pokazuje: „The queue is empty.” Pusta kolejka nie oznacza jednak, że wszystkie języki są przetłumaczone. Sprawdź to na **Dashboard**.

Jeśli zadanie miało zapis włączony, a ciąg przeszedł walidację, tłumaczenie może już być w sklepie. Kolejka **Review** to lista do ręcznego sprawdzenia, a nie blokada zapisu. Osobne zapisywanie wybranych wierszy jest na **Manual**.

### 3.7 Catalog

**Catalog** tłumaczy pola produktów, kategorii i stron CMS. Nie dotyczy napisów z International → Translations. Jedna porcja obejmuje najwyżej 100 rekordów.

![Catalog](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-catalog.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Entity** | product | Wybiera rodzaj rekordów: **product**, **category** albo **cms**. Lista pól zmienia się po wyborze. Sama zmiana rodzaju niczego nie tłumaczy. |
| **Fields** | pola zaznaczone domyślnie dla rodzaju | Teksty, które partia wysyła. Dla produktów to **Title**, **Short description**, **Description**, **Meta title**, **Meta description** i **Friendly URL**. Dla kategorii: **Title**, **Description**, **Meta title**, **Meta description** i **Friendly URL**. Dla CMS: **Title**, **Meta description**, **Meta keywords**, **Content** i **Friendly URL**. Wybieraj przytrzymując Ctrl albo Cmd. Niezaznaczone pola nie są wysyłane i nie zmieniają się. |
| **Source language** | pierwszy język z listy | Język, z którego kopiowany jest tekst. Ten język się nie zmienia. |
| **Target language** | pierwszy język z listy | Język, który dostanie tłumaczenie. Wybierz inny niż źródło. |
| **Only empty** | Yes | Pomija pola, które mają już tekst w języku docelowym. **No** wysyła także wypełnione pola, a wtedy partia może zastąpić ten tekst. |
| **Start after ID** | 0 | Pomija rekordy o numerze ID mniejszym lub równym wpisanemu. 0 zaczyna od pierwszego rekordu. Po każdej partii pole wypełnia się samo, a kolejna partia zaczyna za tym ID. |

Przycisk **Translate batch (max 100)** uruchamia partię. Wynik pokazuje, ile wierszy zapisano i ile się nie udało.

Przed włączeniem **Only empty** na **No** uruchom małą partię i otwórz jeden produkt w języku docelowym. Dopiero potem zastępuj istniejący tekst.

### 3.8 Glossary

**Glossary** to lista terminów, które model ma zachować albo przetłumaczyć w jeden stały sposób. Dodanie terminu nie zmienia zapisanych tłumaczeń. Kolejne tłumaczenia czytają listę.

![Glossary](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-glossary.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Source term** | puste (wymagane) | Słowo lub wyrażenie w języku oryginału, także z wielkimi literami, jeśli mają znaczenie. Model traktuje ten termin jako stały, gdy wystąpi w tekście źródłowym. |
| **Target locale** | puste | Ogranicza wiersz do jednego języka, np. pl-PL. Puste pole stosuje wiersz do wszystkich języków docelowych. |
| **Target term** | puste | Zatwierdzone tłumaczenie terminu. Pozostaw puste tylko wtedy, gdy włączono **Do not translate**. |
| **Do not translate** | No | Model kopiuje termin bez zmian. Włącz dla nazw marek, SKU i placeholderów. Wyłącz, gdy **Target term** ma być tłumaczeniem. |

Przycisk **Add** dodaje termin. Tabela pod formularzem ma kolumny **Source**, **Locale**, **Target** i **Do not translate**, a przy każdym wierszu jest przycisk **Delete**, który usuwa tylko ten wiersz. Pusta lista pokazuje: „No glossary terms yet.”

**Import CSV** dodaje wiersze z pliku. Plik musi mieć kolumny: source_term, target_locale, target_term, do_not_translate. Import dodaje tylko wiersze, które da się odczytać. **Export CSV** pobiera aktualną listę i niczego nie zmienia.

Krótkie, dokładne terminy działają najlepiej. Bardzo ogólny termin będzie wymuszany za każdym razem, gdy się pojawi.

### 3.9 Excludes

**Excludes** to wzorce tekstów, które mają nie trafiać do DeepSeek. Tekst zostaje w PrestaShop bez zmian. Moduł pomija go przy następnym tłumaczeniu ręcznym, zadaniu masowym i akcji na stronie International → Translations.

![Excludes](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-excludes.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Pattern** | puste (wymagane) | Tekst albo wyrażenie porównywane z każdym tekstem źródłowym. Zależnie od **Type** jest to cały tekst, początek, fragment albo wyrażenie regularne. |
| **Type** | exact | **exact** to cały tekst, **prefix** to początek tekstu, **contains** to fragment w dowolnym miejscu, a **regex** to wyrażenie regularne PHP. Zbyt szeroki wzorzec pominie więcej, niż chcesz. Zacznij od krótkiego. |

Przycisk **Add** dodaje wzorzec. Tabela ma kolumny **Pattern**, **Type** i **On** (czy wzorzec jest aktywny). Przy każdym wierszu jest przycisk **Delete**, który usuwa tylko ten wzorzec. Istniejące tłumaczenia nie są czyszczone. Pusta lista pokazuje: „No patterns yet.”

Wzorce są dla tekstów, które mają zostać w języku źródłowym, np. nazwy prawne lub techniczne tokeny. Gdy tekst ma być przetłumaczony w jeden stały sposób, użyj **Glossary**.

### 3.10 History

**History** to pełna lista zapisanych wywołań DeepSeek: ręczne tłumaczenie, strona International → Translations, zadanie masowe, Catalog i test połączenia. Każdy wiersz zawiera prompt, odpowiedź, model, języki, liczbę tokenów i czas odpowiedzi.

![History](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-history.webp)

- **When** to data wywołania, **Type** to miejsce, z którego wystartowało, a przy zadaniu masowym po typie stoi numer zadania.
- **View** otwiera prompt, który wysłano, i odpowiedź, która wróciła, w oknie na tej stronie. Wiersz z błędem pokazuje błąd w miejscu odpowiedzi.
- Filtry: daty, **Model**, typ, status, język, pracownik i fragment tekstu w prompcie lub odpowiedzi. Przyciski **Previous** i **Next** przełączają strony.
- **HTTP 401** lub **HTTP 403** zwykle oznacza, że klucz w **Settings** jest błędny albo nie ma dostępu do wybranego modelu.
- **Clear history** usuwa te wpisy, a zapisane tłumaczenia zostają. Pytanie przed usunięciem brzmi: „Clear the stored history? Saved translations stay.”

Nie wysyła nowego zapytania i nie zmienia tłumaczeń. Gdy tłumaczenia nagle przestają działać, zajrzyj tu na najnowszy wiersz z błędem, zanim zmienisz glosariusz.

### 3.11 Updates

Zakładka **Updates** pokazuje sekcję **MyPresta Updates**. Przycisk **Check Now** przy polu **Manual Check** sprawdza od razu, czy jest nowsza wersja modułu. Pole **Automatic Notifications** (**Enabled** albo **Disabled**) decyduje, czy moduł sprawdza wersję sam. Zmianę zapisujesz przyciskiem **Save**.

![Updates](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-updates.webp)

Gdy automatyczne powiadomienia są włączone, moduł sprawdza wersję co 3 dni, przy wejściu do back office. Do serwera MyPresta wysyła nazwę modułu, jego wersję, adres sklepu i identyfikator licencji, jeśli jest zapisany. Wyłączenie tej opcji zatrzymuje te automatyczne sprawdzenia.

### 3.12 Przyciski przy polach formularzy sklepu

Przy polach wielojęzycznych w formularzach produktów, kategorii, CMS i innych formularzach back office pojawia się przycisk tłumaczenia. Przy zaznaczonych polach działa też pasek na dole formularza.

![Produkt – tłumaczenie pola](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-translate.webp)

![Produkt – meta pola](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-meta.webp)

![Pasek tłumaczenia na formularzu produktu](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-product-bulk-bar.webp)

![Formularz kategorii z paskiem tłumaczenia](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-category-translate.webp)

**Pasek** na dole ma pola **Source** i **Target** oraz przyciski: **Check all**, **Uncheck all**, **Check empty**, **Translate empty** i **Translate selected**. Licznik **Selected** pokazuje, ile pól zaznaczono.

Przycisk przy polu tylko wypełnia to pole. Żeby zmiana została w sklepie, kliknij przycisk **Save** PrestaShop na dole formularza. Pasek działa tak samo: wypełnia zaznaczone pola i wymaga zapisu formularza.

Komunikaty na pasku:

- „Fill the source language field first.” — pole źródłowe jest puste. Wpisz tekst w języku źródłowym i spróbuj ponownie.
- „Tick at least one field.” — nic nie zaznaczono.
- „Target is not a language from this shop.” — wybrany język docelowy nie należy do sklepu.
- „Translating…” i „Done” — trwa tłumaczenie albo zakończono.

Przyciski i pasek znikają, gdy przełączniki w **Settings** są wyłączone. Przy polach formularzy sklepu działają przełączniki **shop forms**.

### 3.13 Strona International → Translations

Na stronie International → Translations przy każdym polu pojawia się przycisk tłumaczenia, a na dole działa ten sam pasek co na formularzach. Pasek ma pola **Source** (domyślnie en-US) i **Target**. Wybierz język, który chcesz uzupełnić.

![Strona International → Translations](https://mypresta.eu/docs/images/docs/myaitranslationsdeepseek-translations-page.webp)

- Przycisk przy polu wypełnia je tłumaczeniem. Zapisuje dopiero przycisk **Save** PrestaShop na tej stronie.
- Pasek przy zaznaczonych polach tłumaczy je jedno po drugim.
- **Translate empty in this section** tłumaczy puste pola w otwartej sekcji.
- W sekcji **Emails** moduł czyta plik źródłowy szablonu. Gdy go nie znajdzie, pojawia się komunikat: „The source language mail file was not found.” Wtedy wybierz inny język źródłowy w **Settings**.
- Komunikat „The source language field is not on this page.” oznacza, że na tej stronie nie ma pola języka źródłowego. Wejdź na inną zakładkę albo sekcję z tym językiem.

Przełączniki **Individual field buttons** i **Individual field checkboxes — International → Translations** w **Settings** ukrywają przyciski i pasek tylko na tej stronie.

## 4. Front sklepu

Moduł nie wyświetla niczego klientom. Nie dodaje strony, bloku, przycisku ani komunikatu w witrynie sklepu, więc motyw nie pokazuje żadnego efektu modułu i nie robię zrzutu witryny. Klient nie ma w module żadnego kroku.

Jedynym adresem modułu, pod którym można go wywołać z zewnątrz, jest adres cron z **Settings**. Nie jest on przeznaczony dla klientów. Służy serwerowi do przetwarzania zadań.

Co zobaczysz po otwarciu tego adresu w przeglądarce:

| Co widać | Co zrobić |
|---|---|
| Tekst `{"ok":false,"error":"Forbidden"}` | Adres jest błędny albo jego token jest nieaktualny. Skopiuj adres CRON URL na nowo z **Settings** i wklej go do harmonogramu. |
| Tekst `{"ok":true,"message":"No pending jobs"}` | Żadne zadanie nie czeka. To normalny stan, nic nie trzeba robić. |
| Tekst `{"ok":true,...}` z danymi porcji | Porcja została przetworzona. Szczegóły zobaczysz na **Jobs**. |
| Tekst `{"ok":false,"error":"..."}` z komunikatem | Odczytaj komunikat i przejdź do punktu 5 tej instrukcji. |

## 5. Problemy

**Brak pozycji w menu International.** Przyczyną jest zwykle cache sklepu. Przejdź do **Zaawansowane → Wydajność** i kliknij **Wyczyść cache**. Jeśli pozycja nadal się nie pojawia, odinstaluj moduł i zainstaluj go ponownie. Pamiętaj, że odinstalowanie usuwa ustawienia i historię zadań, więc zapisz klucz API i ustawienia przed tą czynnością.

**„Nothing was started. There is no DeepSeek API key. Open Settings and paste the key. No job was created.”** Nie wpisano klucza albo został usunięty. Otwórz **Settings**, wklej klucz z konta DeepSeek, kliknij **Save** i potem **Test connection**.

**„No DeepSeek API key. Nothing was translated.”** Ten sam przypadek: wklej klucz w **Settings** i zapisz.

**„Settings saved. No API key is stored, so nothing can be translated until you paste one.”** Zapisano ustawienia bez klucza. Wklej klucz i zapisz ponownie.

**Test connection kończy się błędem albo w History jest HTTP 401 lub 403.** Klucz jest błędny, nieaktualny albo konto nie ma dostępu do wybranego modelu. Wklej klucz od nowa. Jeśli błąd dotyczy modelu, wybierz inny model z listy albo dodaj model poprawnym identyfikatorem w **Add a DeepSeek model**.

**„DeepSeek rate limit (429). Try again later.”** DeepSeek ograniczył liczbę wywołań. Poczekaj kilka minut i wznów zadanie na **Jobs** przyciskiem **Resume** albo **Process slice**. Jeśli błąd wraca, zmniejsz **Batch size** w **Settings**.

**„Rate limit — job auto-paused. Resume later.”** Zadanie wstrzymało się samo po zbyt wielu odrzuconych wywołaniach. Po chwili kliknij **Resume** w zadaniu, a potem **Process slice** albo **Auto-process**.

**„Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.”** Zadanie czeka na ręczne uruchomienie albo na cron. Kliknij **Process slice** albo **Auto-process**. Żeby zadania szły bez klikania, dodaj adres CRON URL do harmonogramu na serwerze i wywołuj go regularnie.

**„Monthly API budget has been exhausted.”** Osiągnięto miesięczny limit **Budget USD / month**. Otwórz **Settings** i podnieś kwotę albo ustaw 0, żeby zdjąć limit. Nowe tłumaczenia ruszą, gdy zadanie zostanie wznowione.

**„Allow publish is off in Settings.”** Zapis tłumaczeń jest zablokowany. Otwórz **Settings** i włącz **Allow publish / save**. Bez tego przycisk **Process slice** nie zapisze tekstu w sklepie.

**„Not saved because of broken placeholders or HTML: N.”** N wierszy nie zapisano, bo model zmienił placeholder albo znacznik HTML. Otwórz **Review** albo tabelę na **Manual**, popraw propozycję i zapisz ponownie, albo odrzuć wiersz.

**Zadanie się skończyło, ale ma status completed_with_errors.** Część ciągów się nie udała. Na **Jobs** włącz filtr **Failed only**, pobierz **Error CSV** i kliknij **Retry failed**, żeby ponowić błędne ciągi.

**Nie da się cofnąć tłumaczenia.** **Rollback** przywraca tylko tłumaczenia, dla których moduł zapisał kopię przed zmianą. Kopie są w zadaniu. Po odinstalowaniu modułu znikają.

**Tłumaczenie zapisano, ale na stronie widać stary tekst.** Wyczyść cache: **Zaawansowane → Wydajność → Wyczyść cache**. Na formularzach i na stronie International → Translations pamiętaj, że przyciski i pasek tylko wypełniają pola, a zapisuje je przycisk **Save** PrestaShop.

**Przycisków tłumaczenia nie widać przy polach.** Przełączniki są wyłączone. Otwórz **Settings** i włącz odpowiedni przełącznik: **Individual field buttons** lub **Individual field checkboxes** dla formularzy sklepu albo dla International → Translations.

**„Fill the source language field first.”** Pole języka źródłowego jest puste. Wpisz tekst w tym języku i spróbuj ponownie.

**„The source language mail file was not found.”** Dla tego szablonu maila nie ma pliku w języku źródłowym. Wybierz inny **Source locale** w **Settings** albo przetłumacz szablon ręcznie.

**Zadanie po Start job nie rusza.** Start job tylko tworzy zadanie i nie uruchamia go. Otwórz **Jobs** i kliknij **Process slice** albo **Auto-process**.

**Nie przychodzi e-mail o zakończonym zadaniu.** Sprawdź, czy włączono **Email notify on complete**, czy adres w **Notify email** jest poprawny, a puste pole kieruje na e-mail sklepu. Wiadomość przychodzi tylko po zakończeniu zadania. Sprawdź też, czy sklep w ogóle wysyła pocztę w **Zaawansowane → E-mail**.

**Zadania nie da się anulować.** W tej wersji modułu na ekranie zadania nie ma przycisku anulowania. Wstrzymaj zadanie przyciskiem **Pause** i nie wznawiaj go.

**History jest puste albo pokazuje „No requests yet.”** Nie było jeszcze żadnego wywołania DeepSeek. Dashboard również pokaże zera, dopóki nie wykonasz tłumaczenia.

## 6. Dla developera

Ta sekcja opisuje kod modułu. Klucze konfiguracji i nazwy klas są tylko tutaj.

### 6.1 Przegląd

- **Klasa główna:** `myaitranslationsdeepseek` (rozszerza `Module`), plik `myaitranslationsdeepseek.php`.
- **Nazwa techniczna:** `myaitranslationsdeepseek`. Przedrostek kluczy konfiguracji i tabel to `MYAITDS_` i `myaitds_`.
- **Wersja:** 1.2.0.
- **Nazwa na liście modułów:** AI Translations with DeepSeek.
- **Autor w kodzie:** MyPresta.eu. Kategoria: `administration`.
- **Zgodność:** PrestaShop 1.7.0.0 do 99.99.99, `bootstrap = true`, `need_instance = 0`.
- **Zakładka w menu:** klasa `AdminMyaitranslationsdeepseek`, rodzic `AdminInternational` (zapas: `IMPROVE`).

Przepływ danych: ustawienia są czytane przez `MyaitdsConfigService` z `Configuration` (klucze `MYAITDS_*`). Serwisy `MyaitdsTranslateService`, `MyaitdsJobWorker`, `MyaitdsCatalogTranslateService` i kontroler zaplecza wywołują `MyaitdsDeepSeekTranslationProvider`, który wysyła żądanie cURL na `https://api.deepseek.com/chat/completions` (timeout 120 s, połączenie 15 s). Odpowiedź przechodzi przez walidatory (`MyaitdsPlaceholderValidator`, `MyaitdsHtmlValidator`, `MyaitdsPsNativeValidator`) i `MyaitdsQualityScorer`. Zapis trafia przez `MyaitdsTranslationAdapterFactory` do usługi tłumaczeń PrestaShop, a gdy jej brakuje, do tabeli `translation`. Dla modułów klasycznych zapis idzie do `translations/{iso}.php` danego modułu. Wywołania zapisują się w `myaitds_request` i `myaitds_api_log`, a koszty w `myaitds_usage_ledger`. Pamięć tłumaczeń (`myaitds_memory`) pozwala pominąć wywołanie API dla tego samego źródła, języka, modelu i wersji glosariusza.

### 6.2 Pliki

| Plik | Do czego służy |
|---|---|
| `myaitranslationsdeepseek.php` | Klasa główna: instalacja, odinstalowanie, zakładka w menu, hooki zaplecza, przekierowanie `getContent()` do kontrolera. |
| `sql/install.php` | Tworzy 11 tabel (`CREATE TABLE IF NOT EXISTS`). |
| `sql/uninstall.php` | Usuwa 11 tabel (`DROP TABLE IF EXISTS`). |
| `controllers/admin/AdminMyaitranslationsdeepseekController.php` | Kontroler zaplecza: wszystkie zakładki, akcje formularzy, akcje zadań i żądania AJAX. |
| `controllers/front/cron.php` | Kontroler frontu `cron`: przetwarza jedną porcję zadania. |
| `src/Admin/MyaitdsForms.php` | Formularze HelperForm i ich opisy `desc`. |
| `src/Admin/MyaitdsSectionHelp.php` | Tekst pomocy każdej zakładki. |
| `src/Service/MyaitdsConfigService.php` | Odczyt i zapis `MYAITDS_*`, listy modeli, zakresy wartości, klucz API. |
| `src/Service/MyaitdsTranslateService.php` | Tłumaczenie ręczne i z przycisków: pamięć, budżet, walidacja, zapis. |
| `src/Service/MyaitdsBulkJobFactory.php` | Estymacja i tworzenie zadania masowego. |
| `src/Service/MyaitdsCatalogTranslateService.php` | Pola produktów, kategorii i CMS, partie po maks. 100 rekordów. |
| `src/Service/MyaitdsDashboardService.php` | Liczenie pokrycia katalogu (braki i tłumaczenia). |
| `src/Service/MyaitdsRateLimiter.php` | Limit wywołań na minutę, zapis w `var/rate_limit.json`. |
| `src/Job/MyaitdsJobWorker.php` | Przetwarzanie porcji, zapis, snapshoty, kolejka przeglądu, powiadomienie e-mail. |
| `src/Job/MyaitdsJobRepository.php` | Odczyt i zapis zadań oraz ich ciągów. |
| `src/Job/MyaitdsJobStatuses.php` | Stałe statusów zadań i ciągów. |
| `src/Provider/MyaitdsDeepSeekTranslationProvider.php` | Wywołanie API DeepSeek (cURL), obsługa błędów i kodów HTTP. |
| `src/Provider/MyaitdsPromptBuilder.php` | Budowa promptu z tonem, głosem marki i glosariuszem. |
| `src/Provider/MyaitdsProviderFactory.php` | Tworzy dostawcę (obecnie tylko DeepSeek). |
| `src/Provider/MyaitdsTranslationProviderInterface.php` | Interfejs dostawcy tłumaczeń. |
| `src/Adapter/MyaitdsTranslationAdapterInterface.php` | Interfejs dostępu do katalogu PrestaShop. |
| `src/Adapter/MyaitdsAbstractTranslationAdapter.php` | Wspólna logika: sekcje, domeny, zapis, czyszczenie cache. |
| `src/Adapter/MyaitdsFilesystemCatalogueTrait.php` | Skanowanie plików XLF i katalogów tłumaczeń. |
| `src/Adapter/MyaitdsLegacyModuleCatalogue.php` | Odczyt i zapis `translations/{iso}.php` modułów klasycznych. |
| `src/Adapter/MyaitdsTranslationAdapter.php` | Konkretna implementacja adaptera. |
| `src/Adapter/MyaitdsTranslationAdapterFactory.php` | Tworzy adapter. |
| `src/Quality/MyaitdsPlaceholderValidator.php` | Sprawdza placeholdery w tłumaczeniu. |
| `src/Quality/MyaitdsHtmlValidator.php` | Sprawdza znaczniki HTML. |
| `src/Quality/MyaitdsPsNativeValidator.php` | Łączy kontrolę placeholderów i HTML-u. Gdy są dostępne, używa klas PrestaShop (`Validate::isCleanHtml`). |
| `src/Quality/MyaitdsEmailHtmlPipeline.php` | Chroni znaczniki i zmienne w szablonach e-mail przed tłumaczeniem. |
| `src/Quality/MyaitdsQualityScorer.php` | Ocena 0–100, flagi i decyzja o kolejce przeglądu (próg 70). |
| `src/Glossary/MyaitdsGlossaryRepository.php` | Odczyt i zapis glosariusza. Import i eksport CSV są w kontrolerze. |
| `src/Glossary/MyaitdsExcludePatternRepository.php` | Wzorce wykluczeń. |
| `src/Audit/MyaitdsRequestLogRepository.php` | Historia wywołań: zapis, filtry, widok i czyszczenie wg retencji. |
| `src/Audit/MyaitdsApiLogRepository.php` | Log API i jego retencja. |
| `src/Audit/MyaitdsTranslationMemory.php` | Pamięć tłumaczeń (hash źródła, języka, modelu i glosariusza). |
| `src/Audit/MyaitdsUsageLedger.php` | Zużycie i koszty miesięczne, źródło dla budżetu. |
| `src/Audit/MyaitdsSnapshotService.php` | Kopie wartości przed zmianą i cofanie (**Rollback**). |
| `src/Security/MyaitdsApiKeyEncryptor.php` | Szyfrowanie klucza API (AES-256-CBC). |
| `views/templates/admin/configure.tpl` | Szkielet panelu z zakładkami. |
| `views/templates/admin/_partials/*.tpl` | Zawartość zakładek: dashboard, manual, bulk, jobs, review, catalog, glossary, excludes, logs, settings, history-stats. |
| `views/js/admin.js` | Logika zaplecza: zadania, auto-przetwarzanie, formularze. |
| `views/js/admin-help.js` | Okna pomocy przy zakładkach. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Wykresy na **Dashboard**. |
| `views/js/entity-fields.js` | Przyciski i pasek przy polach formularzy sklepu. |
| `views/js/translations-tool.js` | Przyciski i pasek na stronie International → Translations. |
| `views/css/admin.css` | Style panelu i przycisków. |
| `lib/updateChecker.php` | Sprawdzanie wersji u MyPresta i zakładka **Updates**. |
| `translations/*.php` | Tłumaczenia modułu (27 języków, w tym `pl.php`). |
| `var/rate_limit.json` | Stan limitu wywołań na minutę. |
| `logo.png`, `logo.gif` | Logo na liście modułów i w panelu. |

### 6.3 Kontrolery

**Zaplecze:** `AdminMyaitranslationsdeepseekController`, zakładka `AdminMyaitranslationsdeepseek`, rodzic `AdminInternational`. Zakładki wybiera parametr `myaitds_tab`. Dozwolone wartości: `dashboard`, `settings`, `manual`, `bulk`, `jobs`, `glossary`, `excludes`, `logs` (zakładka **History**), `review`, `catalog` i `updates`. Inna wartość otwiera `dashboard`. Kontroler nie definiuje własnych uprawnień, więc obowiązują uprawnienia zakładki ustawione w PrestaShop.

Akcje wysyłane przez formularze (`Tools::isSubmit`): `submitMyaitranslationsdeepseekSettings`, `…Ping` (Test connection), `…AddModel`, `…GlossaryAdd`, `…GlossaryImport`, `…GlossaryExport`, `…ExcludeAdd`, `…BulkPreview`, `…Bulk`, `…ManualFilter`, `…ManualTranslate`, `…SaveReview`, `…Catalog`, `…Dashboard`, `…ClearHistory`.

Akcje przez parametry GET: `job_action` (`process`, `pause`, `resume`, `retry_failed`, `rollback`, `export_errors`; `cancel` jest obsłużona, ale żaden szablon nie tworzy linku do niej), `review_action` (`approve`, `reject`) z `id_review`, `delete_deepseek_model`, `delete_glossary`, `delete_exclude`.

Akcje AJAX (`?controller=AdminMyaitranslationsdeepseek&ajax=1&action=…`), obsługiwane przez metody `displayAjax*`: `HistoryDetail` (szczegóły wiersza historii, parametr `hist_id`), `ProcessJob` (jedna porcja, `id_job`), `JobStatus` (stan zadania), `TranslatePageLines` (linie strony tłumaczeń), `MailSource` (plik źródłowy szablonu maila), `ListDomains` (domeny dla wybranej sekcji).

**Front:** `MyaitranslationsdeepseekCronModuleFrontController` w pliku `controllers/front/cron.php`. Adres ma postać `index.php?fc=module&module=myaitranslationsdeepseek&controller=cron&token=…`. Ustawienia kontrolera: `$ssl = true`, `$ajax = true`. Parametry: `token` (wymagany, porównanie przez `hash_equals` z `MYAITDS_CRON_TOKEN`) i opcjonalny `id_job`. Bez `id_job` moduł bierze pierwsze zadanie w statusie `pending` albo `running` spośród 20 najnowszych. Błędny token zwraca HTTP 403 i JSON `{"ok":false,"error":"Forbidden"}`. Brak zadań zwraca `{"ok":true,"message":"No pending jobs"}`. Porcja zwraca wynik `processSlice`.

### 6.4 Hooki

Zarejestrowane przy instalacji:

- `displayBackOfficeHeader` → `hookDisplayBackOfficeHeader()`: zmienia nazwę zakładki (jeśli wciąż techniczna) i ładuje zasoby zaplecza.
- `actionAdminControllerSetMedia` → `hookActionAdminControllerSetMedia()`: ładuje te same zasoby.

`loadBoAssets()` działa tak: na zakładce `AdminMyaitranslationsdeepseek` dołącza `admin.css`, `admin.js`, `admin-help.js` oraz na **Dashboard** `chart.min.js` i `history-charts.js`. Na stronie `AdminTranslations` dołącza `translations-tool.js`, gdy włączone są przyciski lub pasek dla International → Translations (`MYAITDS_TR_BUTTONS` lub `MYAITDS_TR_BULK`). Na pozostałych stronach back office dołącza `entity-fields.js`, gdy włączone są przyciski lub pasek dla formularzy sklepu (`MYAITDS_ENTITY_BUTTONS` lub `MYAITDS_ENTITY_BULK`). Przez `Media::addJsDef` przekazuje konfigurację `myaitdsTr` i `aitHelpLabels`.

Moduł **nie wystawia** własnych hooków: nie wywołuje `Hook::exec` i nie rejestruje hooków frontu.

Moduł **nie ma** metod `enable()` ani `disable()`. Włączenie i wyłączenie nie wykonuje żadnej akcji modułu. Hooki zdejmuje PrestaShop przy odinstalowaniu.

### 6.5 Nadpisania

Moduł nie ma katalogu `override/` i nie nadpisuje klas ani kontrolerów PrestaShop.

Pliki zapisywane przez moduł: tłumaczenia trafiają przez usługę tłumaczeń PrestaShop (`prestashop.service.translation`), a gdy jej brakuje, do tabeli `translation`. Dla modułów klasycznych (klucze w formacie `<{nazwa}>prestashop`) moduł przepisuje `translations/{iso}.php` tego modułu, najpierw do pliku tymczasowego, a potem przez zmianę nazwy. Czyści cache przez `Tools::clearCache()`. Zapisuje też `var/rate_limit.json` oraz wartości `update_<moduł>`, `updatev_<moduł>` i `mypresta_updates` w `Configuration`.

### 6.6 Baza

Tabele mają prefiks sklepu (`_DB_PREFIX_`). Wszystkie są tworzone w silniku `_MYSQL_ENGINE_` z kodowaniem `utf8mb4_unicode_ci`.

| Tabela | Zawartość |
|---|---|
| `myaitds_glossary` | Terminy glosariusza: `id_shop`, `source_term`, `target_locale`, `target_term`, `do_not_translate`, daty. Indeks `idx_shop_locale`. |
| `myaitds_exclude_pattern` | Wzorce wykluczeń: `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`, `date_add`. |
| `myaitds_job` | Zadania: `uuid` (unikalny), `status`, `source_locale`, `target_locales`, `scope_json`, `policy_json`, `dry_run`, liczniki `items_*`, tokeny, `cost_usd_estimate` i `cost_usd_actual`, `id_employee`, `error_summary`, `started_at`, `finished_at`. |
| `myaitds_job_item` | Ciągi zadania: `id_myaitds_job`, `domain`, `translation_key`, `theme`, `target_locale`, `source_text`, `previous_translation`, `new_translation`, `status`, `skip_reason`, `error_message`, `tokens_used`, `source_hash`, `validated_ok`, `validation_warnings`. |
| `myaitds_memory` | Pamięć tłumaczeń: `memory_hash` (unikalny), `source_text`, `target_locale`, `translation`, `model`, `hit_count`. |
| `myaitds_usage_ledger` | Zużycie dzienne: `usage_date`, `id_myaitds_job`, `model`, tokeny, `cost_usd`. Źródło dla budżetu miesięcznego. |
| `myaitds_snapshot` | Wartości sprzed zmiany: `id_myaitds_job`, `id_myaitds_job_item`, `locale`, `domain`, `translation_key`, `theme`, `value_before`. Źródło dla **Rollback**. |
| `myaitds_api_log` | Log API: `id_myaitds_job`, `level`, `provider`, `http_code`, `message`, `context_json`. Czyszczony wg `MYAITDS_LOG_RETENTION_DAYS`. |
| `myaitds_request` | Historia wywołań (**History**): typ, status, model, języki, kod HTTP, czas, tokeny, koszt, `prompt`, `reply`, `error_message`. Czyszczona wg retencji. |
| `myaitds_review` | Kolejka przeglądu: `id_myaitds_job_item`, `status` (`needs_review`, `approved`, `rejected`), `quality_score`, `flags_json`, `id_employee`. |
| `myaitds_catalog_item` | Tworzona przy instalacji, ale żaden kod nie zapisuje do niej ani z niej nie czyta. |

Instalacja tworzy tabele wyłącznie przez `CREATE TABLE IF NOT EXISTS`. Moduł nie dopisuje kolumn przy wejściu na stronę (brak `ALTER TABLE` w kodzie).

Odinstalowanie usuwa wszystkie 11 tabel. Ponowna instalacja tworzy je puste.

### 6.7 Klucze i tłumaczenia

**Klucze konfiguracji** (prefiks `MYAITDS_`) i wartości startowe z `installDefaults()`:

| Klucz | Wartość startowa | Uwagi |
|---|---|---|
| `API_KEY_ENC` | `''` | Klucz zaszyfrowany AES-256-CBC, klucz szyfrowania z `_COOKIE_KEY_`. |
| `MODEL` | `deepseek-flash` | Model wywołania. |
| `EXTRA_MODELS` | `''` | Dodane identyfikatory modeli (**Add a DeepSeek model**). |
| `PROVIDER` | `deepseek` | Jedyny dostawca. Brak pola w panelu. |
| `TONE` | `formal` | `formal`, `casual`, `brand`. |
| `CUSTOM_VOICE` | `''` | Tekst głosu marki. |
| `BATCH_SIZE` | `25` | Zakres 1–100. |
| `MONTHLY_BUDGET` | `0` | 0 = bez limitu. |
| `SOURCE_LOCALE` | `''` | Pusty oznacza, że ekran podaje źródło. Fallback w kodzie: `en-US`. |
| `TEMPERATURE` | `0.2` | Zakres 0–1. |
| `DRY_RUN_SAMPLE` | `10` | Zakres 1–50. |
| `RATE_LIMIT_PER_MIN` | `60` | Pole w formularzu nazywa się `MYAITDS_RATE_LIMIT`. 0 wyłącza limit. |
| `LOG_RETENTION_DAYS` | `30` | Minimum 1. |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` | Przełącznik e-maila. |
| `NOTIFY_EMAIL` | `''` | Pusty = `PS_SHOP_EMAIL`. |
| `PERM_ALLOW_PUBLISH` | `1` | Blokuje zapis z **Manual**, zadań i **Catalog**. |
| `ENTITY_FIELD_BUTTONS`, `ENTITY_BULK` | `1` | Przyciski i pasek przy polach formularzy sklepu. |
| `TR_FIELD_BUTTONS`, `TR_BULK` | `1` | Przyciski i pasek na International → Translations. |
| `MAX_TOKENS` | `0` | 0 = domyślny limit DeepSeek. |
| `CRON_TOKEN` | losowe 16 bajtów (hex) | Token adresu cron. |

Przy odinstalowaniu usuwane są powyższe klucze oraz `DEEPL_API_KEY` i `CLAUDE_API_KEY`, których moduł już nie używa.

**Teksty niezłączone z `$this->l()`.** Opisy pól i pomocy przechodzą przez `l()` w domenach `myaitdsforms` (`MyaitdsForms`) i `sectionhelp` (`MyaitdsSectionHelp`). Etykiety JS trafiają do `Media::addJsDef` przez `translationClientConfig()`. Temat i treść e-maila o zakończeniu zadania są po angielsku w `MyaitdsJobWorker::notifyComplete()` i nie przechodzą przez `l()`. Komunikaty wyświetlane przez `$this->module->l()` w kontrolerze mają domenę `adminmyaitranslationsdeepseekcontroller`.

**Dodanie języka:** dodaj plik `translations/{iso}.php` według wzoru istniejących plików (na przykład `translations/pl.php`). Plik z kodem języka dopasowanym do ISO sklepu jest wczytywany przez PrestaShop.

**Źródło opisów pól:** `MyaitdsForms::help()` (klucz `desc` każdego pola) oraz `MyaitdsSectionHelp::pages()` i `brief()` (tekst pomocy zakładek).

### 6.8 Rozszerzanie

- **Motyw:** nie ma czego nadpisać. Moduł nie renderuje szablonów frontu.
- **Szablony zaplecza:** `views/templates/admin/`. Zmiany w plikach modułu znikną przy aktualizacji.
- **Nowe modele DeepSeek:** bez zmiany kodu, przez **Add a DeepSeek model** (`EXTRA_MODELS`).
- **Nowy dostawca:** implementacja `MyaitdsTranslationProviderInterface` i wpis w `MyaitdsProviderFactory`.
- **Próg kolejki przeglądu:** 70 punktów w `MyaitdsQualityScorer::score()`, zapisany w kodzie.
- **Glosariusz i wykluczenia:** zmieniane w panelu, bez kodu.

## 7. Pomoc

Strona modułu: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-deepseek.html

Zaloguj się na konto klienta na mypresta.eu, przejdź do kontaktu i wybierz temat **Support for paid modules**. Formularz podaje, że dla płatnych modułów logowanie jest wymagane. Po zalogowaniu wybierz ten moduł z historii zakupów.
