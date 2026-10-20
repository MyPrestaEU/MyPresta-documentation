---
title: "CMS na stronie głównej - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „CMS na stronie głównej” od MyPresta.eu."
sidebar:
  label: "CMS na stronie głównej - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł CMS on homepage na MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-on-homepage.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/cms-on-homepage/)
>
> ---


# CMS na stronie głównej

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5 (Zawsze rozszerzane do PHP 8.5)
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop, a ten moduł nie ma żadnych dodatkowych specjalnych wymagań.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „CMS na stronie głównej”. Zostaniesz przeniesiony do jego głównego ekranu konfiguracji.

#### Wybierz stronę CMS

Jest to główne ustawienie modułu. Pozwala ono wybrać, która z Twoich istniejących stron CMS będzie miała swoją zawartość wyświetlaną na stronie głównej.

-   **Co robi to ustawienie:** Ta rozwijana lista zawiera wszystkie strony CMS, które utworzyłeś w swoim sklepie PrestaShop (znajdujące się w **Parametry sklepu > Strony**). Wybierasz jedną z tych stron.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy strona CMS jest wybrana:* Zawartość wybranej strony CMS zostanie pobrana i wyświetlona na stronie głównej Twojego sklepu.
    -   *Gdy żadna strona CMS nie jest wybrana (lub jeśli zmienisz zdanie):* Moduł nie wyświetli żadnej zawartości lub wyświetli zawartość nowo wybranej strony.
-   **Zalecana wartość:** Wybierz stronę CMS, której zawartość chcesz wyróżnić na swojej stronie głównej. Może to być strona „O nas”, „Informacje o wysyłce”, „Polityka prywatności” (jeśli chcesz, aby była bardzo widoczna) lub niestandardowa strona z treściami promocyjnymi.
-   **Scenariusz / przykład dla sprzedawcy:** Masz stronę CMS zatytułowaną „Nasza historia”, która szczegółowo opisuje historię i wartości Twojej marki. Wybierając tutaj „Nasza historia”, każdy odwiedzający Twoją stronę główną natychmiast zobaczy tę treść, co pomoże w budowaniu więzi z marką i zaufania.

Po dokonaniu wyboru pamiętaj, aby kliknąć przycisk **„Zapisz”**, aby zastosować zmiany.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Wybierz stronę CMS | (Początkowo brak wyboru) | Wybierz, której strony CMS zawartość pojawi się na stronie głównej. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Wybrałem stronę CMS, ale nic nie wyświetla się na mojej stronie głównej. Co jest nie tak?**
O:

1.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami PrestaShop potrzebuje odświeżenia pamięci podręcznej, aby wyświetlić nową zawartość.
2.  **Sprawdź status strony CMS:** Upewnij się, że wybrana strona CMS jest aktywna i widoczna w Twoim sklepie (przejdź do **Parametry sklepu > Strony** i sprawdź jej status).
3.  **Kompatybilność z szablonem:** Chociaż moduł używa standardowych haków PrestaShop, niektóre wysoce spersonalizowane szablony mogą nadpisywać te haki lub mieć specyficzne wymagania dotyczące układu. Jeśli wyczyszczenie pamięci podręcznej nie pomoże, skontaktuj się z twórcą szablonu lub wsparciem MyPresta.eu.

**P: Treść CMS wyświetla się, ale nie wygląda prawidłowo (np. złe czcionki, kolory, układ).**
O: Moduł po prostu wstrzykuje zawartość Twojej strony CMS. Stylizacja (czcionki, kolory, odstępy) jest zazwyczaj kontrolowana przez CSS Twojego szablonu PrestaShop.

1.  **Sprawdź zawartość strony CMS:** Upewnij się, że w samej treści strony CMS nie ma niestandardowego, konfliktowego kodu HTML lub stylów inline, które mogłyby powodować problemy.
2.  **Dostosowanie szablonu:** Może być konieczne dodanie niestandardowego CSS do Twojego szablonu, aby lepiej zintegrować wizualnie treść CMS. Deweloper stron internetowych może w tym pomóc.

**P: Czy mogę wyświetlić wiele stron CMS na stronie głównej?**
O: Ten konkretny moduł jest przeznaczony do wyświetlania *jednej* wybranej strony CMS. Jeśli potrzebujesz wyświetlić wiele odrębnych bloków treści CMS, musiałbyś je połączyć w jedną stronę CMS lub poszukać bardziej zaawansowanego modułu do zarządzania treścią.

**P: Jak przetłumaczyć treść CMS na różne języki?**
O: Treść Twojej strony CMS jest zarządzana bezpośrednio w ramach podstawowej funkcjonalności CMS PrestaShop. Podczas edycji strony CMS (**Parametry sklepu > Strony**) możesz wybrać język, w którym chcesz edytować jej zawartość. Moduł automatycznie wyświetli zawartość w języku aktualnie wybranym przez klienta w Twoim sklepie.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „CMS na stronie głównej” to lekki moduł PrestaShop, zaprojektowany przede wszystkim do wstrzykiwania istniejącej zawartości stron CMS do różnych haków strony głównej. Przestrzega standardowej struktury modułu PrestaShop, wykorzystując klasę `Module` oraz jej metody `install()` i `uninstall()` do konfiguracji i czyszczenia, a także `getContent()` do konfiguracji panelu administracyjnego. Wyświetlanie w panelu klienta jest w całości obsługiwane poprzez rejestrację haków i szablony Smarty. Nie wprowadza niestandardowych kontrolerów, modeli ani złożonego JavaScriptu.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery panelu klienta**: Brak. Całe renderowanie treści panelu klienta jest obsługiwane bezpośrednio za pomocą zarejestrowanych haków w głównym pliku modułu.
-   **Kontrolery panelu administracyjnego**: Brak. Konfiguracja modułu jest zarządzana za pomocą metody `getContent()` głównej klasy modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

-   Brak. Moduł opiera się na podstawowych klasach PrestaShop `CMS` i `Configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   Brak. Moduł nie zawiera żadnego niestandardowego JavaScriptu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   Brak. Moduł nie zawiera żadnego niestandardowego CSS. Wyświetlana zawartość CMS dziedziczy stylizację z aktywnego szablonu PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`cmshomepage/views/templates/hook/cmshomepage.tpl`**

    -   **Cel:** Jest to główny szablon odpowiedzialny za renderowanie rzeczywistej zawartości wybranej strony CMS. Jest zaprojektowany do podłączenia do `displayHome` lub `displayHomeTabContent` w celu bezpośredniego wyświetlania treści.
    -   **Zmienne:**
        -   `{$cms_content}`: Zawartość HTML wybranej strony CMS, pobrana i przypisana przez moduł.
    -   **Wyjście:** Renderuje surową zawartość HTML strony CMS.
-   **`cmshomepage/views/templates/hook/tab.tpl`**

    -   **Cel:** Ten szablon jest używany, gdy moduł jest podłączony do `displayHomeTab`. Generuje kod HTML dla nagłówka zakładki, który po kliknięciu ujawnia zawartość CMS.
    -   **Zmienne:**
        -   `{$tab_name}`: Tytuł zakładki, zazwyczaj pochodzący z tytułu strony CMS.
        -   `{$tab_id}`: Unikalny identyfikator zakładki, używany do powiązania jej z odpowiadającym panelem treści.
    -   **Wyjście:** Element `<li>` zawierający tag `<a>`, odpowiedni do włączenia w strukturę nawigacji zakładek.
-   **`cmshomepage/views/templates/hook/tabContents.tpl`**

    -   **Cel:** Ten szablon jest używany, gdy moduł jest podłączony do `displayHomeTabContent`. Generuje kod HTML dla panelu treści powiązanego z zakładką.
    -   **Zmienne:**
        -   `{$tab_id}`: Unikalny identyfikator pasujący do identyfikatora z `tab.tpl`.
        -   `{$cms_content}`: Zawartość HTML wybranej strony CMS.
    -   **Wyjście:** Element `<div>` z zawartością zakładki, zazwyczaj domyślnie ukryty i ujawniany za pomocą JavaScript po kliknięciu odpowiadającej mu zakładki.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    -   Przechowuje swoją konfigurację w tabeli `ps_configuration` używając klucza `CMSHOMEPAGE_ID_CMS` do przechowywania ID wybranej strony CMS.
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHomeTabContent` | Renderuje zawartość w zakładce strony głównej. | Wyświetla `cmshomepage.tpl` lub `tabContents.tpl` z zawartością CMS. |
| `displayHomeTab` | Renderuje nagłówek zakładki na stronie głównej. | Wyświetla `tab.tpl` z tytułem strony CMS jako nazwą zakładki. |
| `displayHome` | Renderuje zawartość bezpośrednio w głównym obszarze strony głównej. | Wyświetla `cmshomepage.tpl` z zawartością CMS. |

Metoda `install()` modułu rejestruje te haki. Metody `hookDisplayHome()`, `hookDisplayHomeTab()` i `hookDisplayHomeTabContent()` w `cmshomepage.php` są odpowiedzialne za pobieranie wybranej zawartości strony CMS i renderowanie odpowiedniego szablonu.

### 4.8 Klucze konfiguracji

Moduł używa następujących kluczy konfiguracji w `ps_configuration`:

-   `CMSHOMEPAGE_ID_CMS`: Przechowuje `id_cms` strony CMS wybranej przez sprzedawcę do wyświetlenia na stronie głównej.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, poprawek błędów i dedykowanego wsparcia deweloperskiego, prosimy odwołać się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu/). Upewnij się, że używasz najnowszej wersji modułu, aby zapewnić optymalną wydajność i kompatybilność z Twoim sklepem PrestaShop.
