---
title: "Komentarze DISQUS - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Komentarze DISQUS od MyPresta.eu."
sidebar:
  label: "Komentarze DISQUS - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł DISQUS comments na MyPresta.eu](https://mypresta.eu/modules/front-office-features/disqus-comments.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/disqus-comments/)
>
> ---


# Komentarze DISQUS

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla PrestaShop i do komunikacji z zewnętrznymi usługami, takimi jak Disqus.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Komentarze DISQUS)

To jest główny ekran konfiguracji, na którym ustawisz, jak Disqus integruje się z Twoim sklepem.

#### **1. Krótka nazwa witryny (Site shortname)**

- **Co robi to ustawienie:** Jest to unikalny identyfikator Twojej witryny Disqus. Otrzymujesz go z konta Disqus po zarejestrowaniu swojej witryny. Informuje Disqus, które wątki komentarzy należą do Twojego sklepu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione poprawnie:* Komentarze Disqus będą ładowane i zapisywane poprawnie dla Twoich produktów.
  - *Gdy niepoprawne lub puste:* Disqus nie będzie w stanie załadować komentarzy lub może załadować komentarze z innej witryny, co prowadzi do błędów lub brakujących komentarzy.
- **Zalecana wartość:** Twoja unikalna krótka nazwa Disqus (np. `nazwatwojegosklepu`).
- **Scenariusz / przykład dla sprzedawcy:** Jeśli zarejestrowałeś swoją witrynę na Disqus jako „Mój Niesamowity Sklep”, Twoja krótka nazwa może brzmieć „mojniesamowitysklep”. Wprowadź dokładnie ten ciąg znaków tutaj.

#### **2. Pozycja widżetu komentarzy (Comments widget position)**

- **Co robi to ustawienie:** Kontroluje, gdzie główna sekcja komentarzy Disqus pojawia się na stronach Twoich produktów.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na „Sekcja zakładki produktu” (Product Tab section):* Komentarze pojawią się w nowej zakładce na stronie produktu (np. obok „Opisu” lub „Karty danych”). Klienci klikają zakładkę, aby zobaczyć komentarze.
  - *Gdy ustawione na „Sekcja stopki produktu” (Product Footer section):* Komentarze pojawią się na dole strony produktu, poniżej głównych informacji o produkcie. Klienci zobaczą je, gdy przewiną stronę w dół.
- **Zalecana wartość:** „Sekcja zakładki produktu” dla czystszego układu strony produktu, lub „Sekcja stopki produktu”, jeśli chcesz, aby komentarze były natychmiast widoczne bez klikania zakładki.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoje strony produktów są już bardzo długie, umieszczenie komentarzy w zakładce utrzymuje początkowy widok w porządku. Jeśli chcesz podkreślić opinie klientów, umieszczenie ich w stopce sprawia, że są bardziej widoczne.

#### **3. Strona z referencjami (Testimonials page)**

- **Co robi to ustawienie:** Włącza lub wyłącza dedykowaną stronę w Twoim sklepie, która agreguje wszystkie komentarze Disqus ze wszystkich Twoich produktów.
- **Efekt zmiany tego ustawienia:**
  - *Gdy „Włączone” (Enabled):* Zostanie utworzona nowa strona pod adresem URL, takim jak `twojasklep.com/testimonials` (lub podobnym, w zależności od Twoich przyjaznych adresów URL), pokazująca wszystkie komentarze.
  - *Gdy „Wyłączone” (Disabled):* Taka strona nie będzie dostępna.
- **Zalecana wartość:** „Włączone”, aby zapewnić centralne centrum opinii klientów.
- **Scenariusz / przykład dla sprzedawcy:** Włączenie tej opcji pozwala na linkowanie do strony „Recenzje klientów” lub „Co mówią nasi klienci” ze stopki, prezentując wszystkie pozytywne opinie w jednym miejscu.

#### **4. Wygląd linku do referencji (Testimonials link appearance)**

- **Co robi to ustawienie:** Jeśli „Strona z referencjami” jest włączona, kontroluje, gdzie link do tej strony pojawia się w układzie Twojego sklepu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy „Ukryj” (Hide):* Strona z referencjami będzie istnieć, ale moduł nie doda automatycznie linku. Musiałbyś ręcznie dodać link (np. w menu stopki Twojego szablonu).
  - *Gdy „Lewa kolumna” (Left column):* Link do strony z referencjami pojawi się w lewej kolumnie Twojego sklepu.
  - *Gdy „Prawa kolumna” (Right column):* Link do strony z referencjami pojawi się w prawej kolumnie Twojego sklepu.
- **Zalecana wartość:** „Prawa kolumna” lub „Lewa kolumna”, aby strona z referencjami była łatwo odkrywalna.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój sklep używa lewej kolumny dla kategorii, umieszczenie linku do referencji w prawej kolumnie może być bardziej odpowiednie.

#### **5. Ostatnie komentarze na stronie głównej (Homepage recent comments)**

- **Co robi to ustawienie:** Kontroluje, czy blok wyświetlający najnowsze komentarze Disqus pojawia się na stronie głównej Twojego sklepu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy „Włączone” (Enabled):* Blok z ostatnimi komentarzami zostanie wyświetlony na stronie głównej.
  - *Gdy „Wyłączone” (Disabled):* Na stronie głównej nie pojawi się blok ostatnich komentarzy.
- **Zalecana wartość:** „Włączone”, aby strona główna była dynamiczna i podkreślała ostatnią aktywność klientów.
- **Scenariusz / przykład dla sprzedawcy:** Pokazywanie ostatnich komentarzy na stronie głównej może zachęcić odwiedzających do przeglądania produktów, które mają aktywne dyskusje, potencjalnie prowadząc do większej sprzedaży.

#### **6. Ostatnie komentarze w prawej kolumnie (Right column recent comments)**

- **Co robi to ustawienie:** Kontroluje, czy blok wyświetlający najnowsze komentarze Disqus pojawia się w prawej kolumnie Twojego sklepu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy „Włączone” (Enabled):* Blok z ostatnimi komentarzami zostanie wyświetlony w prawej kolumnie na stronach, gdzie prawa kolumna jest aktywna.
  - *Gdy „Wyłączone” (Disabled):* W prawej kolumnie nie pojawi się blok ostatnich komentarzy.
- **Zalecana wartość:** „Włączone”, aby utrzymać zaangażowanie na całej stronie.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój sklep ma prawą kolumnę, wyświetlanie tam ostatnich komentarzy może zapewnić stały strumień świeżych treści i zachęcić do eksploracji.

#### **7. Ostatnie komentarze w lewej kolumnie (Left column recent comments)**

- **Co robi to ustawienie:** Kontroluje, czy blok wyświetlający najnowsze komentarze Disqus pojawia się w lewej kolumnie Twojego sklepu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy „Włączone” (Enabled):* Blok z ostatnimi komentarzami zostanie wyświetlony w lewej kolumnie na stronach, gdzie lewa kolumna jest aktywna.
  - *Gdy „Wyłączone” (Disabled):* W lewej kolumnie nie pojawi się blok ostatnich komentarzy.
- **Zalecana wartość:** „Włączone”, aby utrzymać zaangażowanie na całej stronie.
- **Scenariusz / przykład dla sprzedawcy:** Podobnie jak w prawej kolumnie, użycie lewej kolumny dla ostatnich komentarzy może być skuteczne, jeśli Twój szablon używa głównie lewej kolumny do nawigacji lub innych bloków.

#### **8. Pokaż disqus tylko dla zalogowanych użytkowników, którzy kupili produkt (Show disqus only for logged users that purchased product)**

- **Co robi to ustawienie:** Jest to potężne ustawienie do ograniczania, kto może widzieć i wchodzić w interakcje z komentarzami Disqus na stronach produktów.
- **Efekt zmiany tego ustawienia:**
  - *Gdy „Włączone” (Enabled):* Tylko klienci, którzy są zalogowani na swoje konto ORAZ wcześniej kupili konkretny produkt, zobaczą sekcję komentarzy Disqus. Wszyscy inni odwiedzający jej nie zobaczą.
  - *Gdy „Wyłączone” (Disabled):* Wszyscy odwiedzający (zalogowani lub goście, kupujący lub nie) zobaczą sekcję komentarzy Disqus.
- **Zalecana wartość:** „Wyłączone” dla maksymalnego zaangażowania i korzyści SEO. „Włączone”, jeśli chcesz mieć pewność, że tylko zweryfikowani kupujący mogą komentować, co może zwiększyć wiarygodność recenzji, ale zmniejszyć liczbę komentarzy.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli masz problem ze spamem lub nieistotnymi komentarzami, włączenie tej opcji może odfiltrować osoby niebędące kupującymi. Jeśli jednak Twoim celem jest szeroka dyskusja i SEO, pozostaw ją wyłączoną.

#### **9. Ile ostatnich komentarzy pokazać? (How many recent comments to show?)**

- **Co robi to ustawienie:** Określa liczbę ostatnich komentarzy wyświetlanych w blokach „Ostatnie komentarze” (na stronie głównej, w lewej lub prawej kolumnie).
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na liczbę (np. 5):* Bloki wyświetlą tyle najnowszych komentarzy.
  - *Gdy ustawione na 0 lub puste:* W blokach nie zostaną wyświetlone żadne ostatnie komentarze, nawet jeśli bloki są włączone.
- **Zalecana wartość:** 3 do 5 komentarzy dla kompaktowego bloku, lub do 10 dla bardziej widocznego wyświetlania.
- **Scenariusz / przykład dla sprzedawcy:** Pokazywanie 5 komentarzy zapewnia dobrą równowagę między wyświetlaniem aktywności a nieczynieniem bloku zbyt długim.

#### **Tabela szybkiego odniesienia do konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Krótka nazwa witryny | Twoja krótka nazwa Disqus | Unikalny identyfikator Twojego konta Disqus; niezbędny do ładowania komentarzy. |
| Konfiguracja modułu | Pozycja widżetu komentarzy | Sekcja zakładki produktu | Gdzie główna sekcja komentarzy pojawia się na stronach produktów (zakładka lub stopka). |
| Konfiguracja modułu | Strona z referencjami | Włączone | Tworzy dedykowaną stronę agregującą wszystkie komentarze. |
| Konfiguracja modułu | Wygląd linku do referencji | Prawa kolumna | Gdzie pojawia się link do strony z referencjami (jeśli włączona). |
| Konfiguracja modułu | Ostatnie komentarze na stronie głównej | Włączone | Wyświetla blok ostatnich komentarzy na stronie głównej. |
| Konfiguracja modułu | Ostatnie komentarze w prawej kolumnie | Włączone | Wyświetla blok ostatnich komentarzy w prawej kolumnie. |
| Konfiguracja modułu | Ostatnie komentarze w lewej kolumnie | Włączone | Wyświetla blok ostatnich komentarzy w lewej kolumnie. |
| Konfiguracja modułu | Pokaż disqus tylko dla zalogowanych użytkowników, którzy kupili produkt | Wyłączone | Ogranicza widoczność/interakcję komentarzy do zweryfikowanych kupujących. |
| Konfiguracja modułu | Ile ostatnich komentarzy pokazać? | 5 | Liczba komentarzy do wyświetlenia w blokach ostatnich komentarzy. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje komentarze Disqus nie pojawiają się na stronach produktów. Co powinienem zrobić?**

- **O:** Najpierw dokładnie sprawdź swoją „Krótką nazwę witryny” w konfiguracji modułu. Musi ona dokładnie odpowiadać krótkiej nazwie z Twojego konta Disqus. Upewnij się również, że ustawiłeś „Pozycję widżetu komentarzy” na „Sekcja zakładki produktu” lub „Sekcja stopki produktu”. Na koniec wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) i pamięć podręczną przeglądarki.

**P2: Bloki „Ostatnie komentarze” nie pojawiają się w moich kolumnach/na stronie głównej.**

- **O:** Sprawdź, czy włączyłeś „Ostatnie komentarze na stronie głównej”, „Ostatnie komentarze w prawej kolumnie” lub „Ostatnie komentarze w lewej kolumnie” w konfiguracji modułu. Upewnij się również, że „Ile ostatnich komentarzy pokazać?” jest ustawione na liczbę większą niż 0. Jeśli Twój szablon nie wyświetla lewej/prawej kolumny na niektórych stronach, bloki nie pojawią się tam. Wyczyść pamięć podręczną po wprowadzeniu zmian.

**P3: Włączyłem „Stronę z referencjami”, ale nie mogę znaleźć do niej linku.**

- **O:** Jeśli ustawiłeś „Wygląd linku do referencji” na „Ukryj”, moduł nie doda automatycznie linku. Będziesz musiał ręcznie dodać link do strony (np. w menu stopki Twojego szablonu). Adres URL strony z referencjami to zazwyczaj `twojasklep.com/module/disqus/testimonials` (lub wersja przyjaznego adresu URL, jeśli jest włączona). Jeśli wybrałeś „Lewa kolumna” lub „Prawa kolumna”, upewnij się, że te kolumny są aktywne na przeglądanych stronach.

**P4: Tylko niektórzy użytkownicy mogą widzieć komentarze, lub nie mogę ich widzieć jako gość.**

- **O:** Sprawdź ustawienie „Pokaż disqus tylko dla zalogowanych użytkowników, którzy kupili produkt”. Jeśli jest ono włączone, tylko zalogowani klienci, którzy kupili konkretny produkt, zobaczą komentarze. Wyłącz to ustawienie, jeśli chcesz, aby wszyscy odwiedzający widzieli komentarze i wchodzili z nimi w interakcje.

**Q5: Stylizacja mojego niestandardowego szablonu koliduje z komentarzami Disqus.**

- **O:** Sam widżet Disqus jest w dużej mierze samodzielny i stylizowany przez Disqus. Jednak kontener lub zakładka, która zawiera widżet, może być pod wpływem CSS Twojego szablonu. Może być konieczne, aby programista internetowy zbadał elementy za pomocą narzędzi deweloperskich przeglądarki i dodał niestandardowy CSS do Twojego szablonu, aby dostosować odstępy, czcionki lub kolory wokół widżetu Disqus.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu Komentarze DISQUS dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł Komentarze DISQUS stosuje standardową architekturę modułów PrestaShop, głównie wykorzystując hooki do wyświetlania w front-office i metodę `getContent()` do konfiguracji w back-office. Integruje dynamicznie uniwersalny kod osadzania Disqus. Moduł używa niestandardowego kontrolera front-end dla strony z referencjami oraz innego dla wywołań AJAX (chociaż obecnie kontroler AJAX wydaje się być tylko miejscem docelowym lub nie jest intensywnie wykorzystywany do podstawowej funkcjonalności Disqus). Konfiguracja jest przechowywana w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/index.php`
        -   **Nazwa klasy:** `DisqusIndexModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność:** Ten kontroler jest prawdopodobnie domyślnym lub awaryjnym dla routingu front-office modułu. W kontekście Disqus może być używany do ogólnych akcji front-end związanych z modułem, chociaż główne osadzanie Disqus jest zazwyczaj obsługiwane za pomocą hooków. Może służyć jako podstawa dla przyszłych funkcji AJAX lub prostych wyświetleń stron, jeśli zajdzie taka potrzeba.
    -   `controllers/front/testimonials.php`
        -   **Nazwa klasy:** `DisqusTestimonialsModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność:** Ten kontroler jest odpowiedzialny za renderowanie dedykowanej strony „Referencje”. Pobiera niezbędną konfigurację (np. `disqus_shortname`) i przekazuje ją do szablonu `testimonials.tpl`, który następnie osadza uniwersalny kod osadzania Disqus skonfigurowany do wyświetlania wszystkich komentarzy dla danej krótkiej nazwy. Ten kontroler obsługuje trasę `module/disqus/testimonials`.
-   **Kontrolery Back-Office Admin**: Brak wyraźnie zdefiniowanych w dostarczonym spisie. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównego pliku modułu.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

W katalogu `classes/` nie ma niestandardowych klas ani definicji `ObjectModel` zgodnie ze spisem. Moduł opiera się na klasie `Configuration` PrestaShop do przechowywania swoich ustawień.

### 4.4 Zasoby JavaScript (`views/js/`)

W katalogu `views/js/` nie ma niestandardowych plików JavaScript zgodnie ze spisem. Moduł bezpośrednio osadza uniwersalny kod osadzania Disqus (zazwyczaj tag `<script>` z `DISQUS.init()` lub podobną logiką) w odpowiednich szablonach Smarty. Oznacza to, że własny JavaScript Disqus jest ładowany bezpośrednio z `disqus.com`.

### 4.5 Arkusze stylów CSS (`views/css/`)

W katalogu `views/css/` nie ma niestandardowych plików CSS zgodnie ze spisem. Stylizacja samego widżetu komentarzy Disqus jest obsługiwana przez Disqus. Wszelkie stylizacje specyficzne dla integracji (np. dla bloków ostatnich komentarzy lub układu strony z referencjami) byłyby minimalne, dziedziczone z szablonu lub wbudowane w szablony.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   `last-comments.tpl`: Ten szablon służy do wyświetlania bloku „Ostatnie komentarze”. Iteruje przez listę ostatnich komentarzy (pobranych z Disqus za pomocą JavaScript lub wywołania po stronie serwera, jeśli zaimplementowano) i wyświetla je. Ten szablon jest prawdopodobnie renderowany w hookach `displayHome`, `displayLeftColumn` i `displayRightColumn`.
    -   `leftColumn.tpl`: Ten szablon jest prawdopodobnie opakowaniem lub specyficzną zawartością dla hooka `displayLeftColumn`, potencjalnie zawierającą `last-comments.tpl` lub link do referencji.
    -   `productfooter.tpl`: Ten szablon jest renderowany w hooku `displayProductFooter`. Zawiera uniwersalny kod osadzania Disqus dla komentarzy do produktów, gdy „Pozycja widżetu komentarzy” jest ustawiona na „Sekcja stopki produktu”.
    -   `rightColumn.tpl`: Podobnie jak `leftColumn.tpl`, ten jest dla hooka `displayRightColumn`, potencjalnie zawierającego `last-comments.tpl` lub link do referencji.
-   **Szablony administracyjne (`views/templates/admin/`)**: Brak.
-   **Szablony front-office (`views/templates/front/`)**:

    -   `testimonials.tpl`: Ten szablon jest renderowany przez `DisqusTestimonialsModuleFrontController`. Zawiera uniwersalny kod osadzania Disqus skonfigurowany do wyświetlania wszystkich komentarzy dla krótkiej nazwy witryny, efektywnie tworząc zagregowaną stronę z referencjami.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Moduł nie tworzy żadnych niestandardowych tabel SQL. Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `DISQUS_SHORTNAME`, `DISQUS_HOOK`, `DISQUS_TEST`, `DISQUS_TEST_WHERE`, `DISQUS_RIGHTRECENT`, `DISQUS_LEFTRECENT`, `DISQUS_FORLOGGED`, `DISQUS_LASTCOMMENTS`, `DISQUS_LASTC_NB`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Potencjalnie używany do włączania globalnych zmiennych konfiguracyjnych Disqus lub CSS/JS, jeśli jest to potrzebne, chociaż główne osadzanie odbywa się w specyficznych hookach treści. |
| `displayProductExtraContent` | W obrębie strony produktu, często używany do zakładek lub dodatkowych bloków treści. | Używany do wyświetlania sekcji komentarzy Disqus w zakładce produktu, gdy „Pozycja widżetu komentarzy” jest ustawiona na „Sekcja zakładki produktu”. |
| `displayRightColumn` | W prawej kolumnie stron. | Używany do wyświetlania bloku „Ostatnie komentarze” lub „Linku do referencji”, jeśli skonfigurowano. |
| `displayProductFooter` | Na dole treści strony produktu. | Używany do wyświetlania sekcji komentarzy Disqus, gdy „Pozycja widżetu komentarzy” jest ustawiona na „Sekcja stopki produktu”. |
| `displayLeftColumn` | W lewej kolumnie stron. | Używany do wyświetlania bloku „Ostatnie komentarze” lub „Linku do referencji”, jeśli skonfigurowano. |
| `displayHome` | Na stronie głównej. | Używany do wyświetlania bloku „Ostatnie komentarze” na stronie głównej. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Ten hook jest wymieniony w metodzie `install()` modułu, co sugeruje potencjalną przyszłą funkcję lub sprawdzenie zakupionych produktów. Prawdopodobnie jest używany w połączeniu z ustawieniem „Pokaż disqus tylko dla zalogowanych użytkowników, którzy kupili produkt” w celu weryfikacji historii zakupów. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji modułu, poprawek błędów i oficjalnego wsparcia, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu Komentarze DISQUS.
