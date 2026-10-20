---
title: "Arukereso.hu - zaufany program zakupowy, e-maile z ankietami - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Arukereso.hu - zaufany program zakupowy, e-maile z ankietami od MyPresta.eu."
sidebar:
  label: "Arukereso.hu - zaufany program zakupowy, e-maile z ankietami - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Arukereso.hu - trusted purchase program survey emails na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/arukeresohu-trusted-purchase-program-survey-emails.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/arukeresohu-trusted-purchase-program-survey-emails/)
>
> ---


# Arukereso.hu - zaufany program zakupowy, e-maile z ankietami

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu Arukereso.hu. Możesz uzyskać do niego dostęp, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Arukereso.hu” i klikając „Konfiguruj”.

#### 2.1.1 Arukereso.hu WebApiKey

-   **Co robi to ustawienie:** Jest to Twój unikalny identyfikator dostarczony przez Arukereso.hu. Jest on niezbędny, aby Arukereso.hu mogło powiązać żądania ankiet pochodzące z Twojego sklepu PrestaShop z Twoim konkretnym kontem sprzedawcy na ich platformie.
-   **Skutek zmiany tego ustawienia:**
    -   *Po poprawnym wprowadzeniu:* Moduł może pomyślnie komunikować się z systemami Arukereso.hu, umożliwiając automatyczny proces wysyłania e-maili z ankietami.
    -   *Po niepoprawnym lub pustym wprowadzeniu:* Arukereso.hu nie będzie w stanie zidentyfikować Twojego sklepu, a e-maile z ankietami nie zostaną wysłane do Twoich klientów. Integracja zakończy się niepowodzeniem.
-   **Zalecana wartość:** Wprowadź dokładny klucz API dostarczony przez Arukereso.hu. Zazwyczaj znajduje się on w ustawieniach Twojego konta sprzedawcy na stronie internetowej Arukereso.hu.
-   **Scenariusz / przykład dla sprzedawcy:** Rejestrujesz się w „Programie Zaufanych Zakupów” na Arukereso.hu. Otrzymujesz ciąg znaków, np. `abcdef1234567890`. Kopiujesz i wklejasz go w to pole.

#### 2.1.2 Identyfikator produktu (feed ITEM\_ID)

-   **Co robi to ustawienie:** To ustawienie określa, który identyfikator produktu z Twojego sklepu PrestaShop zostanie wysłany do Arukereso.hu. Arukereso.hu używa tego ID do dopasowania zakupionego produktu do jego listy na swojej platformie, zapewniając trafność ankiety.
-   **Skutek zmiany tego ustawienia:**
    -   *Gdy ustawione na „ID produktu”:* Zostanie użyte wewnętrzne ID produktu PrestaShop (np. `123`). Jest to najczęstsza i zazwyczaj najbezpieczniejsza opcja.
    -   *Gdy ustawione na „Referencja produktu”:* Zostanie użyty kod referencyjny Twojego produktu (np. `SKU-001`). Wymaga to, aby Twoje referencje produktów były unikalne i zgodne z oczekiwaniami Arukereso.hu.
    -   *Gdy ustawione na „EAN13 produktu”:* Zostanie użyty kod kreskowy EAN-13 produktu. Jest to odpowiednie, jeśli Twoje kody EAN są konsekwentnie używane i pasują do katalogu produktów Arukereso.hu.
    -   *Gdy ustawione na „UPC produktu”:* Zostanie użyty kod UPC produktu. Podobnie jak w przypadku EAN13, wymaga spójnych danych.
-   **Zalecana wartość:** „ID produktu” jest zazwyczaj najbezpieczniejszą i najbardziej niezawodną opcją, chyba że masz konkretny powód (i zweryfikowany z Arukereso.hu), aby użyć innego identyfikatora.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz produkt „Czerwona koszulka” z wewnętrznym ID `15`, referencją `TSHIRT-RED` i EAN `1234567890123`, wybranie „ID produktu” spowoduje wysłanie `15` do Arukereso.hu. Jeśli wybierzesz „Referencja produktu”, zostanie wysłane `TSHIRT-RED`. Upewnij się, że wybrany identyfikator jest tym, czego oczekuje Arukereso.hu, aby poprawnie powiązać produkty.

#### 2.1.3 Wymagaj zgody klienta

-   **Co robi to ustawienie:** To kluczowe ustawienie kontroluje, czy Twoi klienci muszą wyraźnie zgodzić się na udział w programie ankiet Arukereso.hu podczas realizacji zamówienia. Jest to kluczowe dla zgodności z przepisami o ochronie danych, takimi jak RODO.
-   **Skutek zmiany tego ustawienia:**
    -   *Gdy włączone („Tak”):* Pole wyboru lub podobny mechanizm zgody pojawi się podczas procesu realizacji zamówienia. Tylko klienci, którzy zaznaczą to pole, będą mieli swoje dane zamówienia wysłane do Arukereso.hu w celach ankietowych. Zapewnia to zgodność z RODO.
    -   *Gdy wyłączone („Nie”):* Nie zostanie wyświetlona żadna opcja zgody. Wszyscy klienci, którzy złożą zamówienie, zostaną automatycznie zapisani do programu ankiet Arukereso.hu. **Używaj z ostrożnością i tylko wtedy, gdy masz pewność, że Twoje lokalne przepisy nie wymagają wyraźnej zgody na tego typu udostępnianie danych.**
-   **Zalecana wartość:** „Tak”. Zdecydowanie zaleca się włączenie tej opcji, aby zapewnić zgodność z RODO i innymi przepisami dotyczącymi prywatności, dając klientom kontrolę nad ich danymi.
-   **Scenariusz / przykład dla sprzedawcy:** Działasz w UE. Aby zachować zgodność z RODO, włączasz to ustawienie. Podczas realizacji zamówienia klienci widzą pole wyboru: „Tak, zgadzam się na otrzymywanie ankiety satysfakcji klienta od Arukereso.hu dotyczącej mojego zakupu.” Tylko jeśli zaznaczą to pole, ich dane zostaną udostępnione.

#### 2.1.4 Zapisuj błędy do log.txt

-   **Co robi to ustawienie:** To ustawienie kontroluje, czy moduł rejestruje wszelkie napotkane błędy lub problemy podczas swojego działania w pliku `log.txt` w katalogu modułu.
-   **Skutek zmiany tego ustawienia:**
    -   *Gdy włączone („Tak”):* Wszelkie problemy (np. brak połączenia z Arukereso.hu, problemy z nieprawidłowym kluczem API) zostaną zapisane w `arukereso/log.txt`. Jest to niezwykle pomocne przy rozwiązywaniu problemów.
    -   *Gdy wyłączone („Nie”):* Błędy nie będą zapisywane do pliku. Chociaż to nieznacznie zmniejsza aktywność dysku, znacznie utrudnia diagnozowanie problemów.
-   **Zalecana wartość:** „Tak” podczas początkowej konfiguracji i jeśli napotkasz jakiekolwiek problemy. Gdy moduł działa płynnie, możesz go wyłączyć, jeśli wolisz, ale często najlepiej jest pozostawić go włączonym do bieżącego monitorowania.
-   **Scenariusz / przykład dla sprzedawcy:** Skonfigurowałeś moduł, ale klienci nie otrzymują ankiet. Włączasz to ustawienie, a po kilku testowych zamówieniach sprawdzasz `arukereso/log.txt` i znajdujesz komunikat o błędzie wskazujący „Nieprawidłowy klucz API”. To natychmiast wskazuje, gdzie szukać problemu.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Arukereso.hu WebApiKey | Twój klucz Arukereso.hu | Unikalny identyfikator Twojego sklepu na Arukereso.hu. **Wymagany do integracji.** |
| Konfiguracja modułu | Identyfikator produktu (feed ITEM\_ID) | ID produktu | Definiuje, który identyfikator produktu (ID PrestaShop, Referencja, EAN, UPC) jest wysyłany do Arukereso.hu. |
| Konfiguracja modułu | Wymagaj zgody klienta | Tak | Wyświetla pole wyboru zgody podczas realizacji zamówienia. **Wysoce zalecane dla zgodności z RODO.** |
| Konfiguracja modułu | Zapisuj błędy do log.txt | Tak | Rejestruje błędy modułu w `arukereso/log.txt` w celu rozwiązywania problemów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moi klienci nie otrzymują e-maili z ankietami od Arukereso.hu. Co powinienem sprawdzić?**
O:

1.  **Arukereso.hu WebApiKey:** Sprawdź dokładnie, czy Twój klucz API jest poprawnie wprowadzony w konfiguracji modułu. Nawet pojedyncza literówka uniemożliwi działanie integracji.
2.  **Ustawienie zgody:** Jeśli włączono „Wymagaj zgody klienta”, upewnij się, że klienci faktycznie zaznaczają pole zgody podczas realizacji zamówienia. Jeśli tego nie zrobią, żadne dane nie zostaną wysłane.
3.  **Plik dziennika:** Włącz „Zapisuj błędy do log.txt” w konfiguracji modułu i sprawdź plik `arukereso/log.txt` pod kątem komunikatów o błędach po zamówieniu testowym. Jest to najbardziej bezpośredni sposób diagnozowania problemów.
4.  **Konto Arukereso.hu:** Zaloguj się na swoje konto sprzedawcy Arukereso.hu i sprawdź status integracji „Programu Zaufanych Zakupów”. Mogą tam być specyficzne dzienniki lub wskaźniki statusu.
5.  **Status zamówienia:** Upewnij się, że status zamówienia, który wyzwala ankietę (zazwyczaj „Płatność zaakceptowana” lub „Dostarczono”), jest poprawnie skonfigurowany po stronie Arukereso.hu, a Twoje zamówienia PrestaShop osiągają ten status.

**P: Włączyłem „Wymagaj zgody klienta”, ale nie widzę pola wyboru podczas realizacji zamówienia.**
O:

1.  **Kompatybilność z motywem:** Moduł używa standardowych hooków PrestaShop (`displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`). Jeśli Twój motyw jest mocno dostosowany, może nie renderować tych hooków poprawnie.
2.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).
3.  **Pozycja modułu:** Przejdź do Wygląd > Pozycje i wyszukaj wspomniane hooki. Upewnij się, że moduł Arukereso.hu jest wymieniony i aktywny w tych hookach. Jeśli nie, spróbuj go przeszczepić.
4.  **Konflikty modułów:** Tymczasowo wyłącz inne moduły, które modyfikują proces realizacji zamówienia, aby wykluczyć konflikty.

**P: Co się stanie, jeśli klient zażąda usunięcia swoich danych (prawo do bycia zapomnianym RODO)?**
O: Moduł jest zaprojektowany do integracji z narzędziami RODO PrestaShop. Gdy klient zażąda usunięcia danych za pośrednictwem modułu RODO PrestaShop, ten moduł Arukereso.hu odpowie na hook `actionDeleteGDPRCustomer`, zapewniając usunięcie wszelkich danych związanych z klientem przechowywanych przez moduł (np. rekordy zgody). Należy jednak pamiętać, że ten moduł *wysyła* dane do Arukereso.hu. Będziesz musiał również skontaktować się bezpośrednio z Arukereso.hu, aby zażądać usunięcia danych tego klienta z ich systemów.

**P: Czy mogę dostosować wygląd pola wyboru zgody?**
O: Wygląd pola wyboru zgody jest kontrolowany głównie przez CSS Twojego motywu PrestaShop. Moduł dostarcza strukturę HTML za pośrednictwem swojego szablonu `consent.tpl`. Możesz nadpisać ten szablon w swoim motywie lub dodać niestandardowy CSS, aby stylizować element, jeśli chcesz zmienić jego wygląd.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł Arukereso.hu to lekki moduł PrestaShop, skupiający się głównie na integracji z „Programem Zaufanych Zakupów” Arukereso.hu. Wykorzystuje system hooków PrestaShop do wstrzykiwania opcji zgody podczas realizacji zamówienia i wysyłania danych zamówienia do Arukereso.hu po potwierdzeniu zamówienia. Moduł ten ma standardową strukturę modułu PrestaShop, z główną logiką znajdującą się w głównym pliku modułu (`arukereso.php`) i wykorzystującą szablony Smarty do wyświetlania w front-office. Nie wprowadza niestandardowych kontrolerów ani ObjectModels, opierając się na klasie `Configuration` PrestaShop do przechowywania ustawień.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office. Cała logika jest obsługiwana w głównym pliku modułu `arukereso.php`, głównie za pośrednictwem metod hooków.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł **nie** definiuje żadnych niestandardowych klas ani ObjectModels w katalogu `classes/`. Działa bezpośrednio w pliku `arukereso.php`, używając standardowych klas i funkcji PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript. Cała interakcja w front-office (np. pole wyboru zgody) jest obsługiwana za pośrednictwem standardowych formularzy HTML i przetwarzania po stronie serwera.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików CSS. Wszelkie style dla pola wyboru zgody lub innych elementów byłyby dziedziczone z aktywnego motywu PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `arukereso/views/templates/hook/consent.tpl`
    -   **Hook:** `displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop` (w zależności od motywu i wersji PrestaShop, jeden z nich wyrenderuje zgodę).
    -   **Cel:** Ten szablon renderuje HTML dla pola wyboru zgody klienta podczas procesu realizacji zamówienia. Zazwyczaj zawiera etykietę, pole wyboru i potencjalnie link do polityki prywatności lub więcej informacji o Arukereso.hu.
    -   **Wynik:** Mały element formularza umożliwiający klientowi wyrażenie zgody na program ankiet.
-   `arukereso/views/templates/hook/displayOrderConfirmation.tpl`
    -   **Hook:** `displayOrderConfirmation`
    -   **Cel:** Ten szablon jest renderowany na stronie potwierdzenia zamówienia po udanym zakupie. Może wyświetlać wiadomość do klienta potwierdzającą jego udział w programie ankiet (jeśli wyrażono zgodę) lub dostarczać informacje o nadchodzącej ankiecie.
    -   **Wynik:** Mały blok informacyjny na stronie potwierdzenia zamówienia.

#### Szablony administracyjne (`views/templates/admin/`)

Ten moduł **nie** zawiera żadnych niestandardowych szablonów administracyjnych poza tym, co jest renderowane przez `getContent()` w głównym pliku modułu.

#### Szablony front-office (`views/templates/front/`)

Ten moduł **nie** zawiera żadnych dedykowanych, samodzielnych szablonów stron front-office.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Ten moduł **nie** tworzy żadnych niestandardowych tabel bazy danych. Wszystkie jego ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` PrestaShop przy użyciu następujących kluczy:

-   `ARUKERESO_FILE_LOG`: Przechowuje wartość logiczną dla logowania błędów.
-   `ARUKERESO_ID`: Przechowuje klucz WebApiKey Arukereso.hu.
-   `ARUKERESO_PRODUCT_ID`: Przechowuje wybrany typ identyfikatora produktu (np. 'id\_product', 'reference').
-   `ARUKERESO_CONSENT`: Przechowuje wartość logiczną dla wymagania zgody klienta.
-   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Standardowy klucz konfiguracji PrestaShop, nie zarządzany bezpośrednio przez ten moduł, ale potencjalnie używany do obsługi języków w panelu administracyjnym.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayGDPRConsent` | Podczas realizacji zamówienia, zazwyczaj w pobliżu zgody na politykę prywatności. | Renderuje pole wyboru zgody klienta na udział w ankiecie Arukereso.hu. |
| `actionDeleteGDPRCustomer` | Wyzwalany, gdy klient zażąda usunięcia danych za pośrednictwem modułu RODO PrestaShop. | Obsługuje usuwanie wszelkich danych specyficznych dla klienta przechowywanych przez moduł (np. status zgody). |
| `actionExportGDPRData` | Wyzwalany, gdy klient zażąda eksportu danych za pośrednictwem modułu RODO PrestaShop. | Dostarcza wszelkie dane specyficzne dla klienta przechowywane przez moduł do eksportu. |
| `displayOrderConfirmation` | Na stronie potwierdzenia zamówienia po udanym zakupie. | Renderuje komunikat informacyjny dla klienta i, co najważniejsze, wysyła dane zamówienia do API Arukereso.hu, jeśli wyrażono zgodę. |
| `displayPaymentTop` | Na górze sekcji płatności podczas realizacji zamówienia. | Alternatywny hook do renderowania pola wyboru zgody klienta, w zależności od motywu. |
| `displayCheckoutSummaryTop` | Na górze sekcji podsumowania zamówienia. | Alternatywny hook do renderowania pola wyboru zgody klienta, w zależności od motywu. |
| `DisplayGDPRConsent` | (Alias/Starsza wersja `displayGDPRConsent`) | Renderuje pole wyboru zgody klienta. |
| `DisplayPaymentTop` | (Alias/Starsza wersja `displayPaymentTop`) | Renderuje pole wyboru zgody klienta. |
| `DisplayOrderConfirmation` | (Alias/Starsza wersja `displayOrderConfirmation`) | Renderuje informacje i wysyła dane zamówienia. |
| `ActionDeleteGDPRCustomer` | (Alias/Starsza wersja `actionDeleteGDPRCustomer`) | Obsługuje usuwanie danych klienta. |
| `ActionExportGDPRData` | (Alias/Starsza wersja `actionExportGDPRData`) | Obsługuje eksport danych klienta. |
| `DisplayCheckoutSummaryTop` | (Alias/Starsza wersja `displayCheckoutSummaryTop`) | Renderuje pole wyboru zgody klienta. |

Główna logika modułu do wysyłania danych zamówienia do Arukereso.hu znajduje się w metodzie `hookDisplayOrderConfirmation` w `arukereso.php`. Metoda ta sprawdza zgodę klienta (jeśli jest wymagana), a następnie konstruuje i wysyła żądanie HTTP do API Arukereso.hu ze szczegółami zamówienia.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań dotyczących modułu Arukereso.hu - zaufany program zakupowy, e-maile z ankietami.
