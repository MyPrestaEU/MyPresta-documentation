---
title: "Przypisz przewoźnika do produktów masowo - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Przypisz przewoźnika do produktów masowo” od MyPresta.eu."
sidebar:
  label: "Przypisz przewoźnika do produktów masowo - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Assign carrier to products in bulk na MyPresta.eu](https://mypresta.eu/modules/administration-tools/assign-carrier-to-products-in-bulk.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/assign-carrier-to-products-in-bulk/)
>
> ---


# Przypisz przewoźnika do produktów masowo

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne nietypowe konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Przypisz przewoźnika do produktów masowo)

To jest główny interfejs, w którym będziesz definiować swoje zadania masowego przypisywania przewoźników. Strona została zaprojektowana tak, aby była intuicyjna, prowadząc Cię przez proces wyboru przewoźników, a następnie określania, które produkty powinny zostać objęte zmianami.

**Główne opcje konfiguracji:**

1.  **Wybierz przewoźników:**

    *   **Co robi to ustawienie:** Ta sekcja wyświetla listę wszystkich aktywnych przewoźników skonfigurowanych w Twoim sklepie PrestaShop (znajdujących się w **Wysyłka > Przewoźnicy**). Możesz wybrać jednego lub więcej przewoźników, których chcesz przypisać do swoich produktów.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy wybrano jednego lub więcej przewoźników:* Wybrani przewoźnicy zostaną przypisani do produktów, które określisz w kolejnych krokach. Oznacza to, że ci przewoźnicy staną się dostępnymi opcjami wysyłki dla tych produktów podczas realizacji zamówienia.
        *   *Gdy nie wybrano żadnych przewoźników:* Moduł nie wykona żadnego przypisania. Musisz wybrać co najmniej jednego przewoźnika, aby kontynuować.
    *   **Zalecana wartość:** Wybierz wszystkich przewoźników, którzy powinni być dostępni dla docelowych produktów.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz udostępnić „UPS Ground” i „FedEx Express” dla nowej linii elektroniki, wybierzesz oba z tej listy.
2.  **Wybierz produkty, do których przypisać przewoźników:**

    *   **Co robi to ustawienie:** Ta kluczowa sekcja pozwala zdefiniować zakres produktów, które otrzymają wybrane przypisania przewoźników. Masz trzy potężne opcje:
        *   **Według kategorii:** Przypisz przewoźników do wszystkich produktów w określonych kategoriach.
        *   **Według producentów:** Przypisz przewoźników do wszystkich produktów od określonych producentów.
        *   **Według konkretnych produktów:** Przypisz przewoźników do indywidualnie wybranych produktów.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy wybrano „Według kategorii”:* Pojawi się lista kategorii Twojego sklepu. Wybranie kategorii tutaj oznacza, że wszystkie produkty należące do tych kategorii będą miały przypisanych wybranych przewoźników.
        *   *Gdy wybrano „Według producentów”:* Pojawi się lista producentów Twojego sklepu. Wybranie producentów tutaj oznacza, że wszystkie produkty powiązane z tymi producentami będą miały przypisanych wybranych przewoźników.
        *   *Gdy wybrano „Według konkretnych produktów”:* Pojawi się pole wprowadzania z funkcją autouzupełniania. Możesz wpisać nazwy produktów, a system zasugeruje produkty. Możesz dodać wiele konkretnych produktów do listy.
    *   **Zalecana wartość:** Wybierz metodę, która najlepiej grupuje Twoje docelowe produkty. Dla szerokich zmian, kategorie lub producenci są efektywni. Dla precyzyjnych dostosowań, konkretne produkty są najlepsze.
    *   **Scenariusz / przykład dla sprzedawcy:**
        *   *Kategorie:* Uruchamiasz nową kategorię „Przedmioty kruche”. Wybierzesz tę kategorię i przypiszesz specjalistycznego „Przewoźnika towarów kruchych” do wszystkich produktów w niej.
        *   *Producenci:* Pojawia się nowa marka odzieży. Wybierasz producenta i przypisujesz swojego standardowego „Przewoźnika odzieży” do wszystkich ich produktów.
        *   *Konkretne produkty:* Masz trzy unikalne, ponadgabarytowe produkty, które wymagają „Przewoźnika towarowego”. Wyszukasz i dodasz te trzy produkty indywidualnie.
3.  **Przyciski akcji:**

    *   **Przycisk „Przypisz przewoźników”:**
        *   **Co robi ten przycisk:** Inicjuje proces masowego przypisywania. Po kliknięciu moduł przetworzy Twoje wybory i zaktualizuje powiązania przewoźników dla wszystkich określonych produktów.
        *   **Efekt kliknięcia tego przycisku:** Wybrani przewoźnicy zostaną powiązani z wybranymi produktami. Zazwyczaj zostanie wyświetlony komunikat o sukcesie lub błędzie.
        *   **Zalecana akcja:** Kliknij to tylko po dokładnym przejrzeniu swoich wyborów przewoźników i produktów.
        *   **Scenariusz / przykład dla sprzedawcy:** Po skonfigurowaniu przewoźników i grup produktów, kliknięcie tego przycisku wykonuje zmiany w całym Twoim sklepie.
    *   **Przycisk „Wyczyść wszystkie przypisania” (lub podobny):**
        *   **Co robi ten przycisk:** Ta opcja (jeśli jest obecna) zazwyczaj usuwałaby *wszystkie* przypisania przewoźników dla wybranych produktów, lub potencjalnie dla wszystkich produktów w sklepie, w zależności od dokładnej implementacji modułu.
        *   **Efekt kliknięcia tego przycisku:** Produkty powróciłyby do stanu bez przypisanych konkretnych przewoźników, lub tylko domyślnych przewoźników, potencjalnie wpływając na dostępność wysyłki.
        *   **Zalecana akcja:** Używaj z najwyższą ostrożnością i tylko wtedy, gdy w pełni rozumiesz konsekwencje. Jest to potężna akcja, która może zakłócić Twoje opcje wysyłki.
        *   **Scenariusz / przykład dla sprzedawcy:** Całkowicie zmieniasz swoją strategię wysyłki i musisz zresetować wszystkie powiązania produkt-przewoźnik przed ponownym ich przypisaniem.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 AdminMassCarrierCronController (Panel administracyjny > Zaawansowane > Cron masowego przewoźnika)

Ten ekran zapewnia zarządzanie zadaniami cron związanymi z modułem, umożliwiając planowanie i automatyzację zadań przypisywania przewoźników.

-   **Nazwa ekranu i lokalizacja w menu:** Zazwyczaj znajdziesz nową pozycję menu w sekcji **Zaawansowane** (lub podobnej, w zależności od wersji PrestaShop) o nazwie „Cron masowego przewoźnika” lub „Harmonogram przypisywania przewoźników”.
-   **Dostępne akcje i ustawienia:** Ten ekran prawdopodobnie wyświetli siatkę (listę) zaplanowanych zadań. Dla każdego zadania możesz zobaczyć:
    *   **ID zadania:** Unikalny identyfikator.
    *   **Opis:** Krótkie wyjaśnienie, co robi zadanie (np. „Przypisz UPS do kategorii X”).
    *   **Częstotliwość:** Jak często zadanie jest uruchamiane (np. codziennie, co tydzień, raz).
    *   **Ostatnie uruchomienie:** Sygnatura czasowa ostatniego wykonania.
    *   **Status:** Czy zadanie jest aktywne, oczekujące, czy zakończone.
    *   **Akcje:** Przyciski „Dodaj nowe zadanie”, „Edytuj”, „Usuń” lub „Uruchom teraz”.
-   **Efekt zmian:**
    *   *Dodanie nowego zadania:* Pozwala zdefiniować nową operację masowego przypisywania przewoźników, która ma być uruchamiana automatycznie w określonym interwale. Jest to przydatne do cyklicznych aktualizacji (np. import nowych produktów).
    *   *Edycja zadania:* Modyfikuje parametry (przewoźników, produkty, częstotliwość) istniejącego zaplanowanego przypisania.
    *   *Usunięcie zadania:* Usuwa zaplanowane przypisanie, zapobiegając jego uruchomieniu w przyszłości.
    *   *Uruchomienie zadania teraz:* Wykonuje zaplanowane zadanie natychmiast, poza jego regularnym harmonogramem.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    *   Użyj tego ekranu do automatyzacji rutynowych przypisań przewoźników, zwłaszcza jeśli regularnie importujesz nowe produkty do określonych kategorii lub od niektórych producentów, którzy zawsze korzystają z tych samych przewoźników.
    *   Do jednorazowych, natychmiastowych przypisań użyj głównej strony konfiguracji modułu (4.1).
    *   Regularnie sprawdzaj „Ostatnie uruchomienie” i „Status”, aby upewnić się, że Twoje zautomatyzowane zadania są wykonywane prawidłowo.

#### 2.2.2 index.php (masscarrier/controllers/admin/index.php)

Ten plik zazwyczaj służy jako symbol zastępczy lub przekierowanie w katalogu kontrolerów administracyjnych modułu i zazwyczaj nie reprezentuje odrębnego, konfigurowalnego ekranu dla sprzedawcy. W rozwoju modułów PrestaShop, pliki `index.php` w podkatalogach często zapobiegają listowaniu katalogów lub obsługują podstawowe routowanie, zamiast dostarczać interfejs użytkownika. Dlatego nie ma żadnych konkretnych ustawień ani akcji skierowanych do sprzedawcy związanych z tym plikiem.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Wybierz przewoźników | Wybierz wszystkich odpowiednich | Wybierz, którzy przewoźnicy zostaną przypisani do produktów. |
| | Wybierz produkty: Według kategorii | Wybierz odpowiednie kategorie | Przypisz przewoźników do wszystkich produktów w wybranych kategoriach. |
| | Wybierz produkty: Według producentów | Wybierz odpowiednich producentów | Przypisz przewoźników do wszystkich produktów od wybranych producentów. |
| | Wybierz produkty: Według konkretnych produktów | Wyszukaj i dodaj produkty | Przypisz przewoźników do indywidualnie wybranych produktów. |
| | Przycisk Przypisz przewoźników | Kliknij po wyborze | Wykonuje masowe przypisanie przewoźników. |
| | Przycisk Wyczyść wszystkie przypisania | Używaj ostrożnie | Usuwa przypisania przewoźników dla wybranych produktów (jeśli są obecne). |
| **AdminMassCarrierCronController** | Dodaj/Edytuj/Usuń zadanie | Zgodnie z potrzebami automatyzacji | Planuj i zarządzaj zautomatyzowanymi masowymi przypisaniami przewoźników. |
| | Akcja Uruchom teraz | W razie potrzeby do natychmiastowego wykonania | Ręcznie uruchom zaplanowane zadanie. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Przypisałem przewoźników, ale nie wyświetlają się klientom przy kasie.**
O:

1.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). PrestaShop często buforuje dostępność przewoźników.
2.  **Konfiguracja przewoźnika:** Sprawdź dokładnie, czy sami przewoźnicy są aktywni, mają prawidłowe strefy wysyłki i są skonfigurowani do obsługi zakresu wagi/ceny produktu. Przejdź do **Wysyłka > Przewoźnicy** i edytuj przewoźnika, aby przejrzeć jego ustawienia.
3.  **Wymiary/waga produktu:** Upewnij się, że wymiary i waga produktu są poprawnie wprowadzone i mieszczą się w zdefiniowanych zakresach przewoźnika.
4.  **Wykonanie modułu:** Ponownie uruchom proces przypisywania w module, upewniając się, że wybrałeś prawidłowych przewoźników i grupy produktów.

**P: Moduł wydaje się być zablokowany lub przetwarzanie trwa bardzo długo.**
O:

1.  **Zasoby serwera:** Jeśli masz bardzo duży katalog (dziesiątki tysięcy produktów) i przypisujesz do „wszystkich produktów”, proces może być zasobochłonny. Upewnij się, że Twój hosting ma wystarczającą ilość pamięci PHP i limity czasu wykonania.
2.  **Zadanie Cron:** W przypadku bardzo dużych operacji rozważ użycie „AdminMassCarrierCronController” do zaplanowania zadania jako zadania cron w tle, co jest bardziej niezawodne dla długotrwałych procesów.
3.  **Podziel zadania:** Zamiast przypisywać do *wszystkich* produktów naraz, spróbuj podzielić to na główne kategorie lub producentów.

**P: Czy mogę usunąć przewoźnika z produktów masowo za pomocą tego modułu?**
O: Główną funkcją tego modułu jest *przypisywanie* przewoźników. Chociaż nie ma on bezpośredniej funkcji „usuń przewoźnika z wybranych produktów”, możesz to skutecznie osiągnąć poprzez:

1.  **Ponowne przypisanie:** Jeśli chcesz zastąpić Przewoźnika A Przewoźnikiem B dla grupy produktów, po prostu wybierz Przewoźnika B i grupę produktów, a następnie uruchom przypisanie. Spowoduje to dodanie Przewoźnika B. Następnie musiałbyś ręcznie usunąć Przewoźnika A z tych produktów, jeśli chcesz, aby całkowicie zniknął, lub użyć oddzielnego narzędzia, jeśli jest dostępne.
2.  **Ręczne usunięcie:** Dla konkretnych produktów nadal możesz przejść do strony edycji produktu (**Katalog > Produkty > Edytuj produkt > zakładka Wysyłka**) i ręcznie odznaczyć przewoźnika.

**P: Mój niestandardowy motyw nie wyświetla poprawnie elementów modułu (jeśli jakiekolwiek były widoczne).**
O: Ten moduł nie ma żadnych wizualnych elementów front-office, więc problemy z kompatybilnością motywu są mało prawdopodobne z perspektywy wyświetlania. Jeśli napotkasz problemy z ekranami konfiguracji *panelu administracyjnego*:

1.  **Wersja PrestaShop:** Upewnij się, że pobrałeś prawidłową wersję modułu dla swojej instalacji PrestaShop.
2.  **Pamięć podręczna przeglądarki:** Wyczyść pamięć podręczną przeglądarki.
3.  **Nadpisania motywu:** Jeśli Twój motyw panelu administracyjnego jest mocno dostosowany, może to powodować zakłócenia. Spróbuj tymczasowo przełączyć się na domyślny motyw panelu administracyjnego PrestaShop, aby sprawdzić, czy problem nadal występuje.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Przypisz przewoźnika do produktów masowo” (`masscarrier`) stosuje standardowy wzorzec PrestaShop MVC (Model-View-Controller), koncentrując się głównie na zadaniach administracyjnych. Wykorzystuje klasę `Module` PrestaShop do swojej podstawowej funkcjonalności i rozszerza `AdminController` dla swoich dedykowanych ekranów zarządzania w panelu administracyjnym. Moduł bezpośrednio współdziała z podstawowymi danymi produktów i przewoźników PrestaShop, modyfikując tabelę `ps_product_carrier` w celu ustanowienia powiązań. Zawiera również kontroler frontowy do wykonywania zadań cron, umożliwiając planowanie operacji masowych.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/cronjob.php`
        -   **Nazwa klasy i klasa nadrzędna**: `MassCarrierCronjobModuleFrontController` rozszerza `ModuleFrontController`.
        -   **Odpowiedzialność**: Ten kontroler jest zaprojektowany do wywoływania zewnętrznego, zazwyczaj przez zadanie cron po stronie serwera. Wykonuje zaplanowane zadania przypisywania przewoźników zdefiniowane w panelu administracyjnym. Nie renderuje żadnych wizualnych danych wyjściowych do przeglądarki, ale wykonuje przetwarzanie w tle. Obsługuje logikę pobierania oczekujących zadań z tabeli `masscarriercron` i stosowania zmian przewoźników do produktów.
-   **Kontrolery administracyjne Back-Office**:

    -   `controllers/admin/AdminMassCarrierCron.php`
        -   **Nazwa zakładki i zarządzana encja**: Ten kontroler zarządza encją `masscarriercron`, która reprezentuje zaplanowane zadania masowego przypisywania przewoźników. Tworzy nową zakładkę w panelu administracyjnym PrestaShop (prawdopodobnie w sekcji „Zaawansowane” lub niestandardowym menu „Masowy przewoźnik”).
        -   **Odpowiedzialność**: Zapewnia standardowy interfejs `AdminController` PrestaShop do listowania, dodawania, edytowania i usuwania zaplanowanych zadań cron. Obsługuje przesyłanie formularzy do tworzenia/aktualizowania zadań, walidacji danych wejściowych i interakcji z tabelą bazy danych `masscarriercron`.
    -   `controllers/admin/index.php`
        -   **Odpowiedzialność**: Jest to standardowy pusty plik `index.php` często umieszczany w katalogach modułów PrestaShop, aby zapobiec listowaniu katalogów, gdy są dostępne bezpośrednio przez przeglądarkę internetową. Nie zawiera żadnej logiki funkcjonalnej ani nie zarządza żadną encją.

### 4.3 Podstawowe klasy i modele (`classes/`)

Dossier modułu nie wskazuje żadnych niestandardowych klas w katalogu `classes/`. Oznacza to, że podstawowa logika przypisywania przewoźników i zarządzania zadaniami cron jest prawdopodobnie obsługiwana bezpośrednio w głównym pliku `masscarrier.php` i odpowiednich kontrolerach, być może przy użyciu bezpośrednio `ObjectModel` PrestaShop `Product` i `Carrier`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `masscarrier/lib/searchTool/views/js/autocomplete.js`
    -   **Zakres**: Panel administracyjny.
    -   **Odpowiedzialność**: Ten skrypt prawdopodobnie zapewnia funkcjonalność autouzupełniania do wybierania konkretnych produktów na głównej stronie konfiguracji modułu. Nasłuchuje danych wprowadzanych przez użytkownika w wyznaczonym polu wyszukiwania produktów, wysyła żądania AJAX do kontrolera panelu administracyjnego (lub głównej metody `getContent()` modułu) w celu pobrania sugestii produktów i wyświetla je na liście rozwijanej. Obsługuje zdarzenia wyboru w celu dodania wybranych produktów do listy do masowego przypisania.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `masscarrier/lib/searchTool/views/css/autocomplete.css`
    -   **Zakres**: Stylizacja formularza administracyjnego panelu administracyjnego.
    -   **Odpowiedzialność**: Zapewnia stylizację dla pola wyszukiwania autouzupełniania i jego listy sugestii, zapewniając wizualną integrację z motywem panelu administracyjnego PrestaShop. Definiuje style dla pola wprowadzania, kontenera rozwijanego i poszczególnych elementów sugestii. Programiści mogą nadpisać te klasy w swoich niestandardowych motywach panelu administracyjnego, jeśli zajdzie taka potrzeba.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   Nie ma wymienionych konkretnych szablonów hooków, co sugeruje, że główna konfiguracja modułu jest obsługiwana za pośrednictwem `getContent()` i dedykowanych kontrolerów administracyjnych.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `masscarrier/lib/searchTool/views/scripts.tpl`
        -   **Cel**: Ten szablon prawdopodobnie zawiera niezbędny kod JavaScript dla narzędzia wyszukiwania autouzupełniania (np. `autocomplete.js`) i potencjalnie wbudowane konfiguracje JavaScript lub linki CSS. Prawdopodobnie jest on dołączony do głównego formularza konfiguracji modułu lub formularza kontrolera administracyjnego.
    -   `masscarrier/masscarrier.tpl`
        -   **Cel**: Jest to główny szablon konfiguracji modułu, renderowany przez metodę `getContent()` pliku `masscarrier.php`. Zawiera strukturę HTML do wyboru przewoźników, wyboru grup produktów (kategorie, producenci, konkretne produkty) oraz przycisk „Przypisz przewoźników”. Prawdopodobnie zawiera `scripts.tpl` dla funkcjonalności autouzupełniania.
    -   `masscarrier/views/button-subcategories.tpl`
        -   **Cel**: Ten szablon prawdopodobnie renderuje przycisk lub sekcję związaną z zarządzaniem podkategoriami, być może do rozwijania/zwijania drzew kategorii w interfejsie wyboru produktów lub do konkretnych działań związanych z wyborem podkategorii.
-   **Szablony Front-Office (`views/templates/front/`)**:

    -   Nie ma wymienionych szablonów front-office, co jest zgodne z administracyjnym charakterem modułu w panelu administracyjnym.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_masscarriercron`: Ta niestandardowa tabela przechowuje szczegóły zaplanowanych zadań masowego przypisywania przewoźników. Zazwyczaj zawierałaby pola takie jak:
        -   `id_masscarriercron`: Klucz podstawowy.
        -   `carriers`: Zserializowana tablica lub ciąg identyfikatorów przewoźników oddzielonych przecinkami.
        -   `product_selection_type`: (np. 'category', 'manufacturer', 'product').
        -   `product_selection_ids`: Zserializowana tablica lub ciąg identyfikatorów kategorii/producentów/produktów oddzielonych przecinkami.
        -   `frequency`: (np. 'daily', 'weekly', 'once').
        -   `last_run`: DATETIME ostatniego wykonania.
        -   `active`: BOOLEAN wskazujący, czy zadanie jest włączone.
    -   Moduł głównie współdziała z podstawowymi tabelami PrestaShop:
        -   `ps_product_carrier`: Jest to kluczowa tabela, która przechowuje relację wiele-do-wielu między produktami a przewoźnikami. Moduł wstawia/aktualizuje rekordy w tej tabeli.
        -   `ps_product`: Do pobierania informacji o produkcie.
        -   `ps_category_product`: Do łączenia produktów z kategoriami.
        -   `ps_product_supplier` / `ps_manufacturer`: Do łączenia produktów z producentami.
        -   `ps_carrier`: Do pobierania informacji o przewoźniku.
-   **Tabela zarejestrowanych hooków**:
    Opis modułu wspomina o „Hookach Front-Office: Nagłówek, Kolumny, Produkt lub Stopka”, ale na podstawie inwentaryzacji kodu i celu modułu jest bardzo mało prawdopodobne, aby rejestrował jakiekolwiek hooki front-office do wyświetlania wizualnego. Mogą to być ogólne symbole zastępcze lub odnosić się do wewnętrznych hooków używanych do inicjalizacji modułu lub przetwarzania danych.

    Moduł używałby głównie wewnętrznych hooków PrestaShop do swojej funkcjonalności:

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `actionModuleInstall` | Podczas instalacji modułu | Tworzy tabelę `ps_masscarriercron`, rejestruje zakładki administracyjne. |
    | `actionModuleUninstall` | Podczas deinstalacji modułu | Usuwa tabelę `ps_masscarriercron`, wyrejestrowuje zakładki administracyjne. |
    | `actionAdminControllerSetMedia` | Po załadowaniu kontrolera administracyjnego | Wstrzykuje zasoby JS/CSS dla formularzy panelu administracyjnego (np. autocomplete.js, autocomplete.css). |
    | `displayBackOfficeHeader` | Renderuje w nagłówku panelu administracyjnego | Może zawierać globalne JS/CSS panelu administracyjnego lub konfigurację. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Przypisz przewoźnika do produktów masowo”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu zapewnia bezpośrednie wsparcie i gwarantuje dostęp do najbardziej kompatybilnych i bogatych w funkcje wersji modułu dla Twojego sklepu PrestaShop.
"""
