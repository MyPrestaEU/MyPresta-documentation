---
title: "Minimalna wartość zamówienia według grupy klientów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop „Minimalna wartość zamówienia według grupy klientów” od MyPresta.eu."
sidebar:
  label: "Minimalna wartość zamówienia według grupy klientów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Minimum order value by customer group na MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimum-order-value-by-customer-group.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/minimum-order-value-by-customer-group/)
>
> ---


# Minimalna wartość zamówienia według grupy klientów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji, na którym definiujesz minimalne wartości zamówień dla każdej grupy klientów.

#### Ustawienia ogólne

- **Wyklucz określone grupy klientów z reguły minimalnej wartości zamówienia:**

  - **Co robi to ustawienie:** Pozwala to wybrać grupy klientów, które *nie* będą podlegać żadnej minimalnej wartości zamówienia, nawet jeśli ustawiłeś dla nich taką wartość poniżej. Zawsze mogą zrealizować zamówienie niezależnie od sumy ich koszyka.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (wybrane grupy):* Klienci należący do wybranych grup ominą wszystkie kontrole minimalnej wartości zamówienia.
    - *Gdy wyłączone (nie wybrano grup):* Wszystkie grupy klientów będą podlegać minimalnym wartościom zamówień, które zdefiniujesz.
  - **Zalecana wartość:** Zależy od Twojego modelu biznesowego. Jeśli masz VIP-ów lub konkretnych klientów B2C, których chcesz zwolnić, wybierz ich tutaj. W przeciwnym razie pozostaw puste.
  - **Scenariusz / przykład dla sprzedawcy:** Masz grupę „Klientów VIP”, którzy zawsze mają mieć możliwość realizacji zamówienia, nawet jeśli ich zamówienie jest małe. Wybierz tutaj „Klienci VIP”.
- **Uwzględnij podatek w minimalnej wartości zamówienia:**

  - **Co robi to ustawienie:** Określa, czy ustawiona minimalna wartość zamówienia powinna obejmować, czy wykluczać kwotę podatku obliczoną dla produktów w koszyku.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (TAK):* Moduł sprawdzi sumę koszyka *łącznie z* podatkami w stosunku do zdefiniowanego minimum.
    - *Gdy wyłączone (NIE):* Moduł sprawdzi sumę koszyka *bez* podatków w stosunku do zdefiniowanego minimum.
  - **Zalecana wartość:** „TAK” dla większości sklepów B2C, ponieważ klienci zazwyczaj widzą i płacą całkowitą cenę wraz z podatkiem. „NIE” może być preferowane dla sklepów B2B, gdzie ceny są często podawane bez podatku.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli ustawisz minimum 100 USD i to jest włączone, suma koszyka 90 USD (bez podatku) + 10 USD (podatek) = 100 USD zostanie zaakceptowana. Jeśli wyłączone, ten sam koszyk zostanie odrzucony, ponieważ 90 USD jest mniej niż 100 USD.
- **Uwzględnij koszt wysyłki w minimalnej wartości zamówienia:**

  - **Co robi to ustawienie:** Określa, czy koszt wysyłki zamówienia powinien zostać dodany do sumy koszyka przed sprawdzeniem w stosunku do minimalnej wartości zamówienia.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (TAK):* Moduł sprawdzi (Suma koszyka + Koszt wysyłki) w stosunku do zdefiniowanego minimum.
    - *Gdy wyłączone (NIE):* Moduł sprawdzi tylko Sumę koszyka (produktów) w stosunku do zdefiniowanego minimum.
  - **Zalecana wartość:** „NIE” w większości przypadków, ponieważ minima zazwyczaj dotyczą wartości produktów. Jednak jeśli koszty wysyłki są bardzo wysokie i chcesz zapewnić określoną całkowitą wartość transakcji, możesz to włączyć.
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby klienci kupili produkty o wartości co najmniej 50 USD. Jeśli to jest „NIE”, koszyk z produktami za 50 USD przechodzi. Jeśli to jest „TAK” i wysyłka kosztuje 10 USD, klient potrzebowałby produktów za 50 USD + 10 USD wysyłki = 60 USD łącznie, aby przejść, co oznacza, że potrzebowałby produktów za 60 USD, aby spełnić minimum 50 USD. To ustawienie jest zazwyczaj „NIE”, aby uniknąć zamieszania.
- **Zastosuj minimalną wartość zamówienia tylko dla pierwszego zamówienia:**

  - **Co robi to ustawienie:** Jeśli włączone, zasady minimalnej wartości zamówienia będą obowiązywać tylko dla pierwszego zamówienia klienta w Twoim sklepie. Kolejne zamówienia nie będą podlegać minimom.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (TAK):* Tylko nowi klienci (ci, którzy wcześniej nie złożyli zamówienia) będą podlegać ograniczeniom minimalnej wartości zamówienia.
    - *Gdy wyłączone (NIE):* Wszystkie zamówienia, niezależnie od tego, czy są pierwszym, czy dziesiątym zamówieniem klienta, zostaną sprawdzone pod kątem minimalnej wartości zamówienia.
  - **Zalecana wartość:** „NIE” dla większości scenariuszy, w których chcesz mieć spójne minima. „TAK” może być przydatne do zachęcania do początkowych większych zakupów od nowych klientów, a następnie łagodzenia zasad dla powtarzających się transakcji.
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby nowi klienci B2B złożyli znaczące pierwsze zamówienie o wartości 500 USD, aby założyć swoje konto, ale potem mogą zamawiać dowolną kwotę. Włącz to i ustaw minimum 500 USD dla swojej grupy B2B.

#### Minimalne wartości zamówień według grupy klientów

Poniżej ustawień ogólnych znajdziesz listę wszystkich swoich grup klientów. Dla każdej grupy możesz zdefiniować minimalną wartość zamówienia.

- **Nazwa grupy klientów (np. „Gość”, „Odwiedzający”, „Klient”, „Hurtownik”):**
  - **Co robi to ustawienie:** Tutaj wprowadzasz konkretną minimalną kwotę zamówienia wymaganą dla klientów należących do tej konkretnej grupy.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy wprowadzono wartość (np. 50.00):* Klienci w tej grupie muszą mieć sumę koszyka równą lub większą od tej wartości, aby przejść do kasy.
    - *Gdy pozostawiono puste lub ustawiono na 0.00:* Nie ma minimalnej wartości zamówienia dla tej grupy klientów. Mogą zrealizować zamówienie z dowolną sumą koszyka.
  - **Zalecana wartość:** Ustaw wartość, która ma sens biznesowy dla każdej grupy. Pozostaw puste dla grup takich jak „Odwiedzający” lub „Gość”, chyba że wyraźnie chcesz zablokować im składanie zamówień.
  - **Scenariusz / przykład dla sprzedawcy:**
    - Dla grupy „Klient”: Ustaw na `25.00`, aby zachęcić do nieco większych zakupów detalicznych.
    - Dla grupy „Hurtownik”: Ustaw na `200.00`, aby zapewnić rentowność zamówień B2B.
    - Dla grupy „Gość”: Pozostaw puste (`0.00`), aby umożliwić szybkie zakupy bez rejestracji.

#### Uwagi dotyczące wielu sklepów i wielu walut

- **Wiele sklepów:** Jeśli masz włączonych wiele sklepów, zobaczysz rozwijaną listę na górze strony konfiguracji (zazwyczaj obok przycisku „Zapisz”), umożliwiającą wybranie sklepu, który konfigurujesz. Minimalne wartości zamówień można ustawić niezależnie dla każdego sklepu.
- **Wiele walut:** Wprowadzane minimalne wartości zamówień są zawsze w *domyślnej walucie* Twojego sklepu PrestaShop. Moduł automatycznie konwertuje te wartości na wybraną walutę klienta po bieżącym kursie wymiany podczas sprawdzania sumy koszyka.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyklucz określone grupy klientów | Puste | Wybierz grupy, aby ominąć zasady minimalnego zamówienia. |
| Konfiguracja modułu | Uwzględnij podatek w minimalnej wartości zamówienia | TAK | Określa, czy podatek jest częścią minimalnej sumy. |
| Konfiguracja modułu | Uwzględnij koszt wysyłki w minimalnej wartości zamówienia | NIE | Określa, czy wysyłka jest częścią minimalnej sumy. |
| Konfiguracja modułu | Zastosuj minimalną wartość zamówienia tylko dla pierwszego zamówienia | NIE | Stosuje minima tylko do początkowego zakupu klienta. |
| Konfiguracja modułu | Minimalna wartość zamówienia dla [Nazwa grupy klientów] | 0.00 (puste) | Ustaw wymaganą sumę koszyka dla każdej grupy klientów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moi klienci widzą komunikat o minimalnym zamówieniu, mimo że suma ich koszyka wydaje się prawidłowa. Co jest nie tak?**
O:

1. **Sprawdź ustawienia podatku/wysyłki:** Sprawdź dwukrotnie, czy włączone są opcje „Uwzględnij podatek w minimalnej wartości zamówienia” lub „Uwzględnij koszt wysyłki w minimalnej wartości zamówienia”. Wyświetlana suma koszyka może różnić się od wartości, którą sprawdza moduł.
2. **Konwersja walut:** Jeśli działasz w wielu walutach, upewnij się, że kursy wymiany są aktualne. Moduł konwertuje Twoje minimalne wartości w domyślnej walucie na wybraną walutę klienta.
3. **Przypisanie do grupy klientów:** Sprawdź, czy klient jest prawidłowo przypisany do zamierzonej grupy klientów i czy minimalna wartość dla tej grupy jest ustawiona zgodnie z oczekiwaniami.
4. **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stare dane z pamięci podręcznej mogą powodować problemy.

**P: Ustawiłem minimum, ale konkretna grupa klientów nadal może zrealizować zamówienie z dowolną kwotą. Dlaczego?**
O: Sprawdź ustawienie „Wyklucz określone grupy klientów z reguły minimalnej wartości zamówienia” na stronie konfiguracji modułu. Jeśli ta grupa klientów jest tam wybrana, ominą wszystkie kontrole minimalnego zamówienia. Usuń ich z tej listy wykluczeń, jeśli chcesz, aby minimum obowiązywało.

**P: Komunikat modułu nie wyświetla się lub wygląda dziwnie na moim niestandardowym motywie.**
O:

1. **Kompatybilność motywu:** Niestandardowe motywy mogą nadpisywać standardowe szablony PrestaShop lub CSS, potencjalnie wpływając na sposób wyświetlania komunikatów modułu.
2. **Konflikty CSS:** Inny moduł lub CSS Twojego motywu może kolidować ze stylami modułu.
3. **Pamięć podręczna Smarty:** Wyczyść pamięć podręczną Smarty (Zaawansowane > Wydajność > Wyczyść pamięć podręczną), aby upewnić się, że używane są najnowsze pliki szablonów.
   W przypadku problemów wizualnych może być konieczne skonsultowanie się z programistą stron internetowych w celu sprawdzenia plików CSS i szablonów Twojego motywu.

**P: Czy mogę ustawić różne minima dla różnych produktów?**
O: Nie, ten moduł ustawia minimum dla *całkowitej wartości koszyka* na podstawie grupy klientów, a nie dla poszczególnych produktów. Jeśli potrzebujesz minimów dla konkretnych produktów, będziesz potrzebować innego typu modułu.

**P: Jak ten moduł obsługuje konfiguracje wielu sklepów?**
O: Moduł jest przyjazny dla wielu sklepów. Podczas konfiguracji użyj selektora „Kontekst sklepu” na górze panelu administracyjnego PrestaShop (zazwyczaj obok przycisku „Zapisz”), aby przełączać się między swoimi sklepami. Możesz wtedy ustawić unikalne minimalne wartości zamówień dla każdej grupy klientów, dla każdego sklepu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Minimalna wartość zamówienia według grupy klientów” (`cgma`) jest zbudowany zgodnie ze standardową architekturą modułów PrestaShop. Wykorzystuje głównie hooki do wstrzykiwania swojej logiki do procesu koszyka i realizacji zamówienia w front-office. Konfiguracja jest zarządzana za pomocą metody `getContent()` głównej klasy modułu, przechowując ustawienia w `ps_configuration`. Interakcja z front-office jest obsługiwana przez dedykowany kontroler AJAX do walidacji koszyka w czasie rzeczywistym.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:

  - `cgma/controllers/front/ajax.php`
    - **Nazwa klasy:** `CgmaAjaxModuleFrontController` (rozszerza `ModuleFrontController`)
    - **Odpowiedzialność:** Ten kontroler obsługuje żądania AJAX z front-office, głównie do walidacji w czasie rzeczywistym sumy koszyka w stosunku do minimalnej wartości zamówienia dla grupy klientów. Prawdopodobnie zwraca odpowiedź JSON wskazującą, czy koszyk spełnia wymagania i potencjalnie wiadomość do wyświetlenia użytkownikowi. Jest to kluczowe dla dynamicznych aktualizacji bez pełnego przeładowania strony.
  - `cgma/controllers/front/index.php`
    - **Nazwa klasy:** `CgmaIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    - **Odpowiedzialność:** Jest to kontroler zastępczy lub awaryjny. W wielu modułach, jeśli konkretna akcja nie jest zdefiniowana, żądania mogą trafiać do kontrolera `index`. Może być również używany do prostych przekierowań lub do zapewnienia istnienia prawidłowej trasy modułu, chociaż jego główna funkcja w tym module jest prawdopodobnie minimalna w porównaniu do `ajax.php`.
- **Kontrolery administracyjne Back-Office**:

  - Brak jawnie zdefiniowanych w inwentarzu. Cała konfiguracja back-office jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

- Brak niestandardowych klas lub definicji `ObjectModel` jawnie wymienionych w inwentarzu. Moduł prawdopodobnie opiera się na podstawowych klasach PrestaShop `Customer`, `Group`, `Cart` i `Configuration` dla swojej funkcjonalności. Wartości konfiguracyjne są przechowywane bezpośrednio w tabeli `ps_configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

- `cgma/views/js/cgma.js`
  - **Zakres:** Front-office.
  - **Szczegóły:** Ten skrypt jest odpowiedzialny za interakcję i walidację po stronie klienta. Prawdopodobnie nasłuchuje zmian w koszyku (np. aktualizacje ilości, usuwanie produktów) lub prób przejścia do kasy. Następnie wywołuje wywołania AJAX do `cgma/controllers/front/ajax.php` w celu walidacji sumy koszyka w stosunku do minimalnej wartości zamówienia. Po otrzymaniu odpowiedzi dynamicznie aktualizuje podsumowanie koszyka lub przyciski kasy, wyświetlając komunikaty użytkownikowi, jeśli minimum nie jest spełnione i potencjalnie wyłączając przycisk „Przejdź do kasy”. Może również obsługiwać wyświetlanie komunikatu o minimalnej wartości zamówienia w różnych miejscach front-office.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `cgma/css.css`

  - **Zakres:** Prawdopodobnie front-office.
  - **Szczegóły:** Ten arkusz stylów zapewnia podstawowe style dla komunikatów lub elementów modułu w front-office, takich jak komunikat ostrzegawczy wyświetlany, gdy minimalna wartość zamówienia nie jest spełniona.
  - **Kluczowe selektory klas CSS:** Programiści powinni sprawdzić ten plik pod kątem klas takich jak `.cgma-warning-message`, `.cgma-disabled-button` lub podobnych, które można nadpisać w niestandardowym motywie.
- `cgma/views/css/cgma.css`

  - **Zakres:** Prawdopodobnie front-office.
  - **Szczegóły:** Podobnie jak `cgma/css.css`, ten plik zapewnia dodatkowe lub bardziej specyficzne style dla komponentów modułu w front-office. Może zawierać responsywne dostosowania lub specyficzne reguły układu.
  - **Kluczowe selektory klas CSS:** Sprawdź selektory związane z podsumowaniem koszyka, przyciskami kasy lub konkretnymi kontenerami komunikatów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:

  - Brak jawnie wymienionych w inwentarzu, ale implementacja hooka `displayShoppingCart` modułu prawdopodobnie renderowałaby szablon. Możliwe, że `displayShoppingCart.tpl` znajduje się bezpośrednio w `views/templates/front/` i jest używany przez hook.
- **Szablony administracyjne (`views/templates/admin/`)**:

  - `cgma/admin.tpl`
    - **Zakres:** Konfiguracja back-office.
    - **Szczegóły:** Ten szablon jest renderowany przez metodę `getContent()` głównej klasy modułu (`cgma.php`). Zawiera strukturę HTML dla formularza konfiguracji modułu, w tym pola wejściowe dla ustawień ogólnych (wykluczanie grup, uwzględnianie podatku/wysyłki, tylko pierwsze zamówienie) oraz dynamiczne pola do ustawiania minimalnych wartości zamówień dla każdej grupy klientów.
- **Szablony front-office (`views/templates/front/`)**:

  - `cgma/views/templates/front/displayShoppingCart.tpl`
    - **Zakres:** Front-office, w szczególności strona koszyka.
    - **Szczegóły:** Ten szablon jest prawdopodobnie renderowany, gdy moduł jest podłączony do `displayShoppingCart`. Wyświetla komunikat ostrzegawczy dla klienta, jeśli suma jego koszyka nie spełnia minimalnej wartości zamówienia dla jego grupy. Może również zawierać logikę do wyłączania przycisku „Przejdź do kasy” lub dostarczania instrukcji, jak spełnić minimum.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy niestandardowych tabel SQL.
  - Ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `CGMA_EXCV`, `CGMA_TAX`, `CGMA_FREE`, `CGMA_FIRST_ORDER` i `CGMA_[GROUP_ID]_[CURRENCY_ID]` dla minimalnych wartości na grupę i walutę. Odwołuje się również do `PS_CURRENCY_DEFAULT`.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `stepBeforePaymentOPC` | Przed krokiem płatności w One-Page Checkout. | Zapobiega przejściu klientów do płatności, jeśli minimalna wartość zamówienia nie jest spełniona. |
| `displayPaymentTop` | Na górze sekcji opcji płatności podczas realizacji zamówienia. | Wyświetla komunikat ostrzegawczy, jeśli minimalna wartość zamówienia nie jest spełniona. |
| `displaystepBeforePaymentOPC` | Podobnie jak `stepBeforePaymentOPC`, często używany do wyświetlania treści lub dodatkowych kontroli. | Zapewnia spełnienie minimalnej wartości zamówienia przed płatnością, potencjalnie wyświetlając komunikat. |
| `displayShoppingCart` | Na stronie podsumowania koszyka. | Waliduje sumę koszyka i wyświetla komunikat ostrzegawczy, jeśli minimum nie jest spełnione, potencjalnie wyłączając przyciski kasy. |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Wstrzykuje niezbędne pliki CSS (`cgma.css`) i JavaScript (`cgma.js`) dla funkcjonalności i stylizacji front-office. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dostępu do najnowszych wersji modułu „Minimalna wartość zamówienia według grupy klientów”, odwiedź swoje konto klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
