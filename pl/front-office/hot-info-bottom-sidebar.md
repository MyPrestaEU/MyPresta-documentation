---
title: "Hot Info - dolny pasek boczny - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop Hot Info - dolny pasek boczny od MyPresta.eu."
sidebar:
  label: "Hot Info - dolny pasek boczny - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Hot Info - bottom sidebar na MyPresta.eu](https://mypresta.eu/modules/front-office-features/hot-info-bottom-sidebar.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/hot-info-bottom-sidebar/)
>
> ---


# Hot Info - dolny pasek boczny

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zwykle dostępne w każdym nowoczesnym środowisku hostingowym.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj)

Po zainstalowaniu modułu kliknij „Konfiguruj”, aby uzyskać dostęp do jego ustawień. Tutaj zdefiniujesz zawartość i wygląd paska bocznego „Hot Info”.

#### **Zawartość bloku Hot Info**

- **Co robi to ustawienie:** Jest to główny obszar, w którym wprowadzisz rzeczywistą treść, którą klienci zobaczą w dolnym pasku bocznym. Jest to edytor tekstu sformatowanego (WYSIWYG - What You See Is What You Get), podobny do tego, którego możesz używać do opisów produktów lub wpisów na blogu.
- **Efekt zmiany tego ustawienia:**
  - *Po dodaniu treści:* Tekst, obrazy, linki lub kod HTML, które tutaj wprowadzisz, zostaną wyświetlone w bloku „Hot Info” w Twoim sklepie.
  - *Po pozostawieniu pustego:* Blok „Hot Info” może nadal się pojawiać, ale będzie pusty, lub moduł może wcale się nie wyświetlać (w zależności od innych ustawień i zachowania szablonu). Kluczowe jest dodanie tutaj treści, aby moduł był użyteczny.
- **Zalecana wartość:** Wprowadź tutaj pożądane „gorące informacje”. Użyj jasnego, zwięzłego języka i silnych wezwań do działania.
- **Scenariusz / przykład dla sprzedawcy:** Możesz dodać „BŁYSKAWICZNA WYPRZEDAŻ! Zdobądź 20% zniżki na wszystkie artykuły letnie z kodem LATO20! [Kup teraz]” z linkiem do Twojej letniej kolekcji. Lub „Darmowa wysyłka na wszystkie zamówienia powyżej 200 zł!”

#### **Kolor tła**

- **Co robi to ustawienie:** Kontroluje kolor tła bloku „Hot Info”. Możesz wybrać kolor za pomocą narzędzia do wyboru kolorów.
- **Efekt zmiany tego ustawienia:**
  - *Po ustawieniu na konkretny kolor (np. #FF0000 dla czerwonego):* Tło bloku „Hot Info” zostanie wyświetlone w wybranym kolorze.
  - *Po pozostawieniu domyślnego lub przezroczystego:* Zazwyczaj dziedziczy kolor tła z Twojego szablonu lub jest przezroczysty, co może sprawić, że zbyt mocno się wtopi lub będzie trudny do odczytania.
- **Zalecana wartość:** Wybierz kolor, który albo uzupełnia branding Twojego sklepu, albo wyróżnia się, aby przyciągnąć uwagę, w zależności od Twojego celu. Kontrastujący kolor może być bardzo skuteczny.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój sklep używa dużo niebieskiego, możesz wybrać żywy pomarańczowy lub żółty, aby ogłoszenie wyprzedaży było bardziej widoczne.

#### **Kolor obramowania**

- **Co robi to ustawienie:** Kontroluje kolor obramowania wokół bloku „Hot Info”.
- **Efekt zmiany tego ustawienia:**
  - *Po ustawieniu na konkretny kolor (np. #000000 dla czarnego):* Obramowanie bloku „Hot Info” zostanie wyświetlone w wybranym kolorze.
  - *Po pozostawieniu domyślnego lub przezroczystego:* Blok może pojawić się bez widocznego obramowania lub może dziedziczyć kolor obramowania z Twojego szablonu.
- **Zalecana wartość:** Często kolor obramowania, który pasuje do koloru tekstu lub nieco ciemniejszy odcień koloru tła, działa dobrze.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoje tło jest jasnoniebieskie, ciemnoniebieskie obramowanie może nadać mu czysty, zdefiniowany wygląd.

#### **Rozmiar obramowania (w pikselach)**

- **Co robi to ustawienie:** Określa grubość obramowania wokół bloku „Hot Info”, mierzoną w pikselach.
- **Efekt zmiany tego ustawienia:**
  - *Po ustawieniu wartości takiej jak „2”:* Blok będzie miał obramowanie o grubości 2 pikseli.
  - *Po ustawieniu wartości „0”:* Nie zostanie wyświetlone żadne obramowanie.
- **Zalecana wartość:** Zacznij od małej wartości, takiej jak „1” lub „2”, dla subtelnego obramowania. Zwiększ ją, jeśli chcesz bardziej wyraźnej ramki.
- **Scenariusz / przykład dla sprzedawcy:** Obramowanie o grubości 2 pikseli może subtelnie obramować Twoją wiadomość, sprawiając, że będzie wyglądać jak odrębny element na stronie.

#### **Wysokość (w pikselach)**

- **Co robi to ustawienie:** Kontroluje stałą wysokość bloku „Hot Info”, mierzoną w pikselach.
- **Efekt zmiany tego ustawienia:**
  - *Po ustawieniu wartości takiej jak „50”:* Blok będzie miał wysokość 50 pikseli.
  - *Gdy zawartość przekracza wysokość:* Jeśli Twoja zawartość jest wyższa niż określona wysokość, w bloku pojawi się pasek przewijania, umożliwiając klientom przewijanie treści.
- **Zalecana wartość:** Zachowaj tę wartość stosunkowo małą (np. 40-60 pikseli), aby uniknąć zajmowania zbyt dużej przestrzeni ekranu, zwłaszcza na urządzeniach mobilnych. Dostosuj w zależności od ilości treści, którą masz.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli masz krótką, jednowierszową wiadomość, wysokość 40 pikseli może być idealna. Jeśli masz kilka linii tekstu, możesz potrzebować 60-80 pikseli.

#### **Domyślny język (PS\_LANG\_DEFAULT)**

- **Co robi to ustawienie:** Jest to standardowe ustawienie PrestaShop, które definiuje domyślny język dla Twojego sklepu. Chociaż nie jest bezpośrednio konfigurowane przez ten moduł, pole treści modułu zazwyczaj będzie wyświetlać treść dla aktualnie wybranego języka w panelu administracyjnym, domyślnie dla tego języka.
- **Efekt zmiany tego ustawienia:** Wpływa to na domyślny język całego Twojego sklepu PrestaShop i sposób zarządzania treściami wielojęzycznymi. Dla tego modułu oznacza to, że wprowadzona treść zostanie powiązana z językiem, w którym aktualnie edytujesz w panelu administracyjnym.
- **Zalecana wartość:** Powinno to być ustawione na Twój podstawowy język sklepu.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoim głównym rynkiem jest Polska, będzie to ustawione na polski. Podczas wprowadzania treści dla bloku „Hot Info” upewnij się, że edytujesz w prawidłowym języku, jeśli Twój sklep obsługuje wiele języków.

#### **Aktualizacje MyPresta.eu (mypresta\_updates, update\_, updatev\_)**

- **Co robią te ustawienia:** Są to wewnętrzne ustawienia używane przez moduły MyPresta.eu do sprawdzania i zarządzania aktualizacjami. Zazwyczaj przechowują informacje o wersji modułu i o tym, kiedy ostatnio sprawdzono dostępność aktualizacji.
- **Efekt zmiany tych ustawień:**
  - *Gdy włączone/aktywne:* Moduł może komunikować się z serwerami MyPresta.eu, aby powiadomić Cię o nowych wersjach lub poprawkach bezpieczeństwa.
  - *Gdy wyłączone/nieaktywne:* Moduł nie będzie automatycznie sprawdzał dostępności aktualizacji.
- **Zalecana wartość:** Pozostaw te ustawienia bez zmian. Są one niezbędne do utrzymania modułu w aktualności i bezpieczeństwie.
- **Scenariusz / przykład dla sprzedawcy:** Zazwyczaj nie wchodzisz z nimi w bezpośrednią interakcję. Zapewniają one, że zostaniesz powiadomiony w panelu administracyjnym PrestaShop, gdy nowa wersja modułu będzie dostępna do pobrania z Twojego konta MyPresta.eu.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Zawartość bloku Hot Info** | Twoja niestandardowa wiadomość | Rzeczywisty tekst, obrazy, linki wyświetlane w dolnym pasku bocznym. |
| Konfiguracja modułu | **Kolor tła** | Wybierz, aby dopasować/kontrastować z motywem | Ustawia kolor tła bloku informacyjnego. |
| Konfiguracja modułu | **Kolor obramowania** | Wybierz, aby dopasować/kontrastować z motywem | Ustawia kolor obramowania wokół bloku informacyjnego. |
| Konfiguracja modułu | **Rozmiar obramowania (w pikselach)** | 1 lub 2 | Określa grubość obramowania. Ustaw na 0 dla braku obramowania. |
| Konfiguracja modułu | **Wysokość (w pikselach)** | 40-60 | Ustawia stałą wysokość bloku informacyjnego. Treść przekraczająca tę wysokość będzie przewijana. |
| Konfiguracja modułu | **PS\_LANG\_DEFAULT** | Podstawowy język Twojego sklepu | Domyślne ustawienie języka PrestaShop, wpływa na edycję treści. |
| Konfiguracja modułu | **Aktualizacje MyPresta.eu** | Włączone | Wewnętrzne ustawienia do sprawdzania aktualizacji modułu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Mój blok „Hot Info” nie wyświetla się w panelu klienta.**

-   **O:** Po pierwsze, upewnij się, że moduł jest zainstalowany i włączony w **Moduły > Menedżer modułów**. Po drugie, sprawdź, czy faktycznie dodałeś treść w polu „Zawartość bloku Hot Info” w konfiguracji modułu. Pusty blok może się nie renderować. Na koniec wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**) i pamięć podręczną przeglądarki.

**P2: Blok „Hot Info” wygląda dziwnie lub nie pasuje do stylu mojego szablonu.**

-   **O:** Moduł zapewnia podstawowe opcje stylizacji (tło, kolor/rozmiar obramowania, wysokość). Jeśli nadal koliduje z Twoim szablonem, CSS Twojego szablonu może nadpisywać style modułu.
    -   **Rozwiązanie dla sprzedawców:** Spróbuj dostosować kolory tła i obramowania w ustawieniach modułu, aby sprawdzić, czy znajdziesz lepsze dopasowanie. Jeśli nie, być może będziesz potrzebować webmastera, aby dodał niestandardowy CSS do Twojego szablonu, aby konkretnie celować i stylizować blok modułu.
    -   **Rozwiązanie dla webmasterów:** Sprawdź element w narzędziach deweloperskich przeglądarki, aby zidentyfikować sprzeczne reguły CSS i zastosuj bardziej szczegółowe lub `!important` reguły w niestandardowym pliku CSS Twojego szablonu.

**P3: Jak dodać obrazy lub linki do treści „Hot Info”?**

-   **O:** Użyj edytora tekstu sformatowanego dostępnego dla ustawienia „Zawartość bloku Hot Info”. Posiada on przyciski do wstawiania obrazów, tworzenia linków, formatowania tekstu (pogrubienie, kursywa) i wiele więcej, podobnie jak standardowy edytor tekstu. Kliknij ikonę „Obraz”, aby przesłać i wstawić obraz, lub zaznacz tekst i kliknij ikonę „Link”, aby dodać hiperłącze.

**P4: Czy mogę sprawić, aby blok „Hot Info” pojawiał się tylko na niektórych stronach?**

-   **O:** Ten moduł, w swojej obecnej wersji, jest zaprojektowany tak, aby pojawiał się globalnie na wszystkich stronach, na których wykonywany jest hook `displayHeader`. Jeśli potrzebujesz widoczności specyficznej dla strony, będziesz wymagać niestandardowego rozwoju, aby zmodyfikować logikę wyświetlania modułu lub użyć oddzielnego modułu zaprojektowanego do warunkowego wyświetlania treści.

**P5: Selektor kolorów nie działa lub nie wyświetla się.**

-   **O:** Upewnij się, że JavaScript w Twojej przeglądarce jest włączony. Czasami konflikty z innymi modułami lub JavaScriptem szablonu mogą uniemożliwić prawidłowe załadowanie selektora kolorów. Spróbuj wyczyścić pamięć podręczną przeglądarki i pliki cookie. Jeśli problem nadal występuje, może to wskazywać na bardziej złożony konflikt JavaScript, który webmaster musiałby zbadać.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Hot Info - dolny pasek boczny” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł `hotinfo` to standardowy moduł PrestaShop zgodny z wzorcem MVC, tam gdzie ma to zastosowanie. Działa głównie jako moduł wyświetlający, wstrzykując zawartość do hooka `displayHeader`. Konfiguracja jest obsługiwana za pomocą metody `getContent()` głównej klasy modułu, przechowując ustawienia bezpośrednio w `ps_configuration`. Wykorzystuje edytor tekstu sformatowanego (TinyMCE) do wprowadzania treści i selektor kolorów JavaScript do opcji stylizacji.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje niestandardowych kontrolerów front-office ani back-office. Cała konfiguracja jest obsługiwana w głównym pliku modułu `hotinfo.php` za pomocą metody `getContent()`.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Wszystkie dane (konfiguracja) są przechowywane bezpośrednio w tabeli `ps_configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`hotinfo/jscolor/jscolor.js`**

    -   **Zakres:** Panel administracyjny (strona konfiguracji modułu).
    -   **Opis:** Jest to zewnętrzna biblioteka JavaScript, która zapewnia przyjazny dla użytkownika interfejs selektora kolorów. Zazwyczaj jest inicjalizowana na polach wejściowych z określoną klasą (np. `jscolor`), aby umożliwić administratorom wizualne wybieranie kolorów dla tła i obramowania bloku „Hot Info”. Wiąże się z polami wejściowymi i aktualizuje ich wartości na podstawie wyboru koloru przez użytkownika.
-   **`hotinfo/tinymce16.js`**

    -   **Zakres:** Panel administracyjny (strona konfiguracji modułu).
    -   **Opis:** Ten skrypt prawdopodobnie inicjalizuje i konfiguruje wersję edytora tekstu sformatowanego TinyMCE dla pola tekstowego „Zawartość bloku Hot Info”. Przekształca standardowy element `<textarea>` HTML w bogaty w funkcje edytor, umożliwiając administratorom formatowanie tekstu, wstawianie obrazów, tworzenie linków i zarządzanie treścią HTML bez bezpośredniego kodowania. Ten skrypt wiązałby się z odpowiednim elementem textarea i zapewniałby interfejs edytora.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`hotinfo/css/hotinfo.css`**
    -   **Zakres:** Front-office (sklep widoczny dla klienta).
    -   **Opis:** Ten arkusz stylów zawiera podstawowe reguły CSS dla dolnego paska bocznego „Hot Info”. Definiuje stałe pozycjonowanie, wymiary, tło, obramowanie i stylizację tekstu dla bloku.
    -   **Kluczowe selektory (programiści mogą nadpisywać):**
        -   `#hotinfo_block`: Główny kontener dla całego bloku „Hot Info”. Tutaj stosowane są `position: fixed; bottom: 0; width: 100%;` i inne globalne style.
        -   `#hotinfo_block .hotinfo_content`: Wewnętrzny kontener dla rzeczywistej treści, gdzie `overflow-y: auto;` może być stosowane, jeśli treść przekracza zdefiniowaną wysokość.
        -   Style dla `p`, `a`, `img` wewnątrz `#hotinfo_block`, aby zapewnić dobry wygląd treści.
    -   **Strategia nadpisywania:** Programiści mogą nadpisywać te style, dodając bardziej szczegółowe reguły CSS w pliku `custom.css` lub `theme.css` swojego szablonu, lub tworząc motyw potomny i modyfikując CSS modułu bezpośrednio, jeśli to konieczne.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`hotinfo/hotinfo.tpl`**

    -   **Zakres:** Panel administracyjny (strona konfiguracji modułu).
    -   **Opis:** Ten szablon jest używany do renderowania formularza konfiguracji w panelu administracyjnym PrestaShop podczas uzyskiwania dostępu do strony konfiguracji modułu. Zawiera strukturę HTML dla edytora tekstu sformatowanego, selektorów kolorów i pól wejściowych dla ustawień wysokości i obramowania. Używa zmiennych Smarty do wstępnego wypełniania pól formularza bieżącymi wartościami konfiguracji.
-   **`hotinfo/views/templates/hook/hotinfo.tpl`**

    -   **Zakres:** Front-office (sklep widoczny dla klienta).
    -   **Opis:** Ten szablon jest odpowiedzialny za renderowanie bloku „Hot Info” w sklepie. Jest podłączony do `displayHeader`. Pobiera skonfigurowaną treść, kolor tła, kolor obramowania, rozmiar obramowania i wysokość ze zmiennych Smarty przekazanych przez moduł i stosuje je do struktury HTML.
    -   **Kluczowe elementy:**
        -   Główny `div` z identyfikatorem takim jak `hotinfo_block` dla stałego pozycjonowania.
        -   Wewnętrzny `div` dla treści, potencjalnie z `overflow: auto;` do przewijania.
        -   Rzeczywista treść jest renderowana za pomocą `{html_entity_decode($hotinfo_body)}` w celu wyświetlenia kodu HTML z edytora tekstu sformatowanego.
    -   **Hook:** `displayHeader` (chociaż wizualnie pojawia się na dole, hook znajduje się w nagłówku, aby zapewnić wczesne ładowanie i skuteczne stylizowanie za pomocą `position: fixed;`).

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł nie tworzy żadnych niestandardowych tabel SQL. Wszystkie ustawienia konfiguracyjne są przechowywane w standardowej tabeli PrestaShop `ps_configuration`.

    -   Wpisy `PS_CONFIGURATION`:
        -   `HOTINFO_BODY`: Przechowuje zawartość HTML bloku „Hot Info” (wielojęzyczny).
        -   `HOTINFO_BG_COLOR`: Przechowuje szesnastkową wartość koloru tła.
        -   `HOTINFO_BR_COLOR`: Przechowuje szesnastkową wartość koloru obramowania.
        -   `HOTINFO_BR_SIZE`: Przechowuje całkowitą wartość grubości obramowania.
        -   `HOTINFO_HEIGHT`: Przechowuje całkowitą wartość wysokości bloku.
        -   `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: Wewnętrzne klucze dla mechanizmu aktualizacji MyPresta.eu.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony. | Moduł używa tego hooka do wstrzykiwania swoich plików CSS i JavaScript oraz do renderowania głównej struktury HTML bloku „Hot Info”. Chociaż blok jest wizualnie umieszczony na dole, renderowanie go za pomocą `displayHeader` zapewnia, że jest dostępny wcześnie podczas ładowania strony i może być skutecznie stylizowany za pomocą `position: fixed;`. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Hot Info - dolny pasek boczny”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Najnowszą wersję modułu możesz pobrać z historii zamówień. W przypadku jakiejkolwiek pomocy technicznej lub pytań, skontaktuj się bezpośrednio z obsługą MyPresta.eu.
