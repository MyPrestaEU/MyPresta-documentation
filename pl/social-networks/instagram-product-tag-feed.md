---
title: "Kanał z tagami produktów Instagram - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku i odniesienie dla programistów dla modułu PrestaShop „Kanał z tagami produktów Instagram” od MyPresta.eu."
sidebar:
  label: "Kanał z tagami produktów Instagram - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Instagram product tag feed na MyPresta.eu](https://mypresta.eu/modules/social-networks/instagram-product-tag-feed.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/instagram-product-tag-feed/)
>
> ---


# Kanał z tagami produktów Instagram

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do komunikacji API, które są niemal powszechnie dostępne w nowoczesnych środowiskach hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Aby uzyskać dostęp do ustawień modułu, przejdź do **Moduły > Menedżer modułów** w Panelu administracyjnym PrestaShop, wyszukaj „Kanał z tagami produktów Instagram” i kliknij przycisk „Konfiguruj”.

Tutaj znajdziesz główne opcje konfiguracji, aby kontrolować sposób wyświetlania Twoich kanałów Instagrama.

#### Ustawienia ogólne

-   **Token dostępu do Instagrama:**

    *   **Co robi to ustawienie:** Jest to unikalny kod, który udziela Twojemu sklepowi PrestaShop pozwolenia na dostęp do publicznych danych Twojego konta Instagram (takich jak zdjęcia powiązane z konkretnymi tagami). Musisz wygenerować ten token za pomocą narzędzi deweloperskich Instagrama lub narzędzia innej firmy, które upraszcza ten proces.
    *   **Skutek zmiany tego ustawienia:**
        *   *Po poprawnym wprowadzeniu:* Twój moduł będzie mógł pobierać i wyświetlać zdjęcia z Instagrama.
        *   *Po niepoprawnym wprowadzeniu lub pozostawieniu pustego:* Moduł nie będzie mógł połączyć się z Instagramem, a zdjęcia nie zostaną wyświetlone, co spowoduje pusty kanał lub komunikat o błędzie.
    *   **Zalecana wartość:** Twój prawidłowy token dostępu do Instagrama.
    *   **Scenariusz/przykład dla sprzedawcy:** Właśnie założyłeś konto firmowe na Instagramie. Będziesz musiał postępować zgodnie z instrukcjami Instagrama (lub użyć narzędzia pomocniczego), aby uzyskać ten token i wkleić go tutaj. Bez niego moduł nie będzie mógł „widzieć” Twoich zdjęć z Instagrama.
-   **ID użytkownika Instagrama:**

    *   **Co robi to ustawienie:** Jest to unikalny numeryczny identyfikator Twojego konta Instagram. Często jest wymagany wraz z tokenem dostępu do poprawnego pobierania danych.
    *   **Skutek zmiany tego ustawienia:**
        *   *Po poprawnym wprowadzeniu:* Zapewnia, że moduł pobiera dane z Twojego konkretnego konta Instagram.
        *   *Po niepoprawnym wprowadzeniu lub pozostawieniu pustego:* Może prowadzić do błędów w pobieraniu danych lub pobierania danych z niewłaściwego konta, co skutkuje pustym lub nieprawidłowym kanałem.
    *   **Zalecana wartość:** Twój prawidłowy ID użytkownika Instagrama.
    *   **Scenariusz/przykład dla sprzedawcy:** Podobnie jak w przypadku tokena dostępu, uzyskasz ten ID podczas konfigurowania dostępu do API Instagrama. Mówi on modułowi, *czyj* kanał Instagrama ma przeglądać.
-   **Liczba zdjęć do wyświetlenia:**

    *   **Co robi to ustawienie:** Kontroluje, ile zdjęć z Instagrama jest pobieranych i wyświetlanych w pojedynczej instancji kanału.
    *   **Skutek zmiany tego ustawienia:**
        *   *Po ustawieniu na wyższą liczbę (np. 10):* Więcej zdjęć zostanie załadowanych i potencjalnie wyświetlonych w kanale, co sprawi, że będzie on bogatszy, ale prawdopodobnie wolniejszy w ładowaniu.
        *   *Po ustawieniu na niższą liczbę (np. 3):* Mniej zdjęć zostanie wyświetlonych, co skutkuje bardziej zwięzłym kanałem i szybszym czasem ładowania.
    *   **Zalecana wartość:** Zacznij od 6-9 zdjęć, aby uzyskać dobrą równowagę między treścią a wydajnością. Dostosuj w oparciu o swój układ i testy szybkości strony.
    *   **Scenariusz/przykład dla sprzedawcy:** Dla zakładki strony produktu możesz chcieć 6 zdjęć. Dla karuzeli na stronie głównej możesz chcieć 12, aby zapewnić większą różnorodność podczas przewijania przez użytkowników.
-   **Wyświetl na stronie głównej:**

    *   **Co robi to ustawienie:** Prosty przełącznik do włączania lub wyłączania kanału Instagrama na stronie głównej Twojego sklepu.
    *   **Skutek zmiany tego ustawienia:**
        *   *Po włączeniu:* Moduł spróbuje wyświetlić kanał Instagrama na Twojej stronie głównej (zazwyczaj za pomocą hooka `displayHome`).
        *   *Po wyłączeniu:* Na Twojej stronie głównej nie pojawi się kanał Instagrama.
    *   **Zalecana wartość:** TAK, jeśli chcesz wyraźnie prezentować swoje treści z Instagrama. NIE, jeśli wolisz czystszą stronę główną lub chcesz, aby kanały były tylko na stronach produktów.
    *   **Scenariusz/przykład dla sprzedawcy:** Chcesz pokazać swoje najnowsze zdjęcia lifestyle’owe na stronie głównej, aby natychmiast zaangażować odwiedzających. Włączyłbyś to.
-   **Wyświetl na stronie produktu:**

    *   **Co robi to ustawienie:** Prosty przełącznik do włączania lub wyłączania kanału Instagrama na poszczególnych stronach produktów.
    *   **Skutek zmiany tego ustawienia:**
        *   *Po włączeniu:* Moduł spróbuje wyświetlić kanał Instagrama specyficzny dla produktu na Twoich stronach produktów (zazwyczaj za pomocą hooków `displayProductTab` lub `displayProductExtraContent`).
        *   *Po wyłączeniu:* Na stronach produktów nie pojawi się kanał Instagrama.
    *   **Zalecana wartość:** TAK, ponieważ jest to jedna z podstawowych funkcji modułu i potężne narzędzie do konwersji.
    *   **Scenariusz/przykład dla sprzedawcy:** Sprzedajesz buty i chcesz pokazać zdjęcia z Instagrama ludzi noszących *ten konkretny model buta* na jego stronie produktu. Włączyłbyś to.
-   **Wyświetl w lewej kolumnie:**

    *   **Co robi to ustawienie:** Kontroluje, czy kanał Instagrama pojawia się w lewej kolumnie bocznej Twojego sklepu.
    *   **Skutek zmiany tego ustawienia:**
        *   *Po włączeniu:* Kanał zostanie wyrenderowany w lewej kolumnie na stronach, na których jest podpięty.
        *   *Po wyłączeniu:* Brak kanału w lewej kolumnie.
    *   **Zalecana wartość:** NIE, chyba że masz bardzo specyficzne potrzeby projektowe. Kolumny mogą stać się zagracone.
    *   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby mały, stały kanał był widoczny, gdy klienci przeglądają kategorie.
-   **Wyświetl w prawej kolumnie:**

    *   **Co robi to ustawienie:** Kontroluje, czy kanał Instagrama pojawia się w prawej kolumnie bocznej Twojego sklepu.
    *   **Skutek zmiany tego ustawienia:**
        *   *Po włączeniu:* Kanał zostanie wyrenderowany w prawej kolumnie na stronach, na których jest podpięty.
        *   *Po wyłączeniu:* Brak kanału w prawej kolumnie.
    *   **Zalecana wartość:** NIE, chyba że masz bardzo specyficzne potrzeby projektowe. Kolumny mogą stać się zagracone.
    *   **Scenariusz/przykład dla sprzedawcy:** Podobnie jak w przypadku lewej kolumny, dla stałego, mniejszego kanału.
-   **Wyświetl w stopce:**

    *   **Co robi to ustawienie:** Kontroluje, czy kanał Instagrama pojawia się w obszarze stopki Twojego sklepu.
    *   **Skutek zmiany tego ustawienia:**
        *   *Po włączeniu:* Kanał zostanie wyrenderowany w stopce.
        *   *Po wyłączeniu:* Brak kanału w stopce.
    *   **Zalecana wartość:** TAK, dla subtelnego, ale skutecznego sposobu prezentowania Twojego Instagrama. Jest mniej inwazyjny niż kolumny.
    *   **Scenariusz/przykład dla sprzedawcy:** Chcesz dodać atrakcyjną wizualnie sekcję na dole każdej strony, zachęcając odwiedzających do eksplorowania Twojego Instagrama.
-   **Wyświetl w nagłówku (lewa strona):**

    *   **Co robi to ustawienie:** Kontroluje, czy kanał Instagrama pojawia się w lewej części nagłówka Twojego sklepu.
    *   **Skutek zmiany tego ustawienia:**
        *   *Po włączeniu:* Kanał zostanie wyrenderowany w lewej sekcji nagłówka.
        *   *Po wyłączeniu:* Brak kanału w nagłówku.
    *   **Zalecana wartość:** NIE, zazwyczaj nagłówki są zarezerwowane dla nawigacji i brandingu.
    *   **Scenariusz/przykład dla sprzedawcy:** Bardzo specyficzny projekt, w którym chcesz małą, obracającą się ikonę Instagrama lub pojedynczy obraz w nagłówku.
-   **Wyświetl w nagłówku (prawa strona):**

    *   **Co robi to ustawienie:** Kontroluje, czy kanał Instagrama pojawia się w prawej części nagłówka Twojego sklepu.
    *   **Skutek zmiany tego ustawienia:**
        *   *Po włączeniu:* Kanał zostanie wyrenderowany w prawej sekcji nagłówka.
        *   *Po wyłączeniu:* Brak kanału w nagłówku.
    *   **Zalecana wartość:** NIE, zazwyczaj nagłówki są zarezerwowane dla nawigacji i brandingu.
    *   **Scenariusz/przykład dla sprzedawcy:** Podobnie jak w przypadku nagłówka (lewa strona).
-   **Funkcja karuzeli:**

    *   **Co robi to ustawienie:** Włącza lub wyłącza funkcjonalność karuzeli (galerii przesuwnej) dla kanałów Instagrama.
    *   **Skutek zmiany tego ustawienia:**
        *   *Po włączeniu:* Zdjęcia będą wyświetlane w poziomej, przewijanej karuzeli, oszczędzając miejsce i umożliwiając użytkownikom łatwe przeglądanie wielu obrazów.
        *   *Po wyłączeniu:* Zdjęcia prawdopodobnie będą wyświetlane w statycznej siatce lub liście, w zależności od szablonu.
    *   **Zalecana wartość:** TAK, dla większości miejsc (strona główna, strona produktu), ponieważ jest to oszczędne pod względem miejsca i angażujące.
    *   **Scenariusz/przykład dla sprzedawcy:** Masz 9 zdjęć produktu, ale tylko miejsce na 3 jednocześnie. Włączenie karuzeli pozwala klientom przewijać wszystkie 9.
-   **Funkcja Fancybox:**

    *   **Co robi to ustawienie:** Włącza lub wyłącza efekt „Fancybox”, który jest popularną biblioteką JavaScript wyświetlającą obrazy w stylowym, nakładającym się wyskakującym okienku po kliknięciu.
    *   **Skutek zmiany tego ustawienia:**
        *   *Po włączeniu:* Kliknięcie zdjęcia z Instagrama w kanale otworzy je w dużym, eleganckim wyskakującym okienku, umożliwiając klientom przeglądanie szczegółów bez opuszczania strony.
        *   *Po wyłączeniu:* Kliknięcie obrazu może otworzyć go bezpośrednio w nowej karcie przeglądarki lub po prostu nic nie zrobić, w zależności od motywu.
    *   **Zalecana wartość:** TAK, ponieważ zapewnia znacznie lepsze wrażenia użytkownika podczas przeglądania obrazów.
    *   **Scenariusz/przykład dla sprzedawcy:** Klient widzi świetny strój na Instagramie w Twoim kanale. Kliknięcie go otwiera duży, wyraźny widok zdjęcia, ułatwiając docenienie szczegółów.

#### Ustawienia specyficzne dla strony produktu (zakładka w Panelu administracyjnym produktu)

Po zainstalowaniu modułu znajdziesz nowe pole lub zakładkę podczas edycji produktu w Panelu administracyjnym PrestaShop:

-   **Hashtag Instagrama (dla każdego produktu):**
    *   **Co robi to ustawienie:** To pole pozwala określić unikalny hashtag Instagrama dla każdego pojedynczego produktu. Moduł użyje tego hashtagu do pobrania odpowiednich zdjęć z Twojego konta Instagram.
    *   **Skutek zmiany tego ustawienia:**
        *   *Po wprowadzeniu hashtagu (np. #nazwamojegoproduktu):* Kanał Instagrama na tej konkretnej stronie produktu będzie wyświetlał zdjęcia z Twojego konta Instagram, które są oznaczone `#nazwamojegoproduktu`.
        *   *Po pozostawieniu pustego:* Dla tego produktu nie zostanie wyświetlony kanał Instagrama specyficzny dla produktu, nawet jeśli opcja „Wyświetl na stronie produktu” jest włączona.
    *   **Zalecana wartość:** Unikalny, opisowy hashtag dla każdego produktu. Upewnij się, że konsekwentnie używasz tego hashtagu w swoich postach na Instagramie.
    *   **Scenariusz/przykład dla sprzedawcy:** Dla produktu o nazwie „Sukienka Letnia Bryza” możesz wprowadzić `#SukienkaLetniaBryza` lub `#MojaMarkaSukienkaLetnia`. Następnie, gdy publikujesz zdjęcia tej sukienki na Instagramie, dołączasz ten hashtag. Moduł następnie pobierze te zdjęcia na stronę produktu sukienki.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Token dostępu do Instagrama | Twój prawidłowy token | Łączy się z API Instagrama w celu pobierania zdjęć. **KRYTYCZNE.** |
| Konfiguracja modułu | ID użytkownika Instagrama | Twój prawidłowy ID użytkownika | Identyfikuje Twoje konto Instagram do pobierania danych. |
| Konfiguracja modułu | Liczba zdjęć do wyświetlenia | 6-9 | Kontroluje, ile zdjęć jest wyświetlanych w instancji kanału. |
| Konfiguracja modułu | Wyświetl na stronie głównej | TAK | Pokazuje ogólny kanał na stronie głównej Twojego sklepu. |
| Konfiguracja modułu | Wyświetl na stronie produktu | TAK | Pokazuje kanał specyficzny dla produktu na stronach produktów. |
| Konfiguracja modułu | Wyświetl w lewej kolumnie | NIE | Pokazuje kanał w lewej kolumnie bocznej. Może zagracać układ. |
| Konfiguracja modułu | Wyświetl w prawej kolumnie | NIE | Pokazuje kanał w prawej kolumnie bocznej. Może zagracać układ. |
| Konfiguracja modułu | Wyświetl w stopce | TAK | Pokazuje kanał w stopce sklepu. Dobre do subtelnej promocji. |
| Konfiguracja modułu | Wyświetl w nagłówku (lewa strona) | NIE | Pokazuje kanał w lewym nagłówku. Ogólnie niezalecane. |
| Konfiguracja modułu | Wyświetl w nagłówku (prawa strona) | NIE | Pokazuje kanał w prawym nagłówku. Ogólnie niezalecane. |
| Konfiguracja modułu | Funkcja karuzeli | TAK | Wyświetla zdjęcia w galerii przesuwnej, oszczędzając miejsce. |
| Konfiguracja modułu | Funkcja Fancybox | TAK | Otwiera zdjęcia w stylowym wyskakującym okienku dla lepszego podglądu. |
| Strona edycji produktu | Hashtag Instagrama | Unikalny dla każdego produktu | Definiuje hashtag do pobierania zdjęć dla *tego konkretnego produktu*. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Mój kanał Instagrama nie wyświetla żadnych zdjęć. Co powinienem zrobić?**
O:

1.  **Sprawdź swój token dostępu do Instagrama i ID użytkownika:** To najczęstsze przyczyny problemów. Upewnij się, że są poprawnie wprowadzone w konfiguracji modułu i nadal są ważne. Tokeny Instagrama mogą wygasnąć, więc może być konieczne ich ponowne wygenerowanie.
2.  **Zweryfikuj hashtagi:** Dla stron produktów upewnij się, że pole „Hashtag Instagrama” jest wypełnione dla konkretnego produktu i że faktycznie masz posty na Instagramie używające dokładnie tego hashtagu.
3.  **Konto publiczne:** Upewnij się, że Twoje konto Instagram jest publiczne. Moduł nie może pobierać zdjęć z kont prywatnych.
4.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i wyczyść pamięć podręczną Smarty (i opcjonalnie wszystkie pamięci podręczne). Czasami stare dane z pamięci podręcznej uniemożliwiają wyświetlanie nowych treści.
5.  **Sprawdź limity API:** Instagram ma limity szybkości API. Jeśli pobierasz zbyt często lub masz bardzo dużą liczbę produktów, możesz tymczasowo osiągnąć te limity.

**P: Obrazy są wyświetlane, ale wyglądają dziwnie lub psują układ mojego motywu.**
O:

1.  **Konflikty motywu:** Twój niestandardowy motyw PrestaShop może mieć sprzeczne style CSS. Jest to częsty problem z modułami innych firm.
2.  **CSS modułu:** Moduł zawiera własny CSS (`instagramfeed/css/css.css`, `instagramfeed/lib/src/css/lightslider.css`). Twój webmaster lub deweloper może zbadać stronę, aby zidentyfikować sprzeczne style i napisać niestandardowe nadpisania CSS w arkuszu stylów Twojego motywu.
3.  **Wymiary obrazów:** Upewnij się, że obrazy, które publikujesz na Instagramie, są rozsądnej jakości i proporcji. Chociaż moduł próbuje się dostosować, ekstremalnie szerokie lub wysokie obrazy mogą powodować problemy z wyświetlaniem.

**P: Jak uzyskać token dostępu do Instagrama i ID użytkownika?**
O: Dostęp do API Instagrama zmieniał się w czasie. Zazwyczaj potrzebujesz konta firmowego na Instagramie i konta deweloperskiego na Facebooku. Proces obejmuje utworzenie aplikacji na Facebooku, połączenie jej z Twoim kontem firmowym na Instagramie, a następnie wygenerowanie tokena. Istnieją również narzędzia innych firm (wyszukaj „Instagram Access Token Generator”), które mogą uprościć ten proces, ale zawsze używaj renomowanych.

**P: Czy mogę wyświetlać różne kanały na różnych stronach (np. ogólny kanał na stronie głównej i kanały specyficzne dla produktów)?**
O: Tak, absolutnie! To jest podstawowa funkcjonalność. Użyj ustawienia „Wyświetl na stronie głównej” dla ogólnego kanału (który zazwyczaj będzie pobierał dane z domyślnego hashtagu lub Twojego głównego kanału użytkownika), a następnie użyj pola „Hashtag Instagrama” na poszczególnych stronach produktów dla kanałów specyficznych dla produktów.

**P: Karuzela lub Fancybox nie działa.**
O:

1.  **Włącz funkcje:** Sprawdź dwukrotnie, czy „Funkcja karuzeli” i „Funkcja Fancybox” są włączone w konfiguracji modułu.
2.  **Konflikty JavaScript:** Inny moduł lub Twój motyw może ładować sprzeczne biblioteki JavaScript (np. inny skrypt karuzeli lub lightbox). Twój webmaster musiałby to debugować za pomocą konsoli deweloperskiej przeglądarki (szukaj błędów JavaScript).
3.  **jQuery:** Upewnij się, że jQuery jest poprawnie załadowane w Twoim sklepie, ponieważ wiele funkcji JavaScript na nim polega.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Kanał z tagami produktów Instagram` jest zgodny ze standardową architekturą modułów PrestaShop, głównie wykorzystując klasę `Module` do konfiguracji i system `Hook` do wyświetlania w front-office. Integruje niestandardową klasę do interakcji z API Instagrama i wykorzystuje zewnętrzne biblioteki JavaScript (lightslider, fancybox) do ulepszonego UI/UX. Podstawowa logika modułu znajduje się w jego głównym pliku `index.php`, obsługującym konfigurację, instalację i rejestrację hooków. Renderowanie front-office odbywa się poprzez przekazywanie danych do szablonów Smarty zarejestrowanych w różnych hookach wyświetlania.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych dedykowanych kontrolerów front-office ani back-office. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu, a wyświetlanie w front-office jest zarządzane bezpośrednio za pośrednictwem zarejestrowanych hooków.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   `instagramfeed/classes/index.php`:

    *   Jest to zazwyczaj pusty plik lub plik zawierający `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;` aby zapobiec bezpośredniemu listowaniu katalogów. Nie zawiera żadnej funkcjonalnej logiki klas.
-   `instagramfeed/classes/instagram_class.php`:

    *   **Nazwa klasy**: `Instagram`
    *   **Klasa nadrzędna**: Brak (samodzielna klasa narzędziowa)
    *   **Odpowiedzialność**: Ta klasa hermetyzuje logikę interakcji z API Instagrama. Jest odpowiedzialna za wykonywanie żądań HTTP w celu pobierania mediów na podstawie ID użytkownika i hashtagów, obsługę tokenów dostępu oraz parsowanie odpowiedzi JSON z Instagrama.
    *   **Kluczowe metody publiczne**:
        *   `__construct($access_token, $user_id)`: Konstruktor, inicjalizuje z tokenem dostępu do Instagrama i ID użytkownika.
        *   `getMediaByHashtag($hashtag, $count)`: Pobiera określoną liczbę elementów mediów z API Instagrama, które są oznaczone danym hashtagiem i powiązane ze skonfigurowanym ID użytkownika. Zwraca tablicę obiektów mediów.
        *   `getMediaByUser($count)`: Pobiera określoną liczbę elementów mediów bezpośrednio z kanału użytkownika (jeśli jest obsługiwane przez wersję API i zakres tokena).
        *   (Potencjalnie inne metody pomocnicze do wywołań API, obsługi błędów itp.)

### 4.4 Zasoby JavaScript (`views/js/`)

-   `instagramfeed/js/if_carousell.js`:
    *   **Zakres**: Front-office.
    *   **Opis**: Ten skrypt prawdopodobnie inicjalizuje i konfiguruje funkcjonalność karuzeli `lightslider` dla kanałów Instagrama. Wiąże się z określonymi elementami DOM (np. `ul` z określoną klasą) i stosuje zachowanie karuzeli, w tym ustawienia responsywności, automatycznego odtwarzania, nawigacji itp.
    *   **Zależności**: Opiera się na `lightslider.js` i jQuery.
-   `instagramfeed/js/if_fancybox.js`:
    *   **Zakres**: Front-office.
    *   **Opis**: Ten skrypt inicjalizuje i konfiguruje funkcjonalność lightbox Fancybox. Celuje w linki do obrazów w kanale Instagrama (np. tagi `a` otaczające tagi `img`) i umożliwia ich otwieranie w wyskakującym okienku Fancybox po kliknięciu, zapewniając większy, bardziej wciągający widok obrazu.
    *   **Zależności**: Opiera się na bibliotece Fancybox (nie jest dołączona do tego modułu, ale oczekuje się, że zostanie załadowana przez motyw lub inny moduł) i jQuery.
-   `instagramfeed/js/if_sliding.js`:
    *   **Zakres**: Front-office.
    *   **Opis**: Ten plik może być alternatywnym lub uzupełniającym skryptem do funkcji przesuwania, być może dla starszych wersji PrestaShop lub specyficznych układów. Biorąc pod uwagę `if_carousell.js` i `lightslider.js`, może to być starszy skrypt lub wrapper dla specyficznych zachowań przesuwania nieobjętych główną karuzelą.
    *   **Zależności**: Prawdopodobnie jQuery.
-   `instagramfeed/js/ps14.js`:
    *   **Zakres**: Front-office (specjalnie dla kompatybilności z PrestaShop 1.4).
    *   **Opis**: Ten skrypt prawdopodobnie zawiera poprawki kompatybilności lub polifille dla starszych środowisk PrestaShop 1.4, rozwiązując potencjalne różnice w JavaScript lub brakujące wersje/funkcje jQuery w porównaniu do nowszych wydań PrestaShop.
    *   **Zależności**: jQuery.
-   `instagramfeed/lib/src/js/lightslider.js`:
    *   **Zakres**: Front-office.
    *   **Opis**: Jest to podstawowa biblioteka wtyczki jQuery `lightslider`. Zapewnia funkcjonalność do tworzenia responsywnych, dotykowych karuzel i suwaków treści. `if_carousell.js` zazwyczaj wywoływałby metody z tej biblioteki.
    *   **Zależności**: jQuery.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `instagramfeed/css/css.css`:
    *   **Zakres**: Stylizacja front-office dla klienta.
    *   **Opis**: Zawiera niestandardowe reguły CSS specyficzne dla układu kanału Instagrama, rozmiaru obrazów, odstępów i ogólnego wyglądu w różnych hookach. Definiuje klasy dla kontenera kanału, poszczególnych elementów obrazu i potencjalnie podpisów lub linków.
    *   **Kluczowe selektory klas CSS**: Deweloperzy mogą sprawdzić wygenerowany kod HTML, aby znaleźć klasy takie jak `.instagram-feed-container`, `.instagram-item`, `.instagram-image` itp., które można nadpisać w pliku `custom.css` lub `theme.css` motywu.
-   `instagramfeed/lib/src/css/lightslider.css`:
    *   **Zakres**: Stylizacja front-office dla klienta.
    *   **Opis**: Jest to domyślny arkusz stylów dla wtyczki jQuery `lightslider`. Zapewnia podstawową stylizację dla strzałek nawigacyjnych karuzeli, kropek paginacji, przejść slajdów i responsywnego zachowania.
    *   **Kluczowe selektory klas CSS**: Klasy takie jak `.lightSlider`, `.lSAction`, `.lSPager` itp., które można dostosować do brandingu sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:

    *   `instagramfeed/views/templates/admin/instagram_feed.tpl`: Ten szablon jest renderowany przez metodę `getContent()` w głównym pliku modułu. Wyświetla formularz konfiguracji modułu w back-office, w tym pola wejściowe dla tokena dostępu do Instagrama, ID użytkownika, liczby zdjęć i różnych przełączników wyświetlania (strona główna, strona produktu, kolumny, stopka, nagłówek, karuzela, fancybox). Zazwyczaj używa komponentów formularzy pomocniczych PrestaShop.
-   **Szablony hooków (`views/templates/hook/`)**:

    *   `instagramfeed/views/templates/hook/column-feed.tpl`: Renderuje kanał Instagrama, gdy jest podpięty do `displayLeftColumn` lub `displayRightColumn`. Zazwyczaj wyświetla bardziej kompaktową wersję kanału.
    *   `instagramfeed/views/templates/hook/feed.tpl`: Szablon kanału ogólnego przeznaczenia, prawdopodobnie używany do wyświetlania na stronie głównej lub w stopce. Zawiera podstawową strukturę do wyświetlania obrazów z Instagrama, potencjalnie opakowanych w kontener karuzeli.
    *   `instagramfeed/views/templates/hook/header-left.tpl`: Renderuje kanał, gdy jest podpięty do `displayHeaderLeft`.
    *   `instagramfeed/views/templates/hook/header-right.tpl`: Renderuje kanał, gdy jest podpięty do `displayHeaderRight`.
    *   `instagramfeed/views/templates/hook/homepage-feed.tpl`: Specjalnie zaprojektowany dla hooka `displayHome`, często z bardziej widocznym lub szerszym układem dla strony głównej.
    *   `instagramfeed/views/templates/hook/tab.tpl`: Renderuje tytuł zakładki dla kanału Instagrama na stronie produktu (np. „Zdjęcia z Instagrama”). Jest to zazwyczaj podpięte do `displayProductTab` (PrestaShop 1.6) lub `displayProductExtraContent` (PrestaShop 1.7+).
    *   `instagramfeed/views/templates/hook/tabcontents.tpl`: Renderuje rzeczywistą zawartość kanału Instagrama w zakładce strony produktu. Ten szablon będzie zawierał logikę wyświetlania obrazów pobranych za pomocą hashtagu specyficznego dla produktu, często wykorzystując funkcje karuzeli i fancybox.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    *   Moduł nie tworzy niestandardowych tabel SQL.
    *   Ustawienia konfiguracji (token dostępu, ID użytkownika, opcje wyświetlania itp.) są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `INSTAGRAMFEED_ACCESS_TOKEN`, `INSTAGRAMFEED_USER_ID`, `INSTAGRAMFEED_NUM_PHOTOS` itp.
    *   Hashtag Instagrama specyficzny dla produktu jest przechowywany w tabeli `ps_product_lang` (lub podobnej tabeli związanej z produktami) jako nowe pole dodane przez moduł podczas instalacji. To pole zazwyczaj nazywałoby się `instagram_hashtag` lub podobnie.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Służy do ładowania zasobów CSS i JavaScript (lightslider, fancybox, niestandardowe skrypty) wymaganych dla kanałów Instagrama. |
| `displayHome` | Na stronie głównej sklepu. | Renderuje ogólny kanał Instagrama na stronie głównej. |
| `displayLeftColumn` | W lewej kolumnie bocznej stron, na których jest włączony. | Renderuje kompaktowy kanał Instagrama w lewej kolumnie. |
| `displayRightColumn` | W prawej kolumnie bocznej stron, na których jest włączony. | Renderuje kompaktowy kanał Instagrama w prawej kolumnie. |
| `displayFooter` | W sekcji stopki sklepu. | Renderuje ogólny kanał Instagrama w stopce. |
| `displayHeaderLeft` | W lewej części nagłówka sklepu. | Renderuje mały kanał Instagrama w nagłówku. |
| `displayHeaderRight` | W prawej części nagłówka sklepu. | Renderuje mały kanał Instagrama w nagłówku. |
| `displayProductTab` (PS 1.6) | Na stronie produktu, do dodawania nowych zakładek. | Renderuje tytuł zakładki kanału Instagrama na stronie produktu. |
| `displayProductTabContent` (PS 1.6) | Na stronie produktu, do dodawania treści do zakładek. | Renderuje zawartość (rzeczywisty kanał Instagrama) w zakładce strony produktu. |
| `displayProductExtraContent` (PS 1.7+) | Na stronie produktu, do dodawania dodatkowych bloków treści. | Alternatywny hook dla PrestaShop 1.7+ do wyświetlania kanału Instagrama na stronach produktów, często jako nowy blok poniżej głównych informacji o produkcie. |
| `actionProductUpdate` | Po zaktualizowaniu produktu w Panelu administracyjnym. | Służy do zapisywania wartości pola `instagram_hashtag` dla produktu. |
| `actionProductAdd` | Po dodaniu nowego produktu w Panelu administracyjnym. | Służy do zapisywania wartości pola `instagram_hashtag` dla nowego produktu. |
| `displayAdminProductsExtra` | Na stronie edycji produktu w Panelu administracyjnym. | Renderuje pole wejściowe dla „Hashtagu Instagrama” na stronie konfiguracji produktu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w udzielanie pomocy i zapewnienie optymalnego działania Twojego modułu.
