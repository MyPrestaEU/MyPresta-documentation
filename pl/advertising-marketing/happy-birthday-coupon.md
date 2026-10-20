---
title: "Kupon Urodzinowy - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Kupon Urodzinowy od MyPresta.eu."
sidebar:
  label: "Kupon Urodzinowy - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Happy Birthday Coupon na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/happy-birthday-coupon.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/happy-birthday-coupon/)
>
> ---


# Kupon Urodzinowy

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Upewnij się, że funkcja cron job Twojego serwera jest włączona dla automatycznego wysyłania kuponów.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Kupon Urodzinowy)

Jest to główny ekran konfiguracji, na którym definiujesz, w jaki sposób będą generowane i wysyłane kupony urodzinowe.

#### Ustawienia ogólne

-   **Liczba dni przed urodzinami klienta, aby wysłać kupon (bp\_daysbefore)**

    -   **Co robi to ustawienie:** Określa, ile dni *przed* faktycznymi urodzinami klienta zostanie wysłany e-mail z kuponem.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na 0:* Kupon zostanie wysłany w dniu urodzin klienta.
        -   *Gdy ustawione na 7:* Kupon zostanie wysłany 7 dni przed urodzinami klienta. Daje to im tydzień na zaplanowanie zakupu.
    -   **Zalecana wartość:** `7` dni. Daje to klientom wystarczająco dużo czasu na przeglądanie Twojego sklepu i podjęcie decyzji o zakupie, zamiast otrzymywania go w dniu, w którym mogą być zajęci.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby klienci otrzymali swój urodzinowy prezent tydzień wcześniej, aby mieli czas na wykorzystanie go na specjalny zakup urodzinowy. Ustawienie tego na `7` zapewnia, że otrzymają e-mail z wystarczającym wyprzedzeniem.
-   **Włącz opcję newslettera (bpro\_nletter)**

    -   **Co robi to ustawienie:** Kontroluje, czy funkcja kuponu urodzinowego jest powiązana ze statusem subskrypcji newslettera klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Tylko klienci, którzy są subskrybentami Twojego newslettera, otrzymają kupon urodzinowy.
        -   *Gdy wyłączone (NIE):* Wszyscy klienci z ważną datą urodzenia na swoim koncie otrzymają kupon urodzinowy, niezależnie od ich subskrypcji newslettera.
    -   **Zalecana wartość:** `NIE`. Aby zmaksymalizować wpływ i zasięg, ogólnie lepiej jest wysyłać kupony urodzinowe do wszystkich klientów z datą urodzenia, ponieważ jest to osobisty gest. Jeśli jednak chcesz nagradzać konkretnie subskrybentów newslettera, ustaw na `TAK`.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz nagradzać wszystkich swoich lojalnych klientów w dniu ich urodzin, a nie tylko tych, którzy subskrybują Twój newsletter. Ustawisz to na `NIE`.
-   **Grupy klientów do uwzględnienia (birthdaypro\_groups)**

    -   **Co robi to ustawienie:** Pozwala wybrać konkretne grupy klientów, które są uprawnione do otrzymywania kuponów urodzinowych.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrane są konkretne grupy:* Tylko klienci należący do tych wybranych grup otrzymają kupony urodzinowe.
        -   *Gdy nie wybrano żadnych grup (lub wybrano wszystkie):* Wszyscy klienci (z zastrzeżeniem innych ustawień, takich jak opcja newslettera) będą uprawnieni.
    -   **Zalecana wartość:** Wybierz `Klient` i wszelkie inne grupy, które chcesz uwzględnić. Unikaj wybierania `Gość` lub `Odwiedzający`, ponieważ zazwyczaj nie mają oni kont z datami urodzenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz grupę „Klienci VIP” i grupę „Hurtowi”. Chcesz wysyłać kupony urodzinowe tylko do swojej regularnej grupy „Klient” i „Klienci VIP”, ale nie do swoich partnerów hurtowych. Wybierzesz „Klient” i „Klienci VIP” z listy.
-   **Lista klientów (Informacyjna)**

    -   **Co robi to ustawienie:** To nie jest ustawienie do zmiany, ale sekcja informacyjna, która prawdopodobnie wyświetla listę klientów, którzy otrzymali lub są uprawnieni do otrzymania kuponów urodzinowych. Pomaga monitorować aktywność modułu.
    -   **Efekt zmiany tego ustawienia:** Brak bezpośredniego efektu, ponieważ jest to funkcja tylko do wyświetlania.
    -   **Zalecana wartość:** N/A
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz szybko sprawdzić, którzy klienci mają zarejestrowane daty urodzenia i mogą wkrótce otrzymać kupony.

#### Ustawienia kuponu (Zaawansowana personalizacja)

Moduł umożliwia szeroką personalizację generowanych kuponów. Te ustawienia odzwierciedlają standardowe opcje reguł koszyka (kuponów) PrestaShop.

-   **Prefiks kodu kuponu:** (np. `URODZINY-`)

    -   **Co robi to ustawienie:** Definiuje prefiks dla wszystkich generowanych kodów kuponów urodzinowych.
    -   **Efekt zmiany tego ustawienia:** Wszystkie unikalne kody będą zaczynać się od tego prefiksu, co ułatwi ich identyfikację.
    -   **Zalecana wartość:** `URODZINY-` lub `BDP-`.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz łatwo odróżnić kupony urodzinowe od innych promocji w historii zamówień.
-   **Typ rabatu:** (np. Procentowy, Kwotowy, Darmowa wysyłka)

    -   **Co robi to ustawienie:** Określa typ rabatu, jaki oferuje kupon.
    -   **Efekt zmiany tego ustawienia:**
        -   *Procentowy:* Stosuje rabat procentowy do zamówienia.
        -   *Kwotowy:* Stosuje stały rabat kwotowy.
        -   *Darmowa wysyłka:* Zapewnia darmową wysyłkę.
    -   **Zalecana wartość:** `Procentowy` lub `Kwotowy`, w zależności od Twojej strategii marketingowej.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz zaoferować 15% rabatu na urodziny. Wybierzesz `Procentowy` i ustawisz wartość na `15`.
-   **Wartość rabatu:** (np. `15` dla procentowego, `10.00` dla kwotowego)

    -   **Co robi to ustawienie:** Rzeczywista wartość rabatu.
    -   **Efekt zmiany tego ustawienia:** Bezpośrednio wpływa na rabat zastosowany do zamówienia klienta.
    -   **Zalecana wartość:** Wartość, która jest atrakcyjna, ale także opłacalna dla Twojego sklepu (np. `10` dla 10% lub `5.00` dla 5 zł).
    -   **Scenariusz / przykład dla sprzedawcy:** Zgodnie z powyższym, wpiszesz tutaj `15`.
-   **Minimalna kwota:**

    -   **Co robi to ustawienie:** Ustawia minimalną kwotę zakupu wymaganą do ważności kuponu.
    -   **Efekt zmiany tego ustawienia:** Zachęca klientów do wydawania więcej, aby kwalifikować się do rabatu.
    -   **Zalecana wartość:** Rozsądna kwota, która zachęca do sprzedaży dodatkowej, nie będąc zbyt restrykcyjną.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby klienci wydali co najmniej 50 zł, aby użyć swojego kuponu urodzinowego. Ustawisz to na `50.00`.
-   **Okres ważności:** (np. `30` dni)

    -   **Co robi to ustawienie:** Definiuje, ile dni kupon jest ważny od daty wysłania.
    -   **Efekt zmiany tego ustawienia:** Tworzy poczucie pilności u klienta, aby użyć kuponu.
    -   **Zalecana wartość:** `30` dni. Daje to klientom wystarczająco dużo czasu na wykorzystanie prezentu bez poczucia pośpiechu.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby klienci wykorzystali swój kupon urodzinowy w ciągu miesiąca od jego otrzymania. Ustawisz to na `30`.
-   **Zastosuj do konkretnych produktów/kategorii:**

    -   **Co robi to ustawienie:** Pozwala ograniczyć użycie kuponu do określonych produktów lub kategorii.
    -   **Efekt zmiany tego ustawienia:** Może być użyte do promowania konkretnych przedmiotów lub wyprzedaży starych zapasów.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretny cel promocyjny.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby kupon urodzinowy był ważny tylko dla produktów z kategorii „Nowości”.
-   **Inne opcje kuponu:** (np. kumulatywny z innymi kuponami, produkty-prezenty itp.)

    -   **Co robi to ustawienie:** Moduł prawdopodobnie udostępnia inne zaawansowane opcje reguł koszyka z PrestaShop, takie jak to, czy kupon może być łączony z innymi rabatami, czy dotyczy konkretnych przewoźników, czy oferuje darmowy prezent.
    -   **Efekt zmiany tego ustawienia:** Daje Ci precyzyjną kontrolę nad zachowaniem i ograniczeniami kuponu.
    -   **Zalecana wartość:** Skonfiguruj zgodnie z Twoją konkretną strategią promocyjną. Zachowaj ostrożność z kumulatywnością, aby uniknąć nadmiernych rabatów.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz upewnić się, że kupon urodzinowy nie może być łączony z innymi trwającymi promocjami. Wyłączysz opcję „Kumulatywny z innymi kuponami”.

#### Ustawienia szablonu e-mail

-   **Temat e-maila:** (np. `Wszystkiego najlepszego od {shop_name}! Oto prezent dla Ciebie!`)

    -   **Co robi to ustawienie:** Definiuje temat e-maila urodzinowego.
    -   **Efekt zmiany tego ustawienia:** To pierwsza rzecz, którą widzą klienci; przekonujący temat zwiększa wskaźniki otwarć.
    -   **Zalecana wartość:** Coś ciepłego, osobistego i wyraźnie wskazującego na prezent. Użyj `{shop_name}` i `{customer_firstname}`, jeśli są dostępne.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz chwytliwy temat, który sprawi, że klienci poczują się wyjątkowo.
-   **Treść e-maila:** (edytor HTML)

    -   **Co robi to ustawienie:** Pozwala dostosować pełną treść e-maila urodzinowego.
    -   **Efekt zmiany tego ustawienia:** To tutaj przekazujesz życzenia urodzinowe, wyjaśniasz rabat i zachęcasz do zakupów.
    -   **Zalecana wartość:** Dołącz ciepłe powitanie, wyraźnie podaj kod rabatowy i jego wartość, wyjaśnij, jak go użyć, i dodaj wezwanie do działania. Użyj symboli zastępczych, takich jak `{customer_firstname}`, `{voucher_code}`, `{shop_name}`, `{shop_url}`.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz napisać serdeczną wiadomość, dołączyć logo swojej marki i wyraźnie pokazać kod rabatowy.

#### Informacje o zadaniu Cron

-   **URL zadania Cron:** (np. `http://twoj_sklep.com/modules/birthdaypro/controllers/front/cron.php?token=TWOJ_BEZPIECZNY_TOKEN`)
    -   **Co robi to ustawienie:** Wyświetla URL, który musisz ustawić jako zadanie cron na swoim serwerze. To zadanie cron jest niezbędne, aby moduł automatycznie sprawdzał nadchodzące urodziny i wysyłał kupony.
    -   **Efekt zmiany tego ustawienia:** To nie jest ustawienie do zmiany, ale instrukcja. Jeśli zadanie cron nie zostanie poprawnie skonfigurowane, żadne kupony urodzinowe nie zostaną wysłane automatycznie.
    -   **Zalecana wartość:** Ustaw zadanie cron, aby uruchamiało ten URL raz na 24 godziny (np. codziennie o północy).
    -   **Scenariusz / przykład dla sprzedawcy:** Skonfigurowałeś wszystkie ustawienia, ale żadne e-maile nie są wysyłane. Pierwszą rzeczą do sprawdzenia jest, czy Twój dostawca hostingu poprawnie skonfigurował zadanie cron, używając tego URL.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Dni przed urodzinami klienta, aby wysłać kupon | `7` | Wysyła kupon X dni przed urodzinami, zachęcając do planowanych zakupów. |
| Konfiguracja modułu | Włącz opcję newslettera | `NIE` | Określa, czy tylko subskrybenci newslettera otrzymują kupony. `NIE` dla szerszego zasięgu. |
| Konfiguracja modułu | Grupy klientów do uwzględnienia | `Klient` (i inne w razie potrzeby) | Ogranicza wysyłanie kuponów do określonych segmentów klientów. |
| Konfiguracja modułu | Prefiks kodu kuponu | `URODZINY-` | Dodaje unikalny prefiks do generowanych kodów kuponów dla łatwej identyfikacji. |
| Konfiguracja modułu | Typ rabatu | `Procentowy` lub `Kwotowy` | Definiuje rodzaj rabatu (np. 15% zniżki, 10 zł zniżki). |
| Konfiguracja modułu | Wartość rabatu | `10` (dla 10%) lub `5.00` (dla 5 zł) | Rzeczywista wartość rabatu. |
| Konfiguracja modułu | Minimalna kwota | (Puste lub konkretna wartość) | Ustawia minimalną wartość zamówienia, aby kupon był ważny. |
| Konfiguracja modułu | Okres ważności | `30` dni | Jak długo kupon jest ważny od daty wysłania, tworząc poczucie pilności. |
| Konfiguracja modułu | Zastosuj do konkretnych produktów/kategorii | (Puste lub konkretny wybór) | Ogranicza użycie kuponu do określonych produktów lub kategorii. |
| Konfiguracja modułu | Inne opcje kuponu | (Zgodnie ze strategią) | Precyzyjna kontrola nad zachowaniem kuponu (np. kumulatywność). |
| Konfiguracja modułu | Temat e-maila | `Wszystkiego najlepszego od {shop_name}!` | Temat e-maila urodzinowego. |
| Konfiguracja modułu | Treść e-maila | (Niestandardowy HTML) | Treść e-maila urodzinowego, w tym życzenia i szczegóły kuponu. |
| Konfiguracja modułu | URL zadania Cron | (Wyświetlony URL) | Niezbędny do automatycznych codziennych kontroli i wysyłania kuponów. Musi być skonfigurowany na serwerze. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci nie otrzymują e-maili urodzinowych. Co powinienem najpierw sprawdzić?**
O1:

1.  **Zadanie Cron:** Najczęstszy powód. Upewnij się, że URL zadania cron podany w konfiguracji modułu jest poprawnie skonfigurowany na Twoim serwerze hostingowym, aby uruchamiał się codziennie. Bez niego moduł nie może automatycznie wysyłać e-maili.
2.  **Daty urodzenia klientów:** Sprawdź, czy Twoi klienci faktycznie mają wprowadzone daty urodzenia w swoich kontach PrestaShop. Moduł opiera się na tych danych.
3.  **Konfiguracja e-maila:** Sprawdź ustawienia e-maila w PrestaShop (Zaawansowane > E-mail), aby upewnić się, że Twój sklep może pomyślnie wysyłać e-maile. Przetestuj wysyłanie ogólnego e-maila z PrestaShop.
4.  **Foldery spamowe:** Doradź klientom, aby sprawdzili swoje foldery spamowe lub niechciane.
5.  **Ustawienia modułu:** Dokładnie sprawdź „Liczba dni przed urodzinami klienta”, „Włącz opcję newslettera” i „Grupy klientów do uwzględnienia”, aby upewnić się, że klienci są uprawnieni.

**P2: Kod rabatowy nie działa dla moich klientów.**
O2:

1.  **Ważność kuponu:** Sprawdź ustawienie „Okres ważności” w module. Czy kupon wygasł?
2.  **Minimalna kwota:** Czy koszyk klienta spełnia wymóg „Minimalnej kwoty” ustawiony dla kuponu?
3.  **Ograniczenia produktów/kategorii:** Jeśli zastosowałeś ograniczenia, czy klient próbuje kupić kwalifikujący się produkt?
4.  **Kumulatywny z innymi kuponami:** Jeśli wyłączyłeś tę opcję, upewnij się, że klient nie próbuje połączyć go z innym rabatem.
5.  **Błędy pisowni:** Poproś klienta, aby dokładnie sprawdził, czy nie ma błędów pisowni podczas wprowadzania kodu.

**P3: Jak zmienić wygląd i styl e-maila urodzinowego?**
O3: Możesz w pełni dostosować treść e-maila za pomocą edytora HTML w ustawieniu „Treść e-maila” na stronie konfiguracji modułu. Możesz dodać swoje logo, zmienić czcionki, kolory i układ. Pamiętaj, aby używać dostępnych symboli zastępczych (takich jak `{customer_firstname}`, `{voucher_code}`, `{shop_name}`) do personalizacji wiadomości.

**P4: Czy mogę wysyłać różne kupony urodzinowe do różnych grup klientów?**
O4: Moduł Kupon Urodzinowy, w swojej standardowej konfiguracji, wysyła jeden typ kuponu na podstawie zdefiniowanych ustawień. Aby wysyłać różne kupony do różnych grup (np. 10% rabatu dla stałych klientów i 20% rabatu dla VIP-ów), musiałbyś:
a) Ręcznie tworzyć i wysyłać oddzielne kupony dla konkretnych grup (co niweczy automatyzację).
b) Używać natywnych „Reguł koszyka” PrestaShop dla konkretnych grup i zarządzać nimi ręcznie.
c) Rozważyć zaawansowane dostosowanie lub bardziej złożone rozwiązanie automatyzacji marketingu, jeśli jest to krytyczne wymaganie.

**P5: Moduł wydaje się działać, ale nie widzę żadnych dowodów na generowanie kuponów w sekcji „Reguły koszyka” PrestaShop.**
O5: Moduł generuje unikalne reguły koszyka (kupony) dynamicznie, gdy zbliżają się urodziny klienta. Są to rzeczywiste reguły koszyka PrestaShop. Powinieneś je widzieć w **Katalog > Rabaty > Reguły koszyka** (lub **Reguły cenowe > Reguły koszyka** w starszych wersjach). Szukaj reguł z zdefiniowanym prefiksem (np. `URODZINY-`). Jeśli się nie pojawiają, sprawdź ponownie konfigurację zadania cron i modułu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem Kupon Urodzinowy.

### 4.1 Przegląd architektury

Moduł Kupon Urodzinowy (`birthdaypro`) stosuje standardową architekturę modułu PrestaShop, wykorzystując `Module` jako swoją bazę. Działa głównie poprzez zadanie cron, które uruchamia kontroler front-office w celu identyfikacji uprawnionych klientów i generowania obiektów `CartRule` PrestaShop. Moduł nie rozszerza `ObjectModel` dla własnych danych, ale opiera się na istniejących danych klientów PrestaShop i funkcjonalności `CartRule`. Wykorzystuje niestandardowy silnik kuponów i narzędzie wyszukiwania autouzupełniania, prawdopodobnie do wyboru klientów w panelu administracyjnym lub testowania.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery są zaprojektowane do dostępu zewnętrznego, głównie za pośrednictwem zadań cron.

-   **`controllers/front/cron.php`**

    -   **Nazwa klasy i klasa nadrzędna:** `BirthdayproCronModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Jest to podstawowa logika automatycznego generowania i wysyłania kuponów. Jest zaprojektowany do wywoływania przez zadanie cron po stronie serwera.
        -   Pobiera daty urodzenia klientów.
        -   Określa, którzy klienci są uprawnieni na podstawie konfiguracji `bp_daysbefore`, `bpro_nletter` i `birthdaypro_groups`.
        -   Dla każdego uprawnionego klienta generuje unikalną `CartRule` (kupon) PrestaShop z skonfigurowanymi parametrami.
        -   Wysyła e-mail urodzinowy zawierający kod kuponu do klienta.
        -   Zawiera sprawdzanie tokena bezpieczeństwa, aby zapobiec nieautoryzowanemu dostępowi.
-   **`controllers/front/index.php`**

    -   **Nazwa klasy i klasa nadrzędna:** `BirthdayproIndexModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler prawdopodobnie służy jako symbol zastępczy lub prosty punkt wejścia, być może do testowania lub obsługi żądań, które nie pasują do innych konkretnych kontrolerów front-office. W wielu modułach `index.php` w katalogu kontrolera jest rezerwowym lub podstawowym kontrolerem typu „hello world”. Może nie zawierać znaczącej logiki biznesowej.

#### Kontrolery administracyjne Back-Office

Moduł nie wydaje się mieć dedykowanych niestandardowych kontrolerów administracyjnych na podstawie dostarczonego spisu. Cała konfiguracja back-office jest obsługiwana w głównej metodzie `getContent()` modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Dostarczony spis wskazuje, że w katalogu `classes/` nie ma niestandardowych klas ani modeli. Moduł prawdopodobnie bezpośrednio wykorzystuje natywne klasy PrestaShop `Customer`, `CartRule` i `Mail`. Wzmianki o „voucherengine” i „searchTool” w ścieżkach JS/CSS sugerują wewnętrzne klasy pomocnicze lub funkcje w `birthdaypro.php` lub jego dołączonych bibliotekach, a nie samodzielne pliki `classes/`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`lib/searchTool/views/js/autocomplete.js`**

    -   **Zakres:** Prawdopodobnie Back-office.
    -   **Szczegóły:** Ten skrypt zapewnia funkcjonalność autouzupełniania, prawdopodobnie do wyszukiwania klientów lub produktów w konfiguracji modułu lub powiązanym interfejsie administracyjnym. Będzie wiązał się z polami wejściowymi, wykonywał żądania AJAX do punktu końcowego backendu (prawdopodobnie głównego pliku modułu lub dedykowanego kontrolera administracyjnego, jeśli taki istniał) i wyświetlał sugestie.
-   **`lib/voucherengine/script.js`**

    -   **Zakres:** Prawdopodobnie Back-office.
    -   **Szczegóły:** Ten skrypt jest częścią „silnika kuponów” modułu. Prawdopodobnie obsługuje dynamiczne elementy formularza związane z tworzeniem kuponów na stronie konfiguracji modułu. Może to obejmować pokazywanie/ukrywanie pól na podstawie wyboru typu rabatu, walidację danych wejściowych dla wartości kuponów lub interakcję z innymi ustawieniami związanymi z kuponami.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`lib/searchTool/views/css/autocomplete.css`**

    -   **Zakres:** Prawdopodobnie Back-office.
    -   **Szczegóły:** Zapewnia stylizację dla rozwijanej listy sugestii autouzupełniania i ewentualnie samego pola wejściowego, zapewniając jego wizualną integrację z panelem administracyjnym PrestaShop.
-   **`lib/voucherengine/ps16.css`**

    -   **Zakres:** Prawdopodobnie Back-office.
    -   **Szczegóły:** Ten arkusz stylów zapewnia specyficzną stylizację dla elementów konfiguracji kuponów, potencjalnie celując w estetykę panelu administracyjnego PrestaShop 1.6. Może zawierać style dla grup formularzy, pól wejściowych i etykiet związanych z ustawieniami kuponów.
-   **`views/css/css.css`**

    -   **Zakres:** Prawdopodobnie Back-office.
    -   **Szczegóły:** Ogólny arkusz stylów dla modułu, potencjalnie zawierający style dla głównej strony konfiguracji (`admin.tpl`) lub wszelkich niestandardowych elementów wprowadzonych przez moduł w panelu administracyjnym. Może zawierać podstawowe style układu, przycisków lub alertów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`lib/searchTool/views/scripts.tpl`**

    -   **Zakres:** Back-office.
    -   **Szczegóły:** Ten szablon prawdopodobnie zawiera kod JavaScript lub zmienne Smarty potrzebne do prawidłowego działania skryptu `autocomplete.js`, takie jak adresy URL AJAX, ciągi językowe lub początkowe dane. Zostałby on dołączony do głównego szablonu konfiguracji administracyjnej.
-   **`views/templates/admin.tpl`**

    -   **Zakres:** Back-office.
    -   **Szczegóły:** Jest to główny szablon strony konfiguracji modułu, renderowany przez metodę `getContent()` w `birthdaypro.php`. Zawiera strukturę HTML dla wszystkich ustawień opisanych w Sekcji 4.1, w tym pól formularza, przycisków i potencjalnie dołączenia innych szablonów, takich jak `scripts.tpl`.
-   **`views/templates/script.tpl`**

    -   **Zakres:** Back-office.
    -   **Szczegóły:** Podobnie jak `scripts.tpl` w bibliotece `searchTool`, ten szablon prawdopodobnie zawiera specyficzne dla modułu zmienne JavaScript lub Smarty, które są wstrzykiwane na stronę konfiguracji back-office. Może obsługiwać dynamiczne zachowanie lub przekazywanie danych dla silnika kuponów.
-   **`views/templates/test.tpl`**

    -   **Zakres:** Back-office lub testy wewnętrzne.
    -   **Szczegóły:** Cel tego szablonu jest mniej jasny z samej nazwy. Może to być szablon używany do testów wewnętrznych podczas rozwoju, szablon wyjścia debugowania lub prosty symbol zastępczy. Jest mało prawdopodobne, aby był częścią standardowej konfiguracji dla sprzedawców.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy niestandardowych tabel bazy danych na podstawie dostarczonego spisu.
    -   Przechowuje swoje ustawienia konfiguracyjne (np. `bp_daysbefore`, `bpro_nletter`, `birthdaypro_groups`) w tabeli `ps_configuration` PrestaShop.
    -   Współpracuje z istniejącymi tabelami PrestaShop: `ps_customer` (dla dat urodzenia), `ps_cart_rule` (do tworzenia kuponów), `ps_cart_rule_lang`, `ps_cart_rule_shop`, `ps_cart_rule_product_rule_group` itp.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas / Kontekst wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Zazwyczaj używany do dodawania CSS, JS lub meta tagów. Opis modułu o tym wspomina, ale jego główna funkcja opiera się na cronie, więc ten hook może być używany do minimalnej konfiguracji front-endu lub nie być aktywnie używany do podstawowej funkcjonalności. |
| `displayRightColumn` | W prawej kolumnie stron front-office. | Wyświetla zawartość w prawym pasku bocznym. Mało prawdopodobne, aby był używany przez ten moduł, biorąc pod uwagę jego działanie w tle. |
| `displayLeftColumn` | W lewej kolumnie stron front-office. | Wyświetla zawartość w lewym pasku bocznym. Mało prawdopodobne, aby był używany przez ten moduł, biorąc pod uwagę jego działanie w tle. |
| `displayFooter` | W sekcji stopki każdej strony front-office. | Wyświetla zawartość w stopce. Mało prawdopodobne, aby był używany przez ten moduł, biorąc pod uwagę jego działanie w tle. |
| `displayProductButtons` / `displayProductExtraContent` (lub podobne hooki produktu) | Na stronie produktu. | Mało prawdopodobne, aby był używany przez ten moduł. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Może być potencjalnie używany do śledzenia wykorzystania kuponów lub zachowania klienta po zastosowaniu kuponu urodzinowego, chociaż nie jest to wyraźnie wymienione jako podstawowa funkcja. |
| `actionCustomerAccountAdd` / `actionCustomerAccountUpdate` | Gdy konto klienta jest tworzone lub aktualizowane. | Może być używany do sprawdzania wpisu daty urodzenia lub wyzwalania początkowej konfiguracji dla nowych klientów, chociaż zadanie cron jest głównym wyzwalaczem. |
| (Niejawne) Wykonanie zadania Cron | Codziennie, za pośrednictwem zewnętrznego crona serwera. | **KRYTYCZNE:** Jest to główny „hook” dla podstawowej funkcjonalności modułu, wyzwalający `controllers/front/cron.php` do przetwarzania urodzin i wysyłania e-maili. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu Kupon Urodzinowy, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół dokłada wszelkich starań, aby Twój moduł działał optymalnie i pomagał Ci osiągać cele e-commerce.
