---
title: "Shoutbox - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu Shoutbox dla PrestaShop od MyPresta.eu."
sidebar:
  label: "Shoutbox - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Shoutbox na MyPresta.eu](https://mypresta.eu/modules/front-office-features/shoutbox.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/shoutbox/)
>
> ---


# Shoutbox

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu Shoutbox, dostępny bezpośrednio po instalacji lub poprzez nawigację do **Moduły > Menedżer modułów**, wyszukanie „Shoutbox” i kliknięcie „Konfiguruj”.

| Ustawienie / Opcja | Co robi to ustawienie | Efekt zmiany tego ustawienia | Zalecana wartość | Scenariusz sprzedawcy / przykład |
| --- | --- | --- | --- | --- |
| **Włącz Shoutbox** | To jest główny przełącznik do włączania lub wyłączania całej funkcji Shoutbox w Twoim sklepie. | *Po włączeniu:* Shoutbox pojawi się w Twoim front office w wybranych miejscach zaczepienia. Klienci mogą go widzieć i wchodzić z nim w interakcje.   *Po wyłączeniu:* Shoutbox zostanie całkowicie ukryty w Twoim sklepie, a żadne wiadomości nie będą wyświetlane ani akceptowane. | **TAK** | Chcesz aktywować funkcję czatu społecznościowego w swoim sklepie. Jeśli musisz tymczasowo ukryć go w celu konserwacji lub przeglądu treści, ustaw to na NIE. |
| **Tytuł Shoutboxa** | To ustawia tekst nagłówka, który pojawia się na górze widżetu Shoutbox w front office Twojego sklepu. | *Po ustawieniu na „Czat Społecznościowy”:* Twoi klienci zobaczą „Czat Społecznościowy” jako tytuł okna.   *Po ustawieniu na „Zapytaj nas o cokolwiek”:* Tytuł zmienia się na „Zapytaj nas o cokolwiek”. | **Czat Społecznościowy** | Chcesz wyraźnie oznaczyć okno czatu dla swoich klientów. Możesz zmienić go na „Dyskusje o produktach”, jeśli umieścisz go na stronach produktów. |
| **Liczba wyświetlanych wiadomości** | To kontroluje, ile najnowszych wiadomości jest wyświetlanych w Shoutboxie w danym momencie. Starsze wiadomości zostaną ukryte. | *Po ustawieniu na 10:* W oknie czatu będzie widocznych tylko 10 ostatnich wiadomości.   *Po ustawieniu na 20:* Zostanie wyświetlonych 20 ostatnich wiadomości. | **10** | Aby czat był zwięzły i nie stał się zbyt długi, zazwyczaj najlepiej jest wyświetlać 10-15 najnowszych wiadomości. Jeśli masz bardzo aktywną społeczność, możesz to zwiększyć. |
| **Interwał odświeżania (sekundy)** | To określa, jak często Shoutbox automatycznie sprawdza i ładuje nowe wiadomości bez konieczności odświeżania strony przez klienta. | *Po ustawieniu na 5:* Nowe wiadomości będą pojawiać się co 5 sekund.   *Po ustawieniu na 15:* Nowe wiadomości będą pojawiać się co 15 sekund. | **10** | Krótszy interwał (np. 5 sekund) sprawia, że czat wydaje się bardziej w czasie rzeczywistym, ale zużywa więcej zasobów serwera. Dłuższy interwał (np. 15-20 sekund) zmniejsza obciążenie serwera, ale wiadomości pojawiają się mniej natychmiastowo. 10 sekund to dobry kompromis. |
| **Zezwól gościom na publikowanie** | Ta opcja kontroluje, czy odwiedzający, którzy nie są zalogowani na konto klienta, mogą publikować wiadomości w Shoutboxie. | *Po włączeniu:* Każdy odwiedzający Twój sklep może publikować wiadomości, nawet jeśli nie zarejestrował się ani nie zalogował. Zazwyczaj będą publikować jako „Gość”.   *Po wyłączeniu:* Tylko zarejestrowani i zalogowani klienci mogą publikować wiadomości. Goście zobaczą czat, ale nie będą mogli wnosić wkładu. | **NIE** | Jeśli chcesz zachęcić do rejestracji i zapobiec anonimowemu spamowi, wyłącz to. Jeśli chcesz maksymalnej interakcji i nie przeszkadzają Ci anonimowe posty, włącz to. |
| **Wyświetl Shoutbox w** | To kluczowe ustawienie określa, gdzie widżet Shoutbox pojawi się w front office Twojego sklepu. Możesz wybrać jedną lub więcej lokalizacji. | *Po wybraniu „Lewa kolumna”:* Shoutbox pojawi się w lewym pasku bocznym Twojego sklepu.   *Po wybraniu „Stopka”:* Shoutbox pojawi się na dole stron Twojego sklepu. | **Lewa kolumna** (lub lokalizacja pasująca do Twojego motywu) | Chcesz, aby Shoutbox był łatwo widoczny, ale nie kolidował z główną treścią produktu. Umieszczenie go w kolumnie lub stopce jest często dobrym wyborem. |
| **Wymagana moderacja** | Jeśli włączone, nowe wiadomości nie pojawią się w Shoutboxie, dopóki administrator ręcznie ich nie zatwierdzi w Panelu administracyjnym. | *Po włączeniu:* Wszystkie nowe wiadomości trafiają do kolejki oczekujących. Musisz zatwierdzić każdą wiadomość, zanim stanie się widoczna dla innych klientów.   *Po wyłączeniu:* Wiadomości pojawiają się natychmiast po opublikowaniu. | **NIE** (chyba że przewidujesz spam) | Jeśli obawiasz się spamu, nieodpowiednich treści lub chcesz zachować ścisłą kontrolę nad rozmową, włącz moderację. Aby uzyskać bardziej płynny czat w czasie rzeczywistym, wyłącz to. |
| **Wyczyść wszystkie wiadomości** | To jest przycisk (nie przełącznik), który po kliknięciu trwale usunie wszystkie istniejące wiadomości z Shoutboxa. | *Po kliknięciu:* Wszystkie historyczne wiadomości w Shoutboxie zostają usunięte z Twojej bazy danych i nie będą już wyświetlane. Ta akcja jest nieodwracalna. | **N/A** (Używaj ostrożnie) | Możesz tego użyć, jeśli czat zgromadził zbyt wiele starych wiadomości, lub jeśli chcesz rozpocząć nową rozmowę dla nowej promocji lub wydarzenia. |

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz Shoutbox | TAK | Aktywuje/dezaktywuje całą funkcję Shoutbox. |
| Konfiguracja modułu | Tytuł Shoutboxa | Czat Społecznościowy | Ustawia widoczny tytuł widżetu Shoutbox. |
| Konfiguracja modułu | Liczba wyświetlanych wiadomości | 10 | Kontroluje, ile ostatnich wiadomości jest wyświetlanych. |
| Konfiguracja modułu | Interwał odświeżania (sekundy) | 10 | Jak często czat aktualizuje się nowymi wiadomościami. |
| Konfiguracja modułu | Zezwól gościom na publikowanie | NIE | Określa, czy niezalogowani użytkownicy mogą publikować wiadomości. |
| Konfiguracja modułu | Wyświetl Shoutbox w | Lewa kolumna | Wybiera lokalizację(e) Shoutboxa w front office. |
| Konfiguracja modułu | Wymagana moderacja | NIE | Wymaga zatwierdzenia wiadomości przez administratora przed ich pojawieniem się. |
| Konfiguracja modułu | Wyczyść wszystkie wiadomości | N/A | Trwale usuwa wszystkie wiadomości z Shoutboxa. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Shoutbox nie pojawia się w moim sklepie, mimo że go włączyłem.**
**O1:**

-   **Sprawdź wybór zaczepienia (hook):** Przejdź do konfiguracji modułu i upewnij się, że wybrałeś co najmniej jedną lokalizację „Wyświetl Shoutbox w” (np. Lewa kolumna, Stopka).
-   **Wyczyść pamięć podręczną:** Pamięć podręczna PrestaShop może czasami uniemożliwiać pojawienie się nowych modułów. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
-   **Kompatybilność z motywem:** Niektóre wysoce spersonalizowane motywy mogą niepoprawnie renderować standardowe zaczepienia modułów. Jeśli wyczyszczenie pamięci podręcznej nie działa, spróbuj tymczasowo przełączyć się na domyślny motyw PrestaShop, aby sprawdzić, czy Shoutbox się pojawi. Jeśli tak, Twój motyw prawdopodobnie wymaga niewielkiej korekty (skontaktuj się z twórcą motywu lub webmasterem).

**P2: Nowe wiadomości nie pojawiają się w czasie rzeczywistym; muszę odświeżyć stronę.**
**O2:**

-   **Sprawdź interwał odświeżania:** W konfiguracji modułu upewnij się, że „Interwał odświeżania (sekundy)” jest ustawiony na rozsądną liczbę (np. 5-15 sekund), a nie na 0 lub bardzo wysoką liczbę.
-   **Konflikty JavaScript:** Inny moduł lub JavaScript Twojego motywu może powodować konflikt. Sprawdź konsolę programisty w przeglądarce (klawisz F12, a następnie zakładka „Konsola”) pod kątem błędów JavaScript. Jeśli pojawią się błędy, spróbuj wyłączyć inne ostatnio zainstalowane moduły jeden po drugim, aby zidentyfikować winowajcę.

**P3: Otrzymuję dużo wiadomości spamowych w Shoutboxie.**
**O3:**

-   **Włącz moderację:** Przejdź do konfiguracji modułu i ustaw „Wymagana moderacja” na TAK. Spowoduje to, że wszystkie nowe wiadomości trafią do stanu oczekującego, co pozwoli Ci je zatwierdzić przed ich opublikowaniem.
-   **Wyłącz publikowanie przez gości:** Jeśli spam pochodzi od anonimowych użytkowników, ustaw „Zezwól gościom na publikowanie” na NIE. Będzie to wymagało od użytkowników zalogowania się na konto klienta, aby móc publikować, co często zmniejsza ilość spamu.

**P4: Jak przetłumaczyć tytuł Shoutboxa lub inne teksty na różne języki?**
**O4:**

-   Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
-   Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz swój język.
-   Znajdź moduł „Shoutbox” na liście i będziesz mógł edytować przetłumaczalne ciągi znaków, w tym tytuł Shoutboxa.

**P5: Shoutbox wygląda trochę dziwnie lub nie pasuje do stylu mojego motywu.**
**O5:**

-   Moduł używa podstawowego stylu. Aby uzyskać niestandardowy wygląd, będziesz potrzebować webmastera lub programisty, aby dodać niestandardowe reguły CSS do arkusza stylów Twojego motywu. Mogą oni celować w elementy Shoutboxa i dostosować kolory, czcionki, obramowania itp., aby idealnie pasowały do Twojej marki.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu Shoutbox, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł Shoutbox podąża za klasyczną strukturą modułu PrestaShop, wykorzystując kontrolery front-end do interakcji AJAX oraz główny plik modułu (`index.php`) do konfiguracji i rejestracji zaczepień. Jest to lekki moduł, skupiający się głównie na wyświetlaniu i przesyłaniu wiadomości za pośrednictwem AJAX bez złożonych modeli obiektów lub dedykowanych tabel baz danych poza `ps_configuration` dla ustawień. Podstawowa funkcjonalność opiera się na bezpośredniej interakcji z bazą danych w celu przechowywania i pobierania wiadomości.

### 4.2 Kontrolery (`controllers/`)

Moduł wykorzystuje kontrolery front-end do obsługi żądań AJAX w celu ładowania i wstawiania wiadomości, zapewniając dynamiczne doświadczenie użytkownika bez pełnego przeładowywania strony.

-   **Kontrolery Front-Office**:

    *   `controllers/front/ajaxload.php`
        *   **Nazwa klasy**: `ShoutboxAjaxloadModuleFrontController` (rozszerza `ModuleFrontController`)
        *   **Odpowiedzialność**: Ten kontroler obsługuje żądanie AJAX w celu ładowania istniejących wiadomości. Zazwyczaj pobiera określoną liczbę najnowszych wiadomości z bazy danych i zwraca je, prawdopodobnie jako JSON lub surowy HTML, do wyświetlenia w widżecie Shoutbox. Jest to punkt końcowy mechanizmu automatycznego odświeżania.
    *   `controllers/front/index.php`
        *   **Nazwa klasy**: `ShoutboxIndexModuleFrontController` (rozszerza `ModuleFrontController`)
        *   **Odpowiedzialność**: Ten kontroler może służyć jako rezerwowy lub bezpośredni punkt dostępu do Shoutboxa, gdyby miał on dedykowaną stronę. Biorąc pod uwagę charakter modułu, jest to bardziej prawdopodobne, że jest to symbol zastępczy lub obsługuje początkową logikę renderowania, jeśli Shoutbox jest osadzony bezpośrednio, a nie za pośrednictwem zaczepienia. W większości przypadków Shoutbox jest renderowany za pośrednictwem `shoutbox.tpl` w zaczepieniu.
    *   `controllers/front/insert.php`
        *   **Nazwa klasy**: `ShoutboxInsertModuleFrontController` (rozszerza `ModuleFrontController`)
        *   **Odpowiedzialność**: Ten kontroler obsługuje żądanie AJAX w celu przesyłania nowych wiadomości. Odbiera treść wiadomości (i potencjalnie ID/nazwę użytkownika) z front-endu, wykonuje wszelkie niezbędne walidacje (np. publikowanie przez gości, moderacja), przechowuje wiadomość w bazie danych i zwraca odpowiedź sukcesu/niepowodzenia.
-   **Kontrolery administracyjne Back-Office**:

    *   Brak. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Główne klasy i modele (`classes/`)

Moduł nie definiuje żadnych niestandardowych klas ani `ObjectModel` w katalogu `classes/`. Przechowywanie i pobieranie wiadomości jest obsługiwane bezpośrednio w plikach PHP modułu, prawdopodobnie przy użyciu `Db::getInstance()` do zapytań SQL. Oznacza to, że wiadomości są przechowywane w niestandardowej tabeli utworzonej podczas instalacji lub bezpośrednio w `ps_configuration`, jeśli wiadomości są bardzo nieliczne i proste (chociaż dedykowana tabela jest bardziej prawdopodobna dla wiadomości czatu).

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł opiera się na JavaScript w zakresie funkcjonalności AJAX i dynamicznych aktualizacji.

-   `js/advajax.js`
    *   **Zakres**: Front-office.
    *   **Szczegóły**: Ten plik prawdopodobnie zawiera ogólne narzędzia AJAX lub funkcje opakowujące używane przez moduł. Może zapewniać kompatybilność AJAX między przeglądarkami lub upraszczać proces wysyłania i odbierania danych z kontrolerów front-end. Może to być niestandardowa implementacja lub lekka biblioteka.
-   `js/script.js`
    *   **Zakres**: Front-office.
    *   **Szczegóły**: Jest to główny plik JavaScript dla logiki front-end Shoutboxa.
        *   **Nasłuchiwacze zdarzeń**: Wiąże się ze zdarzeniami przesyłania formularzy w celu publikowania nowych wiadomości i potencjalnie zdarzeniami kliknięć dla działań takich jak czyszczenie wiadomości (jeśli są dostępne w front-end).
        *   **Wywołania AJAX**: Inicjuje żądania AJAX do `ajaxload.php` w celu odświeżania wiadomości w określonym interwale i do `insert.php` w celu przesyłania nowych wiadomości.
        *   **Manipulacja DOM**: Aktualizuje wyświetlanie Shoutboxa nowymi wiadomościami, przewija do dołu czatu i obsługuje czyszczenie pola wprowadzania.
        *   **Timery**: Ustawia `setInterval` do okresowego ładowania wiadomości na podstawie ustawienia „Interwał odświeżania”.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie wymienia jawnie żadnych niestandardowych plików CSS w katalogu `views/css/`. Sugeruje to, że:

1.  Moduł opiera się na stylach wbudowanych lub podstawowych domyślnych stylach przeglądarki.
2.  Może być zaprojektowany tak, aby dziedziczyć styl bezpośrednio z aktywnego motywu PrestaShop, wymagając minimalnego niestandardowego CSS.
3.  Wszelkie style są osadzone bezpośrednio w pliku `shoutbox.tpl` lub głównym pliku PHP modułu.
    Programiści, którzy chcą stylizować Shoutbox, będą musieli zbadać wygenerowany kod HTML i dodać niestandardowe reguły CSS do arkusza stylów swojego motywu, celując w konkretne identyfikatory i klasy używane przez elementy Shoutboxa.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony zaczepień (`views/templates/hook/`)**:
    *   `shoutbox/shoutbox.tpl`
        *   **Renderowane zaczepienia**: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (lub podobne zaczepienie strony produktu). Rzeczywiste zaczepienie zależy od konfiguracji sprzedawcy w Panelu administracyjnym.
        *   **Wyjście bloku wizualnego**: Ten szablon renderuje kompletną strukturę HTML widżetu Shoutbox. Obejmuje to:
            *   Główny kontener dla okna czatu.
            *   Tytuł (np. „Czat Społecznościowy”).
            *   Obszar, w którym wyświetlane są wiadomości (przewijany div).
            *   Pole wprowadzania do wpisywania nowych wiadomości.
            *   Przycisk „Wyślij”.
            *   Warunkowe renderowanie dla możliwości publikowania przez gości.
            *   Będzie również zawierać niezbędny JavaScript i potencjalnie wbudowany CSS.

### 4.7 Schemat bazy danych i mapa zaczepień

-   **Tabele bazy danych**:

    *   Moduł nie deklaruje jawnie niestandardowego `ObjectModel` ani pliku SQL. Przechowywanie wiadomości jest prawdopodobnie obsługiwane bezpośrednio za pośrednictwem `Db::getInstance()` w głównym pliku modułu lub kontrolerach front-end. Typowym wzorcem dla takich modułów jest tworzenie tabeli takiej jak `ps_shoutbox_messages` z polami takimi jak `id_shoutbox_message`, `id_customer`, `customer_name`, `message_content`, `date_add`, `ip_address`, `approved`.
    *   **Rekordy konfiguracji**: Ustawienia modułu (np. `SHOUTBOX_ENABLED`, `SHOUTBOX_TITLE`, `SHOUTBOX_NUM_MESSAGES`, `SHOUTBOX_REFRESH_INTERVAL`, `SHOUTBOX_ALLOW_GUEST`, `SHOUTBOX_MODERATION`, `SHOUTBOX_HOOK`) są przechowywane w tabeli `ps_configuration`.
-   **Tabela zarejestrowanych zaczepień**:

| Nazwa zaczepienia | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` HTML lub na samym początku `<body>`. | Używane do wstrzykiwania plików CSS, JavaScript lub samego widżetu Shoutbox, jeśli jest skonfigurowany do wyświetlania w nagłówku. |
| `displayLeftColumn` | Renderuje zawartość w lewym pasku bocznym sklepu. | Typowe zaczepienie do wyświetlania widżetu Shoutbox jako elementu paska bocznego. |
| `displayRightColumn` | Renderuje zawartość w prawym pasku bocznym sklepu. | Typowe zaczepienie do wyświetlania widżetu Shoutbox jako elementu paska bocznego. |
| `displayFooter` | Renderuje zawartość w sekcji stopki sklepu. | Używane do wyświetlania widżetu Shoutbox na dole strony. |
| `displayProductButtons` (lub podobne zaczepienie strony produktu) | Renderuje zawartość na stronie produktu, często w pobliżu przycisku dodawania do koszyka lub opisu produktu. | Używane do wyświetlania Shoutboxa specjalnie na stronach produktów do dyskusji związanych z produktami. |
| `actionFrontControllerSetMedia` | Wykonywane, gdy kontroler front-end ustawia swoje media (CSS/JS). | Używane do rejestrowania specyficznych dla modułu plików JavaScript (`advajax.js`, `script.js`) i wszelkich potencjalnych plików CSS do załadowania w front office. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu Shoutbox, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu). Nasz dedykowany zespół wsparcia jest gotowy pomóc Ci w przypadku wszelkich problemów lub pytań.
