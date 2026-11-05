---
title: "AI Translations with Claude - dokumentacja i instrukcja użytkownika"
description: "Konfiguracja i rozwiązywanie problemów dla osób, które mają już zainstalowany moduł AI Translations with Claude."
sidebar:
  label: "AI Translations with Claude - dokumentacja i instrukcja użytkownika"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł AI Translations with Claude na MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-claude.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ai-artificial-intelligence/ai-translations-with-claude/)
>
> ---


## 1. Wymagania

Moduł działa w PrestaShop 1.7.0.0 i nowszych, w tym w PrestaShop 8 i 9.

- **PrestaShop:** 1.7.0.0 lub nowszy.
- **PHP:** 5.6 lub nowszy.
- **Rozszerzenia PHP:** cURL, OpenSSL, SimpleXML i mbstring.
- **Inne moduły:** moduł nie wymaga żadnego innego modułu.
- **Poza sklepem:** konto Anthropic oraz klucz API, który znajdziesz na stronie https://console.anthropic.com/settings/keys. Serwer sklepu musi mieć możliwość połączenia się z adresem `https://api.anthropic.com/v1/messages`.
- **Opcjonalnie:** zadanie w harmonogramie serwera, które otwiera adres cron z zakładki **Settings**. Bez niego porcje zadań uruchamiasz ręcznie na zakładce **Jobs**.
- **Duże katalogi:** jeśli domena ma tysiące tekstów, to będzie wiele wywołań API. Zadanie jest dzielone na porcje o wielkości **Batch size**. Zanim cokolwiek uruchomisz, kliknij **Estimate** na zakładce **Bulk**, żeby zobaczyć szacunek.
- Sklep musi mieć co najmniej dwa języki. Przy jednym języku back office pokazuje komunikat **The shop needs at least two languages.** i nie ma wtedy nic do tłumaczenia.

## 2. Instalacja

1. Otwórz **Modules**, a potem **Module Manager**. Wybierz **Upload a module**, wgraj plik ZIP i kliknij **Install** przy module **AI Translations with Claude**.
2. Po instalacji moduł pojawi się w menu **International**.
3. Instalacja nie czyści cache sklepu. Cache czyści dopiero moduł, gdy zapisze tłumaczenie.

Następnie otwórz **AI Translations with Claude**, przejdź do **Settings** i wklej klucz Claude. Dopóki klucz nie zostanie zapisany, każda strona modułu pokazuje komunikat **No Claude API key.** oraz odnośnik **Open Settings**.

**Odinstalowanie.** W **Module Manager** kliknij **Uninstall** i potwierdź pytanie **Delete this module and its data (jobs, glossary, cache)?**

- Pozycja menu znika. Usuwane są zadania, glosariusz, wykluczenia, historia wywołań, kolejka **Review**, kopie do przywrócenia, rejestr kosztów oraz ustawienia modułu, a wraz z nimi klucz API.
- Zostają teksty, które moduł już zapisał w sklepie: tłumaczenia katalogu oraz pliki tłumaczeń modułów klasycznych. Zostaje też wybór dotyczący sprawdzania aktualizacji.
- Ponowna instalacja nie przywraca usuniętych zadań, glosariusza ani historii. Ustawia wartości domyślne i tworzy nowy adres cron.

## 3. Konfiguracja i codzienna praca

Cały moduł mieści się na jednej stronie. Otwórz **International**, a potem **AI Translations with Claude**. Zakładki to kolejno: **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** i **Settings**. Na końcu paska znajduje się **Updates**. Przycisk **Help** otwiera panel pomocy dla zakładki, na której aktualnie jesteś.

Nazwy przycisków i pól w tej instrukcji pochodzą z angielskiej wersji back office. W innym języku panelu zobaczysz tłumaczenie tej samej opcji.

**Od pierwszego kliknięcia do zapisanego tłumaczenia**

Pracę zaczyna pracownik w back office. Klient sklepu nie uruchamia tłumaczeń.

1. **Settings.** Wklej klucz Claude, wybierz model i język źródłowy, kliknij **Test connection**, a potem **Save**. Bez klucza żadne narzędzie nie wyśle tekstu do Claude.
2. **Wybierz sposób pracy.**
   - Kilka tekstów albo jedna domena, z możliwością sprawdzenia przed zapisem: **Manual** (3.3).
   - Duża domena, motyw lub moduł: **Bulk**, a potem zadanie na **Jobs** (3.4 i 3.5).
   - Pola produktów, kategorii i stron CMS: **Catalog**, po maksymalnie 100 rekordów naraz (3.7).
   - Pojedyncze pola na stronie **International → Translations** (3.12) oraz w formularzach produktu, kategorii i CMS (3.13).
3. **Sprawdzenie jakości.** Każdy przetłumaczony tekst jest sprawdzany pod kątem placeholderów i znaczników HTML. Tekst, który nie przejdzie tego sprawdzenia, nie zostaje zapisany. Do **Review** trafia tekst z oceną poniżej 70, tekst ponad dwa i pół raza dłuższy od źródła oraz tekst, w którym zostały angielskie słowa, takie jak *the*, *and*, *with*, *your* czy *please*.
4. **Zapis.**
   - **Manual:** przycisk **Translate selected (review)** niczego nie zapisuje, dopóki nie klikniesz **Save approved**. Przycisk **Save now (skip review)** zapisuje od razu te wiersze, które przeszły sprawdzenie.
   - **Bulk:** zadanie czeka na zakładce **Jobs**. Zapis następuje po kliknięciu **Process slice**, po **Auto-process** albo po wywołaniu adresu cron. Zadanie z włączonym **Dry-run job** niczego nie zapisuje.
   - **Catalog:** poprawne wiersze są od razu zapisywane w języku docelowym.
   - **International → Translations** i formularze sklepu: przyciski tylko wypełniają pola. Zapisuje je dopiero przycisk **Save** w PrestaShop.
   - Gdy opcja **Allow publish / save** jest wyłączona, ekrany **Manual**, **Bulk** i **Catalog** nie zapisują tekstu w sklepie.
5. **Koniec zadania.** Na zakładce **Jobs** status zmienia się na **completed** albo **completed_with_errors**. Wiersze na **Review** znikają z listy po kliknięciu **Approve** lub **Reject**. Zakładka **Catalog** podaje, ile wierszy zapisano, a ile się nie udało.

### 3.1. Konfiguracja modułu

Otwórz **Modules**, a potem **Module Manager**, znajdź **AI Translations with Claude** i kliknij **Configure**. Otworzy się **Dashboard**. Przejdź wtedy do **Settings**.

Przyciski **Save** i **Test connection** znajdują się na dole formularza. Zapisanie formularza nie uruchamia tłumaczenia i nie zmienia tekstów, które są już zapisane w sklepie.

![Ustawienia, angielski back office. Góra formularza: Claude API key, Model, Add a Claude model, Tone i Source locale.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-settings.webp)

**Połączenie**

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Claude API key** | puste | Tajny klucz, który sklep wysyła do Claude. Wklej klucz z https://console.anthropic.com/settings/keys. Jeśli klucz jest już zapisany, zostaw to pole puste, a zapisany klucz pozostanie bez zmian. Wpisana wartość zastępuje zapisany klucz, a puste pole go nie usuwa. Gdy klucz jest zapisany, tekst pomocy pokazuje **Key saved:** i zamaskowaną wersję klucza. |
| **Model** | claude-haiku-4-5 | Model Claude, który pisze tłumaczenia. Wbudowane modele zawsze są na liście: claude-haiku-4-5, claude-sonnet-4-5 i claude-opus-4-5. Kolejne tłumaczenie używa wybranego modelu. Jeśli Twoje konto nie ma dostępu do modelu, wywołanie kończy się błędem, a szczegóły znajdziesz na zakładce **History**. |
| **Add a Claude model** | puste | Wpisz dokładny identyfikator modelu z konta Anthropic i kliknij **Add model**. Nowy identyfikator pojawi się w polu **Model** i od razu stanie się aktywnym modelem. Przycisk **Remove** usuwa tylko modele dodane tutaj. Wbudowanych modeli nie da się usunąć. |

Możliwe komunikaty: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example claude-haiku-4-5.**, **Built-in models cannot be removed.**

**Ton i źródło**

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Tone** | Formal | Dodaje do każdego zapytania wskazówkę dotyczącą stylu. **Formal** sprawdza się w tekstach sklepu i back office, **Casual** daje lżejszy, swobodniejszy ton, a **Brand** działa razem z polem **Brand voice**. Nowe tłumaczenia powstają w wybranym stylu. Tłumaczenia, które już istnieją, nie zmieniają się, dopóki ich nie przetłumaczysz ponownie. |
| **Brand voice** | puste | Pole widoczne tylko wtedy, gdy **Tone** ma wartość **Brand**. Wpisz kilka zdań o tym, jak ma brzmieć Twój sklep. Tekst trafi do kolejnych zapytań. Puste pole oznacza brak dodatkowych wskazówek dotyczących głosu marki. Nie przepisuje tłumaczeń, które już są zapisane. |
| **Source locale** | puste | Język, który model traktuje jako oryginał. Jeśli pozostawisz pustą wartość (kreska na liście), źródłem będzie ekran, który tłumaczysz. Najlepiej wybrać locale, w którym napisano katalogi, zwykle en-US. Opcje **Manual**, **Bulk** i ikony na **International → Translations** używają tego locale jako źródła. Domyślny język sklepu się nie zmienia. |
| **Individual field buttons — shop forms** | Yes | Przycisk przy każdym polu wielojęzycznym w formularzach sklepu: produktów, kategorii, CMS i pozostałych formularzach back office. Przycisk tłumaczy tylko to jedno pole. Wybór **No** ukrywa te przyciski w całym sklepie. Zapisane tłumaczenia nie zmieniają się. |
| **Individual field checkboxes — shop forms** | Yes | Pole wyboru przy każdym takim polu oraz pasek, który tłumaczy tylko zaznaczone pola. Wybór **No** ukrywa pola wyboru i pasek. Przyciski z opcji powyżej mają osobny przełącznik. |
| **Individual field buttons — International → Translations** | Yes | Przycisk przy każdym polu na stronie **International → Translations**. Wybór **No** ukrywa te przyciski. Nie ma to wpływu na formularze sklepu. Jedno kliknięcie wypełnia pole, a stronę zapisuje przycisk **Save** w PrestaShop. |
| **Individual field checkboxes — International → Translations** | Yes | Pola wyboru i pasek na stronie **International → Translations**. Wybór **No** je ukrywa. Nie ma to wpływu na formularze sklepu. |


![Ustawienia, angielski back office. Dół formularza: limity, poczta, adres cron, Test connection i Save.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-settings-limits.webp)

**Limity**

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Batch size** | 25 | Ile tekstów trafia do jednego wywołania API. Przy pierwszym uruchomieniu ustaw wartość od 10 do 25. Wartość musi mieścić się w przedziale od 1 do 100. Większa porcja oznacza mniej wywołań, a całe zadanie kończy się szybciej. Przy błędzie moduł ponawia większą porcję. |
| **Dry-run sample** | 10 | Ile przykładowych tekstów pokaże **Estimate** przed uruchomieniem zadania zbiorczego. Wartość musi mieścić się w przedziale od 1 do 50. **Estimate** nie zapisuje żadnych tłumaczeń. |
| **Max tokens (0 = default)** | 0 | Limit długości jednej odpowiedzi. Wartość 0 oznacza limit 4096 tokenów. Ustaw własną liczbę, gdy odpowiedzi są ucinane albo gdy chcesz, żeby były krótsze. Limit dotyczy tylko kolejnych wywołań. Tłumaczeń, które już są zapisane, nic nie skraca. |
| **Budget USD / month** | 0 | Miesięczny limit w dolarach amerykańskich, liczony na podstawie rejestru zużycia. Wartość 0 oznacza brak limitu. Gdy rejestr osiągnie tę kwotę, nowe tłumaczenia się zatrzymają. Zapisane już teksty pozostają w sklepie. |
| **Rate limit / min** | 60 | Ile wywołań API sklep może rozpocząć w ciągu minuty. Wartość 0 wyłącza ten lokalny limit. Wywołania ponad limit są pomijane i pojawiają się na **History**. Claude może mimo to stosować własny limit. |
| **Log retention days** | 30 | Ile dni przechowywać wiersze na zakładce **History**. Minimum to 1. Starsze wiersze są usuwane. Ta wartość nie usuwa zadań, glosariusza ani zapisanych tłumaczeń. |
| **Temperature** | 0.2 | Jak swobodnie model może przeformułować zdania. Wartość około 0.2 trzyma tłumaczenie blisko oryginału. Wartości bliższe 1 zmieniają zdania mocniej. Wartość musi mieścić się w przedziale od 0 do 1. Placeholdery i HTML są sprawdzane dopiero po tłumaczeniu. Wbudowane modele dostają tę wartość. Modele, które dodasz, a które nie są Claude Haiku, Sonnet ani Opus w wersjach 4.0, 4.1, 4.5 lub 4.6, tej wartości nie dostają, więc to pole nie ma na nie wpływu. |
| **Allow publish / save** | Yes | Czy moduł może zapisywać tłumaczenia w PrestaShop. Wybór **No** blokuje zapis na **Manual**, w zadaniach zbiorczych i na **Catalog**. Przyciski na stronie tłumaczeń i w formularzach sklepu nadal tylko wypełniają pola. Przycisk **Save** w PrestaShop działa osobno. |

Po kliknięciu **Save** zobaczysz jeden z komunikatów:

- **Settings saved. No translation was started.** Ustawienia są zapisane, a nic nie zostało przetłumaczone.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** Wklej klucz w polu **Claude API key** i kliknij **Save** jeszcze raz.

**Poczta i cron**

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Email notify on complete** | No | Wysyła jednego e-maila, gdy zadanie zbiorcze się zakończy. Samo zadanie wykonuje się niezależnie od tej opcji, a włączenie decyduje tylko o wysyłce wiadomości. |
| **Notify email** | puste | Adres, na który przychodzi ten e-mail. Pole działa tylko przy włączonym przełączniku powyżej. Sam zapis adresu nie wysyła żadnej wiadomości. |
| **CRON URL** | adres z tokenem | Tajny adres, pod którym serwer może przetworzyć jedną porcję czekającego zadania. Wklej go do harmonogramu zadań serwera i nie publikuj go. Każdy, kto zna ten adres, może uruchomić porcję. Samo otwarcie **Settings** nie uruchamia żadnego zadania. |

**Test connection** sprawdza klucz i model jednym krótkim zapytaniem. Nic nie tłumaczy i nic nie zapisuje.

- **Connection OK (N ms). No translation was started.** Połączenie działa.
- **Connection was not made. Nothing was translated.** oraz zaraz potem powód. Sprawdź klucz i model. Szczegóły znajdziesz na zakładce **History**.

Na start wystarczy: wkleić klucz, wybrać model i locale źródłowe, kliknąć **Test connection**, a potem **Save**. Pozostałe liczby zostaw na wartościach domyślnych, dopóki zadania działają bez problemów.

### 3.2. Dashboard

Otwórz zakładkę **Dashboard**. Pokazuje ona, ile tekstów w katalogu jeszcze brakuje, a poniżej zużycie Claude przedstawione w kartach, wykresach i w liście dziesięciu ostatnich zapytań. Ta strona niczego nie tłumaczy i nie zmienia tekstów.

![Dashboard, angielski back office. Pokrycie dla jednego locale, linia cron i filtry historii.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-dashboard.webp)

**Pokrycie**

- **Locale:** locale sklepu, dla którego liczone są brakujące teksty.
- **Show:** przelicza tabelę od nowa dla wybranego locale.
- Kolumny: **Section**, **Total**, **Missing**, **Done** i pasek postępu. Sekcje to **Back office**, **Themes**, **Installed modules**, **Emails** i **Others**. Kolumna **Missing** pokazuje liczbę tekstów, które nie mają tłumaczenia w danym locale.
- Pod tabelą linia **CRON** pokazuje ten sam adres co pole **CRON URL** w **Settings**.
- Pusta tabela oznacza, że sklep nie ma jeszcze katalogu dla tego locale. Utwórz go na stronie **International → Translations**.

Po kliknięciu **Show** zobaczysz komunikat **Coverage for {locale}. This page only counts strings. Nothing was translated.**

**Zużycie**

- Gotowe zakresy czasu: **Today**, **7 days**, **30 days**, **This month** i **All time**.
- Filtry: **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** oraz **Prompt or reply contains**. Po ustawieniu filtrów kliknij **Filter**.
- Karty: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** i **Estimated cost**. Szacowany koszt to lokalne wyliczenie, a nie faktura od Anthropic.
- Wykresy: **Requests and errors**, **Tokens sent and received** i **Requests by model**. Pod nimi znajdują się grupy **By day**, **By model**, **By type**, **By language** i **By employee** z kolumnami **Group**, **Calls**, **Sent**, **Received** i **Total**. Pusta grupa wyświetla komunikat **No requests in this range.**
- **Latest prompts** pokazuje dziesięć ostatnich wywołań. Przycisk **View** otwiera prompt i odpowiedź. Przycisk **See all** przenosi do **History** (3.10). Jeśli lista jest pusta, zobaczysz **No requests yet.**

Filtrowanie nie kasuje historii i nie zmienia tłumaczeń.

Jeśli w sekcji brakuje większości tekstów, otwórz **Manual** i przetłumacz kilka z nich albo **Bulk** i przetłumacz całą domenę.

### 3.3. Manual

Otwórz zakładkę **Manual**. Służy do tłumaczenia jednej domeny albo jednego modułu klasycznego, zwykle po kilkadziesiąt tekstów naraz. Samo filtrowanie niczego nie zapisuje.

![Manual, angielskie zaplecze. Section, Source, Target, Domain, Only empty i Search.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-manual.webp)

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Section** | Back office | Który katalog jest czytany: **Back office**, **Themes**, **Installed modules**, **Emails** albo **Others**. Zmiana sekcji przeładowuje stronę i pokazuje tylko pola tej sekcji. Claude nie jest w tym momencie wywoływany. |
| **Theme** | puste | Widoczne tylko przy sekcji **Themes**. Ogranicza listę do jednego motywu. |
| **Module** | puste | Widoczne tylko przy sekcji **Installed modules**. Ogranicza listę do jednego modułu. Moduł klasyczny bez domeny wczytuje wszystkie teksty tego modułu. |
| **Domain** | puste | Ten sam podział, który widzisz na **International → Translations**. Wybierz domenę i kliknij **Filter**. Pole jest ukryte przy module klasycznym i przy sekcji, która nie ma domen. |
| **Source** | **Source locale** z **Settings** albo en-US | Język, z którego pobierane są teksty. Wybierz język, który ma już dobre tłumaczenie. |
| **Target** | pierwszy język na liście | Język, który chcesz uzupełnić. Musi być dodany w **International → Localization → Languages**. |
| **Only empty** | Yes | Pokazuje tylko teksty bez tłumaczenia. Po wyłączeniu widoczne są wszystkie teksty. Zapisane tłumaczenia nie są kasowane. |
| **Search** | puste | Zostawia tylko teksty źródłowe, które zawierają wpisane słowo. |

Kroki:

1. Ustaw **Section**, **Source** i **Target**.
2. Przy sekcji **Themes** wybierz **Theme**. Przy sekcji **Installed modules** wybierz **Module**.
3. Kliknij **Filter**. Lista **Domain** się odświeży. Wybierz domenę i kliknij **Filter** jeszcze raz. Przy module klasycznym pomiń domenę, bo **Filter** wczyta wtedy wszystkie teksty modułu.
4. Zaznacz wiersze, które chcesz przetłumaczyć. Przyciski **Check all** i **Uncheck all** zaznaczają albo odznaczają całą listę.
5. Kliknij **Translate selected (review)**. Otworzy się tabela **Review before save** z kolumnami **Source**, **AI proposal** i **Warnings**. Odznacz wiersze, których nie chcesz zapisywać. Jeśli propozycja wymaga poprawki, edytuj ją bezpośrednio w polu. Na końcu kliknij **Save approved**.
6. Możesz też zaznaczyć **Save now (skip review)** przed tłumaczeniem. Wtedy poprawne wiersze zapisują się od razu, bez tabeli recenzji.

Kolumny listy tekstów to **Source**, **Current** i **Status** (**empty** albo **filled**).

Komunikaty:

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.**
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** Ten komunikat dotyczy listy modułu klasycznego.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to Claude.**
- **No strings match this filter. Nothing was sent to Claude.**
- **No strings match this filter. Turn off Only empty, or this module has no classic strings. Nothing was sent to Claude.**
- **Nothing was translated. Choose a domain, then press Filter to load the strings.**
- **Nothing was translated. Pick a theme, then press Filter.**
- **Nothing was translated. Pick a module, then press Filter.**
- **Nothing was translated. Tick at least one row.**
- **Nothing was translated. There is no Claude API key. Open Settings and paste the key.**
- **Review is ready. Nothing is saved until you press Save approved.**
- **Saved. The approved strings were written for the target language.**
- **Saved N. Only the ticked rows were written.**
- **Nothing was saved. Tick OK on the rows you want to keep.**
- **Not saved because of broken placeholders or HTML: N.** Te wiersze zostały pominięte. Popraw placeholdery i tagi tak, aby zgadzały się z oryginałem, a następnie zapisz jeszcze raz.
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.**

Zmiana sekcji pokazuje też krótką informację, na przykład **Section is Back office. Theme and module are not used.**, razem z komunikatem **Nothing was sent to Claude.** Ten sam układ obowiązuje dla sekcji **Themes**, **Installed modules**, **Emails** i **Others**.

### 3.4. Bulk

Otwórz zakładkę **Bulk**. Tworzy ona jedno zadanie obejmujące wiele domen i języków. Przycisk **Estimate** niczego nie zapisuje. Przycisk **Start job** dodaje wiersz na zakładkę **Jobs**. Nic nie zostanie zapisane, dopóki zadanie nie zostanie przetworzone i opcja **Allow publish / save** nie jest włączona.

![Bulk, angielski back office. Section, Source, Targets, Domains, Policy i Dry-run job.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-bulk.webp)

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Section** | Back office | Który katalog czyta zadanie. Dostępne wybory są takie same jak na **Manual**. |
| **Theme** / **Module** | puste | Widoczne tylko przy pasującej sekcji, tak samo jak na **Manual**. |
| **Source** | **Source locale** z **Settings** albo en-US | Język traktowany jako oryginał. Każdy język docelowy jest tłumaczony z tego języka. |
| **Targets** | brak | Jeden lub więcej języków do uzupełnienia. Aby zaznaczyć kilka, przytrzymaj Ctrl (na Macu Cmd). Zwykłe kliknięcie zastępuje dotychczasowe zaznaczenie. |
| **Domains** | brak | Domeny, które trafią do zadania. Przytrzymaj Ctrl lub Cmd, żeby zaznaczyć kilka. Jeśli nie zaznaczysz żadnej, zadanie obejmie wszystkie domeny wybranej sekcji. |
| **Policy** | Fill empty | **Fill empty** wysyła tylko teksty bez tłumaczenia. **Overwrite all** wysyła wszystkie teksty, także te, które już mają tłumaczenie, i może je zastąpić. **Outdated if equals source** wysyła tylko te teksty, których tłumaczenie jest identyczne z oryginałem. |
| **Dry-run job** | No | Claude i tak pracuje, a zadanie pojawia się na **Jobs**, ale odpowiedzi nie trafiają do sklepu. |

Kroki:

1. Wybierz sekcję, źródło, języki docelowe, domeny i politykę.
2. Kliknij **Estimate**. Strona pokaże **Estimate**, liczbę tekstów, szacunkową liczbę tokenów, szacunkowy koszt oraz **Sample**.
3. Jeśli szacunek Ci odpowiada, kliknij **Start job**. Otworzy się zakładka **Jobs** z nowym zadaniem.
4. Przetwórz zadanie na zakładce **Jobs** (3.5) albo zostaw je do wykonania przez adres cron.

Komunikaty:

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to Claude and nothing was saved.**
- **Job #N is waiting (N strings, est. $X). It has not run yet.**
- **Nothing was started. Select at least one target language.**
- **Nothing was started. Pick a theme.**
- **Nothing was started. Pick a module.**
- **Nothing was started. There is no Claude API key. Open Settings and paste the key. No job was created.**

### 3.5. Jobs

Otwórz zakładkę **Jobs**. Każdy wiersz to jedno uruchomienie zadania z **Bulk**.

![Jobs, angielski back office. Lista zadań. W tym sklepie nie ma jeszcze zadań.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-jobs.webp)

Kolumny: **#**, **Status**, **Locales** (najpierw źródło, potem języki docelowe), **Progress** (zrobione / łącznie), **Cost**, **Employee**, **Date** i **Open**. Jeśli lista jest pusta, zobaczysz **No jobs yet.**

Statusy zadania, tak jak są wyświetlane:

- `pending` - zadanie czeka. Nie uruchamia się samo.
- `running` - zadanie jest w toku.
- `paused` - zadanie jest wstrzymane, dopóki go nie wznowisz.
- `cancelled` - zadanie zostało zatrzymane. Teksty, które jeszcze czekały, nie zostały przetłumaczone.
- `completed` - wszystkie teksty zostały przetworzone bez błędów.
- `completed_with_errors` - zadanie się zakończyło, ale część tekstów nie przeszła.
- `failed` - zadanie zakończyło się błędem.

**Ekran zadania**

Po kliknięciu **Open** zobaczysz **Job #N**, status, postęp (zrobione / łącznie), liczbę **failed** i **skipped**, koszt, numer pracownika oraz etykietę **dry-run**, jeśli zadanie jest przebiegiem próbnym. Pasek postępu odświeża się sam, dopóki zadanie jest otwarte. Tabela pod spodem ma kolumny **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** i **Error**.

Statusy wierszy: `pending`, `processing`, `done`, `failed`, `skipped` (tekst został pominięty przez wykluczenie albo był już przetłumaczony) oraz `rolled_back`.

Przyciski:

- **Process slice** - przetwarza jedną porcję o wielkości **Batch size** i zatrzymuje się. Komunikat: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** Jeśli nie ma już nic do zrobienia: **The job has no more strings waiting.**
- **Auto-process** - powtarza porcje, aż zadanie się skończy albo zatrzyma je błąd. Działa w przeglądarce, więc karta musi pozostać otwarta. Zamknięcie karty przerywa pętlę. Zadanie nie przepada i możesz je dokończyć przyciskiem **Process slice** albo przez adres cron.
- **Pause** - komunikat: **Job paused. It will not translate more strings until you resume it.**
- **Resume** - komunikat: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.**
- **Retry failed** - teksty z błędem wracają do oczekiwania, a zadanie znowu czeka. Komunikat: **Retried N failed items.**
- **Rollback** - pyta **Roll back this job?** i przywraca poprzednie tłumaczenie tam, gdzie moduł zapisał kopię przed zmianą. Komunikat: **Rollback: restored N translations.**
- **Error CSV** - pobiera wiersze z błędem. Kolumny: id, domain, locale, source, error.
- **Failed only** - pokazuje tylko wiersze z błędem.
- **Review queue** - otwiera zakładkę **Review** (3.6).

Na ekranie zadania nie ma przycisku Cancel. Żeby zatrzymać dalszą pracę, użyj przycisku **Pause**.

**Automatyczna pauza**

Jeśli Claude odrzuca wywołania z powodu limitu częstotliwości, zadanie wstrzymuje się samo. Komunikat błędu to **Rate limit — job auto-paused. Resume later.** Odczekaj chwilę, a potem kliknij **Resume**. Opcja **Rate limit / min** w **Settings** zmniejsza liczbę wywołań, które sklep może rozpocząć w ciągu minuty.

Inne komunikaty na tym ekranie:

- **Nothing was translated.** i zaraz potem **No Claude API key. Nothing was translated.** Wklej klucz w **Settings**.
- **Allow publish is off in Settings.** Zadanie, które nie jest przebiegiem próbnym, nie ruszy, dopóki nie włączysz **Allow publish / save**.
- **Monthly API budget has been exhausted.** Podnieś **Budget USD / month** albo ustaw 0.

### 3.6. Review

Otwórz zakładkę **Review** albo kliknij **Review queue** przy zadaniu. Nagłówek strony to **Needs-review queue (quality score / flags).** Lista pokazuje najnowsze wiersze (do 100), które nie przeszły automatycznego sprawdzenia jakości.

![Review, angielski back office. Kolejka do sprawdzenia jest pusta.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-review.webp)

Kolumny: **ID**, **Score**, **Domain**, **Source**, **AI**, **Flags**, a następnie **Approve** i **Reject**. Jeśli nie ma nic do sprawdzenia, zobaczysz **The queue is empty.**

Jak czytać wiersz:

- **Score** to wynik od 0 do 100. Wiersze poniżej 70 trafiają do kolejki.
- **Flags** to znaczniki problemów:
  - `validation_failed` - placeholdery lub HTML nie przeszły sprawdzenia.
  - `warning` - drobniejsza uwaga ze sprawdzenia.
  - `length_explosion` - tłumaczenie jest ponad dwa i pół raza dłuższe od oryginału.
  - `too_short` - tłumaczenie jest wyraźnie krótsze od dłuższego oryginału.
  - `possible_untranslated` - w tłumaczeniu zostały angielskie słowa, takie jak *the*, *and*, *with*, *your* czy *please*.
- **Source** to oryginał, a **AI** to propozycja modelu.

Przyciski **Approve** i **Reject** zmieniają tylko status wiersza. Pojawi się komunikat **Review updated.**, a wiersz zniknie z listy. Ta czynność nie wpisuje tekstu do sklepu i nie zmienia reszty domeny.

Jeśli zadanie mogło zapisywać tekst, propozycja może być już w sklepie. Aby cofnąć zmiany z danego zadania, użyj przycisku **Rollback** na zadaniu w zakładce **Jobs**.

### 3.7. Catalog

Otwórz zakładkę **Catalog**. Tłumaczy ona pola produktów, kategorii lub stron CMS zapisane w językach sklepu. Nie edytuje tekstów z **International → Translations**. Jedno kliknięcie obejmuje maksymalnie 100 rekordów. Zapisane wiersze trafiają do języka docelowego.

![Catalog, angielski back office. Entity, Fields, języki, Only empty i Start after ID.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-catalog.webp)

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Entity** | product | Co jest czytane: **product**, **category** albo **cms**. Zmiana przeładowuje stronę i pokazuje tylko pola tej encji. Sama zmiana niczego nie tłumaczy. |
| **Fields** | wszystkie pola tej encji | Które teksty wysyła porcja. Aby zaznaczyć kilka, przytrzymaj Ctrl lub Cmd. Niezaznaczone pola nie są wysyłane i zostają bez zmian. Dla produktu: **Title**, **Short description**, **Description**, **Meta title**, **Meta description** i **Friendly URL**. Dla kategorii: **Title**, **Description**, **Meta title**, **Meta description** i **Friendly URL**. Dla CMS: **Title**, **Meta description**, **Meta keywords**, **Content** i **Friendly URL**. W produkcie i kategorii pole **Title** to nazwa. W CMS pole **Title** to tytuł strony, a **Content** to treść strony. Jeśli linki mają pozostać bez zmian, nie zaznaczaj **Friendly URL**. |
| **Source language** | pierwszy język sklepu | Język, z którego kopiowane są pola. Tego języka nie zmieniamy. |
| **Target language** | pierwszy język sklepu | Język, który dostaje tłumaczenie. Musi być inny niż język źródłowy. |
| **Only empty** | Yes | Pomija pola, które mają już tekst w języku docelowym. Wyłącz tę opcję tylko wtedy, gdy chcesz nadpisać istniejący tekst. Gdy opcja jest włączona, istniejący tekst docelowy zostaje. Gdy jest wyłączona, porcja może go zastąpić, o ile zapis jest dozwolony. |
| **Start after ID** | 0 | Pomija rekordy o ID niższym lub równym wpisanej wartości. 0 oznacza start od pierwszego rekordu. Po porcji pole ustawia się na najwyższe ID z tej porcji, również dla wierszy, które nie przeszły. Aby przejść dalej, kliknij przycisk ponownie. Jeśli chcesz powtórzyć wiersz z błędem, ustaw ID tak, by był poniżej tego rekordu, zanim ponownie uruchomisz porcję. |

Przycisk: **Translate batch (max 100)**.

Kroki:

1. Wybierz **Entity** i zaznacz pola.
2. Wybierz **Source language** i **Target language**.
3. Zostaw włączoną opcję **Only empty**.
4. Kliknij **Translate batch (max 100)**. Komunikat to **Catalog finished: saved N, failed M.** Strona pokazuje też liczniki **Saved** i **failed**.
5. Otwórz jeden rekord w języku docelowym i sprawdź wynik, zanim wyłączysz **Only empty** albo przetworzysz kolejną porcję.

Komunikaty:

- **Nothing was translated. Select at least one field.**
- **Nothing was translated. Source and target language must be different.**
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. There is no Claude API key. Open Settings and paste the key.**
- Zmiana **Entity** pokazuje komunikat **Showing fields for {entity}. Nothing was translated.**

### 3.8. Glossary

Otwórz zakładkę **Glossary**. Glosariusz to lista słów i zwrotów, które model ma zostawić bez zmian albo zawsze tłumaczyć tak samo. Dodanie wpisu nie zmienia tłumaczeń, które są już zapisane. Kolejne tłumaczenie korzysta z tej listy.

![Glossary, angielski back office. Dodanie terminu i import CSV.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-glossary.webp)

**Pojedynczy termin**

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Source term** | puste, wymagane | Słowo lub zwrot w języku źródłowym. Wpisz go dokładnie tak, jak występuje w tekście, z wielkimi literami tam, gdzie mają znaczenie. |
| **Target locale** | puste | Ogranicza wpis do jednego locale, na przykład pl-PL. Puste pole oznacza, że wpis dotyczy każdego języka docelowego. Jeśli wpiszesz locale, wpis zostanie pominięty przy innych językach. |
| **Target term** | puste | Zatwierdzone tłumaczenie. Może zostać puste tylko wtedy, gdy włączona jest opcja **Do not translate**. |
| **Do not translate** | No | Po włączeniu model kopiuje termin bez zmian, na przykład nazwę marki, SKU lub tag. Po wyłączeniu używa wartości **Target term**. |

Kliknij **Add**. Komunikaty: **Glossary term added. Translations already stored were not changed.** albo **Nothing was added. Type a source term.**

**Tabela**

Kolumny: **Source**, **Locale**, **Target**, **Do not translate** (**Yes** albo **No**) oraz **Delete**. Przycisk **Delete** usuwa tylko ten jeden wiersz. Komunikat: **Glossary term deleted.** Pusta lista pokazuje **No glossary terms yet.**

**Import i eksport CSV**

- Wybierz **CSV file** i kliknij **Import CSV**. Zobaczysz komunikat **Imported N rows.** Jeśli nie wybrano pliku, pojawi się **CSV file is missing.**, a jeśli nie da się go odczytać, **Cannot open the CSV file.**
- Pierwszy wiersz pliku to nagłówek: `source_term`, `target_locale`, `target_term`, `do_not_translate`. Nagłówek jest zawsze pomijany. Wiersze z mniej niż trzema kolumnami również są pomijane. W czwartej kolumnie pusta wartość albo 0 oznacza **No**, a każda inna wartość oznacza **Yes**.
- Import dodaje wiersze z pliku bez sprawdzania, czy termin już istnieje. Jeśli wgrasz ten sam plik ponownie, powstaną duplikaty.
- Przycisk **Export CSV** pobiera bieżącą listę jako plik `glossary.csv`. Nie wymaga pliku wejściowego i nie zmienia listy.

Używaj krótkich i dokładnych terminów. Zbyt ogólny termin będzie wymuszany przy każdym wystąpieniu, nawet tam, gdzie nie pasuje.

### 3.9. Excludes

Otwórz zakładkę **Excludes**. Wykluczenie to wzorzec tekstu źródłowego, którego moduł nie wysyła do Claude. Taki tekst zostaje w sklepie bez zmian. Wzorzec działa na **Manual**, **Bulk**, **Catalog** i na stronach tłumaczeń.

![Excludes, angielski back office. Pattern, Type i pusta lista.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-excludes.webp)

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Pattern** | puste, wymagane | Tekst, który jest porównywany z każdym tekstem źródłowym. Sposób porównania zależy od wybranego **Type**. |
| **Type** | exact | **exact** oznacza dopasowanie całego tekstu. **prefix** dopasowuje początek tekstu. **contains** szuka fragmentu w dowolnym miejscu. **regex** to wyrażenie regularne PHP, stosowane dokładnie tak, jak je wpisano. Błędne wyrażenie nie pasuje do niczego. Zacznij od krótkiego wzorca i sprawdź, co zostało pominięte. Zły typ może pominąć za dużo albo nic. |

Kliknij **Add**. Komunikat: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Jeśli pole jest puste, zobaczysz **Nothing was added. Type a pattern.**

Kolumny: **Pattern**, **Type**, **On** i **Delete**. Kolumna **On** pokazuje 1, gdy wzorzec jest aktywny. Na tym ekranie nie ma przełącznika, który go wyłącza. Aby przestać go stosować, kliknij **Delete**, a jeśli wzorzec nadal jest potrzebny, dodaj go ponownie. Przycisk **Delete** usuwa tylko ten wzorzec i nie kasuje istniejących tłumaczeń. Komunikat: **Pattern deleted.** Pusta lista pokazuje **No patterns yet.**

Wykluczeń używaj do tekstów, które mają zostać w języku źródłowym, na przykład do nazwy prawnej firmy albo tokena technicznego. Jeśli termin ma być zawsze tłumaczony w jeden sposób, użyj **Glossary**.

### 3.10. History

Otwórz zakładkę **History** albo kliknij **See all** na **Dashboard**.

![History, angielski back office. Lista wywołań i Clear history.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-history.webp)

**History** to pełna lista zapisanych wywołań Claude: przebiegi ręczne, strona tłumaczeń, zadania zbiorcze, porcje katalogu oraz test połączenia. Każdy wiersz zawiera prompt, odpowiedź, model, języki, liczbę tokenów i czas wywołania. Karty i wykresy znajdziesz na **Dashboard**. Samo otwarcie tej strony nie wysyła nowego zapytania i nie zmienia tłumaczeń.

Filtry i wykresy są na **Dashboard**. Ta strona to tylko lista.

Kolumny: **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** i **Prompt**. Typy wywołań: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** oraz **Not sent**. Ten ostatni oznacza, że wywołanie nie zostało wysłane, na przykład z powodu lokalnego limitu albo budżetu. W wierszu **Bulk job** widać numer zadania.

- **View** otwiera prompt i odpowiedź wraz z danymi **HTTP**, **Sent**, **Received** i **Total**. Przy błędzie odpowiedzią jest tekst błędu. Przycisk **Back to the list** wraca do tabeli. Jeśli wiersz już nie istnieje, zobaczysz **This history row no longer exists.**
- Błąd dostępu oznacza, że klucz w **Settings** jest nieprawidłowy albo konto nie ma dostępu do wybranego modelu.
- **Previous**, **Next** i **Page** służą do przeglądania listy.
- **Clear history** zapyta **Clear the stored history? Saved translations stay.** Po potwierdzeniu zobaczysz **History cleared. Saved translations were not changed.** Podpowiedź przycisku mówi: **Clear history deletes these rows only. Saved translations stay.**

Jeśli lista jest pusta, zobaczysz **No requests yet.**

Gdy tłumaczenia nagle przestają działać, otwórz tutaj najnowszy wiersz z błędem, zanim zaczniesz zmieniać glosariusz.

### 3.11. Updates

Otwórz **Updates** z prawego końca paska modułu. Tytuł formularza to **MyPresta Updates**.

![Updates, angielski back office. Manual Check, Automatic Notifications i Product Page.](https://mypresta.eu/docs/images/docs/myaitranslationsclaude-updates.webp)

- **Manual Check** zawiera przycisk **Check Now**, który sprawdza wersję od razu.
- **Automatic Notifications** ma stan **Enabled** albo **Disabled**. Domyślnie jest **Enabled**, dopóki nie zapiszesz innego wyboru. Po włączeniu moduł sprawdza, czy MyPresta ma nowszą wersję, i może pokazać ostrzeżenie w back office.
- **Product Page** to odnośnik do strony kontaktowej, której używa ten moduł.
- Przycisk **Save** zapisuje wybór. Komunikat: **Update settings saved.**

Po kliknięciu **Check Now** zobaczysz **New version available!** albo **Module is up to date!**

### 3.12. Przyciski na International → Translations

Otwórz stronę **International → Translations**. Przyciski przy polach pojawiają się, gdy opcja **Individual field buttons — International → Translations** jest włączona. Pola wyboru i pasek widać wtedy, gdy włączona jest opcja **Individual field checkboxes — International → Translations**.

Co zobaczysz:

- Przycisk **Translate** przy każdym polu tekstowym.
- Pole wyboru przy każdym polu, o ile pola wyboru są włączone.
- Pasek z napisem **Claude translations**, a na nim **Source** (en-US albo **Source locale** z **Settings**), **Target**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** oraz podpowiedź **Fills the fields. Save with the PrestaShop button.** Przycisk **Translate empty in this section** wypełnia puste pola w bieżącej sekcji.

Kroki:

1. Wybierz **Target**.
2. Zaznacz pola albo kliknij **Check empty**.
3. Kliknij **Translate selected** albo **Translate empty**.
4. Poczekaj, aż pasek pokaże **Done**. W trakcie pracy status to **Translating…** wraz z licznikiem. Jeśli nic nie zaznaczysz, pasek poinformuje: **Tick at least one field.**
5. Sprawdź wypełnione pola i zapisz stronę przyciskiem **Save** w PrestaShop.

Przyciski tylko wypełniają pola. Bez kliknięcia **Save** w PrestaShop tekst nie trafi do sklepu. Gdy opcja **Allow publish / save** jest wyłączona, pola nadal się wypełniają, a zapisuje je przycisk **Save** w PrestaShop.

Komunikaty:

- **Target is not a language from this shop.**
- **Fill the source language field first.**
- **The source language field is not on this page.**
- **The source language mail file was not found.** Przy sekcji **Emails** tekst źródłowy pochodzi z pliku szablonu e-maila, a nie z pola na stronie. Wybierz inne **Source locale**, dla którego te pliki e-maili istnieją.

### 3.13. Przyciski w formularzach produktów, kategorii i CMS

Otwórz produkt, kategorię, stronę CMS albo inny formularz sklepu z polami wielojęzycznymi. Przyciski pojawiają się, gdy włączona jest opcja **Individual field buttons — shop forms**. Pola wyboru i pasek widać, gdy włączona jest opcja **Individual field checkboxes — shop forms**.

Co zobaczysz:

- Przycisk **Translate** przy każdym polu wielojęzycznym.
- Pole wyboru służące do zaznaczania pól na pasku.
- Pasek z napisem **Claude translations**, a na nim **Translate from** i **to**, **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** oraz podpowiedź **Fills the fields. Save with the PrestaShop button.**

Kroki:

1. Wypełnij pole w języku źródłowym. Jeśli jest puste, pasek poinformuje: **Fill the source language field first.**
2. Wybierz na pasku język docelowy.
3. Kliknij przycisk przy jednym polu albo zaznacz pola i kliknij **Translate selected**. Przycisk **Translate empty** wypełnia puste pola.
4. Kliknij **Save** w formularzu PrestaShop. Bez tego tekst nie zostanie zapisany.

Przycisk tylko wypełnia pole w formularzu. Pola, których nie zaznaczysz, pozostają bez zmian.

## 4. Widok sklepu

Moduł nie dodaje niczego do strony, którą widzi klient. Nie ma tu bloku, przycisku ani komunikatu, więc motyw nie ma nic do wyświetlenia w związku z tym modułem.

Jedyny adres poza back office to adres cron. Służy do zadania uruchamianego przez harmonogram serwera. Nie jest przeznaczony dla klientów.

- Skopiuj go z **Settings**, z pola **CRON URL**, albo z linii **CRON** na **Dashboard**.
- Wklej go do harmonogramu serwera, na przykład tak, aby uruchamiał się co kilka minut. Każde wywołanie przetwarza jedną porcję czekającego zadania.
- Jeśli w sklepie działa SSL, używaj adresu `https://`.

| Co zobaczysz po otwarciu adresu | Co zrobić |
|---|---|
| **Forbidden** | Adres jest niepełny albo został zmieniony. Skopiuj go ponownie z **Settings**. |
| **No pending jobs** | Nie ma zadania w stanie `pending` ani `running`. Utwórz je na **Bulk** albo wznów wstrzymane zadanie na **Jobs**. |
| Wynik w formacie JSON z polami `ok`, `finished` i `counts` | Jedna porcja została przetworzona. Sprawdź postęp na **Jobs**. |

Adres cron przetwarza tylko zadania w stanie `pending` i `running`. Zadanie `paused` trzeba wznowić ręcznie na **Jobs**.

## 5. Problemy

| Co widzisz | Przyczyna | Co zrobić |
|---|---|---|
| **No Claude API key.** na każdej stronie modułu | Klucz nie został zapisany. | Otwórz **Settings**, wklej klucz w polu **Claude API key** i kliknij **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Ustawienia zapisano bez klucza. | Wklej klucz i kliknij **Save**. |
| **Connection was not made. Nothing was translated.** po kliknięciu **Test connection** | Zły klucz, brak połączenia z Anthropic albo model, którego konto nie może użyć. | Sprawdź klucz, wybierz inny **Model** albo dodaj właściwy identyfikator w **Add a Claude model**. Przeczytaj szczegóły w wierszu na **History**. |
| Błędy dostępu na **History** | Klucz jest nieprawidłowy albo konto nie ma dostępu do wybranego modelu. | Popraw klucz albo wybierz model, do którego konto ma dostęp. |
| **Nothing was started. There is no Claude API key.** na **Bulk** | Brak klucza. | Wklej klucz w **Settings**, a następnie ponownie kliknij **Estimate** i **Start job**. |
| Zadanie zostaje w stanie `pending` | Zadanie nie uruchamia się samo. | Kliknij **Process slice** albo **Auto-process** na **Jobs** albo ustaw adres cron (rozdział 4). |
| Zadanie jest `paused` z komunikatem **Rate limit — job auto-paused. Resume later.** | Claude odrzucił wywołania z powodu limitu częstotliwości. | Odczekaj kilka minut i kliknij **Resume**. Zmniejsz **Batch size** albo **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | Osiągnięto kwotę z **Budget USD / month**. | Podnieś kwotę albo ustaw 0. Nowy miesiąc zaczyna licznik od zera. |
| **Nothing was saved. Turn on Allow publish in Settings.** | Opcja **Allow publish / save** jest wyłączona. | Włącz **Allow publish / save**. |
| **Not saved because of broken placeholders or HTML: N.** na **Manual** | Tłumaczenie zmieniło placeholdery albo znaczniki HTML. | Popraw wiersz w **Review before save** tak, aby placeholdery i znaczniki zgadzały się z oryginałem, a następnie kliknij **Save approved**. |
| Zadanie kończy się statusem `completed_with_errors` | Część tekstów nie przeszła. | Otwórz zadanie, kliknij **Failed only**, pobierz **Error CSV**, a potem kliknij **Retry failed**. |
| Wiersze na **Review** mają niski **Score** | Sprawdzenie jakości przeniosło je do kolejki. | Przeczytaj **Source** i **AI**, a następnie kliknij **Approve** albo **Reject**. Jeśli zły tekst już został zapisany, użyj **Rollback** na zadaniu. |
| Tłumaczenie zostało zapisane, a sklep nadal pokazuje stary tekst | Cache strony się nie odświeżył. Moduł czyści cache przy zapisie tłumaczenia katalogu, przy porcji zadania zbiorczego i przy rollbacku. | Wyczyść cache w back office PrestaShop. |
| Wykluczenie nie pomija tekstu | Zły **Type** albo wyrażenie **regex**, które do niczego nie pasuje. | Na **Excludes** usuń wzorzec i dodaj krótszy, z właściwym **Type**. |
| Nowy termin w glosariuszu nie zmienia zapisanych tłumaczeń | Glosariusz jest czytany przy kolejnym tłumaczeniu, a zapisane teksty zostają bez zmian. | Przetłumacz te teksty ponownie na **Bulk** z opcją **Overwrite all**, po wcześniejszym sprawdzeniu **Estimate**. |
| **The source language mail file was not found.** | Wybrane źródło nie ma pliku e-maila. | Na **Settings** wybierz inne **Source locale** albo na stronie tłumaczeń inne **Source**, które ma pliki e-maili. |
| **No strings match this filter. Nothing was sent to Claude.** | Filtr do niczego nie pasuje. | Wyłącz **Only empty**, wyczyść **Search** albo wybierz inną domenę. |
| **Nothing was translated. Tick at least one row.** | Żaden wiersz nie był zaznaczony. | Zaznacz wiersze i kliknij **Translate selected (review)**. |
| **Nothing was translated. Source and target language must be different.** na **Catalog** | Źródło i cel to ten sam język. | Wybierz inny **Target language**. |
| Po **Catalog finished** pole **Start after ID** przeskoczyło za wiersze, które nie przeszły | Pole ustawia się na najwyższe ID porcji, również dla wierszy, które nie przeszły. | Ustaw **Start after ID** poniżej nieudanego rekordu i uruchom porcję ponownie. |
| Pokrycie na **Dashboard** jest puste | Sklep nie ma jeszcze katalogu dla tego locale. | Utwórz go na stronie **International → Translations**, a potem wróć na **Dashboard**. |
| Na **History** widnieje status **Not sent** | Lokalny limit albo budżet zatrzymał wywołanie, zanim zostało wysłane. | Sprawdź **Rate limit / min** i **Budget USD / month** na **Settings**. |
| **The shop needs at least two languages.** | Sklep ma tylko jeden język. | Dodaj język w **International → Localization → Languages**. |

## 6. Dla programistów

### 6.1. Przegląd

- Klasa główna: `myaitranslationsclaude`, plik `myaitranslationsclaude.php`.
- Wersja: 1.2.0.
- Nazwa techniczna: `myaitranslationsclaude`. Nazwa na liście modułów: **AI Translations with Claude**.
- Autor: MyPresta.eu. Zakładka w Module Manager: `administration`.
- Zakładka back office: `AdminMyaitranslationsclaude`, nadrzędna `AdminInternational`, zapasowo `IMPROVE`. Widoczna etykieta zakładki to `AI Translations with Claude`. Metoda `ensureTab()` naprawia brakującą zakładkę, a `renameTabIfTechnical()` podmienia nazwę zakładki, jeśli nadal jest w niej nazwa techniczna.
- Instalacja: `parent::install()`, tabele z `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), `installDefaults()` (zapisuje klucz tylko wtedy, gdy go brakuje), hooki `displayBackOfficeHeader` i `actionAdminControllerSetMedia`, a na końcu zakładka.
- Odinstalowanie: usuwa zakładkę, uruchamia `sql/uninstall.php` (kasuje 11 tabel), a `removeConfiguration()` usuwa klucze `MYAITCL_*` wymienione w tym pliku. Na końcu wywoływane jest `parent::uninstall()`. Nie kasuje `mypresta_updates`, `update_myaitranslationsclaude` ani `updatev_myaitranslationsclaude`.
- Nie ma metod `enable()` ani `disable()`.
- `getContent()` wywołuje `ensureTab()` i przekierowuje do `AdminMyaitranslationsclaude` (domyślna zakładka to `dashboard`).

Przepływ danych:

1. Formularz ustawień wysyła POST do `AdminMyaitranslationsclaudeController::initContent()`.
2. `MyaitclConfigService::saveFromForm()` zapisuje wartości `MYAITCL_*` w `Configuration`. Klasa `MyaitclApiKeyEncryptor` szyfruje klucz API algorytmem AES-256-CBC, używając klucza pochodzącego z `_COOKIE_KEY_`, i przechowuje go jako `MYAITCL_API_KEY_ENC`. Pusty klucz albo wartość zamaskowana nie zastępuje zapisanego klucza.
3. Tłumaczenie: `MyaitclTranslateService::translateMessages()` buduje prompty (`MyaitclPromptBuilder`), wysyła je przez `MyaitclClaudeTranslationProvider` (cURL POST na `https://api.anthropic.com/v1/messages`, nagłówek `anthropic-version: 2023-06-01`), sprawdza odpowiedź (`MyaitclPlaceholderValidator`, `MyaitclHtmlValidator`, `MyaitclPsNativeValidator`), ocenia ją (`MyaitclQualityScorer`) i zapisuje przez `MyaitclTranslationAdapter`.
4. Gdy **Max tokens** wynosi 0, provider wysyła `max_tokens` równe 4096. Metoda `acceptsTemperature()` wysyła **Temperature** tylko wtedy, gdy identyfikator modelu pasuje do wzorca `claude-(opus|sonnet|haiku)-4-(0|1|5|6)`.
5. Zapis katalogu korzysta z usługi tłumaczeń PrestaShop, jeśli ona istnieje. W przeciwnym razie zapisuje do tabeli `_DB_PREFIX_translation`. Klucze modułów klasycznych zapisuje do pliku `translations/{iso}.php` danego modułu klasa `MyaitclLegacyModuleCatalogue`.
6. Bulk: `MyaitclBulkJobFactory` wstawia rekordy do tabel `myaitcl_job` i `myaitcl_job_item`. Metoda `MyaitclJobWorker::processSlice()` wykonuje jedną porcję o wielkości `BATCH_SIZE`. Wywołują ją przycisk **Process slice**, pętla **Auto-process** (AJAX `ProcessJob`) oraz plik `controllers/front/cron.php`.
7. Catalog: `MyaitclCatalogTranslateService::collect()` pobiera maksymalnie 100 wierszy. Metoda `translateAndSave()` zapisuje dane w tabelach `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` albo `_DB_PREFIX_cms_lang`. Wyniki są dopasowywane po ID. Po porcji wartość **Start after ID** staje się najwyższym `id_entity` z zebranego zestawu, również dla wierszy, które nie przeszły.
8. Każde wywołanie trafia do tabeli `myaitcl_request` (**History**). Błędy zapisywane są dodatkowo w `myaitcl_api_log`, a koszt w `myaitcl_usage_ledger`. Klasa `MyaitclSnapshotService` kopiuje poprzednią wartość do `myaitcl_snapshot` na potrzeby **Rollback**. Metoda `clearTranslationCache()` wywołuje `Tools::clearCache()` po zapisie katalogu, po porcji niebędącej przebiegiem próbnym oraz po rollbacku.

### 6.2. Pliki

| Plik | Rola |
|---|---|
| `myaitranslationsclaude.php` | Instalacja, odinstalowanie, zakładka, hooki, assety, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Sprawdzanie aktualizacji dla zakładki **Updates** i ostrzeżenia w back office. Klasa `myaitranslationsclaudeUpdate`. |
| `logo.png`, `logo.gif` | Logo w nagłówku modułu. |
| `controllers/admin/AdminMyaitranslationsclaudeController.php` | Każda zakładka back office, zapisy, akcje zadań, glosariusz, wykluczenia, katalog, CSV i AJAX. |
| `controllers/front/cron.php` | Adres cron. Przetwarza jedną porcję i zwraca JSON. |
| `sql/install.php`, `sql/uninstall.php` | Tworzenie i usuwanie tabel. |
| `src/Adapter/MyaitclTranslationAdapterInterface.php` | Interfejs odczytu i zapisu tłumaczeń PrestaShop. |
| `src/Adapter/MyaitclAbstractTranslationAdapter.php` | Sekcje, domeny, locale, zapis przez usługę albo tabelę `translation`, czyszczenie cache. |
| `src/Adapter/MyaitclTranslationAdapter.php` | Konkretny adapter. |
| `src/Adapter/MyaitclTranslationAdapterFactory.php` | Buduje adapter. |
| `src/Adapter/MyaitclFilesystemCatalogueTrait.php` | Czyta katalogi XLF z motywów i modułów. |
| `src/Adapter/MyaitclLegacyModuleCatalogue.php` | Moduły klasyczne: odczyt i zapis `translations/{iso}.php`. |
| `src/Admin/MyaitclForms.php` | Formularze back office i tekst `desc` pól. |
| `src/Admin/MyaitclSectionHelp.php` | Tekst panelu **Help** dla każdej zakładki. |
| `src/Audit/MyaitclRequestLogRepository.php` | **History**: wiersze, karty, wykresy, filtry, czyszczenie i retencja. |
| `src/Audit/MyaitclApiLogRepository.php` | Log błędów i ostrzeżeń API oraz ich retencja. |
| `src/Audit/MyaitclTranslationMemory.php` | Ponowne użycie wyniku dla tego samego tekstu, locale, modelu i glosariusza. |
| `src/Audit/MyaitclUsageLedger.php` | Szacunek kosztu na podstawie tabeli cen w tym pliku oraz miesięczny budżet. |
| `src/Audit/MyaitclSnapshotService.php` | Kopie przed zapisem i ich przywracanie przy **Rollback**. |
| `src/Glossary/MyaitclGlossaryRepository.php` | Lista glosariusza, wstawianie i kasowanie. |
| `src/Glossary/MyaitclExcludePatternRepository.php` | Wstawianie wykluczeń, kasowanie i dopasowywanie. |
| `src/Job/MyaitclJobStatuses.php` | Stałe statusów zadań i wierszy. |
| `src/Job/MyaitclJobRepository.php` | Zadania i wiersze: odczyt, status, następna porcja, liczniki. |
| `src/Job/MyaitclJobWorker.php` | Przetwarzanie porcji, ponawianie, zakończenie, kolejka review i e-mail po zakończeniu. |
| `src/Provider/MyaitclTranslationProviderInterface.php` | Interfejs providera. |
| `src/Provider/MyaitclClaudeTranslationProvider.php` | Wywołania Claude, test połączenia i log zapytań. |
| `src/Provider/MyaitclPromptBuilder.php` | Prompt systemowy i prompt użytkownika: ton, głos marki i glosariusz. |
| `src/Provider/MyaitclProviderFactory.php` | Buduje provider. |
| `src/Quality/MyaitclPlaceholderValidator.php` | Sprawdzanie placeholderów i tagów. |
| `src/Quality/MyaitclHtmlValidator.php` | Sprawdzanie HTML. |
| `src/Quality/MyaitclPsNativeValidator.php` | Sprawdzanie przed zapisem na **Manual**. |
| `src/Quality/MyaitclEmailHtmlPipeline.php` | Zabezpiecza HTML e-maila przed wywołaniem i przywraca go po odpowiedzi. |
| `src/Quality/MyaitclQualityScorer.php` | Ocena 0-100, flagi i decyzja o kolejce review. |
| `src/Security/MyaitclApiKeyEncryptor.php` | Szyfrowanie i odszyfrowywanie klucza API. |
| `src/Service/MyaitclConfigService.php` | Odczyt i zapis ustawień, modele, token cron i zakresy. |
| `src/Service/MyaitclRateLimiter.php` | Lokalny limit na minutę, plik `var/rate_limit.json`. |
| `src/Service/MyaitclTranslateService.php` | Wykluczenia, pamięć, wywołania, walidacja, ocena, zapis i szacunek. |
| `src/Service/MyaitclBulkJobFactory.php` | Buduje zadanie **Bulk** i szacunek. |
| `src/Service/MyaitclCatalogTranslateService.php` | Zbiera i zapisuje wiersze **Catalog**. |
| `src/Service/MyaitclDashboardService.php` | Liczniki pokrycia na **Dashboard**. |
| `translations/*.php` | Tłumaczenia interfejsu, jeden plik na język. |
| `views/templates/admin/configure.tpl` | Strona modułu i szuflada **Help**. |
| `views/templates/admin/_partials/*.tpl` | Zakładki: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review` i `settings`. |
| `views/css/admin.css` | Style back office. |
| `views/js/admin.js` | Postęp na **Jobs**, **Auto-process**, zaznaczanie wierszy i AJAX. |
| `views/js/admin-help.js` | Panel **Help**. |
| `views/js/translations-tool.js` | Przyciski i pasek na **International → Translations**. |
| `views/js/entity-fields.js` | Przyciski i pasek w formularzach produktów, kategorii i CMS. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Wykresy na **Dashboard**. |
| `var/rate_limit.json` | Licznik lokalnego limitu na minutę. |
| `index.php` w każdym katalogu | Blokuje listing katalogu. |

### 6.3. Kontrolery

**Back office: `AdminMyaitranslationsclaudeController`** (`ModuleAdminController`).

- URL: `index.php?controller=AdminMyaitranslationsclaude&token=…`, opcjonalnie z `&myaitcl_tab=` i wartościami `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs` (etykieta zakładki to **History**), `settings` albo `updates`.
- Akcje zadania przekazywane parametrem `job_action` wraz z `id_job`: `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback` i `export_errors`. Szablon nie wyświetla przycisku Cancel. Parametr `filter_failed=1` ogranicza tabelę wierszy.
- Akcje review: `review_action=approve|reject` oraz `id_review`.
- Glosariusz: `delete_glossary`. Wykluczenia: `delete_exclude`. Modele: `delete_claude_model` oraz POST `new_claude_model` z `submitMyaitranslationsclaudeAddModel`.
- AJAX: `displayAjaxProcessJob`, `displayAjaxJobStatus`, `displayAjaxHistoryDetail` oraz endpointy tłumaczenia pól używane przez `translations-tool.js` i `entity-fields.js`.

**Front: `MyaitranslationsclaudeCronModuleFrontController`** (`controllers/front/cron.php`).

- Adres w sklepie: `module/myaitranslationsclaude/cron`.
- Parametr `token` musi być zgodny z `MYAITCL_CRON_TOKEN` (porównanie `hash_equals`). Brakujący albo błędny token zwraca HTTP 403 i JSON `{"ok":false,"error":"Forbidden"}`.
- Opcjonalny parametr `id_job` przetwarza wskazane zadanie. Bez niego przetwarzane jest pierwsze zadanie w stanie `pending` albo `running`.
- Udana porcja zwraca JSON z polami `ok`, `finished` i `counts`. Gdy żadne zadanie nie czeka, odpowiedzią jest `{"ok":true,"message":"No pending jobs"}`.
- Kontroler ma ustawione `ssl` na true.

### 6.4. Hooki

Zarejestrowane hooki:

- `displayBackOfficeHeader` - zmienia techniczną etykietę zakładki, a potem ładuje CSS i JS.
- `actionAdminControllerSetMedia` - ładuje te same assety.

Plik `translations-tool.js` jest dodawany na kontrolerze tłumaczeń. Plik `entity-fields.js` jest dodawany w formularzach sklepu, gdy przełączniki pól są włączone. Metoda `Media::addJsDef` udostępnia obiekt `myaitclTr` (adres AJAX, locale źródłowe, języki i etykiety paska).

Moduł nie rejestruje własnego hooka, który inne moduły mogłyby implementować. Nie ma metod `enable()` ani `disable()`.

### 6.5. Nadpisania

Moduł nie nadpisuje żadnej klasy ani kontrolera PrestaShop.

### 6.6. Baza danych

| Tabela | Zawartość |
|---|---|
| `myaitcl_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, ID sklepu i daty. |
| `myaitcl_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`) i `enabled`. |
| `myaitcl_job` | Jeden przebieg zbiorczy: locale, `scope_json`, `policy_json`, `dry_run`, liczniki, sumy tokenów, koszt, pracownik, błąd i znaczniki czasu. |
| `myaitcl_job_item` | Jeden tekst zadania: domena, klucz, motyw, locale, źródło, poprzednia wartość, nowa wartość, status, powód pominięcia, błąd, tokeny i walidacja. |
| `myaitcl_memory` | Pamięć tłumaczeń: hash, źródło, locale, tłumaczenie, model i liczba trafień. |
| `myaitcl_usage_ledger` | Dzienne wiersze tokenów i kosztu, opcjonalnie ID zadania i model. |
| `myaitcl_snapshot` | Wartość sprzed zapisu zadania, używana przez **Rollback**. |
| `myaitcl_api_log` | Wiersze błędów i ostrzeżeń: poziom, provider `claude`, kod HTTP, komunikat i kontekst. |
| `myaitcl_request` | Wiersze **History**: typ, status, model, locale, kod HTTP, czas trwania, tokeny, koszt, pracownik, zadanie, prompt, odpowiedź i błąd. |
| `myaitcl_review` | Kolejka review: pozycja zadania, status, ocena, flagi i pracownik. |
| `myaitcl_catalog_item` | Wiersze porcji Catalog: encja, pole, języki, źródło, poprzednia wartość, nowa wartość, status i błąd. |

Odinstalowanie usuwa wszystkie jedenaście tabel. Instalacja używa `CREATE TABLE IF NOT EXISTS`, więc ponowna instalacja na bazie, w której tabele nadal istnieją, zostawia ich wiersze. Zwykłe odinstalowanie usuwa je wcześniej. Przy pierwszej wizycie na stronie nie jest dodawana żadna kolumna.

### 6.7. Klucze i tłumaczenia

Prefiks: `MYAITCL_`. Poniżej wartości używane, gdy klucz nie istnieje. Są to też wartości zapisywane przy instalacji:

| Klucz | Wartość domyślna |
|---|---|
| `API_KEY_ENC` | puste |
| `MODEL` | `claude-haiku-4-5` |
| `EXTRA_MODELS` | puste |
| `PROVIDER` | `claude` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | puste |
| `BATCH_SIZE` | `25` (przy zapisie ponownie przycinane do zakresu 1-100) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | puste |
| `TEMPERATURE` | `0.2` (przy zapisie ponownie przycinane do zakresu 0-1) |
| `DRY_RUN_SAMPLE` | `10` (przy zapisie ponownie przycinane do zakresu 1-50) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (minimum 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | puste |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (provider wysyła wtedy 4096) |
| `CRON_TOKEN` | 16 losowych bajtów zapisanych w postaci hex, generowanych przy instalacji |

Metoda `removeConfiguration()` usuwa również stare nazwy `DEEPL_API_KEY` i `CLAUDE_API_KEY` z tym samym prefiksem. Klucze sprawdzania aktualizacji nie są kasowane.

Opisy pól to ciągi `desc` w pliku `src/Admin/MyaitclForms.php`, składane przez metodę `help()` z celu, sposobu ustawienia i skutku. Pomoc dla zakładek znajduje się w `src/Admin/MyaitclSectionHelp.php`.

Ciągi interfejsu przechodzą przez `$this->l()` albo `{l s=... mod='myaitranslationsclaude'}`. Aby dodać język, utwórz plik `translations/{iso}.php`. Komunikaty błędów zadań, takie jak **Rate limit — job auto-paused. Resume later.**, **Allow publish is off in Settings.**, **No Claude API key. Nothing was translated.** oraz **Monthly API budget has been exhausted.**, to ciągi angielskie zwracane przez `MyaitclJobWorker` i `MyaitclTranslateService`. Nie są wywołaniami `$this->l()`. Ciągi zakładki **Updates** używają domeny tłumaczeń `updatechecker`.

### 6.8. Rozszerzanie

Widok sklepu nie renderuje szablonu modułu, więc motyw nie ma czego nadpisać.

Szablony back office znajdują się w `views/templates/admin/`. PrestaShop nie pozwala nadpisywać ich w motywie. Etykiety zmienisz przez plik `translations/{iso}.php`. Przyciski na **International → Translations** i w formularzach sklepu wstrzykują pliki `views/js/translations-tool.js` oraz `views/js/entity-fields.js` z obiektem `myaitclTr`. Nie ma hooka, dzięki któremu motyw mógłby podmienić ten pasek.

## 7. Pomoc

Strona modułu: https://mypresta.eu/pl/ai-sztuczna-inteligencja/tlumaczenia-ai-z-claude.html

Aby napisać w sprawie tego modułu, zaloguj się na konto klienta na mypresta.eu, otwórz formularz kontaktowy i wybierz temat **Support for paid modules**. Formularz informuje, że przy modułach płatnych wymagane jest logowanie. Po zalogowaniu wybierz ten moduł z historii zakupów.
