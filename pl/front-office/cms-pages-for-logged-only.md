---
title: "Strony CMS tylko dla zalogowanych - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Strony CMS tylko dla zalogowanych” od MyPresta.eu."
sidebar:
  label: "Strony CMS tylko dla zalogowanych - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł CMS pages for logged only na MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-pages-for-logged-only.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/cms-pages-for-logged-only/)
>
> ---


# Strony CMS tylko dla zalogowanych

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Strony CMS tylko dla zalogowanych”. Zobaczysz pojedynczy ekran konfiguracji.

![Przykład ekranu konfiguracji modułu Strony CMS tylko dla zalogowanych](https://mypresta.eu/images/art/cms-pages-for-logged-only-configuration.png)

Ten ekran przedstawia listę wszystkich Twoich istniejących stron CMS. Dla każdej strony zobaczysz prosty przełącznik, aby włączyć lub wyłączyć ograniczenie „tylko dla zalogowanych”.

- **Nazwa ustawienia:** `cmsp` (To jest wewnętrzny identyfikator, zobaczysz rzeczywiste tytuły stron CMS).
- **Co robi to ustawienie:** To ustawienie pozwala wybrać, które konkretne strony CMS będą ograniczone tylko dla zalogowanych klientów. Każdy wiersz reprezentuje jedną ze stron CMS Twojego sklepu.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone (przełącznik jest WŁ./zielony):* Wybrana strona CMS będzie dostępna tylko dla klientów, którzy są zalogowani na swoje konta. Jeśli niezalogowany klient spróbuje odwiedzić tę stronę, zostanie przekierowany na stronę logowania. Po pomyślnym zalogowaniu zostanie odesłany z powrotem do tej konkretnej strony CMS.
  - *Gdy wyłączone (przełącznik jest WYŁ./czerwony):* Wybrana strona CMS będzie publicznie dostępna dla wszystkich odwiedzających, niezależnie od tego, czy są zalogowani, czy nie. Jest to domyślne zachowanie dla wszystkich stron CMS w PrestaShop.
- **Zalecana wartość:** Zależy to całkowicie od Twoich potrzeb biznesowych. Włącz to dla każdej strony CMS, która zawiera wrażliwe, ekskluzywne lub tylko dla członków informacje.
- **Scenariusz/przykład sprzedawcy:**
  - Masz stronę CMS „Warunki handlowe dla hurtowników”. Włączyłbyś przełącznik obok tej strony, aby tylko Twoi zarejestrowani klienci hurtowi mogli ją przeglądać.
  - Tworzysz stronę CMS „Przewodnik po treściach premium” dla lojalnych klientów. Włączyłbyś przełącznik dla tej strony, aby zachęcić do rejestracji i nagrodzić istniejących klientów.
  - Masz standardową stronę „O nas”. Pozostawiłbyś przełącznik wyłączony, ponieważ ta strona powinna być publicznie widoczna dla wszystkich odwiedzających.

Po dokonaniu wyboru pamiętaj, aby kliknąć przycisk **„Zapisz”** na dole strony, aby zastosować zmiany.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Indywidualne przełączniki stron CMS | Wyłączone (OFF) | Kontroluje, czy konkretna strona CMS wymaga zalogowania klienta, aby ją wyświetlić. Włączenie przekierowuje niezalogowanych użytkowników na stronę logowania, a następnie z powrotem na stronę CMS po pomyślnym zalogowaniu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Włączyłem ograniczenie dla strony CMS, ale niezalogowani użytkownicy nadal ją widzą. Co jest nie tak?**
O:

1.  **Wyczyść pamięć podręczną:** Najczęstszą przyczyną jest buforowanie. Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Pamięć podręczna przeglądarki również może wymagać wyczyszczenia.
2.  **Zapisz konfigurację:** Upewnij się, że kliknąłeś przycisk „Zapisz” na stronie konfiguracji modułu po włączeniu ograniczenia dla konkretnej strony CMS.
3.  **Sprawdź adres URL strony CMS:** Sprawdź dokładnie, czy testujesz prawidłowy adres URL dla strony CMS, którą ograniczyłeś.

**P: Po zalogowaniu klient jest przekierowywany na stronę główną zamiast na ograniczoną stronę CMS. Dlaczego?**
O: Ten moduł jest zaprojektowany tak, aby przekierować klienta z powrotem do oryginalnej ograniczonej strony CMS po pomyślnym zalogowaniu. Jeśli tak się nie dzieje, może to być spowodowane:

1.  **Niestandardowe przekierowania logowania:** Inny moduł lub niestandardowa modyfikacja motywu może nadpisywać domyślne zachowanie przekierowania logowania PrestaShop. Tymczasowo wyłącz inne moduły, które wpływają na logowanie/przekierowanie, aby przetestować.
2.  **Specyfika wersji PrestaShop:** Chociaż moduł jest kompatybilny z wieloma wersjami, bardzo specyficzne nadpisania motywu lub rdzenia w starszych/nowszych wersjach PrestaShop mogą zakłócać działanie. Upewnij się, że Twoje pliki rdzenia PrestaShop są standardowe.

**P: Czy mogę ograniczyć kategorie lub produkty zamiast stron CMS?**
O: Nie, ten moduł jest specjalnie zaprojektowany tylko dla stron CMS. Nie zapewnia funkcjonalności do ograniczania kategorii, produktów ani innych typów treści. Do tych celów potrzebowałbyś innego modułu.

**P: Czy ten moduł wpływa na SEO?**
O: Gdy strona jest ograniczona, roboty wyszukiwarek (takie jak Googlebot) będą zazwyczaj przekierowywane na stronę logowania, tak jak użytkownik. Oznacza to, że zawartość ograniczonej strony CMS nie będzie indeksowana przez wyszukiwarki. Jeśli treść ma być publiczna i indeksowana, nie ograniczaj jej za pomocą tego modułu. W przypadku treści, które powinny być ukryte przed wyszukiwarkami, ale nadal dostępne dla zalogowanych użytkowników, takie zachowanie jest pożądane.

**P: Jak przetłumaczyć tekst modułu (jeśli taki istnieje)?**
O: Ten moduł ma bardzo mało tekstu w front-office, ponieważ głównie obsługuje przekierowania. Wszelkie komunikaty związane z logowaniem są obsługiwane przez podstawową stronę uwierzytelniania PrestaShop. Gdyby istniały jakiekolwiek teksty specyficzne dla modułu, przetłumaczyłbyś je za pomocą **Lokalizacja > Tłumaczenia** w Panelu administracyjnym. Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie znajdź „Strony CMS tylko dla zalogowanych” na liście.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Strony CMS tylko dla zalogowanych” (`privatecms`) działa głównie poprzez nadpisywanie podstawowego `CmsController` w celu przechwytywania żądań stron CMS. Sprawdza, czy żądana strona CMS jest skonfigurowana do dostępu „tylko dla zalogowanych”, a jeśli użytkownik nie jest zalogowany, wyzwala przekierowanie na stronę uwierzytelniania. Po pomyślnym zalogowaniu, domyślny mechanizm przekierowania PrestaShop (który moduł wykorzystuje) odsyła użytkownika z powrotem do pierwotnie żądanej strony. Konfiguracja jest zarządzana za pomocą standardowej metody `getContent()` w głównym pliku modułu, przechowując ustawienia w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:

  - `override/controllers/front/CmsController.php`
    - **Nazwa klasy:** `CmsController` (nadpisuje podstawowy `CmsController` PrestaShop)
    - **Klasa nadrzędna:** `CmsControllerCore`
    - **Odpowiedzialność:** To nadpisanie jest rdzeniem funkcjonalności modułu. Przechwytuje metodę `init()` `CmsController`. Zanim strona CMS zostanie wyrenderowana, sprawdza, czy bieżący identyfikator strony CMS (`$this->cms->id`) znajduje się na liście ograniczonych stron przechowywanych w konfiguracji modułu. Jeśli strona jest ograniczona, a klient nie jest zalogowany (`$this->context->customer->isLogged()`), przekierowuje użytkownika na stronę uwierzytelniania (`$this->context->link->getPageLink('authentication')`). Zawiera również parametr `back` w adresie URL przekierowania, zapewniając, że PrestaShop przekieruje użytkownika z powrotem do oryginalnej strony CMS po pomyślnym zalogowaniu.
- **Kontrolery administracyjne Back-Office**: Brak. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównego modułu.

### 4.3 Klasy rdzenia i modele (`classes/`)

Brak. Moduł nie definiuje żadnych niestandardowych klas ani encji `ObjectModel`. Bezpośrednio współdziała z istniejącymi klasami rdzenia PrestaShop, takimi jak `Configuration`, `Cms`, `Customer` i `Link`.

### 4.4 Zasoby JavaScript (`views/js/`)

Brak. Moduł nie zawiera żadnych niestandardowych plików JavaScript. Jego funkcjonalność jest czysto po stronie serwera (przekierowanie oparte na PHP).

### 4.5 Arkusze stylów CSS (`views/css/`)

- `privatecms/css.css`
  - **Zakres:** Stylizacja formularza administracyjnego Back-Office.
  - **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Ten arkusz stylów prawdopodobnie zawiera minimalną stylizację formularza konfiguracji modułu w Panelu administracyjnym PrestaShop, zapewniając prawidłowe i spójne wyświetlanie układu i elementów (takich jak lista stron CMS i przełączniki) z motywem administracyjnym PrestaShop.
  - **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Konkretne selektory znajdowałyby się w pliku, zazwyczaj celując w elementy w szablonie `admin.tpl`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony administracyjne (`views/templates/admin/`)**:
  - `privatecms/admin.tpl`
    - **Cel:** Ten szablon jest renderowany przez metodę `getContent()` głównego pliku modułu (`privatecms.php`). Wyświetla listę wszystkich dostępnych stron CMS w Panelu administracyjnym, wraz z przełącznikiem dla każdej strony, umożliwiając administratorowi włączenie lub wyłączenie ograniczenia „tylko dla zalogowanych”. Iteruje przez strony CMS i wyświetla ich tytuły oraz bieżący status ograniczenia (zaznaczone/niezaznaczone).

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Konfiguracja jest przechowywana w tabeli `ps_configuration` (lub z prefiksem `_configuration`).
    - **Klucz:** `cmsp`
    - **Wartość:** Zserializowana tablica (lub ciąg JSON, w zależności od wersji PrestaShop i implementacji modułu) zawierająca identyfikatory stron CMS, które są wybrane do dostępu „tylko dla zalogowanych”.
- **Tabela zarejestrowanych hooków**:
  Moduł nie rejestruje jawnie żadnych standardowych hooków PrestaShop w swojej metodzie `install()`. Jego podstawowa funkcjonalność opiera się na nadpisywaniu `CmsController`, co jest bardziej bezpośrednim sposobem przechwytywania żądań stron CMS.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `override/controllers/front/CmsController.php` | Podczas inicjalizacji `CmsController` | Przechwytuje żądania stron CMS w celu sprawdzenia statusu zalogowania i przekierowania w razie potrzeby. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Strony CMS tylko dla zalogowanych”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
