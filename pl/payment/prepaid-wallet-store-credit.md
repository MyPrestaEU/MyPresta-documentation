---
title: "Portfel Przedpłacony i Kredyt Sklepowy - Instrukcja Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów dla modułu PrestaShop „Portfel Przedpłacony i Kredyt Sklepowy” od MyPresta.eu."
sidebar:
  label: "Portfel Przedpłacony i Kredyt Sklepowy - Instrukcja Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Prepaid Wallet & Store Credit na MyPresta.eu](https://mypresta.eu/modules/payment-process/prepaid-wallet-store-credit.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/payment/prepaid-wallet-store-credit/)
>
> ---


# Portfel Przedpłacony i Kredyt Sklepowy

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj)

To jest główny ekran konfiguracji, na którym ustawisz podstawowe zachowanie systemu Portfela Przedpłaconego.

#### Zakładka Ustawienia Ogólne

-   **Włącz moduł:**

    -   **Co robi to ustawienie:** To jest główny przełącznik do włączania lub wyłączania całego systemu Portfela Przedpłaconego dla Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klienci będą widzieć opcje portfela, będą mogli doładowywać, używać kredytu, a Ty będziesz mógł zarządzać portfelami w panelu administracyjnym.
        -   *Gdy wyłączone:* Cała funkcjonalność portfela jest ukryta przed klientami, a oni nie mogą używać ani zarządzać swoim kredytem. Zarządzanie przez administratora może być nadal dostępne, ale nie będzie miało wpływu na front office.
    -   **Zalecana wartość:** TAK (aby aktywować moduł).
    -   **Scenariusz / przykład sprzedawcy:** Jesteś gotowy do uruchomienia programu lojalnościowego. Włącz to ustawienie. Jeśli musisz tymczasowo wyłączyć moduł na czas konserwacji, wyłącz go.
-   **Zezwól klientom na doładowywanie portfela:**

    -   **Co robi to ustawienie:** Określa, czy klienci mogą aktywnie samodzielnie dodawać środki do swojego portfela.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klienci zobaczą opcję „Doładuj portfel” na swoim koncie, co pozwoli im kupić kredyt sklepowy.
        -   *Gdy wyłączone:* Klienci mogą otrzymywać kredyt tylko z kodów podarunkowych lub zwrotów/bonusów wydanych przez administratora. Nie mogą kupować kredytu bezpośrednio.
    -   **Zalecana wartość:** TAK (aby zachęcić do samoobsługowej lojalności).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz, aby klienci mogli kupować kredyt sklepowy, kiedy tylko chcą. Włącz to. Jeśli chcesz wydawać kredyt tylko jako nagrody lub karty podarunkowe, wyłącz to.
-   **Minimalna kwota doładowania:**

    -   **Co robi to ustawienie:** Ustawia najniższą kwotę, jaką klient może dodać do swojego portfela w jednej transakcji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiona jest wartość (np. 10.00):* Klienci nie mogą doładować mniej niż ta kwota.
        -   *Gdy ustawiona na 0 lub pusta:* Nie jest egzekwowana minimalna kwota doładowania.
    -   **Zalecana wartość:** 10.00 (lub rozsądna kwota dla Twojej firmy, aby pokryć opłaty transakcyjne i zachęcić do znaczących doładowań).
    -   **Scenariusz / przykład sprzedawcy:** Nie chcesz, aby klienci doładowywali 0.50 EUR. Ustaw to na 5.00 EUR, aby zapewnić minimalną wartość.
-   **Maksymalna kwota doładowania:**

    -   **Co robi to ustawienie:** Ustawia najwyższą kwotę, jaką klient może dodać do swojego portfela w jednej transakcji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiona jest wartość (np. 500.00):* Klienci nie mogą doładować więcej niż ta kwota.
        -   *Gdy ustawiona na 0 lub pusta:* Nie jest egzekwowana maksymalna kwota doładowania.
    -   **Zalecana wartość:** 500.00 (lub odpowiedni górny limit do zarządzania ryzykiem i dużymi transakcjami).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz zapobiec ekstremalnie dużym pojedynczym doładowaniom ze względów bezpieczeństwa lub płynności finansowej. Ustaw to na 1000.00 EUR.
-   **Zezwól klientom na kupowanie kodów podarunkowych:**

    -   **Co robi to ustawienie:** Kontroluje, czy klienci mogą kupować kody podarunkowe, aby dawać je innym.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klienci mogą kupować kody podarunkowe o określonej wartości, które mogą być następnie wykorzystane przez każdego.
        -   *Gdy wyłączone:* Kody podarunkowe mogą być generowane i wydawane tylko przez administratora sklepu.
    -   **Zalecana wartość:** TAK (aby rozszerzyć opcje wręczania prezentów).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz oferować cyfrowe karty podarunkowe. Włącz to, aby klienci mogli je kupować dla przyjaciół i rodziny.
-   **Wygasanie kodu podarunkowego (dni):**

    -   **Co robi to ustawienie:** Określa, ile dni kod podarunkowy pozostaje ważny po jego zakupie lub wygenerowaniu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiona jest liczba (np. 365):* Kody podarunkowe wygasną po tylu dniach.
        -   *Gdy ustawiona na 0 lub pusta:* Kody podarunkowe nie wygasną.
    -   **Zalecana wartość:** 365 (częsty czas trwania kart podarunkowych, lub 0 dla braku wygaśnięcia).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz, aby kody podarunkowe były używane w ciągu roku. Ustaw to na 365.
-   **Wygasanie salda portfela (dni):**

    -   **Co robi to ustawienie:** Określa, ile dni środki w portfelu pozostają ważne po ich dodaniu (poprzez doładowanie, wykorzystanie kodu podarunkowego lub kredyt administratora).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiona jest liczba (np. 180):* Środki w portfelu klienta wygasną po tylu dniach.
        -   *Gdy ustawiona na 0 lub pusta:* Środki w portfelu nie wygasną.
    -   **Zalecana wartość:** 0 (brak wygaśnięcia, aby zmaksymalizować zadowolenie klienta), lub 180/365, jeśli chcesz zachęcić do użycia.
    -   **Scenariusz / przykład sprzedawcy:** Chcesz zachęcić klientów do wykorzystania salda portfela w ciągu 6 miesięcy. Ustaw to na 180. Pamiętaj o przepisach dotyczących ochrony konsumentów w Twoim regionie w zakresie wygasania kart podarunkowych.
-   **Wyślij e-mail z przypomnieniem o wygaśnięciu (dni przed wygaśnięciem):**

    -   **Co robi to ustawienie:** Jeśli włączono wygasanie salda portfela, to ustawienie określa, ile dni przed wygaśnięciem zostanie wysłane przypomnienie e-mail do klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawiona jest liczba (np. 7):* Klienci otrzymają e-mail 7 dni przed wygaśnięciem salda ich portfela.
        -   *Gdy ustawiona na 0 lub pusta:* Nie zostaną wysłane żadne e-maile z przypomnieniem o wygaśnięciu.
    -   **Zalecana wartość:** 7 (daje klientom wystarczająco dużo czasu na reakcję).
    -   **Scenariusz / przykład sprzedawcy:** Masz 180-dniowy termin wygaśnięcia. Ustaw to na 7, aby przypomnieć klientom o wykorzystaniu środków, zanim je stracą.
-   **Zezwól na częściowe płatności portfelem:**

    -   **Co robi to ustawienie:** Kontroluje, czy klienci mogą używać salda swojego portfela do opłacenia tylko części zamówienia, łącząc je z inną metodą płatności.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Jeśli saldo portfela jest mniejsze niż całkowita kwota zamówienia, klienci mogą wykorzystać całe saldo i zapłacić resztę inną metodą.
        -   *Gdy wyłączone:* Klienci mogą używać swojego portfela tylko wtedy, gdy pokrywa on *całą* kwotę zamówienia. W przeciwnym razie muszą wybrać inną metodę płatności.
    -   **Zalecana wartość:** TAK (aby zmaksymalizować wykorzystanie portfela i zmniejszyć porzucanie koszyków).
    -   **Scenariusz / przykład sprzedawcy:** Klient ma 10 EUR w portfelu i zamówienie na 50 EUR. Jeśli włączone, płaci 10 EUR portfelem i 40 EUR kartą kredytową. Jeśli wyłączone, nie może w ogóle użyć portfela do tego zamówienia.
-   **Opcja zwrotu do portfela:**

    -   **Co robi to ustawienie:** Pozwala oferować klientom opcję otrzymania zwrotu za zwrócone zamówienia bezpośrednio do ich portfela sklepowego, zamiast z powrotem na oryginalną metodę płatności.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Podczas przetwarzania zwrotu w panelu administracyjnym zobaczysz opcję zwrotu do portfela klienta.
        -   *Gdy wyłączone:* Zwroty muszą być przetwarzane za pomocą standardowych metod PrestaShop (np. z powrotem na kartę kredytową).
    -   **Zalecana wartość:** TAK (aby utrzymać środki w Twoim sklepie i uprościć zwroty).
    -   **Scenariusz / przykład sprzedawcy:** Klient zwraca przedmiot. Zamiast zwrotu na kartę kredytową, oferujesz wpłacenie pieniędzy do jego portfela, zachęcając go do zakupu czegoś innego w Twoim sklepie.
-   **Włącz obsługę wielu walut:**

    -   **Co robi to ustawienie:** Aktywuje zdolność modułu do obsługi sald portfela i transakcji w wielu walutach, dopasowując się do skonfigurowanych walut Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Salda portfela są zarządzane dla każdej waluty. Klient doładowujący w EUR będzie miał saldo w EUR, a doładowujący w USD będzie miał saldo w USD.
        -   *Gdy wyłączone:* Wszystkie transakcje portfela są konwertowane na domyślną walutę Twojego sklepu, co może prowadzić do problemów z kursem wymiany.
    -   **Zalecana wartość:** TAK (jeśli Twój sklep działa w wielu walutach).
    -   **Scenariusz / przykład sprzedawcy:** Masz klientów w UE i USA. Włączenie tego zapewnia, że klient, który doładowuje 50 EUR, ma 50 EUR w portfelu, a klient, który doładowuje 50 USD, ma 50 USD, zapobiegając stratom z tytułu przeliczania walut.

#### Zakładka Bonusy za doładowanie

-   **Włącz bonusy za doładowanie:**

    -   **Co robi to ustawienie:** Aktywuje system nagradzania klientów dodatkowym kredytem, gdy doładują swój portfel powyżej określonych progów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Zdefiniowane poniżej zasady bonusów zostaną zastosowane do doładowań klientów.
        -   *Gdy wyłączone:* Nie zostaną przyznane żadne bonusy za doładowania.
    -   **Zalecana wartość:** TAK (aby zachęcić do większych doładowań i zwiększyć AOV).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz dać klientom dodatkowe 5% kredytu, jeśli doładują 100 EUR lub więcej. Włącz to.
-   **Poziomy bonusów (Dodaj/Edytuj/Usuń):**

    -   **Co robi to ustawienie:** Pozwala zdefiniować konkretne zasady bonusów w oparciu o kwotę doładowania. Każdy poziom składa się z minimalnej wartości doładowania i procentu bonusu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Dodanie poziomu (np. „Min. kwota: 100, Bonus %: 5”):* Klienci doładowujący 100 EUR lub więcej otrzymają dodatkowe 5% tej kwoty do swojego portfela.
        -   *Edycja poziomu:* Zmienia zasady bonusów dla tego konkretnego progu.
        -   *Usunięcie poziomu:* Usuwa zasadę bonusu.
    -   **Zalecana wartość:** Utwórz 2-3 poziomy (np. 5% za 100 EUR, 10% za 200 EUR), aby zachęcić do stopniowo większych doładowań.
    -   **Scenariusz / przykład sprzedawcy:**
        -   Poziom 1: Min. kwota = 50 EUR, Bonus % = 2% (Klient doładowuje 50 EUR, otrzymuje 51 EUR w portfelu)
        -   Poziom 2: Min. kwota = 100 EUR, Bonus % = 5% (Klient doładowuje 100 EUR, otrzymuje 105 EUR w portfelu)
        -   Poziom 3: Min. kwota = 200 EUR, Bonus % = 10% (Klient doładowuje 200 EUR, otrzymuje 220 EUR w portfelu)

#### Zakładka Opcje wyświetlania

-   **Wyświetl saldo portfela w nagłówku:**

    -   **Co robi to ustawienie:** Wyświetla aktualne saldo portfela klienta w widocznym miejscu w sekcji nagłówka Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Zalogowani klienci zobaczą swoje saldo (np. „Twój portfel: 25.00 EUR”) w pobliżu linku do swojego konta.
        -   *Gdy wyłączone:* Saldo jest widoczne tylko na dedykowanej stronie „Mój portfel”.
    -   **Zalecana wartość:** TAK (dla wysokiej widoczności i wygody).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz, aby klienci zawsze byli świadomi dostępnego kredytu, zachęcając ich do jego wykorzystania.
-   **Wyświetl link do portfela w menu konta klienta:**

    -   **Co robi to ustawienie:** Dodaje bezpośredni link do strony „Mój portfel” w menu nawigacyjnym konta klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Link „Mój portfel” lub „Kredyt sklepowy” pojawia się w lewym menu panelu konta klienta.
        -   *Gdy wyłączone:* Klienci musieliby nawigować do strony portfela za pomocą innego linku (np. z nagłówka, jeśli włączone).
    -   **Zalecana wartość:** TAK (niezbędne dla łatwego dostępu).
    -   **Scenariusz / przykład sprzedawcy:** Chcesz, aby klienci łatwo znajdowali i zarządzali swoimi środkami w portfelu.
-   **Wyświetl link do portfela w stopce:**

    -   **Co robi to ustawienie:** Dodaje link do strony „Mój portfel” w sekcji stopki Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Link „Mój portfel” lub „Kredyt sklepowy” pojawia się w stopce, dostępny z każdej strony.
        -   *Gdy wyłączone:* Brak linku do portfela w stopce.
    -   **Zalecana wartość:** NIE (zazwyczaj zbędne, jeśli jest w nagłówku/menu konta, ale może być TAK dla maksymalnej widoczności).
    -   **Scenariusz / przykład sprzedawcy:** Jeśli menu konta klienta nie jest zbyt widoczne, lub chcesz szerzej podkreślić funkcję portfela, możesz to włączyć.
-   **Wyświetl link do portfela w lewej/prawej kolumnie:**

    -   **Co robi to ustawienie:** Dodaje link do strony „Mój portfel” w jednej z bocznych kolumn Twojego sklepu (jeśli Twój szablon je obsługuje).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Link „Mój portfel” lub „Kredyt sklepowy” pojawia się w wybranej kolumnie.
        -   *Gdy wyłączone:* Brak linku do portfela w kolumnach.
    -   **Zalecana wartość:** NIE (może zaśmiecać układ, zazwyczaj lepiej w nagłówku/koncie).
    -   **Scenariusz / przykład sprzedawcy:** Jeśli masz bardzo minimalistyczny nagłówek/stopkę i chcesz użyć kolumny do nawigacji, może to być opcja.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Ustawienia ogólne** | Włącz moduł | TAK | Aktywuje/dezaktywuje wszystkie funkcje portfela. |
| | Zezwól klientom na doładowywanie portfela | TAK | Klienci mogą kupować kredyt sklepowy. |
| | Minimalna kwota doładowania | 10.00 | Najniższa kwota, jaką klient może dodać. |
| | Maksymalna kwota doładowania | 500.00 | Najwyższa kwota, jaką klient może dodać. |
| | Zezwól klientom na kupowanie kodów podarunkowych | TAK | Klienci mogą kupować karty podarunkowe. |
| | Wygasanie kodu podarunkowego (dni) | 365 | Okres ważności kodów podarunkowych (0 dla braku wygaśnięcia). |
| | Wygasanie salda portfela (dni) | 0 | Okres ważności środków w portfelu (0 dla braku wygaśnięcia). |
| | Wyślij e-mail z przypomnieniem o wygaśnięciu (dni przed wygaśnięciem) | 7 | Dni przed wygaśnięciem, aby wysłać e-mail z przypomnieniem. |
| | Zezwól na częściowe płatności portfelem | TAK | Klienci mogą łączyć portfel z innymi metodami płatności. |
| | Opcja zwrotu do portfela | TAK | Opcja zwrotu zamówień bezpośrednio do portfela klienta. |
| | Włącz obsługę wielu walut | TAK (jeśli sklep wielowalutowy) | Zarządza oddzielnymi saldami dla każdej waluty. |
| **Bonusy za doładowanie** | Włącz bonusy za doładowanie | TAK | Aktywuje system bonusów za doładowania. |
| | Poziomy bonusów | (Niestandardowe) | Zdefiniuj procenty bonusów dla różnych kwot doładowania. |
| **Opcje wyświetlania** | Wyświetl saldo portfela w nagłówku | TAK | Pokazuje saldo w nagłówku sklepu dla zalogowanych użytkowników. |
| | Wyświetl link do portfela w menu konta klienta | TAK | Dodaje link „Mój portfel” do nawigacji konta klienta. |
| | Wyświetl link do portfela w stopce | NIE | Dodaje link „Mój portfel” do stopki sklepu. |
| | Wyświetl link do portfela w lewej/prawej kolumnie | NIE | Dodaje link „Mój portfel” do bocznych kolumn. |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł udostępnia dedykowane ekrany administracyjne do zarządzania portfelami klientów i kodami podarunkowymi.

#### 2.2.1 Zarządzanie portfelami (Panel Administracyjny > Moduły > Portfel Przedpłacony i Kredyt Sklepowy > Portfele)

-   **Nazwa ekranu i lokalizacja w menu:** **Portfele** (znajduje się w pozycji menu „Portfel Przedpłacony i Kredyt Sklepowy”, która pojawia się w „Modułach” lub „Płatności” w zależności od wersji PrestaShop i konfiguracji menu).
-   **Dostępne działania i ustawienia:** Ten ekran wyświetla listę wszystkich klientów, którzy posiadają portfel, wraz z ich aktualnym saldem, całkowitymi doładowaniami i innymi istotnymi informacjami.
    -   **Lista klientów:** Tabela z możliwością wyszukiwania i filtrowania, pokazująca imię i nazwisko klienta, adres e-mail, aktualne saldo portfela (dla każdej waluty, jeśli włączono obsługę wielu walut) oraz całkowitą kwotę doładowaną.
    -   **Wyświetl/Edytuj portfel:** Kliknij wiersz klienta lub ikonę „Edytuj”, aby wyświetlić szczegółową historię portfela i dokonać korekt.
        -   **Dodaj/Usuń środki:** Ręcznie dodaj lub odejmij środki z portfela klienta. Jest to przydatne do wydawania kredytu z tytułu dobrej woli, rekompensat lub korygowania błędów.
        -   **Wyświetl historię transakcji:** Zobacz szczegółowy dziennik wszystkich działań portfela dla tego klienta (doładowania, zakupy, zwroty, bonusy, wygaśnięcia).
        -   **Ustaw datę wygaśnięcia:** Ręcznie ustaw lub dostosuj datę wygaśnięcia dla konkretnych środków w portfelu klienta.
-   **Efekt zmian:**
    -   *Dodawanie/Usuwanie środków:* Bezpośrednio wpływa na dostępne saldo klienta w front office.
    -   *Edycja dat wygaśnięcia:* Wpływa na to, kiedy środki stają się bezużyteczne dla klienta.
    -   *Przeglądanie historii:* Zapewnia pełny ślad audytu dla obsługi klienta i księgowości.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Zapytanie klienta:** Jeśli klient pyta o swoje saldo lub konkretną transakcję, użyj tego ekranu, aby szybko sprawdzić jego portfel i historię.
    2.  **Wydawanie kredytu:** Jeśli musisz przyznać klientowi kredyt sklepowy (np. za reklamację, nagrodę lojalnościową), przejdź do jego portfela i użyj opcji „Dodaj środki”.
    3.  **Zwroty do portfela:** Podczas przetwarzania zwrotu za zamówienie możesz wybrać wysłanie pieniędzy do portfela klienta ze strony szczegółów zamówienia. To działanie zostanie tutaj odzwierciedlone.

#### 2.2.2 Zarządzanie kodami podarunkowymi (Panel Administracyjny > Moduły > Portfel Przedpłacony i Kredyt Sklepowy > Kody)

-   **Nazwa ekranu i lokalizacja w menu:** **Kody** (znajduje się w pozycji menu „Portfel Przedpłacony i Kredyt Sklepowy”).
-   **Dostępne działania i ustawienia:** Ten ekran umożliwia generowanie, zarządzanie i śledzenie wszystkich kodów podarunkowych w Twoim systemie.
    -   **Lista kodów:** Tabela pokazująca wszystkie wygenerowane kody podarunkowe, ich wartość, aktualny status (aktywny, wykorzystany, wygasły), kto go kupił (jeśli dotyczy), kto go wykorzystał i datę wygaśnięcia.
    -   **Generuj nowy kod:** Twórz nowe kody podarunkowe z określoną wartością, walutą i opcjonalną datą wygaśnięcia. Mogą być używane do promocji, rozdawania lub ręcznych kredytów obsługi klienta.
    -   **Edytuj kod:** Modyfikuj wartość, status lub datę wygaśnięcia istniejącego kodu (jeśli jeszcze nie został wykorzystany).
    -   **Usuń kod:** Usuń kod (tylko jeśli nie został wykorzystany).
    -   **Szukaj/Filtruj:** Łatwo znajduj konkretne kody według wartości, statusu lub klienta.
-   **Efekt zmian:**
    -   *Generowanie kodu:* Tworzy nowy, użyteczny kod podarunkowy, który można przekazać klientowi.
    -   *Edycja kodu:* Zmienia jego właściwości, wpływając na jego możliwość wykorzystania i wartość.
    -   *Usuwanie kodu:* Zapobiega jego wykorzystaniu.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Kampanie promocyjne:** Wygeneruj partię kodów podarunkowych dla kampanii marketingowej (np. „10 EUR zniżki dla nowych subskrybentów e-mail”).
    2.  **Obsługa klienta:** Jeśli klient ma problem, możesz szybko wygenerować unikalny kod podarunkowy, aby go zrekompensować.
    3.  **Śledzenie wykorzystania:** Monitoruj, które kody zostały wykorzystane i przez kogo, pomagając analizować skuteczność kampanii.

#### 2.2.3 Dziennik audytu (Panel Administracyjny > Moduły > Portfel Przedpłacony i Kredyt Sklepowy > Audyt)

-   **Nazwa ekranu i lokalizacja w menu:** **Audyt** (znajduje się w pozycji menu „Portfel Przedpłacony i Kredyt Sklepowy”).
-   **Dostępne działania i ustawienia:** Ten ekran zapewnia kompleksowy dziennik wszystkich działań związanych z portfelem w Twoim sklepie.
    -   **Lista aktywności:** Szczegółowa tabela pokazująca każdą transakcję, doładowanie, wykorzystanie, korektę administratora i zdarzenie wygaśnięcia.
    -   **Szczegóły:** Każdy wpis zawiera datę, zaangażowanego klienta, typ aktywności, kwotę i wszelkie istotne uwagi (np. ID zamówienia, administrator, który dokonał zmiany).
    -   **Szukaj/Filtruj:** Filtruj dziennik audytu według klienta, zakresu dat lub typu aktywności, aby szybko znaleźć konkretne zdarzenia.
-   **Efekt zmian:** Jest to dziennik tylko do odczytu; nie można tutaj wprowadzać żadnych zmian. Służy jako kluczowy zapis dla odpowiedzialności i rozwiązywania problemów.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Rozwiązywanie problemów:** Jeśli klient zgłasza nieprawidłowe saldo, użyj dziennika audytu, aby prześledzić wszystkie transakcje i zidentyfikować wszelkie rozbieżności.
    2.  **Zgodność:** Utrzymuj jasny zapis wszystkich ruchów finansowych związanych z systemem portfela dla celów księgowych i prawnych.
    3.  **Przegląd wydajności:** Analizuj ogólną aktywność portfela, aby zrozumieć zaangażowanie klientów i wykorzystanie modułu.

## 3. Rozwiązywanie problemów przez sprzedawcę i często zadawane pytania (FAQ)

**P1: Moi klienci nie widzą opcji portfela w front office.**
O1:

-   **Sprawdź włączenie modułu:** Przejdź do **Moduły > Menedżer modułów**, znajdź „Portfel Przedpłacony i Kredyt Sklepowy” i upewnij się, że moduł jest włączony.
-   **Sprawdź ustawienia ogólne:** Na stronie konfiguracji modułu upewnij się, że „Włącz moduł” jest ustawione na TAK. Sprawdź również, czy włączone są konkretne opcje wyświetlania, takie jak „Wyświetl link do portfela w menu konta klienta”.
-   **Logowanie klienta:** Funkcje portfela są zazwyczaj widoczne tylko dla zalogowanych klientów. Poproś klienta o zalogowanie się.
-   **Kompatybilność z szablonem:** Chociaż moduł jest zaprojektowany pod kątem kompatybilności, niektóre wysoce spersonalizowane szablony mogą wymagać drobnych korekt. Jeśli podejrzewasz konflikt z szablonem, spróbuj tymczasowo przełączyć się na domyślny szablon PrestaShop, aby sprawdzić, czy problem zostanie rozwiązany.

**P2: Saldo portfela klienta wydaje się nieprawidłowe.**
O2:

-   **Sprawdź dziennik audytu:** Przejdź do **Moduły > Portfel Przedpłacony i Kredyt Sklepowy > Audyt**. Wyszukaj imię i nazwisko klienta i przejrzyj całą historię transakcji. Pokaże to wszystkie doładowania, zakupy, zwroty, bonusy i korekty administratora.
-   **Sprawdź szczegóły portfela:** Przejdź do **Moduły > Portfel Przedpłacony i Kredyt Sklepowy > Portfele**, znajdź klienta i kliknij, aby wyświetlić szczegółowy portfel. Porównaj saldo z dziennikiem audytu.
-   **Problem z walutą:** Jeśli „Włącz obsługę wielu walut” jest aktywne, upewnij się, że patrzysz na saldo w prawidłowej walucie. Klient może mieć salda w wielu walutach.
-   **Wygasanie:** Sprawdź, czy jakieś środki wygasły. Dziennik audytu pokaże zdarzenia wygaśnięcia.

**P3: Moi klienci nie otrzymują e-maili z przypomnieniem o wygaśnięciu.**
O3:

-   **Sprawdź ustawienia wygaśnięcia:** Upewnij się, że „Wygasanie salda portfela (dni)” jest ustawione na wartość większą niż 0, a „Wyślij e-mail z przypomnieniem o wygaśnięciu (dni przed wygaśnięciem)” jest również ustawione na wartość większą niż 0.
-   **Zadanie Cron:** Moduł prawdopodobnie używa zadania cron do wyzwalania tych e-maili. Upewnij się, że Twoje zadanie cron PrestaShop jest poprawnie skonfigurowane i regularnie uruchamiane. (Patrz sekcja 7.2 dla `cron.php`).
-   **Konfiguracja e-mail:** Sprawdź, czy Twoje ustawienia e-mail PrestaShop (**Zaawansowane > E-mail**) są poprawnie skonfigurowane i wysyłają e-maile pomyślnie. Przetestuj wysyłanie ogólnego e-maila z PrestaShop.
-   **Foldery spamu:** Doradź klientom, aby sprawdzili swoje foldery spamu lub niechcianej poczty.

**P4: Jak wyczyścić pamięć podręczną Smarty, jeśli widzę starą zawartość lub problemy z wyświetlaniem?**
O4:

-   Przejdź do **Zaawansowane > Wydajność** w Panelu Administracyjnym PrestaShop.
-   W sekcji „Smarty” ustaw „Kompilacja szablonów” na „Skompiluj ponownie szablony, jeśli pliki zostały zaktualizowane” (lub tymczasowo „Wymuś kompilację”).
-   Kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
-   Po wyczyszczeniu możesz przywrócić „Kompilację szablonów” z powrotem na „Nigdy nie kompiluj ponownie plików szablonów” dla lepszej wydajności.

**P5: Moduł nie wygląda prawidłowo na moim niestandardowym szablonie.**
O5:

-   **Nadpisywanie CSS:** CSS Twojego niestandardowego szablonu może nadpisywać domyślne style modułu.
-   **Inspekcja elementu:** Użyj narzędzi deweloperskich przeglądarki (kliknij prawym przyciskiem myszy, „Inspekcja”), aby zidentyfikować reguły CSS wpływające na elementy modułu. Następnie możesz dodać niestandardowy CSS do arkusza stylów Twojego szablonu, aby je nadpisać.
-   **Skontaktuj się z deweloperem:** Jeśli nie czujesz się komfortowo z CSS, skontaktuj się z deweloperem swojego szablonu lub wsparciem MyPresta.eu w celu uzyskania pomocy. Dostarcz zrzuty ekranu i nazwę swojego szablonu.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd struktury technicznej modułu „Portfel Przedpłacony i Kredyt Sklepowy”, przeznaczony dla deweloperów i webmasterów.

### 4.1 Przegląd architektury

Moduł „Portfel Przedpłacony i Kredyt Sklepowy” jest zgodny ze standardowym wzorcem PrestaShop MVC (Model-View-Controller). Rozszerza podstawowe funkcjonalności PrestaShop poprzez hooki, niestandardowe kontrolery i dedykowane klasy.

-   **Kontrolery:** Obsługuje interakcje front-office (doładowania, wykorzystanie kodów, przetwarzanie płatności) oraz administrację back-office (zarządzanie portfelami/kodami).
-   **Modele:** Niestandardowe klasy `ObjectModel` (`PrepaidWalletService`, `PrepaidCodeService` itp.) zarządzają trwałością danych dla portfeli, kodów i transakcji, współpracując z dedykowanymi tabelami bazy danych.
-   **Widoki:** Pliki Smarty `.tpl` renderują zarówno interfejsy klienta front-office (strona portfela, formularze doładowania), jak i siatki/formularze administracyjne back-office.
-   **Usługi:** Kilka klas pomocniczych hermetyzuje specyficzną logikę biznesową (np. `PrepaidCartCreditService` do integracji z koszykiem, `PrepaidExpiry` do zarządzania wygaśnięciem środków).
-   **Hooki:** Moduł intensywnie wykorzystuje hooki PrestaShop do wstrzykiwania swojej funkcjonalności w różne części sklepu (nagłówek, konto klienta, proces płatności, szczegóły zamówienia).

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `prepaidpayment/controllers/front/applycode.php`
    -   **Nazwa klasy i klasa nadrzędna:** `PrepaidPaymentApplyCodeModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Obsługuje żądanie AJAX dotyczące zastosowania kodu podarunkowego podczas procesu realizacji zamówienia lub na dedykowanej stronie realizacji. Waliduje kod i aktualizuje kredyt w koszyku.
-   `prepaidpayment/controllers/front/buycode.php`
    -   **Nazwa klasy i klasa nadrzędna:** `PrepaidPaymentBuyCodeModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Zarządza procesem zakupu kodów podarunkowych przez klientów. Obsługuje wyświetlanie formularza zakupu kodu podarunkowego i tworzenie produktu kodu podarunkowego w koszyku.
-   `prepaidpayment/controllers/front/cron.php`
    -   **Nazwa klasy i klasa nadrzędna:** `PrepaidPaymentCronModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler jest przeznaczony do wywoływania przez zadanie cron. Wykonuje zadania w tle, takie jak sprawdzanie wygasłych środków w portfelu, wysyłanie e-maili z przypomnieniem o wygaśnięciu i potencjalnie inne zaplanowane czynności konserwacyjne.
-   `prepaidpayment/controllers/front/entercode.php`
    -   **Nazwa klasy i klasa nadrzędna:** `PrepaidPaymentEnterCodeModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Wyświetla dedykowaną stronę, na której klienci mogą wprowadzić kod podarunkowy, aby go zrealizować i dodać środki do swojego portfela.
-   `prepaidpayment/controllers/front/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `PrepaidPaymentIndexModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Prawdopodobnie służy jako domyślny lub awaryjny kontroler frontowy, lub podstawa dla innych kontrolerów frontowych. W wielu modułach może to przekierowywać lub wyświetlać ogólną stronę modułu.
-   `prepaidpayment/controllers/front/payment.php`
    -   **Nazwa klasy i klasa nadrzędna:** `PrepaidPaymentPaymentModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Obsługuje proces płatności, gdy klient wybiera płatność portfelem. Waliduje saldo portfela względem całkowitej kwoty zamówienia i przetwarza płatność.
-   `prepaidpayment/controllers/front/redeempay.php`
    -   **Nazwa klasy i klasa nadrzędna:** `PrepaidPaymentRedeemPayModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler prawdopodobnie zarządza realizacją kodu podarunkowego i jego zastosowaniem do bieżącego koszyka, potencjalnie łącząc logikę `applycode.php` i `payment.php` w określonym przepływie.
-   `prepaidpayment/controllers/front/topup.php`
    -   **Nazwa klasy i klasa nadrzędna:** `PrepaidPaymentTopupModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Zarządza procesem doładowania portfela klienta. Wyświetla formularz doładowania, obsługuje wybór kwot doładowania (i związanych z nimi bonusów) oraz dodaje produkt doładowania do koszyka.

#### Kontrolery administracyjne Back-Office

-   `prepaidpayment/controllers/admin/index.php`
    -   **Nazwa zakładki i zarządzana encja:** Ten kontroler służy jako główny punkt wejścia do interfejsu administracyjnego modułu. Prawdopodobnie rozsyła do różnych widoków (Portfele, Kody, Audyt) i zarządza ogólną konfiguracją i danymi dla modułu. Nie zarządza bezpośrednio pojedynczym `ObjectModel`, ale orkiestruje zarządzanie danymi `PrepaidWalletService` i `PrepaidCodeService`.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `prepaidpayment/classes/index.php`
    -   **Cel:** Zazwyczaj pusty plik lub zawiera podstawową instrukcję `die()` w celu zapobiegania bezpośredniemu listowaniu katalogów, co jest powszechną praktyką bezpieczeństwa.
-   `prepaidpayment/classes/PrepaidAdmin.php`
    -   **Cel:** Prawdopodobnie klasa pomocnicza do zadań administracyjnych, potencjalnie zawierająca metody do renderowania formularzy administracyjnych, obsługi żądań AJAX w back office lub specyficznych manipulacji danymi dla widoków administracyjnych.
-   `prepaidpayment/classes/PrepaidCartCreditService.php`
    -   **Cel:** Hermetyzuje logikę stosowania kredytu portfela lub kodów podarunkowych do koszyka klienta podczas realizacji zamówienia. Obsługuje obliczenia, walidacje i aktualizacje całkowitej kwoty koszyka.
-   `prepaidpayment/classes/PrepaidCodeService.php`
    -   **Cel:** Zarządza cyklem życia kodów podarunkowych.
    -   **Interakcja z `ObjectModel`:** Prawdopodobnie rozszerza `ObjectModel` i współpracuje z niestandardową tabelą bazy danych (np. `ps_prepaid_codes`).
    -   **Pola `$definition`:** Zawierałoby pola takie jak `id_prepaid_code`, `code`, `value`, `id_currency`, `id_customer_buyer`, `id_customer_redeemer`, `date_add`, `date_redeem`, `date_expiry`, `active`.
    -   **Kluczowe metody publiczne:** `generateCode()`, `redeemCode()`, `getCodeByCode()`, `isCodeValid()`, `getCodesForCustomer()`.
-   `prepaidpayment/classes/PrepaidCurrency.php`
    -   **Cel:** Klasa pomocnicza do obsługi aspektów wielowalutowych portfela, zapewniająca prawidłowe przeliczanie walut i wyświetlanie. Może rozszerzać `Currency` lub dostarczać metody narzędziowe do operacji uwzględniających waluty.
-   `prepaidpayment/classes/PrepaidExpiry.php`
    -   **Cel:** Zarządza logiką wygasania zarówno kodów podarunkowych, jak i sald portfela. Zawiera metody do obliczania dat wygaśnięcia, sprawdzania wygasłych środków i potencjalnie wyzwalania działań wygasania (np. ustawiania środków na nieaktywne).
-   `prepaidpayment/classes/PrepaidThemeCompat.php`
    -   **Cel:** Zapewnia warstwy kompatybilności lub specyficzne dostosowania dla różnych szablonów PrestaShop (np. Classic, Hummingbird) lub wersji, zapewniając prawidłowe wyświetlanie elementów front-office modułu w różnych środowiskach.
-   `prepaidpayment/classes/PrepaidTopupCart.php`
    -   **Cel:** Zarządza specyficzną logiką koszyka, gdy klient doładowuje swój portfel. Może tworzyć wirtualny produkt w koszyku reprezentujący kwotę doładowania i obsługiwać związane z tym bonusy.
-   `prepaidpayment/classes/PrepaidWalletService.php`
    -   **Cel:** Główna klasa do zarządzania portfelami klientów.
    -   **Interakcja z `ObjectModel`:** Prawdopodobnie rozszerza `ObjectModel` i współpracuje z niestandardową tabelą bazy danych (np. `ps_prepaid_wallets` dla sald i `ps_prepaid_wallet_history` dla transakcji).
    -   **Pola `$definition`:** Dla `ps_prepaid_wallets`: `id_prepaid_wallet`, `id_customer`, `id_currency`, `balance`, `date_update`. Dla `ps_prepaid_wallet_history`: `id_prepaid_wallet_history`, `id_customer`, `id_currency`, `amount`, `type` (topup, purchase, refund, bonus, expiry), `id_order`, `date_add`, `notes`.
    -   **Kluczowe metody publiczne:** `getBalance()`, `addFunds()`, `deductFunds()`, `getHistory()`, `getWalletsForCustomer()`, `processRefundToWallet()`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `prepaidpayment/lib/searchTool/views/js/autocomplete.js`
    -   **Zakres:** Prawdopodobnie Back-office.
    -   **Szczegóły:** Zapewnia funkcjonalność autouzupełniania, prawdopodobnie do wyszukiwania klientów lub produktów w interfejsie administracyjnym, na przykład podczas przypisywania kodu podarunkowego do konkretnego klienta lub zarządzania portfelem.
-   `prepaidpayment/views/js/adminPrepaid.js`
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Ogólny JavaScript dla stron administracyjnych modułu. Może obsługiwać przesyłanie formularzy, aktualizacje AJAX dla list (portfele, kody), ogólne ulepszenia interfejsu użytkownika i interakcje na głównej stronie konfiguracji.
-   `prepaidpayment/views/js/adminPrepaidBonusBuilder.js`
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Specjalnie obsługuje dynamiczne tworzenie i zarządzanie poziomami bonusów na stronie konfiguracji modułu. Prawdopodobnie dodaje/usuwa pola wejściowe dla procentów bonusów i minimalnych kwot oraz waliduje te dane wejściowe.
-   `prepaidpayment/views/js/adminPrepaidDashboard.js`
    -   **Zakres:** Back-office.
    -   **Szczegóły:** JavaScript dla panelu administracyjnego lub ekranu przeglądu, potencjalnie obsługujący wizualizację danych, szybkie statystyki lub interaktywne elementy związane z ogólnym wykorzystaniem portfela.
-   `prepaidpayment/views/js/adminPrepaidSelector.js`
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Zarządza komponentami wyboru w panelu administracyjnym, prawdopodobnie do wyboru klientów, walut lub konkretnych kodów w różnych formularzach lub listach.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `prepaidpayment/lib/searchTool/views/css/autocomplete.css`
    -   **Zakres:** Stylizacja administracyjna Back-office.
    -   **Szczegóły:** Style dla narzędzia wyszukiwania autouzupełniania używanego w back office, zapewniające wizualną spójność rozwijanych list i sugestii.
-   `prepaidpayment/views/css/admin_prepaidpayment.css`
    -   **Zakres:** Stylizacja administracyjna Back-office.
    -   **Szczegóły:** Podstawowy CSS dla stron administracyjnych modułu, stylizujący formularze, tabele, przyciski i ogólny układ w panelu administracyjnym PrestaShop.
-   `prepaidpayment/views/css/front-hummingbird.css`
    -   **Zakres:** Stylizacja klienta Front-office (specjalnie dla szablonu Hummingbird).
    -   **Szczegóły:** Zapewnia specyficzne dostosowania stylów lub nadpisywania, aby zapewnić optymalną integrację wizualną z szablonem PrestaShop Hummingbird.
-   `prepaidpayment/views/css/front.css`
    -   **Zakres:** Stylizacja klienta Front-office (ogólna).
    -   **Szczegóły:** Ogólny CSS dla komponentów front-office modułu, takich jak strona „Mój portfel”, formularze doładowania, formularze realizacji kodów podarunkowych i wyświetlanie portfela w nagłówku/koszyku.
-   `prepaidpayment/views/css/prepaidpayment.css`
    -   **Zakres:** Zarówno Front-office, jak i Back-office (lub ogólne style dla całego modułu).
    -   **Szczegóły:** Zawiera wspólne style używane zarówno w front, jak i back office, lub podstawowe style dla unikalnych elementów modułu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `prepaidpayment/views/templates/hook/adminOrder.tpl`
    -   **Hook:** `displayAdminOrder` lub podobny.
    -   **Wyjście:** Wyświetla informacje lub działania związane z portfelem na stronie szczegółów zamówienia PrestaShop w panelu administracyjnym (np. opcja zwrotu do portfela, szczegóły płatności portfelem).
-   `prepaidpayment/views/templates/hook/customerAccount-hummingbird.tpl`
    -   **Hook:** `displayCustomerAccount` (specjalnie dla szablonu Hummingbird).
    -   **Wyjście:** Dodaje link lub blok „Mój portfel” do panelu konta klienta, stylizowany dla szablonu Hummingbird.
-   `prepaidpayment/views/templates/hook/customerAccount.tpl`
    -   **Hook:** `displayCustomerAccount`.
    -   **Wyjście:** Dodaje link lub blok „Mój portfel” do panelu konta klienta, dla ogólnych szablonów.
-   `prepaidpayment/views/templates/hook/orderDetail.tpl`
    -   **Hook:** `displayOrderDetail` lub podobny.
    -   **Wyjście:** Wyświetla szczegóły płatności portfelem na stronie szczegółów zamówienia klienta w front office.
-   `prepaidpayment/views/templates/hook/payment.tpl`
    -   **Hook:** `displayPayment` (PrestaShop 1.6) lub `paymentOptions` (PrestaShop 1.7+).
    -   **Wyjście:** Renderuje opcję „Zapłać portfelem” na stronie wyboru płatności w koszyku.
-   `prepaidpayment/views/templates/hook/paymentReturn.tpl`
    -   **Hook:** `displayPaymentReturn`.
    -   **Wyjście:** Wyświetla informacje o płatnościach portfelem na stronie potwierdzenia zamówienia po realizacji zamówienia.
-   `prepaidpayment/views/templates/hook/paymentTop.tpl`
    -   **Hook:** `displayPaymentTop`.
    -   **Wyjście:** Może wyświetlać podsumowanie salda portfela lub opcję wprowadzenia kodu podarunkowego na górze strony płatności.
-   `prepaidpayment/views/templates/hook/walletNav.tpl`
    -   **Hook:** `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`.
    -   **Wyjście:** Renderuje saldo portfela lub link do strony portfela w różnych obszarach nawigacyjnych sklepu.

#### Szablony administracyjne (`views/templates/admin/`)

-   `prepaidpayment/views/templates/admin/audit.tpl`
    -   **Wyjście:** Renderuje tabelę dziennika audytu i opcje filtrowania w panelu administracyjnym.
-   `prepaidpayment/views/templates/admin/codes.tpl`
    -   **Wyjście:** Renderuje listę kodów podarunkowych, formularz do generowania nowych kodów i edycji istniejących w panelu administracyjnym.
-   `prepaidpayment/views/templates/admin/dashboard.tpl`
    -   **Wyjście:** Renderuje główny panel lub stronę przeglądu modułu w panelu administracyjnym, potencjalnie pokazując statystyki lub szybkie linki.
-   `prepaidpayment/views/templates/admin/scopeSelector.tpl`
    -   **Wyjście:** Szablon wielokrotnego użytku do wyboru konkretnych zakresów, takich jak waluty lub grupy klientów, w formularzach administracyjnych.
-   `prepaidpayment/views/templates/admin/wallets.tpl`
    -   **Wyjście:** Renderuje listę portfeli klientów, szczegółowy widok portfela i opcje dodawania/usuwania środków w panelu administracyjnym.

#### Szablony front-office (`views/templates/front/`)

-   `prepaidpayment/views/templates/front/buycode.tpl`
    -   **Wyjście:** Renderuje formularz i interfejs dla klientów do zakupu kodów podarunkowych.
-   `prepaidpayment/views/templates/front/entercode.tpl`
    -   **Wyjście:** Renderuje dedykowaną stronę, na której klienci mogą wprowadzić kod podarunkowy, aby go zrealizować.
-   `prepaidpayment/views/templates/front/topup.tpl`
    -   **Wyjście:** Renderuje formularz i opcje dla klientów do doładowania swojego portfela, w tym informacje o bonusach.

#### Szablony bibliotek (`prepaidpayment/lib/searchTool/views/scripts.tpl`)

-   `prepaidpayment/lib/searchTool/views/scripts.tpl`
    -   **Wyjście:** Zawiera logikę JavaScript lub Smarty dla narzędzia wyszukiwania, prawdopodobnie włączoną do szablonów administracyjnych, gdzie potrzebne jest autouzupełnianie.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

-   `ps_prepaid_wallets`: Przechowuje aktualne saldo dla każdego klienta i waluty.
    -   `id_prepaid_wallet` (PK)
    -   `id_customer` (FK do `ps_customer`)
    -   `id_currency` (FK do `ps_currency`)
    -   `balance` (decimal)
    -   `date_upd` (datetime)
-   `ps_prepaid_wallet_history`: Loguje wszystkie transakcje i zmiany w portfelach klientów.
    -   `id_prepaid_wallet_history` (PK)
    -   `id_customer` (FK do `ps_customer`)
    -   `id_currency` (FK do `ps_currency`)
    -   `amount` (decimal, dodatnie dla kredytu, ujemne dla debetu)
    -   `type` (varchar, np. ‘topup’, ‘purchase’, ‘refund’, ‘bonus’, ‘expiry’, ‘admin_add’, ‘admin_deduct’)
    -   `id_order` (FK do `ps_order`, może być null)
    -   `id_prepaid_code` (FK do `ps_prepaid_codes`, może być null)
    -   `notes` (text, np. „Korekta administratora”, „Realizacja kodu podarunkowego”)
    -   `date_add` (datetime)
    -   `date_expiry` (datetime, może być null)
-   `ps_prepaid_codes`: Przechowuje informacje o wygenerowanych i zakupionych kodach podarunkowych.
    -   `id_prepaid_code` (PK)
    -   `code` (varchar, unikalny, rzeczywisty ciąg kodu podarunkowego)
    -   `value` (decimal, początkowa wartość kodu)
    -   `id_currency` (FK do `ps_currency`)
    -   `id_customer_buyer` (FK do `ps_customer`, może być null, jeśli kupiony przez klienta)
    -   `id_customer_redeemer` (FK do `ps_customer`, może być null, po wykorzystaniu)
    -   `date_add` (datetime)
    -   `date_redeem` (datetime, może być null)
    -   `date_expiry` (datetime, może być null)
    -   `active` (tinyint, 0 lub 1)
-   `ps_prepaid_bonus_tiers`: Przechowuje skonfigurowane zasady bonusów za doładowanie.
    -   `id_prepaid_bonus_tier` (PK)
    -   `min_amount` (decimal)
    -   `bonus_percentage` (decimal)
    -   `position` (int)
-   `ps_configuration`: Ustawienia modułu są przechowywane tutaj z kluczami takimi jak `PREPAIDPAYMENT_ENABLED`, `PREPAIDPAYMENT_MIN_TOPUP` itp.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykiwanie CSS/JS, wyświetlanie salda portfela dla zalogowanych użytkowników. |
| `displayLeftColumn` | W lewej kolumnie sklepu. | Wyświetlanie linku do portfela. |
| `displayRightColumn` | W prawej kolumnie sklepu. | Wyświetlanie linku do portfela. |
| `displayFooter` | W sekcji stopki każdej strony. | Wyświetlanie linku do portfela. |
| `displayCustomerAccount` | Na stronie „Moje konto” klienta. | Dodanie linku/bloku „Mój portfel”. |
| `displayPayment` (PS 1.6) / `paymentOptions` (PS 1.7+) | Na stronie wyboru płatności w koszyku. | Wyświetlanie opcji płatności „Zapłać portfelem”. |
| `displayPaymentReturn` | Na stronie potwierdzenia zamówienia po realizacji zamówienia. | Pokazywanie szczegółów płatności portfelem. |
| `displayPaymentTop` | Na górze strony płatności. | Potencjalnie wyświetlanie salda portfela lub pola do wprowadzenia kodu podarunkowego. |
| `displayAdminOrder` | Na stronie szczegółów zamówienia w panelu administracyjnym. | Dodanie opcji zwrotu do portfela, wyświetlanie informacji o płatności portfelem. |
| `displayOrderDetail` | Na stronie szczegółów zamówienia klienta w front office. | Pokazywanie szczegółów płatności portfelem. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Odjęcie środków z portfela, zapisanie transakcji. |
| `actionOrderStatusPostUpdate` | Po zaktualizowaniu statusu zamówienia. | Potencjalne wyzwalanie zwrotów do portfela na podstawie zmiany statusu. |
| `actionFrontControllerSetMedia` | Przed renderowaniem zawartości przez kontroler frontowy. | Dodanie specyficznych dla modułu CSS i JS do stron front-office. |
| `actionAdminControllerSetMedia` | Przed renderowaniem zawartości przez kontroler administracyjny. | Dodanie specyficznych dla modułu CSS i JS do stron back-office. |
| `actionCronJob` (niestandardowy hook) | Wyzwalany przez kontroler cron modułu. | Wykonywanie zaplanowanych zadań, takich jak sprawdzanie wygaśnięcia i przypomnienia e-mail. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkiej dalszej pomocy z modułem „Portfel Przedpłacony i Kredyt Sklepowy”, prosimy o zapoznanie się z kontem klienta na MyPresta.eu. Nasz zespół jest zaangażowany w zapewnienie kompleksowego wsparcia i sprawne działanie modułu.

-   **MyPresta.eu Historia Zamówień i Pliki do Pobrania:** <https://mypresta.eu/my-account/orders/>
-   **MyPresta.eu Kontakt z Działem Wsparcia:** <https://mypresta.eu/contact>
