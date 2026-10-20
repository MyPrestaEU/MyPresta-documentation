---
title: "Prawo UE dotyczące plików cookie - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Prawo UE dotyczące plików cookie” od MyPresta.eu."
sidebar:
  label: "Prawo UE dotyczące plików cookie - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł European Union Cookie Law na MyPresta.eu](https://mypresta.eu/modules/front-office-features/european-union-cookie-law.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/european-union-cookie-law/)
>
> ---


# Prawo UE dotyczące plików cookie

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu „Prawo UE dotyczące plików cookie”. Znajdziesz tu wszystkie ustawienia, aby dostosować powiadomienie o plikach cookie.

#### **Włącz / Wyłącz moduł**

- **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania powiadomień o plikach cookie w całym Twoim sklepie.
- **Efekt zmiany tego ustawienia:**
  - *Po włączeniu:* Pasek powiadomień o plikach cookie pojawi się w Twoim front office zgodnie z innymi ustawieniami.
  - *Po wyłączeniu:* Pasek powiadomień o plikach cookie nie będzie wyświetlany żadnym odwiedzającym.
- **Zalecana wartość:** TAK (chyba że masz inną metodę zgodności z plikami cookie).
- **Scenariusz / przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz aktywować powiadomienie o plikach cookie. Ustaw to na „TAK”. Jeśli tymczasowo musisz je ukryć w celu konserwacji lub testowania, możesz ustawić to na „NIE”.

#### **Tekst cookie**

- **Co robi to ustawienie:** Jest to rzeczywista wiadomość, która zostanie wyświetlona Twoim klientom dotycząca używania plików cookie. Obsługuje wiele języków, co pozwala na dostarczenie zlokalizowanej wiadomości dla każdego języka włączonego w Twoim sklepie.
- **Efekt zmiany tego ustawienia:** Wprowadzony tekst zostanie wyświetlony w pasku powiadomień o plikach cookie. Możesz użyć edytora tekstu sformatowanego, aby sformatować tekst, dodać linki (np. do pełnej strony polityki prywatności) i podkreślić ważne informacje.
- **Zalecana wartość:** Jasna, zwięzła wiadomość, która informuje użytkowników o plikach cookie i idealnie zawiera link do Twojej pełnej polityki prywatności lub strony polityki plików cookie.
- **Scenariusz / przykład dla sprzedawcy:** Możesz napisać: „Ta witryna używa plików cookie, aby zapewnić najlepsze wrażenia na naszej stronie. [Link do Polityki prywatności]”. Pamiętaj, aby przetłumaczyć to na wszystkie aktywne języki Twojego sklepu.

#### **Tekst przycisku**

- **Co robi to ustawienie:** Definiuje tekst wyświetlany na przycisku, który klienci klikają, aby potwierdzić lub zaakceptować politykę plików cookie. Podobnie jak tekst cookie, obsługuje wiele języków.
- **Efekt zmiany tego ustawienia:** Przycisk wyświetli określony tekst. Kliknięcie tego przycisku spowoduje odrzucenie powiadomienia o plikach cookie dla użytkownika.
- **Zalecana wartość:** „Rozumiem”, „Akceptuję”, „Zrozumiałem”, „Kontynuuj” lub „OK”.
- **Scenariusz / przykład dla sprzedawcy:** Aby jasno określić, że użytkownicy potwierdzają politykę, możesz ustawić to na „Rozumiem i akceptuję”.

#### **Pozycja**

- **Co robi to ustawienie:** Określa, gdzie pasek powiadomień o plikach cookie pojawia się na Twojej witrynie.
- **Efekt zmiany tego ustawienia:**
  - *Góra:* Pasek pojawi się na stałe na górze okna przeglądarki.
  - *Dół:* Pasek pojawi się na stałe na dole okna przeglądarki.
- **Zalecana wartość:** Dół (często mniej inwazyjny niż góra, która czasami może kolidować z elementami nagłówka).
- **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby powiadomienie o plikach cookie było widoczne, ale nie zasłaniało głównej nawigacji ani logo. Wybór „Dół” jest zazwyczaj dobrym kompromisem.

#### **Kolor tła**

- **Co robi to ustawienie:** Pozwala wybrać kolor tła paska powiadomień o plikach cookie. Pomaga to wizualnie zintegrować pasek z projektem Twojego sklepu.
- **Efekt zmiany tego ustawienia:** Tło paska cookie zmieni się na wybrany kolor. Zazwyczaj dostępny jest narzędzie do wyboru koloru dla łatwego wyboru.
- **Zalecana wartość:** Kolor, który dobrze kontrastuje z kolorem tekstu i uzupełnia branding Twojego sklepu.
- **Scenariusz / przykład dla sprzedawcy:** Twój sklep używa dużo niebieskiego. Możesz wybrać jasnoniebieski lub subtelny szary dla tła, aby pasował do Twojego motywu.

#### **Kolor tekstu**

- **Co robi to ustawienie:** Pozwala wybrać kolor tekstu w pasku powiadomień o plikach cookie.
- **Efekt zmiany tego ustawienia:** Tekst w pasku cookie zmieni się na wybrany kolor.
- **Zalecana wartość:** Kolor, który zapewnia dobry kontrast z wybranym kolorem tła dla czytelności.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli kolor tła jest ciemny, wybierz jasny kolor tekstu (np. biały, jasnoszary). Jeśli tło jest jasne, wybierz ciemny kolor tekstu (np. czarny, ciemnoszary).

#### **Kolor linku**

- **Co robi to ustawienie:** Pozwala wybrać kolor wszelkich linków zawartych w Twoim „Tekście cookie” (np. link do Twojej polityki prywatności).
- **Efekt zmiany tego ustawienia:** Wszystkie tagi `<a>` w tekście paska cookie będą wyświetlane w tym kolorze.
- **Zalecana wartość:** Kolor, który wyróżnia się od głównego koloru tekstu, ale nadal pasuje do Twojej marki.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby link do Twojej polityki prywatności był łatwo zauważalny. Możesz wybrać akcentowy kolor swojej marki dla linku.

#### **Kolor tła przycisku**

- **Co robi to ustawienie:** Ustawia kolor tła przycisku „Tekst przycisku”.
- **Efekt zmiany tego ustawienia:** Przycisk będzie miał wybrany kolor tła.
- **Zalecana wartość:** Kolor, który sprawia, że przycisk wyróżnia się i zachęca do kliknięć, często pasujący do koloru głównego przycisku wezwania do działania w Twoim sklepie.
- **Scenariusz / przykład dla sprzedawcy:** Przyciski „Dodaj do koszyka” w Twoim sklepie są zielone. Możesz wybrać zielony dla tła przycisku cookie, aby zachować spójność.

#### **Kolor tekstu przycisku**

- **Co robi to ustawienie:** Ustawia kolor tekstu na przycisku „Tekst przycisku”.
- **Efekt zmiany tego ustawienia:** Tekst przycisku zostanie wyświetlony w tym kolorze.
- **Zalecana wartość:** Kolor, który zapewnia dobry kontrast z kolorem tła przycisku dla czytelności.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli tło przycisku jest ciemnozielone, wybierz biały lub bardzo jasny kolor dla tekstu przycisku.

#### **Wygaśnięcie cookie (w dniach)**

- **Co robi to ustawienie:** Określa, jak długo powiadomienie o plikach cookie pozostaje ukryte po kliknięciu przez użytkownika przycisku „Rozumiem”. Po tym okresie powiadomienie ponownie pojawi się dla użytkownika.
- **Efekt zmiany tego ustawienia:**
  - *Ustawione na 30:* Powiadomienie będzie ukryte przez 30 dni dla tego konkretnego użytkownika.
  - *Ustawione na 0:* Powiadomienie może pojawiać się przy każdej wizycie lub sesji, co generalnie nie jest zalecane, ponieważ może być irytujące.
- **Zalecana wartość:** Od 30 do 365 dni. Powszechną praktyką jest 90 lub 180 dni.
- **Scenariusz / przykład dla sprzedawcy:** Aby uniknąć wielokrotnego nękania powracających klientów, ustawiasz to na „180” dni. Oznacza to, że klient, który zaakceptuje politykę, nie zobaczy paska ponownie przez sześć miesięcy.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Włącz / Wyłącz moduł** | TAK | Główny przełącznik widoczności paska cookie. |
| Konfiguracja modułu | **Tekst cookie** | Dostosowywalny | Główna wiadomość o używaniu plików cookie, obsługuje tekst sformatowany i wiele języków. |
| Konfiguracja modułu | **Tekst przycisku** | Dostosowywalny | Tekst na przycisku do odrzucenia powiadomienia, wiele języków. |
| Konfiguracja modułu | **Pozycja** | Dół | Gdzie pojawia się pasek (Góra lub Dół ekranu). |
| Konfiguracja modułu | **Kolor tła** | Dostosowywalny | Kolor tła paska cookie. |
| Konfiguracja modułu | **Kolor tekstu** | Dostosowywalny | Kolor głównego tekstu w pasku cookie. |
| Konfiguracja modułu | **Kolor linku** | Dostosowywalny | Kolor wszelkich linków w tekście cookie. |
| Konfiguracja modułu | **Kolor tła przycisku** | Dostosowywalny | Kolor tła przycisku odrzucenia. |
| Konfiguracja modułu | **Kolor tekstu przycisku** | Dostosowywalny | Kolor tekstu na przycisku odrzucenia. |
| Konfiguracja modułu | **Wygaśnięcie cookie (w dniach)** | 180-365 dni | Jak długo powiadomienie pozostaje ukryte po akceptacji przez użytkownika. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Pasek cookie nie wyświetla się w moim sklepie.**
O1:

- **Sprawdź „Włącz / Wyłącz moduł”:** Upewnij się, że to ustawienie jest ustawione na „TAK” w konfiguracji modułu.
- **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Czasami stare, buforowane treści uniemożliwiają wyświetlanie nowych zmian modułu.
- **Sprawdź konflikty:** Tymczasowo wyłącz inne niedawno zainstalowane moduły, aby sprawdzić, czy nie ma konfliktu.
- **Pamięć podręczna przeglądarki:** Spróbuj wyczyścić pamięć podręczną przeglądarki lub otworzyć swój sklep w oknie incognito/prywatnym.

**P2: Zaktualizowałem tekst, ale nie zmienia się on w front office.**
O2:

- **Zapisz zmiany:** Upewnij się, że kliknąłeś przycisk „Zapisz” po wprowadzeniu zmian w konfiguracji modułu.
- **Wyczyść pamięć podręczną PrestaShop:** Jak wspomniano powyżej, często konieczne jest wyczyszczenie pamięci podręcznej Smarty (w **Zaawansowane > Wydajność**), aby zmiany szablonu i tekstu weszły w życie.
- **Sprawdź język:** Upewnij się, że edytujesz tekst dla poprawnego języka, jeśli Twój sklep jest wielojęzyczny.

**P3: Pasek cookie wygląda dziwnie lub nie pasuje do mojego motywu.**
O3:

- **Dostosuj kolory:** Użyj ustawień „Kolor tła”, „Kolor tekstu”, „Kolor linku”, „Kolor tła przycisku” i „Kolor tekstu przycisku”, aby dopasować je do palety Twojego motywu.
- **Konflikty motywów:** Niektóre niestandardowe motywy mogą mieć kolidujące style CSS. Jeśli dostosowanie kolorów nie pomaga, może być konieczne, aby programista internetowy sprawdził CSS i wprowadził drobne poprawki.

**P4: Jak dodać link do mojej Polityki prywatności w tekście cookie?**
O4:

- W polu „Tekst cookie” użyj edytora tekstu sformatowanego. Wpisz tekst, który ma być linkiem (np. „Polityka prywatności”), zaznacz go, a następnie kliknij ikonę „Link” na pasku narzędzi edytora. Wprowadź adres URL swojej strony Polityki prywatności.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów, webmasterów i agencji pracujących z modułem „Prawo UE dotyczące plików cookie”.

### 4.1 Przegląd architektury

Moduł `uecookie` to prosty moduł PrestaShop, zaprojektowany głównie do wstrzykiwania szablonu front-office do haka wyświetlania, kontrolowanego przez standardową metodę konfiguracji `getContent()`. Wykorzystuje klasę `Module` PrestaShop do instalacji, deinstalacji i konfiguracji, a także szablony Smarty do renderowania powiadomień o plikach cookie. Logika po stronie klienta do odrzucania paska cookie jest obsługiwana za pomocą JavaScript.

### 4.2 Kontrolery (`controllers/`)

- Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała funkcjonalność jest obsługiwana w głównym pliku modułu oraz powiązanych szablonach i zasobach.

### 4.3 Podstawowe klasy i modele (`classes/`)

- Ten moduł **nie** zawiera żadnych niestandardowych klas ani definicji `ObjectModel`. Cała konfiguracja jest przechowywana bezpośrednio w `ps_configuration` za pomocą `Configuration::get()` i `Configuration::updateValue()`.

### 4.4 Zasoby JavaScript (`views/js/`)

- `uecookie/jscolor/jscolor.js`:
  - **Zakres:** Back-office.
  - **Cel:** Zapewnia funkcjonalność selektora kolorów JavaScript dla formularza konfiguracji modułu, umożliwiając administratorom wizualne wybieranie kolorów dla paska cookie.
- `uecookie/tinymce-original.js`:
  - **Zakres:** Back-office.
  - **Cel:** Pełna wersja edytora tekstu sformatowanego TinyMCE, używana dla pola „Tekst cookie” w konfiguracji modułu. Umożliwia to administratorom formatowanie tekstu, dodawanie linków itp.
- `uecookie/tinymce16.inc.js`:
  - **Zakres:** Back-office.
  - **Cel:** Prawdopodobnie plik dołączający lub konfiguracyjny dla TinyMCE, być może dostosowujący jego pasek narzędzi lub opcje dla kompatybilności z PrestaShop 1.6 lub specyficznych potrzeb modułu.
- `uecookie/views/js/scripts.js`:
  - **Zakres:** Front-office.
  - **Cel:** Ten skrypt obsługuje logikę po stronie klienta dla paska powiadomień o plikach cookie.
    - **Słuchacze zdarzeń:** Prawdopodobnie nasłuchuje zdarzenia kliknięcia na przycisku „Rozumiem”.
    - **Manipulacja DOM:** Ukrywa element paska cookie z DOM po odrzuceniu.
    - **Zarządzanie plikami cookie:** Ustawia plik cookie przeglądarki (np. `uecookie_accepted`) z datą wygaśnięcia (określoną przez ustawienie „Wygaśnięcie cookie”), aby zapobiec ponownemu pojawieniu się paska przez określony czas.
    - **Wstępne sprawdzenie:** Po załadowaniu strony sprawdza obecność pliku cookie `uecookie_accepted`, aby określić, czy wyświetlić pasek, czy nie.

### 4.5 Arkusze stylów CSS (`views/css/`)

- Ten moduł **nie** zawiera żadnych niestandardowych plików CSS w `views/css/`. Stylizacja paska cookie jest prawdopodobnie wbudowana lub generowana dynamicznie na podstawie ustawień kolorów, lub opiera się na minimalnych domyślnych stylach przeglądarki. Programiści, którzy chcą dalej dostosować wygląd, musieliby celować w strukturę HTML wygenerowaną przez `top.tpl` za pomocą niestandardowego CSS swojego motywu.

### 4.6 Struktura szablonu Smarty (`views/templates/`)

- **Szablony haków (`views/templates/hook/`)**:
  - `uecookie/top.tpl`:
    - **Hak:** Ten szablon jest przede wszystkim zaprojektowany do renderowania w haku front-office, takim jak `displayHeader`, `displayFooter`, `displayTop` lub `displayBeforeBodyClosingTag`. Metoda `hookDisplayHeader` modułu jest zazwyczaj odpowiedzialna za rejestrowanie i renderowanie tego szablonu.
    - **Wyjście:** Generuje strukturę HTML dla paska powiadomień o plikach cookie, w tym dostosowywalny tekst, przycisk i dynamiczną stylizację na podstawie ustawień konfiguracji modułu (kolor tła, kolor tekstu itp.). Zawiera również niezbędny JavaScript (`scripts.js`) do obsługi odrzucania i ustawiania plików cookie.

### 4.7 Schemat bazy danych i mapa haków

- **Tabele bazy danych**:

  - Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych.
  - Wszystkie ustawienia konfiguracji są przechowywane w tabeli `ps_configuration`. Kluczowe wpisy konfiguracyjne to:
    - `UECOOKIE_ENABLED` (wartość logiczna)
    - `UECOOKIE_TEXT` (ciąg znaków wielojęzyczny)
    - `UECOOKIE_BUTTON_TEXT` (ciąg znaków wielojęzyczny)
    - `UECOOKIE_POSITION` (ciąg znaków: ‘top’ lub ‘bottom’)
    - `UECOOKIE_BG_COLOR` (ciąg znaków: kod koloru hex)
    - `UECOOKIE_TEXT_COLOR` (ciąg znaków: kod koloru hex)
    - `UECOOKIE_LINK_COLOR` (ciąg znaków: kod koloru hex)
    - `UECOOKIE_BUTTON_BG_COLOR` (ciąg znaków: kod koloru hex)
    - `UECOOKIE_BUTTON_TEXT_COLOR` (ciąg znaków: kod koloru hex)
    - `UECOOKIE_EXPIRATION` (liczba całkowita: dni)
- **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony front-office. | Służy do wstrzykiwania plików CSS (jeśli istnieją) i JavaScript modułu, a potencjalnie początkowej struktury HTML paska cookie, jeśli jest umieszczony na górze. |
| `displayFooter` | Wykonywany na dole każdej strony front-office, przed zamykającym tagiem `</body>`. | Może być używany do wstrzykiwania HTML i JavaScript paska cookie, zwłaszcza jeśli jest umieszczony na dole. |
| `displayTop` | Wykonywany w sekcji nagłówka motywu, zazwyczaj powyżej głównej treści. | Alternatywny hak do wyświetlania paska cookie na górze. |
| `displayBeforeBodyClosingTag` | Wykonywany tuż przed tagiem `</body>`. | Solidny hak do wstrzykiwania JavaScript i elementów HTML, które powinny pojawić się na samym końcu strony. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji, poprawek błędów i oficjalnego wsparcia dla modułu „Prawo UE dotyczące plików cookie”, prosimy o zapoznanie się z kontem klienta na [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
