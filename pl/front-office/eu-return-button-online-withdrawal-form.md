---
title: "Przycisk zwrotu UE – Formularz odstąpienia od umowy online - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Przycisk zwrotu UE – Formularz odstąpienia od umowy online” od MyPresta.eu."
sidebar:
  label: "Przycisk zwrotu UE – Formularz odstąpienia od umowy online - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł EU Return Button – Online Withdrawal Form na MyPresta.eu](https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/eu-return-button-online-withdrawal-form/)
>
> ---


# Przycisk zwrotu UE – Formularz odstąpienia od umowy online

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji, na którym kontrolujesz ogólne zachowanie i wygląd przycisku zwrotu i formularza.

#### Zakładka Ustawienia ogólne

-   **Włącz moduł:**

    -   **Co robi to ustawienie:** Jest to główny przełącznik dla całego modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Przycisk zwrotu i formularz odstąpienia od umowy online stają się aktywne i widoczne dla klientów zgodnie z innymi ustawieniami.
        -   *Gdy wyłączony:* Moduł jest całkowicie dezaktywowany. Przycisk nie pojawi się, a formularze nie będą dostępne.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Wyłączysz to tylko wtedy, gdy tymczasowo chcesz przestać oferować zwroty online, być może podczas konserwacji lub zmiany polityki.
-   **Wyświetl przycisk zwrotu w:**

    -   **Co robi to ustawienie:** Określa, gdzie główny przycisk „Zwrot” lub „Odstąpienie od umowy” pojawi się w front-office Twojego sklepu. Możesz wybrać wiele lokalizacji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrane (np. Nagłówek):* Przycisk pojawi się w wybranej lokalizacji, zapewniając bezpośredni link do formularza zwrotu.
        -   *Gdy niewybrane:* Przycisk nie pojawi się w tej konkretnej lokalizacji.
    -   **Zalecana wartość:** Nagłówek i/lub Stopka dla łatwego dostępu oraz Strona produktu, aby informować klientów z góry.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby klienci łatwo znaleźli opcję zwrotu z dowolnej strony, włącz „Nagłówek” i „Stopkę”. Jeśli chcesz podkreślić swoją politykę zwrotów na stronach produktów, włącz „Strona produktu”.
-   **Tekst przycisku:**

    -   **Co robi to ustawienie:** Umożliwia dostosowanie tekstu wyświetlanego na przycisku zwrotu.
    -   **Efekt zmiany tego ustawienia:** Tekst na przycisku zmieni się na określoną wartość.
    -   **Zalecana wartość:** „Wniosek o zwrot”, „Formularz odstąpienia od umowy online” lub „Rozpocznij zwrot”.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz zmienić go z „Zwrot” na „Formularz odstąpienia od umowy”, aby dostosować się do specyficznej terminologii prawnej w Twoim regionie.
-   **Minimalny status zamówienia dla odstąpienia od umowy:**

    -   **Co robi to ustawienie:** Definiuje najwcześniejszy status zamówienia, przy którym klient może zainicjować wniosek o zwrot dla zamówienia. Zamówienia o statusie niższym niż ten nie będą kwalifikować się.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na „Płatność zaakceptowana”:* Klienci mogą żądać zwrotu dopiero po pomyślnym przetworzeniu płatności.
        -   *Gdy ustawione na „Wysłane”:* Klienci mogą żądać zwrotu dopiero po oznaczeniu zamówienia jako wysłane.
    -   **Zalecana wartość:** „Płatność zaakceptowana” lub „Wysłane”, w zależności od Twojej polityki.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli akceptujesz zwroty tylko dla przedmiotów, które zostały faktycznie opłacone i przetworzone, ustaw to na „Płatność zaakceptowana”. Jeśli akceptujesz zwroty tylko dla przedmiotów, które już opuściły Twój magazyn, ustaw to na „Wysłane”.
-   **Maksymalna liczba dni na odstąpienie od umowy:**

    -   **Co robi to ustawienie:** Ustawia maksymalną liczbę dni od złożenia zamówienia (lub wysyłki, w zależności od Twojej polityki), w ciągu których klient może złożyć wniosek o zwrot.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na 14:* Klienci mają 14 dni od daty zamówienia na złożenie wniosku o zwrot. Po 14 dniach opcja ta nie będzie już dostępna dla tego zamówienia.
        -   *Gdy ustawione na 30:* Klienci mają 30 dni.
    -   **Zalecana wartość:** 14 (dla standardowej zgodności z UE) lub 30 (jeśli oferujesz wydłużony okres zwrotu).
    -   **Scenariusz / przykład dla sprzedawcy:** Aby zachować zgodność ze standardowym 14-dniowym prawem do odstąpienia od umowy w UE, ustaw to na 14. Jeśli oferujesz bardziej hojną politykę, możesz wydłużyć ją do 30 lub więcej.
-   **Zezwól na odstąpienia od umowy dla gości:**

    -   **Co robi to ustawienie:** Określa, czy klienci, którzy dokonali zakupu jako goście (bez tworzenia konta), mogą korzystać z formularza odstąpienia od umowy online.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klienci-goście mogą uzyskać dostęp do formularza, podając numer referencyjny zamówienia i adres e-mail.
        -   *Gdy wyłączone:* Tylko zarejestrowani i zalogowani klienci mogą zainicjować zwrot.
    -   **Zalecana wartość:** TAK (dla maksymalnej wygody klienta i zgodności z UE).
    -   **Scenariusz / przykład dla sprzedawcy:** Włączenie tej opcji zapewnia, że wszyscy klienci, niezależnie od metody płatności, mogą łatwo zainicjować zwrot, co jest kluczowe dla zgodności i satysfakcji klienta.
-   **Zezwól na załączniki:**

    -   **Co robi to ustawienie:** Umożliwia klientom przesyłanie plików (np. zdjęć uszkodzonych produktów, dowodu zakupu) podczas składania wniosku o zwrot.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Na formularzu pojawi się pole do przesyłania plików.
        -   *Gdy wyłączone:* Klienci nie mogą przesyłać plików.
    -   **Zalecana wartość:** TAK (zwłaszcza dla produktów, gdzie dowód wizualny może być potrzebny w przypadku uszkodzeń lub wad).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz delikatne przedmioty, zezwolenie na załączniki pomaga klientom szybko dostarczyć dowody uszkodzeń, przyspieszając proces rozwiązywania problemu.
-   **Maksymalny rozmiar załącznika (MB):**

    -   **Co robi to ustawienie:** Ustawia maksymalny rozmiar pliku dla każdego załącznika, który klient może przesłać.
    -   **Efekt zmiany tego ustawienia:** Pliki większe niż ten limit zostaną odrzucone przez formularz.
    -   **Zalecana wartość:** 2-5 MB.
    -   **Scenariusz / przykład dla sprzedawcy:** Ustawienie rozsądnego limitu zapobiega przesyłaniu przez klientów nadmiernie dużych plików, które mogłyby spowolnić serwer lub system e-mail.
-   **Dozwolone rozszerzenia załączników (oddzielone przecinkami):**

    -   **Co robi to ustawienie:** Określa, jakie typy plików (np. jpg, png, pdf) klienci mogą przesyłać.
    -   **Efekt zmiany tego ustawienia:** Akceptowane będą tylko pliki z tymi rozszerzeniami.
    -   **Zalecana wartość:** jpg, jpeg, png, gif, pdf.
    -   **Scenariusz / przykład dla sprzedawcy:** Ograniczenie do popularnych formatów obrazów i dokumentów zapewnia otrzymywanie użytecznych plików i zapobiega złośliwym przesyłkom.
-   **Wymagaj wiadomości o statusie:**

    -   **Co robi to ustawienie:** Gdy zmieniasz status wniosku o zwrot w panelu administracyjnym, to ustawienie określa, czy musisz dodać wiadomość do klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Pole wprowadzania wiadomości będzie obowiązkowe podczas aktualizacji statusu zwrotu.
        -   *Gdy wyłączone:* Możesz zmieniać statusy bez dodawania wiadomości.
    -   **Zalecana wartość:** TAK (dla jasnej komunikacji i ścieżek audytu).
    -   **Scenariusz / przykład dla sprzedawcy:** Włączenie tej opcji zapewnia, że Twój zespół zawsze podaje powód lub aktualizację klientowi podczas zmiany statusu, poprawiając przejrzystość.

#### Zakładka Statusy zamówień

Ta zakładka umożliwia zdefiniowanie różnych statusów dla wniosków o zwrot i sposobu ich interakcji z istniejącymi statusami zamówień PrestaShop.

-   **Nowy status odstąpienia od umowy:**

    -   **Co robi to ustawienie:** Wybiera status zamówienia PrestaShop, który zostanie przypisany do nowego wniosku o zwrot, gdy zostanie on po raz pierwszy złożony przez klienta.
    -   **Efekt zmiany tego ustawienia:** Wszystkie nowe wnioski o zwrot zostaną automatycznie oznaczone tym statussem w Twoim panelu administracyjnym.
    -   **Zalecana wartość:** Utwórz nowy niestandardowy status zamówienia, taki jak „Zwrot zażądany” lub „Odstąpienie od umowy w toku” dla jasnej identyfikacji.
    -   **Scenariusz / przykład dla sprzedawcy:** Tworząc konkretny status „Zwrot zażądany”, Twój zespół obsługi klienta może łatwo filtrować i identyfikować nowe wnioski o zwrot, które wymagają ich uwagi.
-   **Zaakceptowany status odstąpienia od umowy:**

    -   **Co robi to ustawienie:** Wybiera status zamówienia PrestaShop, który zostanie przypisany, gdy Ty, jako sprzedawca, zaakceptujesz wniosek o zwrot klienta.
    -   **Efekt zmiany tego ustawienia:** Gdy oznaczysz zwrot jako „Zaakceptowany” w module, jego status zmieni się na wybrany status zamówienia.
    -   **Zalecana wartość:** Utwórz nowy niestandardowy status zamówienia, taki jak „Zwrot zaakceptowany” lub „Odstąpienie od umowy zatwierdzone”.
    -   **Scenariusz / przykład dla sprzedawcy:** Po przejrzeniu wniosku i jego zatwierdzeniu, zmiana jego statusu na „Zwrot zaakceptowany” może wywołać wysłanie e-maila do klienta z dalszymi instrukcjami.
-   **Odrzucony status odstąpienia od umowy:**

    -   **Co robi to ustawienie:** Wybiera status zamówienia PrestaShop, który zostanie przypisany, gdy odrzucisz wniosek o zwrot klienta.
    -   **Efekt zmiany tego ustawienia:** Gdy oznaczysz zwrot jako „Odrzucony” w module, jego status zmieni się na wybrany status zamówienia.
    -   **Zalecana wartość:** Utwórz nowy niestandardowy status zamówienia, taki jak „Zwrot odrzucony” lub „Odstąpienie od umowy odrzucone”.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli wniosek o zwrot wykracza poza Twoją politykę (np. po upływie terminu zwrotu), zmienisz jego status na „Zwrot odrzucony” i idealnie wyślesz wiadomość wyjaśniającą dlaczego.
-   **Zamknięty status odstąpienia od umowy:**

    -   **Co robi to ustawienie:** Wybiera status zamówienia PrestaShop, który zostanie przypisany, gdy wniosek o zwrot zostanie zakończony lub rozwiązany (np. zwrot pieniędzy, wysłana wymiana).
    -   **Efekt zmiany tego ustawienia:** Gdy oznaczysz zwrot jako „Zamknięty” w module, jego status zmieni się na wybrany status zamówienia.
    -   **Zalecana wartość:** Utwórz nowy niestandardowy status zamówienia, taki jak „Zwrot zakończony” lub „Odstąpienie od umowy zamknięte”.
    -   **Scenariusz / przykład dla sprzedawcy:** Po przetworzeniu zwrotu pieniędzy, oznaczenie zwrotu jako „Zwrot zakończony” zapewnia jasną ścieżkę audytu i usuwa go z aktywnej kolejki zwrotów.
-   **Statusy zamówień do wykluczenia z odstąpienia od umowy:**

    -   **Co robi to ustawienie:** Umożliwia wybranie konkretnych statusów zamówień PrestaShop, dla których klienci *nie mogą* zainicjować wniosku o zwrot, nawet jeśli spełniają inne kryteria.
    -   **Efekt zmiany tego ustawienia:** Zamówienia z dowolnym z wybranych statusów nie będą wyświetlać opcji zwrotu klientowi.
    -   **Zalecana wartość:** „Anulowane”, „Zwrócone”, „Błąd” lub dowolny inny status, który oznacza, że zamówienie nie kwalifikuje się już do nowego wniosku o zwrot.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli zamówienie zostało już „Zwrócone”, nie chciałbyś, aby klient mógł złożyć kolejny wniosek o zwrot dla niego.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### Wnioski o odstąpienie od umowy (Panel administracyjny > Zamówienia > Wnioski o odstąpienie od umowy)

Jest to centralne miejsce do zarządzania wszystkimi wnioskami o zwrot i odstąpienie od umowy złożonymi przez Twoich klientów.

-   **Nazwa ekranu i lokalizacja w menu:** Ten ekran znajdziesz, przechodząc do **Zamówienia > Wnioski o odstąpienie od umowy** w menu panelu administracyjnego PrestaShop.
-   **Dostępne działania i ustawienia:**
    -   **Tabela listująca:** Wyświetla kompleksową listę wszystkich wniosków o zwrot, w tym:
        -   **ID:** Unikalny identyfikator wniosku.
        -   **Nazwa klienta:** Klient, który złożył wniosek.
        -   **Numer referencyjny zamówienia:** Powiązane zamówienie PrestaShop.
        -   **Data:** Kiedy wniosek został złożony.
        -   **Status:** Aktualny status wniosku (np. „Zwrot zażądany”, „Zwrot zaakceptowany”).
        -   **Działania:** Przyciski do „Wyświetlenia” szczegółów wniosku, zmiany jego statusu lub wykonania innych zadań zarządzania.
    -   **Filtrowanie i wyszukiwanie:** Możesz filtrować listę według statusu, klienta, numeru referencyjnego zamówienia i zakresu dat, aby szybko znaleźć konkretne wnioski.
    -   **Działania masowe:** Umożliwia wybranie wielu wniosków i jednoczesne wykonanie działań, takich jak zmiana ich statusu.
    -   **Wyświetl szczegóły:** Kliknięcie „Wyświetl” dla konkretnego wniosku otwiera szczegółową stronę, na której możesz:
        -   Zobaczyć wszystkie informacje podane przez klienta (powód, komentarze, załączone pliki).
        -   Przejrzeć produkty uwzględnione we wniosku o zwrot.
        -   Wyświetlić historię zmian statusu i wewnętrzne notatki.
        -   Dodać prywatne notatki do wewnętrznej komunikacji zespołu.
        -   Zmienić status wniosku (np. z „Zwrot zażądany” na „Zwrot zaakceptowany”).
        -   Wysłać wiadomości do klienta (jeśli włączono „Wymagaj wiadomości o statusie”).
        -   Pobrać załączniki.
        -   Wydrukować formularz odstąpienia od umowy.
-   **Efekt zmian:**
    -   **Zmiana statusu:** Aktualizuje status wniosku o zwrot, co może wywołać powiadomienia e-mail do klienta i zaktualizować wyświetlanie na jego koncie klienta.
    -   **Dodawanie notatek:** Rejestruje wewnętrzną komunikację lub decyzje związane z wnioskiem, widoczne tylko dla użytkowników panelu administracyjnego.
    -   **Wysyłanie wiadomości:** Komunikuje się bezpośrednio z klientem w sprawie jego wniosku o zwrot.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Regularnie sprawdzaj listę „Wnioski o odstąpienie od umowy” pod kątem nowych wniosków (status „Zwrot zażądany”).
    2.  Przejrzyj każdy nowy wniosek, sprawdzając szczegóły zamówienia, komentarze klienta i wszelkie załączniki.
    3.  Zdecyduj, czy zaakceptować, czy odrzucić wniosek na podstawie polityki zwrotów Twojego sklepu.
    4.  Zmień status odpowiednio (np. na „Zwrot zaakceptowany” lub „Zwrot odrzucony”). Jeśli włączono „Wymagaj wiadomości o statusie”, podaj jasną wiadomość klientowi.
    5.  Wykonaj kolejne kroki (np. wystaw zwrot pieniędzy, zorganizuj wysyłkę zwrotną) i zaktualizuj status na „Zwrot zakończony” po rozwiązaniu problemu.
    6.  Używaj wewnętrznych notatek do komunikacji zespołowej lub do rejestrowania konkretnych podjętych działań.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Włącz moduł | TAK | Aktywuje/dezaktywuje cały moduł. |
| | Wyświetl przycisk zwrotu w | Nagłówek, Stopka, Strona produktu | Kontroluje, gdzie przycisk zwrotu pojawia się w front-office. |
| | Tekst przycisku | „Wniosek o zwrot” | Dostosowuje tekst na przycisku zwrotu. |
| | Minimalny status zamówienia dla odstąpienia od umowy | „Płatność zaakceptowana” | Ustawia najwcześniejszy status zamówienia dla kwalifikacji do zwrotu. |
| | Maksymalna liczba dni na odstąpienie od umowy | 14 | Definiuje okno zwrotu w dniach od daty zamówienia. |
| | Zezwól na odstąpienia od umowy dla gości | TAK | Umożliwia niezarejestrowanym klientom korzystanie z formularza. |
| | Zezwól na załączniki | TAK | Włącza/wyłącza przesyłanie plików w formularzu. |
| | Maksymalny rozmiar załącznika (MB) | 2-5 MB | Ustawia maksymalny rozmiar dla przesyłanych plików. |
| | Dozwolone rozszerzenia załączników | jpg, jpeg, png, gif, pdf | Określa dozwolone typy plików do przesyłania. |
| | Wymagaj wiadomości o statusie | TAK | Sprawia, że wiadomość jest obowiązkowa przy zmianie statusu zwrotu. |
| **Zakładka Statusy zamówień** | Nowy status odstąpienia od umowy | „Zwrot zażądany” (niestandardowy) | Status dla nowo złożonych wniosków. |
| | Zaakceptowany status odstąpienia od umowy | „Zwrot zaakceptowany” (niestandardowy) | Status, gdy sprzedawca zatwierdza wniosek. |
| | Odrzucony status odstąpienia od umowy | „Zwrot odrzucony” (niestandardowy) | Status, gdy sprzedawca odrzuca wniosek. |
| | Zamknięty status odstąpienia od umowy | „Zwrot zakończony” (niestandardowy) | Status, gdy wniosek jest w pełni rozwiązany. |
| | Statusy zamówień do wykluczenia z odstąpienia od umowy | „Anulowane”, „Zwrócone” | Zapobiega zwrotom dla zamówień z tymi statusami. |
| **Wnioski o odstąpienie od umowy (Admin)** | Wyświetl/Edytuj wniosek | N/A | Zarządzaj indywidualnymi wnioskami o zwrot, zmieniaj status, dodawaj notatki. |
| | Filtruj/Szukaj | N/A | Lokalizuj konkretne wnioski według różnych kryteriów. |
| | Działania masowe | N/A | Wykonuj działania na wielu wybranych wnioskach. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Przycisk zwrotu nie wyświetla się w moim sklepie. Co powinienem zrobić?**
O1:

-   **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów**, znajdź „Przycisk zwrotu UE – Formularz odstąpienia od umowy online” i upewnij się, że jest „Włączony”.
-   **Sprawdź miejsca wyświetlania:** W konfiguracji modułu, w zakładce „Ustawienia ogólne”, sprawdź, czy wybrano co najmniej jedno miejsce „Wyświetl przycisk zwrotu w” (np. Nagłówek, Stopka).
-   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stara zawartość pamięci podręcznej uniemożliwia pojawienie się nowych elementów modułu.
-   **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany z myślą o szerokiej kompatybilności, niestandardowe motywy mogą wymagać drobnych dostosowań. Jeśli przycisk nadal się nie pojawia, skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły dotyczące Twojego motywu.

**P2: Klienci zgłaszają, że nie mogą złożyć zwrotu dla konkretnego zamówienia, mimo że mieści się ono w okresie zwrotu.**
O2:

-   **Sprawdź minimalny status zamówienia:** W konfiguracji modułu, w zakładce „Ustawienia ogólne”, sprawdź „Minimalny status zamówienia dla odstąpienia od umowy”. Upewnij się, że zamówienie klienta osiągnęło ten status. Na przykład, jeśli jest ustawione na „Wysłane”, a zamówienie nadal ma status „Płatność zaakceptowana”, klient nie zobaczy tej opcji.
-   **Sprawdź wykluczone statusy zamówień:** W konfiguracji modułu, w zakładce „Statusy zamówień”, sprawdź „Statusy zamówień do wykluczenia z odstąpienia od umowy”. Jeśli zamówienie klienta ma jeden z tych statusów (np. „Anulowane”, „Zwrócone”), nie będzie mógł zainicjować nowego zwrotu.
-   **Maksymalna liczba dni na odstąpienie od umowy:** Dokładnie sprawdź ustawienie „Maksymalna liczba dni na odstąpienie od umowy”. Okno zwrotu mogło wygasnąć dla tego konkretnego zamówienia.

**P3: Zmieniłem ustawienie, ale nie jest ono odzwierciedlone w front-office.**
O3:

-   **Wyczyść pamięć podręczną:** Jest to najczęstszy powód. Zawsze czyść pamięć podręczną PrestaShop po wprowadzeniu zmian konfiguracyjnych w dowolnym module. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Jeśli używasz modułu buforowania innej firmy lub CDN, wyczyść również ich pamięci podręczne.
-   **Pamięć podręczna przeglądarki:** Poproś swoich klientów (lub siebie) o wyczyszczenie pamięci podręcznej przeglądarki lub spróbuj wyświetlić stronę w trybie incognito/prywatnym, aby wykluczyć problemy z buforowaniem po stronie przeglądarki.

**P4: Jak przetłumaczyć tekst modułu na inne języki?**
O4:

-   Przejdź do **Lokalizacja > Tłumaczenia** w panelu administracyjnym PrestaShop.
-   Wybierz „Tłumaczenia zainstalowanych modułów”.
-   Wybierz swój motyw, język, na który chcesz przetłumaczyć, a następnie wybierz „Przycisk zwrotu UE – Formularz odstąpienia od umowy online” z listy modułów.
-   Zobaczysz listę wszystkich przetłumaczalnych ciągów w module, w tym tekst przycisku, etykiety formularzy i wiadomości. Wprowadź swoje tłumaczenia i zapisz.

**P5: Chcę dostosować wygląd formularza zwrotu do mojego motywu.**
O5:

-   Moduł zawiera pliki CSS (`front-classic.css`, `front-hummingbird.css`, `front.css`) zaprojektowane dla popularnych motywów PrestaShop.
-   Do zaawansowanego stylizowania potrzebny będzie programista stron internetowych. Może on zbadać strukturę HTML modułu i nadpisać jego reguły CSS w pliku `custom.css` Twojego motywu lub tworząc nowy arkusz stylów, który ładuje się po CSS modułu. Unikaj bezpośredniej edycji plików CSS modułu, ponieważ Twoje zmiany zostaną utracone podczas aktualizacji.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Przycisk zwrotu UE – Formularz odstąpienia od umowy online” (`rbpro`) jest zgodny ze standardową architekturą MVC (Model-View-Controller) PrestaShop. Wykorzystuje `ModuleFrontController` do interakcji z klientem i `AdminController` do zarządzania w panelu administracyjnym. Podstawowa logika biznesowa jest hermetyzowana w dedykowanych klasach usług i ObjectModel, zapewniając integralność danych i separację odpowiedzialności. Moduł integruje się z systemem hooków PrestaShop w celu dynamicznego wstrzykiwania treści i wykorzystuje Smarty do tworzenia szablonów. Zawiera również warstwy kompatybilności dla różnych wersji PrestaShop oraz klasę bezpieczeństwa do walidacji danych wejściowych.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery front-office

Te kontrolery obsługują interakcje klienta związane z formularzem zwrotu i śledzeniem statusu.

-   `rbpro/controllers/front/confirm.php`

    -   **Nazwa klasy:** `RbpConfirmModuleFrontController` (rozszerza `RbpModuleFrontController`)
    -   **Odpowiedzialność:** Wyświetla ostatni krok potwierdzenia formularza odstąpienia od umowy. Przetwarza przesłane dane formularza, tworzy wpis `RbpWithdrawal` i przekierowuje do strony sukcesu lub błędu. Obsługuje walidację danych przed zapisaniem.
-   `rbpro/controllers/front/form.php`

    -   **Nazwa klasy:** `RbpFormModuleFrontController` (rozszerza `RbpModuleFrontController`)
    -   **Odpowiedzialność:** Renderuje główny formularz odstąpienia od umowy online. Obsługuje początkowe wyświetlanie kwalifikujących się zamówień/produktów, przetwarza wybory użytkownika i przygotowuje dane do kroku potwierdzenia. Zarządza dostępem gości za pomocą numeru referencyjnego zamówienia i adresu e-mail.
-   `rbpro/controllers/front/print.php`

    -   **Nazwa klasy:** `RbpPrintModuleFrontController` (rozszerza `RbpModuleFrontController`)
    -   **Odpowiedzialność:** Udostępnia wersję formularza odstąpienia od umowy lub szczegółów wniosku do wydruku. Zazwyczaj używany przez klientów do dołączenia do zwracanej paczki.
-   `rbpro/controllers/front/RbpModuleFrontController.php`

    -   **Nazwa klasy:** `RbpModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Jest to klasa bazowa dla wszystkich kontrolerów front-office w module `rbpro`. Zapewnia wspólne funkcjonalności, takie jak ustawianie ścieżek nawigacyjnych, obsługa zasobów specyficznych dla modułu oraz potencjalnie wspólne kontrole bezpieczeństwa lub inicjalizacja danych.
-   `rbpro/controllers/front/status.php`

    -   **Nazwa klasy:** `RbpStatusModuleFrontController` (rozszerza `RbpModuleFrontController`)
    -   **Odpowiedzialność:** Wyświetla aktualny status i historię konkretnego wniosku o zwrot klientowi. Dostępny za pomocą unikalnego linku śledzącego lub z konta klienta.
-   `rbpro/controllers/front/track.php`

    -   **Nazwa klasy:** `RbpTrackModuleFrontController` (rozszerza `RbpModuleFrontController`)
    -   **Odpowiedzialność:** Zapewnia prosty interfejs dla klientów (zwłaszcza gości) do wprowadzenia numeru referencyjnego zamówienia i adresu e-mail w celu śledzenia statusu ich wniosku o odstąpienie od umowy.

#### Kontrolery administracyjne (back-office)

-   `rbpro/controllers/admin/AdminRbpWithdrawalController.php`
    -   **Nazwa klasy:** `AdminRbpWithdrawalController` (rozszerza `ModuleAdminController`)
    -   **Nazwa zakładki:** „Wnioski o odstąpienie od umowy” (w sekcji „Zamówienia”)
    -   **Zarządzana encja:** `RbpWithdrawal`
    -   **Odpowiedzialność:** Zarządza listowaniem, przeglądaniem, edytowaniem i aktualizowaniem statusów wszystkich wniosków o odstąpienie od umowy klientów w panelu administracyjnym PrestaShop. Implementuje `renderList()` dla tabeli przeglądu i `renderForm()` dla szczegółowego widoku pojedynczego wniosku. Obsługuje działania takie jak zmiana statusu, dodawanie notatek i zarządzanie załącznikami.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `rbpro/classes/index.php`

    -   **Odpowiedzialność:** Standardowy pusty plik `index.php` zapobiegający listowaniu katalogów.
-   `rbpro/classes/RbpCompatibility.php`

    -   **Odpowiedzialność:** Udostępnia statyczne metody do obsługi problemów z kompatybilnością między różnymi wersjami PrestaShop (np. logika specyficzna dla `_PS_VERSION_`, zamienniki przestarzałych funkcji). Zapewnia prawidłowe działanie modułu od PS 1.6 do 9.x.
-   `rbpro/classes/RbpSecurity.php`

    -   **Odpowiedzialność:** Zawiera statyczne metody do zadań związanych z bezpieczeństwem, takich jak walidacja danych wejściowych, sanityzacja i potencjalnie generowanie/weryfikacja tokenów CSRF dla formularzy specyficznych dla modułu.
-   `rbpro/classes/RbpStatsService.php`

    -   **Odpowiedzialność:** Klasa usługowa odpowiedzialna za zbieranie i potencjalne przetwarzanie statystyk związanych z wnioskami o odstąpienie od umowy (np. liczba wniosków, średni czas przetwarzania).
-   `rbpro/classes/RbpWithdrawal.php`

    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `rbp_withdrawal`
    -   **Pola `$definition`:** Definiuje strukturę wniosku o odstąpienie od umowy, w tym pola takie jak `id_customer`, `id_order`, `id_order_state`, `reference`, `email`, `date_add`, `date_upd`, `status`, `reason`, `message` itp.
    -   **Kluczowe metody publiczne:** Metody do operacji CRUD na wnioskach o odstąpienie od umowy, pobierania powiązanych produktów, historii i notatek.
-   `rbpro/classes/RbpWithdrawalAttachment.php`

    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `rbp_withdrawal_attachment`
    -   **Pola `$definition`:** Definiuje strukturę załączników powiązanych z wnioskiem o odstąpienie od umowy, w tym `id_rbp_withdrawal`, `filename`, `original_filename`, `mime_type`, `date_add`.
    -   **Kluczowe metody publiczne:** Metody do zarządzania plikami załączników (przesyłanie, pobieranie, usuwanie).
-   `rbpro/classes/RbpWithdrawalHistory.php`

    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `rbp_withdrawal_history`
    -   **Pola `$definition`:** Definiuje historię zmian statusu dla wniosku o odstąpienie od umowy, w tym `id_rbp_withdrawal`, `id_order_state`, `id_employee`, `message`, `date_add`.
    -   **Kluczowe metody publiczne:** Metody do logowania i pobierania zmian statusu oraz powiązanych wiadomości.
-   `rbpro/classes/RbpWithdrawalNote.php`

    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `rbp_withdrawal_note`
    -   **Pola `$definition`:** Definiuje wewnętrzne notatki dodane przez pracowników do wniosku o odstąpienie od umowy, w tym `id_rbp_withdrawal`, `id_employee`, `note`, `date_add`.
    -   **Kluczowe metody publiczne:** Metody do dodawania i pobierania wewnętrznych notatek.
-   `rbpro/classes/RbpWithdrawalProduct.php`

    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `rbp_withdrawal_product`
    -   **Pola `$definition`:** Definiuje konkretne produkty uwzględnione we wniosku o odstąpienie od umowy, łącząc się z `id_rbp_withdrawal`, `id_order_detail`, `id_product`, `id_product_attribute`, `quantity`, `reason`.
    -   **Kluczowe metody publiczne:** Metody do zarządzania listą produktów w ramach wniosku o zwrot.
-   `rbpro/classes/RbpWithdrawalService.php`

    -   **Odpowiedzialność:** Klasa warstwy usługowej, która orkiestruje złożoną logikę biznesową obejmującą wiele ObjectModels związanych z `RbpWithdrawal`. Przykłady obejmują tworzenie nowego wniosku o odstąpienie od umowy (co obejmuje `RbpWithdrawal`, `RbpWithdrawalProduct`, `RbpWithdrawalHistory`), aktualizowanie jego statusu, wysyłanie powiadomień e-mail i obsługę załączników.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `rbpro/lib/searchTool/views/js/autocomplete.js`

    -   **Zakres:** Panel administracyjny (prawdopodobnie do wyszukiwania zamówień/klientów w formularzach administracyjnych).
    -   **Szczegóły:** Implementuje funkcjonalność autouzupełniania dla pól wprowadzania, zazwyczaj do wyszukiwania klientów lub zamówień podczas ręcznego tworzenia/edycji wniosków o odstąpienie od umowy w panelu administracyjnym. Wiąże się z zdarzeniami `keyup` i wykonuje wywołania AJAX w celu pobrania sugestii.
-   `rbpro/views/js/admin-order-state-picker.js`

    -   **Zakres:** Panel administracyjny (konfiguracja modułu i `AdminRbpWithdrawalController`).
    -   **Szczegóły:** Ulepsza rozwijane listy wyboru statusu zamówienia w konfiguracji modułu i potencjalnie w widoku szczegółów odstąpienia od umowy. Może dodawać wskazówki wizualne lub możliwości filtrowania.
-   `rbpro/views/js/front.js`

    -   **Zakres:** Front-office (formularze odstąpienia od umowy i strony statusu).
    -   **Szczegóły:** Obsługuje interakcje po stronie klienta w formularzu odstąpienia od umowy, takie jak:
        -   Dynamiczny wybór produktu na podstawie zamówienia.
        -   Walidacja pól formularza przed przesłaniem.
        -   Wywołania AJAX do przesyłania formularzy lub ładowania danych.
        -   Wyświetlanie wiadomości lub obsługa przesyłania plików.
-   `rbpro/views/js/order-history.js`

    -   **Zakres:** Front-office (konto klienta > historia zamówień).
    -   **Szczegóły:** Integruje przycisk lub link „Zażądaj zwrotu” na stronie historii zamówień klienta. Może używać AJAX do sprawdzania kwalifikowalności zamówienia lub dynamicznego pokazywania/ukrywania przycisku.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `rbpro/lib/searchTool/views/css/autocomplete.css`

    -   **Zakres:** Panel administracyjny.
    -   **Szczegóły:** Style dla rozwijanych list autouzupełniania i pól wyszukiwania używanych w panelu administracyjnym.
-   `rbpro/views/css/admin-config.css`

    -   **Zakres:** Panel administracyjny (strona konfiguracji modułu).
    -   **Szczegóły:** Style dla głównego formularza konfiguracji modułu, w tym zakładek, pól wprowadzania i ogólnego układu.
-   `rbpro/views/css/admin-dashboard.css`

    -   **Zakres:** Panel administracyjny (potencjalnie dla pulpitu nawigacyjnego modułu lub widoku statystyk).
    -   **Szczegóły:** Style dla wszelkich niestandardowych elementów pulpitu nawigacyjnego lub wyświetlaczy statystycznych w interfejsie administracyjnym modułu.
-   `rbpro/views/css/admin-order-state-picker.css`

    -   **Zakres:** Panel administracyjny.
    -   **Szczegóły:** Specyficzne style dla ulepszonych elementów wyboru statusu zamówienia w panelu administracyjnym.
-   `rbpro/views/css/admin-searchtool.css`

    -   **Zakres:** Panel administracyjny.
    -   **Szczegóły:** Ogólne style dla narzędzi wyszukiwania i komponentów filtrowania w interfejsie administracyjnym.
-   `rbpro/views/css/admin-withdrawal-view.css`

    -   **Zakres:** Panel administracyjny (widok szczegółów `AdminRbpWithdrawalController`).
    -   **Szczegóły:** Style dla szczegółowego widoku pojedynczego wniosku o odstąpienie od umowy, w tym sekcji dla informacji o kliencie, produktach, historii i notatkach.
-   `rbpro/views/css/front-classic.css`

    -   **Zakres:** Front-office (dla kompatybilności z motywem Classic).
    -   **Szczegóły:** Specyficzne dostosowania stylów dla formularza odstąpienia od umowy i przycisków, aby bezproblemowo integrować się z motywem PrestaShop Classic.
-   `rbpro/views/css/front-hummingbird.css`

    -   **Zakres:** Front-office (dla kompatybilności z motywem Hummingbird).
    -   **Szczegóły:** Specyficzne dostosowania stylów dla formularza odstąpienia od umowy i przycisków, aby bezproblemowo integrować się z motywem PrestaShop Hummingbird.
-   `rbpro/views/css/front.css`

    -   **Zakres:** Front-office (ogólne stylizowanie).
    -   **Szczegóły:** Podstawowy CSS dla formularza odstąpienia od umowy, przycisków i stron statusu w front-office, zapewniający podstawowy styl, który może być nadpisany przez arkusze stylów specyficzne dla motywu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

Te szablony są renderowane, gdy moduł jest podłączony do określonych punktów wyświetlania.

-   `rbpro/views/templates/hook/account-link-classic.tpl`

    -   **Hook:** `displayCustomerAccount` (lub podobny)
    -   **Wyjścia:** Link w sekcji „Moje konto” klienta dla motywu Classic, prowadzący do formularza odstąpienia od umowy lub strony śledzenia.
-   `rbpro/views/templates/hook/account-link-hummingbird.tpl`

    -   **Hook:** `displayCustomerAccount` (lub podobny)
    -   **Wyjścia:** Link w sekcji „Moje konto” klienta dla motywu Hummingbird.
-   `rbpro/views/templates/hook/button-classic.tpl`

    -   **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (lub podobny)
    -   **Wyjścia:** Główny przycisk „Zwrot” lub „Odstąpienie od umowy”, stylizowany dla motywu Classic.
-   `rbpro/views/templates/hook/button-hummingbird.tpl`

    -   **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (lub podobny)
    -   **Wyjścia:** Główny przycisk „Zwrot” lub „Odstąpienie od umowy”, stylizowany dla motywu Hummingbird.
-   `rbpro/views/templates/hook/button.tpl`

    -   **Hook:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductButtons` (lub podobny)
    -   **Wyjścia:** Ogólny przycisk „Zwrot” lub „Odstąpienie od umowy”, używany jako rezerwowy lub bazowy dla przycisków specyficznych dla motywu.
-   `rbpro/views/templates/hook/order-detail-classic.tpl`

    -   **Hook:** `displayOrderDetail` (lub podobny)
    -   **Wyjścia:** Opcja lub przycisk na stronie szczegółów indywidualnego zamówienia klienta dla motywu Classic, umożliwiający zainicjowanie zwrotu dla tego konkretnego zamówienia.
-   `rbpro/views/templates/hook/order-detail-hummingbird.tpl`

    -   **Hook:** `displayOrderDetail` (lub podobny)
    -   **Wyjścia:** Opcja lub przycisk na stronie szczegółów indywidualnego zamówienia klienta dla motywu Hummingbird.
-   `rbpro/views/templates/hook/order-detail.tpl`

    -   **Hook:** `displayOrderDetail` (lub podobny)
    -   **Wyjścia:** Ogólna opcja lub przycisk na stronie szczegółów indywidualnego zamówienia klienta.
-   `rbpro/views/templates/hook/order-withdrawal-notice.tpl`

    -   **Hook:** `displayAdminOrder` (lub podobny)
    -   **Wyjścia:** Powiadomienie lub podsumowanie wniosków o odstąpienie od umowy związanych z konkretnym zamówieniem, wyświetlane w widoku zamówienia w panelu administracyjnym PrestaShop.

#### Szablony administracyjne (`views/templates/admin/`)

Te szablony są używane dla interfejsu panelu administracyjnego modułu.

-   `rbpro/lib/searchTool/views/scripts.tpl`

    -   **Wyjścia:** Dołączenia JavaScript i CSS dla biblioteki narzędzia wyszukiwania, zazwyczaj dołączane do formularzy administracyjnych, które używają autouzupełniania.
-   `rbpro/views/templates/admin/configure.tpl`

    -   **Wyjścia:** Główny formularz konfiguracji modułu, renderowany przez `getContent()` w `index.php`. Zawiera wszystkie ustawienia opisane w sekcji 4.1.
-   `rbpro/views/templates/admin/dashboard.tpl`

    -   **Wyjścia:** Pulpit nawigacyjny lub widok podsumowania dla modułu, potencjalnie pokazujący statystyki lub ostatnie wnioski o odstąpienie od umowy.
-   `rbpro/views/templates/admin/order-state-picker.tpl`

    -   **Wyjścia:** Niestandardowy szablon do wyboru statusów zamówień, używany w konfiguracji modułu lub widoku administracyjnym odstąpienia od umowy.
-   `rbpro/views/templates/admin/order-withdrawal-notice.tpl`

    -   **Wyjścia:** Mały widżet lub powiadomienie wyświetlane na stronie szczegółów zamówienia PrestaShop w panelu administracyjnym, wskazujące, czy istnieje aktywny wniosek o odstąpienie od umowy dla tego zamówienia.
-   `rbpro/views/templates/admin/updates.tpl`

    -   **Wyjścia:** Szablon do wyświetlania powiadomień o aktualizacjach modułu lub dzienników zmian w interfejsie administracyjnym.
-   `rbpro/views/templates/admin/view.tpl`

    -   **Wyjścia:** Szczegółowy szablon widoku dla pojedynczego wniosku o odstąpienie od umowy, renderowany przez `AdminRbpWithdrawalController::renderForm()`. Pokazuje wszystkie szczegóły wniosku, produkty, historię, notatki i opcje zmiany statusu.

#### Szablony front-office (`views/templates/front/`)

Są to samodzielne szablony stron dla procesu odstąpienia od umowy skierowanego do klienta.

-   `rbpro/views/templates/front/confirm_step.tpl`

    -   **Wyjścia:** Krok potwierdzenia formularza odstąpienia od umowy, podsumowujący wybory klienta przed ostatecznym przesłaniem.
-   `rbpro/views/templates/front/error.tpl`

    -   **Wyjścia:** Ogólna strona błędu wyświetlana, jeśli coś pójdzie nie tak podczas procesu odstąpienia od umowy (np. nieprawidłowe zamówienie, problem techniczny).
-   `rbpro/views/templates/front/form.tpl`

    -   **Wyjścia:** Główny formularz wniosku o odstąpienie od umowy online, umożliwiający klientom wybór zamówień, produktów i podanie szczegółów.
-   `rbpro/views/templates/front/print.tpl`

    -   **Wyjścia:** Wersja wniosku o odstąpienie od umowy do wydruku, zazwyczaj uproszczony układ bez nawigacji.
-   `rbpro/views/templates/front/status.tpl`

    -   **Wyjścia:** Strona wyświetlająca aktualny status i historię konkretnego wniosku o odstąpienie od umowy.
-   `rbpro/views/templates/front/success.tpl`

    -   **Wyjścia:** Strona z komunikatem o sukcesie wyświetlana po pomyślnym złożeniu wniosku o odstąpienie od umowy.
-   `rbpro/views/templates/front/track.tpl`

    -   **Wyjścia:** Formularz, w którym klienci mogą wprowadzić numer referencyjny zamówienia i adres e-mail, aby śledzić wniosek o odstąpienie od umowy.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł tworzy i zarządza kilkoma niestandardowymi tabelami:

-   `ps_rbp_withdrawal`: Przechowuje główne szczegóły wniosku o odstąpienie od umowy (klient, zamówienie, status, powód itp.).
-   `ps_rbp_withdrawal_attachment`: Przechowuje szczegóły dotyczące plików przesłanych przez klientów dla wniosku o odstąpienie od umowy.
-   `ps_rbp_withdrawal_history`: Rejestruje wszystkie zmiany statusu i powiązane wiadomości dla każdego wniosku o odstąpienie od umowy.
-   `ps_rbp_withdrawal_note`: Przechowuje wewnętrzne notatki dodane przez pracowników do wniosku o odstąpienie od umowy.
-   `ps_rbp_withdrawal_product`: Łączy konkretne produkty z zamówienia z wnioskiem o odstąpienie od umowy, w tym ilość i powód.

Rekordy konfiguracji są przechowywane w `ps_configuration` z kluczami zazwyczaj poprzedzonymi prefiksem `RBP_` (np. `RBP_ALLOW_GUEST_WITHDRAWAL`, `RBP_MIN_ORDER_STATUS`).

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykiwanie CSS/JS, wyświetlanie przycisku zwrotu (jeśli skonfigurowano). |
| `displayFooter` | W stopce każdej strony. | Wyświetlanie przycisku zwrotu (jeśli skonfigurowano). |
| `displayLeftColumn` | W lewej kolumnie stron. | Wyświetlanie przycisku zwrotu (jeśli skonfigurowano). |
| `displayRightColumn` | W prawej kolumnie stron. | Wyświetlanie przycisku zwrotu (jeśli skonfigurowano). |
| `displayProductButtons` | Na stronie produktu, w pobliżu przycisku dodaj do koszyka. | Wyświetlanie przycisku zwrotu (jeśli skonfigurowano). |
| `displayCustomerAccount` | Na stronie „Moje konto” klienta. | Dodanie linku do formularza odstąpienia od umowy/śledzenia. |
| `displayOrderDetail` | Na stronie szczegółów indywidualnego zamówienia klienta. | Dodanie opcji żądania zwrotu dla tego zamówienia. |
| `displayAdminOrder` | W panelu administracyjnym PrestaShop, na stronie szczegółów zamówienia. | Wyświetlanie powiadomienia lub podsumowania powiązanych wniosków o odstąpienie od umowy. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Potencjalne logowanie szczegółów zamówienia do przyszłych kontroli kwalifikowalności do odstąpienia od umowy. |
| `actionOrderStatusUpdate` | Po zmianie statusu zamówienia. | Sprawdzenie, czy status zamówienia wpływa na kwalifikowalność do odstąpienia od umowy lub wywołanie powiadomień. |
| `actionFrontControllerSetMedia` | Przed renderowaniem zawartości przez kontroler front-office. | Ładowanie zasobów CSS i JavaScript specyficznych dla front-office. |
| `actionAdminControllerSetMedia` | Przed renderowaniem zawartości przez kontroler administracyjny. | Ładowanie zasobów CSS i JavaScript specyficznych dla panelu administracyjnego. |
| `actionModuleInstall` | Podczas instalacji modułu. | Tworzenie tabel bazy danych, ustawianie domyślnych wartości konfiguracyjnych. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Usuwanie tabel bazy danych, czyszczenie wartości konfiguracyjnych. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkich pytań dotyczących modułu „Przycisk zwrotu UE – Formularz odstąpienia od umowy online”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia i programiści są dostępni, aby pomóc w przypadku wszelkich problemów lub zapytań.
