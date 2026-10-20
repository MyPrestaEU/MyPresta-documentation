---
title: "Zamówienie utworzone przez pracownika - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla programistów modułu PrestaShop „Zamówienie utworzone przez pracownika” od MyPresta.eu."
sidebar:
  label: "Zamówienie utworzone przez pracownika - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Order created by employee na MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-created-by-employee.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/order-created-by-employee/)
>
> ---


# Zamówienie utworzone przez pracownika

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) zazwyczaj dostępne w każdym środowisku hostingowym kompatybilnym z PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie przycisku „Konfiguruj” przeniesie Cię do głównej strony konfiguracji modułu.

Moduł ten został zaprojektowany tak, aby był niezwykle prosty i skuteczny, wymagając minimalnej konfiguracji. Po instalacji automatycznie rozpoczyna zbieranie niezbędnych danych.

**Co robi ten ekran:**
Ta strona służy jako potwierdzenie, że moduł jest zainstalowany i aktywny. Nie przedstawia żadnych konfigurowalnych ustawień, ponieważ podstawowa funkcjonalność modułu (rejestrowanie zamówień utworzonych przez pracowników) jest domyślnie włączona po instalacji.

**Wpływ zmiany tego ustawienia:**
Na tym ekranie nie ma żadnych ustawień do zmiany. Funkcjonalność modułu jest „zawsze włączona” po zainstalowaniu.

**Zalecana wartość:**
Brak wartości do ustawienia. Po prostu upewnij się, że moduł jest zainstalowany i włączony.

**Scenariusz / przykład dla sprzedawcy:**
Właśnie zainstalowałeś moduł. Przechodzisz do jego strony konfiguracji i widzisz prostą wiadomość potwierdzającą jego status. Od tego momentu każde nowe zamówienie utworzone przez pracownika za pośrednictwem Panelu administracyjnego PrestaShop zostanie odpowiednio oznaczone. Podczas przeglądania szczegółów zamówienia zobaczysz nową sekcję wskazującą, czy zostało ono utworzone przez pracownika i który pracownik to zrobił.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Ten moduł nie dodaje nowych dedykowanych pozycji menu ani złożonych ekranów administracyjnych. Jego funkcjonalność integruje się bezpośrednio z istniejącą stroną szczegółów zamówienia PrestaShop.

**Nazwa ekranu i lokalizacja w menu:**
Informacje dostarczane przez ten moduł są wyświetlane bezpośrednio na **Stronie szczegółów zamówienia**.
Aby uzyskać do nich dostęp:

1.  Przejdź do **Zamówienia > Zamówienia** w Panelu administracyjnym PrestaShop.
2.  Kliknij dowolne zamówienie z listy, aby wyświetlić jego szczegóły.

**Dostępne akcje i ustawienia:**
Na Stronie szczegółów zamówienia znajdziesz nową sekcję (zazwyczaj u góry lub w dedykowanym bloku), która wyświetla informację, czy zamówienie zostało utworzone przez pracownika. Jeśli tak, pokaże również imię i nazwisko pracownika, który je utworzył.

**Wpływ zmian:**
Na tym widoku nie ma żadnych akcji ani ustawień do zmiany. Ta sekcja ma charakter wyłącznie informacyjny, dostarczając danych zebranych przez moduł.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
Podczas przeglądania zamówień, zwłaszcza tych, które wydają się nietypowe, lub podczas przeprowadzania audytów wewnętrznych, zawsze sprawdzaj sekcję „Zamówienie utworzone przez pracownika” na stronie szczegółów zamówienia. To szybkie sprawdzenie może dostarczyć natychmiastowego kontekstu dotyczącego pochodzenia zamówienia, pomagając zrozumieć, czy był to bezpośredni zakup klienta, czy wewnętrzny wpis.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | *(Brak konfigurowalnych ustawień)* | N/A | Potwierdza instalację i aktywację modułu. Funkcjonalność modułu jest zawsze włączona. |
| Strona szczegółów zamówienia (Panel administracyjny) | Blok informacyjny „Zamówienie utworzone przez pracownika” | N/A | Wyświetla informację, czy zamówienie zostało utworzone przez pracownika i jego imię i nazwisko. Ma charakter wyłącznie informacyjny. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zainstalowałem moduł, ale nie widzę żadnych zmian w starych zamówieniach.**
O: Ten moduł zaczyna zbierać dane od momentu instalacji. Nie może retrospektywnie określić, czy poprzednie zamówienia zostały utworzone przez pracownika. Informacje „Zamówienie utworzone przez pracownika” będą widoczne tylko w zamówieniach złożonych *po* pomyślnej instalacji i aktywacji modułu.

**P: Utworzyłem zamówienie w Panelu administracyjnym, ale nie widzę informacji o pracowniku na stronie szczegółów zamówienia.**
O: Najpierw upewnij się, że moduł jest zainstalowany i włączony (sprawdź **Moduły > Menedżer modułów**). Jeśli tak, wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**). Jeśli problem nadal występuje, upewnij się, że przeglądasz zamówienie, które zostało *faktycznie utworzone przez pracownika* w Panelu administracyjnym *po* instalacji modułu.

**P: Czy ten moduł wpływa na wydajność mojego sklepu?**
O: Nie, moduł jest bardzo lekki. Dodaje tylko niewielką część danych podczas procesu tworzenia zamówienia w Panelu administracyjnym i wyświetla te dane na stronie szczegółów zamówienia. Nie ma wpływu na wydajność Twojego sklepu ani doświadczenie klienta.

**P: Czy mogę wyłączyć funkcjonalność modułu bez jego odinstalowywania?**
O: Ten moduł nie ma przełącznika włącz/wyłącz w swojej konfiguracji. Aby zatrzymać jego funkcjonalność, musiałbyś wyłączyć lub odinstalować moduł za pośrednictwem Menedżera modułów. Jednak ze względu na jego korzystny charakter dla śledzenia wewnętrznego, ogólnie zaleca się utrzymywanie go w stanie aktywnym.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Zamówienie utworzone przez pracownika” (`logoe`) to prosty moduł PrestaShop zaprojektowany w celu rozszerzenia podstawowej funkcjonalności `Order`. Działa głównie poprzez podłączenie się do procesu tworzenia zamówienia w Panelu administracyjnym w celu zarejestrowania `id_employee` odpowiedzialnego za zamówienie. Informacje te są następnie wyświetlane na istniejącej stronie szczegółów zamówienia w Panelu administracyjnym. Moduł ten wykorzystuje prosty wzorzec sterowany zdarzeniami za pomocą hooków PrestaShop.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Cała jego logika jest obsługiwana w głównym pliku modułu i za pośrednictwem hooków.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas ani definicji `ObjectModel`. Bezpośrednio współdziała z obiektem `Order` i `Configuration` w celu ustawień.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Stylizacja wyświetlanych informacji jest zazwyczaj minimalna i opiera się na istniejących stylach Panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł używa jednego pliku szablonu do wyświetlania informacji w Panelu administracyjnym.

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `logoe/views/templates/admin/logoelog.tpl`: Ten szablon jest odpowiedzialny za renderowanie bloku informacyjnego „Zamówienie utworzone przez pracownika” na stronie szczegółów zamówienia w Panelu administracyjnym PrestaShop. Zazwyczaj wyświetla imię i nazwisko pracownika, jeśli zamówienie zostało utworzone przez pracownika. Prawdopodobnie jest renderowany za pomocą hooka takiego jak `displayAdminOrder` lub `displayAdminOrderTabContent`.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł nie tworzy nowej dedykowanej tabeli bazy danych. Zamiast tego rozszerza istniejącą tabelę `ps_orders` poprzez dodanie nowej kolumny podczas instalacji.

    -   `ps_orders`: Nowa kolumna, prawdopodobnie `id_employee_created`, jest dodawana do tej tabeli w celu przechowywania identyfikatora pracownika, który utworzył zamówienie. Ta kolumna byłaby typu `INT(10) UNSIGNED` i mogłaby być pusta (nullable), z domyślną wartością `NULL`.
-   **Tabela zarejestrowanych hooków**:

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `actionOrderAdd` | Po pomyślnym dodaniu nowego zamówienia do bazy danych. | Ten hook jest kluczowy. Służy do przechwytywania `id_employee` z bieżącej sesji Panelu administracyjnego i aktualizowania kolumny `id_employee_created` nowo utworzonego zamówienia w `ps_orders`. |
    | `displayAdminOrder` (lub podobny, np. `displayAdminOrderTabContent`, `displayAdminOrderMain`) | Gdy renderowana jest strona szczegółów zamówienia w Panelu administracyjnym. | Ten hook służy do wstrzyknięcia szablonu `logoelog.tpl` na stronę szczegółów zamówienia, wyświetlając informacje `id_employee_created` (np. imię i nazwisko pracownika). |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnego wsparcia, aktualizacji modułu i wszelkiej dalszej pomocy, odwiedź swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnianie terminowego wsparcia i zapewnienie doskonałego funkcjonowania Twojego modułu.
"""
