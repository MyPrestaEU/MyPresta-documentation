---
title: "Moderacja komentarzy / recenzji na pulpicie - Podręcznik handlowca i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop 'Moderacja komentarzy / recenzji na pulpicie' od MyPresta.eu."
sidebar:
  label: "Moderacja komentarzy / recenzji na pulpicie"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Dashboard comments / reviews moderation na MyPresta.eu](https://mypresta.eu/modules/administration-tools/dashboard-comments-reviews-moderation.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/dashboard-comments-reviews-moderation/)
>
> ---


# Moderacja komentarzy / recenzji na pulpicie

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są wymagane dla samego PrestaShop i są zazwyczaj dostępne we wszystkich nowoczesnych środowiskach hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównego ekranu konfiguracji modułu. Moduł ten został zaprojektowany tak, aby był bardzo prosty, z minimalną liczbą ustawień, ponieważ jego główną funkcją jest wyświetlanie informacji na pulpicie.

**Nazwa ekranu:** Konfiguracja moderacji komentarzy / recenzji na pulpicie

**Lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > Moderacja komentarzy / recenzji na pulpicie > Konfiguruj

| Ustawienie / Opcja | Co robi to ustawienie | Efekt zmiany tego ustawienia | Zalecana wartość | Scenariusz handlowca / przykład |
|---|---|---|---|---|
| **Aktualizacje MyPresta.eu** | Ta sekcja zazwyczaj dotyczy sprawdzania aktualizacji modułów MyPresta.eu. Może zawierać opcje włączania/wyłączania sprawdzania aktualizacji lub wyświetlania powiadomień o aktualizacjach. | *Po włączeniu:* Moduł będzie okresowo sprawdzał MyPresta.eu pod kątem nowszych wersji i powiadamiał Cię w panelu administracyjnym, jeśli dostępna jest aktualizacja. Pomaga to utrzymać moduł aktualny z najnowszymi funkcjami i poprawkami błędów. *Po wyłączeniu:* Moduł nie będzie automatycznie sprawdzał aktualizacji. Musiałbyś ręcznie sprawdzać aktualizacje na MyPresta.eu. | **Włączone (Tak)** | Utrzymywanie tego włączonego zapewnia, że zawsze jesteś świadomy nowych wersji, co pozwala korzystać z ulepszeń i aktualizacji bezpieczeństwa bez ręcznego sprawdzania. |
| **Update_ (Wewnętrzne)** | Jest to ustawienie wewnętrzne, prawdopodobnie związane z samym mechanizmem aktualizacji. Zazwyczaj nie jest przeznaczone do bezpośredniej interakcji handlowca. | Zmiana tego ustawienia nie jest zalecana, ponieważ może zakłócić zdolność modułu do sprawdzania i stosowania aktualizacji. | **Pozostaw jako domyślne** | Jest to ustawienie techniczne; właściciele sklepów nie powinni go modyfikować. |
| **Updatev_ (Wewnętrzne)** | Podobnie jak `update_`, jest to wewnętrzne ustawienie związane z wersją dla mechanizmu aktualizacji. | Zmiana tego ustawienia nie jest zalecana, ponieważ może zakłócić zdolność modułu do sprawdzania i stosowania aktualizacji. | **Pozostaw jako domyślne** | Jest to ustawienie techniczne; właściciele sklepów nie powinni go modyfikować. |

**Ważna uwaga:** Podstawowa funkcjonalność wyświetlania komentarzy i recenzji na pulpicie nie wymaga rozbudowanej konfiguracji. Po zainstalowaniu moduł automatycznie integruje się z pulpitem, aby wyświetlać oczekujące recenzje i zgłoszone komentarze, zakładając, że masz zainstalowany i aktywny standardowy moduł PrestaShop „Komentarze produktów” (lub kompatywną alternatywę).

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów
Ten moduł **nie** wprowadza żadnych nowych dedykowanych ekranów administracyjnych ani niestandardowych widoków kontrolerów. Jego funkcjonalność jest zintegrowana bezpośrednio z istniejącym pulpitem PrestaShop.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Strona konfiguracji modułu | Aktualizacje MyPresta.eu | Włączone (Tak) | Włącza automatyczne sprawdzanie aktualizacji modułu z MyPresta.eu. |
| Strona konfiguracji modułu | Update_ | Pozostaw jako domyślne | Wewnętrzne ustawienie mechanizmu aktualizacji. |
| Strona konfiguracji modułu | Updatev_ | Pozostaw jako domyślne | Wewnętrzne ustawienie wersji dla aktualizacji. |

## 3. Rozwiązywanie problemów handlowca i często zadawane pytania (FAQ)

**P1: Zainstalowałem moduł, ale nie widzę żadnych komentarzy/recenzji na moim pulpicie.**
**O1:**
*   **Sprawdź moduł „Komentarze produktów”:** Ten moduł opiera się na standardowym module PrestaShop „Komentarze produktów” (lub kompatybilnym module recenzji innej firmy), aby działać. Upewnij się, że moduł „Komentarze produktów” jest zainstalowany, włączony i poprawnie skonfigurowany w Twoim sklepie.
*   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Czasami pamięć podręczna PrestaShop wymaga odświeżenia, aby nowe elementy pulpitu się pojawiły.
*   **Sprawdź oczekujące recenzje:** Czy faktycznie masz jakieś recenzje oczekujące na moderację lub jakieś komentarze zgłoszone jako obraźliwe? Moduł wyświetli tylko treści, które wymagają Twojej uwagi. Jeśli nie ma takich elementów, blok pulpitu może być pusty lub nie pojawić się, jeśli nie ma nic do wyświetlenia.

**P2: Blok pulpitu wygląda dziwnie lub nie jest poprawnie ostylowany.**
**O2:**
*   **Wyczyść pamięć podręczną przeglądarki:** Czasami Twoja przeglądarka internetowa buforuje stare pliki CSS. Spróbuj wyczyścić pamięć podręczną przeglądarki lub otworzyć panel administracyjny w oknie incognito/prywatnym.
*   **Sprawdź konflikty motywów:** Chociaż rzadkie w przypadku modułów pulpitu, wysoce dostosowany motyw administracyjny może potencjalnie powodować konflikty. Jeśli podejrzewasz to, spróbuj tymczasowo przełączyć się na domyślny motyw administracyjny PrestaShop (jeśli to możliwe), aby sprawdzić, czy problem nadal występuje. Jeśli się rozwiąże, skonsultuj się z deweloperem motywu.
*   **Wyczyść pamięć podręczną PrestaShop:** Jak wspomniano powyżej, wyczyszczenie pamięci podręcznej Smarty w **Zaawansowane > Wydajność** może rozwiązać problemy z wyświetlaniem.

**P3: Jak przetłumaczyć tekst modułu na inny język?**
**O3:**
*   Przejdź do **Lokalizacja > Tłumaczenia** w panelu administracyjnym PrestaShop.
*   Wybierz „Tłumaczenia zainstalowanych modułów” dla „Typu tłumaczenia”.
*   Wybierz swój motyw (np. „Classic”) i język, na który chcesz przetłumaczyć.
*   Znajdź „Moderacja komentarzy / recenzji na pulpicie” na liście, kliknij „Modyfikuj”, a następnie możesz przetłumaczyć wszystkie dostępne ciągi tekstowe.

**P4: Kliknąłem „Konfiguruj”, ale widzę tylko ustawienia aktualizacji, a nie narzędzia moderacji.**
**O4:** Przycisk „Konfiguruj” dla tego modułu prowadzi do jego minimalnej strony ustawień, głównie do zarządzania aktualizacjami. Rzeczywiste narzędzia moderacji (lista komentarzy/recenzji) są wyświetlane bezpośrednio na głównym pulpicie PrestaShop, zazwyczaj w jednym z obszarów „Strefy pulpitu”. Przejdź do głównego „Pulpitu” (pierwsza strona, którą widzisz po zalogowaniu), aby znaleźć dane wyjściowe modułu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury
Moduł „Moderacja komentarzy / recenzji na pulpicie” (`dashcomments`) to lekki moduł PrestaShop zaprojektowany do rozszerzania pulpitu panelu administracyjnego. Wykorzystuje system hooków PrestaShop do wstrzykiwania niestandardowego bloku do pulpitu, wyświetlając oczekujące recenzje produktów i zgłoszone komentarze. Nie wprowadza nowych tabel baz danych ani złożonych struktur `ObjectModel`, zamiast tego opiera się na istniejących danych z modułu `ps_product_comment`. Jego główną funkcją jest prezentacja i interakcja z istniejącymi danymi za pośrednictwem AJAX.

### 4.2 Kontrolery (`controllers/`)
Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów front-office ani back-office. Wszystkie interakcje są obsługiwane bezpośrednio w głównej klasie modułu (`dashcomments.php`) lub za pośrednictwem wywołań AJAX przetwarzanych przez metody `ajaxProcess` modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)
Ten moduł **nie** definiuje żadnych niestandardowych klas ani modeli w katalogu `classes/`. Bezpośrednio współdziała z podstawowymi funkcjonalnościami PrestaShop i, pośrednio, z klasą `ProductComment` z modułu `ps_product_comments` (jeśli jest zainstalowany).

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`dashcomments/js/dashcomments.js`**
    *   **Zakres:** Panel administracyjny (Pulpit).
    *   **Cel:** Obsługuje interakcje AJAX do moderowania komentarzy i recenzji bezpośrednio z widżetu pulpitu.
    *   **Kluczowa funkcjonalność:**
        *   Wiąże słuchaczy zdarzeń kliknięcia z przyciskami „Zatwierdź”, „Odrzuć” i „Usuń” w widżecie pulpitu.
        *   Wysyła żądania AJAX do metod `ajaxProcess` modułu (np. `ajaxProcessApproveComment`, `ajaxProcessDisapproveComment`, `ajaxProcessDeleteComment`) w celu wykonania działań moderacyjnych.
        *   Aktualizuje DOM (usuwa wiersz moderowanego komentarza, aktualizuje liczniki) po pomyślnej odpowiedzi AJAX.
        *   Może zawierać logikę obsługi działań „zgłoś jako obraźliwe”, jeśli zaimplementowano je dla samych komentarzy.
        *   Używa `$.ajax` do komunikacji asynchronicznej.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`dashcomments/css/dashcomments.css`**
    *   **Zakres:** Panel administracyjny (Pulpit).
    *   **Cel:** Zapewnia stylizację widżetu pulpitu, który wyświetla oczekujące komentarze i recenzje.
    *   **Kluczowa stylizacja:**
        *   Style dla listy komentarzy, poszczególnych wierszy komentarzy, przycisków akcji (zatwierdź, odrzuć, usuń) i potencjalnie liczników dla oczekujących elementów.
        *   Zapewnia wizualną integrację widżetu z motywem panelu administracyjnego PrestaShop 1.7+/8+.
        *   **Kluczowe selektory klas CSS:** Deweloperzy mogą sprawdzić wygenerowany kod HTML pod kątem konkretnych klas (np. `.dashcomments-widget`, `.dashcomments-item`, `.dashcomments-actions`), aby nadpisać lub rozszerzyć stylizację w swoich niestandardowych motywach administracyjnych.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`dashcomments/dashboardZoneOne.tpl`**
    *   **Zakres:** Panel administracyjny (Pulpit).
    *   **Hook:** `displaydashboardZoneTwo` (lub `dashboardZoneTwo` w starszych wersjach).
    *   **Cel:** Ten szablon jest odpowiedzialny za renderowanie struktury HTML widżetu moderacji komentarzy/recenzji na pulpicie PrestaShop.
    *   **Treść:**
        *   Wyświetla listę komentarzy do produktów oczekujących na zatwierdzenie.
        *   Wyświetla listę komentarzy do produktów, które zostały zgłoszone jako obraźliwe.
        *   Dla każdego komentarza zazwyczaj wyświetla nazwę produktu, imię klienta, treść komentarza, ocenę i przyciski akcji (Zatwierdź, Odrzuć, Usuń).
        *   Zawiera logikę do iteracji po zmiennych `$pending_comments` i `$reported_comments` przekazanych z modułu.
        *   Zawiera niezbędne elementy HTML i atrybuty danych dla skryptu `dashcomments.js` do dołączania jego słuchaczy zdarzeń i wykonywania działań AJAX.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Ten moduł nie tworzy żadnych niestandardowych tabel baz danych. Opiera się na tabeli `ps_product_comment` (i powiązanych tabelach, takich jak `ps_product_comment_grade`, `ps_product_comment_criterion`), które są tworzone przez oficjalny moduł `ps_product_comments`.
-   **Rekordy konfiguracji**:
    *   `PS_DASHCOMMENTS_UPDATES`: Przechowuje status sprawdzania aktualizacji.
    *   `PS_DASHCOMMENTS_UPDATE_`: Wewnętrzna flaga aktualizacji.
    *   `PS_DASHCOMMENTS_UPDATEV_`: Wewnętrzna flaga wersji dla aktualizacji.

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny konfiguruje swoje zasoby multimedialne (CSS/JS). | Służy do rejestrowania plików `dashcomments.js` i `dashcomments.css` modułu dla pulpitu panelu administracyjnego. |
| `displaydashboardZoneTwo` | Renderuje zawartość w drugiej strefie pulpitu panelu administracyjnego PrestaShop. | Jest to główny hook używany do wyświetlania widżetu moderacji komentarzy/recenzji. |
| `dashboardZoneTwo` | (Starszy hook, podobny do `displaydashboardZoneTwo`) | Zapewnia kompatybilność ze starszymi wersjami PrestaShop lub alternatywnymi układami pulpitu do wyświetlania widżetu. |

## 5. Oficjalne wsparcie i aktualizacje
W celu uzyskania oficjalnego wsparcia, aktualizacji modułu i wszelkiej dalszej pomocy, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Możesz pobrać najnowsze wersje modułu z historii zamówień i uzyskać dostęp do naszych dedykowanych kanałów wsparcia w przypadku wszelkich pytań technicznych lub problemów.
