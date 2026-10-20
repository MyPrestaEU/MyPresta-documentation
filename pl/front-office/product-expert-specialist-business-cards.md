---
title: "Ekspert produktu - Wizytówki specjalistów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Ekspert produktu - Wizytówki specjalistów” od MyPresta.eu."
sidebar:
  label: "Ekspert produktu - Wizytówki specjalistów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product expert - Specialist Business Cards na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-expert-specialist-business-cards.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-expert-specialist-business-cards/)
>
> ---


# Ekspert produktu - Wizytówki specjalistów

## 1. Wymagania i kompatybilność

Aby zapewnić płynne działanie modułu „Ekspert produktu - Wizytówki specjalistów”, zapoznaj się z poniższymi wymaganiami:

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP, takie jak cURL, JSON i OpenSSL, są wymagane i zazwyczaj dostępne w większości nowoczesnych środowisk hostingowych. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Ekspert produktu - Wizytówki specjalistów” oferuje szerokie opcje konfiguracji na kilku ekranach w Twoim Panelu administracyjnym PrestaShop.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Menedżer modułów > Konfiguruj Ekspert produktu - Wizytówki specjalistów)

Jest to główny ekran konfiguracji dla ogólnych ustawień modułu, dostępny bezpośrednio po instalacji lub po kliknięciu „Konfiguruj” w Menedżerze modułów.

-   **Włącz/Wyłącz moduł:**
    *   **Co robi to ustawienie:** Jest to główny przełącznik funkcjonalności modułu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po włączeniu:* Funkcje modułu (wizytówki ekspertów, przypisania) będą aktywne w Twoim front office.
        *   *Po wyłączeniu:* Cała funkcjonalność modułu zostanie ukryta z front office, a wizytówki ekspertów nie będą się pojawiać.
    *   **Zalecana wartość:** TAK (chyba że tymczasowo wyłączasz go do konserwacji).
    *   **Scenariusz/przykład dla sprzedawcy:** Możesz go wyłączyć, jeśli wykonujesz dużą aktualizację motywu i chcesz upewnić się, że nie ma konfliktów, a następnie włączyć go ponownie po zakończeniu testów.
-   **Wyświetl ekspertów na stronie produktu:**
    *   **Co robi to ustawienie:** Kontroluje, czy wizytówki ekspertów są wyświetlane na poszczególnych stronach produktów.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po włączeniu:* Eksperci przypisani do produktów, kategorii, marek lub dostawców pojawią się na odpowiednich stronach produktów.
        *   *Po wyłączeniu:* Eksperci nie będą wyświetlani na stronach produktów, niezależnie od ich przypisań.
    *   **Zalecana wartość:** TAK (jest to podstawowa funkcja modułu).
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz używać ekspertów tylko do zapytań B2B na dedykowanej stronie, a nie bezpośrednio na listach produktów, możesz to wyłączyć.
-   **Wyświetl ekspertów w haku:**
    *   **Co robi to ustawienie:** Pozwala wybrać konkretny hak PrestaShop, w którym będą wyświetlane wizytówki ekspertów. Typowe haki to `displayProductButtons`, `displayProductExtraContent`, `displayRightColumn`, `displayLeftColumn`, `displayFooter`.
    *   **Efekt zmiany tego ustawienia:** Wizytówki ekspertów zostaną wyrenderowane w wybranej lokalizacji na stronach produktów lub innych stronach, gdzie hak jest aktywny.
    *   **Zalecana wartość:** `displayProductExtraContent` lub `displayProductButtons` są często dobrymi wyborami dla stron produktów, ponieważ są zazwyczaj widoczne. Eksperymentuj, aby znaleźć najlepsze dopasowanie do Twojego motywu.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój motyw ma dedykowaną zakładkę lub sekcję „dodatkowa zawartość”, `displayProductExtraContent` może być idealny. Jeśli chcesz, aby eksperci byli w pobliżu przycisku „Dodaj do koszyka”, `displayProductButtons` może zadziałać.
-   **Włącz formularz kontaktowy:**
    *   **Co robi to ustawienie:** Określa, czy formularz kontaktowy jest dostępny dla klientów do bezpośredniego wysyłania wiadomości do ekspertów.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po włączeniu:* Przycisk lub link „Skontaktuj się z ekspertem” pojawi się na wizytówce eksperta, otwierając formularz, za pomocą którego klienci mogą wysłać wiadomość.
        *   *Po wyłączeniu:* Opcja formularza kontaktowego zostanie usunięta z wizytówek ekspertów.
    *   **Zalecana wartość:** TAK (bardzo zalecane dla zaangażowania klienta).
    *   **Scenariusz/przykład dla sprzedawcy:** Włączenie tej opcji pozwala klientom zadawać konkretne pytania dotyczące produktu bezpośrednio ekspertowi, co prowadzi do bardziej świadomych zakupów.
-   **Zgodność z RODO dla formularza kontaktowego:**
    *   **Co robi to ustawienie:** Jeśli formularz kontaktowy jest włączony, to ustawienie dodaje pole wyboru dla klientów, aby wyrazili zgodę na przetwarzanie danych, co jest kluczowe dla zgodności z RODO.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po włączeniu:* Na formularzu kontaktowym pojawi się obowiązkowe pole wyboru, wymagające zgody klienta przed wysłaniem wiadomości.
        *   *Po wyłączeniu:* Nie będzie wyświetlane pole wyboru zgody RODO.
    *   **Zalecana wartość:** TAK (niezbędne dla zgodności prawnej w wielu regionach).
    *   **Scenariusz/przykład dla sprzedawcy:** Zawsze włączaj tę opcję, jeśli Twoja grupa docelowa znajduje się w UE lub w regionie z podobnymi przepisami o ochronie danych.
-   **Domyślny układ wizytówki eksperta:**
    *   **Co robi to ustawienie:** Pozwala wybrać predefiniowany lub niestandardowy układ wyświetlania poszczególnych wizytówek ekspertów. Obejmuje to opcje dotyczące umiejscowienia zdjęcia, wyrównania tekstu i ogólnego projektu wizytówki.
    *   **Efekt zmiany tego ustawienia:** Zmienia wygląd wszystkich wizytówek ekspertów w Twoim sklepie, chyba że zostanie to nadpisane przez ustawienia konkretnego eksperta.
    *   **Zalecana wartość:** Wybierz układ, który najlepiej pasuje do estetyki Twojego sklepu. Możesz podglądać różne opcje.
    *   **Scenariusz/przykład dla sprzedawcy:** Możesz wybrać układ „Nowoczesny” dla eleganckiego, minimalistycznego sklepu lub układ „Klasyczny” dla bardziej tradycyjnego wyglądu.
-   **Domyślny układ listy ekspertów:**
    *   **Co robi to ustawienie:** Określa, w jaki sposób wiele wizytówek ekspertów jest ułożonych, gdy wyświetlanych jest więcej niż jeden ekspert (np. w siatce, liście lub karuzeli).
    *   **Efekt zmiany tego ustawienia:** Kontroluje ogólną prezentację wielu ekspertów na stronie.
    *   **Zalecana wartość:** „Siatka” dla kompaktowego wyświetlania, „Karuzela” dla oszczędności miejsca i interaktywnego przeglądania lub „Lista” dla bardziej szczegółowego, ułożonego widoku.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli masz wielu ekspertów dla kategorii, „Karuzela” może zaoszczędzić miejsce. Jeśli masz tylko jednego lub dwóch, „Siatka” może wyglądać czyściej.
-   **Pokaż narzędzie wyszukiwania ekspertów:**
    *   **Co robi to ustawienie:** Włącza pasek wyszukiwania, który pozwala klientom znaleźć ekspertów według imienia lub specjalizacji.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po włączeniu:* Pojawi się pole wyszukiwania, zazwyczaj w pobliżu wizytówek ekspertów, umożliwiające klientom filtrowanie ekspertów.
        *   *Po wyłączeniu:* Narzędzie wyszukiwania ekspertów nie będzie widoczne.
    *   **Zalecana wartość:** TAK (poprawia użyteczność, zwłaszcza przy wielu ekspertach).
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli masz duży zespół specjalistów, włączenie narzędzia wyszukiwania pomaga klientom szybko znaleźć właściwą osobę.
-   **Hak narzędzia wyszukiwania ekspertów:**
    *   **Co robi to ustawienie:** Określa, gdzie narzędzie wyszukiwania ekspertów będzie wyświetlane w Twoim front office.
    *   **Efekt zmiany tego ustawienia:** Pasek wyszukiwania pojawi się w wybranej lokalizacji haka.
    *   **Zalecana wartość:** `displayTop` lub `displayNav` dla globalnej widoczności, lub `displayLeftColumn`/`displayRightColumn`, jeśli chcesz, aby znajdowało się obok innych filtrów.
    *   **Scenariusz/przykład dla sprzedawcy:** Umieszczenie go w `displayTop` sprawia, że jest łatwo dostępne z każdej strony, podobnie jak wyszukiwanie produktów.

### 2.2 Dedykowany ekran administracyjny: Eksperci (Panel administracyjny > Ekspert produktu > Eksperci)

Ten ekran służy do zarządzania indywidualnymi profilami ekspertów, tworzenia nowych ekspertów i edytowania istniejących.

-   **Nazwa ekranu i lokalizacja w menu:** **Ekspert produktu > Eksperci**
-   **Dostępne działania i ustawienia:**
    *   **Lista ekspertów (Widok siatki):** Wyświetla tabelę wszystkich utworzonych ekspertów. Możesz zobaczyć ich imię, rolę, status (aktywny/nieaktywny) oraz działania takie jak „Edytuj” lub „Usuń”.
    *   **Przycisk „Dodaj nowego eksperta”:** Kliknięcie tego przycisku przenosi Cię do formularza tworzenia nowego profilu eksperta.
    *   **Działania Edytuj/Usuń:** Dla każdego eksperta na liście możesz kliknąć „Edytuj”, aby zmodyfikować jego dane, lub „Usuń”, aby go usunąć.
    *   **Działania masowe:** Pozwala wybrać wielu ekspertów i wykonać działania takie jak „Włącz”, „Wyłącz” lub „Usuń” ich jednocześnie.
-   **Formularz tworzenia/edycji eksperta:**
    *   **Imię:** Pełne imię Twojego eksperta.
    *   **Rola/Tytuł:** Ich tytuł zawodowy lub rola (np. „Starszy Menedżer Sprzedaży”, „Specjalista Wsparcia Technicznego”, „Doradca Mody”).
    *   **Krótka biografia:** Krótki opis ich wiedzy lub doświadczenia. Pomaga to klientom zrozumieć ich kwalifikacje.
    *   **Zdjęcie:** Prześlij profesjonalne zdjęcie eksperta. Jest to kluczowe dla budowania zaufania i osobistego kontaktu.
    *   **Linki kontaktowe:**
        *   **E-mail:** Adres e-mail eksperta.
        *   **Telefon:** Numer telefonu eksperta.
        *   **WhatsApp:** Numer WhatsApp (wygeneruje bezpośredni link do czatu).
        *   **LinkedIn:** Link do ich profilu LinkedIn.
        *   **Inne niestandardowe linki:** Możesz dodać dodatkowe niestandardowe linki z ikonami (np. link do ich osobistego bloga, konkretnego portfolio produktów).
    *   **Aktywny:** Przełącznik do włączania lub wyłączania eksperta.
        *   *Po włączeniu:* Ekspert będzie dostępny do przypisania i wyświetlania.
        *   *Po wyłączeniu:* Ekspert nie pojawi się w front office, nawet jeśli jest przypisany.
    *   **Nadpisanie układu wizytówki eksperta:** Pozwala wybrać konkretny układ wizytówki dla *tego indywidualnego eksperta*, nadpisując globalne ustawienie domyślne w konfiguracji modułu. Jest to przydatne do wyróżniania niektórych ekspertów lub dopasowania do ich osobistej marki.
    *   **Przypisania (Produkty, Kategorie, Marki, Dostawcy):** Tutaj łączysz ekspertów z konkretnymi jednostkami sklepu.
        *   **Produkty:** Wyszukaj i wybierz poszczególne produkty, z którymi ten ekspert jest związany.
        *   **Kategorie:** Wybierz kategorie, w których wizytówka tego eksperta powinna pojawiać się na produktach w tych kategoriach.
        *   **Marki:** Wybierz konkretne marki, w których ten ekspert się specjalizuje.
        *   **Dostawcy:** Wybierz dostawców, których produkty ten ekspert może doradzać.
        *   *Efekt zmian:* Gdy klient przegląda produkt, który pasuje do któregokolwiek z tych przypisań, wizytówka eksperta zostanie wyświetlona. Jeśli przypisanych jest wielu ekspertów, wszyscy odpowiedni eksperci zostaną wyświetleni zgodnie z układem listy.
-   **Efekt zmian:**
    *   Dodanie nowego eksperta sprawia, że jest on dostępny do przypisania do produktów, kategorii itp.
    *   Edycja eksperta aktualizuje jego wyświetlane informacje i dane kontaktowe w całym sklepie.
    *   Usunięcie eksperta usuwa go i jego przypisania z Twojego sklepu.
    *   Zmiana przypisań natychmiast wpływa na to, które wizytówki ekspertów pojawiają się na których stronach produktów.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Twórz nowych ekspertów:** Gdy dołączy nowy członek zespołu lub potrzebna jest nowa specjalizacja, utwórz jego profil tutaj.
    2.  **Przypisuj ekspertów:** Regularnie przeglądaj swój katalog produktów i przypisuj odpowiednich ekspertów do nowych produktów, kategorii lub marek.
    3.  **Aktualizuj profile:** Utrzymuj aktualne zdjęcia, biografie i dane kontaktowe ekspertów.
    4.  **Dezaktywuj/Reaktywuj:** Użyj przełącznika „Aktywny”, aby tymczasowo ukryć eksperta (np. jeśli jest na urlopie) bez usuwania jego profilu.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz/Wyłącz moduł | TAK | Główny przełącznik funkcjonalności modułu. |
| | Wyświetl ekspertów na stronie produktu | TAK | Pokaż wizytówki ekspertów na stronach produktów. |
| | Wyświetl ekspertów w haku | `displayProductExtraContent` | Wybierz, gdzie wizytówki ekspertów pojawiają się na stronach produktów. |
| | Włącz formularz kontaktowy | TAK | Pozwól klientom bezpośrednio wysyłać wiadomości do ekspertów. |
| | Zgodność z RODO dla formularza kontaktowego | TAK | Dodaj pole wyboru zgody do formularza kontaktowego. |
| | Domyślny układ wizytówki eksperta | (Wybierz na podstawie motywu) | Styl wizualny poszczególnych wizytówek ekspertów. |
| | Domyślny układ listy ekspertów | Siatka / Karuzela | Sposób ułożenia wielu wizytówek ekspertów. |
| | Pokaż narzędzie wyszukiwania ekspertów | TAK | Włącz pasek wyszukiwania ekspertów. |
| | Hak narzędzia wyszukiwania ekspertów | `displayTop` / `displayNav` | Gdzie pojawia się narzędzie wyszukiwania ekspertów. |
| **Ekspert produktu > Eksperci** | Dodaj nowego eksperta | N/A | Twórz nowe profile ekspertów. |
| | Edytuj eksperta | N/A | Modyfikuj szczegóły eksperta (imię, rola, biografia, zdjęcie, kontakty). |
| | Aktywny (Status eksperta) | TAK | Włącz/wyłącz widoczność poszczególnych ekspertów. |
| | Nadpisanie układu wizytówki eksperta | N/A | Nadpisz globalny układ wizytówki dla konkretnego eksperta. |
| | Przypisz do produktów | N/A | Połącz eksperta z konkretnymi produktami. |
| | Przypisz do kategorii | N/A | Połącz eksperta z produktami w określonych kategoriach. |
| | Przypisz do marek | N/A | Połącz eksperta z produktami określonych marek. |
| | Przypisz do dostawców | N/A | Połącz eksperta z produktami od określonych dostawców. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

Oto kilka często zadawanych pytań i wskazówek dotyczących rozwiązywania problemów dla właścicieli sklepów korzystających z modułu „Ekspert produktu - Wizytówki specjalistów”:

**P1: Moje wizytówki ekspertów nie wyświetlają się na stronie produktu.**

-   **O:** Najpierw sprawdź, czy moduł jest **włączony** w **Moduły > Menedżer modułów**.
-   **O:** Następnie przejdź do strony konfiguracji modułu i upewnij się, że „Wyświetl ekspertów na stronie produktu” jest ustawione na **TAK**.
-   **O:** Sprawdź, czy faktycznie **przypisałeś** eksperta do konkretnego produktu, jego kategorii, marki lub dostawcy w **Ekspert produktu > Eksperci > [Edytuj eksperta] > Przypisania**.
-   **O:** Sprawdź przełącznik „Aktywny” dla danego eksperta w **Ekspert produktu > Eksperci**. Jeśli jest nieaktywny, nie będzie się wyświetlał.
-   **O:** Wyczyść pamięć podręczną PrestaShop: Przejdź do **Zaawansowane > Wydajność**, a następnie kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Czasami stara zawartość pamięci podręcznej uniemożliwia wyświetlanie nowych elementów modułu.

**P2: Wizytówki ekspertów wyglądają dziwnie lub nie pasują do projektu mojego motywu.**

-   **O:** Moduł udostępnia „Domyślny układ wizytówki eksperta” i „Domyślny układ listy ekspertów” w swojej konfiguracji. Eksperymentuj z różnymi opcjami, aby zobaczyć, która najlepiej integruje się z Twoim motywem.
-   **O:** Jeśli masz niestandardowy motyw, może on mieć specyficzny CSS, który koliduje ze stylami modułu. Może być konieczne, aby programista internetowy sprawdził CSS i wprowadził drobne poprawki.
-   **O:** Upewnij się, że Twój motyw jest aktualny. Przestarzałe motywy mogą czasami powodować problemy z wyświetlaniem z nowszymi modułami.

**P3: Formularz kontaktowy nie wysyła e-maili.**

-   **O:** Najpierw upewnij się, że „Włącz formularz kontaktowy” jest ustawione na **TAK** w konfiguracji modułu.
-   **O:** Sprawdź, czy adres e-mail eksperta jest poprawnie wprowadzony w jego profilu (**Ekspert produktu > Eksperci > [Edytuj eksperta]**).
-   **O:** Sprawdź ustawienia e-mail w PrestaShop (**Zaawansowane > E-mail**). Wyślij testowy e-mail z PrestaShop, aby upewnić się, że konfiguracja e-mail Twojego sklepu działa poprawnie. Jeśli PrestaShop nie może wysyłać e-maili, moduł również nie będzie mógł.
-   **O:** Sprawdź logi poczty swojego serwera pod kątem błędów. Może to wymagać pomocy od Twojego dostawcy hostingu.

**P4: Jak przetłumaczyć tekst modułu na inne języki?**

-   **O:** Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
-   **O:** Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz moduł „Ekspert produktu - Wizytówki specjalistów”.
-   **O:** Możesz wtedy przetłumaczyć wszystkie ciągi modułu na wybrane języki. Pamiętaj, aby zapisać zmiany.

**P5: Chcę wyświetlać ekspertów w innym miejscu niż dostępne haki.**

-   **O:** Moduł udostępnia wybór standardowych haków PrestaShop. Jeśli musisz wyświetlać ekspertów w bardzo specyficznym, niestandardowym miejscu (np. w niestandardowej zakładce lub unikalnej sekcji szablonu strony produktu), będzie to wymagało niestandardowego rozwoju motywu. Programista internetowy musiałby ręcznie wywołać funkcję haka modułu bezpośrednio w plikach `.tpl` Twojego motywu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd architektury technicznej i bazy kodu modułu „Ekspert produktu - Wizytówki specjalistów”, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł „Ekspert produktu - Wizytówki specjalistów” wykorzystuje standardowy wzorzec PrestaShop MVC (Model-View-Controller), w dużym stopniu opierając się na `ObjectModel` do trwałości danych. Wprowadza niestandardowe kontrolery administracyjne do zarządzania ekspertami i ich przypisaniami oraz kontrolery frontowe do interakcji AJAX i wyświetlania informacji o ekspertach. Moduł wykorzystuje solidną strukturę klas do zarządzania układami wizytówek ekspertów, stylami i logiką prezentacji, co pozwala na wysoką konfigurowalność. Integruje się z różnymi hakami PrestaShop, aby dynamicznie wstrzykiwać swoją zawartość do front office.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `controllers/front/ajax.php`
    *   **Nazwa klasy:** `ProductexpertAjaxModuleFrontController` (rozszerza `ModuleFrontController`)
    *   **Odpowiedzialność:** Obsługuje żądania AJAX z front office. Zazwyczaj obejmuje to przetwarzanie zgłoszeń formularzy kontaktowych ekspertów, dynamiczne ładowanie danych ekspertów lub wszelkie inne interaktywne elementy, które wymagają komunikacji z serwerem bez pełnego przeładowania strony. Zwraca odpowiedzi JSON.
-   `controllers/front/index.php`
    *   **Nazwa klasy:** `ProductexpertIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    *   **Odpowiedzialność:** Zastępczy lub domyślny kontroler frontowy. W wielu modułach może obsługiwać dedykowaną stronę modułu, jeśli taka istnieje, lub po prostu przekierowywać, jeśli jego główna funkcja odbywa się za pośrednictwem haków lub AJAX. Dla tego modułu jego główna rola jest prawdopodobnie minimalna, a `ajax.php` obsługuje większość interakcji front-endowych.

#### Kontrolery administracyjne Back-Office

-   `controllers/admin/AdminProductExpertController.php`
    *   **Nazwa klasy:** `AdminProductExpertController` (rozszerza `ModuleAdminController`)
    *   **Nazwa zakładki:** „Eksperci” w menu „Ekspert produktu”.
    *   **Zarządzana jednostka:** `ProductExpertExpert` (za pośrednictwem `classes/ProductExpertExpert.php`).
    *   **Odpowiedzialność:** Jest to główny kontroler administracyjny do zarządzania indywidualnymi profilami ekspertów. Obsługuje listowanie ekspertów (za pomocą `HelperList`) oraz formularze tworzenia/edycji ekspertów (za pomocą `HelperForm`). Zarządza operacjami CRUD dla danych ekspertów, w tym ich imieniem, rolą, biografią, zdjęciem, linkami kontaktowymi, a co najważniejsze, ich przypisaniami do produktów, kategorii, marek i dostawców. Zarządza również nadpisaniami układu dla poszczególnych wizytówek ekspertów.
-   `controllers/admin/index.php`
    *   **Nazwa klasy:** (Brak konkretnej klasy, często przekierowanie lub środek bezpieczeństwa)
    *   **Odpowiedzialność:** Ten plik jest zazwyczaj środkiem bezpieczeństwa, aby zapobiec bezpośredniemu listowaniu katalogów lub dostępowi. Często zawiera proste `header('Location: ../../index.php'); exit;` lub podobne, aby przekierować do głównego panelu administracyjnego. Nie zarządza konkretną jednostką ani formularzem.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Ten moduł posiada bogaty zestaw klas do zarządzania jego złożonymi funkcjami, zwłaszcza w zakresie układów i konfiguracji wizytówek ekspertów.

-   `classes/ProductExpertExpert.php`
    *   **Tabela bazy danych:** `ps_productexpert_expert`
    *   **Rozszerza:** `ObjectModel`
    *   **Pola `$definition`:** Definiuje schemat dla profili ekspertów (id\_expert, name, role, bio, photo\_id, active, date\_add, date\_upd, layout\_preset\_id). Obsługuje pola wielojęzyczne, jeśli dotyczy.
    *   **Kluczowe metody publiczne:** Metody do zapisywania, pobierania i usuwania danych ekspertów. Zawiera logikę obsługi przesyłania zdjęć i skojarzeń.
-   `classes/ProductExpertExpertLinks.php`
    *   **Tabela bazy danych:** `ps_productexpert_expert_link`
    *   **Rozszerza:** `ObjectModel`
    *   **Pola `$definition`:** Definiuje schemat dla linków kontaktowych ekspertów (id\_expert\_link, id\_expert, type, value, icon, position).
    *   **Kluczowe metody publiczne:** Zarządza różnymi linkami kontaktowymi (e-mail, telefon, WhatsApp, LinkedIn, niestandardowe) związanymi z ekspertem.
-   `classes/ProductExpertExpertPhoto.php`
    *   **Tabela bazy danych:** `ps_productexpert_expert_photo`
    *   **Rozszerza:** `ObjectModel`
    *   **Pola `$definition`:** Zarządza szczegółami zdjęć ekspertów (id\_photo, filename, mime\_type, size).
    *   **Kluczowe metody publiczne:** Obsługuje przechowywanie i pobieranie zdjęć profilowych ekspertów.
-   `classes/ProductExpertConfig.php`
    *   **Tabela bazy danych:** `ps_configuration` (przechowuje wartości konfiguracji)
    *   **Rozszerza:** (Prawdopodobnie nie `ObjectModel`, ale klasa narzędziowa)
    *   **Kluczowe metody publiczne:** Udostępnia statyczne metody do pobierania i ustawiania wartości konfiguracyjnych specyficznych dla modułu (np. `PE_DISPLAY_ON_PRODUCT_PAGE`, `PE_CONTACT_FORM_ENABLED`).
-   `classes/ProductExpertResolver.php`
    *   **Rozszerza:** (Prawdopodobnie klasa niestandardowa)
    *   **Kluczowe metody publiczne:** Zawiera podstawową logikę do określania, którzy eksperci powinni być wyświetlani dla danego produktu na podstawie jego kategorii, marki, dostawcy i bezpośrednich przypisań produktów. Rozwiązuje listę ekspertów dla front office.
-   `classes/ProductExpertListPresenter.php`
    *   **Rozszerza:** (Prawdopodobnie klasa niestandardowa)
    *   **Kluczowe metody publiczne:** Odpowiedzialny za przygotowanie danych rozwiązanych ekspertów do formatu odpowiedniego do wyświetlania w szablonach Smarty, stosując wybrane układy listy (siatka, karuzela, lista).
-   `classes/ExpertCardLayout.php`, `ExpertCardLayoutPresets.php`, `ExpertCardLayoutPresetsBuiltin.php`, `ExpertCardLayoutPresetsBuiltinData.php`, `ExpertCardLayoutPresetsFilesystem.php`, `ExpertCardLayoutInstances.php`
    *   **Rozszerza:** (Prawdopodobnie klasy niestandardowe)
    *   **Odpowiedzialność:** Złożony zestaw klas dedykowanych do zarządzania wizualnym projektem i strukturą wizytówek ekspertów. Obejmuje to definiowanie elementów układu, stylów, gradientów oraz obsługę wbudowanych presetów, a także niestandardowych układów zapisanych przez użytkownika. Jest to rdzeń funkcjonalności „Visual Business Card Designer”.
-   `classes/ExpertCardAdminUi.php`, `ProductExpertSettingsAdminUi.php`, `ProductExpertListLayoutAdminUi.php`
    *   **Rozszerza:** (Prawdopodobnie klasy niestandardowe)
    *   **Odpowiedzialność:** Klasy pomocnicze do renderowania złożonych elementów interfejsu użytkownika w formularzach konfiguracji Back Office, w szczególności dla studia układu i ogólnych ustawień modułu.
-   `classes/PeCompatibility.php`
    *   **Rozszerza:** (Prawdopodobnie klasa narzędziowa)
    *   **Kluczowe metody publiczne:** Udostępnia metody do obsługi problemów z kompatybilnością między różnymi wersjami PrestaShop (np. różnice w nazwach haków, wywołaniach API lub przestarzałych funkcjach).
-   `classes/ProductExpertInstallSamples.php`
    *   **Rozszerza:** (Prawdopodobnie klasa narzędziowa)
    *   **Kluczowe metody publiczne:** Zawiera logikę instalacji przykładowych danych (np. przykładowych ekspertów, układów) podczas instalacji modułu, aby zapewnić szybki start dla sprzedawców.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    *   **Zakres:** Front-office.
    *   **Opis:** Zapewnia funkcjonalność autouzupełniania dla narzędzia wyszukiwania ekspertów, sugerując imiona ekspertów lub specjalizacje podczas pisania przez użytkownika.
-   `lib/searchTool/views/pe-searchtool-init.js`
    *   **Zakres:** Front-office.
    *   **Opis:** Inicjuje narzędzie wyszukiwania ekspertów, wiążąc słuchaczy zdarzeń z polem wyszukiwania i integrując funkcjonalność autouzupełniania.
-   `views/js/admin-element-editor.js`
    *   **Zakres:** Back-office.
    *   **Opis:** Zasila wizualny edytor dla poszczególnych elementów w układzie wizytówki eksperta (np. pól tekstowych, obrazów, ikon). Obsługuje przeciąganie i upuszczanie, zmianę rozmiaru i dostosowywanie właściwości stylu.
-   `views/js/admin-expert-photo.js`
    *   **Zakres:** Back-office.
    *   **Opis:** Zarządza funkcjonalnością przesyłania i podglądu zdjęć dla profili ekspertów w panelu administracyjnym.
-   `views/js/admin-layout-studio.js`
    *   **Zakres:** Back-office.
    *   **Opis:** Główny JavaScript dla „Visual Business Card Designer”. Obsługuje ogólny obszar roboczy układu, zarządzanie elementami, zapisywanie/ładowanie układów i stosowanie stylów.
-   `views/js/admin-list-layout-studio.js`
    *   **Zakres:** Back-office.
    *   **Opis:** Zarządza studiem do projektowania sposobu wyświetlania wielu wizytówek ekspertów (siatka, karuzela, lista), w tym opcji responsywności i nawigacji.
-   `views/js/front.js`
    *   **Zakres:** Front-office.
    *   **Opis:** Zawiera ogólny JavaScript front-office dla modułu, w tym:
        *   Słuchacze zdarzeń dla przesyłania formularzy kontaktowych (wywołania AJAX do `ajax.php`).
        *   Logika wyświetlania i ukrywania modalnego formularza kontaktowego.
        *   Inicjalizacja wszelkich funkcji karuzeli lub suwaków dla list ekspertów.
        *   Ogólne ulepszenia interfejsu użytkownika dla wizytówek ekspertów.

### 4.5 Arkusze stylów CSS (`views/css/`)

#### CSS Front-Office

-   `lib/searchTool/views/css/autocomplete.css`
    *   **Zakres:** Front-office.
    *   **Opis:** Style dla rozwijanych sugestii autouzupełniania w narzędziu wyszukiwania ekspertów.
-   `views/css/front.css`
    *   **Zakres:** Front-office.
    *   **Opis:** Ogólne style front-office dla modułu, w tym podstawowy układ, typografia i responsywność dla wizytówek i list ekspertów.
-   `views/css/pe-expert-card-front.css`
    *   **Zakres:** Front-office.
    *   **Opis:** Specyficzne style dla poszczególnych wizytówek ekspertów, stosujące wybrany układ i style elementów.
-   `views/css/pe-front-contact.css`
    *   **Zakres:** Front-office.
    *   **Opis:** Style dla formularza kontaktowego eksperta, w tym prezentacja modalna, pola wejściowe i przyciski.
-   `views/css/pe-front-experts.css`
    *   **Zakres:** Front-office.
    *   **Opis:** Style dla ogólnego wyświetlania wielu ekspertów, takich jak układy siatkowe, układy listowe lub nawigacja karuzelowa.

#### CSS Back-Office

-   `views/css/admin-config.css`
    *   **Zakres:** Back-office.
    *   **Opis:** Ogólne style dla głównej strony konfiguracji modułu w panelu administracyjnym.
-   `views/css/admin-element-editor.css`
    *   **Zakres:** Back-office.
    *   **Opis:** Style dla wizualnego edytora elementów w studiu układu.
-   `views/css/admin-expert-card-studio.css`
    *   **Zakres:** Back-office.
    *   **Opis:** Podstawowy CSS dla interfejsu studia układu wizytówek ekspertów.
-   `views/css/admin-expert-photo.css`
    *   **Zakres:** Back-office.
    *   **Opis:** Style dla obszaru przesyłania i podglądu zdjęć ekspertów w formularzach administracyjnych.
-   `views/css/admin-experts-list.css`
    *   **Zakres:** Back-office.
    *   **Opis:** Style dla widoku listy ekspertów w `AdminProductExpertController`.
-   `views/css/admin-layout-builder.css`
    *   **Zakres:** Back-office.
    *   **Opis:** Style związane z komponentami budowania układu.
-   `views/css/admin-layout-studio.css`
    *   **Zakres:** Back-office.
    *   **Opis:** Ogólne style dla interfejsu studia układu.
-   `views/css/admin-list-layout-studio.css`
    *   **Zakres:** Back-office.
    *   **Opis:** Style dla interfejsu studia układu listy.
-   `views/css/admin-pe-overrides.css`
    *   **Zakres:** Back-office.
    *   **Opis:** Specyficzne nadpisania CSS lub dostosowania dla domyślnych stylów administracyjnych PrestaShop, aby zapewnić spójność interfejsu użytkownika modułu.
-   `views/css/admin-searchtool.css`
    *   **Zakres:** Back-office.
    *   **Opis:** Style dla narzędzia wyszukiwania w panelu administracyjnym (jeśli dotyczy, np. do wyszukiwania produktów/kategorii podczas przypisywania).

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   `lib/searchTool/views/scripts.tpl`
    *   **Zakres:** Front-office.
    *   **Opis:** Prawdopodobnie zawiera niezbędny JavaScript i CSS dla narzędzia wyszukiwania, często podłączony do `displayHeader` lub `displayFooter` w celu załadowania zasobów.
-   `views/templates/admin/configure.tpl`
    *   **Zakres:** Back-office.
    *   **Opis:** Główny szablon dla strony konfiguracji modułu (metoda `getContent()`), renderujący ogólny formularz ustawień.
-   `views/templates/admin/list-layout.tpl`
    *   **Zakres:** Back-office.
    *   **Opis:** Szablon dla studia układu listy w panelu administracyjnym, umożliwiający konfigurację sposobu wyświetlania wielu wizytówek ekspertów.
-   `views/templates/admin/product-tab.tpl`
    *   **Zakres:** Back-office.
    *   **Opis:** Ten szablon jest prawdopodobnie używany do wstrzykiwania niestandardowej zakładki lub sekcji na stronie edycji produktu PrestaShop, umożliwiając bezpośrednie przypisanie ekspertów do produktu z ekranu edycji.
-   `views/templates/hook/product-experts.tpl`
    *   **Zakres:** Front-office.
    *   **Hak:** `displayProductButtons`, `displayProductExtraContent`, `displayRightColumn`, `displayLeftColumn`, `displayFooter` (zgodnie z konfiguracją).
    *   **Opis:** Główny szablon odpowiedzialny za renderowanie bloku wizytówek ekspertów w front office. Iteruje przez rozwiązanych ekspertów i dla każdego z nich zawiera `_pe-expert-card-element.tpl`.
-   `views/templates/hook/_pe-expert-card-element.tpl`
    *   **Zakres:** Front-office.
    *   **Hak:** Włączony przez `product-experts.tpl`.
    *   **Opis:** Renderuje pojedynczą wizytówkę eksperta, stosując wybrany układ i wyświetlając zdjęcie eksperta, imię, rolę, biografię i linki kontaktowe. Prawdopodobnie zawiera `_pe-expert-card-row.tpl` dla ustrukturyzowanej zawartości.
-   `views/templates/hook/_pe-expert-card-row.tpl`
    *   **Zakres:** Front-office.
    *   **Hak:** Włączony przez `_pe-expert-card-element.tpl`.
    *   **Opis:** Renderuje pojedynczy wiersz lub sekcję w wizytówce eksperta, używany do strukturyzowania elementów zawartości (np. wiersz dla ikon kontaktowych, wiersz dla imienia i roli).

### 4.7 Schemat bazy danych i mapa haków

#### Tabele bazy danych

-   `ps_productexpert_expert`: Przechowuje podstawowe informacje o profilu eksperta (imię, rola, biografia, ID zdjęcia, status aktywności, preset układu).
-   `ps_productexpert_expert_lang`: Przechowuje pola wielojęzyczne dla ekspertów (jeśli takie istnieją, np. biografia).
-   `ps_productexpert_expert_link`: Przechowuje indywidualne linki kontaktowe dla każdego eksperta (typ, wartość, ikona).
-   `ps_productexpert_expert_photo`: Przechowuje metadane dla zdjęć profilowych ekspertów.
-   `ps_productexpert_expert_product`: Tabela relacji wiele-do-wielu łącząca ekspertów z produktami.
-   `ps_productexpert_expert_category`: Tabela relacji wiele-do-wielu łącząca ekspertów z kategoriami.
-   `ps_productexpert_expert_manufacturer`: Tabela relacji wiele-do-wielu łącząca ekspertów z markami (producentami).
-   `ps_productexpert_expert_supplier`: Tabela relacji wiele-do-wielu łącząca ekspertów z dostawcami.
-   `ps_productexpert_layout_preset`: Przechowuje definicje niestandardowych układów wizytówek ekspertów utworzonych przez sprzedawcę.
-   `ps_productexpert_list_layout`: Przechowuje definicje niestandardowych układów list ekspertów (siatka, karuzela itp.).
-   `ps_configuration`: Przechowuje globalne ustawienia konfiguracyjne modułu (np. `PE_DISPLAY_ON_PRODUCT_PAGE`, `PE_DEFAULT_CARD_LAYOUT_ID`).

#### Tabela zarejestrowanych haków

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Ładowanie zasobów CSS i JS modułu dla front-office. |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony Back Office. | Ładowanie zasobów CSS i JS modułu dla ekranów administracyjnych. |
| `displayModuleConfigureExtraButtons` | Na stronie menedżera modułów, obok przycisku „Konfiguruj”. | Dodaj szybkie linki do „Zarządzaj ekspertami” lub „Studio układu”. |
| `displayAdminProductsExtra` | Na stronie edycji produktu w Back Office. | Wstrzyknij zakładkę/sekcję przypisania eksperta dla produktów. |
| `displayProductButtons` | W pobliżu przycisku „Dodaj do koszyka” na stronach produktów. | Wyświetl wizytówki ekspertów w widocznym miejscu specyficznym dla produktu. |
| `displayProductExtraContent` | W dedykowanej sekcji/zakładce na stronach produktów. | Wyświetl wizytówki ekspertów jako dodatkową zawartość produktu. |
| `displayLeftColumn` | W lewym pasku bocznym odpowiednich stron. | Wyświetl wizytówki ekspertów lub narzędzie wyszukiwania ekspertów w lewej kolumnie. |
| `displayRightColumn` | W prawym pasku bocznym odpowiednich stron. | Wyświetl wizytówki ekspertów lub narzędzie wyszukiwania ekspertów w prawej kolumnie. |
| `displayFooter` | W sekcji stopki wszystkich stron. | Wyświetl wizytówki ekspertów lub link do strony ekspertów w stopce. |
| `displayTop` | W górnej sekcji sklepu (nagłówek). | Wyświetl narzędzie wyszukiwania ekspertów dla globalnego dostępu. |
| `displayNav` | W pasku nawigacyjnym (często powyżej `displayTop`). | Wyświetl narzędzie wyszukiwania ekspertów dla globalnego dostępu. |
| `actionFrontControllerSetMedia` | Przed renderowaniem kontrolera frontowego, w celu dodania zasobów. | Dynamicznie dodawaj specyficzne dla front-office JS/CSS na podstawie kontekstu. |
| `actionAdminControllerSetMedia` | Przed renderowaniem kontrolera administracyjnego, w celu dodania zasobów. | Dynamicznie dodawaj specyficzne dla back-office JS/CSS na podstawie kontekstu. |
| `actionObjectProductAddAfter` | Po dodaniu nowego produktu. | Potencjalnie wyzwalaj logikę przypisania eksperta lub czyszczenie pamięci podręcznej. |
| `actionObjectProductUpdateAfter` | Po zaktualizowaniu produktu. | Potencjalnie wyzwalaj logikę przypisania eksperta lub czyszczenie pamięci podręcznej. |
| `actionObjectProductDeleteAfter` | Po usunięciu produktu. | Wyczyść wszelkie przypisania ekspertów związane z usuniętym produktem. |
| `actionObjectCategoryUpdateAfter` | Po zaktualizowaniu kategorii. | Wyczyść pamięć podręczną związaną z przypisaniami ekspertów opartymi na kategoriach. |
| `actionObjectManufacturerUpdateAfter` | Po zaktualizowaniu producenta (marki). | Wyczyść pamięć podręczną związaną z przypisaniami ekspertów opartymi na markach. |
| `actionObjectSupplierUpdateAfter` | Po zaktualizowaniu dostawcy. | Wyczyść pamięć podręczną związaną z przypisaniami ekspertów opartymi na dostawcach. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie techniczne, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół jest zaangażowany w zapewnianie kompleksowej pomocy i dbanie o płynne działanie Twojego modułu.

-   **MyPresta.eu Historia zamówień i pobieranie:** <https://mypresta.eu/my-account/orders/>
-   **Wsparcie MyPresta.eu:** Uzyskaj dostęp do naszego portalu wsparcia za pośrednictwem swojego konta, aby uzyskać bezpośrednią pomoc.
