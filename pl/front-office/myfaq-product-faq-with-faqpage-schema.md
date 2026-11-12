---
title: MyFAQ - dokumentacja i instrukcja użytkownika
sidebar:
  label: MyFAQ - dokumentacja i instrukcja użytkownika
description: Instrukcja konfiguracji i rozwiązywania problemów dla sklepów, które mają już MyFAQ.
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł MyFAQ: product FAQ with FAQPage schema na MyPresta.eu](https://mypresta.eu/modules/front-office-features/myfaq-product-faq-with-faqpage-schema.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/myfaq-product-faq-with-faqpage-schema/)
>
> ---


## 1. Wymagania

Ten moduł FAQ PrestaShop działa wewnątrz PrestaShop. Nie potrzebuje innego modułu.

- PrestaShop od 1.7.0.0 do PrestaShop 9. FAQ PrestaShop 8 i FAQ PrestaShop 9 to ten sam pakiet i te same ekrany.
- PHP 7.0 albo nowszy i co najmniej taka wersja PHP, jakiej wymaga ta wersja PrestaShop. Instalacja i adres harmonogramu korzystają z `random_bytes`.
- cURL jest potrzebny przy generowaniu pytań. Bez cURL generowanie staje, a wiersz postępu pokazuje `curl_missing`. Sprawdzenie aktualizacji używa cURL, gdy PHP go ma, a gdy go nie ma i serwer pozwala czytać zdalne adresy, czyta adres bezpośrednio.
- OpenSSL szyfruje zapisany klucz AI. Bez OpenSSL klucz zostaje zapisany tak, jak go wkleisz.
- Żaden inny moduł nie jest wymagany. Strona produktu w motywie musi drukować stopkę produktu albo dodatkowe zakładki produktu, inaczej klient nie zobaczy akordeonu.
- Konto w OpenAI, Anthropic, Google, DeepSeek albo Mistral jest potrzebne tylko dla tego dostawcy. Kafelek zgodny może wskazywać własny serwer, na przykład Ollama, vLLM albo LM Studio, i ten serwer może działać bez zewnętrznego konta.
- Zewnętrzny system jest potrzebny tylko wtedy, gdy wołasz adres FAQ spoza sklepu. Harmonogram jest potrzebny tylko wtedy, gdy serwer ma dokończyć kolejkę przy zamkniętym zapleczu.

Duży katalog jest zapisywany po jednym języku. Zostaw stronę generowania zbiorczego otwartą, aż pasek dojdzie do 100%, albo wstaw adres z **Generowanie zbiorcze** do harmonogramu. Jedno wywołanie pracuje około 20 sekund i kończy, żeby nie uderzyć w limit czasu PHP. Jedno wywołanie zapisuje najwyżej 30 języków.

## 2. Instalacja

1. W zapleczu otwórz **Moduły**, potem **Menedżer modułów**.
2. Wgraj zip modułu i kliknij **Instaluj**.
3. Otwórz **Konfiguruj** przy **MyFAQ**. Strona otwiera się na **Wyświetlanie**. Na pasku są też **Wpisy**, **AI**, **Generowanie zbiorcze**, **API** i **Aktualizacje**.
4. MyFAQ nie dodaje własnej pozycji do lewego menu. Katalog, lista kluczy i historia żądań to ukryte strony. Pierwsze otwarcie **Konfiguruj** je tworzy i daje bieżącemu profilowi pracownika prawo je otworzyć.
5. Instalacja nie czyści cache osobnym krokiem. Gdy po aktualizacji strona produktu nadal pokazuje poprzedni układ, wyczyść cache w **Zaawansowane**, **Wydajność**.

Przy produkcie otwórz produkt i blok **MyFAQ**. Stąd wiesz, jak dodać FAQ do produktu PrestaShop: ustawiasz umieszczenie dla jednego produktu i piszesz pytania, które należą tylko do niego.

Wyłączenie robisz przełącznikiem w **Menedżerze modułów**. Strona produktu przestaje drukować akordeon, a edycja produktu przestaje pokazywać blok MyFAQ. Pytania, klucze i ustawienia zostają. Włącz moduł ponownie, a będą użyte tak jak przedtem. Moduł nie ma własnego osobnego przycisku włączania i wyłączania.

Usunięcie: kliknij **Odinstaluj** i potwierdź. Odinstalowanie zabiera ukryte strony, pytania i odpowiedzi, powiązania, umieszczenie przy produkcie, klucze API, historię żądań, kolejkę generowania oraz ustawienia wyświetlania i AI. Dwa adresy harmonogramu przestają działać, bo znika sekret, który w nich siedzi. Pliki modułu zostają na serwerze, dopóki nie usuniesz modułu z listy. Ponowna instalacja startuje z pustymi wpisami i ustawieniami świeżej instalacji. Stare pytania nie wracają. Przełącznik sprawdzania aktualizacji nie jest przy tym czyszczony.

## 3. Konfiguracja i praca w zapleczu

Piszesz pytanie i odpowiedź, potem wiążesz wpis z produktem albo z czymś, co produkt już ma: kategorią, wartością cechy, wartością atrybutu, tagiem, marką albo dostawcą. Wystarczy jedno trafienie. FAQ na karcie produktu to akordeon, który sklep drukuje po zebraniu każdego aktywnego trafienia w języku klienta i po podmianie tokenów. Wpisy powiązane wprost z produktem idą pierwsze. Dalej obowiązuje pozycja, którą ustawisz.

FAQ w stopce produktu stoi pod produktem. Ta zakładka FAQ produktu to ten sam akordeon w zakładce. Przy jednym produkcie możesz wymusić stopkę, wymusić zakładkę albo ukryć MyFAQ. **Ukryj** zabiera też blok FAQ czytany przez wyszukiwarki. Klient tylko otwiera pytania. Nie ma formularza, w którym klient wysyła nowe pytanie. Ścieżka kończy się, gdy strona produktu pokazuje akordeon, albo gdy umieszczenie to **Ukryj** lub żaden aktywny wpis nie pasuje. Wtedy ten produkt nie pokazuje bloku MyFAQ.

Pisanie modelem jest opcjonalne. Dostawcę i klucz zapisujesz na **AI**. Sam zapis nic nie generuje. **Generuj** przy jednym produkcie albo **Start generowania** na **Generowanie zbiorcze** ustawia pracę w kolejce. Każdy język produktu to jedno żądanie. **Dołącz** zostawia obecne wpisy AI i dokłada nowe. **Zastąp odblokowane wpisy AI powiązane tylko z produktem** kasuje odblokowane wpisy AI powiązane tylko z tym produktem, potem zapisuje nowe. Wpis, który edytowałeś, jest zablokowany i zostaje. Wpis powiązany też z kategorią albo innym celem zostaje. Adres harmonogramu nie czyta filtrów z **Generowanie zbiorcze**. Kończy kolejkę, która już istnieje, albo drugim adresem dokłada każdy aktywny produkt tego sklepu, który nie ma jeszcze wpisu AI.

Zewnętrzny system jest opcjonalny. Na **API** generujesz klucz, kopiujesz adres bazowy i wklejasz oba do tego systemu.

Otwórz **Moduły**, **Menedżer modułów**, **MyFAQ**, **Konfiguruj**. Linia pod paskiem opisuje otwartą sekcję.

### 3.1 Wyświetlanie

**Wyświetlanie** to prezentacja dla całego sklepu. Pojedynczy produkt może mieć inne umieszczenie.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Umieszczenie** | Stopka produktu | Domyślne ustawienie sklepu dla każdego produktu, który nie ma własnego umieszczenia. **Stopka produktu** drukuje akordeon pod produktem. **Zakładka produktu** dodaje zakładkę na stronie produktu. Przy produkcie nadal możesz wymusić stopkę, zakładkę albo ukryć MyFAQ. Inne moduły na tym samym haku zostają tam, gdzie ustawia je **Wygląd**, **Pozycje**. |
| **Tytuł zakładki** | FAQ w każdym języku | Etykieta zakładki produktu. Używana tylko wtedy, gdy umieszczenie to **Zakładka produktu**. Wypełnij ją w każdym języku, w którym sklep sprzedaje. Pusty język pokazuje FAQ. |
| **Nagłówek nad listą** | FAQ w każdym języku | Nagłówek drukowany nad pytaniami, w stopce i w zakładce. Wypełnij go per język. Klienci widzą ten tekst. Zostaw FAQ, gdy nie potrzebujesz własnego nagłówka. |
| **Uwzględnij kategorie nadrzędne** | Nie | **Tak** pokazuje też wpis powiązany z rodzicem kategorii produktu, więc jedno powiązanie obejmuje kategorie potomne. Spacer kończy się przed Stroną główną, więc powiązanie ze Stroną główną nie obejmuje całego katalogu. **Nie** trafia tylko w kategorie, w których produkt jest bezpośrednio. |
| **Otwórz pierwsze pytanie** | Nie | **Tak** rozwija pierwszą odpowiedź przy wczytaniu strony. **Nie** zostawia każdą odpowiedź zamkniętą, aż klient kliknie. Klienci bez JavaScript zawsze widzą odpowiedzi. |
| **Znacznik schema FAQ** | Tak | **Tak** dodaje jeden blok schema.org FAQPage zbudowany z pytań naprawdę pokazanych na tym produkcie, po podmianie shortkodów. Wyszukiwarki mogą użyć go do wyników FAQ. **Nie** drukuje FAQ bez tego bloku. Pusta lista i ukryty produkt nigdy go nie wypisują. |

Kliknij **Zapisz**. Strona pokazuje **Zapisano.**

### 3.2 Wpisy

**Wpisy** to podgląd pytań. Linia pod paskiem mówi, że to 10 wpisów zaktualizowanych najpóźniej oraz że **Nowy wpis** i **Edytuj** otwierają katalog.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Nowy wpis** | przycisk | Otwiera formularz katalogu dla nowego pytania. |
| **Pokaż pełną listę** | przycisk | Otwiera katalog z wyszukiwaniem, gdzie zmieniasz kolejność i usuwasz wpis. |
| **Pytanie** | puste, aż zapiszesz | Pytanie w bieżącym języku zaplecza. **Brak pytania w tym języku** znaczy, że ten język nie ma tekstu pytania. |
| **Powiązane** | puste | Do czterech powiązań, potem wielokropek. |
| **Źródło** | Napisane ręcznie przy wpisie, który wpisałeś | **AI** albo **Napisane ręcznie**. **zablokowane** znaczy, że późniejsze zastąpienie zostawia ten wpis. |
| **Status** | Aktywny przy nowym wpisie | **Aktywny** widać na pasujących stronach produktu. **Nieaktywny** zostaje w zapleczu i znika ze sklepu. |

Licznik po prawej to liczba wpisów, nie tylko dziesięciu z podglądu. **Edytuj** otwiera ten wpis w katalogu.

Gdy wpisów nie ma, strona mówi **Brak wpisów** i że sklep nic nie pokazuje, dopóki aktywny wpis nie jest powiązany z produktem, kategorią, cechą, atrybutem, tagiem, marką albo dostawcą.

### 3.3 Katalog

Otwórz **Pokaż pełną listę**. Tytuł strony to **Wpisy FAQ**. Notka u góry mówi, że wyszukiwanie trafia w pytanie, nazwę lub id produktu, język i pozostałe powiązania. Pytanie jest tym z bieżącego języka zaplecza. Nazwa produktu otwiera ten produkt. **Edytuj** otwiera formularz na tej stronie. **Góra** i **Dół** przesuwają wpis. Przeciągnij kolumnę pozycji, żeby ustawić tę samą kolejność. **Usuń** pyta o potwierdzenie. **Aktywny** pokazuje albo ukrywa wpis. Zablokowane wpisy zostają, gdy AI zastępuje produkt.

Kolumny: **ID**, **Pytanie**, **Produkt**, **Również powiązane z**, **Języki**, **Sklep**, **Źródło**, **Aktywny**, **Zablokowany**, **Pozycja**, **Utworzono**, **Zaktualizowano**.

**Sklep** pokazuje **Wszystkie sklepy**, gdy wpis zapisano przy kontekście wszystkich sklepów. W przeciwnym razie pokazuje nazwę tego sklepu. Witryna sklepu pokazuje wpisy dla wszystkich sklepów i wpisy zapisane dla tego sklepu.

**Źródło** to **Napisane ręcznie** albo **AI**. Tę kolumnę filtrujesz listą. **Aktywny** to przełącznik w wierszu: kliknij, żeby pokazać albo ukryć wpis. **Zablokowany** to znacznik, nie przełącznik. Edycja istniejącego wpisu go blokuje. Nowy wpis nie jest zablokowany.

Akcje wiersza to **Edytuj**, **Góra**, **Dół** i **Usuń**. **Usuń** pyta **Usunąć ten wpis? Zniknie we wszystkich produktach, które go używały.** **Akcje grupowe** mają **Usuń zaznaczone**, które pyta **Usunąć zaznaczone wpisy? Znikną we wszystkich produktach, które ich używały.** Gdy usunięcie się nie uda, strona pokazuje **Nie udało się usunąć wpisu.**

**Nowy wpis** na pasku narzędzi otwiera pusty formularz. **Powrót do modułu** wraca do **Wpisy**.

Tytuł formularza to **Nowy wpis** albo **Edytuj wpis**.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Pytanie** | puste | Linia, którą klient klika, żeby otworzyć odpowiedź. To nagłówek akordeonu. Napisz jedno pytanie na język. Pomoc pod polem mówi, że język domyślny jest wymagany. Pytanie też może zawierać shortkody. Na stronie produktu są podmieniane i pokazane jako zwykły tekst. Gdy każdy język jest pusty, **Zapisz** pokazuje **Wpisz pytanie w co najmniej jednym języku.** |
| **Odpowiedź** | pusta | Tekst odkrywany, gdy klient otwiera pytanie. Użyj edytora do akapitów i list. Shortkody są podmieniane na stronie produktu, a otaczający HTML zostaje. Lista shortkodów siedzi pod tym polem: kliknij token, żeby wstawić go przy kursorze. Wypełnij każdy język, w którym sprzedajesz. Pusty język nie jest pokazywany w tym języku. |
| **Shortkody** | przyciski tokenów | Kliknij token, żeby wstawić go tam, gdzie jest kursor, w pytaniu albo w odpowiedzi. Sklep podmienia go na stronie produktu danymi tego produktu, w języku i walucie klienta. Zapisany tekst trzyma token, więc zmiana ceny albo nazwy aktualizuje każdy wpis, który go używa. W pytaniu wynik jest zwykłym tekstem. |
| **Aktywny** | Tak | **Tak** pokazuje wpis na pasujących stronach produktu i włącza go do schema. **Nie** zostawia go w zapleczu i ukrywa w sklepie. |
| **Produkty** | brak | Wpisz nazwę produktu w wyszukiwarce i wybierz go. Wpis widać na tych produktach nawet wtedy, gdy żadne inne powiązanie nie pasuje. Wystarczy jedno trafienie. Zapis zastępuje poprzednie powiązania tego wpisu. |
| **Kategorie** | brak | Wpisz nazwę kategorii i wybierz ją. Wpis widać na produktach leżących w tych kategoriach. Jedno powiązanie to FAQ dla całej kategorii. Kategorie nadrzędne liczą się tylko wtedy, gdy ta opcja jest włączona w **Wyświetlanie**. |
| **Wartości cech** | brak | Wpisz wartość cechy i wybierz ją, na przykład Bawełna. Wpis widać, gdy produkt ma tę wartość. |
| **Wartości atrybutów** | brak | Wpisz wartość atrybutu i wybierz ją, na przykład M. Wpis widać, gdy dowolna kombinacja produktu używa tej wartości. |
| **Tagi** | brak | Wpisz tag i wybierz go. Wpis widać, gdy produkt ma ten tag w języku strony. |
| **Marki** | brak | Wpisz nazwę marki i wybierz ją. Wpis widać na produktach tych marek. |
| **Dostawcy** | brak | Wpisz nazwę dostawcy i wybierz go. Wpis widać na produktach tych dostawców, łącznie z dostawcą domyślnym i dostawcami dodanymi przy kombinacjach. |

**Zapisz** bez powiązania pokazuje **Powiąż wpis z co najmniej jednym produktem, kategorią, cechą, atrybutem, tagiem, marką lub dostawcą.** Gdy wiersza nie da się zapisać, strona pokazuje **Nie udało się zapisać wpisu.** Udany zapis zostaje na formularzu, a PrestaShop potwierdza aktualizację. **Powrót do listy** wraca do katalogu.

Podpowiedź na przycisku tokenu jest po angielsku. Klient dostaje to:

| Token | Co widzi klient |
|---|---|
| `[product_name]` | Nazwa produktu |
| `[product_reference]` | Indeks |
| `[product_ean13]` | EAN-13 |
| `[product_isbn]` | ISBN |
| `[product_upc]` | UPC |
| `[product_mpn]` | MPN |
| `[product_condition]` | Stan |
| `[product_price]` | Cena brutto w walucie klienta |
| `[product_price_tax_excl]` | Cena netto |
| `[product_price_before_discount]` | Cena przed obniżką |
| `[product_discount_amount]` | Kwota obniżki, pusta gdy obniżki nie ma |
| `[product_discount_percent]` | Procent obniżki, pusty gdy obniżki nie ma |
| `[product_quantity]` | Dostępna ilość kombinacji domyślnej |
| `[product_availability]` | Etykieta dostępności, albo etykieta braku, gdy ilość jest zero |
| `[product_minimal_quantity]` | Ilość minimalna |
| `[product_manufacturer]` | Marka |
| `[product_supplier]` | Dostawca |
| `[product_category]` | Kategoria domyślna |
| `[product_categories]` | Wszystkie kategorie |
| `[product_features]` | Lista cech, nazwa i wartość |
| `[product_feature id=ID]` | Jedna wartość cechy. ID zamień na numer cechy z **Katalog**, **Cechy i atrybuty**. |
| `[product_tags]` | Tagi w bieżącym języku |
| `[product_url]` | Adres produktu |
| `[product_weight]` | Waga z jednostką sklepu |
| `[product_description_short]` | Krótki opis jako zwykły tekst |
| `[shop_name]` | Nazwa sklepu |
| `[shop_url]` | Adres sklepu |

Linia pod przyciskami mówi: **Kliknij shortkod, aby wstawić go w miejscu kursora. Ceny i nazwy są zastępowane na stronie produktu, w walucie i języku klienta.** Token `[product_price]` to shortcode ceny w FAQ. To, co klient czyta, to aktualna cena w odpowiedzi FAQ, w jego walucie.

### 3.4 AI

**AI** trzyma połączenie. Na tej karcie ustawiasz generator FAQ AI PrestaShop. Linia pod paskiem mówi, że zapis tutaj nic nie generuje. Do wielu produktów użyj **Generowanie zbiorcze**, a do jednego produktu sekcji **Faq** przy produkcie.

Kliknij kafelek. Używany kafelek pokazuje **Aktywny**. Kafelek pokazuje **Klucz zapisany**, **Brak klucza** albo **Klucz opcjonalny** na kafelku zgodnym.

| Kafelek | Dokąd woła |
|---|---|
| **OpenAI** | Modele GPT w oficjalnym API OpenAI. Lista zaczyna się od `gpt-4o-mini`, `gpt-4o`, `gpt-4.1-mini`, `gpt-4.1`. |
| **Anthropic Claude** | Modele Claude w oficjalnym API Anthropic. Lista zaczyna się od `claude-sonnet-4-5`, `claude-3-5-haiku-latest`, `claude-3-5-sonnet-latest`. |
| **Google Gemini** | Modele Gemini w oficjalnym API Google. Lista zaczyna się od `gemini-2.0-flash`, `gemini-1.5-pro`, `gemini-1.5-flash`. |
| **DeepSeek** | Modele DeepSeek przez API zgodne z OpenAI. Lista zaczyna się od `deepseek-chat`. |
| **Mistral AI** | Modele Mistral w oficjalnym API. Lista zaczyna się od `mistral-small-latest`, `mistral-large-latest`. |
| **OpenAI-compatible / Ollama** | Własny serwer: Ollama, vLLM, LM Studio. Może działać w pełni lokalnie. Lista jest pusta, aż dodasz identyfikator modelu. |

| Pole | Na starcie | Co robi |
|---|---|---|
| **Dostawca** | OpenAI | Kliknij kafelek, żeby wybrać usługę, która pisze pytania. Lista modeli przełącza się od razu. **Zapisz** zapisuje dostawcę, klucz i model. Oficjalni dostawcy wołają własny host. Adres bazowy widać tylko przy kafelku zgodnym. |
| **Klucz API** | pusty | Sekret z konta dostawcy wybranego kafelka. Wklej nowy klucz, żeby zastąpić zapisany. Zostaw pole puste i zapisz, żeby zatrzymać klucz już zapisany dla tego dostawcy. Klucz jest szyfrowany, gdy serwer ma OpenSSL. Każdy kafelek pokazuje, czy klucz jest zapisany. Zgodny serwer lokalny, na przykład Ollama, może zostać pusty. |
| **Usuń zapisany klucz** | Nie | **Tak** kasuje zapisany klucz wybranego dostawcy przy zapisie. Użyj tego przy rotacji albo cofnięciu klucza. **Nie** zostawia zapisany klucz. Generowanie bez klucza pada u oficjalnych dostawców. |
| **Bazowy adres URL zgodny** | pusty | Używany tylko wtedy, gdy wybrany jest kafelek zgodny. Wpisz korzeń API kończący się na `/v1`, na przykład `http://localhost:11434/v1` dla Ollama. Oficjalni dostawcy ignorują to pole. Zostaw je puste, a uruchomienie nie startuje: strona pokazuje **Przed uruchomieniem ustaw zgodny bazowy adres URL na karcie AI.** |
| **Model** | `gpt-4o-mini` dla OpenAI | Identyfikator modelu wysyłany przy każdym generowaniu dla wybranego dostawcy. Lista zawiera identyfikatory wbudowane i te, które dodałeś w polu pod formularzem. Zły identyfikator zostaje odrzucony przez dostawcę, a dany język w kolejce oznaczony jako nieudany. Kafelek zgodny pokazuje **Brak modelu. Dodaj go poniżej.**, aż go dodasz. |
| **Temperatura** | 0.4 | Jak swobodnie model pisze, od 0 do 2. 0.4 trzyma odpowiedzi blisko danych produktu. Wyższa wartość zmienia sformułowania i może odejść od faktów. Wartości spoza 0–2 są ściągane do tego zakresu. Część dostawców odrzuca to ustawienie. Moduł próbuje wtedy jeszcze raz bez niego. |
| **Maks. tokenów** | 2000 | Górna granica długości jednej odpowiedzi. 2000 wystarcza na kilka krótkich odpowiedzi. Podnieś, gdy odpowiedzi są ucinane. Dostawca może skończyć wcześniej. Bardzo wysokie wartości kosztują więcej i mogą uderzyć w limit dostawcy. Zapisana wartość zostaje między 200 a 8000. |
| **Pytań na produkt** | 5 | Ile par pytanie–odpowiedź prosić dla każdego produktu i każdego języka. Ta liczba jest domyślna na **Generowanie zbiorcze** i na stronie produktu. 5 to praktyczny start. Późniejsze uruchomienie może użyć innej liczby. Zapisana wartość zostaje między 1 a 20. |
| **Dodatkowe instrukcje** | puste | Opcjonalne zasady dodawane do każdego polecenia: ton, długość albo tematy do pominięcia. Moduł i tak mówi modelowi, aby pisał `[product_name]` i `[product_price]` zamiast stałej nazwy lub ceny, dzięki czemu późniejsza zmiana ceny pozostaje poprawna. Zostaw puste, aby używać tylko wbudowanych instrukcji. |

Kliknij **Zapisz**. Strona pokazuje **Zapisano.**

**Modele dodane przez Ciebie** stoi pod formularzem. To osobne pole dla identyfikatorów spoza listy wbudowanej. Zmieniać nazwę albo usuwać można tylko je. Modele wbudowane zostają na liście **Model** i nie mają przycisku usuwania.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Nowy identyfikator modelu** | pusty | Dodaje identyfikator do kafelka dostawcy wybranego powyżej i wybiera go do następnego uruchomienia. Tylko litery, cyfry oraz `.` `_` `:` `/` `@` `-`, do 100 znaków. Identyfikator wbudowany zostaje odrzucony. |
| **Dodaj model** | przycisk | Zapisuje ten identyfikator. |
| **Zapisz** przy wierszu, który dodałeś | bieżący identyfikator | Zmienia nazwę. Gdy to był wybrany model, wybór idzie za nowym identyfikatorem. |
| **Usuń** | przycisk przy wierszu, który dodałeś | Pyta **Usunąć ten model?** i usuwa ten identyfikator. Wbudowanego nie da się usunąć. |

Dopóki nic nie dodasz, pole mówi **Nie masz jeszcze własnego modelu dla tego dostawcy. Identyfikatory wbudowane pozostają na liście powyżej.**

Komunikaty, które tu zobaczysz:

- **Wybierz dostawcę przed dodaniem modelu.**
- **Ten identyfikator jest już modelem wbudowanym. Pozostaje na liście i nie można go dodać ponownie.**
- **Ten identyfikator modelu jest nieprawidłowy. Używaj liter, cyfr oraz znaków . _ : / @ -, do 100 znaków.**
- **Modele wbudowane nie mogą być edytowane.**
- **To identyfikator modelu wbudowanego. Wpisz inny identyfikator.**
- **Nie udało się zmienić nazwy tego modelu. Użyj nowego identyfikatora, którego nie ma jeszcze na liście.**
- **Modele wbudowane nie mogą być usuwane.**
- **Ten model nie został dodany przez Ciebie, więc pozostał na miejscu.**

### 3.5 Generowanie zbiorcze

**Generowanie zbiorcze** ustawia w kolejce wiele produktów. Linia pod paskiem mówi, że puste filtry są pomijane, **Start generowania** pisze jeden język na żądanie, a ta strona pokazuje pasek od 0% do 100%. Adres harmonogramu nie czyta tych filtrów.

**Aktywne produkty w tym sklepie** pokazuje liczbę aktywnych produktów przed jakimkolwiek filtrem. To liczba katalogu sklepu, nie stała wartość modułu.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Kategorie** | nic nie zaznaczone | Zaznacz każdą kategorię, którą chcesz włączyć. Kategoria potomna nie wchodzi, dopóki jej też nie zaznaczysz. Zostaw drzewo puste, żeby zignorować kategorie. Produkt w kilku zaznaczonych kategoriach wchodzi do kolejki raz. |
| **Marki** | nic nie wybrane | Przytrzymaj Ctrl albo Cmd i kliknij jedną lub więcej marek. Do kolejki wchodzą tylko produkty tych marek. Zostaw listę nietkniętą, żeby zignorować markę. Razem z kategoriami produkt musi być w zaznaczonej kategorii i w jednej z tych marek. |
| **Dostawcy** | nic nie wybrane | Przytrzymaj Ctrl albo Cmd i kliknij jednego lub więcej dostawców. Produkt pasuje, gdy ten dostawca jest domyślny albo dodatkowy. Zostaw listę nietkniętą, żeby zignorować dostawcę. |
| **Pomiń produkty, które mają już wpis AI** | Nie | **Tak** pomija produkty, które mają już wpis AI powiązany z nimi wprost. Wpisy napisane ręcznie się nie liczą, więc te produkty nadal wchodzą do kolejki. **Nie** kolejkuje pasujące produkty ponownie. |
| **Pomiń produkty, które mają już jakiekolwiek FAQ** | Nie | **Tak** pomija produkty, które mają już dowolny wpis powiązany z nimi wprost, także napisany ręcznie. **Nie** stosuje tylko przełącznik AI powyżej. |
| **Tylko produkty dostępne w magazynie** | Nie | **Tak** zostawia produkty z ilością powyżej zera, także kombinację, która jest na stanie. **Nie** ignoruje stan. |
| **Tylko produkty z obrazem głównym** | Nie | **Tak** pomija produkty bez obrazu głównego w tym sklepie. **Nie** ignoruje obrazy. |
| **Tylko produkty z opisem** | Nie | **Tak** zostawia produkty, których krótki albo pełny opis jest wypełniony w domyślnym języku sklepu. **Nie** ignoruje tekst. |
| **Cena bazowa od** | pusta | Cena katalogowa netto, przed cenami specjalnymi. Zostaw puste, gdy nie ma minimum. Produkt poniżej tej ceny odpada. |
| **Cena bazowa do** | pusta | Cena katalogowa netto, przed cenami specjalnymi. Zostaw puste, gdy nie ma maksimum. Produkt powyżej tej ceny odpada. |
| **Dodane od** | puste | Kolejkuj tylko produkty utworzone tego dnia albo później. Zostaw puste, żeby zignorować datę utworzenia. |
| **Maksymalna liczba produktów** | pusta | Zatrzymaj się po tylu produktach, najpierw najniższe id. 0 albo puste znaczy brak limitu. Użyj małej liczby, żeby sprawdzić filtry przed pełnym przebiegiem. |
| **Języki** | nic nie wybrane | Przytrzymaj Ctrl albo Cmd i kliknij języki do zapisania. Każdy język to jedno żądanie na produkt. Zostaw listę pustą, żeby zapisać każdy aktywny język tego sklepu. Nazwy to języki tego sklepu. |
| **Pytania** | 5, liczba z **AI** | Ile par napisać dla każdego produktu w tym przebiegu. Nadpisuje domyślną wartość z karty **AI** tylko dla tej kolejki. Użyj tej samej liczby w każdym języku produktu. |
| **Istniejące wpisy AI produktu** | Dołącz | **Dołącz** zostawia obecne wpisy AI i dokłada nowe. **Zastąp odblokowane wpisy AI powiązane tylko z produktem** kasuje odblokowane wpisy AI powiązane tylko z tym produktem, raz na produkt, potem pisze nowe. Wpisy edytowane ręcznie są zablokowane i zostają. Wpisy powiązane też z kategorią albo innym celem zostają. |
| **Wyślij do modelu** | patrz karty | Wybierz dane produktu, które model może czytać. Wyłączona karta nie jest wysyłana. Zapis przebiegu zapisuje też te karty na następny raz. |

Karty pod **Wyślij do modelu** mają angielskie tytuły. Zdanie pod tytułem jest podpowiedzią na karcie, w języku zaplecza.

| Karta | Na starcie | Podpowiedź |
|---|---|---|
| **Name and reference** | włączona | Tytuł i referencja produktu. |
| **Short description** | włączona | Podsumowanie pokazywane pod tytułem. |
| **Full description** | włączona | Długi opis z karty produktu. |
| **Price summary** | włączona | Aktualna cena i cena przed rabatem. |
| **Categories** | włączona | Domyślna kategoria i pozostałe kategorie. |
| **Features** | włączona | Nazwy cech i ich wartości. |
| **Brand** | włączona | Nazwa marki. |
| **Attributes and combinations** | wyłączona | Atrybuty każdej kombinacji. |
| **Tags** | wyłączona | Tagi w pisanym języku. |
| **Supplier** | wyłączona | Nazwa domyślnego dostawcy. |
| **Stock and availability** | wyłączona | Ilość i etykieta dostępności. |
| **Weight and dimensions** | wyłączona | Waga, szerokość, wysokość i głębokość. |
| **EAN, ISBN and condition** | wyłączona | EAN, ISBN, UPC, MPN i stan. |
| **Attachment titles** | wyłączona | Tytuły plików załączonych do produktu. |
| **Existing questions (avoid duplicates)** | wyłączona | Już opublikowane pytania, aby model ich nie powtarzał. |

**Uruchom** ma dwie karty.

**Uruchom w tej przeglądarce.** **Start generowania** kolejkuje produkty pasujące do pól powyżej, jeden wiersz na język. Ta strona zostaje otwarta i pokazuje tu status, potem wysyła każdy język do modelu. Zostaw kartę otwartą, aż pasek się skończy. Zamknięcie karty zatrzymuje tę stronę. Kolejka zostaje i adres harmonogramu może ją dokończyć.

Pasek startuje od **Uruchamianie…** i 0%. W trakcie wiersz to liczba zrobionych, ukośnik i suma. Na końcu czyta `Finished.` plus ten licznik. Nieudany język dokłada `failed` i ostatni tekst błędu od dostawcy. Gdy nic nie pasuje, strona pokazuje **Żaden produkt nie pasuje do tego wyboru.** Gdy kolejki nie da się zapisać, pokazuje **Nie udało się utworzyć kolejki.** Gdy przebieg nie może wystartować, wiersz statusu pokazuje **The run did not start.** Odpowiedź, której strona nie odczyta, pokazuje **That request could not be read.** Nieudany krok pokazuje **The generation request failed.** albo tekst błędu od dostawcy. Te zdania postępu zostają w tym brzmieniu.

**Kontynuuj na serwerze.** To nie jest drugi przycisk startu. Nie czyta kategorii, liczby pytań ani dołączania i zastępowania z tego formularza. Wstaw jeden adres do harmonogramu co kilka minut. Każde wywołanie pracuje około 20 sekund i kończy.

Skopiuj **Dokończ istniejącą kolejkę** po **Start generowania**, gdy zamkniesz kartę albo gdy przebieg stanął przed końcem paska. Ten adres pisze tylko wiersze, które już są w kolejce.

Skopiuj **Uzupełnij produkty, które nie mają jeszcze wpisu AI**, gdy nowe produkty mają się uzupełniać bez otwierania tej strony. Ten adres dokłada każdy aktywny produkt tego sklepu bez wpisu AI, z liczbą pytań i wyborem danych zapisanym na **AI**. Zawsze dołącza, potem opróżnia kolejkę.

Oba adresy trzymaj prywatnie. Zawierają sekret, który autoryzuje wywołanie. **Zapisz** na tym formularzu nie uruchamia przebiegu. Robi to **Start generowania**.

Przed przebiegiem strona odmawia startu i pokazuje jeden z tych komunikatów:

- **Przed uruchomieniem wybierz dostawcę na karcie AI.**
- **Przed uruchomieniem wybierz model na karcie AI.**
- **Przed uruchomieniem ustaw zgodny bazowy adres URL na karcie AI.** Wypełnij **Bazowy adres URL zgodny**. Pusty adres nie uruchamia przebiegu.
- **Przed uruchomieniem zapisz klucz API dla wybranego dostawcy na karcie AI.**

### 3.6 API

**API** jest dla systemu poza sklepem. Linia pod paskiem mówi, że generujesz tu klucz, dajesz mu etykietę i kopiujesz adres bazowy. **Pokaż pełną listę** otwiera katalog kluczy. **Historia żądań** wymienia każde wywołanie, z parametrami i odpowiedzią. **Dokumentacja API** wymienia każdą akcję.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Bazowy adres URL** | adres tego sklepu | Adres, który woła zewnętrzny system. Wyślij `action` i `api_key` jako parametry zapytania albo pola POST. Nagłówek `X-Api-Key` też jest przyjmowany. Otwórz **Dokumentacja API**, żeby zobaczyć listę parametrów każdej akcji. Brakujący albo cofnięty klucz jest odrzucany. |
| **Etykieta klucza** | pusta | Nazwa, po której odróżnisz klucze, na przykład ERP albo staging. To nie jest sekret. **Generuj klucz** tworzy nowy sekret i pokazuje go w tabeli. **Cofnij** zatrzymuje klucz i zostawia go na liście. **Usuń** zabiera ten wiersz i sekret. Pozostałe klucze dalej działają. Możesz utworzyć więcej niż jeden klucz. |

**Generuj klucz** dodaje klucz i wraca na tę stronę. Podgląd **Wydane klucze** wymienia pięć najnowszych kluczy. Licznik to pełna liczba kluczy. Sekret na tym podglądzie jest skrócony. **Pokaż pełną listę** pokazuje cały sekret, żeby wkleić go do drugiego systemu.

| Kolumna | Do czego |
|---|---|
| **Etykieta** | Nazwa, którą wpisałeś. |
| **Klucz** | Początek sekretu na tym podglądzie. Cały sekret jest na liście kluczy. |
| **Status** | **Aktywny** albo **Cofnięty**. |
| **Utworzono** | Kiedy klucz powstał. |
| **Ostatnio użyty** | Ostatnie przyjęte wywołanie albo **Jeszcze nieużyty**. |
| **Historia** | Otwiera **Historia żądań** przefiltrowaną do tego klucza. |
| **Cofnij** | Pyta **Cofnąć ten klucz? Przestanie działać natychmiast i pozostanie na tej liście.** Ukryte, gdy klucz jest już cofnięty. |
| **Usuń** | Pyta **Usunąć ten klucz? Wiersz i sekret zostaną usunięte. Dotychczasowe żądania pozostaną w historii.** |

Gdy kluczy nie ma, strona mówi **Brak kluczy**.

**Dokumentacja API** otwiera okno. **Kopiuj** kopiuje adres bazowy i potem pokazuje **OK**. Każda akcja ma **Kopiuj URL** i **Kopiuj cURL**. W przykładzie zamień `YOUR_API_KEY` na sekret z listy kluczy. Okno wymienia też **Parametr**, **Wymagany** i **Opis**. **Zamknij** zamyka okno.

| Akcja | Co wysłać | Co robi |
|---|---|---|
| `list` | `action=list`. Opcjonalnie `id_product`, `resolved=1`, `page`, `id_shop`. | Zwraca wpisy. Z `id_product` tylko wpisy powiązane wprost z tym produktem. Z `resolved=1` zestaw, który pokazałaby strona produktu. Bez produktu `page` idzie po katalogu, 50 wpisów na stronę. |
| `get` | `action=get` i `id`. | Zwraca jeden wpis ze wszystkimi tłumaczeniami i powiązaniami. |
| `create` | `action=create`, plus pytanie i co najmniej jedno powiązanie. Opcjonalnie `id_product`, `id_lang`, `question`, `answer`, `translations`, `assoc`, `active`, `id_shop`. | Tworzy jeden wpis. `id_product` przypina go do tego produktu. `translations` to JSON kluczowany identyfikatorem języka. Shortkody takie jak `[product_name]` są zapisane tak, jak są. `active` domyślnie jest włączone. Brak pytania albo brak powiązania jest odrzucany. |
| `update` | `action=update` i `id`, plus tylko pola, które chcesz zmienić. | Aktualizuje tylko wysłane pola. `replace_assoc=1` zastępuje powiązania. W przeciwnym razie `id_product` i `assoc` są dodawane. To wywołanie nie blokuje wpisu. |
| `activate` | `action=activate` i `id`. | Znowu pokazuje wpis, bez zmiany tekstu. |
| `deactivate` | `action=deactivate` i `id`. | Ukrywa wpis. Zostaje w zapleczu i znika ze strony produktu. |
| `delete` | `action=delete` i `id`. | Kasuje wpis, jego tłumaczenia i powiązania. |

`assoc` to lista JSON obiektów z `type` i `id`. Typ to `product`, `category`, `feature_value`, `attribute`, `tag`, `manufacturer` albo `supplier`. Opcjonalne `id_shop` wybiera sklep. Bez niego używany jest sklep wywołanego adresu. GET wystarcza do krótkiego wywołania. Te same pola wyślij POST, gdy pytanie albo odpowiedź to długi HTML.

**Historia żądań** to lista tylko do odczytu, tytuł **Historia żądań API**. Notka mówi, że każdy wiersz to jedno wywołanie. Szukaj w polach pod tytułami kolumn. **Podgląd** otwiera parametry i odpowiedź. Sekret w zapisanym wywołaniu jest zamaskowany. Wiersze zostają takie, jak je zapisano. Nie da się dodać, edytować ani usunąć wiersza. Przy próbie zapisu strona pokazuje **Historia żądań to zapis wywołań. Otwórz Podgląd, aby przeczytać jeden wiersz.**

Kolumny: **ID**, **Data**, **Akcja**, **HTTP**, **ID klucza**, **Klucz**, **Szczegóły**, **IP**. **Klucze API** na pasku otwiera katalog kluczy. **Powrót do modułu** wraca do **API**. Wejście w historię z modułu czyści poprzedni filtr. **Historia** przy jednym kluczu zostawia filtr tego klucza.

Katalog kluczy ma tytuł **Klucze API**. Notka mówi, że sekret jest na liście, żeby wkleić go do drugiego systemu. **Cofnij** zatrzymuje ten klucz i zostawia wiersz. **Usuń** zabiera wiersz i sekret. Dotychczasowe żądania zostają w **Historia żądań**. **Wygeneruj klucz** wraca na kartę **API**. Na tej liście nie ma przycisku **Nowy**. Kolumny: **ID**, **Etykieta**, **Klucz**, **Status**, **Utworzono**, **Ostatnio użyty**. **Status** czyta **Aktywny** albo **Cofnięty**. **Ostatnio użyty** czyta **Jeszcze nieużyty** do pierwszego przyjętego wywołania. Akcje wiersza to **Cofnij**, **Historia** i **Usuń**. **Cofnij** jest ukryte przy cofniętym kluczu i pyta **Cofnąć ten klucz? Przestanie działać natychmiast i pozostanie na tej liście.** **Usuń** pyta **Usunąć ten klucz? Wiersz i sekret zostaną usunięte. Dotychczasowe żądania pozostaną w historii.** **Akcje grupowe** mają **Cofnij zaznaczone** i **Usuń zaznaczone**, z tym samym skutkiem dla każdego zaznaczonego wiersza. Gdy pracownik nie może edytować, strona pokazuje **Nie masz uprawnień do edycji tego.**

### 3.7 Aktualizacje

**Aktualizacje** sprawdza na MyPresta.eu, czy jest nowsze wydanie. Sprawdzenie tylko podaje wersję. Instalacja paczki zostaje ręcznym pobraniem ze strony modułu. Tytuł formularza to **Aktualizacje MyPresta**.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Sprawdź aktualizacje** | przycisk **Sprawdź teraz** | Ręcznie sprawdza, czy nowsza wersja tego modułu jest na serwerach MyPresta.eu. **Dostępna nowa wersja!** znaczy, że nowsze wydanie jest na liście. **Moduł jest aktualny!** znaczy, że ta instalacja zgadza się z opublikowanym wydaniem. Przycisk nie wgrywa zipa. |
| **Powiadomienia o aktualizacjach** | Włącz | **Włącz** powtarza to sprawdzenie mniej więcej co trzy dni, gdy pracujesz w zapleczu. **Wyłącz** je pomija. **Włącz** i **Wyłącz** to dwa wybory. |
| **Strona modułu** | link o nazwie **MyFAQ** | Bezpośredni link do oficjalnej strony dodatku, gdzie czytasz o zmianach w module. |

Kliknij **Zapisz**. Strona pokazuje **Zapisano ustawienia aktualizacji.**

Gdy nowsze wydanie jest znane, zaplecze może pokazać **Dostępna jest nowa wersja, sprawdź http://MyPresta.eu, aby uzyskać więcej informacji** i link **Więcej szczegółów w changelogu**. Wgraj nowy zip z **Menedżera modułów**.

### 3.8 Jeden produkt

Otwórz **Katalog**, **Produkty**, produkt, potem blok **MyFAQ**. Nagłówek to **FAQ w tym produkcie**. Tekst pod nim mówi: wybierz, gdzie ten produkt pokazuje pytania, przejrzyj to, co dziedziczy z katalogu, i napisz wpisy, które należą tylko tutaj. Gdy żaden wpis nie jest aktywny albo umieszczenie to **Ukryj**, sklep nie renderuje bloku MyFAQ na tym produkcie.

Zakładki to **Wpisy FAQ**, **Pytanie i odpowiedź** oraz **Generuj z AI**.

**Wpisy FAQ** zaczyna się od **Umieszczenie**.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Umieszczenie** | Użyj domyślnego ustawienia sklepu | **Użyj domyślnego ustawienia sklepu** idzie za **Wyświetlanie**. **Stopka produktu** albo **Zakładka produktu** wymusza to miejsce tylko dla tego produktu. **Ukryj** zabiera MyFAQ z tego produktu, łącznie z blokiem schema. Inne moduły na haku nie są przesuwane. Ich kolejność zostaje w **Wygląd**, **Pozycje**. |

**Zapisz** pokazuje **Zapisano.**

**FAQ w tym produkcie** ma dwie listy. Pierwsza jest tylko do odczytu i pochodzi z kategorii, cechy, atrybutu, tagu, marki albo dostawcy. Druga jest zapisana dla tego produktu. Przeciągnij wiersz, żeby zmienić kolejność, przełącznikiem pokaż albo ukryj pytanie, a usuń, żeby je zabrać.

**Z katalogu** wymienia wpisy widoczne dlatego, że inny produkt z tym samym powiązaniem też by je pokazał. Tekst zmieniasz w katalogu modułu. Kolumny to **Pytanie**, **Status** i **Akcje**. **Status** to **Aktywny** albo **Nieaktywny**. **Edytuj w katalogu** otwiera ten wpis. Wpis AI może pokazać **AI** i **zablokowane**. Wpis wpisany ręcznie pokazuje **Napisane ręcznie**. Gdy nic nie pasuje, karta mówi **Nic nie dziedziczy**.

**Tylko ten produkt** wymienia pytania przypięte do tego produktu. Uchwyt (**Przeciągnij, aby zmienić kolejność**) ustawia ich kolejność na stronie produktu. Przełącznik pokazuje **Aktywny** albo **Nieaktywny**. **Edytuj** otwiera **Pytanie i odpowiedź**. **Usuń** pyta **Usunąć ten wpis?** Gdy lista jest pusta, karta mówi **Brak FAQ dla tego produktu** i proponuje **Dodaj wpis**. **Brak pytania w tym języku** znaczy, że bieżący język zaplecza nie ma tekstu pytania. Inny język może go mieć.

**Pytanie i odpowiedź** to **Dodaj wpis** albo **Edytuj wpis**. Notka mówi, że zapis jest tylko dla tego produktu. Powiązania z kategorią, cechą i innymi celami zostają na ekranie **Wpisy**. Pytanie na sklepie jest zwykłym tekstem. Odpowiedź trzyma formatowanie edytora. Shortkody siedzą pod odpowiedzią. Przycisk języka po prawej przełącza pytanie i odpowiedź razem.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Pytanie** | puste | Ta sama rola co w katalogu. Pomoc mówi, że język domyślny jest wymagany. Gdy każdy język jest pusty, blok pokazuje **Wpisz pytanie w co najmniej jednym języku.** |
| **Odpowiedź** | pusta | Ta sama rola co w katalogu. Pusty język nie jest pokazywany w tym języku. |
| **Shortkody** | przyciski tokenów | Te same tokeny co w katalogu. Kliknij, żeby wstawić przy kursorze. |
| **Aktywny** | Tak | **Tak** pokazuje wpis. **Nie** ukrywa go w sklepie. |

**Zapisz** wiąże wpis tylko z tym produktem. Edycja istniejącego wiersza go blokuje, więc późniejsze zastąpienie go zostawia. Nowy wiersz nie jest zablokowany. **Nowy wpis** czyści formularz. **Usuń wpis** zabiera go po **Usunąć ten wpis?** Gdy otworzysz wpis powiązany też z czymś innym, blok pokazuje **Ten wpis nie jest wyłączny dla produktu.** i nie zapisuje na nim zmian. Taki wpis zmieniasz przez **Edytuj w katalogu**.

Gdy zapis nie dojdzie do sklepu, blok pokazuje **The save could not reach the shop. Reload the product and try again.**

**Generuj z AI** pisze pytania dla tego produktu z jego danych katalogowych, w każdym języku sklepu. Przebieg idzie w tle. Pasek postępu pojawia się tu po starcie.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Pytania** | 5, liczba z **AI** | Ile par napisać dla tego produktu, w każdym języku sklepu. Nadpisuje domyślną wartość z karty **AI** tylko dla tego przebiegu. |
| **Istniejące wpisy AI produktu** | Dołącz | **Dołącz** zostawia obecne wpisy AI i dokłada nowe. **Zastąp odblokowane wpisy AI powiązane tylko z produktem** kasuje odblokowane wpisy AI powiązane tylko z tym produktem, potem pisze nowe. Wpisy edytowane ręcznie są zablokowane i zostają. |
| **Wyślij do modelu** | te same karty co przy generowaniu zbiorczym | Te same karty. Wyłączona karta nie jest wysyłana. Ten przebieg zapisuje karty na następny raz. |

**Generuj** startuje przebieg. Te same cztery komunikaty co na **Generowanie zbiorcze** pojawiają się, gdy brakuje dostawcy, modelu, zgodnego adresu albo klucza. Pasek używa tego samego brzmienia: **Uruchamianie…**, potem liczniki, potem `Finished.` Zostaw stronę produktu otwartą, aż pasek się skończy, albo dokończ kolejkę adresem z **Generowanie zbiorcze**.

## 4. Front sklepu

Klient widzi blok tylko na stronie produktu.

Gdy **Umieszczenie** to **Stopka produktu**, akordeon jest pod produktem. Nagłówek to **Nagłówek nad listą** w języku klienta. Każde pytanie jest przyciskiem. Odpowiedź otwiera się pod nim. **Otwórz pierwsze pytanie** ustawione na **Tak** otwiera pierwszą odpowiedź przy wczytaniu. Bez JavaScript każda odpowiedź jest widoczna.

Gdy **Umieszczenie** to **Zakładka produktu**, motyw dodaje zakładkę produktu. Etykieta zakładki to **Tytuł zakładki** w tym języku albo FAQ, gdy ten język jest pusty. Treść zakładki to ten sam akordeon i ten sam nagłówek.

Wpisy powiązane wprost z produktem idą pierwsze. Potem obowiązuje pozycja z katalogu i z **Przeciągnij, aby zmienić kolejność** przy produkcie. Pytanie albo odpowiedź pusta w języku klienta jest pomijana. Po podmianie tokenów pomijane jest też pytanie, które zostało puste, albo odpowiedź, w której nie zostało tekstu. Wpisy nieaktywne są pomijane. **Ukryj** przy tym produkcie nie drukuje niczego, także bloku schema.

**Znacznik schema FAQ** ustawiony na **Tak** to schemat FAQ PrestaShop w źródle strony: jeden blok FAQPage, zbudowany z pytań, które klient może otworzyć, w języku strony i wskazujący adres produktu. Klient nie widzi osobnego pudełka schema. **Nie**, pusta lista albo **Ukryj** nie drukuje takiego bloku.

Klient nie może dodać, edytować ani wysłać pytania. Nie ma strony konta dla tych wpisów.

Gdy motyw nie drukuje stopki produktu i nie drukuje dodatkowych zakładek produktu, klient nic nie widzi, nawet gdy wpisy istnieją. Przenieś **MyFAQ** w **Wygląd**, **Pozycje**, na stopkę produktu albo dodatkową treść produktu. Inne moduły na tym haku zostają w kolejności, którą tam ustawisz.

Na tym samym motywie mogą być dwie pozycje stopki. Akordeon jest drukowany raz.

## 5. Problemy

**Na stronie produktu nie ma akordeonu.** Produkt nie ma aktywnego wpisu w języku klienta, pytanie albo odpowiedź jest pusta po podmianie tokenów, albo **Umieszczenie** tego produktu to **Ukryj**. Otwórz produkt, ustaw **Umieszczenie** na **Użyj domyślnego ustawienia sklepu**, **Stopka produktu** albo **Zakładka produktu** i potwierdź wpis **Aktywny**. Gdy motyw nie ma stopki ani dodatkowych zakładek, przenieś moduł w **Wygląd**, **Pozycje**.

**Wpis powiązany z kategorią nadrzędną się nie pokazuje.** **Uwzględnij kategorie nadrzędne** jest na **Nie** albo powiązanie to Strona główna. Ustaw **Uwzględnij kategorie nadrzędne** na **Tak**. Powiązanie ze Stroną główną nie obejmuje katalogu. Zaznacz rodzica, którego naprawdę chcesz, pod Stroną główną.

**Sklep pokazuje wpis w jednym języku, a w drugim nie.** Ten język ma puste pytanie albo pustą odpowiedź. Edytuj wpis i wypełnij oba. Strona pomija pusty język.

**Zapis pokazuje „Wpisz pytanie w co najmniej jednym języku.”** Wpisz pytanie w co najmniej jednym języku i kliknij **Zapisz** ponownie.

**Zapis pokazuje „Powiąż wpis z co najmniej jednym produktem, kategorią, cechą, atrybutem, tagiem, marką lub dostawcą.”** Wybierz co najmniej jeden wynik w **Produkty**, **Kategorie**, **Wartości cech**, **Wartości atrybutów**, **Tagi**, **Marki** albo **Dostawcy**.

**Blok produktu pokazuje „Ten wpis nie jest wyłączny dla produktu.”** To pytanie jest też powiązane z kategorią albo innym celem. Kliknij **Edytuj w katalogu** i zmień je tam.

**Blok produktu pokazuje „The save could not reach the shop. Reload the product and try again.”** Odśwież produkt i zapisz ponownie.

**Generuj nic nie robi i pokazuje komunikat o karcie AI.** Otwórz **AI**, wybierz kafelek, zapisz model i zapisz klucz u oficjalnego dostawcy. Przy kafelku zgodnym wypełnij **Bazowy adres URL zgodny**, na przykład `http://localhost:11434/v1` dla Ollama. Potem uruchom przebieg ponownie.

**Start generowania pokazuje „Żaden produkt nie pasuje do tego wyboru.”** Wyczyść filtr albo zaznacz kategorię, w której są aktywne produkty. Puste filtry są pomijane, więc to filtr, który ustawiłeś, zabrał produkty.

**Pasek staje przed 100%.** Zostaw kartę otwartą albo skopiuj **Dokończ istniejącą kolejkę** i otwieraj ją z harmonogramu. Zamknięcie karty nie kasuje kolejki. Wiersz z `failed` i komunikatem dostawcy znaczy, że ten język został odrzucony. Przeczytaj komunikat, popraw klucz albo identyfikator modelu i uruchom ponownie. **Dołącz** dokłada kolejny zestaw. **Zastąp odblokowane wpisy AI powiązane tylko z produktem** najpierw zabiera odblokowany zestaw AI.

**Wiersz postępu pokazuje `curl_missing`.** Serwer nie ma cURL. Poproś hosting o włączenie. Generowanie bez tego nie rusza.

**Pojawia się informacja o nowszej wersji.** Tekst to **Dostępna jest nowa wersja, sprawdź http://MyPresta.eu, aby uzyskać więcej informacji**. Otwórz **Aktualizacje** i kliknij **Sprawdź teraz**. Pobierz zip ze strony modułu i wgraj go w **Menedżerze modułów**. **Wyłącz** przy **Powiadomienia o aktualizacjach** zatrzymuje automatyczną informację.

**MyFAQ nie ma w lewym menu.** Tak ma być. Otwórz **Moduły**, **Menedżer modułów**, **MyFAQ**, **Konfiguruj**. Katalog, klucze i historia otwierają się z tej strony. Gdy **Konfiguruj** nie może otworzyć katalogu, otwórz **Konfiguruj** raz jako pracownik, który może instalować moduły. Ta wizyta tworzy ukryte strony i daje bieżącemu profilowi dostęp.

**Klucz jest odrzucany.** Klucz został cofnięty, usunięty albo skopiowany bez pełnego sekretu. Otwórz **Klucze API**, skopiuj pełny **Klucz** wiersza **Aktywny** albo kliknij **Wygeneruj klucz**.

**Nie da się usunąć wiersza w historii żądań.** Strona pokazuje **Historia żądań to zapis wywołań. Otwórz Podgląd, aby przeczytać jeden wiersz.** Użyj **Podgląd**.

**Nie masz uprawnień do edycji tego.** Profil pracownika nie może edytować listy kluczy. Otwórz **Konfiguruj** jako administrator albo nadaj profilowi dostęp do stron modułu.

**Pierwsza odpowiedź jest zamknięta, choć Otwórz pierwsze pytanie jest na Tak.** Klient ma wyłączony JavaScript. Wtedy każda odpowiedź jest widoczna. Z JavaScript otwarta na starcie jest tylko pierwsza pozycja.

**To samo pytanie widać dwa razy.** Jest powiązane dwa razy tylko wtedy, gdy zapisałeś dwa wpisy. Jeden wpis jest pokazywany raz. Sprawdź **Tylko ten produkt** i **Z katalogu**, czy są dwa różne wiersze z tym samym tekstem.

**Zastąpienie zostawiło stare pytanie AI.** Ten wpis jest zablokowany albo jest też powiązany z kategorią albo innym celem. Zablokowanie to znacznik na wierszu. Edytuj go i usuń, gdy ma zniknąć.

## 6. Dla developera

### 6.1 Przegląd

Klasa główna `myfaq` w `myfaq.php`. Wersja `1.3.1`. Napis na liście **MyFAQ**. Autor `mypresta.eu`. Zakładka `front_office_features`. `ps_versions_compliancy` to `1.7.0.0` do `9.99.99`. `need_instance` to 0. `bootstrap` to true. `config.xml` nadal podaje wersję `1.0.0`. Wersja z klasy jest tą, którą sklep uruchamia.

`getContent()` renderuje `MyfaqAdminBo`. Ustawienia wyświetlania to klucze `Configuration`. Wpisy, powiązania, umieszczenie przy produkcie, klucze API, dziennik żądań i kolejka AI to tabele. Witryna czyta trafienia przez `MyfaqMatcher`, podmienia tokeny przez `MyfaqShortcode` i opcjonalnie drukuje `MyfaqSchema`. Wywołania AI idą przez `MyfaqAi` i `MyfaqQueue`. Adres publiczny to kontroler frontu `api`.

Nie ma `enable()` ani `disable()`.

### 6.2 Pliki

- `myfaq.php` — instalacja, odinstalowanie, hooki, wartości startowe, wejścia ajax.
- `config.xml` — metadane paczki. Wersja tam to `1.0.0`.
- `lib/MyfaqAdminBo.php` — formularze zaplecza, teksty `desc`, panel produktu.
- `lib/MyfaqConfig.php` — dostawcy, modele, flagi, szyfrowanie, token crona.
- `lib/MyfaqRepository.php` — tabele i zapis.
- `lib/MyfaqMatcher.php` — które wpisy pokazuje produkt.
- `lib/MyfaqShortcode.php` — katalog tokenów i podmiana.
- `lib/MyfaqSchema.php` — publikuje JSON-LD FAQ na produkcie.
- `lib/MyfaqAi.php` — wywołania HTTP do dostawcy. Wymaga cURL.
- `lib/MyfaqQueue.php` — partia i kolejka.
- `lib/MyfaqApi.php` — publiczne API.
- `lib/MyfaqApiDocumentation.php` — tekst okna.
- `lib/updatesChecker.php` — klasa `myfaqUpdate`.
- `lib/prestashop9compatibility.php` — szablony helpera, cena, listy id.
- `lib/searchTool/searchTool.php` — autouzupełnianie pól powiązań.
- `controllers/admin/AdminMyfaqController.php` — tylko ajax: wyszukiwanie, panel produktu, start partii, krok partii, zmiana kolejności.
- `controllers/admin/AdminMyfaqEntriesController.php` — katalog.
- `controllers/admin/AdminMyfaqKeysController.php` — klucze.
- `controllers/admin/AdminMyfaqLogsController.php` — historia żądań.
- `controllers/front/api.php` — publiczne API JSON.
- `controllers/front/cron.php` — worker kolejki.
- `views/templates/admin/tabs.tpl` — pasek sekcji.
- `views/templates/admin/entries.tpl` — podgląd dziesięciu ostatnich.
- `views/templates/admin/product.tpl` — blok edycji produktu.
- `views/templates/admin/api.tpl` — podgląd kluczy.
- `views/templates/admin/_shortcodes.tpl` — przyciski tokenów.
- `views/templates/admin/_api_documentation_modal.tpl` — okno akcji.
- `views/templates/admin/_api_log_modal.tpl` — jedno zapisane wywołanie.
- `views/templates/hook/product.tpl` — akordeon witryny.
- `views/css/myfaq.css`, `views/js/myfaq.js` — witryna.
- `views/css/myfaq-admin.css`, `views/css/myfaq-controls.css`, `views/js/admin.js` — zaplecze. Kilka zdań postępu w `admin.js` jest na stałe po angielsku.
- `upgrade/upgrade-1.0.0.php` — woła `installDb()`.
- `key.php` — opcjonalny. Gdy jest, sprawdzenie aktualizacji wysyła jego wartość licencji. Gdy go nie ma, sprawdzenie wysyła `nlc`.

### 6.3 Kontrolery

`AdminMyfaq`, `AdminMyfaqEntries`, `AdminMyfaqKeys` i `AdminMyfaqLogs` to zakładki z `id_parent` `-1`. Nie pojawiają się w menu. `ensureSearchTab()` tworzy brakującą zakładkę. `grantHiddenTabAccess()` nadaje podgląd, dodawanie, edycję i usuwanie profilowi superadministratora i bieżącemu profilowi pracownika.

`AdminMyfaq` obsługuje tylko ajax: `SearchTool`, `ProductPanel`, `BulkStart`, `BulkStep`, `Reorder`. Te same akcje są na obiekcie modułu, bo panel produktu i strona partii tam wysyłają.

`AdminMyfaqEntries` to katalog. **Nowy wpis** na pasku to `addmyfaq_item`. Zapis wysyła `submitMyfaqItem` i przekierowuje z `conf=4`. Pozycja używa linków pozycji helpera.

`AdminMyfaqKeys` nie ma formularza dodawania. **Wygeneruj klucz** wraca do `configure=myfaq&mfq_tab=api`. `processRevoke` i cofnięcie grupowe wołają `MyfaqRepository::revokeApiKey`. Usunięcie woła `deleteApiKey`.

`AdminMyfaqLogs` odmawia dodania, aktualizacji i usunięcia komunikatem **Historia żądań to zapis wywołań. Otwórz Podgląd, aby przeczytać jeden wiersz.** `action=View` zwraca zapisane żądanie i odpowiedź jako JSON do okna. `id_api_key` w zapytaniu wypełnia filtr klucza, chyba że lista jest resetowana.

Kontroler frontu `api` (`module/myfaq/api`) woła `MyfaqApi::handle()` i zwraca JSON. Ustawia status HTTP z wyniku. Kontroler frontu `cron` (`module/myfaq/cron`) wymaga `token` równego `MYFAQ_CRON_TOKEN`. Zły token zwraca `403` i `{"error":"forbidden"}`. `fill_missing=1` woła `MyfaqQueue::enqueueMissing` dla bieżącego sklepu, potem akcja opróżnia oczekujące wiersze przez około 20 sekund, najwyżej 30 wierszy. JSON to `ok`, `enqueued_batch`, `processed`, `finished`.

Wyniki API: brakujący albo cofnięty klucz `401` `unauthorized`. Nieznane `action` `400` `unknown_action`. Brak albo nieznane id `400` `missing_id` albo `not_found`. Utworzenie bez pytania `422` `question_required`. Utworzenie bez powiązania `422` `association_required`. Sukces utworzenia `201`. Sukces aktualizacji, aktywacji, dezaktywacji i usunięcia `200`. Nieudany zapis `500`.

`list` z `id_product` i `resolved=1` używa `MyfaqMatcher::forProductAllLangs`. `list` z `id_product` bez `resolved` zwraca wpisy powiązane wprost z tym produktem. `list` bez produktu stronnicuje `MyfaqRepository::listItems` po 50. Aktualizacja używa `lock_on_update` false, więc aktualizacja przez API nie blokuje wiersza.

### 6.4 Hooki

Rejestrowane w `install()`:

| Hook | Rola |
|---|---|
| `displayHeader` | Na kontrolerze produktu dokłada `views/css/myfaq.css` i `views/js/myfaq.js`. |
| `displayFooterProduct` | Renderuje akordeon, gdy rozwiązane umieszczenie to `footer`. |
| `displayProductFooter` | Ten sam render. Flaga statyczna drukuje blok stopki tylko raz na żądanie. |
| `displayProductExtraContent` | Gdy umieszczenie to `tab`, zwraca jeden `ProductExtraContent`. Tytuł to `MYFAQ_TAB_TITLE` bieżącego języka albo źródłowy napis FAQ, gdy ta wartość jest pusta. |
| `displayAdminProductsExtra` | Blok edycji produktu plus CSS i JS. |
| `actionAdminControllerSetMedia` | CSS i JS zaplecza na stronie produktu, przy `configure=myfaq` oraz na kontrolerach wpisów, kluczy i historii. |

Moduł nie rejestruje własnych hooków i nie woła `Hook::exec` dla własnego hooka. `displayProductExtraContent` zwraca pustą tablicę, gdy umieszczenie nie jest `tab`, gdy HTML jest pusty albo gdy nie ma `ProductExtraContent`.

### 6.5 Nadpisania

Moduł nie nadpisuje żadnej klasy PrestaShop ani żadnego kontrolera.

### 6.6 Baza

`MyfaqRepository::installDb()` tworzy tabele z `_MYSQL_ENGINE_` i `utf8mb4`, a przy porażce próbuje `utf8`. `uninstall()` kasuje je w tej kolejności: `myfaq_queue`, `myfaq_batch`, `myfaq_api_log`, `myfaq_api_key`, `myfaq_product_display`, `myfaq_assoc`, `myfaq_item_lang`, `myfaq_item`. Odinstalowanie kasuje tabele. Ponowna instalacja nie przywraca wierszy.

| Tabela | Zawartość |
|---|---|
| `myfaq_item` | `id_item`, `id_shop` (`0` znaczy wszystkie sklepy), `active`, `position`, `source` (`manual` albo `ai`), `locked`, `date_add`, `date_upd`. |
| `myfaq_item_lang` | `id_item`, `id_lang`, `question`, `answer`. |
| `myfaq_assoc` | `id_assoc`, `id_item`, `type`, `id_target`. Unikalność na wpis, typ i cel. Typy: `product`, `category`, `feature_value`, `attribute`, `tag`, `manufacturer`, `supplier`. |
| `myfaq_product_display` | `id_product`, `id_shop`, `mode` (`inherit`, `footer`, `tab`, `hidden`). |
| `myfaq_api_key` | `id_api_key`, `api_key`, `label`, `active`, `date_add`, `last_used`. |
| `myfaq_api_log` | `id_log`, `id_api_key`, `label`, `action`, `http_code`, `ip`, `request`, `response`, `date_add`. Zapisany klucz jest zamaskowany. |
| `myfaq_batch` | `id_batch`, `id_shop`, `id_employee`, `status` (`pending`, `running`, `done`), `total`, `done`, `failed`, `options`, `date_add`, `date_upd`. |
| `myfaq_queue` | `id_queue`, `id_batch`, `id_shop`, `id_product`, `id_lang`, `status` (`pending`, `running`, `done`, `error`), `attempts`, `error`, `date_upd`. Wiersz `running` starszy niż pięć minut wraca na `pending`. |

`ensureApiSchema()` rusza przy otwarciu karty API, listy kluczy, historii albo publicznego wywołania API. Dokłada `last_used`, gdy tej kolumny nie ma, i tworzy `myfaq_api_log`, gdy tej tabeli nie ma.

Zapis katalogu ustawia `lock_on_update`, więc aktualizacja ustawia `locked` na 1. `source` przy aktualizacji zostaje bieżącą wartością, chyba że ustawiono `force_source`. Nowy wiersz katalogu jest `manual` i odblokowany. Aktualizacja ze strony produktu też blokuje. Wstawienie ze strony produktu wiąże tylko ten produkt i nie blokuje. Zastąpienie AI kasuje wiersze ze `source` `ai`, `locked` 0 i bez powiązania innego niż ten produkt.

`MyfaqMatcher::categoryIds()` dokłada rodziców tylko wtedy, gdy `MYFAQ_INCLUDE_PARENT_CAT` to 1. Spacer staje, gdy `id_parent` jest mniejsze albo równe 2, albo po 25 krokach.

### 6.7 Klucze i tłumaczenia

Wstawiane przez `installConfig()`. Usuwane przez `deleteConfig()` przy odinstalowaniu.

| Klucz | Gdy go nie ma albo przy instalacji |
|---|---|
| `MYFAQ_DISPLAY` | `footer` |
| `MYFAQ_TAB_TITLE` | `FAQ` na język |
| `MYFAQ_HEADING` | `FAQ` na język |
| `MYFAQ_INCLUDE_PARENT_CAT` | `0` |
| `MYFAQ_SCHEMA` | `1` |
| `MYFAQ_OPEN_FIRST` | `0` |
| `MYFAQ_AI_PROVIDER` | `openai` |
| `MYFAQ_AI_MODEL_OPENAI` | `gpt-4o-mini` |
| `MYFAQ_AI_MODEL_ANTHROPIC`, `MYFAQ_AI_MODEL_GEMINI`, `MYFAQ_AI_MODEL_DEEPSEEK`, `MYFAQ_AI_MODEL_MISTRAL`, `MYFAQ_AI_MODEL_COMPATIBLE` | puste, aż model zostanie zapisany. `MyfaqConfig::model()` zwraca wtedy pierwszy identyfikator wbudowany albo pusty ciąg dla `compatible` |
| `MYFAQ_AI_KEY_` plus dostawca wielkimi literami | puste. Zapis przez `MyfaqConfig::encrypt` (`enc:` i AES-256-CBC, klucz `sha256` z `_COOKIE_KEY_`) |
| `MYFAQ_AI_BASE_URL` | puste. `baseUrl('compatible')` używa wtedy `http://localhost:11434/v1`. `aiBlockReason()` odmawia przebiegu, gdy ta wartość jest pusta, więc przyciski zaplecza nie dochodzą do tego zapasu |
| `MYFAQ_AI_TEMPERATURE` | `0.4`. Odczyt ściska do zakresu 0–2 |
| `MYFAQ_AI_MAX_TOKENS` | `2000`. Odczyt używa 2000, gdy zapis jest poniżej 200, i ucina przy 8000 |
| `MYFAQ_AI_COUNT` | `5`. Odczyt używa 5, gdy zapis jest poniżej 1, i ucina przy 20 |
| `MYFAQ_AI_PROMPT` | puste |
| `MYFAQ_AI_CONTEXT` | JSON z `MyfaqConfig::defaultFlags()`. Włączone: `name`, `description_short`, `description`, `prices`, `categories`, `features`, `manufacturer`. Wyłączone: `combinations`, `tags`, `supplier`, `stock`, `dimensions`, `identifiers`, `attachments`, `existing` |
| `MYFAQ_CUSTOM_MODELS` | `{}` |
| `MYFAQ_CRON_TOKEN` | `bin2hex(random_bytes(16))`. `ensureCronToken()` tworzy token, gdy wartość jest pusta |
| `MYFAQ_BO_TAB` | nieustawione przy instalacji. Otwarta sekcja jest zapisywana przy każdym renderze. Nieznane wartości spadają do `display` |

`deleteConfig()` kasuje też każde `MYFAQ_AI_KEY_*` i `MYFAQ_AI_MODEL_*` dla `openai`, `anthropic`, `gemini`, `deepseek`, `mistral`, `compatible`.

Odinstalowanie nie kasuje `mypresta_updates`, `update_myfaq` ani `updatev_myfaq`. Należą do sprawdzenia aktualizacji. `mypresta_updates` jest włączone, gdy klucza nie ma. Odstęp automatycznego sprawdzenia to 259200 sekund.

Opisy pól siedzą w `MyfaqAdminBo` (`desc` i teksty `sectionBrief`) oraz w `MyfaqApiDocumentation`. Napisy zaplecza idą przez `$this->l()`. Język dokładasz plikiem `translations/{iso}.php`. Napisy, które nie idą przez `$this->l()`: podpowiedzi shortkodów w `MyfaqShortcode::catalogue()`, nazwy kafelków dostawców, tytuły kart flag w `MyfaqConfig::contextFlagDefs()` oraz zdania postępu na stałe w `views/js/admin.js`. Podpowiedzi kart flag są tłumaczone. Tytuły kart flag to angielskie ciągi źródłowe.

`MyfaqConfig::shopScope()` zwraca `0`, gdy kontekst wielosklepu to wszystkie sklepy, a w przeciwnym razie id bieżącego sklepu. Zapis katalogu używa tej wartości. Zapis ze strony produktu używa tylko id bieżącego sklepu.

### 6.8 Rozszerzanie

Nadpisz `views/templates/hook/product.tpl` z motywu w `themes/{theme}/modules/myfaq/views/templates/hook/product.tpl`. Przypisane zmienne to `mfq_items` (`id`, `question`, `answer`), `mfq_heading`, `mfq_open_first` i `mfq_schema`. Tak samo nadpisz `views/css/myfaq.css` i `views/js/myfaq.js`. Akordeon nie jest renderowany, gdy dopasowanie nie zwraca widocznych wierszy, więc nadpisanie motywu nie ma wtedy czego drukować. Nie edytuj szablonów modułu w miejscu, gdy motyw może nieść nadpisanie.

## 7. Pomoc

Strona modułu: [https://mypresta.eu/contact.html](https://mypresta.eu/contact.html)

W sprawie tego modułu zaloguj się na konto klienta na [mypresta.eu](https://mypresta.eu), przejdź do kontaktu i wybierz temat **Support for paid modules**. Formularz podaje, że przy tym temacie logowanie jest wymagane. Po zalogowaniu wybierz ten moduł z historii zakupów.
