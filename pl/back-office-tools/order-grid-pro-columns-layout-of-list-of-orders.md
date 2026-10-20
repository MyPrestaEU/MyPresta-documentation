---
title: "Order Grid Pro - kolumny i układ listy zamówień - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop Order Grid Pro - kolumny i układ listy zamówień od MyPresta.eu."
sidebar:
  label: "Order Grid Pro - kolumny i układ listy zamówień - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Order Grid Pro - columns & layout of list of orders na MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-grid-pro-columns-layout-of-list-of-orders.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/order-grid-pro-columns-layout-of-list-of-orders/)
>
> ---


# Order Grid Pro - kolumny i układ listy zamówień

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.7.x, 1.7.8.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony konfiguracji Order Grid Pro. Na tej stronie definiujesz, które kolumny pojawiają się na liście zamówień i ich układ.

Konfiguracja jest zazwyczaj podzielona na kilka zakładek lub sekcji, co pozwala zarządzać różnymi aspektami siatki zamówień.

**Ustawienia ogólne / Widoczność i kolejność kolumn:**
To jest rdzeń modułu. Zazwyczaj zobaczysz listę wszystkich dostępnych kolumn, zarówno domyślnych kolumn PrestaShop, jak i nowych dodanych przez Order Grid Pro.

-   **Co robi to ustawienie:** Ta sekcja pozwala wybrać, które kolumny są widoczne na liście zamówień w Panelu Administracyjnym i uporządkować ich kolejność wyświetlania. Zazwyczaj zobaczysz dwie listy: „Dostępne kolumny” i „Aktywne kolumny” (lub podobne).
-   **Efekt zmiany tego ustawienia:**
    -   *Przeniesienie kolumny z „Dostępne” do „Aktywne”:* Kolumna pojawi się na liście zamówień w Panelu Administracyjnym.
    -   *Przeniesienie kolumny z „Aktywne” do „Dostępne”:* Kolumna zostanie ukryta z listy zamówień w Panelu Administracyjnym.
    -   *Przeciąganie i upuszczanie kolumn w obrębie „Aktywnych kolumn”:* Zmienia kolejność wyświetlania kolumn od lewej do prawej na liście zamówień.
-   **Zalecana wartość:** Jest to całkowicie zależne od potrzeb Twojego zespołu. Zacznij od włączenia kolumn, które często sprawdzasz, i ukrycia tych, których nigdy nie używasz. Uporządkuj je w logicznym ciągu dla swoich codziennych zadań.
-   **Scenariusz sprzedawcy / przykład:**
    -   **Kierownik magazynu:** Może włączyć „Miniatura produktu”, „Waga produktu”, „Numer śledzenia” i „Przewoźnik” i umieścić je widocznie po lewej stronie w celu szybkiego przetwarzania wysyłek. Może ukryć „E-mail klienta” lub „Metoda płatności”, jeśli nie są istotne dla jego roli.
    -   **Agent obsługi klienta:** Priorytetowo traktowałby „Telefon klienta”, „E-mail klienta”, „Fragment wątku obsługi klienta” i „Wiadomość do zamówienia”, aby szybko odpowiadać na zapytania bez otwierania każdego zamówienia.
    -   **Dział finansowy:** Może skupić się na „Metodzie płatności”, „ISO waluty”, „Całkowitej zapłaconej kwocie” i „Regułach koszyka”, aby weryfikować transakcje i rabaty.

**Opcje konkretnych kolumn (Przykłady nowych kolumn, które można włączyć):**

-   **Telefon klienta:**

    -   **Co robi to ustawienie:** Wyświetla numer telefonu klienta bezpośrednio na liście zamówień.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Numery telefonów pojawiają się, ułatwiając dzwonienie do klientów bez przechodzenia do szczegółów ich zamówienia.
        -   *Po wyłączeniu:* Numery telefonów są ukryte.
    -   **Zalecana wartość:** TAK, jeśli Twój zespół obsługi klienta lub wysyłki często potrzebuje kontaktować się z klientami.
    -   **Scenariusz sprzedawcy / przykład:** Agent obsługi klienta może szybko zadzwonić do klienta w sprawie problemu z dostawą bezpośrednio z listy zamówień.
-   **Numer śledzenia:**

    -   **Co robi to ustawienie:** Pokazuje numer śledzenia powiązany z zamówieniem.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Numery śledzenia są widoczne, co pozwala na szybkie kopiowanie i wklejanie w celu aktualizacji statusu śledzenia.
        -   *Po wyłączeniu:* Numery śledzenia są ukryte.
    -   **Zalecana wartość:** TAK, niezbędne dla zespołów magazynowych i obsługi klienta.
    -   **Scenariusz sprzedawcy / przykład:** Personel magazynu może szybko sprawdzić, czy numer śledzenia został dodany przed wysyłką, lub obsługa klienta może go podać klientowi.
-   **Miniatura pierwszego produktu:**

    -   **Co robi to ustawienie:** Wyświetla mały obrazek pierwszego produktu w zamówieniu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Pojawia się wizualna wskazówka dotycząca zawartości zamówienia, ułatwiająca szybką identyfikację.
        -   *Po wyłączeniu:* Nie wyświetla się żaden obrazek produktu.
    -   **Zalecana wartość:** TAK, bardzo pomocne dla wizualnego potwierdzenia, zwłaszcza przy kompletacji w magazynie.
    -   **Scenariusz sprzedawcy / przykład:** Personel magazynu może wizualnie potwierdzić rodzaj produktu w zamówieniu bez jego otwierania, przyspieszając kompletację.
-   **Waga zamówienia:**

    -   **Co robi to ustawienie:** Pokazuje całkowitą wagę zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Waga zamówienia jest wyświetlana, co jest przydatne do obliczeń kosztów wysyłki lub wyboru przewoźnika.
        -   *Po wyłączeniu:* Waga zamówienia jest ukryta.
    -   **Zalecana wartość:** TAK, jeśli zajmujesz się produktami fizycznymi, a waga jest czynnikiem wpływającym na wysyłkę.
    -   **Scenariusz sprzedawcy / przykład:** Menedżerowie wysyłki mogą szybko ocenić rozmiary i wagi paczek dla przesyłek masowych.
-   **Fragment wątku obsługi klienta:**

    -   **Co robi to ustawienie:** Wyświetla krótki fragment z najnowszej wiadomości obsługi klienta związanej z zamówieniem.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zapewnia natychmiastowy kontekst ostatnich komunikacji z klientem.
        -   *Po wyłączeniu:* Nie wyświetla się żaden fragment.
    -   **Zalecana wartość:** TAK, nieocenione dla zespołów obsługi klienta.
    -   **Scenariusz sprzedawcy / przykład:** Agent obsługi klienta może sprawdzić, czy klient ostatnio pytał o zamówienie, bez otwierania całego wątku.
-   **ISO waluty:**

    -   **Co robi to ustawienie:** Pokazuje kod ISO waluty użytej do zamówienia (np. EUR, USD).
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Przydatne dla sklepów międzynarodowych do szybkiej identyfikacji waluty.
        -   *Po wyłączeniu:* ISO waluty jest ukryte.
    -   **Zalecana wartość:** TAK, jeśli prowadzisz sklep wielowalutowy.
    -   **Scenariusz sprzedawcy / przykład:** Personel finansowy może szybko sortować lub filtrować zamówienia według waluty w celu rozliczenia.
-   **Zastosowane reguły koszyka (rabaty):**

    -   **Co robi to ustawienie:** Wskazuje, czy do zamówienia zastosowano jakiekolwiek reguły koszyka (rabaty).
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zapewnia szybki przegląd zamówień objętych rabatem.
        -   *Po wyłączeniu:* Informacje o zastosowanych rabatach są ukryte.
    -   **Zalecana wartość:** TAK, dla działu finansowego, marketingu lub obsługi klienta, aby zrozumieć ceny.
    -   **Scenariusz sprzedawcy / przykład:** Marketing może szybko zidentyfikować zamówienia, które wykorzystały konkretny kod promocyjny.

**Zapisywanie zmian:**
Zawsze pamiętaj, aby kliknąć przycisk „Zapisz” lub „Aktualizuj” po wprowadzeniu jakichkolwiek zmian w wyborze kolumn lub ich kolejności. Moduł zapisuje kolejność kolumn jako JSON, zapewniając trwałość Twojego niestandardowego układu.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 AdminMyordergridproAjaxController (Panel Administracyjny > Moduły > Konfiguruj > Order Grid Pro)

Ten kontroler obsługuje głównie dynamiczne interakcje na stronie konfiguracji modułu. Nie ma on oddzielnego elementu menu w nawigacji PrestaShop.

-   **Nazwa ekranu i lokalizacja w menu:** Ten kontroler jest aktywowany, gdy znajdujesz się na stronie „Moduły > Menedżer modułów > Order Grid Pro > Konfiguruj”. Przetwarza żądania AJAX wysyłane przez JavaScript na tej stronie.
-   **Dostępne akcje i ustawienia:** Zarządza zapisywaniem i ładowaniem niestandardowych konfiguracji siatki (które kolumny są widoczne i ich kolejność). Gdy przeciągasz i upuszczasz kolumny lub przełączasz ich widoczność na stronie konfiguracji modułu, ten kontroler odbiera dane i je zapisuje.
-   **Efekt zmian:** Wszelkie zmiany wprowadzone w układzie kolumn na stronie konfiguracji modułu są wysyłane do tego kontrolera, który następnie aktualizuje zapisane preferencje dla Twojej siatki zamówień. Zapewnia to, że po przejściu do „Zamówienia > Zamówienia” zostanie zastosowany Twój niestandardowy układ.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Z tym kontrolerem wchodzisz w interakcje pośrednio, po prostu konfigurując moduł na jego głównej stronie. Nie ma tu bezpośredniego „widoku zarządzania” dla sprzedawców; jest to procesor zaplecza dla Twoich wyborów konfiguracyjnych.

#### 2.2.2 index.php (myordergridpro/controllers/admin/index.php)

Ten plik jest standardowym plikiem zastępczym lub punktem wejścia dla kontrolerów administracyjnych w module, zapewniającym, że bezpośredni dostęp do katalogu jest zablokowany, a mechanizmy bezpieczeństwa PrestaShop są przestrzegane. Nie reprezentuje on odrębnego, konfigurowalnego ekranu dla sprzedawcy.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | **Widoczność i kolejność kolumn** | Zmienna w zależności od roli | Wybiera, które kolumny pojawiają się na liście zamówień w Panelu Administracyjnym i ich kolejność wyświetlania. Bezpośrednio wpływa na wydajność zespołu. |
| | *Telefon klienta* | TAK | Wyświetla numer telefonu klienta dla szybkiego kontaktu. |
| | *Numer śledzenia* | TAK | Pokazuje numer śledzenia zamówienia dla wysyłki/wsparcia. |
| | *Miniatura pierwszego produktu* | TAK | Wizualna wskazówka dotycząca pierwszego produktu w zamówieniu. |
| | *Waga zamówienia* | TAK (dla towarów fizycznych) | Wyświetla całkowitą wagę zamówienia dla wysyłki. |
| | *Fragment wątku obsługi klienta* | TAK | Zapewnia kontekst ostatnich komunikacji z klientem. |
| | *ISO waluty* | TAK (dla wielu walut) | Pokazuje kod waluty dla sklepów międzynarodowych. |
| | *Zastosowane reguły koszyka* | TAK | Wskazuje, czy do zamówienia zastosowano rabaty. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem kolumny, ale nie widzę zmian na stronie Zamówienia.**
O:

1.  **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Czasami PrestaShop buforuje konfiguracje modułów.
2.  **Pamięć podręczna przeglądarki:** Spróbuj wyczyścić pamięć podręczną przeglądarki lub otworzyć Panel Administracyjny w oknie incognito/prywatnym, aby upewnić się, że nie widzisz starej, zbuforowanej wersji strony.
3.  **Zapisz konfigurację:** Sprawdź dwukrotnie, czy kliknąłeś przycisk „Zapisz” lub „Aktualizuj” na stronie konfiguracji modułu po wprowadzeniu zmian.

**P: Niektóre włączone kolumny są puste lub pokazują „N/A”. Dlaczego?**
O: Zazwyczaj oznacza to, że dane dla tej konkretnej kolumny nie są dostępne dla tego konkretnego zamówienia. Na przykład:

-   „Numer śledzenia” będzie pusty, jeśli do zamówienia nie dodano numeru śledzenia.
-   „Fragment wątku obsługi klienta” będzie pusty, jeśli dla tego zamówienia nie ma wiadomości obsługi klienta.
-   „Waga zamówienia” może być pusta, jeśli wagi produktów nie są zdefiniowane lub jeśli zamówienie zawiera tylko produkty wirtualne.
    Jest to normalne zachowanie i wskazuje na brakujące dane, a nie na błąd modułu.

**P: Funkcja przeciągnij i upuść do zmiany kolejności kolumn nie działa.**
O:

1.  **Konflikt JavaScript:** Inny moduł lub Twój motyw może mieć konflikt JavaScript. Spróbuj wyłączyć inne ostatnio zainstalowane moduły jeden po drugim, aby zidentyfikować przyczynę.
2.  **Problem z przeglądarką:** Przetestuj w innej przeglądarce (Chrome, Firefox, Edge), aby wykluczyć problem specyficzny dla przeglądarki.
3.  **Wyczyść pamięć podręczną:** Wyczyść pamięć podręczną PrestaShop i przeglądarki, jak opisano powyżej.

**P: Czy ten moduł spowolni mój Panel Administracyjny?**
O: Moduł został zaprojektowany tak, aby używać oficjalnych hooków siatki PrestaShop i unikać nadpisywania rdzenia, co pomaga w utrzymaniu wydajności i kompatybilności. Chociaż dodanie wielu nowych kolumn wymaga od PrestaShop pobrania większej ilości danych, wpływ jest zazwyczaj minimalny. Jeśli zauważysz znaczne spowolnienia, rozważ zmniejszenie liczby włączonych bardzo złożonych niestandardowych kolumn.

**P: Czy ten moduł jest kompatybilny z moim niestandardowym motywem?**
O: Tak, ten moduł działa w Panelu Administracyjnym PrestaShop, który używa własnego domyślnego motywu (New Classic lub podobnego). Nie wpływa on na Twój motyw front-office, więc nie powinno być problemów z kompatybilnością z niestandardowymi motywami front-office.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Order Grid Pro” rozszerza funkcjonalność listy zamówień w Panelu Administracyjnym PrestaShop, szczególnie celując w system siatki Symfony wprowadzony w PrestaShop 1.7.7+. Przestrzega najlepszych praktyk rozwoju modułów PrestaShop, wykorzystując oficjalne hooki (`actionGet` i `actionSet` dla definicji siatki) zamiast bezpośrednich nadpisywań rdzenia. Zapewnia to kompatybilność z aktualizacjami i stabilność. Moduł przede wszystkim wstrzykuje nowe definicje kolumn i dostawców danych do istniejącej siatki zamówień oraz przechowuje preferencje użytkownika dotyczące widoczności i kolejności kolumn za pomocą standardowej konfiguracji PrestaShop. Wywołania AJAX obsługują dynamiczne aktualizacje tych preferencji.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Ten moduł jest wyłącznie dla Panelu Administracyjnego.
-   **Kontrolery administracyjne Back-Office**:

    -   `controllers/admin/AdminMyordergridproAjaxController.php`
        -   **Nazwa klasy i klasa nadrzędna**: `AdminMyordergridproAjaxController` rozszerza `ModuleAdminController`.
        -   **Odpowiedzialność**: Ten kontroler jest odpowiedzialny za obsługę żądań AJAX ze strony konfiguracji modułu. Przetwarza żądania zapisywania i ładowania niestandardowej konfiguracji siatki zamówień (widoczność i kolejność kolumn). Zazwyczaj odbiera dane JSON reprezentujące pożądany układ siatki i przechowuje je za pomocą `Configuration::updateValue()`.
        -   **Trasy**: Odpowiada na wywołania AJAX wysyłane do `index.php?controller=AdminMyordergridproAjax&token=...&ajax=1`.
    -   `controllers/admin/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: Nie jest klasą, ale plikiem bezpieczeństwa.
        -   **Odpowiedzialność**: Jest to standardowy pusty plik `index.php` umieszczony w katalogach kontrolerów, aby zapobiec listowaniu katalogów i bezpośredniemu dostępowi, zwiększając bezpieczeństwo. Zazwyczaj zawiera `<?php header('Expires: Mon, 26 Jul 1997 05:00:00 GMT'); header('Last-Modified: '.gmdate('D, d M Y H:i:s').' GMT'); header('Cache-Control: no-store, no-cache, must-revalidate'); header('Cache-Control: post-check=0, pre-check=0', false); header('Pragma: no-cache'); header('Location: ../'); exit;`.

### 4.3 Klasy rdzenia i modele (`classes/`)

Moduł nie wydaje się definiować niestandardowych klas `ObjectModel` ani tabel bazy danych. Działa głównie poprzez rozszerzanie istniejących definicji siatki PrestaShop i przechowywanie danych konfiguracyjnych w `ps_configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `views/js/grid_pro.js`

    -   **Zakres**: Panel administracyjny (strona listy zamówień).
    -   **Opis**: Ten skrypt prawdopodobnie zawiera podstawową logikę manipulowania siatką Symfony PrestaShop na stronie „Zamówienia > Zamówienia”. Byłby odpowiedzialny za:
        -   Odczytywanie zapisanej konfiguracji kolumn z `Configuration::get()`.
        -   Dynamiczne dodawanie/usuwanie kolumn do siatki na podstawie konfiguracji.
        -   Stosowanie niestandardowej kolejności kolumn.
        -   Potencjalnie obsługę aktualizacji na żywo lub specyficzną logikę renderowania kolumn.
        -   Wiązanie z wydarzeniami siatki PrestaShop (np. `prestashop.on('grid.loaded', ...)`).
-   `views/js/order_grid_admin.js`

    -   **Zakres**: Panel administracyjny (strona konfiguracji modułu).
    -   **Opis**: Ten skrypt jest używany głównie na stronie konfiguracji modułu (`getContent()`). Obsługuje interfejs użytkownika do wybierania i porządkowania kolumn. Obejmuje to:
        -   Implementację funkcji przeciągnij i upuść do zmiany kolejności kolumn.
        -   Zarządzanie listami „Dostępne kolumny” i „Aktywne kolumny”.
        -   Wiązanie słuchaczy zdarzeń z przełącznikami/checkboxami dla widoczności kolumn.
        -   Wykonywanie wywołań AJAX do `AdminMyordergridproAjaxController.php` w celu zapisania zaktualizowanej konfiguracji.
-   `views/js/order_list_live_status.js`

    -   **Zakres**: Panel administracyjny (strona listy zamówień).
    -   **Opis**: Ten skrypt prawdopodobnie zapewnia funkcjonalność do aktualizacji na żywo lub interaktywnych elementów bezpośrednio na liście zamówień. Może to obejmować:
        -   Aktualizacje statusu zamówień oparte na AJAX bez odświeżania strony.
        -   Podpowiedzi lub wyskakujące okienka dla dodatkowych informacji w konkretnych kolumnach.
        -   Potencjalne ulepszanie domyślnych rozwijanych list zmiany statusu lub dodawanie niestandardowych szybkich akcji.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `views/css/order_grid_admin.css`
    -   **Zakres**: Panel administracyjny (strona konfiguracji modułu i potencjalnie strona listy zamówień).
    -   **Opis**: Ten arkusz stylów zapewnia wizualne style dla interfejsu konfiguracji modułu, zapewniając, że elementy przeciągnij i upuść oraz listy kolumn są prezentowane jasno. Może również zawierać drobne korekty stylów dla nowych kolumn wprowadzonych w rzeczywistej liście zamówień, aby zapewnić prawidłowe wyrównanie i czytelność w ramach motywu Panelu Administracyjnego PrestaShop.
    -   **Kluczowe selektory klas CSS**: Prawdopodobnie celuje w konkretne identyfikatory lub klasy w szablonie `getContent()` modułu, a potencjalnie w nowe klasy kolumn wstrzyknięte do siatki.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Informacje o module wskazują, że nie znaleziono jawnych plików `.tpl` w `views/templates/`. Sugeruje to, że interfejs konfiguracji modułu jest prawdopodobnie renderowany bezpośrednio w metodzie `getContent()` głównego pliku modułu (`index.php`) za pomocą PHP do generowania kodu HTML, lub dynamicznie wstrzykuje zawartość do istniejących szablonów siatki PrestaShop za pośrednictwem hooków.

Gdyby szablony były obecne, zazwyczaj byłyby to:

-   **Szablony hooków (`views/templates/hook/`)**: Do renderowania nowej zawartości kolumn w komórkach siatki.
-   **Szablony administracyjne (`views/templates/admin/`)**: Dla formularza konfiguracji modułu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy niestandardowych tabel SQL.
    -   Ustawienia konfiguracji (np. ciąg JSON reprezentujący kolejność i widoczność kolumn) są przechowywane w tabeli `ps_configuration` za pomocą kluczy takich jak `MYORDERGRIDPRO_CONFIG` lub podobnych.
-   **Tabela zarejestrowanych hooków**:
    Moduł opiera się głównie na hookach siatki Symfony PrestaShop w celu zapewnienia swojej funkcjonalności.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionGet` i `actionSet` (dla definicji siatki) | Gdy siatka zamówień jest definiowana i renderowana w Panelu Administracyjnym. | Są to podstawowe hooki używane do wstrzykiwania nowych definicji kolumn i dostawców danych do istniejącej siatki zamówień PrestaShop. `actionGet` pozwala modułowi pobrać bieżącą definicję siatki, a `actionSet` pozwala mu modyfikować lub dodawać nowe kolumny przed renderowaniem siatki. |
| `displayBackOfficeHeader` | Wykonywany w sekcji `<head>` każdej strony Panelu Administracyjnego. | Używany do dołączania zasobów CSS i JavaScript (`order_grid_admin.css`, `grid_pro.js`, `order_grid_admin.js`, `order_list_live_status.js`) specjalnie dla Panelu Administracyjnego, zapewniając ich załadowanie, gdy są potrzebne. |
| `displayAdminOrderListToolbar` (lub podobny) | Renderuje zawartość w obszarze paska narzędzi listy zamówień. | Potencjalnie używany do dodawania przycisków szybkiego działania lub filtrów związanych z funkcjonalnością modułu. |
| `actionAdminOrdersListingFieldsModifier` (lub podobny) | Modyfikuje pola/kolumny dostępne w zapytaniu o listę zamówień. | Pozwala modułowi dodawać nowe pola do zapytania SQL, które pobiera dane zamówień, umożliwiając wyświetlanie niestandardowych danych kolumn. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla „Order Grid Pro - kolumny i układ listy zamówień”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół jest zaangażowany w zapewnienie doskonałego funkcjonowania Twojego modułu i pomoc w maksymalizacji wydajności Twojego sklepu PrestaShop.
"""
