---
title: "Przycisk Google +1 produktu + kupon - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Przycisk Google +1 produktu + kupon” od MyPresta.eu."
sidebar:
  label: "Przycisk Google +1 produktu + kupon - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Google product plus button + coupon na MyPresta.eu](https://mypresta.eu/modules/social-networks/google-product-plus-button-coupon.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/google-product-plus-button-coupon/)
>
> ---


# Przycisk Google +1 produktu + kupon

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i każdego modułu, który wchodzi w interakcje z zewnętrznymi API.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest główny ekran konfiguracji modułu „Przycisk Google +1 produktu + kupon”. Znajdziesz tutaj wszystkie ustawienia, aby kontrolować, jak pojawia się przycisk Google +1 i jak generowane są kupony.

#### **Ustawienia ogólne**

-   **Update\_ / Updatev\_ (Ustawienia wewnętrzne)**

    -   **Co robi to ustawienie:** Są to wewnętrzne ustawienia modułu używane do śledzenia aktualizacji i wersji. Nie są przeznaczone do bezpośredniej interakcji sprzedawcy.
    -   **Skutek zmiany tego ustawienia:** Nigdy **nie** powinieneś ręcznie zmieniać tych wartości. Może to zakłócić aktualizacje modułu lub procesy wewnętrzne.
    -   **Zalecana wartość:** Pozostaw bez zmian.
    -   **Scenariusz / przykład dla sprzedawcy:** Te ustawienia zapewniają, że Twój moduł może być poprawnie aktualizowany, gdy MyPresta.eu wyda nowe wersje.
-   **Kod kuponu (gc\_voucher)**

    -   **Co robi to ustawienie:** Jest to **procent rabatu**, który zostanie zastosowany do kuponu wygenerowanego dla klientów, którzy klikną przycisk +1.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy ustawione na `10` (dla 10%):* Klienci, którzy klikną +1 przy produkcie, otrzymają kupon na 10% zniżki na następny zakup.
        -   *Gdy ustawione na `0` lub pozostawione puste:* Nie zostanie zastosowany żaden rabat, co zasadniczo sprawi, że kupon będzie bezwartościowy.
    -   **Zalecana wartość:** Rozsądny procent rabatu, np. `5`, `10` lub `15`.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz zaoferować 10% rabatu, aby zachęcić do udostępniania społecznościowego. Wprowadziłbyś tutaj `10`.
-   **Pokaż ceny (gc\_show\_prices)**

    -   **Co robi to ustawienie:** Określa, czy oryginalne i przecenione ceny są wyświetlane wraz z ofertą kuponu.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Klient zobaczy oryginalną cenę i cenę po zastosowaniu rabatu, co sprawi, że wartość kuponu będzie jaśniejsza.
        -   *Gdy wyłączone (Nie):* Zostanie wyświetlony tylko kod kuponu, bez wyraźnych porównań cen.
    -   **Zalecana wartość:** `Tak`. Pokazywanie różnicy w cenie często zwiększa postrzeganą wartość kuponu.
    -   **Scenariusz / przykład dla sprzedawcy:** Klient widzi produkt za 100 zł. Jeśli „Pokaż ceny” jest włączone, a kupon wynosi 10%, zobaczy „100 zł -> 90 zł z kuponem”, co jest bardziej przekonujące.
-   **Pokaż sumę (gc\_show\_total)**

    -   **Co robi to ustawienie:** Kontroluje, czy całkowita wartość zamówienia (po rabacie) jest wyświetlana z kuponem. Jest to zazwyczaj istotne, jeśli kupon dotyczy całego koszyka.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Klient może zobaczyć szacunkową całkowitą wartość zamówienia z zastosowanym rabatem.
        -   *Gdy wyłączone (Nie):* Skupienie pozostaje na cenie produktu lub samym kodzie kuponu.
    -   **Zalecana wartość:** `Tak`, zwłaszcza jeśli kupon dotyczy całego koszyka, ponieważ pomaga klientowi wizualizować swoje oszczędności.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli kupon dotyczy całego koszyka, pokazanie potencjalnych całkowitych oszczędności może zachęcić do większego zakupu.
-   **Pokaż produkty (gc\_show\_products)**

    -   **Co robi to ustawienie:** Określa, czy konkretne produkty, do których kupon ma zastosowanie, są wymienione, gdy kupon jest wyświetlany.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Komunikat kuponu może wyraźnie stwierdzać „Ten kupon dotyczy [Nazwa produktu]”.
        -   *Gdy wyłączone (Nie):* Kupon jest prezentowany bardziej ogólnie, lub zakłada się, że dotyczy produktu, który właśnie został +1.
    -   **Zalecana wartość:** `Tak`, dla jasności, chyba że Twój kupon zawsze dotyczy całego sklepu.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój kupon jest tylko na produkt, który klient +1, pokazanie nazwy produktu wyjaśnia jego użycie.
-   **Pokaż URL produktu (gc\_show\_product\_url)**

    -   **Co robi to ustawienie:** Kontroluje, czy adres URL produktu, który został +1, jest uwzględniony w wyświetlaczu kuponu.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Klient widzi bezpośredni link z powrotem do strony produktu, co może być przydatne, jeśli odejdzie.
        -   *Gdy wyłączone (Nie):* Adres URL jest pominięty.
    -   **Zalecana wartość:** `Tak`, dla lepszego doświadczenia użytkownika i nawigacji.
    -   **Scenariusz / przykład dla sprzedawcy:** Klient otrzymuje kupon, a następnie zamyka wyskakujące okienko. Posiadanie adresu URL produktu pomaga mu szybko wrócić do produktu, którym był zainteresowany.
-   **Ostatnia zakładka (gc\_lasttab)**

    -   **Co robi to ustawienie:** To ustawienie prawdopodobnie kontroluje, w której zakładce lub sekcji strony produktu pojawi się przycisk Google +1 i informacje o kuponie, jeśli Twój motyw używa obszaru opisu produktu z zakładkami.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy ustawione na `1` (lub podobną wartość):* Zawartość modułu pojawi się w ostatniej zakładce strony produktu.
        -   *Gdy ustawione na `0` (lub podobną wartość):* Zawartość modułu pojawi się w pierwszej zakładce lub domyślnej lokalizacji.
    -   **Zalecana wartość:** Eksperymentuj z `1`, aby sprawdzić, czy pasuje do układu Twojego motywu. Jeśli Twój motyw nie używa zakładek, to ustawienie może nie mieć widocznego efektu.
    -   **Scenariusz / przykład dla sprzedawcy:** Twoja strona produktu ma zakładki „Opis”, „Karta danych” i „Recenzje”. Ustawienie tego na `1` może umieścić przycisk +1 i kupon w nowej zakładce „Udostępnij społecznościowo” lub na końcu zakładki „Opis”.
-   **Pozycja (gc\_position)**

    -   **Co robi to ustawienie:** Określa ogólny obszar na stronie produktu, gdzie zostanie wyświetlony przycisk Google +1 i oferta kuponu. Odpowiada to systemowi hooków PrestaShop.
    -   **Skutek zmiany tego ustawienia:**
        -   *Zmiana wartości:* Przenosi zawartość modułu w różne miejsca na stronie produktu (np. powyżej „Dodaj do koszyka”, poniżej opisu, w bocznej kolumnie).
    -   **Zalecana wartość:** `displayproductActions` lub `displayproductFooter` to popularne i skuteczne miejsca. Przetestuj różne pozycje, aby zobaczyć, co najlepiej integruje się z Twoim motywem i jest najbardziej widoczne dla klientów.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby przycisk +1 był bardzo widoczny, więc wybierasz `displayproductActions`, aby umieścić go w pobliżu przycisku „Dodaj do koszyka”.
-   **Liczba polubień (gc\_nblikes)**

    -   **Co robi to ustawienie:** To ustawienie prawdopodobnie kontroluje minimalną liczbę +1 wymaganych przed wydaniem kuponu, lub może być ustawieniem wyświetlania liczby +1. Biorąc pod uwagę podstawową funkcjonalność modułu, bardziej prawdopodobne jest, że jest to związane z wyzwalaczem kuponu.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy ustawione na `1` (lub `0`):* Kupon jest wydawany natychmiast po pojedynczym +1.
        -   *Gdy ustawione na `5`:* Kupon może być wydany dopiero po 5 unikalnych +1 (mniej prawdopodobne, biorąc pod uwagę charakter natychmiastowej nagrody, ale możliwe dla funkcji „kuponu grupowego”). Bardziej prawdopodobne jest, że kontroluje wyświetlanie liczby +1.
    -   **Zalecana wartość:** `1` (lub `0`, jeśli oznacza „zawsze pokazuj”). Siłą modułu jest natychmiastowa gratyfikacja.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby każdy klient, który kliknie +1, otrzymał kupon, więc ustawiasz to na `1`.
-   **Styl przycisku (gc\_button\_style)**

    -   **Co robi to ustawienie:** Pozwala wybrać styl wizualny lub rozmiar przycisku Google +1.
    -   **Skutek zmiany tego ustawienia:**
        -   *Zmiana wartości:* Zmienia wygląd przycisku +1 (np. mały, średni, duży, wysoki, z licznikiem lub bez).
    -   **Zalecana wartość:** Wybierz styl, który jest widoczny, ale nie zakłóca projektu strony produktu. „Średni” lub „Standardowy” to zazwyczaj dobre punkty wyjścia.
    -   **Scenariusz / przykład dla sprzedawcy:** Twoja strona produktu ma ograniczoną przestrzeń, więc wybierasz „mały” styl przycisku.
-   **Tryb udostępniania (gcshare\_mode)**

    -   **Co robi to ustawienie:** To ustawienie prawdopodobnie kontroluje, jak działa funkcja udostępniania, być może oferując różne sposoby udostępniania lub interakcji klienta z platformą Google+.
    -   **Skutek zmiany tego ustawienia:**
        -   *Zmiana wartości:* Może zmienić zachowanie wyskakującego okienka lub konkretne okno dialogowe udostępniania Google+.
    -   **Zalecana wartość:** Pozostaw domyślną, chyba że masz konkretny powód, aby ją zmienić i rozumiesz konsekwencje dla integracji z Google+.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz eksperymentować z różnymi trybami, jeśli okaże się, że domyślne doświadczenie udostępniania nie jest optymalne dla Twoich klientów.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Kod kuponu (gc\_voucher) | 10 | Procent rabatu dla wygenerowanego kuponu. |
| Konfiguracja modułu | Pokaż ceny (gc\_show\_prices) | Tak | Wyświetla oryginalne i przecenione ceny z kuponem. |
| Konfiguracja modułu | Pokaż sumę (gc\_show\_total) | Tak | Wyświetla szacunkową całkowitą wartość zamówienia z rabatem. |
| Konfiguracja modułu | Pokaż produkty (gc\_show\_products) | Tak | Wyświetla listę konkretnych produktów, do których kupon ma zastosowanie. |
| Konfiguracja modułu | Pokaż URL produktu (gc\_show\_product\_url) | Tak | Uwzględnia URL produktu w wyświetlaczu kuponu. |
| Konfiguracja modułu | Ostatnia zakładka (gc\_lasttab) | 1 (lub zależne od motywu) | Pozycja w zakładkach strony produktu (jeśli dotyczy). |
| Konfiguracja modułu | Pozycja (gc\_position) | displayproductActions / displayproductFooter | Ogólne umiejscowienie przycisku i kuponu na stronie produktu. |
| Konfiguracja modułu | Liczba polubień (gc\_nblikes) | 1 | Minimalna liczba +1 dla kuponu (prawdopodobnie 1 dla natychmiastowej nagrody). |
| Konfiguracja modułu | Styl przycisku (gc\_button\_style) | Standardowy / Średni | Wizualny rozmiar i styl przycisku Google +1. |
| Konfiguracja modułu | Tryb udostępniania (gcshare\_mode) | Domyślny | Kontroluje interakcję udostępniania Google+. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

-   **P: Przycisk Google +1 nie pojawia się na stronach moich produktów.**

    -   **O:** Najpierw sprawdź ustawienie „Pozycja (gc\_position)” w konfiguracji modułu. Upewnij się, że wybrałeś hook, który jest faktycznie renderowany przez Twój motyw na stronie produktu. Niektóre niestandardowe motywy mogą nie implementować wszystkich standardowych hooków PrestaShop.
    -   **O:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).
    -   **O:** Sprawdź, czy nie ma błędów JavaScript w konsoli programisty przeglądarki (F12). Konflikty z innymi modułami lub skryptami motywu mogą czasami uniemożliwić ładowanie przycisków.
    -   **O:** Upewnij się, że moduł jest włączony w Menedżerze modułów.
-   **P: Klienci klikają +1, ale nie otrzymują kuponu.**

    -   **O:** Sprawdź, czy ustawienie „Kod kuponu (gc\_voucher)” ma prawidłowy procent rabatu (np. `10` dla 10%). Jeśli jest `0` lub puste, nie zostanie wygenerowany żaden skuteczny kupon.
    -   **O:** Sprawdź ustawienie „Liczba polubień (gc\_nblikes)”. Jeśli jest ustawione na wartość większą niż 1, kupon nie zostanie wydany, dopóki ten próg nie zostanie osiągnięty. Dla natychmiastowych kuponów powinno być 1.
    -   **O:** Upewnij się, że nie ma błędów po stronie serwera uniemożliwiających generowanie kuponów. Sprawdź logi błędów PrestaShop (Zaawansowane > Logi).
-   **P: Przycisk wygląda dziwnie lub jest źle wyrównany na mojej stronie mobilnej.**

    -   **O:** Jest to często konflikt CSS z Twoim motywem. Moduł zawiera własny CSS, ale style Twojego motywu mogą go nadpisywać lub z nim kolidować. Może być konieczne, aby programista internetowy zbadał CSS i dokonał drobnych korekt.
    -   **O:** Wypróbuj różne opcje „Styl przycisku (gc\_button\_style)”, aby sprawdzić, czy inny rozmiar renderuje się lepiej.
-   **P: Czy mogę dostosować wiadomość kuponu lub jego ważność?**

    -   **O:** Konfiguracja modułu kontroluje głównie procent rabatu i opcje wyświetlania. W przypadku zaawansowanych reguł kuponów (np. minimalny zakup, konkretne kategorie, okres ważności), zazwyczaj zarządzasz nimi w natywnych sekcjach PrestaShop „Reguły cen katalogowych” lub „Reguły koszyka” (Rabaty), a moduł wygeneruje kod, który będzie zgodny z tymi regułami, jeśli ma to zastosowanie, lub może być konieczne ręczne utworzenie konkretnej reguły, która pasuje do kuponu wygenerowanego przez moduł. Sam moduł generuje podstawowy rabat procentowy.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowe informacje techniczne na temat modułu „Przycisk Google +1 produktu + kupon” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie klasę `Module` oraz jej metody `install()`, `uninstall()` i `getContent()`. Integruje się z front-office za pomocą różnych hooków wyświetlania, aby wstrzyknąć przycisk Google +1 i powiązaną logikę kuponów. Generowanie i wyświetlanie kuponów jest obsługiwane dynamicznie za pomocą JavaScript i szablonów Smarty. Nie ma niestandardowych klas `ObjectModel` ani dedykowanych kontrolerów administracyjnych poza główną konfiguracją modułu.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Cała funkcjonalność front-office jest obsługiwana za pomocą hooków modułu i bezpośredniego renderowania szablonów.
-   **Kontrolery Back-Office Admin**: Brak. Konfiguracja odbywa się w całości w metodzie `getContent()` głównego modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   W katalogu `classes/` nie ma niestandardowych klas ani definicji `ObjectModel`. Cała podstawowa logika znajduje się w `googlecoupon/googlecoupon.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `googlecoupon/lib/voucherengine/script.js`
    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Ten skrypt jest prawdopodobnie odpowiedzialny za podstawową logikę generowania i wyświetlania kuponów. Będzie nasłuchiwał zdarzenia kliknięcia przycisku Google +1, wyzwalał proces generowania kuponu (prawdopodobnie za pośrednictwem wywołania AJAX do głównego pliku modułu lub bezpośredniej funkcji JavaScript), a następnie wyświetlał kod kuponu użytkownikowi. Może również obsługiwać interakcję z API Google+ (chociaż API Google+ zostały w dużej mierze wycofane lub zintegrowane z innymi usługami).
-   `googlecoupon/trusted.js`
    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Cel tego skryptu jest mniej jasny z samej nazwy, ale może być związany z zapewnieniem integralności akcji +1, śledzeniem lub integracją z innymi zaufanymi usługami. Może to być również pozostałość po starszych integracjach API Google+.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `googlecoupon/css.css`
    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Zapewnia podstawowe style dla przycisku Google +1, obszaru wyświetlania kuponu oraz wszelkich powiązanych wyskakujących okienek lub powiadomień.
    -   **Kluczowe selektory klas CSS:** Programiści powinni sprawdzić ten plik, aby zidentyfikować konkretne klasy (np. `.googlecoupon-button-container`, `.googlecoupon-voucher-display`, `.googlecoupon-modal`), które można nadpisać w pliku `custom.css` lub `theme.css` niestandardowego motywu, aby dopasować je do brandingu sklepu.
-   `googlecoupon/css/css.css`
    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Wydaje się, że jest to duplikat lub alternatywny arkusz stylów. Ważne jest, aby sprawdzić, czy oba są ładowane, czy jeden jest rezerwowym. Prawdopodobnie zawiera podobne reguły stylów jak `googlecoupon/css.css`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**: Brak jawnie wymienionych, ale `share.tpl` prawdopodobnie służy temu celowi.
-   **Szablony administracyjne (`views/templates/admin/`)**: Brak.
-   **Szablony Front-office (`views/templates/front/`)**: Brak jawnie wymienionych, ale `share.tpl` jest kluczowym szablonem front-office.
    -   `googlecoupon/share.tpl`
        -   **Zakres:** Front-office.
        -   **Cel:** Ten szablon jest odpowiedzialny za renderowanie przycisku Google +1 i kontenera, w którym będą wyświetlane informacje o kuponie. Zostanie on wstrzyknięty do różnych hooków front-office skonfigurowanych w module. Prawdopodobnie zawiera symbole zastępcze dla skryptu Google+ i dynamicznie generowanego kodu kuponu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie wydaje się tworzyć niestandardowych tabel SQL.
    -   Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `GC_VOUCHER`, `GC_SHOW_PRICES`, `GC_SHOW_TOTAL`, `GC_SHOW_PRODUCTS`, `GC_SHOW_PRODUCT_URL`, `GC_LASTTAB`, `GC_POSITION`, `GC_NBLIKES`, `GC_BUTTON_STYLE`, `GCSHARE_MODE`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayproductActions` | Na stronie produktu, zazwyczaj w pobliżu przycisku „Dodaj do koszyka”. | Wstrzykuje przycisk Google +1 i wyświetlanie kuponu w widocznym miejscu. |
| `displayproductFooter` | Na stronie produktu, na dole bloku informacji o produkcie. | Wstrzykuje przycisk Google +1 i wyświetlanie kuponu po głównych szczegółach produktu. |
| `productFooter` | Na stronie produktu, podobnie do `displayproductFooter`, często używany do dodatkowej zawartości. | Alternatywne umiejscowienie przycisku Google +1 i wyświetlania kuponu. |
| `extraLeft` | Na stronie produktu, w lewej kolumnie (jeśli włączone przez motyw). | Umieszcza zawartość modułu w lewym pasku bocznym. |
| `productActions` | Na stronie produktu, szczególnie wokół przycisków „Dodaj do koszyka” i selektorów ilości. | Alternatywne umiejscowienie przycisku Google +1 i wyświetlania kuponu, często bardzo widoczne. |
| `displayextraleft` | Na stronie produktu, w lewej kolumnie. | Podobnie do `extraLeft`, do wstrzykiwania zawartości do lewego paska bocznego. |
| `extraRight` | Na stronie produktu, w prawej kolumnie (jeśli włączone przez motyw). | Umieszcza zawartość modułu w prawym pasku bocznym. |
| `displayextraright` | Na stronie produktu, w prawej kolumnie. | Podobnie do `extraRight`, do wstrzykiwania zawartości do prawego paska bocznego. |
| `displayHeader` | W sekcji `<head>` każdej strony. | Służy do dołączania niezbędnych plików CSS i JavaScript dla modułu. |
| `header` | W sekcji `<head>` każdej strony (starsze wersje PrestaShop). | Podobnie do `displayHeader`, do dołączania zasobów. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego oraz pobrania najnowszych wersji modułu „Przycisk Google +1 produktu + kupon”, zaloguj się na swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
