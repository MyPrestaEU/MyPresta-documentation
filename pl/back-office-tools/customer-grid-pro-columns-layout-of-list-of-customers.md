---
title: "Customer Grid Pro - kolumny i układ listy klientów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla programistów modułu PrestaShop Customer Grid Pro - kolumny i układ listy klientów od MyPresta.eu."
sidebar:
  label: "Customer Grid Pro - kolumny i układ listy klientów"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Customer Grid Pro - columns & layout of list of customers na MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-grid-pro-columns-layout-of-list-of-customers.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/customer-grid-pro-columns-layout-of-list-of-customers/)
>
> ---


# Customer Grid Pro - kolumny i układ listy klientów

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 9.x, 8.x, 1.7.8.x, 1.7.7.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Po zainstalowaniu modułu kliknij „Konfiguruj”, aby uzyskać dostęp do jego ustawień. Ta strona pozwala wybrać, które kolumny pojawią się na liście klientów i w jakiej kolejności.

Strona konfiguracji wyświetli listę wszystkich dostępnych kolumn dla Twojej siatki klientów. Obejmuje to standardowe kolumny PrestaShop i nowe dodane przez moduł (takie jak telefon, adres, statystyki zamówień).

**Jak korzystać z interfejsu konfiguracji:**

1.  **Lista dostępnych kolumn:** Po lewej stronie zobaczysz listę wszystkich kolumn, które *mogą* być wyświetlone.
2.  **Lista aktywnych kolumn:** Po prawej stronie zobaczysz listę kolumn, które są obecnie *aktywne* i będą wyświetlane na liście klientów.
3.  **Dodawanie kolumny:** Aby dodać kolumnę do listy klientów, po prostu przeciągnij ją z listy „Dostępne kolumny” po lewej stronie i upuść na listę „Aktywne kolumny” po prawej stronie.
4.  **Usuwanie kolumny:** Aby usunąć kolumnę z listy klientów, przeciągnij ją z listy „Aktywne kolumny” po prawej stronie i upuść z powrotem na listę „Dostępne kolumny” po lewej stronie.
5.  **Zmienianie kolejności kolumn:** W ramach listy „Aktywne kolumny” możesz przeciągać i upuszczać kolumny w górę lub w dół, aby zmienić ich kolejność wyświetlania w siatce klientów. Kolumna na górze listy pojawi się jako pierwsza (najbardziej po lewej) na liście klientów.
6.  **Przycisk Zapisz:** Po wprowadzeniu jakichkolwiek zmian (dodawanie, usuwanie lub zmienianie kolejności kolumn), pamiętaj, aby kliknąć przycisk **„Zapisz”** na dole strony, aby zastosować nową konfigurację.

**Lista dostępnych kolumn i ich przeznaczenie:**

| Nazwa kolumny (Przykład) | Co robi to ustawienie | Efekt zmiany tego ustawienia | Zalecana wartość | Scenariusz / przykład dla sprzedawcy |
|---|---|---|---|---|
| **ID** | Wyświetla unikalny numer identyfikacyjny dla każdego klienta. | *Gdy aktywne:* Pokazuje ID klienta. *Gdy nieaktywne:* Ukrywa kolumnę ID. | Aktywne | Przydatne do szybkiego odwoływania się do klientów za pomocą ich wewnętrznego ID, zwłaszcza podczas obsługi zgłoszeń. |
| **Tytuł społeczny** | Wyświetla wybrany tytuł klienta (np. Pan, Pani). | *Gdy aktywne:* Pokazuje tytuł społeczny. *Gdy nieaktywne:* Ukrywa kolumnę tytułu społecznego. | Aktywne (opcjonalnie) | Dobre do formalnej komunikacji lub jeśli Twoja firma wymaga konkretnych zwrotów grzecznościowych. |
| **Imię** | Wyświetla imię klienta. | *Gdy aktywne:* Pokazuje imię. *Gdy nieaktywne:* Ukrywa kolumnę imienia. | Aktywne | Niezbędne do identyfikacji klientów. |
| **Nazwisko** | Wyświetla nazwisko klienta. | *Gdy aktywne:* Pokazuje nazwisko. *Gdy nieaktywne:* Ukrywa kolumnę nazwiska. | Aktywne | Niezbędne do identyfikacji klientów. |
| **Adres e-mail** | Wyświetla adres e-mail klienta. | *Gdy aktywne:* Pokazuje adres e-mail. *Gdy nieaktywne:* Ukrywa kolumnę e-mail. | Aktywne | Kluczowe do kontaktu z klientami i często używane jako główny identyfikator. |
| **Wiek** | Wyświetla wiek klienta (jeśli podano datę urodzenia). | *Gdy aktywne:* Pokazuje obliczony wiek klienta. *Gdy nieaktywne:* Ukrywa kolumnę wieku. | Aktywne (opcjonalnie) | Przydatne do segmentacji marketingowej lub produktów z ograniczeniem wieku. |
| **Data rejestracji** | Wyświetla datę rejestracji konta klienta. | *Gdy aktywne:* Pokazuje datę rejestracji. *Gdy nieaktywne:* Ukrywa kolumnę daty rejestracji. | Aktywne | Pomaga śledzić pozyskiwanie klientów i identyfikować nowych vs. starych klientów. |
| **Ostatnia wizyta** | Wyświetla datę ostatniego logowania/wizyty klienta. | *Gdy aktywne:* Pokazuje datę ostatniej wizyty. *Gdy nieaktywne:* Ukrywa kolumnę daty ostatniej wizyty. | Aktywne (opcjonalnie) | Przydatne do identyfikacji aktywnych vs. nieaktywnych klientów dla kampanii ponownego zaangażowania. |
| **Łączna liczba zamówień** | Wyświetla łączną liczbę zamówień złożonych przez klienta. | *Gdy aktywne:* Pokazuje liczbę wszystkich zamówień. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne | Doskonałe do identyfikacji częstych kupujących lub klientów z wieloma zakupami. |
| **Łączna kwota wydana** | Wyświetla łączną wartość pieniężną wydaną przez klienta we wszystkich zamówieniach. | *Gdy aktywne:* Pokazuje sumę wszystkich wartości zamówień. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne | Kluczowe do identyfikacji klientów o wysokiej wartości (VIP) i do zarządzania kontami B2B. |
| **Numer telefonu** | Wyświetla główny numer telefonu klienta (z jego domyślnego adresu). | *Gdy aktywne:* Pokazuje numer telefonu. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne | Niezbędne do bezpośredniego kontaktu, zwłaszcza w przypadku problemów z dostawą lub pilnych zapytań. |
| **Telefon komórkowy** | Wyświetla numer telefonu komórkowego klienta (z jego domyślnego adresu). | *Gdy aktywne:* Pokazuje numer telefonu komórkowego. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne | Zapewnia alternatywną metodę kontaktu, często preferowaną do szybkiej komunikacji. |
| **Adres 1** | Wyświetla pierwszą linię domyślnego adresu klienta. | *Gdy aktywne:* Pokazuje linię adresu. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne (opcjonalnie) | Przydatne do szybkiego odniesienia do lokalizacji bez otwierania pełnego adresu. |
| **Adres 2** | Wyświetla drugą linię domyślnego adresu klienta. | *Gdy aktywne:* Pokazuje linię adresu. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne (opcjonalnie) | Zapewnia dodatkowe szczegóły adresu. |
| **Kod pocztowy** | Wyświetla kod pocztowy domyślnego adresu klienta. | *Gdy aktywne:* Pokazuje kod pocztowy. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne (opcjonalnie) | Przydatne do segmentacji geograficznej lub planowania dostaw. |
| **Miasto** | Wyświetla miasto domyślnego adresu klienta. | *Gdy aktywne:* Pokazuje miasto. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne (opcjonalnie) | Przydatne do segmentacji geograficznej lub lokalnego marketingu. |
| **Województwo** | Wyświetla województwo/stan domyślnego adresu klienta. | *Gdy aktywne:* Pokazuje województwo/stan. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne (opcjonalnie) | Ważne dla targetowania regionalnego i wysyłki. |
| **Kraj** | Wyświetla kraj domyślnego adresu klienta. | *Gdy aktywne:* Pokazuje kraj. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne (opcjonalnie) | Niezbędne dla sklepów międzynarodowych i logistyki wysyłki. |
| **Newsletter** | Wskazuje, czy klient jest subskrybentem Twojego newslettera. | *Gdy aktywne:* Pokazuje wskaźnik „Tak” lub „Nie”. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne | Pomaga identyfikować możliwości marketingowe i zarządzać listami e-mail. |
| **Zgoda na oferty partnerów** | Wskazuje, czy klient wyraził zgodę na oferty partnerów. | *Gdy aktywne:* Pokazuje wskaźnik „Tak” lub „Nie”. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne (opcjonalnie) | Przydatne do zarządzania działaniami marketingowymi partnerów. |
| **Aktywne** | Wskazuje, czy konto klienta jest obecnie aktywne. | *Gdy aktywne:* Pokazuje wskaźnik „Tak” lub „Nie”. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne | Pomaga identyfikować wyłączone konta. |
| **Domyślna grupa** | Wyświetla podstawową grupę klientów. | *Gdy aktywne:* Pokazuje nazwę domyślnej grupy. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne | Kluczowe dla sklepów B2B lub sklepów z warstwowymi cenami/dostępem. |
| **Nazwa sklepu** | Wyświetla nazwę sklepu, jeśli używany jest tryb multi-store. | *Gdy aktywne:* Pokazuje nazwę sklepu. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne (jeśli multi-store) | Niezbędne w środowiskach multi-store do rozróżniania klientów według sklepu. |
| **Zaległa kwota** | Wyświetla wszelkie zaległe saldo, które klient jest winien (jeśli dotyczy, np. dla kredytu B2B). | *Gdy aktywne:* Pokazuje zaległą kwotę. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne (jeśli dotyczy) | Ważne dla zarządzania kredytami B2B. |
| **Dozwolone zamówienie wsteczne** | Wskazuje, czy klient może składać zamówienia wsteczne. | *Gdy aktywne:* Pokazuje „Tak” lub „Nie”. *Gdy nieaktywne:* Ukrywa tę kolumnę. | Aktywne (jeśli dotyczy) | Istotne dla zarządzania zapasami i specyficznych umów z klientami. |

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Strona konfiguracji modułu | Kolejność kolumn „przeciągnij i upuść” | Zdefiniowane przez użytkownika | Kontroluje wizualną kolejność kolumn na liście klientów w Panelu administracyjnym. |
| Strona konfiguracji modułu | Lista aktywnych kolumn | Zdefiniowane przez użytkownika | Określa, które kolumny są widoczne na liście klientów w Panelu administracyjnym. |
| Strona konfiguracji modułu | Lista dostępnych kolumn | Zdefiniowane przez użytkownika | Wyświetla wszystkie możliwe kolumny, które można dodać do listy klientów. |
| Strona konfiguracji modułu | Przycisk Zapisz | Kliknij po zmianach | Stosuje wszystkie zmiany widoczności i kolejności kolumn do siatki klientów. |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P: Skonfigurowałem kolumny, ale nie widzę żadnych zmian na liście klientów.**
O:
1.  **Czy kliknąłeś „Zapisz”?** Po wprowadzeniu zmian na stronie konfiguracji modułu musisz kliknąć przycisk „Zapisz”.
2.  **Wyczyść pamięć podręczną PrestaShop:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe pojawienie się zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
3.  **Sprawdź pamięć podręczną przeglądarki:** Spróbuj wyczyścić pamięć podręczną przeglądarki lub otworzyć Panel administracyjny w oknie incognito/prywatnym.

**P: Niektóre kolumny, których się spodziewam (takie jak „Nazwa firmy” lub „Zaległa kwota”), nie są dostępne na liście.**
O:
1.  **Kompatybilność modułu:** Upewnij się, że pobrałeś i zainstalowałeś poprawną wersję modułu dla Twojej konkretnej wersji PrestaShop.
2.  **Funkcje PrestaShop:** Niektóre kolumny (np. „Zaległa kwota”) są istotne tylko, jeśli masz włączone specyficzne funkcje PrestaShop (takie jak tryb B2B) lub zainstalowane inne moduły, które dostarczają te dane. Jeśli dane nie istnieją w Twoim sklepie, moduł może nie być w stanie ich wyświetlić.

**P: Funkcja „przeciągnij i upuść” nie działa na stronie konfiguracji.**
O:
1.  **Kompatybilność przeglądarki:** Upewnij się, że używasz nowoczesnej przeglądarki internetowej (Chrome, Firefox, Edge, Safari) i że JavaScript jest włączony.
2.  **Konfliktujące moduły:** Rzadko, inny moduł lub niestandardowa modyfikacja motywu może kolidować z JavaScriptem. Spróbuj tymczasowo wyłączyć inne moduły, aby sprawdzić, czy problem zostanie rozwiązany. Jeśli tak, skontaktuj się z pomocą techniczną MyPresta.eu.

**P: Czy mogę przetłumaczyć nowe nazwy kolumn na inne języki?**
O: Tak, system tłumaczeń PrestaShop powinien pozwolić na przetłumaczenie ciągów modułu.
1.  Przejdź do **Lokalizacja > Tłumaczenia**.
2.  Wybierz „Tłumaczenia zainstalowanych modułów”.
3.  Wybierz swój motyw, swój język, a następnie wybierz „Customer Grid Pro”.
4.  Powinieneś znaleźć tam ciągi dla nazw kolumn do przetłumaczenia.

**P: Czy ten moduł spowolni mój Panel administracyjny?**
O: Moduł jest zoptymalizowany do integracji z podstawową siatką klientów PrestaShop. Chociaż dodanie wielu złożonych kolumn (zwłaszcza tych wymagających obliczeń, takich jak „Łączna kwota wydana”) może nieznacznie zwiększyć czas ładowania w porównaniu do listy podstawowej, wpływ jest zazwyczaj znikomy na dobrze skonfigurowanym serwerze. Korzyści z efektywności zazwyczaj znacznie przewyższają wszelkie drobne różnice w wydajności.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury
Moduł `Customer Grid Pro` przede wszystkim rozszerza funkcjonalność listy klientów w Panelu administracyjnym PrestaShop. Osiąga to poprzez podłączenie się do hooków `actionCustomerGridDefinitionModifier` i `actionCustomerGridDataModifier`, które są częścią nowego systemu siatki PrestaShop wprowadzonego w wersji 1.7.x. Pozwala to modułowi dynamicznie dodawać, usuwać i zmieniać kolejność kolumn oraz powiązanych z nimi danych bez bezpośredniej modyfikacji plików rdzenia. Konfiguracja jest zarządzana za pomocą standardowej metody `getContent()` w głównym pliku modułu, wykorzystując niestandardowy JavaScript i CSS dla interfejsu „przeciągnij i upuść”.

### 4.2 Kontrolery (`controllers/`)
Ten moduł nie wprowadza żadnych niestandardowych kontrolerów Front-Office ani Back-Office. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy rdzenia i modele (`classes/`)
Ten moduł nie definiuje żadnych niestandardowych klas ani encji `ObjectModel` w katalogu `classes/`. Cała logika jest zawarta w głównym pliku modułu `index.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`mycustomergridpro/views/js/customer_grid_admin.js`**
    *   **Zakres:** Panel administracyjny (konkretnie strona konfiguracji modułu).
    *   **Cel:** Ten skrypt zapewnia funkcjonalność „przeciągnij i upuść” dla interfejsu wyboru kolumn na stronie konfiguracji modułu. Wykorzystuje widget `sortable` z jQuery UI, aby umożliwić zmianę kolejności i przenoszenie elementów między listami „Dostępne kolumny” i „Aktywne kolumny”.
    *   **Kluczowa funkcjonalność:**
        *   Inicjalizuje dwie listy sortowalne: `#available_columns` i `#active_columns`.
        *   Konfiguruje `connectWith`, aby umożliwić przenoszenie elementów między tymi dwoma listami.
        *   Obsługuje zdarzenie `update` dla list sortowalnych, aby potencjalnie wywołać zapisywanie lub aktualizację ukrytych pól wejściowych (chociaż faktyczne zapisywanie jest obsługiwane przez przesłanie formularza).
        *   Zapewnia, że kolejność elementów na liście `#active_columns` jest poprawnie przesyłana z formularzem.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`mycustomergridpro/views/css/customer_grid_admin.css`**
    *   **Zakres:** Panel administracyjny (konkretnie strona konfiguracji modułu).
    *   **Cel:** Zapewnia stylizację dla interfejsu wyboru kolumn „przeciągnij i upuść”.
    *   **Kluczowa stylizacja:**
        *   Style dla kontenerów list kolumn (`#available_columns`, `#active_columns`).
        *   Style dla poszczególnych elementów kolumn (`.column-item`).
        *   Wizualne wskazówki dla operacji „przeciągnij i upuść” (np. `ui-sortable-helper`, `ui-sortable-placeholder`).
        *   Zapewnia, że dwie listy kolumn są wyświetlane obok siebie lub w przejrzystym układzie dla użyteczności.

### 4.6 Struktura szablonów Smarty (`views/templates/`)
Ten moduł nie używa oddzielnych plików `.tpl` do swojej konfiguracji ani wyświetlania w front-office. Cały kod HTML formularza konfiguracji jest generowany bezpośrednio w metodzie `getContent()` głównego pliku modułu `index.php`.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
    *   Przechowuje swoją konfigurację (listę aktywnych kolumn i ich kolejność) w tabeli `ps_configuration` za pomocą kluczy takich jak `MYCUSTOMERGRIDPRO_ACTIVE_COLUMNS`. Ta konfiguracja jest przechowywana jako serializowana tablica lub ciąg JSON.

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `actionCustomerGridDefinitionModifier` | Wykonywany podczas budowania definicji siatki klientów w Panelu administracyjnym. | Pozwala modułowi dodawać nowe kolumny (np. telefon, łączna liczba zamówień, łączna kwota wydana, pola adresowe) i usuwać istniejące z definicji siatki. Ten hook otrzymuje obiekt `GridDefinition`. |
| `actionCustomerGridDataModifier` | Wykonywany po pobraniu danych siatki klientów, ale przed ich renderowaniem. | Pozwala modułowi wypełniać dane dla niestandardowych kolumn dodanych za pomocą `actionCustomerGridDefinitionModifier`. Ten hook otrzymuje obiekt `QueryResult`, umożliwiając modyfikację wierszy danych. |
| `displayBackOfficeHeader` | Wykonywany w sekcji `<head>` stron Panelu administracyjnego. | Używany do dołączania niestandardowych plików CSS (`customer_grid_admin.css`) i JavaScript (`customer_grid_admin.js`) modułu na stronie konfiguracji modułu, umożliwiając interfejs „przeciągnij i upuść”. |

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Customer Grid Pro - kolumny i układ listy klientów”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań związanych z funkcjonalnością i integracją modułu.
