---
title: "AI Translations with Grok - dokumentacja i instrukcja użytkownika"
description: "Instrukcja konfiguracji i rozwiązywania problemów dla sklepów, które już mają AI Translations with Grok."
sidebar:
  label: "AI Translations with Grok - dokumentacja i instrukcja użytkownika"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł AI Translations with Grok na MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-grok.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ai-artificial-intelligence/ai-translations-with-grok/)
>
> ---


## 1. Wymagania

Moduł działa na PrestaShop 1.7.0.0 i nowszych, w tym na PrestaShop 8 i 9.

- **PrestaShop:** 1.7.0.0 lub nowszy.
- **PHP:** 5.6 lub nowszy.
- **Rozszerzenia PHP:** cURL, OpenSSL, SimpleXML i mbstring.
- **Inne moduły:** moduł nie wymaga żadnych innych modułów.
- **Poza sklepem:** konto xAI i klucz API Grok z konsoli xAI. Serwer sklepu musi mieć dostęp do adresu `https://api.x.ai/v1/chat/completions`.
- **Opcjonalnie:** zadanie w harmonogramie serwera (cron), które otwiera adres z **Ustawienia**. Bez niego partie trzeba uruchamiać ręcznie na **Zadania**.
- **Duże katalogi:** domena z tysiącami ciągów to tysiące wywołań API. Zadanie dzieli się na partie o rozmiarze **Rozmiar partii (Batch size)**. Przed startem warto nacisnąć **Szacuj** na **Masowe (Bulk)**, żeby zobaczyć liczbę ciągów i szacowany koszt.
- Sklep musi mieć co najmniej dwa języki. Przy jednym języku zaplecze pokaże **Sklep musi posiadać co najmniej dwa języki.** i nie będzie czego tłumaczyć.

## 2. Instalacja

1. Otwórz **Moduły**, a potem **Module Manager**. Wybierz wgranie modułu, wgraj plik ZIP i naciśnij **Instaluj** przy **AI Translations with Grok**.
2. Po instalacji **AI Translations with Grok** pojawi się w menu **Międzynarodowe**.
3. Instalacja nie czyści pamięci podręcznej sklepu. Moduł robi to dopiero wtedy, gdy zapisuje tłumaczenie.

Następnie otwórz **AI Translations with Grok**, przejdź do **Ustawienia** i wklej klucz Grok. Dopóki klucza nie ma, każda strona modułu pokazuje komunikat **Brak klucza API Grok.** z odnośnikiem **Otwórz ustawienia**.

**Odinstalowanie.** W **Module Manager** naciśnij **Odinstaluj** i potwierdź pytanie **Usunąć ten moduł i jego dane (zadania, słownik, pamięć podręczna)?**

- Pozycja w menu znika. Usuwane są zadania, słownik, wzorce wykluczeń, historia wywołań, kolejka **Przegląd**, kopie do wycofania, rejestr kosztów oraz ustawienia modułu, w tym klucz API.
- Tekst, który moduł już zapisał w sklepie, zostaje. Dotyczy to tłumaczeń katalogu i plików tłumaczeń klasycznych modułów. Zostaje też wybór sprawdzania aktualizacji.
- Ponowna instalacja nie przywraca usuniętych zadań, słownika ani historii. Ustawia wartości początkowe i tworzy nowy adres crona.

## 3. Konfiguracja i praca w zapleczu

Cały moduł to jedna strona: **Międzynarodowe**, a potem **AI Translations with Grok**. Zakładki to **Pulpit**, **Ręczny**, **Masowe (Bulk)**, **Zadania**, **Przegląd**, **Katalog**, **Słownik**, **Wykluczenia**, **Historia** i **Ustawienia**. **Aktualizacje** są na końcu paska. Przycisk **Pomoc** otwiera panel bieżącej zakładki. Na **Aktualizacje** przycisku **Pomoc** nie ma.

Zrzuty ekranu w tej instrukcji pochodzą z angielskiego zaplecza. Nazwy przycisków i pól są podane tak, jak wyglądają w polskim zapleczu.

Zwykła praca składa się z czterech kroków.

1. **Połączenie.** Na **Ustawienia** wklej klucz, wybierz model i naciśnij **Test połączenia**, a potem **Zapisz**.
2. **Mała próba.** Na **Ręczny** przefiltruj jedną domenę, zaznacz kilka pustych ciągów i przetłumacz je. Sprawdź wynik, zanim puścisz cały katalog.
3. **Zadanie.** Na **Masowe (Bulk)** wybierz sekcję, języki i domeny, naciśnij **Szacuj**, a potem **Uruchom zadanie**. Otwórz zadanie i naciśnij **Przetwórz partię** albo **Przetwarzaj automatycznie**. Możesz też zostawić przetwarzanie cronowi.
4. **Kontrola.** Otwórz **Przegląd**, żeby zobaczyć wiersze zatrzymane przez kontrolę jakości, oraz **Historia**, jeśli jakieś wywołanie się nie udało. Przycisk **Wycofaj** na zadaniu przywraca poprzedni tekst, o ile moduł trzymał jego kopię.

Moduł sam z siebie nie zaczyna tłumaczenia. Przyciski **Szacuj**, **Filtruj** i **Zapisz** na **Ustawienia** nie zapisują tekstu katalogu. Zadanie czeka na **Zadania**, aż je przetworzysz albo wywoła je adres crona.

### 3.1. Konfiguracja modułu

Otwórz **Moduły**, **Module Manager**, znajdź **AI Translations with Grok** i naciśnij **Konfiguruj**. Otworzy się **Pulpit**. Przejdź do **Ustawienia**.

Przyciski **Zapisz** i **Test połączenia** są na dole formularza. Zapisanie formularza nie uruchamia tłumaczenia i nie nadpisuje tłumaczeń, które już istnieją.

![Ustawienia, angielskie zaplecze. Góra formularza: klucz API, model, dodanie modelu, ton i lokalizacja źródłowa.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-settings.webp)

**Połączenie**

| Pole | Domyślnie | Co robi |
|---|---|---|
| **Klucz API Grok** | puste | Tajny klucz, który sklep wysyła do Grok. Wklej klucz z konsoli xAI. Puste pole zostawia klucz, który jest już zapisany. Wpisanie nowej wartości zastępuje stary klucz. Puste pole go nie kasuje. Gdy klucz jest zapisany, pomoc pokazuje **Zapisano klucz:** i zamaskowaną wersję klucza. |
| **Model** | grok-4.7 | Model Grok, który pisze tłumaczenie. Lista zawiera wbudowane modele: grok-4.7, grok-4.6, grok-4.5, grok-4.3, grok-4.20-0309-non-reasoning i grok-4.20-0309-reasoning. Modele dodane przez siebie można usunąć. Następne tłumaczenie użyje wybranego modelu. Jeśli Twoje konto nie ma dostępu do modelu, wywołanie zakończy się błędem, który zobaczysz na **Historia**. |
| **Dodaj model Grok** | puste | Wpisz dokładny identyfikator modelu z konta xAI i naciśnij **Dodaj model**. Podpowiedź w polu to grok-4.7. Nowy identyfikator pojawia się w **Model** i od razu staje się aktywny. **Usuń** kasuje tylko modele dodane tutaj. Wbudowanych nie da się usunąć. |

Komunikaty: **Dodano model.**, **Usunięto model.**, **Ten model znajduje się już na liście. Jest on teraz modelem aktywnym.**, **Wpisz identyfikator modelu, na przykład grok-4.7.**, **Nie można usuwać modeli wbudowanych.**

**Głos i źródło**

| Pole | Domyślnie | Co robi |
|---|---|---|
| **Ton wypowiedzi** | Oficjalny | Dopisuje do każdego promptu instrukcję stylu. **Oficjalny** nadaje się do tekstów sklepu i zaplecza, **Swobodny** brzmi lżej, a **Marka** działa razem z polem **Głos marki**. Nowe tłumaczenia powstają w wybranym stylu. Tłumaczenia, które już są zapisane, zostają bez zmian, dopóki nie uruchomisz ich ponownie. |
| **Głos marki** | puste | Pole widać tylko wtedy, gdy **Ton wypowiedzi** ma wartość **Marka**. Wpisz kilka zdań o tym, jak sklep ma brzmieć, albo zostaw pole puste. Tekst trafia do promptu. Puste pole oznacza brak dodatkowego opisu głosu. Zmiana nie przepisuje istniejących tłumaczeń. |
| **Lokalizacja źródłowa** | puste | Język, który model traktuje jako oryginał. Puste pole to kreska na liście i wtedy źródłem jest ekran, który tłumaczysz. Najczęściej wybiera się lokalizację, w której pisane są katalogi, zwykle en-US. **Ręczny**, **Masowe (Bulk)** i ikony na **Międzynarodowe → Tłumaczenia** wysyłają tę lokalizację jako źródło. Domyślny język sklepu się nie zmienia. |
| **Przyciski pojedynczych pól — formularze sklepu** | Tak | Przycisk przy każdym polu wielojęzycznym w formularzach sklepu: produkt, kategoria, CMS i inne. Przycisk tłumaczy tylko to jedno pole. Nie chowa przycisków w całym sklepie. Zapisane tłumaczenia się nie zmieniają. |
| **Pola wyboru dla poszczególnych pól — formularze sklepu** | Tak | Każde takie pole dostaje pole wyboru, a pasek tłumaczy tylko zaznaczone pola. Nie chowa pól wyboru ani paska. Przyciski z góry mają własny przełącznik. |
| **Przyciski pojedynczych pól — Międzynarodowe → Tłumaczenia** | Tak | Przycisk przy każdym polu na **Międzynarodowe → Tłumaczenia**. Nie chowa tych przycisków. Formularze sklepu pozostają bez zmian. Jedno kliknięcie wypełnia jedno pole. Tekst trzeba jeszcze zapisać przyciskiem **Zapisz** PrestaShop. |
| **Pola wyboru dla poszczególnych pól — Międzynarodowe → Tłumaczenia** | Tak | Pola wyboru i pasek na **Międzynarodowe → Tłumaczenia**. Nie chowa ich. Formularze sklepu nie są ruszane. |

**Limity**

![Ustawienia, angielskie zaplecze. Rozmiar partii i pola limitów pod nim.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-settings-limits.webp)

| Pole | Domyślnie | Co robi |
|---|---|---|
| **Rozmiar partii (Batch size)** | 25 | Ile ciągów trafia do jednego wywołania API. Na początek warto ustawić 10–25. Wartość musi mieścić się w przedziale 1–100. Większa partia oznacza mniej wywołań, ale gdy taka partia się nie uda, powtarzany jest większy fragment. |
| **Próbka testowa (Dry-run)** | 10 | Ile przykładowych ciągów pokaże **Szacuj** przed zadaniem masowym. Wartość musi mieścić się w przedziale 1–50. **Szacuj** pokazuje wtedy te źródła i szacunek kosztu. Nic nie zapisuje. |
| **Maks. tokenów (0 = domyślnie)** | 0 | Limit długości jednej odpowiedzi. Zostaw 0, aby użyć domyślnej długości Grok. Wpisz liczbę, jeśli odpowiedzi są ucinane albo mają być krótsze. Limit działa tylko dla następnego wywołania i nie skraca zapisanych tłumaczeń. |
| **Budżet USD / miesiąc** | 0 | Miesięczny limit w dolarach, liczony z rejestru użycia. Wartość 0 oznacza brak limitu. Ustaw kwotę od pierwszego dnia miesiąca. Gdy rejestr dojdzie do tej kwoty, nowe tłumaczenia się zatrzymują, a ekran pokazuje komunikat **Monthly API budget has been exhausted.** Zapisana już praca zostaje. |
| **Limit częstotliwości / min** | 60 | Ile wywołań API ten sklep może wykonać w ciągu jednej minuty. 60 to spokojny start. 0 wyłącza ten lokalny limit. Wywołania ponad limit są pomijane i trafiają na **Historia**. Grok może mieć własny limit. |
| **Okres przechowywania logów (dni)** | 30 | Ile dni wiersze mają zostać na **Historia**. Minimum to 1 dzień. Starsze wiersze znikają, gdy zapisywane jest nowe wywołanie. Ta wartość nie kasuje zadań, słownika ani zapisanych tłumaczeń. |
| **Temperatura** | 0.2 | Jak swobodnie model może przeredagowywać zdania. Wartość około 0,2 trzyma się źródła. Wartości bliskie 1 zmieniają zdania bardziej. Dozwolony zakres to 0–1. Placeholdery i HTML są sprawdzane później. Wartość działa przy następnym tłumaczeniu. |
| **Zezwól na publikację / zapisywanie** | Tak | Czy moduł może zapisać tłumaczenie w PrestaShop. To ustawienie nie blokuje zapisu na **Ręczny**, w zadaniach masowych ani w **Katalog**. Ikony na stronie tłumaczeń i na formularzach sklepu tylko wypełniają pola. Zapis samej strony robi PrestaShop, przyciskiem **Zapisz**. |

Po naciśnięciu **Zapisz** zobaczysz jeden z komunikatów:

- **Zapisano ustawienia. Nie uruchomiono żadnego tłumaczenia.** Ustawienia są zapisane, a niczego nie przetłumaczono.
- **Zapisano ustawienia. Nie zapisano klucza API, więc nic nie może zostać przetłumaczone, dopóki go nie wkleisz.** Wklej klucz w polu **Klucz API Grok** i naciśnij **Zapisz** jeszcze raz.

**Poczta i cron**

| Pole | Domyślnie | Co robi |
|---|---|---|
| **Powiadomienie e-mail po ukończeniu** | Nie | Wysyła jeden e-mail po zakończeniu zadania masowego. Samo zadanie działa tak samo, zmienia się tylko to, czy przychodzi wiadomość. |
| **Adres e-mail powiadomień** | puste | Adres, na który przychodzi ten e-mail. Pole widać tylko przy włączonym przełączniku powyżej. Puste pole oznacza e-mail sklepu. Sam zapis adresu nie wysyła wiadomości. Temat zaczyna się od nazwy modułu, numeru zadania i statusu. |
| **Adres URL CRON** | adres z tokenem | Tajny adres, pod którym serwer może przetworzyć jedną partię czekającego zadania. Skopiuj go do harmonogramu serwera i nie publikuj. Każdy, kto zna ten adres, może uruchomić partię. Samo otwarcie **Ustawienia** nie uruchamia zadania. |

**Test połączenia** sprawdza klucz i model jednym krótkim wywołaniem. Nie tłumaczy niczego i niczego nie zapisuje.

- **Połączenie OK (N ms). Nie uruchomiono żadnego tłumaczenia.** Połączenie działa.
- **Nie nawiązano połączenia. Nic nie zostało przetłumaczone.** i zaraz potem powód. Sprawdź klucz i model. Szczegóły znajdziesz na **Historia**.

Praktyczny start: wklej klucz, wybierz model i lokalizację źródłową, naciśnij **Test połączenia**, a potem **Zapisz**. Pozostałe liczby zostaw na wartościach z instalacji, dopóki zadanie nie zacznie się zachowywać źle.

### 3.2. Pulpit

Otwórz zakładkę **Pulpit**. Strona liczy brakujące ciągi w katalogu, a potem pokazuje zużycie Grok w postaci kart, wykresów i dziesięciu najnowszych promptów. Pulpit niczego nie tłumaczy i nie zmienia ciągów.

![Pulpit, angielskie zaplecze. Pokrycie jednej lokalizacji, linia crona i filtry historii.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-dashboard.webp)

**Pokrycie**

- **Lokalizacja:** lokalizacja sklepu, dla której liczone są brakujące ciągi.
- **Pokaż:** przelicza tabelę dla wybranej lokalizacji.
- Kolumny: **Sekcja**, **Razem**, **Brakujące**, **Gotowe** i pasek postępu. Sekcje to **Zaplecze**, **Szablony**, **Zainstalowane moduły**, **E-maile** i **Pozostałe**. Kolumna **Brakujące** pokazuje, ile ciągów nie ma jeszcze tłumaczenia w tej lokalizacji.
- Pod tabelą **CRON** widać ten sam adres, który znajduje się w polu **Adres URL CRON** na **Ustawienia**.
- Pusta tabela oznacza, że sklep nie ma jeszcze katalogu w tej lokalizacji. Utwórz go na **Międzynarodowe → Tłumaczenia**.

Po naciśnięciu **Pokaż** zobaczysz komunikat **Pokrycie dla {lokalizacja}. Ta strona zlicza tylko ciągi. Nic nie zostało przetłumaczone.**

**Użycie**

- Gotowe zakresy dat: **Dzisiaj**, **7 dni**, **30 dni**, **Ten miesiąc** i **Cały okres**.
- Filtry: **Od**, **Do**, **Model**, **Typ**, **Status** (**Dowolny**, **Sukces**, **Błąd**), **Język**, **Pracownik** oraz **Prompt lub odpowiedź zawiera**. Wyniki zastosujesz przyciskiem **Filtruj**.
- Karty: **Zapytania**, **Sukces**, **Błędy**, **Wysłane tokeny**, **Otrzymane tokeny**, **Razem tokenów**, **Średni czas** i **Szacowany koszt**. Szacowany koszt to lokalne przybliżenie, a nie faktura od xAI. Kreska oznacza, że Grok nie zwrócił liczby tokenów dla danego wywołania.
- Wykresy: **Żądania i błędy**, **Wysłane i otrzymane tokeny** oraz **Żądania według modelu**. Pod nimi znajdują się grupy **Według dnia**, **Według modelu**, **Według typu**, **Według języka** i **Według pracownika**. Każda ma kolumny **Grupa**, **Wywołania**, **Wysłano**, **Otrzymano** i **Razem**. Pusta grupa pokazuje komunikat **Brak żądań w tym zakresie.**
- **Najnowsze prompty** to dziesięć ostatnich wywołań. **Wyświetl** otwiera prompt i odpowiedź. **Zobacz wszystkie** przenosi do **Historia** (rozdział 3.10). Gdy lista jest pusta, pojawia się napis **Brak żądań.**

Filtrowanie nie kasuje historii i nie zmienia tłumaczeń.

Jeśli sekcja jest prawie pusta, otwórz **Ręczny** i przetłumacz kilka ciągów, albo **Masowe (Bulk)** i przetłumacz całą domenę.

### 3.3. Ręczny

Otwórz **Ręczny**. Tę zakładkę używa się do tłumaczenia jednej domeny albo jednego klasycznego modułu, zwykle po kilkadziesiąt ciągów naraz. Samo filtrowanie niczego nie zapisuje.

![Ręczny, angielskie zaplecze. Sekcja, źródło, cel, domena, tylko puste i szukaj.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-manual.webp)

| Pole | Domyślnie | Co robi |
|---|---|---|
| **Sekcja** | Zaplecze | Który katalog jest czytany: **Zaplecze**, **Szablony**, **Zainstalowane moduły**, **E-maile** albo **Pozostałe**. Zmiana sekcji przeładowuje stronę i pokazuje tylko pola tej sekcji. Nie wywołuje Grok. |
| **Szablon** | puste | Tylko dla **Szablony**. Ogranicza listę do jednego szablonu. |
| **Moduł** | puste | Tylko dla **Zainstalowane moduły**. Ogranicza listę do jednego modułu. Klasyczny moduł bez domeny ładuje wszystkie jego ciągi. |
| **Domena** | puste | Ten sam podział co na **Międzynarodowe → Tłumaczenia**. Wybierz domenę i naciśnij **Filtruj**. Pole jest ukryte dla klasycznego modułu i dla sekcji, które nie mają domen. Pusty wiersz to kreska z podpisem wyboru. |
| **Źródło** | **Lokalizacja źródłowa** z **Ustawienia** albo en-US | Język, z którego pobierane są ciągi. Wybierz język, który ma już dobre tłumaczenie. |
| **Cel** | pierwszy język z listy | Język, który chcesz uzupełnić. Musi istnieć w **Międzynarodowe → Lokalizacja → Języki**. |
| **Tylko puste** | Tak | Pokazuje tylko ciągi bez tłumaczenia. Po wyłączeniu widać wszystkie ciągi. Zapisanych tłumaczeń to nie zmienia. |
| **Szukaj** | puste | Zostawia tylko ciągi źródłowe zawierające wpisane słowo. |

Jak to zrobić:

1. Ustaw **Sekcja**, **Źródło** i **Cel**.
2. Dla **Szablony** wybierz **Szablon**. Dla **Zainstalowane moduły** wybierz **Moduł**.
3. Naciśnij **Filtruj**. Lista **Domena** się odświeży. Wybierz domenę i naciśnij **Filtruj** jeszcze raz. Dla klasycznego modułu pomiń domenę. Wtedy **Filtruj** załaduje wszystkie ciągi modułu.
4. Zaznacz wiersze. Przyciski **Zaznacz wszystkie** i **Odznacz wszystkie** zaznaczają albo czyszczą całą listę.
5. Naciśnij **Tłumacz zaznaczone (z przeglądem)**. Otworzy się tabela **Przejrzyj przed zapisaniem** z kolumnami **Źródło**, **Propozycja AI** i **Ostrzeżenia**. Odznacz wiersze, których nie chcesz zapisać, i popraw propozycję bezpośrednio w polu. Następnie naciśnij **Zapisz zatwierdzone**.
6. Możesz też zaznaczyć **Zapisz teraz (pomiń przegląd)** przed tłumaczeniem. Poprawne wiersze zapiszą się od razu, bez tabeli przeglądu.

Kolumny listy ciągów to **Źródło**, **Bieżący** i **Status** (**puste** albo **wypełnione**).

Komunikaty, które możesz zobaczyć:

- **Wczytano N ciągów. Zaznacz wybrane wiersze, a następnie naciśnij Przetłumacz wybrane. Nic jeszcze nie zostało zapisane.**
- **Wczytano N ciągów z całego modułu. Zaznacz wybrane wiersze, a następnie naciśnij Przetłumacz wybrane. Nic jeszcze nie zostało zapisane.** Tak wygląda lista klasycznego modułu.
- **Ten moduł nie ma domeny tłumaczeń. Naciśnij Filtruj, aby załadować każdy ciąg w module. Nic nie zostało wysłane do Grok.**
- **Żadne ciągi nie pasują do tego filtra. Nic nie zostało wysłane do Grok.**
- **Żadne ciągi nie pasują do tego filtra. Wyłącz opcję Tylko puste lub ten moduł nie ma klasycznych ciągów. Nic nie zostało wysłane do Grok.**
- **Nic nie zostało przetłumaczone. Wybierz domenę, a następnie naciśnij Filtruj, aby wczytać ciągi.**
- **Nic nie zostało przetłumaczone. Wybierz szablon, a następnie naciśnij Filtruj.**
- **Nic nie zostało przetłumaczone. Wybierz moduł, a następnie naciśnij Filtruj.**
- **Nic nie zostało przetłumaczone. Zaznacz co najmniej jeden wiersz.**
- **Nic nie zostało przetłumaczone. Brak klucza API Grok. Otwórz Ustawienia i wklej klucz.**
- **Przegląd jest gotowy. Nic nie zostanie zapisane, dopóki nie naciśniesz Zapisz zatwierdzone.**
- **Zapisano. Zatwierdzone ciągi zostały zapisane dla języka docelowego.**
- **Zapisano N. Zapisano tylko zaznaczone wiersze.**
- **Nic nie zapisano. Zaznacz OK przy wierszach, które chcesz zachować.**
- **Nie zapisano z powodu uszkodzonych placeholderów lub HTML: N.** Te wiersze zostały pominięte. Popraw placeholdery i znaczniki, tak aby zgadzały się ze źródłem, i zapisz ponownie.
- **Nic nie zapisano. Włącz opcję Zezwól na publikację w Ustawieniach.**
- **Nic nie zostało przetłumaczone. Te wiersze nie znajdują się na bieżącej liście. Naciśnij Filtruj i zaznacz je ponownie.**

Zmiana sekcji pokazuje też krótką informację, na przykład **Sekcja to Zaplecze (Back office). Szablon i moduł nie są używane.** wraz z komunikatem **Nic nie zostało wysłane do Grok.** Tak samo wygląda to dla **Szablony**, **Zainstalowane moduły**, **E-maile** i **Pozostałe**.

### 3.4. Masowe

Otwórz **Masowe (Bulk)**. Tu tworzy się jedno zadanie obejmujące wiele domen i języków. **Szacuj** niczego nie zapisuje. **Uruchom zadanie** dodaje wiersz na **Zadania**. Tekst zostanie zapisany dopiero wtedy, gdy zadanie się przetworzy i włączona jest opcja **Zezwól na publikację / zapisywanie**.

![Masowe, angielskie zaplecze. Sekcja, źródło, cele, domeny, polityka i zadanie próbne.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-bulk.webp)

| Pole | Domyślnie | Co robi |
|---|---|---|
| **Sekcja** | Zaplecze | Który katalog czyta zadanie. Strona się przeładowuje i pokazuje pole **Szablon** tylko dla **Szablony**, a pole **Moduł** tylko dla **Zainstalowane moduły**. Ciągi spoza wybranej sekcji nie trafiają do zadania. Zmiana sekcji sama w sobie nie uruchamia zadania. |
| **Szablon** | puste | Tylko dla **Szablony**. Pozostałe szablony są pomijane. |
| **Moduł** | puste | Tylko dla **Zainstalowane moduły**. Klasyczny moduł nie ma domen, więc **Szacuj** i **Uruchom zadanie** obejmują wszystkie jego ciągi. |
| **Źródło** | **Lokalizacja źródłowa** z **Ustawienia** albo en-US | Lokalizacja traktowana jako oryginał. Każdy język docelowy jest tłumaczony z tej lokalizacji. |
| **Cele** | nic nie zaznaczono | Lokalizacje, które zadanie ma uzupełnić. Zaznacz jedną lub więcej. Kliknięcie bez Ctrl zastępuje dotychczasowe zaznaczenie. Zadanie tworzy osobny zestaw ciągów dla każdej zaznaczonej lokalizacji. |
| **Domeny** | nic nie zaznaczono | Domeny, które wchodzą do zadania. Żeby zaznaczyć kilka wierszy, przytrzymaj Ctrl albo Cmd. Niezaznaczone domeny są pomijane. Puste zaznaczenie ma sens tylko wtedy, gdy chcesz utworzyć puste zadanie. Pole jest ukryte dla klasycznego modułu. |
| **Polityka** | Wypełnij puste | **Wypełnij puste** pomija ciągi, które już mają tłumaczenie. **Nadpisz wszystko** wysyła każdy ciąg i zastępuje gotowe tłumaczenia, o ile zadanie może zapisywać. **Przestarzałe, jeśli równe źródłu** wysyła ciągi, których tłumaczenie jest nadal takie samo jak źródło. |
| **Zadanie próbne (Dry-run)** | Nie | Uruchamia model, ale nie zapisuje odpowiedzi w PrestaShop. Zadanie i tak pojawia się na **Zadania**. Pliki katalogu i tłumaczenia w bazie zostają bez zmian. |

Jak to zrobić:

1. Ustaw **Sekcja**, **Źródło** i **Cele**.
2. Dla **Szablony** wybierz **Szablon**. Dla **Zainstalowane moduły** wybierz **Moduł**.
3. Gdy lista jest widoczna, wybierz **Domeny**. Przytrzymaj Ctrl albo Cmd, żeby zaznaczyć kilka.
4. Naciśnij **Szacuj**. Sprawdź liczbę ciągów, szacunek tokenów, szacunek kosztu i podgląd **Próbka**. Nic nie zostało wysłane do Grok ani zapisane. Zobaczysz komunikat: **Tylko szacunek: N ciągów, ~N tokenów, ~$N. Nic nie zostało wysłane do Grok ani zapisane.**
5. Naciśnij **Uruchom zadanie**. Moduł otworzy to zadanie. Zobaczysz komunikat: **Zadanie #N oczekuje (N ciągów, szac. $N). Nie zostało jeszcze uruchomione.**

Jeśli brakuje wymaganego wyboru, zobaczysz jeden z komunikatów:

- **Nic nie uruchomiono. Wybierz co najmniej jeden język docelowy.**
- **Nic nie uruchomiono. Wybierz szablon.**
- **Nic nie uruchomiono. Wybierz moduł.**
- **Nic nie zostało uruchomione. Brak klucza API Grok. Otwórz Ustawienia i wklej klucz. Nie utworzono żadnego zadania.**

### 3.5. Zadania

Otwórz **Zadania**. Lista pokazuje wszystkie zadania. Gdy nie ma żadnego, zobaczysz napis **Brak zadań.**

![Zadania, angielskie zaplecze. Lista zadań ze statusem, językami, postępem, kosztem, pracownikiem i datą.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-jobs.webp)

Kolumny: **#**, **Status**, **Języki**, **Postęp**, **Koszt**, **Pracownik**, **Data** i **Otwórz**.

Nazwy statusów na tym ekranie są po angielsku: **pending**, **running**, **paused**, **cancelled**, **completed**, **completed_with_errors** i **failed**.

Naciśnij **Otwórz** przy wybranym wierszu. Szczegóły pokazują **Status**, postęp w formie zrobione/razem, liczbę **nie powiodło się**, liczbę **pominięto**, koszt, numer pracownika oraz oznaczenie **próbny (dry-run)**, jeśli ten tryb był włączony. Pod tym wszystkim jest pasek postępu.

Przyciski otwartego zadania:

- **Przetwórz partię** tłumaczy jedną partię i się zatrzymuje. Komunikat: **Przetworzono jeden fragment. Sprawdź poniższe wiersze, aby zobaczyć, co zostało zapisane, pominięte lub zakończone niepowodzeniem.** Jeśli nie ma już nic do zrobienia, zobaczysz: **Zadanie nie ma już oczekujących ciągów znaków.**
- **Przetwarzaj automatycznie** pobiera kolejne partie, aż zadanie się skończy albo zostanie wstrzymane.
- **Wstrzymaj** zatrzymuje kolejne partie. Komunikat: **Zadanie wstrzymane. Nie będzie tłumaczyć kolejnych ciągów, dopóki go nie wznowisz.**
- **Wznów** przywraca wstrzymane zadanie do kolejki. Komunikat: **Zadanie ponownie oczekuje. Nie uruchamia się samoczynnie. Naciśnij Przetwórz fragment, Automatyczne przetwarzanie lub pozwól cronowi je wywołać.**
- **Ponów nieudane** wrzuca nieudane wiersze z powrotem do kolejki. Komunikat: **Ponowiono próbę dla N nieudanych elementów.**
- **Wycofaj** pyta **Wycofać to zadanie?** i przywraca poprzedni tekst tam, gdzie moduł trzymał jego kopię. Komunikat: **Cofnięcie (Rollback): przywrócono N tłumaczeń.**
- **Błędy CSV** pobiera listę nieudanych wierszy.
- **Tylko nieudane** pokazuje tylko wiersze ze statusem **failed**.
- **Kolejka przeglądu** otwiera **Przegląd**.

Na tym ekranie nie ma przycisku anulowania. Jeśli nie chcesz, żeby zadanie działało dalej, może zostać wstrzymane (**paused**).

Kolumny tabeli wierszy to **ID**, **Domena**, **Lokalizacja**, **Status**, **Źródło**, **Nowy** i **Błąd**. Statusy pozycji też zostają po angielsku: **pending**, **processing**, **done**, **failed**, **skipped** i **rolled_back**.

Gdy sklep trafi we własny limit na minutę w trakcie partii, zadanie zatrzymuje się automatycznie, a linia błędu pozostaje po angielsku: **Rate limit — job auto-paused. Resume later.** Później naciśnij **Wznów**, a potem **Przetwórz partię**.

Zadanie próbne wywołuje Grok i zapisuje propozycję przy zadaniu, ale nie zapisuje katalogu.

### 3.6. Przegląd

Otwórz **Przegląd**. To kolejka tłumaczeń z zadań masowych, które czekają na sprawdzenie. Strona mówi **Kolejka wymagająca przeglądu (wynik jakości / flagi).** Gdy kolejka jest pusta, zobaczysz **Kolejka jest pusta.**

![Przegląd, angielskie zaplecze. Kolejka do przejrzenia.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-review.webp)

Kolumny: **ID**, **Wynik**, **Domena**, **Źródło**, **AI**, **Flagi**, **Zatwierdź** i **Odrzuć**.

Wiersz trafia tutaj, gdy kontrola jakości da wynik poniżej 70, gdy placeholdery albo HTML się nie zgadzają lub gdy tłumaczenie jest wyraźnie dłuższe od źródła. Jeśli zadanie mogło publikować, a ciąg przeszedł walidację, katalog może już zawierać tę propozycję. **Zatwierdź** i **Odrzuć** zmieniają tylko kolejkę. Nie zapisują nowego tłumaczenia i nie przywracają starego. Po każdym z tych przycisków zobaczysz komunikat **Zaktualizowano przegląd.**, a wiersz znika z kolejki.

Tabela przeglądu na **Ręczny** to osobny ekran. Tam działa przycisk **Zapisz zatwierdzone**.

### 3.7. Katalog

Otwórz **Katalog**. Ta zakładka tłumaczy pola produktów, kategorii albo CMS. Nie jest tym samym co **Międzynarodowe → Tłumaczenia**. Jedno naciśnięcie przetwarza najwyżej 100 rekordów.

![Katalog, angielskie zaplecze. Obiekt, pola, język źródłowy, język docelowy, tylko puste i zacznij po ID.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-catalog.webp)

| Pole | Domyślnie | Co robi |
|---|---|---|
| **Obiekt** | product | Które rekordy są czytane: **product**, **category** albo **cms**. Te trzy nazwy zostają po angielsku. Zmiana obiektu przeładowuje stronę i pokazuje tylko pola tego typu. Sama zmiana niczego nie tłumaczy. Komunikat: **Wyświetlanie pól dla {obiekt}. Nic nie zostało przetłumaczone.** |
| **Pola** | wszystkie pola danego obiektu | Teksty, które wysyła ta partia. Przytrzymaj Ctrl albo Cmd, żeby zaznaczyć kilka. **Tytuł** to nazwa produktu, nazwa kategorii albo tytuł strony CMS. **Treść** to treść strony CMS. Jeśli linki mają zostać bez zmian, odznacz **Przyjazny adres URL**. Tłumaczone są tylko zaznaczone pola. |
| **Język źródłowy** | lista języków sklepu | Język, z którego kopiowany jest tekst. Sam język źródłowy nie jest zmieniany. |
| **Język docelowy** | lista języków sklepu | Język, który dostaje tłumaczenie. Musi być inny niż źródłowy. Zapisywanych jest do 100 rekordów. |
| **Tylko puste** | Tak | Pomija pola, które w języku docelowym mają już tekst. Ta opcja nie pozwala nadpisać tekstu, jeśli publikacja jest dozwolona. |
| **Zacznij po ID** | 0 | Pomija rekordy do wskazanego ID. Zostaw 0, żeby zacząć od pierwszego. Po partii pole pokazuje ostatnio odczytane ID. Naciśnij przycisk jeszcze raz, aby przejść dalej. |

Pola produktu: **Tytuł**, **Krótki opis**, **Opis**, **Tytuł meta**, **Opis meta** i **Przyjazny adres URL**.

Pola kategorii: **Tytuł**, **Opis**, **Tytuł meta**, **Opis meta** i **Przyjazny adres URL**.

Pola CMS: **Tytuł**, **Opis meta**, **Słowa kluczowe meta**, **Treść** i **Przyjazny adres URL**.

Naciśnij **Tłumacz partię (maks. 100)**. Komunikat na końcu: **Katalog zakończony: zapisano N, nie powiodło się N.** Pod formularzem widać też liczniki **Zapisano** i **nie powiodło się**.

- **Nic nie zostało przetłumaczone. Brak klucza API Grok. Otwórz Ustawienia i wklej klucz.**
- **Nic nie zapisano. Włącz opcję Zezwól na publikację w Ustawieniach.**
- **Nic nie zostało przetłumaczone. Język źródłowy i docelowy muszą być różne.**
- **Nic nie zostało przetłumaczone. Wybierz co najmniej jedno pole.**

### 3.8. Słownik

Otwórz **Słownik**. Lista zawiera słowa, które model ma zostawić bez zmian albo przetłumaczyć w określony sposób. Dodanie terminu nie zmienia tłumaczeń, które już są zapisane. Kolejne tłumaczenie będzie jednak korzystać z listy.

![Słownik, angielskie zaplecze. Dodanie terminu i formularz CSV.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-glossary.webp)

| Pole | Domyślnie | Co robi |
|---|---|---|
| **Termin źródłowy** | puste | Słowo lub wyrażenie w języku źródłowym. Wpisz je dokładnie, z wielkimi literami, jeśli mają znaczenie. Pole jest wymagane. |
| **Docelowe ustawienia regionalne** | puste | Ogranicza wpis do jednej lokalizacji docelowej, na przykład pl-PL. Puste pole stosuje wpis do każdego języka docelowego. Wypełniona lokalizacja jest ignorowana dla pozostałych języków. |
| **Termin docelowy** | puste | Brzmienie, które ma się pojawić w tłumaczeniu. Zostaw puste tylko wtedy, gdy włączona jest opcja **Nie tłumacz**. |
| **Nie tłumacz** | Nie | Ustawienie **Tak** każe modelowi skopiować termin źródłowy bez zmian. Używaj tego dla nazw marek, SKU i placeholderów. Nie oznacza to, że **Termin docelowy** jest tłumaczeniem, którego chcesz. |

Naciśnij **Dodaj**.

- **Dodano termin do słownika. Zapisane wcześniej tłumaczenia nie zostały zmienione.**
- **Nic nie dodano. Wpisz termin źródłowy.**

Kolumny tabeli to **Źródło**, **Lokalizacja**, **Cel**, **Nie tłumacz** (**Tak** albo **Nie**) i **Usuń**. Gdy tabela jest pusta, zobaczysz **Brak terminów w słowniku.** Przycisk **Usuń** kasuje dany wiersz, a potem pojawia się komunikat **Usunięto termin ze słownika.**

**Słownik CSV**

| Pole | Domyślnie | Co robi |
|---|---|---|
| **Plik CSV** | puste | Plik musi mieć kolumny source_term, target_locale, target_term i do_not_translate. **Importuj CSV** dodaje wiersze, które da się odczytać. **Eksportuj CSV** pobiera bieżącą listę i ignoruje pole pliku. Eksport niczego w słowniku nie zmienia. |

- **Zaimportowano N wierszy.**
- **Brak pliku CSV.** Wybierz plik i naciśnij **Importuj CSV** jeszcze raz.
- **Nie można otworzyć pliku CSV.** Zapisz plik jako CSV i spróbuj ponownie.

### 3.9. Wykluczenia

Otwórz **Wykluczenia**. Lista zawiera wzorce ciągów źródłowych, które moduł ma pominąć. Pasujący ciąg nie trafia do Grok, ale nie jest usuwany z PrestaShop. Dodanie wzorca nie zmienia ciągów, które już są zapisane.

![Wykluczenia, angielskie zaplecze. Wzorzec, typ i tabela wzorców.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-excludes.webp)

| Pole | Domyślnie | Co robi |
|---|---|---|
| **Wzorzec** | puste | Tekst porównywany z każdym ciągiem źródłowym. Pole jest wymagane. |
| **Typ** | exact | **exact** oznacza cały ciąg, **prefix** początek, **contains** fragment, a **regex** wyrażenie regularne PHP, stosowane dokładnie tak, jak zostało wpisane. Najpierw sprawdź krótki wzorzec. Zły typ może pominąć za dużo albo nic. |

Naciśnij **Dodaj**.

- **Dodano wzorzec wykluczenia. Pasujące ciągi znaków zostaną pominięte przy następnym uruchomieniu. Nic nie zostało teraz przetłumaczone.**
- **Nic nie dodano. Wpisz wzorzec.**

Kolumny tabeli to **Wzorzec**, **Typ**, **Wł.** i **Usuń**. Kolumna **Wł.** pokazuje 1, gdy wzorzec jest używany. Pusta tabela oznacza **Brak wzorców.** Przycisk **Usuń** kasuje wiersz, a potem pojawia się komunikat **Usunięto wzorzec.**

### 3.10. Historia

Otwórz **Historia**. To pełna lista wywołań Grok, łącznie z testami połączenia i wywołaniami zablokowanymi, zanim wyszły. Wykresy i dziesięć najnowszych promptów znajdziesz na **Pulpit**. Przycisk **Zobacz wszystkie** na **Pulpit** otwiera tę zakładkę.

![Historia, angielskie zaplecze. Lista wywołań i wyczyszczenie historii.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-history.webp)

Kolumny: **ID**, **Kiedy**, **Status**, **Typ**, **Model**, **Języki**, **Wysłano**, **Otrzymano**, **Razem**, **Czas**, **Prompt** i **Wyświetl**.

**Typ** to jedna z wartości: **Ręczny**, **Strona tłumaczeń**, **Zadanie masowe**, **Katalog**, **Test połączenia**, **Przetłumacz** albo **Nie wysłano**. **Status** to **Sukces** albo **Błąd**.

**Wyświetl** otwiera prompt i **Odpowiedź**, a także wartości **HTTP**, **Wysłano**, **Otrzymano** i **Razem**. **Powrót do listy** wraca do tabeli. Jeśli wiersz został usunięty, zobaczysz komunikat **Ten wiersz historii już nie istnieje.** Gdy szczegółów nie da się wczytać, strona pokaże **Nie udało się załadować tego żądania.**

**Poprzednia** i **Następna** przechodzą między stronami. Linia pod tabelą to **Strona N / N**.

**Wyczyść historię** pyta: **Wyczyścić zapisaną historię? Zapisane tłumaczenia pozostaną.** Potwierdzenie usuwa tylko te wiersze. Komunikat: **Wyczyszczono historię. Zapisane tłumaczenia nie zostały zmienione.** Pusta lista pokazuje **Brak żądań.**

Ustawienie **Okres przechowywania logów (dni)** na **Ustawienia** również usuwa wiersze starsze niż podana liczba dni, gdy zapisywane jest nowe wywołanie.

### 3.11. Aktualizacje

Otwórz **Aktualizacje**. Ta strona sprawdza, czy dostępny jest nowszy pakiet. Niczego nie tłumaczy.

![Aktualizacje, angielskie zaplecze. Sprawdzenie ręczne, powiadomienia automatyczne i strona produktu.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-updates.webp)

| Pole | Domyślnie | Co robi |
|---|---|---|
| **Sprawdź ręcznie** | przycisk **Sprawdź teraz** | Pyta wydawcę raz. Komunikat **Moduł jest aktualny!** oznacza, że ta instalacja jest najnowsza. **Dostępna jest nowa wersja!** oznacza, że istnieje nowszy pakiet. Pobierz go ze strony produktu i wgraj przez **Module Manager**. |
| **Powiadomienia automatyczne** | Włączone | **Włączone** pozwala zapleczu pokazywać komunikat, gdy jest nowszy pakiet. **Wyłączone** ten komunikat wyłącza. Naciśnij **Zapisz**, żeby zachować wybór. Odinstalowanie modułu nie czyści tego ustawienia. |
| **Strona produktu** | odnośnik z nazwą modułu | Otwiera stronę modułu. Adres znajdziesz w rozdziale 7. |

Gdy dostępny jest nowszy pakiet, zaplecze może też pokazać komunikat **Dostępna jest nowa wersja, sprawdź http://MyPresta.eu, aby uzyskać więcej informacji** z odnośnikiem **Więcej szczegółów w dzienniku zmian**.

### 3.12. Przyciski na Międzynarodowe → Tłumaczenia

Otwórz **Międzynarodowe**, potem **Tłumaczenia**, i otwórz katalog. Gdy **Przyciski pojedynczych pól — Międzynarodowe → Tłumaczenia** ma wartość **Tak**, każde pole dostaje przycisk **Przetłumacz**. Jedno kliknięcie wypełnia to pole. Żeby tekst został zapisany, nadal trzeba nacisnąć **Zapisz** PrestaShop.

Gdy **Pola wyboru dla poszczególnych pól — Międzynarodowe → Tłumaczenia** ma wartość **Tak**, strona pokazuje też pasek **Tłumaczenia Grok**.

- **Źródło** pochodzi z **Lokalizacja źródłowa** na **Ustawienia**. Gdy to ustawienie jest puste, pasek używa en-US. Pole można poprawić ręcznie.
- **Cel** to język katalogu, który masz otwarty.
- **Zaznacz wszystkie**, **Odznacz wszystkie** i **Zaznacz puste** zmieniają zaznaczenia.
- **Przetłumacz puste** wypełnia puste pola. **Przetłumacz wybrane** wypełnia zaznaczone pola.
- Podpowiedź brzmi: **Wypełnia pola. Zapisz za pomocą przycisku PrestaShop.**
- W trakcie pasek pokazuje **Tłumaczenie…**, a po zakończeniu **Gotowe**.
- **Wybrane** pokazuje, ile pól jest zaznaczonych.
- Komunikat **Zaznacz co najmniej jedno pole.** pojawia się, gdy klikniesz **Przetłumacz wybrane** bez zaznaczenia.
- **Najpierw wypełnij pole języka źródłowego.** pojawia się, gdy tekst źródłowy jest pusty.
- **Nie znaleziono pliku wiadomości e-mail w języku źródłowym.** pojawia się na ekranie e-maila, gdy brakuje pliku poczty źródłowej.
- **Przetłumacz puste w tej sekcji** wypełnia puste ciągi w aktualnie oglądanej sekcji.

Te przyciski nie zastępują **Zapisz** na stronie PrestaShop. Ustawienie **Zezwól na publikację / zapisywanie** ich nie blokuje, bo tylko wypełniają formularz.

### 3.13. Przyciski na formularzach produktu, kategorii i CMS

Otwórz produkt, kategorię, stronę CMS albo inny formularz zaplecza, który ma pole dla każdego języka. Gdy **Przyciski pojedynczych pól — formularze sklepu** ma wartość **Tak**, każde takie pole dostaje przycisk **Przetłumacz**. Jedno kliknięcie wypełnia pole tekstem z języka źródłowego na tym samym formularzu.

![Formularz produktu, angielskie zaplecze. Pasek Tłumaczenia Grok pod polami opisu.](https://mypresta.eu/docs/images/docs/myaitranslationsgrok-product.webp)

Gdy **Pola wyboru dla poszczególnych pól — formularze sklepu** ma wartość **Tak**, formularz pokazuje też pasek **Tłumaczenia Grok**.

- **Źródło** startuje z **Lokalizacja źródłowa**, a gdy to ustawienie jest puste, z en-US.
- **Cel** wymienia pozostałe języki sklepu oraz **wszystkie inne języki**.
- Przyciski **Zaznacz wszystkie**, **Odznacz wszystkie**, **Zaznacz puste**, **Przetłumacz puste** i **Przetłumacz wybrane** działają tak samo jak na stronie tłumaczeń.
- Podpowiedź brzmi: **Wypełnia pola. Zapisz za pomocą przycisku PrestaShop.**
- Komunikaty **Zaznacz co najmniej jedno pole.**, **Najpierw wypełnij pole języka źródłowego.** i **Pole języka źródłowego nie znajduje się na tej stronie.** podpowiadają, co poprawić.
- **Język docelowy nie jest językiem tego sklepu.** oznacza, że cel nie pasuje do języków sklepu.
- Linia nad polem może brzmieć **Przetłumacz z** nazwy źródła **na** nazwę celu.

Żeby zachować wypełnione pola, naciśnij **Zapisz** PrestaShop na tym formularzu. Pasek sam z siebie nie zapisuje produktu.

## 4. Front sklepu

Motyw sklepu nie wyświetla niczego z tego modułu. Klient nie widzi przycisku tłumaczenia, formularza ani strony statusu.

Jedynym adresem poza zapleczem jest **Adres URL CRON** z **Ustawienia**, powtórzony pod tabelą pokrycia na **Pulpit**. Skopiuj go do harmonogramu serwera. Każde wywołanie przetwarza jedną partię z pierwszego czekającego albo działającego zadania i kończy się. Samo otwarcie **Ustawienia** tego adresu nie wywołuje.

| Co widać | Co zrobić |
|---|---|
| Linia JSON z wynikiem partii | Partia została wykonana. Otwórz **Zadania** i przeczytaj wiersze. |
| **No pending jobs** | Nie ma czekającego zadania. Utwórz je na **Masowe (Bulk)** albo poprzednie jest już zakończone, wstrzymane lub anulowane. Ten napis zostaje po angielsku. |
| **Forbidden** | Adres jest błędny albo token został zmieniony przy ponownej instalacji. Skopiuj **Adres URL CRON** jeszcze raz. Nie publikuj tego adresu. Ten napis zostaje po angielsku. |

Nie dopisuj własnych parametrów. Adres, który kopiujesz, jest dokładnie tym, który moduł odczytuje.

## 5. Problemy

**Brak klucza API Grok.** pojawia się na każdej zakładce razem z odnośnikiem **Otwórz ustawienia**. Wklej klucz na **Ustawienia**, naciśnij **Test połączenia**, a potem **Zapisz**.

**Sklep musi posiadać co najmniej dwa języki.** Dodaj język w **Międzynarodowe → Lokalizacja → Języki**, a potem otwórz moduł ponownie.

**Nie nawiązano połączenia. Nic nie zostało przetłumaczone.** Zaraz za tym zdaniem jest powód. Sprawdź klucz, model i to, czy serwer ma dostęp do adresu Grok. Otwórz **Historia** i naciśnij **Wyświetl** przy wierszu z błędem.

**Monthly API budget has been exhausted.** Ten komunikat zostaje po angielsku. Podnieś **Budżet USD / miesiąc** albo ustaw 0, jeśli nie chcesz limitu, i naciśnij **Zapisz**. Tekst, który już został zapisany, pozostaje bez zmian.

**Grok rate limit (429). Try again later.** Ten komunikat zostaje po angielsku. Poczekaj i uruchom partię ponownie. Jeśli zadanie pokazuje **Rate limit — job auto-paused. Resume later.**, naciśnij **Wznów**, a potem **Przetwórz partię**. Gdy problem wraca, zmniejsz **Rozmiar partii (Batch size)** albo zwiększ przerwę między wywołaniami crona. **Limit częstotliwości / min** dotyczy tylko tego sklepu, a Grok może i tak odrzucić wywołanie.

**Nic nie zapisano. Włącz opcję Zezwól na publikację w Ustawieniach.** Ustaw **Zezwól na publikację / zapisywanie** na **Tak**, naciśnij **Zapisz** i spróbuj jeszcze raz. Ikony na formularzach nadal tylko wypełniają pola.

**Nie zapisano z powodu uszkodzonych placeholderów lub HTML: N.** Propozycja zmieniła placeholder albo znacznik. Popraw ją tak, żeby zgadzała się ze źródłem, albo zostaw wiersz odznaczony i naciśnij **Zapisz zatwierdzone** ponownie.

**Nic nie zostało przetłumaczone. Wybierz szablon, a następnie naciśnij Filtruj.** albo **Wybierz moduł.** Sekcja potrzebuje tego wyboru, zanim lista się wczyta.

**Żadne ciągi nie pasują do tego filtra. Nic nie zostało wysłane do Grok.** Wyłącz **Tylko puste**, wyczyść **Szukaj** albo wybierz inną domenę.

**Brak pliku CSV.** albo **Nie można otworzyć pliku CSV.** Wybierz plik CSV z czterema kolumnami i naciśnij **Importuj CSV** jeszcze raz.

**Nie znaleziono pliku wiadomości e-mail w języku źródłowym.** Na **Międzynarodowe → Tłumaczenia** otwórz sekcję e-maila dla języka, który ma już plik poczty, albo najpierw wygeneruj tłumaczenia poczty w PrestaShop.

**Ten wiersz historii już nie istnieje.** Wiersz został wyczyszczony albo usunięty przez **Okres przechowywania logów (dni)**. Tłumaczenie, które zostało zapisane, nadal jest w sklepie.

Brakuje pozycji w menu albo zaplecze mówi, że nie znaleziono kontrolera. Otwórz **Module Manager**, znajdź **AI Translations with Grok** i naciśnij **Konfiguruj**. To odtwarza pozycję w menu **Międzynarodowe**. Jeśli modułu nie ma na liście, wgraj ZIP jeszcze raz.

Instalacja zatrzymuje się na **Nie udało się utworzyć tabel modułu.** Oznacza to, że użytkownik bazy nie ma uprawnień do tworzenia tabel. Popraw uprawnienia bazy i naciśnij **Instaluj** ponownie. Komunikat **Nie można dodać zakładki menu.** znaczy, że pozycji menu nie udało się utworzyć. Po udanej instalacji naciśnij **Konfiguruj** albo zainstaluj moduł jeszcze raz.

## 6. Dla developera

### 6.1. Przegląd

Nazwa techniczna to `myaitranslationsgrok`, wersja `1.2.0`, autor MyPresta.eu, a zakładka modułu to `administration`. Nazwa na liście i etykieta w menu **Międzynarodowe** to **AI Translations with Grok**. Klasa to `myaitranslationsgrok`. Minimalna wersja w `ps_versions_compliancy` to `1.7.0.0`.

`getContent()` wywołuje `ensureTab()` i przekierowuje do `AdminMyaitranslationsgrok`. Ustawienia czyta `MyaitgkConfigService` (klucze `MYAITGK_*`). Klucz API jest zaszyfrowany i trzymany w `MYAITGK_API_KEY_ENC`. Wywołania tłumaczenia idą przez `MyaitgkTranslateService` do `MyaitgkGrokTranslationProvider`, który wysyła JSON POST na `https://api.x.ai/v1/chat/completions`. Zapis katalogu odbywa się przez `MyaitgkTranslationAdapter`, a zapis produktu, kategorii i CMS przez `MyaitgkCatalogTranslateService`. Po zapisaniu tłumaczenia katalogu wywoływane jest `Tools::clearCache()`.

Moduł nie definiuje metod `enable()` ani `disable()`. Wyłączenie w **Module Manager** nie uruchamia żadnego dodatkowego sprzątania. Odinstalowanie usuwa zakładkę menu, tabele i klucze `MYAITGK_*`.

### 6.2. Pliki

- `myaitranslationsgrok.php` - instalacja, odinstalowanie, hooki, zakładka i konfiguracja przycisków pól.
- `controllers/admin/AdminMyaitranslationsgrokController.php` - każda zakładka zaplecza i akcje AJAX.
- `controllers/front/cron.php` - jedna partia zadania dla adresu crona.
- `lib/updateChecker.php` - zakładka **Aktualizacje** i sprawdzanie wersji.
- `sql/install.php`, `sql/uninstall.php` - utworzenie i usunięcie tabel.
- `src/Admin/MyaitgkForms.php` - pola HelperForm i teksty `desc`.
- `src/Admin/MyaitgkSectionHelp.php` - panel **Pomoc**.
- `src/Service/MyaitgkConfigService.php` - klucze, lista modeli i token crona.
- `src/Service/MyaitgkTranslateService.php` - budżet, limit, słownik, wykluczenia i zapis.
- `src/Service/MyaitgkBulkJobFactory.php` - tworzy zadanie z **Masowe (Bulk)**.
- `src/Service/MyaitgkCatalogTranslateService.php` - partie produktów, kategorii i CMS.
- `src/Service/MyaitgkDashboardService.php` - liczniki pokrycia.
- `src/Service/MyaitgkRateLimiter.php` - limit na minutę zapisywany w `var/rate_limit.json`.
- `src/Provider/MyaitgkGrokTranslationProvider.php` - żądanie do xAI.
- `src/Provider/MyaitgkPromptBuilder.php` - prompt systemowy i użytkownika.
- `src/Job/MyaitgkJobWorker.php` - partia, ponowienie i e-mail po zakończeniu.
- `src/Job/MyaitgkJobRepository.php`, `src/Job/MyaitgkJobStatuses.php` - wiersze zadań i stałe statusów.
- `src/Quality/MyaitgkPlaceholderValidator.php`, `MyaitgkHtmlValidator.php`, `MyaitgkPsNativeValidator.php`, `MyaitgkEmailHtmlPipeline.php`, `MyaitgkQualityScorer.php` - kontrole przed zapisem.
- `src/Glossary/MyaitgkGlossaryRepository.php`, `MyaitgkExcludePatternRepository.php` - słownik i wykluczenia.
- `src/Audit/MyaitgkRequestLogRepository.php` - **Historia** i raport pulpitu.
- `src/Audit/MyaitgkSnapshotService.php` - kopie do wycofania.
- `src/Security/MyaitgkApiKeyEncryptor.php` - szyfrowanie klucza przez OpenSSL.
- `src/Adapter/MyaitgkTranslationAdapter.php`, `MyaitgkLegacyModuleCatalogue.php` - katalogi PrestaShop i klasyczne moduły `translations/{iso}.php`.
- `views/templates/admin/configure.tpl` oraz `views/templates/admin/_partials/*.tpl` - zakładki.
- `views/js/admin.js`, `admin-help.js`, `history-charts.js`, `translations-tool.js`, `entity-fields.js`, `chart.min.js`.
- `views/css/admin.css`.
- `translations/{iso}.php` - napisy zaplecza.

### 6.3. Kontrolery

`AdminMyaitranslationsgrok` rozszerza `ModuleAdminController`. Rodzicem zakładki jest `AdminInternational` (zapasowo `IMPROVE`). Parametr zapytania to `myaitgk_tab` i przyjmuje wartości: `dashboard`, `manual`, `bulk`, `jobs`, `review`, `catalog`, `glossary`, `excludes`, `logs`, `settings`, `updates`. Nieznana wartość przekierowuje na `dashboard`.

Widoczne akcje to przyciski wysyłające formularz, opisane w rozdziale 3. Dodatkowe adresy używane przez skrypty strony: `ajax=1&action=HistoryDetail` dla **Wyświetl**, odpytywanie statusu zadania dla **Przetwarzaj automatycznie** oraz akcje tłumaczenia pól z `translations-tool.js` i `entity-fields.js`.

`MyaitranslationsgrokCronModuleFrontController` (`controllers/front/cron.php`) odczytuje parametr `token`. Brak tokenu albo zły token zwraca HTTP 403 i `{"ok":false,"error":"Forbidden"}`. Zgodny token bez `id_job` przetwarza jedną partię pierwszego zadania w stanie `pending` lub `running`. Z `id_job` przetwarzane jest wskazane zadanie. Gdy nic nie czeka, odpowiedź to `{"ok":true,"message":"No pending jobs"}`.

`job_action` na zakładce zadań przyjmuje `process`, `pause`, `resume`, `cancel`, `retry_failed`, `rollback` i `export_errors`. Szablon rysuje wszystkie poza `cancel`.

### 6.4. Hooki

Rejestrowane w `install()`:

- `displayBackOfficeHeader` - poprawia techniczną nazwę zakładki i ładuje assety zaplecza.
- `actionAdminControllerSetMedia` - ładuje te same assety.

Na `AdminMyaitranslationsgrok` moduł dodaje `views/css/admin.css`, `views/js/admin.js` i `views/js/admin-help.js`. Pulpit dodatkowo ładuje `chart.min.js` i `history-charts.js`. Na **Międzynarodowe → Tłumaczenia** dołączany jest `translations-tool.js`, gdy przełączniki tej strony są włączone. Na pozostałych formularzach zaplecza dołączany jest `entity-fields.js`, gdy włączone są przełączniki formularzy sklepu. Oba skrypty dostają z PHP obiekt JavaScript `myaitgkTr`.

Moduł nie rejestruje hooka frontu i nie udostępnia własnego hooka.

### 6.5. Nadpisania

Moduł nie nadpisuje żadnej klasy ani kontrolera PrestaShop.

### 6.6. Baza

Odinstalowanie uruchamia `sql/uninstall.php` i usuwa każdą tabelę z poniższej listy. Instalacja używa `CREATE TABLE IF NOT EXISTS`, więc tabela, która z jakiegoś powodu została, zostaje na miejscu.

| Tabela | Zawartość |
|---|---|
| `myaitgk_glossary` | `source_term`, `target_locale`, `target_term`, `do_not_translate`, `id_shop`. |
| `myaitgk_exclude_pattern` | `pattern`, `pattern_type` (`exact`, `prefix`, `contains`, `regex`), `enabled`. |
| `myaitgk_job` | Jedno zadanie masowe: lokalizacje, `scope_json`, `policy_json`, `dry_run`, liczniki, koszt, status i pracownik. |
| `myaitgk_job_item` | Jeden ciąg w zadaniu: domena, klucz, szablon, lokalizacje, źródło, poprzedni tekst, nowy tekst, status i ostrzeżenia. |
| `myaitgk_memory` | Ponownie użyte tłumaczenie, identyfikowane przez `memory_hash`, model i `hit_count`. |
| `myaitgk_usage_ledger` | Dzienne wiersze tokenów i kosztu, z których liczy się **Budżet USD / miesiąc**. |
| `myaitgk_snapshot` | Tekst sprzed zapisu zadania, używany przez **Wycofaj**. |
| `myaitgk_api_log` | Krótki kontekst błędu. Klucz API jest usuwany przed zapisem. |
| `myaitgk_request` | Wiersze **Historia**: prompt, odpowiedź, tokeny, model, status i czas. Repozytorium tworzy tabelę ponownie, gdy jej brakuje. |
| `myaitgk_review` | Wiersze kolejki ze statusem `needs_review`, `approved` albo `rejected`, a także `quality_score` i `flags_json`. |
| `myaitgk_catalog_item` | Wiersze partii katalogu: obiekt, pole, języki, źródło, poprzedni tekst, nowy tekst i status. |

`var/rate_limit.json` to plik, a nie tabela. Odinstalowanie nie usuwa `mypresta_updates`, `update_myaitranslationsgrok` ani `updatev_myaitranslationsgrok`.

### 6.7. Klucze i tłumaczenia

Prefiks kluczy to `MYAITGK_`. `installDefaults()` zapisuje klucz tylko wtedy, gdy go jeszcze nie ma. Wartości domyślne, gdy klucza brakuje:

| Klucz | Wartość domyślna |
|---|---|
| `API_KEY_ENC` | puste |
| `MODEL` | `grok-4.7` |
| `EXTRA_MODELS` | puste |
| `PROVIDER` | `grok` |
| `TONE` | `formal` |
| `CUSTOM_VOICE` | puste |
| `BATCH_SIZE` | `25` (zapis w przedziale 1–100) |
| `MONTHLY_BUDGET` | `0` |
| `SOURCE_LOCALE` | puste |
| `TEMPERATURE` | `0.2` (zapis w przedziale 0–1) |
| `DRY_RUN_SAMPLE` | `10` (zapis w przedziale 1–50) |
| `RATE_LIMIT_PER_MIN` | `60` |
| `LOG_RETENTION_DAYS` | `30` (zapis co najmniej 1) |
| `NOTIFY_EMAIL_ON_COMPLETE` | `0` |
| `NOTIFY_EMAIL` | puste |
| `PERM_ALLOW_PUBLISH` | `1` |
| `ENTITY_FIELD_BUTTONS` | `1` |
| `ENTITY_BULK` | `1` |
| `TR_FIELD_BUTTONS` | `1` |
| `TR_BULK` | `1` |
| `MAX_TOKENS` | `0` (przy 0 pomijane w treści żądania; przy wartości większej od 0 wysyłane jako `max_tokens`) |
| `CRON_TOKEN` | 32 znaki szesnastkowe, tworzone ponownie, gdy wartość jest pusta |

Zapis **Ustawienia** wymusza `PROVIDER` na `grok` i kasuje klucze `MYAITGK_DEEPL_API_KEY` oraz `MYAITGK_CLAUDE_API_KEY`, jeśli istnieją po wcześniejszych wersjach. Puste pole klucza API nie czyści `API_KEY_ENC`.

Wbudowane identyfikatory modeli to `grok-4.7`, `grok-4.6`, `grok-4.5`, `grok-4.3`, `grok-4.20-0309-non-reasoning` i `grok-4.20-0309-reasoning`. Brakujący przełącznik jest traktowany jako włączony, więc sklepy zainstalowane przed wprowadzeniem tych przełączników zachowują ikony.

Opisy pól buduje `MyaitgkForms::help()` w sekcjach **Co to robi:**, **Jak skonfigurować:** i **Efekt:**. Panele pomocy to `MyaitgkSectionHelp`. Napisy zaplecza przechodzą przez `$this->l()`. Nowy język dodaje się przez skopiowanie `translations/en.php` do `translations/{iso}.php`. Kilka komunikatów jest zapisanych po angielsku w PHP i tak się właśnie pokazują: `No Grok API key.`, `Monthly API budget has been exhausted.`, `Grok rate limit (429). Try again later.`, `Rate limit — job auto-paused. Resume later.` oraz komunikaty JSON crona.

### 6.8. Rozszerzanie

Motyw sklepu nie ma szablonu do nadpisania. Moduł nie renderuje żadnego pliku Smarty po stronie frontu. Znaczniki zaplecza są w `views/templates/admin/`. Przyciski pól wstrzykują `views/js/translations-tool.js` i `views/js/entity-fields.js`. Nie ma hooka frontu, do którego dałoby się podpiąć własny kod.

## 7. Pomoc

Strona modułu: [AI Translations with Grok](https://mypresta.eu/ai-artificial-intelligence/ai-translations-with-grok.html).

Żeby napisać w sprawie tego modułu, zaloguj się na konto klienta na mypresta.eu, otwórz formularz kontaktowy i wybierz temat **Support for paid modules**. Formularz wymaga logowania dla płatnych modułów. Po zalogowaniu wybierz ten moduł z historii zakupów.
