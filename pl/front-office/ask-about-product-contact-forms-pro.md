---
title: "Zapytaj o produkt - profesjonalne formularze kontaktowe - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop „Zapytaj o produkt - profesjonalne formularze kontaktowe” od MyPresta.eu."
sidebar:
  label: "Zapytaj o produkt - profesjonalne formularze kontaktowe - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Ask about product - contact forms pro na MyPresta.eu](https://mypresta.eu/modules/front-office-features/ask-about-product-contact-forms-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/ask-about-product-contact-forms-pro/)
>
> ---


# Zapytaj o produkt - profesjonalne formularze kontaktowe

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są wymagane do prawidłowego działania modułu, zwłaszcza dla funkcji takich jak reCAPTCHA i webhooki. Są one zazwyczaj dostępne w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Ten moduł oferuje szerokie opcje dostosowywania, aby dopasować formularze kontaktowe do Twoich konkretnych potrzeb. Przejdziemy przez każdy ekran konfiguracji i ustawienie.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny obszar konfiguracji modułu, dostępny bezpośrednio po instalacji lub poprzez nawigację do **Moduły > Menedżer modułów** i kliknięcie „Konfiguruj” obok „Zapytaj o produkt - profesjonalne formularze kontaktowe”.

#### Ustawienia ogólne

-   **Profil wsparcia szablonu**

    *   **Co robi to ustawienie:** To ustawienie pozwala wybrać predefiniowany profil szablonu, który najlepiej pasuje do Twojego motywu PrestaShop. Różne motywy mogą wymagać różnych stylów lub dostosowań strukturalnych, aby formularz wyświetlał się poprawnie.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawiono na „Classic” (lub podobne):* Moduł będzie używał szablonów i stylów zoptymalizowanych dla domyślnego motywu PrestaShop Classic lub motywów na nim opartych.
        *   *Gdy ustawiono na konkretny profil motywu:* Moduł załaduje szablony i CSS zaprojektowane do płynnej integracji z tym konkretnym motywem, zapewniając lepszą spójność wizualną.
    *   **Zalecana wartość:** Wybierz profil odpowiadający Twojemu aktywnemu motywowi PrestaShop. Jeśli nie masz pewności, zacznij od „Classic” i dostosuj, jeśli wystąpią problemy ze stylem.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli używasz niestandardowego motywu, być może będziesz musiał przetestować różne profile lub użyć opcji „Niestandardowy CSS”, aby dopracować wygląd.
-   **Tytuł e-maila (dla właściciela sklepu)**

    *   **Co robi to ustawienie:** Jest to temat wiadomości e-mail z powiadomieniem, którą *Ty* (właściciel/administrator sklepu) otrzymujesz, gdy klient zadaje pytanie.
    *   **Efekt zmiany tego ustawienia:** Zmienia temat wewnętrznych wiadomości e-mail z powiadomieniami.
    *   **Zalecana wartość:** Coś jasnego i informacyjnego, np. „Nowe pytanie o produkt z Twojego sklepu - [Nazwa produktu]”.
    *   **Scenariusz/przykład dla sprzedawcy:** Ustawienie tego na „PILNE: Nowe zapytanie o [Nazwa produktu]” może pomóc Twojemu zespołowi w ustaleniu priorytetów.
-   **Adres(y) e-mail odbiorcy**

    *   **Co robi to ustawienie:** Określa adres(y) e-mail, na które będą wysyłane zapytania o produkty. Możesz wprowadzić wiele adresów e-mail oddzielonych przecinkami.
    *   **Efekt zmiany tego ustawienia:** Określa, kto w Twojej organizacji otrzymuje pytania od klientów.
    *   **Zalecana wartość:** Adres e-mail Twojego zespołu obsługi klienta lub odpowiedniego działu.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli masz dedykowany adres „[sales@yourstore.com](mailto:sales@yourstore.com)” lub „[support@yourstore.com](mailto:support@yourstore.com)”, wprowadź go tutaj. W przypadku większych zespołów możesz wysłać go na listę dystrybucyjną.
-   **UDW dla e-maila z powiadomieniem sklepu**

    *   **Co robi to ustawienie:** Pozwala wysłać kopię UDW (Ukryte Do Wiadomości) e-maila z powiadomieniem sklepu na dodatkowe adresy e-mail. Ci odbiorcy nie będą widoczni dla głównego odbiorcy.
    *   **Efekt zmiany tego ustawienia:** Zapewnia dyskretny sposób powiadamiania innych członków zespołu lub archiwizowania zapytań bez zaśmiecania skrzynki odbiorczej głównego odbiorcy lub ujawniania dodatkowych odbiorców.
    *   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretną potrzebę wewnętrznego śledzenia lub wtórnych powiadomień.
    *   **Scenariusz/przykład dla sprzedawcy:** Możesz wysłać UDW do swojego menedżera marketingu, aby śledzić zainteresowanie klientów, lub na wewnętrzny adres e-mail archiwum.
-   **E-mail autorespondera**

    *   **Co robi to ustawienie:** Jest to temat automatycznej wiadomości e-mail wysyłanej *do klienta* po przesłaniu pytania.
    *   **Efekt zmiany tego ustawienia:** Zmienia temat wiadomości e-mail z potwierdzeniem, którą otrzymują Twoi klienci.
    *   **Zalecana wartość:** „Dziękujemy za Twoje zapytanie - [Nazwa Twojego sklepu]”.
    *   **Scenariusz/przykład dla sprzedawcy:** Jasny temat autorespondera zapewnia klienta, że jego wiadomość została odebrana.
-   **Czas trwania komunikatu o sukcesie (ms)**

    *   **Co robi to ustawienie:** Kontroluje, jak długo komunikat „Twoja wiadomość została wysłana pomyślnie” pozostaje widoczny na ekranie po przesłaniu formularza przez klienta, mierzony w milisekundach (ms).
    *   **Efekt zmiany tego ustawienia:**
        *   *Wyższa wartość (np. 5000ms):* Komunikat pozostaje widoczny dłużej, dając klientom więcej czasu na jego przeczytanie.
        *   *Niższa wartość (np. 2000ms):* Komunikat znika szybko.
    *   **Zalecana wartość:** 3000-5000ms (3-5 sekund) to zazwyczaj dobra równowaga.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoi klienci często korzystają z wolniejszych połączeń lub potrzebują więcej czasu na przetworzenie informacji, dłuższy czas trwania może być korzystny.
-   **Ukryj „Zadaj pytanie” dla produktów niedostępnych w magazynie (aappro\_HIDE\_OOS)**

    *   **Co robi to ustawienie:** Jeśli włączone, formularz lub przycisk „Zadaj pytanie” nie będzie wyświetlany na stronach produktów, które są aktualnie niedostępne w magazynie.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Zapobiega zadawaniu pytań przez klientów o produkty, które są niedostępne, potencjalnie zmniejszając liczbę nieistotnych zapytań dla Twojego zespołu.
        *   *Gdy wyłączone:* Formularz pozostaje widoczny niezależnie od statusu magazynowego.
    *   **Zalecana wartość:** „Tak”, aby zmniejszyć liczbę zapytań o niedostępne produkty, chyba że chcesz specjalnie zbierać zainteresowanie w celu uzupełnienia zapasów.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz unikalne lub limitowane przedmioty, które nie zostaną uzupełnione, ukrycie formularza dla produktów niedostępnych w magazynie ma sens. Jeśli chcesz ocenić zainteresowanie przyszłymi uzupełnieniami, pozostaw to wyłączone.
-   **Zezwalaj tylko zalogowanym klientom na zadawanie pytań (aappro\_LOGGED\_CUSTOMERS\_ONLY)**

    *   **Co robi to ustawienie:** Ogranicza możliwość przesyłania pytań o produkty tylko do klientów, którzy są zalogowani na swoje konta w sklepie.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Niezarejestrowani lub goście nie będą widzieć ani używać formularza „Zadaj pytanie”. Może to pomóc w ograniczeniu spamu i zapewnieniu, że masz dane konta klienta powiązane z zapytaniami.
        *   *Gdy wyłączone:* Każdy może zadać pytanie, w tym goście.
    *   **Zalecana wartość:** „Nie” dla maksymalnego zasięgu klientów, „Tak”, jeśli priorytetem jest zaangażowanie zarejestrowanych klientów i chcesz zmniejszyć liczbę anonimowych zapytań.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli prowadzisz sklep B2B, gdzie wszystkie interakcje wymagają konta, włączenie tej opcji byłoby odpowiednie. W przypadku ogólnego sklepu detalicznego, pozostawienie jej wyłączonej jest zazwyczaj lepsze dla konwersji.

#### Pola formularza i walidacja

-   **Tak / Nie (aappro\_FIELD\_PHONE\_REQUIRED, aappro\_FIELD\_PHONE\_VISIBLE, aappro\_FIELD\_TOPIC\_VISIBLE, aappro\_QUOTE\_QUANTITY\_VISIBLE)**

    *   **Co robi to ustawienie:** Jest to grupa przełączników „Tak/Nie”, które kontrolują widoczność i wymaganie konkretnych pól w formularzach zapytań o produkty:
        *   **Numer telefonu widoczny:** Pokazuje pole numeru telefonu.
        *   **Numer telefonu wymagany:** Sprawia, że pole numeru telefonu jest obowiązkowe, jeśli jest widoczne.
        *   **Wybór tematu widoczny:** Pokazuje rozwijaną listę, aby klienci mogli wybrać temat swojego pytania (np. „Wysyłka”, „Specyfikacje techniczne”, „Dostępność”).
        *   **Widoczna ilość do wyceny:** Pokazuje pole, w którym klienci mogą poprosić o wycenę dla określonej ilości produktu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Włączone (widoczne):* Pole pojawia się w formularzu.
        *   *Wyłączone (widoczne):* Pole jest ukryte.
        *   *Włączone (wymagane):* Klient *musi* wypełnić pole, aby przesłać formularz.
    *   **Zalecana wartość:**
        *   **Telefon:** Widoczny „Nie”, Wymagany „Nie” (chyba że kontakt telefoniczny jest kluczowy dla Twojego modelu biznesowego).
        *   **Temat:** Widoczny „Tak” (pomaga kategoryzować zapytania), Wymagany „Nie”.
        *   **Ilość do wyceny:** Widoczny „Tak” (jeśli oferujesz rabaty hurtowe lub sprzedaż B2B), Wymagany „Nie”.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz złożoną elektronikę, uczynienie „Wybór tematu” widocznym z opcjami takimi jak „Wsparcie techniczne” lub „Kompatybilność” byłoby bardzo pomocne. Jeśli jesteś hurtownikiem, „Ilość do wyceny” jest niezbędna.
-   **Minimalna długość pytania (znaki)**

    *   **Co robi to ustawienie:** Ustawia minimalną liczbę znaków, które klient musi wpisać w polu pytania, zanim będzie mógł przesłać formularz.
    *   **Efekt zmiany tego ustawienia:** Zapobiega bardzo krótkim, potencjalnie nieprzydatnym lub spamerskim pytaniom.
    *   **Zalecana wartość:** 10-20 znaków.
    *   **Scenariusz/przykład dla sprzedawcy:** Ustawienie tego na 15 znaków zapewnia, że klienci podają wystarczająco dużo szczegółów poza samym „Pytaniem”.
-   **Maksymalna długość pytania (znaki)**

    *   **Co robi to ustawienie:** Ustawia maksymalną liczbę znaków, które klient może wpisać w polu pytania.
    *   **Efekt zmiany tego ustawienia:** Zapobiega nadmiernie długim pytaniom, które mogą być trudne do odczytania lub wskazywać, że klient próbuje użyć formularza jako ogólnego czatu.
    *   **Zalecana wartość:** 500-1000 znaków.
    *   **Scenariusz/przykład dla sprzedawcy:** Limit 750 znaków jest zazwyczaj wystarczający dla większości zapytań o produkty.
-   **Zezwalaj na załączanie obrazów**

    *   **Co robi to ustawienie:** Umożliwia klientom przesyłanie pliku obrazu (np. zrzutu ekranu, zdjęcia uszkodzonego przedmiotu lub diagramu) wraz z pytaniem.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* W formularzu pojawia się pole „Prześlij plik”.
        *   *Gdy wyłączone:* Brak opcji załączania.
    *   **Zalecana wartość:** „Tak” może być bardzo pomocne w przypadku zapytań wizualnych, ale upewnij się, że Twój serwer może obsłużyć przechowywanie.
    *   **Scenariusz/przykład dla sprzedawcy:** Klient może chcieć załączyć zdjęcie konkretnej części produktu, o którą ma pytanie, lub zrzut ekranu błędu, który napotyka.
-   **Maksymalny rozmiar załącznika (MB)**

    *   **Co robi to ustawienie:** Jeśli załączanie obrazów jest włączone, ustawia maksymalny rozmiar pliku (w megabajtach) dozwolony dla każdego załącznika.
    *   **Efekt zmiany tego ustawienia:** Kontroluje obciążenie serwera i wykorzystanie pamięci masowej.
    *   **Zalecana wartość:** 2-5 MB jest zazwyczaj wystarczające dla większości obrazów.
    *   **Scenariusz/przykład dla sprzedawcy:** Ustawienie na 3 MB zapobiega przesyłaniu przez klientów bardzo dużych, wysokiej rozdzielczości obrazów, które nie są konieczne do zapytania.

#### Bezpieczeństwo i zgodność

-   **Zgodność z RODO**

    *   **Co robi to ustawienie:** Włącza funkcje pomagające Twoim formularzom w spełnieniu wymagań RODO (Ogólne Rozporządzenie o Ochronie Danych), zazwyczaj poprzez dodanie pola wyboru zgody na przetwarzanie danych.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* W formularzu pojawi się pole wyboru, wymagające od klientów wyraźnej zgody na Twoją politykę prywatności przed przesłaniem pytania.
        *   *Gdy wyłączone:* Brak pola wyboru zgody RODO.
    *   **Zalecana wartość:** „Tak”, jeśli Twój sklep działa w regionach podlegających RODO (np. UE) lub obsługuje klientów z tych regionów.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz klientom w Europie, włączenie tej opcji jest prawnie ważne.
-   **Strona polityki prywatności**

    *   **Co robi to ustawienie:** Jeśli włączono zgodność z RODO, to ustawienie pozwala wybrać stronę CMS, która zawiera politykę prywatności Twojego sklepu. Pole wyboru zgody RODO będzie prowadzić do tej strony.
    *   **Efekt zmiany tego ustawienia:** Zapewnia klientom łatwy dostęp do Twojej polityki prywatności, spełniając kluczowy wymóg RODO.
    *   **Zalecana wartość:** Wybierz swoją dedykowaną stronę CMS z polityką prywatności.
    *   **Scenariusz/przykład dla sprzedawcy:** Po włączeniu RODO musisz wybrać poprawną stronę CMS, aby klienci mogli zapoznać się z Twoimi praktykami przetwarzania danych.
-   **ReCaptcha (v2)**

    *   **Co robi to ustawienie:** Integruje Google reCAPTCHA v2 (pole wyboru „Nie jestem robotem”) z Twoimi formularzami, aby zapobiegać spamowi i przesyłaniu przez boty.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Pole wyboru reCAPTCHA pojawia się w formularzu, wymagając interakcji użytkownika, aby udowodnić, że jest człowiekiem.
        *   *Gdy wyłączone:* Nie używa się reCAPTCHA.
    *   **Zalecana wartość:** „Tak”, aby znacznie zmniejszyć spam, zwłaszcza jeśli doświadczasz wielu przesyłanych przez boty.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli otrzymujesz wiele niechcianych zapytań, włączenie reCAPTCHA jest silną obroną.
-   **Klucz witryny ReCaptcha**

    *   **Co robi to ustawienie:** Jest to klucz publiczny dostarczony przez Google po zarejestrowaniu Twojej witryny w reCAPTCHA. Służy do wyświetlania widżetu reCAPTCHA na Twojej stronie.
    *   **Efekt zmiany tego ustawienia:** Niezbędny do działania reCAPTCHA. Bez niego reCAPTCHA nie pojawi się ani nie będzie działać.
    *   **Zalecana wartość:** Twój unikalny klucz witryny reCAPTCHA z Google.
    *   **Scenariusz/przykład dla sprzedawcy:** Musisz przejść do konsoli administracyjnej Google reCAPTCHA, zarejestrować swoją domenę i skopiować ten klucz do ustawień modułu.
-   **Klucz tajny ReCaptcha**

    *   **Co robi to ustawienie:** Jest to klucz prywatny dostarczony przez Google, używany do weryfikacji odpowiedzi reCAPTCHA po stronie serwera.
    *   **Efekt zmiany tego ustawienia:** Niezbędny do bezpiecznego działania reCAPTCHA. Moduł używa tego klucza do potwierdzenia, że użytkownik faktycznie przeszedł wyzwanie reCAPTCHA.
    *   **Zalecana wartość:** Twój unikalny klucz tajny reCAPTCHA z Google.
    *   **Scenariusz/przykład dla sprzedawcy:** Ten klucz powinien być poufny i nigdy nie powinien być ujawniany w kodzie po stronie klienta.

#### Integracja i dostosowywanie

-   **Adres URL webhooka (Slack/Discord)**

    *   **Co robi to ustawienie:** Pozwala wysyłać powiadomienia o nowych zapytaniach o produkty na adres URL webhooka, zazwyczaj używany dla usług takich jak Slack lub Discord.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy podano adres URL:* Nowe zapytania wywołają powiadomienie na określonym kanale czatu.
        *   *Gdy puste:* Nie są wysyłane powiadomienia webhook.
    *   **Zalecana wartość:** Pozostaw puste, chyba że aktywnie używasz Slacka, Discorda lub innej usługi, która obsługuje przychodzące webhooki do komunikacji zespołowej.
    *   **Scenariusz/przykład dla sprzedawcy:** Twój zespół obsługi klienta używa Slacka. Możesz skonfigurować przychodzący webhook w Slacku i wkleić jego adres URL tutaj, aby każde nowe pytanie o produkt natychmiast pojawiało się na Twoim kanale #customer-support.
-   **Niestandardowy CSS (tylko strona produktu)**

    *   **Co robi to ustawienie:** Udostępnia obszar tekstowy, w którym możesz dodać niestandardowe reguły CSS do stylizacji formularza zapytania o produkt specjalnie na stronach produktów.
    *   **Efekt zmiany tego ustawienia:** Pozwala nadpisać domyślne style modułu lub style Twojego motywu, aby idealnie dopasować się do estetyki Twojej marki bez bezpośredniej modyfikacji plików modułu.
    *   **Zalecana wartość:** Używaj oszczędnie do drobnych korekt. W przypadku większych zmian rozważ nadpisanie motywu.
    *   **Scenariusz/przykład dla sprzedawcy:** Chcesz zmienić kolor przycisku „Wyślij” na główny kolor Twojej marki lub dostosować odstępy wokół pól formularza. Możesz dodać `.aappro-form-submit-button { background-color: #FF0000; }` tutaj.
-   **Pola niestandardowe (aappro\_CUSTOM\_FIELDS\_JSON)**

    *   **Co robi to ustawienie:** Jest to potężna funkcja, która pozwala definiować dodatkowe, niestandardowe pola dla Twoich formularzy kontaktowych. Możesz określić typy pól (tekst, obszar tekstowy, wybór, pole wyboru), etykiety i to, czy są one wymagane. Jest to zazwyczaj zarządzane za pomocą dedykowanego interfejsu, a nie surowego pola JSON.
    *   **Efekt zmiany tego ustawienia:** Dodaje nowe pola wprowadzania do Twoich formularzy, umożliwiając zbieranie bardziej szczegółowych informacji od klientów.
    *   **Zalecana wartość:** Dodaj pola istotne dla Twoich produktów lub usług (np. „Numer zamówienia” dla istniejących klientów, „Przeznaczenie” dla B2B).
    *   **Scenariusz/przykład dla sprzedawcy:** W przypadku sklepu odzieżowego możesz dodać niestandardowe pole „Pożądany rozmiar”, jeśli klienci często pytają o konkretne rozmiary, których nie ma na liście. W przypadku sklepu technologicznego „Aktualny model urządzenia” może być przydatny.
-   **Zezwalaj na komentarze (aappro\_ALLOW\_COMMENTS)**

    *   **Co robi to ustawienie:** To ustawienie prawdopodobnie kontroluje, czy klienci mogą zostawiać ogólne komentarze na stronie produktu, być może oddzielnie od konkretnego formularza „Zadaj pytanie”.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Może pojawić się ogólna sekcja komentarzy.
        *   *Gdy wyłączone:* Dostępny jest tylko ustrukturyzowany formularz „Zadaj pytanie”.
    *   **Zalecana wartość:** „Nie”, jeśli chcesz, aby komunikacja była skoncentrowana na ustrukturyzowanym formularzu pytań. „Tak”, jeśli chcesz zachęcić do szerszej publicznej dyskusji.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli wolisz bezpośrednie, prywatne zapytania zamiast publicznych komentarzy, wyłącz tę opcję.
-   **PS\_STOCK\_MANAGEMENT**

    *   **Co robi to ustawienie:** Jest to podstawowe ustawienie PrestaShop, niekontrolowane bezpośrednio przez moduł, ale moduł może odczytywać jego wartość. Określa, czy zarządzanie zapasami jest włączone globalnie w Twoim sklepie.
    *   **Efekt zmiany tego ustawienia:** Jeśli zarządzanie zapasami jest wyłączone, ustawienie modułu „Ukryj dla produktów niedostępnych w magazynie” może nie działać zgodnie z oczekiwaniami, ponieważ produkty nie będą miały jasnego statusu magazynowego.
    *   **Zalecana wartość:** „Tak” dla większości sklepów e-commerce, aby dokładnie śledzić inwentarz.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz produkty cyfrowe, możesz wyłączyć zarządzanie zapasami. Jednak w przypadku towarów fizycznych jest to kluczowe.
-   **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG**

    *   **Co robią te ustawienia:** Są to podstawowe ustawienia PrestaShop związane z językiem. `PS_LANG_DEFAULT` ustawia domyślny język front-office, a `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` pozwala pracownikom wybrać język panelu administracyjnego. Moduł używa ich do zapewnienia prawidłowego wyświetlania języka dla formularzy i powiadomień.
    *   **Efekt zmiany tych ustawień:** Wpływa na język formularzy i powiadomień.
    *   **Zalecana wartość:** Ustaw `PS_LANG_DEFAULT` na główny język Twojego sklepu. `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` można włączyć, jeśli masz wielojęzyczny zespół.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli głównym językiem Twojego sklepu jest francuski, upewnij się, że `PS_LANG_DEFAULT` jest ustawiony na francuski.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Główna konfiguracja | Profil wsparcia szablonu | Twój motyw / Classic | Zapewnia prawidłową stylizację i integrację z Twoim motywem. |
| Główna konfiguracja | Tytuł e-maila (dla właściciela sklepu) | „Nowe pytanie o produkt” | Temat wewnętrznych e-maili z powiadomieniami dla administratora. |
| Główna konfiguracja | Adres(y) e-mail odbiorcy | Twój e-mail administratora | Gdzie wysyłane są pytania klientów. |
| Główna konfiguracja | UDW dla e-maila z powiadomieniem sklepu | Puste | Dyskretnie wysyłaj kopie powiadomień do innych. |
| Główna konfiguracja | E-mail autorespondera | „Dziękujemy za Twoje zapytanie” | Temat e-maili z potwierdzeniem dla klientów. |
| Główna konfiguracja | Czas trwania komunikatu o sukcesie (ms) | 3000-5000 | Jak długo widoczne jest powiadomienie „wiadomość wysłana”. |
| Główna konfiguracja | Ukryj dla produktów niedostępnych w magazynie | Tak | Zapobiega pytaniom o niedostępne produkty. |
| Główna konfiguracja | Zezwalaj tylko zalogowanym klientom | Nie | Ogranicza dostęp do formularza zarejestrowanym użytkownikom. |
| Główna konfiguracja | Numer telefonu widoczny | Nie | Pokazuje/ukrywa pole numeru telefonu. |
| Główna konfiguracja | Numer telefonu wymagany | Nie | Sprawia, że numer telefonu jest obowiązkowy, jeśli jest widoczny. |
| Główna konfiguracja | Wybór tematu widoczny | Tak | Pokazuje/ukrywa rozwijaną listę tematów pytań. |
| Główna konfiguracja | Widoczna ilość do wyceny | Tak (jeśli B2B) | Pokazuje/ukrywa pole do zapytań o wycenę ilości. |
| Główna konfiguracja | Minimalna długość pytania | 15 znaków | Zapobiega zbyt krótkim pytaniom. |
| Główna konfiguracja | Maksymalna długość pytania | 750 znaków | Zapobiega zbyt długim pytaniom. |
| Główna konfiguracja | Zezwalaj na załączanie obrazów | Tak | Umożliwia klientom przesyłanie plików. |
| Główna konfiguracja | Maksymalny rozmiar załącznika (MB) | 3 MB | Ogranicza rozmiar przesyłanych plików. |
| Główna konfiguracja | Zgodność z RODO | Tak (jeśli dotyczy) | Dodaje pole wyboru zgody na przetwarzanie danych. |
| Główna konfiguracja | Strona polityki prywatności | Twoja strona CMS z polityką prywatności | Łączy pole wyboru RODO z Twoją stroną polityki. |
| Główna konfiguracja | ReCaptcha (v2) | Tak | Integruje Google reCAPTCHA w celu ochrony przed spamem. |
| Główna konfiguracja | Klucz witryny ReCaptcha | Twój klucz witryny Google | Klucz publiczny do wyświetlania widżetu reCAPTCHA. |
| Główna konfiguracja | Klucz tajny ReCaptcha | Twój klucz tajny Google | Klucz prywatny do weryfikacji reCAPTCHA po stronie serwera. |
| Główna konfiguracja | Adres URL webhooka (Slack/Discord) | Puste | Wysyła powiadomienia do zewnętrznych usług czatu. |
| Główna konfiguracja | Niestandardowy CSS (tylko strona produktu) | Puste | Dodaj niestandardowy CSS do stylizacji formularza. |
| Główna konfiguracja | Pola niestandardowe | Konfigurowane przez AdminAapproForm | Zdefiniuj dodatkowe pola dla swoich formularzy. |
| Główna konfiguracja | Zezwalaj na komentarze | Nie | Kontroluje ogólne komentarze do produktów vs. ustrukturyzowane pytania. |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Oprócz głównej konfiguracji, ten moduł udostępnia dedykowane sekcje w Twoim Panelu administracyjnym PrestaShop do zarządzania formularzami, pytaniami i polami niestandardowymi.

#### 2.2.1 AdminAapproFormController: Zarządzanie formularzami (Panel administracyjny > Moduły > Zapytaj o produkt > Formularze)

Ten ekran pozwala tworzyć i zarządzać różnymi formularzami zapytań o produkty oraz określać, gdzie pojawiają się w Twoim sklepie.

-   **Nazwa ekranu i lokalizacja w menu:** **Moduły > Zapytaj o produkt > Formularze**
-   **Dostępne akcje i ustawienia:**
    *   **Tabela listingu:** Wyświetla wszystkie utworzone formularze z ich nazwami, statusem i powiązanymi produktami/kategoriami/producentami.
    *   **Przycisk Dodaj nowy formularz:** Kliknij, aby utworzyć nowy formularz.
    *   **Akcje Edytuj/Usuń:** Modyfikuj lub usuwaj istniejące formularze.
    *   **Pola formularza:** Podczas dodawania lub edytowania formularza skonfigurujesz:
        *   **Nazwa formularza:** Wewnętrzna nazwa do Twojej referencji.
        *   **Aktywny:** Włącz lub wyłącz formularz.
        *   **Wyświetl na stronie produktu:** Wybierz, czy ten formularz ma pojawiać się na stronach produktów.
        *   **Wyświetl na stronie kategorii:** Wybierz, czy ten formularz ma pojawiać się na stronach kategorii.
        *   **Wyświetl na stronie producenta:** Wybierz, czy ten formularz ma pojawiać się na stronach producentów.
        *   **Adres(y) e-mail odbiorcy dla tego formularza:** Nadpisz globalny adres e-mail odbiorcy dla tego konkretnego formularza. Jest to kluczowe dla kierowania pytań do konkretnych zespołów.
        *   **Produkty:** Wybierz konkretne produkty, na których ma pojawiać się ten formularz.
        *   **Kategorie:** Wybierz konkretne kategorie, na których ma pojawiać się ten formularz.
        *   **Producenci:** Wybierz konkretnych producentów, na których ma pojawiać się ten formularz.
        *   **Pola niestandardowe:** Tutaj definiujesz unikalne pola dla *tego konkretnego formularza*. Możesz dodawać pola tekstowe, obszary tekstowe, rozwijane listy, pola wyboru itp. i oznaczać je jako wymagane.
-   **Efekt zmian:**
    *   Utworzenie nowego formularza pozwala zdefiniować unikalny zestaw pytań i reguł routingu.
    *   Powiązanie formularzy z konkretnymi produktami, kategoriami lub producentami oznacza, że tylko ten konkretny formularz zostanie wyświetlony, gdy klient przegląda element pasujący do tych kryteriów.
    *   Nadpisanie adresów e-mail odbiorców zapewnia, że pytania dotyczące na przykład „Elektroniki” trafiają do działu elektroniki, a pytania dotyczące „Odzieży” trafiają do zespołu mody.
    *   Pola niestandardowe pozwalają zbierać bardzo szczegółowe informacje istotne dla kontekstu formularza.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Zidentyfikuj potrzeby:** Określ, czy potrzebujesz różnych formularzy dla różnych typów produktów, działów lub segmentów klientów.
    2.  **Utwórz formularze:** Przejdź do **Formularze** i kliknij „Dodaj nowy formularz”.
    3.  **Skonfiguruj routing:** Ustaw konkretne „Adres(y) e-mail odbiorcy dla tego formularza”, aby zapewnić, że pytania trafiają we właściwe miejsce.
    4.  **Zdefiniuj zakres:** Użyj selektorów „Produkty”, „Kategorie” i „Producenci”, aby kontrolować, gdzie pojawia się każdy formularz.
    5.  **Dodaj pola niestandardowe:** Dostosuj pytania zadawane w każdym formularzu za pomocą sekcji „Pola niestandardowe”, aby zbierać istotne informacje.
    6.  **Testuj:** Zawsze testuj swoje formularze w front-office, aby upewnić się, że wyświetlają się poprawnie i wysyłają e-maile do właściwych odbiorców.

#### 2.2.2 AdminAapproQuestionController: Zarządzanie pytaniami (Panel administracyjny > Moduły > Zapytaj o produkt > Pytania)

Ten ekran służy jako Twoje centralne centrum do przeglądania i zarządzania wszystkimi przesłanymi pytaniami klientów.

-   **Nazwa ekranu i lokalizacja w menu:** **Moduły > Zapytaj o produkt > Pytania**
-   **Zarządzana tabela / encja:** `aappro_question` (przechowuje wszystkie przesłane zapytania)
-   **Pola formularza i kolumny:**
    *   **Widok siatki / zarządzania:** Wyświetla listę wszystkich przesłanych pytań.
        *   **Kolumny:** Zazwyczaj obejmuje: Imię klienta, E-mail klienta, Nazwa produktu (jeśli dotyczy), Temat pytania, Data przesłania, Status (np. Nowe, Odpowiedziano, Zamknięte).
        *   **Filtrowanie i sortowanie:** Standardowe funkcje listy PrestaShop do filtrowania według daty, klienta, produktu lub statusu.
    *   **Akcja Widok/Odpowiedz:** Kliknięcie pytania pozwala wyświetlić jego pełne szczegóły i odpowiedzieć klientowi.
        *   **Szczegóły pytania:** Pokazuje pełną wiadomość klienta, dane kontaktowe, szczegóły produktu i wszelkie załączniki.
        *   **Interfejs odpowiedzi:** Obszar tekstowy do komponowania odpowiedzi, która zostanie wysłana bezpośrednio na adres e-mail klienta.
        *   **Aktualizacja statusu:** Opcja zmiany statusu pytania (np. z „Nowe” na „Odpowiedziano”).
-   **Efekt zmian:**
    *   Ten ekran zapewnia scentralizowaną skrzynkę odbiorczą dla wszystkich zapytań związanych z produktami, ułatwiając śledzenie i odpowiadanie.
    *   Odpowiadanie bezpośrednio stąd zapewnia, że historia rozmów jest utrzymywana w PrestaShop i powiązana z konkretnym produktem.
    *   Aktualizacja statusu pomaga Twojemu zespołowi zarządzać obciążeniem pracą i zapewnia, że żadne pytania nie zostaną pominięte.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Regularnie sprawdzaj:** Wprowadź nawyk codziennego (lub kilka razy dziennie, w zależności od wolumenu) sprawdzania tej sekcji.
    2.  **Ustal priorytety:** Użyj filtrów, aby zidentyfikować pilne lub nieodpowiedziane pytania.
    3.  **Wyświetl i odpowiedz:** Kliknij „Widok” na pytaniu, przeczytaj szczegóły i skomponuj jasną, pomocną odpowiedź.
    4.  **Zaktualizuj status:** Po udzieleniu odpowiedzi zmień status pytania na „Odpowiedziano” lub „Zamknięte”, aby utrzymać porządek w kolejce.
    5.  **Wykorzystaj kontekst produktu:** Moduł automatycznie łączy pytanie z produktem, dzięki czemu masz cały niezbędny kontekst podczas odpowiadania.

#### 2.2.3 index.php (aappro/controllers/admin/index.php)

Ten plik jest standardową praktyką PrestaShop zapobiegającą bezpośredniemu listowaniu katalogów w Panelu administracyjnym. Zazwyczaj zawiera proste `header('Location: ../../index.php?controller=AdminHome');` lub podobne przekierowanie, zapewniając, że jeśli ktoś spróbuje uzyskać bezpośredni dostęp do katalogu `controllers/admin/`, zostanie odesłany do głównego pulpitu administracyjnego. Nie zarządza żadną konkretną encją ani nie ma konfigurowalnych pól.

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

-   **P: Mój formularz nie wyświetla się na stronie produktu.**

    *   **O:**
        1.  **Sprawdź status modułu:** Upewnij się, że moduł jest zainstalowany i włączony w **Moduły > Menedżer modułów**.
        2.  **Sprawdź konfigurację formularza:** Przejdź do **Moduły > Zapytaj o produkt > Formularze**. Upewnij się, że konkretny formularz, który ma się wyświetlać, jest „Aktywny” i poprawnie powiązany z przeglądanym produktem, kategorią lub producentem.
        3.  **Umiejscowienie haka:** Sprawdź, czy moduł jest podpięty do obszaru wyświetlania, który jest renderowany przez Twój motyw (np. `displayProductExtraContent`, `displayProductAdditionalInfo`). Czasami motywy nadpisują domyślne pozycje haków.
        4.  **Kompatybilność motywu:** Jeśli używasz wysoce spersonalizowanego motywu, spróbuj tymczasowo przełączyć się na domyślny motyw Classic, aby sprawdzić, czy formularz się pojawi. Jeśli tak, może występować konflikt z plikami szablonów lub CSS Twojego niestandardowego motywu.
        5.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**).
-   **P: Nie otrzymuję powiadomień e-mail, gdy klient przesyła pytanie.**

    *   **O:**
        1.  **Sprawdź adresy e-mail odbiorców:** Zweryfikuj „Adres(y) e-mail odbiorcy” w głównej konfiguracji modułu, a także konkretne „Adres(y) e-mail odbiorcy dla tego formularza” w ustawieniach formularza (**Moduły > Zapytaj o produkt > Formularze > Edytuj formularz**). Upewnij się, że są poprawne i wolne od błędów.
        2.  **Folder spam:** Sprawdź folder spam lub niechciane wiadomości e-mail.
        3.  **Ustawienia poczty serwera:** Upewnij się, że ustawienia poczty e-mail Twojego sklepu PrestaShop są poprawnie skonfigurowane (**Zaawansowane > E-mail**). Wyślij testową wiadomość e-mail z PrestaShop, aby potwierdzić, że Twój serwer może wysyłać wiadomości e-mail.
        4.  **Dostawca hostingu:** Skontaktuj się z dostawcą hostingu, aby sprawdzić, czy nie ma żadnych ograniczeń lub problemów z wysyłaniem wiadomości e-mail po stronie serwera.
        5.  **Logi modułu:** Sprawdź logi błędów PrestaShop (jeśli są dostępne) lub logi błędów PHP Twojego serwera pod kątem wszelkich błędów związanych z pocztą.
-   **P: reCAPTCHA nie działa lub nie wyświetla się.**

    *   **O:**
        1.  **Włącz reCAPTCHA:** Upewnij się, że „ReCaptcha (v2)” jest ustawione na „Tak” w głównej konfiguracji modułu.
        2.  **Klucze:** Dokładnie sprawdź, czy Twoje „Klucz witryny ReCaptcha” i „Klucz tajny ReCaptcha” są poprawnie wprowadzone i odpowiadają kluczom z Twojego konta Google reCAPTCHA dla Twojej domeny.
        3.  **Rejestracja domeny:** Upewnij się, że Twoja domena jest poprawnie zarejestrowana w konsoli administracyjnej Google reCAPTCHA.
        4.  **Problemy z przeglądarką:** Przetestuj w różnych przeglądarkach i wyczyść pamięć podręczną przeglądarki. Czasami blokery reklam mogą zakłócać działanie reCAPTCHA.
-   **P: Jak przetłumaczyć pola formularza i wiadomości na inne języki?**

    *   **O:**
        1.  Przejdź do **Lokalizacja > Tłumaczenia**.
        2.  Wybierz „Tłumaczenia zainstalowanych modułów”.
        3.  Wybierz swój motyw, język, na który chcesz przetłumaczyć, a następnie wybierz „Zapytaj o produkt - profesjonalne formularze kontaktowe” z listy modułów.
        4.  Możesz wtedy przetłumaczyć wszystkie widoczne ciągi znaków, etykiety pól i wiadomości używane przez moduł. Pamiętaj, aby zapisać zmiany.
-   **P: Stylizacja formularza wygląda źle z moim niestandardowym motywem.**

    *   **O:**
        1.  **Profil wsparcia szablonu:** Spróbuj dostosować ustawienie „Profil wsparcia szablonu” w głównej konfiguracji modułu, aby sprawdzić, czy inny profil działa lepiej.
        2.  **Niestandardowy CSS:** Użyj pola „Niestandardowy CSS (tylko strona produktu)” w konfiguracji modułu, aby dodać konkretne reguły CSS, aby nadpisać lub dostosować stylizację. Będziesz potrzebować podstawowej wiedzy CSS lub programisty stron internetowych.
        3.  **Nadpisania motywu:** W przypadku bardziej rozległych zmian, programista może potrzebować utworzyć nadpisania motywu dla plików szablonów modułu (`.tpl`) lub plików CSS, umieszczając je w katalogu `modules/aappro/` Twojego motywu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Zapytaj o produkt - profesjonalne formularze kontaktowe”, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł stosuje standardowy wzorzec MVC (Model-View-Controller) PrestaShop, rozszerzając podstawowe klasy PrestaShop dla swojej funkcjonalności. Wykorzystuje `ModuleFrontController` do interakcji z front-office (przesyłanie formularzy, odpowiedzi) i `AdminController` do zarządzania formularzami i pytaniami w back-office. Niestandardowe klasy `ObjectModel` (`AapproCustomFields`, `AapproFormMatcher`) są używane do utrwalania danych specyficznych dla modułu. Haki są szeroko stosowane do integracji formularza w różnych częściach front-office.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `controllers/front/index.php`
    *   **Nazwa klasy i klasa nadrzędna:** `AapproIndexModuleFrontController` rozszerza `ModuleFrontController`.
    *   **Odpowiedzialność:** Prawdopodobnie obsługuje początkowe renderowanie formularza lub wyzwalacz formularza, potencjalnie za pośrednictwem AJAX. Może przygotowywać dane dla szablonu formularza.
-   `controllers/front/question.php`
    *   **Nazwa klasy i klasa nadrzędna:** `AapproQuestionModuleFrontController` rozszerza `ModuleFrontController`.
    *   **Odpowiedzialność:** Ten kontroler jest odpowiedzialny za przetwarzanie przesłania formularza zapytania o produkt. Waliduje dane wejściowe, obsługuje weryfikację reCAPTCHA, przetwarza przesyłanie plików (jeśli włączone), zapisuje pytanie do bazy danych, wysyła powiadomienia e-mail do właściciela sklepu i potencjalnie autoresponder do klienta. Zwraca odpowiedzi JSON dla przesłań AJAX.
-   `controllers/front/reply.php`
    *   **Nazwa klasy i klasa nadrzędna:** `AapproReplyModuleFrontController` rozszerza `ModuleFrontController`.
    *   **Odpowiedzialność:** Ten kontroler prawdopodobnie obsługuje mechanizm odpowiedzi skierowany do klienta, jeśli moduł pozwala klientom przeglądać odpowiedzi w front-office lub udostępnia konkretny link do przeglądania odpowiedzi. Pobierałby pytanie i powiązane odpowiedzi.

#### Kontrolery administracyjne Back-Office

-   `controllers/admin/AdminAapproForm.php`
    *   **Nazwa klasy i klasa nadrzędna:** `AdminAapproFormController` rozszerza `ModuleAdminController`.
    *   **Nazwa zakładki i zarządzana encja:** Zarządza niestandardowymi formularzami zapytań. Dostępne przez **Moduły > Zapytaj o produkt > Formularze**. Obsługuje operacje CRUD dla obiektów `AapproFormMatcher`, w tym definiowanie nazw formularzy, statusu aktywacji, powiązanych produktów/kategorii/producentów i pól niestandardowych.
-   `controllers/admin/AdminAapproQuestion.php`
    *   **Nazwa klasy i klasa nadrzędna:** `AdminAapproQuestionController` rozszerza `ModuleAdminController`.
    *   **Nazwa zakładki i zarządzana encja:** Zarządza przesłanymi pytaniami klientów. Dostępne przez **Moduły > Zapytaj o produkt > Pytania**. Zapewnia widok listy pytań, pozwala przeglądać pełne szczegóły pytania i oferuje interfejs do odpowiadania klientom i aktualizowania statusu pytania.
-   `controllers/admin/index.php`
    *   **Nazwa klasy i klasa nadrzędna:** Nie jest funkcjonalnym kontrolerem.
    *   **Odpowiedzialność:** Standardowy plik bezpieczeństwa PrestaShop zapobiegający listowaniu katalogów. Zazwyczaj przekierowuje do pulpitu administracyjnego.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `classes/AapproCustomFields.php`
    *   **Z jaką tabelą bazy danych współdziała:** Prawdopodobnie `ps_aappro_custom_field` (lub podobna).
    *   **Rozszerza ObjectModel:** Tak, rozszerza `ObjectModel`.
    *   **Pola `$definition`:** Zdefiniowałoby pola takie jak `id_aappro_custom_field`, `id_aappro_form`, `name`, `type`, `label`, `required`, `options` (dla pól wyboru, często zakodowane w JSON), `position`, `active`.
    *   **Kluczowe metody publiczne i logika biznesowa:** Metody do zapisywania, pobierania i usuwania definicji pól niestandardowych powiązanych z konkretnymi formularzami. Logika do parsowania i renderowania danych pól niestandardowych.
-   `classes/AapproFormMatcher.php`
    *   **Z jaką tabelą bazy danych współdziała:** Prawdopodobnie `ps_aappro_form` (lub podobna).
    *   **Rozszerza ObjectModel:** Tak, rozszerza `ObjectModel`.
    *   **Pola `$definition`:** Zdefiniowałoby pola takie jak `id_aappro_form`, `name`, `active`, `recipient_emails`, `products` (tablica ID produktów zakodowana w JSON), `categories` (tablica ID kategorii zakodowana w JSON), `manufacturers` (tablica ID producentów zakodowana w JSON), `display_product`, `display_category`, `display_manufacturer`.
    *   **Kluczowe metody publiczne i logika biznesowa:** Metody do zarządzania konfiguracjami formularzy, w tym zapisywania powiązań z produktami/kategoriami/producentami oraz pobierania poprawnego formularza na podstawie bieżącego kontekstu (ID produktu, ID kategorii).

### 4.4 Zasoby JavaScript (`views/js/`)

-   `aappro/lib/searchTool/views/js/autocomplete.js`
    *   **Zakres:** Back-office.
    *   **Opis:** Zapewnia funkcjonalność autouzupełniania do wybierania produktów, kategorii lub producentów podczas konfigurowania formularzy w `AdminAapproFormController`. Wiąże się z polami wejściowymi, aby sugerować encje podczas pisania przez użytkownika, poprawiając UX dla powiązania formularzy.
-   `aappro/views/aappro.js`
    *   **Zakres:** Front-office.
    *   **Opis:** Główny skrypt front-office dla modułu.
        *   **Słuchacze zdarzeń:** Wiąże zdarzenia kliknięcia z przyciskami/linkami „Zadaj pytanie”, zdarzenia przesłania z formularzami zapytań.
        *   **Manipulacja DOM:** Obsługuje pokazywanie/ukrywanie formularza (np. w modalu lub rozwijanej sekcji), wyświetlanie komunikatów o sukcesie/błędzie (powiadomienia typu toast).
        *   **Wywołania AJAX:** Asynchronicznie przesyła dane formularza do `AapproQuestionModuleFrontController`, obsługuje odpowiedź reCAPTCHA i aktualizuje interfejs użytkownika na podstawie odpowiedzi JSON z serwera.
        *   **Walidacja:** Może zawierać walidację po stronie klienta dla pól formularza (np. minimalna/maksymalna długość).
-   `aappro/views/js/admin-button-style.js`
    *   **Zakres:** Back-office.
    *   **Opis:** Prawdopodobnie zapewnia interaktywne elementy lub podglądy do konfigurowania stylów przycisków (np. selektory kolorów, suwaki rozmiaru) w konfiguracji modułu lub ekranach zarządzania formularzami.
-   `aappro/views/js/admin-form-layout.js`
    *   **Zakres:** Back-office.
    *   **Opis:** Obsługuje dynamiczny układ i interakcję do tworzenia/edycji formularzy w `AdminAapproFormController`, zwłaszcza do zarządzania polami niestandardowymi. Może to obejmować dodawanie/usuwanie wierszy pól niestandardowych, zmianę kolejności pól i zarządzanie opcjami specyficznymi dla typu pola.
-   `aappro/views/js/admin-icon-picker-data.js`
    *   **Zakres:** Back-office.
    *   **Opis:** Zawiera dane (np. tablicę klas ikon lub ścieżek SVG) dla interfejsu wyboru ikon używanego w back-office, prawdopodobnie dla ikon pól niestandardowych lub opcji wyświetlania formularzy.
-   `aappro/views/js/admin-icon-picker.js`
    *   **Zakres:** Back-office.
    *   **Opis:** Implementuje logikę interfejsu użytkownika wyboru ikon, umożliwiając administratorom wybieranie ikon z predefiniowanego zestawu, prawdopodobnie używanego w połączeniu z `admin-icon-picker-data.js`.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `aappro/lib/searchTool/views/css/autocomplete.css`
    *   **Zakres:** Back-office.
    *   **Opis:** Style dla rozwijanych list autouzupełniania i pól wejściowych używanych w konfiguracji formularza administracyjnego (np. do wybierania produktów/kategorii).
-   `aappro/views/aappro.css`
    *   **Zakres:** Stylizacja klienta front-office.
    *   **Opis:** Podstawowa stylizacja formularzy zapytań o produkty, przycisków, modali, komunikatów o sukcesie/błędzie (powiadomienia typu toast) i wszelkich innych elementów front-office renderowanych przez moduł.
    *   **Kluczowe selektory klas CSS:** `.aappro-form-container`, `.aappro-form-trigger`, `.aappro-modal`, `.aappro-field-group`, `.aappro-submit-button`, `.aappro-success-toast`, `.aappro-error-toast`.
-   `aappro/views/css/admin-button-style.css`
    *   **Zakres:** Stylizacja formularza administracyjnego back-office.
    *   **Opis:** Style dla elementów konfiguracji przycisków w interfejsie administracyjnym modułu.
-   `aappro/views/css/admin-custom-fields.css`
    *   **Zakres:** Stylizacja formularza administracyjnego back-office.
    *   **Opis:** Style dla dynamicznego interfejsu zarządzania polami niestandardowymi w `AdminAapproFormController`, zapewniające przejrzysty i użyteczny układ do dodawania/edycji pól niestandardowych.
-   `aappro/views/css/admin-form-layout.css`
    *   **Zakres:** Stylizacja formularza administracyjnego back-office.
    *   **Opis:** Ogólny układ i stylizacja ekranów tworzenia/edycji formularzy w panelu administracyjnym, zapewniające spójny wygląd i działanie.
-   `aappro/views/css/admin-icon-picker.css`
    *   **Zakres:** Stylizacja formularza administracyjnego back-office.
    *   **Opis:** Style dla interfejsu wyboru ikon używanego w panelu administracyjnym.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony haków (`views/templates/hook/`)

-   `aappro/views/aappro-extra-forms.tpl`
    *   **Hak:** `displayProductExtraContent` lub podobny.
    *   **Wyjście:** Renderuje dodatkowe formularze lub bloki treści związane z produktem, potencjalnie zawierające sam formularz zapytania lub jego wyzwalacz.
-   `aappro/views/aappro-extra-trigger.tpl`
    *   **Hak:** `displayProductButtons`, `displayProductAdditionalInfo`.
    *   **Wyjście:** Renderuje przycisk lub link (np. „Zadaj pytanie”), który wyzwala wyświetlanie formularza zapytania, często w modalu lub ukrytej sekcji.
-   `aappro/views/aappro-extra.tpl`
    *   **Hak:** `displayProductExtraContent`, `displayProductAdditionalInfo`.
    *   **Wyjście:** Ogólny szablon dla dodatkowej treści na stronie produktu, potencjalnie opakowujący formularz lub jego wyzwalacz.
-   `aappro/views/aappro-faq-tab-title.tpl`
    *   **Hak:** `displayProductTab`.
    *   **Wyjście:** Renderuje tytuł zakładki produktu (np. „Zadaj pytanie” lub „FAQ”), która po kliknięciu ujawnia zawartość formularza.
-   `aappro/views/aappro-faq-tab.tpl`
    *   **Hak:** `displayProductTabContent`.
    *   **Wyjście:** Renderuje rzeczywistą zawartość zakładki produktu, która byłaby samym formularzem zapytania.
-   `aappro/views/aappro-form-body.tpl`
    *   **Hak:** Wewnętrzne dołączenie.
    *   **Wyjście:** Podstawowa struktura HTML dla pól formularza zapytania (imię, e-mail, pytanie, pola niestandardowe, reCAPTCHA, pole wyboru RODO). Jest to prawdopodobnie dołączane przez inne szablony.
-   `aappro/views/aappro-form-tab.tpl`
    *   **Hak:** `displayProductTabContent`.
    *   **Wyjście:** Podobnie jak `aappro-faq-tab.tpl`, specjalnie do renderowania formularza w zakładce produktu.
-   `aappro/views/aappro-product-embed.tpl`
    *   **Hak:** `displayProductAdditionalInfo`, `displayReassurance`.
    *   **Wyjście:** Osadza formularz zapytania bezpośrednio w treści strony produktu, a nie w zakładce lub modalu.
-   `aappro/views/classic/` (i `views/partials/`)
    *   Te katalogi zawierają szablony specyficzne dla motywu (dla motywu Classic) i wielokrotnego użytku częściowe. Odzwierciedlają strukturę głównego katalogu `views/`, ale są zoptymalizowane lub specjalnie stylizowane dla motywu Classic.
    *   `aappro-custom-field-single.tpl`: Renderuje pojedyncze pole niestandardowe na podstawie jego typu.
    *   `aappro-custom-fields.tpl`: Iteruje i renderuje wszystkie pola niestandardowe dla formularza.
    *   `aappro-field-fragment.tpl`: Fragment wielokrotnego użytku do renderowania wspólnych elementów pól formularza.

#### Szablony administracyjne (`views/templates/admin/`)

-   `aappro/views/templates/admin/button_style_block.tpl`
    *   **Cel:** Renderuje interfejs do konfigurowania stylów przycisków w panelu administracyjnym.
-   `aappro/views/templates/admin/conversation_reply.tpl`
    *   **Cel:** Renderuje interfejs odpowiedzi podczas przeglądania pytania klienta w `AdminAapproQuestionController`.
-   `aappro/views/templates/admin/custom_fields_block.tpl`
    *   **Cel:** Renderuje dynamiczny interfejs do dodawania, edytowania i zarządzania polami niestandardowymi w `AdminAapproFormController`.
-   `aappro/views/templates/admin/form_layout_block.tpl`
    *   **Cel:** Renderuje ogólne opcje układu dla formularzy w panelu administracyjnym.
-   `aappro/views/templates/admin/question_extras.tpl`
    *   **Cel:** Wyświetla dodatkowe szczegóły lub akcje związane z konkretnym pytaniem w `AdminAapproQuestionController`.
-   `aappro/views/templates/admin/question_product_preview.tpl`
    *   **Cel:** Renderuje mały podgląd produktu powiązanego z pytaniem w `AdminAapproQuestionController`.
-   `aappro/views/templates/admin/topic_options_block.tpl`
    *   **Cel:** Renderuje interfejs konfiguracji do definiowania dostępnych tematów dla rozwijanej listy „Wybór tematu”.
-   `aappro/views/templates/admin/view_question.tpl`
    *   **Cel:** Główny szablon do wyświetlania pojedynczego pytania klienta i jego szczegółów w `AdminAapproQuestionController`.

### 4.7 Schemat bazy danych i mapa haków

#### Tabele bazy danych

-   `ps_aappro_form`: Przechowuje definicje każdego niestandardowego formularza zapytania utworzonego przez sprzedawcę.

    *   `id_aappro_form` (PK)
    *   `name` (VARCHAR)
    *   `active` (TINYINT)
    *   `recipient_emails` (TEXT)
    *   `products` (TEXT, tablica ID produktów zakodowana w JSON)
    *   `categories` (TEXT, tablica ID kategorii zakodowana w JSON)
    *   `manufacturers` (TEXT, tablica ID producentów zakodowana w JSON)
    *   `display_product` (TINYINT)
    *   `display_category` (TINYINT)
    *   `display_manufacturer` (TINYINT)
-   `ps_aappro_custom_field`: Przechowuje definicje pól niestandardowych powiązanych z każdym formularzem.

    *   `id_aappro_custom_field` (PK)
    *   `id_aappro_form` (FK do `ps_aappro_form`)
    *   `name` (VARCHAR)
    *   `type` (VARCHAR, np. ‘text’, ‘textarea’, ‘select’, ‘checkbox’)
    *   `label` (TEXT, wielojęzyczne)
    *   `required` (TINYINT)
    *   `options` (TEXT, zakodowane w JSON dla opcji wyboru/radio)
    *   `position` (INT)
    *   `active` (TINYINT)
-   `ps_aappro_question`: Przechowuje każde przesłane pytanie klienta.

    *   `id_aappro_question` (PK)
    *   `id_product` (FK do `ps_product`)
    *   `id_customer` (FK do `ps_customer`, jeśli zalogowany)
    *   `id_aappro_form` (FK do `ps_aappro_form`)
    *   `customer_name` (VARCHAR)
    *   `customer_email` (VARCHAR)
    *   `customer_phone` (VARCHAR, jeśli włączone)
    *   `topic` (VARCHAR, jeśli włączone)
    *   `quantity_request` (INT, jeśli włączone)
    *   `question_text` (TEXT)
    *   `attachment_path` (VARCHAR, jeśli włączone)
    *   `custom_fields_data` (TEXT, tablica wartości pól niestandardowych zakodowana w JSON)
    *   `ip_address` (VARCHAR)
    *   `date_add` (DATETIME)
    *   `status` (VARCHAR, np. ‘new’, ‘replied’, ‘closed’)
-   `ps_aappro_question_reply`: Przechowuje odpowiedzi administratora na pytania klientów.

    *   `id_aappro_question_reply` (PK)
    *   `id_aappro_question` (FK do `ps_aappro_question`)
    *   `id_employee` (FK do `ps_employee`)
    *   `reply_text` (TEXT)
    *   `date_add` (DATETIME)
-   **Rekordy konfiguracji (w tabeli `ps_configuration`):**

    *   `aappro_TITLE`
    *   `aappro_AUTORESPONDER`
    *   `aappro_FIELD_PHONE_REQUIRED`
    *   `aappro_FIELD_PHONE_VISIBLE`
    *   `aappro_FIELD_TOPIC_VISIBLE`
    *   `aappro_QUOTE_QUANTITY_VISIBLE`
    *   `aappro_WEBHOOK_URL`
    *   `aappro_Q_LEN_MIN`
    *   `aappro_Q_LEN_MAX`
    *   `aappro_ATTACHMENT_ENABLE`
    *   `aappro_ATTACHMENT_MAX_MB`
    *   `aappro_SHOP_MAIL_BCC`
    *   `aappro_TOAST_MS`
    *   `aappro_FLOAT_DELAY_MS`
    *   `aappro_THEME_SUPPORT`
    *   `aappro_CUSTOM_CSS`
    *   `aappro_CUSTOM_FIELDS_JSON` (prawdopodobnie przestarzałe na rzecz tabeli `ps_aappro_custom_field`)
    *   `aappro_recaptcha`
    *   `aappro_GDPR`
    *   `aappro_GDPRCMS`
    *   `aappro_recaptcha_sitekey`
    *   `aappro_ALLOW_COMMENTS`
    *   `aappro_recaptcha_secretkey`
    *   `aappro_emailslist`
    *   `aappro_HIDE_OOS`
    *   `aappro_LOGGED_CUSTOMERS_ONLY`

#### Tabela zarejestrowanych haków

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Rejestruje zasoby CSS/JS, inicjalizuje globalne zmienne JS lub renderuje ukryte elementy dla funkcjonalności modułu. |
| `displayFooter` | Na dole każdej strony, przed `</body>`. | Może być używany do wstrzykiwania kodu HTML modala, pływających przycisków lub skryptów, które muszą zostać uruchomione po załadowaniu strony. |
| `displayProductExtraContent` | W bloku „dodatkowej treści” na stronach produktów (często poniżej opisu). | Renderuje formularz zapytania lub jego wyzwalacz, często jako pełny blok. |
| `displayProductAdditionalInfo` | W bloku informacji o produkcie, zazwyczaj w pobliżu ceny/przycisku „Dodaj do koszyka”. | Renderuje mniejszy wyzwalacz lub kompaktowy formularz bezpośrednio w głównych informacjach o produkcie. |
| `displayProductButtons` | W pobliżu przycisku „Dodaj do koszyka”. | Renderuje przycisk lub link do otwarcia formularza zapytania. |
| `displayProductTab` | Do dodawania nowego tytułu zakładki na stronie produktu. | Renderuje tytuł zakładki „Zadaj pytanie” lub „FAQ”. |
| `displayProductTabContent` | Do dodawania treści do nowej zakładki na stronie produktu. | Renderuje rzeczywisty formularz zapytania w dedykowanej zakładce produktu. |
| `displayReassurance` | W bloku zapewnienia (np. „bezpieczna płatność”, „bezpłatna wysyłka”). | Może być używany do wstrzykiwania małego linku lub ikony „Zadaj pytanie” w bloku zapewnienia. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny jest ładowany i jego zasoby multimedialne są ustawiane. | Rejestruje CSS i JS specyficzne dla modułu dla kontrolerów back-office (`AdminAapproForm`, `AdminAapproQuestion`). |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | (Nie jest bezpośrednio używany przez podstawową funkcję tego modułu, ale mógłby być używany do pytań uzupełniających po zakupie, jeśli zostanie rozszerzony). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Zapytaj o produkt - profesjonalne formularze kontaktowe”, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu. Zawsze upewnij się, że używasz najnowszej kompatybilnej wersji modułu, aby zapewnić optymalną wydajność i bezpieczeństwo.
