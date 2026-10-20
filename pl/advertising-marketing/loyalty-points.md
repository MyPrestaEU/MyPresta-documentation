---
title: "Punkty lojalnościowe - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów modułu punktów lojalnościowych PrestaShop od MyPresta.eu."
sidebar:
  label: "Punkty lojalnościowe - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Loyalty points na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/loyalty-points/)
>
> ---


# Punkty lojalnościowe

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Aby uzyskać dostęp do konfiguracji modułu, przejdź do **Moduły > Menedżer modułów** w panelu administracyjnym PrestaShop, wyszukaj „Punkty lojalnościowe” i kliknij przycisk „Konfiguruj”.

Ten ekran pozwala zdefiniować podstawowe zasady Twojego programu lojalnościowego.

#### **Kurs wymiany punktów lojalnościowych**

- **Co robi to ustawienie:** To kluczowe ustawienie określa, ile punktów lojalnościowych klient zdobywa za określoną kwotę pieniędzy wydaną w Twoim sklepie. Jest to podstawa Twojego programu lojalnościowego.
- **Wpływ zmiany tego ustawienia:**
  - *Jeśli ustawiono „1 punkt za każde 10 € wydane”*: Klient wydający 50 € zdobędzie 5 punktów.
  - *Jeśli ustawiono „1 punkt za każde 5 € wydane”*: Klient wydający 50 € zdobędzie 10 punktów.
  - Wyższa wartość (np. 10 €) oznacza, że klienci zdobywają punkty wolniej, podczas gdy niższa wartość (np. 1 €) oznacza, że zdobywają punkty szybciej.
- **Zalecana wartość:** Zależy to od Twoich marż zysku i pożądanej zachęty dla klienta. Częstym punktem wyjścia jest „1 punkt za każde 10 € wydane” lub „1 punkt za każde 5 € wydane”.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja średnia wartość zamówienia wynosi 50 € i chcesz, aby klienci szybko czuli się nagradzani, „1 punkt za każde 5 € wydane” może być lepsze. Jeśli Twoje marże są niższe, „1 punkt za każde 10 € wydane” może być bardziej zrównoważone.

#### **Wartość punktów lojalnościowych**

- **Co robi to ustawienie:** To ustawienie określa wartość pieniężną każdego punktu lojalnościowego, gdy klient zdecyduje się zamienić je na kupon rabatowy.
- **Wpływ zmiany tego ustawienia:**
  - *Jeśli ustawiono „1 punkt = 0,10 €”*: Klient posiadający 100 punktów może otrzymać kupon o wartości 10 €.
  - *Jeśli ustawiono „1 punkt = 0,05 €”*: Klient posiadający 100 punktów może otrzymać kupon o wartości 5 €.
  - Wyższa wartość sprawia, że punkty są bardziej atrakcyjne i wartościowe dla klienta, ale kosztuje Twój sklep więcej w postaci rabatów.
- **Zalecana wartość:** Powinna być zrównoważona z „Kursem wymiany punktów lojalnościowych”, aby program był zarówno atrakcyjny dla klientów, jak i finansowo opłacalny dla Twojej firmy. Częstym stosunkiem jest to, że 10 punktów (zdobytych za wydanie 100 €, jeśli kurs wynosi 1 punkt za 10 €) jest warte 1 €.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli dajesz 1 punkt za każde 10 € wydane, a 1 punkt jest wart 0,10 €, to klient wydający 100 € otrzymuje 10 punktów, które można wymienić na kupon o wartości 1 €. Oznacza to, że otrzymuje 1% zniżki na swoje zakupy. Możesz zwiększyć to do 2% lub 3%, aby być bardziej konkurencyjnym.

#### **Minimalna liczba punktów do konwersji**

- **Co robi to ustawienie:** Określa minimalną liczbę punktów lojalnościowych, jaką klient musi zgromadzić, zanim będzie mógł je zamienić na kupon rabatowy.
- **Wpływ zmiany tego ustawienia:**
  - *Jeśli ustawiono „50 punktów”*: Klienci nie mogą wymieniać punktów, dopóki nie będą mieli co najmniej 50.
  - *Jeśli ustawiono „10 punktów”*: Klienci mogą wymieniać punkty znacznie szybciej.
  - Wyższa minimalna wartość zachęca klientów do dokonywania większej liczby zakupów, aby osiągnąć próg, potencjalnie zwiększając ich wartość życiową. Niższa minimalna wartość oferuje szybszą gratyfikację.
- **Zalecana wartość:** Ustaw wartość, która zachęca do ponownych zakupów, ale nie jest tak wysoka, aby klienci czuli, że jest nieosiągalna. 50-100 punktów to dobry zakres początkowy, w zależności od Twojej stawki zdobywania punktów.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli 1 punkt jest zdobywany za każde 10 €, a potrzeba 50 punktów, klient musi wydać 500 €, aby otrzymać swój pierwszy kupon. Zapewnia to, że jest on zaangażowanym klientem, zanim otrzyma znaczną zniżkę.

#### **Ważność kuponu (dni)**

- **Co robi to ustawienie:** Określa, ile dni będzie ważny kupon rabatowy wygenerowany z punktów lojalnościowych.
- **Wpływ zmiany tego ustawienia:**
  - *Jeśli ustawiono „30 dni”*: Kupon wygasa 30 dni po jego wygenerowaniu.
  - *Jeśli ustawiono „365 dni”*: Kupon jest ważny przez cały rok.
  - Krótszy okres ważności zachęca klientów do szybszego wykorzystania kuponu, co prowadzi do szybszych ponownych zakupów. Dłuższy okres oferuje większą elastyczność, ale może opóźniać zakupy.
- **Zalecana wartość:** Od 30 do 90 dni to typowy zakres. Tworzy to poczucie pilności, nie będąc nadmiernie restrykcyjnym.
- **Scenariusz / przykład dla sprzedawcy:** 60-dniowy okres ważności daje klientom wystarczająco dużo czasu na znalezienie czegoś, co chcą kupić, nie pozwalając kuponowi leżeć niewykorzystanemu w nieskończoność.

#### **Włącz program lojalnościowy**

- **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania całego programu punktów lojalnościowych.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączony (TAK):* Program lojalnościowy jest aktywny. Klienci będą zdobywać punkty, widzieć informacje o punktach na stronach produktów i w koszyku oraz zarządzać punktami na swoim koncie.
  - *Gdy wyłączony (NIE):* Program lojalnościowy jest nieaktywny. Nie będą zdobywane żadne punkty, nie będą wyświetlane żadne informacje o punktach, a klienci nie będą mogli wymieniać punktów. Istniejące punkty zostaną zachowane, ale będą niedostępne, dopóki program nie zostanie ponownie włączony.
- **Zalecana wartość:** TAK, po skonfigurowaniu wszystkich innych ustawień.
- **Scenariusz / przykład dla sprzedawcy:** Możesz tymczasowo wyłączyć go w celu konserwacji lub jeśli prowadzisz inną kampanię promocyjną, która koliduje z programem lojalnościowym.

#### **Wyświetl punkty lojalnościowe na stronie produktu**

- **Co robi to ustawienie:** Kontroluje, czy informacja o punktach lojalnościowych zdobytych za produkt jest wyświetlana na poszczególnych stronach produktów w Twoim sklepie.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączony (TAK):* Klienci zobaczą tekst typu „Zdobądź X punktów z tym zakupem” na każdej stronie produktu.
  - *Gdy wyłączony (NIE):* Ta informacja nie pojawi się na stronach produktów.
- **Zalecana wartość:** TAK. Wyświetlanie tych informacji w widocznym miejscu pomaga klientom zrozumieć propozycję wartości Twojego programu lojalnościowego i zachęca do zakupów.
- **Scenariusz / przykład dla sprzedawcy:** Utrzymywanie tego włączonego zapewnia, że klienci są zawsze świadomi nagród, które mogą zdobyć, co może być decydującym czynnikiem przy zakupie.

#### **Wyświetl punkty lojalnościowe w koszyku**

- **Co robi to ustawienie:** Kontroluje, czy całkowita liczba punktów lojalnościowych do zdobycia za bieżące zamówienie jest wyświetlana w podsumowaniu koszyka.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączony (TAK):* Klienci zobaczą podsumowanie punktów, które zdobędą za zawartość swojego bieżącego koszyka.
  - *Gdy wyłączony (NIE):* Ta informacja nie pojawi się w koszyku.
- **Zalecana wartość:** TAK. Służy to jako ostateczna zachęta przed finalizacją zakupu, przypominając klientom o przyszłych korzyściach z ich zakupu.
- **Scenariusz / przykład dla sprzedawcy:** Wyświetlanie punktów w koszyku może zmniejszyć liczbę porzuconych koszyków, dodając kolejną warstwę wartości do zakupu, zwłaszcza jeśli klient waha się.

#### **Opis programu punktów lojalnościowych**

- **Co robi to ustawienie:** Pozwala na podanie niestandardowego opisu lub wyjaśnienia Twojego programu lojalnościowego. Ten tekst będzie zazwyczaj wyświetlany w sekcji „Moje konto” klienta, gdzie zarządza on swoimi punktami.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy wypełniony tekstem:* Klienci zobaczą Twoją niestandardową wiadomość wyjaśniającą, jak działa program, jego korzyści lub wszelkie specyficzne zasady.
  - *Gdy pozostawiony pusty:* Nie zostanie wyświetlony żaden niestandardowy opis, potencjalnie pozostawiając klientów z mniejszą ilością informacji.
- **Zalecana wartość:** Podaj jasny, zwięzły i angażujący opis. Wyjaśnij, jak zdobywa się punkty, ich wartość i jak je wymieniać.
- **Scenariusz / przykład dla sprzedawcy:** „Zdobądź 1 punkt za każde wydane 10 €! Zbierz 50 punktów i otrzymaj kupon o wartości 5 € na następny zakup. To nasz sposób na podziękowanie za bycie lojalnym klientem!”

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Kurs wymiany punktów lojalnościowych | 1 punkt za każde 10 € wydane | Określa, ile punktów jest zdobywanych za jednostkę waluty. |
| Konfiguracja modułu | Wartość punktów lojalnościowych | 1 punkt = 0,10 € | Określa wartość pieniężną każdego punktu po zamianie na kupon. |
| Konfiguracja modułu | Minimalna liczba punktów do konwersji | 50 punktów | Ustawia minimalną liczbę punktów wymaganą, zanim klient będzie mógł je wymienić na kupon. |
| Konfiguracja modułu | Ważność kuponu (dni) | 60 dni | Jak długo wygenerowany kupon jest ważny. |
| Konfiguracja modułu | Włącz program lojalnościowy | TAK | Główny przełącznik do włączania/wyłączania całego programu lojalnościowego. |
| Konfiguracja modułu | Wyświetl punkty lojalnościowe na stronie produktu | TAK | Pokazuje informacje o zdobywaniu punktów na poszczególnych stronach produktów. |
| Konfiguracja modułu | Wyświetl punkty lojalnościowe w koszyku | TAK | Pokazuje całkowitą liczbę punktów do zdobycia w podsumowaniu koszyka. |
| Konfiguracja modułu | Opis programu punktów lojalnościowych | Niestandardowy tekst | Dostarcza klientom szczegółowe wyjaśnienie programu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moi klienci nie widzą informacji o punktach lojalnościowych na stronach produktów ani w koszyku. Co jest nie tak?**
O:

1.  **Sprawdź „Włącz program lojalnościowy”:** Upewnij się, że to ustawienie jest ustawione na TAK w konfiguracji modułu.
2.  **Sprawdź ustawienia wyświetlania:** Zweryfikuj, czy „Wyświetl punkty lojalnościowe na stronie produktu” i „Wyświetl punkty lojalnościowe w koszyku” są ustawione na TAK.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami zmiany nie pojawiają się, dopóki pamięć podręczna nie zostanie odświeżona.
4.  **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany z myślą o kompatybilności, niestandardowe motywy mogą czasami nadpisywać domyślne hooki wyświetlania. Jeśli wyczyszczenie pamięci podręcznej nie działa, skontaktuj się z pomocą techniczną MyPresta.eu.

**P: Klienci zdobywają punkty, ale nie mogą ich zamienić na kupony.**
O:

1.  **Sprawdź „Minimalna liczba punktów do konwersji”:** Upewnij się, że klient zgromadził co najmniej liczbę punktów określoną w tym ustawieniu. Jeśli minimum wynosi 50, a ma tylko 45, nie zobaczy opcji konwersji.
2.  **Proces generowania kuponu:** Poprowadź swoich klientów do sekcji „Moje konto”, a następnie do sekcji „Moje punkty lojalnościowe” (lub podobnej), gdzie powinni znaleźć opcję zamiany punktów na kupon.

**P: Klient wygenerował kupon, ale nie działa on lub zniknął.**
O:

1.  **Sprawdź „Ważność kuponu (dni)”:** Kupon mógł wygasnąć, jeśli klient zbyt długo czekał z jego użyciem.
2.  **Kod kuponu:** Upewnij się, że klient poprawnie wprowadza kod kuponu podczas finalizacji zakupu.
3.  **Status kuponu:** W panelu administracyjnym PrestaShop przejdź do **Katalog > Rabaty > Reguły koszyka**. Wyszukaj wygenerowany kod kuponu. Sprawdź daty ważności, minimalną kwotę i czy został już użyty.

**P: Czy mogę ręcznie dodawać lub usuwać punkty lojalnościowe dla klienta?**
O: Obecna wersja modułu nie zapewnia bezpośredniego interfejsu w panelu administracyjnym do ręcznej regulacji punktów lojalnościowych klienta. Punkty są automatycznie obliczane na podstawie zamówień. Jeśli musisz dokonać ręcznych korekt, być może będziesz musiał rozważyć niestandardowe rozwiązanie lub skontaktować się z pomocą techniczną MyPresta.eu w celu uzyskania zaawansowanych opcji.

**P: Opis programu lojalnościowego nie wyświetla się poprawnie w wielu językach.**
O: Podczas ustawiania „Opisu programu punktów lojalnościowych” upewnij się, że używasz selektora języka w prawym górnym rogu pola tekstowego, aby dostarczyć tłumaczenia dla wszystkich języków włączonych w Twoim sklepie. Jeśli wprowadzisz tekst tylko w jednym języku, pojawi się on tylko w tym języku.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Loyalty points` (`myprestaloyalty`) stosuje standardową architekturę modułu PrestaShop, wykorzystując głównie klasę `Module` do swojej podstawowej funkcjonalności i konfiguracji. Integruje się z front-office poprzez różne hooki, aby wyświetlać informacje o lojalności, i zapewnia dedykowaną stronę konta klienta do zarządzania punktami. Moduł nie wprowadza niestandardowych tabel baz danych ani klas `ObjectModel`, opierając się na `Configuration` PrestaShop dla ustawień i potencjalnie rozszerzając istniejące dane klienta lub zamówienia poprzez hooki.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `myprestaloyalty/controllers/front/default.php`
        -   **Nazwa klasy i klasa nadrzędna**: `MyPrestaLoyaltyDefaultModuleFrontController` rozszerzający `ModuleFrontController`.
        -   **Odpowiedzialność**: Ten kontroler prawdopodobnie służy jako rezerwowy lub ogólny punkt wejścia dla akcji front-office związanych z modułem. Może obsługiwać początkowe żądania lub przekierowania, jeśli bardziej specyficzny kontroler nie zostanie znaleziony. Biorąc pod uwagę kontroler `index.php`, `default.php` może być mniej krytyczny lub służyć do konkretnego, mniej powszechnego celu.
    -   `myprestaloyalty/controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: `MyPrestaLoyaltyIndexModuleFrontController` rozszerzający `ModuleFrontController`.
        -   **Odpowiedzialność**: Jest to główny kontroler front-office dla modułu. Odpowiada za wyświetlanie informacji o punktach lojalnościowych klienta i obsługę logiki konwersji punktów na kupony. Prawdopodobnie pobiera aktualne punkty klienta, oblicza potencjalne wartości kuponów i przetwarza żądanie generowania kuponu. Renderuje szablon `loyalty.tpl`.
-   **Kontrolery administracyjne Back-Office**: Brak zidentyfikowanych. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównego modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

W dostarczonym spisie modułów nie zidentyfikowano żadnych niestandardowych klas ani modeli (rozszerzeń `ObjectModel`). Moduł prawdopodobnie zarządza logiką punktów lojalnościowych bezpośrednio w głównym pliku `myprestaloyalty.php` i poprzez `Configuration` PrestaShop dla ustawień.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `myprestaloyalty/views/js/admin_manual_customer_search.js`
    -   **Zakres**: Back-office.
    -   **Opis**: Ten skrypt sugeruje funkcjonalność wyszukiwania klientów ręcznie w panelu administracyjnym. Chociaż nie wymieniono wyraźnie żadnych kontrolerów administracyjnych, ten plik JS sugeruje, że może istnieć interfejs administracyjny (być może zintegrowany z istniejącą stroną PrestaShop lub niestandardowym formularzem w `getContent()`), gdzie administrator może wyszukiwać klientów, prawdopodobnie w celu przeglądania lub zarządzania ich punktami lojalnościowymi (chociaż bezpośrednia modyfikacja punktów nie jest potwierdzona w opisie modułu). Prawdopodobnie używa AJAX do pobierania danych klienta.
-   `myprestaloyalty/views/js/myprestaloyalty.js`
    -   **Zakres**: Front-office.
    -   **Opis**: Jest to główny skrypt JavaScript front-office dla modułu. Prawdopodobnie obsługuje dynamiczne interakcje na stronie lojalnościowej klienta (`loyalty.tpl`), takie jak:
        -   Wyświetlanie aktualnych punktów i potencjalnych wartości kuponów.
        -   Obsługa zdarzenia kliknięcia przycisku „Zamień punkty na kupon”.
        -   Wykonywanie żądań AJAX do kontrolera front-office `index.php` w celu przetworzenia generowania kuponu.
        -   Aktualizacja interfejsu użytkownika w celu wyświetlenia nowo wygenerowanego kodu kuponu lub komunikatów o sukcesie/błędzie.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `myprestaloyalty/views/css/myprestaloyalty.css`
    -   **Zakres**: Front-office (i potencjalnie niektóre elementy back-office, jeśli używane są wspólne style).
    -   **Opis**: Ten arkusz stylów zapewnia wizualne style dla komponentów front-office modułu. Obejmuje to:
        -   Wyświetlanie punktów lojalnościowych na stronach produktów.
        -   Podsumowanie punktów w koszyku.
        -   Układ i styl sekcji „Moje punkty lojalnościowe” na koncie klienta, w tym saldo punktów, historia i formularz generowania kuponów.
        -   Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim motywie: Szukaj klas z prefiksem `myprestaloyalty-` lub podobnych, takich jak `.myprestaloyalty-product-points`, `.myprestaloyalty-cart-summary`, `.myprestaloyalty-account-section`, `.myprestaloyalty-voucher-form` itp.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `myprestaloyalty/views/templates/admin/advert.tpl`
        -   **Opis**: Ten szablon jest prawdopodobnie używany do wyświetlania treści promocyjnych lub reklam z MyPresta.eu na stronie konfiguracji modułu w back-office. Jest to powszechna praktyka dla twórców modułów, aby uwzględniać takie elementy.
    -   `myprestaloyalty/views/templates/admin/_configure/helpers/form/form.tpl`
        -   **Opis**: Ten szablon jest standardowym szablonem pomocniczym PrestaShop używanym do renderowania formularza konfiguracji modułu. Nie jest on unikalny dla tego modułu, ale jest dołączony, aby zapewnić poprawne renderowanie strony konfiguracji (`getContent()`), potencjalnie z niestandardowymi polami lub specyficznym stylem.
-   **Szablony front-office (`views/templates/front/`)**:

    -   `myprestaloyalty/views/templates/front/loyalty.tpl`
        -   **Opis**: Jest to główny szablon dla dedykowanej strony klienta „Moje punkty lojalnościowe”, renderowany przez `MyPrestaLoyaltyIndexModuleFrontController`. Wyświetla aktualne saldo punktów klienta, historię zdobytych i wydanych punktów oraz interfejs do konwersji punktów na kupony rabatowe.
-   **Szablony hooków (`views/templates/hook/`)**:

    -   `myprestaloyalty/views/templates/hook/my-account.tpl`
        -   **Hook**: `displayCustomerAccount` (lub podobny, np. `displayMyAccountBlock`).
        -   **Opis**: Ten szablon dodaje link lub blok do strony „Moje konto” klienta, kierując go do dedykowanej strony modułu z punktami lojalnościowymi (`loyalty.tpl`).
    -   `myprestaloyalty/views/templates/hook/product.tpl`
        -   **Hook**: `displayProductExtraContent`, `displayProductButtons` lub `displayProductActions` (w zależności od wersji PrestaShop i motywu).
        -   **Opis**: Ten szablon wyświetla informację o tym, ile punktów lojalnościowych klient zdobędzie, kupując dany produkt na jego stronie produktu.
    -   `myprestaloyalty/views/templates/hook/shopping-cart.tpl`
        -   **Hook**: `displayShoppingCartFooter`, `displayCartExtraProductActions` lub `displayReassurance` (w zależności od wersji PrestaShop i motywu).
        -   **Opis**: Ten szablon wyświetla podsumowanie całkowitej liczby punktów lojalnościowych, które klient zdobędzie za produkty aktualnie znajdujące się w jego koszyku.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele baz danych**: Ten moduł nie tworzy niestandardowych tabel SQL. Wszystkie ustawienia modułu są przechowywane w tabeli `ps_configuration` PrestaShop, zazwyczaj z kluczami poprzedzonymi `MYPRESTALOYALTY_`.

    -   Przykładowe klucze konfiguracji: `MYPRESTALOYALTY_EXCHANGE_RATE`, `MYPRESTALOYALTY_POINT_VALUE`, `MYPRESTALOYALTY_MIN_POINTS`, `MYPRESTALOYALTY_VOUCHER_VALIDITY`, `MYPRESTALOYALTY_ENABLED`, `MYPRESTALOYALTY_DISPLAY_PRODUCT`, `MYPRESTALOYALTY_DISPLAY_CART`, `MYPRESTALOYALTY_DESCRIPTION`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Dołączenie zasobów CSS i JS dla front-office. |
| `displayCustomerAccount` | Na stronie „Moje konto” klienta. | Dodanie linku do sekcji „Moje punkty lojalnościowe”. |
| `displayProductExtraContent` (lub podobny) | Na stronie produktu, w pobliżu szczegółów/przycisków produktu. | Wyświetlanie punktów zdobytych za konkretny produkt. |
| `displayShoppingCartFooter` (lub podobny) | W podsumowaniu koszyka. | Wyświetlanie całkowitej liczby punktów zdobytych za bieżące zamówienie. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Obliczanie i przyznawanie punktów lojalnościowych klientowi na podstawie wartości zamówienia. |
| `displayLeftColumn` / `displayRightColumn` / `displayFooter` (opcjonalnie) | W odpowiednich obszarach kolumn/stopki. | Potencjalnie używane do wyświetlania szybkiego linku lub podsumowania programu lojalnościowego, jeśli skonfigurowano. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i dedykowane wsparcie techniczne dla modułu „Punkty lojalnościowe”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
