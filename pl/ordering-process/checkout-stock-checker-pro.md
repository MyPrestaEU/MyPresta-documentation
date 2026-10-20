---
title: "Checkout stock checker PRO - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop Checkout stock checker PRO od MyPresta.eu."
sidebar:
  label: "Checkout stock checker PRO"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Checkout stock checker PRO na MyPresta.eu](https://mypresta.eu/modules/ordering-process/checkout-stock-checker-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/checkout-stock-checker-pro/)
>
> ---


# Checkout stock checker PRO

## 1. Wymagania i kompatybilność

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 5.6 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i dostępne w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównego i jedynego ekranu konfiguracji modułu „Checkout stock checker PRO”. Ten ekran umożliwia włączenie lub wyłączenie podstawowej funkcjonalności modułu.

#### **Włącz / Wyłącz moduł**
-   **Co robi to ustawienie:** Jest to główny przełącznik do włączania i wyłączania funkcji sprawdzania stanu magazynowego.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączony (TAK):* Moduł będzie aktywnie sprawdzał poziomy zapasów produktów tuż przed złożeniem zamówienia. Jeśli produkt jest niedostępny, klient zostanie przekierowany do koszyka z powiadomieniem.
    -   *Gdy wyłączony (NIE):* Moduł będzie nieaktywny. Sprawdzanie stanu magazynowego nie będzie miało miejsca, a klienci mogą składać zamówienia na produkty, których nie ma na stanie, polegając wyłącznie na domyślnym zachowaniu zarządzania zapasami PrestaShop (które zazwyczaj sprawdza tylko przy dodawaniu do koszyka, a nie przy ostatecznym złożeniu zamówienia).
-   **Zalecana wartość:** **TAK**. Aby w pełni korzystać z przeznaczenia modułu, powinien być zawsze włączony.
-   **Scenariusz / przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz zacząć zapobiegać zamówieniom produktów, których nie ma na stanie. Ustawisz to na „TAK”. Jeśli tymczasowo musisz wyłączyć tę funkcję w celu konserwacji lub testowania, ustawisz ją na „NIE”.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Strona konfiguracji modułu | Włącz / Wyłącz moduł | TAK | Kontroluje, czy moduł aktywnie sprawdza stan magazynowy przed złożeniem zamówienia. Zapobiega zamówieniom produktów, których nie ma na stanie, gdy jest włączony. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moduł jest włączony, ale klienci nadal składają zamówienia na produkty, których nie ma na stanie. Co jest nie tak?**
O:
1.  **Wyczyść pamięć podręczną:** Najpierw spróbuj wyczyścić pamięć podręczną PrestaShop. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
2.  **Sprawdź status modułu:** Upewnij się, że moduł jest rzeczywiście włączony na stronie konfiguracji.
3.  **Konflikty motywów:** Niektóre mocno dostosowane motywy lub inne moduły modyfikujące proces realizacji zamówienia mogą powodować zakłócenia. Tymczasowo przełącz się na domyślny motyw PrestaShop (Classic) i przetestuj ponownie. Jeśli działa, problem prawdopodobnie leży w konflikcie motywu i może być konieczne, aby programista to zbadał.
4.  **Wersja PrestaShop:** Upewnij się, że pobrałeś prawidłową wersję modułu dla swojej konkretnej instalacji PrestaShop.

**P: Moi klienci są przekierowywani do koszyka, ale komunikat powiadomienia nie wyświetla się lub jest źle ostylowany.**
O:
1.  **Wyczyść pamięć podręczną:** Jak zawsze, wyczyść pamięć podręczną PrestaShop.
2.  **Stylizacja motywu:** Komunikat powiadomienia używa standardowych klas alertów PrestaShop. Jeśli Twój motyw mocno dostosował lub usunął te style, wiadomość może być niewidoczna lub nieprawidłowo sformatowana. Webmaster może sprawdzić kod HTML i CSS, aby upewnić się, że wiadomość jest obecna i prawidłowo ostylowana.
3.  **Pliki modułu:** Upewnij się, że wszystkie pliki modułu zostały prawidłowo przesłane. Czasami niekompletne przesyłanie może prowadzić do brakujących plików szablonów dla powiadomień.

**P: Czy ten moduł działa ze sklepami wielojęzycznymi?**
O: Tak, moduł wykorzystuje standardowe mechanizmy tłumaczenia PrestaShop. Komunikaty powiadomień wyświetlane klientom mogą być tłumaczone na wszystkie języki skonfigurowane w Twoim sklepie. Tłumaczenia te można zarządzać w **Międzynarodowe > Tłumaczenia > Tłumaczenia zainstalowanych modułów**.

**P: Czy ten moduł spowolni proces realizacji zamówienia?**
O: Sprawdzanie stanu magazynowego wykonywane przez moduł jest bardzo szybkie, zazwyczaj dodając tylko milisekundy do procesu realizacji zamówienia. Jest to bezpośrednie zapytanie do bazy danych o poziomy zapasów, które jest wysoce zoptymalizowane. Wpływ na wydajność jest znikomy i znacznie przewyższa korzyści wynikające z zapobiegania zamówieniom produktów, których nie ma na stanie.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)
Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury
Moduł „Checkout stock checker PRO” (`csc`) został zaprojektowany tak, aby bezproblemowo integrować się z procesem realizacji zamówienia w PrestaShop. Działa głównie poprzez podłączenie się do końcowego etapu procesu składania zamówienia, wykorzystując kontroler frontowy do wykonania weryfikacji stanu magazynowego opartej na AJAX. Takie podejście zapewnia, że sprawdzenie stanu magazynowego jest wykonywane w czasie rzeczywistym tuż przed zatwierdzeniem zamówienia w bazie danych, zapobiegając warunkom wyścigu, w których stan magazynowy może się zmienić między przeglądem koszyka a ostatecznym potwierdzeniem zamówienia. Moduł przestrzega wzorca MVC PrestaShop dla interakcji z front-endem i konfiguracji.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office
-   `csc/controllers/front/AjaxCheck.php`
    *   **Nazwa klasy i klasa nadrzędna:** `CscAjaxCheckModuleFrontController` rozszerzająca `ModuleFrontController`.
    *   **Odpowiedzialność:** Ten kontroler jest rdzeniem funkcjonalności modułu. Jest odpowiedzialny za obsługę żądania AJAX inicjowanego ze strony realizacji zamówienia w front-office. Po otrzymaniu żądania, iteruje przez produkty w koszyku klienta, sprawdza ich aktualne poziomy zapasów w stosunku do żądanych ilości i zwraca odpowiedź JSON wskazującą, czy wszystkie produkty są dostępne, czy też które produkty są niedostępne. Nie renderuje pełnej strony, ale dostarcza dane, na podstawie których JavaScript może działać.
-   `csc/controllers/front/index.php`
    *   **Nazwa klasy i klasa nadrzędna:** Jest to standardowy pusty plik `index.php`, zazwyczaj dołączany do katalogów modułów PrestaShop, aby zapobiec bezpośredniemu listowaniu katalogów. Nie zawiera klasy ani specyficznej logiki.

#### Kontrolery administracyjne Back-Office
Moduł nie wykorzystuje żadnych niestandardowych kontrolerów administracyjnych. Jego konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)
Moduł nie definiuje żadnych niestandardowych klas `ObjectModel` ani dedykowanych klas logiki biznesowej w katalogu `classes/`. Cała podstawowa logika jest hermetyzowana w głównym pliku modułu (`ajax_csc.php`) i kontrolerze frontowym `AjaxCheck`.

### 4.4 Zasoby JavaScript (`views/js/`)
-   `csc/views/js/csc.js`
    *   **Zakres:** Front-office.
    *   **Szczegóły:** Ten plik JavaScript jest odpowiedzialny za inicjowanie sprawdzania stanu magazynowego za pomocą AJAX. Zazwyczaj podłącza się do zdarzenia kliknięcia końcowego przycisku „Złóż zamówienie” (lub równoważnego przesłania formularza) na stronie realizacji zamówienia. Przed zezwoleniem na przesłanie formularza, wysyła żądanie AJAX do kontrolera frontowego `AjaxCheck`. Na podstawie odpowiedzi JSON, albo pozwala na zakończenie realizacji zamówienia, albo zapobiega przesłaniu, przekierowuje użytkownika z powrotem do koszyka i wyświetla odpowiedni komunikat o błędzie. Wykorzystuje standardowy jQuery lub natywne zdarzenia JavaScript PrestaShop (`prestashop.on`) do osiągnięcia tego.

### 4.5 Arkusze stylów CSS (`views/css/`)
-   `csc/views/css/csc.css`
    *   **Zakres:** Stylizacja klienta front-office.
    *   **Szczegóły:** Ten arkusz stylów zapewnia podstawową stylizację komunikatów powiadomień wyświetlanych na stronie koszyka, gdy produkty okażą się niedostępne. Prawdopodobnie celuje w określone klasy CSS dodane do elementów `div` powiadomień.
    *   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Programiści mogą sprawdzić wyjście HTML komunikatu powiadomienia, aby zidentyfikować konkretne klasy (np. `.alert-danger`, `.csc-notification` itp.) i nadpisać je w pliku `custom.css` lub `theme.css` swojego motywu, aby dopasować je do brandingu swojego sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**: Brak wyraźnie wymienionych, co sugeruje, że główna interakcja modułu odbywa się za pośrednictwem AJAX i przekierowania, a powiadomienia są renderowane bezpośrednio przez kontroler `AjaxCheck` lub główny moduł.
-   **Szablony administracyjne (`views/templates/admin/`)**: Brak, ponieważ konfiguracja jest obsługiwana przez `getContent()`.
-   **Szablony front-office (`views/templates/front/`)**:
    *   `csc/lib/searchTool/views/scripts.tpl`
        *   **Cel:** Ten szablon prawdopodobnie zawiera plik JavaScript `csc.js` i potencjalnie przekazuje zmienne konfiguracyjne z zaplecza modułu do JavaScriptu front-endu. Prawdopodobnie jest podłączony do `displayHeader` lub `displayFooter`, aby zapewnić ładowanie JS na odpowiednich stronach (np. realizacji zamówienia).
    *   `csc/views/errors.tpl`
        *   **Cel:** Ten szablon jest renderowany, gdy sprawdzanie stanu magazynowego zakończy się niepowodzeniem (tj. produkty są niedostępne). Wyświetla komunikat o błędzie i listę konkretnych produktów, które są już niedostępne. Jest to szablon odpowiedzialny za widoczne powiadomienie na stronie koszyka po przekierowaniu.
    *   `csc/views/no-errors.tpl`
        *   **Cel:** Ten szablon jest prawdopodobnie miejscem zastępczym lub szablonem, który byłby renderowany, gdyby nie było błędów, ale główną funkcją modułu jest wyświetlanie błędów. Może być używany do wewnętrznej logiki lub po prostu być pustym szablonem.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Opiera się całkowicie na istniejących tabelach PrestaShop: `ps_product`, `ps_stock_available` i `ps_configuration`. Ustawienia konfiguracji (takie jak przełącznik włącz/wyłącz) są przechowywane w `ps_configuration` przy użyciu kluczy takich jak `CSC_ENABLED`.

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| :-------- | :--------------- | :--------------- |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` każdej strony. | Prawdopodobnie używany do dołączania skryptu `csc.js` i arkusza stylów `csc.css`, zapewniając ich dostępność na stronach realizacji zamówienia. |
| `displayFooter` | Renderuje zawartość na końcu sekcji `<body>` każdej strony. | Alternatywny hook do `displayHeader` do dołączania JS/CSS, często preferowany ze względu na wydajność. |
| `displayProductButtons` | Renderuje zawartość w pobliżu przycisków produktu (np. dodaj do koszyka). | *Nie jest wyraźnie używany do podstawowej funkcjonalności, ale może być używany do przyszłych funkcji lub drobnych elementów interfejsu użytkownika.* |
| `displayRightColumn` | Renderuje zawartość w prawej kolumnie sklepu. | *Nie jest wyraźnie używany do podstawowej funkcjonalności, ale może być używany do przyszłych funkcji lub drobnych elementów interfejsu użytkownika.* |
| `actionFrontControllerSetMedia` | Wykonywany, gdy kontroler frontowy ustawia swoje media (JS/CSS). | Bardziej ukierunkowany hook do dodawania JS/CSS specjalnie do odpowiednich kontrolerów frontowych (np. stron realizacji zamówienia). |
| `actionBeforeUpdateQuantity` | Wykonywany przed aktualizacją ilości produktu w koszyku. | *Nie jest wyraźnie używany do podstawowej funkcjonalności, ale może być używany do przyszłych funkcji lub drobnych elementów interfejsu użytkownika.* |
| `actionCartSave` | Wykonywany po zapisaniu koszyka. | *Nie jest wyraźnie używany do podstawowej funkcjonalności, ale może być używany do przyszłych funkcji lub drobnych elementów interfejsu użytkownika.* |
| `actionValidateOrder` | Wykonywany po zatwierdzeniu zamówienia. | *Kluczowy dla logiki modułu.* Jest to punkt, w którym moduł interweniuje, aby wykonać ostateczne sprawdzenie stanu magazynowego *przed* pełnym zatwierdzeniem zamówienia. JavaScript modułu prawdopodobnie zapobiega przesłaniu formularza, który wyzwala ten hook, jeśli zostaną znalezione problemy z dostępnością. |

*Uwaga: Główny mechanizm sprawdzania stanu magazynowego modułu odbywa się za pośrednictwem jego kontrolera frontowego `AjaxCheck`, który jest wyzwalany przez JavaScript na stronie realizacji zamówienia, a nie wyłącznie poprzez natywne hooki PrestaShop do samego sprawdzania stanu magazynowego. Hooki są używane głównie do ładowania zasobów i potencjalnie do wyświetlania powiadomień.*

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Checkout stock checker PRO”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
