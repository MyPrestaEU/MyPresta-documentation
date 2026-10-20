---
title: "Kupony w responsywnym wyskakującym okienku - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Kupony w responsywnym wyskakującym okienku” od MyPresta.eu."
sidebar:
  label: "Kupony w responsywnym wyskakującym okienku - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Responsive popup coupons na MyPresta.eu](https://mypresta.eu/modules/social-networks/responsive-popup-coupons.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/responsive-popup-coupons/)
>
> ---


# Kupony w responsywnym wyskakującym okienku

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 1.6.x, 1.5.x, 1.4.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i domyślnie włączone w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji, na którym ustawisz wszystkie parametry dla swoich kuponów w wyskakujących okienkach.

#### Ustawienia ogólne

-   **Włącz moduł:**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania całej funkcjonalności kuponów w wyskakujących okienkach dla Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Wyskakujące okienko zacznie pojawiać się na wybranych stronach zgodnie z innymi ustawieniami.
        -   *Gdy wyłączony:* Wyskakujące okienko nie pojawi się nigdzie w Twoim sklepie, niezależnie od innych ustawień.
    -   **Zalecana wartość:** TAK (gdy chcesz używać modułu).
    -   **Scenariusz / przykład sprzedawcy:** Prowadzisz promocję świąteczną i chcesz aktywować wyskakujące okienko na ograniczony czas. Włączasz je na początku i wyłączasz po zakończeniu promocji.
-   **Wyświetl na:**

    -   **Co robi to ustawienie:** Pozwala wybrać, na jakich typach stron wyskakujące okienko będzie wyświetlane Twoim klientom.
    -   **Efekt zmiany tego ustawienia:**
        -   *Strona główna:* Wyskakujące okienko pojawia się tylko na głównej stronie Twojego sklepu.
        -   *Strony kategorii:* Wyskakujące okienko pojawia się, gdy klienci przeglądają kategorie produktów.
        -   *Strony produktów:* Wyskakujące okienko pojawia się, gdy klienci przeglądają szczegóły poszczególnych produktów.
        -   *Strony CMS:* Wyskakujące okienko pojawia się na stronach informacyjnych, takich jak „O nas” lub „Kontakt”.
        -   *Wszystkie strony:* Wyskakujące okienko pojawia się na każdej stronie Twojego sklepu.
    -   **Zalecana wartość:** Strony produktów lub Wszystkie strony (w zależności od Twojej strategii marketingowej).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz zachęcić do zakupów bezpośrednio na stronach produktów, więc wybierasz „Strony produktów”. Jeśli chcesz maksymalnej ekspozycji, możesz wybrać „Wszystkie strony”.
-   **Opóźnienie (w sekundach) przed pojawieniem się wyskakującego okienka:**

    -   **Co robi to ustawienie:** Kontroluje, jak długo po załadowaniu strony wyskakujące okienko będzie czekać przed pojawieniem się.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ustawione na 0:* Wyskakujące okienko pojawia się natychmiast po załadowaniu strony.
        -   *Ustawione na 5:* Wyskakujące okienko pojawia się 5 sekund po załadowaniu strony.
    -   **Zalecana wartość:** 3-5 sekund (pozwala klientom najpierw zobaczyć zawartość).
    -   **Scenariusz / przykład sprzedawcy:** Nie chcesz natychmiast przytłaczać klientów. Ustawienie 3-sekundowego opóźnienia daje im chwilę na zorientowanie się, zanim pojawi się oferta.
-   **Wyświetl wyskakujące okienko tylko raz na sesję:**

    -   **Co robi to ustawienie:** Określa, czy klient zobaczy wyskakujące okienko wielokrotnie podczas jednej wizyty w Twoim sklepie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Gdy klient zobaczy wyskakujące okienko (i potencjalnie je zamknie), nie zobaczy go ponownie, dopóki nie zamknie przeglądarki i nie rozpocznie nowej sesji.
        -   *Gdy wyłączone:* Wyskakujące okienko może pojawiać się za każdym razem, gdy odwiedzi stronę, na której jest skonfigurowane do wyświetlania.
    -   **Zalecana wartość:** TAK (aby uniknąć irytowania klientów).
    -   **Scenariusz / przykład sprzedawcy:** Klient odwiedza kilka stron produktów. Jeśli to ustawienie jest włączone, widzi ofertę kuponu tylko raz, co zapobiega irytacji.
-   **Wyświetl wyskakujące okienko tylko raz na klienta (na zawsze):**

    -   **Co robi to ustawienie:** Jest to bardziej trwałe ustawienie, zapobiegające ponownemu wyświetlaniu wyskakującego okienka zalogowanemu klientowi, gdy już raz je zobaczył.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł zapamiętuje, że konkretny klient (za pośrednictwem jego konta) widział wyskakujące okienko i nie pokaże mu go ponownie, nawet w przyszłych sesjach.
        -   *Gdy wyłączone:* Obowiązuje zasada „raz na sesję”, a jeśli jest wyłączona, będą widzieć je wielokrotnie.
    -   **Zalecana wartość:** TAK (dla mniej inwazyjnego doświadczenia dla lojalnych klientów).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz dać każdemu klientowi szansę na uzyskanie kuponu, ale nie przypominać mu o tym ciągle, jeśli już go widział lub użył.
-   **Wyświetl wyskakujące okienko tylko dla gości (niezalogowanych klientów):**

    -   **Co robi to ustawienie:** Ogranicza widoczność wyskakującego okienka tylko do odwiedzających, którzy nie są zalogowani na konto klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Tylko nowi lub powracający niezalogowani odwiedzający zobaczą wyskakujące okienko. Zalogowani klienci nie.
        -   *Gdy wyłączone:* Zarówno goście, jak i zalogowani klienci zobaczą wyskakujące okienko (z zastrzeżeniem innych zasad wyświetlania).
    -   **Zalecana wartość:** TAK (często chcesz konwertować nowych odwiedzających, a niekoniecznie oferować zniżki istniejącym lojalnym klientom).
    -   **Scenariusz / przykład sprzedawcy:** Twoim celem jest przyciągnięcie nowych klientów lub zachęcenie do pierwszych zakupów. Włączasz to, aby skupić swoją ofertę na potencjalnych nowych klientach.
-   **Wyświetl wyskakujące okienko tylko dla wybranych grup klientów:**

    -   **Co robi to ustawienie:** Pozwala kierować wyskakujące okienko do określonych grup klientów (np. „Odwiedzający”, „Klienci”, „Goście” lub niestandardowe grupy, które utworzyłeś).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrane są konkretne grupy:* Tylko klienci należący do tych grup zobaczą wyskakujące okienko.
        -   *Gdy nie wybrano żadnych grup (lub wybrano wszystkie):* Wszyscy klienci zobaczą wyskakujące okienko (z zastrzeżeniem innych zasad).
    -   **Zalecana wartość:** Wybierz „Goście” i „Odwiedzający”, jeśli Twoim celem jest pozyskiwanie nowych klientów.
    -   **Scenariusz / przykład sprzedawcy:** Chcesz zaoferować specjalną zniżkę tylko swojej grupie klientów VIP. Wybierzesz tutaj tylko tę grupę.
-   **Wyświetl wyskakujące okienko tylko dla wybranych krajów:**

    -   **Co robi to ustawienie:** Ogranicza pojawianie się wyskakującego okienka na podstawie lokalizacji geograficznej klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrane są konkretne kraje:* Tylko klienci z tych krajów zobaczą wyskakujące okienko.
        -   *Gdy nie wybrano żadnych krajów (lub wybrano wszystkie):* Wszyscy klienci zobaczą wyskakujące okienko.
    -   **Zalecana wartość:** Wybierz konkretne kraje, jeśli masz promocje ukierunkowane geograficznie, w przeciwnym razie pozostaw puste.
    -   **Scenariusz / przykład sprzedawcy:** Prowadzisz promocję wyłącznie dla klientów we Francji i Niemczech. Wybierzesz tylko te dwa kraje.
-   **Wyświetl wyskakujące okienko tylko dla wybranych walut:**

    -   **Co robi to ustawienie:** Kontroluje widoczność wyskakującego okienka na podstawie waluty, której klient aktualnie używa w Twoim sklepie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrane są konkretne waluty:* Tylko klienci używający tych walut zobaczą wyskakujące okienko.
        -   *Gdy nie wybrano żadnych walut (lub wybrano wszystkie):* Wszyscy klienci zobaczą wyskakujące okienko.
    -   **Zalecana wartość:** Wybierz konkretne waluty, jeśli Twoja promocja jest zależna od waluty, w przeciwnym razie pozostaw puste.
    -   **Scenariusz / przykład sprzedawcy:** Masz specjalną ofertę dla klientów płacących w USD. Wybierzesz tutaj tylko USD.
-   **Wyświetl wyskakujące okienko tylko dla wybranych języków:**

    -   **Co robi to ustawienie:** Określa, czy wyskakujące okienko pojawia się na podstawie języka wybranego przez klienta dla Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrane są konkretne języki:* Tylko klienci przeglądający Twój sklep w tych językach zobaczą wyskakujące okienko.
        -   *Gdy nie wybrano żadnych języków (lub wybrano wszystkie):* Wszyscy klienci zobaczą wyskakujące okienko.
    -   **Zalecana wartość:** Wybierz konkretne języki, jeśli zawartość wyskakującego okienka jest przetłumaczona tylko na niektóre języki, w przeciwnym razie pozostaw puste.
    -   **Scenariusz / przykład sprzedawcy:** Twoja wiadomość w wyskakującym okienku jest dostępna tylko w języku angielskim i hiszpańskim. Wybierzesz te dwa języki, aby upewnić się, że klienci zobaczą odpowiednią wiadomość.

#### Ustawienia kuponu

-   **Wartość bonu:**

    -   **Co robi to ustawienie:** Definiuje kwotę zniżki lub procent oferowany przez kupon.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ustawione na 10:* Kupon zapewni zniżkę w wysokości 10 jednostek (np. 10 USD, 10 EUR).
        -   *Ustawione na 15%:* Kupon zapewni 15% zniżki.
    -   **Zalecana wartość:** Atrakcyjna zniżka (np. 10%, 5 USD, 10 EUR).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz zaoferować 10% zniżki, więc wpisujesz tutaj „10%”.
-   **Typ bonu:**

    -   **Co robi to ustawienie:** Określa, czy bon jest stałą kwotą, czy procentem.
    -   **Efekt zmiany tego ustawienia:**
        -   *Procent:* „Wartość bonu” będzie traktowana jako procent całkowitej wartości zamówienia.
        -   *Kwota:* „Wartość bonu” będzie traktowana jako stała kwotowa redukcja.
    -   **Zalecana wartość:** Procent (często bardziej atrakcyjny dla różnych rozmiarów zamówień).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz dać 10% zniżki, więc wybierasz „Procent”. Jeśli chcesz dać stałe 5 USD zniżki, wybierasz „Kwota”.
-   **Minimalna kwota bonu:**

    -   **Co robi to ustawienie:** Ustawia minimalną wartość zamówienia, którą klient musi osiągnąć, aby móc użyć kuponu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ustawione na 50:* Kupon może być użyty tylko wtedy, gdy całkowita wartość koszyka wynosi 50 USD lub więcej.
        -   *Ustawione na 0 (lub puste):* Nie jest wymagana minimalna kwota zamówienia.
    -   **Zalecana wartość:** Rozsądne minimum, aby chronić Twoje marże, lub 0, jeśli chcesz zachęcić do każdego zakupu.
    -   **Scenariusz / przykład sprzedawcy:** Chcesz upewnić się, że zniżka jest stosowana tylko do zamówień powyżej 50 USD, więc wpisujesz „50”.
-   **Wygasa bon (w dniach):**

    -   **Co robi to ustawienie:** Definiuje, ile dni wygenerowany kod kuponu będzie ważny od momentu jego wydania.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ustawione na 7:* Kupon wygaśnie 7 dni po otrzymaniu go przez klienta.
        -   *Ustawione na 0 (lub puste):* Kupon nie wygaśnie.
    -   **Zalecana wartość:** 7-30 dni (tworzy pilność, nie będąc zbyt restrykcyjnym).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz, aby klienci szybko wykorzystali kupon, więc ustawiasz wygaśnięcie na 7 dni.
-   **Opis bonu:**

    -   **Co robi to ustawienie:** Zapewnia opisową nazwę kuponu w Twoim panelu administracyjnym PrestaShop (np. w sekcji „Reguły koszyka”). Jest to dla Twojego wewnętrznego odniesienia.
    -   **Efekt zmiany tego ustawienia:** Ten tekst pojawi się w Twoim panelu administracyjnym PrestaShop, gdy będziesz przeglądać wygenerowane reguły koszyka, pomagając Ci zidentyfikować ich pochodzenie. Nie jest widoczny dla klienta.
    -   **Zalecana wartość:** „Kupon z wyskakującego okienka - [Data]” lub „Zniżka za polubienie na Facebooku”.
    -   **Scenariusz / przykład sprzedawcy:** Wpisujesz „Zniżka za polubienie na Facebooku z wyskakującego okienka”, aby wiedzieć dokładnie, skąd pochodzą te kupony, przeglądając swoje reguły koszyka.
-   **Bon darmowa wysyłka:**

    -   **Co robi to ustawienie:** Określa, czy kupon również przyznaje darmową wysyłkę na zamówienie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klient nie zostanie obciążony kosztami wysyłki, używając tego kuponu.
        -   *Gdy wyłączone:* Obowiązywać będą standardowe koszty wysyłki.
    -   **Zalecana wartość:** NIE (chyba że chcesz zaoferować darmową wysyłkę jako silną zachętę).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz zaoferować bardzo atrakcyjną ofertę, więc włączasz darmową wysyłkę wraz ze zniżką.
-   **Bon zastosuj do konkretnych produktów:**

    -   **Co robi to ustawienie:** Pozwala ograniczyć użycie kuponu tylko do niektórych produktów w Twoim sklepie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrane są konkretne produkty:* Kupon zadziała tylko wtedy, gdy te produkty znajdują się w koszyku.
        -   *Gdy nie wybrano żadnych produktów:* Kupon dotyczy wszystkich produktów w koszyku.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretną promocję produktu.
    -   **Scenariusz / przykład sprzedawcy:** Promujesz nową linię butów. Wybierasz tutaj tylko te buty, więc kupon działa tylko na nie.
-   **Bon zastosuj do konkretnych kategorii:**

    -   **Co robi to ustawienie:** Pozwala ograniczyć użycie kuponu do produktów w określonych kategoriach.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrane są konkretne kategorie:* Kupon zadziała tylko wtedy, gdy produkty z tych kategorii znajdują się w koszyku.
        -   *Gdy nie wybrano żadnych kategorii:* Kupon dotyczy wszystkich produktów.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretną promocję kategorii.
    -   **Scenariusz / przykład sprzedawcy:** Chcesz wyprzedać stary zapas w kategorii „Kolekcja letnia”. Wybierasz tutaj tę kategorię.
-   **Bon zastosuj do konkretnych producentów:**

    -   **Co robi to ustawienie:** Pozwala ograniczyć użycie kuponu do produktów od konkretnych marek/producentów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy wybrani są konkretni producenci:* Kupon zadziała tylko wtedy, gdy produkty od tych producentów znajdują się w koszyku.
        -   *Gdy nie wybrano żadnych producentów:* Kupon dotyczy wszystkich produktów.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretną promocję marki.
    -   **Scenariusz / przykład sprzedawcy:** Masz partnerstwo z konkretną marką i chcesz zaoferować zniżkę tylko na ich produkty.

#### Projekt i zawartość wyskakującego okienka

-   **Szerokość wyskakującego okienka (w pikselach):**

    -   **Co robi to ustawienie:** Kontroluje poziomą wielkość okna wyskakującego okienka.
    -   **Efekt zmiany tego ustawienia:** Większa liczba sprawia, że wyskakujące okienko jest szersze, mniejsza liczba sprawia, że jest węższe.
    -   **Zalecana wartość:** 600px - 800px (dla dobrej widoczności na komputerach stacjonarnych, responsywny design obsłuży urządzenia mobilne).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz, aby wyskakujące okienko było widoczne, ale nie za szerokie, więc ustawiasz je na 700px.
-   **Kolor tła wyskakującego okienka:**

    -   **Co robi to ustawienie:** Ustawia kolor tła okna wyskakującego okienka.
    -   **Efekt zmiany tego ustawienia:** Zmienia wygląd wizualny wyskakującego okienka, aby pasował do Twojej marki lub wyróżniał się.
    -   **Zalecana wartość:** Kolor, który dobrze kontrastuje z Twoim tekstem i marką (np. #FFFFFF dla białego, #F0F0F0 dla jasnoszarego).
    -   **Scenariusz / przykład sprzedawcy:** Twoja marka używa dużo niebieskiego, więc wybierasz jasnoniebieski kod szesnastkowy, np. #E0F2F7.
-   **Kolor tekstu wyskakującego okienka:**

    -   **Co robi to ustawienie:** Ustawia kolor tekstu wyświetlanego w wyskakującym okienku.
    -   **Efekt zmiany tego ustawienia:** Zapewnia czytelność na tle wybranego koloru tła.
    -   **Zalecana wartość:** Kolor zapewniający dobry kontrast (np. #000000 dla czarnego, #333333 dla ciemnoszarego).
    -   **Scenariusz / przykład sprzedawcy:** Przy jasnym tle wybierasz ciemny kolor tekstu, np. #333333, dla optymalnej czytelności.
-   **Kolor ramki wyskakującego okienka:**

    -   **Co robi to ustawienie:** Ustawia kolor ramki wokół okna wyskakującego okienka.
    -   **Efekt zmiany tego ustawienia:** Dodaje wizualną ramkę do wyskakującego okienka.
    -   **Zalecana wartość:** Subtelny kolor, który uzupełnia Twój projekt, lub mocny kolor, aby go wyróżnić (np. #CCCCCC dla jasnoszarego lub kolor akcentu Twojej marki).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz uzyskać czysty wygląd, więc wybierasz subtelną szarą ramkę #DDDDDD.
-   **Szerokość ramki wyskakującego okienka (w pikselach):**

    -   **Co robi to ustawienie:** Kontroluje grubość ramki wyskakującego okienka.
    -   **Efekt zmiany tego ustawienia:** Wyższa liczba sprawia, że ramka jest grubsza.
    -   **Zalecana wartość:** 1-3px.
    -   **Scenariusz / przykład sprzedawcy:** Chcesz cienką, elegancką ramkę, więc ustawiasz ją na 1px.
-   **Promień ramki wyskakującego okienka (w pikselach):**

    -   **Co robi to ustawienie:** Kontroluje zaokrąglenie rogów wyskakującego okienka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ustawione na 0:* Ostre, kwadratowe rogi.
        -   *Ustawione na 10:* Lekko zaokrąglone rogi.
        -   *Ustawione na 50 (lub więcej):* Bardzo zaokrąglone, przypominające pigułkę rogi.
    -   **Zalecana wartość:** 5-10px (dla nowoczesnego, miękkiego wyglądu).
    -   **Scenariusz / przykład sprzedawcy:** Preferujesz bardziej miękką estetykę, więc ustawiasz promień ramki na 8px.
-   **Cień wyskakującego okienka:**

    -   **Co robi to ustawienie:** Dodaje efekt cienia wokół wyskakującego okienka, sprawiając, że wydaje się unosić nad stroną.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Wyskakujące okienko będzie miało subtelny cień, nadając mu głębię.
        -   *Gdy wyłączone:* Wyskakujące okienko nie będzie miało cienia.
    -   **Zalecana wartość:** TAK (dodaje profesjonalny, nowoczesny akcent).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz, aby wyskakujące okienko wizualnie wyróżniało się z tła, więc włączasz cień.
-   **Kolor przycisku zamykania wyskakującego okienka:**

    -   **Co robi to ustawienie:** Ustawia kolor przycisku „X”, którego klienci używają do zamykania wyskakującego okienka.
    -   **Efekt zmiany tego ustawienia:** Zapewnia widoczność przycisku zamykania i dopasowanie do Twojego projektu.
    -   **Zalecana wartość:** Kontrastujący kolor dla widoczności (np. #000000, #FF0000).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz, aby przycisk zamykania był wyraźnie widoczny, więc ustawiasz go na czarny #000000.
-   **Zawartość wyskakującego okienka (dozwolony HTML):**

    -   **Co robi to ustawienie:** Tutaj wprowadzasz główną wiadomość i zawartość dla swojego wyskakującego okienka. Możesz użyć HTML do formatowania tekstu, dodawania obrazów i włączania przycisków mediów społecznościowych.
    -   **Efekt zmiany tego ustawienia:** Ten tekst i HTML zostaną wyświetlone w wyskakującym okienku.
    -   **Zalecana wartość:** Jasna, zwięzła wiadomość z silnym wezwaniem do działania. Dołącz kod przycisku „Lubię to” na Facebooku lub podobny widżet mediów społecznościowych.
    -   **Scenariusz / przykład sprzedawcy:** Możesz wpisać: `<p>Polub nas na Facebooku i otrzymaj <strong>10% ZNIŻKI</strong> na kolejne zamówienie!</p><div class="fb-like" data-href="ADRES_URL_TWOJEJ_STRONY_FACEBOOK" data-layout="button_count" data-action="like" data-size="large" data-show-faces="false" data-share="false"></div>` (Pamiętaj, aby zastąpić `ADRES_URL_TWOJEJ_STRONY_FACEBOOK`).
-   **Wiadomość kuponu w wyskakującym okienku (dozwolony HTML):**

    -   **Co robi to ustawienie:** Jest to wiadomość wyświetlana *po* wykonaniu przez klienta wymaganej akcji (np. polubieniu Twojej strony) i otrzymaniu kodu kuponu.
    -   **Efekt zmiany tego ustawienia:** Ta wiadomość pojawi się w wyskakującym okienku, zazwyczaj nad wygenerowanym kodem kuponu.
    -   **Zalecana wartość:** Wiadomość z podziękowaniem i instrukcjami, jak użyć kuponu.
    -   **Scenariusz / przykład sprzedawcy:** Możesz wpisać: `<p>Dziękujemy za polubienie nas! Oto Twój ekskluzywny kod rabatowy:</p><p>Użyj kodu <strong>{coupon_code}</strong> przy kasie.</p>` (Zastępca `{coupon_code}` zostanie automatycznie zastąpiony).

#### Ustawienia zaawansowane

-   **Niestandardowy kod CSS:**

    -   **Co robi to ustawienie:** Pozwala dodać własne niestandardowe reguły CSS, aby dodatkowo stylizować wyskakujące okienko lub nadpisać domyślne style.
    -   **Efekt zmiany tego ustawienia:** Każdy CSS, który tutaj wprowadzisz, zostanie zastosowany do wyskakującego okienka, dając Ci precyzyjną kontrolę nad jego wyglądem.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne potrzeby stylizacyjne.
    -   **Scenariusz / przykład sprzedawcy:** Chcesz zmienić rozmiar czcionki kodu kuponu. Możesz dodać: `.coupon-code { font-size: 24px !important; }`
-   **Niestandardowy kod JavaScript:**

    -   **Co robi to ustawienie:** Pozwala dodać własny niestandardowy kod JavaScript do interakcji z wyskakującym okienkiem lub integracji z innymi usługami.
    -   **Efekt zmiany tego ustawienia:** Każdy JavaScript, który tutaj wprowadzisz, zostanie wykonany, gdy wyskakujące okienko zostanie wyświetlone lub będzie z nim interakcja.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne potrzeby skryptowe (np. śledzenie zdarzeń Google Analytics).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz wysłać zdarzenie do Google Analytics, gdy wyskakujące okienko zostanie wyświetlone. Możesz dodać: `ga('send', 'event', 'Popup', 'Displayed', 'Coupon Offer');`

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz moduł | TAK | Główny przełącznik funkcji wyskakującego okienka. |
| | Wyświetl na | Strony produktów / Wszystkie strony | Wybierz, gdzie pojawia się wyskakujące okienko (Strona główna, Kategoria, Produkt, CMS, Wszystkie). |
| | Opóźnienie (w sekundach) przed pojawieniem się wyskakującego okienka | 3-5 sekund | Czas przed wyświetleniem wyskakującego okienka po załadowaniu strony. |
| | Wyświetl wyskakujące okienko tylko raz na sesję | TAK | Zapobiega wielokrotnemu wyświetlaniu wyskakującego okienka w jednej sesji przeglądarki. |
| | Wyświetl wyskakujące okienko tylko raz na klienta (na zawsze) | TAK | Zapobiega ponownemu wyświetlaniu wyskakującego okienka zalogowanym klientom. |
| | Wyświetl wyskakujące okienko tylko dla gości | TAK | Kieruje do niezalogowanych odwiedzających. |
| | Wyświetl wyskakujące okienko tylko dla wybranych grup klientów | Goście, Odwiedzający | Ogranicza wyskakujące okienko do określonych grup klientów. |
| | Wyświetl wyskakujące okienko tylko dla wybranych krajów | Pozostaw puste | Ogranicza wyskakujące okienko do określonych krajów. |
| | Wyświetl wyskakujące okienko tylko dla wybranych walut | Pozostaw puste | Ogranicza wyskakujące okienko do określonych walut. |
| | Wyświetl wyskakujące okienko tylko dla wybranych języków | Pozostaw puste | Ogranicza wyskakujące okienko do określonych języków. |
| | Wartość bonu | np. 10% | Kwota zniżki lub procent. |
| | Typ bonu | Procent / Kwota | Definiuje, czy bon jest procentowy, czy stałą kwotą. |
| | Minimalna kwota bonu | 0 (lub rozsądna wartość) | Minimalna wartość zamówienia do użycia kuponu. |
| | Wygasa bon (w dniach) | 7-30 dni | Okres ważności wygenerowanego kuponu. |
| | Opis bonu | „Zniżka za polubienie na Facebooku z wyskakującego okienka” | Wewnętrzna nazwa kuponu w Panelu administracyjnym. |
| | Bon darmowa wysyłka | NIE | Przyznaje darmową wysyłkę z kuponem. |
| | Bon zastosuj do konkretnych produktów | Pozostaw puste | Ogranicza kupon do konkretnych produktów. |
| | Bon zastosuj do konkretnych kategorii | Pozostaw puste | Ogranicza kupon do konkretnych kategorii. |
| | Bon zastosuj do konkretnych producentów | Pozostaw puste | Ogranicza kupon do konkretnych producentów. |
| | Szerokość wyskakującego okienka (w pikselach) | 600px - 800px | Poziomy rozmiar wyskakującego okienka. |
| | Kolor tła wyskakującego okienka | #FFFFFF (biały) | Kolor tła wyskakującego okienka. |
| | Kolor tekstu wyskakującego okienka | #000000 (czarny) | Kolor tekstu w wyskakującym okienku. |
| | Kolor ramki wyskakującego okienka | #DDDDDD (jasnoszary) | Kolor ramki wyskakującego okienka. |
| | Szerokość ramki wyskakującego okienka (w pikselach) | 1-3px | Grubość ramki wyskakującego okienka. |
| | Promień ramki wyskakującego okienka (w pikselach) | 5-10px | Zaokrąglenie rogów wyskakującego okienka. |
| | Cień wyskakującego okienka | TAK | Dodaje efekt cienia do wyskakującego okienka. |
| | Kolor przycisku zamykania wyskakującego okienka | #000000 (czarny) | Kolor przycisku zamykania „X”. |
| | Zawartość wyskakującego okienka (dozwolony HTML) | Angażująca wiadomość + widżet społecznościowy | Główna zawartość wyświetlana w wyskakującym okienku. |
| | Wiadomość kuponu w wyskakującym okienku (dozwolony HTML) | Wiadomość z podziękowaniem + {coupon\_code} | Wiadomość wyświetlana po wygenerowaniu kuponu. |
| | Niestandardowy kod CSS | Pozostaw puste | Dodaj niestandardowe style CSS. |
| | Niestandardowy kod JavaScript | Pozostaw puste | Dodaj niestandardowy kod JavaScript. |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P1: Wyskakujące okienko nie pojawia się w moim sklepie. Co powinienem najpierw sprawdzić?**
O1:

-   **Czy moduł jest włączony?** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Kupony w responsywnym wyskakującym okienku” jest zainstalowany i włączony.
-   **Sprawdź ustawienie „Włącz moduł”:** W konfiguracji modułu upewnij się, że przełącznik „Włącz moduł” jest ustawiony na TAK.
-   **Zweryfikuj ustawienia „Wyświetl na”:** Upewnij się, że wybrałeś prawidłowe typy stron (np. Strona główna, Strony produktów), na których spodziewasz się pojawienia wyskakującego okienka.
-   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Pamięć podręczna przeglądarki również może wymagać wyczyszczenia (Ctrl+F5 lub Cmd+Shift+R).
-   **Sprawdź konflikty:** Tymczasowo wyłącz inne moduły, które mogą wchodzić w interakcje z wyskakującymi okienkami lub zawartością strony, aby wykluczyć konflikty.

**P2: Wyskakujące okienko się pojawia, ale przycisk „Lubię to” na Facebooku (lub inny widżet społecznościowy) nie działa lub nie wyświetla się poprawnie.**
O2:

-   **Nieprawidłowy HTML:** Dokładnie sprawdź kod HTML, który wprowadziłeś w polu „Zawartość wyskakującego okienka”. Nawet mała literówka może go zepsuć. Upewnij się, że adres URL Twojej strony na Facebooku jest poprawny.
-   **Facebook SDK:** Aby przyciski „Lubię to” na Facebooku działały, musi być załadowany Facebook JavaScript SDK. Motywy PrestaShop często go zawierają, ale jeśli nie, może być konieczne dodanie go za pomocą niestandardowego kodu lub upewnienie się, że Twój motyw go obsługuje.
-   **Blokery reklam:** Niektóre blokery reklam mogą uniemożliwiać ładowanie widżetów społecznościowych. Przetestuj w oknie incognito bez rozszerzeń.

**P3: Kod kuponu jest generowany, ale nie działa przy kasie.**
O3:

-   **Sprawdź ustawienia kuponu:** Przejrzyj wszystkie ustawienia „Bonu” w konfiguracji modułu:
    -   **Minimalna kwota:** Czy wartość koszyka klienta jest wyższa niż „Minimalna kwota bonu”?
    -   **Wygasa:** Czy data „Wygasa bon” minęła?
    -   **Konkretne produkty/kategorie/producenci:** Czy koszyk klienta zawiera wymagane elementy, jeśli te ustawienia są używane?
    -   **Grupy klientów/kraje/waluty/języki:** Czy klient spełnia kryteria ustawione dla tych ograniczeń?
-   **Reguły koszyka PrestaShop:** Moduł tworzy „Regułę koszyka” w PrestaShop. Przejdź do **Katalog > Rabaty > Reguły koszyka** (lub **Reguły cenowe > Reguły koszyka** w starszych wersjach) i wyszukaj kod kuponu. Sprawdź jego szczegóły, aby zobaczyć, czy jakieś ograniczenia zostały zastosowane niepoprawnie.

**P4: Projekt wyskakującego okienka nie pasuje idealnie do motywu mojego sklepu.**
O4:

-   **Użyj ustawień projektu modułu:** Dostosuj „Kolor tła wyskakującego okienka”, „Kolor tekstu wyskakującego okienka”, „Kolor ramki wyskakującego okienka”, „Szerokość ramki wyskakującego okienka” i „Promień ramki wyskakującego okienka”, aby lepiej pasowały do Twojego motywu.
-   **Niestandardowy CSS:** Aby uzyskać bardziej zaawansowane stylizacje, użyj pola „Niestandardowy kod CSS” w konfiguracji modułu. Możesz sprawdzić elementy wyskakującego okienka za pomocą narzędzi deweloperskich przeglądarki (F12), aby znaleźć odpowiednie selektory CSS do celowania.
-   **Nadpisywanie motywu:** Jeśli czujesz się komfortowo z kodowaniem, możesz również nadpisać CSS modułu w pliku `custom.css` lub `theme.css` swojego motywu.

**P5: Jak przetłumaczyć zawartość wyskakującego okienka na wiele języków?**
O5:

-   Pola „Zawartość wyskakującego okienka” i „Wiadomość kuponu w wyskakującym okienku” są zazwyczaj zaprojektowane do jednorazowego wprowadzenia. Aby uzyskać obsługę wielu języków, musiałbyś użyć systemu tłumaczeń PrestaShop.
-   Przejdź do **Lokalizacja > Tłumaczenia**. Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz „Kupony w responsywnym wyskakującym okienku”. Powinieneś znaleźć tam pola tekstowe do tłumaczenia.
-   Jeśli pola nie są bezpośrednio przetłumaczalne za pośrednictwem standardowego interfejsu PrestaShop, może być konieczne utworzenie oddzielnych wyskakujących okienek dla każdego języka (jeśli moduł obsługuje wiele instancji) lub użycie niestandardowego rozwiązania obejmującego zmienne Smarty i logikę warunkową w treści HTML, co wymaga pomocy programisty.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Kupony w responsywnym wyskakującym okienku” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł „Kupony w responsywnym wyskakującym okienku” (`popcoupon`) to standardowy moduł PrestaShop zaimplementowany głównie w jego głównym pliku PHP, `ajax_popcoupon.php`. Wykorzystuje system hooków PrestaShop do wyświetlania w front-office i klasę `Configuration` do przechowywania ustawień. Podstawowa funkcjonalność modułu obejmuje wyświetlanie wyskakującego okienka, obsługę interakcji użytkownika (np. akcji w mediach społecznościowych) i dynamiczne generowanie kodów `CartRule` (bonów) PrestaShop. Wykorzystuje JavaScript po stronie klienta do logiki wyświetlania wyskakującego okienka i stylizacji, oraz minimalny szablon do renderowania struktury wyskakującego okienka.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych dedykowanych kontrolerów Front-Office ani Back-Office Admin w oddzielnych plikach. Cała logika konfiguracji back-office jest obsługiwana w metodzie `getContent()` głównej klasy modułu. Wyświetlanie w front-office jest zarządzane za pomocą hooków i JavaScriptu po stronie klienta.

### 4.3 Klasy i modele rdzenia (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas `ObjectModel` ani innych podstawowych klas PHP w katalogu `classes/`. Cała logika jest zawarta w głównym pliku modułu `ajax_popcoupon.php`. Moduł bezpośrednio wchodzi w interakcje z klasą `Configuration` PrestaShop dla ustawień i klasą `CartRule` dla generowania bonów.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł zawiera kilka plików JavaScript:

-   **`popcoupon/jscolor/jscolor.js`**

    -   **Zakres:** Back-office.
    -   **Cel:** Jest to zewnętrzna biblioteka JavaScript do wyboru kolorów. Jest używana w formularzu konfiguracji back-office modułu, aby umożliwić sprzedawcom łatwe wybieranie kolorów tła, tekstu, ramki i przycisku zamykania wyskakującego okienka. Wiąże się z polami wejściowymi o określonych klasach, aby zapewnić wizualny interfejs wyboru koloru.
-   **`popcoupon/lib/voucherengine/script.js`**

    -   **Zakres:** Front-office.
    -   **Cel:** Jest to główny plik JavaScript odpowiedzialny za funkcjonalność wyskakującego okienka w front-office.
        -   **Słuchacze zdarzeń:** Nasłuchuje zdarzeń ładowania strony, aby wyzwolić wyskakujące okienko po skonfigurowanym opóźnieniu. Obsługuje również zdarzenia związane z zamykaniem wyskakującego okienka (np. kliknięcie przycisku „X” lub poza obszarem wyskakującego okienka).
        -   **Manipulacja DOM:** Dynamicznie wstrzykuje strukturę HTML wyskakującego okienka do strony, zarządza jej widocznością (pokaż/ukryj) i aktualizuje jej zawartość (np. wyświetlanie kodu kuponu po akcji społecznościowej).
        -   **Wywołania AJAX:** Prawdopodobnie wykonuje wywołania AJAX do `ajax_popcoupon.php` modułu (lub podobnego punktu wejścia), aby:
            1.  Sprawdzić, czy wyskakujące okienko powinno być wyświetlone dla bieżącego użytkownika/sesji.
            2.  Wygenerować unikalny kod kuponu po wykonaniu przez użytkownika wymaganej akcji (np. polubienie na Facebooku).
            3.  Przechować dane użytkownika/sesji (np. plik cookie), aby zapobiec wielokrotnemu wyświetlaniu wyskakującego okienka na podstawie ustawień konfiguracji („raz na sesję”, „raz na klienta”).
        -   **Zewnętrzne SDK:** Jeśli „Zawartość wyskakującego okienka” zawiera przycisk „Lubię to” na Facebooku, ten skrypt może wchodzić w interakcje z Facebook JavaScript SDK (jeśli załadowany przez motyw), aby wykryć, kiedy akcja „lubię to” zostanie zakończona.
-   **`popcoupon/trusted.js`**

    -   **Zakres:** Front-office.
    -   **Cel:** Dokładny cel tego pliku nie jest wyraźnie określony w dostarczonych informacjach, ale na podstawie typowych praktyk modułów może to być:
        -   Mały skrypt narzędziowy do śledzenia lub analizy.
        -   Skrypt związany z odznakami zaufania lub funkcjami bezpieczeństwa.
        -   Skrypt awaryjny lub uzupełniający dla głównego `script.js`.
        -   Może zawierać logikę związaną z obsługą plików cookie lub pamięci lokalnej dla funkcji „wyświetl raz”.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zawiera następujące pliki CSS:

-   **`popcoupon/css.css`**

    -   **Zakres:** Front-office.
    -   **Cel:** Jest to główny arkusz stylów dla okna wyskakującego okienka.
        -   **Komponenty interfejsu użytkownika:** Stylizuje ogólny kontener wyskakującego okienka, jego nakładkę, przycisk zamykania i potencjalnie obszar zawartości.
        -   **Kluczowe selektory:** Programiści mogą spodziewać się selektorów takich jak `.popcoupon-overlay`, `.popcoupon-modal`, `.popcoupon-close` itp. Można je nadpisać w `custom.css` niestandardowego motywu lub za pomocą ustawienia „Niestandardowy kod CSS” modułu.
        -   **Responsywność:** Zawiera zapytania mediów lub elastyczne właściwości box/grid, aby zapewnić, że wyskakujące okienko dobrze dostosowuje się do różnych rozmiarów ekranu.
-   **`popcoupon/lib/voucherengine/ps16.css`**

    -   **Zakres:** Front-office.
    -   **Cel:** Ten arkusz stylów prawdopodobnie zawiera specyficzne dostosowania stylizacji lub nadpisania dostosowane do motywów PrestaShop 1.6. Może dotyczyć różnic w układzie lub domyślnych stylów elementów występujących w PS 1.6, aby zapewnić spójny wygląd wyskakującego okienka w różnych wersjach PrestaShop. Dla PS 1.7/8, niektóre z tych stylów mogą być nadpisane przez `css.css` lub sam motyw.

### 4.6 Struktura szablonu Smarty (`views/templates/`)

Moduł używa jednego szablonu Smarty:

-   **`popcoupon/views/header.tpl`**
    -   **Hook:** `displayHeader` (lub podobny, w zależności od sposobu rejestracji w `ajax_popcoupon.php`).
    -   **Cel:** Ten szablon jest prawdopodobnie odpowiedzialny za wstrzykiwanie niezbędnej struktury HTML dla wyskakującego okienka (które jest początkowo ukryte) oraz potencjalnie zasobów JavaScript i CSS do `<head>` lub `<body>` strony front-office. Może zawierać:
        -   Podstawowy szkielet HTML dla modalu wyskakującego okienka i jego nakładki.
        -   Logikę warunkową do włączania plików JavaScript i CSS tylko wtedy, gdy moduł jest włączony.
        -   Zastępcze miejsca na dynamiczną zawartość, która zostanie wypełniona przez JavaScript.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych:**

    -   Ten moduł nie tworzy niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop. Klucze konfiguracyjne zazwyczaj zaczynają się od `POPCOUPON_` (np. `POPCOUPON_ENABLED`, `POPCOUPON_DELAY`, `POPCOUPON_VOUCHER_VALUE`).
    -   Wykorzystuje tabele `ps_cart_rule` i `ps_cart_rule_lang` PrestaShop do generowania i zarządzania unikalnymi kodami kuponów.
    -   Dla funkcji „wyświetl raz na klienta/sesję” prawdopodobnie używa plików cookie lub wpisów konfiguracyjnych specyficznych dla `ps_customer`.
-   **Tabela zarejestrowanych hooków:**

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Wstrzykiwanie CSS, JavaScript i początkowej (ukrytej) struktury HTML dla wyskakującego okienka. |
| `displayFooter` | Na końcu sekcji `<body>` każdej strony front-office. | Alternatywny hook do wstrzykiwania JS/CSS lub HTML wyskakującego okienka, często preferowany ze względu na wydajność. |
| `displayLeftColumn` | W lewej kolumnie front-office. | Mniej powszechne dla wyskakujących okienek, ale może być używane do wyzwalania lub wyświetlania mniejszego elementu wyskakującego okienka. |
| `displayRightColumn` | W prawej kolumnie front-office. | Podobnie jak `displayLeftColumn`. |
| `displayProductButtons` | Na stronie produktu, w pobliżu przycisku dodawania do koszyka. | Może być używane do wyzwalania wyskakującego okienka specyficznego dla produktu lub wyświetlania małej oferty kuponu. |
| `actionFrontControllerSetMedia` | Gdy kontroler front-office ustawia swoje media (JS/CSS). | Bardziej solidny sposób rejestrowania zasobów JS/CSS, zapewniający ich prawidłowe załadowanie. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | (Mniej prawdopodobne dla tego modułu, ale może być używane do działań po zakupie związanych z kuponami). |

*Uwaga: Dokładne używane hooki są określane przez metody `hook` zaimplementowane w `ajax_popcoupon.php` (np. `hookDisplayHeader()`). Opis modułu wspomina o „Nagłówku, Kolumnach, Produkcie lub Stopce”, co wskazuje, że rejestruje się on dla co najmniej jednego z tych hooków wyświetlania.*

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Kupony w responsywnym wyskakującym okienku”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
