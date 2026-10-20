---
title: "Tooltip Pro - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Tooltip Pro od MyPresta.eu."
sidebar:
  label: "Tooltip Pro - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Tooltip Pro na MyPresta.eu](https://mypresta.eu/modules/front-office-features/tooltip-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/tooltip-pro/)
>
> ---


# Tooltip Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Tooltip Pro)

Jest to główny ekran konfiguracji modułu Tooltip Pro, gdzie kontrolujesz jego ogólne zachowanie i wygląd.

- **Lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > Wyszukaj „Tooltip Pro” > Kliknij „Konfiguruj”

#### Ustawienia i opcje:

1.  **Włącz dymki (tooltipy):**

    - **Co robi to ustawienie:** Jest to główny przełącznik do aktywowania lub dezaktywowania całej funkcjonalności dymków w Twoim Front Office.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy włączone (TAK):* Dymki będą aktywne w Twoim sklepie zgodnie z innymi ustawieniami.
      - *Gdy wyłączone (NIE):* Żadne dymki nie pojawią się w Twoim sklepie, niezależnie od utworzonych pojedynczych wpisów dymków.
    - **Zalecana wartość:** TAK (po skonfigurowaniu dymków).
    - **Scenariusz/przykład dla sprzedawcy:** Jeśli wykonujesz konserwację lub chcesz tymczasowo wyłączyć wszystkie dymki bez ich usuwania, ustaw to na NIE.
2.  **Podświetl słowa kluczowe dymków:**

    - **Co robi to ustawienie:** Określa, czy tekst, który wywołuje dymek, powinien być wizualnie podświetlony na Twojej stronie internetowej.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy włączone (TAK):* Zdefiniowane przez Ciebie słowa kluczowe dla dymków będą miały zastosowany styl wizualny (np. przerywane podkreślenie, pogrubienie lub określony kolor, w zależności od CSS Twojego motywu lub domyślnego stylu modułu). Pomaga to klientom identyfikować interaktywne elementy.
      - *Gdy wyłączone (NIE):* Słowa kluczowe pojawią się jako zwykły tekst, ale najechanie na nie nadal wywoła dymek. Może to sprawić, że dymki będą mniej widoczne.
    - **Zalecana wartość:** TAK.
    - **Scenariusz/przykład dla sprzedawcy:** Włączenie tej opcji jasno informuje klientów, które słowa są interaktywne, zachęcając ich do odkrywania pomocnych informacji. Jeśli preferujesz bardzo minimalistyczny design i oczekujesz, że użytkownicy odkryją dymki naturalnie, możesz to wyłączyć.
3.  **Położenie dymka:**

    - **Co robi to ustawienie:** Kontroluje, gdzie okienko dymka pojawia się względem tekstu słowa kluczowego.
    - **Efekt zmiany tego ustawienia:**
      - *Opcje (np. Góra, Dół, Lewo, Prawo, Auto):* Wybranie „Góra” spowoduje, że dymek pojawi się nad tekstem, „Dół” poniżej itd. „Auto” próbuje inteligentnie umieścić dymek, aby uniknąć wyjścia poza ekran.
    - **Zalecana wartość:** Auto.
    - **Scenariusz/przykład dla sprzedawcy:** „Auto” jest zazwyczaj najlepszym wyborem, ponieważ dostosowuje się do różnych rozmiarów ekranu i układów treści. Jeśli zauważysz, że dymki konsekwentnie zasłaniają ważne treści w określonym obszarze, możesz eksperymentować z ustalonym położeniem, takim jak „Dół”.
4.  **Animacja dymka:**

    - **Co robi to ustawienie:** Wybiera efekt animacji, gdy dymek pojawia się i znika.
    - **Efekt zmiany tego ustawienia:**
      - *Opcje (np. Zanikanie, Rozrost, Kołysanie, Przesuwanie, Opadanie):* Każda opcja zapewnia inną wizualną transformację. „Zanikanie” to proste rozpuszczanie, „Rozrost” rozszerza się itd.
    - **Zalecana wartość:** Zanikanie lub Rozrost.
    - **Scenariusz/przykład dla sprzedawcy:** Subtelna animacja, taka jak „Zanikanie” lub „Rozrost”, dodaje elegancji, nie rozpraszając uwagi. Unikaj zbyt skomplikowanych animacji, które mogą spowolnić doświadczenie użytkownika lub wydawać się nie na miejscu w Twojej marce.
5.  **Motyw dymka:**

    - **Co robi to ustawienie:** Pozwala wybrać predefiniowany motyw wizualny dla Twoich dymków. Wpływa to na kolory, obramowania i ogólny styl.
    - **Efekt zmiany tego ustawienia:**
      - *Opcje (np. Domyślny, Jasny, Ciemny, Z obramowaniem, Punk):* Każdy motyw stosuje inny zestaw stylów CSS.
    - **Zalecana wartość:** Domyślny lub Jasny.
    - **Scenariusz/przykład dla sprzedawcy:** Wybierz motyw, który najlepiej pasuje do ogólnego projektu i brandingu Twojego sklepu. „Jasny” lub „Domyślny” są często dobrymi punktami wyjścia. Jeśli masz stronę internetową o ciemnym motywie, „Ciemny” może być bardziej odpowiedni.
6.  **Maksymalna szerokość dymka (piksele):**

    - **Co robi to ustawienie:** Ustawia maksymalną szerokość okienka dymka w pikselach.
    - **Efekt zmiany tego ustawienia:**
      - *Wprowadzenie wartości (np. 300):* Dymek nie przekroczy tej szerokości, zawijając tekst w razie potrzeby.
      - *Pozostawienie pustego lub 0:* Dymek automatycznie dostosuje swój rozmiar do zawartości, co czasami może prowadzić do bardzo szerokich dymków.
    - **Zalecana wartość:** 250-350 pikseli.
    - **Scenariusz/przykład dla sprzedawcy:** Ustawienie rozsądnej maksymalnej szerokości zapewnia, że dymki nie staną się zbyt szerokie i nie rozciągną się na cały ekran, zwłaszcza na mniejszych urządzeniach lub w wąskich układach kolumn.
7.  **Opóźnienie przed pokazaniem (milisekundy):**

    - **Co robi to ustawienie:** Czas (w milisekundach), przez który użytkownik musi najechać kursorem na słowo kluczowe, zanim pojawi się dymek.
    - **Efekt zmiany tego ustawienia:**
      - *Wyższa wartość (np. 500 ms):* Dymki pojawiają się po dłuższym opóźnieniu, zapobiegając zbyt szybkiemu wyskakiwaniu, jeśli użytkownik tylko przesuwa mysz po stronie.
      - *Niższa wartość (np. 0 ms):* Dymki pojawiają się natychmiast.
    - **Zalecana wartość:** 200-300.
    - **Scenariusz/przykład dla sprzedawcy:** Niewielkie opóźnienie (np. 200 ms) zapewnia płynniejsze doświadczenie użytkownika, ponieważ zapobiega szybkiemu pojawianiu się i znikania przypadkowych dymków.
8.  **Opóźnienie przed ukryciem (milisekundy):**

    - **Co robi to ustawienie:** Czas (w milisekundach), przez który dymek pozostaje widoczny po odsunięciu myszy od słowa kluczowego.
    - **Efekt zmiany tego ustawienia:**
      - *Wyższa wartość (np. 200 ms):* Dymek pozostaje widoczny przez krótki czas, umożliwiając użytkownikom lekkie przesunięcie myszy bez natychmiastowego znikania dymka.
      - *Niższa wartość (np. 0 ms):* Dymek znika natychmiast po opuszczeniu słowa kluczowego przez mysz.
    - **Zalecana wartość:** 100-200.
    - **Scenariusz/przykład dla sprzedawcy:** Niewielkie opóźnienie może być pomocne, jeśli użytkownik przypadkowo odsunie mysz od słowa kluczowego, ale chce kontynuować czytanie dymka.
9.  **Dozwolone typy stron dla dymków:**

    - **Co robi to ustawienie:** Określa, na jakich typach stron dymki powinny być aktywne.
    - **Efekt zmiany tego ustawienia:**
      - *Pola wyboru (np. Strony produktów, Strony kategorii, Strony CMS, Wszystkie strony):* Wybierz konkretne typy stron, na których chcesz, aby Twoje dymki działały.
      - *Wybranie „Wszystkie strony”:* Dymki będą aktywne wszędzie w Twoim sklepie.
    - **Zalecana wartość:** Wybierz tylko te typy stron, na których naprawdę potrzebujesz dymków, aby uniknąć niepotrzebnego przetwarzania na innych stronach.
    - **Scenariusz/przykład dla sprzedawcy:** Jeśli używasz dymków głównie do specyfikacji produktów, możesz zaznaczyć tylko „Strony produktów”. Jeśli masz wiele terminów technicznych na całej swojej stronie, „Wszystkie strony” może być odpowiednie.

### 2.2 Dedykowany ekran administracyjny: Lista dymków (Panel administracyjny > Tooltip Pro > Dymki)

Ten ekran służy do zarządzania wszystkimi pojedynczymi dymkami, które chcesz utworzyć i wyświetlić w swoim sklepie. Działa jako centralne centrum do dodawania, edytowania i usuwania wpisów dymków.

- **Nazwa ekranu i lokalizacja menu:** Panel administracyjny > Tooltip Pro > Dymki
- **Dostępne akcje i ustawienia:**
  - **Tabela listy dymków:** Wyświetla listę wszystkich utworzonych dymków, zazwyczaj pokazując słowo kluczowe, treść i jego status (włączony/wyłączony).
  - **Przycisk Dodaj nowy dymek:** Kliknij to, aby utworzyć nowy wpis dymka.
  - **Akcje Edytuj/Usuń:** Każdy dymek na liście będzie miał przyciski akcji (np. ikonę ołówka dla „Edytuj”, ikonę kosza na śmieci dla „Usuń”) do zarządzania pojedynczymi wpisami.
  - **Akcje masowe:** Często istnieją opcje włączania, wyłączania lub usuwania wielu wybranych dymków jednocześnie.

#### Podczas dodawania/edycji dymka:

1.  **Słowo kluczowe:**

    - **Co robi to ustawienie:** Jest to dokładne słowo lub fraza, która po znalezieniu na Twojej stronie internetowej wywoła dymek.
    - **Efekt zmiany tego ustawienia:** Moduł będzie wyszukiwał ten konkretny tekst na włączonych stronach. Wielkość liter może mieć znaczenie w zależności od wewnętrznej logiki modułu (dla najlepszych rezultatów załóż, że jest wrażliwe na wielkość liter).
    - **Zalecana wartość:** Bądź precyzyjny. Użyj dokładnej pisowni i wielkości liter, tak jak pojawia się na Twojej stronie.
    - **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz wyjaśnić „Bawełna Organiczna”, wpisz „Bawełna Organiczna”. Jeśli wpiszesz „bawełna organiczna”, może to nie zadziałać dla „Bawełna Organiczna”.
2.  **Treść dymka:**

    - **Co robi to ustawienie:** Jest to informacja, która zostanie wyświetlona w okienku dymka. Zazwyczaj jest to edytor tekstu sformatowanego (WYSIWYG) umożliwiający różne typy treści.
    - **Efekt zmiany tego ustawienia:** Cokolwiek wpiszesz tutaj, zostanie pokazane klientowi, gdy najedzie kursorem na słowo kluczowe.
    - **Zalecana wartość:** Zachowaj zwięzłość i informatywność. Używaj obrazów, filmów lub linków oszczędnie, aby nie przytłaczać użytkownika.
    - **Scenariusz/przykład dla sprzedawcy:** Dla „Bawełny Organicznej” możesz dodać: „Bawełna organiczna jest uprawiana bez szkodliwych chemikaliów, pestycydów i GMO, co czyni ją lepszą dla środowiska i Twojej skóry. [Link do wpisu na blogu o zrównoważonym rozwoju].”
3.  **Aktywny:**

    - **Co robi to ustawienie:** Kontroluje, czy ten konkretny wpis dymka jest aktywny czy nieaktywny.
    - **Efekt zmiany tego ustawienia:**
      - *Gdy włączone (TAK):* Ten pojedynczy dymek pojawi się w Twoim sklepie.
      - *Gdy wyłączone (NIE):* Ten dymek nie pojawi się, nawet jeśli główny moduł jest włączony.
    - **Zalecana wartość:** TAK (dla dymków, które chcesz wyświetlić).
    - **Scenariusz/przykład dla sprzedawcy:** Możesz tymczasowo wyłączyć dymek, jeśli informacja jest nieaktualna lub jeśli funkcja produktu, którą opisuje, nie jest już dostępna, bez usuwania całego wpisu.

- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. Zacznij od zidentyfikowania typowych pytań lub mylących terminów na stronach produktów, stronach kategorii lub ważnych stronach CMS.
  2. Przejdź do **Panel administracyjny > Tooltip Pro > Dymki**.
  3. Kliknij „Dodaj nowy dymek”.
  4. Wprowadź dokładne **Słowo kluczowe**, które chcesz wyjaśnić.
  5. Stwórz jasną, zwięzłą i pomocną **Treść dymka**.
  6. Upewnij się, że **Aktywny** jest ustawione na TAK.
  7. Zapisz zmiany.
  8. Przetestuj dymek w swoim Front Office, aby upewnić się, że pojawia się poprawnie i dostarcza pożądanych informacji.
  9. Regularnie przeglądaj swoje dymki, aby upewnić się, że informacje pozostają dokładne i aktualne.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz dymki | TAK | Główny przełącznik dla całej funkcjonalności dymków. |
| | Podświetl słowa kluczowe dymków | TAK | Wizualnie zaznacza słowa kluczowe w Front Office. |
| | Położenie dymka | Auto | Pozycja okienka dymka względem słowa kluczowego. |
| | Animacja dymka | Zanikanie / Rozrost | Efekt wizualny, gdy dymek pojawia się/znika. |
| | Motyw dymka | Domyślny / Jasny | Stylizacja (kolory, obramowania) okienka dymka. |
| | Maksymalna szerokość dymka (piksele) | 250-350 | Zapobiega zbyt szerokim dymkom. |
| | Opóźnienie przed pokazaniem (ms) | 200-300 | Czas przed pojawieniem się dymka po najechaniu kursorem. |
| | Opóźnienie przed ukryciem (ms) | 100-200 | Czas przed zniknięciem dymka po najechaniu kursorem. |
| | Dozwolone typy stron | Wybierz według potrzeb | Ogranicza dymki do określonych typów stron (np. Produkt, Kategoria). |
| **Lista dymków (Dodaj/Edytuj)** | Słowo kluczowe | Dokładny tekst | Konkretne słowo/fraza, która wywołuje dymek. |
| | Treść dymka | Zwięzła, informacyjna | Informacje wyświetlane w dymku. |
| | Aktywny | TAK | Włącza/wyłącza pojedynczy wpis dymka. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje dymki nie wyświetlają się w Front Office, mimo że je utworzyłem.**
O:

1.  **Sprawdź główny przełącznik:** Przejdź do **Moduły > Menedżer modułów > Konfiguruj Tooltip Pro**. Upewnij się, że „Włącz dymki” jest ustawione na TAK.
2.  **Sprawdź status pojedynczego dymka:** Przejdź do **Tooltip Pro > Dymki**. Upewnij się, że konkretny dymek, który oczekujesz zobaczyć, ma ustawione „Aktywny” na TAK.
3.  **Sprawdź typ strony:** Zweryfikuj, czy ustawienie „Dozwolone typy stron dla dymków” zawiera typ strony, którą aktualnie przeglądasz (np. jeśli jesteś na stronie produktu, „Strony produktów” muszą być zaznaczone).
4.  **Dopasowanie słowa kluczowego:** Upewnij się, że „Słowo kluczowe”, które wprowadziłeś dla dymka, dokładnie odpowiada tekstowi w Twoim Front Office, włączając w to wielkość liter i spacje.
5.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić wyświetlanie nowych treści. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.

**P: Treść dymka wygląda dziwnie lub nie wyświetla się poprawnie (np. uszkodzone obrazy, dziwne formatowanie).**
O:

1.  **Błędy HTML:** Jeśli użyłeś edytora tekstu sformatowanego, upewnij się, że nie wprowadziłeś żadnych uszkodzonych tagów HTML. Przełącz się na widok kodu źródłowego w edytorze, aby sprawdzić, czy nie ma niezamkniętych tagów lub nieprawidłowych atrybutów.
2.  **Ścieżki obrazów:** Jeśli obrazy się nie wyświetlają, sprawdź, czy adres URL obrazu w treści dymka jest poprawny i dostępny. Używaj bezwzględnych adresów URL (zaczynających się od `http://` lub `https://`) dla obrazów hostowanych na Twoim serwerze.
3.  **Konflikty CSS:** CSS Twojego motywu może nadpisywać styl modułu. Jest to bardziej problem dla programistów, ale możesz spróbować zmienić „Motyw dymka” w konfiguracji modułu, aby sprawdzić, czy inny motyw rozwiąże problem.

**P: Dymki pojawiają się na stronach, na których ich nie chcę.**
O:

1.  **Przejrzyj „Dozwolone typy stron”:** Przejdź do **Moduły > Menedżer modułów > Konfiguruj Tooltip Pro**. Dokładnie przejrzyj „Dozwolone typy stron dla dymków” i odznacz wszystkie typy stron, na których nie chcesz, aby dymki się pojawiały.
2.  **Specyfika słowa kluczowego:** Jeśli słowo kluczowe jest bardzo ogólne (np. „produkt”), może pojawiać się na wielu stronach. Rozważ uczynienie swoich słów kluczowych bardziej szczegółowymi lub ograniczenie ich do określonych typów stron.

**P: Jak przetłumaczyć moje dymki na inne języki?**
O:

1.  **Edytuj dymek:** Przejdź do **Tooltip Pro > Dymki** i kliknij „Edytuj” na dymku, który chcesz przetłumaczyć.
2.  **Selektor języka:** W edytorze tekstu sformatowanego „Treść dymka” powinieneś zobaczyć selektor języka (zazwyczaj ikonę flagi lub rozwijaną listę). Wybierz żądany język i wprowadź przetłumaczoną treść dla tego języka. Powtórz dla wszystkich języków.
3.  **Tłumaczenie słowa kluczowego:** Samo „Słowo kluczowe” zazwyczaj nie jest tłumaczone przez moduł, ponieważ wyszukuje on dokładny tekst na stronie. Jeśli Twoje słowa kluczowe zmieniają się w zależności od języka (np. „Tabela rozmiarów” vs. „Guide des Tailles”), musiałbyś utworzyć oddzielne wpisy dymków dla słowa kluczowego każdego języka.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł Tooltip Pro przestrzega standardowej architektury modułów PrestaShop, wykorzystując zasady MVC. Składa się głównie z:

- Głównej klasy modułu (`index.php`) do instalacji, deinstalacji i konfiguracji.
- Dedykowanych kontrolerów administracyjnych (`AdminTooltipsListController`) do zarządzania encjami dymków w Panelu administracyjnym.
- Kontrolerów Front Office (`ajax.php`) do obsługi dynamicznych żądań treści, jeśli są potrzebne (chociaż podstawowe renderowanie dymków odbywa się po stronie klienta).
- JavaScriptu po stronie klienta (wykorzystującego bibliotekę Tooltipster) do wykrywania słów kluczowych i dynamicznego wyświetlania dymków.
- Niestandardowej tabeli bazy danych (`ps_tooltips`) do przechowywania definicji dymków.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front Office

- `controllers/front/ajax.php`
  - **Nazwa klasy i klasa nadrzędna:** `TooltipsAjaxModuleFrontController` rozszerza `ModuleFrontController`.
  - **Odpowiedzialność:** Ten kontroler jest przeznaczony do obsługi żądań AJAX z Front Office. Chociaż podstawowa treść dymków jest często renderowana bezpośrednio w HTML, ten kontroler mógłby być używany do dynamicznego ładowania treści, pobierania danych dymków na żądanie lub innych interaktywnych funkcji. Odpowiada na specyficzne trasy zdefiniowane przez moduł.
- `controllers/front/index.php`
  - **Nazwa klasy i klasa nadrzędna:** `TooltipsIndexModuleFrontController` rozszerza `ModuleFrontController`.
  - **Odpowiedzialność:** Ten kontroler może służyć jako rezerwowy lub jako placeholder. W wielu prostych modułach `index.php` w katalogu kontrolerów Front Office nie jest bezpośrednio używany do renderowania strony, ale może być obecny dla kompletności architektonicznej lub do obsługi domyślnego routingu modułu, jeśli żaden inny specyficzny kontroler Front Office nie pasuje. Dla Tooltip Pro główna interakcja Front Office odbywa się za pośrednictwem JavaScriptu i hooków.

#### Kontrolery administracyjne Back Office

- `controllers/admin/AdminTooltipsList.php`
  - **Nazwa klasy i klasa nadrzędna:** `AdminTooltipsListController` rozszerza `ModuleAdminController`.
  - **Nazwa zakładki i zarządzana encja:** Ten kontroler zarządza listą „Dymków” w Panelu administracyjnym PrestaShop. Jest odpowiedzialny za wyświetlanie siatki istniejących dymków, obsługę operacji dodawania/edycji/usuwania dla obiektów `Tooltip` oraz renderowanie powiązanych formularzy. Bezpośrednio współdziała z `ObjectModel` `Tooltip`.
- `controllers/admin/index.php`
  - **Nazwa klasy i klasa nadrzędna:** `TooltipsAdminIndexModuleFrontController` rozszerza `ModuleAdminController`.
  - **Nazwa zakładki i zarządzana encja:** Podobnie jak `index.php` w Front Office, może to być placeholder lub domyślny punkt wejścia dla sekcji administracyjnej modułu. Główne zarządzanie jest obsługiwane przez `AdminTooltipsList.php`.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Dossier modułu nie wskazuje na konkretny katalog `classes/`, co oznacza, że główny `ObjectModel` `Tooltip` i powiązana logika mogą być zdefiniowane bezpośrednio w głównym pliku `tooltips/index.php` lub generowane dynamicznie.
Zakładając standardową strukturę modułu PrestaShop, zazwyczaj istniałaby klasa `Tooltip.php`.

- **`Tooltip` (hipotetycznie, prawdopodobnie w `index.php` lub dedykowanym `classes/Tooltip.php`, jeśli istnieje):**
  - **Tabela bazy danych:** `ps_tooltips` (lub `_PREFIX_tooltips`)
  - **Rozszerza `ObjectModel`:** Tak.
  - **Pola `$definition`:**
    - `id_tooltip`: Klucz podstawowy (INT)
    - `keyword`: Ciąg tekstowy do podświetlenia (VARCHAR)
    - `content`: Treść HTML dymka (HTML, TEXT)
    - `active`: Wartość logiczna dla statusu aktywnego/nieaktywnego (TINYINT)
    - `date_add`: Data utworzenia (DATETIME)
    - `date_upd`: Data ostatniej aktualizacji (DATETIME)
    - `id_shop`: ID sklepu dla wielu sklepów (INT)
    - `id_lang`: ID języka dla treści wielojęzycznych (INT)
  - **Kluczowe metody publiczne:** Standardowe metody `ObjectModel` (`add()`, `update()`, `delete()`, `getFields()`). Niestandardowe metody mogą obejmować `getTooltipsByShopAndLang()` lub `getKeywordsForPageType()`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł wykorzystuje bibliotekę `Tooltipster` do swojej funkcjonalności dymków.

- `tooltips/lib/tooltipster/js/plugins/tooltipster/SVG/tooltipster-SVG.js`
  - **Zakres:** Front Office.
  - **Opis:** Wtyczka do biblioteki Tooltipster specjalnie do obsługi elementów SVG. Jeśli Twoje dymki muszą współdziałać z grafiką SVG lub być na niej umieszczone, ta wtyczka zapewnia niezbędną funkcjonalność.
- `tooltips/lib/tooltipster/js/tooltipster.bundle.js`
  - **Zakres:** Front Office.
  - **Opis:** Pełna, spakowana wersja biblioteki Tooltipster, zawierająca jej rdzeń i potencjalnie inne popularne wtyczki. Zapewnia główną funkcjonalność do tworzenia i zarządzania dymkami.
- `tooltips/lib/tooltipster/js/tooltipster.core.js`
  - **Zakres:** Front Office.
  - **Opis:** Podstawowa funkcjonalność biblioteki Tooltipster. Ten plik zawiera podstawową logikę tworzenia, pozycjonowania, zdarzeń i stylizacji dymków.
- `tooltips/views/js/tooltips.js`
  - **Zakres:** Front Office.
  - **Opis:** To jest niestandardowy JavaScript modułu.
    - **Słuchacze zdarzeń:** Prawdopodobnie wiąże się ze zdarzeniem `ready` dokumentu (`$(document).ready()` lub podobnym) w celu inicjalizacji dymków.
    - **Manipulacja DOM:** Skanuje zawartość strony w poszukiwaniu zdefiniowanych słów kluczowych, owija je w określony element HTML (np. `<span class="tooltip-keyword">`), a następnie inicjalizuje bibliotekę Tooltipster na tych elementach.
    - **Inicjalizacja Tooltipster:** Konfiguruje Tooltipster z ustawieniami z Panelu administracyjnego modułu (położenie, animacja, motyw, opóźnienia, maksymalna szerokość).
    - **Wywołania AJAX:** Potencjalnie wykonuje wywołania AJAX do `controllers/front/ajax.php` w celu dynamicznego pobierania treści dymków, chociaż opis modułu sugeruje, że treść jest często wstępnie renderowana.
    - **Interakcja mobilna:** Obsługuje zdarzenia dotyku dla urządzeń mobilnych w celu wywołania dymków.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `tooltips/lib/tooltipster/css/tooltipster.bundle.css`
  - **Zakres:** Stylizacja Front Office dla klienta.
  - **Opis:** Główny arkusz stylów dla biblioteki Tooltipster, zawierający domyślne style dla okienka dymka, strzałek i różnych motywów.
- `tooltips/lib/tooltipster/css/tooltipster.core.css`
  - **Zakres:** Stylizacja Front Office dla klienta.
  - **Opis:** Podstawowy CSS dla biblioteki Tooltipster, definiujący podstawowe właściwości wizualne dla dymków.
- `tooltips/views/css/tooltips-admin.css`
  - **Zakres:** Stylizacja formularzy Panelu administracyjnego.
  - **Opis:** Zawiera specyficzne style dla stron konfiguracji modułu i kontrolera `AdminTooltipsList` w Panelu administracyjnym PrestaShop, zapewniając spójny i przyjazny dla użytkownika interfejs administracyjny.
- `tooltips/views/css/tooltips.css`
  - **Zakres:** Stylizacja Front Office dla klienta.
  - **Opis:** To jest niestandardowy CSS Front Office modułu.
    - **Główne komponenty UI:** Stylizuje podświetlone słowa kluczowe (np. `span.tooltip-keyword`).
    - **Kluczowe selektory klas CSS:** Programiści mogą nadpisywać style dla `.tooltip-keyword` lub specyficznych klas motywów Tooltipster (np. `.tooltipster-base`, `.tooltipster-light`) w pliku `custom.css` swojego motywu lub tworząc plik nadpisujący.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- `tooltips/views/tooltips.tpl`
  - **Zakres:** Szablon hooka Front Office.
  - **Opis:** Ten szablon jest prawdopodobnie podłączony do `displayHeader` lub `displayFooter`, aby wyprowadzić niezbędne zmienne JavaScript i potencjalnie skrypt inicjalizacyjny dla pliku `tooltips.js`. Może przekazywać ustawienia konfiguracyjne z Panelu administracyjnego (np. `tooltip_placement`, `tooltip_animation`, `tooltip_theme`) jako zmienne Smarty do JavaScriptu. Nie renderuje bezpośrednio samej treści dymka, ponieważ jest to obsługiwane dynamicznie przez JavaScript.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - `ps_tooltips`: Przechowuje definicje każdego dymka.
    - `id_tooltip` (PK, INT)
    - `keyword` (VARCHAR)
    - `content` (TEXT, dozwolony HTML)
    - `active` (TINYINT(1))
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
    - `id_shop` (INT)
    - `id_lang` (INT)
  - `ps_configuration`: Przechowuje ustawienia modułu (np. `TOOLTIPS_PRO_ENABLED`, `TOOLTIPS_PRO_HIGHLIGHT`, `TOOLTIPS_PRO_PLACEMENT` itp.).
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykuje pliki CSS i JavaScript (biblioteka Tooltipster, `tooltips.js` i style specyficzne dla modułu) do strony. Wyprowadza również zmienne konfiguracyjne dla JS. |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony Panelu administracyjnego. | Wstrzykuje CSS specyficzny dla administratora (`tooltips-admin.css`) i potencjalnie JS dla stron konfiguracji i listy modułu. |
| `actionFrontControllerSetMedia` | Po ustawieniu mediów dla kontrolera Front Office. | Pozwala modułowi warunkowo dodawać swój CSS/JS w oparciu o bieżący kontekst strony (np. tylko na stronach produktów, jeśli jest skonfigurowany). |
| `moduleRoutes` | Podczas inicjalizacji routera. | Rejestruje niestandardowe trasy Front Office dla `ajax.php`, jeśli używane jest dynamiczne ładowanie treści. |
| `actionObjectTooltipAddAfter` | Po dodaniu obiektu `Tooltip`. | Może być używany do czyszczenia pamięci podręcznej lub logowania. |
| `actionObjectTooltipUpdateAfter` | Po zaktualizowaniu obiektu `Tooltip`. | Może być używany do czyszczenia pamięci podręcznej lub logowania. |
| `actionObjectTooltipDeleteAfter` | Po usunięciu obiektu `Tooltip`. | Może być używany do czyszczenia pamięci podręcznej lub logowania. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu Tooltip Pro, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie doskonałego działania Twojego modułu i pomoc w ulepszaniu Twojego sklepu PrestaShop.
"""
