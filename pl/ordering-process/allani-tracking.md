---
title: "Śledzenie Allani - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop do śledzenia Allani od MyPresta.eu."
sidebar:
  label: "Śledzenie Allani - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Allani tracking na MyPresta.eu](https://mypresta.eu/modules/ordering-process/allani-tracking.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/allani-tracking/)
>
> ---


# Śledzenie Allani

## 1. Wymagania i Kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Kompatybilność PHP**: PHP 5.6 - 8.5 (Moduł jest zaprojektowany do pracy w szerokim zakresie wersji PHP, aż do najnowszej stabilnej wersji obsługiwanej przez PrestaShop 1.7.x i przyszłe wersje.)
- **Wymagania Hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) zazwyczaj dostępne w każdym nowoczesnym środowisku hostingowym PrestaShop.

## 2. Kompletny Przewodnik Konfiguracji (Każde Ustawienie Pogrupowane Według Ekranu)

### 2.1 Strona Konfiguracji Modułu (Panel Administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Śledzenie Allani”, aby uzyskać dostęp do jego ustawień.

#### Identyfikacja Zamówienia

Ta sekcja kontroluje, w jaki sposób moduł identyfikuje i wysyła dane zamówienia do Allani.

- **Co robi to ustawienie:** Jest to kluczowe ustawienie dla modułu. Określa, czy moduł jest aktywny i wysyła dane zamówienia do Allani.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Moduł będzie automatycznie wysyłał szczegóły zamówienia (identyfikatory produktów, wartość zamówienia, identyfikator zamówienia) do platformy Allani za każdym razem, gdy klient pomyślnie zrealizuje zamówienie w Twoim sklepie PrestaShop. Jest to niezbędne, aby Allani śledziło Twoją sprzedaż.
  - *Gdy wyłączone (NIE):* Moduł przestanie wysyłać jakiekolwiek dane zamówienia do Allani. Oznacza to, że Allani nie będzie otrzymywać aktualizacji w czasie rzeczywistym dotyczących Twojej sprzedaży, co może wpłynąć na Twoje analizy i raportowanie na ich platformie.
- **Zalecana wartość:** **TAK**. Aby w pełni wykorzystać usługę śledzenia Allani, to ustawienie powinno być zawsze włączone.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli właśnie zarejestrowałeś się w Allani i chcesz natychmiast rozpocząć śledzenie sprzedaży, włączysz to ustawienie. Jeśli tymczasowo chcesz wstrzymać transmisję danych do Allani w celu konserwacji lub testowania, możesz je wyłączyć, ale pamiętaj, aby później je ponownie włączyć.

#### Inne Ustawienia Wewnętrzne (Niekonfigurowalne bezpośrednio przez sprzedawcę)

Możesz zobaczyć inne klucze konfiguracyjne, takie jak `mypresta_updates`, `update_`, `updatev_`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`. Są to wewnętrzne ustawienia używane przez moduł do własnych kontroli aktualizacji lub do interakcji z podstawowymi funkcjonalnościami PrestaShop (takimi jak obsługa języków). Nie musisz ich konfigurować i nie są one udostępniane jako opcje edytowalne przez użytkownika.

### 2.2 Tabela Szybkiego Odniesienia do Konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i Wpływ |
| --- | --- | --- | --- |
| Strona Konfiguracji Modułu | Identyfikacja Zamówienia | TAK | Kontroluje, czy dane zamówienia są wysyłane do Allani. **Włącz** dla śledzenia Allani. |

## 3. Rozwiązywanie Problemów dla Sprzedawców i Często Zadawane Pytania (FAQ)

**P: Zainstalowałem moduł, ale nie widzę żadnych zmian w moim sklepie. Czy działa?**
O: Tak, to normalne! Moduł śledzenia Allani działa całkowicie w tle. Nie dodaje żadnych widocznych elementów do front-office Twojego sklepu. Jego funkcją jest wysyłanie danych do Allani po złożeniu zamówienia. Aby potwierdzić, że działa, złóż zamówienie testowe, a następnie sprawdź swoje konto Allani pod kątem nowych danych zamówienia.

**P: Allani nie otrzymuje danych moich zamówień. Co powinienem sprawdzić?**
O:

1. **Moduł Włączony:** Przejdź do **Moduły > Menedżer modułów**, znajdź „Śledzenie Allani” i upewnij się, że jest zainstalowany i włączony.
2. **Ustawienie Konfiguracji:** Kliknij „Konfiguruj” dla modułu i upewnij się, że „Identyfikacja Zamówienia” jest ustawiona na **TAK**.
3. **Wyczyść Pamięć Podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić zastosowanie nowych ustawień. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
4. **Konto Allani:** Dokładnie sprawdź ustawienia swojego konta Allani lub skontaktuj się z obsługą Allani, aby upewnić się, że Twój sklep jest poprawnie połączony po ich stronie.
5. **Wersja PrestaShop:** Upewnij się, że pobrałeś poprawną wersję modułu dla swojej instalacji PrestaShop (np. 1.7.x, 1.6.x).

**P: Czy ten moduł spowolni mój sklep?**
O: Nie, wpływ na wydajność Twojego sklepu jest znikomy. Skrypt śledzący jest wykonywany tylko na stronie potwierdzenia zamówienia, która jest zazwyczaj ostatnim krokiem w podróży klienta. Transfer danych jest szybki i asynchroniczny, co oznacza, że nie opóźni ładowania strony dla Twoich klientów.

**P: Czy ten moduł obsługuje konfiguracje wielojęzyczne lub wielosklepowe?**
O: Moduł przede wszystkim wysyła dane liczbowe i identyfikatory produktów, które są niezależne od języka. W przypadku wielu sklepów, o ile moduł jest włączony i skonfigurowany dla każdego kontekstu sklepu, w którym chcesz śledzić zamówienia, powinien działać poprawnie.

## 4. Przewodnik dla Programistów i Webmasterów (Architektura Techniczna i Mapa Kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd Architektury

Moduł `Śledzenie Allani` to lekki moduł PrestaShop zaprojektowany do jednego celu: wysyłania danych potwierdzenia zamówienia do platformy Allani. Jest zgodny ze standardową strukturą modułu PrestaShop, wykorzystując przede wszystkim hooki do wstrzykiwania swojej logiki śledzenia. Podstawowa funkcjonalność znajduje się w głównej klasie modułu (`allanitracking.php`), która obsługuje instalację, deinstalację, konfigurację i rejestrację hooków. Nie wprowadza niestandardowych kontrolerów, modeli ani złożonych zasobów JavaScript/CSS, skupiając się wyłącznie na transmisji danych za pośrednictwem szablonu Smarty wstrzykiwanego do hooka `displayOrderConfirmation`.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Logika front-office modułu jest obsługiwana bezpośrednio w hooku `displayOrderConfirmation` za pośrednictwem szablonu Smarty.
- **Kontrolery Back-Office Admin**: Brak. Konfiguracja jest zarządzana bezpośrednio za pomocą metody `getContent()` głównej klasy modułu.

### 4.3 Klasy Podstawowe i Modele (`classes/`)

- Ten moduł nie wprowadza żadnych niestandardowych klas ani definicji `ObjectModel`. Cała logika jest zawarta w `allanitracking.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

- Ten moduł nie zawiera ani nie używa żadnych niestandardowych plików JavaScript. Skrypt śledzący jest osadzony bezpośrednio w szablonie `displayOrderConfirmation.tpl`.

### 4.5 Arkusze Stylów CSS (`views/css/`)

- Ten moduł nie zawiera ani nie używa żadnych niestandardowych plików CSS, ponieważ nie ma widocznych komponentów front-office.

### 4.6 Struktura Szablonów Smarty (`views/templates/`)

Moduł używa szablonów Smarty do wstrzykiwania skryptu śledzącego do front-office.

- **Szablony hooków (`views/templates/hook/`)**:

  - `allanitracking/views/templates/hook/displayOrderConfirmation.tpl`
    - **Hook**: `displayOrderConfirmation`
    - **Cel**: Ten szablon jest renderowany na stronie potwierdzenia zamówienia (po udanym zakupie). Zawiera podstawową logikę wysyłania danych zamówienia do Allani. Uzyskuje dostęp do zmiennych Smarty `$order` i `$products`, które są przekazywane przez PrestaShop do tego hooka, aby wyodrębnić `orderValue`, `orderID` i `productIds`. Następnie szablon konstruuje i wykonuje niezbędny kod JavaScript do przesłania tych danych do platformy Allani.
  - `allanitracking/views/templates/hook/header.tpl`
    - **Hook**: `displayHeader` (lub `header` w starszych wersjach)
    - **Cel**: Ten szablon jest zazwyczaj używany do włączania globalnego kodu JavaScript lub CSS w sekcji `<head>` strony. W kontekście tego modułu może być używany do włączania wszelkich niezbędnych globalnych skryptów Allani lub meta tagów, chociaż główna transmisja danych jest obsługiwana przez `displayOrderConfirmation.tpl`. Biorąc pod uwagę opis modułu, prawdopodobnie zawiera minimalną konfigurację lub symbol zastępczy.
- **Szablony administracyjne (`views/templates/admin/`)**: Brak.
- **Szablony front-office (`views/templates/front/`)**: Brak.

### 4.7 Schemat Bazy Danych i Mapa Hooków

- **Tabele Bazy Danych**:

  - Moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Przechowuje swoją konfigurację w tabeli `ps_configuration`, w szczególności klucz `ALLANI_ORDER_TRACK`.
  - Używa również standardowych kluczy konfiguracyjnych PrestaShop do sprawdzania aktualizacji (`mypresta_updates`, `update_`, `updatev_`).
- **Tabela Zarejestrowanych Hooków**:

| Nazwa Hooka | Czas Wykonania | Cel Techniczny |
| --- | --- | --- |
| `displayHeader` / `header` | W sekcji `<head>` każdej strony front-office. | Potencjalnie używany do globalnej inicjalizacji skryptu Allani lub meta tagów. |
| `displayOrderConfirmation` | Na stronie potwierdzenia zamówienia, po udanym zakupie. | **Główny hook dla tego modułu.** Wstrzykuje kod JavaScript do wysyłania szczegółów zamówienia (identyfikatory produktów, wartość zamówienia, identyfikator zamówienia) do platformy Allani. |

## 5. Oficjalne Wsparcie i Aktualizacje

W celu uzyskania najnowszych aktualizacji, poprawek błędów i oficjalnego wsparcia dla modułu „Śledzenie Allani”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
