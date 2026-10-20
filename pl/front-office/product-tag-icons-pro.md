---
title: "Product Tag Icons Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów dla modułu PrestaShop Product Tag Icons Pro od MyPresta.eu."
sidebar:
  label: "Product Tag Icons Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product Tag Icons Pro na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-tag-icons-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-tag-icons-pro/)
>
> ---


# Product Tag Icons Pro

## 1. Wymagania i Kompatybilność

- **Obsługiwane Wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania Hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane i obecne w większości nowoczesnych środowisk hostingowych. Nie jest wymagana żadna specjalna konfiguracja serwera.

## 2. Kompletny Przewodnik Konfiguracji (Każde Ustawienie Pogrupowane Według Ekranu)

Moduł „Product Tag Icons Pro” oferuje kompleksowy zestaw opcji konfiguracyjnych rozmieszczonych na kilku dedykowanych ekranach w Panelu administracyjnym PrestaShop.

### 2.1 Strona Konfiguracji Modułu (Panel administracyjny > Moduły > Menedżer modułów > Konfiguruj Product Tag Icons Pro)

Jest to główny ekran konfiguracji dla ogólnych ustawień modułu.

- **Co robi to ustawienie:** Kontroluje ogólne zachowanie i domyślne opcje wyświetlania ikon produktów.
- **Wpływ zmiany tego ustawienia:** Te ustawienia wpływają na sposób wyświetlania ikon w całym sklepie lub na interakcję modułu z innymi częściami PrestaShop.
- **Zalecana wartość:** Różni się w zależności od projektu sklepu i pożądanej funkcjonalności.

**Tabela Szybkiego Odniesienia do Konfiguracji (Główna Konfiguracja Modułu)**

| Ustawienie / Opcja | Domyślne / Zalecane | Cel i Wpływ |
| --- | --- | --- |
| **Włącz moduł** | TAK | **Cel:** Włącza lub wyłącza funkcjonalność modułu.   **Wpływ:** Jeśli wyłączony, żadne ikony nie pojawią się w Twoim front office, a funkcje modułu będą nieaktywne. Pozostaw włączony, aby korzystać z modułu. |
| **Rozmiar ikony (px)** | 32 | **Cel:** Ustawia domyślny rozmiar (szerokość i wysokość) dla wszystkich ikon wyświetlanych w front office.   **Wpływ:** Wszystkie ikony będą renderowane w tym określonym rozmiarze pikseli. Wybierz rozmiar, który dobrze pasuje do obrazów produktów i ogólnego projektu, nie będąc zbyt małym, aby go zobaczyć, ani zbyt dużym, aby był inwazyjny. |
| **Pozycja ikony (Hook)** | `displayProductAdditionalInfo` (lub podobny hook strony produktu) | **Cel:** Określa, gdzie na stronie produktu ikony będą wyświetlane domyślnie. Możesz wybrać z listy dostępnych hooków PrestaShop.   **Wpływ:** Ikony pojawią się w wybranej sekcji strony produktu. Eksperymentuj z różnymi hookami, aby znaleźć najlepsze wizualne umiejscowienie dla Twojego motywu. Typowe wybory to `displayProductAdditionalInfo`, `displayProductPriceBlock` lub `displayAfterProductThumbs`. |
| **Pokaż ikony na liście produktów** | TAK | **Cel:** Kontroluje, czy ikony są widoczne na stronach list produktów (kategorie, wyniki wyszukiwania, polecane produkty na stronie głównej).   **Wpływ:** Jeśli włączone, ikony przypisane do produktów pojawią się na ich odpowiednich kartach/miniaturach produktów na listach. Jeśli wyłączone, ikony będą wyświetlane tylko na indywidualnych stronach produktów. Zaleca się włączenie dla maksymalnego efektu. |
| **Typ dymka** | Light | **Cel:** Wybiera wizualny motyw dla dymka, który pojawia się, gdy klient najedzie kursorem na ikonę. Opcje zazwyczaj obejmują Light, Noir, Punk, Shadow.   **Wpływ:** Zmienia wygląd pola dymka (tło, kolor tekstu, obramowanie), które wyświetla opis ikony. Wybierz ten, który pasuje do estetyki Twojego sklepu. |
| **Pozycja dymka** | Top | **Cel:** Określa, gdzie dymek pojawia się względem ikony po najechaniu kursorem (np. Top, Bottom, Left, Right).   **Wpływ:** Wpływa na doświadczenie użytkownika podczas interakcji z ikonami. Wybierz pozycję, która nie zasłania innych ważnych informacji na stronie. |
| **Włącz animacje dymków** | TAK | **Cel:** Dodaje subtelne animacje (zanikanie, przesuwanie) podczas pojawiania się i znikania dymków.   **Wpływ:** Sprawia, że interakcja z dymkiem wydaje się bardziej nowoczesna i angażująca. Jeśli wolisz statyczny, natychmiastowy wygląd, wyłącz tę opcję. |
| **Niestandardowy CSS** | (Puste) | **Cel:** Pozwala dodać niestandardowe reguły CSS do dalszego stylizowania ikon lub dymków bez modyfikowania plików modułu.   **Wpływ:** Wszelkie wprowadzone tutaj reguły CSS zostaną zastosowane do elementów modułu, nadpisując domyślne style. Użyj tego do precyzyjnego dostosowywania kolorów, marginesów lub specyficznych zachowań ikon. |

### 2.2 Dedykowany Ekran Administracyjny: Zarządzaj Wszystkimi Ikonami (Panel administracyjny > Product Tag Icons Pro > Zarządzaj Wszystkimi Ikonami)

Ten ekran pozwala tworzyć, edytować i usuwać definicje ikon, które później będziesz kojarzyć z produktami.

- **Nazwa Ekranu i Lokalizacja w Menu:** Znajdziesz to w **Product Tag Icons Pro > Zarządzaj Wszystkimi Ikonami** w menu Panelu administracyjnego PrestaShop.
- **Dostępne Akcje i Ustawienia:**
  - **Dodaj Nową Ikonę:** Kliknij przycisk „Dodaj nową ikonę”, aby utworzyć nową ikonę.
    - **Nazwa Ikony:** Opisowa nazwa dla Twojej ikony (np. „Darmowa Wysyłka”, „Nowość”). Jest to dla Twojego wewnętrznego odniesienia.
    - **Obraz Ikony:** Prześlij plik obrazu dla Twojej ikony. Powinien to być mały, wyraźny obraz (np. PNG, JPG, SVG).
    - **Opis Ikony:** Krótki tekst, który pojawi się jako dymek, gdy klienci najadą kursorem na ikonę w front office. Wyjaśnij, co oznacza ikona.
    - **Aktywny:** Przełącz, czy ta ikona jest aktualnie dostępna do użycia i wyświetlania.
    - **Pola specyficzne dla języka:** Jeśli Twój sklep jest wielojęzyczny, możesz podać różne nazwy i opisy dla każdego języka.
  - **Edytuj Ikonę:** Kliknij przycisk „Edytuj” obok istniejącej ikony na liście, aby zmodyfikować jej szczegóły.
  - **Usuń Ikonę:** Kliknij przycisk „Usuń”, aby usunąć ikonę. Bądź ostrożny, ponieważ spowoduje to również usunięcie jej powiązań z wszelkimi produktami.
  - **Widok Siatki / Zarządzania:** Tabela zawierająca listę wszystkich utworzonych ikon, pokazująca ich nazwę, obraz, opis i status aktywności. Możesz sortować i filtrować tę listę.
- **Wpływ zmian:**
  - **Dodanie ikony:** Sprawia, że nowa ikona jest dostępna do powiązania z produktami.
  - **Edycja ikony:** Aktualizuje obraz, nazwę lub opis dla wszystkich wystąpień tej ikony w całym sklepie.
  - **Usunięcie ikony:** Całkowicie usuwa ikonę i nie będzie ona już wyświetlana na żadnych produktach, do których była wcześniej przypisana.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. Zaplanuj swoje ikony: Zdecyduj, które kluczowe funkcje lub promocje chcesz wyróżnić.
  2. Utwórz wysokiej jakości, małe obrazy ikon (np. 32x32px lub 64x64px), które pasują do Twojej marki.
  3. Przejdź do „Zarządzaj Wszystkimi Ikonami” i dodaj każdą ikonę, podając jasną nazwę i pomocny opis dymka.
  4. Upewnij się, że wszystkie ikony są „Aktywne”, jeśli zamierzasz ich używać.

### 2.3 Dedykowany Ekran Administracyjny: Zarządzaj Powiązaniami Ikon (Panel administracyjny > Product Tag Icons Pro > Zarządzaj Powiązaniami Ikon)

Ten ekran służy do łączenia utworzonych ikon z konkretnymi produktami w Twoim katalogu.

- **Nazwa Ekranu i Lokalizacja w Menu:** Znajdziesz to w **Product Tag Icons Pro > Zarządzaj Powiązaniami Ikon** w menu Panelu administracyjnego PrestaShop.
- **Dostępne Akcje i Ustawienia:**
  - **Wyszukiwanie Produktów:** Użyj paska wyszukiwania, aby znaleźć produkty według nazwy, ID lub referencji.
  - **Lista Produktów:** Po wyszukaniu produktów pojawią się one na liście.
  - **Przypisz Ikony:** Dla każdego produktu zobaczysz sekcję, w której możesz wybrać, które z utworzonych ikon mają być wyświetlane dla tego konkretnego produktu. Zazwyczaj jest to rozwijana lista wielokrotnego wyboru lub lista pól wyboru.
  - **Zapisz Zmiany:** Po przypisaniu lub odpięciu ikon dla produktu, pamiętaj o zapisaniu zmian.
  - **Widok Siatki / Zarządzania:** Tabela pokazująca produkty i ich aktualnie powiązane ikony.
- **Wpływ zmian:**
  - **Przypisanie ikony do produktu:** Wybrana ikona pojawi się teraz w front office dla tego konkretnego produktu (na jego stronie produktu i na listach produktów, w zależności od głównych ustawień modułu).
  - **Odpięcie ikony od produktu:** Ikona nie będzie już wyświetlana dla tego produktu.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. Po utworzeniu ikon (w „Zarządzaj Wszystkimi Ikonami”), przejdź do tego ekranu.
  2. Wyszukaj produkt, który chcesz otagować.
  3. Wybierz odpowiednie ikony z listy dla tego produktu.
  4. Powtórz dla wszystkich produktów, które chcesz otagować.
  5. Okresowo przeglądaj swoje tagi produktów, zwłaszcza podczas wprowadzania nowych produktów lub promocji.

### 2.4 Tabela Szybkiego Odniesienia do Konfiguracji (Wszystkie Ekrany)

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i Wpływ |
|---|---|---|---|
| **Konfiguracja Modułu** | Włącz moduł | TAK | Włącza/wyłącza moduł. |
| | Rozmiar ikony (px) | 32 | Ustawia domyślny rozmiar wyświetlania ikony. |
| | Pozycja ikony (Hook) | `displayProductAdditionalInfo` | Domyślne umiejscowienie na stronie produktu. |
| | Pokaż ikony na liście produktów | TAK | Wyświetla ikony na stronach kategorii/wyszukiwania. |
| | Typ dymka | Light | Motyw wizualny dla opisów ikon. |
| | Pozycja dymka | Top | Gdzie dymek pojawia się względem ikony. |
| | Włącz animacje dymków | TAK | Płynne animacje dla dymków. |
| | Niestandardowy CSS | (Puste) | Dodaj niestandardowe style dla ikon/dymków. |
| **Zarządzaj Wszystkimi Ikonami** | Dodaj nową ikonę | N/A | Utwórz nową definicję ikony. |
| | Nazwa ikony | (Opisowa) | Wewnętrzna nazwa ikony. |
| | Obraz ikony | (Prześlij plik) | Wizualna reprezentacja ikony. |
| | Opis ikony | (Tekst dymka) | Tekst wyświetlany po najechaniu kursorem. |
| | Aktywny | TAK | Włącz/wyłącz ikonę do użycia. |
| | Edytuj ikonę | N/A | Modyfikuj istniejące szczegóły ikony. |
| | Usuń ikonę | N/A | Usuń definicję ikony. |
| **Zarządzaj Powiązaniami Ikon** | Wyszukiwanie produktów | N/A | Znajdź produkty do otagowania. |
| | Przypisz ikony | N/A | Połącz utworzone ikony z konkretnymi produktami. |
| | Zapisz zmiany | N/A | Zastosuj przypisania ikon do produktów. |

## 3. Rozwiązywanie Problemów dla Sprzedawców i Często Zadawane Pytania (FAQ)

**P1: Moje ikony nie wyświetlają się w front office, co powinienem zrobić?**
O:

1.  **Sprawdź Status Modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Product Tag Icons Pro” jest włączony.
2.  **Sprawdź Status Ikony:** Przejdź do **Product Tag Icons Pro > Zarządzaj Wszystkimi Ikonami** i zweryfikuj, czy konkretne ikony, które próbujesz wyświetlić, są oznaczone jako „Aktywne”.
3.  **Sprawdź Powiązania Produktów:** Przejdź do **Product Tag Icons Pro > Zarządzaj Powiązaniami Ikon** i potwierdź, że ikony są poprawnie przypisane do produktów, na których mają się pojawić.
4.  **Wyczyść Pamięć Podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną Smarty” oraz „Wyczyść pamięć podręczną” (jeśli dostępne). Czasami stare dane z pamięci podręcznej uniemożliwiają wyświetlanie nowych zmian modułu.
5.  **Sprawdź Pozycję Hooka:** W głównej konfiguracji modułu upewnij się, że wybrałeś prawidłowy i odpowiedni hook do wyświetlania ikon (np. `displayProductAdditionalInfo`). Niektóre motywy mogą mieć niestandardowe hooki lub mogą nie renderować niektórych standardowych hooków.

**P2: Ikony wyglądają zbyt duże/małe lub nie pasują do projektu mojego motywu.**
O:

1.  **Dostosuj Rozmiar Ikony:** W głównej konfiguracji modułu zmień ustawienie „Rozmiar ikony (px)” na żądane wymiary.
2.  **Niestandardowy CSS:** Jeśli prosta regulacja rozmiaru nie wystarczy, użyj pola „Niestandardowy CSS” w głównej konfiguracji modułu, aby precyzyjnie dostosować styl. Możesz celować w konkretne klasy ikon (np. `.ticon-image`), aby dostosować marginesy, wypełnienie, a nawet zastosować filtry.
3.  **Kompatybilność z Motywem:** Chociaż moduł jest zaprojektowany tak, aby był kompatybilny, niektóre wysoce spersonalizowane motywy mogą wymagać drobnych korekt CSS. Jeśli czujesz się komfortowo z CSS, sprawdź elementy za pomocą narzędzi deweloperskich przeglądarki, aby zidentyfikować odpowiednie selektory.

**P3: Dymki nie pojawiają się lub wyglądają dziwnie.**
O:

1.  **Włącz Dymki:** Upewnij się, że funkcja dymków jest włączona w głównej konfiguracji modułu.
2.  **Sprawdź Zawartość Dymka:** Zweryfikuj, czy wprowadziłeś „Opis” dla każdej ikony w **Product Tag Icons Pro > Zarządzaj Wszystkimi Ikonami**. Ten opis jest tym, co pojawia się w dymku.
3.  **Motyw/Pozycja Dymka:** Eksperymentuj z różnymi ustawieniami „Typ dymka” i „Pozycja dymka” w głównej konfiguracji modułu, aby sprawdzić, czy inna opcja rozwiąże problem lub będzie lepiej wyglądać z Twoim motywem.
4.  **Konflikty JavaScript:** W rzadkich przypadkach JavaScript innego modułu może powodować konflikt. Sprawdź konsolę deweloperską przeglądarki pod kątem błędów JavaScript. Jeśli znajdziesz błędy, spróbuj tymczasowo wyłączyć inne moduły jeden po drugim, aby wyizolować konflikt.

**P4: Czy mogę przetłumaczyć nazwy i opisy ikon na różne języki?**
O: Tak! Podczas tworzenia lub edytowania ikony w **Product Tag Icons Pro > Zarządzaj Wszystkimi Ikonami** zobaczysz zakładki językowe (np. „Angielski”, „Francuski”, „Hiszpański”) obok pól „Nazwa Ikony” i „Opis Ikony”. Po prostu przełącz się na żądaną zakładkę językową i wprowadź tłumaczenie dla tego konkretnego języka. Moduł automatycznie wyświetli prawidłowe tłumaczenie na podstawie wybranego języka klienta.

## 4. Przewodnik dla Deweloperów i Webmasterów (Architektura Techniczna i Mapa Kodu)

Ta sekcja zawiera szczegółowy przegląd struktury technicznej modułu „Product Tag Icons Pro”, przeznaczony dla deweloperów, webmasterów i agencji technicznych.

### 4.1 Przegląd Architektury

Moduł „Product Tag Icons Pro” (`ticons`) stosuje standardową architekturę modułów PrestaShop, głównie wykorzystując wzorzec MVC. Rozszerza `Module` dla swojej podstawowej funkcjonalności i używa dedykowanych instancji `AdminController` do zarządzania ikonami i ich powiązaniami. Dane są przechowywane w niestandardowych tabelach bazy danych, a wyświetlanie w front-office jest realizowane za pomocą różnych hooków PrestaShop i szablonów Smarty. Moduł integruje również biblioteki stron trzecich dla ulepszonego interfejsu użytkownika (np. Tooltipster dla dymków, niestandardowe autouzupełnianie dla wyszukiwania produktów).

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Ten moduł nie definiuje jawnie niestandardowych kontrolerów front-office. Całe renderowanie front-office jest obsługiwane za pomocą metod `hook` w głównej klasie modułu (`ajax_ticons.php`) i powiązanych szablonach Smarty.

#### Kontrolery Administracyjne Back-Office

-   **`ticons/controllers/admin/AdminTiconsAllController.php`**
    -   **Nazwa Klasy:** `AdminTiconsAllController` (rozszerza `ModuleAdminController`)
    -   **Nazwa Zakładki:** „Zarządzaj Wszystkimi Ikonami”
    -   **Odpowiedzialność:** Zarządza tworzeniem, edytowaniem i usuwaniem indywidualnych definicji ikon. Obsługuje operacje CRUD dla encji `ticon`. Ten kontroler używa `HelperList` do wyświetlania listy ikon i `HelperForm` do formularza dodawania/edycji. Zarządza przesyłaniem obrazów ikon.
-   **`ticons/controllers/admin/AdminTiconsAssociationsController.php`**
    -   **Nazwa Klasy:** `AdminTiconsAssociationsController` (rozszerza `ModuleAdminController`)
    -   **Nazwa Zakładki:** „Zarządzaj Powiązaniami Ikon”
    -   **Odpowiedzialność:** Zarządza powiązaniami utworzonych ikon z konkretnymi produktami. Zapewnia interfejs do wyszukiwania produktów, a następnie przypisywania/odpinania wielu ikon do nich. Ten kontroler również używa `HelperList` do wyświetlania produktów i niestandardowego formularza do wyboru ikon. Obsługuje żądania AJAX dla autouzupełniania wyszukiwania produktów.
-   **`ticons/controllers/admin/index.php`**
    -   **Odpowiedzialność:** Jest to standardowy pusty plik `index.php`, zazwyczaj obecny w katalogach PrestaShop, aby zapobiec listowaniu katalogów. Nie zawiera żadnej funkcjonalnej logiki kontrolera.

### 4.3 Klasy Podstawowe i Modele (`classes/`)

Moduł nie definiuje jawnie oddzielnych plików PHP w katalogu `classes/`. Zamiast tego, główny plik modułu `ajax_ticons.php` prawdopodobnie zawiera definicje `ObjectModel` dla `Ticon` i `TiconProduct` (lub podobnych encji) bezpośrednio w swoim zakresie, lub są one niejawnie obsługiwane poprzez interakcje z bazą danych.

-   **`Ticon` (Niejawny ObjectModel):**
    -   **Tabela Bazy Danych:** `ps_ticons` (lub podobna, na podstawie metody `install()` modułu).
    -   **Pola:** Prawdopodobnie zawiera `id_ticon`, `name` (wielojęzyczne), `description` (wielojęzyczne), `image`, `active`.
    -   **Cel:** Reprezentuje indywidualną definicję ikony, w tym jej obraz, nazwę i opis dymka.
-   **`TiconProduct` (Niejawny ObjectModel):**
    -   **Tabela Bazy Danych:** `ps_ticon_products` (lub podobna, na podstawie metody `install()` modułu).
    -   **Pola:** Prawdopodobnie zawiera `id_ticon_product`, `id_ticon`, `id_product`.
    -   **Cel:** Reprezentuje relację wiele do wielu między ikonami a produktami.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`ticons/lib/searchTool/views/js/autocomplete.js`**
    -   **Zakres:** Panel administracyjny (`AdminTiconsAssociationsController`).
    -   **Funkcjonalność:** Zapewnia funkcję autouzupełniania wyszukiwania produktów na ekranie „Zarządzaj Powiązaniami Ikon”. Prawdopodobnie wysyła żądania AJAX do kontrolera administracyjnego, aby pobrać sugestie produktów, gdy użytkownik pisze.
-   **`ticons/lib/tooltipster/js/jquery.tooltipster.js`**
    -   **Zakres:** Front-office.
    -   **Funkcjonalność:** Jest to podstawowa biblioteka dla wtyczki Tooltipster. Obsługuje tworzenie, pozycjonowanie i stylizowanie interaktywnych dymków, które pojawiają się, gdy użytkownicy najadą kursorem na ikony produktów. Wiąże zdarzenia najechania kursorem z elementami o określonych klasach (np. `.tooltipster`).
-   **`ticons/views/js/ticons-front.js`**
    -   **Zakres:** Front-office.
    -   **Funkcjonalność:** Zawiera niestandardowy JavaScript specyficzny dla wyświetlania ikon w front-office. Ten skrypt prawdopodobnie inicjalizuje wtyczkę Tooltipster na odpowiednich elementach ikon, przekazując opcje konfiguracji (motyw, pozycja, animacja) na podstawie ustawień modułu w Panelu administracyjnym. Zapewnia prawidłowe renderowanie i interaktywność ikon.
-   **`ticons/views/js/ticons.js`**
    -   **Zakres:** Panel administracyjny.
    -   **Funkcjonalność:** Zawiera ogólny JavaScript dla ekranów konfiguracji i zarządzania modułu w Panelu administracyjnym. Może to obejmować walidację formularzy, dynamiczną manipulację elementami lub inne ulepszenia interfejsu użytkownika dla interfejsu administracyjnego.

### 4.5 Arkusze Stylów CSS (`views/css/`)

-   **`ticons/lib/searchTool/views/css/autocomplete.css`**
    -   **Zakres:** Panel administracyjny.
    -   **Funkcjonalność:** Stylizuje rozwijane menu autouzupełniania i pole wprowadzania używane na ekranie „Zarządzaj Powiązaniami Ikon”.
-   **`ticons/lib/tooltipster/css/themes/tooltipster-light.css`**
    -   **Zakres:** Front-office.
    -   **Funkcjonalność:** Definiuje style dla motywu „Light” wtyczki Tooltipster.
-   **`ticons/lib/tooltipster/css/themes/tooltipster-noir.css`**
    -   **Zakres:** Front-office.
    -   **Funkcjonalność:** Definiuje style dla motywu „Noir” wtyczki Tooltipster.
-   **`ticons/lib/tooltipster/css/themes/tooltipster-punk.css`**
    -   **Zakres:** Front-office.
    -   **Funkcjonalność:** Definiuje style dla motywu „Punk” wtyczki Tooltipster.
-   **`ticons/lib/tooltipster/css/themes/tooltipster-shadow.css`**
    -   **Zakres:** Front-office.
    -   **Funkcjonalność:** Definiuje style dla motywu „Shadow” wtyczki Tooltipster.
-   **`ticons/lib/tooltipster/css/tooltipster.css`**
    -   **Zakres:** Front-office.
    -   **Funkcjonalność:** Podstawowy CSS dla wtyczki Tooltipster, zapewniający podstawowe style dla wszystkich dymków.
-   **`ticons/views/css/ticons-admin.css`**
    -   **Zakres:** Panel administracyjny.
    -   **Funkcjonalność:** Zawiera niestandardowy CSS specjalnie dla interfejsów Panelu administracyjnego modułu (np. stylizacja list ikon, formularzy i niestandardowych elementów w kontrolerach administracyjnych).
-   **`ticons/views/css/ticons-fontawesome.css`**
    -   **Zakres:** Front-office.
    -   **Funkcjonalność:** Prawdopodobnie zawiera lub importuje ikony Font Awesome, które mogą być używane jako ikony zastępcze lub dla specyficznych elementów interfejsu użytkownika w wyświetlaczu modułu.
-   **`ticons/views/css/ticons-front-24.css`**, **`ticons/views/css/ticons-front-32.css`**, **`ticons/views/css/ticons-front-48.css`**, **`ticons/views/css/ticons-front-64.css`**, **`ticons/views/css/ticons-front-74.css`**
    -   **Zakres:** Front-office.
    -   **Funkcjonalność:** Te arkusze stylów prawdopodobnie zawierają specyficzne reguły dla różnych rozmiarów ikon. Gdy sprzedawca wybierze „Rozmiar Ikony” w konfiguracji, moduł dynamicznie ładuje odpowiedni plik CSS, aby zapewnić renderowanie ikon w prawidłowych wymiarach i potencjalnie z zoptymalizowanym odstępem. Definiują one klasy takie jak `.ticon-24`, `.ticon-32` itd.
-   **`ticons/views/css/ticons.css`**
    -   **Zakres:** Front-office.
    -   **Funkcjonalność:** Ogólny CSS front-office dla modułu, w tym podstawowe style dla kontenerów ikon, obrazów i ogólnego układu. Ten plik może zawierać wspólne reguły stosowane niezależnie od wybranego rozmiaru ikony.

### 4.6 Struktura Szablonów Smarty (`views/templates/`)

#### Szablony Hooków (`views/templates/front/`)

Te szablony są renderowane, gdy moduł jest podłączony do różnych pozycji front-office. Zazwyczaj otrzymują tablicę danych ikon z metod `hook` modułu.

-   **`ticons/views/templates/front/deliveryTime.tpl`**
    -   **Hook:** Potencjalnie `displayProductDeliveryTime` lub podobny.
    -   **Wyjście:** Renderuje ikony związane z informacjami o dostawie.
-   **`ticons/views/templates/front/displayActions.tpl`**
    -   **Hook:** `displayProductActions` lub podobny.
    -   **Wyjście:** Renderuje ikony w pobliżu przycisków akcji produktu (np. „Dodaj do koszyka”).
-   **`ticons/views/templates/front/displayAfterProductThumbs.tpl`**
    -   **Hook:** `displayAfterProductThumbs` (PrestaShop 1.7+).
    -   **Wyjście:** Renderuje ikony bezpośrednio pod miniaturami produktów na stronie produktu.
-   **`ticons/views/templates/front/displayColumns.tpl`**
    -   **Hook:** `displayLeftColumn`, `displayRightColumn`.
    -   **Wyjście:** Renderuje ikony w modułach lewej lub prawej kolumny.
-   **`ticons/views/templates/front/displayLeftColumn.tpl`**
    -   **Hook:** `displayLeftColumn`.
    -   **Wyjście:** Renderuje ikony specjalnie w lewej kolumnie.
-   **`ticons/views/templates/front/displayProductAdditionalInfo.tpl`**
    -   **Hook:** `displayProductAdditionalInfo` (PrestaShop 1.7+).
    -   **Wyjście:** Renderuje ikony w sekcji „Dodatkowe Informacje” na stronie produktu, co jest powszechnym i zalecanym miejscem.
-   **`ticons/views/templates/front/displayProductPriceBlock.tpl`**
    -   **Hook:** `displayProductPriceBlock`.
    -   **Wyjście:** Renderuje ikony w pobliżu bloku ceny produktu.
-   **`ticons/views/templates/front/displayTop.tpl`**
    -   **Hook:** `displayTop` (nagłówek).
    -   **Wyjście:** Renderuje ikony w sekcji nagłówka sklepu.
-   **`ticons/views/templates/front/listReviews.tpl`**
    -   **Hook:** Potencjalnie `displayProductListReviews` lub podobny.
    -   **Wyjście:** Renderuje ikony związane z recenzjami lub ocenami produktów.
-   **`ticons/views/templates/front/productFooter.tpl`**
    -   **Hook:** `displayFooterProduct` lub podobny.
    -   **Wyjście:** Renderuje ikony w sekcji stopki strony produktu.
-   **`ticons/views/templates/front/showIcons.tpl`**
    -   **Hook:** Jest to prawdopodobnie ogólny szablon dołączany przez inne szablony hooków w celu renderowania rzeczywistej struktury HTML ikon (np. tagi `<img>` z klasami `tooltipster`). Iteruje po zmiennej `$icons` przekazanej do niego.

#### Szablony Administracyjne (`views/templates/admin/`)

Te szablony są używane do konfiguracji i zarządzania modułem w Panelu administracyjnym.

-   **`ticons/lib/searchTool/views/scripts.tpl`**
    -   **Zakres:** Panel administracyjny.
    -   **Wyjście:** Zawiera JavaScript dla narzędzia wyszukiwania, prawdopodobnie w tym inicjalizację autouzupełniania jQuery UI lub podobne.
-   **`ticons/views/templates/admin/customHook.tpl`**
    -   **Zakres:** Panel administracyjny.
    -   **Wyjście:** Ogólny szablon, który może być używany do renderowania treści dla niestandardowych hooków zdefiniowanych w interfejsie administracyjnym modułu lub do wyświetlania konkretnych komunikatów.
-   **`ticons/views/templates/admin/tabs.tpl`**
    -   **Zakres:** Panel administracyjny.
    -   **Wyjście:** Renderuje zakładki nawigacyjne (np. „Zarządzaj Wszystkimi Ikonami”, „Zarządzaj Powiązaniami Ikon”) dla stron konfiguracji modułu.
-   **`ticons/views/templates/admin/ticonsSelection.tpl`**
    -   **Zakres:** Panel administracyjny (`AdminTiconsAssociationsController`).
    -   **Wyjście:** Renderuje interfejs do wyboru i przypisywania ikon do produktu, zazwyczaj rozwijane menu wielokrotnego wyboru lub lista pól wyboru w formularzu powiązań produktów.
-   **`ticons/views/templates/admin/ticons_all/helpers/list/list_content.tpl`**
    -   **Zakres:** Panel administracyjny (`AdminTiconsAllController`).
    -   **Wyjście:** Dostosowuje zawartość tabeli `HelperList` do wyświetlania listy wszystkich utworzonych ikon. Może zawierać niestandardowe kolumny dla obrazów ikon lub statusu aktywności.
-   **`ticons/views/templates/admin/ticons_associations/helpers/form/form.tpl`**
    -   **Zakres:** Panel administracyjny (`AdminTiconsAssociationsController`).
    -   **Wyjście:** Dostosowuje `HelperForm` dla ekranu powiązań produktów. Ten szablon prawdopodobnie zawiera pole wyszukiwania produktów i `ticonsSelection.tpl` do przypisywania ikon.
-   **`ticons/views/templates/admin/ticons_associations/helpers/list/list_content.tpl`**
    -   **Zakres:** Panel administracyjny (`AdminTiconsAssociationsController`).
    -   **Wyjście:** Dostosowuje zawartość tabeli `HelperList` do wyświetlania listy produktów i ich powiązanych ikon.

### 4.7 Schemat Bazy Danych i Mapa Hooków

#### Tabele Bazy Danych

Moduł tworzy niestandardowe tabele podczas swojej metody `install()` do przechowywania definicji ikon i ich powiązań:

-   **`ps_ticons`**: Przechowuje główne definicje ikon.
    -   `id_ticon` (PK, INT)
    -   `image` (VARCHAR): Nazwa pliku obrazu ikony.
    -   `active` (TINYINT): 1, jeśli aktywny, 0, jeśli nieaktywny.
-   **`ps_ticons_lang`**: Przechowuje pola wielojęzyczne dla ikon.
    -   `id_ticon` (PK, INT)
    -   `id_lang` (PK, INT)
    -   `name` (VARCHAR): Nazwa ikony do użytku wewnętrznego.
    -   `description` (TEXT): Tekst dymka dla ikony.
-   **`ps_ticon_products`**: Przechowuje relację wiele do wielu między ikonami a produktami.
    -   `id_ticon_product` (PK, INT)
    -   `id_ticon` (FK, INT)
    -   `id_product` (FK, INT)

Ustawienia konfiguracyjne są przechowywane w `ps_configuration` z kluczami takimi jak `TICONS_ICON_SIZE`, `TICONS_HOOK_POSITION`, `TICONS_SHOW_IN_LIST` itp.

#### Tabela Zarejestrowanych Hooków

Moduł rejestruje kilka hooków do wyświetlania ikon w front office. Dokładne używane hooki zależą od wersji PrestaShop i konfiguracji sprzedawcy.

| Nazwa Hooka | Czas Wykonania | Cel Techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstawia zasoby CSS i JS (Tooltipster, niestandardowy JS/CSS). |
| `displayProductAdditionalInfo` | Na stronie produktu, w bloku „Dodatkowe Informacje” (PS 1.7+). | Renderuje ikony powiązane z bieżącym produktem. |
| `displayProductPriceBlock` | Na stronie produktu, w pobliżu ceny. | Renderuje ikony powiązane z bieżącym produktem. |
| `displayAfterProductThumbs` | Na stronie produktu, poniżej obrazów produktów (PS 1.7+). | Renderuje ikony powiązane z bieżącym produktem. |
| `displayProductListFunctionalButtons` | Na elementach listy produktów (np. stronach kategorii). | Renderuje ikony na kartach/miniaturach produktów. |
| `displayProductListReviews` | Na elementach listy produktów, w pobliżu recenzji. | Renderuje ikony na kartach/miniaturach produktów. |
| `displayProductDeliveryTime` | Na stronie produktu, w pobliżu informacji o dostawie. | Renderuje ikony powiązane z bieżącym produktem. |
| `displayLeftColumn` | W lewej kolumnie stron. | Renderuje ikony, jeśli skonfigurowano dla ogólnego wyświetlania. |
| `displayRightColumn` | W prawej kolumnie stron. | Renderuje ikony, jeśli skonfigurowano dla ogólnego wyświetlania. |
| `displayFooterProduct` | Na dole strony produktu. | Renderuje ikony powiązane z bieżącym produktem. |
| `actionProductUpdate` | Po zaktualizowaniu produktu w Panelu administracyjnym. | Potencjalnie czyści pamięć podręczną lub aktualizuje powiązania ikon. |
| `actionProductDelete` | Po usunięciu produktu. | Czyści powiązane wpisy ikon z `ps_ticon_products`. |
| `actionObjectLanguageAddAfter` | Po dodaniu nowego języka. | Zapewnia obsługę pól specyficznych dla języka dla ikon. |

## 5. Oficjalne Wsparcie i Aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu „Product Tag Icons Pro”.
