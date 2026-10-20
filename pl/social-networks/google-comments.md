---
title: "Komentarze Google+ - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop Komentarze Google+ od MyPresta.eu."
sidebar:
  label: "Komentarze Google+ - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Google+ Comments na MyPresta.eu](https://mypresta.eu/modules/social-networks/google-comments.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/google-comments/)
>
> ---


# Komentarze Google+

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest główny ekran konfiguracji modułu Komentarze Google+. Znajdziesz tutaj wszystkie ustawienia, aby kontrolować, jak komentarze pojawiają się i funkcjonują w Twoim sklepie.

**Dostęp:** Przejdź do **Moduły > Menedżer modułów**, wyszukaj „Komentarze Google+” i kliknij **„Konfiguruj”**.

#### Ustawienia i opcje

1.  **Wyświetlaj Komentarze Google+ na stronie produktu**

    -   **Co robi to ustawienie:** Ten przełącznik kontroluje, czy sekcja komentarzy Google+ jest wyświetlana na stronach Twoich produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone (TAK):* Sekcja komentarzy Google+ pojawi się na wszystkich stronach Twoich produktów, umożliwiając klientom przeglądanie i dodawanie komentarzy.
        -   *Gdy wyłączone (NIE):* Sekcja komentarzy Google+ zostanie ukryta ze wszystkich stron produktów.
    -   **Zalecana wartość:** TAK (jeśli chcesz korzystać z funkcji komentowania).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz zachęcić do interakcji z klientami i wykorzystać treści generowane przez użytkowników, włącz to. Jeśli wolisz inny system komentowania lub w ogóle nie chcesz komentarzy, wyłącz to.
2.  **Wybierz zaczep dla Komentarzy Google+**

    -   **Co robi to ustawienie:** Ta lista rozwijana pozwala wybrać, gdzie na stronie produktu (lub innych stronach) zostanie wyświetlony blok komentarzy Google+. Zaczepy to specyficzne miejsca w Twoim szablonie PrestaShop, gdzie moduły mogą wstrzykiwać zawartość.
    -   **Efekt zmiany tego ustawienia:**
        -   *Wybranie `displayProductExtraContent` (lub podobnego zaczepu strony produktu):* Komentarze pojawią się w głównym obszarze treści strony produktu, zazwyczaj poniżej opisu produktu lub zakładek. Jest to najczęstsze i zalecane umiejscowienie.
        -   *Wybranie `displayLeftColumn` lub `displayRightColumn`:* Blok komentarzy pojawi się w lewym lub prawym pasku bocznym Twojego sklepu (jeśli Twój szablon je posiada i są aktywne na stronach produktów). Zazwyczaj nie jest to idealne dla pełnej sekcji komentarzy.
        -   *Wybranie `displayFooter`:* Blok komentarzy pojawi się w sekcji stopki Twojego sklepu. Ponownie, nie jest to idealne dla komentarzy specyficznych dla produktu.
    -   **Zalecana wartość:** `displayProductExtraContent` lub podobny zaczep, który umieszcza komentarze bezpośrednio w obszarze treści strony produktu. Dokładna nazwa zaczepu może się nieznacznie różnić w zależności od wersji PrestaShop lub szablonów, ale dąż do takiego, który dobrze integruje się ze szczegółami produktu.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby komentarze były łatwo widoczne, gdy klient przegląda produkt. Wybranie `displayProductExtraContent` zapewnia, że są one częścią głównego przepływu informacji o produkcie.
3.  **Szerokość bloku Komentarzy Google+ (w pikselach)**

    -   **Co robi to ustawienie:** To pole wprowadzania pozwala zdefiniować stałą szerokość sekcji komentarzy Google+ w pikselach.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ustawienie konkretnej wartości pikselowej (np. `600`):* Blok komentarzy zawsze będzie próbował renderować się z dokładnie tą szerokością. Jeśli ekran jest mniejszy, może wystąpić przepełnienie lub problemy z układem.
        -   *Pozostawienie pustego lub ustawienie na `100%` (jeśli moduł na to pozwala, choć zazwyczaj oczekuje pikseli):* Moduł może próbować automatycznie dostosować, ale dla komentarzy Google+ często oczekuje się stałej szerokości w pikselach.
    -   **Zalecana wartość:** Wartość, która dobrze pasuje do głównego obszaru treści strony produktu, zazwyczaj od `600` do `800` pikseli, w zależności od układu Twojego szablonu. Może być konieczne eksperymentowanie, aby znaleźć najlepsze dopasowanie.
    -   **Scenariusz / przykład dla sprzedawcy:** Obszar treści strony Twojego produktu ma 700px szerokości. Ustawienie tej wartości na `650`px zapewnia, że blok komentarzy ładnie się mieści, nie psując układu.
4.  **Liczba wyświetlanych komentarzy**

    -   **Co robi to ustawienie:** To pole wprowadzania kontroluje, ile komentarzy jest początkowo ładowanych i wyświetlanych w sekcji komentarzy Google+. Więcej komentarzy może być zazwyczaj ładowanych przez użytkownika klikającego przycisk „Załaduj więcej” dostarczony przez Google.
    -   **Efekt zmiany tego ustawienia:**
        -   *Ustawienie niskiej liczby (np. `5`):* Początkowo wyświetli się tylko kilka komentarzy, co przyspieszy ładowanie strony i sprawi, że będzie mniej zagracona. Użytkownicy będą musieli kliknąć, aby zobaczyć więcej.
        -   *Ustawienie wysokiej liczby (np. `20`):* Więcej komentarzy będzie widocznych od razu, co może być dobre dla produktów z dużą liczbą komentarzy, ale może sprawić, że strona będzie dłuższa.
    -   **Zalecana wartość:** Od `5` do `10`. Zapewnia to dobrą równowagę między pokazaniem zaangażowania a zachowaniem zwięzłości strony.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz wiele komentarzy do popularnych produktów. Ustawienie tej wartości na `7` pokazuje wystarczające zaangażowanie, nie przytłaczając klienta bardzo długim przewijaniem.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyświetlaj Komentarze Google+ na stronie produktu | TAK | Włącza/wyłącza sekcję komentarzy na stronach produktów. |
| Konfiguracja modułu | Wybierz zaczep dla Komentarzy Google+ | `displayProductExtraContent` | Określa, gdzie blok komentarzy pojawia się na stronie. |
| Konfiguracja modułu | Szerokość bloku Komentarzy Google+ (w pikselach) | `600` - `800` | Ustawia stałą szerokość sekcji komentarzy. Dostosuj do swojego szablonu. |
| Konfiguracja modułu | Liczba wyświetlanych komentarzy | `5` - `10` | Kontroluje, ile komentarzy jest początkowo widocznych. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Sekcja komentarzy nie wyświetla się na moich stronach produktów po instalacji.**
O:

1.  **Sprawdź konfigurację modułu:** Przejdź do **Moduły > Menedżer modułów > Komentarze Google+ > Konfiguruj**. Upewnij się, że opcja „Wyświetlaj Komentarze Google+ na stronie produktu” jest ustawiona na TAK.
2.  **Zweryfikuj wybór zaczepu:** Upewnij się, że opcja „Wybierz zaczep dla Komentarzy Google+” jest ustawiona na odpowiedni zaczep strony produktu, taki jak `displayProductExtraContent`. Jeśli Twój szablon używa niestandardowego zaczepu dla treści produktu, może być konieczne wybranie go lub skonsultowanie się z twórcą szablonu.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty”). Czasami pamięć podręczna PrestaShop uniemożliwia natychmiastowe pojawienie się nowej zawartości modułu.
4.  **Kompatybilność z szablonem:** Niektóre wysoce spersonalizowane szablony mogą nadpisywać standardowe zaczepy PrestaShop. Jeśli problem nadal występuje, skontaktuj się z twórcą szablonu lub wsparciem MyPresta.eu.

**P: Sekcja komentarzy wygląda zbyt szeroko/wąsko lub psuje mój układ.**
O:

1.  **Dostosuj ustawienie szerokości:** W konfiguracji modułu zmodyfikuj ustawienie „Szerokość bloku Komentarzy Google+ (w pikselach)”. Eksperymentuj z różnymi wartościami (np. 600, 700, 800), aż dopasuje się do układu strony produktu.
2.  **Sprawdź CSS szablonu:** Jeśli dostosowanie szerokości nie pomaga, CSS Twojego szablonu może kolidować. Może być konieczne, aby webmaster zbadał element i dodał niestandardowy CSS do Twojego szablonu, aby zapewnić prawidłowe wyświetlanie.

**P: Czy mogę moderować komentarze, zanim się pojawią?**
O: Moduł Komentarze Google+ używa własnego systemu komentowania Google. Możliwości moderacji są zazwyczaj obsługiwane w samej platformie Google, a nie bezpośrednio w PrestaShop. Musiałbyś sprawdzić zasady i narzędzia Google dotyczące moderacji komentarzy związanych z osadzonymi widżetami.

**P: Moi klienci mają problemy z dodawaniem komentarzy.**
O:

1.  **Wymóg konta Google:** Przypomnij klientom, że muszą być zalogowani na konto Google, aby móc dodawać komentarze.
2.  **Problemy z przeglądarką:** Doradź klientom, aby spróbowali innej przeglądarki lub wyczyścili pamięć podręczną i pliki cookie przeglądarki.
3.  **Status usługi Google:** Czasami usługi Google mogą doświadczać tymczasowych awarii. Sprawdź strony statusu Google, jeśli wielu użytkowników zgłasza problemy jednocześnie.

**P: Czy ten moduł nadal działa, skoro Google+ zostało zamknięte?**
O: Chociaż Google+ jako sieć społecznościowa zostało wycofane, Google nadal udostępnia osadzone widżety do komentowania, które wykorzystują konta Google. Ten moduł integruje się z tą podstawową infrastrukturą komentowania Google. Może nie zapewniać bezpośredniego „wsparcia SEO” z „+1” jak kiedyś, ale nadal funkcjonuje jako system komentowania zasilany przez Google.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera przegląd techniczny dla programistów i webmasterów pracujących z modułem Komentarze Google+.

### 4.1 Przegląd architektury

Moduł `Komentarze Google+` to prosty moduł PrestaShop, zaimplementowany głównie w jego głównym pliku PHP (`google-comments.php`). Wykorzystuje klasę `Module` PrestaShop i klasę `Configuration` do zarządzania ustawieniami. Jego podstawowa funkcjonalność polega na wstrzykiwaniu fragmentu kodu JavaScript dostarczonego przez Google do front-office, który następnie renderuje widżet komentarzy. W samym module nie ma niestandardowych kontrolerów, modeli ani złożonych interakcji AJAX; w dużej mierze opiera się na zewnętrznym skrypcie Google w zakresie swojej funkcjonalności front-endowej.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Wyświetlanie modułu w front-office jest obsługiwane poprzez zaczepianie do standardowych zaczepów wyświetlania PrestaShop i renderowanie szablonu Smarty zawierającego kod osadzania komentarzy Google.
-   **Kontrolery Back-Office Admin**: Brak. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   W tym module nie ma niestandardowych klas ani definicji `ObjectModel`. Wszystkie dane są przechowywane bezpośrednio w tabeli `ps_configuration` PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

-   W tym module nie ma niestandardowych plików JavaScript. Funkcjonalność modułu opiera się całkowicie na zewnętrznej bibliotece JavaScript Google, którą osadza.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   W tym module nie ma niestandardowych plików CSS. Stylizacja widżetu komentarzy Google jest kontrolowana przez własne osadzone style Google. Wszelkie niestandardowe style musiałyby być skierowane na wygenerowane elementy iframe/Google za pomocą nadpisywania szablonu (co może być trudne ze względu na ograniczenia iframe między domenami).

### 4.6 Struktura szablonu Smarty (`views/templates/`)

Moduł używa pojedynczego szablonu Smarty do renderowania widżetu komentarzy Google.

-   **Szablony zaczepów (`views/templates/hook/`)**:
    -   `googlecomments.tpl`: Ten szablon jest renderowany, gdy moduł jest zaczepiony. Zawiera strukturę HTML dla widżetu komentarzy Google, w tym element `<div>` z atrybutami `data-href`, `data-width` i `data-num-comments` oraz tag `script` do ładowania Google Platform JavaScript SDK.
        -   **Cel:** Osadzenie widżetu komentarzy Google w front-office.
        -   **Używane zmienne:**
            -   `{$link->getModuleLink('googlecomments', 'ajax', array(), true)|escape:'htmlall':'UTF-8'}`: Jest to prawdopodobnie pozostałość lub symbol zastępczy, ponieważ moduł nie używa kontrolera AJAX. Atrybut `data-href` dla komentarzy Google zazwyczaj wskazuje na kanoniczny adres URL strony, na której wyświetlane są komentarze (np. adres URL strony produktu).
            -   `{Configuration::get('GOOGLE_COMMENTS_WIDTH')}`: Pobiera skonfigurowaną szerokość bloku komentarzy.
            -   `{Configuration::get('GOOGLE_COMMENTS_NUM')}`: Pobiera skonfigurowaną liczbę komentarzy do wyświetlenia.

### 4.7 Schemat bazy danych i mapa zaczepów

-   **Tabele bazy danych**:
    Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Wszystkie jego ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration`:

    -   `GOOGLE_COMMENTS_ENABLED`: Przechowuje `1` (włączone) lub `0` (wyłączone) dla wyświetlania komentarzy.
    -   `GOOGLE_COMMENTS_HOOK`: Przechowuje nazwę wybranego zaczepu (np. `displayProductExtraContent`).
    -   `GOOGLE_COMMENTS_WIDTH`: Przechowuje szerokość bloku komentarzy w pikselach.
    -   `GOOGLE_COMMENTS_NUM`: Przechowuje liczbę komentarzy do wyświetlenia.
-   **Tabela zarejestrowanych zaczepów**:

| Nazwa zaczepu | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Służy do rejestrowania zasobów (chociaż ten moduł nie używa go do tego celu, jest to powszechny zaczep). |
| `displayProductExtraContent` | W głównym obszarze treści strony produktu, często w zakładce lub poniżej opisu. | **Główny zaczep do wyświetlania bloku komentarzy na stronach produktów.** |
| `displayLeftColumn` | W lewym pasku bocznym sklepu. | Opcjonalny zaczep do wyświetlania bloku komentarzy (mniej powszechny dla pełnych komentarzy). |
| `displayRightColumn` | W prawym pasku bocznym sklepu. | Opcjonalny zaczep do wyświetlania bloku komentarzy (mniej powszechny dla pełnych komentarzy). |
| `displayFooter` | W sekcji stopki sklepu. | Opcjonalny zaczep do wyświetlania bloku komentarzy (mniej powszechny dla pełnych komentarzy). |
| `actionFrontControllerSetMedia` | Przed renderowaniem strony przez kontroler front-end, umożliwiając modułom dodawanie JS/CSS. | Służy do dodawania Google Platform JavaScript SDK do strony. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu Komentarze Google+, prosimy zapoznać się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w udzielanie pomocy i zapewnienie płynnego działania Twoich modułów.
