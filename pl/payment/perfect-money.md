---
title: "Perfect Money - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla programistów modułu Perfect Money dla PrestaShop od MyPresta.eu."
sidebar:
  label: "Perfect Money - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Perfect Money na MyPresta.eu](https://mypresta.eu/modules/payment-process/perfect-money.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/payment/perfect-money/)
>
> ---


# Perfect Money

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 1.6.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do bezpiecznej komunikacji z bramką płatności, które są prawie zawsze dostępne w nowoczesnych środowiskach hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Perfect Money)

Jest to główny ekran konfiguracji modułu Perfect Money, gdzie wprowadzisz dane swojego konta Perfect Money i ustawisz, jak metoda płatności będzie wyglądać i działać w Twoim sklepie.

#### **Ustawienia konta Perfect Money**

- **Co robi to ustawienie:** Te pola są kluczowe do połączenia Twojego sklepu PrestaShop z Twoim kontem sprzedawcy Perfect Money. Informują moduł, na które konto Perfect Money wysyłać płatności i jak weryfikować transakcje.
- **Wpływ zmiany tego ustawienia:** Nieprawidłowe wartości uniemożliwią klientom dokonywanie płatności lub płatności mogą nie być poprawnie przypisane do Twojego konta.
  - *Przy prawidłowej konfiguracji:* Płatności będą przetwarzane pomyślnie przez Twoje konto Perfect Money.
  - *Przy nieprawidłowej konfiguracji:* Płatności nie powiodą się lub klienci napotkają błędy podczas realizacji zamówienia.
- **Zalecana wartość:** Wprowadź dokładne dane dostarczone przez Twoje konto sprzedawcy Perfect Money.
- **Scenariusz / przykład sprzedawcy:** Zarejestrowałeś konto sprzedawcy w Perfect Money. Dostarczają Ci „Perfect Money Account ID” (np. U1234567) i „Perfect Money Account Name” (np. MyStorePayments). Ustawiasz również „Perfect Money Alternate Passphrase” w ustawieniach swojego konta Perfect Money dla zwiększonego bezpieczeństwa. Musisz wprowadzić te dokładne wartości tutaj.

#### **Ustawienia wyświetlania płatności**

- **Co robi to ustawienie:** Ta sekcja kontroluje, jak opcja płatności Perfect Money jest prezentowana Twoim klientom podczas realizacji zamówienia.
- **Wpływ zmiany tego ustawienia:**
  - *Po włączeniu:* Klienci zobaczą opcję Perfect Money i będą mogli ją wybrać do płatności.
  - *Po wyłączeniu:* Perfect Money nie pojawi się jako opcja płatności.
- **Zalecana wartość:** „TAK” (Włączone), jeśli chcesz oferować Perfect Money jako metodę płatności.
- **Scenariusz / przykład sprzedawcy:** Chcesz oferować Perfect Money jako opcję płatności. Włączasz ją. Jeśli tymczasowo chcesz ją wyłączyć z powodu konserwacji lub jeśli nie chcesz już akceptować Perfect Money, ustawisz ją na „NIE”.

#### **Ustawienia statusu zamówienia**

- **Co robi to ustawienie:** Te ustawienia określają status, jaki będzie miało zamówienie w Twoim panelu administracyjnym PrestaShop po dokonaniu płatności przez klienta za pośrednictwem Perfect Money.
- **Wpływ zmiany tego ustawienia:**
  - *Po ustawieniu na „Płatność zaakceptowana”:* Zamówienia opłacone za pośrednictwem Perfect Money zostaną automatycznie oznaczone jako „Płatność zaakceptowana” w Twoim panelu administracyjnym PrestaShop, wskazując pomyślną transakcję.
  - *Po ustawieniu na „Błąd płatności”:* Jeśli płatność nie powiedzie się lub wystąpi problem, zamówienie zostanie oznaczone tym statusem.
- **Zalecana wartość:**
  - **Status zamówienia dla pomyślnej płatności:** „Płatność zaakceptowana” (lub podobny status skonfigurowany dla pomyślnych płatności).
  - **Status zamówienia dla błędu płatności:** „Błąd płatności” (lub podobny status dla nieudanych płatności).
- **Scenariusz / przykład sprzedawcy:** Klient pomyślnie płaci za pomocą Perfect Money. Chcesz szybko zidentyfikować te zamówienia jako gotowe do przetworzenia. Ustawiając „Status zamówienia dla pomyślnej płatności” na „Płatność zaakceptowana”, Twój zespół natychmiast wie, że płatność została rozliczona. Jeśli klient próbuje zapłacić, ale transakcja się nie powiedzie, zamówienie zostanie oznaczone jako „Błąd płatności”, co pozwoli Ci na dalsze działania lub klientowi na ponowną próbę.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Perfect Money Account ID | Twój Perfect Money Account ID (np. U1234567) | Identyfikuje Twoje konto sprzedawcy Perfect Money do odbierania płatności. **KRYTYCZNE dla przetwarzania płatności.** |
| Konfiguracja modułu | Perfect Money Account Name | Twoja nazwa konta Perfect Money | Nazwa powiązana z Twoim kontem Perfect Money. |
| Konfiguracja modułu | Perfect Money Alternate Passphrase | Twoje alternatywne hasło Perfect Money | Klucz bezpieczeństwa do weryfikacji transakcji. Ustaw to w swoim koncie Perfect Money. **KRYTYCZNE dla bezpieczeństwa.** |
| Konfiguracja modułu | Włącz płatność Perfect Money | TAK | Przełącza widoczność Perfect Money jako opcji płatności na stronie kasy. |
| Konfiguracja modułu | Status zamówienia dla pomyślnej płatności | Płatność zaakceptowana | Status zamówienia PrestaShop przypisany do zamówień pomyślnie opłaconych za pośrednictwem Perfect Money. |
| Konfiguracja modułu | Status zamówienia dla błędu płatności | Błąd płatności | Status zamówienia PrestaShop przypisany do zamówień, w których płatność Perfect Money nie powiodła się. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moi klienci widzą błąd podczas próby płatności za pomocą Perfect Money.**
O:

- **Sprawdź ustawienia swojego konta Perfect Money:** Dokładnie sprawdź, czy Twoje „Perfect Money Account ID”, „Perfect Money Account Name” i „Perfect Money Alternate Passphrase” są wprowadzone *dokładnie* tak, jak pojawiają się w Twoim koncie sprzedawcy Perfect Money. Nawet mała literówka może spowodować błędy.
- **Zweryfikuj status konta Perfect Money:** Zaloguj się bezpośrednio na swoje konto Perfect Money, aby upewnić się, że jest aktywne, w dobrym stanie i skonfigurowane do odbierania płatności.
- **Przejrzyj logi błędów PrestaShop:** W panelu administracyjnym PrestaShop przejdź do **Zaawansowane > Logi**, aby sprawdzić, czy rejestrowane są jakieś konkretne błędy związane z modułem Perfect Money.

**P: Zamówienia nie są oznaczane jako „Płatność zaakceptowana” po pomyślnej płatności Perfect Money.**
O:

- **Sprawdź ustawienia statusu zamówienia:** Przejdź do konfiguracji modułu i upewnij się, że „Status zamówienia dla pomyślnej płatności” jest ustawiony na prawidłowy status (np. „Płatność zaakceptowana”).
- **Perfect Money IPN/Callback:** Upewnij się, że Twoje konto Perfect Money jest poprawnie skonfigurowane do wysyłania natychmiastowych powiadomień o płatności (IPN) lub wywołań zwrotnych do Twojego sklepu PrestaShop. Moduł opiera się na tych powiadomieniach w celu aktualizacji statusów zamówień. Chociaż moduł obsługuje adres URL, czasami ustawienia konta Perfect Money mogą zakłócać działanie.

**P: Perfect Money nie pojawia się jako opcja płatności na mojej stronie kasy.**
O:

- **Moduł włączony:** W konfiguracji modułu upewnij się, że „Włącz płatność Perfect Money” jest ustawione na „TAK”.
- **Moduł zainstalowany:** Sprawdź, czy moduł jest poprawnie zainstalowany i włączony w **Moduły > Menedżer modułów**.
- **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (w **Zaawansowane > Wydajność**) i pamięć podręczną przeglądarki. Czasami stare dane z pamięci podręcznej mogą uniemożliwić pojawienie się nowych opcji płatności.
- **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany tak, aby był kompatybilny, bardzo mocno dostosowane motywy mogą czasami wymagać drobnych korekt. Jeśli podejrzewasz konflikt motywu, spróbuj tymczasowo przełączyć się na domyślny motyw PrestaShop, aby sprawdzić, czy opcja się pojawi.

**P: Czy mogę dostosować logo lub tekst Perfect Money na stronie kasy?**
O: Moduł używa standardowego szablonu do wyświetlania opcji płatności. Zazwyczaj możesz dostosować tekst, przechodząc do **Lokalizacja > Tłumaczenia** w panelu administracyjnym PrestaShop, wybierając „Tłumaczenia zainstalowanych modułów”, wybierając swój motyw, a następnie znajdując moduł „Perfect Money”. W przypadku zmian logo, musiałbyś zmodyfikować plik szablonu modułu (`perfectmoney.tpl`) lub użyć nadpisań CSS w swoim motywie.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu Perfect Money dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł Perfect Money jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie główną klasę modułu (`PerfectMoney`) do instalacji, deinstalacji i konfiguracji, oraz klasy `ModuleFrontController` do obsługi przekierowania płatności i procesów walidacji. Integruje się z bramką płatności Perfect Money, używając modelu komunikacji serwer-serwer (IPN/callback) do potwierdzania transakcji i aktualizacji statusów zamówień.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery obsługują aspekty procesu płatności widoczne dla klienta, w tym przekierowanie do Perfect Money i obsługę wywołania zwrotnego po płatności.

- **`perfectmoney/controllers/front/index.php`**

  - **Nazwa klasy**: `PerfectMoneyIndexModuleFrontController`
  - **Klasa nadrzędna**: `ModuleFrontController`
  - **Odpowiedzialność**: Ten kontroler jest zazwyczaj odpowiedzialny za inicjowanie procesu płatności. Gdy klient wybierze Perfect Money i potwierdzi zamówienie, ten kontroler przygotowuje parametry żądania płatności (ID sprzedawcy, kwota, waluta, opis zamówienia, adresy URL powrotu) i przekierowuje przeglądarkę klienta do bramki płatności Perfect Money. Zbiera niezbędne szczegóły zamówienia z koszyka i konstruuje formularz płatności.
- **`perfectmoney/controllers/front/validation.php`**

  - **Nazwa klasy**: `PerfectMoneyValidationModuleFrontController`
  - **Klasa nadrzędna**: `ModuleFrontController`
  - **Odpowiedzialność**: Jest to kluczowy kontroler, który obsługuje wywołanie zwrotne (Instant Payment Notification - IPN) z Perfect Money po przetworzeniu płatności.
    - Odbiera dane POST z Perfect Money zawierające szczegóły transakcji i hash bezpieczeństwa.
    - Weryfikuje integralność i autentyczność powiadomienia o płatności za pomocą skonfigurowanego alternatywnego hasła.
    - Jeśli płatność jest ważna i pomyślna, aktualizuje status zamówienia PrestaShop (np. na „Płatność zaakceptowana”), tworzy wpis w historii zamówień i potencjalnie wysyła e-maile z potwierdzeniem zamówienia.
    - Jeśli płatność nie powiedzie się lub jest nieprawidłowa, odpowiednio aktualizuje status zamówienia (np. na „Błąd płatności”).
    - Następnie przekierowuje klienta z powrotem na odpowiednią stronę PrestaShop (np. stronę potwierdzenia zamówienia lub stronę błędu).

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Moduł nie wydaje się definiować żadnych niestandardowych klas rozszerzających `ObjectModel` ani innych klas rdzeniowych PrestaShop w dedykowanym katalogu `classes/`. Cała logika rdzeniowa jest prawdopodobnie hermetyzowana w głównej klasie modułu `PerfectMoney` (`index.php`) i kontrolerach front-office.

### 4.4 Zasoby JavaScript (`views/js/`)

W archiwum modułu nie wykryto niestandardowych plików JavaScript. Proces płatności jest obsługiwany głównie przez przekierowania po stronie serwera i własny interfejs płatności Perfect Money.

### 4.5 Arkusze stylów CSS (`views/css/`)

W archiwum modułu nie wykryto niestandardowych plików CSS. Stylizacja opcji płatności na stronie kasy jest prawdopodobnie dziedziczona z motywu PrestaShop lub stylów wbudowanych w szablon.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **`perfectmoney/views/admin.tpl`**

  - **Zakres**: Konfiguracja panelu administracyjnego.
  - **Cel**: Ten szablon służy do renderowania formularza konfiguracji modułu w panelu administracyjnym PrestaShop. Wyświetla pola wejściowe dla Perfect Money Account ID, Account Name, Alternate Passphrase oraz rozwijane listy wyboru statusu zamówienia. Używa standardowych pomocników formularzy i stylizacji PrestaShop.
- **`perfectmoney/views/perfectmoney.tpl`**

  - **Zakres**: Front-office (krok płatności w kasie).
  - **Cel**: Ten szablon jest odpowiedzialny za wyświetlanie opcji płatności Perfect Money klientowi na stronie kasy. Zazwyczaj zawiera tytuł metody płatności, opis i potencjalnie logo Perfect Money. Jest renderowany w ramach haka płatności (np. `displayPaymentOptions` w PS 1.7+ lub `displayPayment` w PS 1.6).
- **`perfectmoney/views/success_page.tpl`**

  - **Zakres**: Front-office (strona potwierdzenia/sukcesu zamówienia).
  - **Cel**: Ten szablon jest prawdopodobnie używany do wyświetlania niestandardowej wiadomości o sukcesie lub dodatkowych informacji klientowi po pomyślnej płatności Perfect Money, przed lub jako część standardowej strony potwierdzenia zamówienia. Może być renderowany przez kontroler `validation.php`.

### 4.7 Schemat bazy danych i mapa haków

- **Tabele bazy danych**:

  - Moduł nie wydaje się tworzyć żadnych niestandardowych tabel SQL.
  - Ustawienia konfiguracji (Perfect Money Account ID, Passphrase itp.) są przechowywane w tabeli `ps_configuration`, używając kluczy z prefiksem `PERFECTMONEY_`.
- **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayPaymentOptions` (PS 1.7+) | Na stronie kasy, krok płatności. | Renderuje opcję płatności Perfect Money za pomocą `perfectmoney.tpl`. |
| `displayPayment` (PS 1.6) | Na stronie kasy, krok płatności. | Renderuje opcję płatności Perfect Money za pomocą `perfectmoney.tpl`. |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Potencjalnie używany do ładowania zasobów specyficznych dla modułu (JS/CSS), jeśli takie były obecne, lub do tagów meta. (Nie wykryto zasobów, więc prawdopodobnie do inicjalizacji modułu lub kompatybilności). |
| `actionPaymentConfirmation` | Po potwierdzeniu statusu płatności zamówienia. | Może być używany do przetwarzania po płatności, chociaż główna aktualizacja statusu jest obsługiwana przez kontroler `validation.php`. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu i utworzeniu zamówienia. | Używany przez moduł do tworzenia zamówienia w PrestaShop z początkowym statusie przed przekierowaniem do Perfect Money. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu Perfect Money, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
