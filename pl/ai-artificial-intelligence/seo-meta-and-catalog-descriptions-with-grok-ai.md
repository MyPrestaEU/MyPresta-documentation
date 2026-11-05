---
title: "My AI Grok - AI content generation - dokumentacja i instrukcja obsługi"
description: "Przewodnik dla właścicieli modułu: podłącz konto Grok (xAI), generuj opisy katalogu z panelu administracyjnego i rozwiązuj problemy, gdy coś nie działa."
sidebar:
  label: "My AI Grok - AI content generation - dokumentacja i instrukcja obsługi"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł SEO meta and catalog descriptions with Grok AI na MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai/)
>
> ---


## 1. Wymagania

Ten rozdział wymienia, czego potrzebuje Twój sklep i serwer, zanim moduł zacznie pisać teksty za Ciebie.

- **PrestaShop:** wersje od 1.6 do 9.x.
- **PHP:** wersja 7.0 lub nowsza. Na starszym PHP instalacja zostanie odrzucona z komunikatem.
- **Rozszerzenia PHP:** cURL. Moduł łączy się z Grokiem przez cURL.
- **Połączenia wychodzące:** serwer musi mieć możliwość otwierania bezpiecznych połączeń (HTTPS) z `https://api.x.ai/v1`. Jeśli blokuje je zapora sieciowa, każda generacja zakończy się błędem.
- **Inne moduły:** żadne. Moduł działa samodzielnie.
- **Konto xAI:** potrzebujesz własnego konta na https://console.x.ai, aby uzyskać klucz API Grok. Zapytania do Groka rozlicza xAI na Twoim koncie, a nie moduł.
- **Duże katalogi:** moduł pisze jedno pole jednego produktu na zapytanie. Długie uruchomienie masowe trwa więc tyle, ile wszystkie te zapytania razem. Korzystaj z limitów partii na ekranach Generate i Cron oraz ustaw wystarczająco wysoki limit czasu API dla wolnych modeli (zob. sekcja 3.4).

## 2. Instalacja

### 2.1 Wgranie, instalacja i włączenie

1. W panelu administracyjnym otwórz **Modules**, a następnie **Module Manager**.
2. Wgraj plik ZIP modułu albo znajdź go na liście, jeśli jest już na serwerze.
3. Kliknij **Install**. Instalacja sprawdza wersję PHP, tworzy dane modułu, a następnie włącza moduł.
4. Jeśli instalacja zatrzyma się z komunikatem, przeczytaj sekcję 5.1.

### 2.2 Co pojawia się w menu

- Pod **Modules** pojawia się nowa pozycja **AI Content Generator**. Kliknięcie otwiera ekran **Dashboard** modułu.
- Pozostałe ekrany modułu (Settings, Generate, New product, Cron, History, Images, Updates) otwierasz z paska nawigacji u góry modułu, a nie z menu po lewej stronie.
- Na stronie edycji produktu w zakładce **Modules** pojawia się blok **My AI Grok**, a obok pól tekstowych – małe przyciski **Generate with AI** (zob. sekcja 3.16).
- W górnym pasku każdej strony panelu administracyjnego może pojawić się skrót z magiczną różdżką (zob. **Admin Top Bar CTA** w sekcji 3.4).

Do ustawień dojdziesz też przez **Modules**, **Module Manager**, nazwa modułu, **Configure**.

### 2.3 Pamięć podręczna

Instalacja nie czyści pamięci podręcznej PrestaShop. Jeśli pozycja menu lub blok produktu nie pojawią się zaraz po instalacji, wyczyść cache samodzielnie w **Advanced Parameters**, **Performance** i odśwież stronę.

### 2.4 Odinstalowanie i ponowna instalacja

- **Co znika:** pozycja menu **AI Content Generator** i jej ukryte ekrany, 16 gotowych szablonów promptów wraz z dodanymi przez Ciebie, cała History (każdy zapisany prompt, odpowiedź i liczba tokenów) oraz zapisane ustawienia modułu (klucz API, model, reguły Studio, wybory cron, sekrety).
- **Co zostaje:** wszystkie teksty już zapisane w produktach i kategoriach. Moduł nigdy nie usuwa wygenerowanych tekstów.
- **Pozostałości:** kilka zapamiętanych wyborów z ekranów Generate (filtry, np. ostatnio wybrany język lub status) może pozostać w sklepie. Nie mają one żadnego wpływu.
- **Ponowna instalacja:** nowa instalacja zaczyna od wartości domyślnych podanych w rozdziale 3. Klucz API, reguły Studio, własne szablony i History nie zostaną przywrócone, więc wcześniej zapisz lub wyeksportuj to, czego potrzebujesz.

## 3. Konfiguracja i praca w panelu administracyjnym

To główny rozdział. Zaczyna się od całego procesu pracy, a następnie opisuje każdy ekran w kolejności paska nawigacji.

Zrzuty ekranu pochodzą z angielskiego panelu administracyjnego. Nazwy przycisków, pól i komunikatów podajemy w tym rozdziale pogrubioną czcionką tak, jak widnieją na ekranie w wersji angielskiej, a opisy po polsku.

### 3.1 Cały proces krok po kroku

1. **Połącz Grok.** Otwórz **Settings**, potem **Grok**. Wklej klucz API z https://console.x.ai i wybierz model. Zapisz.
2. **Ustaw styl marki (opcjonalnie).** Otwórz **Settings**, potem **Studio**. Wypełnij głos marki, odbiorców, ton, słownik nazw do zachowania, słowa zakazane, miesięczny budżet i bramkę jakości. Pola niepotrzebne zostaw puste.
3. **Przetestuj bezpiecznie.** W **Settings**, **Playground** wyślij dowolną instrukcję i przeczytaj odpowiedź. Na stronie produktu użyj zakładki **Simulate** i **Try**. W tych dwóch miejscach nic nie jest zapisywane w katalogu.
4. **Uzupełnij jeden produkt.** Otwórz produkt, przejdź do zakładki **Modules**, **My AI Grok**, **Generate**, wybierz język i naciśnij **Fill** przy polu. Możesz też użyć przycisków **Generate with AI** obok własnych pól produktu, a następnie zapisać produkt.
5. **Uzupełnij wiele produktów.** Otwórz **Generate**, **Products**. Przefiltruj listę, naciśnij **Go to next step**, wybierz szablon lub wpisz instrukcję, wskaż, co generować, jak traktować istniejący tekst i które języki, a następnie naciśnij **Run on the list below**. To samo zrobisz dla kategorii w **Generate**, **Categories**.
6. **Partie bez nadzoru.** Otwórz **Cron**, zapisz wybory i skopiuj adres do harmonogramu zadań na serwerze (zob. sekcje 3.12 i 4.2).
7. **Audyt i cofanie zmian.** **History** pokazuje każde wywołanie z promptem, odpowiedzią, statusem i tokenami. W produkcie zakładka **History** pozwala przywrócić wcześniejszy tekst przyciskiem **Restore**.

Wygenerowany tekst jest zapisywany bezpośrednio w katalogu, gdy tylko nadejdzie odpowiedź. Przed pierwszym dużym uruchomieniem przetestuj kilka produktów przez **Simulate** albo filtry **Product IDs** i **Product Limit**.

### 3.2 Nawigacja i panel Help

![Dashboard with the navigation bar and date presets](https://mypresta.eu/docs/images/docs/myaigrok-dashboard.webp)

*Dashboard: pasek nawigacji znajduje się u góry każdego ekranu modułu.*

Pasek pokazuje nazwę modułu z wersją oraz następujące pozycje, w tej kolejności:

| Pozycja | Co tam znajdziesz |
|---|---|
| **Dashboard** | Wykresy zapytań, tokenów i błędów. |
| **Settings** | Pięć podzakładek: **General**, **Grok**, **Studio**, **Prompt templates**, **Playground**. |
| **Generate** | Dwie podzakładki: **Products** i **Categories** do uruchomień masowych. |
| **New product** | Tworzy nowy produkt na podstawie krótkiego opisu. |
| **Cron** | Buduje adresy, które serwer może wywoływać według harmonogramu. |
| **History** | Pełna lista wywołań z filtrami. |
| **Images** | Przełącznik i instrukcja wyszukiwania zdjęć produktów. |
| **Updates** | Sprawdza, czy opublikowano nowszą wersję modułu. |

Najedź na pozycję, aby przeczytać krótkie wyjaśnienie. Okrągły przycisk **Help** przy krawędzi ekranu otwiera panel boczny z pomocą dla bieżącej strony. Zamkniesz go krzyżykiem.

Każde pole w module jest wyjaśnione na ekranie w trzech częściach: **What it does**, **How to configure** i **Effect**. Poniższe tabele przedstawiają te teksty prostymi słowami i dodają wartość, jaką pole ma tuż po instalacji.

### 3.3 Dashboard

Otwórz **AI Content Generator** w **Modules** albo pozycję **Dashboard** na pasku.

- **Presety dat:** **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time**. Strona otwiera się na **30 days**.
- **From** i **To:** wybierz własne daty i naciśnij **Apply**. Jeśli From jest późniejsze niż To, daty zostaną zamienione.
- **Active service:** pokazuje Grok i model wybrany w Settings.
- **Karty:** **Requests** (każde zapisane wywołanie), **Success**, **Errors**, **Tokens sent** (rozmiar promptów) i **Tokens received** (rozmiar odpowiedzi).
- **Wykresy:** **Requests and errors**, **Tokens sent and received** oraz **Requests by model**. Przy zakresach dłuższych niż około cztery miesiące dni są grupowane tygodniami.

| Element | Po instalacji | Co robi |
|---|---|---|
| **Presets** | 30 days | Zlicza generacje Groka zapisane w History w wybranym zakresie dat. Klucz API i model wybiera się nie tutaj, lecz w Settings. |
| **From / To / Apply** | ostatnie 30 dni | Rysuje tylko ten wycinek. Z tej strony nic w katalogu nie jest generowane ani zmieniane, a History nie jest usuwana. |

### 3.4 Settings – General

Otwórz **Settings**, potem **General**.

![Settings, General tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-general.webp)

*Settings – General: przełączniki dla całego sklepu i limit czasu API.*

Te przełączniki decydują o tym, co pracownicy widzą w panelu administracyjnym. Sam zapis tutaj nie zmienia tekstów produktów. Naciśnij **Save**; potwierdzenie brzmi **Settings Updated**.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Live mode** | Wyłączone | Oznacza, że moduł działa w prawdziwym sklepie, a nie w konfiguracji testowej. Włącz go w sklepie produkcyjnym. Na kopii testowej (staging) zostaw wyłączony, jeśli nie chcesz, aby pracownicy traktowali narzędzia jako gotowe. Wyłączony zachowuje te same narzędzia, ale sygnalizuje, że to nie środowisko produkcyjne. |
| **Debug mode** | Wyłączone | Zapisuje dodatkowe szczegóły diagnostyczne, gdy wywołanie Groka się nie powiedzie. Włączaj tylko na czas badania błędu, potem wyłącz. Włączony dodaje komunikaty techniczne do logu PrestaShop (**Advanced Parameters**, **Logs**). Wyłączony ogranicza log do zwykłej historii generacji. Klienci tego nigdy nie widzą. |
| **API timeout (seconds)** | 120 | Ile sekund może trwać jedno wywołanie Groka, zanim moduł się podda. Dla zwykłych opisów użyj 120. Dla długich pakietów SEO lub wolnych modeli podnieś w stronę 600. Nie schodź poniżej 10. Wartości poniżej 10 są zapisywane jako 10, a powyżej 600 jako 600; pusta lub nienumeryczna wartość jest zapisywana jako 120. Krótki limit szybko kończy się błędem i zapisuje go. Długi limit czeka na wolny model zamiast przerywać dobrą odpowiedź. |
| **Product Edit History** | Włączone | Pokazuje na stronie produktu wcześniejsze zapisy AI, dzięki czemu można przywrócić starą wartość. Włącz, jeśli redaktorzy mają móc cofać generację. Włączone dodaje do bloku modułu produktu zakładkę **History** z przyciskiem **Restore**. Wyłączone ją ukrywa. Dawne wiersze i tak pozostają w History. |
| **Admin Top Bar CTA** | Włączone | Dodaje w górnym pasku panelu skrót otwierający generator. Włącz w sklepach, w których personel często generuje teksty. Wyłącz, jeśli pasek jest już zatłoczony. Włączone pokazuje przycisk na każdej stronie panelu. Wyłączone usuwa tylko ten przycisk. Menu modułu zostaje. |
| **Product edit page Form** | Włączone | Pokazuje panel generatora na stronie edycji produktu: zakładki **Generate**, **Simulate** i **Photos** bloku **My AI Grok**. Włącz dla redaktorów katalogu. Wyłącz, jeśli mają być używane tylko generowanie masowe i cron. |
| **AI Image Finder** | Włączone | Pozwala redaktorowi poprosić model o strony, na których prawdopodobnie są zdjęcia bieżącego produktu. Włącz, jeśli chcesz mieć ten przycisk na stronie produktu. To Ty wybierasz, które obrazy zaimportować. Wyłączone ukrywa zawartość zakładki **Photos**. Nic nie jest pobierane, dopóki ktoś nie potwierdzi obrazu. |
| **AI Image Search Prompt** | Prosi o dokładnie 5 adresów stron | Instrukcja wysyłana przy wyszukiwaniu zdjęć produktu. `{product_name}` i `{product_description}` są zastępowane bieżącym produktem. Zachowaj prośbę o listę adresów stron. Zmień sformułowanie, jeśli chcesz strony producentów lub inną liczbę. Precyzyjniejszy prompt zwraca trafniejsze strony. Niejasny zwraca niezwiązane linki. Nic nie jest zapisywane, dopóki nie wybierzesz zdjęć. |

Ten sam przełącznik **AI Image Finder** i prompt istnieją także na ekranie **Images** (sekcja 3.14); oba miejsca zmieniają to samo ustawienie.

### 3.5 Settings – Grok

Otwórz **Settings**, potem **Grok**.

![Settings, Grok tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-grok.webp)

*Settings – Grok: klucz API, model i wartości próbkowania.*

Ten formularz zawiera konto Grok używane przy każdej generacji, także w cron i przy przyciskach w produkcie. Pola próbkowania zmieniają zróżnicowanie sformułowań. Nie zmieniają tego, które produkty są aktualizowane.

Komunikaty, które możesz zobaczyć po **Save**: **OpenAi Settings Updated** (sukces; nazwa to pozostałość, ale ekran należy do Groka), **Grok API KEY field is invalid!** (brak zapisanego klucza, a wklejony ma mniej niż 10 znaków) oraz **OpenAi Model field is invalid!** (nazwa modelu jest zbyt krótka). Klucz ze spacjami wokół jest czyszczony automatycznie i możesz zobaczyć **Grok API Key has been automatically cleaned (whitespace removed).**

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Grok API KEY** | puste | Sekret, który pozwala temu sklepowi wywoływać Twoje konto Grok. Wklej klucz z https://console.x.ai. Spacje są usuwane przy zapisie. Pozostaw pole bez zmian, aby zachować już zapisany klucz. Prawidłowy klucz pozwala na generacje Groka. Pusty lub błędny sprawia, że wywołania kończą się błędem, który trafia do History. |
| **Model** | grok-4.7 | Model Grok, który pisze tekst. Wbudowane nazwy to grok-4.7, grok-4.6, grok-4.5, grok-4.3, grok-4.20-0309-non-reasoning i grok-4.20-0309-reasoning. Pozostają na liście. Nazwy dodane w następnym wierszu można usunąć. Następna generacja użyje tego modelu. Model, do którego klucz nie ma dostępu, zwraca błąd zamiast tekstu. |
| **Add a Grok model** | brak dodatkowych modeli | Dodaje identyfikator modelu Grok spoza wbudowanej listy, aby można go było wybrać powyżej. Wpisz dokładny identyfikator z konta Grok (na przykład grok-4.6), a następnie kliknij **Add model**. Nowy identyfikator pojawi się na liście **Model** i stanie się aktywnym modelem. **Remove** obok dodanego identyfikatora usuwa tylko identyfikatory dodane tutaj. Wbudowanych nie można usunąć. Jeśli usuniesz aktywny model, aktywny staje się grok-4.7. Komunikaty: **Model added.**, **Model removed.**, **That model is already built in.**, **Built-in models cannot be removed.**, **Enter a model id such as grok-4.6.** |
| **Max Tokens** | 3200 | Górna granica długości odpowiedzi, liczona w tokenach, a nie w słowach. Dla meta description użyj około 256, a dla pełnego opisu HTML 1000 lub więcej. Niski limit ucina odpowiedź. Wysoki pozwala na dłuższy tekst i zwiększa koszt na rachunku dostawcy. Nie zmienia promptu. |
| **Temperature** | 0.7 | Jak swobodnie model dobiera słowa. Niższa wartość daje stabilniejszy wynik, wyższa bardziej zróżnicowany. Pozostań między 0 a 1. Użyj około 0,2 dla specyfikacji i tekstów meta, około 0,7 dla opisów. Zmieniaj tę wartość albo **Top P**, nie obie. Niska wartość powtarza podobną strukturę. Wysoka daje bardziej różne sformułowania i większe ryzyko odejścia od zadania. |
| **Top P** | 1 | Inny sposób ograniczania, jak zaskakujące może być następne słowo. 1 uwzględnia pełny zakres. Zostaw 1, jeśli ustawiasz już **Temperature**. Niższą wartość, np. 0,9, stosuj tylko wtedy, gdy chcesz węższego słownictwa. Niższe wartości dają bezpieczniejsze i bardziej powtarzalne odpowiedzi. |
| **Frequency Penalty Value** | 0 | Ogranicza linie powtarzające tę samą frazę w jednej odpowiedzi. Użyj 0, chyba że opisy ciągle kopiują to samo zdanie. Wypróbuj 0,3 do 0,6. Pozostań między -2 a 2. Wartość dodatnia zmniejsza prawdopodobieństwo powtórzeń. Nie uwzględnia innych produktów. |
| **Presence Penalty Value** | 0 | Skłania odpowiedź do nowych wątków zamiast pozostawania przy słowach już użytych. Domyślnie 0. Spróbuj małej wartości dodatniej, jeśli każdy akapit porusza ten sam punkt. Pozostań między -2 a 2. Niektóre nowsze modele ignorują to pole. |

Moduł sam zapamiętuje, których z tych wartości dany model nie przyjmuje, i przestaje je do niego wysyłać, więc nie zobaczysz z tego powodu błędu.

### 3.6 Settings – Studio

Otwórz **Settings**, potem **Studio**.

![Settings, Studio tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-studio.webp)

*Settings – Studio: zasady marki dołączane do każdego promptu.*

Studio jest nakładane na każdy prompt, także przy przyciskach w produkcie, generowaniu masowym i cron. Puste pola są pomijane. Budżet 0 oznacza brak limitu miesięcznego. Moduł informuje też model, w jakim języku pisać, na podstawie języka produktu, kategorii lub używanego ekranu. Naciśnij **Save studio**; potwierdzenie brzmi **Studio settings saved.** Tekst już zapisany w katalogu nie jest nadpisywany.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Brand voice** | puste | Mówi modelowi, kto przemawia, aby teksty produktów pasowały do sklepu, a nie do ogólnego asystenta. Napisz krótkie wytyczne, np.: wyspecjalizowany warsztat, krótkie zdania, bez przesady. Każda kolejna generacja zaczyna od tego głosu. Zmiana nie przepisuje tekstu już zapisanego. |
| **Audience** | puste | Określa czytelnika, dla którego model ma pisać. Użyj prostego określenia, np. profesjonalni monterzy lub kupujący po raz pierwszy. Odpowiedzi używają słownictwa i przykładów dopasowanych do tego czytelnika. |
| **Tone** | puste | Ustala nastrój sformułowań: formalny, ciepły, techniczny itd. Wystarczy jedno lub dwa słowa. Zostaw puste, aby decydował prompt. Nie zmienia modelu ani temperatury. |
| **Glossary** | puste | Lista nazw marek, materiałów i pisowni, które model musi skopiować dokładnie. Wpisz jeden termin w wierszu, w postaci, jaką chcesz zachować. Nowy tekst preferuje te pisownie. Terminy spoza listy mogą nadal zostać przeformułowane. |
| **Forbidden words** | puste | Słowa i frazy, które nie mogą pojawić się w zapisanej odpowiedzi. Jedno słowo lub fraza w wierszu. Lista jest sprawdzana tylko przy włączonej **Quality gate**. Odpowiedź zawierająca jedną z tych pozycji jest odrzucana i nie trafia do produktu. Próba i tak zostaje zapisana w History jako błąd. |
| **Monthly generation budget** | 0 | Ogranicza liczbę udanych generacji, jakie sklep może wykonać w bieżącym miesiącu kalendarzowym. Wpisz liczbę całkowitą. 0 oznacza brak limitu. Licznik zaczyna się od nowa pierwszego dnia miesiąca. Po osiągnięciu limitu nowe generacje zatrzymują się z komunikatem o budżecie do następnego miesiąca. Nieudane wywołania nie są liczone. Liczby ujemne są zapisywane jako 0. |
| **Quality gate** | Włączone | Sprawdza odpowiedź modelu względem listy zakazanych słów, zanim cokolwiek zostanie zapisane. Włącz po wypełnieniu **Forbidden words**. Wyłącz, jeśli lista ma być tylko przechowywana na później. Włączone blokuje pasującą odpowiedź. Wyłączone zapisuje odpowiedź nawet wtedy, gdy zawiera słowo z listy. |

Budżet zlicza wiersze w History, więc użycie **Clear list** na ekranie History zaczyna zliczanie miesiąca od zera.

### 3.7 Settings – Prompt templates

Otwórz **Settings**, potem **Prompt templates**.

![Settings, Prompt templates tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-templates.webp)

*Settings – Prompt templates: lista zapisanych instrukcji.*

Szablon to zapisana instrukcja. Redaktorzy wybierają ją zamiast wpisywać za każdym razem to samo polecenie. Znaczniki zastępcze (placeholders) są zastępowane produktem lub kategorią, dla której generujesz. Sklep startuje z 16 gotowymi szablonami dla nazw produktów, opisów, meta title, meta description i tagów, wszystkie włączone.

**Lista** pokazuje **ID**, **Title**, **Prompt**, **Status** (kliknij ptaszek lub krzyżyk, aby włączyć lub wyłączyć szablon) i **Timestamp**. Każdy wiersz ma **Edit** i **Delete**. Zaznacz kilka wierszy i użyj akcji zbiorczej **Delete** (zostaniesz zapytany: **Are you sure you want to delete the selected prompts?**). Przycisk **Add new** nad listą tworzy szablon.

**Formularz** (**Generate Prompt Template**) ma trzy pola. Naciśnij **Save Prompt** albo **Go Back to Module Settings**, aby wyjść bez zapisu. Komunikaty: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.** Podwójne cudzysłowy wpisane w prompcie są zapisywane jako pojedyncze.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Status** | Wyłączone dla nowego szablonu | Pokazuje lub ukrywa ten szablon na listach rozwijanych na stronie produktu, w generowaniu masowym i w cron. Włącz szablony, z których ma korzystać personel. Wersję roboczą wyłącz zamiast ją usuwać. Włączone szablony pojawiają się na listach. Wyłączone zostają w tej tabeli, ale nie są oferowane. |
| **Prompt title** | puste (wymagane) | Nazwa widoczna dla redaktorów na liście szablonów. Nie jest wysyłana do modelu. Użyj krótkiej etykiety, np. HTML description with features. |
| **Prompt content** | puste (wymagane) | Instrukcja wysyłana do modelu. Napisz polecenie tak, jak powiedziałbyś je copywriterowi, i wspomnij o długości, HTML i języku, jeśli mają znaczenie. Gdy ktoś uruchamia szablon, znaczniki są wypełniane danymi bieżącego elementu, a odpowiedź trafia do wybranego pola. |

**Znaczniki zastępcze** (placeholders), które możesz wpisać w prompcie (są wypełniane dla każdego produktu, kategorii lub strony przy uruchomieniu szablonu):

| Znacznik | Zastępowany przez |
|---|---|
| `{product_name}` `{product_description}` `{product_description_short}` `{product_tags}` `{product_reference}` `{product_ean13}` `{product_weight}` | Własne dane produktu w języku, w którym piszesz. |
| `{product_brand}` `{product_default_category}` `{product_category_description}` `{product_categories}` | Marka produktu, nazwa i opis jego kategorii domyślnej oraz nazwy wszystkich jego kategorii. |
| `{product_attributes}` `{product_features}` `{product_feature_values}` `{product_images}` | Atrybuty kombinacji produktu, nazwy cech, pary nazwa i wartość cechy oraz linki do jego zdjęć. |
| `{category_name}` `{category_description}` `{category_parent_name}` | Kategoria, dla której piszesz, oraz nazwa jej kategorii nadrzędnej. |
| `{cms_title}` `{brand_name}` `{brand_description}` `{brand_short_description}` | Dane strony treści lub marki otwartej w momencie użycia skrótu z górnego paska. |
| `{shop_name}` `{shop_url}` `{shop_language}` `{shop_country}` `{shop_currency}` | Dane całego sklepu: nazwa, domena, język, domyślny kraj i kod domyślnej waluty. |

Używaj tylko znaczników, które mają sens tam, gdzie szablon będzie uruchamiany. Znacznik produktu w poleceniu dla kategorii pozostaje zwykłym wpisanym tekstem.

### 3.8 Settings – Playground

Otwórz **Settings**, potem **Playground**.

![Settings, Playground tab](https://mypresta.eu/docs/images/docs/myaigrok-settings-playground.webp)

*Settings – Playground: brudnopis na jedną dowolną instrukcję.*

Playground wysyła jedną dowolną instrukcję do aktywnego modelu i wypisuje odpowiedź pod przyciskiem. Możesz wspomnieć nazwę sklepu, adres sklepu, nazwę produktu, referencję lub cechy produktu, aby moduł podstawił dane z katalogu. Odpowiedź zostaje na tej stronie. Żadne pole produktu ani kategorii nie jest zapisywane.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Instruction box** | puste | Wpisz instrukcję zwykłym językiem i naciśnij **Generate**. Aktywny dostawca otrzymuje ten tekst razem z regułami Studio. Odpowiedź pojawia się pod przyciskiem wraz z liczbą zużytych tokenów. Katalog nie jest aktualizowany. |

Jeśli naciśniesz **Generate** przy pustym polu, zobaczysz **Write a prompt first.** Każde wywołanie jest zapisywane w History z typem **general**.

### 3.9 Generate – Products

Otwórz **Generate**, potem **Products**. Możesz też kliknąć przycisk **My AI Grok** obok akcji zbiorczych na liście produktów.

Generowanie masowe ma dwa kroki: filtr budujący listę oraz uruchomienie na tej liście.

**Krok 1: Filter products to update.** Ten krok tylko buduje listę produktów. Nic nie jest zapisywane w produktach, dopóki na następnym ekranie nie wybierzesz zakresu i języków i nie naciśniesz **Run**. Te filtry nie są zapisywane jako ustawienia sklepu. Gdy będziesz gotowy, naciśnij **Go to next step**. Puste pole filtra jest ignorowane.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Product Categories** | nic nie zaznaczono | Ogranicza listę do produktów znajdujących się w zaznaczonych kategoriach (lub mających jedną z nich jako domyślną). Zaznacz potrzebne kategorie. Zostaw drzewo puste, jeśli kategoria nie ma znaczenia. |
| **Brand** | Select brand (no filter) | Zostawia produkty jednego producenta. Wybierz markę albo zostaw pierwszą pustą opcję, jeśli mają być uwzględnione wszystkie marki. |
| **Product status** | Active | Zostawia produkty w sprzedaży, wyłączone albo oba rodzaje. Wybierz **Active** dla aktywnego katalogu, **Disabled** dla szkiców lub **Both**. |
| **Product stock** | All products | Opcjonalnie pomija produkty bez stanu magazynowego. **Only in stock products** usuwa z listy produkty bez dostępnej ilości. **All products** nie uwzględnia stanu magazynowego w filtrze. |
| **Update only** | Update all | Na podstawie historii generacji uwzględnia produkty nigdy nieopisane przez ten moduł (**Products that have not been updated with OpenAi content**), tylko te, które już były opisane (**Products that already have been updated with OpenAi content**), albo wszystkie (**Update all**). Wybierz „jeszcze nieopisane” przy pierwszym przejściu, a „już opisane” przy ponownym pisaniu. Produkt uznawany jest za już zaktualizowany, gdy History zawiera dla niego jakikolwiek wpis, także nieudaną próbę. |
| **Product IDs** | puste | Ogranicza listę do wskazanych identyfikatorów produktów. Wpisz identyfikatory oddzielone przecinkami, np. 12,45,103. |
| **Product Reference** | puste | Ogranicza listę do wskazanych referencji. Wpisz jedną lub więcej referencji oddzielonych przecinkami. |
| **Product Add Date From** | puste | Najwcześniejsza data utworzenia, jaką może mieć produkt, aby został uwzględniony. Produkty utworzone wcześniej są pomijane. |
| **Product Add Date To** | puste | Najpóźniejsza data utworzenia, jaką może mieć produkt, aby został uwzględniony. Produkty utworzone później są pomijane. |
| **Minimum product ID** | puste | Najmniejszy identyfikator produktu, który może pojawić się na liście. Wpisz liczbę całkowitą. |
| **Maximum product ID** | puste | Największy identyfikator produktu, który może pojawić się na liście. Wpisz liczbę całkowitą. |
| **Product Limit** | puste (bez limitu) | Ogranicza liczbę produktów ładowanych do listy generacji. W dużym katalogu użyj małej liczby, np. 20. Następny ekran nigdy nie pokaże więcej, więc jedno uruchomienie nie przejdzie przypadkiem całego katalogu. |

**Krok 2: Mass product generation.** Następny ekran pokazuje tabelę pasujących produktów (**ID**, **Reference**, **Result**) z kontrolkami uruchomienia nad nią.

![Mass product generation with the filtered list](https://mypresta.eu/docs/images/docs/myaigrok-generate-products.webp)

*Generate – Products: szablon, zakres, istniejący tekst, języki i lista, na której działa uruchomienie.*

Pisze przefiltrowane produkty jeden po drugim aktywnym modelem. Każdy produkt w tabeli jest aktualizowany w zaznaczonych językach. Produkty spoza filtra pozostają nietknięte. Wiersz pokazuje wynik, gdy tylko dany produkt się zakończy.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Template** | **Choose a template** (brak) | Wypełnia pole promptu z szablonu zapisanego w Settings. Wybierz tytuł albo zostaw pierwszą opcję i wpisz własny prompt w polu poniżej. Model otrzymuje tekst z pola, z podstawionymi dla każdego wiersza znacznikami produktu. Sam tytuł nie jest wysyłany. Jeśli pole pozostanie puste, używane jest gotowe krótkie polecenie dla każdego pola. |
| **What to generate** | Descriptions | **Descriptions** pisze opis długi i krótki. **Meta title and meta description** pisze oba pola meta. **Descriptions and meta together** pisze wszystkie cztery. Pola poza tym wyborem pozostają bez zmian. Każde pole ma własne zapytanie. |
| **Existing text** | Replace | **Replace** nadpisuje pole. **Skip if filled** zostawia wypełnione pole i nie wywołuje dla niego modelu. **Add above** i **Add below** zachowują stary tekst i dołączają nowy przed lub po nim. Replace zmienia zapisaną wartość. Skip chroni wypełnione pola. Add zachowuje obie wersje w tym samym polu. |
| **Languages** | zaznaczony jest język Twojej sesji w panelu | Zaznacz każdy język, który ma być napisany. Odznacz język, aby go nie ruszać. Każdy zaznaczony język jest generowany osobno. Odznaczone języki zachowują obecny tekst. |
| **Run on the list below** | – | Rozpoczyna uruchomienie. Wiersz stanu pokazuje postęp (np. 3 / 24 i nazwa pola) i kończy się komunikatem **Finished N products.** Jeśli nie zaznaczono żadnego języka, zobaczysz **Select at least one language.** |

Każdy wiersz w kolumnie **Result** podaje po jednej linii na pole i język, np. nazwę pola, a po niej **success**, **skipped** lub **error** i krótki komunikat. **skipped** z **Product skipped.** oznacza, że pole miało już tekst i wybrano **Skip if filled**. Linie **error** zawierają przyczynę; ta sama awaria jest zapisana w History.

Zostaw tę kartę przeglądarki otwartą, dopóki uruchomienie nie wyświetli **Finished**. Uruchomienie jest sterowane przez stronę: wysyła jedno zapytanie naraz, a zamknięcie lub przeładowanie karty je zatrzymuje. Produkty już ukończone pozostają zapisane. Bardzo długi tekst jest skracany do limitów PrestaShop: nazwy do 128 znaków, krótkie opisy do 800, meta title do 69, a meta description do 159.

### 3.10 Generate – Categories

Otwórz **Generate**, potem **Categories**. Działa jak ekran produktów, ale z mniejszą liczbą filtrów.

**Krok 1: Filter categories to update.** Ten krok tylko buduje listę kategorii. Nic nie jest wysyłane do modelu, dopóki na następnym ekranie nie napiszesz promptu i nie uruchomisz generowania. Filtry nie są zapisywane jako ustawienia sklepu. Naciśnij **Go to next step**.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Categories** | nic nie zaznaczono | Wybiera kategorie, które pojawią się na liście w następnym kroku. Zaznacz jedną lub więcej kategorii. Zostaw drzewo puste, aby uwzględnić każdą kategorię pasującą do statusu poniżej. |
| **Category status** | Active | Zostawia kategorie aktywne, wyłączone albo oba rodzaje (**Active**, **Disabled**, **Both**). Następny krok wyświetla tylko kategorie o tym statusie. |

**Krok 2: Mass category generation.**

![Mass category generation](https://mypresta.eu/docs/images/docs/myaigrok-generate-categories.webp)

*Generate – Categories: instrukcja, pole, istniejący tekst, język i lista kategorii.*

Pisze jedno pole dla każdej kategorii z przefiltrowanej listy. Każda kategoria z listy jest aktualizowana w tym języku. Pozostałe pola i inne języki pozostają bez zmian.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Instruction box** (nad listą pól) | puste | Instrukcja wysyłana dla każdej kategorii. Opisz ton, długość i HTML. Użyj `{category_name}`, gdy chcesz mieć nazwę kategorii w poleceniu. Każda kategoria jest generowana z tego samego tekstu. Jeśli pole jest puste, używane jest gotowe krótkie polecenie. |
| **Field selector** | Description | Pole kategorii, które pisze to uruchomienie: **Description**, **Name**, **Meta title**, **Meta description** lub **Additional description**. Zapisywane jest tylko to pole. Pozostałe pola kategorii zostają bez zmian. Jeśli Twój PrestaShop nie ma pola Additional description dla kategorii, zobaczysz **Error! This PrestaShop version does not support the category Additional Description field.** |
| **Existing text selector** | Replace | **Replace** nadpisuje pole. **Skip if filled** zostawia je i nie wywołuje modelu dla tej kategorii. |
| **Language selector** | język Twojego panelu | Wersja językowa, która zostanie napisana. Wybierz jeden język. Uruchom ponownie dla kolejnego języka. Zmienia się tylko ten język. |
| **Run on the categories below** | – | Rozpoczyna uruchomienie. Wyniki pojawiają się w wierszach, jak na ekranie produktów. |

Pod listą ekran pokazuje także drugi formularz o nazwie **Generate category content**. Do generowania użyj przycisku **Run on the categories below** nad nim. Ten drugi formularz tylko zapamiętuje wybory i odsyła do filtra kategorii (zob. sekcja 5.12).

### 3.11 New product

Otwórz **New product**. Ten ekran zamienia krótki opis w szkic produktu i może wstawić ten szkic do katalogu.

![New product screen](https://mypresta.eu/docs/images/docs/myaigrok-new-product.webp)

*New product: opis, opcjonalna strona źródłowa, język i kategoria domyślna.*

**Generate data** pokazuje szkic i nie zapisuje produktu. **Create product** dodaje aktywny produkt w tym języku i kategorii, kopiuje ze szkicu nazwę, opisy, meta, tagi, cechy, cenę i referencję, nadaje mu początkowy stan 100 sztuk i umieszcza go w wybranej kategorii.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **What is the product?** | puste | Opis, który model rozwija w nazwę, opisy, meta, tagi, cechy, referencję i cenę. Opisz produkt kilkoma zdaniami. Wspomnij materiały, odbiorców i nazwy, które trzeba zachować. Bogatszy opis daje trafniejszy szkic. Puste pole jest odrzucane z komunikatem **Prompt is required**. |
| **Optional source URL** | puste | Dodaje do opisu tekst odczytany z publicznej strony, aby szkic mógł opierać się na istniejącej stronie produktu. Wklej pełny adres internetowy albo zostaw puste. Czytelna strona jest dołączana jako dodatkowy kontekst. Strona, której sklep nie może odczytać, jest ignorowana i używany jest sam opis. |
| **Language** | domyślny język sklepu | Język sklepu, w którym zapisywany jest tekst nowego produktu. Inne języki nie są wypełniane przez ten ekran. Nazwa, opisy, meta i tagi są zapisywane tylko w tym języku. |
| **Default category ID** | 2 | Identyfikator kategorii przypisany jako kategoria domyślna produktu. Wpisz numeryczny identyfikator z **Catalog**, **Categories**. 2 to zwykle Home. Nowy produkt trafia do tej kategorii. |
| **Generate data** | – | Prosi model o szkic i wypisuje go jako tekst uporządkowany pod przyciskami. Jeśli odpowiedzi nie da się odczytać, zobaczysz **Failed to parse AI response. Please try again.** |
| **Create product** | – | Wstawia szkic. Po sukcesie pole pokazuje **Product #** i identyfikator nowego produktu. Naciśnięcie przed wygenerowaniem pokazuje **Generate the product first.** |

Produkt jest tworzony bez zdjęć, z pierwszą regułą podatkową sklepu i ceną ze szkicu; po utworzeniu otwórz go i sprawdź cenę, podatek, zdjęcia i stan magazynowy. Jeśli nie zapisano klucza API, ekran pokazuje **Add an API key in the module settings first.**

### 3.12 Cron

Otwórz **Cron**. Ten ekran buduje adresy, które Twój serwer wywołuje według harmonogramu, aby uzupełniać pola produktów lub kategorii małymi partiami. Nic nie uruchamia się samo. Sklep nic nie robi, dopóki serwer nie wywoła adresu.

![Cron screen](https://mypresta.eu/docs/images/docs/myaigrok-cron.webp)

*Cron: panel adresu kategorii, a następnie formularz produktów z adresem i przełącznikami.*

**Co zawiera ekran, od góry do dołu:** panel **Category cron** z adresem kategorii; formularz **CRON JOB Settings – Generate product content using Grok**; formularz **CRON JOB Settings - Generate category content using Grok**; oraz panel **Cron parameters** z adresem produktów, wybranym polem, celem i rozmiarem partii.

**Ważne:** adresy pokazane na tym ekranie kończą się na sekrecie. Aby wywołanie cokolwiek zrobiło, musisz dodać do adresu akcję. Pełne postacie adresów znajdują się w sekcji 4.2. Ponadto **Enable Cron Feature** musi mieć wartość **Yes**, w przeciwnym razie każde wywołanie cron, dla produktów i kategorii, odpowie, że funkcja jest wyłączona.

**Formularz produktów** (naciśnij **Save** na dole formularza):

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Enable Cron Feature** | No | Pozwala serwerowi generować tekst według harmonogramu, bez klikania przez pracownika po katalogu. Włącz dopiero po zapisaniu sekretu, pola, języka i promptu poniżej. Serwer nadal musi wywołać adres. Włączone sprawia, że zapisany adres wykonuje pracę. Ten przełącznik bramkuje także adres kategorii. |
| **Cron Job Secret Token** | długa losowa wartość utworzona przy instalacji | Długie hasło, które musi znaleźć się w adresie produktów. Bez niego sklep odrzuca wywołanie. Zachowaj wygenerowaną wartość. Jeśli ją zmienisz, skopiuj nowy adres do harmonogramu serwera. Nikt, kto nie zna tego sekretu, nie uruchomi cron produktów. Zmiana natychmiast unieważnia stary adres. Użyj co najmniej 24 znaków (zob. sekcja 5.10). |
| **Update Field** | description | Jedno pole produktu, które przepisuje to polecenie cron: **name**, **description**, **description_short**, **meta_title**, **meta_description** lub **tags**. Aby uzupełnić opis i meta, utwórz dwa polecenia cron z dwoma różnymi polami. Każde uruchomienie pisze tylko to pole w języku wybranym poniżej. |
| **Selected Products** | pendingGrok | Decyduje, które produkty nadal czekają. **pendingGrok** bierze produkty nigdy skutecznie nieopisane przez ten moduł w żadnym polu. **pendingField** bierze produkty jeszcze nieopisane dla tego konkretnego pola, dzięki czemu można uruchomić kilka zadań cron (np. opis i nazwę) na tych samych produktach. **emptyField** bierze tylko produkty, w których wybrane pole jest puste w wybranym języku. Każde uruchomienie pomija produkty, które już nie pasują, więc zakończony katalog przestaje się zmieniać. Wcześniejsze nieudane próby nie liczą się jako zapisane i są ponawiane. |
| **Product Categories** | nic nie zaznaczono | Ogranicza cron do produktów znajdujących się w zaznaczonych kategoriach. Zaznacz jedną lub więcej kategorii. Zostaw drzewo puste, aby ignorować kategorię i użyć tylko pozostałych filtrów. Przed zaznaczeniem kategorii zobacz sekcję 5.10. |
| **Product ID list** | puste | Ogranicza uruchomienie do jawnej listy identyfikatorów produktów. Wpisz identyfikatory oddzielone przecinkami, np. 12,45,103. Litery i inne znaki są usuwane przy zapisie. Tylko te produkty mogą być aktualizowane tym poleceniem. |
| **Language** | domyślny język sklepu z chwili instalacji | Wersja językowa pola produktu, które pisze ten cron. Wybierz jeden język sklepu. Inne języki wymagają własnego polecenia cron. |
| **Product to update** | 5 products | Ile pasujących produktów jest przetwarzanych przy każdym wywołaniu adresu (od 2 do 1000). Zacznij od 5 lub 10, aby wolny model nie przekroczył limitu czasu serwera. Zwiększ, gdy uruchomienie kończy się bez problemów. |
| **Prompt Template** | nie wybrano | Zapisana instrukcja wysyłana do modelu dla każdego produktu w tym uruchomieniu. Wybierz włączony szablon z Settings. Znaczniki w szablonie są wypełniane dla każdego produktu. Wybierz szablon przed pierwszym wywołaniem. Późniejsza zmiana szablonu wpływa tylko na następne uruchomienie. |
| **Enable Debug** | No | Pokazuje, co zrobiłby cron, gdy otworzysz adres w przeglądarce, bez zapisywania produktów. Włącz na czas sprawdzania polecenia. Wyłącz, zanim harmonogram serwera użyje tego samego adresu. Włączone wypisuje plan i nie zapisuje tekstu w katalogu. |
| **CRON JOB interval** | Every Hour | Rytm, który planujesz zastosować na serwerze (od **Every 1 Minute** do **Every 6 Hours**). Dopasuj do harmonogramu, który utworzysz. Moduł sam nie uruchamia harmonogramu i nie wymusza tej wartości. |
| **Product Cron Job command** | – | Pokazuje adres bazowy. Skopiuj go, dodaj akcję zgodnie z sekcją 4.2 i wklej wynik do harmonogramu serwera. Możesz utworzyć dowolnie wiele poleceń cron. |

**Formularz kategorii** działa tak samo, z własnym sekretem i własną partią:

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Cron Job Secret Token** | długa losowa wartość utworzona przy instalacji | Długie hasło, które musi znaleźć się w adresie kategorii. Jest oddzielne od sekretu produktów. Zachowaj wygenerowaną wartość. Wywołania bez tego sekretu są odrzucane. Zmiana natychmiast unieważnia stary adres kategorii. |
| **Update Field** | description | Jedno pole kategorii, które przepisuje to polecenie: **name**, **description**, **meta_title** lub **meta_description**. Nazwa, opis i meta wymagają osobnych poleceń, jeśli chcesz uzupełnić wszystkie. |
| **Selected categories** | pendingGrok | Te same trzy wybory co dla produktów (**pendingGrok**, **pendingField**, **emptyField**), zastosowane do kategorii. Każde uruchomienie pomija kategorie, które już nie pasują. |
| **Language** | domyślny język sklepu z chwili instalacji | Wersja językowa pola kategorii, które pisze ten cron. Inne języki wymagają własnego polecenia. |
| **Categories to update** | 5 categories | Ile pasujących kategorii jest przetwarzanych przy każdym wywołaniu adresu. Zacznij od 5 lub 10. |
| **Prompt Template** | nie wybrano | Zapisana instrukcja wysyłana do modelu dla każdej kategorii w tym uruchomieniu. Napisz polecenie dla kategorii, a nie dla produktu (np. z `{category_name}`). |
| **Enable Debug** | No | Pokazuje, co zrobiłby cron kategorii, gdy otworzysz adres w przeglądarce, bez zapisywania kategorii. Wyłącz, zanim harmonogram użyje adresu. |
| **CRON JOB interval** | Every Hour | Rytm, który planujesz zastosować na serwerze. To tylko przypomnienie. |
| **Category Cron Job command** | – | Pokazuje adres bazowy do skopiowania. Dodaj akcję zgodnie z sekcją 4.2. |

Cron kategorii nigdy nie rusza samej kategorii głównej (home).

### 3.13 History

Otwórz **History**. Ten ekran to raport z każdego wywołania Groka i służy jako ślad audytowy.

![History screen](https://mypresta.eu/docs/images/docs/myaigrok-history.webp)

*History: filtry, sumy, tabele zestawień i lista wywołań.*

Zawęź karty, tabele zestawień i listę historii do jednego wycinka generacji. Kliknij preset daty lub ustaw **From** i **To**. Następnie opcjonalnie ogranicz według modelu, typu, statusu, języka, pracownika, identyfikatora produktu lub kategorii albo słowa, które musi wystąpić w prompcie lub odpowiedzi. Naciśnij **Filter**. Widoczne zostają tylko pasujące wiersze. Zapisana historia nie jest usuwana, a żaden produkt nie jest zmieniany.

| Element | Po instalacji | Co robi |
|---|---|---|
| **Date presets** | This month | **Today**, **7 days**, **30 days**, **This month**, **All time**. |
| **From / To** | od pierwszego dnia miesiąca do dziś | Własny zakres dat. |
| **Model** | Any | Tylko wywołania wykonane tym modelem. |
| **Type** | Any | Tylko ten rodzaj wywołań (zob. tabelę poniżej). |
| **Status** | Any | **Success** lub **Error**. |
| **Language** | Any | Tylko wywołania dla tego języka. |
| **Employee** | Any | Tylko wywołania uruchomione przez tego pracownika. Wywołania uruchomione przez cron nie mają pracownika. |
| **Product / category ID** | puste | Tylko wiersze dla tego identyfikatora (produkt, kategoria, strona treści lub marka o tym numerze). |
| **Prompt or reply contains** | puste | Tylko wiersze, w których prompt, odpowiedź lub tekst błędu zawiera to słowo. |
| **Filter** | – | Stosuje filtry. |

**Karty:** **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total** i **Average time**. Kreska oznacza, że Grok nie zwrócił liczby tokenów dla tego wywołania.

**Tabele zestawień:** **By day**, **By model**, **By type**, **By language**, **By employee**, każda z kolumnami **Group**, **Calls**, **Sent**, **Received** i **Total**. Mała liczba obok Calls to liczba błędów w tej grupie.

**Lista** nosi tytuł **Prompt history** i pokazuje 50 wierszy na stronę z kolumnami **ID**, **Status** (zielona plakietka **Success** lub czerwona **Error**), **Prompt**, **Reply / Error**, **Provider** (usługa, model i czas trwania oraz kod statusu z Groka, jeśli jest), **Sent**, **Received**, **Total**, **Entity ID**, **Type** i **Timestamp**. Akcja wiersza **View** otwiera pełny prompt i odpowiedź z tokenami, a **Back to the list** wraca do listy. Jeśli wiersz został w międzyczasie usunięty, zobaczysz **This log entry no longer exists.**

| Wartość typu | Znaczenie |
|---|---|
| **general** | Dowolna instrukcja z Playground lub ze skrótu w górnym pasku. |
| **singleCategory**, **singleCMS**, **singleBrand** | Skrót z górnego paska użyty przy otwartej kategorii, stronie treści lub marce. |
| **product_name**, **product_description**, **product_description_short**, **product_meta_title**, **product_meta_description**, **product_tags** | Pole produktu zostało napisane (lub podjęto próbę) przez przycisk, uruchomienie masowe lub cron. |
| **product_seo_pack** | Pakiet SEO napisał nazwę, opisy i meta za jednym razem. |
| **category_name**, **category_description**, **category_meta_title**, **category_meta_description**, **category_additional_description** | Pole kategorii zostało napisane. |
| **error** | Nieudane wywołanie produktu. |

Przycisk paska narzędzi **Clear list** usuwa na stałe każdy wiersz w History i potwierdza komunikatem **Log list successfully deleted.** To usuwa także punkty przywracania na stronach produktów i zeruje miesięczne zliczanie budżetu, więc używaj go ostrożnie.

### 3.14 Images

Otwórz **Images**. Ten ekran włącza lub wyłącza wyszukiwanie zdjęć na stronie produktu i przechowuje instrukcję wysyłaną do modelu.

![Images screen](https://mypresta.eu/docs/images/docs/myaigrok-images.webp)

*Images: przełącznik AI Image Finder i jego prompt.*

Te dwa pola sterują wyszukiwaniem zdjęć na stronie produktu. Ich zapis nie pobiera obrazów i nie zmienia tekstów produktów. Naciśnij **Save**; potwierdzenie brzmi **Settings saved.**

| Pole | Po instalacji | Co robi |
|---|---|---|
| **AI Image Finder** | Włączone | Pokazuje lub ukrywa wyszukiwanie zdjęć na stronie edycji produktu. Włącz, gdy redaktorzy mają szukać zdjęć bieżącego produktu. Wyłącz, aby usunąć ten przycisk. Włączone pokazuje wyszukiwanie. Wyłączone je ukrywa. Obraz jest importowany dopiero po potwierdzeniu przez kogoś. |
| **AI Image Search Prompt** | Prosi o dokładnie 5 adresów stron | Instrukcja wysyłana przy wyszukiwaniu zdjęć produktu. Znaczniki nazwy i opisu produktu są zastępowane bieżącym produktem. Zachowaj prośbę o listę adresów stron (ekran nazywa to tablicą JSON z adresami URL stron). Zmień sformułowanie, jeśli chcesz strony producentów lub inną liczbę linków. Precyzyjniejszy prompt zwraca trafniejsze strony. Niejasny zwraca niezwiązane linki. Nic nie jest zapisywane, dopóki redaktor nie wybierze obrazu. |

### 3.15 Updates

Otwórz **Updates** (na samym końcu paska).

![Updates screen](https://mypresta.eu/docs/images/docs/myaigrok-updates.webp)

*Updates: ręczne sprawdzenie, automatyczne powiadomienia i link do strony produktu.*

Ekran nosi tytuł **MyPresta Updates**. Sprawdza w MyPresta.eu, czy jest nowsza wersja modułu, i może ostrzec Cię w panelu administracyjnym. Katalog i wygenerowane teksty pozostają bez zmian.

| Pole | Po instalacji | Co robi |
|---|---|---|
| **Manual Check** | – | Jednorazowo łączy się z serwerami aktualizacji MyPresta.eu i porównuje wersję zdalną z wersją w tym sklepie. Kliknij **Check Now** po instalacji lub gdy podejrzewasz nowe wydanie. Obok przycisku pojawi się **Module is up to date!** albo **New version available!**. |
| **Automatic Notifications** | Włączone | Okresowo (mniej więcej co 3 dni) sprawdza aktualizacje w panelu administracyjnym. Ustaw **Enabled**, aby otrzymać baner ostrzegawczy, gdy istnieje nowsza wersja. Pracownicy zobaczą wtedy powiadomienie z linkiem do szczegółów. Ustaw **Disabled**, jeśli aktualizacjami zarządzasz wyłącznie ręcznie. Zapisz przyciskiem **Save**; potwierdzenie to **Update settings saved.** |
| **Product Page** | link | Otwiera w nowej karcie oficjalną stronę produktu MyPresta dla tego modułu. |

### 3.16 Praca na stronie edycji produktu

Otwórz produkt (**Catalog**, **Products**, produkt), następnie zakładkę **Modules**, potem **My AI Grok**. Blok ma do czterech zakładek: **Generate**, **Simulate**, **Photos** i **History**. To, które zakładki zobaczysz, zależy od **Product edit page Form** i **Product Edit History** w sekcji 3.4. Produkt musi być zapisany przynajmniej raz.

![My AI Grok block on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-edit.webp)

*Strona edycji produktu, zakładka Generate: chipy języków, zachowanie istniejącego tekstu i jedna karta na pole.*

**Zakładka Generate.** Każdy przycisk pisze jedno pole produktu, a tekst jest od razu zapisywany w produkcie.

- **Language:** jeden chip na każdy aktywny język oraz **Every language**, który uruchamia kolejno każdy język.
- **If the field already has text:** **Replace**, **Add above**, **Add below** lub **Skip if filled**. Działają tak, jak opisano w sekcji 3.9.
- **Karty pól:** **Description** (długi tekst z krótkim wstępem i listą cech), **Short description** (krótkie zwykłe podsumowanie, do około 400 znaków), **Name**, **Meta title** (około 70 znaków), **Meta description** (około 160 znaków) i **Tags** (lista oddzielona przecinkami). Naciśnij **Fill** na karcie.
- **SEO pack:** **Fill all** wypełnia nazwę, oba opisy i oba pola meta jednym zapytaniem. Jest dostępny tylko w zakładce Generate. Potem odśwież stronę produktu, aby zobaczyć nowe wartości.
- **Use your own instruction or a saved prompt:** otwórz tę sekcję, aby przefiltrować zapisane szablony według tytułu lub tekstu, wybrać jeden (pierwszy kafelek **Standard brief** używa gotowego polecenia dla pola, które naciskasz) albo wpisać własny tekst w **Instruction**. Zostaw puste, aby użyć standardowego polecenia. Jeśli żaden szablon nie pasuje do filtra, zobaczysz **No prompt matches that filter.**
- Wynik jest też wypisywany w panelu pod kartami, wraz z liczbą tokenów.

Po **Fill** przeładuj stronę produktu, aby zobaczyć nowy tekst w formularzu.

**Zakładka Simulate.** Najpierw wypróbuj pole. Odpowiedź zostaje na tej stronie, a produkt nie jest zmieniany. Ma te same chipy języków i karty pól, ale każda karta ma **Try** zamiast **Fill**. Każde Try nadal tworzy wiersz w History.

![Simulate tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-simulate.webp)

*Zakładka Simulate: **Try** pokazuje odpowiedź bez zapisu.*

**Zakładka Photos.** Gdy **AI Image Finder** jest włączony, Grok szuka zdjęć tego produktu.

![Photos tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-photos.webp)

*Zakładka Photos: znajdź strony, zaznacz zdjęcia, dodaj je do produktu.*

1. Naciśnij **Find pages**. Grok proponuje strony internetowe, a moduł odczytuje zdjęcia z maksymalnie pięciu z nich (do 24 zdjęć).
2. Zaznacz zdjęcia, które chcesz.
3. Naciśnij **Add selected to this product**. Zdjęcia są pobierane i dołączane; pierwsze zaznaczone zdjęcie zostaje okładką. Przed tym krokiem nic nie jest zapisywane.

Adresy sieci prywatnych nigdy nie są otwierane. Jeśli wyszukiwarka jest wyłączona, zakładka informuje, że musisz włączyć **AI Image Finder** w Settings, General, i ponownie otworzyć produkt.

**Zakładka History.** Wymienia wcześniejsze zapisy dla tego produktu z kolumnami **When**, **Type**, **Status** i przyciskiem **Restore**. **Restore** pyta **Restore the previous value?** i po potwierdzeniu przywraca wcześniejszy tekst oraz informuje, że trzeba odświeżyć stronę. Ogólna History sklepu nie jest usuwana. **Restore** jest oferowany tylko dla udanych wierszy, które zapisały poprzednią wartość. Gdy lista jest pusta, zakładka pokazuje **No generations for this product yet.**

![History tab on the product edit page](https://mypresta.eu/docs/images/docs/myaigrok-product-history.webp)

*Zakładka History: wcześniejsze zapisy z przyciskiem Restore.*

### 3.17 Inne miejsca, w których pojawia się moduł

- **Przyciski Generate with AI obok pól.** W formularzu edycji produktu mały przycisk pojawia się obok opisu, krótkiego opisu, meta title i meta description każdego języka. W formularzu edycji kategorii pojawia się obok opisu, dodatkowego opisu, meta title i meta description. Kliknij go. Jeśli sklep ma więcej niż jeden język, zostaniesz poproszony o wybór **Current language**, **All languages** lub **Cancel**. Tekst trafia do pola formularza. Zapisz produkt lub kategorię, aby go zachować. Używane jest gotowe polecenie dla tego pola, a reguły Studio nadal obowiązują. Jeśli element nigdy nie był zapisany, zobaczysz **Save the product once before generating.** (lub **Save the category once before generating.**). Przełącznik **Product edit page Form** ukrywa tylko blok modułu w zakładce **Modules**; nie usuwa tych małych przycisków.
- **Skrót w górnym pasku.** Przy włączonym **Admin Top Bar CTA** ikona magicznej różdżki w górnym pasku otwiera małe okno: wybierz **Template** (opcjonalnie), wpisz instrukcję i naciśnij **Generate**. Gdy jesteś na ekranie edycji kategorii, strony treści lub marki, odpowiednie znaczniki są wypełniane. Odpowiedź pokazuje się w oknie i nic nie jest zapisywane.
- **Lista produktów.** Przycisk **My AI Grok** obok akcji zbiorczych otwiera **Generate**, **Products**.

## 4. Front sklepu

Moduł nie ma żadnego ekranu widocznego dla klientów. Nie pokazuje niczego w nagłówku, stopce ani na stronie produktu, kategorii czy kasy, a motyw nie ma nic do wyświetlenia ani nadpisania. Klienci nigdy nie widzą żadnego narzędzia do generowania tekstu; widzą wyłącznie tekst, który już zapisałeś w katalogu.

### 4.1 Adresy używane przez sam moduł

Dwa adresy internetowe Twojego sklepu należą do modułu. Pierwszego nigdy nie otwierasz samodzielnie.

- **Adres generatora** jest wywoływany przez przyciski wewnątrz panelu administracyjnego (Fill, Try, Run, Playground itd.). Chroni go sekret wbudowany w strony panelu.
- **Adres cron** jest wywoływany przez harmonogram Twojego serwera albo przez Ciebie w przeglądarce podczas testów. Opisano go poniżej.

### 4.2 Adres cron

Adres ma postać adresu Twojego sklepu, po którym następują ścieżka modułu, sekret i akcja. Zastąp znaczniki własnymi wartościami. Użyj sekretu widocznego na ekranie **Cron** i nigdy nie publikuj go publicznie.

Dla produktów:

`https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent`

Dla kategorii:

`https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent`

Adres pokazany na ekranie Cron kończy się po sekrecie (panel kategorii dodaje inne zakończenie, którego sklep nie używa). Część `action` dodaj samodzielnie. Bez akcji sklep odpowiada **Invalid action!**

Partia używa wyborów zapisanych na ekranie Cron: pole, reguła wyboru, język, szablon, rozmiar partii i debug. Każde wywołanie aktualizuje jedną partię, a potem się kończy. Każdy udany zapis pojawia się też w History z metodą **cron**.

Aby zaplanować to na serwerze Linux, utwórz zadanie cron, które pobiera adres, na przykład co dziesięć minut:

```
*/10 * * * * curl -s "https://YOUR-SHOP/module/myaigrok/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent" > /dev/null
```

Zachowaj adres w cudzysłowie, ponieważ zawiera znak ampersand. W systemie Windows użyj Harmonogramu zadań z zadaniem otwierającym adres. Aby przetestować, przełącz **Enable Debug** na **Yes**, zapisz i otwórz adres w przeglądarce: strona wypisze plan (parametry, wybrane produkty lub kategorie i końcową instrukcję) i niczego nie zapisze. Nie udostępniaj tego wyniku, ponieważ zawiera parametry Twojego adresu. Przełącz debug z powrotem na **No**, zanim harmonogram użyje adresu.

### 4.3 Co odpowiada adres cron

| Co widzisz | Co zrobić |
|---|---|
| **Cron Job feature is disabled. You can enable it from the module settings.** | Ustaw **Enable Cron Feature** na **Yes** na ekranie Cron i zapisz. |
| **The token does not exist or it's wrong!** | Sekretu brakuje lub nie pasuje. Skopiuj sekret ponownie z ekranu Cron. |
| **Invalid action!** | Brakuje części `action` lub jest błędnie zapisana. Użyj jednej z dwóch postaci z sekcji 4.2. |
| **All must include all mandatory parameters!** | Wartość, taka jak pole, cel, rozmiar partii, język lub szablon, jest pusta. Otwórz ekran Cron, uzupełnij ją i zapisz. |
| **No valid product IDs provided.** | Product ID list nie zawiera użytecznej liczby. Popraw lub opróżnij listę i zapisz. |
| **No products to update.** lub **No categories to update.** | Nic już nie pasuje do reguły. To normalny koniec zakończonego zadania. Zmień regułę wyboru lub filtry, aby przetworzyć więcej. |
| **N products have been updated.** lub **N categories have been updated.** | Partia zakończona. Harmonogram weźmie następną partię przy kolejnym wywołaniu. |
| **Error!** z komunikatem (na przykład **Monthly generation budget reached.** lub **Reply rejected by the studio quality gate.**) | Przeczytaj komunikat i postępuj według rozdziału 5. Uruchomienie zatrzymuje się na pierwszym błędzie. |
| **Error! The model returned an empty response.** | Zwiększ **Max Tokens** w Settings, Grok albo spróbuj innego modelu. |
| **Error! Could not save product** i identyfikator | Nie udało się zapisać produktu z nowym tekstem, na przykład dlatego, że PrestaShop odrzucił tekst. Sprawdź ten produkt i uruchom ponownie. |

## 5. Problemy

### 5.1 Instalacja jest odrzucana

- **Objaw:** **This module requires PHP 7.0.0 or newer. This server is running PHP** i Twoja wersja, albo **Could not create the module database tables.**
- **Przyczyna:** PHP serwera jest zbyt stare albo użytkownik bazy danych nie może tworzyć tabel.
- **Co zrobić:** poproś hosting o przełączenie na PHP 7.0 lub nowsze albo o nadanie użytkownikowi bazy uprawnienia do tworzenia tabel, a następnie zainstaluj ponownie.

### 5.2 Brakuje pozycji menu lub bloku w produkcie

- **Objaw:** brak **AI Content Generator** w **Modules** albo brak bloku **My AI Grok** w zakładce **Modules** produktu.
- **Przyczyna:** nieaktualny cache, brak uprawnień profilu pracownika albo wyłączony przełącznik.
- **Co zrobić:** wyczyść cache w **Advanced Parameters**, **Performance**. W **Advanced Parameters**, **Team**, **Permissions** sprawdź, czy Twój profil może otwierać ekrany modułu. Jeśli menu nadal brakuje, odinstaluj i zainstaluj moduł ponownie. W przypadku bloku produktu sprawdź **Product edit page Form** i **Product Edit History** w Settings, General, oraz zapisz produkt raz, aby miał identyfikator.

### 5.3 Klucz jest odrzucany lub go brakuje

- **Objaw:** **Grok API KEY field is invalid!** przy zapisie, albo **The Grok API key is not set. Add it in the module settings.** przy generowaniu, albo wiersz błędu w History po każdej próbie.
- **Przyczyna:** pole klucza jest puste lub zbyt krótkie, klucz skopiowano z literówką lub został unieważniony w xAI.
- **Co zrobić:** otwórz **Settings**, **Grok**, wklej świeży klucz z https://console.x.ai i naciśnij **Save**. Następnie otwórz **History**, przefiltruj **Status** po **Error** i otwórz najnowszy wiersz, aby przeczytać dokładną odpowiedź Groka.

### 5.4 Model jest odrzucany

- **Objaw:** **OpenAi Model field is invalid!** albo błędy w History, że model nie istnieje lub nie masz do niego dostępu.
- **Przyczyna:** nazwa modelu jest zbyt krótka, błędnie wpisana albo Twoje konto xAI nie może wywołać tego modelu.
- **Co zrobić:** w **Settings**, **Grok** wybierz jeden z modeli wbudowanych albo dodaj dokładny identyfikator z konta xAI przez **Add model**, a następnie zapisz.

### 5.5 Wywołanie przekracza limit czasu

- **Objaw:** **Grok request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.** albo, na ekranie, **The request timed out or the shop blocked it.**
- **Przyczyna:** wolny model, bardzo długa odpowiedź, zajęta usługa xAI albo serwer blokujący długie zapytania.
- **Co zrobić:** zwiększ **API timeout (seconds)** w **Settings**, **General** (do 600), zmniejsz **Max Tokens** dla krótkich pól albo wypróbuj szybszy model. W przypadku cron zmniejsz **Product to update**, aby partia mieściła się w limicie czasu serwera.

### 5.6 Odpowiedź jest pusta lub ucięta

- **Objaw:** **The model hit the token limit before returning any text. Increase "Max Tokens" in the module settings — reasoning models spend part of that budget on thinking.** albo **The response was blocked by the provider content filter. Try rewording the prompt.** albo **The model returned an empty response.**
- **Co zrobić:** zwiększ **Max Tokens** w **Settings**, **Grok**. W przypadku zablokowanej odpowiedzi przeformułuj instrukcję. Potem spróbuj ponownie.

### 5.7 Osiągnięto budżet miesięczny

- **Objaw:** **Monthly generation budget reached. Raise it in the studio settings or wait until next month.**
- **Co zrobić:** otwórz **Settings**, **Studio**, zwiększ **Monthly generation budget** lub ustaw 0 i zapisz. Nieudane wywołania nie są liczone.

### 5.8 Odpowiedź odrzucona z powodu zakazanego słowa

- **Objaw:** **The reply was rejected because it contains a forbidden word from the studio settings.** (cron pokazuje **Reply rejected by the studio quality gate.**). Produkt pozostaje bez zmian, a History pokazuje wiersz błędu.
- **Co zrobić:** uruchom generowanie ponownie (sformułowania za każdym razem się różnią), skróć **Forbidden words** w **Settings**, **Studio** albo przełącz **Quality gate** na **Disabled**.

### 5.9 Pole jest pomijane lub tekst jest nieprawidłowy

- **Objaw:** wiersz zawiera **skipped** z **Product skipped.** (lub **Category skipped.**) albo tekst został dopisany do starego zamiast go zastąpić.
- **Przyczyna:** **Existing text** ustawiono na **Skip if filled**, **Add above** lub **Add below**.
- **Co zrobić:** wybierz **Replace** i uruchom ponownie. Aby cofnąć niechciany zapis w produkcie, użyj zakładki **History** produktu i naciśnij **Restore**.

### 5.10 Cron nic nie robi, powtarza się albo adres przestaje działać

- **Objaw:** harmonogram się uruchamia, ale nic nie jest zapisywane, albo te same produkty są przepisywane, albo adres, który działał wczoraj, teraz odpowiada **The token does not exist or it's wrong!**
- **Cron wyłączony:** **Cron Job feature is disabled.** Ustaw **Enable Cron Feature** na **Yes** na ekranie Cron i zapisz.
- **Brak akcji w adresie:** otrzymujesz **Invalid action!** Dodaj akcję, jak pokazano w sekcji 4.2.
- **Pozostawiony debug:** debug wypisuje plan i nigdy nie zapisuje. Ustaw **Enable Debug** na **No** i zapisz.
- **Brak szablonu:** jeśli **Prompt Template** jest pusty, wysyłana instrukcja jest pusta. Wybierz włączony szablon i zapisz.
- **Sekret zastąpiony:** przycisk **Generate Token** obok sekretu nie ma w tej wersji żadnej funkcji, więc wpisz lub wklej długi losowy sekret samodzielnie. Sekret krótszy niż 24 znaki jest zastępowany nowym losowym przy następnym otwarciu dowolnej strony panelu, a stary adres przestaje działać. Skopiuj sekret ponownie z ekranu Cron.
- **Wciąż te same produkty:** gdy zaznaczysz **Product Categories**, produkty, których kategoria domyślna jest zaznaczona, są wybierane przy każdym wywołaniu, nawet jeśli reguła wyboru mówi, że nie są już oczekujące. Zostaw drzewo kategorii puste i ogranicz cron przez **Product ID list** albo użyj ekranu **Generate** do pracy ograniczonej kategoriami.
- **Błędy serwera:** błędy cron są wypisywane tylko w odpowiedzi adresu; nie są zapisywane w History. Uruchom adres w przeglądarce z włączonym debugiem, aby je przeczytać.

### 5.11 Uruchomienie masowe zatrzymuje się w połowie

- **Objaw:** wiersz stanu przestaje się zmieniać albo niektóre wiersze nie mają wyniku.
- **Przyczyna:** karta przeglądarki została zamknięta lub przeładowana, komputer przeszedł w stan uśpienia albo wywołanie przekroczyło limit czasu.
- **Co zrobić:** naciśnij **Run** ponownie. W **Existing text** wybierz **Skip if filled**, aby nie płacić dwa razy za gotowe pola. Wiersze z błędem podają przyczynę; ta sama przyczyna jest w History.

### 5.12 Formularz Generate category content nic nie robi

- **Objaw:** po naciśnięciu **Generate content** w formularzu pod listą kategorii trafiasz do filtra kategorii i nic nie jest zapisywane.
- **Co zrobić:** użyj przycisku **Run on the categories below** nad tym formularzem. Na ekranach filtrów produktów i kategorii przycisk **Module settings** nie otwiera ustawień tego modułu; użyj pozycji **Settings** na pasku nawigacji.

### 5.13 Problemy ze zdjęciami produktu (Photos)

- **Objaw:** **Find pages** nie pokazuje zdjęć albo widzisz **No images could be imported.** ze szczegółami.
- **Przyczyna:** Grok zasugerował strony bez użytecznych zdjęć, strona zablokowała pobieranie przez sklep, adres wskazywał na sieć prywatną albo plik nie był prawidłowym obrazem.
- **Co zrobić:** naciśnij **Find pages** ponownie, przeformułuj **AI Image Search Prompt** na ekranie **Images** (np. poproś o strony producentów) albo wgraj zdjęcia ręcznie.

### 5.14 Ekran New product kończy się błędem

- **Objaw:** **Add an API key in the module settings first.**, **Prompt is required**, **Failed to parse AI response. Please try again.** lub **Failed to create product**.
- **Co zrobić:** zapisz klucz API w **Settings**, **Grok**, napisz opis i naciśnij **Generate data** ponownie. Zwiększ **Max Tokens**, jeśli odpowiedź wygląda na ściętą. Jeśli **Create product** się nie udaje, sprawdź, czy szkic nie ma pustej nazwy.

### 5.15 Przywrócenie nie jest możliwe

- **Objaw:** **Error! This log entry has no previous value to restore.** lub **Error! Nothing to restore for this entry.**
- **Przyczyna:** ten wiersz nie zapisał wcześniejszej wartości (na przykład dowolny prompt lub pole, które było puste).
- **Co zrobić:** użyj innego wiersza tego samego produktu albo popraw tekst ręcznie.

### 5.16 Ekran informuje, że token jest nieprawidłowy

- **Objaw:** **Error! Invalid token!** po naciśnięciu przycisku po długiej przerwie.
- **Przyczyna:** strona panelu została otwarta, zanim wewnętrzny sekret modułu został odnowiony.
- **Co zrobić:** przeładuj stronę i spróbuj ponownie.

### 5.17 Tekst jest krótszy, niż oczekiwano

- **Przyczyna:** PrestaShop ogranicza niektóre pola. Moduł skraca nazwę do 128 znaków, krótki opis do 800, meta title do 69, a meta description do 159.
- **Co zrobić:** użyj bardziej zwięzłej instrukcji, na przykład prosząc o tytuł poniżej 60 znaków.

### 5.18 Log techniczny i debug

- **Objaw:** potrzebujesz więcej szczegółów o nieudanym wywołaniu albo log PrestaShop rośnie.
- **Co zrobić:** włącz **Debug mode** w **Settings**, **General**, powtórz czynność, przeczytaj nowe wpisy w **Advanced Parameters**, **Logs** i ponownie wyłącz debug. Po testach ustaw też **Enable Debug** na ekranie Cron z powrotem na **No**.

### 5.19 Powiadomienia o aktualizacjach

- **Objaw:** **Check Now** nie pokazuje **Module is up to date!** ani **New version available!**
- **Przyczyna:** Twój serwer nie może połączyć się z serwerem aktualizacji MyPresta.eu, który jest sprawdzany z krótkim limitem czasu.
- **Co zrobić:** zezwól na połączenia wychodzące albo spróbuj później. Moduł działa bez tego sprawdzania.

## 6. Dla programistów

### 6.1 Przegląd

- **Klasa główna:** `myaigrok` (plik `myaigrok.php`), rozszerza `Module`, wersja `1.1.0`, `bootstrap = true`, `need_instance = 0`.
- **Nazwa na liście modułów:** `My AI Grok - AI content generation`. **Autor:** `MyPresta.eu`. **Tab:** `front_office_features`.
- **Zgodność:** PrestaShop 1.6 do 9.99.99 (`ps_versions_compliancy`). Minimalne PHP 7.0.0 (`MIN_PHP_VERSION`); `install()` odrzuca starsze PHP przetłumaczonym komunikatem.
- **Klasy:** przestrzeń nazw `MyAIGrok\` jest ładowana przez `autoload.php` (bez Composera). `MyAIGrok\OpenAIService` to klient cURL dla `https://api.x.ai/v1` (`/chat/completions`, `/models`); `MyAIGrok\Studio` stosuje styl marki, miesięczny budżet i bramkę jakości. Moduł sprawdzania aktualizacji `myaigrokUpdate` (w `lib/updateChecker.php`) rozszerza `myaigrok`.
- **Przepływ danych:** ustawienia są w `ps_configuration` (prefiks `MYPRESTA_MYAIGROK_`). Przyciski panelu i uruchomienia masowe wywołują kontroler front `ajax`; harmonogramy wywołują kontroler front `cron`. Oba odczytują ustawienia, przepuszczają prompt przez `Studio::gate()` (sprawdzenie budżetu i `Studio::decorate()`), wysyłają go przez `OpenAIService::createChatCompletion()`, sprawdzają odpowiedź przez `Studio::inspect()`, zapisują tekst w obiekcie produktu lub kategorii i wstawiają wiersz do `myaigrok_log`.
- **Wywołania dostawcy:** wysyłane są parametry modelu `temperature`, `max_tokens`, `top_p`, `frequency_penalty`, `presence_penalty`; parametry odrzucane przez model są zapamiętywane i zapisywane w `MYPRESTA_MYAIGROK_MODEL_CAPS`. Weryfikacja certyfikatu jest wyłączana tylko wtedy, gdy sam sklep działa na localhost.

### 6.2 Pliki

| Ścieżka | Przeznaczenie |
|---|---|
| `myaigrok.php` | Klasa modułu: instalacja, odinstalowanie, hooki, ekrany Settings (HelperForm), Dashboard, umieszczenie menu, zakładka Modules produktu. |
| `autoload.php` | Loader klas dla przestrzeni nazw `MyAIGrok\`. |
| `src/OpenAIService.php` | Klient cURL dla Groka: chat completions, lista modeli, limity czasu, dostosowanie parametrów. |
| `src/Studio.php` | `gate()`, `decorate()`, `inspect()`, `overBudget()`, prompty pakietu SEO i tekstów alt. |
| `controllers/admin/AdminMyAIGrok.php` | Ekrany Generate (filtry produktów i kategorii, panele masowe). |
| `controllers/admin/AdminMyAIGrokProductCreator.php` | Ekran New product i jego akcje Ajax. |
| `controllers/admin/AdminMyAIGrokCron.php` | Formularze Cron. |
| `controllers/admin/AdminMyAIGrokUsage.php` | Raport i lista History. |
| `controllers/admin/AdminMyAIGrokImageFinder.php` | Ekran Images oraz akcje wyszukiwania i importu obrazów. |
| `controllers/admin/AdminMyAIGrokMain.php`, `AdminMyAIGrokSettings.php` | Przekierowanie na stronę konfiguracji modułu. |
| `controllers/front/ajax.php` | Punkt końcowy generowania używany przez panel administracyjny. |
| `controllers/front/cron.php` | Punkt końcowy cron. |
| `lib/sectionHelp.php` | Zawartość panelu bocznego Help. |
| `lib/updateChecker.php` | Sprawdzanie aktualizacji MyPresta.eu (`dev.mypresta.eu/update/get.php`; wysyła nazwę modułu, wersję, symbol zastępczy klucza licencji i adres sklepu). |
| `lib/prestashop9compatibility.php` | Funkcje zgodności (szyfrowanie tokenów dla PS 9). |
| `lib/searchTool/` | Mały pomocnik autouzupełniania ładowany na stronie konfiguracji. |
| `views/templates/hook/*.tpl` | Szablony hooków i ekranów (nav, subnav, dashboard, usage, generatory masowe, playground, zakładki produktu, panele cron). |
| `views/templates/admin/product_creator.tpl` | Ekran New product. |
| `views/js/back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `admin-help.js`, `dashboard.js`, `chart.min.js` | Skrypty panelu administracyjnego. |
| `views/css/back.css`, `admin-nav.css`, `stats.css` | Style panelu administracyjnego. |
| `translations/{iso}.php` | Pliki tłumaczeń (wiele języków). |

### 6.3 Kontrolery

| Kontroler | Rodzic i trasa | Uwagi |
|---|---|---|
| `AdminMyAIGrokMain` | Dziecko zakładki nadrzędnej Modules (`AdminParentModulesSf`, w przeciwnym razie `AdminParentModules`, w przeciwnym razie `AdminModules`), nazwa w menu **AI Content Generator** | Przekierowuje do `AdminModules&configure=myaigrok&mds_tab=dashboard`. |
| `AdminMyAIGrokSettings` | Ukryte dziecko (`active = 0`) kontrolera Main | Przekierowuje do `mds_tab=settings`. |
| `AdminMyAIGrok` | Ukryte dziecko kontrolera Main | `mds_sub=products` lub `categories`; akcje wysyłki `filterProducts`, `filterCategories`. |
| `AdminMyAIGrokProductCreator` | Ukryte dziecko kontrolera Main | Akcje Ajax `generateProductData`, `extractImages`, `createProduct`, `generateImages` (symbol zastępczy). |
| `AdminMyAIGrokCron` | Ukryte dziecko kontrolera Main | Wysyłka `submitCronUpdate`, `submitCatCronUpdate`. |
| `AdminMyAIGrokUsage` | Ukryte dziecko kontrolera Main | Filtry `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q`; `clear_log` usuwa wszystkie wiersze; akcja wiersza `view`. |
| `AdminMyAIGrokImageFinder` | Ukryte dziecko kontrolera Main | Akcje `searchImages`, `extractImages`, `saveImages`; hosty sieci prywatnych odrzucane; do 5 stron i 24 zdjęć. |

Uprawnienia to standardowe prawa zakładek panelu administracyjnego dla tych kontrolerów. Każdy kontroler administracyjny przekierowuje do `AdminHome`, gdy moduł jest wyłączony. `AdminModules` z `configure=myaigrok` przyjmuje `mds_tab` (`dashboard`, `settings`, `updates`), `mds_sub` (`general`, `openai`, `studio`, `templates`, `playground`; `openai` to zakładka Grok) oraz `mcg_preset` (`today`, `7`, `30`, `90`, `month`, `all`) a także `mds_from`, `mds_to`.

**Front `ajax`** (`module/myaigrok/ajax`): wymaga `secret_token` równego `MYPRESTA_MYAIGROK_TOKEN`, w przeciwnym razie `Error! Invalid token!`. Nie ma sprawdzenia pracownika; jedyną ochroną jest token na stronie. Akcje: `initiatePrompt`, `updateSettings` (zapisuje klucze próbkowania), `updateProduct`, `updateCategory`, `initiateProductRestore`, `generateSeoPack`, `generateAltTexts` (brak przycisku w interfejsie). `updateProduct` i `updateCategory` przyjmują wartości `behavior`: `replace`, `keep`, `keep_top`, `keep_end` oraz `single_product` / `single_category` (próba na sucho, nic nie jest zapisywane).

**Front `cron`** (`module/myaigrok/cron`): konstruktor wykonuje całą pracę. Kończy działanie z komunikatem, gdy `ENABLE_CRON` ma wartość 0, następnie wymaga `secret` równego `MYPRESTA_MYAIGROK_SECRET` albo `MYPRESTA_MYAIGROK_CAT_SECRET` (dla obu akcji akceptowany jest każdy z sekretów). `action` musi mieć wartość `generateProductContent` lub `generateCategoryContent`, w przeciwnym razie `Invalid action!`. Parametr `entity` widoczny w adresie kategorii na ekranie Cron nie jest odczytywany. Opcjonalne parametry nadpisują zapisane wybory: dla produktów `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`; dla kategorii `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug`. Dozwolone cele: `pendingGrok`, `pendingField`, `emptyField`; błędna wartość odpowiada `productTarget parameter is wrong! Allowed values: ...`, błędne pole `updatedField parameter is wrong!`. Warunek listy kategorii dla produktów jest dodawany jako `p.id_product IN (...) OR p.id_category_default IN (...)` bez nawiasów, więc łączy się z pozostałymi warunkami według pierwszeństwa operatorów SQL (zob. sekcja 5.10). Błędy cron są wypisywane (echo) i żądanie kończy działanie; nie są zapisywane w `myaigrok_log`.

Zasoby, do których są odwołania, ale nie dostarczone w paczce: `views/js/admin.js` i `views/css/admin.css` (kontrolery Main i Settings, nieosiągalne, bo wcześniej następuje przekierowanie) oraz `views/js/product_creator.js` i `views/css/product_creator.css` (ekran New product; ekran używa `back.js`). Funkcje `generateTokenAndFill()` i `generateCategoryTokenAndFill()` wywoływane przez przyciski **Generate Token** nie są zdefiniowane w żadnym dostarczonym skrypcie. Przyciski **Module settings** na formularzach filtrów Generate prowadzą do `configure=mychatgpt`.

### 6.4 Hooki

Rejestrowane w `install()`:

| Hook | Zachowanie |
|---|---|
| `displayAdminProductsExtra` | Renderuje blok My AI Grok (`product-tab-wrapper.tpl`) w zakładce Modules produktu. Nic nie zwraca, gdy zarówno `PRODUCT`, jak i `PRODUCT_LOG` mają wartość 0. |
| `displayBackOfficeHeader` | Wywołuje `ensureLongSecrets()` i `placeModuleMenu()`, dodaje CSS i JS, publikuje zmienne JS, jednorazowo rejestruje zakładkę Image Finder (`IMAGEFINDER_TAB_OK`), ładuje `product-fields.js` na stronach produktów i kategorii oraz skrypt przycisku na liście produktów. |
| `displayBackOfficeTop` | Publikuje `admin_controller_url` i identyfikatory edytowanej kategorii, strony CMS lub marki oraz zwraca generator z górnego paska, gdy `TOPCTA` ma wartość 1. |
| `dashboardZoneTwo` | Renderuje `dashboard.tpl`. Rejestrowany ponownie w `displayBackOfficeHeader`, jeśli go brakuje. |
| `displayHeader`, `displayFooter` | Zarejestrowane; metody są puste. |
| `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom`, `actionProductFormBuilderModifier` | Zarejestrowane; metody zwracają pusty ciąg lub nic. |

Moduł nie nadpisuje ani `enable()`, ani `disable()`. Wyłączenie modułu sprawia jedynie, że jego kontrolery administracyjne przekierowują do kokpitu PrestaShop. Metoda `hookActionProductGridDataModifier` istnieje, ale nie jest zarejestrowana. Moduł nie udostępnia własnych hooków.

### 6.5 Overrides

Moduł nie ma overrides.

### 6.6 Baza danych

| Tabela | Zawartość |
|---|---|
| `{prefix}myaigrok_prompt` | `id_prompt`, `status`, `title` (128), `prompt` (text), `date_generated`. Wypełniona 16 szablonami przy instalacji. |
| `{prefix}myaigrok_log` | `id_log`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, pary `old_` i `new_` dla name, description, description_short, meta_title, meta_description i tags, `date_updated`. Klucze na `id_product` i `status`. |

Trzy kolumny tokenów są dodawane przez `ensureUsageColumns()` przy pierwszym użyciu, gdy starsza tabela ich nie ma. Odinstalowanie usuwa obie tabele, wszystkie zakładki administracyjne (w tym dawną `AdminMyAIGrokChangelog`) i główne klucze konfiguracji. Wygenerowane teksty produktów i kategorii nie są ruszane.

### 6.7 Klucze i tłumaczenia

Wszystkie klucze zaczynają się od `MYPRESTA_MYAIGROK_`. Wartości po instalacji:

| Klucz | Wartość |
|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | 0, 0 |
| `TIMEOUT` | 120 (przycinane do 10–600 przy zapisie) |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT`, `IMAGEFINDER_ENABLE` | po 1 |
| `IMAGEFINDER_PROMPT` | Domyślny prompt prosi o 5 adresów URL stron jako tablicę JSON |
| `TOKEN`, `SECRET`, `CAT_SECRET` | Losowe 32 znaki; `ensureLongSecrets()` generuje ponownie każdy krótszy niż 24 znaki |
| `API_KEY`, `MODEL`, `EXTRA_MODELS`, `MODEL_CAPS` | pojedyncza spacja, `grok-4.7`, puste, puste |
| `TEMPERATURE`, `MAX_TOKENS`, `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 0.7, 3200, 1, 0, 0 |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | puste |
| `BUDGET`, `QUALITY` | 0, 1 |
| `ENABLE_CRON`, `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 0, 6, 6 |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList`, `categories` | `description`, `pendingGrok`, 5, puste, domyślny język sklepu, puste, 0, puste, puste |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug` | `description`, `pendingGrok`, 5, puste, domyślny język sklepu, 0 |
| `IMAGEFINDER_TAB_OK` | Ustawiany po pierwszym załadowaniu panelu administracyjnego |

Ekrany Generate zapisują też ostatnie wartości filtrów pod `MYPRESTA_MYAIGROK_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_IDS`, `_PROD_REF`, `_PROD_DATE_FROM`, `_PROD_DATE_TO`, `_PROD_MIN_ID`, `_PROD_MAX_ID`, `_PROD_LIMIT`, `_CATEGORIES`, `_BRANDS`. Odinstalowanie ich nie usuwa. Moduł sprawdzania aktualizacji używa `mypresta_updates`, `update_myaigrok` i `updatev_myaigrok`. Każde załadowanie strony konfiguracji w panelu usuwa przestarzałe klucze `GEMINI_API_KEY`, `GEMINI_MODEL` i `ACTIVE_SERVICE`.

**Tłumaczenia:** aby dodać język, utwórz `translations/{iso}.php`. Ciągi modułu używają `$this->l()` i `{l s='...' mod='myaigrok'}`. Kontrolery administracyjne używają `trans()` z domenami takimi jak `Admin.MyAIGrok` i `Admin.MyAIGrokCron` w PrestaShop 8 i 9 oraz `l()` modułu w 1.6 i 1.7. Te ciągi nie są tłumaczone: komunikaty budowane w `back.js` i zapasowe teksty `product-fields.js`, odpowiedzi tekstowe cron, teksty błędów Image Finder i New product oraz angielskie prompty budowane przez `Studio`. Opisy pól (What it does / How to configure / Effect) są budowane przez `fieldHelp()` w `myaigrok.php` i przez opakowanie `help()` w każdym kontrolerze administracyjnym; teksty generatora masowego i Playground znajdują się w szablonach; teksty panelu Help są w `lib/sectionHelp.php`.

### 6.8 Rozszerzanie

- Dodawaj lub edytuj szablony promptów w `myaigrok_prompt` (lub na ekranie Prompt templates); znaczniki są zastępowane w `ajax.php` i `cron.php`.
- Dodawaj identyfikatory modeli przez **Add a Grok model**; są przechowywane w `EXTRA_MODELS`.
- Kształtuj wynik regułami Studio; są stosowane w `Studio::decorate()`.
- Wywołuj punkt końcowy cron z nadpisaniami parametrów, aby uruchamiać różne zadania bez ruszania zapisanego formularza.
- Front office nie renderuje żadnego szablonu modułu, więc motyw nie ma czego nadpisywać.

## 7. Pomoc

Strona produktu modułu: https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-grok-ai.html

Aby skontaktować się z pomocą techniczną w sprawie modułu:

1. Zaloguj się na swoje konto klienta na mypresta.eu.
2. Przejdź do formularza kontaktowego.
3. Wybierz temat **Support for paid modules**.
4. Opisz, co zrobiłeś i co zobaczyłeś. Dodaj numer wersji widoczny obok nazwy modułu u góry jego ekranów oraz, jeśli generacja się nie udała, tekst błędu z kolumny **Reply / Error** w **History**.
