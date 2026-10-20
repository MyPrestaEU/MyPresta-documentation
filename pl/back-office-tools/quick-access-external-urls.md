---
title: "Szybki dostęp - zewnętrzne adresy URL - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Szybki dostęp - zewnętrzne adresy URL” od MyPresta.eu."
sidebar:
  label: "Szybki dostęp - zewnętrzne adresy URL - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Quick Access - external urls na MyPresta.eu](https://mypresta.eu/modules/administration-tools/quick-access-external-urls.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/quick-access-external-urls/)
>
> ---


# Szybki dostęp - zewnętrzne adresy URL

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

Ten moduł integruje się bezpośrednio z istniejącym systemem zarządzania Szybkim dostępem w PrestaShop. Nie ma oddzielnego ekranu konfiguracji dla samego modułu. Zamiast tego, modyfikuje on zachowanie domyślnej funkcji „Szybki dostęp” w Twoim Panelu administracyjnym.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po kliknięciu „Konfiguruj” dla modułu „Szybki dostęp - zewnętrzne adresy URL”, zazwyczaj zobaczysz proste potwierdzenie, że moduł jest zainstalowany i aktywny. Na tej stronie nie ma żadnych konkretnych ustawień do dostosowania, ponieważ moduł działa poprzez nadpisywanie podstawowego zachowania PrestaShop.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Funkcjonalność modułu jest zarządzana za pośrednictwem standardowego menu Szybkiego dostępu PrestaShop.

**Nazwa ekranu i lokalizacja w menu:**

- **Panel administracyjny > Administracja > Szybki dostęp** (lub **Konfiguruj > Zaawansowane > Szybki dostęp** w starszych wersjach PrestaShop 1.7.x).
- Możesz również uzyskać do niego dostęp bezpośrednio z samego menu Szybkiego dostępu (mała ikona zegara na górze Panelu administracyjnego), klikając „Zarządzaj szybkim dostępem”.

**Dostępne akcje i ustawienia:**
Na tym ekranie zobaczysz listę istniejących linków Szybkiego dostępu.

- **Dodawanie nowego linku Szybkiego dostępu:**

  1.  Kliknij przycisk **„Dodaj nowy szybki dostęp”** (lub podobny, zazwyczaj ikona plusa).
  2.  Zobaczysz formularz z polami takimi jak:
      -   **Nazwa:** Tekst, który pojawi się w menu Szybkiego dostępu (np. „Portal wysyłkowy DHL”, „Panel Stripe”, „Google Analytics”).
      -   **URL:** To jest kluczowe pole. **Po zainstalowaniu tego modułu możesz teraz wprowadzić DOWOLNY prawidłowy adres URL, w tym zewnętrzne strony internetowe.** Na przykład:
          -   `https://www.dhl.com/global-en/home/tracking.html`
          -   `https://dashboard.stripe.com/`
          -   `https://analytics.google.com/`
          -   `https://mypresta.eu/`
      -   **Otwórz w nowym oknie:** (Zalecane: TAK) Ta opcja określa, czy link otwiera się w nowej karcie/oknie przeglądarki.
          -   *Gdy włączone:* Zewnętrzny link otworzy się w nowej karcie, pozostawiając Panel administracyjny PrestaShop otwarty w bieżącej karcie. Jest to ogólnie zalecane dla linków zewnętrznych, aby uniknąć opuszczania panelu administracyjnego.
          -   *Gdy wyłączone:* Link otworzy się w tej samej karcie, zastępując widok Panelu administracyjnego PrestaShop.
  3.  Kliknij **„Zapisz”**.
- **Edytowanie istniejącego linku Szybkiego dostępu:**

  1.  Znajdź link na liście i kliknij ikonę „Edytuj” (ołówek).
  2.  Zmodyfikuj nazwę lub adres URL według potrzeb.
  3.  Kliknij „Zapisz”.
- **Usuwanie linku Szybkiego dostępu:**

  1.  Znajdź link na liście i kliknij ikonę „Usuń” (kosz).
  2.  Potwierdź usunięcie.

**Efekt zmian:**

- Wszelkie linki Szybkiego dostępu, które dodasz, edytujesz lub usuniesz na tym ekranie, natychmiast odzwierciedlą się w menu Szybkiego dostępu (ikona zegara) na górze Panelu administracyjnego PrestaShop.
- Po kliknięciu linku Szybkiego dostępu, który wskazuje na zewnętrzny adres URL, Twoja przeglądarka przejdzie do tej zewnętrznej witryny (albo w tej samej karcie, albo w nowej, w zależności od ustawienia „Otwórz w nowym oknie”).

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

1.  **Zidentyfikuj często używane narzędzia zewnętrzne:** Pomyśl o stronach internetowych, które odwiedzasz codziennie lub co tydzień, aby zarządzać swoim sklepem (np. wysyłka, płatności, marketing, wsparcie, portale dostawców).
2.  **Dodaj je do Szybkiego dostępu:** Przejdź do **Administracja > Szybki dostęp** i dodaj każdy zewnętrzny adres URL z jasną, opisową nazwą.
3.  **Włącz „Otwórz w nowym oknie”:** Dla wszystkich linków zewnętrznych ustaw „Otwórz w nowym oknie” na TAK. Zapewni to, że Twój Panel administracyjny PrestaShop pozostanie otwarty i dostępny.
4.  **Zorganizuj dla swojego zespołu:** Jeśli masz wielu użytkowników administracyjnych, rozważ, które szybkie linki byłyby najbardziej korzystne dla każdej roli.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Panel administracyjny > Administracja > Szybki dostęp** | **Nazwa** | Zdefiniowane przez użytkownika | Tekst wyświetlany w menu Szybkiego dostępu. |
|  | **URL** | Zdefiniowane przez użytkownika (Zewnętrzny URL) | Adres internetowy, na który wskazuje link. **Ten moduł umożliwia tutaj zewnętrzne adresy URL.** |
|  | **Otwórz w nowym oknie** | TAK (dla linków zewnętrznych) | Określa, czy link otwiera się w nowej karcie/oknie przeglądarki. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Zainstalowałem moduł, ale nadal nie mogę dodawać zewnętrznych adresów URL do Szybkiego dostępu. Co jest nie tak?**
O1:

-   **Wyczyść pamięć podręczną:** Po instalacji zawsze wyczyść pamięć podręczną PrestaShop. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
-   **Sprawdź status modułu:** Upewnij się, że moduł jest włączony. Przejdź do **Moduły > Menedżer modułów**, wyszukaj „Szybki dostęp - zewnętrzne adresy URL” i sprawdź, czy jest aktywny.
-   **Zweryfikuj instalację:** Czasami instalacja może zakończyć się niepowodzeniem bez powiadomienia. Spróbuj odinstalować i ponownie zainstalować moduł.
-   **Pamięć podręczna przeglądarki:** Wyczyść pamięć podręczną i pliki cookie przeglądarki lub spróbuj uzyskać dostęp do Panelu administracyjnego w oknie incognito/prywatnym.

**P2: Moje linki Szybkiego dostępu otwierają się w tej samej karcie, nawet dla stron zewnętrznych. Jak to naprawić?**
O2:

-   Podczas dodawania lub edytowania linku Szybkiego dostępu upewnij się, że opcja **„Otwórz w nowym oknie”** jest ustawiona na **TAK**. To ustawienie kontroluje, czy link otwiera się w nowej karcie, czy w bieżącej.

**P3: Czy ten moduł wpłynie na wydajność mojego sklepu lub SEO?**
O3:

-   Nie. Ten moduł działa całkowicie w Panelu administracyjnym PrestaShop. Nie dodaje żadnego kodu, stylów ani funkcjonalności do front-office Twojego sklepu (tego, co widzą klienci). Dlatego nie ma wpływu na szybkość ładowania Twojego sklepu, SEO ani doświadczenie klienta.

**P4: Dodałem wiele linków Szybkiego dostępu. Czy mogę je uporządkować?**
O4:

-   Domyślna funkcja Szybkiego dostępu PrestaShop nie oferuje zaawansowanej organizacji, takiej jak foldery czy kategorie. Możesz jednak kontrolować kolejność linków, przeciągając je i upuszczając na stronie **Administracja > Szybki dostęp**. Możesz również używać opisowych nazw, aby ułatwić ich identyfikację.

**P5: Co się stanie, jeśli odinstaluję ten moduł? Czy moje zewnętrzne linki Szybkiego dostępu znikną?**
O5:

-   Jeśli odinstalujesz ten moduł, możliwość dodawania *nowych* zewnętrznych adresów URL zostanie usunięta. Istniejące zewnętrzne adresy URL, które dodałeś, gdy moduł był aktywny, *mogą* nadal działać, ale podstawowa walidacja PrestaShop może uniemożliwić ich edycję lub spowodować problemy. Najlepiej jest pozostawić moduł zainstalowany, jeśli polegasz na zewnętrznych linkach Szybkiego dostępu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Szybki dostęp - zewnętrzne adresy URL” (`qae`) osiąga swoją funkcjonalność poprzez nadpisywanie podstawowych klas i kontrolerów PrestaShop. W szczególności, celuje w `ObjectModel` `QuickAccess` i `AdminQuickAccessesController`, aby usunąć walidację, która ogranicza adresy URL Szybkiego dostępu do wewnętrznych ścieżek Panelu administracyjnego. Jest to powszechny wzorzec nadpisywania w PrestaShop.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Ten moduł nie zawiera żadnych kontrolerów front-office, ponieważ jego funkcjonalność jest przeznaczona wyłącznie dla Panelu administracyjnego.
-   **Kontrolery administracyjne Back-Office**:

    -   **`qae/override/controllers/admin/AdminQuickAccessesController.php`**
        -   **Nazwa klasy**: `AdminQuickAccessesController` (nadpisuje podstawowy `AdminQuickAccessesController`)
        -   **Klasa nadrzędna**: `AdminController`
        -   **Odpowiedzialność**: To nadpisanie jest kluczowe. Oryginalny `AdminQuickAccessesController` zawiera logikę walidacji pola `url` wpisu Szybkiego dostępu, zapewniając, że jest to wewnętrzna ścieżka Panelu administracyjnego PrestaShop. To nadpisanie modyfikuje lub usuwa tę walidację, umożliwiając zapisywanie zewnętrznych adresów URL. Programiści powinni zbadać metody `postProcess()` lub `renderForm()` pod kątem konkretnych zmian związanych z walidacją URL.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   **`qae/override/classes/index.php`**

    -   Jest to zazwyczaj pusty plik lub plik zawierający tylko `<?php exit; ?>`, aby zapobiec bezpośredniemu listowaniu katalogów. Jest to środek bezpieczeństwa i nie jest częścią podstawowej logiki modułu.
-   **`qae/override/classes/Link.php`**

    -   **Nazwa klasy**: `Link` (nadpisuje podstawową klasę `Link`)
    -   **Klasa nadrzędna**: `LinkCore`
    -   **Odpowiedzialność**: Klasa `Link` jest odpowiedzialna za generowanie adresów URL w PrestaShop. Chociaż główna zmiana dla zewnętrznych adresów URL znajduje się w `QuickAccess` i `AdminQuickAccessesController`, nadpisanie `Link` może być obecne, aby zapewnić, że wszelkie wewnętrzne metody generowania lub walidacji URL, na których polega `QuickAccess`, są kompatybilne z nowym zezwoleniem na zewnętrzne adresy URL, lub aby zapobiec niezamierzonym skutkom ubocznym. Programiści powinni szukać modyfikacji w metodach związanych z walidacją lub sanitacją URL.
-   **`qae/override/classes/QuickAccess.php`**

    -   **Nazwa klasy**: `QuickAccess` (nadpisuje podstawowy `ObjectModel` `QuickAccess`)
    -   **Klasa nadrzędna**: `ObjectModel`
    -   **Tabela bazy danych**: `ps_quick_access`
    -   Pola `$definition`: Ta klasa definiuje strukturę wpisu Szybkiego dostępu, w tym `id_quick_access`, `name`, `url` i `new_window`.
    -   **Kluczowe metody publiczne i logika biznesowa**: To nadpisanie jest fundamentalne. Oryginalny `ObjectModel` `QuickAccess` prawdopodobnie zawiera reguły walidacji dla pola `url` w swoich metodach `validateFields()` lub `add()`/`update()`. To nadpisanie usuwa lub rozluźnia te reguły walidacji, umożliwiając polu `url` przechowywanie dowolnego ciągu znaków, w tym zewnętrznych adresów URL, bez wywoływania błędów walidacji.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Zmiany są czysto po stronie serwera (nadpisania PHP).

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Wizualna prezentacja menu Szybkiego dostępu jest obsługiwana przez domyślny motyw Panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie zawiera żadnych niestandardowych plików szablonów Smarty. Wykorzystuje istniejące szablony Panelu administracyjnego PrestaShop do renderowania strony zarządzania Szybkim dostępem i samego menu Szybkiego dostępu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Ten moduł nie tworzy żadnych nowych tabel bazy danych. Modyfikuje zachowanie sposobu przechowywania i walidacji danych dla istniejącej tabeli `ps_quick_access`.
    -   Rekordy konfiguracji nie są przechowywane w `ps_configuration` przez ten moduł, ponieważ opiera się on głównie na nadpisywaniu klas/kontrolerów.
-   **Tabela zarejestrowanych hooków**:
    Ten moduł nie rejestruje żadnych konkretnych hooków w tradycyjnym sensie (np. `displayHeader`, `actionValidateOrder`). Jego funkcjonalność jest implementowana poprzez system nadpisywania PrestaShop, który bezpośrednio modyfikuje podstawowe klasy i kontrolery, zamiast wstrzykiwać kod za pośrednictwem hooków.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Szybki dostęp - zewnętrzne adresy URL”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań.
