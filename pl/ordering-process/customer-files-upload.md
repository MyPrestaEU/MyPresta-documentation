---
title: "Przesyłanie plików przez klienta - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop „Przesyłanie plików przez klienta” od MyPresta.eu."
sidebar:
  label: "Przesyłanie plików przez klienta - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Customer Files Upload na MyPresta.eu](https://mypresta.eu/modules/ordering-process/customer-files-upload.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/customer-files-upload/)
>
> ---


# Przesyłanie plików przez klienta

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i są wystarczające dla tego modułu. Upewnij się, że Twój serwer ma wystarczającą ilość miejsca na dysku do przechowywania przesłanych plików.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu, dostępny po instalacji lub po kliknięciu „Konfiguruj” w Menedżerze modułów.

- **Włącz moduł:**

  - **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji funkcjonalności modułu w całym Twoim sklepie.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Wszystkie funkcje przesyłania plików, zarządzanie plikami klienta i narzędzia panelu administracyjnego stają się aktywne.
    - *Po wyłączeniu:* Funkcje modułu są całkowicie wyłączone, a żadne formularze przesyłania ani sekcje „Moje pliki” nie będą się pojawiać.
  - **Zalecana wartość:** TAK
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli konfigurujesz moduł po raz pierwszy lub wykonujesz konserwację, możesz go tymczasowo wyłączyć. W przeciwnym razie pozostaw go włączonym, aby oferować usługę przesyłania plików.
- **Zezwól na przesyłanie na stronie produktu:**

  - **Co robi to ustawienie:** Kontroluje, czy klienci mogą przesyłać pliki bezpośrednio ze strony produktu.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Formularz przesyłania pojawi się na stronach produktów, umożliwiając klientom dołączanie plików przed dodaniem produktu do koszyka.
    - *Po wyłączeniu:* Żaden formularz przesyłania nie będzie widoczny na stronach produktów.
  - **Zalecana wartość:** TAK (jeśli Twoje produkty wymagają plików personalizacyjnych przed zakupem)
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz niestandardowe kubki z nadrukiem, włączenie tej opcji pozwala klientom przesłać swoje zdjęcie bezpośrednio na stronie produktu kubka.
- **Zezwól na przesyłanie na stronie koszyka:**

  - **Co robi to ustawienie:** Określa, czy obszar przesyłania jest wyświetlany na stronie podsumowania koszyka.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Klienci mogą przesyłać ogólne pliki związane z całym koszykiem lub konkretnymi przedmiotami przed przejściem do kasy.
    - *Po wyłączeniu:* Żaden formularz przesyłania nie będzie widoczny na stronie koszyka.
  - **Zalecana wartość:** TAK (jeśli klienci mogą potrzebować podać ogólne instrukcje dotyczące zamówienia lub pliki dla wielu przedmiotów)
  - **Scenariusz / przykład dla sprzedawcy:** Klient zamawiający wiele niestandardowych przedmiotów może przesłać jeden dokument z ogólnymi instrukcjami lub przewodnikiem po marce dla całego zamówienia.
- **Zezwól na przesyłanie na stronie potwierdzenia zamówienia:**

  - **Co robi to ustawienie:** Kontroluje, czy klienci mogą przesyłać pliki natychmiast po złożeniu zamówienia, na ekranie potwierdzenia zamówienia.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Formularz przesyłania pojawia się na stronie „Potwierdzenie zamówienia”, umożliwiając klientom dołączanie plików do ich nowo złożonego zamówienia.
    - *Po wyłączeniu:* Żaden formularz przesyłania nie będzie widoczny na stronie potwierdzenia zamówienia.
  - **Zalecana wartość:** TAK (wysoce zalecane dla większości przypadków użycia)
  - **Scenariusz / przykład dla sprzedawcy:** Klient właśnie kupił niestandardowy baner. Może natychmiast przesłać swój plik projektu w wysokiej rozdzielczości na stronie potwierdzenia bez konieczności nawigowania gdzie indziej.
- **Zezwól na przesyłanie w koncie klienta (Moje pliki i Historia zamówień):**

  - **Co robi to ustawienie:** Włącza sekcję „Moje pliki” w koncie klienta i umożliwia przesyłanie na stronach szczegółów poszczególnych zamówień w ich historii.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Klienci otrzymują dedykowany obszar „Moje pliki” do zarządzania wszystkimi swoimi przesyłanymi plikami i mogą dodawać pliki do konkretnych przeszłych zamówień.
    - *Po wyłączeniu:* Klienci nie mogą zarządzać plikami ze swojego konta, a żadne opcje przesyłania nie pojawią się na stronach historii zamówień.
  - **Zalecana wartość:** TAK (zapewnia maksymalną elastyczność i kontrolę klienta)
  - **Scenariusz / przykład dla sprzedawcy:** Klient dzień później zdaje sobie sprawę, że zapomniał przesłać konkretny plik czcionki dla swojego niestandardowego zamówienia na koszulkę. Może zalogować się na swoje konto, przejść do zamówienia i przesłać go.
- **Maksymalny rozmiar pliku (MB):**

  - **Co robi to ustawienie:** Ustawia górny limit rozmiaru każdego pojedynczego pliku, który klient może przesłać.
  - **Efekt zmiany tego ustawienia:**
    - *Po ustawieniu wartości (np. 10):* Klienci nie będą mogli przesyłać plików większych niż 10 MB.
    - *Po ustawieniu na 0 lub puste:* Moduł zazwyczaj będzie odwoływał się do limitów przesyłania PHP na Twoim serwerze, które mogą być bardzo wysokie lub bardzo niskie.
  - **Zalecana wartość:** 5-20 MB (dostosuj w zależności od typowych typów plików; np. obrazy w wysokiej rozdzielczości mogą wymagać więcej).
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli oczekujesz, że klienci będą przesyłać zdjęcia w wysokiej rozdzielczości, możesz ustawić to na 20 MB. Jeśli potrzebne są tylko małe dokumenty, 5 MB może wystarczyć, aby zaoszczędzić miejsce na serwerze.
- **Dozwolone typy plików (rozdzielone przecinkami):**

  - **Co robi to ustawienie:** Określa, które rozszerzenia plików są dozwolone do przesłania.
  - **Efekt zmiany tego ustawienia:**
    - *Po ustawieniu na „jpg,png,pdf”:* Tylko pliki z tymi rozszerzeniami mogą być przesyłane. Każdy inny typ pliku zostanie odrzucony.
    - *Po pozostawieniu pustego:* Wszystkie typy plików mogą być dozwolone (niezalecane ze względów bezpieczeństwa).
  - **Zalecana wartość:** Uwzględnij tylko typy, których oczekujesz (np. `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt,zip`). Unikaj plików wykonywalnych.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli potrzebujesz tylko plików projektowych, możesz wymienić `ai,eps,svg,psd,pdf,jpg,png`. Jeśli potrzebujesz dokumentów, odpowiednie byłyby `doc,docx,pdf`.
- **Wymuś przesyłanie plików dla określonych produktów (ID produktów):**

  - **Co robi to ustawienie:** Pozwala uczynić przesyłanie plików obowiązkowym dla niektórych produktów. Wprowadź ID produktów oddzielone przecinkami.
  - **Efekt zmiany tego ustawienia:**
    - *Po wprowadzeniu ID produktów:* Jeśli klient spróbuje dodać jeden z tych produktów do koszyka lub przejść do kasy bez przesłania pliku, zostanie poproszony o to.
    - *Po pozostawieniu pustego:* Żadne produkty nie będą miały obowiązkowego przesyłania plików.
  - **Zalecana wartość:** Używaj tylko dla produktów, dla których plik jest absolutnie niezbędny do przetworzenia zamówienia.
  - **Scenariusz / przykład dla sprzedawcy:** Dla produktu „Niestandardowy projekt wizytówki” (ID 123) możesz wprowadzić `123`. Klient nie może dokończyć zakupu bez przesłania swojego logo lub briefu projektowego.
- **Powiadomienie e-mailowe do klienta o przesłaniu pliku:**

  - **Co robi to ustawienie:** Kontroluje, czy e-mail jest wysyłany do klienta po pomyślnym przesłaniu pliku.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Klient otrzymuje e-mail potwierdzający, że jego plik został odebrany.
    - *Po wyłączeniu:* Żadne powiadomienie e-mailowe nie jest wysyłane do klienta.
  - **Zalecana wartość:** TAK (poprawia zaufanie klienta i zapewnia potwierdzenie)
  - **Scenariusz / przykład dla sprzedawcy:** Klient przesyła zdjęcie do spersonalizowanego prezentu. E-mail potwierdza przesłanie, zapewniając go, że plik został poprawnie odebrany.
- **Powiadomienie e-mailowe do administratora o przesłaniu pliku:**

  - **Co robi to ustawienie:** Kontroluje, czy e-mail jest wysyłany do administratora(ów) sklepu, gdy klient przesyła plik.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu:* Administrator sklepu otrzymuje powiadomienie e-mailowe, informujące go o nowych plikach, które wymagają uwagi.
    - *Po wyłączeniu:* Żadne powiadomienie e-mailowe nie jest wysyłane do administratora.
  - **Zalecana wartość:** TAK (niezbędne do terminowego przetwarzania zamówień)
  - **Scenariusz / przykład dla sprzedawcy:** Klient przesyła plik projektu. Administrator otrzymuje e-mail, zachęcający go do sprawdzenia zamówienia i rozpoczęcia przetwarzania niestandardowego przedmiotu.
- **Wyświetl przycisk przesyłania w nagłówku/stopce/kolumnach:**

  - **Co robi to ustawienie:** Pozwala wybrać, gdzie ogólny przycisk lub link „Prześlij pliki” pojawia się w Twoim sklepie (np. w nagłówku, stopce lub bocznych kolumnach).
  - **Efekt zmiany tego ustawienia:**
    - *Po wybraniu haka:* Link lub przycisk pojawi się w tej lokalizacji, kierując klientów do ich sekcji „Moje pliki” lub ogólnej strony przesyłania.
    - *Po wybraniu „Brak”:* Żaden ogólny przycisk przesyłania nie będzie wyświetlany poza stronami produktów/koszyka/zamówień.
  - **Zalecana wartość:** Rozważ `displayHeader` lub `displayFooter` dla łatwego dostępu do „Moich plików”, jeśli oczekujesz częstych przesyłań.
  - **Scenariusz / przykład dla sprzedawcy:** Umieszczenie linku „Moje pliki” w stopce pozwala powracającym klientom szybko uzyskać dostęp do swoich przesłanych dokumentów i zarządzać nimi.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 Menedżer plików klienta (Panel administracyjny > Moduły > Przesyłanie plików przez klienta > Pliki klienta)

Ten ekran zapewnia scentralizowane miejsce dla Ciebie, właściciela sklepu, do przeglądania i zarządzania wszystkimi plikami przesłanymi przez Twoich klientów.

- **Nazwa ekranu i lokalizacja w menu:** Możesz to znaleźć, przechodząc do **Moduły > Menedżer modułów**, znajdując „Przesyłanie plików przez klienta” i klikając „Konfiguruj”. W konfiguracji modułu powinna znajdować się zakładka lub link o nazwie „Pliki klienta” lub „Zarządzaj plikami”. Alternatywnie, może pojawić się bezpośrednio pod menu „Moduły” jako „Pliki klienta”.
- **Dostępne akcje i ustawienia:**
  - **Tabela z listą plików:** Wyświetla listę wszystkich przesłanych plików, w tym szczegóły takie jak:
    - **Nazwa pliku:** Nazwa przesłanego pliku.
    - **Klient:** Nazwa klienta, który przesłał plik.
    - **ID zamówienia:** Jeśli plik jest powiązany z konkretnym zamówieniem.
    - **Produkt:** Jeśli plik jest powiązany z konkretnym produktem.
    - **Data przesłania:** Kiedy plik został przesłany.
    - **Rozmiar:** Rozmiar pliku.
    - **Akcje:** Zazwyczaj obejmuje opcje **Pobierz** plik, **Wyświetl szczegóły** lub **Usuń** plik.
  - **Filtrowanie i wyszukiwanie:** Zazwyczaj możesz filtrować pliki według klienta, ID zamówienia, produktu lub zakresu dat, aby szybko znaleźć konkretne przesłane pliki.
  - **Akcje masowe:** Opcje wyboru wielu plików i wykonywania akcji, takich jak masowe usuwanie.
- **Efekt zmian:**
  - **Pobieranie pliku:** Pobiera przesłany plik klienta na Twój komputer w celu przetworzenia.
  - **Usuwanie pliku:** Trwale usuwa plik z Twojego serwera i z sekcji „Moje pliki” klienta. Używaj z ostrożnością!
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie sprawdzaj tę sekcję pod kątem nowych przesłanych plików, zwłaszcza po otrzymaniu powiadomień e-mailowych od administratora. Pobieraj niezbędne pliki do realizacji zamówień, a także okresowo przeglądaj i usuwaj stare lub niepotrzebne pliki, aby zwolnić miejsce na serwerze.

#### 2.2.2 Integracja ze stroną szczegółów zamówienia (Panel administracyjny > Zamówienia > Zamówienia > Wyświetl zamówienie)

Moduł integruje się bezpośrednio z istniejącymi stronami szczegółów zamówień w PrestaShop.

- **Nazwa ekranu i lokalizacja w menu:** Gdy przeglądasz konkretne zamówienie w Panelu administracyjnym (np. **Zamówienia > Zamówienia**, a następnie kliknij „Wyświetl” obok zamówienia).
- **Dostępne akcje i ustawienia:**
  - Na stronie szczegółów zamówienia pojawi się nowa sekcja lub zakładka, specjalnie dla „Plików klienta” lub „Przesłanych plików”.
  - Ta sekcja wyświetli wszystkie pliki, które klient przesłał dla *tego konkretnego zamówienia*.
  - Zobaczysz nazwy plików, daty przesłania i opcje **Pobierz** każdy plik.
  - Może również istnieć opcja dla administratora, aby **Przesłać plik** w imieniu klienta lub do użytku wewnętrznego związanego z zamówieniem.
- **Efekt zmian:**
  - **Pobieranie plików stąd:** Pozwala szybko uzyskać dostęp do plików związanych z aktualnie przeglądanym zamówieniem, usprawniając przetwarzanie zamówień.
  - **Przesyłanie przez administratora:** Jeśli dostępne, pozwala dodawać wewnętrzne notatki lub pliki związane z zamówieniem bezpośrednio do listy plików zamówienia.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Podczas przetwarzania zamówienia, które wymaga plików klienta, przejdź do strony szczegółów zamówienia, znajdź sekcję „Pliki klienta” i pobierz wszystkie niezbędne dokumenty przed rozpoczęciem produkcji lub realizacji.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz moduł | TAK | Główny przełącznik funkcjonalności modułu. |
| | Zezwól na przesyłanie na stronie produktu | TAK (jeśli potrzebne) | Wyświetla formularz przesyłania na stronach produktów. |
| | Zezwól na przesyłanie na stronie koszyka | TAK (jeśli potrzebne) | Wyświetla formularz przesyłania na stronie koszyka. |
| | Zezwól na przesyłanie na stronie potwierdzenia zamówienia | TAK | Wyświetla formularz przesyłania po złożeniu zamówienia. |
| | Zezwól na przesyłanie w koncie klienta | TAK | Włącza „Moje pliki” i przesyłanie w historii zamówień. |
| | Maksymalny rozmiar pliku (MB) | 5-20 MB | Ogranicza rozmiar pojedynczego przesyłanego pliku. |
| | Dozwolone typy plików | `jpg,png,pdf,...` | Ogranicza rozszerzenia plików ze względów bezpieczeństwa/relewancji. |
| | Wymuś przesyłanie plików dla określonych produktów (ID) | Puste (używaj w razie potrzeby) | Uczynia przesyłanie obowiązkowym dla określonych produktów. |
| | Powiadomienie e-mailowe do klienta | TAK | Wysyła e-mail potwierdzający do klienta po przesłaniu. |
| | Powiadomienie e-mailowe do administratora | TAK | Wysyła powiadomienie e-mailowe do administratora o nowym przesłaniu. |
| | Wyświetl przycisk przesyłania w nagłówku/stopce/kolumnach | `displayFooter` (lub w razie potrzeby) | Umieszcza ogólny link „Prześlij pliki” w wybranym haku. |
| **Menedżer plików klienta** | Lista plików | N/A | Przeglądaj, filtruj, pobieraj i usuwaj wszystkie pliki klienta. |
| | Akcje masowe | N/A | Wykonuj akcje na wielu wybranych plikach. |
| **Strona szczegółów zamówienia** | Sekcja plików klienta | N/A | Przeglądaj i pobieraj pliki specyficzne dla bieżącego zamówienia. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci nie widzą formularzy przesyłania ani sekcji „Moje pliki”.**
O:

- **Sprawdź status modułu:** Upewnij się, że moduł jest włączony w **Moduły > Menedżer modułów**.
- **Sprawdź konfigurację:** Przejdź do strony konfiguracji modułu i sprawdź, czy „Włącz moduł” jest ustawione na TAK oraz czy określone miejsca przesyłania (Strona produktu, Koszyk, Konto klienta) są również włączone.
- **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe pojawienie się zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.
- **Kompatybilność z motywem:** Jeśli używasz bardzo spersonalizowanego motywu, może on nieprawidłowo łączyć się z punktami wyświetlania modułu. Skontaktuj się z pomocą techniczną MyPresta.eu lub swoim programistą.

**P2: Klienci otrzymują błąd podczas próby przesłania plików.**
O:

- **Sprawdź limit rozmiaru pliku:** Zweryfikuj „Maksymalny rozmiar pliku (MB)” w konfiguracji modułu. Plik klienta może być zbyt duży.
- **Sprawdź dozwolone typy plików:** Upewnij się, że typ pliku, który klient próbuje przesłać, znajduje się na liście „Dozwolone typy plików” (np. jeśli przesyła plik `.zip`, `zip` musi znajdować się na liście).
- **Limity serwera:** Twój host internetowy może mieć limity przesyłania PHP po stronie serwera (`upload_max_filesize`, `post_max_size`), które są niższe niż ustawienie modułu. Może być konieczne skontaktowanie się z hostem lub dostosowanie pliku `php.ini`.

**P3: Nie otrzymuję powiadomień e-mailowych, gdy klienci przesyłają pliki.**
O:

- **Sprawdź ustawienia powiadomień e-mailowych:** W konfiguracji modułu upewnij się, że „Powiadomienie e-mailowe do administratora o przesłaniu pliku” jest ustawione na TAK.
- **Ustawienia e-mailowe PrestaShop:** Zweryfikuj, czy ustawienia e-mailowe Twojego sklepu PrestaShop są poprawnie skonfigurowane i czy e-maile są wysyłane pomyślnie (**Zaawansowane > E-mail**). Wyślij stamtąd testowy e-mail.
- **Folder spamu:** Sprawdź folder spamu lub wiadomości-śmieci pod kątem powiadomień.
- **Serwer pocztowy:** Upewnij się, że funkcja poczty Twojego serwera działa poprawnie.

**P4: Jak przetłumaczyć tekst modułu na inne języki?**
O:

- Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
- Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz „Przesyłanie plików przez klienta” z rozwijanej listy modułów.
- Następnie możesz przetłumaczyć wszystkie widoczne ciągi znaków używane przez moduł.

**P5: Gdzie są przechowywane przesłane pliki na moim serwerze?**
O: Moduł zazwyczaj przechowuje pliki w dedykowanym folderze w Twojej instalacji PrestaShop, często nazwanym `upload` lub `orderfiles_uploads` w katalogu modułu lub ogólnym katalogu `upload`. Możesz uzyskać do nich dostęp za pomocą FTP/SFTP, ale zawsze najlepiej jest zarządzać nimi za pośrednictwem interfejsu Panelu administracyjnego, aby zachować integralność bazy danych.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Przesyłanie plików przez klienta” jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując zasady MVC. Rozszerza `Module` dla swojej podstawowej funkcjonalności i konfiguracji, używa `ModuleFrontController` do interakcji z front-office (przesyłanie, zarządzanie plikami) oraz `AdminController` do zarządzania back-office. Dane są przechowywane w systemie plików i potencjalnie łączone za pomocą `ps_configuration` dla ustawień. Moduł w dużym stopniu opiera się na systemie haków PrestaShop, aby wstrzykiwać swoją funkcjonalność w różne części sklepu.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

- `controllers/front/customerfiles.php`
  - **Nazwa klasy i klasa nadrzędna:** `CustomerfilesCustomerfilesModuleFrontController` rozszerza `ModuleFrontController`
  - **Odpowiedzialność:** Prawdopodobnie obsługuje główną stronę „Moje pliki” widoczną dla klienta, wyświetlając listę przesłanych plików i zapewniając opcje zarządzania. Pobiera pliki powiązane z zalogowanym klientem.
- `controllers/front/download.php`
  - **Nazwa klasy i klasa nadrzędna:** `DownloadCustomerfilesModuleFrontController` rozszerza `ModuleFrontController`
  - **Odpowiedzialność:** Zarządza bezpiecznymi pobieraniem plików. Przyjmuje ID pliku lub ścieżkę, weryfikuje uprawnienia klienta (jeśli dotyczy) i udostępnia plik przeglądarce, często wymuszając pobieranie.
- `controllers/front/filesmanager.php`
  - **Nazwa klasy i klasa nadrzędna:** `FilesmanagerCustomerfilesModuleFrontController` rozszerza `ModuleFrontController`
  - **Odpowiedzialność:** Może być ogólnym interfejsem zarządzania plikami, potencjalnie używanym do wywołań AJAX związanych z operacjami na plikach (np. usuwanie pliku z widoku klienta).
- `controllers/front/index.php`
  - **Nazwa klasy i klasa nadrzędna:** `IndexCustomerfilesModuleFrontController` rozszerza `ModuleFrontController`
  - **Odpowiedzialność:** Często jest to kontroler zastępczy lub przekierowujący. W niektórych modułach może służyć jako domyślny punkt wejścia lub obsługiwać podstawowe routowanie.
- `controllers/front/myfiles.php`
  - **Nazwa klasy i klasa nadrzędna:** `MyfilesCustomerfilesModuleFrontController` rozszerza `ModuleFrontController`
  - **Odpowiedzialność:** Podobnie jak `customerfiles.php`, ten kontroler prawdopodobnie obsługuje konkretną sekcję „Moje pliki” w koncie klienta, wyświetlając przesłane pliki i potencjalnie formularz przesyłania.
- `controllers/front/thumb.php`
  - **Nazwa klasy i klasa nadrzędna:** `ThumbCustomerfilesModuleFrontController` rozszerza `ModuleFrontController`
  - **Odpowiedzialność:** Generuje i udostępnia miniatury dla przesłanych plików graficznych, poprawiając wydajność i wyświetlanie na stronach z listą plików.
- `controllers/front/upload.php`
  - **Nazwa klasy i klasa nadrzędna:** `UploadCustomerfilesModuleFrontController` rozszerza `ModuleFrontController`
  - **Odpowiedzialność:** Główny moduł obsługi przesyłania. Odbiera przesłane pliki (za pośrednictwem AJAX lub standardowego przesyłania formularza), waliduje typ i rozmiar pliku, przenosi plik do wyznaczonego katalogu i zapisuje informacje o pliku w bazie danych.

#### Kontrolery administracyjne Back-Office

- `controllers/admin/customerFiles.php`
  - **Nazwa klasy i klasa nadrzędna:** `AdminCustomerFilesController` rozszerza `ModuleAdminController`
  - **Nazwa zakładki i zarządzana encja:** „Pliki klienta” (lub podobne). Ten kontroler zarządza głównym widokiem siatki wszystkich plików przesłanych przez klienta w Panelu administracyjnym. Zapewnia funkcjonalność listowania, filtrowania, przeglądania szczegółów, pobierania i usuwania plików.
  - **Powiązane klucze konfiguracyjne:** `PS_SHOP_EMAIL`, `PS_SHOP_NAME` (dla powiadomień e-mailowych), `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH` (prawdopodobnie związane z ustawieniami szablonów e-mailowych dla powiadomień klienta).
- `controllers/admin/index.php`
  - **Nazwa klasy i klasa nadrzędna:** `IndexCustomerfilesModuleAdminController` rozszerza `ModuleAdminController`
  - **Nazwa zakładki i zarządzana encja:** Podobnie jak `index.php` w front-office, może to być kontroler zastępczy lub przekierowujący dla sekcji administracyjnej modułu.

### 4.3 Główne klasy i modele (`classes/`)

Dostarczony spis nie wskazuje na żadne niestandardowe klasy w katalogu `classes/`. Sugeruje to, że moduł może używać `ObjectModel` bezpośrednio w głównym pliku modułu lub kontrolerach administracyjnych, lub jest to starsza struktura modułu, w której obsługa danych jest osadzona. Jeśli dane są przechowywane w niestandardowej tabeli, metoda `install()` głównego modułu definiowałaby jej schemat.

### 4.4 Zasoby JavaScript (`views/js/`)

- `js/jquery.form.js`
  - **Zakres:** Prawdopodobnie Front-office i Back-office.
  - **Wyjaśnienie:** Wtyczka jQuery do łatwego przesyłania formularzy za pośrednictwem AJAX, w tym przesyłania plików. Obsługuje złożoność `multipart/form-data` i zapewnia wywołania zwrotne postępu.
- `js/orders.js`
  - **Zakres:** Back-office (szczególnie strony szczegółów zamówienia).
  - **Wyjaśnienie:** Ten skrypt prawdopodobnie dodaje funkcjonalność do strony szczegółów zamówienia PrestaShop, taką jak wyświetlanie sekcji przesłanych plików, obsługa pobierania plików po stronie administratora lub potencjalnie umożliwianie administratorom przesyłania plików do zamówienia.
- `js/script-customers.js`
  - **Zakres:** Front-office (strony konta klienta).
  - **Wyjaśnienie:** Obsługuje logikę po stronie klienta dla sekcji „Moje pliki” w koncie klienta, w tym wyświetlanie list plików, zarządzanie akcjami usuwania i inicjowanie nowych przesyłań.
- `js/script.js`
  - **Zakres:** Front-office (ogólne, strony produktów, koszyka) i potencjalnie konfiguracja Back-office.
  - **Wyjaśnienie:** Ogólny skrypt dla modułu. Prawdopodobnie inicjalizuje formularze przesyłania, obsługuje walidację plików (rozmiar, typ) przed przesłaniem, wyświetla postęp przesyłania i zarządza interakcjami UI związanymi z przesyłaniem plików w różnych lokalizacjach front-office.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `css/ajaxuploader.css`
  - **Zakres:** Front-office.
  - **Wyjaśnienie:** Style dla interfejsu przesyłania plików opartego na AJAX, w tym paski postępu, strefy przeciągnij i upuść oraz elementy wejściowe plików.
- `css/backoffice.css`
  - **Zakres:** Back-office.
  - **Wyjaśnienie:** Specyficzne style dla stron administracyjnych modułu, takie jak siatka „Menedżera plików klienta”, formularze konfiguracji i integracja ze stroną szczegółów zamówienia.
- `css/orderfiles.css`
  - **Zakres:** Front-office.
  - **Wyjaśnienie:** Ogólne style dla komponentów front-office modułu, w tym list plików, przycisków i wiadomości wyświetlanych klientom.
- `css.css`
  - **Zakres:** Front-office.
  - **Wyjaśnienie:** Może być starszym lub ogólnym arkuszem stylów, potencjalnie zawierającym podstawowe style dla elementów wizualnych modułu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony haków (`views/templates/hook/`)

- `displayProductPageUploadFormSmall.tpl`: Renderuje kompaktowy formularz przesyłania na stronie produktu.
- `filesmanager-orderhistory.tpl`: Wyświetla menedżera plików/sekcję przesyłania na stronie szczegółów historii zamówień klienta.
- `force-redirect.tpl`: Szablon narzędziowy, prawdopodobnie do obsługi przekierowań po określonych akcjach lub do wyświetlania wiadomości przed przekierowaniem.
- `header.tpl`: Wstrzykiwany do `displayHeader`, zazwyczaj do ładowania zasobów CSS/JS lub metatagów wymaganych przez moduł.
- `my-account-17.tpl`: Renderuje link lub blok „Moje pliki” w panelu konta klienta dla PrestaShop 1.7.x i nowszych.
- `my-account.tpl`: Renderuje link lub blok „Moje pliki” w panelu konta klienta dla starszych wersji PrestaShop (1.5.x, 1.6.x).
- `orderConfirmation.tpl`: Wyświetla formularz przesyłania lub listę plików na stronie potwierdzenia zamówienia.
- `product-files-button.tpl`: Renderuje przycisk lub link na stronie produktu, który może otwierać modalne okno przesyłania lub przekierowywać do sekcji przesyłania.
- `product-files.tpl`: Wyświetla listę plików powiązanych z produktem lub formularz przesyłania na stronie produktu.
- `shopping-cart-force-files-alert.tpl`: Wyświetla alert w koszyku, jeśli brakuje obowiązkowych plików dla niektórych produktów.
- `shopping-cart-qty-infos-alert.tpl`: Potencjalnie związane z alertami dotyczącymi wymagań plików opartych na ilości w koszyku.
- `shopping-cart.tpl`: Wyświetla formularz przesyłania lub listę plików na stronie podsumowania koszyka.
- `tab.tpl`: Ogólny szablon zakładki, prawdopodobnie używany do wyświetlania zakładki „Pliki” na stronach produktów lub w koncie klienta.

#### Szablony administracyjne (`views/templates/admin/`)

- `admin.tpl`: Ogólny szablon administracyjny, prawdopodobnie dla głównej strony konfiguracji modułu lub pulpitu nawigacyjnego.
- `adminOrderDetailUpload.tpl`: Integruje sekcję przesyłania/zarządzania plikami ze stroną szczegółów zamówienia PrestaShop w Panelu administracyjnym.
- `boscript.tpl`: Zawiera JavaScript specyficzny dla Panelu administracyjnego, potencjalnie do inicjalizacji formularzy lub obsługi AJAX na stronach administracyjnych.
- `bulk-delete-files.tpl`: Szablon do potwierdzenia masowego usuwania lub interfejsu w menedżerze plików administracyjnych.
- `comments_cartfiles.tpl`: Wyświetla komentarze lub notatki związane z plikami przesłanymi dla konkretnego koszyka.
- `comments_orderfiles.tpl`: Wyświetla komentarze lub notatki związane z plikami przesłanymi dla konkretnego zamówienia.
- `comments_productfiles.tpl`: Wyświetla komentarze lub notatki związane z plikami przesłanymi dla konkretnego produktu.
- `customerfilesmanager.tpl`: Główny szablon dla widoku siatki „Menedżera plików klienta” w Panelu administracyjnym.
- `_configure/helpers/list/list_action_details.tpl`: Szablon dla przycisku akcji „szczegóły” w pomocniku listy.
- `_configure/helpers/list/list_content.tpl`: Szablon dla głównej zawartości pomocnika listy (np. wiersze listy plików).
- `_configure/prestashopbug/helpers/list/*.tpl`: Te szablony (`list.tpl`, `list_action_delete.tpl`, `list_action_details.tpl`, `list_content.tpl`, `list_footer.tpl`, `list_header.tpl`) sugerują niestandardową lub nadpisaną implementację pomocnika listy, prawdopodobnie w celu rozwiązania konkretnych potrzeb wyświetlania lub błędów w starszych wersjach PrestaShop.

#### Szablony Front-office (`views/templates/front/`)

- `access-denied.tpl`: Wyświetla komunikat, gdy klient próbuje uzyskać dostęp do pliku lub strony bez odpowiednich uprawnień.
- `customerfilesmanager.tpl`: Główny szablon dla strony „Moje pliki” klienta, wyświetlający przesłane pliki i opcje zarządzania.
- `filesmanager.tpl`: Ogólny szablon menedżera plików, potencjalnie używany do różnych scenariuszy listowania i przesyłania plików w front-office.
- `my-files.tpl`: Inny szablon dla sekcji „Moje pliki” klienta, prawdopodobnie podobny do `customerfilesmanager.tpl` lub używany w połączeniu.

### 4.7 Schemat bazy danych i mapa haków

- **Tabele bazy danych**:

  - Moduł prawdopodobnie tworzy co najmniej jedną niestandardową tabelę do przechowywania metadanych o przesłanych plikach. Typowa struktura tabeli to `ps_orderfiles` (lub podobna), zawierająca pola takie jak:
    - `id_order_file` (Klucz podstawowy)
    - `id_customer` (Klucz obcy do `ps_customer`)
    - `id_order` (Klucz obcy do `ps_order`, może być null)
    - `id_product` (Klucz obcy do `ps_product`, może być null)
    - `filename` (Oryginalna nazwa pliku)
    - `filepath` (Ścieżka do przechowywanego pliku na serwerze)
    - `filesize` (Rozmiar w bajtach)
    - `file_extension`
    - `date_add` (Sygnatura czasowa przesłania)
    - `comment` (Opcjonalny komentarz od klienta lub administratora)
  - Ustawienia konfiguracyjne są przechowywane w `ps_configuration` z kluczami takimi jak `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH` i innymi ustawieniami specyficznymi dla modułu.
- **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykiwanie CSS, JavaScript i potencjalnie metatagów dla modułu. |
| `displayProductAdditionalInfo` (lub podobny hak strony produktu) | Na stronie produktu, zazwyczaj poniżej opisu produktu lub przycisku dodaj do koszyka. | Wyświetlanie formularza przesyłania lub przycisku specyficznego dla produktu. |
| `displayShoppingCartFooter` (lub podobny hak strony koszyka) | Na stronie podsumowania koszyka. | Wyświetlanie formularza przesyłania lub listy plików dla całego koszyka. |
| `displayOrderConfirmation` | Na stronie potwierdzenia zamówienia po udanym zakupie. | Wyświetlanie formularza przesyłania po zakupie. |
| `displayCustomerAccount` | W panelu „Moje konto” klienta. | Dodawanie linku lub bloku do sekcji „Moje pliki”. |
| `displayMyAccountBlock` (PrestaShop 1.6.x) | W panelu „Moje konto” klienta. | Dodawanie linku lub bloku do sekcji „Moje pliki”. |
| `displayRightColumn` / `displayLeftColumn` | W bocznych kolumnach sklepu. | Wyświetlanie ogólnego przycisku/linku „Prześlij pliki”, jeśli skonfigurowano. |
| `displayFooter` | W stopce każdej strony. | Wyświetlanie ogólnego przycisku/linku „Prześlij pliki”, jeśli skonfigurowano. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Potencjalnie używane do łączenia przesłanych plików z nowo utworzonym ID zamówienia lub wyzwalania powiadomień administratora. |
| `actionProductUpdate` / `actionProductAdd` | Po zaktualizowaniu lub dodaniu produktu. | Może być używane do zarządzania wymaganiami plików specyficznymi dla produktu lub czyszczenia powiązanych plików. |
| `actionCustomerAccountAdd` | Po utworzeniu nowego konta klienta. | (Mniej prawdopodobne dla tego modułu, ale możliwe dla początkowej konfiguracji). |
| `actionAdminOrdersView` | Gdy administrator przegląda zamówienie w Panelu administracyjnym. | Wstrzykiwanie sekcji zarządzania plikami modułu na stronę szczegółów zamówienia. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Przesyłanie plików przez klienta”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie doskonałego funkcjonowania Twojego modułu i pomoc w maksymalizacji potencjału Twojego sklepu.
