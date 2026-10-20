---
title: "Zdjęcia produktów na listach produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop „Zdjęcia produktów na listach produktów” od MyPresta.eu."
sidebar:
  label: "Zdjęcia produktów na listach produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product pictures on product listings na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-pictures-on-product-listings.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-pictures-on-product-listings/)
>
> ---


# Zdjęcia produktów na listach produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są wymagane dla samego PrestaShop i zazwyczaj dostępne we wszystkich nowoczesnych środowiskach hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest główny ekran konfiguracji modułu „Zdjęcia produktów na listach produktów”. Możesz uzyskać do niego dostęp, przechodząc do **Moduły > Menedżer modułów** i klikając „Konfiguruj” obok nazwy modułu.

#### **Pozycja modułu**

-   **Co robi to ustawienie:** Określa, gdzie dodatkowe zdjęcia produktów będą wyświetlane w stosunku do głównego zdjęcia produktu na stronach list.
-   **Efekt zmiany tego ustawienia:**
    *   *displayProductAdditionalInfo:* Zdjęcia pojawią się w typowym haku często używanym do dodatkowych szczegółów produktu.
    *   *displayAfterProductThumbs:* Zdjęcia pojawią się natychmiast po miniaturach głównego zdjęcia produktu (jeśli Twój motyw je wyświetla).
    *   *displayFooterProduct:* Zdjęcia pojawią się w sekcji stopki bloku produktu na stronie listy.
    *   *displayProductDeliveryTime:* Zdjęcia pojawią się w pobliżu informacji o czasie dostawy (jeśli Twój motyw je wyświetla).
    *   *displayHeader:* Jest to mniej typowa pozycja dla zdjęć produktów na stronach list i może wymagać niestandardowego stylizowania, aby dobrze wyglądać.
    *   *displayProductListReviews:* Zdjęcia pojawią się w pobliżu gwiazdek lub liczby recenzji produktów (jeśli Twój motyw je wyświetla).
-   **Zalecana wartość:** Najpierw eksperymentuj z `displayProductAdditionalInfo` lub `displayAfterProductThumbs`, ponieważ są to zazwyczaj dobre miejsca wizualne.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój motyw ma przejrzysty układ i chcesz, aby zdjęcia były subtelnie zintegrowane pod głównym zdjęciem, `displayProductAdditionalInfo` może być najlepsze. Jeśli chcesz, aby bardziej się wyróżniały, `displayFooterProduct` może zadziałać.

#### **Wygląd modułu**

-   **Co robi to ustawienie:** Pozwala wybrać między różnymi stylami wizualnymi dla wyjścia modułu, głównie wpływając na sposób prezentacji miniatur.
-   **Efekt zmiany tego ustawienia:**
    *   *Motyw klasyczny:* Stosuje stylizację, która jest często kompatybilna ze starszymi motywami PrestaShop lub motywami naśladującymi klasyczny wygląd.
    *   *Uniwersalny:* Stosuje bardziej nowoczesny, responsywny projekt, który ma dobrze działać w szerszym zakresie współczesnych motywów.
-   **Zalecana wartość:** `Uniwersalny` dla większości nowoczesnych sklepów PrestaShop (1.7.x, 8.x, 9.x). Użyj `Motyw klasyczny`, jeśli masz starszy lub mocno dostosowany motyw, który nie renderuje `Uniwersalny` poprawnie.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój sklep używa domyślnego motywu PrestaShop 8, `Uniwersalny` prawdopodobnie zintegruje się bezproblemowo. Jeśli używasz PrestaShop 1.6 z niestandardowym motywem, `Motyw klasyczny` może być bezpieczniejszym wyborem.

#### **Metoda wyświetlania**

-   **Co robi to ustawienie:** Kontroluje, które dodatkowe zdjęcia są wyświetlane dla każdego produktu na stronie listy.
-   **Efekt zmiany tego ustawienia:**
    *   *Zdjęcia dla kombinacji kolorów:* Wyświetla tylko zdjęcia specjalnie powiązane z atrybutami kolorów produktu. Przydatne dla mody lub produktów z wyraźnymi wariantami kolorystycznymi.
    *   *Zdjęcia dla każdej kombinacji:* Wyświetla zdjęcia dla wszystkich kombinacji produktów (np. rozmiar, kolor, materiał). Może to prowadzić do wielu zdjęć, jeśli masz wiele kombinacji.
    *   *Wszystkie zdjęcia produktu:* Wyświetla wszystkie zdjęcia powiązane z produktem, niezależnie od kombinacji. Jest to najbardziej kompleksowa opcja.
-   **Zalecana wartość:** `Wszystkie zdjęcia produktu` dla większości ogólnych produktów. `Zdjęcia dla kombinacji kolorów`, jeśli Twoje produkty w dużej mierze opierają się na wariantach kolorystycznych i chcesz utrzymać liczbę zdjęć na rozsądnym poziomie.
-   **Scenariusz/przykład dla sprzedawcy:** Dla sklepu odzieżowego, wybranie `Zdjęcia dla kombinacji kolorów` pokazałoby wszystkie dostępne kolory dla konkretnego t-shirtu. Dla sklepu meblowego, `Wszystkie zdjęcia produktu` pokazałoby różne kąty i zbliżenia sofy.

#### **Tylko w magazynie**

-   **Co robi to ustawienie:** Ta opcja filtruje wyświetlane obrazy na podstawie dostępności produktu w magazynie.
-   **Efekt zmiany tego ustawienia:**
    *   *Włączone:* Wyświetla tylko obrazy dla kombinacji produktów, które są aktualnie w magazynie. Jeśli konkretny kolor jest niedostępny, jego powiązane obrazy nie pojawią się.
    *   *Wyłączone:* Wyświetla wszystkie wybrane obrazy, niezależnie od statusu magazynowego.
-   **Zalecana wartość:** `Włączone`, aby uniknąć pokazywania klientom obrazów produktów, których nie mogą natychmiast kupić, co może prowadzić do frustracji.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz buty i konkretna kombinacja rozmiaru/koloru jest niedostępna, włączenie tej opcji zapobiega wyświetlaniu klientom obrazów tego konkretnego wariantu, kierując ich do dostępnych opcji.

#### **Wyświetlaj pola kolorów zamiast zdjęć**

-   **Co robi to ustawienie:** Zamiast wyświetlać małe miniatury zdjęć, ta opcja wyświetla próbki kolorów (pola) dla kombinacji produktów.
-   **Efekt zmiany tego ustawienia:**
    *   *Włączone:* Zastępuje miniatury zdjęć małymi polami kolorów, zazwyczaj używając koloru zdefiniowanego dla atrybutu produktu.
    *   *Wyłączone:* Wyświetla rzeczywiste miniatury zdjęć.
-   **Zalecana wartość:** `Wyłączone`, jeśli chcesz pokazać rzeczywiste zdjęcia produktów. `Włączone`, jeśli Twoje produkty mają wyraźne atrybuty kolorów i preferujesz czystszy, bardziej kompaktowy wygląd dla wyboru koloru.
-   **Scenariusz/przykład dla sprzedawcy:** Dla sklepu z farbami, włączenie tej opcji pokazałoby małe kolorowe kwadraty reprezentujące różne kolory farb, co jest bardziej efektywne niż pokazywanie maleńkiego zdjęcia każdego koloru.

#### **Główny kontener produktu na liście produktów**

-   **Co robi to ustawienie:** Jest to ustawienie techniczne, które pomaga modułowi zidentyfikować główny kontener dla każdego produktu na stronach list. Wymaga selektora CSS.
-   **Efekt zmiany tego ustawienia:** Jeśli ustawione nieprawidłowo, moduł może nie być w stanie znaleźć miejsca, w którym ma wstrzyknąć dodatkowe obrazy, lub może wstrzyknąć je w niewłaściwym miejscu.
-   **Zalecana wartość:** Zależy to całkowicie od Twojego motywu. Typowe wartości to `.product-miniature`, `.product-container` lub `.ajax_block_product`. Może być konieczne sprawdzenie kodu HTML Twojego motywu, aby znaleźć prawidłowy selektor.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój motyw używa `<div class="product-item">` dla każdego produktu, wpisałbyś tutaj `.product-item`.

#### **CSS zdjęcia okładki produktu**

-   **Co robi to ustawienie:** Jest to ustawienie techniczne, które pomaga modułowi zidentyfikować główny element zdjęcia produktu w każdym kontenerze produktu. Wymaga selektora CSS.
-   **Efekt zmiany tego ustawienia:** Jeśli ustawione nieprawidłowo, moduł nie będzie w stanie przełączyć głównego zdjęcia produktu po kliknięciu/najechaniu na miniaturę.
-   **Zalecana wartość:** Zależy to od Twojego motywu. Typowe wartości to `.product-thumbnail`, `.img-fluid` lub `img.replace-me`. Może być konieczne sprawdzenie kodu HTML Twojego motywu.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli główne zdjęcie produktu w Twoim motywie ma klasę `product-image-thumb`, wpisałbyś tutaj `.product-image-thumb`.

#### **CSS kotwicy zdjęcia okładki produktu**

-   **Co robi to ustawienie:** Jest to ustawienie techniczne, które pomaga modułowi zidentyfikować link (tag kotwicy), który otacza główne zdjęcie produktu. Jest to ważne dla zapewnienia, że link nadal działa poprawnie po przełączeniu obrazu.
-   **Efekt zmiany tego ustawienia:** Jeśli ustawione nieprawidłowo, kliknięcie głównego zdjęcia produktu może nie prowadzić do strony produktu, lub przełączanie obrazu może się nie powieść.
-   **Zalecana wartość:** Zależy to od Twojego motywu. Typowe wartości to `.product-thumbnail a`, `.product-image a` lub `a.product-cover`. Może być konieczne sprawdzenie kodu HTML Twojego motywu.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój motyw otacza główne zdjęcie produktu w `<a class="product-link">`, wpisałbyś tutaj `a.product-link`.

#### **Kotwica tytułu produktu**

-   **Co robi to ustawienie:** Jest to ustawienie techniczne do identyfikacji linku (tagu kotwicy) wokół tytułu produktu.
-   **Efekt zmiany tego ustawienia:** To ustawienie pomaga modułowi zapewnić, że link tytułu produktu pozostaje funkcjonalny i prawidłowo wskazuje na stronę produktu.
-   **Zalecana wartość:** Zależy to od Twojego motywu. Typowe wartości to `.product-title a`, `.product-name a` lub `h3 a`. Może być konieczne sprawdzenie kodu HTML Twojego motywu.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli tytuły Twoich produktów są otoczone w `<h3 class="product-name"><a href="...">`, wpisałbyś tutaj `h3.product-name a`.

#### **Dodatkowa klasa dla kotwicy miniatury**

-   **Co robi to ustawienie:** Pozwala dodać dodatkową klasę CSS do tagów kotwicy miniaturowych obrazów wyświetlanych przez moduł. Jest to przydatne do niestandardowego stylizowania.
-   **Efekt zmiany tego ustawienia:** Określona klasa zostanie dodana do kodu HTML linków miniaturowych obrazów, co pozwoli Ci na ich celowanie za pomocą niestandardowych reguł CSS w Twoim motywie.
-   **Zalecana wartość:** Pozostaw puste, chyba że masz specyficzne wymagania dotyczące niestandardowego stylizowania.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz dodać specjalną ramkę do swoich miniaturowych obrazów, możesz wpisać tutaj `my-custom-miniature-class`, a następnie dodać CSS, takie jak `.my-custom-miniature-class img { border: 1px solid blue; }` do swojego motywu.

#### **Metoda przełączania zdjęć**

-   **Co robi to ustawienie:** Kontroluje, jak zmienia się główne zdjęcie produktu, gdy klient wchodzi w interakcję z dodatkowymi miniaturami.
-   **Efekt zmiany tego ustawienia:**
    *   *Po kliknięciu:* Główne zdjęcie zmienia się tylko, gdy klient kliknie miniaturę.
    *   *Po najechaniu kursorem:* Główne zdjęcie zmienia się, gdy klient przesunie kursor myszy nad miniaturę (bez klikania).
    *   *Slider:* Moduł wyświetla mały slider ze strzałkami nawigacyjnymi, umożliwiając klientom przewijanie zdjęć. Często oznacza to zachowanie „po kliknięciu” dla elementów sterujących slidera.
-   **Zalecana wartość:** `Po najechaniu kursorem` dla szybkiego, interaktywnego doświadczenia. `Po kliknięciu`, jeśli preferujesz wyraźne działanie użytkownika. `Slider`, jeśli masz wiele zdjęć i chcesz bardziej kompaktowej prezentacji.
-   **Scenariusz/przykład dla sprzedawcy:** Dla sklepu odzieżowego, `Po najechaniu kursorem` pozwala klientom szybko podglądać różne stylizacje. Dla produktu z wieloma szczegółowymi zdjęciami, `Slider` może utrzymać stronę listy w czystości, jednocześnie oferując pełny dostęp do wszystkich wizualizacji.

#### **Zdjęcia dla kombinacji kolorów (ustawienie zduplikowane, prawdopodobnie błąd lub dziedzictwo)**

-   **Co robi to ustawienie:** Wydaje się być duplikatem ustawienia „Metoda wyświetlania”, szczególnie w odniesieniu do wyświetlania zdjęć dla kombinacji kolorów.
-   **Efekt zmiany tego ustawienia:** Najlepiej polegać na ustawieniu „Metoda wyświetlania” dla tej funkcjonalności. Jeśli jest to oddzielna kontrola, może ona nadpisywać lub kolidować z ustawieniem „Metoda wyświetlania”.
-   **Zalecana wartość:** Zapewnij spójność z ustawieniem „Metoda wyświetlania”.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli „Metoda wyświetlania” jest ustawiona na „Zdjęcia dla kombinacji kolorów”, to ustawienie również powinno być włączone lub spójne.

#### **Zdjęcia dla każdej kombinacji (ustawienie zduplikowane, prawdopodobnie błąd lub dziedzictwo)**

-   **Co robi to ustawienie:** Podobnie jak powyżej, wydaje się być duplikatem ustawienia „Metoda wyświetlania”, szczególnie w odniesieniu do wyświetlania zdjęć dla wszystkich kombinacji.
-   **Efekt zmiany tego ustawienia:** Najlepiej polegać na ustawieniu „Metoda wyświetlania”.
-   **Zalecana wartość:** Zapewnij spójność z ustawieniem „Metoda wyświetlania”.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli „Metoda wyświetlania” jest ustawiona na „Zdjęcia dla każdej kombinacji”, to ustawienie również powinno być włączone lub spójne.

#### **Wszystkie zdjęcia produktu (ustawienie zduplikowane, prawdopodobnie błąd lub dziedzictwo)**

-   **Co robi to ustawienie:** Podobnie jak powyżej, wydaje się być duplikatem ustawienia „Metoda wyświetlania”, szczególnie w odniesieniu do wyświetlania wszystkich zdjęć produktu.
-   **Efekt zmiany tego ustawienia:** Najlepiej polegać na ustawieniu „Metoda wyświetlania”.
-   **Zalecana wartość:** Zapewnij spójność z ustawieniem „Metoda wyświetlania”.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli „Metoda wyświetlania” jest ustawiona na „Wszystkie zdjęcia produktu”, to ustawienie również powinno być włączone lub spójne.

#### **Tabela szybkiego odniesienia konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Pozycja modułu | `displayProductAdditionalInfo` | Określa, gdzie dodatkowe zdjęcia pojawiają się na listach produktów. |
| Konfiguracja modułu | Wygląd modułu | `Uniwersalny` | Ustawia styl wizualny dla miniatur zdjęć (Klasyczny vs. Nowoczesny). |
| Konfiguracja modułu | Metoda wyświetlania | `Wszystkie zdjęcia produktu` | Kontroluje, które zdjęcia są wyświetlane (kombinacje kolorów, wszystkie kombinacje lub wszystkie zdjęcia produktu). |
| Konfiguracja modułu | Tylko w magazynie | `Włączone` | Filtruje zdjęcia, aby wyświetlać tylko dla kombinacji produktów dostępnych w magazynie. |
| Konfiguracja modułu | Wyświetlaj pola kolorów zamiast zdjęć | `Wyłączone` | Zastępuje miniatury zdjęć próbkami kolorów, jeśli włączone. |
| Konfiguracja modułu | Główny kontener produktu na liście produktów | `.product-miniature` (lub specyficzny dla motywu) | Selektor CSS dla głównego bloku produktu na stronach list. |
| Konfiguracja modułu | CSS zdjęcia okładki produktu | `.product-thumbnail` (lub specyficzny dla motywu) | Selektor CSS dla głównego elementu zdjęcia produktu. |
| Konfiguracja modułu | CSS kotwicy zdjęcia okładki produktu | `.product-thumbnail a` (lub specyficzny dla motywu) | Selektor CSS dla linku otaczającego główne zdjęcie produktu. |
| Konfiguracja modułu | Kotwica tytułu produktu | `h3 a` (lub specyficzny dla motywu) | Selektor CSS dla linku otaczającego tytuł produktu. |
| Konfiguracja modułu | Dodatkowa klasa dla kotwicy miniatury | Pozostaw puste | Dodaje niestandardową klasę CSS do linków miniaturowych obrazów do stylizacji. |
| Konfiguracja modułu | Metoda przełączania zdjęć | `Po najechaniu kursorem` | Definiuje, jak zmienia się główne zdjęcie (kliknięcie, najechanie kursorem lub slider). |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Dodatkowe zdjęcia nie wyświetlają się na moich listach produktów.**

-   **Odp.:** Najpierw sprawdź konfigurację modułu:
    *   Upewnij się, że „Pozycja modułu” jest ustawiona na hak, który Twój motyw faktycznie renderuje (np. `displayProductAdditionalInfo`). Jeśli Twój motyw jest mocno dostosowany, może być konieczne wypróbowanie różnych pozycji lub skonsultowanie się z programistą.
    *   Zweryfikuj ustawienia „Główny kontener produktu na liście produktów”, „CSS zdjęcia okładki produktu”, „CSS kotwicy zdjęcia okładki produktu” i „Kotwica tytułu produktu”. Są to kluczowe selektory CSS, które muszą pasować do struktury HTML Twojego motywu. Użyj narzędzi deweloperskich przeglądarki (F12), aby zbadać elementy na stronie kategorii i znaleźć prawidłowe klasy/ID.
    *   Upewnij się, że produkty faktycznie mają wiele zdjęć przesłanych w ich ustawieniach produktu w Panelu administracyjnym.
-   **Odp.:** Wyczyść pamięć podręczną PrestaShop: Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Wyczyść również pamięć podręczną przeglądarki.

**P2: Zdjęcia pojawiają się, ale nie przełączają się po najechaniu kursorem/kliknięciu.**

-   **Odp.:** Zazwyczaj wskazuje to na problem z selektorami CSS dla głównego zdjęcia produktu lub jego kontenera.
    *   Sprawdź ponownie „CSS zdjęcia okładki produktu” i „CSS kotwicy zdjęcia okładki produktu”. Muszą one dokładnie wskazywać główne zdjęcie i jego otaczający link.
    *   Upewnij się, że na Twojej stronie nie ma błędów JavaScript, które mogłyby uniemożliwić działanie skryptu modułu. Sprawdź konsolę deweloperską przeglądarki (F12 > zakładka Konsola).
    *   Jeśli masz inne moduły, które modyfikują listy produktów, może wystąpić konflikt. Spróbuj tymczasowo wyłączyć inne moduły front-office, aby wyizolować problem.

**P3: Zdjęcia wyglądają zniekształcone lub stylizacja jest nieprawidłowa.**

-   **Odp.:**
    *   Spróbuj przełączyć ustawienie „Wygląd modułu” między `Motyw klasyczny` a `Uniwersalny`, aby sprawdzić, czy któryś z nich lepiej integruje się z Twoim motywem.
    *   Twój motyw może mieć sprzeczne reguły CSS. Możesz użyć ustawienia „Dodatkowa klasa dla kotwicy miniatury”, aby dodać niestandardową klasę, a następnie użyć niestandardowego CSS w swoim motywie, aby nadpisać sprzeczne style.
    *   Upewnij się, że przesłane zdjęcia produktów są spójnej jakości i proporcji.

**P4: Używam niestandardowego motywu, a moduł w ogóle nie działa.**

-   **Odp.:** Niestandardowe motywy często używają innych struktur HTML i klas CSS niż domyślne motywy PrestaShop.
    *   Prawie na pewno będziesz musiał dostosować selektory CSS dla „Głównego kontenera produktu na liście produktów”, „CSS zdjęcia okładki produktu”, „CSS kotwicy zdjęcia okładki produktu” i „Kotwicy tytułu produktu”, aby pasowały do specyficznego kodu Twojego motywu. Zazwyczaj wymaga to podstawowej znajomości inspekcji HTML/CSS za pomocą narzędzi deweloperskich przeglądarki.
    *   Twój niestandardowy motyw może nie wywoływać standardowych haków PrestaShop, których używa moduł. Może być konieczne ręczne dodanie wywołań haków modułu do plików `.tpl` Twojego motywu (skonsultuj się z deweloperem motywu lub deweloperem PrestaShop w tej sprawie).

**P5: Moduł spowalnia ładowanie mojej strony.**

-   **Odp.:** Chociaż moduł jest zoptymalizowany, wyświetlanie wielu dodatkowych zdjęć może naturalnie wydłużyć czas ładowania strony.
    *   Upewnij się, że Twoje zdjęcia produktów są zoptymalizowane pod kątem sieci (skompresowane, odpowiednie wymiary).
    *   Rozważ użycie opcji „Tylko w magazynie”, aby zmniejszyć liczbę ładowanych zdjęć dla produktów niedostępnych w magazynie.
    *   Jeśli masz wiele zdjęć na produkt, rozważ użycie metody `Slider`, która często ładuje zdjęcia bardziej efektywnie lub leniwie.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu „Zdjęcia produktów na listach produktów”, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł `productlistpics` jest przede wszystkim modułem funkcji front-office, zaprojektowanym do wstrzykiwania dodatkowej funkcjonalności obrazów produktów do istniejących szablonów list produktów. Wykorzystuje system haków PrestaShop do renderowania swojej zawartości i używa JavaScript do obsługi dynamicznego przełączania obrazów (najechanie/kliknięcie) lub funkcjonalności slidera. Konfiguracja jest zarządzana za pomocą standardowej metody `getContent()` w głównej klasie modułu, przechowując ustawienia w `ps_configuration`. Moduł nie wprowadza niestandardowych tabel baz danych ani złożonych encji `ObjectModel`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała logika jest hermetyzowana w głównej klasie modułu oraz powiązanych z nią szablonach i zasobach.

### 4.3 Klasy i modele rdzenia (`classes/`)

Ten moduł **nie** zawiera żadnych niestandardowych klas ani encji `ObjectModel` w katalogu `classes/`. Cała logika rdzenia znajduje się w `productlistpics.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł zawiera kilka plików JavaScript, głównie do obsługi przełączania obrazów i funkcjonalności slidera.

-   `productlistpics/js/owl-carousel/owl.carousel.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Jest to podstawowa biblioteka Owl Carousel, popularna wtyczka jQuery z obsługą dotyku do responsywnych karuzel. Zapewnia podstawową funkcjonalność do tworzenia sliderów obrazów.
-   `productlistpics/js/owl-carousel/owl.run.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Ten skrypt prawdopodobnie zawiera kod inicjalizacji i konfiguracji instancji Owl Carousel używanych przez moduł. Ustawia zachowanie slidera, responsywność i opcje nawigacji na podstawie ustawień modułu.
-   `productlistpics/js/plp-replacement.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Ten skrypt jest prawdopodobnie odpowiedzialny za podstawową logikę zastępowania głównego obrazu produktu, gdy miniatura jest interaktywna. Nasłuchuje zdarzeń (kliknięcie/najechanie) na wygenerowanych miniaturach i aktualizuje atrybuty `src` i `srcset` głównego obrazu produktu, potencjalnie również aktualizując `href` tagu kotwicy głównego obrazu.
-   `productlistpics/js/productlistpics-mouseover.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Ten skrypt konkretnie implementuje metodę przełączania obrazów „Po najechaniu kursorem”. Dołącza słuchacze zdarzeń `mouseover` i `mouseout` do kotwic miniaturowych obrazów, aby wywołać zastąpienie głównego obrazu.
-   `productlistpics/js/productlistpics.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Jest to prawdopodobnie główny punkt wejścia JavaScript modułu front-office. Może obsługiwać metodę przełączania obrazów „Po kliknięciu”, ogólną manipulację DOM związaną z wstrzykiwaniem miniatur i potencjalnie orkiestrowanie ładowania innych skryptów na podstawie konfiguracji.
-   `productlistpics/js/slider-productlistpics-mouseover.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Ten skrypt łączy funkcjonalność slidera z przełączaniem obrazów opartym na najechaniu kursorem. Prawdopodobnie zainicjuje Owl Carousel, a następnie doda słuchacze najechania kursorem do elementów slidera, aby zaktualizować główne zdjęcie produktu.
-   `productlistpics/js/slider-productlistpics.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Ten skrypt integruje slider Owl Carousel z przełączaniem obrazów opartym na kliknięciu. Inicjuje slider i obsługuje kliknięcia na elementach slidera, aby zaktualizować główne zdjęcie produktu.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zawiera kilka plików CSS do stylizacji wstrzykiwanych elementów i Owl Carousel.

-   `productlistpics/css.css`:
    *   **Zakres:** Front-office.
    *   **Opis:** Ogólna stylizacja elementów modułu, takich jak kontener na dodatkowe zdjęcia, rozmiar miniatur i podstawowy układ.
-   `productlistpics/js/owl-carousel/owl.carousel.css`:
    *   **Zakres:** Front-office.
    *   **Opis:** Podstawowe style dla wtyczki Owl Carousel, definiujące strukturę i domyślny wygląd slidera.
-   `productlistpics/js/owl-carousel/owl.theme.css`:
    *   **Zakres:** Front-office.
    *   **Opis:** Domyślny motyw dla Owl Carousel, zapewniający wizualną stylizację przycisków nawigacyjnych, kropek i ogólnej estetyki slidera.
-   `productlistpics/js/owl-carousel/owl.transitions.css`:
    *   **Zakres:** Front-office.
    *   **Opis:** CSS dla różnych efektów przejścia używanych przez Owl Carousel (np. zanikanie, przesuwanie).
-   `productlistpics/productlistpics-classic.css`:
    *   **Zakres:** Front-office.
    *   **Opis:** Specyficzne reguły stylizacji stosowane, gdy w konfiguracji modułu wybrano opcję projektową „Motyw klasyczny”. Dotyczy to starszych motywów PrestaShop lub motywów naśladujących klasyczny wygląd.
-   `productlistpics/productlistpics.css`:
    *   **Zakres:** Front-office.
    *   **Opis:** Główna stylizacja modułu, prawdopodobnie zawierająca reguły dla opcji projektowej „Uniwersalny” oraz ogólne nadpisania lub ulepszenia.

**Kluczowe selektory klas CSS, które programiści mogą nadpisać:**

-   `.productlistpics-container`: Główny wrapper dla dodatkowych obrazów.
-   `.productlistpics-thumb`: Pojedyncze kontenery miniatur.
-   `.productlistpics-thumb img`: Rzeczywisty obraz w miniaturze.
-   `.owl-carousel`, `.owl-item`, `.owl-nav`, `.owl-dots`: Standardowe selektory Owl Carousel do dostosowywania slidera.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa szablonów Smarty do renderowania swojej zawartości w różnych hakach PrestaShop.

-   **Szablony haków (`views/templates/hook/`)**:
    *   `productlistpics/header.tpl`:
        *   **Hak:** `displayHeader` (lub podobny, zazwyczaj rejestrowany w `install()`).
        *   **Wyjście:** Ten szablon jest odpowiedzialny za dołączenie niezbędnych zasobów CSS i JavaScript, aby moduł działał w front-office. Warunkowo ładuje skrypty na podstawie wybranej „Metody przełączania zdjęć” (np. `owl.carousel.js`, `productlistpics-mouseover.js`, `slider-productlistpics.js`).
    *   `productlistpics/html.tpl`:
        *   **Hak:** Jest to ogólny szablon, który może być dołączany przez inne szablony lub używany do konkretnych bloków treści. Jego dokładne użycie zależy od tego, jak główny plik PHP modułu renderuje zawartość.
        *   **Wyjście:** Zawiera strukturę HTML do wyświetlania dodatkowych zdjęć produktów, w tym pętle do iteracji po zdjęciach i logikę warunkową do wyświetlania pól kolorów lub miniatur zdjęć.
    *   `productlistpics/productFooter.tpl`:
        *   **Hak:** `displayFooterProduct` (zgodnie z konfiguracją w „Pozycji modułu”).
        *   **Wyjście:** Renderuje dodatkowe zdjęcia produktów w sekcji stopki bloku produktu na stronach list. Prawdopodobnie zawiera `html.tpl` lub podobną logikę.
    *   `productlistpics/productPage.tpl`:
        *   **Hak:** Ten szablon jest prawdopodobnie używany dla haków takich jak `displayProductAdditionalInfo`, `displayAfterProductThumbs`, `displayProductDeliveryTime`, `displayProductListReviews` (zgodnie z konfiguracją w „Pozycji modułu”).
        *   **Wyjście:** Renderuje dodatkowe zdjęcia produktów w określonym haku listy produktów. Zawiera podstawową logikę generowania miniatur zdjęć lub pól kolorów oraz ustawiania niezbędnych atrybutów danych dla interakcji JavaScript.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:
    Moduł **nie** tworzy żadnych niestandardowych tabel baz danych. Wszystkie jego ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `PLP_TYPE`, `PLP_INSTOCK`, `PLP_METHOD`, `PLP_SWITCH`, `PLP_DESIGN`, `PLP_POSITION` oraz różnych kluczy selektorów CSS (`pls_product_miniature`, `pls_product_miniature_img` itp.).
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Wstrzykuje zasoby CSS i JavaScript wymagane przez moduł. |
| `displayProductAdditionalInfo` | W bloku miniatury produktu, często poniżej głównego obrazu lub tytułu. | Renderuje dodatkowe miniatury/slider zdjęć produktu. |
| `displayAfterProductThumbs` | Po miniaturach głównego zdjęcia produktu (jeśli są obecne). | Renderuje dodatkowe miniatury/slider zdjęć produktu. |
| `displayFooterProduct` | W obszarze stopki każdego bloku miniatury produktu. | Renderuje dodatkowe miniatury/slider zdjęć produktu. |
| `displayProductDeliveryTime` | W pobliżu informacji o czasie dostawy produktu w miniaturze produktu. | Renderuje dodatkowe miniatury/slider zdjęć produktu. |
| `displayProductListReviews` | W pobliżu gwiazdek/liczby recenzji produktu w miniaturze produktu. | Renderuje dodatkowe miniatury/slider zdjęć produktu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Zdjęcia produktów na listach produktów”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
