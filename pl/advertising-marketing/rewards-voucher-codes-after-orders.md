---
title: "Nagrody - Kody kuponów po zamówieniach - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Nagrody - Kody kuponów po zamówieniach” od MyPresta.eu."
sidebar:
  label: "Nagrody - Kody kuponów po zamówieniach - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Rewards - Voucher codes after orders na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/rewards-voucher-codes-after-orders.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/rewards-voucher-codes-after-orders/)
>
> ---


# Nagrody - Kody kuponów po zamówieniach

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do prawidłowego funkcjonowania sklepu PrestaShop. Ten moduł nie ma żadnych nietypowych ani dodatkowych wymagań hostingowych poza standardową konfiguracją PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Nagrody - Kody kuponów po zamówieniach)

To jest główny ekran konfiguracji, na którym definiujesz zasady generowania i wysyłania kodów kuponów.

#### Ustawienia ogólne

-   **Włącz moduł:**

    *   **Co robi to ustawienie:** To jest główny przełącznik modułu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączony:* Moduł będzie aktywnie monitorować zamówienia i generować/wysyłać kupony zgodnie z Twoimi zasadami.
        *   *Gdy wyłączony:* Moduł będzie nieaktywny, a żadne kupony nie będą generowane ani wysyłane, niezależnie od innych ustawień.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Zakończyłeś konfigurację wszystkich swoich zasad i jesteś gotowy do uruchomienia programu nagród. Włącz to, aby rozpocząć wysyłanie kuponów. Jeśli musisz tymczasowo wstrzymać program w celu konserwacji, wyłącz go.
-   **Statusy zamówień do generowania kuponów:**

    *   **Co robi to ustawienie:** Określa, które statusy zamówień wyzwolą proces generowania kuponów. Tylko zamówienia, które osiągną jeden z wybranych statusów, będą kwalifikować się do nagrody.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy wybrane:* Zamówienia z tymi statusami zostaną sprawdzone pod kątem kwalifikowalności do kuponu.
        *   *Gdy niewybrane:* Zamówienia z tymi statusami zostaną zignorowane przez moduł.
    *   **Zalecana wartość:** Zazwyczaj „Płatność zaakceptowana” i „Dostarczono”. Możesz również uwzględnić „Wysłane”, jeśli chcesz wysłać kupon wcześniej.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz mieć pewność, że klienci otrzymają kupon dopiero po potwierdzeniu płatności i przetworzeniu lub dostarczeniu zamówienia. Wybierz „Płatność zaakceptowana” i „Dostarczono”, aby zapobiec wysyłaniu kuponów dla anulowanych lub oczekujących zamówień.
-   **Minimalna wartość zamówienia dla kuponu:**

    *   **Co robi to ustawienie:** Ustawia minimalną całkowitą wartość (bez kosztów wysyłki), którą zamówienie musi spełnić, aby kwalifikować się do kuponu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawione na wartość (np. 50):* Tylko zamówienia o wartości całkowitej większej lub równej 50 wyzwolą kupon.
        *   *Gdy ustawione na 0 (lub puste):* Wszystkie zamówienia, niezależnie od wartości, będą kwalifikować się (jeśli spełnione są inne warunki).
    *   **Zalecana wartość:** Wartość, która ma sens biznesowy dla Twojej średniej wartości zamówienia, lub 0, jeśli chcesz nagradzać wszystkie zamówienia.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz zachęcić do większych zakupów. Ustaw to na 50 €, aby tylko klienci wydający 50 € lub więcej otrzymywali rabat, czyniąc kupon nagrodą za transakcje o wyższej wartości.

#### Ustawienia kodu kuponu

-   **Prefiks kodu kuponu:**

    *   **Co robi to ustawienie:** Ciąg znaków, który pojawi się na początku każdego wygenerowanego kodu kuponu. Pomaga to zidentyfikować kupony z tego modułu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawiony (np. „REWARD”):* Kody będą wyglądać jak „REWARDABCD123”.
        *   *Gdy pusty:* Kody będą czysto losowymi znakami.
    *   **Zalecana wartość:** Krótki, opisowy prefiks, taki jak „REWARD”, „THANKYOU” lub inicjały Twojego sklepu.
    *   **Scenariusz / przykład dla sprzedawcy:** Prowadzisz wiele promocji. Użycie „REWARD” jako prefiksu pomaga szybko zidentyfikować, które kupony pochodzą z tego modułu w Twoich zasadach rabatowych PrestaShop.
-   **Długość kodu kuponu:**

    *   **Co robi to ustawienie:** Definiuje całkowitą liczbę znaków w wygenerowanym kodzie kuponu (w tym prefiks).
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawione na 10 z prefiksem „REWARD”:* Losowa część będzie miała 4 znaki (10 - 6 dla „REWARD”).
        *   *Gdy ustawione na niższą liczbę:* Krótsze kody, potencjalnie łatwiejsze do wpisania, ale mniej unikalne.
        *   *Gdy ustawione na wyższą liczbę:* Dłuższe kody, bezpieczniejsze, ale trudniejsze do wpisania.
    *   **Zalecana wartość:** 8-12 znaków (w tym prefiks) dla dobrej równowagi bezpieczeństwa i użyteczności.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby kody były łatwe do zapamiętania, ale nadal unikalne. Długość 10-12 znaków jest zazwyczaj wystarczająca.
-   **Typ wartości kuponu:**

    *   **Co robi to ustawienie:** Określa, czy kupon oferuje rabat procentowy, czy stałą kwotę.
    *   **Efekt zmiany tego ustawienia:**
        *   *Procentowy:* Kupon odliczy procent od całkowitej wartości zamówienia.
        *   *Stała kwota:* Kupon odliczy określoną wartość pieniężną.
    *   **Zalecana wartość:** Zależy od Twojej strategii marketingowej. Procentowy jest dobry do zachęcania do większych zamówień, stała kwota jest prostsza i jaśniejsza.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz dać 10% zniżki na następne zamówienie, więc wybierasz „Procentowy”. Jeśli chcesz dać stałą zniżkę 5 €, wybierz „Stała kwota”.
-   **Wartość kuponu:**

    *   **Co robi to ustawienie:** Rzeczywista wartość rabatu. Będzie to procent (np. 10) lub stała kwota (np. 5.00) w zależności od ustawienia „Typ wartości kuponu”.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawione na 10 i „Procentowy”:* Klienci otrzymują 10% zniżki.
        *   *Gdy ustawione na 5.00 i „Stała kwota”:* Klienci otrzymują 5 € zniżki.
    *   **Zalecana wartość:** Wartość, która sprawia, że oferta jest atrakcyjna, ale jest zrównoważona dla Twojej firmy.
    *   **Scenariusz / przykład dla sprzedawcy:** Decydujesz się zaoferować 15% zniżki, więc wpisujesz „15” tutaj po wybraniu „Procentowy” powyżej.
-   **Minimalna wartość zamówienia do użycia kuponu:**

    *   **Co robi to ustawienie:** Ustawia minimalną kwotę zakupu wymaganą, aby klient mógł użyć wygenerowanego kodu kuponu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawione na 20:* Klient musi wydać co najmniej 20 € na następne zamówienie, aby zastosować kupon.
        *   *Gdy ustawione na 0 (lub puste):* Kupon może być użyty na dowolne zamówienie, niezależnie od jego wartości.
    *   **Zalecana wartość:** Wartość nieco wyższa niż Twoja średnia wartość zamówienia, aby zachęcić do sprzedaży dodatkowej, lub 0, jeśli chcesz maksymalnej użyteczności.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz mieć pewność, że kupon zachęca do nowego zakupu, a nie tylko małego dodatku. Ustaw to na 25 €, aby klient musiał kupić coś znaczącego, aby użyć swojego kuponu o wartości 5 €.
-   **Ważność kuponu (dni):**

    *   **Co robi to ustawienie:** Definiuje, ile dni wygenerowany kod kuponu będzie ważny od daty jego utworzenia.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawione na 30:* Kupon wygaśnie 30 dni po wysłaniu.
        *   *Gdy ustawione na 0 (lub puste):* Kupon będzie ważny bezterminowo (niezalecane, ponieważ usuwa poczucie pilności).
    *   **Zalecana wartość:** 30-90 dni, aby stworzyć poczucie pilności, nie będąc zbyt restrykcyjnym.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby klienci wykorzystali swój kupon w rozsądnym czasie. Ustaw to na 60 dni, aby dać im dwa miesiące na dokonanie kolejnego zakupu.
-   **Zastosuj kupon do określonych grup klientów:**

    *   **Co robi to ustawienie:** Pozwala ograniczyć użycie wygenerowanego kuponu do określonych grup klientów (np. „Klienci VIP”, „Hurtownicy”).
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy wybrane:* Tylko klienci należący do wybranych grup mogą użyć kuponu.
        *   *Gdy niewybrane (lub wszystkie grupy wybrane):* Każdy klient może użyć kuponu.
    *   **Zalecana wartość:** Pozostaw wszystkie wybrane, chyba że masz konkretną strategię segmentacji.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz zaoferować specjalny rabat tylko grupie „Zarejestrowani klienci”. Wybierz tylko tę grupę tutaj.
-   **Zastosuj kupon do określonych produktów/kategorii:**

    *   **Co robi to ustawienie:** Pozwala ograniczyć zastosowanie kuponu do niektórych produktów lub kategorii produktów.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy wybrane:* Kupon będzie dotyczył tylko pozycji z wybranych produktów/kategorii.
        *   *Gdy niewybrane (lub żadne nie wybrane):* Kupon dotyczy wszystkich produktów w koszyku.
    *   **Zalecana wartość:** Pozostaw niewybrane dla ogólnych rabatów w całym sklepie. Użyj tego do ukierunkowanych promocji.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz promować konkretną nową kolekcję. Możesz skonfigurować kupon tak, aby dotyczył tylko produktów z tej kategorii.
-   **Wyklucz produkty objęte rabatem:**

    *   **Co robi to ustawienie:** Jeśli włączone, kupon nie może być użyty na produktach, które są już w promocji lub mają specjalną cenę.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Zapobiega „nakładaniu się” rabatów, zapewniając, że klienci nie otrzymają podwójnych rabatów.
        *   *Gdy wyłączone:* Kupony mogą być stosowane do już przecenionych produktów.
    *   **Zalecana wartość:** TAK, aby chronić Twoje marże zysku.
    *   **Scenariusz / przykład dla sprzedawcy:** Prowadzisz ogólnosklepową wyprzedaż 20%. Nie chcesz, aby klienci używali swojego kuponu nagrody dodatkowo, dając im efektywnie 30% zniżki. Włącz to, aby temu zapobiec.
-   **Wyklucz wysyłkę:**

    *   **Co robi to ustawienie:** Określa, czy rabat kuponu dotyczy kosztów wysyłki zamówienia.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Kupon zmniejsza tylko całkowitą wartość produktów, a nie opłatę za wysyłkę.
        *   *Gdy wyłączone:* Kupon może zmniejszyć całkowitą wartość zamówienia, w tym wysyłkę.
    *   **Zalecana wartość:** TAK, ponieważ koszty wysyłki są często stałe i nie stanowią części Twojej marży produktowej.
    *   **Scenariusz / przykład dla sprzedawcy:** Oferujesz darmową wysyłkę powyżej określonego progu. Chcesz, aby kupon wpływał tylko na ceny produktów, a nie na koszt wysyłki. Włącz to.
-   **Kupon na N-te zamówienie:**

    *   **Co robi to ustawienie:** Jest to potężna funkcja, która pozwala określić, dla którego numeru zamówienia (1., 2., 3. itd.) klient otrzymuje kupon.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawione na 1:* Tylko pierwsze zamówienie klienta wyzwoli kupon.
        *   *Gdy ustawione na 2:* Tylko drugie zamówienie wyzwoli kupon.
        *   *Gdy ustawione na 0 (lub puste):* Każde kwalifikujące się zamówienie wyzwoli kupon (jeśli spełnione są inne warunki).
    *   **Zalecana wartość:** 1 dla oferty „witamy ponownie” lub 0 dla ogólnego programu lojalnościowego. Możesz również utworzyć wiele zasad (patrz sekcja 4.2) dla różnych N-tych zamówień.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz podziękować klientom kupującym po raz pierwszy. Ustaw to na „1”. Dla ogólnego programu lojalnościowego pozostaw na „0” lub utwórz konkretne zasady dla 2., 3. itd. zamówień.

#### Ustawienia szablonu e-mail

-   **Temat e-maila:**

    *   **Co robi to ustawienie:** Temat e-maila, który klienci otrzymują, zawierający ich kod kuponu.
    *   **Efekt zmiany tego ustawienia:** To jest to, co klienci widzą w swojej skrzynce odbiorczej. Przekonujący temat zwiększa wskaźniki otwarć.
    *   **Zalecana wartość:** Coś angażującego, np. „Twój specjalny rabat na następne zamówienie!” lub „Dziękujemy! Oto prezent od nas.”
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz jasno określić, że to nagroda. Ustaw temat na „Twój ekskluzywny kupon od [Nazwa Twojego sklepu]!”
-   **Treść e-maila:**

    *   **Co robi to ustawienie:** Główna treść e-maila. Możesz użyć symboli zastępczych, takich jak `{customer_name}`, `{voucher_code}`, `{voucher_value}`, `{min_order_total}`, `{validity_days}`, aby spersonalizować wiadomość.
    *   **Efekt zmiany tego ustawienia:** To tutaj komunikujesz wartość kuponu i sposób jego użycia. Jasna, przyjazna wiadomość zachęca do użycia.
    *   **Zalecana wartość:** Powitalna wiadomość, jasne instrukcje i wszystkie istotne szczegóły kuponu.
    *   **Scenariusz / przykład dla sprzedawcy:** „Drogi {customer\_name}, dziękujemy za ostatni zakup! W dowód naszego uznania, oto kod rabatowy {voucher\_value} na Twoje następne zamówienie: **{voucher\_code}**. Ten kupon jest ważny przez {validity\_days} dni i może być użyty na zamówienia powyżej {min\_order\_total}. Udanych zakupów!”
-   **Wyślij e-mail do klienta:**

    *   **Co robi to ustawienie:** Kontroluje, czy e-mail zawierający kupon jest faktycznie wysyłany do klienta.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci otrzymują e-mail.
        *   *Gdy wyłączone:* Kupony są nadal generowane (jeśli włączone), ale klienci nie otrzymują powiadomienia e-mail. Wtedy musiałbyś przekazać kod kuponu innym kanałem.
    *   **Zalecana wartość:** TAK, ponieważ e-mail jest główną metodą dostarczania dla tego modułu.
    *   **Scenariusz / przykład dla sprzedawcy:** Skonfigurowałeś wszystko i chcesz, aby klienci otrzymywali swoje nagrody. Włącz to. Jeśli testujesz lub wolisz ręcznie wysyłać kody, możesz tymczasowo to wyłączyć.

#### Ustawienia zadania Cron

-   **URL zadania Cron:**
    *   **Co robi to ustawienie:** Jest to unikalny URL, który po wywołaniu powoduje, że moduł sprawdza nowe kwalifikujące się zamówienia i generuje/wysyła kupony.
    *   **Efekt zmiany tego ustawienia:** Ten URL jest kluczowy dla automatyzacji modułu. Musi być regularnie wywoływany.
    *   **Zalecana wartość:** NIE zmieniaj tego URL-a. Skopiuj go i skonfiguruj w panelu sterowania swojego hostingu.
    *   **Scenariusz / przykład dla sprzedawcy:** Kopiujesz ten URL i wklejasz go do menedżera zadań cron swojego dostawcy hostingu (np. cPanel, Plesk), aby uruchamiał się co 15-30 minut. Zapewnia to szybkie wysyłanie kuponów po przetworzeniu zamówień.

### 2.2 Dedykowany ekran administracyjny: Lista nagród (Panel administracyjny > Nagrody > Lista nagród)

Ten ekran zapewnia kompleksowy przegląd wszystkich kodów kuponów, które zostały wygenerowane przez moduł. Działa jako dziennik i interfejs zarządzania Twoim programem nagród.

-   **Nazwa ekranu i lokalizacja w menu:** **Lista nagród** (znajduje się w nowej pozycji menu „Nagrody” w Twoim Panelu administracyjnym PrestaShop, lub potencjalnie w „Katalog” lub „Marketing” w zależności od Twojej wersji PrestaShop i motywu).
-   **Dostępne akcje i ustawienia:**
    *   **Kolumny tabeli:** Zobaczysz tabelę z następującymi kolumnami:
        *   **ID:** Unikalny identyfikator wpisu nagrody.
        *   **ID zamówienia:** ID zamówienia PrestaShop, które wyzwoliło tę nagrodę.
        *   **Klient:** Imię i nazwisko klienta, który otrzymał kupon.
        *   **E-mail:** Adres e-mail klienta.
        *   **Numer referencyjny zamówienia:** Unikalny numer referencyjny zamówienia.
        *   **Kod nagrody:** Rzeczywisty kod kuponu wygenerowany i wysłany do klienta.
        *   **Data generacji:** Data i godzina wygenerowania kuponu.
    *   **Filtrowanie i wyszukiwanie:** Zazwyczaj możesz filtrować lub wyszukiwać według dowolnej z tych kolumn (np. wyszukać konkretny adres e-mail klienta, ID zamówienia lub kod kuponu), aby znaleźć konkretne wpisy nagród.
    *   **Brak przycisków „Dodaj/Edytuj”:** Ten ekran służy głównie do przeglądania wygenerowanych nagród. Kupony są tworzone automatycznie na podstawie Twojej konfiguracji, a nie dodawane ręcznie tutaj.
-   **Efekt zmian:** Ten ekran jest dziennikiem tylko do odczytu. Zmiany w konfiguracji modułu (Sekcja 4.1) wpłyną na *przyszłe* generowanie kuponów, ale istniejące wpisy tutaj odzwierciedlają przeszłe zdarzenia.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    *   Okresowo sprawdzaj tę listę, aby monitorować aktywność swojego programu nagród.
    *   Jeśli klient twierdzi, że nie otrzymał kuponu, możesz szybko wyszukać jego zamówienie tutaj, znaleźć „Kod nagrody” i potwierdzić datę jego generacji. W razie potrzeby możesz ręcznie przekazać kod klientowi.
    *   Użyj opcji filtrowania, aby analizować, które zamówienia wyzwalają nagrody, lub rozwiązywać konkretne zapytania klientów.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz moduł | TAK | Główny przełącznik funkcjonalności modułu. |
| | Statusy zamówień do generowania kuponów | Płatność zaakceptowana, Dostarczono | Definiuje, które statusy zamówień wyzwalają generowanie kuponów. |
| | Minimalna wartość zamówienia dla kuponu | 0 (lub Twoja pożądana wartość) | Minimalna wartość zamówienia, aby zamówienie kwalifikowało się do kuponu. |
| | Prefiks kodu kuponu | REWARD (lub Twój wybór) | Prefiks dla generowanych kodów kuponów. |
| | Długość kodu kuponu | 8-12 | Całkowita długość kodu kuponu. |
| | Typ wartości kuponu | Procentowy / Stała kwota | Wybierz między rabatem procentowym a stałą kwotą. |
| | Wartość kuponu | Twoja pożądana wartość (np. 10 lub 5.00) | Rzeczywista wartość rabatu kuponu. |
| | Minimalna wartość zamówienia do użycia kuponu | 0 (lub Twoja pożądana wartość) | Minimalna wartość zamówienia wymagana do *użycia* kuponu. |
| | Ważność kuponu (dni) | 30-90 | Ile dni kupon jest ważny po wygenerowaniu. |
| | Zastosuj kupon do określonych grup klientów | Wszystkie wybrane | Ogranicza użycie kuponu do wybranych grup klientów. |
| | Zastosuj kupon do określonych produktów/kategorii | Żadne nie wybrane | Ogranicza użycie kuponu do wybranych produktów/kategorii. |
| | Wyklucz produkty objęte rabatem | TAK | Zapobiega stosowaniu kuponów do już przecenionych produktów. |
| | Wyklucz wysyłkę | TAK | Zapobiega zmniejszaniu kosztów wysyłki przez kupony. |
| | Kupon na N-te zamówienie | 0 (lub 1 dla pierwszego zamówienia) | Określa, dla którego numeru zamówienia (1., 2. itd.) generowany jest kupon. |
| | Temat e-maila | Twój specjalny rabat! | Temat e-maila zawierającego kupon. |
| | Treść e-maila | Spersonalizowana wiadomość z symbolami zastępczymi | Treść e-maila, w tym szczegóły kuponu. |
| | Wyślij e-mail do klienta | TAK | Kontroluje, czy e-mail z kuponem jest wysyłany do klienta. |
| | URL zadania Cron | NIE zmieniaj | Niezbędny URL do automatycznego generowania kuponów. |
| **Lista nagród** | ID, ID zamówienia, Klient, E-mail, Numer referencyjny zamówienia, Kod nagrody, Data generacji | N/A (tylko do odczytu) | Wyświetla dziennik wszystkich wygenerowanych kuponów do monitorowania i rozwiązywania problemów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moi klienci nie otrzymują e-maili z kuponami. Co powinienem sprawdzić?**
O:

1.  **Moduł włączony?** Sprawdź dwukrotnie, czy „Włącz moduł” jest ustawione na TAK w konfiguracji modułu.
2.  **Statusy zamówień:** Upewnij się, że status zamówienia odpowiada jednemu z wybranych przez Ciebie „Statusów zamówień do generowania kuponów”.
3.  **Zadanie Cron:** Zweryfikuj, czy Twoje zadanie cron jest poprawnie skonfigurowane i regularnie działa na Twoim hostingu. „URL zadania Cron” musi być wywoływany, aby moduł przetwarzał zamówienia.
4.  **Wysyłanie e-maili włączone:** Upewnij się, że „Wyślij e-mail do klienta” jest ustawione na TAK.
5.  **Folder spamu:** Poproś klientów o sprawdzenie folderów spamu lub śmieci.
6.  **Ustawienia e-mail PrestaShop:** Sprawdź główną konfigurację e-mail PrestaShop (Zaawansowane > E-mail), aby upewnić się, że e-maile są pomyślnie wysyłane z Twojego sklepu.

**P: Kupony są generowane, ale wydaje się, że nie działają dla klientów.**
O:

1.  **Ważność kuponu:** Sprawdź ustawienie „Ważność kuponu (dni)”. Czy kupon wygasł?
2.  **Minimalna wartość zamówienia do użycia:** Czy aktualny koszyk klienta spełnia „Minimalną wartość zamówienia do użycia kuponu”?
3.  **Grupy klientów:** Czy klient należy do wybranych „Zastosuj kupon do określonych grup klientów”?
4.  **Ograniczenia produktów/kategorii:** Czy produkty w koszyku klienta kwalifikują się na podstawie „Zastosuj kupon do określonych produktów/kategorii”?
5.  **Wykluczone produkty objęte rabatem:** Czy klient próbuje użyć kuponu na już przecenionym produkcie, a „Wyklucz produkty objęte rabatem” jest włączone?
6.  **Błędy typograficzne:** Poproś klienta o dwukrotne sprawdzenie kodu kuponu pod kątem błędów typograficznych.

**P: Chcę oferować różne kupony na różne numery zamówień (np. 1., 2., 5. zamówienie). Jak to zrobić?**
O: Opis modułu wskazuje na obsługę „wielu rodzajów akcji, takich jak: kupon na pierwsze zamówienie, kupon na drugie zamówienie, piąte, szóste itd.”. Oznacza to, że moduł ma mechanizm do definiowania wielu zasad opartych na N-tym zamówieniu.

-   **Sprawdź, czy są dostępne zakładki z wieloma zasadami:** Poszukaj dodatkowych zakładek lub sekcji w konfiguracji modułu, które pozwalają „Dodać nową zasadę” lub zdefiniować oddzielne konfiguracje dla różnych wartości „N-tego zamówienia”. Jeśli taki interfejs istnieje, utworzyłbyś oddzielną zasadę dla każdego N-tego zamówienia z jego specyficznymi ustawieniami kuponu.
-   **Jeśli istnieje tylko jedno pole „Kupon na N-te zamówienie”:** Jeśli moduł przedstawia tylko jedno pole „Kupon na N-te zamówienie” na głównej stronie konfiguracji, oznacza to, że możesz ustawić *tylko jedną* taką zasadę naraz. Aby wdrożyć system poziomowy, musiałbyś ręcznie zmieniać to ustawienie po pewnym czasie lub rozważyć, czy aktualna wersja modułu obsługuje tę zaawansowaną funkcjonalność poprzez mniej oczywisty interfejs. Dla większości użytkowników ustawienie go na `0` (każde zamówienie) lub `1` (tylko pierwsze zamówienie) jest głównym przypadkiem użycia.

**P: Moduł spowalnia mój Panel administracyjny / Front Office.**
O: Ten moduł działa głównie w tle za pośrednictwem zadania cron i ma minimalny wpływ na wydajność Front Office. Jeśli zauważysz spowolnienia:

1.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i wyczyść pamięć podręczną PrestaShop.
2.  **Sprawdź zasoby serwera:** Monitoruj użycie procesora i pamięci serwera, zwłaszcza gdy działa zadanie cron. Jeśli Twój serwer jest niedostatecznie wydajny, nawet proste zadania mogą powodować spowolnienia.
3.  **Inne moduły:** Tymczasowo wyłącz inne ostatnio zainstalowane moduły, aby sprawdzić, czy nie ma konfliktu.

**P: Czy mogę dalej dostosować szablon e-maila?**
O: Tak, moduł udostępnia pola „Temat e-maila” i „Treść e-maila” z symbolami zastępczymi do podstawowej personalizacji. W przypadku zaawansowanych zmian projektowych (np. dodawanie logo sklepu, zmiana czcionek/kolorów) zazwyczaj trzeba by bezpośrednio modyfikować pliki szablonów e-mail modułu. Zazwyczaj wymaga to webmastera lub programisty. Wewnętrzna struktura modułu sugeruje, że używa on `lib/emailTemplatesManager`, co może oferować bardziej zaawansowane zarządzanie szablonami w samym module, ale podstawowa konfiguracja odbywa się za pomocą pól tekstowych.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Nagrody - Kody kuponów po zamówieniach” stosuje standardową architekturę modułu PrestaShop, wykorzystując zasady MVC tam, gdzie ma to zastosowanie. Jego podstawowa funkcjonalność opiera się na mechanizmie zadania cron, który okresowo sprawdza kwalifikujące się zamówienia, a po ich znalezieniu generuje obiekty `CartRule` (kupony) PrestaShop i wysyła e-maile. Moduł rozszerza `Module` dla swojej głównej funkcjonalności i używa `AdminController` dla swojego interfejsu zarządzania w Panelu administracyjnym. Zawiera również kilka bibliotek narzędziowych do zarządzania szablonami e-mail i funkcjonalności wyszukiwania.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front Office

-   `controllers/front/cronJob.php`
    *   **Nazwa klasy:** `OrdercouponsCronJobModuleFrontController` (prawdopodobnie, na podstawie nazwy pliku)
    *   **Klasa nadrzędna:** `ModuleFrontController`
    *   **Odpowiedzialność:** Ten kontroler jest zaprojektowany do dostępu za pośrednictwem URL-a zadania Cron podanego w konfiguracji modułu. Po wywołaniu, wyzwala główną logikę w pliku modułu `cronjob.php` do przetwarzania zamówień, generowania kuponów i wysyłania e-maili. Zazwyczaj nie renderuje żadnej zawartości Front Office, ale wykonuje zadania w tle.
-   `controllers/front/index.php`
    *   **Nazwa klasy:** `OrdercouponsIndexModuleFrontController` (prawdopodobnie)
    *   **Klasa nadrzędna:** `ModuleFrontController`
    *   **Odpowiedzialność:** Jest to często symbol zastępczy lub prosty kontroler przekierowujący. W wielu modułach `index.php` w katalogu kontrolerów po prostu zapewnia, że bezpośredni dostęp do katalogu nie skutkuje listą katalogów, lub może zawierać minimalną logikę dla domyślnego widoku Front Office, jeśli moduł taki posiadał. Dla tego modułu jest mało prawdopodobne, aby miał znaczącą odpowiedzialność za renderowanie Front Office.

#### Kontrolery administracyjne Back Office

-   `controllers/admin/AdminOrderCouponsRewards.php`
    *   **Nazwa klasy:** `AdminOrderCouponsRewardsController`
    *   **Klasa nadrzędna:** `ModuleAdminController` (lub `AdminController` w starszych wersjach)
    *   **Nazwa zakładki:** „Lista nagród” (pod pozycją menu „Nagrody”)
    *   **Zarządzana encja:** `orewards_list` (prawdopodobnie niestandardowa tabela bazy danych do logowania wygenerowanych nagród).
    *   **Odpowiedzialność:** Ten kontroler zarządza „Listą nagród” w Panelu administracyjnym PrestaShop. Wyświetla listę wszystkich wygenerowanych kodów kuponów, powiązanych ID zamówień, danych klienta i dat generacji. Używa `HelperList` do renderowania tabeli i zapewnia możliwości filtrowania. Nie pozwala na ręczne tworzenie ani edytowanie nagród, ponieważ są one generowane automatycznie.
-   `controllers/admin/index.php`
    *   **Nazwa klasy:** `AdminOrdercouponsIndexController` (prawdopodobnie)
    *   **Klasa nadrzędna:** `ModuleAdminController` (lub `AdminController`)
    *   **Odpowiedzialność:** Podobnie jak `index.php` w Front Office, jest to prawdopodobnie symbol zastępczy lub domyślny kontroler dla sekcji administracyjnej, zapewniający ochronę katalogu lub dostarczający widok awaryjny. Główna funkcjonalność administracyjna jest obsługiwana przez `AdminOrderCouponsRewards.php`.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dostarczony spis nie wskazuje na żadne niestandardowe klasy w katalogu `classes/`. Sugeruje to, że podstawowa logika modułu do generowania kuponów może znajdować się bezpośrednio w głównym pliku modułu `cronjob.php` lub wykorzystuje wbudowany `ObjectModel` `CartRule` (Rabat) PrestaShop i powiązane z nim metody.

-   **Interakcja z `CartRule`:** Moduł bezpośrednio wchodziłby w interakcję z klasą `CartRule` PrestaShop, aby tworzyć nowe kody rabatowe. Obejmuje to ustawianie właściwości takich jak `code`, `value`, `reduction_type`, `minimum_amount`, `date_from`, `date_to`, `quantity`, `quantity_per_user`, `id_customer`, `id_group`, `id_product`, `id_category`, `reduction_exclude_special`, `free_shipping` itp., na podstawie konfiguracji modułu.
-   **Niestandardowa tabela `orewards_list`:** Chociaż nie ma jawnie wymienionego `ObjectModel`, `AdminOrderCouponsRewardsController` zarządza `orewards_list`. To silnie sugeruje, że istnieje niestandardowa tabela bazy danych `ps_orewards_list` (lub podobny prefiks) do logowania wygenerowanych nagród. Kontroler bezpośrednio odpytywałby tę tabelę lub używał prostej warstwy dostępu do danych.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `ordercoupons/js/script.js`
    *   **Zakres:** Prawdopodobnie Back Office.
    *   **Odpowiedzialność:** Ogólny JavaScript dla strony konfiguracji modułu lub ekranów administracyjnych. Może to obejmować walidację formularzy, wywołania AJAX do zapisywania ustawień, dynamiczne aktualizacje interfejsu użytkownika lub nasłuchiwacze zdarzeń dla konkretnych opcji konfiguracji.
-   `ordercoupons/lib/emailTemplatesManager/js/emailTemplatesManager.js`
    *   **Zakres:** Back Office.
    *   **Odpowiedzialność:** Zarządza interfejsem edycji szablonów e-mail. Ten skrypt obsługiwałby dynamiczne wstawianie symboli zastępczych, możliwości edycji tekstu sformatowanego, funkcjonalność podglądu i zapisywanie treści e-mail.
-   `ordercoupons/lib/searchTool/views/js/autocomplete.js`
    *   **Zakres:** Back Office.
    *   **Odpowiedzialność:** Zapewnia funkcjonalność autouzupełniania dla pól wejściowych, prawdopodobnie używaną do wybierania konkretnych produktów, kategorii lub grup klientów w formularzach konfiguracji modułu. Obsługiwałby żądania AJAX w celu pobierania wyników wyszukiwania i wyświetlania ich użytkownikowi.
-   `ordercoupons/lib/voucherengine/script.js`
    *   **Zakres:** Back Office.
    *   **Odpowiedzialność:** Specyficzny JavaScript związany z silnikiem generowania kuponów. Może to obejmować logikę dynamicznego obliczania długości kodu kuponu, walidacji wartości kuponów lub interakcji z ustawieniami `CartRule` w formularzu konfiguracji.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `ordercoupons/css.css`
    *   **Zakres:** Głównie Back Office, potencjalnie trochę Front Office, jeśli moduł miał widoczne elementy. Biorąc pod uwagę charakter modułu, jest to głównie do stylizacji administracyjnej.
    *   **Główne komponenty interfejsu użytkownika:** Ogólna stylizacja strony konfiguracji modułu i tabeli „Lista nagród”.
    *   **Kluczowe selektory klas CSS:** `.ordercoupons-config`, `.ordercoupons-table`, `.ordercoupons-form-group`.
-   `ordercoupons/lib/emailTemplatesManager/css/emailTemplatesManager.css`
    *   **Zakres:** Back Office.
    *   **Główne komponenty interfejsu użytkownika:** Style dla interfejsu edytora szablonów e-mail, w tym obszarów tekstowych, przycisków i sekcji podglądu.
    *   **Kluczowe selektory klas CSS:** `.email-template-editor`, `.template-preview`.
-   `ordercoupons/lib/searchTool/views/css/autocomplete.css`
    *   **Zakres:** Back Office.
    *   **Główne komponenty interfejsu użytkownika:** Stylizacja dla rozwijanych list autouzupełniania i pól wejściowych.
    *   **Kluczowe selektory klas CSS:** `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item`.
-   `ordercoupons/lib/voucherengine/ps16.css`
    *   **Zakres:** Back Office.
    *   **Główne komponenty interfejsu użytkownika:** Specyficzne dostosowania stylizacji dla kompatybilności z PrestaShop 1.6 lub konkretnych elementów związanych z silnikiem kuponów, zapewniające spójny wygląd i działanie w różnych wersjach PS.
    *   **Kluczowe selektory klas CSS:** `.voucher-engine-settings`, `.ps16-compat`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

Spis nie wymienia żadnych szablonów bezpośrednio w `views/templates/hook/`. Potwierdza to, że moduł nie renderuje żadnej zawartości wizualnej bezpośrednio w standardowych hookach PrestaShop, takich jak `displayHeader`, `displayRightColumn`, `displayFooter` itp. Jego interakcja z Front Office odbywa się wyłącznie za pośrednictwem poczty e-mail.

#### Szablony administracyjne (`views/templates/admin/`)

-   `ordercoupons/views/templates/admin/admin.tpl`
    *   **Cel:** Główny szablon strony konfiguracji modułu (dostępny za pośrednictwem `getContent()` w `cronjob.php`). Zawierałby strukturę formularza dla wszystkich ustawień opisanych w Sekcji 4.1.
-   `ordercoupons/views/templates/admin/customerGroups.tpl`
    *   **Cel:** Częściowy szablon prawdopodobnie używany w `admin.tpl` do renderowania interfejsu wyboru dla „Zastosuj kupon do określonych grup klientów”.
-   `ordercoupons/views/templates/admin/orderstates.tpl`
    *   **Cel:** Częściowy szablon prawdopodobnie używany w `admin.tpl` do renderowania interfejsu wyboru dla „Statusów zamówień do generowania kuponów”.
-   `ordercoupons/views/templates/admin/scripts.tpl`
    *   **Cel:** Częściowy szablon używany do dołączania plików JavaScript lub wbudowanego JavaScript specyficznego dla strony konfiguracji administracyjnej. Jest to powszechna praktyka, aby oddzielić JS od głównej struktury HTML.

#### Szablony Front Office (`views/templates/front/`)

Spis nie wymienia żadnych szablonów bezpośrednio w `views/templates/front/`. Jest to zgodne z zachowaniem modułu, który nie wyświetla zawartości Front Office.

#### Szablony bibliotek

-   `ordercoupons/lib/emailTemplatesManager/views/buttonManager.tpl`
-   `ordercoupons/lib/emailTemplatesManager/views/createTemplateForm.tpl`
-   `ordercoupons/lib/emailTemplatesManager/views/editTemplateForm.tpl`
-   `ordercoupons/lib/emailTemplatesManager/views/mainForm.tpl`
-   `ordercoupons/lib/emailTemplatesManager/views/selectInput.tpl`
    *   **Cel:** Te szablony są częścią biblioteki `emailTemplatesManager` i służą do renderowania interfejsu do zarządzania i edycji szablonów e-mail w konfiguracji modułu. `mainForm.tpl` byłby prawdopodobnie głównym punktem wejścia, a inne byłyby częściami dla konkretnych elementów interfejsu użytkownika.
-   `ordercoupons/lib/searchTool/views/scripts.tpl`
    *   **Cel:** Szablon do dołączania plików JavaScript lub wbudowanych skryptów dla biblioteki `searchTool`, w szczególności dla funkcjonalności autouzupełniania.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

-   **`ps_configuration`**: Moduł przechowuje swoje ustawienia konfiguracyjne (np. `ORDERCOUPONS_ENABLED`, `ORDERCOUPONS_ORDER_STATES`, `ORDERCOUPONS_VOUCHER_VALUE`) w standardowej tabeli `ps_configuration` PrestaShop.
-   **`ps_orewards_list` (Domniemana tabela niestandardowa)**: Na podstawie `AdminOrderCouponsRewardsController` zarządzającego `orewards_list`, jest bardzo prawdopodobne, że moduł tworzy niestandardową tabelę bazy danych, prawdopodobnie nazwaną `ps_orewards_list`, do logowania każdego wygenerowanego kuponu.
    *   **Schemat (prawdopodobne pola):**
        *   `id_orewards_list` (KLUCZ GŁÓWNY, INT)
        *   `id_order` (INT)
        *   `id_customer` (INT)
        *   `customer_email` (VARCHAR)
        *   `order_reference` (VARCHAR)
        *   `reward_code` (VARCHAR)
        *   `date_add` (DATETIME)

#### Tabela zarejestrowanych hooków

Opis modułu wspomina o „Hookach Front Office: Nagłówek, Kolumny, Produkt lub Stopka”. Jednak spis plików i podstawowa funkcja modułu (wysyłanie kuponów e-mailem) sugerują, że prawdopodobnie *nie* są one używane do wyświetlania treści, ale być może do wewnętrznego przetwarzania lub ładowania zasobów, jeśli moduł miałby jakiekolwiek komponenty Front Office. Biorąc pod uwagę charakter modułu, najważniejsze hooki to hooki akcji.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu i zapisaniu zamówienia w bazie danych. | Jest to najbardziej prawdopodobny hook, w którym moduł wykrywa nowe zamówienia, które muszą zostać przetworzone w celu wygenerowania kuponów. Moduł nasłuchiwałby tego zdarzenia, aby zidentyfikować potencjalnych kandydatów. |
| `actionOrderStatusPostUpdate` | Po zmianie statusu zamówienia w Panelu administracyjnym. | Kluczowe dla modułu do sprawdzenia, czy zamówienie osiągnęło jeden ze skonfigurowanych „Statusów zamówień do generowania kuponów” (np. „Płatność zaakceptowana”, „Dostarczono”). To tutaj zadanie cron prawdopodobnie wyzwoliłoby logikę generowania kuponów. |
| `displayBackOfficeHeader` | Renderuje zawartość w sekcji `<head>` Panelu administracyjnego. | Używane do dołączania plików CSS i JavaScript specyficznych dla modułu dla stron konfiguracji administracyjnej i ekranu „Lista nagród”. |
| `moduleRoutes` | Pozwala modułom definiować niestandardowe przyjazne adresy URL. | Mniej prawdopodobne dla tego modułu, ale możliwe, jeśli potrzebowałby konkretnej trasy dla swojego zadania cron lub innych wewnętrznych procesów. |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` Front Office. | Jeśli moduł musiałby załadować jakiekolwiek globalne JS/CSS dla potencjalnych przyszłych funkcji Front Office lub do celów śledzenia. (Mało prawdopodobne dla obecnej funkcjonalności). |
| `displayRightColumn` / `displayLeftColumn` | Renderuje zawartość w bocznych kolumnach Front Office. | Nie używane dla obecnej funkcjonalności tego modułu. |
| `displayFooter` | Renderuje zawartość w stopce Front Office. | Nie używane dla obecnej funkcjonalności tego modułu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Nagrody - Kody kuponów po zamówieniach”, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Możesz pobrać najnowsze wersje z historii zamówień i uzyskać dostęp do dedykowanych kanałów wsparcia w celu uzyskania pomocy technicznej lub zapytań.
