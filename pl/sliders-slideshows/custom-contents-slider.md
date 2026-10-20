---
title: "Custom contents slider - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Custom contents slider od MyPresta.eu."
sidebar:
  label: "Custom contents slider - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Custom contents slider na MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/custom-contents-slider.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/sliders-slideshows/custom-contents-slider/)
>
> ---


# Custom contents slider

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony ustawień modułu „Custom contents slider”. Tutaj definiujesz zawartość, wygląd i zachowanie swoich suwaków.

Strona konfiguracji jest obsługiwana przez bibliotekę `SmartyTemplatesManager`, która umożliwia tworzenie i zarządzanie wieloma niestandardowymi blokami treści.

#### **Główny formularz (mainForm.tpl)**

Ta sekcja zawiera przegląd istniejących suwaków i umożliwia dodawanie nowych.

-   **Co robi ta sekcja:** Wyświetla listę wszystkich utworzonych niestandardowych suwaków treści. Każdy wpis pokazuje podstawowe informacje, takie jak nazwa suwaka, pozycja i status.
-   **Wpływ zmiany tej sekcji:** Stąd możesz szybko zobaczyć, które suwaki są aktywne i gdzie są wyświetlane. Możesz również kliknąć, aby edytować istniejące suwaki lub dodać nowe.
-   **Zalecane działanie:** Przejrzyj swoje istniejące suwaki. Jeśli konfigurujesz po raz pierwszy, będziesz chciał kliknąć przycisk „Dodaj nowy szablon”.

#### **Formularz tworzenia/edycji szablonu (createTemplateForm.tpl / editTemplateForm.tpl)**

Po kliknięciu „Dodaj nowy szablon” lub „Edytuj” istniejący suwak, zostaniesz przeniesiony do formularza, w którym zdefiniujesz wszystkie szczegóły dla tego konkretnego suwaka.

-   **Nazwa szablonu:**

    -   **Co robi to ustawienie:** Jest to wewnętrzna nazwa Twojego suwaka, widoczna tylko w panelu administracyjnym. Pomaga identyfikować różne suwaki.
    -   **Wpływ zmiany tego ustawienia:** Zmiana tego wpływa tylko na to, jak widzisz to w panelu administracyjnym; nie ma wpływu na front-office.
    -   **Zalecana wartość:** Opisowa nazwa, np. „Suwak letniej wyprzedaży lewy”, „Zapis do newslettera dolny”.
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli masz wiele promocji, jasne nazwanie ich pomaga w zarządzaniu nimi.
-   **Zawartość szablonu:**

    -   **Co robi to ustawienie:** To jest rdzeń Twojego suwaka. Możesz wprowadzić dowolny kod HTML, tekst, a nawet kod Smarty. Ta zawartość zostanie wyświetlona w panelu suwaka.
    -   **Wpływ zmiany tego ustawienia:** Bezpośrednio zmienia to, co widzą Twoi klienci, gdy suwak się rozszerza. Możesz dołączyć obrazy, linki, akapity, formularze itp.
    -   **Zalecana wartość:** Użyj standardowego HTML. Zachowaj zwięzłość i atrakcyjny wygląd. Dla obrazów użyj bezwzględnych adresów URL lub pomocnika obrazów PrestaShop.
    -   **Scenariusz/przykład dla sprzedawcy:**

        ```
        <h3>Oferta ograniczona czasowo!</h3><p>Otrzymaj <strong>15% ZNIŻKI</strong> na wszystkie produkty z kolekcji letniej!</p><a href="{$link->getPageLink('category', true, null, ['id\_category' => 123])}" class="button btn btn-primary">Kup teraz!</a>
        ```

        (Uwaga: Zmienne Smarty, takie jak `{$link->getPageLink(...)`, wymagają włączenia przetwarzania Smarty dla treści, co ten moduł obsługuje.)
-   **Pozycja:**

    -   **Co robi to ustawienie:** Określa, gdzie suwak pojawi się na ekranie klienta.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Lewo:* Suwak pojawia się z lewej krawędzi.
        -   *Prawo:* Suwak pojawia się z prawej krawędzi.
        -   *Dół:* Suwak pojawia się z dolnej krawędzi.
    -   **Zalecana wartość:** Wybierz na podstawie swojego projektu i innych elementów na stronie. Prawa i dolna strona są często mniej inwazyjne niż lewa.
    -   **Scenariusz/przykład dla sprzedawcy:** Użyj „Prawo” dla szybkiego formularza kontaktowego, „Dół” dla banera zgody na pliki cookie lub „Lewo” dla specjalnego kodu rabatowego.
-   **Otwórz na:**

    -   **Co robi to ustawienie:** Definiuje, jak suwak rozszerza się, aby pokazać swoją zawartość.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Kliknięcie:* Suwak rozszerza się tylko, gdy klient kliknie jego zakładkę wyzwalającą.
        -   *Najazd:* Suwak rozszerza się, gdy klient przesunie kursor myszy nad jego zakładkę wyzwalającą.
    -   **Zalecana wartość:** „Kliknięcie” jest zazwyczaj mniej inwazyjne i zapobiega przypadkowym otwarciom. „Najazd” może być dobry dla bardzo subtelnych, szybkich podglądów treści.
    -   **Scenariusz/przykład dla sprzedawcy:** Dla ważnych ogłoszeń lub formularzy lepsze jest „Kliknięcie”. Dla szybkiego przycisku czatu „Witaj, jak mogę pomóc?” może działać „Najazd”.
-   **Aktywny:**

    -   **Co robi to ustawienie:** Włącza lub wyłącza widoczność i aktywność tego konkretnego suwaka w Twoim front-office.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Włączony (Tak):* Suwak pojawi się w Twoim sklepie zgodnie z jego ustawieniami.
        -   *Wyłączony (Nie):* Suwak zostanie ukryty w Twoim sklepie, ale jego konfiguracja zostanie zapisana.
    -   **Zalecana wartość:** „Tak” dla aktywnych suwaków, „Nie” dla suwaków, które chcesz tymczasowo ukryć lub nad którymi nadal pracujesz.
    -   **Scenariusz/przykład dla sprzedawcy:** Możesz wyłączyć suwak promocji świątecznej po świętach, a następnie ponownie go włączyć w przyszłym roku.

#### **Menedżer przycisków (buttonManager.tpl)**

Ta sekcja jest częścią `SmartyTemplatesManager` i umożliwia zarządzanie przyciskami lub wyzwalaczami dla Twoich suwaków. Chociaż moduł głównie używa ustawienia „Otwórz na”, ta sekcja może oferować dodatkowe dostosowanie samego wizualnego wyzwalacza.

-   **Co robi ta sekcja:** Udostępnia opcje dostosowania wyglądu zakładki lub przycisku, z którym klienci wchodzą w interakcję, aby otworzyć suwak. Może to obejmować tekst, ikony lub podstawowe style.
-   **Wpływ zmiany tej sekcji:** Modyfikuje wizualny wygląd wyzwalacza suwaka w front-office.
-   **Zalecana wartość:** Zachowaj wyzwalacz jasny i zachęcający. Użyj zwięzłego tekstu lub odpowiedniej ikony.
-   **Scenariusz/przykład dla sprzedawcy:** Możesz ustawić tekst przycisku na „Wyprzedaż!”, „Skontaktuj się z nami” lub użyć małej ikony czatu.

#### **Wybór wejścia (selectInput.tpl)**

Jest to ogólny szablon dla rozwijanych list wyboru w `SmartyTemplatesManager`. Jest używany do ustawień takich jak „Pozycja” i „Otwórz na”.

-   **Co robi ta sekcja:** Przedstawia rozwijaną listę predefiniowanych opcji dla konkretnego ustawienia.
-   **Wpływ zmiany tej sekcji:** Umożliwia wybór z ograniczonego zestawu opcji dla danej konfiguracji.
-   **Zalecana wartość:** Wybierz opcję, która najlepiej pasuje do pożądanego zachowania suwaka.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Główny formularz | (Lista suwaków) | N/A | Przegląd wszystkich utworzonych suwaków; umożliwia dodawanie/edycję. |
| Tworzenie/Edycja szablonu | **Nazwa szablonu** | Opisowa nazwa | Wewnętrzny identyfikator suwaka w panelu administracyjnym. |
| Tworzenie/Edycja szablonu | **Zawartość szablonu** | Niestandardowy HTML/Tekst | Rzeczywista zawartość wyświetlana wewnątrz suwaka. |
| Tworzenie/Edycja szablonu | **Pozycja** | Prawo / Dół | Gdzie suwak pojawia się na ekranie (Lewo, Prawo, Dół). |
| Tworzenie/Edycja szablonu | **Otwórz na** | Kliknięcie | Jak suwak się rozszerza (Kliknięcie lub Najazd). |
| Tworzenie/Edycja szablonu | **Aktywny** | Tak | Włącza/wyłącza widoczność suwaka w front-office. |
| Menedżer przycisków | (Opcje przycisków) | N/A | Dostosowuje wizualny wyzwalacz suwaka (tekst, ikona, styl). |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P: Mój suwak nie wyświetla się w front-office. Co powinienem sprawdzić?**
O:

1.  **Czy suwak jest „Aktywny”?** Przejdź do konfiguracji modułu, edytuj swój suwak i upewnij się, że ustawienie „Aktywny” jest ustawione na „Tak”.
2.  **Czy zawartość jest prawidłowa?** Upewnij się, że w „Zawartości szablonu” nie ma niezamkniętych tagów HTML ani błędów JavaScript, które mogłyby zakłócić wyświetlanie.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym PrestaShop i wyczyść pamięć podręczną Smarty (i opcjonalnie całą pamięć podręczną).
4.  **Sprawdź konflikty:** Tymczasowo wyłącz inne moduły, które mogą dodawać pływające elementy lub modyfikować układ strony, aby sprawdzić, czy nie ma konfliktu.

**P: Suwak się pojawia, ale stylizacja wygląda źle lub nie pasuje do mojego motywu.**
O:

1.  **Domyślny CSS modułu:** Moduł ma swój własny CSS. CSS Twojego motywu może go nadpisywać lub odwrotnie.
2.  **Niestandardowa stylizacja motywu:** Może być konieczne dodanie niestandardowych reguł CSS do arkusza stylów Twojego motywu, aby dostosować wygląd suwaka. Użyj narzędzi deweloperskich przeglądarki (F12), aby zbadać elementy suwaka i zidentyfikować klasy CSS do celowania.
3.  **Stylizacja treści:** Jeśli umieszczasz surowy kod HTML w „Zawartości szablonu”, upewnij się, że używasz odpowiednich klas lub stylów wbudowanych, które działają z Twoim motywem.

**P: Czy mogę mieć wiele suwaków aktywnych jednocześnie?**
O: Tak, moduł obsługuje wiele suwaków. Pamiętaj jednak o doświadczeniu użytkownika. Zbyt wiele suwaków (np. jeden po lewej, jeden po prawej i jeden na dole) może zaśmiecać interfejs i przytłaczać klientów. Zazwyczaj najlepiej jest używać jednego lub dwóch strategicznie.

**P: Jak dodać obrazy lub linki do zawartości suwaka?**
O: Możesz użyć standardowych tagów HTML w polu „Zawartość szablonu”:

-   **Obrazy:** `<img src="adres_url_twojego_obrazu.jpg" alt="Opis" style="width:100px;">` (Użyj bezwzględnych adresów URL dla obrazów).
-   **Linki:** `<a href="adres_url_twojej_strony.html">Kliknij tutaj</a>` (Możesz również użyć zmiennych Smarty dla linków PrestaShop, np. `<a href="{$link->getPageLink('contact')}">Skontaktuj się z nami</a>`).

**P: Czy działa z wielojęzycznością i wielosklepowością?**
O: Tak, moduł jest zaprojektowany do poprawnego działania w środowiskach wielojęzycznych i wielosklepowych. Możesz tworzyć różne suwaki lub różne treści dla tego samego suwaka dla każdego języka i sklepu, co pozwala na bardzo ukierunkowane komunikaty.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Custom contents slider” (`saslider`) jest zbudowany jako standardowy moduł PrestaShop, wykorzystujący głównie klasę `Module` do zarządzania cyklem życia oraz `SmartyTemplatesManager` do dynamicznego tworzenia i zarządzania treścią. Integruje się z systemem hooków PrestaShop, aby wstrzykiwać swoje zasoby front-office i zawartość. Główna logika modułu znajduje się w jego głównym pliku `index.php`, obsługującym konfigurację, instalację i renderowanie front-office. Nie wykorzystuje dedykowanych kontrolerów front-office ani admina, lecz opiera się na metodzie `getContent()` dla konfiguracji back-office i bezpośredniej rejestracji hooków dla wyświetlania front-office.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Całe renderowanie front-office jest obsługiwane bezpośrednio za pośrednictwem zarejestrowanych hooków w głównym pliku modułu.
-   **Kontrolery Back-Office Admin**: Brak. Cała konfiguracja back-office jest zarządzana za pomocą metody `getContent()` głównej klasy modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

Moduł nie definiuje niestandardowych klas rozszerzających `ObjectModel`. Jego podstawowe przechowywanie danych dla konfiguracji suwaków jest prawdopodobnie obsługiwane za pomocą `Configuration::updateValue()` dla ustawień na poziomie modułu i potencjalnie serializowanych danych przechowywanych w `ps_configuration` dla indywidualnych treści i właściwości suwaków, zarządzanych przez bibliotekę `SmartyTemplatesManager`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł zawiera kilka plików JavaScript, głównie odpowiedzialnych za animację przesuwania i logikę interakcji (kliknięcie/najazd) dla różnych pozycji suwaka.

-   `saslider/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`

    -   **Zakres**: Back-office.
    -   **Odpowiedzialność**: Ten skrypt jest częścią biblioteki `SmartyTemplatesManager`. Prawdopodobnie obsługuje dynamiczne tworzenie, edycję i zarządzanie szablonami (suwakami) w interfejsie konfiguracji modułu. Może zarządzać przesyłaniem formularzy, wywołaniami AJAX do zapisywania/ładowania treści oraz interakcjami UI dla systemu zarządzania szablonami.
-   `saslider/views/js/saslider-click-bottom.js`

    -   **Zakres**: Front-office.
    -   **Odpowiedzialność**: Implementuje logikę JavaScript dla suwaka umieszczonego na dole, który rozszerza się/zwija po zdarzeniu kliknięcia. Będzie wiązać słuchaczy kliknięć z elementem wyzwalającym suwaka, przełączać klasy CSS lub bezpośrednio manipulować właściwościami `style`, aby animować rozszerzanie i zwijanie suwaka.
-   `saslider/views/js/saslider-click-left.js`

    -   **Zakres**: Front-office.
    -   **Odpowiedzialność**: Podobnie jak `saslider-click-bottom.js`, ale specjalnie dla suwaka umieszczonego po lewej stronie, obsługując jego rozszerzanie/zwijanie oparte na kliknięciu.
-   `saslider/views/js/saslider-click-right.js`

    -   **Zakres**: Front-office.
    -   **Odpowiedzialność**: Podobnie jak `saslider-click-bottom.js`, ale specjalnie dla suwaka umieszczonego po prawej stronie, obsługując jego rozszerzanie/zwijanie oparte na kliknięciu.
-   `saslider/views/js/saslider-hover-bottom.js`

    -   **Zakres**: Front-office.
    -   **Odpowiedzialność**: Implementuje logikę JavaScript dla suwaka umieszczonego na dole, który rozszerza się/zwija po zdarzeniu najechania kursorem. Będzie wiązać słuchaczy `mouseenter` i `mouseleave` z elementem wyzwalającym suwaka, przełączając jego widoczność i pozycję.
-   `saslider/views/js/saslider-hover-left.js`

    -   **Zakres**: Front-office.
    -   **Odpowiedzialność**: Podobnie jak `saslider-hover-bottom.js`, ale specjalnie dla suwaka umieszczonego po lewej stronie, obsługując jego rozszerzanie/zwijanie oparte na najechaniu kursorem.
-   `saslider/views/js/saslider-hover-right.js`

    -   **Zakres**: Front-office.
    -   **Odpowiedzialność**: Podobnie jak `saslider-hover-bottom.js`, ale specjalnie dla suwaka umieszczonego po prawej stronie, obsługując jego rozszerzanie/zwijanie oparte na najechaniu kursorem.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zawiera kilka plików CSS zarówno do stylizacji konfiguracji back-office, jak i wyglądu suwaka front-office.

-   `saslider/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`

    -   **Zakres**: Stylizacja formularza administracyjnego back-office.
    -   **Główne komponenty UI**: Stylizuje elementy interfejsu `SmartyTemplatesManager`, w tym formularze, przyciski, pola wejściowe i potencjalnie tabele list do zarządzania szablonami.
    -   **Kluczowe selektory klas CSS**: Prawdopodobnie zawiera klasy dla układów formularzy, grup wejściowych i ogólnych komponentów UI administracyjnych.
-   `saslider/views/css/saslider-bottom.css`

    -   **Zakres**: Stylizacja klienta front-office.
    -   **Główne komponenty UI**: Definiuje specyficzne pozycjonowanie, stan początkowy (zwinięty) i właściwości animacji dla suwaka umieszczonego na dole.
    -   **Kluczowe selektory klas CSS**: `body #saslider_bottom`, `.saslider-bottom-tab`, `.saslider-bottom-content`, klasy dla stanów `open`/`closed`.
-   `saslider/views/css/saslider-left.css`

    -   **Zakres**: Stylizacja klienta front-office.
    -   **Główne komponenty UI**: Definiuje specyficzne pozycjonowanie, stan początkowy i właściwości animacji dla suwaka umieszczonego po lewej stronie.
    -   **Kluczowe selektory klas CSS**: `body #saslider_left`, `.saslider-left-tab`, `.saslider-left-content`, klasy dla stanów `open`/`closed`.
-   `saslider/views/css/saslider-right.css`

    -   **Zakres**: Stylizacja klienta front-office.
    -   **Główne komponenty UI**: Definiuje specyficzne pozycjonowanie, stan początkowy i właściwości animacji dla suwaka umieszczonego po prawej stronie.
    -   **Kluczowe selektory klas CSS**: `body #saslider_right`, `.saslider-right-tab`, `.saslider-right-content`, klasy dla stanów `open`/`closed`.
-   `saslider/views/css/saslider.css`

    -   **Zakres**: Stylizacja klienta front-office.
    -   **Główne komponenty UI**: Zawiera ogólne, wspólne style mające zastosowanie do wszystkich pozycji suwaka, takie jak podstawowe style kontenera, rozmiary czcionek, kolory, z-index i właściwości przejścia.
    -   **Kluczowe selektory klas CSS**: `.saslider-container`, `.saslider-tab`, `.saslider-content` i potencjalnie dostosowania responsywne.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł wykorzystuje szablony Smarty zarówno dla interfejsu konfiguracji back-office, jak i renderowania treści front-office.

-   **Szablony administracyjne (`saslider/lib/smartyTemplatesManager/views/`)**:

    -   `buttonManager.tpl`: Prawdopodobnie renderuje interfejs użytkownika do zarządzania przyciskiem/zakładką wyzwalającą suwak.
    -   `createTemplateForm.tpl`: Szablon formularza używany podczas tworzenia nowego suwaka.
    -   `editTemplateForm.tpl`: Szablon formularza używany podczas edycji istniejącego suwaka.
    -   `mainForm.tpl`: Główny szablon strony konfiguracji, prawdopodobnie wyświetlający listę wszystkich suwaków i zawierający przycisk „Dodaj nowy”.
    -   `selectInput.tpl`: Szablon wielokrotnego użytku do renderowania rozwijanych elementów `<select>` w formularzach administracyjnych.
-   **Szablony hooków (`saslider/views/`)**:

    -   `footer-bottom.tpl`: Renderuje strukturę HTML dla suwaka umieszczonego na dole. Ten szablon jest prawdopodobnie podłączony do `displayFooter` lub podobnego globalnego hooka. Zawiera otaczające `div`y dla suwaka, jego zakładki wyzwalającej i obszaru treści.
    -   `footer-left.tpl`: Renderuje strukturę HTML dla suwaka umieszczonego po lewej stronie. Prawdopodobnie podłączony do `displayFooter` lub podobnego.
    -   `footer-right.tpl`: Renderuje strukturę HTML dla suwaka umieszczonego po prawej stronie. Prawdopodobnie podłączony do `displayFooter` lub podobnego.
-   **Przykładowe/narzędziowe szablony (`saslider/lib/smartyTemplatesManager/tpl/`)**:

    -   `example.tpl`: Przykładowy szablon, prawdopodobnie do demonstracji lub wewnętrznego testowania `SmartyTemplatesManager`.
    -   `MyShortCode.tpl`: Sugeruje, że `SmartyTemplatesManager` może obsługiwać jakąś formę shortcode'u lub dynamicznego wstawiania treści.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie definiuje jawnie niestandardowych tabel SQL za pomocą `install.sql`.
    -   Konfiguracja dla poszczególnych suwaków (treść, pozycja, status aktywności, otwórz na) jest przechowywana w tabeli `ps_configuration`, prawdopodobnie jako serializowane dane pod określonymi kluczami konfiguracyjnymi zarządzanymi przez bibliotekę `SmartyTemplatesManager`. Na przykład `PS_SASLIDER_TEMPLATES` lub podobne.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Używany do rejestrowania zasobów CSS i JavaScript (np. `saslider.css`, `saslider-click-right.js`) wymaganych do wyświetlania i funkcjonalności suwaka w front-office. |
| `displayFooter` | Na końcu sekcji `<body>` każdej strony, przed zamykającym tagiem `</body>`. | Używany do renderowania rzeczywistej struktury HTML suwaka (np. `footer-bottom.tpl`, `footer-left.tpl`, `footer-right.tpl`) na stronie, zapewniając jego prawidłowe pływanie. |
| `displayLeftColumn` | W lewej kolumnie sklepu. | *Potencjalnie* używany do renderowania suwaka, chociaż `displayFooter` jest bardziej powszechny dla elementów pływających. |
| `displayRightColumn` | W prawej kolumnie sklepu. | *Potencjalnie* używany do renderowania suwaka, chociaż `displayFooter` jest bardziej powszechny dla elementów pływających. |
| `displayProductAdditionalInfo` | Na stronie produktu, poniżej głównych informacji o produkcie. | *Potencjalnie* używany do renderowania suwaka specjalnie na stronach produktów, np. dla powiązanych ofert. |
| `actionFrontControllerSetMedia` | Po tym, jak kontroler front-office ustawi swoje media, umożliwiając modułom dodawanie własnych. | Używany do warunkowego dodawania plików CSS/JS na podstawie bieżącej strony lub innych warunków, zapewniając optymalne ładowanie. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Custom contents slider”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnianie terminowej pomocy i dbanie o to, aby Twój moduł działał płynnie z Twoim sklepem PrestaShop.
