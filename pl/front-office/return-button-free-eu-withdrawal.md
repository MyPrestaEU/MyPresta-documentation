---
title: "Przycisk Zwrotu Darmowy - Wycofanie UE - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Przycisk Zwrotu Darmowy - Wycofanie UE” od MyPresta.eu."
sidebar:
  label: "Przycisk Zwrotu Darmowy - Wycofanie UE"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Return Button Free - EU Withdrawal na MyPresta.eu](https://mypresta.eu/modules/front-office-features/return-button-free-eu-withdrawal.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/return-button-free-eu-withdrawal/)
>
> ---


# Przycisk Zwrotu Darmowy - Wycofanie UE

## 1. Wymagania i Kompatybilność
-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 7.1 - 8.5
-   **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny Przewodnik Konfiguracji (Każde Ustawienie Pogrupowane według Ekranu)

### 2.1 Strona Konfiguracji Modułu (Panel Administracyjny > Moduły > Konfiguruj)
To jest główny ekran konfiguracji modułu, gdzie kontrolujesz jego ogólne zachowanie i wygląd.

#### Zakładka Ustawienia Ogólne

-   **Włącz Moduł:**
    -   **Co robi to ustawienie:** To jest główny przełącznik do aktywacji lub dezaktywacji funkcjonalności modułu w Twoim sklepie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Przycisk odstąpienia od umowy i funkcjonalność będą aktywne i widoczne dla klientów zgodnie z innymi ustawieniami.
        -   *Gdy wyłączony:* Funkcje modułu będą całkowicie ukryte w front office, a klienci nie będą mogli składać wniosków o odstąpienie od umowy za jego pośrednictwem.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Włączysz to, gdy będziesz gotowy zaoferować klientom opcję odstąpienia od umowy. Możesz tymczasowo wyłączyć to podczas konserwacji lub jeśli musisz wprowadzić znaczące zmiany w swojej polityce zwrotów.

-   **Wyświetl Przycisk Odstąpienia w:**
    -   **Co robi to ustawienie:** Określa, gdzie główny przycisk „Wniosek o Odstąpienie od Umowy” pojawia się w front office Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Nagłówek:* Przycisk pojawia się w górnej sekcji Twojej strony internetowej, często globalnie widoczny.
        -   *Lewa Kolumna:* Przycisk pojawia się w lewym pasku bocznym (jeśli Twój motyw go posiada).
        -   *Prawa Kolumna:* Przycisk pojawia się w prawym pasku bocznym (jeśli Twój motyw go posiada).
        -   *Strona Produktu:* Przycisk pojawia się na poszczególnych stronach produktów.
        -   *Stopka:* Przycisk pojawia się w dolnej sekcji Twojej strony internetowej.
    -   **Zalecana wartość:** Stopka (często dobra, nienachalna lokalizacja dla linków prawnych) lub Nagłówek (dla maksymalnej widoczności). Wybierz na podstawie układu Twojego motywu i Twoich preferencji co do widoczności.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby klienci łatwo znaleźli tę opcję, umieszczenie jej w Nagłówku lub Stopce jest powszechne. Jeśli wolisz, aby była mniej widoczna, ale nadal dostępna, kolumna może być odpowiednia.

-   **Zezwól na Wnioski o Odstąpienie od Umowy dla Gości:**
    -   **Co robi to ustawienie:** Kontroluje, czy klienci, którzy dokonali zakupu bez tworzenia konta, nadal mogą składać wniosek o odstąpienie od umowy.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Goście będą mogli uzyskać dostęp do formularza odstąpienia od umowy, podając numer referencyjny zamówienia i adres e-mail.
        -   *Gdy wyłączony:* Tylko zarejestrowani klienci, którzy są zalogowani na swoje konta, będą mogli składać wnioski o odstąpienie od umowy.
    -   **Zalecana wartość:** TAK (Wysoce zalecane dla zgodności z przepisami UE, ponieważ prawo do odstąpienia od umowy dotyczy wszystkich konsumentów, nie tylko zarejestrowanych).
    -   **Scenariusz / przykład dla sprzedawcy:** Włączenie tej opcji zapewnia zgodność z prawami konsumentów dla wszystkich klientów, niezależnie od ich metody zakupu, i pozwala uniknąć frustracji gości, którzy nie mogą znaleźć sposobu na odstąpienie od umowy.

-   **Statusy Zamówień Kwalifikujące do Odstąpienia od Umowy:**
    -   **Co robi to ustawienie:** Definiuje, które statusy zamówień sprawiają, że zamówienie kwalifikuje się do wniosku o odstąpienie od umowy. Na przykład, możesz zezwolić na odstąpienie od umowy tylko dla zamówień, które zostały „Dostarczone” lub „Wysłane”.
    -   **Efekt zmiany tego ustawienia:** Klienci zobaczą opcję odstąpienia od umowy tylko dla zamówień, które pasują do jednego z wybranych statusów w ich historii zamówień lub po wprowadzeniu numeru referencyjnego zamówienia gościa.
    -   **Zalecana wartość:** Wybierz statusy takie jak „Płatność zaakceptowana”, „Przygotowanie w toku”, „Wysłane”, „Dostarczone”. Unikaj statusów takich jak „Anulowane” lub „Zwrócone”, ponieważ odstąpienie od umowy nie ma tam zastosowania.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz zezwolić na odstąpienie od umowy dla zamówień, które są już przetworzone lub dostarczone, ale nie dla zamówień, które nadal oczekują na płatność lub zostały już anulowane.

-   **Statusy Zamówień dla Potwierdzenia Odstąpienia od Umowy:**
    -   **Co robi to ustawienie:** Określa, który status zamówienia powinien zostać automatycznie zastosowany do zamówienia po pomyślnym złożeniu wniosku o odstąpienie od umowy przez klienta. Pomaga to szybko zidentyfikować zamówienia z oczekującymi wnioskami o odstąpienie od umowy.
    -   **Efekt zmiany tego ustawienia:** Gdy klient złoży wniosek o odstąpienie od umowy, status zamówienia zmieni się na ten, który wybierzesz tutaj.
    -   **Zalecana wartość:** Utwórz nowy, odrębny status zamówienia, taki jak „Wniosek o odstąpienie od umowy” lub „Odstąpienie od umowy UE w toku” w ustawieniach statusów zamówień PrestaShop (w Parametry Sklepu > Ustawienia Zamówień > Statusy) i wybierz go tutaj.
    -   **Scenariusz / przykład dla sprzedawcy:** Ustawienie konkretnego statusu, takiego jak „Wniosek o odstąpienie od umowy”, pozwala Twojemu zespołowi obsługi klienta łatwo filtrować i zarządzać zamówieniami, które wymagają uwagi w procesie odstąpienia od umowy.

-   **Statusy Zamówień dla Zakończenia Odstąpienia od Umowy:**
    -   **Co robi to ustawienie:** Określa, który status zamówienia powinien zostać automatycznie zastosowany do zamówienia po przetworzeniu i zakończeniu odstąpienia od umowy przez Ciebie, sprzedawcę (np. wydaniu zwrotu pieniędzy).
    -   **Efekt zmiany tego ustawienia:** Po oznaczeniu wniosku o odstąpienie od umowy jako zakończonego w interfejsie administracyjnym modułu, status powiązanego zamówienia zostanie zaktualizowany do wybranego statusu.
    -   **Zalecana wartość:** Wybierz istniejący status, taki jak „Zwrócone” lub utwórz nowy, taki jak „Odstąpienie od umowy UE zakończone”.
    -   **Scenariusz / przykład dla sprzedawcy:** Po przetworzeniu zwrotu pieniędzy i zamknięciu sprawy odstąpienia od umowy, aktualizacja statusu zamówienia na „Zwrócone” zapewnia jasny zapis zarówno dla Ciebie, jak i dla klienta.

-   **Włącz Statystyki:**
    -   **Co robi to ustawienie:** Kontroluje, czy moduł zbiera anonimowe statystyki dotyczące jego użytkowania. Dane te pomagają deweloperowi modułu ulepszać moduł.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Moduł będzie wysyłał anonimowe dane użytkowania.
        -   *Gdy wyłączony:* Żadne dane użytkowania nie zostaną wysłane.
    -   **Zalecana wartość:** TAK (Pomaga ulepszyć moduł dla wszystkich).
    -   **Scenariusz / przykład dla sprzedawcy:** Włączasz to, aby przyczynić się do rozwoju modułu, lub wyłączasz, jeśli masz ścisłe zasady prywatności danych, które uniemożliwiają jakąkolwiek zewnętrzną transmisję danych.

#### Zakładka Informacje Prawne

-   **Okres Odstąpienia od Umowy (Dni):**
    -   **Co robi to ustawienie:** Definiuje liczbę dni kalendarzowych, w ciągu których klient ma prawo do odstąpienia od umowy, licząc od dnia otrzymania towaru.
    -   **Efekt zmiany tego ustawienia:** Moduł wyświetli ten okres klientom i użyje go wewnętrznie do wszelkich obliczeń dat lub sprawdzeń kwalifikowalności.
    -   **Zalecana wartość:** 14 (Jest to minimalny wymóg prawny w UE, ale możesz zaoferować dłuższy okres, jeśli chcesz).
    -   **Scenariusz / przykład dla sprzedawcy:** Ustawiasz to na 14 dni, aby być zgodnym z prawem UE. Jeśli oferujesz bardziej hojną politykę zwrotów, możesz ustawić to na 30 dni.

-   **Tekst Formularza Odstąpienia od Umowy:**
    -   **Co robi to ustawienie:** Pozwala dostosować tekst wprowadzający wyświetlany na górze formularza wniosku o odstąpienie od umowy. Jest to pole wielojęzyczne.
    -   **Efekt zmiany tego ustawienia:** Wprowadzony tekst pojawi się klientom, gdy uzyskają dostęp do formularza odstąpienia od umowy.
    -   **Zalecana wartość:** Podaj jasne, zwięzłe instrukcje lub krótkie wyjaśnienie procesu odstąpienia od umowy.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz dodać wiadomość taką jak: „Prosimy o wypełnienie tego formularza, aby skorzystać z prawa do odstąpienia od umowy. Masz 14 dni od otrzymania zamówienia na złożenie tego wniosku.”

-   **Tekst E-maila Potwierdzającego:**
    -   **Co robi to ustawienie:** Pozwala dostosować tekst zawarty w e-mailu potwierdzającym wysyłanym do klientów po złożeniu wniosku o odstąpienie od umowy. Jest to pole wielojęzyczne.
    -   **Efekt zmiany tego ustawienia:** Wprowadzony tekst będzie częścią e-maila, który otrzymają klienci, służąc jako trwały nośnik dowodu ich wniosku.
    -   **Zalecana wartość:** Uwzględnij ważne informacje, takie jak kolejne kroki, gdzie wysłać towar i wszelkie szczegółowe instrukcje dotyczące zwrotu.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz napisać: „Dziękujemy za wniosek o odstąpienie od umowy. Twój wniosek został otrzymany i zostanie wkrótce przetworzony. Prosimy o zwrot towaru na adres [Twój Adres Zwrotny] w ciągu 14 dni. Aby uzyskać więcej szczegółów, zapoznaj się z naszą polityką zwrotów.”

-   **Link do Polityki Odstąpienia od Umowy:**
    -   **Co robi to ustawienie:** Pozwala podać link do szczegółowej strony polityki odstąpienia od umowy lub zwrotów Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:** Na formularzu odstąpienia od umowy zostanie wyświetlony link, kierujący klientów do Twojej pełnej polityki.
    -   **Zalecana wartość:** Podaj URL do Twojej dedykowanej strony CMS dla zwrotów/odstąpień od umowy.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz stronę CMS zatytułowaną „Polityka Zwrotów i Reklamacji” pod adresem `twojasklep.com/content/zwroty-reklamacje`. Wprowadziłbyś ten URL tutaj.

#### 2.1.1 Tabela Szybkiego Odniesienia do Konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i Wpływ |
|---|---|---|---|
| **Zakładka Ustawienia Ogólne** | Włącz Moduł | TAK | Aktywuje/dezaktywuje funkcjonalność modułu. |
| | Wyświetl Przycisk Odstąpienia w | Stopka / Nagłówek | Ustawia lokalizację głównego przycisku odstąpienia. |
| | Zezwól na Wnioski o Odstąpienie od Umowy dla Gości | TAK | Umożliwia odstąpienie od umowy dla niezarejestrowanych klientów. |
| | Statusy Zamówień Kwalifikujące do Odstąpienia od Umowy | Płatność zaakceptowana, Wysłane, Dostarczone | Definiuje, które statusy zamówień zezwalają na wnioski o odstąpienie od umowy. |
| | Statusy Zamówień dla Potwierdzenia Odstąpienia od Umowy | „Wniosek o odstąpienie od umowy” (Niestandardowy) | Status zastosowany do zamówienia po złożeniu przez klienta. |
| | Statusy Zamówień dla Zakończenia Odstąpienia od Umowy | „Zwrócone” (Istniejący) / „Odstąpienie od umowy UE zakończone” (Niestandardowy) | Status zastosowany do zamówienia po zakończeniu przez sprzedawcę. |
| | Włącz Statystyki | TAK | Umożliwia zbieranie anonimowych danych użytkowania w celu ulepszenia modułu. |
| **Zakładka Informacje Prawne** | Okres Odstąpienia od Umowy (Dni) | 14 | Ustawia prawny okres na odstąpienie od umowy. |
| | Tekst Formularza Odstąpienia od Umowy | Możliwy do dostosowania | Tekst wprowadzający na formularzu odstąpienia od umowy. |
| | Tekst E-maila Potwierdzającego | Możliwy do dostosowania | Tekst zawarty w e-mailu potwierdzającym odstąpienie od umowy. |
| | Link do Polityki Odstąpienia od Umowy | URL Twojej strony CMS | Link do Twojej szczegółowej polityki zwrotów/odstąpienia od umowy. |

### 2.2 Dedykowane Ekrany Administracyjne i Widoki Kontrolera

#### Wnioski o Odstąpienie od Umowy (Panel Administracyjny > Moduły > Przycisk Zwrotu Darmowy > Wnioski o Odstąpienie od Umowy)
Ten dedykowany ekran administracyjny służy do zarządzania wszystkimi przychodzącymi wnioskami o odstąpienie od umowy od Twoich klientów.

-   **Nazwa Ekranu i Lokalizacja w Menu:** **Wnioski o Odstąpienie od Umowy** (znajduje się w głównym menu „Moduły”, a następnie w podmenu „Przycisk Zwrotu Darmowy”).
-   **Dostępne Akcje i Ustawienia:**
    -   **Tabela Listy:** Wyświetla kompleksową listę wszystkich wniosków o odstąpienie od umowy.
        -   **ID:** Unikalny identyfikator dla każdego wniosku.
        -   **Złożono:** Data i godzina złożenia wniosku.
        -   **Zamówienie:** Powiązany numer referencyjny zamówienia PrestaShop.
        -   **Imię, Nazwisko, E-mail:** Dane kontaktowe klienta.
        -   **Zakres:** Wskazuje, czy jest to odstąpienie od całego zamówienia (ta darmowa wersja obsługuje tylko odstąpienie od całego zamówienia).
        -   **Typ:** Typ odstąpienia od umowy (np. „Odstąpienie od umowy UE”).
        -   **Status:** Aktualny status wniosku o odstąpienie od umowy (np. „Oczekujące”, „Przetworzone”, „Anulowane”).
    -   **Wyświetl Szczegóły:** Kliknij dowolny wniosek na liście, aby otworzyć szczegółowy widok.
        -   Ten widok zawiera wszystkie informacje przesłane przez klienta, w tym szczegóły zamówienia, produkty i wszelkie dodatkowe uwagi.
        -   Możesz dodawać wewnętrzne uwagi, zmieniać status odstąpienia od umowy (np. z „Oczekujące” na „Przetworzone” lub „Anulowane”) i śledzić historię zmian.
        -   Ustawienie „Statusy Zamówień dla Zakończenia Odstąpienia od Umowy” (z głównej konfiguracji) zostanie zastosowane do powiązanego zamówienia, gdy oznaczysz odstąpienie od umowy jako zakończone tutaj.
    -   **Filtrowanie i Wyszukiwanie:** Możesz filtrować listę według statusu, nazwy klienta, ID zamówienia itp., aby szybko znaleźć konkretne wnioski.
-   **Efekt zmian:**
    -   **Zmiana Statusu:** Aktualizacja statusu wniosku o odstąpienie od umowy (np. na „Przetworzone” lub „Zakończone”) zaktualizuje rekord w module i, jeśli skonfigurowano, status powiązanego zamówienia PrestaShop. Pomaga to śledzić postępy i komunikować się z klientami.
    -   **Dodawanie Uwag:** Wewnętrzne uwagi są przeznaczone do celów referencyjnych Twojego zespołu i nie są widoczne dla klienta. Pomagają w dokumentowaniu komunikacji i działań podjętych w związku z każdym odstąpieniem od umowy.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Regularnie sprawdzaj ekran „Wnioski o Odstąpienie od Umowy” pod kątem nowych wniosków o statusie „Oczekujące”.
    2.  Kliknij wniosek, aby wyświetlić jego szczegóły.
    3.  Przejrzyj informacje o kliencie i powiązane zamówienie.
    4.  Komunikuj się z klientem w razie potrzeby (np. podaj instrukcje dotyczące wysyłki zwrotnej).
    5.  Po otrzymaniu i sprawdzeniu towaru, przetwórz zwrot pieniędzy w zarządzaniu zamówieniami PrestaShop.
    6.  Zaktualizuj status wniosku o odstąpienie od umowy w module na „Przetworzone” lub „Zakończone”. Spowoduje to również aktualizację głównego statusu zamówienia, jeśli skonfigurowano „Statusy Zamówień dla Zakończenia Odstąpienia od Umowy”.
    7.  Dodaj wszelkie istotne wewnętrzne uwagi dotyczące zwrotu, numerów śledzenia lub komunikacji.

## 3. Rozwiązywanie Problemów dla Sprzedawców i Często Zadawane Pytania (FAQ)

-   **P: Przycisk odstąpienia od umowy nie wyświetla się w moim sklepie.**
    -   **O:** Najpierw sprawdź, czy moduł jest „Włączony” w jego konfiguracji. Następnie zweryfikuj, czy wybrałeś lokalizację „Wyświetl Przycisk Odstąpienia w” (np. Stopka, Nagłówek). Jeśli Twój motyw jest mocno dostosowany, może nie być poprawnie podłączony. Spróbuj wybrać inną lokalizację wyświetlania. Upewnij się również, że pamięć podręczna Smarty została wyczyszczona (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).
-   **P: Klienci składają wnioski o odstąpienie od umowy, ale status zamówienia się nie zmienia.**
    -   **O:** Przejdź do konfiguracji modułu i sprawdź ustawienie „Statusy Zamówień dla Potwierdzenia Odstąpienia od Umowy”. Upewnij się, że wybrałeś tam odpowiedni status zamówienia. Jeśli utworzyłeś nowy status, upewnij się, że jest on poprawnie skonfigurowany w PrestaShop (Parametry Sklepu > Ustawienia Zamówień > Statusy).
-   **P: Czy klienci mogą odstąpić od pojedynczych produktów z zamówienia za pomocą tego modułu?**
    -   **O:** Nie, darmowy moduł „Przycisk Zwrotu Darmowy - Wycofanie UE” jest przeznaczony wyłącznie do **odstąpienia od całego zamówienia**, zgodnie z dyrektywą UE. Jeśli potrzebujesz obsługiwać częściowe zwroty dla pojedynczych produktów, potrzebowałbyś bardziej zaawansowanego modułu do zarządzania zwrotami.
-   **P: Moduł jest zainstalowany, ale tekst w formularzu lub e-mailu jest w złym języku lub wygląda ogólnie.**
    -   **O:** Ustawienia „Tekst Formularza Odstąpienia od Umowy” i „Tekst E-maila Potwierdzającego” to pola wielojęzyczne. Upewnij się, że wprowadziłeś żądany tekst dla każdego języka włączonego w Twoim sklepie. Możesz przełączać się między językami za pomocą ikony flagi obok pola tekstowego w konfiguracji modułu.
-   **P: Zaktualizowałem moduł i teraz coś wygląda nie tak. Co powinienem zrobić?**
    -   **O:** Po każdej aktualizacji modułu dobrą praktyką jest wyczyszczenie pamięci podręcznej PrestaShop. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Jeśli problem nadal występuje, sprawdź ustawienia konfiguracji modułu, aby upewnić się, że są one nadal takie, jakich oczekujesz.

## 4. Przewodnik dla Deweloperów i Webmasterów (Architektura Techniczna i Mapa Kodu)

Ta sekcja zawiera szczegółowy przegląd struktury technicznej modułu „Przycisk Zwrotu Darmowy - Wycofanie UE”, przeznaczony dla deweloperów i webmasterów.

### 4.1 Przegląd Architektury
Moduł stosuje standardowy wzorzec PrestaShop MVC (Model-View-Controller). Wykorzystuje `ModuleFrontController` do interakcji z front-office i `AdminController` do zarządzania back-office. `ObjectModel` jest używany do trwałego przechowywania danych związanych z wnioskami o odstąpienie od umowy. Kluczowe usługi i klasy pomocnicze hermetyzują logikę biznesową i zapewniają kompatybilność między wersjami PrestaShop. Moduł integruje się z różnymi hookami PrestaShop, aby wyświetlać swoją funkcjonalność.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office
Te kontrolery obsługują interakcje z klientem związane z wnioskami o odstąpienie od umowy.

-   `rbfree/controllers/front/confirm.php`
    *   Nazwa klasy: `RbfConfirmModuleFrontController` (rozszerza `RbfModuleFrontController`)
    *   Odpowiedzialność: Wyświetla ostatni krok potwierdzenia formularza odstąpienia od umowy, umożliwiając klientowi przegląd i przesłanie wniosku. Obsługuje przesłanie POST w celu utworzenia nowego wpisu `RbfWithdrawal`.
-   `rbfree/controllers/front/form.php`
    *   Nazwa klasy: `RbfFormModuleFrontController` (rozszerza `RbfModuleFrontController`)
    *   Odpowiedzialność: Renderuje początkowy formularz wniosku o odstąpienie od umowy. Obsługuje walidację danych wejściowych dla numeru referencyjnego zamówienia, adresu e-mail i danych klienta.
-   `rbfree/controllers/front/print.php`
    *   Nazwa klasy: `RbfPrintModuleFrontController` (rozszerza `RbfModuleFrontController`)
    *   Odpowiedzialność: Zapewnia wersję formularza wniosku o odstąpienie od umowy do druku, zazwyczaj po przesłaniu, dla dokumentacji klienta.
-   `rbfree/controllers/front/RbfModuleFrontController.php`
    *   Nazwa klasy: `RbfModuleFrontController` (rozszerza `ModuleFrontController`)
    *   Odpowiedzialność: Klasa bazowa dla wszystkich kontrolerów front-office modułu, zapewniająca wspólne narzędzia, kontrole bezpieczeństwa i przypisania zmiennych Smarty.
-   `rbfree/controllers/front/status.php`
    *   Nazwa klasy: `RbfStatusModuleFrontController` (rozszerza `RbfModuleFrontController`)
    *   Odpowiedzialność: Wyświetla aktualny status konkretnego wniosku o odstąpienie od umowy klientowi.
-   `rbfree/controllers/front/track.php`
    *   Nazwa klasy: `RbfTrackModuleFrontController` (rozszerza `RbfModuleFrontController`)
    *   Odpowiedzialność: Umożliwia klientom (w tym gościom) śledzenie ich wniosku o odstąpienie od umowy poprzez wprowadzenie numeru referencyjnego zamówienia i adresu e-mail.

#### Kontrolery Administracyjne Back-Office
Te kontrolery zarządzają interfejsem administracyjnym dla wniosków o odstąpienie od umowy.

-   `rbfree/controllers/admin/AdminRbfWithdrawalController.php`
    *   Nazwa klasy: `AdminRbfWithdrawalController` (rozszerza `ModuleAdminController`)
    *   Nazwa zakładki: „Wnioski o Odstąpienie od Umowy” (w „Moduły > Przycisk Zwrotu Darmowy”)
    *   Zarządzana encja: `RbfWithdrawal`
    *   Odpowiedzialność: Zapewnia interfejs CRUD (Create, Read, Update, Delete) do zarządzania wnioskami o odstąpienie od umowy. Wyświetla listę wniosków, umożliwia przeglądanie szczegółowych informacji, aktualizację statusu i dodawanie notatek. Obsługuje przesyłanie formularzy dla zmian statusu i notatek.

### 4.3 Klasy Rdzenia i Modele (`classes/`)

-   `rbfree/classes/RbfCompatibility.php`
    *   Nazwa klasy: `RbfCompatibility`
    *   Odpowiedzialność: Zapewnia metody pomocnicze do zapewnienia kompatybilności między różnymi wersjami PrestaShop (np. obsługa różnic w metodach `Context` lub `Tools`).
-   `rbfree/classes/RbfSecurity.php`
    *   Nazwa klasy: `RbfSecurity`
    *   Odpowiedzialność: Zawiera metody pomocnicze związane z bezpieczeństwem, takie jak generowanie i walidacja tokenów, w celu ochrony formularzy przed atakami CSRF.
-   `rbfree/classes/RbfSelfHeal.php`
    *   Nazwa klasy: `RbfSelfHeal`
    *   Odpowiedzialność: Implementuje logikę samonaprawy lub kontroli diagnostycznych, zapewniając integralność modułu i spójność danych.
-   `rbfree/classes/RbfStatsService.php`
    *   Nazwa klasy: `RbfStatsService`
    *   Odpowiedzialność: Obsługuje zbieranie i przesyłanie anonimowych statystyk użytkowania, jeśli jest to włączone przez sprzedawcę.
-   `rbfree/classes/RbfWithdrawal.php`
    *   Nazwa klasy: `RbfWithdrawal` (rozszerza `ObjectModel`)
    *   Tabela bazy danych: `ps_rbf_withdrawal`
    *   Pola `$definition`: Definiuje strukturę wniosku o odstąpienie od umowy, w tym `id_order`, `id_customer`, `firstname`, `lastname`, `email`, `status`, `date_add`, `date_upd` itp.
    *   Kluczowe metody publiczne: `add()`, `update()`, `delete()`, metody do pobierania szczegółów odstąpienia od umowy, zarządzania przejściami statusu.
-   `rbfree/classes/RbfWithdrawalAttachment.php`
    *   Nazwa klasy: `RbfWithdrawalAttachment` (rozszerza `ObjectModel`)
    *   Tabela bazy danych: `ps_rbf_withdrawal_attachment`
    *   Pola `$definition`: Przechowuje informacje o plikach dołączonych do wniosku o odstąpienie od umowy (jeśli wersja Pro to obsługuje).
    *   Kluczowe metody publiczne: Metody do zarządzania załącznikami.
-   `rbfree/classes/RbfWithdrawalHistory.php`
    *   Nazwa klasy: `RbfWithdrawalHistory` (rozszerza `ObjectModel`)
    *   Tabela bazy danych: `ps_rbf_withdrawal_history`
    *   Pola `$definition`: Rejestruje zmiany statusu wniosku o odstąpienie od umowy lub inne kluczowe atrybuty.
    *   Kluczowe metody publiczne: `add()`, metody do pobierania historii.
-   `rbfree/classes/RbfWithdrawalNote.php`
    *   Nazwa klasy: `RbfWithdrawalNote` (rozszerza `ObjectModel`)
    *   Tabela bazy danych: `ps_rbf_withdrawal_note`
    *   Pola `$definition`: Przechowuje wewnętrzne notatki dodane przez administratorów do wniosku o odstąpienie od umowy.
    *   Kluczowe metody publiczne: `add()`, metody do pobierania notatek.
-   `rbfree/classes/RbfWithdrawalProduct.php`
    *   Nazwa klasy: `RbfWithdrawalProduct` (rozszerza `ObjectModel`)
    *   Tabela bazy danych: `ps_rbf_withdrawal_product`
    *   Pola `$definition`: Przechowuje szczegóły produktów zawartych we wniosku o odstąpienie od umowy.
    *   Kluczowe metody publiczne: Metody do zarządzania powiązanymi produktami.
-   `rbfree/classes/RbfWithdrawalService.php`
    *   Nazwa klasy: `RbfWithdrawalService`
    *   Odpowiedzialność: Hermetyzuje podstawową logikę biznesową do obsługi wniosków o odstąpienie od umowy, taką jak tworzenie nowych wniosków, aktualizacja statusów zamówień, wysyłanie e-maili i walidacja kwalifikowalności.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `rbfree/views/js/admin-order-state-picker.js`
    *   Zakres: Back-office
    *   Szczegóły: Zarządza interaktywnym wyborem statusów zamówień w konfiguracji modułu, prawdopodobnie dla ustawień „Statusy Zamówień Kwalifikujące do Odstąpienia od Umowy/Potwierdzenia/Zakończenia”.
-   `rbfree/views/js/front.js`
    *   Zakres: Front-office
    *   Szczegóły: Zawiera ogólny JavaScript front-office dla modułu. Może to obejmować walidację formularzy, przesyłanie AJAX dla formularzy odstąpienia od umowy, dynamiczne ładowanie treści lub interakcje z przyciskiem odstąpienia od umowy.
-   `rbfree/views/js/order-history.js`
    *   Zakres: Front-office (Konto Klienta > Historia Zamówień)
    *   Szczegóły: Specjalnie obsługuje integrację linku/przycisku odstąpienia od umowy na stronie historii zamówień klienta, potencjalnie dodając słuchaczy zdarzeń do dynamicznego pokazywania/ukrywania opcji na podstawie statusu zamówienia.

### 4.5 Arkusze Stylów CSS (`views/css/`)

-   `rbfree/views/css/admin-config.css`
    *   Zakres: Back-office (Konfiguracja Modułu)
    *   Szczegóły: Style dla głównej strony konfiguracji modułu (`configure.tpl`), zapewniające spójny wygląd w panelu administracyjnym PrestaShop.
-   `rbfree/views/css/admin-dashboard.css`
    *   Zakres: Back-office (panel `AdminRbfWithdrawalController`)
    *   Szczegóły: Stylizacja widoku panelu wniosków o odstąpienie od umowy, w tym układów tabel, wskaźników statusu i ogólnego układu.
-   `rbfree/views/css/admin-order-state-picker.css`
    *   Zakres: Back-office
    *   Szczegóły: Style dla interfejsu wyboru statusu zamówienia używanego w konfiguracji modułu.
-   `rbfree/views/css/admin-pro-teaser.css`
    *   Zakres: Back-office
    *   Szczegóły: Stylizacja elementów zapowiedzi wersji „Pro” w interfejsie administracyjnym darmowego modułu.
-   `rbfree/views/css/admin-searchtool.css`
    *   Zakres: Back-office
    *   Szczegóły: Style dla narzędzi wyszukiwania i filtrowania na liście administracyjnej odstąpień od umowy.
-   `rbfree/views/css/admin-withdrawal-view.css`
    *   Zakres: Back-office (widok `AdminRbfWithdrawalController`)
    *   Szczegóły: Stylizacja szczegółowego widoku pojedynczego wniosku o odstąpienie od umowy w panelu administracyjnym, w tym notatek, historii i list produktów.
-   `rbfree/views/css/front-classic.css`
    *   Zakres: Front-office (motyw Classic)
    *   Szczegóły: Specyficzne dostosowania stylizacji dla klasycznego motywu PrestaShop, zapewniające spójność wizualną z projektem motywu.
-   `rbfree/views/css/front-hummingbird.css`
    *   Zakres: Front-office (motyw Hummingbird)
    *   Szczegóły: Specyficzne dostosowania stylizacji dla motywu PrestaShop Hummingbird, zapewniające spójność wizualną z projektem motywu.
-   `rbfree/views/css/front.css`
    *   Zakres: Front-office
    *   Szczegóły: Ogólna stylizacja front-office dla formularzy odstąpienia od umowy, przycisków i stron statusu, stosowana we wszystkich motywach.

### 4.6 Struktura Szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)
-   `rbfree/views/templates/hook/account-link-classic.tpl`
    *   Hook: `displayCustomerAccount` (lub podobny)
    *   Wyjście: Link w panelu konta klienta dla motywu Classic.
-   `rbfree/views/templates/hook/account-link-hummingbird.tpl`
    *   Hook: `displayCustomerAccount` (lub podobny)
    *   Wyjście: Link w panelu konta klienta dla motywu Hummingbird.
-   `rbfree/views/templates/hook/button-classic.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (lub podobny)
    *   Wyjście: Główny przycisk odstąpienia od umowy dla motywu Classic.
-   `rbfree/views/templates/hook/button-hummingbird.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (lub podobny)
    *   Wyjście: Główny przycisk odstąpienia od umowy dla motywu Hummingbird.
-   `rbfree/views/templates/hook/button.tpl`
    *   Hook: `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (lub podobny)
    *   Wyjście: Ogólny główny przycisk odstąpienia od umowy, używany jako fallback lub dla wspólnych elementów.
-   `rbfree/views/templates/hook/order-detail-classic.tpl`
    *   Hook: `displayOrderDetail` (lub podobny)
    *   Wyjście: Link/przycisk odstąpienia od umowy na stronie szczegółów zamówienia dla motywu Classic.
-   `rbfree/views/templates/hook/order-detail-hummingbird.tpl`
    *   Hook: `displayOrderDetail` (lub podobny)
    *   Wyjście: Link/przycisk odstąpienia od umowy na stronie szczegółów zamówienia dla motywu Hummingbird.
-   `rbfree/views/templates/hook/order-detail.tpl`
    *   Hook: `displayOrderDetail` (lub podobny)
    *   Wyjście: Ogólny link/przycisk odstąpienia od umowy na stronie szczegółów zamówienia.
-   `rbfree/views/templates/hook/order-withdrawal-notice.tpl`
    *   Hook: `displayAdminOrder` (lub podobny)
    *   Wyjście: Powiadomienie lub podsumowanie statusu odstąpienia od umowy na stronie widoku zamówienia w Back Office.

#### Szablony administracyjne (`views/templates/admin/`)
-   `rbfree/views/templates/admin/configure.tpl`
    *   Używane przez: `getContent()` w `rbfree/index.php`
    *   Wyjście: Główny formularz konfiguracji modułu w Back Office.
-   `rbfree/views/templates/admin/dashboard.tpl`
    *   Używane przez: `AdminRbfWithdrawalController`
    *   Wyjście: Widok panelu wyświetlający wszystkie wnioski o odstąpienie od umowy.
-   `rbfree/views/templates/admin/order-state-picker.tpl`
    *   Używane przez: Konfigurację modułu
    *   Wyjście: Interaktywny widżet wyboru statusu zamówienia.
-   `rbfree/views/templates/admin/order-withdrawal-notice.tpl`
    *   Używane przez: hook `displayAdminOrder`
    *   Wyjście: Powiadomienie o statusie odstąpienia od umowy na stronie widoku zamówienia w Back Office.
-   `rbfree/views/templates/admin/pro-teaser-dashboard-intro.tpl`
    *   Używane przez: `AdminRbfWithdrawalController`
    *   Wyjście: Wprowadzająca zapowiedź wersji Pro na panelu.
-   `rbfree/views/templates/admin/pro-teaser-dashboard.tpl`
    *   Używane przez: `AdminRbfWithdrawalController`
    *   Wyjście: Ogólna zapowiedź wersji Pro na panelu.
-   `rbfree/views/templates/admin/pro-teaser-exclusions.tpl`
    *   Używane przez: Konfigurację modułu
    *   Wyjście: Zapowiedź funkcji wersji Pro związanych z wykluczeniami.
-   `rbfree/views/templates/admin/pro-teaser-order-states.tpl`
    *   Używane przez: Konfigurację modułu
    *   Wyjście: Zapowiedź funkcji wersji Pro związanych ze statusami zamówień.
-   `rbfree/views/templates/admin/pro-teaser-withdrawal-scope.tpl`
    *   Używane przez: Konfigurację modułu
    *   Wyjście: Zapowiedź funkcji wersji Pro związanych z zakresem odstąpienia od umowy.
-   `rbfree/views/templates/admin/pro-teaser.tpl`
    *   Używane przez: Różne sekcje administracyjne
    *   Wyjście: Ogólna zapowiedź wersji Pro.
-   `rbfree/views/templates/admin/updates.tpl`
    *   Używane przez: Konfigurację modułu
    *   Wyjście: Wyświetla informacje o aktualizacjach modułu.
-   `rbfree/views/templates/admin/view.tpl`
    *   Używane przez: `AdminRbfWithdrawalController`
    *   Wyjście: Strona szczegółowego widoku pojedynczego wniosku o odstąpienie od umowy w Back Office.

#### Szablony front-office (`views/templates/front/`)
-   `rbfree/views/templates/front/confirm_step.tpl`
    *   Używane przez: `RbfConfirmModuleFrontController`
    *   Wyjście: Drugi krok formularza odstąpienia od umowy, do potwierdzenia.
-   `rbfree/views/templates/front/error.tpl`
    *   Używane przez: Różne kontrolery front-office
    *   Wyjście: Ogólna strona z komunikatem o błędzie.
-   `rbfree/views/templates/front/form.tpl`
    *   Używane przez: `RbfFormModuleFrontController`
    *   Wyjście: Początkowy formularz wniosku o odstąpienie od umowy.
-   `rbfree/views/templates/front/print.tpl`
    *   Używane przez: `RbfPrintModuleFrontController`
    *   Wyjście: Wersja formularza odstąpienia od umowy do druku.
-   `rbfree/views/templates/front/status.tpl`
    *   Używane przez: `RbfStatusModuleFrontController`
    *   Wyjście: Strona wyświetlająca status konkretnego wniosku o odstąpienie od umowy.
-   `rbfree/views/templates/front/success.tpl`
    *   Używane przez: `RbfConfirmModuleFrontController`
    *   Wyjście: Komunikat o sukcesie po złożeniu wniosku o odstąpienie od umowy.
-   `rbfree/views/templates/front/track.tpl`
    *   Używane przez: `RbfTrackModuleFrontController`
    *   Wyjście: Formularz dla klientów do śledzenia ich wniosku o odstąpienie od umowy.

### 4.7 Schemat Bazy Danych i Mapa Hooków

#### Tabele Bazy Danych
-   `ps_rbf_withdrawal`: Przechowuje główne szczegóły wniosku o odstąpienie od umowy (id, id_order, id_customer, status, daty, informacje o kliencie).
-   `ps_rbf_withdrawal_attachment`: Przechowuje szczegóły wszelkich załączników do wniosku o odstąpienie od umowy.
-   `ps_rbf_withdrawal_history`: Przechowuje dziennik zmian statusu i innych aktualizacji dla każdego wniosku o odstąpienie od umowy.
-   `ps_rbf_withdrawal_note`: Przechowuje wewnętrzne notatki dodane przez administratorów do wniosku o odstąpienie od umowy.
-   `ps_rbf_withdrawal_product`: Przechowuje szczegóły produktów zawartych we wniosku o odstąpienie od umowy.
-   `ps_configuration`: Ustawienia modułu są przechowywane tutaj z kluczami takimi jak `RBFREE_ENABLED`, `RBFREE_BUTTON_HOOK`, `RBFREE_ALLOW_GUEST` itp.

#### Tabela Zarejestrowanych Hooków

| Nazwa Hooka | Czas Wykonania | Cel Techniczny |
|---|---|---|
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykiwanie CSS/JS lub renderowanie przycisku odstąpienia od umowy, jeśli skonfigurowano. |
| `displayLeftColumn` | W lewym pasku bocznym odpowiednich stron. | Renderowanie przycisku odstąpienia od umowy, jeśli skonfigurowano. |
| `displayRightColumn` | W prawym pasku bocznym odpowiednich stron. | Renderowanie przycisku odstąpienia od umowy, jeśli skonfigurowano. |
| `displayFooter` | W sekcji stopki każdej strony. | Renderowanie przycisku odstąpienia od umowy, jeśli skonfigurowano. |
| `displayProductButtons` | Na stronie produktu, w pobliżu przycisku dodawania do koszyka. | Renderowanie przycisku odstąpienia od umowy, jeśli skonfigurowano. |
| `displayCustomerAccount` | W panelu „Moje Konto” klienta. | Dodanie linku do formularza odstąpienia od umowy. |
| `displayOrderDetail` | Na stronie szczegółów zamówienia klienta. | Dodanie linku/przycisku do inicjowania odstąpienia od umowy dla tego konkretnego zamówienia. |
| `displayAdminOrder` | Na stronie widoku zamówienia w Back Office. | Wyświetlanie powiadomienia lub podsumowania wszelkich powiązanych wniosków o odstąpienie od umowy. |
| `actionOrderStatusUpdate` | Gdy status zamówienia zostanie zmieniony. | Potencjalne wyzwalanie działań, takich jak aktualizacja statusu odstąpienia od umowy lub wysyłanie powiadomień. |
| `actionFrontControllerSetMedia` | Przed renderowaniem szablonu przez kontroler front-office. | Dodawanie do kolejki plików CSS i JavaScript front-office. |
| `actionAdminControllerSetMedia` | Przed renderowaniem szablonu przez kontroler administracyjny. | Dodawanie do kolejki plików CSS i JavaScript back-office. |
| `actionModuleInstall` | Podczas instalacji modułu. | Tworzenie tabel bazy danych, ustawianie domyślnej konfiguracji. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Usuwanie tabel bazy danych, usuwanie konfiguracji. |

## 5. Oficjalne Wsparcie i Aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Przycisk Zwrotu Darmowy - Wycofanie UE”, prosimy o zapoznanie się z kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
