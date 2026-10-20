---
title: "Free PopUp - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu Free PopUp PrestaShop od MyPresta.eu."
sidebar:
  label: "Free PopUp - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Free PopUp na MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-popup.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/free-popup/)
>
> ---


# Free PopUp

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest główny i jedyny ekran konfiguracji modułu Free PopUp. Znajdziesz tu wszystkie ustawienia do kontrolowania zawartości i zachowania Twojego wyskakującego okienka.

#### **1. Włącz / Wyłącz wyskakujące okienko**

- **Co robi to ustawienie:** To jest główny przełącznik dla Twojego wyskakującego okienka.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Wyskakujące okienko pojawi się w Twoim front office zgodnie z innymi ustawieniami.
  - *Gdy wyłączone (NIE):* Wyskakujące okienko nie pojawi się w Twoim front office, niezależnie od innych ustawień.
- **Zalecana wartość:** TAK (gdy chcesz, aby wyskakujące okienko było aktywne), NIE (gdy chcesz je tymczasowo ukryć).
- **Scenariusz / przykład dla sprzedawcy:** Włącz je, gdy masz nową promocję. Wyłącz je podczas konserwacji lub jeśli chcesz tymczasowo uruchomić inną kampanię.

#### **2. Zawartość wyskakującego okienka**

- **Co robi to ustawienie:** Tutaj wprowadzasz rzeczywistą wiadomość, ofertę lub informację, którą chcesz wyświetlić w wyskakującym okienku. Używa edytora tekstu sformatowanego (TinyMCE), umożliwiając formatowanie tekstu, dodawanie obrazów, linków i wiele więcej.
- **Efekt zmiany tego ustawienia:** Cokolwiek wpiszesz i sformatujesz tutaj, zostanie wyświetlone bezpośrednio Twoim klientom w oknie wyskakującym.
- **Zalecana wartość:** Twoja konkretna wiadomość promocyjna, tekst powitalny lub ważne ogłoszenie.
- **Scenariusz / przykład dla sprzedawcy:** „Witaj w naszym sklepie! Użyj kodu WITAJ10, aby otrzymać 10% zniżki na pierwsze zamówienie!” lub „Darmowa wysyłka na wszystkie zamówienia powyżej 50 USD w tym tygodniu!” Możesz również dodać obraz nowego produktu lub logo marki.

#### **3. Wygaśnięcie pliku cookie (dni)**

- **Co robi to ustawienie:** Określa, jak długo wyskakujące okienko pozostaje ukryte po jego zamknięciu przez klienta. Ustawia plik cookie w przeglądarce klienta.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na 0:* Wyskakujące okienko pojawi się przy *każdym* załadowaniu strony, nawet jeśli klient właśnie je zamknął. Jest to ogólnie niezalecane, ponieważ może być irytujące.
  - *Gdy ustawione na liczbę dodatnią (np. 7):* Wyskakujące okienko pojawi się przy pierwszej wizycie. Po zamknięciu nie pojawi się ponownie przez następne 7 dni dla tego konkretnego klienta w tej konkretnej przeglądarce.
- **Zalecana wartość:** 7 (dla cotygodniowych promocji), 30 (dla miesięcznych wiadomości powitalnych) lub 1 (jeśli chcesz, aby pojawiało się codziennie).
- **Scenariusz / przykład dla sprzedawcy:** Jeśli masz ogólną wiadomość powitalną, ustawienie jej na 30 dni jest dobre. Jeśli prowadzisz cotygodniową wyprzedaż, 7 dni zapewnia, że klienci zobaczą nową ofertę w następnym tygodniu.

#### **4. Tryb testowy**

- **Co robi to ustawienie:** Pozwala przetestować wygląd i zawartość wyskakującego okienka bez czekania na wygaśnięcie pliku cookie.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Wyskakujące okienko pojawi się przy każdym odświeżeniu strony, nawet jeśli właśnie je zamknąłeś. To nadpisuje ustawienie „Wygaśnięcie pliku cookie” do celów testowych.
  - *Gdy wyłączone (NIE):* Wyskakujące okienko będzie działać normalnie, respektując ustawienie „Wygaśnięcie pliku cookie”.
- **Zalecana wartość:** TAK (podczas konfigurowania i dostosowywania wyskakującego okienka), NIE (gdy jesteś zadowolony z konfiguracji i chcesz, aby działało normalnie dla klientów).
- **Scenariusz / przykład dla sprzedawcy:** Właśnie zaktualizowałeś zawartość wyskakującego okienka i chcesz natychmiast zobaczyć, jak wygląda w front office. Włącz Tryb testowy, odśwież stronę sklepu, a wyskakujące okienko się pojawi. Gdy będziesz zadowolony, wyłącz Tryb testowy.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Włącz / Wyłącz wyskakujące okienko | TAK | Główny przełącznik do pokazywania lub ukrywania wyskakującego okienka w Twoim sklepie. |
| Strona konfiguracji modułu | Zawartość wyskakującego okienka | Twoja wiadomość | Rzeczywisty tekst, obrazy i linki wyświetlane w wyskakującym okienku. |
| Strona konfiguracji modułu | Wygaśnięcie pliku cookie (dni) | 7 | Ile dni wyskakujące okienko pozostaje ukryte po jego zamknięciu przez klienta. |
| Strona konfiguracji modułu | Tryb testowy | NIE | Wymusza wyświetlanie wyskakującego okienka przy każdym odświeżeniu w celach testowych. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje wyskakujące okienko nie pojawia się w front office, nawet po jego włączeniu.**

- **O:** Najpierw sprawdź, czy „Włącz / Wyłącz wyskakujące okienko” jest ustawione na TAK. Jeśli tak, spróbuj włączyć „Tryb testowy”, aby sprawdzić, czy się pojawi. Jeśli nadal się nie pojawia, wyczyść pamięć podręczną przeglądarki i pamięć podręczną Smarty PrestaShop (Przejdź do **Zaawansowane > Wydajność**, a następnie kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu). Upewnij się również, że zapisałeś konfigurację po wprowadzeniu zmian.

**P2: Wyskakujące okienko pojawiło się raz, ale teraz nie chce się ponownie wyświetlić.**

- **O:** Jest to normalne zachowanie ze względu na ustawienie „Wygaśnięcie pliku cookie”. Moduł ustawia plik cookie w Twojej przeglądarce, aby zapobiec ponownemu pojawieniu się wyskakującego okienka przez określoną liczbę dni. Aby wymusić jego wyświetlenie w celach testowych, włącz „Tryb testowy” w konfiguracji modułu. Aby zobaczyć je jako nowy odwiedzający, wyczyść pliki cookie przeglądarki dla domeny Twojego sklepu lub użyj okna incognito/prywatnego przeglądania.

**P3: Jak mogę zmienić wygląd wyskakującego okienka (zmienić kolory, czcionki itp.)?**

- **O:** Moduł zapewnia podstawowe białe okno modalne z 70% nakładką. Do zaawansowanego stylizowania potrzebny byłby niestandardowy CSS. Zazwyczaj zajmuje się tym programista stron internetowych. Możesz dodać niestandardowy CSS do pliku `custom.css` swojego motywu lub bezpośrednio edytować plik `front.css` modułu (choć to ostatnie nie jest zalecane, ponieważ aktualizacje by go nadpisały).

**P4: Czy mogę mieć różne wyskakujące okienka dla różnych stron lub grup klientów?**

- **O:** Moduł Free PopUp jest przeznaczony do jednej, ogólnosklepowej kampanii. Wyświetla tę samą zawartość wszystkim odwiedzającym. Do bardziej zaawansowanych, ukierunkowanych wyskakujących okienek potrzebny byłby moduł wyskakujących okienek o bogatszych funkcjach (i prawdopodobnie płatny).

**P5: Moje obrazy lub linki w zawartości wyskakującego okienka nie działają poprawnie.**

- **O:** Upewnij się, że używasz pełnych, bezwzględnych adresów URL dla obrazów i linków (np. `https://twojskep.com/img/twojobraz.jpg` zamiast `/img/twojobraz.jpg`). Edytor TinyMCE powinien to obsługiwać automatycznie, ale czasami pojawiają się problemy, jeśli kopiujesz i wklejasz zawartość z zewnętrznych źródeł. Sprawdź ponownie źródło HTML, jeśli czujesz się z tym komfortowo.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł Free PopUp to prosty moduł PrestaShop, który stosuje podstawowy wzorzec MVC. Wykorzystuje głównie klasę `Module` do swojej podstawowej funkcjonalności, zarządzania konfiguracją i rejestracji hooków. Wyświetlanie w front-office jest zarządzane przez pojedynczy szablon renderowany za pomocą hooka, a jego zachowanie jest kontrolowane przez prosty plik JavaScript. Stylizacja jest obsługiwana przez dedykowane pliki CSS zarówno dla panelu administracyjnego, jak i front-office.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje niestandardowych kontrolerów front-office ani back-office. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównej klasy modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani instancji `ObjectModel`. Wszystkie dane konfiguracyjne są przechowywane bezpośrednio w tabeli `ps_configuration` PrestaShop za pomocą standardowych metod `Configuration::get()` i `Configuration::updateValue()`.

### 4.4 Zasoby JavaScript (`views/js/`)

- **`myfreepopup/js/front.js`**
  - **Zakres:** Front-office.
  - **Odpowiedzialność:** Ten skrypt odpowiada za zachowanie wyskakującego okienka po stronie klienta.
  - **Szczegóły:**
    - Sprawdza obecność konkretnego pliku cookie (`myfreepopup_closed`).
    - Jeśli plik cookie nie zostanie znaleziony (co oznacza, że użytkownik nie zamknął ostatnio wyskakującego okienka lub jest to jego pierwsza wizyta), wyświetla wyskakujące okienko, manipulując właściwościami CSS (np. `display: block`).
    - Dołącza nasłuch zdarzeń do przycisku zamykania w wyskakującym okienku.
    - Po kliknięciu przycisku zamykania ukrywa wyskakujące okienko i ustawia plik cookie `myfreepopup_closed` z datą wygaśnięcia opartą na konfiguracji modułu.
    - Obsługuje również logikę „Trybu testowego”, zapewniając pominięcie sprawdzania plików cookie, gdy tryb testowy jest aktywny.

### 4.5 Arkusze stylów CSS (`views/css/`)

- **`myfreepopup/css/admin.css`**
  - **Zakres:** Stylizacja formularza administracyjnego w panelu administracyjnym.
  - **Szczegóły:** Zawiera podstawowe reguły stylizacji dla strony konfiguracji modułu w panelu administracyjnym PrestaShop, zapewniając spójny wygląd i działanie w panelu administracyjnym.
- **`myfreepopup/css/front.css`**
  - **Zakres:** Stylizacja dla klientów w front-office.
  - **Szczegóły:** Definiuje wygląd samego wyskakującego okienka. Obejmuje to:
    - Stylizację dla nakładki modalnej (np. `position: fixed`, `background-color`, `opacity`, `z-index`).
    - Stylizację dla głównego pola zawartości wyskakującego okienka (np. `background-color: #fff`, `border`, `box-shadow`, `max-width`, `padding`, `text-align`, `position: fixed`, `top`, `left`, `transform` do centrowania).
    - Stylizację dla przycisku zamykania (np. `position: absolute`, `font-size`, `cursor: pointer`).
    - Responsywne dostosowania dla różnych rozmiarów ekranu za pomocą zapytań mediów.
  - **Kluczowe selektory klas CSS do nadpisywania:** `.myfreepopup_overlay`, `.myfreepopup_content`, `.myfreepopup_close`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **`myfreepopup/views/admin_banner.tpl`**
  - **Zakres:** Szablon administracyjny.
  - **Cel:** Wyświetla baner promocyjny lub wiadomość informacyjną na stronie konfiguracji modułu w panelu administracyjnym.
- **`myfreepopup/views/admin_locks.tpl`**
  - **Zakres:** Szablon administracyjny.
  - **Cel:** Prawdopodobnie używany do wyświetlania informacji związanych z licencjonowaniem modułu lub dodatkowymi funkcjami, często z ikoną kłódki.
- **`myfreepopup/views/front.tpl`**
  - **Zakres:** Szablon hooka front-office.
  - **Cel:** To jest główny szablon odpowiedzialny za renderowanie struktury HTML wyskakującego okienka w front-office.
  - **Renderowany w hooku:** `displayHeader` (lub podobny globalny hook, w którym można załadować JS/CSS).
  - **Zawartość:** Zawiera HTML dla nakładki, pola zawartości wyskakującego okienka, przycisku zamykania i dynamicznie wstawia zmienną `{$popup_content}` (która pochodzi z edytora TinyMCE w panelu administracyjnym). Zawiera również niezbędne pliki JavaScript i CSS.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Ten moduł nie tworzy niestandardowych tabel SQL.
  - Przechowuje swoje ustawienia konfiguracyjne w standardowej tabeli `ps_configuration` za pomocą kluczy takich jak `MYFREEPOPUP_ENABLED`, `MYFREEPOPUP_CONTENT`, `MYFREEPOPUP_COOKIE_DAYS`, `MYFREEPOPUP_TEST_MODE`.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony front-office. | Służy do dołączania plików CSS i JavaScript modułu oraz do renderowania początkowej struktury HTML wyskakującego okienka (`front.tpl`), która jest następnie kontrolowana przez JavaScript. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu Free PopUp.
