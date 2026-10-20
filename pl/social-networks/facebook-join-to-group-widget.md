---
title: "Widget dołączania do grupy na Facebooku - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla deweloperów modułu PrestaShop „Widget dołączania do grupy na Facebooku” od MyPresta.eu."
sidebar:
  label: "Widget dołączania do grupy na Facebooku - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook join to group widget na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-join-to-group-widget.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-join-to-group-widget/)
>
> ---


# Widget dołączania do grupy na Facebooku

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran, na którym ustawisz wszystkie opcje dla swojego widgetu dołączania do grupy na Facebooku.

- **Nazwa ekranu i lokalizacja w menu:** Panel administracyjny > Moduły > Menedżer modułów > „Widget dołączania do grupy na Facebooku” > Konfiguruj

#### Ustawienia i opcje:

1.  **URL grupy** (Klucz konfiguracji: `fbg_href`)

    - **Co robi to ustawienie:** Jest to najważniejsze ustawienie. Definiuje bezpośredni link do Twojej Grupy na Facebooku. Gdy klienci klikną przycisk „Dołącz do grupy”, zostaną przekierowani na ten URL.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy ustawiony na prawidłowy URL Grupy na Facebooku:* Przycisk „Dołącz do grupy” prawidłowo przekieruje użytkowników do Twojej określonej grupy.
      - *Gdy pozostawiony pusty lub ustawiony na nieprawidłowy URL:* Przycisk może nie działać lub może prowadzić do strony błędu, frustrując Twoich klientów.
    - **Zalecana wartość:** Zawsze podawaj pełny i prawidłowy URL do Twojej Grupy na Facebooku (np. `https://www.facebook.com/groups/nazwagrupy/`).
    - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby klienci dołączyli do Twojej grupy „Społeczność Mojego Niesamowitego Sklepu”. Wkleiłbyś tutaj `https://www.facebook.com/groups/spolecznoscmojegoniesamowitegosklepu/`.
2.  **Szerokość pola** (Klucz konfiguracji: `fbg_width`)

    - **Co robi to ustawienie:** Kontroluje szerokość pola widgetu dołączania do grupy na Facebooku w Twoim sklepie. Możesz określić to w pikselach.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy ustawiony na konkretną wartość w pikselach (np. `280`):* Pole spróbuje renderować się z dokładnie taką szerokością.
      - *Gdy pozostawiony pusty lub ustawiony na `0`:* Moduł spróbuje automatycznie dostosować swoją szerokość w oparciu o dostępną przestrzeń w hooku, w którym jest wyświetlany, lub użyje wartości domyślnej.
    - **Zalecana wartość:** Zacznij od `280` lub `300` pikseli. Testuj na różnych urządzeniach. Jeśli chcesz, aby wypełniał dostępną przestrzeń w kolumnie, możesz pozostawić go pustym, ale pamiętaj, że może rozciągnąć się zbyt szeroko w niektórych hookach.
    - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby widget ładnie pasował do Twojej lewej kolumny, która ma 250px szerokości. Ustawisz to na `250`.
3.  **Gdzie chcesz wyświetlić pole?** (Klucz konfiguracji: `fbg_hook`)

    - **Co robi to ustawienie:** Ta lista rozwijana pozwala wybrać konkretną lokalizację (hook PrestaShop), w której widget pojawi się w Twoim sklepie.
    - **Efekt zmiany tego ustawienia:**
      - *Wybranie `DisplayFooter`:* Widget pojawi się na dole każdej strony.
      - *Wybranie `DisplayHome`:* Widget pojawi się tylko na Twojej stronie głównej.
      - *Wybranie `DisplayRightColumn`:* Widget pojawi się w prawym pasku bocznym na stronach, które go posiadają.
      - *Wybranie dowolnego innego hooka:* Widget pojawi się w tej konkretnej lokalizacji.
    - **Zalecana wartość:** Zależy to całkowicie od Twojego motywu i strategii marketingowej. `DisplayRightColumn` lub `DisplayLeftColumn` są powszechne dla widgetów bocznych. `DisplayFooter` jest dobry dla mniej inwazyjnego umiejscowienia. `DisplayHome` jest świetny dla wysokiej widoczności.
    - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby widget był widoczny na większości stron, ale nie kolidował z główną treścią. Wybierasz `DisplayRightColumn`.
4.  **Nagłówek** (Klucz konfiguracji: `fbg_header`)

    - **Co robi to ustawienie:** Jest to główny tekst tytułu wyświetlany na górze Twojego widgetu dołączania do grupy na Facebooku.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy ustawiony na „Dołącz do naszej społeczności”:* Ten tekst zostanie wyraźnie wyświetlony.
      - *Gdy pozostawiony pusty:* Nie zostanie wyświetlony żaden tekst nagłówka, co sprawi, że widget będzie mniej czytelny dla klientów.
    - **Zalecana wartość:** Jasny, zachęcający tytuł, taki jak „Dołącz do naszej grupy na Facebooku”, „Nasza społeczność” lub „Połącz się z nami”.
    - **Scenariusz / przykład dla sprzedawcy:** Chcesz jasno powiedzieć klientom, o czym jest to pole. Ustawiasz to na „Dołącz do naszej ekskluzywnej grupy na Facebooku!”.
5.  **Opis** (Klucz konfiguracji: `fbg_desc`)

    - **Co robi to ustawienie:** Zapewnia krótki tekst wyjaśniający pod nagłówkiem, dając klientom więcej kontekstu na temat Twojej Grupy na Facebooku.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy ustawiony na „Otrzymuj ekskluzywne oferty i aktualizacje!”:* Ta wiadomość pojawi się pod nagłówkiem.
      - *Gdy pozostawiony pusty:* Widget wyświetli tylko nagłówek i przycisk, potencjalnie tracąc okazję do zachęcenia użytkowników.
    - **Zalecana wartość:** Krótkie, przekonujące zdanie lub dwa wyjaśniające korzyści z dołączenia (np. „Bądź pierwszym, który dowie się o nowych produktach i specjalnych ofertach!”).
    - **Scenariusz / przykład dla sprzedawcy:** Chcesz zachęcić do rejestracji, podkreślając korzyści. Ustawiasz to na „Uzyskaj dostęp do zniżek tylko dla członków, zapowiedzi i połącz się z innymi entuzjastami!”.
6.  **Tekst przycisku** (Klucz konfiguracji: `fbg_btn_text`)

    - **Co robi to ustawienie:** Jest to tekst wyświetlany na przycisku, który klienci klikają, aby dołączyć do Twojej grupy.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy ustawiony na „Dołącz do grupy”:* Ten tekst pojawi się na przycisku.
      - *Gdy pozostawiony pusty:* Przycisk może pojawić się pusty lub użyć wartości domyślnej, co jest mniej skuteczne.
    - **Zalecana wartość:** Jasne wezwanie do działania, takie jak „Dołącz do grupy”, „Dołącz teraz” lub „Połącz się na Facebooku”.
    - **Scenariusz / przykład dla sprzedawcy:** Chcesz bezpośredniego wezwania do działania. Ustawiasz to na „Dołącz do naszej grupy”.
7.  **Kolor tekstu** (Klucz konfiguracji: `fbg_text_color`)

    - **Co robi to ustawienie:** Pozwala ustawić kolor tekstu nagłówka i opisu w widżecie.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy ustawiony na `#000000` (czarny):* Tekst pojawi się czarny.
      - *Gdy ustawiony na `#FFFFFF` (biały):* Tekst pojawi się biały.
    - **Zalecana wartość:** Wybierz kolor, który dobrze kontrastuje z wybranym kolorem tła i pasuje do palety kolorów Twojej marki. Użyj kodu szesnastkowego (np. `#333333`).
    - **Scenariusz / przykład dla sprzedawcy:** Twój widget ma ciemne tło. Ustawiasz kolor tekstu na `#FFFFFF` dla czytelności.
8.  **Styl obramowania** (Klucz konfiguracji: `fbg_border_style`)

    - **Co robi to ustawienie:** Definiuje styl wizualny obramowania wokół pola widgetu.
    - **Efekt zmiany tego ustawienia:**
      - *`solid`:* Pojedyncza, ciągła linia.
      - *`dashed`:* Seria krótkich linii.
      - *`dotted`:* Seria kropek.
      - *`none`:* Nie zostanie wyświetlone żadne obramowanie.
    - **Zalecana wartość:** `solid` lub `none` są najczęstsze. `solid` zapewnia wyraźną granicę.
    - **Scenariusz / przykład dla sprzedawcy:** Chcesz subtelnego obrysu dla pola. Wybierasz `solid`.
9.  **Kolor obramowania** (Klucz konfiguracji: `fbg_border_color`)

    - **Co robi to ustawienie:** Ustawia kolor obramowania wokół pola widgetu.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy ustawiony na `#CCCCCC` (jasnoszary):* Obramowanie będzie jasnoszare.
      - *Gdy ustawiony na `#FF0000` (czerwony):* Obramowanie będzie czerwone.
    - **Zalecana wartość:** Kolor, który uzupełnia projekt Twojego sklepu, często subtelny szary lub akcentujący kolor marki. Użyj kodu szesnastkowego.
    - **Scenariusz / przykład dla sprzedawcy:** Twoja marka używa specyficznego odcienia niebieskiego. Ustawiasz kolor obramowania na `#007bff`.
10. **Rozmiar obramowania** (Klucz konfiguracji: `fbg_border_size`)

    - **Co robi to ustawienie:** Określa grubość obramowania w pikselach.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy ustawiony na `1`:* Pojawi się cienkie obramowanie.
      - *Gdy ustawiony na `5`:* Pojawi się grubsze, bardziej widoczne obramowanie.
    - **Zalecana wartość:** `1` lub `2` piksele dla subtelnego obramowania.
    - **Scenariusz / przykład dla sprzedawcy:** Chcesz bardzo cienkiego obramowania. Ustawiasz rozmiar na `1`.
11. **Promień obramowania** (Klucz konfiguracji: `fbg_border_radius`)

    - **Co robi to ustawienie:** Kontroluje zaokrąglenie rogów pola widgetu. Wyższa wartość tworzy bardziej zaokrąglone rogi.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy ustawiony na `0`:* Pole będzie miało ostre, kwadratowe rogi.
      - *Gdy ustawiony na `10`:* Rogi będą zauważalnie zaokrąglone.
    - **Zalecana wartość:** `0` dla ostrych rogów, `3` do `5` dla lekko zaokrąglonych lub `10+` dla bardzo zaokrąglonych, w zależności od estetyki Twojego motywu.
    - **Scenariusz / przykład dla sprzedawcy:** Twój motyw używa lekko zaokrąglonych elementów. Ustawiasz promień obramowania na `5`.
12. **Kolor tła** (Klucz konfiguracji: `fbg_bg_color`)

    - **Co robi to ustawienie:** Ustawia główny kolor tła pola widgetu.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy ustawiony na `#F0F2F5` (jasnoszary, podobny do tła Facebooka):* Tło pola będzie jasnoszare.
      - *Gdy ustawiony na `#FFFFFF` (biały):* Tło pola będzie białe.
    - **Zalecana wartość:** Kolor, który sprawia, że tekst jest czytelny i pasuje do projektu Twojego sklepu. Użyj kodu szesnastkowego.
    - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby widget lekko wyróżniał się na białym tle strony. Ustawiasz kolor tła na `#F8F8F8`.
13. **Gradient tła** (Klucz konfiguracji: `fbg_bg_gradient`)

    - **Co robi to ustawienie:** Pozwala dodać gradient CSS do tła pola widgetu, tworząc płynne przejście między dwoma lub więcej kolorami. To zastępuje pojedynczy „Kolor tła”, jeśli jest używany.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy ustawiony na `linear-gradient(to right, #FFD700, #FFA500)`:* Tło przejdzie od złotego do pomarańczowego.
      - *Gdy pozostawiony pusty:* Zamiast tego zostanie użyte ustawienie „Kolor tła”.
    - **Zalecana wartość:** Użyj ciągu gradientu CSS, jeśli chcesz bardziej dynamicznego tła. Jeśli nie jesteś pewien, pozostaw to puste i użyj pojedynczego „Koloru tła”.
    - **Scenariusz / przykład dla sprzedawcy:** Chcesz subtelnego, nowoczesnego wyglądu. Używasz gradientu, takiego jak `linear-gradient(to bottom, #e0eafc, #cfdef3)`.

#### Ukryte/wewnętrzne ustawienia (do celów referencyjnych dla deweloperów, niekonfigurowalne bezpośrednio przez sprzedawcę):

- `mypresta_updates`, `update_`, `updatev_`: Wewnętrzne klucze do aktualizacji modułów i sprawdzania wersji.
- `fbg_app`, `fbg_appid`: Te klucze sugerują potencjał integracji z aplikacją Facebooka, ale nie są dostępne w bieżącej konfiguracji.
- `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Podstawowe ustawienia PrestaShop związane z obsługą języków w panelu administracyjnym.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **URL grupy** | URL Twojej Grupy na Facebooku | Bezpośredni link do Twojej Grupy na Facebooku dla przycisku „Dołącz do grupy”. **KRYTYCZNE!** |
| Konfiguracja modułu | **Szerokość pola** | `280` lub `300`px | Ustawia szerokość pola widgetu. Pozostaw puste dla automatycznego dostosowania. |
| Konfiguracja modułu | **Gdzie chcesz wyświetlić pole?** | `DisplayRightColumn` lub `DisplayFooter` | Wybiera hook PrestaShop, w którym pojawi się widget. |
| Konfiguracja modułu | **Nagłówek** | „Dołącz do naszej grupy na Facebooku” | Główny tekst tytułu dla widgetu. |
| Konfiguracja modułu | **Opis** | „Otrzymuj ekskluzywne oferty i aktualizacje!” | Krótki tekst wyjaśniający pod nagłówkiem. |
| Konfiguracja modułu | **Tekst przycisku** | „Dołącz do grupy” | Tekst wyświetlany na przycisku akcji. |
| Konfiguracja modułu | **Kolor tekstu** | `#333333` (ciemnoszary) | Kolor tekstu nagłówka i opisu. Użyj kodu szesnastkowego. |
| Konfiguracja modułu | **Styl obramowania** | `solid` lub `none` | Styl wizualny obramowania pola (solidny, przerywany, kropkowany, brak). |
| Konfiguracja modułu | **Kolor obramowania** | `#CCCCCC` (jasnoszary) | Kolor obramowania pola. Użyj kodu szesnastkowego. |
| Konfiguracja modułu | **Rozmiar obramowania** | `1` lub `2`px | Grubość obramowania pola. |
| Konfiguracja modułu | **Promień obramowania** | `0` lub `5`px | Zaokrąglenie rogów pola. |
| Konfiguracja modułu | **Kolor tła** | `#F0F2F5` (jasnoszary) | Główny kolor tła pola widgetu. Użyj kodu szesnastkowego. |
| Konfiguracja modułu | **Gradient tła** | Pozostaw puste | Gradient CSS dla tła. Zastępuje `Kolor tła`, jeśli ustawiony. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

1.  **Widget nie wyświetla się w moim sklepie.**

    - **Sprawdź 1:** Przejdź do **Moduły > Menedżer modułów**, wyszukaj „Widget dołączania do grupy na Facebooku” i upewnij się, że jest zainstalowany i włączony.
    - **Sprawdź 2:** W konfiguracji modułu sprawdź, czy wybrałeś „Gdzie chcesz wyświetlić pole?” (hook). Upewnij się, że wybrany hook faktycznie istnieje i jest aktywny w Twoim obecnym motywie. Niektóre motywy mogą nie używać wszystkich standardowych hooków PrestaShop.
    - **Sprawdź 3:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**). Czasami zmiany nie pojawiają się, dopóki pamięć podręczna nie zostanie odświeżona.
    - **Sprawdź 4:** Jeśli masz niestandardowy motyw, może on nadpisywać standardowe wyświetlanie hooków. Skontaktuj się z deweloperem motywu lub webmasterem.
2.  **Przycisk „Dołącz do grupy” nie działa lub prowadzi do błędu.**

    - **Sprawdź:** Przejdź do konfiguracji modułu i ostrożnie ponownie wprowadź swój „URL grupy”. Upewnij się, że jest to kompletny i prawidłowy URL do Twojej Grupy na Facebooku (np. `https://www.facebook.com/groups/nazwagrupy/`). Przetestuj URL bezpośrednio w przeglądarce, aby potwierdzić, że działa.
3.  **Widget wygląda dziwnie lub nie pasuje do projektu mojego motywu.**

    - **Sprawdź 1:** Dostosuj ustawienie „Szerokość pola”. Jeśli jest zbyt szerokie dla kolumny, może zepsuć układ. Spróbuj mniejszej wartości w pikselach.
    - **Sprawdź 2:** Użyj ustawień „Kolor tekstu”, „Styl obramowania”, „Kolor obramowania”, „Rozmiar obramowania”, „Promień obramowania”, „Kolor tła” i „Gradient tła”, aby dopasować je do kolorów i stylów Twojego motywu.
    - **Sprawdź 3:** Wyczyść pamięć podręczną PrestaShop po wprowadzeniu zmian stylistycznych.
    - **Sprawdź 4:** Jeśli problem nadal występuje, może to być konflikt CSS z Twoim motywem. Webmaster może sprawdzić CSS Twojej witryny, aby zidentyfikować i rozwiązać konflikty.
4.  **Czy mogę wyświetlić widget w wielu miejscach?**

    - Obecna wersja modułu pozwala wybrać tylko jeden hook z listy rozwijanej. Jeśli chcesz wyświetlić go w wielu miejscach, musiałbyś zduplikować moduł (co wymaga interwencji dewelopera) lub użyć niestandardowego rozwiązania.
5.  **Mój tekst nie wyświetla się w prawidłowym języku.**

    - Pola „Nagłówek”, „Opis” i „Tekst przycisku” są zazwyczaj tłumaczone, jeśli Twoja instalacja PrestaShop obsługuje wiele języków dla konfiguracji modułów. Upewnij się, że edytujesz konfigurację modułu w prawidłowym kontekście językowym w Panelu administracyjnym (sprawdź listę rozwijaną języków w prawym górnym rogu panelu administracyjnego).

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Widget dołączania do grupy na Facebooku” to prosty moduł PrestaShop, który stosuje podstawowy wzorzec podobny do MVC, właściwy dla struktury modułów PrestaShop. Wykorzystuje głównie klasę `Module` do swojej podstawowej funkcjonalności, zarządzania konfiguracją i rejestracji hooków. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu, przechowując ustawienia w `ps_configuration`. Wyświetlanie w front-office jest zarządzane za pomocą szablonów Smarty renderowanych za pośrednictwem zarejestrowanych hooków. Nie ma niestandardowych kontrolerów ani ObjectModels.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Całe renderowanie front-office jest obsługiwane bezpośrednio za pomocą metod `hook` w głównym pliku modułu `fbgroup.php`, które następnie renderują szablony Smarty.
- **Kontrolery Back-Office Admin**: Brak. Cała administracja jest obsługiwana za pomocą metody `getContent()` głównej klasy modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

- **`fbgroup/fbgroup.php` (Główna klasa modułu)**
  - **Nazwa klasy:** `Fbgroup`
  - **Klasa nadrzędna:** `Module`
  - **Odpowiedzialność:**
    - Instalacja (`install()`) i deinstalacja (`uninstall()`) modułu.
    - Rejestracja wszystkich określonych hooków (`registerHook()`).
    - Zarządzanie ustawieniami konfiguracji modułu za pomocą metody `getContent()`, która obsługuje przesyłanie formularzy i aktualizuje tabelę `ps_configuration`.
    - Implementacja różnych metod `hook` (np. `hookDisplayHeader`, `hookDisplayFooter`, `hookDisplayHome` itp.) do renderowania widgetu w front-office.
    - Pobieranie wartości konfiguracyjnych z `ps_configuration` do renderowania szablonów.
    - Metoda `_clearCache()` do czyszczenia pamięci podręcznej specyficznej dla modułu.
    - Metoda `_displayForm()` do renderowania formularza konfiguracji w back-office.

### 4.4 Zasoby JavaScript (`views/js/`)

- W tym module nie ma niestandardowych plików JavaScript. Cała funkcjonalność jest obsługiwana po stronie serwera lub za pomocą standardowego HTML/CSS.

### 4.5 Arkusze stylów CSS (`views/css/`)

- W tym module nie ma niestandardowych plików CSS. Całe stylowanie jest stosowane bezpośrednio w szablonie `displayHeader.tpl` lub bezpośrednio za pomocą metody `hookDisplayHeader`, używając wartości konfiguracyjnych. Oznacza to, że deweloperzy, którzy chcą nadpisać style, będą musieli bezpośrednio celować w wygenerowany kod HTML lub użyć hooka `displayHeader` do wstrzyknięcia własnego CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:

  - `fbgroup/views/displayHeader.tpl`:
    - **Hook:** Głównie przeznaczony dla `displayHeader` (chociaż metoda `hookDisplayHeader` modułu jest używana do wstrzykiwania dynamicznego CSS, a nie do renderowania samego widgetu). Ten szablon NIE jest używany do głównego wyświetlania widgetu. Prawdopodobnie jest to pozostałość lub jest używany do wstrzykiwania meta/CSS.
    - **Cel:** Gdyby był używany, wyprowadzałby kod HTML w sekcji `<head>`. W kontekście tego modułu, metoda `hookDisplayHeader` jest używana do *wstrzykiwania stylów CSS* dynamicznie na podstawie ustawień konfiguracyjnych, a nie do renderowania widocznego szablonu.
  - `fbgroup/views/displayWidget.tpl`:
    - **Hook:** Jest to główny szablon używany do renderowania widgetu dołączania do grupy na Facebooku we wszystkich wybranych hookach front-office (np. `displayFooter`, `displayHome`, `displayRightColumn` itp.).
    - **Cel:** Wyprowadza strukturę HTML dla widgetu, w tym nagłówek, opis i przycisk „Dołącz do grupy”. Otrzymuje zmienne, takie jak `fbg_href`, `fbg_header`, `fbg_desc`, `fbg_btn_text` i dynamiczne style CSS z metod hooków modułu.
- **Szablony administracyjne (`views/templates/admin/`)**: Brak. Formularz konfiguracji jest budowany programowo w `getContent()` za pomocą `HelperForm` PrestaShop.
- **Szablony front-office (`views/templates/front/`)**: Brak.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy żadnych niestandardowych tabel bazy danych.
  - Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` (lub prefiksie `_configuration`, w zależności od konfiguracji) przy użyciu kluczy konfiguracyjnych wymienionych w sekcji 4.1 (np. `FBG_HREF`, `FBG_WIDTH`, `FBG_HEADER` itp.).
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Używany przez moduł do wstrzykiwania dynamicznych stylów CSS dla widgetu na podstawie konfiguracji. |
| `displayFooter` | Na dole każdej strony, przed `</body>`. | Renderuje szablon `displayWidget.tpl`, wyświetlając widget Facebooka. |
| `displayHome` | Na stronie głównej, zazwyczaj w głównym obszarze treści. | Renderuje szablon `displayWidget.tpl`, wyświetlając widget Facebooka. |
| `displayNav1` | W pasku nawigacyjnym, często w lewym górnym rogu. | Renderuje szablon `displayWidget.tpl`, wyświetlając widget Facebooka. |
| `displayNav2` | W pasku nawigacyjnym, często w prawym górnym rogu. | Renderuje szablon `displayWidget.tpl`, wyświetlając widget Facebooka. |
| `displayNav` | Ogólny hook nawigacyjny, zależny od motywu. | Renderuje szablon `displayWidget.tpl`, wyświetlając widget Facebooka. |
| `displayFbgroup` | Niestandardowy hook, wymaga integracji z motywem. | Renderuje szablon `displayWidget.tpl`, wyświetlając widget Facebooka. |
| `displayTop` | W sekcji nagłówka, często nad logo. | Renderuje szablon `displayWidget.tpl`, wyświetlając widget Facebooka. |
| `displayTopColumn` | W głównym obszarze treści nagłówka. | Renderuje szablon `displayWidget.tpl`, wyświetlając widget Facebooka. |
| `displayLeftColumn` | W lewym pasku bocznym stron, które go posiadają. | Renderuje szablon `displayWidget.tpl`, wyświetlając widget Facebooka. |
| `displayRightColumn` | W prawym pasku bocznym stron, które go posiadają. | Renderuje szablon `displayWidget.tpl`, wyświetlając widget Facebooka. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Widget dołączania do grupy na Facebooku”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
