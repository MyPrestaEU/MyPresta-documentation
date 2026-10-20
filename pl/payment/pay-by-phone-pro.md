---
title: "Pay By Phone Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu Pay By Phone Pro dla PrestaShop od MyPresta.eu."
sidebar:
  label: "Pay By Phone Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Pay By Phone Pro na MyPresta.eu](https://mypresta.eu/modules/payment-process/pay-by-phone-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/payment/pay-by-phone-pro/)
>
> ---


# Pay By Phone Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop, a ten moduł nie ma żadnych dodatkowych specyficznych wymagań poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Pay By Phone Pro)

Jest to główny ekran konfiguracji, na którym definiujesz, jak metoda płatności „Pay By Phone Pro” pojawia się i działa w Twoim sklepie.

- **Lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > Wyszukaj „Pay By Phone Pro” > Kliknij „Konfiguruj”.

#### Ustawienia i opcje

1. **Tytuł metody płatności**

   - **Co robi to ustawienie:** Jest to nazwa metody płatności, którą Twoi klienci zobaczą podczas realizacji zamówienia. To, co pojawia się na liście opcji płatności.
   - **Efekt zmiany tego ustawienia:**
     - *Gdy ustawione na „Zapłać telefonicznie”:* Klienci zobaczą „Zapłać telefonicznie” jako opcję.
     - *Gdy ustawione na „Zadzwoń do nas, aby zapłacić”:* Klienci zobaczą „Zadzwoń do nas, aby zapłacić” jako opcję.
   - **Zalecana wartość:** Coś jasnego i profesjonalnego, np. „Zapłać telefonicznie” lub „Zadzwoń, aby sfinalizować zamówienie”.
   - **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz podkreślić bezpośredni kontakt, możesz użyć „Zadzwoń do naszego zespołu sprzedaży, aby zapłacić”. Jeśli chcesz, aby brzmiało to bardziej jak standardowa opcja płatności, „Zapłać telefonicznie” jest lepsze.
2. **Opis metody płatności**

   - **Co robi to ustawienie:** Jest to krótki opis, który pojawia się pod tytułem metody płatności podczas realizacji zamówienia. Wyjaśnia klientowi, na czym polega ta metoda płatności.
   - **Efekt zmiany tego ustawienia:**
     - *Gdy ustawione na „Zadzwoń do nas, aby podać dane karty kredytowej i sfinalizować zamówienie.”:* Ten tekst się pojawi, prowadząc klienta przez kolejne kroki.
     - *Gdy ustawione na „Skontaktuj się z naszym działem obsługi klienta, aby omówić opcje płatności.”:* Ten alternatywny tekst zostanie wyświetlony.
   - **Zalecana wartość:** Jasno określ, co klient musi zrobić, np. „Prosimy zadzwonić pod numer [Twój numer telefonu], aby sfinalizować płatność i szczegóły zamówienia.”
   - **Scenariusz/przykład dla sprzedawcy:** Możesz napisać: „Po złożeniu zamówienia, prosimy zadzwonić pod numer +1-800-123-4567 w godzinach pracy, aby sfinalizować płatność. Przygotuj numer zamówienia.”
3. **Instrukcje dla klienta na stronie potwierdzenia zamówienia**

   - **Co robi to ustawienie:** Jest to bardziej szczegółowa wiadomość wyświetlana klientowi na stronie potwierdzenia zamówienia *po* wybraniu „Pay By Phone Pro” i złożeniu zamówienia. Tutaj podajesz konkretne instrukcje.
   - **Efekt zmiany tego ustawienia:**
     - *Gdy ustawione na „Dziękujemy za zamówienie. Prosimy zadzwonić do nas, aby sfinalizować płatność.”:* Ta wiadomość zostanie wyświetlona.
     - *Gdy ustawione na „Twoje zamówienie jest w toku. Prosimy o kontakt z naszym zespołem wsparcia z numerem zamówienia, aby ustalić płatność.”:* Ta alternatywna wiadomość zostanie wyświetlona.
   - **Zalecana wartość:** Podaj swój numer telefonu, godziny pracy i informacje, które klient powinien mieć przygotowane (np. numer zamówienia).
   - **Scenariusz/przykład dla sprzedawcy:** „Twoje zamówienie #12345 zostało złożone. Prosimy zadzwonić do naszego zespołu sprzedaży pod numer +1-800-123-4567 (pon-pt, 9:00 - 17:00 EST) w ciągu 24 godzin, aby podać dane płatności. Prosimy mieć przygotowany numer zamówienia.”
4. **Status zamówienia dla płatności oczekujących**

   - **Co robi to ustawienie:** Określa początkowy status zamówienia złożonego za pomocą „Pay By Phone Pro” w Twoim Panelu administracyjnym PrestaShop. Ten status wskazuje, że płatność nie jest jeszcze zakończona i wymaga Twojej interwencji.
   - **Efekt zmiany tego ustawienia:**
     - *Gdy ustawione na „Oczekiwanie na przelew bankowy”:* Zamówienia będą wyświetlane z tym statussem.
     - *Gdy ustawione na „Płatność zaakceptowana”:* (Nie zalecane dla tego modułu) Spowodowałoby to błędne oznaczenie zamówienia jako opłaconego, zanim je przetworzysz.
   - **Zalecana wartość:** Wybierz status, który jasno wskazuje „płatność oczekująca” lub „oczekiwanie na płatność”. Typowe wybory to „Oczekiwanie na przelew bankowy”, „Płatność oczekująca” lub „Oczekiwanie na płatność czekiem”. Jeśli masz niestandardowy status zamówienia, taki jak „Oczekiwanie na płatność telefoniczną”, byłoby to idealne.
   - **Scenariusz/przykład dla sprzedawcy:** Wybranie „Oczekiwanie na przelew bankowy” zapewnia, że te zamówienia są łatwo identyfikowalne na liście zamówień jako wymagające ręcznego przetwarzania płatności.
5. **Włącz dla określonych krajów**

   - **Co robi to ustawienie:** Umożliwia ograniczenie tej metody płatności tylko do klientów z określonych krajów. Jeśli pozostawione puste, będzie dostępne dla wszystkich krajów.
   - **Efekt zmiany tego ustawienia:**
     - *Gdy wybrane są konkretne kraje (np. „Stany Zjednoczone”, „Kanada”):* Tylko klienci z adresem rozliczeniowym w tych krajach zobaczą „Pay By Phone Pro” jako opcję.
     - *Gdy nie wybrano żadnych krajów:* Metoda płatności jest dostępna globalnie.
   - **Zalecana wartość:** Pozostaw puste, jeśli chcesz oferować ją na całym świecie, lub wybierz konkretne kraje, jeśli masz ograniczenia operacyjne (np. wsparcie telefoniczne tylko w niektórych regionach).
   - **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoje wsparcie telefoniczne jest dostępne tylko w języku angielskim i wysyłasz tylko do USA i Kanady, wybierzesz „Stany Zjednoczone” i „Kanada”, aby uniknąć oferowania jej klientom, których nie możesz obsłużyć.
6. **Włącz dla określonych walut**

   - **Co robi to ustawienie:** Umożliwia ograniczenie tej metody płatności do klientów płacących w określonych walutach. Jeśli pozostawione puste, będzie dostępne dla wszystkich walut.
   - **Efekt zmiany tego ustawienia:**
     - *Gdy wybrane są konkretne waluty (np. „USD”, „EUR”):* Tylko klienci płacący w tych walutach zobaczą „Pay By Phone Pro”.
     - *Gdy nie wybrano żadnych walut:* Metoda płatności jest dostępna dla wszystkich walut skonfigurowanych w Twoim sklepie.
   - **Zalecana wartość:** Pozostaw puste, jeśli obsługujesz wszystkie waluty, lub wybierz konkretne, jeśli Twój system ręcznego przetwarzania płatności ma ograniczenia walutowe.
   - **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój terminal kart kredytowych przetwarza tylko USD i EUR, wybierzesz te dwie waluty.
7. **Włącz dla określonych grup klientów**

   - **Co robi to ustawienie:** Umożliwia ograniczenie tej metody płatności do określonych grup klientów (np. „Goście”, „Klienci”, „Hurtownicy”). Jeśli pozostawione puste, będzie dostępne dla wszystkich grup klientów.
   - **Efekt zmiany tego ustawienia:**
     - *Gdy wybrane są konkretne grupy (np. „Hurtownicy”):* Tylko klienci należący do grupy „Hurtownicy” zobaczą tę opcję płatności.
     - *Gdy nie wybrano żadnych grup:* Metoda płatności jest dostępna dla wszystkich grup klientów.
   - **Zalecana wartość:** Pozostaw puste do ogólnego użytku lub wybierz konkretne grupy, jeśli ta metoda płatności jest częścią specjalnego porozumienia (np. dla VIP-ów lub klientów B2B).
   - **Scenariusz/przykład dla sprzedawcy:** Możesz oferować to tylko swojej grupie klientów „Hurtowych”, ponieważ często mają oni niestandardowe warunki płatności, które wymagają bezpośredniej dyskusji.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Tytuł metody płatności | „Zapłać telefonicznie” | Nazwa wyświetlana klientom podczas realizacji zamówienia. |
| Konfiguracja modułu | Opis metody płatności | „Zadzwoń do nas, aby podać dane karty kredytowej i sfinalizować zamówienie.” | Krótkie wyjaśnienie pod tytułem płatności. |
| Konfiguracja modułu | Instrukcje dla klienta na stronie potwierdzenia zamówienia | „Dziękujemy za zamówienie. Prosimy zadzwonić do nas, aby sfinalizować płatność.” | Szczegółowe instrukcje na stronie potwierdzenia zamówienia. |
| Konfiguracja modułu | Status zamówienia dla płatności oczekujących | „Oczekiwanie na przelew bankowy” (lub podobny status oczekujący) | Początkowy status zamówień złożonych tą metodą. |
| Konfiguracja modułu | Włącz dla określonych krajów | Puste (Wszystkie kraje) | Ogranicz metodę płatności według kraju klienta. |
| Konfiguracja modułu | Włącz dla określonych walut | Puste (Wszystkie waluty) | Ogranicz metodę płatności według wybranej waluty. |
| Konfiguracja modułu | Włącz dla określonych grup klientów | Puste (Wszystkie grupy) | Ogranicz metodę płatności według grupy klientów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Opcja „Pay By Phone Pro” nie pojawia się podczas realizacji zamówienia.**
O:

- **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Pay By Phone Pro” jest zainstalowany i włączony.
- **Ustawienia konfiguracji:** Przejrzyj ustawienia „Włącz dla określonych krajów”, „Włącz dla określonych walut” i „Włącz dla określonych grup klientów”. Jeśli moduł został ograniczony, upewnij się, że obecny klient/koszyk testowy spełnia te kryteria.
- **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop w **Zaawansowane > Wydajność**. Czasami stara pamięć podręczna uniemożliwia pojawienie się nowych modułów lub ustawień.
- **Kompatybilność z motywem:** Chociaż rzadko, wysoce dostosowany motyw może kolidować. Tymczasowo przełącz się na domyślny motyw PrestaShop (np. Classic), aby wykluczyć konflikty motywu.

**P2: Jak zmienić tekst, który widzą klienci dla tej metody płatności?**
O: Cały tekst widoczny dla klienta (tytuł, opis i instrukcje potwierdzenia) można dostosować bezpośrednio ze strony konfiguracji modułu w Panelu administracyjnym. Przejdź do **Moduły > Menedżer modułów**, znajdź „Pay By Phone Pro” i kliknij „Konfiguruj”. Znajdziesz tam pola takie jak „Tytuł metody płatności”, „Opis metody płatności” i „Instrukcje dla klienta na stronie potwierdzenia zamówienia”. Pamiętaj, aby zapisać zmiany.

**P3: Co się stanie, jeśli klient złoży zamówienie za pomocą „Pay By Phone Pro”, ale nigdy nie zadzwoni?**
O: Zamówienie pozostanie w skonfigurowanym statusie „oczekujące na płatność” (np. „Oczekiwanie na przelew bankowy”). Będziesz musiał monitorować te zamówienia w swoim Panelu administracyjnym. Możesz ustawić automatyczne przypomnienia lub ręcznie skontaktować się z klientem po pewnym czasie (np. 24-48 godzin), aby uzyskać dalsze informacje. Jeśli nie nawiązano kontaktu, ostatecznie możesz anulować zamówienie.

**P4: Czy mogę przetłumaczyć tekst modułu na inne języki?**
O: Tak, system tłumaczeń PrestaShop obsługuje teksty modułów. Przejdź do **Lokalizacja > Tłumaczenia**, wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz „Pay By Phone Pro”. Następnie możesz przetłumaczyć wszystkie konfigurowalne pola tekstowe na aktywne języki Twojego sklepu.

**P5: Jak przetworzyć płatność, gdy klient zadzwoni?**
O: Ten moduł sam nie przetwarza płatności. Ułatwia składanie zamówień. Gdy klient zadzwoni, użyjesz swoich istniejących metod przetwarzania płatności offline (np. fizycznego terminala kart kredytowych, wirtualnego terminala dostarczonego przez Twój bank lub rejestrowania przelewu bankowego), aby pobrać dane płatności i zakończyć transakcję. Po pomyślnej płatności musisz ręcznie zaktualizować status zamówienia w swoim Panelu administracyjnym PrestaShop z „oczekujące na płatność” na „Płatność zaakceptowana” (lub „W trakcie realizacji”), aby odzwierciedlić zmianę.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Pay By Phone Pro” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł „Pay By Phone Pro” jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie `PaymentModule` do swojej podstawowej funkcjonalności. Integruje się z procesem realizacji zamówienia poprzez rejestrowanie hooków i dostarczanie kontrolerów front-endowych do realizacji i walidacji płatności. Konfiguracja jest obsługiwana za pomocą metody `getContent()` głównej klasy modułu.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery obsługują aspekty procesu płatności widoczne dla klienta.

- **`controllers/front/index.php`**

  - **Nazwa klasy i klasa nadrzędna:** `PayByPhoneIndexModuleFrontController` rozszerzający `ModuleFrontController`.
  - **Odpowiedzialność:** Ten kontroler jest zazwyczaj odpowiedzialny za wyświetlanie początkowego formularza płatności lub przekierowanie do strony realizacji płatności. W kontekście tego modułu prawdopodobnie działa jako brama przed faktyczną realizacją płatności, potencjalnie ustawiając dane sesji lub przekierowując do `payment_execution.tpl`.
- **`controllers/front/validation.php`**

  - **Nazwa klasy i klasa nadrzędna:** `PayByPhoneValidationModuleFrontController` rozszerzający `ModuleFrontController`.
  - **Odpowiedzialność:** Jest to krytyczny kontroler, który przetwarza zamówienie po tym, jak klient wybierze „Pay By Phone Pro”. Waliduje zamówienie, tworzy je w bazie danych PrestaShop ze skonfigurowanym statusem oczekującym, a następnie przekierowuje klienta na stronę potwierdzenia zamówienia, wyświetlając konkretne instrukcje. Używa metody `validateOrder` z nadrzędnej klasy `PaymentModule`.

#### Kontrolery administracyjne Back-Office

Ten moduł nie zawiera żadnych niestandardowych kontrolerów administracyjnych Back-Office. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie zawiera żadnych niestandardowych klas ani definicji `ObjectModel` w katalogu `classes/`. Opiera się na podstawowych klasach PrestaShop `PaymentModule` i `Configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Jego funkcjonalność jest głównie po stronie serwera i oparta na szablonach.

### 4.5 Arkusze stylów CSS (`views/css/`)

- **`paybyphone/css/paybyphone.css`**
  - **Zakres:** Stylizacja klienta w front-office.
  - **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Ten arkusz stylów jest prawdopodobnie używany do zapewnienia podstawowej stylizacji wyglądu metody płatności podczas realizacji zamówienia, takiej jak blok opcji płatności, tekst opisu lub wszelkie specyficzne elementy w szablonach `payment.tpl` lub `shopping-cart.tpl`.
  - **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Programiści mogą sprawdzić wygenerowany kod HTML dla metody płatności na stronie realizacji zamówienia, aby zidentyfikować konkretne klasy (np. `.paybyphone-payment-option`, `.paybyphone-description`), które można nadpisać w pliku `custom.css` swojego motywu lub za pomocą opcji dostosowywania motywu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

Te szablony są renderowane, gdy wykonywane są określone hooki PrestaShop.

- **`views/templates/hook/infos.tpl`**

  - **Hook:** Prawdopodobnie `displayPaymentTop` lub podobny, dostarczający dodatkowe informacje o metodzie płatności.
  - **Blok wizualny:** Może być używany do wyświetlania ogólnego bloku informacyjnego o opcji „Pay By Phone”, być może na stronie produktu lub w kolumnie, zanim klient dotrze do realizacji zamówienia.
- **`views/templates/hook/payment.tpl`**

  - **Hook:** `displayPayment` (PrestaShop 1.6) lub `paymentOptions` (PrestaShop 1.7+).
  - **Blok wizualny:** Jest to główny szablon do wyświetlania opcji „Pay By Phone Pro” na stronie wyboru płatności podczas realizacji zamówienia. Będzie zawierał tytuł i opis metody płatności skonfigurowane w Panelu administracyjnym.

#### Szablony administracyjne (`views/templates/admin/`)

Ten moduł nie zawiera żadnych niestandardowych szablonów administracyjnych. Formularz konfiguracji jest prawdopodobnie generowany bezpośrednio w metodzie `getContent()` pliku `index.php` za pomocą `HelperForm` PrestaShop.

#### Szablony front-office (`views/templates/front/`)

Te szablony są renderowane przez kontrolery front-endowe modułu.

- **`views/templates/front/payment_execution.tpl`**

  - **Cel:** Ten szablon jest prawdopodobnie renderowany przez `PayByPhoneIndexModuleFrontController` lub bezpośrednio po wybraniu metody płatności przez klienta. Może służyć jako strona pośrednia lub krok potwierdzenia przed ostateczną walidacją, potencjalnie wyświetlając przycisk „Potwierdź zamówienie”.
- **`views/templates/front/shopping-cart.tpl`**

  - **Cel:** Ten szablon jest prawdopodobnie rezerwowym lub alternatywnym wyświetlaniem opcji płatności w podsumowaniu koszyka, być może dla starszych wersji PrestaShop lub specyficznych integracji motywów. Przedstawiłby opcję „Pay By Phone” przed rozpoczęciem pełnego procesu realizacji zamówienia.
- **`views/templates/front/validation.tpl`**

  - **Cel:** Jest to szablon strony potwierdzenia zamówienia, renderowany po pomyślnej walidacji i utworzeniu zamówienia przez `PayByPhoneValidationModuleFrontController`. Wyświetla tekst „Instrukcje dla klienta na stronie potwierdzenia zamówienia” wraz z podsumowaniem zamówienia.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł „Pay By Phone Pro” nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop, używając kluczy takich jak `PAYBYPHONE_TITLE`, `PAYBYPHONE_DESCRIPTION`, `PAYBYPHONE_INSTRUCTIONS`, `PAYBYPHONE_ORDER_STATUS`, `PAYBYPHONE_COUNTRIES`, `PAYBYPHONE_CURRENCIES` i `PAYBYPHONE_GROUPS`.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayPayment` (PrestaShop 1.6) | Na stronie wyboru płatności podczas realizacji zamówienia. | Wyświetla opcję płatności „Pay By Phone Pro”. |
| `paymentOptions` (PrestaShop 1.7+) | Na stronie wyboru płatności podczas realizacji zamówienia. | Wyświetla opcję płatności „Pay By Phone Pro” (nowoczesny hook). |
| `displayPaymentReturn` | Na stronie potwierdzenia zamówienia po płatności. | Wyświetla konkretne instrukcje dla klienta, aby zadzwonił. |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Potencjalnie używany do ładowania plików CSS (`paybyphone.css`). |
| `displayLeftColumn` / `displayRightColumn` / `displayFooter` | W odpowiednich obszarach kolumny/stopki. | Może być używany do wyświetlania bloków informacyjnych o metodzie płatności (za pośrednictwem `infos.tpl`). |
| `actionValidateOrder` | Po pomyślnej walidacji i utworzeniu zamówienia. | Umożliwia modułowi wykonywanie dodatkowych działań lub logowania po utworzeniu zamówienia (np. ustawianie konkretnych szczegółów zamówienia). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Pay By Phone Pro”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie płynnego działania i ciągłej kompatybilności naszych modułów z najnowszymi wersjami PrestaShop.
