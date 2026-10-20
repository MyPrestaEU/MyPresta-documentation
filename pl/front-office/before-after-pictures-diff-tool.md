---
title: "Przed i po - narzędzie do porównywania zdjęć - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów dla modułu PrestaShop „Przed i po - narzędzie do porównywania zdjęć” od MyPresta.eu."
sidebar:
  label: "Przed i po - narzędzie do porównywania zdjęć - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Before & after - pictures diff tool na MyPresta.eu](https://mypresta.eu/modules/front-office-features/before-after-pictures-diff-tool.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/before-after-pictures-diff-tool/)
>
> ---


# Przed i po - narzędzie do porównywania zdjęć

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Przed i po - narzędzie do porównywania zdjęć”, aby uzyskać dostęp do jego głównych ustawień.

#### Ustawienia ogólne

-   **Co robi to ustawienie:** Ta sekcja kontroluje ogólną aktywację i tryb działania modułu.
-   **Wpływ zmiany tego ustawienia:**
    -   *Włączony:* Moduł będzie aktywny w całym Twoim sklepie. Narzędzie do porównywania obrazów „Przed i po” będzie dostępne na stronach produktów, dla których skonfigurowano obrazy.
    -   *Wyłączony:* Moduł będzie nieaktywny. Narzędzie do porównywania obrazów „Przed i po” nie pojawi się na żadnych stronach produktów, nawet jeśli skonfigurowano dla nich obrazy.
    -   *Tryb testowy:* Ta opcja jest zazwyczaj używana w środowiskach deweloperskich lub testowych. Po włączeniu moduł może wyświetlać dodatkowe informacje debugowania lub działać w określonych warunkach, które nie są odpowiednie dla działającego sklepu produkcyjnego. Zazwyczaj nie jest zalecany dla sklepów działających na żywo, chyba że wyraźnie zaleci to wsparcie.
-   **Zalecana wartość:** „Włączony” dla sklepu działającego na żywo. „Wyłączony”, jeśli chcesz tymczasowo ukryć funkcję bez odinstalowywania modułu.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli wprowadzasz nową linię produktów, która w dużym stopniu opiera się na wizualnych transformacjach (np. niestandardowo malowane buty), ustawisz to na „Włączony”, aby zaprezentować pracę. Jeśli przeprowadzasz konserwację lub nie chcesz, aby funkcja była aktywna przez pewien czas, ustawisz ją na „Wyłączony”.

#### Ustawienia języka (domyślne)

Chociaż nie jest to wyraźnie wymienione jako ustawienie, moduł będzie respektował domyślne ustawienia języka PrestaShop dla Panelu administracyjnego.

-   **`PS_LANG_DEFAULT`**: To podstawowe ustawienie PrestaShop określa domyślny język dla Twojego sklepu.
-   **`PS_BO_ALLOW_EMPLOYEE_FORM_LANG`**: To podstawowe ustawienie PrestaShop pozwala pracownikom wybrać preferowany język dla formularzy.
-   **Wpływ zmiany tego ustawienia:** Te podstawowe ustawienia PrestaShop zapewniają, że wszelkie teksty lub etykiety dostarczone przez moduł w Panelu administracyjnym (np. na stronie edycji produktu do dodawania obrazów przed/po) są wyświetlane w prawidłowym języku dla administratora.
-   **Zalecana wartość:** Upewnij się, że `PS_LANG_DEFAULT` jest ustawiony na główny język Twojego sklepu. Jeśli masz wielojęzyczny zespół, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` powinno być włączone.

#### Ustawienia aktualizacji (domyślne)

Moduł zawiera również wewnętrzne ustawienia związane z aktualizacjami z MyPresta.eu. Są one zazwyczaj zarządzane automatycznie.

-   **`mypresta_updates`, `update_`, `updatev_`**: Są to wewnętrzne klucze konfiguracyjne używane przez moduły MyPresta.eu do sprawdzania i zarządzania aktualizacjami. Zazwyczaj nie musisz z nimi wchodzić w interakcje.
-   **Wpływ zmiany tego ustawienia:** Bezpośrednia modyfikacja tych kluczy może zakłócić zdolność modułu do otrzymywania ważnych aktualizacji i poprawek błędów.
-   **Zalecana wartość:** Pozostaw je bez zmian.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### Strona edycji produktu (Panel administracyjny > Katalog > Produkty > Edytuj produkt)

Ten moduł integruje się bezpośrednio ze standardowym interfejsem edycji produktu PrestaShop.

-   **Nazwa ekranu i lokalizacja w menu:** Aby uzyskać dostęp, przejdź do **Katalog > Produkty**, a następnie kliknij „Edytuj” przy dowolnym produkcie.
-   **Dostępne akcje i ustawienia:** Na stronie edycji produktu znajdziesz nową sekcję lub zakładkę specjalnie dla „Przed i po - narzędzie do porównywania zdjęć”. Tutaj będziesz mógł:
    -   **Przesłać obraz „Przed”:** Wybierz i prześlij obraz stanu początkowego dla swojego produktu.
    -   **Przesłać obraz „Po”:** Wybierz i prześlij obraz stanu końcowego dla swojego produktu.
    -   **Zapisz:** Po przesłaniu pamiętaj, aby zapisać produkt, aby zastosować zmiany.
-   **Wpływ zmian:**
    -   *Dodawanie obrazów:* Po przesłaniu zarówno obrazu „Przed”, jak i „Po” dla konkretnego produktu i zapisaniu, interaktywny suwak porównania automatycznie pojawi się na stronie front-office tego produktu.
    -   *Usuwanie obrazów:* Jeśli usuniesz jeden lub oba obrazy, suwak porównania nie będzie już wyświetlany dla tego produktu.
    -   *Aktualizacja obrazów:* Zastąpienie obrazów zaktualizuje suwak na front-office.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Dodając nowy produkt, który korzysta z porównania przed/po, najpierw utwórz produkt jak zwykle.
    2.  Przejdź do jego strony edycji.
    3.  Znajdź sekcję „Przed i po”.
    4.  Prześlij swoje obrazy „przed” i „po”. Upewnij się, że mają podobne wymiary, aby uzyskać najlepszy efekt wizualny.
    5.  Zapisz produkt.
    6.  Sprawdź stronę produktu na front-office, aby potwierdzić, że suwak działa zgodnie z oczekiwaniami.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Status modułu | Włączony | Aktywuje/dezaktywuje całą funkcjonalność modułu. |
| Strona edycji produktu | Prześlij obraz „Przed” | N/A | Definiuje obraz stanu początkowego do porównania. |
| Strona edycji produktu | Prześlij obraz „Po” | N/A | Definiuje obraz stanu końcowego do porównania. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Suwak „Przed i po” nie wyświetla się na mojej stronie produktu.**
O1:

-   **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Przed i po - narzędzie do porównywania zdjęć” jest „Włączony”.
-   **Sprawdź obrazy produktu:** Edytuj konkretny produkt (**Katalog > Produkty > Edytuj**) i sprawdź, czy zarówno obraz „Przed”, jak i „Po” zostały przesłane i zapisane w sekcji modułu.
-   **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić wyświetlanie nowej zawartości. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.
-   **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany tak, aby był kompatybilny, niektóre wysoce spersonalizowane motywy mogą wymagać drobnych dostosowań CSS. Jeśli powyższe kroki nie zadziałają, skontaktuj się z pomocą techniczną MyPresta.eu.

**P2: Obrazy wyglądają na zniekształcone lub źle wyrównane w suwaku.**
O2:

-   **Wymiary obrazu:** Aby uzyskać najlepsze rezultaty, upewnij się, że obrazy „Przed” i „Po” mają dokładnie takie same wymiary (szerokość i wysokość). Jeśli znacznie się różnią, suwak może mieć trudności z ich idealnym wyrównaniem.
-   **Jakość obrazu:** Używaj obrazów wysokiej jakości. Obrazy o niskiej rozdzielczości mogą wyglądać na pikselowane po skalowaniu.

**P3: Czy mogę używać tego modułu dla produktów z wieloma wariantami (kombinacjami)?**
O3: Moduł obecnie pozwala ustawić jeden obraz „Przed” i jeden obraz „Po” na produkt, a nie na kombinację. Jeśli Twoje warianty mają różne stany przed/po, być może będziesz musiał utworzyć oddzielne produkty lub użyć głównych obrazów produktu do porównania.

**P4: Jak przetłumaczyć tekst modułu (jeśli taki istnieje) na inne języki?**
O4: Wszelkie etykiety tekstowe wprowadzone przez moduł w Panelu administracyjnym (np. „Prześlij obraz Przed”) można zazwyczaj przetłumaczyć za pomocą wbudowanego systemu tłumaczeń PrestaShop. Przejdź do **Lokalizacja > Tłumaczenia**, wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie znajdź moduł „Przed i po - narzędzie do porównywania zdjęć”, aby edytować jego tłumaczenia.

**P5: Suwak działa, ale nie wygląda dobrze z projektem mojego motywu.**
O5: Często sprowadza się to do stylów CSS. Twój motyw może mieć sprzeczne style. Możesz spróbować zbadać element za pomocą narzędzi deweloperskich przeglądarki, aby zidentyfikować sprzeczne CSS. W przypadku bardziej zaawansowanej personalizacji, możesz potrzebować programisty stron internetowych lub skontaktować się z pomocą techniczną MyPresta.eu w celu uzyskania wskazówek dotyczących nadpisywania domyślnych stylów modułu.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Przed i po - narzędzie do porównywania zdjęć” to standardowy moduł PrestaShop, który stosuje wzorzec podobny do MVC. Głównie rozszerza klasę `Module`, integruje się ze stroną administracji produktami za pomocą hooków i wstrzykuje swoje zasoby front-office oraz szablony do stopki strony produktu. Wykorzystuje zewnętrzne wtyczki jQuery (`jquery.event.move.js`, `jquery.twentytwenty.js`) do interaktywnej funkcjonalności suwaka.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie używa dedykowanych kontrolerów front-office ani back-office. Cała logika jest obsługiwana w głównej klasie modułu i za pośrednictwem hooków.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani `ObjectModel`s. Przechowuje swoją konfigurację bezpośrednio w `ps_configuration` oraz ścieżki obrazów specyficznych dla produktu jako atrybuty produktu lub wartości konfiguracyjne, zarządzane za pomocą hooka `displayAdminProductsExtra`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł zawiera kilka plików JavaScript, głównie dla suwaka porównania obrazów „TwentyTwenty”. Są one ładowane w front-office.

-   **`beforeafter/js/jquery.event.move.js`**
    -   **Zakres:** Front-office.
    -   **Cel:** Lekka wtyczka jQuery, która zapewnia obsługę zdarzeń dotykowych i myszy do przeciągania elementów. Jest to zależność dla `jquery.twentytwenty.js`.
    -   **Szczegóły:** Wiąże zdarzenia takie jak `move`, `movestart`, `moveend`, aby umożliwić funkcję przeciągania.
-   **`beforeafter/js/jquery.twentytwenty.js`**
    -   **Zakres:** Front-office.
    -   **Cel:** Podstawowa wtyczka jQuery, która implementuje suwak porównania obrazów „TwentyTwenty”.
    -   **Szczegóły:** Inicjalizuje suwak na określonych elementach, obsługuje wizualne renderowanie obrazów przed/po i zarządza interaktywnym dzielnikiem na podstawie `jquery.event.move.js`. Zazwyczaj celuje w kontener z dwoma tagami `img` w środku.
-   **`beforeafter/js/twentytwenty.js`**
    -   **Zakres:** Front-office.
    -   **Cel:** Ten plik prawdopodobnie zawiera specyficzną logikę inicjalizacji modułu dla wtyczki `jquery.twentytwenty.js`, stosując ją do prawidłowych elementów na stronie produktu.
    -   **Szczegóły:** Będzie zawierał selektory jQuery do identyfikacji elementu `div` otaczającego obrazy przed/po i wywoła na nim metodę `.twentytwenty()`, potencjalnie z opcjami konfiguracji.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zawiera pliki CSS do stylizacji suwaka porównania obrazów i jego komponentów.

-   **`beforeafter/css/foundation.css`**
    -   **Zakres:** Front-office.
    -   **Cel:** Ten plik prawdopodobnie zawiera podstawowe style resetujące lub podstawowe, być może podzbiór frameworka Zurb Foundation, aby zapewnić spójne renderowanie elementów suwaka. Może definiować podstawowe style siatki, typografii lub formularzy, których używa moduł.
    -   **Kluczowe selektory:** Mogą obejmować ogólne style `div`, `img`, `button` lub specyficzne klasy, takie jak `.row`, `.column`.
-   **`beforeafter/css/twentytwenty.css`**
    -   **Zakres:** Front-office.
    -   **Cel:** Zawiera specyficzną stylizację wymaganą dla samego suwaka porównania obrazów „TwentyTwenty”.
    -   **Kluczowe selektory:** Zdefiniuje wygląd kontenera suwaka, uchwytu dzielnika, nakładki oraz pozycjonowanie obrazów „przed” i „po”. Przykłady: `.twentytwenty-container`, `.twentytwenty-overlay`, `.twentytwenty-handle`, `.twentytwenty-before`, `.twentytwenty-after`. Deweloperzy mogą nadpisać te klasy w pliku `custom.css` lub `theme.css` swojego motywu, aby dopasować je do projektu swojego sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `beforeafter/views/templates/front/hook/displayFooter.tpl`
        -   **Hook:** `displayFooter` (lub potencjalnie `displayFooterProduct` w zależności od wewnętrznej logiki).
        -   **Cel:** Ten szablon jest odpowiedzialny za renderowanie rzeczywistej struktury HTML dla suwaka porównania obrazów „Przed i Po” na front-office. Będzie zawierał elementy `div`, które JavaScript będzie celował, aby zainicjalizować wtyczkę `twentytwenty`, w tym tagi `img` dla obrazów „przed” i „po”. Prawdopodobnie zawiera również niezbędne ładowanie zasobów JavaScript i CSS.
    -   `beforeafter/views/templates/front/hook/displayFooterCms.tpl`
        -   **Hook:** Prawdopodobnie `displayFooter` lub `displayFooterProduct`, ale potencjalnie z logiką warunkową dla stron CMS.
        -   **Cel:** Ten szablon może być rezerwowym lub alternatywnym rozwiązaniem do renderowania suwaka na stronach CMS, chociaż opis modułu koncentruje się na stronach produktów. Jego zawartość byłaby podobna do `displayFooter.tpl`.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `beforeafter/views/templates/admin/displayAdminProductsExtra.tpl`
        -   **Hook:** `displayAdminProductsExtra`
        -   **Cel:** Ten szablon renderuje niestandardowe pola wejściowe i formularze przesyłania w ramach strony edycji produktu PrestaShop w Panelu administracyjnym. Zapewnia interfejs dla administratorów do przesyłania i zarządzania obrazami „Przed” i „Po” dla każdego produktu. Będzie zawierał elementy formularza (np. `input type="file"`) i potencjalnie wyświetlał miniatury już przesłanych obrazów.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne (takie jak `BA_TEST`) w tabeli `ps_configuration`.
    -   Ścieżki obrazów „przed” i „po” specyficzne dla produktu są prawdopodobnie przechowywane jako wartości konfiguracyjne lub atrybuty specyficzne dla produktu, zarządzane za pomocą hooka `displayAdminProductsExtra` oraz metod `install()` i `uninstall()` modułu.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionProductUpdate` | Po zaktualizowaniu produktu w Panelu administracyjnym. | Służy do zapisywania ścieżek obrazów „przed” i „po” przesłanych za pośrednictwem strony edycji produktu. |
| `displayFooterProduct` | Renderuje zawartość w sekcji stopki strony produktu. | Służy do wyświetlania suwaka porównania obrazów „Przed i Po” na stronie produktu front-office. |
| `displayAdminProductsExtra` | Renderuje dodatkową zawartość na stronie edycji produktu w Panelu administracyjnym. | Służy do wstrzykiwania niestandardowych pól formularza do przesyłania obrazów „przed” i „po” do interfejsu administracji produktami. |
| `actionAdminControllerSetMedia` | Przed renderowaniem widoku przez kontroler administracyjny, umożliwiając modułom dodawanie JS/CSS. | Służy do ładowania niezbędnych plików JavaScript (`jquery.event.move.js`, `jquery.twentytwenty.js`, `twentytwenty.js`) i CSS (`foundation.css`, `twentytwenty.css`) dla modułu w Panelu administracyjnym (jeśli potrzebne dla strony produktu administracyjnego) i potencjalnie front-office. |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` stron front-office. | Służy do ładowania niezbędnych plików JavaScript i CSS dla suwaka „Przed i Po” na front-office, zapewniając ich dostępność przed renderowaniem HTML suwaka przez hook `displayFooterProduct`. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnego wsparcia, aktualizacji i wszelkiej dalszej pomocy z modułem „Przed i po - narzędzie do porównywania zdjęć”, prosimy odnieść się do swojego konta klienta MyPresta.eu. Najnowsze wersje modułu, dokumentację i możliwość bezpośredniego kontaktu z naszym zespołem wsparcia znajdziesz na stronie MyPresta.eu.
