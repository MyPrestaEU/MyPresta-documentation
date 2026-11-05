---
title: "My AI Mistral - AI content generation - dokumentacja i instrukcja obsługi"
description: "Instrukcja konfiguracji, codziennej pracy i rozwiązywania problemów dla sprzedawców, którzy mają już moduł My AI Mistral zainstalowany w swoim sklepie PrestaShop."
sidebar:
  label: "My AI Mistral - AI content generation - dokumentacja i instrukcja obsługi"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Meta and catalog descriptions with Mistral AI na MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/meta-and-catalog-descriptions-with-mistral-ai.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ai-artificial-intelligence/meta-and-catalog-descriptions-with-mistral-ai/)
>
> ---


## 1. Wymagania

### 1.1 Sklep i serwer

| Element | Wymagane | Uwagi |
|---|---|---|
| PrestaShop | 1.6 do 9.x | Moduł deklaruje obsługę wersji od 1.6 do 9.99.99. Zakładka **My AI Mistral** na stronie edycji produktu oraz małe przyciski "Generate with AI" są przygotowane dla PrestaShop 1.7, 8 i 9. |
| PHP | 7.0 lub nowszy | Instalacja zatrzymuje się z komunikatem, jeśli serwer działa na starszym PHP. |
| Rozszerzenia PHP | cURL, JSON, mbstring, DOM | cURL służy do każdego połączenia z Mistral AI. DOM i mbstring służą do odczytu stron internetowych w wyszukiwarce zdjęć oraz do mierzenia i przycinania wygenerowanego tekstu. |
| Połączenie wychodzące | HTTPS (port 443) do `api.mistral.ai` | Serwer musi mieć zgodę na połączenia z API Mistral AI. Plany hostingowe blokujące połączenia wychodzące nie działają. |
| Adres frontu sklepu | Dostępny z przeglądarki | Przyciski w panelu administracyjnym wysyłają zapytania pod adres we froncie sklepu. Okno z hasłem, reguła zapory lub strona przerwy technicznej blokująca ten adres powoduje, że przyciski przestają działać. |

### 1.2 Konto Mistral AI

1. Załóż konto w konsoli Mistral AI i otwórz stronę z kluczami API: https://console.mistral.ai/api-keys/
2. Utwórz klucz i skopiuj go. Konsola pokazuje go tylko raz.
3. Upewnij się, że konto może korzystać z API (plan lub rozliczenia obejmujące dostęp do API). Każdy wygenerowany tekst to jedno zapytanie API, które jest płatne lub wlicza się do Twojego limitu.

Moduł nie wymaga żadnego innego modułu i nie dodaje żadnego override. Niczego nie pokazuje Twoim klientom.

### 1.3 Koszty i obciążenie

- Jedno wygenerowane pole w jednym języku to jedno zapytanie. Partia 40 produktów z opisami i metatagami w dwóch językach to 40 × 4 × 2 = 320 zapytań, ponieważ opcja opisów zapisuje dwa pola, a opcja metatagów też dwa pola.
- Każde zapytanie czeka na odpowiedź maksymalnie tyle, ile wynosi wartość w **API timeout (seconds)** (domyślnie 120 sekund). Duża partia uruchomiona z przeglądarki jest z natury wolna; przy dużych katalogach używaj crona.
- Moduł może przestać generować po osiągnięciu miesięcznej liczby udanych zapytań (**Monthly generation budget** w Studio).

## 2. Instalacja

### 2.1 Instalowanie modułu

1. Otwórz **Modules > Module Manager** (**Modules and Services** w PrestaShop 1.6).
2. Kliknij **Upload a module** (**Add a new module** w wersji 1.6) i wybierz plik ZIP modułu.
3. Kliknij **Install**, a potem **Configure**.

Co instalacja robi za Ciebie:

- Dodaje pozycję menu w panelu administracyjnym **AI Content Generator** w sekcji **Modules**. Otwiera ona stronę ustawień modułu, a wszystkie pozostałe ekrany są dostępne z paska menu u góry tej strony.
- Tworzy dwie tabele w bazie danych: jedną na szablony promptów i jedną na historię zapytań.
- Zapisuje 16 gotowych szablonów promptów (nazwy produktów, opisy, meta tytuły, meta opisy i tagi). Wszystkie są na początku włączone.
- Generuje tajne kody dla przycisków w panelu administracyjnym i dla crona oraz wybiera model **mistral-small-latest**.
- Nie czyści pamięci podręcznej PrestaShop. Jeśli pozycja menu się nie pojawi, wyczyść cache w **Advanced Parameters > Performance**.

Przy pierwszej wizycie możesz zobaczyć zielony komunikat "Mistral AI API Key has been automatically cleaned (whitespace removed)". Oznacza on tylko, że pusty klucz zastępczy został uporządkowany. Nic złego się nie dzieje.

### 2.2 Pierwsze kroki po instalacji

1. Otwórz **AI Content Generator > Settings > Mistral** i wklej swój klucz API.
2. Do pierwszego testu zostaw model domyślny i kliknij **Save**.
3. Otwórz **Settings > Playground**, wpisz jedno krótkie polecenie i kliknij **Generate**. Odpowiedź potwierdza, że połączenie działa.
4. Otwórz istniejący produkt, przejdź do zakładki **Modules**, wybierz **My AI Mistral**, otwórz **Simulate** i kliknij **Try** przy **Meta title**. Tekst zostanie wyświetlony, a nic nie zostanie zapisane.

### 2.3 Aktualizacja

Wgraj nowy plik ZIP w Module Manager tak samo jak przy pierwszej instalacji. Ustawienia, szablony i historia zostają zachowane. Strona **Updates** w module informuje, czy dostępna jest nowsza wersja (sekcja 3.15).

### 2.4 Odinstalowanie

Odinstalowanie usuwa pozycje menu, szablony promptów, całą historię zapytań i ustawienia modułu, w tym klucz API oraz sekrety crona. Ponowna instalacja zaczyna od zera i tworzy nowe sekrety, więc każdy adres podany harmonogramowi zadań trzeba zastąpić nowym.

Teksty już zapisane w produktach i kategoriach, zaimportowane zdjęcia, produkty utworzone przez **New product** oraz tagi pozostają w sklepie. Ustawienia sprawdzania aktualizacji i kilka pozostałych wartości filtrów nie są usuwane.

## 3. Konfiguracja i praca w panelu administracyjnym

Zrzuty ekranu w tej instrukcji pokazują angielski panel administracyjny. Nazwy menu, pól i przycisków podajemy po angielsku i pogrubiamy, tak jak widzisz je na ekranie.

### 3.1 Jak przebiega praca

1. **Connect** – wklej klucz API i wybierz model (Settings – Mistral).
2. **Set the rules** – zasady firmowe, budżet i kontrola jakości (Settings – Studio).
3. **Prepare prompts** – edytuj lub dodaj szablony promptów (Settings – Prompt templates) i wypróbuj je w Playground.
4. **Generate** – wybierz jeden z trzech sposobów:
   - jeden produkt naraz, ze strony edycji produktu (sekcja 3.16) lub małymi przyciskami "Generate with AI" obok pól (sekcja 3.17);
   - wiele produktów lub kategorii naraz, ze stron Generate (sekcje 3.9 i 3.10);
   - automatycznie, małymi partiami, przez cron (sekcja 3.12).
5. **Check** – każde zapytanie jest zapisywane w History (sekcja 3.13). Błędny tekst można przywrócić z zakładki History w samym produkcie.

Każda strona ustawień ma własny przycisk **Save**. Zapisz stronę, zanim ją opuścisz, ponieważ strony nie korzystają z jednego wspólnego formularza.

### 3.2 Otwieranie modułu i pasek menu

Otwórz **Modules > AI Content Generator** lub kliknij **Configure** w Module Manager. Każdy ekran pokazuje u góry ten sam pasek menu:

| Pozycja menu | Co otwiera |
|---|---|
| Dashboard | Karty użycia i wykresy (sekcja 3.3). |
| Settings | Grupa z pięcioma podstronami: General, Mistral, Studio, Prompt templates, Playground (sekcje 3.4 do 3.8). |
| Generate | Masowe generowanie dla produktów i kategorii (sekcje 3.9 i 3.10). |
| New product | Tworzenie produktu na podstawie krótkiego opisu (sekcja 3.11). |
| Cron | Adresy do generowania według harmonogramu (sekcja 3.12). |
| History | Lista wszystkich zapytań z filtrami i sumami tokenów (sekcja 3.13). |
| Images | Ustawienia wyszukiwarki zdjęć (sekcja 3.14). |
| Updates | Sprawdzanie aktualizacji (sekcja 3.15). |

Każdy ekran ma przycisk **Help**. Otwiera on panel boczny z krótkim wyjaśnieniem tego ekranu. Po najechaniu myszą na pozycję menu pojawia się jednolinijkowa podpowiedź. Pod każdym polem znajdziesz opis w trzech częściach: co pole robi, jak je ustawić i jaki jest efekt.

### 3.3 Dashboard

![Dashboard with usage cards and charts](https://mypresta.eu/docs/images/docs/myaimistral-dashboard.webp)

Dashboard zlicza, co moduł zrobił w wybranym okresie. Wiersz na górze podaje aktywną usługę i model.

| Element | Domyślnie | Co pokazuje |
|---|---|---|
| Period buttons | 30 days | Today, 7 days, 30 days, 90 days, This month, All time. |
| From / To and Apply | wypełniane według okresu | Własny zakres dat. Jeśli From jest późniejsze niż To, obie daty są zamieniane miejscami. |
| Requests | – | Każde zapisane połączenie z Mistral AI w danym okresie. |
| Success | – | Połączenia, które zwróciły tekst. |
| Errors | – | Połączenia zakończone błędem. Otwórz History, aby zobaczyć przyczynę. |
| Tokens sent | – | Rozmiar wysłanych przez Ciebie poleceń. |
| Tokens received | – | Rozmiar odpowiedzi. |
| Requests and errors | – | Wykres liniowy dzień po dniu. |
| Tokens sent and received | – | Wykres liniowy dzień po dniu. |
| Requests by model | – | Wykres słupkowy. |

Ta strona tylko raportuje. Stąd nic w katalogu nie jest generowane ani zmieniane, a History nie jest usuwana.

### 3.4 Settings – General

![Settings – General](https://mypresta.eu/docs/images/docs/myaimistral-settings-general.webp)

Otwórz **Settings > General**. Ta strona decyduje, co pracownicy widzą w panelu administracyjnym. Zapisanie jej nie zmienia żadnego tekstu produktu.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Live mode | Disabled | Oznacza moduł jako działający w prawdziwym sklepie, a nie w ustawieniach próbnych. Włącz go w sklepie produkcyjnym. |
| Debug mode | Disabled | Zapisuje dodatkowe szczegóły diagnostyczne w logu PrestaShop, gdy połączenie z dostawcą się nie powiedzie. Włączaj tylko na czas badania błędu. Klienci nigdy tego nie widzą. To nie to samo co **Enable Debug** na stronie Cron. |
| API timeout (seconds) | 120 | Ile sekund jedno połączenie z Mistral może trwać, zanim moduł się podda. Wartość jest utrzymywana w zakresie od 10 do 600. Pusta lub nienumeryczna wartość zostanie zapisana jako 120. Przy długich tekstach i wolnych modelach zwiększ ją w stronę 600. |
| Product Edit History | Enabled | Pokazuje podzakładkę **History** na stronie edycji produktu, dzięki czemu możesz przywrócić starą wartość. Dotychczasowe wiersze zostają w History w obu przypadkach. |
| Admin Top Bar CTA | Enabled | Pokazuje małą ikonę różdżki na górnym pasku panelu administracyjnego. Wyłączenie usuwa tylko ten przycisk, a nie menu modułu. |
| Product edit page Form | Enabled | Pokazuje panel **My AI Mistral** (Generate, Simulate, Photos) w zakładce **Modules** na stronie edycji produktu. Wyłącz, gdy ma być używane tylko generowanie masowe i cron. Małe przyciski "Generate with AI" obok pól (sekcja 3.17) nie są w tej wersji wyłączane tym ustawieniem. |
| AI Image Finder | Enabled | Pokazuje lub ukrywa wyszukiwanie zdjęć na stronie edycji produktu. Zdjęcie jest importowane dopiero po Twoim potwierdzeniu. |
| AI Image Search Prompt | Wbudowane polecenie | Polecenie wysyłane, gdy ktoś szuka zdjęć. `{product_name}` i `{product_description}` są zastępowane danymi bieżącego produktu. Zachowaj prośbę o listę adresów stron w formacie JSON. Te same dwa pola powtarzają się na stronie **Images**. |

Kliknij **Save**. Potwierdzenie to "Settings Updated".

### 3.5 Settings – Mistral

![Settings – Mistral](https://mypresta.eu/docs/images/docs/myaimistral-settings-mistral.webp)

Otwórz **Settings > Mistral**. Strona łączy sklep z Twoim kontem Mistral AI i ustawia, jak zróżnicowane ma być słownictwo. Pola próbkowania nie zmieniają tego, które produkty są aktualizowane.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Mistral AI API KEY | pusty | Klucz z https://console.mistral.ai/api-keys/. Spacje są usuwane przy zapisie. Pozostaw pole nietknięte, aby zachować zapisany klucz. Wartość krótsza niż 10 znaków jest odrzucana, jeśli nie ma zapisanego klucza. |
| Model | mistral-small-latest | Model, który pisze tekst. Lista zawiera modele wbudowane i dodane przez Ciebie. Model, którego Twój klucz nie może używać, zwraca błąd API zamiast tekstu. |
| Add a Mistral model | pusty | Wpisz dokładną nazwę modelu z konta Mistral i naciśnij **Add model**. Nowa nazwa pojawi się na liście **Model** i od razu stanie się aktywnym modelem. Nazwy mogą zawierać litery, cyfry oraz znaki `.`, `_`, `:` i `-`. Obok każdej dodanej nazwy jest link **Remove**. Modeli wbudowanych nie można usunąć. |
| Max Tokens | 3200 | Najdłuższa odpowiedź w tokenach. Dla meta opisu użyj około 256, a dla pełnego opisu HTML 1000 lub więcej. Zbyt niska wartość ucina tekst. Wysoka wartość kosztuje więcej. |
| Temperature | 0.7 | Jak swobodnie model dobiera słowa, od 0 do 1. Około 0.2 pasuje do metatekstów, około 0.7 do opisów. Zmieniaj albo Temperature, albo Top P, nie oba naraz. |
| Top P | 1 | Inny sposób ograniczenia, jak zaskakujące może być następne słowo, od 0 do 1. Zostaw 1, jeśli ustawiasz Temperature. |
| Frequency Penalty Value | 0 | Od -2 do 2. Wartość dodatnia, np. 0.3 do 0.6, ogranicza powtarzanie fraz w jednej odpowiedzi. |
| Presence Penalty Value | 0 | Od -2 do 2. Wartość dodatnia rozkłada tekst na więcej wątków. Niektóre modele ją ignorują. |

Wbudowane modele to: mistral-small-latest, mistral-medium-latest, mistral-large-latest, ministral-8b-latest, ministral-3b-latest, codestral-latest i open-mistral-nemo.

Jeśli Mistral odrzuci jedno z ustawień liczbowych dla danego modelu, moduł to zapamiętuje, pomija to ustawienie dla tego modelu i ponawia zapytanie. Nie musisz nic robić.

Pole z nazwą modelu musi mieć przy zapisie co najmniej 3 znaki, w przeciwnym razie strona pokaże "OpenAi Model field is invalid!". Potwierdzenie po zapisie to "OpenAi Settings Updated". Komunikaty "Model added.", "Model removed." i "That model is already built in." dotyczą przycisków dodawania i usuwania.

### 3.6 Settings – Studio

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaimistral-settings-studio.webp)

Studio jest nakładane na każdy prompt, niezależnie od tego, skąd zaczyna się zapytanie: ze strony produktu, stron Generate, crona, Playground czy górnego paska. Puste pola są pomijane.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Brand voice | pusty | Krótkie wytyczne mówiące modelowi, kto przemawia, np. "specialist workshop, short sentences, no hype". |
| Audience | pusty | Czytelnik, dla którego model ma pisać, np. "professional installers". |
| Tone | pusty | Nastrój tekstu. Wystarczy jedno lub dwa słowa. |
| Glossary | pusty | Nazwy marek, materiały i pisownie, które model musi skopiować dokładnie. Jeden termin w wierszu. |
| Forbidden words | pusty | Słowa i wyrażenia, które nie mogą pojawić się w zapisanej odpowiedzi. Jedno w wierszu. Używane tylko wtedy, gdy Quality gate jest Enabled. |
| Monthly generation budget | 0 | Największa liczba udanych generowań w bieżącym miesiącu kalendarzowym. 0 oznacza brak limitu. Licznik zaczyna się od nowa pierwszego dnia miesiąca. Po osiągnięciu limitu generowanie zatrzymuje się z komunikatem o budżecie. Nieudane połączenia nie są liczone. |
| Quality gate | Enabled | Sprawdza każdą odpowiedź pod kątem Forbidden words, zanim cokolwiek zostanie zapisane. Odpowiedź zawierająca słowo z listy jest odrzucana, nie trafia do produktu i jest zapisywana w History jako błąd. Gdy jest Disabled, odpowiedź zostaje zapisana mimo to. |

Kliknij **Save studio**. Potwierdzenie to "Studio settings saved.".

### 3.7 Settings – Prompt templates

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaimistral-settings-templates.webp)

Szablon promptu to zapisane polecenie. Strona pokazuje listę **Prompt Templates** z przyciskiem tworzenia nowego szablonu.

#### Lista

| Kolumna | Co pokazuje |
|---|---|
| ID | Numer szablonu. |
| Title | Nazwa, którą widzisz na listach szablonów. |
| Prompt | Treść polecenia. |
| Status | Kliknij ikonę, aby włączyć lub wyłączyć szablon. |
| Timestamp | Czas utworzenia. |

Każdy wiersz ma **Edit** i **Delete**. Zaznacz kilka wierszy i użyj zbiorczego **Delete**, aby je usunąć. Najnowsze szablony są na górze.

#### Formularz "Generate Prompt Template"

| Pole | Domyślnie | Co robi |
|---|---|---|
| Status | nie ustawiono | Włączone szablony są oferowane w panelu produktu, na stronie Generate – Products i na górnym pasku. Wyłączone zostają w tabeli, ale nie są tam oferowane. Wybierz **Enabled** przed zapisem, ponieważ nowy szablon startuje bez wybranej wartości. |
| Prompt title | pusty | Nazwa pokazywana w listach rozwijanych. Nie jest wysyłana do modelu. Wymagane. |
| Prompt content | pusty | Polecenie wysyłane do modelu. Znaczniki w nawiasach klamrowych są zastępowane dla każdej pozycji przed wysłaniem. Podwójne cudzysłowy są przy zapisie zamieniane na pojedyncze. Wymagane. |

Kliknij **Save Prompt**. Potwierdzenia to "Prompt template successfully added!", "Prompt template successfully updated!" oraz "Prompt template removed.". **Go Back to Module Settings** wraca do listy.

#### Znaczniki (placeholders)

| Znacznik | Zastępowany przez | Działa w |
|---|---|---|
| {product_name} | Nazwa produktu | Generowanie produktów |
| {product_description} | Opis długi | Generowanie produktów |
| {product_description_short} | Opis krótki | Generowanie produktów |
| {product_tags} | Aktualne tagi | Generowanie produktów |
| {product_reference} | Referencja | Generowanie produktów |
| {product_ean13} | Kod EAN-13 | Generowanie produktów |
| {product_weight} | Waga | Generowanie produktów |
| {product_brand} | Nazwa marki | Generowanie produktów |
| {product_default_category} | Nazwa kategorii domyślnej | Generowanie produktów |
| {product_category_description} | Opis kategorii domyślnej | Generowanie produktów |
| {product_categories} | Nazwy wszystkich kategorii produktu | Generowanie produktów |
| {product_attributes} | Atrybuty kombinacji (grupa i wartość) | Generowanie produktów |
| {product_features} | Nazwy cech | Generowanie produktów |
| {product_feature_values} | Cechy wraz z wartościami | Generowanie produktów |
| {product_images} | Adresy zdjęć produktu | Generowanie produktów |
| {category_name} | Nazwa kategorii | Generowanie kategorii |
| {category_description} | Opis kategorii | Generowanie kategorii |
| {category_parent_name} | Nazwa kategorii nadrzędnej | Generowanie kategorii |
| {shop_name} | Nazwa sklepu | Generowanie produktów i kategorii |
| {shop_url} | Domena sklepu | Generowanie produktów i kategorii |
| {shop_language} | Nazwa języka | Generowanie produktów i kategorii |
| {shop_country} | Kraj domyślny | Generowanie produktów i kategorii |
| {shop_currency} | Kod waluty domyślnej | Generowanie produktów i kategorii |

"Generowanie produktów" oznacza panel produktu, Generate – Products i cron produktów. "Generowanie kategorii" oznacza Generate – Categories i cron kategorii. Znaczniki nie są zastępowane w Playground ani w oknie górnego paska, ponieważ nie jest tam wybrany żaden produkt ani kategoria. Znacznik bez danych jest zastępowany pustym tekstem.

#### Szablony dostarczane z modułem (16)

| Nr | Tytuł | Przeznaczenie |
|---|---|---|
| 1 | Product name 1 | Krótsza, lepsza nazwa oparta na obecnej nazwie. |
| 2 | Product name 2 | Sprzedażowy tytuł wykorzystujący markę i kategorię domyślną. |
| 3 | Product description 1 | Opis HTML z trzema nagłówkami i tagami pogrubionymi. |
| 4 | Product description 2 | Opis w trzech prostych sekcjach. |
| 5 | Product description 3 | Długie wytyczne SEO, które dodatkowo proszą o pomysły na nagłówki, słowa kluczowe i metatagi. |
| 6 | Product description 4 | Krótka prośba o "zachwycający opis". |
| 7 | Product description 5 | Opis wykorzystujący tagi produktu jako słowa kluczowe. |
| 8 | Product description 6 | Opis wykorzystujący markę i kategorię domyślną. |
| 9 | Product description 7 - using product images | Opis, który osadza zdjęcia produktu przez {product_images}. |
| 10 | Product meta title 1 | Meta tytuł SEO, do 60 znaków. |
| 11 | Product meta title 2 | Drugi wariant meta tytułu. |
| 12 | Product meta title 3 | Meta tytuł zawierający markę. |
| 13 | Product meta description 1 | Meta opis SEO, do 160 znaków. |
| 14 | Product meta description 2 | Drugi wariant; przykładowy tekst wspomina o smartwatchu. |
| 15 | Product meta description 3 | Ten sam tekst co numer 14. |
| 16 | Product tags | Pięć tagów w jednym wierszu, oddzielonych przecinkami. |

Przeczytaj i dostosuj szablony, zanim użyjesz ich na prawdziwych produktach:

- Szablon 3 prosi model o dodanie do tekstu kilku błędów ortograficznych. Usuń to zdanie.
- Szablon 5 zwraca więcej niż opis (pomysły na nagłówki, listę słów kluczowych i metatagi). Używaj go jako inspiracji, nie do zapisu prosto w pole opisu.
- Szablony 5, 10, 13 i 16 proszą o odpowiedź po angielsku. Zmień ten wiersz, jeśli Twój sklep używa innego języka.
- Szablony 14 i 15 są napisane dla smartwatcha. Zamień przykład, zanim ich użyjesz.

### 3.8 Settings – Playground

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaimistral-settings-playground.webp)

Playground wysyła jeden dowolny prompt do aktywnego modelu i wypisuje odpowiedź pod przyciskiem. Odpowiedź zostaje na tej stronie. Żaden produkt ani kategoria nie są zapisywane.

| Element | Domyślnie | Co robi |
|---|---|---|
| Prompt box | pusty | Polecenie dla tego jednego połączenia. Dodawane są do niego reguły Studio. |
| Generate | – | Wysyła prompt. W czasie oczekiwania obszar odpowiedzi pokazuje "Working…". |
| Answer area | – | Odpowiedź modelu wraz z liczbą zużytych tokenów. |

Komunikaty: "Write a prompt first." (pole jest puste) oraz "The request timed out or the shop blocked it." (zobacz sekcję 5.2).

Zapytanie jest zapisywane w History tak jak każde inne.

### 3.9 Generate – Products

![Generate – Products](https://mypresta.eu/docs/images/docs/myaimistral-generate-products.webp)

Otwórz **Generate** i zostań na **Products**. Praca ma dwa kroki: zbudowanie listy, a następnie uruchomienie generowania na tej liście.

#### Krok 1 – zbuduj listę ("Filter products to update")

W tym kroku nic nie jest wysyłane do modelu. Przy każdym otwarciu strony filtry startują z poniższymi wartościami.

| Pole | Domyślnie | Co robi |
|---|---|---|
| Product Categories | żadna nie zaznaczona | Drzewo kategorii. Na liście są tylko produkty znajdujące się w zaznaczonej kategorii lub mające ją jako kategorię domyślną. Pozostaw drzewo puste, aby ignorować kategorie. |
| Brand | Select brand (all) | Tylko produkty jednej marki. |
| Product status | Active | **Active**, **Disabled** lub **Both**. |
| Product stock | All products | **All products** lub **Only in stock products**. |
| Update only | Update all | Korzysta z History: **Products that have not been updated with OpenAi content** wyświetla produkty bez wiersza w History, **Products that already have been updated with OpenAi content** wyświetla produkty z wierszem, **Update all** ignoruje History. Słowo "OpenAi" w dwóch pierwszych opcjach to stara etykieta; oznacza ten moduł. Liczy się wiersz o dowolnym statusie, także nieudany. |
| Product IDs | pusty | ID produktów oddzielone przecinkami, np. 12,45,103. Wpisuj tylko cyfry i przecinki. |
| Product Reference | pusty | Jedna lub kilka referencji oddzielonych przecinkami. Referencja musi się zgadzać dokładnie. |
| Product Add Date From | pusty | Tylko produkty utworzone po tej dacie i godzinie. |
| Product Add Date To | pusty | Tylko produkty utworzone przed tą datą i godziną. |
| Minimum product ID | pusty | Najmniejsze ID produktu na liście. |
| Maximum product ID | pusty | Największe ID produktu na liście. |
| Product Limit | pusty | Największa liczba produktów do załadowania. W dużym katalogu użyj małej liczby, np. 20. |

Kliknij **Go to next step**. Przycisk **Module settings** obok niego to stary skrót i nie otwiera ustawień tego modułu.

#### Krok 2 – uruchom generowanie ("Mass product generation")

| Pole | Domyślnie | Co robi |
|---|---|---|
| Template | Choose a template | Kopiuje włączony szablon do pola promptu. Sam tytuł nie jest wysyłany. |
| Prompt box | pusty | Polecenie wysyłane dla każdego produktu, ze znacznikami zastąpionymi osobno dla każdego produktu. Jeśli pole jest puste, używane są standardowe wytyczne dla każdego pola. |
| What to generate | Descriptions | **Descriptions** (opis długi i krótki), **Meta title and meta description** lub **Descriptions and meta together** (wszystkie cztery). Każde pole to osobne zapytanie. |
| Existing text | Replace | **Replace** nadpisuje tekst. **Skip if filled** pomija wypełnione pole i nie wywołuje dla niego modelu. **Add above** i **Add below** zachowują stary tekst i dołączają nowy. |
| Languages | zaznaczony język Twojego panelu administracyjnego | Zaznacz każdy język, w którym ma powstać tekst. Każdy zaznaczony język to jedno dodatkowe zapytanie na pole. |

Kliknij **Run on the list below**. Tabela wyświetla produkty według ID i referencji. Uruchomienie przechodzi po kolei przez każdy produkt, pole i język. Wiersz nad przyciskiem pokazuje postęp, np. "3 / 120 – description", a kolumna **Result** pokazuje odpowiedź dla każdego kroku. "skipped" oznacza, że pole miało już tekst, a Ty wybrałeś **Skip if filled**. Po zakończeniu wiersz informuje: "Finished N products.".

Nie możesz odznaczać pojedynczych produktów w tabeli. Aby zmienić listę, zmień filtr w kroku 1. Nazwy i tagi nie wchodzą w skład tego uruchomienia; użyj do nich strony edycji produktu lub crona. Tekst jest zapisywany w miarę nadchodzenia odpowiedzi. Zamknięcie strony zatrzymuje uruchomienie, a produkty już przetworzone zachowują nowy tekst.

### 3.10 Generate – Categories

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaimistral-generate-categories.webp)

Otwórz **Generate** i przełącz się na **Categories**.

#### Krok 1 – zbuduj listę ("Filter categories to update")

| Pole | Domyślnie | Co robi |
|---|---|---|
| Categories | żadna nie zaznaczona | Zaznacz kategorie do wyświetlenia na liście. Gdy nic nie jest zaznaczone, lista zawiera każdą kategorię pasującą do statusu, w tym Root i Home. Zaznacz konkretne kategorie, aby tego uniknąć. |
| Category status | Active | **Active**, **Disabled** lub **Both**. |

Kliknij **Go to next step**.

#### Krok 2 – uruchom generowanie ("Mass category generation")

| Pole | Domyślnie | Co robi |
|---|---|---|
| Prompt box | pusty | Polecenie wysyłane dla każdej kategorii. Użyj {category_name}, {category_description}, {category_parent_name} oraz znaczników sklepu. Na tej stronie nie ma listy szablonów. |
| Field | Description | Pole do zapisania: **Description**, **Name**, **Meta title**, **Meta description** lub **Additional description**. Zapisywane jest tylko to pole. |
| Existing text | Replace | **Replace** lub **Skip if filled**. |
| Language | język Twojego panelu administracyjnego | Jeden język. Aby uzyskać inny język, uruchom ponownie. |

Kliknij **Run on the categories below**. Tabela wyświetla ID kategorii i pokazuje wynik dla każdej z nich.

Jeśli pole promptu jest puste, dla opisu, meta tytułu i meta opisu używane są standardowe wytyczne. Dla **Name** i **Additional description** użyte zostałyby wytyczne do opisu, więc dla tych dwóch pól zawsze wpisuj własny prompt.

Pod listą strona pokazuje także starszy formularz **Generate category content** z przyciskiem **Generate content**. Nie generuje on niczego. Użyj przycisku uruchomienia powyżej.

### 3.11 New product

![New product](https://mypresta.eu/docs/images/docs/myaimistral-new-product.webp)

**New product** prosi model o pełny szkic produktu i może go wstawić do katalogu.

| Pole | Domyślnie | Co robi |
|---|---|---|
| What is the product? | pusty | Kilka zdań: czym jest produkt, z czego jest wykonany, dla kogo, jakie nazwy zachować. Bogatszy opis daje trafniejszy szkic. Puste pole jest odrzucane. |
| Optional source URL | pusty | Pełny adres http lub https publicznej strony. Jej czytelny tekst jest dodawany do opisu. Strona, której sklep nie może odczytać, jest ignorowana. |
| Language | domyślny język sklepu | Język, w którym zapisywane są nazwa, opisy, metatagi i tagi. Inne języki nie są wypełniane. |
| Default category ID | 2 | Numer kategorii z **Catalog > Categories**. 2 to zwykle Home. Produkt jest tam umieszczany. |

Przyciski:

- **Generate data** pokazuje szkic jako zwykły tekst w polu pod przyciskami. Niczego nie zapisuje. Szkic zawiera nazwę, opisy, metatagi, tagi, referencję, sugerowaną cenę i cechy.
- **Create product** wstawia ostatnio wygenerowany szkic. Nowy produkt jest **aktywny**, ma stan magazynowy **100**, używa pierwszej grupy reguł podatkowych sklepu i jest umieszczony w kategorii, którą wpisałeś. Po sukcesie pole pokazuje "Product #" i numer nowego produktu.

Szkicu nie można edytować na tej stronie. Cenę, podatek, zdjęcia i kategorię sprawdź potem w samym produkcie; cena jest tą, którą zasugerował model, i może wynosić 0. Strona pokazuje "Add an API key in the module settings first.", gdy klucz nie jest zapisany.

### 3.12 Cron

![Cron](https://mypresta.eu/docs/images/docs/myaimistral-cron.webp)

Cron pozwala Twojemu serwerowi aktualizować kilka produktów lub kategorii za każdym razem, gdy harmonogram zadań otworzy adres. Strona pokazuje: panel **Category cron**, formularz **CRON JOB Settings - Generate product content using Mistral AI**, formularz **CRON JOB Settings - Generate category content using Mistral AI** oraz panel **Cron parameters**. Formularze tylko budują i zapisują ustawienia; nic nie działa, dopóki serwer nie wywoła adresu.

#### Adres crona

Adres dla produktów wygląda tak:

```text
https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent
```

Adres dla kategorii wygląda tak:

```text
https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_CATEGORY_SECRET&action=generateCategoryContent
```

- Zastąp `YOUR-SHOP.EXAMPLE` adresem swojego sklepu.
- Zastąp sekret wartością **Cron Job Secret Token** z odpowiedniego formularza. Nigdy go nie publikuj.
- Część `&action=generateProductContent` lub `&action=generateCategoryContent` jest wymagana. Bez niej adres odpowiada "Invalid action!".
- Panele na stronie pokazują adres tylko do sekretu włącznie. Panel kategorii dodaje `&entity=category`, którego sklep nie używa. Część z `action` dopisz sam, jak pokazano wyżej.
- Wiersz "Command:" w każdym formularzu pokazuje tylko goły adres, bez sekretu i bez akcji. Pełny adres zbuduj samodzielnie.

#### Formularz produktów

| Pole | Domyślnie | Co robi |
|---|---|---|
| Enable Cron Feature | No | Główny przełącznik dla crona produktów i kategorii. Gdy jest No, każdy adres crona odpowiada, że funkcja jest wyłączona. |
| Cron Job Secret Token | losowy, 32 znaki | Hasło w adresie produktów. Musi mieć co najmniej 24 znaki. Krótszy sekret jest zastępowany losowym przy ładowaniu strony modułu. |
| Update Field | description | Jedno pole na wpis harmonogramu: name, description, description_short, meta_title, meta_description lub tags. Aby wypełnić kilka pól, utwórz kilka wpisów. |
| Selected Products | pendingMistral | Które produkty jeszcze czekają. **pendingMistral** bierze produkty, które nie mają udanego wiersza w History dla żadnego pola. **pendingField** bierze produkty bez udanego wiersza dla wybranego pola, więc kilka wpisów może wypełniać różne pola tych samych produktów. **emptyField** bierze produkty, w których wybrane pole jest puste w wybranym języku. |
| Product Categories | żadna nie zaznaczona | Ogranicza uruchomienie do produktów w zaznaczonych kategoriach. Zobacz ostrzeżenie poniżej. |
| Product ID list | pusty | Stała lista ID produktów oddzielonych przecinkami. Litery są odrzucane przy zapisie. |
| Language | domyślny język sklepu | Język, w którym ma powstać tekst. Inne języki wymagają własnego wpisu. |
| Product to update | 5 products | Ile produktów przetworzyć przy jednym wywołaniu: 2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 lub 1000. Zacznij od 5 lub 10, aby wolny model nie przekroczył limitu czasu serwera. |
| Prompt Template | pierwszy szablon na liście | Zapisane polecenie używane dla każdego produktu. Zobacz uwagę poniżej. |
| Enable Debug | No | Gdy Yes, adres wypisuje, co by zrobił, i niczego nie zapisuje. |
| CRON JOB interval | Every Hour | Przypomnienie, jak często planujesz wywoływać adres (od co minutę do co 6 godzin). Moduł sam niczego nie uruchamia. |

Kliknij **Save**. Lista **Prompt Template** nie ma pustej opcji i pokazuje każdy zapisany szablon, także wyłączone, od najnowszego. Dopóki nie zapiszesz żadnego, formularz wyświetla najnowszy szablon (Product tags). Zawsze wybierz szablon, który chcesz, i zapisz, w przeciwnym razie zapisany zostanie ten, który jest widoczny.

Ostrzeżenie: gdy w **Product Categories** zaznaczone są kategorie, sklep wybiera także produkty, których kategoria domyślna jest zaznaczona, nawet jeśli były już przetworzone. Cron może wtedy przy każdym wywołaniu nadpisywać te same pierwsze produkty. Pozostaw drzewo kategorii puste i użyj zamiast tego **Product ID list**.

#### Formularz kategorii

| Pole | Domyślnie | Co robi |
|---|---|---|
| Cron Job Secret Token | losowy, 32 znaki | Hasło w adresie kategorii. Co najmniej 24 znaki. |
| Update Field | description | name, description, meta_title lub meta_description. |
| Selected categories | pendingMistral | **pendingMistral**, **pendingField** lub **emptyField**, o tym samym znaczeniu co dla produktów. |
| Language | domyślny język sklepu | Język, w którym ma powstać tekst. |
| Categories to update | 5 categories | Ile kategorii przy jednym wywołaniu (te same opcje co dla produktów). |
| Prompt Template | pierwszy szablon na liście | Zapisane polecenie. Napisz je dla kategorii, nie dla produktu. |
| Enable Debug | No | Gdy Yes, adres wypisuje plan i niczego nie zapisuje. |
| CRON JOB interval | Every Hour | Tylko przypomnienie. |

Kliknij **Save** pod formularzem. Root i Home nigdy nie są przetwarzane przez cron kategorii. Przełącznik **Enable Cron Feature** znajduje się w formularzu produktów i kontroluje także cron kategorii.

#### Sekrety i "Generate Token"

Jeśli chcesz nowy sekret, wpisz go w pole ręcznie, co najmniej 24 znaki, litery i cyfry. Przycisk **Generate Token** może w tej wersji nie wypełniać pola, więc nie polegaj na nim. Po zapisaniu nowego sekretu zmień go także w harmonogramie, ponieważ stary adres przestaje działać. Każdy z dwóch sekretów otwiera obie akcje, więc oba trzymaj w tajemnicy.

#### Konfiguracja harmonogramu

Na serwerze Linux dodaj do crontab wiersz taki jak ten (co godzinę):

```text
0 * * * * curl -s -o /dev/null "https://YOUR-SHOP.EXAMPLE/module/myaimistral/cron?secret=YOUR_PRODUCT_SECRET&action=generateProductContent"
```

Adres trzymaj w cudzysłowie, ponieważ zawiera znak `&`. W systemie Windows użyj Harmonogramu zadań z `curl.exe` i tym samym adresem. Panele hostingowe z ekranem "cron job" przyjmują to samo polecenie.

#### Bezpieczne testowanie

1. Zapisz formularz z **Enable Cron Feature** ustawionym na Yes i **Enable Debug** ustawionym na Yes.
2. Otwórz pełny adres w przeglądarce. Zobaczysz odczytane ustawienia, zapytanie i końcowy prompt, a nic nie zostanie zapisane.
3. Ustaw **Enable Debug** na No, zapisz i otwórz adres ponownie. Strona odpowie teraz krótkim tekstem, np. "5 products have been updated.".

Jeśli **Enable Debug** pozostanie włączone, zaplanowane wywołania niczego nie zapisują. To najczęstszy powód, dla którego cron "nic nie robi".

Zapisywany tekst jest przycinany do długości dozwolonej przez PrestaShop: nazwa 128, opis krótki 799, meta tytuł 69 i meta opis 159 znaków. Stary tekst zostaje w History, więc możesz go przywrócić ze strony produktu.

### 3.13 History

![History](https://mypresta.eu/docs/images/docs/myaimistral-history.webp)

Każde zapytanie do Mistral AI jest zapisywane w History wraz z poleceniem, odpowiedzią lub błędem, modelem, liczbą tokenów i czasem trwania.

#### Filtry i sumy

| Element | Domyślnie | Co robi |
|---|---|---|
| Period buttons | This month | Today, 7 days, 30 days, This month, All time. |
| From / To | wypełniane według okresu | Własny zakres dat. |
| Model | Any | Tylko jeden model. |
| Type | Any | Tylko jeden rodzaj zapytania, np. product_description lub category_meta_title. |
| Status | Any | Success lub Error. |
| Language | Any | Tylko jeden język. |
| Employee | Any | Tylko zapytania wykonane przez jednego pracownika. |
| Product / category ID | pusty | Tylko zapytania dotyczące tego rekordu. |
| Prompt or reply contains | pusty | Słowo wyszukiwane w poleceniu i w odpowiedzi. |
| Filter | – | Stosuje filtry. |

Karty pokazują Requests, Success, Errors, Tokens sent, Tokens received, Tokens total i Average time. Kreska oznacza, że Mistral nie zwrócił liczby tokenów dla tego połączenia. Pod kartami znajdują się tabele **By day**, **By model**, **By type**, **By language** i **By employee** z kolumnami Group, Calls, Sent, Received i Total. Mała liczba obok Calls to liczba błędów w tej grupie.

#### Lista "Prompt history"

Lista podąża za filtrami i pokazuje 50 wierszy na stronę.

| Kolumna | Co pokazuje |
|---|---|
| ID | Numer wiersza logu. |
| Status | Success lub Error. |
| Prompt | Początek polecenia. |
| Reply / Error | Początek odpowiedzi lub tekst błędu. |
| Provider | Nazwa dostawcy, model, kod HTTP i czas w sekundach, rozdzielone kropkami. Nazwa dostawcy nadal brzmi "openai". |
| Sent / Received / Total | Tokeny. |
| Entity ID | Produkt lub kategoria, której dotyczyło zapytanie. |
| Type | Rodzaj zapytania. |
| Timestamp | Kiedy zapytanie zostało wykonane. |

Kliknij **View** w wierszu, aby przeczytać pełny prompt i odpowiedź. **Back to the list** wraca do listy.

**Clear list** (pasek narzędzi) usuwa wszystkie wiersze, nie tylko przefiltrowane, i pokazuje "Log list successfully deleted.". Resetuje też informacje, według których cron wie, które pozycje zostały już zaktualizowane (cele "pending" zaczynają się od początku), zeruje miesięczny licznik budżetu i usuwa poprzednie teksty potrzebne do **Restore**. Nie ma cofnięcia.

### 3.14 Images

![Images](https://mypresta.eu/docs/images/docs/myaimistral-images.webp)

Strona **AI Image Finder** zawiera te same dwa ustawienia co koniec Settings – General. Zapisanie ich nie pobiera żadnych zdjęć i nie zmienia żadnych tekstów.

| Pole | Domyślnie | Co robi |
|---|---|---|
| AI Image Finder | Enabled | Pokazuje lub ukrywa wyszukiwanie zdjęć na stronie edycji produktu. |
| AI Image Search Prompt | Wbudowane polecenie | Polecenie wysyłane, gdy ktoś szuka zdjęć. `{product_name}` i `{product_description}` są zastępowane danymi bieżącego produktu. Wbudowany tekst prosi dokładnie o 5 adresów stron w postaci listy JSON. Zmień brzmienie, jeśli wolisz strony producentów. Niejasny prompt zwraca niepowiązane linki. |

Kliknij **Save**. Potwierdzenie to "Settings saved.".

Jak to działa: model proponuje strony internetowe, które prawdopodobnie pokazują produkt, moduł otwiera te strony i wyświetla znalezione zdjęcia, a Ty zaznaczasz zdjęcia do zaimportowania. Moduł nie sprawdza, do kogo należą zdjęcia. Używaj tylko zdjęć, do których masz prawo.

### 3.15 Updates

![Updates](https://mypresta.eu/docs/images/docs/myaimistral-updates.webp)

| Element | Domyślnie | Co robi |
|---|---|---|
| Manual Check – Check Now | – | Jednorazowo pyta serwer aktualizacji o najnowszą wersję. Odpowiedź to "Module is up to date!" lub "New version available!". |
| Automatic Notifications | Enabled | Mniej więcej co trzy dni moduł sprawdza w tle. Gdy istnieje nowsza wersja, pracownicy widzą w panelu administracyjnym baner z ostrzeżeniem. Wybierz Disabled, aby zarządzać aktualizacjami ręcznie. |
| Product Page | – | Link do strony modułu. |

Kliknij **Save**. Potwierdzenie to "Update settings saved.". Sprawdzenie wysyła do MyPresta.eu nazwę modułu, jego wersję i adres Twojego sklepu.

### 3.16 Strona edycji produktu

![Product edit page – My AI Mistral tab](https://mypresta.eu/docs/images/docs/myaimistral-product-edit.webp)

Otwórz **Catalog > Products**, edytuj istniejący produkt i otwórz zakładkę **Modules**. Wybierz **My AI Mistral**. Zakładka ma podzakładki **Generate**, **Simulate**, **Photos** i **History**. Pierwsze trzy pojawiają się, gdy **Product edit page Form** jest Enabled; **History** pojawia się, gdy **Product Edit History** jest Enabled.

#### Elementy wspólne dla Generate i Simulate

| Element | Domyślnie | Co robi |
|---|---|---|
| Language | pierwszy język | Kliknij język albo **Every language**, aby zapisać wszystkie po kolei. |
| If the field already has text | Replace | **Replace**, **Add above**, **Add below** lub **Skip if filled**. Widoczne tylko w podzakładce Generate. |
| Use your own instruction or a saved prompt | zamknięte | Otwiera pole filtra i kafelki: **Standard brief** oraz każdy włączony szablon. Kliknij kafelek, aby go użyć. |
| Instruction | pusty | Twój własny tekst. Gdy jest pusty, używane są standardowe wytyczne pola, które naciskasz. Znaczniki są zastępowane danymi tego produktu. |

Pole Instruction zachowuje tekst ostatniego uruchomienia. Po naciśnięciu jednego przycisku pole pokazuje użyte wytyczne, a następny przycisk użyje ich ponownie. Wyczyść pole, zanim naciśniesz przycisk innego pola.

#### Generate

Każda karta ma przycisk **Fill**: **Description** ("The long text on the product page, with a short intro and a feature list."), **Short description**, **Name**, **Meta title**, **Meta description** i **Tags**. Tekst jest **od razu zapisywany w produkcie** i pokazywany pod kartami wraz z liczbą tokenów. Karta **SEO pack** ma przycisk **Fill all**; wypełnia nazwę, oba opisy i oba pola meta w jednym zapytaniu i odpowiada "SEO pack saved. Refresh the product to see it.".

Ważne: formularz produktu otwarty w przeglądarce nadal zawiera stare teksty. Przeładuj stronę produktu, zanim klikniesz **Save** w PrestaShop, w przeciwnym razie stare teksty nadpiszą nowe.

#### Simulate

Te same karty z przyciskiem **Try**. Tekst jest pokazywany na stronie, a produkt nie jest zmieniany. Użyj tego do porównania promptów i modeli, zanim moduł zacznie zapisywać.

#### Photos

![Photos sub-tab](https://mypresta.eu/docs/images/docs/myaimistral-product-photos.webp)

1. Kliknij **Find pages**. Model proponuje strony, które prawdopodobnie pokazują produkt, a moduł wyświetla znalezione na nich zdjęcia.
2. Zaznacz zdjęcia, które chcesz. Komunikat brzmi "Tick the photos you want, then add them to this product.".
3. Kliknij **Add selected to this product**. Zdjęcia są pobierane i dołączane do produktu. Komunikat brzmi "Done. Reload the product to see the new photos." lub podaje liczbę dodanych.

Gdy wyszukiwarka jest wyłączona, zakładka o tym informuje i wskazuje Settings – General. Inne komunikaty: "No photos were found on the suggested pages.", "The search failed." i "The photos could not be added.".

#### History

Tabela z kolumnami **When**, **Type**, **Status** i przyciskiem **Restore** dla ostatnich 50 zapytań dotyczących produktu. **Restore** pyta "Restore the previous value?", przywraca poprzedni tekst i odpowiada "Content successfully restored. Refresh this page to see changes.". Przycisk jest pokazywany tylko przy udanych zmianach, które zachowały poprzedni tekst. Jeśli go nie ma, strona pokazuje "No generations for this product yet.".

### 3.17 Przyciski "Generate with AI" obok pól

Na stronie edycji produktu mały przycisk z logo Mistral znajduje się obok edytorów pól **Description**, **Short description**, **Meta title** i **Meta description**. Na stronie edycji kategorii znajduje się obok **Description**, **Additional description**, **Meta title** i **Meta description**.

1. Kliknij przycisk. Jeśli sklep ma więcej niż jeden język, wybierz **Current language**, **All languages** lub **Cancel**.
2. Poczekaj. W trakcie zapytania przycisk pokazuje stan zajętości.
3. Tekst pojawia się w polu. Kliknij **Save** w produkcie lub kategorii, aby go zachować. Do tego momentu nic nie jest zapisane.

Rekord musi już istnieć. Przy nowym produkcie przycisk odpowiada "Save the product once before generating.", a przy nowej kategorii "Save the category once before generating.". Błędy pojawiają się w okienku komunikatu, np. "Generation failed.".

Te przyciski zawsze używają standardowych wytycznych pola, a nie Twoich szablonów. Zasady firmowe, budżet i kontrola jakości ze Studio oraz model z Settings nadal obowiązują.

### 3.18 Inne skróty

| Miejsce | Co robi |
|---|---|
| Ikona różdżki na górnym pasku | Otwiera małe okno: opcjonalny **Template**, pole tekstowe i **Generate**. Odpowiedź jest pokazywana w oknie; skopiuj ją tam, gdzie jej potrzebujesz. Nic nie jest zapisywane, a znaczniki nie są zastępowane. Ukryj ikonę przez **Admin Top Bar CTA** w Settings – General. |
| Lista produktów | Przycisk **My AI Mistral** obok akcji zbiorczych lub paska narzędzi w **Catalog > Products** otwiera stronę Generate. |
| PrestaShop Dashboard | Mały panel ze skrótami **Mass content**, **Log** i **Cron** oraz linkiem do wsparcia MyPresta.eu. |

## 4. Front sklepu

My AI Mistral nie ma części widocznej dla klientów. Nie dodaje bloków, stron, skryptów ani stylów do stron Twojego sklepu, a klienci nie widzą, że moduł istnieje. Jego dwa adresy we froncie są używane tylko przez panel administracyjny i przez Twój harmonogram.

### 4.1 Adresy

| Adres | Używany przez | Co zrobić |
|---|---|---|
| /module/myaimistral/cron | Twój harmonogram (sekcja 3.12) | Wywołuj go z sekretem i akcją, jak pokazano w sekcji 3.12. |
| /module/myaimistral/ajax | Przyciski w panelu administracyjnym | Nie wywołuj go ręcznie i nie wstawiaj do harmonogramu. |

### 4.2 Co odpowiada adres crona

Adres odpowiada zwykłym tekstem. Uruchomienie zatrzymuje się przy pierwszym błędzie; pozycje już zakończone pozostają zapisane.

| Odpowiedź | Znaczenie | Co zrobić |
|---|---|---|
| Cron Job feature is disabled. You can enable it from the module settings. | **Enable Cron Feature** to No. | Ustaw Yes i zapisz. |
| The token does not exist or it's wrong! | Sekret jest brakujący, błędny lub stary. | Skopiuj aktualny sekret z formularza. |
| Invalid action! | Brakuje części `action` lub jest błędnie napisana. | Dodaj `&action=generateProductContent` lub `&action=generateCategoryContent`. |
| updatedField parameter is wrong! | Pole nie jest jednym z dozwolonych. | Wybierz pole ponownie i zapisz formularz. |
| All must include all mandatory parameters! | Zapisane ustawienie jest puste. | Zapisz formularz ponownie, z wybranym językiem i szablonem. |
| productTarget parameter is wrong! Allowed values: … | Wartość celu jest nieznana. | Wybierz ponownie **Selected Products**. To samo dotyczy formularza kategorii. |
| No valid product IDs provided. | **Product ID list** zawiera tekst, ale żadnej poprawnej liczby. | Popraw listę lub ją opróżnij. |
| No products to update. / No categories to update. | Nic nie pasuje do ustawień. | Zmień filtry lub cel albo przyjmij, że praca jest skończona. |
| 5 products have been updated. / 5 categories have been updated. | Uruchomienie zakończone. Liczba to liczba pozycji. | Sprawdź szczegóły w History. |
| 5 pending products. | Debug jest włączony; nic nie zostało zapisane. | Ustaw **Enable Debug** na No. |
| Error! followed by a text | Dostawca zwrócił błąd. | Przeczytaj tekst, zobacz sekcję 5.2. |
| Error! The model returned an empty response. | Mistral nie wysłał tekstu. | Zwiększ **Max Tokens** lub zmień szablon. |
| Error! Could not save product 12: … | PrestaShop odrzucił tekst dla tego produktu. | Przeczytaj podaną przyczynę; uruchomienie zatrzymało się w tym miejscu. |

## 5. Problemy

### 5.1 Instalacja i menu

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| Instalator informuje, że moduł wymaga PHP 7.0 lub nowszego | Serwer działa na starszym PHP. | Zmień wersję PHP w panelu hostingu i zainstaluj ponownie. |
| "Could not create the module database tables." | Użytkownik bazy danych nie może tworzyć tabel. | Nadaj użytkownikowi to uprawnienie lub zwróć się do hostingodawcy. |
| Brakuje pozycji menu AI Content Generator | Stary cache, moduł jest wyłączony lub profil pracownika nie ma uprawnień. | Wyczyść cache, włącz moduł i sprawdź **Administration > Permissions** dla profilu. |
| Strona produktu nie ma panelu My AI Mistral w zakładce Modules | **Product edit page Form** i **Product Edit History** są oba Disabled albo strona jest w cache. | Włącz ustawienie w Settings – General i przeładuj stronę produktu. |

### 5.2 Połączenie z Mistral AI

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| "The Mistral API key is not set. Add it in the module settings." | Klucz nie jest zapisany. | Wklej klucz w Settings – Mistral. |
| "Mistral AI API KEY field is invalid!" | Mniej niż 10 znaków i brak zapisanego klucza. | Skopiuj cały klucz z konsoli. |
| "Mistral AI API Error (401): …" | Klucz jest błędny, unieważniony lub z innego konta. | Utwórz nowy klucz i wklej go ponownie. |
| "Mistral AI API Error (429): …" | Osiągnięto limit Mistral. | Odczekaj minutę i spróbuj ponownie, używaj mniejszych partii lub zwiększ swój plan. |
| "Mistral request timed out after N seconds…" | Model jest wolny lub tekst jest długi. | Zwiększ **API timeout (seconds)** w Settings – General albo użyj szybszego modelu. |
| "The request timed out or the shop blocked it." | Serwer, zapora lub front sklepu zablokował zapytanie. | Zezwól na wychodzące HTTPS do API Mistral i udostępnij adres frontu sklepu. |
| Nie znaleziono modelu | Nazwa modelu, z którego Twoje konto Mistral nie może korzystać. | Wybierz inny model z listy. |
| Lista Model przełączyła się na gpt-4o po usunięciu modelu | Moduł wraca do starej nazwy domyślnej. | Wybierz ponownie model Mistral i zapisz. |
| "Error! Invalid token!" | Sekret w otwartej stronie panelu administracyjnego nie zgadza się już z tym w sklepie, np. po ponownej instalacji. | Przeładuj stronę. |

### 5.3 Generowanie

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| "Error! Content retrieve has failed! Details: …" | API zwróciło błąd. Szczegóły go nazywają. | Przeczytaj szczegóły i wiersz w History. |
| "Monthly generation budget reached. Raise it in the studio settings or wait until next month." | Limit ze Studio został wykorzystany. | Zwiększ budżet lub poczekaj do następnego miesiąca. |
| "The reply was rejected because it contains a forbidden word from the studio settings." | Quality gate znalazła słowo z Twojej listy. | Edytuj listę lub prompt i uruchom ponownie. |
| "The model returned an empty response." lub "The model hit the token limit before returning any text…" | **Max Tokens** jest zbyt niskie albo model zużył je na "myślenie". | Zwiększ **Max Tokens**. |
| "The response was blocked by the provider content filter. Try rewording the prompt." | Mistral odmówił przetworzenia treści. | Zmień sformułowanie promptu. |
| "Error! Prompt is missing or too short!" | Prompt ma mniej niż 4 znaki. | Napisz dłuższe polecenie lub zostaw pole puste. |
| Meta tytuł lub meta opis kończy się nagle w uruchomieniu crona | Cron przycina meta tytuły do 69, a meta opisy do 159 znaków. | Poproś w prompcie o krótszy tekst. |
| Produkt po generowaniu pokazuje stary tekst | Formularz produktu otwarty w przeglądarce został zapisany na wierzchu. | Przeładuj stronę produktu, zanim klikniesz Save. |
| Wiersz mówi "skipped" | Pole miało tekst, a Ty wybrałeś Skip if filled. | Wybierz Replace, aby nadpisać. |
| Te same wytyczne są użyte dla dwóch pól | Pole Instruction nadal zawiera poprzednie wytyczne. | Wyczyść pole, zanim naciśniesz inne pole. |
| Name lub Additional description w Generate – Categories dostaje tekst podobny do opisu | Pusty prompt używa dla tych dwóch pól wytycznych do opisu. | Wpisz własny prompt. |
| "Error! This log entry has no previous value to restore." | Wiersz nie zachował starego tekstu albo lista została wyczyszczona. | Moduł nie może odzyskać starego tekstu. |
| "Error! This PrestaShop version does not support the category Additional Description field." | Starsza wersja PrestaShop. | Pomiń to pole. |

### 5.4 Zdjęcia i New product

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| Zakładka Photos informuje, że wyszukiwarka jest wyłączona | **AI Image Finder** jest Disabled. | Włącz go w Settings – General lub Images i przeładuj stronę produktu. |
| "No photos were found on the suggested pages." | Zaproponowane strony nie mają użytecznych zdjęć. | Kliknij **Find pages** ponownie lub dodaj zdjęcia ręcznie. |
| "The photos could not be added." | Serwer nie mógł ich pobrać. | Wybierz inne zdjęcia. |
| "Failed to parse AI response. Please try again." | Model zwrócił dane, których moduł nie potrafi odczytać. | Kliknij **Generate data** ponownie lub zwiększ **Max Tokens**. |
| "Generate the product first." | Kliknięto **Create product** przed **Generate data**. | Najpierw wygeneruj. |
| "Prompt is required" | **What is the product?** jest puste. | Opisz produkt. |

### 5.5 Cron

| Objaw | Przyczyna | Co zrobić |
|---|---|---|
| Adres odpowiada, ale nic się nie zmienia | **Enable Debug** jest Yes. | Ustaw No i zapisz. |
| Adres informuje, że funkcja jest wyłączona | **Enable Cron Feature** to No. | Ustaw Yes. |
| Sekret zmienił się sam | Sekret krótszy niż 24 znaki został zastąpiony. | Skopiuj nowy sekret z formularza i zaktualizuj harmonogram. |
| Te same produkty są nadpisywane za każdym razem | **Product Categories** jest zaznaczone (zobacz sekcję 3.12). | Pozostaw drzewo kategorii puste i użyj **Product ID list**. |
| Cron używa złego szablonu | Formularz wyświetlał najnowszy szablon i ten wybór został zapisany. | Wybierz właściwy **Prompt Template** i zapisz. |
| "Generate Token" nic nie robi | Skrypt tego przycisku nie jest dostarczany w tej wersji. | Wpisz nowy sekret samodzielnie. |
| "Command:" w formularzu nie pokazuje sekretu | Pokazuje tylko goły adres. | Zbuduj adres jak w sekcji 3.12. |
| Adres kończy się przekroczeniem czasu | Zbyt wiele pozycji na jedno wywołanie. | Zmniejsz **Product to update**. |
| Po pewnym czasie wszystko jest przetwarzane od nowa | **Clear list** w History usunęło log, który oznacza zakończone pozycje. | Nie czyść History, gdy działa cron, albo użyj **Product ID list**. |

### 5.6 Teksty wspominające OpenAI lub ChatGPT

Moduł powstał na bazie wcześniejszego modułu dla innego dostawcy AI. Kilka tekstów nadal pokazuje starą nazwę. Nie wpływają one na działanie modułu.

| Gdzie | Co widzisz | Znaczenie |
|---|---|---|
| Settings – Mistral | Przykład nazwy modelu w polu dodawania to nazwa GPT; komunikaty "OpenAi Settings Updated" i "OpenAi Model field is invalid!". | Tylko przykłady i sformułowania. Wpisz nazwę modelu Mistral. |
| Generate – Products | "OpenAi content" w **Update only**. | Oznacza treść z tego modułu. |
| Generate pages | Przycisk **Module settings**. | Stary skrót, który nie otwiera tego modułu. Użyj paska menu. |
| History | Dostawca pokazuje "openai". | Tylko etykieta. |

## 6. Dla programisty

### 6.1 Przegląd

| Element | Wartość |
|---|---|
| Nazwa modułu | `myaimistral` |
| Nazwa wyświetlana | My AI Mistral - AI content generation |
| Wersja | 1.0.0 |
| Klasa główna | `myaimistral` (`myaimistral.php`) |
| PrestaShop | 1.6 do 9.99.99 |
| PHP | 7.0.0 lub nowszy (sprawdzany przy instalacji, stała `MIN_PHP_VERSION`) |
| Baza API | `https://api.mistral.ai/v1` (`/chat/completions`, `/models`) |
| Prefiks konfiguracji | `MYPRESTA_MYAIMISTRAL_` |
| Tabele | `PREFIX_myaimistral_prompt`, `PREFIX_myaimistral_log` |
| Prefiks CSS | `.mam-` |
| Parametry URL | `mam_tab`, `mam_sub`, `mcg_preset`, `mam_from`, `mam_to` oraz `stats_*` w History |

Foldery: `controllers/admin`, `controllers/front`, `src` (klasy ładowane automatycznie `OpenAIService` i `Studio` w przestrzeni nazw `MyAIMistral`), `lib` (sprawdzanie aktualizacji, pomoc sekcji, zgodność z PrestaShop 9), `views/templates`, `views/js`, `views/css`, `translations`.

Moduł nie ma override i nie ma szablonów frontu. Pomoc przy polach jest pisana za pomocą helpera `fieldHelp($does,$how,$effect)`, który buduje tekst "What it does / How to configure / Effect" w każdym `desc` HelperForm.

### 6.2 Kontrolery administracyjne, hooki i routing

| Klasa kontrolera | Nazwa zakładki | Przeznaczenie |
|---|---|---|
| `AdminMyAIMistralMain` | AI Content Generator (menu entry) | Przekierowuje do `AdminModules&configure=myaimistral`. |
| `AdminMyAIMistral` | Mass Content Creator | Strony Generate (produkty i kategorie). |
| `AdminMyAIMistralProductCreator` | AI Product Creator | New product. |
| `AdminMyAIMistralSettings` | Module Settings | Wejście do ustawień. |
| `AdminMyAIMistralCron` | Cron Job Settings | Formularze crona. |
| `AdminMyAIMistralUsage` | Module Log and Usage | History. |
| `AdminMyAIMistralImageFinder` | AI Image Finder | Strona Images i akcje zdjęć `searchImages`, `extractImages`, `saveImages`. |

Kontrolery administracyjne przekierowują do `AdminHome`, gdy moduł jest nieaktywny.

Hooki rejestrowane przy instalacji: `displayBackOfficeHeader` (zasoby i wartości `Media::addJsDef`, takie jak `myaimistralField`, `myaimistralAdminLink`, `mamHelpLabels`), `displayBackOfficeTop` (ikona górnego paska i lista rozwijana), `displayAdminProductsExtra` i `actionProductFormBuilderModifier` (zakładka produktu), `actionProductGridDataModifier` (lista produktów), `dashboardZoneTwo` (panel PrestaShop Dashboard), `displayAdminProductsMainStepLeftColumnMiddle` i `displayAdminProductsMainStepLeftColumnBottom` (puste), `displayHeader` i `displayFooter` (puste).

Nawigacja wewnątrz strony modułu używa parametrów URL:

| Parametr | Wartości | Znaczenie |
|---|---|---|
| `mam_tab` | dashboard, settings, updates (strona modułu); pozostałe zakładki to kontrolery | Główna zakładka na stronie konfiguracji modułu. |
| `mam_sub` | general, openai, studio, templates, playground (settings); products, categories (Generate) | Podzakładka. `openai` to zakładka Mistral. |
| `mcg_preset` | today, 7, 30, 90, month, all | Gotowy okres Dashboard. |
| `mam_from`, `mam_to` | `YYYY-MM-DD` | Własny zakres Dashboard. |
| `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q` | zobacz History | Filtry History. `clear_log` usuwa log. |

### 6.3 Kontrakt crona

```text
GET /module/myaimistral/cron?secret=SECRET&action=generateProductContent
GET /module/myaimistral/cron?secret=SECRET&action=generateCategoryContent
```

| Reguła | Działanie |
|---|---|
| Przełącznik | `MYPRESTA_MYAIMISTRAL_ENABLE_CRON` nie może być równe 0. |
| Uwierzytelnianie | `secret` musi być równy `SECRET` lub `CAT_SECRET`. Każdy działa dla każdej akcji. |
| Opcjonalne nadpisania (produkty) | `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `categories`, `productIds`. Zastępują zapisane wartości tylko dla tego jednego wywołania. |
| Opcjonalne nadpisania (kategorie) | `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug`. |
| Dozwolone pola | Produkty: name, description, description_short, meta_title, meta_description, tags. Kategorie: name, description, meta_title, meta_description, additional_description. |
| Cele | `pendingMistral`: brak udanego wiersza logu dla pozycji. `pendingField`: brak udanego wiersza logu typu `product_FIELD` lub `category_FIELD`. `emptyField`: pole jest puste w danym języku. Wiersze o statusie `error` się nie liczą. |
| Kolejność i limit | `ORDER BY id ASC LIMIT n`. Zapytania o kategorie zaczynają się po `PS_HOME_CATEGORY`. |
| Debug | Gdy `debug` wynosi 1, wypisywane są SQL, wybrane pozycje i końcowe prompty, a nic nie jest zapisywane. Zapisana wartość debug równa 1 także zatrzymuje zaplanowane zapisywanie. |
| Przycinanie | nazwa 128, opis krótki 799, meta tytuł 69, meta opis 159. Tagi przechodzą przez `Tag::addTags`. |
| Sekrety | `ensureLongSecrets()` zastępuje sekrety krótsze niż 24 znaki. |
| Log | Każda zapisana pozycja zapisuje wiersz z `method` `cron` oraz starą i nową wartością. |

Filtr kategorii w cronie produktów jest zbudowany jako `... AND p.id_product IN (...) OR p.id_category_default IN (...)` bez nawiasów, więc produkty z zaznaczoną kategorią domyślną omijają pozostałe warunki. Filtr Generate – Products używa nawiasów i nie jest tym dotknięty.

### 6.4 Kontroler AJAX

`/module/myaimistral/ajax` to frontowy kontroler modułu. Każde wywołanie niesie `secret_token` (wartość `TOKEN`) i odpowiada JSON-em `{status, msg, date}`.

| Akcja | Przeznaczenie |
|---|---|
| `initiatePrompt` | Playground i górny pasek. Może przenosić `id_category`, `id_cms` lub `id_manufacturer`, aby zastąpić `{category_*}`, `{cms_title}`, `{brand_name}`, `{brand_description}`, `{brand_short_description}`. |
| `updateProduct` | Generuje jedno pole produktu. Zachowania: `replace`, `keep`, `keep_top`, `keep_end`, `single_product` (bez zapisu). `keep` odpowiada statusem `skipped`. |
| `updateCategory` | To samo dla kategorii (`single_category` niczego nie zapisuje). |
| `generateSeoPack` | Zapisuje nazwę, opisy i pola meta w jednym zapytaniu. |
| `generateAltTexts` | Zapisuje teksty alternatywne obrazów. Brak przycisku w interfejsie. |
| `initiateProductRestore` | Przywraca poprzednią wartość z wiersza logu. |
| `updateSettings` | Zapisuje Max Tokens, Temperature, Top P i kary. |

Token jest drukowany na stronach panelu administracyjnego, a kontroler nie sprawdza sesji pracownika. Traktuj token jako sekret.

`Studio::gate()` stosuje zasady firmowe, miesięczny budżet (liczy wiersze, które nie są błędami) i kontrolę zakazanych słów. `OpenAIService` wywołuje Mistral przez cURL, utrzymuje timeout w przedziale od 10 do 600 sekund, ponawia do sześciu razy bez parametrów odrzuconych przez API (zapamiętywanych w `MODEL_CAPS`) i luzuje weryfikację SSL tylko na localhost. Kontroler ajax wydłuża PHP `max_execution_time` tak, aby odpowiadał timeoutowi.

### 6.5 Klucze konfiguracji

Wszystkie klucze zaczynają się od `MYPRESTA_MYAIMISTRAL_`.

| Sufiks klucza | Domyślnie | Przeznaczenie |
|---|---|---|
| `LIVE_MODE` | 0 | Live mode. |
| `DEBUG_MODE` | 0 | Debug mode. |
| `TOPCTA` | 1 | Admin Top Bar CTA. |
| `PRODUCT` | 1 | Product edit page Form. |
| `PRODUCT_LOG` | 1 | Product Edit History. |
| `TOKEN` | losowy | Sekret AJAX. |
| `SECRET` | losowy | Sekret crona produktów. |
| `CAT_SECRET` | losowy | Sekret crona kategorii. |
| `API_KEY` | pojedyncza spacja | Klucz Mistral. |
| `MODEL` | mistral-small-latest | Aktywny model. |
| `EXTRA_MODELS` | pusty | Modele dodane przez sprzedawcę, po jednym w wierszu. |
| `MODEL_CAPS` | pusty | Parametry odrzucone dla danego modelu. |
| `TEMPERATURE` | 0.7 | Temperatura próbkowania. |
| `MAX_TOKENS` | 3200 | Limit odpowiedzi. |
| `TOP_P` | 1 | Top P. |
| `FREQ_PEN`, `PRES_PEN` | 0 | Kary. |
| `TIMEOUT` | 120 | Sekundy, od 10 do 600. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | pusty | Teksty Studio. |
| `BUDGET` | 0 | Miesięczny limit zapytań. |
| `QUALITY` | 1 | Kontrola zakazanych słów. |
| `IMAGEFINDER_ENABLE` | 1 | Przełącznik wyszukiwarki zdjęć. |
| `IMAGEFINDER_PROMPT` | tekst wbudowany | Polecenie wyszukiwarki zdjęć. |
| `ENABLE_CRON` | 0 | Przełącznik crona. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | 6 | Przypomnienie o interwale (6 to Every Hour). |
| `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug`, `productIdsList`, `categories` | description, pendingMistral, 5, domyślny język sklepu, pusty, 0, pusty, pusty | Formularz crona produktów. |
| `catupdatedField`, `categoryTarget`, `categoriesToUpdate`, `catlanguageId`, `catpromptTemplateId`, `catdebug` | description, pendingMistral, 5, domyślny język sklepu, pusty, 0 | Formularz crona kategorii. |

Filtry strony Generate używają tego samego prefiksu: `CATEGORIES`, `BRANDS`, `STATUS`, `STOCK`, `HISTORY`, `PROD_IDS`, `PROD_REF`, `PROD_DATE_FROM`, `PROD_DATE_TO`, `PROD_MIN_ID`, `PROD_MAX_ID`, `PROD_LIMIT`, `CATEGORIESC`, a także `FIELD`, `LANGUAGE`, `CONTENT`, `DELAY` i `EXISTING` ze starego formularza kategorii. Są zapisywane przy każdym żądaniu kontrolera Generate i nie są usuwane przy odinstalowaniu. Wartość Product IDs jest wstawiana do zapytania tak, jak została wpisana, po usunięciu spacji, więc udostępniaj tę stronę tylko zaufanym pracownikom.

### 6.6 Baza danych

| Tabela | Kolumny | Uwagi |
|---|---|---|
| `myaimistral_prompt` | `id_prompt`, `status`, `title`, `prompt`, `date_generated` | 16 wierszy przy instalacji. |
| `myaimistral_log` | `id_log`, `type`, `method`, `status`, `ai_service`, `model`, `prompt`, `reply`, `error_message`, `http_code`, `duration_ms`, `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, wartości pól `old_*` i `new_*`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `date_updated` | Kolumny tokenów są dodawane na żądanie przez `ensureUsageColumns()`. Obie tabele są usuwane przy odinstalowaniu. |

Wartości `type` to na przykład `general`, `singleCategory`, `singleCMS`, `singleBrand`, `product_name`, `product_description`, `product_description_short`, `product_meta_title`, `product_meta_description`, `product_tags`, `category_description` i `error`. Wartości `method` to `initiatePrompt`, `updateProduct`, `updateCategory` i `cron`.

### 6.7 Elementy front-endu

| Element | Uwagi |
|---|---|
| Klasy | Style administracyjne zaczynają się od `.mam-` (nawigacja, dashboard, karty, chipy, kafelki, szuflada pomocy). Panel produktu używa `.myaimistral-ui`, a przyciski przy polach używają `.myaimistral-field-btn`. |
| `views/js/back.js` | Playground, przyciski panelu produktu, masowy runner, New product, restore, zakładki, lista rozwijana górnego paska. Atrybuty danych panelu produktu: `data-myaimistral`, `data-myaimistral-product`, `data-mam-fill`, `data-mam-for`. |
| `views/js/product-fields.js` | Przyciski przy polach na stronach produktu i kategorii. Czyta `window.myaimistralField`. |
| `views/js/image-finder.js` | Wyszukiwanie i import zdjęć. |
| `views/js/admin-products-bulk.js` | Przycisk na liście produktów. Czyta `myaimistralAdminLink`. |
| Style | `back.css`, `admin-nav.css`, `stats.css`. |

### 6.8 Rozszerzanie

- Nowe szablony promptów: wstaw wiersz do `myaimistral_prompt` ze `status` 1.
- Nowe znaczniki: rozszerz konstruktory promptów produktu i kategorii w `controllers/front/ajax.php` oraz w `controllers/front/cron.php`. Znaczniki sklepu obsługuje `applyShopShortcodes()`.
- Nowe modele: dodaj je w Settings – Mistral albo dopisz nazwę do wbudowanej listy w `myaimistral.php`.
- Inny dostawca: zmień bazowy URL i treść zapytania w `src/OpenAIService.php`. Cała reszta komunikuje się wyłącznie z tą klasą.
- Tłumaczenia: używaj `$this->l()` w module i `trans()` w kontrolerach w PrestaShop 8 i 9. Teksty znajdują się w `translations/`.

## 7. Pomoc

Strona produktu: https://mypresta.eu/modules/administration-tools/my-ai-mistral.html

Aby uzyskać pomoc z modułem, zaloguj się na mypresta.eu, otwórz **contact** i wybierz **Support for paid modules**. Opisz problem, podaj wersje PrestaShop i PHP oraz tekst komunikatu, który widzisz. Nigdy nie wysyłaj klucza API ani sekretu crona.
