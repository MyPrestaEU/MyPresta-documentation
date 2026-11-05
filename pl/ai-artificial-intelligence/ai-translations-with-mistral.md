---
title: "AI Translations with Mistral – dokumentacja i instrukcja użytkownika"
description: "Instrukcja konfiguracji i rozwiązywania problemów dla osób, które mają moduł AI Translations with Mistral."
sidebar:
  label: "AI Translations with Mistral – dokumentacja i instrukcja użytkownika"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł AI Translations with Mistral na MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-mistral.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ai-artificial-intelligence/ai-translations-with-mistral/)
>
> ---


## 1. Wymagania

Moduł działa w PrestaShop od wersji 1.7.0.0 w górę.

- **PrestaShop:** 1.7.0.0 lub nowszy.
- **PHP:** wersja, którą wymaga Twoja wersja PrestaShop. Moduł nie podaje własnego minimum.
- **Rozszerzenia PHP:** cURL (łączenie z Mistral), OpenSSL (szyfrowanie klucza API), SimpleXML (odczyt plików tłumaczeń XLF), mbstring.
- **Inne moduły:** moduł nie wymaga żadnego innego modułu.
- **Poza sklepem:** konto w Mistral AI i klucz API, który wygenerujesz na stronie https://console.mistral.ai/api-keys. Serwer sklepu musi mieć dostęp wychodzący do `api.mistral.ai` po HTTPS.
- **Opcjonalnie:** zaplanowane zadanie na serwerze, które wywołuje adres cron (opisany w 3.1). Bez niego zadania uruchamiasz ręcznie w zakładce **Jobs**.
- **Duże katalogi:** tłumaczenie całej domeny z tysiącami tekstów oznacza wiele wywołań API i dłuższy czas pracy. Zadanie dzieli się na porcje o rozmiarze **Batch size**. Przed startem zawsze wykonaj **Estimate** w **Bulk**.
- Sklep musi mieć co najmniej dwa języki. Przy jednym języku panel administracyjny pokaże ostrzeżenie, bo nie będzie czego tłumaczyć.

## 2. Instalacja

1. Wejdź w **Modules** → **Module Manager**. Wybierz **Upload a module**, wgraj plik ZIP modułu i kliknij **Install** przy module **AI Translations with Mistral**.
2. Po instalacji pozycja **AI Translations with Mistral** pojawi się w menu **International**.
3. Instalacja nie czyści cache sklepu. Moduł sam czyści cache PrestaShop, gdy zapisuje tłumaczenie.
4. Wejdź w **AI Translations with Mistral** → **Settings** i wklej klucz Mistral. Dopóki klucza nie ma, panel pokazuje komunikat **No Mistral API key.**

**Odinstalowanie.** W **Module Manager** kliknij **Uninstall** i potwierdź komunikat **Delete this module and its data (jobs, glossary, cache)?**

- Znikają: pozycja w menu, wszystkie zadania, glosariusz, wykluczenia, historia wywołań, kolejka **Review**, zapisane kopie do cofania, zestawienie kosztów oraz ustawienia modułu (w tym klucz API).
- Zostają teksty zapisane w sklepie: tłumaczenia w katalogu PrestaShop i pliki tłumaczeń modułów klasycznych, do których moduł zapisywał. Zostają też ustawienia sprawdzania aktualizacji.
- Ponowna instalacja nie przywraca usuniętych zadań, glosariusza ani historii. Ustawia wartości domyślne i tworzy nowy adres cron.

## 3. Konfiguracja i praca w panelu

Cały moduł mieści się na jednej stronie: **International** → **AI Translations with Mistral**. Na górze są zakładki: **Dashboard**, **Manual**, **Bulk**, **Jobs**, **Review**, **Catalog**, **Glossary**, **Excludes**, **History** i **Settings**. Zakładka **Updates** jest na końcu paska. Przycisk **Help** otwiera panel z opisem bieżącej zakładki.

Nazwy pól i przycisków w tej instrukcji są takie, jak na ekranie w angielskiej wersji panelu. W innym języku zobaczysz ich tłumaczenie. Zrzuty ekranu także pochodzą z wersji angielskiej.

Na górze każdej zakładki jest jedno zdanie o tym, co zakładka robi i jaki ma skutek. Ten sam opis, podzielony na trzy części, znajdziesz też pod polami formularza. Przycisk **Help** w prawym dolnym rogu pokazuje opis bieżącej zakładki. Samo otwarcie **Help** niczego nie tłumaczy.

**Proces od początku do końca**

Tłumaczenie uruchamia pracownik sklepu w panelu administracyjnym. Klient niczego w sklepie nie uruchamia.

1. **Ustawienia.** W **Settings** wklej klucz Mistral, wybierz model i język źródłowy. Kliknij **Test connection**, a potem **Save**. Bez klucza żadna z metod nie wyśle tekstu do Mistral.
2. **Wybierz sposób pracy.**
   - Kilka zdań albo jedna domena, z przeglądem przed zapisem: **Manual** (3.3).
   - Duża domena, motyw albo moduł: **Bulk**, a potem praca na zadaniu w **Jobs** (3.4, 3.5).
   - Pola produktów, kategorii i stron CMS: **Catalog** (partia do 100 rekordów, 3.7).
   - Pojedyncze pola na stronie **International → Translations** (3.12) oraz w formularzach produktu, kategorii i CMS (3.13).
3. **Kontrola jakości.** Każdy przetłumaczony tekst jest sprawdzany. Moduł sprawdza zmienne, znaczniki i HTML. Tekst z błędem nie zostaje zapisany. Tekst z oceną poniżej 70, zbyt długi (ponad dwa i pół raza dłuższy od oryginału) albo zawierający angielskie słowa, trafia do **Review**.
4. **Zapis.** Zależy od wybranej drogi:
   - **Manual:** po **Translate selected (review)** nic nie zostaje zapisane, dopóki nie klikniesz **Save approved**. Zaznaczenie **Save now (skip review)** zapisuje poprawne wiersze od razu.
   - **Bulk:** zadanie czeka w **Jobs** i zapisuje tłumaczenia dopiero wtedy, gdy je przetworzysz (**Process slice**, **Auto-process**) albo gdy zrobi to cron. Zadanie typu dry-run niczego nie zapisuje.
   - **Catalog:** zapisuje wiersze od razu w wybranym języku docelowym.
   - **Strona International → Translations** i formularze sklepu: przyciski tylko wypełniają pola. Tekst trafia do sklepu dopiero po kliknięciu **Save** w PrestaShop.
   - Gdy **Allow publish / save** jest wyłączone, żadna z dróg nie zapisuje tekstu do sklepu.
5. **Koniec pracy.** Zadanie w **Jobs** kończy się statusem **completed** (wszystko zapisane) albo **completed_with_errors** (były błędy, patrz 3.5). Wiersze w **Review** znikają po kliknięciu **Approve** lub **Reject**. Wynik **Catalog** pokazuje, ile wierszy zapisano i ile się nie udało.

### 3.1. Strona konfiguracji modułu

Wejdź w **Modules** → **Module Manager**, znajdź **AI Translations with Mistral** i kliknij **Configure**. Otworzy się **Dashboard**. Przejdź do zakładki **Settings**.

**Settings** to jeden formularz. Pola są ułożone w kolejności opisanej poniżej. Przyciski **Save** i **Test connection** znajdziesz na dole formularza, nie na górze.

![Ustawienia: klucz, model, ton i język źródłowy. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings.webp)

![Przełączniki przycisków przy polach oraz limity. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings-fields.webp)

![Koszt, poczta, adres cron oraz przyciski Test connection i Save. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-settings-cron.webp)

**Połączenie**

| Pole | Na starcie | Co robi |
|---|---|---|
| **Mistral API key** | puste | Klucz z konta Mistral. Wklej go z https://console.mistral.ai/api-keys. Zostaw pole puste, jeśli chcesz zachować klucz, który już zapisałeś. Wpisana wartość zastępuje zapisany klucz, a puste pole go nie usuwa. Zapisany klucz widać w formie zamaskowanej. |
| **Model** | mistral-small-latest | Model Mistral, który tłumaczy. Na liście są: mistral-small-latest, mistral-medium-latest, mistral-large-latest, ministral-8b-latest, ministral-3b-latest i codestral-latest. Nowy wybór działa od następnego tłumaczenia. Jeśli Twoje konto nie ma dostępu do modelu, wywołanie się nie uda, a błąd trafi do **History**. |
| **Add a Mistral model** | puste | Pole pod listą modeli. Wpisz dokładny identyfikator modelu z konta i kliknij **Add model**. Nowy model pojawi się na liście i stanie się aktywny. Pod polem widać modele dodane ręcznie, a przy każdym z nich przycisk **Remove**. Modeli wbudowanych nie da się usunąć. |

Komunikaty po akcjach: **Model added.**, **Model removed.**, **That model is already in the list. It is now the active model.**, **Enter a model id, for example mistral-small-latest.**, **Built-in models cannot be removed.**

**Styl i język**

| Pole | Na starcie | Co robi |
|---|---|---|
| **Tone** | Formal | Dopisuje do każdego polecenia styl: **Formal** do oficjalnego tonu sklepu i panelu, **Casual** do lżejszego, a **Brand** razem z polem **Brand voice**. Nowe tłumaczenia powstają w wybranym stylu. Istniejące zostają bez zmian, dopóki ich nie wyślesz ponownie. |
| **Brand voice** | puste | Pojawia się po wybraniu **Tone: Brand**. Kilka zdań o tym, jak ma brzmieć sklep. Puste pole oznacza brak dodatkowego opisu. Tekst trafia do kolejnych poleceń, ale nie zmienia tłumaczeń, które już zapisano. |
| **Source locale** | — | Język, który model traktuje jak oryginał. Zwykle wybierasz en-US, czyli język, w którym piszesz katalogi. Znak **—** oznacza, że język źródłowy wynika z ekranu, z którego tłumaczysz. Zmiana tego pola nie zmienia domyślnego języka sklepu. |
| **Individual field buttons — shop forms** | Yes | Przycisk tłumaczenia przy każdym polu wielojęzycznym w formularzach sklepu: produkt, kategoria, CMS i inne. Każdy przycisk tłumaczy tylko swoje pole. Ustawienie **No** ukrywa te przyciski w całym sklepie. Zapisane tłumaczenia nie zmieniają się. |
| **Individual field checkboxes — shop forms** | Yes | Pola wielojęzyczne w formularzach sklepu dostają pola wyboru. Pasek na dole formularza tłumaczy zaznaczone pola jedno po drugim. Przy **No** pola wyboru i pasek znikają. |
| **Individual field buttons — International → Translations** | Yes | Przycisk przy każdym polu na stronie **International → Translations**. Formularze sklepu pozostają bez zmian. |
| **Individual field checkboxes — International → Translations** | Yes | Pola wyboru i pasek na stronie **International → Translations**. Przy **No** znikają z tej strony. |

**Limity i koszty**

| Pole | Na starcie | Co robi |
|---|---|---|
| **Batch size** | 25 | Ile tekstów idzie w jednym wywołaniu. Przy pierwszym uruchomieniu wybierz wartość od 10 do 25. Wartość mieści się w zakresie 1–100. Większa paczka oznacza mniej wywołań, a przy błędzie ponawiana jest większa porcja. |
| **Dry-run sample** | 10 | Ile przykładowych tekstów pokazuje **Estimate** w **Bulk**. Wartość mieści się w zakresie 1–50. Estymacja niczego nie zapisuje. |
| **Max tokens (0 = default)** | 0 | Limit długości jednej odpowiedzi. Wpisz 0, aby używać domyślnego limitu Mistral. Ustaw własną liczbę, gdy odpowiedzi są ucinane albo zbyt długie. Zmiana działa od następnego wywołania. |
| **Budget USD / month** | 0 | Miesięczny limit w dolarach, liczony z zestawienia kosztów. Wpisz 0, aby nie mieć limitu. Po wykorzystaniu kwoty nowe tłumaczenia się zatrzymają, a gotowa praca zostaje. |
| **Rate limit / min** | 60 | Ile wywołań API sklep może wykonać w ciągu minuty. Wpisz 0, aby wyłączyć ten lokalny limit. Wywołania ponad limit są pomijane i zapisywane w **History**. Mistral może stosować własny limit. |
| **Temperature** | 0.2 | Jak swobodnie model przeformułowuje tekst. Wartość około 0.2 trzyma się oryginału, a wartości bliżej 1 zmieniają zdania mocniej. Zakres to 0–1. Sprawdzanie zmiennych i HTML działa nadal. |
| **Log retention days** | 30 | Ile dni trzymać wpisy w **History**. Minimum to 1 dzień. Starsze wpisy znikają. Zadania, glosariusz i zapisane tłumaczenia nie są kasowane. |
| **Allow publish / save** | Yes | Czy moduł może zapisać tłumaczenie w sklepie. Przy **No** zapis jest zablokowany w **Manual** (przyciski **Save approved** i **Save now**), w **Bulk** (zadania inne niż dry-run) oraz w **Catalog**. Przyciski na stronach tylko wypełniają pola, a zapisuje je PrestaShop. |

Komunikaty po **Save**:

- **Settings saved. No translation was started.** (zielony) – ustawienia zapisane, nic nie zostało przetłumaczone.
- **Settings saved. No API key is stored, so nothing can be translated until you paste one.** (żółty) – brak klucza, wklej go.

**Poczta i cron**

| Pole | Na starcie | Co robi |
|---|---|---|
| **Email notify on complete** | No | Wysyła jeden e-mail, gdy zadanie z **Bulk** się skończy. Samo zadanie działa tak samo, zmienia się tylko wysyłka. |
| **Notify email** | puste | Adres, na który przyjdzie e-mail o zakończeniu zadania. Pole widać po włączeniu **Email notify on complete**. Sam zapis adresu nie wysyła wiadomości. |
| **CRON URL** | adres z tokenem | Adres, który serwer może wywołać, aby przetworzyć jedną porcję oczekującego zadania. Każde wywołanie przetwarza jedną porcję i kończy się. Nie publikuj tego adresu, bo każdy, kto go zna, może uruchomić porcję. Samo otwarcie **Settings** nie uruchamia żadnego zadania. |

**Test connection** sprawdza klucz i model jednym krótkim zapytaniem. Nic nie tłumaczy i nic nie zapisuje. Wynik:

- **Connection OK (N ms). No translation was started.** – połączenie działa.
- **Connection was not made. Nothing was translated.** z podanym powodem – sprawdź klucz i model.

Na start wklej klucz, wybierz model i język źródłowy, a potem kliknij **Test connection**. Pozostałe wartości zostaw domyślne, dopóki zadania działają poprawnie.

### 3.2. Dashboard

Gdzie: pierwsza zakładka **Dashboard**.

![Zestawienie braków, filtry historii i karty wywołań. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard.webp)

![Wykresy wywołań i tokenów. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard-charts.webp)

![Zestawienia oraz dziesięć ostatnich wywołań. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-dashboard-latest.webp)

Dashboard ma dwie części. Pierwsza to zestawienie brakujących tekstów, a druga to historia wywołań Mistral w formie kart i wykresów. Strona niczego nie tłumaczy i nie zmienia tekstów.

**Zestawienie brakujących tekstów**

- **Locale:** wybierz język, dla którego chcesz policzyć brakujące teksty.
- **Show:** odśwież tabelę dla wybranego języka.
- Tabela ma kolumny **Section**, **Total**, **Missing** i **Done**. Kolumna **Done** zawiera pasek postępu. Sekcje to **Back office**, **Themes**, **Installed modules**, **Emails** i **Others**. **Missing** to liczba tekstów bez tłumaczenia w tym języku.
- Po kliknięciu **Show** pojawi się komunikat **Coverage for [język]. This page only counts strings. Nothing was translated.**
- Pod tabelą jest wiersz **CRON** z adresem cron, takim samym jak w **Settings**.
- Pusta tabela oznacza, że sklep nie ma jeszcze katalogu dla tego języka. Katalog tworzysz w **International → Translations**.

**Historia wywołań**

- **Filter** działa na presetach **Today**, **7 days**, **30 days**, **This month**, **All time** oraz na polach **From**, **To**, **Model**, **Type**, **Status** (**Any**, **Success**, **Error**), **Language**, **Employee** i **Prompt or reply contains**.
- Karty pokazują: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** i **Estimated cost**. Koszt jest szacunkiem, a nie fakturą.
- Wykresy: **Requests and errors**, **Tokens sent and received**, **Requests by model**.
- Pod wykresami są pięć zestawień: **By day**, **By model**, **By type**, **By language** i **By employee**. Gdy w zakresie są wywołania, każde zestawienie jest tabelą z kolumnami **Group**, **Calls**, **Sent**, **Received** i **Total**. Gdy wywołań nie ma, zobaczysz **No requests in this range.**
- **Latest prompts** pokazuje dziesięć ostatnich wywołań. Kolumny: **When**, **Status**, **Type**, **Languages**, **Preview**. Pusta lista oznacza **No requests yet.** Przycisk **View** otwiera okno z wysłanym poleceniem i odpowiedzią, a **See all** przenosi do **History** (3.10).

Co dalej: jeśli w sekcji brakuje większości tekstów, otwórz **Manual**, żeby przetłumaczyć kilka z nich, albo **Bulk**, żeby zrobić całą domenę.

### 3.3. Manual

Gdzie: zakładka **Manual**.

![Filtr Manual. Przycisk Filter jest pod polem Search. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-manual.webp)

**Manual** tłumaczy jedną domenę albo jeden moduł, kilkadziesiąt tekstów naraz. Samo filtrowanie niczego nie zapisuje.

**Pola filtra**

| Pole | Na starcie | Co robi |
|---|---|---|
| **Section** | Back office | Wybiera katalog PrestaShop do odczytu: **Back office**, **Themes**, **Installed modules**, **Emails** lub **Others**. Zmiana sekcji odświeża stronę, pokazuje tylko pola tej sekcji i nie wywołuje Mistral. |
| **Theme** | — | Widoczne tylko dla **Themes**. Ogranicza listę do jednego motywu. Inne motywy są pomijane. |
| **Module** | — | Widoczne tylko dla **Installed modules**. Ogranicza listę do jednego modułu. Moduł bez domen (klasyczny) pokazuje wszystkie teksty naraz. |
| **Domain** | — | Grupa tekstów, taka sama jak na **International → Translations**. Wybierz ją i kliknij **Filter**. Pole jest ukryte dla modułu klasycznego i dla sekcji bez domen. |
| **Source** | en-US albo wartość z **Settings** | Język, z którego bierzesz teksty. Wybierz język, który ma już dobre tłumaczenia. |
| **Target** | pierwszy język na liście | Język, który chcesz uzupełnić. Musi istnieć w **International → Localization → Languages**. |
| **Only empty** | Yes | Pokazuje tylko teksty bez tłumaczenia. Po wyłączeniu widzisz wszystkie teksty. Zapisane tłumaczenia nie są kasowane. |
| **Search** | puste | Zostawia tylko teksty źródłowe, w których występuje wpisane słowo. |

Kroki:

1. Ustaw **Section**, **Source** i **Target**.
2. Dla **Themes** wybierz **Theme**. Dla **Installed modules** wybierz **Module**.
3. Kliknij **Filter**. Lista **Domain** się odświeży. Wybierz domenę i kliknij **Filter** jeszcze raz. Dla modułu klasycznego pomiń domenę: **Filter** wczyta wszystkie teksty modułu.
4. Zaznacz wiersze. Do zaznaczania służą **Check all**, **Uncheck all** oraz pola przy wierszach.
5. Po **Filter** lista ma kolumny **Source**, **Current** i **Status** (**empty** albo **filled**). Nad listą są przyciski **Translate selected (review)** oraz pole **Save now (skip review)**.
6. Kliknij **Translate selected (review)**. Pojawi się tabela **Review before save** z kolumnami: pole wyboru, **Source**, **AI proposal** i **Warnings**. Poprawne wiersze są zaznaczone. Odznacz te, których nie chcesz, a w razie potrzeby popraw propozycję w polu. Kliknij **Save approved**, aby zapisać zaznaczone wiersze.
7. Zamiast kroku 6 możesz przed tłumaczeniem zaznaczyć **Save now (skip review)**. Wtedy poprawne wiersze zapisują się od razu, bez tabeli przeglądu.

**Komunikaty**

- **Loaded N strings. Tick the rows you want, then press Translate selected. Nothing is saved yet.** – lista gotowa.
- **No strings match this filter. Nothing was sent to Mistral.** – zmień filtr albo wyłącz **Only empty**.
- **Nothing was translated. Choose a domain, then press Filter to load the strings.** – wybierz domenę.
- **Nothing was translated. Tick at least one row.** – zaznacz wiersze.
- **Review is ready. Nothing is saved until you press Save approved.** – tłumaczenie gotowe, zapis dopiero po kliknięciu **Save approved**.
- **Saved. The approved strings were written for the target language.** – po **Save now (skip review)** poprawne wiersze zostały zapisane.
- **Saved N. Only the ticked rows were written.** – po **Save approved** zapisano zaznaczone wiersze.
- **Nothing was saved. Tick OK on the rows you want to keep.** – w tabeli przeglądu nie zaznaczono żadnego wiersza. Zaznacz wiersze i kliknij **Save approved** ponownie.
- **Not saved because of broken placeholders or HTML: N.** – N wierszy nie przeszło sprawdzenia i zostało pominiętych. Popraw je ręcznie w tabeli tak, aby zmienne i znaczniki HTML były takie jak w oryginale.
- **Nothing was saved. Turn on Allow publish in Settings.** – włącz **Allow publish / save**.
- **Nothing was translated. Those rows are not in the current list. Press Filter and tick them again.** – lista się zmieniła. Kliknij **Filter** i zaznacz wiersze ponownie.
- **Loaded N strings from the whole module. Tick the rows you want, then press Translate selected. Nothing is saved yet.** – moduł klasyczny, bez domen. Lista obejmuje cały moduł.
- **This module has no translation domain. Press Filter to load every string in the module. Nothing was sent to Mistral.** – ten sam przypadek, zanim klikniesz **Filter**.
- **Nothing was translated. Pick a theme, then press Filter.** / **Nothing was translated. Pick a module, then press Filter.** – wybierz motyw albo moduł.

### 3.4. Bulk

Gdzie: zakładka **Bulk**.

![Zakres zadania Bulk. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-bulk.webp)

![Polityka, próba bez zapisu oraz przyciski Start job i Estimate. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-bulk-actions.webp)

**Bulk** tworzy jedno zadanie dla wielu domen i języków. Estymacja niczego nie zapisuje. **Start job** dodaje zadanie na listę **Jobs**. Nic nie zostanie zapisane, dopóki zadanie nie zostanie przetworzone, a **Allow publish / save** jest włączone.

**Pola**

| Pole | Na starcie | Co robi |
|---|---|---|
| **Section** | Back office | Jaki katalog czyta zadanie. Ten sam wybór co w **Manual**. |
| **Theme** / **Module** | — | Pojawiają się tylko dla odpowiedniej sekcji, tak jak w **Manual**. |
| **Source** | en-US albo wartość z **Settings** | Język traktowany jako oryginał. Każdy język docelowy jest tłumaczony z tego języka. |
| **Targets** | brak | Jeden lub więcej języków do uzupełnienia. Zaznaczaj z klawiszem Ctrl (Cmd na Macu). Zwykłe kliknięcie zastępuje dotychczasowe zaznaczenie. |
| **Domains** | brak | Domeny objęte zadaniem. Zaznaczaj z Ctrl lub Cmd. Jeśli nie zaznaczysz żadnej, zadanie obejmuje wszystkie domeny wybranej sekcji. |
| **Policy** | Fill empty | **Fill empty** wysyła tylko teksty bez tłumaczenia. **Overwrite all** wysyła wszystkie, także już przetłumaczone, i może je nadpisać. **Outdated if equals source** wysyła tylko te, których tłumaczenie jest takie samo jak oryginał. |
| **Dry-run job** | No | Model wykonuje pracę, a zadanie widać na liście **Jobs**, ale odpowiedzi nie trafiają do sklepu. Dobre do sprawdzenia kosztu i jakości. |

**Kroki**

1. Wybierz sekcję, język źródłowy, języki docelowe, domeny i politykę.
2. Kliknij **Estimate**. Nad formularzem pojawi się estymacja: liczba tekstów, szacowana liczba tokenów, koszt i próbka tekstów.
3. Gdy estymacja wygląda dobrze, kliknij **Start job**. Otworzy się **Jobs** z nowym zadaniem.
4. Przetwórz zadanie w **Jobs** (3.5) albo zostaw je cronowi.

**Komunikaty**

- **Estimate only: N strings, ~N tokens, ~$X. Nothing was sent to Mistral and nothing was saved.** – wynik estymacji.
- **Job #N is waiting (N strings, est. $X). It has not run yet.** – zadanie utworzone, czeka na uruchomienie.
- **Nothing was started. Select at least one target language.** – brak języka docelowego.
- **Nothing was started. Pick a theme.** / **Nothing was started. Pick a module.** – wybierz motyw albo moduł.
- **Nothing was started. There is no Mistral API key. Open Settings and paste the key. No job was created.** – brak klucza.

### 3.5. Jobs

Gdzie: zakładka **Jobs**.

![Lista zadań. Pusta lista pokazuje No jobs yet. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-jobs.webp)

**Lista zadań**

Gdy nie ma żadnego zadania, tabela pokazuje **No jobs yet.**

Każdy wiersz to jedno uruchomienie z **Bulk**. Kolumny: **#**, **Status**, **Locales** (język źródłowy → języki docelowe), **Progress** (wykonane z wszystkich), **Cost**, **Employee** i **Date**. Przycisk **Open** otwiera zadanie.

Statusy zadania, dokładnie tak jak na ekranie:

- `pending` – czeka, nic jeszcze nie przetworzono. Nie uruchamia się samo.
- `running` – w toku.
- `paused` – wstrzymane. Nie przetwarza dalej, dopóki go nie wznowisz.
- `cancelled` – anulowane. Teksty, które jeszcze czekały, nie zostały przetłumaczone.
- `completed` – wszystkie teksty przetworzono bez błędów.
- `completed_with_errors` – zadanie zakończone, ale część tekstów się nie udała.
- `failed` – zadanie zakończyło się błędem.

**Ekran zadania**

Po otwarciu zadania widzisz nagłówek **Job #N**, status, postęp (**done/total**), liczbę **failed** i **skipped**, koszt, pracownika oraz etykietę **dry-run**, jeśli zadanie jest próbne. Pasek postępu odświeża się sam co 2–3 sekundy, dopóki zadanie jest otwarte. Tabela pod nim pokazuje wiersze zadania: **ID**, **Domain**, **Locale**, **Status**, **Source**, **New** i **Error**.

Statusy wierszy: `pending`, `processing`, `done`, `failed`, `skipped` (pominięty, bo pasuje do wykluczenia albo tekst był już przetłumaczony) oraz `rolled_back` (cofnięty).

**Przyciski**

- **Process slice** – przetwarza jedną porcję (**Batch size** tekstów) i zatrzymuje się. Komunikat: **One slice was processed. Check the rows below to see what was saved, skipped or failed.** Gdy nie ma nic do zrobienia: **The job has no more strings waiting.**
- **Auto-process** – powtarza porcje, aż zadanie się skończy albo wystąpi błąd. Działa w przeglądarce, więc tylko dopóki karta jest otwarta. Zamknięcie karty go zatrzymuje, ale zadanie zostaje i można je dokończyć kolejnym **Process slice** albo cronem.
- **Pause** – wstrzymuje zadanie. Komunikat: **Job paused. It will not translate more strings until you resume it.**
- **Resume** – wraca do kolejki. Komunikat: **Job is waiting again. It does not run by itself. Press Process slice, Auto-process, or let the cron call it.** Zadanie nie rusza samo.
- **Retry failed** – błędne teksty wracają do oczekujących, a zadanie wraca do stanu oczekiwania. Komunikat: **Retried N failed items.**
- **Rollback** – przywraca poprzednie tłumaczenie tam, gdzie moduł zapisał kopię przed zmianą. Najpierw potwierdzasz **Roll back this job?**. Po wykonaniu zobaczysz **Rollback: restored N translations.**
- **Error CSV** – pobiera plik CSV z błędnymi wierszami. Kolumny: **id**, **domain**, **locale**, **source**, **error**.
- **Failed only** – pokazuje w tabeli tylko błędne wiersze.
- **Review queue** – przechodzi do **Review** (3.6).

Na ekranie zadania nie ma przycisku anulowania. Aby je zatrzymać, użyj **Pause**.

**Automatyczne wstrzymanie**

Gdy Mistral odrzuci wywołania z powodu limitu, zadanie zatrzyma się samo ze statusem `paused`. W polu błędu pojawi się komunikat **Rate limit — job auto-paused. Resume later.** Poczekaj i kliknij **Resume**. Ustawienie **Rate limit / min** w **Settings** zmniejsza liczbę wywołań w ciągu minuty.

**Komunikaty błędów**

- **Nothing was translated.** z dopiskiem **No Mistral API key. Nothing was translated.** – brak klucza, zadanie nie rusza. Wklej klucz w **Settings**.
- **Allow publish is off in Settings.** – zadanie bez dry-run nie ruszy, dopóki nie włączysz **Allow publish / save**.
- **Monthly API budget has been exhausted.** – miesięczny budżet został wyczerpany. Zwiększ **Budget USD / month** albo ustaw 0.

### 3.6. Review

Gdzie: zakładka **Review** albo przycisk **Review queue** na ekranie zadania.

![Kolejka Review. Pusta lista pokazuje The queue is empty. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-review.webp)

Nad tabelą jest nagłówek **Needs-review queue (quality score / flags).** **Review** to lista tekstów, których kontrola jakości nie przepuściła automatycznie. Pokazuje do 100 najnowszych wierszy.

Kolumny: **ID**, **Score**, **Domain**, **Source**, **AI** (propozycja), **Flags** oraz przyciski **Approve** i **Reject**. Pusta lista pokazuje **The queue is empty.**

**Jak czytać wiersz**

- **Score** – ocena od 0 do 100. Poniżej 70 wiersz trafia do przeglądu.
- **Flags** – powody wstrzymania:
  - `validation_failed` – tekst nie przeszedł sprawdzenia zmiennych lub HTML.
  - `warning` – drobna uwaga ze sprawdzenia.
  - `length_explosion` – tłumaczenie jest ponad dwa i pół raza dłuższe od oryginału.
  - `too_short` – tłumaczenie jest wyraźnie krótsze od dłuższego oryginału.
  - `possible_untranslated` – w tłumaczeniu zostały angielskie słowa, np. the, and, with, your, please.
- **Source** – oryginalny tekst. **AI** – propozycja modelu.

**Approve** i **Reject** zmieniają tylko status wiersza. Komunikat: **Review updated.** Wiersz znika z listy. Ta akcja nie wkleja tekstu do sklepu i nie zmienia reszty domeny.

Jeśli zadanie coś zapisywało, propozycja mogła już trafić do sklepu. Aby cofnąć zmiany z zadania, użyj **Rollback** na ekranie tego zadania w **Jobs**.

### 3.7. Catalog

Gdzie: zakładka **Catalog**.

![Partia katalogu. Przycisk Translate batch (max 100) jest pod polem Start after ID. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-catalog.webp)

**Catalog** tłumaczy pola produktów, kategorii i stron CMS zapisane w językach sklepu. Nie dotyczy **International → Translations**. Jedno kliknięcie obsługuje najwyżej 100 rekordów. Zapis idzie od razu do danych wybranego języka docelowego.

**Pola**

| Pole | Na starcie | Co robi |
|---|---|---|
| **Entity** | product | Co tłumaczysz: **product**, **category** albo **cms**. Zmiana odświeża stronę i pokazuje tylko pola tego rodzaju. Sama zmiana niczego nie tłumaczy. |
| **Fields** | wszystkie pola listy | Które teksty partia wysyła. Zaznacz tylko te, które mają się zmienić. Niezaznaczone pola nie są wysyłane i nie zmieniają się. Dla produktu: **Title**, **Short description**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Dla kategorii: **Title**, **Description**, **Meta title**, **Meta description**, **Friendly URL**. Dla CMS: **Title**, **Meta description**, **Meta keywords**, **Content**, **Friendly URL**. |
| **Source language** | pierwszy język na liście | Język, z którego pobierane są teksty. |
| **Target language** | pierwszy język na liście | Język, do którego trafi tłumaczenie. Musi być inny niż źródłowy. |
| **Only empty** | Yes | Pomija pola, które mają już tekst w języku docelowym. Wyłącz tę opcję tylko wtedy, gdy chcesz zastąpić istniejący tekst. |
| **Start after ID** | 0 | Pomija rekordy o ID niższym lub równym wpisanej wartości. Po partii pole ustawia się na ostatnio przetworzone ID. Kliknij przycisk ponownie, aby przejść dalej. |

Przycisk: **Translate batch (max 100)**.

**Kroki**

1. Wybierz **Entity** i zaznacz pola.
2. Wybierz **Source language** i **Target language**.
3. Zostaw włączone **Only empty**.
4. Kliknij **Translate batch (max 100)**. Wynik ma postać: **Catalog finished: saved N, failed M.**
5. Otwórz jeden produkt w języku docelowym i sprawdź wynik. Dopiero potem wyłącz **Only empty** albo przejdź do kolejnej partii.

**Komunikaty**

- **Nothing was translated. Select at least one field.** – zaznacz pola.
- **Nothing was translated. Source and target language must be different.** – wybierz różne języki.
- **Nothing was saved. Turn on Allow publish in Settings.** – włącz **Allow publish / save**.
- **Nothing was translated. There is no Mistral API key. Open Settings and paste the key.** – brak klucza.

### 3.8. Glossary

Gdzie: zakładka **Glossary**.

![Dodawanie terminu. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-glossary.webp)

![Import i eksport CSV oraz pusta lista terminów. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-glossary-csv.webp)

Glosariusz to lista słów i fraz, które model ma zachować albo tłumaczyć zawsze w ten sam sposób. Dodanie wiersza nie zmienia zapisanych tłumaczeń, ale następne tłumaczenie będzie korzystać z listy.

**Dodawanie jednego terminu**

| Pole | Na starcie | Co robi |
|---|---|---|
| **Source term** | puste, wymagane | Słowo albo wyrażenie w języku źródłowym. Wpisz je dokładnie tak, jak występuje, z wielkimi literami, jeśli mają znaczenie. |
| **Target locale** | puste | Ogranicza wiersz do jednego języka, np. pl-PL. Puste pole oznacza, że wiersz dotyczy każdego języka docelowego. |
| **Target term** | puste | Zatwierdzone tłumaczenie terminu. Może być puste tylko wtedy, gdy włączono **Do not translate**. |
| **Do not translate** | No | Włączone: model przepisze termin bez zmian, np. nazwę marki, SKU albo znacznik. Wyłączone: model użyje **Target term**. |

Przycisk: **Add**. Komunikaty: **Glossary term added. Translations already stored were not changed.** albo **Nothing was added. Type a source term.**

**Tabela**

Kolumny: **Source**, **Locale**, **Target**, **Do not translate** (Yes albo No) oraz przycisk **Delete** przy każdym wierszu. Usuwa tylko ten wiersz. Komunikat: **Glossary term deleted.** Pusta lista: **No glossary terms yet.**

**Import i eksport CSV**

- **CSV file** – wybierz plik i kliknij **Import CSV**. Komunikat: **Imported N rows.**
- Format pliku: pierwszy wiersz to nagłówek `source_term`, `target_locale`, `target_term`, `do_not_translate`. Nagłówek jest zawsze pomijany. Wiersze z mniej niż trzema kolumnami też są pomijane. W czwartej kolumnie wartość pusta albo 0 oznacza **No**, a każda inna wartość oznacza **Yes**.
- Import dodaje wiersze z pliku. Nie sprawdza, czy taki termin już istnieje, więc ponowny import tego samego pliku doda duplikaty.
- **Export CSV** pobiera aktualną listę jako plik `glossary.csv`. Nie potrzebuje pliku wejściowego i niczego nie zmienia.

Wskazówka: używaj krótkich, dokładnych terminów. Zbyt ogólny termin będzie wymuszany przy każdym tekście, w którym się pojawi.

### 3.9. Excludes

Gdzie: zakładka **Excludes**.

![Wzorce wykluczeń. Pusta lista pokazuje No patterns yet. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-excludes.webp)

Wykluczenie to wzorzec tekstu źródłowego, którego moduł nie wysyła do Mistral. Taki tekst zostaje w sklepie bez zmian. Wykluczenia działają na każdej drodze: **Manual**, **Bulk**, **Catalog** i strony tłumaczeń.

**Dodawanie wzorca**

| Pole | Na starcie | Co robi |
|---|---|---|
| **Pattern** | puste, wymagane | Tekst albo wyrażenie porównywane z każdym tekstem źródłowym. Sposób porównania zależy od **Type**. |
| **Type** | exact | **exact** – cały tekst musi być taki sam. **prefix** – tekst zaczyna się od wzorca. **contains** – wzorzec występuje w dowolnym miejscu. **regex** – wyrażenie regularne PHP. |

Przycisk: **Add**. Komunikat: **Exclude pattern added. Matching strings will be skipped on the next run. Nothing was translated now.** Przy pustym polu: **Nothing was added. Type a pattern.**

Wzorzec typu **regex** jest stosowany dokładnie tak, jak go wpisano. Błędne wyrażenie nie pasuje do niczego. Zacznij od krótkiego wzorca i sprawdź, co pominął.

**Tabela**

Kolumny: **Pattern**, **Type**, **On** i **Delete**. Kolumna **On** pokazuje 1 przy aktywnym wzorcu. Na tym ekranie nie ma przełącznika, więc aby wyłączyć wzorzec, usuń go i dodaj ponownie. **Delete** usuwa tylko ten wzorzec i nie kasuje istniejących tłumaczeń. Komunikat: **Pattern deleted.** Pusta lista: **No patterns yet.**

Wykluczeń używaj dla tekstów, które mają zostać w języku źródłowym, np. nazwy prawnej albo technicznego znacznika. Do tekstów, które mają być zawsze tłumaczone w ten sam sposób, służy **Glossary**.

### 3.10. History

Gdzie: zakładka **History** albo przycisk **See all** na **Dashboard**.

![Lista historii. Pusta lista pokazuje No requests yet. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-history.webp)

**History** to pełna lista zapisanych wywołań Mistral: ręcznych tłumaczeń, stron tłumaczeń, zadań **Bulk**, **Catalog** i testów połączenia. Każdy wpis zawiera wysłany tekst, odpowiedź, model, języki, liczbę tokenów i czas wywołania. Karty, wykresy i filtry znajdziesz na **Dashboard**, nie na tej stronie. Samo otwarcie **History** nie wysyła żadnego zapytania i nie zmienia tłumaczeń. Zdanie pod polem **Model** w **Settings** mówi o **Logs**. Chodzi o te same wpisy, które widzisz tutaj. Osobnej zakładki Logs nie ma.

**Kolumny listy:** **ID**, **When**, **Status**, **Type**, **Model**, **Languages**, **Sent**, **Received**, **Total**, **Time** i **Prompt**. Typy wpisów: **Manual**, **Translation page**, **Bulk job**, **Catalog**, **Connection test**, **Translate** oraz **Not sent** (wywołanie nie zostało wysłane, np. przez lokalny limit albo budżet). Przy wpisie z **Bulk job** widać numer zadania.

- **View** otwiera okno z wysłanym poleceniem i odpowiedzią. Przy błędzie zamiast odpowiedzi widać komunikat o błędzie.
- Wpis z błędem dostępu oznacza, że klucz w **Settings** jest błędny albo konto nie ma prawa do wybranego modelu.
- **Previous**, **Next** i pole **Page** przechodzą między stronami listy.
- **Clear history** usuwa te wpisy. Potwierdzasz komunikatem **Clear the stored history? Saved translations stay.** Po wykonaniu zobaczysz **History cleared. Saved translations were not changed.**

Gdy tłumaczenia nagle się zatrzymują, otwórz najnowszy wpis z błędem na tej stronie, zanim zmienisz glosariusz.

### 3.11. Updates

Gdzie: zakładka **Updates** z prawej strony menu.

![Sprawdzanie aktualizacji. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-updates.webp)

Panel nazywa się **MyPresta Updates**.

- **Manual Check** – przycisk **Check Now** sprawdza wersję od razu.
- **Automatic Notifications** – **Enabled** albo **Disabled**. Po włączeniu moduł sprawdza, czy na serwerze MyPresta jest nowsza wersja, i pokazuje ostrzeżenie w panelu.
- **Product Page** – link do strony modułu.
- **Save** – zapisuje wybór **Automatic Notifications**.

Komunikaty: **Update settings saved.**, **New version available!**, **Module is up to date!**

### 3.12. Przyciski na stronie International → Translations

Gdzie: **International** → **Translations**. Wybierz typ tłumaczenia i język, a potem kliknij **Modify**. Przyciski przy polach pojawiają się, gdy w **Settings** włączono **Individual field buttons — International → Translations**. Pola wyboru i pasek pojawiają się przy włączonym **Individual field checkboxes — International → Translations**.

![Pasek Mistral translations na dole strony International → Translations. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-translations-page.webp)

**Co widzisz**

- Przy każdym polu tekstowym – przycisk tłumaczenia tego pola.
- Przy każdym polu – pole wyboru (gdy pola wyboru są włączone).
- Pasek **Mistral translations** z polem **Source** (domyślnie en-US albo wartość z **Settings**), listą **Target** i przyciskami **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected**. Pod nim jest podpowiedź **Fills the fields. Save with the PrestaShop button.**

**Kroki**

1. Wybierz **Target**.
2. Zaznacz pola, które chcesz wypełnić, albo kliknij **Check empty**.
3. Kliknij **Translate selected** albo **Translate empty**, który wypełnia puste pola w tej sekcji.
4. Poczekaj, aż pasek pokaże **Done (N)**. W trakcie zobaczysz postęp: **Translating… N/M**.
5. Sprawdź wypełnione pola. Zapisz stronę przyciskiem **Save** z PrestaShop.

Przyciski tylko wypełniają pola. Bez **Save** w PrestaShop tekst nie trafi do sklepu. Przy wyłączonym **Allow publish / save** pola też się wypełniają, a zapis wykonuje PrestaShop.

**Komunikaty**

- **Target is not a language from this shop.** – wybrany język nie istnieje w sklepie.
- **Fill the source language field first.** – uzupełnij najpierw pole języka źródłowego.
- **The source language field is not on this page.** – na tej stronie nie ma pola z językiem źródłowym.
- **The source language mail file was not found.** – nie znaleziono pliku źródłowego e-maila. Wybierz w **Settings** inny **Source locale**, dla którego są pliki e-maili.

Dla sekcji **Emails** tekst źródłowy pochodzi z pliku źródłowego szablonu e-maila, a nie z pola na stronie.

### 3.13. Przyciski w formularzach produktu, kategorii i CMS

Gdzie: formularz produktu, kategorii, strony CMS albo innego formularza sklepu z polami wielojęzycznymi. Przyciski są widoczne, gdy w **Settings** włączono **Individual field buttons — shop forms** i **Individual field checkboxes — shop forms**.

![Pasek na dole formularza produktu oraz pole wyboru przy polu wielojęzycznym. Ekran po angielsku.](https://mypresta.eu/docs/images/docs/myaitranslationsmistral-product-form.webp)

**Co widzisz**

- Przy każdym polu wielojęzycznym przycisk tłumaczenia tego pola.
- Przy polach – wybór do paska, jeśli pola wyboru są włączone.
- Pasek na dole strony produktu z etykietą **Mistral translations**, listą **Translate from … to …**, przyciskami **Check all**, **Uncheck all**, **Check empty**, **Translate empty**, **Translate selected** oraz podpowiedzią **Fills the fields. Save with the PrestaShop button.**

**Kroki**

1. Uzupełnij pole w języku źródłowym. Bez tego pasek pokaże **Fill the source language field first.**
2. Wybierz język docelowy na pasku.
3. Kliknij przycisk przy jednym polu albo zaznacz pola i kliknij **Translate selected**. **Translate empty** wypełnia puste pola.
4. Po zakończeniu kliknij **Save** w formularzu PrestaShop. Bez tego tekst nie zostanie zapisany.

Przycisk tylko wypełnia pole w formularzu. Zapisuje dopiero **Save** formularza produktu, kategorii lub CMS. Pola, których nie zaznaczysz, zostają bez zmian.

## 4. Front sklepu

Moduł nie dodaje niczego na stronie sklepu, którą widzi klient. Klient nie ma ekranu ani przycisku związanego z modułem, więc w motywie nie ma czego sprawdzać.

Jedyny adres poza panelem to adres cron. Jest przeznaczony dla zaplanowanego zadania na serwerze i nie jest do użytku przez klientów.

- **Skąd skopiować adres:** **Settings** → **CRON URL** albo **Dashboard** → wiersz **CRON**.
- **Co zrobić:** wklej adres w planerze zadań serwera, np. co kilka minut. Każde wywołanie przetworzy jedną porcję oczekującego zadania.
- **Adres działa przez HTTPS.** Jeśli sklep ma włączone SSL, używaj adresu zaczynającego się od `https://`.

| Co widać po otwarciu adresu | Co zrobić |
|---|---|
| Komunikat **Forbidden** | Adres jest niepełny albo się zmienił. Skopiuj go ponownie z **Settings**. |
| Komunikat **No pending jobs** | Nie ma zadań czekających ani uruchomionych. Utwórz zadanie w **Bulk** albo wznów wstrzymane w **Jobs**. |
| Dane w formacie JSON z wynikiem porcji (pola `ok`, `finished`, `counts`) | Zadanie przetworzyło jedną porcję. Sprawdź postęp w **Jobs**. |

Cron obsługuje tylko zadania w statusie `pending` i `running`. Zadanie `paused` musisz wznowić ręcznie.

## 5. Problemy

| Objaw (co widać) | Przyczyna | Co zrobić |
|---|---|---|
| **No Mistral API key.** na każdej stronie modułu | Klucz nie został zapisany. | Wejdź w **Settings**, wklej klucz w polu **Mistral API key** i kliknij **Save**. |
| **Settings saved. No API key is stored, so nothing can be translated until you paste one.** | Ustawienia zapisano bez klucza. | Wklej klucz w polu **Mistral API key** i kliknij **Save**. |
| **Connection was not made. Nothing was translated.** po **Test connection** | Zły klucz, brak połączenia z serwerem albo model niedostępny dla konta. | Sprawdź klucz, wybierz inny **Model** albo dodaj poprawny identyfikator w **Add a Mistral model**. Szczegóły znajdziesz w **History**. |
| Wywołania kończą się błędem dostępu w **History** | Klucz jest błędny albo konto nie może użyć wybranego modelu. | Popraw klucz albo wybierz model dostępny na koncie. |
| **Nothing was started. There is no Mistral API key.** w **Bulk** | Brak klucza. | Wklej klucz w **Settings**, a potem ponownie wykonaj **Estimate** i **Start job**. |
| Zadanie stoi w `pending` i nic się nie dzieje | Zadanie nie uruchamia się samo. | Kliknij **Process slice** albo **Auto-process** w **Jobs**. Możesz też ustawić cron (sekcja 4). |
| Zadanie w `paused` z komunikatem **Rate limit — job auto-paused. Resume later.** | Mistral odrzucił wywołania z powodu limitu. | Poczekaj kilka minut i kliknij **Resume**. Zmniejsz **Batch size** albo **Rate limit / min**. |
| **Monthly API budget has been exhausted.** | Przekroczono **Budget USD / month**. | Zwiększ kwotę albo ustaw 0. Nowy miesiąc zaczyna się od zera. |
| **Nothing was saved. Turn on Allow publish in Settings.** | **Allow publish / save** jest wyłączone. | Włącz **Allow publish / save** w **Settings**. |
| **Not saved because of broken placeholders or HTML: N.** w **Manual** | Tłumaczenie zmieniło zmienne albo znaczniki HTML. | Popraw wiersz ręcznie w tabeli przeglądu, tak aby zmienne i znaczniki były takie jak w oryginale, a potem zapisz. |
| Zadanie kończy się statusem `completed_with_errors` | Część tekstów się nie udała. | Otwórz zadanie, zaznacz **Failed only**, pobierz **Error CSV**, a potem kliknij **Retry failed**. |
| Wiersze w **Review** mają niski **Score** | Kontrola jakości ich nie przepuściła. | Przeczytaj **Source** i **AI**. Zatwierdź wiersz przyciskiem **Approve** albo odrzuć **Reject**. Jeśli zapisano błędne tłumaczenie, użyj **Rollback** w zadaniu. |
| Tłumaczenie zapisane, ale w sklepie wciąż widać stary tekst | Zapis czyści cache PrestaShop, ale motyw albo przeglądarka mogą trzymać starą stronę. | Wejdź w **Advanced Parameters** → **Performance**, wyczyść cache i odśwież stronę sklepu. |
| **Exclude pattern** nie pomija tekstu | Zły **Type** albo błędne wyrażenie **regex**. | W **Excludes** zmień typ albo usuń wzorzec i dodaj go ponownie, z krótszym tekstem. |
| Nowy termin z glosariusza nie działa w zapisanych tłumaczeniach | Glosariusz działa dla nowych tłumaczeń, a zapisane teksty nie są zmieniane. | Uruchom ponownie tłumaczenie tych tekstów w **Bulk** z polityką **Overwrite all**, po wcześniejszym sprawdzeniu w **Estimate**. |
| **The source language mail file was not found.** | Dla wybranego języka źródłowego nie ma pliku e-maila. | Wybierz w **Settings** albo na stronie tłumaczeń inny **Source locale**, dla którego są pliki e-maili. |
| **No strings match this filter. Nothing was sent to Mistral.** | Filtr nie pasuje do żadnego tekstu. | Wyłącz **Only empty**, wyczyść **Search** albo wybierz inną domenę. |
| **Nothing was translated. Tick at least one row.** | Nie zaznaczono żadnego wiersza. | Zaznacz wiersze i kliknij **Translate selected (review)**. |
| **Nothing was translated. Source and target language must be different.** w **Catalog** | Ten sam język jest źródłowy i docelowy. | Wybierz inny **Target language**. |
| Dashboard pokazuje puste zestawienie | Sklep nie ma jeszcze katalogu dla wybranego języka. | Utwórz katalog w **International → Translations** i wróć na **Dashboard**. |
| Historia zawiera wpisy **Not sent** | Wywołanie zatrzymał lokalny limit albo budżet. | Sprawdź **Rate limit / min** i **Budget USD / month** w **Settings**. |

## 6. Dla developera

### 6.1. Przegląd

- **Klasa główna:** `myaitranslationsmistral`, plik `myaitranslationsmistral.php`.
- **Wersja:** 1.2.0.
- **Nazwa techniczna:** `myaitranslationsmistral`. Na liście modułów widoczna jest jako **AI Translations with Mistral**.
- **Autor:** MyPresta.eu. Zakładka modułu w Module Manager: `administration`.
- **Zakładka w panelu:** `AdminMyaitranslationsmistral`, rodzic `AdminInternational` (zapasowo `IMPROVE`).
- **Instalacja:** `parent::install()`, tabele z `sql/install.php` (`CREATE TABLE IF NOT EXISTS`), wartości domyślne przez `installDefaults()` (ustawiane tylko brakujące klucze), rejestracja hooków `displayBackOfficeHeader` i `actionAdminControllerSetMedia`, utworzenie zakładki.
- **Odinstalowanie:** usunięcie zakładki, `sql/uninstall.php` (kasuje 11 tabel), usunięcie kluczy `MYAITMI_*` przez `removeConfiguration()`, a potem `parent::uninstall()`.
- Moduł **nie** ma metod `enable()` ani `disable()`.
- **Konfiguracja:** `getContent()` przekierowuje do `AdminMyaitranslationsmistral` (domyślnie zakładka `dashboard`).

**Przepływ danych**

1. Formularze z `MyaitmiForms` (zakładka `settings`) wysyłają wartości do `AdminMyaitranslationsmistralController::initContent()`.
2. `MyaitmiConfigService::saveFromForm()` zapisuje klucze `MYAITMI_*` w `Configuration`. Klucz API szyfruje `MyaitmiApiKeyEncryptor` (AES-256-CBC, klucz wyprowadzony z `_COOKIE_KEY_`) i zapisuje go pod `MYAITMI_API_KEY_ENC`.
3. Tłumaczenie: `MyaitmiTranslateService::translateMessages()` buduje polecenia (`MyaitmiPromptBuilder`), wysyła je przez `MyaitmiMistralTranslationProvider` (cURL, POST na `https://api.mistral.ai/v1/chat/completions`), sprawdza odpowiedź (`MyaitmiPlaceholderValidator`, `MyaitmiHtmlValidator`, `MyaitmiPsNativeValidator`), ocenia ją (`MyaitmiQualityScorer`) i zapisuje przez `MyaitmiTranslationAdapter`.
4. Zapis tłumaczenia odbywa się przez usługę `prestashop.service.translation`, a gdy jej brak, bezpośrednio w tabeli `_DB_PREFIX_translation`. Klucze modułów klasycznych (postaci `<{nazwa}prestashop>…`) zapisywane są w pliku `translations/{iso}.php` danego modułu (`MyaitmiLegacyModuleCatalogue`).
5. Bulk: `MyaitmiBulkJobFactory` tworzy zadanie i wiersze w `myaitmi_job` i `myaitmi_job_item`. `MyaitmiJobWorker::processSlice()` przetwarza jedną porcję (rozmiar z `BATCH_SIZE`). Wywołują ją przycisk **Process slice** (żądanie zakładki **Jobs**), pętla **Auto-process** w przeglądarce (AJAX `ProcessJob`) albo cron (`controllers/front/cron.php`).
6. Catalog: `MyaitmiCatalogTranslateService` wybiera rekordy (`collect()`, maks. 100) i zapisuje je bezpośrednio w `_DB_PREFIX_product_lang`, `_DB_PREFIX_category_lang` lub `_DB_PREFIX_cms_lang`.
7. Każde wywołanie trafia do `myaitmi_request` (zakładka **History**), a błędy do `myaitmi_api_log`. Koszt zapisuje się w `myaitmi_usage_ledger`. Tekst sprzed zmiany w zadaniu kopiuje `MyaitmiSnapshotService` do `myaitmi_snapshot` (cofanie przez **Rollback**).

### 6.2. Pliki

| Plik | Do czego służy |
|---|---|
| `myaitranslationsmistral.php` | Klasa główna: instalacja, odinstalowanie, zakładka menu, hooki, ładowanie assetów, `translationClientConfig()`, `getContent()`. |
| `lib/updateChecker.php` | Sprawdzanie aktualizacji (zakładka **Updates**, ostrzeżenie w panelu). |
| `logo.png`, `logo.gif` | Logo w nagłówku zakładek i w menu modułu. |
| `controllers/admin/AdminMyaitranslationsmistralController.php` | Cały panel: zakładki, zapisy, akcje zadań, glosariusz, wykluczenia, katalog, CSV, odpowiedzi AJAX. |
| `controllers/front/cron.php` | Adres cron: przetwarza porcję zadania i zwraca JSON. |
| `sql/install.php`, `sql/uninstall.php` | Tworzenie i kasowanie tabel. |
| `src/Adapter/MyaitmiTranslationAdapterInterface.php` | Interfejs odczytu i zapisu tłumaczeń PrestaShop. |
| `src/Adapter/MyaitmiAbstractTranslationAdapter.php` | Wspólna logika adaptera: listy sekcji, domen i języków, zapis przez usługę lub tabelę `translation`, czyszczenie cache. |
| `src/Adapter/MyaitmiTranslationAdapter.php` | Konkretny adapter (używany przez fabrykę). |
| `src/Adapter/MyaitmiTranslationAdapterFactory.php` | Tworzy adapter. |
| `src/Adapter/MyaitmiFilesystemCatalogueTrait.php` | Odczyt katalogów XLF z motywów i modułów (domeny). |
| `src/Adapter/MyaitmiLegacyModuleCatalogue.php` | Moduły klasyczne: odczyt i zapis `translations/{iso}.php`, czyszczenie OPcache po zapisie. |
| `src/Admin/MyaitmiForms.php` | Budowa wszystkich formularzy panelu i opisów pól (`desc`). |
| `src/Admin/MyaitmiSectionHelp.php` | Teksty panelu **Help** dla każdej zakładki. |
| `src/Audit/MyaitmiRequestLogRepository.php` | Historia wywołań, karty, wykresy, filtry, czyszczenie, retencja. |
| `src/Audit/MyaitmiApiLogRepository.php` | Log błędów i ostrzeżeń API, retencja. |
| `src/Audit/MyaitmiTranslationMemory.php` | Pamięć tłumaczeń (cache): ponowne użycie wyniku dla tego samego tekstu, języka, modelu i glosariusza. |
| `src/Audit/MyaitmiUsageLedger.php` | Koszt według tabeli cen w kodzie, miesięczny budżet. |
| `src/Audit/MyaitmiSnapshotService.php` | Kopie przed zapisem i cofanie zadania. |
| `src/Glossary/MyaitmiGlossaryRepository.php` | Glosariusz: lista, zapis, usuwanie. |
| `src/Glossary/MyaitmiExcludePatternRepository.php` | Wykluczenia: dodawanie, usuwanie, dopasowanie. |
| `src/Job/MyaitmiJobStatuses.php` | Stałe statusów zadań i wierszy. |
| `src/Job/MyaitmiJobRepository.php` | Zadania i wiersze: odczyt, zmiana statusu, pobieranie porcji, przeliczanie liczników. |
| `src/Job/MyaitmiJobWorker.php` | Przetwarzanie porcji, ponawianie błędów, zakończenie zadania, kolejka przeglądu, e-mail po zakończeniu. |
| `src/Provider/MyaitmiTranslationProviderInterface.php` | Interfejs dostawcy tłumaczeń. |
| `src/Provider/MyaitmiMistralTranslationProvider.php` | Wywołania Mistral (cURL), test połączenia, zapis historii wywołania. |
| `src/Provider/MyaitmiPromptBuilder.php` | Budowa poleceń systemowego i użytkownika (ton, głos marki, glosariusz). |
| `src/Provider/MyaitmiProviderFactory.php` | Tworzy dostawcę. |
| `src/Quality/MyaitmiPlaceholderValidator.php` | Sprawdzenie zmiennych i znaczników w tekście. |
| `src/Quality/MyaitmiHtmlValidator.php` | Sprawdzenie poprawności HTML. |
| `src/Quality/MyaitmiPsNativeValidator.php` | Sprawdzenie przed zapisem w sekcji **Manual**. |
| `src/Quality/MyaitmiEmailHtmlPipeline.php` | Ochrona HTML szablonów e-maili przed wysłaniem i przywrócenie go po odpowiedzi. |
| `src/Quality/MyaitmiQualityScorer.php` | Ocena 0–100, flagi, decyzja o przeglądzie. |
| `src/Security/MyaitmiApiKeyEncryptor.php` | Szyfrowanie i odszyfrowanie klucza API. |
| `src/Service/MyaitmiConfigService.php` | Odczyt i zapis ustawień, modele, token cron, walidacja zakresów. |
| `src/Service/MyaitmiRateLimiter.php` | Lokalny limit wywołań na minutę (plik `var/rate_limit.json`). |
| `src/Service/MyaitmiTranslateService.php` | Główny potok tłumaczenia: wykluczenia, pamięć, wywołania, walidacja, ocena, zapis, estymacja. |
| `src/Service/MyaitmiBulkJobFactory.php` | Budowa zadania **Bulk** i estymacji. |
| `src/Service/MyaitmiCatalogTranslateService.php` | Zbieranie i zapis rekordów **Catalog**. |
| `src/Service/MyaitmiDashboardService.php` | Zestawienie brakujących tekstów na **Dashboard**. |
| `translations/*.php` | Tłumaczenia interfejsu (jeden plik na język). |
| `views/templates/admin/configure.tpl` | Szablon całej strony panelu i panelu **Help**. |
| `views/templates/admin/_partials/*.tpl` | Zakładki: `bulk`, `catalog`, `dashboard`, `excludes`, `glossary`, `history-stats`, `jobs`, `logs`, `manual`, `review`, `settings`. |
| `views/css/admin.css` | Style panelu. |
| `views/js/admin.js` | Zakładka **Jobs** (postęp, **Auto-process**), zaznaczanie wierszy, odpowiedzi AJAX. |
| `views/js/admin-help.js` | Panel **Help**. |
| `views/js/translations-tool.js` | Przyciski i pasek na **International → Translations**. |
| `views/js/entity-fields.js` | Przyciski i pasek w formularzach produktu, kategorii i CMS. |
| `views/js/history-charts.js`, `views/js/chart.min.js` | Wykresy na **Dashboard**. |
| `var/rate_limit.json` | Licznik lokalnego limitu wywołań w bieżącej minucie. |
| `index.php` (w każdym katalogu) | Zabezpieczenia przed przeglądaniem katalogów. |

### 6.3. Kontrolery

**Panel: `AdminMyaitranslationsmistralController`** (klasa `ModuleAdminController`, zakładka pod `AdminInternational`).

- Adres: `index.php?controller=AdminMyaitranslationsmistral&token=…`, opcjonalnie `&myaitmi_tab=…`.
- Dozwolone wartości `myaitmi_tab`: `dashboard`, `settings`, `manual`, `bulk`, `jobs`, `glossary`, `excludes`, `logs` (**History**), `review`, `catalog`, `updates`. Każda inna wartość daje `dashboard`.
- Parametry wejściowe (GET/POST):
  - Ustawienia: pola `MYAITMI_*` z formularza, `new_mistral_model`, `delete_mistral_model`, przyciski `submitMyaitranslationsmistralSettings`, `…Ping`, `…AddModel`.
  - Filtry i tłumaczenie: `section`, `theme`, `module`, `domain`, `source_locale`, `target_locale`, `only_empty`, `search`, `selected_keys[]`, `save_now`, `review_key[]`, `review_value[]`, `review_approve[]`, `review_source[]`.
  - Bulk: `target_locales[]`, `domains[]`, `policy_mode` (`fill_empty`, `overwrite`, `outdated_if_changed`), `dry_run`, `bulk_step` (`estimate`).
  - Zadania: `id_job`, `job_action` (`pause`, `resume`, `cancel`, `process`, `retry_failed`, `rollback`, `export_errors`), `filter_failed`.
  - Przegląd: `review_action` (`approve`, `reject`) i `id_review`.
  - Katalog: `entity_type` (`product`, `category`, `cms`), `id_lang_source`, `id_lang_target`, `catalog_fields_{entity}[]`, `catalog_start_id`, `only_empty`.
  - Glosariusz i wykluczenia: `source_term`, `target_locale`, `target_term`, `do_not_translate`, `glossary_csv` (plik), `pattern`, `pattern_type`, `delete_glossary`, `delete_exclude`.
  - Historia i karty: `dash_locale`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_q`, `stats_preset`, `hist_id`.
- Zwraca stronę HTML (`configure.tpl`) albo pliki: `glossary.csv` (eksport glosariusza) lub `job-{id}-errors.csv` (błędy zadania).
- Komunikaty sukcesu i błędu przekazywane są w parametrach `flash` i `flash_kind` (`info`, `success`, `warning`, `danger`).

**Akcje AJAX panelu** (`index.php?controller=AdminMyaitranslationsmistral&ajax=1&action=…`):

| `action` | Parametry | Zwraca |
|---|---|---|
| `ProcessJob` | `id_job` | Wynik porcji: `ok`, `finished`, `paused`, `rate_limited`, `counts`, `job`. |
| `JobStatus` | `id_job` | `ok` i obiekt `job`. |
| `TranslatePageLines` | `items` (JSON), `source_locale`, `target_locale` | `translations` (id → tekst), `error`. Nie zapisuje. |
| `MailSource` | `template`, `kind` (`html`/`txt`), `module`, `theme` | Źródłowy plik e-maila. |
| `ListDomains` | `section`, `locale`, `theme`, `module` | Lista `domains`. |
| `HistoryDetail` | `hist_id` | Szczegóły wywołania. |

**Front: `MyaitranslationsmistralCronModuleFrontController`** (`ajax = true`, `ssl = true`).

- Adres: `index.php?fc=module&module=myaitranslationsmistral&controller=cron&token=…`, opcjonalnie `&id_job=N`.
- `token` jest wymagany i porównywany przez `hash_equals()` z `MYAITMI_CRON_TOKEN`. Zły token daje kod 403 i JSON `{"ok":false,"error":"Forbidden"}`.
- Z parametrem `id_job` przetwarza porcję tego zadania.
- Bez `id_job` bierze pierwsze zadanie ze statusem `pending` lub `running` spośród 20 ostatnich. Gdy takiego nie ma, zwraca `{"ok":true,"message":"No pending jobs"}`.

### 6.4. Hooki

Zarejestrowane przy instalacji:

- `displayBackOfficeHeader` → `hookDisplayBackOfficeHeader()`: zmienia nazwę zakładki z technicznej na etykietę (`renameTabIfTechnical()`) i ładuje assety panelu (`loadBoAssets()`).
- `actionAdminControllerSetMedia` → `hookActionAdminControllerSetMedia()`: ładuje assety (`loadBoAssets()`).

Assety w `loadBoAssets()`:

- Na zakładce modułu: `admin.css`, `admin.js`, `admin-help.js`. Na zakładce **Dashboard** dodatkowo `chart.min.js` i `history-charts.js`. Do JS trafia `Media::addJsDef` z `aitHelpLabels`.
- Na stronie **International → Translations** (`AdminTranslations` lub adres `/international/translations`), gdy włączone są jej przyciski: `admin.css` i `translations-tool.js`.
- Na pozostałych stronach panelu (formularze produktów, kategorii, CMS), gdy włączone są przyciski formularzy: `admin.css` i `entity-fields.js`.
- Dane dla JS: `Media::addJsDef(['myaitmiTr' => …])` z listą języków, locale, flagami przycisków i etykietami (`translationClientConfig()`).

Moduł nie wystawia własnych hooków (brak `Hook::exec`).

### 6.5. Nadpisania

Moduł nie nadpisuje żadnej klasy ani kontrolera PrestaShop. Nie ma katalogu `override`.

### 6.6. Baza

Tabele tworzone w `sql/install.php` (`_DB_PREFIX_` to prefiks sklepu, domyślnie `ps_`). Wszystkie używają silnika `_MYSQL_ENGINE_` i `utf8mb4_unicode_ci`.

| Tabela | Zawartość |
|---|---|
| `myaitmi_glossary` | `id_myaitmi_glossary`, `id_shop`, `source_term`, `target_locale`, `target_term`, `do_not_translate`, `date_add`, `date_upd`. Klucz `idx_shop_locale` (`id_shop`, `target_locale`). Odczyt: `id_shop` IN (0, sklep). |
| `myaitmi_exclude_pattern` | `id_myaitmi_exclude_pattern`, `pattern` (VARCHAR 512), `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled` (przy dodawaniu zawsze 1), `date_add`. |
| `myaitmi_job` | `id_myaitmi_job`, `uuid` (unikalny), `status`, `source_locale`, `target_locales`, `scope_json`, `policy_json`, `dry_run`, `items_total`, `items_done`, `items_failed`, `items_skipped`, `tokens_prompt`, `tokens_completion`, `cost_usd_estimate`, `cost_usd_actual`, `id_employee`, `error_summary`, `started_at`, `finished_at`, `date_add`, `date_upd`. Klucz `idx_status`. |
| `myaitmi_job_item` | `id_myaitmi_job_item`, `id_myaitmi_job`, `domain`, `translation_key`, `theme`, `target_locale`, `source_text`, `previous_translation`, `new_translation`, `status`, `skip_reason`, `error_message`, `tokens_used`, `source_hash`, `validated_ok`, `validation_warnings`, `date_add`, `date_upd`. Klucz `idx_job_status`. Porcja to jeden język docelowy. |
| `myaitmi_memory` | Pamięć tłumaczeń: `memory_hash` (unikalny), `source_text`, `target_locale`, `translation`, `model`, `hit_count`. |
| `myaitmi_usage_ledger` | `usage_date`, `id_myaitmi_job`, `model`, `tokens_prompt`, `tokens_completion`, `cost_usd`, `date_add`. Suma miesięczna liczy budżet. |
| `myaitmi_snapshot` | Kopia przed zapisem: `id_myaitmi_job`, `id_myaitmi_job_item`, `locale`, `domain`, `translation_key`, `theme`, `value_before`. |
| `myaitmi_api_log` | Log błędów i ostrzeżeń: `id_myaitmi_job`, `level`, `provider`, `http_code`, `message`, `context_json`, `date_add`. Retencja wg `MYAITMI_LOG_RETENTION_DAYS`. |
| `myaitmi_review` | Kolejka przeglądu: `id_myaitmi_job_item`, `status` (`needs_review`, `approved`, `rejected`), `quality_score`, `flags_json`, `id_employee`, `date_add`, `date_upd`. |
| `myaitmi_catalog_item` | Tworzona przy instalacji i usuwana przy odinstalowaniu. Kod modułu do niej nie zapisuje. **Catalog** zapisuje bezpośrednio w tabelach językowych sklepu. |
| `myaitmi_request` | Historia wywołań: `request_type` (`translate`, `manual`, `page`, `job`, `catalog`, `ping`, `blocked`), `status`, `model`, `source_locale`, `target_locale`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `cost_usd`, `id_employee`, `id_myaitmi_job`, `item_count`, `prompt`, `reply`, `error_message`, `date_add`. Tabelę tworzy też `ensure()` przy pierwszym zapisie lub wejściu na **History**, jeśli jej nie ma. |

Odinstalowanie kasuje wszystkie 11 tabel z powyższej listy. Tabele tłumaczeń PrestaShop (`_DB_PREFIX_translation`) oraz tabele językowe produktów, kategorii i CMS nie są kasowane.

### 6.7. Klucze i tłumaczenia

**Klucze `Configuration`** (prefiks `MYAITMI_`), wartości domyślne z `installDefaults()`:

| Klucz | Domyślnie | Uwagi |
|---|---|---|
| `API_KEY_ENC` | `''` | Zaszyfrowany klucz API. Odczyt przez `MyaitmiConfigService::getApiKey()`. |
| `MODEL` | `mistral-small-latest` | Aktywny model. |
| `EXTRA_MODELS` | `''` | Dodane ręcznie identyfikatory modeli, po jednym w wierszu. |
| `PROVIDER` | `mistral` | Zawsze `mistral` po zapisie formularza. |
| `TONE` | `formal` | `formal`, `casual` lub `brand`. |
| `CUSTOM_VOICE` | `''` | Tekst **Brand voice**. |
| `BATCH_SIZE` | `25` | Zakres 1–100. |
| `MONTHLY_BUDGET` | `0` | USD, 0 = bez limitu. |
| `SOURCE_LOCALE` | `''` | Pusty = język podaje ekran. |
| `TEMPERATURE` | `0.2` | Zakres 0–1. |
| `DRY_RUN_SAMPLE` | `10` | Zakres 1–50. |
| `RATE_LIMIT_PER_MIN` | `60` | 0 wyłącza lokalny limit. |
| `LOG_RETENTION_DAYS` | `30` | Minimum 1. |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` | Wysyłka e-maila przy zakończeniu zadania (szablon `contact`). |
| `NOTIFY_EMAIL` | `''` | Adres odbiorcy. Gdy pusty, używany jest `PS_SHOP_EMAIL`. |
| `PERM_ALLOW_PUBLISH` | `1` | Zapis do sklepu. |
| `ENTITY_FIELD_BUTTONS`, `ENTITY_BULK` | `1` | Przyciski i pasek w formularzach sklepu. |
| `TR_FIELD_BUTTONS`, `TR_BULK` | `1` | Przyciski i pasek na stronie tłumaczeń. |
| `MAX_TOKENS` | `0` | 0 = domyślny limit dostawcy. |
| `CRON_TOKEN` | losowy 32-znakowy hex | Token adresu cron. Generowany też przy pierwszym odczycie, gdy go brakuje. |

Klucze usuwane przy zapisie formularza albo przy odinstalowaniu: `DEEPL_API_KEY` i `CLAUDE_API_KEY` (pozostałości po wcześniejszych wersjach). Klucze sprawdzania aktualizacji (`mypresta_updates`, `update_{nazwa}`, `updatev_{nazwa}`) nie są kasowane.

**Tłumaczenia interfejsu.** Każdy język to plik `translations/{iso}.php` (np. `pl.php`, `de.php`, `fr.php`). Plik `en.php` jest źródłem napisów. Napisy przechodzą przez `$this->l()` albo przez domeny `myaitmiforms` i `sectionhelp` (opisy pól i panel **Help**). Napisy z szablonów zapisuje się jako `{l s='…' mod='myaitranslationsmistral'}`. Napisy przekazywane do JS (`labels` w `translationClientConfig()` oraz `aitHelpLabels`) też przechodzą przez `$this->l()`.

Jak dodać język: skopiuj `translations/en.php` do `translations/{iso}.php`, przetłumacz wartości i zachowaj identyfikatory kluczy.

### 6.8. Rozszerzanie

- **Motyw sklepu:** moduł niczego nie renderuje w motywie, więc nie ma szablonu do nadpisania.
- **Dostawca tłumaczeń:** nowy dostawca wymaga klasy zgodnej z `MyaitmiTranslationProviderInterface` oraz zmiany w `MyaitmiProviderFactory`. Obecnie fabryka zwraca tylko Mistral.
- **Adapter katalogu:** interfejs `MyaitmiTranslationAdapterInterface` i fabryka `MyaitmiTranslationAdapterFactory`.
- **Cennik:** stawki za milion tokenów są wpisane w `MyaitmiUsageLedger::estimateCost()`. Po zmianie cen Mistral trzeba je zaktualizować w kodzie.
- **Limit lokalny:** plik `var/rate_limit.json` tworzony jest w katalogu modułu.

## 7. Pomoc

Strona modułu: https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-mistral.html

Jeśli potrzebujesz pomocy w sprawie modułu:

1. Zaloguj się na konto klienta na mypresta.eu.
2. Przejdź do kontaktu i wybierz temat **Support for paid modules**. Formularz podaje, że dla płatnych modułów logowanie jest wymagane.
3. Po zalogowaniu wybierz ten moduł z historii zakupów.
