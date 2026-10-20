---
title: "Amazon connect (rejestracja + logowanie) - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów dla modułu PrestaShop Amazon connect (rejestracja + logowanie) od MyPresta.eu."
sidebar:
  label: "Amazon connect (rejestracja + logowanie) - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Amazon connect (register + login) na MyPresta.eu](https://mypresta.eu/modules/social-networks/amazon-connect-register-login.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/amazon-connect-register-login/)
>
> ---


# Amazon connect (rejestracja + logowanie)

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do bezpiecznej komunikacji API.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu logowania Amazon, gdzie połączysz swój sklep PrestaShop z kontem deweloperskim Amazon.

-   **aml\_ClientID (ID klienta Amazon)**
    -   **Co robi to ustawienie:** Jest to unikalny identyfikator dostarczany przez Amazon, gdy rejestrujesz swoją aplikację (Twój sklep PrestaShop) w ich usłudze Login with Amazon. Informuje Amazon, która aplikacja żąda uwierzytelnienia użytkownika.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po poprawnym wprowadzeniu:* Twój przycisk „Zaloguj się z Amazon” będzie działał poprawnie, umożliwiając klientom uwierzytelnienie za pośrednictwem ich konta Amazon.
        -   *Po niepoprawnym wprowadzeniu lub pozostawieniu pustego:* Przycisk „Zaloguj się z Amazon” nie będzie działał, lub klienci napotkają błąd podczas próby jego użycia.
    -   **Zalecana wartość:** ID klienta uzyskane z konsoli deweloperskiej Amazon. To pole nie może być puste, aby moduł działał.
    -   **Scenariusz / przykład dla sprzedawcy:** Zarejestrowałeś swój sklep PrestaShop jako aplikację w konsoli deweloperskiej Amazon. Amazon dostarcza Ci „ID klienta” (np. `amzn1.oauth-client.xxxxxxxxxxxxxxxxxxxxxxxxxxxx`). Musisz skopiować i wkleić ten dokładny identyfikator do tego pola.
-   **aml\_ClientSecret (Tajny klucz klienta Amazon)**
    -   **Co robi to ustawienie:** Jest to poufny klucz, również dostarczany przez Amazon, używany w połączeniu z ID klienta do bezpiecznego uwierzytelniania Twojej aplikacji na serwerach Amazon. Zapewnia, że tylko Twoja legalna aplikacja może żądać danych użytkownika.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po poprawnym wprowadzeniu:* Twój moduł może bezpiecznie komunikować się z API Amazon w celu weryfikacji tożsamości użytkowników.
        -   *Po niepoprawnym wprowadzeniu lub pozostawieniu pustego:* Proces uwierzytelniania zakończy się niepowodzeniem, ponieważ Twój sklep nie może bezpiecznie zidentyfikować się w Amazon.
    -   **Zalecana wartość:** Tajny klucz klienta uzyskany z konsoli deweloperskiej Amazon. To pole nie może być puste, aby moduł działał.
    -   **Scenariusz / przykład dla sprzedawcy:** Oprócz ID klienta, Amazon dostarcza również „Tajny klucz klienta” (np. `yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy`). Ten klucz musi być utrzymywany w tajemnicy i wprowadzony tutaj dokładnie.
-   **aml\_RedirectURI (URI przekierowania Amazon)**
    -   **Co robi to ustawienie:** Jest to adres URL w Twoim sklepie PrestaShop, na który Amazon przekieruje przeglądarkę użytkownika *po* pomyślnym zalogowaniu się lub autoryzacji Twojej aplikacji na stronie Amazon. Jest to kluczowe dla bezpiecznego przebiegu procesu uwierzytelniania.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po poprawnym skonfigurowaniu po obu stronach (moduł i konsola deweloperska Amazon):* Użytkownicy są płynnie przekierowywani z powrotem do Twojego sklepu po zalogowaniu się w Amazon.
        -   *Po niepoprawnym wprowadzeniu:* Użytkownicy napotkają błąd po zalogowaniu się w Amazon, lub nie zostaną poprawnie przekierowani z powrotem do Twojego sklepu. Ten URI musi być również zarejestrowany w ustawieniach konsoli deweloperskiej Amazon dla Twojej aplikacji.
    -   **Zalecana wartość:** Powinien być zazwyczaj automatycznie generowany przez moduł lub być konkretnym adresem URL, takim jak `https://twojasklep.com/module/amlogin/ajax_amlogin` (zweryfikuj dokładną ścieżkę dostarczoną przez moduł lub dokumentację Amazon). Upewnij się, że odpowiada URI, który zarejestrowałeś w konsoli deweloperskiej Amazon.
    -   **Scenariusz / przykład dla sprzedawcy:** Podczas konfigurowania aplikacji w konsoli deweloperskiej Amazon zostaniesz poproszony o „Dozwolone adresy URL zwrotne”. Musisz wprowadzić dokładny adres URL, którego ten moduł używa do przekierowania (np. `https://www.twojasklep.com/module/amlogin/ajax_amlogin`).
-   **Wyświetl przycisk logowania Amazon w nagłówku**
    -   **Co robi to ustawienie:** Kontroluje, czy przycisk „Zaloguj się z Amazon” pojawia się w sekcji nagłówka Twojego sklepu.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po włączeniu:* Przycisk będzie widoczny w nagłówku, oferując natychmiastowy dostęp do logowania Amazon.
        -   *Po wyłączeniu:* Przycisk nie pojawi się w nagłówku.
    -   **Zalecana wartość:** TAK, dla maksymalnej widoczności i łatwości dostępu.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby klienci widzieli opcję logowania Amazon, gdy tylko wejdą na Twoją stronę, więc włączasz to.
-   **Wyświetl przycisk logowania Amazon w lewej kolumnie**
    -   **Co robi to ustawienie:** Kontroluje, czy przycisk „Zaloguj się z Amazon” pojawia się w lewej kolumnie bocznej Twojego sklepu.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po włączeniu:* Przycisk będzie widoczny w lewej kolumnie, często obok innych bloków nawigacyjnych lub konta.
        -   *Po wyłączeniu:* Przycisk nie pojawi się w lewej kolumnie.
    -   **Zalecana wartość:** TAK, jeśli Twój motyw używa lewej kolumny i chcesz stałej widoczności.
    -   **Scenariusz / przykład dla sprzedawcy:** Twój sklep ma widoczną lewą kolumnę i chcesz oferować opcję logowania Amazon, gdy klienci przeglądają kategorie.
-   **Wyświetl przycisk logowania Amazon w prawej kolumnie**
    -   **Co robi to ustawienie:** Kontroluje, czy przycisk „Zaloguj się z Amazon” pojawia się w prawej kolumnie bocznej Twojego sklepu.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po włączeniu:* Przycisk będzie widoczny w prawej kolumnie.
        -   *Po wyłączeniu:* Przycisk nie pojawi się w prawej kolumnie.
    -   **Zalecana wartość:** TAK, jeśli Twój motyw używa prawej kolumny i chcesz stałej widoczności.
    -   **Scenariusz / przykład dla sprzedawcy:** Podobnie jak w przypadku lewej kolumny, jeśli Twój motyw używa prawej kolumny, możesz umieścić tam przycisk dla widoczności.
-   **Wyświetl przycisk logowania Amazon na stronie produktu**
    -   **Co robi to ustawienie:** Kontroluje, czy przycisk „Zaloguj się z Amazon” pojawia się na poszczególnych stronach szczegółów produktu.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po włączeniu:* Przycisk zostanie wyświetlony na stronach produktów, potencjalnie w pobliżu przycisku „Dodaj do koszyka” lub opisu produktu.
        -   *Po wyłączeniu:* Przycisk nie pojawi się na stronach produktów.
    -   **Zalecana wartość:** TAK, ponieważ może zachęcić do natychmiastowego logowania lub rejestracji przed dodaniem do koszyka.
    -   **Scenariusz / przykład dla sprzedawcy:** Klient przegląda produkt i decyduje się go kupić. Widząc przycisk logowania Amazon, może szybko zalogować się lub utworzyć konto przed przejściem do kasy.
-   **Wyświetl przycisk logowania Amazon w stopce**
    -   **Co robi to ustawienie:** Kontroluje, czy przycisk „Zaloguj się z Amazon” pojawia się w sekcji stopki Twojego sklepu.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Po włączeniu:* Przycisk będzie widoczny w stopce, zapewniając alternatywny punkt logowania.
        -   *Po wyłączeniu:* Przycisk nie pojawi się w stopce.
    -   **Zalecana wartość:** NIE, chyba że masz konkretny powód projektowy. Inne lokalizacje oferują lepszą widoczność.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz oferować opcję logowania Amazon, ale wolisz, aby nie była zbyt widoczna, więc umieszczasz ją w stopce.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | `aml_ClientID` | Twój ID klienta Amazon | Unikalny identyfikator Twojej aplikacji w Amazon. **Wymagane do działania.** |
| Strona konfiguracji modułu | `aml_ClientSecret` | Twój tajny klucz klienta Amazon | Poufny klucz do bezpiecznego uwierzytelniania w Amazon. **Wymagane do działania.** |
| Strona konfiguracji modułu | `aml_RedirectURI` | Automatycznie generowany / Konkretny URL | URL, na który Amazon przekierowuje użytkowników po zalogowaniu. **Musi odpowiadać konsoli deweloperskiej Amazon.** |
| Strona konfiguracji modułu | Wyświetl w nagłówku | TAK | Pokazuje przycisk w nagłówku sklepu. |
| Strona konfiguracji modułu | Wyświetl w lewej kolumnie | TAK | Pokazuje przycisk w lewej kolumnie bocznej. |
| Strona konfiguracji modułu | Wyświetl w prawej kolumnie | TAK | Pokazuje przycisk w prawej kolumnie bocznej. |
| Strona konfiguracji modułu | Wyświetl na stronie produktu | TAK | Pokazuje przycisk na poszczególnych stronach produktów. |
| Strona konfiguracji modułu | Wyświetl w stopce | NIE | Pokazuje przycisk w stopce sklepu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Przycisk logowania Amazon pojawia się, ale nic się nie dzieje po kliknięciu lub otrzymuję błąd.**
O: Zazwyczaj wskazuje to na problem z `aml_ClientID`, `aml_ClientSecret` lub `aml_RedirectURI`.
-   **Sprawdź 1:** Dokładnie sprawdź, czy skopiowałeś ID klienta i tajny klucz klienta dokładnie z konsoli deweloperskiej Amazon do konfiguracji modułu. Nawet pojedynczy błąd w znaku spowoduje awarię.
-   **Sprawdź 2:** Zweryfikuj, czy `aml_RedirectURI` w konfiguracji modułu dokładnie odpowiada jednemu z „Dozwolonych adresów URL zwrotnych”, które zarejestrowałeś w konsoli deweloperskiej Amazon dla swojej aplikacji. Zwróć uwagę na `http` vs `https` i ukośniki końcowe.
-   **Sprawdź 3:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) i pamięć podręczną przeglądarki.

**P: Moi klienci są przekierowywani do Amazon, ale potem otrzymują błąd lub nie są odsyłani z powrotem do mojego sklepu.**
O: Jest to prawie na pewno niezgodność `aml_RedirectURI`. Przejdź do konsoli deweloperskiej Amazon, znajdź swoją aplikację i upewnij się, że lista „Dozwolonych adresów URL zwrotnych” zawiera *dokładny* adres URL, którego używa Twój moduł PrestaShop. Musi to być dokładne dopasowanie, w tym `http/https` i wszelkie podkatalogi.

**P: Przycisk logowania Amazon nie pojawia się w miejscach, które włączyłem.**
O:
-   **Sprawdź 1:** Upewnij się, że moduł jest włączony i poprawnie skonfigurowany w Panelu administracyjnym.
-   **Sprawdź 2:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną). Czasami zmiany w szablonach nie odzwierciedlają się natychmiast.
-   **Sprawdź 3:** Twój motyw może nadpisywać standardowe hooki PrestaShop. Jeśli przycisk nadal się nie pojawia, może być konieczne, aby programista internetowy ręcznie wstawił wywołanie hooka modułu do plików `.tpl` Twojego motywu (patrz sekcja 7.6 dla odpowiednich szablonów).

**P: Czy ten moduł działa ze sklepami wielojęzycznymi?**
O: Tak, moduł powinien dziedziczyć możliwości wielojęzyczne PrestaShop dla każdego wyświetlanego tekstu. Sam proces logowania Amazon jest obsługiwany przez Amazon i zazwyczaj dostosowuje się do ustawień językowych konta Amazon użytkownika.

**P: Czy mogę dostosować wygląd przycisku logowania Amazon?**
O: Moduł używa standardowych zasobów przycisku logowania Amazon. Chociaż nie możesz zmienić podstawowego projektu przycisku Amazon (zgodnie z wytycznymi marki Amazon), możesz użyć niestandardowego CSS (patrz sekcja 7.5), aby dostosować jego położenie, marginesy lub kontener wokół niego, aby lepiej pasował do Twojego motywu.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Amazon connect (rejestracja + logowanie)” integruje usługę Login with Amazon (LWA) firmy Amazon z PrestaShop. Działa głównie jako standardowy moduł PrestaShop, wykorzystując hooki do wyświetlania przycisku logowania w różnych miejscach front-office. Podstawowa logika obsługi przepływu Amazon OAuth 2.0 (przekierowanie do Amazon, odbieranie kodu autoryzacji, wymiana go na token dostępu i pobieranie danych profilu użytkownika) jest hermetyzowana w głównym pliku modułu i jego powiązanym kontrolerze AJAX. Dane użytkownika otrzymane od Amazon są następnie wykorzystywane do zalogowania istniejącego klienta PrestaShop lub utworzenia nowego.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie używa dedykowanych kontrolerów front-office ani administracyjnych w katalogu `controllers/`. Wszystkie żądania AJAX front-office i główna konfiguracja modułu są obsługiwane przez główny plik modułu (`amlogin/ajax_amlogin.php`), który działa jako pseudo-kontroler dla akcji AJAX.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie zawiera żadnych niestandardowych klas ani modeli w dedykowanym katalogu `classes/`. Podstawowa logika znajduje się w głównym pliku modułu `amlogin/ajax_amlogin.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `amlogin/js/amlogin.js`
    -   **Zakres:** Front-office.
    -   **Opis:** Ten skrypt jest odpowiedzialny za inicjalizację SDK logowania Amazon, obsługę zdarzeń kliknięcia przycisku logowania Amazon i zarządzanie przepływem OAuth 2.0. Prawdopodobnie używa metody `amazon.Login.authorize` do inicjowania procesu logowania i obsługuje wywołanie zwrotne z Amazon. Następnie wykona wywołanie AJAX do backendu modułu w celu przetworzenia danych użytkownika Amazon i zalogowania klienta do PrestaShop. Może również aktualizować interfejs użytkownika (np. pokazywać stan zalogowania) po pomyślnym uwierzytelnieniu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `amlogin/css.css`
    -   **Zakres:** Front-office.
    -   **Opis:** Ogólne style dla przycisku logowania Amazon i wszelkich powiązanych elementów interfejsu użytkownika. Może zawierać podstawowe dostosowania układu, wypełnienia lub marginesów.
-   `amlogin/css/amlogin.css`
    -   **Zakres:** Front-office.
    -   **Opis:** Specyficzne style dla przycisku logowania Amazon, potencjalnie obejmujące responsywne dostosowania lub nadpisania specyficzne dla motywu dla PrestaShop 1.6.
-   `amlogin/css/amlogin17.css`
    -   **Zakres:** Front-office.
    -   **Opis:** Specyficzne style dostosowane do motywów PrestaShop 1.7, uwzględniające potencjalne różnice w domyślnych strukturach motywów lub frameworkach CSS (np. Bootstrap 4 vs. Bootstrap 3). Deweloperzy mogą nadpisać te style w pliku `custom.css` swojego motywu lub tworząc motyw potomny.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł wykorzystuje kompleksowy zestaw szablonów Smarty do renderowania przycisku logowania Amazon w różnych hookach PrestaShop.

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `amlogin/ajax-amlogin.tpl`: Prawdopodobnie używany do odpowiedzi AJAX lub dynamicznej zawartości związanej z procesem logowania Amazon.
    -   `amlogin/amlogin.tpl`: Ogólny szablon dla przycisku logowania Amazon, często dołączany przez inne szablony hooków.
    -   `amlogin/createAccountForm.tpl`: Renderuje przycisk logowania Amazon w standardowym formularzu tworzenia konta PrestaShop.
    -   `amlogin/createAccountTop.tpl`: Renderuje przycisk logowania Amazon na górze strony tworzenia konta.
    -   `amlogin/dashboardZoneOne.tpl`: Renderuje przycisk logowania Amazon w pierwszej strefie panelu klienta (np. `displayCustomerAccount`).
    -   `amlogin/displayCustomerLoginFormAfter.tpl`: Renderuje przycisk logowania Amazon po standardowym formularzu logowania klienta.
    -   `amlogin/displayNav.tpl`: Renderuje przycisk logowania Amazon w pasku nawigacyjnym (np. hook `displayNav`).
    -   `amlogin/displayPopUpLogin.tpl`: Renderuje przycisk logowania Amazon w modalnym oknie logowania pop-up (jeśli zaimplementowane przez motyw lub moduł).
    -   `amlogin/footer.tpl`: Renderuje przycisk logowania Amazon w stopce sklepu (hook `displayFooter`).
    -   `amlogin/header.tpl`: Renderuje przycisk logowania Amazon w nagłówku sklepu (hook `displayHeader`).
    -   `amlogin/home.tpl`: Renderuje przycisk logowania Amazon na stronie głównej (hook `displayHome`).
    -   `amlogin/leftcolumn.tpl`: Renderuje przycisk logowania Amazon w lewej kolumnie bocznej (hook `displayLeftColumn`).
    -   `amlogin/rightcolumn.tpl`: Renderuje przycisk logowania Amazon w prawej kolumnie bocznej (hook `displayRightColumn`).
    -   `amlogin/shoppingCart.tpl`: Renderuje przycisk logowania Amazon w podsumowaniu koszyka.
    -   `amlogin/shoppingCartExtra.tpl`: Renderuje przycisk logowania Amazon w dodatkowej sekcji koszyka.
    -   `amlogin/top.tpl`: Renderuje przycisk logowania Amazon w górnej sekcji strony (np. hook `displayTop`).
    -   `amlogin/topColumn.tpl`: Renderuje przycisk logowania Amazon w obszarze górnej kolumny (hook `displayTopColumn`).

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Ten moduł nie wydaje się tworzyć niestandardowych tabel SQL. Ustawienia konfiguracji (ID klienta, tajny klucz klienta itp.) są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `AML_CLIENT_ID`, `AML_CLIENT_SECRET`, `AML_REDIRECT_URI` i `AML_DISPLAY_HEADER` itp.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` strony. | Wstrzykuje CSS, JS i potencjalnie przycisk logowania Amazon. |
| `displayNav` | W górnym pasku nawigacyjnym. | Wyświetla przycisk logowania Amazon w nawigacji. |
| `displayLeftColumn` | W lewej kolumnie bocznej. | Wyświetla przycisk logowania Amazon w lewej kolumnie. |
| `displayRightColumn` | W prawej kolumnie bocznej. | Wyświetla przycisk logowania Amazon w prawej kolumnie. |
| `displayProductButtons` (lub podobny) | Na stronie produktu, w pobliżu przycisków akcji. | Wyświetla przycisk logowania Amazon na stronach produktów. |
| `displayFooter` | W stopce sklepu. | Wyświetla przycisk logowania Amazon w stopce. |
| `displayCustomerAccount` | Na panelu konta klienta. | Wyświetla przycisk logowania Amazon w obszarze konta klienta. |
| `displayCustomerLoginFormAfter` | Po standardowym formularzu logowania. | Integruje przycisk logowania Amazon ze stroną logowania. |
| `displayBeforeBodyClosingTag` | Przed tagiem `</body>`. | Może wstrzykiwać JavaScript dla SDK Amazon lub wyskakujących okien. |
| `displayShoppingCart` | Na stronie podsumowania koszyka. | Wyświetla przycisk logowania Amazon w koszyku. |
| `displayShoppingCartExtra` | Dodatkowy obszar zawartości w koszyku. | Wyświetla przycisk logowania Amazon w dodatkowym obszarze koszyka. |
| `displayTop` | Na górze strony, powyżej nagłówka. | Wyświetla przycisk logowania Amazon w samej górnej sekcji. |
| `displayTopColumn` | W głównym obszarze górnej kolumny. | Wyświetla przycisk logowania Amazon w górnej kolumnie. |
| `displayHome` | Na stronie głównej sklepu. | Wyświetla przycisk logowania Amazon na stronie głównej. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Amazon connect (rejestracja + logowanie)”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół dokłada wszelkich starań, aby Twój moduł działał idealnie i bezproblemowo integrował się z Twoim sklepem PrestaShop.
