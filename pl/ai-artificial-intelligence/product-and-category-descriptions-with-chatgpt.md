---
title: "My ChatGPT - generowanie treści AI - dokumentacja i instrukcja obsługi"
description: "Ta instrukcja pomaga skonfigurować OpenAI, generować teksty katalogowe w posiadanym już module i naprawiać problemy, gdy generowanie się nie powiedzie."
sidebar:
  label: "My ChatGPT - generowanie treści AI - dokumentacja i instrukcja obsługi"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product and Category Descriptions with ChatGPT na MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-chatgpt.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ai-artificial-intelligence/product-and-category-descriptions-with-chatgpt/)
>
> ---


## 1. Wymagania

Sprawdź te punkty, zanim połączysz moduł z OpenAI.

- Użyj PrestaShop 1.6, 1.7, 8 lub 9 (do wersji 9.99.99).
- Użyj PHP 7.0 lub nowszego. Instalator nie przejdzie dalej na starszej wersji PHP.
- Włącz rozszerzenia PHP cURL i JSON. Każde połączenie z OpenAI i sprawdzanie aktualizacji korzysta z cURL. Włącz też mbstring, bo korzysta z niego czyszczenie tekstu w wyszukiwarce obrazów i na ekranie nowego produktu.
- Opcjonalnego pola **Opcjonalny adres URL źródła** na ekranie **Nowy produkt** używaj tylko wtedy, gdy PHP może czytać strony internetowe (ustawienie `allow_url_fopen`) i dostępne jest rozszerzenie DOM. Bez nich pole jest pomijane i liczy się wyłącznie Twój brief.
- Miej własne konto OpenAI i klucz API z platform.openai.com. Klucz musi mieć prawo wywoływać wybrany model. Za każde zapytanie płacisz OpenAI. Moduł nie zawiera kredytu.
- Zapewnij serwerowi dostęp do internetu na porcie 443. Sklep łączy się z OpenAI przy każdym generowaniu oraz z serwerem aktualizacji MyPresta.eu przy sprawdzaniu aktualizacji.
- Dodaj zaplanowane zadanie (CRON) na serwerze tylko wtedy, gdy generowanie ma działać bez klikania. Adresy cron nic nie robią, dopóki serwer ich nie wywoła.
- Żaden inny moduł PrestaShop nie jest wymagany.
- Zaplanuj czas przy dużych katalogach. Każde pole w każdym języku to osobne zapytanie do OpenAI. Masowe uruchomienie dla 500 produktów, czterech pól i dwóch języków wysyła 4000 zapytań, jedno po drugim, i zajmuje kartę przeglądarki. Zacznij od małych partii testowych albo użyj partii cron przy dużych katalogach.

## 2. Instalacja

1. Otwórz **Moduły**, potem **Menedżer modułów**.
2. Kliknij **Wgraj moduł** i wgraj plik ZIP.
3. Kliknij **Zainstaluj** przy module **Mój ChatGPT - Generowanie treści AI**.
4. Otwórz **Moduły** w menu po lewej. Pojawi się tam nowa pozycja **Generator treści AI**. Kliknij ją, aby otworzyć **Panel** modułu. **Skonfiguruj** w **Menedżerze modułów** otwiera to samo miejsce.

Instalacja robi następujące rzeczy:

- Dodaje pozycję menu **Generator treści AI** w **Moduły**. Pozostałe ekrany modułu otwierasz z jego własnego górnego menu, nie mają osobnych pozycji w menu.
- Tworzy dwie tabele: jedną na szablony promptów i jedną na historię każdego generowania.
- Dodaje 16 gotowych szablonów promptów (nazwy produktów, opisy, meta tytuły, meta opisy i tagi). Wszystkie są włączone.
- Tworzy długie tajne wartości dla wewnętrznych wywołań modułu i dla dwóch adresów cron.
- Wyłącza filtr HTML obowiązujący w całym sklepie (HTMLPurifier). Opisy i teksty kategorii zachowują wtedy znaczniki HTML, ale ten sam przełącznik jest wyłączony dla każdego innego tekstu w sklepie. Włącz go ponownie w ustawieniach sklepu, jeśli tego nie chcesz.
- Nie czyści pamięci podręcznej PrestaShop. Wyczyść ją w **Parametry zaawansowane**, potem **Wydajność**, tylko jeśli widać stare style lub stary ekran.

Jeśli instalator pokaże „Ten moduł wymaga PHP 7.0.0 lub nowszego”, najpierw zaktualizuj PHP. Jeśli pokaże „Nie udało się utworzyć tabel bazy danych modułu.”, sprawdź, czy użytkownik bazy danych może tworzyć tabele, i zainstaluj ponownie.

Odinstalowanie:

- Usuwa pozycje menu, obie tabele (wszystkie szablony promptów i cała **Historia** przepadają) oraz prawie wszystkie ustawienia modułu, w tym klucz API i sekrety cron.
- Nie włącza z powrotem filtra HTML. Włącz go sam, jeśli chcesz.
- Nie usuwa żadnych tekstów produktów, tekstów kategorii ani zdjęć produktów, które utworzył moduł. Zostają w katalogu.
- Zostawia kilka nieszkodliwych resztek w konfiguracji sklepu (zapisany wybór kategorii cron, ostatnie wartości filtrów z **Generuj** i wartości sprawdzania aktualizacji).
- Nowa instalacja tworzy nowe sekrety, pustą Historię i ponownie 16 domyślnych szablonów. Stare adresy cron przestają działać, więc skopiuj je jeszcze raz.

## 3. Konfiguracja i praca w zapleczu

Otwórz **Moduły**, potem **Generator treści AI**. Górne menu modułu zawiera pozycje: **Panel**, **Ustawienia**, **Generuj**, **Nowy produkt**, **Cron**, **Historia**, **Obrazy** i, po prawej, **Aktualizacje**. Okrągły przycisk **Pomoc** na dole każdego ekranu modułu otwiera krótkie wyjaśnienie ekranu, na którym jesteś.

Zrzuty ekranu w tej instrukcji pochodzą z angielskiego panelu administracyjnego. Nazwy przycisków, pól i zakładek podano w tej instrukcji po polsku. W opisie każdego zrzutu w nawiasie widać angielski napis z ekranu.

Postępuj według tego procesu:

1. Otwórz **Ustawienia**, potem **ChatGPT**. Wklej klucz API OpenAI i wybierz model. Kliknij **Zapisz**.
2. Opcjonalnie otwórz **Studio** i ustaw głos marki, odbiorców, ton, słownik, zabronione słowa, miesięczny budżet i bramkę jakości.
3. Otwórz **Szablony promptów**. Przejrzyj 16 szablonów, edytuj je albo dodaj własne i zostaw włączone tylko te, z których ma korzystać Twój zespół.
4. Generuj tekst w sposób pasujący do zadania:
   - Jeden produkt: otwórz produkt, zakładkę **Moduły** i użyj **Generuj**, **Symuluj** lub **Zdjęcia**. Działają też małe przyciski **Generuj z AI** obok pól opisu i meta.
   - Wiele produktów lub kategorii naraz: otwórz **Generuj**, zbuduj listę filtrami i naciśnij **Uruchom**.
   - Nowy produkt z krótkiego briefu: otwórz **Nowy produkt**.
   - Zaplanowane partie bez klikania: otwórz **Cron** i dodaj adres do harmonogramu serwera.
5. Sprawdź **Historię**, aby zobaczyć każdy prompt, odpowiedź, błąd i liczbę tokenów. Sprawdź **Panel**, aby zobaczyć sumy i wykresy.

Moduł nie ma statusów w stylu zamówień. Szablon promptu jest **Włączony** albo **Wyłączony**. Każde wywołanie w **Historii** ma wynik **Sukces** albo **Błąd**. Masowe uruchomienie lub cron kończy się, gdy zapisany zostanie ostatni element, a tekst trafia do produktu lub kategorii zaraz po nadejściu każdej odpowiedzi.

Jeśli włączona jest opcja **Przycisk CTA na górnym pasku administratora**, na górnym pasku każdej strony zaplecza widać mały przycisk z magiczną różdżką **Mój ChatGPT**. Otwiera małe okno z listą szablonów, polem tekstowym i przyciskiem **Generuj**. Działa jak **Piaskownica** (sekcja 3.6): odpowiedź jest pokazana w oknie i nic nie jest zapisywane w katalogu.

Na liście produktów w **Katalog**, **Produkty**, moduł dodaje także przycisk **Mój ChatGPT**, który otwiera **Generuj**.

### 3.1 Panel

Otwórz **Generator treści AI**, **Panel**. Ta strona jest raportem. Nigdy nie zapisuje tekstów produktów ani kategorii.

![Panel (Dashboard)](https://mypresta.eu/docs/images/docs/mychatgpt-dashboard.webp)

- Kliknij przycisk okresu: **Dziś**, **7 dni**, **30 dni** (otwarty domyślnie), **90 dni**, **W tym miesiącu** lub **Cały czas**. Możesz też wpisać **Od** i **Do** i kliknąć **Zastosuj**.
- Wiersz **Aktywna usługa** pokazuje ChatGPT i model zapisany w **Ustawienia**, **ChatGPT**.
- Czytaj karty **Żądania**, **Sukces**, **Błędy**, **Wysłane tokeny** i **Odebrane tokeny** dla wybranego okresu. **Żądania** liczą każde wywołanie zapisane w **Historii**. **Błędy** liczą te nieudane. Wysłane tokeny to rozmiar Twojej instrukcji, odebrane tokeny to rozmiar odpowiedzi.
- Czytaj wykresy **Żądania i błędy**, **Wysłane i odebrane tokeny** oraz **Żądania według modelu**.
- Puste wykresy oznaczają, że w tym okresie nic nie wygenerowano. Zmiana dat tylko odrysowuje stronę. Nic nie jest usuwane.

### 3.2 Ustawienia – Ogólne

Otwórz **Ustawienia**, potem **Ogólne**. Po każdej zmianie kliknij **Zapisz**. Zobaczysz „Ustawienia zaktualizowane”.

![Ustawienia ogólne (General settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-general.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Tryb na żywo** | Nie | Oznacza, że moduł działa w prawdziwym sklepie, a nie w konfiguracji próbnej. Włącz w produkcji. Po wyłączeniu narzędzia są te same, ale moduł sygnalizuje, że to nie jest konfiguracja produkcyjna. |
| **Tryb debugowania** | Nie | Zapisuje dodatkowe szczegóły techniczne, gdy wywołanie OpenAI się nie powiedzie. Włączaj tylko na czas badania problemu. Szczegóły znajdziesz w **Parametry zaawansowane**, **Logi**. Klienci ich nie widzą. |
| **Limit czasu API (sekundy)** | 120 | Jak długo jedno wywołanie OpenAI może trwać, zanim moduł się podda. 120 wystarcza do zwykłych opisów. Podnieś do 600 przy długich tekstach lub wolnych modelach. Wartości poniżej 10 są podnoszone do 10, powyżej 600 obniżane do 600, a puste lub nienumeryczne zamieniane na 120. Krótki limit szybko kończy się błędem i zapisuje go w Historii. |
| **Historia edycji produktu** | Tak | Dodaje na stronie produktu listę **Historia** z przyciskiem **Przywróć**, aby redaktorzy mogli wrócić do starszego tekstu. Po wyłączeniu lista jest ukryta. Wiersze i tak zostają w **Historii**. |
| **Przycisk CTA na górnym pasku administratora** | Tak | Dodaje skrót **Mój ChatGPT** do górnego paska zaplecza na każdej stronie. Po wyłączeniu znika tylko ten przycisk. Pozycja menu **Generator treści AI** zostaje. |
| **Formularz strony edycji produktu** | Tak | Pokazuje panel generatora (**Generuj**, **Symuluj**, **Zdjęcia**) w zakładce **Moduły** produktu oraz przyciski **Generuj z AI** obok pól opisu i meta. Po wyłączeniu są ukryte. Wyłącz, gdy mają działać tylko generowanie masowe i cron. |
| **Wyszukiwarka obrazów AI** | Tak | Pozwala redaktorowi poprosić model o strony internetowe, które prawdopodobnie pokazują zdjęcia bieżącego produktu. Po włączeniu na produkcie widać zakładkę **Zdjęcia**. Po wyłączeniu jest ukryta. Nic nie jest pobierane, dopóki ktoś nie potwierdzi zdjęć. Ten sam przełącznik jest w **Obrazy** (sekcja 3.12). |
| **Prompt wyszukiwania obrazów AI** | Długi tekst domyślny | Instrukcja wysyłana, gdy ktoś szuka zdjęć. Domyślnie prosi o dokładnie pięć adresów stron w postaci prostej listy, z preferencją dla stron producentów, dużych sprzedawców i katalogów. Słowa `{product_name}` i `{product_description}` są zastępowane bieżącym produktem. Zachowaj prośbę o prostą listę adresów. Precyzyjny prompt zwraca trafne strony, ogólnikowy zwraca niepowiązane linki. Ten sam tekst jest w **Obrazy**. |

### 3.3 Ustawienia – ChatGPT

Otwórz **Ustawienia**, potem **ChatGPT**. Formularz nazywa się **Ustawienia OpenAI**. Każde generowanie, także przyciski przy produkcie, uruchomienia masowe i cron, korzysta z tych wartości. Kliknij **Zapisz**. Zobaczysz „Ustawienia OpenAI zaktualizowane”.

![Ustawienia ChatGPT (ChatGPT settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-chatgpt.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Klucz API OpenAI** | Pusty | Sekret, który pozwala sklepowi wywoływać Twoje konto OpenAI. Wklej klucz utworzony na platform.openai.com na swoim koncie OpenAI. Spacje wokół klucza są usuwane przy zapisie. Pozostaw pole nietknięte, aby zachować zapisany już klucz. Pusty lub błędny klucz powoduje błąd każdego generowania, a błąd trafia do Historii. Jeśli zapiszesz nowy klucz krótszy niż 10 znaków, gdy żaden klucz nie jest zapisany, zobaczysz „Pole Klucz API OpenAI jest nieprawidłowe!”. |
| **Model** | gpt-3.5-turbo | Model ChatGPT, który pisze tekst. Lista zawiera wbudowane modele (gpt-4o, gpt-4o-mini, gpt-4-turbo, gpt-4, gpt-3.5-turbo, o4-mini, o3-mini, o1-mini i inne) oraz modele, które dodałeś. Wybierz jeden i kliknij **Zapisz**. Model, którego Twój klucz nie może użyć, zwraca błąd OpenAI zamiast tekstu. Pusty model daje „Pole Model OpenAI jest nieprawidłowe!”. |
| **Dodaj model ChatGPT** | Pusty | Dodaje nazwę modelu, której nie ma na liście wbudowanej. Wpisz dokładną nazwę z konta OpenAI (na przykład `gpt-4.1`) i kliknij **Dodaj model**. Nazwa pojawia się w **Model** i staje się aktywnym modelem. **Usuń** obok dodanej nazwy ją kasuje. Wbudowanych nazw nie można usunąć. Jeśli usuniesz aktywny dodany model, moduł przełączy się na gpt-4o. Komunikaty: „Model dodany.”, „Ten model jest już wbudowany.”, „Model usunięty.”, „Wbudowanych modeli nie można usunąć.”, „Wprowadź ID modelu, np. gpt-4.1.”. |
| **Maksymalna liczba tokenów** | 3200 | Górny limit długości odpowiedzi, liczony w tokenach, nie w słowach. Użyj około 256 dla meta opisu i 1000 lub więcej dla pełnego opisu HTML. Zbyt mało ucina odpowiedź. Zbyt dużo pozwala na długi tekst i podnosi rachunek w OpenAI. Wartość 0 jest traktowana jako pusta i zamieniana na 256. |
| **Temperatura** | 0.7 | Jak swobodnie model dobiera słowa. Trzymaj się między 0 a 1. Użyj około 0.2 dla specyfikacji i tekstów meta, a około 0.7 dla opisów. Zmieniaj to albo **Top P**, nie oba naraz. Niskie wartości powtarzają podobną strukturę. Wysokie wprowadzają więcej różnorodności i mogą odejść od briefu. Wartość 0 jest traktowana jako pusta i zamieniana na 0.7. |
| **Top P** | 1 | Inny sposób ograniczania, jak zaskakujące może być następne słowo. 1 uwzględnia pełny zakres. Zostaw 1, jeśli ustawiłeś już **Temperaturę**. Niższa wartość, na przykład 0.9, daje węższe słownictwo. Wartość 0 jest zamieniana na 1. |
| **Wartość kary za częstotliwość** | 0 | Ogranicza frazy powtarzające się w jednej odpowiedzi. Użyj 0, chyba że opisy ciągle kopiują to samo zdanie, wtedy spróbuj 0.3–0.6. Dozwolony zakres od -2 do 2. Nie porównuje produktów między sobą. |
| **Wartość kary za obecność** | 0 | Popycha odpowiedź ku nowym tematom. Domyślnie użyj 0. Spróbuj małej liczby dodatniej, jeśli każdy akapit mówi to samo. Dozwolony zakres od -2 do 2. Niektóre nowsze modele ignorują to pole. |

Moduł sam uczy się, których ustawień model odmawia (niektóre modele rozumujące odrzucają temperaturę lub kary), i przestaje je do niego wysyłać.

### 3.4 Ustawienia – Studio

Otwórz **Ustawienia**, potem **Studio**. Studio dodaje zasady firmowe do każdego promptu: przycisków przy produkcie, uruchomień masowych, crona i piaskownicy. Puste pola są pomijane. Kliknij **Zapisz studio**. Zobaczysz „Ustawienia studia zapisane.”. Tekst już zapisany w katalogu nie jest przepisywany.

![Ustawienia Studio (Studio settings)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-studio.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Głos marki** | Pusty | Mówi modelowi, kto przemawia, aby tekst pasował do Twojego sklepu, a nie do ogólnego asystenta. Napisz krótki brief, na przykład „specjalistyczny warsztat, krótkie zdania, bez przesady”. Każde kolejne generowanie zaczyna się od tego głosu. |
| **Odbiorcy** | Pusty | Wskazuje czytelnika, dla którego model ma pisać, na przykład „zawodowi monterzy” albo „osoby kupujące po raz pierwszy”. Odpowiedzi używają słownictwa i przykładów dopasowanych do tego czytelnika. |
| **Ton** | Pusty | Nastrój sformułowań: formalny, ciepły, techniczny. Wystarczą jedno lub dwa słowa. Nie zmienia modelu ani temperatury. |
| **Słownik** | Pusty | Nazwy marek, materiały i pisownie, które model musi skopiować dokładnie. Wpisz jeden termin w wierszu. Nowy tekst preferuje te pisownie. Terminy spoza listy mogą nadal zostać sparafrazowane. |
| **Zabronione słowa** | Pusty | Słowa i frazy, które nie mogą pojawić się w zapisanej odpowiedzi. Po jednym w wierszu. Lista działa tylko przy włączonej **Bramce jakości**. Odpowiedź zawierająca któryś z wierszy (także wewnątrz dłuższego słowa) jest odrzucana, nie trafia do produktu i jest zapisana w Historii jako błąd. |
| **Miesięczny budżet generowania** | 0 | Największa liczba udanych generowań, które sklep może wykonać w bieżącym miesiącu kalendarzowym. Wpisz liczbę całkowitą. 0 oznacza brak limitu. Licznik zaczyna się od nowa pierwszego dnia miesiąca. Po osiągnięciu limitu nowe generowania zatrzymują się z komunikatem o budżecie. Nieudane wywołania nie są liczone. Piaskownica, przyciski przy produkcie, uruchomienia masowe i cron liczą się wszystkie. |
| **Bramka jakości** | Tak | Sprawdza każdą odpowiedź względem **Zabronionych słów**, zanim cokolwiek zostanie zapisane. Włączona blokuje pasującą odpowiedź. Wyłączona zapisuje odpowiedź nawet wtedy, gdy zawiera słowo z listy. |

### 3.5 Ustawienia – Szablony promptów

Otwórz **Ustawienia**, potem **Szablony promptów**. Szablon to zapisana instrukcja, którą redaktorzy wybierają po tytule, zamiast za każdym razem pisać ten sam brief. Tytuł jest tylko etykietą w liście rozwijanej. Model otrzymuje tekst promptu. Włączone szablony pojawiają się w panelu produktu, w generatorze masowym i w formularzu cron. Wyłączone zostają na liście, ale nie są oferowane (formularz cron nadal je wyświetla, więc wybierz włączony).

![Szablony promptów (Prompt templates)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-templates.webp)

Lista **Szablony promptów** pokazuje **ID**, **Tytuł**, **Prompt**, **Status** i **Sygnatura czasowa**, od najnowszych, po 50 na stronie.

- Kliknij zielony przycisk **+**, aby utworzyć szablon.
- Kliknij znak statusu w wierszu, aby przełączyć szablon między włączonym a wyłączonym.
- Użyj **Edytuj** lub **Usuń** w wierszu. Zaznacz kilka wierszy i użyj akcji zbiorczej **Usuń** (musisz potwierdzić „Czy na pewno chcesz usunąć wybrane prompty?”).

Formularz **Generuj szablon promptu**:

| Pole | Na starcie | Co robi |
|---|---|---|
| **Status** | Wyłączony dla nowego szablonu | Pokazuje lub ukrywa ten szablon w listach rozwijanych na stronie produktu, w generowaniu masowym i w cronie. Włącz szablony, z których ma korzystać personel. Wyłącz szkic zamiast go usuwać. |
| **Tytuł promptu** | Pusty (wymagane) | Nazwa, którą redaktorzy widzą na liście rozwijanej, na przykład „Opis HTML z cechami”. Nie jest wysyłana do modelu. |
| **Treść promptu** | Pusty (wymagane) | Instrukcja wysyłana do modelu. Napisz ją tak, jak brief dla copywritera: długość, HTML, język. Zmienne w nawiasach klamrowych są wypełniane danymi pisanego elementu. Podwójne cudzysłowy są przy zapisie zamieniane na pojedyncze. |

Kliknij **Zapisz prompt**. Zobaczysz „Szablon promptu został pomyślnie dodany!” lub „Szablon promptu został pomyślnie zaktualizowany!”. **Wróć do ustawień modułu** wraca do listy. Po usunięciu zobaczysz „Szablon promptu usunięty.”.

Zmienne, których możesz użyć w szablonie:

| Dla | Zmienne | Zastępowane przez |
|---|---|---|
| Produkty | `{product_name}`, `{product_description}`, `{product_description_short}`, `{product_tags}`, `{product_reference}`, `{product_ean13}`, `{product_weight}` | Wartość tego produktu w pisanym języku. |
| Produkty | `{product_brand}`, `{product_default_category}`, `{product_category_description}`, `{product_categories}` | Dane marki i kategorii produktu. |
| Produkty | `{product_attributes}`, `{product_features}`, `{product_feature_values}`, `{product_images}` | Atrybuty oddzielone przecinkami, nazwy cech, pary nazwa:wartość cech i adresy zdjęć produktu. |
| Kategorie | `{category_name}`, `{category_description}`, `{category_parent_name}` | Kategoria i jej rodzic. |
| Produkty i kategorie | `{shop_name}`, `{shop_url}`, `{shop_language}`, `{shop_country}`, `{shop_currency}` | Dane Twojego sklepu. |

16 domyślnych szablonów to **Nazwa produktu 1–2**, **Opis produktu 1–7**, **Meta tytuł produktu 1–3**, **Meta opis produktu 1–3** i **Tagi produktu**. Część z nich zawiera przykładowe sformułowania (na przykład smartwatch). Przejrzyj je przed pierwszym uruchomieniem masowym.

### 3.6 Ustawienia – Piaskownica

Otwórz **Ustawienia**, potem **Piaskownica**. Piaskownica to brudnopis, który wywołuje aktywny model i pokazuje odpowiedź na stronie. Użyj jej, aby wypróbować prompt, zanim zapiszesz go jako szablon, albo aby sprawdzić, czy Twój klucz API działa.

![Piaskownica (Playground)](https://mypresta.eu/docs/images/docs/mychatgpt-settings-playground.webp)

1. Wpisz instrukcję w polu. Szara podpowiedź brzmi „Zapytaj model o cokolwiek z Twojego katalogu”.
2. Kliknij **Generuj**.
3. Przeczytaj odpowiedź i liczbę tokenów pod przyciskiem.

Wywołanie korzysta z modelu, wartości próbkowania i zasad Studio, które zapisałeś. Odpowiedź trafia do Historii. Żaden produkt, kategoria ani pole meta nie jest zmieniane. Wpisuj prawdziwe nazwy i szczegóły: zmienne w nawiasach klamrowych nie są w piaskownicy wypełniane.

### 3.7 Generuj – Produkty

Otwórz **Generuj**, potem podzakładkę **Produkty**. Pracuj w dwóch krokach. Krok 1 tylko buduje listę. Nic nie jest wysyłane do OpenAI i nic nie jest zapisywane jako ustawienie sklepu.

![Generuj produkty (Generate products)](https://mypresta.eu/docs/images/docs/mychatgpt-generate-products.webp)

Krok 1 – formularz **Filtr produktów do aktualizacji**. Wszystkie filtry łączą się ze sobą. Filtr, który zostawisz pusty, jest pomijany.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Kategorie produktów** | Nic nie zaznaczono | Zostawia produkty z zaznaczonych kategorii (także produkty, których kategorią domyślną jest jedna z nich). Puste drzewo wyłącza ten filtr. |
| **Marka** | Wybierz markę | Zostawia produkty jednego producenta. Pusta opcja obejmuje każdą markę. |
| **Status produktu** | Aktywne | **Aktywne** zostawia produkty w sprzedaży, **Wyłączone** zostawia szkice, **Oba** zostawia wszystkie. |
| **Stan magazynowy produktu** | Wszystkie produkty | **Tylko produkty w magazynie** usuwa produkty bez dostępnej ilości. **Wszystkie produkty** ignoruje stan magazynowy. |
| **Aktualizuj tylko** | Aktualizuj wszystko | **Produkty, które nie zostały jeszcze zaktualizowane treścią OpenAI** służy do pierwszego przejścia (produkty bez wiersza w Historii). **Produkty, które zostały już zaktualizowane treścią OpenAI** służy do przepisywania. **Aktualizuj wszystko** ignoruje Historię. |
| **ID produktów** | Pusty | Tylko te numery produktów, oddzielone przecinkami, na przykład 12,45,103. |
| **Referencja produktu** | Pusty | Tylko produkty z tymi kodami referencyjnymi, oddzielonymi przecinkami. |
| **Data dodania produktu od** | Pusty | Pomija produkty utworzone przed tą datą i godziną. |
| **Data dodania produktu do** | Pusty | Pomija produkty utworzone po tej dacie i godzinie. |
| **Minimalne ID produktu** | Pusty | Pomija produkty z mniejszym numerem. |
| **Maksymalne ID produktu** | Pusty | Pomija produkty z większym numerem. |
| **Limit produktów** | Pusty | Największa liczba produktów wczytanych do listy, na przykład 20. Lista nigdy nie pokaże więcej, więc jedno uruchomienie nie przejdzie przypadkiem całego katalogu. |

Kliknij **Przejdź do następnego kroku**. **Ustawienia modułu** otwiera konfigurację modułu.

Krok 2 – panel **Masowe generowanie produktów** i tabela produktów (**ID**, **Referencja**, **Wynik**):

| Pole | Na starcie | Co robi |
|---|---|---|
| **Szablon** | Wybierz szablon | Wypełnia pole promptu z włączonego szablonu. Możesz też wpisać własny prompt. Tytuł nie jest wysyłany. Jeśli pole zostanie puste, moduł używa standardowego briefu dla każdego pola. |
| Pole promptu | Pusty | Instrukcja dla każdego produktu w tabeli. Jeśli wpiszesz jeden tekst, ten sam tekst jest użyty dla każdego wybranego pola, więc uruchamiaj jedno pole naraz, gdy pola wymagają różnych sformułowań. |
| **Co wygenerować** | Opisy | **Opisy** pisze opis długi i krótki. **Meta tytuł i meta opis** pisze oba pola meta. **Opisy i meta razem** pisze wszystkie cztery. Każde pole to osobne zapytanie. Nazwy i tagi pisze się ze strony produktu, nie stąd. |
| **Istniejący tekst** | Zastąp | **Zastąp** nadpisuje. **Pomiń, jeśli wypełnione** zostawia wypełnione pole w spokoju i nie wywołuje dla niego modelu. **Dodaj powyżej** i **Dodaj poniżej** zachowują stary tekst i dołączają nowy. |
| **Języki** | Zaznaczony Twój bieżący język | Zaznacz każdy język do napisania. Każdy zaznaczony język jest generowany osobno. Niezaznaczone języki zachowują swój tekst. |

Kliknij **Uruchom na poniższej liście**. Wiersz stanu pokazuje postęp, na przykład „3 / 40 – description”. Każdy wiersz pokazuje własne wyniki, gdy tylko dany produkt się zakończy, na przykład „description: success Content successfully generated and updated to product.”, „description_short: skipped Product skipped.” albo „meta_title: error …” z powodem. Na końcu zobaczysz „Finished N products.”. Bez zaznaczonego języka zobaczysz „Select at least one language.”.

Nie zamykaj karty przeglądarki do końca uruchomienia. Zamknięcie zatrzymuje uruchomienie, a produkty już zapisane zostają zapisane. Aby kontynuować, zbuduj listę ponownie z opcją **Aktualizuj tylko** ustawioną na produkty, które nie zostały jeszcze zaktualizowane. Błąd przy jednym polu nie cofa pól już zapisanych. Zacznij od małego **Limitu produktów**, na przykład 20, i najpierw sprawdź sformułowania.

### 3.8 Generuj – Kategorie

Otwórz **Generuj**, potem podzakładkę **Kategorie**. Oba kroki działają jak na ekranie produktów.

![Generuj kategorie (Generate categories)](https://mypresta.eu/docs/images/docs/mychatgpt-generate-categories.webp)

Krok 1 – formularz **Filtr kategorii do aktualizacji**:

| Pole | Na starcie | Co robi |
|---|---|---|
| **Kategorie** | Nic nie zaznaczono | Wybiera kategorie do następnego kroku. Puste drzewo nie zawęża listy według kategorii, więc lista zawiera wtedy każdą kategorię o wybranym statusie, razem ze **Stroną główną** i kategorią główną. Zaznacz kategorie, które chcesz. |
| **Status kategorii** | Aktywne | **Aktywne**, **Wyłączone** lub **Oba**. |

Kliknij **Przejdź do następnego kroku**.

Krok 2 – panel **Masowe generowanie kategorii** i tabela kategorii (**ID**, **Wynik**):

| Pole | Na starcie | Co robi |
|---|---|---|
| Pole promptu (pierwsze pole) | Pusty | Instrukcja wysyłana dla każdej kategorii. Opisz ton, długość i HTML. Nazwij temat w tekście. To pole nie wstawia zmiennych produktowych. Ten panel nie ma wyboru szablonu. |
| Lista pól | Opis | Pole do napisania: **Opis**, **Nazwa**, **Meta tytuł**, **Meta opis** lub **Dodatkowy opis**. Zapisywane jest tylko to pole. |
| Lista istniejącego tekstu | Zastąp | **Zastąp** nadpisuje. **Pomiń, jeśli wypełnione** zostawia wypełnione pole w spokoju i nie wywołuje modelu dla tej kategorii. |
| Lista języków | Twój bieżący język | Jeden język. Uruchom ponownie dla innego języka. |

Kliknij **Uruchom na poniższych kategoriach**. Wyniki pojawiają się w wierszach tak jak na ekranie produktów. Kategoria bez pola **Dodatkowy opis** w Twojej wersji PrestaShop pokazuje „Error! This PrestaShop version does not support the category Additional Description field.”.

Pod tabelą ekran pokazuje także formularz **Generuj treść kategorii**. Jego wstęp brzmi „This form writes the filtered categories. Press Generate content to start. Each category is saved as soon as its reply arrives.” W tej wersji ten formularz nie uruchamia generowania. Użyj **Uruchom na poniższych kategoriach** powyżej. Formularz ma te pola:

| Pole | Na starcie | Co robi |
|---|---|---|
| **Pole do aktualizacji** | Opis | Pole kategorii, które ten formularz przepisałby: **Nazwa kategorii**, **Opis**, **Meta tytuł**, **Meta opis** lub **Dodatkowy opis**. Tylko to pole jest wysyłane do modelu i zapisywane. Pozostałe pola zostają bez zmian. Opis i meta to osobne uruchomienia. |
| **Istniejące dane** | Zachowaj istniejące dane i dodaj nową wygenerowaną treść na górze | Co się dzieje, gdy wybrane pole ma już tekst: **Zachowaj istniejące dane i dodaj nową wygenerowaną treść na górze**, **Zachowaj istniejące dane i dodaj nową wygenerowaną treść na końcu**, **Zachowaj istniejące dane i pomiń kategorię** lub **Usuń dane i dodaj nową wygenerowaną treść**. Zastąpienie zmienia zapisany tekst. Pominięcie nie wywołuje modelu dla kategorii, która ma już to pole. Dodanie zachowuje obie wersje w jednym polu. |
| **Język** | Pierwszy język z listy | Wersja językowa, która jest pisana. Zmienia się tylko ten język. |
| **Prompt treści** | Pusty (wymagane) | Instrukcja dla każdej kategorii z listy. Opisz ton, długość i HTML. Nazwij temat kategorii w tekście, ponieważ zmienne produktowe nie są wstawiane. |
| **Opóźnienie wywołań API** | Pusty | Przerwa w sekundach między jedną kategorią a następną, aby nie trafić w limit zapytań OpenAI. Użyj 1 lub 2 przy kluczu niskiego poziomu. Ustaw 0, aby wysłać następne zapytanie od razu. Panel **Uruchom** powyżej nie używa tej przerwy. |

Przyciski **Generuj treść** i **Wróć do filtra kategorii** nie generują tekstu. **Generuj treść** tylko zapisuje wpisane wartości i ponownie pokazuje filtr. **Ustawienia modułu** otwiera konfigurację modułu.

### 3.9 Nowy produkt

Otwórz **Nowy produkt**. Panel **Utwórz produkt z briefu** prosi model o szkic produktu i może wstawić ten szkic jako nowy produkt. Służy do produktów, których nie ma jeszcze w katalogu. Aby uzupełnić istniejący produkt, użyj **Generuj** albo strony produktu.

![Nowy produkt (New product)](https://mypresta.eu/docs/images/docs/mychatgpt-new-product.webp)

Jeśli nie zapisano klucza, zobaczysz „Najpierw dodaj klucz API w ustawieniach modułu.”.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Co to za produkt?** | Pusty (wymagane) | Brief, który model rozwija w nazwę, opisy, meta, tagi, cechy, referencję i cenę. Napisz kilka zdań z materiałem, odbiorcami i nazwami, które mają zostać. Puste pole jest odrzucane z komunikatem „Prompt is required”. |
| **Opcjonalny adres URL źródła** | Pusty | Pełny adres publicznej strony o produkcie. Czytelna strona dodaje do briefu swój tytuł, opis i tekst ceny. Strona, której nie da się odczytać, jest pomijana. |
| **Język** | Domyślny język sklepu | Język, w którym tekst jest zapisywany. Inne języki nie są wypełniane. Wybierz domyślny język sklepu, ponieważ PrestaShop wymaga nazwy w języku domyślnym, aby utworzyć produkt. |
| **Domyślny ID kategorii** | 2 | Numer kategorii z **Katalog**, **Kategorie**. 2 to zwykle **Strona główna**. Produkt trafia do tej kategorii i staje się ona kategorią domyślną. |

1. Kliknij **Generuj dane**. Szkic pojawia się jako tekst w polu poniżej (nazwa, opis, opis krótki, meta tytuł, meta opis, słowa kluczowe, tagi, referencja, cena, cechy). Nic nie jest jeszcze zapisane. Kliknij ponownie, aby otrzymać nowy szkic. Szkicu nie można edytować na tym ekranie.
2. Sprawdź szkic, zwłaszcza proponowaną cenę i referencję.
3. Kliknij **Utwórz produkt**. Wiersz wyniku pokazuje „Product #” i numer nowego produktu.

Nowy produkt jest aktywny, dostępny do zamówienia, widoczny w katalogu i wyszukiwarce, w stanie nowym, z grupą reguł podatkowych o numerze 1, ze stanem magazynowym 100 sztuk i proponowaną ceną. Nazwa, opisy, meta, tagi i cechy są zapisywane tylko w wybranym języku. Ten ekran nie dodaje zdjęć. Otwórz nowy produkt, zakładkę **Moduły**, **Zdjęcia**, aby je dodać. Przed publikacją sprawdź cenę, podatek, ilość i kategorię. Generowanie tutaj nie jest zapisywane w Historii i nie liczy się do miesięcznego budżetu.

### 3.10 Cron

Otwórz **Cron**. Cron jest dla serwera, a nie dla osoby klikającej **Uruchom**. Ten ekran zapisuje Twoje wybory i pokazuje tajne adresy, które Twój serwer wywołuje według harmonogramu. Każde prawdziwe wywołanie zapisuje jedną małą partię i się zatrzymuje. Sklep nic nie robi, dopóki serwer nie zażąda adresu.

![Cron (Cron)](https://mypresta.eu/docs/images/docs/mychatgpt-cron.webp)

Górny panel **Cron kategorii** i panel **Parametry Crona** pokazują adresy Twojego sklepu z sekretami. Traktuj sekrety jak hasła: nigdy nie publikuj pełnego adresu. Ta instrukcja pokazuje je jako `YOUR_SECURE_KEY`, na przykład `https://your-shop.example/module/mychatgpt/cron?secret=YOUR_SECURE_KEY`. Do każdego adresu trzeba dopisać ustawienia z formularza (pole, język, szablon, wielkość partii i tak dalej). Sekcja 6.3 je wymienia. Poproś programistę lub hosting o ich dodanie przy konfiguracji harmonogramu.

Formularz produktów **CRON JOB Settings – Generate product content using OpenAI**. Po zmianie kliknij **Zapisz**.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Włącz funkcję cron** | Nie | Pozwala serwerowi generować teksty produktów i kategorii według harmonogramu. Włącz dopiero po zapisaniu sekretu, pola, języka i szablonu. Gdy jest wyłączone, każdy adres cron odpowiada, że funkcja jest wyłączona. Ten jeden przełącznik jest wymagany także dla crona kategorii. |
| **Tajny token zadania cron** | Długa losowa wartość | Długie hasło, które musi być częścią adresu cron produktów. Bez niego sklep odrzuca wywołanie. Zachowaj wygenerowaną wartość. Zmiana natychmiast unieważnia stary adres. Przycisk **Generuj token** w tej wersji nie tworzy nowej wartości, więc zachowaj wartość utworzoną przy instalacji. |
| **Pole do aktualizacji** | description | Jedno pole produktu, które ten cron zapisuje: name, description, description_short, meta_title, meta_description lub tags. Aby wypełnić kilka pól, utwórz kilka poleceń cron. |
| **Wybrane produkty** | pendingOpenAI | Decyduje, które produkty nadal czekają. **pendingOpenAI**: produkty, których moduł jeszcze nie zapisał (dowolne pole). **pendingField**: produkty jeszcze niezapisane dla tego konkretnego pola, więc kilka poleceń (na przykład description i name) może pracować na tych samych produktach. **emptyField**: tylko produkty, w których wybrane pole jest puste. Każde uruchomienie pomija produkty, które już nie pasują, więc gotowy katalog przestaje się zmieniać. |
| **Kategorie produktów** | Nic nie zaznaczono | Ogranicza uruchomienie do zaznaczonych kategorii. Puste drzewo oznacza, że kategoria nie jest filtrem. |
| **Lista ID produktów** | Pusty | Ogranicza uruchomienie do tych numerów produktów, oddzielonych przecinkami. Litery i inne znaki są usuwane przy zapisie. |
| **Język** | Domyślny język sklepu | Wersja językowa, która jest pisana. Inne języki wymagają własnego polecenia. |
| **Produkty do aktualizacji** | 5 produktów | Ile pasujących produktów przetwarza jedno wywołanie (2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 lub 1000). Zacznij od 5 lub 10, aby wolny model nie przekroczył limitu czasu serwera. |
| **Szablon promptu** | Pierwszy szablon na liście | Zapisana instrukcja używana dla każdego produktu w uruchomieniu. Zmienne są wypełniane dla każdego produktu. Wybierz włączony szablon. |
| **Włącz debugowanie** | Nie | Gdy adres jest otwarty z włączonym debugowaniem, wypisuje plan (ustawienia, wybrane produkty, końcowe prompty) i niczego nie zapisuje. Sprawdź tak polecenie raz. Wyłącz przed użyciem adresu przez harmonogram. |
| **Interwał zadania cron** | Co godzinę | Rytm, który planujesz (co 1, 2, 5, 10 lub 30 minut, co godzinę, co 2 lub co 6 godzin). Dokumentuje Twój plan. Moduł nie uruchamia harmonogramu. |
| **Polecenie zadania cron produktów** | – | Pokazuje wiersz polecenia do skopiowania do harmonogramu. Najpierw zapisz formularz. |

Formularz kategorii **CRON JOB Settings – Generate category content using OpenAI**. Ma własny sekret i własny przycisk **Zapisz**, a nie potrzebuje własnego przełącznika włączenia:

| Pole | Na starcie | Co robi |
|---|---|---|
| **Tajny token zadania cron** | Długa losowa wartość | Hasło adresu kategorii. Jest oddzielne od sekretu produktów. Zmiana unieważnia stary adres kategorii. |
| **Pole do aktualizacji** | description | Jedno zapisywane pole kategorii: name, description, meta_title lub meta_description. |
| **Wybrane kategorie** | pendingOpenAI | Te same trzy reguły co dla produktów, zastosowane do kategorii. **pendingField** pozwala kilku poleceniom dzielić te same kategorie. |
| **Język** | Domyślny język sklepu | Wersja językowa, która jest pisana. |
| **Kategorie do aktualizacji** | 5 kategorii | Ile kategorii przetwarza jedno wywołanie (od 2 do 1000). |
| **Szablon promptu** | Pierwszy szablon na liście | Napisz szablon dla kategorii, a nie produktu, na przykład ze zmienną `{category_name}`. |
| **Włącz debugowanie** | Nie | Wypisuje plan i nie zapisuje kategorii. |
| **Interwał zadania cron** | Co godzinę | Rytm, który planujesz. |
| **Polecenie zadania cron kategorii** | – | Wiersz polecenia do skopiowania po zapisaniu. |

Cron kategorii nigdy nie dotyka **Strony głównej** ani kategorii głównej.

### 3.11 Historia

Otwórz **Historia**. Historia to dziennik tego, o co zapytano i co wróciło. Otwarcie lub filtrowanie strony niczego nie usuwa i nie zmienia żadnego produktu.

![Historia (History)](https://mypresta.eu/docs/images/docs/mychatgpt-history.webp)

Pasek filtrów otwiera się na **W tym miesiącu**. Użyj przycisków okresu **Dziś**, **7 dni**, **30 dni**, **W tym miesiącu** i **Cały czas** albo **Od** i **Do**. Możesz też zawęzić według **Model**, **Typ**, **Status** (**Dowolny**, **Sukces**, **Błąd**), **Język**, **Pracownik**, **ID produktu / kategorii** i **Monit lub odpowiedź zawiera**. Kliknij **Filtruj**.

- Karty pokazują **Żądania**, **Sukces**, **Błędy**, **Wysłane tokeny**, **Odebrane tokeny**, **Wszystkie tokeny** i **Średni czas** dla filtra. Myślnik oznacza, że OpenAI nie zwróciło liczby tokenów dla tego wywołania.
- Panele **Wg dnia**, **Wg modelu**, **Wg typu**, **Wg języka** i **Wg pracownika** grupują te same wiersze według **Grupa**, **Wywołania**, **Wysłano**, **Odebrano** i **Suma**. Mała kursywna liczba obok wywołań to liczba błędów.
- Lista **Historia promptów** ma kolumny **ID**, **Status**, **Prompt**, **Odpowiedź / Błąd**, **Dostawca** (model, kod błędu, sekundy), **Wysłano**, **Odebrano**, **Suma**, **ID obiektu**, **Typ** i **Sygnatura czasowa**. Prompt i odpowiedź są skrócone. Kliknij **Zobacz** w wierszu, aby przeczytać pełny prompt i pełną odpowiedź z tokenami, potem **Wróć do listy**. Wiersz błędu pokazuje tekst błędu zamiast odpowiedzi. **Typ** pokazuje, co zostało zapisane, na przykład product_description lub category_meta_title. Symulacje i piaskownica też tworzą wiersze.
- Przycisk **Wyczyść listę** usuwa każdy wiersz naraz, bez pytania, także wiersze spoza Twojego filtra. Potem liczniki **Panelu**, filtr **Aktualizuj tylko**, reguła **pendingOpenAI** i licznik miesięcznego budżetu zaczynają od zera, a **Przywróć** nie jest już możliwe dla starych tekstów.

### 3.12 Obrazy

Otwórz **Obrazy**. Ta strona nie pobiera zdjęć. Włącza lub wyłącza wyszukiwanie obrazów na stronie produktu i zapisuje instrukcję używaną do tego wyszukiwania.

![Obrazy (Images)](https://mypresta.eu/docs/images/docs/mychatgpt-images.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Wyszukiwarka obrazów AI** | Włączony | **Włączony** pokazuje zakładkę **Zdjęcia** na stronie edycji produktu. **Wyłączony** ją usuwa. Obraz jest importowany dopiero po potwierdzeniu przez osobę. |
| **Prompt wyszukiwania obrazów AI** | Ten sam długi tekst domyślny co w **Ogólne** | Instrukcja wysyłana, gdy ktoś szuka. `{product_name}` i `{product_description}` są zastępowane bieżącym produktem. Zachowaj prośbę o prostą listę adresów stron. |

Kliknij **Zapisz**. Zobaczysz „Ustawienia zapisane.”. Wyszukiwanie stron i import zdjęć opisuje sekcja 3.13.

### 3.13 Edycja produktu (zakładka Moduły)

Otwórz **Katalog**, **Produkty**, edytuj produkt i otwórz zakładkę **Moduły**. Panel **Mój ChatGPT** ma zakładki **Generuj**, **Symuluj**, **Zdjęcia** i **Historia**. Jeśli **Formularz strony edycji produktu** jest wyłączony, zostaje tylko **Historia**. Jeśli wyłączona jest także **Historia edycji produktu**, nic się nie pojawia. Zapisz nowy produkt raz przed generowaniem, aby miał numer.

![Edycja produktu (Product edit)](https://mypresta.eu/docs/images/docs/mychatgpt-product-edit.webp)

**Generuj** zapisuje jedno pole i od razu zapisuje je w produkcie.

1. Wybierz chip **Język** albo **Każdy język**.
2. W **Jeśli pole już zawiera tekst** wybierz **Zastąp**, **Dodaj powyżej**, **Dodaj poniżej** lub **Pomiń, jeśli wypełnione**.
3. Kliknij **Wypełnij** na karcie pola: **Opis** (długi tekst z krótkim wstępem i listą cech), **Krótki opis** (zwykłe podsumowanie, poniżej około 400 znaków), **Nazwa**, **Meta tytuł** (około 70 znaków), **Meta opis** (około 160 znaków) lub **Tagi** (słowa oddzielone przecinkami).
4. **Pakiet SEO** z **Wypełnij wszystko** zapisuje nazwę, oba opisy i oba pola meta za jednym razem. Zastępuje te pola niezależnie od wyboru w **Jeśli pole już zawiera tekst**.
5. Opcjonalnie: otwórz **Użyj własnej instrukcji lub zapisanego monitu**. Wpisz w **Filtruj według tytułu lub tekstu**, wybierz **Standardowy brief** (gotowy brief dla pola, które naciskasz) albo włączony szablon, albo wpisz własną **Instrukcję**.

Pod przyciskami widzisz wysłaną instrukcję i odpowiedź oraz „Content successfully generated and updated to product.”. Formularz produktu na ekranie nie jest odświeżany. Przeładuj stronę produktu, zanim znów zaczniesz edytować. Jeśli naciśniesz **Zapisz** na starym formularzu, PrestaShop zapisze z powrotem stary tekst. Moduł skraca długie odpowiedzi do rozmiaru pola: nazwa 128 znaków, krótki opis 800, meta tytuł 69, meta opis 159.

**Symuluj** ma te same opcje i przyciski **Wypróbuj**. Pokazuje odpowiedź na stronie i nie zmienia produktu. Próba jest zapisywana w Historii.

**Zdjęcia** (wymaga włączonej **Wyszukiwarki obrazów AI**):

1. Kliknij **Znajdź strony**. Model proponuje strony, które prawdopodobnie pokazują ten produkt.
2. Kliknij adres strony. Sklep czyta stronę (adresy sieci prywatnych lub lokalnych są odrzucane) i wyświetla do 24 obrazów. Małe ikony i piksele śledzące są pomijane.
3. Zaznacz zdjęcia, które chcesz. Pierwsze zaznaczone zdjęcie zostaje okładką produktu i zastępuje bieżącą okładkę. Pozostałe są dodawane po istniejących zdjęciach.
4. Kliknij **Dodaj wybrane do tego produktu**. Przed tym kliknięciem nic nie jest zapisywane. Przeładuj produkt, aby zobaczyć zdjęcia.

Wyszukiwania zdjęć nie są zapisywane w Historii i nie liczą się do budżetu. Szanuj prawa autorskie do importowanych zdjęć.

**Historia** wymienia wcześniejsze zapisy dla tego produktu z kolumnami **Kiedy**, **Typ** i **Status**. **Przywróć** przywraca poprzedni tekst po potwierdzeniu „Restore the previous value?”. Zobaczysz „Content successfully restored. Refresh this page to see changes.”. Historia całego sklepu nie jest usuwana.

Obok pól opisu, krótkiego opisu, meta tytułu i meta opisu (w każdym formularzu produktu) widzisz też mały okrągły przycisk z logo OpenAI **Generuj z AI**. Kliknij go. Jeśli sklep ma więcej niż jeden język, wybierz **Bieżący język**, **Wszystkie języki** lub **Anuluj**. Pole otrzymuje gotowy brief dla tego pola, a tekst trafia tylko do pola formularza, z komunikatem „Tekst znajduje się w polu. Zapisz produkt, aby go zachować.”. Kliknij **Zapisz** na produkcie, aby go zachować. Ten przycisk nie używa szablonów ani pola **Instrukcja**.

### 3.14 Aktualizacje

Otwórz **Aktualizacje** (po prawej stronie górnego menu). Formularz **Aktualizacje MyPresta** sprawdza w MyPresta.eu, czy jest nowszy plik modułu. Nie zmienia katalogu i niczego nie instaluje.

![Aktualizacje (Updates)](https://mypresta.eu/docs/images/docs/mychatgpt-updates.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Sprawdzanie ręczne** | – | Kliknij **Sprawdź teraz**. Sklep jednorazowo pyta serwer aktualizacji MyPresta.eu i pokazuje obok przycisku „Moduł jest aktualny!” lub „Dostępna nowa wersja!”. |
| **Powiadomienia automatyczne** | Włączony | **Włączony** pozwala zapleczu sprawdzać mniej więcej co trzy dni i pokazywać ostrzeżenie z linkiem, gdy istnieje nowsza wersja. **Wyłączony** to zatrzymuje. |
| **Strona produktu** | – | Link do strony modułu w MyPresta.eu. |

Kliknij **Zapisz**, aby zapisać wybór powiadomień. Zobaczysz „Ustawienia aktualizacji zapisane.”. Numer wersji obok nazwy modułu w menu to wersja zainstalowana w Twoim sklepie, a nie najnowsza.

## 4. Front sklepu

Moduł niczego nie pokazuje Twoim klientom. Nie dodaje do witryny sklepu żadnego bloku, strony, skryptu ani stylu. Motyw nie ma czego nadpisywać. Wszystko, co widzisz, jest w zapleczu: przycisk **Mój ChatGPT** na górnym pasku, ekrany modułu i panel na stronie produktu.

Moduł ma dwa adresy internetowe, które istnieją tylko dla serwerów i dla zaplecza:

- **Adres cron**. Skopiuj go z **Cron** (sekcja 3.10) i wklej tylko do harmonogramu na serwerze. Każdy, kto zna pełny adres z sekretem, może uruchomić partię, więc nigdy go nie publikuj i nie wklejaj do czatów ani zgłoszeń.
- Adres techniczny, z którego korzystają przyciski zaplecza przy każdym generowaniu. Nie otwieraj go i nie udostępniaj.

Otwarcie adresu cron w przeglądarce pokazuje zwykły tekst. Oto komunikaty, które możesz przeczytać:

| Co widzisz | Co zrobić |
|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | Otwórz **Cron**, ustaw **Włącz funkcję cron** na **Tak** i kliknij **Zapisz**. |
| The token does not exist or it’s wrong! | Sekretu brakuje albo nie pasuje. Po zapisaniu skopiuj adres ponownie z **Cron**. |
| Invalid action! | Adres nie ma części z zadaniem. Dodaj ustawienia wymienione w sekcji 6.3. |
| updatedField parameter is wrong! | Nazwa pola w adresie nie jest jednym z dozwolonych pól. Użyj pola z listy **Pole do aktualizacji**. |
| All must include all mandatory parameters! | W adresie brakuje pola, reguły wyboru, wielkości partii, języka lub szablonu. Dodaj je (sekcja 6.3). |
| productTarget parameter is wrong! Allowed values: … (lub categoryTarget) | Użyj pendingOpenAI, pendingField lub emptyField. |
| No valid product IDs provided. | **Lista ID produktów** nie zawiera użytecznych numerów. Popraw lub wyczyść listę. |
| No products to update. / No categories to update. | Nic już nie pasuje do reguły. Zadanie jest skończone albo zmień **Wybrane produkty** lub filtry. |
| N products have been updated. / N categories have been updated. | Jedna partia została zapisana. Następne wywołanie kontynuuje od kolejnych elementów. |
| N pending products. | Debugowanie jest włączone. Nic nie zapisano. Wyłącz debugowanie przy prawdziwych uruchomieniach. |
| Error!Monthly generation budget reached. | Podnieś **Miesięczny budżet generowania** albo poczekaj do następnego miesiąca. |
| Error!Reply rejected by the studio quality gate. | Odpowiedź zawierała zabronione słowo. Zmień **Zabronione słowa** albo wyłącz **Bramkę jakości**. |
| Error! The model returned an empty response. | Zwiększ **Maksymalną liczbę tokenów**, spróbuj innego modelu lub szablonu. |
| Error! po którym następuje komunikat OpenAI | Przeczytaj komunikat. Typowe przyczyny to zły klucz, brak środków lub nieznany model. |
| Error! Could not save product … (N product(s) updated before this one.) | PrestaShop odrzucił tekst dla tego elementu. Sprawdź produkt, potem uruchom ponownie. |

## 5. Problemy

### 5.1 Połączenie i ustawienia

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| „The OpenAI API key is not set. Add it in the module settings.” lub „The ChatGPT API key is not set. Add it in the module settings.” | Nie zapisano klucza. | Otwórz **Ustawienia**, **ChatGPT**, wklej klucz w **Klucz API OpenAI** i kliknij **Zapisz**. |
| „Pole Klucz API OpenAI jest nieprawidłowe!” | Zapisano nowy klucz krótszy niż 10 znaków, gdy nie było zapisanego klucza. | Wklej pełny klucz. |
| „Pole Model OpenAI jest nieprawidłowe!” | **Model** ma mniej niż 3 znaki. | Wybierz model z listy i zapisz ponownie. |
| Komunikat od OpenAI o błędnym kluczu, limicie lub modelu, który nie istnieje | OpenAI odrzuciło wywołanie. Moduł pokazuje własny tekst OpenAI. | Sprawdź klucz, rozliczenia w OpenAI i nazwę modelu w **Ustawienia**, **ChatGPT**. Dodany model musi być dostępny dla Twojego konta. |
| „Error! Invalid token!” | Strona została otwarta, zanim moduł odnowił swój wewnętrzny sekret, albo była otwarta bardzo długo. | Przeładuj stronę i spróbuj ponownie. |
| „OpenAI request timed out after N seconds. The model may be overloaded, or the timeout is too low for this prompt.” | OpenAI odpowiedziało zbyt wolno. | Podnieś **Limit czasu API (sekundy)** w **Ustawienia**, **Ogólne** (do 600), użyj szybszego modelu lub poproś o krótszy tekst. |
| „The model hit the token limit before returning any text. Increase "Max Tokens" in the module settings – reasoning models spend part of that budget on thinking.” | **Maksymalna liczba tokenów** jest za niska dla tego modelu. | Podnieś **Maksymalną liczbę tokenów** w **Ustawienia**, **ChatGPT**. |
| „The response was blocked by the provider content filter. Try rewording the prompt.” | Filtr OpenAI zatrzymał odpowiedź. | Zmień sformułowanie promptu lub danych produktu, których używa. |
| „The model returned an empty response.” | Model nie zwrócił tekstu. | Spróbuj ponownie, użyj innego modelu lub mniej rygorystycznego promptu. |
| „Monthly generation budget reached. Raise it in the studio settings or wait until next month.” | Liczba udanych generowań osiągnęła **Miesięczny budżet generowania**. | Podnieś liczbę w **Ustawienia**, **Studio**, ustaw 0 albo poczekaj do następnego miesiąca. Wyczyszczenie **Historii** także zeruje licznik. |
| „The reply was rejected because it contains a forbidden word from the studio settings.” | Wiersz z **Zabronionych słów** występuje w odpowiedzi, także wewnątrz dłuższego słowa. | Skróć lub edytuj listę albo ustaw **Bramkę jakości** na **Nie**. Nic nie zapisano w produkcie. |

### 5.2 Strona produktu i wyniki generowania

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| Panelu **Mój ChatGPT** nie ma na stronie produktu. | **Formularz strony edycji produktu** i **Historia edycji produktu** są oba wyłączone albo nie jesteś w zakładce **Moduły**. | Włącz przełączniki w **Ustawienia**, **Ogólne**, potem otwórz zakładkę **Moduły**. |
| „Zapisz produkt raz przed generowaniem.” | Produkt nie ma jeszcze numeru. | Zapisz produkt, potem generuj. |
| Nowy tekst zniknął po zapisaniu produktu. | Formularz produktu na ekranie nadal zawierał stary tekst. | Po **Wypełnij** przeładuj stronę produktu, zanim zaczniesz edytować i zapisywać. |
| „Product skipped.” lub „Category skipped.” | **Pomiń, jeśli wypełnione** znalazło tekst w polu. To nie jest błąd. | Wybierz **Zastąp**, **Dodaj powyżej** lub **Dodaj poniżej**, jeśli mimo to chcesz zapisać. |
| „Error! Content retrieve has failed! Details: …” | OpenAI lub serwer zwrócił błąd. | Przeczytaj szczegóły po „Details:”. Otwórz **Historię**, ustaw filtr **Status** na **Błąd** i otwórz wiersz. |
| „Error! The generated content could not be saved to the product.” lub „… to the category.” | PrestaShop odrzucił tekst, na przykład z powodu niedozwolonego znaku. | Przeczytaj powód po zdaniu. Spróbuj innego promptu lub krótszego pola. |
| „Error! Prompt is missing or too short!” | Instrukcja ma mniej niż 4 znaki. | Napisz dłuższą instrukcję albo zostaw pole puste, aby użyć standardowego briefu. |
| „Error! Product not found!” / „Error! Category not found!” | Element został usunięty albo numer jest zły. | Zbuduj listę ponownie i uruchom jeszcze raz. |
| „Error! This log entry has no previous value to restore.” lub „Error! Nothing to restore for this entry.” | Ten wiersz Historii nie ma starego tekstu. | Użyj innego wiersza. Wiersze zapisane przez **Symuluj** i błędy nie mogą przywrócić niczego użytecznego. |
| „The model did not return a usable SEO pack.” | Odpowiedź nie miała oczekiwanego formatu. | Kliknij **Wypełnij wszystko** ponownie albo wypełniaj pola po jednym. |
| „Generowanie nie powiodło się.” przy przycisku **Generuj z AI** | Wywołanie się nie powiodło. | Spróbuj ponownie. Powód znajdziesz w **Historii**. |
| „Error! This PrestaShop version does not support the category Additional Description field.” | Twój sklep nie ma takiego pola kategorii. | Wybierz inne pole kategorii. |

### 5.3 Generowanie masowe

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| Tabela po **Przejdź do następnego kroku** jest pusta. | Filtry nic nie pasują. | Poluzuj filtry. Sprawdź **Status produktu**, **Stan magazynowy produktu** i **Aktualizuj tylko**. |
| „Select at least one language.” | Nie zaznaczono żadnego języka. | Zaznacz co najmniej jeden język. |
| Uruchomienie zatrzymało się w środku. | Karta została zamknięta, połączenie spadło albo serwer się zatrzymał. | Zbuduj listę ponownie z opcją **Aktualizuj tylko** ustawioną na produkty, które nie zostały zaktualizowane, i uruchom jeszcze raz. |
| Wiele wierszy pokazuje błędy. | Problem z budżetem, kluczem lub limitem czasu. | Otwórz **Historię**, przeczytaj pierwszy błąd, napraw go i uruchom ponownie. |
| Strona główna i kategoria główna są na liście kategorii. | Pole **Kategorie** zostało puste. | Zaznacz kategorie, które chcesz, przed **Przejdź do następnego kroku**. |

### 5.4 Cron

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| Nic się nie zmienia w katalogu. | **Włącz funkcję cron** jest wyłączone, harmonogram nie wywołuje adresu albo żaden element nie pasuje do reguły. | Sprawdź przełącznik, dziennik harmonogramu i **Wybrane produkty**. Otwórz raz adres z włączonym debugowaniem, aby zobaczyć plan. |
| Adres odpowiada komunikatem z tabeli w sekcji 4. | Zobacz tę tabelę. | Zrób to, co mówi tabela. |
| Te same produkty są zapisywane w kółko. | **Wybrane produkty** to **emptyField** i pole zostaje puste albo użyto **pendingOpenAI**, a Historia została wyczyszczona. | Użyj **pendingField** albo popraw prompt, aby tekst był zapisywany. |
| Stary adres przestał działać. | Moduł zastępuje sekrety krótsze niż 24 znaki, sekret został zmieniony albo moduł zainstalowano ponownie. | Skopiuj adres ponownie z **Cron** i zaktualizuj harmonogram. |
| **Generuj token** nic nie robi. | Przycisk nie ma funkcji w tej wersji. | Zachowaj sekret utworzony przy instalacji. |

### 5.5 Obrazy, nowy produkt i menu

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| Brakuje zakładki **Zdjęcia**. | **Wyszukiwarka obrazów AI** jest wyłączona. | Włącz ją w **Ustawienia**, **Ogólne** lub **Obrazy**, potem przeładuj produkt. |
| „No pages were suggested.” lub „The search failed.” | Model nie zwrócił użytecznych adresów albo klucz ma problem. | Kliknij **Znajdź strony** ponownie albo sprawdź **Prompt wyszukiwania obrazów AI**. |
| „That page could not be read.”, „URL not allowed (private network)” lub błąd zaczynający się od HTTP | Strona blokuje sklep, wymaga logowania albo jest w sieci prywatnej. | Wybierz inną stronę. |
| „No photos were found on that page.” | Strona nie ma użytecznych obrazów. | Wybierz inną stronę. |
| „No images could be imported. Details: …” | Obrazów nie udało się pobrać albo nie są prawdziwymi obrazami. | Przeczytaj szczegóły. Wybierz inne zdjęcia. |
| „Failed to parse AI response. Please try again.” w **Nowy produkt** | Odpowiedź nie miała oczekiwanego formatu. | Kliknij **Generuj dane** ponownie. |
| „Error creating product: …” lub „Failed to create product” | PrestaShop odrzucił produkt, często dlatego, że wybrany **Język** nie jest domyślnym językiem sklepu. | Wybierz język domyślny i sprawdź numer kategorii. |
| „Generate the product first.” | Kliknięto **Utwórz produkt** przed **Generuj dane**. | Najpierw kliknij **Generuj dane**. |
| Brakuje pozycji menu **Generator treści AI**. | Moduł jest wyłączony albo pozycja została przeniesiona. | Włącz moduł w **Menedżerze modułów** i raz otwórz dowolną stronę zaplecza. Moduł przywróci pozycję w **Moduły**. Jeśli nadal jej brak, sprawdź, czy Twój profil pracownika może otwierać **Moduły**. |
| Panel i Historia są puste. | W wybranym okresie nic nie wygenerowano albo użyto **Wyczyść listę**. | Wybierz **Cały czas**. |

## 6. Dla developera

### 6.1 Przegląd

| Pozycja | Wartość |
|---|---|
| Nazwa techniczna | mychatgpt |
| Wersja | 1.1.0 |
| Nazwa na liście modułów | My ChatGPT - AI content generation |
| Autor | MyPresta.eu |
| Zakładka modułu | front_office_features |
| PrestaShop | 1.6 – 9.99.99 |
| Minimalne PHP | 7.0.0 (sprawdzane w `install()`) |
| Klasa główna | `mychatgpt extends Module`, z klasami pomocniczymi `mychatgptUpdate` i `searchToolmychatgpt`, które ją rozszerzają |

Przepływ danych: JavaScript zaplecza wywołuje kontroler frontowy `ajax` z `secret_token` (odczytywanym z `MYPRESTA_MYCHATGPT_TOKEN`) albo kontroler admina. Kontroler odczytuje klucze modelu i próbkowania, stosuje Studio (`MyChatGPT\Studio`), wywołuje OpenAI przez `MyChatGPT\OpenAIService` (cURL do punktu chat completions API OpenAI), zapisuje tekst modelem obiektowym PrestaShop i wstawia wiersz do `mychatgpt_log`. `cron` robi to samo bez przeglądarki. `getServiceName()` zawsze zwraca `openai`. Pozostały kod dla innych dostawców został usunięty. Klucze ustawień wcześniejszego drugiego dostawcy (`_GEMINI_API_KEY`, `_GEMINI_MODEL`, `_ACTIVE_SERVICE`) są usuwane przy każdym otwarciu ekranu ustawień.

### 6.2 Pliki

| Ścieżka | Przeznaczenie |
|---|---|
| `mychatgpt.php` | Klasa główna: instalacja i odinstalowanie, zakładki, formularze ustawień, szablony promptów, panel, hooki, zakładka produktu, katalog modeli. |
| `autoload.php` | Mały ładowacz klas dla przestrzeni nazw `MyChatGPT\` (bez Composera). |
| `src/OpenAIService.php` | Klient cURL dla chat completions i listy modeli. Limit czasu 10–600 s, pomija parametry odrzucane przez model (do 6 ponowień), wyłącza sprawdzanie certyfikatów tylko na localhost. |
| `src/Studio.php` | Sprawdzanie budżetu, dekorowanie promptu (język, głos, odbiorcy, ton, słownik, zabronione), kontrola odpowiedzi, pakiet SEO i prompty tekstów alternatywnych. |
| `controllers/admin/*.php` | Siedem kontrolerów admina (sekcja 6.3). |
| `controllers/front/ajax.php` | Punkt JSON dla całego generowania uruchamianego z przeglądarki. |
| `controllers/front/cron.php` | Punkt cron zwracający zwykły tekst. |
| `lib/updateChecker.php` | Sprawdzanie aktualizacji w dev.mypresta.eu co 3 dni i formularz Aktualizacje. |
| `lib/sectionHelp.php` | Teksty szuflady Pomocy. |
| `lib/searchTool/` | Klasa pomocnicza `searchToolmychatgpt` (narzędzie autouzupełniania na ekranach modułu). |
| `lib/prestashop9compatibility.php` | Opakowania dla wyświetlania cen, haszowania i przekierowań w PrestaShop 9. |
| `views/templates/hook/*.tpl` | Ekrany i panele modułu (panel, nawigacja, podnawigacja, generatory masowe, zakładka produktu, historia, informacje o cronie, okno na górnym pasku). |
| `views/templates/admin/product_creator.tpl` | Ekran nowego produktu. |
| `views/js/back.js` | Uruchomienia masowe, panel produktu, piaskownica, okno górnego paska, nowy produkt, przywracanie. |
| `views/js/product-fields.js` | Przyciski **Generuj z AI** obok pól produktu. |
| `views/js/image-finder.js` | Zakładka **Zdjęcia**. |
| `views/js/admin-products-bulk.js` | Dodaje przycisk **Mój ChatGPT** do listy produktów. |
| `views/js/dashboard.js`, `chart.min.js`, `admin-help.js` | Wykresy i szuflada Pomocy. |
| `views/css/admin-nav.css`, `back.css`, `stats.css` | Style. |
| `translations/*.php` | 34 pliki językowe. |
| `upgrade/index.php` | Tylko plik przekierowujący. Nie ma skryptów aktualizacji. |

Klasy `AdminMyChatGPTMain` i `AdminMyChatGPTSettings` wywołują `addJS`/`addCSS` dla `views/js/admin.js` i `views/css/admin.css`, a kontroler nowego produktu dla `product_creator.js` i `product_creator.css`. Żaden z tych plików nie jest dołączony. Formularz cron oczekuje funkcji JavaScript `generateTokenAndFill()` i `generateCategoryTokenAndFill()` i wypełnia elementy span `.cron-parameters`. Ten skrypt również nie jest dołączony.

### 6.3 Kontrolery

| Kontroler | Rodzic i trasa | Przeznaczenie |
|---|---|---|
| `AdminMyChatGPTMain` | Pod **Moduły**, widoczny. Przekierowuje do konfiguracji modułu, Panel. | Pozycja menu **Generator treści AI**. |
| `AdminMyChatGPTSettings` | Ukryta zakładka (`active = 0`). Przekierowuje do konfiguracji, Ustawienia. | Wpis zgodności. |
| `AdminMyChatGPT` (plik `AdminMyChatGPT.php`, klasa `AdminMyChatGPTController`) | Ukryta zakładka. `mcg_sub=products` lub `categories`. | Filtry i generatory masowe. `renderProductUpdateForm()` i formularz aktualizacji kategorii nie mają obsługi. Wysłania `generateProductContent` i `generateCategoryContent` tylko zapisują wartości formularza. Generowanie działa z `back.js`. |
| `AdminMyChatGPTProductCreator` | Ukryta zakładka. Akcje Ajax `generateProductData`, `createProduct`, `extractImages`, `generateImages` (zaślepka). | Nowy produkt. |
| `AdminMyChatGPTCron` | Ukryta zakładka. Formularze `submitCronUpdate`, `submitCatCronUpdate`. | Ustawienia cron. |
| `AdminMyChatGPTUsage` | Ukryta zakładka. Parametry `stats_*`, `view` i `clear_log`. | Historia. `clear_log` wykonuje `DELETE` na całej tabeli logu. |
| `AdminMyChatGPTImageFinder` | Ukryta zakładka. Akcje Ajax `searchImages`, `extractImages`, `saveImages`. | Formularz **Obrazy** i wyszukiwanie zdjęć. |

Wszystkie kontrolery admina przekierowują na ekran główny, jeśli moduł jest nieaktywny. Strona konfiguracji modułu (`getContent`) renderuje Panel, Ustawienia (`mcg_tab=settings`, `mcg_sub` general, openai, studio, templates, playground) i Aktualizacje (`mcg_tab=updates`).

Kontroler frontowy `ajax` (`secret_token` musi być równy `_TOKEN`; nie ma sprawdzania pracownika). Akcje: `initiatePrompt`, `updateSettings` (zapisuje max tokens, temperature, top p i obie kary), `updateProduct`, `updateCategory`, `initiateProductRestore`, `generateAltTexts` (żaden przycisk go nie używa; najwyżej 8 obrazów), `generateSeoPack`. `updateProduct` i `updateCategory` przyjmują `target` (pole), `behavior` (`replace`, `keep`, `keep_top`, `keep_end` lub `single_product` dla podglądu, który nie jest zapisywany), `prompt`, język i numer elementu. Odpowiedzi to JSON z `status` (`success`, `error`, `skipped`), `msg` i `date`.

Kontroler frontowy `cron`: odmawia z komunikatem „disabled”, gdy `_ENABLE_CRON` wynosi 0. Parametr `secret` musi być równy `_SECRET` lub `_CAT_SECRET` (każdy z sekretów otwiera oba zadania). Parametry:

| Parametr | Używany przez | Znaczenie |
|---|---|---|
| `secret` | oba | Sekret produktów lub kategorii. |
| `action` | oba | `generateProductContent` lub `generateCategoryContent`. |
| `updatedField` | oba | Produkty: name, description, description_short, meta_title, meta_description, tags. Kategorie: name, description, meta_title, meta_description, additional_description. |
| `productTarget` / `categoryTarget` | każdy | `pendingOpenAI`, `pendingField`, `emptyField`. |
| `productsToUpdate` / `categoriesToUpdate` | każdy | Wielkość partii (`LIMIT`). |
| `languageId` | oba | Numer języka. |
| `promptTemplateId` | oba | Numer szablonu z `mychatgpt_prompt`. |
| `debug` | oba | Dowolna wartość poza 0 wypisuje plan i niczego nie zapisuje. |
| `categories` | produkty | Numery kategorii oddzielone przecinkami. |
| `productIds` | produkty | Numery produktów oddzielone przecinkami. |

Przykład (użyj `YOUR_SECURE_KEY` tylko jako zmiennej zastępczej):

```text
https://your-shop.example/module/mychatgpt/cron?secret=YOUR_SECURE_KEY&action=generateProductContent&updatedField=description&productTarget=pendingField&productsToUpdate=5&languageId=1&promptTemplateId=3&debug=1
```

`pendingOpenAI` i `pendingField` sprawdzają udane wiersze `mychatgpt_log` (wiersze ze statusem error są ignorowane, więc nieudane elementy są ponawiane). Zadanie kategorii pomija kategorie o numerze do kategorii głównej sklepu włącznie.

### 6.4 Hooki

Zarejestrowane w `install()`:

| Hook | Zachowanie |
|---|---|
| `displayAdminProductsExtra` | Renderuje panel zakładki **Moduły** (`product-tab-wrapper.tpl`), gdy `_PRODUCT` lub `_PRODUCT_LOG` wynosi 1. |
| `displayBackOfficeHeader` | Ładuje zasoby; uruchamia `ensureLongSecrets()` (zastępuje `_TOKEN`, `_SECRET`, `_CAT_SECRET` krótsze niż 24 znaki) i `placeModuleMenu()`; raz rejestruje zakładkę **Wyszukiwarka obrazów AI** (`_IMAGEFINDER_TAB_OK`); kolejkuje `product-fields.js`, `admin-products-bulk.js` i `image-finder.js` na `AdminProducts`; ponownie rejestruje `dashboardZoneTwo`, jeśli go brakuje. `product-fields.js` jest kolejkowany na każdej stronie produktu, niezależnie od `_PRODUCT`. |
| `displayBackOfficeTop` | Definiuje wartości JavaScript (`admin_controller_url`, `idcms`, `idcategory`, `idmanufacturer`) i renderuje okno górnego paska, gdy `_TOPCTA` wynosi 1. |
| `dashboardZoneTwo` | Renderuje `dashboard.tpl`, który odczytuje zmienne `mcg_*`, których ten hook nie przypisuje. |
| `displayAdminProductsMainStepLeftColumnMiddle` | Pusta zaślepka, zwraca pusty ciąg. |
| `displayAdminProductsMainStepLeftColumnBottom` | Pusta zaślepka, zwraca pusty ciąg. |
| `actionProductFormBuilderModifier` | Brak działania, nic nie zwraca. |
| `displayHeader` | Pusta zaślepka. |
| `displayFooter` | Pusta zaślepka. |

Metoda `hookActionProductGridDataModifier` istnieje, ale nie jest zarejestrowana. Moduł nie ma nadpisania `enable()` ani `disable()` i nie udostępnia własnych hooków.

### 6.5 Nadpisania

Moduł nie ma nadpisań.

### 6.6 Baza

| Tabela | Zawartość |
|---|---|
| `mychatgpt_prompt` | `id_prompt`, `status` (0/1), `title` (128), `prompt` (text), `date_generated`. Zasilona 16 wierszami. |
| `mychatgpt_log` | `id_log`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, pary `old_*` i `new_*` dla name, description, description_short, meta_title, meta_description i tags, `date_updated`. Klucze na `id_product` i `status`. |

Odinstalowanie usuwa obie tabele. `ensureUsageColumns()` dodaje trzy kolumny tokenów przy otwarciu ekranu, jeśli starszej tabeli ich brakuje. Wiersze produktów, kategorii i obrazów zapisane przez moduł to standardowe dane PrestaShop i nie są ruszane przy odinstalowaniu.

### 6.7 Klucze i tłumaczenia

Klucze mają przedrostek `MYPRESTA_MYCHATGPT_`. Wartości ustawiane przy instalacji:

| Klucz | Wartość domyślna |
|---|---|
| `_LIVE_MODE`, `_DEBUG_MODE` | 0 |
| `_TOPCTA`, `_PRODUCT`, `_PRODUCT_LOG` | 1 |
| `_TOKEN`, `_SECRET`, `_CAT_SECRET` | Losowe 32 znaki |
| `_API_KEY` | Jedna spacja |
| `_MODEL` | gpt-3.5-turbo |
| `_EXTRA_MODELS`, `_MODEL_CAPS` | Puste (drugi jest wypełniany w czasie działania odrzuconymi parametrami dla każdego modelu) |
| `_TEMPERATURE`, `_TOP_P` | 0.7, 1 |
| `_MAX_TOKENS`, `_TIMEOUT` | 3200, 120 |
| `_FREQ_PEN`, `_PRES_PEN` | 0 |
| `_VOICE`, `_AUDIENCE`, `_TONE`, `_GLOSSARY`, `_FORBIDDEN` | Puste |
| `_BUDGET`, `_QUALITY` | 0, 1 |
| `_IMAGEFINDER_ENABLE`, `_IMAGEFINDER_PROMPT` | 1, długi prompt domyślny |
| `_ENABLE_CRON`, `_CRON_INTERVAL`, `_CAT_CRON_INTERVAL` | 0, 6, 6 |
| `updatedField`, `productTarget`, `productsToUpdate`, `promptTemplateId`, `languageId`, `interval_select`, `debug`, `productIdsList` | description, pendingOpenAI, 5, puste, język domyślny, puste, 0, puste |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catpromptTemplateId`, `catlanguageId`, `catdebug` | description, pendingOpenAI, 5, puste, język domyślny, 0 |
| `PS_USE_HTMLPURIFIER` | Ustawione na 0 (w całym sklepie) |

Klucze cron bez przedrostka (`updatedField`, `debug` i pozostałe wyżej) to nazwy globalne i mogą kolidować z innymi modułami.

Tworzone później: `_IMAGEFINDER_TAB_OK`, `categories` (wybór kategorii cron), `mypresta_updates`, `update_mychatgpt`, `updatev_mychatgpt`. `AdminMyChatGPT::postProcess()` zapisuje też każde pole filtra (`_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_IDS`, `_PROD_REF`, `_PROD_DATE_FROM`, `_PROD_DATE_TO`, `_PROD_MIN_ID`, `_PROD_MAX_ID`, `_PROD_LIMIT`, `_CATEGORIES`, `_BRANDS`) w konfiguracji przy każdym żądaniu tego kontrolera, ale nic ich nie odczytuje.

Odinstalowanie usuwa klucze wymienione w `uninstall()`. Nie przywraca `PS_USE_HTMLPURIFIER`. Zostawia `categories`, wymienione wyżej klucze filtrów i klucze aktualizacji.

Generatory, cron i zwykła walidacja używają `Tools::getValue` z listami dozwolonych wartości. Klucz API jest przechowywany jako zwykły tekst w tabeli konfiguracji. `randomString()` używa `rand()`.

Tłumaczenia: dodaj `translations/{iso}.php` w standardowym formacie modułów PrestaShop (dołączono 34 języki). Teksty przechodzą przez `$this->l()` w klasie głównej, w narzędziu sprawdzającym aktualizacje i w szufladzie pomocy. W PrestaShop 8 i 9 kontrolery admina używają `trans()` z domenami `Admin.MyChatGPT`, `Admin.MyChatGPTCron` i `Admin.MyChatGPTUsage`. Nietłumaczone: komunikaty wewnątrz `back.js` i `image-finder.js`, domyślne instrukcje używane przez **Wypełnij** i **Generuj z AI**, wynik `cron` oraz teksty błędów `AdminMyChatGPTProductCreator` i `AdminMyChatGPTImageFinder`. Długie teksty pomocy („What it does / How to configure / Effect”) są budowane przez `fieldHelp()` i znajdują się w definicjach formularzy w `mychatgpt.php` i kontrolerów admina (metoda `help()`), w szablonach i w `lib/sectionHelp.php`. Nazwy domyślnych szablonów i nazwy menu są zapisywane w bazie w językach sklepu przy instalacji.

### 6.8 Rozszerzanie

- Dodawaj lub edytuj szablony promptów na ekranie modułu albo w `mychatgpt_prompt`.
- Dodawaj zmienne w konstruktorach promptów w `ajax.php` (`updateProduct`, `updateCategory`) i w `cron.php`.
- Dodawaj modele w **Ustawienia**, **ChatGPT** bez zmian w kodzie. Moduł sam uczy się nieobsługiwanych parametrów.
- Zmieniaj standardowe instrukcje dla **Wypełnij**, **Generuj z AI** i uruchomień masowych w `back.js` i `product-fields.js`.
- Front office nie ma szablonu, więc motyw nie ma czego nadpisywać. Szablony zaplecza w `views/templates` zmienia się w folderze modułu.

## 7. Pomoc

Strona produktu: https://mypresta.eu/modules/administration-tools/my-chatgpt.html

Aby napisać w sprawie modułu:

1. Zaloguj się na swoje konto klienta na mypresta.eu.
2. Otwórz stronę kontaktu.
3. Wybierz **Support for paid modules**.
4. Opisz problem. Podaj dokładny komunikat z ekranu i kroki, które do niego prowadzą. Nigdy nie wklejaj klucza API OpenAI ani pełnego adresu cron z sekretem.
