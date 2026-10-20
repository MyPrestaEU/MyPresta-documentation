---
title: "Bank Izraela – kursy wymiany walut – Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Bank Izraela – kursy wymiany walut” od MyPresta.eu."
sidebar:
  label: "Bank Izraela – kursy wymiany walut – Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Bank of Israel - currency exchange rates na MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-israel-currency-exchange-rates.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/bank-of-israel-currency-exchange-rates/)
>
> ---


# Bank Izraela – kursy wymiany walut

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do pobierania danych zewnętrznych. Twoje środowisko hostingowe musi również obsługiwać zadania CRON dla automatycznych aktualizacji.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj”, aby uzyskać dostęp do ustawień modułu. Jest to główny ekran, na którym skonfigurujesz sposób pobierania i stosowania kursów wymiany przez moduł.

#### **Aktualizacje MyPresta.eu**

- **Co robi to ustawienie:** Ta sekcja zawiera informacje o aktualizacjach z MyPresta.eu, w tym bieżącą wersję modułu i dostępne aktualizacje. Pomaga utrzymać moduł w aktualnym stanie.
- **Efekt zmiany tego ustawienia:**
  - *Gdy dostępna jest aktualizacja:* Zobaczysz powiadomienie i link do pobrania najnowszej wersji ze swojego konta MyPresta.eu.
  - *Gdy nie ma dostępnych aktualizacji:* Sekcja po prostu pokaże Twoją bieżącą wersję.
- **Zalecana wartość:** Zawsze aktualizuj swoje moduły, aby korzystać z nowych funkcji, poprawek błędów i ulepszeń bezpieczeństwa.
- **Scenariusz / przykład dla sprzedawcy:** Regularnie sprawdzaj tę sekcję, aby upewnić się, że Twój moduł jest aktualny, zwłaszcza po dużych aktualizacjach wersji PrestaShop.

#### **Interwał aktualizacji**

- **Co robi to ustawienie:** Określa, jak często moduł próbuje pobierać i aktualizować kursy wymiany z Banku Izraela.
- **Efekt zmiany tego ustawienia:**
  - *Ustawienie krótszego interwału (np. 1 godzina):* Kursy wymiany będą aktualizowane częściej, zapewniając, że Twoje ceny są zawsze bardzo zbliżone do rzeczywistych. Jest to dobre dla walut o dużej zmienności lub dużej sprzedaży międzynarodowej.
  - *Ustawienie dłuższego interwału (np. 24 godziny):* Kursy wymiany będą aktualizowane rzadziej. Może to być odpowiednie, jeśli wahania walutowe nie są głównym problemem dla Twojej firmy lub jeśli wolisz rzadsze połączenia zewnętrzne.
- **Zalecana wartość:** „24 godziny” dla większości sklepów. Jeśli masz duży wolumen sprzedaży z klientami międzynarodowymi i często zmieniające się kursy walut, rozważ „12 godzin” lub „6 godzin”.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz drogie artykuły elektroniczne klientom międzynarodowym, możesz wybrać „6 godzin”, aby upewnić się, że Twoje ceny odzwierciedlają najnowsze warunki rynkowe. Dla lokalnego butiku z okazjonalną sprzedażą międzynarodową, „24 godziny” jest wystarczające.

#### **Marża aktualizacji (%)**

- **Co robi to ustawienie:** Umożliwia dodanie procentowej marży do kursów wymiany pobranych z Banku Izraela. Ta marża jest stosowana ponad oficjalny kurs.
- **Efekt zmiany tego ustawienia:**
  - *Ustawienie dodatniej marży (np. 2%):* Twoje przeliczone ceny w innych walutach będą nieco wyższe niż bezpośredni oficjalny kurs wymiany, pomagając pokryć potencjalne opłaty transakcyjne, koszty przeliczenia walut lub po prostu zwiększyć marżę zysku.
  - *Ustawienie zerowej marży (0%):* Twoje ceny będą odzwierciedlać dokładny oficjalny kurs wymiany bez dodatkowej narzutu.
- **Zalecana wartość:** „0”, jeśli chcesz dokładnych oficjalnych kursów. Mała dodatnia wartość (np. „1” lub „2”) jest często zalecana, aby pokryć potencjalne opłaty bankowe lub zapewnić bufor przed drobnymi wahaniami.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja bramka płatności pobiera 1,5% opłaty za transakcje międzynarodowe, ustawienie marży „1,5” lub „2” procent może pomóc Ci wchłonąć ten koszt bez wpływu na cenę bazową produktu w Twojej domyślnej walucie.

#### **Waluty do aktualizacji**

- **Co robi to ustawienie:** Jest to lista wszystkich walut aktualnie aktywnych w Twoim sklepie PrestaShop. Możesz wybrać, które z tych walut mają mieć automatycznie aktualizowane kursy wymiany przez ten moduł.
- **Efekt zmiany tego ustawienia:**
  - *Wybranie waluty (zaznaczone pole wyboru):* Moduł pobierze kurs wymiany dla tej waluty (w stosunku do ILS) z Banku Izraela i zaktualizuje go w Twoim sklepie.
  - *Odznaczenie waluty (niezaznaczone pole wyboru):* Moduł zignoruje tę walutę, a jej kurs wymiany *nie* zostanie automatycznie zaktualizowany. W razie potrzeby musiałbyś zaktualizować go ręcznie.
- **Zalecana wartość:** Wybierz wszystkie waluty, których aktywnie używasz do sprzedaży międzynarodowej i które chcesz aktualizować. Upewnij się, że Twoja domyślna waluta (np. ILS) jest poprawnie skonfigurowana w PrestaShop.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz klientom w USA, Europie i Wielkiej Brytanii, zaznaczyłbyś pola dla USD, EUR i GBP. Jeśli sprzedajesz tylko lokalnie w ILS i sporadycznie do USA, możesz zaznaczyć tylko USD.

#### **Adres URL zadania CRON**

- **Co robi to ustawienie:** Wyświetla unikalny adres URL, który należy skonfigurować jako zadanie CRON na Twoim serwerze WWW. Zadanie CRON to zaplanowane zadanie, które nakazuje Twojemu serwerowi odwiedzać ten adres URL w regularnych odstępach czasu, co powoduje, że moduł automatycznie pobiera i aktualizuje kursy wymiany.
- **Efekt zmiany tego ustawienia:** To nie jest ustawienie, które zmieniasz, ale raczej adres URL, którego *używasz*.
  - *Gdy zadanie CRON jest poprawnie skonfigurowane:* Moduł będzie działał automatycznie w określonym przez Ciebie „Interwale aktualizacji”, utrzymując aktualne kursy wymiany bez żadnej ręcznej interwencji.
  - *Gdy zadanie CRON NIE jest skonfigurowane:* Kursy wymiany *nie* będą aktualizowane automatycznie. Musiałbyś ręcznie odwiedzić ten adres URL w swojej przeglądarce (co nie jest zalecane do regularnego użytku) lub ręcznie zaktualizować kursy w PrestaShop.
- **Zalecana wartość:** Skopiuj ten adres URL i skonfiguruj go jako zadanie CRON w swoim panelu hostingowym (np. cPanel, Plesk lub przez SSH). Częstotliwość zadania CRON powinna odpowiadać lub być nieco częstsza niż ustawiony „Interwał aktualizacji”. Na przykład, jeśli Twój interwał aktualizacji wynosi 24 godziny, ustaw zadanie CRON tak, aby uruchamiało się raz na 24 godziny.
- **Scenariusz / przykład dla sprzedawcy:** Po skonfigurowaniu wszystkich innych ustawień skopiuj ten adres URL i wklej go do harmonogramu zadań CRON swojego dostawcy hostingu. Ustaw go tak, aby uruchamiał się codziennie w czasie niskiego ruchu (np. o 3 nad ranem).

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Aktualizacje MyPresta.eu | N/A | Wyświetla wersję modułu i dostępność aktualizacji. |
| Konfiguracja modułu | Interwał aktualizacji | 24 godziny | Jak często pobierane są kursy wymiany (np. 6, 12, 24 godziny). |
| Konfiguracja modułu | Marża aktualizacji (%) | 0-2% | Dodaje procentową narzutę do pobranych kursów wymiany. |
| Konfiguracja modułu | Waluty do aktualizacji | Wszystkie aktywne waluty | Wybiera, które waluty mają być automatycznie aktualizowane. |
| Konfiguracja modułu | Adres URL zadania CRON | N/A | Adres URL do skonfigurowania na serwerze dla automatycznych aktualizacji. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje kursy wymiany nie aktualizują się automatycznie. Co powinienem zrobić?**
O:

1.  **Sprawdź zadanie CRON:** Najczęstszą przyczyną jest nieprawidłowo skonfigurowane lub brakujące zadanie CRON. Dokładnie sprawdź adres URL zadania CRON podany w konfiguracji modułu i upewnij się, że jest on poprawnie skonfigurowany na Twoim serwerze hostingowym, aby uruchamiał się z żądaną częstotliwością.
2.  **Ustawienia modułu:** Sprawdź, czy „Interwał aktualizacji” jest ustawiony i czy żądane „Waluty do aktualizacji” są zaznaczone w konfiguracji modułu.
3.  **Dostęp do serwera:** Upewnij się, że Twój serwer może wykonywać zewnętrzne żądania do API Banku Izraela. Czasami zapory sieciowe lub ustawienia bezpieczeństwa mogą to blokować. Skontaktuj się z dostawcą hostingu, jeśli podejrzewasz taką sytuację.
4.  **Pamięć podręczna PrestaShop:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) po wprowadzeniu jakichkolwiek zmian w ustawieniach modułu.

**P: Czy mogę ręcznie nadpisać kurs wymiany po jego zaktualizowaniu przez moduł?**
O: Tak, możesz. Po uruchomieniu modułu kursy są przechowywane w standardowych ustawieniach walut PrestaShop (Lokalizacja > Waluty). Możesz tam ręcznie edytować kurs wymiany dla konkretnej waluty. Pamiętaj jednak, że następnym razem, gdy uruchomi się zadanie CRON, nadpisze ono Twoją ręczną zmianę najnowszym kursem z Banku Izraela (plus Twoja marża).

**P: Co się stanie, jeśli API Banku Izraela będzie tymczasowo niedostępne?**
O: Jeśli moduł nie może pobrać danych, zazwyczaj zachowa ostatnie pomyślnie zaktualizowane kursy wymiany. Nie usunie ani nie zresetuje Twoich kursów do zera. Po prostu spróbuje ponownie podczas następnego zaplanowanego uruchomienia zadania CRON.

**P: Moje ceny wyglądają nieco inaczej po aktualizacji. Dlaczego?**
O:

1.  **Marża aktualizacji:** Sprawdź ustawienie „Marża aktualizacji (%)” w konfiguracji modułu. Jeśli masz ustawioną dodatnią marżę, Twoje ceny będą nieco wyższe niż bezpośredni oficjalny kurs.
2.  **Zaokrąglanie:** Ustawienia walut PrestaShop mają również opcję „Miejsca dziesiętne”. Upewnij się, że jest ona odpowiednio ustawiona dla Twoich walut, aby uniknąć nieoczekiwanych problemów z zaokrąglaniem.
3.  **Waluta bazowa:** Upewnij się, że Twoja domyślna waluta w PrestaShop (Lokalizacja > Waluty) jest poprawnie ustawiona jako szekel izraelski (ILS), jeśli jest to Twoja waluta bazowa dla tych aktualizacji.

**P: Jak skonfigurować zadanie CRON?**
O: Ten proces różni się w zależności od dostawcy hostingu. Zazwyczaj logujesz się do swojego panelu sterowania hostingiem (np. cPanel, Plesk). Poszukaj sekcji o nazwie „Cron Jobs”, „Zaplanowane zadania” lub „Zadania automatyczne”. Będziesz musiał dodać nowe zadanie CRON, określić częstotliwość (np. raz dziennie) i wkleić „Adres URL zadania CRON” dostarczony przez moduł. Jeśli nie jesteś pewien, skontaktuj się z pomocą techniczną swojego dostawcy hostingu, podając im adres URL i żądaną częstotliwość.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Bank Izraela – kursy wymiany walut” (`boirates`) jest zgodny ze standardową architekturą modułów PrestaShop. Wykorzystuje główną klasę modułu (`boirates.php`) do obsługi instalacji, deinstalacji i konfiguracji. Aktualizacje kursów wymiany są głównie wywoływane za pośrednictwem kontrolera frontowego (`cronjob.php`) zaprojektowanego do wywoływania przez zadanie CRON po stronie serwera. Moduł pobiera dane XML z oficjalnego API Banku Izraela, analizuje je i aktualizuje tabelę `ps_currency` w PrestaShop.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front Office**:

  - `controllers/front/cronjob.php`
    - **Nazwa klasy**: `BoiratesCronjobModuleFrontController` (rozszerza `ModuleFrontController`)
    - **Odpowiedzialność**: Ten kontroler jest przeznaczony do wywoływania przez zewnętrzne zadanie CRON. Zawiera podstawową logikę pobierania kursów wymiany z API Banku Izraela, analizowania odpowiedzi XML, stosowania skonfigurowanej marży i aktualizowania tabeli `ps_currency` w PrestaShop. Nie renderuje żadnej zawartości front office, ale wykonuje przetwarzanie danych w tle. Jest kluczowy dla zautomatyzowanej funkcjonalności modułu.
  - `controllers/front/index.php`
    - **Nazwa klasy**: `BoiratesIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    - **Odpowiedzialność**: Jest to kontroler zastępczy lub domyślny kontroler frontowy. W wielu modułach, jeśli konkretna akcja nie jest routowana, może zostać wywołany `index.php`. Dla tego modułu jego główną funkcją jest prawdopodobnie zapobieganie listowaniu katalogów lub dostarczanie minimalnej domyślnej odpowiedzi, jeśli jest dostępny bezpośrednio bez określonych parametrów. Podstawowa logika znajduje się w `cronjob.php`.
- **Kontrolery administracyjne Back Office**:

  - Brak. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

- Brak. Logika modułu jest głównie hermetyzowana w głównym pliku `boirates.php` i `BoiratesCronjobModuleFrontController`. Interakcja z danymi odbywa się bezpośrednio z klasą `Currency` PrestaShop i tabelą `ps_configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

- Brak. Moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

- Brak. Moduł nie zawiera żadnych niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony administracyjne (`views/templates/admin/`)**:
  - `views/templates/admin/admin.tpl`
    - **Cel**: Ten szablon jest renderowany przez metodę `getContent()` pliku modułu `boirates.php`. Definiuje strukturę i układ strony konfiguracji modułu w Panelu administracyjnym PrestaShop. Zawiera elementy formularza dla ustawień `mypresta_updates`, `update_`, `updatev_` i `currency_`, a także wyświetla adres URL zadania CRON.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Współpracuje ze standardową tabelą `ps_configuration` PrestaShop do przechowywania swoich ustawień (np. `BOIRATES_UPDATE_INTERVAL`, `BOIRATES_UPDATE_MARGIN`, `BOIRATES_CURRENCIES_TO_UPDATE`).
  - Aktualizuje kolumnę `exchange_rate` w tabeli `ps_currency` dla wybranych walut.
- **Tabela zarejestrowanych hooków**:
  Moduł nie rejestruje jawnie żadnych hooków wyświetlania front office (takich jak `displayHeader`, `displayRightColumn`, `displayProductButtons`, `displayFooter`) w swojej metodzie `install()` do renderowania zawartości. Jego główną funkcją jest przetwarzanie danych w tle.
  Prawdopodobnie używa wewnętrznych hooków PrestaShop do swojej podstawowej funkcjonalności, takich jak:

  | Nazwa hooka | Czas wykonania | Cel techniczny |
  | --- | --- | --- |
  | `actionModuleInstall` | Podczas instalacji modułu | Ustawia domyślne wartości konfiguracyjne i rejestruje niezbędne elementy. |
  | `actionModuleUninstall` | Podczas deinstalacji modułu | Czyści wartości konfiguracyjne. |
  | `displayBackOfficeHeader` | Renderuje zawartość w nagłówku Panelu administracyjnego | Potencjalnie używany do dodawania CSS/JS lub powiadomień, choć nie został wyraźnie wykryty w inwentarzu. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnego wsparcia, aktualizacji i pobrania najnowszych wersji modułu „Bank Izraela – kursy wymiany walut” odwiedź swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
