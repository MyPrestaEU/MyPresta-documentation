---
title: "Powiadomienie o nowym koncie klienta - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla programistów modułu PrestaShop „Powiadomienie o nowym koncie klienta” od MyPresta.eu."
sidebar:
  label: "Powiadomienie o nowym koncie klienta - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Notification about new customer account na MyPresta.eu](https://mypresta.eu/modules/administration-tools/notification-about-new-customer-account.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/notification-about-new-customer-account/)
>
> ---


# Powiadomienie o nowym koncie klienta

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i domyślnie włączone w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Powiadomienie o nowym koncie klienta”. Zostanie wyświetlony główny ekran konfiguracji.

#### **1. Wyślij powiadomienie do właściciela sklepu o nowym koncie klienta**

- **Co robi to ustawienie:** Ten przełącznik kontroluje, czy Ty, właściciel sklepu, otrzymujesz powiadomienie e-mail, gdy nowy klient zarejestruje się w Twoim sklepie.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Za każdym razem, gdy klient pomyślnie utworzy konto w front-office Twojego sklepu, e-mail zostanie wysłany na adres(y) e-mail podany(e) w polu „Adres(y) e-mail do powiadomień” poniżej.
  - *Gdy wyłączone (NIE):* Nie będziesz otrzymywać żadnych powiadomień e-mail o nowych rejestracjach klientów.
- **Zalecana wartość:** TAK.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz być natychmiast świadomy nowych rejestracji klientów, aby śledzić wzrost lub identyfikować potencjalnych klientów do kampanii powitalnej. Włączenie tego zapewnia otrzymanie tych kluczowych informacji.

#### **2. Adres(y) e-mail do powiadomień**

- **Co robi to ustawienie:** To pole określa adres(y) e-mail, na które będą wysyłane powiadomienia o nowych rejestracjach klientów.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiony jest jeden lub więcej adresów e-mail:* Powiadomienia zostaną dostarczone na te adresy. Jeśli wprowadzisz wiele adresów, oddziel je przecinkiem (np. `admin@twojsklep.com, support@twojsklep.com`).
  - *Gdy pozostawione puste:* Nawet jeśli „Wyślij powiadomienie do właściciela sklepu” jest włączone, żadne e-maile nie zostaną wysłane, ponieważ nie ma odbiorcy.
- **Zalecana wartość:** Twój główny adres e-mail administracji sklepu lub dedykowany adres e-mail zespołu (np. `info@twojsklep.com`).
- **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby zarówno Ty, jak i Twój zespół obsługi klienta otrzymywali powiadomienia o nowych rejestracjach. Wprowadziłbyś tutaj `twojeimie@twojsklep.com, support@twojsklep.com`.

#### **3. Wyślij powiadomienie do klienta, jeśli administrator tworzy nowe konto**

- **Co robi to ustawienie:** Ten przełącznik określa, czy powitalny e-mail jest automatycznie wysyłany do klienta, jeśli jego konto jest ręcznie tworzone przez administratora w Panelu administracyjnym PrestaShop (np. poprzez Klienci > Dodaj nowego klienta).
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Gdy Ty lub inny administrator utworzycie nowe konto klienta w Panelu administracyjnym, nowo utworzony klient automatycznie otrzyma powitalny e-mail. Ten e-mail zazwyczaj zawiera dane logowania lub potwierdzenie utworzenia konta.
  - *Gdy wyłączone (NIE):* Klienci, których konta są ręcznie tworzone w Panelu administracyjnym, nie otrzymają żadnego automatycznego powitalnego e-maila od modułu. W razie potrzeby musiałbyś ich poinformować ręcznie.
- **Zalecana wartość:** TAK.
- **Scenariusz / przykład dla sprzedawcy:** Często tworzysz konta dla klientów B2B lub dla klientów, którzy składają zamówienia telefonicznie. Włączenie tego zapewnia, że otrzymają natychmiastowy, profesjonalny e-mail powitalny bez konieczności ręcznego komponowania i wysyłania go za każdym razem.

#### **4. Przycisk Zapisz**

- **Co to robi:** Po wprowadzeniu jakichkolwiek zmian w powyższych ustawieniach, musisz kliknąć ten przycisk, aby zastosować i zapisać nową konfigurację.
- **Efekt kliknięcia:** Twoje zmiany zostają zapisane w bazie danych, a moduł zacznie działać zgodnie z nowymi ustawieniami natychmiast.
- **Zalecane działanie:** Zawsze kliknij „Zapisz” po zmodyfikowaniu dowolnego ustawienia.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyślij powiadomienie do właściciela sklepu o nowym koncie klienta | TAK | Kontroluje, czy właściciel sklepu otrzymuje e-mail o nowej rejestracji klienta. |
| Konfiguracja modułu | Adres(y) e-mail do powiadomień | Główny adres e-mail Twojego sklepu | Określa odbiorcę(ów) powiadomień dla właściciela (oddzielone przecinkami). |
| Konfiguracja modułu | Wyślij powiadomienie do klienta, jeśli administrator tworzy nowe konto | TAK | Kontroluje, czy klient otrzymuje powitalny e-mail, gdy administrator tworzy jego konto. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Nie otrzymuję powiadomień o nowych klientach, ale moduł jest włączony. Co powinienem sprawdzić?**
O1:

-   **Sprawdź adresy e-mail:** Dokładnie sprawdź pole „Adres(y) e-mail do powiadomień” w konfiguracji modułu. Upewnij się, że jest poprawnie wpisany i nie ma literówek. Jeśli jest ich wiele, upewnij się, że są oddzielone przecinkami.
-   **Folder spamu:** Sprawdź folder spamu lub wiadomości-śmieci w swojej poczcie e-mail. Powiadomienia mogą być tam filtrowane.
-   **Ustawienia e-mail PrestaShop:** Zweryfikuj, czy główne ustawienia e-mail PrestaShop (Zaawansowane > E-mail) są poprawnie skonfigurowane i czy e-maile są wysyłane pomyślnie. Możesz wysłać testowy e-mail stamtąd.
-   **Problemy z e-mailem hostingowym:** Skontaktuj się z dostawcą hostingu, aby upewnić się, że nie ma żadnych ograniczeń wysyłania e-maili po stronie serwera ani problemów z Twoim serwerem pocztowym.

**P2: Moi klienci nie otrzymują e-maili powitalnych, gdy tworzę ich konta w Panelu administracyjnym.**
O2:

-   **Ustawienie modułu:** Upewnij się, że opcja „Wyślij powiadomienie do klienta, jeśli administrator tworzy nowe konto” jest ustawiona na TAK w konfiguracji modułu.
-   **E-mail klienta:** Zweryfikuj, czy adres e-mail wprowadzony dla klienta w Panelu administracyjnym jest poprawny i ważny.
-   **Folder spamu klienta:** Doradź klientowi, aby sprawdził swój folder spamu lub wiadomości-śmieci.
-   **Ustawienia e-mail PrestaShop:** Jak wyżej, upewnij się, że ogólne ustawienia e-mail Twojego sklepu działają.

**P3: Czy mogę dostosować treść e-maili powiadomień?**
O3: Ten moduł, w swojej obecnej wersji, wysyła standardowe e-maile systemowe PrestaShop. Dostosowanie treści zazwyczaj wymagałoby bezpośredniej modyfikacji szablonów e-mail PrestaShop (znajdujących się w katalogu `mails/` dla Twojego języka) lub kodu rdzenia modułu, co nie jest zalecane dla sprzedawców. W celu zaawansowanej personalizacji skonsultuj się z programistą.

**P4: Czy ten moduł spowolni mój sklep?**
O4: Nie. Ten moduł wykonuje bardzo lekką operację (wysyłanie e-maila) tylko wtedy, gdy tworzone jest nowe konto klienta. Nie dodaje żadnego obciążenia do ładowania stron ani ogólnej wydajności sklepu.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem „Powiadomienie o nowym koncie klienta”.

### 4.1 Przegląd architektury

Moduł `registernotification` to standardowy moduł PrestaShop, który wykorzystuje wzorzec zbliżony do MVC. Wykorzystuje on głównie system hooków PrestaShop do przechwytywania zdarzeń związanych z rejestracją klienta, a następnie używa klasy `Mail` PrestaShop do wysyłania powiadomień. Konfiguracja modułu jest przechowywana bezpośrednio w tabeli `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje żadnych niestandardowych kontrolerów front-office ani back-office. Cała logika jest hermetyzowana w głównej klasie modułu i jej metodzie `getContent()` do konfiguracji.

### 4.3 Klasy rdzenia i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani instancji `ObjectModel`. Cała logika rdzenia znajduje się w głównej klasie `registernotification`.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie zawiera żadnych niestandardowych plików szablonów Smarty. Opiera się na domyślnych szablonach e-mail PrestaShop dla powiadomień klientów.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Wszystkie jego ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy z prefiksem `REGISTERNOTIFICATION_`.

    -   Wpisy `PS_CONFIGURATION`:
        -   `REGISTERNOTIFICATION_SEND_OWNER`: Przechowuje wartość logiczną (0 lub 1) dla wysyłania powiadomień do właściciela sklepu.
        -   `REGISTERNOTIFICATION_EMAIL_ADDRESSES`: Przechowuje ciąg adresów e-mail oddzielonych przecinkami dla powiadomień właściciela.
        -   `REGISTERNOTIFICATION_SEND_CUSTOMER_ADMIN`: Przechowuje wartość logiczną (0 lub 1) dla wysyłania powiadomień do klientów, gdy są tworzone przez administratora.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Wykonywany natychmiast po pomyślnym dodaniu nowego konta klienta do bazy danych. | Ten hook jest używany do wyzwalania powiadomienia e-mail do właściciela sklepu, gdy klient rejestruje się za pośrednictwem front-office. Wyzwala również powitalny e-mail do klienta, jeśli jego konto zostało utworzone przez administratora w back-office. |
| `displayBackOfficeHeader` | Wykonywany podczas renderowania nagłówka Panelu administracyjnego. | Zazwyczaj używany do dodawania CSS/JS lub wyświetlania alertów w Panelu administracyjnym. Chociaż jest wymieniony jako potencjalny hook, jego podstawowe zastosowanie w tym module dotyczyłoby wyświetlania komunikatu o sukcesie/błędzie po zapisaniu konfiguracji lub potencjalnie do dodawania zasobów specyficznych dla modułu (chociaż żadne nie są obecne). |

### 4.8 Struktura plików modułu (`registernotification/`)

-   `index.php`: Główny plik modułu. Ten plik zawiera klasę `registernotification`, która rozszerza `Module`. Obsługuje:
    -   `__construct()`: Inicjalizacja modułu, ustawianie nazwy, zakładki, wersji, autora itp.
    -   `install()`: Rejestruje niezbędne hooki (`actionCustomerAccountAdd`, `displayBackOfficeHeader`) i ustawia domyślne wartości konfiguracyjne w `ps_configuration`.
    -   `uninstall()`: Wyrejestrowuje hooki i usuwa wartości konfiguracyjne.
    -   `getContent()`: Renderuje formularz konfiguracji modułu w Panelu administracyjnym, obsługuje przesyłanie formularza i aktualizuje `ps_configuration`.
    -   `hookActionCustomerAccountAdd($params)`: Główna logika wysyłania e-maili. Sprawdza konfigurację modułu i używa `Mail::Send()` do wysyłania e-maili do właściciela i/lub nowego klienta w zależności od kontekstu tworzenia konta.
    -   `hookDisplayBackOfficeHeader()`: Potencjalnie używany do wyświetlania komunikatów potwierdzających po zapisaniu konfiguracji.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji, poprawek błędów i oficjalnego wsparcia dla modułu „Powiadomienie o nowym koncie klienta”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
