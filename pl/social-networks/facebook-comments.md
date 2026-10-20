---
title: "Komentarze Facebooka - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu Komentarze Facebooka PrestaShop od MyPresta.eu."
sidebar:
  label: "Komentarze Facebooka - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook Comments na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-comments.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-comments/)
>
> ---


# Komentarze Facebooka

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i każdego modułu, który wchodzi w interakcje z zewnętrznymi API, takimi jak Facebook.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj”, aby uzyskać dostęp do ustawień modułu. To tutaj będziesz kontrolować, jak pole Komentarzy Facebooka pojawia się i działa na stronach Twoich produktów.

#### 2.1.1 Identyfikator aplikacji Facebooka (`Facebook App ID`)

-   **Co robi to ustawienie:** Jest to unikalny identyfikator Twojej aplikacji Facebooka. Chociaż moduł może działać bez niego, podanie identyfikatora aplikacji daje Ci dostęp do narzędzi moderacji i statystyk Facebooka dla komentarzy na Twojej stronie.
-   **Efekt zmiany tego ustawienia:**
    *   *Po podaniu:* Uzyskujesz dostęp do panelu moderacji komentarzy Facebooka (developers.facebook.com/tools/comments), gdzie możesz przeglądać, zatwierdzać lub usuwać komentarze. Pomaga to również Facebookowi przypisać komentarze do Twojej konkretnej witryny.
    *   *Po pozostawieniu pustego:* Komentarze nadal będą się pojawiać, ale nie będziesz mieć zaawansowanych możliwości moderacji za pośrednictwem narzędzi deweloperskich Facebooka. Będziesz polegać na domyślnym filtrowaniu spamu przez Facebooka.
-   **Zalecana wartość:** Zdecydowanie zaleca się utworzenie aplikacji Facebooka i wprowadzenie tutaj identyfikatora aplikacji w celu lepszej kontroli i moderacji.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz mieć pewność, że wszystkie komentarze są odpowiednie i na temat. Konfigurując identyfikator aplikacji Facebooka, możesz łatwo moderować komentarze bezpośrednio z panelu deweloperskiego Facebooka, usuwając spam lub nieodpowiednie treści.

#### 2.1.2 Liczba komentarzy (`Number of Comments`)

-   **Co robi to ustawienie:** Kontroluje, ile komentarzy jest początkowo wyświetlanych w polu Komentarzy Facebooka, zanim użytkownicy będą musieli kliknąć „Pokaż więcej komentarzy” lub „Załaduj więcej”, aby zobaczyć starsze.
-   **Efekt zmiany tego ustawienia:**
    *   *Po ustawieniu niskiej liczby (np. 5):* Sekcja komentarzy będzie bardziej kompaktowa, wymagając od użytkowników kliknięcia, aby zobaczyć więcej. Może to być dobre dla stron z ograniczoną przestrzenią lub jeśli chcesz, aby początkowe ładowanie strony było lżejsze.
    *   *Po ustawieniu wyższej liczby (np. 20):* Więcej komentarzy będzie widocznych natychmiast, zapewniając więcej dowodów społecznych na pierwszy rzut oka. Może to jednak wydłużyć stronę produktu.
-   **Zalecana wartość:** 5-10 komentarzy to dobry punkt wyjścia, aby zrównoważyć widoczność i długość strony. Dostosuj w zależności od projektu strony produktu i typowej liczby komentarzy.
-   **Scenariusz / przykład dla sprzedawcy:** W przypadku popularnych produktów z wieloma komentarzami możesz ustawić tę wartość na 5, aby strona była uporządkowana. W przypadku nowszych produktów ustawienie jej na 10 może zachęcić do większej interakcji, pokazując więcej istniejących komentarzy.

#### 2.1.3 Szerokość pola komentarzy (`Width of Comments Box`)

-   **Co robi to ustawienie:** Określa szerokość pola Komentarzy Facebooka w pikselach.
-   **Efekt zmiany tego ustawienia:**
    *   *Po ustawieniu konkretnej wartości w pikselach (np. 600px):* Pole komentarzy zachowa tę stałą szerokość, potencjalnie tworząc pustą przestrzeń lub przepełnienie, jeśli obszar zawartości Twojego motywu jest węższy lub szerszy.
    *   *Po pozostawieniu pustego lub ustawieniu na 100% (jeśli obsługiwane przez moduł):* Pole komentarzy spróbuje automatycznie dostosować się do dostępnej szerokości swojego kontenera nadrzędnego, czyniąc je responsywnym.
-   **Zalecana wartość:** Pozostaw puste dla automatycznego wykrywania lub ustaw na 100%, jeśli moduł to obsługuje, aby zapewnić responsywność. Jeśli potrzebujesz stałej szerokości, upewnij się, że pasuje ona do obszaru zawartości Twojego motywu.
-   **Scenariusz / przykład dla sprzedawcy:** Twoja strona produktu ma główną kolumnę treści o szerokości 700px. Możesz ustawić szerokość na 700px, aby idealnie wypełnić tę przestrzeń. Jeśli chcesz, aby dostosowywała się do urządzeń mobilnych, pozostawienie jej pustej jest zazwyczaj najlepsze.

#### 2.1.4 Język pola komentarzy (`Language of Comments Box`)

-   **Co robi to ustawienie:** Pozwala określić język interfejsu wtyczki Komentarzy Facebooka (np. „Napisz komentarz…”, „Pokaż więcej komentarzy”).
-   **Efekt zmiany tego ustawienia:**
    *   *Po ustawieniu konkretnego kodu języka (np. „en\_US” dla angielskiego, „fr\_FR” dla francuskiego):* Tekst wtyczki Facebooka będzie wyświetlany w tym języku, niezależnie od języka przeglądarki użytkownika lub aktywnego języka Twojego sklepu PrestaShop.
    *   *Po pozostawieniu pustego:* Facebook zazwyczaj spróbuje wykryć preferowany język użytkownika lub język Twojego sklepu PrestaShop.
-   **Zalecana wartość:** Zazwyczaj najlepiej jest pozostawić to puste, aby Facebook mógł automatycznie wykryć język użytkownika, lub ustawić na podstawowy język Twojego sklepu, jeśli chcesz zachować spójność.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój sklep jest skierowany głównie do klientów w Niemczech, możesz ustawić to na „de\_DE”, aby upewnić się, że cały tekst wtyczki Facebooka jest w języku niemieckim, nawet jeśli przeglądarka użytkownika jest ustawiona na angielski.

#### 2.1.5 Pozycja pola komentarzy (`Position of Comments Box`)

-   **Co robi to ustawienie:** Określa, gdzie na stronie produktu zostanie wyświetlone pole Komentarzy Facebooka. Możesz wybrać spośród różnych hooków PrestaShop.
-   **Efekt zmiany tego ustawienia:**
    *   *Po ustawieniu na `displayProductButtons` (lub podobny):* Pole komentarzy może pojawić się w pobliżu przycisku „Dodaj do koszyka” lub innych akcji produktu.
    *   *Po ustawieniu na `displayFooterProduct` (lub podobny):* Pole komentarzy pojawi się niżej na stronie produktu, często poniżej głównych szczegółów produktu, co jest powszechną i zazwyczaj preferowaną lokalizacją.
    *   *Po ustawieniu na `displayRightColumn` lub `displayLeftColumn` (jeśli dostępne):* Pole komentarzy pojawiłoby się w jednej z bocznych kolumn Twojego sklepu, co jest mniej powszechne dla komentarzy i może nie być idealne wizualnie.
-   **Zalecana wartość:** `displayFooterProduct` lub podobny hook, który umieszcza sekcję komentarzy poniżej głównych informacji o produkcie, jest zazwyczaj najbardziej naturalnym i efektywnym umiejscowieniem.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby komentarze były widoczne, ale nie odwracały uwagi od głównego celu dodania produktu do koszyka. Umieszczenie ich w `displayFooterProduct` zapewnia, że klienci najpierw zobaczą wszystkie szczegóły produktu, a następnie mogą zaangażować się w komentarze.

#### 2.1.6 Włącz komentarze Facebooka (`Enable Facebook Comments`)

-   **Co robi to ustawienie:** Jest to prosty przełącznik WŁ./WYŁ. do aktywacji lub dezaktywacji całej funkcjonalności Komentarzy Facebooka.
-   **Efekt zmiany tego ustawienia:**
    *   *Po włączeniu (TAK):* Pole Komentarzy Facebooka pojawi się na stronach Twoich produktów zgodnie z innymi ustawieniami.
    *   *Po wyłączeniu (NIE):* Pole Komentarzy Facebooka zostanie całkowicie ukryte ze stron Twoich produktów, a moduł nie załaduje żadnych skryptów związanych z Facebookiem.
-   **Zalecana wartość:** TAK, jeśli chcesz korzystać z tej funkcji.
-   **Scenariusz / przykład dla sprzedawcy:** Zakończyłeś konfigurację modułu i chcesz go uruchomić w swoim sklepie. Przełączasz to na TAK. Później, jeśli zdecydujesz się tymczasowo wyłączyć komentarze w celu konserwacji, możesz przełączyć to na NIE.

#### 2.1.7 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Identyfikator aplikacji Facebooka | (Puste) / Zalecane: Twój identyfikator aplikacji | Włącza narzędzia moderacji Facebooka dla komentarzy. |
| Konfiguracja modułu | Liczba komentarzy | 5-10 | Określa, ile komentarzy jest początkowo widocznych. Wpływa na długość strony. |
| Konfiguracja modułu | Szerokość pola komentarzy | (Puste) / Automatyczne wykrywanie (Responsywne) | Definiuje szerokość sekcji komentarzy. Puste dla responsywności. |
| Konfiguracja modułu | Język pola komentarzy | (Puste) / Automatyczne wykrywanie | Ustawia język interfejsu wtyczki Facebooka. Puste dla języka użytkownika/sklepu. |
| Konfiguracja modułu | Pozycja pola komentarzy | `displayFooterProduct` | Określa, gdzie na stronie produktu pojawia się pole komentarzy. |
| Konfiguracja modułu | Włącz komentarze Facebooka | TAK | Włącza lub wyłącza całą funkcję Komentarzy Facebooka. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Pole Komentarzy Facebooka nie wyświetla się na stronach moich produktów. Co powinienem zrobić?**
O:

1.  **Sprawdź „Włącz komentarze Facebooka”:** Upewnij się, że to ustawienie w konfiguracji modułu jest ustawione na TAK.
2.  **Zweryfikuj pozycję:** Upewnij się, że ustawienie „Pozycja pola komentarzy” jest ustawione na hook, który jest faktycznie obecny i renderowany przez Twój motyw na stronach produktów (np. `displayFooterProduct`). Niektóre niestandardowe motywy mogą nie używać wszystkich standardowych hooków.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty”). Czasami stare, buforowane treści uniemożliwiają pojawienie się nowych modułów.
4.  **Kompatybilność z motywem:** Jeśli używasz mocno dostosowanego motywu, może on nadpisywać standardowe szablony stron produktów lub usuwać niezbędne hooki. Skontaktuj się z deweloperem motywu lub ekspertem PrestaShop w celu uzyskania pomocy.
5.  **Problemy z przeglądarką:** Spróbuj wyczyścić pamięć podręczną i pliki cookie przeglądarki lub przetestuj w trybie incognito.

**P: Jak moderować komentarze?**
O: Jeśli skonfigurowałeś identyfikator aplikacji Facebooka i wprowadziłeś go w konfiguracji modułu, możesz moderować komentarze bezpośrednio za pomocą narzędzi deweloperskich Facebooka. Przejdź do [developers.facebook.com/tools/comments](https://developers.facebook.com/tools/comments). Musisz być zalogowany na konto Facebooka powiązane z Twoim identyfikatorem aplikacji.

**P: Czy mogę zmienić styl (kolory, czcionki) pola Komentarzy Facebooka?**
O: Stylizacja wtyczki Komentarzy Facebooka jest w dużej mierze kontrolowana przez samego Facebooka, aby zachować spójne doświadczenie marki. Masz bardzo ograniczoną kontrolę nad jej wewnętrznym wyglądem. Możesz kontrolować szerokość i jej umiejscowienie, ale nie jej wewnętrzny CSS.

**P: Czy Komentarze Facebooka spowolnią moją stronę internetową?**
O: Wtyczka Komentarzy Facebooka ładuje zewnętrzne skrypty z Facebooka. Chociaż Facebook je optymalizuje, każdy zewnętrzny skrypt może dodać niewielkie opóźnienie do ładowania strony. Moduł jest zaprojektowany tak, aby ładować te skrypty efektywnie. Możesz użyć narzędzi takich jak Google PageSpeed Insights do monitorowania wydajności swojej witryny.

**P: Czy potrzebuję strony biznesowej na Facebooku, aby ten moduł działał?**
O: Nie, nie potrzebujesz strony biznesowej na Facebooku. Jeśli jednak chcesz korzystać z zaawansowanych narzędzi moderacji, będziesz potrzebować konta dewelopera Facebooka i utworzyć podstawową aplikację Facebooka, która jest oddzielnym bytem od strony biznesowej.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł Komentarze Facebooka (`facebook-comments`) to prosty moduł PrestaShop, zaprojektowany głównie do wstrzykiwania kodu HTML i JavaScript SDK wtyczki społecznościowej Komentarze Facebooka na strony produktów w front-office. Moduł ten stosuje standardową strukturę modułu PrestaShop, wykorzystując hooki do wstrzykiwania treści oraz klasę `Configuration` do przechowywania ustawień. Nie wprowadza niestandardowych kontrolerów, modeli ani złożonych interakcji AJAX.

### 4.2 Kontrolery (`controllers/`)

-   Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównego pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   Ten moduł **nie** zawiera żadnych niestandardowych klas ani definicji `ObjectModel`. Cała logika jest hermetyzowana w głównym pliku `facebook-comments.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript. Facebook JavaScript SDK jest ładowany bezpośrednio z CDN Facebooka przez szablon modułu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   Ten moduł **nie** zawiera żadnych niestandardowych plików CSS. Stylizacja wtyczki Komentarzy Facebooka jest obsługiwana przez własne arkusze stylów Facebooka.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł używa głównie jednego pliku szablonu do renderowania pola Komentarzy Facebooka.

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `facebook-comments.tpl`: To jest główny plik szablonu.
        -   **Cel:** Renderuje element `div`, który Facebook JavaScript SDK przekształca w pole komentarzy. Zawiera również niezbędny kod inicjalizacyjny JavaScript SDK.
        -   **Zmienne:**
            -   `{$facebook_app_id}`: Identyfikator aplikacji Facebooka z konfiguracji modułu.
            -   `{$facebook_comments_number}`: Liczba komentarzy do wyświetlenia.
            -   `{$facebook_comments_width}`: Szerokość pola komentarzy.
            -   `{$facebook_comments_lang}`: Kod języka dla wtyczki.
            -   `{$product_link}`: Adres URL bieżącej strony produktu, używany przez Facebooka do identyfikacji wątku komentarzy.
        -   **Hooki:** Ten szablon jest renderowany za pomocą hooka określonego w konfiguracji modułu (np. `displayFooterProduct`).

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Ten moduł **nie** tworzy żadnych niestandardowych tabel bazy danych. Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu standardowych metod PrestaShop `Configuration::get()` i `Configuration::updateValue()`.

    -   Klucze konfiguracyjne zazwyczaj obejmują:
        -   `FACEBOOK_COMMENTS_APP_ID`
        -   `FACEBOOK_COMMENTS_NUMBER`
        -   `FACEBOOK_COMMENTS_WIDTH`
        -   `FACEBOOK_COMMENTS_LANG`
        -   `FACEBOOK_COMMENTS_POSITION`
        -   `FACEBOOK_COMMENTS_ENABLED`
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Służy do jednorazowego dołączenia Facebook JavaScript SDK na stronę, zapewniając jego dostępność przed renderowaniem pola komentarzy. |
| `displayProductButtons` | W pobliżu przycisku „Dodaj do koszyka” na stronach produktów. | Opcjonalny hook do renderowania pola komentarzy, jeśli skonfigurowany przez sprzedawcę. |
| `displayFooterProduct` | Na dole treści strony produktu. | Powszechny i zalecany hook do renderowania pola komentarzy, jeśli skonfigurowany przez sprzedawcę. |
| `displayLeftColumn` | W lewym pasku bocznym stron. | Opcjonalny hook do renderowania pola komentarzy, jeśli skonfigurowany przez sprzedawcę. (Mniej powszechne dla komentarzy). |
| `displayRightColumn` | W prawym pasku bocznym stron. | Opcjonalny hook do renderowania pola komentarzy, jeśli skonfigurowany przez sprzedawcę. (Mniej powszechne dla komentarzy). |
| `displayFooter` | W sekcji stopki sklepu. | Opcjonalny hook do renderowania pola komentarzy, jeśli skonfigurowany przez sprzedawcę. (Mniej powszechne dla komentarzy dotyczących konkretnego produktu). |

Moduł dynamicznie rejestruje się do hooka wybranego przez sprzedawcę w konfiguracji. Hook `displayHeader` jest zawsze używany do ładowania Facebook SDK.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji, poprawek błędów i oficjalnego wsparcia dla modułu Komentarze Facebooka, prosimy odwołać się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu.
