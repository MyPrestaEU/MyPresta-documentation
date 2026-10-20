---
title: "Integracja śledzenia sprzedaży Kelkoo - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop 'Integracja śledzenia sprzedaży Kelkoo' od MyPresta.eu."
sidebar:
  label: "Integracja śledzenia sprzedaży Kelkoo"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Kelkoo sales tracking integration na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/kelkoo-sales-tracking-integration.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/kelkoo-sales-tracking-integration/)
>
> ---


# Integracja śledzenia sprzedaży Kelkoo

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 8.x, 1.7.x, 1.6.x, 1.5.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla większości modułów PrestaShop i są zazwyczaj dostępne w każdym nowoczesnym środowisku hostingowym. Brak specjalnych lub nietypowych wymagań dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po instalacji kliknij „Konfiguruj” obok modułu „Integracja śledzenia sprzedaży Kelkoo”. Zostanie wyświetlony prosty ekran konfiguracji.

#### Identyfikator śledzenia Kelkoo
-   **Co robi to ustawienie:** Jest to najważniejsze ustawienie. Tutaj wprowadzasz swój unikalny identyfikator śledzenia dostarczony przez Kelkoo. Ten identyfikator informuje Kelkoo, do którego sprzedawcy (Twojego sklepu) należą dane sprzedażowe.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po poprawnym wprowadzeniu:* Moduł użyje tego identyfikatora do wysyłania danych sprzedażowych do Twojego konkretnego konta Kelkoo, umożliwiając Kelkoo przypisywanie sprzedaży do Twoich kampanii.
    -   *Po pozostawieniu pustego lub niepoprawnego:* Śledzenie sprzedaży nie będzie działać poprawnie, a Kelkoo nie otrzyma danych o zakupach dokonanych za pośrednictwem ich platformy, co uniemożliwi mierzenie wydajności Twojej kampanii.
-   **Zalecana wartość:** Wprowadź dokładny identyfikator śledzenia dostarczony przez Kelkoo. Zazwyczaj jest to ciąg numeryczny lub alfanumeryczny.
-   **Scenariusz / przykład dla sprzedawcy:** Założyłeś konto sprzedawcy w Kelkoo. Otrzymasz unikalny „Identyfikator śledzenia Kelkoo” lub „Identyfikator sprzedawcy”. Musisz dokładnie skopiować i wkleić ten identyfikator w to pole. Bez niego integracja jest niekompletna.

#### Włącz śledzenie
-   **Co robi to ustawienie:** Jest to prosty przełącznik ON/OFF do aktywowania lub dezaktywowania funkcji śledzenia sprzedaży Kelkoo w całym Twoim sklepie.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po włączeniu (TAK):* Moduł będzie aktywnie wstrzykiwał niezbędne skrypty śledzące i wysyłał dane sprzedażowe do Kelkoo na stronie potwierdzenia zamówienia.
    -   *Po wyłączeniu (NIE):* Moduł zaprzestanie wszystkich działań śledzących. Nie zostaną wstrzyknięte żadne skrypty i żadne dane sprzedażowe nie zostaną wysłane do Kelkoo.
-   **Zalecana wartość:** TAK. Powinieneś wyłączyć to tylko wtedy, gdy tymczasowo chcesz zatrzymać śledzenie sprzedaży za pośrednictwem Kelkoo lub rozwiązujesz problem.
-   **Scenariusz / przykład dla sprzedawcy:** Ukończyłeś konfigurację Kelkoo i chcesz natychmiast rozpocząć śledzenie sprzedaży. Ustaw to na TAK. Jeśli zdecydujesz się wstrzymać kampanie Kelkoo lub musisz przeprowadzić konserwację, możesz tymczasowo ustawić to na NIE.

### 2.2 Tabela szybkiego odniesienia konfiguracji
| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Konfiguracja modułu | Identyfikator śledzenia Kelkoo | Twój identyfikator Kelkoo | Unikalny identyfikator Twojego konta sprzedawcy Kelkoo. Niezbędny do atrybucji sprzedaży. |
| Konfiguracja modułu | Włącz śledzenie | TAK | Aktywuje/dezaktywuje funkcję śledzenia sprzedaży Kelkoo. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem moduł, ale Kelkoo nie pokazuje żadnej sprzedaży. Co powinienem zrobić?**
O:
1.  **Dokładnie sprawdź swój identyfikator śledzenia Kelkoo:** Upewnij się, że został wprowadzony dokładnie tak, jak dostarczył Kelkoo, bez dodatkowych spacji lub znaków.
2.  **Upewnij się, że „Włącz śledzenie” jest ustawione na TAK:** Ten przełącznik musi być aktywny, aby moduł działał.
3.  **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami buforowana zawartość może uniemożliwić zastosowanie nowych ustawień modułu.
4.  **Dokonaj testowego zakupu:** Zrealizuj pełne zamówienie w swoim sklepie, aby uruchomić śledzenie.
5.  **Skontaktuj się z pomocą techniczną Kelkoo:** Jeśli wszystkie ustawienia są poprawne i wyczyściłeś pamięć podręczną, skontaktuj się z zespołem wsparcia Kelkoo. Często mogą oni sprawdzić swoją stronę, aby zobaczyć, czy jakieś dane są odbierane lub czy występuje problem z konfiguracją Twojego konta na ich platformie.

**P: Czy ten moduł spowolni moją stronę internetową?**
O: Nie, moduł jest bardzo lekki. Wstrzykuje tylko mały, nieblokujący fragment JavaScript do nagłówka i wysyła dane na stronie potwierdzenia zamówienia. Ten proces jest zoptymalizowany tak, aby nie wpływać na szybkość ładowania Twojego sklepu ani na doświadczenie klienta.

**P: Czy ten moduł działa z konfiguracjami wielu sklepów?**
O: Tak, moduł powinien działać poprawnie w środowisku wielu sklepów. Skonfigurujesz identyfikator śledzenia Kelkoo dla każdego sklepu indywidualnie, jeśli mają oddzielne konta Kelkoo, lub użyjesz tego samego identyfikatora, jeśli śledzisz wszystkie sklepy pod jednym kontem Kelkoo.

**P: Używam niestandardowego motywu. Czy ten moduł nadal będzie działać?**
O: Tak, moduł wykorzystuje standardowe hooki PrestaShop (`displayHeader`, `displayOrderConfirmation`), które są prawie powszechnie obecne we wszystkich dobrze zakodowanych motywach. Nie opiera się na konkretnych elementach motywu, więc powinien być kompatybilny z niestandardowymi motywami. Jeśli napotkasz problemy, upewnij się, że Twój niestandardowy motyw poprawnie implementuje te podstawowe hooki PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury
Moduł „Integracja śledzenia sprzedaży Kelkoo” to prosty moduł PrestaShop zaprojektowany do integracji piksela śledzenia sprzedaży Kelkoo. Wykorzystuje on głównie system hooków PrestaShop do wstrzykiwania globalnego skryptu śledzącego do nagłówka i skryptu śledzenia konwersji na stronie potwierdzenia zamówienia. Moduł ten ma podstawową strukturę modułu PrestaShop, a jego główna logika znajduje się w głównym pliku modułu i plikach szablonów do renderowania hooków. Nie ma niestandardowych kontrolerów, modeli ani złożonych zasobów JavaScript/CSS poza tymi, które są niezbędne dla piksela śledzącego.

### 4.2 Kontrolery (`controllers/`)
- **Kontrolery Front-Office**: Brak. Cała funkcjonalność front-office jest obsługiwana za pomocą hooków w głównym pliku modułu.
- **Kontrolery Back-Office Admin**: Brak. Konfiguracja jest obsługiwana bezpośrednio przez metodę `getContent()` w głównym pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)
- W tym module nie ma niestandardowych klas ani definicji `ObjectModel`. Cała logika znajduje się w głównym pliku modułu `Kelkoo.php` (lub `index.php` w starszych strukturach).

### 4.4 Zasoby JavaScript (`views/js/`)
- W module nie ma dedykowanych plików JavaScript. Niezbędny skrypt śledzący Kelkoo jest dynamicznie generowany i wstrzykiwany bezpośrednio do HTML za pomocą szablonów Smarty lub hooka `displayHeader`.

### 4.5 Arkusze stylów CSS (`views/css/`)
- W module nie ma dedykowanych plików CSS. Moduł nie ma wizualnych komponentów front-office, a jego konfiguracja back-office wykorzystuje standardowe style formularzy PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)
- **Szablony hooków (`views/templates/hook/`)**:
    *   `kelkoo/views/templates/hook/displayOrderConfirmation.tpl`:
        *   **Hook**: `displayOrderConfirmation`
        *   **Cel**: Ten szablon jest renderowany na stronie potwierdzenia zamówienia po udanym zakupie. Jest odpowiedzialny za generowanie piksela śledzenia sprzedaży Kelkoo (KST) z dynamicznymi szczegółami zamówienia (ID zamówienia, suma, szczegóły produktu). Pobiera informacje o zamówieniu przekazane do hooka i formatuje je zgodnie ze specyfikacjami Kelkoo.
    *   `kelkoo/views/templates/hook/header.tpl`:
        *   **Hook**: `displayHeader`
        *   **Cel**: Ten szablon jest renderowany w sekcji `<head>` każdej strony. Ma na celu włączenie wszelkich globalnych skryptów śledzących Kelkoo lub inicjalizatorów, które muszą być obecne na całej stronie, chociaż dla prostego śledzenia sprzedaży główna logika często znajduje się w `displayOrderConfirmation`. Może zawierać podstawowy piksel bazowy Kelkoo lub placeholder dla przyszłych funkcji Kelkoo.

- **Szablony administracyjne (`views/templates/admin/`)**: Brak. Formularz konfiguracji jest budowany bezpośrednio w `getContent()` za pomocą klas pomocniczych formularzy PrestaShop.
- **Szablony front-office (`views/templates/front/`)**: Brak.

### 4.7 Schemat bazy danych i mapa hooków
- **Tabele bazy danych**:
    *   Moduł nie tworzy żadnych niestandardowych tabel SQL.
    *   Ustawienia konfiguracji (`Identyfikator śledzenia Kelkoo`, `Włącz śledzenie`) są przechowywane w tabeli `ps_configuration` (lub z prefiksem `_configuration`) przy użyciu kluczy takich jak `KELKOO_TRACKING_ID` i `KELKOO_ENABLED`.

- **Tabela zarejestrowanych hooków**:
  | Nazwa hooka | Czas wykonania | Cel techniczny |
  |---|---|---|
  | `displayHeader` | Renderuje się w sekcji `<head>` każdej strony. | Wstrzykuje globalne skrypty śledzące Kelkoo lub piksel bazowy. |
  | `displayOrderConfirmation` | Renderuje się na stronie potwierdzenia zamówienia po udanym zakupie. | Wysyła szczegółowe dane sprzedażowe (ID zamówienia, kwota, produkty) do Kelkoo w celu śledzenia konwersji. |

## 5. Oficjalne wsparcie i aktualizacje
W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dostępu do najnowszych wersji modułu „Integracja śledzenia sprzedaży Kelkoo” prosimy odwiedzić swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
"""
