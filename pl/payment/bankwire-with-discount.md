---
title: "Przelew bankowy z rabatem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla deweloperów modułu PrestaShop „Przelew bankowy z rabatem” od MyPresta.eu."
sidebar:
  label: "Przelew bankowy z rabatem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Bankwire with discount na MyPresta.eu](https://mypresta.eu/modules/payment-process/bankwire-with-discount.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/payment/bankwire-with-discount/)
>
> ---


# Przelew bankowy z rabatem

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są wymagane dla samego PrestaShop i zazwyczaj dostępne we wszystkich nowoczesnych środowiskach hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Przelew bankowy z rabatem)

Jest to główny ekran konfiguracji, na którym ustawisz wszystkie podstawowe funkcjonalności modułu.

#### **Ustawienia ogólne**

- **Włącz płatność przelewem bankowym:**

  - **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania metody płatności „Przelew bankowy z rabatem” w Twoim sklepie.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Klienci zobaczą „Zapłać przelewem bankowym” jako opcję płatności podczas realizacji zamówienia.
    - *Gdy wyłączone:* Opcja płatności przelewem bankowym zostanie ukryta przed klientami.
  - **Zalecana wartość:** TAK (aby korzystać z funkcji modułu).
  - **Scenariusz sprzedawcy:** Chcesz oferować płatności przelewem bankowym.
- **Tytuł przelewu bankowego:**

  - **Co robi to ustawienie:** Definiuje tytuł wyświetlany dla opcji płatności przelewem bankowym na stronie realizacji zamówienia.
  - **Efekt zmiany tego ustawienia:** Zmienia tekst, który klienci widzą podczas wyboru tej metody płatności.
  - **Zalecana wartość:** „Zapłać przelewem bankowym”, „Przelew bankowy (z rabatem!)” lub podobne.
  - **Scenariusz sprzedawcy:** Chcesz jasno oznaczyć metodę płatności dla klientów.
- **Instrukcje płatności (podsumowanie przy realizacji zamówienia):**

  - **Co robi to ustawienie:** Krótki tekst wyświetlany na stronie wyboru płatności (przed potwierdzeniem), aby szybko udzielić klientom instrukcji lub informacji o przelewie bankowym.
  - **Efekt zmiany tego ustawienia:** Zapewnia klientowi natychmiastowy kontekst dotyczący metody przelewu bankowego.
  - **Zalecana wartość:** „Dane bankowe otrzymasz po potwierdzeniu zamówienia. Rabat zastosowany!”
  - **Scenariusz sprzedawcy:** Chcesz poinformować klientów o kolejnych krokach lub wcześnie podkreślić korzyści z rabatu.
- **Instrukcje płatności (po potwierdzeniu zamówienia):**

  - **Co robi to ustawienie:** Szczegółowe instrukcje wyświetlane na stronie potwierdzenia zamówienia po złożeniu przez klienta zamówienia przelewem bankowym. Tutaj umieszczasz swoje dane konta bankowego.
  - **Efekt zmiany tego ustawienia:** Zapewnia klientom niezbędne informacje do dokonania przelewu bankowego.
  - **Zalecana wartość:** Podaj nazwę banku, właściciela konta, IBAN, SWIFT/BIC oraz wszelkie szczegółowe uwagi (np. „Prosimy o podanie numeru zamówienia w opisie przelewu”).
  - **Scenariusz sprzedawcy:** Jest to kluczowe dla klientów, aby pomyślnie zakończyli płatność.

#### **Dane konta bankowego**

Te pola służą do podawania klientom informacji o Twoim koncie bankowym.

- **Właściciel konta:**

  - **Co robi to ustawienie:** Nazwa właściciela konta bankowego.
  - **Efekt zmiany tego ustawienia:** Wyświetla tę nazwę klientowi.
  - **Zalecana wartość:** Nazwa Twojej firmy lub imię i nazwisko.
  - **Scenariusz sprzedawcy:** Niezbędne do przelewu bankowego.
- **Nazwa banku:**

  - **Co robi to ustawienie:** Nazwa Twojego banku.
  - **Efekt zmiany tego ustawienia:** Wyświetla tę nazwę klientowi.
  - **Zalecana wartość:** np. „Deutsche Bank”, „Bank of America”.
  - **Scenariusz sprzedawcy:** Niezbędne do przelewu bankowego.
- **Adres:**

  - **Co robi to ustawienie:** Adres Twojego banku.
  - **Efekt zmiany tego ustawienia:** Wyświetla ten adres klientowi.
  - **Zalecana wartość:** Adres oddziału Twojego banku.
  - **Scenariusz sprzedawcy:** Może być wymagane dla przelewów międzynarodowych.
- **IBAN (Międzynarodowy Numer Rachunku Bankowego):**

  - **Co robi to ustawienie:** Twój IBAN, ustandaryzowany międzynarodowy numer rachunku bankowego.
  - **Efekt zmiany tego ustawienia:** Wyświetla ten numer klientowi.
  - **Zalecana wartość:** Twój pełny IBAN.
  - **Scenariusz sprzedawcy:** Kluczowe dla przelewów bankowych, zwłaszcza w Europie.
- **SWIFT/BIC (Kod Identyfikacyjny Banku):**

  - **Co robi to ustawienie:** Twój kod SWIFT/BIC, używany do międzynarodowych przelewów bankowych.
  - **Efekt zmiany tego ustawienia:** Wyświetla ten kod klientowi.
  - **Zalecana wartość:** Twój pełny kod SWIFT/BIC.
  - **Scenariusz sprzedawcy:** Niezbędne dla międzynarodowych przelewów bankowych.
- **Dodatkowe informacje:**

  - **Co robi to ustawienie:** Wszelkie dodatkowe uwagi lub instrukcje, które chcesz podać dotyczące przelewu bankowego (np. „Prosimy o uwzględnienie 1-3 dni roboczych na przetworzenie”).
  - **Efekt zmiany tego ustawienia:** Zapewnia klientowi dodatkowe wskazówki.
  - **Zalecana wartość:** Wszelkie szczegółowe instrukcje nieobjęte innymi polami.
  - **Scenariusz sprzedawcy:** Chcesz zarządzać oczekiwaniami klientów dotyczącymi czasu przelewu.

#### **Ustawienia rabatów i dopłat**

Ta sekcja pozwala skonfigurować rabaty lub dopłaty za korzystanie z przelewu bankowego.

- **Typ rabatu:**

  - **Co robi to ustawienie:** Określa sposób obliczania rabatu.
  - **Efekt zmiany tego ustawienia:**
    - *Procentowy:* Rabat jest procentem od całkowitej kwoty zamówienia.
    - *Stała kwota:* Rabat jest stałą kwotą, niezależnie od całkowitej kwoty zamówienia.
  - **Zalecana wartość:** Procentowy (często bardziej atrakcyjny dla zmiennych wartości zamówień).
  - **Scenariusz sprzedawcy:** Chcesz zaoferować 5% zniżki lub stały rabat w wysokości 10 $.
- **Wartość rabatu:**

  - **Co robi to ustawienie:** Rzeczywista wartość rabatu (np. „5” dla 5% lub „10 $” dla stałej kwoty).
  - **Efekt zmiany tego ustawienia:** Bezpośrednio stosuje rabat do całkowitej kwoty zamówienia, jeśli wybrano przelew bankowy.
  - **Zalecana wartość:** Wartość, która sprawia, że przelew bankowy jest atrakcyjny, nie wpływając negatywnie na Twoje marże.
  - **Scenariusz sprzedawcy:** Decydujesz się zaoferować 3% rabatu lub 5 $ rabatu.
- **Podstawa procentowa (jeśli typ rabatu to procentowy):**

  - **Co robi to ustawienie:** Określa, do której części całkowitej kwoty zamówienia stosowany jest rabat procentowy.
  - **Efekt zmiany tego ustawienia:** Zmienia kwotę bazową do obliczania rabatu.
    - *Całkowita kwota zamówienia (z podatkami):* Rabat obliczany od pełnej ceny z podatkiem.
    - *Całkowita kwota zamówienia (bez podatków):* Rabat obliczany od ceny przed podatkiem.
    - *Całkowita kwota produktów (z podatkami):* Rabat tylko od wartości produktów, z podatkiem.
    - *Całkowita kwota produktów (bez podatków):* Rabat tylko od wartości produktów, bez podatku.
  - **Zalecana wartość:** Całkowita kwota zamówienia (z podatkami) dla prostoty i jasności dla klienta.
  - **Scenariusz sprzedawcy:** Chcesz dać 5% zniżki od całej ostatecznej ceny, którą widzi klient.
- **Minimalna wartość koszyka:**

  - **Co robi to ustawienie:** Minimalna całkowita wartość zamówienia, jaką musi mieć zamówienie, aby rabat za przelew bankowy został zastosowany.
  - **Efekt zmiany tego ustawienia:** Rabat pojawi się i zostanie zastosowany tylko wtedy, gdy całkowita kwota koszyka osiągnie lub przekroczy tę wartość.
  - **Zalecana wartość:** Pozostaw puste, jeśli nie ma minimum, lub ustaw wartość, aby zachęcić do większych zamówień.
  - **Scenariusz sprzedawcy:** Chcesz oferować rabat tylko na zamówienia powyżej 100 $.
- **Maksymalna wartość koszyka:**

  - **Co robi to ustawienie:** Maksymalna całkowita wartość zamówienia, jaką może mieć zamówienie, aby rabat za przelew bankowy został zastosowany.
  - **Efekt zmiany tego ustawienia:** Rabat nie zostanie zastosowany, jeśli całkowita kwota koszyka przekroczy tę wartość.
  - **Zalecana wartość:** Pozostaw puste, jeśli nie ma maksimum, lub ustaw wartość, aby ograniczyć ekspozycję rabatu na bardzo duże zamówienia.
  - **Scenariusz sprzedawcy:** Nie chcesz dawać rabatu na zamówienia powyżej 1000 $.
- **Waluty:**

  - **Co robi to ustawienie:** Wybierz waluty, dla których metoda płatności przelewem bankowym (i jej rabat) będzie dostępna.
  - **Efekt zmiany tego ustawienia:** Opcja płatności pojawi się tylko dla klientów dokonujących zakupów w wybranych walutach.
  - **Zalecana wartość:** Wybierz wszystkie akceptowane waluty.
  - **Scenariusz sprzedawcy:** Akceptujesz przelewy bankowe tylko w EUR i USD.
- **Strefy:**

  - **Co robi to ustawienie:** Wybierz strefy geograficzne, dla których metoda płatności przelewem bankowym (i jej rabat) będzie dostępna.
  - **Efekt zmiany tego ustawienia:** Opcja płatności pojawi się tylko dla klientów, których adres wysyłki znajduje się w wybranych strefach.
  - **Zalecana wartość:** Wybierz wszystkie strefy, do których wysyłasz.
  - **Scenariusz sprzedawcy:** Oferujesz przelew bankowy tylko w Europie.
- **Kraje:**

  - **Co robi to ustawienie:** Wybierz konkretne kraje, w których metoda płatności przelewem bankowym (i jej rabat) będzie dostępna.
  - **Efekt zmiany tego ustawienia:** Zastępuje ustawienia stref dla konkretnych krajów.
  - **Zalecana wartość:** Wybierz wszystkie kraje, do których wysyłasz.
  - **Scenariusz sprzedawcy:** Chcesz wykluczyć konkretny kraj z płatności przelewem bankowym.
- **Grupy klientów:**

  - **Co robi to ustawienie:** Wybierz grupy klientów, które mogą widzieć i używać metody płatności przelewem bankowym (i jej rabatu).
  - **Efekt zmiany tego ustawienia:** Tylko klienci należący do wybranych grup zobaczą tę opcję płatności.
  - **Zalecana wartość:** Wybierz wszystkie odpowiednie grupy klientów (np. „Klient”, „Gość”, „Odwiedzający”).
  - **Scenariusz sprzedawcy:** Chcesz oferować przelew bankowy tylko zarejestrowanym klientom.

#### **Zarządzanie nieopłaconymi zamówieniami**

Te funkcje pomagają zarządzać zamówieniami złożonymi przelewem bankowym, ale jeszcze nieopłaconymi.

- **Wysyłaj przypomnienia o nieopłaconych zamówieniach:**

  - **Co robi to ustawienie:** Włącza lub wyłącza automatyczne przypomnienia e-mail do klientów o nieopłaconych zamówieniach przelewem bankowym.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Moduł będzie wysyłał e-maile z przypomnieniami.
    - *Gdy wyłączone:* Nie będą wysyłane żadne przypomnienia.
  - **Zalecana wartość:** TAK (pomaga zmniejszyć liczbę porzuconych płatności).
  - **Scenariusz sprzedawcy:** Chcesz delikatnie przypomnieć klientom o dokonaniu płatności.
- **Pierwsze przypomnienie po (dniach):**

  - **Co robi to ustawienie:** Liczba dni po złożeniu zamówienia, po której zostanie wysłany pierwszy e-mail z przypomnieniem.
  - **Efekt zmiany tego ustawienia:** Kontroluje czas wysłania pierwszego przypomnienia.
  - **Zalecana wartość:** 2-3 dni (daje klientom czas na zapłatę, ale nie za długo).
  - **Scenariusz sprzedawcy:** Chcesz wysłać przypomnienie, jeśli płatność nie zostanie odebrana w ciągu 2 dni.
- **Maks. przypomnień na zamówienie:**

  - **Co robi to ustawienie:** Maksymalna liczba e-maili z przypomnieniami, które zamówienie wywoła.
  - **Efekt zmiany tego ustawienia:** Zapobiega spamowaniu klientów zbyt wieloma przypomnieniami.
  - **Zalecana wartość:** 1-2 (wystarczające do przypomnienia bez irytowania).
  - **Scenariusz sprzedawcy:** Chcesz wysłać tylko jeden e-mail z przypomnieniem.
- **Automatyczne anulowanie nieopłaconych zamówień:**

  - **Co robi to ustawienie:** Włącza lub wyłącza automatyczne anulowanie zamówień przelewem bankowym, które pozostają nieopłacone po określonym czasie.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Zamówienia zostaną automatycznie anulowane, zwalniając zapasy.
    - *Gdy wyłączone:* Zamówienia pozostaną w statusie „Oczekuje na płatność przelewem bankowym” na czas nieokreślony.
  - **Zalecana wartość:** TAK (automatyzuje zarządzanie zapasami i utrzymuje czystą listę zamówień).
  - **Scenariusz sprzedawcy:** Nie chcesz zbyt długo blokować zapasów dla nieopłaconych zamówień.
- **Anuluj po (dniach):**

  - **Co robi to ustawienie:** Liczba dni po złożeniu zamówienia, po której zostanie ono automatycznie anulowane, jeśli jest nieopłacone.
  - **Efekt zmiany tego ustawienia:** Kontroluje, kiedy nieopłacone zamówienia są anulowane.
  - **Zalecana wartość:** 5-7 dni (pozwala na rozsądny czas na płatność, ale zapobiega nieokreślonym blokadom).
  - **Scenariusz sprzedawcy:** Chcesz anulować zamówienia, jeśli płatność nie zostanie odebrana w ciągu 7 dni.
- **Automatyczne umieszczanie na czarnej liście sprawców:**

  - **Co robi to ustawienie:** Jeśli włączone, klienci, którzy wielokrotnie składają zamówienia przelewem bankowym, a następnie mają je anulowane z powodu braku płatności, zostaną dodani do czarnej listy.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Klienci przekraczający próg zostaną umieszczeni na czarnej liście.
    - *Gdy wyłączone:* Żaden klient nie zostanie automatycznie umieszczony na czarnej liście.
  - **Zalecana wartość:** TAK (pomaga zniechęcić oszustów lub klientów marnujących czas).
  - **Scenariusz sprzedawcy:** Chcesz uniemożliwić klientom, którzy nigdy nie płacą, składanie przyszłych zamówień przelewem bankowym.
- **Próg anulowanych zamówień:**

  - **Co robi to ustawienie:** Liczba anulowanych zamówień przelewem bankowym, jaką klient może mieć, zanim zostanie automatycznie umieszczony na czarnej liście.
  - **Efekt zmiany tego ustawienia:** Definiuje tolerancję dla braku płatności przed umieszczeniem na czarnej liście.
  - **Zalecana wartość:** 2-3 (pozwala na prawdziwe błędy, ale wyłapuje recydywistów).
  - **Scenariusz sprzedawcy:** Chcesz umieścić klienta na czarnej liście po 3 nieopłaconych i anulowanych zamówieniach przelewem bankowym.

#### **Ustawienia zaawansowane**

- **Token zadania Cron:**

  - **Co robi to ustawienie:** Unikalny token bezpieczeństwa używany do zabezpieczenia adresu URL zadania cron modułu. Jest to niezbędne do działania automatycznych przypomnień i funkcji anulowania.
  - **Efekt zmiany tego ustawienia:** Zadanie cron zostanie wykonane tylko wtedy, gdy ten token zostanie poprawnie uwzględniony w adresie URL.
  - **Zalecana wartość:** Pozostaw jako wygenerowane. Nie zmieniaj, chyba że wiesz, co robisz.
  - **Scenariusz sprzedawcy:** Musisz skonfigurować zadanie cron na swoim serwerze, aby uruchamiać zautomatyzowane zadania modułu. Adres URL cron będzie wyglądał mniej więcej tak: `twojasklep.com/module/bankwiredis/cron?token=TWÓJ_TOKEN_TUTAJ`.
- **Selektory CSS do dynamicznych aktualizacji:**

  - **Co robi to ustawienie:** Te pola pozwalają określić selektory CSS dla elementów na stronie realizacji zamówienia, które wyświetlają całkowitą kwotę koszyka, sumę częściową i koszt wysyłki. Moduł używa ich do dynamicznej aktualizacji cen po zastosowaniu rabatu.
  - **Efekt zmiany tego ustawienia:** Jeśli Twój motyw używa niestandardowych klas CSS dla tych elementów, dostosowanie tych selektorów zapewnia, że rabat jest poprawnie odzwierciedlony w wyświetlanych cenach podczas realizacji zamówienia.
  - **Zalecana wartość:** Pozostaw domyślne, chyba że rabat nie wyświetla się poprawnie na stronie realizacji zamówienia. W przypadku problemów skonsultuj się z deweloperem motywu lub webmasterem.
  - **Scenariusz sprzedawcy:** Twój niestandardowy motyw używa `.my-custom-total-price` zamiast domyślnego `.cart-total-price`. Zaktualizowałbyś to pole, aby upewnić się, że rabat jest wizualnie zastosowany.
- **Szablon e-mail:**

  - **Co robi to ustawienie:** Pozwala wybrać niestandardowy szablon e-mail dla instrukcji płatności przelewem bankowym i przypomnień.
  - **Efekt zmiany tego ustawienia:** Zmienia wygląd i zawartość e-maili wysyłanych przez moduł.
  - **Zalecana wartość:** Domyślny (chyba że masz niestandardowy szablon).
  - **Scenariusz sprzedawcy:** Chcesz użyć markowego szablonu e-mail do komunikacji dotyczącej przelewów bankowych.

#### **Zasady widoczności (zaawansowane targetowanie rabatów)**

Ta sekcja pozwala tworzyć bardzo szczegółowe zasady dotyczące tego, kiedy oferowany jest rabat za przelew bankowy.

- **Nazwa reguły:**

  - **Co robi to ustawienie:** Opisowa nazwa dla Twojej reguły rabatowej (np. „Rabat świąteczny za przelew bankowy”).
  - **Efekt zmiany tego ustawienia:** Pomaga identyfikować i zarządzać różnymi regułami.
  - **Zalecana wartość:** Jasna i zwięzła nazwa.
  - **Scenariusz sprzedawcy:** Masz wiele reguł rabatowych i musisz je rozróżnić.
- **Aktywna:**

  - **Co robi to ustawienie:** Włącza lub wyłącza tę konkretną regułę rabatową.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Reguła jest aktywna i jej warunki zostaną sprawdzone.
    - *Gdy wyłączone:* Reguła jest ignorowana.
  - **Zalecana wartość:** TAK (jeśli chcesz, aby reguła miała zastosowanie).
  - **Scenariusz sprzedawcy:** Chcesz tymczasowo wyłączyć sezonowy rabat.
- **Pozycja (priorytet):**

  - **Co robi to ustawienie:** Określa kolejność, w jakiej reguły są oceniane, jeśli może mieć zastosowanie wiele reguł. Niższe liczby mają wyższy priorytet.
  - **Efekt zmiany tego ustawienia:** Jeśli koszyk klienta pasuje do wielu reguł, zastosowana zostanie ta z najniższą pozycją.
  - **Zalecana wartość:** Użyj kolejnych liczb (1, 2, 3…), aby zarządzać priorytetem.
  - **Scenariusz sprzedawcy:** Jeśli klient kwalifikuje się zarówno do reguły „Ogólne 5% zniżki” (pozycja 10), jak i reguły „VIP 10% zniżki” (pozycja 5), zastosowana zostanie reguła VIP.
- **Typ rabatu, Wartość rabatu, Podstawa procentowa, Minimalna wartość koszyka, Maksymalna wartość koszyka, Waluty, Strefy, Kraje, Grupy klientów:**

  - **Co robi to ustawienie:** Są to te same ustawienia, co opisane w sekcji „Ustawienia rabatów i dopłat” powyżej, ale zastosowane konkretnie do *tej indywidualnej reguły*. Pozwala to na posiadanie różnych kwot rabatów lub warunków dla różnych scenariuszy.
  - **Efekt zmiany tego ustawienia:** Rabat zdefiniowany w tej regule zostanie zastosowany tylko wtedy, gdy spełnione zostaną wszystkie jej specyficzne warunki.
  - **Zalecana wartość:** Skonfiguruj na podstawie swojej konkretnej strategii promocyjnej.
  - **Scenariusz sprzedawcy:** Chcesz zaoferować 10% rabatu na płatności przelewem bankowym tylko dla klientów z grupy „Hurtownik” i tylko dla zamówień powyżej 500 $.
- **Produkty:**

  - **Co robi to ustawienie:** Pozwala określić, że ta reguła rabatowa ma zastosowanie tylko wtedy, gdy w koszyku znajdują się określone produkty.
  - **Efekt zmiany tego ustawienia:** Rabat za przelew bankowy zostanie zaoferowany tylko wtedy, gdy w koszyku klienta znajduje się jeden lub więcej wybranych produktów.
  - **Zalecana wartość:** Pozostaw puste, aby zastosować do wszystkich produktów, lub wybierz konkretne produkty do ukierunkowanych promocji.
  - **Scenariusz sprzedawcy:** Chcesz oferować rabat za przelew bankowy tylko wtedy, gdy klient kupi konkretny, drogi przedmiot.
- **Kategorie:**

  - **Co robi to ustawienie:** Pozwala określić, że ta reguła rabatowa ma zastosowanie tylko wtedy, gdy w koszyku znajdują się produkty z określonych kategorii.
  - **Efekt zmiany tego ustawienia:** Rabat za przelew bankowy zostanie zaoferowany tylko wtedy, gdy w koszyku klienta znajduje się jeden lub więcej produktów z wybranych kategorii.
  - **Zalecana wartość:** Pozostaw puste, aby zastosować do wszystkich kategorii, lub wybierz konkretne kategorie do ukierunkowanych promocji.
  - **Scenariusz sprzedawcy:** Chcesz oferować rabat za przelew bankowy tylko na produkty z kategorii „Elektronika”.

#### **Tabela szybkiego odniesienia do konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz płatność przelewem bankowym | TAK | Aktywuje/dezaktywuje metodę płatności. |
|  | Tytuł przelewu bankowego | „Zapłać przelewem bankowym” | Tekst wyświetlany dla opcji płatności. |
|  | Instrukcje płatności (realizacja zamówienia) | Krótki, jasny tekst | Informacje wyświetlane na stronie wyboru płatności. |
|  | Instrukcje płatności (potwierdzenie) | Szczegółowe dane bankowe | Dane bankowe i instrukcje po zamówieniu. |
|  | Właściciel konta | Nazwa Twojej firmy | Nazwa na koncie bankowym. |
|  | Nazwa banku | Twój bank | Nazwa Twojego banku. |
|  | Adres | Adres Twojego banku | Adres Twojego banku. |
|  | IBAN | Twój IBAN | Międzynarodowy Numer Rachunku Bankowego. |
|  | SWIFT/BIC | Twój SWIFT/BIC | Kod Identyfikacyjny Banku dla przelewów międzynarodowych. |
|  | Dodatkowe informacje | Opcjonalne uwagi | Dodatkowe instrukcje dla klientów. |
|  | Typ rabatu | Procentowy | Sposób obliczania rabatu (procentowy/stała kwota). |
|  | Wartość rabatu | 0 (lub pożądana wartość) | Rzeczywista kwota lub procent rabatu. |
|  | Podstawa procentowa | Całkowita kwota zamówienia (z podatkami) | Kwota, do której stosowany jest rabat procentowy. |
|  | Minimalna wartość koszyka | Puste (lub pożądana wartość) | Minimalna wartość zamówienia dla rabatu. |
|  | Maksymalna wartość koszyka | Puste (lub pożądana wartość) | Maksymalna wartość zamówienia dla rabatu. |
|  | Waluty | Wszystkie aktywne | Waluty, w których dostępny jest przelew bankowy. |
|  | Strefy | Wszystkie aktywne | Strefy geograficzne, w których dostępny jest przelew bankowy. |
|  | Kraje | Wszystkie aktywne | Konkretne kraje, w których dostępny jest przelew bankowy. |
|  | Grupy klientów | Wszystkie aktywne | Grupy klientów, które mogą korzystać z przelewu bankowego. |
|  | Wysyłaj przypomnienia o nieopłaconych zamówieniach | TAK | Włącza przypomnienia e-mail o nieopłaconych zamówieniach. |
|  | Pierwsze przypomnienie po (dniach) | 2-3 dni | Opóźnienie przed pierwszym przypomnieniem. |
|  | Maks. przypomnień na zamówienie | 1-2 | Maksymalna liczba e-maili z przypomnieniami. |
|  | Automatyczne anulowanie nieopłaconych zamówień | TAK | Automatycznie anuluje nieopłacone zamówienia. |
|  | Anuluj po (dniach) | 5-7 dni | Opóźnienie przed automatycznym anulowaniem. |
|  | Automatyczne umieszczanie na czarnej liście sprawców | TAK | Umieszcza na czarnej liście klientów z zbyt wieloma anulowanymi zamówieniami. |
|  | Próg anulowanych zamówień | 2-3 | Liczba anulowanych zamówień przed umieszczeniem na czarnej liście. |
|  | Token zadania Cron | Automatycznie generowany | Token bezpieczeństwa dla zadania cron. |
|  | Selektory CSS | Domyślne (lub specyficzne dla motywu) | Do dynamicznych aktualizacji cen przy realizacji zamówienia. |
|  | Szablon e-mail | Domyślny | Szablon e-mail do komunikacji dotyczącej przelewów bankowych. |
|  | **Zasady widoczności** | Nazwa reguły | Opisowa nazwa |
|  | Aktywna | TAK | Aktywuje/dezaktywuje konkretną regułę. |
|  | Pozycja (priorytet) | 1, 2, 3… | Kolejność oceny reguł (niższa = wyższy priorytet). |
|  | Produkty | Puste (lub konkretne produkty) | Rabat ma zastosowanie tylko wtedy, gdy te produkty znajdują się w koszyku. |
|  | Kategorie | Puste (lub konkretne kategorie) | Rabat ma zastosowanie tylko wtedy, gdy produkty z tych kategorii znajdują się w koszyku. |

### 2.2 Ekran kontrolera Panelu administracyjnego: AdminBankwiredisSearchController

- **Nazwa ekranu i lokalizacja w menu:** Ten kontroler jest zazwyczaj używany do zarządzania konkretnymi encjami związanymi z modułem, takimi jak klienci na czarnej liście lub konkretne zasady rabatowe, często dostępny za pośrednictwem podzakładki w głównej konfiguracji modułu lub dedykowanej pozycji menu. W tym module prawdopodobnie służy do zarządzania zasadami widoczności lub klientami na czarnej liście.
  - **Lokalizacja w menu:** Prawdopodobnie dostępny za pośrednictwem zakładki lub linku na głównej stronie konfiguracji modułu „Przelew bankowy z rabatem” lub potencjalnie w **Sprzedaż > Zamówienia > Czarna lista przelewów bankowych z rabatem** (przykład, rzeczywista lokalizacja może się różnić w zależności od wersji PrestaShop i projektu modułu).
- **Dostępne działania i ustawienia:** Ten ekran zapewnia widok zarządzania oparty na siatce.
  - **Tabela listująca:** Wyświetla listę elementów (np. klientów na czarnej liście, zasady rabatowe). Każdy wiersz zazwyczaj pokazuje odpowiednie szczegóły, takie jak ID klienta, adres e-mail klienta, powód umieszczenia na czarnej liście, nazwa reguły, status aktywności itp.
  - **Przyciski Dodaj/Edytuj:** Pozwala ręcznie dodawać nowe wpisy (np. ręcznie umieścić klienta na czarnej liście) lub edytować istniejące.
  - **Działania zbiorcze:** Opcje wykonywania działań na wielu wybranych elementach (np. usuwanie wielu klientów z czarnej listy).
  - **Wyszukiwanie/Filtrowanie:** Narzędzia do znajdowania konkretnych wpisów na liście.
- **Efekt zmian:**
  - **Dodawanie/Edytowanie wpisów na czarnej liście:** Bezpośrednio wpływa na to, którym klientom uniemożliwia się korzystanie z metody płatności przelewem bankowym.
  - **Dodawanie/Edytowanie zasad rabatowych:** Modyfikuje warunki, na jakich stosowane są rabaty, wpływając na ceny i zachęty dla klientów.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. Regularnie przeglądaj listę klientów na czarnej liście, aby upewnić się, że jest aktualna.
  2. Jeśli musisz ręcznie umieścić klienta na czarnej liście (np. po bezpośredniej komunikacji), użyj tutaj funkcji „Dodaj”.
  3. Jeśli musisz dostosować lub utworzyć nowe zasady rabatowe, to tutaj będziesz nimi zarządzać, upewniając się, że są zgodne z Twoimi aktualnymi promocjami.

### 2.3 Ekran kontrolera Panelu administracyjnego: index.php (Kontroler administracyjny)

- **Nazwa ekranu i lokalizacja w menu:** Plik `index.php` w katalogu kontrolera administracyjnego często służy jako placeholder lub przekierowanie, lub w niektórych przypadkach może być punktem wejścia do pulpitu nawigacyjnego lub prostej listy. Biorąc pod uwagę funkcje modułu, może to być pulpit nawigacyjny dla statystyk przelewów bankowych lub prosta lista oczekujących zamówień przelewem bankowym.
  - **Lokalizacja w menu:** Potencjalnie podzakładka w głównej konfiguracji modułu lub dedykowana pozycja menu, taka jak **Sprzedaż > Zamówienia > Pulpit nawigacyjny przelewów bankowych z rabatem**.
- **Dostępne działania i ustawienia:** Ten ekran prawdopodobnie przedstawia siatkę lub pulpit nawigacyjny.
  - **Widok siatki / zarządzania:** Może wyświetlać listę ostatnich zamówień przelewem bankowym, ich status, wysłane przypomnienia o płatności lub status anulowania.
  - **Analityka/Statystyki:** Może wyświetlać wykresy lub podsumowania związane z płatnościami przelewem bankowym, takie jak współczynniki konwersji, średni zastosowany rabat lub liczba nieopłaconych zamówień.
- **Efekt zmian:** Ten ekran służy zazwyczaj do monitorowania i raportowania, a nie do bezpośrednich zmian konfiguracji. Wszelkie działania podjęte tutaj (np. ręczne oznaczenie zamówienia jako opłaconego) zaktualizują status zamówienia w PrestaShop.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. Okresowo sprawdzaj ten pulpit nawigacyjny, aby monitorować wydajność metody płatności przelewem bankowym.
  2. Przeglądaj oczekujące zamówienia przelewem bankowym, aby upewnić się, że są przetwarzane lub przypominane/anulowane zgodnie z oczekiwaniami.
  3. Korzystaj z dostępnych statystyk, aby ocenić skuteczność rabatów za przelew bankowy i systemu przypomnień.

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P1: Opcja płatności przelewem bankowym nie wyświetla się na mojej stronie realizacji zamówienia.**

- **O:** Najpierw sprawdź, czy „Włącz płatność przelewem bankowym” jest ustawione na TAK w konfiguracji modułu.
- **O:** Następnie zweryfikuj ustawienia „Waluty”, „Strefy”, „Kraje” i „Grupy klientów”. Jeśli kontekst klienta (waluta, adres wysyłki lub grupa) nie pasuje do Twoich wyborów, metoda płatności nie pojawi się.
- **O:** Jeśli masz konkretne zasady widoczności, upewnij się, że koszyk klienta spełnia wszystkie warunki (min/max wartość koszyka, konkretne produkty/kategorie).
- **O:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).

**P2: Rabat nie jest stosowany lub wyświetlany poprawnie na stronie realizacji zamówienia.**

- **O:** Sprawdź dokładnie ustawienia „Typ rabatu” i „Wartość rabatu”.
- **O:** Przejrzyj wszelkie ustawienia „Minimalna wartość koszyka” lub „Maksymalna wartość koszyka” – całkowita kwota koszyka musi mieścić się w tych zakresach.
- **O:** Jeśli używasz niestandardowego motywu, moduł może nie być w stanie znaleźć poprawnych selektorów CSS do dynamicznej aktualizacji cen. Przejdź do sekcji „Ustawienia zaawansowane” i upewnij się, że „Selektory CSS do dynamicznych aktualizacji” pasują do rzeczywistych selektorów Twojego motywu dla całkowitej kwoty koszyka, sumy częściowej i wysyłki. Może być konieczne, aby webmaster sprawdził kod Twojego motywu.
- **O:** Wyczyść pamięć podręczną PrestaShop.

**P3: Automatyczne przypomnienia lub anulowania nie działają.**

- **O:** Jest to prawie zawsze problem z zadaniem cron. Musisz skonfigurować zadanie cron na swoim serwerze, aby okresowo uruchamiać zadania modułu.
- **O:** W „Ustawieniach zaawansowanych” modułu skopiuj „Token zadania Cron” i pełny adres URL cron.
- **O:** Uzyskaj dostęp do panelu sterowania swojego hostingu (cPanel, Plesk itp.) i znajdź sekcję „Zadania Cron”.
- **O:** Dodaj nowe zadanie cron, które wykonuje podany adres URL co kilka godzin (np. `wget -O /dev/null "https://twojasklep.com/module/bankwiredis/cron?token=TWÓJ_TOKEN_TUTAJ"`).
- **O:** Upewnij się, że „Wysyłaj przypomnienia o nieopłaconych zamówieniach” i „Automatyczne anulowanie nieopłaconych zamówień” są włączone, a dni są poprawnie ustawione.

**P4: Jak przetłumaczyć teksty modułu na inne języki?**

- **O:** W Panelu administracyjnym PrestaShop przejdź do **Lokalizacja > Tłumaczenia**.
- **O:** Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz „Przelew bankowy z rabatem” z rozwijanej listy modułów.
- **O:** Możesz wtedy edytować wszystkie przetłumaczalne ciągi dla modułu. Pamiętaj, aby zapisać zmiany.

**P5: Klient został umieszczony na czarnej liście, ale chcę ponownie zezwolić mu na korzystanie z przelewu bankowego.**

- **O:** Przejdź do dedykowanego ekranu administracyjnego modułu (prawdopodobnie w **Sprzedaż > Zamówienia > Czarna lista przelewów bankowych z rabatem** lub podobnie, lub zakładka w konfiguracji modułu).
- **O:** Znajdź klienta na liście i usuń jego wpis z czarnej listy lub edytuj go, aby dezaktywować czarną listę dla niego.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Przelew bankowy z rabatem” (`bankwiredis`) rozszerza funkcjonalność płatności PrestaShop, przestrzegając wzorca MVC. Integruje się z procesem realizacji zamówienia za pomocą hooków `PaymentOptions`, zarządza statusami zamówień i implementuje zautomatyzowane zadania (przypomnienia, anulowania, umieszczanie na czarnej liście) za pośrednictwem zadania cron. Logika rabatowa jest stosowana dynamicznie podczas realizacji zamówienia i utrwalana wraz z zamówieniem. Niestandardowe kontrolery administracyjne zapewniają interfejsy zarządzania dla zasad rabatowych i klientów na czarnej liście.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

- `controllers/front/cron.php`
  - **Nazwa klasy:** `BankwiredisCronModuleFrontController` (rozszerza `ModuleFrontController`)
  - **Odpowiedzialność:** Ten kontroler obsługuje wykonywanie zaplanowanych zadań. Jest zaprojektowany do wywoływania przez zadanie cron po stronie serwera przy użyciu bezpiecznego tokena. Przetwarza przypomnienia o nieopłaconych zamówieniach, automatyczne anulowania i umieszczanie klientów na czarnej liście na podstawie konfiguracji modułu. Nie renderuje bezpośrednio żadnej zawartości front-office, ale wykonuje operacje w tle.
- `controllers/front/index.php`
  - **Nazwa klasy:** `BankwiredisIndexModuleFrontController` (rozszerza `ModuleFrontController`)
  - **Odpowiedzialność:** Często placeholder lub domyślny punkt wejścia. W tym module może obsługiwać przekierowania lub służyć jako fallback, jeśli inne konkretne kontrolery front-office nie pasują. Zazwyczaj nie ma bezpośredniej funkcji skierowanej do użytkownika.
- `controllers/front/payment.php`
  - **Nazwa klasy:** `BankwiredisPaymentModuleFrontController` (rozszerza `ModuleFrontController`)
  - **Odpowiedzialność:** Ten kontroler jest odpowiedzialny za wyświetlanie szczegółów płatności przelewem bankowym i instrukcji dla klienta *po* wybraniu przelewu bankowego jako metody płatności, ale *przed* pełnym zatwierdzeniem zamówienia. Przygotowuje dane (dane bankowe, ostateczna kwota z rabatem) dla szablonu `payment.tpl` lub `validation.tpl`.
- `controllers/front/validation.php`
  - **Nazwa klasy:** `BankwiredisValidationModuleFrontController` (rozszerza `ModuleFrontController`)
  - **Odpowiedzialność:** Jest to kluczowy kontroler, który przetwarza ostateczne zatwierdzenie zamówienia przelewem bankowym. Po potwierdzeniu wyboru przez klienta, ten kontroler tworzy zamówienie w PrestaShop, ustawia jego początkowy status (np. „Oczekuje na płatność przelewem bankowym”), stosuje obliczony rabat i przekierowuje klienta na stronę potwierdzenia zamówienia.

#### Kontrolery administracyjne Back-Office

- `controllers/admin/AdminBankwiredisSearchController.php`
  - **Nazwa klasy:** `AdminBankwiredisSearchController` (rozszerza `ModuleAdminController`)
  - **Nazwa zakładki:** Prawdopodobnie podzakładka w głównej konfiguracji modułu lub dedykowana pozycja menu.
  - **Zarządzana encja:** Ten kontroler zarządza niestandardowymi encjami modułu, w szczególności zasadami widoczności rabatów i potencjalnie klientami na czarnej liście. Zapewnia standardowy interfejs PrestaShop `HelperList` lub `HelperForm` do przeglądania, dodawania, edytowania i usuwania tych rekordów.
- `controllers/admin/index.php`
  - **Nazwa klasy:** `AdminBankwiredisIndexController` (rozszerza `ModuleAdminController`)
  - **Nazwa zakładki:** Podobnie jak `AdminBankwiredisSearchController`, byłaby to dedykowana strona administracyjna.
  - **Zarządzana encja:** Biorąc pod uwagę funkcje modułu, ten kontroler prawdopodobnie służy jako pulpit nawigacyjny lub interfejs zarządzania dla podstawowych danych modułu, takich jak lista oczekujących zamówień przelewem bankowym, statystyki lub uproszczony widok klientów na czarnej liście.

### 4.3 Podstawowe klasy i modele (`classes/`)

Dossier modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Sugeruje to, że dane modułu (takie jak zasady rabatowe, klienci na czarnej liście) mogą być przechowywane bezpośrednio w `ps_configuration` lub zarządzane za pośrednictwem ogólnych instancji `ObjectModel` zdefiniowanych w głównym pliku `bankwiredis.php` lub bezpośrednio w kontrolerach administracyjnych.

- **Uwaga:** Jeśli używane są niestandardowe tabele, ich definicje `ObjectModel` zazwyczaj znajdowałyby się tutaj. Moduł prawdopodobnie używa `Configuration::get()` i `Configuration::updateValue()` dla większości ustawień i potencjalnie `Db::getInstance()` do bezpośrednich interakcji z bazą danych dla bardziej złożonych struktur danych, takich jak zasady rabatowe lub klienci na czarnej liście, jeśli nie są mapowane na niestandardowy `ObjectModel`.

### 4.4 Zasoby JavaScript (`views/js/`)

- `bankwiredis/lib/searchTool/views/js/autocomplete.js`
  - **Zakres:** Panel administracyjny.
  - **Funkcjonalność:** Zapewnia funkcjonalność autouzupełniania, prawdopodobnie używaną w formularzach administracyjnych (np. `AdminBankwiredisSearchController`) do wybierania produktów lub kategorii podczas definiowania zasad widoczności rabatów. Nasłuchuje wprowadzania danych przez użytkownika w określonych polach tekstowych i wykonuje żądania AJAX, aby sugerować pasujące elementy.
- `bankwiredis/views/js/adminBankwiredisAccounts.js`
  - **Zakres:** Panel administracyjny.
  - **Funkcjonalność:** Prawdopodobnie obsługuje dynamiczne zachowanie na stronie konfiguracji modułu związane z danymi konta bankowego. Może to obejmować pokazywanie/ukrywanie pól na podstawie wybranych opcji, walidację danych wejściowych lub wywołania AJAX w celu zapisania informacji o koncie.
- `bankwiredis/views/js/adminBankwiredisDashboard.js`
  - **Zakres:** Panel administracyjny.
  - **Funkcjonalność:** Zarządza interaktywnymi elementami i wizualizacją danych na pulpicie nawigacyjnym modułu (np. `AdminBankwiredisIndexController`). Może to obejmować pobieranie danych za pośrednictwem AJAX w celu wypełniania wykresów, tabel lub aktualizowania statystyk oraz obsługę interakcji użytkownika z widżetami pulpitu nawigacyjnego.
- `bankwiredis/views/js/bankwiredis-checkout.js`
  - **Zakres:** Front-office.
  - **Funkcjonalność:** Jest to kluczowy skrypt dla doświadczenia klienta. Nasłuchuje wyboru opcji płatności przelewem bankowym na stronie realizacji zamówienia. Po wybraniu wykonuje wywołanie AJAX do kontrolera front-office modułu w celu obliczenia i wyświetlenia dynamicznego rabatu, aktualizując elementy całkowitej kwoty zamówienia, sumy częściowej i kosztów wysyłki na stronie. Używa selektorów CSS skonfigurowanych w panelu administracyjnym (`BDIS_CSS_PAY_INPUT`, `BDIS_CSS_CART_TOTAL` itp.), aby wskazać poprawne elementy DOM do aktualizacji.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `bankwiredis/lib/searchTool/views/css/autocomplete.css`
  - **Zakres:** Panel administracyjny.
  - **Funkcjonalność:** Stylizuje rozwijane sugestie autouzupełniania i pola wprowadzania używane w narzędziach wyszukiwania administracyjnego.
- `bankwiredis/views/css/admin_bankwiredis.css`
  - **Zakres:** Panel administracyjny.
  - **Funkcjonalność:** Zapewnia specyficzne style dla strony konfiguracji modułu i niestandardowych widoków kontrolera administracyjnego, zapewniając spójny i przyjazny dla użytkownika interfejs w panelu administracyjnym PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

- `bankwiredis/views/templates/hook/infos.tpl`
  - **Hook:** Prawdopodobnie `displayPaymentInfo` lub podobny.
  - **Wyjście:** Wyświetla ogólne informacje lub podsumowanie dotyczące metody płatności przelewem bankowym, potencjalnie zawierające ofertę rabatową, na stronie wyboru płatności lub w podsumowaniu zamówienia.
- `bankwiredis/views/templates/hook/payment.tpl`
  - **Hook:** `displayPaymentOptions` (PrestaShop 1.7+), `displayPayment` (PrestaShop 1.6).
  - **Wyjście:** Renderuje rzeczywistą opcję płatności przelewem bankowym na stronie realizacji zamówienia, w tym jej tytuł, opis i dynamicznie obliczoną kwotę rabatu. To tutaj klient wybiera „Zapłać przelewem bankowym”.
- `bankwiredis/views/templates/hook/payment_return.tpl`
  - **Hook:** `displayPaymentReturn`.
  - **Wyjście:** Wyświetla dane konta bankowego i instrukcje płatności na stronie potwierdzenia zamówienia po pomyślnym złożeniu zamówienia przelewem bankowym przez klienta.
- `bankwiredis/views/templates/hook/payment_return_pdf_invoice.tpl`
  - **Hook:** `displayPDFInvoice` (lub podobny do generowania PDF).
  - **Wyjście:** Zapewnia niezbędną zawartość (dane bankowe, podsumowanie rabatu) do włączenia do faktury PDF generowanej dla zamówień przelewem bankowym.

#### Szablony administracyjne (`views/templates/admin/`)

- `bankwiredis/lib/searchTool/views/scripts.tpl`
  - **Wyjście:** Prawdopodobnie zawiera zasoby JavaScript i CSS dla narzędzia wyszukiwania autouzupełniania w formularzach administracyjnych.
- `bankwiredis/views/templates/admin/scopeSelector.tpl`
  - **Wyjście:** Szablon do wyboru zakresu (np. sklep, grupa, wszystkie sklepy) w środowisku wielosklepowym, często używany w formularzach konfiguracji.
- `bankwiredis/views/templates/admin/selectedProducts.tpl`
  - **Wyjście:** Wyświetla listę produktów, które zostały wybrane dla konkretnej reguły rabatowej (np. w `AdminBankwiredisSearchController` podczas konfigurowania reguły opartej na produktach).

#### Szablony front-office (`views/templates/front/`)

- `bankwiredis/views/templates/front/validation.tpl`
  - **Wyjście:** Ten szablon jest renderowany przez `BankwiredisPaymentModuleFrontController` lub `BankwiredisValidationModuleFrontController` w celu wyświetlenia ostatecznych danych bankowych i instrukcji *przed* pełnym potwierdzeniem zamówienia lub natychmiast po nim, zapewniając dedykowaną stronę z instrukcjami płatności.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł wykorzystuje głównie tabelę `ps_configuration` PrestaShop dla większości swoich ustawień (np. `BANK_WIRE_DIS_OWNER_`, `BDIS_CRON_TOKEN`, `BANK_WIRE_DIS_CHARGEP`).
Dla bardziej złożonych danych, takich jak zasady widoczności rabatów i klienci na czarnej liście, moduł prawdopodobnie tworzy niestandardowe tabele podczas swojej metody `install()`. Na podstawie opcji konfiguracji, te tabele zazwyczaj byłyby:

- `ps_bankwiredis_rules`: Przechowuje definicję każdej reguły rabatowej (nazwa reguły, status aktywności, typ rabatu, wartość, min/max koszyk, waluty, strefy, kraje, grupy klientów, produkty, kategorie).
- `ps_bankwiredis_blacklist`: Przechowuje rekordy klientów na czarnej liście (ID klienta, e-mail, powód, data umieszczenia na czarnej liście).
- `ps_bankwiredis_reminders`: Przechowuje dziennik wysłanych e-maili z przypomnieniami dla każdego zamówienia w celu śledzenia `Max reminders per order`.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Służy do ładowania zasobów CSS i JavaScript front-office (`bankwiredis-checkout.js`) do dynamicznego wyświetlania rabatów. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny ładuje swoje zasoby multimedialne. | Służy do ładowania zasobów CSS i JavaScript back-office (`admin_bankwiredis.css`, `adminBankwiredisAccounts.js`, `autocomplete.js`) dla konfiguracji modułu i stron administracyjnych. |
| `displayPaymentOptions` | Na stronie realizacji zamówienia, gdy wyświetlane są opcje płatności. | Renderuje opcję płatności przelewem bankowym, w tym obliczony rabat, za pomocą `payment.tpl`. |
| `displayPaymentReturn` | Na stronie potwierdzenia zamówienia po pomyślnym złożeniu zamówienia. | Wyświetla dane konta bankowego i instrukcje płatności klientowi za pomocą `payment_return.tpl`. |
| `displayPDFInvoice` | Gdy generowana jest faktura PDF. | Wstrzykuje dane konta bankowego i informacje o rabacie do faktury PDF generowanej dla zamówień przelewem bankowym za pomocą `payment_return_pdf_invoice.tpl`. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Służy do przechwytywania szczegółów zamówienia, stosowania ostatecznego rabatu i potencjalnego logowania zamówienia do przetwarzania przypomnień/anulowań. |
| `displayPaymentInfo` | (Implicitnie) Często używany do wyświetlania dodatkowych informacji o wyborze płatności. | Renderuje `infos.tpl` z ogólnymi informacjami o przelewie bankowym. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie deweloperskie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Upewnij się, że używasz najnowszej kompatybilnej wersji modułu dla swojego sklepu PrestaShop.
