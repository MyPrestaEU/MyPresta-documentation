---
title: "Zmiana numeru bonu towarowego - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Zmiana numeru bonu towarowego” od MyPresta.eu."
sidebar:
  label: "Zmiana numeru bonu towarowego - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Credit slip number change na MyPresta.eu](https://mypresta.eu/modules/administration-tools/credit-slip-number-change.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/credit-slip-number-change/)
>
> ---


# Zmiana numeru bonu towarowego

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Ten moduł ma bardzo prostą stronę konfiguracji, głównie do wewnętrznych aktualizacji MyPresta.eu. Podstawowa funkcjonalność zmiany numerów bonów towarowych jest dostępna bezpośrednio ze strony szczegółów zamówienia.

- **Lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > Wyszukaj „Zmiana numeru bonu towarowego” > Kliknij „Konfiguruj”.

| Ustawienie / Opcja | Do czego służy to ustawienie | Efekt zmiany tego ustawienia | Zalecana wartość | Scenariusz / przykład sprzedawcy |
| --- | --- | --- | --- | --- |
| **Aktualizacje MyPresta.eu** | To ustawienie kontroluje, czy moduł sprawdza dostępność aktualizacji z MyPresta.eu. | *Gdy włączone:* Moduł będzie okresowo sprawdzał dostępność nowych wersji i powiadamiał Cię w panelu administracyjnym. *Gdy wyłączone:* Moduł nie będzie automatycznie sprawdzał dostępności aktualizacji. | TAK | Włączenie tej opcji zapewnia, że zawsze będziesz świadomy nowych wersji, poprawek błędów i ulepszeń funkcji modułu. |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Główna funkcjonalność tego modułu jest zintegrowana bezpośrednio ze **stroną szczegółów zamówienia** w panelu administracyjnym PrestaShop. Nie ma oddzielnych dedykowanych ekranów administracyjnych.

- **Nazwa ekranu i lokalizacja menu:** Panel administracyjny > Zamówienia > Zamówienia > Kliknij dowolne zamówienie, aby wyświetlić jego szczegóły.
- **Dostępne działania i ustawienia:**
  - Na stronie szczegółów zamówienia przewiń w dół do sekcji „Bony towarowe”.
  - Dla każdego wymienionego bonu towarowego zobaczysz nowe pole wprowadzania obok jego bieżącego numeru.
  - Możesz wpisać nowy numer w tym polu.
  - Po wprowadzeniu nowego numeru kliknij przycisk „Zapisz” (lub podobną ikonę, zazwyczaj dyskietkę lub znacznik wyboru) obok pola wprowadzania, aby zastosować zmianę.
- **Efekt zmian:**
  - Po zmianie numeru bonu towarowego i jego zapisaniu, nowy numer jest natychmiast aktualizowany w Twojej bazie danych PrestaShop.
  - Ten nowy numer zostanie następnie odzwierciedlony w pliku PDF bonu towarowego wygenerowanym dla tego konkretnego bonu. Zarówno Ty, jak i Twój klient zobaczycie zaktualizowany numer na dokumencie.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. Przejdź do **Zamówienia > Zamówienia** w panelu administracyjnym PrestaShop.
  2. Wybierz zamówienie, dla którego musisz zmodyfikować numer bonu towarowego.
  3. Na stronie szczegółów zamówienia znajdź blok „Bony towarowe”.
  4. Znajdź konkretny bon towarowy, który chcesz zmienić.
  5. Wprowadź żądany nowy numer w udostępnionym polu wprowadzania.
  6. Kliknij ikonę zapisu obok pola wprowadzania.
  7. Zweryfikuj zmianę, pobierając plik PDF bonu towarowego; powinien teraz wyświetlać nowy numer.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Aktualizacje MyPresta.eu | TAK | Kontroluje automatyczne sprawdzanie aktualizacji modułu. |
| Strona szczegółów zamówienia (sekcja Bony towarowe) | Pole wprowadzania numeru bonu towarowego | N/A (definiowane przez użytkownika) | Umożliwia bezpośrednią modyfikację indywidualnych numerów bonów towarowych. Zmiany odzwierciedlone w pliku PDF. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zmieniłem numer bonu towarowego, ale nie pojawia się on w pliku PDF.**
O: Po zmianie numeru upewnij się, że kliknąłeś przycisk „Zapisz” obok pola wprowadzania. Następnie wygeneruj ponownie lub pobierz ponownie plik PDF bonu towarowego. Jeśli nadal się nie wyświetla, spróbuj wyczyścić pamięć podręczną przeglądarki lub pamięć podręczną Smarty PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).

**P: Czy mogę zmienić numer już zatwierdzonego lub wysłanego bonu towarowego?**
O: Tak, moduł pozwala na zmianę numeru dowolnego istniejącego bonu towarowego. Zmiana wpłynie tylko na numer wyświetlany w pliku PDF, a nie na samą transakcję finansową.

**P: Czy istnieje sposób na masową edycję numerów bonów towarowych?**
O: Nie, ten moduł jest przeznaczony do indywidualnych zmian numerów bonów towarowych bezpośrednio na stronie szczegółów zamówienia. Nie oferuje funkcji masowej edycji. W przypadku operacji masowych może być wymagane niestandardowe opracowanie.

**P: Co się stanie, jeśli wprowadzę zduplikowany numer bonu towarowego?**
O: Podstawowy system PrestaShop może nie zapobiegać duplikowaniu numerów bonów towarowych, ponieważ moduł bezpośrednio aktualizuje numer. Twoim obowiązkiem jest zapewnienie unikalności, jeśli wymagają tego Twoje praktyki księgowe. Moduł ułatwia zmianę, ale nie wymusza ograniczeń unikalności poza domyślnym zachowaniem PrestaShop.

**P: Pole wprowadzania do zmiany numeru nie pojawia się na mojej stronie zamówienia.**
O:

1. **Sprawdź instalację modułu:** Upewnij się, że moduł jest poprawnie zainstalowany i włączony w **Moduły > Menedżer modułów**.
2. **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.
3. **Kompatybilność z motywem:** Chociaż moduł używa standardowych hooków PrestaShop, bardzo mocno dostosowane motywy mogą czasami zakłócać jego działanie. Jeśli problem nadal występuje, tymczasowo przełącz się na domyślny motyw PrestaShop, aby sprawdzić, czy pole się pojawi. Jeśli tak, Twój motyw może wymagać niewielkiej korekty.
4. **Wersja PrestaShop:** Upewnij się, że pobrałeś poprawną wersję modułu dla swojej instalacji PrestaShop.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Zmiana numeru bonu towarowego” (`creditnb`) to lekki moduł PrestaShop, który rozszerza funkcjonalność panelu administracyjnego poprzez wstrzyknięcie niestandardowego pola wprowadzania do hooka `displayAdminOrder`. Pozwala to administratorom modyfikować numery bonów towarowych bezpośrednio na stronie szczegółów zamówienia. Moduł głównie współdziała z obiektem `OrderSlip` PrestaShop i powiązaną z nim tabelą bazy danych w celu aktualizacji pola `number`. Wykorzystuje standardową strukturę modułu PrestaShop i szablony.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Wszystkie interakcje są obsługiwane za pośrednictwem głównego pliku modułu (`creditnb.php`) i standardowych mechanizmów AJAX PrestaShop do przesyłania formularzy na stronie zamówienia administratora.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas ani modeli w katalogu `classes/`. Bezpośrednio współdziała z natywnym obiektem `OrderSlip` PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Funkcjonalność zapisywania nowego numeru bonu towarowego jest obsługiwana przez przesyłanie formularza w szablonie hooka `displayAdminOrder`, prawdopodobnie wykorzystując istniejące mechanizmy AJAX lub obsługę formularzy PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Stylizacja pola wprowadzania ma dziedziczyć z motywu panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa szablonów hooków do wstrzykiwania swojej funkcjonalności do panelu administracyjnego PrestaShop.

- **Szablony hooków (`views/templates/hook/`)**:
  - `creditnb/views/templates/hook/displayAdminOrder16.tpl`
    - **Cel:** Ten szablon jest przeznaczony dla PrestaShop 1.6.x (chociaż moduł wymienia kompatybilność z 1.7.x, 8.x, 9.x, ten plik może być dziedzicznym elementem lub dla szerszej kompatybilności). Renderuje pole wprowadzania i przycisk zapisu do zmiany numerów bonów towarowych w sekcji „Bony towarowe” na stronie szczegółów zamówienia.
    - **Hook:** `displayAdminOrder`
    - **Wynik:** Blok HTML zawierający element formularza z polem wprowadzania dla numeru każdego bonu towarowego i mechanizmem do zapisywania zaktualizowanej wartości.
  - `creditnb/views/templates/hook/displayAdminOrder17.tpl`
    - **Cel:** Ten szablon jest przeznaczony dla PrestaShop 1.7.x, 8.x i 9.x. Renderuje pole wprowadzania i przycisk zapisu do zmiany numerów bonów towarowych w sekcji „Bony towarowe” na stronie szczegółów zamówienia, dostosowany do nowszego interfejsu użytkownika panelu administracyjnego.
    - **Hook:** `displayAdminOrder`
    - **Wynik:** Blok HTML zawierający element formularza z polem wprowadzania dla numeru każdego bonu towarowego i mechanizmem do zapisywania zaktualizowanej wartości.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy żadnych nowych niestandardowych tabel bazy danych.
  - Modyfikuje kolumnę `number` w tabeli `ps_order_slip` (lub `_order_slip`), która jest częścią podstawowego schematu bazy danych PrestaShop.
  - Ustawienia konfiguracji (`mypresta_updates`, `update_`, `updatev_`) są przechowywane w tabeli `ps_configuration`.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayAdminOrder` | Renderuje zawartość na stronie szczegółów zamówienia w panelu administracyjnym PrestaShop. | Wstrzykuje niestandardowe pole wprowadzania i mechanizm zapisu do modyfikacji numerów bonów towarowych bezpośrednio do sekcji „Bony towarowe” w widoku zamówienia. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Zmiana numeru bonu towarowego”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie płynnego działania i ciągłego ulepszania naszych modułów.
