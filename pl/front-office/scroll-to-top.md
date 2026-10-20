---
title: "Przewiń do góry - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Przewiń do góry” od MyPresta.eu."
sidebar:
  label: "Przewiń do góry - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Scroll to top na MyPresta.eu](https://mypresta.eu/modules/front-office-features/scroll-to-top.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/scroll-to-top/)
>
> ---


# Przewiń do góry

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po zainstalowaniu modułu przejdź do **Moduły > Menedżer modułów** i kliknij „Konfiguruj” obok „Przewiń do góry”. Ta strona umożliwia dostosowanie wyglądu i położenia przycisku przewijania do góry.

#### **Pozycjonowanie wizualne**

- **Co robi to ustawienie:** Jest to wizualna reprezentacja miejsca, w którym przycisk pojawi się w Twoim sklepie. Nie jest to bezpośrednie ustawienie, ale raczej pomoc wizualna, która zmienia się w zależności od ustawień „Pozycja X” i „Pozycja Y”.
- **Efekt zmiany tego ustawienia:** Podczas dostosowywania „Pozycji X” i „Pozycji Y” podgląd przycisku na tej stronie konfiguracji będzie się przesuwał, pomagając Ci zwizualizować jego ostateczne położenie w Twoim front office.
- **Zalecana wartość:** Jest to dynamiczne.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby przycisk był bliżej prawego dolnego rogu, zobaczysz, jak podgląd przesuwa się tam, gdy dostosowujesz wartości X i Y.

#### **Schemat kolorów**

- **Co robi to ustawienie:** Kontroluje kolor tła przycisku przewijania do góry.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiony na konkretny kolor (np. #007bff dla niebieskiego):* Przycisk będzie wyświetlany z tym kolorem tła w Twoim front office.
  - *Gdy ustawiony na inny kolor:* Tło przycisku zmieni się odpowiednio.
- **Zalecana wartość:** Wybierz kolor, który uzupełnia branding Twojego sklepu i jest wyraźnie widoczny na tle Twojej witryny, ale nie jest zbyt rozpraszający.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli kolory Twojej marki to niebieski i biały, możesz ustawić ten kolor na odcień niebieskiego, aby pasował do Twojego motywu.

#### **Przezroczystość**

- **Co robi to ustawienie:** Określa, jak przezroczysty lub nieprzezroczysty jest przycisk przewijania do góry. Niższa przezroczystość sprawia, że jest bardziej przezroczysty, umożliwiając wyświetlanie treści w tle.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiony na wysoką wartość (np. 1.0 lub 100%):* Przycisk będzie w pełni nieprzezroczysty, bez przezroczystości.
  - *Gdy ustawiony na niższą wartość (np. 0.7 lub 70%):* Przycisk będzie półprzezroczysty, subtelnie wtapiając się w tło Twojego sklepu.
- **Zalecana wartość:** Wartość między 0.8 a 1.0 (80%-100%) jest zazwyczaj dobra. Zbyt niska, a może być trudno go zobaczyć; zbyt wysoka, a może wydawać się zbyt dominujący.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby przycisk był obecny, ale nie nadmiernie dominujący, ustawienie przezroczystości na 0.8 może być dobrym wyborem.

#### **Pozycja X (od prawej)**

- **Co robi to ustawienie:** Kontroluje poziomą pozycję przycisku, a konkretnie jego odległość od prawej krawędzi okna przeglądarki.
- **Efekt zmiany tego ustawienia:**
  - *Zwiększenie wartości (np. z 20px do 50px):* Przesuwa przycisk dalej w lewo, od prawej krawędzi.
  - *Zmniejszenie wartości (np. z 50px do 20px):* Przesuwa przycisk bliżej prawej krawędzi.
- **Zalecana wartość:** Zacznij od wartości takiej jak `20px` lub `30px`, aby utrzymać go w wygodnej odległości od krawędzi, nie wchodząc zbyt daleko w obszar treści.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli masz widżet czatu lub inny stały element po prawej stronie swojego sklepu, możesz zwiększyć tę wartość do `60px`, aby zapobiec nakładaniu się przycisku przewijania do góry.

#### **Pozycja Y (od dołu)**

- **Co robi to ustawienie:** Kontroluje pionową pozycję przycisku, a konkretnie jego odległość od dolnej krawędzi okna przeglądarki.
- **Efekt zmiany tego ustawienia:**
  - *Zwiększenie wartości (np. z 20px do 50px):* Przesuwa przycisk dalej w górę, od dolnej krawędzi.
  - *Zmniejszenie wartości (np. z 50px do 20px):* Przesuwa przycisk bliżej dolnej krawędzi.
- **Zalecana wartość:** Zacznij od wartości takiej jak `20px` lub `30px`, aby utrzymać go w wygodnej odległości od dolnej krawędzi, powyżej stopki.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój sklep ma stałą stopkę lub pasek zgody na pliki cookie na samym dole, możesz zwiększyć tę wartość do `70px`, aby upewnić się, że przycisk przewijania do góry jest zawsze widoczny nad tymi elementami.

#### **Tabela szybkiego odniesienia do konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Pozycjonowanie wizualne | Dynamiczne | Pomoc wizualna dla umiejscowienia przycisku na podstawie ustawień X/Y. |
| Konfiguracja modułu | Schemat kolorów | Różne (np. #007bff) | Ustawia kolor tła przycisku przewijania do góry. |
| Konfiguracja modułu | Przezroczystość | 0.8 - 1.0 | Kontroluje przezroczystość przycisku (0.0 = w pełni przezroczysty, 1.0 = w pełni nieprzezroczysty). |
| Konfiguracja modułu | Pozycja X (od prawej) | 20px - 30px | Określa poziomą odległość przycisku od prawej krawędzi ekranu. |
| Konfiguracja modułu | Pozycja Y (od dołu) | 20px - 30px | Określa pionową odległość przycisku od dolnej krawędzi ekranu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Przycisk przewijania do góry nie pojawia się w moim sklepie. Co powinienem zrobić?**
O:

1.  **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że moduł „Przewiń do góry” jest zainstalowany i włączony.
2.  **Wyczyść pamięć podręczną:** PrestaShop używa pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność**, przewiń w dół do „Wyczyść pamięć podręczną” i kliknij „Wyczyść pamięć podręczną”. Następnie odśwież swój front office.
3.  **Przewiń w dół:** Pamiętaj, że przycisk pojawia się tylko po przewinięciu strony w dół. Upewnij się, że przewinąłeś wystarczająco, aby stał się widoczny.
4.  **Sprawdź pozycje:** Upewnij się, że „Pozycja X” i „Pozycja Y” nie są ustawione na ekstremalnie wysokie wartości, które mogłyby wypchnąć przycisk poza ekran. Spróbuj ustawić je na `20px` każdy jako test.
5.  **Kompatybilność z motywem:** Chociaż rzadko, niektóre wysoce spersonalizowane motywy mogą mieć konflikty CSS. Jeśli powyższe kroki nie działają, tymczasowo przełącz się na domyślny motyw PrestaShop (Classic), aby sprawdzić, czy przycisk się pojawi. Jeśli tak, deweloper Twojego motywu może potrzebować pomocy.

**P: Przycisk jest widoczny, ale nie przewija do góry po kliknięciu.**
O:

1.  **Sprawdź JavaScript:** Zazwyczaj wskazuje to na konflikt lub błąd JavaScript. Otwórz konsolę deweloperską przeglądarki (zazwyczaj F12, a następnie przejdź do zakładki „Konsola”) i poszukaj czerwonych komunikatów o błędach.
2.  **Kolejność modułów:** Upewnij się, że żaden inny moduł nie zakłóca podstawowej funkcjonalności JavaScript.
3.  **Ponowna instalacja:** Spróbuj odinstalować i ponownie zainstalować moduł. Czasami może to rozwiązać problem uszkodzonych plików.

**P: Jak mogę zmienić ikonę przycisku (np. ze strzałki na coś innego)?**
O: Moduł używa standardowej ikony strzałki. Zmiana tego wymaga bezpośredniej modyfikacji plików CSS lub szablonów modułu, co wchodzi w zakres dostosowań deweloperskich. Nie jest to opcja dostępna w konfiguracji modułu.

**P: Przycisk wygląda dobrze na komputerze stacjonarnym, ale jest za duży/mały/źle umieszczony na urządzeniach mobilnych.**
O:

1.  **Dostosuj X i Y:** Użyj ustawień „Pozycja X” i „Pozycja Y”, aby precyzyjnie dostosować jego położenie specjalnie dla urządzeń mobilnych. Możesz potrzebować różnych wartości, aby uniknąć konfliktów z elementami interfejsu użytkownika specyficznymi dla urządzeń mobilnych.
2.  **Responsywność motywu:** CSS modułu jest zaprojektowany tak, aby był responsywny, ale ogólna responsywność Twojego motywu może wpływać na jego wygląd. Testuj na rzeczywistych urządzeniach lub użyj narzędzi deweloperskich przeglądarki, aby symulować różne rozmiary ekranu.
3.  **Niestandardowy CSS (zadanie dewelopera):** W przypadku zaawansowanych zmian rozmiaru lub stylizacji specyficznych dla urządzeń mobilnych, webmaster musiałby dodać niestandardowe reguły CSS do Twojego motywu, celując w przycisk tylko na mniejszych ekranach.

**P: Czy ten moduł spowolni moją stronę?**
O: Nie, moduł „Przewiń do góry” jest bardzo lekki. Dodaje minimalne CSS i JavaScript, które są ładowane efektywnie. Wszelki wpływ na wydajność byłby znikomy.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów, webmasterów i agencji, którzy chcą zrozumieć, debugować lub rozszerzać moduł „Przewiń do góry”.

### 4.1 Przegląd architektury

Moduł „Przewiń do góry” to prosty moduł PrestaShop, skupiający się głównie na ulepszaniu interfejsu użytkownika front-office. Podąża za klasyczną strukturą modułu PrestaShop, wykorzystując hooki do wstrzykiwania swoich zasobów HTML, CSS i JavaScript do front office. Nie wprowadza niestandardowych kontrolerów ani złożonych modeli danych, polegając zamiast tego na systemie konfiguracji PrestaShop dla swoich ustawień. Podstawowa funkcjonalność jest obsługiwana po stronie klienta za pomocą JavaScript.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery front-office**: Brak. Funkcjonalność front-office modułu jest w całości obsługiwana przez wstrzykiwanie zasobów i szablonu za pośrednictwem hooków.
- **Kontrolery administracyjne back-office**: Brak. Cała konfiguracja jest zarządzana za pomocą głównej metody `getContent()` modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

- W tym module nie ma niestandardowych klas ani definicji `ObjectModel`. Cała logika znajduje się w głównym pliku `scrolltop.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

- **`scrolltop/scrolltop.js`**
  - **Zakres:** Front-office.
  - **Odpowiedzialność:** Ten skrypt obsługuje podstawową logikę po stronie klienta dla przycisku przewijania do góry.
  - **Szczegóły:**
    - Czeka na pełne załadowanie DOM (`$(document).ready()`).
    - Dołącza słuchacz zdarzeń do zdarzenia `$(window).scroll()`.
    - Wewnątrz obsługi zdarzenia przewijania sprawdza `$(this).scrollTop()`. Jeśli pozycja przewijania jest większa niż określony próg (np. 100px), pokazuje przycisk przewijania do góry; w przeciwnym razie go ukrywa.
    - Dołącza słuchacz zdarzeń kliknięcia do elementu przycisku przewijania do góry.
    - Po kliknięciu używa `$('html, body').animate({scrollTop: 0}, 'slow');` do płynnego animowania przewijania strony z powrotem na górę.
    - Zapobiega domyślnemu zachowaniu linku (`return false;`).
  - **Zależności:** jQuery (który jest zazwyczaj dostępny w front office PrestaShop).

### 4.5 Arkusze stylów CSS (`views/css/`)

- **`scrolltop/scrolltop.css`**
  - **Zakres:** Stylizacja klienta front-office.
  - **Odpowiedzialność:** Definiuje wygląd wizualny i stałe pozycjonowanie przycisku przewijania do góry.
  - **Szczegóły:**
    - Celuje w element `#scroll-to-top`.
    - Używa `position: fixed;` do utrzymania przycisku w statycznej pozycji względem obszaru widoku.
    - Stosuje właściwości `bottom` i `right`, dynamicznie ustawiane przez konfigurację modułu, aby kontrolować jego dokładne położenie.
    - Definiuje `z-index`, aby upewnić się, że przycisk pojawia się nad innymi treściami.
    - Początkowo ustawia `display: none;`, ponieważ JavaScript kontroluje jego widoczność.
    - Style dla `background-color`, `border-radius`, `padding`, `width`, `height`, `line-height`, `text-align`, `color` (dla ikony strzałki), `font-size` i `cursor`.
    - Zawiera właściwość `transition` dla płynnych zmian wizualnych (np. po najechaniu myszką lub podczas pojawiania się/znikania).
    - Może zawierać responsywne dostosowania za pomocą zapytań mediów, aby zoptymalizować wygląd na różnych rozmiarach ekranu.
  - **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** `#scroll-to-top`, `#scroll-to-top i` (dla ikony).

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:
  - **`scrolltop/footer.tpl`**
    - **Hook:** `displayFooter` (lub `displayHeader` dla ładowania zasobów).
    - **Cel:** Ten szablon renderuje strukturę HTML dla przycisku przewijania do góry.
    - **Zawartość:** Zazwyczaj zawiera tag `<a>` lub `<div>` z ID takim jak `#scroll-to-top` oraz tag `<i>` (często używający Font Awesome lub podobnej czcionki ikon) dla ikony strzałki.
    - Zawiera również atrybuty stylu inline lub atrybuty danych, aby przekazać skonfigurowane wartości `color`, `opacity`, `position X` i `position Y` z ustawień modułu do front-endowego CSS lub JavaScript w celu dynamicznej stylizacji.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Ustawienia konfiguracji (`st_color`, `st_x`, `st_y`, `st_o`, `mypresta_updates`, `update_`, `updatev_`) są przechowywane w tabeli `ps_configuration` PrestaShop.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Służy do rejestrowania i ładowania zasobów CSS (`scrolltop.css`) i JavaScript (`scrolltop.js`) modułu. |
| `displayFooter` | Na końcu sekcji `<body>` każdej strony front-office, tuż przed zamykającym tagiem `</body>`. | Służy do renderowania struktury HTML przycisku przewijania do góry (`footer.tpl`). Zapewnia to obecność HTML przycisku w DOM, aby JavaScript mógł nim manipulować. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i najnowszych wersji modułu „Przewiń do góry”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
