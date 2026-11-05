---
title: My AI Gemini - AI content generation - dokumentacja i instrukcja obsługi
description: Przewodnik konfiguracji, codziennej pracy i rozwiązywania problemów dla właścicieli sklepów, którzy mają już zainstalowany moduł My AI Gemini w panelu administracyjnym PrestaShop.
sidebar:
  label: My AI Gemini - AI content generation - dokumentacja i instrukcja obsługi
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product and Category Descriptions with Gemini na MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-gemini.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ai-artificial-intelligence/product-and-category-descriptions-with-gemini/)
>
> ---


Zrzuty ekranu w tej instrukcji pochodzą z angielskiego panelu administracyjnego (back office). Nazwy wszystkich przycisków i pól są zapisane dokładnie tak, jak wyświetlają się na ekranie.

## 1. Wymagania

Zanim zaczniesz, sprawdź, czy sklep i serwer spełniają poniższe warunki.

- **PrestaShop:** 1.6, 1.7, 8 i 9 (wszystkie wersje od 1.6 do 9.99.99).
- **PHP:** 7.0 lub nowszy. Instalator odmawia kontynuacji na starszym PHP i pokazuje komunikat "This module requires PHP 7.0.0 or newer. This server is running PHP …".
- **Rozszerzenia PHP:** cURL (każde zapytanie do Gemini i każde pobranie strony), JSON, DOM (odczyt stron internetowych dla funkcji New product i wyszukiwania zdjęć), mbstring oraz fileinfo (sprawdzanie pobranych obrazów).
- **Połączenia wychodzące:** serwer musi mieć możliwość otwierania bezpiecznych połączeń (HTTPS) z usługą Google Gemini. Jeśli serwer blokuje połączenia wychodzące, nic nie zostanie wygenerowane.
- **Inne moduły:** moduł nie wymaga żadnego innego modułu.
- **Konto Google:** potrzebujesz własnego klucza API Google Gemini. Utworzysz go na stronie https://aistudio.google.com/apikey – trzymaj go w tajemnicy. Google nalicza opłaty lub limity zgodnie z Twoim własnym kontem Google, a nie przez ten moduł.
- **Czas i rozmiar:** każde pole to jedno zapytanie do Gemini. Długie teksty i wolne modele mogą potrzebować ponad minuty na jedno zapytanie. Duże uruchomienie masowe lub duża partia crona trwa tyle, ile wszystkie jej zapytania razem, dlatego zaczynaj od małych list.

## 2. Instalacja

1. Otwórz **Modules**, a następnie **Module Manager**.
2. Kliknij **Upload a module** i upuść plik ZIP albo wgraj go swoją zwykłą metodą.
3. Gdy moduł pojawi się na liście, kliknij obok niego **Install** i potwierdź.
4. Po instalacji w lewym menu, w sekcji **Modules**, pojawia się nowa pozycja **AI Content Generator**. Kliknij ją: otworzy się **Dashboard** modułu. Te same ekrany są dostępne także z **Module Manager**, przez **Configure**.
5. Zanim cokolwiek zostanie wygenerowane, otwórz **Settings**, potem **Gemini**, wklej klucz w polu **Google Gemini API KEY** i zapisz (szczegóły w rozdziale 3).

Instalacja tworzy 16 gotowych szablonów promptów (nazwy produktów, opisy, meta tytuły, meta opisy i tagi), dzięki czemu możesz od razu wypróbować moduł. Nie czyści pamięci podręcznej sklepu. Jeśli pozycja menu się nie pojawi, otwórz jeszcze raz dowolną stronę panelu administracyjnego: moduł przywraca pozycję menu przy każdym załadowaniu strony panelu.

**Odinstalowanie.** Odinstalowanie usuwa pozycję menu **AI Content Generator**, kasuje szablony promptów oraz całą historię (znikają więc także listy przywracania na produktach) i usuwa ustawienia modułu, w tym klucz API i sekrety crona. Nie rusza tekstów, zdjęć i produktów, które zostały już napisane lub utworzone za pomocą modułu. Kilka filtrów ekranowych, których używałeś na stronach **Generate**, może pozostać zapisanych w ustawieniach sklepu – są nieszkodliwe. Ponowna instalacja zaczyna od czystego stanu: wracają 16 domyślnych szablonów, a stare ustawienia, szablony i historia nie są przywracane.

## 3. Konfiguracja i codzienna praca w panelu administracyjnym

### 3.1 Cały proces krok po kroku

1. **Połącz Gemini.** **Settings**, **Gemini**: wklej klucz API, zostaw lub zmień model, zapisz.
2. **Przetestuj.** **Settings**, **Playground**: wpisz krótkie polecenie i naciśnij **Generate**. Jeśli zobaczysz odpowiedź, połączenie działa. Nic nie jest zapisywane w Twoim katalogu.
3. **Ustaw styl sklepu (opcjonalnie).** **Settings**, **Studio**: wpisz głos marki, odbiorców, ton, słowa do zachowania i słowa zakazane.
4. **Przygotuj instrukcje.** **Settings**, **Prompt templates**: zostaw szablony domyślne lub dodaj własne. Włączone szablony są oferowane we wszystkich pozostałych miejscach.
5. **Wybierz sposób pracy:**
   - Jeden produkt naraz: otwórz produkt, potem **Modules**, **My AI Gemini**, i naciśnij **Fill** przy polu (3.16).
   - Wiele produktów lub kategorii: **Generate**, **Products** lub **Categories** (3.9 i 3.10).
   - Produkt, który jeszcze nie istnieje: **New product** (3.11).
   - Automatycznie, małymi partiami, bez klikania: **Cron** (3.12).
6. **Sprawdź wynik.** **History** wyświetla każde zapytanie z promptem, odpowiedzią, statusem i zużyciem tokenów. **Dashboard** pokazuje te same liczby na wykresach.
7. **Cofnij.** Na produkcie: **Modules**, **My AI Gemini**, **History**: **Restore** przywraca poprzedni tekst.

Teksty są zapisywane bezpośrednio w produkcie lub kategorii, gdy tylko Gemini odpowie, chyba że ta instrukcja mówi inaczej (przyciski **Try**, **Playground**, **Generate data** oraz przyciski **Generate with AI** obok pól, które tylko wstawiają tekst do otwartego formularza, dopóki go nie zapiszesz).

### 3.2 Otwieranie modułu i poruszanie się po nim

Otwórz **AI Content Generator** w lewym menu. Pasek u góry każdego ekranu zawiera pozycje: **Dashboard**, **Settings**, **Generate**, **New product**, **Cron**, **History**, **Images**, a po prawej stronie **Updates**. Najedź myszą na pozycję, aby zobaczyć krótkie objaśnienie. Pod **Settings** pojawia się drugi rząd z pozycjami **General**, **Gemini**, **Studio**, **Prompt templates** i **Playground**. Pod **Generate** drugi rząd pokazuje **Products** i **Categories**.

Okrągły przycisk **Help** na brzegu każdej strony modułu otwiera panel boczny z krótkim objaśnieniem strony, na której jesteś. Jedna linijka w tym panelu nadal odnosi się do konta OpenAI (patrz rozdział 5); używaj swojego klucza Google Gemini.

Do modułu możesz też przejść z **Module Manager** przyciskiem **Configure**, przyciskiem skrótu na górnym pasku (3.18) oraz z linku na liście produktów (3.18).

### 3.3 Dashboard

**Dashboard** to raport. Nigdy nie zapisuje tekstów produktów ani kategorii.

![My AI Gemini – Dashboard z zakresem dat, kartami i wykresami](https://mypresta.eu/docs/images/docs/myaigemini-dashboard.webp)

U góry wybierasz okres. Linia **Active service** zawsze pokazuje Gemini i model zapisany na ekranie **Gemini**.

| Pole | Na start | Co robi |
|---|---|---|
| **Today**, **7 days**, **30 days**, **90 days**, **This month**, **All time** | **30 days** | Szybkie przyciski okresu. Wybrany jest podświetlony. Zmieniają się tylko liczby i wykresy na tej stronie. |
| **From** i **To** | Daty ostatnich 30 dni | Własny okres. Naciśnij **Apply**, aby odświeżyć. Jeśli From jest późniejsze niż To, moduł je zamienia. |
| **Apply** | – | Odświeża karty i wykresy dla wpisanych dat. |
| **Requests** | Liczone z History | Każde zapisane wywołanie w okresie, udane lub nie. |
| **Success** | Liczone z History | Wywołania, które nie zakończyły się błędem. |
| **Errors** | Liczone z History | Wywołania, które zakończyły się błędem. |
| **Tokens sent** | Liczone z History | Łączny rozmiar Twoich poleceń wysłanych do Gemini. |
| **Tokens received** | Liczone z History | Łączny rozmiar odpowiedzi. |
| Wykres **Requests and errors** | – | Wykres liniowy, jeden punkt na dzień. Dla okresów dłuższych niż 120 dni jeden punkt obejmuje tydzień. |
| Wykres **Tokens sent and received** | – | Ten sam okres, dwie linie. |
| Wykres **Requests by model** | – | Wykres słupkowy: ile zapytań obsłużył każdy model. |

Jeśli wykresy są puste, w danym okresie nic nie zostało wygenerowane. Dashboard istnieje też jako mały blok na głównym dashboardzie PrestaShop, ale ten blok nie otrzymuje danych z History, więc jego karty i wykresy pozostają puste. Korzystaj z **Dashboard** modułu.

### 3.4 Settings – General

Otwórz **Settings**, potem **General**. Te przełączniki decydują, co widzą pracownicy w panelu administracyjnym. Zapis nie nadpisuje żadnego tekstu produktu.

![Settings – General](https://mypresta.eu/docs/images/docs/myaigemini-settings-general.webp)

| Pole | Na start | Co robi |
|---|---|---|
| **Live mode** | Disabled | Oznacza, że moduł działa w prawdziwym sklepie. Włącz go w sklepie produkcyjnym. Na kopii testowej zostaw wyłączony, aby zaznaczyć, że to nie jest konfiguracja produkcyjna. Te same narzędzia działają w obu stanach. |
| **Debug mode** | Disabled | Zapisuje dodatkowe komunikaty techniczne w logu PrestaShop (**Advanced Parameters**, **Logs**), gdy wywołanie Gemini się nie powiedzie. Włączaj tylko na czas analizy błędu, potem wyłącz. Klienci tego nigdy nie widzą. |
| **API timeout (seconds)** | 120 | Ile sekund może trwać jedno wywołanie Gemini, zanim moduł się podda. 120 wystarcza do zwykłych opisów. Zwiększ do 600 dla długich tekstów SEO lub wolnych modeli. Wartości poniżej 10 zamieniane są na 10, powyżej 600 na 600, pusta lub nienumeryczna wartość na 120. Krótki limit czasu szybko kończy się błędem i zapisuje go. |
| **Product Edit History** | Enabled | Pokazuje zakładkę **History** z przyciskami **Restore** na stronie produktu (**Modules**, **My AI Gemini**). Wyłączenie ukrywa tę listę. Dawne wiersze i tak pozostają w ogólnej **History** sklepu. |
| **Admin Top Bar CTA** | Enabled | Umieszcza mały przycisk z magiczną różdżką na górnym pasku każdej strony panelu, który otwiera okno z promptem. Wyłączenie usuwa tylko ten przycisk. Menu modułu zostaje. |
| **Product edit page Form** | Enabled | Pokazuje panel generatora w **Modules**, **My AI Gemini** na stronie produktu. Włącz dla redaktorów katalogu. Wyłącz, jeśli mają być używane tylko generowanie masowe i cron. |
| **AI Image Finder** | Enabled | Pokazuje zakładkę **Photos** na stronie produktu. Wyłączenie ją ukrywa. Zdjęcie jest importowane dopiero po zaznaczeniu i potwierdzeniu. |
| **AI Image Search Prompt** | Wbudowane angielskie polecenie z prośbą o 5 adresów stron | Polecenie wysyłane przy szukaniu zdjęć produktu. Słowa {product_name} i {product_description} są zastępowane danymi bieżącego produktu. Zachowaj prośbę o listę adresów stron. Dokładniejszy prompt daje trafniejsze strony. |
| **Save** | – | Zapisuje wszystkie powyższe pola. Komunikat: **Settings Updated**. |

Dwa pola dotyczące zdjęć występują zarówno tutaj, jak i na ekranie **Images** (3.14). To te same dwa ustawienia.

### 3.5 Settings – Gemini

Otwórz **Settings**, potem **Gemini**. Tutaj łączysz konto Google i ustawiasz, jak zróżnicowane ma być słownictwo. Każde generowanie (przyciski przy produktach, uruchomienia masowe, cron, New product, wyszukiwanie zdjęć, Playground) używa tych wartości.

![Settings – Gemini](https://mypresta.eu/docs/images/docs/myaigemini-settings-gemini.webp)

| Pole | Na start | Co robi |
|---|---|---|
| **Google Gemini API KEY** | Empty | Sekret, który pozwala sklepowi korzystać z Twojego konta Gemini. Wklej klucz ze strony https://aistudio.google.com/apikey. Spacje na początku i na końcu są usuwane. Jeśli nie ruszysz pola, zapisany klucz zostaje. Pusty lub błędny klucz powoduje błędy wywołań, a błąd trafia do History. |
| **Model** | gemini-2.0-flash | Model Gemini, który pisze tekst. Wbudowane wybory: gemini-2.0-flash, gemini-2.0-flash-lite, gemini-1.5-flash, gemini-1.5-flash-8b, gemini-1.5-pro, gemini-2.5-flash, gemini-2.5-pro. Kolejne generowanie używa zapisanego modelu. Model, którego Twój klucz nie może użyć, zwraca błąd zamiast tekstu. |
| **Add a Gemini model** (pole z przyciskiem **Add model**) | – | Dodaje nazwę modelu, której nie ma na wbudowanej liście. Wpisz dokładną nazwę ze swojego konta Gemini i naciśnij **Add model**. Nazwa pojawia się w **Model** i jest od razu wybrana. Dodane nazwy mają obok link **Remove**. Wbudowanych nazw nie da się usunąć. |
| **Max Tokens** | 3200 | Górny limit długości odpowiedzi, liczony w tokenach, nie w słowach. Około 256 wystarcza na meta opis, 1000 lub więcej na pełny opis HTML. Niski limit ucina odpowiedź. Wysoki pozwala na dłuższy tekst. Niektóre modele Gemini 2.5 zużywają część tego limitu na „myślenie”, więc dla nich zostaw limit z zapasem. |
| **Temperature** | 0.7 | Jak swobodnie model dobiera słowa. Trzymaj się między 0 a 1. Około 0.2 pasuje do specyfikacji i tekstów meta, około 0.7 do opisów. Niska wartość powtarza podobną strukturę. Wysoka daje bardziej urozmaicone słownictwo i większe ryzyko odejścia od polecenia. |
| **Top P** | 1 | Drugi sposób zawężania wyboru następnego słowa. W tej wersji wartość jest zapisywana, ale nie jest wysyłana do Gemini, więc jej zmiana nie wpływa na odpowiedzi. |
| **Frequency Penalty Value** | 0 | Ma zniechęcać do powtarzania fraz. Zapisywane, ale w tej wersji niewysyłane do Gemini, więc nie ma wpływu na odpowiedzi. |
| **Presence Penalty Value** | 0 | Ma kierować tekst ku nowym wątkom. Zapisywane, ale w tej wersji niewysyłane do Gemini, więc nie ma wpływu na odpowiedzi. |
| **Save** | – | Zapisuje formularz. Komunikat: **OpenAi Settings Updated** (moduł nadal używa tu starszego brzmienia). |

Komunikaty, które możesz zobaczyć na tym ekranie:

| Komunikat | Przyczyna | Co zrobić |
|---|---|---|
| **Google Gemini API KEY field is invalid!** | Pole klucza ma mniej niż 10 znaków i nie ma jeszcze zapisanego klucza. | Wklej cały klucz i ponownie naciśnij **Save**. |
| **OpenAi Model field is invalid!** | Nazwa modelu ma mniej niż 3 znaki. | Wybierz nazwę z listy **Model**. |
| **Google Gemini API Key has been automatically cleaned (whitespace removed).** | Zapisany klucz miał spacje dookoła. | Nic: moduł to naprawił. |
| **Model added.** | Nowa nazwa została zapisana i wybrana. | Naciśnij **Save**, jeśli zmieniłeś też inne pola. |
| **That model is already built in.** | Wpisana nazwa jest już na liście. | Moduł wybiera ją za Ciebie. |
| **Model removed.** | Dodana nazwa została usunięta. | Jeśli był to aktywny model, wybierz ponownie model Gemini (patrz rozdział 5). |
| **Built-in models cannot be removed.** | Próbowałeś usunąć nazwę wbudowaną. | Nic do zrobienia. |
| **Enter a model id such as gpt-4.1.** | Pole nazwy modelu było puste lub zawierało niedozwolone znaki. | Wpisz nazwę Gemini, na przykład gemini-2.5-flash. Przykład w tym komunikacie to pozostałość. |

### 3.6 Settings – Studio

Otwórz **Settings**, potem **Studio**. Studio dodaje zasady „domu” do każdego promptu: przycisków przy produktach, uruchomień masowych, crona i Playground. Puste pola są pomijane. Moduł zawsze też każe Gemini pisać w języku generowanego elementu.

![Settings – Studio](https://mypresta.eu/docs/images/docs/myaigemini-settings-studio.webp)

| Pole | Na start | Co robi |
|---|---|---|
| **Brand voice** | Empty | Mówi modelowi, kto przemawia, aby tekst brzmiał jak Twój sklep. Napisz krótki opis, na przykład: specjalistyczny warsztat, krótkie zdania, bez przesadnych haseł. Zmiana nie przepisuje już zapisanych tekstów. |
| **Audience** | Empty | Nazywa czytelnika, na przykład zawodowi monterzy lub osoby kupujące po raz pierwszy. Nowe odpowiedzi używają słownictwa dopasowanego do tego czytelnika. |
| **Tone** | Empty | Jedno lub dwa słowa określające nastrój: formalny, ciepły, techniczny. Nie zmienia modelu ani temperatury. |
| **Glossary** | Empty | Nazwy marek, materiały i pisownie, które model musi skopiować dokładnie. Jeden termin w wierszu. Terminy spoza listy mogą nadal zostać przeformułowane. |
| **Forbidden words** | Empty | Słowa i frazy, które nie mogą pojawić się w zapisanej odpowiedzi. Jedno w wierszu. Lista jest też wysyłana do modelu jako słowa do unikania. Odrzucenie pasującej odpowiedzi następuje tylko wtedy, gdy **Quality gate** jest włączona. |
| **Monthly generation budget** | 0 | Maksymalna liczba udanych generowań w bieżącym miesiącu kalendarzowym, liczona z History. 0 oznacza brak limitu. Po osiągnięciu limitu nowe zapytania są zatrzymywane z komunikatem o budżecie aż do następnego miesiąca. Nieudane wywołania nie są liczone. |
| **Quality gate** | Enabled | Sprawdza każdą odpowiedź pod kątem **Forbidden words**, zanim cokolwiek zostanie zapisane. Włączona odrzuca pasującą odpowiedź: produkt zostaje bez zmian, a History zapisuje błąd. Wyłączona zapisuje odpowiedź nawet wtedy, gdy zawiera słowo z listy. Przy pustej liście Forbidden words bramka nie ma czego sprawdzać. |
| **Save studio** | – | Zapisuje formularz. Komunikat: **Studio settings saved.** |

### 3.7 Settings – Prompt templates

Otwórz **Settings**, potem **Prompt templates**. Szablon to zapisana instrukcja. Redaktorzy wybierają ją po tytule, zamiast wpisywać za każdym razem to samo polecenie.

![Settings – Prompt templates](https://mypresta.eu/docs/images/docs/myaigemini-settings-templates.webp)

Lista pokazuje kolumny: **ID**, **Title**, **Prompt**, **Status** (kliknij ptaszek lub krzyżyk, aby włączyć albo wyłączyć szablon), **Timestamp**. Każdy wiersz ma **Edit** i **Delete**. Zaznacz kilka wierszy i użyj akcji zbiorczej **Delete** (zostaniesz zapytany "Are you sure you want to delete the selected prompts?"). Zielony przycisk plus nad listą tworzy nowy szablon.

Formularz szablonu:

| Pole | Na start | Co robi |
|---|---|---|
| **Status** | Przełącznik Enabled / Disabled | Pokazuje lub ukrywa szablon na listach używanych na stronie produktu, w oknie promptu na górnym pasku, w generowaniu masowym i w cronie. Włącz szablony, z których ma korzystać Twój zespół. Szkic wyłącz zamiast usuwać. |
| **Prompt title** | Empty (wymagane) | Nazwa widoczna dla redaktorów na liście. Nie jest wysyłana do Gemini. Użyj krótkiej etykiety, na przykład HTML description with features. |
| **Prompt content** | Empty (wymagane) | Polecenie wysyłane do Gemini. Napisz je tak, jak briefowałbyś copywritera: długość, HTML, język. Możesz używać placeholderów (3.19). Podwójne cudzysłowy są przy zapisie zamieniane na pojedyncze. |
| **Save Prompt** | – | Zapisuje szablon. |
| **Go Back to Module Settings** | – | Wraca do listy bez zapisywania. |

Komunikaty: **Prompt template successfully added!**, **Prompt template successfully updated!**, **Prompt template removed.**, **Unable to delete prompt template with id:** z numerem, **Failed to edit prompt template! Please fill the form with the right informations!**.

16 domyślnych szablonów to: Product name 1–2, Product description 1–7 (siódmy osadza linki do zdjęć produktu), Product meta title 1–3, Product meta description 1–3 oraz Product tags. Dwa szablony meta opisu wspominają smartwatch; jeśli sprzedajesz coś innego, zmień je przed użyciem. Teksty szablonów są zapisane w języku, którego sklep używał podczas instalacji.

### 3.8 Settings – Playground

Otwórz **Settings**, potem **Playground**. To brudnopis: wysyła jedno dowolne polecenie do aktywnego modelu i pokazuje odpowiedź na stronie.

![Settings – Playground](https://mypresta.eu/docs/images/docs/myaigemini-settings-playground.webp)

1. Wpisz polecenie w dużym polu ("Ask the model anything about your catalog").
2. Naciśnij **Generate**.
3. Przeczytaj odpowiedź pod przyciskiem wraz z liczbą zużytych tokenów.

Możesz wspomnieć nazwę sklepu, adres sklepu, nazwę produktu, referencję lub cechy, jeśli chcesz, aby odpowiedź opierała się na danych katalogu. Reguły Studio są stosowane. Żaden produkt, kategoria ani pole meta nie jest zmieniane, a wywołanie zapisuje się w History. Jeśli pole jest puste, zobaczysz "Write a prompt first." Użyj Playground, aby przetestować klucz i dopracować prompt, zanim zamienisz go w szablon.

### 3.9 Generate – Products

Otwórz **Generate**, potem **Products**. Generowanie masowe ma dwa kroki. W kroku 1 nic nie jest wysyłane do Gemini.

![Generate – Products](https://mypresta.eu/docs/images/docs/myaigemini-generate-products.webp)

**Krok 1 – filtruj produkty.** Wszystkie filtry są opcjonalne i nie są zapisywane jako ustawienia sklepu.

| Pole | Na start | Co robi |
|---|---|---|
| **Product Categories** | Nic nie zaznaczono | Zostawia produkty znajdujące się w którejkolwiek zaznaczonej kategorii lub mające ją jako kategorię główną. Puste drzewo nie filtruje według kategorii. |
| **Brand** | **Select brand** | Zostawia produkty jednego producenta. Pierwsza opcja oznacza każdą markę. |
| **Product status** | **Active** | **Active** zostawia produkty w sprzedaży, **Disabled** wyłączone, **Both** wszystkie. |
| **Product stock** | **All products** | **Only in stock products** odrzuca produkty bez dostępnej ilości. |
| **Update only** | **Update all** | Korzysta z History. Pierwsza opcja zostawia produkty, których ten moduł nigdy nie opisał. Druga te, które już opisał. Etykiety nadal mówią "OpenAi content" (patrz rozdział 5). |
| **Product IDs** | Empty | Wpisz identyfikatory oddzielone przecinkami, na przykład 12,45,103. Mogą pojawić się tylko te produkty. |
| **Product Reference** | Empty | Wpisz jedną lub więcej referencji oddzielonych przecinkami. |
| **Product Add Date From** / **Product Add Date To** | Empty | Zostawiają produkty utworzone po pierwszej dacie i przed drugą. |
| **Minimum product ID** / **Maximum product ID** | Empty | Zostawiają produkty z tego zakresu identyfikatorów. |
| **Product Limit** | Empty | Maksymalna liczba produktów wczytanych na listę. Za pierwszym razem użyj małej liczby, na przykład 20. |
| **Go to next step** | – | Buduje listę. |
| **Module settings** | – | Przycisk obok **Go to next step**. Otwiera stronę ustawień innego modułu (patrz rozdział 5); zamiast niego użyj **Settings** na pasku modułu. |

**Krok 2 – pisanie.** Strona pokazuje teraz panel **Mass product generation** z tabelą znalezionych produktów (kolumny **ID**, **Reference**, **Result**).

| Pole | Na start | Co robi |
|---|---|---|
| **Template** | **Choose a template** | Kopiuje tekst włączonego szablonu do pola poniżej. Sam tytuł nie jest wysyłany. |
| Duże pole promptu | Empty | Polecenie wysyłane dla każdego produktu. Placeholdery są uzupełniane dla każdego produktu (3.19). Jeśli zostawisz pole puste, używane jest standardowe polecenie dla każdego pola. |
| **What to generate** | **Descriptions** | **Descriptions** pisze opis długi i krótki. **Meta title and meta description** pisze oba pola meta. **Descriptions and meta together** pisze wszystkie cztery. Każde pole to osobne zapytanie. Inne pola (w tym nazwa produktu i tagi) nigdy nie są tu zmieniane. |
| **Existing text** | **Replace** | **Replace** nadpisuje pole. **Skip if filled** zostawia wypełnione pole w spokoju i nic dla niego nie wysyła do Gemini. **Add above** i **Add below** zachowują stary tekst i dołączają nowy przed nim lub po nim. |
| **Languages** | Zaznaczony jest język, którego używasz w panelu administracyjnym | Zaznacz każdy język, który chcesz. Każdy zaznaczony język jest generowany osobno. Co najmniej jeden musi być zaznaczony ("Select at least one language."). |
| **Run on the list below** | – | Uruchamia przebieg. |

Podczas przebiegu linia nad przyciskiem pokazuje postęp, na przykład "3 / 40 – description". Każdy wiersz tabeli pokazuje wynik, taki jak "description: success Content successfully generated and updated to product." lub "description: skipped Product skipped." albo tekst błędu. Przebieg bierze produkty jeden po drugim i od razu zapisuje każdą odpowiedź, więc błąd przy jednym produkcie nie cofa już zapisanych. Nie zamykaj strony, dopóki nie zobaczysz "Finished … products."

### 3.10 Generate – Categories

Otwórz **Generate**, potem **Categories**.

![Generate – Categories](https://mypresta.eu/docs/images/docs/myaigemini-generate-categories.webp)

**Krok 1 – filtruj kategorie.**

| Pole | Na start | Co robi |
|---|---|---|
| **Categories** | Nic nie zaznaczono | Zaznacz kategorie do uwzględnienia. Puste drzewo obejmuje każdą kategorię zgodną ze statusem. |
| **Category status** | **Active** | **Active**, **Disabled** lub **Both**. |
| **Go to next step** | – | Buduje listę. Nic jeszcze nie jest generowane. |
| **Module settings** | – | Otwiera stronę ustawień innego modułu (patrz rozdział 5). |

**Krok 2 – pisanie.** Panel **Mass category generation** wyświetla kategorie (kolumny **ID**, **Result**).

| Pole | Na start | Co robi |
|---|---|---|
| Duże pole promptu | Empty | Polecenie wysyłane dla każdej kategorii. Możesz użyć {category_name}, {category_description}, {category_parent_name} oraz placeholderów sklepu (3.19). Zawsze wpisz tu prompt: dla kategorii nie ma standardowego polecenia. |
| Lista pól | **Description** | **Description**, **Name**, **Meta title**, **Meta description** lub **Additional description**. Zapisywane jest tylko to pole. |
| Lista istniejącego tekstu | **Replace** | **Replace** nadpisuje. **Skip if filled** zostawia wypełnione pole w spokoju. |
| Lista języków | Twój język panelu administracyjnego | Jeden język na przebieg. Uruchom ponownie dla innego języka. |
| **Run on the categories below** | – | Uruchamia przebieg. Każda kategoria jest zapisywana, gdy tylko nadejdzie jej odpowiedź. |

Pod tabelą jest drugi formularz o tytule **Generate category content** z przyciskiem **Generate content**. Niczego nie generuje: tylko wraca do filtra kategorii. Zawsze używaj **Run on the categories below**.

### 3.11 New product

Otwórz **New product**. Ten ekran zamienia krótki opis w szkic produktu, który jeszcze nie istnieje.

![New product](https://mypresta.eu/docs/images/docs/myaigemini-new-product.webp)

| Pole | Na start | Co robi |
|---|---|---|
| **What is the product?** | Empty | Opis (brief). Napisz kilka zdań z materiałami, odbiorcami i nazwami, które mają zostać. Bogatszy opis daje trafniejszy szkic. Pusty opis zostanie odrzucony. |
| **Optional source URL** | Empty | Pełny adres publicznej strony o produkcie. Tekst ze strony (tytuł, opis, cena) jest dodawany do Twojego opisu. Puste pole lub strona, której sklep nie może odczytać, są ignorowane. |
| **Language** | Domyślny język sklepu | Język, w którym zapisywane są nazwa, opisy, meta i tagi. Pozostałe języki nie są uzupełniane. Wybierz domyślny język sklepu, ponieważ PrestaShop oczekuje w nim nazwy. |
| **Default category ID** | 2 | Numer kategorii w Catalog, Categories. 2 to zwykle Home. Nowy produkt trafia do tej kategorii i staje się ona kategorią domyślną. |
| **Generate data** | – | Prosi Gemini o szkic i wypisuje go poniżej jako tekst ustrukturyzowany (nazwa, opisy, meta, tagi, referencja, cena, cechy). Żaden produkt nie jest zapisywany. |
| **Create product** | – | Zapisuje szkic jako nowy aktywny produkt. Ustawia nazwę, opisy, meta, tagi, cechy, referencję i cenę ze szkicu, widoczność wszędzie oraz stan magazynowy 100. Żadne zdjęcia nie są dołączane; dodaj je później (3.16). Linia wyniku: "Product #" z numerem nowego produktu. |

Jeśli nie zapisano klucza API, zobaczysz "Add an API key in the module settings first." Naciśnięcie **Create product** przed **Generate data** pokazuje "Generate the product first." Po utworzeniu sprawdź cenę, podatek i zdjęcia: moduł ustawia pierwszą grupę reguł podatkowych i cenę zasugerowaną przez Gemini.

### 3.12 Cron

Otwórz **Cron**. Cron jest przeznaczony dla serwera, nie dla człowieka: serwer według harmonogramu wywołuje tajny adres internetowy, a sklep za każdym razem uzupełnia małą partię produktów lub kategorii. Nic się nie dzieje, dopóki serwer nie zażąda adresu.

![Cron](https://mypresta.eu/docs/images/docs/myaigemini-cron.webp)

Ekran ma dwa formularze: jeden dla produktów i jeden dla kategorii. Każdy ma własny przycisk **Save**, a po zapisie nie jest wyświetlany żaden komunikat potwierdzenia.

**Formularz crona produktów**

| Pole | Na start | Co robi |
|---|---|---|
| **Enable Cron Feature** | **No** | Przełącznik dla całego crona (produkty i kategorie). Dopóki jest **No**, każde wywołanie jest odrzucane komunikatem "Cron Job feature is disabled. You can enable it from the module settings." Włącz dopiero po zapisaniu pozostałych pól. |
| **Cron Job Secret Token** | Długa losowa wartość | Hasło, które musi znajdować się w adresie. Bez niego sklep odrzuca wywołanie. Zmiana unieważnia stary adres. Przycisk **Generate Token** obok pola może w tej wersji nie działać; jeśli nie działa, wpisz długą wartość samodzielnie. |
| **Update Field** | **description** | Które jedno pole produktu cron przepisuje: **name**, **description**, **description_short**, **meta_title**, **meta_description** lub **tags**. Aby uzupełniać kilka pól, utwórz kilka poleceń crona. |
| **Selected Products** | **pendingGemini** | Które produkty nadal czekają. **pendingGemini**: produkty, których ten moduł nigdy pomyślnie nie opisał (żadne pole). **pendingField**: produkty, dla których wybrane pole nie zostało jeszcze wygenerowane, dzięki czemu jeden katalog można przetwarzać kilkoma zadaniami crona. **emptyField**: tylko produkty, których wybrane pole jest puste w wybranym języku. |
| **Product Categories** | Nic nie zaznaczono | Ogranicza przebieg do zaznaczonych kategorii (ostrzeżenie w rozdziale 5). |
| **Product ID list** | Empty | Jawne identyfikatory produktów oddzielone przecinkami. Znaki inne niż cyfry są przy zapisie usuwane. |
| **Language** | Domyślny język sklepu | Wersja językowa, która jest zapisywana. |
| **Product to update** | 5 products | Wielkość partii na jedno wywołanie: 2, 3, 5, 8, 10, 15, 20, 50, 100, 200, 300, 500 lub 1000. Zacznij od 5 lub 10, aby wolny model nie przekroczył limitu czasu serwera. Produkty są brane w kolejności ID. |
| **Prompt Template** | Pierwszy szablon na liście | Zapisane polecenie używane dla każdego produktu. Placeholdery są uzupełniane dla każdego produktu (3.19). |
| **Enable Debug** | **No** | **Yes** sprawia, że adres wypisuje plan (zapytanie, wybrane produkty, ostateczne prompty) i niczego nie zapisuje. Wyłącz przed użyciem adresu przez harmonogram serwera. |
| **CRON JOB interval** | **Every Hour** | Sugestia wyświetlana dla Twojego własnego harmonogramu. Moduł nie uruchamia harmonogramu. Prawdziwy termin ustaw na serwerze. |
| **Product Cron Job command** | – | Pokazuje początek adresu. W tej wersji linia polecenia na ekranie jest niekompletna (patrz niżej). |
| **Save** | – | Zapisuje ustawienia crona produktów. |

**Formularz crona kategorii** ma własne **Cron Job Secret Token**, **Update Field** (**name**, **description**, **meta_title**, **meta_description**), **Selected categories** (te same trzy tryby), **Language**, **Categories to update** (2–1000), **Prompt Template**, **Enable Debug**, **CRON JOB interval** i **Save**. Zawsze pomija kategorię główną sklepu (root).

**Adres, który podajesz serwerowi.** Nad formularzami ekran wypisuje adres produktów i adres kategorii, każdy kończący się po sekrecie. Serwerowi trzeba też powiedzieć, które zadanie uruchomić. Dopisz to na końcu adresu z ekranu:

| Zadanie | Kompletny adres | Uwagi |
|---|---|---|
| Produkty | `https://your-shop.example/module/myaigemini/cron?secret=PRODUCT_SECRET&action=generateProductContent` | Użyj sekretu z formularza produktów. |
| Kategorie | `https://your-shop.example/module/myaigemini/cron?secret=CATEGORY_SECRET&action=generateCategoryContent` | Linia kategorii na ekranie kończy się `&entity=category`; zastąp to zakończenie przez `&action=generateCategoryContent`. |

Opcjonalne dodatki, które możesz dopisać, aby w jednym poleceniu nadpisać zapisany formularz: dla produktów `updatedField`, `productTarget`, `productsToUpdate`, `languageId`, `promptTemplateId`, `debug=1`, `categories` (identyfikatory oddzielone przecinkami), `productIds`; dla kategorii `updatedField`, `categoryTarget`, `categoriesToUpdate`, `languageId`, `promptTemplateId`, `debug=1`. Wartości, których nie dopiszesz, pochodzą z zapisanego formularza.

**Harmonogram.** W panelu hostingu utwórz zadanie cykliczne, które otwiera kompletny adres, na przykład przez `curl -s "ADDRESS"` co godzinę. Najpierw przetestuj w przeglądarce z **Enable Debug** ustawionym na **Yes**: zobaczysz, które produkty zostałyby przetworzone, oraz ostateczne prompty. Potem ustaw **No** i otwórz adres jeszcze raz. Każde prawdziwe wywołanie aktualizuje jedną partię i kończy działanie.

Odpowiedzi, które możesz zobaczyć po otwarciu adresu:

| Odpowiedź | Przyczyna | Co zrobić |
|---|---|---|
| **N products have been updated.** / **N categories have been updated.** | Partia zadziałała. | Nic. |
| **N pending products.** | Debug jest włączony, nic nie zapisano. | Gdy będziesz zadowolony, wyłącz debug. |
| **No products to update.** / **No categories to update.** | Nic już nie pasuje do **Selected Products** i pozostałych filtrów. | Zadanie jest ukończone albo zmień regułę. |
| **Cron Job feature is disabled. You can enable it from the module settings.** | **Enable Cron Feature** jest ustawione na **No**. | Ustaw **Yes** i naciśnij **Save**. |
| **The token does not exist or it's wrong!** | Brakuje sekretu lub jest niezgodny. | Skopiuj adres ponownie z ekranu. |
| **Invalid action!** | W adresie nie ma części `action` albo jest błędna. | Dopisz część `action` z tabeli powyżej. |
| **updatedField parameter is wrong!** | Pole nie jest dozwolone dla tego zadania. | Wybierz pole z formularza. |
| **All must include all mandatory parameters!** | Zapisana wartość (na przykład szablon) jest pusta. | Wybierz **Prompt Template** i zapisz. |
| **productTarget parameter is wrong! Allowed values: …** | Nazwa trybu w adresie jest błędna. | Użyj jednego z trzech trybów. |
| **Error!** z komunikatem | Gemini odmówiło lub zawiodło. | Przeczytaj komunikat, potem sprawdź History. |
| **Error! The model returned an empty response.** | Gemini nic nie zwróciło, na przykład limit Max Tokens był zbyt niski. | Zwiększ **Max Tokens** na ekranie **Gemini**. |
| **Monthly generation budget reached.** | Budżet Studio został wyczerpany. | Zwiększ budżet lub poczekaj do następnego miesiąca. |
| **Reply rejected by the studio quality gate.** | Odpowiedź zawierała zakazane słowo. | Zmień listę lub szablon. |
| **Error! Could not save product …** | PrestaShop odrzucił nowy tekst (na przykład za długi). | Sprawdź pole i prompt. |

Wywołanie crona zatrzymuje się na pierwszym błędzie i podaje, ile elementów zdążyło zostać zaktualizowanych przed nim.

### 3.13 History

Otwórz **History**. To dziennik tego, o co pytano i co wróciło. Otwarcie lub filtrowanie strony niczego nie usuwa i nie zmienia produktów.

![History](https://mypresta.eu/docs/images/docs/myaigemini-history.webp)

| Pole | Na start | Co robi |
|---|---|---|
| **Today**, **7 days**, **30 days**, **This month**, **All time** | **This month** | Gotowe zakresy dat. |
| **From** / **To** | Bieżący miesiąc | Własny okres. |
| **Model** | **Any** | Tylko zapytania wykonane tym modelem. |
| **Type** | **Any** | Tylko jeden rodzaj zadania, na przykład opis produktu lub meta tytuł kategorii. |
| **Status** | **Any** | **Success** lub **Error**. |
| **Language** | **Any** | Tylko zapytania dla tego języka. |
| **Employee** | **Any** | Tylko zapytania uruchomione przez tego użytkownika panelu. |
| **Product / category ID** | Empty | Jeden numer produktu lub kategorii. |
| **Prompt or reply contains** | Empty | Słowo, które musi być w prompcie, odpowiedzi lub tekście błędu. |
| **Filter** | – | Stosuje filtry. |

Karty: **Requests**, **Success**, **Errors**, **Tokens sent**, **Tokens received**, **Tokens total**, **Average time**. Kreska w kolumnie tokenów oznacza, że Gemini nie zwróciło liczby dla tego wywołania. Pod nimi pięć tabel grupuje przefiltrowane zapytania: **By day**, **By model**, **By type**, **By language**, **By employee**, z małym paskiem pokazującym udział tokenów. Mała liczba kursywą obok liczby wywołań to liczba błędów.

Lista na dole ma kolumny **ID**, **Status** (zielone **Success** lub czerwone **Error**), **Prompt** (pierwsze 180 znaków), **Reply / Error**, **Provider** (usługa, model i czas trwania), **Sent**, **Received**, **Total**, **Entity ID**, **Type**, **Timestamp** oraz przycisk **View**, który otwiera pełny prompt i odpowiedź z **Back to the list**. Lista pokazuje 50 wierszy na stronę.

Przycisk paska narzędzi **Clear list** usuwa wszystkie wiersze History naraz, bez pytania. Rób to tylko świadomie: przyciski przywracania na produktach, miesięczny licznik budżetu oraz tryby crona **pendingGemini** i **pendingField** opierają się na History, więc po wyczyszczeniu cron traktuje każdy produkt jako jeszcze nieopisany.

### 3.14 Images

Otwórz **Images**. Ten ekran tylko włącza lub wyłącza wyszukiwanie zdjęć produktów i zapisuje jego polecenie. Nie pobiera żadnych zdjęć.

![Images](https://mypresta.eu/docs/images/docs/myaigemini-images.webp)

| Pole | Na start | Co robi |
|---|---|---|
| **AI Image Finder** | Enabled | Pokazuje zakładkę **Photos** na stronie produktu. Wyłączenie ją ukrywa. |
| **AI Image Search Prompt** | Wbudowane polecenie angielskie | Polecenie, które prosi Gemini o adresy stron, na których prawdopodobnie są zdjęcia tego produktu. {product_name} i {product_description} są zastępowane dla bieżącego produktu. Zachowaj prośbę o zwykłą listę adresów. |
| **Save** | – | Zapisuje oba pola. Komunikat: **Settings saved.** |

Wyszukiwanie znajduje strony internetowe, które już pokazują Twój produkt; nie tworzy obrazów. Upewnij się, że masz prawo korzystać z każdego importowanego zdjęcia.

### 3.15 Updates

Otwórz **Updates** (skrajnie po prawej na pasku modułu). Strona sprawdza w MyPresta.eu, czy jest nowszy plik modułu. Nie zmienia katalogu i niczego nie instaluje.

![Updates](https://mypresta.eu/docs/images/docs/myaigemini-updates.webp)

| Pole | Na start | Co robi |
|---|---|---|
| **Manual Check** (**Check Now**) | – | Pyta jednorazowo, natychmiast. Zobaczysz **Module is up to date!** lub **New version available!**. |
| **Automatic Notifications** | Przełącznik Enabled lub Disabled | Enabled: mniej więcej co trzy dni panel administracyjny sprawdza i pokazuje baner ostrzegawczy z linkiem, gdy istnieje nowsza wersja. To ustawienie jest wspólne z innymi modułami MyPresta w tym samym sklepie. |
| **Product Page** | – | Link do strony modułu w MyPresta.eu, gdzie możesz przeczytać, co się zmieniło, i pobrać plik. |
| **Save** | – | Zapisuje ustawienie powiadomień. Komunikat: **Update settings saved.** |

### 3.16 Praca na stronie edycji produktu

Otwórz **Catalog**, **Products**, edytuj produkt i otwórz **Modules**, potem **My AI Gemini**. Produkt musi być już raz zapisany. Panel pojawia się, gdy włączone jest **Product edit page Form** lub **Product Edit History** (3.4).

![Strona edycji produktu – panel My AI Gemini](https://mypresta.eu/docs/images/docs/myaigemini-product-edit.webp)

Panel ma do czterech zakładek: **Generate**, **Simulate**, **Photos** i **History**.

**Zakładka Generate**

| Pole | Na start | Co robi |
|---|---|---|
| Przyciski **Language** | Pierwszy język | Wybierz, która wersja językowa jest zapisywana. **Every language** zapisuje wszystkie aktywne języki, jeden po drugim. |
| **If the field already has text** | **Replace** | **Replace**, **Add above**, **Add below** lub **Skip if filled**. Skip nie wysyła nic do Gemini dla wypełnionego pola. |
| Karty pól | – | **Description**, **Short description**, **Name**, **Meta title**, **Meta description**, **Tags**. Naciśnij **Fill** na karcie, aby zapisać to jedno pole i od razu zapisać je w produkcie. |
| **SEO pack** – **Fill all** | – | Zapisuje nazwę, oba opisy i oba pola meta w jednym zapytaniu i je zapisuje. |
| **Use your own instruction or a saved prompt** | Zwinięte | Rozwiń, aby filtrować zapisane szablony po tytule lub tekście, wybrać kafelek (**Standard brief** lub włączony szablon) i edytować pole **Instruction**. Jeśli pole jest puste, **Fill** używa standardowego polecenia dla pola. |

Odpowiedź jest wypisywana pod panelem. Tekst jest od razu zapisywany w produkcie, ale pola otwartego formularza produktu nie odświeżają się same: przeładuj stronę produktu, zanim zaczniesz edytować i naciśniesz zapis w formularzu, inaczej stare wartości w formularzu mogą nadpisać nowy tekst.

**Zakładka Simulate.** Ten sam wybór języka i te same karty pól, ale przyciski nazywają się **Try**. Odpowiedź zostaje na tej stronie, a produkt nie jest zmieniany. Użyj jej, aby najpierw sprawdzić brzmienie.

![Strona edycji produktu – zakładka Photos](https://mypresta.eu/docs/images/docs/myaigemini-product-photos.webp)

**Zakładka Photos.** Naciśnij **Find pages**. Moduł prosi Gemini o maksymalnie 5 stron, które prawdopodobnie pokazują ten produkt, odczytuje z nich do 24 zdjęć i pokazuje je jako małe miniatury. Zaznacz te, które chcesz, i naciśnij **Add selected to this product**. Jeśli dodajesz kilka, pierwsze zaznaczone zdjęcie staje się okładką. Nic nie jest zapisywane przed naciśnięciem przycisku. Linia pod przyciskami informuje o postępie: "Looking for photos…", "Reading photos…", "Tick the photos you want, then add them to this product." Po dodaniu przeładuj stronę produktu, aby je zobaczyć. Jeśli przełącznik jest wyłączony, zobaczysz notatkę z poleceniem włączenia **AI Image Finder** w **Settings**, **General**.

**Zakładka History.** Tabela z kolumnami **When**, **Type**, **Status** i przyciskiem **Restore** przy każdym udanym zapisie, który zachował poprzednią wartość. Naciśnij **Restore**, potwierdź "Restore the previous value?", a poprzedni tekst wróci. Wiersze z błędem nie mają przycisku. Przywrócony SEO pack zwraca nazwę, oba opisy i oba pola meta. Bez żadnych wierszy zobaczysz "No generations for this product yet."

**Przyciski Generate with AI obok pól.** Na stronie produktu moduł dodaje też przycisk **Generate with AI** obok pól opisu, krótkiego opisu, meta tytułu i meta opisu. Jeśli sklep ma więcej niż jeden język, pyta "Generate this field for the current language, or for every active language?" z opcjami **Current language**, **All languages** i **Cancel**. Tekst trafia tylko do otwartego formularza: "Text is in the field. Save the product to keep it." Inne pola nie są zmieniane. Dla produktu, który nigdy nie został zapisany, zobaczysz "Save the product once before generating."

### 3.17 Praca na stronie edycji kategorii

Edytuj kategorię w **Catalog**, **Categories**. Obok pól opisu, dodatkowego opisu, meta tytułu i meta opisu moduł dodaje przycisk **Generate with AI**. Działa dokładnie tak jak przy produktach: wybierasz bieżący język lub wszystkie języki, tekst jest umieszczany w formularzu, a kategorię zapisujesz, aby go zachować ("Text is in the field. Save the category to keep it."). Kategoria, która nigdy nie została zapisana, pokazuje "Save the category once before generating." To samo okno promptu na górnym pasku (3.18) działa także na stronach kategorii, stron CMS i marek i zapisuje je w History.

### 3.18 Skróty: górny pasek, lista produktów i Help

- **Przycisk na górnym pasku.** Gdy **Admin Top Bar CTA** jest włączone, na górnym pasku znajduje się ikona magicznej różdżki. Otwiera okno **My AI Gemini** z listą **Template**, polem tekstowym i przyciskiem **Generate**. Odpowiedź jest pokazywana pod przyciskiem, z liczbą tokenów. Nie zmienia żadnego pola. Użyj **×**, aby zamknąć.
- **Lista produktów.** Na liście produktów w **Catalog**, **Products** moduł dodaje link **My AI Gemini** obok akcji zbiorczych lub na pasku narzędzi. Otwiera **Generate**, **Products**.
- **Help.** Przycisk **Help** na każdej stronie modułu otwiera objaśnienie strony.

### 3.19 Placeholdery, których możesz używać w promptach

W szablonach, polu **Instruction**, dużych polach promptów masowych i w Playground możesz pisać placeholdery w nawiasach klamrowych. Moduł zastępuje je prawdziwymi danymi dla każdego elementu przed wysłaniem polecenia.

| Placeholder | Działa dla | Czym się staje |
|---|---|---|
| {product_name}, {product_description}, {product_description_short}, {product_tags}, {product_reference}, {product_ean13}, {product_weight} | Produkty | Własne dane produktu w wybranym języku. |
| {product_default_category}, {product_category_description}, {product_categories}, {product_brand} | Produkty | Nazwa i opis kategorii głównej, nazwy wszystkich kategorii (oddzielone przecinkami), nazwa marki. |
| {product_attributes}, {product_features}, {product_feature_values} | Produkty | Atrybuty kombinacji, nazwy cech oraz pary nazwa cechy:wartość. |
| {product_images} | Produkty | Linki do zdjęć produktu, oddzielone przecinkami. |
| {category_name}, {category_description}, {category_parent_name} | Kategorie | Własne dane kategorii i nazwa rodzica. |
| {cms_title}, {brand_name}, {brand_description}, {brand_short_description} | Strony CMS, marki (okno na górnym pasku) | Tytuł strony lub dane marki. |
| {shop_name}, {shop_url}, {shop_language}, {shop_country}, {shop_currency} | Wszystko | Nazwa sklepu, domena, nazwa języka, kraj domyślny i kod waluty domyślnej. |

Placeholder, który nie ma danych, zamienia się w pusty tekst. Placeholdery kategorii nie są zastępowane w promptach produktów i odwrotnie.

## 4. Witryna sklepu

My AI Gemini nie ma interfejsu dla klientów. Niczego nie dodaje do stron produktów, stron kategorii, koszyka, stopki ani konta klienta, a w motywie nie ma niczego do włączania ani wyłączania. Witryna sklepu nie otrzymuje żadnego szablonu modułu, dlatego nie pokazano zrzutu ekranu.

Moduł jest właścicielem dwóch adresów internetowych, które nie są stronami dla klientów:

| Adres | Kto używa | Co warto wiedzieć |
|---|---|---|
| Adres crona (`…/module/myaigemini/cron?secret=…&action=…`) | Harmonogram Twojego serwera | Opisany w 3.12. Otwarty bez właściwego sekretu odpowiada tylko "The token does not exist or it's wrong!". Trzymaj go w tajemnicy: kto go zna, może uruchomić partię. |
| Adres wewnętrzny używany przez ekrany modułu | Własne przyciski modułu w panelu administracyjnym | Nie otwieraj go ani nie udostępniaj. Odrzuca żądania bez własnego sekretu modułu ("Error! Invalid token!"). |

## 5. Problemy

**Nic się nie generuje i widzę komunikat "The Gemini API key is not set. Add it in the module settings."**
Pole klucza w **Settings**, **Gemini** jest puste. Wklej klucz ze strony https://aistudio.google.com/apikey i naciśnij **Save**.

**Błąd od Google pojawia się w wyniku, w History lub w odpowiedzi crona (na przykład komunikat zaczynający się od "Google Gemini API Error").**
Google odrzuciło wywołanie: błędny lub wyłączony klucz, model, którego Twój klucz może nie używać, wyczerpane darmowe limity lub zablokowany region. Otwórz **History**, naciśnij **View** na czerwonym wierszu, aby przeczytać pełny tekst. Popraw klucz lub wybierz inny model w **Settings**, **Gemini**, potem spróbuj ponownie.

**"Gemini request timed out after … seconds. The model may be overloaded, or the timeout is too low for this prompt."**
Model potrzebował więcej czasu niż **API timeout (seconds)**. Zwiększ limit czasu w **Settings**, **General** (do 600), skróć tekst lub wybierz szybszy model, na przykład gemini-2.0-flash.

**"The model hit the token limit before returning any text. Increase "Max Tokens" …" lub "The model returned an empty response."**
Odpowiedź została ucięta lub jest pusta. Zwiększ **Max Tokens** w **Settings**, **Gemini**. Niektóre modele Gemini 2.5 zużywają część limitu na „myślenie”.

**"The response was blocked by the provider content filter. Try rewording the prompt."**
Google odmówiło odpowiedzi na polecenie. Przepisz szablon lub tekst produktu, którego używa.

**"Monthly generation budget reached. Raise it in the studio settings or wait until next month."**
Limit w **Settings**, **Studio**, **Monthly generation budget** został wyczerpany. Zwiększ go lub ustaw 0, aby go nie było.

**"The reply was rejected because it contains a forbidden word from the studio settings."**
**Quality gate** jest włączona, a odpowiedź zawierała wiersz z **Forbidden words**. Produkt pozostał bez zmian. Zmień listę, zmień prompt lub wyłącz bramkę.

**"Error! Prompt is missing or too short!"**
Polecenie ma mniej niż 4 znaki. Wpisz pełne polecenie lub wybierz szablon.

**Wiersz uruchomienia masowego pokazuje "skipped Product skipped."**
**Existing text** to **Skip if filled**, a pole miało już tekst. Wybierz **Replace**, **Add above** lub **Add below**, aby mimo to zapisać.

**Po usunięciu dodanego modelu każde zapytanie kończy się błędem.**
Usunięcie aktywnego modelu resetuje nazwę modelu do gpt-4o, którego Gemini nie zna. Otwórz **Settings**, **Gemini**, wybierz nazwę Gemini w **Model** (na przykład gemini-2.0-flash) i naciśnij **Save**.

**Ekrany nadal mówią "OpenAi" lub "gpt".**
Ta wersja nadal ma część sformułowań ze starszego wydania: potwierdzenie **OpenAi Settings Updated**, błąd **OpenAi Model field is invalid!**, etykiety filtrów "Products that have not been updated with OpenAi content" i "Products that already have been updated with OpenAi content" w **Generate**, **Products**, przykład "gpt-4.1" w polu modelu i w komunikacie "Enter a model id such as gpt-4.1.", nazwę usługi "openai" w kolumnie **Provider** w History oraz linię panelu **Help** "Paste the secret key from your OpenAI account". Wszystko to tylko sformułowania. Moduł wywołuje Google Gemini. Używaj klucza ze strony https://aistudio.google.com/apikey i nazw modeli Gemini.

**Przycisk "Module settings" w Generate otwiera stronę innego modułu lub błąd.**
Ten przycisk wskazuje ustawienia starszego modułu siostrzanego, a nie tego. Użyj **Settings** na pasku modułu.

**Dolny formularz "Generate category content" nic nie robi.**
Tylko przeładowuje filtr kategorii. Naciśnij **Run on the categories below** w panelu nad nim.

**Cron produktów nic nie robi.**
Sprawdź w tej kolejności: **Enable Cron Feature** jest ustawione na **Yes** i zapisane; adres zawiera `&action=generateProductContent`; sekret w adresie zgadza się z ekranem; wybrano **Prompt Template**; **Enable Debug** to **No**; serwer naprawdę wywołuje adres (zajrzyj do logu jego harmonogramu). Test w przeglądarce z **Enable Debug** ustawionym na **Yes** wypisuje, co zostałoby uruchomione.

**Polecenie crona na ekranie kończy się tuż po sekrecie, a przycisk "Generate Token" nic nie robi.**
Znane ograniczenie tej wersji. Linia polecenia nie jest uzupełniana przez stronę, a przycisk tokenu nie wypełnia pola. Zbuduj adres samodzielnie według 3.12 i wpisz długi sekret, jeśli chcesz go zmienić.

**Cron wciąż przepisuje produkty w zaznaczonej kategorii.**
Gdy zaznaczone jest **Product Categories**, przy każdym wywołaniu wybierane są produkty, których kategoria główna jest zaznaczona, nawet jeśli były już zapisane. Dla uruchomień według harmonogramu zostaw drzewo kategorii puste i ogranicz przebieg przez **Product ID list** albo użyj **Enable Debug**, aby sprawdzić, które produkty są wybierane, zanim ustawisz harmonogram.

**Cron przetwarza te same produkty ponownie po wyczyszczeniu History.**
Tryby crona **pendingGemini** i **pendingField** korzystają z History, aby wiedzieć, co jest już zapisane. Po **Clear list** wszystko liczy się jako niezapisane. Użyj **emptyField**, jeśli chcesz, aby wypełnione pola zostały nietknięte.

**Top P, Frequency Penalty i Presence Penalty niczego nie zmieniają.**
W tej wersji do Gemini wysyłane są tylko **Temperature** i **Max Tokens**. Pozostałe trzy są zapisywane, ale nieużywane.

**Brakuje pozycji menu "AI Content Generator".**
Otwórz jeszcze raz dowolną stronę panelu administracyjnego; moduł przywraca pozycję. Jeśli nadal jej brak, odinstaluj i zainstaluj moduł ponownie (to czyści History i ustawienia).

**Brak panelu "Modules → My AI Gemini" na stronie produktu.**
Sprawdź, czy **Product edit page Form** (lub **Product Edit History**) jest włączone w **Settings**, **General**, czy produkt był raz zapisany i czy otwierasz zakładkę **Modules** produktu. Przyciski **Generate with AI** obok pól są dodawane przez moduł osobno i mogą pozostać widoczne nawet po wyłączeniu panelu.

**Wygenerowany tekst zniknął po zapisaniu produktu.**
Formularz produktu był otwarty ze starymi wartościami. Po użyciu **Fill** przeładuj stronę produktu i dopiero potem edytuj. Użyj **Restore** w zakładce **History**, aby przywrócić poprzedni tekst.

**Blok Dashboard na głównym dashboardzie PrestaShop jest pusty.**
Ten blok nie otrzymuje danych z History. Otwórz **AI Content Generator**, **Dashboard**.

**Wyszukiwanie zdjęć: "The search did not return photos. Reload the product page and try again." lub "No photos were found on the suggested pages."**
Gemini zasugerowało strony, których nie dało się odczytać lub które nie zawierały odpowiednich zdjęć. Naciśnij **Find pages** ponownie lub popraw **AI Image Search Prompt** w **Images**. Strony pod prywatnymi lub lokalnymi adresami są odrzucane.

**New product pokazuje "Failed to parse AI response. Please try again." lub "Failed to create product".**
Gemini nie zwróciło użytecznego szkicu albo sklep odrzucił dane (na przykład język bez nazwy w języku domyślnym). Naciśnij **Generate data** ponownie, wybierz domyślny język sklepu i sprawdź numer kategorii.

## 6. Dla programisty

### 6.1 Przegląd

| Element | Wartość | Gdzie zdefiniowano |
|---|---|---|
| Nazwa techniczna | `myaigemini` | Główny plik modułu |
| Klasa główna | `myaigemini` (extends `Module`) | Główny plik modułu |
| Wersja | **1.1.0** | Główny plik modułu |
| Nazwa wyświetlana | My AI Gemini - AI content generation | Główny plik modułu |
| Autor | MyPresta.eu | Główny plik modułu |
| Tab | `front_office_features` | Główny plik modułu |
| PrestaShop | 1.6 – 9.99.99 (`ps_versions_compliancy`) | Główny plik modułu |
| PHP | 7.0 lub nowszy (`MIN_PHP_VERSION`, sprawdzane w `install()`) | Główny plik modułu |
| API | Google Gemini pod `https://generativelanguage.googleapis.com/v1beta`, klucz jako parametr zapytania `key` | Główny plik modułu |
| Źródło klucza | https://aistudio.google.com/apikey | Główny plik modułu |
| Prefiks konfiguracji | `MYPRESTA_MYAIGEMINI_` | Główny plik modułu |
| Prefiks CSS | `.mag-` (oraz `.myaigemini-ui`, `.myaigemini-stats`) | Główny plik modułu |

Przepływ danych: ekran (panel produktu, przebieg masowy, okno na górnym pasku, Playground) wysyła żądanie POST do kontrolera front modułu `ajax` z tajnym tokenem; kontroler buduje prompt (szablon, placeholdery, `Studio::decorate`), wywołuje `OpenAIService` (klient Gemini zachowany pod starą nazwą klasy), zapisuje wynik w produkcie lub kategorii i wstawia wiersz do `myaigemini_log`. Cron działa tak samo przez kontroler front `cron`. Wygenerowany tekst jest zapisywany przez `Product::save()` lub `Category::save()`.

Parametry URL na stronie konfiguracji: `mag_tab` (`dashboard`, `settings`, `updates`), `mag_sub` (`general`, `openai`, `studio`, `templates`, `playground`; `openai` to zakładka **Gemini**; w **Generate** `products` i `categories`), zakres dashboardu `mcg_preset` (`today`, `7`, `30`, `90`, `month`, `all`), `mag_from`, `mag_to`. W History: `stats_preset`, `stats_from`, `stats_to`, `stats_model`, `stats_type`, `stats_status`, `stats_lang`, `stats_employee`, `stats_entity`, `stats_q`.

### 6.2 Pliki

| Plik | Przeznaczenie | Obszar |
|---|---|---|
| `myaigemini.php` | Klasa główna: instalacja i deinstalacja, formularze konfiguracji (General, Gemini, Studio, szablony), Dashboard, hooki, umieszczanie menu, katalog modeli. | Kod modułu |
| `autoload.php` | Ładuje klasy modułu bez Composera. | Kod modułu |
| `src/OpenAIService.php` | Klient Gemini (`generateContent`, `models`); limity czasu; zapamiętuje parametry, które model odrzuca. | Kod modułu |
| `src/Studio.php` | Dekorowanie promptów, miesięczny budżet, sprawdzanie zakazanych słów, SEO pack i prompty tekstów alt. | Kod modułu |
| `controllers/admin/AdminMyAIGeminiMain.php` | Pozycja menu; przekierowuje do Dashboard. | Kod modułu |
| `controllers/admin/AdminMyAIGeminiSettings.php` | Ukryty; przekierowuje do Settings. | Kod modułu |
| `controllers/admin/AdminMyAIGemini.php` | **Generate** (filtry i panele masowe). | Kod modułu |
| `controllers/admin/AdminMyAIGeminiProductCreator.php` | **New product**. | Kod modułu |
| `controllers/admin/AdminMyAIGeminiCron.php` | Formularze **Cron**. | Kod modułu |
| `controllers/admin/AdminMyAIGeminiUsage.php` | **History**. | Kod modułu |
| `controllers/admin/AdminMyAIGeminiImageFinder.php` | Formularz **Images** i akcje wyszukiwania zdjęć. | Kod modułu |
| `controllers/front/ajax.php` | Akcje JSON używane przez ekrany. | Kod modułu |
| `controllers/front/cron.php` | Punkt końcowy crona. | Kod modułu |
| `lib/sectionHelp.php` | Tekst panelu Help. | Kod modułu |
| `lib/updateChecker.php` | Sprawdzanie aktualizacji (`myaigeminiUpdate`). | Kod modułu |
| `lib/prestashop9compatibility.php`, `lib/searchTool/` | Pomocnik zgodności i wyszukiwarka modułu. | Kod modułu |
| `views/templates/hook/*.tpl`, `views/templates/admin/product_creator.tpl` | Ekrany. | Kod modułu |
| `views/js/back.js`, `product-fields.js`, `image-finder.js`, `admin-products-bulk.js`, `dashboard.js`, `admin-help.js`, `chart.min.js` | Zachowanie ekranów. | Kod modułu |
| `views/css/admin-nav.css`, `back.css`, `stats.css` | Style. | Kod modułu |
| `translations/*.php` | Pliki językowe (wiele języków). | Kod modułu |

Zasoby, do których są odwołania, ale nie są dostarczane: `views/js/admin.js`, `views/css/admin.css` (kontrolery Main i Settings), `views/js/product_creator.js` oraz `views/css/product_creator.css` (kontroler New product). Są po cichu pomijane; przyciski New product obsługuje `back.js`.

### 6.3 Kontrolery

| Kontroler | Klasa i rodzic menu | Uwagi |
|---|---|---|
| `AdminMyAIGeminiMain` | `AdminMyAIGeminiMainController` (rodzic: sekcja Modules) | Widoczna pozycja **AI Content Generator**. `initContent()` przekierowuje na stronę konfiguracji z `mag_tab=dashboard`. |
| `AdminMyAIGemini` | `AdminMyAIGeminiController` (rodzic: AdminMyAIGeminiMain) | Ukryta zakładka (`active = 0`). **Generate**. `mag_sub` `products` / `categories`; nazwy submit `filterProducts`, `filterCategories`. |
| `AdminMyAIGeminiProductCreator` | `AdminMyAIGeminiProductCreatorController` (rodzic: AdminMyAIGeminiMain) | Ukryty. AJAX `generateProductData`, `extractImages`, `createProduct`, `generateImages` (odpowiedź zastępcza "coming soon"). |
| `AdminMyAIGeminiSettings` | `AdminMyAIGeminiSettingsController` (rodzic: AdminMyAIGeminiMain) | Ukryty. Tylko przekierowanie. |
| `AdminMyAIGeminiCron` | `AdminMyAIGeminiCronController` (rodzic: AdminMyAIGeminiMain) | Ukryty. Submit `submitCronUpdate`, `submitCatCronUpdate`. |
| `AdminMyAIGeminiUsage` | `AdminMyAIGeminiUsageController` (rodzic: AdminMyAIGeminiMain) | Ukryty. `clear_log` opróżnia tabelę logu. |
| `AdminMyAIGeminiImageFinder` | `AdminMyAIGeminiImageFinderController` (rodzic: AdminMyAIGeminiMain) | Ukryty. Akcje `searchImages`, `extractImages` (hosty prywatne odrzucane), `saveImages`. Submit formularza `submitImageFinder`. |
| `ajax` (front) | `myaigeminiajaxModuleFrontController` (rodzic: –) | Wymaga `secret_token` równego `MYPRESTA_MYAIGEMINI_TOKEN`, w przeciwnym razie "Error! Invalid token!". Akcje: `initiatePrompt`, `updateSettings`, `updateProduct`, `initiateProductRestore`, `updateCategory`, `generateSeoPack`, `generateAltTexts` (żaden przycisk jej nie wywołuje). |
| `cron` (front) | `MyAIGeminiCronModuleFrontController` (rodzic: –) | Wymaga `MYPRESTA_MYAIGEMINI_ENABLE_CRON` i `secret` równego `_SECRET` lub `_CAT_SECRET` (każdy z sekretów otwiera obie akcje). `action` = `generateProductContent` lub `generateCategoryContent`. |

Formularze filtrów Generate linkują "Module settings" do `configure=mychatgpt`. Wyjście hooka panelu edycji produktów jest budowane w `renderProductModulesContent()`.

SQL wyboru dla crona: filtr kategorii i lista identyfikatorów produktów są dołączane do klauzuli WHERE; warunek kategorii (`id_product IN (…) OR id_category_default IN (…)`) nie jest ujęty w nawiasy, więc OR poszerza cały warunek. `pendingGemini` i `pendingField` używają `NOT EXISTS` na wierszach `myaigemini_log`, których status jest pusty lub inny niż `error`; `pendingField` dopasowuje też `type = product_<field>` / `category_<field>`. `emptyField` łączy `product_lang` / `category_lang` dla wybranego języka. Długości tekstów produktu przy zapisie: nazwa 128, krótki opis 799 (cron) lub 800 (ajax), meta tytuł 69, meta opis 159.

### 6.4 Hooki

Rejestrowane w `install()`: `displayAdminProductsMainStepLeftColumnMiddle` (zwraca pusty ciąg), `displayAdminProductsMainStepLeftColumnBottom` (pusty), `actionProductFormBuilderModifier` (bez działania), `displayAdminProductsExtra` (renderuje panel w zakładce **Modules** produktu), `displayBackOfficeHeader` (ładuje zasoby, uruchamia `ensureLongSecrets()` i `placeModuleMenu()`, jednorazowo rejestruje zakładkę wyszukiwarki zdjęć, dodaje zmienne JS), `displayBackOfficeTop` (okno na górnym pasku, gdy `TOPCTA` jest włączone, oraz zmienne JS dla identyfikatorów kategorii, CMS i marek), `displayFooter` (pusty), `displayHeader` (pusty), `dashboardZoneTwo` (renderuje `dashboard.tpl` bez jego danych). `actionProductGridDataModifier` istnieje jako metoda, ale nie jest rejestrowany. Moduł nie ma metod `enable()` ani `disable()`. Moduł nie udostępnia własnych hooków.

`hookDisplayBackOfficeHeader` ładuje `product-fields.js` na stronach edycji produktu i kategorii niezależnie od przełącznika `MYPRESTA_MYAIGEMINI_PRODUCT` (przełącznik steruje tylko panelem w zakładce Modules).

### 6.5 Nadpisania (overrides)

Moduł nie ma żadnych overrides. Nie zastępuje żadnego pliku rdzenia.

### 6.6 Baza danych

| Tabela | Zawartość | Uwagi |
|---|---|---|
| `myaigemini_prompt` | `id_prompt` (PK), `status`, `title` (128), `prompt` (text), `date_generated`. 16 wierszy wstawianych przy instalacji. | Tworzona przy instalacji, usuwana przy deinstalacji |
| `myaigemini_log` | `id_log` (PK), `id_product`, `id_category`, `id_cms`, `id_manufacturer`, `id_lang`, `id_employee`, `type`, `method`, `status`, `ai_service`, `model`, `http_code`, `duration_ms`, `prompt_tokens`, `completion_tokens`, `total_tokens`, `error_message`, `prompt`, `reply`, pary `old_` / `new_` dla `name`, `description`, `description_short`, `meta_title`, `meta_description`, `tags`, `date_updated`. Indeksy na `id_product` i `status`. | Tworzona przy instalacji, usuwana przy deinstalacji |

Obie tabele używają silnika bazy danych sklepu i są usuwane przy deinstalacji. Trzy kolumny tokenów są też dodawane w czasie działania przez `ensureUsageColumns()`, gdy Dashboard, History lub zapis logu crona/ajax ich potrzebuje, a ich brakuje. `ai_service` zawsze przechowuje wartość `openai` (pozostałość). `postProcess()` generatora masowego zapisuje przesłane wartości filtrów w kluczach konfiguracji takich jak `MYPRESTA_MYAIGEMINI_FIELD`, `_LANGUAGE`, `_CONTENT`, `_DELAY`, `_EXISTING`, `_HISTORY`, `_STATUS`, `_STOCK`, `_PROD_*`, `_CATEGORIES`, `_BRANDS` przy każdym załadowaniu **Generate**. Deinstalacja tych kluczy nie usuwa.

### 6.7 Klucze konfiguracji i tłumaczenia

Prefiks `MYPRESTA_MYAIGEMINI_`. Wartości zapisywane przez `install()`:

| Klucz | Domyślnie | Znaczenie |
|---|---|---|
| `LIVE_MODE`, `DEBUG_MODE` | `0`, `0` | Przełączniki live i debug (`PrestaShopLogger` z typem obiektu `MyAIGemini`). |
| `TIMEOUT` | `120` | Sekundy; ograniczane do 10–600; limit czasu przeglądarki to ta wartość plus 15. |
| `PRODUCT_LOG`, `TOPCTA`, `PRODUCT` | `1`, `1`, `1` | Lista przywracania, okno na górnym pasku, panel produktu. |
| `IMAGEFINDER_ENABLE`, `IMAGEFINDER_PROMPT` | `1`, tekst wbudowany | Przełącznik wyszukiwania zdjęć i polecenie. `IMAGEFINDER_TAB_OK` oznacza jednorazową naprawę zakładki. |
| `TOKEN`, `SECRET`, `CAT_SECRET` | losowe 32 znaki | Token ajax, sekret crona produktów, sekret crona kategorii. Wartości krótsze niż 24 znaki są generowane na nowo na następnej stronie panelu. |
| `API_KEY` | pojedyncza spacja | Zapisywany po przycięciu; formularz zachowuje zapisany klucz, jeśli pole jest puste. |
| `MODEL`, `EXTRA_MODELS` | `gemini-2.0-flash`, puste | Aktywny model i dodane nazwy (po jednej w wierszu). Usunięcie aktywnego dodanego modelu ustawia `gpt-4o`. |
| `TEMPERATURE`, `MAX_TOKENS` | `0.7`, `3200` | Wysyłane do Gemini jako `temperature` i `maxOutputTokens`. |
| `TOP_P`, `FREQ_PEN`, `PRES_PEN` | `1`, `0`, `0` | Zapisywane; niewłączane do żądania Gemini. |
| `MODEL_CAPS` | puste | Wyuczone parametry poszczególnych modeli. |
| `VOICE`, `AUDIENCE`, `TONE`, `GLOSSARY`, `FORBIDDEN` | puste | Teksty Studio. |
| `BUDGET`, `QUALITY` | `0`, `1` | Miesięczny limit; bramka jakości. |
| `ENABLE_CRON` | `0` | Globalny przełącznik crona. |
| `CRON_INTERVAL`, `CAT_CRON_INTERVAL` | `6`, `6` | Wybór interwału (6 = Every Hour). Tylko zapisywany; używany do wyświetlania. |
| `updatedField`, `catupdatedField` | `description`, `description` | Pole crona (nazwy kluczy zapisywane są jako `MYPRESTA_MYAIGEMINI_updatedField` itd.). |
| `productTarget`, `categoryTarget` | `pendingGemini` | Tryb wyboru crona. |
| `productsToUpdate`, `categoriesToUpdate` | `5`, `5` | Wielkość partii. |
| `promptTemplateId`, `catpromptTemplateId` | puste | Szablon crona. |
| `languageId`, `catlanguageId` | `PS_LANG_DEFAULT` | Język crona. |
| `debug`, `catdebug`, `interval_select` | `0`, `0`, puste | Debug crona i dawny selektor. |
| `productIdsList`, `categories` | puste | Filtry crona. |

Deinstalacja usuwa powyższe klucze oraz `ACTIVE_SERVICE`, `GEMINI_API_KEY` i `GEMINI_MODEL` (stare nazwy), zakładki i obie tabele. Panel administracyjny usuwa też `GEMINI_API_KEY`, `GEMINI_MODEL` i `ACTIVE_SERVICE` przy każdym załadowaniu strony konfiguracji. Wspólne klucze `mypresta_updates`, `update_myaigemini` i `updatev_myaigemini` należą do mechanizmu sprawdzania aktualizacji i nie są usuwane.

Tłumaczenia: aby dodać język, utwórz `translations/{iso}.php` (moduł dostarcza wiele języków). Teksty przechodzą przez `$this->l()` w klasie głównej i `l s='…' mod='myaigemini'` w szablonach. Kontrolery administracyjne tłumaczą przez `trans()` w PrestaShop 8 i 9 oraz przez `l()` modułu w 1.6 i 1.7. Teksty nieprzetłumaczone: tytuł kolumny **ID**, etykieta **Cron Job Secret Token** i **Generate Token**, komunikaty JavaScript w `back.js`, `image-finder.js` i na stronie wyboru zdjęć ("Write a prompt first.", "Looking for photos…" i podobne) oraz szkic zwracany przez New product. Opisy pól to wpisy `desc` budowane przez `fieldHelp()` w definicjach formularzy, w formie "What it does / How to configure / Effect"; tekst panelu Help znajduje się w `lib/sectionHelp.php`.

Placeholdery są zastępowane w `controllers/front/ajax.php` (przebiegi interaktywne) i `controllers/front/cron.php` (cron); listy są takie same, z tą różnicą, że cron nie ma placeholderów CMS ani marek.

### 6.8 Rozszerzanie

W motywie nie ma szablonu front do nadpisania. Aby dodać placeholdery promptów, rozbuduj bloki zastępowania w `ajax.php` i `cron.php`. Aby zmienić zachowanie usługi AI, edytuj `src/OpenAIService.php` (`createChatCompletion()` buduje ładunek Gemini). Aby dodać model, użyj **Add a Gemini model** lub rozszerz `getPopularGeminiModels()`. Własny CSS może celować w klasy `.mag-` na ekranach modułu. Zmiana formatu adresu crona wymaga edycji `AdminMyAIGeminiCron.php` oraz szablonów `cron.tpl` i `cron-info.tpl`.

## 7. Pomoc

Strona modułu: https://mypresta.eu/ai-artificial-intelligence/product-and-category-descriptions-with-gemini.html

Aby poprosić o pomoc:

1. Zaloguj się na swoje konto klienta na mypresta.eu.
2. Przejdź na stronę kontaktową.
3. Wybierz temat **Support for paid modules**. Dla modułów płatnych formularz informuje, że musisz być zalogowany; po zalogowaniu wybierz ten moduł z historii zakupów.
4. Opisz, co zrobiłeś, czego oczekiwałeś i co zobaczyłeś. Dołącz czerwony wiersz **History** (otwórz go przez **View**) lub tekst komunikatu z ekranu oraz nazwę używanego modelu.
