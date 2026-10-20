---
title: "Kod kuponu po rejestracji - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Kod kuponu po rejestracji” od MyPresta.eu."
sidebar:
  label: "Kod kuponu po rejestracji - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Voucher code after registration na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-code-after-registration.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/voucher-code-after-registration/)
>
> ---


# Kod kuponu po rejestracji

## 1. Wymagania i kompatybilność

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 5.6 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające i zazwyczaj preinstalowane w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij przycisk „Konfiguruj” obok modułu „Kod kuponu po rejestracji”. Spowoduje to przejście do głównego ekranu konfiguracji, gdzie możesz zdefiniować, jak będą działać Twoje kupony dla nowych klientów.

Strona konfiguracji przedstawi Ci opcje definiowania cech kuponu, który otrzymają nowi klienci. Te ustawienia bezpośrednio odpowiadają standardowym funkcjom „Reguły koszyka” (kuponu) PrestaShop.

Oto typowe ustawienia, które napotkasz:

-   **Opis:**

    -   **Co robi to ustawienie:** Jest to wewnętrzna nazwa reguły koszyka (kuponu), która zostanie utworzona. Pomaga zidentyfikować kupon w Twoim Panelu administracyjnym.
    -   **Wpływ zmiany tego ustawienia:** Ta nazwa służy wyłącznie do Twojej referencji i nie jest widoczna dla klientów.
    -   **Zalecana wartość:** Coś opisowego, np. „Kupon rejestracyjny dla nowego klienta” lub „Rabat powitalny”.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli prowadzisz wiele promocji, jasny opis, taki jak „Kupon powitalny – 10% zniżki”, pomaga śledzić jego wydajność.
-   **Kod:**

    -   **Co robi to ustawienie:** Definiuje prefiks dla generowanych unikalnych kodów kuponów. Moduł dołączy unikalny ciąg znaków do tego prefiksu dla każdego nowego klienta.
    -   **Wpływ zmiany tego ustawienia:** Jeśli ustawisz go na „WELCOME”, klienci mogą otrzymać kody takie jak „WELCOME12345” lub „WELCOMEABCDE”. To sprawia, że kody są łatwo identyfikowalne.
    -   **Zalecana wartość:** Krótki, łatwy do zapamiętania prefiks, np. „WELCOME”, „NEWCUSTOMER” lub „MYSTORE”. Pozostaw puste dla w pełni losowego kodu.
    -   **Scenariusz / przykład dla sprzedawcy:** Użycie „WELCOME” jasno informuje klienta, że jest to oferta powitalna.
-   **Wyróżnij:**

    -   **Co robi to ustawienie:** Jeśli włączone, ten kupon zostanie wyświetlony w podsumowaniu koszyka (jeśli dotyczy) i na stronie produktu (jeśli jest tak skonfigurowane w podstawowych ustawieniach PrestaShop).
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy włączone:* Istnienie kuponu może być subtelnie sugerowane w miejscach, gdzie zazwyczaj promowane są reguły koszyka.
        -   *Gdy wyłączone:* Kupon jest znany klientowi tylko za pośrednictwem poczty e-mail i jego konta.
    -   **Zalecana wartość:** TAK (Włączone), ponieważ może subtelnie przypominać klientom o dostępnych rabatach.
    -   **Scenariusz / przykład dla sprzedawcy:** Włączenie tej opcji może zachęcić klientów do użycia otrzymanego kuponu, nawet jeśli o nim zapomnieli.
-   **Częściowe użycie:**

    -   **Co robi to ustawienie:** Określa, czy kupon może być używany wielokrotnie, jeśli jego wartość jest większa niż całkowita kwota zamówienia.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy włączone:* Jeśli klient ma kupon o wartości 50 zł i kupuje przedmiot za 30 zł, pozostanie mu 20 zł salda na kuponie do wykorzystania w przyszłym zakupie.
        -   *Gdy wyłączone:* Cała wartość kuponu musi zostać wykorzystana w jednej transakcji, w przeciwnym razie pozostałe saldo przepada.
    -   **Zalecana wartość:** NIE (Wyłączone) dla większości kuponów powitalnych, aby zachęcić do pełnego zakupu.
    -   **Scenariusz / przykład dla sprzedawcy:** Dla kuponu „10% zniżki” to ustawienie jest mniej istotne, ale dla kuponu „stała kwota” (np. „10 zł zniżki”), wyłączenie częściowego użycia zachęca do większego pierwszego zamówienia.
-   **Priorytet:**

    -   **Co robi to ustawienie:** Jeśli klient ma wiele kuponów, ta liczba określa kolejność ich zastosowania. Niższe liczby oznaczają wyższy priorytet.
    -   **Wpływ zmiany tego ustawienia:** Kupon z priorytetem 1 zostanie zastosowany przed kuponem z priorytetem 2. Jest to ważne, jeśli kupony nie mogą być łączone.
    -   **Zalecana wartość:** 1 (Najwyższy priorytet) dla kuponów powitalnych, aby zapewnić ich zastosowanie w pierwszej kolejności.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz ogólny kupon na „darmową wysyłkę” (priorytet 5) i kupon na „rabat powitalny” (priorytet 1), rabat powitalny zostanie obliczony jako pierwszy.
-   **Status:**

    -   **Co robi to ustawienie:** Kontroluje, czy moduł jest aktywny i generuje kupony.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy włączone:* Nowi klienci otrzymają kupony po rejestracji.
        -   *Gdy wyłączone:* Moduł przestanie generować i wysyłać kupony.
    -   **Zalecana wartość:** TAK (Włączone), aby aktywować podstawową funkcjonalność modułu.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz tymczasowo wyłączyć go podczas konkretnego wydarzenia sprzedażowego, podczas którego nie chcesz oferować dodatkowych rabatów rejestracyjnych.
-   **Typ rabatu:**

    -   **Co robi to ustawienie:** Definiuje, czy rabat jest procentowy, stałą kwotą, czy darmową wysyłką.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Procentowy:* np. „10%” zniżki na zamówienie.
        -   *Kwota:* np. „10 zł” zniżki na zamówienie.
        -   *Darmowa wysyłka:* Znosi koszty wysyłki.
    -   **Zalecana wartość:** Procentowy lub Kwotowy, w zależności od Twojej strategii marketingowej.
    -   **Scenariusz / przykład dla sprzedawcy:** Oferowanie „10% zniżki” jest powszechne dla rabatów powitalnych. „5 zł zniżki” może być lepsze dla produktów o niższej cenie.
-   **Wartość:**

    -   **Co robi to ustawienie:** Rzeczywista wartość rabatu, odpowiadająca wybranemu „Typowi rabatu”.
    -   **Wpływ zmiany tego ustawienia:** Jeśli „Typ rabatu” to Procentowy, a „Wartość” to 10, klienci otrzymują 10% zniżki. Jeśli „Typ rabatu” to Kwota, a „Wartość” to 10, otrzymują 10 zł zniżki.
    -   **Zalecana wartość:** Wartość, która jest atrakcyjna, ale także opłacalna, np. „10” dla 10% lub „5 zł”.
    -   **Scenariusz / przykład dla sprzedawcy:** 10% rabatu to dobry punkt wyjścia, aby zachęcić nowych klientów.
-   **Minimalna kwota:**

    -   **Co robi to ustawienie:** Minimalna całkowita kwota zamówienia (przed wysyłką) wymagana do ważności kuponu.
    -   **Wpływ zmiany tego ustawienia:** Jeśli ustawiono na 50 zł, klient musi złożyć zamówienie o wartości 50 zł lub więcej, aby użyć kuponu.
    -   **Zalecana wartość:** Ustaw rozsądne minimum, aby zachęcić do większych pierwszych zamówień, lub 0, jeśli nie jest wymagane minimum.
    -   **Scenariusz / przykład dla sprzedawcy:** Ustawienie minimalnej kwoty 50 zł dla kuponu 10% zniżki zapewnia, że nadal osiągniesz dobry zysk z pierwszego zamówienia.
-   **Kumulatywny:**

    -   **Co robi to ustawienie:** Określa, czy ten kupon może być łączony z innymi kuponami.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy włączone:* Klienci mogą użyć tego kuponu powitalnego wraz z innymi aktywnymi kuponami (np. kuponem na darmową wysyłkę).
        -   *Gdy wyłączone:* Ten kupon nie może być użyty, jeśli inny kupon jest już zastosowany do koszyka.
    -   **Zalecana wartość:** NIE (Wyłączone) dla większości kuponów powitalnych, aby zapobiec nadmiernym rabatom.
    -   **Scenariusz / przykład dla sprzedawcy:** Zazwyczaj chcesz ograniczyć kumulowanie rabatów, aby chronić swoje marże, dlatego wyłączenie kumulatywnego użycia jest często preferowane.
-   **Ważny od / Ważny do:**

    -   **Co robi to ustawienie:** Definiuje zakres dat, w którym kupon jest aktywny.
    -   **Wpływ zmiany tego ustawienia:** Kupon będzie ważny tylko w tych datach.
    -   **Zalecana wartość:** Pozostaw „Ważny od” jako bieżącą datę. Dla „Ważny do” rozważ ustawienie daty wygaśnięcia (np. 30 dni od rejestracji), aby stworzyć poczucie pilności, lub pozostaw ją daleko w przyszłości, jeśli chcesz, aby była wieczna.
    -   **Scenariusz / przykład dla sprzedawcy:** Ustawienie „Ważny do” na 30 dni w przyszłości zachęca klientów do szybkiego użycia kuponu.
-   **Ilość:**

    -   **Co robi to ustawienie:** Odnosi się do całkowitej liczby *unikalnych* kuponów, które mogą być wygenerowane przez moduł.
    -   **Wpływ zmiany tego ustawienia:** Jeśli ustawiono na 100, tylko pierwszych 100 nowych zarejestrowanych użytkowników otrzyma kupon.
    -   **Zalecana wartość:** Bardzo wysoka liczba (np. 999999) lub pozostaw puste, jeśli chcesz, aby generowana była nieograniczona liczba kuponów dla nowych zarejestrowanych użytkowników.
    -   **Scenariusz / przykład dla sprzedawcy:** Dla trwającej oferty powitalnej zazwyczaj chcesz nieograniczonej ilości. Jeśli prowadzisz kampanię ograniczoną czasowo dla pierwszych X zarejestrowanych użytkowników, ustawiasz konkretną liczbę.
-   **Ilość na klienta:**

    -   **Co robi to ustawienie:** Definiuje, ile razy *pojedynczy klient* może otrzymać ten konkretny kupon.
    -   **Wpływ zmiany tego ustawienia:** Ustaw na 1, aby zapewnić, że każdy klient otrzyma tylko jeden kupon powitalny po swojej początkowej rejestracji.
    -   **Zalecana wartość:** 1.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby każdy nowy klient otrzymał jeden rabat powitalny, a nie wiele, jeśli zarejestruje się ponownie z innym adresem e-mail (chociaż rdzeń PrestaShop zazwyczaj temu zapobiega).

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Opis** | „Kupon dla nowego klienta” | Wewnętrzna nazwa kuponu w Panelu administracyjnym. |
| Konfiguracja modułu | **Kod** | Puste (losowe) / „WELCOME” | Prefiks dla generowanych kodów kuponów. |
| Konfiguracja modułu | **Wyróżnij** | TAK | Wyświetl kupon w podsumowaniu koszyka/na stronie produktu. |
| Konfiguracja modułu | **Częściowe użycie** | NIE | Zezwól na wielokrotne użycie, jeśli wartość > całkowita kwota zamówienia. |
| Konfiguracja modułu | **Priorytet** | 1 | Kolejność zastosowania, jeśli wiele kuponów. |
| Konfiguracja modułu | **Status** | TAK | Aktywuj/dezaktywuj generowanie kuponów przez moduł. |
| Konfiguracja modułu | **Typ rabatu** | Procentowy | Typ rabatu (%, kwota, darmowa wysyłka). |
| Konfiguracja modułu | **Wartość** | 10 | Rzeczywista wartość rabatu (np. 10 dla 10%). |
| Konfiguracja modułu | **Minimalna kwota** | 0 | Minimalna całkowita kwota zamówienia dla ważności kuponu. |
| Konfiguracja modułu | **Kumulatywny** | NIE | Zezwól na łączenie z innymi kuponami. |
| Konfiguracja modułu | **Ważny od** | Bieżąca data | Data rozpoczęcia ważności kuponu. |
| Konfiguracja modułu | **Ważny do** | Daleka przyszłość / 30 dni | Data zakończenia ważności kuponu. |
| Konfiguracja modułu | **Ilość** | 999999 | Całkowita liczba unikalnych kuponów do wygenerowania. |
| Konfiguracja modułu | **Ilość na klienta** | 1 | Ile razy pojedynczy klient może go otrzymać. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moi klienci nie otrzymują e-maila z kuponem. Co powinienem sprawdzić?**
O:

1.  **Status modułu:** Upewnij się, że ustawienie „Status” w konfiguracji modułu jest ustawione na TAK (Włączone).
2.  **Konfiguracja e-maila:** Sprawdź ustawienia e-maila w PrestaShop w **Zaawansowane > E-mail**. Wyślij testowy e-mail, aby upewnić się, że system e-mailowy Twojego sklepu działa poprawnie.
3.  **Foldery spamu:** Doradź klientom, aby sprawdzili swoje foldery spamu lub niechcianej poczty.
4.  **Logi modułu:** Jeśli dostępne, sprawdź, czy nie ma żadnych logów błędów związanych z modułem lub wysyłaniem e-maili.
5.  **Pamięć podręczna Smarty:** Czasami wyczyszczenie pamięci podręcznej Smarty w **Zaawansowane > Wydajność** może rozwiązać problemy z wyświetlaniem lub funkcjonalnością.

**P: Kod kuponu jest generowany, ale nie jest poprawnie stosowany przy kasie.**
O:

1.  **Ustawienia kuponu:** Dokładnie sprawdź wszystkie ustawienia kuponu w konfiguracji modułu (np. „Minimalna kwota”, „Ważny od/do”, „Kumulatywny”). Upewnij się, że koszyk klienta spełnia wszystkie warunki.
2.  **Wprowadzanie kodu:** Potwierdź, że klient poprawnie wprowadza kod w koszyku/przy kasie.
3.  **Ograniczenia produktów:** Upewnij się, że nie ma żadnych ukrytych ograniczeń produktów lub kategorii zastosowanych do wygenerowanej reguły koszyka (chociaż ten moduł zazwyczaj tworzy proste, szerokie reguły).

**P: Czy mogę dostosować szablon e-maila, który wysyła kupon?**
O: Tak, moduł używa standardowego systemu szablonów e-mail PrestaShop. Możesz znaleźć i dostosować odpowiednie pliki szablonów e-mail (zazwyczaj w `themes/your_theme/mail/en/` lub `mails/en/` dla starszych wersji), które są wyzwalane, gdy tworzona i wysyłana jest nowa reguła koszyka. Szukaj szablonów związanych z `voucher` lub `cart_rule`.

**P: Co się stanie, jeśli klient zarejestruje się wielokrotnie z różnymi adresami e-mail?**
O: Moduł wygeneruje nowy unikalny kupon dla każdej nowej rejestracji. Podstawowa funkcjonalność PrestaShop zazwyczaj zapobiega duplikowaniu rejestracji e-mail, ale jeśli klient użyje różnych e-maili, otrzyma nowy kupon za każdym razem. Ustawienie „Ilość na klienta” dotyczy pojedynczego identyfikatora klienta, a niekoniecznie unikalnych adresów e-mail, jeśli ominą one podstawowe sprawdzenia.

**P: Moduł jest zainstalowany, ale nie widzę żadnych nowych pozycji menu w Panelu administracyjnym.**
O: Ten moduł integruje się bezpośrednio z istniejącą sekcją „Moduły > Menedżer modułów” i nie dodaje nowych pozycji menu najwyższego poziomu. Jego konfiguracja jest dostępna po kliknięciu „Konfiguruj” obok jego nazwy na liście modułów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Kod kuponu po rejestracji” (`registervoucher`) to standardowy moduł PrestaShop, zaprojektowany głównie do rozszerzania haka `actionCustomerAccountAdd`. Wykorzystuje podstawową funkcjonalność `CartRule` (kuponu) PrestaShop do automatycznego tworzenia i przypisywania unikalnego kodu rabatowego do nowych kont klientów. Konfiguracja modułu jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu, przechowując ustawienia w `ps_configuration`. Obejmuje minimalną interakcję z front-office, głównie opierając się na natywnym systemie e-mail PrestaShop i wyświetlaniu konta klienta w celu dostarczenia kuponu.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała logika jest hermetyzowana w głównym pliku modułu i jego zarejestrowanych hakach.

### 4.3 Klasy i modele rdzenia (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Bezpośrednio współdziała z podstawową klasą `CartRule` PrestaShop w celu tworzenia i zarządzania kuponami.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `registervoucher/lib/voucherengine/script.js`
    -   **Zakres:** Potencjalnie Back-office lub ogólny skrypt dołączony dla kompatybilności.
    -   **Opis:** Biorąc pod uwagę podstawową funkcję modułu (generowanie kuponów w backendzie), ten skrypt jest prawdopodobnie skryptem narzędziowym lub kompatybilności. Może obsługiwać ulepszenia interfejsu użytkownika na stronie konfiguracji, walidację formularzy lub zapewniać poprawki kompatybilności dla starszych wersji PrestaShop, zwłaszcza w odniesieniu do dynamicznych elementów formularzy lub interakcji AJAX w metodzie `getContent()`. Bez dalszej inspekcji jego dokładny cel jest spekulatywny, ale ogólnie związany z ulepszaniem interfejsu konfiguracji modułu lub zapewnianiem kompatybilności między wersjami dla panelu administracyjnego.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `registervoucher/css.css`

    -   **Zakres:** Prawdopodobnie stylizacja formularza administracyjnego Back-office.
    -   **Opis:** Ten arkusz stylów prawdopodobnie zawiera niestandardowe style dla strony konfiguracji modułu w Panelu administracyjnym PrestaShop. Może dostosowywać układ, odstępy, kolory lub wygląd konkretnych elementów, aby zapewnić wizualną spójność formularza konfiguracji lub zastosować niestandardowe branding.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** `.registervoucher-config`, `.form-group`, `.control-label`, `.help-block` (specyficzne dla wygenerowanego kodu HTML modułu).
-   `registervoucher/lib/voucherengine/ps16.css`

    -   **Zakres:** Stylizacja formularza administracyjnego Back-office, specjalnie dla kompatybilności z PrestaShop 1.6.
    -   **Opis:** Ten arkusz stylów jest prawie na pewno dołączony, aby zapewnić, że strona konfiguracji modułu renderuje się poprawnie i spójnie z motywem Panelu administracyjnego PrestaShop 1.6. Odnosi się do różnic w stylizacji między PS 1.6 a nowszymi wersjami, zapewniając niezbędne nadpisania lub specyficzne style dla elementów takich jak przyciski, pola formularzy i kontenery układu, aby zachować odpowiedni wygląd i styl.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Specyficzne dla motywu administracyjnego PS 1.6, np. `.panel`, `.form-horizontal`, `.btn`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Dossier modułu nie wskazuje na żadne niestandardowe pliki `.tpl`. Sugeruje to, że formularz konfiguracji modułu jest renderowany bezpośrednio w metodzie `getContent()` za pomocą klas pomocniczych PrestaShop (np. `HelperForm`), a wszelkie wyświetlanie w front-office (takie jak kupon na koncie klienta) jest obsługiwane przez nadpisywanie podstawowych szablonów PrestaShop lub przez bezpośrednie wstrzykiwanie treści za pomocą haków bez dedykowanych szablonów modułu. Treść e-maila jest zarządzana za pośrednictwem natywnych szablonów poczty PrestaShop.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych niestandardowych tabel bazy danych.
    -   Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration` (np. `PS_REGISTERVOUCHER_DESCRIPTION`, `PS_REGISTERVOUCHER_CODE` itp.).
    -   Wygenerowane kupony są przechowywane w podstawowych tabelach PrestaShop `ps_cart_rule` i `ps_cart_rule_lang`.
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Wykonywany natychmiast po pomyślnym utworzeniu nowego konta klienta. | To jest główny hak. Moduł nasłuchuje tego zdarzenia, aby wyzwolić proces generowania i przypisywania kuponu dla nowo zarejestrowanego klienta. |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony front-office. | Często używany do dodawania CSS/JS, ale w tym module nie jest wyraźnie używany do wyświetlania w front-office. Może służyć do wewnętrznej konfiguracji modułu lub kompatybilności. |
| `displayRightColumn` | Wykonywany w prawej kolumnie front-office. | Nie jest bezpośrednio używany do podstawowej funkcjonalności modułu wyświetlania kuponów. |
| `displayLeftColumn` | Wykonywany w lewej kolumnie front-office. | Nie jest bezpośrednio używany do podstawowej funkcjonalności modułu wyświetlania kuponów. |
| `displayFooter` | Wykonywany w sekcji stopki każdej strony front-office. | Nie jest bezpośrednio używany do podstawowej funkcjonalności modułu wyświetlania kuponów. |
| `displayProductButtons` | Wykonywany na stronie produktu, w pobliżu przycisku dodawania do koszyka. | Nie jest bezpośrednio używany do podstawowej funkcjonalności modułu wyświetlania kuponów. |
| `displayCustomerAccount` | Wykonywany na stronie „Moje konto” klienta. | Ten hak jest kluczowy do wyświetlania wygenerowanego kodu kuponu bezpośrednio w obszarze konta klienta, co czyni go łatwo dostępnym. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Kod kuponu po rejestracji”, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
