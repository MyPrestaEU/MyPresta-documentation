---
title: "Darmowy widżet Twittera - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Darmowy widżet Twittera” od MyPresta.eu."
sidebar:
  label: "Darmowy widżet Twittera - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Twitter widget free na MyPresta.eu](https://mypresta.eu/modules/social-networks/twitter-widget-free.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/twitter-widget-free/)
>
> ---


# Darmowy widżet Twittera

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Brak specjalnych wymagań poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu „Darmowy widżet Twittera”. Tutaj zdefiniujesz, jak Twoja oś czasu Twittera będzie wyglądać i działać w Twoim sklepie.

| Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- |
| **Nazwa użytkownika Twittera** | `mypresta` (przykład) | **Co robi to ustawienie:** Jest to najważniejsze ustawienie. Określa konto Twitter (X), którego publiczne tweety będą wyświetlane. Musisz wprowadzić nazwę użytkownika swojego konta (np. `mypresta`, `nazwatwojegosklepu`). **Efekt zmiany tego ustawienia:** *Po ustawieniu na Twoją nazwę użytkownika:* Widżet pobierze i wyświetli tweety z Twojego określonego konta. *Po pozostawieniu pustego lub nieprawidłowego:* Widżet albo nie wyświetli żadnych tweetów, albo wyświetli komunikat o błędzie, ponieważ nie będzie wiedział, z którego konta pobrać dane. **Zalecana wartość:** Twoja oficjalna nazwa użytkownika Twitter (X), bez symbolu „@”. **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój uchwyt Twittera to `@MojWspanialySklep`, wpisz `MojWspanialySklep`. |
| **ID widżetu** | `(puste)` | **Co robi to ustawienie:** Jest to zaawansowane ustawienie dla specyficznych konfiguracji widżetu Twittera. Twitter umożliwia tworzenie niestandardowych widżetów na swojej platformie, które generują unikalny ID. Ten ID może być użyty do wyświetlania wysoce spersonalizowanej osi czasu (np. osi czasu konkretnych list, wyników wyszukiwania lub kolekcji). **Efekt zmiany tego ustawienia:** *Po pozostawieniu pustego:* Moduł wygeneruje standardową oś czasu na podstawie Twojej „Nazwy użytkownika Twittera”. Zazwyczaj jest to wystarczające dla większości sprzedawców. *Po wprowadzeniu prawidłowego ID widżetu:* Moduł wyświetli konkretną, spersonalizowaną oś czasu powiązaną z tym ID, zastępując domyślną oś czasu użytkownika. **Zalecana wartość:** Pozostaw puste, chyba że utworzyłeś niestandardowy widżet na platformie deweloperskiej Twittera i chcesz użyć jego ID. **Scenariusz / przykład dla sprzedawcy:** Możesz utworzyć niestandardowy widżet Twittera, który wyświetla tylko tweety zawierające konkretny hashtag związany z kampanią. Następnie uzyskasz ID tego widżetu z Twittera i wprowadzisz je tutaj. |
| **Motyw** | `light` | **Co robi to ustawienie:** Kontroluje wizualny motyw widżetu Twittera. **Efekt zmiany tego ustawienia:** *Po ustawieniu na `light` (domyślne):* Widżet będzie miał jasne tło i ciemny tekst, odpowiedni dla większości sklepów PrestaShop o jasnym motywie. *Po ustawieniu na `dark` (jeśli dostępne):* Widżet będzie miał ciemne tło i jasny tekst, idealny dla sklepów o ciemnym motywie lub do stworzenia kontrastu. **Zalecana wartość:** `light` dla większości sklepów. Wybierz `dark`, jeśli projekt Twojego sklepu wykorzystuje ciemną kolorystykę. **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja strona internetowa ma czyste, białe tło, motyw `light` idealnie się wtopi. Jeśli Twoja strona używa wyrafinowanego ciemnoszarego lub czarnego tła, motyw `dark` byłby bardziej odpowiedni. |
| **Kolor linków** | `(puste)` | **Co robi to ustawienie:** Umożliwia dostosowanie koloru linków w widżecie Twittera (np. hashtagów, wzmianek, adresów URL). **Efekt zmiany tego ustawienia:** *Po pozostawieniu pustego:* Widżet użyje domyślnego koloru linków Twittera (zazwyczaj odcień niebieskiego). *Po wprowadzeniu prawidłowego kodu koloru szesnastkowego (np. `#FF0000` dla czerwonego):* Wszystkie linki w widżecie zostaną wyświetlone w tym niestandardowym kolorze. **Zalecana wartość:** Pozostaw puste dla domyślnego, lub wprowadź kod koloru szesnastkowego, który pasuje do brandingu Twojego sklepu. **Scenariusz / przykład dla sprzedawcy:** Jeśli głównym kolorem Twojej marki jest zielony, możesz wprowadzić `#008000`, aby linki w widżecie pasowały do Twojej marki. |
| **Kolor obramowania** | `(puste)` | **Co robi to ustawienie:** Umożliwia dostosowanie koloru obramowania wokół widżetu Twittera. **Efekt zmiany tego ustawienia:** *Po pozostawieniu pustego:* Widżet użyje domyślnego koloru obramowania Twittera. *Po wprowadzeniu prawidłowego kodu koloru szesnastkowego:* Obramowanie widżetu zostanie wyświetlone w tym niestandardowym kolorze. **Zalecana wartość:** Pozostaw puste dla domyślnego, lub wprowadź kod koloru szesnastkowego, który pasuje do brandingu Twojego sklepu lub komponuje się z Twoim układem. **Scenariusz / przykład dla sprzedawcy:** Aby widżet wyróżniał się subtelną ramką, możesz użyć jasnoszarego obramowania `#CCCCCC`. |
| **Limit tweetów** | `20` | **Co robi to ustawienie:** Określa maksymalną liczbę tweetów, które zostaną wyświetlone na osi czasu. **Efekt zmiany tego ustawienia:** *Po ustawieniu na niższą liczbę (np. `3`):* Widoczne będą tylko najnowsze tweety, co skróci widżet. *Po ustawieniu na wyższą liczbę (np. `20`):* Załadowanych zostanie więcej tweetów, co wydłuży widżet i umożliwi większe przewijanie. **Zalecana wartość:** `3` do `7` dla kolumn bocznych, aby zachować zwięzłość, `10` do `20` dla szerszych obszarów, takich jak stopka lub główna treść. **Scenariusz / przykład dla sprzedawcy:** Jeśli umieścisz widżet w wąskiej lewej kolumnie, możesz ustawić go na `3`, aby uniknąć zbyt długiej kolumny. W stopce możesz ustawić go na `10`, aby pokazać więcej aktywności. |
| **Wysokość** | `300` | **Co robi to ustawienie:** Ustawia stałą wysokość widżetu Twittera w pikselach. **Efekt zmiany tego ustawienia:** *Po ustawieniu na niższą liczbę (np. `200`):* Widżet będzie krótszy, potencjalnie wymagając więcej przewijania, aby zobaczyć wszystkie tweety (do limitu tweetów). *Po ustawieniu na wyższą liczbę (np. `500`):* Widżet będzie wyższy, wyświetlając więcej tweetów jednocześnie bez przewijania. **Zalecana wartość:** `280` do `400` pikseli, w zależności od umiejscowienia i dostępnej przestrzeni. **Scenariusz / przykład dla sprzedawcy:** Dla prawej kolumny wysokość `300px` jest często dobrym kompromisem. Dla umiejscowienia w stopce możesz zwiększyć ją do `400px`, jeśli masz dużo pionowej przestrzeni. |
| **Szerokość** | `(puste)` | **Co robi to ustawienie:** Ustawia stałą szerokość widżetu Twittera w pikselach. **Efekt zmiany tego ustawienia:** *Po pozostawieniu pustego:* Widżet spróbuje automatycznie dostosować swoją szerokość do kontenera, w którym jest umieszczony (zachowanie responsywne). Jest to ogólnie zalecane. *Po ustawieniu na konkretną liczbę (np. `250`):* Widżet zachowa tę stałą szerokość, co może spowodować przepełnienie lub pustą przestrzeń, jeśli kontener jest większy lub mniejszy. **Zalecana wartość:** Pozostaw puste dla zachowania responsywnego, lub ustaw konkretną szerokość, jeśli potrzebujesz precyzyjnej kontroli i rozumiesz konsekwencje dla różnych rozmiarów ekranu. **Scenariusz / przykład dla sprzedawcy:** Pozostawienie pustego zapewnia dobry wygląd na urządzeniach mobilnych. Jeśli absolutnie potrzebujesz stałej szerokości dla bardzo specyficznego układu, możesz ustawić ją na `280px` dla wąskiej kolumny. |
| **Język** | `en` | **Co robi to ustawienie:** Określa język, w którym wyświetlany jest interfejs widżetu Twittera (np. przycisk „Wyświetl na Twitterze”, znaczniki czasu). **Efekt zmiany tego ustawienia:** *Po ustawieniu na `en` (angielski):* Interfejs widżetu będzie w języku angielskim. *Po ustawieniu na inny prawidłowy kod języka (np. `fr` dla francuskiego, `es` dla hiszpańskiego):* Interfejs widżetu zostanie zlokalizowany na ten język. **Zalecana wartość:** Główny język Twojego sklepu. **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój sklep obsługuje głównie klientów we Francji, ustawienie tego na `fr` sprawi, że widżet będzie dla nich bardziej przyjazny. |
| **Wyświetl nagłówek** | `TAK` | **Co robi to ustawienie:** Kontroluje, czy sekcja nagłówka widżetu Twittera (pokazująca nazwę Twojego konta i etykietę „Tweety”) jest widoczna. **Efekt zmiany tego ustawienia:** *Po włączeniu (TAK):* Nagłówek zostanie wyświetlony, zapewniając jasny kontekst, czyje tweety są pokazywane. *Po wyłączeniu (NIE):* Nagłówek zostanie ukryty, co spowoduje bardziej kompaktowy widżet, ale potencjalnie mniej jasny kontekst. **Zalecana wartość:** `TAK` dla przejrzystości, chyba że potrzebujesz bardzo minimalistycznego projektu. **Scenariusz / przykład dla sprzedawcy:** Jeśli widżet znajduje się w widocznym miejscu, `TAK` jest dobre. Jeśli jest to mały widżet w zatłoczonym obszarze, `NIE` może zaoszczędzić miejsce. |
| **Wyświetl stopkę** | `TAK` | **Co robi to ustawienie:** Kontroluje, czy sekcja stopki widżetu Twittera (zazwyczaj pokazująca link „Wyświetl na Twitterze”) jest widoczna. **Efekt zmiany tego ustawienia:** *Po włączeniu (TAK):* Stopka zostanie wyświetlona, zapewniając bezpośredni link dla użytkowników do odwiedzenia Twojego pełnego profilu Twittera. *Po wyłączeniu (NIE):* Stopka zostanie ukryta, co sprawi, że widżet będzie bardziej kompaktowy. **Zalecana wartość:** `TAK`, aby zachęcić użytkowników do śledzenia Cię na Twitterze. **Scenariusz / przykład dla sprzedawcy:** Utrzymanie `TAK` pomaga kierować ruch na Twój profil Twittera. |
| **Wyświetl obramowanie** | `TAK` | **Co robi to ustawienie:** Kontroluje, czy wokół widżetu Twittera wyświetlane jest obramowanie. **Efekt zmiany tego ustawienia:** *Po włączeniu (TAK):* Obramowanie otoczy widżet, pomagając mu wyróżnić się z otaczającej treści. *Po wyłączeniu (NIE):* Widżet nie będzie miał widocznego obramowania, lepiej wtapiając się w tło. **Zalecana wartość:** `TAK` dla lepszego wizualnego rozdzielenia, zwłaszcza w kolumnach. **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja strona ma dużo treści, obramowanie pomaga zdefiniować przestrzeń widżetu. Jeśli chcesz bardzo czystego, zintegrowanego wyglądu, `NIE` może być preferowane. |
| **Wyświetl pasek przewijania** | `TAK` | **Co robi to ustawienie:** Kontroluje, czy w widżecie pojawia się pasek przewijania, jeśli zawartość (tweety) przekracza ustawioną wysokość. **Efekt zmiany tego ustawienia:** *Po włączeniu (TAK):* Pojawi się pasek przewijania, umożliwiając użytkownikom przewijanie wszystkich załadowanych tweetów w ramach ustalonej wysokości. *Po wyłączeniu (NIE):* Nie pojawi się pasek przewijania. Jeśli tweety przekroczą wysokość, zostaną obcięte lub widżet może się rozszerzyć (w zależności od innych ustawień i zachowania przeglądarki). Zazwyczaj nie jest to zalecane, ponieważ ukrywa zawartość. **Zalecana wartość:** `TAK`, aby zapewnić dostępność wszystkich tweetów. **Scenariusz / przykład dla sprzedawcy:** Zawsze utrzymuj `TAK`, chyba że chcesz wyświetlać tylko 1-2 tweety i nigdy nie chcesz przewijania. |
| **Przezroczyste tło** | `TAK` | **Co robi to ustawienie:** Kontroluje, czy tło widżetu Twittera jest przezroczyste. **Efekt zmiany tego ustawienia:** *Po włączeniu (TAK):* Tło widżetu będzie przezroczyste, umożliwiając wyświetlanie koloru lub obrazu tła Twojego sklepu. *Po wyłączeniu (NIE):* Widżet będzie miał jednolite tło (białe dla motywu `light`, ciemne dla motywu `dark`), potencjalnie tworząc wygląd pudełkowy. **Zalecana wartość:** `TAK` dla lepszej integracji z Twoim motywem. **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój sklep ma teksturowane tło lub określony kolor tła, `TAK` sprawi, że widżet będzie wyglądał jak naturalna część Twojego projektu. |
| **Pokaż odpowiedzi** | `TAK` | **Co robi to ustawienie:** Kontroluje, czy odpowiedzi na tweety są uwzględniane na osi czasu. **Efekt zmiany tego ustawienia:** *Po włączeniu (TAK):* Odpowiedzi zostaną wyświetlone, zapewniając pełniejszy kontekst rozmowy. *Po wyłączeniu (NIE):* Wyświetlane będą tylko oryginalne tweety i retweety, co sprawi, że oś czasu będzie potencjalnie czystsza, ale mniej konwersacyjna. **Zalecana wartość:** `TAK` dla bardziej aktywnego i angażującego kanału. **Scenariusz / przykład dla sprzedawcy:** Jeśli często angażujesz się w rozmowy z klientami poprzez odpowiedzi, `TAK` jest ważne, aby pokazać tę interakcję. Jeśli Twój kanał służy wyłącznie do ogłoszeń, `NIE` może być preferowane. |
| **Autoodtwarzanie wideo** | `NIE` | **Co robi to ustawienie:** Kontroluje, czy filmy osadzone w tweetach w widżecie będą odtwarzane automatycznie. **Efekt zmiany tego ustawienia:** *Po włączeniu (TAK):* Filmy zaczną odtwarzać się automatycznie, gdy pojawią się w widoku. Może to być angażujące, ale może zużywać przepustowość i irytować niektórych użytkowników. *Po wyłączeniu (NIE):* Filmy będą wymagały kliknięcia użytkownika, aby je odtworzyć. **Zalecana wartość:** `NIE`, aby uniknąć zaskakiwania klientów dźwiękiem lub zużywania ich danych bez zgody. **Scenariusz / przykład dla sprzedawcy:** Ogólnie `NIE` jest lepsze dla doświadczenia użytkownika. Jeśli masz bardzo konkretny, cichy, krótki film, który chcesz wyróżnić, możesz rozważyć `TAK`, ale postępuj ostrożnie. |
| **Ukryj pasek przewijania** | `NIE` | **Co robi to ustawienie:** To ustawienie jest prawdopodobnie zbędne lub sprzeczne z „Wyświetl pasek przewijania”. Ogólnie, jeśli „Wyświetl pasek przewijania” jest TAK, to ustawienie powinno być NIE. **Efekt zmiany tego ustawienia:** *Po włączeniu (TAK):* Próbuje ukryć pasek przewijania. Może to prowadzić do niedostępności treści, jeśli wysokość jest stała, a tweety ją przekraczają. *Po wyłączeniu (NIE):* Pozwala na widoczność paska przewijania, jeśli „Wyświetl pasek przewijania” jest również TAK. **Zalecana wartość:** `NIE`, aby zapewnić stałą dostępność treści. **Scenariusz / przykład dla sprzedawcy:** Zawsze utrzymuj `NIE` w połączeniu z `Wyświetl pasek przewijania: TAK`. |
| **Umieść w haku** | `displayRightColumn` | **Co robi to ustawienie:** Określa, gdzie w Twoim sklepie PrestaShop zostanie wyświetlony widżet Twittera. **Efekt zmiany tego ustawienia:** *Po ustawieniu na `displayRightColumn` (domyślne):* Widżet pojawi się w prawej kolumnie bocznej. *Po ustawieniu na `displayLeftColumn` (jeśli dostępne):* Widżet pojawi się w lewej kolumnie bocznej. *Po ustawieniu na `displayFooter` (jeśli dostępne):* Widżet pojawi się w sekcji stopki. *Po ustawieniu na `displayHeader` (jeśli dostępne):* Widżet pojawi się w sekcji nagłówka. *Po ustawieniu na `displayProductButtons` lub podobne (jeśli dostępne):* Widżet pojawi się na stronach produktów. **Zalecana wartość:** `displayRightColumn` lub `displayLeftColumn` dla ogólnej widoczności, `displayFooter` dla mniej inwazyjnego umiejscowienia. Wybierz na podstawie układu Twojego motywu i miejsca, w którym chcesz przyciągnąć uwagę. **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój motyw ma widoczną prawą kolumnę boczną, `displayRightColumn` jest dobrym wyborem. Jeśli chcesz, aby był widoczny na każdej stronie, ale nie zajmował dużo miejsca, `displayFooter` jest odpowiedni. |

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|
| Konfiguracja modułu | Nazwa użytkownika Twittera | Twoja nazwa użytkownika X | Określa konto, z którego mają być wyświetlane tweety. |
| Konfiguracja modułu | ID widżetu | Puste | Zaawansowane: Użyj dla niestandardowych widżetów generowanych przez Twittera. |
| Konfiguracja modułu | Motyw | `light` | Wizualny motyw widżetu (jasny/ciemny). |
| Konfiguracja modułu | Kolor linków | Puste | Dostosowuje kolory linków w widżecie. |
| Konfiguracja modułu | Kolor obramowania | Puste | Dostosowuje kolor obramowania widżetu. |
| Konfiguracja modułu | Limit tweetów | `20` | Maksymalna liczba tweetów do wyświetlenia. |
| Konfiguracja modułu | Wysokość | `300` | Stała wysokość widżetu w pikselach. |
| Konfiguracja modułu | Szerokość | Puste | Stała szerokość widżetu w pikselach (pozostaw puste dla responsywności). |
| Konfiguracja modułu | Język | `en` | Język interfejsu widżetu. |
| Konfiguracja modułu | Wyświetl nagłówek | `TAK` | Pokaż/ukryj nagłówek widżetu (nazwa konta). |
| Konfiguracja modułu | Wyświetl stopkę | `TAK` | Pokaż/ukryj stopkę widżetu (link Wyświetl na Twitterze). |
| Konfiguracja modułu | Wyświetl obramowanie | `TAK` | Pokaż/ukryj zewnętrzne obramowanie widżetu. |
| Konfiguracja modułu | Wyświetl pasek przewijania | `TAK` | Pokaż/ukryj wewnętrzny pasek przewijania dla tweetów. |
| Konfiguracja modułu | Przezroczyste tło | `TAK` | Ustaw tło widżetu jako przezroczyste. |
| Konfiguracja modułu | Pokaż odpowiedzi | `TAK` | Włącz/wyłącz odpowiedzi na osi czasu. |
| Konfiguracja modułu | Autoodtwarzanie wideo | `NIE` | Autoodtwarzanie filmów w tweetach. |
| Konfiguracja modułu | Ukryj pasek przewijania | `NIE` | (Zbędne z Wyświetl pasek przewijania) Utrzymaj NIE. |
| Konfiguracja modułu | Umieść w haku | `displayRightColumn` | Gdzie widżet pojawia się w Twoim sklepie. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Mój widżet Twittera nie wyświetla się w moim sklepie. Co powinienem zrobić?**
O:

1.  **Sprawdź konfigurację:** Przejdź do **Moduły > Menedżer modułów > Darmowy widżet Twittera > Konfiguruj**. Upewnij się, że wprowadziłeś poprawną „Nazwę użytkownika Twittera” i zapisałeś ustawienia.
2.  **Sprawdź umiejscowienie haka:** Zweryfikuj, czy ustawienie „Umieść w haku” jest ustawione na hak, który jest faktycznie renderowany przez Twój motyw (np. `displayRightColumn`). Niektóre motywy mogą nie wyświetlać wszystkich standardowych haków.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami pamięć podręczna PrestaShop uniemożliwia natychmiastowe pojawienie się nowej zawartości modułu.
4.  **Kompatybilność z motywem:** Chociaż moduł jest szeroko kompatybilny, bardzo mocno dostosowane motywy mogą wymagać drobnych korekt. Jeśli problem nadal występuje, skontaktuj się z pomocą techniczną MyPresta.eu.

**P: Widżet pojawia się, ale jest pusty lub wyświetla komunikat o błędzie.**
O:

1.  **Nieprawidłowa nazwa użytkownika:** Dokładnie sprawdź swoją „Nazwę użytkownika Twittera” w konfiguracji modułu. Nawet mała literówka uniemożliwi pobieranie tweetów.
2.  **Konto prywatne:** Upewnij się, że Twoje konto Twitter jest publiczne. Widżet nie może wyświetlać tweetów z kont prywatnych (chronionych).
3.  **Problemy z API Twittera:** Czasami mogą występować tymczasowe problemy z własnym API Twittera. Poczekaj chwilę i sprawdź ponownie.

**P: Jak zmienić język widżetu?**
O: W konfiguracji modułu znajdź ustawienie „Język” i wybierz odpowiedni dwuliterowy kod języka (np. `fr` dla francuskiego, `es` dla hiszpańskiego).

**P: Widżet wygląda na zbyt szeroki/wąski lub zbyt wysoki/niski.**
O:

1.  **Szerokość:** Aby uzyskać responsywne zachowanie, pozostaw ustawienie „Szerokość” puste. Jeśli ustawiłeś konkretną wartość w pikselach, spróbuj ją usunąć.
2.  **Wysokość:** Dostosuj ustawienie „Wysokość” (w pikselach), aby widżet był wyższy lub niższy.
3.  **Limit tweetów:** Zmniejsz „Limit tweetów”, aby widżet był krótszy, jeśli masz stałą wysokość i chcesz wyświetlać mniej tweetów.

**P: Czy mogę wyświetlać tweety z konkretnego hashtagu lub listy zamiast z mojego głównego konta?**
O: Tak, ale wymaga to zaawansowanej konfiguracji. Musiałbyś utworzyć niestandardowy osadzony widżet osi czasu bezpośrednio na platformie deweloperskiej Twittera (developer.twitter.com), skonfigurować go tam, aby wyświetlał hashtag lub listę, a następnie uzyskać unikalny „ID widżetu”, który on udostępnia. Następnie wprowadziłbyś ten „ID widżetu” do konfiguracji modułu, pozostawiając „Nazwę użytkownika Twittera” pustą.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Darmowy widżet Twittera” to prosty moduł PrestaShop zaprojektowany do integracji funkcji osadzonej osi czasu Twittera. Wykorzystuje on głównie standardową strukturę modułów PrestaShop, używając głównego pliku `index.php` zarówno do instalacji/deinstalacji, jak i konfiguracji (`getContent()`). Moduł wstrzykuje widżet Twittera oparty na JavaScript do front-office za pomocą szablonu Smarty i pliku CSS do podstawowego stylizowania. Opiera się na własnym `widgets.js` Twittera do renderowania osi czasu, który jest ładowany asynchronicznie.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Wyświetlanie modułu w front-office jest obsługiwane w całości za pomocą haków i szablonu Smarty.
-   **Kontrolery Back-Office Admin**: Brak. Cała konfiguracja jest zarządzana za pomocą metody `getContent()` głównej klasy modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

-   W tym module nie ma niestandardowych klas ani definicji `ObjectModel`. Cała logika jest zawarta w głównym pliku `twitterwidget/index.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   W katalogu `views/js/` modułu nie ma bezpośrednio dołączonych niestandardowych plików JavaScript.
-   Moduł w dużym stopniu opiera się na oficjalnym skrypcie Twittera `widgets.js`, który jest dynamicznie ładowany w szablonie front-office (`rightcolumn.tpl`) w celu renderowania osadzonej osi czasu. Ten skrypt obsługuje całą złożoną logikę pobierania tweetów i ich wyświetlania.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `twitterwidget/twitterwidget.css`:
    -   **Zakres**: Stylizacja dla klienta w front-office.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje**: Ten plik prawdopodobnie zawiera minimalną stylizację, głównie w celu zapewnienia, że widżet Twittera dobrze integruje się z różnymi motywami PrestaShop. Może zawierać reguły dla kontenera `.twitter-widget`, podstawowe resetowanie lub responsywne dostosowania.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać**: Programiści mogą sprawdzić ten plik, aby zidentyfikować konkretne selektory (np. `.twitter-widget-container`, `.twitter-timeline`) i nadpisać je w pliku `custom.css` lub `theme.css` swojego motywu, aby dalej dostosować wygląd widżetu.

### 4.6 Struktura szablonu Smarty (`views/templates/`)

-   **Szablony haków (`views/templates/hook/`)**:
    -   `twitterwidget/rightcolumn.tpl`:
        -   **Hak(i) renderowane w**: Ten szablon jest zaprojektowany do renderowania w różnych hakach wyświetlania, zgodnie z konfiguracją sprzedawcy (np. `displayRightColumn`, `displayLeftColumn`, `displayFooter`, `displayHeader`, `displayProductButtons`). Metody `hookDisplay*` modułu wywołają ten szablon.
        -   **Wyjście bloku wizualnego**: Ten szablon wyprowadza strukturę HTML wymaganą dla osadzonej osi czasu Twittera. Zazwyczaj zawiera tag `<a>` z atrybutami `data-` (np. `data-tweet-limit`, `data-theme`, `data-link-color`, `data-border-color`, `data-height`, `data-width`, `data-lang`, `data-chrome`, `data-dnt`, `data-show-replies`, `data-autoplay`), które skrypt `widgets.js` Twittera odczytuje w celu renderowania osi czasu. Zawiera również tag `<script>` do asynchronicznego ładowania `widgets.js`.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:
    -   Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration` przy użyciu standardowych kluczy konfiguracji PrestaShop (np. `TWITTERWIDGET_USERNAME`, `TWITTERWIDGET_WIDGETID`, `TWITTERWIDGET_THEME` itp.).
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Potencjalnie używany do globalnego ładowania skryptu widżetu Twittera lub do wyświetlania widżetu w obszarze nagłówka. |
| `displayRightColumn` | W prawej kolumnie bocznej stron, które ją posiadają. | Wyświetla widżet Twittera w prawej kolumnie. |
| `displayLeftColumn` | W lewej kolumnie bocznej stron, które ją posiadają. | Wyświetla widżet Twittera w lewej kolumnie. |
| `displayFooter` | W sekcji stopki każdej strony. | Wyświetla widżet Twittera w stopce. |
| `displayProductButtons` | Na stronie produktu, zazwyczaj w pobliżu przycisku dodawania do koszyka lub opisu produktu. | Wyświetla widżet Twittera na stronach produktów. |
| `actionFrontControllerSetMedia` | Po tym, jak kontroler front-office ustawi swoje media, umożliwiając modułom dodawanie własnych. | Używany do rejestrowania plików CSS modułu i potencjalnie plików JS (chociaż ten moduł ładuje JS Twittera bezpośrednio w TPL). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Darmowy widżet Twittera”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań.
