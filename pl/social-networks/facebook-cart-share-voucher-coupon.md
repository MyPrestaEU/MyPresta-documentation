---
title: "Udostępnianie koszyka na Facebooku + kupon rabatowy - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Udostępnianie koszyka na Facebooku + kupon rabatowy” od MyPresta.eu."
sidebar:
  label: "Udostępnianie koszyka na Facebooku + kupon rabatowy"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook cart share + voucher coupon na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-cart-share-voucher-coupon.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-cart-share-voucher-coupon/)
>
> ---


# Udostępnianie koszyka na Facebooku + kupon rabatowy

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do interakcji z PrestaShop i API Facebooka.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
To jest główny ekran konfiguracji modułu „Udostępnianie koszyka na Facebooku + kupon rabatowy”. Znajdziesz go, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Udostępnianie koszyka na Facebooku + kupon rabatowy” i klikając „Konfiguruj”.

#### **Ustawienia ogólne**

-   **ID aplikacji Facebooka (cshare_appid / cshare_app_id)**
    -   **Co robi to ustawienie:** Jest to unikalny identyfikator Twojej aplikacji Facebooka, który jest wymagany, aby moduł mógł komunikować się z API Facebooka. Musisz utworzyć aplikację Facebooka na platformie Facebook Developers (developers.facebook.com), aby uzyskać ten ID.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione poprawnie:* Moduł może pomyślnie połączyć się z Facebookiem, umożliwiając klientom udostępnianie ich koszyków, a Twojemu sklepowi śledzenie tych udostępnień.
        -   *Gdy pozostawione puste lub ustawione niepoprawnie:* Funkcjonalność udostępniania na Facebooku nie będzie działać, a klienci nie będą mogli udostępniać swoich koszyków.
    -   **Zalecana wartość:** Twój unikalny ID aplikacji Facebooka.
    -   **Scenariusz / przykład dla sprzedawcy:** Zarejestrowałeś swój sklep PrestaShop jako aplikację na Facebook Developers i otrzymałeś ID aplikacji, np. `123456789012345`. Wprowadź ten ID tutaj.

-   **Wyświetl przycisk udostępniania na (cshare_lasttab)**
    -   **Co robi to ustawienie:** Określa, gdzie przycisk „Udostępnij koszyk na Facebooku” pojawi się w front-office Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na „Strona koszyka zakupowego” (Shopping Cart Page):* Przycisk pojawia się na stronie, gdzie klienci przeglądają zawartość swojego koszyka przed przejściem do kasy.
        -   *Gdy ustawione na „Strona potwierdzenia zamówienia” (Order Confirmation Page):* Przycisk pojawia się po tym, jak klient pomyślnie złożył zamówienie.
        -   *Gdy ustawione na „Obie” (Both):* Przycisk pojawia się na obu stronach.
    -   **Zalecana wartość:** „Obie”, aby zmaksymalizować widoczność i możliwości udostępniania.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz zachęcić do udostępniania zarówno przed, jak i po zakupie, więc wybierasz „Obie”.

-   **Styl przycisku udostępniania na Facebooku (cshare_button_style)**
    -   **Co robi to ustawienie:** Pozwala wybrać wizualny styl przycisku udostępniania na Facebooku.
    -   **Efekt zmiany tego ustawienia:** Zmienia wygląd przycisku udostępniania, aby lepiej pasował do projektu Twojego sklepu lub Twoich preferencji dotyczących większego/mniejszego przycisku.
    -   **Zalecana wartość:** Eksperymentuj, aby znaleźć to, co najlepiej wygląda z Twoim motywem.
    -   **Scenariusz / przykład dla sprzedawcy:** Twój motyw ma minimalistyczny design, więc możesz wybrać prosty, tekstowy przycisk udostępniania zamiast dużego, graficznego.

#### **Ustawienia kuponu**

-   **Włącz generowanie kuponów (cshare_voucher)**
    -   **Co robi to ustawienie:** Włącza lub wyłącza generowanie i oferowanie kuponu rabatowego klientowi po pomyślnym udostępnieniu koszyka na Facebooku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Unikalny kod kuponu jest tworzony i wyświetlany klientowi po udostępnieniu.
        -   *Gdy wyłączone:* Nie jest generowany ani oferowany żaden kupon, co usuwa bezpośrednią zachętę do udostępniania.
    -   **Zalecana wartość:** „TAK”, aby wykorzystać zachętę do udostępniania i zwiększyć konwersje.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz nagradzać klientów za udostępnianie i zachęcać do ponownych zakupów, więc włączasz tę opcję.

-   **Rodzaj kuponu (cshare_gift)**
    -   **Co robi to ustawienie:** Definiuje typ i wartość kuponu rabatowego, który otrzymują klienci. Odpowiada to ustawieniom „Typ rabatu” i „Wartość” podczas tworzenia nowej reguły koszyka w PrestaShop.
    -   **Efekt zmiany tego ustawienia:**
        -   *Stała kwota:* Klient otrzymuje określoną zniżkę pieniężną (np. 5 zł zniżki).
        -   *Procent:* Klient otrzymuje zniżkę procentową (np. 10% zniżki).
        -   *Darmowa wysyłka:* Klient otrzymuje darmową wysyłkę przy następnym zamówieniu.
    -   **Zalecana wartość:** Wartość, która jest wystarczająco atrakcyjna, aby zachęcić do udostępniania, ale także zrównoważona dla Twojej firmy.
    -   **Scenariusz / przykład dla sprzedawcy:** Decydujesz się zaoferować „10% zniżki”, aby zachęcić do nowych zakupów, więc wybierasz „Procent” i ustawiasz wartość w następnym polu.

-   **Wartość kuponu (cshare_image)**
    -   **Co robi to ustawienie:** Ustawia konkretną wartość kuponu, w zależności od wybranego typu „Rodzaju kuponu”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli wybrano „Stała kwota”:* Będzie to dokładna wartość pieniężna rabatu.
        -   *Jeśli wybrano „Procent”:* Będzie to procent rabatu.
    -   **Zalecana wartość:** Atrakcyjny rabat (np. 5, 10, 15 dla procentu; 5, 10, 20 dla stałej kwoty).
    -   **Scenariusz / przykład dla sprzedawcy:** Wybrałeś „Procent” dla „Rodzaju kuponu”, więc tutaj wpisujesz „10” dla 10% zniżki.

#### **Ustawienia udostępnianej treści**

Te ustawienia kontrolują, jakie informacje o koszyku klienta są zawarte w poście na Facebooku, gdy go udostępnia.

-   **Pokaż ceny (cshare_show_prices)**
    -   **Co robi to ustawienie:** Określa, czy indywidualne ceny produktów w koszyku są wyświetlane w poście udostępnianym na Facebooku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Każdy produkt wymieniony w udostępnionym koszyku pokaże swoją cenę.
        -   *Gdy wyłączone:* Ceny produktów zostaną pominięte w udostępnionym poście.
    -   **Zalecana wartość:** „TAK”, aby zapewnić przejrzystość i zachęcić do kliknięć, chyba że Twoja strategia cenowa wymaga inaczej.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby potencjalni klienci widzieli wartość przedmiotów, więc włączasz „Pokaż ceny”.

-   **Pokaż sumę (cshare_show_total)**
    -   **Co robi to ustawienie:** Określa, czy całkowita wartość koszyka zakupowego jest wyświetlana w poście udostępnianym na Facebooku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Zostanie wyświetlona całkowita cena wszystkich przedmiotów w koszyku.
        -   *Gdy wyłączone:* Suma koszyka nie zostanie uwzględniona w poście.
    -   **Zalecana wartość:** „TAK”, aby zapewnić jasny przegląd wartości koszyka.
    -   **Scenariusz / przykład dla sprzedawcy:** Klient ma koszyk o wartości 250 zł, a Ty chcesz, aby jego znajomi zobaczyli ten znaczący zakup, więc włączasz „Pokaż sumę”.

-   **Pokaż produkty (cshare_show_products)**
    -   **Co robi to ustawienie:** Określa, czy nazwy i ilości poszczególnych produktów w koszyku są wymienione w poście udostępnianym na Facebooku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Lista produktów (np. „T-shirt x1, Jeansy x1”) pojawi się w poście.
        -   *Gdy wyłączone:* Pojawi się tylko ogólna wiadomość o udostępnianiu koszyka, bez szczegółowych informacji o produkcie.
    -   **Zalecana wartość:** „TAK”, aby zaprezentować konkretne przedmioty i wzbudzić zainteresowanie.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz podkreślić konkretne produkty, które klient kupuje, więc włączasz „Pokaż produkty”.

-   **Pokaż URL produktu (cshare_show_product_url)**
    -   **Co robi to ustawienie:** Określa, czy bezpośrednie linki do indywidualnych stron produktów są zawarte w poście udostępnianym na Facebooku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Każdy wymieniony produkt będzie miał klikalny link do swojej strony w Twoim sklepie.
        -   *Gdy wyłączone:* Nazwy produktów będą wyświetlane, ale bez bezpośrednich linków.
    -   **Zalecana wartość:** „TAK”, aby kierować ruch bezpośrednio na strony produktów.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby znajomi udostępniającego mogli łatwo kliknąć i zobaczyć produkty, więc włączasz „Pokaż URL produktu”.

#### **Ustawienia zaawansowane**

-   **Wymuś HTTPS (cshare_http)**
    -   **Co robi to ustawienie:** Zapewnia, że wszystkie adresy URL generowane do udostępniania na Facebooku używają HTTPS, nawet jeśli Twoja konfiguracja PrestaShop może czasami domyślnie używać HTTP. Jest to kluczowe dla bezpieczeństwa i wymagań Facebooka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Wszystkie udostępnione linki będą bezpieczne (HTTPS).
        -   *Gdy wyłączone:* Linki mogą czasami być HTTP, co może powodować problemy z API Facebooka i ostrzeżenia bezpieczeństwa.
    -   **Zalecana wartość:** „TAK”, jeśli Twój sklep używa HTTPS (co powinien!).
    -   **Scenariusz / przykład dla sprzedawcy:** Cały Twój sklep działa na HTTPS, więc włączasz tę opcję, aby zapewnić spójność i uniknąć ostrzeżeń przeglądarki.

-   **Nazwa sklepu PrestaShop (PS_SHOP_NAME)**
    -   **Co robi to ustawienie:** To pole zazwyczaj pobiera nazwę Twojego sklepu z ogólnych ustawień PrestaShop. Jest używane w udostępnianym poście na Facebooku.
    -   **Efekt zmiany tego ustawienia:** Zapewnia wyświetlanie poprawnej nazwy sklepu w poście na Facebooku.
    -   **Zalecana wartość:** Pozostaw jako domyślne (powinno automatycznie wypełnić się z Twojej konfiguracji PrestaShop).
    -   **Scenariusz / przykład dla sprzedawcy:** Twój sklep nazywa się „Mój Niesamowity Sklep”, a to pole poprawnie wyświetla „Mój Niesamowity Sklep”.

-   **E-mail sklepu PrestaShop (PS_SHOP_EMAIL)**
    -   **Co robi to ustawienie:** To pole zazwyczaj pobiera adres e-mail kontaktowy Twojego sklepu z ogólnych ustawień PrestaShop. Może być używane do wewnętrznych operacji modułu lub w generowanej treści.
    -   **Efekt zmiany tego ustawienia:** Zapewnia użycie poprawnego adresu e-mail, jeśli moduł musi się do niego odwołać.
    -   **Zalecana wartość:** Pozostaw jako domyślne (powinno automatycznie wypełnić się z Twojej konfiguracji PrestaShop).
    -   **Scenariusz / przykład dla sprzedawcy:** Adres e-mail kontaktowy Twojego sklepu to `info@mojniezwyklysklep.com`, a to pole poprawnie go wyświetla.

-   **Podatek PrestaShop (PS_TAX)**
    -   **Co robi to ustawienie:** To pole zazwyczaj pobiera domyślne ustawienie podatku Twojego sklepu. Może być używane do poprawnego obliczania cen w udostępnianej treści.
    -   **Efekt zmiany tego ustawienia:** Zapewnia prawidłowe uwzględnienie podatków, jeśli ceny są wyświetlane.
    -   **Zalecana wartość:** Pozostaw jako domyślne (powinno automatycznie wypełnić się z Twojej konfiguracji PrestaShop).
    -   **Scenariusz / przykład dla sprzedawcy:** Twój sklep działa z 20% VAT, a to pole to odzwierciedla.

#### **Wewnętrzne ustawienia modułu (Zazwyczaj pozostaw jako domyślne)**

-   **Aktualizacje MyPresta.eu (mypresta_updates, update_, updatev_)**
    -   **Co robi to ustawienie:** Są to wewnętrzne ustawienia używane przez moduły MyPresta.eu do sprawdzania aktualizacji i zapewnienia kompatybilności.
    -   **Efekt zmiany tego ustawienia:** Modyfikacja tych ustawień może zakłócić zdolność modułu do otrzymywania aktualizacji lub prawidłowego działania.
    -   **Zalecana wartość:** Pozostaw jako domyślne.
    -   **Scenariusz / przykład dla sprzedawcy:** Zazwyczaj nie musisz z nimi wchodzić w interakcje.

-   **Inicjalizacja Facebooka (cshare_fbinit)**
    -   **Co robi to ustawienie:** Wewnętrzna flaga wskazująca, czy SDK Facebooka zostało zainicjalizowane.
    -   **Efekt zmiany tego ustawienia:** Modyfikacja tego może uniemożliwić prawidłowe ładowanie funkcji udostępniania na Facebooku.
    -   **Zalecana wartość:** Pozostaw jako domyślne.
    -   **Scenariusz / przykład dla sprzedawcy:** Jest to ustawienie techniczne, nieprzeznaczone do interakcji ze sprzedawcą.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów
Ten moduł nie wprowadza żadnych dedykowanych niestandardowych ekranów administracyjnych ani kontrolerów poza swoją główną stroną konfiguracji. Wszystkie ustawienia są zarządzane bezpośrednio w standardowym interfejsie konfiguracji modułu.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Konfiguracja modułu | ID aplikacji Facebooka | Twój unikalny ID aplikacji | Niezbędne do połączenia z API Facebooka; udostępnianie nie będzie działać bez niego. |
| Konfiguracja modułu | Wyświetl przycisk udostępniania na | Obie | Kontroluje, gdzie pojawia się przycisk udostępniania (Koszyk, Potwierdzenie zamówienia lub oba). |
| Konfiguracja modułu | Styl przycisku udostępniania na Facebooku | (Różne) | Zmienia wygląd wizualny przycisku udostępniania. |
| Konfiguracja modułu | Włącz generowanie kuponów | TAK | Włącza lub wyłącza tworzenie i wyświetlanie kuponu rabatowego po udostępnieniu. |
| Konfiguracja modułu | Rodzaj kuponu | Procent / Stała kwota | Definiuje typ rabatu (np. 10% zniżki, 5 zł zniżki, Darmowa wysyłka). |
| Konfiguracja modułu | Wartość kuponu | (Twoja pożądana wartość) | Ustawia konkretną wartość dla wybranego typu kuponu. |
| Konfiguracja modułu | Pokaż ceny | TAK | Zawiera indywidualne ceny produktów w poście udostępnianym na Facebooku. |
| Konfiguracja modułu | Pokaż sumę | TAK | Zawiera całkowitą wartość koszyka w poście udostępnianym na Facebooku. |
| Konfiguracja modułu | Pokaż produkty | TAK | Wyświetla nazwy i ilości poszczególnych produktów w poście udostępnianym na Facebooku. |
| Konfiguracja modułu | Pokaż URL produktu | TAK | Dodaje bezpośrednie linki do stron produktów w poście udostępnianym na Facebooku. |
| Konfiguracja modułu | Wymuś HTTPS | TAK | Zapewnia, że wszystkie udostępnione linki są bezpieczne (HTTPS). |
| Konfiguracja modułu | Nazwa sklepu PrestaShop | (Automatycznie wypełniane) | Wyświetla nazwę Twojego sklepu w poście na Facebooku. |
| Konfiguracja modułu | E-mail sklepu PrestaShop | (Automatycznie wypełniane) | Adres e-mail kontaktowy sklepu. |
| Konfiguracja modułu | Podatek PrestaShop | (Automatycznie wypełniane) | Domyślne ustawienie podatku sklepu. |
| Konfiguracja modułu | Aktualizacje MyPresta.eu | (Wewnętrzne) | Wewnętrzne ustawienia aktualizacji modułu. |
| Konfiguracja modułu | Inicjalizacja Facebooka | (Wewnętrzne) | Wewnętrzna flaga inicjalizacji SDK Facebooka. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Przycisk udostępniania na Facebooku nie pojawia się na mojej stronie koszyka/potwierdzenia zamówienia.**
*   **O:** Najpierw sprawdź konfigurację modułu w Panelu administracyjnym (**Moduły > Menedżer modułów > Konfiguruj Udostępnianie koszyka na Facebooku + kupon rabatowy**). Upewnij się, że opcja „Wyświetl przycisk udostępniania na” jest ustawiona poprawnie (np. „Strona koszyka zakupowego”, „Strona potwierdzenia zamówienia” lub „Obie”). Sprawdź również, czy Twój ID aplikacji Facebooka jest poprawnie wprowadzony. Jeśli nadal się nie wyświetla, wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**).

**P2: Gdy klienci klikają przycisk udostępniania, nic się nie dzieje lub otrzymują błąd.**
*   **O:** To prawie zawsze wskazuje na problem z Twoim ID aplikacji Facebooka lub samą konfiguracją aplikacji Facebooka.
    1.  **Sprawdź dwukrotnie swój ID aplikacji Facebooka:** Upewnij się, że jest poprawnie wprowadzony w konfiguracji modułu.
    2.  **Zweryfikuj ustawienia aplikacji Facebooka:** Zaloguj się na [developers.facebook.com](https://developers.facebook.com/). Upewnij się, że Twoja aplikacja jest „Aktywna” (nie w trybie deweloperskim). Sprawdź sekcję „Ustawienia > Podstawowe” dla Twojej aplikacji: pola „Domeny aplikacji” i „Strona internetowa” muszą dokładnie zawierać domenę Twojego sklepu (np. `twojasklep.com` i `https://www.twojasklep.com`).
    3.  **Wymuś HTTPS:** Upewnij się, że opcja „Wymuś HTTPS” w konfiguracji modułu jest ustawiona na „TAK”, jeśli Twój sklep używa HTTPS.

**P3: Kupony nie są generowane po pomyślnym udostępnieniu.**
*   **O:**
    1.  **Sprawdź „Włącz generowanie kuponów”:** W konfiguracji modułu upewnij się, że to ustawienie jest ustawione na „TAK”.
    2.  **Rodzaj kuponu i wartość:** Upewnij się, że wybrałeś typ „Rodzaju kuponu” (np. Procent, Stała kwota) i wprowadziłeś prawidłową „Wartość kuponu”.
    3.  **Limity reguł koszyka PrestaShop:** PrestaShop ma limity dotyczące liczby reguł koszyka. Chociaż jest to mało prawdopodobne dla tego modułu, jeśli masz bardzo dużą liczbę udostępnień, upewnij się, że Twój serwer może obsłużyć tworzenie nowych reguł koszyka.
    4.  **Logi błędów:** Sprawdź logi błędów PrestaShop (zazwyczaj w `var/logs/` lub `app/logs/` dla PS 1.7+) pod kątem wszelkich powiązanych błędów podczas procesu generowania kuponów.

**P4: Udostępniona treść na Facebooku nie wygląda poprawnie (np. brakujące ceny, złe zdjęcie).**
*   **O:**
    1.  **Ustawienia modułu:** Przejrzyj „Ustawienia udostępnianej treści” w konfiguracji modułu (Pokaż ceny, Pokaż sumę, Pokaż produkty, Pokaż URL produktu). Upewnij się, że wszystkie są ustawione na „TAK”, jeśli chcesz uzyskać maksymalną szczegółowość.
    2.  **Facebook Open Graph:** Facebook używa tagów Open Graph (OG) ze stron Twoich produktów do generowania podglądów. Upewnij się, że Twój motyw PrestaShop i inne moduły poprawnie generują te tagi OG (zwłaszcza `og:image`, `og:title`, `og:description`). Możesz użyć [Narzędzia do debugowania udostępniania Facebooka](https://developers.facebook.com/tools/debug/), aby zobaczyć, jak Facebook skanuje Twoje adresy URL.
    3.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop i pamięć podręczną przeglądarki. Facebook również buforuje udostępniane treści, więc użyj Narzędzia do debugowania udostępniania, aby „Skanować ponownie”, jeśli wprowadziłeś zmiany.

**P5: Moduł nie wygląda dobrze z moim niestandardowym motywem.**
*   **O:** Moduł używa własnych plików CSS (`css.css`, `ps16.css`). Twój niestandardowy motyw może nadpisywać lub kolidować z tymi stylami.
    1.  **Zbadaj element:** Użyj narzędzi deweloperskich przeglądarki (F12), aby zbadać przycisk udostępniania i wyświetlanie kuponu. Zidentyfikuj klasy CSS zastosowane przez moduł i Twój motyw.
    2.  **Niestandardowy CSS:** Możesz dodać niestandardowy CSS do pliku `custom.css` (lub równoważnego) swojego motywu, aby nadpisać style modułu i lepiej dopasować go do swojego motywu. Celuj w konkretne klasy modułu, aby uniknąć wpływania na inne części Twojego sklepu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury
Moduł „Udostępnianie koszyka na Facebooku + kupon rabatowy” wykorzystuje standardową architekturę modułów PrestaShop, głównie klasę `Module` i `ModuleFrontController` do interakcji z front-office. Integruje się z JavaScript SDK Facebooka dla funkcji udostępniania i używa obiektu `CartRule` PrestaShop do generowania kuponów. Konfiguracja jest zarządzana za pomocą metody `getContent()` w głównym pliku modułu, przechowując ustawienia w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:
    *   `cartshare/controllers/front/cartshare.php`
        *   **Nazwa klasy i klasa nadrzędna:** `CartshareCartshareModuleFrontController` rozszerza `ModuleFrontController`.
        *   **Odpowiedzialność:** Ten kontroler jest prawdopodobnie odpowiedzialny za obsługę wywołania zwrotnego AJAX z Facebooka po udostępnieniu lub za renderowanie dedykowanej strony udostępniania koszyka, jeśli moduł taką posiada. Przetwarzałby zdarzenie udostępniania i uruchamiał logikę generowania kuponów. Może być również odpowiedzialny za renderowanie szablonu `cartsharepage.tpl`.
    *   `cartshare/controllers/front/index.php`
        *   **Nazwa klasy i klasa nadrzędna:** Jest to zazwyczaj pusty plik lub proste przekierowanie, aby zapobiec listowaniu katalogów, co jest powszechne w modułach PrestaShop. Nie zawiera konkretnej klasy kontrolera.
        *   **Odpowiedzialność:** Środek bezpieczeństwa zapobiegający bezpośredniemu dostępowi do katalogu `front`.

-   **Kontrolery Back-Office Admin**:
    *   Brak. Cała administracja jest obsługiwana za pomocą metody `getContent()` głównej klasy modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)
Ten moduł nie wydaje się definiować żadnych niestandardowych klas ani `ObjectModel` w katalogu `classes/`. Jego podstawowa logika generowania kuponów prawdopodobnie bezpośrednio współdziała z klasą `CartRule` PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `cartshare/lib/voucherengine/script.js`
    *   **Zakres:** Front-office.
    *   **Szczegóły:** Ten skrypt jest kluczowy dla interakcji po stronie klienta. Prawdopodobnie inicjalizuje Facebook JavaScript SDK, używając `cshare_appid` z konfiguracji modułu. Wiąże słuchaczy zdarzeń z przyciskiem „Udostępnij na Facebooku”, obsługuje okno dialogowe udostępniania na Facebooku, a po pomyślnym udostępnieniu wykonuje wywołanie AJAX do kontrolera frontowego `cartshare.php`, aby uruchomić generowanie kuponów i wyświetlić kod kuponu użytkownikowi. Może również obsługiwać dynamiczne wyświetlanie kodu kuponu na stronie.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `cartshare/css.css`
    *   **Zakres:** Front-office.
    *   **Szczegóły:** Zawiera ogólne style dla elementów modułu, takich jak przycisk udostępniania, obszar wyświetlania kuponu i wszelkie inne komponenty interfejsu użytkownika wprowadzone przez moduł.
-   `cartshare/lib/voucherengine/ps16.css`
    *   **Zakres:** Front-office.
    *   **Szczegóły:** Prawdopodobnie zawiera specyficzne dostosowania stylów lub nadpisania dostosowane do motywów PrestaShop 1.6, zapewniając kompatybilność i prawidłowe renderowanie w starszych wersjach.
-   `cartshare/views/css/css/css.css`
    *   **Zakres:** Front-office.
    *   **Szczegóły:** Ta ścieżka wydaje się redundantna (`css/css/`). Możliwe, że jest to duplikat lub starsza wersja `cartshare/css.css`, lub zawiera bardzo specyficzne style dla niektórych elementów. Deweloperzy powinni sprawdzić jej zawartość, aby zrozumieć jej cel.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    *   `cartshare/views/templates/hook/header.tpl`
        *   **Hook:** `displayHeader`
        *   **Wyjście:** Ten szablon jest odpowiedzialny za włączenie kodu inicjalizacji Facebook JavaScript SDK oraz potencjalnie głównych plików JavaScript (`script.js`) i CSS modułu. Zapewnia, że API Facebooka jest gotowe, zanim przycisk udostępniania zostanie wyrenderowany.
    *   `cartshare/views/templates/hook/share.tpl`
        *   **Hook:** `displayShoppingcart`, `displayOrderConfirmation` (w zależności od konfiguracji modułu)
        *   **Wyjście:** Renderuje przycisk „Udostępnij koszyk na Facebooku” i kontener do wyświetlania kodu kuponu po pomyślnym udostępnieniu. Jest to główny komponent wizualny, z którym klienci wchodzą w interakcje.

-   **Szablony Front-office (`views/templates/front/`)**:
    *   `cartshare/views/templates/front/cartsharepage.tpl`
        *   **Cel:** Ten szablon jest prawdopodobnie renderowany przez `CartshareCartshareModuleFrontController` i może być dedykowaną stroną lub częściowym widokiem do wyświetlania zawartości koszyka do udostępnienia lub kodu kuponu.
    *   `cartshare/views/templates/front/facebook-share-contents.tpl`
        *   **Cel:** Ten szablon dynamicznie generuje treść, która zostanie przekazana do okna dialogowego udostępniania na Facebooku. Konstruuje tytuł, opis, obraz i adresy URL na podstawie koszyka klienta i ustawień konfiguracji modułu (np. `cshare_show_prices`, `cshare_show_products`).
    *   `cartshare/views/templates/front/shopping-cart.tpl`
        *   **Cel:** Ten szablon może być nadpisaniem lub dodatkowym blokiem specjalnie zaprojektowanym do włączenia do standardowej strony koszyka zakupowego PrestaShop, potencjalnie w celu renderowania przycisku udostępniania lub innych treści specyficznych dla modułu bezpośrednio w podsumowaniu koszyka.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Ten moduł nie tworzy niestandardowych tabel SQL.
    *   Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration`, używając kluczy takich jak `CSHARE_APPID`, `CSHARE_VOUCHER`, `CSHARE_SHOW_PRICES` itp.
    *   Kupony są generowane jako standardowe wpisy `CartRule` PrestaShop, przechowywane w `ps_cart_rule` i powiązanych tabelach.

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
|---|---|---|
| `displayHeader` | W sekcji `<head>` każdej strony. | Inicjalizuje SDK Facebooka, ładuje zasoby JS/CSS modułu. |
| `displayShoppingcart` | Na stronie podsumowania koszyka zakupowego. | Renderuje przycisk „Udostępnij koszyk na Facebooku” i obszar wyświetlania kuponu. |
| `displayOrderConfirmation` | Na stronie potwierdzenia zamówienia po pomyślnym zakupie. | Renderuje przycisk „Udostępnij koszyk na Facebooku” i obszar wyświetlania kuponu. |
| `displayShoppingCart` | (Duplikat `displayShoppingcart` w informacjach o module, prawdopodobnie odnosi się do tego samego hooka) | Renderuje przycisk „Udostępnij koszyk na Facebooku” i obszar wyświetlania kuponu. |

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Udostępnianie koszyka na Facebooku + kupon rabatowy”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie optymalnego działania modułu z Twoim sklepem PrestaShop.
"""
