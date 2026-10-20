---
title: "Html box - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Html box od MyPresta.eu."
sidebar:
  label: "Html box - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Html box na MyPresta.eu](https://mypresta.eu/modules/front-office-features/html-box.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/html-box/)
>
> ---


# Html box

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do instalacji PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Html box)

Jest to główny ekran konfiguracji, na którym definiujesz zawartość swoich pól HTML i miejsce ich wyświetlania.

#### Ustawienia ogólne

-   **Włącz SSL (https) dla tego modułu?** (`htmlbox_ssl`)

    *   **Co robi to ustawienie:** Określa, czy zawartość modułu powinna być ładowana bezpiecznie przez HTTPS.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po włączeniu (TAK):* Zapewnia, że wszelka zawartość generowana przez ten moduł jest serwowana przez HTTPS, zapobiegając ostrzeżeniom o „mieszanej zawartości” w przeglądarkach, jeśli Twój sklep używa SSL.
        *   *Po wyłączeniu (NIE):* Zawartość może być serwowana przez HTTP, co może powodować ostrzeżenia bezpieczeństwa w sklepach z włączonym HTTPS.
    *   **Zalecana wartość:** **TAK**
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój sklep używa HTTPS (co powinien!), włączenie tego zapewnia, że Twoja niestandardowa zawartość nie wywoła alertów bezpieczeństwa dla Twoich klientów.
-   **Wyłącz edytor TinyMCE?** (`htmlbox_disabletiny`)

    *   **Co robi to ustawienie:** Kontroluje, czy edytor tekstu sformatowanego (TinyMCE) jest używany do wprowadzania treści HTML.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po włączeniu (TAK):* Zobaczysz zwykłe pole tekstowe do wprowadzania kodu HTML, JavaScript lub CSS. Jest to przydatne, jeśli wklejasz złożony kod, który TinyMCE mógłby próbować „oczyścić”, lub jeśli wolisz pisać czysty HTML.
        *   *Po wyłączeniu (NIE):* Będziesz miał przyjazny dla użytkownika edytor tekstu sformatowanego, podobny do edytora tekstu, umożliwiający formatowanie tekstu, dodawanie obrazów i tworzenie linków bez bezpośredniego pisania HTML.
    *   **Zalecana wartość:** **NIE** (chyba że jesteś programistą lub wklejasz złożony kod).
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz szybko dodać pogrubione ogłoszenie tekstowe, pozostaw to wyłączone. Jeśli wklejasz kod widżetu Facebooka, włącz to, aby zapobiec zmianie kodu przez edytor.
-   **Pokaż tylko dla zalogowanych klientów?** (`htmlbox_logged`)

    *   **Co robi to ustawienie:** Ogranicza widoczność zawartości pola HTML tylko do klientów, którzy są zalogowani na swoje konta.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po włączeniu (TAK):* Tylko zarejestrowani i zalogowani klienci zobaczą zawartość pola HTML.
        *   *Po wyłączeniu (NIE):* Wszyscy odwiedzający, niezależnie od tego, czy są zalogowani, czy nie, zobaczą zawartość.
    *   **Zalecana wartość:** **NIE** (chyba że masz specyficzną zawartość dla zalogowanych użytkowników).
    *   **Scenariusz / przykład dla sprzedawcy:** Możesz włączyć to, jeśli chcesz wyświetlić specjalną wiadomość programu lojalnościowego lub ekskluzywne oferty widoczne tylko dla Twojej istniejącej bazy klientów.
-   **Pokaż tylko dla NIEzalogowanych klientów?** (`htmlbox_unlogged`)

    *   **Co robi to ustawienie:** Ogranicza widoczność zawartości pola HTML tylko do klientów, którzy *nie* są zalogowani na swoje konta.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po włączeniu (TAK):* Tylko odwiedzający, którzy nie są zalogowani, zobaczą zawartość pola HTML.
        *   *Po wyłączeniu (NIE):* Wszyscy odwiedzający, niezależnie od tego, czy są zalogowani, czy nie, zobaczą zawartość.
    *   **Zalecana wartość:** **NIE** (chyba że masz specyficzną zawartość dla gości).
    *   **Scenariusz / przykład dla sprzedawcy:** Możesz włączyć to, aby wyświetlić wiadomość „Zaloguj się lub zarejestruj, aby uzyskać ekskluzywne oferty” w celu zachęcenia nowych użytkowników do rejestracji lub powracających klientów do zalogowania się.

#### Pola zawartości pola HTML

Te pola służą do wprowadzania rzeczywistej zawartości HTML, JavaScript lub CSS dla każdego konkretnego hooka. Każde pole odpowiada innej lokalizacji w Twoim sklepie.

-   **HTML dla nagłówka (displayTop, displayNav1, displayNav2)** (`htmlbox_header`)

    *   **Co robi to ustawienie:** Jest to zawartość, która pojawi się w sekcji nagłówka Twojego sklepu. W zależności od Twojego motywu, może to być `displayTop`, `displayNav1` lub `displayNav2`.
    *   **Efekt zmiany tego ustawienia:** Wprowadzona tutaj zawartość będzie widoczna na samej górze Twojej strony internetowej.
    *   **Zalecana wartość:** Pozostaw puste, jeśli nie jest potrzebne.
    *   **Scenariusz / przykład dla sprzedawcy:** Baner z ogłoszeniem na całej stronie („Darmowa wysyłka na wszystkie zamówienia powyżej 50$!”), mały pasek ikon mediów społecznościowych lub niestandardowy pasek wyszukiwania.
-   **HTML dla górnej kolumny (displayTopColumn)** (`htmlbox_top`)

    *   **Co robi to ustawienie:** Ta zawartość pojawia się tuż pod nagłówkiem, często rozciągając się na całą szerokość głównego obszaru treści.
    *   **Efekt zmiany tego ustawienia:** Wprowadzona tutaj zawartość będzie wyraźnie wyświetlana na górze głównego obszaru treści, zazwyczaj powyżej głównych list produktów lub zawartości strony głównej.
    *   **Zalecana wartość:** Pozostaw puste, jeśli nie jest potrzebne.
    *   **Scenariusz / przykład dla sprzedawcy:** Duży baner promocyjny na wyprzedaż sezonową, slider z wyróżnionymi produktami lub wideo wprowadzające do Twojej marki.
-   **HTML dla lewej kolumny (displayLeftColumn)** (`htmlbox_leftcol`)

    *   **Co robi to ustawienie:** Ta zawartość pojawia się w lewym pasku bocznym Twojego sklepu (jeśli Twój motyw go ma i jest włączony).
    *   **Efekt zmiany tego ustawienia:** Wprowadzona tutaj zawartość będzie wyświetlana w lewej kolumnie, obok innych modułów, takich jak filtry kategorii lub nawigacja.
    *   **Zalecana wartość:** Pozostaw puste, jeśli nie jest potrzebne.
    *   **Scenariusz / przykład dla sprzedawcy:** Lista „Kupuj według marki”, formularz zapisu do newslettera, mała reklama dla konkretnej kategorii produktów lub pole „Lubię to” na Facebooku.
-   **HTML dla prawej kolumny (displayRightColumn)** (`htmlbox_rightcol`)

    *   **Co robi to ustawienie:** Ta zawartość pojawia się w prawym pasku bocznym Twojego sklepu (jeśli Twój motyw go ma i jest włączony).
    *   **Efekt zmiany tego ustawienia:** Wprowadzona tutaj zawartość będzie wyświetlana w prawej kolumnie, podobnie jak w lewej kolumnie.
    *   **Zalecana wartość:** Pozostaw puste, jeśli nie jest potrzebne.
    *   **Scenariusz / przykład dla sprzedawcy:** Lista „Bestsellery”, blok kontaktowy obsługi klienta, kanał Pinterest lub sekcja „Ostatnio oglądane produkty”.
-   **HTML dla stopki (displayFooter)** (`htmlbox_footercol`)

    *   **Co robi to ustawienie:** Ta zawartość pojawia się w sekcji stopki na dole każdej strony.
    *   **Efekt zmiany tego ustawienia:** Wprowadzona tutaj zawartość będzie widoczna na samym dole Twojej strony internetowej.
    *   **Zalecana wartość:** Pozostaw puste, jeśli nie jest potrzebne.
    *   **Scenariusz / przykład dla sprzedawcy:** Logo metod płatności, pieczęcie zaufania, krótki opis „O nas”, linki do mediów społecznościowych lub niestandardowa informacja o prawach autorskich.
-   **HTML dla strony głównej (displayHome)** (`htmlbox_homecol`)

    *   **Co robi to ustawienie:** Ta zawartość jest wyświetlana specjalnie na stronie głównej Twojego sklepu.
    *   **Efekt zmiany tego ustawienia:** Wprowadzona tutaj zawartość będzie centralnym elementem układu Twojej strony głównej.
    *   **Zalecana wartość:** Pozostaw puste, jeśli nie jest potrzebne.
    *   **Scenariusz / przykład dla sprzedawcy:** Siatka wyróżnionych kategorii, sekcja „Dlaczego warto u nas kupować”, referencje klientów lub duży przycisk wezwania do działania.
-   **HTML dla ciała (displayBody)** (`htmlbox_body`)

    *   **Co robi to ustawienie:** Ta zawartość jest wstrzykiwana do tagu `<body>` Twojego HTML, zazwyczaj na samym końcu przed zamykającym tagiem `</body>`. Jest często używana do globalnych skryptów lub elementów, które muszą być dostępne na całej stronie, ale nie są wizualnie powiązane z konkretną sekcją.
    *   **Efekt zmiany tego ustawienia:** Zawartość będzie obecna na każdej stronie Twojego sklepu, ale jej wizualne umiejscowienie może zależeć od CSS Twojego motywu. Jest doskonała do kodów śledzących lub wyskakujących okienek.
    *   **Zalecana wartość:** Pozostaw puste, jeśli nie jest potrzebne.
    *   **Scenariusz / przykład dla sprzedawcy:** Kod śledzenia Google Analytics, piksel Facebooka, globalny baner zgody na pliki cookie (jeśli nie jest obsługiwany przez inny moduł) lub skrypt widżetu czatu.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz SSL (https) dla tego modułu? | TAK | Zapewnia bezpieczne ładowanie treści, zapobiegając ostrzeżeniom o mieszanej zawartości. |
| Konfiguracja modułu | Wyłącz edytor TinyMCE? | NIE | Kontroluje edytor tekstu sformatowanego do wprowadzania treści. Włącz dla surowego kodu. |
| Konfiguracja modułu | Pokaż tylko dla zalogowanych klientów? | NIE | Ogranicza widoczność treści do zalogowanych użytkowników. |
| Konfiguracja modułu | Pokaż tylko dla NIEzalogowanych klientów? | NIE | Ogranicza widoczność treści do gości. |
| Konfiguracja modułu | HTML dla nagłówka | Puste | Niestandardowa zawartość w obszarze nagłówka (np. ogłoszenia, górne banery). |
| Konfiguracja modułu | HTML dla górnej kolumny | Puste | Niestandardowa zawartość poniżej nagłówka, często na całą szerokość (np. główne promocje). |
| Konfiguracja modułu | HTML dla lewej kolumny | Puste | Niestandardowa zawartość w lewym pasku bocznym (np. kanały społecznościowe, newsletter). |
| Konfiguracja modułu | HTML dla prawej kolumny | Puste | Niestandardowa zawartość w prawym pasku bocznym (np. bestsellery, obsługa klienta). |
| Konfiguracja modułu | HTML dla stopki | Puste | Niestandardowa zawartość w stopce (np. logo płatności, pieczęcie zaufania). |
| Konfiguracja modułu | HTML dla strony głównej | Puste | Niestandardowa zawartość specjalnie na stronie głównej (np. wyróżnione produkty). |
| Konfiguracja modułu | HTML dla ciała | Puste | Globalna zawartość/skrypty wstrzykiwane do `<body>` (np. analityka, widżety czatu). |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Mój niestandardowy HTML nie wyświetla się lub wygląda na uszkodzony.**
O:

1.  **Sprawdź hook:** Upewnij się, że wprowadziłeś zawartość w prawidłowym polu Html box dla żądanej lokalizacji (np. `HTML dla strony głównej` dla strony głównej).
2.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). PrestaShop często buforuje zawartość, a nowe ustawienia modułu mogą nie pojawić się natychmiast.
3.  **Sprawdź HTML:** Jeśli czujesz się komfortowo, użyj narzędzi deweloperskich przeglądarki (F12), aby sprawdzić obszar, w którym powinna znajdować się zawartość. Poszukaj błędów w konsoli lub sprawdź, czy Twój HTML jest obecny, ale nieprawidłowo ostylowany.
4.  **Interferencja TinyMCE:** Jeśli wklejasz złożony kod (zwłaszcza JavaScript lub iframes), spróbuj włączyć „Wyłącz edytor TinyMCE?”, aby upewnić się, że edytor nie usuwa ani nie zmienia Twojego kodu.

**P: Zawartość pojawia się, ale nie wygląda dobrze na urządzeniach mobilnych.**
O: Sam moduł jest responsywny, ale *dodana przez Ciebie zawartość* również musi być responsywna.

1.  **Użyj responsywnego HTML/CSS:** Jeśli piszesz niestandardowy HTML, upewnij się, że używasz zasad responsywnego projektowania (np. `max-width: 100%` dla obrazów, zapytania mediów CSS).
2.  **Widżety stron trzecich:** Jeśli osadzasz widżet (taki jak Facebook lub Twitter), sprawdź, czy dostawca widżetu oferuje responsywne kody osadzania lub ustawienia.
3.  **Prosta zawartość:** W przypadku krytycznej zawartości mobilnej, zachowaj prostotę: zwykły tekst, małe obrazy i wyraźne wezwania do działania.

**P: Dodałem JavaScript, ale nie jest wykonywany.**
O:

1.  **Umiejscowienie:** JavaScript dodany do pola `HTML dla ciała` jest zazwyczaj najbezpieczniejszym miejscem dla globalnych skryptów, ponieważ jest ładowany na końcu strony.
2.  **Błędy składni:** Sprawdź swój kod JavaScript pod kątem błędów składniowych. Pojedynczy błąd może uniemożliwić uruchomienie całego skryptu.
3.  **Konflikty jQuery:** Jeśli Twój skrypt opiera się na jQuery, upewnij się, że jest on prawidłowo załadowany i że nie ma konfliktów z wersją jQuery PrestaShop. Może być konieczne opakowanie kodu w `(function($){ /* Twój kod */ })(jQuery);` lub użycie `jQuery.noConflict();`.
4.  **Skrypty zewnętrzne:** Jeśli łączysz się z zewnętrznym plikiem `.js`, upewnij się, że adres URL jest poprawny i dostępny.

**P: Jak przetłumaczyć zawartość moich pól HTML na różne języki?**
O: Obecna wersja modułu nie oferuje wbudowanych pól wielojęzycznych dla każdego pola HTML. Aby uzyskać zawartość wielojęzyczną, masz dwie główne opcje:

1.  **Ręczne wykrywanie języka (zaawansowane):** Możesz osadzić logikę warunkową w zawartości pola HTML za pomocą zmiennych Smarty (jeśli Twój motyw pozwala na przetwarzanie Smarty w hookach) lub JavaScript, aby wykryć bieżący język i wyświetlić inną zawartość. Jest to bardziej zaawansowane rozwiązanie.
    *Przykład (Smarty):*

    ```
    {if $language.iso\_code == 'en'} <p>Welcome to our English store!</p>{elseif $language.iso\_code == 'fr'} <p>Bienvenue dans notre boutique française !</p>{/if}
    ```
2.  **Oddzielne moduły (obejście):** W przypadku krytycznej zawartości możesz rozważyć zainstalowanie oddzielnych instancji modułu „Html box” (jeśli jest to dozwolone przez dewelopera modułu lub poprzez duplikowanie modułu) i przypisanie każdej z nich do konkretnego języka, a następnie zarządzanie ich wyświetlaniem za pomocą pozycji modułów PrestaShop. Jest to bardziej złożone obejście.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem Html box.

### 4.1 Przegląd architektury

Moduł `Html box` to prosty moduł PrestaShop zaprojektowany przede wszystkim do wstrzykiwania niestandardowej zawartości HTML/JS/CSS do różnych hooków front-office. Przestrzega klasycznej struktury modułu PrestaShop, wykorzystując klasę `Module` do instalacji, deinstalacji i konfiguracji, oraz metody `hook` do renderowania zawartości w front-office. Konfiguracja jest zarządzana za pomocą metody `getContent()`, która renderuje standardowy formularz konfiguracji PrestaShop. Moduł przechowuje swoją zawartość bezpośrednio w tabeli `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała funkcjonalność, w tym konfiguracja i renderowanie front-office, jest obsługiwana bezpośrednio w głównym pliku modułu `htmlbox.php`.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł **nie** definiuje żadnych niestandardowych klas ani instancji `ObjectModel`. Wszystkie dane są przechowywane jako wartości konfiguracyjne.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`htmlbox/tinymce16.inc.js`**
    *   **Zakres:** Back-office (konkretnie strona konfiguracji modułu).
    *   **Cel:** Ten plik jest odpowiedzialny za inicjalizację i konfigurację edytora tekstu sformatowanego TinyMCE w formularzu konfiguracji modułu. Przekształca standardowe elementy `<textarea>` w przyjazny dla użytkownika edytor WYSIWYG, umożliwiając sprzedawcom formatowanie tekstu, wstawianie obrazów i zarządzanie zawartością HTML bez bezpośredniego kodowania. Prawdopodobnie zawiera niestandardowe ustawienia do integracji TinyMCE z menedżerem plików PrestaShop do przesyłania obrazów.
    *   **Uwagi dla programistów:** Jeśli `htmlbox_disabletiny` jest włączone, ten skrypt nie zostanie załadowany lub jego funkcjonalność zostanie pominięta. Programiści, którzy chcą dostosować doświadczenie TinyMCE (np. dodając niestandardowe przyciski, zmieniając układ paska narzędzi), musieliby zmodyfikować ten plik lub nadpisać jego ładowanie/konfigurację.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików CSS. Wszelkie style dla wstrzykniętej zawartości HTML muszą być dostarczone w samej zawartości HTML (style inline lub tagi `<style>`) lub przez aktywny motyw PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`views/templates/hook/html.tpl`**
    *   **Zakres:** Front-office.
    *   **Renderowanie hooka:** Jest to główny plik szablonu używany przez moduł do renderowania niestandardowej zawartości HTML we wszystkich zarejestrowanych hookach front-office.
    *   **Zawartość:** Prawdopodobnie zawiera prostą strukturę do wyprowadzania zmiennej `$html_content`, która jest przekazywana z metod hooka modułu.
    *   **Uwagi dla programistów:** Ten szablon jest minimalny. Rzeczywista zawartość jest dynamicznie ładowana z tabeli `ps_configuration` na podstawie hooka. Programiści mogą nadpisać ten szablon w swoim motywie (np. `themes/yourtheme/modules/htmlbox/html.tpl`), aby opakować zawartość w niestandardowe `div`y, dodać specyficzne klasy lub zastosować logikę warunkową, chociaż większość dostosowań zostanie wykonana bezpośrednio w samej zawartości pola HTML.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Cała konfiguracja i zawartość są przechowywane w standardowej tabeli PrestaShop `ps_configuration` przy użyciu następujących kluczy:

    -   `mypresta_updates`
    -   `update_`
    -   `updatev_`
    -   `htmlbox_header`
    -   `htmlbox_top`
    -   `htmlbox_leftcol`
    -   `htmlbox_rightcol`
    -   `htmlbox_footercol`
    -   `htmlbox_homecol`
    -   `htmlbox_body`
    -   `htmlbox_ssl`
    -   `htmlbox_origtiny`
    -   `htmlbox_disabletiny`
    -   `htmlbox_home`
    -   `htmlbox_hook`
    -   `htmlbox_logged`
    -   `htmlbox_unlogged`
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Głównie do dodawania meta tagów, linków CSS lub JavaScript, które muszą zostać załadowane wcześnie. |
| `displayTop` | Górna sekcja strony, zazwyczaj powyżej głównej zawartości. | Ogólna zawartość dla góry strony, często zależna od motywu. |
| `displayNav1` | Pasek nawigacji, często bardzo górny pasek z szybkimi linkami. | Zawartość dla pierwszego paska nawigacji. |
| `displayNav2` | Drugi pasek nawigacji, często poniżej `displayNav1`. | Zawartość dla drugiego paska nawigacji. |
| `displayTopColumn` | Obszar na całą szerokość poniżej nagłówka, powyżej głównej zawartości. | Widoczny obszar treści, często używany do banerów lub sliderów. |
| `displayLeftColumn` | Lewy pasek boczny na stronach, gdzie jest włączony. | Zawartość dla lewego paska bocznego (np. filtry, kategorie, niestandardowe bloki). |
| `displayRightColumn` | Prawy pasek boczny na stronach, gdzie jest włączony. | Zawartość dla prawego paska bocznego (np. reklamy, widżety społecznościowe). |
| `displayHome` | Główny obszar treści strony głównej. | Zawartość specjalnie dla strony głównej. |
| `displayFooter` | Dolna sekcja każdej strony. | Zawartość dla stopki (np. prawa autorskie, logo płatności, linki). |
| `displayBody` | Na końcu tagu `<body>`. | Idealne dla globalnego JavaScript (np. analityka, widżety czatu) lub elementów, które powinny ładować się jako ostatnie. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu zapewnia dedykowane wsparcie dla wszystkich swoich modułów.
"""
