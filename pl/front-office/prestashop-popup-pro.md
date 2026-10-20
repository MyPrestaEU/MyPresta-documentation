---
title: "Prestashop Popup Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu Prestashop Popup Pro od MyPresta.eu."
sidebar:
  label: "Prestashop Popup Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Prestashop Popup Pro na MyPresta.eu](https://mypresta.eu/modules/front-office-features/prestashop-popup-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/prestashop-popup-pro/)
>
> ---


# Prestashop Popup Pro

## 1. Wymagania i kompatybilność

Aby zapewnić płynne działanie modułu Prestashop Popup Pro w Twoim sklepie, sprawdź następujące wymagania:

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do ogólnego działania PrestaShop i powinny być dostępne w każdym nowoczesnym środowisku hostingowym. Dla tego modułu nie są potrzebne żadne specjalne ani nietypowe rozszerzenia.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Główna strona konfiguracji Prestashop Popup Pro to miejsce, w którym definiujesz wszystko na temat swojego pop-upu: jego zawartość, wygląd i zachowanie.

**Zakładka Ustawienia ogólne**

-   **Włącz Popup Pro:**
    *   **Co robi to ustawienie:** Jest to główny przełącznik dla całego modułu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po włączeniu:* Moduł zacznie wyświetlać pop-upy zgodnie z innymi ustawieniami.
        *   *Po wyłączeniu:* Żadne pop-upy nie będą wyświetlane w Twoim sklepie, niezależnie od innych konfiguracji.
    *   **Zalecana wartość:** TAK (gdy chcesz używać pop-upów).
    *   **Scenariusz/przykład sprzedawcy:** Prowadzisz kampanię i chcesz aktywować swój pop-up. Włączasz go. Po kampanii wyłączasz go, nie tracąc ustawień.
-   **Zawartość pop-upu (Edytor HTML):**
    *   **Co robi to ustawienie:** To jest rdzeń Twojego pop-upu. Jest to potężny edytor HTML, w którym projektujesz to, co pojawia się w oknie pop-upu. Możesz dodawać tekst, obrazy, linki, filmy, a nawet osadzać formularze (np. zapis do newslettera).
    *   **Efekt zmiany tego ustawienia:** Wszelkie zmiany tutaj bezpośrednio aktualizują wizualną zawartość wyświetlaną klientom w pop-upie.
    *   **Zalecana wartość:** Twoja pożądana wiadomość promocyjna, obraz lub wezwanie do działania.
    *   **Scenariusz/przykład sprzedawcy:** Chcesz ogłosić 15% zniżki. Wpisujesz „Otrzymaj 15% zniżki na pierwsze zamówienie! Użyj kodu: ZAPISZ15” i być może dodajesz obraz popularnych produktów.
-   **Szerokość pop-upu (px):**
    *   **Co robi to ustawienie:** Definiuje szerokość okna pop-upu w pikselach.
    *   **Efekt zmiany tego ustawienia:**
        *   *Zwiększenie wartości:* Sprawia, że pop-up jest szerszy.
        *   *Zmniejszenie wartości:* Sprawia, że pop-up jest węższy.
    *   **Zalecana wartość:** Zacznij od `600px` do `800px` dla komputerów stacjonarnych, a następnie dostosuj w oparciu o swoją zawartość i projekt.
    *   **Scenariusz/przykład sprzedawcy:** Masz duży obraz banerowy w swoim pop-upie. Możesz ustawić szerokość na `800px`, aby obraz dobrze się wyświetlał. Dla prostej wiadomości tekstowej `400px` może być wystarczające.
-   **Wysokość pop-upu (px):**
    *   **Co robi to ustawienie:** Definiuje wysokość okna pop-upu w pikselach.
    *   **Efekt zmiany tego ustawienia:**
        *   *Zwiększenie wartości:* Sprawia, że pop-up jest wyższy.
        *   *Zmniejszenie wartości:* Sprawia, że pop-up jest niższy.
    *   **Zalecana wartość:** `auto` (pozostaw puste) lub konkretna wartość w pikselach, jeśli Twoja zawartość ma stałą wysokość.
    *   **Scenariusz/przykład sprzedawcy:** Jeśli zawartość Twojego pop-upu jest dynamiczna lub krótka, pozostawienie jej pustej (`auto`) pozwala pop-upowi dostosować wysokość do zawartości. Jeśli masz wideo, które wymaga określonego współczynnika proporcji, możesz ustawić stałą wysokość.
-   **Wyświetl pop-up na:**
    *   **Co robi to ustawienie:** Określa, *kiedy* pop-up się pojawia.
    *   **Efekt zmiany tego ustawienia:**
        *   *Ładowanie strony:* Pop-up pojawia się po załadowaniu strony.
        *   *Intencja wyjścia:* Pop-up pojawia się, gdy mysz użytkownika przesuwa się poza okno przeglądarki (wskazując, że może opuścić stronę).
        *   *Przewijanie:* Pop-up pojawia się po przewinięciu przez użytkownika określonego procentu strony.
        *   *Opóźnienie czasowe:* Pop-up pojawia się po określonej liczbie sekund.
    *   **Zalecana wartość:** Zależy od Twojego celu. „Intencja wyjścia” jest często skuteczna w przechwytywaniu opuszczających witrynę odwiedzających. „Ładowanie strony” z krótkim opóźnieniem (np. 3-5 sekund) jest dobre dla ogólnych ogłoszeń.
    *   **Scenariusz/przykład sprzedawcy:** Aby zmniejszyć porzucanie koszyków, wybierzesz „Intencja wyjścia” i zaoferujesz kod rabatowy. Aby ogłosić nową linię produktów, możesz użyć „Ładowanie strony” z 3-sekundowym opóźnieniem.
-   **Opóźnienie przed pojawieniem się pop-upu (sekundy):**
    *   **Co robi to ustawienie:** Jeśli „Wyświetl pop-up na” jest ustawione na „Ładowanie strony” lub „Opóźnienie czasowe”, określa, ile sekund należy poczekać, zanim pop-up się pojawi.
    *   **Efekt zmiany tego ustawienia:** Wyższa wartość oznacza, że pop-up pojawi się później, dając klientowi więcej czasu na przeglądanie. Niższa wartość oznacza, że pojawi się wcześniej.
    *   **Zalecana wartość:** `3` do `5` sekund. Zbyt szybko może być natrętne, zbyt wolno może przegapić klienta.
    *   **Scenariusz/przykład sprzedawcy:** Chcesz dać klientom chwilę na zobaczenie Twojej strony głównej, zanim pokażesz zapis do newslettera. Ustawiasz to na `5` sekund.
-   **Częstotliwość pop-upu (dni):**
    *   **Co robi to ustawienie:** Kontroluje, jak często *powracający* klient widzi pop-up. Gdy klient zamknie pop-up, to ustawienie określa, ile dni minie, zanim zobaczy go ponownie.
    *   **Efekt zmiany tego ustawienia:**
        *   *0:* Pop-up pojawia się przy każdej wizycie (może być irytujące).
        *   *Wyższa wartość:* Pop-up pojawia się rzadziej dla powracających odwiedzających.
    *   **Zalecana wartość:** `7` do `30` dni. Unikaj irytowania swoich lojalnych klientów.
    *   **Scenariusz/przykład sprzedawcy:** Prowadzisz miesięczną wyprzedaż. Ustawiasz to na `7` dni, aby klienci byli przypominani co tydzień, ale nie przy każdej wizycie.
-   **Pokaż pop-up na urządzeniach mobilnych:**
    *   **Co robi to ustawienie:** Włącza lub wyłącza wyświetlanie pop-upu na smartfonach i tabletach.
    *   **Efekt zmiany tego ustawienia:**
        *   *Włączone:* Pop-up pojawia się na urządzeniach mobilnych, dostosowując się responsywnie.
        *   *Wyłączone:* Pop-up będzie wyświetlany tylko na komputerach stacjonarnych.
    *   **Zalecana wartość:** TAK, ale upewnij się, że zawartość pop-upu jest przyjazna dla urządzeń mobilnych.
    *   **Scenariusz/przykład sprzedawcy:** Masz prosty, tekstowy pop-up, który dobrze wygląda na urządzeniach mobilnych. Włączasz to, aby dotrzeć do wszystkich swoich klientów. Jeśli Twój pop-up zawiera złożone obrazy lub formularze, które psują się na urządzeniach mobilnych, możesz go wyłączyć.
-   **Kolor tła pop-upu:**
    *   **Co robi to ustawienie:** Ustawia kolor tła samego okna pop-upu.
    *   **Efekt zmiany tego ustawienia:** Zmienia wizualny kolor za Twoją zawartością.
    *   **Zalecana wartość:** Kolor, który uzupełnia Twoją markę i sprawia, że Twoja zawartość się wyróżnia. Często biały (`#FFFFFF`) lub jasny neutralny kolor.
    *   **Scenariusz/przykład sprzedawcy:** Twoja marka używa dużo niebieskiego. Możesz wybrać jasnoniebieskie tło dla pop-upu, aby pasowało.
-   **Kolor ramki pop-upu:**
    *   **Co robi to ustawienie:** Ustawia kolor ramki wokół okna pop-upu.
    *   **Efekt zmiany tego ustawienia:** Zmienia wizualny kolor krawędzi pop-upu.
    *   **Zalecana wartość:** Często subtelny kolor lub przezroczysty, jeśli wolisz bez ramki.
    *   **Scenariusz/przykład sprzedawcy:** Chcesz uzyskać czysty wygląd, więc ustawiasz to na bardzo jasnoszary lub przezroczysty.
-   **Szerokość ramki pop-upu (px):**
    *   **Co robi to ustawienie:** Ustawia grubość ramki wokół okna pop-upu.
    *   **Efekt zmiany tego ustawienia:** Wyższa wartość sprawia, że ramka jest grubsza.
    *   **Zalecana wartość:** `0` do `2` pikseli dla subtelnego efektu.
    *   **Scenariusz/przykład sprzedawcy:** Chcesz bardzo wyraźny pop-up, więc ustawiasz ramkę na `2px`. Dla minimalistycznego projektu ustawiasz ją na `0`.
-   **Promień ramki pop-upu (px):**
    *   **Co robi to ustawienie:** Kontroluje zaokrąglenie rogów pop-upu.
    *   **Efekt zmiany tego ustawienia:**
        *   *0:* Ostre, kwadratowe rogi.
        *   *Wyższa wartość:* Bardziej zaokrąglone rogi.
    *   **Zalecana wartość:** `0` do `10` pikseli dla nowoczesnego wyglądu.
    *   **Scenariusz/przykład sprzedawcy:** Chcesz, aby Twój pop-up miał miękkie, nowoczesne krawędzie, więc ustawiasz to na `8px`.
-   **Kolor tła nakładki:**
    *   **Co robi to ustawienie:** Ustawia kolor półprzezroczystej warstwy, która pojawia się *za* pop-upem, przyciemniając resztę zawartości Twojego sklepu.
    *   **Efekt zmiany tego ustawienia:** Zmienia kolor nakładki. Często ciemny kolor z przezroczystością.
    *   **Zalecana wartość:** Czarny (`#000000`) z pewną przezroczystością (np. `rgba(0,0,0,0.7)`, jeśli możesz wprowadzić RGBA).
    *   **Scenariusz/przykład sprzedawcy:** Chcesz, aby pop-up był absolutnym centrum uwagi, więc wybierasz ciemną, prawie nieprzezroczystą nakładkę.
-   **Przezroczystość nakładki (0-100):**
    *   **Co robi to ustawienie:** Kontroluje, jak przezroczyste lub nieprzezroczyste jest tło nakładki. `0` to całkowicie przezroczyste (niewidoczne), `100` to całkowicie nieprzezroczyste (jednolity kolor).
    *   **Efekt zmiany tego ustawienia:**
        *   *Wyższa wartość:* Bardziej nieprzezroczyste, ciemniejsze tło, większe skupienie na pop-upie.
        *   *Niższa wartość:* Bardziej przezroczyste, jaśniejsze tło, więcej zawartości Twojego sklepu widoczne.
    *   **Zalecana wartość:** `50` do `80`.
    *   **Scenariusz/przykład sprzedawcy:** Chcesz lekko przyciemnić tło, ale nadal pozwolić klientom widzieć Twój sklep za pop-upem. Ustawiasz to na `60`.
-   **Pokaż przycisk zamykania:**
    *   **Co robi to ustawienie:** Włącza lub wyłącza widoczność standardowego przycisku zamykania „X” na pop-upie.
    *   **Efekt zmiany tego ustawienia:**
        *   *Włączone:* Pojawia się przycisk zamykania, umożliwiając klientom łatwe odrzucenie pop-upu.
        *   *Wyłączone:* Brak przycisku „X”. Klienci będą musieli kliknąć poza pop-upem lub nacisnąć ESC (jeśli włączone), aby go zamknąć.
    *   **Zalecana wartość:** TAK, dla dobrego doświadczenia użytkownika.
    *   **Scenariusz/przykład sprzedawcy:** Chcesz ułatwić klientom zamykanie pop-upu, więc włączasz przycisk zamykania.
-   **Zezwól na zamykanie przez kliknięcie poza obszarem:**
    *   **Co robi to ustawienie:** Określa, czy kliknięcie w dowolnym miejscu nakładki (poza zawartością pop-upu) zamknie pop-up.
    *   **Efekt zmiany tego ustawienia:**
        *   *Włączone:* Kliknięcie nakładki zamyka pop-up.
        *   *Wyłączone:* Tylko przycisk zamykania lub klawisz ESC zamkną pop-up.
    *   **Zalecana wartość:** TAK, dla dobrego doświadczenia użytkownika.
    *   **Scenariusz/przykład sprzedawcy:** Chcesz zapewnić wiele sposobów na odrzucenie pop-upu przez klientów, więc włączasz to.
-   **Zezwól na zamykanie klawiszem ESC:**
    *   **Co robi to ustawienie:** Określa, czy naciśnięcie klawisza ESC na klawiaturze zamknie pop-up.
    *   **Efekt zmiany tego ustawienia:**
        *   *Włączone:* Klawisz ESC zamyka pop-up.
        *   *Wyłączone:* Klawisz ESC nie ma wpływu na pop-up.
    *   **Zalecana wartość:** TAK, dla dobrego doświadczenia użytkownika.
    *   **Scenariusz/przykład sprzedawcy:** Chcesz zapewnić dostępny sposób na odrzucenie pop-upu przez klientów, więc włączasz to.
-   **Niestandardowy CSS:**
    *   **Co robi to ustawienie:** Pozwala dodać własne niestandardowe reguły CSS, aby dalej stylizować pop-up lub jego zawartość. Jest to dla zaawansowanych użytkowników lub programistów.
    *   **Efekt zmiany tego ustawienia:** Wszelkie prawidłowe reguły CSS, które dodasz tutaj, zostaną zastosowane do pop-upu, potencjalnie nadpisując domyślne style.
    *   **Zalecana wartość:** Pozostaw puste, chyba że masz specyficzne potrzeby stylizacyjne.
    *   **Scenariusz/przykład sprzedawcy:** Chcesz zmienić rozmiar czcionki konkretnego akapitu w swoim pop-upie lub dodać unikalny efekt cienia niedostępny w innych ustawieniach. Dodasz CSS tutaj.

**Zakładka Ustawienia zaawansowane (lub podobne grupowanie, jeśli dostępne)**

-   **Animacja pop-upu (Efekt wejścia):**
    *   **Co robi to ustawienie:** Wybiera efekt animacji, gdy pop-up pojawia się na ekranie.
    *   **Efekt zmiany tego ustawienia:** Pop-up animuje się do widoku, używając wybranego efektu (np. zanikanie, zsuwanie w dół, powiększanie).
    *   **Zalecana wartość:** „Zanikanie” lub „Zsuwanie w dół” są zazwyczaj subtelne i profesjonalne.
    *   **Scenariusz/przykład sprzedawcy:** Chcesz, aby Twój pop-up płynnie się pojawiał, zamiast po prostu natychmiast wyskakiwać, więc wybierasz „Zanikanie”.
-   **Animacja pop-upu (Efekt wyjścia):**
    *   **Co robi to ustawienie:** Wybiera efekt animacji, gdy pop-up znika z ekranu.
    *   **Efekt zmiany tego ustawienia:** Pop-up animuje się z widoku, używając wybranego efektu.
    *   **Zalecana wartość:** „Zanikanie” lub „Zsuwanie w górę”, aby pasowało do efektu wejścia.
    *   **Scenariusz/przykład sprzedawcy:** Aby zachować spójne i płynne doświadczenie użytkownika, wybierasz „Zanikanie” jako animację wyjścia.
-   **Wyświetl pop-up na konkretnych stronach (URL):**
    *   **Co robi to ustawienie:** Pozwala określić dokładne adresy URL lub wzorce adresów URL, na których pop-up powinien (lub nie powinien) się pojawiać.
    *   **Efekt zmiany tego ustawienia:** Pop-up będzie wyświetlany tylko na stronach pasujących do Twoich kryteriów lub będzie na nich ukryty.
    *   **Zalecana wartość:** Użyj tego, aby skutecznie targetować swoje pop-upy.
    *   **Scenariusz/przykład sprzedawcy:** Masz specjalną ofertę dla konkretnej kategorii produktów. Wprowadziłbyś tutaj adres URL tej strony kategorii, aby upewnić się, że pop-up pojawia się tylko dla odpowiednich odwiedzających.
-   **Nie wyświetlaj pop-upu na konkretnych stronach (URL):**
    *   **Co robi to ustawienie:** Pozwala określić dokładne adresy URL lub wzorce adresów URL, na których pop-up *nie* powinien się pojawiać.
    *   **Efekt zmiany tego ustawienia:** Pop-up będzie ukryty na stronach pasujących do Twoich kryteriów.
    *   **Zalecana wartość:** Użyj tego, aby uniknąć wyświetlania pop-upów na wrażliwych stronach, takich jak strona kasy lub logowania.
    *   **Scenariusz/przykład sprzedawcy:** Nie chcesz, aby pop-up przerywał proces realizacji zamówienia. Dodałbyś tutaj adres URL strony kasy (np. `/order`).
-   **Wyświetl pop-up dla konkretnych grup klientów:**
    *   **Co robi to ustawienie:** Ogranicza widoczność pop-upu do określonych grup klientów (np. Odwiedzający, Klienci, Goście, Hurtownicy).
    *   **Efekt zmiany tego ustawienia:** Tylko klienci należący do wybranych grup zobaczą pop-up.
    *   **Zalecana wartość:** Zależy od Twojej grupy docelowej. „Odwiedzający” i „Goście” są powszechne do generowania leadów.
    *   **Scenariusz/przykład sprzedawcy:** Masz specjalną ofertę wyłącznie dla swoich zarejestrowanych klientów. Wybrałbyś tutaj „Klienci”.
-   **Wyświetl pop-up dla konkretnych języków:**
    *   **Co robi to ustawienie:** Ogranicza widoczność pop-upu do klientów przeglądających w określonych językach.
    *   **Efekt zmiany tego ustawienia:** Tylko klienci używający wybranego języka zobaczą pop-up.
    *   **Zalecana wartość:** Wszystkie języki lub konkretne, jeśli zawartość pop-upu jest zależna od języka.
    *   **Scenariusz/przykład sprzedawcy:** Masz pop-up z treścią przetłumaczoną tylko na angielski i francuski. Wybrałbyś tutaj „Angielski” i „Francuski”.
-   **Wyświetl pop-up dla konkretnych walut:**
    *   **Co robi to ustawienie:** Ogranicza widoczność pop-upu do klientów przeglądających z określonymi walutami.
    *   **Efekt zmiany tego ustawienia:** Tylko klienci używający wybranej waluty zobaczą pop-up.
    *   **Zalecana wartość:** Wszystkie waluty lub konkretne, jeśli zawartość pop-upu jest zależna od waluty.
    *   **Scenariusz/przykład sprzedawcy:** Masz specjalną ofertę ważną tylko dla klientów płacących w USD. Wybrałbyś tutaj „USD”.
-   **Wyświetl pop-up dla konkretnych krajów:**
    *   **Co robi to ustawienie:** Ogranicza widoczność pop-upu do klientów z określonych krajów.
    *   **Efekt zmiany tego ustawienia:** Tylko klienci wykryci jako pochodzący z wybranych krajów zobaczą pop-up.
    *   **Zalecana wartość:** Wszystkie kraje lub konkretne dla kampanii ukierunkowanych geograficznie.
    *   **Scenariusz/przykład sprzedawcy:** Prowadzisz promocję wyłącznie dla klientów we Francji. Wybrałbyś tutaj „Francja”.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Włącz Popup Pro | TAK | Główny przełącznik do aktywacji/dezaktywacji pop-upu. |
| | Zawartość pop-upu (Edytor HTML) | (Puste) | Projektuj to, co pojawia się w pop-upie (tekst, obrazy, linki). |
| | Szerokość pop-upu (px) | 600-800px | Ustawia rozmiar poziomy pop-upu. |
| | Wysokość pop-upu (px) | auto (puste) | Ustawia rozmiar pionowy pop-upu lub automatycznie dostosowuje. |
| | Wyświetl pop-up na | Intencja wyjścia / Ładowanie strony (opóźnienie 3-5s) | Określa wyzwalacz pojawienia się pop-upu. |
| | Opóźnienie przed pojawieniem się pop-upu (sekundy) | 3-5 | Opóźnienie czasowe przed wyświetleniem pop-upu (jeśli wybrano „Ładowanie strony”). |
| | Częstotliwość pop-upu (dni) | 7-30 | Jak często powracający klient widzi pop-up. |
| | Pokaż pop-up na urządzeniach mobilnych | TAK | Kontroluje widoczność pop-upu na telefonach/tabletach. |
| | Kolor tła pop-upu | #FFFFFF (Biały) | Kolor tła okna pop-upu. |
| | Kolor ramki pop-upu | Przezroczysty / Jasnoszary | Kolor ramki pop-upu. |
| | Szerokość ramki pop-upu (px) | 0-2 | Grubość ramki pop-upu. |
| | Promień ramki pop-upu (px) | 0-10 | Zaokrąglenie rogów pop-upu. |
| | Kolor tła nakładki | #000000 (Czarny) | Kolor półprzezroczystego tła za pop-upem. |
| | Przezroczystość nakładki (0-100) | 50-80 | Poziom przezroczystości nakładki. |
| | Pokaż przycisk zamykania | TAK | Wyświetla przycisk „X” do zamykania pop-upu. |
| | Zezwól na zamykanie przez kliknięcie poza obszarem | TAK | Pozwala na zamykanie przez kliknięcie na nakładkę. |
| | Zezwól na zamykanie klawiszem ESC | TAK | Pozwala na zamykanie przez naciśnięcie klawisza ESC. |
| | Niestandardowy CSS | (Puste) | Dodaj niestandardowy CSS do zaawansowanego stylizowania. |
| | Animacja pop-upu (Efekt wejścia) | Zanikanie / Zsuwanie w dół | Efekt wizualny, gdy pop-up się pojawia. |
| | Animacja pop-upu (Efekt wyjścia) | Zanikanie / Zsuwanie w górę | Efekt wizualny, gdy pop-up znika. |
| | Wyświetl pop-up na konkretnych stronach (URL) | (Puste) | Pokaż pop-up tylko na określonych adresach URL. |
| | Nie wyświetlaj pop-upu na konkretnych stronach (URL) | (Puste) | Ukryj pop-up z określonych adresów URL (np. strona kasy). |
| | Wyświetl pop-up dla konkretnych grup klientów | Wszystkie | Kieruj pop-up do określonych typów klientów. |
| | Wyświetl pop-up dla konkretnych języków | Wszystkie | Kieruj pop-up do określonych języków. |
| | Wyświetl pop-up dla konkretnych walut | Wszystkie | Kieruj pop-up do określonych walut. |
| | Wyświetl pop-up dla konkretnych krajów | Wszystkie | Kieruj pop-up do określonych krajów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Mój pop-up w ogóle się nie wyświetla. Co powinienem sprawdzić w pierwszej kolejności?**
**O1:**

1.  **Czy moduł jest włączony?** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Prestashop Popup Pro” jest zainstalowany i włączony.
2.  **Czy „Włącz Popup Pro” jest ustawione na TAK w konfiguracji modułu?** To jest główny przełącznik.
3.  **Sprawdź ustawienia „Wyświetl pop-up na”:** Jeśli jest ustawione na „Opóźnienie czasowe”, upewnij się, że opóźnienie nie jest zbyt długie. Jeśli „Intencja wyjścia”, upewnij się, że faktycznie wyzwalasz ją poprawnie (przesuwanie myszy poza okno przeglądarki).
4.  **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność**, przewiń w dół i kliknij „Wyczyść pamięć podręczną”. Czasami stare pliki pamięci podręcznej uniemożliwiają zastosowanie nowych ustawień modułu.
5.  **Sprawdź konflikty:** Tymczasowo wyłącz inne moduły pop-up lub nakładek, aby sprawdzić, czy nie ma konfliktu.

**P2: Mój pop-up wygląda dziwnie lub jest uszkodzony na urządzeniach mobilnych.**
**O2:**

1.  **Czy „Pokaż pop-up na urządzeniach mobilnych” jest włączone?** Jeśli nie, w ogóle się nie wyświetli.
2.  **Przejrzyj swoją „Zawartość pop-upu”:** Złożony kod HTML, bardzo duże obrazy lub treści nieprzeznaczone dla małych ekranów mogą powodować problemy. Spróbuj uprościć zawartość lub użyć mniejszych, zoptymalizowanych obrazów.
3.  **Sprawdź „Szerokość pop-upu” i „Wysokość pop-upu”:** Chociaż moduł jest responsywny, czasami stałe wartości pikseli mogą powodować problemy na bardzo małych ekranach. Rozważ pozostawienie „Wysokości pop-upu” pustej dla `auto`.
4.  **Niestandardowy CSS:** Jeśli dodałeś niestandardowy CSS, może on nie być przyjazny dla urządzeń mobilnych. Przetestuj swój CSS za pomocą narzędzi deweloperskich przeglądarki (inspekcja elementu) na różnych rozmiarach ekranu.

**P3: Pop-up pojawia się zbyt często dla moich klientów. Jak mogę to kontrolować?**
**O3:**

1.  **Dostosuj „Częstotliwość pop-upu (dni)”:** To jest kluczowe ustawienie. Wyższa liczba oznacza, że klienci będą widzieć pop-up rzadziej. Na przykład, ustawienie na `30` oznacza, że zobaczą go tylko raz w miesiącu po jego zamknięciu.
2.  **Rozważ ustawienie „Wyświetl pop-up na”:** Jeśli jest to „Ładowanie strony” z krótkim opóźnieniem, może to być bardziej natrętne niż „Intencja wyjścia”.

**P4: Chcę przetłumaczyć zawartość mojego pop-upu na wiele języków. Jak to zrobić?**
**O4:** Edytor HTML „Zawartość pop-upu” powinien obsługiwać wielojęzyczne wprowadzanie danych w PrestaShop. Podczas edycji treści szukaj zakładek językowych lub rozwijanych list (zazwyczaj w prawym górnym rogu edytora), aby przełączać się między językami i dostarczać różne treści dla każdego z nich. Upewnij się, że masz zainstalowane pożądane języki w PrestaShop. Jeśli edytor nie wyświetla zakładek językowych, może być konieczne ręczne wprowadzenie treści dla każdego języka poprzez zmianę języka w panelu administracyjnym.

**P5: Zawartość pop-upu jest za mała/za duża, lub czcionka jest nieprawidłowa.**
**O5:**

1.  **Użyj edytora HTML:** Wbudowany edytor HTML zazwyczaj oferuje opcje zmiany rozmiaru czcionki, koloru i innych stylów dla Twojego tekstu.
2.  **Niestandardowy CSS:** Aby uzyskać bardziej precyzyjną kontrolę, użyj pola „Niestandardowy CSS”. Na przykład, aby zmienić rozmiar czcionki całego tekstu w pop-upie, możesz dodać:

    ```
    .popuppro-content p { font-size: 16px !important;}
    ```

    (Może być konieczne sprawdzenie pop-upu w przeglądarce, aby znaleźć prawidłowe selektory CSS, takie jak `.popuppro-content`).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu Prestashop Popup Pro, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł Prestashop Popup Pro stosuje standardową architekturę modułów PrestaShop, wykorzystując głównie klasę `Module` do swojej podstawowej funkcjonalności i `ModuleFrontController` do interakcji AJAX. W dużym stopniu opiera się na JavaScript do logiki wyświetlania w front-office, animacji i obsługi zdarzeń (takich jak intencja wyjścia). Konfiguracja jest zarządzana za pomocą metody `getContent()` w głównym pliku modułu, przechowując ustawienia w `ps_configuration`. Moduł integruje Smarty Templates Manager do elastycznego tworzenia treści i selektor kolorów do dostosowywania interfejsu użytkownika.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:
    *   `popuppro/controllers/front/index.php`
        *   **Nazwa klasy:** `PopupproIndexModuleFrontController` (prawdopodobnie, na podstawie konwencji nazewnictwa plików)
        *   **Klasa nadrzędna:** `ModuleFrontController`
        *   **Odpowiedzialność:** Ten kontroler może służyć jako ogólny punkt wejścia lub rezerwowy dla żądań front-office związanych z modułem. Może być odpowiedzialny za początkowe ładowanie danych lub renderowanie podstawowego widoku modułu, jeśli nie jest wymagana żadna konkretna akcja.
    *   `popuppro/controllers/front/popuploader.php`
        *   **Nazwa klasy:** `PopupproPopuploaderModuleFrontController`
        *   **Klasa nadrzędna:** `ModuleFrontController`
        *   **Odpowiedzialność:** Ten kontroler jest bardzo prawdopodobnie odpowiedzialny za dynamiczne ładowanie zawartości i konfiguracji pop-upu za pośrednictwem AJAX. Gdy użytkownik odwiedza stronę, skrypt JavaScript wysyła żądanie AJAX do tego kontrolera, aby pobrać kod HTML, stylizację i ustawienia zachowania pop-upu na podstawie konfiguracji modułu. Zwraca ładunek JSON lub HTML.
    *   `popuppro/controllers/front/popupstat.php`
        *   **Nazwa klasy:** `PopupproPopupstatModuleFrontController`
        *   **Klasa nadrzędna:** `ModuleFrontController`
        *   **Odpowiedzialność:** Ten kontroler jest przeznaczony do obsługi danych statystycznych związanych z pop-upem. Otrzymywałby żądania AJAX z JavaScript front-office w celu rejestrowania wyświetleń pop-upu, kliknięć przycisku zamykania lub innych interakcji, umożliwiając modułowi śledzenie wydajności (chociaż dedykowany widok statystyk nie jest wyraźnie wymieniony w kontrolerach administracyjnych, dane te mogą być przechowywane do przyszłego użytku lub wewnętrznego logowania).
-   **Kontrolery administracyjne Back-Office**: Brak wyraźnie wymienionych, co wskazuje, że cała administracja jest obsługiwana za pomocą metody `getContent()` głównego pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

W katalogu `classes/` nie ma wymienionych niestandardowych klas ani definicji `ObjectModel`. Sugeruje to, że moduł przechowuje swoją konfigurację bezpośrednio w tabeli `ps_configuration` za pomocą `Configuration::updateValue()` i `Configuration::get()`, i nie zarządza złożonymi niestandardowymi encjami danych wymagającymi dedykowanych tabel bazy danych lub mapowania `ObjectModel`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `popuppro/js/popup-engine.js`:
    *   **Zakres:** Front-office.
    *   **Szczegóły:** Jest to prawdopodobnie główny plik JavaScript odpowiedzialny za podstawowe mechanizmy pop-upu. Obsługiwałby tworzenie elementów DOM pop-upu (nakładka, kontener pop-upu, przycisk zamykania), wstrzykiwanie treści, zarządzanie animacjami (efekty wejścia/wyjścia) i pozycjonowanie pop-upu na ekranie. Prawdopodobnie definiuje główny obiekt `PopupPro` lub podobny.
-   `popuppro/js/popup-events.js`:
    *   **Zakres:** Front-office.
    *   **Szczegóły:** Ten skrypt zarządzałby wszystkimi słuchaczami zdarzeń, które wyzwalają pop-up. Obejmuje to:
        *   `DOMContentLoaded` lub `window.load` dla początkowej konfiguracji.
        *   `setTimeout` dla pop-upów z opóźnieniem czasowym.
        *   Słuchacze zdarzeń przewijania dla pop-upów wyzwalanych przewijaniem.
        *   `mouseleave` lub podobne zdarzenia na `document.body` do wykrywania intencji wyjścia.
        *   Słuchacze kliknięć dla przycisku zamykania i zamykania po kliknięciu poza obszarem.
        *   Słuchacz `keyup` dla klawisza ESC.
        *   Wywołania AJAX do `popuploader.php` w celu pobrania treści i `popupstat.php` w celu rejestrowania zdarzeń.
-   `popuppro/js/popup-scripts.js`:
    *   **Zakres:** Front-office.
    *   **Szczegóły:** Ten plik może zawierać dodatkowe, być może bardziej specyficzne, skrypty związane z zachowaniem pop-upu lub interakcjami, prawdopodobnie obsługujące przesyłanie formularzy w pop-upie, dynamiczne aktualizacje treści lub integrację z innymi elementami front-office.
-   `popuppro/js/script.js`:
    *   **Zakres:** Front-office/Back-office (ogólna nazwa, może być jedno lub drugie).
    *   **Szczegóły:** Biorąc pod uwagę jego ogólną nazwę, może to być ogólny skrypt narzędziowy, lub może zawierać logikę inicjalizacji pop-upu w front-office, a nawet drobne skrypty back-office, jeśli jest tam ładowany. Moduły często mają `script.js` do ogólnego kodu.
-   `popuppro/js/tinymce16-force-urls.inc.js`, `popuppro/js/tinymce16.inc.js`:
    *   **Zakres:** Back-office.
    *   **Szczegóły:** Te pliki są związane z edytorem tekstu sformatowanego TinyMCE, w szczególności wersją 1.6. Są one dołączone w celu zapewnienia funkcjonalności edytora HTML dla pola „Zawartość pop-upu” w konfiguracji modułu w back-office. `tinymce16-force-urls.inc.js` prawdopodobnie zajmuje się zapewnieniem prawidłowego formatowania adresów URL w edytorze.
-   `popuppro/jscolor/jscolor.js`:
    *   **Zakres:** Back-office.
    *   **Szczegóły:** Jest to biblioteka JavaScript do funkcji selektora kolorów używanej w konfiguracji back-office (np. dla koloru tła pop-upu, koloru ramki, koloru nakładki). Zapewnia interaktywny interfejs wyboru koloru.
-   `popuppro/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`:
    *   **Zakres:** Back-office.
    *   **Szczegóły:** Ten skrypt jest częścią wewnętrznej biblioteki do zarządzania szablonami Smarty w konfiguracji modułu. Prawdopodobnie zapewnia funkcjonalność podglądu szablonów, ich wyboru lub dynamicznego wstawiania treści opartych na szablonach do edytora HTML.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `popuppro/css.css`:
    *   **Zakres:** Front-office.
    *   **Szczegóły:** Jest to prawdopodobnie główny arkusz stylów dla pop-upu front-office, definiujący jego domyślny wygląd: pozycjonowanie, rozmiar, ramkę, cień, stylizację przycisku zamykania i potencjalne responsywne dostosowania.
    *   **Kluczowe selektory:** `.popuppro-overlay`, `.popuppro-popup`, `.popuppro-close-btn`, `.popuppro-content`.
-   `popuppro/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`:
    *   **Zakres:** Back-office.
    *   **Szczegóły:** Arkusze stylów dla interfejsu Smarty Templates Manager w konfiguracji modułu w back-office. Stylizowałyby one wybór szablonów, obszary podglądu i powiązane elementy interfejsu użytkownika.
-   `popuppro/popuppro.css`:
    *   **Zakres:** Front-office.
    *   **Szczegóły:** Podobnie jak `css.css`, może zawierać dodatkowe lub specyficzne style dla pop-upu, potencjalnie dla różnych stanów animacji lub konkretnych elementów treści. Może występować pewne nakładanie się lub rozdzielenie odpowiedzialności między `css.css` a `popuppro.css`.
    *   **Kluczowe selektory:** Prawdopodobnie podobne do `css.css`, skupiające się na głównych komponentach pop-upu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**: (Brak wyraźnie wymienionych w `views/templates/hook/`, ale `views/header.tpl` jest prawdopodobnie podpięty)
    *   `popuppro/views/header.tpl`:
        *   **Hook:** `displayHeader`
        *   **Wyjście:** Ten szablon jest prawie na pewno podpięty do `displayHeader`. Byłby odpowiedzialny za wstrzykiwanie niezbędnych plików JavaScript i CSS do sekcji `<head>` front-office, a potencjalnie także początkowej struktury HTML lub danych konfiguracyjnych do wykorzystania przez JavaScript.
    *   `popuppro/views/header_address.tpl`, `popuppro/views/header_carrier.tpl`:
        *   **Hook:** Potencjalnie `displayHeader` lub inne specyficzne hooki związane z informacjami o adresie/przewoźniku.
        *   **Wyjście:** Wydają się to być specjalistyczne szablony nagłówków, prawdopodobnie do wyświetlania dynamicznej zawartości związanej z adresem klienta lub informacjami o przewoźniku *w* pop-upie, lub dla konkretnych scenariuszy pop-upów. Ich dokładne użycie zależałoby od logiki modułu.
    *   `popuppro/views/popup.tpl`:
        *   **Hook:** Nie jest bezpośrednio podpięty, ale renderowany przez JavaScript.
        *   **Wyjście:** Jest to główny szablon dla struktury pop-upu front-office. Definiuje kod HTML dla nakładki, kontenera pop-upu, przycisku zamykania i miejsca na dynamiczną zawartość ładowaną za pośrednictwem AJAX.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   `popuppro/views/admin/admin.tpl`:
        *   **Cel:** Główny szablon dla strony konfiguracji modułu w panelu administracyjnym. Zawierałby ogólny układ, zakładki i strukturę formularzy ustawień.
    *   `popuppro/views/admin/boscript.tpl`:
        *   **Cel:** Szablon JavaScript dla back-office. Prawdopodobnie wstrzykuje specyficzny kod JavaScript potrzebny dla strony konfiguracji administracyjnej, taki jak inicjalizacja TinyMCE, selektora kolorów lub niestandardowej walidacji formularzy.
    *   `popuppro/views/admin/popup_preview.tpl`:
        *   **Cel:** Szablon do wyświetlania podglądu na żywo lub symulowanego pop-upu w konfiguracji back-office, umożliwiający sprzedawcom podgląd zmian na bieżąco.
    *   `popuppro/views/admin/presets.tpl`:
        *   **Cel:** Szablon do zarządzania lub wyświetlania predefiniowanych szablonów lub stylów pop-upów.
    *   `popuppro/views/admin/shadow_editor.tpl`:
        *   **Cel:** Specjalistyczny szablon do konfigurowania efektów cienia dla pop-upu, potencjalnie oferujący zaawansowane sterowanie poza prostym kolorem/przezroczystością.
    *   `popuppro/views/admin/stats.tpl`:
        *   **Cel:** Jeśli moduł zbiera statystyki (jak sugeruje `popupstat.php`), ten szablon byłby używany do wyświetlania tych statystyk w back-office.
    *   `popuppro/views/templates/admin/_configure/helpers/form/form.tpl`:
        *   **Cel:** Jest to standardowy szablon nadpisujący PrestaShop dla klasy `HelperForm`, specjalnie dla formularza konfiguracji modułu. Pozwala modułowi dostosować sposób renderowania formularza ustawień, potencjalnie dodając niestandardowe pola lub układ.
-   **Szablony biblioteki SmartyTemplatesManager (`popuppro/lib/smartyTemplatesManager/tpl/` i `views/`)**:
    *   `popuppro/lib/smartyTemplatesManager/tpl/cartMini.tpl`, `example.tpl`, `freeShippingBar.tpl`, `helloCustomer.tpl`, `lastOrder.tpl`, `productHighlight.tpl`, `showReachedQtyInCart.tpl`:
        *   **Cel:** Są to predefiniowane szablony treści, które sprzedawca może wybrać lub użyć jako punkt wyjścia dla zawartości swojego pop-upu. Oferują typowe przypadki użycia, takie jak wyświetlanie mini-koszyka, ogłoszenia o darmowej wysyłce, wiadomości powitalne, szczegóły ostatniego zamówienia, wyróżnienia produktów lub wiadomości o osiągniętej ilości w koszyku. Zostaną one dynamicznie renderowane w głównym obszarze zawartości pop-upu.
    *   `popuppro/lib/smartyTemplatesManager/views/buttonManager.tpl`, `buttonManagerNoJs.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`:
        *   **Cel:** Te szablony są częścią wewnętrznej biblioteki Smarty Templates Manager, używanej w konfiguracji back-office do zarządzania i interakcji z szablonami treści. Zapewniają interfejs użytkownika do tworzenia, edytowania i wybierania tych predefiniowanych bloków treści.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Moduł nie wydaje się tworzyć niestandardowych tabel SQL.
    *   Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration`. Kluczowe nazwy konfiguracji zazwyczaj przyjmują wzorzec `POPUPPRO_NAZWA_USTAWIENIA`. Przykłady obejmują:
        *   `POPUPPRO_ENABLED`
        *   `POPUPPRO_CONTENT` (prawdopodobnie wielojęzyczne)
        *   `POPUPPRO_WIDTH`
        *   `POPUPPRO_DISPLAY_ON`
        *   `POPUPPRO_FREQUENCY`
        *   `POPUPPRO_BG_COLOR`
        *   …i tak dalej dla wszystkich opcji konfiguracyjnych.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony front-office. | Wstrzykuje niezbędne pliki CSS i JavaScript do działania pop-upu, a potencjalnie inicjalizuje globalne zmienne JavaScript lub dane konfiguracyjne do wykorzystania przez JavaScript. |
| `displayRightColumn` | Wykonywany w prawej kolumnie stron (jeśli włączony przez motyw). | Chociaż opis modułu wspomina o „Kolumnach”, jest to mniej prawdopodobne dla pełnoekranowego pop-upu. Jeśli używany, może renderować wyzwalacz dla pop-upu lub mniejszy, nie nakładający się element. |
| `displayLeftColumn` | Wykonywany w lewej kolumnie stron (jeśli włączony przez motyw). | Podobnie jak `displayRightColumn`, mniej prawdopodobne dla głównego pop-upu, ale może być używany jako wyzwalacz. |
| `displayFooter` | Wykonywany na dole każdej strony front-office, przed zamykającym tagiem `</body>`. | Może być używany do wstrzykiwania JavaScript, który musi zostać uruchomiony po pełnym załadowaniu DOM, lub do umieszczenia struktury HTML pop-upu na samym końcu dokumentu. |
| `displayProductAdditionalInfo` (lub podobny hook strony produktu) | Wykonywany na stronie produktu, zazwyczaj poniżej głównych szczegółów produktu. | Jeśli moduł obsługuje pop-upy specyficzne dla produktu, może użyć tego hooka do wstrzyknięcia wyzwalacza lub specyficznej logiki pop-upu związanej z produktem. |
| `actionFrontControllerSetMedia` | Wykonywany, gdy kontroler front-office ustawia swoje media (CSS/JS). | Powszechny hook dla modułów do efektywnego rejestrowania swoich zasobów (CSS/JS), zapewniając ich ładowanie tylko wtedy, gdy są potrzebne. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnego wsparcia, aktualizacji modułu i wszelkiej dalszej pomocy z modułem Prestashop Popup Pro, odwiedź swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz dedykowany zespół wsparcia jest gotowy pomóc Ci maksymalnie wykorzystać potencjał Twojego modułu.
