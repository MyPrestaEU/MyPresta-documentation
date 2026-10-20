---
title: "Cart protection pro - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Cart protection pro od MyPresta.eu."
sidebar:
  label: "Cart protection pro - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Cart protection pro na MyPresta.eu](https://mypresta.eu/modules/administration-tools/cart-protection-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/cart-protection-pro/)
>
> ---


# Cart protection pro

## 1. Wymagania i kompatybilność

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 5.6 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do integracji z zewnętrznymi API (takimi jak CleanTalk lub StopForumSpam), jeśli zdecydujesz się je włączyć. Większość nowoczesnych środowisk hostingowych już je zapewnia.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny panel sterowania dla „Cart protection pro”, gdzie definiujesz, w jaki sposób moduł wykrywa i reaguje na podejrzaną aktywność koszyka.

#### Ustawienia ogólne

-   **Włączony**:

    -   **Co robi to ustawienie:** Jest to główny przełącznik modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Moduł aktywnie monitoruje aktywność koszyka i stosuje wybrane reguły ochrony.
        -   *Gdy wyłączony:* Moduł jest nieaktywny i nie będzie chronił Twojego sklepu przed atakami fałszywych koszyków.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Zawsze utrzymuj to włączone, aby zapewnić ochronę Twojego sklepu. Wyłącz tylko w celu rozwiązywania problemów lub konserwacji.
-   **Typ ochrony**:

    -   **Co robi to ustawienie:** Określa metodę, której moduł używa do identyfikacji i blokowania podejrzanej aktywności.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na „Adres IP”:* Moduł śledzi próby koszyka na podstawie adresu IP odwiedzającego. Jeśli adres IP przekroczy dozwoloną liczbę prób, zostanie zablokowany.
        -   *Gdy ustawione na „Cookie”:* Moduł śledzi próby koszyka za pomocą pliku cookie przeglądarki. Jeśli przeglądarka (zidentyfikowana przez plik cookie) przekroczy liczbę prób, zostanie zablokowana. Jest to mniej niezawodne, ponieważ pliki cookie mogą zostać wyczyszczone.
        -   *Gdy ustawione na „Adres IP + Cookie”:* Łączy obie metody dla silniejszej ochrony. Adres IP lub plik cookie przekraczający limity wywoła blokadę.
        -   *Gdy ustawione na „CleanTalk”:* Używa zewnętrznej usługi anty-spamowej CleanTalk do weryfikacji żądań. Wymaga klucza API CleanTalk.
        -   *Gdy ustawione na „StopForumSpam”:* Używa zewnętrznej bazy danych StopForumSpam do sprawdzenia, czy adres IP jest znany z wysyłania spamu. Wymaga klucza StopForumSpam.
    -   **Zalecana wartość:** „Adres IP + Cookie” dla solidnej lokalnej ochrony, lub „CleanTalk” / „StopForumSpam”, jeśli masz konta w tych usługach do zaawansowanych zewnętrznych kontroli.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli doświadczasz dużej liczby fałszywych koszyków, zacznij od „Adres IP + Cookie”. Jeśli problem się utrzymuje lub chcesz bardziej zaawansowanych kontroli, rozważ integrację z CleanTalk lub StopForumSpam.
-   **Ramy czasowe**:

    -   **Co robi to ustawienie:** Definiuje czas trwania (w minutach), w którym moduł zlicza próby koszyka z jednego źródła (IP lub pliku cookie).
    -   **Efekt zmiany tego ustawienia:**
        -   *Krótsze ramy czasowe (np. 5 minut):* Bardziej agresywna ochrona. Użytkownik/bot zostanie zablokowany szybciej, jeśli wykona wiele prób w krótkim czasie.
        -   *Dłuższe ramy czasowe (np. 60 minut):* Mniej agresywne. Pozwala na więcej prób w dłuższym okresie przed zablokowaniem.
    -   **Zalecana wartość:** 10 minut
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli boty szybko tworzą koszyki, krótsze ramy czasowe szybciej je złapią. Jeśli okaże się, że legalni użytkownicy są blokowani (rzadko), możesz nieco zwiększyć tę wartość.
-   **Liczba prób**:

    -   **Co robi to ustawienie:** Ustawia maksymalną liczbę dodanych produktów do koszyka dozwoloną z jednego źródła (IP lub pliku cookie) w ramach zdefiniowanych „Ram czasowych” przed wywołaniem blokady.
    -   **Efekt zmiany tego ustawienia:**
        -   *Niższa liczba (np. 3):* Bardzo agresywna. Użytkownik/bot zostanie zablokowany po zaledwie kilku dodaniach do koszyka.
        -   *Wyższa liczba (np. 10):* Mniej agresywna. Pozwala na więcej dodanych produktów do koszyka przed zablokowaniem.
    -   **Zalecana wartość:** 5
    -   **Scenariusz / przykład dla sprzedawcy:** Normalny klient rzadko dodaje więcej niż 5 produktów do koszyka w ciągu 10 minut. Boty jednak często próbują dodać dziesiątki lub setki. Ustawienie tej wartości na 5 pomaga w rozróżnieniu.
-   **Tytuł e-maila do sprzedawcy**:

    -   **Co robi to ustawienie:** Określa temat wiadomości e-mail wysyłanej do Ciebie (sprzedawcy) po zablokowaniu koszyka.
    -   **Efekt zmiany tego ustawienia:** Zmienia temat otrzymywanych e-maili z alertami.
    -   **Zalecana wartość:** „Cart Protection Pro - Alert o zablokowaniu!”
    -   **Scenariusz / przykład dla sprzedawcy:** Dostosuj to, aby alerty były łatwo rozpoznawalne w Twojej skrzynce odbiorczej, np. „PILNE: Bot zablokowany w [Nazwa Twojego sklepu]”.
-   **Logi**:

    -   **Co robi to ustawienie:** Kontroluje, czy moduł rejestruje szczegóły prób koszyka i blokad w Twojej bazie danych PrestaShop.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł przechowuje historię wszystkich prób i blokad, którą możesz przeglądać w sekcjach „Próby” i „Blokady” modułu. Jest to kluczowe do monitorowania i zrozumienia ataków.
        -   *Gdy wyłączone:* Nie są przechowywane żadne logi, co utrudnia śledzenie lub rozwiązywanie problemów.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Zawsze utrzymuj włączone logi. Dostarczają one cennych informacji o typach i częstotliwości ataków, z którymi boryka się Twój sklep, pomagając w dopracowaniu ustawień.

#### Integracja z CleanTalk

-   **Włącz darmowe wsparcie CleanTalk**:

    -   **Co robi to ustawienie:** Włącza integrację z usługą anty-spamową CleanTalk do sprawdzania spamu w czasie rzeczywistym. CleanTalk oferuje darmowy plan dla podstawowych kontroli.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł będzie wysyłał żądania do CleanTalk w celu weryfikacji, czy adres IP lub e-mail (jeśli dostępny) jest znany z wysyłania spamu przed zezwoleniem na dodanie produktów do koszyka.
        -   *Gdy wyłączone:* Kontrole CleanTalk nie są wykonywane.
    -   **Zalecana wartość:** NIE (chyba że masz konto CleanTalk i klucz API)
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli już używasz CleanTalk do innej ochrony przed spamem (np. komentarze, rejestracje) lub chcesz dodatkowej warstwy zewnętrznej weryfikacji, włącz to.
-   **Włącz płatne wsparcie CleanTalk**:

    -   **Co robi to ustawienie:** Włącza integrację z usługą anty-spamową CleanTalk, w szczególności dla funkcji dostępnych z płatną subskrypcją CleanTalk.
    -   **Efekt zmiany tego ustawienia:** Podobnie jak w przypadku darmowego wsparcia, ale potencjalnie z bardziej zaawansowanymi kontrolami, jeśli Twój plan CleanTalk na to pozwala.
    -   **Zalecana wartość:** NIE (chyba że masz płatne konto CleanTalk i klucz API)
    -   **Scenariusz / przykład dla sprzedawcy:** Wybierz to, jeśli masz płatną subskrypcję CleanTalk i chcesz wykorzystać jej pełne możliwości do ochrony koszyka.
-   **Klucz API CleanTalk**:

    -   **Co robi to ustawienie:** Jest to unikalny klucz dostarczony przez CleanTalk, który uwierzytelnia Twój sklep w ich usłudze.
    -   **Efekt zmiany tego ustawienia:** Bez ważnego klucza API integracja CleanTalk nie będzie działać, nawet jeśli jest włączona.
    -   **Zalecana wartość:** Twój rzeczywisty klucz API CleanTalk (pozostaw puste, jeśli nie używasz CleanTalk).
    -   **Scenariusz / przykład dla sprzedawcy:** Po zarejestrowaniu się w CleanTalk otrzymasz klucz API. Wprowadź go tutaj, aby aktywować ich usługę.

#### Integracja ze StopForumSpam

-   **Włącz wsparcie StopForumSpam**:

    -   **Co robi to ustawienie:** Włącza integrację z bazą danych StopForumSpam, która zawiera listy adresów IP, e-maili i nazw użytkowników znanych z wysyłania spamu na forach i stronach internetowych.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł będzie wysyłał zapytania do StopForumSpam, aby sprawdzić, czy adres IP odwiedzającego jest wymieniony jako znany spamer.
        -   *Gdy wyłączone:* Kontrole StopForumSpam nie są wykonywane.
    -   **Zalecana wartość:** NIE (chyba że masz klucz StopForumSpam)
    -   **Scenariusz / przykład dla sprzedawcy:** Jest to dobra dodatkowa warstwa ochrony, jeśli chcesz blokować adresy IP, które są globalnie rozpoznawane jako spamery, nawet jeśli jeszcze nie przekroczyły Twoich lokalnych limitów koszyka.
-   **Klucz StopForumSpam**:

    -   **Co robi to ustawienie:** Jest to unikalny klucz dostarczony przez StopForumSpam, który uwierzytelnia Twój sklep w ich usłudze.
    -   **Efekt zmiany tego ustawienia:** Bez ważnego klucza integracja StopForumSpam nie będzie działać, nawet jeśli jest włączona.
    -   **Zalecana wartość:** Twój rzeczywisty klucz API StopForumSpam (pozostaw puste, jeśli nie używasz StopForumSpam).
    -   **Scenariusz / przykład dla sprzedawcy:** Po zarejestrowaniu się w StopForumSpam otrzymasz klucz API. Wprowadź go tutaj, aby aktywować ich usługę.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolera

#### 2.2.1 Cart Protection Pro > Próby (Panel administracyjny > Moduły > Cart Protection Pro > Próby)

-   **Nazwa ekranu i lokalizacja w menu:** Ten ekran można znaleźć, przechodząc do **Moduły > Menedżer modułów**, a następnie klikając „Konfiguruj” przy „Cart protection pro”, a następnie wybierając zakładkę „Próby” (lub podobny element menu, jeśli moduł dodaje własne menu najwyższego poziomu).
-   **Dostępne akcje i ustawienia:** Ten ekran wyświetla listę (widok siatki) wszystkich zarejestrowanych prób koszyka, które wywołały logowanie modułu. Pokazuje szczegóły takie jak:
    -   **Adres IP:** Adres IP odwiedzającego.
    -   **ID pliku cookie:** Unikalny identyfikator pliku cookie (jeśli włączona jest ochrona „Cookie”).
    -   **Próby:** Liczba dodanych produktów do koszyka przez to źródło w skonfigurowanych ramach czasowych.
    -   **Sygnatura czasowa:** Kiedy próba została zarejestrowana.
    -   **Status:** Czy doprowadziło to do zablokowania, czy była to tylko próba.
-   **Efekt zmian:** Jest to dziennik tylko do odczytu. Nie można bezpośrednio modyfikować prób tutaj. Jego celem jest zapewnienie przejrzystości i danych, abyś mógł zrozumieć potencjalne ataki. Zazwyczaj możesz filtrować i sortować listę, aby analizować wzorce.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie sprawdzaj ten dziennik, zwłaszcza jeśli podejrzewasz aktywność botów. Szukaj wzorców:
    -   Wiele prób z tego samego adresu IP lub pliku cookie.
    -   Próby skoncentrowane w krótkim okresie.
    -   Nietypowe zakresy adresów IP lub lokalizacje geograficzne.
    Te dane pomogą Ci dopracować ustawienia „Ram czasowych” i „Liczby prób”.

#### 2.2.2 Cart Protection Pro > Blokady (Panel administracyjny > Moduły > Cart Protection Pro > Blokady)

-   **Nazwa ekranu i lokalizacja w menu:** Podobnie jak ekran Prób, ten jest dostępny poprzez **Moduły > Menedżer modułów > Konfiguruj „Cart protection pro” > Blokady** (zakładka/element menu).
-   **Dostępne akcje i ustawienia:** Ten ekran wyświetla listę (widok siatki) wszystkich adresów IP lub identyfikatorów plików cookie, które zostały zablokowane przez moduł. Zazwyczaj pokazuje:
    -   **Adres IP:** Zablokowany adres IP.
    -   **ID pliku cookie:** Zablokowany plik cookie (jeśli dotyczy).
    -   **Powód:** Dlaczego nastąpiła blokada (np. „Zbyt wiele prób”).
    -   **Czas rozpoczęcia/zakończenia blokady:** Kiedy blokada została zainicjowana i czy jest tymczasowa.
    -   **Akcje:** Często zawiera opcje ręcznego „Odblokowania” wpisu.
-   **Efekt zmian:**
    -   *Odblokowanie wpisu:* Usuwa blokadę dla tego konkretnego adresu IP lub pliku cookie, umożliwiając im ponowny dostęp do funkcji koszyka. Używaj ostrożnie!
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    -   Okresowo przeglądaj listę blokad. Jeśli zauważysz, że legalny adres IP (np. Twój własny lub znanego partnera) został przypadkowo zablokowany, możesz go tutaj odblokować.
    -   Szukaj powtarzających się adresów IP lub wzorców w blokadach, co może wskazywać na uporczywe ataki.
    -   Ten ekran jest kluczowy do zapewnienia, że moduł skutecznie blokuje złośliwy ruch bez przypadkowego wpływania na prawdziwych klientów.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włączony | TAK | Główny przełącznik funkcjonalności modułu. |
| Konfiguracja modułu | Typ ochrony | Adres IP + Cookie | Metoda identyfikacji i blokowania podejrzanej aktywności (IP, Cookie, oba, CleanTalk, StopForumSpam). |
| Konfiguracja modułu | Ramy czasowe | 10 minut | Czas trwania (minuty) zliczania prób koszyka. |
| Konfiguracja modułu | Liczba prób | 5 | Maksymalna liczba dodanych produktów do koszyka w ramach czasowych przed blokadą. |
| Konfiguracja modułu | Tytuł e-maila do sprzedawcy | Cart Protection Pro - Alert o zablokowaniu! | Temat e-maili z powiadomieniami dla sprzedawcy. |
| Konfiguracja modułu | Logi | TAK | Włącza/wyłącza logowanie prób i blokad. |
| Konfiguracja modułu | Włącz darmowe wsparcie CleanTalk | NIE | Aktywuje darmowe kontrole anty-spamowe CleanTalk. |
| Konfiguracja modułu | Włącz płatne wsparcie CleanTalk | NIE | Aktywuje płatne kontrole anty-spamowe CleanTalk. |
| Konfiguracja modułu | Klucz API CleanTalk | (puste) | Twój unikalny klucz API CleanTalk. |
| Konfiguracja modułu | Włącz wsparcie StopForumSpam | NIE | Aktywuje kontrole bazy danych IP StopForumSpam. |
| Konfiguracja modułu | Klucz StopForumSpam | (puste) | Twój unikalny klucz API StopForumSpam. |
| AdminCproAttempts | Widok siatki / zarządzania | N/A | Wyświetla dziennik wszystkich prób koszyka. |
| AdminCproBans | Widok siatki / zarządzania | N/A | Wyświetla listę wszystkich zablokowanych adresów IP/plików cookie, z opcją odblokowania. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci skarżą się, że nie mogą dodawać produktów do koszyka, ale ja nie widzę żadnych blokad.**
O1: Najpierw sprawdź, czy moduł „Cart protection pro” jest „Włączony” w jego konfiguracji. Jeśli tak, przejdź do sekcji „Blokady” w konfiguracji modułu. Sprawdź, czy są tam wymienione jakieś legalne adresy IP klientów. Jeśli tak, być może ustawiłeś „Liczbę prób” lub „Ramy czasowe” zbyt agresywnie. Spróbuj nieznacznie zwiększyć „Liczbę prób” (np. z 3 do 5 lub 7) lub wydłużyć „Ramy czasowe” (np. z 5 do 10-15 minut). Upewnij się również, że Twój szablon lub inne moduły nie zakłócają procesu koszyka.

**P2: Skonfigurowałem CleanTalk/StopForumSpam, ale wydaje się, że nie działa.**
O2: Sprawdź następujące elementy:
1.  Upewnij się, że „Włącz wsparcie CleanTalk/StopForumSpam” jest włączone.
2.  Zweryfikuj, czy Twój „Klucz API CleanTalk” lub „Klucz StopForumSpam” jest wprowadzony poprawnie i jest aktywny w odpowiedniej usłudze. Nawet pojedyncza literówka uniemożliwi jego działanie.
3.  Potwierdź, że Twoje środowisko hostingowe zezwala na wychodzące żądania cURL, które są niezbędne do komunikacji z tymi zewnętrznymi usługami. Twój host może to potwierdzić.
4.  Sprawdź logi „Prób” i „Blokad” modułu pod kątem wszelkich wpisów wskazujących na blokadę przez te usługi.

**P3: Mój sklep nadal otrzymuje wiele fałszywych koszyków, nawet z włączonym modułem.**
O3: Może to wskazywać na zaawansowanego bota lub na to, że Twoje ustawienia nie są wystarczająco agresywne.
1.  **Przejrzyj swoje ustawienia:** Spróbuj zmniejszyć „Liczbę prób” (np. z 5 do 3) i/lub skrócić „Ramy czasowe” (np. z 10 do 5 minut).
2.  **Włącz usługi zewnętrzne:** Jeśli jeszcze tego nie zrobiłeś, rozważ włączenie i skonfigurowanie CleanTalk lub StopForumSpam dla dodatkowej warstwy ochrony.
3.  **Sprawdź konflikty:** Tymczasowo wyłącz inne moduły bezpieczeństwa lub buforowania, aby sprawdzić, czy nie ma konfliktu.
4.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna Smarty PrestaShop może uniemożliwić natychmiastowe zastosowanie nowych ustawień modułu. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.

**P4: Czy ten moduł spowolni mój sklep?**
O4: Moduł został zaprojektowany tak, aby był lekki. Podstawowe kontrole (IP/Cookie) są bardzo szybkie. Jeśli włączysz usługi zewnętrzne, takie jak CleanTalk lub StopForumSpam, nastąpi niewielkie opóźnienie, ponieważ Twój serwer komunikuje się z ich API. Jednak te usługi są zoptymalizowane pod kątem szybkości, a wpływ jest zazwyczaj znikomy. Korzyść z zapobiegania przeciążeniu serwera przez fałszywe koszyki znacznie przewyższa minimalny czas przetwarzania.

**P5: Jak przetłumaczyć tytuł e-maila lub inne teksty modułu?**
O5: W przypadku „Tytułu e-maila do sprzedawcy” możesz po prostu zmienić tekst bezpośrednio w konfiguracji modułu. W przypadku innych tekstów modułu (jeśli byłyby widoczne dla klientów, co w przypadku tego modułu zazwyczaj nie ma miejsca), zazwyczaj należy przejść do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop. Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój szablon, a następnie wybierz „Cart protection pro”, aby znaleźć i edytować tłumaczone ciągi znaków.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu „Cart protection pro”, przeznaczony dla programistów i webmasterów, którzy muszą zrozumieć, debugować lub rozszerzać jego funkcjonalność.

### 4.1 Przegląd architektury

Moduł „Cart protection pro” wykorzystuje standardową architekturę modułów PrestaShop, głównie wykorzystując hooki do swojej podstawowej funkcjonalności i dedykowane kontrolery administracyjne do zarządzania zapleczem. Integruje zewnętrzne usługi anty-spamowe (CleanTalk, StopForumSpam) za pośrednictwem żądań cURL. Logika modułu jest hermetyzowana w jego głównej klasie i klasach pomocniczych, a konfiguracja jest przechowywana w `ps_configuration`, a logi w niestandardowych tabelach bazy danych.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front Office

Ten moduł nie definiuje jawnie niestandardowych kontrolerów front-office. Jego logika front-office jest głównie wykonywana za pośrednictwem hooków w głównym pliku modułu `cpro.php`, przechwytując akcje koszyka, zanim zostaną w pełni przetworzone.

#### Kontrolery administracyjne Back Office

Te kontrolery zarządzają dedykowanymi ekranami administracyjnymi modułu, zapewniając widoki siatki dla prób i blokad.

-   `cpro/controllers/admin/AdminCproAttempts.php`

    -   **Nazwa klasy i klasa nadrzędna**: `AdminCproAttemptsController` rozszerza `ModuleAdminController`.
    -   **Odpowiedzialność**: Zarządza wyświetlaniem i interakcją dla dziennika „Prób” w Panelu administracyjnym PrestaShop. Pobiera dane z tabeli bazy danych `cattempt` i renderuje je w formacie listy, umożliwiając administratorowi przeglądanie wszystkich zarejestrowanych prób koszyka. Nie pozwala na bezpośrednią modyfikację prób, działając jako przeglądarka dziennika tylko do odczytu.
-   `cpro/controllers/admin/AdminCproBans.php`

    -   **Nazwa klasy i klasa nadrzędna**: `AdminCproBansController` rozszerza `ModuleAdminController`.
    -   **Odpowiedzialność**: Zarządza wyświetlaniem i interakcją dla listy „Blokad” w Panelu administracyjnym PrestaShop. Pobiera dane z tabeli bazy danych `cban` i prezentuje je w formie listy. Ten kontroler obsługuje również akcje takie jak „Odblokuj”, umożliwiając administratorowi usunięcie określonego adresu IP lub pliku cookie z listy blokad.
-   `cpro/controllers/admin/index.php`

    -   **Nazwa klasy i klasa nadrzędna**: Ten plik zazwyczaj służy jako środek bezpieczeństwa w PrestaShop, zawierając `die('No direct script access');` w celu zapobiegania bezpośredniemu dostępowi do katalogu. Nie zawiera funkcjonalnej klasy kontrolera.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Dossier modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Główna logika obsługi prób i blokad, w tym interakcje z bazą danych, jest prawdopodobnie zarządzana bezpośrednio w głównym pliku modułu `cpro.php` lub poprzez bezpośrednie wywołania `Db::getInstance()`.

### 4.4 Zasoby JavaScript (`views/js/`)

Dossier modułu wskazuje brak niestandardowych plików JavaScript. Wszelkie dynamiczne zachowania w panelu administracyjnym są prawdopodobnie obsługiwane przez podstawowy JS PrestaShop lub skrypty inline w szablonach.

### 4.5 Arkusze stylów CSS (`views/css/`)

Dossier modułu wskazuje brak niestandardowych plików CSS. Stylizacja ekranów panelu administracyjnego będzie opierać się na domyślnym motywie administracyjnym PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `cpro/views/templates/admin/main.tpl`
        -   **Cel**: Ten szablon jest prawdopodobnie używany dla głównej strony konfiguracji modułu, renderowanej przez metodę `getContent()` w `cpro.php`. Zawiera strukturę HTML dla wszystkich ustawień opisanych w Sekcji 4.1, w tym pól formularza dla „Typu ochrony”, „Ram czasowych”, „Liczby prób”, kluczy API i przełącznika „Włączony”. Może również zawierać zakładki nawigacyjne lub linki do kontrolerów `AdminCproAttempts` i `AdminCproBans`.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_cattempt`: Przechowuje logi prób koszyka.
        -   `id_cattempt` (Klucz główny)
        -   `ip_address` (VARCHAR): Adres IP odwiedzającego.
        -   `cookie_id` (VARCHAR): Unikalny identyfikator z pliku cookie przeglądarki.
        -   `attempts` (INT): Liczba dodanych produktów do koszyka.
        -   `date_add` (DATETIME): Sygnatura czasowa próby.
        -   `status` (TINYINT): Status, np. 0 dla próby, 1 dla zablokowanego.
    -   `ps_cban`: Przechowuje rekordy zablokowanych adresów IP/plików cookie.
        -   `id_cban` (Klucz główny)
        -   `ip_address` (VARCHAR): Zablokowany adres IP.
        -   `cookie_id` (VARCHAR): Zablokowany identyfikator pliku cookie.
        -   `reason` (TEXT): Powód blokady (np. „Zbyt wiele prób”).
        -   `date_add` (DATETIME): Kiedy blokada została zainicjowana.
        -   `date_expire` (DATETIME): Jeśli blokada jest tymczasowa.
    -   **Rekordy konfiguracji (w `ps_configuration`)**:
        -   `CPRO_PTYPE_5`: Ustawienie typu ochrony (np. IP, Cookie, CleanTalk).
        -   `CPRO_CTALK_APIKEY`: Klucz API CleanTalk.
        -   `CPRO_CTALK`: Włączone/wyłączone darmowe wsparcie CleanTalk.
        -   `CPRO_CTALK_PAID`: Włączone/wyłączone płatne wsparcie CleanTalk.
        -   `CPRO_ATMPT`: Dozwolona liczba prób.
        -   `CPRO_TIME`: Ramy czasowe w minutach.
        -   `CPRO_PTYPE_1`, `CPRO_PTYPE_2`, `CPRO_PTYPE_3`, `CPRO_PTYPE_4`: Wewnętrzne flagi dla typów ochrony.
        -   `CPRO_SFS`: Włączone/wyłączone wsparcie StopForumSpam.
        -   `CPRO_SFS_KEY`: Klucz API StopForumSpam.
        -   `CPRO_MTITLE`: Tytuł e-maila dla powiadomień sprzedawcy.
        -   `CPRO_LOGS`: Włączone/wyłączone logowanie.
        -   `mypresta_updates`, `update_`, `updatev_`: Wewnętrzne klucze do aktualizacji modułu.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionObjectCartAddAfter` | Po dodaniu/zaktualizowaniu obiektu koszyka w bazie danych. | Potencjalnie używane do logowania udanych dodanych produktów do koszyka lub przetwarzania po zapisaniu koszyka. |
| `actionCartSave` | Po zapisaniu koszyka (wstawieniu lub zaktualizowaniu). | Podobnie jak `actionObjectCartAddAfter`, używane do monitorowania lub logowania zmian w koszyku. |
| `actionFrontControllerInitBefore` | Przed inicjalizacją kontrolera front-office. | Wczesny punkt przechwytywania do sprawdzania zablokowanych adresów IP/plików cookie przed renderowaniem jakiejkolwiek zawartości strony, potencjalnie przekierowując lub wyświetlając komunikat o blokadzie. |
| `actionObjectCartAddBefore` | Przed dodaniem/zaktualizowaniem obiektu koszyka w bazie danych. | **KRYTYCZNE**: Jest to główny hook do przechwytywania i walidacji dodanych produktów do koszyka. Moduł będzie wykonywał swoje kontrole (IP, cookie, CleanTalk, StopForumSpam) tutaj i może zapobiec dodaniu produktu do koszyka, jeśli limity zostaną przekroczone lub zostanie wykryta blokada. |
| `displayHeader` | W sekcji `<head>` stron front-office. | Może być używane do wstrzykiwania niezbędnego JavaScriptu (choć nie wykryto) lub CSS, lub do ustawiania plików cookie do śledzenia. |
| `actionDispatcherBefore` | Przed przetworzeniem żądania przez dispatcher. | Kolejny wczesny punkt przechwytywania, podobny do `actionFrontControllerInitBefore`, umożliwiający modułowi wykonywanie kontroli i potencjalne blokowanie żądań, zanim dotrą do określonego kontrolera. |

### 4.8 Integracje z zewnętrznymi API

-   **CleanTalk**: Używa cURL do wysyłania adresów IP i potencjalnie innych danych do API CleanTalk w celu weryfikacji spamu.
-   **StopForumSpam**: Używa cURL do wysyłania zapytań do bazy danych StopForumSpam z adresami IP w celu sprawdzenia znanych spamerów.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Cart protection pro”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu). Nasz zespół jest zaangażowany w zapewnienie optymalnego funkcjonowania modułu i bezpieczeństwa Twojego sklepu.
