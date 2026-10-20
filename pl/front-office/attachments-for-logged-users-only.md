---
title: "Załączniki tylko dla zalogowanych użytkowników - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Załączniki tylko dla zalogowanych użytkowników” od MyPresta.eu."
sidebar:
  label: "Załączniki tylko dla zalogowanych użytkowników - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Attachments for logged users only na MyPresta.eu](https://mypresta.eu/modules/front-office-features/attachments-for-logged-users-only.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/attachments-for-logged-users-only/)
>
> ---


# Załączniki tylko dla zalogowanych użytkowników

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po zainstalowaniu modułu kliknij „Konfiguruj”, aby uzyskać dostęp do jego ustawień. Jest to główny ekran, na którym kontrolujesz zachowanie modułu.

#### **Aktywuj funkcję**

- **Co robi to ustawienie:** Jest to główny przełącznik modułu. Określa, czy funkcja ograniczenia załączników jest aktywna, czy nieaktywna w Twoim sklepie.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone („Włączone”):* Moduł będzie aktywnie ograniczał pobieranie załączników produktów tylko do zalogowanych klientów. Niezalogowani użytkownicy nie będą mogli pobierać załączników.
  - *Gdy wyłączone („Wyłączone”):* Moduł będzie nieaktywny. Załączniki produktów będą zachowywać się domyślnie w PrestaShop, co oznacza, że każdy (zalogowany lub gość) może je pobrać.
- **Zalecana wartość:** „Włączone”, jeśli chcesz ograniczyć pobieranie załączników.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz zacząć wymagać od klientów logowania się, aby pobrać instrukcje, ustaw to na „Włączone”. Jeśli testujesz lub chcesz tymczasowo wrócić do domyślnego zachowania PrestaShop, ustaw to na „Wyłączone”.

#### **Pobieranie tylko dla klientów**

- **Co robi to ustawienie:** To ustawienie precyzuje „Aktywuj funkcję”, pozwalając określić, *którzy* klienci mogą pobierać załączniki na podstawie ich historii zamówień.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone:* Tylko klienci, którzy są zalogowani ORAZ mają co najmniej jedno zamówienie o wybranym statusie (patrz „Wybierz statusy zamówień” poniżej), będą mogli pobierać załączniki. Dodaje to dodatkową warstwę ekskluzywności.
  - *Gdy wyłączone:* Każdy zalogowany klient (niezależnie od historii zamówień) będzie mógł pobierać załączniki, pod warunkiem, że „Aktywuj funkcję” jest włączone.
- **Zalecana wartość:** „Wyłączone” w większości przypadków, pozwalając każdemu zalogowanemu klientowi na pobieranie. „Włączone”, jeśli chcesz oferować załączniki jako bonus dla *płacących* klientów.
- **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz oprogramowanie i chcesz udostępniać aktualizacje lub przewodniki premium tylko klientom, którzy faktycznie zakupili oprogramowanie. Włączysz to ustawienie i wybierzesz „Płatność zaakceptowana” w opcji „Wybierz statusy zamówień”.

#### **Wybierz statusy zamówień**

- **Co robi to ustawienie:** Ta opcja pojawia się tylko, jeśli „Pobieranie tylko dla klientów” jest włączone. Pozwala wybrać, które statusy zamówień kwalifikują klienta do pobierania załączników. Klient musi mieć co najmniej jedno zamówienie z jednym z wybranych statusów, aby uzyskać dostęp.
- **Efekt zmiany tego ustawienia:**
  - *Gdy wybrano jeden lub więcej statusów:* Tylko zalogowani klienci z zamówieniem pasującym do jednego z tych statusów mogą pobierać załączniki.
  - *Gdy nie wybrano żadnych statusów (i „Pobieranie tylko dla klientów” jest włączone):* Ta konfiguracja może spowodować, że żaden klient nie będzie mógł pobierać, ponieważ nie zdefiniowano kwalifikujących statusów zamówień. Kluczowe jest wybranie co najmniej jednego statusu, jeśli włączysz „Pobieranie tylko dla klientów”.
- **Zalecana wartość:** Jeśli „Pobieranie tylko dla klientów” jest włączone, wybierz odpowiednie statusy, takie jak „Płatność zaakceptowana”, „Dostarczone” lub „Wysłane”, aby przyznać dostęp klientom, którzy pomyślnie zrealizowali zamówienie.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz dać dostęp do załączników tylko klientom, których zamówienia zostały pomyślnie opłacone i przetworzone, wybierzesz „Płatność zaakceptowana” i „Dostarczone”. Zapobiega to dostępowi do plików klientom z oczekującymi lub anulowanymi zamówieniami.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Aktywuj funkcję | Włączone | Główny przełącznik do włączania/wyłączania ograniczenia załączników. |
| Konfiguracja modułu | Pobieranie tylko dla klientów | Wyłączone | Jeśli włączone, tylko zalogowani klienci z określonymi statusami zamówień mogą pobierać. |
| Konfiguracja modułu | Wybierz statusy zamówień | (Brak wybranych) | Jeśli „Pobieranie tylko dla klientów” jest aktywne, wybierz statusy zamówień, które przyznają dostęp do pobierania. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje załączniki są nadal dostępne do pobrania dla wszystkich, nawet po włączeniu modułu. Co jest nie tak?**
O:

1. **Sprawdź „Aktywuj funkcję”:** Upewnij się, że ustawienie „Aktywuj funkcję” na stronie konfiguracji modułu jest ustawione na „Włączone”.
2. **Wyczyść pamięć podręczną:** PrestaShop używa pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Często rozwiązuje to problemy z wyświetlaniem po zmianach konfiguracji modułu.
3. **Pozycja modułu:** Upewnij się, że moduł jest poprawnie podpięty. Chociaż moduł obsługuje to automatycznie, czasami mogą wystąpić konflikty z szablonem.

**P: Włączyłem „Pobieranie tylko dla klientów” i wybrałem statusy zamówień, ale moi zalogowani klienci nadal nie mogą pobierać.**
O:

1. **Zweryfikuj status zamówienia:** Sprawdź dokładnie, czy klient próbujący pobrać plik faktycznie ma zamówienie z *dokładnie* jednym ze statusów wybranych w „Wybierz statusy zamówień”.
2. **Logowanie klienta:** Potwierdź, że klient jest faktycznie zalogowany na swoje konto.
3. **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność).

**P: Jak przetłumaczyć komunikaty wyświetlane niezalogowanym użytkownikom?**
O: Moduł powinien integrować się z systemem tłumaczeń PrestaShop.

1. Przejdź do **Lokalizacja > Tłumaczenia**.
2. Wybierz „Tłumaczenia zainstalowanych modułów”.
3. Wybierz swój szablon, swój język, a następnie moduł „Załączniki tylko dla zalogowanych użytkowników”.
4. Powinieneś znaleźć tam odpowiednie ciągi tekstowe do przetłumaczenia.

**P: Czy ten moduł będzie działał z moim niestandardowym szablonem?**
O: Tak, moduł jest zaprojektowany do współpracy ze standardowymi mechanizmami załączników PrestaShop. Przede wszystkim przechwytuje żądanie pobierania, zamiast mocno modyfikować wizualne wyświetlanie załączników. Jednakże, jeśli Twój niestandardowy szablon całkowicie nadpisuje sposób wyświetlania lub linkowania załączników, mogą być potrzebne drobne korekty. Zawsze dokładnie testuj po instalacji.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Załączniki tylko dla zalogowanych użytkowników” działa głównie poprzez nadpisywanie domyślnego `AttachmentController` w celu przechwytywania żądań pobierania. Wykorzystuje system hooków PrestaShop (`displayHeader`, `header`) do wstrzykiwania niezbędnego JavaScriptu i CSS, a jego główna logika znajduje się w pliku `atlogged.php`, obsługując konfigurację i podstawowe nadpisanie. Moduł używa prostej struktury konfiguracji przechowywanej w `ps_configuration` i zawiera kontrolery front-office do interakcji AJAX i potencjalnej logiki awaryjnej.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

- `atlogged/controllers/front/index.php`

  - **Nazwa klasy:** `AtloggedIndexModuleFrontController` (prawdopodobnie, na podstawie konwencji nazewnictwa plików)
  - **Klasa nadrzędna:** `ModuleFrontController`
  - **Odpowiedzialność:** Ten kontroler może służyć jako ogólny punkt wejścia dla akcji front-office specyficznych dla modułu, potencjalnie obsługując przekierowania lub wyświetlając komunikaty, gdy pobieranie załącznika jest ograniczone. Może również być miejscem zastępczym lub używanym do specyficznego routingu.
- `atlogged/controllers/front/popuploader.php`

  - **Nazwa klasy:** `AtloggedPopuploaderModuleFrontController`
  - **Klasa nadrzędna:** `ModuleFrontController`
  - **Odpowiedzialność:** Ten kontroler prawdopodobnie obsługuje żądania AJAX związane z wyświetlaniem monitu o logowanie/rejestrację lub konkretnego komunikatu, gdy użytkownik próbuje pobrać ograniczony załącznik. Może renderować mały szablon (np. `atlogged-ajax.tpl`) z odpowiednią zawartością.
- `atlogged/override/controllers/front/AttachmentController.php`

  - **Nazwa klasy:** `AttachmentController` (nadpisuje klasę bazową)
  - **Klasa nadrzędna:** `AttachmentControllerCore`
  - **Odpowiedzialność:** Jest to najbardziej krytyczna część logiki front-office modułu. Bezpośrednio nadpisuje podstawowy `AttachmentController` PrestaShop. Jego główną funkcją jest:
    1. Sprawdzenie, czy moduł jest włączony (`ATLOGGED_ON`).
    2. Weryfikacja, czy bieżący użytkownik jest zalogowany.
    3. Jeśli `ATLOGGED_C_ON` (Pobieranie tylko dla klientów) jest włączone, dodatkowo sprawdza historię zamówień użytkownika pod kątem skonfigurowanych `atlogged_ostates`.
    4. Jeśli użytkownik nie spełnia kryteriów, zapobiega domyślnemu procesowi pobierania załącznika i zamiast tego przekierowuje użytkownika lub wyzwala akcję specyficzną dla modułu (np. wyświetlanie monitu o logowanie za pośrednictwem AJAX).
- `atlogged/override/controllers/front/index.php`

  - **Nazwa klasy:** `IndexController` (nadpisuje klasę bazową)
  - **Klasa nadrzędna:** `IndexControllerCore`
  - **Odpowiedzialność:** Nadpisywanie `IndexController` jest mniej powszechne dla logiki specyficznej dla załączników. Może być używane do:
    1. Globalnych sprawdzeń lub przekierowań związanych z modułem na stronie głównej.
    2. Zapewnienia, że niektóre zasoby specyficzne dla modułu (JS/CSS) są ładowane globalnie.
    3. Potencjalnie obsługi przekierowania do strony logowania, jeśli link do załącznika jest dostępny bezpośrednio bez logowania z kontekstu strony głównej.

#### Kontrolery administracyjne Back-Office

- Brak zidentyfikowanych. Konfiguracja modułu jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy bazowe i modele (`classes/`)

- Brak zidentyfikowanych. Moduł nie wydaje się definiować niestandardowych klas `ObjectModel`. Prawdopodobnie działa bezpośrednio z istniejącymi obiektami bazowymi PrestaShop (np. `Customer`, `Order`, `Attachment`) i wartościami konfiguracyjnymi.

### 4.4 Zasoby JavaScript (`views/js/`)

- `atlogged/views/js/atlogged.js`
  - **Zakres:** Front-office.
  - **Szczegóły:** Ten skrypt jest prawdopodobnie odpowiedzialny za:
    1. Przechwytywanie kliknięć na linki do pobierania załączników (tagi `<a>` ze specyficznymi klasami lub atrybutami danych).
    2. Wykonywanie wywołań AJAX do kontrolerów frontowych `popuploader.php` lub `index.php`, gdy niezgodny użytkownik próbuje pobrać ograniczony plik.
    3. Wyświetlanie wyskakujących okien modalnych lub komunikatów (np. „Zaloguj się, aby pobrać”) na podstawie odpowiedzi AJAX.
    4. Potencjalne przekierowywanie użytkowników na stronę logowania, jeśli odpowiedź AJAX tego wymaga.
    5. Zapewnienie płynnego doświadczenia użytkownika, gdy dostęp jest odmawiany.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `atlogged/views/css/atlogged.css`
  - **Zakres:** Stylizacja klienta front-office.
  - **Szczegóły:** Ten arkusz stylów zapewnia niezbędną stylizację dla wszelkich niestandardowych elementów wprowadzonych przez moduł, takich jak:
    1. Stylizacja modalnego okna lub pola komunikatu z monitem o logowanie/rejestrację.
    2. Dostosowania wyglądu linków do załączników, jeśli są wyłączone lub wizualnie zmienione, gdy są ograniczone.
  - **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Programiści powinni zbadać wyjście HTML generowane przez szablony modułu (np. `atlogged-ajax.tpl`), aby zidentyfikować specyficzne klasy (np. `.atlogged-modal`, `.atlogged-message`, `.atlogged-login-button`) do integracji i dostosowania szablonu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony administracyjne (`views/templates/admin/`)**:

  - `atlogged/views/templates/admin/orderstates.tpl`
    - **Cel:** Ten szablon jest używany w metodzie `getContent()` modułu w Panelu Administracyjnym. Renderuje listę statusów zamówień (`atlogged_ostates`) dla opcji konfiguracji „Wybierz statusy zamówień”, zazwyczaj jako rozwijaną listę wielokrotnego wyboru lub listę pól wyboru.
- **Szablony front-office (`views/templates/front/`)**:

  - `atlogged/views/templates/front/atlogged-ajax.tpl`
    - **Cel:** Ten szablon jest prawdopodobnie renderowany przez kontroler frontowy `popuploader.php` w odpowiedzi na żądanie AJAX. Zawiera zawartość HTML komunikatu wyświetlanego użytkownikom, którzy nie mogą pobrać załącznika (np. „Zaloguj się, aby kontynuować”, z linkami do logowania/rejestracji).
  - `atlogged/views/templates/front/atlogged.tpl`
    - **Cel:** Ten szablon może być dołączony za pomocą hooka (np. `displayHeader`) lub bezpośrednio przez kontroler frontowy. Może zawierać:
      1. Ukryte elementy lub atrybuty danych używane przez `atlogged.js`.
      2. Początkowe ustawienia lub zmienne konfiguracyjne dla JavaScriptu.
      3. Komunikaty awaryjne lub elementy, które są zawsze obecne, ale warunkowo wyświetlane przez JS.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy niestandardowych tabel SQL.
  - Rekordy konfiguracyjne są przechowywane w tabeli `ps_configuration`:
    - `ATLOGGED_ON`: Przechowuje wartość logiczną dla ustawienia „Aktywuj funkcję”.
    - `ATLOGGED_C_ON`: Przechowuje wartość logiczną dla ustawienia „Pobieranie tylko dla klientów”.
    - `atlogged_ostates`: Przechowuje serializowaną tablicę lub ciąg znaków rozdzielonych przecinkami identyfikatorów wybranych statusów zamówień dla ustawienia „Wybierz statusy zamówień”.
    - `mypresta_updates`, `update_`, `updatev_`: Używane do sprawdzania aktualizacji modułu przez MyPresta.eu.
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Klucz konfiguracyjny PrestaShop, prawdopodobnie używany do kontekstu językowego w Panelu Administracyjnym.
- **Tabela zarejestrowanych hooków**:

  | Nazwa hooka | Czas wykonania | Cel techniczny |
  | --- | --- | --- |
  | `displayHeader` | W sekcji `<head>` każdej strony front-office. | Używany do wstrzykiwania `atlogged.js` i `atlogged.css` do strony, zapewniając załadowanie logiki po stronie klienta i stylizacji modułu. |
  | `header` | Alias dla `displayHeader` w niektórych wersjach/kontekstach PrestaShop. | Ten sam cel co `displayHeader`. |
  | `actionFrontControllerSetMedia` | Gdy kontroler frontowy ustawia swoje zasoby multimedialne. | Może być używany do warunkowego ładowania JS/CSS tylko na określonych stronach (np. stronach produktów) w celu optymalizacji wydajności. |
  | `actionDispatcherBefore` | Przed wysłaniem kontrolera frontowego. | Potencjalnie używany przez nadpisanie `AttachmentController` do bardzo wczesnego przechwytywania żądania pobierania. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i dedykowane wsparcie techniczne dla modułu „Załączniki tylko dla zalogowanych użytkowników”, prosimy odwołać się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest gotowy pomóc w przypadku wszelkich pytań lub problemów, które mogą się pojawić.
