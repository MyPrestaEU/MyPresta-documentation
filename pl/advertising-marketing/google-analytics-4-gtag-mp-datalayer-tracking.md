---
title: "Google Analytics 4 - śledzenie gtag, MP i dataLayer - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletny podręcznik użytkownika, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop Google Analytics 4 - gtag, MP & dataLayer tracking od MyPresta.eu."
sidebar:
  label: "Google Analytics 4 - śledzenie gtag, MP i dataLayer - Podręcznik dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Google Analytics 4 - gtag, MP & dataLayer tracking na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/google-analytics-4-gtag-mp-datalayer-tracking.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/google-analytics-4-gtag-mp-datalayer-tracking/)
>
> ---


# Google Analytics 4 - śledzenie gtag, MP i dataLayer

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP, takie jak cURL, JSON i OpenSSL, są wymagane do prawidłowego działania modułu, zwłaszcza w przypadku śledzenia Measurement Protocol po stronie serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Google Analytics 4 - gtag, MP & dataLayer tracking” oferuje kompleksowy zestaw opcji konfiguracji, dostępnych za pośrednictwem jego głównej strony konfiguracji i dedykowanych ekranów administracyjnych.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran, na którym skonfigurujesz śledzenie GA4. Moduł wykorzystuje interfejs przypominający kreator, aby poprowadzić Cię przez początkową konfigurację, ale zawsze możesz wrócić i dostosować ustawienia.

#### **Kreator początkowej konfiguracji**

Przy pierwszej konfiguracji prawdopodobnie powita Cię kreator. Postępuj zgodnie z jego krokami, aby szybko skonfigurować swoją główną usługę GA4.

- **Krok 1: Wybierz tryb śledzenia**

  - **Co robi to ustawienie:** Określa, w jaki sposób Twój sklep wysyła dane do Google Analytics 4. Jest to kluczowa decyzja oparta na Twojej konfiguracji technicznej i wymaganiach dotyczących prywatności.
  - **Efekt zmiany tego ustawienia:**
    - *`gtag.js` (Zalecane dla większości):* Jest to standardowy tag internetowy Google Analytics 4. Ładuje bibliotekę JavaScript (`gtag.js`) bezpośrednio na stronach Twojego sklepu, która następnie wysyła dane do GA4. Jest łatwy do wdrożenia, ale opiera się na wykonywaniu po stronie klienta w przeglądarce i zgodzie na pliki cookie.
    - *`dataLayer` (Dla użytkowników Google Tag Manager):* Ten tryb wypycha wszystkie dane zdarzeń GA4 do obiektu `dataLayer`, który następnie jest odczytywany przez Twój kontener Google Tag Manager (GTM) i wysyłany do GA4. Wybierz ten tryb, jeśli już używasz GTM do innych tagów i chcesz scentralizowanego zarządzania tagami.
    - *`Measurement Protocol` (Zaawansowane, dla maksymalnego odzyskiwania danych):* Ten tryb wysyła dane bezpośrednio z serwera PrestaShop do Google Analytics 4, całkowicie omijając przeglądarkę. Jest to idealne rozwiązanie do odzyskiwania danych, gdy śledzenie `gtag.js` lub `dataLayer` jest blokowane przez blokery reklam, ustawienia przeglądarki lub odmowę zgody na pliki cookie. Jest bardziej złożone, ale zapewnia najbardziej niezawodne zbieranie danych.
  - **Zalecana wartość:** `gtag.js` dla prostoty, `dataLayer` jeśli używasz GTM, `Measurement Protocol` jeśli dokładność danych jest najważniejsza i czujesz się komfortowo z zaawansowaną konfiguracją.
  - **Scenariusz / przykład sprzedawcy:** Jeśli chcesz szybko zacząć i nie używasz GTM, `gtag.js` jest idealny. Jeśli masz dedykowany zespół marketingowy zarządzający GTM, `dataLayer` integruje się bezproblemowo. Jeśli widzisz znaczne rozbieżności między sprzedażą a danymi GA4, `Measurement Protocol` może pomóc zmniejszyć tę lukę.
- **Krok 2: Wprowadź swoje identyfikatory pomiaru GA4**

  - **Co robi to ustawienie:** Jest to Twój unikalny identyfikator usługi Google Analytics 4 (np. `G-XXXXXXXXXX`). Moduł potrzebuje go, aby wiedzieć, gdzie wysyłać Twoje dane. Możesz dodać wiele identyfikatorów, jeśli śledzisz różne części swojego sklepu w oddzielnych usługach GA4.
  - **Efekt zmiany tego ustawienia:** Dane zostaną wysłane do określonej usługi GA4. Nieprawidłowe identyfikatory oznaczają brak danych lub dane wysłane w niewłaściwe miejsce.
  - **Zalecana wartość:** Twój główny identyfikator pomiaru GA4.
  - **Scenariusz / przykład sprzedawcy:** Masz główną usługę GA4 `G-ABCDEF1234`. Wprowadź ten identyfikator. Jeśli chcesz również wysyłać konkretne dane produktów do oddzielnej usługi `G-XYZW5678`, możesz ją również dodać.
- **Krok 3: Skonfiguruj zarządzanie zgodami (jeśli dotyczy)**

  - **Co robi to ustawienie:** Integruje się z rozwiązaniem do zarządzania zgodami na pliki cookie w Twoim sklepie, aby zapewnić, że śledzenie GA4 szanuje wybory użytkowników dotyczące prywatności.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Tagi GA4 zostaną uruchomione tylko wtedy, gdy użytkownik wyraził zgodę na analityczne pliki cookie.
    - *Wyłączone:* Tagi GA4 zostaną uruchomione niezależnie od zgody (niezalecane dla zgodności z RODO/CCPA).
  - **Zalecana wartość:** Włączone, i upewnij się, że masz zainstalowany i skonfigurowany solidny moduł zgody na pliki cookie.
  - **Scenariusz / przykład sprzedawcy:** Klient odwiedza Twój sklep i odmawia zgody na analityczne pliki cookie. Przy włączonym zarządzaniu zgodami, skrypty `gtag.js` lub `dataLayer` nie zostaną załadowane, co zapobiegnie śledzeniu po stronie klienta. Jeśli używasz Measurement Protocol, nadal możesz wysyłać anonimowe dane dotyczące zakupów po stronie serwera.

#### **Ustawienia ogólne (po kreatorze)**

Po zakończeniu kreatora zobaczysz bardziej szczegółowy interfejs konfiguracji, często zorganizowany w zakładki.

- **Zarządzanie identyfikatorami pomiaru**

  - **Co robi to ustawienie:** Umożliwia dodawanie, edytowanie lub usuwanie wielu identyfikatorów pomiaru GA4 (`G-XXXXXXXXXX`) i kojarzenie ich z określonymi trybami śledzenia.
  - **Efekt zmiany tego ustawienia:** Określa, które usługi GA4 otrzymują dane z Twojego sklepu.
  - **Zalecana wartość:** Zachowaj tylko niezbędne usługi GA4.
  - **Scenariusz / przykład sprzedawcy:** Utworzyłeś nową usługę GA4 dla konkretnej kampanii marketingowej. Możesz dodać jej identyfikator tutaj, aby śledzić wydajność specyficzną dla kampanii.
- **Domeny łączące (do śledzenia między domenami)**

  - **Co robi to ustawienie:** Jeśli Twój sklep działa na wielu domenach (np. `shop.example.com` i `blog.example.com`), to ustawienie pomaga Google Analytics zrozumieć, że są to części tej samej podróży użytkownika, zapobiegając rozpoczynaniu nowych sesji, gdy użytkownik nawiguje między nimi.
  - **Efekt zmiany tego ustawienia:** Zapewnia dokładne śledzenie podróży użytkownika w powiązanych domenach. Bez tego, użytkownicy przechodzący między Twoimi domenami mogą być liczeni jako nowi użytkownicy lub nowe sesje.
  - **Zalecana wartość:** Dodaj wszystkie powiązane domeny, które użytkownik może odwiedzić w ramach swojej podróży po Twojej witrynie.
  - **Scenariusz / przykład sprzedawcy:** Twój główny sklep to `mystore.com`, a Twój blog to `blog.mystore.com`. Dodaj `blog.mystore.com` do listy domen łączących.
- **Tryb debugowania**

  - **Co robi to ustawienie:** Aktywuje specjalny widok debugowania w front office i wysyła zdarzenia debugowania do GA4, umożliwiając weryfikację prawidłowego działania śledzenia.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Mały panel debugowania pojawia się w front office Twojego sklepu, pokazując, które zdarzenia GA4 są wysyłane. Zdarzenia pojawiają się również w widoku DebugView GA4.
    - *Wyłączone:* Brak panelu debugowania, normalne śledzenie.
  - **Zalecana wartość:** Włącz tylko podczas testowania i rozwiązywania problemów. Wyłącz dla działających sklepów produkcyjnych.
  - **Scenariusz / przykład sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz potwierdzić, że zdarzenia `add_to_cart` są prawidłowo wyzwalane. Włącz tryb debugowania, dodaj produkt do koszyka i sprawdź panel debugowania oraz widok DebugView GA4.
- **Trener jakości danych**

  - **Co robi to ustawienie:** Dostarcza informacji i rekomendacji w celu poprawy jakości i kompletności danych GA4. Sprawdza typowe problemy, takie jak brakujące identyfikatory produktów, nieprawidłowe formaty walut itp.
  - **Efekt zmiany tego ustawienia:** Jest to narzędzie diagnostyczne; nie zmienia bezpośrednio zachowania front office, ale pomaga identyfikować i naprawiać problemy, które mogą prowadzić do niedokładnej analityki.
  - **Zalecana wartość:** Regularnie przeglądaj rekomendacje.
  - **Scenariusz / przykład sprzedawcy:** Trener może poinformować Cię, że niektórym produktom brakuje kodów EAN/UPC, które są cenne dla danych produktów GA4. Możesz wtedy zaktualizować swój katalog produktów.
- **Lekarz katalogu**

  - **Co robi to ustawienie:** Analizuje Twój katalog produktów pod kątem potencjalnych problemów, które mogą wpływać na śledzenie GA4, takich jak produkty bez cen, zdjęć lub prawidłowych kategorii.
  - **Efekt zmiany tego ustawienia:** Podobnie jak Trener jakości danych, jest to narzędzie diagnostyczne, które zapewnia, że dane Twoich produktów są solidne dla GA4.
  - **Zalecana wartość:** Okresowo uruchamiaj tę kontrolę.
  - **Scenariusz / przykład sprzedawcy:** Lekarz może oznaczyć produkty, które są niedostępne, ale nadal widoczne, co może wprowadzać w błąd śledzenie wyświetleń produktów w GA4.
- **Statystyki na żywo**

  - **Co robi to ustawienie:** Wyświetla dane zdarzeń wysyłane z Twojego sklepu do GA4 w czasie rzeczywistym, bezpośrednio w panelu administracyjnym PrestaShop.
  - **Efekt zmiany tego ustawienia:** Zapewnia natychmiastowy przegląd ostatnich interakcji użytkowników i zdarzeń.
  - **Zalecana wartość:** Przydatne do monitorowania, zwłaszcza po wprowadzeniu zmian lub w okresach szczytowego ruchu.
  - **Scenariusz / przykład sprzedawcy:** Właśnie wprowadziłeś nowy produkt. Możesz obserwować statystyki na żywo, aby zobaczyć zdarzenia `view_item` i `add_to_cart` w czasie rzeczywistym.
- **Mapowanie i dostosowywanie zdarzeń**

  - **Co robi to ustawienie:** Umożliwia dostosowanie sposobu mapowania działań PrestaShop na zdarzenia GA4 i ich parametry. Na przykład, możesz chcieć wysłać niestandardowy parametr ze zdarzeniem `purchase`.
  - **Efekt zmiany tego ustawienia:** Precyzyjnie dostraja dane wysyłane do GA4, umożliwiając bardziej szczegółowe raportowanie i tworzenie odbiorców.
  - **Zalecana wartość:** Modyfikuj tylko, jeśli masz specyficzne potrzeby raportowania GA4.
  - **Scenariusz / przykład sprzedawcy:** Chcesz uwzględnić niestandardowy parametr `loyalty_program_status` z każdym zdarzeniem `purchase`. Możesz skonfigurować to mapowanie tutaj.
- **Reguły wielu usług**

  - **Co robi to ustawienie:** Definiuje reguły wysyłania określonych zdarzeń lub danych do różnych usług GA4. Na przykład, możesz wysyłać wszystkie zdarzenia do swojej głównej usługi, ale tylko zdarzenia „zakupu” dla konkretnej kategorii do oddzielnej usługi.
  - **Efekt zmiany tego ustawienia:** Umożliwia zaawansowaną segmentację danych analitycznych w wielu usługach GA4.
  - **Zalecana wartość:** Użyj, jeśli masz złożone wymagania dotyczące śledzenia obejmujące wiele usług GA4.
  - **Scenariusz / przykład sprzedawcy:** Masz główną usługę GA4 dla całego sklepu, ale masz również oddzielną usługę dla linii „Produktów Premium”. Możesz ustawić regułę, aby wysyłać zdarzenia `purchase` dla produktów z kategorii „Produkty Premium” do obu usług.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł udostępnia również dedykowane ekrany do bardziej zaawansowanego zarządzania i diagnostyki.

#### **AdminMyanalyticsAjaxController (Panel administracyjny > Moduły > Google Analytics 4 > [Różne zakładki])**

Ten kontroler obsługuje wiele interaktywnych elementów i wyświetlania danych w konfiguracji modułu, szczególnie w przypadku narzędzi diagnostycznych i statystyk na żywo. Nie będziesz bezpośrednio nawigować do tego kontrolera; zasila on dynamiczną zawartość na głównej stronie konfiguracji.

- **Nazwa ekranu i lokalizacja w menu:** Ten kontroler nie jest samodzielnym elementem menu. Obsługuje żądania AJAX dla różnych zakładek i sekcji na głównej stronie konfiguracji modułu (np. „Trener jakości danych”, „Lekarz katalogu”, „Statystyki na żywo”).
- **Dostępne działania i ustawienia:**
  - **Tabela Trenera jakości danych:** Wyświetla tabelę wykrytych problemów z jakością danych, często z sugestiami rozwiązania.
  - **Raport Lekarza katalogu:** Pokazuje raport o integralności danych produktów.
  - **Strumień zdarzeń na żywo:** Kanał zdarzeń wysyłanych do GA4 w czasie rzeczywistym.
  - **Kroki kreatora:** Obsługuje postęp i przesyłanie danych dla kreatora początkowej konfiguracji.
- **Efekt zmian:** Interakcja z tymi elementami (np. kliknięcie „Uruchom sprawdzanie” dla Trenera jakości danych) wyzwala procesy w tle, które analizują dane Twojego sklepu i aktualizują wyświetlane informacje. Pomaga to diagnozować i naprawiać problemy, ale nie zmienia bezpośrednio zachowania front office.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie sprawdzaj zakładki „Trener jakości danych” i „Lekarz katalogu”, aby upewnić się, że dane GA4 pozostają dokładne. Monitoruj „Statystyki na żywo” w krytycznych okresach lub po większych zmianach w sklepie.

#### **index.php (Panel administracyjny > Moduły > Google Analytics 4)**

Jest to główny punkt wejścia do konfiguracji modułu w panelu administracyjnym. Chociaż nazywa się `index.php`, jest to rdzeń metody `getContent()`, która renderuje cały interfejs konfiguracji, w tym wszystkie zakładki i ustawienia opisane w sekcji 4.1.

- **Nazwa ekranu i lokalizacja w menu:** **Moduły > Menedżer modułów > Google Analytics 4 - śledzenie gtag, MP i dataLayer > Konfiguruj**.
- **Dostępne działania i ustawienia:** Wszystkie ustawienia, zakładki i kroki kreatora wymienione w sekcji 4.1 są renderowane i zarządzane za pośrednictwem tego głównego widoku konfiguracji.
- **Efekt zmian:** Wszelkie zmiany zapisane na tym ekranie bezpośrednio wpływają na sposób implementacji śledzenia GA4 i na to, jakie dane są wysyłane do Google Analytics.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** To tutaj początkowo skonfigurujesz moduł i wrócisz, aby wprowadzić wszelkie większe zmiany w swoich usługach GA4, trybach śledzenia lub zaawansowanych regułach.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Główna konfiguracja | **Tryb śledzenia** | `gtag.js` | Definiuje sposób wysyłania danych (po stronie klienta, GTM lub po stronie serwera). Kluczowe dla dokładności danych i prywatności. |
| Główna konfiguracja | **Identyfikator(y) pomiaru** | Twój identyfikator GA4 (`G-XXXXXXXXXX`) | Określa, która usługa GA4 otrzymuje dane. Nieprawidłowe identyfikatory oznaczają brak danych. |
| Główna konfiguracja | **Zarządzanie zgodami** | Włączone (jeśli używasz modułu zgody) | Zapewnia, że śledzenie GA4 szanuje wybory użytkowników dotyczące prywatności. |
| Główna konfiguracja | **Domeny łączące** | Puste (dodaj, jeśli między domenami) | Umożliwia dokładne śledzenie użytkowników w wielu powiązanych domenach. |
| Główna konfiguracja | **Tryb debugowania** | Wyłączony (włącz do testowania) | Pokazuje panel debugowania w front office i wysyła zdarzenia debugowania do GA4. |
| Główna konfiguracja | **Trener jakości danych** | N/A (narzędzie diagnostyczne) | Identyfikuje i sugeruje poprawki dla problemów z jakością danych GA4. |
| Główna konfiguracja | **Lekarz katalogu** | N/A (narzędzie diagnostyczne) | Analizuje katalog produktów pod kątem gotowości do śledzenia GA4. |
| Główna konfiguracja | **Statystyki na żywo** | N/A (narzędzie monitorujące) | Wyświetla zdarzenia GA4 w czasie rzeczywistym w panelu administracyjnym. |
| Główna konfiguracja | **Mapowanie zdarzeń** | Domyślne (modyfikuj dla niestandardowych potrzeb) | Dostosowuje sposób mapowania działań PrestaShop na zdarzenia i parametry GA4. |
| Główna konfiguracja | **Reguły wielu usług** | Brak (dodaj dla zaawansowanego śledzenia) | Definiuje reguły wysyłania określonych danych do różnych usług GA4. |
| AdminMyanalyticsAjaxController | (Różne widoki oparte na AJAX) | N/A | Zapewnia dynamiczną zawartość dla narzędzi diagnostycznych i statystyk na żywo. |
| index.php | (Główna strona konfiguracji) | N/A | Renderuje cały interfejs konfiguracji modułu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Zainstalowałem moduł, ale nie widzę żadnych danych w mojej usłudze Google Analytics 4.**

- **O:** Po pierwsze, upewnij się, że wprowadziłeś prawidłowy identyfikator pomiaru GA4 (zaczynający się od `G-`) w konfiguracji modułu.
- **O:** Sprawdź „DebugView” swojej usługi GA4 (w Google Analytics przejdź do Administracja > DebugView) podczas przeglądania swojego sklepu. Jeśli widzisz tam zdarzenia, dane są wysyłane.
- **O:** Wyczyść pamięć podręczną Smarty PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).
- **O:** Jeśli używasz `gtag.js` lub `dataLayer`, sprawdź konsolę programisty przeglądarki (F12) pod kątem błędów JavaScript. Upewnij się również, że zaakceptowałeś analityczne pliki cookie, jeśli masz moduł zgody.
- **O:** Jeśli używasz Measurement Protocol, upewnij się, że Twój serwer ma włączony `cURL` i nie ma reguł zapory blokujących połączenia wychodzące do serwerów Google.

**P2: Moje dane zakupu w GA4 nie zgadzają się z danymi zamówień w PrestaShop.**

- **O:** Jest to częsty problem, często spowodowany przez blokery reklam, ustawienia prywatności przeglądarki lub odmowę zgody na pliki cookie przez użytkowników.
- **O:** **Zdecydowanie rozważ włączenie Measurement Protocol dla zdarzeń zakupu.** Wysyła to dane zakupu bezpośrednio z Twojego serwera, omijając problemy z przeglądarką po stronie klienta.
- **O:** Użyj „Trenera jakości danych” i „Lekarza katalogu” modułu, aby zidentyfikować wszelkie niespójności danych, które mogą powodować problemy.
- **O:** Upewnij się, że strona potwierdzenia zamówienia jest zawsze osiągana przez klientów po udanym zakupie. Jeśli klienci są przekierowywani gdzie indziej lub zbyt szybko zamykają przeglądarkę, zdarzenia zakupu po stronie klienta mogą nie zostać wyzwolone.

**P3: Panel debugowania modułu nie wyświetla się lub nie widzę zdarzeń w DebugView GA4.**

- **O:** Upewnij się, że „Tryb debugowania” jest wyraźnie włączony w konfiguracji modułu.
- **O:** Wyczyść pamięć podręczną przeglądarki i pamięć podręczną Smarty PrestaShop.
- **O:** Upewnij się, że jesteś zalogowany jako administrator w panelu administracyjnym PrestaShop i przeglądasz front office w tej samej sesji przeglądarki.
- **O:** Sprawdź konsolę programisty przeglądarki pod kątem błędów JavaScript, które mogą uniemożliwić załadowanie panelu debugowania.

**P4: Jak upewnić się, że moduł szanuje mój moduł zgody na pliki cookie?**

- **O:** Moduł jest zaprojektowany do integracji ze standardowymi mechanizmami zgody na pliki cookie. W konfiguracji modułu powinno znajdować się ustawienie „Zarządzanie zgodami”. Upewnij się, że jest ono włączone.
- **O:** Zweryfikuj, czy Twój moduł zgody na pliki cookie prawidłowo kategoryzuje analityczne pliki cookie i czy wybory użytkowników są przechowywane i szanowane. Moduł GA4 załaduje wtedy tagi po stronie klienta (`gtag.js`, `dataLayer`) tylko wtedy, gdy zostanie udzielona zgoda.
- **O:** Aby uzyskać maksymalne odzyskiwanie danych, rozważ użycie Measurement Protocol dla krytycznych zdarzeń, takich jak `purchase`, ponieważ często może on ominąć problemy ze zgodą po stronie klienta (chociaż nadal powinieneś informować użytkowników o przetwarzaniu danych).

**P5: Chcę śledzić niestandardowe zdarzenia lub parametry, które nie są objęte domyślną konfiguracją.**

- **O:** Moduł zawiera sekcję „Mapowanie i dostosowywanie zdarzeń”. Tutaj możesz zdefiniować, w jaki sposób działania PrestaShop mapują się na zdarzenia GA4 i dodawać niestandardowe parametry.
- **O:** W przypadku bardzo złożonego niestandardowego śledzenia, zwłaszcza z `dataLayer`, może być konieczne połączenie możliwości tego modułu z niestandardowymi skryptami w kontenerze Google Tag Manager.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `myanalytics` dla PrestaShop został zaprojektowany w celu zapewnienia solidnej i elastycznej integracji z Google Analytics 4. Wykorzystuje modułowe, obiektowe podejście, korzystając z wzorca MVC PrestaShop i systemu hooków.

Kluczowe komponenty architektury:

- **Główna klasa modułu (`Myanalytics`):** Obsługuje instalację, deinstalację, rejestrację hooków i główną metodę `getContent()` do konfiguracji panelu administracyjnego.
- **Fabryka trackerów (`MyanalyticsTrackerFactory`):** Dynamicznie tworzy odpowiedni mechanizm śledzenia (`gtag.js`, `dataLayer` lub `Measurement Protocol`) na podstawie konfiguracji modułu.
- **Dedykowane klasy trackerów:** Każda metoda śledzenia (`MyanalyticsGtagTracker`, `MyanalyticsDataLayerTracker`, `MyanalyticsMpTracker`) implementuje `MyanalyticsTrackerInterface` i hermetyzuje logikę wysyłania zdarzeń GA4 za pomocą swojej specyficznej metody.
- **Mapowanie zdarzeń i zarządzanie warstwą danych:** Klasy takie jak `MyanalyticsEvents` i `MyanalyticsDataLayerTracker` są odpowiedzialne za tłumaczenie działań PrestaShop (np. wyświetlenie produktu, dodanie do koszyka) na nazwy zdarzeń i parametry zgodne z GA4.
- **Narzędzia diagnostyczne:** Klasy takie jak `MyanalyticsDataQualityCoach`, `MyanalyticsCatalogDoctor` i `MyanalyticsHealthScore` dostarczają informacji w panelu administracyjnym na temat integralności danych i stanu śledzenia.
- **Kontrolery administracyjne:** Obsługują żądania AJAX dotyczące dynamicznej zawartości w panelu administracyjnym (np. statystyki na żywo, raporty diagnostyczne).
- **Kontrolery front-office:** Głównie używane do punktów końcowych AJAX, zwłaszcza dla Measurement Protocol fallback lub działań związanych ze zgodą.
- **Szablony Smarty:** Używane do renderowania zarówno widoków konfiguracji panelu administracyjnego, jak i skryptów śledzących front-office wstrzykiwanych za pomocą hooków.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

- `controllers/front/ajax.php`
  - **Nazwa klasy i klasa nadrzędna:** `MyanalyticsAjaxModuleFrontController` rozszerza `ModuleFrontController`.
  - **Odpowiedzialność:** Obsługuje żądania AJAX z front office. Może to obejmować wysyłanie zdarzeń Measurement Protocol w określonych scenariuszach (np. gdy śledzenie po stronie klienta jest zablokowane), aktualizowanie statusu zgody lub inne dynamiczne interakcje, które nie wymagają pełnego przeładowania strony. Zazwyczaj zwraca odpowiedzi JSON.
- `controllers/front/index.php`
  - **Nazwa klasy i klasa nadrzędna:** `MyanalyticsIndexModuleFrontController` rozszerza `ModuleFrontController`.
  - **Odpowiedzialność:** Ten kontroler może służyć jako fallback lub specyficzny punkt końcowy dla niektórych funkcji modułu, chociaż często główna klasa modułu obsługuje większość wstrzykiwania skryptów front-office za pomocą hooków. Może być używany do specyficznych przekierowań lub przetwarzania danych, jeśli jest to konieczne.

#### Kontrolery administracyjne Back-Office

- `controllers/admin/AdminMyanalyticsAjaxController.php`
  - **Nazwa klasy i klasa nadrzędna:** `AdminMyanalyticsAjaxController` rozszerza `AdminController`.
  - **Nazwa zakładki i zarządzana encja:** Ten kontroler nie jest bezpośrednio dostępny jako zakładka menu. Obsługuje żądania AJAX z głównej strony konfiguracji modułu (`getContent()`). Obsługuje dynamiczne aktualizacje dla sekcji takich jak Trener jakości danych, Lekarz katalogu, Statystyki na żywo i kroki kreatora konfiguracji.
  - **Odpowiedzialność:** Przetwarza żądania dotyczące raportów diagnostycznych, danych zdarzeń na żywo i przesyłania kroków kreatora, zwracając dane JSON w celu aktualizacji interfejsu użytkownika panelu administracyjnego.
- `controllers/admin/index.php`
  - **Nazwa klasy i klasa nadrzędna:** `AdminMyanalyticsIndexController` rozszerza `AdminController`.
  - **Nazwa zakładki i zarządzana encja:** Podobnie jak `AdminMyanalyticsAjaxController`, jest to prawdopodobnie wewnętrzny kontroler lub placeholder. Główna konfiguracja panelu administracyjnego jest obsługiwana przez metodę `getContent()` głównej klasy modułu `Myanalytics`.

### 4.3 Klasy podstawowe i modele (`classes/`)

- `classes/autoload.php`: Standardowy plik autoload PrestaShop dla klas modułów.
- `classes/index.php`: Pusty plik, powszechna praktyka zapobiegania listowaniu katalogów.
- `classes/MyanalyticsCatalogDoctor.php`
  - **Co robi:** Analizuje katalog produktów PrestaShop pod kątem problemów z jakością danych istotnych dla śledzenia GA4 (np. brakujące ceny, obrazy, nieprawidłowe kategorie).
  - **Kluczowe metody publiczne:** Metody do uruchamiania kontroli i pobierania raportów o stanie katalogu.
- `classes/MyanalyticsConsent.php`
  - **Co robi:** Zarządza i współdziała z mechanizmami zgody na pliki cookie, określając, czy śledzenie analityczne jest dozwolone na podstawie wyborów użytkownika.
  - **Kluczowe metody publiczne:** Metody do sprawdzania statusu zgody, ustawiania zgody i potencjalnej integracji z modułami zgody innych firm.
- `classes/MyanalyticsCurrencyHelper.php`
  - **Co robi:** Dostarcza funkcji pomocniczych do obsługi formatowania i konwersji walut, zapewniając, że GA4 otrzymuje dane walutowe w prawidłowym formacie.
- `classes/MyanalyticsDataLayerTracker.php`
  - **Co robi:** Implementuje `MyanalyticsTrackerInterface` dla śledzenia `dataLayer`. Wypycha dane zdarzeń GA4 do tablicy JavaScript `dataLayer`, udostępniając je Google Tag Managerowi.
  - **Kluczowe metody publiczne:** Metody do dodawania zdarzeń do dataLayer, obsługi specyficznych zdarzeń e-commerce (np. `add_to_cart`, `purchase`).
- `classes/MyanalyticsDataQualityCoach.php`
  - **Co robi:** Dostarcza narzędzie diagnostyczne do identyfikowania i raportowania potencjalnych problemów z jakością danych w strumieniu zdarzeń GA4 lub konfiguracji.
  - **Kluczowe metody publiczne:** Metody do uruchamiania kontroli jakości danych i generowania raportów.
- `classes/MyanalyticsEventId.php`
  - **Co robi:** Prawdopodobnie klasa narzędziowa do generowania unikalnych identyfikatorów zdarzeń, które mogą być przydatne do deduplikacji w GA4, zwłaszcza z Measurement Protocol.
- `classes/MyanalyticsEventMap.php`
  - **Co robi:** Definiuje mapowanie między działaniami/danymi PrestaShop a standardowymi nazwami zdarzeń i parametrami GA4.
  - **Kluczowe metody publiczne:** Metody do pobierania definicji zdarzeń i mapowań parametrów.
- `classes/MyanalyticsEvents.php`
  - **Co robi:** Centralna klasa do wyzwalania i zarządzania zdarzeniami GA4 w module. Koordynuje, który tracker (gtag, datalayer, MP) powinien obsługiwać które zdarzenie.
  - **Kluczowe metody publiczne:** Metody takie jak `trackPageView()`, `trackAddToCart()`, `trackPurchase()` itp.
- `classes/MyanalyticsGtagTracker.php`
  - **Co robi:** Implementuje `MyanalyticsTrackerInterface` dla śledzenia `gtag.js`. Generuje i wstrzykuje niezbędny kod JavaScript do wysyłania zdarzeń bezpośrednio do GA4 za pomocą `gtag()`.
  - **Kluczowe metody publiczne:** Metody do generowania wywołań `gtag()` dla różnych zdarzeń GA4.
- `classes/MyanalyticsHealthScore.php`
  - **Co robi:** Oblicza i wyświetla „wynik zdrowia” integracji GA4, oparty na różnych kontrolach i najlepszych praktykach.
- `classes/MyanalyticsLiveStats.php`
  - **Co robi:** Zbiera i dostarcza statystyki w czasie rzeczywistym dotyczące zdarzeń wysyłanych do GA4, wyświetlane w panelu administracyjnym.
- `classes/MyanalyticsMpClient.php`
  - **Co robi:** Obsługuje rzeczywiste żądania HTTP do wysyłania danych do Google Analytics 4 za pośrednictwem Measurement Protocol.
  - **Kluczowe metody publiczne:** Metody do konstruowania i wysyłania ładunków Measurement Protocol.
- `classes/MyanalyticsMpTracker.php`
  - **Co robi:** Implementuje `MyanalyticsTrackerInterface` dla śledzenia `Measurement Protocol`. Przygotowuje dane zdarzeń i używa `MyanalyticsMpClient` do wysyłania ich po stronie serwera.
  - **Kluczowe metody publiczne:** Metody do formatowania i wysyłania zdarzeń po stronie serwera.
- `classes/MyanalyticsProductIdResolver.php`
  - **Co robi:** Rozwiązuje różne identyfikatory produktów (ID, referencja, EAN, UPC), aby zapewnić spójne dane produktów wysyłane do GA4.
- `classes/MyanalyticsPropertyRules.php`
  - **Co robi:** Zarządza logiką śledzenia wielu usług, definiując reguły, które zdarzenia trafiają do których usług GA4.
- `classes/MyanalyticsTrackerFactory.php`
  - **Co robi:** Klasa wzorca fabryki odpowiedzialna za tworzenie i zwracanie prawidłowej implementacji `MyanalyticsTrackerInterface` na podstawie konfiguracji modułu (gtag, datalayer lub MP).
- `classes/MyanalyticsTrackerInterface.php`
  - **Co robi:** Definiuje wspólny interfejs, który muszą implementować wszystkie klasy trackerów GA4, zapewniając spójność w obsłudze zdarzeń.
- `classes/MyanalyticsUserData.php`
  - **Co robi:** Zbiera i formatuje dane specyficzne dla użytkownika (np. ID użytkownika, dane demograficzne) do śledzenia GA4, z poszanowaniem ustawień prywatności.

### 4.4 Zasoby JavaScript (`views/js/`)

- `myanalytics/views/js/myanalytics-admin.js`
  - **Zakres:** Panel administracyjny.
  - **Co robi:** Zapewnia interaktywną funkcjonalność dla stron konfiguracji modułu w panelu administracyjnym. Obejmuje to obsługę przesyłania formularzy, wywołań AJAX dla narzędzi diagnostycznych (Trener jakości danych, Lekarz katalogu), aktualizowanie statystyk na żywo i zarządzanie regułami wielu usług.
- `myanalytics/views/js/myanalytics-debug.js`
  - **Zakres:** Front-office (gdy tryb debugowania jest włączony).
  - **Co robi:** Wstrzykuje panel debugowania do front office, wyświetlając zdarzenia GA4 w miarę ich wyzwalania. Nasłuchuje wywołań `gtag()` lub zdarzeń `dataLayer.push()` i renderuje je w celu łatwej weryfikacji.
- `myanalytics/views/js/myanalytics-ghost.js`
  - **Zakres:** Front-office.
  - **Co robi:** Ten skrypt może być związany z „ghost” lub „shadow” śledzeniem, potencjalnie dla Measurement Protocol fallback lub do przechwytywania zdarzeń, które w przeciwnym razie mogłyby zostać pominięte. Może obejmować nasłuchiwanie specyficznych zdarzeń DOM i wyzwalanie wywołań po stronie serwera.
- `myanalytics/views/js/myanalytics-live.js`
  - **Zakres:** Panel administracyjny.
  - **Co robi:** Zasila funkcję „Statystyki na żywo” w panelu administracyjnym. Prawdopodobnie używa AJAX do okresowego pobierania ostatnich zdarzeń GA4 z serwera i aktualizuje wyświetlanie w czasie rzeczywistym.
- `myanalytics/views/js/myanalytics-wizard.js`
  - **Zakres:** Panel administracyjny.
  - **Co robi:** Zapewnia interaktywną logikę dla kreatora konfiguracji modułu, prowadząc użytkownika przez początkowe kroki konfiguracji, walidując dane wejściowe i przesyłając dane za pośrednictwem AJAX.
- `myanalytics/views/js/myanalytics.js`
  - **Zakres:** Front-office.
  - **Co robi:** Główny plik JavaScript front-office. Obsługuje podstawową logikę śledzenia GA4 po stronie klienta, w tym:
    - Inicjalizację `gtag.js` lub `dataLayer`.
    - Nasłuchiwanie zdarzeń DOM (np. kliknięć przycisków „Dodaj do koszyka”, wyświetleń zdjęć produktów).
    - Zbieranie odpowiednich danych produktów i użytkowników.
    - Wypychanie zdarzeń do `dataLayer` lub wywoływanie poleceń `gtag()`.
    - Potencjalnie obsługę integracji ze zgodą na pliki cookie.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `myanalytics/views/css/myanalytics-admin.css`
  - **Zakres:** Stylizacja formularzy panelu administracyjnego.
  - **Co robi:** Stylizuje stronę konfiguracji modułu, w tym zakładki, pola wejściowe, przyciski, raporty diagnostyczne i wyświetlanie statystyk na żywo, zapewniając spójny i przyjazny dla użytkownika interfejs w panelu administracyjnym PrestaShop.
- `myanalytics/views/css/myanalytics-debug.css`
  - **Zakres:** Stylizacja front-office dla klienta (gdy tryb debugowania jest włączony).
  - **Co robi:** Stylizuje panel debugowania front-office, czyniąc go wizualnie wyraźnym i czytelnym dla programistów i administratorów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

- `myanalytics/views/templates/hook/debug.tpl`
  - **Hook:** Prawdopodobnie wstrzykiwany za pomocą `displayHeader` lub `displayFooter` warunkowo, gdy tryb debugowania jest aktywny.
  - **Wyjścia:** Struktura HTML dla panelu debugowania front-office.
- `myanalytics/views/templates/hook/displayOrderConfirmation.tpl`
  - **Hook:** `displayOrderConfirmation`.
  - **Wyjścia:** Niezbędny kod JavaScript lub wypchnięcia `dataLayer` dla zdarzenia `purchase`, zazwyczaj zawierające szczegóły transakcji, informacje o produkcie i potencjalnie parametry Measurement Protocol.
- `myanalytics/views/templates/hook/ghost.tpl`
  - **Hook:** Może to być `displayHeader` lub `displayFooter`.
  - **Wyjścia:** Kod JavaScript związany ze śledzeniem „ghost”, potencjalnie dla Measurement Protocol fallback lub zaawansowanego przechwytywania zdarzeń.
- `myanalytics/views/templates/hook/header.tpl`
  - **Hook:** `displayHeader`.
  - **Wyjścia:** Główny skrypt inicjalizacyjny `gtag.js` lub `dataLayer`, zawierający identyfikatory pomiaru GA4 i wszelkie globalne ustawienia konfiguracji. Jest to kluczowe dla początkowego śledzenia wyświetleń stron.
- `myanalytics/views/templates/hook/mp-pageview.tpl`
  - **Hook:** Prawdopodobnie `displayHeader` lub `displayFooter` (warunkowo dla Measurement Protocol).
  - **Wyjścia:** Kod renderowany po stronie serwera do wysyłania zdarzenia `page_view` za pośrednictwem Measurement Protocol, szczególnie przydatny, gdy śledzenie po stronie klienta jest zablokowane lub zgoda jest odmówiona.
- `myanalytics/views/templates/hook/payment.tpl`
  - **Hook:** `displayPaymentTop` lub podobne hooki związane z płatnościami.
  - **Wyjścia:** Wypchnięcia JavaScript lub `dataLayer` dla zdarzeń `add_payment_info` lub `begin_checkout`, przechwytujące wybór metody płatności.
- `myanalytics/views/templates/hook/product-details.tpl`
  - **Hook:** `displayProductButtons`, `displayProductExtraContent` lub podobne hooki strony produktu.
  - **Wyjścia:** Wypchnięcia JavaScript lub `dataLayer` dla zdarzeń `view_item` i `add_to_cart`, zawierające szczegółowe informacje o produkcie.

#### Szablony administracyjne (`views/templates/admin/`)

- `myanalytics/views/templates/admin/doctor.tpl`: Renderuje interfejs dla Lekarza katalogu, wyświetlając raporty i rekomendacje.
- `myanalytics/views/templates/admin/dq.tpl`: Renderuje interfejs dla Trenera jakości danych, pokazując problemy z jakością danych.
- `myanalytics/views/templates/admin/health.tpl`: Wyświetla ogólny wynik zdrowia i powiązane metryki dla integracji GA4.
- `myanalytics/views/templates/admin/linker-domains.tpl`: Renderuje pole wejściowe i listę do zarządzania domenami łączącymi między domenami.
- `myanalytics/views/templates/admin/live-maintain.tpl`: Prawdopodobnie podszablon dla statystyk na żywo, być może dla komunikatów konserwacyjnych lub kontroli.
- `myanalytics/views/templates/admin/live.tpl`: Renderuje główny interfejs dla funkcji Statystyk na żywo, pokazując dane zdarzeń w czasie rzeczywistym.
- `myanalytics/views/templates/admin/measurement-ids.tpl`: Renderuje sekcję do zarządzania wieloma identyfikatorami pomiaru GA4.
- `myanalytics/views/templates/admin/mode-context.tpl`: Dostarcza informacji kontekstowych lub wyjaśnień dla wybranego trybu śledzenia.
- `myanalytics/views/templates/admin/mode-note-datalayer.tpl`: Specyficzne uwagi lub instrukcje dla trybu śledzenia `dataLayer`.
- `myanalytics/views/templates/admin/mode-note-gtag.tpl`: Specyficzne uwagi lub instrukcje dla trybu śledzenia `gtag.js`.
- `myanalytics/views/templates/admin/mode-note-mp.tpl`: Specyficzne uwagi lub instrukcje dla trybu śledzenia `Measurement Protocol`.
- `myanalytics/views/templates/admin/mode-picker.tpl`: Renderuje przyciski radiowe lub listę rozwijaną do wyboru trybu śledzenia GA4.
- `myanalytics/views/templates/admin/properties-list.tpl`: Wyświetla listę skonfigurowanych usług GA4.
- `myanalytics/views/templates/admin/recent-events.tpl`: Podszablon do wyświetlania listy ostatnich zdarzeń, często używany w statystykach na żywo lub widokach debugowania.
- `myanalytics/views/templates/admin/tabs.tpl`: Renderuje strukturę nawigacji po zakładkach dla strony konfiguracji modułu.
- `myanalytics/views/templates/admin/tag-chips.tpl`: Wyświetla wizualne „chipsy” lub etykiety dla skonfigurowanych tagów/usług GA4.
- `myanalytics/views/templates/admin/wizard.tpl`: Renderuje ogólną strukturę i kroki kreatora konfiguracji modułu.

#### Szablony front-office (`views/templates/front/`)

Moduł nie wydaje się mieć dedykowanych samodzielnych szablonów stron front-office, polegając zamiast tego na wstrzykiwaniu skryptów i danych za pośrednictwem hooków.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł przechowuje swoją konfigurację głównie w tabeli `ps_configuration` PrestaShop.
  - Może również tworzyć niestandardowe tabele dla:
    - `ps_myanalytics_events`: Do logowania zdarzeń Measurement Protocol lub innych wewnętrznych danych zdarzeń do debugowania/statystyk na żywo.
    - `ps_myanalytics_properties`: Do przechowywania szczegółów o wielu usługach GA4 i ich powiązanych regułach.
    - `ps_myanalytics_consent`: Do przechowywania statusu zgody lub integracji z modułami zgody.
    - `ps_myanalytics_health_log`: Do przechowywania wyników kontroli stanu i raportów jakości danych.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykiwanie skryptów inicjalizacyjnych `gtag.js` lub `dataLayer`, globalnej konfiguracji GA4 i potencjalnie zdarzeń `page_view`. |
| `displayFooter` | Przed zamykającym tagiem `</body>` każdej strony. | Wstrzykiwanie dodatkowych skryptów śledzących, paneli debugowania lub wywołań Measurement Protocol fallback. |
| `displayOrderConfirmation` | Na stronie potwierdzenia zamówienia po udanym zakupie. | Wysyłanie kluczowego zdarzenia `purchase` do GA4, w tym szczegółów transakcji i danych produktów. To często tutaj wykorzystywany jest Measurement Protocol. |
| `displayProductButtons` | W pobliżu przycisków akcji produktu (np. „Dodaj do koszyka”) na stronie produktu. | Wstrzykiwanie JavaScript do przechwytywania zdarzeń `add_to_cart`. |
| `displayProductExtraContent` | W sekcji dodatkowej zawartości strony produktu. | Wstrzykiwanie JavaScript dla zdarzeń `view_item` lub innych interakcji ze szczegółami produktu. |
| `displayPaymentTop` | Przed opcjami płatności na stronie realizacji zamówienia. | Przechwytywanie zdarzeń `begin_checkout` i `add_payment_info`. |
| `actionFrontControllerSetMedia` | Gdy kontroler front-office ustawia swoje zasoby multimedialne. | Dodawanie do kolejki plików JS/CSS specyficznych dla modułu dla front office. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny ustawia swoje zasoby multimedialne. | Dodawanie do kolejki plików JS/CSS specyficznych dla modułu dla panelu administracyjnego. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Wyzwalanie zdarzeń `purchase` Measurement Protocol po stronie serwera, zapewniając przechwytywanie danych nawet jeśli po stronie klienta zawiedzie. |
| `actionObjectProductAddAfter` | Po dodaniu nowego produktu. | Potencjalne wyzwalanie kontroli lekarza katalogu lub aktualizacja wewnętrznych pamięci podręcznych danych produktów. |
| `actionObjectProductUpdateAfter` | Po zaktualizowaniu istniejącego produktu. | Podobnie jak `actionObjectProductAddAfter`. |
| `actionObjectProductDeleteAfter` | Po usunięciu produktu. | Czyszczenie wszelkich powiązanych danych śledzenia lub pamięci podręcznych. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i upewnienia się, że używasz najnowszej, najbardziej kompatybilnej wersji modułu „Google Analytics 4 - gtag, MP & dataLayer tracking”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/).

MyPresta.eu zapewnia dedykowane wsparcie dla wszystkich swoich modułów, zapewniając, że integracja analityki Twojego sklepu pozostaje solidna i aktualna z najnowszymi standardami GA4 i wersjami PrestaShop.
"""
