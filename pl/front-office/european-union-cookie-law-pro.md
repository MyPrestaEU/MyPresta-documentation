---
title: "European Union Cookie Law Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop European Union Cookie Law Pro od MyPresta.eu."
sidebar:
  label: "European Union Cookie Law Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł European Union Cookie Law Pro na MyPresta.eu](https://mypresta.eu/modules/front-office-features/european-union-cookie-law-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/european-union-cookie-law-pro/)
>
> ---


# European Union Cookie Law Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > European Union Cookie Law Pro)

Jest to główny ekran konfiguracji, na którym zdefiniujesz wygląd, treść i zachowanie powiadomienia o plikach cookie. Moduł oferuje funkcję podglądu na żywo, umożliwiającą podgląd zmian w czasie rzeczywistym w panelu administracyjnym przed zapisaniem.

#### **Ustawienia ogólne**

- **Włącz moduł Prawa o Ciasteczkach:**

  - **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania powiadomienia o plikach cookie w całym Twoim sklepie.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (TAK):* Powiadomienie o plikach cookie będzie wyświetlane odwiedzającym zgodnie z innymi ustawieniami.
    - *Gdy wyłączone (NIE):* Powiadomienie o plikach cookie nie pojawi się w Twoim sklepie, a ten moduł nie będzie zbierał zgody na pliki cookie.
  - **Zalecana wartość:** TAK (aby zapewnić zgodność z prawem).
  - **Scenariusz / przykład sprzedawcy:** Możesz tymczasowo wyłączyć to ustawienie podczas konserwacji lub jeśli testujesz inne rozwiązanie dotyczące plików cookie.
- **Czas wygaśnięcia plików cookie (w dniach):**

  - **Co robi to ustawienie:** Określa, jak długo zgoda użytkownika na pliki cookie jest zapamiętywana przez Twój sklep. Po tym okresie użytkownik zostanie ponownie poproszony o zgodę.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawione na 365:* Zgoda użytkownika będzie ważna przez rok.
    - *Gdy ustawione na 30:* Zgoda będzie ważna przez miesiąc.
  - **Zalecana wartość:** 365 (jeden rok) to powszechny i rozsądny okres dla większości przepisów. Sprawdź lokalne przepisy pod kątem konkretnych wymagań.
  - **Scenariusz / przykład sprzedawcy:** Jeśli Twoje lokalne przepisy wymagają ponownej zgody co 6 miesięcy, ustaw to na 180.
- **Wyświetlaj na urządzeniach mobilnych:**

  - **Co robi to ustawienie:** Kontroluje, czy powiadomienie o plikach cookie jest wyświetlane użytkownikom przeglądającym na smartfonach i tabletach.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (TAK):* Powiadomienie o plikach cookie pojawi się na urządzeniach mobilnych, dostosowując swój układ do mniejszych ekranów.
    - *Gdy wyłączone (NIE):* Użytkownicy mobilni nie zobaczą powiadomienia o plikach cookie.
  - **Zalecana wartość:** TAK (dla pełnej zgodności na wszystkich urządzeniach).
  - **Scenariusz / przykład sprzedawcy:** Zawsze powinieneś to włączyć, ponieważ użytkownicy mobilni podlegają tym samym przepisom dotyczącym prywatności.
- **Wyświetlaj tylko odwiedzającym z krajów UE:**

  - **Co robi to ustawienie:** Jeśli włączone, powiadomienie o plikach cookie będzie wyświetlane tylko odwiedzającym, których adres IP wskazuje, że przeglądają z państwa członkowskiego UE.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (TAK):* Odwiedzający spoza UE nie zobaczą banera.
    - *Gdy wyłączone (NIE):* Wszyscy odwiedzający, niezależnie od ich lokalizacji, zobaczą baner.
  - **Zalecana wartość:** Zależy od Twojej grupy docelowej i porady prawnej. Jeśli obsługujesz tylko klientów z UE, TAK może być odpowiednie. Jeśli obsługujesz globalną publiczność i chcesz być bezpieczny, NIE jest lepsze.
  - **Scenariusz / przykład sprzedawcy:** Australijski sklep obsługujący głównie australijskich klientów może to włączyć, aby uniknąć wyświetlania banera swojej głównej publiczności, jednocześnie przestrzegając przepisów dla kilku odwiedzających z UE. Globalny sklep może to wyłączyć, aby być uniwersalnie zgodnym.

#### **Treść i linki**

- **Wiadomość o Prawie o Ciasteczkach:**

  - **Co robi to ustawienie:** Jest to główny tekst wyświetlany w powiadomieniu o plikach cookie, informujący użytkowników o używaniu plików cookie. Możesz użyć edytora tekstu sformatowanego, aby go sformatować.
  - **Efekt zmiany tego ustawienia:** Wprowadzony tutaj tekst będzie główną wiadomością, którą przeczytają Twoi klienci.
  - **Zalecana wartość:** Jasna, zwięzła wiadomość, taka jak „Ta strona używa plików cookie, aby zapewnić najlepsze doświadczenia na naszej stronie. [Dowiedz się więcej]”
  - **Scenariusz / przykład sprzedawcy:** Możesz uwzględnić informacje o typach używanych plików cookie (np. „Używamy plików cookie do analizy i poprawy Twoich doświadczeń zakupowych.”).
- **Tekst przycisku „Akceptuj”:**

  - **Co robi to ustawienie:** Definiuje tekst wyświetlany na przycisku, który użytkownicy klikają, aby zaakceptować pliki cookie.
  - **Efekt zmiany tego ustawienia:** Zmienia etykietę przycisku akceptacji.
  - **Zalecana wartość:** „Akceptuj”, „Rozumiem”, „OK”, „Zgadzam się”.
  - **Scenariusz / przykład sprzedawcy:** Możesz użyć „Akceptuj i kontynuuj”, aby zachęcić użytkowników do kontynuowania.
- **Tekst przycisku „Więcej informacji”:**

  - **Co robi to ustawienie:** Definiuje tekst wyświetlany na przycisku, który użytkownicy klikają, aby dowiedzieć się więcej o Twojej polityce plików cookie.
  - **Efekt zmiany tego ustawienia:** Zmienia etykietę przycisku informacyjnego.
  - **Zalecana wartość:** „Dowiedz się więcej”, „Więcej informacji”, „Polityka prywatności”.
  - **Scenariusz / przykład sprzedawcy:** Możesz użyć „Ustawienia plików cookie”, jeśli masz szczegółowy system zarządzania preferencjami.
- **Link do strony Polityki prywatności:**

  - **Co robi to ustawienie:** Określa adres URL, pod którym użytkownicy mogą znaleźć Twoją pełną politykę prywatności lub plików cookie. Ten link zostanie dołączony do przycisku „Więcej informacji” lub konkretnej części Twojej wiadomości.
  - **Efekt zmiany tego ustawienia:** Gdy użytkownicy klikną przycisk „Więcej informacji”, zostaną przekierowani na ten adres URL.
  - **Zalecana wartość:** Pełny adres URL Twojej strony CMS (np. `https://twojasklep.com/content/3-regulamin`).
  - **Scenariusz / przykład sprzedawcy:** Tworzysz dedykowaną stronę CMS w PrestaShop (Wygląd > Strony) dla swojej „Polityki plików cookie” i linkujesz do niej tutaj.

#### **Opcje wyświetlania i stylizacja**

- **Pozycja powiadomienia o plikach cookie:**

  - **Co robi to ustawienie:** Określa, gdzie powiadomienie o plikach cookie pojawia się na Twojej stronie internetowej.
  - **Efekt zmiany tego ustawienia:**
    - *Górny pasek:* Baner pojawia się na górze okna przeglądarki.
    - *Dolny pasek:* Baner pojawia się na dole okna przeglądarki.
    - *Modalne okno centralne:* Wyskakujące okno na środku ekranu.
    - *Pływające okno (Górny lewy, Górny prawy, Dolny lewy, Dolny prawy):* Mniejsze, stałe okno w jednym z narożników.
  - **Zalecana wartość:** Dolny pasek lub Pływające okno są zazwyczaj mniej inwazyjne. Modalne okno centralne jest bardzo widoczne, ale może być uciążliwe.
  - **Scenariusz / przykład sprzedawcy:** Sklep modowy może preferować subtelny „Dolny pasek”, aby skupić się na produktach, podczas gdy firma usługowa może użyć „Modalnego okna centralnego” dla maksymalnej widoczności.
- **Kolor tła:**

  - **Co robi to ustawienie:** Ustawia główny kolor tła banera powiadomienia o plikach cookie.
  - **Efekt zmiany tego ustawienia:** Zmienia wizualne tło powiadomienia.
  - **Zalecana wartość:** Kolor, który dobrze kontrastuje z Twoim tekstem i pasuje do Twojej marki.
  - **Scenariusz / przykład sprzedawcy:** Użyj głównego koloru swojej marki lub neutralnej szarości.
- **Kolor tekstu:**

  - **Co robi to ustawienie:** Ustawia kolor głównego tekstu wiadomości w powiadomieniu.
  - **Efekt zmiany tego ustawienia:** Zmienia kolor tekstu wiadomości.
  - **Zalecana wartość:** Kolor, który zapewnia dobrą czytelność na wybranym tle.
  - **Scenariusz / przykład sprzedawcy:** Biały tekst na ciemnym tle lub ciemnoszary tekst na jasnym tle.
- **Kolor linku:**

  - **Co robi to ustawienie:** Ustawia kolor dla wszelkich linków w Twojej wiadomości o plikach cookie (np. link „Dowiedz się więcej”, jeśli jest częścią wiadomości).
  - **Efekt zmiany tego ustawienia:** Zmienia kolor klikalnego tekstu w wiadomości.
  - **Zalecana wartość:** Kolor akcentu Twojej marki lub standardowy niebieski dla linków.
  - **Scenariusz / przykład sprzedawcy:** Użyj jasnego koloru, aby link „Dowiedz się więcej” wyróżniał się.
- **Kolor tła przycisku:**

  - **Co robi to ustawienie:** Ustawia kolor tła dla przycisków „Akceptuj” i „Więcej informacji”.
  - **Efekt zmiany tego ustawienia:** Zmienia wizualne tło przycisków.
  - **Zalecana wartość:** Kolor, który sprawia, że przyciski są wyraźnie widoczne i klikalne.
  - **Scenariusz / przykład sprzedawcy:** Użyj koloru wezwania do działania swojej marki.
- **Kolor tekstu przycisku:**

  - **Co robi to ustawienie:** Ustawia kolor tekstu na przyciskach „Akceptuj” i „Więcej informacji”.
  - **Efekt zmiany tego ustawienia:** Zmienia kolor etykiet przycisków.
  - **Zalecana wartość:** Kolor, który zapewnia dobry kontrast z tłem przycisku.
  - **Scenariusz / przykład sprzedawcy:** Biały tekst na kolorowym przycisku lub czarny tekst na jasnym przycisku.
- **Kolor tła przycisku po najechaniu myszą:**

  - **Co robi to ustawienie:** Ustawia kolor tła przycisków, gdy użytkownik najedzie na nie myszą.
  - **Efekt zmiany tego ustawienia:** Zapewnia wizualną informację zwrotną dla użytkownika, że przycisk jest interaktywny.
  - **Zalecana wartość:** Nieco ciemniejszy lub jaśniejszy odcień normalnego koloru tła przycisku.
  - **Scenariusz / przykład sprzedawcy:** Subtelna zmiana koloru, aby wskazać interaktywność.
- **Kolor tekstu przycisku po najechaniu myszą:**

  - **Co robi to ustawienie:** Ustawia kolor tekstu przycisków, gdy użytkownik najedzie na nie myszą.
  - **Efekt zmiany tego ustawienia:** Zapewnia wizualną informację zwrotną.
  - **Zalecana wartość:** Często taki sam jak normalny kolor tekstu przycisku lub kontrastujący kolor, jeśli tło znacznie się zmienia.
  - **Scenariusz / przykład sprzedawcy:** Jeśli tło przycisku staje się ciemne po najechaniu myszą, możesz zmienić tekst na biały.
- **Promień zaokrąglenia (px):**

  - **Co robi to ustawienie:** Kontroluje zaokrąglenie narożników powiadomienia o plikach cookie i jego przycisków. Wartość 0 oznacza ostre narożniki, wyższe wartości oznaczają bardziej zaokrąglone narożniki.
  - **Efekt zmiany tego ustawienia:**
    - *0px:* Ostre, kwadratowe narożniki.
    - *5px:* Lekko zaokrąglone narożniki.
    - *20px:* Bardzo zaokrąglone, w kształcie pigułki narożniki.
  - **Zalecana wartość:** 0-5px dla nowoczesnego, czystego wyglądu; wyższa dla bardziej miękkiego, przyjaznego wyglądu.
  - **Scenariusz / przykład sprzedawcy:** Dopasuj to do promienia zaokrąglenia używanego w Twoim motywie dla spójności.
- **Efekt szkła:**

  - **Co robi to ustawienie:** Stosuje półprzezroczysty, matowy efekt szkła do tła powiadomienia o plikach cookie.
  - **Efekt zmiany tego ustawienia:** Sprawia, że tło jest lekko przezroczyste i rozmyte, pozwalając subtelnie prześwitywać treściom znajdującym się za nim.
  - **Zalecana wartość:** Wypróbuj i zobacz, czy pasuje do Twojego projektu. Może dodać wrażenie premium.
  - **Scenariusz / przykład sprzedawcy:** Użyj tego, jeśli Twój motyw ma nowoczesną, minimalistyczną estetykę.
- **Tło gradientowe:**

  - **Co robi to ustawienie:** Pozwala użyć płynnego przejścia między dwoma kolorami dla tła powiadomienia o plikach cookie zamiast jednego jednolitego koloru.
  - **Efekt zmiany tego ustawienia:** Tworzy wizualnie atrakcyjną mieszankę kolorów. Zazwyczaj będziesz mieć opcje koloru początkowego i końcowego.
  - **Zalecana wartość:** Użyj kolorów, które wzajemnie się uzupełniają i pasują do Twojej marki.
  - **Scenariusz / przykład sprzedawcy:** Sklep technologiczny może użyć gradientu od niebieskiego do fioletowego dla nowoczesnego wyglądu.
- **Kolor tła nakładki (dla modalnego okna centralnego):**

  - **Co robi to ustawienie:** Podczas korzystania z pozycji „Modalne okno centralne” ustawia kolor półprzezroczystej warstwy, która pokrywa resztę strony za modalnym oknem.
  - **Efekt zmiany tego ustawienia:** Kontroluje wizualne skupienie na modalnym oknie. Ciemniejsza, bardziej nieprzezroczysta nakładka sprawia, że modalne okno bardziej się wyróżnia.
  - **Zalecana wartość:** Półprzezroczysta czerń (`rgba(0,0,0,0.7)`) lub ciemny odcień pasujący do Twojego motywu.
  - **Scenariusz / przykład sprzedawcy:** Użyj ciemnej, lekko przezroczystej nakładki, aby upewnić się, że modalne okno plików cookie jest głównym punktem uwagi, gdy się pojawi.
- **Niestandardowy CSS:**

  - **Co robi to ustawienie:** Udostępnia obszar tekstowy, w którym możesz dodać własne niestandardowe reguły CSS, aby dalej stylizować powiadomienie o plikach cookie, nadpisując domyślne style modułu.
  - **Efekt zmiany tego ustawienia:** Pozwala na zaawansowane dostosowanie poza dostępne opcje.
  - **Zalecana wartość:** Pozostaw puste, chyba że masz specyficzne wymagania projektowe i wiedzę CSS.
  - **Scenariusz / przykład sprzedawcy:** Możesz użyć tego do zmiany rozmiaru czcionki wiadomości, dodania cienia lub dostosowania odstępów, jeśli wbudowane opcje nie są wystarczające.

#### **Presety i podgląd na żywo**

- **Wczytaj preset:**

  - **Co robi to ustawienie:** Pozwala szybko zastosować predefiniowany zestaw opcji stylizacji (kolory, pozycje, efekty) z biblioteki gotowych projektów.
  - **Efekt zmiany tego ustawienia:** Natychmiast zmienia wygląd powiadomienia o plikach cookie, aby pasował do wybranego presetu. Wszystkie indywidualne ustawienia stylizacji zostaną zaktualizowane.
  - **Zalecana wartość:** Przeglądaj presety, aby znaleźć taki, który najbardziej pasuje do Twojej marki, a następnie dopracuj go.
  - **Scenariusz / przykład sprzedawcy:** Szukasz ciemnego, minimalistycznego banera. Wybierasz preset „Ciemny motyw”, a następnie dostosowujesz dokładne odcienie czerni i szarości.
- **Podgląd na żywo:**

  - **Co robi to ustawienie:** Ta sekcja strony konfiguracji wyświetla podgląd powiadomienia o plikach cookie w czasie rzeczywistym podczas dostosowywania ustawień.
  - **Efekt zmiany tego ustawienia:** Pokazuje dokładnie, jak będzie wyglądał Twój baner na stronie głównej, bez konieczności zapisywania i odświeżania sklepu.
  - **Zalecana wartość:** Zawsze używaj podglądu na żywo, aby zweryfikować swoje wybory projektowe przed zapisaniem.
  - **Scenariusz / przykład sprzedawcy:** Eksperymentujesz z różnymi kolorami przycisków; podgląd na żywo natychmiast pokazuje, która kombinacja wygląda najlepiej.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz moduł Prawa o Ciasteczkach | TAK | Główny przełącznik dla powiadomienia o plikach cookie. |
| | Czas wygaśnięcia plików cookie (dni) | 365 | Jak długo zgoda jest zapamiętywana. |
| | Wyświetlaj na urządzeniach mobilnych | TAK | Pokaż baner na telefonach/tabletach. |
| | Wyświetlaj tylko odwiedzającym z UE | NIE (dla globalnej zgodności) | Celuj w odwiedzających z UE lub wszystkich odwiedzających. |
| | Wiadomość o Prawie o Ciasteczkach | Konfigurowalne | Główny tekst powiadomienia o plikach cookie. |
| | Tekst przycisku „Akceptuj” | „Akceptuj” | Etykieta przycisku zgody. |
| | Tekst przycisku „Więcej informacji” | „Dowiedz się więcej” | Etykieta przycisku informacyjnego. |
| | Link do strony Polityki prywatności | Twój URL polityki | URL dla szczegółowej polityki plików cookie. |
| | Pozycja powiadomienia o plikach cookie | Dolny pasek / Pływające okno | Gdzie pojawia się baner (Górny/Dolny pasek, Modalne okno centralne, Pływające okno). |
| | Kolor tła | Konfigurowalne | Główny kolor tła powiadomienia. |
| | Kolor tekstu | Konfigurowalne | Kolor tekstu wiadomości. |
| | Kolor linku | Konfigurowalne | Kolor linków w wiadomości. |
| | Kolor tła przycisku | Konfigurowalne | Kolor tła przycisków akcji. |
| | Kolor tekstu przycisku | Konfigurowalne | Kolor tekstu na przyciskach akcji. |
| | Kolor tła przycisku po najechaniu myszą | Konfigurowalne | Kolor tła po najechaniu myszą na przycisk. |
| | Kolor tekstu przycisku po najechaniu myszą | Konfigurowalne | Kolor tekstu po najechaniu myszą na przycisk. |
| | Promień zaokrąglenia (px) | 0-5 | Zaokrąglenie narożników. |
| | Efekt szkła | NIE | Dodaje półprzezroczysty, matowy efekt. |
| | Tło gradientowe | NIE | Używa gradientu kolorów dla tła. |
| | Kolor tła nakładki | Półprzezroczysty ciemny | Kolor nakładki tła dla modalnego okna centralnego. |
| | Niestandardowy CSS | Puste | Do zaawansowanych nadpisań stylów. |
| | Wczytaj preset | Wybierz jeden | Zastosuj predefiniowane opcje stylizacji. |
| | Podgląd na żywo | N/A | Wizualna informacja zwrotna w czasie rzeczywistym o ustawieniach. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem moduł, ale baner cookie nie wyświetla się w moim sklepie.**
O:

1.  **Sprawdź „Włącz moduł Prawa o Ciasteczkach”:** Upewnij się, że jest ustawiony na TAK w konfiguracji modułu.
2.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Pamięć podręczna przeglądarki również może wymagać wyczyszczenia (Ctrl+F5 lub Cmd+R).
3.  **Sprawdź ustawienie kraju UE:** Jeśli opcja „Wyświetlaj tylko odwiedzającym z krajów UE” jest włączona, upewnij się, że testujesz z adresu IP z UE. Spróbuj tymczasowo wyłączyć to ustawienie do celów testowych.
4.  **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany tak, aby był kompatybilny, niektóre wysoce spersonalizowane motywy mogą mieć konflikty. Sprawdź konsolę programisty przeglądarki (F12) pod kątem błędów JavaScript.

**P: Baner wygląda inaczej w moim sklepie niż w podglądzie na żywo.**
O:

1.  **Wyczyść pamięć podręczną:** Zawsze czyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**) po wprowadzeniu zmian. Pamięć podręczna przeglądarki również może wyświetlać starszą wersję.
2.  **Konflikty niestandardowego CSS:** Jeśli dodałeś „Niestandardowy CSS” lub Twój motyw ma sprzeczne style, mogą one nadpisywać ustawienia modułu. Tymczasowo usuń swój niestandardowy CSS, aby sprawdzić, czy to rozwiąże problem.
3.  **Nadpisania motywu:** Twój motyw może mieć specyficzne reguły CSS, które są bardziej szczegółowe niż te z modułu. Programista może pomóc zidentyfikować i rozwiązać te problemy.

**P: Jak przetłumaczyć wiadomość o plikach cookie i teksty przycisków na inne języki?**
O:

1.  Przejdź do **Lokalizacja > Tłumaczenia** w panelu administracyjnym PrestaShop.
2.  Wybierz „Tłumaczenia zainstalowanych modułów” jako Typ tłumaczenia.
3.  Wybierz swój motyw.
4.  Wybierz język, na który chcesz przetłumaczyć.
5.  Znajdź moduł „European Union Cookie Law Pro” na liście. Będziesz mógł przetłumaczyć „Wiadomość o Prawie o Ciasteczkach”, „Tekst przycisku Akceptuj” i „Tekst przycisku Więcej informacji” tam.

**P: Baner cookie zakrywa ważną część mojej witryny (np. widżet czatu, element menu).**
O:

1.  **Dostosuj pozycję:** Eksperymentuj z ustawieniem „Pozycja powiadomienia o plikach cookie”. Jeśli dolny pasek zakrywa widżet czatu, spróbuj górnego paska lub pływającego okna w innym rogu.
2.  **Niestandardowy CSS (zaawansowany):** Jeśli żadna pozycja nie działa, programista może użyć pola „Niestandardowy CSS” do dostosowania właściwości `z-index` banera cookie lub konfliktu elementu, aby upewnić się, że prawidłowy element jest na wierzchu.

**P: Czy ten moduł obsługuje różne kategorie plików cookie (np. niezbędne, analityczne, marketingowe)?**
O: Ten moduł koncentruje się głównie na wyświetlaniu ogólnego powiadomienia o zgodzie na pliki cookie i zbieraniu pojedynczej zgody „akceptuj” lub „odrzuć” (poprzez nieakceptowanie). W przypadku bardziej zaawansowanego, szczegółowego zarządzania kategoriami plików cookie (gdzie użytkownicy mogą wybrać, jakie typy plików cookie zezwalają), zazwyczaj potrzebne jest bardziej złożone rozwiązanie lub integracja z dedykowaną platformą zarządzania zgodami (CMP). Ten moduł jest przeznaczony do prostego przestrzegania przepisów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera przegląd techniczny dla programistów i webmasterów, którzy chcą zrozumieć, dostosować lub debugować moduł „European Union Cookie Law Pro”.

### 4.1 Przegląd architektury

Moduł `uecookiepro` stosuje standardową architekturę modułów PrestaShop, głównie wykorzystując klasę `Module` do swojej podstawowej funkcjonalności i `getContent()` do konfiguracji panelu administracyjnego. Wstrzykuje swoją zawartość front-office bezpośrednio do wybranego haka, dynamicznie renderując baner cookie na podstawie ustawień konfiguracyjnych. Stylizacja jest zarządzana za pomocą stylów inline i potencjalnie niestandardowego CSS, a JavaScript obsługuje interakcję użytkownika i przechowywanie zgody.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych niestandardowych kontrolerów front-office ani back-office. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu, a wyświetlanie front-office jest zarządzane za pomocą haków.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani instancji `ObjectModel`. Cała konfiguracja jest przechowywana bezpośrednio w tabeli `ps_configuration` przy użyciu standardowych kluczy konfiguracyjnych PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł zawiera kilka plików JavaScript, głównie do ulepszeń konfiguracji panelu administracyjnego i interakcji front-office.

- `uecookiepro/jscolor/jscolor.js`:
  - **Zakres:** Panel administracyjny.
  - **Odpowiedzialność:** Zapewnia funkcjonalność wyboru koloru używaną w formularzu konfiguracji modułu, umożliwiając sprzedawcom wizualne wybieranie kolorów dla banera.
- `uecookiepro/tinymce-original.js`:
  - **Zakres:** Panel administracyjny.
  - **Odpowiedzialność:** Podstawowa biblioteka edytora tekstu sformatowanego TinyMCE. Jest używana dla pola „Wiadomość o Prawie o Ciasteczkach”, umożliwiając sprzedawcom formatowanie wiadomości za pomocą HTML.
- `uecookiepro/tinymce16.inc.js`:
  - **Zakres:** Panel administracyjny.
  - **Odpowiedzialność:** Plik dołączany, prawdopodobnie zawierający specyficzne ustawienia inicjalizacji i konfiguracji TinyMCE dostosowane do środowisk PrestaShop 1.6.x, zapewniające prawidłowe działanie edytora w konfiguracji modułu.
- `uecookiepro/views/js/patterns.js`:
  - **Zakres:** Panel administracyjny.
  - **Odpowiedzialność:** Prawdopodobnie zawiera predefiniowane wzorce lub konfiguracje dla presetów stylizacji modułu, używane do szybkiego ładowania różnych motywów wizualnych dla banera cookie.
- `uecookiepro/views/js/presets-community.js`:
  - **Zakres:** Panel administracyjny.
  - **Odpowiedzialność:** Zawiera dodatkowe presety dostarczone przez społeczność lub rozszerzone presety do wizualnej stylizacji banera cookie, oferując więcej gotowych opcji projektowych.
- `uecookiepro/views/js/scripts.js`:
  - **Zakres:** Front-office i Panel administracyjny.
  - **Odpowiedzialność:** Jest to główny niestandardowy plik JavaScript dla modułu.
    - **Front-office:** Obsługuje logikę wyświetlania banera cookie, nasłuchuje kliknięć przycisku „Akceptuj”, ustawia plik cookie zgody i ukrywa baner. Zarządza również widocznością na podstawie `Cookie Expiration Time`.
    - **Panel administracyjny:** Prawdopodobnie zawiera logikę funkcji podglądu na żywo, dynamicznie aktualizując baner podglądu w miarę zmiany ustawień w formularzu konfiguracji. Może również obsługiwać interakcje z funkcją „Wczytaj preset”.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie wymienia jawnie żadnych plików `.css` w dostarczonym spisie. Sugeruje to, że stylizacja jest głównie obsługiwana za pomocą:

1.  **Stylów inline:** Generowanych dynamicznie przez moduł na podstawie ustawień konfiguracyjnych (kolory, pozycje itp.).
2.  **Wewnętrznego CSS `jscolor.js`:** Dla interfejsu użytkownika wyboru koloru.
3.  **Wewnętrznego CSS `tinymce`:** Dla interfejsu użytkownika edytora tekstu sformatowanego.
4.  **Pola niestandardowego CSS:** Umożliwiającego sprzedawcom wstrzykiwanie własnych stylów.
    Programiści, którzy chcą nadpisać style, powinni zbadać renderowany kod HTML banera cookie i celować w jego elementy za pomocą bardziej specyficznych reguł CSS w arkuszu stylów swojego motywu lub za pośrednictwem pola niestandardowego CSS modułu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony haków (`views/templates/hook/`)**:
  - `uecookiepro/top.tpl`:
    - **Hak:** Ten szablon jest przeznaczony do renderowania w różnych hakach front-office, takich jak `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, a nawet bezpośrednio w plikach `product.tpl` lub `index.tpl` motywu, w zależności od wybranej „Pozycji powiadomienia o plikach cookie” i sposobu implementacji metod `hookDisplay*` modułu.
    - **Wyjście:** Generuje strukturę HTML dla banera zgody na pliki cookie, w tym tekst wiadomości, przycisk „Akceptuj” i link „Więcej informacji”. Dynamiczna stylizacja (kolory, pozycja, efekty) jest wstrzykiwana do tego szablonu, albo jako style inline, albo poprzez manipulację JavaScript.

### 4.7 Schemat bazy danych i mapa haków

- **Tabele bazy danych**:
  Moduł nie tworzy żadnych niestandardowych tabel SQL. Wszystkie ustawienia konfiguracyjne są przechowywane w standardowej tabeli PrestaShop `ps_configuration`. Klucze konfiguracyjne zazwyczaj mają wzorzec `UECOOKIEPRO_NAZWA_USTAWIENIA`.
- **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` każdej strony. | Potencjalnie używany do ładowania zasobów CSS/JS lub do wstrzykiwania banera na samej górze strony. |
| `displayFooter` | Renderuje się na dole każdej strony, przed zamykającym tagiem `</body>`. | Powszechny hak do wstrzykiwania banera cookie (pozycja dolnego paska) lub powiązanego z nim JavaScriptu. |
| `displayLeftColumn` | Renderuje się w lewym pasku bocznym (jeśli włączony przez motyw). | Mniej powszechne dla banerów cookie, ale może być używane do pływającego okna w lewej kolumnie. |
| `displayRightColumn` | Renderuje się w prawym pasku bocznym (jeśli włączony przez motyw). | Mniej powszechne dla banerów cookie, ale może być używane do pływającego okna w prawej kolumnie. |
| `displayProductAdditionalInfo` (lub podobny hak strony produktu) | Renderuje się na stronie produktu, często poniżej opisu produktu lub szczegółów. | Może być używany do umieszczenia pływającego okna specjalnie na stronach produktów. |
| `actionFrontControllerSetMedia` | Wykonywany, gdy kontroler front-office ustawia swoje media (CSS/JS). | Idealny do warunkowego ładowania CSS i JavaScriptu specyficznego dla modułu tylko wtedy, gdy jest to potrzebne, poprawiając wydajność. |

Moduł dynamicznie wybiera, którego haka użyć, na podstawie ustawienia „Pozycja powiadomienia o plikach cookie”. Na przykład, jeśli wybrano „Dolny pasek”, prawdopodobnie używa `displayFooter`. Jeśli wybrano „Górny pasek”, może używać `displayHeader`. Pozycje „Pływające okno” lub „Modalne okno centralne” są zazwyczaj zarządzane poprzez wstrzykiwanie kodu HTML do ogólnego haka, takiego jak `displayFooter`, a następnie używanie CSS (`position: fixed;`) i JavaScriptu do kontrolowania jego dokładnego umiejscowienia i widoczności.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnego wsparcia, aktualizacji modułu i wszelkiej dalszej pomocy, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnianie terminowego wsparcia i zapewnienie optymalnego funkcjonowania modułu.
