---
title: "Facebook Fan Slider - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Facebook Fan Slider od MyPresta.eu."
sidebar:
  label: "Facebook Fan Slider - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook Fan Slider na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-fan-slider.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-fan-slider/)
>
> ---


# Facebook Fan Slider

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są wymagane dla samego PrestaShop i zazwyczaj dostępne we wszystkich nowoczesnych środowiskach hostingowych. Nie są potrzebne żadne specjalne konfiguracje serwera poza standardową konfiguracją PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj)

Aby uzyskać dostęp do ustawień modułu, przejdź do **Moduły > Menedżer modułów**, wyszukaj „Facebook Fan Slider” i kliknij przycisk „Konfiguruj”.

Oto szczegółowy opis każdego ustawienia:

-   **Adres URL strony na Facebooku (fs\_url)**

    *   **Co robi to ustawienie:** Jest to najważniejsze ustawienie. Informuje moduł, którą konkretną Stronę na Facebooku ma wyświetlać w wysuwanym oknie.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na adres URL Twojej Strony na Facebooku:* Moduł pobierze i wyświetli Like Box/Page Plugin dla tej konkretnej strony.
        *   *Gdy pozostawione puste lub ustawione nieprawidłowo:* Moduł albo nie wyświetli treści z Facebooka, albo pokaże błąd, ponieważ nie będzie wiedział, z którą stroną się połączyć.
    *   **Zalecana wartość:** Wprowadź pełny adres URL swojej Strony na Facebooku (np. `https://www.facebook.com/MyPresta.eu`).
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja strona biznesowa to `https://www.facebook.com/MyAwesomeShop`, wpiszesz ten adres URL tutaj.
-   **Szerokość (fs\_width)**

    *   **Co robi to ustawienie:** Kontroluje szerokość Like Boxa/Page Plugina Facebooka *wewnątrz* wysuwanego panelu, w pikselach.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na konkretną wartość w pikselach (np. 280):* Treść z Facebooka będzie miała dokładnie taką szerokość.
        *   *Gdy ustawione na mniejszą wartość:* Treść może wydawać się ściśnięta lub niektóre elementy mogą zostać obcięte.
        *   *Gdy ustawione na większą wartość:* Treść się rozszerzy, ale upewnij się, że nie przekracza szerokości ekranu ani nie wygląda nieproporcjonalnie.
    *   **Zalecana wartość:** Zacznij od `280` lub `300` pikseli. Dostosuj w zależności od ilości wyświetlanej treści (np. jeśli pokazujesz posty, możesz potrzebować większej szerokości).
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby wysuwane okno było wystarczająco szerokie, aby wyraźnie pokazać zdjęcie w tle Twojej strony i przycisk „Lubię to”, nie będąc zbyt masywnym.
-   **Wysokość (fs\_height)**

    *   **Co robi to ustawienie:** Kontroluje wysokość Like Boxa/Page Plugina Facebooka *wewnątrz* wysuwanego panelu, w pikselach.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na konkretną wartość w pikselach (np. 400):* Treść z Facebooka będzie miała dokładnie taką wysokość.
        *   *Gdy ustawione na mniejszą wartość:* Treść może zostać obcięta, wymagając od użytkowników przewijania wewnątrz okna.
        *   *Gdy ustawione na większą wartość:* Okno będzie wyższe, potencjalnie zajmując więcej miejsca na ekranie.
    *   **Zalecana wartość:** Zacznij od `400` lub `500` pikseli. Jeśli włączysz „Pokaż posty”, prawdopodobnie będziesz potrzebować większej wysokości (np. `600-700px`), aby wyświetlić kilka postów bez nadmiernego przewijania.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz pokazać kilka ostatnich postów ze swojej strony na Facebooku, więc zwiększasz wysokość do `600px`, aby były widoczne.
-   **Ukryj zdjęcie w tle (fs\_hide\_cover)**

    *   **Co robi to ustawienie:** Określa, czy duże zdjęcie w tle Twojej Strony na Facebooku jest wyświetlane na górze Like Boxa/Page Plugina.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone (zaznaczone):* Zdjęcie w tle nie będzie wyświetlane, co sprawi, że Like Box będzie bardziej kompaktowy.
        *   *Gdy wyłączone (niezaznaczone):* Zdjęcie w tle będzie wyświetlane, co sprawi, że Like Box będzie wizualnie bogatszy, ale także wyższy.
    *   **Zalecana wartość:** *Wyłączone* (niezaznaczone), jeśli chcesz bardziej atrakcyjnego wizualnie okna. *Włączone* (zaznaczone), jeśli musisz zaoszczędzić miejsce w pionie.
    *   **Scenariusz / przykład dla sprzedawcy:** Masz piękne zdjęcie w tle na Facebooku i chcesz je zaprezentować, więc pozostawiasz to niezaznaczone. Jeśli masz mało miejsca, możesz to zaznaczyć.
-   **Pokaż zdjęcia znajomych (fs\_show\_facepile)**

    *   **Co robi to ustawienie:** Kontroluje, czy zdjęcia profilowe znajomych, którzy już polubili Twoją stronę, są wyświetlane poniżej przycisku „Lubię to”.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone (zaznaczone):* Pojawi się rząd zdjęć profilowych wspólnych znajomych, którzy lubią Twoją stronę, dodając dowód społeczny.
        *   *Gdy wyłączone (niezaznaczone):* Te zdjęcia profilowe nie będą wyświetlane.
    *   **Zalecana wartość:** *Włączone* (zaznaczone). Dowód społeczny może zachęcić innych do polubienia Twojej strony.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz wykorzystać dowód społeczny, aby zachęcić do nowych polubień, więc włączasz to, aby pokazać znajomych, którzy już lubią Twoją stronę.
-   **Pokaż posty (fs\_show\_posts)**

    *   **Co robi to ustawienie:** Określa, czy ostatnie posty z osi czasu Twojej Strony na Facebooku są wyświetlane w Like Boxie/Page Pluginie.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone (zaznaczone):* Twoje najnowsze posty z Facebooka pojawią się, czyniąc okno bardziej dynamicznym i angażującym. Prawdopodobnie będziesz musiał zwiększyć ustawienie `Wysokość`.
        *   *Gdy wyłączone (niezaznaczone):* Wyświetlana będzie tylko podstawowa funkcja „Polub Stronę” i zdjęcia znajomych (jeśli włączone).
    *   **Zalecana wartość:** *Włączone* (zaznaczone), jeśli regularnie publikujesz angażujące treści i chcesz je zaprezentować. Pamiętaj o dostosowaniu `Wysokości`.
    *   **Scenariusz / przykład dla sprzedawcy:** Często publikujesz informacje o nowych produktach i promocjach na Facebooku. Włączenie tej opcji pozwala klientom zobaczyć Twoje najnowsze aktualizacje bezpośrednio ze sklepu.
-   **Ukryj wezwanie do działania (fs\_hide\_cta)**

    *   **Co robi to ustawienie:** Kontroluje widoczność przycisku „Wezwanie do działania” (np. „Wyślij wiadomość”, „Kup teraz”), który mogłeś skonfigurować na swojej Stronie na Facebooku.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone (zaznaczone):* Przycisk CTA nie będzie wyświetlany w Like Boxie.
        *   *Gdy wyłączone (niezaznaczone):* Przycisk CTA (jeśli skonfigurowany na Twojej Stronie na Facebooku) będzie widoczny.
    *   **Zalecana wartość:** *Wyłączone* (niezaznaczone), jeśli Twoje CTA jest istotne dla odwiedzających Twój sklep. *Włączone* (zaznaczone), jeśli wolisz skupić się tylko na uzyskiwaniu polubień.
    *   **Scenariusz / przykład dla sprzedawcy:** Twoja strona na Facebooku ma przycisk „Kup teraz”. Chcesz, aby klienci go używali, więc pozostawiasz to niezaznaczone.
-   **Mały nagłówek (fs\_small\_header)**

    *   **Co robi to ustawienie:** Używa mniejszej wersji nagłówka dla Like Boxa/Page Plugina Facebooka.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone (zaznaczone):* Obszar nagłówka Like Boxa będzie bardziej kompaktowy, oszczędzając miejsce w pionie.
        *   *Gdy wyłączone (niezaznaczone):* Użyty zostanie standardowy, większy nagłówek.
    *   **Zalecana wartość:** *Włączone* (zaznaczone), jeśli chcesz bardziej opływowego wyglądu lub potrzebujesz zaoszczędzić miejsce.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby wysuwane okno było jak najbardziej kompaktowe, nie ukrywając istotnych informacji, więc włączasz mały nagłówek.
-   **Wysuń po (fanslider\_slideon)**

    *   **Co robi to ustawienie:** Określa metodę interakcji, która powoduje wysunięcie okna Facebooka.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na „Kliknięcie” (Click):* Okno wysunie się tylko wtedy, gdy klient wyraźnie kliknie zakładkę.
        *   *Gdy ustawione na „Najechaniu” (Hover):* Okno wysunie się, gdy klient przesunie kursor myszy nad zakładką.
    *   **Zalecana wartość:** „Kliknięcie” jest zazwyczaj mniej inwazyjne i zapobiega przypadkowym wysunięciom. „Najechaniu” może być bardziej natychmiastowe, ale może irytować niektórych użytkowników.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz upewnić się, że suwak pojawia się tylko wtedy, gdy klient aktywnie zdecyduje się go zobaczyć, więc ustawiasz go na „Kliknięcie”.
-   **Pozycja (fs\_pos)**

    *   **Co robi to ustawienie:** Kontroluje, gdzie wysuwana zakładka pojawia się na Twojej stronie internetowej.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na „Lewo” (Left):* Zakładka pojawi się po lewej stronie okna przeglądarki.
        *   *Gdy ustawione na „Prawo” (Right):* Zakładka pojawi się po prawej stronie okna przeglądarki.
    *   **Zalecana wartość:** „Lewo” lub „Prawo”, w zależności od układu Twojego motywu i miejsca, w którym powoduje najmniejsze zakłócenia z innymi elementami.
    *   **Scenariusz / przykład dla sprzedawcy:** Twój motyw ma widżet czatu na żywo po prawej stronie, więc ustawiasz Facebook Fan Slider na „Lewo”, aby uniknąć konfliktów.
-   **Kolor tła (fs\_bg\_color)**

    *   **Co robi to ustawienie:** Ustawia kolor tła samego wysuwanego panelu (nie treści z Facebooka, ale kontenera, w którym się wysuwa).
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na konkretny kolor (np. #FFFFFF dla białego, #0000FF dla niebieskiego):* Tło wysuwanego okna zmieni się na ten kolor.
    *   **Zalecana wartość:** Kolor pasujący do brandingu Twojego sklepu lub neutralny kolor, taki jak biały (`#FFFFFF`) lub jasnoszary (`#F0F0F0`).
    *   **Scenariusz / przykład dla sprzedawcy:** Twoja marka używa konkretnego odcienia niebieskiego. Wprowadzasz kod szesnastkowy dla tego niebieskiego, aby upewnić się, że suwak pasuje do Twojej tożsamości marki.
-   **Kolor ramki (fs\_br\_color)**

    *   **Co robi to ustawienie:** Ustawia kolor ramki wokół wysuwanego panelu.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na konkretny kolor (np. #CCCCCC dla jasnoszarego):* Ramka wysuwanego okna zmieni się na ten kolor.
    *   **Zalecana wartość:** Subtelny kolor, który uzupełnia kolor tła, lub kolor pasujący do Twojej marki.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz subtelnej ramki wokół suwaka, więc wybierasz jasnoszary kolor (`#DDDDDD`).
-   **Język (fs\_langarray)**

    *   **Co robi to ustawienie:** Pozwala wybrać język dla Like Boxa/Page Plugina Facebooka. Zapewnia to, że przycisk „Polub Stronę” i inne teksty generowane przez Facebooka są w odpowiednim języku dla Twojej publiczności.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na konkretny język (np. „en\_US” dla angielskiego, „fr\_FR” dla francuskiego):* Plugin Facebooka zostanie wyświetlony w tym języku.
    *   **Zalecana wartość:** Wybierz podstawowy język swojego sklepu lub swojej grupy docelowej.
    *   **Scenariusz / przykład dla sprzedawcy:** Twój sklep obsługuje głównie klientów we Francji, więc wybierasz „fr\_FR”, aby wyświetlać treści z Facebooka po francusku.
-   **Dostosuj szerokość kontenera (fs\_adapt\_container\_width)**

    *   **Co robi to ustawienie:** Informuje Page Plugin Facebooka, aby dostosował swoją szerokość do szerokości swojego kontenera nadrzędnego (wysuwanego okna).
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone (zaznaczone):* Treść z Facebooka spróbuje wypełnić `Szerokość`, którą określiłeś dla wysuwanego okna, czyniąc ją responsywną w tym kontenerze.
        *   *Gdy wyłączone (niezaznaczone):* Treść z Facebooka może użyć swojej domyślnej szerokości, potencjalnie prowadząc do przepełnienia lub pustej przestrzeni, jeśli nie pasuje do Twojego ustawienia `Szerokości`.
    *   **Zalecana wartość:** *Włączone* (zaznaczone) dla lepszej responsywności i aby upewnić się, że treść z Facebooka dobrze pasuje do określonej `Szerokości`.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby treść z Facebooka automatycznie dostosowywała się do szerokości Twojego suwaka, więc włączasz to dla czystszego wyglądu.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Adres URL strony na Facebooku (fs\_url) | Adres URL Twojej strony na Facebooku | Określa, którą stronę na Facebooku wyświetlić. **KRYTYCZNE!** |
| Konfiguracja modułu | Szerokość (fs\_width) | 280-300px | Ustawia szerokość treści z Facebooka wewnątrz suwaka. |
| Konfiguracja modułu | Wysokość (fs\_height) | 400-500px (więcej, jeśli pokazujesz posty) | Ustawia wysokość treści z Facebooka wewnątrz suwaka. |
| Konfiguracja modułu | Ukryj zdjęcie w tle (fs\_hide\_cover) | Wyłączone (niezaznaczone) | Pokazuje/ukrywa duże zdjęcie w tle z Twojej strony na Facebooku. |
| Konfiguracja modułu | Pokaż zdjęcia znajomych (fs\_show\_facepile) | Włączone (zaznaczone) | Wyświetla zdjęcia profilowe znajomych, którzy lubią Twoją stronę (dowód społeczny). |
| Konfiguracja modułu | Pokaż posty (fs\_show\_posts) | Włączone (zaznaczone) | Wyświetla ostatnie posty z Twojej osi czasu na Facebooku. Wymaga większej wysokości. |
| Konfiguracja modułu | Ukryj wezwanie do działania (fs\_hide\_cta) | Wyłączone (niezaznaczone) | Pokazuje/ukrywa przycisk CTA skonfigurowany na Twojej stronie na Facebooku. |
| Konfiguracja modułu | Mały nagłówek (fs\_small\_header) | Włączone (zaznaczone) | Używa bardziej kompaktowego nagłówka dla wtyczki Facebooka. |
| Konfiguracja modułu | Wysuń po (fanslider\_slideon) | Kliknięcie | Określa, czy okno wysuwa się po „Kliknięciu” czy „Najechaniu”. „Kliknięcie” jest mniej inwazyjne. |
| Konfiguracja modułu | Pozycja (fs\_pos) | Lewo / Prawo | Ustawia stronę ekranu, na której pojawia się zakładka. |
| Konfiguracja modułu | Kolor tła (fs\_bg\_color) | Pasuje do motywu / Biały (#FFFFFF) | Ustawia kolor tła wysuwanego panelu. |
| Konfiguracja modułu | Kolor ramki (fs\_br\_color) | Subtelny szary (#DDDDDD) | Ustawia kolor ramki wysuwanego panelu. |
| Konfiguracja modułu | Język (fs\_langarray) | Podstawowy język Twojego sklepu | Ustawia język tekstu wtyczki Facebooka. |
| Konfiguracja modułu | Dostosuj szerokość kontenera (fs\_adapt\_container\_width) | Włączone (zaznaczone) | Sprawia, że treść z Facebooka jest responsywna do szerokości suwaka. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Suwak Facebooka nie pojawia się w moim sklepie. Co powinienem najpierw sprawdzić?**
O1:

-   **Moduł włączony:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że moduł „Facebook Fan Slider” jest zainstalowany i włączony.
-   **Adres URL strony na Facebooku:** Dokładnie sprawdź `Adres URL strony na Facebooku (fs_url)` w konfiguracji modułu. Upewnij się, że jest to *dokładny* adres URL Twojej strony na Facebooku (np. `https://www.facebook.com/MyPresta.eu`), a nie tylko Twój profil lub grupa.
-   **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (przejdź do **Zaawansowane > Wydajność**, a następnie kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu). Wyczyść również pamięć podręczną przeglądarki.
-   **Konflikty motywów:** Tymczasowo przełącz się na domyślny motyw PrestaShop, aby sprawdzić, czy suwak się pojawi. Jeśli tak, Twój niestandardowy motyw może mieć konflikty CSS lub JavaScript.

**P2: Treść z Facebooka wewnątrz suwaka wygląda na obciętą lub jest za mała/duża.**
O2:

-   **Szerokość i wysokość:** Dostosuj ustawienia `Szerokość (fs_width)` i `Wysokość (fs_height)` w konfiguracji modułu. Jeśli pokazujesz posty, na pewno będziesz potrzebować większej wysokości.
-   **Dostosuj szerokość kontenera:** Upewnij się, że `Dostosuj szerokość kontenera (fs_adapt_container_width)` jest włączone (zaznaczone). Pomaga to treści z Facebooka dopasować się responsywnie do suwaka.
-   **Mały nagłówek:** Jeśli próbujesz zaoszczędzić miejsce w pionie, spróbuj włączyć `Mały nagłówek (fs_small_header)`.

**P3: Język Like Boxa Facebooka jest nieprawidłowy.**
O3:

-   **Ustawienie języka:** Przejdź do konfiguracji modułu i sprawdź ustawienie `Język (fs_langarray)`. Wybierz prawidłowy kod języka dla swojej grupy docelowej (np. `en_US` dla angielskiego w USA, `fr_FR` dla francuskiego).

**P4: Zmieniłem ustawienia, ale nic nie dzieje się w front-office.**
O4:

-   **Zapisz zmiany:** Zawsze kliknij przycisk „Zapisz” po dokonaniu jakichkolwiek zmian w konfiguracji modułu.
-   **Wyczyść pamięć podręczną:** PrestaShop w dużym stopniu opiera się na buforowaniu. Po zapisaniu zawsze wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**) i pamięć podręczną przeglądarki. Jest to najczęstszy powód, dla którego zmiany nie pojawiają się natychmiast.

**P5: Suwak nakłada się na inny element na mojej stronie.**
O5:

-   **Pozycja:** Dostosuj ustawienie `Pozycja (fs_pos)` (Lewo lub Prawo), aby sprawdzić, czy przeniesienie suwaka na drugą stronę rozwiąże konflikt.
-   **Dostosowania CSS (potrzebny programista):** Jeśli problem nadal występuje, może to wymagać niestandardowych dostosowań CSS zarówno do suwaka, jak i do konfliktuującego elementu. Zazwyczaj zajmuje się tym webmaster lub programista.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł Facebook Fan Slider (`fanslider`) to standardowy moduł PrestaShop implementujący klasę `Module`. Wykorzystuje on głównie system hooków PrestaShop do wstrzykiwania swojego kodu HTML, CSS i JavaScript do front-office. Podstawowa funkcjonalność polega na wyświetlaniu oficjalnego Page Plugina Facebooka w niestandardowym, wysuwanym elemencie interfejsu użytkownika. Konfiguracja jest zarządzana za pomocą metody `getContent()`, przechowując ustawienia w `ps_configuration`. Moduł nie używa niestandardowych tabel baz danych ani klas `ObjectModel`.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery front-office**: Brak. Całe renderowanie i logika front-office są obsługiwane bezpośrednio w głównym pliku modułu (`fanslider.php`) za pośrednictwem hooków i wstrzykniętego JavaScriptu.
-   **Kontrolery administracyjne back-office**: Brak. Konfiguracja jest obsługiwana przez metodę `getContent()` głównej klasy modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

-   W katalogu `classes/` nie ma niestandardowych klas ani definicji `ObjectModel`. Logika modułu jest zawarta w `fanslider/fanslider.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł zawiera kilka plików JavaScript, głównie do animacji wysuwania i funkcjonalności wyboru koloru.

-   `fanslider/jscolor/jscolor.js`

    *   **Zakres:** Back-office (używany w `getContent()` dla pól wyboru koloru).
    *   **Odpowiedzialność:** Dostarcza narzędzie JavaScript do wyboru koloru, umożliwiając administratorom wizualne wybieranie kolorów tła i ramki suwaka. Dołącza się do pól wejściowych z klasą `jscolor`.
-   `fanslider/js/fanslider-click.js`

    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Ten skrypt obsługuje interakcję „kliknięcia” dla suwaka. Nasłuchuje zdarzeń kliknięcia na zakładce suwaka i przełącza widoczność oraz pozycję głównego kontenera suwaka (`#fanslider`). Zarządza również klasą `fanslider_open` w celu kontrolowania stanu otwarcia/zamknięcia.
-   `fanslider/js/fanslider.js`

    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Jest to prawdopodobnie główny skrypt do animacji suwaka i początkowej konfiguracji. Obsługuje interakcję „najechaniu” (hover), jeśli jest skonfigurowana, i potencjalnie oblicza początkowe pozycje lub stosuje transformacje CSS dla efektu wysuwania. Współpracuje z elementami `#fanslider` i `#fanslider_tab`.
-   `fanslider/script.js`

    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Ten skrypt prawdopodobnie zawiera podstawową logikę inicjalizacji Page Plugina Facebooka (FB.init i FB.XFBML.parse) oraz potencjalnie inne ogólne ustawienia lub wiązanie zdarzeń związane z zachowaniem suwaka. Zapewnia, że SDK Facebooka jest załadowane, a plugin jest poprawnie renderowany.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie wymienia jawnie plików CSS w `views/css/`. Stylizacja suwaka jest prawdopodobnie osadzona bezpośrednio w metodzie `hookDisplayHeader` pliku `fanslider.php` lub w szablonie `rightcolumn.tpl`, albo generowana dynamicznie na podstawie konfiguracji. Programiści powinni sprawdzić wygenerowany kod HTML i główny plik modułu pod kątem stylów inline lub bloków `<style>`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    *   `fanslider/views/templates/hook/rightcolumn.tpl`
        *   **Hook:** Ten szablon jest przede wszystkim zaprojektowany do renderowania w hooku, który pozwala na wstrzykiwanie treści do strony, takim jak `displayFooter` lub `displayHeader` (chociaż jego nazwa sugeruje `displayRightColumn`, implementacja modułu umieszcza go jako stały element).
        *   **Blok wizualny:** Ten szablon generuje główną strukturę HTML dla Facebook Fan Slider. Zazwyczaj zawiera:
            *   Główny kontener dla suwaka (`#fanslider`).
            *   Klikalną zakładkę (`#fanslider_tab`).
            *   Kontener dla Page Plugina Facebooka (`<div class="fb-page">`).
            *   Otrzymuje zmienne konfiguracyjne z modułu do dynamicznego ustawiania atrybutów dla Page Plugina Facebooka (np. `data-href`, `data-width`, `data-height`, `data-hide-cover`, `data-show-facepile`, `data-show-posts`, `data-hide-cta`, `data-small-header`, `data-adapt-container-width`).
            *   Zawiera również niezbędny `div` dla SDK Facebooka do renderowania wtyczki.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele baz danych**:

    *   Moduł nie tworzy żadnych niestandardowych tabel baz danych.
    *   Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy z prefiksem `FS_` lub `FANSIDER_` (np. `FS_WIDTH`, `FANSIDER_SLIDEON`).
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony. | Wstrzykuje niezbędne pliki CSS i JavaScript, a potencjalnie skrypt inicjalizujący SDK Facebooka. Może również generować style inline na podstawie konfiguracji. |
| `displayFooter` | Wykonywany na dole każdej strony, przed zamykającym tagiem `</body>`. | Renderuje główną strukturę HTML Facebook Fan Slider (z `rightcolumn.tpl`) i zapewnia załadowanie SDK Facebooka oraz inicjalizację Page Plugina po gotowości DOM. To tutaj wizualny komponent jest dodawany do strony. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze wersje, aktualizacje i profesjonalne wsparcie dla modułu Facebook Fan Slider, odwiedź swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
