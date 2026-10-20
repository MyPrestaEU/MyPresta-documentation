---
title: "Abandoned Cart Reminder Pro – drip emails, discount codes & ROI - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów modułu PrestaShop Abandoned Cart Reminder Pro – drip emails, discount codes & ROI od MyPresta.eu."
sidebar:
  label: "Abandoned Cart Reminder Pro – drip emails, discount codes & ROI - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Abandoned Cart Reminder Pro – drip emails, discount codes & ROI na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/abandoned-cart-reminder-pro-drip-emails-discount-codes-roi.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/abandoned-cart-reminder-pro-drip-emails-discount-codes-roi/)
>
> ---


# Abandoned Cart Reminder Pro – drip emails, discount codes & ROI

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5 (Moduł jest napisany z myślą o PHP 5.6+, ale PrestaShop 9.x wymaga PHP 8.1+ dla samego sklepu. Zalecamy używanie najwyższej stabilnej wersji PHP kompatybilnej z Twoją instalacją PrestaShop, do 8.5.)
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP, takie jak cURL, JSON i OpenSSL. Twoje środowisko hostingowe musi również obsługiwać zadania cron (zaplanowane zadania), aby moduł działał poprawnie, ponieważ przetwarza przypomnienia w tle.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Abandoned Cart Reminder Pro” oferuje kompleksowy zestaw narzędzi do zarządzania kampaniami. Będziesz głównie korzystać z jego dedykowanych pozycji menu w Panelu administracyjnym PrestaShop.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Chociaż moduł ma dedykowane ekrany administracyjne, początkowy przycisk „Konfiguruj” z Menedżera modułów może prowadzić do podstawowej konfiguracji lub przekierowania. Moduł wykorzystuje klucz konfiguracyjny PrestaShop `PS_SSL_ENABLED`.

-   **Co robi to ustawienie:** To ustawienie nie jest bezpośrednio kontrolowane przez moduł, ale jest podstawowym ustawieniem PrestaShop, które wskazuje, czy Twój sklep używa HTTPS (bezpiecznego połączenia). Moduł polega na tym, aby generować poprawne, bezpieczne linki w e-mailach przypominających.
-   **Wpływ zmiany tego ustawienia:**
    *   *Gdy `PS_SSL_ENABLED` jest TAK:* Wszystkie linki generowane przez moduł (np. do porzuconych koszyków, stron rezygnacji) będą używać `https://`, zapewniając bezpieczne i zaufane doświadczenie dla Twoich klientów.
    *   *Gdy `PS_SSL_ENABLED` jest NIE:* Linki mogą być generowane przy użyciu `http://`, co jest mniej bezpieczne i może wywoływać ostrzeżenia przeglądarki, potencjalnie zmniejszając zaufanie klientów i współczynniki konwersji.
-   **Zalecana wartość:** **TAK**. Twój sklep powinien zawsze używać SSL ze względów bezpieczeństwa i SEO. Upewnij się, że cały Twój sklep działa na HTTPS.
-   **Scenariusz/przykład sprzedawcy:** Jeśli Twoi klienci otrzymają e-mail z linkiem `http://` do swojego koszyka, ich przeglądarka może wyświetlić ostrzeżenie „Niezabezpieczone”. Może to sprawić, że będą się wahać przed kliknięciem linku lub dokończeniem zakupu, nawet jeśli Twoja płatność jest bezpieczna. Zawsze używaj HTTPS.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Po zainstalowaniu modułu znajdziesz nową pozycję menu w Panelu administracyjnym PrestaShop, zazwyczaj w sekcji **Marketing** lub w dedykowanej sekcji dla „Abandoned Cart Reminder Pro”. To menu będzie prowadzić do kilku podsekcji:

#### 2.2.1 Kampanie (Panel administracyjny > Abandoned Cart Reminder Pro > Kampanie)

Tutaj tworzysz, zarządzasz i optymalizujesz swoje kampanie przypomnień o porzuconych koszykach.

-   **Nazwa ekranu i lokalizacja w menu:** **Abandoned Cart Reminder Pro > Kampanie**
-   **Dostępne działania i ustawienia:**
    *   **Lista kampanii:** Tabela pokazująca wszystkie Twoje aktywne i nieaktywne kampanie, w tym ich nazwę, status i kluczowe statystyki.
    *   **Dodaj nową kampanię:** Kliknij, aby utworzyć nową wieloetapową sekwencję e-maili.
        *   **Nazwa kampanii:** Opisowa nazwa do Twojego wewnętrznego użytku (np. „Standardowe przypomnienie 2-etapowe”, „Rabat na koszyk o wysokiej wartości”).
        *   **Zasady targetowania:**
            *   **Minimalna wartość koszyka:** Ustaw minimalną całkowitą wartość koszyka, aby kwalifikował się do tej kampanii.
                *   *Efekt:* Koszyki poniżej tej wartości nie otrzymają e-maili z tej kampanii.
                *   *Scenariusz sprzedawcy:* Utwórz kampanię specjalnie dla koszyków o wysokiej wartości, oferując być może większy rabat.
            *   **Grupy klientów:** Targetuj określone grupy klientów (np. „Odwiedzający”, „Klienci”, „Hurtownicy”).
                *   *Efekt:* Tylko klienci należący do wybranych grup otrzymają e-maile.
                *   *Scenariusz sprzedawcy:* Wysyłaj różne przypomnienia do nowych odwiedzających w porównaniu do lojalnych klientów lub wyklucz klientów B2B, jeśli mają inny proces zakupowy.
            *   **Produkty w koszyku:** Targetuj koszyki zawierające określone produkty lub produkty z określonych kategorii.
                *   *Efekt:* Tylko koszyki z określonymi produktami uruchomią kampanię.
                *   *Scenariusz sprzedawcy:* Utwórz kampanię dla klientów, którzy porzucili koszyk z konkretnym produktem o wysokiej marży.
        *   **Kroki kampanii (E-maile kroplowe):** Zdefiniuj sekwencję e-maili do wysłania.
            *   **Opóźnienie:** Jak długo po porzuceniu koszyka powinien zostać wysłany ten e-mail (np. 1 godzina, 24 godziny, 3 dni).
                *   *Efekt:* Kontroluje czas Twojej korespondencji.
                *   *Scenariusz sprzedawcy:* Wyślij szybkie przypomnienie po 1 godzinie, silniejsze z rabatem po 24 godzinach i ostatnie po 3 dniach.
            *   **Temat e-maila:** Temat e-maila (obsługuje wiele języków).
            *   **Treść e-maila (Kreator e-maili):** Zaprojektuj treść e-maila za pomocą edytora tekstu sformatowanego. Możesz dołączyć dynamiczne symbole zastępcze, takie jak imię klienta, link do koszyka, lista produktów i kody rabatowe.
            *   **Kod rabatowy:** Opcja generowania unikalnego, jednorazowego kodu rabatowego dla tego konkretnego e-maila.
                *   *Efekt:* Unikalny kod kuponu jest tworzony i dołączany do e-maila, zachęcając do konwersji.
                *   *Scenariusz sprzedawcy:* Zaoferuj 10% rabatu w drugim e-mailu przypominającym, aby zachęcić do dokończenia.
            *   **Testy A/B:** Twórz warianty tematu lub treści e-maila, aby sprawdzić, który działa lepiej.
                *   *Efekt:* Moduł podzieli wysyłki między warianty i będzie śledzić współczynniki konwersji, umożliwiając optymalizację kampanii.
                *   *Scenariusz sprzedawcy:* Przetestuj dwa różne tematy, aby zobaczyć, który uzyska wyższy współczynnik otwarć.
    *   **Edytuj/Duplikuj/Usuń kampanie:** Zarządzaj istniejącymi kampaniami. Duplikowanie jest przydatne do szybkiego tworzenia podobnych kampanii.
-   **Wpływ zmian:** Zmiany tutaj bezpośrednio wpływają na to, którzy klienci otrzymują e-maile przypominające, kiedy je otrzymują, jaką treść widzą i czy otrzymują kody rabatowe. Dobrze skonfigurowane kampanie mogą znacznie zwiększyć wskaźnik odzyskiwania koszyków w Twoim sklepie.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Zacznij od prostej kampanii 2-etapowej: przypomnienie po 1-2 godzinach (bez rabatu) i kolejne po 24 godzinach (z małym rabatem).
    2.  Monitoruj swój Panel (patrz 4.2.2), aby zobaczyć, które kampanie działają najlepiej.
    3.  Eksperymentuj z testami A/B na tematach lub kwotach rabatów, aby zoptymalizować współczynniki konwersji.
    4.  Rozważ tworzenie ukierunkowanych kampanii dla określonych segmentów klientów lub produktów o wysokiej wartości.

#### 2.2.2 Panel (Panel administracyjny > Abandoned Cart Reminder Pro > Panel)

Ten ekran zapewnia przejrzysty przegląd wydajności modułu i kluczowych statystyk.

-   **Nazwa ekranu i lokalizacja w menu:** **Abandoned Cart Reminder Pro > Panel**
-   **Dostępne działania i ustawienia:**
    *   **Kluczowe wskaźniki wydajności (KPI):** Wyświetla metryki takie jak:
        *   **Porzucone koszyki:** Całkowita liczba porzuconych koszyków.
        *   **Wysłane e-maile:** Liczba wysłanych e-maili przypominających.
        *   **Odzyskane koszyki:** Liczba porzuconych koszyków, które zakończyły się zrealizowanym zamówieniem po otrzymaniu przypomnienia.
        *   **Współczynnik odzyskiwania:** Procent odzyskanych porzuconych koszyków.
        *   **Przypisany przychód:** Całkowity przychód wygenerowany z odzyskanych koszyków.
        *   **ROI:** Zwrot z inwestycji dla Twoich kampanii.
    *   **Szczegółowa analiza wydajności kampanii:** Wizualna reprezentacja (np. wykresy, grafiki) pokazująca, jak działają poszczególne kampanie.
    *   **Ostatnia aktywność:** Szybki przegląd ostatnio porzuconych koszyków, wysłanych e-maili i odzyskanych zamówień.
-   **Wpływ zmian:** Jest to ekran raportowania; nie dokonujesz tutaj bezpośrednich zmian, ale dane pomagają zrozumieć wpływ Twoich kampanii i kierują Twoimi wysiłkami optymalizacyjnymi w sekcji „Kampanie”.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie sprawdzaj ten panel (np. co tydzień), aby identyfikować trendy, sprawdzać, które kampanie są najskuteczniejsze i wykrywać wszelkie problemy. Wykorzystaj te dane do udoskonalenia strategii kampanii.

#### 2.2.3 Logi (Panel administracyjny > Abandoned Cart Reminder Pro > Logi)

Sekcja Logi zawiera szczegółową historię wszystkich działań podjętych przez moduł, pomagając w rozwiązywaniu problemów i weryfikacji jego działania.

-   **Nazwa ekranu i lokalizacja w menu:** **Abandoned Cart Reminder Pro > Logi**
-   **Dostępne działania i ustawienia:**
    *   **Tabela wpisów logów:** Tabela z możliwością wyszukiwania i filtrowania, wyświetlająca:
        *   **Sygnatura czasowa:** Kiedy zdarzenie miało miejsce.
        *   **Klient:** Klient związany ze zdarzeniem.
        *   **ID koszyka:** ID porzuconego koszyka.
        *   **Kampania/Krok:** Która kampania i krok wywołały zdarzenie.
        *   **Typ zdarzenia:** (np. „Koszyk porzucony”, „E-mail wysłany”, „E-mail otwarty”, „Link kliknięty”, „Koszyk odzyskany”, „Rabat zastosowany”).
        *   **Status:** Sukces lub niepowodzenie.
        *   **Szczegóły:** Dodatkowe informacje, takie jak podgląd treści e-maila lub komunikaty o błędach.
    *   **Podgląd e-maila:** Opcja podglądu dokładnej treści wysłanego e-maila.
-   **Wpływ zmian:** Jest to ekran diagnostyczny i audytowy. Nie dokonujesz tutaj zmian, ale jest on kluczowy do zrozumienia, dlaczego klient mógł nie otrzymać e-maila lub jeśli kampania nie działa zgodnie z oczekiwaniami.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Jeśli klient zgłosi, że nie otrzymał e-maila, lub jeśli współczynnik odzyskiwania spadnie niespodziewanie, sprawdź logi. Możesz zobaczyć, czy e-maile zostały pomyślnie wysłane, czy wystąpiły jakieś błędy, lub czy klienci zrezygnowali.

#### 2.2.4 Ustawienia (Panel administracyjny > Abandoned Cart Reminder Pro > Ustawienia)

Ten ekran zawiera globalne ustawienia, które wpływają na ogólne zachowanie modułu.

-   **Nazwa ekranu i lokalizacja w menu:** **Abandoned Cart Reminder Pro > Ustawienia**
-   **Dostępne działania i ustawienia:**
    *   **Ustawienia ogólne:**
        *   **Włącz moduł:** Włącz lub wyłącz cały moduł.
            *   *Efekt:* Gdy wyłączony, żadne koszyki nie będą śledzone, a żadne e-maile nie będą wysyłane.
            *   *Zalecane:* TAK, chyba że tymczasowo wyłączasz go do konserwacji.
        *   **Minimalna wartość koszyka do śledzenia:** Ustaw globalną minimalną wartość koszyka, aby każdy koszyk był uważany za „porzucony” i śledzony przez moduł.
            *   *Efekt:* Koszyki poniżej tej wartości będą ignorowane przez wszystkie kampanie.
            *   *Scenariusz sprzedawcy:* Unikaj wysyłania przypomnień dla bardzo małych koszyków, gdzie wysiłek odzyskiwania może nie być tego wart.
        *   **Czas uznania koszyka za porzucony:** Jak długo po ostatniej aktywności w koszyku koszyk powinien być uważany za porzucony (np. 30 minut, 1 godzina).
            *   *Efekt:* Określa, kiedy moduł zaczyna liczyć opóźnienie dla pierwszego e-maila przypominającego.
            *   *Zalecane:* 30-60 minut. Zbyt krótki czas może irytować klientów, zbyt długi może przegapić okno możliwości.
        *   **Limity antyspamowe:**
            *   **Maksymalna liczba e-maili na klienta:** Ogranicz całkowitą liczbę e-maili o porzuconych koszykach, które pojedynczy klient może otrzymać w danym okresie (np. 3 e-maile na 30 dni).
                *   *Efekt:* Zapobiega zasypywaniu klientów zbyt wieloma e-mailami, zmniejszając wskaźniki rezygnacji z subskrypcji.
                *   *Zalecane:* Ustaw rozsądne limity, aby utrzymać pozytywne doświadczenia klienta.
            *   **Minimalny czas między e-mailami:** Zapewnij minimalne opóźnienie między dwoma e-mailami wysłanymi do tego samego klienta.
                *   *Efekt:* Zapobiega wysyłaniu wielu e-maili z różnych kampanii zbyt blisko siebie.
        *   **RODO / Ustawienia rezygnacji:**
            *   **Włącz link rezygnacji:** Dołącz link w e-mailach przypominających, umożliwiający klientom rezygnację z przyszłych przypomnień.
                *   *Efekt:* Kluczowe dla zgodności z RODO i poszanowania prywatności klienta.
                *   *Zalecane:* TAK.
            *   **Treść strony rezygnacji:** Dostosuj tekst wyświetlany na stronie potwierdzenia rezygnacji.
        *   **URL zadania Cron:** Wyświetla dokładny adres URL, który należy ustawić jako zadanie cron na serwerze.
            *   *Efekt:* Ten adres URL uruchamia przetwarzanie w tle modułu, wysyłając e-maile i aktualizując statystyki.
            *   *Zalecane:* Skopiuj ten adres URL i skonfiguruj zadanie cron serwera, aby uruchamiało się co 5-15 minut.
    *   **Ustawienia e-maila:**
        *   **Nazwa i adres e-mail nadawcy:** Nazwa i adres e-mail, które pojawią się jako nadawca Twoich e-maili przypominających.
            *   *Efekt:* Wpływa na dostarczalność e-maili i sposób, w jaki klienci postrzegają Twoją markę.
            *   *Zalecane:* Użyj rozpoznawalnej nazwy sklepu i profesjonalnego adresu e-mail (np. `sprzedaz@twojsklep.com`, `noreply@twojsklep.com`).
        *   **Szablon e-maila:** Wybierz podstawowy szablon dla swoich e-maili przypominających (jeśli dostępnych jest wiele).
            *   *Efekt:* Określa ogólny projekt i układ Twoich e-maili.
    *   **Ustawienia zaawansowane:**
        *   **Tryb debugowania:** Włącz dla szczegółowego logowania (dla programistów).
            *   *Efekt:* Zapewnia bardziej szczegółowe informacje w logach, przydatne do rozwiązywania problemów.
            *   *Zalecane:* NIE, chyba że wyraźnie poprosi o to wsparcie.
-   **Wpływ zmian:** Te ustawienia kontrolują podstawowe zachowanie modułu, od momentu śledzenia koszyków po sposób, w jaki szanuje prywatność klienta i wysyła e-maile. Nieprawidłowe ustawienia mogą prowadzić do utraconych możliwości lub złych doświadczeń klienta.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Przejrzyj te ustawienia podczas początkowej konfiguracji i okresowo, aby upewnić się, że są zgodne z polityką i strategią marketingową Twojego sklepu. Zwróć szczególną uwagę na ustawienia antyspamowe i RODO.

#### 2.2.5 index.php (cartrempro/controllers/admin/index.php)

Ten plik jest standardową praktyką PrestaShop zapobiegającą bezpośredniemu listowaniu katalogów w folderach administracyjnych i zazwyczaj sam w sobie nie stanowi konfigurowalnego ekranu. Zapewnia bezpieczeństwo poprzez przekierowanie lub wyświetlenie pustej strony, jeśli ktoś spróbuje uzyskać bezpośredni dostęp do folderu.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | `PS_SSL_ENABLED` (Rdzeń PrestaShop) | TAK | Zapewnia bezpieczne linki HTTPS w e-mailach. |
| **Kampanie** | Nazwa kampanii | Opisowa | Wewnętrzna identyfikacja Twoich kampanii. |
| | Minimalna wartość koszyka | 0 (lub Twój próg) | Filtruje koszyki na podstawie wartości dla konkretnych kampanii. |
| | Grupy klientów | Wszystkie (lub konkretne) | Targetuje konkretne segmenty klientów. |
| | Produkty w koszyku | Brak (lub konkretne) | Targetuje koszyki zawierające konkretne produkty/kategorie. |
| | Opóźnienie kroku kampanii | 1h, 24h, 3d | Kontroluje czas wysyłania e-maili przypominających. |
| | Temat e-maila | Angażujący | Kluczowy dla współczynników otwarć. |
| | Treść e-maila | Spersonalizowana | Główna wiadomość do odzyskania koszyka. |
| | Kod rabatowy | Opcjonalny | Zachęta do konwersji. |
| | Testy A/B | Opcjonalne | Optymalizuje wydajność kampanii. |
| **Panel** | Wszystkie KPI | N/A (Raportowanie) | Zapewnia przegląd wydajności i ROI. |
| **Logi** | Wszystkie wpisy logów | N/A (Raportowanie) | Szczegółowa historia do rozwiązywania problemów i audytu. |
| **Ustawienia** | Włącz moduł | TAK | Włącza/wyłącza moduł. |
| | Min. wartość koszyka do śledzenia | 0 (lub Twój próg) | Globalny filtr dla wszystkich śledzonych koszyków. |
| | Czas uznania koszyka za porzucony | 30-60 minut | Definiuje, kiedy koszyk jest „porzucony”. |
| | Maks. liczba e-maili na klienta | Rozsądny limit | Zapobiega spamowaniu klientów. |
| | Min. czas między e-mailami | Rozsądny limit | Zapobiega szybkiemu wysyłaniu e-maili. |
| | Włącz link rezygnacji | TAK | Zgodność z RODO, wybór klienta. |
| | URL zadania Cron | Skopiuj z modułu | **KRYTYCZNE:** Umożliwia przetwarzanie w tle. |
| | Nazwa i adres e-mail nadawcy | Nazwa Twojego sklepu, profesjonalny e-mail | Wpływa na dostarczalność i zaufanie do marki. |
| | Tryb debugowania | NIE | Tylko do rozwiązywania problemów przez programistów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci nie otrzymują e-maili przypominających. Co powinienem sprawdzić?**
O1:

-   **Zadanie Cron:** To najczęstszy problem. Upewnij się, że Twoje zadanie cron jest poprawnie skonfigurowane na serwerze i działa regularnie (co 5-15 minut). Dokładny adres URL znajduje się w **Abandoned Cart Reminder Pro > Ustawienia**.
-   **Moduł włączony:** Sprawdź w **Abandoned Cart Reminder Pro > Ustawienia**, czy moduł jest globalnie włączony.
-   **Aktywne kampanie:** Sprawdź, czy Twoje kampanie są włączone i mają aktywne kroki w **Abandoned Cart Reminder Pro > Kampanie**.
-   **Konfiguracja e-maila:** Sprawdź ustawienia e-maila w PrestaShop (Parametry zaawansowane > E-mail), aby upewnić się, że Twój sklep może ogólnie wysyłać e-maile.
-   **Filtry antyspamowe:** Poproś klienta testowego o sprawdzenie folderu ze spamem/śmieciami. Upewnij się, że Twój adres e-mail nadawcy jest profesjonalny i nie znajduje się na czarnej liście.
-   **Logi:** Przejdź do **Abandoned Cart Reminder Pro > Logi**, aby sprawdzić, czy e-maile są kolejkowane, wysyłane, lub czy występują jakieś komunikaty o błędach.

**P2: Dlaczego niektóre porzucone koszyki nie uruchamiają kampanii?**
O2:

-   **Minimalna wartość koszyka:** Sprawdź globalną „Minimalną wartość koszyka do śledzenia” w **Abandoned Cart Reminder Pro > Ustawienia** oraz konkretną „Minimalną wartość koszyka” dla Twoich kampanii w **Abandoned Cart Reminder Pro > Kampanie**. Koszyki poniżej tych wartości zostaną zignorowane.
-   **Czas uznania koszyka za porzucony:** Upewnij się, że czas ustawiony w **Abandoned Cart Reminder Pro > Ustawienia** upłynął od ostatniej aktywności w koszyku.
-   **Grupy klientów/Targetowanie produktów:** Jeśli Twoja kampania ma określone targetowanie grup klientów lub produktów, upewnij się, że porzucony koszyk spełnia te kryteria.
-   **Limity antyspamowe:** Klient mógł osiągnąć limity „Maksymalna liczba e-maili na klienta” lub „Minimalny czas między e-mailami” ustawione w **Abandoned Cart Reminder Pro > Ustawienia**.
-   **Rezygnacja klienta:** Klient mógł wcześniej zrezygnować z otrzymywania przypomnień. Sprawdź logi.

**P3: Jak upewnić się, że e-maile przypominające wyglądają dobrze na urządzeniach mobilnych?**
O3: Moduł używa responsywnych szablonów e-mail. Jednak treść, którą dodajesz w kreatorze e-maili, może na to wpływać.

-   **Zachowaj prostotę:** Unikaj zbyt skomplikowanych układów lub bardzo szerokich obrazów.
-   **Testuj:** Zawsze wysyłaj do siebie e-mail testowy i przeglądaj go na różnych urządzeniach (komputer stacjonarny, tablet, telefon) przed aktywacją kampanii.
-   **Motyw PrestaShop:** Upewnij się, że Twój główny motyw PrestaShop jest responsywny mobilnie, ponieważ linki w e-mailach będą prowadzić z powrotem do Twojego sklepu.

**P4: Czy mogę przetłumaczyć treść e-maila i tematy?**
O4: Tak! Podczas edycji kroku kampanii zobaczysz zakładki językowe dla tematu i treści e-maila. Możesz dostarczyć różne tłumaczenia dla każdego języka zainstalowanego w Twoim sklepie PrestaShop. Jest to kluczowe dla sklepów międzynarodowych.

**P5: Wyczyściłem pamięć podręczną Smarty i teraz coś wygląda dziwnie. Co się stało?**
O5: Czyszczenie pamięci podręcznej Smarty (w **Parametry zaawansowane > Wydajność**) jest typowym krokiem rozwiązywania problemów z wyświetlaniem. Chociaż zazwyczaj jest to bezpieczne, czasami może tymczasowo wpływać na sposób renderowania treści przez moduły, dopóki pamięć podręczna nie zostanie przebudowana. Jeśli zauważysz problemy z wyświetlaniem po wyczyszczeniu pamięci podręcznej, spróbuj odświeżyć stronę kilka razy lub ponownie zapisać konfigurację modułu (nawet bez wprowadzania zmian), aby wymusić przebudowę pamięci podręcznej dla modułu. Ten moduł używa własnych mechanizmów buforowania, więc czyszczenie pamięci podręcznej Smarty nie powinno bezpośrednio wpływać na jego podstawową funkcjonalność, ale raczej na wyświetlanie jego interfejsu administracyjnego.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu „Abandoned Cart Reminder Pro” dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł opiera się na solidnej, sterowanej zdarzeniami architekturze, zgodnej z wzorcem MVC PrestaShop, gdzie to stosowne, ale także wykorzystuje niestandardowy kontener usług i automatyczne ładowanie dla lepszej organizacji i testowalności. W dużym stopniu polega na zadaniach cron do przetwarzania w tle, zapewniając, że wysyłanie e-maili i śledzenie koszyków nie wpływa na wydajność front-office. Kluczowe komponenty to:

-   **Śledzenie koszyka:** Wykorzystuje hooki `ActionCartSave` i `ActionValidateOrder` do monitorowania statusu koszyka.
-   **Silnik kampanii:** Zarządza wieloetapowymi sekwencjami e-maili, targetowaniem i generowaniem rabatów.
-   **Procesor kolejki:** Obsługuje asynchroniczne wysyłanie e-maili za pośrednictwem crona.
-   **Analityka i atrybucja:** Śledzi wskaźniki odzyskiwania i przychody.
-   **Kontrolery administracyjne:** Dedykowane kontrolery do zarządzania kampaniami, przeglądania logów i konfigurowania ustawień.
-   **Zgodność z RODO:** Zawiera mechanizm rezygnacji.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery obsługują specyficzne interakcje front-office, głównie w celu wykonania crona, śledzenia i rezygnacji.

-   `controllers/front/cron.php`
    *   **Nazwa klasy:** `CartRemProCronModuleFrontController` (rozszerza `ModuleFrontController`)
    *   **Odpowiedzialność:** Jest to główny punkt końcowy dla zadania cron modułu. Po uzyskaniu dostępu, uruchamia `CartRemProQueueProcessor` do przetwarzania kolejki porzuconych koszyków, wysyłania zaplanowanych e-maili i aktualizowania statystyk. Jest zaprojektowany do wywoływania przez zadanie cron po stronie serwera, a nie bezpośrednio przez użytkowników.
-   `controllers/front/index.php`
    *   **Nazwa klasy:** `CartRemProIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    *   **Odpowiedzialność:** Standardowa praktyka PrestaShop zapobiegająca bezpośredniemu listowaniu katalogów. Zazwyczaj przekierowuje do strony głównej sklepu lub wyświetla pustą stronę.
-   `controllers/front/optout.php`
    *   **Nazwa klasy:** `CartRemProOptoutModuleFrontController` (rozszerza `ModuleFrontController`)
    *   **Odpowiedzialność:** Obsługuje żądania klientów dotyczące rezygnacji z przypomnień o porzuconych koszykach. Przetwarza akcję `optout`, aktualizuje preferencje klienta i wyświetla stronę potwierdzenia (`optout.tpl`).
-   `controllers/front/track.php`
    *   **Nazwa klasy:** `CartRemProTrackModuleFrontController` (rozszerza `ModuleFrontController`)
    *   **Odpowiedzialność:** Służy do śledzenia otwarć e-maili i kliknięć linków w e-mailach przypominających. Rejestruje te zdarzenia w logach modułu, umożliwiając analizę zaangażowania w e-maile.

#### Kontrolery administracyjne Back-Office

Te kontrolery zarządzają interfejsem modułu w Panelu administracyjnym PrestaShop.

-   `controllers/admin/AdminCartRemProCampaignsController.php`
    *   **Nazwa zakładki:** Abandoned Cart Reminder Pro > Kampanie
    *   **Odpowiedzialność:** Zarządza tworzeniem, edycją, duplikowaniem i usuwaniem kampanii porzuconych koszyków. Obsługuje przesyłanie formularzy dla szczegółów kampanii, kroków, zasad targetowania i konfiguracji testów A/B. Współpracuje z klasami `CartRemProCampaign` i `CartRemProCampaignStep`.
-   `controllers/admin/AdminCartRemProDashboardController.php`
    *   **Nazwa zakładki:** Abandoned Cart Reminder Pro > Panel
    *   **Odpowiedzialność:** Wyświetla metryki wydajności modułu, w tym porzucone koszyki, odzyskane koszyki, przypisane przychody i ROI. Agreguje dane z `CartRemProAnalytics` i `CartRemProAbandoned`, aby przedstawić kompleksowy przegląd.
-   `controllers/admin/AdminCartRemProLogsController.php`
    *   **Nazwa zakładki:** Abandoned Cart Reminder Pro > Logi
    *   **Odpowiedzialność:** Zapewnia szczegółowy dziennik wszystkich działań modułu, takich jak porzucenia koszyków, wysyłki e-maili, otwarcia, kliknięcia i odzyskiwanie. Umożliwia filtrowanie i wyszukiwanie w tych logach w celu rozwiązywania problemów i audytu.
-   `controllers/admin/AdminCartRemProSettingsController.php`
    *   **Nazwa zakładki:** Abandoned Cart Reminder Pro > Ustawienia
    *   **Odpowiedzialność:** Zarządza globalnymi ustawieniami konfiguracyjnymi modułu, w tym włączaniem/wyłączaniem, limitami antyspamowymi, opcjami RODO i wyświetlaniem adresu URL zadania cron. Współpracuje z klasą `Configuration` PrestaShop.
-   `controllers/admin/index.php`
    *   **Odpowiedzialność:** Standardowy plik bezpieczeństwa PrestaShop zapobiegający bezpośredniemu listowaniu katalogów.

### 4.3 Klasy i modele rdzeniowe (`classes/`)

Moduł wykorzystuje bogaty zestaw niestandardowych klas dla swojej logiki biznesowej, wiele z nich rozszerza `ObjectModel` dla interakcji z bazą danych.

-   `classes/CartRemProAbandoned.php`
    *   **Tabela bazy danych:** `ps_cartrempro_abandoned`
    *   **Rozszerza:** `ObjectModel`
    *   **Pola `$definition`:** `id_cart`, `id_customer`, `id_shop`, `id_lang`, `cart_value`, `date_add`, `date_upd`, `is_recovered`, `is_optout`
    *   **Kluczowe metody publiczne:** Zarządza śledzeniem i statusem porzuconych koszyków.
-   `classes/CartRemProAbTesting.php`
    *   **Odpowiedzialność:** Obsługuje logikę testów A/B w krokach kampanii, w tym dzielenie ruchu i śledzenie współczynników konwersji dla różnych wariantów.
-   `classes/CartRemProAdminController.php`
    *   **Rozszerza:** `ModuleAdminController`
    *   **Odpowiedzialność:** Klasa bazowa dla kontrolerów administracyjnych modułu, zapewniająca wspólne funkcjonalności i narzędzia specyficzne dla interfejsu back-office modułu.
-   `classes/CartRemProAdminUi.php`
    *   **Odpowiedzialność:** Klasa pomocnicza do generowania i renderowania wspólnych elementów interfejsu użytkownika w panelu administracyjnym, zapewniająca spójność.
-   `classes/CartRemProAnalytics.php`
    *   **Odpowiedzialność:** Gromadzi i przetwarza dane dla panelu, obliczając KPI, takie jak współczynnik odzyskiwania, przypisane przychody i ROI.
-   `classes/CartRemProAntiSpam.php`
    *   **Odpowiedzialność:** Implementuje logikę dla limitów antyspamowych, zapewniając, że klienci nie otrzymują zbyt wielu e-maili w danym okresie.
-   `classes/CartRemProAttribution.php`
    *   **Odpowiedzialność:** Określa, czy odzyskany koszyk może być przypisany do konkretnej kampanii przypomnień o porzuconych koszykach.
-   `classes/CartRemProAutoload.php`
    *   **Odpowiedzialność:** Niestandardowy autoloader dla klas modułu, zapewniający ich efektywne ładowanie bez konfliktu z domyślnym autoloaderem PrestaShop.
-   `classes/CartRemProCampaign.php`
    *   **Tabela bazy danych:** `ps_cartrempro_campaign`
    *   **Rozszerza:** `ObjectModel`
    *   **Pola `$definition`:** `name`, `active`, `min_cart_value`, `customer_groups`, `products`, `categories`, `date_add`, `date_upd`
    *   **Kluczowe metody publiczne:** Reprezentuje kampanię porzuconych koszyków, zarządzając jej ustawieniami, zasadami targetowania i powiązanymi krokami.
-   `classes/CartRemProCampaignEngine.php`
    *   **Odpowiedzialność:** Główna logika do oceny porzuconych koszyków względem aktywnych kampanii, określania, która kampania (jeśli w ogóle) powinna zostać uruchomiona i planowania następnego kroku e-maila.
-   `classes/CartRemProCampaignStep.php`
    *   **Tabela bazy danych:** `ps_cartrempro_campaign_step`
    *   **Rozszerza:** `ObjectModel`
    *   **Pola `$definition`:** `id_cartrempro_campaign`, `delay_hours`, `subject`, `content`, `discount_type`, `discount_value`, `ab_test_active`, `ab_test_variations`
    *   **Kluczowe metody publiczne:** Definiuje pojedynczy krok w kampanii, w tym treść e-maila, opóźnienie i rabat.
-   `classes/CartRemProCartTracker.php`
    *   **Odpowiedzialność:** Monitoruje koszyki klientów, identyfikuje, kiedy stają się porzucone, i rejestruje je w tabeli `ps_cartrempro_abandoned`.
-   `classes/CartRemProChannelEmail.php`
    *   **Implementuje:** `CartRemProChannelInterface`
    *   **Odpowiedzialność:** Obsługuje faktyczne wysyłanie e-maili przypominających, w tym renderowanie szablonów e-maili i integrację z klasą Mail PrestaShop.
-   `classes/CartRemProChannelInterface.php`
    *   **Odpowiedzialność:** Definiuje wspólny interfejs dla różnych kanałów komunikacji (obecnie tylko e-mail, ale rozszerzalny o SMS, powiadomienia web push).
-   `classes/CartRemProCompat.php`
    *   **Odpowiedzialność:** Zapewnia warstwy kompatybilności dla różnych wersji PrestaShop (1.7, 8.x, 9.x), aby zapewnić płynne działanie w całym obsługiwanym zakresie.
-   `classes/CartRemProDiscountGenerator.php`
    *   **Odpowiedzialność:** Tworzy unikalne, jednorazowe kody rabatowe (Reguły koszyka) dla klientów, którzy otrzymują e-mail przypominający z ofertą rabatową.
-   `classes/CartRemProEmailRenderer.php`
    *   **Odpowiedzialność:** Renderuje szablony Smarty dla e-maili przypominających, wstrzykując dynamiczne dane, takie jak szczegóły koszyka, informacje o kliencie i kody rabatowe.
-   `classes/CartRemProGdpr.php`
    *   **Odpowiedzialność:** Zarządza funkcjami zgodności z RODO, w szczególności mechanizmem rezygnacji klienta.
-   `classes/CartRemProProductBlocks.php`
    *   **Odpowiedzialność:** Pomocnik do generowania bloków związanych z produktami w szablonach e-maili, takich jak listy produktów z porzuconego koszyka lub polecane produkty.
-   `classes/CartRemProQueueProcessor.php`
    *   **Odpowiedzialność:** Serce zadania cron. Pobiera zaplanowane zadania z kolejki (np. wysyłanie e-maila, sprawdzanie statusu koszyka), przetwarza je i aktualizuje logi.
-   `classes/CartRemProScheduleGuard.php`
    *   **Odpowiedzialność:** Zapewnia, że zaplanowane zadania są wykonywane tylko raz i w zamierzonych ramach czasowych, zapobiegając duplikowaniu e-maili lub działań.
-   `classes/CartRemProSegmentation.php`
    *   **Odpowiedzialność:** Implementuje logikę segmentacji klientów i koszyków na podstawie zasad targetowania kampanii (np. wartość koszyka, grupa klientów, produkty).
-   `classes/CartRemProServiceContainer.php`
    *   **Odpowiedzialność:** Niestandardowy kontener wstrzykiwania zależności do zarządzania i dostarczania instancji podstawowych usług i klas modułu, poprawiając modułowość i testowalność.
-   `classes/CartRemProStockChecker.php`
    *   **Odpowiedzialność:** Sprawdza poziomy zapasów produktów przed wysłaniem przypomnień, aby upewnić się, że produkty w porzuconym koszyku są nadal dostępne.
-   `classes/CartRemProTabInstaller.php`
    *   **Odpowiedzialność:** Obsługuje instalację i deinstalację zakładek menu administracyjnego modułu w Panelu administracyjnym PrestaShop.
-   `classes/index.php`
    *   **Odpowiedzialność:** Standardowy plik bezpieczeństwa PrestaShop zapobiegający bezpośredniemu listowaniu katalogów.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `cartrempro/devtools/crp-ab-stats-demo-console.js`
    *   **Zakres:** Back-office (narzędzia deweloperskie)
    *   **Odpowiedzialność:** Prawdopodobnie skrypt deweloperski do demonstrowania lub debugowania statystyk testów A/B w konsoli przeglądarki. Nie do użytku produkcyjnego.
-   `cartrempro/devtools/crp-dashboard-demo-console.js`
    *   **Zakres:** Back-office (narzędzia deweloperskie)
    *   **Odpowiedzialność:** Podobnie jak powyżej, do demonstrowania lub debugowania danych z panelu. Nie do użytku produkcyjnego.
-   `cartrempro/lib/searchTool/views/js/autocomplete.js`
    *   **Zakres:** Back-office (formularze administracyjne)
    *   **Odpowiedzialność:** Zapewnia funkcjonalność autouzupełniania dla pól wejściowych, prawdopodobnie używaną do wybierania produktów lub kategorii w targetowaniu kampanii. Wiąże się ze zdarzeniami wejściowymi i wykonuje wywołania AJAX w celu uzyskania sugestii wyszukiwania.
-   `cartrempro/views/js/admin-common.js`
    *   **Zakres:** Back-office (globalny administrator)
    *   **Odpowiedzialność:** Zawiera wspólne funkcje JavaScript i słuchacze zdarzeń używane na różnych ekranach administracyjnych modułu, takie jak ogólna obsługa formularzy, funkcje narzędziowe AJAX i ulepszenia interfejsu użytkownika.
-   `cartrempro/views/js/admin-dashboard.js`
    *   **Zakres:** Back-office (Panel)
    *   **Odpowiedzialność:** Obsługuje interaktywne elementy i wizualizację danych na panelu modułu, potencjalnie renderując wykresy lub dynamicznie aktualizując statystyki.
-   `cartrempro/views/js/campaigns-admin.js`
    *   **Zakres:** Back-office (Kampanie)
    *   **Odpowiedzialność:** Zarządza złożonym interfejsem użytkownika do tworzenia i edycji kampanii, w tym dodawania/usuwania kroków kampanii, konfigurowania zasad targetowania, obsługi opcji rabatowych i zarządzania wariantami testów A/B. Wiąże się ze zdarzeniami kliknięcia przycisków, zdarzeniami zmiany pól wyboru i przesyłaniem formularzy.
-   `cartrempro/views/js/email-builder.js`
    *   **Zakres:** Back-office (Kampanie - Treść e-maila)
    *   **Odpowiedzialność:** Ulepsza edytor tekstu sformatowanego używany do treści e-maila, potencjalnie dodając niestandardowe przyciski dla dynamicznych symboli zastępczych (np. `{{customer_name}}`, `{{cart_link}}`) lub zapewniając podgląd w czasie rzeczywistym.
-   `cartrempro/views/js/logs-admin.js`
    *   **Zakres:** Back-office (Logi)
    *   **Odpowiedzialność:** Zapewnia interaktywne funkcje dla tabeli logów, takie jak filtrowanie, wyszukiwanie, paginacja i potencjalnie wyskakujące okienka modalne do przeglądania podglądów e-maili.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `cartrempro/lib/searchTool/views/css/autocomplete.css`
    *   **Zakres:** Back-office (formularze administracyjne)
    *   **Główne komponenty interfejsu użytkownika:** Stylizuje sugestie rozwijane autouzupełniania i pola wejściowe używane w narzędziu wyszukiwania.
    *   **Kluczowe selektory klas CSS:** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`
-   `cartrempro/views/css/admin.css`
    *   **Zakres:** Back-office (globalny administrator)
    *   **Główne komponenty interfejsu użytkownika:** Zapewnia ogólne style dla interfejsu administracyjnego modułu, w tym układy panelu, formularze kampanii, tabele logów oraz ogólne style przycisków/pól wejściowych.
    *   **Kluczowe selektory klas CSS:** `.cartrempro-dashboard`, `.cartrempro-campaign-form`, `.cartrempro-logs-table`, `.crp-badge`, `.crp-stat-card`, itp.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

Moduł nie wymienia jawnie szablonów w katalogu `hook/`, co sugeruje, że renderowanie front-office dla hooków może być obsługiwane bezpośrednio w głównym pliku modułu lub za pośrednictwem konkretnych kontrolerów frontowych.

#### Szablony administracyjne (`views/templates/admin/`)

Te szablony renderują interfejs Back Office modułu.

-   `cartrempro/views/templates/admin/ab_email_preview.tpl`
    *   **Cel:** Wyświetla podgląd wariantu e-maila testu A/B.
-   `cartrempro/views/templates/admin/campaigns.tpl`
    *   **Cel:** Główny szablon dla ekranu administracyjnego „Kampanie”, wyświetlający listę kampanii i udostępniający formularze do dodawania/edycji.
-   `cartrempro/views/templates/admin/dashboard.tpl`
    *   **Cel:** Główny szablon dla ekranu „Panel”, wyświetlający KPI i wykresy wydajności.
-   `cartrempro/views/templates/admin/logs.tpl`
    *   **Cel:** Główny szablon dla ekranu „Logi”, przedstawiający tabelę działań modułu.
-   `cartrempro/views/templates/admin/logs_email_preview.tpl`
    *   **Cel:** Wyświetla podgląd e-maila z logów.
-   `cartrempro/views/templates/admin/settings.tpl`
    *   **Cel:** Główny szablon dla ekranu „Ustawienia”, zawierający globalne opcje konfiguracji.
-   `cartrempro/views/templates/admin/_partials/ab_stats.tpl`
    *   **Cel:** Renderuje statystyki dla wariantów testów A/B w ramach kampanii.
-   `cartrempro/views/templates/admin/_partials/campaign_form.tpl`
    *   **Cel:** Wielokrotnie używalny fragment formularza tworzenia/edycji kampanii, w tym kroki, targetowanie i ogólne ustawienia.
-   `cartrempro/views/templates/admin/_partials/campaign_list_compact.tpl`
    *   **Cel:** Renderuje kompaktową listę kampanii, być może dla widżetów panelu lub szybkich przeglądów.
-   `cartrempro/views/templates/admin/_partials/campaign_targeting.tpl`
    *   **Cel:** Renderuje sekcję zasad targetowania w formularzu kampanii.
-   `cartrempro/views/templates/admin/_partials/copy_box.tpl`
    *   **Cel:** Wielokrotnie używalny komponent do wyświetlania tekstu, który można łatwo skopiować (np. URL zadania cron).
-   `cartrempro/views/templates/admin/_partials/empty_state.tpl`
    *   **Cel:** Wyświetla komunikat, gdy lista lub sekcja jest pusta (np. „Nie znaleziono kampanii”).
-   `cartrempro/views/templates/admin/_partials/icon_duplicate.tpl`
    *   **Cel:** Renderuje ikonę duplikowania.
-   `cartrempro/views/templates/admin/_partials/icon_edit.tpl`
    *   **Cel:** Renderuje ikonę edycji.
-   `cartrempro/views/templates/admin/_partials/icon_trash.tpl`
    *   **Cel:** Renderuje ikonę kosza/usuwania.
-   `cartrempro/views/templates/admin/_partials/page_header.tpl`
    *   **Cel:** Renderuje spójny nagłówek dla stron administracyjnych w module.
-   `cartrempro/views/templates/admin/_partials/status_badge.tpl`
    *   **Cel:** Renderuje wizualną plakietkę wskazującą status (np. „Aktywny”, „Nieaktywny”).
-   `cartrempro/views/templates/admin/_partials/stat_card.tpl`
    *   **Cel:** Renderuje pojedynczą kartę statystyczną dla panelu (np. „Odzyskane koszyki”).
-   `cartrempro/views/templates/admin/_partials/step_subject_lang.tpl`
    *   **Cel:** Renderuje pole wejściowe tematu z zakładkami językowymi dla kroków kampanii.
-   `cartrempro/views/templates/admin/_partials/toggle_row.tpl`
    *   **Cel:** Renderuje wiersz z przełącznikiem (np. do włączania/wyłączania ustawienia).

#### Szablony front-office (`views/templates/front/`)

-   `cartrempro/views/templates/front/optout.tpl`
    *   **Cel:** Wyświetla stronę potwierdzenia po rezygnacji klienta z przypomnień o porzuconych koszykach.

#### Szablony e-mail (`views/templates/email/`)

-   `cartrempro/views/templates/email/default_recovery.tpl`
    *   **Cel:** Domyślny szablon bazowy dla e-maili przypominających o porzuconych koszykach. Zawiera symbole zastępcze dla dynamicznej treści, takiej jak imię klienta, link do koszyka, lista produktów i kody rabatowe. Deweloperzy mogą dostosować ten szablon lub tworzyć nowe dla różnych projektów e-maili.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł tworzy następujące niestandardowe tabele podczas instalacji:

-   `ps_cartrempro_abandoned`: Przechowuje szczegóły porzuconych koszyków.
    *   `id_cartrempro_abandoned` (PK)
    *   `id_cart` (FK do `ps_cart`)
    *   `id_customer` (FK do `ps_customer`)
    *   `id_shop` (FK do `ps_shop`)
    *   `id_lang` (FK do `ps_lang`)
    *   `cart_value` (decimal)
    *   `date_add` (datetime)
    *   `date_upd` (datetime)
    *   `is_recovered` (tinyint)
    *   `is_optout` (tinyint)
-   `ps_cartrempro_campaign`: Przechowuje szczegóły każdej kampanii przypomnień.
    *   `id_cartrempro_campaign` (PK)
    *   `name` (varchar)
    *   `active` (tinyint)
    *   `min_cart_value` (decimal)
    *   `customer_groups` (text - serialized array)
    *   `products` (text - serialized array)
    *   `categories` (text - serialized array)
    *   `date_add` (datetime)
    *   `date_upd` (datetime)
-   `ps_cartrempro_campaign_step`: Przechowuje szczegóły każdego kroku w kampanii.
    *   `id_cartrempro_campaign_step` (PK)
    *   `id_cartrempro_campaign` (FK do `ps_cartrempro_campaign`)
    *   `delay_hours` (int)
    *   `subject` (text - multi-lang)
    *   `content` (text - multi-lang)
    *   `discount_type` (varchar)
    *   `discount_value` (decimal)
    *   `ab_test_active` (tinyint)
    *   `ab_test_variations` (text - serialized array)
-   `ps_cartrempro_log`: Przechowuje szczegółowe logi działań modułu.
    *   `id_cartrempro_log` (PK)
    *   `id_cart`
    *   `id_customer`
    *   `id_cartrempro_campaign`
    *   `id_cartrempro_campaign_step`
    *   `event_type` (varchar)
    *   `details` (text)
    *   `date_add` (datetime)
-   `ps_cartrempro_queue`: Przechowuje zadania zaplanowane dla zadania cron.
    *   `id_cartrempro_queue` (PK)
    *   `id_cart`
    *   `id_cartrempro_campaign`
    *   `id_cartrempro_campaign_step`
    *   `task_type` (varchar)
    *   `scheduled_at` (datetime)
    *   `processed_at` (datetime)
    *   `status` (varchar)
    *   `error_message` (text)

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `ActionObjectCartUpdateAfter` | Po zaktualizowaniu obiektu `Cart` (np. dodano/usunięto produkt, zmieniono ilość). | Służy do śledzenia zmian w koszykach klientów i identyfikowania potencjalnych porzuceń. |
| `actionDispatcher` | Przed wysłaniem kontrolera. | Potencjalnie używany do routingu, przepisywania adresów URL lub wczesnej inicjalizacji. |
| `ActionCronJob` | Gdy uruchamia się natywne zadanie cron PrestaShop (jeśli skonfigurowano). | Uruchamia kontroler `cron.php` modułu do przetwarzania kolejki. |
| `ActionFrontControllerInit` | Przed inicjalizacją dowolnego kontrolera frontowego. | Używany do wczesnej konfiguracji, takiej jak rejestrowanie zasobów modułu lub specyficznego routingu. |
| `moduleRoutes` | Podczas generowania routingu URL. | Umożliwia modułowi definiowanie niestandardowych, przyjaznych adresów URL dla jego kontrolerów frontowych (np. `/cartrempro/optout`). |
| `displayModuleRoutes` | Podobnie jak `moduleRoutes`, często używany do wyświetlania lub debugowania tras. | Mniej powszechne dla logiki funkcjonalnej, bardziej do debugowania. |
| `ActionCartSave` | Po zapisaniu koszyka w bazie danych. | Kluczowe dla śledzenia aktywności koszyka i identyfikowania, kiedy koszyk staje się porzucony. |
| `ActionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Służy do oznaczania porzuconego koszyka jako „odzyskany”, jeśli prowadzi do zrealizowanego zakupu. |
| `ActionCustomerAccountAdd` | Po utworzeniu nowego konta klienta. | Potencjalnie używany do segmentacji lub początkowego śledzenia klientów, choć mniej krytyczny dla podstawowej logiki porzuconych koszyków. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół jest zaangażowany w zapewnianie terminowej pomocy i zapewnienie płynnego działania Twojego modułu.

-   **MyPresta.eu Historia zamówień i pobieranie:** <https://mypresta.eu/my-account/orders/>
-   **Kontakt z pomocą techniczną:** [support@mypresta.eu](mailto:support@mypresta.eu)
