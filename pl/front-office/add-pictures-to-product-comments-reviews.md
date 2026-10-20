---
title: "Dodawanie zdjęć do komentarzy (recenzji) produktów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Dodawanie zdjęć do komentarzy (recenzji) produktów” od MyPresta.eu."
sidebar:
  label: "Dodawanie zdjęć do komentarzy (recenzji) produktów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Add pictures to product comments (reviews) na MyPresta.eu](https://mypresta.eu/modules/front-office-features/add-pictures-to-product-comments-reviews.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/add-pictures-to-product-comments-reviews/)
>
> ---


# Dodawanie zdjęć do komentarzy (recenzji) produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).
- **Zależność**: Ten moduł wymaga zainstalowania i aktywowania modułu „Komentarze produktów” (opracowanego przez MyPresta.eu), ponieważ rozszerza jego funkcjonalność.

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Dodawanie zdjęć do komentarzy (recenzji) produktów” w Menedżerze modułów. Spowoduje to przejście do jego głównego ekranu konfiguracji.

Konfiguracja modułu jest prosta i koncentruje się głównie na włączaniu lub wyłączaniu jego podstawowej funkcjonalności.

**Ustawienia i opcje:**

- **Włącz przesyłanie zdjęć dla komentarzy produktów:**
  - **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji podstawowej funkcjonalności modułu. Po włączeniu, Twoi klienci zobaczą opcję przesyłania zdjęć, gdy piszą recenzję produktu.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu (TAK):* Pole przesyłania obrazów pojawi się w formularzu przesyłania recenzji produktu na stronach Twoich produktów. Klienci będą mogli dołączać obrazy do swoich recenzji. Istniejące recenzje z obrazami również będą wyświetlać te obrazy.
    - *Po wyłączeniu (NIE):* Pole przesyłania obrazów zostanie ukryte z formularza przesyłania recenzji produktu. Klienci będą mogli przesyłać tylko recenzje tekstowe. Istniejące recenzje z obrazami mogą nadal je wyświetlać, ale nie będzie można dodawać nowych obrazów.
  - **Zalecana wartość:** **TAK**. Aby wykorzystać korzyści płynące z recenzji wizualnych, należy włączyć tę funkcję.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz umożliwić klientom pokazanie swojej nowej sukienki lub tego, jak działa gadżet w prawdziwym życiu, włącz tę opcję. Jeśli tymczasowo chcesz ograniczyć przesyłanie obrazów w celu konserwacji lub konkretnej kampanii, możesz ją wyłączyć.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Włącz przesyłanie zdjęć dla komentarzy produktów | TAK | Kontroluje, czy klienci mogą przesyłać zdjęcia wraz z recenzjami produktów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Włączyłem moduł, ale nie widzę pola do przesyłania zdjęć na stronie mojego produktu.**
O:

1. **Sprawdź moduł „Komentarze produktów”:** Ten moduł rozszerza moduł „Komentarze produktów”. Upewnij się, że moduł „Komentarze produktów” (od MyPresta.eu) jest zainstalowany, włączony i poprawnie skonfigurowany w Twoim sklepie.
2. **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Czasami stare pliki pamięci podręcznej uniemożliwiają pojawienie się nowych funkcji modułu.
3. **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany z myślą o szerokiej kompatybilności, niestandardowe motywy mogą czasami nadpisywać domyślne struktury szablonów. Jeśli wyczyszczenie pamięci podręcznej nie pomoże, skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojego motywu.

**P: Moi klienci przesyłają zdjęcia, ale nie pojawiają się one obok recenzji.**
O:

1. **Moderacja recenzji:** Sprawdź, czy moduł „Komentarze produktów” ma włączoną moderację recenzji. Jeśli tak, nowe recenzje (i związane z nimi zdjęcia) pojawią się dopiero po ich zatwierdzeniu w Panelu administracyjnym.
2. **Sprawdź konfigurację modułu:** Upewnij się, że opcja „Włącz przesyłanie zdjęć dla komentarzy produktów” jest ustawiona na TAK w konfiguracji tego modułu.
3. **Uprawnienia do plików:** Upewnij się, że katalog `img/p/` (lub gdziekolwiek PrestaShop przechowuje obrazy produktów) ma prawidłowe uprawnienia do zapisu (zazwyczaj 755 lub 775). Jeśli serwer nie może zapisywać plików, obrazy nie zostaną zapisane.

**P: Czy mogę ograniczyć liczbę zdjęć, które klient może przesłać do jednej recenzji?**
O: Ten konkretny moduł zapewnia podstawową funkcję przesyłania. Zaawansowane kontrole, takie jak ograniczenie liczby obrazów lub rozmiaru pliku, mogą wymagać niestandardowych modyfikacji lub aktualizacji podstawowego modułu „Komentarze produktów”. Sprawdź ustawienia modułu „Komentarze produktów” lub skontaktuj się z pomocą techniczną MyPresta.eu w sprawie takich funkcji.

**P: Przesłane zdjęcia wyglądają na zniekształcone lub nie są wyświetlane poprawnie.**
O:

1. **Konflikty CSS:** CSS Twojego motywu może kolidować ze stylami modułu. Użyj narzędzi deweloperskich przeglądarki (F12), aby zbadać elementy obrazu i zidentyfikować wszelkie kolidujące style.
2. **Regeneracja obrazów:** Czasami miniatury obrazów mogą nie generować się poprawnie. W PrestaShop przejdź do **Wygląd > Ustawienia obrazów** i spróbuj ponownie wygenerować miniatury dla „produktów” lub „recenzji”, jeśli taka opcja istnieje, lub dla wszystkich obrazów.
3. **Oryginalna jakość obrazu:** Doradź klientom, aby przesyłali obrazy o rozsądnych rozmiarach i wyraźne. Obrazy o bardzo niskiej rozdzielczości będą naturalnie wyglądać słabo, gdy zostaną wyświetlone w większym rozmiarze.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Dodawanie zdjęć do komentarzy (recenzji) produktów” (`reviewspics`) jest zaprojektowany jako rozszerzenie podstawowego modułu „Komentarze produktów” (prawdopodobnie `productcomments` lub podobnego modułu MyPresta.eu). Głównie wstrzykuje interfejs przesyłania obrazów do istniejącego formularza recenzji i modyfikuje wyświetlanie recenzji, aby zawierały obrazy. Wykorzystuje system hooków PrestaShop do integracji i używa standardowych zasobów front-office i back-office. Moduł tworzy niestandardową tabelę bazy danych, aby połączyć obrazy z konkretnymi komentarzami produktów.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów Front-Office ani Back-Office. Jego funkcjonalność jest zintegrowana za pomocą hooków i bezpośrednich modyfikacji szablonów w kontekście nadrzędnego modułu „Komentarze produktów”.

### 4.3 Podstawowe klasy i modele (`classes/`)

Ten moduł nie definiuje niestandardowych klas w katalogu `classes/`. Jego główna logika znajduje się w głównym pliku modułu `index.php` i pliku `install.sql` dla schematu bazy danych.

### 4.4 Zasoby JavaScript (`views/js/`)

- **`reviewspics/views/js/reviewspics-bo.js`**

  - **Zakres:** Back-office.
  - **Cel:** Ten skrypt prawdopodobnie obsługuje wszelkie funkcje oparte na JavaScript w konfiguracji back-office modułu lub do zarządzania przesłanymi obrazami związanymi z recenzjami w panelu administracyjnym. Może to obejmować wywołania AJAX do usuwania obrazów, aktualizacji statusu lub dynamicznych elementów formularza.
  - **Szczegóły:** Zazwyczaj wiąże się z elementami w szablonie `backOffice.tpl` lub interfejsie zarządzania komentarzami produktów w panelu administracyjnym.
- **`reviewspics/views/js/reviewspics.js`**

  - **Zakres:** Front-office.
  - **Cel:** Jest to podstawowy JavaScript front-office dla funkcji przesyłania obrazów. Obsługuje:
    - Wyświetlanie pola do przesyłania obrazów (np. pole wyboru pliku, obszar przeciągnij i upuść).
    - Podgląd wybranych obrazów przed przesłaniem.
    - Przesyłanie obrazów oparte na AJAX podczas przesyłania recenzji.
    - Walidację typów/rozmiarów obrazów (po stronie klienta).
    - Potencjalnie, usuwanie wybranych obrazów przed przesłaniem.
  - **Szczegóły:** Wiąże się z elementami formularza przesyłania recenzji, prawdopodobnie w szablonie `displayMyPrestaCommentsField.tpl`, i współdziała z logiką po stronie serwera w celu przetwarzania plików obrazów.

### 4.5 Arkusze stylów CSS (`views/css/`)

- **`reviewspics/views/css/reviewspics.css`**
  - **Zakres:** Front-office (głównie) i potencjalnie Back-office.
  - **Cel:** Ten arkusz stylów zapewnia wizualne style dla formularza przesyłania obrazów i wyświetlania przesłanych obrazów w recenzjach produktów.
  - **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:**
    - Obszar przesyłania obrazów (np. obramowanie, tło, ikona).
    - Podglądy obrazów (rozmiar, proporcje, obramowania).
    - Układ obrazów w recenzji.
    - Potencjalnie, stylizacja zarządzania obrazami w Back Office.
  - **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Szukaj klas takich jak `.reviewspics-upload-area`, `.reviewspics-image-preview`, `.reviewspics-review-images` itp. Można je docelowo modyfikować w pliku `custom.css` lub `theme.css` niestandardowego motywu, aby dopasować je do brandingu sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:

  - **`reviewspics/views/templates/hook/backOffice.tpl`**

    - **Hook:** Prawdopodobnie renderowany w `displayAdminProductsExtra` lub niestandardowym hooku w interfejsie administracyjnym modułu „Komentarze produktów”.
    - **Wyniki:** Ten szablon jest przeznaczony dla Back Office. Prawdopodobnie renderuje formularz konfiguracji modułu (jak opisano w sekcji 4.1) lub zapewnia interfejs dla administratorów do zarządzania obrazami związanymi z komentarzami produktów (np. przeglądanie, usuwanie, zatwierdzanie obrazów).
  - **`reviewspics/views/templates/hook/displayMyPrestaComment.tpl`**

    - **Hook:** Ten szablon jest zaprojektowany do wpięcia w wyświetlanie *indywidualnego* komentarza produktu, prawdopodobnie w `displayProductListReviews` lub podobnym hooku dostarczonym przez moduł „Komentarze produktów”.
    - **Wyniki:** Renderuje rzeczywiste obrazy związane z konkretną recenzją produktu. Iterowałby przez obrazy połączone z komentarzem i wyświetlał je, potencjalnie jako miniatury lub małą galerię.
  - **`reviewspics/views/templates/hook/displayMyPrestaCommentsField.tpl`**

    - **Hook:** Ten szablon ma być wstrzyknięty do *formularza przesyłania* recenzji produktu, prawdopodobnie za pośrednictwem hooka takiego jak `displayProductForm` lub niestandardowego hooka w formularzu recenzji modułu „Komentarze produktów”.
    - **Wyniki:** Renderuje strukturę HTML dla pola wprowadzania obrazu, z którym klienci wchodzą w interakcję podczas pisania nowej recenzji. Obejmuje to pole wyboru pliku, wszelkie obszary przeciągnij i upuść oraz potencjalnie miejsca na podglądy obrazów.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Plik `reviewspics/install.sql` wskazuje na utworzenie co najmniej jednej niestandardowej tabeli do przechowywania danych obrazów i łączenia ich z komentarzami produktów.
  - **`ps_reviewspics_image`**: (Prawdopodobna nazwa tabeli, oparta na nazwie modułu i typowych konwencjach PrestaShop).
    - **Cel:** Przechowuje metadane o każdym przesłanym obrazie.
    - **Pola (oczekiwane):**
      - `id_reviewspics_image` (Klucz główny, INT)
      - `id_product_comment` (Klucz obcy, INT, łączący z tabelą recenzji nadrzędnego modułu „Komentarze produktów”)
      - `image_name` (VARCHAR, nazwa pliku obrazu)
      - `date_add` (DATETIME, znacznik czasu przesłania)
      - `active` (TINYINT, dla moderacji/widoczności)
      - `position` (INT, dla kolejności, jeśli wiele obrazów na recenzję)
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` wszystkich stron front-office. | Aby dołączyć pliki CSS (`reviewspics.css`) i JavaScript (`reviewspics.js`) front-office. |
| `displayBackOfficeHeader` | Renderuje się w sekcji `<head>` wszystkich stron back-office. | Aby dołączyć pliki CSS i JavaScript (`reviewspics-bo.js`) back-office do konfiguracji administratora lub zarządzania recenzjami. |
| `displayProductListReviews` (lub podobny z modułu Komentarze produktów) | Renderuje się w liście recenzji produktów na stronach produktów. | Aby wstrzyknąć `displayMyPrestaComment.tpl` do wyświetlania obrazów w istniejących recenzjach. |
| `displayProductForm` (lub podobny z modułu Komentarze produktów) | Renderuje się w formularzu przesyłania recenzji produktów. | Aby wstrzyknąć `displayMyPrestaCommentsField.tpl` dla pola wprowadzania obrazu. |
| `actionProductCommentAdd` (lub podobny z modułu Komentarze produktów) | Wykonywany po dodaniu nowego komentarza produktu. | Aby przetworzyć przesłane obrazy, zapisać je w systemie plików i zapisać ich szczegóły w tabeli `ps_reviewspics_image`, łącząc je z nowym komentarzem. |
| `actionProductCommentDelete` (lub podobny z modułu Komentarze produktów) | Wykonywany po usunięciu komentarza produktu. | Aby usunąć powiązane obrazy z systemu plików i tabeli `ps_reviewspics_image`. |
| `actionProductCommentUpdate` (lub podobny z modułu Komentarze produktów) | Wykonywany po zaktualizowaniu komentarza produktu. | Aby obsłużyć wszelkie zmiany w powiązaniach obrazów lub statusie moderacji. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i profesjonalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu). Nasz zespół jest zaangażowany w zapewnienie płynnego działania i ciągłego ulepszania Twoich modułów PrestaShop.
"""
