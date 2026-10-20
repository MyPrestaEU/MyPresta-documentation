---
title: "Udostępnianie produktu na Twitterze + kod kuponu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Udostępnianie produktu na Twitterze + kod kuponu” od MyPresta.eu."
sidebar:
  label: "Udostępnianie produktu na Twitterze + kod kuponu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Twitter product share + voucher code na MyPresta.eu](https://mypresta.eu/modules/social-networks/twitter-product-share-voucher-code.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/twitter-product-share-voucher-code/)
>
> ---


# Udostępnianie produktu na Twitterze + kod kuponu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla PrestaShop i są domyślnie włączone w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Udostępnianie produktu na Twitterze + kod kuponu”, dostępny po instalacji poprzez kliknięcie przycisku „Konfiguruj”. Tutaj zdefiniujesz, jak zachowuje się przycisk udostępniania i jak generowane są kody kuponów.

#### **Ustawienia ogólne**

- **Włącz moduł:**

  - **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania całego modułu.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączony (TAK):* Przycisk udostępniania na Twitterze pojawi się na stronach Twoich produktów (na podstawie wyboru haka), a system generowania kodów kuponów będzie aktywny.
    - *Gdy wyłączony (NIE):* Przycisk udostępniania na Twitterze nie pojawi się, a kody kuponów nie będą generowane dla udostępnień.
  - **Zalecana wartość:** TAK (aby aktywować funkcjonalność modułu).
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli konfigurujesz moduł po raz pierwszy lub wykonujesz konserwację, możesz go tymczasowo wyłączyć. W przeciwnym razie pozostaw go włączonym, aby korzystać z udostępniania społecznościowego.
- **Hak do wyświetlania przycisku:**

  - **Co robi to ustawienie:** Określa, gdzie wizualnie zostanie umieszczony przycisk udostępniania na Twitterze na stronach Twoich produktów.
  - **Efekt zmiany tego ustawienia:**
    - *Opcje (przykłady):* `displayProductButtons`, `displayRightColumnProduct`, `displayFooterProduct`, `displayProductExtraContent`.
    - *Gdy ustawiony na `displayProductButtons` (często):* Przycisk prawdopodobnie pojawi się w pobliżu przycisku „Dodaj do koszyka” lub selektora ilości produktu.
    - *Gdy ustawiony na `displayRightColumnProduct`:* Przycisk pojawi się w prawej kolumnie strony produktu (jeśli Twój motyw ją posiada).
    - *Gdy ustawiony na `displayFooterProduct`:* Przycisk pojawi się w sekcji stopki strony produktu.
  - **Zalecana wartość:** `displayProductButtons` lub `displayProductExtraContent` dla maksymalnej widoczności i zaangażowania, ponieważ są one zazwyczaj blisko głównych informacji o produkcie.
  - **Scenariusz / przykład dla sprzedawcy:** Możesz przetestować różne haki, aby zobaczyć, które umiejscowienie generuje najwięcej udostępnień w Twoim konkretnym motywie. Widoczne miejsce jest zazwyczaj najlepsze.
- **Liczba udostępnień wymagana do otrzymania kuponu:**

  - **Co robi to ustawienie:** Definiuje, ile unikalnych udostępnień produktu musi wykonać klient, zanim otrzyma kupon rabatowy.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawiony na 1:* Klient otrzymuje kupon natychmiast po pierwszym udostępnieniu.
    - *Gdy ustawiony na 3:* Klient musi udostępnić trzy różne produkty (lub ten sam produkt trzy razy, w zależności od wewnętrznej logiki), zanim zostanie wydany kupon.
  - **Zalecana wartość:** 1 (aby zachęcić do natychmiastowego działania i nagrody) lub 2 (aby zachęcić do nieco większego zaangażowania, nie będąc zbyt wymagającym).
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz ułatwić klientom uzyskanie rabatu, ustaw na 1. Jeśli chcesz zachęcić do bardziej obszernego udostępniania, ustaw wyżej, ale pamiętaj, że wyższa liczba może zmniejszyć uczestnictwo.

#### **Ustawienia kodu kuponu**

- **Prefiks kodu kuponu:**

  - **Co robi to ustawienie:** Niestandardowy ciąg znaków, który pojawi się na początku każdego wygenerowanego kodu kuponu.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawiony na `TWITTER-`:* Kod kuponu może wyglądać jak `TWITTER-ABCDE123`.
    - *Gdy pozostawiony pusty:* Kod kuponu będzie składał się z czysto losowych znaków.
  - **Zalecana wartość:** `TWITTER-` lub `SHARE-`, aby łatwo zidentyfikować źródło kuponu.
  - **Scenariusz / przykład dla sprzedawcy:** Użycie prefiksu pomaga śledzić, które kampanie marketingowe generują konkretne kupony w raportach sprzedaży PrestaShop.
- **Wartość kodu kuponu (procent):**

  - **Co robi to ustawienie:** Procentowa zniżka stosowana przez wygenerowany kod kuponu.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawiony na 10:* Kupon da 10% zniżki na zamówienie klienta.
    - *Gdy ustawiony na 5:* Kupon da 5% zniżki.
  - **Zalecana wartość:** 5-15% (w zależności od marży zysku i pożądanego poziomu zachęty).
  - **Scenariusz / przykład dla sprzedawcy:** 10% zniżki jest często dobrym balansem między kuszeniem klientów a utrzymaniem rentowności.
- **Ważność kodu kuponu (dni):**

  - **Co robi to ustawienie:** Ile dni wygenerowany kod kuponu będzie ważny od momentu jego wydania.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawiony na 7:* Kupon wygaśnie 7 dni po otrzymaniu go przez klienta.
    - *Gdy ustawiony na 30:* Kupon będzie ważny przez miesiąc.
  - **Zalecana wartość:** 7-14 dni (aby stworzyć poczucie pilności, nie będąc zbyt restrykcyjnym).
  - **Scenariusz / przykład dla sprzedawcy:** Krótszy okres ważności zachęca klientów do szybszego dokonania zakupu, zamiast zapominania o kuponie.
- **Minimalna kwota, aby kupon był ważny:**

  - **Co robi to ustawienie:** Minimalna całkowita kwota zamówienia (przed wysyłką) wymagana, aby klient mógł użyć kuponu rabatowego.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawiony na 50:* Kupon może być użyty tylko wtedy, gdy suma koszyka klienta wynosi 50 € lub więcej.
    - *Gdy ustawiony na 0 (lub pusty):* Kupon może być użyty dla dowolnej kwoty zamówienia.
  - **Zalecana wartość:** Rozsądna kwota, która zachęca do nieco większego zakupu, lub 0, jeśli chcesz zezwolić na użycie przy dowolnym zamówieniu.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli średnia wartość zamówienia wynosi 40 €, ustawienie minimum 50 € może zachęcić klientów do dodania kolejnego przedmiotu do koszyka, aby osiągnąć próg i skorzystać z rabatu.
- **Opis kodu kuponu:**

  - **Co robi to ustawienie:** Krótki tekstowy opis, który będzie powiązany z kodem kuponu w Twoim panelu administracyjnym PrestaShop (i potencjalnie widoczny dla klienta na jego koncie, jeśli sprawdzi swoje kupony).
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawiony na „Rabat za udostępnienie na Twitterze”:* Ten tekst pojawi się w szczegółach kuponu.
  - **Zalecana wartość:** „Rabat za udostępnienie na Twitterze” lub „Dziękujemy za udostępnienie na Twitterze!”
  - **Scenariusz / przykład dla sprzedawcy:** Pomaga to Tobie i Twoim klientom zrozumieć pochodzenie kuponu.
- **Nazwa kodu kuponu:**

  - **Co robi to ustawienie:** Wewnętrzna nazwa reguły kuponu w PrestaShop. Jest to przede wszystkim dla Twojej wewnętrznej organizacji.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawiony na „Kupon za udostępnienie na Twitterze”:* Ta nazwa pojawi się w sekcji „Reguły koszyka” w PrestaShop.
  - **Zalecana wartość:** „Kupon za udostępnienie na Twitterze” lub „Rabat za udostępnienie społecznościowe”.
  - **Scenariusz / przykład dla sprzedawcy:** Jasna nazwa ułatwia znajdowanie i zarządzanie tymi automatycznie generowanymi kuponami w panelu administracyjnym PrestaShop.

#### **Ustawienia tekstu udostępniania na Twitterze**

- **Domyślny tekst udostępniania:**
  - **Co robi to ustawienie:** Domyślny tekst, który zostanie wstępnie wypełniony w wyskakującym okienku udostępniania na Twitterze, gdy klient kliknie przycisk udostępniania. Ten tekst zostanie połączony z nazwą produktu i linkiem.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawiony na „Sprawdź ten niesamowity produkt!”:* Tweet może wyglądać tak: „Sprawdź ten niesamowity produkt! [Nazwa produktu] [Link do produktu]”.
  - **Zalecana wartość:** Coś angażującego, np. „Sprawdź ten niesamowity produkt ze sklepu [Nazwa Twojego Sklepu]!” lub „Właśnie znalazłem ten świetny produkt!”
  - **Scenariusz / przykład dla sprzedawcy:** Przekonujący domyślny tekst zachęca do większej liczby kliknięć i zaangażowania ze strony obserwujących klienta.

#### **Przycisk Zapisz**

- **Zapisz:**
  - **Co robi ten przycisk:** Stosuje wszystkie zmiany wprowadzone na tej stronie konfiguracji.
  - **Efekt kliknięcia tego przycisku:** Twoje ustawienia są zapisywane w bazie danych, a zachowanie modułu zostanie natychmiast zaktualizowane w Twoim front-office.
  - **Zalecane działanie:** Zawsze kliknij „Zapisz” po wprowadzeniu jakichkolwiek zmian.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz moduł | TAK | Włącza/wyłącza moduł. |
| | Hak do wyświetlania przycisku | `displayProductButtons` | Kontroluje, gdzie przycisk udostępniania pojawia się na stronach produktów. |
| | Liczba udostępnień wymagana do otrzymania kuponu | 1 | Ile udostępnień, zanim klient otrzyma kupon. |
| | Prefiks kodu kuponu | `TWITTER-` | Dodaje niestandardowy prefiks do generowanych kodów kuponów. |
| | Wartość kodu kuponu (procent) | 10 | Procentowa zniżka kuponu. |
| | Ważność kodu kuponu (dni) | 7-14 | Jak długo kupon jest ważny po wygenerowaniu. |
| | Minimalna kwota, aby kupon był ważny | 0 (lub rozsądna kwota) | Minimalna suma koszyka wymagana do użycia kuponu. |
| | Opis kodu kuponu | „Rabat za udostępnienie na Twitterze” | Wewnętrzny opis kuponu. |
| | Nazwa kodu kuponu | „Kupon za udostępnienie na Twitterze” | Wewnętrzna nazwa reguły kuponu. |
| | Domyślny tekst udostępniania | „Sprawdź ten niesamowity produkt!” | Wstępnie wypełniony tekst dla wyskakującego okienka udostępniania na Twitterze. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Przycisk udostępniania na Twitterze nie pojawia się na stronach moich produktów.**

- **O:** Po pierwsze, upewnij się, że moduł jest **włączony** w jego konfiguracji. Po drugie, sprawdź ustawienie **„Hak do wyświetlania przycisku”**. Twój motyw może nie renderować wybranego haka w widocznym miejscu, lub hak może nie istnieć. Spróbuj przełączyć się na inny popularny hak, taki jak `displayProductButtons` lub `displayProductExtraContent`. Jeśli nadal się nie pojawia, Twój motyw może wymagać niestandardowej integracji dla niektórych haków, lub może występować konflikt.
- **Wskazówka dla profesjonalistów:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność) po wprowadzeniu jakichkolwiek zmian w ustawieniach modułu lub plikach motywu.

**P2: Klienci udostępniają, ale nie otrzymują kodów kuponów.**

- **O:**
  1.  **Sprawdź „Liczbę udostępnień wymaganą do otrzymania kuponu”:** Czy jest ustawiona na 1? Jeśli jest wyższa, klienci muszą udostępnić więcej razy, zanim otrzymają kupon.
  2.  **Zweryfikuj ustawienia kuponu:** Upewnij się, że „Wartość kodu kuponu (procent)” jest ustawiona na liczbę większą niż 0, a „Ważność kodu kuponu (dni)” również jest ustawiona.
  3.  **Reguły koszyka PrestaShop:** Sprawdź swój panel administracyjny PrestaShop w **Katalog > Rabaty > Reguły koszyka**. Powinieneś zobaczyć automatycznie wygenerowane kupony z nazwą, którą określiłeś (np. „Kupon za udostępnienie na Twitterze”). Jeśli nowe reguły się nie pojawiają, może występować problem z logiką generowania kuponów.
- **Wskazówka dla profesjonalistów:** Przetestuj proces samodzielnie. Udostępnij produkt ze swojego sklepu, będąc zalogowanym jako klient i sprawdź, czy kupon zostanie wygenerowany.

**P3: Wyskakujące okienko udostępniania na Twitterze wygląda dziwnie lub nie działa poprawnie.**

- **O:** Jest to często spowodowane konfliktami JavaScript z innymi modułami lub Twoim motywem.
  1.  **Sprawdź konsolę przeglądarki:** Otwórz narzędzia deweloperskie przeglądarki (zazwyczaj F12) i poszukaj błędów w zakładce „Konsola” po kliknięciu przycisku udostępniania.
  2.  **Konflikty modułów:** Tymczasowo wyłącz inne moduły, które dodają JavaScript do stron produktów (zwłaszcza moduły udostępniania społecznościowego lub wyskakujących okienek), aby sprawdzić, czy problem zostanie rozwiązany.
- **Wskazówka dla profesjonalistów:** Upewnij się, że Twoja instalacja PrestaShop i motyw są aktualne. Przestarzałe komponenty mogą czasami powodować nieoczekiwane konflikty.

**P4: Czy mogę dostosować wygląd przycisku udostępniania?**

- **O:** Moduł używa własnych stylów CSS (`twittercoupon/css.css` i `twittercoupon/css/css.css`). Możesz nadpisać te style w niestandardowym pliku CSS swojego motywu. Sprawdź przycisk za pomocą narzędzi deweloperskich przeglądarki, aby zidentyfikować jego klasy CSS, a następnie dodaj swoje niestandardowe style do pliku `custom.css` swojego motywu lub równoważnego pliku.
- **Wskazówka dla profesjonalistów:** Unikaj bezpośredniej edycji plików CSS modułu, ponieważ Twoje zmiany zostaną utracone podczas aktualizacji modułu. Zawsze używaj możliwości niestandardowego CSS swojego motywu.

**P5: Jak moduł zapobiega nadużyciom (np. ktoś udostępnia wielokrotnie, aby uzyskać wiele kuponów)?**

- **O:** Moduł zazwyczaj śledzi udostępnienia na klienta (często według adresu IP lub identyfikatora klienta, jeśli jest zalogowany), aby zapobiec generowaniu nieograniczonej liczby kuponów przez jednego użytkownika. Ustawienie „Liczba udostępnień wymagana do otrzymania kuponu” również pomaga w zarządzaniu tym. W przypadku bardziej zaawansowanego zapobiegania oszustwom, możesz potrzebować dodatkowych modułów bezpieczeństwa PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Udostępnianie produktu na Twitterze + kod kuponu” (`twittercoupon`) to standardowy moduł PrestaShop zaimplementowany głównie w jego głównym pliku PHP, `ajax_twittercoupon.php`. Wykorzystuje system haków PrestaShop do wyświetlania w front-office i klasę `Configuration` do przechowywania ustawień. Moduł dynamicznie generuje obiekty `CartRule` (kupony) na podstawie działań użytkownika. Jego funkcjonalność w front-office opiera się na JavaScript do interakcji z API Twittera i punkcie końcowym AJAX w module do przetwarzania udostępnień i wydawania kuponów.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje dedykowanych kontrolerów front-office ani back-office w katalogu `controllers/`. Wszystkie żądania AJAX z front-office i obsługa konfiguracji back-office są zarządzane bezpośrednio w głównym pliku modułu, `ajax_twittercoupon.php`, w szczególności poprzez jego metodę `getContent()` dla konfiguracji i niestandardowe wysyłanie AJAX do przetwarzania udostępnień.

### 4.3 Klasy i modele rdzenia (`classes/`)

Ten moduł nie definiuje niestandardowych klas ani nie rozszerza `ObjectModel` w dedykowanym katalogu `classes/`. Główna logika generowania kuponów bezpośrednio współdziała z klasami `CartRule` i `Configuration` PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł zawiera pliki JavaScript do obsługi interakcji w front-office.

- `twittercoupon/lib/voucherengine/script.js`
  - **Zakres:** Front-office.
  - **Odpowiedzialność:** Wydaje się, że jest to główny skrypt odpowiedzialny za logikę po stronie klienta modułu. Prawdopodobnie obsługuje:
    - Wiązanie zdarzeń kliknięcia z przyciskiem udostępniania na Twitterze.
    - Otwieranie wyskakującego okienka udostępniania na Twitterze (przy użyciu Twitter’s Web Intent API).
    - Wykrywanie udanych udostępnień (prawdopodobnie za pomocą wywołań zwrotnych lub odpytywania).
    - Wykonywanie wywołań AJAX do backendu modułu w celu zarejestrowania udostępnienia i zażądania kuponu.
    - Wyświetlanie kodu kuponu użytkownikowi po pomyślnym wygenerowaniu.
    - Może zawierać logikę zapobiegania wielokrotnym udostępnieniom od tego samego użytkownika w krótkim czasie lub śledzenia liczby udostępnień.
- `twittercoupon/trusted.js`
  - **Zakres:** Front-office.
  - **Odpowiedzialność:** Nazwa „trusted.js” sugeruje, że może być związana z bezpieczeństwem, śledzeniem lub zapewnieniem integralności procesu udostępniania. Potencjalnie może obsługiwać:
    - Walidację po stronie klienta przed zainicjowaniem udostępnienia.
    - Śledzenie interakcji użytkowników w celu zapobiegania oszustwom.
    - Integrację z innymi skryptami śledzącymi lub analitycznymi.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł dostarcza pliki CSS do stylizowania elementów front-office.

- `twittercoupon/css.css`
  - **Zakres:** Stylizacja klienta w front-office.
  - **Odpowiedzialność:** Zawiera główne style dla przycisku udostępniania na Twitterze, wszelkich powiązanych wyskakujących okienek lub wiadomości wyświetlanych klientowi.
  - **Kluczowe selektory klas CSS:** Programiści powinni sprawdzić renderowany kod HTML, aby zidentyfikować konkretne klasy (np. `.twitter-share-button`, `.twitter-coupon-message`), które mają zostać nadpisane w pliku `custom.css` swojego motywu.
- `twittercoupon/css/css.css`
  - **Zakres:** Stylizacja klienta w front-office.
  - **Odpowiedzialność:** Ten plik wydaje się być duplikatem lub alternatywną ścieżką dla głównego CSS. Często moduły mają redundantne ścieżki lub jedna z nich jest awaryjna. Programiści powinni sprawdzić, który z nich jest faktycznie ładowany w przeglądarce.
  - **Kluczowe selektory klas CSS:** Takie same jak powyżej.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa szablonów Smarty do renderowania treści w front-office.

- **Szablony haków (`views/templates/hook/`)**:
  - `twittercoupon/share.tpl`
    - **Hak:** Ten szablon jest renderowany w haku wybranym w konfiguracji modułu (np. `displayProductButtons`, `displayRightColumnProduct`, `displayFooterProduct`).
    - **Cel:** Wyświetla kod HTML dla przycisku „Udostępnij na Twitterze” i potencjalnie placeholder dla wiadomości z kodem kuponu lub wyzwalacza modalnego. Prawdopodobnie będzie zawierał zmienne dla nazwy produktu, adresu URL produktu i domyślnego tekstu udostępniania.

### 4.7 Schemat bazy danych i mapa haków

- **Tabele bazy danych**:

  - Moduł przechowuje swoje ustawienia konfiguracyjne głównie w tabeli `ps_configuration` PrestaShop.
    - `PS_TWITTERCOUPON_ENABLED` (boolean)
    - `PS_TWITTERCOUPON_HOOK` (string)
    - `PS_TWITTERCOUPON_SHARES_REQUIRED` (int)
    - `PS_TWITTERCOUPON_PREFIX` (string)
    - `PS_TWITTERCOUPON_VALUE` (float)
    - `PS_TWITTERCOUPON_VALIDITY` (int)
    - `PS_TWITTERCOUPON_MIN_AMOUNT` (float)
    - `PS_TWITTERCOUPON_DESCRIPTION` (string)
    - `PS_TWITTERCOUPON_NAME` (string)
    - `PS_TWITTERCOUPON_DEFAULT_TEXT` (string)
  - Prawdopodobnie używa również niestandardowej tabeli (np. `ps_twittercoupon_shares` lub podobnej) do śledzenia indywidualnych udostępnień klientów (według `id_customer` lub `ip_address`, `id_product`) i zapobiegania nadużyciom, chociaż nie wymieniono żadnego jawnego pliku SQL, ta logika byłaby obsługiwana w metodzie `install()` głównego modułu. Ta tabela śledziłaby:
    - `id_customer` (jeśli zalogowany)
    - `ip_address`
    - `id_product`
    - `share_date`
    - `voucher_issued` (boolean)
- **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Ładowanie zasobów CSS i JavaScript modułu (`twittercoupon/css.css`, `twittercoupon/lib/voucherengine/script.js`, `twittercoupon/trusted.js`). |
| `displayProductButtons` | Na stronie produktu, zazwyczaj w pobliżu przycisku dodawania do koszyka. | Wyświetlanie przycisku udostępniania na Twitterze (`share.tpl`). |
| `displayRightColumnProduct` | Na stronie produktu, w prawej kolumnie. | Alternatywny hak do wyświetlania przycisku udostępniania na Twitterze (`share.tpl`). |
| `displayFooterProduct` | Na stronie produktu, w obszarze stopki. | Alternatywny hak do wyświetlania przycisku udostępniania na Twitterze (`share.tpl`). |
| `displayProductExtraContent` | Na stronie produktu, często poniżej głównego opisu produktu. | Alternatywny hak do wyświetlania przycisku udostępniania na Twitterze (`share.tpl`). |
| `actionFrontControllerSetMedia` | Przed renderowaniem treści przez kontroler front-office, umożliwiając modułom dodawanie zasobów. | Ładowanie zasobów CSS i JavaScript modułu warunkowo w zależności od strony. |
| (Wewnętrzne wywołanie AJAX) | Wyzwalane przez JavaScript po zdarzeniu udostępnienia. | Przetwarzanie udostępnienia, aktualizacja licznika udostępnień i generowanie `CartRule` (kuponu), jeśli warunki są spełnione. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i dedykowane wsparcie techniczne dla modułu „Udostępnianie produktu na Twitterze + kod kuponu”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnianie terminowej pomocy i optymalnej wydajności Twojego modułu.
