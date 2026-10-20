---
title: "Czat Facebook Messenger - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu czatu Facebook Messenger PrestaShop od MyPresta.eu."
sidebar:
  label: "Czat Facebook Messenger - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook Messenger chat na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-messenger-chat.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-messenger-chat/)
>
> ---


# Czat Facebook Messenger

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zazwyczaj dostępne we wszystkich nowoczesnych środowiskach hostingowych. Dla tego modułu nie są potrzebne żadne specjalne rozszerzenia poza standardowymi wymaganiami PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest główny ekran konfiguracji modułu czatu Facebook Messenger. Znajdziesz tutaj wszystkie opcje, aby dostosować wygląd i działanie czatu w Twoim sklepie.

-   **Co robi to ustawienie:** Jest to ogólne ustawienie dla modułów MyPresta.eu do sprawdzania aktualizacji.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone (Włączone):* Moduł będzie okresowo sprawdzał MyPresta.eu pod kątem nowych wersji.
    -   *Gdy wyłączone (Wyłączone):* Moduł nie będzie sprawdzał aktualizacji.
-   **Zalecana wartość:** **Włączone** (Zawsze dobrze jest być na bieżąco z aktualizacjami dla bezpieczeństwa i nowych funkcji).
-   **Scenariusz/przykład dla sprzedawcy:** Pozostawienie tego włączonego zapewnia powiadomienie o dostępności nowej wersji z poprawkami błędów lub nowymi funkcjami, pomagając Twojemu sklepowi pozostać aktualnym i bezpiecznym.

---

-   **Co robi to ustawienie:** Ta opcja pozwala wybrać między dwoma typami integracji czatu Facebook: prostym czatem Strony na Facebooku lub bardziej zaawansowanym czatem Facebook Messenger.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione na „Czat Strony na Facebooku”:* Pojawi się prostszy widżet czatu, głównie do wysyłania wiadomości na Twoją Stronę na Facebooku.
    -   *Gdy ustawione na „Czat Facebook Messenger”:* Pojawi się pełnowartościowy widżet czatu Facebook Messenger, oferujący bogatsze doświadczenie rozmowy, w tym wiadomości powitalne i potencjalnie bardziej zaawansowane funkcje z Facebooka.
-   **Zalecana wartość:** **Czat Facebook Messenger** (Oferuje lepsze doświadczenie użytkownika i więcej funkcji).
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz pełnego, interaktywnego doświadczenia Messengera z wiadomościami powitalnymi, wybierz „Czat Facebook Messenger”. Jeśli wolisz bardzo podstawowy, lekki nadawca wiadomości, „Czat Strony na Facebooku” może być wystarczający.

---

-   **Co robi to ustawienie:** To ustawienie pomaga poprawić wyniki wydajności Twojego sklepu w narzędziach takich jak Google PageSpeed Insights, zapobiegając natychmiastowemu ładowaniu czatu Facebook, co czasami może blokować renderowanie Twojej strony.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone (Włączone):* Skrypt czatu Facebook załaduje się z niewielkim opóźnieniem lub w sposób nieblokujący, co może poprawić Twoje wyniki Google PageSpeed.
    -   *Gdy wyłączone (Wyłączone):* Skrypt czatu Facebook załaduje się normalnie, co może nieznacznie wpłynąć na metryki wydajności ładowania strony.
-   **Zalecana wartość:** **Włączone** (Zalecane dla lepszego SEO i doświadczenia użytkownika).
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli zależy Ci na metrykach wydajności Twojego sklepu i chcesz mieć pewność, że czat nie wpłynie na nie negatywnie, włącz tę opcję.

---

-   **Co robi to ustawienie:** Kontroluje, czy Facebook Application SDK (Software Development Kit) jest dołączony do Twojej witryny. SDK jest niezbędne do pełnej funkcjonalności czatu Facebook Messenger, zwłaszcza dla funkcji takich jak identyfikacja zalogowanych użytkowników.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone (Włączone):* Facebook SDK zostanie załadowane, umożliwiając wszystkie funkcje czatu Messenger.
    -   *Gdy wyłączone (Wyłączone):* Niektóre zaawansowane funkcje Messengera, zwłaszcza te związane z identyfikacją użytkownika i spersonalizowanymi powitaniami, mogą nie działać poprawnie.
-   **Zalecana wartość:** **Włączone** (Wymagane do pełnej funkcjonalności czatu Messenger).
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz, aby czat rozpoznawał, czy klient jest zalogowany na Facebooku i wyświetlał spersonalizowane powitanie, musisz włączyć tę opcję.

---

-   **Co robi to ustawienie:** To jest Twój unikalny identyfikator dla Twojej aplikacji Facebook. Musisz utworzyć aplikację Facebook na stronie Facebook Developers, aby uzyskać ten identyfikator. Łączy on Twoją witrynę z Twoją Stroną na Facebooku dla zaawansowanych funkcji Messengera.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy poprawnie wprowadzony:* Umożliwia pełną funkcjonalność czatu Facebook Messenger, w tym spersonalizowane powitania i potencjalnie dokładniejszą identyfikację użytkownika.
    -   *Gdy niepoprawny lub pusty:* Czat Messenger może nie działać poprawnie lub wcale.
-   **Zalecana wartość:** Twój rzeczywisty **ID aplikacji Facebook**. (Pozostaw puste, jeśli „Dołącz SDK aplikacji Facebook” jest wyłączone).
-   **Scenariusz/przykład dla sprzedawcy:** Aby korzystać z zaawansowanych funkcji czatu Messenger, musisz przejść do [developers.facebook.com](https://developers.facebook.com/), utworzyć aplikację, połączyć ją ze swoją Stroną na Facebooku, a następnie skopiować ID aplikacji tutaj.

---

-   **Co robi to ustawienie:** Pozwala określić język interfejsu czatu Facebook Messenger.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy wybrany jest kod języka:* Widżet czatu będzie wyświetlał tekst (np. „Wyślij nam wiadomość”) w wybranym języku.
    -   *Gdy pozostawiony pusty lub niepoprawny:* Czat może domyślnie używać języka angielskiego lub języka przeglądarki.
-   **Zalecana wartość:** Wybierz podstawowy język swojego sklepu, np. `en_US` dla angielskiego (Stany Zjednoczone), `fr_FR` dla francuskiego (Francja), `es_ES` dla hiszpańskiego (Hiszpania).
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój sklep obsługuje głównie klientów w Niemczech, ustawienie tego na `de_DE` zapewni, że interfejs czatu będzie w języku niemieckim, co uczyni go bardziej przyjaznym dla lokalnych klientów.

---

-   **Co robi to ustawienie:** To jest adres URL Twojej Strony Fanowskiej na Facebooku. Jest to kluczowe, ponieważ informuje widżet czatu, gdzie wysyłać wiadomości.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy poprawnie wprowadzony:* Wiadomości wysłane przez widżet czatu trafią bezpośrednio do skrzynki odbiorczej Twojej Strony na Facebooku.
    -   *Gdy niepoprawny lub pusty:* Widżet czatu nie będzie mógł połączyć się z Twoją stroną, a wiadomości nie zostaną dostarczone.
-   **Zalecana wartość:** Pełny adres URL Twojej Strony Fanowskiej na Facebooku, np. `https://www.facebook.com/MyPresta.eu`.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoja Strona na Facebooku to `https://www.facebook.com/MyAwesomeStore/`, wpiszesz ten adres URL tutaj, aby klienci mogli się z Tobą skontaktować.

---

-   **Co robi to ustawienie:** To jest początkowa wiadomość wyświetlana klientom, którzy są już zalogowani na Facebooku, gdy otwierają czat.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione:* Zalogowani klienci zobaczą to spersonalizowane powitanie, co sprawi, że interakcja będzie bardziej przyjazna.
    -   *Gdy puste:* Może zostać użyte domyślne powitanie Facebooka lub nie pojawi się żadne powitanie.
-   **Zalecana wartość:** Przyjazne, zwięzłe powitanie, np. „Witaj [Imię Klienta], jak możemy Ci dzisiaj pomóc?”
-   **Scenariusz/przykład dla sprzedawcy:** Możesz ustawić to na „Witaj ponownie! Jak możemy Ci pomóc w dzisiejszych zakupach?”, aby powracający klienci czuli się docenieni.

---

-   **Co robi to ustawienie:** To jest początkowa wiadomość wyświetlana klientom, którzy NIE są zalogowani na Facebooku, gdy otwierają czat.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione:* Niezalogowani klienci zobaczą to powitanie, zachęcając ich do rozpoczęcia rozmowy.
    -   *Gdy puste:* Może zostać użyte domyślne powitanie Facebooka lub nie pojawi się żadne powitanie.
-   **Zalecana wartość:** Jasna, zachęcająca wiadomość, np. „Witaj! Jesteśmy tutaj, aby pomóc. Zapytaj nas o wszystko!”
-   **Scenariusz/przykład dla sprzedawcy:** Dla nowych odwiedzających możesz użyć „Witaj! Masz pytanie o nasze produkty? Porozmawiaj z nami!”

---

-   **Co robi to ustawienie:** To jest numeryczny identyfikator Twojej Strony na Facebooku. Możesz go znaleźć w sekcji „Informacje” Twojej Strony na Facebooku lub za pomocą narzędzia do wyszukiwania ID Strony na Facebooku. Jest to niezbędne do połączenia widżetu czatu z Twoją konkretną stroną.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy poprawnie wprowadzony:* Widżet czatu poprawnie zidentyfikuje i połączy się z Twoją Stroną na Facebooku.
    -   *Gdy niepoprawny lub pusty:* Widżet czatu nie będzie działał, ponieważ nie będzie wiedział, z którą stroną się połączyć.
-   **Zalecana wartość:** Twój rzeczywisty **ID Strony na Facebooku**.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli ID Twojej Strony na Facebooku to `123456789012345`, wpiszesz ten numer tutaj. Jest to odrębne od ID aplikacji.

---

-   **Co robi to ustawienie:** Kontroluje położenie widżetu czatu na Twojej stronie internetowej.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione na „Lewo”:* Ikona/panel czatu pojawi się po lewej stronie ekranu.
    -   *Gdy ustawione na „Prawo”:* Ikona/panel czatu pojawi się po prawej stronie ekranu.
-   **Zalecana wartość:** **Prawo** (Jest to powszechne i często mniej inwazyjne położenie, ponieważ wiele stron internetowych ma nawigację lub inne elementy po lewej stronie).
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli główna nawigacja Twojej witryny lub ważny baner znajduje się po lewej stronie, wybierzesz „Prawo”, aby uniknąć jego zasłaniania.

---

-   **Co robi to ustawienie:** To jest tekst, który pojawia się jako tytuł okna czatu lub wysuwanego panelu przed rozpoczęciem rozmowy.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawione:* Klienci zobaczą ten tytuł, jasno wskazujący, do czego służy czat.
    -   *Gdy puste:* Może zostać użyty domyślny tytuł lub nie pojawi się żaden tytuł, co może być mylące.
-   **Zalecana wartość:** Jasny i zachęcający tytuł, np. „Porozmawiaj z nami!”, „Obsługa klienta” lub „Pytania?”.
-   **Scenariusz/przykład dla sprzedawcy:** Ustawienie tego na „Potrzebujesz pomocy?” jasno informuje klientów, że mogą uzyskać pomoc za pośrednictwem czatu.

---

-   **Co robi to ustawienie:** Pozwala dostosować kolor tekstu w widżecie czatu Facebook.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy wprowadzony jest kod koloru:* Tekst w widżecie czatu będzie wyświetlany w wybranym kolorze.
    -   *Gdy puste:* Zostanie użyty domyślny kolor tekstu Facebook Messenger.
-   **Zalecana wartość:** Wybierz kolor, który dobrze kontrastuje z kolorem tła i pasuje do Twojej marki. Użyj szesnastkowego kodu koloru (np. `#FFFFFF` dla białego, `#000000` dla czarnego).
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli kolory Twojej marki to ciemnoniebieski i biały, możesz ustawić kolor czcionki na `#FFFFFF` (biały), jeśli kolor tła jest ciemnoniebieski.

---

-   **Co robi to ustawienie:** Pozwala dostosować kolor tła widżetu czatu Facebook.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy wprowadzony jest kod koloru:* Tło widżetu czatu będzie wyświetlane w wybranym kolorze.
    -   *Gdy puste:* Zostanie użyty domyślny kolor tła Facebook Messenger.
-   **Zalecana wartość:** Wybierz kolor, który uzupełnia projekt Twojego sklepu. Użyj szesnastkowego kodu koloru (np. `#F0F2F5` dla jasnoszarego, `#3B5998` dla niebieskiego Facebooka).
-   **Scenariusz/przykład dla sprzedawcy:** Aby bezproblemowo zintegrować czat z projektem Twojego sklepu, możesz ustawić kolor tła na subtelny szary lub kolor z palety Twojej marki.

---

-   **Co robi to ustawienie:** Pozwala dostosować główny kolor akcentu czatu Facebook Messenger, taki jak przycisk wysyłania lub aktywne elementy.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy wprowadzony jest kod koloru:* Kluczowe interaktywne elementy w widżecie czatu będą wyświetlane w wybranym kolorze.
    -   *Gdy puste:* Zostanie użyty domyślny kolor akcentu Facebook Messenger (zazwyczaj niebieski Facebooka).
-   **Zalecana wartość:** Wybierz kolor, który jest zgodny z głównym lub wtórnym kolorem akcentu Twojej marki. Użyj szesnastkowego kodu koloru (np. `#1877F2` dla niebieskiego Facebooka lub koloru wezwania do działania Twojej marki).
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli przyciski wezwania do działania w Twoim sklepie są zielone, ustawienie tego na podobny zielony (`#28A745`) sprawi, że widżet czatu będzie bardziej zintegrowany z Twoją witryną.

---

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Aktualizacje MyPresta.eu | Włączone | Włącza sprawdzanie aktualizacji modułu dla bezpieczeństwa i funkcji. |
| Konfiguracja modułu | Typ czatu | Czat Facebook Messenger | Wybiera między podstawowym czatem Strony na Facebooku a pełnym doświadczeniem Messengera. |
| Konfiguracja modułu | Wyłącz czat dla Google Insights | Włączone | Poprawia wyniki PageSpeed poprzez opóźnienie ładowania skryptu czatu. |
| Konfiguracja modułu | Dołącz SDK aplikacji Facebook | Włączone | Włącza zaawansowane funkcje Messengera, takie jak spersonalizowane powitania. |
| Konfiguracja modułu | Twój ID aplikacji | Twój ID aplikacji Facebook | Łączy Twoją witrynę z Twoją aplikacją Facebook dla pełnej funkcjonalności Messengera. |
| Konfiguracja modułu | Kody języków aplikacji Facebook | `pl_PL` (lub język Twojego sklepu) | Ustawia język interfejsu czatu. |
| Konfiguracja modułu | Adres URL do strony fanowskiej Facebook (odbiorca wiadomości) | Adres URL Twojej Strony na Facebooku | Kieruje wiadomości klientów do skrzynki odbiorczej Twojej Strony na Facebooku. |
| Konfiguracja modułu | Wiadomość powitalna dla zalogowanych | „Witaj [Imię Klienta], jak możemy Ci dzisiaj pomóc?” | Spersonalizowane powitanie dla użytkowników zalogowanych na Facebooku. |
| Konfiguracja modułu | Wiadomość powitalna dla niezalogowanych | „Witaj! Jesteśmy tutaj, aby pomóc. Zapytaj nas o wszystko!” | Zachęcająca wiadomość dla użytkowników niezalogowanych na Facebooku. |
| Konfiguracja modułu | Twój ID strony na Facebooku | Twój ID strony na Facebooku | Identyfikuje Twoją konkretną Stronę na Facebooku dla połączenia czatu. |
| Konfiguracja modułu | Gdzie wyświetlić? | Prawo | Pozycjonuje widżet czatu po lewej lub prawej stronie ekranu. |
| Konfiguracja modułu | Tytuł wysuwanego panelu | „Porozmawiaj z nami!” | Tekst wyświetlany jako tytuł okna czatu. |
| Konfiguracja modułu | Kolor czcionki czatu Facebook | `#000000` (czarny) lub kolor Twojej marki | Dostosowuje kolor tekstu w widżecie czatu. |
| Konfiguracja modułu | Kolor tła czatu Facebook | `#F0F2F5` (jasnoszary) lub kolor Twojej marki | Dostosowuje kolor tła widżetu czatu. |
| Konfiguracja modułu | Kolor Facebook Messenger | `#1877F2` (niebieski Facebooka) lub kolor Twojej marki | Dostosowuje kolor akcentu interaktywnych elementów czatu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Widżet czatu nie pojawia się w moim sklepie. Co powinienem zrobić?**
O:

1.  **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że moduł „Czat Facebook Messenger” jest zainstalowany i włączony.
2.  **Zweryfikuj konfigurację:** Dokładnie sprawdź wszystkie ustawienia na stronie konfiguracji modułu, zwłaszcza „Twój ID aplikacji”, „Adres URL do strony fanowskiej Facebook” i „Twój ID strony na Facebooku”. Nawet jeden niepoprawny znak może uniemożliwić jego działanie.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stare pliki pamięci podręcznej uniemożliwiają wyświetlanie nowych modułów.
4.  **Kompatybilność z motywem:** Jeśli używasz bardzo spersonalizowanego motywu, może wystąpić konflikt. Tymczasowo przełącz się na domyślny motyw PrestaShop, aby sprawdzić, czy czat się pojawi. Jeśli tak, Twój motyw może wymagać niewielkiej korekty.

**P: Moje wiadomości powitalne nie wyświetlają się, lub czat nie rozpoznaje zalogowanych użytkowników.**
O:

1.  **Włącz SDK:** Upewnij się, że „Dołącz SDK aplikacji Facebook” jest ustawione na **Włączone**.
2.  **Podaj ID aplikacji:** Upewnij się, że „Twój ID aplikacji” jest poprawnie wprowadzony. Musisz utworzyć aplikację Facebook i połączyć ją ze swoją stroną, aby to uzyskać.
3.  **Logowanie na Facebooku:** Klient musi być zalogowany na Facebooku w swojej przeglądarce, aby spersonalizowane powitanie działało.

**P: Widżet czatu wygląda nie na miejscu lub nie pasuje do projektu mojego sklepu.**
O:

1.  **Użyj ustawień kolorów:** Przejdź do konfiguracji modułu i dostosuj „Kolor czcionki czatu Facebook”, „Kolor tła czatu Facebook” i „Kolor Facebook Messenger”, aby pasowały do palety Twojej marki.
2.  **Pozycjonowanie:** Eksperymentuj z ustawieniem „Gdzie wyświetlić?” (Lewo/Prawo), aby znaleźć najmniej inwazyjne położenie dla Twojej witryny.

**P: Jak znaleźć mój ID strony na Facebooku i ID aplikacji?**
O:

-   **ID strony na Facebooku:** Przejdź do swojej Strony na Facebooku, kliknij „Informacje” w lewym menu. Przewiń w dół, a powinieneś zobaczyć „ID strony”.
-   **ID aplikacji Facebook:** Musisz utworzyć konto dewelopera Facebook, a następnie utworzyć nową aplikację. Po utworzeniu ID aplikacji będzie widoczne w Twoim Panelu aplikacji. Upewnij się, że połączyłeś tę aplikację ze swoją Stroną na Facebooku.

**P: Czy ten moduł spowolni moją witrynę?**
O: SDK Facebooka może czasami wpływać na czasy ładowania strony. Jednak moduł zawiera opcję „Wyłącz czat dla Google Insights”. Włączenie tej opcji może pomóc złagodzić wpływ na wydajność poprzez ładowanie skryptu w sposób nieblokujący, poprawiając Twoje wyniki PageSpeed.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł `Facebook Messenger chat` (`fbchat`) to standardowy moduł PrestaShop, który stosuje wzorzec zbliżony do MVC w ramach swojego zakresu. Wykorzystuje głównie system hooków PrestaShop do wstrzykiwania JavaScriptu i HTML do front-office. Konfiguracja jest zarządzana za pomocą metody `getContent()` w głównej klasie modułu, przechowując ustawienia w `ps_configuration`. Moduł integruje się bezpośrednio z Facebook Messenger Platform SDK, opierając się na zewnętrznych zasobach Facebooka w zakresie swojej podstawowej funkcjonalności.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała logika jest obsługiwana w głównym pliku modułu (`fbchat.php`) i wstrzykiwana za pomocą hooków.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł **nie** definiuje żadnych niestandardowych klas ani instancji `ObjectModel` w katalogu `classes/`. Cała obsługa danych odbywa się bezpośrednio za pośrednictwem klasy `Configuration` dla ustawień.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`fbchat/jscolor/jscolor.js`**

    -   **Zakres:** Back-office (strona konfiguracji administratora).
    -   **Cel:** Jest to zewnętrzna biblioteka JavaScript do wyboru kolorów. Jest używana na stronie konfiguracji modułu, aby zapewnić przyjazny dla użytkownika interfejs do wybierania kolorów dla widżetu czatu (np. kolor czcionki, kolor tła).
    -   **Interakcja:** Dołącza funkcjonalność wyboru kolorów do określonych pól wejściowych w formularzu administratora.
-   **`fbchat/js/fbchat.js`**

    -   **Zakres:** Front-office.
    -   **Cel:** Ten niestandardowy JavaScript obsługuje dynamiczne ładowanie i inicjalizację widżetu czatu Facebook Messenger. Zawiera logikę warunkowego ładowania Facebook SDK i czatu Messenger w oparciu o ustawienia modułu i potencjalnie flagi optymalizacji wydajności.
    -   **Interakcja:**
        -   Sprawdza konfigurację `fbchat_hack`, aby określić, czy włączone jest opóźnione ładowanie dla Google Insights.
        -   Dynamicznie tworzy i dołącza skrypt Facebook SDK (`sdk.js`) do `<body>`, jeśli `fbchat_appsdk` jest włączone.
        -   Inicjalizuje wtyczkę `FB.CustomerChat` z parametrami pobranymi z konfiguracji modułu (np. `page_id`, `app_id`, `theme_color`, `logged_in_greeting`, `logged_out_greeting`, `locale`).
        -   Obsługuje pozycjonowanie widżetu czatu w oparciu o `fbchat_side`.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`fbchat/css.css`**

    -   **Zakres:** Back-office (strona konfiguracji administratora).
    -   **Cel:** Zawiera style specyficzne dla formularza konfiguracji modułu w Panelu administracyjnym PrestaShop. Może to obejmować style dla pól wejściowych, przycisków lub niestandardowych elementów układu w ramach wyjścia `getContent()`.
    -   **Kluczowe selektory:** Prawdopodobnie celuje w elementy w formularzu konfiguracji modułu.
-   **`fbchat/css/fbchat_left.css`**

    -   **Zakres:** Front-office.
    -   **Cel:** Zapewnia dostosowania stylów dla widżetu czatu Facebook Messenger, gdy jego pozycja jest ustawiona na „Lewą” stronę ekranu. Może to obejmować właściwości CSS `right` lub `left` do kontrolowania jego stałej pozycji.
    -   **Kluczowe selektory:** Celuje w główny kontener czatu lub jego wrapper, aby zapewnić prawidłowe wyrównanie do lewej strony.
-   **`fbchat/css/fbchat_right.css`**

    -   **Zakres:** Front-office.
    -   **Cel:** Zapewnia dostosowania stylów dla widżetu czatu Facebook Messenger, gdy jego pozycja jest ustawiona na „Prawą” stronę ekranu. Może to obejmować właściwości CSS `right` lub `left` do kontrolowania jego stałej pozycji.
    -   **Kluczowe selektory:** Celuje w główny kontener czatu lub jego wrapper, aby zapewnić prawidłowe wyrównanie do prawej strony.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`fbchat/admin-script.tpl`**

    -   **Zakres:** Back-office (strona konfiguracji administratora).
    -   **Cel:** Ten szablon jest prawdopodobnie używany do wstrzykiwania kodu JavaScript (np. do inicjalizacji wyboru kolorów z `jscolor.js`) lub specyficznych stylów na stronę konfiguracji modułu. Jest renderowany w metodzie `getContent()`.
    -   **Zmienne:** Może otrzymywać zmienne konfiguracyjne do dynamicznego ustawiania początkowych wartości wyboru kolorów.
-   **`fbchat/fbchat.tpl`**

    -   **Zakres:** Front-office.
    -   **Cel:** Jest to główny szablon front-office odpowiedzialny za renderowanie niezbędnej struktury HTML i inicjalizacji JavaScript dla widżetu czatu Facebook Messenger. Jest zazwyczaj podłączony do `displayFooter` lub `displayHeader`.
    -   **Zmienne:** Otrzymuje wszystkie niezbędne zmienne konfiguracyjne z metod `hookDisplayFooter` lub `hookDisplayHeader` modułu, takie jak `fbchat_fanid`, `fbchat_appid`, `fbchat_theme`, `fbchat_bg`, `fbchat_color`, `fbchat_langarray`, `fbchat_hello_logged`, `fbchat_hello_unlogged`, `fbchat_hack`, `fbchat_appsdk`, `fbchat_type`, `fbchat_side`.
    -   **Wyjście:** Generuje element `<div class="fb-customerchat">` i tag `<script>` do inicjalizacji Facebook SDK.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `mypresta_updates`, `fbchat_theme`, `fbchat_bg`, `fbchat_color`, `fbchat_fanpage`, `fbchat_positions`, `fbchat_hack`, `fbchat_appsdk`, `fbchat_type`, `fbchat_fanid`, `fbchat_appid`, `fbchat_title`, `fbchat_langarray`, `fbchat_hello_logged`, `fbchat_hello_unlogged`, `fbchat_side`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony front-office. | Służy do dołączania plików CSS (`fbchat_left.css`, `fbchat_right.css`) i potencjalnie niektórych początkowych skryptów JavaScript, jeśli są potrzebne wcześnie podczas ładowania strony. |
| `displayFooter` | Wykonywany tuż przed zamykającym tagiem `</body>` każdej strony front-office. | Jest to główny hook do renderowania szablonu `fbchat.tpl`, który zawiera kod HTML czatu Facebook Messenger i inicjalizuje skrypt `fbchat.js`. Umieszczenie go tutaj zapewnia, że główna zawartość strony ładuje się najpierw, poprawiając postrzeganą wydajność. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i najnowszych wersji modułu „Czat Facebook Messenger” prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności lub integracji modułu.
"""
