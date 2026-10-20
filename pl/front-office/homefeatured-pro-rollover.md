---
title: "HomeFeatured Pro Rollover - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop HomeFeatured Pro Rollover od MyPresta.eu."
sidebar:
  label: "HomeFeatured Pro Rollover"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł HomeFeatured Pro Rollover na MyPresta.eu](https://mypresta.eu/modules/front-office-features/homefeatured-pro-rollover.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/homefeatured-pro-rollover/)
>
> ---


# HomeFeatured Pro Rollover

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i zazwyczaj preinstalowane w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po instalacji kliknij „Konfiguruj” obok „HomeFeatured Pro Rollover” w Menedżerze modułów, aby uzyskać dostęp do jego ustawień.

#### 2.1.1 Liczba produktów do wyświetlenia
-   **Co robi to ustawienie:** Kontroluje, ile wyróżnionych produktów zostanie wyświetlonych w sekcji „Wyróżnione produkty” na Twojej stronie głównej.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po ustawieniu na konkretną liczbę (np. 8):* Twoja strona główna wyświetli dokładnie tyle produktów z kategorii „Strona główna” (lub dowolnej kategorii, którą wyznaczyłeś dla wyróżnionych produktów).
    -   *Po ustawieniu na inną liczbę:* Liczba wyświetlanych produktów zmieni się odpowiednio. Jeśli ustawisz ją zbyt wysoko, Twoja strona główna może stać się bardzo długa; jeśli zbyt nisko, możesz nie zaprezentować wystarczającej liczby produktów.
-   **Zalecana wartość:** Liczba, która dobrze pasuje do układu Twojej strony głównej, zazwyczaj od 8 do 12 dla standardowej siatki.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz wyróżnić 8 najlepiej sprzedających się produktów na stronie głównej, ustaw to na „8”. Jeśli masz szerszy układ i chcesz pokazać większą różnorodność, możesz zwiększyć to do „12”.

#### 2.1.2 Wyświetl atrybuty na stronie produktu
-   **Co robi to ustawienie:** Jest to standardowe ustawienie PrestaShop, które kontroluje, czy atrybuty produktu (takie jak rozmiar, kolor) są wyświetlane na samej stronie produktu. Chociaż ten moduł wpływa głównie na stronę główną, to ustawienie jest często uwzględniane w modułach, które wchodzą w interakcje z wyświetlaniem produktów.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po włączeniu (Tak):* Atrybuty produktu będą widoczne i możliwe do wyboru na poszczególnych stronach produktów.
    -   *Po wyłączeniu (Nie):* Atrybuty produktu nie będą wyświetlane na stronach produktów, co potencjalnie uprości stronę, ale usunie ważne opcje wyboru dla klientów.
-   **Zalecana wartość:** **Tak**. Większość sklepów musi wyświetlać atrybuty dla produktów z wariantami.
-   **Scenariusz / przykład dla sprzedawcy:** W sklepie odzieżowym klienci muszą wybrać rozmiar i kolor. Włączenie tego zapewnia, że te opcje pojawią się na stronie produktu. Wyłączenie tego uniemożliwiłoby klientom wybór wariantów.

#### 2.1.3 Domyślny język
-   **Co robi to ustawienie:** To ustawienie określa domyślny język dla Twojego sklepu. Jest to podstawowe ustawienie PrestaShop często używane przez moduły w celu zapewnienia prawidłowej obsługi języków.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po ustawieniu na Twój główny język (np. Polski):* Moduł będzie używał tego języka dla wszelkich danych zależnych od języka lub jako rezerwowy, jeśli brakuje tłumaczeń.
-   **Zalecana wartość:** **Główny język Twojego sklepu.** Powinno to odpowiadać domyślnemu językowi ustawionemu w ustawieniach lokalizacji PrestaShop.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli główna grupa odbiorców Twojego sklepu znajduje się w Polsce, ustawisz to na „Polski”, aby upewnić się, że cały domyślny tekst i informacje o produkcie są poprawnie wyświetlane po polsku.

#### 2.1.4 Liczba produktów do wyświetlenia (Duplikat 4.1.1)
-   **Co robi to ustawienie:** Jest to duplikat ustawienia „Liczba produktów do wyświetlenia” (`HOME_FEATURED_PRO_NBR`). Kontroluje ten sam aspekt: ile wyróżnionych produktów pojawia się na Twojej stronie głównej.
-   **Wpływ zmiany tego ustawienia:** Zmiana tego bezpośrednio zmieni liczbę produktów wyświetlanych w sekcji wyróżnionych.
-   **Zalecana wartość:** Patrz sekcja 4.1.1.
-   **Scenariusz / przykład dla sprzedawcy:** Patrz sekcja 4.1.1.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Konfiguracja modułu | Liczba produktów do wyświetlenia (`HOME_FEATURED_PRO_NBR`) | 8-12 (zależy od układu) | Ustawia liczbę wyróżnionych produktów na stronie głównej. |
| Konfiguracja modułu | Wyświetl atrybuty na stronie produktu (`PS_ATTRIBUTE_CATEGORY_DISPLAY`) | Tak | Kontroluje widoczność atrybutów produktu na stronach produktów. |
| Konfiguracja modułu | Domyślny język (`PS_LANG_DEFAULT`) | Główny język Twojego sklepu | Określa domyślny język dla sklepu. |
| Konfiguracja modułu | Liczba produktów do wyświetlenia (`HOME_FEATURED_NBR`) | Takie samo jak `HOME_FEATURED_PRO_NBR` | Zduplikowane ustawienie dla liczby wyróżnionych produktów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Efekt zmiany obrazu nie działa na mojej stronie głównej.**
O:
1.  **Sprawdź status modułu:** Upewnij się, że moduł „HomeFeatured Pro Rollover” jest zainstalowany i włączony w **Moduły > Menedżer modułów**.
2.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stara pamięć podręczna uniemożliwia wyświetlanie nowych zmian modułu.
3.  **Obrazy produktów:** Sprawdź, czy wyróżnione produkty mają *co najmniej dwa* obrazy przesłane w ich ustawieniach produktu (**Katalog > Produkty > [Edytuj produkt] > zakładka Obrazy**). Moduł potrzebuje drugiego obrazu do wyświetlenia po najechaniu myszką.
4.  **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany z myślą o szerokiej kompatybilności, bardzo mocno dostosowane motywy mogą wymagać drobnych korekt CSS. Jeśli problem nadal występuje, skontaktuj się z pomocą techniczną MyPresta.eu.

**P: Moja strona główna wygląda na uszkodzoną po instalacji.**
O:
1.  **Natychmiastowe działanie:** Jeśli Twój sklep stanie się bezużyteczny, natychmiast wyłącz moduł z **Moduły > Menedżer modułów**.
2.  **Sprawdź wersję PrestaShop:** Upewnij się, że pobrałeś poprawną wersję modułu dla swojej instalacji PrestaShop (np. wersję PS 8.x dla PrestaShop 8.x).
3.  **Konflikty motywów:** Niektóre motywy mogą mieć własną logikę „wyróżnionych produktów”, która powoduje konflikty. Spróbuj tymczasowo przełączyć się na domyślny motyw PrestaShop (Classic), aby sprawdzić, czy problem zostanie rozwiązany. Jeśli tak, problem jest związany z motywem.
4.  **Skontaktuj się z pomocą techniczną:** Podaj wsparciu MyPresta.eu szczegóły dotyczące Twojej wersji PrestaShop, motywu i wszelkich komunikatów o błędach, które widzisz.

**P: Jak zmienić, które produkty są „wyróżnione”?**
O: Moduł wykorzystuje standardowy mechanizm „Wyróżnionych produktów” PrestaShop. Aby zmienić, które produkty się pojawiają:
1.  Przejdź do **Katalog > Kategorie**.
2.  Znajdź kategorię o nazwie „Strona główna” (lub kategorię, którą wyznaczyłeś jako kategorię strony głównej).
3.  Edytuj tę kategorię i przejdź do zakładki „Produkty”.
4.  Możesz dodawać lub usuwać produkty z tej kategorii, aby kontrolować, co pojawia się w sekcji wyróżnionych.

**P: Obrazy nie są idealnie wyrównane lub mają niewłaściwy rozmiar podczas zmiany.**
O: Zazwyczaj wskazuje to na konflikt CSS z Twoim motywem.
1.  **Wymiary obrazów:** Upewnij się, że wszystkie obrazy produktów (zwłaszcza pierwszy i drugi) są przesłane z zachowaniem spójnych proporcji i podobnych wymiarów. PrestaShop automatycznie je zmienia, ale duże różnice mogą powodować przesunięcia układu.
2.  **Dostosowanie motywu:** CSS Twojego motywu może nadpisywać stylizację modułu. Webmaster może zbadać element za pomocą narzędzi deweloperskich przeglądarki, aby zidentyfikować sprzeczne reguły CSS i zastosować poprawkę w niestandardowym pliku CSS Twojego motywu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury
Moduł HomeFeatured Pro Rollover (`homefeaturedpro`) to prosty moduł PrestaShop zaprojektowany do nadpisywania i rozszerzania funkcjonalności domyślnego modułu `homefeatured`. Skupia się głównie na wyświetlaniu w front-office, w szczególności na wstrzykiwaniu JavaScript i CSS, aby umożliwić efekt zmiany obrazu po najechaniu myszką na wyróżnionych produktach na stronie głównej. Wykorzystuje system hooków PrestaShop do integracji swojej logiki i szablonów. Moduł nie wprowadza nowych tabel baz danych ani złożonych ObjectModels, zamiast tego opiera się na istniejących danych produktów PrestaShop.

### 4.2 Kontrolery (`controllers/`)
Ten moduł nie wprowadza żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)
Ten moduł nie wprowadza żadnych niestandardowych klas ani ObjectModels. Działa poprzez rozszerzanie istniejącej funkcjonalności PrestaShop i renderowanie własnych szablonów.

### 4.4 Zasoby JavaScript (`views/js/`)
Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Efekt zmiany obrazu jest osiągany wyłącznie za pomocą CSS.

### 4.5 Arkusze stylów CSS (`views/css/`)
-   **`homefeaturedpro/homefeatured.css`**
    *   **Zakres:** Stylizacja front-office dla klienta.
    *   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Ten arkusz stylów zawiera podstawowe reguły CSS odpowiedzialne za efekt zmiany obrazu po najechaniu myszką. Celuje w kontenery obrazów produktów w sekcji wyróżnionych produktów, prawdopodobnie używając selektorów takich jak `.product-container .product-image`, `.product-image-container` lub podobnych, aby domyślnie ukryć drugi obraz i wyświetlić go po najechaniu myszką.
    *   **Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim motywie:**
        *   `.product-image-container .img-hover`: Prawdopodobnie kontroluje widoczność i pozycjonowanie drugiego obrazu.
        *   `.product-image-container .img-primary`: Kontroluje główny obraz.
        *   Style związane z właściwościami `transition` dla płynnych zmian obrazu.
        *   `overflow: hidden` na kontenerze obrazu do zarządzania zamianą obrazów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`homefeaturedpro/homefeatured.tpl`**
    *   **Zakres:** Front-office.
    *   **Hook:** Głównie renderowany w `displayHome` lub `Home` (w zależności od wersji PrestaShop i konfiguracji motywu).
    *   **Cel:** Jest to główny szablon odpowiedzialny za renderowanie siatki wyróżnionych produktów na stronie głównej. Iteruje przez zmienną `$products` (przekazaną z metody `hookDisplayHome` modułu) i dla każdego produktu generuje strukturę HTML zawierającą główny i dodatkowy obraz, nazwę produktu, cenę i inne szczegóły. Jest zaprojektowany do współpracy z PrestaShop 1.7.x i nowszymi. Logika w tym szablonie jest kluczowa dla wyświetlania obu obrazów i stosowania niezbędnych klas CSS dla efektu zmiany obrazu.

-   **`homefeaturedpro/homefeatured14.tpl`**
    *   **Zakres:** Front-office.
    *   **Hook:** Prawdopodobnie przeznaczony dla starszych wersji PrestaShop (np. 1.4.x, 1.5.x, 1.6.x), jeśli moduł je obsługuje, lub jako alternatywa dla specyficznych struktur motywów.
    *   **Cel:** Ten szablon służy temu samemu celowi co `homefeatured.tpl`, ale jest skonstruowany tak, aby był kompatybilny ze starszymi składniami szablonów PrestaShop i strukturami HTML. Również iterowałby przez produkty i renderował niezbędne elementy obrazu dla efektu zmiany obrazu. Dla nowoczesnych wersji PrestaShop (1.7+), `homefeatured.tpl` jest głównym używanym szablonem.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele baz danych**:
    *   Moduł nie tworzy żadnych niestandardowych tabel baz danych.
    *   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` za pomocą następujących kluczy:
        *   `HOME_FEATURED_PRO_NBR`: Przechowuje liczbę wyróżnionych produktów do wyświetlenia.
        *   `PS_ATTRIBUTE_CATEGORY_DISPLAY`: (Standardowa konfiguracja PrestaShop, potencjalnie odwoływana lub ustawiana przez moduł).
        *   `PS_LANG_DEFAULT`: (Standardowa konfiguracja PrestaShop, potencjalnie odwoływana lub ustawiana przez moduł).
        *   `HOME_FEATURED_NBR`: (Duplikat `HOME_FEATURED_PRO_NBR`, prawdopodobnie dla kompatybilności wstecznej lub wewnętrznej spójności).

-   **Zarejestrowane hooki**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Służy do dołączenia arkusza stylów CSS modułu (`homefeatured.css`), aby upewnić się, że style zmiany obrazu są załadowane przed treścią strony. |
| `header` | Alias dla `displayHeader`. | To samo co `displayHeader`. |
| `Home` | Na stronie głównej, zazwyczaj w głównym obszarze treści. | Renderuje szablon wyróżnionych produktów modułu (`homefeatured.tpl` lub `homefeatured14.tpl`) i przekazuje do niego dane produktu. |
| `displayHome` | Alias dla `Home` w nowoczesnych wersjach PrestaShop. | To samo co `Home`. |

## 5. Oficjalne wsparcie i aktualizacje
W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dalszej pomocy z modułem HomeFeatured Pro Rollover, odwiedź swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
