---
title: "Material Icons + Font Awesome - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracyjny"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Material Icons + Font Awesome od MyPresta.eu."
sidebar:
  label: "Material Icons + Font Awesome - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracyjny"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Material Icons + Font Awesome na MyPresta.eu](https://mypresta.eu/modules/front-office-features/material-icons-font-awesome.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/material-icons-font-awesome/)
>
> ---


# Material Icons + Font Awesome

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Brak specjalnych wymagań poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu „Material Icons + Font Awesome”. Znajdziesz go, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Material Icons + Font Awesome” i klikając „Konfiguruj”.

#### **Dodaj Font Awesome**

- **Co robi to ustawienie:** Ten przełącznik kontroluje, czy biblioteka ikon Font Awesome jest ładowana do front-office Twojego sklepu (co widzą klienci) i back-office (Twój panel administracyjny).
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone:* Plik CSS Font Awesome zostanie dodany do sekcji `<head>` Twojej witryny, udostępniając wszystkie ikony Font Awesome. Naprawi to wszelkie brakujące ikony Font Awesome.
  - *Gdy wyłączone:* Plik CSS Font Awesome NIE zostanie załadowany przez ten moduł. Jeśli Twój motyw lub inny moduł już ładuje Font Awesome, lub jeśli go nie potrzebujesz, możesz to wyłączyć, aby uniknąć dwukrotnego ładowania.
- **Zalecana wartość:**
  - **Włączone**, jeśli zauważysz brakujące ikony Font Awesome w swoim sklepie lub w panelu administracyjnym, lub jeśli planujesz używać ikon Font Awesome w swojej treści.
  - **Wyłączone**, jeśli wszystkie ikony Font Awesome już wyświetlają się poprawnie (co oznacza, że Twój motyw lub inny moduł już je ładuje), aby zapobiec redundantnemu ładowaniu.
- **Scenariusz / przykład dla sprzedawcy:** Zainstalowałeś nowy moduł płatności, a jego ikony metod płatności (np. symbol karty kredytowej) wyświetlają się jako puste pola. Jeśli te ikony są oparte na Font Awesome, włączenie tego ustawienia sprawi, że pojawią się poprawnie.

#### **Dodaj Material Icons**

- **Co robi to ustawienie:** Ten przełącznik kontroluje, czy biblioteka Material Icons (od Google) jest ładowana do front-office i back-office Twojego sklepu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone:* Plik CSS Material Icons zostanie dodany do sekcji `<head>` Twojej witryny, udostępniając wszystkie Material Icons. Naprawi to wszelkie brakujące Material Icons.
  - *Gdy wyłączone:* Plik CSS Material Icons NIE zostanie załadowany przez ten moduł. Jeśli Twój motyw lub inny moduł już ładuje Material Icons, lub jeśli ich nie potrzebujesz, możesz to wyłączyć.
- **Zalecana wartość:**
  - **Włączone**, jeśli zauważysz brakujące Material Icons w swoim sklepie lub w panelu administracyjnym.
  - **Wyłączone**, jeśli wszystkie Material Icons już wyświetlają się poprawnie (co oznacza, że Twój motyw lub inny moduł już je ładuje), aby zapobiec redundantnemu ładowaniu.
- **Scenariusz / przykład dla sprzedawcy:** Twój motyw używa Material Icons dla strzałek nawigacyjnych lub niektórych elementów strony produktu, ale po aktualizacji motywu zniknęły. Włączenie tego ustawienia prawdopodobnie je przywróci.

#### **Tabela szybkiego odniesienia konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Dodaj Font Awesome | Włączone (jeśli potrzebne) | Ładuje bibliotekę ikon Font Awesome dla front-office i back-office. Naprawia brakujące ikony Font Awesome. |
| Konfiguracja modułu | Dodaj Material Icons | Włączone (jeśli potrzebne) | Ładuje bibliotekę ikon Material Icons dla front-office i back-office. Naprawia brakujące ikony Material Icons. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Włączyłem ustawienia, ale ikony nadal brakuje. Co powinienem zrobić?**
O: Najpierw wyczyść pamięć podręczną PrestaShop. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Wyczyść również pamięć podręczną przeglądarki (Ctrl+F5 lub Cmd+Shift+R). Jeśli ikony nadal brakuje, możliwe jest, że ikony, których szukasz, należą do innej biblioteki ikon nieobjętej tym modułem, lub istnieje konflikt CSS w Twoim motywie.

**P: Czy ten moduł spowolni moją witrynę?**
O: Moduł ładuje standardowe pliki CSS dla bibliotek ikon. Jeśli włączysz tylko te biblioteki, których potrzebujesz, i nie są one już ładowane przez Twój motyw, wpływ na wydajność jest minimalny i niezbędny do poprawnego wyświetlania. Jeśli włączysz bibliotekę, która jest już ładowana przez Twój motyw, będziesz ją ładować dwukrotnie, co może spowodować niewielkie spowolnienie. Zawsze sprawdzaj, czy Twój motyw już zawiera te biblioteki, zanim je tutaj włączysz.

**P: Mój niestandardowy motyw ma własny zestaw ikon. Czy ten moduł będzie kolidował?**
O: Nie powinien bezpośrednio kolidować. Ten moduł dodaje określone biblioteki ikon. Jeśli Twój motyw używa innego zestawu ikon (np. niestandardowych SVG lub innej biblioteki ikon czcionek), ten moduł po prostu doda Font Awesome i/lub Material Icons obok niego. Jeśli doświadczysz konfliktów, możesz spróbować wyłączyć jedną lub obie opcje w module, aby sprawdzić, czy to rozwiąże problem.

**P: Jak sprawdzić, czy mój motyw już ładuje Font Awesome lub Material Icons?**
O: Najłatwiejszym sposobem jest kliknięcie prawym przyciskiem myszy na stronie Twojego sklepu (front-office) i wybranie „Wyświetl źródło strony” lub „Zbadaj element”. Następnie wyszukaj „font-awesome.css” lub „material-icons.css” w sekcji `<head>`. Jeśli je znajdziesz, Twój motyw prawdopodobnie już je ładuje. Alternatywnie, jeśli wszystkie ikony wyświetlają się poprawnie bez tego modułu, to Twój motyw lub inny moduł już to obsługuje.

**P: Czy mogę używać jednocześnie Font Awesome i Material Icons?**
O: Tak, absolutnie. Możesz włączyć obie opcje w konfiguracji modułu. Jest to często konieczne, jeśli różne części Twojego sklepu (np. Twój motyw i moduł strony trzeciej) polegają na różnych bibliotekach ikon.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Material Icons + Font Awesome” to lekki moduł PrestaShop zaprojektowany przede wszystkim do wstrzykiwania zewnętrznych arkuszy stylów CSS dla bibliotek ikon. Przestrzega standardowej struktury modułu PrestaShop, wykorzystując hooki do integracji swojej funkcjonalności z front-office i back-office. Nie wprowadza niestandardowych kontrolerów, modeli ani tabel baz danych, koncentrując się wyłącznie na zarządzaniu zasobami.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych niestandardowych kontrolerów front-office ani back-office. Cała logika jest obsługiwana w głównym pliku modułu (`fonticons.php`) za pośrednictwem hooków.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Cała konfiguracja jest przechowywana bezpośrednio w `ps_configuration` przy użyciu kluczy zdefiniowanych poniżej.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Podstawowa funkcjonalność modułu opiera się na tych plikach CSS:

- **`fonticons/views/css/font-awesome.css`**:

  - **Zakres**: Front-office i Back-office.
  - **Cel**: Zawiera reguły CSS i deklaracje `@font-face` dla biblioteki ikon Font Awesome. Ten plik jest odpowiedzialny za udostępnienie ikon Font Awesome w całym sklepie.
  - **Kluczowe selektory klas CSS**: `fa`, `fas`, `far`, `fal`, `fab` (dla różnych stylów Font Awesome), a następnie specyficzne klasy ikon, takie jak `fa-shopping-cart`, `fa-user` itp. Programiści mogą je nadpisać, celując w te klasy w CSS swojego motywu.
- **`fonticons/views/css/material-icons.css`**:

  - **Zakres**: Front-office i Back-office.
  - **Cel**: Zawiera reguły CSS i deklaracje `@font-face` dla biblioteki Material Icons od Google. Ten plik udostępnia Material Icons.
  - **Kluczowe selektory klas CSS**: `material-icons`. Ikony są zazwyczaj renderowane przez umieszczenie nazwy ligatury ikony w elemencie z tą klasą (np. `<i class="material-icons">shopping_cart</i>`). Programiści mogą nadpisać styl dla tej klasy.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **`fonticons/views/advert.tpl`**:
  - **Zakres**: Back-office (strona konfiguracji modułu).
  - **Cel**: Ten szablon służy do wyświetlania reklamy lub komunikatu promocyjnego na stronie konfiguracji modułu w panelu administracyjnym PrestaShop. Jest renderowany przez metodę `getContent()`.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  Ten moduł nie tworzy żadnych niestandardowych tabel baz danych. Przechowuje swoje ustawienia konfiguracyjne w standardowej tabeli `ps_configuration`.

  - Wpisy `ps_configuration`:
    - `fonticons_FA`: Przechowuje status (1 dla włączonego, 0 dla wyłączonego) włączenia Font Awesome dla front-office.
    - `fonticons_MI`: Przechowuje status (1 dla włączonego, 0 dla wyłączonego) włączenia Material Icons dla front-office.
    - `BO_fonticons_FA`: Przechowuje status (1 dla włączonego, 0 dla wyłączonego) włączenia Font Awesome dla back-office.
    - `BO_fonticons_MI`: Przechowuje status (1 dla włączonego, 0 dla wyłączonego) włączenia Material Icons dla back-office.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony front-office. | Służy do ładowania plików CSS Font Awesome i/lub Material Icons dla części sklepu widocznej dla klienta, na podstawie konfiguracji `fonticons_FA` i `fonticons_MI`. |
| `actionAdminControllerSetMedia` | Wykonywany, gdy AdminController ustawia swoje zasoby multimedialne (CSS/JS). | Służy do ładowania plików CSS Font Awesome i/lub Material Icons dla panelu administracyjnego PrestaShop, na podstawie konfiguracji `BO_fonticons_FA` i `BO_fonticons_MI`. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Znajdziesz tam zakupione moduły i linki do pobierania. W celu uzyskania pomocy technicznej lub w razie pytań, skorzystaj z kanałów wsparcia dostępnych na MyPresta.eu.
"""
