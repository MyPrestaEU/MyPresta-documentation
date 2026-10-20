---
title: "My AI Act Pro - Zgodność z Ustawą o Sztucznej Inteligencji - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop My AI Act Pro - Zgodność z Ustawą o Sztucznej Inteligencji od MyPresta.eu."
sidebar:
  label: "My AI Act Pro - Zgodność z Ustawą o Sztucznej Inteligencji - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł My AI Act Pro - Artificial Intelligence Compliance na MyPresta.eu](https://mypresta.eu/modules/front-office-features/my-ai-act-pro-artificial-intelligence-compliance.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/my-ai-act-pro-artificial-intelligence-compliance/)
>
> ---


# My AI Act Pro - Zgodność z Ustawą o Sztucznej Inteligencji

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.6.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Upewnij się, że Twój serwer spełnia ogólne wymagania PrestaShop dla optymalnej wydajności.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > My AI Act Pro)

To jest główny panel sterowania dla Twojego modułu zgodności z Ustawą o Sztucznej Inteligencji. Tutaj włączysz funkcje, zdefiniujesz globalne ustawienia i zarządzasz ogólnym zachowaniem ujawnień AI.

#### Zakładka Ustawienia ogólne

-   **Włącz zgodność z Ustawą o Sztucznej Inteligencji:**

    -   **Co robi to ustawienie:** To jest główny przełącznik dla całego modułu.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone:* Wszystkie funkcje modułu (odznaki, banery, logi itp.) zostaną aktywowane w Twoim sklepie zgodnie z ich indywidualnymi ustawieniami.
        -   *Gdy wyłączone:* Moduł przestanie wyświetlać wszelkie treści związane z Ustawą o Sztucznej Inteligencji w Twoim front office, a jego procesy w tle zostaną wstrzymane.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Włącz to, gdy będziesz gotowy do uruchomienia zgodności z Ustawą o Sztucznej Inteligencji. Jeśli musisz tymczasowo wyłączyć wszystkie ujawnienia w celu konserwacji, wyłącz to.
-   **Wyświetlaj odznakę ujawniającą AI na stronach produktów:**

    -   **Co robi to ustawienie:** Kontroluje, czy odznaka ujawniająca AI pojawia się na poszczególnych stronach produktów.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone:* Odznaka AI będzie widoczna na stronach produktów oznaczonych jako generowane przez AI.
        -   *Gdy wyłączone:* Odznaka nie będzie wyświetlana na stronach produktów, nawet jeśli produkty są oznaczone.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Jest to kluczowe dla bezpośredniej przejrzystości produktu. Pozostaw włączone, aby informować klientów bezpośrednio o przeglądanym produkcie.
-   **Wyświetlaj odznakę ujawniającą AI na listach produktów:**

    -   **Co robi to ustawienie:** Kontroluje, czy odznaka ujawniająca AI pojawia się na stronach kategorii, w wynikach wyszukiwania lub innych widokach list produktów.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone:* Mniejsza odznaka AI pojawi się na miniaturach produktów na listach.
        -   *Gdy wyłączone:* Żadna odznaka nie pojawi się na listach produktów.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Włączenie tego zapewnia natychmiastową przejrzystość podczas przeglądania przez klientów, pomagając im zidentyfikować treści generowane przez AI przed kliknięciem na stronę produktu.
-   **Pozycja odznaki ujawniającej AI (strona produktu):**

    -   **Co robi to ustawienie:** Określa, gdzie odznaka AI jest umieszczana na stronie produktu. Opcje zazwyczaj obejmują „Nad zdjęciem produktu”, „Poniżej zdjęcia produktu”, „W pobliżu nazwy produktu”, „W opisie produktu” itp.
    -   **Skutek zmiany tego ustawienia:** Odznaka przeniesie się do wybranej lokalizacji na stronie produktu.
    -   **Zalecana wartość:** Eksperymentuj, aby znaleźć najlepsze dopasowanie do Twojego szablonu, często „Nad zdjęciem produktu” lub „W pobliżu nazwy produktu” dla widoczności.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoje zdjęcia produktów są bardzo duże, umieszczenie odznaki „Poniżej zdjęcia produktu” może być mniej inwazyjne. Jeśli chcesz, aby była natychmiast zauważalna, lepsze jest „Nad zdjęciem produktu”.
-   **Układ odznaki ujawniającej AI:**

    -   **Co robi to ustawienie:** Pozwala wybrać predefiniowany styl wizualny dla odznaki AI ze „Studia Układu”.
    -   **Skutek zmiany tego ustawienia:** Wygląd odznaki AI (ikona, tekst, kolory, kształt) zmieni się zgodnie z wybranym układem.
    -   **Zalecana wartość:** Wybierz układ, który pasuje do brandingu Twojego sklepu i jest wyraźnie widoczny.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz stworzyć niestandardowy układ z kolorami Twojej marki i konkretną ikoną, aby zapewnić, że odznaka wygląda profesjonalnie i dobrze się integruje.
-   **Link do strony polityki AI:**

    -   **Co robi to ustawienie:** Pozwala połączyć się z dedykowaną stroną CMS lub zewnętrznym adresem URL wyjaśniającym politykę AI Twojego sklepu.
    -   **Skutek zmiany tego ustawienia:** Moduł użyje tego adresu URL podczas linkowania do Twojej polityki AI z odznak, banerów lub innych elementów ujawniających.
    -   **Zalecana wartość:** Utwórz szczegółową stronę CMS (np. „Nasza polityka przejrzystości AI”) i połącz ją tutaj.
    -   **Scenariusz / przykład dla sprzedawcy:** Ten link jest kluczowy dla dostarczania kompleksowych informacji klientom, którzy chcą dowiedzieć się więcej o Twoim użyciu AI.
-   **Włącz baner ujawniający AI:**

    -   **Co robi to ustawienie:** Aktywuje baner na całej stronie, aby informować klientów o użyciu AI.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone:* Baner pojawi się w wybranym hooku (np. nagłówek lub stopka).
        -   *Gdy wyłączone:* Żaden baner nie zostanie wyświetlony.
    -   **Zalecana wartość:** TAK, zwłaszcza przy początkowym wdrożeniu lub jeśli Twój sklep intensywnie korzysta z AI.
    -   **Scenariusz / przykład dla sprzedawcy:** Użyj tego banera, aby ogólnie poinformować o polityce AI Twojego sklepu, być może linkując do Twojej dedykowanej strony polityki.
-   **Pozycja banera ujawniającego AI (Hook):**

    -   **Co robi to ustawienie:** Wybiera, gdzie baner się pojawi (np. `displayHeader`, `displayFooter`).
    -   **Skutek zmiany tego ustawienia:** Baner zostanie wyrenderowany w wybranej lokalizacji.
    -   **Zalecana wartość:** `displayHeader` dla maksymalnej widoczności lub `displayFooter` dla mniej inwazyjnego podejścia.
    -   **Scenariusz / przykład dla sprzedawcy:** Umieszczenie go w `displayHeader` zapewnia, że każdy odwiedzający zobaczy go natychmiast po wejściu na Twoją stronę.
-   **Treść banera ujawniającego AI:**

    -   **Co robi to ustawienie:** Pozwala dostosować tekst i zawartość HTML banera.
    -   **Skutek zmiany tego ustawienia:** Baner wyświetli Twoją niestandardową wiadomość.
    -   **Zalecana wartość:** Zwięzła wiadomość, taka jak „Używamy AI, aby poprawić Twoje doświadczenie zakupowe. [Dowiedz się więcej]” z linkiem do Twojej strony polityki.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz użyć tego, aby krótko wyjaśnić swoje użycie AI i skierować klientów do pełnej polityki.
-   **Włącz informacje o ludzkim wsparciu:**

    -   **Co robi to ustawienie:** Wyświetla wiadomość wskazującą na nadzór człowieka lub oferującą pomoc człowieka dla treści generowanych przez AI.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone:* Konfigurowalna wiadomość pojawi się na odpowiednich stronach.
        -   *Gdy wyłączone:* Żadna wiadomość o ludzkim wsparciu nie zostanie wyświetlona.
    -   **Zalecana wartość:** TAK, jeśli chcesz zapewnić klientów, że zaangażowany jest przegląd człowieka lub podać punkt kontaktowy.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoje opisy produktów generowane przez AI są zawsze przeglądane przez ludzkiego edytora, możesz użyć tego, aby stwierdzić „Wszystkie treści generowane przez AI są przeglądane przez nasz zespół. Skontaktuj się z nami, jeśli masz pytania.”
-   **Wiadomość o ludzkim wsparciu:**

    -   **Co robi to ustawienie:** Dostosowuje tekst dla informacji o ludzkim wsparciu.
    -   **Skutek zmiany tego ustawienia:** Wiadomość zostanie wyświetlona zgodnie z wpisem.
    -   **Zalecana wartość:** Jasna, uspokajająca wiadomość.
    -   **Scenariusz / przykład dla sprzedawcy:** „Nasze narzędzia AI są nadzorowane przez ekspertów. W przypadku jakichkolwiek obaw, prosimy o kontakt z naszym działem obsługi klienta.”
-   **Włącz dziennik audytu:**

    -   **Co robi to ustawienie:** Rejestruje wszystkie działania i ujawnienia związane z Ustawą o Sztucznej Inteligencji w dzienniku w celach zgodności.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone:* Za każdym razem, gdy dokonane jest ujawnienie AI lub produkt jest oznaczony, wpis jest zapisywany w dzienniku audytu modułu.
        -   *Gdy wyłączone:* Nie będzie prowadzony żaden ślad audytu.
    -   **Zalecana wartość:** TAK, jest to kluczowe dla wykazania zgodności i rozwiązywania problemów.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli organ regulacyjny poprosi o dowód Twoich ujawnień AI, dziennik audytu dostarcza historyczny zapis.

#### Zakładka API i Integracje

-   **Włącz REST API:**

    -   **Co robi to ustawienie:** Aktywuje punkt końcowy REST API dla systemów zewnętrznych do interakcji z modułem (np. oznaczanie produktów jako generowanych przez AI).
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone:* API staje się aktywne, umożliwiając programową interakcję.
        -   *Gdy wyłączone:* API jest nieaktywne.
    -   **Zalecana wartość:** NIE, chyba że masz konkretną potrzebę techniczną integracji z zewnętrznymi narzędziami lub systemami AI.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli używasz zewnętrznej usługi generowania obrazów AI, możesz użyć API do automatycznego oznaczania obrazów jako generowanych przez AI w PrestaShop.
-   **Zarządzanie kluczami API:**

    -   **Co robi to ustawienie:** Pozwala generować i zarządzać kluczami API dla bezpiecznego dostępu do REST API modułu.
    -   **Skutek zmiany tego ustawienia:** Nowe klucze mogą być tworzone, istniejące odwoływane, kontrolując, kto może uzyskać dostęp do API.
    -   **Zalecana wartość:** Wygeneruj silny, unikalny klucz dla każdej integracji.
    -   **Scenariusz / przykład dla sprzedawcy:** Utwórz konkretny klucz API dla swojego generatora obrazów AI i inny dla swojego pisarza treści AI, odwołując je, jeśli integracja nie jest już potrzebna.
-   **Włącz CRON dla znaku wodnego:**

    -   **Co robi to ustawienie:** Aktywuje zaplanowane zadanie (CRON job) do automatycznego stosowania znaków wodnych na obrazach generowanych przez AI.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone:* Zadanie CRON będzie uruchamiane okresowo, stosując konfigurowalny znak wodny do oznaczonych obrazów.
        -   *Gdy wyłączone:* Nie będzie automatycznego znakowania wodnego.
    -   **Zalecana wartość:** NIE, chyba że wyraźnie wymagasz znakowania wodnego dla obrazów AI.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz mieć wizualny wskaźnik bezpośrednio na samym obrazie (np. małe logo „AI”) dla wszystkich obrazów produktów generowanych przez AI, włącz to.
-   **Obraz/tekst znaku wodnego:**

    -   **Co robi to ustawienie:** Definiuje znak wodny do zastosowania (np. plik obrazu lub ciąg tekstowy).
    -   **Skutek zmiany tego ustawienia:** Zadanie CRON użyje tego znaku wodnego.
    -   **Zalecana wartość:** Subtelny, wyraźny wskaźnik, jeśli używany.
    -   **Scenariusz / przykład dla sprzedawcy:** Prześlij mały, półprzezroczysty obraz „AI Generated” lub wprowadź „AI” jako tekst.

#### Zakładka Krótkie kody

-   **Lista krótkich kodów i użycie:**
    -   **Co robi to ustawienie:** Dostarcza listę dostępnych krótkich kodów, które można wstawić do opisów produktów, stron CMS lub innych obszarów tekstowych.
    -   **Skutek zmiany tego ustawienia:** Brak bezpośredniej zmiany, ale użycie tych krótkich kodów w Twojej treści wyświetli odpowiednie elementy ujawniające AI.
    -   **Zalecana wartość:** Użyj tych krótkich kodów, aby osadzić konkretne ujawnienia tam, gdzie ustawienia globalne mogą nie być wystarczające.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz mieć produkt, w którym tylko konkretny akapit opisu został wygenerowany przez AI. Możesz owinąć ten akapit krótkim kodem, aby wyświetlić obok niego małą odznakę.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 Ustawa o Sztucznej Inteligencji > Masowe zarządzanie produktami (AdminMyAiActBulkController)

-   **Nazwa ekranu i lokalizacja w menu:** W Panelu administracyjnym PrestaShop przejdź do **Ustawa o Sztucznej Inteligencji > Masowe zarządzanie produktami**.
-   **Dostępne działania i ustawienia:** Ten ekran zapewnia potężny widok siatki do zarządzania statusem zgodności z Ustawą o Sztucznej Inteligencji wielu produktów jednocześnie.
    -   **Lista produktów:** Wyświetla listę wszystkich Twoich produktów z kolumnami dla nazwy produktu, ID i, co najważniejsze, ich statusu zgodności z Ustawą o Sztucznej Inteligencji.
    -   **Filtry i wyszukiwanie:** Pozwala filtrować produkty według różnych kryteriów (np. kategoria, dostawca, status zgodności z Ustawą o Sztucznej Inteligencji), aby szybko znaleźć konkretne elementy.
    -   **Działania masowe:**
        -   **Oznacz jako generowane przez AI:** Wybierz wiele produktów i zastosuj do nich jednocześnie flagę „generowane przez AI”.
        -   **Usuń oznaczenie jako generowane przez AI:** Usuń flagę „generowane przez AI” z wybranych produktów.
        -   **Zastosuj konkretne tagi Ustawy o Sztucznej Inteligencji:** Przypisz niestandardowe tagi lub reguły (jeśli skonfigurowano) do wielu produktów.
-   **Skutek zmian:**
    -   Gdy oznaczysz produkty jako generowane przez AI, odznaki i ujawnienia w front office pojawią się dla tych produktów zgodnie z ogólnymi ustawieniami modułu.
    -   Usunięcie oznaczenia produktów usuwa te ujawnienia.
    -   Stosowanie tagów pozwala na bardziej szczegółową kontrolę nad konkretnymi typami ujawnień lub wiadomościami.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Po zaimportowaniu nowych produktów lub wygenerowaniu treści za pomocą AI, użyj filtrów, aby szybko zlokalizować te produkty.
    2.  Wybierz wszystkie odpowiednie produkty za pomocą pól wyboru.
    3.  Użyj masowej akcji „Oznacz jako generowane przez AI”, aby zastosować flagę.
    4.  Okresowo przeglądaj produkty, aby upewnić się, że ich status zgodności z Ustawą o Sztucznej Inteligencji jest dokładny.

#### 2.2.2 Ustawa o Sztucznej Inteligencji > Dzienniki audytu (AdminMyAiActLogsController)

-   **Nazwa ekranu i lokalizacja w menu:** W Panelu administracyjnym PrestaShop przejdź do **Ustawa o Sztucznej Inteligencji > Dzienniki audytu**.
-   **Dostępne działania i ustawienia:** Ten ekran wyświetla szczegółowy dziennik wszystkich zdarzeń i ujawnień związanych z Ustawą o Sztucznej Inteligencji, pod warunkiem, że ustawienie „Włącz dziennik audytu” jest aktywne.
    -   **Wpisy dziennika:** Każdy wpis zazwyczaj zawiera:
        -   **Sygnatura czasowa:** Kiedy zdarzenie miało miejsce.
        -   **Akcja/Zdarzenie:** Co się stało (np. „Produkt X oznaczony jako AI”, „Odznaka AI wyświetlona dla Produktu Y”).
        -   **Użytkownik/System:** Kto zainicjował akcję (np. „Użytkownik administracyjny Z”, „Zadanie CRON”, „Odwiedzający Front Office”).
        -   **ID produktu/Kontekst:** Który produkt lub encja została dotknięta.
        -   **Szczegóły:** Wszelkie dodatkowe istotne informacje.
    -   **Filtry i wyszukiwanie:** Pozwala filtrować wpisy dziennika według zakresu dat, typu zdarzenia lub produktu, aby zbadać konkretne incydenty.
-   **Skutek zmian:** Ten ekran służy tylko do przeglądania; nie można tutaj bezpośrednio wprowadzać zmian. Służy jako zapis historyczny.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Regularnie przeglądaj dzienniki audytu, zwłaszcza po wprowadzeniu znaczących zmian w ustawieniach Ustawy o Sztucznej Inteligencji lub danych produktów, aby upewnić się, że wszystko działa zgodnie z oczekiwaniami.
    2.  W przypadku audytu zgodności lub zapytania klienta, użyj tego dziennika, aby pobrać konkretne zdarzenia ujawnienia.

#### 2.2.3 Ustawa o Sztucznej Inteligencji > Studio Układu (AdminMyAiActLayoutsController - *Wywnioskowano z szablonów i opisu*)

-   **Nazwa ekranu i lokalizacja w menu:** W Panelu administracyjnym PrestaShop przejdź do **Ustawa o Sztucznej Inteligencji > Studio Układu** (lub podobnie, w zależności od struktury menu modułu).
-   **Dostępne działania i ustawienia:** Ten ekran służy do projektowania i zarządzania wyglądem wizualnym odznak ujawniających AI i innych elementów.
    -   **Lista układów:** Tabela pokazująca wszystkie istniejące układy odznak.
    -   **Dodaj nowy układ / Edytuj układ:**
        -   **Nazwa układu:** Opisowa nazwa dla Twojego układu.
        -   **Typ odznaki:** Wybierz między tylko ikoną, tylko tekstem lub ikoną + tekstem.
        -   **Wybór ikony:** Wybierz z katalogu ikon lub prześlij własną.
        -   **Treść tekstowa:** Wprowadź tekst do wyświetlenia na odznace (np. „Generowane przez AI”).
        -   **Opcje stylizacji:**
            -   **Kolory:** Kolor tła, kolor tekstu, kolor ikony.
            -   **Ramki:** Styl ramki, szerokość, kolor.
            -   **Cienie:** Efekty cienia.
            -   **Gradienty:** Opcje gradientu tła.
            -   **Wypełnienie i marginesy:** Odstępy wokół odznaki.
            -   **Ustawienia czcionki:** Rozmiar czcionki, waga.
        -   **Podgląd:** Podgląd na żywo Twojej odznaki podczas jej projektowania.
-   **Skutek zmian:**
    -   Tworzenie nowych układów daje więcej opcji wyglądu Twoich ujawnień AI.
    -   Edycja istniejącego układu natychmiast zaktualizuje wygląd wszystkich odznak używających tego układu w całym Twoim sklepie.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Zacznij od domyślnego układu i dostosuj go do estetyki Twojej marki.
    2.  W razie potrzeby utwórz różne układy dla różnych typów ujawnień AI (np. jeden dla obrazów AI, inny dla tekstu AI).
    3.  Przetestuj układy na różnych urządzeniach, aby upewnić się, że są widoczne i dobrze wyglądają.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz zgodność z Ustawą o Sztucznej Inteligencji | TAK | Główny przełącznik dla wszystkich funkcji modułu. |
| | Wyświetlaj odznakę ujawniającą AI na stronach produktów | TAK | Pokazuje odznakę na stronach szczegółów produktu. |
| | Wyświetlaj odznakę ujawniającą AI na listach produktów | TAK | Pokazuje odznakę na stronach kategorii/wyszukiwania. |
| | Pozycja odznaki ujawniającej AI (strona produktu) | *Zależne od szablonu* | Kontroluje umiejscowienie odznaki na stronach produktów. |
| | Układ odznaki ujawniającej AI | *Możliwość dostosowania* | Styl wizualny odznaki AI. |
| | Link do strony polityki AI | *URL Twojej strony CMS* | Link do polityki AI Twojego sklepu. |
| | Włącz baner ujawniający AI | TAK | Aktywuje baner informacyjny na całej stronie. |
| | Pozycja banera ujawniającego AI (Hook) | `displayHeader` | Umiejscowienie banera (np. góra/dół strony). |
| | Treść banera ujawniającego AI | *Możliwość dostosowania tekstu/HTML* | Wiadomość wyświetlana w banerze. |
| | Włącz informacje o ludzkim wsparciu | TAK | Wyświetla wiadomość o nadzorze człowieka. |
| | Wiadomość o ludzkim wsparciu | *Możliwość dostosowania tekstu* | Treść wiadomości o ludzkim wsparciu. |
| | Włącz dziennik audytu | TAK | Rejestruje wszystkie działania związane z Ustawą o Sztucznej Inteligencji w celu zgodności. |
| | Włącz REST API | NIE | Aktywuje API dla zewnętrznych integracji. |
| | Zarządzanie kluczami API | *N/A* | Generuj/zarządzaj kluczami API dla bezpiecznego dostępu. |
| | Włącz CRON dla znaku wodnego | NIE | Automatycznie znakuje wodnym obrazami generowanymi przez AI. |
| | Obraz/tekst znaku wodnego | *N/A* | Definiuje zawartość znaku wodnego. |
| | Lista krótkich kodów i użycie | *N/A* | Dostarcza krótkie kody do szczegółowego ujawniania treści. |
| **Ustawa o Sztucznej Inteligencji > Masowe zarządzanie produktami** | Oznacz jako generowane przez AI (Akcja masowa) | N/A | Oznacza wiele produktów jako generowane przez AI. |
| | Usuń oznaczenie jako generowane przez AI (Akcja masowa) | N/A | Usuwa flagę generowane przez AI z produktów. |
| | Zastosuj konkretne tagi Ustawy o Sztucznej Inteligencji (Akcja masowa) | N/A | Przypisuje niestandardowe tagi ujawnienia do produktów. |
| **Ustawa o Sztucznej Inteligencji > Dzienniki audytu** | Przeglądaj wpisy dziennika | N/A | Dostarcza historyczny zapis zdarzeń Ustawy o Sztucznej Inteligencji. |
| **Ustawa o Sztucznej Inteligencji > Studio Układu** | Twórz/Edytuj układy | N/A | Projektuj niestandardowe style wizualne dla odznak AI. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Skonfigurowałem moduł, ale nie widzę żadnych odznak ani banerów AI w moim sklepie. Co jest nie tak?**
O1:

-   **Sprawdź główny przełącznik:** Najpierw upewnij się, że „Włącz zgodność z Ustawą o Sztucznej Inteligencji” jest ustawione na TAK w głównej konfiguracji modułu.
-   **Przełączniki poszczególnych funkcji:** Sprawdź, czy „Wyświetlaj odznakę ujawniającą AI na stronach produktów”, „Wyświetlaj odznakę ujawniającą AI na listach produktów” i „Włącz baner ujawniający AI” są również ustawione na TAK, jeśli chcesz, aby te funkcje były aktywne.
-   **Status produktu:** Aby odznaki się pojawiły, produkty muszą być wyraźnie oznaczone jako „generowane przez AI”. Sprawdź to na stronie edycji produktu (w dedykowanej zakładce) lub za pośrednictwem „Ustawa o Sztucznej Inteligencji > Masowe zarządzanie produktami”.
-   **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) i pamięć podręczną przeglądarki. Czasami wyświetlana jest stara zawartość.
-   **Kompatybilność z szablonem:** Chociaż moduł jest zaprojektowany tak, aby był kompatybilny, niektóre bardzo dostosowane szablony mogą wymagać drobnych korekt. Sprawdź konsolę deweloperską przeglądarki pod kątem błędów JavaScript.

**P2: Odznaka AI pojawia się, ale nie wygląda dobrze z projektem mojego szablonu. Jak mogę zmienić jej wygląd?**
O2:

-   **Studio Układu:** Przejdź do **Ustawa o Sztucznej Inteligencji > Studio Układu** w Panelu administracyjnym. Tutaj możesz tworzyć i edytować układy odznak. Masz szerokie opcje kolorów, ikon, tekstu, cieni i gradientów.
-   **Wybierz układ:** Po utworzeniu lub edycji układu, wróć do głównej konfiguracji modułu i wybierz żądany układ w sekcji „Układ odznaki ujawniającej AI”.
-   **Nadpisywanie CSS (zaawansowane):** Jeśli Studio Układu nie oferuje wystarczającej personalizacji, webmaster może użyć niestandardowego CSS w Twoim szablonie, aby nadpisać domyślne style modułu (patrz sekcja 7.5 dla lokalizacji plików CSS).

**P3: Jak efektywnie oznaczyć produkty jako generowane przez AI, zwłaszcza jeśli mam ich wiele?**
O3:

-   **Masowe zarządzanie produktami:** Przejdź do **Ustawa o Sztucznej Inteligencji > Masowe zarządzanie produktami**. Ten ekran pozwala filtrować produkty i wybierać wiele elementów, aby oznaczyć je lub usunąć oznaczenie jako generowane przez AI za jednym razem. Jest to najbardziej efektywna metoda dla dużych katalogów.
-   **Indywidualna strona produktu:** Dla pojedynczych produktów znajdziesz dedykowaną zakładkę (np. „Zgodność z Ustawą o Sztucznej Inteligencji”) podczas edycji produktu w Panelu administracyjnym, gdzie możesz przełączać jego status AI.

**P4: Chcę przedstawić szczegółowe wyjaśnienie mojej polityki AI. Gdzie powinienem to umieścić?**
O4:

-   **Dedykowana strona CMS:** Utwórz nową stronę CMS (Wygląd > Strony) zatytułowaną na przykład „Nasza polityka przejrzystości AI” lub „Jak używamy AI”. Napisz tutaj swoją kompleksową politykę.
-   **Link w module:** W głównej konfiguracji modułu ustaw „Link do strony polityki AI” na adres URL nowo utworzonej strony CMS. Ten link będzie następnie używany przez banery i odznaki do kierowania klientów do Twojej polityki.

**P5: Zadanie CRON dla znaku wodnego nie działa. Co powinienem sprawdzić?**
O5:

-   **Włącz CRON dla znaku wodnego:** Upewnij się, że „Włącz CRON dla znaku wodnego” jest ustawione na TAK w konfiguracji modułu.
-   **Konfiguracja zadania CRON:** Sprawdź, czy samo zadanie CRON jest poprawnie skonfigurowane na Twoim serwerze. Moduł zazwyczaj dostarcza dokładną linię poleceń do dodania do menedżera CRON Twojego panelu hostingowego. Jeśli nie jesteś pewien, skontaktuj się z dostawcą hostingu lub webmasterem.
-   **Uprawnienia:** Upewnij się, że moduł i foldery obrazów mają poprawne uprawnienia do zapisu.
-   **Dzienniki błędów:** Sprawdź dzienniki błędów PHP serwera i tryb debugowania PrestaShop pod kątem wszelkich powiązanych błędów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „My AI Act Pro” jest zgodny ze standardową architekturą MVC (Model-View-Controller) PrestaShop. Wykorzystuje `ObjectModel` do interakcji z bazą danych, rejestruje różne hooki do wyświetlania w front-office i zawiera dedykowane kontrolery administracyjne do konfiguracji i zarządzania danymi. Moduł wprowadza kilka niestandardowych klas do hermetyzacji specyficznej logiki biznesowej związanej ze zgodnością z Ustawą o Sztucznej Inteligencji, takiej jak obsługa API, zarządzanie układem odznak i logowanie audytu. Zawiera również kontrolery frontowe do wykonywania API i zadań CRON, umożliwiając zewnętrzne integracje i zaplanowane zadania.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `controllers/front/api.php`
    -   **Nazwa klasy i klasa nadrzędna:** `MyaiactproApiModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler obsługuje punkty końcowe REST API modułu. Przetwarza przychodzące żądania (np. oznaczanie produktów jako generowanych przez AI, pobieranie statusu AI) i zwraca odpowiedzi JSON. Jest odpowiedzialny za walidację klucza API i przekazywanie żądań do odpowiednich metod klasy `AiActApi`.
-   `controllers/front/cron.php`
    -   **Nazwa klasy i klasa nadrzędna:** `MyaiactproCronModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler służy jako punkt końcowy dla zadań CRON modułu, w szczególności do stosowania znaku wodnego. Po uzyskaniu dostępu za pośrednictwem zaplanowanego zadania, uruchamia proces znakowania wodnego dla obrazów generowanych przez AI.
-   `controllers/front/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `MyaiactproIndexModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Zastępczy lub domyślny kontroler frontowy. W wielu modułach może obsługiwać domyślną trasę lub przekierowanie. Dla tego modułu może to być awaryjne rozwiązanie lub używane do specyficznych, prostych interakcji front-office nieobjętych przez `api.php` lub `cron.php`.

#### Kontrolery administracyjne Back-Office

-   `controllers/admin/AdminMyAiActBulkController.php`
    -   **Nazwa zakładki i zarządzana encja:** Dostępne przez **Ustawa o Sztucznej Inteligencji > Masowe zarządzanie produktami**. Zarządza encją `product` pośrednio, umożliwiając masowe aktualizacje ich statusu zgodności z Ustawą o Sztucznej Inteligencji.
    -   **Odpowiedzialność:** Zapewnia interfejs siatki do wyświetlania produktów i stosowania masowych działań związanych ze zgodnością z Ustawą o Sztucznej Inteligencji (np. oznaczanie produktów jako generowanych przez AI, stosowanie tagów). Obsługuje przesyłanie formularzy dla masowych aktualizacji.
-   `controllers/admin/AdminMyAiActLogsController.php`
    -   **Nazwa zakładki i zarządzana encja:** Dostępne przez **Ustawa o Sztucznej Inteligencji > Dzienniki audytu**. Zarządza encją `aiact_audit_log`.
    -   **Odpowiedzialność:** Wyświetla paginowaną listę wpisów dziennika audytu, zapewniając historyczny zapis zdarzeń związanych z Ustawą o Sztucznej Inteligencji. Obsługuje filtrowanie i przeglądanie szczegółów dziennika.
-   `controllers/admin/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `MyaiactproAdminIndexModuleAdminController` rozszerza `ModuleAdminController`.
    -   **Nazwa zakładki i zarządzana encja:** Zazwyczaj domyślny lub wprowadzający kontroler administracyjny dla głównego wpisu menu modułu.
    -   **Odpowiedzialność:** Może służyć jako przekierowanie do głównej konfiguracji lub pulpitu nawigacyjnego modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   `classes/AiActApi.php`
    -   **Tabela bazy danych:** Brak bezpośredniej interakcji z tabelą, ale współpracuje z `AiActApiKey` i `AiActAuditLog`.
    -   **Rozszerza `ObjectModel`:** Nie.
    -   **Kluczowe metody publiczne:** Obsługuje parsowanie żądań API, uwierzytelnianie i przekazuje działania do aktualizacji statusu AI produktu.
-   `classes/AiActApiDocumentation.php`
    -   **Tabela bazy danych:** Brak.
    -   **Rozszerza `ObjectModel`:** Nie.
    -   **Kluczowe metody publiczne:** Generuje i dostarcza dokumentację dla REST API modułu, zazwyczaj do wyświetlania w Panelu administracyjnym.
-   `classes/AiActApiKey.php`
    -   **Tabela bazy danych:** `ps_myaiactpro_api_key`
    -   **Rozszerza `ObjectModel`:** Tak.
    -   **Pola `$definition`:** `id_myaiactpro_api_key`, `key_value`, `description`, `active`, `date_add`, `date_upd`.
    -   **Kluczowe metody publiczne:** Zarządza tworzeniem, pobieraniem, walidacją i usuwaniem kluczy API dla bezpiecznego dostępu do API.
-   `classes/AiActAuditLog.php`
    -   **Tabela bazy danych:** `ps_myaiactpro_audit_log`
    -   **Rozszerza `ObjectModel`:** Tak.
    -   **Pola `$definition`:** `id_myaiactpro_audit_log`, `id_employee`, `id_customer`, `id_product`, `action`, `details`, `ip_address`, `date_add`.
    -   **Kluczowe metody publiczne:** Rejestruje i pobiera wpisy dziennika audytu dla działań zgodności z Ustawą o Sztucznej Inteligencji.
-   `classes/AiActBadgeLayout.php`
    -   **Tabela bazy danych:** `ps_myaiactpro_badge_layout`
    -   **Rozszerza `ObjectModel`:** Tak.
    -   **Pola `$definition`:** `id_myaiactpro_badge_layout`, `name`, `type`, `icon_class`, `text_content`, `styles_json`, `active`.
    -   **Kluczowe metody publiczne:** Zarządza tworzeniem, przechowywaniem i pobieraniem niestandardowych układów wizualnych dla odznak ujawniających AI.
-   `classes/AiActConfigureUi.php`
    -   **Tabela bazy danych:** Brak.
    -   **Rozszerza `ObjectModel`:** Nie.
    -   **Kluczowe metody publiczne:** Klasa pomocnicza do budowania i renderowania formularzy konfiguracyjnych modułu w Panelu administracyjnym, abstrahująca elementy interfejsu użytkownika.
-   `classes/AiActDisplayResolver.php`
    -   **Tabela bazy danych:** Brak.
    -   **Rozszerza `ObjectModel`:** Nie.
    -   **Kluczowe metody publiczne:** Określa, które ujawnienia Ustawy o Sztucznej Inteligencji (odznaki, banery itp.) powinny być wyświetlane w front office na podstawie ustawień modułu, statusu produktu i bieżącego kontekstu.
-   `classes/AiActFlag.php`
    -   **Tabela bazy danych:** `ps_myaiactpro_product_flag` (lub podobna, łącząca produkty ze statusem AI)
    -   **Rozszerza `ObjectModel`:** Tak (prawdopodobnie, lub niestandardowa klasa zarządzająca relacjami statusu produktu-AI).
    -   **Pola `$definition`:** `id_product`, `is_ai_generated`, `id_myaiactpro_badge_layout`, `date_add`, `date_upd`.
    -   **Kluczowe metody publiczne:** Zarządza statusem generowania przez AI poszczególnych produktów i ich powiązanymi układami odznak.
-   `classes/AiActIconCatalog.php`
    -   **Tabela bazy danych:** Brak.
    -   **Rozszerza `ObjectModel`:** Nie.
    -   **Kluczowe metody publiczne:** Dostarcza listę lub katalog dostępnych ikon do użycia w układach odznak, często integrując się z Font Awesome lub podobnymi bibliotekami ikon.
-   `classes/AiActShortcode.php`
    -   **Tabela bazy danych:** Brak.
    -   **Rozszerza `ObjectModel`:** Nie.
    -   **Kluczowe metody publiczne:** Przetwarza i renderuje niestandardowe krótkie kody osadzone w treści, zastępując je elementami ujawniającymi AI.
-   `classes/AiActTagRule.php`
    -   **Tabela bazy danych:** `ps_myaiactpro_tag_rule` (lub podobna dla niestandardowych tagów/reguł)
    -   **Rozszerza `ObjectModel`:** Tak.
    -   **Pola `$definition`:** `id_myaiactpro_tag_rule`, `name`, `description`, `badge_layout_id`, `active`.
    -   **Kluczowe metody publiczne:** Zarządza niestandardowymi regułami lub tagami, które można zastosować do produktów dla bardziej specyficznych ujawnień AI poza prostą flagą „generowane przez AI”.
-   `classes/index.php`
    -   **Tabela bazy danych:** Brak.
    -   **Rozszerza `ObjectModel`:** Nie.
    -   **Kluczowe metody publiczne:** Zazwyczaj pusty plik, aby zapobiec listowaniu katalogu.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    -   **Zakres:** Back-office (prawdopodobnie do wyszukiwania produktów w masowym zarządzaniu).
    -   **Opis:** Zapewnia funkcjonalność autouzupełniania dla pól wejściowych, zazwyczaj używaną w formularzach administracyjnych do wyszukiwania produktów, kategorii lub innych encji.
-   `views/js/admin_api.js`
    -   **Zakres:** Back-office (zakładka API i Integracje).
    -   **Opis:** Obsługuje interakcje po stronie klienta dla interfejsu zarządzania kluczami API, w tym generowanie nowych kluczy, odwoływanie kluczy i wyświetlanie modalnych okien dokumentacji API.
-   `views/js/admin_icon_picker.js`
    -   **Zakres:** Back-office (Studio Układu).
    -   **Opis:** Zarządza interfejsem wyboru ikon w Studio Układu, umożliwiając administratorom przeglądanie i wybieranie ikon dla odznak.
-   `views/js/admin_layouts.js`
    -   **Zakres:** Back-office (Studio Układu).
    -   **Opis:** Obsługuje interfejs Studio Układu, zarządzając aktualizacjami podglądu w czasie rzeczywistym, dostosowaniami stylu (kolory, cienie, gradienty) i przesyłaniem formularzy dla układów odznak.
-   `views/js/front.js`
    -   **Zakres:** Front-office.
    -   **Opis:** Zawiera logikę po stronie klienta do wyświetlania i interakcji z elementami ujawniającymi AI w front office. Może to obejmować:
        -   Inicjalizację podpowiedzi lub wyskakujących okienek odznak.
        -   Obsługę zdarzeń kliknięcia na odznakach w celu ujawnienia więcej informacji lub nawigacji do strony polityki AI.
        -   Zapewnienie responsywności mobilnej elementów ujawniających.
-   `views/js/tinymce_ai_button.js`
    -   **Zakres:** Back-office (edytor produktu/CMS).
    -   **Opis:** Integruje niestandardowy przycisk z edytorem TinyMCE (używanym do opisów produktów i stron CMS) w celu łatwego wstawiania krótkich kodów Ustawy o Sztucznej Inteligencji.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`
    -   **Zakres:** Back-office.
    -   **Opis:** Style dla pól wejściowych wyszukiwania autouzupełniania i ich wyników rozwijanych, używane w formularzach administracyjnych.
-   `views/css/admin.css`
    -   **Zakres:** Stylizacja formularzy administracyjnych Back-office.
    -   **Opis:** Zawiera ogólne reguły stylizacji dla interfejsów Back Office modułu, w tym strony konfiguracji, masowego zarządzania, dzienników audytu i studia układu. Programiści mogą nadpisywać klasy takie jak `.myaiactpro-admin-form`, `.myaiactpro-layout-preview` itp.
-   `views/css/front.css`
    -   **Zakres:** Stylizacja klienta Front-office.
    -   **Opis:** Zapewnia domyślną stylizację dla odznak ujawniających AI, banerów i innych elementów front-office. Kluczowe selektory klas CSS, które programiści mogą nadpisywać w swoim szablonie, to:
        -   `.myaiactpro-badge` (dla głównego kontenera odznaki)
        -   `.myaiactpro-badge-icon` (dla ikony w odznace)
        -   `.myaiactpro-badge-text` (dla tekstu w odznace)
        -   `.myaiactpro-banner` (dla banera ujawniającego na całej stronie)
        -   `.myaiactpro-additional-info` (dla dodatkowych bloków informacyjnych)
        -   `.myaiactpro-human-fallback` (dla wiadomości o ludzkim wsparciu)

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `hook/additional_info.tpl`
    -   **Hook:** Potencjalnie `displayProductExtraContent` lub niestandardowy hook.
    -   **Wyjście:** Renderuje dodatkowy blok informacyjny na stronie produktu, często używany do szczegółowych ujawnień AI lub linków do polityki.
-   `hook/ai_badge.tpl`
    -   **Hook:** `displayProductListReviews`, `displayProductButtons`, `displayProductPriceBlock` lub niestandardowe hooki.
    -   **Wyjście:** Renderuje odznakę ujawniającą AI na stronach produktów lub listach, używając wybranego układu.
-   `hook/banner.tpl`
    -   **Hook:** `displayHeader`, `displayFooter`.
    -   **Wyjście:** Renderuje baner ujawniający AI na całej stronie.
-   `hook/human_fallback.tpl`
    -   **Hook:** Potencjalnie `displayProductExtraContent` lub niestandardowy hook.
    -   **Wyjście:** Renderuje wiadomość o ludzkim wsparciu na odpowiednich stronach.
-   `hook/shortcode_badge.tpl`
    -   **Hook:** Renderowany dynamicznie przez klasę `AiActShortcode`.
    -   **Wyjście:** Renderuje konkretną odznakę AI, gdy w treści używany jest krótki kod.

#### Szablony administracyjne (`views/templates/admin/`)

-   `admin/api.tpl`
    -   **Cel:** Renderuje panel konfiguracji API i Integracji, w tym zarządzanie kluczami API i dokumentację.
-   `admin/bulk_intro.tpl`
    -   **Cel:** Dostarcza wiadomość wprowadzającą lub instrukcje dla ekranu masowego zarządzania produktami.
-   `admin/configure.tpl`
    -   **Cel:** Główny szablon konfiguracji modułu, renderowany przez `getContent()`, zawierający ogólne ustawienia, przełączniki funkcji i linki do innych ekranów administracyjnych.
-   `admin/configure_shell.tpl`
    -   **Cel:** Szablon opakowujący lub powłoka dla głównej strony konfiguracji, zapewniający spójny układ.
-   `admin/cron_box.tpl`
    -   **Cel:** Wyświetla informacje związane z konfiguracją zadania CRON, w tym polecenie CRON.
-   `admin/layouts_form.tpl`
    -   **Cel:** Renderuje formularz do tworzenia lub edytowania układu odznaki AI w Studio Układu.
-   `admin/layouts_list.tpl`
    -   **Cel:** Wyświetla listę istniejących układów odznak AI w Studio Układu.
-   `admin/mass_settings.tpl`
    -   **Cel:** Renderuje interfejs do stosowania masowych ustawień lub działań na produktach, używany w kontrolerze masowego zarządzania.
-   `admin/overrides_entity.tpl`
    -   **Cel:** Prawdopodobnie do zarządzania konkretnymi nadpisaniami lub wyjątkami dla reguł Ustawy o Sztucznej Inteligencji na podstawie encji (np. na kategorię, na producenta).
-   `admin/overrides_fields.tpl`
    -   **Cel:** Renderuje pola formularza do definiowania reguł nadpisywania.
-   `admin/overrides_list.tpl`
    -   **Cel:** Wyświetla listę skonfigurowanych reguł nadpisywania.
-   `admin/partials/gradient_editor.tpl`
    -   **Cel:** Częściowy szablon dla edytora/wyboru koloru gradientu używanego w Studio Układu.
-   `admin/partials/icon_picker.tpl`
    -   **Cel:** Częściowy szablon dla interfejsu wyboru ikon używanego w Studio Układu.
-   `admin/partials/shadow_editor.tpl`
    -   **Cel:** Częściowy szablon dla edytora efektów cienia używanego w Studio Układu.
-   `admin/product_tab.tpl`
    -   **Cel:** Renderuje zawartość dedykowanej zakładki „Zgodność z Ustawą o Sztucznej Inteligencji” na stronie edycji produktu PrestaShop.
-   `admin/shortcodes.tpl`
    -   **Cel:** Wyświetla listę dostępnych krótkich kodów i instrukcje ich użycia.
-   `admin/_api_documentation_modal.tpl`
    -   **Cel:** Renderuje zawartość wyskakującego okna modalnego wyświetlającego dokumentację API.

#### Szablony Front-office (`views/templates/front/`)

-   Brak jawnie wymienionych jako samodzielne szablony stron, co wskazuje, że zawartość front-office jest renderowana głównie za pośrednictwem hooków.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

-   `ps_myaiactpro_api_key`: Przechowuje klucze API dla REST API modułu.
    -   `id_myaiactpro_api_key` (PK)
    -   `key_value` (VARCHAR)
    -   `description` (TEXT)
    -   `active` (TINYINT)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_myaiactpro_audit_log`: Rejestruje zdarzenia związane z Ustawą o Sztucznej Inteligencji.
    -   `id_myaiactpro_audit_log` (PK)
    -   `id_employee` (INT)
    -   `id_customer` (INT)
    -   `id_product` (INT)
    -   `action` (VARCHAR)
    -   `details` (TEXT)
    -   `ip_address` (VARCHAR)
    -   `date_add` (DATETIME)
-   `ps_myaiactpro_badge_layout`: Przechowuje niestandardowe układy wizualne dla odznak AI.
    -   `id_myaiactpro_badge_layout` (PK)
    -   `name` (VARCHAR)
    -   `type` (VARCHAR)
    -   `icon_class` (VARCHAR)
    -   `text_content` (VARCHAR)
    -   `styles_json` (TEXT)
    -   `active` (TINYINT)
-   `ps_myaiactpro_product_flag`: Łączy produkty z ich statusem generowania przez AI i wybranym układem odznaki.
    -   `id_product` (PK, INT)
    -   `is_ai_generated` (TINYINT)
    -   `id_myaiactpro_badge_layout` (INT, FK do `ps_myaiactpro_badge_layout`)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_myaiactpro_tag_rule`: Przechowuje niestandardowe reguły tagów Ustawy o Sztucznej Inteligencji.
    -   `id_myaiactpro_tag_rule` (PK)
    -   `name` (VARCHAR)
    -   `description` (TEXT)
    -   `badge_layout_id` (INT, FK do `ps_myaiactpro_badge_layout`)
    -   `active` (TINYINT)
-   Rekordy konfiguracji w `ps_configuration`: Ustawienia modułu są przechowywane tutaj (np. `MYAIACTPRO_ENABLED`, `MYAIACTPRO_BADGE_LAYOUT_ID`, `MYAIACTPRO_POLICY_LINK`).

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny | Renderowane szablony |
| --- | --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykiwanie CSS/JS, renderowanie górnego banera. | `hook/banner.tpl` (jeśli skonfigurowano) |
| `displayFooter` | Na dole każdej strony. | Renderowanie dolnego banera, wstrzykiwanie JS. | `hook/banner.tpl` (jeśli skonfigurowano) |
| `displayProductAdditionalInfo` | Na stronie produktu, zazwyczaj poniżej opisu. | Wyświetlanie dodatkowych informacji o ujawnieniu AI. | `hook/additional_info.tpl`, `hook/human_fallback.tpl` |
| `displayProductListReviews` | W listach produktów, w pobliżu nazwy/obrazu produktu. | Wyświetlanie odznaki AI na miniaturach produktów. | `hook/ai_badge.tpl` |
| `displayProductButtons` | Na stronie produktu, w pobliżu przycisku dodaj do koszyka. | Wyświetlanie odznaki AI na stronie produktu. | `hook/ai_badge.tpl` |
| `displayAdminProductsExtra` | Na stronie edycji produktu w Panelu administracyjnym. | Dodanie dedykowanej zakładki dla ustawień Ustawy o Sztucznej Inteligencji. | `admin/product_tab.tpl` |
| `actionProductUpdate` | Po zaktualizowaniu produktu w Panelu administracyjnym. | Aktualizacja flag/statusu Ustawy o Sztucznej Inteligencji dla produktu. | N/A |
| `actionProductDelete` | Po usunięciu produktu. | Czyszczenie powiązanych danych Ustawy o Sztucznej Inteligencji. | N/A |
| `actionFrontControllerSetMedia` | Przed renderowaniem treści przez kontroler frontowy. | Rejestrowanie CSS/JS front-office. | N/A |
| `actionAdminControllerSetMedia` | Przed renderowaniem treści przez kontroler administracyjny. | Rejestrowanie CSS/JS back-office. | N/A |
| `actionRegisterShortcode` | Podczas instalacji/aktualizacji modułu. | Rejestruje niestandardowe krótkie kody do parsowania treści. | N/A |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony administracyjnej. | Wstrzykiwanie CSS/JS administracyjnego. | N/A |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów lub pytań dotyczących modułu „My AI Act Pro - Artificial Intelligence Compliance”.
