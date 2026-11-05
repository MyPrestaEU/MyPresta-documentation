---
title: "AI Translations with ChatGPT - dokumentacja i instrukcja użytkownika"
description: "Konfiguracja i rozwiązywanie problemów w sklepach, w których jest już zainstalowany moduł AI Translations with ChatGPT."
sidebar:
  label: "AI Translations with ChatGPT - dokumentacja i instrukcja użytkownika"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł AI Translations with ChatGPT na MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-chatgpt.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ai-artificial-intelligence/ai-translations-with-chatgpt/)
>
> ---


## 1. Wymagania

Moduł działa w PrestaShop 1.7.0.0 i nowszych, także w PrestaShop 8 i 9.

- **PrestaShop:** 1.7.0.0 lub nowszy.
- **PHP:** 5.6 lub nowszy.
- **Rozszerzenia PHP:** cURL, OpenSSL, SimpleXML i mbstring.
- **Inne moduły:** moduł nie wymaga żadnego innego modułu.
- **Poza sklepem:** konto OpenAI i klucz API. Serwer sklepu musi mieć możliwość połączenia się z adresem `https://api.openai.com/v1/chat/completions`.
- **Opcjonalnie:** zadanie w harmonogramie serwera (cron), które otwiera adres z **Settings**. Bez niego zadania uruchamiasz ręcznie na stronie **Jobs**.
- **Duże katalogi:** domena z tysiącami ciągów to bardzo dużo wywołań API. Zadanie jest dzielone na porcje o wielkości **Batch size**. Przed startem uruchom **Estimate** na stronie **Bulk**.
- Sklep potrzebuje co najmniej dwóch języków. Przy jednym języku zaplecze pokazuje komunikat **The shop needs at least two languages.** i nie ma czego tłumaczyć.

## 2. Instalacja

1. Otwórz **Modules**, a potem **Module Manager**. Wybierz **Upload a module**, wgraj plik ZIP i kliknij **Install** przy module **AI Translations with ChatGPT**.
2. Po instalacji moduł pojawia się w menu **International**.
3. Instalacja nie czyści pamięci podręcznej sklepu. Moduł czyści ją dopiero wtedy, gdy zapisze tłumaczenie.

Otwórz **AI Translations with ChatGPT**, potem **Settings** i wklej klucz ChatGPT. Dopóki klucz nie zostanie zapisany, każda strona modułu pokazuje komunikat **No ChatGPT API key.** oraz odnośnik **Open Settings**.

**Odinstalowanie.** W **Module Manager** kliknij **Uninstall** i potwierdź pytanie **Delete this module and its data (jobs, glossary, cache)?**

- Pozycja w menu znika. Usuwane są zadania, słownik, wzorce wykluczeń, historia wywołań, kolejka **Review**, kopie do przywrócenia, rejestr kosztów oraz ustawienia modułu, w tym klucz API.
- Tekst, który moduł już zapisał w sklepie, zostaje. Dotyczy to tłumaczeń z katalogu oraz plików tłumaczeń klasycznych modułów, do których moduł coś zapisał. Zostaje też wybór dotyczący sprawdzania aktualizacji.
- Ponowna instalacja nie przywraca usuniętych zadań, słownika ani historii. Ustawia wartości domyślne i tworzy nowy adres cron.

## 3. Konfiguracja i praca w zapleczu

Cały moduł to jedna strona: **International**, a w niej **AI Translations with ChatGPT**. Zakładki to **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** i **Settings**. Zakładka **Updates** znajduje się na końcu paska. Przycisk **Help** otwiera panel z opisem bieżącej zakładki.

Nazwy przycisków i pól w tej instrukcji są podane tak, jak widać je w angielskim zapleczu. W innym języku panelu zobaczysz tłumaczenie tej samej kontrolki. Zrzuty ekranu pochodzą z angielskiego zaplecza.

Zwykła praca składa się z czterech etapów:

1. **Połączenie.** W **Settings** wklej klucz, wybierz model i kliknij **Test connection**, a potem **Save**.
2. **Mała próba.** Na **Manual** wybierz jedną domenę, zaznacz kilka pustych ciągów i przetłumacz je. Sprawdź wynik, zanim uruchomisz cały katalog.
3. **Zadanie.** Na **Bulk** wybierz sekcję, języki i domeny, kliknij **Estimate**, a potem **Start job**. Otwórz zadanie i kliknij **Process slice** lub **Auto-process**. Możesz też zostawić przetwarzanie wywołaniu adresu cron.
4. **Kontrola.** Sprawdź **Review**, gdzie trafiają wiersze zatrzymane przez kontrolę jakości, i **History**, jeśli wywołanie się nie powiodło. Przycisk **Rollback** na zadaniu przywraca poprzedni tekst tam, gdzie moduł zachował kopię.

Moduł nie zaczyna tłumaczenia sam. Ani **Estimate**, ani **Filter**, ani **Save** na stronie **Settings** nie zapisują tekstu katalogu. Zadanie czeka na stronie **Jobs**, aż je przetworzysz albo zostanie wywołany adres cron.

### 3.1. Konfiguracja modułu

Otwórz **Modules**, **Module Manager**, znajdź **AI Translations with ChatGPT** i kliknij **Configure**. Otworzy się **Dashboard**. Przejdź do zakładki **Settings**.

Przyciski **Save** i **Test connection** znajdują się na dole formularza. Zapisanie formularza nie uruchamia tłumaczenia i nie nadpisuje tłumaczeń, które są już zapisane.

![Ustawienia w angielskim zapleczu. Na górze formularza: ChatGPT API key, Model, Add a ChatGPT model, Tone i Source locale.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-settings.webp)

**Połączenie**

| Pole | Po instalacji | Co robi |
|---|---|---|
| **ChatGPT API key** | puste | Sekretny klucz, który sklep wysyła do ChatGPT. Wklej klucz z konta OpenAI. Jeśli chcesz zachować już zapisany klucz, zostaw pole puste. Wpisana wartość zastępuje zapisany klucz, a puste pole go nie usuwa. Gdy klucz jest zapisany, pomoc pokazuje **Key saved:** i zamaskowany klucz. |
| **Model** | gpt-4.1-mini | Model ChatGPT, który pisze tłumaczenie. Wbudowane nazwy zostają na liście: gpt-4.1, gpt-4.1-mini, gpt-4.1-nano, gpt-4o, gpt-4o-mini, gpt-4-turbo, gpt-4-turbo-preview, gpt-4, gpt-4-0613, gpt-3.5-turbo, gpt-3.5-turbo-0125, o4-mini, o3-mini i o1-mini. Kolejne tłumaczenie używa wybranego modelu. Jeśli konto nie ma dostępu do modelu, wywołanie kończy się błędem, który znajdziesz w **History**. |
| **Add a ChatGPT model** | puste | Wpisz dokładny identyfikator modelu z konta OpenAI i kliknij **Add model**. Podpowiedź w polu to gpt-4.1. Nowy identyfikator pojawia się na liście **Model** i od razu staje się aktywnym modelem. **Remove** usuwa tylko identyfikatory dodane tutaj. Wbudowanych modeli nie da się usunąć. |

Komunikaty: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example gpt-4.1.**, **Built-in models cannot be removed.**

**Głos i źródło**

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Tone** | Formal | Dodaje do każdego promptu wskazówkę dotyczącą stylu. **Formal** nadaje się do tekstów sklepu i zaplecza, **Casual** jest swobodniejszy, a **Brand** działa razem z polem **Brand voice**. Nowe tłumaczenia powstają w wybranym stylu. Istniejące tłumaczenia zostają bez zmian, dopóki nie uruchomisz ich ponownie. |
| **Brand voice** | puste | Widoczne tylko wtedy, gdy **Tone** ma wartość **Brand**. Wpisz kilka zdań o tym, jak sklep ma brzmieć. Pusty tekst oznacza brak dodatkowego opisu głosu. Tekst trafia do kolejnego promptu i nie przepisuje zapisanych tłumaczeń. |
| **Source locale** | puste | Język, który model traktuje jako oryginał. Pusty wybór to kreska na liście. Wtedy źródłem jest ekran, który tłumaczysz. Wybierz locale, w którym napisane są katalogi, zwykle en-US. **Manual**, **Bulk** i ikony na stronie **International → Translations** używają tego locale jako źródła. Domyślny język sklepu się nie zmienia. |
| **Individual field buttons — shop forms** | Yes | Przycisk przy każdym polu wielojęzycznym w formularzach sklepu: produktu, kategorii, CMS i innych formularzach zaplecza. Przycisk tłumaczy tylko to jedno pole. Ustawienie **No** ukrywa te przyciski w całym sklepie. Zapisane tłumaczenia się nie zmieniają. |
| **Individual field checkboxes — shop forms** | Yes | Każde z tych pól dostaje pole wyboru, a pasek tłumaczy tylko zaznaczone pola. Ustawienie **No** ukrywa pola wyboru i pasek. Przyciski z poprzedniego punktu mają osobny przełącznik. |
| **Individual field buttons — International → Translations** | Yes | Przycisk przy każdym polu na stronie **International → Translations**. Ustawienie **No** ukrywa te przyciski. Formularze sklepu nie są tym objęte. Jedno kliknięcie wypełnia jedno pole. Stronę zapisuje przycisk **Save** PrestaShop. |
| **Individual field checkboxes — International → Translations** | Yes | Pola wyboru i pasek na stronie **International → Translations**. Ustawienie **No** je ukrywa. Formularze sklepu nie są tym objęte. |

**Limity**

![Ustawienia w angielskim zapleczu. Pole Batch size i pola limitów pod nim.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-settings-limits.webp)

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Batch size** | 25 | Ile ciągów trafia do jednego wywołania API. Przy pierwszym uruchomieniu użyj wartości od 10 do 25. Wartość mieści się w zakresie od 1 do 100. Większa porcja oznacza mniej wywołań, ale awaria powtarza wtedy większy fragment. |
| **Dry-run sample** | 10 | Ile przykładowych ciągów pokazuje **Estimate** przed zadaniem masowym. Wartość mieści się w zakresie od 1 do 50. **Estimate** nie zapisuje tłumaczeń. |
| **Max tokens (0 = default)** | 0 | Formularz zapisuje tę liczbę, ale żądanie tłumaczenia jej nie wysyła. Nie skraca więc odpowiedzi i nie zatrzymuje odpowiedzi, która została ucięta. Test połączenia używa własnego, krótkiego żądania. Zapisane tłumaczenia nie są przycinane. |
| **Budget USD / month** | 0 | Miesięczny limit w dolarach, liczony z rejestru użycia. Wartość 0 oznacza brak limitu. Gdy rejestr osiągnie tę kwotę, nowe tłumaczenia się zatrzymują. To, co już zapisano, zostaje. |
| **Rate limit / min** | 60 | Ile wywołań API sklep może rozpocząć w ciągu minuty. Wartość 0 wyłącza ten lokalny limit. Wywołania ponad limit są pomijane i zapisywane na **History**. ChatGPT może mieć też własny limit, który stosuje niezależnie. |
| **Log retention days** | 30 | Przez ile dni przechowywać wiersze na **History**. Minimum to 1 dzień. Starsze wiersze są usuwane. Ta liczba nie kasuje zadań, słownika ani zapisanych tłumaczeń. |
| **Temperature** | 0.2 | Jak swobodnie model może przeformułować tekst. Wartość około 0,2 trzyma się oryginału. Im bliżej 1, tym bardziej model zmienia zdania. Zapisana wartość mieści się w zakresie od 0 do 1. Placeholdery i HTML są sprawdzane później. Każde żądanie wysyła tę wartość, także dla dodanego ręcznie identyfikatora modelu. |
| **Allow publish / save** | Yes | Czy moduł może zapisywać tłumaczenia w PrestaShop. Ustawienie **No** blokuje zapis na stronach **Manual**, w zadaniach masowych i na **Catalog**. Ikony na stronie tłumaczeń i w formularzach sklepu nadal tylko wypełniają pola. Przycisk **Save** PrestaShop działa osobno. |

Po kliknięciu **Save** zobaczysz jeden z komunikatów:

- **Settings saved. No translation was started.** Ustawienia są zapisane, a nic nie zostało przetłumaczone.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** Wklej klucz w pole **ChatGPT API key** i kliknij **Save** jeszcze raz.

**Poczta i cron**

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Email notify on complete** | No | Wysyła jeden e-mail, gdy zadanie masowe się skończy. Samo zadanie działa tak samo. Ustawienie dotyczy tylko powiadomienia e-mailem. |
| **Notify email** | puste | Adres, na który przychodzi ten e-mail. Pole jest widoczne tylko wtedy, gdy powyższy przełącznik jest włączony. Sam zapis adresu nie wysyła wiadomości. |
| **CRON URL** | adres z tokenem | Tajny adres, pod którym serwer może przetworzyć jedną porcję czekającego zadania. Wklej go w harmonogramie serwera i nie publikuj. Każdy, kto zna ten adres, może uruchomić porcję. Samo otwarcie **Settings** nie uruchamia zadania. |

**Test connection** sprawdza klucz i model jednym krótkim żądaniem. Nie tłumaczy niczego i niczego nie zapisuje.

- **Connection OK (N ms). No translation was started.** Połączenie działa.
- **Connection was not made. Nothing was translated.** i dalej przyczyna. Sprawdź klucz i model. Szczegóły znajdziesz na **History**.

Praktyczny start wygląda tak: wklej klucz, wybierz model i locale źródłowe, kliknij **Test connection**, a potem **Save**. Pozostaw liczbowe ustawienia z instalacji, dopóki zadania działają poprawnie.

### 3.2. Dashboard

Otwórz zakładkę **Dashboard**. Strona liczy brakujące ciągi katalogu, a następnie pokazuje zużycie ChatGPT w postaci kart, wykresów i dziesięciu najnowszych promptów. Dashboard niczego nie tłumaczy i nie zmienia ciągów.

![Dashboard w angielskim zapleczu. Pokrycie jednego locale, linia cron i filtry historii.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-dashboard.webp)

**Pokrycie**

- **Locale:** locale sklepu, dla którego liczone są brakujące ciągi.
- **Show:** odświeża tabelę dla wybranego locale.
- Kolumny: **Section**, **Total**, **Missing**, **Done** i pasek postępu. Sekcje to **Back office**, **Themes**, **Installed modules**, **Emails** i **Others**. **Missing** to liczba ciągów bez tłumaczenia w tym locale.
- Pod tabelą linia **CRON** pokazuje ten sam adres, co pole **CRON URL** w **Settings**.
- Pusta tabela oznacza, że sklep nie ma jeszcze katalogu dla tego locale. Utwórz go w **International → Translations**.

Po kliknięciu **Show** pojawia się komunikat **Coverage for {locale}. This page only counts strings. Nothing was translated.**

**Użycie**

- Gotowe zakresy: **Today**, **7 days**, **30 days**, **This month** i **All time**.
- Filtry: **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success** albo **Error**), **Language**, **Employee** i **Prompt or reply contains**. Kliknij **Filter**.
- Karty: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** i **Estimated cost**. Szacowany koszt to lokalne wyliczenie, a nie faktura OpenAI.
- Wykresy: **Requests and errors**, **Tokens sent and received** i **Requests by model**. Pod nimi znajdziesz grupy **By day**, **By model**, **By type**, **By language** i **By employee** z kolumnami **Group**, **Calls**, **Sent**, **Received** i **Total**. Pusta grupa pokazuje komunikat **No requests in this range.**
- **Latest prompts** wyświetla dziesięć ostatnich wywołań. **View** otwiera prompt i odpowiedź. **See all** przenosi do **History** (punkt 3.10). Pusta lista pokazuje **No requests yet.**

Filtrowanie nie kasuje historii i nie zmienia tłumaczeń.

Jeśli większość sekcji jest pusta, otwórz **Manual** i przetłumacz kilka ciągów albo **Bulk**, by przetłumaczyć całą domenę.

### 3.3. Manual

Otwórz **Manual**. Tutaj tłumaczysz jedną domenę albo jeden klasyczny moduł, po kilkadziesiąt ciągów naraz. Filtrowanie niczego nie zapisuje.

![Manual w angielskim zapleczu. Pola Section, Source, Target, Domain, Only empty i Search.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-manual.webp)

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Section** | Back office | Który katalog jest czytany: **Back office**, **Themes**, **Installed modules**, **Emails** albo **Others**. Zmiana sekcji przeładowuje stronę i pokazuje tylko pola tej sekcji. Nie wywołuje ChatGPT. |
| **Theme** | puste | Widoczne tylko dla sekcji **Themes**. Ogranicza listę do jednego motywu. |
| **Module** | puste | Widoczne tylko dla sekcji **Installed modules**. Ogranicza listę do jednego modułu. Klasyczny moduł bez domeny ładuje wszystkie swoje ciągi. |
| **Domain** | puste | Ta sama grupa, co na **International → Translations**. Wybierz domenę i kliknij **Filter**. Pole jest ukryte dla klasycznego modułu i dla sekcji bez domen. |
| **Source** | **Source locale** z **Settings** albo en-US | Język, z którego pobierane są ciągi. Wybierz język, który ma już dobry tekst. |
| **Target** | pierwszy język na liście | Język, który chcesz uzupełnić. Musi istnieć w **International → Localization → Languages**. |
| **Only empty** | Yes | Pokazuje tylko ciągi bez tłumaczenia. Wyłączenie pokazuje wszystkie ciągi. Zapisane tłumaczenia nie są kasowane. |
| **Search** | puste | Zostawia tylko ciągi źródłowe, które zawierają wpisane słowo. |

Kroki:

1. Ustaw **Section**, **Source** i **Target**.
2. Dla **Themes** wybierz **Theme**. Dla **Installed modules** wybierz **Module**.
3. Kliknij **Filter**. Lista **Domain** się odświeży. Wybierz domenę i kliknij **Filter** jeszcze raz. W przypadku klasycznego modułu pomiń domenę. **Filter** załaduje wtedy wszystkie ciągi modułu.
4. Zaznacz wiersze. **Check all** i **Uncheck all** zaznaczają lub czyszczą całą listę.
5. Kliknij **Translate selected (review)**. Otworzy się tabela **Review before save** z kolumnami **Source**, **AI proposal** i **Warnings**. Odznacz wiersze, których nie chcesz zapisywać. Popraw propozycję bezpośrednio w polu. Kliknij **Save approved**.
6. Możesz też zaznaczyć **Save now (skip review)** przed tłumaczeniem. Poprawne wiersze zostaną wtedy zapisane od razu, bez tabeli recenzji.

Kolumny listy ciągów to **Source**, **Current** i **Status** (**empty** albo **filled**).

Komunikaty:

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.**
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** Ten komunikat dotyczy listy klasycznego modułu.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to ChatGPT.**
- **No strings match this filter. Nothing was sent to ChatGPT.**
- **No strings match this filter. Turn off Only empty, or this module has no classic strings. Nothing was sent to ChatGPT.**
- **Nothing was translated. Choose a domain, then press Filter to load the strings.**
- **Nothing was translated. Pick a theme, then press Filter.**
- **Nothing was translated. Pick a module, then press Filter.**
- **Nothing was translated. Tick at least one row.**
- **Nothing was translated. There is no ChatGPT API key. Open Settings and paste the key.**
- **Review is ready. Nothing is saved until you press Save approved.**
- **Saved. The approved strings were written for the target language.**
- **Saved N. Only the ticked rows were written.**
- **Nothing was saved. Tick OK on the rows you want to keep.**
- **Not saved because of broken placeholders or HTML: N.** Te wiersze zostały pominięte. Popraw placeholdery i znaczniki tak, żeby zgadzały się ze źródłem, a potem zapisz ponownie.
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.**

Zmiana sekcji pokazuje też krótką linię, na przykład **Section is Back office. Theme and module are not used.**, a obok niej **Nothing was sent to ChatGPT.** Ten sam schemat dotyczy sekcji **Themes**, **Installed modules**, **Emails** i **Others**.

### 3.4. Bulk

Otwórz **Bulk**. Tutaj tworzysz jedno zadanie dla wielu domen i języków. **Estimate** niczego nie zapisuje. **Start job** dodaje wiersz na stronie **Jobs**. Nic nie zostanie zapisane, dopóki zadanie nie zostanie przetworzone, a **Allow publish / save** nie jest włączone.

![Bulk w angielskim zapleczu. Pola Section, Source, Targets, Domains, Policy i Dry-run job.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-bulk.webp)

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Section** | Back office | Który katalog czyta zadanie. Wybór jest taki sam jak na **Manual**. |
| **Theme** / **Module** | puste | Widoczne tylko dla pasującej sekcji, tak jak na **Manual**. |
| **Source** | **Source locale** z **Settings** albo en-US | Język traktowany jako oryginał. Każdy język docelowy jest tłumaczony właśnie z niego. |
| **Targets** | brak | Jeden lub więcej języków do uzupełnienia. Aby zaznaczyć kilka, przytrzymaj Ctrl (na Macu Cmd). Zwykłe kliknięcie zastępuje dotychczasowy wybór. |
| **Domains** | brak | Domeny wchodzące w skład zadania. Aby zaznaczyć kilka, przytrzymaj Ctrl (na Macu Cmd). Domeny, których nie zaznaczysz, nie zostaną przetłumaczone. Zostaw wszystkie niezaznaczone tylko wtedy, gdy chcesz utworzyć puste zadanie. Wyjątkiem jest klasyczny moduł bez domeny: wtedy zadanie obejmuje cały ten moduł. |
| **Policy** | Fill empty | **Fill empty** wysyła tylko ciągi bez tłumaczenia. **Overwrite all** wysyła wszystkie ciągi, także te już przetłumaczone, i może je zastąpić. **Outdated if equals source** wysyła tylko te ciągi, których tłumaczenie jest identyczne z oryginałem. |
| **Dry-run job** | No | ChatGPT nadal działa, a zadanie pojawia się na **Jobs**, ale odpowiedzi nie są zapisywane w sklepie. |

Kroki:

1. Wybierz sekcję, źródło, języki docelowe, domeny i politykę.
2. Kliknij **Estimate**. Strona pokaże **Estimate**, liczbę ciągów, szacunek tokenów, szacunek kosztu i **Sample**.
3. Gdy szacunek jest akceptowalny, kliknij **Start job**. Otworzy się strona **Jobs** z nowym zadaniem.
4. Przetwórz zadanie na stronie **Jobs** (punkt 3.5) albo zostaw je adresowi cron.

Komunikaty:

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to ChatGPT and nothing was saved.**
- **Job #N is waiting (N strings, est. $X). It has not run yet.**
- **Nothing was started. Select at least one target language.**
- **Nothing was started. Pick a theme.**
- **Nothing was started. Pick a module.**
- **Nothing was started. There is no ChatGPT API key. Open Settings and paste the key. No job was created.**

### 3.5. Jobs

Otwórz **Jobs**. Każdy wiersz to jedno uruchomienie z **Bulk**.

![Jobs w angielskim zapleczu. Pusta lista zadań.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-jobs.webp)

Kolumny: **#**, **Status**, **Locales** (najpierw źródło, potem cele), **Progress** (zrobione z wszystkich), **Cost**, **Employee**, **Date** i **Open**. Pusta lista pokazuje **No jobs yet.**

Statusy zadania, dokładnie tak, jak są wyświetlane:

- `pending` - czeka. Nie rusza samo z siebie.
- `running` - w toku.
- `paused` - wstrzymane, dopóki go nie wznowisz.
- `cancelled` - zatrzymane. Ciągi, które jeszcze czekały, nie zostały przetłumaczone.
- `completed` - wszystkie ciągi przetworzone, bez błędów.
- `completed_with_errors` - zakończone, ale część ciągów się nie powiodła.
- `failed` - zadanie zakończyło się błędem.

**Ekran zadania**

Po otwarciu zadania **Open** zobaczysz **Job #N**, status, postęp (zrobione z wszystkich), liczby **failed** i **skipped**, koszt, numer pracownika oraz etykietę **dry-run**, jeśli zadanie jest próbne. Pasek postępu odświeża się sam, gdy zadanie jest otwarte. Poniżej znajduje się tabela z kolumnami **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** i **Error**.

Statusy wierszy: `pending`, `processing`, `done`, `failed`, `skipped` (ciąg pasował do wzorca wykluczenia albo był już przetłumaczony) i `rolled_back`.

Przyciski:

- **Process slice** - przetwarza jedną porcję o wielkości **Batch size** i zatrzymuje się. Komunikat: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** Gdy nie ma już nic do zrobienia, pojawia się komunikat **The job has no more strings waiting.**
- **Auto-process** - powtarza porcje, aż zadanie się skończy albo zatrzyma je błąd. Działa w przeglądarce, więc karta musi pozostać otwarta. Zamknięcie karty zatrzymuje pętlę. Zadanie zostaje, a dokończyć je można przyciskiem **Process slice** albo adresem cron.
- **Pause** - komunikat: **Job paused. It will not translate more strings until you resume it.**
- **Resume** - komunikat: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.**
- **Retry failed** - nieudane ciągi wracają do oczekiwania, a zadanie znowu czeka. Komunikat: **Retried N failed items.**
- **Rollback** - pyta **Roll back this job?** i przywraca poprzednie tłumaczenie tam, gdzie moduł zapisał kopię przed zmianą. Komunikat: **Rollback: restored N translations.**
- **Error CSV** - pobiera nieudane wiersze. Kolumny: id, domain, locale, source, error.
- **Failed only** - pokazuje tylko nieudane wiersze.
- **Review queue** - otwiera **Review** (punkt 3.6).

Ekran zadania nie ma przycisku Cancel. Dalsze przetwarzanie zatrzymujesz przyciskiem **Pause**.

**Automatyczna pauza**

Gdy ChatGPT odrzuca wywołania z powodu limitu, zadanie wstrzymuje się samo. Komunikat błędu to **Rate limit — job auto-paused. Resume later.** Poczekaj, a potem kliknij **Resume**. Żeby sklep zaczynał mniej wywołań w ciągu minuty, zmniejsz **Rate limit / min** w **Settings**.

Inne komunikaty na tym ekranie:

- **Nothing was translated.** i dalej **No ChatGPT API key. Nothing was translated.** Wklej klucz w **Settings**.
- **Allow publish is off in Settings.** Zadanie, które nie jest próbne, nie ruszy, dopóki nie włączysz **Allow publish / save**.
- **Monthly API budget has been exhausted.** Podnieś **Budget USD / month** albo ustaw 0.

### 3.6. Review

Otwórz **Review** albo kliknij **Review queue** na zadaniu. Nagłówek to **Needs-review queue (quality score / flags).** Lista pokazuje najnowsze wiersze, które kontrola jakości nie przepuściła automatycznie, maksymalnie 100.

![Review w angielskim zapleczu. Pusta kolejka do sprawdzenia.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-review.webp)

Kolumny: **ID**, **Score**, **Domain**, **Source**, **AI**, **Flags**, a dalej **Approve** i **Reject**. Pusta lista pokazuje **The queue is empty.**

Jak czytać wiersz:

- **Score** mieści się w przedziale od 0 do 100. Wiersze poniżej 70 trafiają do kolejki.
- **Flags:**
  - `validation_failed` - placeholdery albo HTML nie przeszły kontroli.
  - `warning` - drobniejsza uwaga kontroli.
  - `length_explosion` - tłumaczenie jest ponad dwa i pół raza dłuższe od oryginału.
  - `too_short` - tłumaczenie jest wyraźnie krótsze od dłuższego oryginału.
  - `possible_untranslated` - w tłumaczeniu zostały angielskie słowa, takie jak *the*, *and*, *with*, *your* albo *please*.
- **Source** to oryginał. **AI** to propozycja modelu.

**Approve** i **Reject** zmieniają tylko status wiersza. Pojawia się komunikat **Review updated.**, a wiersz znika z listy. Sama ta strona nie wpisuje tekstu do katalogu.

Jeśli zadanie mogło już zapisywać, propozycja może być już w sklepie. Aby cofnąć zmiany z tego zadania, użyj przycisku **Rollback** na zadaniu w **Jobs**.

### 3.7. Catalog

Otwórz **Catalog**. Tutaj tłumaczysz pola produktów, kategorii albo CMS zapisane w językach sklepu. Ta zakładka nie edytuje **International → Translations**. Jedno kliknięcie obsługuje maksymalnie 100 rekordów. Zapisane wiersze trafiają do języka docelowego.

![Catalog w angielskim zapleczu. Pola Entity, Fields, języki i przycisk Translate batch.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-catalog.webp)

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Entity** | product | Co jest czytane: **product**, **category** albo **cms**. Zmiana przeładowuje stronę i pokazuje tylko pola tej encji. Sama zmiana niczego nie tłumaczy. |
| **Fields** | wszystkie pola tej encji | Które teksty wysyła porcja. Aby zaznaczyć kilka, przytrzymaj Ctrl (na Macu Cmd). Niezaznaczone pola nie są wysyłane i zostają bez zmian. Produkt: **Title**, **Short description**, **Description**, **Meta title**, **Meta description** i **Friendly URL**. Kategoria: **Title**, **Description**, **Meta title**, **Meta description** i **Friendly URL**. CMS: **Title**, **Meta description**, **Meta keywords**, **Content** i **Friendly URL**. **Title** produktu lub kategorii to nazwa. W CMS **Title** to tytuł strony, a **Content** to treść. Jeśli linki mają pozostać bez zmian, nie zaznaczaj **Friendly URL**. |
| **Source language** | pierwszy język sklepu | Język, z którego kopiowane są pola. Ten język nie jest zmieniany. |
| **Target language** | pierwszy język sklepu | Język, który dostaje tłumaczenie. Musi być inny niż język źródłowy. |
| **Only empty** | Yes | Pomija pola, które mają już tekst w języku docelowym. Wyłącz tę opcję tylko wtedy, gdy chcesz zastąpić istniejący tekst. Gdy jest włączona, istniejący tekst zostaje. Gdy jest wyłączona, porcja może go nadpisać, o ile publikacja jest dozwolona. |
| **Start after ID** | 0 | Pomija rekordy o ID niższym lub równym tej wartości. 0 oznacza start od pierwszego rekordu. Po każdej porcji pole ustawia się na najwyższe ID z tej porcji, także dla wierszy, które się nie powiodły. Kliknij przycisk ponownie, aby przejść dalej. Aby powtórzyć nieudany wiersz, ustaw ID z powrotem poniżej tego rekordu przed kolejnym kliknięciem. |

Przycisk: **Translate batch (max 100)**.

Kroki:

1. Wybierz **Entity** i zaznacz pola.
2. Wybierz **Source language** i **Target language**.
3. Zostaw **Only empty** włączone.
4. Kliknij **Translate batch (max 100)**. Pojawi się komunikat **Catalog finished: saved N, failed M.** Strona pokazuje też liczby **Saved** i **failed**.
5. Otwórz jeden rekord w języku docelowym i sprawdź wynik, zanim wyłączysz **Only empty** albo uruchomisz następną porcję.

Komunikaty:

- **Nothing was translated. Select at least one field.**
- **Nothing was translated. Source and target language must be different.**
- **Nothing was saved. Turn on Allow publish in Settings.**
- **Nothing was translated. There is no ChatGPT API key. Open Settings and paste the key.**
- Zmiana **Entity** pokazuje **Showing fields for {entity}. Nothing was translated.**

### 3.8. Glossary

Otwórz **Glossary**. Słownik to lista słów i zwrotów, które model ma zostawić bez zmian albo zawsze tłumaczyć tak samo. Dodanie wiersza nie zmienia tłumaczeń, które już zapisano. Kolejne tłumaczenie uwzględni listę.

![Glossary w angielskim zapleczu. Formularz dodawania terminu i lista terminów.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-glossary.webp)

**Pojedynczy termin**

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Source term** | puste, wymagane | Słowo albo zwrot w języku źródłowym. Wpisz go dokładnie tak, jak występuje w tekście, z wielkimi literami, jeśli mają znaczenie. |
| **Target locale** | puste | Ogranicza wiersz do jednego locale, na przykład pl-PL. Puste pole oznacza, że wiersz obowiązuje dla każdego języka docelowego. Wypełnione locale jest ignorowane przy innych językach. |
| **Target term** | puste | Zatwierdzone tłumaczenie. Może zostać puste tylko wtedy, gdy włączona jest opcja **Do not translate**. |
| **Do not translate** | No | Po włączeniu model kopiuje termin bez zmian, na przykład nazwę marki, SKU albo znacznik. Po wyłączeniu używa pola **Target term**. |

Kliknij **Add**. Komunikaty: **Glossary term added. Translations already stored were not changed.** albo **Nothing was added. Type a source term.**

**Tabela**

Kolumny: **Source**, **Locale**, **Target**, **Do not translate** (**Yes** albo **No**) i **Delete**. **Delete** usuwa tylko ten jeden wiersz. Komunikat: **Glossary term deleted.** Pusta lista pokazuje **No glossary terms yet.**

**CSV**

- Wybierz **CSV file** i kliknij **Import CSV**. Komunikat: **Imported N rows.** Jeśli nie wybrano pliku, zobaczysz **CSV file is missing.**, a jeśli nie da się go odczytać, **Cannot open the CSV file.**
- Pierwszy wiersz to nagłówek: `source_term`, `target_locale`, `target_term`, `do_not_translate`. Ten wiersz jest zawsze pomijany. Wiersze z mniej niż trzema kolumnami również są pomijane. W czwartej kolumnie pusta wartość albo 0 oznacza **No**, a każda inna wartość oznacza **Yes**.
- Import dodaje wszystkie wiersze, które udało się odczytać. Nie szuka istniejących terminów i ich nie nadpisuje, więc ponowny import tego samego pliku tworzy duplikaty.
- **Export CSV** pobiera bieżącą listę jako `glossary.csv`. Nie potrzebuje pliku wejściowego i nie zmienia listy.

Używaj krótkich i dokładnych terminów. Zbyt ogólny termin będzie wymuszany za każdym razem, gdy się pojawi.

### 3.9. Excludes

Otwórz **Excludes**. Wykluczenie to wzorzec tekstu źródłowego, którego moduł nie wysyła do ChatGPT. Taki tekst zostaje w sklepie bez zmian. Wzorzec działa na stronach **Manual**, **Bulk**, **Catalog** i na stronach tłumaczeń.

![Excludes w angielskim zapleczu. Pola Pattern, Type i lista wzorców.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-excludes.webp)

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Pattern** | puste, wymagane | Tekst porównywany z każdym ciągiem źródłowym. Sposób porównania zależy od pola **Type**. |
| **Type** | exact | **exact** to cały ciąg. **prefix** to początek ciągu. **contains** to fragment w dowolnym miejscu ciągu. **regex** to wyrażenie regularne PHP, stosowane dokładnie tak, jak je wpisano. Błędne wyrażenie niczego nie dopasuje. Zacznij od krótkiego wzorca i sprawdź, co zostało pominięte. Zły typ może pominąć za dużo albo nic. |

Kliknij **Add**. Komunikat: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Pusty wzorzec daje komunikat **Nothing was added. Type a pattern.**

Kolumny: **Pattern**, **Type**, **On** i **Delete**. Kolumna **On** pokazuje 1, gdy wzorzec jest aktywny. Na tym ekranie nie ma przełącznika, który wyłącza wzorzec. Jeśli chcesz przestać go stosować, kliknij **Delete**, a potrzebny wzorzec dodaj ponownie. **Delete** usuwa tylko ten wzorzec i nie kasuje istniejących tłumaczeń. Komunikat: **Pattern deleted.** Pusta lista pokazuje **No patterns yet.**

Wykluczeń używaj do tekstu, który ma zostać w języku źródłowym, na przykład do nazwy prawnej albo tokenu technicznego. Jeśli termin ma być zawsze tłumaczony w ten sam sposób, użyj **Glossary**.

### 3.10. History

Otwórz **History** albo kliknij **See all** na **Dashboard**.

![History w angielskim zapleczu. Lista żądań.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-history.webp)

**History** to pełna lista zapisanych wywołań ChatGPT: uruchomienia ręczne, strona tłumaczeń, zadania masowe, porcje katalogu i test połączenia. Każdy wiersz zawiera prompt, odpowiedź, model, języki, liczbę tokenów i czas wywołania. Karty i wykresy znajdziesz na **Dashboard**. Samo otwarcie tej strony nie wysyła nowego żądania i nie zmienia tłumaczeń.

Filtry są takie same jak na **Dashboard** (punkt 3.2).

Kolumny: **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** i **Prompt**. Typy wpisów: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** oraz **Not sent**. Ostatni typ oznacza, że wywołanie nie zostało wysłane, na przykład przez lokalny limit albo budżet. Wiersz **Bulk job** pokazuje numer zadania.

- **View** otwiera prompt i odpowiedź wraz z **HTTP**, **Sent**, **Received** i **Total**. Przy błędzie odpowiedzią jest tekst błędu. **Back to the list** wraca do tabeli. Jeśli wiersza już nie ma, zobaczysz **This history row no longer exists.**
- Błąd dostępu oznacza, że klucz w **Settings** jest nieprawidłowy albo konto nie ma dostępu do wybranego modelu.
- **Previous**, **Next** i **Page** służą do przeglądania listy.
- **Clear history** pyta **Clear the stored history? Saved translations stay.** Po wykonaniu pojawia się komunikat **History cleared. Saved translations were not changed.** Podpowiedź przycisku mówi: **Clear history deletes these rows only. Saved translations stay.**

Pusta lista pokazuje **No requests yet.**

Jeśli tłumaczenia nagle przestają działać, otwórz tutaj najnowszy wiersz błędu, zanim zmienisz słownik.

### 3.11. Updates

Otwórz **Updates** z prawej strony paska modułu. Tytuł formularza to **MyPresta Updates**.

![Updates w angielskim zapleczu. Sekcje Manual Check, Automatic Notifications i Product Page.](https://mypresta.eu/docs/images/docs/myaitranslationsgpt-updates.webp)

- **Manual Check** zawiera przycisk **Check Now**. Sprawdza wersję od razu.
- **Automatic Notifications** może mieć wartość **Enabled** albo **Disabled**. Domyślnie jest **Enabled**, dopóki nikt nie zapisał wyboru. Gdy opcja jest włączona, moduł sprawdza, czy MyPresta ma nowszą wersję, i może pokazać ostrzeżenie w zapleczu.
- **Product Page** to odnośnik do strony kontaktowej używanej przez ten moduł.
- **Save** zapisuje wybór. Komunikat: **Update settings saved.**

Po kliknięciu **Check Now** zobaczysz **New version available!** albo **Module is up to date!**

### 3.12. Przyciski na stronie International → Translations

Otwórz **International → Translations**. Przyciski przy polach pojawiają się, gdy włączone jest **Individual field buttons — International → Translations**. Pola wyboru i pasek pojawiają się, gdy włączone jest **Individual field checkboxes — International → Translations**.

Co zobaczysz:

- Przycisk **Translate** przy każdym polu tekstowym.
- Pole wyboru przy każdym polu, gdy pola wyboru są włączone.
- Pasek **ChatGPT translations** z polami **Source** (en-US albo **Source locale** z **Settings**) i **Target**, a także przyciskami **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** oraz podpowiedzią **Fills the fields. Save with the PrestaShop button.** Przycisk **Translate empty in this section** wypełnia puste pola w bieżącej sekcji.

Kroki:

1. Wybierz **Target**.
2. Zaznacz pola albo kliknij **Check empty**.
3. Kliknij **Translate selected** albo **Translate empty**.
4. Poczekaj, aż pasek pokaże **Done**. W trakcie pracy status to **Translating…** z licznikiem. Jeśli niczego nie zaznaczysz, pasek pokaże **Tick at least one field.**
5. Sprawdź wypełnione pola i zapisz stronę przyciskiem **Save** PrestaShop.

Te przyciski tylko wypełniają pola. Bez przycisku **Save** PrestaShop tekst nie trafi do sklepu. Gdy **Allow publish / save** jest wyłączone, pola i tak się wypełniają, a zapisuje je dopiero przycisk **Save** PrestaShop.

Komunikaty:

- **Target is not a language from this shop.**
- **Fill the source language field first.**
- **The source language field is not on this page.**
- **The source language mail file was not found.** W sekcji **Emails** tekst źródłowy pochodzi z pliku szablonu poczty, a nie z pola na stronie. Wybierz inne **Source locale**, dla którego istnieją te pliki poczty.

### 3.13. Przyciski na formularzach produktu, kategorii i CMS

Otwórz produkt, kategorię, stronę CMS albo inny formularz sklepu z polami wielojęzycznymi. Przyciski są widoczne, gdy włączone jest **Individual field buttons — shop forms**. Pola wyboru i pasek są widoczne, gdy włączone jest **Individual field checkboxes — shop forms**.

Co zobaczysz:

- Przycisk **Translate** przy każdym polu wielojęzycznym.
- Pole wyboru dla paska.
- Pasek **ChatGPT translations** z polami **Translate from** i **to**, przyciskami **Check all**, **Uncheck all**, **Check empty**, **Translate empty** i **Translate selected** oraz podpowiedzią **Fills the fields. Save with the PrestaShop button.**

Kroki:

1. Wypełnij pole w języku źródłowym. Jeśli jest puste, pasek pokaże **Fill the source language field first.**
2. Wybierz język docelowy na pasku.
3. Kliknij przycisk przy jednym polu albo zaznacz pola i kliknij **Translate selected**. **Translate empty** wypełnia puste pola.
4. Kliknij **Save** w formularzu PrestaShop. Bez tego tekst nie zostanie zapisany.

Przycisk tylko wypełnia pole w formularzu. Pola, których nie zaznaczysz, zostają bez zmian.

## 4. Front sklepu

Moduł nie dodaje niczego na stronę, którą widzi klient. Nie ma tam bloku, przycisku ani komunikatu, więc motyw nie ma czego wyświetlać w związku z tym modułem.

Jedynym adresem spoza zaplecza jest adres cron. Służy do zadania w harmonogramie serwera, a nie do klientów.

- Skopiuj go z **Settings** (pole **CRON URL**) albo z linii **CRON** na **Dashboard**.
- Wklej go w harmonogramie serwera, na przykład co kilka minut. Każde wywołanie przetwarza jedną porcję czekającego zadania.
- Jeśli sklep działa na SSL, używaj adresu `https://`.

| Co zobaczysz po otwarciu adresu | Co zrobić |
|---|---|
| **Forbidden** | Adres jest niepełny albo został zmieniony. Skopiuj go ponownie z **Settings**. |
| **No pending jobs** | Nie ma zadania w stanie `pending` ani `running`. Utwórz je na **Bulk** albo wznów wstrzymane zadanie na **Jobs**. |
| Wynik JSON z polami `ok`, `finished` i `counts` | Jedna porcja została przetworzona. Postęp sprawdzisz na **Jobs**. |

Adres cron przetwarza tylko zadania w stanie `pending` i `running`. Zadanie `paused` trzeba wznowić na **Jobs**.

## 5. Problemy

| Co widzisz | Przyczyna | Co zrobić |
|---|---|---|
| **No ChatGPT API key.** na każdej stronie modułu | Klucz nie został zapisany. | Otwórz **Settings**, wklej klucz w pole **ChatGPT API key** i kliknij **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Ustawienia zapisano bez klucza. | Wklej klucz i kliknij **Save**. |
| **Connection was not made. Nothing was translated.** po **Test connection** | Nieprawidłowy klucz, brak połączenia z OpenAI albo model, do którego konto nie ma dostępu. | Sprawdź klucz, wybierz inny **Model** albo dodaj właściwy identyfikator w **Add a ChatGPT model**. Przeczytaj wiersz na **History**. |
| Błędy dostępu na **History** | Klucz jest nieprawidłowy albo konto nie ma dostępu do wybranego modelu. | Popraw klucz albo wybierz model, do którego konto ma dostęp. |
| **Nothing was started. There is no ChatGPT API key.** na **Bulk** | Brak klucza. | Wklej klucz w **Settings**, a potem ponownie uruchom **Estimate** i **Start job**. |
| Zadanie zostaje w stanie `pending` | Zadanie nie startuje samo. | Kliknij **Process slice** albo **Auto-process** na **Jobs**, albo skonfiguruj adres cron (rozdział 4). |
| Zadanie jest `paused` z komunikatem **Rate limit — job auto-paused. Resume later.** | ChatGPT odrzucił wywołania z powodu limitu. Na **History** może też być **ChatGPT rate limit (429). Try again later.** | Poczekaj kilka minut i kliknij **Resume**. Zmniejsz **Batch size** albo **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | Wykorzystano **Budget USD / month**. | Podnieś kwotę albo ustaw 0. Nowy miesiąc zaczyna od zera. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** jest wyłączone. | Włącz **Allow publish / save**. |
| **Not saved because of broken placeholders or HTML: N.** na **Manual** | Tłumaczenie zmieniło placeholdery albo znaczniki HTML. | Popraw wiersz w **Review before save**, tak aby placeholdery i znaczniki zgadzały się ze źródłem, a potem kliknij **Save approved**. |
| Zadanie kończy się statusem `completed_with_errors` | Część ciągów się nie powiodła. | Otwórz zadanie, kliknij **Failed only**, pobierz **Error CSV**, a potem kliknij **Retry failed**. |
| Wiersz jest na **Review** | Wynik jest poniżej 70, kontrola długości nie przeszła albo placeholdery nie przeszły kontroli. | Przeczytaj **Flags**. **Approve** i **Reject** zmieniają tylko kolejkę. Jeśli tekst został już zapisany, użyj **Rollback** na zadaniu. |
| **The shop needs at least two languages.** | Sklep ma tylko jeden język. | Dodaj język w **International → Localization → Languages**, a potem ponownie otwórz moduł. |
| Brak przycisków na formularzu produktu | Przełączniki dla formularzy sklepu są wyłączone. | W **Settings** włącz **Individual field buttons — shop forms** oraz, jeśli chcesz pasek, **Individual field checkboxes — shop forms**. |
| Strona tłumaczeń nie pokazuje paska | Przełączniki dla strony tłumaczeń są wyłączone. | Włącz oba przełączniki **International → Translations** w **Settings**. |
| **Max tokens** nie zmienia długości odpowiedzi | Żądanie tłumaczenia nie wysyła tej liczby. | Zostaw 0. Aby skrócić pojedynczy wynik, edytuj go przed kliknięciem **Save approved**. |
| Import CSV słownika tworzy duplikaty | Import dodaje wiersze i nie nadpisuje istniejących terminów. | Usuń dodatkowe wiersze albo wyeksportuj listę, wyczyść plik, usuń stare wiersze i zaimportuj plik raz. |

## 6. Dla developera

### 6.1. Przegląd

- Klasa główna: `myaitranslationsgpt`, plik `myaitranslationsgpt.php`.
- Wersja: 1.2.0.
- Nazwa techniczna: `myaitranslationsgpt`. Nazwa na liście modułów: **AI Translations with ChatGPT**.
- Autor: MyPresta.eu. Zakładka w Module Manager: `administration`.
- Zakładka zaplecza: `AdminMyaitranslationsgpt`, rodzic `AdminInternational`, zapasowy rodzic `IMPROVE`. Widoczna etykieta to `AI Translations with ChatGPT`. Metoda `ensureTab()` naprawia brakującą zakładkę, a `renameTabIfTechnical()` zamienia nazwę zakładki, jeśli nadal jest nazwą techniczną.
- Instalacja: `parent::install()`, tabele z `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), `installDefaults()` (zapisuje klucz tylko wtedy, gdy go brakuje), hooki `displayBackOfficeHeader` i `actionAdminControllerSetMedia`, a na końcu zakładka.
- Odinstalowanie: usuwa zakładkę, wykonuje `sql/uninstall.php` (kasuje 11 tabel), a `removeConfiguration()` kasuje klucze `MYAITGPT_*` wymienione w tej metodzie. Następnie wywoływane jest `parent::uninstall()`. Nie kasuje tabel `mypresta_updates`, `update_myaitranslationsgpt` ani `updatev_myaitranslationsgpt`.
- Moduł nie ma metod `enable()` ani `disable()`.
- `getContent()` wywołuje `ensureTab()` i przekierowuje do `AdminMyaitranslationsgpt` (domyślna zakładka to `dashboard`).

Przepływ danych:

1. Formularz ustawień wysyła POST do `AdminMyaitranslationsgptController::initContent()`.
2. `ConfigService::saveFromForm()` zapisuje wartości `MYAITGPT_*` w `Configuration`. `ApiKeyEncryptor` szyfruje klucz API algorytmem AES-256-CBC. Klucz szyfrujący to `hash('sha256', _COOKIE_KEY_ . '|myaitranslationsgpt|v1', true)`. Zapisana wartość ma prefiks `MYAITGPT1:`. Pusty klucz albo wartość zamaskowana nie nadpisuje zapisanego klucza.
3. Tłumaczenie: `TranslateService::translateMessages()` buduje prompty (`PromptBuilder`), wysyła je przez `OpenAiTranslationProvider` (cURL POST na `https://api.openai.com/v1/chat/completions`, nagłówek `Authorization: Bearer`), sprawdza odpowiedź (`PlaceholderValidator`, `HtmlValidator`, `PsNativeValidator`), ocenia ją (`QualityScorer`) i zapisuje przez `TranslationAdapter`.
4. `translateBatch()` wysyła `temperature` z ustawień, ale nie wysyła `max_tokens`. Test połączenia (`ping`) wysyła `max_tokens` równe 5 i `temperature` równe 0. `MYAITGPT_MAX_TOKENS` jest zapisywany, ale `translateBatch()` go nie odczytuje.
5. Zapis katalogu używa usługi tłumaczeń PrestaShop, jeśli ona istnieje. W przeciwnym razie zapisuje do tabeli `_DB_PREFIX_translation`. Klucze klasycznych modułów zapisuje `LegacyModuleCatalogue` w pliku `translations/{iso}.php` danego modułu.
6. Bulk: `BulkJobFactory` wstawia wiersze do `myaitgpt_job` i `myaitgpt_job_item`. Pusta lista domen nie tworzy pozycji, z wyjątkiem klasycznego modułu, który używa `LegacyModuleCatalogue::DOMAIN`. `JobWorker::processSlice()` wykonuje jedną porcję o wielkości `BATCH_SIZE`. Wywołują ją przycisk **Process slice**, pętla **Auto-process** (AJAX `ProcessJob`) oraz `controllers/front/cron.php`.
7. Catalog: `CatalogTranslateService::collect()` jest wywoływane z limitem 100. `translateAndSave()` zapisuje do `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` albo `_DB_PREFIX_cms_lang`. Wyniki są dopasowywane po ID. Po porcji **Start after ID** przyjmuje wartość najwyższego `id_entity` w zebranym zbiorze, łącznie z wierszami nieudanymi.
8. Każde wywołanie trafia do `myaitgpt_request` (**History**). Błędy zapisywane są też w `myaitgpt_api_log` (kolumna `provider` ma domyślnie wartość `openai`). Koszt trafia do `myaitgpt_usage_ledger`. `SnapshotService` kopiuje poprzednią wartość do `myaitgpt_snapshot`, żeby możliwy był **Rollback**. `clearTranslationCache()` wywołuje `Tools::clearCache()` po zapisie katalogu, po porcji, która nie jest próbna, i po wycofaniu zmian.

`QualityScorer` startuje od 100. `validation_failed` odejmuje 40 punktów, a każde ostrzeżenie odejmuje 5. Stosunek długości powyżej 2,5 ustawia `length_explosion` i odejmuje 20 punktów. Stosunek poniżej 0,3, gdy źródło ma więcej niż 20 znaków, ustawia `too_short` i odejmuje 15 punktów. Angielskie słowa *the*, *and*, *with*, *your* albo *please* ustawiają `possible_untranslated` i odejmują 10 punktów. Wiersz wymaga recenzji, gdy wynik jest poniżej 70 albo gdy ustawiono `validation_failed` lub `length_explosion`.

### 6.2. Pliki

| Plik | Rola |
|---|---|
| `myaitranslationsgpt.php` | Instalacja, odinstalowanie, zakładka, hooki, zasoby, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Sprawdzanie aktualizacji dla zakładki **Updates** i ostrzeżeń w zapleczu. Klasa `myaitranslationsgptUpdate`. |
| `logo.png`, `logo.gif` | Logo w nagłówku modułu. |
| `controllers/admin/AdminMyaitranslationsgptController.php` | Każda zakładka zaplecza, zapisy, akcje zadań, słownik, wykluczenia, katalog, CSV i AJAX. |
| `controllers/front/cron.php` | Adres cron. Przetwarza jedną porcję i zwraca JSON. |
| `sql/install.php`, `sql/uninstall.php` | Tworzenie i usuwanie tabel. |
| `src/Adapter/TranslationAdapterInterface.php` | Interfejs odczytu i zapisu tłumaczeń PrestaShop. |
| `src/Adapter/AbstractTranslationAdapter.php` | Sekcje, domeny, locale, zapis przez usługę albo tabelę `translation`, czyszczenie pamięci podręcznej. |
| `src/Adapter/TranslationAdapter.php` | Konkretny adapter. |
| `src/Adapter/TranslationAdapterFactory.php` | Tworzy adapter. |
| `src/Adapter/FilesystemCatalogueTrait.php` | Czyta katalogi XLF z motywów i modułów. |
| `src/Adapter/LegacyModuleCatalogue.php` | Klasyczne moduły: odczyt i zapis `translations/{iso}.php`. |
| `src/Admin/MyaitgptForms.php` | Formularze zaplecza i teksty `desc` pól. |
| `src/Admin/MyaitgptSectionHelp.php` | Tekst panelu **Help** dla każdej zakładki. |
| `src/Audit/RequestLogRepository.php` | **History**: wiersze, karty, wykresy, filtry, czyszczenie i retencja. |
| `src/Audit/ApiLogRepository.php` | Dziennik błędów i ostrzeżeń API oraz retencja. |
| `src/Audit/TranslationMemory.php` | Ponowne użycie wyniku dla tego samego tekstu, locale, modelu i słownika. |
| `src/Audit/UsageLedger.php` | Szacunek kosztu i miesięczny budżet. |
| `src/Audit/SnapshotService.php` | Kopie przed zapisem i przywracanie przy **Rollback**. |
| `src/Glossary/GlossaryRepository.php` | Lista słownika: wstawianie i usuwanie. |
| `src/Glossary/ExcludePatternRepository.php` | Wstawianie, usuwanie i dopasowywanie wykluczeń. |
| `src/Job/JobStatuses.php` | Stałe statusów zadań i wierszy. |
| `src/Job/JobRepository.php` | Zadania i wiersze: odczyt, status, następna porcja, liczniki. |
| `src/Job/JobWorker.php` | Przetwarzanie porcji, ponawianie, zakończenie zadania, kolejka recenzji i e-mail o zakończeniu. |
| `src/Provider/TranslationProviderInterface.php` | Interfejs dostawcy. |
| `src/Provider/OpenAiTranslationProvider.php` | Wywołania ChatGPT, test połączenia i dziennik żądań. |
| `src/Provider/PromptBuilder.php` | Prompty systemowe i użytkownika: ton, głos marki, słownik. |
| `src/Provider/ProviderFactory.php` | Tworzy dostawcę. |
| `src/Quality/PlaceholderValidator.php` | Kontrola placeholderów i znaczników. |
| `src/Quality/HtmlValidator.php` | Kontrola HTML. |
| `src/Quality/PsNativeValidator.php` | Kontrola przed zapisem na **Manual**. |
| `src/Quality/EmailHtmlPipeline.php` | Chroni HTML wiadomości e-mail przed wysłaniem do API i przywraca go po odpowiedzi. |
| `src/Quality/QualityScorer.php` | Wynik 0-100, flagi i decyzja o recenzji. |
| `src/Security/ApiKeyEncryptor.php` | Szyfrowanie i odszyfrowywanie klucza API. |
| `src/Service/ConfigService.php` | Odczyt i zapis ustawień, modele, token cron, zakresy wartości. |
| `src/Service/RateLimiter.php` | Lokalny limit na minutę, plik `var/rate_limit.json`. |
| `src/Service/TranslateService.php` | Wykluczenia, pamięć, wywołania, walidacja, ocena, zapis i szacunek. |
| `src/Service/BulkJobFactory.php` | Buduje zadanie **Bulk** i szacunek. |
| `src/Service/CatalogTranslateService.php` | Zbiera i zapisuje wiersze **Catalog**. |
| `src/Service/DashboardService.php` | Liczniki pokrycia na **Dashboard**. |
| `translations/*.php` | Tłumaczenia interfejsu, jeden plik na język. |
| `views/templates/admin/configure.tpl` | Strona modułu i szuflada **Help**. |
| `views/templates/admin/_partials/*.tpl` | Zakładki: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review` i `settings`. |
| `views/css/admin.css` | Style zaplecza. |
| `views/js/admin.js` | Postęp na **Jobs** i **Auto-process**, zaznaczanie wierszy, AJAX. Pokazuje **Brand voice** tylko wtedy, gdy **Tone** ma wartość **Brand**, a **Notify email** tylko wtedy, gdy powiadomienia e-mail są włączone. |
| `views/js/admin-help.js` | Panel **Help**. |
| `views/js/translations-tool.js` | Przyciski i pasek na **International → Translations**. |
| `views/js/entity-fields.js` | Przyciski i pasek na formularzach produktu, kategorii i CMS. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Wykresy na **Dashboard**. |
| `var/rate_limit.json` | Licznik lokalnego limitu na minutę. |
| `index.php` w każdym katalogu | Blokuje wyświetlanie listingu katalogu. |

### 6.3. Kontrolery

**Zaplecze: `AdminMyaitranslationsgptController`** (`ModuleAdminController`).

- URL: `index.php?controller=AdminMyaitranslationsgpt&token=…`, opcjonalnie `&myaitgpt_tab=` z wartościami `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs` (etykieta zakładki to **History**), `settings` i `updates`.
- Akcje zadania, parametr `job_action` oraz `id_job`: `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback` i `export_errors`. Szablon nie rysuje przycisku Cancel. `filter_failed=1` ogranicza tabelę wierszy. Akcja `cancel` ustawia zadanie na `cancelled` i zostawia czekające ciągi nieprzetłumaczone. Komunikat: **Job cancelled. Strings still waiting were not translated.**
- Akcje recenzji: `review_action=approve|reject` oraz `id_review`.
- Słownik: `delete_glossary`. Wykluczenia: `delete_exclude`. Modele: `delete_openai_model` oraz POST `new_openai_model` z `submitMyaitranslationsgptAddModel`.
- CSV słownika: `importGlossaryCsv()` pomija nagłówek i każdy wiersz z mniej niż trzema kolumnami, a pozostałe wiersze wstawia. Nie aktualizuje istniejących terminów.
- AJAX: `displayAjaxProcessJob`, `displayAjaxJobStatus`, `displayAjaxHistoryDetail`, `displayAjaxTranslatePageLines`, `displayAjaxMailSource` i `displayAjaxListDomains`.

**Front: `MyaitranslationsgptCronModuleFrontController`** (`controllers/front/cron.php`).

- URL w sklepie: `module/myaitranslationsgpt/cron`.
- Parametr `token` musi zgadzać się z `MYAITGPT_CRON_TOKEN` (porównanie przez `hash_equals`). Brak tokenu albo zły token zwraca HTTP 403 i JSON `{"ok":false,"error":"Forbidden"}`.
- Opcjonalny parametr `id_job` przetwarza wskazane zadanie. Bez niego przetwarzane jest pierwsze zadanie w stanie `pending` albo `running`.
- Udana porcja zwraca JSON z polami `ok`, `finished` i `counts`. Gdy żadne zadanie nie czeka, treść to `{"ok":true,"message":"No pending jobs"}`.
- Kontroler ma ustawione `ssl` na true.

### 6.4. Hooki

Zarejestrowane hooki:

- `displayBackOfficeHeader` - zmienia techniczną etykietę zakładki, a następnie ładuje CSS i JS.
- `actionAdminControllerSetMedia` - ładuje te same zasoby.

`translations-tool.js` jest dodawany do kontrolera tłumaczeń. `entity-fields.js` jest dodawany do formularzy sklepu, gdy przełączniki pól są włączone. `Media::addJsDef` udostępnia obiekt `myaitgptTr` (adres AJAX, locale źródłowe, języki i etykiety paska). Etykieta paska to **ChatGPT translations**.

Moduł nie rejestruje własnego hooka, który inne moduły mogłyby implementować. Nie ma metod `enable()` ani `disable()`.

### 6.5. Nadpisania

Moduł nie nadpisuje żadnej klasy ani kontrolera PrestaShop.

### 6.6. Baza

| Tabela | Zawartość |
|---|---|
| `myaitgpt_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, ID sklepu i daty. |
| `myaitgpt_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitgpt_job` | Jedno uruchomienie masowe: locale, `scope_json`, `policy_json`, `dry_run`, liczniki, sumy tokenów, koszt, pracownik, błąd i znaczniki czasu. |
| `myaitgpt_job_item` | Jeden ciąg zadania: domena, klucz, motyw, locale, źródło, poprzednia wartość, nowa wartość, status, powód pominięcia, błąd, tokeny i walidacja. |
| `myaitgpt_memory` | Pamięć tłumaczeń: hash, źródło, locale, tłumaczenie, model i liczba trafień. |
| `myaitgpt_usage_ledger` | Dzienne wiersze tokenów i kosztu, opcjonalnie ID zadania i model. |
| `myaitgpt_snapshot` | Wartość sprzed zapisu zadania, używana przez **Rollback**. |
| `myaitgpt_api_log` | Wiersze błędów i ostrzeżeń: poziom, dostawca (domyślnie `openai`), kod HTTP, komunikat i kontekst. |
| `myaitgpt_request` | Wiersze **History**: typ, status, model, locale, kod HTTP, czas, tokeny, koszt, pracownik, zadanie, prompt, odpowiedź i błąd. |
| `myaitgpt_review` | Kolejka recenzji: pozycja zadania, status, wynik, flagi i pracownik. |
| `myaitgpt_catalog_item` | Wiersze porcji katalogu: encja, pole, języki, źródło, poprzednia wartość, nowa wartość, status i błąd. |

Odinstalowanie usuwa wszystkie jedenaście tabel. Instalacja używa `CREATE TABLE IF NOT EXISTS`, więc ponowna instalacja na bazie, która nadal ma tabele, zachowuje ich wiersze. Zwykłe odinstalowanie usuwa je wcześniej. Żadna kolumna nie jest dodawana przy pierwszej wizycie na stronie.

### 6.7. Klucze i tłumaczenia

Wszystkie klucze mają prefiks `MYAITGPT_`. Poniżej wartości, które moduł przyjmuje, gdy klucza brakuje (także wartości zapisane przy instalacji):

| Klucz | Wartość, gdy klucz brakuje |
|---|---|
| `API_KEY_ENC` | puste |
| `MODEL` | `gpt-4.1-mini` |
| `EXTRA_MODELS` | puste |
| `PROVIDER` | `openai` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | puste |
| `BATCH_SIZE` | `25` (przy zapisie ponownie przycinany do zakresu 1-100) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | puste |
| `TEMPERATURE` | `0.2` (przy zapisie ponownie przycinany do zakresu 0-1) |
| `DRY_RUN_SAMPLE` | `10` (przy zapisie ponownie przycinany do zakresu 1-50) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (minimum 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | puste |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (tylko zapis; `translateBatch()` tej wartości nie wysyła) |
| `CRON_TOKEN` | 16 losowych bajtów zapisanych jako hex, generowane przy instalacji |

`removeConfiguration()` kasuje też pozostałe nazwy `DEEPL_API_KEY` i `CLAUDE_API_KEY` pod tym samym prefiksem. Nie kasuje kluczy sprawdzania aktualizacji.

Opisy pól to ciągi `desc` w `src/Admin/MyaitgptForms.php`, budowane przez `help()` z trzech części: celu, sposobu ustawienia i efektu. Pomoc dla **Max tokens** zaleca zostawienie 0, czyli domyślnej wartości ChatGPT. Żądanie ignoruje zapisaną wartość. Pomoc zakładek znajduje się w `src/Admin/MyaitgptSectionHelp.php`.

Ciągi interfejsu przechodzą przez `$this->l()` albo `{l s=... mod='myaitranslationsgpt'}`. Nowy język dodajesz plikiem `translations/{iso}.php`. Komunikaty **Rate limit — job auto-paused. Resume later.**, **Allow publish is off in Settings.**, **No ChatGPT API key. Nothing was translated.** i **Monthly API budget has been exhausted.** to angielskie ciągi zwracane przez `JobWorker` i `TranslateService`, a nie wywołania `$this->l()`. Ciągi **Updates** korzystają z domeny tłumaczeń `updatechecker`. `OpenAiTranslationProvider` zwraca **ChatGPT rate limit (429). Try again later.** przy kodzie HTTP 429.

### 6.8. Rozszerzanie

Front sklepu nie renderuje szablonu modułu, więc motyw nie ma czego nadpisać.

Szablony zaplecza znajdują się w `views/templates/admin/`. PrestaShop nie pozwala nadpisywać tych szablonów administracyjnych w motywie. Etykiety zmienisz w `translations/{iso}.php`. Przyciski na stronie **International → Translations** i w formularzach sklepu wstrzykują pliki `views/js/translations-tool.js` i `views/js/entity-fields.js` z obiektem `myaitgptTr`. Nie ma hooka, dzięki któremu motyw mógłby zastąpić ten pasek.

## 7. Pomoc

Strona modułu: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-chatgpt.html

Aby napisać w sprawie tego modułu, zaloguj się na konto klienta na mypresta.eu, otwórz formularz kontaktowy i wybierz **Support for paid modules**. Formularz informuje, że w przypadku modułów płatnych wymagane jest zalogowanie. Po zalogowaniu wybierz ten moduł z historii zakupów.
