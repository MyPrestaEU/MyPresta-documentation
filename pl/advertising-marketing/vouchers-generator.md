---
title: "Generator Bonów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Generator Bonów od MyPresta.eu."
sidebar:
  label: "Generator Bonów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Vouchers Generator na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/vouchers-generator.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/vouchers-generator/)
>
> ---


# Generator Bonów

## 1. Wymagania i Kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne nietypowe konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po zainstalowaniu modułu przejdź do **Moduły > Menedżer modułów** i kliknij „Konfiguruj” obok „Generator Bonów”. Jest to główny ekran, na którym będziesz zarządzać wszystkimi ustawieniami i generować swoje bony.

Strona konfiguracji jest zaprojektowana tak, aby była intuicyjna, umożliwiając zdefiniowanie zasad dla nowych bonów, a następnie ich wygenerowanie.

#### **1. Ustawienia generowania bonów**

Ta sekcja pozwala zdefiniować podstawowe właściwości bonów, które chcesz wygenerować.

- **Nazwa:**

  - **Co robi to ustawienie:** Jest to nazwa, która pojawi się w Twoim Panelu administracyjnym PrestaShop w sekcji „Katalog > Rabaty > Reguły koszyka” dla wygenerowanej partii bonów. Jest to również nazwa bazowa dla poszczególnych kodów bonów (np. jeśli ustawisz „LATO2024”, kody mogą być „LATO2024-ABCDE”, „LATO2024-FGHIJ”).
  - **Efekt zmiany tego ustawienia:** Jasna i opisowa nazwa pomaga później zidentyfikować cel partii bonów.
  - **Zalecana wartość:** Coś opisowego, np. „Wyprzedaż Letnia 2024”, „Powitanie Nowego Klienta” lub „Odzyskiwanie Porzuconego Koszyka”.
  - **Scenariusz / przykład dla sprzedawcy:** Prowadzisz letnią promocję. Możesz nazwać ją „LATO2024”.
- **Opis:**

  - **Co robi to ustawienie:** Wewnętrzna notatka dla Twojej referencji, widoczna tylko w Panelu administracyjnym. Pomaga zapamiętać szczegóły lub cele tej kampanii bonów.
  - **Efekt zmiany tego ustawienia:** Dostarcza kontekstu dla Ciebie i Twojego zespołu.
  - **Zalecana wartość:** Krótkie wyjaśnienie, np. „20% zniżki na wszystkie zamówienia powyżej 50 USD, ważne przez 1 miesiąc, dystrybuowane za pośrednictwem newslettera e-mail”.
  - **Scenariusz / przykład dla sprzedawcy:** Dla kampanii „LATO2024” możesz dodać „20% zniżki na wszystkie produkty, minimalny zakup 50 USD, ważne do 31 sierpnia”.
- **Podświetl:**

  - **Co robi to ustawienie:** Jeśli włączone, ten bon będzie wyświetlany w podsumowaniu koszyka dla wszystkich klientów, nawet jeśli go nie wprowadzili. Jest to zazwyczaj używane do ogólnych, publicznych promocji.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Bon pojawia się automatycznie w podsumowaniu koszyka, zachęcając klientów do jego użycia.
    - *Gdy wyłączone:* Bon jest stosowany tylko wtedy, gdy klient wyraźnie wprowadzi kod.
  - **Zalecana wartość:** „NIE” dla unikalnych, ukierunkowanych bonów; „TAK” dla promocji ogólnosklepowych, publicznych.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli dajesz unikalne kody konkretnym klientom, wyłącz to. Jeśli jest to ogólna promocja „10% zniżki na wszystko”, włącz to.
- **Częściowe użycie:**

  - **Co robi to ustawienie:** Określa, czy bon może być użyty wielokrotnie, jeśli jego wartość przekracza całkowitą kwotę zamówienia.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Jeśli klient ma bon o wartości 50 USD i kupuje przedmiot za 30 USD, pozostanie mu 20 USD salda na tym samym bonie do wykorzystania w przyszłym zakupie.
    - *Gdy wyłączone:* Jeśli klient ma bon o wartości 50 USD i kupuje przedmiot za 30 USD, cały bon o wartości 50 USD zostaje zużyty i nie pozostaje żadne saldo.
  - **Zalecana wartość:** „NIE” dla większości promocji, aby zachęcić do pełnego wykorzystania lub zapobiec skomplikowanemu śledzeniu. „TAK” dla kart podarunkowych lub kredytu sklepowego.
  - **Scenariusz / przykład dla sprzedawcy:** Dla standardowej zniżki zazwyczaj wyłączyłbyś to. Dla bonu podarunkowego włączyłbyś to.
- **Priorytet:**

  - **Co robi to ustawienie:** Ustawia kolejność, w jakiej reguły koszyka są stosowane, jeśli aktywnych jest wiele reguł. Niższa liczba oznacza wyższy priorytet (stosowane jako pierwsze).
  - **Efekt zmiany tego ustawienia:** Wpływa na to, jak rabaty się sumują. Jeśli zastosowanie mają dwa bony, ten z wyższym priorytetem jest przetwarzany jako pierwszy.
  - **Zalecana wartość:** Pozostaw domyślną (1), chyba że masz złożone reguły sumowania.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli masz bon „Darmowa wysyłka” (priorytet 1) i bon „10% zniżki” (priorytet 2), darmowa wysyłka zostanie obliczona przed rabatem procentowym.
- **Status:**

  - **Co robi to ustawienie:** Aktywuje lub dezaktywuje wygenerowane bony.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Bony są aktywne i mogą być używane przez klientów.
    - *Gdy wyłączone:* Bony są nieaktywne i nie mogą być używane.
  - **Zalecana wartość:** „TAK”, jeśli chcesz, aby bony były natychmiast używalne. Możesz je później wyłączyć, jeśli zajdzie taka potrzeba.
  - **Scenariusz / przykład dla sprzedawcy:** Generujesz bony na przyszłą wyprzedaż. Możesz je włączyć w dniu rozpoczęcia wyprzedaży.

#### **2. Warunki bonu**

Ta sekcja definiuje, kiedy i jak wygenerowane bony mogą być używane.

- **Ważny od:**

  - **Co robi to ustawienie:** Ustawia datę początkową, od której bony stają się aktywne.
  - **Efekt zmiany tego ustawienia:** Bony nie mogą być używane przed tą datą.
  - **Zalecana wartość:** Dzisiejsza data, jeśli chcesz, aby były aktywne natychmiast, lub przyszła data dla zaplanowanej promocji.
  - **Scenariusz / przykład dla sprzedawcy:** Ustaw na „2024-07-01” dla promocji lipcowej.
- **Ważny do:**

  - **Co robi to ustawienie:** Ustawia datę końcową, po której bony wygasają.
  - **Efekt zmiany tego ustawienia:** Bony nie mogą być używane po tej dacie.
  - **Zalecana wartość:** Rozsądna data ważności dla Twojej promocji (np. 1 tydzień, 1 miesiąc, koniec sezonu).
  - **Scenariusz / przykład dla sprzedawcy:** Ustaw na „2024-07-31” dla promocji lipcowej.
- **Minimalna kwota:**

  - **Co robi to ustawienie:** Minimalna całkowita kwota zakupu (przed wysyłką i podatkami) wymagana do ważności bonu.
  - **Efekt zmiany tego ustawienia:** Jeśli całkowita kwota koszyka klienta jest niższa niż ta kwota, bon nie może zostać zastosowany.
  - **Zalecana wartość:** Ustaw na wartość, która zachęca do wyższych średnich wartości zamówień, lub 0, jeśli nie jest wymagana minimalna kwota.
  - **Scenariusz / przykład dla sprzedawcy:** Ustaw na „50.00”, aby oferować zniżkę tylko na zamówienia powyżej 50 USD.
- **Łącznie dostępnych:**

  - **Co robi to ustawienie:** Całkowita liczba razy, ile *wszystkie* wygenerowane bony w tej partii mogą być użyte przez *wszystkich* klientów.
  - **Efekt zmiany tego ustawienia:** Po osiągnięciu tego limitu, żadne inne bony z tej partii nie mogą być użyte, nawet jeśli poszczególne kody mają jeszcze dostępne użycia.
  - **Zalecana wartość:** Wysoka liczba (np. 99999), jeśli chcesz, aby obowiązywały limity poszczególnych kodów, lub konkretna liczba dla kampanii z ograniczonym czasem i całkowitą liczbą użyć.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli wygenerujesz 100 unikalnych kodów i ustawisz „Łącznie dostępnych” na 50, tylko pierwsze 50 użyć wszystkich kodów będzie ważnych.
- **Łącznie dostępnych dla każdego użytkownika:**

  - **Co robi to ustawienie:** Maksymalna liczba razy, ile *każdy indywidualny klient* może użyć *dowolnego* z bonów z tej partii.
  - **Efekt zmiany tego ustawienia:** Zapobiega wielokrotnemu używaniu przez jednego klienta różnych kodów z tej samej partii.
  - **Zalecana wartość:** „1” dla większości kampanii z unikalnymi bonami, aby zapewnić każdemu klientowi jedno użycie. „0” dla nieograniczonej liczby użyć na klienta (niezalecane dla unikalnych kodów).
  - **Scenariusz / przykład dla sprzedawcy:** Ustaw na „1”, aby upewnić się, że każdy klient może skorzystać tylko z jednego z wygenerowanych kodów.

#### **3. Akcje bonu**

Ta sekcja definiuje, co bon faktycznie robi po zastosowaniu.

- **Darmowa wysyłka:**

  - **Co robi to ustawienie:** Określa, czy bon przyznaje darmową wysyłkę.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Koszty wysyłki są anulowane dla zamówień korzystających z tego bonu.
    - *Gdy wyłączone:* Obowiązują standardowe koszty wysyłki.
  - **Zalecana wartość:** „NIE”, chyba że jest to konkretna promocja na darmową wysyłkę.
  - **Scenariusz / przykład dla sprzedawcy:** Dla promocji „Weekend z darmową wysyłką” włączyłbyś to.
- **Zastosuj rabat:**

  - **Co robi to ustawienie:** Tutaj definiujesz rzeczywistą kwotę lub procent rabatu.
  - **Efekt zmiany tego ustawienia:** Określa wartość pieniężną rabatu.
  - **Zalecana wartość:** Wybierz jeden rodzaj rabatu (procentowy, kwotowy lub na konkretny produkt) i wypełnij szczegóły.
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz zaoferować 15% zniżki.
  - **Procent:**

    - **Co robi to ustawienie:** Stosuje rabat procentowy do całkowitej kwoty zamówienia.
    - **Efekt zmiany tego ustawienia:** Zmniejsza całkowitą kwotę zamówienia o określony procent.
    - **Zalecana wartość:** Typowy procent, np. 5, 10, 15, 20.
    - **Scenariusz / przykład dla sprzedawcy:** Wprowadź „15” dla 15% zniżki.
  - **Kwota:**

    - **Co robi to ustawienie:** Stosuje stały rabat pieniężny do całkowitej kwoty zamówienia.
    - **Efekt zmiany tego ustawienia:** Zmniejsza całkowitą kwotę zamówienia o określoną kwotę.
    - **Zalecana wartość:** Stała kwota, np. 5.00, 10.00, 25.00.
    - **Scenariusz / przykład dla sprzedawcy:** Wprowadź „10.00” dla 10 USD zniżki.
  - **Zastosuj rabat do:**

    - **Co robi to ustawienie:** Określa, do której części zamówienia ma zastosowanie rabat.
    - **Efekt zmiany tego ustawienia:**
      - *Zamówienie (bez wysyłki):* Rabat dotyczy tylko sumy produktów.
      - *Konkretny produkt:* Rabat dotyczy tylko konkretnego produktu lub wyboru produktów.
      - *Najtańszy produkt:* Rabat dotyczy najtańszego przedmiotu w koszyku.
      - *Wybrane produkty:* Rabat dotyczy konkretnej listy produktów, którą definiujesz.
    - **Zalecana wartość:** „Zamówienie (bez wysyłki)” dla ogólnych rabatów.
    - **Scenariusz / przykład dla sprzedawcy:** Dla ogólnej 15% zniżki wybierz „Zamówienie (bez wysyłki)”. Jeśli chcesz 20% zniżki tylko na „T-shirty”, wybierz „Wybrane produkty”, a następnie wybierz kategorię/produkty T-shirtów.
- **Wyślij prezent:**

  - **Co robi to ustawienie:** Pozwala automatycznie dodać konkretny produkt jako darmowy prezent, gdy bon zostanie użyty.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Wybrany produkt jest dodawany do koszyka klienta za darmo.
    - *Gdy wyłączone:* Nie jest dostarczany żaden darmowy prezent.
  - **Zalecana wartość:** „NIE”, chyba że jest to konkretna promocja „prezent przy zakupie”.
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz dać darmowy „Brelok” do każdego zamówienia powyżej 100 USD. Włączyłbyś to i wybrał produkt Brelok.

#### **4. Generowanie bonów**

To ostatni krok, w którym definiujesz, ile kodów ma zostać wygenerowanych, a następnie wykonujesz generowanie.

- **Liczba bonów do wygenerowania:**

  - **Co robi to ustawienie:** Określa, ile unikalnych kodów bonów chcesz, aby moduł utworzył.
  - **Efekt zmiany tego ustawienia:** Określa ilość indywidualnych kodów rabatowych, które zostaną dodane do Twoich Reguł koszyka PrestaShop.
  - **Zalecana wartość:** Dokładna liczba unikalnych kodów, których potrzebujesz do swojej kampanii (np. 100 dla listy e-mail, 500 dla rozdawania w mediach społecznościowych).
  - **Scenariusz / przykład dla sprzedawcy:** Potrzebujesz 250 unikalnych kodów do kampanii marketingowej. Wprowadź „250”.
- **Przycisk Generuj Bony:**

  - **Co robi to ustawienie:** Ten przycisk inicjuje proces tworzenia wszystkich bonów na podstawie skonfigurowanych powyżej ustawień.
  - **Efekt zmiany tego ustawienia:** Kliknięcie tego przycisku spowoduje utworzenie określonej liczby unikalnych reguł koszyka w Twoim sklepie PrestaShop. Pojawi się komunikat potwierdzający, a Ty będziesz mógł pobrać plik CSV/Excel zawierający wygenerowane kody.
  - **Zalecana wartość:** Kliknij to tylko wtedy, gdy jesteś absolutnie pewien, że wszystkie Twoje ustawienia są poprawne.
  - **Scenariusz / przykład dla sprzedawcy:** Po przejrzeniu wszystkich ustawień dla kampanii „LATO2024” i ustawieniu liczby bonów na 250, klikasz „Generuj Bony”.

#### **5. Aktualizacje i informacje MyPresta.eu**

Ta sekcja zazwyczaj zawiera informacje o wersji modułu, dostępności aktualizacji i linki do MyPresta.eu.

- **Aktualizacje MyPresta.eu / Sprawdź aktualizacje:**
  - **Co robi to ustawienie:** Pozwala modułowi sprawdzić dostępność nowych wersji z MyPresta.eu.
  - **Efekt zmiany tego ustawienia:** Pomaga utrzymać moduł w aktualnym stanie z najnowszymi funkcjami i poprawkami błędów.
  - **Zalecana wartość:** Pozostaw to włączone, aby otrzymywać powiadomienia o aktualizacjach.
  - **Scenariusz / przykład dla sprzedawcy:** Widzisz powiadomienie, że dostępna jest nowa wersja, co zapewnia, że masz najbardziej stabilną i bogatą w funkcje wersję.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Nazwa | Tekst opisowy | Wewnętrzna nazwa dla partii bonów. |
| Konfiguracja modułu | Opis | Tekst opcjonalny | Wewnętrzne notatki dotyczące szczegółów kampanii. |
| Konfiguracja modułu | Podświetl | NIE | Wyświetl bon w podsumowaniu koszyka (TAK dla publicznych, NIE dla prywatnych). |
| Konfiguracja modułu | Częściowe użycie | NIE | Pozwól na wielokrotne użycie bonu, jeśli wartość > zamówienie. |
| Konfiguracja modułu | Priorytet | 1 | Kolejność stosowania dla wielu reguł koszyka (niższy = wyższy priorytet). |
| Konfiguracja modułu | Status | TAK | Aktywuj/dezaktywuj wygenerowane bony. |
| Konfiguracja modułu | Ważny od | Bieżąca data | Data rozpoczęcia ważności bonu. |
| Konfiguracja modułu | Ważny do | Przyszła data | Data zakończenia ważności bonu. |
| Konfiguracja modułu | Minimalna kwota | 0.00 | Minimalny zakup wymagany do użycia bonu. |
| Konfiguracja modułu | Łącznie dostępnych | Wysoka liczba (np. 99999) | Całkowita liczba użyć dla WSZYSTKICH bonów w tej partii. |
| Konfiguracja modułu | Łącznie dostępnych dla każdego użytkownika | 1 | Maksymalna liczba użyć na klienta dla dowolnego bonu w tej partii. |
| Konfiguracja modułu | Darmowa wysyłka | NIE | Przyznaj darmową wysyłkę z bonem. |
| Konfiguracja modułu | Zastosuj rabat | TAK | Włącz zastosowanie rabatu. |
| Konfiguracja modułu | Procent | (np. 10) | Rabat procentowy. |
| Konfiguracja modułu | Kwota | (np. 10.00) | Stały rabat pieniężny. |
| Konfiguracja modułu | Zastosuj rabat do | Zamówienie (bez wysyłki) | Zakres rabatu (zamówienie, konkretny produkt itp.). |
| Konfiguracja modułu | Wyślij prezent | NIE | Dodaj darmowy produkt jako prezent. |
| Konfiguracja modułu | Liczba bonów do wygenerowania | (np. 100) | Ilość unikalnych kodów do utworzenia. |
| Konfiguracja modułu | Przycisk Generuj Bony | Kliknij, gdy gotowe | Inicjuje tworzenie bonów i eksport CSV. |
| Konfiguracja modułu | Aktualizacje MyPresta.eu | TAK | Sprawdź aktualizacje modułu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Wygenerowałem bony, ale wydaje się, że nie działają we front office.**
O1:

- **Sprawdź status i daty:** Przejdź do „Katalog > Rabaty > Reguły koszyka” w Panelu administracyjnym PrestaShop. Znajdź wygenerowane bony. Upewnij się, że ich „Status” jest ustawiony na „Tak” oraz że daty „Ważny od” i „Ważny do” są aktualne.
- **Minimalna kwota:** Sprawdź, czy koszyk klienta spełnia wymóg „Minimalna kwota” ustawiony dla bonu.
- **Warunki:** Dokładnie sprawdź wszelkie inne warunki, które ustawiłeś (np. konkretne produkty, grupy klientów).
- **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).

**P2: Czy mogę edytować wygenerowane bony po ich utworzeniu?**
O2: Tak, po wygenerowaniu każdy bon staje się standardową „Regułą koszyka” w PrestaShop. Możesz przejść do „Katalog > Rabaty > Reguły koszyka” w Panelu administracyjnym, znaleźć poszczególne bony (zazwyczaj będą miały tę samą nazwę bazową, którą podałeś) i edytować ich właściwości (np. datę ważności, kwotę rabatu, warunki) indywidualnie. Jednak zazwyczaj lepiej jest poprawnie ustawić wszystkie ustawienia przed generowaniem.

**P3: Jak uzyskać listę wygenerowanych kodów bonów?**
O3: Natychmiast po kliknięciu przycisku „Generuj Bony” moduł poprosi Cię o pobranie pliku CSV/Excel zawierającego wszystkie unikalne kody. Jeśli to przegapiłeś, nie możesz ponownie pobrać listy bezpośrednio z modułu. Musiałbyś ręcznie wyeksportować „Reguły koszyka” z „Katalog > Rabaty > Reguły koszyka” w PrestaShop lub uzyskać bezpośredni dostęp do bazy danych (zadanie dla programisty). Kluczowe jest natychmiastowe zapisanie pliku CSV po wygenerowaniu.

**P4: Moduł wyświetla „Aktualizacje MyPresta.eu”, ale nie pokazuje nowej wersji.**
O4: Oznacza to, że Twój moduł jest aktualny z najnowszą oficjalną wersją dostępną z MyPresta.eu. Nie są wymagane żadne działania.

**P5: Mój niestandardowy motyw nie wyświetla poprawnie pola wprowadzania bonu.**
O5: Moduł Generator Bonów nie dodaje elementów front-office. Pole wprowadzania bonu to standardowa funkcja PrestaShop. Jeśli nie wyświetla się poprawnie, prawdopodobnie jest to problem ze stylizacją Twojego niestandardowego motywu lub nadpisaniami szablonów dla stron koszyka/realizacji zamówienia. Musiałbyś skonsultować się z deweloperem motywu lub webmasterem, aby dostosować pliki CSS lub TPL związane z hookami `displayCart` lub `displayPaymentTop`, gdzie zazwyczaj pojawia się pole bonu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł Generator Bonów (`vouchers`) to standardowy moduł PrestaShop działający głównie w Panelu administracyjnym. Wykorzystuje podstawową funkcjonalność `CartRule` PrestaShop do efektywnego tworzenia wielu kodów rabatowych. Główna logika modułu znajduje się w pliku `vouchers.php`, obsługującym konfigurację i proces generowania. Nie wprowadza złożonych wzorców MVC ani niestandardowych tabel baz danych, lecz bezpośrednio współdziała z istniejącym modelem obiektu `CartRule` PrestaShop.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Moduł nie dodaje żadnych niestandardowych kontrolerów front-office. Wszystkie interakcje front-office związane z bonami są obsługiwane przez natywne kontrolery PrestaShop `CartController` lub `OrderController`.
- **Kontrolery Back-Office Admin**: Brak. Logika konfiguracji i generowania modułu jest w całości zawarta w metodzie `getContent()` głównej klasy modułu, która jest renderowana przez standardowy `AdminModulesController`.

### 4.3 Klasy i modele podstawowe (`classes/`)

- Brak. Moduł nie definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Bezpośrednio wykorzystuje natywną klasę `CartRule` PrestaShop do tworzenia i zarządzania bonami.

### 4.4 Zasoby JavaScript (`views/js/`)

- `vouchers/lib/voucherengine/script.js`
  - **Zakres:** Panel administracyjny.
  - **Cel:** Ten skrypt prawdopodobnie zawiera logikę po stronie klienta dla strony konfiguracji modułu. Może to obejmować:
    - Walidację formularza przed generowaniem bonów.
    - Wywołania AJAX do metody `getContent()` modułu w celu dynamicznych aktualizacji lub przetwarzania.
    - Ulepszenia interfejsu użytkownika lub interakcje specyficzne dla formularza generowania bonów.
    - Potencjalnie obsługę pobierania wygenerowanego pliku CSV.
  - **Słuchacze zdarzeń:** Prawdopodobnie wiąże się z zdarzeniami przesyłania formularzy, zdarzeniami zmiany danych wejściowych i kliknięciami przycisków na stronie konfiguracji modułu.
  - **Manipulacja DOM:** Może pokazywać/ukrywać elementy na podstawie wyborów użytkownika (np. pokazywanie pól wyboru konkretnego produktu, jeśli wybrano „Zastosuj rabat do: Konkretny produkt”).

### 4.5 Arkusze stylów CSS (`views/css/`)

- `vouchers/lib/voucherengine/ps16.css`
  - **Zakres:** Stylizacja formularza administratora Panelu administracyjnego.
  - **Cel:** Zapewnia specyficzną stylizację interfejsu konfiguracji modułu, potencjalnie w celu zapewnienia spójnego wyglądu w różnych wersjach PrestaShop (np. dostosowanie do specyficznej struktury motywu administratora PrestaShop 1.6).
  - **Główne komponenty interfejsu użytkownika:** Stylizuje pola formularza, przyciski i elementy układu w ramach danych wyjściowych `getContent()` modułu.
  - **Kluczowe selektory klas CSS:** Programiści mogą sprawdzić stronę konfiguracji modułu w przeglądarce, aby zidentyfikować konkretne klasy (np. `.vouchers-generator-form`, `.mypresta-update-block`), które można nadpisać w niestandardowym motywie administratora, jeśli to konieczne.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- `vouchers/views/pdf.tpl`
  - **Zakres:** Panel administracyjny / Narzędzie.
  - **Cel:** Ten szablon jest prawdopodobnie używany do generowania dokumentu PDF do druku lub pobrania, zawierającego listę wygenerowanych bonów. Chociaż opis modułu wspomina o eksporcie CSV/Excel, szablon PDF sugeruje alternatywny lub dodatkowy format wyjściowy dla listy bonów, być może do drukowania fizycznych bonów.
  - **Użycie:** Zostanie wyrenderowany, gdy moduł będzie musiał przedstawić wygenerowane kody bonów w ustrukturyzowanym, możliwym do wydrukowania formacie. Otrzyma tablicę danych bonów (kod, wartość, data ważności itp.) z logiki PHP.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy żadnych niestandardowych tabel baz danych.
  - Współdziała z natywnymi tabelami PrestaShop `ps_cart_rule` i `ps_cart_rule_lang` w celu przechowywania wygenerowanych bonów.
  - Ustawienia konfiguracji (takie jak `vg_counter`, `mypresta_updates`) są przechowywane w tabeli `ps_configuration`.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administratora jest inicjalizowany, a jego media (JS/CSS) są ustawiane. | Używany przez moduł do dołączania plików JavaScript (`script.js`) i CSS (`ps16.css`) Panelu administracyjnego specjalnie na stronie konfiguracji, zapewniając ich ładowanie tylko wtedy, gdy są potrzebne. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu Generator Bonów, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
