---
title: "Pole ceny specyficznej z podatkiem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla deweloperów modułu PrestaShop „Specific price tax included field” od MyPresta.eu."
sidebar:
  label: "Pole ceny specyficznej z podatkiem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Specific price tax included field na MyPresta.eu](https://mypresta.eu/modules/administration-tools/specific-price-tax-included-field.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/specific-price-tax-included-field/)
>
> ---


# Pole ceny specyficznej z podatkiem

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Specific price tax included field” w Menedżerze modułów. Spowoduje to przejście do głównego ekranu konfiguracji modułu.

#### Ustawienia ogólne

- **Co robi to ustawienie:** Ta sekcja zazwyczaj zawiera ogólne ustawienia związane z aktualizacjami modułu i sprawdzaniem wersji.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone:* Moduł będzie okresowo sprawdzał dostępność nowych wersji z MyPresta.eu i powiadamiał Cię w Panelu administracyjnym. Zapewnia to, że zawsze używasz najnowszej, najbezpieczniejszej i najbardziej funkcjonalnej wersji.
  - *Gdy wyłączone:* Moduł nie będzie wykonywał automatycznych sprawdzeń aktualizacji. Musiałbyś ręcznie sprawdzać aktualizacje, odwiedzając swoje konto MyPresta.eu.
- **Zalecana wartość:** **TAK** (lub włączone). Utrzymywanie tej opcji włączonej zapewnia, że będziesz informowany o ważnych aktualizacjach i poprawkach błędów.
- **Scenariusz / przykład sprzedawcy:** Chcesz być powiadamiany, jeśli zostanie wydana nowa wersja modułu, która zawiera poprawki kompatybilności dla nowej wersji PrestaShop lub ulepszenia wydajności. Włączenie tej opcji spowoduje wyświetlenie powiadomienia w Twoim Panelu administracyjnym.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Sprawdzanie aktualizacji (mypresta\_updates, update\_, updatev\_) | Włączone | Okresowo sprawdza nowe wersje modułu i powiadamia Cię w Panelu administracyjnym. |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P: Zainstalowałem moduł, ale nie widzę nowego pola „Cena z podatkiem”.**
O: Najpierw upewnij się, że moduł jest włączony w **Moduły > Menedżer modułów**. Następnie przejdź do strony produktu, do zakładki „Ceny” i kliknij „Dodaj nową cenę specyficzną” lub „Edytuj” istniejącą. Nowe pole powinno pojawić się w formularzu tworzenia/edycji ceny specyficznej. Jeśli nadal nie jest widoczne, spróbuj wyczyścić pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**, a następnie kliknij „Wyczyść pamięć podręczną”).

**P: Obliczona cena bez podatku wydaje się nieprawidłowa.**
O: Moduł opiera się na regule podatkowej przypisanej do produktu.
1. **Sprawdź regułę podatkową produktu:** Przejdź do strony produktu, zakładki „Ceny” i sprawdź, czy dla produktu wybrana jest prawidłowa „Reguła podatkowa”.
2. **Sprawdź konfigurację reguły podatkowej:** Przejdź do **Lokalizacja > Podatki > Reguły podatkowe** i upewnij się, że stawki podatkowe zdefiniowane dla wybranej reguły podatkowej są prawidłowe dla Twoich docelowych krajów/stref.
3. **Wyczyść pamięć podręczną:** Po zweryfikowaniu i ewentualnym poprawieniu ustawień podatkowych, wyczyść pamięć podręczną PrestaShop.

**P: Czy ten moduł wpływa na istniejące ceny specyficzne?**
O: Nie, ten moduł dodaje tylko nowe pole wejściowe do formularza tworzenia/edycji ceny specyficznej. Nie zmienia ani nie przelicza żadnych cen specyficznych, które zostały utworzone przed jego instalacją lub za pomocą domyślnego pola „Cena bez podatku”. Po prostu zapewnia alternatywny sposób wprowadzania nowych cen specyficznych.

**P: Czy ten moduł będzie działał z moim niestandardowym motywem?**
O: Tak, ten moduł modyfikuje głównie standardowy formularz Panelu administracyjnego PrestaShop. Wykorzystuje standardowe hooki PrestaShop i JavaScript do wstrzykiwania nowego pola. Jest bardzo mało prawdopodobne, aby kolidował z niestandardowymi motywami front-office, ponieważ nie ma komponentów wyświetlania w front-office.

**P: Otrzymuję błąd po aktualizacji PrestaShop.**
O: Po każdej większej aktualizacji PrestaShop dobrą praktyką jest:
1. Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**).
2. Sprawdź, czy na Twoim koncie MyPresta.eu jest dostępna nowa wersja modułu „Specific price tax included field”, ponieważ aktualizacje często zawierają poprawki kompatybilności.
3. Jeśli problem nadal występuje, skontaktuj się z pomocą techniczną MyPresta.eu.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Specific price tax included field” (`sptincl`) to lekki moduł PrestaShop 1.7.x zaprojektowany w celu ulepszenia interfejsu zarządzania cenami specyficznymi w Panelu administracyjnym. Działa głównie poprzez wstrzykiwanie JavaScriptu do hooka `actionAdminControllerSetMedia`, który następnie modyfikuje DOM formularza cen specyficznych, aby dodać pole „Cena z podatkiem” i zaimplementować niezbędną logikę obliczeń po stronie klienta. Nie wprowadza nowych tabel baz danych, kontrolerów ani złożonej logiki biznesowej po stronie serwera poza swoją konfiguracją.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała jego funkcjonalność jest wstrzykiwana do istniejących stron administracyjnych PrestaShop za pośrednictwem hooków i JavaScriptu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas PHP ani definicji `ObjectModel`. Jego podstawowa logika znajduje się w głównym pliku modułu (`sptincl.php`).

### 4.4 Zasoby JavaScript (`views/js/`)

- **`sptincl/views/js/sptincl.js`**
  - **Zakres:** Panel administracyjny (konkretnie formularz tworzenia/edycji ceny specyficznej).
  - **Cel:** Ten skrypt odpowiada za podstawową funkcjonalność modułu.
    - **Manipulacja DOM:** Dynamicznie dodaje nowe pole wejściowe dla „Ceny z podatkiem” do formularza ceny specyficznej. Modyfikuje również zachowanie istniejącego pola „Cena bez podatku”.
    - **Słuchacze zdarzeń:** Dołącza słuchacze zdarzeń (np. `keyup`, `change`) zarówno do nowego pola „Cena z podatkiem”, jak i do istniejącego pola „Cena bez podatku”, a także do selektora reguły podatkowej.
    - **Logika obliczeń:** Gdy użytkownik wprowadzi wartość do pola „Cena z podatkiem” lub zmieni regułę podatkową, skrypt oblicza odpowiadającą wartość „Ceny bez podatku” przy użyciu wybranej stawki podatkowej. Odwrotnie, jeśli pole „Cena bez podatku” zostanie zmodyfikowane, oblicza wartość „Ceny z podatkiem”.
    - **AJAX (niejawny):** Chociaż nie wykonuje bezpośrednio wywołań AJAX, opiera się na stawkach podatkowych dostępnych w DOM lub pobranych przez istniejące mechanizmy PrestaShop w celu wykonania swoich obliczeń. Używa funkcji `getTaxRate()` (która może być globalną funkcją JS PrestaShop lub niestandardową zdefiniowaną w skrypcie) do pobierania bieżącej stawki podatkowej na podstawie wybranej reguły podatkowej.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Opiera się na domyślnych stylach PrestaShop dla elementów formularza, zapewniając bezproblemową integrację z interfejsem użytkownika Panelu administracyjnego.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie wykorzystuje niestandardowych plików szablonów Smarty. Jego konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównej klasy modułu, a jego modyfikacje front-end są wyłącznie oparte na JavaScript.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele baz danych**: Ten moduł nie tworzy żadnych niestandardowych tabel baz danych. Przechowuje swoje ustawienia konfiguracyjne (takie jak `mypresta_updates`, `update_`, `updatev_`) w standardowej tabeli `ps_configuration`.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny jest inicjowany, a jego zasoby multimedialne (JS/CSS) są ustawiane. | Jest to główny hook używany przez moduł. Wstrzykuje plik JavaScript `sptincl.js` do Panelu administracyjnego, szczególnie celując w formularz tworzenia/edycji ceny specyficznej. Pozwala to modułowi modyfikować DOM formularza i dodawać logikę obliczeń po stronie klienta. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Specific price tax included field”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
"""
