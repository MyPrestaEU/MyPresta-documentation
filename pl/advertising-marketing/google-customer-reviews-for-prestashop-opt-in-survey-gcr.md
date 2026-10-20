---
title: "Google Customer Reviews for PrestaShop - opt-in & survey (GCR) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu Google Customer Reviews for PrestaShop - opt-in & survey (GCR) od MyPresta.eu."
sidebar:
  label: "Google Customer Reviews for PrestaShop - opt-in & survey (GCR) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Google Customer Reviews for PrestaShop - opt-in & survey (GCR) na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/google-customer-reviews-for-prestashop-opt-in-survey-gcr.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/google-customer-reviews-for-prestashop-opt-in-survey-gcr/)
>
> ---


# Google Customer Reviews for PrestaShop - opt-in & survey (GCR)

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Aby uzyskać dostęp do ustawień modułu, przejdź do **Moduły > Menedżer modułów**, wyszukaj „Google Customer Reviews” i kliknij przycisk „Konfiguruj”.

#### **Identyfikator sprzedawcy Google (Google Merchant ID)**

-   **Co robi to ustawienie:** Jest to unikalny identyfikator Twojego konta Google Merchant Center. Google używa tego identyfikatora do powiązania zebranych recenzji z Twoją konkretną firmą.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po poprawnym wprowadzeniu:* Skrypt zgody na Google Customer Reviews będzie działał prawidłowo, wysyłając dane recenzji do Twojego konta Google Merchant Center.
    -   *Po niepoprawnym wprowadzeniu lub pozostawieniu pustego:* Skrypt zgody nie będzie działał, a Google nie będzie zbierać recenzji dla Twojego sklepu.
-   **Zalecana wartość:** Twój dokładny identyfikator Google Merchant Center. Możesz znaleźć ten identyfikator, logując się do swojego konta Google Merchant Center (merchant.google.com) – zazwyczaj jest wyświetlany w prawym górnym rogu.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój identyfikator Google Merchant Center to `123456789`, wpiszesz `123456789` w to pole. Bez niego Google nie wie, któremu sprzedawcy przypisać recenzje.

#### **Dołącz listę GTIN produktów do ładunku GCR (Include product GTIN list in GCR payload)**

-   **Co robi to ustawienie:** Ta opcja kontroluje, czy globalne numery identyfikacyjne produktów (GTIN) produktów w zamówieniu klienta są uwzględniane podczas wysyłania danych zgody do Google. GTIN (takie jak EAN, UPC, ISBN) pomagają Google identyfikować konkretne produkty do recenzji na poziomie produktu.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po włączeniu (Tak):* Moduł spróbuje pobrać i uwzględnić GTIN dla każdego produktu w zamówieniu. Pozwala to Google potencjalnie zbierać recenzje specyficzne dla produktu, które mogą pojawiać się na stronach produktów i w Google Shopping.
    -   *Po wyłączeniu (Nie):* Będą zbierane tylko recenzje sprzedawcy. GTIN specyficzne dla produktu nie zostaną wysłane, co oznacza, że Google nie będzie prosić klientów o recenzje poszczególnych produktów z tego zamówienia.
-   **Zalecana wartość:** **Tak**. Włączenie GTIN jest wysoce zalecane, jeśli chcesz zbierać recenzje na poziomie produktu, które są bardzo cenne dla widoczności produktu i zaufania. Upewnij się, że Twoje produkty w PrestaShop mają poprawnie wypełnione pola EAN/UPC.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz „Niebieską koszulkę” z EAN `1234567890123`, włączenie tej opcji zapewnia, że Google wie, *który* produkt kupił klient, co pozwala mu ocenić ten konkretny przedmiot. Jeśli jest wyłączona, Google zapyta tylko o ogólną recenzję Twojego sklepu.

#### **Domyślne przesunięcie dostawy (dni) (Fallback delivery offset (days))**

-   **Co robi to ustawienie:** To ustawienie określa szacowaną liczbę dni po złożeniu zamówienia, w ciągu których klient ma otrzymać dostawę. Google używa tej daty do zaplanowania, kiedy wysłać e-mail z ankietą recenzji.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po ustawieniu na konkretną liczbę (np. 7):* Moduł oblicza szacowaną datę dostawy, dodając tę liczbę dni do daty zamówienia. Google następnie wyśle e-mail z ankietą około tej obliczonej daty dostawy.
    -   *Po ustawieniu na 0 lub bardzo niską liczbę:* Google może wysłać ankietę zbyt wcześnie, zanim klient otrzyma produkt, co prowadzi do nieistotnych lub negatywnych recenzji.
    -   *Po ustawieniu na bardzo wysoką liczbę:* Google może wysłać ankietę zbyt późno, a klient mógł zapomnieć szczegóły swojego doświadczenia zakupowego.
-   **Zalecana wartość:** Zależy to od Twoich średnich czasów wysyłki. Częstym punktem wyjścia jest **7 dni**. Dostosuj to na podstawie rzeczywistej wydajności dostaw.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój średni czas dostawy wynosi 5-7 dni roboczych, ustawienie tej wartości na `7` dni jest odpowiednie. Jeśli wysyłasz międzynarodowo, a dostawy trwają 2-3 tygodnie, możesz ustawić ją na `14` lub `21` dni. Zapewnia to, że ankieta dotrze, gdy klient miał czas na otrzymanie i doświadczenie produktu.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Identyfikator sprzedawcy Google | Twój identyfikator sprzedawcy | Łączy zebrane recenzje z Twoim kontem Google Merchant Center. **KRYTYCZNE dla działania.** |
| Konfiguracja modułu | Dołącz listę GTIN produktów do ładunku GCR | Tak | Umożliwia zbieranie recenzji specyficznych dla produktu poprzez wysyłanie identyfikatorów produktów. |
| Konfiguracja modułu | Domyślne przesunięcie dostawy (dni) | 7 | Ustawia szacowaną datę dostawy dla planowania ankiet. Dostosuj na podstawie średniego czasu wysyłki. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem moduł, ale nie widzę opcji zgody na Google Customer Reviews na mojej stronie potwierdzenia zamówienia.**
O:

1.  **Sprawdź swój identyfikator sprzedawcy Google:** Dokładnie sprawdź, czy wprowadziłeś poprawny identyfikator sprzedawcy Google w konfiguracji modułu. Nieprawidłowy identyfikator uniemożliwi załadowanie skryptu.
2.  **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami buforowana zawartość może uniemożliwić wyświetlanie nowych skryptów modułów.
3.  **Sprawdź błędy JavaScript:** Otwórz konsolę programisty przeglądarki (zazwyczaj F12) na stronie potwierdzenia zamówienia. Poszukaj wszelkich błędów JavaScript, które mogą wskazywać na konflikt z innym modułem lub Twoim szablonem.
4.  **Zweryfikuj wykonanie hooka:** Upewnij się, że Twój szablon poprawnie wywołuje hook `displayOrderConfirmation`. Chociaż jest to standardowe, niektóre mocno dostosowane szablony mogą pomijać lub zmieniać nazwy hooków.

**P: Opcja zgody pojawia się, ale nie widzę żadnych recenzji w moim Google Merchant Center.**
O:

1.  **Status Google Merchant Center:** Zaloguj się do swojego konta Google Merchant Center i przejdź do sekcji „Google Customer Reviews”. Upewnij się, że program jest aktywny i nie ma zgłoszonych problemów. Może minąć trochę czasu, zanim recenzje zaczną się pojawiać po początkowej konfiguracji.
2.  **Współczynnik zgody klienta:** Nie każdy klient zgodzi się na ankietę. Pewien procent klientów musi wyrazić zgodę na otrzymanie e-maila z ankietą od Google.
3.  **Ukończenie ankiety:** Nawet jeśli klient wyrazi zgodę, nadal musi wypełnić ankietę wysłaną przez Google.

**P: Czy mogę dostosować wygląd opcji zgody lub plakietki Google Customer Reviews?**
O: Wygląd monitu zgody i plakietki Google Customer Reviews jest kontrolowany przez Google i nie można go bezpośrednio dostosować za pomocą modułu PrestaShop. Google utrzymuje spójne doświadczenie marki dla tych elementów. Możesz jednak wybrać, gdzie wyświetlać plakietkę na swojej stronie za pomocą ustawień Google Merchant Center (np. stopka, pasek boczny).

**P: Moje produkty mają GTIN, ale nie otrzymuję recenzji na poziomie produktu.**
O:

1.  **Włącz GTIN w module:** Upewnij się, że opcja „Dołącz listę GTIN produktów do ładunku GCR” jest ustawiona na „Tak” w konfiguracji modułu.
2.  **Prawidłowy format GTIN:** Sprawdź, czy Twoje GTIN produktów (EAN, UPC, ISBN) są poprawnie wprowadzone na stronach produktów PrestaShop i są zgodne ze standardowymi formatami. Nieprawidłowo sformatowane GTIN mogą zostać zignorowane przez Google.
3.  **Uznanie Google:** Nawet po podaniu GTIN, Google ostatecznie decyduje, czy poprosić o recenzje na poziomie produktu. Czynniki takie jak popularność produktu i liczba recenzji mogą na to wpływać.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł `gcroptin` to lekki moduł PrestaShop zaprojektowany do wstrzykiwania oficjalnego skryptu zgody na Google Customer Reviews do hooka `displayOrderConfirmation`. Wykorzystuje klasę `Module` PrestaShop i silnik szablonów `Smarty`. Główna logika znajduje się w głównym pliku modułu, obsługując przechowywanie konfiguracji i dynamiczne wstrzykiwanie danych do szablonu Smarty. Nie wprowadza niestandardowych kontrolerów, modeli ani złożonych zasobów JavaScript/CSS, koncentrując się wyłącznie na wymaganym wstrzykiwaniu skryptu z dynamicznymi danymi zamówienia.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Moduł działa poprzez podłączenie się do `displayOrderConfirmation` i bezpośrednie renderowanie szablonu.
-   **Kontrolery administracyjne Back-Office**: Brak. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównej klasy modułu.

### 4.3 Główne klasy i modele (`classes/`)

-   Nie zdefiniowano żadnych niestandardowych klas ani instancji `ObjectModel`. Cała logika jest zawarta w pliku `gcroptin.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   Brak. Moduł bezpośrednio wyprowadza fragment kodu JavaScript Google Customer Reviews w szablonie Smarty.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   Brak. Interfejs użytkownika zgody na Google Customer Reviews jest renderowany przez skrypt Google i nie wymaga niestandardowego stylu z modułu.

### 4.6 Struktura szablonu Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    -   `gcroptin/views/templates/hook/gcroptin-order-confirmation.tpl`
        -   **Cel:** Ten szablon jest renderowany, gdy wykonywany jest hook `displayOrderConfirmation`. Zawiera główny fragment kodu JavaScript zgody na Google Customer Reviews.
        -   **Dostępne dane:** Ten szablon otrzymuje różne zmienne specyficzne dla zamówienia z modułu, w tym:
            -   `{$gcr_merchant_id}`: Identyfikator Google Merchant Center skonfigurowany w panelu administracyjnym.
            -   `{$gcr_order_id}`: Identyfikator zamówienia PrestaShop.
            -   `{$gcr_currency_iso_code}`: Kod ISO waluty zamówienia.
            -   `{$gcr_total_paid}`: Całkowita kwota zapłacona za zamówienie.
            -   `{$gcr_customer_email}`: Adres e-mail klienta.
            -   `{$gcr_delivery_country}`: Kod ISO kraju dostawy.
            -   `{$gcr_delivery_date}`: Obliczona szacowana data dostawy.
            -   `{$gcr_product_gtins_json}`: Zakodowana w JSON tablica GTIN produktów (jeśli włączona).
        -   **Wyjście:** Wyprowadza tag `<script>` zawierający kod zgody na Google Customer Reviews, dynamicznie wypełniony szczegółami zamówienia.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**: Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop, używając kluczy takich jak `GCROPTIN_MERCHANT_ID`, `GCROPTIN_INCLUDE_GTIN` i `GCROPTIN_DELIVERY_OFFSET`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayOrderConfirmation` | Wykonywany na stronie potwierdzenia zamówienia po udanym dokonaniu zakupu. | Wstrzykuje fragment kodu JavaScript zgody na Google Customer Reviews z dynamicznymi danymi zamówienia. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu „Google Customer Reviews for PrestaShop - opt-in & survey (GCR)”.
