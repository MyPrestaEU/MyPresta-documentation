---
title: "Karty podarunkowe - sprzedaż kodów voucherów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop „Karty podarunkowe - sprzedaż kodów voucherów” od MyPresta.eu."
sidebar:
  label: "Karty podarunkowe - sprzedaż kodów voucherów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Gift Cards - sell voucher codes na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/gift-cards-sell-voucher-codes.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/gift-cards-sell-voucher-codes/)
>
> ---


# Karty podarunkowe - sprzedaż kodów voucherów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Karty podarunkowe - sprzedaż kodów voucherów” oferuje kilka ekranów konfiguracyjnych do efektywnego zarządzania kartami podarunkowymi.

### 2.1 Główna strona konfiguracji modułu (Panel administracyjny > Moduły > Menedżer modułów > Konfiguruj Karty podarunkowe - sprzedaż kodów voucherów)

Jest to główny ekran konfiguracji modułu, na którym ustawiasz ogólne zachowanie i uzyskujesz dostęp do innych sekcji zarządzania.

-   **Co robi to ustawienie:** Ta sekcja zazwyczaj zawiera globalne ustawienia modułu, takie jak włączanie/wyłączanie funkcji, linkowanie do innych ekranów zarządzania i potencjalne ustawianie domyślnych zachowań dla kart podarunkowych.
-   **Wpływ zmiany tego ustawienia:** Zmiany tutaj wpłyną na sposób wyświetlania, zakupu i zarządzania kartami podarunkowymi w całym Twoim sklepie.
-   **Zalecana wartość:** Dokładnie przejrzyj każdą opcję. Ogólnie rzecz biorąc, włącz funkcje, których zamierzasz używać, i postępuj zgodnie z domyślnymi zaleceniami modułu, chyba że masz konkretny powód, aby je zmienić.
-   **Scenariusz/przykład dla sprzedawcy:** Możesz znaleźć tutaj ustawienie, aby włączyć dedykowany link „Karty podarunkowe” w stopce Twojego sklepu. Włączenie tego ułatwi klientom znajdowanie i kupowanie kart podarunkowych.

### 2.2 Zarządzanie grupami kart podarunkowych (Panel administracyjny > Karty podarunkowe > Grupy kart podarunkowych)

Ten ekran umożliwia definiowanie różnych kategorii lub grup dla Twoich kart podarunkowych. Pomyśl o nich jako o szablonach lub typach kart podarunkowych, które chcesz oferować.

-   **Nazwa ekranu i lokalizacja w menu:** **Panel administracyjny > Karty podarunkowe > Grupy kart podarunkowych**
-   **Dostępne działania i ustawienia:**
    *   **Tabela listująca:** Wyświetla wszystkie istniejące grupy kart podarunkowych. Zobaczysz kolumny takie jak Nazwa grupy, Wartość, Status (aktywna/nieaktywna) i działania (Edytuj, Usuń).
    *   **Dodaj nową grupę kart podarunkowych:** Kliknij ten przycisk, aby utworzyć nowy typ karty podarunkowej.
        *   **Nazwa grupy:** (np. „Karta podarunkowa na urodziny”, „Voucher świąteczny”, „Karta podarunkowa na każdą okazję”)
            *   *Co robi to ustawienie:* Jest to wewnętrzna nazwa Twojej grupy kart podarunkowych. Pomaga Ci organizować i identyfikować różne typy kart podarunkowych w Panelu administracyjnym.
            *   *Wpływ zmiany tego ustawienia:* Wpływa tylko na Twoją organizację w Panelu administracyjnym.
            *   *Zalecana wartość:* Opisowa i jasna.
        *   **Wartość:** (np. „25.00”, „50.00”, „100.00”)
            *   *Co robi to ustawienie:* Definiuje wartość pieniężną karty podarunkowej w tej grupie.
            *   *Wpływ zmiany tego ustawienia:* Jest to kwota, którą klienci zapłacą, a odbiorcy otrzymają jako kredyt.
            *   *Zalecana wartość:* Popularne, atrakcyjne nominały dla Twojego rynku docelowego.
        *   **Aktywna:** (przełącznik Tak/Nie)
            *   *Co robi to ustawienie:* Kontroluje, czy karty podarunkowe z tej grupy są dostępne do zakupu w Twoim sklepie.
            *   *Wpływ zmiany tego ustawienia:*
                *   *Gdy włączone:* Klienci mogą widzieć i kupować karty podarunkowe o tej wartości.
                *   *Gdy wyłączone:* Karty podarunkowe o tej wartości są ukryte w Front Office i nie można ich kupić.
            *   *Zalecana wartość:* TAK dla aktywnych kart podarunkowych, które chcesz sprzedawać.
        *   **Inne pola:** Mogą zawierać opcje dotyczące okresu ważności, minimalnego zakupu do realizacji lub specyficznych ograniczeń produktów.
            *   *Co robi to ustawienie:* Te pola pozwalają precyzyjnie dostosować warunki, na jakich karta podarunkowa może być używana.
            *   *Wpływ zmiany tego ustawienia:* Bezpośrednio wpływa na użyteczność i ograniczenia karty podarunkowej dla odbiorcy.
            *   *Zalecana wartość:* Ustaw zgodnie z polityką Twojej firmy (np. ważność 1 rok, brak minimalnego zakupu).
-   **Wpływ zmian:** Tworzenie nowych grup pozwala oferować różne nominały kart podarunkowych. Edycja grup zmienia wartość lub dostępność istniejących typów kart podarunkowych. Usunięcie grupy usuwa opcję zakupu tego konkretnego typu karty podarunkowej.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Zacznij od utworzenia kilku popularnych wartości kart podarunkowych (np. 25 zł, 50 zł, 100 zł).
    2.  W miarę rozwoju Twojej firmy lub w przypadku promocji sezonowych, dodawaj nowe grupy z różnymi wartościami lub określonymi okresami ważności.
    3.  Dezaktywuj grupy, których już nie chcesz sprzedawać, zamiast je usuwać, aby zachować dane historyczne.

### 2.3 Historia kart podarunkowych (Panel administracyjny > Karty podarunkowe > Historia kart podarunkowych)

Ten ekran zapewnia kompleksowy przegląd wszystkich zakupionych kart podarunkowych i ich aktualnego statusu.

-   **Nazwa ekranu i lokalizacja w menu:** **Panel administracyjny > Karty podarunkowe > Historia kart podarunkowych**
-   **Dostępne działania i ustawienia:**
    *   **Tabela listująca:** Wyświetla listę wszystkich wygenerowanych bonów podarunkowych. Kolumny zazwyczaj obejmują:
        *   **Kod vouchera:** Unikalny kod powiązany z kartą podarunkową.
        *   **Wartość początkowa:** Początkowa wartość karty podarunkowej.
        *   **Aktualne saldo:** Pozostałe saldo na karcie podarunkowej (jeśli częściowo wykorzystane).
        *   **E-mail odbiorcy:** Adres e-mail osoby, która otrzymała kartę podarunkową.
        *   **Imię nadawcy:** Imię osoby, która zakupiła kartę podarunkową.
        *   **ID zamówienia:** ID zamówienia, za pośrednictwem którego zakupiono kartę podarunkową.
        *   **Status:** (np. „Oczekujący”, „Aktywny”, „Wykorzystany”, „Wygasły”).
        *   **Działania:** Mogą obejmować opcje przeglądania szczegółów zamówienia, ponownego wysłania e-maila z kartą podarunkową lub ręcznej korekty salda (używać z ostrożnością).
    *   **Wyszukiwanie i filtrowanie:** Narzędzia do znajdowania konkretnych kart podarunkowych według kodu, e-maila, ID zamówienia lub statusu.
-   **Wpływ zmian:** Ten ekran służy głównie do monitorowania i zarządzania. Możesz śledzić wykorzystanie kart podarunkowych, identyfikować zaległe salda i pomagać klientom w ich zapytaniach dotyczących kart podarunkowych.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Regularnie sprawdzaj tę sekcję, aby monitorować sprzedaż i realizację kart podarunkowych.
    2.  Użyj funkcji wyszukiwania, aby szybko znaleźć kartę podarunkową, jeśli klient ma pytanie dotyczące jej salda lub statusu.
    3.  Jeśli klient zgłosi, że nie otrzymał e-maila z kartą podarunkową, możesz zweryfikować jej status i potencjalnie wysłać ją ponownie stąd.

### 2.4 Zarządzanie voucherami kart podarunkowych (Panel administracyjny > Karty podarunkowe > Vouchery kart podarunkowych)

Ten ekran jest przeznaczony do zarządzania indywidualnymi kodami voucherów generowanymi dla każdego zakupu karty podarunkowej.

-   **Nazwa ekranu i lokalizacja w menu:** **Panel administracyjny > Karty podarunkowe > Vouchery kart podarunkowych**
-   **Dostępne działania i ustawienia:**
    *   **Tabela listująca:** Pokazuje indywidualne kody voucherów podarunkowych. Kolumny mogą obejmować:
        *   **Kod vouchera:** Unikalny kod.
        *   **Powiązana grupa kart podarunkowych:** Do jakiego typu karty podarunkowej należy ten voucher.
        *   **Wartość:** Wartość tego konkretnego vouchera.
        *   **Klient:** Klient powiązany z voucherem (nadawca lub odbiorca).
        *   **Data dodania/wygenerowania:** Kiedy voucher został utworzony.
        *   **Status:** (np. „Aktywny”, „Wykorzystany”, „Wygasły”).
        *   **Działania:** Opcje przeglądania szczegółów, edycji (np. zmiana statusu, przedłużenie ważności) lub usunięcia (używać z niezwykłą ostrożnością, ponieważ usuwa to voucher).
-   **Wpływ zmian:** Ten ekran pozwala na szczegółową kontrolę nad indywidualnymi voucherami kart podarunkowych. Możesz ręcznie aktywować/dezaktywować vouchery, przedłużać ich ważność, a nawet modyfikować ich wartość, jeśli to konieczne (np. w przypadku problemów z obsługą klienta).
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Używaj tego ekranu do zaawansowanych zadań zarządzania, takich jak ręczne wystawianie karty podarunkowej jako gest dobrej woli lub rozwiązywanie konkretnych problemów klientów związanych z voucherem.
    2.  Zachowaj ostrożność podczas edytowania lub usuwania voucherów, ponieważ ma to bezpośredni wpływ na kredyt klienta.
    3.  Ten ekran zapewnia szczegółowy widok cyklu życia każdego vouchera.

### 2.5 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | *Ustawienia ogólne* | Różne | Globalne zachowanie modułu, opcje wyświetlania i linki do innych obszarów zarządzania. |
| **Grupy kart podarunkowych** | **Nazwa grupy** | Opisowa | Wewnętrzna nazwa typu karty podarunkowej. |
| | **Wartość** | Popularne nominały (np. 25 zł, 50 zł) | Wartość pieniężna karty podarunkowej. |
| | **Aktywna** | TAK | Kontroluje widoczność i możliwość zakupu typu karty podarunkowej. |
| | *Okres ważności* | Zgodnie z polityką | Definiuje, jak długo karta podarunkowa jest ważna po zakupie. |
| | *Min. zakup do realizacji* | Zgodnie z polityką | Ustawia minimalną wartość zamówienia, aby karta podarunkowa mogła być użyta. |
| **Historia kart podarunkowych** | *Kod vouchera* | N/D | Unikalny identyfikator dla każdej zakupionej karty podarunkowej. |
| | *Aktualne saldo* | N/D | Pozostały kredyt na karcie podarunkowej. |
| | *Status* | N/D | Śledzi cykl życia karty podarunkowej (Aktywna, Wykorzystana, Wygasła). |
| **Vouchery kart podarunkowych** | *Kod vouchera* | N/D | Unikalny identyfikator dla każdego wygenerowanego vouchera. |
| | *Status* | N/D | Śledzi stan indywidualnego vouchera. |
| | *Działania Edytuj/Usuń* | Używać z ostrożnością | Umożliwia ręczną modyfikację lub usunięcie indywidualnych voucherów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci nie mogą znaleźć kart podarunkowych w moim sklepie.**

-   **Odp.:** Po pierwsze, upewnij się, że utworzone „Grupy kart podarunkowych” są oznaczone jako „Aktywne” w Panelu administracyjnym w sekcji **Karty podarunkowe > Grupy kart podarunkowych**. Po drugie, sprawdź główną stronę konfiguracji modułu (Moduły > Menedżer modułów > Konfiguruj Karty podarunkowe - sprzedaż kodów voucherów) pod kątem opcji wyświetlania linków w nagłówku, stopce lub kolumnach. Jeśli Twój motyw ma niestandardowe zarządzanie menu, być może będziesz musiał ręcznie dodać link do strony kart podarunkowych (zazwyczaj dostępnej za pośrednictwem przyjaznego adresu URL, takiego jak `twojasklep.com/prezenty`).

**P2: Klient kupił kartę podarunkową, ale odbiorca nie otrzymał e-maila.**

-   **Odp.:** Przejdź do **Karty podarunkowe > Historia kart podarunkowych** w Panelu administracyjnym. Znajdź konkretną kartę podarunkową według ID zamówienia lub e-maila nadawcy/odbiorcy. Sprawdź jej status – powinna być „Aktywna” lub „Oczekująca”, jeśli jeszcze nie została użyta. Poszukaj opcji „Wyślij ponownie e-mail” dla tego konkretnego vouchera. Ponadto, doradź klientowi, aby sprawdził folder spam/śmieci. Upewnij się, że ustawienia e-mail Twojego sklepu (Zaawansowane > E-mail) są poprawnie skonfigurowane i że Twój serwer może niezawodnie wysyłać e-maile.

**P3: Rabat z karty podarunkowej nie jest stosowany podczas realizacji zamówienia.**

-   **Odp.:** Sprawdź następujące kwestie:
    1.  **Wprowadzanie kodu:** Upewnij się, że klient wprowadza poprawny, pełny kod karty podarunkowej bez literówek lub dodatkowych spacji.
    2.  **Ważność:** Sprawdź status karty podarunkowej w **Karty podarunkowe > Historia kart podarunkowych** lub **Karty podarunkowe > Vouchery kart podarunkowych**. Czy jest „Aktywna”? Czy wygasła? Czy pozostało saldo?
    3.  **Minimalny zakup:** Czy karta podarunkowa ma wymóg minimalnego zakupu, którego obecna suma koszyka nie spełnia?
    4.  **Ograniczenia produktów:** Czy istnieją jakieś kategorie produktów lub konkretne produkty wykluczone z użycia karty podarunkowej? (Byłoby to skonfigurowane w ustawieniach Grupy kart podarunkowych).
    5.  **Pamięć podręczna:** Czasami wyczyszczenie pamięci podręcznej PrestaShop (Zaawansowane > Wydajność) może rozwiązać problemy z wyświetlaniem lub funkcjonalnością.

**P4: Czy mogę dostosować szablon e-maila dla kart podarunkowych?**

-   **Odp.:** Tak, moduł zawiera menedżera szablonów e-mail. Powinieneś znaleźć opcje w konfiguracji modułu lub w dedykowanej sekcji (np. w **Karty podarunkowe > Szablony e-mail**) do edycji treści i wyglądu e-maila wysyłanego do odbiorców kart podarunkowych. Pozwala to na branding e-maila i włączenie konkretnych instrukcji lub wiadomości.

**P5: Co się stanie, jeśli suma zamówienia klienta jest mniejsza niż wartość karty podarunkowej?**

-   **Odp.:** Moduł jest zaprojektowany do obsługi tej sytuacji. Jeśli suma zamówienia jest mniejsza niż wartość karty podarunkowej, pozostałe saldo powinno pozostać na karcie podarunkowej, umożliwiając odbiorcy wykorzystanie go do przyszłych zakupów, dopóki saldo nie zostanie wyczerpane lub karta nie wygaśnie. Możesz zweryfikować pozostałe saldo w sekcji **Karty podarunkowe > Historia kart podarunkowych**.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla deweloperów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Karty podarunkowe - sprzedaż kodów voucherów” stosuje standardowy wzorzec PrestaShop MVC (Model-View-Controller), chociaż nie definiuje jawnie niestandardowych klas `ObjectModel` w katalogu `classes/`. Zamiast tego, wykorzystuje podstawową funkcjonalność `CartRule` (vouchera) PrestaShop i rozszerza możliwości administracyjne poprzez dedykowane `AdminController`y do zarządzania grupami kart podarunkowych, historią i indywidualnymi voucherami. Interakcja z Front Office jest obsługiwana przez `ModuleFrontController`y, głównie do wyświetlania kart podarunkowych i zarządzania kontami użytkowników. Moduł w dużym stopniu opiera się na systemie konfiguracji PrestaShop (`Configuration::get()`) dla swoich ustawień i integruje się z różnymi hookami w celu wyświetlania treści i zarządzania procesami zamówień.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front Office

-   `controllers/front/gifts.php`
    *   **Nazwa klasy i klasa nadrzędna**: `GiftcertificateGiftsModuleFrontController` rozszerzający `ModuleFrontController`
    *   **Odpowiedzialność**: Ten kontroler jest odpowiedzialny za wyświetlanie głównej strony kart podarunkowych w Front Office. Pobiera dostępne grupy kart podarunkowych i renderuje je za pomocą szablonu `gifts.tpl`, umożliwiając klientom przeglądanie i wybieranie kart podarunkowych do zakupu.
-   `controllers/front/index.php`
    *   **Nazwa klasy i klasa nadrzędna**: `GiftcertificateIndexModuleFrontController` rozszerzający `ModuleFrontController`
    *   **Odpowiedzialność**: Jest to kontroler zastępczy lub awaryjny, często używany do przekierowywania lub obsługi podstawowego routingu modułu. W wielu przypadkach może po prostu przekierowywać do kontrolera `gifts.php` lub służyć jako podstawa dla innych działań Front Office.

#### Kontrolery administracyjne Back Office

-   `controllers/admin/AdminGiftcertificateGroupController.php`
    *   **Nazwa zakładki i zarządzana encja**: „Grupy kart podarunkowych” (w głównym menu „Karty podarunkowe”). Zarządza encjami `gift_group`.
    *   **Odpowiedzialność**: Ten kontroler zapewnia interfejs do tworzenia, edytowania i usuwania grup kart podarunkowych. Obsługuje przesyłanie formularzy do definiowania wartości kart podarunkowych, nazw i innych ustawień specyficznych dla grupy. Wykorzystuje `HelperList` i `HelperForm` PrestaShop do renderowania siatki i formularzy.
-   `controllers/admin/AdminGiftcertificateHistoryController.php`
    *   **Nazwa zakładki i zarządzana encja**: „Historia kart podarunkowych” (w głównym menu „Karty podarunkowe”). Zarządza encjami `giftcertlist`.
    *   **Odpowiedzialność**: Ten kontroler wyświetla historyczny przegląd wszystkich zakupionych kart podarunkowych. Wyświetla kody voucherów, wartości, odbiorców i statusy. Umożliwia administratorom śledzenie wykorzystania kart podarunkowych i potencjalne ponowne wysyłanie e-maili. Wykorzystuje `HelperList` PrestaShop do widoku siatki i współdziała z kluczami konfiguracyjnymi, takimi jak `mowner`, `PS_SHOP_EMAIL`, `PS_SHOP_NAME` dla działań związanych z e-mailami.
-   `controllers/admin/AdminGiftcertificateVoucherController.php`
    *   **Nazwa zakładki i zarządzana encja**: „Vouchery kart podarunkowych” (w głównym menu „Karty podarunkowe”). Zarządza encjami `gift_voucher`.
    *   **Odpowiedzialność**: Ten kontroler zapewnia szczegółowe zarządzanie indywidualnymi kodami voucherów kart podarunkowych. Umożliwia administratorom przeglądanie, edytowanie (np. zmiana statusu, przedłużenie ważności) lub usuwanie konkretnych voucherów. Wykorzystuje `HelperList` i `HelperForm` PrestaShop do zarządzania indywidualnymi rekordami voucherów.
-   `controllers/admin/index.php`
    *   **Nazwa zakładki i zarządzana encja**: N/D
    *   **Odpowiedzialność**: Ten plik zazwyczaj służy jako środek bezpieczeństwa, aby zapobiec bezpośredniemu listowaniu lub dostępowi do katalogu. Zazwyczaj zawiera proste `header('Location: ../../../index.php'); exit;` lub podobne, aby przekierować do głównego panelu administracyjnego PrestaShop.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Sugeruje to, że moduł:

1.  Bezpośrednio manipuluje tabelami bazy danych za pomocą `Db::getInstance()` bez `ObjectModel`s.
2.  Opiera się na podstawowej klasie `CartRule` (voucher) PrestaShop dla rzeczywistej logiki vouchera, a jego własne kontrolery administracyjne zarządzają aspektem „karty podarunkowej” jako opakowaniem wokół tworzenia i zarządzania `CartRule`.
3.  Główny plik modułu (`ajax_giftcertificate.php`) lub jego dołączone biblioteki zawierają podstawową logikę i obsługę danych.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `giftcertificate/js/script.js`
    *   **Zakres**: Prawdopodobnie Front Office lub ogólna funkcjonalność modułu.
    *   **Szczegóły**: Zawiera ogólny kod JavaScript dla modułu, potencjalnie obsługujący żądania AJAX dotyczące dodawania kart podarunkowych do koszyka, dynamiczne aktualizacje na stronie kart podarunkowych lub walidacje formularzy Front Office.
-   `giftcertificate/lib/emailTemplatesManager/js/emailTemplatesManager.js`
    *   **Zakres**: Back Office (Admin).
    *   **Szczegóły**: Zarządza funkcjonalnością edycji i tworzenia szablonów e-mail w konfiguracji modułu. Obejmuje to obsługę przesyłania formularzy, wywołań AJAX do zapisywania szablonów i potencjalnie integracje z edytorami tekstu sformatowanego.
-   `giftcertificate/lib/pdfTemplatesManager/js/pdfTemplatesManager.js`
    *   **Zakres**: Back Office (Admin).
    *   **Szczegóły**: Podobnie jak menedżer szablonów e-mail, ale dla szablonów PDF, prawdopodobnie używanych do generowania drukowalnych kart podarunkowych. Obsługuje interakcje z formularzami, zapisywanie projektów szablonów PDF i funkcjonalność podglądu.
-   `giftcertificate/lib/searchTool/views/js/autocomplete.js`
    *   **Zakres**: Back Office (Admin).
    *   **Szczegóły**: Zapewnia funkcjonalność autouzupełniania dla pól wyszukiwania w kontrolerach administracyjnych, takich jak wyszukiwanie klientów lub produktów podczas tworzenia/edycji kart podarunkowych lub voucherów.
-   `giftcertificate/lib/voucherengine/script.js`
    *   **Zakres**: Prawdopodobnie Front Office lub ogólna funkcjonalność modułu.
    *   **Szczegóły**: Zawiera kod JavaScript specyficzny dla logiki generowania i realizacji voucherów, potencjalnie współdziałający z koszykiem lub procesem realizacji zamówienia w celu zastosowania rabatów z kart podarunkowych.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `giftcertificate/css.css`
    *   **Zakres**: Ogólny, może być Front Office lub Back Office.
    *   **Szczegóły**: Zawiera podstawowe style dla elementów modułu, potencjalnie obejmujące ogólny układ, style przycisków lub wspólne komponenty.
-   `giftcertificate/lib/emailTemplatesManager/css/emailTemplatesManager.css`
    *   **Zakres**: Back Office (Admin).
    *   **Szczegóły**: Style dla interfejsu zarządzania szablonami e-mail, zapewniające spójny wygląd w panelu administracyjnym PrestaShop.
-   `giftcertificate/lib/pdfTemplatesManager/css/pdfTemplatesManager.css`
    *   **Zakres**: Back Office (Admin).
    *   **Szczegóły**: Style dla interfejsu zarządzania szablonami PDF, podobnie jak menedżer szablonów e-mail.
-   `giftcertificate/lib/searchTool/views/css/autocomplete.css`
    *   **Zakres**: Back Office (Admin).
    *   **Szczegóły**: Stylizacja dla wyników wyszukiwania autouzupełniania i pól wprowadzania.
-   `giftcertificate/lib/voucherengine/ps16.css`
    *   **Zakres**: Front Office (specjalnie dla motywów PrestaShop 1.6).
    *   **Szczegóły**: Zawiera style kompatybilności dla motywów PrestaShop 1.6, uwzględniające potencjalne różnice w układzie lub elementach, aby zapewnić prawidłowe wyświetlanie komponentów kart podarunkowych.
-   `giftcertificate/views/css/giftcertificate.css`
    *   **Zakres**: Front Office (widoczne dla klienta).
    *   **Szczegóły**: Główny arkusz stylów dla wyświetlania kart podarunkowych w Front Office, w tym dedykowanej strony kart podarunkowych, elementów strony produktu i potencjalnie stylizacji sekcji „Moje konto”. Deweloperzy mogą nadpisać te klasy w pliku `custom.css` swojego motywu lub motywu potomnego.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `giftcertificate/views/templates/hook/displayAdminOrder.tpl`
    *   **Hook**: `displayAdminOrder`
    *   **Wyjście**: Renderuje informacje związane z kartami podarunkowymi na stronie szczegółów zamówienia PrestaShop w Back Office. Może to pokazywać, które karty podarunkowe zostały zakupione w zamówieniu lub które karty podarunkowe zostały użyte do opłacenia zamówienia.
-   `giftcertificate/views/templates/hook/displayMyAccountBlock.tpl`
    *   **Hook**: `displayMyAccountBlock` (PrestaShop 1.6)
    *   **Wyjście**: Dodaje link lub blok do strony „Moje konto” klienta, kierując go do zakupionych kart podarunkowych lub historii kart podarunkowych.
-   `giftcertificate/views/templates/hook/my-account-16.tpl`
    *   **Hook**: `displayCustomerAccount` (PrestaShop 1.6)
    *   **Wyjście**: Specyficzny szablon do dodawania linku do strony „Moje konto” dla motywów PrestaShop 1.6.
-   `giftcertificate/views/templates/hook/my-account-17.tpl`
    *   **Hook**: `displayCustomerAccount` (PrestaShop 1.7+)
    *   **Wyjście**: Specyficzny szablon do dodawania linku do strony „Moje konto” dla motywów PrestaShop 1.7 i nowszych.
-   `giftcertificate/views/templates/hook/my-account.tpl`
    *   **Hook**: `displayCustomerAccount` (Ogólny/Awaryjny)
    *   **Wyjście**: Ogólny szablon linku „Moje konto”, potencjalnie używany jako awaryjny lub dla starszych wersji.

#### Szablony administracyjne (`views/templates/admin/`)

-   `giftcertificate/views/templates/admin/admin.tpl`
    *   **Zakres**: Ogólna konfiguracja administracyjna.
    *   **Wyjście**: Prawdopodobnie główny formularz konfiguracji modułu, renderowany za pomocą `getContent()` w głównym pliku modułu. Może zawierać zakładki lub sekcje dla różnych ustawień.
-   `giftcertificate/views/templates/admin/adminOrder.tpl`
    *   **Zakres**: Widok zamówienia administracyjnego.
    *   **Wyjście**: Podobnie jak `displayAdminOrder.tpl`, ale potencjalnie dla bardziej zintegrowanego widoku w ramach niestandardowej strony zamówienia administracyjnego, jeśli moduł ją nadpisuje lub rozszerza.
-   `giftcertificate/views/templates/admin/list/list_action_email.tpl`
    *   **Zakres**: Widoki list administracyjnych (np. Historia kart podarunkowych).
    *   **Wyjście**: Specyficzny przycisk akcji lub link do wysyłania e-maili, zazwyczaj znajdujący się w kolumnie akcji tabeli `HelperList`, umożliwiający administratorom ponowne wysyłanie e-maili z kartami podarunkowymi.

#### Szablony Front Office (`views/templates/front/`)

-   `giftcertificate/views/templates/front/gifts.tpl`
    *   **Zakres**: Dedykowana strona Front Office.
    *   **Wyjście**: Główny szablon do wyświetlania listy dostępnych kart podarunkowych klientom, renderowany przez `GiftcertificateGiftsModuleFrontController`.

#### Szablony bibliotek (`lib/`)

-   `giftcertificate/lib/emailTemplatesManager/views/*.tpl`
    *   **Zakres**: Back Office (Admin).
    *   **Wyjście**: Szablony dla interfejsu zarządzania szablonami e-mail (np. `buttonManager.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`).
-   `giftcertificate/lib/helpers/views/orderStates.tpl`
    *   **Zakres**: Back Office (Admin).
    *   **Wyjście**: Szablon pomocniczy, prawdopodobnie do wyświetlania lub wybierania statusów zamówień w konfiguracjach modułów lub formularzach.
-   `giftcertificate/lib/pdfTemplatesManager/views/*.tpl`
    *   **Zakres**: Back Office (Admin).
    *   **Wyjście**: Szablony dla interfejsu zarządzania szablonami PDF (np. `buttonManager.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`).
-   `giftcertificate/lib/searchTool/views/scripts.tpl`
    *   **Zakres**: Back Office (Admin).
    *   **Wyjście**: Zawiera logikę JavaScript lub Smarty związaną z narzędziem wyszukiwania, potencjalnie obejmującą skrypty inicjalizacyjne dla autouzupełniania.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł prawdopodobnie tworzy niestandardowe tabele do zarządzania swoimi danymi, chociaż nie znaleziono jawnych definicji `ObjectModel` w `classes/`. Na podstawie kontrolerów administracyjnych, implikowane są następujące tabele:

-   `ps_gift_group`: Przechowuje definicje grup kart podarunkowych (np. wartość, nazwa, ważność, ograniczenia).
-   `ps_giftcertlist`: Przechowuje historię zakupionych kart podarunkowych, w tym ich unikalne kody, wartość początkową, aktualne saldo, odbiorcę, nadawcę i powiązane zamówienie.
-   `ps_gift_voucher`: Przechowuje szczegóły indywidualnych kodów voucherów, potencjalnie łącząc się z `ps_cart_rule`, jeśli wykorzystuje natywny system voucherów PrestaShop.

Rekordy konfiguracyjne przechowywane w `ps_configuration` obejmowałyby:

-   Ustawienia specyficzne dla modułu skonfigurowane za pomocą `getContent()`, takie jak ID szablonów e-mail, ID szablonów PDF, opcje wyświetlania itp.
-   `mowner`, `PS_SHOP_EMAIL`, `PS_SHOP_NAME` to podstawowe konfiguracje PrestaShop używane przez moduł do wysyłania e-maili.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykiwanie zasobów CSS/JS, metatagów lub danych specyficznych dla modułu. |
| `displayLeftColumn` / `displayRightColumn` | W lewej/prawej kolumnie Front Office. | Wyświetlanie bloku promocji kart podarunkowych lub linku do strony kart podarunkowych. |
| `displayProductAdditionalInfo` / `displayProductButtons` | Na stronie produktu. | Potencjalne wyświetlanie przycisku „Kup kartę podarunkową” lub powiązanych informacji. |
| `displayFooter` | W sekcji stopki każdej strony. | Dodawanie linku do strony kart podarunkowych. |
| `displayCustomerAccount` | Na stronie „Moje konto” klienta. | Dodawanie linku do historii/szczegółów kart podarunkowych klienta. |
| `displayMyAccountBlock` | Na stronie „Moje konto” klienta (specyficzne dla PrestaShop 1.6). | Dodawanie linku do historii/szczegółów kart podarunkowych klienta. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Wyzwalanie generowania i wysyłania voucherów kart podarunkowych, gdy produkt karty podarunkowej zostanie zakupiony. Aktualizacja historii kart podarunkowych. |
| `displayAdminOrder` | Na stronie szczegółów zamówienia w Back Office. | Wyświetlanie informacji o karcie podarunkowej związanych z zamówieniem (zakupione lub użyte). |
| `actionOrderStatusUpdate` | Gdy status zamówienia się zmienia. | Potencjalne aktywowanie/dezaktywowanie kart podarunkowych na podstawie statusu zamówienia (np. aktywacja po „Płatność zaakceptowana”). |
| `actionFrontControllerSetMedia` | Przed renderowaniem szablonu przez kontroler Front Office. | Ładowanie zasobów CSS i JavaScript specyficznych dla Front Office. |
| `actionAdminControllerSetMedia` | Przed renderowaniem szablonu przez kontroler administracyjny. | Ładowanie zasobów CSS i JavaScript specyficznych dla Back Office. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i upewnienia się, że używasz najnowszej, najbezpieczniejszej wersji modułu „Karty podarunkowe - sprzedaż kodów voucherów”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnianie terminowej pomocy i ciągłych ulepszeń naszych modułów.
"""
