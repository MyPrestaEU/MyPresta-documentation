---
title: "Proste odzyskiwanie hasła - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Proste odzyskiwanie hasła” od MyPresta.eu."
sidebar:
  label: "Proste odzyskiwanie hasła - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Simple password recovery na MyPresta.eu](https://mypresta.eu/modules/front-office-features/simple-password-recovery.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/simple-password-recovery/)
>
> ---


# Proste odzyskiwanie hasła

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne nietypowe konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Moduł „Proste odzyskiwanie hasła” został zaprojektowany jako w dużej mierze plug-and-play, zastępując domyślny przepływ odzyskiwania hasła w PrestaShop z minimalną wymaganą konfiguracją.

Gdy przejdziesz do **Moduły > Menedżer modułów** i klikniesz „Konfiguruj” obok „Proste odzyskiwanie hasła”, zazwyczaj znajdziesz prosty interfejs konfiguracji.

**Co robi to ustawienie:** Ten ekran pozwala włączyć lub wyłączyć podstawową funkcjonalność modułu i potencjalnie dostosować drobne ustawienia zachowania. Głównym celem jest aktywacja uproszczonego procesu odzyskiwania hasła.

**Efekt zmiany tego ustawienia:**

- **Gdy włączone:** Moduł przejmuje domyślny mechanizm odzyskiwania hasła w PrestaShop. Gdy klient zażąda zresetowania hasła, otrzyma wiadomość e-mail z unikalnym, bezpiecznym linkiem, który skieruje go na dedykowaną stronę do ustawienia nowego hasła. To znacznie upraszcza doświadczenie użytkownika.
- **Gdy wyłączone:** Funkcjonalność modułu jest dezaktywowana. Twój sklep PrestaShop powróci do domyślnego, standardowego procesu odzyskiwania hasła, który może obejmować więcej kroków lub różne metody weryfikacji dla klienta.

**Zalecana wartość:** **Włączone (TAK)**. Główną korzyścią z tego modułu jest uproszczenie procesu odzyskiwania hasła. Utrzymywanie go włączonym zapewnia klientom korzyści z tego ulepszonego doświadczenia.

**Scenariusz / przykład dla sprzedawcy:**
Zauważyłeś, że klienci często kontaktują się z obsługą klienta, ponieważ mają problemy z domyślnym odzyskiwaniem hasła. Włączając ten moduł, zapewniasz bezpośredni link jednym kliknięciem w wiadomości e-mail, umożliwiając im natychmiastowe ustawienie nowego hasła. To zmniejsza zamieszanie i szybciej przywraca ich do zakupów.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Status modułu (Włącz/Wyłącz) | Włączone | Aktywuje lub dezaktywuje uproszczony proces odzyskiwania hasła. Gdy włączone, klienci otrzymują bezpośredni link do ustawienia nowego hasła. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moi klienci nie otrzymują wiadomości e-mail z resetowaniem hasła.**
O:

- **Sprawdź foldery ze spamem:** Doradź klientom, aby sprawdzili swoje foldery ze spamem lub niechcianą pocztą.
- **Konfiguracja poczty e-mail:** Zweryfikuj ustawienia poczty e-mail w PrestaShop w sekcji **Zaawansowane > E-mail**. Upewnij się, że ustawienia SMTP są poprawne lub że funkcja PHP `mail()` działa.
- **Konflikty modułów:** Tymczasowo wyłącz inne moduły, które mogą zakłócać wysyłanie wiadomości e-mail lub zarządzanie kontami klientów, aby wykluczyć konflikty.
- **Logi serwera:** Sprawdź logi poczty serwera pod kątem błędów związanych z wychodzącymi wiadomościami e-mail.

**P: Link do resetowania hasła prowadzi klientów do pustej strony lub błędu.**
O:

- **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i wyczyść pamięć podręczną Smarty, pamięć podręczną przeglądarki i pamięć podręczną modułu.
- **Przepisywanie adresów URL:** Upewnij się, że przepisywanie adresów URL jest włączone w PrestaShop (**Parametry sklepu > SEO i adresy URL**) i że plik `.htaccess` jest poprawnie skonfigurowany.
- **Integralność modułu:** Ponownie prześlij pliki modułu za pośrednictwem FTP, aby upewnić się, że żadne pliki nie są uszkodzone lub brakujące.
- **Kompatybilność z motywem:** Chociaż rzadko, wysoce dostosowany motyw może mieć konflikty JavaScript. Sprawdź konsolę programisty przeglądarki pod kątem błędów JavaScript.

**P: Czy mogę dostosować wygląd nowej strony hasła?**
O: Tak, moduł wykorzystuje standardowe szablony PrestaShop. Wygląd jest kontrolowany głównie przez CSS aktywnego motywu PrestaShop i własny CSS modułu (`spreset/views/css/spreset.css`). Programiści mogą nadpisać te style w niestandardowym pliku CSS motywu lub modyfikując pliki szablonów modułu (`views/templates/front/password-change-form.tpl`, `views/templates/front/simple-reset-page.tpl`, `views/templates/front/simple-reset.tpl`).

**P: Czy ten moduł działa ze sklepami wielojęzycznymi?**
O: Tak, podobnie jak większość modułów PrestaShop, ciągi tekstowe są tłumaczone. Możesz przetłumaczyć frazy modułu za pośrednictwem **Lokalizacja > Tłumaczenia** w Panelu administracyjnym, wybierając „Tłumaczenia zainstalowanych modułów”, a następnie znajdując „Proste odzyskiwanie hasła”.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem „Proste odzyskiwanie hasła”.

### 4.1 Przegląd architektury

Moduł „Proste odzyskiwanie hasła” nadpisuje domyślny mechanizm odzyskiwania hasła w PrestaShop, wprowadzając niestandardowe kontrolery front-office do obsługi generowania tokenów, wysyłania wiadomości e-mail i procesu ustawiania nowego hasła. Wykorzystuje wzorzec MVC PrestaShop, z dedykowanymi kontrolerami dla różnych etapów odzyskiwania. Główny plik modułu (`index.php`) obsługuje instalację, deinstalację i główny formularz konfiguracji.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:

  - `controllers/front/changepass.php`
    - **Nazwa klasy**: `SpresetChangepassModuleFrontController` (rozszerza `ModuleFrontController`)
    - **Odpowiedzialność**: Ten kontroler odpowiada za wyświetlanie formularza, w którym klient może ustawić nowe hasło po kliknięciu bezpiecznego linku do resetowania. Waliduje token podany w adresie URL i obsługuje przesłanie nowego hasła.
  - `controllers/front/index.php`
    - **Nazwa klasy**: `SpresetIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    - **Odpowiedzialność**: Ten kontroler prawdopodobnie służy jako rezerwowy lub ogólny punkt wejścia dla funkcjonalności front-office modułu, potencjalnie przekierowując lub obsługując początkowe żądania związane z procesem resetowania hasła. W wielu przypadkach może to być symbol zastępczy lub używany do specyficznego routingu.
  - `controllers/front/simplereset.php`
    - **Nazwa klasy**: `SpresetSimpleresetModuleFrontController` (rozszerza `ModuleFrontController`)
    - **Odpowiedzialność**: Ten kontroler jest rdzeniem uproszczonego procesu resetowania. Odbiera początkowe żądanie resetowania hasła (np. ze standardowego formularza „Nie pamiętasz hasła” w PrestaShop), generuje bezpieczny token, wysyła wiadomość e-mail z unikalnym linkiem do resetowania i obsługuje początkową walidację adresu e-mail klienta.
- **Kontrolery administracyjne Back-Office**: Brak. Konfiguracja modułu jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł nie wydaje się definiować niestandardowych klas rozszerzających `ObjectModel` ani innych podstawowych klas PrestaShop w dedykowanym katalogu `classes/`. Jego logika jest przede wszystkim hermetyzowana w głównym pliku modułu i jego kontrolerach front-office.

### 4.4 Zasoby JavaScript (`views/js/`)

- `views/js/spreset.js`
  - **Zakres**: Front-office.
  - **Szczegóły**: Ten skrypt prawdopodobnie obsługuje walidację po stronie klienta dla formularza nowego hasła (np. sprawdzanie, czy hasła pasują, minimalne wymagania dotyczące długości) i potencjalnie przesyłanie AJAX dla zmiany hasła. Może również zawierać ulepszenia interfejsu użytkownika lub interakcje specyficzne dla strony resetowania hasła. Programiści powinni sprawdzić ten plik pod kątem konkretnych słuchaczy zdarzeń (np. `submit` w formularzu hasła) i wszelkich niestandardowych funkcji.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `views/css/spreset.css`
  - **Zakres**: Stylizacja klienta Front-office.
  - **Szczegóły**: Ten arkusz stylów zapewnia specyficzną stylizację dla komponentów front-office modułu, głównie formularza wprowadzania nowego hasła i powiązanych stron. Zapewnia, że interfejs odzyskiwania hasła wygląda estetycznie i rozsądnie integruje się z różnymi motywami. Programiści mogą sprawdzić ten plik, aby zidentyfikować kluczowe selektory klas CSS (np. `.spreset-form`, `.spreset-input`, `.spreset-button`), które można nadpisać w niestandardowym pliku CSS motywu, aby dopasować je do brandingu sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony Front-office (`views/templates/front/`)**:

  - `views/templates/front/password-change-form.tpl`
    - **Cel**: Ten szablon prawdopodobnie renderuje rzeczywisty formularz, w którym klient wprowadza i potwierdza swoje nowe hasło. Zawierałby pola wejściowe dla „Nowego hasła” i „Potwierdź nowe hasło” wraz z przyciskiem przesyłania.
  - `views/templates/front/simple-reset-page.tpl`
    - **Cel**: Ten szablon może służyć jako główny wrapper lub układ dla uproszczonego procesu resetowania hasła, potencjalnie zawierający wiadomości, instrukcje i osadzający inne częściowe szablony, takie jak `password-change-form.tpl`.
  - `views/templates/front/simple-reset.tpl`
    - **Cel**: Podobnie jak `simple-reset-page.tpl`, ten szablon jest częścią wyświetlania front-office dla przepływu resetowania hasła. Może być używany do początkowego formularza „wprowadź swój adres e-mail” lub do wyświetlania komunikatów o sukcesie/błędzie związanych z żądaniem resetowania.
- **Szablony specyficzne dla modułu (`views/templates/`)**:

  - `views/templates/spreset.tpl`
    - **Cel**: Ten szablon jest prawdopodobnie używany do głównej konfiguracji modułu w Panelu administracyjnym (jeśli `getContent()` renderuje szablon) lub do ogólnego haka wyświetlania, jeśli moduł ma proste wyjście dla haka. Biorąc pod uwagę charakter modułu, jest to bardziej prawdopodobne w przypadku konfiguracji Panelu administracyjnego.

### 4.7 Schemat bazy danych i mapa haków

- **Tabele bazy danych**: Moduł nie wydaje się tworzyć niestandardowych tabel SQL. Prawdopodobnie wykorzystuje istniejące tabele PrestaShop (np. `ps_customer` dla danych klienta, `ps_configuration` dla ustawień modułu) i generuje tymczasowe tokeny bez trwałego przechowywania w dedykowanej tabeli. Tokeny są zazwyczaj przechowywane w sesji lub przekazywane za pośrednictwem parametrów URL z krótkim okresem ważności.
- **Tabela zarejestrowanych haków**:
  Moduł nie wymienia jawnie zarejestrowanych haków w dostarczonych informacjach, ale na podstawie jego funkcjonalności, pośrednio wchodziłby w interakcje ze standardowym przepływem odzyskiwania hasła w PrestaShop, który jest często wyzwalany przez haki `displayCustomerAccountForm` lub `actionAuthenticationBefore`, lub przez nadpisywanie podstawowych kontrolerów PrestaShop.
  Główny plik modułu (`index.php`) rejestrowałby swoje kontrolery front-office do obsługi określonych tras, skutecznie „hakując” się w system routingu URL, a nie tradycyjne haki `display` lub `action` dla wizualnego wyjścia.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Proste odzyskiwanie hasła”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie optymalnej wydajności i kompatybilności naszych modułów z najnowszymi wersjami PrestaShop.
