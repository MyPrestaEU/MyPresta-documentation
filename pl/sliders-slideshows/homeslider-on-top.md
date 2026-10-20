---
title: "Homeslider on top - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Homeslider on top od MyPresta.eu."
sidebar:
  label: "Homeslider on top - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Homeslider on top na MyPresta.eu](https://mypresta.eu/modules/slider-slideshow/homeslider-on-top.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/sliders-slideshows/homeslider-on-top/)
>
> ---


# Homeslider on top

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do instalacji PrestaShop i będą obsługiwać ten moduł.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

Ten moduł jest zaprojektowany tak, aby był niezwykle prosty, działając przede wszystkim jako „most”, aby umożliwić wyświetlanie *domyślnego suwaka obrazów PrestaShop* w nowej lokalizacji. Dlatego jego własny ekran konfiguracji jest minimalny. Rzeczywiste obrazy suwaka, linki i ustawienia (takie jak prędkość, pauza po najechaniu myszą itp.) są zarządzane za pomocą standardowego modułu PrestaShop „Suwak obrazów”.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po zainstalowaniu „Homeslider on top” przejdź do **Moduły > Menedżer modułów**, wyszukaj „Homeslider on top” i kliknij „Konfiguruj”.

Zazwyczaj znajdziesz bardzo prosty interfejs konfiguracji, skupiony głównie na włączaniu lub wyłączaniu podstawowej funkcjonalności modułu.

- **Co robi to ustawienie:** To ustawienie kontroluje, czy moduł „Homeslider on top” jest aktywny i próbuje wyświetlić Twój suwak obrazów w wyznaczonej górnej pozycji.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączony:* Moduł zarejestruje swoje haki i spróbuje wyrenderować domyślny suwak obrazów PrestaShop na górze Twojego sklepu.
  - *Gdy wyłączony:* Moduł przestanie działać, a suwak obrazów nie pojawi się w górnej pozycji (powróci do swojego domyślnego miejsca, jeśli standardowy moduł Suwak obrazów jest nadal aktywny i podłączony gdzie indziej).
- **Zalecana wartość:** **TAK** (Włączony), jeśli chcesz, aby Twój suwak pojawiał się na górze.
- **Scenariusz/przykład dla sprzedawcy:** Właśnie wprowadziłeś nową kolekcję i chcesz ją wyróżnić dużym banerem na samej górze swojej witryny. Włączyłbyś ten moduł. Jeśli później zdecydujesz, że wolisz suwak w innym miejscu (np. pod nagłówkiem), możesz wyłączyć ten moduł i ponownie podłączyć standardowy moduł Suwak obrazów gdzie indziej.

**Ważna uwaga:** Ten moduł *nie* zarządza obrazami ani ustawieniami samego suwaka. Aby dodać, edytować lub usunąć slajdy, lub zmienić zachowanie suwaka (takie jak prędkość przejścia, automatyczne odtwarzanie itp.), musisz przejść do konfiguracji modułu **„Suwak obrazów”** (często znajdującego się w **Moduły > Menedżer modułów**, wyszukaj „Suwak obrazów” lub „ps\_imageslider”).

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Moduł Włączony/Wyłączony | Włączony | Kontroluje, czy moduł aktywnie wyświetla suwak obrazów na górze sklepu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Mój suwak w ogóle się nie wyświetla, nawet po włączeniu modułu.**
O:

1. **Sprawdź moduł „Suwak obrazów”:** Upewnij się, że *domyślny moduł PrestaShop „Suwak obrazów”* (często nazywany `ps_imageslider`) jest zainstalowany, włączony i ma skonfigurowane slajdy. Ten moduł „Homeslider on top” zmienia tylko *pozycję* istniejącego suwaka.
2. **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami PrestaShop potrzebuje odświeżenia pamięci podręcznej, aby rozpoznać nowe miejsca modułów.
3. **Kompatybilność z motywem:** Chociaż zaprojektowany z myślą o szerokiej kompatybilności, niektóre mocno dostosowane motywy mogą nadpisywać domyślne zachowania haków. Jeśli problemy nadal występują, skontaktuj się z deweloperem swojego motywu lub wsparciem MyPresta.eu.

**P: Suwak się wyświetla, ale wygląda dziwnie lub jest źle wyrównany.**
O:

1. **Sprawdź ustawienia „Suwaka obrazów”:** Upewnij się, że obrazy, które przesłałeś do *domyślnego modułu PrestaShop „Suwak obrazów”*, mają spójne wymiary i wysoką jakość.
2. **Stylizacja motywu:** CSS Twojego motywu może powodować konflikty. Ten moduł przede wszystkim zajmuje się umieszczeniem. Jeśli stylizacja jest nieprawidłowa, prawdopodobnie jest to problem z CSS Twojego motywu, który wchodzi w interakcję z domyślnymi stylami suwaka. Może być konieczne, aby programista internetowy sprawdził CSS.

**P: Jak zmienić obrazy lub prędkość suwaka?**
O: Ten moduł kontroluje tylko *umieszczenie*. Aby zarządzać rzeczywistą zawartością (obrazami, linkami, opisami) i zachowaniem (prędkością, automatycznym odtwarzaniem, pauzą po najechaniu myszą) suwaka, musisz przejść do konfiguracji modułu **„Suwak obrazów”** (standardowy moduł PrestaShop, zazwyczaj znajduje się go, wyszukując „Suwak obrazów” w **Moduły > Menedżer modułów**).

**P: Czy mogę mieć dwa suwaki, jeden na górze i jeden w domyślnej pozycji?**
O: Ten moduł specjalnie przenosi *domyślny* suwak obrazów PrestaShop na górę. Jeśli chcesz mieć drugi, niezależny suwak, potrzebowałbyś innego modułu zaprojektowanego do tego celu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera przegląd techniczny dla programistów i webmasterów, którzy chcą zrozumieć, dostosować lub rozwiązać problemy z modułem „Homeslider on top”.

### 4.1 Przegląd architektury

Moduł „Homeslider on top” to lekki moduł PrestaShop, zaprojektowany przede wszystkim do zmiany lokalizacji wyświetlania podstawowego modułu `ps_imageslider`. Osiąga to poprzez wyrejestrowanie `ps_imageslider` z jego domyślnych haków (takich jak `displayHome`) i ponowne zarejestrowanie go do bardziej widocznego haka, zazwyczaj `displayHeader`. Nie wprowadza nowych tabel baz danych, złożonych klas ani rozbudowanych zasobów front-office, co czyni go prostym, ale skutecznym „menedżerem haków” dla istniejącej funkcjonalności suwaka.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów Front-Office ani Back-Office. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Podstawowe klasy i modele (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas ani modeli. Działa poprzez interakcję z podstawowymi funkcjami zarządzania modułami PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. JavaScript dla funkcjonalności suwaka jest dostarczany przez sam moduł `ps_imageslider`.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Stylizacja suwaka jest dostarczana przez moduł `ps_imageslider` i/lub aktywny motyw PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie zawiera żadnych niestandardowych plików szablonów Smarty. Opiera się na szablonach dostarczanych przez moduł `ps_imageslider`.

### 4.7 Schemat bazy danych i mapa haków

- **Tabele baz danych**: Ten moduł nie tworzy żadnych niestandardowych tabel baz danych. Jego konfiguracja jest przechowywana w `ps_configuration` przy użyciu standardowych kluczy konfiguracyjnych PrestaShop.
- **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `install()` | Podczas instalacji modułu | Rejestruje moduł do `displayHeader` i potencjalnie wyrejestrowuje `ps_imageslider` z `displayHome` lub innych domyślnych haków. |
| `uninstall()` | Podczas deinstalacji modułu | Wyrejestrowuje moduł z `displayHeader` i potencjalnie ponownie rejestruje `ps_imageslider` do jego domyślnych haków. |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` lub na samej górze `<body>` | Jest to główny hak, w którym moduł próbuje renderować zawartość `ps_imageslider`. |
| `hookDisplayHeader` | Gdy wywoływany jest `displayHeader` | Metoda modułu, która wykonuje się, gdy wywoływany jest `displayHeader`. Zazwyczaj wywołuje `Module::hookDisplayHome()` modułu `ps_imageslider`, aby wyrenderować jego zawartość. |

Główna logika znajduje się w pliku `homeslider-on-top.php`, w szczególności w metodach `install()`, `uninstall()` i `hookDisplayHeader()`. Metoda `hookDisplayHeader()` jest kluczowa, ponieważ odpowiada za pobieranie i renderowanie zawartości modułu `ps_imageslider`, gdy ten moduł jest aktywny.

**Kluczowa logika w `homeslider-on-top.php`:**

- **`__construct()`**: Ustawia podstawowe informacje o module.
- **`install()`**:
  - Wywołuje `parent::install()`.
  - Rejestruje moduł do `displayHeader`.
  - Co najważniejsze, często próbuje wyrejestrować moduł `ps_imageslider` z `displayHome`, aby zapobiec podwójnemu wyświetlaniu, a następnie rejestruje `ps_imageslider` do `displayHeader`, jeśli jeszcze tam nie jest, lub zapewnia, że jego zawartość jest renderowana za pośrednictwem metody `hookDisplayHeader()` tego modułu.
- **`uninstall()`**:
  - Wywołuje `parent::uninstall()`.
  - Wyrejestrowuje moduł z `displayHeader`.
  - Ponownie rejestruje `ps_imageslider` do `displayHome`, aby przywrócić domyślne zachowanie.
- **`getContent()`**: Obsługuje formularz konfiguracji modułu w panelu administracyjnym (który jest zazwyczaj bardzo prosty, często tylko przełącznik włącz/wyłącz).
- **`hookDisplayHeader()`**:
  - Ta metoda jest wykonywana, gdy PrestaShop wywołuje hak `displayHeader`.
  - Zazwyczaj sprawdza, czy moduł `ps_imageslider` jest zainstalowany i włączony.
  - Jeśli tak, bezpośrednio wywołuje metodę `hookDisplayHome()` modułu `ps_imageslider`, aby pobrać jego wyrenderowaną zawartość i zwrócić ją, skutecznie „przenosząc” wyjście suwaka do pozycji `displayHeader`.

Programiści, którzy chcą dostosować ten moduł, skupiliby się przede wszystkim na metodzie `hookDisplayHeader()`, jeśli chcieliby zmienić sposób pobierania lub opakowywania zawartości `ps_imageslider`, lub na metodach `install()`/`uninstall()`, jeśli musieliby zmienić konkretne zaangażowane haki.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Homeslider on top”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
