---
title: "Snapchat Pixel & Conversions API - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Snapchat Pixel & Conversions API od MyPresta.eu."
sidebar:
  label: "Snapchat Pixel & Conversions API - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Snapchat Pixel & Conversions API na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/snapchat-pixel-conversions-api.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/snapchat-pixel-conversions-api/)
>
> ---


# Snapchat Pixel & Conversions API

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Są one zazwyczaj domyślnie włączone w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji, na którym skonfigurujesz swój Snapchat Pixel i Conversions API. Moduł zapewnia przyjazny dla użytkownika interfejs z różnymi sekcjami, które poprowadzą Cię przez konfigurację.

#### **1. Ustawienia ogólne i tryb śledzenia**

-   **Tryb śledzenia:**

    *   **Co robi to ustawienie:** Określa, w jaki sposób Twój sklep wysyła dane do Snapchata. Możesz wybrać między śledzeniem po stronie klienta (Pixel), po stronie serwera (Conversions API) lub podejściem hybrydowym.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Tylko Pixel:* Tylko Snap Pixel (kod JavaScript w przeglądarce) będzie śledził zdarzenia. Jest to prostsze, ale bardziej podatne na blokery reklam i ograniczenia przeglądarek.
        *   *Tylko Conversions API:* Będzie używane tylko śledzenie po stronie serwera. Jest to bardziej niezawodne pod względem prywatności i dokładności danych, ale wymaga solidnej konfiguracji serwera.
        *   *Hybrydowy (zalecane):* Zarówno Pixel, jak i CAPI będą śledzić zdarzenia. Moduł automatycznie deduplikuje zdarzenia za pomocą wspólnego `event_id`, zapewniając dokładne raportowanie przy jednoczesnym maksymalizowaniu przechwytywania danych. Jest to ogólnie najbardziej niezawodna i zalecana opcja.
    *   **Zalecana wartość:** `Hybrydowy`
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli dopiero zaczynasz, „Tylko Pixel” jest szybki. W przypadku poważnych reklam, „Hybrydowy” daje Ci to, co najlepsze z obu światów, zapewniając przechwytywanie jak największej ilości dokładnych danych do optymalizacji kampanii.
-   **ID Snap Pixela:**

    *   **Co robi to ustawienie:** Jest to Twój unikalny identyfikator Snap Pixela. Informuje Snapchata, z którym kontem reklamowym należy powiązać śledzone zdarzenia.
    *   **Wpływ zmiany tego ustawienia:** Jeśli jest nieprawidłowy lub pusty, nie będzie śledzenia po stronie klienta, a Twoje reklamy na Snapchacie nie będą w stanie śledzić odwiedzających witrynę ani konwersji.
    *   **Zalecana wartość:** Twój ID Snap Pixela (np. `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`). Możesz go znaleźć w Menedżerze reklam Snapchata.
    *   **Scenariusz/przykład dla sprzedawcy:** Utworzyłeś konto reklamowe na Snapchacie i musisz połączyć z nim swój sklep. Wprowadź tutaj ID Pixela dostarczony przez Snapchata.
-   **Token Conversions API:**

    *   **Co robi to ustawienie:** Jest to bezpieczny token, który umożliwia Twojemu serwerowi wysyłanie danych bezpośrednio do Conversions API Snapchata. Uwierzytelnia on Twoje żądania po stronie serwera.
    *   **Wpływ zmiany tego ustawienia:** Jeśli jest nieprawidłowy lub pusty, nie będzie śledzenia po stronie serwera. Oznacza to, że tracisz korzyści związane ze zwiększoną niezawodnością i prywatnością CAPI.
    *   **Zalecana wartość:** Twój Token Conversions API. Generujesz go w Menedżerze reklam Snapchata.
    *   **Scenariusz/przykład dla sprzedawcy:** Aby zapewnić niezawodne wysyłanie danych o zakupach do Snapchata, nawet jeśli klient używa blokera reklam, musisz skonfigurować i wprowadzić tutaj swój token CAPI.

#### **2. Śledzenie zdarzeń i jakość danych**

-   **Włącz zaawansowane dopasowywanie:**

    *   **Co robi to ustawienie:** Umożliwia modułowi wysyłanie dodatkowych danych klienta (takich jak e-mail, numer telefonu, imię) do Snapchata, bezpiecznie zaszyfrowanych, w celu poprawy dopasowywania zdarzeń i budowania odbiorców.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Włączone:* Snapchat może dokładniej dopasowywać odwiedzających witrynę do ich profili na Snapchacie, poprawiając targetowanie odbiorców i atrybucję reklam.
        *   *Wyłączone:* Wysyłanych jest mniej danych, co potencjalnie zmniejsza dokładność dopasowywania odbiorców i optymalizacji kampanii.
    *   **Zalecana wartość:** `TAK` (chyba że masz ścisłe obawy dotyczące prywatności, które przeważają nad korzyściami).
    *   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby Snapchat był jak najbardziej skuteczny w znajdowaniu klientów podobnych do Twoich obecnych. Włączenie tej opcji pomaga Snapchatowi precyzyjniej identyfikować użytkowników.
-   **Integracja zarządzania zgodą:**

    *   **Co robi to ustawienie:** Integruje się z popularnymi modułami zgody na pliki cookie (np. modułami RODO), aby zapewnić, że śledzenie Snapchata odbywa się tylko po wyraźnej zgodzie klienta.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Włączone:* Moduł będzie czekał na zgodę przed zainicjowaniem Snap Pixela lub wysłaniem zdarzeń CAPI, które wymagają danych użytkownika.
        *   *Wyłączone:* Śledzenie będzie odbywać się niezależnie od zgody użytkownika, co może prowadzić do problemów z zgodnością z przepisami dotyczącymi prywatności w niektórych regionach.
    *   **Zalecana wartość:** `TAK` (wysoce zalecane dla RODO, CCPA i innych przepisów dotyczących prywatności).
    *   **Scenariusz/przykład dla sprzedawcy:** Twój sklep działa w UE i musi być zgodny z RODO. Włączenie tej opcji zapewnia, że śledzisz tylko użytkowników, którzy zgodzili się na Twoją politykę plików cookie.
-   **Typ ID produktu do dopasowywania katalogu:**

    *   **Co robi to ustawienie:** Określa, który identyfikator produktu (np. ID produktu, referencja produktu, EAN/UPC) moduł powinien wysyłać do Snapchata w celu dopasowania katalogu produktów. Jest to kluczowe dla dynamicznych reklam produktów.
    *   **Wpływ zmiany tego ustawienia:** Jeśli typ ID wysyłany przez moduł nie pasuje do ID w Twoim katalogu produktów Snapchata, Twoje dynamiczne reklamy nie będą wyświetlać prawidłowych produktów.
    *   **Zalecana wartość:** Wybierz typ ID, którego konsekwentnie używasz w swoim katalogu produktów Snapchata. Często `ID produktu` lub `Referencja produktu` są dobrymi wyborami.
    *   **Scenariusz/przykład dla sprzedawcy:** Prowadzisz dynamiczne reklamy retargetingowe na Snapchacie. Jeśli Twój katalog produktów używa „Referencji produktu” jako unikalnego identyfikatora, musisz wybrać „Referencję produktu” tutaj, aby reklamy wyświetlały klientom odpowiednie produkty.
-   **Włącz tryb debugowania:**

    *   **Co robi to ustawienie:** Aktywuje specjalny tryb, który wyświetla szczegółowe informacje o zdarzeniach wysyłanych do Snapchata bezpośrednio w konsoli programisty Twojej przeglądarki.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Włączone:* Będziesz widzieć informacje zwrotne w czasie rzeczywistym o tym, jakie dane są wysyłane, co pomoże Ci rozwiązywać problemy i weryfikować konfigurację. Jest to widoczne tylko dla Ciebie (lub każdego, kto ma otwarte narzędzia programistyczne).
        *   *Wyłączone:* Nie są wyświetlane żadne informacje debugowania.
    *   **Zalecana wartość:** `NIE` dla sklepów działających na żywo. `TAK` podczas początkowej konfiguracji i rozwiązywania problemów.
    *   **Scenariusz/przykład dla sprzedawcy:** Po zainstalowaniu modułu chcesz potwierdzić, że zdarzenia „Dodaj do koszyka” są prawidłowo wywoływane. Włączasz tryb debugowania, dodajesz produkt do koszyka i sprawdzasz konsolę pod kątem szczegółów zdarzenia.

#### **3. Zaawansowane funkcje**

-   **Ghost Collector (dopasowywanie ScCid):**

    *   **Co robi to ustawienie:** Poprawia dokładność dopasowywania użytkowników w różnych sesjach i urządzeniach, tworząc unikalny, anonimowy identyfikator (ScCid) i przechowując go w pliku cookie pierwszej strony.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Włączone:* Lepsza atrybucja i budowanie odbiorców, zwłaszcza w scenariuszach, w których pliki cookie stron trzecich są ograniczone.
        *   *Wyłączone:* Zdolność Snapchata do śledzenia użytkowników w różnych sesjach może być mniej dokładna.
    *   **Zalecana wartość:** `TAK`
    *   **Scenariusz/przykład dla sprzedawcy:** Klient odwiedza Twój sklep, opuszcza go i wraca później z innego urządzenia. Ghost Collector pomaga Snapchatowi rozpoznać go jako tego samego użytkownika, poprawiając Twoje działania retargetingowe.
-   **Domeny łączące (śledzenie między domenami):**

    *   **Co robi to ustawienie:** Umożliwia określenie dodatkowych domen (np. oddzielnego bloga, subdomeny dla konkretnych produktów), na których również chcesz śledzić zdarzenia Snapchata i łączyć sesje użytkowników.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Skonfigurowane:* Snapchat może płynnie śledzić podróż użytkownika w Twoim głównym sklepie i określonych połączonych domenach.
        *   *Puste:* Śledzenie jest ograniczone tylko do domeny Twojego głównego sklepu.
    *   **Zalecana wartość:** Pozostaw puste, chyba że masz wiele domen/subdomen, które wymagają śledzenia między domenami.
    *   **Scenariusz/przykład dla sprzedawcy:** Masz swój główny sklep pod adresem `moj-sklep.com` i oddzielny blog pod adresem `blog.moj-sklep.com`. Chcesz śledzić użytkowników, którzy odwiedzają oba. Dodałbyś `blog.moj-sklep.com` do tego ustawienia.
-   **URL zadania Cron dla synchronizacji CAPI:**

    *   **Co robi to ustawienie:** Udostępnia unikalny URL, który możesz skonfigurować jako zadanie cron na swoim serwerze. To zadanie cron okresowo wysyła wszelkie zakolejkowane zdarzenia po stronie serwera do Snapchata, zapewniając dostarczenie danych nawet w przypadku tymczasowych problemów z siecią.
    *   **Wpływ zmiany tego ustawienia:** Jest to pole tylko do odczytu. Skonfigurowanie zadania cron zapewnia niezawodne, asynchroniczne dostarczanie zdarzeń CAPI. Jeśli nie zostanie skonfigurowane, zdarzenia CAPI mogą być wysyłane tylko w czasie rzeczywistym lub po określonych działaniach użytkownika, potencjalnie pomijając niektóre dane, jeśli wysyłanie w czasie rzeczywistym się nie powiedzie.
    *   **Zalecana wartość:** Skonfiguruj zadanie cron na swoim serwerze, aby uruchamiać ten URL co 5-15 minut.
    *   **Scenariusz/przykład dla sprzedawcy:** Aby upewnić się, że wszystkie dane o zakupach są wysyłane do Snapchata, nawet jeśli klient zamknie przeglądarkę natychmiast po zakupie, konfigurujesz zadanie cron, aby regularnie przetwarzać wszelkie oczekujące zdarzenia CAPI.

#### **4. Jakość danych i ocena stanu**

Ta sekcja zazwyczaj zawiera tylko do odczytu informacje i rekomendacje oparte na Twojej bieżącej konfiguracji i śledzonych zdarzeniach.

-   **Ocena stanu:**

    *   **Co robi to ustawienie:** Wyświetla ogólną ocenę wskazującą jakość i kompletność konfiguracji śledzenia Snapchata. Wyższa ocena oznacza lepsze dane.
    *   **Wpływ zmiany tego ustawienia:** Jest to narzędzie diagnostyczne. Poprawa konfiguracji (np. włączenie CAPI, zaawansowane dopasowywanie) zwiększy tę ocenę.
    *   **Zalecana wartość:** Dąż do jak najwyższej oceny.
    *   **Scenariusz/przykład dla sprzedawcy:** Twoja ocena stanu wynosi 60%. Moduł może sugerować włączenie zaawansowanego dopasowywania, aby ją poprawić, wskazując potencjalny obszar dla lepszej jakości danych.
-   **Trener jakości danych:**

    *   **Co robi to ustawienie:** Oferuje konkretne rekomendacje i ostrzeżenia dotyczące konfiguracji śledzenia, takie jak brakujące tokeny CAPI, nieskonfigurowane typy ID produktów lub potencjalne problemy ze zgodą.
    *   **Wpływ zmiany tego ustawienia:** Jest to narzędzie diagnostyczne. Rozwiązanie rekomendacji poprawi dokładność śledzenia.
    *   **Zalecana wartość:** Przejrzyj i zastosuj wszystkie rekomendacje.
    *   **Scenariusz/przykład dla sprzedawcy:** Trener informuje Cię, że Twój „Typ ID produktu” nie pasuje do Twojego katalogu. Wracasz do ustawień i dostosowujesz go.
-   **Lekarz katalogu:**

    *   **Co robi to ustawienie:** Pomaga diagnozować problemy związane z katalogiem produktów i sposobem jego dopasowywania do zdarzeń Snapchata. Sprawdza spójność identyfikatorów produktów.
    *   **Wpływ zmiany tego ustawienia:** Jest to narzędzie diagnostyczne. Rozwiązanie problemów tutaj zapewnia prawidłowe działanie dynamicznych reklam produktów.
    *   **Zalecana wartość:** Użyj tego narzędzia, jeśli masz problemy z dynamicznymi reklamami produktów wyświetlającymi nieprawidłowe elementy.
    *   **Scenariusz/przykład dla sprzedawcy:** Twoje dynamiczne reklamy wyświetlają ogólne produkty zamiast tych, które klienci oglądali. Lekarz katalogu może ujawnić, że Twoje ID produktów są niespójne.

#### **5. Statystyki na żywo i ostatnie zdarzenia**

-   **Statystyki na żywo:**

    *   **Co robi to ustawienie:** Zapewnia przegląd w czasie rzeczywistym zdarzeń wysyłanych do Snapchata (np. Wyświetlenia strony, Dodania do koszyka, Zakupy).
    *   **Wpływ zmiany tego ustawienia:** Jest to narzędzie monitorujące. Pomaga szybko zweryfikować, czy zdarzenia są wywoływane zgodnie z oczekiwaniami.
    *   **Zalecana wartość:** Regularnie sprawdzaj tę sekcję, aby upewnić się, że Twoje śledzenie jest aktywne.
    *   **Scenariusz/przykład dla sprzedawcy:** Uruchamiasz nowy produkt i chcesz sprawdzić, czy zdarzenia „Wyświetlenie treści” są śledzone natychmiast. Sprawdzasz statystyki na żywo.
-   **Dziennik ostatnich zdarzeń:**

    *   **Co robi to ustawienie:** Pokazuje dziennik najnowszych zdarzeń wysłanych do Snapchata, w tym szczegóły, takie jak typ zdarzenia, sygnatura czasowa i informacja, czy zostało wysłane za pośrednictwem Pixela czy CAPI.
    *   **Wpływ zmiany tego ustawienia:** Jest to szczegółowe narzędzie do logowania w celu weryfikacji i rozwiązywania problemów.
    *   **Zalecana wartość:** Użyj tego, aby zagłębić się w konkretne zdarzenia, jeśli podejrzewasz problem.
    *   **Scenariusz/przykład dla sprzedawcy:** Klient zgłasza problem z zakupem, a Ty chcesz potwierdzić, czy zdarzenie „Zakup” zostało pomyślnie wysłane do Snapchata dla tego zamówienia.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### **AdminMysnapapiAjaxController (Panel administracyjny > Moduły > Snapchat Pixel & Conversions API > [Wewnętrzne wywołania AJAX])**

Ten kontroler nie jest bezpośrednio dostępny poprzez element menu, ale obsługuje żądania AJAX w tle ze strony konfiguracji modułu. Jest odpowiedzialny za:

-   **Nazwa ekranu i lokalizacja w menu:** Niewidoczne bezpośrednio w menu. Przetwarza żądania inicjowane z głównej strony konfiguracji modułu.
-   **Dostępne działania i ustawienia:** Zarządza dynamicznym ładowaniem danych dla sekcji „Statystyki na żywo”, „Ostatnie zdarzenia”, „Ocena stanu”, „Trener jakości danych” i „Lekarz katalogu”. Obsługuje również zapisywanie określonych ustawień konfiguracyjnych bez pełnego przeładowania strony.
-   **Wpływ zmian:** Kiedy wchodzisz w interakcję z dynamicznymi elementami na głównej stronie konfiguracji (np. odświeżanie statystyk na żywo, zapisywanie konkretnego podustawienia), ten kontroler przetwarza żądanie i aktualizuje wyświetlane informacje lub zapisuje dane.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Sprzedawcy nie wchodzą bezpośrednio w interakcję z tym kontrolerem. Jego funkcjonalność jest osadzona w głównej stronie konfiguracji modułu.

#### **index.php (mysnapapi/controllers/admin/index.php)**

Ten plik jest plikiem zastępczym i zazwyczaj nie zawiera bezpośredniej funkcjonalności ani interfejsu użytkownika. W PrestaShop pliki `index.php` w katalogach kontrolerów często służą do zapobiegania listowaniu katalogów, a nie do dostarczania konkretnej logiki kontrolera.

-   **Nazwa ekranu i lokalizacja w menu:** Nie jest to bezpośredni ekran.
-   **Dostępne działania i ustawienia:** Brak.
-   **Wpływ zmian:** Brak bezpośredniej interakcji sprzedawcy ani wpływu.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Nie jest wymagana interakcja.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Tryb śledzenia | Hybrydowy | Definiuje sposób wysyłania danych (Pixel, CAPI lub oba). Hybrydowy jest najbardziej niezawodny. |
| | ID Snap Pixela | Twój ID Pixela | Unikalny ID do śledzenia po stronie klienta. Niezbędny dla Pixela. |
| | Token Conversions API | Twój Token CAPI | Bezpieczny token do śledzenia po stronie serwera. Niezbędny dla CAPI. |
| | Włącz zaawansowane dopasowywanie | TAK | Poprawia dopasowywanie użytkowników dla lepszego targetowania reklam. |
| | Integracja zarządzania zgodą | TAK | Zapewnia zgodność z prywatnością poprzez poszanowanie zgody użytkownika. |
| | Typ ID produktu do dopasowywania katalogu | ID produktu / Referencja | Dopasowuje identyfikatory produktów dla dynamicznych reklam. |
| | Włącz tryb debugowania | NIE (TAK do konfiguracji) | Wyświetla informacje o śledzeniu w konsoli przeglądarki w celu rozwiązywania problemów. |
| | Ghost Collector (dopasowywanie ScCid) | TAK | Zwiększa dopasowywanie użytkowników w różnych sesjach/urządzeniach. |
| | Domeny łączące | Puste (lub Twoje domeny) | Umożliwia śledzenie między domenami dla wielu powiązanych witryn. |
| | URL zadania Cron dla synchronizacji CAPI | (Tylko do odczytu) | URL do dostarczania zdarzeń po stronie serwera, skonfigurowany jako zadanie cron. |
| | Ocena stanu | (Diagnostyczne) | Ogólna jakość konfiguracji śledzenia. Dąż do wysokiej oceny. |
| | Trener jakości danych | (Diagnostyczne) | Konkretne rekomendacje dotyczące poprawy jakości danych. |
| | Lekarz katalogu | (Diagnostyczne) | Diagnozuje problemy z dopasowywaniem katalogu produktów. |
| | Statystyki na żywo | (Monitorowanie) | Przegląd śledzonych zdarzeń w czasie rzeczywistym. |
| | Dziennik ostatnich zdarzeń | (Monitorowanie) | Szczegółowy dziennik ostatnich zdarzeń do weryfikacji. |

## 3. Rozwiązywanie problemów przez sprzedawcę i często zadawane pytania (FAQ)

**P1: Moje reklamy na Snapchacie nie pokazują żadnych konwersji, ale wiem, że mam sprzedaż. Co jest nie tak?**
O1:

-   **Sprawdź ID Pixela i Token CAPI:** Dokładnie sprawdź, czy Twój ID Snap Pixela i Token Conversions API są poprawnie wprowadzone w konfiguracji modułu. Nawet jedna literówka uniemożliwi śledzenie.
-   **Tryb śledzenia:** Upewnij się, że używasz „Hybrydowego” lub przynajmniej „Tylko Pixela”, jeśli oczekujesz śledzenia po stronie klienta.
-   **Tryb debugowania:** Włącz „Tryb debugowania” w ustawieniach modułu i otwórz konsolę programisty swojej przeglądarki (F12). Przejdź przez swój sklep i wykonaj działania (wyświetl produkt, dodaj do koszyka, dokonaj testowego zakupu). Szukaj zdarzeń Snapchata logowanych w konsoli. Jeśli ich nie widzisz, istnieje podstawowy problem z konfiguracją.
-   **Wyczyść pamięć podręczną:** Zawsze czyść pamięć podręczną PrestaShop (Parametry zaawansowane > Wydajność) po wprowadzeniu jakichkolwiek zmian w konfiguracji modułu.
-   **Blokery reklam:** Testuj w oknie incognito/prywatnym przeglądarki bez włączonych blokerów reklam, ponieważ mogą one zakłócać śledzenie pikselowe.

**P2: Włączyłem moduł, ale martwię się o zgodność z RODO/CCPA. Jak ten moduł pomaga?**
O2:

-   Moduł zawiera ustawienie **„Integracja zarządzania zgodą”**. Po włączeniu zintegruje się z Twoim istniejącym rozwiązaniem do zarządzania zgodą na pliki cookie (np. modułem RODO). Oznacza to, że śledzenie Snapchata zostanie aktywowane *dopiero po* wyraźnej zgodzie użytkownika za pośrednictwem banera zgody w Twoim sklepie.
-   **Działanie:** Upewnij się, że to ustawienie jest włączone i że masz funkcjonalny moduł zgody na pliki cookie w swoim sklepie PrestaShop.

**P3: Moje dynamiczne reklamy produktów na Snapchacie pokazują niewłaściwe produkty lub w ogóle nie działają.**
O3:

-   **Typ ID produktu:** Przejdź do konfiguracji modułu i zweryfikuj ustawienie **„Typ ID produktu do dopasowywania katalogu”**. Musi ono dokładnie odpowiadać unikalnemu identyfikatorowi, którego używasz w swoim katalogu produktów Snapchata (np. jeśli Twój katalog używa `reference`, wybierz `Referencja produktu` tutaj).
-   **Synchronizacja katalogu:** Upewnij się, że Twój katalog produktów jest poprawnie zsynchronizowany i aktualny w Menedżerze reklam Snapchata. Moduł wysyła prawidłowe ID, ale Snapchat musi mieć te ID w swoim katalogu.
-   **Lekarz katalogu:** Użyj narzędzia „Lekarz katalogu” w konfiguracji modułu, aby zdiagnozować potencjalne niespójności między danymi produktów w Twoim sklepie a tym, czego oczekuje Snapchat.

**P4: Widzę zduplikowane zdarzenia w moim Menedżerze reklam Snapchata (np. dwa zdarzenia „Zakup” dla jednego zamówienia).**
O4:

-   Zazwyczaj dzieje się tak, jeśli używasz zarówno Pixela, jak i CAPI bez odpowiedniej deduplikacji.
-   **Działanie:** Upewnij się, że Twój „Tryb śledzenia” jest ustawiony na **„Hybrydowy”**. Ten moduł jest zaprojektowany do automatycznego obsługi deduplikacji zdarzeń, gdy działa w trybie hybrydowym, generując wspólny `event_id` dla zdarzeń po stronie klienta i po stronie serwera. Jeśli widzisz duplikaty, sprawdź, czy moduł jest poprawnie skonfigurowany dla trybu hybrydowego i czy na Twojej stronie nie ma żadnego innego kodu śledzenia Snapchata.

**P5: Sekcje „Statystyki na żywo” lub „Ocena stanu” na stronie konfiguracji modułu nie aktualizują się ani nie pokazują danych.**
O5:

-   **Problemy z AJAX:** Zazwyczaj wskazuje to na problem ze zdolnością Twojego serwera do przetwarzania żądań AJAX lub błąd JavaScript w Twoim panelu administracyjnym.
-   **Konsola przeglądarki:** Otwórz konsolę programisty swojej przeglądarki (F12) na stronie konfiguracji modułu i sprawdź, czy w zakładce „Konsola” nie ma żadnych czerwonych komunikatów o błędach.
-   **Logi serwera:** Sprawdź logi błędów PHP swojego serwera pod kątem wszelkich powiązanych błędów.
-   **Tryb debugowania PrestaShop:** Tymczasowo włącz tryb debugowania PrestaShop (Parametry zaawansowane > Wydajność > Tryb debugowania: TAK), aby zobaczyć, czy pojawią się bardziej szczegółowe błędy.
-   **Skontaktuj się z pomocą techniczną:** Jeśli nie możesz tego rozwiązać, zbierz wszelkie komunikaty o błędach i skontaktuj się z pomocą techniczną MyPresta.eu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Snapchat Pixel & Conversions API` (`mysnapapi`) implementuje solidne rozwiązanie do śledzenia, wykorzystujące zarówno śledzenie zdarzeń po stronie klienta (Snap Pixel), jak i po stronie serwera (Conversions API - CAPI). Przyjmuje modułowe, obiektowe podejście, przestrzegając wzorca MVC PrestaShop, tam gdzie ma to zastosowanie.

Kluczowe komponenty architektoniczne:

-   **Śledzenie hybrydowe:** Moduł obsługuje tryb tylko Pixel, tylko CAPI oraz zalecany tryb hybrydowy. W trybie hybrydowym generuje unikalny `event_id` dla każdego zdarzenia, współdzielony między ładunkami Pixela i CAPI, aby zapewnić deduplikację po stronie Snapchata.
-   **Mapowanie zdarzeń:** Kompleksowe mapowanie działań PrestaShop (np. `actionCartSave`, `actionValidateOrder`) na standardowe zdarzenia Snapchata (`ADD_CART`, `PURCHASE`, `VIEW_CONTENT`, `PAGE_VIEW`).
-   **Zarządzanie zgodą:** Punkty integracji dla popularnych modułów zgody w celu zapewnienia zgodności z RODO/CCPA.
-   **Narzędzia do jakości danych:** Wbudowane narzędzia diagnostyczne, takie jak Ocena stanu, Trener jakości danych i Lekarz katalogu, pomagające w konfiguracji i rozwiązywaniu problemów.
-   **Asynchroniczne CAPI:** Zdarzenia CAPI są często kolejkowane i wysyłane asynchronicznie, w czasie rzeczywistym lub za pośrednictwem zadania cron, w celu poprawy wydajności i niezawodności.
-   **Dane pierwszej strony:** Wykorzystuje „Ghost Collector” do tworzenia plików cookie pierwszej strony do dopasowywania `ScCid`, zwiększając identyfikację użytkowników w środowisku skoncentrowanym na prywatności.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `mysnapapi/controllers/front/ajax.php`
    *   **Nazwa klasy i klasa nadrzędna:** `MysnapapiAjaxModuleFrontController` rozszerza `ModuleFrontController`.
    *   **Odpowiedzialność:** Obsługuje różne żądania AJAX z front-office, głównie dla funkcjonalności „Ghost Collector” (ScCid). Może zbierać anonimowe dane użytkownika lub aktualizować pliki cookie pierwszej strony bez pełnego przeładowania strony.
-   `mysnapapi/controllers/front/cron.php`
    *   **Nazwa klasy i klasa nadrzędna:** `MysnapapiCronModuleFrontController` rozszerza `ModuleFrontController`.
    *   **Odpowiedzialność:** Ten kontroler jest przeznaczony do wywoływania przez zewnętrzne zadanie cron. Jego główną rolą jest przetwarzanie wszelkich zakolejkowanych zdarzeń po stronie serwera (CAPI), które nie zostały wysłane w czasie rzeczywistym. Zapewnia, że wszystkie dane CAPI są ostatecznie dostarczane do Snapchata, poprawiając niezawodność.
-   `mysnapapi/controllers/front/index.php`
    *   **Nazwa klasy i klasa nadrzędna:** `MysnapapiIndexModuleFrontController` rozszerza `ModuleFrontController`.
    *   **Odpowiedzialność:** Zazwyczaj jest to plik zastępczy lub domyślny punkt wejścia. Może obsługiwać podstawową inicjalizację modułu lub przekierowywać, jeśli jest dostępny bezpośrednio. Często `index.php` w katalogu kontrolera zapobiega listowaniu katalogów.
-   `mysnapapi/controllers/front/sync.php`
    *   **Nazwa klasy i klasa nadrzędna:** `MysnapapiSyncModuleFrontController` rozszerza `ModuleFrontController`.
    *   **Odpowiedzialność:** Prawdopodobnie obsługuje specyficzne zadania synchronizacji danych, potencjalnie związane z aktualizacjami katalogu produktów lub inną wymianą danych z API Snapchata, oddzielnie od głównego śledzenia zdarzeń.

#### Kontrolery administracyjne Back-Office

-   `mysnapapi/controllers/admin/AdminMysnapapiAjaxController.php`
    *   **Nazwa klasy i klasa nadrzędna:** `AdminMysnapapiAjaxController` rozszerza `AdminController`.
    *   **Nazwa zakładki i zarządzana encja:** Nie jest to bezpośrednia zakładka menu. Ten kontroler obsługuje żądania AJAX pochodzące z głównej strony konfiguracji modułu (metoda `getContent()` z `mysnapapi.php`). Jest odpowiedzialny za dynamiczne ładowanie danych dla różnych narzędzi diagnostycznych (Statystyki na żywo, Ocena stanu itp.) oraz zapisywanie konkretnych ustawień konfiguracyjnych bez pełnego przeładowania strony.
-   `mysnapapi/controllers/admin/index.php`
    *   **Nazwa klasy i klasa nadrzędna:** Nie jest to funkcjonalny kontroler.
    *   **Nazwa zakładki i zarządzana encja:** Plik zastępczy. Zapobiega listowaniu katalogów.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `mysnapapi/classes/autoload.php`: Standardowy plik autoload PrestaShop.
-   `mysnapapi/classes/index.php`: Plik zastępczy zapobiegający listowaniu katalogów.
-   `mysnapapi/classes/MysnapapiCapiClient.php`:
    *   **Interakcje z:** Punkt końcowy Snapchat Conversions API.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Obsługuje wysyłanie zdarzeń po stronie serwera do Snapchata. Hermetyzuje logikę żądań API, uwierzytelnianie (za pomocą tokena CAPI) i obsługę błędów.
-   `mysnapapi/classes/MysnapapiCapiTracker.php`:
    *   **Interakcje z:** `ps_configuration` (dla tokena CAPI), `MysnapapiCapiClient`.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Odpowiedzialny za przygotowywanie i wysyłanie danych zdarzeń specjalnie dla Conversions API. Formatuje ładunki zdarzeń zgodnie ze specyfikacjami CAPI Snapchata.
-   `mysnapapi/classes/MysnapapiCatalogDoctor.php`:
    *   **Interakcje z:** Danymi produktów (z ObjectModels `Product` i `ProductSupplier`).
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Zapewnia logikę diagnostyczną do sprawdzania spójności i problemów związanych z identyfikatorami produktów używanymi do dopasowywania katalogu (np. `id_product`, `reference`, `ean13`).
-   `mysnapapi/classes/MysnapapiConsent.php`:
    *   **Interakcje z:** `ps_configuration` (dla ustawień zgody), potencjalnie innymi modułami zgody.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Zarządza stanem zgody. Sprawdza, czy zgoda użytkownika jest wymagana i czy została udzielona przed zezwoleniem na uruchomienie skryptów śledzących lub zdarzeń CAPI.
-   `mysnapapi/classes/MysnapapiCurrencyHelper.php`:
    *   **Interakcje z:** Klasą `Currency` PrestaShop.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Zapewnia funkcje pomocnicze do obsługi formatowania i konwersji walut, zapewniając, że wartości zdarzeń są wysyłane w prawidłowym formacie i kodzie waluty do Snapchata.
-   `mysnapapi/classes/MysnapapiDataQualityCoach.php`:
    *   **Interakcje z:** Ustawieniami konfiguracji modułu.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Analizuje konfigurację modułu i dostarcza rekomendacje lub ostrzeżenia w celu poprawy jakości danych i skuteczności śledzenia.
-   `mysnapapi/classes/MysnapapiEventId.php`:
    *   **Interakcje z:** Sesją, plikami cookie.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Generuje i zarządza unikalnymi wartościami `event_id` dla każdego śledzonego zdarzenia. Kluczowe dla deduplikacji podczas korzystania z trybu śledzenia hybrydowego.
-   `mysnapapi/classes/MysnapapiEventMap.php`:
    *   **Interakcje z:** N/A.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Definiuje mapowanie między wewnętrznymi zdarzeniami/danymi PrestaShop a standardowymi nazwami zdarzeń i parametrami Snapchata.
-   `mysnapapi/classes/MysnapapiEvents.php`:
    *   **Interakcje z:** Różnymi klasami podstawowymi PrestaShop (np. `Cart`, `Product`, `Order`).
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Scentralizowana klasa do zbierania i formatowania danych zdarzeń (np. `PageView`, `ViewContent`, `AddToCart`, `Purchase`) z kontekstu PrestaShop do struktury zgodnej ze Snapchatem.
-   `mysnapapi/classes/MysnapapiHealthScore.php`:
    *   **Interakcje z:** Konfiguracją modułu, potencjalnie danymi zdarzeń na żywo.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Oblicza ogólną „ocenę stanu” konfiguracji śledzenia na podstawie skonfigurowanych opcji i wykrytych problemów.
-   `mysnapapi/classes/MysnapapiHybridTracker.php`:
    *   **Interakcje z:** `MysnapapiPixelTracker`, `MysnapapiCapiTracker`, `MysnapapiEventId`.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Koordynuje śledzenie w trybie „Hybrydowym”, zapewniając, że zdarzenia Pixel i CAPI są wysyłane z tym samym `event_id` w celu deduplikacji.
-   `mysnapapi/classes/MysnapapiLiveStats.php`:
    *   **Interakcje z:** Potencjalnie tymczasowym dziennikiem ostatnich zdarzeń lub danymi w czasie rzeczywistym.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Zbieranie i prezentowanie statystyk w czasie rzeczywistym dotyczących śledzonych zdarzeń dla panelu administracyjnego.
-   `mysnapapi/classes/MysnapapiPixelTracker.php`:
    *   **Interakcje z:** `ps_configuration` (dla ID Pixela).
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Odpowiedzialny za generowanie kodu JavaScript dla Snap Pixela i osadzanie go w front-office, w tym danych zdarzeń.
-   `mysnapapi/classes/MysnapapiProductIdResolver.php`:
    *   **Interakcje z:** Danymi produktów.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Określa prawidłowy identyfikator produktu (np. `id_product`, `reference`, `ean13`) do użycia na podstawie konfiguracji modułu do dopasowywania katalogu.
-   `mysnapapi/classes/MysnapapiPropertyRules.php`:
    *   **Interakcje z:** N/A.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Definiuje reguły i walidacje dla właściwości zdarzeń, zapewniając, że dane wysyłane do Snapchata są zgodne z ich specyfikacjami API.
-   `mysnapapi/classes/MysnapapiTrackerFactory.php`:
    *   **Interakcje z:** Konfiguracją modułu (tryb śledzenia).
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Wzorzec fabryki do tworzenia instancji prawidłowej klasy trackera (`MysnapapiPixelTracker`, `MysnapapiCapiTracker` lub `MysnapapiHybridTracker`) na podstawie skonfigurowanego trybu śledzenia modułu.
-   `mysnapapi/classes/MysnapapiTrackerInterface.php`:
    *   **Interakcje z:** N/A.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Definiuje wspólny interfejs dla wszystkich klas trackerów, zapewniając spójne sygnatury metod dla śledzenia zdarzeń.
-   `mysnapapi/classes/MysnapapiUserData.php`:
    *   **Interakcje z:** Danymi klienta (z ObjectModel `Customer`), sesją, plikami cookie.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody:** Zbieranie i formatowanie danych specyficznych dla użytkownika (np. e-mail, telefon, adres IP, user agent) do zaawansowanego dopasowywania, zapewniając, że dane są zaszyfrowane i zgodne z przepisami.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `mysnapapi/tools/console-simulate-bo-ui.js`:
    *   **Zakres:** Back-office (narzędzie dla programistów).
    *   **Opis:** Skrypt narzędziowy, prawdopodobnie do rozwoju/debugowania, do symulowania lub interakcji z interfejsem użytkownika Back Office z konsoli przeglądarki.
-   `mysnapapi/views/js/mp-collect.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Podstawowy skrypt do zbierania danych po stronie klienta. Może nasłuchiwać określonych zdarzeń DOM lub interakcji użytkownika w celu wywołania zdarzeń Snap Pixela.
-   `mysnapapi/views/js/mp-consent.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Obsługuje integrację z mechanizmami zgody na pliki cookie. Sprawdza status zgody i warunkowo ładuje/inicjalizuje Snap Pixel lub powiązane śledzenie. Może wchodzić w interakcje z `prestashop.on('updateConsent')`.
-   `mysnapapi/views/js/mp-front.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Ogólny JavaScript front-office dla modułu. Prawdopodobnie zawiera główną logikę inicjalizacji podstawowego kodu Snap Pixela, przesyłania zdarzeń do obiektu `snap` i obsługi wyzwalaczy zdarzeń po stronie klienta.
-   `mysnapapi/views/js/mp-inspect.js`:
    *   **Zakres:** Front-office (tryb debugowania).
    *   **Opis:** Używany, gdy tryb debugowania jest włączony. Przechwytuje i wyświetla zdarzenia Snapchata w konsoli przeglądarki, dostarczając szczegółowych informacji o wysyłanych danych.
-   `mysnapapi/views/js/mysnapapi-admin.js`:
    *   **Zakres:** Back-office.
    *   **Opis:** JavaScript dla interfejsu administracyjnego modułu. Obsługuje interakcje z formularzami, wywołania AJAX do `AdminMysnapapiAjaxController`, dynamiczne aktualizacje sekcji diagnostycznych (Statystyki na żywo, Ocena stanu) i kroki kreatora.
-   `mysnapapi/views/js/mysnapapi-debug.js`:
    *   **Zakres:** Front-office (tryb debugowania).
    *   **Opis:** Podobnie jak `mp-inspect.js`, dostarcza dodatkowe narzędzia debugowania lub wizualne nakładki dla programistów do weryfikacji śledzenia.
-   `mysnapapi/views/js/mysnapapi-ghost.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Implementuje funkcjonalność „Ghost Collector”. Zarządza tworzeniem i odczytywaniem plików cookie pierwszej strony dla dopasowywania `ScCid` (Snapchat Click ID), zwiększając identyfikację użytkowników.
-   `mysnapapi/views/js/mysnapapi-live.js`:
    *   **Zakres:** Back-office.
    *   **Opis:** Zasila sekcję „Statystyki na żywo” w panelu administracyjnym, wykonując wywołania AJAX w celu pobierania i wyświetlania danych zdarzeń w czasie rzeczywistym.
-   `mysnapapi/views/js/mysnapapi-tcf.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Specjalnie do integracji z rozwiązaniami zgody zgodnymi z Transparency and Consent Framework (TCF), zapewniając, że śledzenie Snapchata jest zgodne z sygnałami TCF.
-   `mysnapapi/views/js/mysnapapi-wizard.js`:
    *   **Zakres:** Back-office.
    *   **Opis:** Zapewnia interaktywną logikę dla kreatora konfiguracji modułu, prowadząc sprzedawcę przez początkowe kroki konfiguracji.
-   `mysnapapi/views/js/mysnapapi.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Główny punkt wejścia lub ogólny JavaScript narzędziowy dla front-office, potencjalnie ładujący inne skrypty lub zawierający globalne funkcje specyficzne dla modułu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `mysnapapi/views/css/mp-inspect.css`:
    *   **Zakres:** Front-office (tryb debugowania).
    *   **Opis:** Style dla nakładki debugowania lub wyjścia konsoli, gdy `mp-inspect.js` jest aktywny.
-   `mysnapapi/views/css/mysnapapi-admin.css`:
    *   **Zakres:** Stylizacja formularza administracyjnego Back-office.
    *   **Opis:** Style dla strony konfiguracji modułu, w tym układ, przyciski, sekcje diagnostyczne (Ocena stanu, Trener jakości danych) i kroki kreatora.
-   `mysnapapi/views/css/mysnapapi-debug.css`:
    *   **Zakres:** Front-office (tryb debugowania).
    *   **Opis:** Dodatkowa stylizacja dla elementów debugowania, potencjalnie wizualne wskaźniki lub obramowania dla śledzonych elementów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `mysnapapi/views/templates/hook/capi-pageview.tpl`:
    *   **Hook:** Potencjalnie `displayHeader` lub `displayFooter` (kontekst po stronie serwera).
    *   **Wyjście:** Renderuje ukryty element lub wywołanie po stronie serwera w celu wywołania zdarzenia CAPI `PAGE_VIEW`, często używane jako rozwiązanie awaryjne lub do początkowego ładowania strony.
-   `mysnapapi/views/templates/hook/debug.tpl`:
    *   **Hook:** `displayHeader` lub `displayFooter` (warunkowo w trybie debugowania).
    *   **Wyjście:** Renderuje informacje debugowania lub inicjalizuje skrypty debugowania w front-office.
-   `mysnapapi/views/templates/hook/displayOrderConfirmation.tpl`:
    *   **Hook:** `displayOrderConfirmation`.
    *   **Wyjście:** Renderuje zdarzenie Snap Pixela `PURCHASE` i/lub wywołuje zdarzenie CAPI `PURCHASE` na stronie potwierdzenia zamówienia, przekazując szczegóły zamówienia.
-   `mysnapapi/views/templates/hook/ghost.tpl`:
    *   **Hook:** `displayHeader` lub `displayFooter`.
    *   **Wyjście:** Renderuje JavaScript dla „Ghost Collector” do zarządzania plikami cookie `ScCid`.
-   `mysnapapi/views/templates/hook/header.tpl`:
    *   **Hook:** `displayHeader`.
    *   **Wyjście:** Główny szablon do inicjalizacji podstawowego kodu Snap Pixela, obiektu `snap` i potencjalnie zdarzeń `PAGE_VIEW`. Ładuje niezbędne pliki JavaScript.
-   `mysnapapi/views/templates/hook/payment.tpl`:
    *   **Hook:** `displayPayment` lub `displayPaymentTop`.
    *   **Wyjście:** Renderuje `INITIATE_CHECKOUT` lub inne istotne zdarzenia podczas fazy wyboru płatności w procesie płatności.
-   `mysnapapi/views/templates/hook/product-details.tpl`:
    *   **Hook:** `displayProductButtons` lub `displayFooterProduct`.
    *   **Wyjście:** Renderuje zdarzenie Snap Pixela `VIEW_CONTENT` i zdarzenie `ADD_CART` (lub powiązany JS) na stronie produktu, przekazując dane specyficzne dla produktu.

#### Szablony administracyjne (`views/templates/admin/`)

-   `mysnapapi/views/templates/admin/consent-guide.tpl`: Wyświetla wskazówki dotyczące integracji z zarządzaniem zgodą.
-   `mysnapapi/views/templates/admin/doctor.tpl`: Renderuje interfejs dla narzędzia diagnostycznego „Lekarz katalogu”.
-   `mysnapapi/views/templates/admin/dq.tpl`: Renderuje rekomendacje „Trenera jakości danych”.
-   `mysnapapi/views/templates/admin/health.tpl`: Wyświetla „Ocenę stanu” i powiązane informacje.
-   `mysnapapi/views/templates/admin/linker-domains.tpl`: Pole wprowadzania i wyjaśnienie dotyczące śledzenia między domenami.
-   `mysnapapi/views/templates/admin/live-maintain.tpl`: Interfejs do utrzymywania lub czyszczenia statystyk na żywo.
-   `mysnapapi/views/templates/admin/live.tpl`: Wyświetla pulpit nawigacyjny „Statystyki na żywo”.
-   `mysnapapi/views/templates/admin/mode-context.tpl`: Zapewnia kontekst lub wyjaśnienie dla wybranego trybu śledzenia.
-   `mysnapapi/views/templates/admin/mode-note-both.tpl`: Specyficzna uwaga dla trybu śledzenia „Hybrydowego”.
-   `mysnapapi/views/templates/admin/mode-note-capi.tpl`: Specyficzna uwaga dla trybu śledzenia „Tylko Conversions API”.
-   `mysnapapi/views/templates/admin/mode-note-pixel.tpl`: Specyficzna uwaga dla trybu śledzenia „Tylko Pixel”.
-   `mysnapapi/views/templates/admin/mode-picker.tpl`: Interfejs wyboru trybu śledzenia.
-   `mysnapapi/views/templates/admin/properties-list.tpl`: Wyświetla listę właściwości zdarzeń i ich reguł.
-   `mysnapapi/views/templates/admin/recent-events.tpl`: Tabela lub lista wyświetlająca najnowsze śledzone zdarzenia.
-   `mysnapapi/views/templates/admin/tabs.tpl`: Renderuje strukturę nawigacji po zakładkach dla strony konfiguracji modułu.
-   `mysnapapi/views/templates/admin/tag-chips.tpl`: Komponenty wizualne do wyświetlania tagów lub identyfikatorów.
-   `mysnapapi/views/templates/admin/tag-ids.tpl`: Pola wprowadzania dla ID Pixela i Tokena CAPI.
-   `mysnapapi/views/templates/admin/wizard.tpl`: Szablon dla kreatora konfiguracji krok po kroku modułu.

#### Szablony Front-office (`views/templates/front/`)

(Brak dedykowanych samodzielnych szablonów stron, wszystkie szablony front-office są oparte na hookach.)

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł wykorzystuje głównie tabelę `ps_configuration` PrestaShop do przechowywania swoich ustawień.

-   `ps_configuration`: Przechowuje pary klucz-wartość dla ustawień modułu (np. `MYSNAPAPI_PIXEL_ID`, `MYSNAPAPI_CAPI_TOKEN`, `MYSNAPAPI_TRACKING_MODE`).
-   Na podstawie dostarczonego spisu moduł nie tworzy jawnie żadnych niestandardowych tabel SQL. Zdarzenia CAPI mogą być tymczasowo kolejkowane w pamięci lub systemie plików przed wysłaniem, zamiast w dedykowanej tabeli bazy danych.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` każdej strony front-office. | Inicjalizuje podstawowy kod Snap Pixela, ładuje zasoby JS, wywołuje zdarzenia `PAGE_VIEW` i konfiguruje `ScCid` (Ghost Collector). |
| `displayFooter` | Renderuje się na końcu sekcji `<body>` każdej strony front-office. | Może zawierać odroczone ładowanie skryptów, dodatkowe wyzwalacze zdarzeń lub zarządzanie `ScCid`. |
| `displayProductButtons` | Na stronie produktu, w pobliżu przycisku „Dodaj do koszyka”. | Wywołuje zdarzenia `VIEW_CONTENT` i potencjalnie `ADD_CART` ze szczegółami produktu. |
| `displayFooterProduct` | Na stronie produktu, w obszarze stopki. | Alternatywna lub dodatkowa lokalizacja dla zdarzeń `VIEW_CONTENT` i `ADD_CART`. |
| `actionCartSave` | Wykonywane za każdym razem, gdy koszyk jest modyfikowany (dodanie, aktualizacja, usunięcie produktu). | Wywołuje zdarzenia `ADD_CART` lub `REMOVE_FROM_CART`. |
| `actionValidateOrder` | Wykonywane po pomyślnym złożeniu zamówienia. | Wywołuje kluczowe zdarzenie `PURCHASE`, wysyłając pełne szczegóły zamówienia (wartość, waluta, produkty). |
| `displayOrderConfirmation` | Na stronie potwierdzenia zamówienia po pomyślnym zakupie. | Renderuje zdarzenie `PURCHASE` po stronie klienta dla Snap Pixela. |
| `displayPayment` | Przed wyborem metody płatności. | Wywołuje zdarzenie `INITIATE_CHECKOUT`. |
| `displayPaymentTop` | Na górze strony wyboru płatności. | Alternatywna lub dodatkowa lokalizacja dla zdarzenia `INITIATE_CHECKOUT`. |
| `actionFrontControllerSetMedia` | Wykonywane, gdy kontroler front-office ustawia swoje zasoby multimedialne. | Wstrzykuje pliki CSS i JavaScript specyficzne dla modułu do front-office. |
| `actionAdminControllerSetMedia` | Wykonywane, gdy kontroler administracyjny ustawia swoje zasoby multimedialne. | Wstrzykuje pliki CSS i JavaScript specyficzne dla modułu do strony konfiguracji back-office. |
| `actionModuleInstall` | Wykonywane podczas instalacji modułu. | Ustawia domyślne wartości konfiguracyjne w `ps_configuration`. |
| `actionModuleUninstall` | Wykonywane podczas deinstalacji modułu. | Czyści wartości konfiguracyjne z `ps_configuration`. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i najnowszych wersji modułu Snapchat Pixel & Conversions API, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
