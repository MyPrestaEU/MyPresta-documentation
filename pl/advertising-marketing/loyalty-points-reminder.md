---
title: "Przypomnienie o punktach lojalnościowych - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop 'Przypomnienie o punktach lojalnościowych' od MyPresta.eu."
sidebar:
  label: "Przypomnienie o punktach lojalnościowych - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Loyalty points reminder na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points-reminder.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/loyalty-points-reminder/)
>
> ---


# Przypomnienie o punktach lojalnościowych

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Moduł opiera się na natywnych funkcjach poczty PrestaShop i możliwościach zadań cron.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Przypomnienie o punktach lojalnościowych)

Jest to główny i jedyny ekran konfiguracji modułu „Przypomnienie o punktach lojalnościowych”. Tutaj zdefiniujesz, jak i kiedy wysyłane są e-maile z przypomnieniami.

#### **Włącz / Wyłącz moduł**

- **Co robi to ustawienie:** Jest to główny przełącznik modułu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączony:* Moduł będzie aktywnie sprawdzał wygasające punkty lojalnościowe i wysyłał e-maile z przypomnieniami zgodnie z innymi ustawieniami.
  - *Gdy wyłączony:* Moduł nie będzie wysyłał żadnych e-maili z przypomnieniami, niezależnie od innych ustawień.
- **Zalecana wartość:** TAK (po skonfigurowaniu pozostałych ustawień).
- **Scenariusz / przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz zacząć przypominać klientom. Włączyłbyś to po ustawieniu dni przed wygaśnięciem.

#### **Dni przed wygaśnięciem, aby wysłać przypomnienie**

- **Co robi to ustawienie:** Określa, ile dni *przed* wygaśnięciem punktów lojalnościowych klienta zostanie wysłany e-mail z przypomnieniem.
- **Efekt zmiany tego ustawienia:**
  - *Jeśli ustawiono na 7:* Klienci otrzymają e-mail 7 dni przed wygaśnięciem ich punktów.
  - *Jeśli ustawiono na 30:* Klienci otrzymają e-mail 30 dni przed wygaśnięciem ich punktów.
- **Zalecana wartość:** 7-14 dni. Daje to klientom wystarczająco dużo czasu na reakcję, nie będąc zbyt wcześnie, aby zapomnieli.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz dać klientom tydzień na wykorzystanie ich punktów. Ustawisz to na „7”. Jeśli chcesz dać im więcej swobody, być może „14”.

#### **URL zadania Cron**

- **Co robi to ustawienie:** Wyświetla unikalny URL, który musisz skonfigurować jako zadanie cron na swoim serwerze. Zadanie cron to zaplanowane zadanie, które nakazuje Twojemu serwerowi uruchomienie określonego skryptu w regularnych odstępach czasu (np. raz dziennie). W ten sposób moduł automatycznie sprawdza wygasające punkty i wysyła e-maile bez konieczności ręcznego wykonywania czegokolwiek.
- **Efekt zmiany tego ustawienia:** Nie możesz bezpośrednio zmienić tego ustawienia. Jest to wygenerowany URL.
  - *Jeśli zadanie cron jest poprawnie skonfigurowane:* Moduł będzie działał automatycznie, wysyłając e-maile zgodnie z konfiguracją.
  - *Jeśli zadanie cron NIE jest skonfigurowane:* Moduł nigdy nie wyśle żadnych e-maili z przypomnieniami, nawet jeśli jest włączony.
- **Zalecana wartość:** Skopiuj ten URL i skonfiguruj go jako codzienne zadanie cron na swoim serwerze hostingowym.
- **Scenariusz / przykład dla sprzedawcy:** Po skonfigurowaniu ustawienia „Dni przed wygaśnięciem” skopiowałbyś ten URL i wkleił go do harmonogramu zadań cron w panelu sterowania hostingu (np. cPanel, Plesk lub bezpośredni dostęp do serwera). Zazwyczaj ustawiałbyś go na uruchamianie raz na 24 godziny.

#### **Testowy adres e-mail**

- **Co robi to ustawienie:** Pozwala wysłać testowy e-mail z przypomnieniem na określony adres, aby upewnić się, że moduł działa poprawnie, a treść e-maila wygląda dobrze.
- **Efekt zmiany tego ustawienia:**
  - *Wprowadzenie adresu e-mail i kliknięcie „Wyślij testowy e-mail”:* E-mail zostanie wysłany na podany adres, symulując przypomnienie o punktach lojalnościowych. Ten e-mail będzie zawierał dane zastępcze, ponieważ jest to test.
- **Zalecana wartość:** Użyj własnego adresu e-mail lub adresu współpracownika do testowania.
- **Scenariusz / przykład dla sprzedawcy:** Przed uruchomieniem chcesz zobaczyć, jak wygląda e-mail z przypomnieniem. Wprowadziłbyś tutaj swój adres e-mail i kliknął przycisk testowy.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Włącz / Wyłącz moduł** | TAK | Główny przełącznik do aktywacji lub dezaktywacji e-maili z przypomnieniami. |
| Konfiguracja modułu | **Dni przed wygaśnięciem, aby wysłać przypomnienie** | 7-14 dni | Określa, ile dni przed wygaśnięciem punktów zostanie wysłany e-mail. |
| Konfiguracja modułu | **URL zadania Cron** | Skopiuj i ustaw codziennie | Niezbędne do automatycznego wysyłania e-maili; musi być skonfigurowane na Twoim serwerze. |
| Konfiguracja modułu | **Testowy adres e-mail** | Twój e-mail do testowania | Wysyła przykładowy e-mail z przypomnieniem w celu weryfikacji treści i dostarczenia. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moi klienci nie otrzymują e-maili z przypomnieniami. Co powinienem sprawdzić?**
O:

1.  **Czy moduł jest włączony?** Przejdź do konfiguracji modułu i upewnij się, że „Włącz / Wyłącz moduł” jest ustawione na TAK.
2.  **Czy zadanie cron jest poprawnie skonfigurowane?** To najczęstszy problem. Moduł opiera się na zadaniu cron, aby działać automatycznie. Skopiuj „URL zadania Cron” z konfiguracji modułu i upewnij się, że jest poprawnie skonfigurowane na Twoim serwerze hostingowym, aby uruchamiało się codziennie.
3.  **Sprawdź ustawienia e-mail PrestaShop:** Przejdź do **Zaawansowane > E-mail** w swoim Panelu administracyjnym. Wyślij stamtąd testowy e-mail, aby upewnić się, że system e-mail Twojego sklepu działa.
4.  **Sprawdź foldery spamu:** Poproś klientów o sprawdzenie folderów spamu lub śmieci.
5.  **Wyczyść pamięć podręczną Smarty:** Czasami zmiany szablonów lub aktualizacje modułów wymagają wyczyszczenia pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność**, przewiń w dół do „Wyczyść pamięć podręczną” i kliknij „Wyczyść pamięć podręczną”.

**P: Testowy e-mail działa, ale klienci nadal nie otrzymują przypomnień.**
O: To zdecydowanie sugeruje, że problemem jest zadanie cron. Testowy e-mail wykorzystuje natychmiastowe wysyłanie poczty PrestaShop, podczas gdy rzeczywiste przypomnienia zależą od uruchomienia procesu w tle modułu przez zadanie cron. Dokładnie sprawdź konfigurację zadania cron u swojego dostawcy hostingu.

**P: Czy mogę dostosować treść e-maila z przypomnieniem?**
O: Moduł używa standardowych szablonów e-mail PrestaShop. Zazwyczaj pliki szablonów e-mail znajdziesz w katalogu `mails/` Twojego motywu (np. `themes/yourtheme/mails/en/loyalty_points_reminder.html` i `loyalty_points_reminder.txt`). Jeśli te pliki nie istnieją, moduł użyje domyślnych szablonów poczty PrestaShop. Możesz je nadpisać w swoim motywie, aby dostosować tekst i wygląd.

**P: Co się stanie, jeśli klient nie ma żadnych punktów lojalnościowych?**
O: Moduł jest zaprojektowany tak, aby wysyłać e-maile tylko do klientów, którzy faktycznie mają punkty lojalnościowe, które zbliżają się do daty wygaśnięcia. Jeśli klient nie ma punktów lub jego punkty nie wygasają wkrótce, nie otrzyma e-maila.

**P: Czy ten moduł działa z niestandardowymi modułami punktów lojalnościowych?**
O: Ten moduł jest zaprojektowany do pracy z natywnym systemem punktów lojalnościowych PrestaShop. Jeśli używasz modułu lojalnościowego innej firmy, może on nie integrować się bezpośrednio, chyba że ten moduł specjalnie rozszerza lub używa podstawowych funkcji lojalnościowych PrestaShop w kompatybilny sposób.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem „Przypomnienie o punktach lojalnościowych”.

### 4.1 Przegląd architektury

Moduł „Przypomnienie o punktach lojalnościowych” (`lpreminder`) to standardowy moduł PrestaShop, zgodny z wzorcem MVC. Jego podstawowa funkcjonalność opiera się na zaplanowanym zadaniu (cron job), które uruchamia kontroler frontowy w celu przetworzenia wygasających punktów lojalnościowych i wysłania e-maili. Wykorzystuje natywne klasy PrestaShop `LoyaltyModule` i `Mail`.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery są zaprojektowane do dostępu za pośrednictwem określonego URL, głównie do wykonywania zadań cron.

-   **`controllers/front/cronjob.php`**
    -   **Nazwa klasy i klasa nadrzędna:** `LpreminderCronjobModuleFrontController` rozszerzająca `ModuleFrontController`.
    -   **Odpowiedzialność:** Jest to krytyczny punkt końcowy dla zadania cron. Po uzyskaniu dostępu wykonuje logikę modułu w celu zidentyfikowania klientów z wygasającymi punktami lojalnościowymi i wysyła e-maile z przypomnieniami. Powinien być idealnie chroniony (np. za pomocą tokena lub ograniczenia IP), jeśli nie zostało to już zaimplementowane przez moduł, aby zapobiec nieautoryzowanemu dostępowi. Nie renderuje żadnego wizualnego wyjścia, ale wykonuje przetwarzanie w tle.
-   **`controllers/front/index.php`**
    -   **Nazwa klasy i klasa nadrzędna:** `LpreminderIndexModuleFrontController` rozszerzająca `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler może służyć jako domyślny punkt wejścia lub symbol zastępczy. W wielu modułach, jeśli konkretna akcja nie jest zdefiniowana, `index.php` może ją obsłużyć. Biorąc pod uwagę podstawową funkcję modułu, `cronjob.php` jest głównym operacyjnym kontrolerem frontowym. Ten `index.php` może być awaryjny lub używany do przyszłych rozszerzeń.

#### Kontrolery administracyjne Back-Office

Moduł nie wykorzystuje żadnych niestandardowych kontrolerów administracyjnych. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Moduł nie definiuje żadnych niestandardowych klas ani `ObjectModel` w katalogu `classes/`. Bezpośrednio współdziała z podstawowymi klasami PrestaShop, w szczególności:

-   `LoyaltyModule`: Do pobierania punktów lojalnościowych klienta i ich dat wygaśnięcia.
-   `Customer`: Do pobierania danych klienta do wysyłania e-maili.
-   `Mail`: Do wysyłania e-maili z przypomnieniami.
-   `Configuration`: Do przechowywania i pobierania ustawień modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł nie zawiera żadnych niestandardowych plików JavaScript. Cała funkcjonalność jest obsługiwana po stronie serwera.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł nie zawiera żadnych niestandardowych plików CSS. Strona konfiguracji używa domyślnego stylu Panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł nie zawiera żadnych niestandardowych plików szablonów Smarty w katalogu `views/templates/`.

-   **Szablony e-mail:** Moduł opiera się na domyślnym systemie szablonów e-mail PrestaShop. Treść e-maila z przypomnieniem jest generowana przy użyciu szablonu o nazwie `loyalty_points_reminder`. Programiści mogą dostosować ten e-mail, tworząc lub nadpisując następujące pliki w katalogu `mails/` swojego aktywnego motywu:
    -   `themes/yourtheme/mails/en/loyalty_points_reminder.html` (dla treści e-maila HTML)
    -   `themes/yourtheme/mails/en/loyalty_points_reminder.txt` (dla treści e-maila w postaci zwykłego tekstu)
    -   Zastąp `en` odpowiednim kodem języka.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoje ustawienia konfiguracyjne (np. `PS_LPREMINDER_DAYS_BEFORE_EXPIRY`, `PS_LPREMINDER_ENABLED`) w tabeli `ps_configuration`. Odpytuje istniejące tabele PrestaShop, takie jak `ps_loyalty_history` i `ps_customer`.
-   **Tabela zarejestrowanych hooków**:
    Moduł używa głównie hooka `actionFrontControllerSetMedia` do potencjalnego przyszłego włączenia JS/CSS (chociaż obecnie żadne nie są obecne) i niejawnie opiera się na mechanizmie zadań cron dla swojej podstawowej funkcjonalności, który nie jest tradycyjnym hookiem PrestaShop, ale zewnętrznym wyzwalaczem dla kontrolera frontowego.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` stron front-office. | Nie jest bezpośrednio używany do podstawowej logiki modułu, ale może być używany do JS/CSS, jeśli jest to potrzebne. |
| `displayRightColumn` | Renderuje zawartość w prawej kolumnie stron front-office. | Nie jest bezpośrednio używany do podstawowej logiki modułu. |
| `displayLeftColumn` | Renderuje zawartość w lewej kolumnie stron front-office. | Nie jest bezpośrednio używany do podstawowej logiki modułu. |
| `displayFooter` | Renderuje zawartość w stopce stron front-office. | Nie jest bezpośrednio używany do podstawowej logiki modułu. |
| `displayProductExtraContent` | Renderuje zawartość na stronie produktu. | Nie jest bezpośrednio używany do podstawowej logiki modułu. |
| `actionFrontControllerSetMedia` | Wykonywany, gdy kontroler frontowy ustawia swoje media (JS/CSS). | Pozwala modułowi rejestrować własne zasoby JS/CSS, jeśli jest to potrzebne. |
| *(Wyzwalacz zadania Cron)* | Zewnętrzne, zaplanowane zadanie po stronie serwera (np. codziennie). | Wyzwala kontroler frontowy `cronjob.php` w celu przetworzenia wygasających punktów lojalnościowych i wysłania e-maili. Jest to główny wyzwalacz operacyjny modułu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Przypomnienie o punktach lojalnościowych”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
