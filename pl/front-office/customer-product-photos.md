---
title: "Zdjęcia produktów od klientów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Zdjęcia produktów od klientów” firmy MyPresta.eu."
sidebar:
  label: "Zdjęcia produktów od klientów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Customer product photos na MyPresta.eu](https://mypresta.eu/modules/front-office-features/customer-product-photos.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/customer-product-photos/)
>
> ---


# Zdjęcia produktów od klientów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Zdjęcia produktów od klientów”. Znajdziesz tutaj różnorodne ustawienia, które kontrolują zachowanie i wygląd modułu w Twoim sklepie.

#### Ustawienia ogólne

-   **Zezwolić na pliki JPEG?**
    -   **Co robi to ustawienie:** Określa, czy klienci mogą przesyłać obrazy w formacie JPEG.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klienci mogą przesyłać pliki `.jpg` lub `.jpeg`.
        -   *Gdy wyłączone:* Pliki JPEG zostaną odrzucone podczas przesyłania.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz/przykład dla sprzedawcy:** Większość zdjęć jest robiona w formacie JPEG. Włączenie tej opcji zapewnia maksymalną kompatybilność dla przesyłanych zdjęć klientów.
-   **Zezwolić na pliki GIF?**
    -   **Co robi to ustawienie:** Określa, czy klienci mogą przesyłać obrazy w formacie GIF.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klienci mogą przesyłać pliki `.gif`.
        -   *Gdy wyłączone:* Pliki GIF zostaną odrzucone podczas przesyłania.
    -   **Zalecana wartość:** TAK (chyba że masz konkretny powód, aby nie zezwalać na animowane obrazy)
    -   **Scenariusz/przykład dla sprzedawcy:** GIF-y mogą być przydatne do pokazywania krótkich animacji produktu, ale mogą być również większymi plikami. Włącz, jeśli chcesz je obsługiwać.
-   **Zezwolić na pliki PNG?**
    -   **Co robi to ustawienie:** Określa, czy klienci mogą przesyłać obrazy w formacie PNG.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klienci mogą przesyłać pliki `.png`.
        -   *Gdy wyłączone:* Pliki PNG zostaną odrzucone podczas przesyłania.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz/przykład dla sprzedawcy:** PNG są świetne do obrazów z przezroczystością lub ostrą grafiką. Jest to popularny format, więc włączenie go jest ogólnie dobrym pomysłem.
-   **Zezwolić na pliki BMP?**
    -   **Co robi to ustawienie:** Określa, czy klienci mogą przesyłać obrazy w formacie BMP.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klienci mogą przesyłać pliki `.bmp`.
        -   *Gdy wyłączone:* Pliki BMP zostaną odrzucone podczas przesyłania.
    -   **Zalecana wartość:** NIE (chyba że jest to specjalnie wymagane)
    -   **Scenariusz/przykład dla sprzedawcy:** Pliki BMP są zazwyczaj bardzo duże i nieskompresowane, co czyni je nieodpowiednimi do użytku w sieci. Wyłączenie tej opcji pomaga utrzymać wydajność galerii.
-   **Zezwolić niezalogowanym klientom na przesyłanie zdjęć?**
    -   **Co robi to ustawienie:** Kontroluje, czy odwiedzający, którzy nie są zalogowani na konto klienta, mogą przesyłać zdjęcia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Goście mogą przesyłać zdjęcia. Mogą zostać poproszeni o adres e-mail lub imię.
        -   *Gdy wyłączone:* Tylko zarejestrowani i zalogowani klienci mogą przesyłać zdjęcia.
    -   **Zalecana wartość:** TAK (jeśli chcesz maksymalnej generacji treści), NIE (jeśli chcesz powiązać treści z konkretnymi kontami klientów)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz zmaksymalizować treści generowane przez użytkowników, zezwolenie gościom jest korzystne. Jeśli chcesz śledzić, kto co przesyła i potencjalnie ich nagradzać, wymagaj logowania.
-   **Maksymalny rozmiar pliku (w MB)**
    -   **Co robi to ustawienie:** Ustawia górny limit rozmiaru pliku obrazu, który klient może przesłać.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na 5:* Klienci nie mogą przesyłać plików większych niż 5MB.
        -   *Gdy ustawione na 0:* Brak limitu (choć limity serwera PHP nadal będą obowiązywać).
    -   **Zalecana wartość:** 2-5 MB
    -   **Scenariusz/przykład dla sprzedawcy:** Rozsądny limit zapobiega przesyłaniu przez klientów nadmiernie dużych plików, które mogłyby spowolnić Twoją witrynę lub zużyć zbyt dużo miejsca na serwerze. 2-5MB jest zazwyczaj wystarczające dla wysokiej jakości obrazów internetowych.
-   **Wysokość miniatury (px)**
    -   **Co robi to ustawienie:** Definiuje wysokość generowanych miniatur dla galerii.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na 100:* Wszystkie miniatury będą miały 100 pikseli wysokości.
        -   *Gdy ustawione na 200:* Wszystkie miniatury będą miały 200 pikseli wysokości.
    -   **Zalecana wartość:** 150-250px (dostosuj do projektu swojego motywu)
    -   **Scenariusz/przykład dla sprzedawcy:** Spójne rozmiary miniatur zapewniają czysty i uporządkowany układ galerii. Dostosuj to, aby pasowało do estetyki Twojego motywu.
-   **Szerokość miniatury (px)**
    -   **Co robi to ustawienie:** Definiuje szerokość generowanych miniatur dla galerii.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na 100:* Wszystkie miniatury będą miały 100 pikseli szerokości.
        -   *Gdy ustawione na 200:* Wszystkie miniatury będą miały 200 pikseli szerokości.
    -   **Zalecana wartość:** 150-250px (dostosuj do projektu swojego motywu)
    -   **Scenariusz/przykład dla sprzedawcy:** Podobnie jak wysokość, spójna szerokość pomaga utrzymać atrakcyjną wizualnie galerię.
-   **Zdjęcia na stronę w galerii** (CG\_PAGINATION)
    -   **Co robi to ustawienie:** Kontroluje, ile zdjęć klientów jest wyświetlanych na jednej stronie w głównym widoku galerii przed włączeniem paginacji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na 12:* Galeria wyświetli 12 zdjęć na stronę.
        -   *Gdy ustawione na 24:* Galeria wyświetli 24 zdjęcia na stronę.
    -   **Zalecana wartość:** 12-24
    -   **Scenariusz/przykład dla sprzedawcy:** Umiarkowana liczba zapobiega przytłoczeniu użytkownika i utrzymuje rozsądny czas ładowania strony. Zbyt mało oznacza więcej kliknięć, zbyt wiele może spowolnić stronę.
-   **Włączyć głosowanie na zdjęcia?** (CG\_voting)
    -   **Co robi to ustawienie:** Umożliwia klientom głosowanie na przesłane zdjęcia, zazwyczaj za pomocą prostego „polubienia” lub oceny gwiazdkowej.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Obok każdego zdjęcia pojawią się kontrolki głosowania (np. gwiazdki, kciuki w górę).
        -   *Gdy wyłączone:* Nie będą wyświetlane żadne opcje głosowania.
    -   **Zalecana wartość:** TAK (zachęca do interakcji)
    -   **Scenariusz/przykład dla sprzedawcy:** Włączenie głosowania może wyróżnić popularne zdjęcia i zachęcić do większego zaangażowania społeczności.
-   **Zezwolić niezalogowanym klientom na głosowanie?** (cg\_unl\_voting)
    -   **Co robi to ustawienie:** Określa, czy odwiedzający, którzy nie są zalogowani, mogą oddawać głosy na zdjęcia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Goście mogą głosować na zdjęcia.
        -   *Gdy wyłączone:* Tylko zalogowani klienci mogą głosować.
    -   **Zalecana wartość:** NIE (aby zapobiec spamowi/głosowaniu botów i zapewnić bardziej znaczące zaangażowanie)
    -   **Scenariusz/przykład dla sprzedawcy:** Ograniczenie głosowania do zalogowanych użytkowników pomaga zapewnić, że głosy pochodzą od rzeczywistych klientów i zmniejsza ryzyko manipulacji.
-   **Styl głosowania** (CG\_VOTE\_STAR, CGV\_voting)
    -   **Co robi to ustawienie:** Wybiera styl wizualny mechanizmu głosowania (np. różne kolory gwiazdek).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na „Czarne gwiazdki”*: Głosowanie będzie używać ikon czarnych gwiazdek.
        -   *Gdy ustawione na „Złote gwiazdki”*: Głosowanie będzie używać ikon złotych gwiazdek.
    -   **Zalecana wartość:** Złote gwiazdki (często kojarzone z jakością i recenzjami)
    -   **Scenariusz/przykład dla sprzedawcy:** Wybierz styl, który najlepiej pasuje do brandingu i estetyki Twojego sklepu.
-   **Włączyć tryb konkursowy?** (cg\_contest)
    -   **Co robi to ustawienie:** Aktywuje funkcje wspierające prowadzenie konkursu fotograficznego, takie jak wyświetlanie zwycięzców lub konkretnych zasad konkursu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Mogą pojawić się dodatkowe opcje lub wyświetlacze związane z konkursem.
        -   *Gdy wyłączone:* Standardowe zachowanie galerii.
    -   **Zalecana wartość:** NIE (chyba że aktywnie prowadzisz konkurs)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli planujesz zorganizować konkurs na „najlepsze zdjęcie”, włącz tę opcję, aby wykorzystać funkcje konkursowe modułu.

#### Miejsca wyświetlania w Front-Office

Te ustawienia kontrolują, gdzie galeria zdjęć klientów i opcje przesyłania pojawiają się w Twoim sklepie.

-   **Pokazać formularz przesyłania na stronie produktu?** (CG\_FUPLOADON)
    -   **Co robi to ustawienie:** Określa, czy formularz przesyłania zdjęć jest bezpośrednio widoczny na stronie produktu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klienci zobaczą formularz do przesyłania zdjęć bezpośrednio na stronie produktu.
        -   *Gdy wyłączone:* Formularz przesyłania nie pojawi się na stronie produktu; klienci mogą potrzebować przejść do swojego konta lub dedykowanej strony galerii, aby przesłać zdjęcia.
    -   **Zalecana wartość:** TAK (dla maksymalnej wygody i generowania treści)
    -   **Scenariusz/przykład dla sprzedawcy:** Uczynienie formularza przesyłania łatwo dostępnym na stronie produktu zachęca więcej klientów do udostępniania swoich zdjęć zaraz po obejrzeniu produktu.
-   **Pokazać galerię na stronie produktu jako zakładkę?** (CG\_PRODUCTTAB, cg\_productTabM)
    -   **Co robi to ustawienie:** Integruje galerię zdjęć klientów jako nową zakładkę na stronie produktu (np. obok „Opisu” lub „Karty danych”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Na stronach produktów pojawi się nowa zakładka, wyświetlająca zdjęcia klientów dla tego konkretnego produktu.
        -   *Gdy wyłączone:* Galeria nie pojawi się jako zakładka.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz/przykład dla sprzedawcy:** Jest to bardzo widoczny i skuteczny sposób wyświetlania treści generowanych przez użytkowników, co ułatwia ich odkrywanie przez kupujących.
-   **Pokazać galerię na stronie produktu w stopce?** (CG\_PRODUCTFOOTER)
    -   **Co robi to ustawienie:** Wyświetla sekcję zdjęć klientów w obszarze stopki strony produktu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Blok zdjęć klientów pojawi się poniżej głównej treści produktu.
        -   *Gdy wyłączone:* Żadne zdjęcia nie pojawią się w stopce strony produktu.
    -   **Zalecana wartość:** TAK (jako dodatkowy punkt wyświetlania)
    -   **Scenariusz/przykład dla sprzedawcy:** Zapewnia to kolejną okazję do prezentowania zdjęć klientów bez zaśmiecania głównego obszaru informacji o produkcie.
-   **Pokazać galerię w koncie klienta?** (CG\_CUSTOMERACCOUNT, CG\_CUSTOMERACCOUNTV)
    -   **Co robi to ustawienie:** Tworzy dedykowaną sekcję „Moje zdjęcia” w osobistym obszarze konta klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Zalogowani klienci zobaczą nowy link i stronę w swoim koncie do zarządzania przesłanymi zdjęciami.
        -   *Gdy wyłączone:* Klienci nie mogą zarządzać swoimi zdjęciami z konta.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz/przykład dla sprzedawcy:** Niezbędne dla klientów do przeglądania i zarządzania swoimi wkładami, co sprzyja poczuciu własności i społeczności.
-   **Pokazać link do galerii w bloku „Moje konto”?** (CG\_MYACCOUNTBLOCK, CG\_MYACCOUNTBLOCKV)
    -   **Co robi to ustawienie:** Dodaje link do sekcji „Moje zdjęcia” (lub głównej galerii) w bloku „Moje konto”, który często znajduje się w lewej lub prawej kolumnie lub stopce.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Pojawi się szybki link dla zalogowanych użytkowników.
        -   *Gdy wyłączone:* Link nie będzie obecny w bloku.
    -   **Zalecana wartość:** TAK (dla łatwej nawigacji)
    -   **Scenariusz/przykład dla sprzedawcy:** Ułatwia klientom dostęp do ich galerii zdjęć lub przesyłanie nowych zdjęć z niemal każdej strony.
-   **Pokazać galerię w prawej kolumnie?** (CG\_RIGHTCOL)
    -   **Co robi to ustawienie:** Wyświetla blok zdjęć klientów w prawej kolumnie Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Dynamiczny blok zdjęć pojawi się w prawym pasku bocznym.
        -   *Gdy wyłączone:* Żadne zdjęcia nie pojawią się w prawej kolumnie.
    -   **Zalecana wartość:** NIE (może rozpraszać, rozważ tylko, jeśli Twój motyw ma dużo miejsca)
    -   **Scenariusz/przykład dla sprzedawcy:** Przydatne, jeśli masz szeroki układ i chcesz stale prezentować treści klientów, ale czasami może zaśmiecać stronę.
-   **Pokazać galerię w lewej kolumnie?** (CG\_LEFTCOL)
    -   **Co robi to ustawienie:** Wyświetla blok zdjęć klientów w lewej kolumnie Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Dynamiczny blok zdjęć pojawi się w lewym pasku bocznym.
        -   *Gdy wyłączone:* Żadne zdjęcia nie pojawią się w lewej kolumnie.
    -   **Zalecana wartość:** NIE (podobnie jak w prawej kolumnie, używaj oszczędnie)
    -   **Scenariusz/przykład dla sprzedawcy:** Podobnie jak w prawej kolumnie, użyj, jeśli projekt Twojego motywu na to pozwala bez pogarszania czytelności.
-   **Pokazać galerię na stronie głównej?** (CG\_GALLERY, cg\_hpg\_nb, cg\_hpg\_o)
    -   **Co robi to ustawienie:** Wyświetla wybór zdjęć klientów bezpośrednio na stronie głównej Twojego sklepu. Możesz również mieć opcje kontrolowania liczby zdjęć (cg\_hpg\_nb) i ich kolejności (cg\_hpg\_o).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Sekcja ze zdjęciami klientów pojawi się na stronie głównej.
        -   *Gdy wyłączone:* Żadne zdjęcia klientów nie będą wyświetlane na stronie głównej.
    -   **Zalecana wartość:** TAK (gorąco polecane dla zaangażowania)
    -   **Scenariusz/przykład dla sprzedawcy:** Strona główna to najważniejsze miejsce. Prezentowanie zdjęć klientów od razu przekazuje zaufanie i poczucie wspólnoty nowym odwiedzającym.
-   **Wykluczyć konkretne produkty z galerii?** (cg\_excludeproduct)
    -   **Co robi to ustawienie:** Umożliwia określenie identyfikatorów produktów, dla których zdjęcia klientów nie powinny być wyświetlane ani przesyłane.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wprowadzono ID produktu 123:* Produkt 123 nie będzie wyświetlał zdjęć klientów, a przesyłanie dla niego zostanie wyłączone.
        -   *Gdy pozostawiono puste:* Wszystkie produkty kwalifikują się do zdjęć klientów.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz produkty wrażliwe lub nie-wizualne.
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz produkty cyfrowe lub usługi, które nie mają komponentu wizualnego, lub produkty, dla których nie chcesz treści generowanych przez użytkowników, możesz je tutaj wykluczyć.

#### Powiadomienia i aktualizacje

-   **Włączyć powiadomienia e-mail o nowych przesyłanych zdjęciach?** (CG\_NTF)
    -   **Co robi to ustawienie:** Wysyła powiadomienie e-mail do administratora sklepu za każdym razem, gdy zostanie przesłane nowe zdjęcie klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Otrzymasz e-mail dla każdego nowego przesłanego zdjęcia, co pozwoli na szybką moderację.
        -   *Gdy wyłączone:* Nie będą wysyłane żadne powiadomienia e-mail.
    -   **Zalecana wartość:** TAK (niezbędne do moderacji i kontroli jakości)
    -   **Scenariusz/przykład dla sprzedawcy:** Bycie na bieżąco z nowymi przesyłanymi zdjęciami pomaga zapewnić, że wszystkie treści są odpowiednie i wysokiej jakości, zanim staną się szeroko widoczne.
-   **Aktualizacje MyPresta.eu** (mypresta\_updates, update\_, updatev\_)
    -   **Co robi to ustawienie:** Jest to standardowe ustawienie w modułach MyPresta.eu do sprawdzania dostępnych aktualizacji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł będzie okresowo sprawdzał MyPresta.eu pod kątem nowych wersji.
        -   *Gdy wyłączone:* Moduł nie będzie automatycznie sprawdzał aktualizacji.
    -   **Zalecana wartość:** TAK (zawsze bądź na bieżąco z bezpieczeństwem i funkcjami)
    -   **Scenariusz/przykład dla sprzedawcy:** Włączenie tej opcji zapewnia powiadomienia o nowych funkcjach, poprawkach błędów i łatkach bezpieczeństwa, pomagając Twojemu sklepowi pozostać aktualnym i bezpiecznym.

#### Ustawienia wewnętrzne/zaawansowane (zazwyczaj pozostaw domyślne)

-   **CG\_LAST\_TAB**: Ustawienie wewnętrzne do zapamiętywania ostatniej aktywnej zakładki w konfiguracji modułu.
-   **cg\_altered1, cg\_altered2**: Flagi wewnętrzne, zazwyczaj związane z aktualizacjami modułu lub migracjami danych.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Zezwolić na pliki JPEG? | TAK | Umożliwia klientom przesyłanie obrazów JPEG. |
| Konfiguracja modułu | Zezwolić na pliki GIF? | TAK | Umożliwia klientom przesyłanie obrazów GIF. |
| Konfiguracja modułu | Zezwolić na pliki PNG? | TAK | Umożliwia klientom przesyłanie obrazów PNG. |
| Konfiguracja modułu | Zezwolić na pliki BMP? | NIE | Nie zezwala na duże, nieskompresowane obrazy BMP. |
| Konfiguracja modułu | Zezwolić niezalogowanym klientom na przesyłanie zdjęć? | TAK / NIE (wybór sprzedawcy) | Kontroluje przesyłanie przez gości. |
| Konfiguracja modułu | Maksymalny rozmiar pliku (w MB) | 2-5 MB | Ogranicza rozmiar przesyłanych plików, aby zapobiec dużym plikom. |
| Konfiguracja modułu | Wysokość miniatury (px) | 150-250px | Ustawia spójną wysokość miniatur galerii. |
| Konfiguracja modułu | Szerokość miniatury (px) | 150-250px | Ustawia spójną szerokość miniatur galerii. |
| Konfiguracja modułu | Zdjęcia na stronę w galerii | 12-24 | Kontroluje paginację dla głównej galerii. |
| Konfiguracja modułu | Włączyć głosowanie na zdjęcia? | TAK | Umożliwia klientom głosowanie na zdjęcia. |
| Konfiguracja modułu | Zezwolić niezalogowanym klientom na głosowanie? | NIE | Zapobiega spamowi/głosowaniu botów. |
| Konfiguracja modułu | Styl głosowania | Złote gwiazdki | Ustawia styl wizualny ikon głosowania. |
| Konfiguracja modułu | Włączyć tryb konkursowy? | NIE | Aktywuje funkcje specyficzne dla konkursu. |
| Konfiguracja modułu | Pokazać formularz przesyłania na stronie produktu? | TAK | Wyświetla formularz przesyłania bezpośrednio na stronach produktów. |
| Konfiguracja modułu | Pokazać galerię na stronie produktu jako zakładkę? | TAK | Dodaje dedykowaną zakładkę dla zdjęć na stronach produktów. |
| Konfiguracja modułu | Pokazać galerię na stronie produktu w stopce? | TAK | Wyświetla zdjęcia poniżej treści produktu. |
| Konfiguracja modułu | Pokazać galerię w koncie klienta? | TAK | Tworzy sekcję „Moje zdjęcia” w kontach klientów. |
| Konfiguracja modułu | Pokazać link do galerii w bloku „Moje konto”? | TAK | Dodaje szybki link do galerii w bloku Moje konto. |
| Konfiguracja modułu | Pokazać galerię w prawej kolumnie? | NIE | Wyświetla zdjęcia w prawym pasku bocznym. |
| Konfiguracja modułu | Pokazać galerię w lewej kolumnie? | NIE | Wyświetla zdjęcia w lewym pasku bocznym. |
| Konfiguracja modułu | Pokazać galerię na stronie głównej? | TAK | Wyświetla zdjęcia na stronie głównej sklepu. |
| Konfiguracja modułu | Wykluczyć konkretne produkty z galerii? | Pozostaw puste | Zapobiega zdjęciom dla określonych produktów. |
| Konfiguracja modułu | Włączyć powiadomienia e-mail o nowych przesyłanych zdjęciach? | TAK | Wysyła e-mail do administratora o nowych przesyłanych zdjęciach. |
| Konfiguracja modułu | Aktualizacje MyPresta.eu | TAK | Włącza automatyczne sprawdzanie aktualizacji. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje zdjęcia klientów nie pojawiają się po przesłaniu, lub galeria wygląda na pustą.**
**O1:**

-   **Sprawdź konfigurację modułu:** Upewnij się, że opcje wyświetlania (np. „Pokazać galerię na stronie produktu jako zakładkę”, „Pokazać galerię na stronie głównej?”) są włączone w ustawieniach modułu.
-   **Wyczyść pamięć podręczną:** PrestaShop używa pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” i „Wyczyść pamięć podręczną”, jeśli są oddzielne opcje). To często rozwiązuje problemy z wyświetlaniem.
-   **Moderacja obrazów:** Niektóre moduły mają proces zatwierdzania. Sprawdź, czy istnieje sekcja administracyjna (chociaż ten moduł nie ma dedykowanego kontrolera administracyjnego, może mieć wewnętrzny status zatwierdzenia), gdzie zdjęcia muszą zostać zatwierdzone przed opublikowaniem.
-   **Uprawnienia do plików:** Upewnij się, że Twój folder `img/customersgallery` (lub podobna ścieżka, w której przechowywane są obrazy) ma prawidłowe uprawnienia do zapisu (zazwyczaj 755 lub 775). Twój dostawca hostingu może w tym pomóc.

**P2: Klienci mają problemy z przesyłaniem zdjęć lub otrzymują komunikat o błędzie.**
**O2:**

-   **Sprawdź typ pliku i limity rozmiaru:** Przejrzyj ustawienia „Zezwolić na pliki JPEG/GIF/PNG/BMP?” i „Maksymalny rozmiar pliku (w MB)” w konfiguracji modułu. Upewnij się, że plik klienta odpowiada dozwolonym typom i mieści się w limicie rozmiaru.
-   **Limity PHP serwera:** Nawet jeśli moduł pozwala na duży rozmiar pliku, konfiguracja PHP Twojego serwera (np. `upload_max_filesize`, `post_max_size` w `php.ini`) może narzucać bardziej rygorystyczny limit. Skontaktuj się z dostawcą hostingu, aby sprawdzić i potencjalnie zwiększyć te limity, jeśli to konieczne.
-   **Kompatybilność przeglądarki:** Poproś klienta, aby spróbował innej przeglądarki lub wyczyścił pamięć podręczną przeglądarki.
-   **Błędy JavaScript:** Otwórz konsolę programisty przeglądarki (F12) i sprawdź, czy podczas procesu przesyłania nie występują żadne błędy JavaScript. Może to wskazywać na konflikt z innym modułem lub motywem.

**P3: Zdjęcia klientów wyglądają na zniekształcone lub mają nieprawidłowy rozmiar w galerii.**
**O3:**

-   **Wymiary miniatur:** Dostosuj ustawienia „Wysokość miniatury (px)” i „Szerokość miniatury (px)” w konfiguracji modułu. Eksperymentuj z różnymi wartościami, aby znaleźć to, co najlepiej wygląda z Twoim motywem. Pamiętaj, aby wyczyścić pamięć podręczną PrestaShop po wprowadzeniu zmian.
-   **Konflikty CSS:** CSS Twojego motywu może nadpisywać styl modułu. Użyj narzędzi programistycznych przeglądarki (F12), aby zbadać elementy i zidentyfikować wszelkie konfliktowe reguły CSS. Może być konieczne, aby webmaster dodał niestandardowy CSS do Twojego motywu, aby to poprawić.

**P4: Link „Moje zdjęcia” nie pojawia się w koncie klienta ani w bloku „Moje konto”.**
**O4:**

-   **Podpięcie modułu:** Upewnij się, że moduł jest prawidłowo podpięty do `displayCustomerAccount` i `displayMyAccountBlock` (lub `displayMyAccountBlockFooter` w zależności od Twojego motywu). Możesz to sprawdzić w **Wygląd > Pozycje** (lub **Moduły > Pozycje** w starszych wersjach) i wyszukać moduł. Jeśli nie jest podpięty, spróbuj ponownie zainstalować moduł lub podpiąć go ręcznie.
-   **Konfiguracja modułu:** Sprawdź dwukrotnie, czy opcje „Pokazać galerię w koncie klienta?” i „Pokazać link do galerii w bloku „Moje konto”?” są włączone w ustawieniach modułu.
-   **Logowanie klienta:** Link „Moje zdjęcia” jest widoczny tylko dla zalogowanych klientów. Upewnij się, że jesteś zalogowany podczas testowania.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Zdjęcia produktów od klientów”, przeznaczony dla programistów i webmasterów, którzy muszą zrozumieć jego wewnętrzne działanie, dostosować jego zachowanie lub rozwiązać zaawansowane problemy.

### 4.1 Przegląd architektury

Moduł „Zdjęcia produktów od klientów” stosuje standardową architekturę modułu PrestaShop, głównie wykorzystując kontrolery Front do interakcji z użytkownikiem i szablony Smarty do renderowania. Używa głównej klasy modułu (`customersgallery.php`) do zarządzania konfiguracją i rejestracji hooków. Chociaż nie rozszerza `ObjectModel` dla swoich podstawowych danych, bezpośrednio wchodzi w interakcje z bazą danych w celu przechowywania metadanych zdjęć i polega na systemie plików PrestaShop do przechowywania obrazów. AJAX jest intensywnie używany do dynamicznego ładowania treści i przesyłania zdjęć, zapewniając płynne doświadczenie użytkownika bez pełnego przeładowywania strony.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery obsługują wszystkie interakcje z klientem, w tym wyświetlanie galerii, zarządzanie zdjęciami użytkowników i przetwarzanie żądań AJAX.

-   **`controllers/front/ajax.php`**
    -   **Nazwa klasy:** `CustomersGalleryAjaxModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Jest to główny punkt końcowy dla wszystkich operacji asynchronicznych (AJAX). Obsługuje:
        -   Przesyłanie zdjęć ze strony produktu lub konta klienta.
        -   Akcje głosowania (polubienie/ocenianie zdjęć).
        -   Potencjalne żądania usunięcia lub moderacji obrazów z sekcji „Moje zdjęcia” klienta.
        -   Zwraca odpowiedzi JSON wskazujące sukces lub niepowodzenie, wraz z odpowiednimi danymi.
-   **`controllers/front/gallery.php`**
    -   **Nazwa klasy:** `CustomersGalleryGalleryModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Renderuje główną, dedykowaną stronę galerii zdjęć klientów. Ta strona zazwyczaj wyświetla wszystkie zatwierdzone zdjęcia klientów, prawdopodobnie z paginacją i opcjami filtrowania. Pobiera dane zdjęć z bazy danych i przypisuje je do szablonu `gallery.tpl`.
-   **`controllers/front/index.php`**
    -   **Nazwa klasy:** `CustomersGalleryIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Ten kontroler prawdopodobnie służy jako domyślny lub awaryjny punkt wejścia dla tras front-office modułu. Może przekierowywać do głównej galerii lub kontrolera `myphotos`, jeśli jest dostępny bezpośrednio bez określonych parametrów.
-   **`controllers/front/myphotos.php`**
    -   **Nazwa klasy:** `CustomersGalleryMyPhotosModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Obsługuje sekcję „Moje zdjęcia” w koncie klienta. Wyświetla zdjęcia przesłane przez aktualnie zalogowanego klienta, umożliwia im zarządzanie (np. usuwanie) własnymi zdjęciami i potencjalnie zapewnia interfejs przesyłania. Wymaga uwierzytelnienia klienta.
-   **`controllers/front/myvideos.php`**
    -   **Nazwa klasy:** `CustomersGalleryMyVideosModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Chociaż nazwa modułu to „Zdjęcia produktów od klientów”, ten kontroler sugeruje potencjalną (lub planowaną) funkcję przesyłania filmów przez klientów. Prawdopodobnie działałby podobnie do `myphotos.php`, ale dla treści wideo.

#### Kontrolery administracyjne Back-Office

Moduł nie posiada dedykowanych kontrolerów administracyjnych. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównego modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł nie wydaje się definiować niestandardowych klas rozszerzających `ObjectModel` w dedykowanym katalogu `classes/`. Cała podstawowa logika interakcji z bazą danych, przetwarzania obrazów i reguł biznesowych jest prawdopodobnie hermetyzowana w głównym pliku `customersgallery.php` i kontrolerach frontowych. Oznacza to, że operacje na bazie danych są obsługiwane bezpośrednio za pomocą wywołań `Db::getInstance()`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`customersgallery/js/customersgallery.js`**
    -   **Zakres:** Front-office
    -   **Szczegóły:** Jest to główny niestandardowy JavaScript dla modułu. Prawdopodobnie obsługuje:
        -   Wywołania AJAX do przesyłania zdjęć (np. wiązanie z przesyłaniem formularzy).
        -   Wywołania AJAX dla mechanizmów głosowania.
        -   Dynamiczne ładowanie treści galerii.
        -   Walidację po stronie klienta dla typów plików i rozmiarów przed przesłaniem.
        -   Interakcję z biblioteką Fancybox dla lightboxów obrazów.
        -   Słuchacze zdarzeń dla paginacji, filtrowania i innych interakcji z galerią.
-   **`customersgallery/js/fancybox.js`**
    -   **Zakres:** Front-office
    -   **Szczegóły:** Jest to biblioteka zewnętrzna (Fancybox) używana do wyświetlania obrazów w responsywnej, eleganckiej nakładce lightbox, gdy użytkownik kliknie miniaturę. Obsługuje powiększanie obrazów, nawigację między obrazami w galerii i prezentację modalną.
-   **`customersgallery/js/script.js`**
    -   **Zakres:** Front-office
    -   **Szczegóły:** Może to być dodatkowy skrypt, potencjalnie do ogólnych ulepszeń interfejsu użytkownika, specyficznych animacji lub dodatkowej obsługi zdarzeń nieobjętej przez `customersgallery.js`. Może również zawierać procedury inicjalizacji dla innych komponentów JS.
-   **`customersgallery/lib/voucherengine/script.js`**
    -   **Zakres:** Front-office (potencjalnie)
    -   **Szczegóły:** Obecność `voucherengine` sugeruje potencjalną integrację lub osobną funkcję do generowania/zarządzania kuponami, być może jako nagrodę za przesyłanie zdjęć lub udział w konkursie. Ten skrypt obsługiwałby logikę po stronie klienta dla takiego systemu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`customersgallery/css/customersgallery.css`**
    -   **Zakres:** Stylizacja klienta Front-office
    -   **Szczegóły:** Jest to główny arkusz stylów dla komponentów front-office modułu. Stylizuje:
        -   Układ galerii zdjęć (siatka, flexbox).
        -   Indywidualne kontenery zdjęć i miniatury.
        -   Formularze przesyłania i przyciski.
        -   Kontrolki paginacji.
        -   Elementy głosowania (jeśli nie są obsługiwane przez specyficzne CSS gwiazdek).
        -   Dostosowania responsywne dla różnych rozmiarów ekranu.
    -   **Kluczowe selektory klas CSS:** `.customer-photo-gallery`, `.cg-item`, `.cg-thumbnail`, `.cg-upload-form`, `.cg-vote-stars`
-   **`customersgallery/css/fancybox.css`**
    -   **Zakres:** Stylizacja klienta Front-office
    -   **Szczegóły:** Arkusz stylów dla biblioteki lightbox Fancybox, zapewniający, że nakładka obrazu, strzałki nawigacyjne, przycisk zamykania i podpisy są wizualnie spójne i atrakcyjne.
-   **`customersgallery/css/star-black.css`, `star-blue.css`, `star-gold.css`, `star-pink.css`, `star-red.css`, `star-whitered.css`, `star.css`**
    -   **Zakres:** Stylizacja klienta Front-office
    -   **Szczegóły:** Są to specyficzne arkusze stylów dla systemu głosowania opartego na gwiazdkach. Każdy plik zapewnia inną kolorystykę lub styl wizualny dla ikon gwiazdek, umożliwiając sprzedawcy wybór projektu pasującego do jego motywu. `star.css` to prawdopodobnie podstawowa stylizacja, a pozostałe zapewniają nadpisania kolorów.
-   **`customersgallery/lib/voucherengine/ps16.css`**
    -   **Zakres:** Front-office (potencjalnie)
    -   **Szczegóły:** Ten arkusz stylów, znajdujący się w katalogu `voucherengine`, sugeruje stylizację specjalnie dla funkcji związanych z kuponami, potencjalnie zoptymalizowaną dla motywów PrestaShop 1.6, ale prawdopodobnie kompatybilną lub adaptowalną dla nowszych wersji.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

Te szablony są zaprojektowane do renderowania, gdy wykonywane są określone hooki PrestaShop, integrując zawartość modułu w różnych częściach sklepu.

-   **`customersgallery/views/templates/hook/column-link.tpl`**
    -   **Hook:** `displayLeftColumn`, `displayRightColumn`
    -   **Wyjście:** Link lub blok, który kieruje użytkowników do głównej galerii zdjęć klientów lub ich sekcji „Moje zdjęcia”, zazwyczaj umieszczony w paskach bocznych.
-   **`customersgallery/views/templates/hook/customer-my-account.tpl`**
    -   **Hook:** `displayCustomerAccount`
    -   **Wyjście:** Link lub blok na stronie „Moje konto” klienta, prowadzący do jego dedykowanej sekcji „Moje zdjęcia”.
-   **`customersgallery/views/templates/hook/hookHome.tpl`**
    -   **Hook:** `displayHome`
    -   **Wyjście:** Blok lub sekcja wyświetlająca wybór zdjęć klientów na stronie głównej sklepu, często prezentująca najnowsze lub najpopularniejsze przesłane zdjęcia.
-   **`customersgallery/views/templates/hook/my-account.tpl`**
    -   **Hook:** `displayMyAccountBlock`, `displayMyAccountBlockFooter`
    -   **Wyjście:** Link do sekcji „Moje zdjęcia”, zintegrowany ze standardowym blokiem „Moje konto”, który pojawia się w kolumnach lub stopce dla zalogowanych użytkowników.
-   **`customersgallery/views/templates/hook/productfooter.tpl`**
    -   **Hook:** `displayProductFooter`, `displayProductExtraContent`
    -   **Wyjście:** Sekcja wyświetlająca zdjęcia klientów dla bieżącego produktu, znajdująca się poniżej głównej treści produktu na stronie produktu.
-   **`customersgallery/views/templates/hook/tab.tpl`**
    -   **Hook:** `displayProductTab`
    -   **Wyjście:** HTML dla nowego nagłówka zakładki (np. „Zdjęcia klientów”), który pojawia się na stronie produktu.
-   **`customersgallery/views/templates/hook/tabContents.tpl`**
    -   **Hook:** `displayProductTabContent`
    -   **Wyjście:** Rzeczywista zawartość wyświetlana, gdy zakładka „Zdjęcia klientów” jest aktywna na stronie produktu, pokazująca galerię i potencjalnie formularz przesyłania dla tego konkretnego produktu.

#### Szablony niestandardowe (`views/templates/custom/`)

Te szablony są prawdopodobnie używane do konkretnych formularzy lub części procesu przesyłania.

-   **`customersgallery/views/templates/custom/upload-form.tpl`**
    -   **Cel:** Renderuje formularz HTML, którego klienci używają do przesyłania zdjęć produktów. Może to być prostsza wersja lub starsza iteracja.
-   **`customersgallery/views/templates/custom/upload-form2.tpl`**
    -   **Cel:** Prawdopodobnie zaktualizowana lub alternatywna wersja formularza przesyłania, potencjalnie z inną stylizacją, funkcjami lub kompatybilnością dla nowszych wersji PrestaShop.

#### Szablony Front-Office (`views/templates/front/`)

Te szablony są zazwyczaj używane przez kontrolery frontowe modułu do renderowania pełnych stron lub znaczących sekcji funkcjonalności modułu.

-   **`customersgallery/views/templates/front/gallery.tpl`**
    -   **Cel:** Główny szablon dla dedykowanej strony galerii zdjęć klientów, wyświetlający wszystkie zdjęcia z paginacją.
-   **`customersgallery/views/templates/front/gallery2.tpl`**
    -   **Cel:** Alternatywna lub zaktualizowana wersja głównego szablonu galerii, potencjalnie oferująca różne układy lub funkcje.
-   **`customersgallery/views/templates/front/gallery3.tpl`**
    -   **Cel:** Kolejna alternatywna lub zaktualizowana wersja głównego szablonu galerii. Moduł może przełączać się między nimi w zależności od konfiguracji lub wersji PrestaShop.
-   **`customersgallery/views/templates/front/menu.tpl`**
    -   **Cel:** Renderuje menu nawigacyjne specyficzne dla galerii zdjęć klientów, potencjalnie do filtrowania, sortowania lub nawigacji między „Moimi zdjęciami” a główną galerią.
-   **`customersgallery/views/templates/front/my-photos.tpl`**
    -   **Cel:** Renderuje stronę „Moje zdjęcia” w koncie klienta, pokazując przesłane obrazy i opcje zarządzania.
-   **`customersgallery/views/templates/front/my-videos-16.tpl`**
    -   **Cel:** Szablon dla sekcji „Moje filmy”, specjalnie zaprojektowany lub zoptymalizowany dla PrestaShop 1.6, jeśli funkcja przesyłania filmów jest włączona.
-   **`customersgallery/views/templates/front/video-upload.tpl`**
    -   **Cel:** Renderuje formularz dla klientów do przesyłania filmów, jeśli ta funkcja jest aktywna.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł nie definiuje jawnie niestandardowych plików SQL, ale na podstawie swojej funkcjonalności będzie wchodził w interakcje z bazą danych.

-   **Tabele niestandardowe (prawdopodobnie utworzone podczas install()):**
    -   `_customersgallery`: Przechowuje metadane dla każdego przesłanego zdjęcia (np. `id_customersgallery`, `id_customer`, `id_product`, `filename`, `date_add`, `approved`, `votes`, `active`).
    -   `_customersgallery_vote`: Przechowuje rekordy głosów klientów (np. `id_customersgallery_vote`, `id_customersgallery`, `id_customer`, `ip_address`, `date_add`).
-   **Rekordy konfiguracji (przechowywane w `ps_configuration`):**
    -   `CG_LAST_TAB`, `CG_ALLOW_JPEG`, `CG_ALLOW_GIF`, `CG_ALLOW_PNG`, `CG_ALLOW_BMP`, `mypresta_updates`, `CG_PAGINATION`, `CG_ALLOW_UNLOGGED`, `CG_MAX_FILE_SIZE`, `CG_PRODUCTTAB`, `cg_productTabM`, `CG_PRODUCTFOOTER`, `CG_CUSTOMERACCOUNT`, `CG_MYACCOUNTBLOCK`, `CG_THUMBHEIGHT`, `CG_THUMBWIDTH`, `CG_FUPLOADON`, `CG_GALLERY`, `CG_RIGHTCOL`, `CG_LEFTCOL`, `CG_NTF`, `update_`, `updatev_`, `cg_altered1`, `cg_altered2`, `cg_hpg_nb`, `cg_hpg_o`, `cg_contest`, `cg_excludeproduct`, `CG_CUSTOMERACCOUNTV`, `CG_MYACCOUNTBLOCKV`, `CG_voting`, `CG_VOTE_STAR`, `CGV_voting`, `cg_unl_voting`.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykuje zasoby CSS i JavaScript wymagane przez moduł (np. `customersgallery.css`, `fancybox.js`, `customersgallery.js`). |
| `displayMyAccountBlock` | W bloku „Moje konto” klienta (często w lewej/prawej kolumnie lub stopce). | Dodaje link do sekcji „Moje zdjęcia” klienta. |
| `displayLeftColumn` | W lewym pasku bocznym sklepu. | Wyświetla blok zdjęć klientów lub link do galerii. |
| `displayRightColumn` | W prawym pasku bocznym sklepu. | Wyświetla blok zdjęć klientów lub link do galerii. |
| `displayHome` | Na stronie głównej sklepu. | Wyświetla sekcję zdjęć klientów (najnowsze, najpopularniejsze). |
| `displayProductTab` | Na stronie produktu, do dodawania nowych zakładek. | Dodaje nagłówek zakładki „Zdjęcia klientów”. |
| `displayProductTabContent` | Na stronie produktu, dla zawartości zakładki. | Wyświetla galerię zdjęć klientów i formularz przesyłania w zakładce „Zdjęcia klientów”. |
| `displayProductFooter` | Na dole strony produktu. | Wyświetla sekcję zdjęć klientów dla bieżącego produktu. |
| `displayProductExtraContent` | Inny hook dla dodatkowej zawartości na stronie produktu. | Może być używany jako alternatywne lub dodatkowe miejsce dla treści zdjęć specyficznych dla produktu. |
| `displayCustomerAccount` | Na stronie „Moje konto” klienta. | Dodaje link do sekcji „Moje zdjęcia” dla zalogowanego klienta. |
| `displayLeftColumnProduct` | W lewej kolumnie specjalnie na stronach produktów. | Wyświetla blok zdjęć klientów lub link do galerii na stronach produktów. |
| `displayRightColumnProduct` | W prawej kolumnie specjalnie na stronach produktów. | Wyświetla blok zdjęć klientów lub link do galerii na stronach produktów. |
| `displayMyAccountBlockFooter` | W wersji stopki bloku „Moje konto”. | Dodaje link do sekcji „Moje zdjęcia” klienta w stopce. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | (Potencjalnie) Może być używany do wysyłania e-maila do klienta zachęcającego do przesyłania zdjęć zakupionych produktów. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnego wsparcia, aktualizacji modułu i wszelkiej dalszej pomocy dotyczącej modułu „Zdjęcia produktów od klientów”, prosimy odwołać się do swojego konta klienta MyPresta.eu. Możesz zalogować się na stronie [MyPresta.eu Historia zamówień i pobieranie](https://mypresta.eu/my-account/orders/), aby uzyskać dostęp do najnowszych wersji i zgłosić zgłoszenia do wsparcia.
