---
title: "PrestaMind AI - dokumentacja i podręcznik użytkownika"
sidebar:
  label: "PrestaMind AI - dokumentacja i podręcznik użytkownika"
description: "Konfiguracja i rozwiązywanie problemów dla sklepu, który ma już zainstalowany PrestaMind AI."
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł PrestaMind AI - AI assistant, live chat and chatbot na MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot/)
>
> ---


Napisy przycisków i zakładek poniżej są angielskimi napisami z ekranu modułu. Gdy panel pracownika jest po polsku, PrestaShop pokazuje polski odpowiednik tego samego napisu, jeśli tłumaczenie modułu go ma.

## 1. Wymagania

PrestaShop 1.7.6, 8 i 9. PHP w wersji wymaganej przez tę instalację PrestaShop. Moduł woła rozszerzenie cURL oraz OpenSSL albo libsodium, żeby zapisać klucze dostawców. Nie wymaga innego modułu.

Potrzebujesz konta i klucza API u wybranego dostawcy, chyba że zostajesz przy demo offline. Lokalny serwer zgodny z OpenAI (Ollama, vLLM, LM Studio) musi mieć adres, który serwer sklepu otwiera. Śledzenie DHL na żywo wymaga darmowego klucza ze strony dewelopera DHL. InPost na żywo klucza nie wymaga.

Duży katalog wydłuża pierwsze indeksowanie. Embeddingi wysyłają tekst każdego produktu do dostawcy embeddingów jeden raz, więc pierwszy przebieg zużywa tokeny i czas. Wyszukiwanie słów kluczowych tego nie robi.

## 2. Instalacja

1. Wgraj moduł w **Module Manager** i naciśnij **Install**.
2. Pytanie **Delete this module and all its data (conversations, knowledge index, settings)?** pojawia się przy odinstalowaniu, nie przy instalacji.
3. Po instalacji pozycja **PrestaMind AI** jest w menu **Customer service**. Gdy tego menu nie ma, pozycja trafia pod **Improve**. **Configure** w wierszu modułu otwiera tę samą stronę.
4. Instalacja nie czyści cache sklepu. Dymek czatu zostaje ukryty, dopóki go nie włączysz.

Odinstalowanie usuwa pozycję menu, tabele modułu i zapisane ustawienia, w tym klucze dostawców. Zamówienia, produkty, strony CMS i reguły koszyka już zapisane w PrestaShop zostają. Katalog modułu zostaje na dysku, dopóki go nie skasujesz. Nowa instalacja zaczyna z pustymi rozmowami i pustym indeksem. Poprzednich nie podnosi.

## 3. Konfiguracja i praca w zapleczu

### 3.1 Cały proces

Zaczynasz w zapleczu. Klient zaczyna na sklepie.

1. Otwórz **PrestaMind AI**. W **Settings**, potem **Health**, popraw każdą linię, która nie jest OK.
2. W **Model provider** kliknij kafelek dostawcy, wklej klucz API, wybierz model główny i model szybki, wpisz ceny i naciśnij **Save and test the connection**.
3. W **Knowledge** na stronie ustawień wybierz, co wchodzi do indeksu. Potem otwórz zakładkę **Knowledge** i naciśnij **Reindex now**.
4. W **Playground** wyślij pytanie o produkt, o dostawę i o zamówienie. Każde wysłanie zużywa tokeny u prawdziwego dostawcy.
5. W **Settings**, potem **Widget**, zostaw **Show the assistant to all visitors** wyłączone. Wpisz swój publiczny adres IP w **Preview only for these IP addresses**, zapisz i otwórz sklep. Gdy odpowiedzi są dobre, włącz widżet dla wszystkich i wyczyść cache całej strony, jeśli dymka nie widać.
6. Odwiedzający otwiera dymek, wpisuje pytanie i naciska strzałkę. Moduł czyta cenę, stan, dostawę albo zamówienie ze sklepu, gdy pytanie tego potrzebuje, i pokazuje odpowiedź w tym samym oknie.
7. Rabat jest tylko wtedy, gdy zapisana oferta pasuje do koszyka. **Add to cart**, **Send the return request** i **Send the quote request** czekają na kliknięcie odwiedzającego.
8. Gdy odwiedzający naciśnie **Talk to a person**, wiersz jest na **Escalations**, a przy włączonej konsoli także na przycisku **Live chats**. Naciskasz **Take over this conversation**, piszesz odpowiedź, naciskasz **Send**, potem **Give back to the assistant**. Status **new**, **open** albo **done** nie wysyła maila do odwiedzającego.

### 3.2 Gdzie są ekrany

Zakładki, w tej kolejności: **Dashboard**, **Live stats**, **History**, **Conversations**, **Knowledge**, **Triggers & offers**, **Playground**, **Quality tests**, **Escalations**, **Settings**, **Updates**.

**Settings** ma własny rząd: **Health**, **Widget**, **Model provider**, **Knowledge**, **Limits & cost**, **Privacy**, **Escalation**, **Cart reminders**, **Couriers**, **Tools**. Każda podstrona zapisuje tylko swoje pola. **Save** pokazuje **Settings saved.** Zapis nie kasuje rozmów ani indeksu.

Pulpit sklepu (strona po zalogowaniu) pokazuje blok z liczbami asystenta, klientami czekającymi na człowieka i ostatnimi rozmowami.

### 3.3 Dashboard

![Dashboard](https://mypresta.eu/docs/images/docs/prestamindai-dashboard.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Dashboard.

Tylko odczyt. Wybierz **today**, **7**, **30** albo **90** dni, albo ustaw **From** i **To**. Możesz zawęzić wywołania AI po modelu, dostawcy, typie (odpowiedzi albo embeddingi) albo statusie, potem naciśnij **Filter**. **See full history** otwiera **History**.

Ekran pokazuje przychód z zamówień złożonych w ciągu 7 dni po czacie, rozmowy, ile rozwiązano bez człowieka, oceny, tokeny wysłane i odebrane oraz szacowany koszt. Koszt bierze cenę zapisaną przy wywołaniu. To nie jest faktura dostawcy. Grupę kontrolną ustawiasz w **Settings**, potem **Privacy**, jeśli chcesz porównać wartość zamówień. Pytania bez odpowiedzi przenieś do FAQ.

### 3.4 Live stats

![Live stats](https://mypresta.eu/docs/images/docs/prestamindai-live.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Live stats.

Zostaw stronę otwartą. Nowe linie pojawiają się u góry co kilka sekund. Chipami ukrywasz klientów, asystenta, zespół, narzędzia albo eskalacje. Szukasz tekstu albo wpisujesz numer czatu, żeby śledzić jedną rozmowę. **thumbs down only** zostawia odpowiedzi, które odwiedzający ocenili w dół. **Pause** zatrzymuje widok. **Compact** zagęszcza wiersze. **Reset filters** pokazuje wszystko. **Clear** czyści widok na tej stronie. **Open chat** otwiera rozmowę. **Take over** pozwala odpowiedzieć.

Strona tylko czyta zapisane rozmowy. Filtry zostają w tej przeglądarce. Zamaskowane numery kart, IBAN i PESEL zostają zamaskowane.

### 3.5 History

![History](https://mypresta.eu/docs/images/docs/prestamindai-history.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się History.

Pełna lista wywołań modeli, od najnowszych: data, typ, dostawca, model, tokeny wysłane, tokeny odebrane, cena za 1M tokenów ważna w tamtej chwili, szacowany koszt, czas i status, z linkiem do rozmowy. Działają te same filtry co na **Dashboard**. Karty nad listą liczą ten sam filtr.

Lista nie trzyma treści wiadomości. Późniejsza zmiana ceny nie zmienia starych wierszy. Log zostaje po skasowaniu rozmów przez retencję.

### 3.6 Conversations

![Conversations](https://mypresta.eu/docs/images/docs/prestamindai-conversations.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Conversations.

Filtruj przez **Waiting for a reply**, **Handled by a person**, eskalację albo negatywny sentyment. Ikona oka otwiera wątek: wiadomości, model, czas odpowiedzi, kciuki w górę i w dół oraz każde wywołanie narzędzia. Ikona kosza kasuje tę rozmowę, jej wiadomości i wywołania narzędzi. Kasowanie jest trwałe.

Naciśnij **Take over this conversation**. Asystent milczy dla tego odwiedzającego. Twoje odpowiedzi widać jako **Shop team**. **Send** wysyła odpowiedź. **Give back to the assistant** oddaje czat asystentowi.

**Live chats** to pływający przycisk na dole po prawej na każdej stronie zaplecza, gdy **Live chat console in the back office** jest włączone i możesz otworzyć **PrestaMind AI**. Licznik pokazuje czekających klientów. Możesz trzymać otwartych kilka okien. Wyłączenie konsoli chowa przycisk. Ta strona nadal działa.

### 3.7 Knowledge

![Knowledge](https://mypresta.eu/docs/images/docs/prestamindai-knowledge.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Knowledge.

Naciśnij **Reindex now** po instalacji, po zmianie wykluczeń i po zmianie dostawcy albo modelu embeddingów. **Clear answer cache** kasuje zapisane odpowiedzi na powtarzane pytania o zasady sklepu. Cache czyści się też przy edycji wpisu FAQ albo produktu. Dokument, który jeszcze czeka, nie jest używany. Nowy wpis FAQ działa od następnego pytania.

Cena i stan nie są w indeksie. Moduł czyta je z produktu w chwili pytania.

**Add FAQ entry** / **Edit FAQ entry**: wpisz pytanie i odpowiedź tak, jak asystent ma ją powiedzieć, i zapisz. Aktywne strony CMS oraz aktywne widoczne produkty wchodzą do indeksu, gdy te przełączniki są włączone.

### 3.8 Triggers

![Triggers](https://mypresta.eu/docs/images/docs/prestamindai-triggers.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Triggers.

**Triggers & offers** ma dwie podstrony. Najpierw tworzysz ofertę, potem przypinasz ją do wyzwalacza. Odwiedzający widzi najwyżej jedną wiadomość z inicjatywy na wizytę. Ten sam wyzwalacz milczy potem przez czas cool-down.

Kolumny listy: **Name**, **When**, **Threshold**, **Page**, **Message**, **Discount**, **Active**. W wierszu jest edycja i kasowanie. Ramka statusu mówi, czemu dymek może nie wyjść. **Open the shop in test mode** pomija zgodę, cool-down i limit jednej wiadomości na wizytę.

| Pole | Przy nowym wyzwalaczu | Co robi |
|---|---|---|
| **Name** | puste | Etykieta dla Ciebie. Puste bierze tekst wiadomości. Odwiedzający jej nie widzi. |
| **Type** | **Seconds on the page** | **Seconds on the page**, **Scrolled percent of the page**, **Exit intent (desktop)**, **Seconds idle on the cart page** albo **Product viewed N times in a visit**. Wiadomość jest obok przycisku czatu. Kliknięcie otwiera czat. |
| **Threshold** | 30 | Sekundy, procent przewinięcia albo liczba wyświetleń. Exit intent to ignoruje. Czas i bezczynny koszyk biorą co najmniej 5 sekund. |
| **Page type** | **Any page** | **Any page**, **Product page**, **Category page**, **Cart / checkout** albo **Home page**. Na innych stronach ten wyzwalacz milczy. |
| **Message shown to the visitor** | puste, wymagane | Jedno albo dwa zdania na język sklepu, do 300 znaków. Pusty język bierze język domyślny. Ten tekst jest też pierwszą linią, gdy odwiedzający otworzy czat z dymka. |
| **Only for these categories** | brak | Na karcie produktu produkt musi być w jednej z nich. Na stronie kategorii kategoria musi pasować. Puste oznacza wszystkie kategorie. |
| **Only for these products** | brak | Ogranicza wyzwalacz do tych produktów. Puste oznacza wszystkie produkty. |
| **Offer the assistant may grant after this trigger** | **None** | Wybierz zapisaną ofertę albo **None**. Decydują reguły. Model nie wymyśla procentu. |
| **How the discount is handed out** | **Give the code at once when the visitor clicks the message** | **Only if the visitor asks or hesitates over the price** albo od razu, gdy czat otwiera się z wiadomości. W obu przypadkach koszyk musi pasować do oferty. Gdy **apply_offer** jest odznaczone w **Tools**, kod idzie od razu. |
| **Cool-down (days)** | 7 | Od 0 do 365. Po pokazaniu dymka ten odwiedzający nie widzi tego wyzwalacza, aż cool-down minie. |

**Add trigger** albo **Save trigger** zapisuje wiersz. **Allow proactive messages** musi być włączone w **Privacy**, inaczej żaden wyzwalacz nie odpala.

### 3.9 Offers

![Offers](https://mypresta.eu/docs/images/docs/prestamindai-offers.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Offers.

Kolumny: **Name**, **%**, **Min. cart**, **Valid (h)**, **Max / day**. W wierszu jest edycja i kasowanie. Bez ofert asystent nie daje rabatu. Jedna rozmowa dostaje najwyżej jedną ofertę. Kod jest jednorazowy, wchodzi do koszyka i nie dokłada się do produktów, które już mają rabat. Odwiedzający widzi nazwę reguły **PrestaMind offer**.

| Pole | Przy nowej ofercie | Co robi |
|---|---|---|
| **Name** | puste | Twoja etykieta, widoczna w formularzu wyzwalacza. |
| **Discount percent (1-50)** | 5 | Procent od produktów, które nie są już w promocji. |
| **Minimum cart value (tax incl.)** | 0 | 0 oznacza dowolny koszyk. Poniżej tej kwoty oferta jest odmówiona. Kwota jest w domyślnej walucie sklepu. |
| **Valid for (hours)** | 24 | Od 1 do 720. Kod wygasa po tylu godzinach. |
| **Maximum codes per day** | 20 | 0 oznacza brak limitu. Po osiągnięciu limitu ta oferta milczy do następnego dnia. |
| **No offer when the cart contains products from** | brak | Gdy jakakolwiek pozycja koszyka jest w tych kategoriach, cały koszyk jest odmówiony. |

**Add offer** albo **Save offer** zapisuje regułę. Przypnij ją do wyzwalacza, zanim asystent będzie mógł jej użyć. Przypomnienia koszyka też mogą dołączyć jedną ofertę.

### 3.10 Playground

![Playground](https://mypresta.eu/docs/images/docs/prestamindai-playground.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Playground.

Używa prawdziwego dostawcy. Zużywa tokeny i liczy się do dziennego budżetu. Wątek ma kanał playground. Do odwiedzających nic nie idzie.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Page the customer is on** | **Other** | **Other**, **Home**, **Product page**, **Category** albo **Cart**. Asystent dostaje tę stronę jako kontekst. |
| **Product id (optional)** | puste | Tylko przy **Product page**. Id z **Catalog**, potem **Products**. Asystent widzi aktualną cenę i stan tego produktu. |
| **Customer message** | puste | Pytanie. **Send** pokazuje odpowiedź i ślad (źródła, narzędzia, tokeny, koszt). **New conversation** zaczyna od nowa. |

### 3.11 Quality tests

![Quality tests](https://mypresta.eu/docs/images/docs/prestamindai-quality-tests.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Quality tests.

Dodaj pytanie, słowa, które odpowiedź musi zawierać, i słowa, których zawierać nie może. Naciśnij **Run all tests**. Każdy przebieg pyta prawdziwy model, więc zużywa tokeny. Lista pokazuje zaliczenie albo błąd, powód i odpowiedź. Rozmowy testowe są kasowane po przebiegu.

### 3.12 Escalations

![Escalations](https://mypresta.eu/docs/images/docs/prestamindai-escalations.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Escalations.

Wiersze to klienci, którzy prosili o człowieka, zgłoszenia zwrotu i zapytania o wycenę, ze streszczeniem i kontaktem, który zostawili. Cel powiadomienia ustawiasz w **Settings**, potem **Escalation**. Na liście ustaw status **new**, **open** albo **done**. Status nie wysyła maila do odwiedzającego. Odpowiedz na kontakt z wiersza albo otwórz link czatu.

### 3.13 Health

![Health](https://mypresta.eu/docs/images/docs/prestamindai-health.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Health.

Lista kontrolna. **OK** oznacza, że linia jest gotowa. **!** oznacza, że nie jest. **Repair hooks** dopisuje brakujące hooki i pokazuje **All hooks are registered.** albo **Could not register:** i nazwy hooków. **Test streaming** sprawdza, czy serwer nie buforuje odpowiedzi na żywo. Samo oglądanie strony nic innego nie zmienia. Linia widżetu jest OK tylko wtedy, gdy dymek jest widoczny dla Ciebie.

### 3.14 Widget

![Widget](https://mypresta.eu/docs/images/docs/prestamindai-widget.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Widget.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Show the assistant to all visitors** | Nie | Włączone: dymek widzi każdy odwiedzający poza grupą kontrolną. Wyłączone: nikt, poza adresami IP podglądu. Po zmianie wyczyść cache całej strony. |
| **Preview only for these IP addresses** | puste | Publiczne adresy IP po przecinku. Strona pokazuje adres, który sklep widzi teraz. Za proxy może się różnić od tego, który znasz. |
| **Assistant name** | PrestaMind | Nazwa w nagłówku czatu, osobno dla języka, do 60 znaków. Pusty język bierze język domyślny. |
| **Greeting** | puste | Pierwsza wiadomość pustego czatu, do 300 znaków na język. Puste bierze zdanie wbudowane. |
| **AI disclosure line** | puste | Linia pod nagłówkiem, do 300 znaków na język. Puste bierze zdanie wbudowane, które mówi też, że odpowiedzi mogą zawierać błędy. |
| **Color** | #2563eb | Główny kolor przycisku, nagłówka, przycisków i dymków odwiedzającego. |
| **Position** | **Bottom right** | **Bottom right** albo **Bottom left**. |
| **Button shape** | **Circle** | **Circle**, **Rounded square** albo **Square with sharp corners**. Okno się nie zmienia. |
| **Button size** | **Medium (56 px)** | **Small (48 px)**, **Medium (56 px)** albo **Large (68 px)**. |
| **Window corners** | **Soft (default)** | **Sharp**, **Soft (default)** albo **Very round**. |
| **Button icon** | wbudowany dymek | **Choose icon** otwiera Font Awesome i Material Icons. **Use the built-in bubble** przywraca domyślną. Ikona jest zapisana w sklepie. Zapisz formularz, żeby ją zastosować. |
| **Button color** | puste (bierze **Color**) | Tło przycisku czatu. |
| **Icon color** | #ffffff | Kolor ikony na przycisku. |
| **Header color** | puste (bierze **Color**) | Tło górnego paska. |
| **Header text color** | #ffffff | Nazwa i przyciski na górnym pasku. |
| **Customer bubble color** | puste (bierze **Color**) | Wiadomości odwiedzającego oraz przyciski i strzałka wysyłki. |
| **Customer bubble text color** | #ffffff | Tekst w wiadomościach odwiedzającego i na głównych przyciskach. |
| **Preview** | próbka | Zmienia się razem z polami. Nic nie jest zapisane przed **Save**. |
| **Tone** | **Friendly** | **Friendly**, **Formal**, **Casual** albo **Expert**. Działa dla nowych wiadomości. |
| **Your instructions to the assistant** | puste | Do 1500 znaków, dokładane do każdej rozmowy. Nie uchylają aktualnych cen, zakazu wymyślonego rabatu ani zakazu danych innych klientów. Długi tekst kosztuje tokeny przy każdej wiadomości. |

### 3.15 Dostawca modelu i każdy wbudowany model

![Dostawca modelu i każdy wbudowany model](https://mypresta.eu/docs/images/docs/prestamindai-provider.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Dostawca modelu i każdy wbudowany model.

Kliknij kafelek. Wołany jest tylko aktywny dostawca oraz zapasowy, jeśli go ustawisz i aktywny zawiedzie, zanim pójdzie pierwsze słowo. Modele i ceny zostają przy każdym dostawcy, więc możesz się przełączać.

Po instalacji aktywny dostawca to **Demo (offline)**. Nie potrzebuje klucza i nic nie kosztuje. Zwraca gotowe odpowiedzi, żeby sprawdzić instalację. To nie jest asystent sklepu.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Fallback provider** | **None** | Drugi dostawca, gdy aktywny przekroczy czas, limit albo zwróci błąd serwera. Wybierz takiego, którego klucz jest zapisany. Zużycie rozlicza ten drugi dostawca. Demo nie może być zapasowym. |
| **API key** | puste | Wklej klucz i zapisz. Puste pole zostawia zapisany klucz. Klucz jest zaszyfrowany i nie pokazuje się ponownie, tylko pierwsze i ostatnie znaki. **Remove the stored key** na Yes, potem zapis, kasuje go. Serwer zgodny z OpenAI może zostać bez klucza. |
| **Base URL** | http://localhost:11434/v1 | Tylko dla **OpenAI-compatible / Ollama**. Adres musi kończyć się na /v1. Zapytania idą tam, a nie do chmury. |
| **Main model** | tabela tego dostawcy | Porady o produktach, pytania o zamówienia i każda odpowiedź, która potrzebuje narzędzi. |
| **Fast model** | tabela tego dostawcy | Pytania o zasady sklepu i pogawędka. Ustaw ten sam model co główny, jeśli chcesz jeden model do wszystkiego. |
| **Your own model id** | puste | Litery, cyfry oraz . _ - : / @, do 100 znaków. **Add model** zapisuje od razu razem z resztą strony. **Model added. Choose it as the main or fast model and enter its price.** Gdy już jest na liście: **That model is already on the list.** Zły identyfikator: **Enter a model id: letters, digits and . _ - : / @ only.** |
| Kolumny cen | cena z listy | **USD / 1M input tokens** i **USD / 1M output tokens**. Kropka jest separatorem dziesiętnym. Model z plakietką **set price** nie ma znanej ceny domyślnej. Model bez ceny liczy się jako darmowy, więc dzienny budżet w dolarach Cię nie chroni. |
| **Reset prices to defaults** | - | Przywraca ceny wbudowane. **Prices set back to the built-in defaults.** Ceny, które wpisałeś, giną. |
| **Remove** | - | Tylko przy własnym modelu czatu. **Model removed.** Model wbudowany ma kłódkę i **Built-in models cannot be removed.** |

**Save and test the connection** zapisuje i woła aktywnego dostawcę modelem głównym. **No API key stored for the selected provider.** oznacza, że klucza jeszcze nie ma.

Ceny poniżej są w USD za 1 milion tokenów, najpierw wejście, potem wyjście. To ceny z cennika zapisane w module 2026-10-31. Dostawca może je zmienić. Popraw dwie kolumny, gdy faktura się różni. DeepSeek ma ceny szczytowe i poza szczytem. Moduł trzyma cenę szczytową, żeby szacunek nie był za niski.

**OpenAI.** Strumień, narzędzia i embeddingi. Domyślny model główny **gpt-6.1-sol**. Domyślny model szybki **gpt-6-luna**.

| Model | Rodzaj | Wejście / wyjście USD za 1M | Po instalacji |
|---|---|---|---|
| gpt-6.1-sol | czat | 2 / 10 | model główny |
| gpt-6.1-terra | czat | 1 / 5 | nie |
| gpt-6-luna | czat | 0.10 / 0.50 | model szybki |
| gpt-5.5 | czat | 5 / 30 | nie |
| gpt-5-mini | czat | 0.25 / 2 | nie |
| gpt-4.1 | czat | 2 / 8 | nie |
| gpt-4.1-mini | czat | 0.40 / 1.60 | nie |
| gpt-4o-mini | czat | 0.15 / 0.60 | nie |
| text-embedding-3-small | embeddingi | 0.02 / 0 | domyślny model embeddingów |
| text-embedding-3-large | embeddingi | 0.13 / 0 | nie |

**Anthropic Claude.** Strumień i narzędzia. Bez embeddingów. Domyślny model główny **claude-sonnet-5-5**. Domyślny model szybki **claude-haiku-5-5**.

| Model | Rodzaj | Wejście / wyjście USD za 1M | Po instalacji |
|---|---|---|---|
| claude-fable-5-1 | czat | 10 / 50 | nie |
| claude-opus-5-5 | czat | 4 / 20 | nie |
| claude-opus-5 | czat | 5 / 25 | nie |
| claude-sonnet-5-5 | czat | 2 / 10 | model główny |
| claude-sonnet-4-6 | czat | 3 / 15 | nie |
| claude-haiku-5-5 | czat | 0.10 / 0.50 | model szybki |
| claude-haiku-4-5 | czat | 1 / 5 | nie |

**Google Gemini.** Strumień, narzędzia i embeddingi. Domyślny model główny **gemini-2.5-flash**. Domyślny model szybki **gemini-2.5-flash-lite**.

| Model | Rodzaj | Wejście / wyjście USD za 1M | Po instalacji |
|---|---|---|---|
| gemini-2.5-pro | czat | 1.25 / 10 | nie |
| gemini-2.5-flash | czat | 0.30 / 2.50 | model główny |
| gemini-2.5-flash-lite | czat | 0.10 / 0.40 | model szybki |
| gemini-embedding-001 | embeddingi | 0.15 / 0 | domyślny model embeddingów |

**DeepSeek.** API zgodne z OpenAI. Bez embeddingów. Domyślny model główny i szybki to **deepseek-flash**.

| Model | Rodzaj | Wejście / wyjście USD za 1M | Po instalacji |
|---|---|---|---|
| deepseek-flash | czat | 0.30 / 1.20 | model główny i szybki |
| deepseek-v4-pro | czat | 1.32 / 3.96 | nie |

**Mistral AI.** Strumień, narzędzia i embeddingi. Domyślny model główny **mistral-large-latest**. Domyślny model szybki **mistral-small-latest**. Pusta cena oznacza, że moduł nie ma ceny z cennika: wiersz ma **set price**, dopóki jej nie wpiszesz.

| Model | Rodzaj | Wejście / wyjście USD za 1M | Po instalacji |
|---|---|---|---|
| mistral-large-latest | czat | 0.50 / 1.50 | model główny |
| mistral-medium-latest | czat | brak ceny wbudowanej | nie |
| mistral-small-latest | czat | brak ceny wbudowanej | model szybki |
| open-mistral-nemo | czat | brak ceny wbudowanej | nie |
| mistral-embed | embeddingi | brak ceny wbudowanej | domyślny model embeddingów |

**OpenAI-compatible / Ollama.** Twój serwer. Ceny wbudowane to 0 / 0, także dla modeli lokalnych. Domyślny model główny i szybki to **llama3.1**. Domyślny model embeddingów to **nomic-embed-text**.

| Model | Rodzaj | Wejście / wyjście USD za 1M | Po instalacji |
|---|---|---|---|
| llama3.1 | czat | 0 / 0 | model główny i szybki |
| llama3.2 | czat | 0 / 0 | nie |
| mistral | czat | 0 / 0 | nie |
| qwen2.5 | czat | 0 / 0 | nie |
| nomic-embed-text | embeddingi | 0 / 0 | domyślny model embeddingów |
| mxbai-embed-large | embeddingi | 0 / 0 | nie |
| bge-m3 | embeddingi | 0 / 0 | nie |
| snowflake-arctic-embed | embeddingi | 0 / 0 | nie |

**Demo (offline).** Bez klucza. Ceny 0 / 0.

| Model | Rodzaj | Wejście / wyjście USD za 1M | Po instalacji |
|---|---|---|---|
| mock | czat | 0 / 0 | model główny i szybki, i ten dostawca jest aktywny |
| mock-64 | embeddingi | 0 / 0 | gdy dostawcą embeddingów jest demo |

Część nowszych modeli OpenAI ignoruje **Temperature**. Identyfikator, którego dostawca nie zna, widać jako błąd dostawcy na **Dashboard**.

### 3.16 Ustawienia Knowledge

![Ustawienia Knowledge](https://mypresta.eu/docs/images/docs/prestamindai-knowledge-settings.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Ustawienia Knowledge.

Adres cron jest na tej stronie. Wołaj go co 10 do 15 minut. Każde wywołanie indeksuje nowe i zmienione strony, buduje embeddingi, wysyła przypomnienia koszyka, jeśli je włączysz, kasuje rozmowy starsze niż retencja i czyści cache odpowiedzi oraz wiersze limitu starsze niż dwa dni. Bez crona indeks i tak się aktualizuje, gdy odwiedzający piszą albo gdy lecą hooki produktu i CMS. Kasowanie po retencji i embeddingi idą wtedy tylko z przycisków.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Embeddings provider** | **None (keyword search)** | **None (keyword search)**, **openai**, **gemini**, **mistral**, **compatible** albo **demo**. Anthropic i DeepSeek nie są na tej liście. Zmiana wymaga **Reindex now**. |
| **Embeddings model** | **Default for the chosen provider** | Model dostawcy powyżej. Wektorów dwóch modeli nie da się porównać. Model innego dostawcy jest pomijany i wchodzi domyślny. Po zmianie zrób reindeks. |
| **Other embeddings model** | puste | Dokładny identyfikator modelu spoza listy, na przykład z Ollama. Gdy jest wypełnione, zastępuje wybór powyżej. |
| **Index products** | Tak | Indeksuje nazwę, markę, kategorie, cechy i opisy aktywnych widocznych produktów. Nie oznacza, że pytania o produkty nie mają tekstu katalogu. |
| **Index CMS pages** | Tak | Indeksuje aktywne strony CMS. Nie indeksuj stron z notatkami wewnętrznymi. |
| **Never use these categories** | brak | Produkty z tych kategorii nie wchodzą do indeksu i nie mogą być pokazane, porównane ani podane do koszyka. Po zmianie zrób reindeks. |
| **Never use these products** | brak | To samo dla pojedynczych produktów. |
| **Cache answers to repeated policy questions** | Tak | Goście, tylko pierwsze pytanie, i nigdy odpowiedź z ceną albo zamówieniem. **Clear answer cache** na zakładce Knowledge po edycji strony z zasadami. |
| **Cache lifetime (hours)** | 24 | Od 1 do 720. Potem model odpowiada od nowa. |

### 3.17 Limity i koszt

![Limity i koszt](https://mypresta.eu/docs/images/docs/prestamindai-limits.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Limity i koszt.

Górna linia pokazuje dzisiejsze zapytania, tokeny i szacowany koszt. Gdy dzienny budżet jest osiągnięty, asystent wysyła krótką informację i proponuje przekazanie pytania zespołowi do następnego dnia.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Daily budget (USD)** | 0 | 0 oznacza brak limitu. Działa tylko wtedy, gdy używane modele mają ceny. Gdy dzisiejszy koszt dojdzie do limitu, wywołania modelu stoją do północy. |
| **Daily token budget** | 0 | 0 oznacza brak limitu. Liczy tokeny także przy cenie 0. 1000000 tokenów to około kilkaset rozmów. |
| **Messages per minute per visitor IP** | 8 | Od 1 do 60. Szybsi dostają prośbę o czekanie i nie ma wywołania modelu. |
| **Messages per conversation per day** | 60 | Od 1 do 500. Potem rozmowa jest zablokowana do końca dnia. |
| **Max reply tokens** | 700 | Od 150 do 3000. Przy 700 to około 450 słów. Krótki limit ucina odpowiedź. |
| **Max tool steps per message** | 5 | Od 1 do 8. Ile odczytów na żywo (szukanie, produkt, dostawa) może zrobić jedna wiadomość. 1 wyłącza wielokrokowe szukanie. |
| **Max characters per customer message** | 800 | Od 100 do 2000. Dłuższy tekst jest ucięty. |
| **Messages of history sent to the model** | 12 | Od 2 do 30. 12 to ostatnie sześć wymian. Więcej historii wysyła więcej tokenów. |
| **Temperature (0-1)** | 0.3 | 0.2 do 0.4 trzyma się bliżej danych sklepu. Wyżej zmienia sformułowania. Część nowszych modeli OpenAI to ignoruje. |

### 3.18 Privacy

![Privacy](https://mypresta.eu/docs/images/docs/prestamindai-privacy.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Privacy.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Mask card numbers, IBAN and PESEL** | Tak | Zamienia je na [card], [iban] i [id], zanim tekst zostanie zapisany i zanim pójdzie do dostawcy. |
| **Delete conversations after (days)** | 90 | 0 zostawia je na zawsze. Adres cron kasuje starsze rozmowy. Statystyki zamówień zostają. |
| **Order status without signing in, for registered customers** | Tak | Odwiedzający może zapytać numerem zamówienia i e-mailem z kasy. Nie: ta para działa tylko dla zamówień gościa, a klient z kontem musi się zalogować. Najwyżej 10 prób w 10 minut. |
| **Allow proactive messages** | Tak | Nie wyłącza wszystkie wyzwalacze. |
| **Proactive triggers wait for consent** | Tak | Brak dymka, dopóki baner ciasteczek nie wywoła funkcji zgody. Sam czat działa. Nie: wyzwalacze idą do wszystkich. |
| **Control group (% of visitors)** | 0 | Od 0 do 50. Ci odwiedzający nie widzą asystenta. **Dashboard** może porównać wartość zamówień. |

**Delete old conversations** to osobny formularz. **Older than (days)** startuje tam od 30. **Delete** kasuje te rozmowy od razu. Komunikat to **Deleted N conversations.** Tego nie cofniesz.

### 3.19 Ustawienia Escalation

![Ustawienia Escalation](https://mypresta.eu/docs/images/docs/prestamindai-escalation.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Ustawienia Escalation.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Live chat console in the back office** | Tak | Pokazuje przycisk **Live chats**. Widzą go pracownicy, którzy mogą otworzyć **PrestaMind AI**. Wyłączenie chowa przycisk. **Conversations** nadal działa. |
| **E-mail for hand-offs** | puste | Każda eskalacja wysyła streszczenie i kontakt zostawiony przez odwiedzającego. Puste oznacza brak maila. Poczta sklepu musi działać. |
| **Webhook type** | **Slack** | **Slack**, **Telegram** albo **Generic JSON**. |
| **Webhook URL** | puste | Adres incoming webhook Slacka, Telegram `https://api.telegram.org/bot<TOKEN>/sendMessage` albo dowolny adres https. Puste oznacza brak webhooka. Wynik jest na liście **Escalations**. |
| **Telegram chat id** | puste | Numeryczny identyfikator czatu albo grupy. Dla Slacka i generic JSON jest ignorowany. |
| **Offer a person when sentiment falls below** | -0.5 | Od -1 do 0. Bliżej 0 reaguje wcześniej. Asystent przeprasza i proponuje przekazanie sprawy zespołowi. |

### 3.20 Przypomnienia koszyka

![Przypomnienia koszyka](https://mypresta.eu/docs/images/docs/prestamindai-reminders.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Przypomnienia koszyka.

Nic nie wychodzi, dopóki **Send cart reminders** nie jest Yes i nie działa adres cron. Jeden mail na porzucony koszyk, tylko do klienta z kontem. Goście maila nie dostają.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Send cart reminders** | Nie | Włączone: następny przebieg crona wysyła przypomnienia pasujące do reguł poniżej. Wyłączone: nic nowego nie wychodzi. Wysłane wiersze zostają na liście. |
| **Only customers who subscribed to the newsletter** | Tak | Tak: klienci bez zgody na newsletter nic nie dostają. |
| **Send after (hours of inactivity)** | 3 | Co najmniej 1. Koszyk musi tyle leżeć bez zmian. |
| **Stop after (hours since the last change)** | 72 | Musi być większe niż wartość powyżej. Starsze koszyki są pomijane. |
| **Minimum cart value (tax incl.)** | 0 | 0 oznacza dowolny koszyk. Kwota jest w walucie sklepu. |
| **Discount code in the e-mail** | **No discount code** | Jedna z Twoich ofert albo brak. Reguły oferty nadal obowiązują. Gdy dzienny limit jest osiągnięty, mail wychodzi bez kodu. |
| **E-mail subject** | puste | Osobno dla języka. Puste bierze temat wbudowany. Klient dostaje temat w języku konta. |

**Send a test e-mail** używa **Send the test to** (na starcie Twój e-mail zaplecza) i **Send test**. Jedna próbka idzie od razu. Nie jest zapisywana i nie tworzy kodu. **Test e-mail sent.** albo **The e-mail could not be sent. Check the e-mail settings of the shop.** Zły adres pokazuje **Enter a valid e-mail address.**

**Latest reminders** wymienia datę, koszyk, klienta, kod i status.

### 3.21 Couriers

![Couriers](https://mypresta.eu/docs/images/docs/prestamindai-couriers.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Couriers.

Strona wymienia metody dostawy tego sklepu. Gdy sklep ich nie ma, widzisz **Your shop has no shipping methods yet. Add them in Shipping > Carriers; they appear here automatically.**

Przy każdej metodzie **tracking link** to jeden adres na język. Wstaw `{n}` tam, gdzie ma być numer przesyłki. Adres bez `{n}` albo taki, który nie zaczyna się od http albo https, jest pomijany. Pusty język bierze język domyślny. Gdy przewoźnik ma już adres śledzenia w **Shipping**, potem **Carriers**, ten adres idzie pierwszy. Bez żadnego linku asystent podaje tylko numer.

**live status** widać tylko wtedy, gdy nazwa metody zawiera InPost albo DHL, albo wybrałeś to wcześniej. **No live status (tracking link only)** zostawia sam link. InPost nie potrzebuje klucza. DHL pokazuje **DHL API key**: zarejestruj się na stronie dewelopera DHL, utwórz aplikację Shipment Tracking - Unified i wklej klucz. Darmowy klucz to około 250 wywołań dziennie. Klucz jest zaszyfrowany. Bez niego status DHL na żywo jest pomijany i zostaje link. Odpowiedzi na żywo są w cache przez 10 minut.

### 3.22 Tools

![Tools](https://mypresta.eu/docs/images/docs/prestamindai-tools.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Tools.

Odznacz narzędzie, żeby model go nie dostawał. Wyłączone narzędzie nie może zadziałać. W trybie katalogu narzędzia koszyka, oferty i zawartości koszyka zostają wyłączone. Pytanie o zasady sklepu albo pogawędka może wołać tylko **create_ticket**.

| Narzędzie | Ryzyko na ekranie | Potrzebuje | Co dostaje odwiedzający |
|---|---|---|---|
| search_products | odczyt | - | Do sześciu kart produktów. Opcjonalnie maksymalna cena i tylko na stanie. Odwiedzający naciska **Add to cart**. |
| popular_products | odczyt | - | Bestsellery z prawdziwych zamówień, domyślnie 90 dni, od 7 do 365, do sześciu kart. Bez dokładnej liczby sprzedaży. |
| get_product_live | odczyt | - | Aktualna cena, stan, cechy i warianty jednego produktu. |
| compare_products | odczyt | - | Dwa albo trzy produkty obok siebie. |
| suggest_substitute | odczyt | - | Zamienniki, które są na stanie. |
| get_cart | odczyt | koszyk | Zawartość i suma. |
| add_to_cart | ekran oznacza potwierdzenie | potwierdzenie klienta | Karta produktu. Ilość od 1 do 20. Moduł nie dodaje pozycji. Odwiedzający naciska **Add to cart**. |
| check_shipping | odczyt | - | Metody, czasy i próg darmowej dostawy. Opcjonalny kod ISO kraju. |
| get_order_status | odczyt | sesja albo numer plus e-mail z kasy | Status tego zamówienia. |
| track_parcel | odczyt | ta sama tożsamość co status zamówienia | Przewoźnik, numer i link. InPost na żywo bez klucza. DHL na żywo z kluczem DHL. |
| start_return | potwierdzenie | zalogowany klient | Nic nie wychodzi przed **Send the return request**. |
| request_quote | potwierdzenie | formularz | Pozycje, firma i kontakt. Nic nie wychodzi przed **Send the quote request**. |
| create_ticket | przekazanie | gość jest proszony o e-mail albo telefon | **Talk to a person** otwiera eskalację. |
| apply_offer | decydują reguły | koszyk | Kod tylko wtedy, gdy zapisana oferta pasuje. Brak pasującej reguły oznacza brak kodu. |

**Save** zapisuje zaznaczenia.

### 3.23 Updates

![Updates](https://mypresta.eu/docs/images/docs/prestamindai-updates.webp)

Ekran jest po angielsku. W tej instrukcji ta strona nazywa się Updates.

**Check now** porównuje zainstalowaną wersję z wersją na serwerach MyPresta.eu. Zostaw automatyczne powiadomienia włączone, żeby zobaczyć komunikat w zapleczu. Moduł sam się nie aktualizuje. Nową paczkę instalujesz sam.

## 4. Front sklepu

Dymek jest ukryty, dopóki **Show the assistant to all visitors** nie jest włączone, poza adresami IP z listy podglądu. Odwiedzający z grupy kontrolnej go nie widzą.

Odwiedzający naciska przycisk w rogu, który wybrałeś. Okno pokazuje nazwę asystenta, linię informacji i powitanie. Odwiedzający wpisuje tekst i naciska strzałkę. Na sklepie nie ma przycisku o napisie Send. Odpowiedź spływa do okna, gdy serwer jej nie buforuje.

Karty produktów mają **Add to cart**. Zwrot czeka, aż padnie **Send the return request**. Wycena czeka, aż padnie **Send the quote request**. **Talk to a person** oddaje czat zespołowi. Gdy przejąłeś rozmowę, nowe wiadomości odwiedzającego są zapisane, a Twoje odpowiedzi widać jako **Shop team**.

Dymek z inicjatywy pojawia się tylko wtedy, gdy wyzwalacze są dozwolone, odwiedzający pasuje do reguły i jest zgoda, jeśli jej wymagasz. Jeden dymek na wizytę. Link testowy z **Triggers** jest dla Ciebie, nie dla klientów.

Adres cron nie jest stroną dla odwiedzających. Otwieraj go tylko z harmonogramu serwera. Zły token dostaje odmowę i nic nie robi.

## 5. Problemy

**Nie ma dymka.** **Show the assistant to all visitors** jest wyłączone, ten odwiedzający jest w grupie kontrolnej albo cache całej strony trzyma starą stronę. Włącz przełącznik albo dopisz swoje IP do listy podglądu, zapisz i wyczyść cache całej strony.

**Could not create the module tables.** Instalacja stanęła, zanim doszła pozycja menu. Przeczytaj komunikat bazy na ekranie, popraw uprawnienia użytkownika bazy i zainstaluj ponownie.

**Could not register hook** i nazwa hooka, albo **Could not register:** na **Health**. Naciśnij **Repair hooks**. Jeśli linia zostaje, użytkownik sklepu nie może zapisywać hooków. Popraw uprawnienia bazy i naciśnij przycisk jeszcze raz.

**Could not add the menu tab.** Instalacja nie dokończyła menu. Otwórz **Module Manager**, odinstaluj, jeśli moduł jest w połowie, i zainstaluj ponownie. **Configure** też próbuje odtworzyć pozycję menu.

**No API key stored for the selected provider.** Wklej klucz w **Model provider** i naciśnij **Save and test the connection**. Puste pole hasła nie kasuje klucza. **Remove the stored key** kasuje.

**That model is already on the list.** Wybierz go jako **Main model** albo **Fast model** zamiast dodawać drugi raz.

**Enter a model id: letters, digits and . _ - : / @ only.** Wpisz identyfikator z listy modeli dostawcy. Spacje są niedozwolone.

**Built-in models cannot be removed.** Zostaw wiersz. Dodaj własny identyfikator, jeśli potrzebujesz innego modelu.

**Błędy dostawcy na Dashboard.** Klucz jest zły, dostawca nie zna identyfikatora modelu albo dostawca nie działa. Gdy jest zapasowy i błąd jest przed pierwszym słowem, odpowiada zapasowy. Popraw klucz albo model i użyj **Playground**.

**Odpowiedź wpada jednym blokiem, nie słowo po słowie.** Naciśnij **Test streaming** na **Health**. Jeśli test pada, proxy albo hosting buforuje odpowiedź. Poproś hosting o wyłączenie buforowania na adresie czatu sklepu.

**I cannot answer right now.** Dzienny budżet albo budżet tokenów jest osiągnięty, albo dostawca zawiódł i nie ma zapasowego. Podnieś budżet, poczekaj do następnego dnia albo napraw dostawcę. Asystent proponuje przekazanie pytania zespołowi.

**Prośba o czekanie albo zablokowana rozmowa.** Odwiedzający wysłał więcej niż **Messages per minute per visitor IP** albo więcej niż **Messages per conversation per day**. Poczekaj albo podnieś limit.

**Wyzwalacz nigdy nie wychodzi.** Przeczytaj ramkę na **Triggers**. **Allow proactive messages** jest wyłączone, wyzwalacz jest nieaktywny, **apply_offer** jest wyłączone, a wyzwalacz czeka, aż odwiedzający zapyta, albo wyzwalacze czekają na zgodę, a baner nigdy nie woła funkcji zgody. Użyj **Open the shop in test mode**, żeby pominąć zgodę, cool-down i limit jednej wiadomości na wizytę. Po prawdziwym teście cool-down chowa ten wyzwalacz w tej przeglądarce.

**Rabat nigdy nie wychodzi.** Nie ma oferty, oferta nie jest przypięta do wyzwalacza, koszyk jest poniżej minimum, dzienny limit jest osiągnięty, produkt jest w wykluczonej kategorii albo produkt już ma rabat. Asystent nie wymyśla procentu.

**Add to cart samo nic nie dodaje.** Karta jest tylko kartą. Odwiedzający naciska **Add to cart**. W trybie katalogu narzędzia koszyka zostają wyłączone.

**Test e-mail sent.** to sukces. **The e-mail could not be sent. Check the e-mail settings of the shop.** oznacza, że poczta sklepu nie wyszła. **Enter a valid e-mail address.** oznacza, że adres testu jest pusty albo zły. Maile do klientów wymagają też **Send cart reminders** na Yes i działającego adresu cron.

**Deleted N conversations.** Nacisnąłeś **Delete** w **Privacy**. Te wątki zniknęły.

## 6. Dla developera

### 6.1 Przegląd

Nazwa techniczna `prestamindai`, klasa `prestamindai`, wersja w pliku `1.8.9`, nazwa na liście **PrestaMind AI**, autor MyPresta.eu, zakładka `front_office_features`. Zgodność od 1.7.6.0, maksimum `99.99.99`. Nie ma własnego `enable()` ani `disable()`. Wyłączenie w PrestaShop zatrzymuje zarejestrowane hooki. Włączenie rejestruje je ponownie przez rdzeń.

`PmaiConfig` czyta i zapisuje klucze `Configuration` z prefiksem `PMAI_`. `PmaiProviderRouter` wybiera `PmaiOpenAiProvider`, `PmaiAnthropicProvider`, `PmaiGeminiProvider` albo `PmaiMockProvider`. DeepSeek i zgodny adres używają klienta zgodnego z OpenAI. `PmaiOrchestrator` składa prompt, woła model i uruchamia narzędzia z `PmaiToolRegistry`. Ceny użyte przy wywołaniu są kopiowane do wiersza zużycia.

### 6.2 Pliki

| Plik | Rola |
|---|---|
| `prestamindai.php` | Instalacja, odinstalowanie, hooki, zakładka menu, przekierowanie z **Configure**. |
| `sql/install.php` | Tworzy 16 tabel. |
| `sql/uninstall.php` | Kasuje te tabele. |
| `controllers/admin/AdminPrestamindaiController.php` | Zakładki zaplecza i akcje POST. |
| `controllers/front/chat.php` | Adres czatu na sklepie. |
| `controllers/front/cron.php` | Jeden adres cron. |
| `src/Service/PmaiConfig.php` | Wartości startowe, listy modeli, ceny wbudowane, modele własne. |
| `src/Admin/PmaiForms.php` | Każdy formularz zaplecza i opisy pól. |
| `src/Admin/PmaiSectionHelp.php` | Tekst pomocy każdej zakładki. |
| `src/Agent/PmaiToolRegistry.php` | 14 narzędzi i filtr trybu katalogu. |
| `src/Llm/PmaiOpenAiProvider.php` | OpenAI, DeepSeek i zgodny adres. |
| `src/Llm/PmaiAnthropicProvider.php` | Anthropic. |
| `src/Llm/PmaiGeminiProvider.php` | Gemini. |
| `src/Llm/PmaiMockProvider.php` | Demo offline. |
| `src/Knowledge/PmaiIndexer.php` | Odkrywanie i reindeks. |
| `src/Safety/PmaiGuardrails.php` | Zamiana karty, IBAN i PESEL. |
| `upgrade/` | Aktualizacje wersji wołają `upgradeDb()`. |
| `translations/{iso}.php` | Napisy zaplecza. |
| `views/` | Szablony, CSS i JS zaplecza i sklepu. |

### 6.3 Kontrolery

`AdminPrestamindai` to klasa menu. Rodzicem jest pierwsza istniejąca klasa spośród `AdminParentCustomerThreads`, `AdminCustomerThreads` i `IMPROVE`. Etykieta zakładki to **PrestaMind AI**. `getContent()` przekierowuje do tego kontrolera.

Parametr `pmai_tab` to jedno z: `dashboard`, `live`, `history`, `conversations`, `knowledge`, `triggers`, `playground`, `evals`, `escalations`, `settings`, `updates`. Ustawienia czytają też `pmai_sub`: `health`, `widget`, `provider`, `knowledge`, `limits`, `privacy`, `escalation`, `reminders`, `couriers`, `tools`.

`controllers/front/chat.php` przyjmuje operacje sklepu: init, message, feedback, confirm, add_to_cart, escalate, poll, event i open_trigger. `controllers/front/cron.php` wymaga tokenu cron. Zły token zwraca JSON `ok: false` i `error: token`.

### 6.4 Hooki

Rejestrowane przy instalacji: `displayBackOfficeHeader`, `dashboardZoneTwo`, `actionAdminControllerSetMedia`, `displayHeader`, `displayBeforeBodyClosingTag`, `displayFooter`, `actionObjectProductAddAfter`, `actionObjectProductUpdateAfter`, `actionObjectProductDeleteAfter`, `actionObjectCmsAddAfter`, `actionObjectCmsUpdateAfter`, `actionObjectCmsDeleteAfter`, `actionValidateOrder`, `registerGDPRConsent`, `actionDeleteGDPRCustomer`, `actionExportGDPRData`.

`displayBeforeBodyClosingTag` wypisuje widżet, a `displayFooter` jest zapasem. Hooki produktu i CMS oznaczają dokumenty do reindeksu. `actionValidateOrder` łączy zamówienie z liczbą przychodu. Hooki GDPR eksportują albo kasują wiersze tego klienta. **Repair hooks** woła `ensureHooks()` dla brakującej nazwy. Moduł nie wystawia własnych hooków dla innych modułów.

### 6.5 Nadpisania

Moduł nie nadpisuje klasy ani kontrolera PrestaShop.

### 6.6 Baza

Odinstalowanie robi `DROP TABLE` na każdej tabeli poniżej. Instalacja używa `CREATE TABLE IF NOT EXISTS`, więc nieudane odinstalowanie, które zostawiło tabele, zachowałoby stare wiersze. Zwykłe odinstalowanie je kasuje, a następna instalacja jest pusta.

| Tabela | Zawartość |
|---|---|
| `PREFIX_pmai_thread` | Jedna rozmowa: sklep, klient, gość, kanał, status, strona. |
| `PREFIX_pmai_message` | Wiadomości wątku, w tym payload kart. |
| `PREFIX_pmai_tool_call` | Nazwa narzędzia, argumenty i wynik wiadomości. |
| `PREFIX_pmai_doc` | Zindeksowany dokument produktu, CMS albo FAQ. |
| `PREFIX_pmai_chunk` | Kawałki dokumentu, w tym embedding, gdy jest. |
| `PREFIX_pmai_cache` | Zcache'owane odpowiedzi o zasadach. |
| `PREFIX_pmai_trigger` | Reguły wyzwalaczy. |
| `PREFIX_pmai_offer` | Reguły rabatów. |
| `PREFIX_pmai_event` | Zdarzenia sklepu używane przez wyzwalacze i statystyki. |
| `PREFIX_pmai_usage` | Jedno wywołanie modelu: dostawca, model, tokeny, migawka ceny, koszt, status. Bez treści wiadomości. |
| `PREFIX_pmai_request` | Wiersze limitu zapytań. |
| `PREFIX_pmai_cart_reminder` | Jedno wysłane przypomnienie koszyka. |
| `PREFIX_pmai_escalation` | Przekazanie, zwrot albo wycena oraz wynik powiadomienia. |
| `PREFIX_pmai_ratelimit` | Liczniki krótkiego okna. |
| `PREFIX_pmai_eval_case` | Pytanie testu jakości i wymagane słowa. |
| `PREFIX_pmai_eval_run` | Jeden przebieg tych testów. |

`PmaiConfig::PRICES_CHECKED` to `2026-10-31`. Wbudowane identyfikatory czatu i embeddingów oraz ceny są w `PmaiConfig::builtinModels()`, `builtinEmbeddingModels()` i `builtinPrices()`. Własne identyfikatory to JSON w `PMAI_CUSTOM_MODELS`. Poprawione ceny to JSON w `PMAI_MODEL_PRICES` i wygrywają z ceną wbudowaną.

### 6.7 Klucze i tłumaczenia

Każdy klucz to `PMAI_` plus nazwa z `PmaiConfig::defaults()`. Sekrety dostawców to `PMAI_KEY_OPENAI`, `PMAI_KEY_ANTHROPIC`, `PMAI_KEY_GEMINI`, `PMAI_KEY_DEEPSEEK`, `PMAI_KEY_MISTRAL`, `PMAI_KEY_COMPATIBLE`, `PMAI_KEY_MOCK` oraz `PMAI_KEY_DHLTRACK`. Są szyfrowane libsodium, gdy jest `sodium_crypto_secretbox`, w przeciwnym razie OpenSSL. `PMAI_CRON_TOKEN` to losowy hex tworzony przy instalacji, gdy jest pusty.

Klucze wyboru modelu to `PMAI_MODEL_MAIN_{PROVIDER}` i `PMAI_MODEL_FAST_{PROVIDER}`. Po instalacji: OpenAI `gpt-6.1-sol` / `gpt-6-luna`, Anthropic `claude-sonnet-5-5` / `claude-haiku-5-5`, Gemini `gemini-2.5-flash` / `gemini-2.5-flash-lite`, DeepSeek `deepseek-flash` / `deepseek-flash`, Mistral `mistral-large-latest` / `mistral-small-latest`, compatible `llama3.1` / `llama3.1`, mock `mock` / `mock`. `PMAI_PROVIDER` to `mock`. `PMAI_EMBED_PROVIDER` to `none`. `PMAI_EMBED_MODEL` jest puste, więc używany jest pierwszy wbudowany model embeddingów wybranego dostawcy.

`PMAI_BOT_NAME`, `PMAI_GREETING`, `PMAI_DISCLOSURE` i `PMAI_REMINDER_SUBJECT` są wielojęzyczne. Pomoc pól to HTML `desc` składany w `PmaiForms`. Język dodajesz tłumaczeniem `translations/{iso}.php`. Napisy, które nie idą przez `$this->l()`, zostają tak, jak są w tablicach PHP (nazwy kafelków dostawców, identyfikatory modeli, identyfikatory narzędzi).

### 6.8 Rozszerzanie

Szablon i CSS widżetu na sklepie da się nadpisać w motywie w zwykły sposób PrestaShop, pod `modules/prestamindai/views/`. Zaplecze nie jest nadpisaniem motywu. Nie zmieniaj identyfikatorów modeli w motywie. Model dodajesz na **Model provider**. Baner ciasteczek może wołać `window.PrestaMindAI.setConsent(true)` po akceptacji odwiedzającego. Moduł nie dostarcza banera.

## 7. Pomoc

Strona modułu: [https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html](https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html)

Żeby napisać w sprawie tego modułu, zaloguj się na konto klienta na mypresta.eu, otwórz formularz kontaktu i wybierz temat **Support for paid modules**. Formularz podaje, że przy modułach płatnych logowanie jest wymagane. Po zalogowaniu wybierz ten moduł z historii zakupów.
