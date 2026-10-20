---
title: "Amazon Ads Tag Conversions API - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Amazon Ads Tag Conversions API od MyPresta.eu."
sidebar:
  label: "Amazon Ads Tag Conversions API - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Amazon Ads Tag Conversions API na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/amazon-ads-tag-conversions-api.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/amazon-ads-tag-conversions-api/)
>
> ---


# Amazon Ads Tag Conversions API

## 1. Wymagania i kompatybilność

-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 7.1 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są wymagane do prawidłowego działania modułu, zwłaszcza dla Conversions API (CAPI), które opiera się na bezpiecznej komunikacji serwer-serwer. Twoje środowisko hostingowe powinno również zezwalać na połączenia wychodzące do punktów końcowych API Amazona.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Ta sekcja przeprowadzi Cię przez każde ustawienie modułu „Amazon Ads Tag Conversions API”.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest główny ekran konfiguracji, na którym skonfigurujesz śledzenie reklam Amazon.

**Dostęp:** Przejdź do **Moduły > Menedżer modułów**, następnie znajdź „Amazon Ads Tag Conversions API” i kliknij **Konfiguruj**.

#### **Wybór trybu śledzenia**

Ta sekcja określa, w jaki sposób Twój sklep wysyła dane do Amazona.

-   **Co robi to ustawienie:** Pozwala wybrać jedną z trzech podstawowych metod wysyłania danych o konwersjach do Amazona: Amazon Ads Tag (po stronie klienta), Conversions API (po stronie serwera) lub kombinację obu.
-   **Efekt zmiany tego ustawienia:**
    -   *Po ustawieniu na „Amazon Ads Tag (po stronie klienta)”:* Moduł będzie polegał głównie na tagu JavaScript umieszczonym w przeglądarce klienta do wysyłania danych. Jest to podatne na blokery reklam.
    -   *Po ustawieniu na „Conversions API (po stronie serwera)”:* Moduł będzie wysyłał dane bezpośrednio z Twojego serwera PrestaShop do serwerów Amazona. Jest to bardziej niezawodne i omija blokery reklam.
    -   *Po ustawieniu na „Tryb podwójny (hybrydowy)”:* Moduł będzie wysyłał dane zarówno za pomocą Amazon Ads Tag, jak i Conversions API. Zapewnia to maksymalną odporność i dokładność danych.
-   **Zalecana wartość:** **„Tryb podwójny (hybrydowy)”** dla najbardziej solidnego i dokładnego śledzenia. Jeśli bardzo zależy Ci na prywatności i chcesz zminimalizować skrypty po stronie klienta, „Conversions API (po stronie serwera)” jest silną alternatywą.
-   **Scenariusz / przykład dla sprzedawcy:** Jeśli zauważyłeś rozbieżność między zgłoszonymi konwersjami z Amazon Ads a rzeczywistą sprzedażą w PrestaShop, przełączenie na „Tryb podwójny” lub „Conversions API” może znacznie poprawić dokładność, odzyskując konwersje utracone z powodu blokerów reklam.

#### **ID tagu Amazon Ads**

-   **Co robi to ustawienie:** To jest Twój unikalny identyfikator dostarczony przez Amazon Ads dla Twojego tagu śledzenia. Informuje Amazona, do którego konta przypisać dane o konwersjach.
-   **Efekt zmiany tego ustawienia:**
    -   *Po wprowadzeniu prawidłowego ID:* Amazon Ads Tag (jeśli włączony w Twoim trybie śledzenia) będzie prawidłowo wysyłał dane do Twojego konta Amazon Ads.
    -   *Po pozostawieniu pustego lub wprowadzeniu nieprawidłowego ID:* Śledzenie po stronie klienta nie będzie działać, a dane nie będą wysyłane do Twojego konta Amazon Ads za pośrednictwem tagu.
-   **Zalecana wartość:** Twój konkretny ID tagu Amazon Ads. Możesz go znaleźć na swoim koncie Amazon Ads w sekcji „Menedżer zdarzeń” lub „Odbiorcy”.
-   **Scenariusz / przykład dla sprzedawcy:** Właśnie skonfigurowałeś nową kampanię Amazon Ads. Wprowadzenie prawidłowego ID tagu tutaj jest pierwszym krokiem do zapewnienia śledzenia wydajności Twojej kampanii.

#### **Token dostępu do Amazon Conversions API**

-   **Co robi to ustawienie:** To jest bezpieczny token dostarczony przez Amazon Ads, który uwierzytelnia Twój serwer podczas wysyłania danych za pośrednictwem Conversions API. Zapewnia, że tylko autoryzowane źródła mogą wysyłać dane do Twojego konta Amazon Ads.
-   **Efekt zmiany tego ustawienia:**
    -   *Po wprowadzeniu prawidłowego tokenu:* Twój serwer PrestaShop może bezpiecznie wysyłać dane o konwersjach bezpośrednio do Amazona za pośrednictwem Conversions API (jeśli włączone w Twoim trybie śledzenia).
    -   *Po pozostawieniu pustego lub wprowadzeniu nieprawidłowego tokenu:* Śledzenie po stronie serwera za pośrednictwem Conversions API nie będzie działać, a dane nie będą wysyłane do Twojego konta Amazon Ads za pośrednictwem CAPI.
-   **Zalecana wartość:** Twój konkretny token dostępu do Amazon Conversions API. Jest on generowany na Twoim koncie Amazon Ads, zazwyczaj w sekcji „Menedżer zdarzeń” lub „Źródła danych”. Traktuj ten token jak hasło; przechowuj go bezpiecznie.
-   **Scenariusz / przykład dla sprzedawcy:** Chcesz poprawić niezawodność śledzenia konwersji, używając Conversions API. Po wygenerowaniu tokenu w Amazon Ads, wklej go tutaj, aby włączyć transmisję danych po stronie serwera.

#### **Włącz tryb debugowania**

-   **Co robi to ustawienie:** Aktywuje specjalny tryb, który wyświetla szczegółowe informacje o danych wysyłanych do Amazona, widoczne tylko dla Ciebie (lub każdego, kto ma otwarte narzędzia deweloperskie) w konsoli przeglądarki. Jest to nieocenione przy rozwiązywaniu problemów.
-   **Efekt zmiany tego ustawienia:**
    -   *Po włączeniu:* Zobaczysz logi konsoli i potencjalnie nakładki na ekranie (w zależności od konkretnej implementacji debugowania) pokazujące, jakie zdarzenia są wyzwalane i jakie dane są wysyłane do Amazona. Nie jest to widoczne dla zwykłych klientów.
    -   *Po wyłączeniu:* Nie będą wyświetlane żadne informacje debugowania.
-   **Zalecana wartość:** **„NIE”** dla działających sklepów produkcyjnych. Włączaj tymczasowo tylko podczas konfiguracji lub rozwiązywania problemów.
-   **Scenariusz / przykład dla sprzedawcy:** Skonfigurowałeś moduł, ale konwersje nie pojawiają się na Twoim koncie Amazon Ads. Włączenie trybu debugowania może pomóc Ci sprawdzić, czy zdarzenia są prawidłowo wyzwalane na Twojej stronie internetowej i czy ładunek danych wygląda poprawnie.

#### **Integracja z zarządzaniem zgodami**

-   **Co robi to ustawienie:** Pozwala modułowi integrować się z rozwiązaniem do zarządzania zgodami na pliki cookie w Twoim sklepie. Zapewnia to, że śledzenie Amazon Ads aktywuje się tylko po wyrażeniu przez klienta wyraźnej zgody, zgodnie z przepisami o ochronie prywatności, takimi jak RODO lub CCPA.
-   **Efekt zmiany tego ustawienia:**
    -   *Po włączeniu i zintegrowaniu z modułem zgody:* Amazon Ads Tag (po stronie klienta) załaduje się i wywoła zdarzenia tylko wtedy, gdy klient zaakceptował pliki cookie śledzące. CAPI po stronie serwera może nadal wysyłać anonimowe dane lub czekać na zgodę, w zależności od Twojej konkretnej konfiguracji i polityki prywatności.
    -   *Po wyłączeniu:* Moduł będzie próbował śledzić zdarzenia bez wyraźnych kontroli zgody, co może nie być zgodne z przepisami o ochronie prywatności w niektórych regionach.
-   **Zalecana wartość:** **„TAK”**, jeśli Twój sklep działa w regionach z surowymi przepisami o ochronie prywatności (np. UE, Kalifornia) i używasz modułu zgody na pliki cookie.
-   **Scenariusz / przykład dla sprzedawcy:** Twój sklep obsługuje klientów w Europie i używasz banera cookie zgodnego z RODO. Włączenie tego ustawienia zapewnia, że śledzenie Amazon Ads szanuje wybory klientów dotyczące prywatności.

#### **Ustawienia zaawansowane (np. Warstwa danych, Mapowanie zdarzeń, Rozwiązywanie ID produktu)**

Moduł może zawierać zaawansowane ustawienia, które pozwalają na precyzyjne dostosowanie zbierania i przesyłania danych. Są one zazwyczaj przeznaczone dla bardziej technicznych użytkowników lub specyficznych scenariuszy.

-   **Śledzenie warstwy danych:**
    -   **Co robi to ustawienie:** Określa, czy moduł powinien używać ustandaryzowanej „warstwy danych” do zbierania informacji z Twojego sklepu. Jest to często używane do kompatybilności z innymi narzędziami śledzącymi lub niestandardowymi implementacjami.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Moduł będzie szukał i przesyłał dane do obiektu JavaScript `dataLayer`, co może być przydatne do debugowania lub integracji z Google Tag Managerem.
        -   *Po wyłączeniu:* Moduł będzie zbierał dane bezpośrednio z wewnętrznych zmiennych PrestaShop.
    -   **Zalecana wartość:** **„TAK”**, jeśli używasz Google Tag Managera lub innych narzędzi, które polegają na warstwie danych. W przeciwnym razie „NIE” jest zazwyczaj w porządku.
-   **Mapowanie zdarzeń:**
    -   **Co robi to ustawienie:** Pozwala dostosować, w jaki sposób konkretne działania PrestaShop (np. „dodaj do koszyka”) są mapowane na nazwy zdarzeń Amazon Ads.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po dostosowaniu:* Możesz wysyłać do Amazona inne nazwy zdarzeń niż domyślne modułu, co może być przydatne dla specyficznych konfiguracji kampanii Amazon Ads.
        -   *Po pozostawieniu domyślnego:* Moduł używa swojego predefiniowanego mapowania.
    -   **Zalecana wartość:** Pozostaw domyślne, chyba że masz konkretny powód, aby to zmienić na podstawie dokumentacji Amazon Ads.
-   **Rozwiązywanie ID produktu:**
    -   **Co robi to ustawienie:** Definiuje, który identyfikator produktu (np. ID produktu, EAN, UPC, SKU) moduł powinien wysyłać do Amazona dla zdarzeń związanych z produktem.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po ustawieniu na ID produktu:* Amazon otrzyma wewnętrzny ID produktu PrestaShop.
        -   *Po ustawieniu na EAN/UPC/SKU:* Amazon otrzyma odpowiedni identyfikator produktu. Jest to kluczowe dla dopasowywania produktów w Twoim katalogu produktów Amazon.
    -   **Zalecana wartość:** Wybierz identyfikator, który najbardziej konsekwentnie pasuje do identyfikatorów produktów, których używasz w swoich kanałach produktów Amazon lub katalogu. **EAN/UPC** jest często preferowane dla produktów detalicznych.
-   **Domeny łączące (Linker Domains):**
    -   **Co robi to ustawienie:** Określa dodatkowe domeny, które powinny być uwzględnione w śledzeniu między domenami. Jest to ważne, jeśli Twój proces realizacji zamówienia lub inne części ścieżki klienta obejmują wiele domen (np. oddzielna subdomena dla bloga lub bramka płatności, która przekierowuje).
    -   **Efekt zmiany tego ustawienia:**
        -   *Po skonfigurowaniu:* Amazon Ads Tag może utrzymywać ciągłość śledzenia między różnymi domenami, zapobiegając utracie atrybucji.
        -   *Po nieskonfigurowaniu dla wielu domen:* Konwersje mogą być błędnie przypisane lub utracone, jeśli klient nawiguje między domenami podczas swojej podróży.
    -   **Zalecana wartość:** Dodaj wszystkie domeny lub subdomeny, które są częścią ścieżki klienta.
-   **Pomocnik waluty (Currency Helper):**
    -   **Co robi to ustawienie:** Zapewnia, że wartości walut wysyłane do Amazona są poprawnie sformatowane i odpowiadają walucie używanej na Twoim koncie Amazon Ads.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po prawidłowej konfiguracji:* Amazon otrzymuje dokładne wartości walut.
        -   *Po błędnej konfiguracji:* Wartości walut mogą być błędnie interpretowane przez Amazona, co prowadzi do nieprawidłowego raportowania.
    -   **Zalecana wartość:** Upewnij się, że jest to zgodne z główną walutą Twojego sklepu i walutą Twojego konta Amazon Ads.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł udostępnia kilka dedykowanych ekranów, które pomogą Ci monitorować i optymalizować śledzenie reklam Amazon. Są one zazwyczaj dostępne za pośrednictwem zakładek lub podsekcji w ramach głównej konfiguracji modułu.

#### **4.2.1 Statystyki na żywo**

-   **Nazwa ekranu i lokalizacja w menu:** Zazwyczaj zakładka w głównej konfiguracji modułu (np. „Statystyki na żywo”).
-   **Dostępne działania i ustawienia:** Ten ekran wyświetla dane w czasie rzeczywistym lub zbliżonym do rzeczywistego o zdarzeniach wysyłanych do Amazona. Może pokazywać:
    -   Ostatnie zdarzenia (np. PageView, AddToCart, Purchase) z sygnaturami czasowymi.
    -   Typy zdarzeń i ich częstotliwość.
    -   Wyniki jakości danych.
    -   Wizualizacje aktywności śledzenia.
-   **Efekt zmian:** Jest to ekran raportowania; nie ma tu bezpośrednich ustawień do zmiany. Odzwierciedla dane wysyłane na podstawie Twojej głównej konfiguracji.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie sprawdzaj ten ekran, aby upewnić się, że zdarzenia są wyzwalane zgodnie z oczekiwaniami, zwłaszcza po wprowadzeniu zmian w sklepie lub uruchomieniu nowych kampanii. Jest to Twoja pierwsza linia obrony w identyfikowaniu problemów ze śledzeniem.

#### **4.2.2 Ocena stanu zdrowia i Radar odzyskiwania**

-   **Nazwa ekranu i lokalizacja w menu:** Często zakładka w głównej konfiguracji modułu (np. „Ocena stanu zdrowia” lub „Diagnostyka”).
-   **Dostępne działania i ustawienia:** Ta sekcja zapewnia ogólną ocenę stanu zdrowia śledzenia reklam Amazon i identyfikuje potencjalne problemy lub „utracone” konwersje. Może zawierać:
    -   Wynik procentowy wskazujący stan zdrowia śledzenia.
    -   Zalecenia dotyczące poprawy jakości danych.
    -   „Radar odzyskiwania” pokazujący szacowane konwersje, które mogły zostać pominięte z powodu blokerów reklam lub innych problemów, oraz jak CAPI pomaga je odzyskać.
    -   Ostrzeżenia o brakujących ID tagów, tokenach dostępu lub problemach ze zgodą.
-   **Efekt zmian:** Podobnie jak Statystyki na żywo, jest to przede wszystkim ekran raportowania i diagnostyki. Działania, które podejmiesz na podstawie jego zaleceń (np. aktualizacja brakującego ID tagu), poprawią Twoje śledzenie.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Okresowo przeglądaj swoją Ocenę stanu zdrowia. Niski wynik lub aktywny „Radar odzyskiwania” wskazuje obszary, w których Twoje śledzenie mogłoby zostać poprawione, potencjalnie prowadząc do lepszej wydajności reklam.

#### **4.2.3 Trener jakości danych / Doktor katalogu**

-   **Nazwa ekranu i lokalizacja w menu:** Potencjalnie zakładka w głównej konfiguracji modułu (np. „Jakość danych” lub „Doktor katalogu”).
-   **Dostępne działania i ustawienia:** Te narzędzia pomagają zapewnić, że dane wysyłane do Amazona są wysokiej jakości i poprawnie sformatowane. Mogą:
    -   Sprawdzać typowe problemy z danymi (np. brakujące ID produktów, nieprawidłowe formaty walut).
    -   Dostarczać sugestie dotyczące poprawy danych katalogu produktów, aby lepiej odpowiadały wymaganiom Amazona.
    -   Podkreślać rozbieżności między danymi po stronie klienta a danymi po stronie serwera.
-   **Efekt zmian:** Ten ekran dostarcza praktycznych wskazówek. Rozwiązanie problemów podkreślonych tutaj (np. aktualizacja EAN-ów produktów w katalogu PrestaShop) bezpośrednio poprawi jakość i możliwości dopasowywania danych o konwersjach w Amazon Ads.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Jeśli masz problemy z dopasowywaniem produktów w Amazon Ads lub widzisz ostrzeżenia w swojej Ocenie stanu zdrowia, skonsultuj się z tymi narzędziami, aby udoskonalić swoje dane.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Główna konfiguracja | **Tryb śledzenia** | Tryb podwójny (hybrydowy) | Określa, czy śledzenie jest po stronie klienta, po stronie serwera, czy obu. Tryb podwójny oferuje maksymalną odporność. |
| Główna konfiguracja | **ID tagu Amazon Ads** | Twój ID tagu Amazon | Niezbędne do śledzenia po stronie klienta. Łączy dane z Twoim kontem Amazon Ads. |
| Główna konfiguracja | **Token dostępu do Amazon Conversions API** | Twój token dostępu CAPI | Niezbędne do śledzenia po stronie serwera. Uwierzytelnia Twój serwer w Amazonie. |
| Główna konfiguracja | **Włącz tryb debugowania** | NIE | Wyświetla dane śledzenia w konsoli przeglądarki do rozwiązywania problemów. Wyłącz w działających sklepach. |
| Główna konfiguracja | **Integracja z zarządzaniem zgodami** | TAK (jeśli dotyczy) | Zapewnia, że śledzenie szanuje prywatność klienta i zgodę na pliki cookie. |
| Główna konfiguracja | **Śledzenie warstwy danych** | TAK (jeśli używasz GTM) | Używa warstwy danych do zbierania zdarzeń, przydatne dla GTM lub niestandardowych integracji. |
| Główna konfiguracja | **Rozwiązywanie ID produktu** | EAN/UPC | Definiuje, który identyfikator produktu jest wysyłany do Amazona w celu dopasowania. Kluczowe dla dopasowywania katalogu. |
| Główna konfiguracja | **Domeny łączące** | Puste (dodaj w razie potrzeby) | Utrzymuje śledzenie między wieloma domenami w ścieżce klienta. |
| Statystyki na żywo | (Tylko raportowanie) | N/A | Pokazuje dane zdarzeń w czasie rzeczywistym, pomagając zweryfikować aktywność śledzenia. |
| Ocena stanu zdrowia | (Tylko raportowanie) | N/A | Zapewnia ogólną ocenę stanu zdrowia śledzenia i identyfikuje problemy. |
| Jakość danych | (Tylko raportowanie) | N/A | Pomaga identyfikować i naprawiać problemy z jakością danych w katalogu produktów dla lepszego dopasowania w Amazonie. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje konwersje z Amazon Ads nie zgadzają się ze sprzedażą w PrestaShop. Co powinienem zrobić?**
O1: Jest to częsty problem, często spowodowany blokerami reklam.
\* **Sprawdź tryb śledzenia:** Upewnij się, że używasz „Trybu podwójnego (hybrydowego)” lub „Conversions API (po stronie serwera)” w ustawieniach modułu. Jest to najskuteczniejszy sposób na odzyskanie utraconych konwersji.
\* **Zweryfikuj ID/tokeny:** Dokładnie sprawdź, czy Twój ID tagu Amazon Ads i token dostępu do Conversions API są poprawnie wprowadzone w konfiguracji modułu.
\* **Użyj trybu debugowania:** Tymczasowo włącz „Tryb debugowania” i wykonaj testowy zakup. Sprawdź konsolę przeglądarki i „Statystyki na żywo” modułu, aby zobaczyć, czy zdarzenia są wyzwalane.
\* **Wyczyść pamięć podręczną:** Przejdź do **Parametry zaawansowane > Wydajność** w panelu administracyjnym PrestaShop i wyczyść pamięć podręczną Smarty oraz inne pamięci podręczne. Czasami stary kod modułu może się utrzymywać.

**P2: Widzę ostrzeżenia o „Jakości danych” lub „Brakujących ID produktów” w Ocenie stanu zdrowia modułu. Jak to naprawić?**
O2: Amazon polega na wysokiej jakości danych produktów dla dokładnego dopasowania.
\* **Rozwiązywanie ID produktu:** W konfiguracji modułu upewnij się, że ustawienie „Rozwiązywanie ID produktu” (np. EAN, UPC, SKU) odpowiada głównemu identyfikatorowi używanemu w Twoim kanale produktów Amazon.
\* **Zaktualizuj dane produktów:** Przejdź do **Katalog > Produkty** w panelu administracyjnym PrestaShop. Edytuj produkty oznaczone przez „Trenera jakości danych” i upewnij się, że mają kompletne i dokładne EAN-y, UPC-y lub SKU zgodnie z wymaganiami.
\* **Spójność:** Upewnij się, że identyfikatory produktów w Twoim sklepie PrestaShop są spójne z tym, co dostarczasz Amazonowi w swoich kanałach produktów.

**P3: Moja strona internetowa używa banera zgody na pliki cookie. Czy ten moduł będzie szanował wybory klientów?**
O3: Tak, jeśli jest poprawnie skonfigurowany.
\* **Włącz integrację zgody:** W konfiguracji modułu upewnij się, że „Integracja z zarządzaniem zgodami” jest włączona.
\* **Kompatybilność modułu cookie:** Ten moduł jest zaprojektowany do integracji ze standardowymi modułami zgody na pliki cookie PrestaShop. Jeśli używasz niestandardowego rozwiązania, musisz upewnić się, że prawidłowo wyzwala ono zdarzenia `prestashop.on('updateProduct', ...)` lub podobne, których moduły nasłuchują w celu zmian zgody.
\* **CAPI vs. Tag:** Pamiętaj, że Conversions API (po stronie serwera) jest mniej podatne na banery zgody po stronie klienta niż Amazon Ads Tag (po stronie klienta), ponieważ wysyła dane bezpośrednio z Twojego serwera. Jednak nadal najlepszą praktyką jest wysyłanie danych osobowych (PII) za pośrednictwem CAPI tylko po uzyskaniu zgody.

**P4: Moduł wydaje się spowalniać moją witrynę. Co mogę zrobić?**
O4: Ten moduł jest zoptymalizowany pod kątem wydajności, ale oto kilka kontroli:
\* **Wyłącz tryb debugowania:** Upewnij się, że „Tryb debugowania” jest wyłączony w Twoim działającym sklepie, ponieważ dodaje on dodatkowe logowanie do konsoli.
\* **Wydajność serwera:** Conversions API (CAPI) wykonuje wywołania serwer-serwer. Chociaż zazwyczaj jest szybkie, upewnij się, że Twój serwer hostingowy ma odpowiednie zasoby i stabilne połączenie internetowe.
\* **Inne moduły:** Sprawdź, czy inne ciężkie moduły śledzące lub reklamowe również działają jednocześnie. Zbyt wiele skryptów po stronie klienta może wpływać na wydajność.
\* **Wyczyść pamięć podręczną:** Zawsze czyść pamięć podręczną PrestaShop po wprowadzeniu zmian w konfiguracji.

**P5: Otrzymuję komunikat o błędzie podczas próby zapisania konfiguracji modułu.**
O5:
\* **Sprawdź uprawnienia:** Upewnij się, że folder modułu (`/modules/myamazon/`) i jego podfoldery mają prawidłowe uprawnienia do zapisu (zazwyczaj 755 dla folderów, 644 dla plików).
\* **Logi serwera:** Sprawdź logi błędów PHP swojego serwera, aby uzyskać bardziej szczegółowe informacje o błędzie. Można je często znaleźć w panelu sterowania hostingu lub kontaktując się z dostawcą hostingu.
\* **Tryb debugowania PrestaShop:** Tymczasowo włącz tryb debugowania PrestaShop (w `config/defines.inc.php` zmień `define('_PS_MODE_DEV_', false);` na `define('_PS_MODE_DEV_', true);`), aby zobaczyć bardziej szczegółowe komunikaty o błędach na ekranie.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd struktury technicznej modułu „Amazon Ads Tag Conversions API”, przeznaczony dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł `myamazon` jest zbudowany zgodnie z wzorcem MVC (Model-View-Controller) PrestaShop, z silnym naciskiem na modułowość i śledzenie oparte na zdarzeniach. Wykorzystuje zarówno mechanizmy po stronie klienta (Amazon Ads Tag), jak i po stronie serwera (Conversions API), często w podejściu hybrydowym.

Kluczowe komponenty architektoniczne:

-   **Główna klasa modułu (`myamazon/index.php`):** Obsługuje instalację, deinstalację, rejestrację hooków i główną metodę `getContent()` dla konfiguracji panelu administracyjnego.
-   **Kontrolery:** Dedykowane kontrolery front-endowe do interakcji AJAX i kontrolery administracyjne do zarządzania ustawieniami modułu i widokami diagnostycznymi.
-   **Klasy podstawowe (`classes/`):** Solidny zestaw klas zarządza różnymi aspektami:
    -   **Logika śledzenia:** `MyamazonAatTracker.php` (po stronie klienta), `MyamazonCapiTracker.php` (po stronie serwera), `MyamazonHybridTracker.php` (tryb podwójny), `MyamazonTrackerFactory.php` (tworzy instancje trackerów).
    -   **Obsługa danych:** `MyamazonUserData.php` (dane klienta), `MyamazonEventMap.php` (tłumaczenie zdarzeń), `MyamazonProductIdResolver.php` (logika ID produktu), `MyamazonCurrencyHelper.php`.
    -   **Klient API:** `MyamazonCapiClient.php` (obsługuje komunikację z Amazon CAPI).
    -   **Diagnostyka i stan zdrowia:** `MyamazonHealthScore.php`, `MyamazonCatalogDoctor.php`, `MyamazonDataQualityCoach.php`, `MyamazonLiveStats.php`.
    -   **Zgoda:** `MyamazonConsent.php` (integruje się z mechanizmami zgody).
-   **Hooki:** Obszerne wykorzystanie hooków PrestaShop do wstrzykiwania JavaScriptu, przechwytywania zdarzeń i wysyłania danych w krytycznych punktach ścieżki klienta.
-   **Szablony Smarty:** Używane do renderowania zarówno widoków konfiguracji panelu administracyjnego, jak i skryptów śledzących front-office.
-   **JavaScript:** Zarządza wstrzykiwaniem tagów po stronie klienta, nasłuchiwaniem zdarzeń i interakcjami z warstwą danych.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `controllers/front/ajax.php`
    -   **Nazwa klasy:** `MyamazonAjaxModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Obsługuje asynchroniczne (AJAX) żądania z front-office. Jest to zazwyczaj używane do wysyłania zdarzeń po stronie serwera za pośrednictwem CAPI, których nie można wykonać bezpośrednio w przeglądarce (np. zdarzenia po zakupie, gdy przeglądarka może być zamknięta, lub zdarzenia wymagające przetwarzania danych po stronie serwera). Odbiera dane z JavaScriptu po stronie klienta i przekazuje je do `MyamazonCapiTracker`.
-   `controllers/front/index.php`
    -   **Nazwa klasy:** `MyamazonIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Ten kontroler może służyć jako rezerwowy lub prosty punkt wejścia, chociaż jego główne zastosowanie może być minimalne, jeśli `ajax.php` obsługuje większość interakcji front-endowych. Może być używany do specyficznych przekierowań lub prostych wyświetleń danych, jeśli jest to potrzebne, ale często służy jako placeholder.

#### Kontrolery administracyjne Back-Office

-   `controllers/admin/AdminMyamazonAjaxController.php`
    -   **Nazwa klasy:** `AdminMyamazonAjaxController` (rozszerza `ModuleAdminController`)
    -   **Nazwa zakładki:** Nie jest bezpośrednio zakładką menu, ale punktem końcowym AJAX dla interfejsu administracyjnego.
    -   **Odpowiedzialność:** Obsługuje żądania AJAX pochodzące ze stron konfiguracji panelu administracyjnego modułu. Obejmuje to pobieranie danych dla statystyk na żywo, ocen stanu zdrowia lub wykonywanie kontroli w tle (np. walidacja tokenu API) bez ponownego ładowania całej strony. Współpracuje z klasami takimi jak `MyamazonLiveStats`, `MyamazonHealthScore` i `MyamazonCapiClient`.
-   `controllers/admin/index.php`
    -   **Nazwa klasy:** `AdminMyamazonIndexController` (rozszerza `ModuleAdminController`)
    -   **Nazwa zakładki:** Nie jest bezpośrednią zakładką menu.
    -   **Odpowiedzialność:** Podobnie jak `index.php` front-office, może to być placeholder lub obsługiwać bardzo specyficzne, nie-AJAX-owe interakcje administracyjne. Główna logika konfiguracji znajduje się w metodzie `getContent()` głównego modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `classes/autoload.php`: Standardowy plik autoload PrestaShop.
-   `classes/index.php`: Plik placeholder, często spotykany w pustych katalogach.
-   `classes/MyamazonAatTracker.php`:
    -   **Odpowiedzialność:** Implementuje logikę śledzenia Amazon Ads Tag po stronie klienta. Generuje niezbędny JavaScript dla `aa.js` i przesyła zdarzenia do warstwy danych przeglądarki lub bezpośrednio do Amazon Ads Tag.
-   `classes/MyamazonCapiClient.php`:
    -   **Odpowiedzialność:** Obsługuje rzeczywiste żądania HTTP do punktów końcowych Amazon Conversions API. Hermetyzuje logikę cURL lub Guzzle (jeśli używane), uwierzytelnianie za pomocą tokenu dostępu i obsługę błędów dla komunikacji serwer-serwer.
-   `classes/MyamazonCapiTracker.php`:
    -   **Odpowiedzialność:** Implementuje logikę śledzenia Conversions API po stronie serwera. Formatuje dane zdarzeń zgodnie ze specyfikacjami CAPI Amazona i używa `MyamazonCapiClient` do ich wysyłania.
-   `classes/MyamazonCatalogDoctor.php`:
    -   **Odpowiedzialność:** Analizuje dane katalogu produktów sklepu pod kątem potencjalnych problemów, które mogą wpływać na dopasowanie produktów Amazon (np. brakujące EAN-y, nieprawidłowe SKU). Dostarcza diagnostyczne informacje zwrotne dla interfejsu administracyjnego.
-   `classes/MyamazonConsent.php`:
    -   **Odpowiedzialność:** Zarządza integracją zgody na pliki cookie. Sprawdza status zgody klienta i warunkowo włącza/wyłącza skrypty śledzące po stronie klienta. Integruje się ze zdarzeniem `prestashop.on('updateProduct', ...)` PrestaShop dla zmian zgody.
-   `classes/MyamazonCurrencyHelper.php`:
    -   **Odpowiedzialność:** Dostarcza metody pomocnicze do prawidłowego formatowania wartości walut dla Amazon Ads, obsługi dziesiętnych i kodów walut.
-   `classes/MyamazonDataLayerTracker.php`:
    -   **Odpowiedzialność:** Zarządza przesyłaniem danych zdarzeń do obiektu JavaScript `dataLayer`, często używanego do kompatybilności z Google Tag Managerem lub innymi konsumentami warstwy danych.
-   `classes/MyamazonDataQualityCoach.php`:
    -   **Odpowiedzialność:** Dostarcza wglądu i zaleceń dotyczących poprawy ogólnej jakości danych wysyłanych do Amazona, obejmujących aspekty wykraczające poza same ID produktów.
-   `classes/MyamazonEventId.php`:
    -   **Odpowiedzialność:** Generuje unikalne ID zdarzeń dla każdego zdarzenia, kluczowe dla deduplikacji podczas korzystania ze śledzenia w trybie podwójnym (zapewniając, że Amazon nie liczy tego samego zdarzenia dwukrotnie z klienta i serwera).
-   `classes/MyamazonEventMap.php`:
    -   **Odpowiedzialność:** Definiuje mapowanie między wewnętrznymi zdarzeniami PrestaShop (np. `actionCartSave`) a standardowymi nazwami zdarzeń Amazon Ads (np. `AddToCart`). Pozwala na dostosowanie tych mapowań.
-   `classes/MyamazonEvents.php`:
    -   **Odpowiedzialność:** Centralna klasa lub zbiór metod do wyzwalania i zarządzania różnymi zdarzeniami Amazon Ads (np. `PageView`, `ViewContent`, `AddToCart`, `Purchase`).
-   `classes/MyamazonHealthScore.php`:
    -   **Odpowiedzialność:** Oblicza i prezentuje ogólną „ocenę stanu zdrowia” śledzenia modułu, identyfikując problemy z konfiguracją, brakujące dane lub potencjalne luki w śledzeniu.
-   `classes/MyamazonHybridTracker.php`:
    -   **Odpowiedzialność:** Koordynuje śledzenie w trybie podwójnym, łącząc `MyamazonAatTracker` i `MyamazonCapiTracker` w celu wysyłania zdarzeń zarówno metodami po stronie klienta, jak i po stronie serwera, obsługując deduplikację.
-   `classes/MyamazonLiveStats.php`:
    -   **Odpowiedzialność:** Zbiera i przetwarza dane zdarzeń w czasie rzeczywistym lub zbliżonym do rzeczywistego do wyświetlania w widoku „Statystyki na żywo” w panelu administracyjnym.
-   `classes/MyamazonProductIdResolver.php`:
    -   **Odpowiedzialność:** Określa, który identyfikator produktu (ID, EAN, UPC, SKU) powinien być używany podczas wysyłania danych produktu do Amazona, na podstawie konfiguracji modułu.
-   `classes/MyamazonPropertyRules.php`:
    -   **Odpowiedzialność:** Definiuje reguły i walidacje dla właściwości zdarzeń, zapewniając, że dane wysyłane do Amazona są zgodne z ich specyfikacjami API.
-   `classes/MyamazonTrackerFactory.php`:
    -   **Odpowiedzialność:** Klasa wzorca fabryki odpowiedzialna za tworzenie instancji prawidłowego trackera (`AatTracker`, `CapiTracker` lub `HybridTracker`) na podstawie konfiguracji modułu.
-   `classes/MyamazonTrackerInterface.php`:
    -   **Odpowiedzialność:** Definiuje wspólny interfejs dla wszystkich klas trackerów (`AatTracker`, `CapiTracker`, `HybridTracker`), zapewniając, że implementują one spójny zestaw metod do śledzenia zdarzeń.
-   `classes/MyamazonUserData.php`:
    -   **Odpowiedzialność:** Zbiera i formatuje dane związane z klientem (np. e-mail, telefon, adres) do włączenia w zdarzenia Amazon Ads, zwłaszcza dla Conversions API, gdzie PII może być haszowane i wysyłane.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `views/js/myamazon-admin.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Szczegóły:** Obsługuje interaktywne elementy na stronach konfiguracji modułu, takie jak przełączanie zakładek, wywołania AJAX dla statystyk na żywo, walidacja formularzy i dynamiczne aktualizacje narzędzi diagnostycznych.
-   `views/js/myamazon-debug.js`:
    -   **Zakres:** Front-office (ładowany warunkowo, gdy tryb debugowania jest aktywny).
    -   **Szczegóły:** Zapewnia szczegółowe logowanie do konsoli przeglądarki, wyświetlając wyzwalane zdarzenia, ładunki danych i status wywołań Amazon Ads Tag i CAPI. Może zawierać wizualne nakładki do szybkiego debugowania.
-   `views/js/myamazon-ghost.js`:
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Prawdopodobnie związane z mechanizmami śledzenia „duchów” lub w tle, potencjalnie do przechwytywania zdarzeń, które w przeciwnym razie mogłyby zostać pominięte, lub do specyficznych odroczeń związanych ze zgodą.
-   `views/js/myamazon-live.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Szczegóły:** Obsługuje pulpit nawigacyjny „Statystyki na żywo”, wykonując żądania AJAX do `AdminMyamazonAjaxController` w celu pobierania i wyświetlania danych zdarzeń w czasie rzeczywistym.
-   `views/js/myamazon-tcf.js`:
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Integruje się z rozwiązaniami do zarządzania zgodami na pliki cookie zgodnymi z Transparency and Consent Framework (TCF), zapewniając, że śledzenie po stronie klienta jest zgodne z preferencjami użytkownika dotyczącymi zgody.
-   `views/js/myamazon-wizard.js`:
    -   **Zakres:** Panel administracyjny.
    -   **Szczegóły:** Zapewnia interaktywne kroki dla początkowego kreatora konfiguracji, prowadząc sprzedawcę przez niezbędną konfigurację.
-   `views/js/myamazon.js`:
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Główny JavaScript po stronie klienta dla modułu. Wstrzykuje Amazon Ads Tag (`aa.js`), nasłuchuje różnych zdarzeń DOM (np. `click` na przyciskach dodawania do koszyka), przechwytuje dane ze strony, przesyła zdarzenia do warstwy danych i potencjalnie wykonuje wywołania AJAX do `MyamazonAjaxModuleFrontController` w celu przetwarzania po stronie serwera. Obsługuje również logikę deduplikacji zdarzeń.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `myamazon/opis/sugestie/style1.css`, `myamazon/opis/sugestie/style2.css`, `myamazon/opis/sugestie/sugestie/style1.css`, `myamazon/opis/sugestie/sugestie/style2.css`, `myamazon/opis/sugestie/sugestie/tailwind-new-7.css`, `myamazon/opis/sugestie/tailwind-new-7.css`:
    -   **Zakres:** Panel administracyjny.
    -   **Szczegóły:** Te pliki wydają się być związane z niestandardową strukturą UI lub stylizacją sugestii/podpowiedzi w konfiguracji panelu administracyjnego, prawdopodobnie dla prowadzonej konfiguracji lub diagnostyki. `tailwind-new-7.css` sugeruje użycie Tailwind CSS do stylizacji opartej na narzędziach.
-   `views/css/myamazon-admin.css`:
    -   **Zakres:** Stylizacja formularzy administracyjnych panelu administracyjnego.
    -   **Szczegóły:** Zapewnia specyficzną stylizację dla formularzy konfiguracji modułu, zakładek, paneli diagnostycznych i innych niestandardowych elementów UI w panelu administracyjnym PrestaShop.
-   `views/css/myamazon-debug.css`:
    -   **Zakres:** Front-office (ładowany warunkowo).
    -   **Szczegóły:** Style dla nakładki debugowania lub komunikatów konsoli, zapewniające ich czytelność i odrębność, gdy tryb debugowania jest aktywny.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `views/templates/hook/capi-pageview.tpl`:
    -   **Hook:** `displayHeader` (lub podobny).
    -   **Wyjście:** Wstrzykuje dane zdarzenia PageView po stronie serwera (CAPI), potencjalnie jako ukryte pole wejściowe lub zmienną JavaScript, które mają zostać odebrane przez kontroler `ajax.php` w celu wysłania po stronie serwera.
-   `views/templates/hook/debug.tpl`:
    -   **Hook:** `displayHeader` (warunkowo).
    -   **Wyjście:** Wstrzykuje skrypt `myamazon-debug.js` i wszelkie niezbędne początkowe zmienne debugowania, gdy tryb debugowania jest włączony.
-   `views/templates/hook/displayOrderConfirmation.tpl`:
    -   **Hook:** `displayOrderConfirmation`.
    -   **Wyjście:** Renderuje krytyczne dane zdarzenia „Purchase”, w tym szczegóły zamówienia, produkty i informacje o kliencie, zarówno dla tagu po stronie klienta, jak i transmisji CAPI po stronie serwera. To tutaj przechwytywana jest wartość konwersji.
-   `views/templates/hook/ghost.tpl`:
    -   **Hook:** `displayHeader` (lub podobny).
    -   **Wyjście:** Związane z mechanizmem śledzenia „duchów”, potencjalnie do odroczonego ładowania lub specyficznej logiki związanej ze zgodą.
-   `views/templates/hook/header.tpl`:
    -   **Hook:** `displayHeader`.
    -   **Wyjście:** Główny szablon do wstrzykiwania Amazon Ads Tag (skrypt `aa.js`), `myamazon.js` i początkowych zmiennych konfiguracyjnych do sekcji `<head>` każdej strony.
-   `views/templates/hook/payment.tpl`:
    -   **Hook:** `displayPaymentTop` (lub podobny).
    -   **Wyjście:** Może być używany do śledzenia zdarzeń „InitiateCheckout” lub innych zdarzeń związanych z płatnością przed ostatecznym potwierdzeniem zamówienia.
-   `views/templates/hook/product-details.tpl`:
    -   **Hook:** `displayProductButtons` lub `displayProductExtraContent`.
    -   **Wyjście:** Wstrzykuje JavaScript do śledzenia zdarzeń „ViewContent” po załadowaniu strony produktu, przechwytując dane specyficzne dla produktu.

#### Szablony administracyjne (`views/templates/admin/`)

-   `views/templates/admin/consent-guide.tpl`: Wyświetla wskazówki dotyczące integracji z modułami zgody na pliki cookie.
-   `views/templates/admin/doctor.tpl`: Renderuje widok diagnostyczny „Doktor katalogu”, pokazując problemy z danymi produktów.
-   `views/templates/admin/dq.tpl`: Renderuje widok „Trener jakości danych”, dostarczając wglądu w jakość danych.
-   `views/templates/admin/health.tpl`: Wyświetla ogólną „Ocenę stanu zdrowia” i powiązane diagnostyki.
-   `views/templates/admin/linker-domains.tpl`: Renderuje pole wejściowe do konfiguracji domen łączących.
-   `views/templates/admin/live-maintain.tpl`: Prawdopodobnie widok konserwacji dla statystyk na żywo.
-   `views/templates/admin/live.tpl`: Renderuje pulpit nawigacyjny „Statystyki na żywo”.
-   `views/templates/admin/mode-context.tpl`, `views/templates/admin/mode-note-aat.tpl`, `views/templates/admin/mode-note-both.tpl`, `views/templates/admin/mode-note-capi.tpl`, `views/templates/admin/mode-note-datalayer.tpl`, `views/templates/admin/mode-picker.tpl`: Te szablony są używane dla sekcji „Wybór trybu śledzenia”, dostarczając wyjaśnień i przycisku radiowego/rozwijanego do wyboru metody śledzenia.
-   `views/templates/admin/properties-list.tpl`: Wyświetla listę właściwości zdarzeń i ich wartości, prawdopodobnie do debugowania lub konfiguracji.
-   `views/templates/admin/recent-events.tpl`: Renderuje tabelę lub listę ostatnio śledzonych zdarzeń, część „Statystyk na żywo”.
-   `views/templates/admin/tabs.tpl`: Renderuje strukturę nawigacji po zakładkach dla konfiguracji panelu administracyjnego modułu.
-   `views/templates/admin/tag-chips.tpl`: Wyświetla wizualne „chipy” lub etykiety dla skonfigurowanych tagów/tokenów.
-   `views/templates/admin/tag-ids.tpl`: Renderuje pola wejściowe dla ID tagu Amazon Ads i tokenu dostępu CAPI.
-   `views/templates/admin/wizard.tpl`: Renderuje interfejs początkowego kreatora konfiguracji.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł przechowuje swoją konfigurację głównie w tabeli `ps_configuration` PrestaShop.

-   `ps_configuration`: Przechowuje pary klucz-wartość dla ustawień modułu (np. `MYAMAZON_TAG_ID`, `MYAMAZON_CAPI_TOKEN`, `MYAMAZON_TRACKING_MODE`).
    Brak niestandardowych tabel SQL jawnie utworzonych przez ten moduł na podstawie dostarczonego spisu.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykuje skrypt Amazon Ads Tag (`aa.js`), `myamazon.js` i początkowe zmienne konfiguracyjne. Używany również dla `capi-pageview.tpl` i `debug.tpl`. |
| `displayOrderConfirmation` | Na stronie potwierdzenia zamówienia po udanym zakupie. | Przechwytuje i wysyła dane zdarzenia „Purchase”, w tym szczegóły zamówienia i produkty, do Amazona za pomocą metod po stronie klienta i serwera. |
| `actionCartSave` | Gdy produkt jest dodawany do koszyka lub usuwany z niego, lub zmienia się ilość w koszyku. | Wyzwala zdarzenia „AddToCart” lub „RemoveFromCart”. |
| `actionProductAdd` | Gdy nowy produkt jest dodawany do katalogu. | Potencjalnie używany przez `MyamazonCatalogDoctor` do kontroli jakości danych. |
| `actionProductUpdate` | Gdy istniejący produkt jest aktualizowany w katalogu. | Potencjalnie używany przez `MyamazonCatalogDoctor` do kontroli jakości danych. |
| `actionFrontControllerSetMedia` | Przed renderowaniem szablonu przez kontroler front-endowy, umożliwiając dodanie JS/CSS. | Wstrzykuje pliki JS/CSS specyficzne dla modułu (`myamazon.js`, `myamazon-debug.js` itp.) do front-office. |
| `actionAdminControllerSetMedia` | Przed renderowaniem szablonu przez kontroler administracyjny. | Wstrzykuje pliki JS/CSS specyficzne dla modułu (`myamazon-admin.js`, `myamazon-admin.css` itp.) do panelu administracyjnego. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu i zapisaniu zamówienia w bazie danych. | Kluczowe dla wysyłania zdarzeń „Purchase” po stronie serwera za pośrednictwem CAPI, zapewniając wysłanie danych nawet jeśli klient zamknie przeglądarkę przed dotarciem do strony potwierdzenia. |
| `displayProductButtons` / `displayProductExtraContent` | Na stronie produktu, w pobliżu przycisku dodawania do koszyka lub opisu produktu. | Wstrzykuje JavaScript do śledzenia zdarzeń „ViewContent”. |
| `displayPaymentTop` | Na górze strony wyboru płatności podczas realizacji zamówienia. | Potencjalnie używany do śledzenia zdarzeń „InitiateCheckout”. |
| `displayFooter` | W sekcji stopki każdej strony. | Rzadziej używany do podstawowego śledzenia, ale może być używany do odroczonego ładowania skryptów lub specyficznych wyskakujących okienek zgody. |
| `actionObjectCustomerAddAfter` | Po utworzeniu nowego konta klienta. | Potencjalnie używany do wysyłania zdarzeń „SignUp” lub „Lead” do Amazona. |
| `actionObjectCustomerUpdateAfter` | Po zaktualizowaniu danych klienta. | Może być używany do aktualizacji danych klienta dla CAPI. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na MyPresta.eu.

-   **Aktualizacje modułu:** Zaloguj się do swojego konta na [MyPresta.eu Historia zamówień i pobieranie](https://mypresta.eu/my-account/orders/), aby pobrać najnowsze wersje modułu „Amazon Ads Tag Conversions API”.
-   **Wsparcie techniczne:** Jeśli napotkasz jakiekolwiek problemy lub masz pytania dotyczące funkcjonalności, konfiguracji lub integracji modułu, otwórz zgłoszenie do pomocy technicznej za pośrednictwem swojego konta klienta MyPresta.eu. Nasz zespół ekspertów jest gotowy do pomocy.
