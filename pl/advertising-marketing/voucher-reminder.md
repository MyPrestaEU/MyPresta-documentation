---
title: "Voucher Reminder - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów dla modułu PrestaShop Voucher Reminder od MyPresta.eu."
sidebar:
  label: "Voucher Reminder - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Voucher Reminder na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-reminder.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/voucher-reminder/)
>
> ---


# Voucher Reminder

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Dostęp do konfiguracji zadania cron na Twoim serwerze jest niezbędny do automatycznego działania modułu.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji pierwszym ekranem, który zobaczysz, jest główna strona konfiguracji modułu Voucher Reminder. Ta strona jest kluczowa do ustawienia podstawowej funkcjonalności.

**URL zadania Cron:**

- **Co robi to ustawienie:** Wyświetla unikalny adres URL, który zadanie cron Twojego serwera musi wywoływać okresowo. Ten adres URL uruchamia moduł, aby sprawdzić wygasające kupony i wysłać przypomnienia.
- **Wpływ zmiany tego ustawienia:** Nie możesz bezpośrednio zmienić tego adresu URL. Jest on generowany przez moduł. Jeśli zadanie cron nie jest poprawnie skonfigurowane na Twoim serwerze, aby wywoływać ten adres URL, moduł nie będzie automatycznie wysyłał żadnych przypomnień.
- **Zalecana wartość:** Skopiuj ten adres URL dokładnie i użyj go do skonfigurowania zadania cron na swoim serwerze hostingowym.
- **Scenariusz / przykład dla sprzedawcy:** Utworzyłeś kilka reguł przypomnień, ale żadne e-maile nie są wysyłane. Pierwszą rzeczą do sprawdzenia jest, czy poprawnie skonfigurowałeś zadanie cron na swoim serwerze, używając tego adresu URL.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 Zarządzanie przypomnieniami o kuponach (Panel administracyjny > Moduły > Voucher Reminder > Voucher Reminders)

Tutaj definiujesz i zarządzasz rzeczywistymi regułami przypomnień. Każda reguła określa, kiedy przypomnienie powinno zostać wysłane i jakiego szablonu e-maila powinno użyć.

- **Nazwa ekranu i lokalizacja w menu:** **Przypomnienia o kuponach** (pod **Moduły > Voucher Reminder** w głównym menu PrestaShop).
- **Dostępne działania i ustawienia:**
  - **Lista przypomnień:** Zobaczysz tabelę zawierającą wszystkie zdefiniowane reguły przypomnień.
  - **Dodaj nowe przypomnienie:** Kliknij przycisk „Dodaj nowe”, aby utworzyć nową regułę przypomnienia.
    - **Przypomnij (godziny przed wygaśnięciem):**
      - **Co robi to ustawienie:** Jest to najważniejsze ustawienie dla reguły przypomnienia. Określa, ile godzin *przed* datą wygaśnięcia kuponu powinien zostać wysłany e-mail z przypomnieniem.
      - **Wpływ zmiany tego ustawienia:**
        - *Ustawione na 24:* E-mail z przypomnieniem zostanie wysłany dokładnie 24 godziny przed wygaśnięciem kuponu.
        - *Ustawione na 72:* E-mail z przypomnieniem zostanie wysłany 3 dni (72 godziny) przed wygaśnięciem.
      - **Zalecana wartość:** Zależy to od Twojej strategii. Typowe wartości to 24, 48, 72 godziny, a nawet 168 godzin (1 tydzień).
      - **Scenariusz / przykład dla sprzedawcy:** Chcesz dać klientom ostatnie przypomnienie dzień przed wygaśnięciem ich kuponu. Ustawisz to na `24`. Jeśli chcesz dać im tydzień wcześniej, ustawisz to na `168`.
    - **Tytuł:**
      - **Co robi to ustawienie:** Opisowa nazwa dla Twojej reguły przypomnienia, widoczna tylko w Panelu administracyjnym. Pomaga to zidentyfikować różne reguły przypomnień.
      - **Wpływ zmiany tego ustawienia:** Zmienia etykietę dla tej reguły w Twoim panelu administracyjnym. Brak wpływu na front office.
      - **Zalecana wartość:** Coś jasnego i opisowego, np. „24 godziny przed wygaśnięciem”, „Tydzień przed wygaśnięciem kuponu”.
      - **Scenariusz / przykład dla sprzedawcy:** Masz wiele przypomnień. Nazwanie ich „Przypomnienie 1-dniowe” i „Przypomnienie 3-dniowe” ułatwia zarządzanie.
    - **Tytuł e-maila:**
      - **Co robi to ustawienie:** Jest to temat e-maila, który otrzymają Twoi klienci.
      - **Wpływ zmiany tego ustawienia:** Bezpośrednio zmienia temat e-maili z przypomnieniami.
      - **Zalecana wartość:** Coś angażującego i jasnego, np. „Twój [Kod kuponu] wkrótce wygasa!”, „Nie przegap swojego rabatu!”.
      - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby e-mail wyróżniał się w skrzynce odbiorczej klienta. Temat taki jak „Ostatnia szansa: Twój rabat wkrótce wygasa!” jest bardziej skuteczny niż ogólny.
    - **Plik szablonu e-maila:**
      - **Co robi to ustawienie:** Określa, którego pliku szablonu e-maila (np. `voucher_reminder.html` i `voucher_reminder.txt`) moduł powinien użyć dla tego konkretnego przypomnienia. Pozwala to na posiadanie różnych projektów e-maili dla różnych terminów przypomnień.
      - **Wpływ zmiany tego ustawienia:** Określa zawartość i układ wysyłanego e-maila. Jeśli utworzysz niestandardowy szablon, wybierzesz jego nazwę tutaj.
      - **Zalecana wartość:** Użyj domyślnego szablonu, chyba że masz specyficzne potrzeby projektowe. Jeśli tworzysz niestandardowe szablony, upewnij się, że są one poprawnie umieszczone w katalogu `mails` Twojego motywu.
      - **Scenariusz / przykład dla sprzedawcy:** Chcesz wysłać delikatne przypomnienie e-mailem tydzień wcześniej i bardziej pilny e-mail „ostatnia szansa” 24 godziny wcześniej. Utworzysz dwa różne szablony e-maili i przypiszesz je do odpowiednich reguł przypomnień.
    - **Wyślij przypomnienie:**
      - **Co robi to ustawienie:** Prosty przełącznik ON/OFF, aby włączyć lub wyłączyć tę konkretną regułę przypomnienia.
      - **Wpływ zmiany tego ustawienia:**
        - *Włączone (Tak):* Moduł będzie wysyłał e-maile zgodnie z tą regułą.
        - *Wyłączone (Nie):* Ta reguła zostanie zignorowana i żadne e-maile nie zostaną wysłane.
      - **Zalecana wartość:** „Tak” po skonfigurowaniu reguły i gotowości do jej użycia.
      - **Scenariusz / przykład dla sprzedawcy:** Testujesz nową regułę przypomnienia i chcesz upewnić się, że jest idealna przed aktywowaniem jej dla wszystkich klientów. Będziesz ją trzymać wyłączoną podczas testowania.
  - **Przycisk Zapisz:** Stosuje wszystkie zmiany wprowadzone w regule przypomnienia.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. Zacznij od utworzenia jednej lub dwóch reguł przypomnień (np. 72 godziny i 24 godziny przed wygaśnięciem).
  2. Używaj jasnych tytułów i przekonujących tematów e-maili.
  3. Monitoruj „Historię przypomnień o kuponach”, aby sprawdzić, czy e-maile są wysyłane zgodnie z oczekiwaniami.
  4. Rozważ utworzenie niestandardowych szablonów e-maili dla różnych terminów przypomnień, aby dostosować swoją wiadomość.

#### 2.2.2 Historia przypomnień o kuponach (Panel administracyjny > Moduły > Voucher Reminder > History)

Ten ekran zawiera dziennik wszystkich e-maili z przypomnieniami, które zostały pomyślnie wysłane przez moduł.

- **Nazwa ekranu i lokalizacja w menu:** **Historia** (pod **Moduły > Voucher Reminder** w głównym menu PrestaShop).
- **Dostępne działania i ustawienia:**
  - **Lista wysłanych przypomnień:** Tabela wyświetlająca:
    - **ID:** Unikalny identyfikator wpisu historii.
    - **Data dostarczenia e-maila:** Kiedy e-mail został wysłany.
    - **Przypomnienie:** Która reguła przypomnienia (według tytułu) wywołała ten e-mail.
    - **Klient:** Klient, który otrzymał przypomnienie.
    - **Kupon:** Konkretny kod kuponu, o którym przypomniano.
- **Wpływ zmian:** Jest to dziennik tylko do odczytu. Nie możesz tutaj wprowadzać zmian, ale jest on nieoceniony do weryfikacji działania modułu.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie sprawdzaj tę historię, aby upewnić się, że przypomnienia są wysyłane zgodnie z oczekiwaniami. Jeśli zauważysz luki lub nieoczekiwane zachowanie, ten dziennik jest Twoim pierwszym punktem odniesienia do rozwiązywania problemów.

#### 2.2.3 Rezygnacje z subskrypcji (Panel administracyjny > Moduły > Voucher Reminder > Unsubscriptions)

Ten ekran wyświetla listę klientów, którzy zrezygnowali z otrzymywania przypomnień o kuponach.

- **Nazwa ekranu i lokalizacja w menu:** **Rezygnacje z subskrypcji** (pod **Moduły > Voucher Reminder** w głównym menu PrestaShop).
- **Dostępne działania i ustawienia:**
  - **Lista klientów, którzy zrezygnowali z subskrypcji:** Tabela wyświetlająca:
    - **ID:** Unikalny identyfikator wpisu rezygnacji z subskrypcji.
    - **E-mail:** Adres e-mail klienta, który zrezygnował z subskrypcji.
    - **IP:** Adres IP, z którego nastąpiła rezygnacja z subskrypcji.
    - **Data rezygnacji z subskrypcji:** Kiedy klient zrezygnował z subskrypcji.
  - **Dodaj nową rezygnację z subskrypcji:** Możesz ręcznie dodać adres e-mail do listy rezygnacji z subskrypcji.
    - **E-mail klienta:** Wprowadź adres e-mail, który chcesz usunąć z subskrypcji.
    - **IP:** (Opcjonalnie) Adres IP związany z rezygnacją z subskrypcji.
    - **Data:** (Opcjonalnie) Data rezygnacji z subskrypcji.
    - **Przycisk Zapisz:** Dodaje klienta do listy rezygnacji z subskrypcji.
- **Wpływ zmian:** Klienci wymienieni tutaj nie będą już otrzymywać e-maili z przypomnieniami o kuponach z Twojego sklepu, nawet jeśli mają wygasające kupony. Ręczne dodanie adresu e-mail zapewnia, że zostaną oni wypisani.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Chociaż klienci mogą sami zrezygnować z subskrypcji, ten ekran pozwala ręcznie dodawać klientów, jeśli skontaktują się z Tobą bezpośrednio z prośbą o usunięcie z list przypomnień. Jest to również dobre miejsce do monitorowania trendów rezygnacji z subskrypcji.

#### 2.2.4 index.php (vreminders/controllers/admin/index.php)

Ten plik jest zazwyczaj plikiem zastępczym lub przekierowaniem w strukturze administracyjnej PrestaShop i nie reprezentuje bezpośredniego, konfigurowalnego ekranu dla sprzedawcy. Jego celem jest zazwyczaj zapewnienie, że bezpośredni dostęp do katalogu jest ograniczony lub przekierowanie do głównej konfiguracji modułu.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | URL zadania Cron | (Wygenerowany URL) | Niezbędne do ustawienia automatyzacji po stronie serwera w celu wysyłania przypomnień. |
| **Przypomnienia o kuponach** | Przypomnij (godziny przed wygaśnięciem) | Różne (np. 24, 72) | Definiuje czas wysyłki e-maila z przypomnieniem w stosunku do wygaśnięcia kuponu. |
| | Tytuł | Opisowy (np. „Przypomnienie 1-dniowe”) | Wewnętrzna etykieta do identyfikacji reguł przypomnień w Panelu administracyjnym. |
| | Tytuł e-maila | Angażujący temat | Temat e-maila, który otrzymują klienci. |
| | Plik szablonu e-maila | `voucher_reminder` | Określa szablon e-maila używany dla tego przypomnienia. |
| | Wyślij przypomnienie | Tak | Aktywuje lub dezaktywuje konkretną regułę przypomnienia. |
| **Historia przypomnień o kuponach** | (Wszystkie pola) | N/A (Tylko do odczytu) | Dziennik wszystkich wysłanych e-maili z przypomnieniami do weryfikacji i rozwiązywania problemów. |
| **Rezygnacje z subskrypcji** | E-mail klienta | N/A | Ręcznie dodaj adresy e-mail klientów, aby zapobiec otrzymywaniu przez nich przypomnień. |
| | IP | N/A | (Opcjonalnie) Adres IP związany z rezygnacją z subskrypcji. |
| | Data | N/A | (Opcjonalnie) Data rezygnacji z subskrypcji. |

## 3. Rozwiązywanie problemów dla sprzedawcy i często zadawane pytania (FAQ)

**P: Moje przypomnienia nie są wysyłane. Co powinienem sprawdzić w pierwszej kolejności?**
O: Najczęstszą przyczyną jest nieprawidłowo skonfigurowane zadanie cron.

1. Przejdź do **Moduły > Voucher Reminder > Konfiguruj**.
2. Skopiuj dokładnie „URL zadania Cron”.
3. Zaloguj się do panelu sterowania swojego hostingu (cPanel, Plesk itp.) i przejdź do sekcji „Zadania Cron”.
4. Utwórz nowe zadanie cron, które wywołuje ten adres URL co 5-15 minut. Polecenie zazwyczaj wygląda mniej więcej tak: `wget -q -O /dev/null "TWÓJ_URL_ZADANIA_CRON_TUTAJ"` lub `curl -s "TWÓJ_URL_ZADANIA_CRON_TUTAJ" > /dev/null`.
5. Upewnij się również, że poszczególne reguły przypomnień są włączone („Wyślij przypomnienie” jest ustawione na „Tak”) w **Moduły > Voucher Reminder > Voucher Reminders**.

**P: Klienci skarżą się, że nie otrzymują przypomnień, ale historia pokazuje, że zostały wysłane.**
O: Zazwyczaj wskazuje to na problemy z dostarczaniem e-maili.

1. **Sprawdź foldery ze spamem:** Doradź klientom, aby sprawdzili swoje foldery ze spamem lub niechcianymi wiadomościami.
2. **Konfiguracja serwera pocztowego:** Upewnij się, że ustawienia poczty e-mail Twojego sklepu PrestaShop (w **Zaawansowane > E-mail**) są poprawnie skonfigurowane, a Twój serwer nie jest na czarnej liście. Używanie serwera SMTP (takiego jak SendGrid, Mailgun itp.) jest często bardziej niezawodne niż funkcja `mail()` PHP.
3. **Problemy z szablonem e-maila:** Upewnij się, że Twoje szablony e-maili są prawidłowym HTML/tekstem i nie zawierają uszkodzonych linków ani obrazów, które mogłyby wywołać filtry antyspamowe.

**P: Czy mogę dostosować szablony e-maili?**
O: Tak!

1. Moduł używa standardowych szablonów e-maili PrestaShop. Domyślne pliki szablonów znajdziesz w `modules/vreminders/mails/en/` (lub w folderze Twojego języka).
2. **Najlepsza praktyka:** Skopiuj te pliki do katalogu `mails/en/` Twojego aktywnego motywu (np. `themes/yourtheme/mails/en/`). W ten sposób Twoje dostosowania nie zostaną nadpisane podczas aktualizacji modułu.
3. Edytuj pliki `.html` i `.txt`, aby dopasować je do Twojej marki i wiadomości. Możesz używać zmiennych Smarty dostępnych w szablonach e-maili PrestaShop.
4. Jeśli utworzysz zupełnie nowe pliki szablonów (np. `my_custom_reminder.html`), będziesz musiał wybrać `my_custom_reminder` w ustawieniu „Plik szablonu e-maila” dla swojej reguły przypomnienia.

**P: Jak przetestować przypomnienia bez wysyłania ich do prawdziwych klientów?**
O:

1. Utwórz testowe konto klienta w swoim sklepie.
2. Ręcznie utwórz kod kuponu dla tego testowego klienta z datą wygaśnięcia za kilka godzin lub dni.
3. Skonfiguruj regułę przypomnienia z krótkim czasem „Przypomnij (godziny przed wygaśnięciem)” (np. 1 godzina).
4. Zamiast czekać na zadanie cron, możesz ręcznie wywołać adres URL cron w swojej przeglądarce (chociaż nie jest to zalecane dla środowiska produkcyjnego).
5. Sprawdź „Historię przypomnień o kuponach” i skrzynkę odbiorczą testowego klienta.
6. Po zadowoleniu usuń testowy kupon i regułę przypomnienia, a następnie skonfiguruj swoje reguły produkcyjne.

**P: Co się stanie, jeśli klient użyje swojego kuponu po wysłaniu przypomnienia, ale przed jego wygaśnięciem?**
O: Moduł jest zaprojektowany tak, aby wysyłać przypomnienia tylko dla *niewykorzystanych* kuponów. Jeśli klient użyje swojego kuponu, nie będzie on już uważany za „aktywny” i „niewykorzystany”, więc żadne dalsze przypomnienia dotyczące tego konkretnego kuponu nie zostaną wysłane.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Voucher Reminder” jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując zasady MVC. Jego podstawowa funkcjonalność opiera się na zadaniu cron, które okresowo sprawdza wygasające kupony i wysyła e-maile na podstawie skonfigurowanych reguł. Wykorzystuje `ObjectModel` PrestaShop do zarządzania swoimi niestandardowymi encjami (przypomnienia, historia, rezygnacje z subskrypcji) oraz standardowe mechanizmy e-mailowe do komunikacji. Główna logika modułu znajduje się w `cronjob.php` (który działa jako główna klasa modułu) oraz dedykowanych kontrolerach administracyjnych do operacji CRUD na jego niestandardowych danych.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:

  - `controllers/front/CronJob.php`
    - **Nazwa klasy i klasa nadrzędna**: `VremindersCronJobModuleFrontController` rozszerza `ModuleFrontController`.
    - **Odpowiedzialność**: Ten kontroler jest punktem wejścia dla zadania cron modułu. Gdy adres URL cron (wygenerowany w konfiguracji modułu) jest dostępny, ten kontroler jest wykonywany. Zawiera logikę do pobierania wygasających kuponów, sprawdzania ich pod kątem skonfigurowanych reguł przypomnień i wysyłania e-maili. Zazwyczaj nie renderuje żadnego wizualnego wyjścia, ale wykonuje przetwarzanie w tle.
  - `controllers/front/index.php`
    - **Nazwa klasy i klasa nadrzędna**: Nie jest klasą, zazwyczaj pusty plik lub proste `die('No direct script access allowed')` w celu zapobieżenia bezpośredniemu listowaniu katalogów lub dostępowi.
- **Kontrolery administracyjne Back-Office**:

  - `controllers/admin/AdminVoucherReminders.php`
    - **Nazwa zakładki i zarządzana encja**: Zarządza listą i formularzami „Przypomnień o kuponach” w Panelu administracyjnym. Obsługuje operacje CRUD dla encji `VoucherReminder` (która mapuje się do tabeli `ps_vr`).
  - `controllers/admin/AdminVoucherRemindersHistory.php`
    - **Nazwa zakładki i zarządzana encja**: Zarządza listą „Historii przypomnień o kuponach” w Panelu administracyjnym. Wyświetla dziennik wysłanych przypomnień tylko do odczytu, mapując się do encji `VoucherReminderHistory` (która mapuje się do tabeli `ps_vr_history`).
  - `controllers/admin/AdminVRemindersUnsub.php`
    - **Nazwa zakładki i zarządzana encja**: Zarządza listą i formularzami „Rezygnacji z subskrypcji” w Panelu administracyjnym. Obsługuje operacje CRUD dla encji `VoucherReminderUnsub` (która mapuje się do tabeli `ps_vr_vunsub`).
  - `controllers/admin/index.php`
    - **Nazwa klasy i klasa nadrzędna**: Nie jest klasą, zazwyczaj pusty plik lub proste `die('No direct script access allowed')` w celu zapobieżenia bezpośredniemu listowaniu katalogów lub dostępowi.

### 4.3 Klasy i modele rdzenia (`classes/`)

Dossier modułu nie wskazuje na istnienie jawnego katalogu `classes/`. Oznacza to, że podstawowe klasy `ObjectModel` są prawdopodobnie zdefiniowane bezpośrednio w głównym pliku modułu (`cronjob.php`) lub w odpowiednich plikach kontrolerów administracyjnych. Na podstawie typowej struktury modułów PrestaShop i zidentyfikowanych encji, oczekuje się, że następujące klasy `ObjectModel` będą obecne, prawdopodobnie zdefiniowane w `cronjob.php` lub `AdminVoucherReminders.php`, `AdminVoucherRemindersHistory.php`, `AdminVRemindersUnsub.php`:

- **`VoucherReminder` (lub podobne)**

  - **Tabela bazy danych**: `ps_vr` (lub `_vreminders_vr`)
  - **Rozszerza `ObjectModel`**: Tak.
  - **Pola `$definition`**: Oczekiwane pola to `id_vr`, `remind_hours`, `title`, `email_title`, `email_template`, `active`.
  - **Kluczowe metody publiczne**: Metody do dodawania, aktualizowania, usuwania reguł przypomnień i potencjalnie metody do pobierania aktywnych reguł.
- **`VoucherReminderHistory` (lub podobne)**

  - **Tabela bazy danych**: `ps_vr_history` (lub `_vreminders_vr_history`)
  - **Rozszerza `ObjectModel`**: Tak.
  - **Pola `$definition`**: Oczekiwane pola to `id_vr_history`, `id_vr`, `id_customer`, `id_cart_rule`, `date_add`.
  - **Kluczowe metody publiczne**: Metody do logowania wysłanych przypomnień.
- **`VoucherReminderUnsub` (lub podobne)**

  - **Tabela bazy danych**: `ps_vr_vunsub` (lub `_vreminders_vr_vunsub`)
  - **Rozszerza `ObjectModel`**: Tak.
  - **Pola `$definition`**: Oczekiwane pola to `id_vunsub`, `email`, `ip`, `date_add`.
  - **Kluczowe metody publiczne**: Metody do zarządzania rezygnacjami z subskrypcji, w tym dodawanie i sprawdzanie adresów e-mail, które zrezygnowały z subskrypcji.

### 4.4 Zasoby JavaScript (`views/js/`)

Dossier modułu nie wskazuje na pliki JavaScript. Sugeruje to, że moduł opiera się wyłącznie na podstawowych funkcjonalnościach JavaScript PrestaShop dla swoich formularzy i list w Panelu administracyjnym, lub że wszelkie minimalne JS są wbudowane bezpośrednio w szablony.

### 4.5 Arkusze stylów CSS (`views/css/`)

Dossier modułu nie wskazuje na pliki CSS. Sugeruje to, że moduł opiera się wyłącznie na podstawowym CSS Panelu administracyjnego PrestaShop dla swoich interfejsów administracyjnych, a wszelkie style front-office (dla e-maili) są obsługiwane w samych szablonach e-maili.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony administracyjne (`views/templates/admin/`)**:

  - `vreminders/views/templates/admin/order_reminders/helpers/form/form.tpl`
    - **Cel**: Ten szablon jest prawdopodobnie używany przez `AdminVoucherRemindersController` do renderowania formularza dodawania/edycji dla poszczególnych reguł przypomnień o kuponach. Zawierałby pola wejściowe dla „Przypomnij (godziny przed wygaśnięciem)”, „Tytuł”, „Tytuł e-maila”, „Plik szablonu e-maila” i „Wyślij przypomnienie”.
- **Szablony hooków (`views/templates/hook/`)**:

  - `vreminders/views/templates/hook/form.tpl`
    - **Cel**: Ten szablon może być ogólnym szablonem formularza lub specyficznym dla hooka, który wyświetla formularz. Biorąc pod uwagę charakter modułu, jest mniej prawdopodobne, że będzie to widoczny formularz front-office, a bardziej prawdopodobne, że będzie to wewnętrzny komponent lub przestarzały hook. Bez dalszego kontekstu, jego dokładne umiejscowienie w front-office jest niejasne, ale może to być formularz rezygnacji z subskrypcji lub podobny.
  - `vreminders/views/templates/hook/header.tpl`
    - **Cel**: Ten szablon jest renderowany w hooku `displayHeader`. Jest zazwyczaj używany do dołączania plików CSS lub JavaScript, meta tagów lub innych elementów, które muszą zostać załadowane w sekcji `<head>` dokumentu HTML. Dla tego modułu może być używany do dołączania wszelkich niezbędnych JS dla zadania cron lub do ustawiania specyficznych meta tagów, chociaż dossier nie wskazuje na pliki JS/CSS. Może to być również placeholder.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - `ps_vr` (lub `_vreminders_vr`): Przechowuje konfigurację dla każdej reguły przypomnienia o kuponie.
    - `id_vr` (PK, INT)
    - `remind_hours` (INT)
    - `title` (VARCHAR)
    - `email_title` (VARCHAR)
    - `email_template` (VARCHAR)
    - `active` (TINYINT)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_vr_history` (lub `_vreminders_vr_history`): Loguje każdy wysłany e-mail z przypomnieniem.
    - `id_vr_history` (PK, INT)
    - `id_vr` (FK do `ps_vr.id_vr`, INT)
    - `id_customer` (FK do `ps_customer.id_customer`, INT)
    - `id_cart_rule` (FK do `ps_cart_rule.id_cart_rule`, INT)
    - `date_add` (DATETIME)
  - `ps_vr_vunsub` (lub `_vreminders_vr_vunsub`): Przechowuje adresy e-mail klientów, którzy zrezygnowali z subskrypcji przypomnień.
    - `id_vunsub` (PK, INT)
    - `email` (VARCHAR)
    - `ip` (VARCHAR)
    - `date_add` (DATETIME)
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Do dołączania wszelkich niezbędnych zasobów (JS/CSS) lub meta tagów dla modułu. |
| `actionModuleInstall` | Podczas instalacji modułu. | Do tworzenia tabel bazy danych i domyślnej konfiguracji. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Do usuwania tabel bazy danych i konfiguracji. |
| `displayAdminProductsExtra` (lub podobne) | Potencjalnie na stronach produktów w BO. | Jeśli moduł miałby ustawienia przypomnień specyficzne dla produktu, ale nie wskazane w dossier. |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony back-office. | Do dołączania JS/CSS specyficznego dla administratora lub kontekstu dla konfiguracji modułu. |
| `moduleRoutes` | Podczas inicjalizacji przepisywania adresów URL. | Do definiowania niestandardowych przyjaznych adresów URL dla kontrolerów front-office (np. URL zadania cron, URL rezygnacji z subskrypcji). |

Główna logika modułu do wysyłania przypomnień jest wywoływana przez kontroler front-office `CronJob.php`, który jest wywoływany za pośrednictwem zadania cron po stronie serwera, a nie bezpośrednio przez hook PrestaShop.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dalszej pomocy z modułem „Voucher Reminder”, prosimy odwołać się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie kompleksowego wsparcia i płynnego działania Twojego modułu.
