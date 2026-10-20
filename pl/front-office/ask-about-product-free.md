---
title: "Zapytaj o produkt za darmo - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Zapytaj o produkt za darmo” od MyPresta.eu."
sidebar:
  label: "Zapytaj o produkt za darmo - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Ask about product free na MyPresta.eu](https://mypresta.eu/modules/front-office-features/ask-about-product-free.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/ask-about-product-free/)
>
> ---


# Zapytaj o produkt za darmo

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Zapytaj o produkt za darmo”, gdzie kontrolujesz jego zachowanie i wygląd.

- **Lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > „Zapytaj o produkt za darmo” > Konfiguruj

#### Ustawienia i opcje:

1.  **Wyświetl podsumowanie produktu w wyskakującym okienku**

    - **Co robi to ustawienie:** Kontroluje, czy małe podsumowanie produktu (takie jak jego nazwa i obraz) jest wyświetlane w wyskakującym formularzu „Zapytaj o produkt”.
    - **Efekt zmiany tego ustawienia:**
        - *Gdy włączone (Tak):* Formularz wyskakujący będzie zawierał krótki przegląd produktu, o który pyta klient. Pomaga to klientowi potwierdzić, że pyta o właściwy przedmiot i zapewnia kontekst dla Ciebie, gdy otrzymasz e-mail.
        - *Gdy wyłączone (Nie):* Formularz wyskakujący będzie zawierał tylko pola na imię i nazwisko klienta, adres e-mail i pytanie, bez podsumowania specyficznego dla produktu.
    - **Zalecana wartość:** **Tak**.
    - **Scenariusz/przykład dla sprzedawcy:** Włączenie tego pomaga uniknąć zamieszania. Klient może mieć otwartych wiele kart i zapomnieć, o który produkt pyta. Podsumowanie potwierdza to dla niego i dla Ciebie.
2.  **Włączone**

    - **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji całej funkcji „Zapytaj o produkt” w Twoim sklepie.
    - **Efekt zmiany tego ustawienia:**
        - *Gdy włączone (Tak):* Przycisk „Zapytaj o produkt” pojawi się na stronach produktów, a formularz wyskakujący będzie funkcjonalny.
        - *Gdy wyłączone (Nie):* Przycisk „Zapytaj o produkt” zostanie ukryty ze stron produktów, a klienci nie będą mogli korzystać z tej funkcji.
    - **Zalecana wartość:** **Tak** (aby używać modułu).
    - **Scenariusz/przykład dla sprzedawcy:** Możesz tymczasowo wyłączyć tę funkcję, jeśli przeprowadzasz konserwację lub jeśli wolisz obsługiwać wszystkie zapytania za pośrednictwem innego kanału przez pewien czas.
3.  **Zgodne z RODO**

    - **Co robi to ustawienie:** Aktywuje pole wyboru w formularzu „Zapytaj o produkt”, wymagając od klientów wyraźnej zgody na Twoją politykę prywatności przed wysłaniem pytania. Pomaga to Twojemu sklepowi zachować zgodność z RODO i innymi przepisami o ochronie danych.
    - **Efekt zmiany tego ustawienia:**
        - *Gdy włączone (Tak):* W formularzu pojawi się obowiązkowe pole wyboru, zazwyczaj z tekstem „Zgadzam się z polityką prywatności”. Klient musi zaznaczyć to pole, aby wysłać swoje pytanie.
        - *Gdy wyłączone (Nie):* Pole wyboru polityki prywatności nie będzie wyświetlane, a klienci mogą wysyłać swoje pytania bez wyraźnej zgody.
    - **Zalecana wartość:** **Tak**.
    - **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój sklep działa w regionach z surowymi przepisami o ochronie danych (takich jak UE), włączenie tej funkcji jest kluczowe dla zgodności prawnej.
4.  **Strona polityki prywatności**

    - **Co robi to ustawienie:** Jeśli „Zgodne z RODO” jest włączone, to ustawienie pozwala wybrać, która strona CMS (System Zarządzania Treścią) z Twojego sklepu zostanie połączona jako Twoja polityka prywatności.
    - **Efekt zmiany tego ustawienia:**
        - *Gdy strona jest wybrana:* Tekst „Zgadzam się z polityką prywatności” w formularzu wyskakującym będzie zawierał klikalny link do wybranej strony CMS, umożliwiając klientom łatwe zapoznanie się z Twoją polityką.
        - *Gdy żadna strona nie jest wybrana (lub Zgodne z RODO jest Nie):* Nie zostanie podany żaden link, lub funkcja RODO nie będzie aktywna.
    - **Zalecana wartość:** Wybierz oficjalną stronę polityki prywatności swojego sklepu.
    - **Scenariusz/przykład dla sprzedawcy:** Musisz mieć dedykowaną stronę CMS, która opisuje Twoje praktyki dotyczące obsługi danych. To ustawienie zapewnia klientom łatwy dostęp do niej.
5.  **Tytuł e-maila**

    - **Co robi to ustawienie:** Definiuje temat wiadomości e-mail, którą otrzymujesz, gdy klient wysyła pytanie za pośrednictwem formularza.
    - **Efekt zmiany tego ustawienia:**
        - *Gdy ustawiony jest konkretny tytuł (np. „Nowe pytanie o produkt”):* Wszystkie przychodzące e-maile z tego modułu będą używać tego tematu, co ułatwi ich identyfikację w Twojej skrzynce odbiorczej.
        - *Gdy pozostawiony domyślny:* Moduł użyje swojego domyślnego tematu, który może być mniej opisowy.
    - **Zalecana wartość:** Coś jasnego i opisowego, np. „Nowe pytanie o produkt ze sklepu [Nazwa Twojego Sklepu]”.
    - **Scenariusz/przykład dla sprzedawcy:** Jasny temat pomaga szybko priorytetyzować i odpowiadać na zapytania klientów, zwłaszcza jeśli codziennie otrzymujesz wiele e-maili.
6.  **Odbiorca e-maila z formularza**

    - **Co robi to ustawienie:** Określa adres(y) e-mail, na które będą wysyłane pytania klientów przesłane za pośrednictwem formularza „Zapytaj o produkt”.
    - **Efekt zmiany tego ustawienia:**
        - *Gdy wprowadzono jeden lub więcej adresów e-mail (oddzielonych przecinkami):* Moduł wyśle wszystkie zapytania klientów na te określone adresy.
        - *Gdy pozostawione puste:* Moduł może domyślnie użyć głównego adresu e-mail kontaktowego sklepu, lub funkcja może nie działać poprawnie.
    - **Zalecana wartość:** Twój adres e-mail obsługi klienta (np. `support@twojsklep.com`) lub dedykowany adres e-mail do zapytań o produkty. Możesz dodać wiele adresów e-mail oddzielonych przecinkami, jeśli wielu członków zespołu musi je otrzymywać.
    - **Scenariusz/przykład dla sprzedawcy:** Kierowanie tych e-maili do właściwego zespołu zapewnia szybkie odpowiedzi, poprawiając zadowolenie klienta.
7.  **Ochrona ReCaptcha (v2)**

    - **Co robi to ustawienie:** Integruje Google reCAPTCHA v2 (pole wyboru „Nie jestem robotem”) z formularzem „Zapytaj o produkt”, aby chronić przed spamem i automatycznymi wysyłkami.
    - **Efekt zmiany tego ustawienia:**
        - *Gdy włączone (Tak):* Pole wyboru reCAPTCHA pojawi się w formularzu, wymagając od klientów przejścia wyzwania przed wysłaniem.
        - *Gdy wyłączone (Nie):* Formularz nie będzie miał ochrony reCAPTCHA, co czyni go potencjalnie podatnym na boty spamujące.
    - **Zalecana wartość:** **Tak**.
    - **Scenariusz/przykład dla sprzedawcy:** Jeśli otrzymujesz dużo zapytań spamowych za pośrednictwem formularza, włączenie reCAPTCHA jest niezbędne do odfiltrowania nielegalnych wiadomości.
8.  **Klucz witryny reCaptcha**

    - **Co robi to ustawienie:** Jest to klucz publiczny dostarczony przez Google reCAPTCHA, który umożliwia Twojej witrynie wyświetlanie widżetu reCAPTCHA. Otrzymujesz ten klucz, gdy rejestrujesz swoją witrynę w Google reCAPTCHA.
    - **Efekt zmiany tego ustawienia:**
        - *Gdy poprawnie wprowadzony:* Widżet reCAPTCHA będzie wyświetlany i działał poprawnie w Twoim formularzu.
        - *Gdy niepoprawny lub pusty:* reCAPTCHA nie będzie działać, a możesz zobaczyć komunikat o błędzie lub formularz nie zostanie wysłany.
    - **Zalecana wartość:** Klucz witryny uzyskany z Twojego konta Google reCAPTCHA.
    - **Scenariusz/przykład dla sprzedawcy:** Musisz zarejestrować swoją domenę w Google reCAPTCHA (v2), aby uzyskać zarówno klucz witryny, jak i klucz tajny.
9.  **Klucz tajny reCaptcha**

    - **Co robi to ustawienie:** Jest to klucz prywatny dostarczony przez Google reCAPTCHA, który umożliwia Twojemu serwerowi weryfikację odpowiedzi reCAPTCHA. Jest używany do walidacji po stronie serwera.
    - **Efekt zmiany tego ustawienia:**
        - *Gdy poprawnie wprowadzony:* Twój serwer może pomyślnie zweryfikować, czy klient przeszedł wyzwanie reCAPTCHA.
        - *Gdy niepoprawny lub pusty:* Nawet jeśli widżet reCAPTCHA jest wyświetlany, wysłanie formularza zakończy się niepowodzeniem walidacji, a pytanie nie zostanie wysłane.
    - **Zalecana wartość:** Klucz tajny uzyskany z Twojego konta Google reCAPTCHA.
    - **Scenariusz/przykład dla sprzedawcy:** Ten klucz jest kluczowy dla aspektu bezpieczeństwa reCAPTCHA, zapewniając, że przetwarzane są tylko legalne zgłoszenia.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyświetl podsumowanie produktu w wyskakującym okienku | Tak | Wyświetla szczegóły produktu w wyskakującym okienku dla jasności. |
| Konfiguracja modułu | Włączone | Tak | Aktywuje/dezaktywuje funkcję „Zapytaj o produkt”. |
| Konfiguracja modułu | Zgodne z RODO | Tak | Dodaje pole wyboru zgody na politykę prywatności do formularza. |
| Konfiguracja modułu | Strona polityki prywatności | Wybierz swoją stronę CMS Polityki Prywatności | Łączy się z polityką prywatności Twojego sklepu dla RODO. |
| Konfiguracja modułu | Tytuł e-maila | „Nowe pytanie o produkt ze sklepu [Nazwa Twojego Sklepu]” | Ustawia temat dla przychodzących e-maili z pytaniami. |
| Konfiguracja modułu | Odbiorca e-maila z formularza | Twój adres e-mail obsługi klienta (np. `support@twojsklep.com`) | Określa, gdzie wysyłane są pytania klientów. |
| Konfiguracja modułu | Ochrona ReCaptcha (v2) | Tak | Włącza Google reCAPTCHA, aby zapobiec spamowi. |
| Konfiguracja modułu | Klucz witryny reCaptcha | Twój klucz witryny Google reCAPTCHA | Klucz publiczny do wyświetlania widżetu reCAPTCHA. |
| Konfiguracja modułu | Klucz tajny reCaptcha | Twój klucz tajny Google reCAPTCHA | Klucz prywatny do walidacji reCAPTCHA po stronie serwera. |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### AdminAapfreeQuestionController (Panel administracyjny > Zapytaj o produkt > Pytania)

Ten dedykowany ekran administracyjny umożliwia przeglądanie i zarządzanie wszystkimi pytaniami przesłanymi za pośrednictwem formularza „Zapytaj o produkt”.

- **Nazwa ekranu i lokalizacja menu:** Panel administracyjny > **Zapytaj o produkt** (nowy element menu) > **Pytania**
- **Dostępne akcje i ustawienia:**
  - **Tabela listy:** Ten ekran wyświetla tabelę wszystkich przesłanych pytań. Każdy wiersz zazwyczaj pokazuje:
    - **ID:** Unikalny identyfikator pytania.
    - **Imię klienta:** Imię podane przez klienta.
    - **E-mail klienta:** Adres e-mail podany przez klienta.
    - **Nazwa produktu:** Nazwa produktu, którego dotyczy pytanie.
    - **Pytanie:** Fragment lub pełny tekst pytania klienta.
    - **Data dodania:** Kiedy pytanie zostało przesłane.
    - **Status:** (np. Nowe, Odpowiedziano, Oczekujące) - *Uwaga: Dokumentacja modułu nie wspomina wyraźnie o polu statusu, ale jest to częsta funkcja dla takich list. Jeśli nie jest obecne, po prostu wyświetli wszystkie pytania.*
  - **Wyświetl szczegóły:** Zazwyczaj można kliknąć pytanie na liście, aby wyświetlić jego pełne szczegóły, w tym pełny tekst pytania i potencjalnie link do produktu.
  - **Usuń:** Opcje usuwania pojedynczych pytań lub potencjalnie masowego usuwania wybranych pytań.
- **Efekt zmian:**
  - **Przeglądanie pytań:** Umożliwia przeglądanie wszystkich zapytań klientów w jednej scentralizowanej lokalizacji w panelu administracyjnym PrestaShop, nawet jeśli otrzymujesz je również pocztą e-mail.
  - **Usuwanie pytań:** Usuwa rekord pytania z Twojej bazy danych. Jest to przydatne do porządkowania starych lub nieistotnych zapytań.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. Regularnie sprawdzaj tę listę „Pytania” (lub swoją skrzynkę odbiorczą, zgodnie z konfiguracją) pod kątem nowych zapytań.
  2. Priorytetyzuj i odpowiadaj na pytania szybko, aby utrzymać dobrą obsługę klienta.
  3. Po udzieleniu odpowiedzi możesz usunąć pytanie z tej listy, aby utrzymać porządek, lub, jeśli moduł to obsługuje, oznaczyć je jako „Odpowiedziano”.

#### index.php (aapfree/controllers/admin/index.php)

Ten plik jest zazwyczaj symbolem zastępczym lub przekierowaniem w katalogu `controllers/admin` i nie reprezentuje odrębnego, konfigurowalnego ekranu dla sprzedawcy. Jest to standardowa praktyka PrestaShop, aby mieć `index.php` w podkatalogach, aby zapobiec listowaniu katalogów, lub może zawierać podstawową logikę routingu. Nie zarządza on żadną konkretną tabelą ani encją do bezpośredniej interakcji sprzedawcy.

## 3. Rozwiązywanie problemów przez sprzedawcę i często zadawane pytania (FAQ)

**P1: Przycisk „Zapytaj o produkt” nie wyświetla się na moich stronach produktów.**

- **O:** Najpierw sprawdź, czy moduł jest „Włączony” w jego ustawieniach konfiguracyjnych (Panel administracyjny > Moduły > Menedżer modułów > Zapytaj o produkt za darmo > Konfiguruj). Jeśli tak, spróbuj wyczyścić pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną). Czasami konflikty motywów lub specyficzne niestandardowe struktury motywów mogą uniemożliwić wyświetlenie przycisku. Jeśli nadal go brakuje, skontaktuj się z administratorem swojej strony lub wsparciem MyPresta.eu.

**P2: Nie otrzymuję żadnych e-maili, gdy klienci wysyłają pytania.**

- **O:**
  1. Sprawdź ustawienie „Odbiorca e-maila z formularza” w konfiguracji modułu. Upewnij się, że adres(y) e-mail są poprawne i oddzielone przecinkami, jeśli jest ich wiele.
  2. Sprawdź folder spam/śmieci w skrzynce odbiorczej adresata.
  3. Upewnij się, że ustawienia e-mail Twojego sklepu są poprawnie skonfigurowane w PrestaShop (Zaawansowane > E-mail). Przetestuj wysyłanie ogólnego e-maila z PrestaShop, aby potwierdzić, że Twój serwer pocztowy działa.
  4. Jeśli ReCAPTCHA jest włączona, upewnij się, że zarówno „Klucz witryny reCaptcha”, jak i „Klucz tajny reCaptcha” są poprawnie wprowadzone. Nieprawidłowe klucze uniemożliwią wysyłanie.

**P3: reCAPTCHA nie działa lub widzę komunikat o błędzie.**

- **O:** Zazwyczaj oznacza to, że Twoje klucze reCAPTCHA są nieprawidłowe lub nieprawidłowo skonfigurowane w Google.
  1. Przejdź do konsoli administracyjnej Google reCAPTCHA i upewnij się, że Twoja domena jest poprawnie zarejestrowana dla reCAPTCHA v2.
  2. Skopiuj „Klucz witryny” i „Klucz tajny” dokładnie tak, jak zostały dostarczone przez Google, i wklej je w polach konfiguracyjnych modułu.
  3. Wyczyść pamięć podręczną PrestaShop po wprowadzeniu zmian.

**P4: Jak zmienić tekst na przycisku „Zapytaj o produkt” lub w wyskakującym formularzu?**

- **O:** Możesz przetłumaczyć ciągi tekstowe modułu bezpośrednio w PrestaShop. Przejdź do **Lokalizacja > Tłumaczenia**, wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz „Zapytaj o produkt za darmo”. Znajdziesz tam wszystkie tłumaczone ciągi, w tym etykiety przycisków, etykiety pól formularza i komunikaty potwierdzające.

**P5: Wyskakujące okienko wygląda dziwnie lub nie wyświetla się poprawnie na moim telefonie komórkowym.**

- **O:** Chociaż moduł jest zaprojektowany tak, aby był responsywny, niestandardowe motywy mogą czasami nadpisywać lub kolidować z jego stylizacją.
  1. Wyczyść pamięć podręczną przeglądarki i pamięć podręczną PrestaShop.
  2. Jeśli problem nadal występuje, prawdopodobnie jest to konflikt CSS z Twoim motywem. Twój webmaster lub programista musiałby zbadać stronę za pomocą narzędzi deweloperskich przeglądarki, aby zidentyfikować i rozwiązać konflikt CSS.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Zapytaj o produkt za darmo” wykorzystuje standardowy wzorzec PrestaShop MVC (Model-View-Controller), koncentrując się głównie na interakcji z front-office i administracji przesłanymi pytaniami w back-office. Wykorzystuje system hooków PrestaShop do integracji ze stronami produktów i używa dedykowanych kontrolerów front-office do żądań AJAX i wysyłania formularzy. Komponent back-office zapewnia prosty interfejs zarządzania listą pytań.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:

  - `controllers/front/index.php`
    - **Nazwa klasy i klasa nadrzędna:** `AapfreeIndexModuleFrontController` rozszerzający `ModuleFrontController`.
    - **Odpowiedzialność:** Ten kontroler prawdopodobnie obsługuje początkową logikę wyświetlania komponentu front-office modułu, być może renderując przycisk lub przygotowując dane dla wyskakującego okienka. Może również służyć jako ogólny kontroler dla tras front-office specyficznych dla modułu.
  - `controllers/front/question.php`
    - **Nazwa klasy i klasa nadrzędna:** `AapfreeQuestionModuleFrontController` rozszerzający `ModuleFrontController`.
    - **Odpowiedzialność:** Jest to główny kontroler do obsługi wysyłania formularza „Zapytaj o produkt”. Odbiera dane POST z formularza wyskakującego, waliduje dane wejściowe (w tym reCAPTCHA, jeśli jest włączona), przetwarza pytanie, wysyła e-mail do skonfigurowanych odbiorców i przechowuje pytanie w bazie danych. Zwraca odpowiedzi JSON dla żądań AJAX (np. komunikaty o sukcesie/błędzie).
- **Kontrolery administracyjne Back-Office**:

  - `controllers/admin/AdminAapfreeQuestion.php`
    - **Nazwa klasy i klasa nadrzędna:** `AdminAapfreeQuestionController` rozszerzający `ModuleAdminController`.
    - **Nazwa zakładki i zarządzana encja:** Ten kontroler tworzy i zarządza zakładką „Pytania” w menu „Zapytaj o produkt” w Panelu administracyjnym PrestaShop. Jest odpowiedzialny za wyświetlanie listy (siatki) wszystkich przesłanych pytań, umożliwiając administratorom przeglądanie szczegółów i usuwanie wpisów. Współpracuje z `ObjectModel` `AapfreeQuestion` (jeśli istnieje, w przeciwnym razie bezpośrednio z bazą danych).
  - `controllers/admin/index.php`
    - **Nazwa klasy i klasa nadrzędna:** Nie jest to funkcjonalny kontroler w tradycyjnym sensie.
    - **Nazwa zakładki i zarządzana encja:** Ten plik jest standardowym środkiem bezpieczeństwa PrestaShop, aby zapobiec listowaniu katalogów. Zazwyczaj zawiera proste `header('Location: ../../index.php?controller=AdminHome');` lub podobne przekierowanie, lub po prostu `<?php exit;`. Nie zarządza żadną konkretną encją ani nie zapewnia konfigurowalnego ekranu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dokumentacja modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Sugeruje to, że moduł może obsługiwać interakcje z bazą danych bezpośrednio w swoich kontrolerach lub głównym pliku modułu, lub może używać ogólnego `ObjectModel` dla `aapfreequestion`, jeśli jest on niejawnie zdefiniowany.

- **Niejawny model (prawdopodobnie):** Biorąc pod uwagę, że `AdminAapfreeQuestionController` zarządza tabelą, istnieje niejawny model `AapfreeQuestion`, nawet jeśli nie jest on jawnie w `classes/`. Ten model mapowałby się do tabeli bazy danych `_aapfree_question`.
  - **Tabela bazy danych:** `ps_aapfree_question` (lub podobna, w zależności od prefiksu modułu).
  - **Rozszerza `ObjectModel`:** Tak, niejawnie.
  - **Oczekiwane pola `$definition`:** `id_aapfree_question`, `id_product`, `customer_name`, `customer_email`, `question_text`, `date_add`.

### 4.4 Zasoby JavaScript (`views/js/`)

- `aapfree/views/aapfree.js`
  - **Zakres:** Front-office.
  - **Słuchacze zdarzeń:**
    - Wiąże zdarzenia kliknięcia z przyciskiem „Zapytaj o produkt” (`.aapfree-button`).
    - Wiąże zdarzenia wysyłania z formularzem „Zapytaj o produkt” w wyskakującym okienku (`#aapfree-form`).
    - Obsługuje zdarzenia związane z widżetem reCAPTCHA (jeśli jest włączony).
  - **Manipulacja DOM:**
    - Otwiera i zamyka modalne wyskakujące okienko (`#aapfree-modal`).
    - Wypełnia dane podsumowania produktu w wyskakującym okienku.
    - Wyświetla komunikaty o sukcesie lub błędzie użytkownikowi po wysłaniu formularza.
    - Zarządza stanami pól formularza (np. wyłączanie przycisku wysyłania podczas AJAX).
  - **Wywołania AJAX:**
    - Wysyła dane formularza do `AapfreeQuestionModuleFrontController` (np. `index.php?fc=module&module=aapfree&controller=question`).
    - Przetwarza odpowiedzi JSON z serwera.
  - **Wywołania zewnętrznych SDK:** Inicjuje i renderuje widżet Google reCAPTCHA v2, jeśli `aapfree_recaptcha` jest włączony, używając `aapfree_recaptcha_sitekey`.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `aapfree/views/aapfree.css`
  - **Zakres:** Stylizacja klienta front-office.
  - **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:**
    - Przycisk „Zapytaj o produkt” (`.aapfree-button`).
    - Kontener modalnego wyskakującego okienka (`#aapfree-modal`).
    - Elementy formularza w wyskakującym okienku (pola wejściowe, pola tekstowe, etykiety, pola wyboru).
    - Wyświetlanie komunikatów o sukcesie i błędzie.
    - Responsywne dostosowania dla różnych rozmiarów ekranu.
  - **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** `.aapfree-button`, `.aapfree-modal`, `.aapfree-modal-content`, `.aapfree-form-group`, `.aapfree-product-summary`, `.aapfree-success-message`, `.aapfree-error-message`. Programiści mogą nadpisać te style w pliku `custom.css` swojego motywu lub za pomocą funkcji dostosowywania motywu PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:
  - `aapfree/views/aapfree-extra.tpl`
    - **Hook:** `displayProductAdditionalInfo` (lub podobny hook strony produktu, np. `displayProductButtons`, `displayProductActions`).
    - **Wyjście bloku wizualnego:** Ten szablon jest odpowiedzialny za renderowanie przycisku „Zapytaj o produkt” na stronie produktu. Zawiera również strukturę HTML dla modalnego formularza wyskakującego, który jest początkowo ukryty i wyświetlany za pomocą JavaScript. Zawiera symbole zastępcze dla podsumowania produktu, pól formularza, pola wyboru RODO i reCAPTCHA.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - `ps_aapfree_question`:
    - `id_aapfree_question` (INT, KLUCZ GŁÓWNY, AUTO_INCREMENT)
    - `id_product` (INT, Klucz obcy do `ps_product`)
    - `customer_name` (VARCHAR)
    - `customer_email` (VARCHAR)
    - `question_text` (TEXT)
    - `date_add` (DATETIME)
    - (Potencjalnie inne pola, takie jak `ip_address`, `status`, `id_customer`, jeśli zaimplementowane)
  - **Rekordy konfiguracji (w `ps_configuration`):**
    - `AAPFREE_TITLE`: Temat e-maila.
    - `AAPFREE_GDPR`: Status zgodności z RODO (0/1).
    - `AAPFREE_GDPRCMS`: ID strony CMS dla polityki prywatności.
    - `AAPFREE_SUMMARY`: Status wyświetlania podsumowania produktu (0/1).
    - `AAPFREE_RECAPTCHA`: Status ochrony reCAPTCHA (0/1).
    - `AAPFREE_RECAPTCHA_SITEKEY`: Klucz witryny Google reCAPTCHA.
    - `AAPFREE_RECAPTCHA_SECRETKEY`: Klucz tajny Google reCAPTCHA.
    - `AAPFREE_EMAILSLIST`: Lista adresów e-mail odbiorców oddzielonych przecinkami.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayProductAdditionalInfo` | Na stronach produktów, zazwyczaj poniżej opisu produktu lub ceny. | Renderuje przycisk „Zapytaj o produkt” i ukrytą strukturę modalnego wyskakującego okienka. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny ładuje swoje zasoby (CSS/JS). | Wstrzykuje CSS (`aapfree.css`) i JavaScript (`aapfree.js`) specyficzne dla modułu do Panelu administracyjnego dla `AdminAapfreeQuestionController`. |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Potencjalnie używane do ładowania globalnych zmiennych JavaScript, CSS lub skryptu API Google reCAPTCHA, jeśli reCAPTCHA jest włączona. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Zapytaj o produkt za darmo”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół jest zaangażowany w zapewnienie płynnego działania i ciągłego ulepszania Twojego modułu.
