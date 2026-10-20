---
title: "Krok po kroku - kategorie - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Krok po kroku - kategorie” od MyPresta.eu."
sidebar:
  label: "Krok po kroku - kategorie - Podręcznik Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Step by step - categories na MyPresta.eu](https://mypresta.eu/modules/front-office-features/step-by-step-categories.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/step-by-step-categories/)
>
> ---


# Krok po kroku - kategorie

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Brak specjalnych wymagań serwerowych poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównego ekranu konfiguracji modułu „Krok po kroku - kategorie”. Tutaj kontrolujesz, jak moduł działa i wygląda w Twoim sklepie.

| Ustawienie / Opcja | Co robi to ustawienie | Efekt zmiany tego ustawienia | Zalecana wartość | Scenariusz / przykład dla sprzedawcy |
| --- | --- | --- | --- | --- |
| **Wyświetl blok w nagłówku** | Kontroluje, czy nawigacja kategorii krok po kroku pojawia się w sekcji nagłówka Twojego sklepu. | *Gdy włączone:* Rozwijane listy kategorii będą widoczne na górze Twojej strony internetowej, często w pobliżu logo lub głównej nawigacji. Zapewnia to natychmiastowy dostęp do filtrowania kategorii. *Gdy wyłączone:* Blok nie pojawi się w nagłówku. | **TAK** (jeśli chcesz widocznej nawigacji) | Chcesz, aby klienci łatwo znajdowali produkty z dowolnej strony, więc umieszczenie go w nagłówku sprawia, że jest zawsze dostępny. |
| **Wyświetl blok w lewej kolumnie** | Kontroluje, czy nawigacja kategorii krok po kroku pojawia się w lewym pasku bocznym Twojego sklepu. | *Gdy włączone:* Rozwijane listy kategorii będą widoczne w lewej kolumnie Twojej strony internetowej (jeśli Twój motyw obsługuje lewą kolumnę). Jest to tradycyjne umiejscowienie dla filtrów kategorii. *Gdy wyłączone:* Blok nie pojawi się w lewej kolumnie. | **TAK** (jeśli Twój motyw ma lewą kolumnę i chcesz nawigacji w pasku bocznym) | Twój motyw ma lewy pasek boczny, a Ty wolisz, aby elementy nawigacji były tam uporządkowane, podobnie jak standardowe drzewo kategorii. |
| **Wyświetl blok w prawej kolumnie** | Kontroluje, czy nawigacja kategorii krok po kroku pojawia się w prawym pasku bocznym Twojego sklepu. | *Gdy włączone:* Rozwijane listy kategorii będą widoczne w prawej kolumnie Twojej strony internetowej (jeśli Twój motyw obsługuje prawą kolumnę). *Gdy wyłączone:* Blok nie pojawi się w prawej kolumnie. | **NIE** (chyba że Twój motyw specjalnie używa prawej kolumny do nawigacji) | Twój motyw używa prawej kolumny do informacji uzupełniających, a Ty chcesz umieścić tam nawigację kategorii zamiast w lewej. |
| **Wyświetl blok w stopce** | Kontroluje, czy nawigacja kategorii krok po kroku pojawia się w sekcji stopki Twojego sklepu. | *Gdy włączone:* Rozwijane listy kategorii będą widoczne na dole Twojej strony internetowej. Jest to mniej powszechne dla głównej nawigacji, ale może być przydatne dla dodatkowego dostępu. *Gdy wyłączone:* Blok nie pojawi się w stopce. | **NIE** (chyba że z konkretnych powodów projektowych) | Masz bardzo minimalistyczny nagłówek i kolumny, a chcesz zaoferować nawigację kategorii w stopce jako alternatywę dla użytkowników, którzy przewijają w dół. |
| **Wyświetl blok na stronie produktu** | Kontroluje, czy nawigacja kategorii krok po kroku pojawia się na poszczególnych stronach produktów. | *Gdy włączone:* Rozwijane listy kategorii będą widoczne na stronach szczegółów produktu. Może to pomóc klientom w eksploracji innych kategorii lub powiązanych produktów. *Gdy wyłączone:* Blok nie pojawi się na stronach produktów. | **NIE** (chyba że masz konkretną potrzebę, aby tam był) | Chcesz zachęcić klientów przeglądających produkt do łatwego przechodzenia do innych kategorii bez opuszczania strony produktu, być może w celu porównania przedmiotów. |
| **Pokaż przycisk „Idź”** | Określa, czy przycisk „Idź” lub „Szukaj” jest wyświetlany obok ostatniej rozwijanej listy kategorii. | *Gdy włączone:* Pojawi się przycisk. Klienci muszą kliknąć ten przycisk, aby zostać przekierowani na wybraną stronę kategorii. *Gdy wyłączone:* Klienci są automatycznie przekierowywani na wybraną stronę kategorii, gdy tylko dokonają ostatecznego wyboru w ostatniej rozwijanej liście. | **TAK** (dla większej kontroli) | Chcesz, aby klienci potwierdzili swój wybór kategorii przed przekierowaniem, dając im szansę na przejrzenie swojego wyboru. |
| **Liczba rozwijanych list** | Ustawia maksymalną liczbę poziomów kategorii (głębokość), które będą wyświetlane jako rozwijane listy. | *Gdy ustawione na 1:* Tylko kategorie najwyższego poziomu pojawią się w jednej rozwijanej liście. *Gdy ustawione na 3:* Wyświetlone zostaną do trzech poziomów kategorii (np. Kategoria główna > Podkategoria 1 > Podkategoria 2) w oddzielnych rozwijanych listach. | **3** (lub w zależności od głębokości Twoich kategorii) | Twój sklep ma kategorie zagnieżdżone do 3 lub 4 poziomów głębokości, a Ty chcesz, aby klienci mogli efektywnie drążyć w dół. |
| **Kategoria główna** | Określa punkt początkowy dla nawigacji kategorii. Wyświetlane będą tylko kategorie w ramach tej kategorii głównej. | *Gdy ustawione na „Strona główna”:* Dostępne będą wszystkie kategorie, począwszy od samego szczytu Twojego katalogu. *Gdy ustawione na „Elektronika”:* W rozwijanych listach będą wyświetlane tylko kategorie pod „Elektroniką” (np. „Laptopy”, „Smartfony”). | **Strona główna** (chyba że chcesz ograniczyć nawigację) | Chcesz oferować nawigację krok po kroku tylko dla konkretnej części swojego katalogu, takiej jak „Odzież”, i wykluczyć inne sekcje, takie jak „Dom i ogród”. |

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyświetl blok w nagłówku | TAK | Pokazuje rozwijane listy kategorii w nagłówku sklepu dla widocznej nawigacji. |
| Konfiguracja modułu | Wyświetl blok w lewej kolumnie | TAK | Pokazuje rozwijane listy kategorii w lewym pasku bocznym dla tradycyjnej nawigacji. |
| Konfiguracja modułu | Wyświetl blok w prawej kolumnie | NIE | Pokazuje rozwijane listy kategorii w prawym pasku bocznym. |
| Konfiguracja modułu | Wyświetl blok w stopce | NIE | Pokazuje rozwijane listy kategorii w stopce sklepu. |
| Konfiguracja modułu | Wyświetl blok na stronie produktu | NIE | Pokazuje rozwijane listy kategorii na stronach szczegółów produktu. |
| Konfiguracja modułu | Pokaż przycisk „Idź” | TAK | Wymaga od klientów kliknięcia przycisku, aby przejść do wybranej kategorii. |
| Konfiguracja modułu | Liczba rozwijanych list | 3 | Ustawia maksymalną głębokość wyświetlanych poziomów kategorii. |
| Konfiguracja modułu | Kategoria główna | Strona główna | Definiuje punkt początkowy dla nawigacji kategorii. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moduł jest zainstalowany, ale nie widzę rozwijanych list w moim sklepie.**
O1:

- **Sprawdź konfigurację:** Przejdź do **Moduły > Menedżer modułów > Krok po kroku - kategorie > Konfiguruj**. Upewnij się, że co najmniej jedna opcja „Wyświetl blok w…” (np. „Wyświetl blok w nagłówku”, „Wyświetl blok w lewej kolumnie”) jest ustawiona na **TAK**.
- **Wyczyść pamięć podręczną:** PrestaShop często buforuje zawartość. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
- **Kompatybilność z motywem:** Niektóre wysoce spersonalizowane motywy mogą wymagać drobnych dostosowań. Jeśli wyczyszczenie pamięci podręcznej nie pomoże, spróbuj tymczasowo przełączyć się na domyślny motyw PrestaShop, aby sprawdzić, czy moduł się pojawi. Jeśli tak, Twój motyw może nadpisywać standardowe pozycje haków.

**P2: Rozwijane listy pojawiają się, ale nie aktualizują się po wybraniu kategorii.**
O2:

- **Problemy z AJAX:** Zazwyczaj wskazuje to na błąd JavaScript. Otwórz konsolę programisty przeglądarki (F12) i sprawdź, czy w zakładce „Konsola” nie ma żadnych błędów.
- **Konfliktujący JavaScript:** Inny moduł lub JavaScript Twojego motywu może powodować zakłócenia. Spróbuj wyłączyć inne moduły front-office jeden po drugim, aby zidentyfikować konflikty.
- **Pliki modułu:** Upewnij się, że wszystkie pliki modułu zostały poprawnie przesłane i nie są uszkodzone. Ponowne przesłanie modułu może rozwiązać ten problem.

**P3: Jak zmienić styl (kolory, czcionki, rozmiar) rozwijanych list?**
O3:

- Moduł używa standardowego CSS. Będziesz potrzebować podstawowej wiedzy o CSS lub pomocy webmastera.
- Pliki CSS modułu (np. `sbs-block.css`, `sbs-header.css`) definiują domyślne style.
- **Najlepsza praktyka:** NIE modyfikuj bezpośrednio plików CSS modułu, ponieważ Twoje zmiany zostaną utracone podczas aktualizacji. Zamiast tego użyj niestandardowego pliku CSS swojego motywu (często znajdującego się w `themes/yourtheme/assets/css/custom.css` lub podobnym), aby nadpisać style modułu. Użyj inspektora przeglądarki (F12), aby zidentyfikować klasy CSS używane przez rozwijane listy.

**P4: Moje kategorie są bardzo głębokie, ale widzę tylko kilka rozwijanych list.**
O4:

- **Ustawienie „Liczba rozwijanych list”:** Przejdź do **Moduły > Menedżer modułów > Krok po kroku - kategorie > Konfiguruj** i dostosuj ustawienie „Liczba rozwijanych list”. Zwiększ tę wartość, aby odpowiadała maksymalnej głębokości kategorii, które chcesz wyświetlić. Pamiętaj, że wyświetlanie zbyt wielu rozwijanych list może zaśmiecić interfejs.

**P5: Moduł pokazuje kategorie, których nie chcę uwzględniać w nawigacji krok po kroku.**
O5:

- **Ustawienie „Kategoria główna”:** W konfiguracji modułu użyj ustawienia „Kategoria główna”. Wybierz konkretną kategorię nadrzędną, od której chcesz rozpocząć nawigację krok po kroku. Wyświetlane będą tylko kategorie i podkategorie pod wybraną kategorią główną.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Krok po kroku - kategorie” to przede wszystkim funkcja front-office wykorzystująca architekturę modułów PrestaShop. Wykorzystuje standardową klasę `Module` do instalacji i konfiguracji oraz klasy `ModuleFrontController` do obsługi żądań AJAX do dynamicznego ładowania kategorii. Nie wprowadza niestandardowych klas `ObjectModel` ani tabel baz danych, polegając na natywnym obiekcie `Category` PrestaShop do danych. Moduł intensywnie wykorzystuje szablony Smarty do renderowania i JavaScript do interaktywnej funkcjonalności AJAX.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:
  - `controllers/front/ajaxload.php`
    - Nazwa klasy: `StepbystepAjaxloadModuleFrontController`
    - Klasa nadrzędna: `ModuleFrontController`
    - Odpowiedzialność: Ten kontroler jest rdzeniem funkcjonalności AJAX. Odpowiada na żądania z JavaScriptu front-office w celu pobrania podkategorii na podstawie ID kategorii nadrzędnej. Zazwyczaj zwraca dane JSON zawierające nazwy i ID kategorii do wypełniania kolejnych rozwijanych list.
  - `controllers/front/index.php`
    - Nazwa klasy: `StepbystepIndexModuleFrontController`
    - Klasa nadrzędna: `ModuleFrontController`
    - Odpowiedzialność: Ten kontroler prawdopodobnie służy jako domyślny punkt wejścia lub rezerwowy dla routingu front-office modułu, chociaż jego główna funkcja może być minimalna, biorąc pod uwagę charakter oparty na AJAX. Może obsługiwać początkową logikę wyświetlania lub przekierowania, gdyby moduł miał dedykowaną stronę.
  - `controllers/front/tree.php`
    - Nazwa klasy: `StepbystepTreeModuleFrontController`
    - Klasa nadrzędna: `ModuleFrontController`
    - Odpowiedzialność: Ten kontroler może być odpowiedzialny za renderowanie pełnej struktury drzewa kategorii, potencjalnie do debugowania lub alternatywnej metody wyświetlania, chociaż główną cechą modułu są rozwijane listy. Może być również używany do generowania początkowych danych dla pierwszej rozwijanej listy.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł nie zawiera żadnych niestandardowych klas w katalogu `classes/`. Bezpośrednio wykorzystuje podstawową klasę `Category` PrestaShop i inne funkcje pomocnicze do pobierania danych kategorii.

### 4.4 Zasoby JavaScript (`views/js/`)

- `stepbystep/js/advajax.js`
  - Zakres: Front-office
  - Jest to główny plik JavaScript odpowiedzialny za interaktywne zachowanie modułu.
  - Wiąże słuchaczy zdarzeń z elementami `<select>` rozwijanych list kategorii.
  - Po dokonaniu wyboru w rozwijanej liście, wyzwala żądanie AJAX (prawdopodobnie do `ajaxload.php`) w celu pobrania następnego poziomu podkategorii.
  - Dynamicznie tworzy i wypełnia kolejne rozwijane listy otrzymanymi danymi.
  - Obsługuje przekierowanie do końcowej strony kategorii po dokonaniu wyboru lub kliknięciu przycisku „Idź”.
  - Zarządza widocznością i stanem rozwijanych list na podstawie interakcji użytkownika i konfiguracji modułu (np. „Liczba rozwijanych list”).

### 4.5 Arkusze stylów CSS (`views/css/`)

- `stepbystep/css/sbs-block.css`
  - Zakres: Stylizacja klienta front-office
  - Stylizuje ogólny wygląd bloku kategorii krok po kroku, w tym dopełnienie, marginesy i ogólny układ, gdy jest umieszczony w kolumnach lub innych pozycjach przypominających bloki.
  - Kluczowe selektory: `.sbs-block`, `.sbs-category-select-wrapper`
- `stepbystep/css/sbs-header.css`
  - Zakres: Stylizacja klienta front-office
  - Specjalnie stylizuje moduł, gdy jest podłączony do pozycji `displayHeader`, potencjalnie dostosowując się do układów nagłówka (np. wyświetlanie w linii, określone szerokości).
  - Kluczowe selektory: `.sbs-header-container`
- `stepbystep/css/sbs-top.css`
  - Zakres: Stylizacja klienta front-office
  - Prawdopodobnie stylizuje moduł, gdy jest podłączony do `displayTop` lub podobnych pozycji na górze strony, podobnie do `sbs-header.css`, ale dla różnych kontekstów wizualnych.
  - Kluczowe selektory: `.sbs-top-container`
- `stepbystep/css.css`
  - Zakres: Stylizacja klienta front-office
  - Ogólny arkusz stylów, który może zawierać wspólne style mające zastosowanie we wszystkich miejscach docelowych lub style zastępcze.
  - Kluczowe selektory: `.sbs-select`, `.sbs-go-button`

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony haków (`views/templates/hook/`)**:

  - `block.tpl`: Ten szablon jest prawdopodobnie używany, gdy moduł jest podłączony do `displayLeftColumn` lub `displayRightColumn`. Renderuje rozwijane listy krok po kroku w standardowej strukturze bloku PrestaShop.
  - `blockSbs.tpl`: Może to być alternatywny lub bardziej ogólny szablon bloku, potencjalnie używany dla innych haków kolumn lub specyficznych niestandardowych miejsc docelowych.
  - `displaySearch.tpl`: Ten szablon może być przeznaczony do integracji w pobliżu paska wyszukiwania lub jako część haka związanego z wyszukiwaniem, dostarczając rozwijane listy jako narzędzie do doprecyzowania wyszukiwania.
  - `header.tpl`: Ten szablon jest używany, gdy moduł jest podłączony do `displayHeader`. Renderuje rozwijane listy w sekcji nagłówka sklepu.
  - `top.tpl`: Ten szablon jest używany, gdy moduł jest podłączony do `displayTop`. Podobnie jak `header.tpl`, ale dla haka `displayTop`, który jest często używany dla głównego paska nawigacji.
- **Szablony administracyjne (`views/templates/admin/`)**: Brak zidentyfikowanych. Konfiguracja jest obsługiwana bezpośrednio w `getContent()`.
- **Szablony front-office (`views/templates/front/`)**: Brak zidentyfikowanych jako samodzielne strony.

### 4.7 Schemat bazy danych i mapa haków

- **Tabele baz danych**: Moduł nie tworzy żadnych niestandardowych tabel SQL. Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop, używając kluczy takich jak `STEPMYSTEP_HEADER`, `STEPMYSTEP_LEFT`, `STEPMYSTEP_RIGHT`, `STEPMYSTEP_FOOTER`, `STEPMYSTEP_PRODUCT`, `STEPMYSTEP_GO_BUTTON`, `STEPMYSTEP_DROPDOWNS`, `STEPMYSTEP_ROOT_CATEGORY`.
- **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` HTML lub na samym początku `<body>` przed inną zawartością. | Wstrzykuje zasoby CSS/JS i potencjalnie strukturę HTML modułu, jeśli skonfigurowano dla wyświetlania w nagłówku. |
| `displayLeftColumn` | Renderuje zawartość w lewym pasku bocznym sklepu. | Wyświetla rozwijane listy kategorii krok po kroku w lewej kolumnie. |
| `displayRightColumn` | Renderuje zawartość w prawym pasku bocznym sklepu. | Wyświetla rozwijane listy kategorii krok po kroku w prawej kolumnie. |
| `displayFooter` | Renderuje zawartość w sekcji stopki sklepu. | Wyświetla rozwijane listy kategorii krok po kroku w stopce. |
| `displayProductAdditionalInfo` (lub podobny hak strony produktu) | Renderuje zawartość na stronie produktu, często poniżej opisu produktu lub w określonym bloku. | Wyświetla rozwijane listy kategorii krok po kroku na stronach produktów. |
| `displayTop` | Renderuje zawartość w górnej sekcji strony, zazwyczaj powyżej lub w ramach głównej nawigacji. | Wyświetla rozwijane listy kategorii krok po kroku w górnym pasku. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Krok po kroku - kategorie”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
