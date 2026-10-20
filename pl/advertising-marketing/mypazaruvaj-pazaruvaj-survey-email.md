---
title: "MyPazaruvaj - Pazaruvaj survey email - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop MyPazaruvaj - Pazaruvaj survey email od MyPresta.eu."
sidebar:
  label: "MyPazaruvaj - Pazaruvaj survey email - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł MyPazaruvaj - Pazaruvaj survey email na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/mypazaruvaj-pazaruvaj-survey-email.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/mypazaruvaj-pazaruvaj-survey-email/)
>
> ---


# MyPazaruvaj - Pazaruvaj survey email

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5 (Moduł został zaprojektowany tak, aby był szeroko kompatybilny z różnymi wersjami PHP, aż do najnowszej stabilnej wersji obsługiwanej przez PrestaShop 8 i 9.)
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i są wystarczające dla tego modułu. Nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > MyPazaruvaj)

Jest to główny i jedyny ekran konfiguracji modułu MyPazaruvaj. Tutaj ustawisz wszystkie niezbędne parametry do połączenia Twojego sklepu z Pazaruvaj.com.

#### **ID sklepu Pazaruvaj.com**

- **Co robi to ustawienie:** Jest to Twój unikalny identyfikator dostarczony przez Pazaruvaj.com dla Twojego sklepu internetowego. Informuje Pazaruvaj, do którego sklepu należą dane zamówienia.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawione poprawnie:* Moduł pomyślnie wyśle dane zamówienia do Twojego profilu sklepu Pazaruvaj.com.
  - *Gdy niepoprawne lub puste:* Pazaruvaj.com nie będzie w stanie zidentyfikować Twojego sklepu, a żadne e-maile z ankietami nie zostaną wysłane do Twoich klientów.
- **Zalecana wartość:** Wprowadź dokładny identyfikator sklepu (Shop ID) dostarczony przez Pazaruvaj.com. Jest to pole obowiązkowe.
- **Scenariusz / przykład dla sprzedawcy:** Zarejestrowałeś swój sklep na Pazaruvaj.com i otrzymaliście identyfikator sklepu, np. `12345`. Musisz wprowadzić `12345` tutaj, aby integracja działała.

#### **Pole ID produktu Pazaruvaj.com**

- **Co robi to ustawienie:** Ta opcja określa, który identyfikator produktu z Twojego sklepu PrestaShop powinien zostać wysłany do Pazaruvaj.com. Pazaruvaj.com używa tego identyfikatora do dopasowania zakupionego produktu do jego listy na swojej platformie.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawione na „ID produktu”:* Zostanie wysłany wewnętrzny identyfikator produktu PrestaShop (np. `id_product`). Jest to zazwyczaj najbezpieczniejsza opcja, jeśli Twój feed Pazaruvaj.com używa tych identyfikatorów.
  - *Gdy ustawione na „Referencja produktu”:* Zostanie wysłany kod referencyjny produktu (np. `reference`). Wybierz tę opcję, jeśli Twój feed Pazaruvaj.com dopasowuje produkty według ich referencji.
  - *Gdy ustawione na „EAN13 produktu”:* Zostanie wysłany kod kreskowy EAN13 produktu. Przydatne, jeśli Twój feed Pazaruvaj.com opiera się na kodach EAN.
  - *Gdy ustawione na „UPC produktu”:* Zostanie wysłany kod UPC produktu.
- **Zalecana wartość:** „ID produktu” jest często najbardziej niezawodnym domyślnym ustawieniem. Musisz jednak **zweryfikować**, którego identyfikatora używa Twój feed produktów na Pazaruvaj.com do dopasowywania produktów. Jeśli Twój feed używa referencji produktów, wybierz „Referencja produktu”.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój feed produktów na Pazaruvaj.com używa unikalnego wewnętrznego identyfikatora, który PrestaShop przypisuje każdemu produktowi, powinieneś wybrać „ID produktu”. Jeśli przesłałeś feed, w którym każdy produkt jest identyfikowany przez konkretny numer SKU lub referencyjny (np. `REF-001`), to wybierz „Referencja produktu”.

#### **Włącz zgodę na wysyłanie danych do Pazaruvaj.com**

- **Co robi to ustawienie:** Ten przełącznik kontroluje, czy klienci muszą wyraźnie zgodzić się na wysłanie danych ich zamówienia do Pazaruvaj.com w celu przeprowadzenia ankiety. Po włączeniu, podczas realizacji zamówienia pojawia się pole wyboru.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Na stronie realizacji zamówienia pojawi się pole wyboru. Tylko klienci, którzy zaznaczą to pole, będą mieli swoje dane zamówienia wysłane do Pazaruvaj.com. Pomaga to w zgodności z RODO i innymi przepisami dotyczącymi prywatności danych.
  - *Gdy wyłączone (NIE):* Dane zamówienia będą wysyłane do Pazaruvaj.com dla *wszystkich* zrealizowanych zamówień bez wymagania wyraźnej zgody klienta. Jest to prostsze dla klientów, ale może nie być zgodne ze wszystkimi przepisami dotyczącymi prywatności w Twoim regionie.
- **Zalecana wartość:** „TAK” jest ogólnie zalecane dla zgodności z przepisami o ochronie danych (takimi jak RODO).
- **Scenariusz / przykład dla sprzedawcy:** Aby zapewnić pełną zgodność Twojego sklepu z przepisami o ochronie prywatności, włączasz to ustawienie. Podczas realizacji zamówienia Twoi klienci zobaczą pole wyboru z etykietą podobną do „Zgadzam się na udostępnienie moich danych zamówienia Pazaruvaj.com w celu przeprowadzenia ankiety”. Dane zostaną wysłane tylko wtedy, gdy je zaznaczą.

#### **Pokaż zgodę na**

- **Co robi to ustawienie:** Jeśli „Włącz zgodę” jest ustawione na TAK, ta opcja określa, gdzie pole wyboru zgody zostanie wyświetlone w front-office Twojego sklepu.
- **Wpływ zmiany tego ustawienia:**
  - *Nagłówek, Kolumny, Produkt, Stopka:* Pole wyboru zgody zostanie wyświetlone w wybranym obszarze hooka. Dokładne wizualne umiejscowienie zależy od układu Twojego motywu dla tego hooka.
- **Zalecana wartość:** Wybierz widoczne, ale nieingerujące miejsce. „Stopka” lub konkretna „Kolumna” (jeśli Twój motyw ma odpowiednią) są często dobrymi wyborami dla powiadomień związanych z prywatnością. Może być konieczne przetestowanie różnych opcji, aby zobaczyć, co najlepiej wygląda z Twoim motywem.
- **Scenariusz / przykład dla sprzedawcy:** Włączyłeś zgodę. Decydujesz się pokazać pole wyboru zgody w „Stopce”, aby było widoczne, ale nie zaśmiecało głównego przepływu realizacji zamówienia.

#### **Włącz dziennik błędów**

- **Co robi to ustawienie:** Ten przełącznik kontroluje, czy moduł rejestruje wszelkie błędy napotkane podczas procesu transferu danych do Pazaruvaj.com.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Moduł zapisze szczegóły wszelkich nieudanych przesłań danych do pliku dziennika. Jest to nieocenione przy rozwiązywaniu problemów, jeśli ankiety nie są wysyłane.
  - *Gdy wyłączone (NIE):* Nie zostaną zarejestrowane żadne informacje o błędach, co utrudni diagnozowanie problemów.
- **Zalecana wartość:** „TAK” jest wysoce zalecane, zwłaszcza podczas początkowej konfiguracji i do bieżącego monitorowania.
- **Scenariusz / przykład dla sprzedawcy:** Nie jesteś pewien, czy integracja działa idealnie. Włączasz dziennik błędów. Jeśli Pazaruvaj.com nie otrzymuje danych, możesz sprawdzić dziennik, aby zobaczyć, czy są jakieś konkretne komunikaty o błędach, takie jak nieprawidłowy identyfikator sklepu lub problemy z połączeniem.

#### **Wyczyść dziennik błędów**

- **Co robi to ustawienie:** Ten przycisk umożliwia usunięcie wszystkich wpisów z dziennika błędów modułu.
- **Wpływ zmiany tego ustawienia:**
  - *Po kliknięciu:* Wszystkie wcześniej zarejestrowane błędy zostają trwale usunięte z pliku dziennika.
- **Zalecana wartość:** Użyj tego po przejrzeniu i rozwiązaniu wszelkich problemów lub jeśli plik dziennika stanie się zbyt duży.
- **Scenariusz / przykład dla sprzedawcy:** Naprawiłeś problem z identyfikatorem sklepu Pazaruvaj.com. Klikasz „Wyczyść dziennik błędów”, aby zacząć od nowa i upewnić się, że rejestrowane są tylko nowe, istotne błędy.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | ID sklepu Pazaruvaj.com | Twój ID Pazaruvaj (Obowiązkowe) | Unikalny identyfikator Twojego sklepu na Pazaruvaj.com. Niezbędny do transferu danych. |
| Konfiguracja modułu | Pole ID produktu Pazaruvaj.com | ID produktu (Zweryfikuj z feedem Pazaruvaj) | Określa, który identyfikator produktu PrestaShop (ID, Referencja, EAN13, UPC) jest wysyłany do Pazaruvaj.com w celu dopasowania produktu. |
| Konfiguracja modułu | Włącz zgodę na wysyłanie danych do Pazaruvaj.com | TAK (Dla zgodności) | Wymaga zgody klienta za pomocą pola wyboru podczas realizacji zamówienia przed wysłaniem danych do Pazaruvaj.com. |
| Konfiguracja modułu | Pokaż zgodę na | Stopka (Testuj dla najlepszego umiejscowienia) | Określa hook front-office, w którym pojawi się pole wyboru zgody, jeśli jest włączone. |
| Konfiguracja modułu | Włącz dziennik błędów | TAK (Do rozwiązywania problemów) | Aktywuje logowanie wszelkich błędów podczas przesyłania danych do Pazaruvaj.com. |
| Konfiguracja modułu | Wyczyść dziennik błędów | N/A (Przycisk) | Usuwa wszystkie wpisy z dziennika błędów modułu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moi klienci nie otrzymują e-maili z ankietami od Pazaruvaj.com. Co powinienem sprawdzić?**
O:

1.  **ID sklepu Pazaruvaj.com:** Dokładnie sprawdź, czy Twój „ID sklepu Pazaruvaj.com” w konfiguracji modułu jest absolutnie poprawny i zgodny z ID dostarczonym przez Pazaruvaj.com.
2.  **Dziennik błędów:** Włącz „Dziennik błędów” w konfiguracji modułu i sprawdź, czy po testowym zamówieniu nie ma żadnych zarejestrowanych błędów. Często wskaże to dokładny problem.
3.  **Ustawienie zgody:** Jeśli „Włącz zgodę na wysyłanie danych do Pazaruvaj.com” jest włączone, upewnij się, że klienci faktycznie zaznaczają pole wyboru podczas realizacji zamówienia. Jeśli tego nie zrobią, dane nie zostaną wysłane.
4.  **Status zamówienia:** Upewnij się, że zamówienie osiągnie status „Płatność zaakceptowana” lub podobny status końcowy w PrestaShop, ponieważ moduł zazwyczaj uruchamia się po pomyślnym zakończeniu zamówienia.
5.  **Konto Pazaruvaj.com:** Zaloguj się na swoje konto Pazaruvaj.com, aby sprawdzić, czy nie ma żadnych problemów lub ostrzeżeń z ich strony dotyczących Twojego sklepu lub feedu danych.

**P: Pole wyboru zgody nie pojawia się na mojej stronie realizacji zamówienia.**
O:

1.  **Ustawienie „Włącz zgodę”:** Najpierw upewnij się, że „Włącz zgodę na wysyłanie danych do Pazaruvaj.com” jest ustawione na TAK w konfiguracji modułu.
2.  **Ustawienie „Pokaż zgodę na”:** Sprawdź, który hook wybrałeś dla „Pokaż zgodę na”. Jeśli Twój motyw nie wyświetla aktywnie treści w tym konkretnym hooku (np. niestandardowy `displayMyCustomHook`), pole wyboru nie pojawi się. Spróbuj przełączyć się na wspólny hook, taki jak `displayFooter` lub `displayHeader`, aby przetestować.
3.  **Kompatybilność motywu:** Niektóre wysoce spersonalizowane motywy mogą nadpisywać standardowe umiejscowienia hooków. Jeśli problem nadal występuje, może być konieczne, aby webmaster sprawdził pliki szablonów Twojego motywu.
4.  **Pamięć podręczna Smarty:** Wyczyść pamięć podręczną Smarty PrestaShop w **Zaawansowane > Wydajność** (Wymuś kompilację i wyczyść pamięć podręczną).

**P: Zmieniłem ustawienie, ale nic się nie stało w moim sklepie.**
O: Po wprowadzeniu jakichkolwiek zmian w konfiguracji modułu, zawsze wyczyść pamięć podręczną PrestaShop. Przejdź do **Zaawansowane > Wydajność**, a następnie kliknij „Wyczyść pamięć podręczną” i opcjonalnie „Wymuś kompilację”, jeśli wprowadzasz zmiany związane z szablonem. Może być również konieczne wyczyszczenie pamięci podręcznej przeglądarki (Ctrl+F5 lub Cmd+R).

**P: Czy mogę dostosować tekst pola wyboru zgody?**
O: Tak, tekst pola wyboru zgody jest tłumaczalny. Możesz go zmodyfikować za pomocą systemu tłumaczeń PrestaShop:

1.  Przejdź do **Lokalizacja > Tłumaczenia**.
2.  Wybierz „Tłumaczenia zainstalowanych modułów”.
3.  Wybierz swój motyw, język, a następnie wybierz „MyPazaruvaj”.
4.  Znajdziesz tam ciąg znaków związany z komunikatem zgody i możesz go edytować.

**P: Co jeśli mam włączonych wiele sklepów (multistore)?**
O: Moduł powinien być konfigurowany indywidualnie dla każdego sklepu w środowisku multistore. Upewnij się, że wybrałeś właściwy kontekst sklepu w panelu administracyjnym PrestaShop przed skonfigurowaniem modułu dla tego konkretnego sklepu. Każdy sklep będzie prawdopodobnie miał swój własny, unikalny identyfikator sklepu Pazaruvaj.com.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem MyPazaruvaj.

### 4.1 Przegląd architektury

Moduł MyPazaruvaj jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie klasę `Module` i jej metody `install()`, `uninstall()` oraz `getContent()` do konfiguracji. Jego podstawowa funkcjonalność jest sterowana zdarzeniami, wykorzystując hooki PrestaShop do przechwytywania zdarzeń potwierdzenia zamówienia i wyświetlania opcjonalnej zgody. Przesyłanie danych do Pazaruvaj.com jest obsługiwane bezpośrednio w głównym pliku PHP modułu, bez dedykowanych kontrolerów front-office lub admin, co czyni go lekkim i wydajnym rozwiązaniem.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje dedykowanych kontrolerów front-office ani back-office. Cała logika konfiguracji jest obsługiwana w metodzie `getContent()` głównego pliku modułu, a logika wyświetlania front-office jest zarządzana bezpośrednio za pomocą szablonów hooków.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Cała logika jest zawarta w głównej klasie `MyPazaruvaj` zdefiniowanej w `mypazaruvaj/index.php`.

Główna klasa `MyPazaruvaj` rozszerza `Module` i zawiera:

- `__construct()`: Ustawia właściwości modułu (nazwa, zakładka, wersja, autor, `need_instance`, `ps_versions_compliancy`, `bootstrap`).
- `install()`: Rejestruje niezbędne hooki (`displayOrderConfirmation`, `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`), tworzy wpisy konfiguracyjne i inicjalizuje plik dziennika błędów.
- `uninstall()`: Wyrejestrowuje hooki i usuwa wpisy konfiguracyjne.
- `getContent()`: Renderuje formularz konfiguracji back-office modułu, obsługuje przesyłanie formularzy i aktualizuje wartości konfiguracyjne.
- `hookDisplayOrderConfirmation()`: Główny hook do przesyłania danych. Pobiera szczegóły zamówienia, informacje o kliencie i dane produktu, a następnie konstruuje i wysyła żądanie do Pazaruvaj.com. Obsługuje również opcjonalne sprawdzenie zgody.
- `hookDisplayHeader()`, `hookDisplayFooter()`, `hookDisplayLeftColumn()`, `hookDisplayRightColumn()`: Te hooki są używane do wyświetlania pola wyboru zgody, jeśli jest włączone i skonfigurowane do pojawiania się w tych miejscach. Renderują szablon `consent.tpl`.
- `_clearLog()`: Wewnętrzna metoda do czyszczenia pliku dziennika błędów.
- `_writeLog()`: Wewnętrzna metoda do zapisywania wiadomości do pliku dziennika błędów.
- `_displayForm()`: Wewnętrzna metoda do renderowania formularza konfiguracji za pomocą `HelperForm` PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Wszelkie style dla pola wyboru zgody opierałyby się na domyślnych stylach elementów formularza motywu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:

  - `mypazaruvaj/views/templates/hook/consent.tpl`:
    - **Cel:** Renderuje opcjonalne pole wyboru zgody na wysyłanie danych do Pazaruvaj.com.
    - **Renderowane w hookach:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn` (w zależności od konfiguracji modułu).
    - **Zmienne:** Zazwyczaj sprawdza `$consent_enabled` i wyświetla pole formularza.
    - **Wyjście:** Proste pole wyboru HTML i etykieta.
  - `mypazaruvaj/views/templates/hook/displayOrderConfirmation.tpl`:
    - **Cel:** Ten szablon jest prawdopodobnie placeholderem lub jest używany do wewnętrznej logiki modułu, która nie wyświetla bezpośrednio widocznej treści klientowi. Główna logika przesyłania danych dla `displayOrderConfirmation` jest obsługiwana w samej metodzie hooka PHP, niekoniecznie poprzez wyjście szablonu. Może być używany do przekazywania zmiennych lub wyzwalania JS, jeśli moduł miałby takie funkcje. W kontekście tego modułu, to głównie metoda hooka PHP wykonuje akcję.
- **Szablony administracyjne (`views/templates/admin/`)**:

  - Ten moduł nie używa dedykowanych szablonów administracyjnych. Formularz konfiguracji jest generowany programowo za pomocą `HelperForm` w `getContent()`.
- **Szablony front-office (`views/templates/front/`)**:

  - Ten moduł nie zawiera żadnych dedykowanych szablonów front-office poza szablonami hooków.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Przechowuje swoje ustawienia konfiguracyjne w standardowej tabeli PrestaShop `ps_configuration`.
    - `MYPAZARUVAJ_SHOP_ID`: Przechowuje ID sklepu Pazaruvaj.com.
    - `MYPAZARUVAJ_PRODUCT_ID_FIELD`: Przechowuje wybrane pole ID produktu (np. 'id\_product', 'reference').
    - `MYPAZARUVAJ_CONSENT_ENABLED`: Wartość logiczna (0 lub 1) dla włączania/wyłączania zgody.
    - `MYPAZARUVAJ_CONSENT_HOOK`: Przechowuje nazwę hooka, w którym wyświetlana jest zgoda.
    - `MYPAZARUVAJ_ERROR_LOG_ENABLED`: Wartość logiczna (0 lub 1) dla włączania/wyłączania dziennika błędów.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayOrderConfirmation` | Po pomyślnym zakończeniu zamówienia przez klienta. | **Główny hook do przesyłania danych.** Pobiera szczegóły zamówienia i produktu, konstruuje żądanie Pazaruvaj.com i wysyła je. Sprawdza zgodę, jeśli jest włączona. |
| `displayHeader` | W sekcji `<head>` lub na górze każdej strony. | Renderuje `consent.tpl`, jeśli skonfigurowano wyświetlanie zgody tutaj. |
| `displayFooter` | W sekcji stopki każdej strony. | Renderuje `consent.tpl`, jeśli skonfigurowano wyświetlanie zgody tutaj. |
| `displayLeftColumn` | W lewej kolumnie bocznej (jeśli aktywna w motywie). | Renderuje `consent.tpl`, jeśli skonfigurowano wyświetlanie zgody tutaj. |
| `displayRightColumn` | W prawej kolumnie bocznej (jeśli aktywna w motywie). | Renderuje `consent.tpl`, jeśli skonfigurowano wyświetlanie zgody tutaj. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu MyPazaruvaj.
