---
title: "HTML Box Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop HTML Box Pro od MyPresta.eu."
sidebar:
  label: "HTML Box Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł HTML Box Pro na MyPresta.eu](https://mypresta.eu/modules/front-office-features/html-box-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/html-box-pro/)
>
> ---


# HTML Box Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > HTML Box Pro)

To jest główny ekran, na którym zarządzasz wszystkimi swoimi Pudełkami HTML. Moduł przedstawia listę istniejących pudełek oraz opcje dodawania nowych lub modyfikowania ustawień globalnych.

#### Sekcja Ustawienia globalne

Na górze strony konfiguracji znajdziesz kilka ustawień globalnych, które wpływają na działanie modułu.

-   **Użyj modułu wewnętrznego**

    *   **Co robi to ustawienie:** Jest to starsze ustawienie, które zazwyczaj odnosi się do wewnętrznego mechanizmu aktualizacji modułu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone („Wł.”):* Moduł może używać własnych wewnętrznych metod do sprawdzania aktualizacji.
        *   *Gdy wyłączone („Wył.”):* Moduł będzie polegał na standardowych mechanizmach aktualizacji PrestaShop lub ręcznych aktualizacjach.
    *   **Zalecana wartość:** „Wł.” (chyba że występują problemy, wtedy spróbuj „Wył.”).
    *   **Scenariusz/przykład dla sprzedawcy:** Zazwyczaj pozostaw to włączone. Jeśli napotkasz problemy z aktualizacjami modułu lub powiadomieniami, Twój webmaster może zasugerować przełączenie tego.
-   **Zapobiegaj usuwaniu adresów URL z obrazów**

    *   **Co robi to ustawienie:** Kiedy używasz wbudowanego edytora TinyMCE (edytora tekstu sformatowanego) do dodawania obrazów, czasami może on automatycznie usuwać pełną ścieżkę URL, zwłaszcza jeśli kopiujesz i wklejasz zawartość. To ustawienie zapobiega takiemu zachowaniu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone („Wł.”):* Adresy URL obrazów, które wstawiasz do zawartości pola HTML, zostaną zachowane dokładnie tak, jak je wpiszesz, zapobiegając uszkodzonym linkom do obrazów.
        *   *Gdy wyłączone („Nie”):* Edytor może modyfikować lub usuwać części adresów URL obrazów, co potencjalnie prowadzi do nieprawidłowego wyświetlania obrazów.
    *   **Zalecana wartość:** „Wł.”
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli dodajesz obrazy ze źródeł zewnętrznych (np. CDN lub innej strony internetowej) lub nawet wewnętrzne obrazy z absolutnymi ścieżkami, włączenie tego zapewnia, że Twoje obrazy zawsze się wyświetlają.
-   **Nie ładuj bibliotek tinyMCE**

    *   **Co robi to ustawienie:** TinyMCE to edytor tekstu sformatowanego, który pozwala łatwo formatować tekst, dodawać obrazy i tworzyć tabele bez bezpośredniego pisania kodu HTML. To ustawienie kontroluje, czy moduł ładuje własną wersję edytora TinyMCE.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone („Wł.”):* Moduł NIE załaduje swojego edytora TinyMCE. Może to być przydatne, jeśli Twój szablon lub inny moduł już ładuje TinyMCE, zapobiegając konfliktom lub podwójnemu ładowaniu. Jednak stracisz wizualny edytor dla swoich pól HTML i będziesz musiał pisać surowy kod HTML.
        *   *Gdy wyłączone („Wył.”):* Moduł załaduje swój edytor TinyMCE, zapewniając przyjazny dla użytkownika interfejs do tworzenia i edytowania zawartości pola HTML.
    *   **Zalecana wartość:** „Wył.” (chyba że jesteś programistą i wolisz pisać surowy kod HTML, lub jeśli występują konflikty z innymi instancjami TinyMCE).
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz używać edytora wizualnego do łatwego dodawania tekstu, pogrubienia, kursywy, obrazów i linków bez znajomości HTML, pozostaw to „Wył.”. Jeśli widzisz dziwne zachowanie edytora lub błędy w konsoli, programista może zasugerować włączenie tego w celu rozwiązania problemu.

#### Sekcja Zarządzanie Pudełkami HTML

Poniżej ustawień globalnych znajdziesz tabelę zawierającą listę wszystkich utworzonych pudełek HTML. Z tego miejsca możesz dodawać nowe pudełka, edytować istniejące lub je usuwać.

-   **Dodaj nowe pudełko HTML** (Przycisk)

    *   **Co to robi:** Kliknięcie tego przycisku przenosi Cię do nowego formularza, w którym możesz zdefiniować zupełnie nowe pudełko HTML.
    *   **Efekt:** Otwiera formularz „Dodaj nowe pudełko HTML”.
-   **Edytuj** (Ikona obok każdego pudełka)

    *   **Co to robi:** Pozwala modyfikować ustawienia i zawartość istniejącego pudełka HTML.
    *   **Efekt:** Otwiera formularz „Edytuj pudełko HTML”, wstępnie wypełniony bieżącymi ustawieniami pudełka.
-   **Usuń** (Ikona obok każdego pudełka)

    *   **Co to robi:** Trwale usuwa pudełko HTML z Twojego sklepu.
    *   **Efekt:** Pudełko HTML nie będzie już wyświetlane w Twoim front office. Ta akcja jest nieodwracalna.
    *   **Zalecana wartość:** Usuwaj tylko te pudełka, których już nie potrzebujesz.

#### Formularz Dodaj/Edytuj Pudełko HTML

Po kliknięciu „Dodaj nowe pudełko HTML” lub „Edytuj” istniejące, zobaczysz formularz z następującymi polami:

-   **Nazwa**

    *   **Co robi to ustawienie:** Jest to wewnętrzna nazwa Twojego pudełka HTML, widoczna tylko w Panelu administracyjnym. Pomaga Ci identyfikować różne pudełka.
    *   **Efekt zmiany tego ustawienia:** Zmienia etykietę dla tego pudełka na liście konfiguracji modułu. Brak efektu w front office.
    *   **Zalecana wartość:** Opisowa nazwa (np. „Baner strony głównej - Letnia wyprzedaż”, „Odznaki zaufania na stronie produktu”, „Informacje kontaktowe w stopce”).
    *   **Scenariusz/przykład dla sprzedawcy:** Jasne nazywanie pudełek pomaga szybko je znaleźć i zarządzać nimi, zwłaszcza gdy Twój sklep rośnie i dodajesz więcej niestandardowych treści.
-   **Sklep** (Widoczne tylko w środowiskach wielosklepowych)

    *   **Co robi to ustawienie:** Jeśli prowadzisz wiele sklepów z jednej instalacji PrestaShop, pozwala to określić, na których sklepach to pudełko HTML ma się pojawić.
    *   **Efekt zmiany tego ustawienia:** Pudełko HTML będzie wyświetlane tylko w wybranych sklepach.
    *   **Zalecana wartość:** Wybierz konkretne sklepy, dla których treść jest istotna.
    *   **Scenariusz/przykład dla sprzedawcy:** Możesz mieć inny baner promocyjny dla swojego francuskiego sklepu niż dla niemieckiego.
-   **Pozycja**

    *   **Co robi to ustawienie:** Jest to najważniejsze ustawienie, określające *gdzie* w Twoim sklepie pojawi się pudełko HTML. Jest to lista rozwijana wszystkich dostępnych hooków PrestaShop.
    *   **Efekt zmiany tego ustawienia:** Zawartość Twojego pudełka HTML zostanie wyrenderowana w wybranej lokalizacji hooka.
    *   **Zalecana wartość:** Wybierz hook, który najlepiej pasuje do celu treści (np. `displayHeader` dla górnego banera, `displayLeftColumn` dla bloku bocznego).
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz dodać wiadomość „Darmowa wysyłka” powyżej opisów produktów, wybierz `displayProductAdditionalInfo`.
-   **Aktywny**

    *   **Co robi to ustawienie:** Kontroluje, czy pudełko HTML jest aktualnie widoczne w Twoim sklepie.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone („Wł.”):* Pudełko HTML zostanie wyświetlone w Twoim front office.
        *   *Gdy wyłączone („Wył.”):* Pudełko HTML zostanie ukryte, ale jego zawartość i ustawienia są zapisane, co pozwala na ponowne aktywowanie go później.
    *   **Zalecana wartość:** „Wł.” dla aktywnej treści, „Wył.” dla treści, którą chcesz tymczasowo ukryć lub przygotować do przyszłego użycia.
    *   **Scenariusz/przykład dla sprzedawcy:** Możesz przygotować pudełko z promocją świąteczną z wyprzedzeniem, pozostawić je „Wył.”, a następnie przełączyć na „Wł.”, gdy nadejdzie czas, bez konieczności ponownego tworzenia.
-   **Tylko na stronach zabezpieczonych (SSL)**

    *   **Co robi to ustawienie:** Ogranicza wyświetlanie pudełka HTML do stron ładowanych przez HTTPS (bezpieczne połączenie).
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone („Wł.”):* Pudełko pojawi się tylko na stronach z `https://` w adresie URL.
        *   *Gdy wyłączone („Wył.”):* Pudełko pojawi się zarówno na stronach bezpiecznych (HTTPS), jak i niezabezpieczonych (HTTP) (jeśli Twój sklep nadal używa HTTP, co nie jest zalecane).
    *   **Zalecana wartość:** „Wł.”, jeśli treść zawiera wrażliwe informacje lub jeśli chcesz upewnić się, że ładuje się tylko na bezpiecznych stronach. Ogólnie rzecz biorąc, wszystkie nowoczesne sklepy powinny być w pełni HTTPS, więc może to nie być ściśle konieczne, ale dodaje dodatkową warstwę kontroli.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoje pudełko HTML zawiera odznakę płatności lub pieczęć bezpieczeństwa, możesz chcieć upewnić się, że pojawia się tylko na bezpiecznych stronach, aby wzmocnić zaufanie.
-   **Tylko na stronie głównej**

    *   **Co robi to ustawienie:** Ogranicza wyświetlanie pudełka HTML tylko do strony głównej Twojego sklepu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone („Wł.”):* Pudełko pojawi się tylko wtedy, gdy klienci odwiedzą Twoją główną stronę główną.
        *   *Gdy wyłączone („Wył.”):* Pudełko pojawi się na wszystkich stronach, na których dostępna jest wybrana „Pozycja” (hook).
    *   **Zalecana wartość:** „Wył.”, chyba że treść jest specjalnie zaprojektowana dla strony głównej.
    *   **Scenariusz/przykład dla sprzedawcy:** Duży baner promocyjny dla wyprzedaży w całym sklepie byłby zazwyczaj ustawiony na „Wł.” dla tej opcji, jeśli chcesz go tylko na stronie głównej, lub „Wył.”, jeśli chcesz, aby pojawiał się w nagłówku na każdej stronie.
-   **Zawartość** (To jest główny edytor treści)

    *   **Co robi to ustawienie:** To tutaj wprowadzasz rzeczywisty kod HTML, JavaScript lub CSS, który zostanie wyświetlony. Używa edytora tekstu sformatowanego TinyMCE (jeśli nie jest globalnie wyłączony) do łatwego tworzenia treści.
    *   **Efekt zmiany tego ustawienia:** Wprowadzona tutaj treść zostanie wyrenderowana w Twoim front office w wybranym hooku.
    *   **Zalecana wartość:** Wprowadź pożądaną treść. Możesz użyć:
        *   Zwykłego tekstu
        *   HTML (np. `<p>Witaj Świecie!</p>`, tagi `<img>`, linki `<a>`)
        *   CSS (zawarte w tagach `<style>`, np. `<style>.moja-klasa { color: red; }</style>`)
        *   JavaScript (zawarte w tagach `<script>`, np. `<script>alert('Witaj!');</script>`)
    *   **Scenariusz/przykład dla sprzedawcy:**
        *   *HTML:* Dodawanie niestandardowego obrazu banera: `<img src="https://twojskep.com/img/cms/baner.jpg" alt="Letnia wyprzedaż" style="width:100%;">`
        *   *JavaScript:* Osadzanie kodu śledzącego Google Analytics: `<script> (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){ (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o), m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m) })(window,document,'script','//www.google-analytics.com/analytics.js','ga'); ga('create', 'UA-XXXXX-Y', 'auto'); ga('send', 'pageview'); </script>`
        *   *CSS:* Zmiana koloru konkretnego elementu: `<style> #header .logo { border: 2px solid blue; } </style>`

#### 2.1.1 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Główna strona konfig. | Użyj modułu wewnętrznego | Wł. | Kontroluje wewnętrzny mechanizm aktualizacji. |
| Główna strona konfig. | Zapobiegaj usuwaniu adresów URL z obrazów | Wł. | Zapewnia zachowanie adresów URL obrazów w edytorze. |
| Główna strona konfig. | Nie ładuj bibliotek tinyMCE | Wył. | Włącza edytor wizualny do łatwego tworzenia treści. |
| Formularz Dodaj/Edytuj | Nazwa | Opisowa nazwa | Wewnętrzna etykieta dla pudełka HTML. |
| Formularz Dodaj/Edytuj | Sklep | Wszystkie sklepy | Wybiera, które sklepy wyświetlają treść (wielosklepowość). |
| Formularz Dodaj/Edytuj | Pozycja | (Wybierz Hook) | Określa, gdzie treść pojawia się w front office. |
| Formularz Dodaj/Edytuj | Aktywny | Wł. | Przełącza widoczność pudełka HTML w front office. |
| Formularz Dodaj/Edytuj | Tylko na stronach zabezpieczonych (SSL) | Wył. (lub Wł. jeśli krytyczne) | Ogranicza wyświetlanie do stron HTTPS. |
| Formularz Dodaj/Edytuj | Tylko na stronie głównej | Wył. | Ogranicza wyświetlanie tylko do strony głównej. |
| Formularz Dodaj/Edytuj | Zawartość | (Twój HTML/JS/CSS) | Rzeczywista treść do wyświetlenia. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje pudełko HTML nie wyświetla się w front office. Co powinienem sprawdzić?**
O1:

-   **Czy jest aktywne?** Przejdź do konfiguracji modułu i upewnij się, że przełącznik „Aktywny” dla Twojego pudełka jest ustawiony na „Wł.”.
-   **Poprawna pozycja (Hook)?** Sprawdź dokładnie, czy wybrałeś poprawną „Pozycję” (hook), w której spodziewasz się, że treść się pojawi. Niektóre hooki są specyficzne dla określonych stron (np. `displayProductAdditionalInfo` tylko na stronach produktów).
-   **Tylko strona główna?** Jeśli ustawiłeś „Tylko na stronie głównej” na „Wł.”, pojawi się tylko na Twojej głównej stronie głównej.
-   **Tylko SSL?** Jeśli „Tylko na stronach zabezpieczonych (SSL)” jest ustawione na „Wł.”, upewnij się, że przeglądasz stronę HTTPS.
-   **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) i pamięć podręczną przeglądarki.
-   **Błędy w treści:** Jeśli Twoja treść HTML/JS/CSS zawiera błędy, może to uniemożliwić renderowanie pudełka. Spróbuj prostego tekstu „Witaj Świecie”, aby przetestować.

**P2: Edytor TinyMCE (edytor wizualny) nie działa lub wygląda dziwnie.**
O2:

-   **Ustawienie „Nie ładuj bibliotek tinyMCE”:** Upewnij się, że jest ustawione na „Wył.” w globalnych ustawieniach modułu, jeśli chcesz używać edytora wizualnego.
-   **Konflikty z szablonem:** Czasami niestandardowe szablony lub inne moduły mogą kolidować z TinyMCE. Spróbuj tymczasowo wyłączyć inne moduły, aby sprawdzić, czy problem zostanie rozwiązany.
-   **Problemy z przeglądarką:** Spróbuj innej przeglądarki lub wyczyść pamięć podręczną i pliki cookie przeglądarki.

**P3: Moje obrazy lub linki są uszkodzone po zapisaniu zawartości pudełka HTML.**
O3:

-   **Ustawienie „Zapobiegaj usuwaniu adresów URL z obrazów”:** Upewnij się, że jest ustawione na „Wł.” w globalnych ustawieniach modułu.
-   **Ścieżki absolutne vs. względne:** Zawsze używaj absolutnych adresów URL (zaczynających się od `http://` lub `https://`) dla obrazów i linków, zwłaszcza jeśli są zewnętrzne lub jeśli chcesz, aby działały spójnie w całym Twoim sklepie.
-   **Sprawdź HTML:** Sprawdź wygenerowany kod HTML w edytorze (zazwyczaj przycisk „Kod źródłowy”), aby upewnić się, że atrybuty `src` i `href` są poprawne.

**P4: Jak przetłumaczyć zawartość moich pudełek HTML na różne języki?**
O4:

-   HTML Box Pro obsługuje treści wielojęzyczne. Podczas edycji pudełka HTML zobaczysz zakładki językowe (np. angielski, francuski, hiszpański) obok pola „Zawartość”.
-   Kliknij każdą zakładkę językową i wprowadź przetłumaczoną treść dla tego konkretnego języka. Moduł automatycznie wyświetli poprawną wersję językową Twoim klientom, w oparciu o ich wybrany język sklepu.

**P5: Treść wygląda dobrze na komputerze stacjonarnym, ale jest zniekształcona na urządzeniach mobilnych.**
O5:

-   **Responsywny projekt:** Upewnij się, że dodawana treść HTML jest zaprojektowana tak, aby była responsywna. Użyj właściwości CSS, takich jak `max-width: 100%; height: auto;` dla obrazów, i rozważ użycie zapytań mediów CSS w tagach `<style>` dla bardziej złożonych układów.
-   **Responsywność szablonu:** Chociaż sam moduł jest responsywny, jeśli Twój niestandardowy HTML nie jest, może to zepsuć układ. Dokładnie przetestuj na różnych urządzeniach.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł HTML Box Pro wykorzystuje standardową architekturę modułów PrestaShop, głównie klasę `Module` dla swojej podstawowej funkcjonalności i `getContent()` dla konfiguracji w Panelu administracyjnym. Dynamicznie rejestruje hooki i renderuje zawartość na podstawie przechowywanej konfiguracji. Moduł używa niestandardowej biblioteki `SmartyTemplatesManager` do zarządzania formularzami i szablonami w Panelu administracyjnym, zapewniając spójny interfejs użytkownika do dodawania i edytowania pudełek HTML. Zawartość jest przechowywana w tabeli `ps_configuration`, przy czym każde pudełko HTML jest reprezentowane przez unikalny klucz konfiguracyjny.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie używa dedykowanych kontrolerów front-office ani back-office w katalogach `controllers/front` lub `controllers/admin`. Cała logika Panelu administracyjnego jest obsługiwana w metodzie `getContent()` pliku `htmlboxpro.php`, która renderuje formularze i przetwarza przesłane dane. Renderowanie zawartości front-office jest obsługiwane bezpośrednio poprzez wykonanie hooków w głównym pliku modułu.

### 4.3 Klasy rdzenia i modele (`classes/`)

Moduł nie definiuje niestandardowych klas `ObjectModel` ani innych klas rdzenia w katalogu `classes/`. Całe zarządzanie danymi i logika biznesowa są hermetyzowane w głównym pliku modułu `htmlboxpro.php`. Konfiguracje pudełek HTML są przechowywane bezpośrednio w tabeli `ps_configuration`, z kluczami takimi jak `hbp_name_X`, `hbp_content_X_Y`, `hbp_hook_X` itd., gdzie `X` to ID pudełka, a `Y` to ID języka.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `htmlboxpro/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`
    *   **Zakres:** Panel administracyjny.
    *   **Odpowiedzialność:** Zapewnia funkcjonalność JavaScript dla biblioteki `SmartyTemplatesManager`, która jest używana do renderowania i zarządzania formularzami konfiguracyjnymi modułu (np. dodawanie/edycja pudełek HTML). Obejmuje to dynamiczne elementy formularzy, interakcje AJAX do zapisywania/ładowania danych szablonu i potencjalnie zarządzanie zakładkami.
-   `htmlboxpro/views/js/script.js`
    *   **Zakres:** Panel administracyjny.
    *   **Odpowiedzialność:** Zawiera JavaScript specyficzny dla modułu dla strony konfiguracji Panelu administracyjnego. Może to obejmować słuchacze zdarzeń dla przesyłania formularzy, dynamiczne aktualizacje listy pudełek HTML lub inne ulepszenia interfejsu użytkownika specyficzne dla HTML Box Pro.
-   `htmlboxpro/views/js/tinymce16-force-urls.inc.js`
    *   **Zakres:** Panel administracyjny.
    *   **Odpowiedzialność:** Ten skrypt jest ładowany, gdy opcja „Zapobiegaj usuwaniu adresów URL z obrazów” jest włączona. Zawiera konfigurację i wtyczki TinyMCE specjalnie zaprojektowane, aby zapobiec usuwaniu lub modyfikowaniu absolutnych adresów URL przez edytor, szczególnie dla obrazów. Zapewnia, że atrybuty `src` pozostają nienaruszone.
-   `htmlboxpro/views/js/tinymce16.inc.js`
    *   **Zakres:** Panel administracyjny.
    *   **Odpowiedzialność:** Ten skrypt zawiera podstawową inicjalizację i konfigurację edytora TinyMCE dla modułu. Definiuje pasek narzędzi edytora, wtyczki i ogólne zachowanie podczas edycji zawartości pudełka HTML. Jest ładowany, gdy opcja „Nie ładuj bibliotek tinyMCE” jest wyłączona.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `htmlboxpro/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`
    *   **Zakres:** Stylizacja formularza administracyjnego w Panelu administracyjnym.
    *   **Odpowiedzialność:** Zapewnia stylizację dla komponentów interfejsu użytkownika biblioteki `SmartyTemplatesManager`, zapewniając spójny wygląd formularzy konfiguracyjnych modułu w Panelu administracyjnym PrestaShop.
-   `htmlboxpro/views/css/styles.css`
    *   **Zakres:** Stylizacja formularza administracyjnego w Panelu administracyjnym.
    *   **Odpowiedzialność:** Zawiera reguły CSS specyficzne dla modułu dla strony konfiguracji HTML Box Pro, takie jak stylizacja listy pudełek HTML, przycisków lub innych niestandardowych elementów w interfejsie administracyjnym modułu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł intensywnie wykorzystuje szablony Smarty dla swojego interfejsu Panelu administracyjnego.

-   **Szablony hooków (`htmlboxpro/`)**:
    *   `htmlboxpro/html.tpl`: To jest główny szablon front-office. Jest odpowiedzialny za renderowanie rzeczywistej zawartości pudełka HTML (`{$htmlboxpro_content}`) w wybranym hooku w front office.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   `htmlboxpro/views/templates/admin/_configure/helpers/form/form.tpl`: Ten szablon jest prawdopodobnie nadpisaniem lub specyficznym szablonem używanym przez formularz konfiguracyjny modułu, być może dostosowującym sposób, w jaki standardowy `HelperForm` PrestaShop renderuje swoje pola, zwłaszcza dla edytora TinyMCE.
-   **Szablony administracyjne (`views/templates/`)**:
    *   `htmlboxpro/views/custom_hook_info.tpl`: Prawdopodobnie wyświetla informacje lub instrukcje dotyczące niestandardowych hooków.
    *   `htmlboxpro/views/form-add-new.tpl`: Szablon dla formularza „Dodaj nowe pudełko HTML”.
    *   `htmlboxpro/views/form-edit.tpl`: Szablon dla formularza „Edytuj pudełko HTML”.
    *   `htmlboxpro/views/messages.tpl`: Używany do wyświetlania komunikatów o sukcesie, błędach lub informacyjnych w Panelu administracyjnym.
    *   `htmlboxpro/views/scripts.tpl`: Prawdopodobnie zawiera zasoby JavaScript i CSS dla strony konfiguracji Panelu administracyjnego.
-   **Szablony biblioteki SmartyTemplatesManager (`htmlboxpro/lib/smartyTemplatesManager/tpl/`, `htmlboxpro/lib/smartyTemplatesManager/views/`)**:
    *   `htmlboxpro/lib/smartyTemplatesManager/tpl/example.tpl`: Przykład szablonu, prawdopodobnie do celów rozwojowych lub demonstracyjnych w ramach biblioteki.
    *   `htmlboxpro/lib/smartyTemplatesManager/views/buttonManager.tpl`: Renderuje przyciski lub linki akcji w interfejsie `SmartyTemplatesManager`.
    *   `htmlboxpro/lib/smartyTemplatesManager/views/createTemplateForm.tpl`: Używany do tworzenia nowych szablonów/elementów w kontekście `SmartyTemplatesManager`.
    *   `htmlboxpro/lib/smartyTemplatesManager/views/editTemplateForm.tpl`: Używany do edycji istniejących szablonów/elementów w kontekście `SmartyTemplatesManager`.
    *   `htmlboxpro/lib/smartyTemplatesManager/views/mainForm.tpl`: Główna otoczka lub struktura dla formularzy zarządzanych przez `SmartyTemplatesManager`.
    *   `htmlboxpro/lib/smartyTemplatesManager/views/selectInput.tpl`: Ogólny szablon do renderowania rozwijanego pola wyboru.
    *   `htmlboxpro/lib/searchTool/views/scripts.tpl`: Prawdopodobnie zawiera zasoby JavaScript i CSS dla komponentu narzędzia wyszukiwania w Panelu administracyjnym.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    *   Moduł nie tworzy niestandardowych tabel SQL. Cała konfiguracja pudełek HTML jest przechowywana w standardowej tabeli PrestaShop `ps_configuration`.
    *   Klucze konfiguracyjne mają wzorzec, taki jak:
        *   `HBP_NAME_{ID}`: Nazwa pudełka HTML.
        *   `HBP_CONTENT_{ID}_{LANG_ID}`: Rzeczywista zawartość HTML/JS/CSS dla konkretnego pudełka i języka.
        *   `HBP_HOOK_{ID}`: Nazwa hooka, w którym wyświetlane jest pudełko.
        *   `HBP_ACTIVE_{ID}`: Wartość logiczna (0/1) wskazująca, czy pudełko jest aktywne.
        *   `HBP_SSL_{ID}`: Wartość logiczna (0/1) wskazująca, czy jest tylko na stronach SSL.
        *   `HBP_HOMEPAGE_{ID}`: Wartość logiczna (0/1) wskazująca, czy jest tylko na stronie głównej.
        *   `HBP_SHOP_{ID}`: Lista identyfikatorów sklepów oddzielonych przecinkami (dla wielu sklepów).
        *   `HBP_LAST_ID`: Przechowuje ostatnio używany identyfikator dla pudełka HTML w celu generowania unikalnych identyfikatorów.
        *   `HBP_NOTINYJS`: Globalne ustawienie dla „Nie ładuj bibliotek tinyMCE”.
        *   `HBP_FORCEURLS`: Globalne ustawienie dla „Zapobiegaj usuwaniu adresów URL z obrazów”.
        *   Inne klucze, takie jak `MYPRESTA_UPDATES`, `UPDATE_HTMLBOXPRO`, `UPDATEV_HTMLBOXPRO` do zarządzania aktualizacjami.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayAfterCarrier` | Po wyborze przewoźnika w kasie. | Wyświetlaj treści związane z opcjami wysyłki lub ostatnimi krokami. |
| `displayFooterBefore` | Przed główną zawartością stopki. | Dodaj treść powyżej standardowej stopki. |
| `displayLeftColumn` | W lewej kolumnie bocznej odpowiednich stron. | Wyświetlaj bloki boczne (np. kategorie, filtry, niestandardowe informacje). |
| `displayCustomerAccountForm` | W formularzu tworzenia/edycji konta klienta. | Dodaj niestandardowe pola lub informacje związane z kontami klientów. |
| `displayRightColumnProduct` | W prawej kolumnie bocznej na stronach produktów. | Wyświetlaj treści boczne specyficzne dla produktu (np. powiązane produkty, odznaki zaufania). |
| `displayBanner` | Na górze strony, zazwyczaj dla banera obejmującego całą witrynę. | Wyświetlaj banery promocyjne lub ogłoszenia. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny ustawia swoje media (CSS/JS). | Wstrzyknij niestandardowy CSS/JS do Panelu administracyjnego (używany przez moduł dla własnych zasobów administracyjnych). |
| `displayOrderConfirmation` | Na stronie potwierdzenia zamówienia po udanym zakupie. | Wyświetlaj wiadomości z podziękowaniami, informacje o śledzeniu lub oferty dodatkowe. |
| `displayHeader` | W sekcji `<head>` każdej strony. | Idealny do wstrzykiwania meta tagów, skryptów śledzących lub globalnego CSS/JS. |
| `displayCartExtraProductActions` | W podsumowaniu koszyka, w pobliżu akcji produktu. | Dodaj treści związane z produktami w koszyku (np. oferty dodatkowe, oferty krzyżowe, informacje o wysyłce). |
| `displayFooter` | W głównej sekcji stopki sklepu. | Dodaj ogólną zawartość stopki, linki lub informacje o prawach autorskich. |
| `displayPaymentByBinaries` | Podczas procesu wyboru płatności. | Wyświetlaj informacje związane z płatnościami lub pieczęcie zaufania. |
| `displayCustomerLoginFormAfter` | Po formularzu logowania klienta. | Dodaj treść poniżej formularza logowania (np. linki „zapomniałem hasła”, zachęty do rejestracji). |
| `displayReassurance` | W bloku zapewnienia produktu (często poniżej obrazu produktu). | Wyświetlaj elementy zaufania, takie jak darmowa wysyłka, bezpieczna płatność, łatwe zwroty. |
| `displayProductAdditionalInfo` | Poniżej opisu produktu lub głównego bloku informacyjnego. | Dodaj dodatkowe szczegóły produktu, tabele rozmiarów lub niestandardową treść. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest gotowy pomóc Ci w przypadku wszelkich problemów lub pytań dotyczących modułu HTML Box Pro.
