---
title: "Pokaż dwie ceny - z podatkiem / bez podatku - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop 'Pokaż dwie ceny - z podatkiem / bez podatku' od MyPresta.eu."
sidebar:
  label: "Pokaż dwie ceny - z podatkiem / bez podatku - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Show two prices - tax included / excluded na MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-two-prices-tax-included-excluded.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/show-two-prices-tax-included-excluded/)
>
> ---


# Pokaż dwie ceny - z podatkiem / bez podatku

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są wymagane dla samego PrestaShop i ogólnie dla działania modułów. Brak specjalnych wymagań hostingowych poza standardowym środowiskiem kompatybilnym z PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Pokaż dwie ceny - z podatkiem / bez podatku”. Możesz uzyskać do niego dostęp, przechodząc do **Moduły > Menedżer modułów** i klikając „Konfiguruj” obok nazwy modułu.

#### Ustawienia ogólne

-   **Włączony / Wyłączony (Przełącznik globalny)**
    -   **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania całej funkcjonalności modułu w Twoim sklepie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Moduł zacznie wyświetlać ceny zarówno z podatkiem, jak i bez podatku zgodnie z innymi ustawieniami.
        -   *Gdy wyłączony:* Moduł przestanie wyświetlać dodatkowe informacje o cenach, a Twój sklep powróci do domyślnego sposobu wyświetlania cen.
    -   **Zalecana wartość:** Włączony (aby korzystać z funkcji modułu).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli wykonujesz konserwację lub tymczasowo chcesz ukryć podwójne wyświetlanie cen, możesz je tutaj wyłączyć.

#### Ustawienia strony produktu

-   **Pokaż na stronie produktu (BF\_PP)**

    -   **Co robi to ustawienie:** Kontroluje, czy ceny z podatkiem i bez podatku są wyświetlane na indywidualnych stronach szczegółów produktu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Obie ceny pojawią się na stronach produktów.
        -   *Gdy wyłączony:* Na stronach produktów będzie wyświetlana tylko domyślna cena PrestaShop (zazwyczaj z podatkiem).
    -   **Zalecana wartość:** Włączony (aby zapewnić pełną przejrzystość).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz wyświetlać podwójne ceny tylko na listach kategorii, ale zachować czystsze strony produktów, możesz to wyłączyć.
-   **Ukryj cenę z podatkiem na stronie produktu (BOTH\_HIDE\_P)**

    -   **Co robi to ustawienie:** Jeśli opcja „Pokaż na stronie produktu” jest włączona, ta opcja pozwala ukryć cenę z podatkiem, skutecznie pokazując tylko cenę bez podatku obok ceny oryginalnej (jeśli nie jest ukryta).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Cena z podatkiem zostanie ukryta na stronach produktów.
        -   *Gdy wyłączony:* Cena z podatkiem będzie widoczna na stronach produktów (jeśli opcja „Pokaż na stronie produktu” jest włączona).
    -   **Zalecana wartość:** Wyłączony (chyba że masz konkretny powód, aby ją ukryć, np. sklep skoncentrowany na B2B).
    -   **Scenariusz / przykład dla sprzedawcy:** Sklep B2B może chcieć podkreślić ceny bez podatku i ukryć cenę z podatkiem, aby usprawnić widok dla swoich klientów biznesowych.
-   **Niestandardowy CSS dla strony produktu (BF\_PPC)**

    -   **Co robi to ustawienie:** Pozwala dodać niestandardowe reguły CSS specjalnie dla podwójnego wyświetlania cen na stronach produktów. Jest to dla zaawansowanych użytkowników lub webmasterów.
    -   **Efekt zmiany tego ustawienia:** Dowolny kod CSS wprowadzony tutaj zostanie zastosowany do elementów cenowych modułu na stronach produktów, umożliwiając zmianę kolorów, czcionek, rozmiarów lub pozycjonowania.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne potrzeby stylizacyjne.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz chcieć, aby cena bez podatku była mniejsza lub miała inny kolor niż cena z podatkiem, aby wizualnie je odróżnić.
-   **Wymuś ukrycie strony produktu (BP\_FORCE\_HIDE)**

    -   **Co robi to ustawienie:** Jest to bardziej agresywna opcja ukrycia wyjścia modułu na stronie produktu. Może być przydatna, jeśli wyjście modułu koliduje z Twoim motywem lub innymi modułami.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Moduł spróbuje wymusić ukrycie wyświetlania cen na stronach produktów, niezależnie od innych ustawień.
        -   *Gdy wyłączony:* Moduł będzie wyświetlać ceny zgodnie z innymi ustawieniami.
    -   **Zalecana wartość:** Wyłączony (włącz tylko, jeśli występują problemy z wyświetlaniem).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli podwójne wyświetlanie cen nakłada się na inny element na stronie produktu, włączenie tej opcji może rozwiązać konflikt.
-   **Etykieta ceny z podatkiem (BP\_TIN)**

    -   **Co robi to ustawienie:** Definiuje etykietę tekstową wyświetlaną obok ceny z podatkiem na stronach produktów.
    -   **Efekt zmiany tego ustawienia:** Zmienia tekst etykiety.
    -   **Zalecana wartość:** „Cena brutto” lub „VAT wliczony”.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz zmienić to na „Cena z VAT” dla jasności w niektórych regionach.
-   **Etykieta ceny bez podatku (BP\_TEX)**

    -   **Co robi to ustawienie:** Definiuje etykietę tekstową wyświetlaną obok ceny bez podatku na stronach produktów.
    -   **Efekt zmiany tego ustawienia:** Zmienia tekst etykiety.
    -   **Zalecana wartość:** „Cena netto” lub „VAT wyłączony”.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz zmienić to na „Cena bez VAT” dla jasności.
-   **Etykieta oryginalnej ceny z podatkiem (BP\_O\_TIN)**

    -   **Co robi to ustawienie:** Definiuje etykietę tekstową dla *oryginalnej* ceny z podatkiem, szczególnie przydatną, gdy stosowane są konkretne ceny lub rabaty.
    -   **Efekt zmiany tego ustawienia:** Zmienia tekst etykiety.
    -   **Zalecana wartość:** „Oryginalna cena brutto”.
    -   **Scenariusz / przykład dla sprzedawcy:** Gdy produkt jest na wyprzedaży, możesz chcieć pokazać oryginalną cenę z konkretną etykietą.

#### Ustawienia strony z listą produktów

-   **Pokaż na liście produktów (BF\_PL)**

    -   **Co robi to ustawienie:** Kontroluje, czy ceny z podatkiem i bez podatku są wyświetlane na stronach z listą produktów (kategorie, wyniki wyszukiwania, moduły na stronie głównej).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Obie ceny pojawią się na stronach z listą produktów.
        -   *Gdy wyłączony:* Na stronach z listą produktów będzie wyświetlana tylko domyślna cena PrestaShop.
    -   **Zalecana wartość:** Włączony (dla spójnej przejrzystości).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoje strony kategorii są bardzo gęste, możesz to wyłączyć, aby zmniejszyć wizualny bałagan.
-   **Ukryj cenę z podatkiem na liście produktów (BOTH\_HIDE\_PL)**

    -   **Co robi to ustawienie:** Jeśli opcja „Pokaż na liście produktów” jest włączona, ta opcja pozwala ukryć cenę z podatkiem na stronach z listą.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Cena z podatkiem zostanie ukryta na stronach z listą produktów.
        -   *Gdy wyłączony:* Cena z podatkiem będzie widoczna na stronach z listą produktów.
    -   **Zalecana wartość:** Wyłączony (chyba że masz konkretny powód, aby ją ukryć).
    -   **Scenariusz / przykład dla sprzedawcy:** Sklep B2B może chcieć wyświetlać tylko ceny bez podatku na wszystkich listach produktów.
-   **Niestandardowy CSS dla listy produktów (BF\_PLC)**

    -   **Co robi to ustawienie:** Pozwala dodać niestandardowe reguły CSS specjalnie dla podwójnego wyświetlania cen na stronach z listą produktów.
    -   **Efekt zmiany tego ustawienia:** Dowolny kod CSS wprowadzony tutaj zostanie zastosowany do elementów cenowych modułu na stronach z listą.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne potrzeby stylizacyjne.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz chcieć, aby cena bez podatku była mniejsza i wyszarzona na stronach kategorii, aby główna cena (z podatkiem) bardziej się wyróżniała.
-   **Etykieta ceny z podatkiem (BP\_TINL)**

    -   **Co robi to ustawienie:** Definiuje etykietę tekstową wyświetlaną obok ceny z podatkiem na stronach z listą produktów.
    -   **Efekt zmiany tego ustawienia:** Zmienia tekst etykiety.
    -   **Zalecana wartość:** „Cena brutto” lub „VAT wliczony”.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz użyć krótszej etykiety, takiej jak „brutto”, na stronach z listą ze względu na ograniczoną przestrzeń.
-   **Etykieta ceny bez podatku (BP\_TEXL)**

    -   **Co robi to ustawienie:** Definiuje etykietę tekstową wyświetlaną obok ceny bez podatku na stronach z listą produktów.
    -   **Efekt zmiany tego ustawienia:** Zmienia tekst etykiety.
    -   **Zalecana wartość:** „Cena netto” lub „VAT wyłączony”.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz użyć krótszej etykiety, takiej jak „netto”, na stronach z listą.

#### Reguły widoczności

-   **Reguła widoczności (bp\_visibility\_rule)**

    -   **Co robi to ustawienie:** Określa, jak zachowuje się podwójne wyświetlanie cen w zależności od grup klientów, konkretnych produktów lub kategorii.
    -   **Efekt zmiany tego ustawienia:**
        -   *Zawsze pokazuj:* Podwójne ceny są zawsze pokazywane wszystkim klientom, produktom i kategoriom.
        -   *Ukryj dla wybranych grup/produktów/kategorii:* Podwójne ceny są ukrywane dla konkretnych wyborów.
        -   *Pokaż tylko dla wybranych grup/produktów/kategorii:* Podwójne ceny są pokazywane tylko dla konkretnych wyborów.
    -   **Zalecana wartość:** Zawsze pokazuj (dla maksymalnej przejrzystości) lub „Pokaż tylko dla wybranych grup”, jeśli celujesz w klientów B2B.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz wybrać „Pokaż tylko dla wybranych grup”, a następnie wybrać grupę „Klienci hurtowi”, aby wyświetlać podwójne ceny tylko dla swoich klientów B2B.
-   **Widoczność dla grup klientów (actionAdminGroupsControllerSaveAfter)**

    -   **Co robi to ustawienie:** Pozwala wybrać, które grupy klientów zobaczą podwójne wyświetlanie cen, na podstawie powyższej „Reguły widoczności”.
    -   **Efekt zmiany tego ustawienia:** Tylko klienci należący do wybranych grup zobaczą podwójne ceny (jeśli reguła to „Pokaż tylko dla wybranych grup”) lub *nie* zobaczą ich (jeśli reguła to „Ukryj dla wybranych grup”).
    -   **Zalecana wartość:** Wybierz „Wszystkie grupy klientów”, jeśli Twoja reguła to „Zawsze pokazuj”. W przeciwnym razie wybierz odpowiednie grupy.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby tylko grupy „Gość” i „Klient” widziały głównie ceny z podatkiem, ale „Hurtowi” widzieli obie, ustaw regułę na „Pokaż tylko dla wybranych grup” i wybierz „Hurtowi”.
-   **Widoczność dla produktów (bp\_visibility\_products)**

    -   **Co robi to ustawienie:** Pozwala określić pojedyncze produkty, dla których podwójne wyświetlanie cen powinno być stosowane (lub nie), na podstawie „Reguły widoczności”. Używa to pola wyszukiwania z autouzupełnianiem.
    -   **Efekt zmiany tego ustawienia:** Podwójne wyświetlanie cen zostanie włączone lub wyłączone dla wybranych produktów zgodnie z wybraną regułą widoczności.
    -   **Zalecana wartość:** Pozostaw puste, jeśli chcesz, aby dotyczyło wszystkich produktów.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz mieć kilka konkretnych produktów, gdzie pokazywanie obu cen jest mylące, więc ustawiasz regułę na „Ukryj dla wybranych produktów” i dodajesz te produkty tutaj.
-   **Widoczność dla kategorii (bp\_visibility\_cat)**

    -   **Co robi to ustawienie:** Pozwala określić kategorie, dla których podwójne wyświetlanie cen powinno być stosowane (lub nie), na podstawie „Reguły widoczności”.
    -   **Efekt zmiany tego ustawienia:** Podwójne wyświetlanie cen zostanie włączone lub wyłączone dla wszystkich produktów w wybranych kategoriach zgodnie z wybraną regułą widoczności.
    -   **Zalecana wartość:** Pozostaw puste, jeśli chcesz, aby dotyczyło wszystkich kategorii.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz zarówno towary fizyczne (gdzie podatek jest istotny), jak i produkty cyfrowe (gdzie podatek może być obsługiwany inaczej), możesz ukryć podwójne ceny dla kategorii „Pobrane pliki cyfrowe”.

#### Opcje wyświetlania

-   **Pokaż typy cen (BF\_SHOW\_TYPES)**

    -   **Co robi to ustawienie:** Określa, które typy cen są wyświetlane.
    -   **Efekt zmiany tego ustawienia:**
        -   *Z podatkiem i bez podatku:* Pokazuje obie ceny.
        -   *Tylko z podatkiem:* Pokazuje tylko cenę z podatkiem (moduł nadal przetwarza, ale wyświetla tylko jedną).
        -   *Tylko bez podatku:* Pokazuje tylko cenę bez podatku.
    -   **Zalecana wartość:** Z podatkiem i bez podatku (aby wykorzystać podstawową funkcję modułu).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoim głównym celem jest pokazanie cen bez podatku klientom B2B, możesz wybrać „Tylko bez podatku” w połączeniu z regułą widoczności dla grup klientów.
-   **Użyj CSS motywu Classic (BF\_CLASSICCSS)**

    -   **Co robi to ustawienie:** Jeśli Twój motyw jest oparty na domyślnym motywie PrestaShop Classic, włączenie tej opcji zastosuje specyficzne reguły CSS zaprojektowane do płynnej integracji ze stylizacją tego motywu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Moduł załaduje dedykowany arkusz stylów (`classic.css`), aby zapewnić lepszą integrację wizualną z motywami opartymi na Classic.
        -   *Gdy wyłączony:* Moduł użyje swojego domyślnego stylu, co może wymagać niestandardowego CSS dla idealnej integracji z motywami innymi niż Classic.
    -   **Zalecana wartość:** Włącz, jeśli Twój motyw jest oparty na Classic lub jest motywem potomnym Classic. W przeciwnym razie wyłącz.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli właśnie zainstalowałeś moduł, a ceny wyglądają na źle wyrównane w Twoim motywie Classic, włączenie tej opcji może to naprawić.
-   **Własny CSS (BF\_OWNCSS)**

    -   **Co robi to ustawienie:** Udostępnia pole tekstowe, w którym możesz wprowadzić własny kod CSS, aby nadpisać lub dodać style do wyjścia modułu. Jest to dla zaawansowanych użytkowników lub webmasterów.
    -   **Efekt zmiany tego ustawienia:** Dowolny kod CSS wprowadzony tutaj zostanie zastosowany globalnie do wyświetlania cen modułu, umożliwiając pełną kontrolę nad stylizacją.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne potrzeby stylizacyjne.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz zmienić rozmiar czcionki wyświetlanych cen lub dodać do nich obramowanie, aby były bardziej widoczne.

#### Ustawienia zaawansowane

-   **Procent podatku na stronie produktu (BP\_PP\_TPERCENT)**

    -   **Co robi to ustawienie:** Pozwala wyświetlić procent podatku na stronach produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Włączony:* Procent podatku (np. „20% VAT”) zostanie wyświetlony obok cen.
        -   *Wyłączony:* Procent podatku nie zostanie wyświetlony.
    -   **Zalecana wartość:** Wyłączony (chyba że chcesz wyraźnie pokazać stawkę podatku).
    -   **Scenariusz / przykład dla sprzedawcy:** W krajach, gdzie klienci są bardzo świadomi podatków, pokazanie procentu może dodać kolejną warstwę przejrzystości.
-   **Procent podatku na stronie produktu (bez podatku) (BP\_PP\_TPERCENT\_TEXL)**

    -   **Co robi to ustawienie:** Podobnie jak powyżej, ale specjalnie dla wyświetlania ceny bez podatku na stronach produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Włączony:* Procent podatku zostanie wyświetlony obok ceny bez podatku.
        -   *Wyłączony:* Procent podatku nie zostanie wyświetlony.
    -   **Zalecana wartość:** Wyłączony.
    -   **Scenariusz / przykład dla sprzedawcy:** Przydatne, jeśli chcesz podkreślić stawkę podatku, która jest wykluczona.
-   **Procent podatku na liście produktów (BP\_PL\_TPERCENT)**

    -   **Co robi to ustawienie:** Pozwala wyświetlić procent podatku na stronach z listą produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Włączony:* Procent podatku zostanie wyświetlony obok cen na stronach z listą.
        -   *Wyłączony:* Procent podatku nie zostanie wyświetlony.
    -   **Zalecana wartość:** Wyłączony (aby zachować czystsze strony z listą).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoje listy produktów nie są zbyt zatłoczone, pokazanie procentu podatku może być informacyjne.
-   **Procent podatku na liście produktów (bez podatku) (BP\_PL\_TPERCENT\_TEXL)**

    -   **Co robi to ustawienie:** Podobnie jak powyżej, ale specjalnie dla wyświetlania ceny bez podatku na stronach z listą produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Włączony:* Procent podatku zostanie wyświetlony obok ceny bez podatku na stronach z listą.
        -   *Wyłączony:* Procent podatku nie zostanie wyświetlony.
    -   **Zalecana wartość:** Wyłączony.
    -   **Scenariusz / przykład dla sprzedawcy:** Mniej powszechne, ale może być używane do podkreślenia składnika podatku, który jest usuwany.

#### Ustawienia języka (Wewnętrzne)

-   **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG**
    -   **Co robi to ustawienie:** Są to wewnętrzne ustawienia PrestaShop związane z domyślnym językiem i językiem formularza pracownika. Są wyświetlane tutaj w celach informacyjnych i nie są bezpośrednio konfigurowalne przez moduł.
    -   **Efekt zmiany tego ustawienia:** Nie dotyczy, są to wartości tylko do odczytu z konfiguracji PrestaShop.
    -   **Zalecana wartość:** N/A
    -   **Scenariusz / przykład dla sprzedawcy:** Te wartości pomagają modułowi określić, którego języka użyć dla etykiet, jeśli nie ustawiłeś ich jawnie dla wszystkich języków.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### AdminBothpricesSearchController (Panel administracyjny > Moduły > Pokaż dwie ceny - z podatkiem / bez podatku > Wyszukaj produkty)

Ten dedykowany ekran administracyjny służy do zarządzania ustawieniem „Widoczność dla produktów”. Zapewnia interfejs do wyszukiwania i wybierania konkretnych produktów, które powinny być objęte regułami widoczności modułu.

-   **Nazwa ekranu i lokalizacja w menu:** Możesz uzyskać dostęp do tego ekranu, klikając link lub przycisk „Wyszukaj produkty” na głównej stronie konfiguracji modułu, zazwyczaj obok ustawienia „Widoczność dla produktów”.
-   **Dostępne akcje i ustawienia:**
    -   **Pole wyszukiwania produktów:** Pole tekstowe, w którym możesz wpisać nazwy produktów lub identyfikatory, aby znaleźć konkretne produkty.
    -   **Siatka wyników wyszukiwania:** Wyświetla listę produktów pasujących do Twojego zapytania.
    -   **Przyciski Dodaj/Usuń:** Pozwala dodawać wybrane produkty do listy produktów objętych regułą widoczności lub usuwać je z niej.
    -   **Lista wybranych produktów:** Pokazuje wszystkie produkty aktualnie skonfigurowane dla reguły widoczności.
-   **Efekt zmian:**
    -   Dodanie produktu do listy oznacza, że podwójne wyświetlanie cen modułu będzie albo pokazywane *tylko* dla tego produktu, albo *ukryte* dla tego produktu, w zależności od ogólnego ustawienia „Reguły widoczności”.
    -   Usunięcie produktu oznacza, że nie będzie on już konkretnie objęty regułą widoczności na poziomie produktu i powróci do ogólnych ustawień modułu.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Przejdź do głównej strony konfiguracji modułu.
    2.  Ustaw swoją „Regułę widoczności” (np. „Ukryj dla wybranych produktów”).
    3.  Kliknij link/przycisk, aby otworzyć ekran „AdminBothpricesSearchController”.
    4.  Użyj pola wyszukiwania, aby znaleźć produkty, które chcesz uwzględnić w regule.
    5.  Dodaj je do „Listy wybranych produktów”.
    6.  Zapisz zmiany na głównej stronie konfiguracji modułu.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włączony / Wyłączony | Włączony | Główny przełącznik funkcjonalności modułu. |
| Konfiguracja modułu | Pokaż na stronie produktu (BF\_PP) | Włączony | Wyświetla podwójne ceny na stronach szczegółów produktu. |
| Konfiguracja modułu | Ukryj cenę z podatkiem na stronie produktu (BOTH\_HIDE\_P) | Wyłączony | Ukrywa cenę brutto na stronach produktów. |
| Konfiguracja modułu | Niestandardowy CSS dla strony produktu (BF\_PPC) | Puste | Niestandardowy CSS dla wyświetlania cen na stronie produktu. |
| Konfiguracja modułu | Wymuś ukrycie strony produktu (BP\_FORCE\_HIDE) | Wyłączony | Wymusza ukrycie wyjścia modułu na stronie produktu. |
| Konfiguracja modułu | Etykieta ceny z podatkiem (BP\_TIN) | „Cena brutto” | Etykieta dla ceny z podatkiem na stronie produktu. |
| Konfiguracja modułu | Etykieta ceny bez podatku (BP\_TEX) | „Cena netto” | Etykieta dla ceny bez podatku na stronie produktu. |
| Konfiguracja modułu | Etykieta oryginalnej ceny z podatkiem (BP\_O\_TIN) | „Oryginalna cena brutto” | Etykieta dla oryginalnej ceny z podatkiem na stronie produktu. |
| Konfiguracja modułu | Pokaż na liście produktów (BF\_PL) | Włączony | Wyświetla podwójne ceny na stronach kategorii/listy. |
| Konfiguracja modułu | Ukryj cenę z podatkiem na liście produktów (BOTH\_HIDE\_PL) | Wyłączony | Ukrywa cenę brutto na stronach listy. |
| Konfiguracja modułu | Niestandardowy CSS dla listy produktów (BF\_PLC) | Puste | Niestandardowy CSS dla wyświetlania cen na stronach listy. |
| Konfiguracja modułu | Etykieta ceny z podatkiem (BP\_TINL) | „Cena brutto” | Etykieta dla ceny z podatkiem na stronach listy produktów. |
| Konfiguracja modułu | Etykieta ceny bez podatku (BP\_TEXL) | „Cena netto” | Etykieta dla ceny bez podatku na stronach listy produktów. |
| Konfiguracja modułu | Reguła widoczności (bp\_visibility\_rule) | Zawsze pokazuj | Definiuje, jak stosowane są reguły widoczności (pokaż/ukryj dla wybranych). |
| Konfiguracja modułu | Widoczność dla grup klientów | Wszystkie grupy klientów | Wybiera grupy klientów objęte regułą widoczności. |
| Konfiguracja modułu | Widoczność dla produktów (bp\_visibility\_products) | Puste | Wybiera konkretne produkty objęte regułą widoczności. |
| Konfiguracja modułu | Widoczność dla kategorii (bp\_visibility\_cat) | Puste | Wybiera konkretne kategorie objęte regułą widoczności. |
| Konfiguracja modułu | Pokaż typy cen (BF\_SHOW\_TYPES) | Z podatkiem i bez podatku | Określa, które typy cen są wyświetlane (obie, tylko brutto, tylko netto). |
| Konfiguracja modułu | Użyj CSS motywu Classic (BF\_CLASSICCSS) | Wyłączony (Włącz dla motywów Classic) | Stosuje stylizację specyficzną dla motywu Classic. |
| Konfiguracja modułu | Własny CSS (BF\_OWNCSS) | Puste | Globalny niestandardowy CSS dla wyjścia modułu. |
| Konfiguracja modułu | Procent podatku na stronie produktu (BP\_PP\_TPERCENT) | Wyłączony | Wyświetla procent podatku na stronach produktów. |
| Konfiguracja modułu | Procent podatku na stronie produktu (bez podatku) (BP\_PP\_TPERCENT\_TEXL) | Wyłączony | Wyświetla procent podatku dla ceny bez podatku na stronach produktów. |
| Konfiguracja modułu | Procent podatku na liście produktów (BP\_PL\_TPERCENT) | Wyłączony | Wyświetla procent podatku na stronach listy. |
| Konfiguracja modułu | Procent podatku na liście produktów (bez podatku) (BP\_PL\_TPERCENT\_TEXL) | Wyłączony | Wyświetla procent podatku dla ceny bez podatku na stronach listy. |
| AdminBothpricesSearchController | Wyszukiwanie produktów / Dodaj/Usuń | N/A | Zarządza listą produktów dla reguł widoczności. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moduł jest włączony, ale nie widzę dwóch cen w moim sklepie.**
O:

-   **Sprawdź globalne włączenie:** Upewnij się, że główny przełącznik „Włączony / Wyłączony” na górze konfiguracji modułu jest ustawiony na „Włączony”.
-   **Sprawdź ustawienia specyficzne dla strony:** Zweryfikuj, czy opcje „Pokaż na stronie produktu” (BF\_PP) i/lub „Pokaż na liście produktów” (BF\_PL) są włączone, w zależności od tego, gdzie spodziewasz się zobaczyć ceny.
-   **Sprawdź reguły widoczności:** Jeśli ustawiłeś „Regułę widoczności”, upewnij się, że Twoja obecna grupa klientów, produkt lub kategoria jest uwzględniona w regule „pokaż” lub nie jest wykluczona przez regułę „ukryj”.
-   **Wyczyść pamięć podręczną:** Zawsze wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) po wprowadzeniu zmian w konfiguracji modułu. Wyczyść również pamięć podręczną przeglądarki.
-   **Konflikty motywów:** Niektóre wysoce spersonalizowane motywy mogą powodować konflikty. Spróbuj tymczasowo przełączyć się na domyślny motyw PrestaShop Classic, aby sprawdzić, czy ceny się pojawiają. Jeśli tak, jest to konflikt CSS lub JS związany z motywem.

**P2: Ceny są wyświetlane, ale wyglądają na źle wyrównane lub mają nieprawidłową stylizację.**
O:

-   **Użyj CSS motywu Classic:** Jeśli Twój motyw jest oparty na domyślnym motywie PrestaShop Classic, spróbuj włączyć opcję „Użyj CSS motywu Classic (BF\_CLASSICCSS)” w konfiguracji modułu.
-   **Niestandardowy CSS:** Jeśli masz niestandardowy motyw, może być konieczne dodanie niestandardowego CSS. Użyj narzędzi deweloperskich przeglądarki (F12), aby zidentyfikować klasy CSS elementów cenowych modułu. Następnie użyj pola „Własny CSS (BF\_OWNCSS)” w konfiguracji modułu, aby dodać swoje reguły stylów.
-   **Pozycja modułu:** Upewnij się, że moduł jest prawidłowo podpięty. Chociaż moduł obsługuje większość hooków automatycznie, czasami mogą być potrzebne hooki specyficzne dla motywu.

**P3: Ceny nie aktualizują się, gdy zmieniam atrybuty produktu (np. rozmiar, kolor) na stronie produktu.**
O:

-   **Kompatybilność modułu:** Upewnij się, że Twoja wersja PrestaShop mieści się w obsługiwanym zakresie.
-   **Konflikty JavaScript:** Jest to często spowodowane konfliktami JavaScript z Twoim motywem lub innym modułem. Sprawdź konsolę przeglądarki (F12 > zakładka Konsola) pod kątem błędów JavaScript podczas zmiany atrybutów.
-   **Nadpisywanie motywu:** Jeśli Twój motyw mocno nadpisuje domyślny JavaScript strony produktu PrestaShop, może to uniemożliwić modułowi wykrywanie zmian cen. Skontaktuj się z deweloperem motywu lub webmasterem w celu uzyskania pomocy.
-   **Wyczyść pamięć podręczną:** Wyczyść pamięć podręczną PrestaShop i przeglądarki.

**P4: Jak przetłumaczyć etykiety cen (np. „Cena brutto”, „Cena netto”) na inne języki?**
O:

-   Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
-   Wybierz „Tłumaczenia zainstalowanych modułów”.
-   Wybierz swój motyw.
-   Wybierz swój język.
-   Znajdź moduł „Pokaż dwie ceny - z podatkiem / bez podatku” na liście.
-   Znajdziesz pola dla „Etykieta ceny z podatkiem”, „Etykieta ceny bez podatku” itp., zarówno dla stron produktów, jak i list. Wprowadź tam swoje tłumaczenia i zapisz.

**P5: Chcę wyświetlać ceny bez podatku tylko dla konkretnych grup klientów (np. B2B). Jak to zrobić?**
O:

-   W konfiguracji modułu ustaw **„Regułę widoczności”** na „Pokaż tylko dla wybranych grup”.
-   Następnie wybierz konkretne grupy klientów (np. „Hurtowi”, „B2B”), które powinny widzieć podwójne ceny.
-   Opcjonalnie ustaw **„Pokaż typy cen”** na „Tylko bez podatku”, jeśli chcesz całkowicie ukryć cenę z podatkiem dla tych grup.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Pokaż dwie ceny - z podatkiem / bez podatku” (`bothprices`) to standardowy moduł PrestaShop zgodny z wzorcem MVC. Głównie rozszerza klasę `Module`, wykorzystując system hooków PrestaShop do wstrzykiwania informacji o cenach i modyfikowania wyświetlania. Wykorzystuje dedykowany kontroler administracyjny do funkcji wyszukiwania produktów oraz kontrolery front-office do interakcji AJAX. Moduł opiera się na szablonach Smarty do renderowania oraz niestandardowym JavaScript/CSS do dynamicznych aktualizacji i stylizacji. Konfiguracja jest przechowywana w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/ajax.php`
        -   **Nazwa klasy i klasa nadrzędna**: `BothpricesAjaxModuleFrontController` rozszerza `ModuleFrontController`.
        -   **Odpowiedzialność**: Obsługuje żądania AJAX z front-office, głównie w celu dynamicznej aktualizacji cen po zmianie atrybutów produktu. Prawdopodobnie pobiera informacje o produkcie i oblicza ceny na podstawie wybranych atrybutów i kontekstu klienta, zwracając dane JSON.
    -   `controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: `BothpricesIndexModuleFrontController` rozszerza `ModuleFrontController`.
        -   **Odpowiedzialność**: Jest to kontroler zastępczy lub awaryjny. W wielu modułach kontrolery `index.php` są używane do podstawowego routingu lub do zapobiegania listowaniu katalogów. Może nie mieć znaczącej niestandardowej logiki poza podstawowym wysyłaniem.
-   **Kontrolery administracyjne Back-Office**:

    -   `controllers/admin/AdminBothpricesSearchController.php`
        -   **Nazwa klasy i klasa nadrzędna**: `AdminBothpricesSearchController` rozszerza `ModuleAdminController`.
        -   **Nazwa zakładki i zarządzana encja**: Ten kontroler zarządza wyszukiwaniem i wyborem produktów dla reguł widoczności modułu. Nie zarządza bezpośrednio konkretnym `ObjectModel`, ale wchodzi w interakcje z danymi `Product` w celu wyboru. Zapewnia interfejs podobny do siatki do wyszukiwania i dodawania/usuwania produktów z konfiguracji `bp_visibility_products`.

### 4.3 Klasy i modele podstawowe (`classes/`)

Moduł nie wydaje się definiować żadnych niestandardowych klas `ObjectModel` w katalogu `classes/`. Prawdopodobnie opiera się na istniejących klasach PrestaShop `Product` i `Configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `bothprices/lib/searchTool/views/js/autocomplete.js`
    -   **Zakres**: Back-office.
    -   **Opis**: Zapewnia funkcjonalność autouzupełniania dla pola wyszukiwania produktów w `AdminBothpricesSearchController`, umożliwiając administratorom szybkie znajdowanie i wybieranie produktów dla reguł widoczności.
-   `bothprices/views/js/both-hide-p.js`
    -   **Zakres**: Front-office (strona produktu).
    -   **Opis**: Zawiera logikę JavaScript do ukrywania ceny z podatkiem specjalnie na stronie produktu, na podstawie ustawienia konfiguracyjnego `BOTH_HIDE_P`. Prawdopodobnie celuje w konkretne elementy DOM, aby zastosować `display: none` lub podobną stylizację.
-   `bothprices/views/js/both-hide-pl.js`
    -   **Zakres**: Front-office (strony z listą produktów).
    -   **Opis**: Podobnie jak `both-hide-p.js`, ale dla stron z listą produktów, ukrywając cenę z podatkiem na podstawie konfiguracji `BOTH_HIDE_PL`.
-   `bothprices/views/js/bothprices-admin.js`
    -   **Zakres**: Back-office.
    -   **Opis**: Zawiera ogólny JavaScript dla strony konfiguracji modułu w back-office. Może to obejmować logikę pokazywania/ukrywania pól konfiguracyjnych na podstawie innych wyborów (np. zmian reguł widoczności), walidację formularzy lub wywołania AJAX do zapisywania ustawień.
-   `bothprices/views/js/bothprices.js`
    -   **Zakres**: Front-office (globalny).
    -   **Opis**: Jest to główny plik JavaScript front-office. Jest odpowiedzialny za:
        -   Nasłuchiwanie zdarzeń `prestashop.on('updateProduct', ...)` lub podobnych, aby wykrywać zmiany atrybutów produktu.
        -   Wykonywanie wywołań AJAX do `controllers/front/ajax.php` w celu pobrania zaktualizowanych podwójnych cen.
        -   Dynamiczną aktualizację wyświetlanych cen z podatkiem i bez podatku na stronie produktu i potencjalnie na stronach z listą.
        -   Stosowanie niestandardowych CSS lub klas na podstawie ustawień modułu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `bothprices/lib/searchTool/views/css/autocomplete.css`
    -   **Zakres**: Back-office.
    -   **Opis**: Style dla rozwijanej listy autouzupełniania i wyników wyszukiwania w interfejsie `AdminBothpricesSearchController`.
-   `bothprices/views/css/admin.css`
    -   **Zakres**: Back-office.
    -   **Opis**: Ogólna stylizacja strony konfiguracji modułu w Panelu administracyjnym PrestaShop, zapewniająca spójny wygląd z panelem administracyjnym.
-   `bothprices/views/css/bothprices.css`
    -   **Zakres**: Front-office (globalny).
    -   **Opis**: Zawiera domyślne reguły CSS do wyświetlania podwójnych cen zarówno na stronach produktów, jak i na stronach z listą. Obejmuje to podstawowe formatowanie, pozycjonowanie i rozróżnianie dwóch elementów cenowych.
    -   **Kluczowe selektory klas CSS**: Deweloperzy mogą szukać klas takich jak `.bothprices_price_tax_incl`, `.bothprices_price_tax_excl`, `.bothprices_wrapper`, aby je nadpisać.
-   `bothprices/views/css/classic.css`
    -   **Zakres**: Front-office (specyficzny dla motywu Classic).
    -   **Opis**: Zawiera dodatkowe lub nadpisujące reguły CSS specjalnie zaprojektowane w celu poprawy integracji wizualnej z domyślnym motywem PrestaShop Classic lub motywami na nim opartymi. Ten plik jest ładowany warunkowo na podstawie ustawienia `BF_CLASSICCSS`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `bothprices/views/templates/bothprices.tpl`
        -   **Hook**: Prawdopodobnie renderowany w hookach takich jak `displayProductPriceBlock`, `displayProductListReviews`, `displayProductPriceBlock`, `displayProductPriceBlock`, `displayAfterProductThumbs` lub podobnych, zarówno na stronach produktów, jak i list.
        -   **Wyjście**: Ten szablon jest odpowiedzialny za renderowanie rzeczywistej struktury HTML podwójnego wyświetlania cen (ceny z podatkiem i bez podatku) wraz z ich etykietami. Otrzymuje zmienne cenowe z logiki PHP modułu.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `bothprices/views/templates/admin/configure_shell.tpl`
        -   **Hook**: Renderowany w metodzie `getContent()` modułu dla głównej strony konfiguracji.
        -   **Wyjście**: Działa jako wrapper lub powłoka dla formularza konfiguracji modułu, potencjalnie zawierając zakładki, nagłówki i stopki dla interfejsu administracyjnego.
    -   `bothprices/views/templates/selectedProducts.tpl`
        -   **Hook**: Używany przez `AdminBothpricesSearchController`.
        -   **Wyjście**: Renderuje listę produktów, które zostały wybrane dla reguł widoczności, zazwyczaj w formacie tabeli lub listy w interfejsie wyszukiwania administracyjnego.
-   **Szablony Front-office (`views/templates/front/`)**:
    -   `bothprices/views/templates/bothprices-product-page.tpl`
        -   **Hook**: Prawdopodobnie renderowany na stronie produktu, być może w `displayProductPriceBlock` lub podobnym.
        -   **Wyjście**: Specyficzny szablon dla podwójnego wyświetlania cen na stronie produktu, potencjalnie z bardziej szczegółowymi informacjami lub innym układem w porównaniu do stron z listą.
-   **Szablony biblioteczne (`lib/searchTool/views/scripts.tpl`)**:
    -   `bothprices/lib/searchTool/views/scripts.tpl`
        -   **Hook**: Prawdopodobnie zawarty w widoku `AdminBothpricesSearchController`.
        -   **Wyjście**: Zawiera skrypty inicjalizacyjne JavaScript lub zmienne konfiguracyjne dla narzędzia wyszukiwania z autouzupełnianiem.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł używa głównie tabeli `ps_configuration` PrestaShop do przechowywania swoich ustawień. Klucze konfiguracyjne obejmują: `mypresta_updates`, `update_`, `updatev_`, `BOTH_HIDE_PL_CSS`, `BOTH_HIDE_P_CSS`, `BF_PP`, `BF_PL`, `bp_visibility_rule`, `bp_visibility_products`, `bp_visibility_cat`, `BF_SHOW_TYPES`, `BF_PLC`, `BF_PPC`, `BP_FORCE_HIDE`, `BP_PP_TPERCENT_TEXL`, `BP_PP_TPERCENT`, `BP_PL_TPERCENT_TEXL`, `BP_PL_TPERCENT`, `BOTH_HIDE_PL`, `BOTH_HIDE_P`, `BF_OWNCSS`, `BF_CLASSICCSS`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `BP_TIN`, `BP_TIN_L`, `BP_TEX`, `BP_TEX_L`, `BP_TINL`, `BP_TINL_L`, `BP_TEXL`, `BP_TEXL_L`, `BP_O_TIN`, `BP_O_TIN_L`, `BP_O_TEX`.
    -   Nie wydaje się tworzyć żadnych niestandardowych tabel SQL.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Zakres | Czas wykonania | Cel techniczny |
| --- | --- | --- | --- |
| `ActionFrontControllerSetMedia` | Front-Office | Przed wyjściem kontrolera, po inicjalizacji mediów. | Wstrzykuje zasoby CSS i JS modułu do front-office. |
| `ActionAdminGroupsControllerSaveAfter` | Back-Office | Po zapisaniu grupy klientów przez administratora. | Potencjalnie używane do czyszczenia pamięci podręcznej lub ponownej oceny reguł widoczności związanych z grupami klientów. |
| `ActionAdminControllerSetMedia` | Back-Office | Przed wyjściem kontrolera administracyjnego, po inicjalizacji mediów. | Wstrzykuje zasoby CSS i JS modułu do back-office (np. dla strony konfiguracji, kontrolera wyszukiwania). |
| `updateproduct` | Back-Office | Po zaktualizowaniu produktu. | Czyści odpowiednie pamięci podręczne, ponownie ocenia dane cenowe specyficzne dla produktu. |
| `ActionProductDelete` | Back-Office | Po usunięciu produktu. | Czyści wszelkie dane specyficzne dla modułu związane z usuniętym produktem (np. z `bp_visibility_products`). |
| `displayUpdateProduct` | Back-Office | Na stronie edycji produktu. | Potencjalnie wstrzykuje niestandardowe pola lub informacje do formularza edycji produktu. |
| `actionProductUpdate` | Back-Office | Po zaktualizowaniu produktu. | Podobnie jak `updateproduct`, zapewnia, że wewnętrzne dane modułu odzwierciedlają zmiany produktu. |
| `displayHeader` | Front-Office | W sekcji `<head>` każdej strony front-office. | Wstrzykuje CSS i JS modułu dla globalnej dostępności lub renderuje mały fragment. |
| `displayCategoryUpdate` | Back-Office | Na stronie edycji kategorii. | Potencjalnie wstrzykuje niestandardowe pola lub informacje do formularza edycji kategorii. |
| `ActionCategoryUpdate` | Back-Office | Po zaktualizowaniu kategorii. | Czyści odpowiednie pamięci podręczne, ponownie ocenia dane cenowe specyficzne dla kategorii. |
| `actionProductAdd` | Back-Office | Po dodaniu nowego produktu. | Inicjalizuje dane specyficzne dla modułu dla nowego produktu. |
| `actionObjectSpecificPriceUpdateAfter` | Back-Office | Po zaktualizowaniu ceny specyficznej (rabatu). | Zapewnia, że dynamiczne obliczenia cen odzwierciedlają nowe ceny specyficzne. |
| `categoryUpdate` | Back-Office | Po zaktualizowaniu kategorii. | Alias lub duplikat `ActionCategoryUpdate`. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Pokaż dwie ceny - z podatkiem / bez podatku”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
