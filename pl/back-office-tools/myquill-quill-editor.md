---
title: "MyQuill - edytor Quill - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów modułu MyQuill - edytor Quill dla PrestaShop od MyPresta.eu."
sidebar:
  label: "MyQuill - edytor Quill"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł MyQuill - Quill editor na MyPresta.eu](https://mypresta.eu/modules/administration-tools/myquill-quill-editor.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/myquill-quill-editor/)
>
> ---


# MyQuill - edytor Quill

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i domyślnie włączone w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po instalacji kliknięcie "Konfiguruj" przeniesie Cię do głównego ekranu konfiguracji MyQuill. Tutaj kontrolujesz, jak edytor Quill zachowuje się w Twoim Panelu administracyjnym.

#### **Zakładka Ustawienia ogólne**

**1. Włącz edytor MyQuill**
-   **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji edytora MyQuill.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączony (TAK):* Edytor Quill zastąpi domyślny edytor TinyMCE we wszystkich obsługiwanych obszarach Twojego Panelu administracyjnego PrestaShop (np. opisy produktów, strony CMS, opisy kategorii).
    -   *Gdy wyłączony (NIE):* Zostanie przywrócony domyślny edytor TinyMCE, a funkcje MyQuill nie będą dostępne.
-   **Zalecana wartość:** **TAK** (aby korzystać z funkcji modułu).
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz tymczasowo wrócić do TinyMCE w celu testowania kompatybilności z innym modułem, wyłączyłbyś MyQuill tutaj. W przeciwnym razie pozostaw go włączonego, aby cieszyć się zaawansowanym edytorem.

**2. Załaduj edytor Quill w Front Office**
-   **Co robi to ustawienie:** Określa, czy niezbędne zasoby edytora Quill (CSS, JS) są ładowane w Front Office Twojego sklepu. Jest to zazwyczaj potrzebne tylko wtedy, gdy masz niestandardowy motyw lub inny moduł, który używa Quill na front-endzie.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączony (TAK):* Pliki rdzenia Quill zostaną dołączone do publicznych stron Twojego sklepu. Może to nieznacznie zwiększyć czas ładowania strony, ale jest to konieczne, jeśli wyświetlasz treści wygenerowane przez Quill, które wymagają jego specyficznego stylu lub funkcjonalności na front-endzie.
    -   *Gdy wyłączony (NIE):* Pliki rdzenia Quill *nie* zostaną załadowane w Front Office, co oszczędza przepustowość i potencjalnie poprawia szybkość ładowania strony.
-   **Zalecana wartość:** **NIE** (chyba że masz konkretny powód, aby go załadować, np. niestandardową funkcję motywu).
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli używasz niestandardowego motywu, który wyświetla interaktywne treści (takie jak akordeony lub zakładki) stworzone za pomocą MyQuill, a te elementy nie renderują się poprawnie, włączenie tego może rozwiązać problem. Dla większości sklepów nie jest to potrzebne.

**3. Załaduj edytor Quill w Panelu administracyjnym**
-   **Co robi to ustawienie:** Kontroluje, czy zasoby edytora Quill są ładowane w Panelu administracyjnym PrestaShop. Jest to niezbędne do działania modułu.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączony (TAK):* Edytor Quill załaduje się i będzie działał poprawnie w Twoim Panelu administracyjnym.
    -   *Gdy wyłączony (NIE):* Edytor Quill nie załaduje się, a prawdopodobnie zobaczysz pusty obszar edytora lub domyślny TinyMCE. To skutecznie wyłącza podstawową funkcjonalność modułu w Panelu administracyjnym.
-   **Zalecana wartość:** **TAK** (Musi być włączone, aby moduł działał).
-   **Scenariusz / przykład dla sprzedawcy:** Zawsze powinieneś to mieć włączone. Wyłączenie tego uniemożliwiłoby korzystanie z funkcji MyQuill w panelu administracyjnym.

**4. Wysokość edytora (w pikselach)**
-   **Co robi to ustawienie:** Ustawia domyślną wysokość obszaru wprowadzania edytora Quill w pikselach.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawiona na wyższą wartość (np. 500px):* Edytor będzie wyższy, dając więcej pionowej przestrzeni do przeglądania i edytowania treści bez przewijania.
    -   *Gdy ustawiona na niższą wartość (np. 200px):* Edytor będzie krótszy, co może być przydatne dla krótszych sekcji treści, ale może wymagać więcej przewijania dla dłuższych opisów.
-   **Zalecana wartość:** **300px** (lub dostosuj w zależności od preferencji dla typowej długości treści).
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli często piszesz bardzo długie opisy produktów, zwiększenie tej wartości do 400px lub 500px może sprawić, że edycja będzie bardziej komfortowa. Dla krótkich tytułów stron CMS mniejsza wysokość może być wystarczająca.

**5. Opcje paska narzędzi edytora**
-   **Co robi to ustawienie:** Pozwala dostosować, które narzędzia pojawiają się na pasku narzędzi edytora Quill. Możesz zaznaczyć lub odznaczyć różne przyciski i funkcje.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy opcje są zaznaczone:* Odpowiednie przyciski (np. pogrubienie, kursywa, obraz, wideo, tabela) pojawią się na pasku narzędzi edytora, udostępniając te funkcje.
    -   *Gdy opcje są odznaczone:* Odpowiednie przyciski zostaną ukryte z paska narzędzi, uniemożliwiając ich użycie.
-   **Zalecana wartość:** Początkowo włącz wszystkie opcje, a następnie odznacz wszelkie narzędzia, których na pewno nigdy nie użyjesz, aby uprościć pasek narzędzi.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli nigdy nie planujesz osadzać filmów, możesz odznaczyć opcję "YouTube/Vimeo", aby zmniejszyć bałagan na pasku narzędzi. Jeśli chcesz upewnić się, że Twój zespół używa tylko podstawowego formatowania, możesz znacznie ograniczyć opcje.

**6. Folder przesyłania obrazów**
-   **Co robi to ustawienie:** Określa domyślny folder na Twoim serwerze, w którym będą przechowywane obrazy przesłane za pomocą edytora Quill.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy ustawiona na konkretną ścieżkę (np. `/img/cms/`):* Wszystkie obrazy przesłane za pośrednictwem edytora trafią do tego folderu.
    -   *Gdy pozostawiona jako domyślna (zazwyczaj `/img/cms/` lub podobna):* Obrazy będą przechowywane w standardowym katalogu obrazów CMS PrestaShop.
-   **Zalecana wartość:** Pozostaw jako domyślną (`/img/cms/`), chyba że masz konkretną potrzebę organizacyjną, aby ją zmienić.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz przechowywać obrazy specyficzne dla produktów oddzielnie od obrazów stron CMS, możesz utworzyć nowy folder (np. `/img/products_quill/`) i odpowiednio ustawić tę opcję. Upewnij się, że folder istnieje i ma uprawnienia do zapisu.

**7. Włącz generowanie linków SEO**
-   **Co robi to ustawienie:** Aktywuje funkcję, która pomaga tworzyć linki przyjazne dla SEO w Twoich treściach.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączony (TAK):* Narzędzie do tworzenia linków w Quill zaoferuje opcje generowania czystych, opisowych linków, potencjalnie używając nazw produktów lub kategorii jako tekstu linku.
    -   *Gdy wyłączony (NIE):* Narzędzie do tworzenia linków będzie działać jako standardowy wstawiacz linków bez specyficznych ulepszeń SEO.
-   **Zalecana wartość:** **TAK** (aby skorzystać z ulepszonego linkowania wewnętrznego dla SEO).
-   **Scenariusz / przykład dla sprzedawcy:** Podczas linkowania do produktu, zamiast po prostu wklejać URL, ta funkcja może pomóc automatycznie wygenerować link z nazwą produktu jako tekstem kotwicy, co jest lepsze dla SEO.

**8. Włącz osadzanie YouTube/Vimeo**
-   **Co robi to ustawienie:** Pozwala osadzać filmy z YouTube i Vimeo bezpośrednio w Twoich treściach za pomocą edytora Quill.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączony (TAK):* Na pasku narzędzi pojawi się dedykowany przycisk lub opcja do łatwego wklejania adresów URL filmów i ich osadzania.
    -   *Gdy wyłączony (NIE):* Nie będziesz mógł używać dedykowanego narzędzia do osadzania filmów.
-   **Zalecana wartość:** **TAK** (jeśli planujesz używać filmów w swoich treściach).
-   **Scenariusz / przykład dla sprzedawcy:** Możesz łatwo dodać film demonstracyjny produktu do opisu produktu lub film z historią marki do strony "O nas".

**9. Włącz tabele**
-   **Co robi to ustawienie:** Dodaje funkcjonalność do tworzenia i edytowania tabel HTML w edytorze Quill.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączony (TAK):* Narzędzie do tworzenia tabel będzie dostępne na pasku narzędzi, umożliwiając wstawianie i zarządzanie tabelami (dodawanie wierszy/kolumn, łączenie komórek itp.).
    -   *Gdy wyłączony (NIE):* Narzędzie do tworzenia tabel zostanie ukryte.
-   **Zalecana wartość:** **TAK** (tabele są przydatne do wyświetlania ustrukturyzowanych danych, takich jak specyfikacje lub porównania).
-   **Scenariusz / przykład dla sprzedawcy:** Użyj tabel do wyświetlania specyfikacji produktów, tabel porównawczych lub informacji o stawkach wysyłki na stronie CMS.

**10. Włącz przyciski Bootstrap**
-   **Co robi to ustawienie:** Zapewnia narzędzie do łatwego wstawiania przycisków w stylu Bootstrap do Twoich treści, które mogą być używane do wezwań do działania.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączony (TAK):* Pojawi się narzędzie do tworzenia przycisków, pozwalające wybrać style przycisków (primary, secondary, success itp.) i połączyć je.
    -   *Gdy wyłączony (NIE):* Narzędzie do tworzenia przycisków zostanie ukryte.
-   **Zalecana wartość:** **TAK** (dla wyraźnych wezwań do działania).
-   **Scenariusz / przykład dla sprzedawcy:** Dodaj przycisk "Kup teraz" do banera promocyjnego na stronie CMS lub przycisk "Pobierz PDF" do specyfikacji technicznych produktu.

**11. Włącz zakładki**
-   **Co robi to ustawienie:** Pozwala tworzyć sekcje treści z zakładkami, przydatne do organizowania dużych ilości informacji w kompaktowy sposób.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączony (TAK):* Narzędzie do tworzenia zakładek będzie dostępne, pozwalając zdefiniować tytuły zakładek i treści dla każdej zakładki.
    -   *Gdy wyłączony (NIE):* Narzędzie do tworzenia zakładek zostanie ukryte.
-   **Zalecana wartość:** **TAK** (dla lepszej organizacji treści).
-   **Scenariusz / przykład dla sprzedawcy:** Na stronie produktu użyj zakładek dla "Opisu", "Specyfikacji", "Recenzji" i "Informacji o wysyłce", aby strona była przejrzysta.

**12. Włącz galerie**
-   **Co robi to ustawienie:** Integruje funkcję tworzenia prostych galerii obrazów w Twoich treściach.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączony (TAK):* Pojawi się narzędzie do tworzenia galerii, pozwalające wybrać wiele obrazów i ułożyć je w galerię.
    -   *Gdy wyłączony (NIE):* Narzędzie do tworzenia galerii zostanie ukryte.
-   **Zalecana wartość:** **TAK** (dla atrakcyjnych wizualnie wyświetlaczy obrazów).
-   **Scenariusz / przykład dla sprzedawcy:** Zaprezentuj wiele ujęć produktu lub kolekcję zdjęć lifestyle'owych na stronie CMS.

**13. Włącz FAQ (Akordeon)**
-   **Co robi to ustawienie:** Dodaje narzędzie do tworzenia interaktywnych sekcji FAQ w formacie akordeonu (rozwijane/zwijane).
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączony (TAK):* Narzędzie FAQ będzie dostępne, pozwalając dodawać pary pytań i odpowiedzi, które użytkownicy mogą rozwijać lub zwijać.
    -   *Gdy wyłączony (NIE):* Narzędzie FAQ zostanie ukryte.
-   **Zalecana wartość:** **TAK** (doskonałe dla stron wsparcia lub FAQ produktów).
-   **Scenariusz / przykład dla sprzedawcy:** Utwórz dedykowaną stronę CMS "Często zadawane pytania" lub dodaj małą sekcję FAQ do strony produktu, aby odpowiedzieć na typowe pytania klientów.

#### **Przycisk Zapisz**
-   **Co robi:** Po wprowadzeniu jakichkolwiek zmian w ustawieniach na tej stronie, **musisz** kliknąć przycisk "Zapisz", aby je zastosować.
-   **Efekt kliknięcia:** Twoje zmiany zostaną zapisane w bazie danych, a edytor Quill odzwierciedli te nowe ustawienia następnym razem, gdy otworzysz go w Panelu administracyjnym.
-   **Zalecane działanie:** Zawsze kliknij "Zapisz" po zmodyfikowaniu dowolnego ustawienia.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

MyQuill integruje się przede wszystkim bezpośrednio z istniejącymi ekranami edycji treści PrestaShop (takimi jak formularze edycji produktów, kategorii i stron CMS). Nie wprowadza nowych pozycji menu najwyższego poziomu ani dedykowanych ekranów zarządzania danymi dla własnych treści. Kontrolery "AdminMyquillAjaxController" i "index.php" to wewnętrzne komponenty obsługujące operacje w tle modułu, takie jak przesyłanie obrazów lub dynamiczne ładowanie treści dla funkcji edytora.

Dlatego nie ma oddzielnego ekranu "AdminMyquill" do zarządzania. Cała interakcja odbywa się bezpośrednio w formularzach edycji treści, gdzie Quill zastępuje TinyMCE.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| **Strona konfiguracji modułu** | Włącz edytor MyQuill | TAK | Aktywuje/dezaktywuje edytor Quill w BO. |
| | Załaduj edytor Quill w Front Office | NIE | Ładuje zasoby Quill w FO (tylko jeśli potrzebne przez motyw/moduł). |
| | Załaduj edytor Quill w Panelu administracyjnym | TAK | Ładuje zasoby Quill w BO (niezbędne do działania modułu). |
| | Wysokość edytora (w pikselach) | 300px | Ustawia pionowy rozmiar okna edytora. |
| | Opcje paska narzędzi edytora | Wszystkie włączone | Dostosowuje, które narzędzia pojawiają się na pasku narzędzi edytora. |
| | Folder przesyłania obrazów | `/img/cms/` | Określa, gdzie przechowywane są przesłane obrazy. |
| | Włącz generowanie linków SEO | TAK | Dodaje funkcje do tworzenia linków przyjaznych dla SEO. |
| | Włącz osadzanie YouTube/Vimeo | TAK | Pozwala osadzać filmy z YouTube/Vimeo. |
| | Włącz tabele | TAK | Dodaje funkcjonalność do tworzenia i edytowania tabel HTML. |
| | Włącz przyciski Bootstrap | TAK | Zapewnia narzędzie do wstawiania przycisków w stylu Bootstrap. |
| | Włącz zakładki | TAK | Pozwala tworzyć sekcje treści z zakładkami. |
| | Włącz galerie | TAK | Integruje funkcję tworzenia galerii obrazów. |
| | Włącz FAQ (Akordeon) | TAK | Dodaje narzędzie do tworzenia interaktywnych sekcji FAQ. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Po zainstalowaniu MyQuill obszar edytora jest pusty lub nadal wyświetla TinyMCE.**
*   **O:** Po pierwsze, upewnij się, że "Włącz edytor MyQuill" i "Załaduj edytor Quill w Panelu administracyjnym" są ustawione na **TAK** w konfiguracji modułu. Po drugie, wyczyść pamięć podręczną PrestaShop: Przejdź do **Zaawansowane > Wydajność**, a następnie kliknij "Wyczyść pamięć podręczną" w prawym górnym rogu. Wyczyść również pamięć podręczną przeglądarki.

**P2: Moje obrazy nie są przesyłane lub nie widzę ich po przesłaniu.**
*   **O:** Sprawdź ustawienie "Folder przesyłania obrazów" w konfiguracji MyQuill. Upewnij się, że określony folder istnieje na Twoim serwerze (np. `/img/cms/`) i ma prawidłowe uprawnienia do zapisu (zazwyczaj 755 lub 775). Jeśli folder nie istnieje, utwórz go za pomocą FTP/SFTP.

**P3: Niektóre przyciski paska narzędzi (np. Tabele, Filmy) brakuje w edytorze.**
*   **O:** Przejdź do strony konfiguracji MyQuill i sprawdź sekcję "Opcje paska narzędzi edytora". Upewnij się, że konkretne funkcje, których chcesz używać (np. "Włącz tabele", "Włącz osadzanie YouTube/Vimeo") są ustawione na **TAK**. Zapisz zmiany i wyczyść pamięć podręczną.

**P4: Treści stworzone za pomocą MyQuill (takie jak zakładki lub akordeony) nie wyświetlają się poprawnie w moim Front Office.**
*   **O:** Dzieje się tak często, jeśli Twój motyw nie zawiera niezbędnych plików CSS lub JavaScript dla tych interaktywnych elementów. Spróbuj włączyć "Załaduj edytor Quill w Front Office" w konfiguracji MyQuill. Jeśli problem nadal występuje, Twój motyw może wymagać specyficznych bibliotek Bootstrap lub JavaScript, które nie są ładowane domyślnie lub powodują konflikty. W takim przypadku może być konieczne, aby webmaster zbadał problem.

**P5: Jak wrócić do domyślnego edytora TinyMCE?**
*   **O:** Po prostu przejdź do **Moduły > Menedżer modułów**, znajdź "MyQuill - edytor Quill" i kliknij przycisk "Wyłącz". Cała zawartość wcześniej utworzona za pomocą MyQuill nadal będzie tam, ale interfejs edycji powróci do TinyMCE. Możesz ponownie włączyć MyQuill w dowolnym momencie.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)
Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury
Moduł MyQuill integruje edytor tekstu sformatowanego Quill.js z Panelu administracyjnego PrestaShop, zastępując domyślny TinyMCE. Osiąga to poprzez podłączenie się do `displayBackOfficeHeader` w celu wstrzyknięcia swoich zasobów, a następnie użycie JavaScript do targetowania i inicjalizacji instancji Quill na odpowiednich elementach textarea. Moduł zapewnia rozszerzone funkcje, takie jak przesyłanie obrazów, osadzanie wideo i niestandardowe bloki treści (tabele, zakładki, galerie, FAQ) poprzez rozszerzenie funkcjonalności Quill i udostępnienie punktów końcowych AJAX dla operacji po stronie serwera. Unika nadpisywania rdzenia, zapewniając kompatybilność i łatwą deinstalację.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front Office**:
    Moduł nie zawiera żadnych dedykowanych kontrolerów Front Office. Cała funkcjonalność Front Office związana z wyświetlaniem treści wygenerowanych przez Quill jest obsługiwana przez renderowanie standardowych treści PrestaShop przez motyw (opisy produktów, strony CMS itp.) oraz opcjonalne ładowanie zasobów Front Office MyQuill za pośrednictwem hooków.

-   **Kontrolery administracyjne Back Office**:
    *   `controllers/admin/AdminMyquillAjaxController.php`
        *   **Nazwa klasy i klasa nadrzędna**: `AdminMyquillAjaxController` rozszerza `ModuleAdminController`.
        *   **Odpowiedzialność**: Ten kontroler obsługuje żądania AJAX pochodzące z edytora Quill w Panelu administracyjnym. Jego główną rolą jest zarządzanie operacjami po stronie serwera, takimi jak przesyłanie obrazów, zapewniając ich prawidłowe przechowywanie w wyznaczonym katalogu i zwracanie adresu URL do wstawienia do edytora. Może również obsługiwać inne dynamiczne żądania danych dla konkretnych wtyczek Quill (np. pobieranie danych produktów dla linków SEO).
    *   `controllers/admin/index.php`
        *   **Nazwa klasy i klasa nadrzędna**: Ten plik zazwyczaj zawiera prostą instrukcję `die('Access Denied');` lub podobne zabezpieczenie.
        *   **Odpowiedzialność**: Jest to standardowa praktyka PrestaShop, aby dołączać plik `index.php` do każdego katalogu, aby zapobiec listowaniu katalogów i bezpośredniemu dostępowi. Nie zawiera żadnej funkcjonalnej logiki kontrolera dla modułu.

### 4.3 Klasy rdzenia i modele (`classes/`)
Moduł MyQuill nie wprowadza żadnych niestandardowych klas `ObjectModel` ani tabel baz danych. Działa przede wszystkim poprzez zastąpienie interfejsu edytora i przechowywanie jego konfiguracji w `ps_configuration`. Treści utworzone za pomocą Quill są przechowywane bezpośrednio w istniejących polach treści PrestaShop (np. `ps_product_lang.description`, `ps_cms_lang.content`) jako standardowy kod HTML.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `views/js/myquill-admin.js`
    *   **Zakres**: Panel administracyjny.
    *   **Szczegóły**: Jest to główny plik JavaScript administracyjny. Odpowiada za inicjalizację edytora Quill na wszystkich odpowiednich elementach textarea w Panelu administracyjnym PrestaShop. Odczytuje ustawienia konfiguracyjne modułu (wysokość edytora, opcje paska narzędzi, włączone funkcje) i dynamicznie konstruuje instancję Quill z odpowiednimi modułami i handlerami. Zawiera również logikę integracji niestandardowych przycisków paska narzędzi i obsługi ich działań (np. otwieranie okien dialogowych przesyłania obrazów, wstawianie osadzonych filmów).
-   `views/js/myquill-editor.js`
    *   **Zakres**: Panel administracyjny.
    *   **Szczegóły**: Ten plik prawdopodobnie zawiera samą bibliotekę Quill.js lub specyficzne dostosowania/rozszerzenia do podstawowego edytora Quill. Definiuje podstawowe zachowanie, renderowanie i API edytora.
-   `views/js/myquill-front.js`
    *   **Zakres**: Front Office.
    *   **Szczegóły**: Ten skrypt jest warunkowo ładowany w Front Office, jeśli włączone jest ustawienie "Załaduj edytor Quill w Front Office". Zawiera kod JavaScript niezbędny do działania interaktywnych elementów stworzonych za pomocą Quill (takich jak zakładki, akordeony, galerie) po stronie klienta sklepu. Może zawierać słuchacze zdarzeń kliknięcia na nagłówkach zakładek lub tytułach akordeonów w celu przełączania widoczności treści.
-   `views/js/myquill-plugins.js`
    *   **Zakres**: Panel administracyjny.
    *   **Szczegóły**: Ten plik zawiera logikę JavaScript dla różnych niestandardowych wtyczek i rozszerzeń dodanych do Quill przez MyQuill. Obejmuje to implementację funkcji takich jak obsługa przesyłania obrazów, osadzanie wideo, tworzenie tabel, przyciski Bootstrap, zakładki, galerie i akordeony FAQ. Definiuje, jak te niestandardowe "blots" (termin Quill dla niestandardowych bloków treści) są renderowane i jak zachowują się ich powiązane działania paska narzędzi.
-   `views/js/myquill-pro.js`
    *   **Zakres**: Panel administracyjny.
    *   **Szczegóły**: Ten plik prawdopodobnie zawiera zaawansowane lub "pro" funkcje i ulepszenia dla edytora Quill, potencjalnie bazujące na `myquill-plugins.js`. Może zawierać bardziej wyrafinowane elementy interfejsu użytkownika, dodatkowe opcje formatowania lub dalsze integracje specyficzne dla wersji modułu MyPresta.eu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `views/css/myquill-admin.css`
    *   **Zakres**: Stylizacja formularzy administracyjnych Back Office.
    *   **Szczegóły**: Zawiera style specyficzne dla wyglądu edytora Quill w Panelu administracyjnym PrestaShop. Obejmuje to stylizację paska narzędzi, kontenera edytora, niestandardowych okien dialogowych i zapewnienie wizualnej integracji edytora z motywem administracyjnym PrestaShop.
-   `views/css/myquill-editor.css`
    *   **Zakres**: Stylizacja formularzy administracyjnych Back Office.
    *   **Szczegóły**: Ten plik prawdopodobnie zawiera podstawowy CSS dla samego edytora Quill, definiujący podstawowe style dla formatowania tekstu, cytatów blokowych, list i innych standardowych elementów Quill. Może również zawierać style dla niestandardowych blots (np. tabel, przycisków) podczas renderowania w edytorze.
-   `views/css/myquill-front.css`
    *   **Zakres**: Stylizacja klienta Front Office.
    *   **Szczegóły**: Ten arkusz stylów jest warunkowo ładowany w Front Office, jeśli włączone jest odpowiednie ustawienie. Zapewnia niezbędny CSS do prawidłowego renderowania interaktywnych elementów stworzonych za pomocą MyQuill (takich jak zakładki, akordeony, galerie) w sklepie widocznym dla klienta. Programiści mogą nadpisać te style w pliku `custom.css` lub `theme.css` swojego motywu, aby dopasować je do swojej marki.
-   `views/css/quill.snow.css`
    *   **Zakres**: Stylizacja formularzy administracyjnych Back Office.
    *   **Szczegóły**: Jest to standardowy arkusz stylów motywu "Snow" dla Quill.js. Zapewnia domyślny wygląd wizualny paska narzędzi edytora Quill i obszaru treści, w tym ikon, stylów przycisków i podstawowego formatowania. Jest to podstawowy komponent Quill.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    *   `bo-header.tpl`
        *   **Hook**: `displayBackOfficeHeader`
        *   **Wyjście**: Ten szablon odpowiada za wstrzykiwanie niezbędnych zasobów CSS i JavaScript (rdzeń Quill, specyficzne dla modułu JS/CSS) do sekcji `<head>` stron Panelu administracyjnego, gdzie edytor jest potrzebny. Dynamicznie dołącza pliki na podstawie konfiguracji modułu.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   `configure.tpl`
        *   **Wyjście**: Ten szablon renderuje główny formularz konfiguracji modułu MyQuill, dostępny poprzez **Moduły > Menedżer modułów > Konfiguruj**. Wyświetla wszystkie ustawienia opisane w Sekcji 4.1, w tym przełączniki, pola wprowadzania i przycisk "Zapisz".
    *   `preview.tpl`
        *   **Wyjście**: Ten szablon może być używany do funkcji podglądu w Panelu administracyjnym, potencjalnie pokazując, jak treści wygenerowane przez Quill wyglądałyby na front-endzie. Jego dokładne użycie zależałoby od wewnętrznej implementacji modułu do podglądu treści.

-   **Szablony Front Office (`views/templates/front/`)**:
    Moduł nie zawiera żadnych dedykowanych szablonów Front Office. Cała zawartość wygenerowana przez Quill jest renderowana w ramach istniejących szablonów motywu PrestaShop (np. `product.tpl`, `cms.tpl`) poprzez wstawienie surowego kodu HTML z edytora.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł MyQuill nie tworzy żadnych niestandardowych tabel baz danych. Wszystkie jego ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy zazwyczaj poprzedzonych prefiksem `MYQUILL_`. Treści utworzone za pomocą edytora są przechowywane w standardowych tabelach treści PrestaShop (np. `ps_product_lang`, `ps_cms_lang`).

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `displayBackOfficeHeader` | Wykonywany w `<head>` stron Panelu administracyjnego. | Wstrzykuje zasoby CSS i JavaScript MyQuill (edytor Quill, wtyczki, style administracyjne) do Panelu administracyjnego w celu inicjalizacji edytora. |
| `displayHeader` | Wykonywany w `<head>` stron Front Office. | Warunkowo wstrzykuje zasoby CSS i JavaScript Front Office MyQuill, jeśli włączone jest "Załaduj edytor Quill w Front Office", aby zapewnić prawidłowe działanie interaktywnych elementów (zakładek, akordeonów). |
| `displayFooter` | Wykonywany na końcu `<body>` stron Front Office. | Potencjalnie używany do wstrzykiwania późno ładowanych skryptów lub dodatkowych zasobów dla interaktywnych elementów Front Office, jeśli nie jest obsługiwany przez `displayHeader`. |
| `displayProductExtraContent` | Wykonywany na stronie produktu. | Pozwala na wstrzykiwanie dodatkowych bloków treści na stronie produktu, potencjalnie przydatnych dla niestandardowych treści wygenerowanych przez Quill, jeśli moduł zostałby rozszerzony do bezpośredniego zarządzania takimi blokami. (Mniej prawdopodobne, aby był bezpośrednio używany przez podstawową funkcję zastępowania edytora MyQuill, ale dostępny dla rozszerzeń). |
| `displayLeftColumn` | Wykonywany w lewej kolumnie stron Front Office. | Podobnie jak `displayProductExtraContent`, zapewnia hook do wstrzykiwania treści do lewej kolumny. |
| `displayRightColumn` | Wykonywany w prawej kolumnie stron Front Office. | Podobnie jak `displayProductExtraContent`, zapewnia hook do wstrzykiwania treści do prawej kolumny. |

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu MyQuill - edytor Quill, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Możesz pobrać najnowsze wersje z historii zamówień i uzyskać dostęp do zasobów wsparcia bezpośrednio ze strony MyPresta.eu.
