---
title: "Tagi Open Graph Facebooka - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Tagi Open Graph Facebooka od MyPresta.eu."
sidebar:
  label: "Tagi Open Graph Facebooka - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook Open Graph Tags na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-open-graph-tags.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-open-graph-tags/)
>
> ---


# Tagi Open Graph Facebooka

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.3.x, 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i zazwyczaj domyślnie włączone w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Tagi Open Graph Facebooka)

To jest główny ekran konfiguracji, na którym kontrolujesz podstawowe zachowanie modułu.

| Ustawienie / Opcja | Co robi to ustawienie | Efekt zmiany tego ustawienia | Zalecana wartość | Scenariusz / przykład dla sprzedawcy |
| --- | --- | --- | --- | --- |
| **Włącz tagi Open Graph** | Ten główny przełącznik kontroluje, czy moduł w ogóle generuje jakiekolwiek tagi Open Graph. | *Po włączeniu:* Moduł wstrzyknie niezbędne tagi Open Graph do sekcji `<head>` kodu HTML Twojego sklepu, umożliwiając Facebookowi wyświetlanie bogatych podglądów. *Po wyłączeniu:* Ten moduł nie będzie generował żadnych tagów Open Graph, a Facebook spróbuje odgadnąć zawartość, co często skutkuje słabymi lub brakującymi podglądami. | **TAK** | Chcesz, aby udostępnienia Twoich produktów wyglądały profesjonalnie na Facebooku. |
| **ID aplikacji Facebooka** | Twój unikalny identyfikator dla Twojej aplikacji Facebooka. Łączy udostępnienia Twojej witryny z Twoją aplikacją Facebooka, umożliwiając wgląd i analizy. | *Po podaniu:* Facebook może przypisać udostępnienia do Twojej aplikacji, dostarczając Ci analizy dotyczące tego, jak Twoje treści działają na ich platformie. *Po pozostawieniu pustego:* Udostępnienia nadal będą działać, ale nie uzyskasz szczegółowych informacji za pośrednictwem narzędzi deweloperskich Facebooka. | **Twój ID aplikacji Facebooka** (jeśli go masz) | Chcesz śledzić wydajność udostępnianych treści na Facebooku za pomocą Facebook Insights. Jeśli go nie masz, możesz pozostawić to pole puste. |
| **ID administratora Facebooka** | ID użytkownika Facebooka administratora(ów) Twojej strony lub aplikacji Facebooka. Pomaga to Facebookowi zrozumieć, kto zarządza treścią. | *Po podaniu:* Facebook wie, kto jest autorem/administratorem treści, co może być przydatne do moderacji lub specyficznych funkcji Facebooka. *Po pozostawieniu pustego:* Nie zostanie powiązany żaden konkretny administrator. | **Twój ID użytkownika Facebooka** (jeśli dotyczy) | Chcesz powiązać swój osobisty profil Facebooka jako administratora udostępnianych treści. |
| **Domyślny obraz dla strony głównej** | To ustawienie pozwala określić obraz zastępczy, którego Facebook użyje, gdy Twoja strona główna zostanie udostępniona, zwłaszcza jeśli Twoja strona główna sama w sobie nie ma wyraźnego obrazu. | *Po przesłaniu obrazu:* Ten obraz zostanie użyty jako `og:image`, gdy strona główna Twojego sklepu zostanie udostępniona na Facebooku. *Po pozostawieniu pustego:* Facebook spróbuje znaleźć obraz na Twojej stronie głównej, co może nie zawsze być idealne (np. małe logo lub baner). | **Prześlij główne logo swojego sklepu lub atrakcyjny obraz banerowy.** | Twoja strona główna to głównie tekst, a Ty chcesz, aby konkretny, atrakcyjny obraz pojawiał się, gdy ktoś udostępni główny adres URL Twojego sklepu. |
| **Domyślny tytuł dla strony głównej** | Tytuł, który Facebook wyświetli, gdy strona główna Twojego sklepu zostanie udostępniona. | *Po podaniu:* Ten tytuł zostanie użyty jako `og:title` dla udostępnień Twojej strony głównej. *Po pozostawieniu pustego:* Facebook prawdopodobnie użyje domyślnego meta tytułu Twojego sklepu, który może nie być zoptymalizowany pod kątem udostępniania w mediach społecznościowych. | **Nazwa Twojego sklepu - Slogan** (np. „Mój Niesamowity Sklep - Odkryj Unikalne Produkty!”) | Chcesz, aby chwytliwy, markowy tytuł pojawiał się, gdy główny adres URL Twojego sklepu zostanie udostępniony. |
| **Domyślny opis dla strony głównej** | Opis, który Facebook wyświetli, gdy strona główna Twojego sklepu zostanie udostępniona. | *Po podaniu:* Ten opis zostanie użyty jako `og:description` dla udostępnień Twojej strony głównej. *Po pozostawieniu pustego:* Facebook prawdopodobnie użyje domyślnego meta opisu Twojego sklepu, który może nie być zoptymalizowany pod kątem udostępniania w mediach społecznościowych. | **Zwięzłe, angażujące podsumowanie Twojego sklepu.** (np. „Kupuj najnowsze trendy w modzie i elektronice. Szybka wysyłka na cały świat!”) | Chcesz kontrolować wiadomość, która pojawia się, gdy strona główna Twojego sklepu zostanie udostępniona, zachęcając użytkowników do kliknięcia. |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolera

#### 2.2.1 AdminOpenGraphController (Panel administracyjny > Zaawansowane > Tagi Open Graph)

Ten ekran pozwala zarządzać konkretnymi tagami Open Graph dla poszczególnych stron lub nadpisywać domyślne zachowanie. Chociaż moduł automatycznie generuje tagi dla produktów i kategorii, ta sekcja jest przydatna dla niestandardowych stron lub precyzyjnego dostrajania.

- **Nazwa ekranu i lokalizacja w menu:** Możesz uzyskać dostęp do tego ekranu, przechodząc do **Zaawansowane > Tagi Open Graph** w Panelu administracyjnym PrestaShop.
- **Dostępne działania i ustawienia:** Ten ekran zazwyczaj przedstawia siatkę (listę) niestandardowych konfiguracji tagów Open Graph, które dodałeś. Znajdziesz opcje do:
  - **Dodaj nowy:** Utwórz nowy niestandardowy zestaw tagów Open Graph dla konkretnego adresu URL.
  - **Edytuj:** Modyfikuj istniejący niestandardowy zestaw tagów.
  - **Usuń:** Usuń niestandardowy zestaw tagów.
  - **Kolumny siatki:** Zazwyczaj wyświetla adres URL, tytuł, opis i obraz powiązany z niestandardowym tagiem.
- **Efekt zmian:**
  - **Dodanie nowego wpisu:** Gdy dodasz nowy wpis dla konkretnego adresu URL (np. niestandardowej strony CMS lub adresu URL wpisu na blogu), moduł użyje podanego tutaj tytułu, opisu i obrazu zamiast próbować je automatycznie generować, gdy ten konkretny adres URL zostanie udostępniony na Facebooku.
  - **Edycja wpisu:** Aktualizuje podgląd społecznościowy dla tego konkretnego adresu URL.
  - **Usunięcie wpisu:** Przywraca zachowanie dla tego adresu URL do automatycznego generowania przez moduł lub domyślnych ustawień strony głównej.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. **Zidentyfikuj strony wymagające niestandardowych podglądów:** Dla większości produktów i kategorii moduł działa automatycznie. Jednak dla niestandardowych stron CMS (np. „O nas”, „Kontakt”, wpisów na blogu, jeśli masz zintegrowany blog), możesz chcieć konkretnych, angażujących podglądów.
  2. **Kliknij „Dodaj nowy”**, aby utworzyć nowy wpis.
  3. **Wprowadź dokładny adres URL** strony, którą chcesz dostosować.
  4. **Podaj atrakcyjny Tytuł, Opis i prześlij odpowiedni Obraz** dla tej konkretnej strony.
  5. **Zapisz** swoje zmiany.
  6. **Testuj:** Użyj [Debuggera udostępniania](https://developers.facebook.com/tools/debug/) Facebooka, aby sprawdzić, jak wygląda Twoja strona po wprowadzeniu zmian.

#### 2.2.2 index.php (opengraph/controllers/admin/index.php)

Ten plik jest standardowym punktem wejścia kontrolera PrestaShop i nie stanowi odrębnego, konfigurowalnego ekranu dla sprzedawców. Jest zazwyczaj używany do routingu lub podstawowej administracji modułem, a nie do zarządzania konkretnymi treściami lub ustawieniami. Wszystkie konfiguracje skierowane do sprzedawców są obsługiwane za pośrednictwem głównej strony konfiguracji modułu lub `AdminOpenGraphController`.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz tagi Open Graph | TAK | Główny przełącznik funkcjonalności modułu. |
|  | ID aplikacji Facebooka | (Twój ID aplikacji) / Puste | Łączy udostępnienia z Twoją aplikacją Facebooka w celu analizy. |
|  | ID administratora Facebooka | (Twój ID użytkownika) / Puste | Identyfikuje administratora treści na Facebooku. |
|  | Domyślny obraz dla strony głównej | Prześlij swoje logo | Obraz zastępczy dla udostępnień strony głównej. |
|  | Domyślny tytuł dla strony głównej | Nazwa Twojego sklepu | Tytuł dla udostępnień strony głównej. |
|  | Domyślny opis dla strony głównej | Slogan sklepu | Opis dla udostępnień strony głównej. |
| **Zaawansowane > Tagi Open Graph** | Dodaj/Edytuj/Usuń niestandardowe tagi | N/A | Nadpisuje automatycznie generowane tagi dla konkretnych adresów URL niestandardowymi tytułami, opisami i obrazami. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje udostępnienia na Facebooku nadal wyglądają źle, nawet po zainstalowaniu modułu. Co jest nie tak?**
O:

1. **Sprawdź aktywację modułu:** Upewnij się, że „Włącz tagi Open Graph” jest ustawione na TAK w konfiguracji modułu.
2. **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Jest to kluczowe, aby zmiany zaczęły obowiązywać.
3. **Użyj Debuggera udostępniania Facebooka:** To Twój najlepszy przyjaciel! Przejdź do [developers.facebook.com/tools/debug/](https://developers.facebook.com/tools/debug/), wklej adres URL, który próbujesz udostępnić, i kliknij „Debuguj”. Pokaże Ci dokładnie, jakie tagi widzi Facebook i czy są jakieś błędy. Może być konieczne kliknięcie „Scrape Again”, aby wymusić na Facebooku ponowne odczytanie Twojej strony po wprowadzeniu zmian.
4. **Sprawdź konflikty:** Inny moduł lub Twój motyw może dodawać sprzeczne tagi Open Graph. Debugger często podkreśla zduplikowane tagi.

**P: Obraz dla moich udostępnień produktów jest błędny lub brakuje go.**
O:

1. **Obraz produktu:** Upewnij się, że Twój produkt ma przypisany główny obraz w ustawieniach produktu.
2. **Rozmiar obrazu:** Chociaż Facebook może zmieniać rozmiar, bardzo małe obrazy lub obrazy o nietypowym współczynniku proporcji mogą zostać zignorowane. Celuj w co najmniej 600x315 pikseli, idealnie 1200x628 dla optymalnego wyświetlania.
3. **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop i użyj Debuggera udostępniania Facebooka, aby „Scrape Again”.

**P: Jak uzyskać ID aplikacji Facebooka lub ID administratora?**
O:

1. **ID aplikacji Facebooka:** Przejdź do [developers.facebook.com](https://developers.facebook.com/), zaloguj się i utwórz nową aplikację. Postępuj zgodnie z instrukcjami, aby uzyskać swój ID aplikacji. Jest to ciąg cyfr.
2. **ID administratora Facebooka:** To Twój osobisty ID użytkownika Facebooka. Możesz go znaleźć, przechodząc do swojego profilu na Facebooku, klikając swoje zdjęcie profilowe i patrząc na adres URL w przeglądarce (np. `facebook.com/profile.php?id=TWÓJ_ID_UŻYTKOWNIKA`).

**P: Czy ten moduł działa z niestandardowymi motywami?**
O: Tak, moduł wstrzykuje tagi bezpośrednio do sekcji `<head>` Twojego HTML, co jest standardową praktyką i powinno działać z każdym dobrze zakodowanym motywem PrestaShop. Jeśli napotkasz problemy, zazwyczaj jest to problem z pamięcią podręczną lub konflikt z innym modułem.

**P: Moja niestandardowa strona (np. wpis na blogu) nie wyświetla prawidłowego podglądu.**
O: Użyj sekcji **Zaawansowane > Tagi Open Graph** w Panelu administracyjnym. Dodaj nowy wpis dla dokładnego adresu URL swojej niestandardowej strony i ręcznie określ żądany tytuł, opis i obraz. Pamiętaj, aby wyczyścić pamięć podręczną i użyć Debuggera udostępniania Facebooka.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Tagi Open Graph Facebooka” został zaprojektowany tak, aby bezproblemowo integrować się z podstawową funkcjonalnością PrestaShop, głównie poprzez wykorzystanie hooków do wstrzykiwania meta tagów Open Graph do sekcji `<head>` HTML różnych stron front-office. Przyjmuje standardową strukturę modułu PrestaShop, używając głównej klasy modułu, kontrolera administracyjnego do zarządzania niestandardowymi tagami i szablonów Smarty do renderowania. Moduł nie wprowadza złożonych schematów baz danych ani niestandardowych modeli obiektów dla swojej podstawowej funkcji, ale używa `Configuration` dla swoich głównych ustawień i potencjalnie niestandardowej tabeli dla `og_tags` zarządzanej przez `AdminOpenGraphController`.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Ten moduł nie zawiera żadnych dedykowanych kontrolerów front-office. Cała logika front-office do generowania tagów jest obsługiwana bezpośrednio w głównej klasie modułu (`index.php`) za pośrednictwem słuchaczy hooków.
- **Kontrolery administracyjne Back-Office**:

  - `opengraph/controllers/admin/AdminOpenGraphController.php`
    - **Nazwa klasy i klasa nadrzędna**: `AdminOpenGraphController` rozszerza `ModuleAdminController`.
    - **Nazwa zakładki i zarządzana encja**: Ten kontroler zarządza niestandardową encją, prawdopodobnie `og_tags`, która przechowuje niestandardowe konfiguracje Open Graph dla konkretnych adresów URL. Tworzy nowy wpis menu w sekcji „Zaawansowane” (lub podobnej) w Panelu administracyjnym.
    - **Odpowiedzialność**: Zapewnia standardowy interfejs CRUD (Create, Read, Update, Delete) PrestaShop do zarządzania niestandardowymi zestawami tagów Open Graph. Obsługuje wyświetlanie listy niestandardowych tagów (za pomocą `renderList()`) oraz formularza do ich dodawania/edycji (za pomocą `renderForm()`). Przetwarza przesłane formularze i wchodzi w interakcje z bazą danych w celu przechowywania i pobierania danych `og_tags`.
  - `opengraph/controllers/admin/index.php`
    - **Nazwa klasy i klasa nadrzędna**: Jest to zazwyczaj pusty plik `index.php` w katalogu kontrolera, służący jako środek bezpieczeństwa zapobiegający bezpośredniemu listowaniu katalogów. Nie zawiera żadnej funkcjonalnej klasy ani logiki.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Główna logika generowania tagów Open Graph prawdopodobnie znajduje się w głównym pliku modułu (`opengraph/index.php`), a `AdminOpenGraphController` obsługiwałby interakcje z niestandardową tabelą bazy danych bezpośrednio lub za pośrednictwem prostego `ObjectModel`, gdyby taki był zdefiniowany wewnętrznie.

Jeśli niestandardowa tabela `og_tags` jest zarządzana przez `AdminOpenGraphController`, jest bardzo prawdopodobne, że sam `AdminOpenGraphController` definiuje właściwości `$this->table` i `$this->className`, a potencjalnie prosta definicja `ObjectModel` dla `og_tags` jest zadeklarowana w głównym pliku modułu lub w samym kontrolerze, nawet jeśli nie w osobnym pliku `classes/`.

### 4.4 Zasoby JavaScript (`views/js/`)

Dossier modułu wskazuje brak niestandardowych plików JavaScript. Wszelkie dynamiczne zachowania lub interakcje AJAX byłyby obsługiwane przez podstawowy JS PrestaShop lub nie są obecne w tym module.

### 4.5 Arkusze stylów CSS (`views/css/`)

Dossier modułu wskazuje brak niestandardowych plików CSS. Moduł opiera się na domyślnej stylizacji Panelu administracyjnego PrestaShop dla swoich formularzy konfiguracyjnych, a wszelkie dane wyjściowe front-office to wyłącznie meta tagi, a nie elementy wizualne.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:

  - `opengraph/views/templates/front/hook/header.tpl`:
    - **Hook**: Prawdopodobnie `displayHeader` lub `actionFrontControllerSetMedia`.
    - **Cel**: Jest to główny szablon odpowiedzialny za renderowanie rzeczywistych tagów `<meta>` Open Graph w sekcji `<head>` stron front-office. Otrzymuje zmienne (np. `og_title`, `og_description`, `og_image`, `og_url`, `og_type`, `og_app_id`, `og_admin_id`) z metody `hookDisplayHeader` (lub podobnej) modułu i wyprowadza odpowiadające im meta tagi HTML.
  - `opengraph/views/templates/hook/form.tpl`:
    - **Hook**: Ten szablon jest prawdopodobnie używany wewnętrznie przez `AdminOpenGraphController` do renderowania pól formularza podczas dodawania lub edytowania niestandardowego wpisu tagu Open Graph. Nie jest to szablon hooka front-office.
    - **Cel**: Definiuje strukturę i pola wejściowe dla niestandardowego formularza konfiguracji tagów Open Graph w Panelu administracyjnym.
  - `opengraph/views/templates/hook/script.tpl`:
    - **Hook**: Może to być `displayHeader` lub `actionFrontControllerSetMedia`.
    - **Cel**: Ten szablon może być używany do wyprowadzania dowolnego wbudowanego kodu JavaScript związanego z Open Graph, takiego jak inicjalizacja Facebook SDK lub śledzenie konkretnych zdarzeń, chociaż dossier wskazuje brak plików JS, więc może to być bardzo minimalny skrypt lub placeholder.
- **Szablony administracyjne (`views/templates/admin/`)**: Nie są jawnie wymienione, ale `form.tpl` i potencjalnie `list.tpl` byłyby używane przez `AdminOpenGraphController` dla jego widoków.
- **Szablony front-office (`views/templates/front/`)**:

  - `opengraph/views/templates/front/hook/header.tpl` jest jedynym zidentyfikowanym szablonem front-office, specjalnie do wstrzykiwania hooków.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - `ps_configuration`: Przechowuje główne ustawienia modułu (np. `PS_OG_ENABLED`, `PS_OG_APP_ID`, `PS_OG_ADMIN_ID`, `PS_OG_HOME_IMAGE`, `PS_OG_HOME_TITLE`, `PS_OG_HOME_DESCRIPTION`).
  - `ps_og_tags` (lub podobna, zarządzana przez `AdminOpenGraphController`): Niestandardowa tabela do przechowywania zdefiniowanych przez użytkownika nadpisań tagów Open Graph dla konkretnych adresów URL.
    - Prawdopodobne pola: `id_og_tag`, `url`, `title`, `description`, `image`, `date_add`, `date_upd`.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` wszystkich stron front-office. | Główny hook do wstrzykiwania meta tagów Open Graph (`og:title`, `og:description`, `og:image`, `og:url`, `og:type` itp.) do kodu HTML. |
| `actionFrontControllerSetMedia` | Wykonywany po ustawieniu przez kontroler front-office jego mediów (CSS/JS). | Może być używany jako alternatywny lub dodatkowy hook do wstrzykiwania meta tagów lub powiązanych skryptów, zwłaszcza w PrestaShop 1.7+. |
| `displayBackOfficeHeader` | Renderuje zawartość w sekcji `<head>` stron Panelu administracyjnego. | Używany do dołączania wszelkich niezbędnych CSS lub JS dla stron konfiguracyjnych modułu w Panelu administracyjnym. |
| `actionAdminControllerSetMedia` | Wykonywany po ustawieniu przez kontroler administracyjny jego mediów. | Podobnie jak `displayBackOfficeHeader`, ale bardziej specyficzny dla kontrolerów administracyjnych, do ładowania zasobów dla `AdminOpenGraphController`. |
| `moduleRoutes` (PrestaShop 1.7+) | Pozwala modułom definiować niestandardowe trasy. | Nie jest jawnie używany do podstawowej funkcji tego modułu, ale może być obecny dla przyszłych rozszerzeń lub specyficznej obsługi adresów URL. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego oraz dostępu do najnowszych wersji modułu „Tagi Open Graph Facebooka”, prosimy odwiedzić swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
