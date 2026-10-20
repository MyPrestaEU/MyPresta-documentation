---
title: "tinyMCE pro - rozszerzony edytor tekstu sformatowanego - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop tinyMCE pro - rozszerzony edytor tekstu sformatowanego od MyPresta.eu."
sidebar:
  label: "tinyMCE pro - rozszerzony edytor tekstu sformatowanego - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł tinyMCE pro - extended rich text editor na MyPresta.eu](https://mypresta.eu/modules/administration-tools/tinymce-pro-extended-rich-text-editor.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/tinymce-pro-extended-rich-text-editor/)
>
> ---


# tinyMCE pro - rozszerzony edytor tekstu sformatowanego

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj”, aby uzyskać dostęp do głównych ustawień modułu. Ten ekran umożliwia włączenie lub wyłączenie rozszerzonego edytora oraz zarządzanie jego podstawowymi funkcjonalnościami.

Strona konfiguracji „tinyMCE pro” została zaprojektowana tak, aby była prosta, ponieważ moduł działa głównie poprzez zastępowanie i ulepszanie istniejącego edytora bez rozbudowanych ustawień widocznych dla użytkownika poza jego aktywacją.

-   **Co robi to ustawienie:** Ten moduł działa głównie poprzez zastępowanie domyślnego edytora PrestaShop ulepszoną wersją tinyMCE. Strona konfiguracji będzie zazwyczaj zawierać przełącznik „Włącz/Wyłącz” dla samego modułu oraz potencjalnie opcje kontrolujące, do których konkretnych obszarów panelu administracyjnego powinien być stosowany rozszerzony edytor.
-   **Efekt zmiany tego ustawienia:**

    *   *Gdy włączony:* Standardowy, często ograniczony, edytor tekstu w obszarach takich jak opisy produktów, strony CMS i opisy kategorii zostanie zastąpiony edytorem „tinyMCE pro”. Ten nowy edytor będzie zawierał bogatszy pasek narzędzi z opcjami ikon Font Awesome, osadzania filmów z YouTube, akceptacji zaawansowanego kodu HTML/JavaScript i innych.
    *   *Gdy wyłączony:* Moduł przestanie działać, a PrestaShop powróci do swojego domyślnego edytora tekstu. Wszystkie zaawansowane funkcje dostarczane przez „tinyMCE pro” nie będą już dostępne.
-   **Zalecana wartość:** **Włączony**. Aby korzystać z funkcji modułu, powinien być zawsze włączony.
-   **Scenariusz/przykład dla sprzedawcy:** Edytujesz opis produktu dla nowego artykułu. Z włączonym „tinyMCE pro” możesz łatwo dodać film z YouTube prezentujący produkt, dołączyć ikony Font Awesome dla funkcji (np. ikonę zaznaczenia dla „Dostępny w magazynie”) i użyć zaawansowanego formatowania, aby stworzyć atrakcyjny wizualnie układ, wszystko bezpośrednio w edytorze. Jeśli wyłączony, byłbyś ograniczony do podstawowego formatowania tekstu.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | **Status modułu (Włącz/Wyłącz)** | Włączony | Kontroluje, czy rozszerzony edytor tinyMCE zastępuje domyślny edytor PrestaShop w panelu administracyjnym. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Włączyłem moduł, ale edytor nadal wygląda tak samo. Co powinienem zrobić?**
**O1:** Po włączeniu dowolnego modułu, który modyfikuje panel administracyjny, dobrą praktyką jest wyczyszczenie pamięci podręcznej przeglądarki i pamięci podręcznej Smarty PrestaShop.
- **Pamięć podręczna przeglądarki:** Odśwież przeglądarkę (Ctrl+F5 lub Cmd+Shift+R).
- **Pamięć podręczna PrestaShop:** Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym PrestaShop. Kliknij przycisk „Wyczyść pamięć podręczną” w prawym górnym rogu.

**P2: Niektóre nowe funkcje edytora (takie jak ikony Font Awesome) nie wyświetlają się poprawnie w moim front-office.**
**O2:** Zazwyczaj wskazuje to na konflikt z CSS lub JavaScript Twojego niestandardowego motywu.
- **Sprawdź konflikty:** Tymczasowo przełącz się na domyślny motyw PrestaShop (Classic lub Hummingbird) i sprawdź, czy funkcje wyświetlają się poprawnie. Jeśli tak, problem leży w Twoim niestandardowym motywie.
- **Dostosowanie motywu:** Twój motyw może nadpisywać lub nie zawierać niezbędnych CSS/JS dla tych elementów. Może być konieczne skonsultowanie się z deweloperem motywu lub webmasterem w celu prawidłowej integracji zasobów front-office modułu z Twoim motywem.

**P3: Czy mogę używać tego edytora dla wszystkich języków w moim sklepie?**
**O3:** Tak, edytor tinyMCE jest zaprojektowany do bezproblemowej współpracy z wielojęzycznymi możliwościami PrestaShop. Kiedy zmienisz język w panelu administracyjnym, edytor będzie nadal dostępny do wprowadzania treści w wybranym języku. Moduł zawiera również pliki językowe dla wielu swoich wtyczek (np. Font Awesome, PowerPaste), zapewniając zlokalizowane doświadczenie tam, gdzie jest to dostępne.

**P4: Widzę błąd po zainstalowaniu modułu, lub mój panel administracyjny działa wolno.**
**O4:**
- **Sprawdź logi błędów serwera:** Pierwszym krokiem jest zawsze sprawdzenie logów błędów PHP serwera. Te logi często dostarczają szczegółowych informacji o tym, co poszło nie tak.
- **Wyłącz inne moduły:** Tymczasowo wyłącz inne niedawno zainstalowane lub złożone moduły, aby wykluczyć konflikty.
- **Wersja PHP:** Upewnij się, że Twoja wersja PHP mieści się w obsługiwanym zakresie (PHP 7.1 - 8.5). Niekompatybilna wersja PHP może powodować różne problemy.
- **Skontaktuj się z pomocą techniczną:** Jeśli problem nadal występuje, zbierz wszelkie komunikaty o błędach i skontaktuj się z pomocą techniczną MyPresta.eu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych, które utrzymują lub rozszerzają sklep.

### 4.1 Przegląd architektury

Moduł `tinyMCE pro` działa głównie poprzez nadpisywanie domyślnej klasy `Validate` PrestaShop, aby zapewnić kompatybilność z rozszerzoną zawartością HTML generowaną przez ulepszony edytor tinyMCE. Wstrzykuje on własną wersję biblioteki tinyMCE i wiele wtyczek do panelu administracyjnego, skutecznie zastępując standardowy edytor. Podstawowa logika modułu znajduje się w `index.php`, który obsługuje instalację, deinstalację i formularz konfiguracji. Wykorzystuje system hooków PrestaShop do ładowania swoich zasobów i inicjalizacji edytora tam, gdzie jest to potrzebne.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Jego funkcjonalność jest głównie zintegrowana poprzez główny plik modułu (`index.php`) i poprzez nadpisywanie podstawowych klas PrestaShop.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   **`tinymcepro/override/classes/index.php`**: Ten plik jest zazwyczaj pustym placeholderem, aby zapobiec listowaniu katalogów, co jest powszechną praktyką bezpieczeństwa. Nie zawiera żadnych funkcjonalnych definicji klas.
-   **`tinymcepro/override/classes/Validate.php`**:
    *   **Cel**: Jest to kluczowe nadpisanie. Klasa `Validate` PrestaShop jest odpowiedzialna za sanitację i walidację różnych danych wejściowych, w tym treści HTML. Domyślna metoda `isCleanHtml()` może być zbyt restrykcyjna dla bogatej treści, usuwając prawidłowe elementy HTML5, atrybuty lub JavaScript, które rozszerzony edytor tinyMCE może generować.
    *   **Logika nadpisania**: To nadpisanie prawdopodobnie modyfikuje lub rozszerza metodę `isCleanHtml()` (lub powiązane metody walidacji), aby zezwolić na szerszy zakres HTML, atrybutów i potencjalnie osadzonych skryptów/stylów, zapewniając, że treść generowana przez tinyMCE pro nie zostanie usunięta ani uznana za nieprawidłową przez podstawową walidację PrestaShop.
    *   **Wpływ**: Programiści powinni być świadomi, że to nadpisanie zmienia podstawowe zachowanie walidacji. Jeśli istnieją niestandardowe reguły walidacji lub inne moduły polegają na ścisłej `isCleanHtml()`, mogą pojawić się konflikty.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł zawiera szeroki wachlarz plików JavaScript, głównie dla podstawowej biblioteki tinyMCE i jej licznych wtyczek.

-   **`tinymcepro/js/accordion.js`**: Prawdopodobnie niestandardowy skrypt do obsługi funkcjonalności akordeonu w front-office, być może związany z wtyczką tinyMCE `bootstrapaccordion`.
-   **`tinymcepro/js/alerts.js`**: Niestandardowy skrypt do obsługi komunikatów alertów, potencjalnie powiązany z wtyczką Bootstrap alert.
-   **`tinymcepro/js/fancybox.js`**: Integracja biblioteki Fancybox dla lightboxów, prawdopodobnie używana do wyświetlania obrazów lub mediów w wynikach edytora.
-   **`tinymcepro/js/readmore.js`**: Skrypt do implementacji funkcjonalności „czytaj więcej”, zwijający długie sekcje treści.
-   **`tinymcepro/js/tinymce-cmscategory.js`**: Specyficzny skrypt inicjalizacji lub konfiguracji tinyMCE używanego w polach opisu CMS lub kategorii.
-   **`tinymcepro/lib/htmlTemplatesManager/js/htmlTemplatesManager.js`**: Podstawowy JavaScript dla wtyczki HTML Templates Manager, umożliwiający tworzenie, edytowanie i wstawianie predefiniowanych fragmentów HTML.
-   **`tinymcepro/lib/plugins/bootstrapaccordion/plugin.js`**: Wtyczka tinyMCE do wstawiania i zarządzania akordeonami w stylu Bootstrap.
-   **`tinymcepro/lib/plugins/codesample/plugin.js`**: Wtyczka tinyMCE do wstawiania i podświetlania składni próbek kodu. Zawiera `prism.css` do stylizacji.
-   **`tinymcepro/lib/plugins/editattributes/plugin.js`**: Wtyczka tinyMCE do łatwej edycji atrybutów HTML wybranych elementów.
-   **`tinymcepro/lib/plugins/fontawesome/langs/*.js`**: Pliki językowe dla wtyczki Font Awesome tinyMCE.
-   **`tinymcepro/lib/plugins/lineheight/index.js`, `langs/de.js`, `plugin.js`**: Wtyczka tinyMCE do kontrolowania wysokości linii tekstu.
-   **`tinymcepro/lib/plugins/paragraph/*.js`**: Złożona wtyczka do zarządzania stylami akapitów i potencjalnie wyświetlania elementów blokowych. Zawiera kilka wewnętrznych skryptów narzędziowych.
-   **`tinymcepro/lib/plugins/powerpaste/*.js`**: Zaawansowana wtyczka tinyMCE do czyszczenia i sanitacji treści wklejanych z Microsoft Word, Google Docs itp. Zawiera wiele plików językowych.
-   **`tinymcepro/lib/plugins/smileys/plugin.js`**: Wtyczka tinyMCE do wstawiania emoji/buźek.
-   **`tinymcepro/lib/plugins/youtube/includes/youtube.js`, `plugin.js`**: Wtyczka tinyMCE do osadzania filmów z YouTube.
-   **`tinymcepro/lib/tinymce.inc.js`**: Prawdopodobnie główny plik biblioteki tinyMCE lub niestandardowy plik kompilacji/konfiguracji dla edytora.
-   **`tinymcepro/lib/tinymce_loader.js`**: Skrypt odpowiedzialny za ładowanie i inicjalizację instancji edytora tinyMCE w całym panelu administracyjnym PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`tinymcepro/css/tinymcepro.css`**: Ogólne niestandardowe style dla modułu, potencjalnie dla jego strony konfiguracji lub elementów front-office.
-   **`tinymcepro/css.css`**: Inny ogólny arkusz stylów, być może dla starszych wersji PrestaShop lub specyficznych elementów interfejsu użytkownika.
-   **`tinymcepro/lib/editor.css`**: Podstawowy CSS dla samego edytora tinyMCE, definiujący jego wygląd w panelu administracyjnym.
-   **`tinymcepro/lib/htmlTemplatesManager/css/htmlTemplatesManager.css`**: Style dla interfejsu HTML Templates Manager.
-   **`tinymcepro/lib/iconset.css`**: Prawdopodobnie zawiera style dla niestandardowych ikon używanych w edytorze lub module.
-   **`tinymcepro/lib/plugins/bs_alert/assets/css/bootstrap.css`, `plugin.css`**: CSS Bootstrap i specyficzne style wtyczki dla wtyczki Bootstrap Alert tinyMCE.
-   **`tinymcepro/lib/plugins/bs_images/assets/css/bootstrap.css`, `plugin.css`**: CSS Bootstrap i specyficzne style wtyczki dla wtyczki Bootstrap Images tinyMCE.
-   **`tinymcepro/lib/plugins/codesample/css/prism.css`**: Arkusz stylów do podświetlania składni używany przez wtyczkę `codesample`.
-   **`tinymcepro/lib/plugins/powerpaste/css/editorcss.css`**: Style specyficzne dla wtyczki PowerPaste, potencjalnie dla wizualnej informacji zwrotnej podczas wklejania.
-   **`tinymcepro/lib/plugins/tinyplusBootstrapTools/flat-blue.css`, `res-show-blocks-style.css`**: Dodatkowe style związane z Bootstrapem lub wyświetlaniem bloków, być może dla specyficznych motywów edytora lub narzędzi.
-   **`tinymcepro/lib/plugins/youtube/includes/youtube.css`**: Style dla funkcjonalności osadzania filmów z YouTube.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`tinymcepro/header.tpl`**: Ten szablon jest prawdopodobnie podłączony do `displayHeader`, aby załadować niezbędne zasoby CSS i JavaScript dla modułu, zarówno w panelu administracyjnym (dla samego edytora), jak i potencjalnie w front-office (dla renderowanej treści, takiej jak akordeony lub fancybox).
-   **`tinymcepro/lib/htmlTemplatesManager/views/buttonManager.tpl`**: Szablon dla przycisku lub interfejsu, który otwiera HTML Templates Manager.
-   **`tinymcepro/lib/htmlTemplatesManager/views/createTemplateForm.tpl`**: Szablon formularza do tworzenia nowych szablonów HTML.
-   **`tinymcepro/lib/htmlTemplatesManager/views/editTemplateForm.tpl`**: Szablon formularza do edytowania istniejących szablonów HTML.
-   **`tinymcepro/lib/htmlTemplatesManager/views/mainForm.tpl`**: Główny szablon interfejsu dla HTML Templates Manager.
-   **`tinymcepro/lib/htmlTemplatesManager/views/selectInput.tpl`**: Szablon wielokrotnego użytku dla rozwijanego pola wyboru w menedżerze szablonów.
-   **`tinymcepro/views/admin/fonts.tpl`**: Szablon związany z wyborem lub wyświetlaniem czcionek, być może do niestandardowej integracji czcionek w edytorze.
-   **`tinymcepro/views/admin/form.tpl`**: Główny szablon formularza konfiguracji modułu, renderowany za pomocą `getContent()` w `index.php`.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Ten moduł nie wydaje się tworzyć niestandardowych tabel SQL. Jego ustawienia konfiguracyjne są przechowywane w `ps_configuration` (np. `PS_TINYMCEPRO_ENABLED`). Szablony HTML tworzone za pomocą `htmlTemplatesManager` mogą być przechowywane w niestandardowej tabeli lub serializowane również w `ps_configuration`, chociaż nie ma jawnego pliku SQL, co sugeruje dynamiczne tworzenie lub przechowywanie konfiguracji.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renderuje się w sekcji `<head>` panelu administracyjnego PrestaShop. | Wstrzykuje niezbędne pliki CSS i JavaScript, aby edytor tinyMCE i jego wtyczki mogły działać. Tutaj ładowana jest podstawowa biblioteka tinyMCE i jej skrypty inicjalizacyjne. |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje zasoby medialne. | Pozwala modułowi dodawać swoje specyficzne pliki JS/CSS do bieżącej strony administracyjnej, zapewniając, że edytor tinyMCE jest ładowany tylko na stronach, gdzie jest potrzebny (np. edycja produktu, edycja strony CMS). |
| `actionGetContentEditor` | (Jeśli niestandardowy hook) | Ten hook byłby używany do zastąpienia domyślnej instancji edytora ulepszonym edytorem tinyMCE modułu. |
| `displayHeader` | Renderuje się w sekcji `<head>` front-office. | Potencjalnie ładuje zasoby specyficzne dla front-office (takie jak `accordion.js`, `fancybox.js`, `tinymcepro.css`), jeśli treść generowana przez edytor wymaga specjalnego stylizowania lub JavaScriptu do poprawnego wyświetlania (np. akordeony, lightboxy). |
| `displayRightColumn` | Renderuje się w prawej kolumnie front-office. | (Mało prawdopodobne, aby było używane bezpośrednio do funkcjonalności edytora, ale mogłoby być używane do wyświetlania treści *utworzonych* przez edytor, gdyby moduł miał widżet front-office). |
| `displayLeftColumn` | Renderuje się w lewej kolumnie front-office. | (Podobnie jak `displayRightColumn`). |
| `displayFooter` | Renderuje się w stopce front-office. | Może być używane do ładowania niekrytycznego JavaScriptu lub CSS do wyświetlania w front-office. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkiej dalszej pomocy z modułem „tinyMCE pro - rozszerzony edytor tekstu sformatowanego”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w instalacji, konfiguracji i rozwiązywaniu problemów.
