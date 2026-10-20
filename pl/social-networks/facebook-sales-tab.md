---
title: "Zakładka Sprzedaż na Facebooku - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów dla modułu PrestaShop „Zakładka Sprzedaż na Facebooku” od MyPresta.eu."
sidebar:
  label: "Zakładka Sprzedaż na Facebooku - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook Sales Tab na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-sales-tab.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-sales-tab/)
>
> ---


# Zakładka Sprzedaż na Facebooku

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).
- **Wymagania zewnętrzne**: Aktywny Fanpage na Facebooku (strona biznesowa), którego jesteś administratorem. Będziesz także musiał utworzyć aplikację Facebooka, aby połączyć swój sklep z Fanpage'em, co wiąże się z uzyskaniem identyfikatora aplikacji (App ID) i tajnego klucza aplikacji (App Secret) z portalu dla deweloperów Facebooka.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Zakładka Sprzedaż na Facebooku)

Jest to główny i jedyny ekran konfiguracji modułu Zakładka Sprzedaż na Facebooku. Tutaj połączysz swój sklep PrestaShop z Fanpage'em na Facebooku i zdefiniujesz, jakie treści będą wyświetlane.

Aby uzyskać dostęp do tej strony, przejdź do **Panel administracyjny > Moduły > Menedżer modułów**, wyszukaj „Zakładka Sprzedaż na Facebooku” i kliknij „Konfiguruj”.

#### **Ustawienia aplikacji Facebooka**

Te ustawienia są kluczowe dla nawiązania połączenia między Twoim sklepem PrestaShop a Twoim Fanpage'em na Facebooku. Będziesz musiał utworzyć aplikację Facebooka za pośrednictwem portalu dla deweloperów Facebooka, aby uzyskać te dane uwierzytelniające.

-   **Identyfikator aplikacji Facebooka (Facebook App ID):**

    -   **Co robi to ustawienie:** Jest to unikalny identyfikator Twojej aplikacji Facebooka. Informuje Facebooka, która aplikacja próbuje połączyć się z Twoim Fanpage'em.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po poprawnym wprowadzeniu:* Umożliwia modułowi komunikację z Facebookiem i wyświetlanie zakładki sprzedaży.
        -   *Po niepoprawnym wprowadzeniu lub pozostawieniu pustym:* Moduł nie będzie mógł połączyć się z Facebookiem, a zakładka sprzedaży nie będzie działać ani pojawiać się na Twoim Fanpage'u.
    -   **Zalecana wartość:** Dokładny identyfikator aplikacji dostarczony przez Facebooka podczas tworzenia aplikacji.
    -   **Scenariusz/przykład dla sprzedawcy:** Utworzyłeś aplikację Facebooka o nazwie „Zakładka Sprzedaż Mojego Sklepu” na developers.facebook.com, a Facebook przypisał jej identyfikator aplikacji, np. `123456789012345`. Wprowadziłbyś ten numer tutaj.
-   **Tajny klucz aplikacji Facebooka (Facebook App Secret):**

    -   **Co robi to ustawienie:** Jest to tajny klucz powiązany z Twoją aplikacją Facebooka, używany do uwierzytelniania żądań Twojej aplikacji do Facebooka. Powinien być utrzymywany w tajemnicy.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po poprawnym wprowadzeniu:* Zapewnia bezpieczną komunikację między Twoim sklepem a Facebookiem.
        -   *Po niepoprawnym wprowadzeniu lub pozostawieniu pustym:* Facebook odrzuci próby połączenia, a zakładka sprzedaży nie będzie działać.
    -   **Zalecana wartość:** Dokładny tajny klucz aplikacji dostarczony przez Facebooka podczas tworzenia aplikacji.
    -   **Scenariusz/przykład dla sprzedawcy:** Wraz z identyfikatorem aplikacji, Facebook dostarcza tajny klucz aplikacji (np. `abcdef1234567890abcdef1234567890`). Wprowadzasz ten ciąg znaków tutaj.
-   **Identyfikator strony Facebooka (Facebook Page ID):**

    -   **Co robi to ustawienie:** Jest to unikalny identyfikator Twojego konkretnego Fanpage'a na Facebooku, na którym chcesz, aby pojawiła się zakładka sprzedaży.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po poprawnym wprowadzeniu:* Moduł wie, który Fanpage ma być celem dodania zakładki sprzedaży.
        -   *Po niepoprawnym wprowadzeniu lub pozostawieniu pustym:* Zakładka sprzedaży nie zostanie dodana do Twojego wybranego Fanpage'a, lub może zostać dodana do niewłaściwego, jeśli wprowadzono niepoprawny identyfikator.
    -   **Zalecana wartość:** Dokładny identyfikator strony Twojego Fanpage'a na Facebooku. Zazwyczaj można go znaleźć w sekcji „Informacje” Twojego Fanpage'a lub za pomocą narzędzia do wyszukiwania identyfikatorów stron Facebooka.
    -   **Scenariusz/przykład dla sprzedawcy:** Fanpage Twojego sklepu to „Mój Niesamowity Sklep”. Znajdujesz jego identyfikator strony (np. `987654321098765`) i wprowadzasz go tutaj.

#### **Ustawienia treści zakładki sprzedaży**

Te ustawienia kontrolują, jakie produkty lub promocje są wyświetlane na Twojej zakładce Sprzedaż na Facebooku.

-   **Liczba produktów do wyświetlenia:**

    -   **Co robi to ustawienie:** Określa, ile produktów z Twojej specjalnej selekcji sprzedaży zostanie pokazanych na zakładce Facebooka.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po ustawieniu na wyższą liczbę (np. 20):* Więcej produktów będzie widocznych, dając klientom szerszy wybór.
        -   *Po ustawieniu na niższą liczbę (np. 5):* Mniej produktów zostanie wyświetlonych, potencjalnie skupiając uwagę na Twoich najlepszych ofertach.
    -   **Zalecana wartość:** 10-20, w zależności od tego, ile aktywnych wyprzedaży zazwyczaj masz i ile treści chcesz zaprezentować.
    -   **Scenariusz/przykład dla sprzedawcy:** Masz 15 produktów na wyprzedaży. Ustawienie tej wartości na „15” zapewnia, że wszystkie z nich zostaną pokazane na Twojej zakładce Facebooka. Jeśli chcesz wyróżnić tylko 5 najlepszych, ustawisz ją na „5”.
-   **Wyświetlaj produkty z określonych kategorii:**

    -   **Co robi to ustawienie:** Pozwala filtrować produkty wyświetlane na zakładce Facebooka, aby uwzględniać tylko te z wybranych kategorii w Twoim sklepie PrestaShop.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po wybraniu konkretnych kategorii:* Tylko produkty należące do tych kategorii pojawią się na zakładce Facebooka, nawet jeśli inne produkty są na wyprzedaży.
        -   *Po niewybraniu żadnych kategorii (lub wybraniu wszystkich):* Wszystkie produkty spełniające kryteria „wyprzedaży” zostaną wyświetlone.
    -   **Zalecana wartość:** Wybierz kategorie istotne dla Twoich aktualnych promocji lub najlepiej sprzedających się produktów, które chcesz wyróżnić na Facebooku.
    -   **Scenariusz/przykład dla sprzedawcy:** Prowadzisz specjalną promocję na „Sukienki letnie” i „Akcesoria plażowe”. Wybierzesz te dwie kategorie, aby upewnić się, że tylko te produkty pojawią się na Twojej zakładce Sprzedaż na Facebooku.
-   **Wyświetlaj produkty z określonymi rabatami/wyprzedażami:**

    -   **Co robi to ustawienie:** Jest to główny filtr określający, co stanowi produkt „wyprzedażowy”. Możesz wybrać wyświetlanie produktów, które mają określoną obniżkę ceny.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po włączeniu i skonfigurowaniu:* Wyświetlane będą tylko produkty z aktywnymi cenami specjalnymi lub rabatami procentowymi.
        -   *Po wyłączeniu:* Moduł może wyświetlać regularne produkty lub produkty na podstawie innych kryteriów (chociaż głównym celem modułu jest „sprzedaż”).
    -   **Zalecana wartość:** TAK, i upewnij się, że Twoje produkty mają aktywne ceny specjalne skonfigurowane w PrestaShop.
    -   **Scenariusz/przykład dla sprzedawcy:** Ustawiłeś 10% rabatu na wszystkie „Płaszcze zimowe” w ustawieniach produktów PrestaShop. To ustawienie zapewnia, że te przecenione płaszcze pojawią się na Twojej zakładce Facebooka.

#### **Ogólne ustawienia wyświetlania**

-   **Tytuł zakładki na Facebooku:**

    -   **Co robi to ustawienie:** Jest to tekst, który pojawi się jako nazwa zakładki na Twoim Fanpage'u na Facebooku.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po ustawieniu na „Oferty specjalne”:* Twoja zakładka zostanie oznaczona jako „Oferty specjalne” na Facebooku.
        -   *Po ustawieniu na „Kup teraz”:* Twoja zakładka zostanie oznaczona jako „Kup teraz”.
    -   **Zalecana wartość:** Coś jasnego i zachęcającego, np. „Promocje”, „Kup teraz” lub „Nasze okazje”.
    -   **Scenariusz/przykład dla sprzedawcy:** Chcesz wyraźnie wskazać, że ta zakładka jest przeznaczona na promocje, więc ustawiasz tytuł na „Błyskawiczne wyprzedaże!”.
-   **Ikona zakładki:**

    -   **Co robi to ustawienie:** Pozwala przesłać niestandardową ikonę, która pojawi się obok tytułu zakładki na Facebooku. Pomaga to wyróżnić Twoją zakładkę.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po przesłaniu ikony:* Twoja zakładka będzie miała niestandardowy identyfikator wizualny.
        -   *Po nieprzesłaniu ikony:* Facebook użyje domyślnej ikony, lub zakładka może pojawić się bez konkretnej ikony.
    -   **Zalecana wartość:** Mała, wyraźna i odpowiednia ikona (np. koszyk na zakupy, gwiazdka, znak procentu), która pasuje do Twojej marki.
    -   **Scenariusz/przykład dla sprzedawcy:** Przesyłasz mały obrazek koszyka na zakupy, aby Twoja zakładka „Kup teraz” była wizualnie atrakcyjna i łatwa do zauważenia.

#### **Tabela szybkiego odniesienia do konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Identyfikator aplikacji Facebooka | Twój identyfikator aplikacji Facebooka | Łączy Twój sklep z Twoją aplikacją Facebooka w celu uwierzytelnienia. |
| Konfiguracja modułu | Tajny klucz aplikacji Facebooka | Twój tajny klucz aplikacji Facebooka | Bezpiecznie uwierzytelnia Twoją aplikację na Facebooku. |
| Konfiguracja modułu | Identyfikator strony Facebooka | Identyfikator Twojego Fanpage'a na Facebooku | Określa, do którego Fanpage'a zostanie dodana zakładka sprzedaży. |
| Konfiguracja modułu | Liczba produktów do wyświetlenia | 10-20 | Kontroluje, ile produktów objętych wyprzedażą jest wyświetlanych na zakładce. |
| Konfiguracja modułu | Wyświetlaj produkty z określonych kategorii | Wybierz odpowiednie kategorie | Filtruje produkty według kategorii do wyświetlenia na zakładce. |
| Konfiguracja modułu | Wyświetlaj produkty z określonymi rabatami/wyprzedażami | TAK | Zapewnia, że na zakładce wyświetlane są tylko produkty objęte rabatem. |
| Konfiguracja modułu | Tytuł zakładki na Facebooku | „Promocje” / „Kup teraz” | Ustawia widoczną nazwę zakładki na Twoim Fanpage'u na Facebooku. |
| Konfiguracja modułu | Ikona zakładki | Prześlij odpowiednią ikonę | Zapewnia niestandardową ikonę wizualną dla Twojej zakładki Facebooka. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moja zakładka Sprzedaż na Facebooku nie pojawia się na moim Fanpage'u. Co powinienem zrobić?**
O1:

-   **Sprawdź identyfikator aplikacji, tajny klucz aplikacji i identyfikator strony:** Dokładnie sprawdź, czy wszystkie trzy wartości zostały poprawnie wprowadzone w konfiguracji modułu. Nawet jedna literówka uniemożliwi połączenie.
-   **Status aplikacji Facebooka:** Upewnij się, że Twoja aplikacja Facebooka jest aktywna i publicznie dostępna (nie w trybie deweloperskim). Możesz to sprawdzić w swoim panelu dewelopera Facebooka.
-   **Uprawnienia:** Upewnij się, że Twoja aplikacja Facebooka ma niezbędne uprawnienia do zarządzania stronami.
-   **Pamięć podręczna:** Wyczyść pamięć podręczną Smarty w PrestaShop (Zaawansowane > Wydajność) i pamięć podręczną przeglądarki. Czasami zmiany potrzebują chwili, aby się rozprzestrzenić.
-   **Administrator strony Facebooka:** Upewnij się, że konto Facebooka, którego używasz do zarządzania Fanpage'em, ma prawa administratora zarówno dla Fanpage'a, jak i aplikacji Facebooka.

**P2: Produkty wyświetlane na zakładce Facebooka nie są tymi, których się spodziewam.**
O2:

-   **Ustawienie „Wyświetlaj produkty z określonymi rabatami/wyprzedażami”:** Upewnij się, że jest włączone, jeśli chcesz wyświetlać tylko przecenione produkty.
-   **Rabaty na produkty:** Sprawdź, czy produkty, które *spodziewasz się* zobaczyć, faktycznie mają aktywne ceny specjalne lub rabaty procentowe skonfigurowane w ustawieniach produktów PrestaShop.
-   **Ustawienie „Wyświetlaj produkty z określonych kategorii”:** Jeśli wybrałeś konkretne kategorie, upewnij się, że produkty, które chcesz wyświetlić, należą do tych kategorii.
-   **„Liczba produktów do wyświetlenia”:** Jeśli masz wiele wyprzedaży, ale ta liczba jest niska, wyświetli się tylko kilka pierwszych.

**P3: Jak uzyskać identyfikator aplikacji Facebooka, tajny klucz aplikacji i identyfikator strony?**
O3:

-   **Identyfikator aplikacji Facebooka i tajny klucz aplikacji:** Przejdź do [developers.facebook.com](https://developers.facebook.com/), zaloguj się i utwórz nową aplikację. Postępuj zgodnie z instrukcjami Facebooka, aby skonfigurować nową aplikację, zazwyczaj wybierając typ „Biznes” lub „Strona internetowa”. Po utworzeniu znajdziesz identyfikator aplikacji i tajny klucz aplikacji w ustawieniach panelu swojej aplikacji.
-   **Identyfikator strony Facebooka:** Przejdź do swojego Fanpage'a na Facebooku. Identyfikator strony często można znaleźć w sekcji „Informacje” Twojej strony. Alternatywnie, istnieją narzędzia online (wyszukaj „Facebook Page ID Finder”), gdzie możesz wkleić adres URL swojego Fanpage'a, aby pobrać jego identyfikator.

**P4: Ikona lub tytuł zakładki nie aktualizuje się na Facebooku.**
O4:

-   **Buforowanie Facebooka:** Sam Facebook może buforować informacje o stronie. Odzwierciedlenie zmian w tytule lub ikonie zakładki globalnie może zająć trochę czasu (do kilku godzin).
-   **Zapis konfiguracji modułu:** Upewnij się, że zapisałeś konfigurację modułu po wprowadzeniu zmian.
-   **Wyczyść pamięć podręczną:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność) i pamięć podręczną przeglądarki.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla deweloperów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Facebook Sales Tab` (`prestasales`) to standardowy moduł PrestaShop zaprojektowany do integracji z platformą Facebook. Jego główną funkcją jest dostarczanie treści (konkretnie listy produktów objętych wyprzedażą), które mogą być osadzone w zakładce Fanpage'a na Facebooku. Moduł wykorzystuje system konfiguracji PrestaShop do przechowywania danych uwierzytelniających API Facebooka i preferencji wyświetlania. Nie wprowadza złożonych wzorców MVC ani niestandardowych tabel baz danych, lecz opiera się na podstawowych funkcjonalnościach PrestaShop do pobierania produktów i zarządzania konfiguracją. Główna logika modułu znajduje się w pliku `de.php`, obsługując instalację, deinstalację i wyświetlanie konfiguracji.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównej klasy modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas ani definicji `ObjectModel`. Bezpośrednio współdziała z podstawowymi klasami PrestaShop `Product` i `Category` oraz klasą `Configuration` dla ustawień.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`prestasales/css/css.css`**:
    -   **Zakres:** Ten arkusz stylów jest przeznaczony do stylizowania treści wyświetlanych w zakładce Facebooka.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Zazwyczaj zawierałby style dla list produktów, obrazów, cen, odznak rabatowych i przycisków „dodaj do koszyka” lub „zobacz produkt” w osadzonej zakładce Facebooka.
    -   **Kluczowe selektory klas CSS, które deweloperzy mogą nadpisać w swoim motywie:** Deweloperzy powinni sprawdzić wyjście HTML w zakładce Facebooka, aby zidentyfikować konkretne nazwy klas. Typowe selektory mogą obejmować `.prestasales-product-list`, `.prestasales-product-item`, `.prestasales-product-image`, `.prestasales-product-name`, `.prestasales-price`, `.prestasales-discount`, `.prestasales-button`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie wymienia jawnie plików `.tpl` w dostarczonym spisie. Jednakże, bazując na jego funkcjonalności, zazwyczaj zawierałby:

-   **Szablony hooków (`views/templates/hook/`)**:

    -   Jest bardzo prawdopodobne, że szablon taki jak `views/templates/hook/displayFacebookSalesTab.tpl` (lub podobny) istnieje wewnętrznie w pliku `de.php` modułu lub jest generowany na bieżąco. Ten szablon byłby odpowiedzialny za renderowanie struktury HTML listy produktów, która jest następnie serwowana na Facebooka.
    -   **Cel:** Ten szablon iterowałby po wybranych produktach objętych wyprzedażą i wyświetlał ich obrazy, nazwy, ceny i linki, sformatowane do osadzenia w iframe Facebooka.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   Biorąc pod uwagę, że konfiguracja jest obsługiwana przez `getContent()`, szablon taki jak `views/templates/admin/configure.tpl` lub `views/templates/admin/configuration_form.tpl` byłby używany do renderowania formularza konfiguracji modułu w panelu administracyjnym. Ten szablon zawierałby pola wejściowe dla identyfikatora aplikacji, tajnego klucza aplikacji, identyfikatora strony, opcji wyświetlania produktów itp.
-   **Szablony front-office (`views/templates/front/`)**:

    -   Nie oczekuje się dedykowanych szablonów front-office, ponieważ wyjście modułu jest przeznaczone głównie dla platformy Facebook.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele baz danych**:

    -   Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` PrestaShop przy użyciu kluczy takich jak `PRESTASALES_APP_ID`, `PRESTASALES_APP_SECRET`, `PRESTASALES_PAGE_ID`, `PRESTASALES_NUM_PRODUCTS`, `PRESTASALES_CATEGORIES`, `PRESTASALES_DISCOUNTS_ONLY`, `PRESTASALES_TAB_TITLE`, `PRESTASALES_TAB_ICON`.
-   **Tabela zarejestrowanych hooków**:
    Główna interakcja modułu z systemem hooków PrestaShop dotyczyłaby jego konfiguracji i potencjalnie renderowania treści, które pobiera Facebook.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Chociaż moduł nie wyświetla treści bezpośrednio w sklepie, może używać tego hooka do ładowania niezbędnych skryptów SDK Facebooka lub meta tagów, gdyby miał implementować zaawansowane funkcje integracji z Facebookiem (np. tagi Open Graph), choć nie jest to wyraźnie określone dla podstawowej funkcji tego modułu. |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony back-office. | Służy do ładowania specyficznych dla modułu CSS lub JS dla strony konfiguracji, jeśli takie istnieją. |
| `moduleRoutes` | Podczas inicjalizacji przepisywania adresów URL. | Nie jest jawnie używany przez ten moduł, ponieważ nie definiuje niestandardowych tras front-office. |
| `actionProductUpdate` / `actionProductAdd` | Po zaktualizowaniu lub dodaniu produktu. | Nie jest jawnie używany, ale mógłby być użyty do czyszczenia pamięci podręcznej związanej z listami produktów dla zakładki Facebooka. |
| `actionModuleInstall` | Podczas instalacji modułu. | Do rejestrowania domyślnych ustawień konfiguracji i potencjalnego konfigurowania początkowych kroków integracji z aplikacją Facebooka. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Do czyszczenia danych konfiguracyjnych z `ps_configuration`. |

Główna funkcjonalność dostarczania treści na Facebooka jest prawdopodobnie obsługiwana przez bezpośrednie żądanie do głównego pliku PHP modułu (`de.php`) lub konkretnej wewnętrznej metody, która renderuje listę produktów, a nie przez standardowy hook `display` PrestaShop. Ta treść jest następnie osadzana w iframe na Fanpage'u na Facebooku.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dalszej pomocy z modułem „Zakładka Sprzedaż na Facebooku”, prosimy o zapoznanie się z kontem klienta na [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
