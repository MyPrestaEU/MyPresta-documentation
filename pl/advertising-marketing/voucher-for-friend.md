---
title: "Voucher for friend - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Voucher for friend od MyPresta.eu."
sidebar:
  label: "Voucher for friend - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Voucher for friend na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-for-friend.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/voucher-for-friend/)
>
> ---


# Voucher for friend

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla sklepu PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Voucher for friend)

Jest to główny ekran konfiguracji modułu „Voucher for friend”. Tutaj zdefiniujesz, jak działa funkcja udostępniania voucherów i gdzie pojawia się w Twoim sklepie.

#### **Ustawienia i opcje**

-   **Wyświetl link „Voucher for friend” w bloku moje konto (fvc\_b\_position)**

    -   **Co robi to ustawienie:** Kontroluje, czy link do strony „Voucher for friend” pojawia się w bloku „Moje konto” klienta, który zazwyczaj znajduje się w nagłówku lub kolumnie po zalogowaniu się klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Link, zazwyczaj oznaczony jako „Moje vouchery” lub „Voucher dla przyjaciela”, będzie widoczny w bloku konta klienta, zapewniając szybki dostęp do funkcji udostępniania.
        -   *Gdy wyłączone (Nie):* Link nie pojawi się w bloku konta klienta. Klienci musieliby przejść do pełnej strony „Moje konto”, aby znaleźć link, lub skorzystać z innej opcji umieszczenia.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby zalogowani klienci bardzo łatwo znajdowali tę funkcję, włącz ją. Jest to widoczne miejsce dla aktywnych użytkowników.
-   **Wyświetl link „Voucher for friend” na stronie moje konto (fvc\_b\_position2)**

    -   **Co robi to ustawienie:** Określa, czy link do strony „Voucher for friend” jest wyświetlany na głównej stronie „Moje konto”, która zawiera wszystkie opcje specyficzne dla klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Dedykowany link pojawi się na stronie „Moje konto”, zazwyczaj jako ikona lub link tekstowy obok innych opcji, takich jak „Historia zamówień” lub „Moje adresy”.
        -   *Gdy wyłączone (Nie):* Link nie będzie obecny na stronie „Moje konto”.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Jest to standardowe i oczekiwane miejsce, w którym klienci mogą znaleźć taką funkcję. Włączenie jej zapewnia wykrywalność dla wszystkich zalogowanych użytkowników.
-   **Wyświetl link „Voucher for friend” w lewej/prawej kolumnie (fvc\_b\_position3)**

    -   **Co robi to ustawienie:** Kontroluje, czy blok promocyjny lub link do „Voucher for friend” pojawia się w lewej lub prawej kolumnie Twojego sklepu. Może być widoczny zarówno dla zalogowanych, jak i niezalogowanych odwiedzających.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Blok lub link zostanie wyrenderowany w określonej kolumnie, zachęcając odwiedzających do korzystania z funkcji udostępniania voucherów lub dowiedzenia się o niej.
        -   *Gdy wyłączone (Nie):* Taki blok nie pojawi się w kolumnach.
    -   **Zalecana wartość:** TAK (jeśli chcesz szeroko promować tę funkcję)
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz aktywnie promować program poleceń wszystkim odwiedzającym, w tym tym, którzy jeszcze się nie zalogowali, włączenie tej opcji zwiększy widoczność. Możesz umieścić ją w prawej kolumnie na stronach produktów, aby zachęcić do udostępniania.
-   **Liczba voucherów do wygenerowania (FV\_NBC)**

    -   **Co robi to ustawienie:** Definiuje, ile unikalnych kodów voucherów może wygenerować i wysłać do znajomych jeden klient.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ustawione na 1:* Każdy klient może wysłać tylko jeden voucher do jednego znajomego.
        -   *Ustawione na 5:* Każdy klient może wysłać do pięciu voucherów do pięciu różnych znajomych.
        -   *Ustawione na 0 (lub bardzo wysoką liczbę):* Pozwala na nieograniczone generowanie voucherów na klienta.
    -   **Zalecana wartość:** 3-5 (aby zachęcić do udostępniania bez przeciążania systemu lub tworzenia zbyt wielu rabatów)
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz ograniczyć liczbę poleceń, które może wykonać jeden klient, aby zapobiec nadużyciom lub zarządzać budżetem rabatowym, ustaw konkretną liczbę, np. 3. Jeśli chcesz maksymalnego rozprzestrzeniania się wirusowego, ustaw wyższą liczbę lub 0 dla nieograniczonej.
-   **Zezwól niezalogowanym użytkownikom na wysyłanie voucherów (FV\_UNLOGGED)**

    -   **Co robi to ustawienie:** Określa, czy odwiedzający, którzy nie są zalogowani na konto klienta, mogą nadal uzyskiwać dostęp do formularza „Voucher for friend” i wysyłać voucher.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (Tak):* Niezalogowani użytkownicy zobaczą linki „Voucher for friend” (jeśli włączone w kolumnach/stopce) i będą mogli wypełnić formularz. Prawdopodobnie zostaną poproszeni o podanie własnego adresu e-mail jako osoby polecającej.
        -   *Gdy wyłączone (Nie):* Tylko zalogowani klienci mogą uzyskiwać dostęp do funkcji udostępniania voucherów i korzystać z niej. Niezalogowani użytkownicy klikający link mogą zostać przekierowani na stronę logowania/rejestracji.
    -   **Zalecana wartość:** NIE (aby zapewnić, że tylko faktyczni klienci polecają, i aby zapobiec spamowi/nadużyciom)
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz ściśle kontrolować, kto może polecać i upewnić się, że tylko Twoja istniejąca baza klientów uczestniczy, wyłącz tę opcję. Jeśli chcesz zezwolić każdemu na polecanie, nawet jeśli jeszcze nie kupił, włącz ją (ale pamiętaj o potencjalnym spamie).
-   **E-mail sklepu (PS\_SHOP\_EMAIL)**

    -   **Co robi to ustawienie:** To pole zazwyczaj wyświetla domyślny adres e-mail Twojego sklepu, który jest używany jako adres e-mail „nadawcy” dla powiadomienia o voucherze wysyłanego do znajomych. Zazwyczaj pobiera dane z ogólnych ustawień PrestaShop.
    -   **Efekt zmiany tego ustawienia:** Zmiana tego tutaj może nadpisać ogólnosystemowy adres e-mail sklepu dla wiadomości e-mail specyficznych dla tego modułu.
    -   **Zalecana wartość:** Upewnij się, że jest to prawidłowy, profesjonalny adres e-mail powiązany z Twoim sklepem (np. `info@twojsklep.com`).
    -   **Scenariusz / przykład dla sprzedawcy:** Znajomy otrzymujący voucher zobaczy ten adres e-mail jako nadawcę. Powinien to być adres, który mogą rozpoznać i któremu ufają.
-   **Nazwa sklepu (PS\_SHOP\_NAME)**

    -   **Co robi to ustawienie:** To pole zazwyczaj wyświetla oficjalną nazwę Twojego sklepu, która jest używana w temacie i treści wiadomości e-mail podczas wysyłania vouchera do znajomego. Zazwyczaj pobiera dane z ogólnych ustawień PrestaShop.
    -   **Efekt zmiany tego ustawienia:** Zmiana tego tutaj może nadpisać ogólnosystemową nazwę sklepu dla wiadomości e-mail specyficznych dla tego modułu.
    -   **Zalecana wartość:** Oficjalna nazwa Twojego sklepu (np. „Mój Niesamowity Sklep”).
    -   **Scenariusz / przykład dla sprzedawcy:** Znajomy otrzymujący voucher zobaczy tę nazwę. Powinna być jasna i spójna z Twoją marką.

#### 2.1.1 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyświetl link „Voucher for friend” w bloku moje konto (fvc\_b\_position) | TAK | Pokazuje link w bloku konta klienta (nagłówek/kolumna) dla szybkiego dostępu. |
| Konfiguracja modułu | Wyświetl link „Voucher for friend” na stronie moje konto (fvc\_b\_position2) | TAK | Pokazuje link na głównej stronie „Moje konto”. |
| Konfiguracja modułu | Wyświetl link „Voucher for friend” w lewej/prawej kolumnie (fvc\_b\_position3) | TAK | Pokazuje blok promocyjny/link w bocznych kolumnach dla wszystkich odwiedzających. |
| Konfiguracja modułu | Liczba voucherów do wygenerowania (FV\_NBC) | 3-5 | Ogranicza liczbę voucherów, które może wysłać jeden klient. |
| Konfiguracja modułu | Zezwól niezalogowanym użytkownikom na wysyłanie voucherów (FV\_UNLOGGED) | NIE | Ogranicza wysyłanie voucherów tylko do zalogowanych klientów. |
| Konfiguracja modułu | E-mail sklepu (PS\_SHOP\_EMAIL) | E-mail Twojego sklepu | Adres e-mail nadawcy dla powiadomień o voucherach. |
| Konfiguracja modułu | Nazwa sklepu (PS\_SHOP\_NAME) | Nazwa Twojego sklepu | Nazwa sklepu używana w wiadomościach e-mail z powiadomieniami o voucherach. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci nie mogą znaleźć linku „Voucher for friend”.**
O1: Przejdź do **Moduły > Menedżer modułów > Konfiguruj** dla „Voucher for friend”. Upewnij się, że `fvc_b_position`, `fvc_b_position2` i `fvc_b_position3` są ustawione na „Tak” dla pożądanych miejsc (blok Moje konto, strona Moje konto, lewa/prawa kolumna). Sprawdź również przypisania hooków w swoim szablonie w **Wygląd > Pozycje**, aby upewnić się, że moduł jest podpięty do `displayMyAccountBlock`, `displayCustomerAccount`, `displayLeftColumn` lub `displayRightColumn` zgodnie z oczekiwaniami.

**P2: Znajomi nie otrzymują e-maili z voucherami.**
O2:
1.  **Sprawdź foldery spamowe:** Doradź swoim klientom, aby poprosili swoich znajomych o sprawdzenie folderów spamowych lub śmieci.
2.  **Konfiguracja e-maila sklepu:** Sprawdź, czy ustawienie `PS_SHOP_EMAIL` w konfiguracji modułu jest prawidłowym i aktywnym adresem e-mail.
3.  **Ustawienia e-maila PrestaShop:** Przejdź do **Zaawansowane > E-mail** w panelu administracyjnym PrestaShop. Wyślij testowy e-mail, aby upewnić się, że system e-mailowy Twojego sklepu działa poprawnie. Jeśli nie, możesz mieć problem z konfiguracją serwera SMTP.
4.  **Logi serwera:** Twój webmaster może sprawdzić logi poczty serwera pod kątem błędów związanych z wychodzącymi wiadomościami e-mail.

**P3: Kod vouchera nie działa dla znajomego.**
O3:
1.  **Sprawdź datę ważności/warunki:** Upewnij się, że voucher nie wygasł i że koszyk znajomego spełnia wszelkie wymagania dotyczące minimalnego zakupu lub ograniczenia produktów, które mogą być ustawione dla wygenerowanego vouchera (są one zazwyczaj definiowane w natywnej sekcji „Reguły koszyka” PrestaShop, którą ten moduł wykorzystuje).
2.  **Prawidłowe wprowadzenie kodu:** Potwierdź, że znajomy wprowadza kod dokładnie tak, jak się pojawia (z uwzględnieniem wielkości liter, bez dodatkowych spacji).
3.  **Jednorazowe użycie:** Większość voucherów polecających jest jednorazowego użytku. Jeśli znajomy wcześniej próbował go użyć, może już nie być ważny.

**P4: Moduł nie wygląda prawidłowo w moim niestandardowym szablonie.**
O4: Niestandardowe szablony często mają unikalne style, które czasami mogą kolidować z projektami modułów.
1.  **Wyczyść pamięć podręczną:** Najpierw spróbuj wyczyścić pamięć podręczną PrestaShop w **Zaawansowane > Wydajność**.
2.  **Nadpisywanie szablonu:** Twój webmaster może potrzebować utworzyć nadpisywania CSS w arkuszu stylów Twojego szablonu, aby dostosować wygląd modułu. Moduł używa `views/css/ps16.css` do swojego stylu, co może być punktem wyjścia do dostosowań.
3.  **Wyświetlanie mobilne:** Upewnij się, że Twój szablon jest w pełni responsywny. Jeśli problemy utrzymują się na urządzeniach mobilnych, prawdopodobnie jest to konflikt CSS wymagający interwencji programisty.

**P5: Czy mogę zmienić kwotę rabatu lub typ vouchera?**
O5: Sam moduł generuje standardową regułę koszyka PrestaShop. Zazwyczaj konfigurujesz szczegóły wygenerowanego vouchera (np. rabat procentowy, stała kwota, minimalny zakup, konkretne produkty) w natywnej sekcji PrestaShop **Katalog > Rabaty > Reguły koszyka**. Moduł tworzy *mechanizm* udostępniania, ale *szczegóły* rabatu są zarządzane przez podstawowy system rabatowy PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowe informacje na temat struktury technicznej modułu „Voucher for friend”, przeznaczone dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł „Voucher for friend” jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie `ModuleFrontController` do interakcji z front-office oraz główną klasę modułu do konfiguracji i zarządzania hookami. Integruje się z natywnym systemem `CartRule` PrestaShop w celu generowania i zarządzania voucherami rabatowymi. Logika modułu jest zawarta w jego głównym pliku PHP i dedykowanych kontrolerach front-office, a szablony Smarty obsługują prezentację.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery obsługują logikę skierowaną do klienta w celu generowania i zarządzania voucherami.

-   **`controllers/front/index.php`**

    -   **Nazwa klasy:** `FriendvoucherIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Ten kontroler jest prawdopodobnie odpowiedzialny za wyświetlanie początkowego formularza „Voucher for friend”, w którym klient wprowadza dane swojego znajomego. Obsługuje przesyłanie tego formularza, waliduje dane wejściowe, generuje `CartRule` (voucher) i wysyła powiadomienie e-mail do znajomego. Zarządza również logiką ograniczania liczby voucherów, które klient może wysłać.
    -   **Trasy:** Odpowiada na adres URL, taki jak `twojsklep.com/module/friendvoucher/index`.
-   **`controllers/front/myvoucher.php`**

    -   **Nazwa klasy:** `FriendvoucherMyvoucherModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Ten kontroler jest odpowiedzialny za wyświetlanie osobistej strony „Moje vouchery” klienta, zazwyczaj dostępnej z sekcji „Moje konto”. Wyświetla listę voucherów, które klient już wysłał, i potencjalnie zapewnia opcje przeglądania ich statusu lub wysyłania nowych.
    -   **Trasy:** Odpowiada na adres URL, taki jak `twojsklep.com/module/friendvoucher/myvoucher`.

#### Kontrolery administracyjne Back-Office

Ten moduł nie wydaje się mieć dedykowanych niestandardowych kontrolerów administracyjnych. Cała konfiguracja back-office jest obsługiwana za pomocą metody `getContent()` głównej klasy modułu.

### 4.3 Podstawowe klasy i modele (`classes/`)

Na podstawie dostarczonego spisu, ten moduł nie definiuje niestandardowych klas ani `ObjectModel` w katalogu `classes/`. Prawdopodobnie używa podstawowej klasy `CartRule` PrestaShop do zarządzania voucherami i `Customer` do danych użytkownika.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`lib/voucherengine/script.js`**
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Ten skrypt prawdopodobnie obsługuje interakcje po stronie klienta w formularzu „Voucher for friend”. Może to obejmować:
        -   Walidację formularza (np. sprawdzanie poprawności formatów e-mail, wymaganych pól).
        -   Przesyłanie AJAX żądania vouchera do kontrolera front-office `index.php`.
        -   Wyświetlanie komunikatów o sukcesie lub błędach użytkownikowi bez pełnego przeładowania strony.
        -   Potencjalnie dynamiczne aktualizacje formularza na podstawie danych wprowadzonych przez użytkownika.
        -   Wszelkie interaktywne elementy związane z procesem generowania vouchera.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`lib/voucherengine/ps16.css`**
    -   **Zakres:** Stylizacja klienta front-office.
    -   **Szczegóły:** Ten arkusz stylów zapewnia wizualną stylizację formularzy, linków i bloków wyświetlania „Voucher for friend” w front-office. Prawdopodobnie zawiera style dla:
        -   Elementów formularza udostępniania vouchera (pola wejściowe, przyciski).
        -   Listy „Moje vouchery” na stronie konta klienta.
        -   Bloków promocyjnych w lewej/prawej kolumnie.
        -   Podstawowego układu i typografii w celu zapewnienia czytelności.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Programiści powinni sprawdzić wyrenderowany kod HTML, aby zidentyfikować konkretne nazwy klas (np. `.friendvoucher-form`, `.voucher-list`, `.friendvoucher-block`) do celów integracji i dostosowania szablonu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

Moduł nie wymienia jawnie szablonów w podkatalogu `hook/`, ale szablony wymienione poniżej są zazwyczaj renderowane za pomocą hooków.

-   **`views/templates/front/footer.tpl`**

    -   **Hook:** `displayFooter`
    -   **Wyjścia:** Link lub blok związany z „Voucher for friend” w stopce sklepu.
-   **`views/templates/front/leftcolumn.tpl`**

    -   **Hook:** `displayLeftColumn`
    -   **Wyjścia:** Blok promocyjny lub link do „Voucher for friend” w lewym pasku bocznym sklepu.
-   **`views/templates/front/rightcolumn.tpl`**

    -   **Hook:** `displayRightColumn`
    -   **Wyjścia:** Blok promocyjny lub link do „Voucher for friend” w prawym pasku bocznym sklepu.

#### Szablony administracyjne (`views/templates/admin/`)

Ten moduł nie wydaje się mieć niestandardowych szablonów administracyjnych. Konfiguracja jest prawdopodobnie renderowana bezpośrednio przez metodę `getContent()` za pomocą formularzy pomocniczych PrestaShop.

#### Szablony Front-office (`views/templates/front/`)

Te szablony są renderowane przez kontrolery front-office modułu.

-   **`views/templates/front/my-account.tpl`**

    -   **Hook:** `displayCustomerAccount` (lub `displayMyAccountBlock`)
    -   **Wyjścia:** Link lub ikona na głównej stronie „Moje konto” klienta, kierująca go do kontrolera `myvoucher.php`.
-   **`views/templates/front/my-voucher.tpl`**

    -   **Kontroler:** `FriendvoucherMyvoucherModuleFrontController`
    -   **Wyjścia:** Dedykowana strona wyświetlająca listę voucherów wysłanych przez klienta, ich status oraz potencjalnie formularz do wysyłania nowych.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Ten moduł nie wydaje się tworzyć niestandardowych tabel SQL. Prawdopodobnie przechowuje swoją konfigurację w `ps_configuration` i wykorzystuje podstawowe tabele PrestaShop `ps_cart_rule` i `ps_cart_rule_lang` dla wygenerowanych voucherów.

#### Tabela zarejestrowanych hooków

Moduł rejestruje się w różnych hookach, aby wyświetlać swoją zawartość i funkcjonalność.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displaymyAccountBlock` | Renderuje się w bloku konta klienta (nagłówek/kolumna) po zalogowaniu. | Wyświetla szybki link do strony voucherów dla zalogowanych użytkowników. |
| `displayrightColumn` | Renderuje zawartość w prawym pasku bocznym. | Wyświetla blok promocyjny/link do funkcji vouchera. |
| `displayLeftColumn` | Renderuje zawartość w lewym pasku bocznym. | Wyświetla blok promocyjny/link do funkcji vouchera. |
| `displayFooter` | Renderuje zawartość w stopce sklepu. | Wyświetla link do strony voucherów w stopce. |
| `displaycustomerAccount` | Renderuje zawartość na głównej stronie „Moje konto” klienta. | Wyświetla dedykowany link/ikonę do funkcji vouchera na stronie konta. |
| `actionValidateOrder` | Wykonywane po pomyślnym zatwierdzeniu zamówienia. | (Potencjalnie) Może być używane do wyzwalania działań związanych z nagrodami dla polecających lub śledzenia udanych poleceń, chociaż nie jest to wyraźnie potwierdzone przez spis plików. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnego wsparcia, aktualizacji modułu i wszelkiej dalszej pomocy, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Możesz uzyskać dostęp do zakupionych modułów, pobrać najnowsze wersje i przesyłać zgłoszenia do pomocy technicznej bezpośrednio ze swojego konta.
"""
