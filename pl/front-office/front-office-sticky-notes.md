---
title: "Front office Sticky Notes - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Front office Sticky Notes od MyPresta.eu."
sidebar:
  label: "Front office Sticky Notes - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Front office Sticky Notes na MyPresta.eu](https://mypresta.eu/modules/front-office-features/front-office-sticky-notes.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/front-office-sticky-notes/)
>
> ---


# Front office Sticky Notes

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zwykle dostępne w każdym nowoczesnym środowisku hostingowym.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównego ekranu konfiguracji modułu Front office Sticky Notes. To tutaj zarządzasz wszystkimi swoimi karteczkami samoprzylepnymi.

Strona konfiguracji wyświetli listę wszystkich utworzonych karteczek samoprzylepnych. Z tego miejsca możesz:

- **Dodaj nową karteczkę samoprzylepną:** Kliknij przycisk (zazwyczaj „Dodaj nowy” lub ikonę plusa), aby utworzyć nową notatkę.
- **Edytuj istniejącą karteczkę samoprzylepną:** Kliknij ikonę „Edytuj” obok notatki na liście, aby zmodyfikować jej ustawienia.
- **Usuń karteczkę samoprzylepną:** Kliknij ikonę „Usuń” obok notatki, aby usunąć ją ze swojego sklepu.

Podczas dodawania lub edytowania karteczki samoprzylepnej zazwyczaj zobaczysz formularz z następującymi ustawieniami:

- **Treść notatki (Tekst):**

  - **Co robi to ustawienie:** Jest to rzeczywista wiadomość lub tekst, który pojawi się w Twojej karteczce samoprzylepnej. Możesz używać podstawowych tagów HTML (takich jak `<b>` dla pogrubienia, `<i>` dla kursywy, `<br>` dla łamania linii lub `<a>` dla linków), aby formatować tekst i zawierać klikalne linki.
  - **Efekt zmiany tego ustawienia:** Wprowadzony tutaj tekst zostanie wyświetlony Twoim klientom.
  - **Zalecana wartość:** Zachowaj zwięzłość i skuteczność. Na przykład: „Ograniczona ilość!”, „Nowości!”, „Darmowa wysyłka powyżej 75 $!”.
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz ogłosić błyskawiczną wyprzedaż. Wprowadziłbyś: `<b>Błyskawiczna wyprzedaż!</b> 20% zniżki na wszystkie sukienki! <a href="/20-off-dresses">Kup teraz!</a>`
- **Kolor notatki (Kolor tła):**

  - **Co robi to ustawienie:** Pozwala wybrać kolor tła Twojej karteczki samoprzylepnej. Zazwyczaj dostępny jest narzędzie do wyboru koloru dla łatwego wyboru.
  - **Efekt zmiany tego ustawienia:** Karteczka samoprzylepna pojawi się z wybranym kolorem tła. Jest to kluczowe, aby wyróżnić ją lub dopasować do Twojej marki.
  - **Zalecana wartość:** Wybierz kolor, który dobrze kontrastuje z tłem Twojego sklepu i kolorem tekstu, czyniąc notatkę łatwo czytelną i zauważalną. Jasne, ciepłe kolory (żółty, pomarańczowy, jasnozielony) często dobrze sprawdzają się w przyciąganiu uwagi.
  - **Scenariusz / przykład dla sprzedawcy:** Dla wiadomości ostrzegawczej możesz wybrać jasny czerwony lub pomarańczowy. Dla ogólnego ogłoszenia, klasyczny żółty lub jasnoniebieski.
- **Kolor tekstu:**

  - **Co robi to ustawienie:** Ustawia kolor tekstu w Twojej karteczce samoprzylepnej.
  - **Efekt zmiany tego ustawienia:** Tekst zostanie wyświetlony w wybranym kolorze.
  - **Zalecana wartość:** Zawsze wybieraj kolor, który zapewnia wysoki kontrast z wybranym kolorem tła dla optymalnej czytelności. Czarny lub ciemnoszary na jasnym tle, lub biały na ciemnym tle, są zazwyczaj najlepsze.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli tło Twojej notatki jest żółte, wybrałbyś czarny lub ciemnoszary dla tekstu. Jeśli tło jest ciemnoniebieskie, biały tekst byłby idealny.
- **Pozycja (Współrzędna X / Przesunięcie w lewo):**

  - **Co robi to ustawienie:** Określa poziomą pozycję karteczki samoprzylepnej na stronie, mierzoną od lewej krawędzi ekranu lub jej kontenera nadrzędnego. Zazwyczaj jest określana w pikselach (px).
  - **Efekt zmiany tego ustawienia:** Wyższa wartość przesuwa notatkę dalej w prawo. Niższa wartość przesuwa ją bliżej lewej.
  - **Zalecana wartość:** Eksperymentuj, aby znaleźć pozycję, która nie zasłania ważnej treści, ale jest nadal widoczna. Zacznij od wartości takich jak `20px` lub `50px` i dostosuj.
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby notatka pojawiła się nieco na prawo od Twojego głównego logo w nagłówku. Możesz ustawić to na `200px`.
- **Pozycja (Współrzędna Y / Przesunięcie w górę):**

  - **Co robi to ustawienie:** Określa pionową pozycję karteczki samoprzylepnej na stronie, mierzoną od górnej krawędzi ekranu lub jej kontenera nadrzędnego. Zazwyczaj jest określana w pikselach (px).
  - **Efekt zmiany tego ustawienia:** Wyższa wartość przesuwa notatkę dalej w dół strony. Niższa wartość przesuwa ją bliżej góry.
  - **Zalecana wartość:** Zastanów się, gdzie notatka będzie najbardziej efektywna, nie będąc inwazyjną. Dla wiadomości w nagłówku, mała wartość, taka jak `10px` lub `20px`, może działać. Dla notatek na stronie produktu, może być konieczne przewinięcie w dół, aby zobaczyć efekt.
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby notatka pojawiła się tuż pod Twoim głównym paskiem nawigacyjnym. Możesz ustawić to na `100px`.
- **Szerokość:**

  - **Co robi to ustawienie:** Kontroluje szerokość kontenera karteczki samoprzylepnej. Zazwyczaj jest określana w pikselach (px).
  - **Efekt zmiany tego ustawienia:** Większa szerokość pozwala na więcej tekstu w jednej linii, podczas gdy mniejsza szerokość spowoduje częstsze zawijanie tekstu.
  - **Zalecana wartość:** Wybierz szerokość, która wygodnie mieści Twoją wiadomość, nie będąc nadmiernie dużą ani zbyt wąską. `200px` do `300px` to typowy zakres.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja wiadomość jest krótka, `200px` może wystarczyć. Jeśli jest to nieco dłuższe zdanie, `280px` może być lepsze.
- **Wysokość:**

  - **Co robi to ustawienie:** Kontroluje wysokość kontenera karteczki samoprzylepnej. Zazwyczaj jest określana w pikselach (px).
  - **Efekt zmiany tego ustawienia:** Większa wysokość pozwala na więcej linii tekstu. Jeśli tekst przekracza wysokość, może zostać obcięty lub przepełnić się, w zależności od CSS Twojego szablonu.
  - **Zalecana wartość:** Często możesz pozostawić to puste lub ustawić na `auto`, jeśli moduł to obsługuje, pozwalając wysokości dostosować się do treści. Jeśli potrzebujesz stałego rozmiaru, `100px` do `150px` to typowy zakres.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli masz wiadomość wieloliniową, może być konieczne zwiększenie wysokości, aby cały tekst był widoczny.
- **Obrót (Kąt):**

  - **Co robi to ustawienie:** Pozwala obrócić karteczkę samoprzylepną o określony stopień, nadając jej bardziej naturalny wygląd „przyklejonej”.
  - **Efekt zmiany tego ustawienia:** Notatka pojawi się przechylona o określony kąt. Wartości dodatnie obracają zgodnie z ruchem wskazówek zegara, wartości ujemne przeciwnie do ruchu wskazówek zegara.
  - **Zalecana wartość:** Małe obroty, takie jak `3deg`, `-5deg` lub `7deg`, często wyglądają najlepiej, zapewniając subtelny, realistyczny efekt, nie utrudniając czytania tekstu.
  - **Scenariusz / przykład dla sprzedawcy:** Aby notatka wyglądała, jakby była swobodnie przyklejona do strony, możesz ustawić to na `5deg`.
- **Z-Index:**

  - **Co robi to ustawienie:** Ta właściwość CSS określa kolejność nakładania się elementów. Element z wyższą wartością z-index jest umieszczany przed elementami z niższymi wartościami.
  - **Efekt zmiany tego ustawienia:** Jeśli Twoja karteczka samoprzylepna pojawia się za innymi elementami (takimi jak wyskakujące okienka, menu lub banery), zwiększenie jej z-index przeniesie ją na przód.
  - **Zalecana wartość:** Zacznij od stosunkowo wysokiej wartości, takiej jak `999` lub `9999`. Jeśli nadal jest ukryta, zwiększ ją dalej.
  - **Scenariusz / przykład dla sprzedawcy:** Twoja karteczka samoprzylepna jest ukryta za banerem zgody na pliki cookie. Zwiększyłbyś jej Z-Index do `9999`, aby upewnić się, że zawsze jest na wierzchu.
- **Aktywny / Włączony:**

  - **Co robi to ustawienie:** Jest to prosty przełącznik (Tak/Nie) do włączania lub wyłączania karteczki samoprzylepnej bez jej usuwania.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączony:* Karteczka samoprzylepna będzie widoczna w panelu klienta zgodnie z innymi ustawieniami.
    - *Gdy wyłączony:* Karteczka samoprzylepna zostanie ukryta w panelu klienta, ale jej konfiguracja zostanie zapisana, co pozwoli na jej ponowne aktywowanie później.
  - **Zalecana wartość:** „Tak”, gdy chcesz, aby notatka była widoczna; „Nie”, gdy chcesz ją tymczasowo ukryć.
  - **Scenariusz / przykład dla sprzedawcy:** Masz notatkę o sezonowej promocji. Możesz ją wyłączyć po zakończeniu sezonu i ponownie włączyć w przyszłym roku bez ponownego tworzenia.

#### 2.1.1 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Treść notatki (Tekst) | Różne | Wiadomość wyświetlana na karteczce samoprzylepnej. Obsługuje podstawowy HTML. |
| Konfiguracja modułu | Kolor notatki (Tło) | Różne (np. Żółty) | Ustawia kolor tła notatki. Wybierz dla kontrastu. |
| Konfiguracja modułu | Kolor tekstu | Różne (np. Czarny) | Ustawia kolor tekstu. Zapewnij wysoki kontrast z tłem. |
| Konfiguracja modułu | Pozycja (Współrzędna X) | Różne (np. 50px) | Pozioma pozycja od lewej. Dostosuj dla umiejscowienia. |
| Konfiguracja modułu | Pozycja (Współrzędna Y) | Różne (np. 50px) | Pionowa pozycja od góry. Dostosuj dla umiejscowienia. |
| Konfiguracja modułu | Szerokość | Różne (np. 250px) | Szerokość karteczki samoprzylepnej. Wpływa na zawijanie tekstu. |
| Konfiguracja modułu | Wysokość | Różne (np. auto lub 120px) | Wysokość karteczki samoprzylepnej. Wpływa na widoczność treści. |
| Konfiguracja modułu | Obrót (Kąt) | Różne (np. 5deg) | Przechyla notatkę dla realistycznego efektu „przyklejenia”. |
| Konfiguracja modułu | Z-Index | Różne (np. 9999) | Kolejność nakładania. Wyższe wartości pojawiają się na wierzchu innych elementów. |
| Konfiguracja modułu | Aktywny / Włączony | Tak | Przełącza widoczność karteczki samoprzylepnej w panelu klienta. |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P: Moja karteczka samoprzylepna nie wyświetla się w panelu klienta.**
O:

1.  **Sprawdź status „Aktywny”:** Przejdź do konfiguracji modułu i upewnij się, że przełącznik „Aktywny” dla tej konkretnej notatki jest ustawiony na „Tak”.
2.  **Wyczyść pamięć podręczną:** PrestaShop często buforuje zawartość. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.
3.  **Z-Index:** Jeśli Z-Index notatki jest zbyt niski, może być ukryta za innymi elementami. Spróbuj zwiększyć wartość Z-Index (np. do `9999`).
4.  **Pozycjonowanie:** Dokładnie sprawdź współrzędne X i Y. Jeśli są bardzo wysokie, notatka może być poza ekranem. Spróbuj ustawić małe wartości, takie jak `10px` dla obu, aby sprawdzić, czy się pojawi.
5.  **Instalacja modułu:** Upewnij się, że moduł jest poprawnie zainalowany i włączony w **Moduły > Menedżer modułów**.

**P: Tekst mojej karteczki samoprzylepnej jest obcięty lub przepełnia się.**
O:

1.  **Dostosuj szerokość/wysokość:** Zwiększ ustawienia „Szerokość” i/lub „Wysokość” dla tej konkretnej karteczki samoprzylepnej w konfiguracji modułu.
2.  **Sprawdź HTML:** Jeśli używasz HTML, upewnij się, że wszystkie tagi są poprawnie zamknięte (np. `<b>` ma odpowiadający `</b>`). Nieprawidłowy HTML może czasami powodować błędy renderowania.

**P: Karteczka samoprzylepna wygląda inaczej na urządzeniach mobilnych niż na komputerach stacjonarnych.**
O: Moduł dąży do responsywności, ale dokładne umiejscowienie może się różnić ze względu na różne rozmiary ekranu i CSS Twojego szablonu.

1.  **Testuj na urządzeniu:** Zawsze testuj wygląd notatki na rzeczywistych urządzeniach mobilnych lub użyj narzędzi deweloperskich przeglądarki (F12), aby symulować widoki mobilne.
2.  **Dostosuj pozycjonowanie:** Może być konieczne dostosowanie współrzędnych X i Y dla umiejscowienia specyficznego dla urządzeń mobilnych, chociaż moduł może nie oferować oddzielnych ustawień mobilnych. Jeśli jest to poważny problem, zastanów się, czy notatka jest naprawdę niezbędna na urządzeniach mobilnych, czy też potrzebne jest inne podejście.
3.  **Konflikty szablonu:** Czasami CSS Twojego szablonu może powodować konflikty. Jeśli podejrzewasz to, skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojego szablonu.

**P: Jak zrobić z tekstu link?**
O: Możesz użyć standardowych tagów kotwicy HTML w polu „Treść notatki”.
Przykład: `<a href="https://twoj-sklep.com/nowe-produkty">Kliknij tutaj, aby zobaczyć nowości!</a>`
Pamiętaj, aby uwzględnić pełny adres URL, w tym `https://`.

**P: Czy mogę mieć różne karteczki samoprzylepne dla różnych języków?**
O: Tak, moduł obsługuje funkcje wielojęzyczności PrestaShop. Podczas edytowania karteczki samoprzylepnej powinieneś zobaczyć zakładki językowe obok pola „Treść notatki” (i potencjalnie innych pól tekstowych). Wybierz żądaną zakładkę językową i wprowadź przetłumaczoną treść dla tej notatki.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera przegląd techniczny dla programistów i webmasterów, którzy chcą zrozumieć, dostosować lub debugować moduł „Front office Sticky Notes”.

### 4.1 Przegląd architektury

Moduł „Front office Sticky Notes” jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie klasę `Module` do swojej podstawowej funkcjonalności i `ModuleFrontController` do interakcji AJAX. Przechowuje dane konfiguracyjne bezpośrednio w `ps_configuration` i renderuje swoją zawartość za pomocą szablonu Smarty podłączonego do panelu klienta. Moduł używa JavaScript po stronie klienta do dynamicznego zachowania i dedykowanego pliku CSS do stylizacji.

### 4.2 Kontrolery (`controllers/`)

Moduł wykorzystuje kontrolery frontowe do obsługi żądań AJAX związanych z zarządzaniem karteczkami samoprzylepnymi (dodawanie, edytowanie, usuwanie). Nie są to kontrolery pełnostronicowe, ale punkty końcowe dla dynamicznych interakcji.

-   **Kontrolery panelu klienta**:

    -   `controllers/front/add.php`
        -   **Nazwa klasy i klasa nadrzędna**: `StickynotesfoAddModuleFrontController` rozszerzający `ModuleFrontController`
        -   **Odpowiedzialność**: Obsługuje żądania AJAX w celu dodania nowej karteczki samoprzylepnej. Prawdopodobnie otrzymuje dane POST zawierające treść notatki, pozycję, kolory itp., waliduje je i zapisuje do bazy danych (za pomocą klasy `Configuration` lub niestandardowego `ObjectModel`, jeśli taki istniał). Zwraca odpowiedź JSON wskazującą sukces lub porażkę.
    -   `controllers/front/delete.php`
        -   **Nazwa klasy i klasa nadrzędna**: `StickynotesfoDeleteModuleFrontController` rozszerzający `ModuleFrontController`
        -   **Odpowiedzialność**: Obsługuje żądania AJAX w celu usunięcia istniejącej karteczki samoprzylepnej. Oczekuje identyfikatora (np. `id_note`) w żądaniu, usuwa odpowiednie dane z bazy danych i zwraca odpowiedź JSON.
    -   `controllers/front/edit.php`
        -   **Nazwa klasy i klasa nadrzędna**: `StickynotesfoEditModuleFrontController` rozszerzający `ModuleFrontController`
        -   **Odpowiedzialność**: Obsługuje żądania AJAX w celu aktualizacji istniejącej karteczki samoprzylepnej. Otrzymuje dane POST z ID notatki i zaktualizowanymi właściwościami, modyfikuje rekord w bazie danych i zwraca odpowiedź JSON.
    -   `controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: `StickynotesfoIndexModuleFrontController` rozszerzający `ModuleFrontController`
        -   **Odpowiedzialność**: Ten kontroler może służyć jako ogólny punkt wejścia dla żądań AJAX lub może być rezerwowym. Biorąc pod uwagę specyficzne kontrolery `add`, `delete`, `edit`, `index.php` może obsługiwać listowanie notatek lub inne ogólne interakcje nieobjęte specyficznymi operacjami CRUD.
-   **Kontrolery administracyjne panelu administracyjnego**: Brak wykrytych. Cała konfiguracja panelu administracyjnego jest obsługiwana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Nie wykryto niestandardowych definicji `classes/` ani `ObjectModel`. Moduł prawdopodobnie przechowuje swoją konfigurację bezpośrednio w tabeli `ps_configuration` PrestaShop, używając unikalnych kluczy dla właściwości każdej karteczki samoprzylepnej. Takie podejście jest typowe dla prostszych modułów zarządzających ograniczoną liczbą ustawień.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `js/advajax.js`
    -   **Zakres**: Prawdopodobnie panel klienta.
    -   **Opis**: Ten plik sugeruje niestandardowy lub zewnętrzny skrypt narzędziowy AJAX. Prawdopodobnie dostarcza funkcji pomocniczych do wykonywania asynchronicznych żądań do kontrolerów frontowych modułu (`add.php`, `delete.php`, `edit.php`). Może hermetyzować wspólne wzorce AJAX, obsługę błędów lub serializację danych. Programiści powinni przejrzeć ten plik, aby zrozumieć, jak strukturyzowane i inicjowane są wywołania AJAX w module.
-   `js/jscolor/jscolor.js`
    -   **Zakres**: Panel administracyjny (do konfiguracji).
    -   **Opis**: Jest to zewnętrzna biblioteka JavaScript do wyboru kolorów. Jest używana w formularzu konfiguracji modułu w panelu administracyjnym, aby zapewnić przyjazny dla użytkownika interfejs do wyboru kolorów notatek i tekstu. Wiąże się z polami wejściowymi o określonej klasie lub ID, przekształcając je w interaktywne narzędzia do wyboru kolorów.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `css/stickynotes.css`
    -   **Zakres**: Stylizacja panelu klienta.
    -   **Opis**: Jest to główny arkusz stylów dla karteczek samoprzylepnych wyświetlanych w panelu klienta. Definiuje wygląd wizualny notatek, w tym:
        -   Podstawową stylizację kontenera karteczki samoprzylepnej (np. `position: absolute;`, `background-color`, `border-radius`).
        -   Stylizację tekstu w notatce (`font-size`, `color`, `line-height`).
        -   Efekt „odklejenia” lub obrotu (prawdopodobnie za pomocą `transform: rotate()`).
        -   `z-index` w celu zapewnienia widoczności.
        -   Potencjalnie responsywne dostosowania dla różnych rozmiarów ekranu za pomocą zapytań mediów.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać**: Programiści powinni sprawdzić renderowany HTML, aby zidentyfikować główną klasę kontenera (np. `.sticky-note`, `.stickynotesfo-item`) i jej elementy potomne, aby zastosować niestandardową stylizację w pliku `custom.css` lub `theme.css` swojego szablonu.

### 4.6 Struktura szablonu Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/front/`)**:
    -   `views/templates/front/sticky-notes-front-office.tpl`
        -   **Hook**: Ten szablon jest prawdopodobnie renderowany w ogólnym hooku panelu klienta, takim jak `displayHeader`, `displayFooter` lub potencjalnie `displayBeforeBodyClosingTag`. Metoda `hookDisplayHeader` lub `hookDisplayFooter` modułu zazwyczaj pobiera wszystkie aktywne karteczki samoprzylepne z bazy danych i przypisuje je do tego szablonu.
        -   **Wyjście bloku wizualnego**: Ten szablon jest odpowiedzialny za iterowanie po liście aktywnych karteczek samoprzylepnych i renderowanie struktury HTML dla każdej z nich. Dynamicznie wstawi treść notatki, kolory, pozycje, szerokość, wysokość, obrót i z-index jako style inline lub atrybuty danych, które są następnie pobierane przez `stickynotes.css` i potencjalnie `advajax.js` do dynamicznych aktualizacji. Każda notatka będzie prawdopodobnie elementem `div` z unikalnymi ID lub klasami.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy niestandardowych tabel SQL. Zamiast tego przechowuje swoje dane konfiguracyjne w tabeli `ps_configuration` PrestaShop. Właściwości każdej karteczki samoprzylepnej (treść, kolor, pozycja itp.) są przechowywane jako indywidualne klucze konfiguracyjne, prawdopodobnie poprzedzone prefiksem `STICKYNOTESFO_NOTE_`, a następnie unikalnym identyfikatorem (np. `STICKYNOTESFO_NOTE_1_CONTENT`, `STICKYNOTESFO_NOTE_1_COLOR`). Pola wielojęzyczne używałyby sufiksów `_LANG_ID`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany na końcu sekcji `<head>` każdej strony panelu klienta. | Idealny do wstrzykiwania CSS, JavaScript i potencjalnie początkowej struktury HTML karteczek samoprzylepnych, zapewniając ich dostępność wcześnie w DOM. |
| `displayFooter` | Wykonywany na końcu sekcji `<body>` każdej strony panelu klienta. | Może być używany do wstrzykiwania HTML karteczek samoprzylepnych, zwłaszcza jeśli mają one pływać lub być pozycjonowane absolutnie względem obszaru widoku. |
| `displayLeftColumn` | Wykonywany w lewej kolumnie stron, które ją posiadają. | Umożliwia umieszczanie karteczek samoprzylepnych specjalnie w lewym pasku bocznym. |
| `displayRightColumn` | Wykonywany w prawej kolumnie stron, które ją posiadają. | Umożliwia umieszczanie karteczek samoprzylepnych specjalnie w prawym pasku bocznym. |
| `displayProductAdditionalInfo` (lub podobny hook strony produktu) | Wykonywany na stronie produktu, zazwyczaj w pobliżu opisu produktu lub przycisku dodania do koszyka. | Umożliwia umieszczanie karteczek samoprzylepnych specyficznych dla poszczególnych stron produktów. |
| `actionFrontControllerSetMedia` | Wykonywany, gdy kontroler frontowy ustawia swoje media (CSS/JS). | Używany przez moduł do rejestrowania plików `stickynotes.css` i `advajax.js` do wyświetlania w panelu klienta. |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje media (CSS/JS). | Używany przez moduł do rejestrowania `jscolor.js` i innych specyficznych dla administratora CSS/JS dla swojej strony konfiguracji. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkiej dalszej pomocy z modułem „Front office Sticky Notes” prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnianie terminowego wsparcia i zapewnienie optymalnego funkcjonowania modułu.
