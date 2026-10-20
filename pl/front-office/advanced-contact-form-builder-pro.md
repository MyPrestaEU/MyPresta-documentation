---
title: "Advanced Contact Form Builder Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Advanced Contact Form Builder Pro od MyPresta.eu."
sidebar:
  label: "Advanced Contact Form Builder Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Advanced Contact Form Builder Pro na MyPresta.eu](https://mypresta.eu/modules/front-office-features/advanced-contact-form-builder-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/advanced-contact-form-builder-pro/)
>
> ---


# Advanced Contact Form Builder Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x (do 12.x zgodnie z definicją modułu)
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop oraz dla funkcji takich jak webhooki czy reCAPTCHA.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran, na którym ustawiasz ogólne zachowanie i domyślne opcje dla swoich formularzy kontaktowych.

-   **Profil wsparcia szablonu**

    *   **Co robi to ustawienie:** To ustawienie pomaga modułowi dostosować jego wizualny wygląd, aby lepiej pasował do motywu Twojego sklepu. Różne motywy PrestaShop mogą mieć nieco inne struktury HTML.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na „Classic” (lub podobne):* Moduł będzie używał szablonów zoptymalizowanych dla domyślnego motywu PrestaShop Classic lub motywów na nim opartych. Zapewnia to dobry wygląd formularzy bez dodatkowego wysiłku stylizacyjnego.
        *   *Gdy ustawione na „Niestandardowy” lub inną nazwę motywu:* Moduł może używać specyficznych szablonów lub reguł stylizacji dostosowanych do tego konkretnego motywu, jeśli są dostępne.
    *   **Zalecana wartość:** Wybierz opcję, która najlepiej pasuje do Twojego aktywnego motywu PrestaShop. Jeśli używasz domyślnego motywu Classic lub motywu z niego pochodzącego, „Classic” jest zazwyczaj najlepszym wyborem. Jeśli Twoje formularze nie wyglądają poprawnie, spróbuj poeksperymentować z tym ustawieniem.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoje formularze wyglądają na niestylizowane lub źle wyrównane po instalacji, przełączenie tego ustawienia z „Classic” na inny dostępny profil (jeśli istnieje) może rozwiązać problem.
-   **Adres e-mail autorespondera**

    *   **Co robi to ustawienie:** Jest to adres e-mail, z którego będą wysyłane automatyczne e-maile potwierdzające do Twoich klientów po przesłaniu formularza.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na prawidłowy adres e-mail:* Klienci otrzymają natychmiastowy e-mail „Dziękujemy za zapytanie” z tego adresu.
        *   *Gdy pozostawione puste:* Do klienta nie zostanie wysłany żaden automatyczny e-mail potwierdzający.
    *   **Zalecana wartość:** Użyj profesjonalnego adresu e-mail powiązanego z Twoim sklepem, np. `info@twojskep.com` lub `noreply@twojskep.com`.
    *   **Scenariusz / przykład dla sprzedawcy:** Ustawienie tego na `support@moj-sklep.com` zapewnia klientom, że ich wiadomość została odebrana i dostarcza im punkt kontaktowy do dalszej korespondencji.
-   **Tytuł e-maila (dla właściciela sklepu)**

    *   **Co robi to ustawienie:** Definiuje temat wiadomości e-mail, którą Ty (właściciel sklepu) otrzymujesz, gdy klient przesyła formularz.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na „Nowe zapytanie z mojego sklepu”:* Twoje e-maile powiadomień będą miały ten temat, co ułatwi ich identyfikację.
    *   **Zalecana wartość:** Coś jasnego i opisowego, np. „Nowe zgłoszenie z formularza kontaktowego - [Nazwa Twojego Sklepu]”.
    *   **Scenariusz / przykład dla sprzedawcy:** Użycie „Nowe zapytanie klienta - MyPresta.eu” pomaga szybko zauważyć ważne wiadomości w skrzynce odbiorczej.
-   **Adres(y) e-mail odbiorcy**

    *   **Co robi to ustawienie:** Tutaj określasz jeden lub więcej adresów e-mail, które będą otrzymywać powiadomienia, gdy klient prześle *dowolny* formularz utworzony przez ten moduł. Możesz oddzielić wiele adresów e-mail przecinkiem.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na `sprzedaz@twojskep.com`:* Wszystkie zgłoszenia z formularzy zostaną wysłane do działu sprzedaży.
        *   *Gdy ustawione na `sprzedaz@twojskep.com, wsparcie@twojskep.com`:* Oba działy otrzymają kopie wszystkich zgłoszeń.
    *   **Zalecana wartość:** Główny(e) adres(y) e-mail dla Twojego działu obsługi klienta lub sprzedaży.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz dedykowany zespół obsługi klienta, wpiszesz tutaj `obslugaklienta@twojskep.com`.
-   **DW dla e-maila powiadomienia sklepu**

    *   **Co robi to ustawienie:** Umożliwia wysłanie „Ukrytej kopii” (DW) e-maila powiadomienia właściciela sklepu na dodatkowe adresy e-mail. Ci odbiorcy nie będą widoczni dla głównego odbiorcy.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na `manager@twojskep.com`:* Menedżer otrzyma ukrytą kopię wszystkich powiadomień o przesłaniu formularza.
    *   **Zalecana wartość:** Użyj tego do wewnętrznego śledzenia, tworzenia kopii zapasowych lub dla menedżerów, którzy muszą monitorować zapytania bez bycia głównym kontaktem. Pozostaw puste, jeśli nie jest potrzebne.
    *   **Scenariusz / przykład dla sprzedawcy:** Twój zespół marketingowy może chcieć wysłać sobie DW, aby śledzić generowanie leadów z formularzy, bez bezpośredniego angażowania się w odpowiedzi klientów.
-   **Tak / Nie (dla różnych ustawień widoczności/wymagalności pól)**

    *   **Co robi to ustawienie:** Są to ogólne przełączniki do włączania lub wyłączania określonych funkcji lub do ustawiania niektórych pól jako obowiązkowych/opcjonalnych w Twoich formularzach.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone (Tak):* Funkcja jest aktywna (np. pole telefonu jest widoczne, załączniki są dozwolone).
        *   *Gdy wyłączone (Nie):* Funkcja jest nieaktywna (np. pole telefonu jest ukryte, załączniki nie są dozwolone).
    *   **Zalecana wartość:** Zależy całkowicie od Twoich potrzeb biznesowych dla każdego konkretnego ustawienia (patrz poszczególne ustawienia poniżej).
-   **Zgodność z RODO**

    *   **Co robi to ustawienie:** Włącza pole wyboru w Twoich formularzach, gdzie klienci muszą wyraźnie zgodzić się na Twoją politykę prywatności przed przesłaniem swoich danych. Jest to kluczowe dla zgodności z RODO.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* W formularzach pojawia się obowiązkowe pole wyboru, zazwyczaj z tekstem typu „Zgadzam się z polityką prywatności”. Formularz nie może zostać przesłany, dopóki to pole nie zostanie zaznaczone.
        *   *Gdy wyłączone:* Nie pojawi się pole wyboru zgody RODO.
    *   **Zalecana wartość:** **TAK**, jeśli Twój sklep działa w regionach podlegających RODO (np. UE) lub jeśli chcesz zapewnić najlepsze praktyki w zakresie prywatności danych.
    *   **Scenariusz / przykład dla sprzedawcy:** Sklep z siedzibą w UE *musi* to włączyć, aby legalnie zbierać dane klientów za pośrednictwem formularzy.
-   **Strona polityki prywatności**

    *   **Co robi to ustawienie:** Jeśli włączona jest zgodność z RODO, to ustawienie umożliwia podlinkowanie do strony CMS z polityką prywatności Twojego sklepu. Pole wyboru zgody RODO zazwyczaj będzie zawierać link do tej strony.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy strona jest wybrana:* Tekst zgody RODO będzie zawierał klikalny link do wybranej strony polityki prywatności.
        *   *Gdy żadna strona nie jest wybrana:* Tekst zgody RODO może pojawić się bez linku lub linkować do domyślnej strony, co nie jest idealne dla zgodności.
    *   **Zalecana wartość:** Wybierz oficjalną stronę CMS z polityką prywatności Twojego sklepu.
    *   **Scenariusz / przykład dla sprzedawcy:** Po włączeniu RODO, wybierzesz stronę CMS zatytułowaną „Polityka prywatności” z listy rozwijanej.
-   **ReCaptcha (v2)**

    *   **Co robi to ustawienie:** Włącza Google reCAPTCHA v2 w Twoich formularzach, aby chronić przed spamem i botami.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* W Twoich formularzach pojawi się pole wyboru reCAPTCHA „Nie jestem robotem”. Użytkownicy muszą ukończyć to wyzwanie przed przesłaniem.
        *   *Gdy wyłączone:* Nie jest aktywna żadna ochrona reCAPTCHA.
    *   **Zalecana wartość:** **TAK**, aby zapobiec spamowi. Będziesz również musiał skonfigurować klucz witryny i klucz tajny poniżej.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli otrzymujesz dużo spamu za pośrednictwem formularzy kontaktowych, włączenie reCAPTCHA jest pierwszym krokiem do walki z nim.
-   **Klucz witryny ReCaptcha**

    *   **Co robi to ustawienie:** Jest to publiczny klucz dostarczony przez Google reCAPTCHA, który umożliwia Twojej witrynie wyświetlanie widżetu reCAPTCHA.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy poprawnie wprowadzony:* Widżet reCAPTCHA pojawi się i będzie działał poprawnie w Twoich formularzach.
        *   *Gdy niepoprawny lub pusty:* reCAPTCHA nie będzie działać, a formularze mogą nie zostać przesłane lub wyświetlać błędy.
    *   **Zalecana wartość:** Klucz witryny uzyskany z Twojego konta Google reCAPTCHA.
    *   **Scenariusz / przykład dla sprzedawcy:** Po utworzeniu pary kluczy reCAPTCHA v2 w konsoli administracyjnej Google reCAPTCHA, skopiujesz tutaj „Klucz witryny”.
-   **Klucz tajny ReCaptcha**

    *   **Co robi to ustawienie:** Jest to prywatny klucz dostarczony przez Google reCAPTCHA, który umożliwia Twojemu serwerowi weryfikację odpowiedzi reCAPTCHA. Powinien być utrzymywany w tajemnicy.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy poprawnie wprowadzony:* Twój serwer może pomyślnie zweryfikować, czy użytkownik przeszedł wyzwanie reCAPTCHA.
        *   *Gdy niepoprawny lub pusty:* Weryfikacja zakończy się niepowodzeniem, a legalni użytkownicy mogą nie być w stanie przesłać formularzy.
    *   **Zalecana wartość:** Klucz tajny uzyskany z Twojego konta Google reCAPTCHA.
    *   **Scenariusz / przykład dla sprzedawcy:** Skopiujesz tutaj „Klucz tajny” z konsoli administracyjnej Google reCAPTCHA.
-   **Adres URL webhooka (Slack/Discord)**

    *   **Co robi to ustawienie:** Umożliwia wysyłanie powiadomień o przesłaniu formularza na określony kanał Slack lub Discord za pośrednictwem webhooka. Zapewnia to natychmiastowe alerty dla zespołu.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy wprowadzony jest prawidłowy adres URL:* Każde przesłanie formularza wywoła powiadomienie na skonfigurowany kanał Slack/Discord.
        *   *Gdy pusty:* Nie zostaną wysłane żadne powiadomienia webhooka.
    *   **Zalecana wartość:** Twój adres URL webhooka Slack lub Discord. Pozostaw puste, jeśli nie używasz tych usług do powiadomień.
    *   **Scenariusz / przykład dla sprzedawcy:** Twój zespół obsługi klienta używa Slacka. Konfigurujesz webhooka w Slacku, wklejasz tutaj adres URL, a teraz każde nowe zapytanie pojawia się bezpośrednio na ich kanale #customer-support.
-   **Niestandardowy CSS (front-office)**

    *   **Co robi to ustawienie:** Udostępnia obszar tekstowy, w którym możesz dodać własny kod CSS, aby stylizować formularze w swoim sklepie. Jest to przydatne do precyzyjnego dostosowywania wyglądu, aby idealnie pasował do Twojej marki.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy wprowadzony jest CSS:* Zdefiniowane tutaj style zostaną zastosowane do Twoich formularzy, nadpisując domyślne style modułu.
    *   **Zalecana wartość:** Używaj tego tylko wtedy, gdy masz specyficzne potrzeby stylizacyjne wykraczające poza domyślny wygląd modułu. W razie wątpliwości skonsultuj się z projektantem stron internetowych.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby przycisk przesyłania formularza miał określony odcień zieleni, który pasuje do Twojego logo. Dodasz tutaj CSS, taki jak `.cfrompro-form button[type="submit"] { background-color: #00FF00; }`.
-   **Minimalna długość pytania (znaki)**

    *   **Co robi to ustawienie:** Ustawia minimalną liczbę znaków wymaganą dla głównego pola „Pytanie” lub „Wiadomość” w Twoich formularzach.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na 10:* Klienci muszą wpisać co najmniej 10 znaków w polu wiadomości, aby przesłać formularz.
        *   *Gdy ustawione na 0 (lub bardzo nisko):* Pozwala na bardzo krótkie wiadomości.
    *   **Zalecana wartość:** 10-20 znaków, aby zachęcić klientów do podania wystarczającej ilości szczegółów.
    *   **Scenariusz / przykład dla sprzedawcy:** Aby uniknąć niejasnych zapytań, takich jak „Cześć”, ustawiasz to na 15, zapewniając, że klienci podadzą bardziej opisową wiadomość.
-   **Maksymalna długość pytania (znaki)**

    *   **Co robi to ustawienie:** Ustawia maksymalną liczbę znaków dozwoloną dla głównego pola „Pytanie” lub „Wiadomość”.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na 500:* Klienci nie mogą wpisać więcej niż 500 znaków w polu wiadomości.
    *   **Zalecana wartość:** 500-1000 znaków, w zależności od tego, jak szczegółowe mają być zapytania. Zbyt niska wartość może frustrować użytkowników, zbyt wysoka może prowadzić do zbyt długich wiadomości.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz zapobiec ekstremalnie długim esejom w formularzu kontaktowym, więc ustawiasz to na 750 znaków.
-   **Zezwalaj na załączniki graficzne**

    *   **Co robi to ustawienie:** Włącza lub wyłącza możliwość przesyłania plików (takich jak obrazy, pliki PDF) przez klientów wraz z przesłanym formularzem.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* W Twoich formularzach pojawi się pole do przesyłania plików.
        *   *Gdy wyłączone:* Nie będzie dostępna opcja przesyłania plików.
    *   **Zalecana wartość:** **TAK**, jeśli klienci często muszą dostarczać zrzuty ekranu, potwierdzenia zamówień lub inne dokumenty. **NIE**, jeśli chcesz, aby formularze były proste.
    *   **Scenariusz / przykład dla sprzedawcy:** W przypadku formularza wsparcia, włączenie załączników pozwala klientom wysyłać zrzuty ekranu problemów, co jest bardzo pomocne.
-   **Maksymalny rozmiar załącznika (MB)**

    *   **Co robi to ustawienie:** Jeśli załączniki są dozwolone, to ustawienie definiuje maksymalny rozmiar pliku (w megabajtach), który klient może przesłać.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na 5:* Klienci mogą przesyłać pliki o rozmiarze do 5 MB. Większe pliki zostaną odrzucone.
    *   **Zalecana wartość:** 2-5 MB jest zazwyczaj wystarczające dla większości dokumentów i obrazów, nie przeciążając serwera.
    *   **Scenariusz / przykład dla sprzedawcy:** Zezwalasz na załączniki, ale chcesz zapobiec przesyłaniu ogromnych plików, więc ustawiasz limit na 3 MB.
-   **Czas trwania komunikatu o sukcesie (ms)**

    *   **Co robi to ustawienie:** Kontroluje, jak długo komunikat „Formularz przesłany pomyślnie” (często powiadomienie typu „toast”) pozostaje widoczny dla klienta po przesłaniu formularza. Mierzone w milisekundach (1000 ms = 1 sekunda).
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na 3000:* Komunikat o sukcesie zniknie po 3 sekundach.
        *   *Gdy ustawione na 0:* Komunikat może pozostać na stałe lub zniknąć natychmiast (w zależności od motywu/przeglądarki).
    *   **Zalecana wartość:** 3000-5000 ms (3-5 sekund) to dobry kompromis, dający klientom wystarczająco dużo czasu na przeczytanie go, nie będąc inwazyjnym.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby klienci wyraźnie widzieli potwierdzenie, więc ustawiasz to na 4000 ms.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł dodaje nowe elementy menu pod **„Advanced Contact Form Pro”** w Twoim Panelu administracyjnym PrestaShop.

#### 2.2.1 Zarządzanie formularzami (Panel administracyjny > Advanced Contact Form Pro > Formularze)

Ten ekran umożliwia tworzenie, edytowanie i zarządzanie wszystkimi niestandardowymi formularzami kontaktowymi.

-   **Nazwa ekranu i lokalizacja w menu:** **Advanced Contact Form Pro > Formularze**
-   **Dostępne akcje i ustawienia:**
    *   **Widok listy (siatka):** Wyświetla tabelę wszystkich utworzonych formularzy, pokazując ich nazwę, ID i status.
    *   **Dodaj nowy formularz:** Kliknij przycisk „Dodaj nowy formularz”, aby utworzyć zupełnie nowy niestandardowy formularz.
    *   **Edytuj formularz:** Kliknij ikonę „Edytuj” obok formularza na liście, aby zmodyfikować jego ustawienia.
    *   **Usuń formularz:** Kliknij ikonę „Usuń”, aby usunąć formularz.
    *   **Pola konfiguracji formularza (podczas dodawania/edycji):**
        *   **Nazwa formularza:** Jasna wewnętrzna nazwa dla Twojego formularza (np. „Zapytanie hurtowe”, „Wsparcie produktu”).
        *   **Shortcode:** Unikalny kod (np. `[cfrompro id="1"]`), którego użyjesz do osadzenia tego konkretnego formularza na stronach CMS lub w opisach produktów.
        *   **Status formularza:** Włącz/Wyłącz formularz. Wyłączone formularze nie będą widoczne w sklepie.
        *   **Adres(y) e-mail odbiorcy DLA TEGO Formularza:** Możesz nadpisać globalne adresy e-mail odbiorców dla tego konkretnego formularza. Jest to bardzo potężne narzędzie do routingu zapytań.
        *   **Adres e-mail autorespondera DLA TEGO Formularza:** Nadpisz globalny adres e-mail autorespondera dla tego formularza.
        *   **Tytuł e-maila (dla właściciela sklepu) DLA TEGO Formularza:** Nadpisz globalny temat e-maila dla powiadomień z tego formularza.
        *   **Pola niestandardowe:** Tutaj definiujesz unikalne pola dla *tego* formularza. Możesz dodać pola tekstowe, obszary tekstowe, listy rozwijane, pola wyboru, przyciski radiowe, przesyłanie plików i wiele innych. Dla każdego pola niestandardowego możesz ustawić:
            *   **Etykieta:** Co widzi klient (np. „Nazwa Twojej Firmy”).
            *   **Typ:** (Tekst, Obszar tekstowy, Wybór, Pole wyboru, Radio, Plik itp.).
            *   **Wymagane:** Czy to pole jest obowiązkowe?
            *   **Placeholder:** Tekst podpowiedzi w polu wprowadzania.
            *   **Opcje (dla Wyboru, Pola wyboru, Radio):** Zdefiniuj wybory, które klienci mogą wybrać.
            *   **Reguły walidacji:** (np. format e-maila, tylko liczby).
        *   **Ustawienia pływającego wyzwalacza:**
            *   **Włącz pływający wyzwalacz:** Pokaż pływający przycisk w sklepie, który otwiera ten formularz.
            *   **Tekst wyzwalacza:** Jaki tekst pojawia się na pływającym przycisku (np. „Skontaktuj się z nami”).
            *   **Pozycja wyzwalacza:** Gdzie pojawia się przycisk (np. lewo, prawo, dół-lewo).
            *   **Ikona wyzwalacza:** Wybierz ikonę dla przycisku.
            *   **Opóźnienie wyzwalacza (ms):** Jak długo czekać, zanim pojawi się pływający przycisk (np. 2000 ms = 2 sekundy).
            *   **Kolor wyzwalacza, Kolor tekstu, Kolor po najechaniu:** Dostosuj wygląd przycisku.
-   **Wpływ zmian:**
    *   Dodanie/edycja formularza sprawia, że jest on dostępny do osadzenia lub jako pływający wyzwalacz.
    *   Zmiany w polach niestandardowych bezpośrednio wpływają na to, co klienci widzą i wypełniają w tym konkretnym formularzu.
    *   Zmiany w adresach e-mail odbiorców kierują zgłoszenia do różnych działów.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Zdecyduj, jaki rodzaj zapytania chcesz obsłużyć (np. „Wniosek hurtowy”).
    2.  Przejdź do **Formularze** i kliknij „Dodaj nowy formularz”.
    3.  Nadaj mu jasną nazwę.
    4.  Dodaj wszystkie potrzebne niestandardowe pola (np. Nazwa firmy, NIP, Typ działalności, Oczekiwana wielkość zamówienia).
    5.  Ustaw konkretny adres e-mail odbiorcy, jeśli ten formularz ma trafić do konkretnego zespołu (np. `hurt@twojskep.com`).
    6.  Zapisz formularz. Zapisz jego shortcode.
    7.  Osadź shortcode na odpowiedniej stronie CMS (np. „Informacje hurtowe”).

#### 2.2.2 Zarządzanie pytaniami (Panel administracyjny > Advanced Contact Form Pro > Pytania)

Ten ekran służy jako Twoja skrzynka odbiorcza dla wszystkich zgłoszeń z formularzy.

-   **Nazwa ekranu i lokalizacja w menu:** **Advanced Contact Form Pro > Pytania**
-   **Dostępne akcje i ustawienia:**
    *   **Widok listy (siatka):** Wyświetla tabelę wszystkich przesłanych pytań/zapytań.
        *   **Kolumny:** Pokazuje informacje takie jak Nazwa formularza, Imię klienta, E-mail, Temat (jeśli dotyczy), Data przesłania i Status.
    *   **Wyświetl pytanie:** Kliknij ikonę „Wyświetl” (lupa) obok zapytania, aby zobaczyć jego pełne szczegóły.
        *   **Widok szczegółów:** Pokazuje wszystkie informacje przesłane przez klienta, w tym odpowiedzi na pola niestandardowe, załączniki (z linkami do pobrania) oraz formularz, z którego pochodzi.
        *   **Sekcja odpowiedzi:** Umożliwia bezpośrednią odpowiedź klientowi z poziomu Panelu administracyjnego PrestaShop. Ta odpowiedź zostanie wysłana z domyślnego adresu e-mail kontaktowego Twojego sklepu.
        *   **Zmień status:** Możesz zaktualizować status zapytania (np. „Nowe”, „W toku”, „Rozwiązane”).
    *   **Usuń pytanie:** Usuń zapytanie z listy.
-   **Wpływ zmian:**
    *   Wyświetlanie pytania pozwala efektywnie przetwarzać zapytania klientów.
    *   Odpowiadanie stąd utrzymuje zapis komunikacji (chociaż moduł nie przechowuje pełnej historii odpowiedzi w sobie, wysyła standardowy e-mail).
    *   Zmiana statusu pomaga śledzić postęp każdego zapytania.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Regularnie sprawdzaj sekcję „Pytania”.
    2.  Dla każdego nowego zapytania kliknij „Wyświetl”, aby przeczytać szczegóły.
    3.  Jeśli potrzebna jest odpowiedź, użyj funkcji „Odpowiedz”.
    4.  Zaktualizuj status (np. na „W toku”), aby wskazać, że jest obsługiwane.
    5.  Po rozwiązaniu zmień status na „Rozwiązane”.

#### 2.2.3 index.php (cfrompro/controllers/admin/index.php)

Ten plik jest zazwyczaj placeholderem lub przekierowaniem w modułach PrestaShop i nie reprezentuje bezpośredniego, konfigurowalnego ekranu dla sprzedawcy. Zapewnia, że jeśli ktoś spróbuje uzyskać bezpośredni dostęp do katalogu `controllers/admin`, zostanie przekierowany lub zostanie wykonana domyślna akcja, zapobiegając lukom w zabezpieczeniach związanych z listowaniem katalogów. Sprzedawcy nie będą z tym bezpośrednio wchodzić w interakcje.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Główna konfiguracja modułu** | Profil wsparcia szablonu | Classic | Dostosowuje styl formularza do Twojego motywu. |
| | Adres e-mail autorespondera | `info@twojskep.com` | Adres e-mail do potwierdzeń dla klientów. |
| | Tytuł e-maila (dla właściciela sklepu) | Nowe zgłoszenie z formularza kontaktowego | Temat Twoich e-maili powiadomień. |
| | Adres(y) e-mail odbiorcy | `kontakt@twojskep.com` | Gdzie wysyłane są wszystkie zgłoszenia z formularzy (globalnie). |
| | DW dla e-maila powiadomienia sklepu | Puste | Ukryta kopia powiadomień do wewnętrznego śledzenia. |
| | Zgodność z RODO | TAK | Dodaje obowiązkowe pole wyboru zgody na politykę prywatności. |
| | Strona polityki prywatności | Twoja strona CMS z polityką prywatności | Łączy pole wyboru RODO z Twoją polityką. |
| | ReCaptcha (v2) | TAK | Włącza Google reCAPTCHA do ochrony przed spamem. |
| | Klucz witryny ReCaptcha | Twój klucz witryny Google | Klucz publiczny dla widżetu reCAPTCHA. |
| | Klucz tajny ReCaptcha | Twój klucz tajny Google | Klucz prywatny do weryfikacji reCAPTCHA. |
| | Adres URL webhooka (Slack/Discord) | Puste | Wysyła powiadomienia do Slack/Discord. |
| | Niestandardowy CSS (front-office) | Puste | Dodaj niestandardowe style do swoich formularzy. |
| | Minimalna długość pytania (znaki) | 10-20 | Minimalna liczba znaków dla głównego pola wiadomości. |
| | Maksymalna długość pytania (znaki) | 500-1000 | Maksymalna liczba znaków dla głównego pola wiadomości. |
| | Zezwalaj na załączniki graficzne | TAK | Włącza przesyłanie plików w formularzach. |
| | Maksymalny rozmiar załącznika (MB) | 2-5 | Maksymalny rozmiar przesyłanych plików. |
| | Czas trwania komunikatu o sukcesie (ms) | 3000-5000 | Jak długo widoczne jest powiadomienie o sukcesie. |
| **Zarządzanie formularzami** | Nazwa formularza | Opisowa nazwa | Wewnętrzna nazwa dla Twojego niestandardowego formularza. |
| | Shortcode | Automatycznie generowany `[cfrompro id="X"]` | Kod do osadzenia formularza. |
| | Status formularza | Włączony | Aktywuje/dezaktywuje formularz. |
| | Adres(y) e-mail odbiorcy DLA TEGO Formularza | Specyficzny(e) adres(y) e-mail | Nadpisuje globalnego odbiorcę dla tego formularza. |
| | Pola niestandardowe | Różne | Zdefiniuj unikalne pola wprowadzania dla każdego formularza. |
| | Włącz pływający wyzwalacz | NIE (lub TAK dla konkretnych formularzy) | Pokazuje pływający przycisk do otwierania formularza. |
| | Tekst wyzwalacza | „Skontaktuj się z nami” | Tekst na pływającym przycisku. |
| | Pozycja wyzwalacza | Prawo/Lewo | Umiejscowienie pływającego przycisku. |
| **Zarządzanie pytaniami** | Wyświetl pytanie | N/A | Wyświetla pełne szczegóły zapytania klienta. |
| | Odpowiedz | N/A | Wyślij odpowiedź e-mail do klienta. |
| | Zmień status | Nowe, W toku, Rozwiązane | Śledź obsługę zapytań. |

## 3. Rozwiązywanie problemów dla sprzedawcy i często zadawane pytania (FAQ)

**P: Moje formularze nie wyglądają poprawnie lub stylizacja jest uszkodzona.**
O:

-   **Sprawdź „Profil wsparcia szablonu”:** Przejdź do **Moduły > Menedżer modułów > Advanced Contact Form Builder Pro > Konfiguruj** i upewnij się, że „Profil wsparcia szablonu” pasuje do Twojego aktualnego motywu PrestaShop (np. „Classic” dla domyślnego motywu).
-   **Wyczyść pamięć podręczną Smarty:** Przejdź do **Zaawansowane > Wydajność**, przewiń w dół do „Pamięć podręczna” i kliknij „Wyczyść pamięć podręczną”. Czasami stare pliki stylów mogą się zablokować.
-   **Niestandardowy CSS:** Jeśli dodałeś niestandardowy CSS, dokładnie sprawdź go pod kątem błędów. Tymczasowo usuń go, aby sprawdzić, czy to on powoduje problem.
-   **Konflikty motywów:** Jeśli problem nadal występuje, Twój motyw może mieć konflikt. Skontaktuj się z twórcą motywu lub wsparciem MyPresta.eu.

**P: Nie otrzymuję powiadomień e-mail, gdy formularz zostanie przesłany.**
O:

-   **Sprawdź adresy e-mail odbiorców:** Przejdź do **Moduły > Menedżer modułów > Advanced Contact Form Builder Pro > Konfiguruj** i sprawdź, czy „Adres(y) e-mail odbiorcy” są poprawne. Sprawdź również indywidualne ustawienia formularza w **Advanced Contact Form Pro > Formularze**, aby sprawdzić, czy konkretny formularz nadpisuje globalnego odbiorcę.
-   **Sprawdź folder spamu:** E-maile mogą trafiać do folderu spamu lub wiadomości-śmieci.
-   **Ustawienia poczty serwera:** Upewnij się, że ustawienia e-mail Twojego sklepu PrestaShop są poprawnie skonfigurowane (**Zaawansowane > E-mail**). Przetestuj wysyłanie zwykłego e-maila z PrestaShop.
-   **Dostawca hostingu:** Twój dostawca hostingu może mieć limity wysyłania e-maili lub problemy. Sprawdź logi serwera lub skontaktuj się z nim.

**P: reCAPTCHA nie działa lub formularze nie są przesyłane z włączoną reCAPTCHA.**
O:

-   **Zweryfikuj klucze:** Dokładnie sprawdź „Klucz witryny ReCaptcha” i „Klucz tajny ReCaptcha” w głównej konfiguracji modułu. Upewnij się, że nie ma literówek i że odpowiadają one konfiguracji reCAPTCHA v2 na Twoim koncie Google.
-   **Rejestracja domeny:** Upewnij się, że nazwa domeny Twojego sklepu jest poprawnie zarejestrowana na Twoim koncie Google reCAPTCHA.
-   **Problemy z siecią:** Tymczasowo wyłącz reCAPTCHA, aby sprawdzić, czy formularze są przesyłane. Jeśli tak, problem leży w konfiguracji reCAPTCHA lub komunikacji z serwerami Google.

**P: Jak przetłumaczyć pola formularza i wiadomości na inne języki?**
O:

-   **System tłumaczeń PrestaShop:** Przejdź do **Lokalizacja > Tłumaczenia**.
-   **Typ tłumaczenia:** Wybierz „Tłumaczenia zainstalowanych modułów”.
-   **Wybierz swój motyw:** Wybierz swój aktualny motyw.
-   **Wybierz swój język:** Wybierz język, na który chcesz przetłumaczyć.
-   **Moduł:** Wybierz „cfrompro” (techniczna nazwa modułu).
-   Następnie zobaczysz listę wszystkich przetłumaczalnych ciągów z modułu, w tym etykiety pól, komunikaty o sukcesie i komunikaty o błędach. Przetłumacz je i zapisz.

**P: Mój pływający przycisk wyzwalający nie pojawia się.**
O:

-   **Włącz wyzwalacz:** Przejdź do **Advanced Contact Form Pro > Formularze**, edytuj formularz, który chcesz wyzwolić, i upewnij się, że „Włącz pływający wyzwalacz” jest ustawione na TAK.
-   **Opóźnienie wyzwalacza:** Sprawdź ustawienie „Opóźnienie wyzwalacza (ms)”. Jeśli jest to wysoka liczba, być może będziesz musiał poczekać dłużej, aż się pojawi.
-   **Konflikty motywów:** Niektóre motywy mogą mieć CSS, który ukrywa przycisk, lub JavaScript, który zakłóca jego działanie. Sprawdź konsolę programisty w przeglądarce pod kątem błędów.
-   **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł **Advanced Contact Form Builder Pro** (`cfrompro`) stosuje standardowy wzorzec PrestaShop MVC (Model-View-Controller), rozszerzając podstawowe klasy PrestaShop dla swojej funkcjonalności. Wykorzystuje `ObjectModel` do zarządzania niestandardowymi formularzami i przesłanymi pytaniami, używa dedykowanych kontrolerów administracyjnych do zarządzania w Panelu administracyjnym oraz integruje się z różnymi hookami PrestaShop do wyświetlania w front-office i działań w backendzie. Niestandardowe pola są zarządzane za pomocą dedykowanej klasy i przechowywane jako JSON.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `cfrompro/controllers/front/index.php`
    *   **Nazwa klasy:** `CfromproIndexModuleFrontController` (prawdopodobnie, na podstawie nazwy pliku)
    *   **Klasa nadrzędna:** `ModuleFrontController`
    *   **Odpowiedzialność:** Ten kontroler jest prawdopodobnie odpowiedzialny za obsługę początkowego wyświetlania formularza, jeśli jest dostępny za pośrednictwem bezpośredniego adresu URL (chociaż większość formularzy jest osadzona lub otwierana za pośrednictwem AJAX). Może również obsługiwać początkowe renderowanie pływającego wyzwalacza lub modalu zawierającego formularz.
-   `cfrompro/controllers/front/question.php`
    *   **Nazwa klasy:** `CfromproQuestionModuleFrontController` (prawdopodobnie)
    *   **Klasa nadrzędna:** `ModuleFrontController`
    *   **Odpowiedzialność:** Jest to główny kontroler do przetwarzania zgłoszeń formularzy. Odbiera dane POST z formularzy, wykonuje walidację (w tym reCAPTCHA, długość pola, wymagane pola, rozmiar załącznika), zapisuje przesłane dane (pytanie i pola niestandardowe) do bazy danych, wysyła powiadomienia e-mail do właściciela sklepu i autoresponder do klienta, a potencjalnie uruchamia webhook. Zwraca odpowiedzi JSON dla zgłoszeń AJAX (np. komunikaty o sukcesie/błędzie).

#### Kontrolery administracyjne Back-Office

-   `cfrompro/controllers/admin/AdminCfromproForm.php`
    *   **Nazwa klasy:** `AdminCfromproFormController`
    *   **Klasa nadrzędna:** `ModuleAdminController`
    *   **Nazwa zakładki:** „Formularze” pod „Advanced Contact Form Pro”
    *   **Zarządzana encja:** `CfromproForm` (hipotetyczny `ObjectModel` dla formularzy)
    *   **Odpowiedzialność:** Zarządza operacjami CRUD (Create, Read, Update, Delete) dla niestandardowych formularzy. Definiuje widok listy (siatkę) dla formularzy i strukturę formularza do dodawania/edycji formularza. Ten kontroler obsługuje zapisywanie ustawień formularza, w tym złożonej struktury JSON dla pól niestandardowych.
-   `cfrompro/controllers/admin/AdminCfromproQuestion.php`
    *   **Nazwa klasy:** `AdminCfromproQuestionController`
    *   **Klasa nadrzędna:** `ModuleAdminController`
    *   **Nazwa zakładki:** „Pytania” pod „Advanced Contact Form Pro”
    *   **Zarządzana encja:** `CfromproQuestion` (hipotetyczny `ObjectModel` dla przesłanych pytań)
    *   **Odpowiedzialność:** Zarządza operacjami CRUD dla przesłanych pytań. Wyświetla listę zapytań, umożliwia przeglądanie szczegółów poszczególnych pytań oraz zapewnia funkcjonalność odpowiadania klientom i zmiany statusu zapytania.
-   `cfrompro/controllers/admin/index.php`
    *   **Nazwa klasy:** (Zazwyczaj brak)
    *   **Klasa nadrzędna:** (Zazwyczaj brak)
    *   **Odpowiedzialność:** Jest to standardowa praktyka PrestaShop, aby zapobiec bezpośredniemu listowaniu katalogów. Zazwyczaj zawiera prosty `header('Location: ../../index.php?controller=AdminHome');` lub podobny, aby przekierować do pulpitu nawigacyjnego Panelu administracyjnego. Nie reprezentuje funkcjonalnego kontrolera dla logiki modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `cfrompro/classes/CfromproCustomFields.php`
    *   **Nazwa klasy:** `CfromproCustomFields`
    *   **Klasa nadrzędna:** (Prawdopodobnie `ObjectModel` lub niestandardowa klasa bazowa do obsługi złożonych danych)
    *   **Tabela bazy danych:** (Prawdopodobnie `ps_cfrompro_form`, jeśli przechowuje definicje pól niestandardowych w obiekcie formularza, lub oddzielna tabela `ps_cfrompro_custom_field`, jeśli pola są samodzielnymi encjami). Dokumentacja modułu wskazuje `cfrompro_form` i `cfrompro_question` jako zarządzane tabele, co sugeruje, że pola niestandardowe są prawdopodobnie serializowane w tabeli `cfrompro_form`.
    *   **Pola `$definition`:** Jeśli rozszerza `ObjectModel`, definiowałoby pola związane z właściwościami pól niestandardowych (np. `id_cfrompro_custom_field`, `id_cfrompro_form`, `type`, `label`, `required`, `options`, `validation`). Biorąc pod uwagę opis modułu, bardziej prawdopodobne jest, że pola niestandardowe są przechowywane jako ciąg JSON w tabeli `cfrompro_form`, a ta klasa dostarcza pomocnicze metody do parsowania, walidacji i renderowania tych pól.
    *   **Kluczowe metody publiczne i logika biznesowa:**
        *   Metody do dodawania, edytowania i usuwania definicji pól niestandardowych w formularzu.
        *   Metody do renderowania pól niestandardowych w szablonie front-office.
        *   Metody do walidacji przesłanych danych pól niestandardowych.
        *   Metody do serializacji/deserializacji konfiguracji pól niestandardowych do/z JSON.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `cfrompro/views/cfrompro.js`
    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Jest to główny plik JavaScript front-office. Prawdopodobnie obsługuje:
        *   Wyświetlanie i zarządzanie pływającym przyciskiem wyzwalającym (zdarzenia kliknięcia, opóźnienia).
        *   Otwieranie i zamykanie modalu/wyskakującego okna formularza.
        *   Przesyłanie formularzy za pomocą AJAX (zbieranie danych, wysyłanie do kontrolera `question.php`).
        *   Wyświetlanie komunikatów o sukcesie/błędzie (powiadomienia typu toast).
        *   Walidację pól formularza po stronie klienta.
        *   Integrację z reCAPTCHA v2 (renderowanie widżetu, uzyskiwanie tokena odpowiedzi).
        *   Dynamiczne aktualizacje na podstawie typów pól niestandardowych (np. pokazywanie/ukrywanie opcji dla list rozwijanych).
-   `cfrompro/views/js/admin-button-style.js`
    *   **Zakres:** Back-office (AdminCfromproFormController).
    *   **Odpowiedzialność:** Zapewnia funkcjonalność JavaScript do stylizowania pływającego przycisku wyzwalającego w interfejsie konfiguracji formularza. Może to obejmować próbniki kolorów, podglądy ikon i aktualizacje w czasie rzeczywistym podglądu przycisku.
-   `cfrompro/views/js/admin-form-layout.js`
    *   **Zakres:** Back-office (AdminCfromproFormController).
    *   **Odpowiedzialność:** Obsługuje dynamiczny układ i zarządzanie polami niestandardowymi w interfejsie tworzenia/edycji formularza. Obejmowałoby to:
        *   Dodawanie nowych pól niestandardowych (dynamiczne generowanie HTML dla różnych typów pól).
        *   Zmienianie kolejności pól (przeciągnij i upuść).
        *   Edytowanie właściwości pól (etykieta, typ, wymagane, opcje).
        *   Usuwanie pól.
        *   Serializowanie konfiguracji pól niestandardowych do ciągu JSON przed zapisaniem formularza.
-   `cfrompro/views/js/admin-icon-picker-data.js`
    *   **Zakres:** Back-office (AdminCfromproFormController).
    *   **Odpowiedzialność:** Zawiera dane (np. tablicę klas ikon lub ścieżek SVG) używane przez selektor ikon dla pływającego przycisku wyzwalającego.
-   `cfrompro/views/js/admin-icon-picker.js`
    *   **Zakres:** Back-office (AdminCfromproFormController).
    *   **Odpowiedzialność:** Implementuje interfejs użytkownika i logikę do wyboru ikony dla pływającego przycisku wyzwalającego. Wykorzystuje dane z `admin-icon-picker-data.js` do wyświetlania dostępnych ikon i aktualizuje wybraną ikonę w formularzu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `cfrompro/views/cfrompro.css`
    *   **Zakres:** Stylizacja klienta front-office.
    *   **Odpowiedzialność:** Zapewnia podstawową stylizację formularzy kontaktowych, pływającego wyzwalacza, modalnych wyskakujących okienek oraz komunikatów o sukcesie/błędzie w sklepie. Definiuje ogólny układ, typografię, kolory i responsywność.
    *   **Kluczowe selektory klas CSS:** `.cfrompro-form`, `.cfrompro-field`, `.cfrompro-trigger`, `.cfrompro-modal`, `.cfrompro-toast`.
-   `cfrompro/views/css/admin-button-style.css`
    *   **Zakres:** Stylizacja formularzy administracyjnych back-office.
    *   **Odpowiedzialność:** Stylizuje elementy związane z konfiguracją pływającego przycisku wyzwalającego w Panelu administracyjnym (np. próbniki kolorów, obszary podglądu ikon).
-   `cfrompro/views/css/admin-custom-fields.css`
    *   **Zakres:** Stylizacja formularzy administracyjnych back-office.
    *   **Odpowiedzialność:** Stylizuje interfejs do zarządzania polami niestandardowymi w kreatorze formularzy (np. uchwyty do przeciągania i upuszczania, panele konfiguracji pól).
-   `cfrompro/views/css/admin-form-layout.css`
    *   **Zakres:** Stylizacja formularzy administracyjnych back-office.
    *   **Odpowiedzialność:** Zapewnia ogólny układ i stylizację strony tworzenia/edycji formularza w Panelu administracyjnym.
-   `cfrompro/views/css/admin-icon-picker.css`
    *   **Zakres:** Stylizacja formularzy administracyjnych back-office.
    *   **Odpowiedzialność:** Stylizuje interfejs wyboru ikon dla pływającego przycisku wyzwalającego.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `cfrompro/views/templates/hook/dashboard_recent_messages.tpl`
    *   **Hook:** `displaydashboardZoneTwo` (lub podobny hook pulpitu nawigacyjnego).
    *   **Wyjście:** Blok na pulpicie nawigacyjnym PrestaShop wyświetlający ostatnie zgłoszenia formularzy, zapewniający szybki przegląd dla sprzedawcy.

#### Szablony administracyjne (`views/templates/admin/`)

-   `cfrompro/views/templates/admin/button_style_block.tpl`
    *   **Zakres:** AdminCfromproFormController (strona edycji formularza).
    *   **Wyjście:** HTML dla sekcji, w której sprzedawca konfiguruje wygląd pływającego przycisku wyzwalającego (kolory, tekst, ikona).
-   `cfrompro/views/templates/admin/conversation_reply.tpl`
    *   **Zakres:** AdminCfromproQuestionController (strona widoku pytania).
    *   **Wyjście:** HTML dla formularza odpowiedzi i sekcji aktualizacji statusu podczas przeglądania przesłanego pytania.
-   `cfrompro/views/templates/admin/custom_fields_block.tpl`
    *   **Zakres:** AdminCfromproFormController (strona edycji formularza).
    *   **Wyjście:** Główny kontener i kontrolki do dodawania, edytowania i układania pól niestandardowych w formularzu. Ten szablon prawdopodobnie działa w połączeniu z `admin-form-layout.js`.
-   `cfrompro/views/templates/admin/form_layout_block.tpl`
    *   **Zakres:** AdminCfromproFormController (strona edycji formularza).
    *   **Wyjście:** Ogólna struktura układu dla strony konfiguracji formularza, otaczająca inne bloki, takie jak pola niestandardowe i style przycisków.
-   `cfrompro/views/templates/admin/question_extras.tpl`
    *   **Zakres:** AdminCfromproQuestionController (strona widoku pytania).
    *   **Wyjście:** Wyświetla dodatkowe szczegóły związane z przesłanym pytaniem, takie jak załączniki lub specyficzne metadane.
-   `cfrompro/views/templates/admin/question_form_profile.tpl`
    *   **Zakres:** AdminCfromproQuestionController (strona widoku pytania).
    *   **Wyjście:** Wyświetla szczegóły dotyczące formularza, z którego zostało przesłane pytanie.
-   `cfrompro/views/templates/admin/topic_options_block.tpl`
    *   **Zakres:** AdminCfromproFormController (strona edycji formularza).
    *   **Wyjście:** Jeśli moduł obsługuje predefiniowane tematy, ten szablon renderowałby opcje ich konfiguracji.

#### Szablony front-office (`views/templates/front/` i katalog główny `views/`)

-   `cfrompro/views/cfrompro-extra-forms.tpl`
    *   **Hook:** Prawdopodobnie `displayFooter` lub `actionOutputHTMLBefore` do renderowania formularzy, które nie są osadzone bezpośrednio, ale pojawiają się w modalach.
    *   **Wyjście:** Zawiera strukturę HTML dla formularzy, które mają być wyświetlane w oknie modalnym, często wywoływanych przez pływający przycisk.
-   `cfrompro/views/cfrompro-extra-trigger.tpl`
    *   **Hook:** Prawdopodobnie `displayHeader` lub `actionOutputHTMLBefore` do renderowania pływającego przycisku wyzwalającego.
    *   **Wyjście:** HTML dla pływającego przycisku, który po kliknięciu otwiera formularz kontaktowy.
-   `cfrompro/views/cfrompro-form-body.tpl`
    *   **Zakres:** Używany przez inne szablony (np. `cfrompro-extra-forms.tpl`) lub bezpośrednio podczas osadzania formularza za pomocą shortcode'u.
    *   **Wyjście:** Podstawowa struktura HTML dla pojedynczego formularza kontaktowego, w tym pól, etykiet, reCAPTCHA, pola wyboru RODO i przycisku przesyłania. Ten szablon jest dynamicznie wypełniany polami niestandardowymi.
-   `cfrompro/views/classic/cfrompro-extra-forms.tpl`
    *   **Zakres:** Nadpisanie specyficzne dla motywu dla `cfrompro-extra-forms.tpl`.
    *   **Wyjście:** To samo co `cfrompro-extra-forms.tpl`, ale specjalnie dostosowane do struktury HTML motywu Classic.
-   `cfrompro/views/classic/cfrompro-extra-trigger.tpl`
    *   **Zakres:** Nadpisanie specyficzne dla motywu dla `cfrompro-extra-trigger.tpl`.
    *   **Wyjście:** To samo co `cfrompro-extra-trigger.tpl`, ale specjalnie dostosowane do motywu Classic.
-   `cfrompro/views/partials/cfrompro-custom-field-single.tpl`
    *   **Zakres:** Dołączony przez `cfrompro-form-body.tpl`.
    *   **Wyjście:** Renderuje HTML dla pojedynczego pola niestandardowego na podstawie jego typu (tekst, obszar tekstowy, wybór itp.).
-   `cfrompro/views/partials/cfrompro-custom-fields.tpl`
    *   **Zakres:** Dołączony przez `cfrompro-form-body.tpl`.
    *   **Wyjście:** Iteruje przez definicje pól niestandardowych dla formularza i renderuje każde z nich za pomocą `cfrompro-custom-field-single.tpl`.
-   `cfrompro/views/partials/cfrompro-field-fragment.tpl`
    *   **Zakres:** Dołączony przez `cfrompro-form-body.tpl` lub `cfrompro-custom-field-single.tpl`.
    *   **Wyjście:** Fragment HTML wielokrotnego użytku dla wspólnych elementów pól, takich jak etykiety, komunikaty o błędach lub opakowania.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

-   `ps_cfrompro_form`: Przechowuje definicje każdego niestandardowego formularza kontaktowego utworzonego przez moduł.
    *   `id_cfrompro_form`: Klucz główny.
    *   `name`: Wewnętrzna nazwa formularza.
    *   `shortcode`: Unikalny identyfikator do osadzania.
    *   `active`: (boolean) Status formularza.
    *   `recipient_emails`: (text) Nadpisane adresy e-mail odbiorców dla tego formularza.
    *   `autoresponder_email`: (text) Nadpisany adres e-mail autorespondera dla tego formularza.
    *   `email_title`: (text) Nadpisany temat e-maila dla tego formularza.
    *   `custom_fields_json`: (text/JSON) Serializowany ciąg JSON zawierający definicje wszystkich pól niestandardowych dla tego formularza (typ, etykieta, wymagane, opcje, walidacja itp.).
    *   `trigger_enabled`: (boolean) Czy pływający wyzwalacz jest aktywny dla tego formularza.
    *   `trigger_text`: (text) Tekst na pływającym wyzwalaczu.
    *   `trigger_position`: (text) Pozycja pływającego wyzwalacza.
    *   `trigger_icon`: (text) Klasa ikony dla wyzwalacza.
    *   `trigger_delay_ms`: (int) Opóźnienie pojawienia się wyzwalacza.
    *   `trigger_color`, `trigger_text_color`, `trigger_hover_color`: (text) Stylizacja wyzwalacza.
-   `ps_cfrompro_question`: Przechowuje każde przesłane pytanie/zapytanie.
    *   `id_cfrompro_question`: Klucz główny.
    *   `id_cfrompro_form`: Klucz obcy do `ps_cfrompro_form`.
    *   `customer_name`: Imię i nazwisko klienta przesyłającego.
    *   `customer_email`: Adres e-mail klienta przesyłającego.
    *   `customer_phone`: Numer telefonu (jeśli widoczny/wymagany).
    *   `topic`: Wybrany temat (jeśli widoczny/wymagany).
    *   `message`: Główna treść pytania/wiadomości.
    *   `submitted_data_json`: (text/JSON) Serializowany ciąg JSON zawierający wszystkie przesłane wartości pól niestandardowych.
    *   `attachments`: (text/JSON) Ścieżka(i) do przesłanych plików.
    *   `ip_address`: Adres IP przesyłającego.
    *   `date_add`: Sygnatura czasowa przesłania.
    *   `status`: (int/text) Status zapytania (np. 0=Nowe, 1=W toku, 2=Rozwiązane).
-   `ps_configuration`: Ustawienia modułu są przechowywane tutaj z kluczami takimi jak `cfrompro_TITLE`, `cfrompro_AUTORESPONDER`, `cfrompro_GDPR`, `cfrompro_recaptcha_sitekey` itp.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionOutputHTMLBefore` | Przed wysłaniem wyjścia HTML do przeglądarki. | Wstrzykiwanie HTML pływającego wyzwalacza, formularzy modalnych lub niestandardowego CSS/JS globalnie. |
| `displaydashboardZoneTwo` | Renderuje zawartość w drugiej strefie pulpitu nawigacyjnego PrestaShop. | Wyświetlanie podsumowania ostatnich zgłoszeń formularzy w Panelu administracyjnym. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny ustawia swoje media (JS/CSS). | Dodawanie do kolejki specyficznych dla Panelu administracyjnego JS (`admin-button-style.js`, `admin-form-layout.js` itp.) i CSS (`admin-button-style.css`, `admin-custom-fields.css` itp.) dla stron konfiguracji modułu. |
| `displayHeader` | W sekcji `<head>` front-office. | Dodawanie do kolejki specyficznych dla front-office JS (`cfrompro.js`) i CSS (`cfrompro.css`), a potencjalnie skryptów reCAPTCHA. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu **Advanced Contact Form Builder Pro**.
