---
title: "Przelew bankowy z podsumowaniem zamówienia - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów dla modułu PrestaShop „Przelew bankowy z podsumowaniem zamówienia” od MyPresta.eu."
sidebar:
  label: "Przelew bankowy z podsumowaniem zamówienia - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Bank wire with order summary na MyPresta.eu](https://mypresta.eu/modules/payment-process/bank-wire-with-order-summary.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/payment/bank-wire-with-order-summary/)
>
> ---


# Przelew bankowy z podsumowaniem zamówienia

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i są zwykle dostępne w większości środowisk hostingowych. Dla tego modułu nie są potrzebne żadne specyficzne, nietypowe rozszerzenia.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji, na którym definiujesz dane swojego konta bankowego i sposób działania metody płatności przelewem bankowym w Twoim sklepie.

#### **Ustawienia konta przelewu bankowego**

Ta sekcja pozwala zdefiniować wiele profili kont bankowych. Każdy profil może mieć własne dane i może być aktywowany lub dezaktywowany niezależnie. Jest to przydatne, jeśli masz różne konta bankowe dla różnych walut, krajów, a nawet różnych marek.

-   **Nazwa profilu:**

    -   **Co robi to ustawienie:** Jest to wewnętrzna nazwa Twojego profilu konta bankowego, pomagająca Ci zidentyfikować go w panelu administracyjnym. Nie jest widoczna dla klientów.
    -   **Skutek zmiany tego ustawienia:** Zmiana wpływa tylko na to, jak widzisz profil w panelu administracyjnym.
    -   **Zalecana wartość:** Opisowa nazwa, np. „Główne konto w EUR”, „Konto w USD dla zamówień z USA”.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz konto bankowe w Niemczech dla płatności w EUR i inne w USA dla płatności w USD, utworzyłbyś dwa profile, nazywając je odpowiednio.
-   **Aktywny:**

    -   **Co robi to ustawienie:** Kontroluje, czy ten konkretny profil konta bankowego jest dostępny jako opcja płatności dla klientów.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Ten profil konta bankowego zostanie zaoferowany klientom, jeśli spełnia wszystkie inne kryteria kwalifikacji (waluta, kraj itp.).
        -   *Gdy wyłączone (Nie):* Ten profil nie będzie wyświetlany jako opcja płatności, niezależnie od innych ustawień.
    -   **Zalecana wartość:** „Tak” dla aktywnych kont, „Nie” dla nieaktywnych lub tymczasowych kont.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz wyłączyć profil, jeśli konto bankowe jest tymczasowo niedostępne lub jeśli wycofujesz określoną walutę.
-   **Priorytet:**

    -   **Co robi to ustawienie:** Jeśli wiele profili przelewów bankowych jest aktywnych i kwalifikuje się do zamówienia klienta, ta liczba określa, który z nich jest wyświetlany jako pierwszy lub preferowany. Niższe liczby oznaczają wyższy priorytet.
    -   **Skutek zmiany tego ustawienia:** Wpływa na kolejność, w jakiej kwalifikujące się opcje przelewu bankowego są prezentowane klientowi.
    -   **Zalecana wartość:** Użyj kolejnych liczb (np. 1, 2, 3), aby uporządkować swoje preferencje.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli wolisz, aby klienci używali Twojego głównego konta w EUR zamiast drugiego, nadaj głównemu kontu niższy numer priorytetu (np. 1) niż drugiemu (np. 2).
-   **Waluta:**

    -   **Co robi to ustawienie:** Określa, w jakiej walucie ten profil konta bankowego jest skonfigurowany do przyjmowania płatności.
    -   **Skutek zmiany tego ustawienia:** Ten profil będzie oferowany tylko klientom, których suma zamówienia jest w wybranej walucie.
    -   **Zalecana wartość:** Wybierz główną walutę dla tego konta bankowego.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz konto bankowe, które akceptuje tylko EUR, wybierz „Euro”. Jeśli klient złoży zamówienie w USD, ten profil nie zostanie wyświetlony.
-   **Kraje kwalifikujące się:**

    -   **Co robi to ustawienie:** Określa, dla których krajów ten profil konta bankowego jest dostępny. Możesz wybrać wiele krajów.
    -   **Skutek zmiany tego ustawienia:** Ten profil będzie oferowany tylko klientom, których adres rozliczeniowy znajduje się w jednym z wybranych krajów.
    -   **Zalecana wartość:** Wybierz wszystkie kraje, z których jesteś gotów przyjmować przelewy bankowe na to konkretne konto.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoje niemieckie konto bankowe jest przeznaczone tylko dla klientów w Niemczech i Austrii, wybierz „Niemcy” i „Austria”.
-   **Strefy kwalifikujące się:**

    -   **Co robi to ustawienie:** Określa, dla których stref geograficznych ten profil konta bankowego jest dostępny. Możesz wybrać wiele stref.
    -   **Skutek zmiany tego ustawienia:** Podobnie jak w przypadku krajów, ten profil będzie oferowany tylko klientom, których adres rozliczeniowy znajduje się w jednej z wybranych stref.
    -   **Zalecana wartość:** Wybierz strefy odpowiednie dla tego konta bankowego.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz konto bankowe specjalnie dla klientów europejskich, możesz wybrać strefę „Europa”.
-   **Kwalifikujące się grupy klientów:**

    -   **Co robi to ustawienie:** Ogranicza tę opcję płatności do określonych grup klientów (np. „Odwiedzający”, „Goście”, „Klienci”, „Hurtownicy”).
    -   **Skutek zmiany tego ustawienia:** Tylko klienci należący do wybranych grup zobaczą tę opcję przelewu bankowego.
    -   **Zalecana wartość:** Zazwyczaj „Klienci” i „Goście”, ale można dostosować dla B2B.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz chcieć oferować przelew bankowy tylko grupie „Hurtownicy” dla dużych zamówień B2B, a nie zwykłym klientom detalicznym.
-   **Posiadacz konta:**

    -   **Co robi to ustawienie:** Pełna nazwa posiadacza konta (nazwa Twojej firmy lub imię i nazwisko) tak, jak pojawia się na koncie bankowym.
    -   **Skutek zmiany tego ustawienia:** Ta informacja jest wyświetlana klientowi na stronie potwierdzenia płatności, aby wiedział, komu przelać pieniądze.
    -   **Zalecana wartość:** Twoja dokładna, prawna nazwa firmy lub imię i nazwisko.
    -   **Scenariusz / przykład dla sprzedawcy:** „MyPresta.eu Sp. z o.o.”
-   **IBAN:**

    -   **Co robi to ustawienie:** Twój Międzynarodowy Numer Rachunku Bankowego. Jest to ustandaryzowany międzynarodowy identyfikator konta bankowego.
    -   **Skutek zmiany tego ustawienia:** Jest to kluczowa informacja wyświetlana klientowi do wykonania przelewu bankowego.
    -   **Zalecana wartość:** Twój pełny i poprawny numer IBAN.
    -   **Scenariusz / przykład dla sprzedawcy:** „DE89370400440532013000”
-   **BIC / SWIFT:**

    -   **Co robi to ustawienie:** Twój Kod Identyfikacyjny Banku (BIC) lub kod SWIFT. Identyfikuje on Twój bank globalnie.
    -   **Skutek zmiany tego ustawienia:** Jest to niezbędna informacja wyświetlana klientowi do wykonywania międzynarodowych przelewów bankowych.
    -   **Zalecana wartość:** Twój pełny i poprawny kod BIC/SWIFT.
    -   **Scenariusz / przykład dla sprzedawcy:** „COBADEFFXXX”
-   **Numer konta / szczegóły:**

    -   **Co robi to ustawienie:** Twój tradycyjny numer konta bankowego lub inne specyficzne dane wymagane przez Twój bank lub kraj, jeśli IBAN/BIC nie są wystarczające lub mają zastosowanie.
    -   **Skutek zmiany tego ustawienia:** Ta informacja jest wyświetlana klientowi.
    -   **Zalecana wartość:** Twój numer konta, jeśli IBAN nie jest używany, lub inne specyficzne dane. Pozostaw puste, jeśli IBAN/BIC są wystarczające.
    -   **Scenariusz / przykład dla sprzedawcy:** W niektórych krajach lokalny numer konta może być nadal preferowany obok lub zamiast IBAN.
-   **Adres banku / posiadacza:**

    -   **Co robi to ustawienie:** Adres Twojego banku lub zarejestrowany adres posiadacza konta.
    -   **Skutek zmiany tego ustawienia:** Ta informacja jest wyświetlana klientowi, czasami wymagana do przelewów bankowych.
    -   **Zalecana wartość:** Pełny adres Twojego oddziału banku lub zarejestrowany adres Twojej firmy.
    -   **Scenariusz / przykład dla sprzedawcy:** „Bank Przykładu, Główna Ulica 123, 10001 Miasto, Kraj”
-   **Dodatkowe instrukcje:**

    -   **Co robi to ustawienie:** Pole tekstowe, w którym możesz podać dodatkowe uwagi dla klienta dotyczące przelewu bankowego (np. „Prosimy o podanie numeru referencyjnego zamówienia w opisie przelewu”, „Płatności zazwyczaj księgowane są w ciągu 1-3 dni roboczych”).
    -   **Skutek zmiany tego ustawienia:** Ten tekst zostanie wyświetlony klientowi na stronie potwierdzenia płatności.
    -   **Zalecana wartość:** Jasne, zwięzłe instrukcje, które pomogą klientom poprawnie wykonać przelew.
    -   **Scenariusz / przykład dla sprzedawcy:** „Ważne: Prosimy o użycie numeru zamówienia # [ORDER\_ID] jako referencji płatności, aby zapewnić szybkie przetworzenie.”

#### **Ograniczenia wartości koszyka**

Te ustawienia pozwalają kontrolować minimalne i maksymalne wartości zamówienia, dla których opcja płatności przelewem bankowym jest dostępna.

-   **Minimalna wartość koszyka:**

    -   **Co robi to ustawienie:** Włącza lub wyłącza ograniczenie minimalnej wartości koszyka dla tej metody płatności.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone:* Pole „Minimalna wartość koszyka” staje się aktywne, a przelew bankowy będzie dostępny tylko dla zamówień powyżej tej wartości.
        -   *Gdy wyłączone:* Nie stosuje się ograniczenia minimalnej wartości koszyka.
    -   **Zalecana wartość:** „Włączone”, jeśli chcesz ustawić minimum, „Wyłączone” w przeciwnym razie.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz to włączyć, jeśli przelewy bankowe są bardziej opłacalne dla większych zamówień lub aby zniechęcić do przelewów bankowych dla bardzo małych zakupów.
-   **Minimalna wartość koszyka:**

    -   **Co robi to ustawienie:** Rzeczywista wartość pieniężna, którą koszyk klienta musi przekroczyć, aby pojawiła się opcja przelewu bankowego.
    -   **Skutek zmiany tego ustawienia:** Jeśli całkowita wartość koszyka klienta jest niższa niż ta wartość, opcja przelewu bankowego nie zostanie wyświetlona.
    -   **Zalecana wartość:** Rozsądne minimum, np. „50.00”.
    -   **Scenariusz / przykład dla sprzedawcy:** Ustaw na „50.00”, jeśli chcesz oferować przelew bankowy tylko dla zamówień o wartości 50 € lub więcej.
-   **Maksymalna wartość koszyka:**

    -   **Co robi to ustawienie:** Włącza lub wyłącza ograniczenie maksymalnej wartości koszyka dla tej metody płatności.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone:* Pole „Maksymalna wartość koszyka” staje się aktywne, a przelew bankowy będzie dostępny tylko dla zamówień poniżej tej wartości.
        -   *Gdy wyłączone:* Nie stosuje się ograniczenia maksymalnej wartości koszyka.
    -   **Zalecana wartość:** „Włączone”, jeśli chcesz ustawić maksimum, „Wyłączone” w przeciwnym razie.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz to włączyć, jeśli preferujesz inne metody płatności (takie jak bezpośrednie negocjacje lub niestandardowe fakturowanie) dla bardzo dużych zamówień.
-   **Maksymalna wartość koszyka:**

    -   **Co robi to ustawienie:** Rzeczywista wartość pieniężna, poniżej której musi znajdować się koszyk klienta, aby pojawiła się opcja przelewu bankowego.
    -   **Skutek zmiany tego ustawienia:** Jeśli całkowita wartość koszyka klienta jest powyżej tej wartości, opcja przelewu bankowego nie zostanie wyświetlona.
    -   **Zalecana wartość:** Rozsądne maksimum, np. „5000.00”.
    -   **Scenariusz / przykład dla sprzedawcy:** Ustaw na „5000.00”, jeśli nie chcesz akceptować przelewów bankowych dla zamówień przekraczających 5000 €.

#### **Wyświetlanie podsumowania zamówienia**

Te ustawienia kontrolują, jakie informacje są wyświetlane klientowi na stronie potwierdzenia płatności, zanim sfinalizuje zamówienie. Jest to kluczowe dla zgodności z przepisami.

-   **Podsumowanie zamówienia przed potwierdzeniem:**

    -   **Co robi to ustawienie:** Kontroluje, czy szczegółowe podsumowanie zamówienia jest wyświetlane klientowi na stronie potwierdzenia płatności.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone:* Zostanie wyświetlone podsumowanie produktów, cen i sum.
        -   *Gdy wyłączone:* Szczegółowe podsumowanie nie zostanie wyświetlone, co potencjalnie wpłynie na zgodność z przepisami w niektórych regionach.
    -   **Zalecana wartość:** „Włączone”, aby zapewnić zgodność z przepisami i przejrzystość dla klienta.
    -   **Scenariusz / przykład dla sprzedawcy:** Zawsze utrzymuj to włączone, aby zapewnić pełną przejrzystość swoim klientom, zanim zobowiążą się do zakupu.
-   **Wyświetl podsumowanie klienta przed potwierdzeniem:**

    -   **Co robi to ustawienie:** Kontroluje, czy podsumowanie adresu rozliczeniowego i wysyłkowego klienta jest wyświetlane na stronie potwierdzenia płatności.
    -   **Skutek zmiany tego ustawienia:**
        -   *Gdy włączone:* Zostaną wyświetlone dane adresowe klienta.
        -   *Gdy wyłączone:* Dane adresowe nie zostaną wyświetlone.
    -   **Zalecana wartość:** „Włączone” dla pełnej przejrzystości.
    -   **Scenariusz / przykład dla sprzedawcy:** Włączenie tej opcji pozwala klientom po raz ostatni sprawdzić informacje o dostawie przed złożeniem zamówienia.

#### **Zaawansowane analizy (wewnętrzne)**

Te ustawienia są zazwyczaj przeznaczone do wewnętrznych analiz i raportowania modułu, nie wpływając bezpośrednio na doświadczenie klienta w front-office.

-   **BANKWIREPRO\_ANALYTICS\_DEFAULT\_CHART, BANKWIREPRO\_ANALYTICS\_PERIOD, BANKWIREPRO\_ANALYTICS\_CHART\_WEEKS, BANKWIREPRO\_ANALYTICS\_CHART\_MONTHS, BANKWIREPRO\_ANALYTICS\_CHART\_YEARS:**
    -   **Co robią te ustawienia:** Są to wewnętrzne wartości konfiguracyjne związane z tym, jak moduł może śledzić lub wyświetlać statystyki płatności w panelu administracyjnym PrestaShop (jeśli taka funkcja jest zaimplementowana). Definiują domyślne typy wykresów, okresy raportowania i ramy czasowe dla analiz.
    -   **Skutek zmiany tych ustawień:** Nie wpływają one na proces płatności widoczny dla klienta. Mogą wpływać na sposób prezentacji danych w wewnętrznym panelu analitycznym, jeśli jest dostępny.
    -   **Zalecana wartość:** Pozostaw jako domyślne, chyba że obsługa techniczna zaleci inaczej.
    -   **Scenariusz / przykład dla sprzedawcy:** Nie ma bezpośredniego zastosowania do podejmowania decyzji przez sprzedawcę w zakresie przetwarzania płatności.

#### **Ustawienia języka (wewnętrzne)**

-   **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG:**

    -   **Co robią te ustawienia:** Są to standardowe zmienne konfiguracyjne PrestaShop, które określają domyślny język Twojego sklepu i to, czy pracownicy mogą zmieniać język formularzy w panelu administracyjnym. Są one wyświetlane tutaj w celach informacyjnych, ale nie są specyficzne dla tego modułu.
    -   **Skutek zmiany tych ustawień:** Zmiany w tych ustawieniach byłyby dokonywane w ogólnych ustawieniach PrestaShop, a nie tutaj. Wpływają one na domyślny język pól tekstowych w panelu administracyjnym.
    -   **Zalecana wartość:** Domyślny język Twojego sklepu.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli głównym językiem Twojego sklepu jest angielski, `PS_LANG_DEFAULT` byłoby ustawione na ID języka angielskiego.
-   **PS\_CURRENCY\_DEFAULT:**

    -   **Co robi to ustawienie:** Jest to domyślna waluta Twojego sklepu PrestaShop. Jest wyświetlana tutaj w celach informacyjnych.
    -   **Skutek zmiany tego ustawienia:** Jest to globalne ustawienie PrestaShop. Zmiana wpłynęłaby na wszystkie ceny i wyświetlanie walut w całym Twoim sklepie.
    -   **Zalecana wartość:** Główna waluta operacyjna Twojego sklepu.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój sklep handluje głównie w euro, to ustawienie byłoby ustawione na „Euro”.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Nazwa profilu | Opisowa nazwa | Wewnętrzna identyfikacja konta bankowego. |
| Konfiguracja modułu | Aktywny | Tak | Włącza/wyłącza ten profil konta bankowego do użytku przez klienta. |
| Konfiguracja modułu | Priorytet | 1 (lub sekwencyjny) | Porządkuje wyświetlanie wielu kwalifikujących się opcji przelewu bankowego. |
| Konfiguracja modułu | Waluta | Waluta Twojego sklepu | Ogranicza profil do zamówień w tej walucie. |
| Konfiguracja modułu | Kraje kwalifikujące się | Wszystkie kraje | Ogranicza profil do klientów z wybranych krajów. |
| Konfiguracja modułu | Strefy kwalifikujące się | Wszystkie strefy | Ogranicza profil do klientów z wybranych stref. |
| Konfiguracja modułu | Kwalifikujące się grupy klientów | Wszystkie grupy | Ogranicza profil do wybranych grup klientów. |
| Konfiguracja modułu | Posiadacz konta | Twoja firma/nazwa | Wyświetla się klientowi do przelewu bankowego. |
| Konfiguracja modułu | IBAN | Twój IBAN | Wyświetla się klientowi do przelewu bankowego. |
| Konfiguracja modułu | BIC / SWIFT | Twój BIC/SWIFT | Wyświetla się klientowi do międzynarodowego przelewu bankowego. |
| Konfiguracja modułu | Numer konta / szczegóły | (Opcjonalnie) | Dodatkowe dane bankowe dla klienta. |
| Konfiguracja modułu | Adres banku / posiadacza | Adres Twojego banku/firmy | Wyświetla się klientowi do przelewu bankowego. |
| Konfiguracja modułu | Dodatkowe instrukcje | Jasne instrukcje | Dodatkowe uwagi dla klienta (np. numer referencyjny). |
| Konfiguracja modułu | Minimalna wartość koszyka | Wyłączone | Włącza/wyłącza ograniczenie minimalnej wartości zamówienia. |
| Konfiguracja modułu | Minimalna wartość koszyka | 0.00 | Minimalna wartość zamówienia, dla której przelew bankowy jest dostępny. |
| Konfiguracja modułu | Maksymalna wartość koszyka | Wyłączone | Włącza/wyłącza ograniczenie maksymalnej wartości zamówienia. |
| Konfiguracja modułu | Maksymalna wartość koszyka | 0.00 | Maksymalna wartość zamówienia, dla której przelew bankowy jest dostępny. |
| Konfiguracja modułu | Podsumowanie zamówienia przed potwierdzeniem | Włączone | Wyświetla szczegółowe podsumowanie produktów na stronie potwierdzenia. |
| Konfiguracja modułu | Wyświetl podsumowanie klienta przed potwierdzeniem | Włączone | Wyświetla podsumowanie adresu klienta na stronie potwierdzenia. |
| Konfiguracja modułu | BANKWIREPRO\_ANALYTICS\_\* | Domyślne | Wewnętrzne ustawienia analityczne (bez wpływu na front-office). |
| Konfiguracja modułu | PS\_LANG\_DEFAULT | Domyślne sklepu | Domyślne ustawienie języka PrestaShop. |
| Konfiguracja modułu | PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG | Domyślne sklepu | Ustawienie języka formularzy dla pracowników PrestaShop. |
| Konfiguracja modułu | PS\_CURRENCY\_DEFAULT | Domyślne sklepu | Domyślne ustawienie waluty PrestaShop. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Dlaczego opcja przelewu bankowego nie wyświetla się moim klientom?**
O1: Sprawdź następujące ustawienia w konfiguracji modułu:
\* Przełącznik **„Aktywny”** dla profilu konta bankowego: Upewnij się, że jest ustawiony na „Tak”.
\* **„Waluta”**: Czy waluta zamówienia klienta odpowiada walucie profilu?
\* **„Kraje kwalifikujące się” / „Strefy kwalifikujące się”**: Czy kraj/strefa adresu rozliczeniowego klienta jest uwzględniona?
\* **„Kwalifikujące się grupy klientów”**: Czy grupa klienta może korzystać z tej metody płatności?
\* **„Minimalna wartość koszyka” / „Maksymalna wartość koszyka”**: Czy wartość koszyka klienta mieści się w dozwolonym zakresie?
\* **Pamięć podręczna PrestaShop**: Czasami wyczyszczenie pamięci podręcznej Smarty (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) może rozwiązać problemy z wyświetlaniem.

**P2: Moje dane bankowe są niepoprawne lub nieaktualne. Jak je zmienić?**
O2: Przejdź do **Moduły > Menedżer modułów**, znajdź „Przelew bankowy z podsumowaniem zamówienia” i kliknij „Konfiguruj”. Zobaczysz swoje istniejące profile kont bankowych. Kliknij przycisk „Edytuj” (ikona ołówka) obok profilu, który chcesz zaktualizować, zmodyfikuj pola „Posiadacz konta”, „IBAN”, „BIC / SWIFT” itp., a następnie zapisz zmiany.

**P3: Podsumowanie zamówienia nie wyświetla się na stronie potwierdzenia. Czy coś jest nie tak?**
O3: Upewnij się, że ustawienia „Podsumowanie zamówienia przed potwierdzeniem” i „Wyświetl podsumowanie klienta przed potwierdzeniem” są ustawione na „Włączone” w konfiguracji modułu. Jeśli tak jest i wyczyściłeś pamięć podręczną PrestaShop, może występować konflikt z motywem. Przetestuj z domyślnym motywem PrestaShop, aby to wykluczyć.

**P4: Czy mogę oferować różne konta bankowe dla różnych typów klientów lub produktów?**
O4: Tak, absolutnie! Ten moduł obsługuje wiele profili kont bankowych. Możesz tworzyć oddzielne profile i używać ustawień „Kwalifikujące się grupy klientów”, „Waluta”, „Kraje kwalifikujące się” i „Wartość koszyka”, aby określić, kiedy oferowane jest każde konkretne konto bankowe. Na przykład, jedno konto dla klientów detalicznych w EUR, inne dla klientów hurtowych w USD.

**P5: Po aktualizacji mojego motywu lub PrestaShop strona przelewu bankowego wygląda dziwnie. Co powinienem zrobić?**
O5: Często wskazuje to na konflikt CSS lub problem z nadpisaniem szablonu.
1.  **Wyczyść pamięć podręczną:** Zawsze zaczynaj od wyczyszczenia pamięci podręcznej PrestaShop (Zaawansowane > Wydajność).
2.  **Sprawdź aktualizacje modułu:** Upewnij się, że masz najnowszą wersję modułu „Przelew bankowy z podsumowaniem zamówienia” z MyPresta.eu, ponieważ aktualizacje często zawierają poprawki kompatybilności.
3.  **Konflikt motywu:** Jeśli problem nadal występuje, tymczasowo przełącz się na domyślny motyw PrestaShop (np. „Classic”), aby sprawdzić, czy problem zniknie. Jeśli tak, Twój niestandardowy motyw prawdopodobnie nadpisuje lub koliduje ze stylami lub szablonami modułu. Może być konieczne skonsultowanie się z twórcą motywu lub webmasterem w celu dostosowania plików CSS lub szablonów motywu.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla deweloperów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `bankwirepro` jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując `ModuleFrontController` do interakcji z front-office i główną klasę `Module` do konfiguracji. Integruje się z procesem realizacji zamówienia za pomocą hooków płatności (`displayPaymentOptions`, `paymentOptions`, `displayPaymentReturn`). Konfiguracja jest zarządzana za pomocą wpisów w tabeli `Configuration`, a dane konta bankowego są przechowywane jako serializowane tablice lub indywidualne klucze `Configuration`, co pozwala na wiele profili. Główną funkcją modułu jest prezentowanie danych bankowych i podsumowania zamówienia klientowi przed i po walidacji zamówienia.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:
    -   `controllers/front/index.php`
        -   **Nazwa klasy**: `BankwireproIndexModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność**: Ten kontroler prawdopodobnie służy jako domyślny punkt wejścia lub rezerwowy. W wielu modułach kontrolery `index.php` przekierowują do bardziej specyficznego kontrolera lub obsługują podstawowe wyświetlanie modułu, jeśli nie jest wymagana żadna inna konkretna akcja. Może obsługiwać początkową konfigurację lub przekierowanie do wyboru płatności.
    -   `controllers/front/payment.php`
        -   **Nazwa klasy**: `BankwireproPaymentModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność**: Ten kontroler jest odpowiedzialny za renderowanie strony wyboru płatności, gdy wybrana zostanie opcja przelewu bankowego. Gromadzi niezbędne dane konta bankowego w oparciu o bieżący koszyk, klienta i walutę, a następnie przygotowuje je do wyświetlenia w szablonie `payment.tpl`. Działa jako pomost między wyborem opcji płatności a końcowym krokiem walidacji.
    -   `controllers/front/validation.php`
        -   **Nazwa klasy**: `BankwireproValidationModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność**: Jest to krytyczny kontroler, który obsługuje ostatni krok procesu płatności przelewem bankowym. Waliduje zamówienie, tworzy zamówienie w bazie danych PrestaShop, a następnie renderuje szablon `validation.tpl`. Ten szablon wyświetla pełne podsumowanie zamówienia, podsumowanie adresu klienta i wybrane dane konta bankowego, wraz z dodatkowymi instrukcjami, zanim klient zostanie przekierowany na standardową stronę `order-confirmation`. Zapewnia to, że wszystkie niezbędne informacje są prezentowane w celu zapewnienia zgodności z przepisami.

### 4.3 Klasy i modele podstawowe (`classes/`)

Dossier modułu nie wskazuje na żadne niestandardowe klasy w `classes/`. Podstawowa logika obsługi profili kont bankowych i konfiguracji jest prawdopodobnie zawarta w głównym pliku `bankwirepro.php`, wykorzystując `Configuration::get()` i `Configuration::updateValue()` do przechowywania ustawień, potencjalnie z serializowanymi tablicami dla wielu profili kont bankowych.

### 4.4 Zasoby JavaScript (`views/js/`)

Dossier modułu nie wskazuje na żadne niestandardowe pliki JavaScript. Sugeruje to, że funkcjonalność front-office modułu jest głównie renderowana po stronie serwera i opiera się na standardowym JavaScript PrestaShop do podstawowych interakcji, lub że wszelkie minimalne JS są wbudowane w szablony.

### 4.5 Arkusze stylów CSS (`views/css/`)

Dossier modułu nie wskazuje na żadne niestandardowe pliki CSS. Oznacza to, że moduł opiera się całkowicie na stylach domyślnego motywu PrestaShop, lub że wszelkie minimalne style są wbudowane w szablony. Deweloperzy powinni być świadomi, że wygląd modułu będzie w dużej mierze dyktowany przez CSS aktywnego motywu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `accountSelector.tpl`: Ten szablon jest prawdopodobnie używany w konfiguracji panelu administracyjnego modułu do wyświetlania listy skonfigurowanych profili kont bankowych, umożliwiając administratorowi ich wybór, edycję lub usunięcie. Zazwyczaj renderowałby tabelę lub listę z nazwami profili, statusem i przyciskami akcji.
-   **Szablony front-office (`views/templates/front/`)**:

    -   `validation.tpl`: Jest to kluczowy szablon renderowany przez `BankwireproValidationModuleFrontController`. Wyświetla on kompleksowe podsumowanie zamówienia (produkty, sumy), podsumowanie adresu klienta i wybrane dane konta bankowego (posiadacz konta, IBAN, BIC/SWIFT, instrukcje) klientowi przed pełnym potwierdzeniem zamówienia. Ten szablon jest kluczowy dla zgodności z przepisami.
-   **Szablony hooków (`views/templates/hook/`)**:

    -   `infos.tpl`: Ten szablon jest prawdopodobnie podłączony do `displayPaymentReturn` lub podobnego hooka na stronie `order-confirmation`. Powtarza instrukcje płatności przelewem bankowym i dane bankowe po pomyślnym złożeniu zamówienia, służąc jako przypomnienie dla klienta o konieczności dokonania przelewu.
    -   `payment.tpl`: Ten szablon jest prawdopodobnie używany dla hooka `displayPayment` (PrestaShop 1.6.x) lub `paymentOptions` (PrestaShop 1.7+). Renderuje on samą opcję przelewu bankowego na stronie wyboru płatności podczas realizacji zamówienia, prezentując ją jako dostępną metodę płatności dla klienta.
    -   `payment_return.tpl`: Podobnie jak `infos.tpl`, ten szablon jest również prawdopodobnie podłączony do `displayPaymentReturn`. Zapewnia ostateczną wiadomość potwierdzającą i dane bankowe na stronie potwierdzenia zamówienia, zapewniając klientowi wszystkie informacje do kontynuowania przelewu bankowego.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy niestandardowych tabel SQL. Wszystkie ustawienia konfiguracyjne, w tym wiele profili kont bankowych, są przechowywane w tabeli `ps_configuration`.
    -   Używane klucze konfiguracyjne:
        -   `BANK_WIRE_PRO_MINCART`, `BANK_WIRE_PRO_MINCART_V`, `BANK_WIRE_PRO_MAXCART`, `BANK_WIRE_PRO_MAXCART_V`: Dla ograniczeń wartości koszyka.
        -   `BANK_WIRE_PRO_OWNER_`, `BANK_WIRE_PRO_DETAILS_`, `BANK_WIRE_PRO_ADDRESS_`, `BANK_WIRE_PRO_SWIFT_`, `BANK_WIRE_PRO_IBAN_`, `BANK_WIRE_PRO_MORE_`: Są to prawdopodobnie prefiksy do przechowywania szczegółów *każdego* profilu konta bankowego, prawdopodobnie z sufiksem ID języka lub ID profilu (np. `BANK_WIRE_PRO_OWNER_1_1` dla profilu 1, języka 1).
        -   `BANK_WIRE_PRO_OWNER_SUMMARY`, `BANK_WIRE_PRO_CSUMMARY`, `BANK_WIRE_PRO_ASUMMARY`: Do kontrolowania wyświetlania podsumowań zamówień i adresów.
        -   `BANKWIREPRO_ANALYTICS_*`: Wewnętrzne ustawienia analityczne.
        -   Standardowe klucze PrestaShop, takie jak `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `PS_CURRENCY_DEFAULT`, są odczytywane, ale nie zarządzane przez moduł.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Zakres | Czas wykonania | Cel techniczny |
| --- | --- | --- | --- |
| `displayPayment` | Front-Office | Krok wyboru płatności (PrestaShop 1.6.x) | Renderuje opcję płatności przelewem bankowym na stronie realizacji zamówienia. |
| `paymentOptions` | Front-Office | Krok wyboru płatności (PrestaShop 1.7.x, 8.x, 9.x) | Dostarcza obiekty `PaymentOption` dla przelewu bankowego na stronę realizacji zamówienia. |
| `displayPaymentReturn` | Front-Office | Strona potwierdzenia zamówienia (`order-confirmation`) | Wyświetla dane bankowe i instrukcje po walidacji zamówienia. |
| `displayPaymentOptions` | Front-Office | Krok wyboru płatności (PrestaShop 1.7.x, 8.x, 9.x) | Alternatywny lub uzupełniający hook do renderowania opcji płatności. |
| `actionPaymentConfirmation` | Panel administracyjny | Po potwierdzeniu, że zamówienie zostało opłacone | (Domniemane, typowe dla modułów płatności) Może aktualizować status zamówienia lub wykonywać działania po płatności. |
| `actionValidateOrder` | Panel administracyjny | Po walidacji zamówienia | (Domniemane, typowe dla modułów płatności) Używane do ustawiania początkowego statusu zamówienia, zapisywania szczegółów płatności. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i upewnienia się, że używasz najbardziej bezpiecznej i kompatybilnej wersji modułu „Przelew bankowy z podsumowaniem zamówienia”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
