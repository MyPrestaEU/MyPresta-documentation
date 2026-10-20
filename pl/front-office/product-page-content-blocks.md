---
title: "Bloki treści na stronie produktu - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Bloki treści na stronie produktu” od MyPresta.eu."
sidebar:
  label: "Bloki treści na stronie produktu - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product page content blocks na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-content-blocks.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-page-content-blocks/)
>
> ---


# Bloki treści na stronie produktu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do instalacji PrestaShop, a ten moduł nie wprowadza żadnych dodatkowych specyficznych wymagań poza tymi.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Bloki treści na stronie produktu” działa głównie poprzez dedykowaną zakładkę na stronie edycji każdego produktu, a nie poprzez jeden globalny ekran konfiguracji. Istnieje jednak główna strona konfiguracji modułu do początkowej konfiguracji oraz kontroler AJAX do zarządzania blokami.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po pierwszej instalacji modułu i kliknięciu „Konfiguruj” zostaniesz przeniesiony na jego główną stronę konfiguracji. Strona ta zazwyczaj obsługuje początkową konfigurację lub ustawienia globalne, jeśli takie istnieją.

-   **Co robi to ustawienie:** Ta strona służy jako punkt wejścia do modułu. Chociaż podstawowa funkcjonalność tworzenia bloków odbywa się na stronach produktów, ten ekran może oferować ogólne ustawienia lub szybki przegląd.
-   **Efekt zmiany tego ustawienia:** Wszelkie ustawienia tutaj miałyby zastosowanie globalnie do sposobu działania modułu na wszystkich stronach produktów, takie jak całkowite włączanie/wyłączanie modułu lub ustawianie domyślnych zachowań.
-   **Zalecana wartość:** Postępuj zgodnie z instrukcjami wyświetlanymi na ekranie. Jeśli nie ma konkretnych ustawień, ta strona po prostu potwierdzi, że moduł jest zainstalowany i gotowy do użycia.
-   **Scenariusz/przykład dla sprzedawcy:** Możesz znaleźć tutaj przełącznik „Włącz/Wyłącz moduł”, który wyłączy wszystkie niestandardowe bloki treści w Twoim sklepie bez odinstalowywania modułu.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Główna interakcja z tym modułem odbywa się na stronie edycji produktu.

#### 2.2.1 Strona edycji produktu (Katalog > Produkty > Edytuj produkt)

Po zainstalowaniu modułu, podczas edycji dowolnego produktu w panelu administracyjnym PrestaShop, znajdziesz nową zakładkę dedykowaną „Blokom treści na stronie produktu” (lub podobnej nazwie).

-   **Nazwa ekranu i lokalizacja w menu:** **Katalog > Produkty > [Wybierz/Edytuj produkt] > zakładka „Bloki treści na stronie produktu”**
-   **Dostępne działania i ustawienia:**

    -   **Dodawanie nowego bloku:** Zazwyczaj zobaczysz przycisk, taki jak „Dodaj nowy blok” lub podobny interfejs do tworzenia nowego bloku treści dla bieżącego produktu.
        -   **Co robi to ustawienie:** Umożliwia zdefiniowanie nowego fragmentu treści.
        -   **Efekt zmiany tego ustawienia:** Zostanie utworzony i zapisany nowy blok treści dla tego konkretnego produktu.
        -   **Scenariusz/przykład dla sprzedawcy:** Chcesz dodać samouczek wideo dla złożonego produktu. Klikasz „Dodaj nowy blok”.
    -   **Edytor treści:** Dla każdego bloku będziesz mieć edytor tekstu sformatowanego (WYSIWYG), w którym możesz wprowadzać tekst, obrazy, filmy, a nawet niestandardowy kod HTML.
        -   **Co robi to ustawienie:** Definiuje rzeczywistą treść, która zostanie wyświetlona.
        -   **Efekt zmiany tego ustawienia:** Treść, którą tutaj wprowadzisz, zostanie wyrenderowana w sklepie.
        -   **Scenariusz/przykład dla sprzedawcy:** Wpisujesz „Obejrzyj nasz film z rozpakowywania!” i osadzasz link do filmu z YouTube.
    -   **Wybór hooka:** Rozwijana lista lub lista dostępnych hooków PrestaShop (`displayHeader`, `displayFooterProduct`, `displayRightColumnProduct` itp.).
        -   **Co robi to ustawienie:** Określa dokładną pozycję, w której Twój blok treści pojawi się na stronie produktu.
        -   **Efekt zmiany tego ustawienia:** Blok zostanie wyrenderowany w wybranej pozycji hooka.
        -   **Zalecana wartość:** Wybierz hook, który najlepiej odpowiada celowi treści. Dla szczegółów specyficznych dla produktu, `displayProductAdditionalInfo` lub `displayFooterProduct` są powszechne. Dla elementów zaufania, `displayReassurance`.
        -   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby odznaka zaufania pojawiła się w pobliżu przycisku „Dodaj do koszyka”, więc wybierasz `displayReassurance`.
    -   **Status bloku (Włączony/Wyłączony):** Przełącznik do aktywowania lub dezaktywowania bloku.
        -   **Co robi to ustawienie:** Kontroluje, czy blok jest widoczny w sklepie.
        -   **Efekt zmiany tego ustawienia:**
          -   *Gdy włączony:* Blok pojawi się na stronie produktu.
          -   *Gdy wyłączony:* Blok zostanie ukryty, ale nie usunięty, co pozwala na jego ponowną aktywację później.
        -   **Zalecana wartość:** Włącz bloki, które chcesz wyświetlać, wyłącz te, które chcesz tymczasowo ukryć.
        -   **Scenariusz/przykład dla sprzedawcy:** Masz blok promocji sezonowej, który chcesz ukryć po zakończeniu sezonu, ale możesz go ponownie wykorzystać w przyszłym roku.
    -   **Kolejność/Pozycja:** Często interfejs przeciągnij i upuść lub pole wprowadzania do ustawiania kolejności wyświetlania, jeśli wiele bloków znajduje się w tym samym hooku.
        -   **Co robi to ustawienie:** Określa kolejność bloków w ramach jednego hooka.
        -   **Efekt zmiany tego ustawienia:** Bloki pojawią się w określonej kolejności.
        -   **Scenariusz/przykład dla sprzedawcy:** Masz trzy odznaki zaufania w `displayReassurance` i chcesz, aby odznaka „Darmowa wysyłka” pojawiła się jako pierwsza.
    -   **Edycja/Usuwanie bloków:** Przyciski do modyfikowania istniejących bloków lub całkowitego ich usuwania.
        -   **Co robi to ustawienie:** Umożliwia aktualizację treści, hooka lub statusu, lub trwałe usunięcie bloku.
        -   **Efekt zmiany tego ustawienia:** Aktualizuje lub usuwa blok ze strony produktu.
        -   **Scenariusz/przykład dla sprzedawcy:** Opis produktu uległ zmianie, więc edytujesz treść powiązanego bloku.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

    1.  Przejdź do **Katalog > Produkty** i wybierz produkt, który chcesz ulepszyć.
    2.  Kliknij zakładkę „Bloki treści na stronie produktu”.
    3.  Kliknij „Dodaj nowy blok”, aby utworzyć nową sekcję treści.
    4.  Wprowadź swoją treść za pomocą edytora tekstu sformatowanego.
    5.  Wybierz odpowiedni hook, w którym chcesz, aby treść się pojawiła.
    6.  Upewnij się, że blok jest włączony.
    7.  Zapisz zmiany dla produktu.
    8.  Powtórz dla innych produktów w razie potrzeby. Regularnie przeglądaj strony produktów, aby upewnić się, że bloki wyświetlają się zgodnie z zamierzeniami.

#### 2.2.2 AdminMegablocksAjaxController (megablocks/controllers/admin/AdminMegablocksAjax.php)

Ten kontroler nie jest bezpośrednio dostępny dla sprzedawców poprzez element menu. Zamiast tego, obsługuje operacje w tle (żądania AJAX), gdy wchodzisz w interakcję z zakładką „Bloki treści na stronie produktu” na stronie edycji produktu. Na przykład, gdy zapisujesz nowy blok, edytujesz istniejący lub zmieniasz jego kolejność, ten kontroler przetwarza te żądania bez konieczności pełnego przeładowania strony.

-   **Nazwa ekranu i lokalizacja w menu:** Niedostępny bezpośrednio. Działa w tle na stronie edycji produktu.
-   **Dostępne działania i ustawienia:** Zarządza tworzeniem, aktualizowaniem, usuwaniem i zmianą kolejności bloków treści dla poszczególnych produktów.
-   **Efekt zmian:** Zapewnia, że Twoje zmiany w blokach treści na stronie edycji produktu są zapisywane w bazie danych i odzwierciedlane w sklepie.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Z tym kontrolerem wchodzisz w interakcję pośrednio, używając zakładki „Bloki treści na stronie produktu” na stronie edycji produktu. Bezpośrednia interakcja nie jest wymagana.

#### 2.2.3 index.php (megablocks/controllers/admin/index.php)

Ten plik jest standardową praktyką PrestaShop w celu zabezpieczenia katalogów kontrolerów administracyjnych i zazwyczaj zawiera tylko instrukcję `die('Access Denied');`. Nie reprezentuje on funkcjonalnego ekranu ani obszaru konfiguracji dla sprzedawcy.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | (Ustawienia globalne, jeśli istnieją) | (Zgodnie z domyślnymi ustawieniami modułu) | Początkowa konfiguracja, globalne włączanie/wyłączanie lub ogólne zachowanie modułu. |
| **Strona edycji produktu (zakładka)** | Dodaj nowy blok | N/A | Tworzy nowy blok treści dla bieżącego produktu. |
| | Edytor treści | Pusty | Definiuje zawartość HTML/tekstową bloku. |
| | Wybór hooka | Różne (np. `displayFooterProduct`) | Określa pozycję wyświetlania na stronie produktu. |
| | Status bloku | Włączony | Kontroluje widoczność bloku w sklepie. |
| | Kolejność/Pozycja | 1 (lub następna dostępna) | Ustawia kolejność wyświetlania bloków w ramach hooka. |
| | Edytuj/Usuń blok | N/A | Modyfikuje lub usuwa istniejące bloki treści. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Mój nowy blok treści nie wyświetla się na stronie produktu. Co powinienem zrobić?**
**O1:**

1.  **Sprawdź status bloku:** Przejdź do strony edycji produktu, przejdź do zakładki „Bloki treści na stronie produktu” i upewnij się, że utworzony blok jest ustawiony na „Włączony”.
2.  **Wyczyść pamięć podręczną:** PrestaShop używa pamięci podręcznej, aby przyspieszyć działanie Twojego sklepu. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty”, jeśli jest dostępna).
3.  **Zweryfikuj wybór hooka:** Sprawdź dokładnie, czy wybrałeś hook, który jest faktycznie renderowany przez Twój motyw na stronie produktu. Niektóre motywy mogą nie używać wszystkich standardowych hooków PrestaShop.
4.  **Kompatybilność z motywem:** Jeśli Twój motyw jest mocno dostosowany, może on nadpisywać standardowe miejsca hooków. Skontaktuj się z twórcą motywu lub webmasterem, aby potwierdzić strukturę hooków motywu.

**P2: Blok treści wygląda dziwnie lub jest nieostylowany na mojej stronie produktu.**
**O2:**

1.  **Sprawdź swoją treść:** Jeśli dodałeś niestandardowy kod HTML lub skopiowałeś treść z innego źródła, może ona zawierać sprzeczne style. Spróbuj najpierw wkleić treść do prostego edytora tekstu, aby usunąć wszelkie ukryte formatowanie, a następnie wklej ją ponownie do edytora modułu.
2.  **CSS modułu:** Moduł zawiera podstawowy CSS. Jeśli Twój motyw ma bardzo specyficzne style, może on nadpisywać lub kolidować ze stylami modułu.
3.  **Niestandardowe style motywu:** W przypadku zaawansowanego stylizowania, może być konieczne, aby webmaster dodał niestandardowe reguły CSS do arkusza stylów Twojego motywu, aby blok pasował do projektu Twojego sklepu. Mogą one celować w konkretne elementy HTML generowane przez moduł.

**P3: Czy mogę używać tego modułu w sklepach wielojęzycznych?**
**O3:** Tak, zazwyczaj bloki treści utworzone za pomocą tego modułu będą obsługiwać funkcjonalność wielojęzyczną PrestaShop. Podczas edycji bloku powinieneś zobaczyć zakładki językowe (np. angielski, francuski, hiszpański) obok edytora treści. Możesz wprowadzić różne treści dla każdego języka, zapewniając, że Twoje bloki są zlokalizowane dla Twoich międzynarodowych klientów.

**P4: Chcę wyświetlić ten sam blok na wielu stronach produktów. Czy muszę go tworzyć wielokrotnie?**
**O4:** Ten moduł jest przeznaczony do treści *specyficznych dla produktu*. Jeśli potrzebujesz *dokładnie tego samego* bloku treści na wielu produktach, musiałbyś go obecnie tworzyć dla każdego produktu. W przypadku treści naprawdę globalnych, które pojawiają się na *wszystkich* stronach produktów (lub wszystkich stronach określonego typu), bardziej efektywny może być inny typ modułu (np. moduł niestandardowego bloku HTML, który działa globalnie). Jednak siłą tego modułu jest jego zdolność do dostosowywania treści do każdego produktu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu „Bloki treści na stronie produktu” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł „Bloki treści na stronie produktu” (`megablocks`) stosuje standardową architekturę modułu PrestaShop, wykorzystując głównie klasę `Module` do instalacji i rejestracji hooków. Jego podstawowa funkcjonalność koncentruje się na zarządzaniu blokami treści specyficznymi dla produktu, które są przechowywane w niestandardowej tabeli bazy danych. Moduł rozszerza funkcjonalność panelu administracyjnego PrestaShop, wstrzykując niestandardową zakładkę na stronę edycji produktu, zarządzaną przez kontroler AJAX. Wyświetlanie w sklepie jest realizowane poprzez podłączenie do różnych hooków `display*` na stronie produktu i renderowanie określonych szablonów Smarty.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery sklepu (`Front-Office Controllers`)**: Ten moduł nie zawiera żadnych dedykowanych kontrolerów sklepu. Całe renderowanie treści w sklepie jest obsługiwane bezpośrednio za pośrednictwem zarejestrowanych hooków w głównym pliku modułu `index.php`, który następnie renderuje określone szablony.
-   **Kontrolery panelu administracyjnego (`Back-Office Admin Controllers`)**:

    -   `megablocks/controllers/admin/AdminMegablocksAjax.php`
        -   **Nazwa klasy i klasa nadrzędna**: `AdminMegablocksAjaxController` rozszerzający `ModuleAdminController`.
        -   **Odpowiedzialność**: Ten kontroler obsługuje wszystkie żądania AJAX pochodzące z zakładki „Bloki treści na stronie produktu” na stronie edycji produktu. Jest odpowiedzialny za:
            -   Tworzenie nowych bloków treści.
            -   Aktualizowanie istniejących bloków treści (treść, hook, status, pozycja).
            -   Usuwanie bloków treści.
            -   Pobieranie danych bloków treści dla konkretnego produktu.
            -   Nie ma bezpośredniego wpisu w menu, ale jest wywoływany za pośrednictwem wywołań JavaScript ze strony edycji produktu.
    -   `megablocks/controllers/admin/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: Nie jest to funkcjonalny kontroler.
        -   **Odpowiedzialność**: Jest to plik zabezpieczający, standardowy w katalogach administracyjnych PrestaShop, zawierający `die('Access Denied');` w celu zapobiegania bezpośredniemu listowaniu katalogów lub dostępowi.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Dossier modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Oznacza to, że obsługa danych modułu (np. zapisywanie i pobieranie bloków treści) jest prawdopodobnie zarządzana bezpośrednio w głównym pliku `megablocks/index.php`, potencjalnie przy użyciu `Db::getInstance()` do bezpośrednich interakcji z bazą danych lub prostej struktury tablicowej do konfiguracji. Jeśli używana jest niestandardowa tabela bazy danych, jej schemat i metody interakcji byłyby zdefiniowane w głównym pliku modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `megablocks/js/script.js`
    -   **Zakres**: Prawdopodobnie sklep.
    -   **Szczegóły**: Ten skrypt zawierałby wszelką logikę po stronie klienta wymaganą do wyświetlania bloków treści w sklepie. Może to obejmować proste animacje, responsywne dostosowania lub interakcje, jeśli bloki zawierają elementy dynamiczne.
-   `megablocks/views/admin/megablocks.js`
    -   **Zakres**: Panel administracyjny (strona edycji produktu).
    -   **Szczegóły**: Jest to główny plik JavaScript do zarządzania blokami treści w panelu administracyjnym. Jest odpowiedzialny za:
        -   Inicjalizację zakładki „Bloki treści na stronie produktu” na stronie edycji produktu.
        -   Obsługę zdarzeń kliknięcia dla przycisków „Dodaj nowy blok”, „Edytuj” i „Usuń”.
        -   Zarządzanie edytorem tekstu sformatowanego (np. integracja TinyMCE lub CKEditor) do wprowadzania treści.
        -   Wysyłanie żądań AJAX do `AdminMegablocksAjaxController` w celu tworzenia, aktualizowania i usuwania bloków.
        -   Dynamiczne aktualizowanie interfejsu użytkownika na podstawie odpowiedzi AJAX (np. dodawanie nowego bloku do listy, usuwanie usuniętego bloku).
        -   Implementację funkcji przeciągnij i upuść do zmiany kolejności bloków.
-   `megablocks/views/fancybox/script.js`
    -   **Zakres**: Panel administracyjny (strona edycji produktu).
    -   **Szczegóły**: Ten skrypt prawdopodobnie integruje się z „Fancybox” (lub podobną biblioteką modalną/lightbox) lub ją implementuje w celu wyświetlania formularzy „Dodaj nowy blok” lub „Edytuj blok” w wyskakującym oknie. Obsługiwałby otwieranie/zamykanie modalu, ładowanie do niego treści i przesyłanie danych formularza.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `megablocks/views/admin/megablocks.css`
    -   **Zakres**: Stylizacja formularzy administracyjnych panelu administracyjnego.
    -   **Szczegóły**: Zawiera specyficzne reguły CSS do stylizowania zakładki „Bloki treści na stronie produktu”, listy bloków, formularzy dodawania/edycji i wszelkich niestandardowych elementów interfejsu użytkownika w panelu administracyjnym PrestaShop.
    -   **Kluczowe selektory klas CSS**: Programiści mogą sprawdzić wygenerowany kod HTML na stronie edycji produktu, aby zidentyfikować konkretne klasy (np. `.megablocks-list`, `.megablock-item`, `.megablock-form`) w celu nadpisania lub rozszerzenia w swoim niestandardowym motywie administracyjnym lub nadpisaniach modułu.
-   `megablocks/views/css/milligram.css`
    -   **Zakres**: Potencjalnie zarówno sklep, jak i panel administracyjny, lub specjalnie dla formularzy modalnych.
    -   **Szczegóły**: Milligram to minimalistyczny framework CSS. Jego włączenie sugeruje, że moduł może go używać do podstawowego, czystego stylizowania generowanych bloków treści w sklepie lub do formularzy modalnych w panelu administracyjnym (np. zawartości Fancybox). Zapewnia lekką podstawę dla typografii, formularzy i układu siatki.
    -   **Kluczowe selektory klas CSS**: Standardowe klasy Milligram (np. `.container`, `.row`, `.column`, `.button`, `.input`) byłyby obecne. Programiści mogą je nadpisywać lub dodawać bardziej specyficzne style w CSS swojego motywu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/front/`)**: Te szablony są dynamicznie dołączane przez moduł, gdy blok treści jest skonfigurowany dla określonego hooka. Każdy plik `megablock-*.tpl` prawdopodobnie służy jako opakowanie lub standardowy szablon do renderowania zawartości pojedynczego bloku. Rzeczywista treść (HTML) zdefiniowana przez sprzedawcę jest zazwyczaj przekazywana jako zmienna Smarty i renderowana bezpośrednio.

    -   `megablocks/views/front/megablock-actionProductOutOfStock.tpl`: Renderuje treść, gdy produkt jest niedostępny.
    -   `megablocks/views/front/megablock-displayAfterProductThumbs.tpl`: Renderuje treść po obrazach/miniaturach produktu.
    -   `megablocks/views/front/megablock-displayBeforeBodyClosingTag.tpl`: Renderuje treść tuż przed tagiem `</body>`.
    -   `megablocks/views/front/megablock-displayFooter.tpl`: Renderuje treść w ogólnej stopce witryny.
    -   `megablocks/views/front/megablock-displayFooterBefore.tpl`: Renderuje treść przed ogólną stopką witryny.
    -   `megablocks/views/front/megablock-displayFooterProduct.tpl`: Renderuje treść w obszarze stopki specyficznym dla produktu.
    -   `megablocks/views/front/megablock-displayHeader.tpl`: Renderuje treść w ogólnym nagłówku witryny.
    -   `megablocks/views/front/megablock-displayLeftColumnProduct.tpl`: Renderuje treść w lewej kolumnie strony produktu.
    -   `megablocks/views/front/megablock-displayNav1.tpl`: Renderuje treść w pierwszym obszarze nawigacji.
    -   `megablocks/views/front/megablock-displayNav2.tpl`: Renderuje treść w drugim obszarze nawigacji.
    -   `megablocks/views/front/megablock-displayProductAdditionalInfo.tpl`: Renderuje treść w sekcji dodatkowych informacji o produkcie.
    -   `megablocks/views/front/megablock-displayProductPriceBlock.tpl`: Renderuje treść w pobliżu bloku ceny produktu.
    -   `megablocks/views/front/megablock-displayReassurance.tpl`: Renderuje treść w bloku zapewnienia (np. odznaki zaufania).
    -   `megablocks/views/front/megablock-displayRightColumnProduct.tpl`: Renderuje treść w prawej kolumnie strony produktu.
    -   `megablocks/views/front/megablock-displayTop.tpl`: Renderuje treść w górnej sekcji strony.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `megablocks/views/admin/li_megablock.tpl`: Ten szablon jest prawdopodobnie używany do renderowania pojedynczego elementu na liście bloków treści na stronie edycji produktu. Wyświetlałby tytuł bloku, wybrany hook, status oraz przyciski edycji/usuwania.
    -   `megablocks/views/admin/tabs.tpl`: Ten szablon prawdopodobnie definiuje strukturę samej zakładki „Bloki treści na stronie produktu”, w tym przycisk „Dodaj nowy blok” i kontener na listę bloków.
-   **Szablony Fancybox (`views/fancybox/`)**: Te szablony są używane do formularzy modalnych (Fancybox) w panelu administracyjnym.

    -   `megablocks/views/fancybox/edit.tpl`: Szablon formularza do edycji istniejącego bloku treści.
    -   `megablocks/views/fancybox/heading.tpl`: Szablon nagłówka lub tytułu modalu Fancybox.
    -   `megablocks/views/fancybox/new.tpl`: Szablon formularza do tworzenia nowego bloku treści.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł prawdopodobnie tworzy niestandardową tabelę bazy danych, na przykład `ps_megablocks` (lub podobną), do przechowywania bloków treści.
    -   Tabela ta zazwyczaj zawierałaby pola takie jak:
        -   `id_megablock`: Klucz podstawowy.
        -   `id_product`: Klucz obcy łączący z `ps_product`.
        -   `hook_name`: Nazwa hooka PrestaShop, w którym wyświetlany jest blok (np. `displayFooterProduct`).
        -   `position`: Kolejność bloku w ramach jego hooka.
        -   `active`: Wartość logiczna (0 lub 1) dla statusu bloku.
        -   `content`: Rzeczywista zawartość HTML bloku (prawdopodobnie pole `TEXT` lub `LONGTEXT`).
        -   `content_lang`: Jeśli treść jest wielojęzyczna, może to być oddzielna tabela (`ps_megablocks_lang`) lub obsługa za pomocą serializowanych danych w `content`.
    -   Rekordy konfiguracji są przechowywane w `ps_configuration` dla globalnych ustawień modułu (np. `MEGABLOCKS_ENABLED`).
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| :--- | :---

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Bloki treści na stronie produktu”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu i jego integracji z Twoim sklepem PrestaShop.
"""
