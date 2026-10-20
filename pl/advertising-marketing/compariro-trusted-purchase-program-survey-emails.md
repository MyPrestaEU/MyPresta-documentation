---
title: "Compari.ro - program zaufanych zakupów, e-maile z ankietami - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla deweloperów modułu PrestaShop Compari.ro - program zaufanych zakupów, e-maile z ankietami od MyPresta.eu."
sidebar:
  label: "Compari.ro - program zaufanych zakupów, e-maile z ankietami - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Compari.ro - trusted purchase program survey emails na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/compariro-trusted-purchase-program-survey-emails.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/compariro-trusted-purchase-program-survey-emails/)
>
> ---


# Compari.ro - program zaufanych zakupów, e-maile z ankietami

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu Compari.ro. Możesz uzyskać do niego dostęp, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Compari.ro” i klikając przycisk „Konfiguruj”.

#### **1. Compari.ro WebApiKey**

- **Co robi to ustawienie:** Jest to Twój unikalny identyfikator dostarczony przez Compari.ro, który łączy Twój sklep PrestaShop z Twoim kontem sprzedawcy Compari.ro. Jest to niezbędne, aby „Program Zaufanych Zakupów” prawidłowo przypisywał prośby o ankiety do Twojego sklepu.
- **Wpływ zmiany tego ustawienia:**
  - *Po poprawnym wprowadzeniu:* Moduł będzie mógł wysyłać dane zamówienia do Compari.ro, umożliwiając im wysyłanie e-maili z ankietami do Twoich klientów.
  - *Po nieprawidłowym lub pustym wprowadzeniu:* Integracja zakończy się niepowodzeniem, a Compari.ro nie otrzyma informacji o zamówieniu, co oznacza, że żadne e-maile z ankietami nie zostaną wysłane.
- **Zalecana wartość:** Wprowadź dokładny WebApiKey dostarczony przez Compari.ro.
- **Scenariusz / przykład sprzedawcy:** Zarejestrowałeś się w „Programie Zaufanych Zakupów” Compari.ro i otrzymałeś e-mail z kluczem API. Musisz skopiować i wkleić ten klucz tutaj, aby integracja działała.

#### **2. Identyfikator produktu (feed ITEM\_ID)**

- **Co robi to ustawienie:** To ustawienie definiuje, który identyfikator produktu z Twojego sklepu PrestaShop powinien być używany jako `ITEM_ID` podczas wysyłania informacji o produkcie do Compari.ro. Jest to kluczowe dla dopasowania produktów w Twoim kanale Compari.ro do produktów w Twoich zamówieniach.
- **Wpływ zmiany tego ustawienia:**
  - *Po ustawieniu na `id_product` (domyślnie):* Zostanie użyty wewnętrzny identyfikator produktu PrestaShop. Jest to zazwyczaj najbezpieczniejsza opcja, jeśli nie masz konkretnego niestandardowego identyfikatora.
  - *Po ustawieniu na `reference`:* Zostanie użyty kod referencyjny produktu. Wybierz tę opcję, jeśli Twój kanał produktów Compari.ro używa referencji produktu jako `ITEM_ID`.
  - *Po ustawieniu na `ean13`:* Zostanie użyty kod kreskowy EAN-13 produktu. Wybierz tę opcję, jeśli Twój kanał produktów Compari.ro używa EAN-13 jako `ITEM_ID`.
  - *Po ustawieniu na `upc`:* Zostanie użyty kod UPC produktu. Wybierz tę opcję, jeśli Twój kanał produktów Compari.ro używa UPC jako `ITEM_ID`.
- **Zalecana wartość:** `id_product` (chyba że Twój kanał produktów Compari.ro wyraźnie używa `reference`, `ean13` lub `upc` jako `ITEM_ID`).
- **Scenariusz / przykład sprzedawcy:** Twój kanał produktów Compari.ro używa unikalnego kodu kreskowego EAN-13 dla każdego produktu. Wybierzesz tutaj `ean13`, aby upewnić się, że Compari.ro może prawidłowo zidentyfikować produkty zakupione przez Twoich klientów.

#### **3. Wymagaj zgody klienta**

- **Co robi to ustawienie:** Ta opcja określa, czy Twoi klienci muszą wyraźnie zgodzić się na udział w programie ankiet Compari.ro podczas realizacji zamówienia. Jest to ważne dla zgodności z RODO i poszanowania preferencji prywatności klientów.
- **Wpływ zmiany tego ustawienia:**
  - *Po włączeniu (ustawione na „Tak”):* Podczas procesu realizacji zamówienia (np. na stronie płatności lub w podsumowaniu zamówienia) pojawi się pole wyboru. Klienci muszą zaznaczyć to pole, aby zezwolić na wysłanie danych ich zamówienia do Compari.ro w celach ankietowych. Jeśli nie wyrażą zgody, żaden e-mail z ankietą nie zostanie wysłany dla ich zamówienia.
  - *Po wyłączeniu (ustawione na „Nie”):* Nie zostanie wyświetlone pole wyboru zgody. Dane zamówienia zostaną wysłane do Compari.ro dla wszystkich zamówień, zakładając, że `WebApiKey` jest poprawny.
- **Zalecana wartość:** „Tak”, jeśli działasz w regionach z surowymi przepisami dotyczącymi prywatności danych (takimi jak RODO) lub jeśli chcesz dać klientom pełną kontrolę nad udostępnianiem ich danych. „Nie”, jeśli ustaliłeś, że wyraźna zgoda nie jest wymagana w Twoim konkretnym kontekście prawnym lub jeśli chcesz zmaksymalizować udział w ankietach.
- **Scenariusz / przykład sprzedawcy:** Aby zachować zgodność z przepisami RODO, włączasz to ustawienie. Podczas realizacji zamówienia klienci widzą pole wyboru „Zgadzam się na udział w ankiecie Programu Zaufanych Zakupów Compari.ro”. Tylko klienci, którzy zaznaczą to pole, otrzymają e-mail z ankietą.

#### **4. Zapisuj błędy do log.txt**

- **Co robi to ustawienie:** Jest to opcja debugowania, która kontroluje, czy moduł rejestruje wszelkie napotkane błędy podczas jego działania (np. problemy z wysyłaniem danych do Compari.ro) do pliku `log.txt` w katalogu modułu.
- **Wpływ zmiany tego ustawienia:**
  - *Po włączeniu (ustawione na „Tak”):* Wszelkie błędy techniczne zostaną zapisane do `compari/log.txt`. Ten plik może być bardzo pomocny dla Twojego webmastera lub wsparcia MyPresta.eu w diagnozowaniu problemów.
  - *Po wyłączeniu (ustawione na „Nie”):* Błędy nie będą jawnie logowane do pliku. Jest to ogólnie preferowane dla działających sklepów produkcyjnych, aby uniknąć generowania dużych plików dziennika, chyba że aktywnie rozwiązujesz problem.
- **Zalecana wartość:** „Nie” dla działającego sklepu produkcyjnego. „Tak”, jeśli masz problemy z integracją i potrzebujesz debugować. Pamiętaj, aby wyłączyć tę opcję po rozwiązaniu problemu.
- **Scenariusz / przykład sprzedawcy:** Skonfigurowałeś moduł, ale klienci nie otrzymują e-maili z ankietami. Włączasz „Zapisuj błędy do log.txt”, a następnie składasz zamówienie testowe. Następnie sprawdzasz plik `log.txt` w poszukiwaniu wskazówek, dlaczego integracja może się nie powieść.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Compari.ro WebApiKey | Twój unikalny klucz API | Łączy Twój sklep z Compari.ro w celu automatyzacji ankiet. **Krytyczne dla funkcjonalności.** |
| Konfiguracja modułu | Identyfikator produktu (feed ITEM\_ID) | `id_product` (lub dopasuj do swojego kanału) | Określa, który identyfikator produktu (wewnętrzny, referencyjny, EAN, UPC) wysłać do Compari.ro. |
| Konfiguracja modułu | Wymagaj zgody klienta | Tak (dla RODO) | Wyświetla pole wyboru zgody podczas realizacji zamówienia. Jeśli nie zaznaczone, e-mail z ankietą nie jest wysyłany. |
| Konfiguracja modułu | Zapisuj błędy do log.txt | Nie (włącz do debugowania) | Rejestruje błędy techniczne do `compari/log.txt` w celu rozwiązywania problemów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci nie otrzymują e-maili z ankietami od Compari.ro, mimo że moduł jest skonfigurowany.**
O1:

- **Sprawdź WebApiKey:** Sprawdź dokładnie, czy Twój „Compari.ro WebApiKey” jest wprowadzony poprawnie i dokładnie tak, jak został dostarczony przez Compari.ro. Nawet pojedyncza literówka uniemożliwi działanie integracji.
- **Sprawdź ustawienie zgody:** Jeśli „Wymagaj zgody klienta” jest ustawione na „Tak”, upewnij się, że Twoi klienci testowi faktycznie zaznaczają pole zgody podczas realizacji zamówienia.
- **Sprawdź konto Compari.ro:** Zaloguj się na swoje konto sprzedawcy Compari.ro, aby sprawdzić, czy są jakieś komunikaty o błędach lub czy zamówienia są odbierane z Twojego sklepu.
- **Włącz logowanie:** Ustaw „Zapisuj błędy do log.txt” na „Tak” w konfiguracji modułu, złóż zamówienie testowe, a następnie sprawdź plik `compari/log.txt` pod kątem komunikatów o błędach. Zapewni to szczegółowe informacje techniczne.
- **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może zakłócać działanie. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.

**P2: Włączyłem „Wymagaj zgody klienta”, ale nie widzę pola wyboru podczas realizacji zamówienia.**
O2:

- **Kompatybilność z motywem:** Moduł używa standardowych hooków PrestaShop (`displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`) do wyświetlania pola wyboru zgody. Jeśli Twój niestandardowy motyw mocno modyfikuje proces realizacji zamówienia, te hooki mogą nie być renderowane lub stylizacja może sprawić, że pole wyboru będzie niewidoczne.
- **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**).
- **Pozycja modułu:** Upewnij się, że moduł nie jest wyłączony dla konkretnych hooków, których używa. Chociaż jest to mniej powszechne w przypadku pola wyboru zgody, warto to sprawdzić w **Wygląd > Pozycje**.

**P3: Co jeśli klient zmieni zdanie co do zgody po złożeniu zamówienia?**
O3: Moduł przetwarza zgodę w momencie złożenia zamówienia. Jeśli klient chce cofnąć zgodę na przyszłe ankiety, zazwyczaj musi to zrobić bezpośrednio w Compari.ro lub za pomocą ogólnych narzędzi do zarządzania danymi RODO w Twoim sklepie (jeśli je posiadasz). Sam moduł nie oferuje bezpośredniego „cofnięcia” dla poprzednich zamówień, ale integruje się z hookami RODO PrestaShop do usuwania i eksportowania danych.

**P4: Widzę, że plik `log.txt` staje się bardzo duży. Co powinienem zrobić?**
O4: Jeśli nie rozwiązujesz aktywnie problemów, ustaw opcję „Zapisuj błędy do log.txt” na „Nie” w konfiguracji modułu. Spowoduje to, że moduł przestanie zapisywać dalsze wpisy do pliku dziennika. Następnie możesz bezpiecznie usunąć plik `log.txt`, aby zwolnić miejsce.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla deweloperów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Compari` to prosty moduł PrestaShop, skupiający się głównie na integracji z zewnętrznym API (Compari.ro) w oparciu o zdarzenia zamówień. Przyjmuje standardową strukturę modułu PrestaShop, wykorzystując hooki do wstrzykiwania treści (zgoda RODO) i wyzwalania akcji (wysyłanie danych zamówienia). Nie wprowadza niestandardowych kontrolerów ani złożonych ObjectModels, opierając się na podstawowych danych `Order` i `Customer` PrestaShop. Główna logika znajduje się w pliku `compari.php`, obsługując konfigurację, instalację i wywołania zwrotne hooków.

### 4.2 Kontrolery (`controllers/`)

- Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front Office ani Back Office Admin. Cała logika jest obsługiwana w głównym pliku `compari.php` za pośrednictwem hooków.

### 4.3 Klasy i modele podstawowe (`classes/`)

- Ten moduł **nie** zawiera żadnych niestandardowych klas ani ObjectModels w katalogu `classes/`. Cała obsługa danych odbywa się bezpośrednio w pliku `compari.php` przy użyciu podstawowych encji PrestaShop `Order`, `Customer` i `Product`.

### 4.4 Zasoby JavaScript (`views/js/`)

- Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

- Ten moduł **nie** zawiera żadnych niestandardowych plików CSS. Stylizacja pola wyboru zgody ma być dziedziczona z motywu lub obsługiwana przez podstawową stylizację modułu RODO PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:
  - `compari/views/templates/hook/consent.tpl`:
    - **Hook:** `displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`
    - **Cel:** Renderuje pole wyboru zgody RODO i powiązany tekst, umożliwiając klientom wyrażenie zgody lub rezygnację z programu ankiet Compari.ro. Ten szablon jest renderowany tylko wtedy, gdy konfiguracja `COMPARI_CONSENT` jest włączona.
    - **Wynik:** Pole wejściowe typu checkbox z etykietą.
  - `compari/views/templates/hook/displayOrderConfirmation.tpl`:
    - **Hook:** `displayOrderConfirmation`
    - **Cel:** Ten szablon jest dołączony do hooka `displayOrderConfirmation`. Chociaż jest to plik szablonu, jego główną rolą jest wywołanie logiki backendowej w `hookDisplayOrderConfirmation` w `compari.php` w celu wysłania danych zamówienia do Compari.ro. Nie wyświetla widocznej treści użytkownikowi.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł **nie** tworzy żadnych niestandardowych tabel SQL.
  - Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration`:
    - `COMPARI_FILE_LOG`: Przechowuje wartość logiczną dla logowania błędów.
    - `COMPARI_ID`: Przechowuje WebApiKey Compari.ro.
    - `COMPARI_PRODUCT_ID`: Przechowuje wybrany typ identyfikatora produktu (np. `id_product`, `reference`).
    - `COMPARI_CONSENT`: Przechowuje wartość logiczną dla wymagania zgody klienta.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `install()` | Podczas instalacji modułu | Ustawia domyślne wartości konfiguracyjne, rejestruje hooki. |
| `uninstall()` | Podczas deinstalacji modułu | Usuwa wartości konfiguracyjne, wyrejestrowuje hooki. |
| `hookDisplayGDPRConsent` | Renderuje się na stronach, gdzie zbierana jest zgoda RODO (np. realizacja zamówienia) | Wyświetla pole wyboru zgody na udział w ankiecie Compari.ro. |
| `hookActionDeleteGDPRCustomer` | Gdy klient żąda usunięcia danych RODO | Obsługuje usuwanie wszelkich danych klienta związanych z Compari.ro (chociaż żadne nie są przechowywane bezpośrednio przez moduł, jest to hook zgodności). |
| `hookActionExportGDPRData` | Gdy klient żąda eksportu danych RODO | Obsługuje eksport wszelkich danych klienta związanych z Compari.ro (żadne nie są przechowywane bezpośrednio). |
| `hookDisplayOrderConfirmation` | Na stronie potwierdzenia zamówienia po udanym zakupie | Wyzwala wysyłanie danych zamówienia do Compari.ro, jeśli zgoda została udzielona (lub nie jest wymagana). |
| `hookDisplayPaymentTop` | Górna część kroku płatności w realizacji zamówienia | Alternatywny hook do wyświetlania pola wyboru zgody. |
| `hookDisplayCheckoutSummaryTop` | Górna część kroku podsumowania zamówienia | Alternatywny hook do wyświetlania pola wyboru zgody. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Compari.ro - program zaufanych zakupów, e-maile z ankietami”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań.
