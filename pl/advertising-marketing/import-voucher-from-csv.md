---
title: "Import voucher from CSV - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Import voucher from CSV” od MyPresta.eu."
sidebar:
  label: "Import voucher from CSV - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Import voucher from CSV na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/import-voucher-from-csv.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/import-voucher-from-csv/)
>
> ---


# Import voucher from CSV

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i domyślnie włączone w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównego ekranu konfiguracji modułu. Tutaj prześlesz plik CSV i zdefiniujesz, w jaki sposób kody bonów mają być importowane i jakie mają mieć właściwości.

Strona konfiguracji jest zazwyczaj podzielona na kilka sekcji, prowadząc Cię przez proces importu.

#### **Krok 1: Prześlij plik CSV**

-   **Co robi to ustawienie:** Tutaj wybierasz plik CSV zawierający kody bonów z Twojego komputera.
-   **Efekt zmiany tego ustawienia:** Kliknięcie „Przeglądaj” lub „Wybierz plik” otwiera okno dialogowe wyboru pliku. Po wybraniu pliku jego nazwa pojawi się obok przycisku, wskazując, że jest gotowy do przesłania.
-   **Zalecana wartość:** Wybierz plik CSV, który przygotowałeś z kodami bonów.
-   **Scenariusz / przykład dla sprzedawcy:** Otrzymałeś listę 1000 unikalnych kodów bonów od partnera, takiego jak Groupon. Zapisałeś te kody w pliku CSV (np. `groupon_vouchers.csv`). Kliknąłbyś „Wybierz plik” i wybrał ten plik.

#### **Krok 2: Ustawienia pliku CSV**

Ta sekcja definiuje, jak moduł powinien interpretować Twój plik CSV.

-   **Separator CSV:**

    -   **Co robi to ustawienie:** Określa znak używany do oddzielania wartości (kolumn) w pliku CSV. Typowe separatory to przecinek (`,`), średnik (`;`) lub tabulator (`\t`).
    -   **Efekt zmiany tego ustawienia:** Jeśli zostanie wybrany niewłaściwy separator, moduł nieprawidłowo przetworzy Twój plik, a wszystkie dane mogą pojawić się w jednej kolumnie lub zostać nieprawidłowo podzielone.
    -   **Zalecana wartość:** Dopasuj separator użyty podczas tworzenia lub eksportowania pliku CSV. Większość programów do arkuszy kalkulacyjnych domyślnie używa przecinka.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój CSV wygląda tak: `CODE123,10,USD`, wybierzesz „Przecinek”. Jeśli wygląda tak: `CODE123;10;USD`, wybierzesz „Średnik”.
-   **Ogranicznik tekstu:**

    -   **Co robi to ustawienie:** Określa znak używany do otaczania wartości tekstowych, zwłaszcza tych, które mogą zawierać znak separatora. Często jest to podwójny cudzysłów (`"`).
    -   **Efekt zmiany tego ustawienia:** Jeśli Twoje pola tekstowe zawierają separator (np. nazwa produktu z przecinkiem) i nie są prawidłowo ograniczone, moduł może błędnie zinterpretować dane, co doprowadzi do nieprawidłowego parsowania.
    -   **Zalecana wartość:** Dopasuj ogranicznik użyty w Twoim CSV. Zazwyczaj „Podwójny cudzysłów”.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli opis bonu to `"10% zniżki, oferta ograniczona czasowo"`, a Twój separator to przecinek, podwójne cudzysłowy zapewniają, że „10% zniżki, oferta ograniczona czasowo” jest traktowane jako jedno pole.
-   **Pomiń pierwszą linię (nagłówek):**

    -   **Co robi to ustawienie:** Jeśli Twój plik CSV ma wiersz nagłówka (np. `Kod bonu,Wartość rabatu,Data ważności`), który opisuje kolumny, włączenie tej opcji spowoduje, że moduł zignoruje ten pierwszy wiersz podczas importu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Wiersz nagłówka jest pomijany, a importowane są tylko rzeczywiste wiersze danych.
        -   *Gdy wyłączone:* Pierwszy wiersz Twojego CSV zostanie potraktowany jako kod bonu lub dane, co jest zazwyczaj nieprawidłowe i może prowadzić do błędów.
    -   **Zalecana wartość:** „TAK”, jeśli Twój CSV ma wiersz nagłówka, „NIE”, jeśli zawiera tylko dane.
    -   **Scenariusz / przykład dla sprzedawcy:** Twój CSV zaczyna się od `kod,wartość,waluta`. Włączyłbyś to, aby zapobiec importowaniu „kod” jako rzeczywistego bonu.

#### **Krok 3: Ustawienia bonu (Właściwości ogólne)**

Ta sekcja definiuje wspólne właściwości dla wszystkich importowanych bonów. Te ustawienia dotyczą *wszystkich* kodów w Twoim pliku CSV.

-   **Nazwa:**

    -   **Co robi to ustawienie:** Jest to wewnętrzna nazwa reguły bonu w Twoim Panelu administracyjnym. Pomaga zidentyfikować grupę bonów.
    -   **Efekt zmiany tego ustawienia:** Ta nazwa jest widoczna tylko dla Ciebie w Panelu administracyjnym, nie dla klientów.
    -   **Zalecana wartość:** Opisowa nazwa, np. „Kody Groupon - Maj 2024”.
    -   **Scenariusz / przykład dla sprzedawcy:** Importujesz kody z kampanii „Letnia Wyprzedaż 2024”. Nazwałbyś to „Bony Letnia Wyprzedaż 2024”.
-   **Opis:**

    -   **Co robi to ustawienie:** Opcjonalny wewnętrzny opis reguły bonu.
    -   **Efekt zmiany tego ustawienia:** Zapewnia więcej kontekstu dla Twojego zespołu w Panelu administracyjnym.
    -   **Zalecana wartość:** Krótkie wyjaśnienie, np. „Unikalne kody na 10% zniżki, jednorazowe, ważne do 31/05/2024”.
    -   **Scenariusz / przykład dla sprzedawcy:** „Kody dostarczone przez LivingSocial dla nowych klientów.”
-   **Wyróżnij:**

    -   **Co robi to ustawienie:** Określa, czy bon jest wyróżniony w podsumowaniu koszyka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Bon będzie bardziej widoczny w podsumowaniu koszyka, potencjalnie przyciągając większą uwagę do rabatu.
        -   *Gdy wyłączone:* Bon będzie wyświetlany normalnie.
    -   **Zalecana wartość:** „NIE” do ogólnego użytku, „TAK”, jeśli chcesz podkreślić rabat.
    -   **Scenariusz / przykład dla sprzedawcy:** W przypadku specjalnej oferty ograniczonej czasowo możesz włączyć „TAK”, aby upewnić się, że klienci zauważą zastosowany rabat.
-   **Częściowe użycie:**

    -   **Co robi to ustawienie:** Pozwala klientom wykorzystać tylko część wartości bonu i zachować resztę na przyszłe zakupy.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Jeśli klient ma bon o wartości 50 USD i kupuje przedmiot za 30 USD, zachowuje saldo 20 USD na bonie.
        -   *Gdy wyłączone:* Cała wartość bonu musi zostać wykorzystana w jednej transakcji; wszelkie pozostałe saldo zostaje utracone.
    -   **Zalecana wartość:** „NIE” dla większości kodów rabatowych. „TAK” dla kart podarunkowych lub kredytu sklepowego.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli importujesz kody kart podarunkowych, włączyłbyś „TAK”. Dla standardowego kuponu „10% zniżki” użyłbyś „NIE”.
-   **Priorytet:**

    -   **Co robi to ustawienie:** Określa kolejność, w jakiej stosowane są wielokrotne bony, jeśli klient używa więcej niż jednego. Bony o wyższym priorytecie są stosowane jako pierwsze.
    -   **Efekt zmiany tego ustawienia:** Może wpływać na ostateczną kwotę rabatu, jeśli wiele bonów wchodzi w interakcje (np. rabaty procentowe vs. rabaty o stałej kwocie).
    -   **Zalecana wartość:** „1” dla najwyższego priorytetu lub pozostaw domyślne, jeśli nie masz złożonych interakcji bonów.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz bon „Darmowa wysyłka” i bon „10% zniżki”, możesz nadać „Darmowej wysyłce” wyższy priorytet, aby upewnić się, że zostanie zastosowana jako pierwsza, a następnie rabat procentowy.
-   **Status:**

    -   **Co robi to ustawienie:** Aktywuje lub dezaktywuje regułę bonu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Bony zaimportowane zgodnie z tą regułą mogą być używane przez klientów.
        -   *Gdy wyłączone:* Bony nie mogą być używane, nawet jeśli są ważne.
    -   **Zalecana wartość:** „TAK”, aby bony były natychmiast użyteczne. Możesz je później wyłączyć, jeśli zajdzie taka potrzeba.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz przygotować bony z wyprzedzeniem, ale aktywować je dopiero w dniu rozpoczęcia kampanii. Początkowo ustawiłbyś „NIE”, a następnie zmienił na „TAK”, gdy będziesz gotowy.

#### **Krok 4: Ustawienia bonu (Warunki)**

Ta sekcja definiuje warunki, na jakich importowane bony mogą być używane.

-   **Minimalna kwota:**

    -   **Co robi to ustawienie:** Określa minimalną kwotę zamówienia (przed wysyłką i podatkami) wymaganą do ważności bonu.
    -   **Efekt zmiany tego ustawienia:** Klienci muszą spełnić tę minimalną wartość zakupu, aby zastosować rabat.
    -   **Zalecana wartość:** „0”, jeśli nie jest wymagana minimalna kwota, lub konkretna kwota (np. „50.00”).
    -   **Scenariusz / przykład dla sprzedawcy:** „Otrzymaj 10 USD zniżki na zamówienia powyżej 100 USD.” Ustawiłbyś „100.00”.
-   **Waluta:**

    -   **Co robi to ustawienie:** Wybiera walutę dla minimalnej kwoty.
    -   **Efekt zmiany tego ustawienia:** Zapewnia prawidłową interpretację minimalnej kwoty dla sklepów wielowalutowych.
    -   **Zalecana wartość:** Domyślna waluta Twojego sklepu (np. „USD”, „EUR”).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój sklep działa w wielu walutach, upewnij się, że to odpowiada walucie, której klienci mają używać dla tego bonu.
-   **Kumulatywne z innymi bonami:**

    -   **Co robi to ustawienie:** Określa, czy ten bon może być łączony z innymi aktywnymi bonami w tym samym zamówieniu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klienci mogą używać tego bonu wraz z innymi ważnymi bonami.
        -   *Gdy wyłączone:* Ten bon nie może być używany, jeśli inny bon jest już zastosowany do koszyka.
    -   **Zalecana wartość:** „NIE” dla większości unikalnych kodów, aby zapobiec nadmiernym rabatom. „TAK” dla konkretnych promocji, takich jak „darmowa wysyłka”, które chcesz połączyć.
    -   **Scenariusz / przykład dla sprzedawcy:** Importujesz kody „10% zniżki”. Prawdopodobnie chcesz „NIE”, aby zapobiec kumulowaniu przez klientów wielu rabatów procentowych.
-   **Data ważności (Od):**

    -   **Co robi to ustawienie:** Ustawia datę początkową, od której importowane bony stają się ważne.
    -   **Efekt zmiany tego ustawienia:** Bony nie mogą być używane przed tą datą.
    -   **Zalecana wartość:** Dzisiejsza data lub przyszła data dla zaplanowanych promocji.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby bony były aktywne od przyszłego poniedziałku. Wybrałbyś datę przyszłego poniedziałku.
-   **Data ważności (Do):**

    -   **Co robi to ustawienie:** Ustawia datę końcową, po której importowane bony przestają być ważne.
    -   **Efekt zmiany tego ustawienia:** Bony nie mogą być używane po tej dacie.
    -   **Zalecana wartość:** Przyszła data odpowiadająca zakończeniu Twojej promocji.
    -   **Scenariusz / przykład dla sprzedawcy:** Twoja kampania kończy się 31 grudnia. Wybrałbyś 31 grudnia.
-   **Ilość:**

    -   **Co robi to ustawienie:** Definiuje całkowitą liczbę razy, ile *każdy indywidualny kod bonu* może być użyty.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ustawione na 1:* Każdy kod w Twoim CSV może być użyty tylko raz (najczęściej dla unikalnych kodów).
        -   *Ustawione na >1:* Każdy kod może być użyty wielokrotnie do tego limitu.
    -   **Zalecana wartość:** „1” dla unikalnych, jednorazowych kodów (np. z Groupona).
    -   **Scenariusz / przykład dla sprzedawcy:** Dla 1000 unikalnych kodów Groupon, ustawiłbyś to na „1”, aby każdy klient mógł użyć swojego konkretnego kodu tylko raz.
-   **Ilość na użytkownika:**

    -   **Co robi to ustawienie:** Definiuje, ile razy *jeden klient* może użyć *dowolnego* bonu z tej zaimportowanej partii.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ustawione na 1:* Klient może użyć tylko jednego bonu z tej partii, nawet jeśli ma wiele unikalnych kodów.
        -   *Ustawione na >1:* Klient może użyć wielu bonów z tej partii, do tego limitu.
    -   **Zalecana wartość:** „1” dla większości kampanii z unikalnymi kodami, aby zapobiec używaniu wielu kodów przez jednego klienta.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby każdy klient skorzystał tylko z jednego bonu „powitalnego”. Ustawiłbyś to na „1”.

#### **Krok 5: Ustawienia bonu (Akcje)**

Ta sekcja definiuje, jaki rodzaj rabatu zapewnią importowane bony.

-   **Darmowa wysyłka:**

    -   **Co robi to ustawienie:** Jeśli włączone, bon zapewni darmową wysyłkę dla zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Koszty wysyłki są anulowane po zastosowaniu bonu.
        -   *Gdy wyłączone:* Koszty wysyłki są obliczane normalnie.
    -   **Zalecana wartość:** „NIE”, chyba że głównym celem tych bonów jest darmowa wysyłka.
    -   **Scenariusz / przykład dla sprzedawcy:** Importujesz kody na promocję „Weekend z darmową wysyłką”. Włączyłbyś „TAK”.
-   **Zastosuj rabat:**

    -   **Co robi to ustawienie:** Określa typ i wartość rabatu zastosowanego przez bon.
    -   **Efekt zmiany tego ustawienia:** Jest to podstawowy mechanizm rabatowy.
    -   **Zalecana wartość:** Wybierz jedną z poniższych opcji w zależności od Twojej promocji.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz dać 10% zniżki.
    -   **Procent:**

        -   **Co robi to ustawienie:** Stosuje rabat procentowy do zamówienia.
        -   **Efekt zmiany tego ustawienia:** Pole `Wartość` zostanie zinterpretowane jako procent (np. `10` dla 10%).
        -   **Zalecana wartość:** Wybierz to dla rabatów procentowych.
        -   **Scenariusz / przykład dla sprzedawcy:** Dla promocji „15% zniżki” wybierz „Procent” i wprowadź `15` w polu `Wartość`.
    -   **Kwota:**

        -   **Co robi to ustawienie:** Stosuje stały rabat pieniężny do zamówienia.
        -   **Efekt zmiany tego ustawienia:** Pole `Wartość` zostanie zinterpretowane jako stała kwota w wybranej walucie (np. `10.00` dla 10 USD zniżki).
        -   **Zalecana wartość:** Wybierz to dla rabatów o stałej kwocie.
        -   **Scenariusz / przykład dla sprzedawcy:** Dla promocji „20 USD zniżki” wybierz „Kwota” i wprowadź `20.00` w polu `Wartość`.
    -   **Brak:**

        -   **Co robi to ustawienie:** Jeśli wybrane, bon nie zastosuje żadnego rabatu pieniężnego ani procentowego. Jest to zazwyczaj używane, gdy jedyną akcją bonu jest „Darmowa wysyłka” lub „Wyślij prezent”.
        -   **Efekt zmiany tego ustawienia:** Nie jest stosowana żadna wartość rabatu.
        -   **Zalecana wartość:** Wybierz „Brak” tylko wtedy, gdy używasz „Darmowej wysyłki” lub „Wyślij prezent” jako głównej akcji.
        -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz oferować tylko darmową wysyłkę, wybrałbyś tutaj „Brak” i włączył „Darmową wysyłkę” powyżej.
-   **Wartość:**

    -   **Co robi to ustawienie:** Rzeczywista wartość liczbowa rabatu. Jej interpretacja zależy od tego, czy powyżej wybrano „Procent” czy „Kwota”.
    -   **Efekt zmiany tego ustawienia:** Bezpośrednio kontroluje wielkość rabatu.
    -   **Zalecana wartość:** Wartość liczbowa (np. `10` dla 10% lub 10 USD).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli wybrałeś „Procent” i chcesz 15% zniżki, wprowadź `15`. Jeśli wybrałeś „Kwota” i chcesz 20 USD zniżki, wprowadź `20.00`.
-   **Zastosuj rabat do:**

    -   **Co robi to ustawienie:** Określa, do czego rabat jest stosowany.
    -   **Efekt zmiany tego ustawienia:**
        -   *Zamówienie (bez wysyłki):* Rabat dotyczy całkowitej wartości produktów w koszyku.
        -   *Konkretny produkt:* Rabat dotyczy tylko określonego produktu, który określisz.
        -   *Najtańszy produkt:* Rabat dotyczy najtańszego produktu w koszyku.
        -   *Wybrane produkty:* Rabat dotyczy wyboru produktów.
    -   **Zalecana wartość:** „Zamówienie (bez wysyłki)” dla ogólnych rabatów.
    -   **Scenariusz / przykład dla sprzedawcy:** Dla ogólnej kampanii „10% zniżki na wszystko” wybierz „Zamówienie (bez wysyłki)”. Jeśli jest to „10% zniżki na wszystkie T-shirty”, wybrałbyś „Wybrane produkty”, a następnie wybrał kategorię/produkty T-shirtów.
-   **Wyślij prezent:**

    -   **Co robi to ustawienie:** Jeśli włączone, bon doda konkretny produkt do koszyka klienta jako darmowy prezent.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Zostaniesz poproszony o wybranie produktu, który ma zostać dodany jako prezent.
        -   *Gdy wyłączone:* Nie dodaje się prezentu.
    -   **Zalecana wartość:** „NIE”, chyba że prowadzisz promocję typu „kup X, otrzymaj Y za darmo”.
    -   **Scenariusz / przykład dla sprzedawcy:** „Kup dowolny produkt, otrzymaj darmowy brelok.” Włączyłbyś „TAK” i wybrał produkt brelok.

Po skonfigurowaniu wszystkich ustawień zazwyczaj znajdziesz przycisk „Zapisz” lub „Importuj”. Kliknij go, aby rozpocząć proces importu. Moduł odczyta Twój plik CSV i utworzy odpowiednie reguły bonów w bazie danych PrestaShop na podstawie zdefiniowanych ustawień.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Prześlij plik CSV | Twój przygotowany CSV | Wybiera plik zawierający kody bonów. |
| | Separator CSV | Przecinek (`,`) | Znak oddzielający kolumny w Twoim CSV. Musi pasować do Twojego pliku. |
| | Ogranicznik tekstu | Podwójny cudzysłów (`"`) | Znak otaczający pola tekstowe w Twoim CSV. Musi pasować do Twojego pliku. |
| | Pomiń pierwszą linię (nagłówek) | TAK (jeśli nagłówek istnieje) | Ignoruje pierwszy wiersz Twojego CSV, jeśli jest to nagłówek. |
| | **Ustawienia bonu (Ogólne)** | | |
| | Nazwa | Opisowa nazwa | Wewnętrzna nazwa reguły bonu w Panelu administracyjnym. |
| | Opis | Opcjonalny tekst | Wewnętrzny opis reguły bonu. |
| | Wyróżnij | NIE | Wyróżnia bon w podsumowaniu koszyka. |
| | Częściowe użycie | NIE | Pozwala na częściowe użycie wartości bonu. TAK dla kart podarunkowych. |
| | Priorytet | 1 | Kolejność zastosowania dla wielu bonów. |
| | Status | TAK | Aktywuje/dezaktywuje regułę bonu. |
| | **Ustawienia bonu (Warunki)** | | |
| | Minimalna kwota | 0 | Minimalna kwota zamówienia dla ważności bonu. |
| | Waluta | Domyślna sklepu | Waluta dla minimalnej kwoty. |
| | Kumulatywne z innymi bonami | NIE | Pozwala na łączenie z innymi bonami. |
| | Data ważności (Od) | Dzisiejsza data | Data rozpoczęcia ważności bonu. |
| | Data ważności (Do) | Przyszła data | Data zakończenia ważności bonu. |
| | Ilość | 1 | Całkowita liczba użyć na *indywidualny* kod bonu. |
| | Ilość na użytkownika | 1 | Całkowita liczba użyć na *klienta* z tej partii. |
| | **Ustawienia bonu (Akcje)** | | |
| | Darmowa wysyłka | NIE | Udziela darmowej wysyłki. |
| | Zastosuj rabat | Procent / Kwota | Typ rabatu (procentowy lub stała kwota). |
| | Wartość | Wartość liczbowa | Rzeczywista wartość rabatu (np. 10 dla 10% lub 10 USD). |
| | Zastosuj rabat do | Zamówienie (bez wysyłki) | Do czego rabat jest stosowany (zamówienie, konkretny produkt itp.). |
| | Wyślij prezent | NIE | Dodaje darmowy produkt jako prezent. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zaimportowałem plik CSV, ale bony nie działają lub nie są widoczne.**
O:

1.  **Sprawdź status modułu:** Upewnij się, że sam moduł jest włączony w **Moduły > Menedżer modułów**.
2.  **Sprawdź status bonu:** Przejdź do **Katalog > Rabaty > Reguły koszyka** (lub **Reguły cenowe > Reguły koszyka** w starszych wersjach). Znajdź regułę bonu utworzoną przez import (będzie miała „Nazwę” określoną podczas konfiguracji). Upewnij się, że jej „Status” jest ustawiony na „TAK” (aktywny).
3.  **Daty ważności:** Sprawdź ponownie ustawienia „Data ważności (Od)” i „Data ważności (Do)”. Jeśli bieżąca data znajduje się poza tym zakresem, bony nie będą działać.
4.  **Minimalna kwota:** Sprawdź, czy koszyk klienta spełnia warunek „Minimalna kwota”, który ustawiłeś.
5.  **Kody bonów:** Upewnij się, że kody w Twoim CSV są dokładnie takie, jak klienci je wprowadzają (rozróżnianie wielkości liter, bez dodatkowych spacji).

**P: Mój plik CSV nie jest prawidłowo parsowany. Wszystkie dane znajdują się w jednej kolumnie lub kolumny są pomieszane.**
O: Jest to prawie zawsze spowodowane nieprawidłowymi ustawieniami „Separator CSV” lub „Ogranicznik tekstu”.

1.  **Otwórz swój plik CSV** w prostym edytorze tekstu (takim jak Notatnik, Sublime Text, VS Code, a nawet Excel/Google Sheets, ale następnie zapisz ponownie jako CSV).
2.  **Zidentyfikuj separator:** Sprawdź, jak wartości są oddzielone. Czy jest to przecinek (`,`), średnik (`;`) czy tabulator? Wybierz prawidłowy w ustawieniach modułu.
3.  **Zidentyfikuj ogranicznik:** Poszukaj znaków otaczających tekst, zazwyczaj podwójnych cudzysłowów (`"`). Jeśli są obecne, upewnij się, że „Ogranicznik tekstu” jest ustawiony na „Podwójny cudzysłów”.
4.  **Wiersz nagłówka:** Jeśli Twój CSV ma nagłówek, upewnij się, że „Pomiń pierwszą linię (nagłówek)” jest ustawione na „TAK”.

**P: Zaimportowałem bony, ale teraz chcę je usunąć lub wyłączyć.**
O:

1.  Przejdź do **Katalog > Rabaty > Reguły koszyka** (lub **Reguły cenowe > Reguły koszyka**).
2.  Znajdź regułę bonu, którą utworzyłeś za pomocą modułu (używając przypisanej „Nazwy”).
3.  Możesz albo:
    -   **Wyłączyć:** Kliknij zielony znacznik wyboru obok reguły, aby zmienić go na czerwony „X”. Spowoduje to dezaktywację wszystkich bonów objętych tą regułą.
    -   **Usunąć:** Wybierz regułę i użyj akcji masowych lub kliknij ikonę usuwania, aby usunąć całą regułę i wszystkie powiązane kody bonów.

Usunięcie reguły koszyka jest trwałe i nie można go cofnąć.

**P: Czy mogę aktualizować istniejące bony za pomocą tego modułu?**
O: Nie, ten moduł jest przeznaczony do importowania *nowych* bonów. Nie posiada funkcji aktualizacji istniejących kodów bonów ani reguł koszyka. Jeśli musisz zmodyfikować istniejący bon, musisz to zrobić ręcznie za pośrednictwem **Katalog > Rabaty > Reguły koszyka**.

**P: Dlaczego moje zaimportowane bony nie kumulują się z innymi rabatami?**
O: Sprawdź ustawienie „Kumulatywne z innymi bonami” w konfiguracji modułu. Jeśli ustawiłeś je na „NIE” (co jest często zalecane dla unikalnych kodów), klienci nie będą mogli używać tych bonów wraz z innymi aktywnymi rabatami w swoim koszyku. Jeśli chcesz, aby były kumulatywne, ustaw to na „TAK” podczas importu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem „Import voucher from CSV”.

### 4.1 Przegląd architektury

Moduł `importvoucher` to standardowy moduł PrestaShop, skupiający się głównie na funkcjonalności Panelu administracyjnego. Wykorzystuje on podstawowe ObjectModels PrestaShop `CartRule` i `CartRuleProduct` do tworzenia i zarządzania kodami rabatowymi. Główna logika modułu znajduje się w jego głównym pliku PHP, obsługującym przesyłanie plików, parsowanie CSV i interakcje z bazą danych. Nie wprowadza złożonych wzorców MVC z dedykowanymi kontrolerami front-office ani admin, ale raczej używa metody `getContent()` dla swojego interfejsu konfiguracyjnego.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje dedykowanych kontrolerów front-office ani back-office w katalogach `controllers/front` ani `controllers/admin`. Cała logika administracyjna, w tym formularz konfiguracji i proces importu CSV, jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Podstawowe klasy i modele (`classes/`)

Moduł nie definiuje niestandardowych klas w katalogu `classes/`. Bezpośrednio współdziała z podstawowymi ObjectModels PrestaShop `CartRule` i `CartRuleProduct` w celu tworzenia i zarządzania kodami rabatowymi.

-   **`CartRule` (Podstawowa klasa PrestaShop):**

    -   Współdziała z tabelą bazy danych `ps_cart_rule`.
    -   Moduł wypełnia właściwości obiektów `CartRule` (np. `name`, `description`, `code`, `quantity`, `quantity_per_user`, `date_from`, `date_to`, `minimum_amount`, `reduction_percent`, `reduction_amount`, `free_shipping`, `active`, `highlight`, `partial_use`, `priority`, `cumulative_with_other_rules`) na podstawie konfiguracji i danych CSV.
    -   Metoda `add()` klasy `CartRule` jest używana do utrwalania nowych reguł bonów w bazie danych.
-   **`CartRuleProduct` (Podstawowa klasa PrestaShop):**

    -   Współdziała z tabelami `ps_cart_rule_product_rule_group` i `ps_cart_rule_product_rule`.
    -   Używane, gdy wybrano opcję „Zastosuj rabat do: Wybrane produkty”, aby powiązać regułę koszyka z określonymi produktami, kategoriami lub producentami.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `importvoucher/lib/voucherengine/script.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Ten skrypt prawdopodobnie obsługuje dynamiczne interakcje na stronie konfiguracji modułu. Może to obejmować:
        -   Pokazywanie/ukrywanie pól na podstawie wybranych opcji (np. pokazywanie pola wejściowego „Wartość” tylko po wybraniu typu rabatu „Procent” lub „Kwota”).
        -   Wywołania AJAX do walidacji formularzy lub przetwarzania.
        -   Inicjalizacja selektora dat dla „Daty ważności (Od)” i „Daty ważności (Do)”.
        -   Potencjalnie podglądy parsowania CSV po stronie klienta lub obsługa błędów.
    -   **Interakcja:** Wiąże słuchaczy zdarzeń z elementami formularza (np. zdarzenia `change` na przyciskach radiowych, `click` na przyciskach).

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `importvoucher/lib/voucherengine/ps16.css`:

    -   **Zakres:** Panel administracyjny (prawdopodobnie dla kompatybilności z PrestaShop 1.6, ale może być ładowany w nowszych wersjach dla ogólnego stylu).
    -   **Cel:** Zapewnia stylizację interfejsu konfiguracji modułu, zapewniając jego wizualną integrację z motywem Panelu administracyjnego PrestaShop 1.6. Może zawierać ogólną stylizację elementów formularza, dostosowania układu i specyficzne style oparte na klasach dla komponentów modułu.
    -   **Kluczowe selektory:** Prawdopodobnie celuje w ogólne elementy formularza (`.form-group`, `.control-label`, `.form-control`) i potencjalnie w specyficzne dla modułu opakowania (np. `#module_form_importvoucher`).
-   `importvoucher/views/css/css.css`:

    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Zawiera ogólne lub specyficzne reguły stylów dla strony konfiguracji modułu. Może to nadpisywać lub rozszerzać `ps16.css` dla nowszych wersji PrestaShop lub zapewniać unikalną stylizację dla niestandardowych elementów w szablonie modułu.
    -   **Kluczowe selektory:** Podobnie jak `ps16.css`, skupiając się na elementach interfejsu użytkownika modułu. Programiści powinni sprawdzić ten plik pod kątem konkretnych nazw klas, aby w razie potrzeby nadpisać je w swoich niestandardowych motywach administracyjnych.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł wykorzystuje szablony Smarty do renderowania interfejsu konfiguracji Panelu administracyjnego.

-   **`importvoucher/views/backoffice.tpl`**:

    -   **Zakres:** Szablon administracyjny.
    -   **Cel:** Jest to prawdopodobnie główny plik szablonu renderowany przez metodę `getContent()`. Działa jako kontener dla całego formularza konfiguracji modułu, w tym wszystkich ustawień, pól wejściowych i przycisków. Prawdopodobnie zawiera inne częściowe szablony.
    -   **Zawartość:** Zawiera strukturę HTML strony konfiguracji modułu, w tym tagi formularza, zestawy pól i potencjalnie wywołania do włączenia innych plików `.tpl`.
-   **`importvoucher/views/csv.tpl`**:

    -   **Zakres:** Szablon administracyjny.
    -   **Cel:** Ten szablon prawdopodobnie obsługuje wyświetlanie sekcji przesyłania pliku CSV i powiązanych ustawień (separator, ogranicznik, pominięcie nagłówka). Jest to częściowy szablon dołączony do `backoffice.tpl`.
-   **`importvoucher/views/csv_file.tpl`**:

    -   **Zakres:** Szablon administracyjny.
    -   **Cel:** Bardziej szczegółowy częściowy szablon, być może specjalnie dla samego pola wejściowego pliku lub do wyświetlania informacji o przesłanym pliku CSV.
-   **`importvoucher/views/file_settings.tpl`**:

    -   **Zakres:** Szablon administracyjny.
    -   **Cel:** Ten szablon prawdopodobnie renderuje sekcję „Ustawienia pliku CSV”, w tym pola wejściowe dla separatora CSV, ogranicznika tekstu i pola wyboru „pomiń pierwszą linię”.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych:**
    Moduł nie tworzy niestandardowych tabel bazy danych. Bezpośrednio współdziała z podstawowymi tabelami PrestaShop związanymi z regułami koszyka:

    -   `ps_cart_rule`: Przechowuje główne właściwości każdej reguły rabatowej (nazwa, kod, daty, minimalna kwota itp.).
    -   `ps_cart_rule_lang`: Przechowuje pola specyficzne dla języka dla reguł koszyka (np. `name`, jeśli jest wielojęzyczne).
    -   `ps_cart_rule_product_rule_group`: Używane podczas stosowania rabatów do określonych produktów/kategorii.
    -   `ps_cart_rule_product_rule`: Definiuje rzeczywiste reguły produktów w grupie.
    -   `ps_cart_rule_product_rule_exclusion`: Do wykluczania określonych produktów z reguły.
    -   `ps_cart_rule_carrier`: Do ograniczeń przewoźników.
    -   `ps_cart_rule_country`: Do ograniczeń krajów.
    -   `ps_cart_rule_group`: Do ograniczeń grup klientów.
    -   `ps_cart_rule_shop`: Dla kontekstu wielu sklepów.
-   **Tabela zarejestrowanych hooków:**
    Główna funkcja modułu znajduje się w konfiguracji Panelu administracyjnego. Chociaż opis modułu wspomina o „Hookach Front-Office: Nagłówek, Kolumny, Produkt lub Stopka”, dostarczony spis plików i typowa funkcjonalność modułu importu sugerują, że nie renderuje on aktywnie treści w tych hookach front-office. Te wzmianki mogą być ogólne lub odnosić się do miejsc, w których widoczne są *efekty* zaimportowanych bonów (np. bon zastosowany w koszyku, który jest częścią procesu realizacji zamówienia, potencjalnie pod wpływem hooków).

    Moduł wykorzystuje głównie następujący hook dla swojego interfejsu Panelu administracyjnego:

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `displayBackOfficeHeader` | Renderuje się w sekcji `<head>` stron Panelu administracyjnego. | Służy do dołączania zasobów CSS i JavaScript dla strony konfiguracji modułu. |
    | `moduleRoutes` (PrestaShop 1.7+) | Gdy inicjowane są trasy modułu. | Gdyby moduł miał niestandardowe kontrolery front-office, ten hook definiowałby ich adresy URL. (Nie dotyczy tutaj, ponieważ nie ma niestandardowych kontrolerów front-office). |

    Podstawowa logika modułu do *tworzenia* bonów nie opiera się na konkretnych hookach PrestaShop, ale raczej na bezpośrednich wywołaniach metod `CartRule` wyzwalanych przez przesłanie formularza w `getContent()`.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Import voucher from CSV”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
