---
title: "My AI DeepSeek - AI content generation - dokumentacja i instrukcja obsługi"
description: "Instrukcja konfiguracji, codziennej pracy i rozwiązywania problemów dla właścicieli sklepów, którzy mają już zainstalowany moduł My AI DeepSeek w PrestaShop."
sidebar:
  label: "My AI DeepSeek - AI content generation - dokumentacja i instrukcja obsługi"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł SEO meta and catalog descriptions with DeepSeek AI na MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-deepseek-ai.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ai-artificial-intelligence/seo-meta-and-catalog-descriptions-with-deepseek-ai/)
>
> ---


## 1. Wymagania

Moduł pisze teksty katalogowe za pośrednictwem usługi DeepSeek, dlatego Twój sklep potrzebuje działającego połączenia z DeepSeek oraz własnego konta DeepSeek.

- **PrestaShop:** wersje od 1.6 do 9.99.99.
- **PHP:** 7.0 lub nowszy. Na starszej wersji PHP instalacja zostaje odrzucona z komunikatem, który podaje wymaganą i wykrytą wersję.
- **Rozszerzenie PHP:** cURL. Serwer sklepu musi móc otwierać wychodzące połączenia HTTPS do `https://api.deepseek.com/v1`. Jeśli Twój hosting blokuje połączenia wychodzące, poproś hosting o ich odblokowanie.
- **Inne moduły:** brak. Moduł nie zależy od żadnego innego modułu.
- **Konto DeepSeek:** potrzebujesz klucza API. Utworzysz go na https://platform.deepseek.com/api_keys. Zużycie rozlicza DeepSeek z Twoim kontem, a nie MyPresta.eu.
- **Język panelu administracyjnego:** w tej instrukcji ekrany są pokazane po angielsku, a zrzuty ekranu pochodzą z angielskiego panelu administracyjnego. Nazwy pogrubione to nazwy, które widzisz na ekranie.
- **Duże katalogi:** każde generowane pole to jedno zapytanie do DeepSeek i trwa kilka sekund. Uruchomienie dla setek produktów trwa długo, a na ekranach Generate karta przeglądarki musi pozostać otwarta przez cały czas pracy. Przy dużych katalogach wybierz ekran Cron, który pracuje w tle małymi partiami.

## 2. Instalacja

### 2.1 Wgranie i instalacja

1. Otwórz **Modules**, a następnie **Module Manager**.
2. Kliknij **Upload a module** i wybierz plik ZIP. Nie rozpakowuj go wcześniej.
3. Gdy wgrywanie się zakończy, kliknij **Install** (jeśli przycisk jest widoczny), a potem **Configure**.

Instalacja zapisuje ustawienia domyślne, tworzy tabele modułu, dodaje 16 gotowych szablonów promptów i dodaje moduł do menu panelu administracyjnego.

### 2.2 Co pojawia się w menu

Dodawana jest nowa pozycja menu **AI Content Generator**. Jej pierwszą stroną jest **Dashboard**. Wewnątrz modułu przechodzisz między ekranami za pomocą paska nawigacji u góry każdej strony:

| Element nawigacji | Co otwiera |
|---|---|
| **Dashboard** | Wykresy zapytań, błędów i tokenów. |
| **Settings** | Pięć sekcji: **General**, **DeepSeek**, **Studio**, **Prompt templates**, **Playground**. |
| **Generate** | Dwie listy: **Products** i **Categories**. |
| **New product** | Tworzy szkic produktu na podstawie krótkiego opisu. |
| **Cron** | Buduje adresy zadań cyklicznych dla produktów i kategorii. |
| **History** | Każde zapytanie z jego promptem, odpowiedzią, statusem i tokenami. |
| **Images** | Przełącznik i prompt wyszukiwarki zdjęć produktów. |
| **Updates** | Sprawdza, czy opublikowano nowszą wersję. |

Po najechaniu na element nawigacji pojawia się krótka podpowiedź w formie What it does / How to configure / Effect.

### 2.3 Pamięć podręczna

Instalacja nie czyści pamięci podręcznej PrestaShop. Jeśli po pierwszej instalacji w menu brakuje pozycji **AI Content Generator**, wyczyść pamięć podręczną w **Advanced Parameters**, **Performance** i przeładuj panel administracyjny.

### 2.4 Odinstalowanie i ponowna instalacja

- **Usuwane:** pozycja menu, lista szablonów promptów, tabela History ze wszystkimi wierszami oraz główne ustawienia modułu, w tym klucz API.
- **Zachowywane:** każdy tekst już zapisany w produktach i kategoriach. Moduł nigdy nie usuwa tekstów katalogowych.
- **Możliwe pozostałości:** kilka zapisanych wartości filtrów ekranów Generate może pozostać w konfiguracji sklepu. Nie szkodzą one w niczym.
- **Ponowna instalacja:** nowa instalacja startuje od ustawień domyślnych. Szablony promptów, History i klucz API znikają, dlatego przed odinstalowaniem zapisz własne szablony i reguły Studio.

## 3. Konfiguracja i codzienna praca w panelu administracyjnym

### 3.1 Cały proces w skrócie

Moduł nie ma żadnych kroków po stronie klienta. Twoi pracownicy rozpoczynają każdą akcję w panelu administracyjnym.

1. **Jednorazowo:** wklej klucz API DeepSeek i wybierz model w **Settings**, **DeepSeek**. Opcjonalnie uzupełnij **Studio** (głos marki, zakazane słowa, limit miesięczny).
2. **Pojedynczy produkt:** otwórz produkt, przejdź do zakładki **Modules**, **My AI DeepSeek**. Użyj **Generate**, aby napisać pola, **Simulate**, aby najpierw spróbować, **Photos**, aby znaleźć zdjęcia, oraz **History**, aby przywrócić starszy tekst.
3. **Wiele produktów lub kategorii:** otwórz **Generate**, przefiltruj listę, wybierz prompt i zakres, a następnie naciśnij **Run**. Każdy wiersz pokazuje własny wynik, gdy skończy pracę.
4. **Bez nadzoru:** otwórz **Cron**, zapisz definicję partii, skopiuj adres i przekaż go harmonogramowi zadań na serwerze.
5. **Kontrola:** **History** pokazuje każde zapytanie. **Dashboard** pokazuje sumy. Nic nie ginie: poprzedni tekst każdego zapisanego pola jest zachowany i można go przywrócić przyciskiem **Restore** na produkcie.
6. **Nowy produkt z pomysłu:** **New product** tworzy szkic, a po jego zaakceptowaniu prawdziwy produkt.

Każde zapytanie jest zapisywane w **History** ze statusem **Success** lub **Error**. Odpowiedź, która łamie listę **Forbidden words** albo przychodzi po wyczerpaniu **Monthly generation budget**, nie jest zapisywana w produkcie.

![Dashboard](https://mypresta.eu/docs/images/docs/myaideepseek-dashboard.webp)

### 3.2 Dashboard

Otwórz **AI Content Generator**, a następnie **Dashboard**. Strona przedstawia na wykresach zapytania do DeepSeek, tokeny i błędy zapisane w **History** dla wybranego zakresu. Z tej strony nic w katalogu nie jest generowane ani zmieniane.

| Element | Wartość początkowa | Co robi |
|---|---|---|
| **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time** | moduł otwiera się z domyślnym zakresem | Szybkie zakresy dat. Kliknij jeden, aby odświeżyć stronę. |
| **From** / **To** i **Apply** | puste | Twój własny zakres. Karty i wykresy go uwzględniają. |
| Wiersz **Active service** | – | Pokazuje, z jakiej usługi korzysta moduł. |
| Karty **Requests**, **Errors**, **Tokens sent**, **Tokens received** | – | Liczba zapisanych wywołań, nieudanych wywołań, rozmiar promptów i rozmiar odpowiedzi w obrębie zakresu. |
| Wykresy **Requests and errors**, **Tokens sent and received**, **Requests by model** | – | Krzywe dzień po dniu oraz podział według modeli. |

Strona pojawia się także jako mały blok na standardowym **Dashboard** PrestaShop z szybkimi odnośnikami do **Generate**, **History** i **Cron**.

### 3.3 Settings – General

Otwórz **Settings**, a następnie **General**. Te przełączniki decydują, jak długo może trwać wywołanie i jakie narzędzia widzą pracownicy. Zapis w tym miejscu nie zmienia żadnego tekstu produktu.

![Settings – General](https://mypresta.eu/docs/images/docs/myaideepseek-settings-general.webp)

| Pole | Wartość początkowa | Co robi |
|---|---|---|
| **Live mode** | Disabled | Oznacza, że moduł działa w prawdziwym sklepie, a nie w konfiguracji testowej. Włącz go w sklepie produkcyjnym. W kopii testowej (staging) zostaw wyłączony, jeśli nie chcesz, aby pracownicy traktowali narzędzia jako gotowe. Narzędzia działają tak samo w obu stanach. |
| **Debug mode** | Disabled | Zapisuje dodatkowe szczegóły diagnostyczne, gdy wywołanie DeepSeek się nie powiedzie. Włącz go tylko na czas badania błędu, a potem wyłącz. Komunikaty techniczne trafiają do logu PrestaShop. Klienci nigdy ich nie widzą. |
| **API timeout (seconds)** | 120 | Ile sekund jedno wywołanie DeepSeek może trwać, zanim moduł się podda. Dla zwykłych opisów użyj 120. Zwiększ w stronę 600 dla długich pakietów SEO lub modelu rozumującego. Nie schodź poniżej 10. Krótki limit czasu kończy się szybko i zapisuje błąd w History. Długi limit czeka na wolną odpowiedź. |
| **Product Edit History** | Enabled | Pokazuje poprzednie zapisy AI na stronie produktu, aby redaktor mógł przywrócić starą wartość. Wyłączone ukrywa tę listę. Dawne wiersze i tak zostają w **History**. |
| **Admin Top Bar CTA** | Enabled | Dodaje skrót w górnym pasku panelu administracyjnego, który otwiera generator na każdej stronie. Wyłączone usuwa tylko ten przycisk. Menu modułu zostaje. |
| **Product edit page Form** | Enabled | Pokazuje panel generatora i przyciski Generate with AI na stronie edycji produktu (PrestaShop 1.7, 8 i 9). Wyłącz, jeśli mają być używane tylko generowanie masowe i cron. |
| **AI Image Finder** | Enabled | Pozwala redaktorowi poprosić model o strony, które prawdopodobnie zawierają zdjęcia bieżącego produktu. Nic nie jest pobierane, dopóki ktoś nie potwierdzi obrazu. Wyłączone ukrywa wyszukiwanie, a zakładka **Photos** wyjaśnia wtedy, jak je włączyć. |
| **AI Image Search Prompt** | gotowa instrukcja po angielsku | Instrukcja wysyłana, gdy ktoś wyszukuje obrazy produktu. Nazwa produktu i opis produktu są uzupełniane dla bieżącego produktu. Zachowaj prośbę o listę adresów stron. Dokładniejszy prompt daje trafniejsze strony. |

Naciśnij **Save**. Pojawi się zielone potwierdzenie. Te same dwa pola obrazów istnieją w **Images**.

### 3.4 Settings – DeepSeek

Otwórz **Settings**, a następnie **DeepSeek**. To jest konto i próbkowanie używane przez każde generowanie: przyciski w produkcie, uruchomienia masowe, cron i playground.

![Settings – DeepSeek](https://mypresta.eu/docs/images/docs/myaideepseek-settings-deepseek.webp)

| Pole | Wartość początkowa | Co robi |
|---|---|---|
| **DeepSeek API KEY** | puste | Sekret, który pozwala temu sklepowi wywoływać Twoje konto DeepSeek. Wklej klucz z https://platform.deepseek.com/api_keys. Spacje są usuwane przy zapisie (zobaczysz informację, że klucz został oczyszczony). Pozostaw pole nietknięte, aby zachować zapisany klucz. Pusty lub błędny klucz powoduje, że wywołania kończą się niepowodzeniem, a błąd trafia do History. |
| **Model** | `deepseek-chat` | Model, który pisze tekst. Modele wbudowane: `deepseek-chat` (szybki, normalny wybór) i `deepseek-reasoner` (model rozumujący, wolniejszy). Pokazywane są także modele dodane przez Ciebie. Następne generowanie używa wybranego modelu. Model, którego Twój klucz nie może użyć, zwraca błąd API zamiast tekstu. |
| **Add a DeepSeek model** | pusty wiersz | Wpisz identyfikator modelu i naciśnij przycisk dodawania w tym wierszu. Zobaczysz **Model added.** Modeli wbudowanych nie można usunąć (**Built-in models cannot be removed.**). Model, który jest już wbudowany, odpowiada **That model is already built in.** Modele dodane przez Ciebie można usunąć z tego samego wiersza (**Model removed.**). |
| **Max Tokens** | 3200 | Górny limit długości odpowiedzi, liczony w tokenach, a nie w słowach. Użyj około 256 dla meta description i 1000 lub więcej dla pełnego opisu HTML. Niski limit ucina odpowiedź. Wysoki limit pozwala na dłuższy tekst i kosztuje więcej. W `deepseek-reasoner` część limitu jest zużywana na rozumowanie, więc ustaw większą wartość. |
| **Temperature** | 0.7 | Jak swobodnie model dobiera słowa. Trzymaj się zakresu od 0 do 1. Użyj około 0.2 dla specyfikacji i tekstów meta oraz około 0.7 dla opisów. Zmieniaj Temperature albo Top P, nie oba naraz. |
| **Top P** | 1 | Inny sposób ograniczania, jak zaskakujące może być następne słowo. Zostaw 1, jeśli ustawiono już Temperature. Niższa wartość, np. 0.9, daje węższe słownictwo. |
| **Frequency Penalty Value** | 0 | Ogranicza wiersze powtarzające tę samą frazę w jednej odpowiedzi. Spróbuj 0.3 do 0.6 tylko wtedy, gdy opisy ciągle kopiują jedno zdanie. Zakres –2 do 2. |
| **Presence Penalty Value** | 0 | Popycha odpowiedź ku nowym tematom. Domyślnie używaj 0. Mała liczba dodatnia pomaga, gdy każdy akapit powtarza tę samą myśl. Zakres –2 do 2. |

Naciśnij **Save**. Pola próbkowania nie zmieniają tego, które produkty są aktualizowane.

> Model rozumujący może ignorować Temperature, Top P i dwie kary. Jeśli zmiana tych pól nie daje widocznego efektu z `deepseek-reasoner`, przełącz się na `deepseek-chat`.

### 3.5 Settings – Studio

Otwórz **Settings**, a następnie **Studio**. Studio dodaje Twoje wewnętrzne zasady do każdego promptu: przycisków w produkcie, uruchomień masowych i crona. Puste pola są pomijane. Tekst już zapisany w katalogu nie jest przepisywany po zmianie reguły.

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaideepseek-settings-studio.webp)

| Pole | Wartość początkowa | Co robi |
|---|---|---|
| **Brand voice** | puste | Mówi modelowi, kto przemawia, aby tekst produktu pasował do Twojego sklepu, a nie do ogólnego asystenta. Napisz krótki opis, na przykład: wyspecjalizowany warsztat, krótkie zdania, bez przesadnych haseł. |
| **Audience** | puste | Wskazuje czytelnika, dla którego pisany jest tekst, na przykład profesjonalnych monterów lub kupujących po raz pierwszy. |
| **Tone** | puste | Ustawia nastrój: formalny, ciepły, techniczny i tak dalej. Wystarczy jedno lub dwa słowa. Nie zmienia modelu ani temperatury. |
| **Glossary** | puste | Nazwy marek, materiały i pisownie, które model musi skopiować dokładnie. Jeden termin w wierszu. Terminy spoza listy mogą nadal zostać sparafrazowane. |
| **Forbidden words** | puste | Słowa i frazy, które nie mogą pojawić się w zapisanej odpowiedzi. Jedno w wierszu. Używane tylko wtedy, gdy **Quality gate** jest włączone. Odpowiedź zawierająca wpis z listy jest odrzucana i nie jest zapisywana w produkcie. Próba pozostaje w History jako błąd. |
| **Monthly generation budget** | 0 | Ogranicza liczbę udanych generowań, które sklep może wykonać w bieżącym miesiącu kalendarzowym. Wpisz liczbę całkowitą. 0 oznacza brak limitu. Licznik zaczyna od nowa pierwszego dnia miesiąca. Po osiągnięciu limitu zobaczysz **Monthly generation budget reached. Raise it in the studio settings or wait until next month.** Nieudane wywołania nie są liczone. |
| **Quality gate** | Enabled | Sprawdza odpowiedź modelu pod kątem **Forbidden words**, zanim cokolwiek zostanie zapisane. Włączone blokuje pasującą odpowiedź. Wyłączone zapisuje ją, nawet jeśli zawiera słowo z listy. |

Naciśnij **Save studio**. Zobaczysz **Studio settings saved.**

### 3.6 Settings – Prompt templates

Otwórz **Settings**, a następnie **Prompt templates**. Szablon to zapisana instrukcja. Redaktorzy wybierają go zamiast pisać ten sam opis od nowa. Na stronie produktu, w generowaniu masowym i w cronie oferowane są tylko włączone szablony.

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaideepseek-settings-templates.webp)

Instalacja dodaje **16 szablonów**: Product name 1 i 2; Product description 1 do 7 (numer 7 korzysta ze zdjęć produktu); Product meta title 1 do 3; Product meta description 1 do 3; Product tags.

**Kolumny listy:** ID, **Title**, **Prompt**, **Status** (kliknij ptaszek, aby przełączyć Enabled/Disabled), **Timestamp**. Akcje w wierszu: **Edit** i **Delete**. Akcja zbiorcza: **Delete** dla zaznaczonych wierszy (potwierdzenie: *Are you sure you want to delete the selected prompts?*).

Użyj przycisku **+** w nagłówku listy, aby utworzyć szablon. Formularz **Generate Prompt Template** zawiera następujące pola:

| Pole | Wartość początkowa | Co robi |
|---|---|---|
| **Status** | przełącznik Enabled / Disabled | Pokazuje lub ukrywa szablon na listach używanych na stronie produktu, w generowaniu masowym i w cronie. Zamiast usuwać wersję roboczą, wyłącz ją. |
| **Prompt title** | puste (wymagane) | Nazwa, którą redaktorzy widzą na liście szablonów, na przykład HTML description with features. Nie jest wysyłana do modelu. |
| **Prompt content** | puste (wymagane) | Instrukcja wysyłana do modelu. Napisz ją tak, jakbyś zlecał zadanie copywriterowi, i wspomnij o długości, HTML oraz języku, jeśli mają znaczenie. Możesz użyć zmiennych `{product_name}`, `{product_brand}`, `{product_features}` i `{product_tags}`. Są one zastępowane produktem, dla którego generujesz tekst. |

Naciśnij **Save Prompt**. Komunikaty: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.** Jeśli formularz jest niekompletny, zobaczysz **Failed to edit prompt template! Please fill the form with the right informations!** Przycisk **Go Back to Module Settings** wraca do listy.

Szablony kategorii pisz bez zmiennych produktowych. Ekrany kategorii ich nie wstawiają.

### 3.7 Settings – Playground

Otwórz **Settings**, a następnie **Playground**. To brudnopis, który wywołuje aktywny model i wypisuje odpowiedź pod przyciskiem. Żaden produkt, kategoria ani pole meta nie jest zmieniane.

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaideepseek-settings-playground.webp)

| Pole | Wartość początkowa | Co robi |
|---|---|---|
| Duże pole tekstowe (**Ask the model anything about your catalog**) | puste | Instrukcja dla tego jednego wywołania. Napisz ją zwykłym językiem. Możesz wspomnieć nazwę sklepu, adres sklepu, nazwę produktu, referencję lub cechy produktu, jeśli chcesz, aby odpowiedź opierała się na danych katalogu. Dodawane są także Twoje reguły Studio. |
| **Generate** | – | Wysyła instrukcję. Odpowiedź pojawia się pod przyciskiem. |

### 3.8 Generate – Products

Otwórz **Generate**, a następnie **Products**. To ekran dwuetapowy. Pierwszy krok tylko buduje listę. Nic nie jest wysyłane do DeepSeek, dopóki nie naciśniesz **Run** w drugim kroku.

![Generate – Products](https://mypresta.eu/docs/images/docs/myaideepseek-generate-products.webp)

**Krok 1 – Filter products to update.** Filtry nie są zapisywane jako ustawienia sklepu. Puste filtry nie zawężają listy.

| Pole | Wartość początkowa | Co robi |
|---|---|---|
| **Product Categories** | nic nie zaznaczono | Zachowuje produkty z zaznaczonych kategorii. Puste drzewo wyłącza ten filtr. |
| **Brand** | pierwsza (pusta) opcja | Zachowuje produkty jednego producenta. |
| **Product status** | – | **Active** (w sprzedaży), **Disabled** (szkice) lub **Both**. |
| **Product stock** | – | **Only in stock products** usuwa produkty bez ilości. **All products** ignoruje stan magazynowy. |
| **Update only** | – | Korzysta z historii generowania: produkty nigdy niepisane przez ten moduł, produkty już zapisane lub **Update all**. Użyj opcji "not yet updated" przy pierwszym przejściu, a "already updated", aby przepisać. |
| **Product IDs** | puste | Numery produktów oddzielone przecinkami, na przykład 12,45,103. |
| **Product Reference** | puste | Jeden lub więcej kodów referencyjnych oddzielonych przecinkami. |
| **Product Add Date From** / **Product Add Date To** | puste | Zakres dat utworzenia. Puste oznacza brak ograniczenia po tej stronie. |
| **Minimum product ID** / **Maximum product ID** | puste | Najniższy i najwyższy numer produktu do uwzględnienia. |
| **Product Limit** | puste | Ogranicza liczbę produktów ładowanych do listy. W dużym katalogu użyj małej liczby, np. 20, aby jedno uruchomienie nie przeszło przypadkiem przez cały katalog. |

Naciśnij **Go to next step**. Przycisk **Module settings** wraca do ustawień modułu.

**Krok 2 – Run.** Zobaczysz **Mass product generation** z tabelą przefiltrowanych produktów (kolumny **ID**, **Reference**, **Result**).

| Pole | Wartość początkowa | Co robi |
|---|---|---|
| **Template** | **Choose a template** | Wypełnia pole promptu z włączonego szablonu. Zostaw pierwszą opcję i wpisz własny prompt, jeśli wolisz. Sam tytuł nie jest wysyłany. |
| Pole promptu | puste | Tekst wysyłany dla każdego wiersza. Zmienne produktowe są zastępowane w każdym wierszu. |
| **What to generate** | **Descriptions** | **Descriptions** pisze opis długi i krótki. **Meta title and meta description** pisze oba pola meta. **Descriptions and meta together** pisze wszystkie cztery. Każde pole to osobne zapytanie. Pozostałe pola zostają bez zmian. |
| **Existing text** | **Replace** | **Replace** nadpisuje. **Skip if filled** zachowuje wypełnione pola i nie wywołuje dla nich DeepSeek. **Add above** i **Add below** zachowują stary tekst i dołączają nowy. |
| **Languages** | język Twojego panelu administracyjnego, zaznaczony | Zaznacz każdy język, który chcesz. Niezaznaczone języki zachowują swój tekst. Każdy zaznaczony język jest generowany osobno. |
| **Run on the list below** | – | Rozpoczyna uruchomienie. Każdy wiersz pokazuje wynik, gdy tylko dany produkt się zakończy. Produkty spoza filtra pozostają nietknięte. |

Zostaw kartę przeglądarki otwartą, dopóki każdy wiersz nie pokaże wyniku. Nieudany wiersz pokazuje przyczynę; pozostałe wiersze są kontynuowane.

### 3.9 Generate – Categories

Otwórz **Generate**, a następnie **Categories**. Działa jak ekran produktów, z mniejszą liczbą filtrów.

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaideepseek-generate-categories.webp)

**Krok 1 – Filter categories to update.**

| Pole | Wartość początkowa | Co robi |
|---|---|---|
| **Categories** | nic nie zaznaczono | Kategorie oferowane na liście. Zostaw drzewo puste, aby uwzględnić każdą kategorię pasującą do statusu. |
| **Category status** | – | **Active**, **Disabled** lub **Both**. |

Naciśnij **Go to next step**.

**Krok 2 – Mass category generation.**

| Pole | Wartość początkowa | Co robi |
|---|---|---|
| Pole promptu | puste | Instrukcja wysyłana dla każdej kategorii. Opisz ton, długość i HTML. Zmienne produktowe nie są tu dostępne. |
| Wybór pola | **Description** | Jedno pole, które zapisuje to uruchomienie: **Description**, **Name**, **Meta title**, **Meta description** lub **Additional description**. |
| Existing data | **Replace** | **Replace** nadpisuje. **Skip if filled** chroni wypełnione pola i nie wywołuje DeepSeek dla tej kategorii. |
| **Language** | język Twojego panelu administracyjnego | Jeden język na uruchomienie. Uruchom ponownie dla innego języka. |
| **Run on the categories below** | – | Rozpoczyna uruchomienie. Tabela pokazuje **ID** i **Result** dla każdej kategorii. |

### 3.10 New product

Otwórz **New product**. Zamienia krótki opis w szkic produktu i może wstawić ten produkt do katalogu.

![New product](https://mypresta.eu/docs/images/docs/myaideepseek-new-product.webp)

| Pole | Wartość początkowa | Co robi |
|---|---|---|
| **What is the product?** | puste | Opis, który model rozwija w nazwę, opisy, pola meta, tagi, cechy, referencję i cenę. Kilka zdań z materiałami, odbiorcami i nazwami do zachowania daje bliższy szkic. Puste pole jest odrzucane. |
| **Optional source URL** | puste | Publiczna strona (http lub https) opisująca produkt. Jej tekst jest dodawany jako kontekst. Puste pole lub strona, której sklep nie może odczytać, są ignorowane. |
| **Language** | język Twojego panelu administracyjnego | Język, w którym zapisywane są nazwa, opisy, meta i tagi. Pozostałe języki nie są tu wypełniane. |
| **Default category ID** | 2 | Numer kategorii z **Catalog**, **Categories**. 2 to zwykle Home. Nowy produkt jest tam umieszczany. |
| **Generate data** | – | Pokazuje szkic jako tekst. Żaden produkt nie jest zapisywany. |
| **Create product** | – | Dodaje **aktywny** produkt w tym języku i tej kategorii z nazwą, opisami, meta, tagami, cechami, ceną i ilością magazynową ze szkicu. |

Jeśli nie zapisano klucza, zobaczysz **Add an API key in the module settings first.** Przejrzyj szkic, cenę i stan magazynowy, zanim zaczniesz sprzedawać: szkic pisze model.

### 3.11 Cron

Otwórz **Cron**. Strona buduje adresy, które wywołuje harmonogram zadań serwera. Każde wywołanie wypełnia **jedną partię** i kończy pracę. Sklep nic nie robi, dopóki Twój serwer nie zażąda adresu.

![Cron](https://mypresta.eu/docs/images/docs/myaideepseek-cron.webp)

Strona ma dwa formularze: **CRON JOB Settings – Generate product content using DeepSeek** oraz odpowiadający mu formularz dla kategorii. Możesz tworzyć nieograniczoną liczbę wariantów poleceń, po jednym na pole.

**Formularz crona dla produktów**

| Pole | Wartość początkowa | Co robi |
|---|---|---|
| **Enable Cron Feature** | No | Jeden przełącznik dla całego sklepu (produkty i kategorie). Włącz go dopiero po zapisaniu sekretu, pola, języka i promptu poniżej. Serwer nadal musi wywołać adres. |
| **Cron Job Secret Token** | wygenerowany | Długie hasło, które musi być częścią adresu produktów. Bez niego sklep odrzuca wywołanie. Zachowaj wartość pokazaną po instalacji. Jeśli ją zmienisz, od razu skopiuj nowy adres do harmonogramu serwera. Przycisk **Generate Token** w formularzu może nie wypełnić nowej wartości; jeśli potrzebujesz zmienić token, wpisz sam długi losowy ciąg znaków. |
| **Update Field** | description | Jedno pole produktu, które to polecenie przepisuje: name, description, short description, meta title, meta description lub tags. Aby wypełnić kilka pól, utwórz kilka poleceń. |
| **Selected Products** | pendingDeepSeek | Które produkty jeszcze czekają. **pendingDeepSeek**: produkty nigdy nieedytowane przez ten moduł (żadne pole). **pendingField**: produkty, dla których to pole nie zostało jeszcze wygenerowane, przy kilku poleceniach dla tych samych produktów. **emptyField**: tylko produkty, których pole jest puste. |
| **Product Categories** | nic nie zaznaczono | Ogranicza uruchomienie do zaznaczonych kategorii. Puste oznacza, że kategoria nie jest filtrem. |
| **Product ID list** | puste | Tylko te numery produktów, oddzielone przecinkami. Litery są usuwane przy zapisie. |
| **Language** | domyślny język sklepu | Jeden język na polecenie. Inne języki wymagają własnego polecenia. |
| **Product to update** | 5 products | Rozmiar partii na wywołanie, od 2 do 1000. Zacznij od 5 lub 10, aby wolny model nie przekroczył limitu czasu serwera. |
| **Prompt Template** | none | Włączony szablon. Każdy produkt w uruchomieniu jest pisany na podstawie tego opisu. |
| **Enable Debug** | No | **Yes** wypisuje plan po otwarciu adresu w przeglądarce i niczego nie zapisuje. Ustaw **No**, zanim użyje go harmonogram. |
| **CRON JOB interval** | Every Hour | Tylko sugestia używana do zbudowania tekstu polecenia (od **Every 1 Minute** do **Every 6 Hours**). Moduł nie uruchamia harmonogramu. |
| **Product Cron Job command** | – | Gotowe polecenie do skopiowania. Najpierw zapisz formularz. |

**Formularz crona dla kategorii** ma własne **Cron Job Secret Token**, **Update Field** (name, description, meta title, meta description), **Selected categories** (te same trzy reguły), **Language**, **Categories to update** (rozmiar partii), **Prompt Template** (napisz opis dla kategorii), **Enable Debug**, **CRON JOB interval** i **Category Cron Job command**. Wartości domyślne: description, pendingDeepSeek, 5 categories, Every Hour.

**Uzupełnij adres.** Adres pokazany na stronie może być niekompletny. Zawsze sprawdź, czy końcowy adres zawiera akcję. Użyj tego schematu, zastępując zmienne:

```text
https://YOUR-SHOP-DOMAIN/module/myaideepseek/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent&updatedField=description&productTarget=pendingDeepSeek&productsToUpdate=5&languageId=1&promptTemplateId=TEMPLATE_ID
https://YOUR-SHOP-DOMAIN/module/myaideepseek/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent&updatedField=description&categoryTarget=pendingDeepSeek&categoriesToUpdate=5&languageId=1&promptTemplateId=TEMPLATE_ID
```

Użyj `&action=generateProductContent` dla produktów i `&action=generateCategoryContent` dla kategorii. Bez tego wywołanie nic nie robi. Jeśli Twój sklep nie używa przyjaznych adresów URL, skopiuj adres bazowy ze strony i dołącz części za pomocą `&`. Nie publikuj tych adresów: zawarty w nich sekret jest jedyną ochroną.

Zalecany pierwszy test: ustaw **Enable Debug** na **Yes**, otwórz adres w przeglądarce i przeczytaj plan. Potem ustaw na **No**, zaplanuj adres w harmonogramie i po pierwszym wywołaniu sprawdź **History**.

### 3.12 History

Otwórz **History**. Wyświetla każdy prompt, odpowiedź, status i liczbę tokenów. Strona jest raportem: filtrowanie nie usuwa wierszy i nie zmienia produktów.

![History](https://mypresta.eu/docs/images/docs/myaideepseek-history.webp)

| Element | Co robi |
|---|---|
| **7 days**, **30 days**, **This month**, **All time** | Gotowe zakresy dat. |
| **From** / **To** | Własny zakres dat. |
| **Model**, **Type**, **Status** (**Success** lub **Error**), **Language**, **Employee** | Zawężają stronę do jednego wycinka. |
| **Product / category ID** | Tylko zapytania dotyczące tego elementu. |
| **Prompt or reply contains** | Słowo, które musi pojawić się w prompcie lub odpowiedzi. |
| **Filter** | Stosuje filtry. |
| Karty **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time** | Sumy dla przefiltrowanych wierszy. Myślnik oznacza, że DeepSeek nie zwrócił liczby tokenów dla tego wywołania. |
| Grupy **By day**, **By model**, **By type**, **By language**, **By employee** | Tabele z podziałem. |
| Kolumny listy **Status**, **Prompt**, **Reply / Error**, **Provider**, **Received**, **Entity ID**, **Timestamp** | Jeden wiersz na zapytanie. Otwórz wiersz, aby przeczytać pełny prompt, odpowiedź i tokeny. **Back to the list** wraca do listy. |
| **Clear list** | Usuwa wiersze historii. Zobaczysz **Log list successfully deleted.** Punkty **Restore** na stronie produktu znikają razem z nimi. Tekst katalogowy nie jest zmieniany. |

### 3.13 Images

Otwórz **Images**. Zapisuje przełącznik i instrukcję wyszukiwarki zdjęć produktów. Otwarcie tej strony niczego nie pobiera.

![Images](https://mypresta.eu/docs/images/docs/myaideepseek-images.webp)

| Pole | Wartość początkowa | Co robi |
|---|---|---|
| **AI Image Finder** | Enabled | Pokazuje lub ukrywa wyszukiwarkę zdjęć na stronie edycji produktu. Obraz jest importowany dopiero po potwierdzeniu przez kogoś. |
| **AI Image Search Prompt** | gotowa instrukcja po angielsku | Instrukcja wysyłana podczas wyszukiwania. Nazwa produktu i krótki opis są uzupełniane. Zachowaj prośbę o zwykłą listę adresów stron. |

Naciśnij **Save**. To te same dwa ustawienia co w **Settings**, **General**.

### 3.14 Updates

Otwórz **Updates**. Pyta MyPresta.eu, czy opublikowano nowsze wydanie tego modułu.

![Updates](https://mypresta.eu/docs/images/docs/myaideepseek-updates.webp)

| Element | Wartość początkowa | Co robi |
|---|---|---|
| **Automatic Notifications** | zgodnie z zapisanym ustawieniem | Pozwala panelowi administracyjnemu ostrzegać Cię, gdy istnieje nowsza wersja. |
| **Check Now** | – | Pyta jednorazowo, natychmiast. Strona informuje potem, że ta kopia jest aktualna lub że istnieje nowsza wersja. |
| Odnośnik do strony modułu | – | Otwiera stronę modułu w MyPresta.eu. |

Ta strona nie dotyka Twojego katalogu ani wygenerowanych tekstów.

### 3.15 Strona edycji produktu

Otwórz **Catalog**, a następnie **Products**, edytuj produkt i otwórz zakładkę **Modules**, a potem **My AI DeepSeek**. W zależności od wersji PrestaShop i ustawień **General** możesz też zobaczyć małe przyciski **Generate with AI** obok opisu, krótkiego opisu i pól meta.

![Product edit](https://mypresta.eu/docs/images/docs/myaideepseek-product-edit.webp)

Zakładka ma cztery części: **Generate**, **Simulate**, **Photos** i **History**. Jeśli **Product edit page Form** jest wyłączone, zostaje tylko **History** (gdy **Product Edit History** jest włączone).

**Generate** – każdy przycisk pisze jedno pole i zapisuje tekst w produkcie.

| Element | Co robi |
|---|---|
| Przyciski **Language** | Wybierają jeden język sklepu. **Every language** zapisuje wszystkie. |
| **If the field already has text** | **Replace** (domyślnie), **Add above**, **Add below** lub **Skip if filled**. |
| **Description** | Długi tekst z krótkim wstępem i listą cech. |
| **Short description** | Krótkie, zwykłe podsumowanie, poniżej około 400 znaków. |
| **Name** | Tytuł produktu widoczny dla klientów. |
| **Meta title** | Tytuł w wynikach wyszukiwania, około 70 znaków. |
| **Meta description** | Tekst w wynikach wyszukiwania, około 160 znaków. |
| **Tags** | Lista słów oddzielonych przecinkami. |
| **SEO pack** – **Fill all** | Pisze nazwę, oba opisy i oba pola meta za jednym razem. Jeśli odpowiedzi nie da się użyć, zobaczysz **The model did not return a usable SEO pack.** |
| **Fill** | Pojawia się na każdej karcie pola: generuje i zapisuje to pole. |
| **Use your own instruction or a saved prompt** | Otwiera pole filtra, kafelki z włączonymi szablonami (**Standard brief** jest domyślny) i pole **Instruction**. Zostaw pole puste, aby użyć standardowego opisu pola, które naciskasz. |

**Simulate** – te same karty pól z przyciskiem **Try**. Odpowiedź jest pokazywana na tej stronie, a produkt **nie** jest zmieniany. Użyj tego do przetestowania promptu, a potem wróć do **Generate**.

**Photos** – zobacz sekcję 3.16.

**History** – tabela **When**, **Type**, **Status** i przycisk **Restore**. **Restore** przywraca w produkcie poprzedni tekst z tego zapisu. Wiersze bez poprzedniej wartości lub z błędem nie mają przycisku. Ogólny raport **History** dla całego sklepu nie jest usuwany. Pusta lista pokazuje **No generations for this product yet.**

![Product photos](https://mypresta.eu/docs/images/docs/myaideepseek-product-photos.webp)

### 3.16 Zdjęcia produktu

Otwórz zakładkę **Photos** w produkcie. Jeśli **AI Image Finder** jest wyłączone, zakładka wyjaśnia, jak włączyć go w **Settings**, **General**.

1. Kliknij **Find pages**. DeepSeek proponuje strony internetowe, które prawdopodobnie zawierają zdjęcia produktu.
2. Pojawiają się strony i obrazy. Zaznacz obrazy, które chcesz.
3. Kliknij **Add selected to this product**. Przed tym kliknięciem nic nie jest zapisywane.

Model proponuje strony na podstawie własnej wiedzy, a nie z wyszukiwania w sieci na żywo. Przed publikacją sprawdź obrazy pod kątem praw autorskich i jakości.

## 4. Strona sklepu dla klientów

Moduł nie pokazuje klientom niczego. Dwa zarejestrowane hooki front są puste, a do Twojego motywu nie jest dodawany żaden szablon, przycisk ani blok. Tekst zapisany przez moduł pojawia się w Twoim sklepie wyłącznie jako zwykłe pola produktów i kategorii (nazwa, opisy, meta tagi, tagi). Nie musisz zmieniać motywu.

Moduł ma też dwa adresy, które może otworzyć przeglądarka lub serwer:

| Adres | Kto go używa | Co się dzieje |
|---|---|---|
| Adres **Cron** z `&action=generateProductContent` lub `&action=generateCategoryContent` | Harmonogram Twojego serwera lub Ty podczas testów | Zapisywana jest jedna partia. Przy **Enable Debug** ustawionym na **Yes** plan jest wypisywany i nic nie jest zapisywane. Błędny lub brakujący sekret jest odrzucany. |
| Wewnętrzny adres zapytań używany przez przyciski panelu administracyjnego | Twoja przeglądarka, gdy pracujesz w panelu administracyjnym | Wymaga tokenu, który panel administracyjny dodaje automatycznie. Nigdy go nie wpisujesz. Jeśli zostanie odrzucony, przeładuj stronę panelu administracyjnego. |

## 5. Problemy

**Generowanie kończy się niepowodzeniem, a History pokazuje Error.**
Otwórz **History**, otwórz wiersz i przeczytaj komunikat. Typowe przyczyny podano poniżej.

**Klucz API jest odrzucany lub go brakuje.**
Otwórz **Settings**, **DeepSeek**, wklej klucz ponownie z https://platform.deepseek.com/api_keys i naciśnij **Save**. Na stronie nowego produktu ostrzeżenie **Add an API key in the module settings first.** znika po tym kroku. Jeśli DeepSeek zgłasza brak środków, zasil konto w DeepSeek.

**Wywołanie kończy się przekroczeniem czasu.**
Zwiększ **API timeout (seconds)** w **Settings**, **General** (dla `deepseek-reasoner` użyj kilkuset sekund). W cronie zmniejsz **Product to update**.

**Tekst jest ucięty w połowie zdania.**
Zwiększ **Max Tokens** w **Settings**, **DeepSeek**. W `deepseek-reasoner` limit obejmuje także jego rozumowanie.

**Ustawienia chyba nie zmieniają stylu.**
W `deepseek-reasoner` pola **Temperature**, **Top P** i dwie kary mogą być ignorowane. Użyj `deepseek-chat`. Sprawdź też, czy **Studio** jest zapisane i czy użyto właściwego języka.

**Odpowiedź nie jest zapisywana i nic się nie zmienia w produkcie.**
Możliwe przyczyny: odpowiedź zawiera wpis z **Forbidden words**, a **Quality gate** jest włączone (zmień listę lub wyłącz bramkę); **Existing text** ma wartość **Skip if filled**, a pole zawiera tekst; osiągnięto limit miesięczny (**Monthly generation budget reached. Raise it in the studio settings or wait until next month.**).

**Wpisana przeze mnie nazwa modelu nie działa.**
Dodano identyfikator, którego Twoje konto nie może wywołać. Wybierz ponownie wbudowany `deepseek-chat` i usuń własny wpis.

**Lista Generate jest pusta lub zbyt krótka.**
Sprawdź **Product status**, **Product stock**, **Update only** i **Product Limit**. Częsty błąd to pozostawienie **Update only** na "already updated" przy pierwszym uruchomieniu.

**Cron nic nie robi.**
Sprawdź w tej kolejności: **Enable Cron Feature** jest ustawione na **Yes**; adres kończy się poprawnym `&action=…`; sekret to ten aktualnie pokazany; **Enable Debug** jest ustawione na **No**; **Selected Products** nadal ma oczekujące pozycje; serwer naprawdę wywołuje adres. Zakończony zestaw przestaje się zmieniać celowo. Dla kilku pól użyj **pendingField** zamiast **pendingDeepSeek**, ponieważ drugi pomija produkt, gdy tylko jakiekolwiek pole zostało wygenerowane.

**Cron przestał działać po zmianie sekretu.**
Stary adres przestał być ważny. Skopiuj nowy adres (z `&action=…`) do harmonogramu.

**Strona pokazuje "Error! Invalid token!" lub przyciski milczą.**
Strona była otwarta zbyt długo. Przeładuj stronę panelu administracyjnego i spróbuj ponownie.

**Zakładka Modules w produkcie nie ma treści My AI DeepSeek.**
Sprawdź, czy **Product edit page Form** lub **Product Edit History** jest włączone, czy moduł jest aktywny i czy pamięć podręczna została wyczyszczona.

**Brak przycisku "Restore".**
Wiersz był błędem, zapis nie miał poprzedniej wartości albo **Clear list** usunęło wiersze History.

**Niektóre etykiety nadal mówią "OpenAi".**
Kilka komunikatów i etykiet filtrów zachowuje starszą nazwę, na przykład **OpenAi Settings Updated** po zapisaniu formularza **DeepSeek**, opcje "updated with OpenAi content" filtra **Update only** lub starszą przykładową nazwę modelu w podpowiedzi. Używaną usługą jest DeepSeek. W History kolumna **Provider** może pokazywać starszą nazwę wewnętrzną. Nie wpływa to na wyniki.

**Nic się nie zmienia na stronie sklepu dla klientów.**
Moduł zapisuje zwykłe pola produktów. Sprawdź produkt w **Catalog** i pamięć podręczną motywu.

## 6. Dla programisty

### 6.1 Przegląd

- **Nazwa techniczna:** `myaideepseek`
- **Nazwa modułu na liście:** My AI DeepSeek - AI content generation
- **Wersja:** 1.0.0
- **Autor:** MyPresta.eu
- **Zgodność z PrestaShop:** 1.6 – 9.99.99
- **PHP:** 7.0 lub nowszy (instalacja odrzuca starsze wersje)
- **Sieć:** cURL i HTTPS do `https://api.deepseek.com/v1`
- **Prefiks konfiguracji:** `MYPRESTA_MYAIDEEPSEEK_`
- **Przepływ:** ustawienia są odczytywane z tabeli konfiguracji; prompty są budowane z szablonu lub instrukcji oraz reguł Studio; na każde pole wysyłane jest jedno zapytanie czatu; odpowiedź jest sprawdzana (Quality gate, budżet), zapisywana w produkcie lub kategorii i logowana do `myaideepseek_log` wraz z poprzednią wartością.

### 6.2 Pliki

| Plik | Przeznaczenie |
|---|---|
| `myaideepseek.php` | Klasa główna: instalacja, odinstalowanie, formularze ustawień, nawigacja, hooki, zakładka produktu. |
| `autoload.php` | Ładowanie klas dla `src/` i `lib/`. |
| `src/OpenAIService.php` | Klient HTTP dla wywołania chat completion (zachowano pod starszą nazwą pliku). |
| `src/Studio.php` | Dodaje reguły Studio i kontrolę jakości. |
| `lib/updateChecker.php` | Sprawdzanie aktualizacji w MyPresta.eu. |
| `lib/sectionHelp.php` | Teksty podpowiedzi pomocy. |
| `lib/searchTool/` | Pomocnik autouzupełniania. |
| `lib/prestashop9compatibility.php` | Pomocnik zgodności z PrestaShop 9. |
| `controllers/admin/` | Siedem kontrolerów administracyjnych (zobacz 6.3). |
| `controllers/front/ajax.php` | Akcje AJAX panelu administracyjnego (generowanie, przywracanie, wyszukiwanie obrazów). |
| `controllers/front/cron.php` | Generowanie zaplanowane. |
| `views/templates/hook/*.tpl` | Zakładka produktu, generatory masowe, dashboard, cron, history, playground, nawigacja. |
| `views/templates/admin/product_creator.tpl` | Ekran nowego produktu. |
| `views/js/` | `back.js`, `product-fields.js`, `image-finder.js`, `dashboard.js`, `admin-help.js`, `admin-products-bulk.js`, `chart.min.js`. |
| `views/css/` | `back.css`, `admin-nav.css`, `stats.css`. |
| `translations/{iso}.php` | Tłumaczenia modułu. |

### 6.3 Kontrolery

| Klasa | Rola |
|---|---|
| `AdminMyAIDeepSeekMain` | Rodzic menu **AI Content Generator**. |
| `AdminMyAIDeepSeek` | **Generate** (`mds_sub=products` lub `categories`). |
| `AdminMyAIDeepSeekProductCreator` | **New product**. |
| `AdminMyAIDeepSeekSettings` | Wejście do ustawień (formularze znajdują się na stronie konfiguracji modułu). |
| `AdminMyAIDeepSeekCron` | Formularze **Cron**. |
| `AdminMyAIDeepSeekUsage` | **History**. |
| `AdminMyAIDeepSeekImageFinder` | **Images**. |
| `ModuleFrontController` ajax | Wymaga parametru `secret_token` równego `MYPRESTA_MYAIDEEPSEEK_TOKEN`; w przeciwnym razie odpowiada *Error! Invalid token!* |
| `ModuleFrontController` cron | Wymaga `secret` równego sekretowi produktów lub kategorii. |

Strona konfiguracji modułu używa `mds_tab` (`dashboard`, `settings`, `updates`), `mds_sub` (`general`, `openai` = sekcja **DeepSeek**, `studio`, `templates`, `playground`) oraz `mcg_preset` dla gotowych zakresów dat.

Parametry zapytania crona odczytywane przez `controllers/front/cron.php`:

| Parametr | Do czego służy | Wartość domyślna, gdy brak |
|---|---|---|
| `secret` | Sekret produktów lub kategorii (wymagany) | – |
| `action` | `generateProductContent` lub `generateCategoryContent` (wymagany) | – |
| `updatedField` | Pole do zapisu | zapisana wartość |
| `productTarget` / `categoryTarget` | `pendingDeepSeek`, `pendingField`, `emptyField` | zapisana wartość |
| `productsToUpdate` / `categoriesToUpdate` | Rozmiar partii | zapisana wartość |
| `languageId` | Język | zapisana wartość |
| `promptTemplateId` | Szablon | zapisana wartość |
| `debug` | Tylko wypisz plan | zapisana wartość |
| `categories` | Filtr kategorii (produkty) | zapisana wartość |
| `productIds` | Filtr identyfikatorów produktów | zapisana wartość |

### 6.4 Hooki

Zarejestrowane: `displayAdminProductsMainStepLeftColumnMiddle`, `displayAdminProductsMainStepLeftColumnBottom` (oba zwracają pusty ciąg), `actionProductFormBuilderModifier` (kończy bez wyjścia), `displayAdminProductsExtra` (treść zakładki **Modules**), `displayBackOfficeHeader` (zasoby, loader strony produktu), `displayBackOfficeTop` (skrót w górnym pasku), `dashboardZoneTwo` (blok na dashboardzie PrestaShop), `displayHeader` i `displayFooter` (oba puste). Moduł nie udostępnia własnych hooków. Nie ma nadpisania `enable()` ani `disable()`.

### 6.5 Overrides

Brak.

### 6.6 Baza danych

| Tabela | Zawartość |
|---|---|
| `myaideepseek_prompt` | `id_prompt`, `status`, `title`, `prompt`, `date_generated`. 16 wierszy po instalacji. |
| `myaideepseek_log` | Jeden wiersz na zapytanie: identyfikatory produktu, kategorii, CMS, producenta, języka i pracownika; `type`, `method`, `status`, usługa, `model`, kod HTTP, czas trwania, liczby tokenów, komunikat błędu, `prompt`, `reply` oraz stare i nowe wartości nazwy, opisów, pól meta i tagów. |

Odinstalowanie usuwa obie tabele. Zakładki są usuwane. Tekst produktów i kategorii nie jest dotykany.

### 6.7 Klucze i tłumaczenia

Wszystkie klucze mają prefiks `MYPRESTA_MYAIDEEPSEEK_`.

| Sufiks klucza | Domyślnie | Znaczenie |
|---|---|---|
| `LIVE_MODE` | 0 | Live mode. |
| `DEBUG_MODE` | 0 | Debug mode. |
| `TIMEOUT` | 120 | Limit czasu wywołania w sekundach. |
| `PRODUCT_LOG` | 1 | Historia edycji produktu. |
| `TOPCTA` | 1 | Skrót w górnym pasku. |
| `PRODUCT` | 1 | Generator na stronie produktu. |
| `IMAGEFINDER_ENABLE` | 1 | Przełącznik wyszukiwarki zdjęć. |
| `IMAGEFINDER_PROMPT` | wbudowany tekst angielski | Instrukcja wyszukiwarki zdjęć. |
| `API_KEY` | puste | Klucz DeepSeek. |
| `MODEL` | `deepseek-chat` | Aktywny model. |
| `EXTRA_MODELS` | puste | Modele dodane przez sprzedawcę, po jednym w wierszu. |
| `MODEL_CAPS` | puste | Parametry poznane dla modelu w czasie działania. |
| `TEMPERATURE` | 0.7 | Próbkowanie. |
| `MAX_TOKENS` | 3200 | Limit odpowiedzi. |
| `TOP_P`, `FREQ_PEN`, `PRES_PEN` | 1, 0, 0 | Próbkowanie i kary. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | puste | Reguły Studio. |
| `BUDGET` | 0 | Limit miesięczny, 0 = brak. |
| `QUALITY` | 1 | Quality gate. |
| `TOKEN` | losowy | Token adresu AJAX. |
| `SECRET`, `CAT_SECRET` | losowy | Sekrety crona produktów i kategorii. |
| `ENABLE_CRON` | 0 | Globalny przełącznik crona. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Sugerowany interwał (Every Hour). |
| `updatedField`, `catupdatedField` | `description` | Pole crona. |
| `productTarget`, `categoryTarget` | `pendingDeepSeek` | Reguła crona. |
| `productsToUpdate`, `categoriesToUpdate` | 5 | Partia crona. |
| `promptTemplateId`, `catpromptTemplateId` | puste | Szablon crona. |
| `languageId`, `catlanguageId` | język domyślny | Język crona. |
| `debug`, `catdebug` | 0 | Debug crona. |
| `productIdsList`, `categories` | puste | Filtry crona. |
| `interval_select`, `IMAGEFINDER_TAB_OK` | puste / ustawiane w czasie działania | Stan interfejsu. |

Modelem domyślnym jest `deepseek-chat`. Modele wbudowane to `deepseek-chat` i `deepseek-reasoner`. Odinstalowanie usuwa powyższe klucze. Klucze filtrów Generate (na przykład filtry kategorii, marki i statusu w formularzach **Generate**) nie znajdują się na liście usuwania przy odinstalowaniu i mogą pozostać.

Tłumaczenia: dodaj `translations/{iso}.php` w standardowym formacie PrestaShop. Teksty pomocy pól są budowane przez `fieldHelp()` w formie What it does / How to configure / Effect i przechodzą przez `$this->l()`. Niektóre ciągi w zakładce produktu i szablonach generowania są zdefiniowane w plikach `.tpl` za pomocą `{l s=…}`. Kilka pozostałych ciągów nadal zawiera starszą nazwę dostawcy (zobacz Problemy).

### 6.8 Rozszerzanie

Zakładka produktu, ekrany masowe i cron używają tych samych zmiennych promptów i tych samych akcji AJAX, więc własny szablon, który stosuje `{product_name}`, `{product_brand}`, `{product_features}` i `{product_tags}`, działa wszędzie. Kontrolery front nie renderują żadnego szablonu, więc motyw nie ma czego nadpisywać. Szablony administracyjne w `views/templates/hook/` można nadpisać za pomocą standardowego nadpisywania szablonów modułu w motywie panelu administracyjnego.

## 7. Pomoc

Strona modułu: https://mypresta.eu/modules/administration-tools/my-ai-deepseek.html

Aby napisać w sprawie modułu:

1. Zaloguj się na swoje konto klienta na mypresta.eu.
2. Otwórz stronę kontaktową.
3. Wybierz temat **Support for paid modules**. Formularz informuje, że musisz być zalogowany. Po zalogowaniu wybierz ten moduł z historii zakupów.
4. Opisz problem. Dołącz wiersz z **History** (status i komunikat) oraz wersje PrestaShop i PHP. Nigdy nie wysyłaj klucza API ani sekretu crona.
