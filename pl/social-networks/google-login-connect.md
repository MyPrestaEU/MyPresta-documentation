---
title: "Google Login Connect - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Google Login Connect od MyPresta.eu."
sidebar:
  label: "Google Login Connect"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Google Login Connect na MyPresta.eu](https://mypresta.eu/modules/social-networks/google-login-connect.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/google-login-connect/)
>
> ---


# Google Login Connect

## 1. Wymagania i Kompatybilność

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 5.6 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do bezpiecznej komunikacji z API Google.

## 2. Kompletny Przewodnik Konfiguracji (Każde Ustawienie Pogrupowane według Ekranu)

### 2.1 Strona Konfiguracji Modułu (Panel Administracyjny > Moduły > Konfiguruj > Google Login Connect)

To jest główny ekran konfiguracji, na którym ustawisz swoje dane uwierzytelniające Google API i zdecydujesz, gdzie w Twoim sklepie pojawi się przycisk „Zaloguj się przez Google”.

#### **Dane Uwierzytelniające Google API**

Przed skonfigurowaniem modułu musisz utworzyć projekt Google API i uzyskać swój Identyfikator Klienta. Jest to kluczowe dla bezpiecznej komunikacji modułu z Google.

**Jak uzyskać swój Identyfikator Klienta Google:**
1.  Przejdź do [Google Cloud Console](https://console.cloud.google.com/).
2.  Utwórz nowy projekt lub wybierz istniejący.
3.  Przejdź do **API i Usługi > Dane uwierzytelniające**.
4.  Kliknij **„Utwórz dane uwierzytelniające”** i wybierz **„Identyfikator klienta OAuth”**.
5.  Wybierz **„Aplikacja internetowa”** jako typ aplikacji.
6.  W sekcji **„Autoryzowane źródła JavaScript”** dodaj adres URL swojego sklepu (np. `https://www.twojsklep.com`).
7.  W sekcji **„Autoryzowane identyfikatory URI przekierowania”** dodaj adres URL swojego sklepu, a następnie ścieżkę zwrotną modułu (np. `https://www.twojsklep.com/module/glogin/index`).
8.  Po utworzeniu Google poda Ci **Identyfikator Klienta**. Skopiuj tę wartość.

-   **Identyfikator Klienta Google (ggl_appid)**
    -   **Co robi to ustawienie:** Jest to unikalny identyfikator Twojej aplikacji (Twojego sklepu PrestaShop), którego Google używa do rozpoznawania Twoich żądań logowania. Jest on niezbędny do działania funkcji „Zaloguj się przez Google”.
    -   **Skutek zmiany tego ustawienia:**
        -   *Po poprawnym wprowadzeniu:* Twoje przyciski logowania Google będą działać, umożliwiając klientom uwierzytelnianie za pośrednictwem Google.
        -   *Po niepoprawnym wprowadzeniu lub pozostawieniu pustego:* Przyciski logowania Google nie będą działać, lub klienci napotkają błędy podczas próby logowania przez Google.
    -   **Zalecana wartość:** Identyfikator Klienta uzyskany z Google Cloud Console.
    -   **Scenariusz/przykład dla sprzedawcy:** Właśnie utworzyłeś swój projekt Google API i otrzymałeś `1234567890-abcdefg.apps.googleusercontent.com`. Musisz wkleić ten dokładny ciąg znaków tutaj.

#### **Ustawienia Konta Klienta**

-   **Grupa Klientów dla Użytkowników Google (glogin_groupid)**
    -   **Co robi to ustawienie:** Określa, do której grupy klientów zostaną automatycznie przypisani nowi użytkownicy rejestrujący się przez Google.
    -   **Skutek zmiany tego ustawienia:**
        -   *Po ustawieniu na „Klient” (domyślnie):* Nowi użytkownicy Google będą standardowymi klientami.
        -   *Po ustawieniu na „Gość” lub inną niestandardową grupę:* Nowi użytkownicy Google zostaną przypisani do tej konkretnej grupy, co może wpłynąć na ich dostęp do zniżek, specjalnych cen lub treści.
    -   **Zalecana wartość:** „Klient” (lub Twoja domyślna grupa klientów).
    -   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby wszyscy nowi użytkownicy rejestrujący się przez Google byli częścią Twojej grupy „Klienci Hurtowi”, aby automatycznie przyznawać im ceny B2B. Wybrałbyś „Klienci Hurtowi” z listy rozwijanej.

-   **Wyślij E-mail Powitalny do Nowych Użytkowników Google (glogin_semail)**
    -   **Co robi to ustawienie:** Kontroluje, czy PrestaShop wysyła standardowy e-mail powitalny do klientów, którzy rejestrują się za pomocą swojego konta Google.
    -   **Skutek zmiany tego ustawienia:**
        -   *Po włączeniu (TAK):* Nowi użytkownicy Google otrzymają standardowy e-mail powitalny PrestaShop, potwierdzający utworzenie ich konta.
        -   *Po wyłączeniu (NIE):* Nowi użytkownicy Google nie otrzymają e-maila powitalnego.
    -   **Zalecana wartość:** TAK (aby potwierdzić utworzenie konta i zapewnić dobre pierwsze wrażenie).
    -   **Scenariusz/przykład dla sprzedawcy:** Chcesz mieć pewność, że nowi klienci czują się mile widziani i mają potwierdzone dane swojego konta, więc włączasz tę opcję.

#### **Opcje Wyświetlania**

-   **Styl Przycisku Logowania Google (glogin_button_style)**
    -   **Co robi to ustawienie:** Pozwala wybrać styl wizualny przycisku „Zaloguj się przez Google”. Opcje zazwyczaj obejmują różne rozmiary, kształty lub schematy kolorów dostarczane przez Google.
    -   **Skutek zmiany tego ustawienia:** Zmienia wygląd wszystkich przycisków logowania Google w Twoim sklepie.
    -   **Zalecana wartość:** Wybierz styl, który najlepiej pasuje do projektu Twojego sklepu.
    -   **Scenariusz/przykład dla sprzedawcy:** Twój motyw używa dużych, zaokrąglonych przycisków. Wybrałbyś styl przycisku, który pasuje do tej estetyki, aby zachować spójność.

-   **Wyświetl Przycisk Logowania Google w Wyskakującym Oknie (ggl_popuplogin)**
    -   **Co robi to ustawienie:** Jeśli włączone, gdy klient kliknie link do logowania, pojawi się wyskakujące okno z opcją logowania Google, zamiast przekierowywać go na pełną stronę logowania.
    -   **Skutek zmiany tego ustawienia:**
        -   *Po włączeniu (TAK):* Zapewnia szybsze, mniej uciążliwe doświadczenie logowania za pośrednictwem modalnego wyskakującego okna.
        -   *Po wyłączeniu (NIE):* Klienci zostaną przekierowani na standardową stronę logowania.
    -   **Zalecana wartość:** TAK (dla nowoczesnego, płynnego doświadczenia użytkownika).
    -   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby klienci pozostawali na bieżącej stronie tak długo, jak to możliwe, więc włączasz logowanie w wyskakującym oknie.

#### **Umiejscowienie Przycisku (Wybór Hooka)**

Te ustawienia kontrolują, gdzie w Twoim sklepie pojawi się przycisk „Zaloguj się przez Google”. Możesz włączyć lub wyłączyć przycisk dla różnych hooków wyświetlania PrestaShop.

-   **Wyświetl w Nagłówku (ggl_top)**
    -   **Co robi to ustawienie:** Kontroluje widoczność przycisku logowania Google w sekcji nagłówka Twojego sklepu.
    -   **Skutek zmiany tego ustawienia:**
        -   *Włączone:* Przycisk pojawia się w nagłówku (np. obok „Moje konto” lub „Zaloguj się”).
        -   *Wyłączone:* Przycisk jest ukryty z nagłówka.
    -   **Zalecana wartość:** TAK (dla łatwego dostępu z dowolnej strony).

-   **Wyświetl w Pasku Nawigacyjnym (ggl_displayNav, ggl_displayNav1, ggl_displayNav2)**
    -   **Co robią te ustawienia:** Kontrolują widoczność przycisku logowania Google w różnych pozycjach paska nawigacyjnego, w zależności od Twojej wersji PrestaShop i motywu. `displayNav` jest powszechne w starszych motywach, podczas gdy `displayNav1` i `displayNav2` są często używane w PrestaShop 1.7+ dla nawigacji na górze strony.
    -   **Skutek zmiany tego ustawienia:**
        -   *Włączone:* Przycisk pojawia się w wybranym pasku nawigacyjnym.
        -   *Wyłączone:* Przycisk jest ukryty z tego paska nawigacyjnego.
    -   **Zalecana wartość:** Włącz jeden lub dwa, które najlepiej pasują do Twojego motywu, unikając redundancji.

-   **Wyświetl w Koszyku (ggl_shoppingCart, ggl_shoppingCartExtra)**
    -   **Co robią te ustawienia:** Kontrolują widoczność przycisku logowania Google na stronie koszyka. `ggl_shoppingCart` jest zazwyczaj dla głównej zawartości koszyka, podczas gdy `ggl_shoppingCartExtra` może być dla dodatkowych bloków lub podsumowań.
    -   **Skutek zmiany tego ustawienia:**
        -   *Włączone:* Przycisk pojawia się na stronie koszyka, umożliwiając szybkie logowanie przed realizacją zamówienia.
        -   *Wyłączone:* Przycisk jest ukryty ze strony koszyka.
    -   **Zalecana wartość:** TAK (aby zachęcić do szybkiego logowania i zmniejszyć porzucanie koszyków).

-   **Wyświetl w Lewej Kolumnie (ggl_leftcolumn)**
    -   **Co robi to ustawienie:** Kontroluje widoczność przycisku logowania Google w lewym pasku bocznym Twojego sklepu.
    -   **Skutek zmiany tego ustawienia:**
        -   *Włączone:* Przycisk pojawia się w lewej kolumnie.
        -   *Wyłączone:* Przycisk jest ukryty z lewej kolumny.
    -   **Zalecana wartość:** TAK (jeśli Twój motyw używa lewej kolumny i chcesz widocznego umiejscowienia).

-   **Wyświetl w Prawej Kolumnie (ggl_rightoclumn)**
    -   **Co robi to ustawienie:** Kontroluje widoczność przycisku logowania Google w prawym pasku bocznym Twojego sklepu.
    -   **Skutek zmiany tego ustawienia:**
        -   *Włączone:* Przycisk pojawia się w prawej kolumnie.
        -   *Wyłączone:* Przycisk jest ukryty z prawej kolumny.
    -   **Zalecana wartość:** TAK (jeśli Twój motyw używa prawej kolumny i chcesz widocznego umiejscowienia).

-   **Wyświetl na Stronie Głównej (ggl_home)**
    -   **Co robi to ustawienie:** Kontroluje widoczność przycisku logowania Google na stronie głównej Twojego sklepu.
    -   **Skutek zmiany tego ustawienia:**
        -   *Włączone:* Przycisk pojawia się na stronie głównej.
        -   *Wyłączone:* Przycisk jest ukryty ze strony głównej.
    -   **Zalecana wartość:** TAK (dla maksymalnej widoczności i szybkiego dostępu dla nowych odwiedzających).

-   **Wyświetl Po Formularzu Logowania Klienta (ggl_displayCustomerLoginFormAfter)**
    -   **Co robi to ustawienie:** Kontroluje widoczność przycisku logowania Google bezpośrednio po standardowym formularzu logowania klienta PrestaShop (np. na stronie `/moje-konto`).
    -   **Skutek zmiany tego ustawienia:**
        -   *Włączone:* Przycisk pojawia się poniżej tradycyjnego formularza logowania.
        -   *Wyłączone:* Przycisk jest ukryty z tej pozycji.
    -   **Zalecana wartość:** TAK (jest to podstawowa lokalizacja dla przycisków logowania społecznościowego).

-   **Wyświetl na Formularzu Tworzenia Konta (ggl_createAccountForm, ggl_createAccountTop)**
    -   **Co robią te ustawienia:** Kontrolują widoczność przycisku logowania Google na stronie tworzenia konta klienta. `ggl_createAccountForm` zazwyczaj umieszcza go w formularzu lub w jego pobliżu, podczas gdy `ggl_createAccountTop` umieszcza go na samej górze strony tworzenia konta.
    -   **Skutek zmiany tego ustawienia:**
        -   *Włączone:* Przycisk pojawia się na stronie tworzenia konta, oferując szybką alternatywę rejestracji.
        -   *Wyłączone:* Przycisk jest ukryty z tej strony.
    -   **Zalecana wartość:** TAK (aby uprościć rejestrację nowych klientów).

-   **Wyświetl w Górnej Kolumnie (ggl_topColumn)**
    -   **Co robi to ustawienie:** Kontroluje widoczność przycisku logowania Google w hooku `displayTopColumn`, często używanym do banerów lub treści tuż pod nagłówkiem.
    -   **Skutek zmiany tego ustawienia:**
        -   *Włączone:* Przycisk pojawia się w górnej kolumnie.
        -   *Wyłączone:* Przycisk jest ukryty z górnej kolumny.
    -   **Zalecana wartość:** Rozważ na podstawie układu Twojego motywu; często mniej krytyczne niż inne pozycje.

-   **Wyświetl Informacje Osobiste na Górze (ggl_displayPersonalInformationTop)**
    -   **Co robi to ustawienie:** Kontroluje widoczność przycisku logowania Google na stronie „Moje dane osobowe”, zazwyczaj gdy klient jest już zalogowany. Może to być mniej powszechne dla przycisku logowania, ale może być używane do łączenia kont.
    -   **Skutek zmiany tego ustawienia:**
        -   *Włączone:* Przycisk pojawia się na stronie danych osobowych.
        -   *Wyłączone:* Przycisk jest ukryty z tej strony.
    -   **Zalecana wartość:** NIE (zazwyczaj nie jest to główny punkt logowania).

#### **Inne Ustawienia (Wewnętrzne/Starsze)**

-   **mypresta_updates, update_, update_**: Są to wewnętrzne ustawienia używane przez MyPresta.eu do sprawdzania aktualizacji modułów i zarządzania wersjami. Nie należy ich modyfikować.
-   **PS_CUSTOMER_GROUP, PS_CUSTOMER_CREATION_EMAIL, PS_CART_FOLLOWING**: Są to standardowe zmienne konfiguracyjne PrestaShop, do których moduł może się odwoływać, ale zazwyczaj nie pozwala na bezpośrednią modyfikację za pośrednictwem swojego interfejsu. Odzwierciedlają one podstawowe ustawienia Twojego sklepu.
-   **glogin_identity**: Jest to prawdopodobnie wewnętrzny identyfikator używany przez moduł. Nie modyfikuj.
-   **ggl_**: Wszelkie inne ustawienia zaczynające się od `ggl_`, które nie są wyraźnie wymienione powyżej, są prawdopodobnie wewnętrznymi flagami lub starszymi opcjami. Najlepiej pozostawić je w ich domyślnych wartościach, chyba że wsparcie zaleci inaczej.

### 2.2 Tabela Szybkiego Odniesienia do Konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i Wpływ |
|---|---|---|---|
| Konfiguracja Modułu | Identyfikator Klienta Google | Twój Identyfikator Klienta Google | Niezbędny do działania funkcji logowania Google. |
| Konfiguracja Modułu | Grupa Klientów dla Użytkowników Google | Klient | Przypisuje nowych użytkowników Google do określonej grupy klientów. |
| Konfiguracja Modułu | Wyślij E-mail Powitalny do Nowych Użytkowników Google | TAK | Wysyła e-mail powitalny do nowych użytkowników rejestrujących się przez Google. |
| Konfiguracja Modułu | Styl Przycisku Logowania Google | (Wybierz najlepiej pasujący) | Zmienia wygląd wizualny przycisku. |
| Konfiguracja Modułu | Wyświetl Przycisk Logowania Google w Wyskakującym Oknie | TAK | Włącza logowanie w wyskakującym oknie dla płynniejszego UX. |
| Konfiguracja Modułu | Wyświetl w Nagłówku (ggl_top) | TAK | Pokazuje przycisk w nagłówku sklepu. |
| Konfiguracja Modułu | Wyświetl w Pasku Nawigacyjnym (ggl_displayNav, ggl_displayNav1, ggl_displayNav2) | TAK (w razie potrzeby) | Pokazuje przycisk w różnych paskach nawigacyjnych. |
| Konfiguracja Modułu | Wyświetl w Koszyku (ggl_shoppingCart, ggl_shoppingCartExtra) | TAK | Pokazuje przycisk na stronie koszyka. |
| Konfiguracja Modułu | Wyświetl w Lewej Kolumnie (ggl_leftcolumn) | TAK (jeśli dotyczy) | Pokazuje przycisk w lewym pasku bocznym. |
| Konfiguracja Modułu | Wyświetl w Prawej Kolumnie (ggl_rightoclumn) | TAK (jeśli dotyczy) | Pokazuje przycisk w prawym pasku bocznym. |
| Konfiguracja Modułu | Wyświetl na Stronie Głównej (ggl_home) | TAK | Pokazuje przycisk na stronie głównej sklepu. |
| Konfiguracja Modułu | Wyświetl Po Formularzu Logowania Klienta (ggl_displayCustomerLoginFormAfter) | TAK | Pokazuje przycisk poniżej standardowego formularza logowania. |
| Konfiguracja Modułu | Wyświetl na Formularzu Tworzenia Konta (ggl_createAccountForm, ggl_createAccountTop) | TAK | Pokazuje przycisk na stronie tworzenia konta. |
| Konfiguracja Modułu | Wyświetl w Górnej Kolumnie (ggl_topColumn) | NIE (lub w razie potrzeby) | Pokazuje przycisk w hooku górnej kolumny. |
| Konfiguracja Modułu | Wyświetl Informacje Osobiste na Górze (ggl_displayPersonalInformationTop) | NIE | Pokazuje przycisk na stronie danych osobowych (mniej powszechne). |

## 3. Rozwiązywanie Problemów dla Sprzedawcy i Często Zadawane Pytania (FAQ)

**P: Przycisk logowania Google pojawia się, ale nic się nie dzieje po kliknięciu lub otrzymuję błąd.**
O: Jest to prawie zawsze problem z Twoim Identyfikatorem Klienta Google lub Autoryzowanymi Identyfikatorami URI Przekierowania w Google Cloud Console.
    *   **Sprawdź Identyfikator Klienta:** Dokładnie sprawdź, czy `Identyfikator Klienta Google` wprowadzony w konfiguracji modułu jest dokładnie tym, co dostarczyło Google, bez dodatkowych spacji.
    *   **Sprawdź Autoryzowane Identyfikatory URI Przekierowania:** W Google Cloud Console upewnij się, że dodałeś `https://www.twojsklep.com/module/glogin/index` (zastąp `twojsklep.com` swoją rzeczywistą domeną) do listy „Autoryzowane identyfikatory URI przekierowania”. Musi to być dokładne dopasowanie, w tym `https://`, jeśli Twój sklep używa SSL.
    *   **Sprawdź Autoryzowane źródła JavaScript:** Upewnij się również, że główny adres URL Twojego sklepu (np. `https://www.twojsklep.com`) jest wymieniony w sekcji „Autoryzowane źródła JavaScript”.

**P: Nowi klienci rejestrują się przez Google, ale nie otrzymują e-maila powitalnego.**
O: Sprawdź ustawienie „Wyślij E-mail Powitalny do Nowych Użytkowników Google” w konfiguracji modułu. Upewnij się, że jest ustawione na „TAK”. Sprawdź również, czy ogólne ustawienia e-mail Twojego sklepu PrestaShop są poprawnie skonfigurowane i czy inne e-maile transakcyjne (takie jak potwierdzenia zamówień) są wysyłane pomyślnie.

**P: Przycisk logowania Google nie pojawia się w określonej lokalizacji (np. w nagłówku), mimo że go włączyłem.**
O:
    *   **Wyczyść Pamięć Podręczną:** Najpierw wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**).
    *   **Pozycja Modułu:** Przejdź do **Wygląd > Pozycje** (lub **Moduły > Pozycje** w starszych wersjach). Wyszukaj moduł `glogin`. Upewnij się, że jest on podpięty do `displayHeader`, `displayNav` lub innych odpowiednich hooków, które włączyłeś. Czasami motywy mogą nadpisywać domyślne zachowania hooków.
    *   **Konflikty z Motywem:** Twój motyw może mieć niestandardowe szablony, które nie wywołują wszystkich standardowych hooków PrestaShop. Jeśli przycisk nie pojawia się po wyczyszczeniu pamięci podręcznej i sprawdzeniu pozycji modułu, może być konieczne, aby webmaster sprawdził pliki `.tpl` Twojego motywu.

**P: Czy klienci mogą połączyć istniejące konto PrestaShop ze swoim kontem Google?**
O: Ten moduł przede wszystkim ułatwia nowe rejestracje i logowania. Jeśli klient loguje się za pomocą Google, a konto z tym adresem e-mail już istnieje w Twoim sklepie PrestaShop, moduł zazwyczaj zaloguje go na jego istniejące konto. Zazwyczaj nie oferuje oddzielnej funkcji „połącz istniejące konto” po zalogowaniu, ale inteligentnie dopasowuje po adresie e-mail.

**P: Chcę zmienić tekst lub wygląd przycisku poza opcjami modułu.**
O: Moduł zapewnia standardowe style przycisków Google. W przypadku zaawansowanej personalizacji (np. zmiany tekstu, dodawania niestandardowych ikon) potrzebne byłyby niestandardowe modyfikacje CSS i potencjalnie JavaScript, które powinien obsłużyć programista stron internetowych.

## 4. Przewodnik dla Programistów i Webmasterów (Architektura Techniczna i Mapa Kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem Google Login Connect.

### 4.1 Przegląd Architektury
Moduł `Google Login Connect` przestrzega standardowej architektury modułów PrestaShop, głównie wykorzystując kontrolery front-office do obsługi wywołań zwrotnych OAuth 2.0 i różne hooki wyświetlania do wstrzykiwania przycisków. Opiera się na klasie `Configuration` PrestaShop do przechowywania ustawień i `ObjectModel` `Customer` do zarządzania użytkownikami. Moduł integruje się z Google JavaScript API do uwierzytelniania po stronie klienta, które następnie wysyła token do kontrolera front-office modułu w celu weryfikacji po stronie serwera i utworzenia sesji użytkownika.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:
    *   `glogin/controllers/front/index.php`
        *   **Nazwa klasy i klasa nadrzędna**: `GloginIndexModuleFrontController` rozszerza `ModuleFrontController`
        *   **Odpowiedzialność**: Jest to główny punkt końcowy wywołania zwrotnego dla przepływu OAuth 2.0 Google. Po uwierzytelnieniu użytkownika w Google, Google przekierowuje do tego kontrolera. Odbiera on token ID Google, weryfikuje go, wyodrębnia informacje o użytkowniku (e-mail, imię i nazwisko), a następnie loguje istniejącego klienta PrestaShop lub tworzy nowego. Obsługuje zarządzanie sesjami i przekierowuje użytkownika z powrotem do sklepu.
    *   `glogin/controllers/front/loginloader.php`
        *   **Nazwa klasy i klasa nadrzędna**: `GloginLoginloaderModuleFrontController` rozszerza `ModuleFrontController`
        *   **Odpowiedzialność**: Ten kontroler prawdopodobnie dostarcza mały fragment JavaScriptu lub inicjalizuje klienta Google API na stronach, gdzie wyświetlany jest przycisk logowania. Może być używany do dynamicznego ładowania biblioteki Google Platform (`platform.js`) lub do dostarczania zmiennych konfiguracyjnych (takich jak `ggl_appid`) do front-endowego JavaScriptu.

-   **Kontrolery Administracyjne Back-Office**:
    *   Brak. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównego modułu.

### 4.3 Główne Klasy i Modele (`classes/`)
-   W katalogu `classes/` nie są zdefiniowane żadne niestandardowe klasy `ObjectModel`. Moduł bezpośrednio współdziała z podstawową klasą `Customer` `ObjectModel` i `Configuration` PrestaShop.
-   Główny plik modułu `glogin/glogin.php` działa jako główna klasa, rozszerzając `Module` i zawierając całą logikę instalacji, deinstalacji i konfiguracji.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `glogin/views/js/glogin.js`
    *   **Zakres**: Front-office.
    *   **Odpowiedzialność**: Ten skrypt jest odpowiedzialny za inicjalizację biblioteki klienta Google Sign-In. Prawdopodobnie zawiera:
        *   Ładowanie biblioteki Google Platform (`https://apis.google.com/js/platform.js`).
        *   Renderowanie przycisku „Zaloguj się przez Google” za pomocą `gapi.signin2.render()`.
        *   Obsługę funkcji wywołania zwrotnego `onSignIn`, która jest wyzwalana po pomyślnym zalogowaniu przez Google. To wywołanie zwrotne wyodrębnia token ID i wysyła go za pośrednictwem AJAX do kontrolera front-office modułu (`index.php`) w celu przetwarzania po stronie serwera.
        *   Potencjalnie zarządza funkcjonalnością logowania w wyskakującym oknie (`ggl_popuplogin`), dynamicznie wyświetlając przycisk Google w oknie modalnym.
        *   Słuchacze zdarzeń dla kliknięć na przyciskach logowania Google.

### 4.5 Arkusze Stylów CSS (`views/css/`)

-   `glogin/css.css`
    *   **Zakres**: Front-office.
    *   **Odpowiedzialność**: Ogólne style dla przycisków logowania Google i potencjalnie wszelkich niestandardowych kontenerów lub wyskakujących okien wprowadzonych przez moduł. Może zawierać podstawowe dostosowania układu.
-   `glogin/views/css/glogin.css`
    *   **Zakres**: Front-office.
    *   **Odpowiedzialność**: Podobnie jak `css.css`, prawdopodobnie zawiera podstawowe style dla przycisków logowania Google, zapewniając ich prawidłowe wyrównanie i rozmiar w różnych motywach PrestaShop.
-   `glogin/views/css/glogin17-new.css`
    *   **Zakres**: Front-office.
    *   **Odpowiedzialność**: Specyficzne reguły CSS dostosowane do motywów PrestaShop 1.7+, uwzględniające potencjalne różnice w układzie lub nadpisywanie stylów wymagane dla nowszych wersji. Może to obejmować dostosowania Flexbox lub Grid.
-   `glogin/views/css/glogin17.css`
    *   **Zakres**: Front-office.
    *   **Odpowiedzialność**: Kolejny arkusz stylów specjalnie dla PrestaShop 1.7.x, potencjalnie zawierający dodatkowe lub alternatywne style w porównaniu do `glogin17-new.css`, w zależności od dokładnej struktury motywu.

### 4.6 Struktura Szablonów Smarty (`views/templates/`)

Moduł wykorzystuje liczne szablony do wstrzykiwania przycisku logowania Google do różnych hooków PrestaShop. Większość tych szablonów będzie zawierać wywołanie logiki renderowania przycisku Google Sign-In (np. `<div class="g-signin2" data-onsuccess="onSignIn"></div>`) i potencjalnie otaczający kod HTML do stylizacji.

-   **Szablony hooków (`views/templates/hook/`)**:
    *   `glogin/views/templates/createAccountForm.tpl`: Renderuje przycisk Google w formularzu tworzenia konta klienta.
    *   `glogin/views/templates/createAccountTop.tpl`: Renderuje przycisk Google na górze strony tworzenia konta.
    *   `glogin/views/templates/dashboardZoneOne.tpl`: Renderuje przycisk Google w hooku `dashboardZoneOne` (mniej powszechne dla logowania, prawdopodobnie dla integracji z panelem administracyjnym lub konkretnego motywu).
    *   `glogin/views/templates/displayCustomerLoginFormAfter.tpl`: Renderuje przycisk Google bezpośrednio po standardowym formularzu logowania klienta.
    *   `glogin/views/templates/displayNav.tpl`: Renderuje przycisk Google w hooku `displayNav` (często górna nawigacja).
    *   `glogin/views/templates/displayNav1.tpl`: Renderuje przycisk Google w hooku `displayNav1` (nawigacja PrestaShop 1.7+).
    *   `glogin/views/templates/displayNav2.tpl`: Renderuje przycisk Google w hooku `displayNav2` (nawigacja PrestaShop 1.7+).
    *   `glogin/views/templates/displayPopUpLogin.tpl`: Zawiera strukturę HTML dla modalnego okna logowania w wyskakującym oknie, w tym przycisk Google.
    *   `glogin/views/templates/footer.tpl`: Renderuje przycisk Google w hooku `displayFooter`.
    *   `glogin/views/templates/glogin.tpl`: Ogólny szablon, prawdopodobnie używany jako rezerwowy lub do wewnętrznej logiki renderowania.
    *   `glogin/views/templates/header.tpl`: Renderuje przycisk Google w hooku `displayHeader`.
    *   `glogin/views/templates/home.tpl`: Renderuje przycisk Google w hooku `displayHome`.
    *   `glogin/views/templates/leftcolumn.tpl`: Renderuje przycisk Google w hooku `displayLeftColumn`.
    *   `glogin/views/templates/rightcolumn.tpl`: Renderuje przycisk Google w hooku `displayRightColumn`.
    *   `glogin/views/templates/shoppingCart.tpl`: Renderuje przycisk Google w hooku `displayShoppingCart`.
    *   `glogin/views/templates/shoppingCartExtra.tpl`: Renderuje przycisk Google w hooku `displayShoppingCartExtra`.
    *   `glogin/views/templates/top.tpl`: Renderuje przycisk Google w hooku `displayTop`.
    *   `glogin/views/templates/topColumn.tpl`: Renderuje przycisk Google w hooku `displayTopColumn`.

### 4.7 Schemat Bazy Danych i Mapa Hooków

-   **Tabele Bazy Danych**:
    *   Moduł nie tworzy żadnych niestandardowych tabel SQL.
    *   Ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `GLOGIN_GROUPID`, `GLOGIN_SEMAIL`, `GGL_APPID`, `GGL_POPUP_LOGIN`, `GGL_BUTTON_STYLE` oraz różnych flag `GGL_DISPLAY[NAZWA_HOOKA]`.

-   **Tabela Zarejestrowanych Hooków**:

| Nazwa Hooka | Czas Wykonania | Cel Techniczny |
|---|---|---|
| `displayHeader` | W sekcji `<head>` lub na samym początku `<body>` | Wstrzykiwanie CSS, JS i potencjalnie przycisku Google w nagłówku. |
| `displayFooter` | Na końcu `<body>` | Wstrzykiwanie przycisku Google w stopce. |
| `displayHome` | W obszarze treści strony głównej | Wstrzykiwanie przycisku Google na stronie głównej. |
| `displayShoppingCart` | Na stronie koszyka | Wstrzykiwanie przycisku Google na stronie koszyka. |
| `displayRightColumn` | W prawym pasku bocznym | Wstrzykiwanie przycisku Google w prawej kolumnie. |
| `displayCustomerLoginFormAfter` | Po standardowym formularzu logowania klienta | Wstrzykiwanie przycisku Google dla alternatywnego logowania. |
| `displayNav` | W głównym pasku nawigacyjnym (starsze motywy) | Wstrzykiwanie przycisku Google w nawigacji. |
| `displayCreateAccountTop` | Na górze strony tworzenia konta | Wstrzykiwanie przycisku Google dla szybkiej rejestracji. |
| `displayTop` | W górnej sekcji strony (często nad nagłówkiem) | Wstrzykiwanie przycisku Google w samej górnej sekcji. |
| `displayNav2` | W drugim pasku nawigacyjnym (PS 1.7+) | Wstrzykiwanie przycisku Google w nawigacji. |
| `displayShoppingCartExtra` | Dodatkowy obszar treści na stronie koszyka | Wstrzykiwanie przycisku Google na stronie koszyka. |
| `displayTopColumn` | W obszarze treści poniżej nagłówka (często dla banerów) | Wstrzykiwanie przycisku Google w górnej kolumnie. |
| `displayNav1` | W głównym pasku nawigacyjnym (PS 1.7+) | Wstrzykiwanie przycisku Google w nawigacji. |
| `dashboardZoneOne` | W pierwszej strefie panelu administracyjnego | Potencjalnie dla informacji po stronie administratora lub konkretnego przycisku. |
| `displayLeftColumn` | W lewym pasku bocznym | Wstrzykiwanie przycisku Google w lewej kolumnie. |

## 5. Oficjalne Wsparcie i Aktualizacje
Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Upewnij się, że używasz najnowszej kompatybilnej wersji modułu dla swojego sklepu PrestaShop.
