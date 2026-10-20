---
title: "Voucher & Letters Printer - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop Voucher & Letters Printer od MyPresta.eu."
sidebar:
  label: "Voucher & Letters Printer - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Voucher & Letters Printer na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-letters-printer.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/voucher-letters-printer/)
>
> ---


# Voucher & Letters Printer

## 1. Wymagania i Kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Brak specjalnych wymagań hostingowych poza typową konfiguracją PrestaShop.

## 2. Kompletny Przewodnik Konfiguracji (Każde Ustawienie Pogrupowane Według Ekranu)

### 2.1 Strona Konfiguracji Modułu (Panel administracyjny > Moduły > Konfiguruj > Voucher & Letters Printer)

To jest główny ekran konfiguracji, na którym zdefiniujesz parametry dla swoich kuponów i listów.

#### **Ustawienia Ogólne**

- **Co robi to ustawienie:** Te ustawienia kontrolują ogólne zachowanie i wygląd generowanych kuponów i listów.
- **Efekt zmiany tego ustawienia:** Zmiany tutaj będą miały bezpośredni wpływ na zawartość i format drukowanych dokumentów.

#### **Generowanie Kodu Rabatowego**

- **Prefiks Kuponu:**

  - **Co robi to ustawienie:** Ten tekst zostanie dodany na początku każdego wygenerowanego kodu rabatowego. Pomaga zidentyfikować źródło kuponu (np. „WELCOME-”, „LOYALTY-”).
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawione na „SALE-”:* Wszystkie wygenerowane kody będą zaczynać się od „SALE-”, np. „SALE-ABC123XYZ”.
    - *Gdy pozostawione puste:* Kody będą składać się wyłącznie z losowych znaków, np. „ABC123XYZ”.
  - **Zalecana wartość:** Krótki, opisowy prefiks związany z Twoją kampanią.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli wysyłasz nagrodę lojalnościową, użyj „LOYALTY-”. W przypadku wyprzedaży sezonowej, „SUMMER-”.
- **Sufiks Kuponu:**

  - **Co robi to ustawienie:** Podobnie jak prefiks, ten tekst zostanie dodany na końcu każdego wygenerowanego kodu rabatowego.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawione na „-2024”:* Wszystkie wygenerowane kody będą kończyć się na „-2024”, np. „ABC123XYZ-2024”.
    - *Gdy pozostawione puste:* Kody nie będą miały sufiksu.
  - **Zalecana wartość:** Pozostaw puste, chyba że masz konkretną potrzebę śledzenia.
  - **Scenariusz / przykład dla sprzedawcy:** Możesz użyć sufiksu roku, np. „-2024” dla kampanii rocznych.
- **Długość Kodu Rabatowego (bez prefiksu/sufiksu):**

  - **Co robi to ustawienie:** Określa liczbę losowych znaków w samym kodzie rabatowym, między prefiksem a sufiksem. Dłuższy kod jest bezpieczniejszy, ale trudniejszy do wpisania.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawione na 8:* Kody będą miały 8 losowych znaków (np. „ABC123XY”).
    - *Gdy ustawione na 12:* Kody będą miały 12 losowych znaków (np. „ABC123XYZ456”).
  - **Zalecana wartość:** 8-12 znaków dla dobrej równowagi między bezpieczeństwem a użytecznością.
  - **Scenariusz / przykład dla sprzedawcy:** W przypadku ogólnej promocji 8 znaków jest zazwyczaj wystarczające. W przypadku kuponów o wysokiej wartości, ekskluzywnych, możesz wybrać 10-12.

#### **Zawartość Kuponu i Listu**

- **Wartość Kuponu:**

  - **Co robi to ustawienie:** Jest to wartość pieniężna lub procentowy rabat, który zapewni wygenerowany kupon.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawione na „10”:* Kupon udzieli rabatu w wysokości 10 jednostek (np. 10 €, 10 $).
    - *Gdy ustawione na „20%”:* Kupon udzieli 20% rabatu.
  - **Zalecana wartość:** Wartość, która zachęca do zakupów bez znaczącego wpływu na Twoje marże.
  - **Scenariusz / przykład dla sprzedawcy:** Oferuj 15 € zniżki przy minimalnym zamówieniu 100 €, lub 10% zniżki na cały koszyk.
- **Minimalna Kwota Kuponu:**

  - **Co robi to ustawienie:** Minimalna kwota zamówienia (przed wysyłką) wymagana do użycia kuponu przez klienta.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawione na „50”:* Klienci muszą wydać co najmniej 50 €, aby użyć kuponu.
    - *Gdy ustawione na „0” lub pozostawione puste:* Nie jest wymagany minimalny zakup.
  - **Zalecana wartość:** Ustaw minimalną kwotę, aby zapewnić rentowność, zazwyczaj 2-3 razy wartość kuponu.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli kupon jest na 10 €, ustaw minimum 30 €, aby zachęcić do większego zakupu.
- **Data Ważności Kuponu (Dni od Generacji):**

  - **Co robi to ustawienie:** Określa, ile dni po wygenerowaniu kuponu upłynie jego ważność. Tworzy to poczucie pilności.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawione na „30”:* Kupon będzie ważny przez 30 dni od daty jego utworzenia.
    - *Gdy ustawione na „0” lub pozostawione puste:* Kupon nie będzie miał daty ważności (niezalecane dla większości kampanii).
  - **Zalecana wartość:** 30-90 dni, w zależności od pilności, jaką chcesz stworzyć.
  - **Scenariusz / przykład dla sprzedawcy:** W przypadku szybkiej wyprzedaży, 30 dni. W przypadku nagrody lojalnościowej, 90 dni.
- **Tekst Nagłówka Listu:**

  - **Co robi to ustawienie:** Jest to główny tytuł lub powitanie, które pojawi się na górze spersonalizowanego listu.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawione na „Szanowny Kliencie,”:* Będzie to początkowa linia każdego listu.
    - *Gdy ustawione na „Specjalna Oferta Tylko dla Ciebie!”:* Będzie to wyróżniający się nagłówek.
  - **Zalecana wartość:** Ciepłe, osobiste powitanie.
  - **Scenariusz / przykład dla sprzedawcy:** „Witaj [Imię Klienta],” (jeśli planujesz ręcznie wstawiać imiona lub używać narzędzia do korespondencji seryjnej później) lub „Dziękujemy za bycie Lojalnym Klientem!”
- **Tekst Treści Listu:**

  - **Co robi to ustawienie:** Jest to główna treść listu, w której wyjaśniasz ofertę, dziękujesz klientowi i podajesz wszelkie inne istotne informacje. Możesz używać symboli zastępczych dla dynamicznej zawartości (chociaż sam moduł nie oferuje bezpośrednich symboli zastępczych, zazwyczaj używałbyś narzędzia do korespondencji seryjnej po wyeksportowaniu).
  - **Efekt zmiany tego ustawienia:** Ten tekst będzie stanowił główną wiadomość Twojego fizycznego listu.
  - **Zalecana wartość:** Jasny, zwięzły i przekonujący tekst, który wyjaśnia korzyści z kuponu i zachęca do jego wykorzystania.
  - **Scenariusz / przykład dla sprzedawcy:** „W dowód naszego uznania, skorzystaj z [Wartość Kuponu] zniżki na następny zakup o wartości [Minimalna Kwota]. Użyj kodu: [Kod Kuponu]. Ważne do [Data Ważności].”
- **Tekst Stopki Listu:**

  - **Co robi to ustawienie:** Ten tekst pojawia się na dole listu, zazwyczaj zawiera informacje kontaktowe Twojego sklepu, stronę internetową lub końcową uwagę.
  - **Efekt zmiany tego ustawienia:** Będzie to sekcja zamykająca Twój list.
  - **Zalecana wartość:** Strona internetowa Twojego sklepu, adres e-mail do kontaktu lub przyjazne zakończenie, takie jak „Z poważaniem, Zespół [Nazwa Twojego Sklepu].”
  - **Scenariusz / przykład dla sprzedawcy:** „Odwiedź nas na [www.twojasklep.com](http://www.twojasklep.com), aby znaleźć więcej niesamowitych produktów!”

#### **Opcje Drukowania i Projektowania**

- **Drukuj Kod Rabatowy na Liście:**

  - **Co robi to ustawienie:** Prosty przełącznik, aby włączyć kod rabatowy bezpośrednio w drukowanym liście.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (TAK):* Unikalny kod rabatowy zostanie automatycznie wstawiony do treści listu w wybranym miejscu (lub w domyślnej pozycji, jeśli nie określono w treści listu).
    - *Gdy wyłączone (NIE):* Kod rabatowy nie zostanie wydrukowany na liście. Możesz wybrać tę opcję, jeśli drukujesz oddzielne karty rabatowe.
  - **Zalecana wartość:** TAK, dla wygody i aby upewnić się, że klient ma kod.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby klient otrzymał jeden dokument, włącz tę opcję.
- **Kolor Tekstu (dla Listu/Kuponu):**

  - **Co robi to ustawienie:** Pozwala wybrać kolor tekstu na drukowanych dokumentach.
  - **Efekt zmiany tego ustawienia:** Zmienia kolor atramentu używanego do tekstu.
  - **Zalecana wartość:** Czarny lub ciemny, czytelny kolor, który dobrze kontrastuje z białym papierem.
  - **Scenariusz / przykład dla sprzedawcy:** Użyj podstawowego koloru tekstu swojej marki dla spójności.
- **Kolor Tła (dla Sekcji Kuponu):**

  - **Co robi to ustawienie:** Jeśli drukujesz kupony bezpośrednio na liście, ustawia kolor tła dla obszaru kodu rabatowego, aby go wyróżnić.
  - **Efekt zmiany tego ustawienia:** Tworzy kolorowe pole za kodem rabatowym.
  - **Zalecana wartość:** Jasny, subtelny kolor, który nie zasłania tekstu, lub pozostaw biały, jeśli wolisz.
  - **Scenariusz / przykład dla sprzedawcy:** Jasnoszary lub pastelowa wersja koloru Twojej marki, aby podkreślić kupon.
- **Rozmiar Czcionki (dla Listu/Kuponu):**

  - **Co robi to ustawienie:** Kontroluje rozmiar tekstu na drukowanych dokumentach.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawione na „12px”:* Tekst będzie miał standardowy, czytelny rozmiar.
    - *Gdy ustawione na „16px”:* Tekst będzie większy, łatwiejszy do odczytania dla niektórych.
  - **Zalecana wartość:** 10-14px dla tekstu głównego, nieco większy dla nagłówków.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja grupa docelowa obejmuje starszych demograficznie, nieco większy rozmiar czcionki może być korzystny.

#### **Wybór i Generowanie Klientów**

- **Wybierz Klientów:**

  - **Co robi to ustawienie:** Ta sekcja pozwala wybrać, którzy klienci otrzymają spersonalizowane listy i kupony. Możesz wybrać konkretnych klientów z listy.
  - **Efekt zmiany tego ustawienia:** Tylko wybrani klienci będą mieli wygenerowane kupony, a ich dane zostaną użyte do listów.
  - **Zalecana wartość:** Wybierz klientów na podstawie celów kampanii (np. nowi klienci, lojalni klienci, nieaktywni klienci).
  - **Scenariusz / przykład dla sprzedawcy:** Wybierz wszystkich klientów, którzy nie dokonali zakupu w ciągu ostatnich 6 miesięcy, aby ich ponownie zaangażować.
- **Przycisk Generuj Kupony i Listy:**

  - **Co robi to ustawienie:** Po skonfigurowaniu wszystkich ustawień i wybraniu klientów, kliknięcie tego przycisku rozpocznie proces generowania unikalnych kodów rabatowych i przygotowania spersonalizowanych listów do druku.
  - **Efekt zmiany tego ustawienia:** Ta akcja tworzy nowe reguły koszyka (kupony) w Twoim sklepie PrestaShop i generuje dokumenty do druku.
  - **Zalecana wartość:** Kliknij dopiero po dokładnym przejrzeniu wszystkich ustawień.
  - **Scenariusz / przykład dla sprzedawcy:** Po zaplanowaniu kampanii kliknij ten przycisk, aby przygotować wysyłkę.

#### **Tabela Szybkiego Odniesienia do Konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i Wpływ |
| --- | --- | --- | --- |
| Główna Konfiguracja | Prefiks Kuponu | `LOYALTY-` | Tekst na początku kodu rabatowego. Pomaga zidentyfikować kampanię. |
| Główna Konfiguracja | Sufiks Kuponu | Puste | Tekst na końcu kodu rabatowego. Przydatny do śledzenia. |
| Główna Konfiguracja | Długość Kodu Rabatowego | 8-12 | Liczba losowych znaków w kodzie. Wpływa na bezpieczeństwo/użyteczność. |
| Główna Konfiguracja | Wartość Kuponu | `10` (np. 10 € lub 10%) | Kwota lub procent rabatu. |
| Główna Konfiguracja | Minimalna Kwota Kuponu | `0` (lub 2-3x wartość kuponu) | Minimalne zamówienie do użycia kuponu. Zapewnia rentowność. |
| Główna Konfiguracja | Data Ważności Kuponu (Dni) | `30-90` | Dni do wygaśnięcia kuponu. Tworzy pilność. |
| Główna Konfiguracja | Tekst Nagłówka Listu | `Szanowny Kliencie,` | Główne powitanie/tytuł listu. |
| Główna Konfiguracja | Tekst Treści Listu | (Własna wiadomość) | Główna treść listu, wyjaśniająca ofertę. |
| Główna Konfiguracja | Tekst Stopki Listu | `www.twojasklep.com` | Uwagi końcowe, informacje kontaktowe. |
| Główna Konfiguracja | Drukuj Kod Rabatowy na Liście | TAK | Zawiera kod rabatowy bezpośrednio na liście. |
| Główna Konfiguracja | Kolor Tekstu | Czarny | Kolor całego tekstu na drukowanych dokumentach. |
| Główna Konfiguracja | Kolor Tła | Biały (lub jasnoszary) | Kolor tła dla obszaru kodu rabatowego. |
| Główna Konfiguracja | Rozmiar Czcionki | `12px` | Rozmiar tekstu na drukowanych dokumentach. |
| Główna Konfiguracja | Wybierz Klientów | (Konkretny wybór) | Wybierz, którzy klienci otrzymają przesyłkę. |
| Główna Konfiguracja | Generuj Kupony i Listy | (Kliknięcie przycisku) | Tworzy kupony i dokumenty do druku. |

## 3. Rozwiązywanie Problemów Sprzedawcy i Często Zadawane Pytania (FAQ)

**P1: Wygenerowałem kupony, ale wydaje się, że nie działają w moim sklepie.**
O1: Po wygenerowaniu moduł tworzy „Reguły koszyka” w PrestaShop.
1. **Sprawdź Reguły Koszyka:** Przejdź do **Katalog > Rabaty > Reguły koszyka** w Panelu administracyjnym. Upewnij się, że wygenerowane kupony są tam wymienione i są „Włączone”.
2. **Sprawdź Warunki:** Zweryfikuj, czy warunki kuponu (minimalna kwota, data ważności, ograniczenia dla klientów) odpowiadają Twoim zamierzeniom. Jeśli klient próbuje użyć kuponu, który nie spełnia kryteriów, nie zostanie on zastosowany.
3. **Wyczyść Pamięć Podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe zastosowanie nowych ustawień. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.

**P2: Wydrukowane listy nie wyglądają prawidłowo lub kolory są nieprawidłowe.**
O2:
1. **Sprawdź Ustawienia Modułu:** Ponownie odwiedź stronę konfiguracji modułu. Dokładnie sprawdź ustawienia „Kolor Tekstu”, „Kolor Tła” i „Rozmiar Czcionki”. Upewnij się, że wybrano kolory, które dobrze się drukują.
2. **Ustawienia Drukarki:** Ostateczna jakość wydruku w dużej mierze zależy od Twojej fizycznej drukarki. Sprawdź poziom atramentu drukarki, typ papieru i ustawienia jakości druku. Spróbuj wydrukować stronę testową z innej aplikacji.
3. **Podgląd Wydruku w Przeglądarce:** Kiedy inicjujesz drukowanie z przeglądarki, użyj funkcji podglądu wydruku, aby zobaczyć, jak będzie wyglądać, zanim zużyjesz atrament i papier. W razie potrzeby dostosuj ustawienia drukowania w przeglądarce (np. marginesy, nagłówki/stopki).

**P3: Czy mogę przetłumaczyć treść listu na różne języki dla klientów międzynarodowych?**
O3: Obecna wersja modułu nie oferuje wbudowanych pól wielojęzycznych dla treści listu bezpośrednio w swojej konfiguracji. Musiałbyś:
1. **Generować dla każdego języka:** Skonfiguruj moduł z treścią listu w jednym języku, wygeneruj listy dla odpowiednich klientów, a następnie powtórz proces dla innych języków i grup klientów.
2. **Ręczne Tłumaczenie:** Jeśli wyeksportujesz dane klientów i kody rabatowe, możesz użyć oddzielnego narzędzia do korespondencji seryjnej, aby stworzyć listy wielojęzyczne.

**P4: Chcę wysyłać listy tylko do klientów z konkretnego kraju. Jak to zrobić?**
O4: Funkcja „Wybierz Klientów” modułu pozwala wybierać pojedynczych klientów. Jeśli musisz filtrować według kraju lub innych kryteriów, zazwyczaj musiałbyś:
1. **Eksportuj Dane Klientów:** Przejdź do **Klienci > Klienci** w Panelu administracyjnym i użyj funkcji eksportu, aby uzyskać listę wszystkich swoich klientów.
2. **Filtruj Zewnętrznie:** Użyj programu do arkuszy kalkulacyjnych (takiego jak Excel lub Arkusze Google), aby filtrować listę klientów według kraju lub innych pożądanych kryteriów.
3. **Ręczny Wybór:** Wróć do modułu i ręcznie wybierz przefiltrowanych klientów z listy. Może to być żmudne w przypadku dużych list.
4. **Dostosowanie przez Programistę (Zaawansowane):** W przypadku bardzo dużych lub złożonych potrzeb filtrowania, programista mógłby rozszerzyć moduł, aby dodać bardziej zaawansowane opcje filtrowania klientów.

## 4. Przewodnik dla Programistów i Webmasterów (Architektura Techniczna i Mapa Kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem „Voucher & Letters Printer”.

### 4.1 Przegląd Architektury

Moduł „Voucher & Letters Printer” to standardowy moduł PrestaShop działający głównie w Panelu administracyjnym. Wykorzystuje klasę `Module` PrestaShop do swojej podstawowej funkcjonalności oraz klasę `Configuration` do przechowywania ustawień. Głównym celem modułu jest generowanie obiektów `CartRule` (kuponów), a następnie renderowanie zawartości HTML do druku na podstawie ustawień modułu i wybranych danych klientów. Nie wprowadza niestandardowych tabel baz danych ani złożonych struktur `ObjectModel` poza tymi, które PrestaShop już zapewnia dla `CartRule` i `Customer`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja i logika są obsługiwane w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i Modele Podstawowe (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas w katalogu `classes/`. Bezpośrednio współdziała z podstawowymi klasami PrestaShop, głównie:

- `Module`: Klasa bazowa dla samego modułu.
- `Configuration`: Do przechowywania i pobierania ustawień modułu.
- `Customer`: Do pobierania danych klientów do personalizacji listów.
- `CartRule`: Do tworzenia i zarządzania generowanymi kodami rabatowymi.

### 4.4 Zasoby JavaScript (`views/js/`)

- **`voucherletter/js/jscolor/jscolor.js`**

  - **Zakres:** Panel administracyjny.
  - **Opis:** Jest to zewnętrzna biblioteka JavaScript do zaawansowanego wyboru kolorów. Pozwala administratorowi wizualnie wybierać kolory tekstu i tła w formularzu konfiguracji modułu.
  - **Funkcjonalność:** Wiąże się z polami wejściowymi o określonych klasach (np. `jscolor`), aby wyświetlać paletę kolorów i aktualizować wartość pola wejściowego wybranym szesnastkowym kodem koloru.
- **`voucherletter/js/script.js`**

  - **Zakres:** Panel administracyjny (strona konfiguracji modułu).
  - **Opis:** Zawiera niestandardową logikę JavaScript specyficzną dla formularza konfiguracji modułu.
  - **Funkcjonalność:**
    - Prawdopodobnie obsługuje żądania AJAX do generowania kuponów i listów (chociaż dokumentacja modułu sugeruje, że `getContent()` obsługuje cały proces, ten skrypt może pomagać w przesyłaniu formularzy lub dynamicznych aktualizacjach).
    - Może zawierać logikę walidacji pól formularza (np. upewnienie się, że wartość kuponu jest liczbą).
    - Może zarządzać wyświetlaniem/ukrywaniem niektórych elementów formularza na podstawie innych wyborów.
    - Potencjalnie uruchamia funkcję drukowania w przeglądarce po wygenerowaniu treści listu.

### 4.5 Arkusze Stylów CSS (`views/css/`)

Dokumentacja modułu wskazuje, że w `views/css/` nie ma niestandardowych plików CSS. Stylizacja konfiguracji Panelu administracyjnego opierałaby się na domyślnym CSS motywu administracyjnego PrestaShop. Wszelka stylizacja *wydruku* byłaby wbudowanym CSS generowanym przez kod PHP lub bardzo podstawową stylizacją HTML.

### 4.6 Struktura Szablonów Smarty (`views/templates/`)

Dokumentacja modułu wskazuje, że w `views/templates/` nie ma niestandardowych plików `.tpl`. Sugeruje to, że:

- Formularz konfiguracji Panelu administracyjnego jest prawdopodobnie renderowany bezpośrednio w metodzie `getContent()` za pomocą `HelperForm` PrestaShop lub przez konkatenację ciągów HTML.
- Treść listu do druku jest generowana dynamicznie jako ciąg HTML w kodzie PHP, a następnie wyprowadzana do funkcji drukowania przeglądarki.

### 4.7 Schemat Bazy Danych i Mapa Hooków

- **Tabele Baz Danych**:

  - Moduł nie tworzy żadnych niestandardowych tabel baz danych.
  - Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop. Klucze konfiguracyjne zazwyczaj przestrzegałyby wzorca, takiego jak `VOUCHERLETTER_PREFIX`, `VOUCHERLETTER_VALUE` itp.
  - Tworzy nowe wpisy w `ps_cart_rule` i powiązanych tabelach (`ps_cart_rule_lang`, `ps_cart_rule_product_rule_group` itp.) podczas generowania kuponów.
- **Tabela Zarejestrowanych Hooków**:
  Dokumentacja modułu wskazuje, że moduł nie rejestruje żadnych hooków front-office (Header, Columns, Product, Footer). Potwierdza to jego główną funkcję jako narzędzia Panelu administracyjnego do generowania fizycznej poczty.

| Nazwa Hooka | Czas Wykonania | Cel Techniczny |
| --- | --- | --- |
| `actionModuleInstall` | Podczas instalacji modułu | Ustawia domyślne wartości konfiguracyjne w `ps_configuration`. |
| `actionModuleUninstall` | Podczas deinstalacji modułu | Czyści wartości konfiguracyjne z `ps_configuration`. |

## 5. Oficjalne Wsparcie i Aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkiej dalszej pomocy z modułem „Voucher & Letters Printer”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
"""
