---
title: "Geolocation pro - waluta i język według kraju - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Geolocation pro - waluta i język według kraju” od MyPresta.eu."
sidebar:
  label: "Geolocation pro - waluta i język według kraju - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Geolocation pro - currency and language by country na MyPresta.eu](https://mypresta.eu/modules/front-office-features/geolocation-pro-currency-and-language-by-country.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/geolocation-pro-currency-and-language-by-country/)
>
> ---


# Geolocation pro - waluta i język według kraju

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane i dostępne w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Geolocation pro - waluta i język według kraju)

Jest to główny ekran konfiguracji, na którym włączasz lub wyłączasz podstawową funkcjonalność modułu i uzyskujesz dostęp do narzędzi diagnostycznych.

-   **Włącz Geolocation Pro:**
    -   **Co robi to ustawienie:** Jest to główny przełącznik dla całego modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł będzie aktywnie wykrywać lokalizacje klientów i stosować zdefiniowane reguły waluty i języka.
        -   *Gdy wyłączone:* Moduł będzie nieaktywny, a Twój sklep powróci do domyślnych ustawień waluty i języka dla wszystkich odwiedzających, niezależnie od ich lokalizacji.
    -   **Zalecana wartość:** TAK (aby korzystać z funkcji modułu).
    -   **Scenariusz/przykład dla sprzedawcy:** Skończyłeś konfigurować wszystkie swoje reguły i jesteś gotowy do uruchomienia spersonalizowanych doświadczeń. Włącz ten przełącznik. Jeśli musisz tymczasowo wyłączyć funkcję w celu konserwacji, wyłącz ją.
-   **Pokaż baner z wyborem kraju:**
    -   **Co robi to ustawienie:** Określa, czy mały baner lub wyskakujące okienko pojawi się, aby poinformować klientów o wykrytym kraju i zaoferować im możliwość jego zmiany.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Baner pojawi się (zazwyczaj na górze lub na dole ekranu) pokazując wykryty kraj i potencjalnie umożliwiając klientowi ręczne nadpisanie wykrytej lokalizacji, waluty lub języka. Może to być przydatne dla klientów korzystających z VPN-ów lub tych, którzy preferują ustawienia innego regionu.
        -   *Gdy wyłączone:* Nie zostanie wyświetlony żaden baner. Moduł cicho zastosuje reguły na podstawie wykrywania IP.
    -   **Zalecana wartość:** TAK (początkowo, aby dać klientom kontrolę, a następnie rozważ NIE, jeśli wolisz całkowicie płynne doświadczenie i ufasz wykrywaniu IP).
    -   **Scenariusz/przykład dla sprzedawcy:** Klient z USA odwiedza Twój sklep, a moduł poprawnie wykrywa jego lokalizację. Jeśli to ustawienie jest włączone, baner może powiedzieć „Przeglądasz z Stanów Zjednoczonych. [Zmień kraj?]” Daje im to szansę na poprawienie, jeśli używają VPN-u lub wolą robić zakupy z innego regionu.
-   **Diagnostyka i narzędzia:**
    -   **Co robi to ustawienie:** Ta sekcja zawiera narzędzia do testowania funkcjonalności modułu i weryfikacji wykrywania IP. Nie jest to ustawienie do zmiany, ale narzędzie.
    -   **Efekt zmiany tego ustawienia:** Kliknięcie narzędzi diagnostycznych otworzy nowe widoki lub wyskakujące okienka, które pokażą informacje o Twoim aktualnym adresie IP, wykrytym kraju i sposobie, w jaki moduł zastosowałby reguły.
    -   **Zalecana wartość:** Używaj tego zawsze, gdy konfigurujesz nowe reguły lub rozwiązujesz problemy.
    -   **Scenariusz/przykład dla sprzedawcy:** Utworzyłeś regułę dla Niemiec. Możesz użyć narzędzia diagnostycznego, aby zasymulować wizytę z Niemiec i sprawdzić, czy zastosowano poprawną walutę i język, upewniając się, że Twoje reguły działają zgodnie z oczekiwaniami.

### 2.2 Dedykowany ekran administracyjny: Reguły Geo (Panel administracyjny > Moduły > Geolocation pro > Reguły Geo)

Ten ekran pozwala definiować i zarządzać podstawowymi regułami waluty i języka na podstawie kraju.

-   **Nazwa ekranu i lokalizacja w menu:** **Panel administracyjny > Moduły > Geolocation pro - waluta i język według kraju > Reguły Geo** (lub podobna ścieżka w głównym menu modułu).
-   **Dostępne akcje i ustawienia:**
    -   **Tabela listy:** Wyświetla wszystkie istniejące reguły geo, pokazując kraj, przypisaną walutę i przypisany język.
    -   **Dodaj nową regułę geo:** Przycisk do tworzenia nowej reguły.
    -   **Akcje Edytuj/Usuń:** Ikony obok każdej reguły do modyfikacji lub usunięcia.
-   **Efekt zmian:**
    -   **Dodanie nowej reguły:** Po dodaniu reguły (np. dla „Niemiec” do używania „EUR” i „niemieckiego”), każdy odwiedzający wykryty jako pochodzący z Niemiec będzie miał automatycznie ustawioną walutę i język na te wartości.
    -   **Edycja reguły:** Modyfikacja istniejącej reguły natychmiast zmieni zachowanie modułu dla odwiedzających z tego konkretnego kraju.
    -   **Usunięcie reguły:** Usunięcie reguły oznacza, że odwiedzający z tego kraju nie będą już mieli przypisanej konkretnej waluty ani języka przez ten moduł i powrócą do domyślnych ustawień Twojego sklepu.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Zidentyfikuj rynki docelowe:** Zdecyduj, które kraje chcesz targetować z konkretnymi walutami i językami.
    2.  **Upewnij się, że waluty/języki są włączone:** Upewnij się, że waluty i języki, które chcesz przypisać, są już włączone w Twoim sklepie PrestaShop (Panel administracyjny > Lokalizacja > Waluty / Języki).
    3.  **Utwórz reguły:** Dla każdego kraju kliknij „Dodaj nową regułę geo”, wybierz kraj z listy rozwijanej, a następnie wybierz żądaną walutę i język. Zapisz regułę.
    4.  **Testuj za pomocą diagnostyki:** Użyj wbudowanych narzędzi diagnostycznych modułu, aby sprawdzić, czy Twoje reguły działają zgodnie z przeznaczeniem.

### 2.3 Dedykowany ekran administracyjny: Reguły Językowe (Panel administracyjny > Moduły > Geolocation pro > Reguły Językowe)

Ten ekran wydaje się być duplikatem lub alternatywnym interfejsem do zarządzania regułami specyficznymi dla języka, potencjalnie oferując bardziej szczegółową kontrolę lub inny widok. Biorąc pod uwagę opis modułu, ekran „Reguły Geo” jest prawdopodobnie głównym interfejsem do przypisywania na podstawie kraju. Ten ekran może służyć do bardziej zaawansowanych, specyficznych dla języka nadpisań, które nie są bezpośrednio związane z krajem.

-   **Nazwa ekranu i lokalizacja w menu:** **Panel administracyjny > Moduły > Geolocation pro - waluta i język według kraju > Reguły Językowe** (lub podobna ścieżka).
-   **Dostępne akcje i ustawienia:**
    -   **Tabela listy:** Pokazuje istniejące reguły językowe.
    -   **Dodaj nową regułę językową:** Przycisk do tworzenia nowej reguły.
    -   **Akcje Edytuj/Usuń:** Ikony do modyfikacji lub usunięcia reguł.
-   **Efekt zmian:** Te reguły prawdopodobnie nadpiszą lub uzupełnią reguły językowe oparte na kraju. Na przykład, możesz mieć ogólną regułę dla „angielskiego” dla wszystkich nieokreślonych krajów, a następnie użyć tego ekranu dla wyjątków lub specyficznych zachowań językowych.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj tego ekranu, jeśli musisz zarządzać ustawieniami języka niezależnie od reguł geo specyficznych dla kraju, lub jeśli napotkasz scenariusze, w których reguła kraju nie jest wystarczająca do obsługi języka. W przeciwnym razie skup się na ekranie „Reguły Geo”.

### 2.4 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz Geolocation Pro | TAK | Główny przełącznik funkcjonalności modułu. TAK aktywuje wykrywanie waluty/języka na podstawie kraju. |
| | Pokaż baner z wyborem kraju | TAK | Wyświetla baner informujący klientów o wykrytym kraju i umożliwiający ręczne nadpisanie. |
| | Diagnostyka i narzędzia | N/A | Narzędzie do testowania wykrywania IP i stosowania reguł. |
| **Reguły Geo** | Dodaj/Edytuj regułę Geo (Kraj, Waluta, Język) | N/A | Definiuje, która waluta i język są automatycznie ustawiane dla odwiedzających z określonego kraju. |
| **Reguły Językowe** | Dodaj/Edytuj regułę językową | N/A | (Potencjalnie) Definiuje nadpisania językowe lub specyficzne zachowania językowe, być może niezależnie od kraju. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci nadal widzą niewłaściwą walutę/język, mimo że ustawiłem reguły. Co jest nie tak?**
O1:

-   **Czy moduł jest włączony?** Sprawdź dwukrotnie ustawienie „Włącz Geolocation Pro” na głównej stronie konfiguracji.
-   **Czy Twoje reguły są poprawne?** Przejdź do „Reguł Geo” i upewnij się, że kraj, waluta i język są poprawnie przypisane.
-   **Czy waluty/języki są włączone w PrestaShop?** Upewnij się, że waluty i języki, które próbujesz przypisać, są aktywne w Twoim PrestaShop (Lokalizacja > Waluty / Języki).
-   **Wyczyść pamięć podręczną przeglądarki:** Czasami Twoja przeglądarka może buforować stare ustawienia. Poproś klientów o wyczyszczenie pamięci podręcznej przeglądarki lub wypróbowanie okna incognito.
-   **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
-   **Testuj za pomocą diagnostyki:** Użyj wbudowanych narzędzi diagnostycznych modułu, aby zasymulować wizytę z określonego kraju i zobaczyć, jaką walutę/język zastosuje. Pomaga to ustalić, czy problem dotyczy wykrywania, czy stosowania reguł.

**P2: Moduł wykrywa niewłaściwy kraj dla niektórych klientów. Dlaczego?**
O2:

-   **VPN-y i serwery proxy:** Klienci korzystający z wirtualnych sieci prywatnych (VPN) lub serwerów proxy będą wydawać się przeglądać z lokalizacji swojego VPN/proxy, a nie z ich rzeczywistej fizycznej lokalizacji. Moduł opiera się na wykrywaniu adresu IP, który może być fałszowany.
-   **Dokładność bazy danych IP:** Bazy danych geolokalizacyjnych są zazwyczaj bardzo dokładne, ale nie w 100% doskonałe. Niektóre zakresy IP mogą być błędnie zidentyfikowane.
-   **„Pokaż baner z wyborem kraju”:** Jeśli to ustawienie jest włączone, klienci mogą ręcznie poprawić wykryty kraj, co jest najlepszym rozwiązaniem w tych skrajnych przypadkach.

**P3: Jak dodać nową walutę lub język do mojego sklepu, abym mógł go użyć w regule geo?**
O3:

-   **Dodawanie waluty:** Przejdź do **Lokalizacja > Waluty** w Panelu administracyjnym PrestaShop. Kliknij „Dodaj nową walutę”, wypełnij szczegóły i włącz ją.
-   **Dodawanie języka:** Przejdź do **Lokalizacja > Języki** w Panelu administracyjnym PrestaShop. Kliknij „Dodaj nowy język”, wypełnij szczegóły i włącz go. Pamiętaj również o zainstalowaniu pakietów językowych i przetłumaczeniu treści na nowy język.

**P4: Czy ten moduł spowolni moją stronę internetową?**
O4: Moduł wykonuje szybkie wyszukiwanie IP i stosowanie reguł, co jest zazwyczaj bardzo szybkie i zoptymalizowane. Nie powinien zauważalnie wpływać na szybkość ładowania Twojej strony internetowej. Jeśli doświadczysz jakichkolwiek problemów z wydajnością, upewnij się, że pamięć podręczna PrestaShop jest włączona i regularnie czyszczona.

**P5: Chcę dostosować styl banera wyboru kraju do mojego motywu. Jak to zrobić?**
O5: Baner używa specyficznych klas CSS. Chociaż bezpośrednia modyfikacja plików modułu nie jest zalecana (ponieważ aktualizacje by je nadpisały), programista stron internetowych może użyć niestandardowego pliku CSS Twojego motywu, aby nadpisać domyślne style. Sprawdziłby baner za pomocą narzędzi deweloperskich przeglądarki, aby zidentyfikować odpowiednie selektory CSS (np. klasy takie jak `.progeo-banner`, `.progeo-choice`) i następnie zastosowałby własne style.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Geolocation pro - waluta i język według kraju” (`progeo`) został zaprojektowany w celu głębokiej integracji z podstawowymi funkcjami internacjonalizacji PrestaShop. Wykorzystuje głównie nadpisywanie, aby modyfikować sposób, w jaki PrestaShop określa aktywną `Configuration`, `Currency` i `Language` na podstawie adresu IP odwiedzającego. Moduł ma standardową strukturę modułu PrestaShop, wykorzystując kontrolery front-office i admin, niestandardowe klasy (zwłaszcza dla encji `ObjectModel`) oraz szablony Smarty zarówno do konfiguracji, jak i wyświetlania w front-office (np. baner wyboru kraju). Główna logika modułu znajduje się w pliku `index.php` (główny plik modułu) oraz w nadpisanych klasach rdzenia.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `progeo/controllers/front/choice.php`
    -   **Nazwa klasy i klasa nadrzędna:** `ProgeoChoiceModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler obsługuje żądania AJAX związane z banerem wyboru kraju. Kiedy klient wchodzi w interakcję z banerem (np. wybiera inny kraj, walutę lub język), ten kontroler przetwarza żądanie, aktualizuje zmienne sesji lub ciasteczka i potencjalnie przekierowuje użytkownika, aby zastosować nowe ustawienia. Jest to kluczowe dla interaktywnego aspektu banera.
-   `progeo/controllers/front/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `ProgeoIndexModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler może służyć jako rezerwowy lub prosty punkt wejścia dla akcji modułu w front-office, chociaż `choice.php` jest bardziej specyficzny dla interaktywności banera. W wielu modułach `index.php` w `controllers/front` jest miejscem zastępczym lub obsługuje bardzo podstawowe, niespecyficzne żądania front-office.

#### Kontrolery administracyjne Back-Office

-   `progeo/controllers/admin/AdminGeorulesController.php`
    -   **Nazwa zakładki i zarządzana encja:** „Reguły Geo” (w głównym menu modułu). Zarządza encjami `Georule`.
    -   **Odpowiedzialność:** Jest to główny kontroler do zarządzania przypisaniami walut i języków specyficznych dla kraju. Zapewnia interfejs CRUD (Create, Read, Update, Delete) dla rekordów `ps_progeo_georule`, umożliwiając administratorom definiowanie, która waluta i język powinny być aktywne dla odwiedzających z określonych krajów. Rozszerza `AdminController` i używa `HelperList` dla siatki oraz `HelperForm` dla formularzy dodawania/edycji.
-   `progeo/controllers/admin/AdminLangrules.php`
    -   **Nazwa zakładki i zarządzana encja:** „Reguły Językowe” (w głównym menu modułu). Zarządza encjami `Langrule`.
    -   **Odpowiedzialność:** Ten kontroler zarządza regułami specyficznymi dla języka. Zapewnia interfejs CRUD dla rekordów `ps_progeo_langrule`. Prawdopodobnie jest używany do bardziej szczegółowej kontroli języka, potencjalnie nadpisując lub uzupełniając język ustawiony w `AdminGeorulesController`.
-   `progeo/controllers/admin/AdminLangrulesController.php`
    -   **Nazwa zakładki i zarządzana encja:** „Reguły Językowe” (w głównym menu modułu). Zarządza encjami `Langrule`.
    -   **Odpowiedzialność:** Wydaje się to być duplikatem lub alternatywną implementacją `AdminLangrules.php`. W typowym module PrestaShop `AdminLangrulesController.php` byłby standardową konwencją nazewnictwa. Programiści powinni zweryfikować, który plik jest faktycznie używany przez rejestrację menu modułu.
-   `progeo/controllers/admin/index.php`
    -   **Nazwa zakładki i zarządzana encja:** Nie jest to bezpośrednia zakładka, ale standardowy placeholder.
    -   **Odpowiedzialność:** Ten plik jest często obecny w katalogach `controllers/admin`, ale zazwyczaj jest pusty lub zawiera podstawowe środki bezpieczeństwa (np. `die('Forbidden');`). Nie zarządza konkretną encją ani nie zapewnia interfejsu użytkownika.

### 4.3 Klasy rdzenia i modele (`classes/`)

Moduł wykorzystuje nadpisywanie, aby wstrzyknąć swoją logikę do podstawowego zachowania PrestaShop.

-   `progeo/override/classes/Configuration.php`
    -   **Odpowiedzialność:** Nadpisuje podstawową klasę `Configuration`. Jest to kluczowe dla modułu, aby dynamicznie modyfikować globalne wartości konfiguracyjne (takie jak `PS_CURRENCY_DEFAULT` lub `PS_LANG_DEFAULT`) na podstawie geolokalizacji, bez faktycznej zmiany wartości w bazie danych dla innych odwiedzających. Zapewnia, że gdy PrestaShop żąda wartości konfiguracyjnej, moduł może ją przechwycić i zwrócić zlokalizowaną.
-   `progeo/override/classes/Currency.php`
    -   **Odpowiedzialność:** Nadpisuje podstawową klasę `Currency`. To nadpisanie pozwala modułowi manipulować tym, która waluta jest uważana za „aktywną” lub „domyślną” dla bieżącego odwiedzającego, zapewniając poprawne wyświetlanie cen zgodnie z regułą geo.
-   `progeo/override/classes/Language.php`
    -   **Odpowiedzialność:** Nadpisuje podstawową klasę `Language`. Podobnie jak `Currency.php`, to nadpisanie umożliwia modułowi ustawienie aktywnego języka dla bieżącego odwiedzającego na podstawie geolokalizacji, zapewniając wyświetlanie treści w poprawnym języku.
-   `progeo/override/classes/index.php`
    -   **Odpowiedzialność:** Standardowy pusty plik `index.php` dla bezpieczeństwa w katalogu.
-   `progeo/override/classes/_Configuration.php`
    -   **Odpowiedzialność:** Ta nazwa pliku sugeruje potencjalną kopię zapasową lub starszą wersję nadpisania `Configuration`. W środowisku produkcyjnym powinno być aktywne tylko jedno nadpisanie `Configuration.php`. Programiści powinni zweryfikować proces instalacji modułu, aby upewnić się, że używane jest poprawne nadpisanie.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `progeo/views/js/banner.js`
    -   **Zakres:** Front-office.
    -   **Odpowiedzialność:** Ten skrypt obsługuje interaktywny baner wyboru kraju.
        -   **Słuchacze zdarzeń:** Wiąże zdarzenia z elementami w banerze (np. zdarzenia kliknięcia na przyciskach „zmień kraj”, zmiany w polach wyboru waluty/języka).
        -   **Wywołania AJAX:** Wykonuje żądania AJAX do `ProgeoChoiceModuleFrontController` (np. `choice.php`), aby zaktualizować wybrany przez użytkownika kraj, walutę lub język.
        -   **Manipulacja DOM:** Pokazuje/ukrywa baner, aktualizuje zawartość tekstową na podstawie wyborów użytkownika i potencjalnie przekierowuje przeglądarkę po dokonaniu wyboru.
        -   **Ciasteczka/Pamięć lokalna:** Może przechowywać preferencje użytkownika w ciasteczkach lub pamięci lokalnej, aby zapamiętać ich wybór w różnych sesjach.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `progeo/views/css/admin.css`
    -   **Zakres:** Stylizacja formularzy administracyjnych w back-office.
    -   **Odpowiedzialność:** Zapewnia specyficzną stylizację dla stron konfiguracyjnych modułu i kontrolerów administracyjnych (np. `AdminGeorulesController`, `AdminLangrulesController`). Zapewnia to spójny wygląd i działanie w panelu administracyjnym PrestaShop oraz zwiększa użyteczność formularzy i list modułu.
-   `progeo/views/css/banner.css`
    -   **Zakres:** Stylizacja dla klienta w front-office.
    -   **Odpowiedzialność:** Stylizuje baner wyboru kraju, który pojawia się w front-office. Definiuje pozycję banera, kolory, czcionki, responsywność i ogólną prezentację wizualną. Programiści mogą nadpisać te style w niestandardowym pliku CSS swojego motywu, aby bezproblemowo zintegrować baner z projektem sklepu. Kluczowe selektory mogą obejmować `.progeo-banner`, `.progeo-choice-form` itp.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `progeo/views/displayHeader.tpl`: Ten szablon jest prawdopodobnie podpięty do `displayHeader` (lub `actionFrontControllerSetMedia`), aby dołączyć niezbędne pliki CSS i JS dla banera front-office, lub aby wstrzyknąć początkowe zmienne JavaScript.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `progeo/views/advert.tpl`: Prawdopodobnie używany do wyświetlania komunikatów promocyjnych lub linków do innych modułów MyPresta.eu w konfiguracji modułu.
    -   `progeo/views/banner.tpl`: Ten szablon jest prawdopodobnie używany w konfiguracji modułu do podglądu lub zarządzania ustawieniami związanymi z banerem front-office.
    -   `progeo/views/currenciesForm.tpl`: Szablon do zarządzania ustawieniami związanymi z walutami, prawdopodobnie w głównej konfiguracji lub na dedykowanym ekranie administracyjnym.
    -   `progeo/views/diagnostics-layer1.tpl`, `progeo/views/diagnostics-layer2.tpl`, `progeo/views/diagnostics-overview.tpl`, `progeo/views/diagnostics-result.tpl`, `progeo/views/diagnostics.tpl`: Te szablony są używane do renderowania różnych narzędzi diagnostycznych i ich wyników, pomagając administratorowi rozwiązywać problemy z wykrywaniem IP i stosowaniem reguł.
    -   `progeo/views/languagesForm.tpl`: Szablon do zarządzania ustawieniami związanymi z językami, podobny do `currenciesForm.tpl`.
    -   `progeo/views/tabs.tpl`: Używany do renderowania zakładek nawigacyjnych w interfejsie konfiguracji modułu, umożliwiając administratorowi przełączanie się między różnymi sekcjami ustawień (np. „Reguły Geo”, „Reguły Językowe”, „Konfiguracja”).
    -   `progeo/views/tools-hint.tpl`, `progeo/views/tools.tpl`: Szablony do wyświetlania wskazówek lub ogólnych narzędzi w interfejsie back-office modułu.
-   **Szablony front-office (`views/templates/front/`)**:
    -   `progeo/views/banner.tpl`: Jest to rzeczywisty szablon dla banera wyboru kraju w front-office, renderowany dla klienta. Zawiera strukturę HTML do wyświetlania wykrytego kraju, waluty, języka i opcji ręcznego wyboru.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_progeo_georule`: Przechowuje główne reguły geolokalizacji.
        -   `id_progeo_georule` (Klucz podstawowy)
        -   `id_country` (Klucz obcy do `ps_country`)
        -   `id_currency` (Klucz obcy do `ps_currency`)
        -   `id_lang` (Klucz obcy do `ps_lang`)
    -   `ps_progeo_langrule`: Przechowuje reguły specyficzne dla języka (szczegóły zależałyby od konkretnej implementacji, ale prawdopodobnie podobna struktura dla nadpisań językowych).
        -   `id_progeo_langrule` (Klucz podstawowy)
        -   `id_lang` (Klucz obcy do `ps_lang`)
        -   (Potencjalnie inne pola dla specyficznych zachowań językowych)
    -   Rekordy konfiguracji w `ps_configuration`:
        -   `PROGEO_ENABLED`: (1 lub 0) Główny przełącznik modułu.
        -   `PROGEO_SHOW_BANNER`: (1 lub 0) Czy wyświetlać baner wyboru kraju.
        -   (Inne klucze konfiguracyjne zdefiniowane w `getContent()` i `install()`)
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Dołączenie zasobów CSS i JavaScript (`banner.css`, `banner.js`) dla banera front-office oraz potencjalnie wstrzyknięcie początkowych zmiennych JavaScript lub renderowanie samego banera. |
| `actionFrontControllerSetMedia` | Wykonywany, gdy kontroler front-office ustawia swoje zasoby multimedialne. | Podobnie jak `displayHeader`, używany do dodawania plików CSS i JS warunkowo lub w bardziej nowoczesny sposób w PrestaShop. |
| `actionModuleInstall` | Podczas instalacji modułu. | Tworzenie tabel bazy danych (`ps_progeo_georule`, `ps_progeo_langrule`), rejestrowanie hooków i ustawianie domyślnych wartości konfiguracyjnych. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Usuwanie tabel bazy danych, wyrejestrowywanie hooków i czyszczenie wartości konfiguracyjnych. |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony back-office. | Dołączenie `admin.css` dla stron konfiguracyjnych modułu i potencjalnie JavaScriptu specyficznego dla administratora. |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje zasoby multimedialne. | Podobnie jak `displayBackOfficeHeader`, do dodawania CSS i JS dla administratora. |
| `actionDispatcherBefore` | Przed przetworzeniem żądania przez dispatcher. | Kluczowe dla podstawowej logiki modułu: wykrywanie adresu IP odwiedzającego, stosowanie reguły geo i ustawianie poprawnej waluty i języka `Context` *przed* renderowaniem strony przez PrestaShop. To tutaj nadpisania są skutecznie wyzwalane. |
| `displayBanner` (Niestandardowy hook) | Potencjalnie niestandardowy hook do renderowania banera front-office. | Jeśli `displayBanner` jest niestandardowym hookiem, moduł zarejestrowałby się, aby renderować `banner.tpl` w tej konkretnej lokalizacji. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Geolocation pro - waluta i język według kraju”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie optymalnego działania modułu i jego bezproblemowej integracji z Twoim sklepem PrestaShop.
