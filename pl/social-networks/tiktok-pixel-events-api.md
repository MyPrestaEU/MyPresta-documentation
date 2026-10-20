---
title: "TikTok Pixel / Events API - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop TikTok Pixel / Events API od MyPresta.eu."
sidebar:
  label: "TikTok Pixel / Events API - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł TikTok Pixel / Events API na MyPresta.eu](https://mypresta.eu/modules/social-networks/tiktok-pixel-events-api.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/tiktok-pixel-events-api/)
>
> ---


# TikTok Pixel / Events API

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są wymagane do prawidłowego działania modułu, zwłaszcza dla Events API (śledzenie po stronie serwera). Są one zazwyczaj dostępne w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj)

To jest główny obszar konfiguracji, w którym ustawisz swój TikTok Pixel i Events API. Ustawienia zostały zaprojektowane tak, aby były intuicyjne, prowadząc Cię przez proces łączenia Twojego sklepu z TikTok Ads.

#### **Ustawienia ogólne**

-   **ID Piksela TikTok:**
    *   **Co robi to ustawienie:** To jest Twój unikalny identyfikator dostarczony przez TikTok Ads Manager. Informuje TikTok, do którego konta reklamowego należą dane z Twojej witryny.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po wprowadzeniu:* Moduł zacznie wysyłać dane do Twojego określonego Piksela TikTok.
        *   *Po pozostawieniu pustego:* Żadne dane nie zostaną wysłane do TikTok za pośrednictwem Piksela, a moduł nie będzie działać w zakresie śledzenia po stronie przeglądarki.
    *   **Zalecana wartość:** Twój prawidłowy ID Piksela TikTok.
    *   **Scenariusz / przykład dla sprzedawcy:** Tworzysz konto reklamowe TikTok i konfigurujesz Piksel. TikTok dostarcza Ci numeryczny ID (np. `1234567890`). Wprowadzasz ten ID tutaj, aby połączyć swój sklep z kontem TikTok.
-   **Token dostępu TikTok (dla Events API):**
    *   **Co robi to ustawienie:** To jest bezpieczny token wygenerowany w Twoim TikTok Ads Manager, który autoryzuje Twój sklep PrestaShop do wysyłania danych bezpośrednio na serwery TikTok za pośrednictwem Events API. Jest to kluczowe dla śledzenia po stronie serwera.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po wprowadzeniu:* Włącza śledzenie po stronie serwera (Events API), które jest bardziej niezawodne i mniej podatne na blokery reklam.
        *   *Po pozostawieniu pustego:* Śledzenie po stronie serwera zostanie wyłączone.
    *   **Zalecana wartość:** Twój prawidłowy Token dostępu TikTok Events API.
    *   **Scenariusz / przykład dla sprzedawcy:** Aby poprawić dokładność danych i ominąć ograniczenia przeglądarki, decydujesz się użyć Events API. Generujesz Token dostępu w TikTok Ads Manager i wklejasz go tutaj.
-   **Tryb śledzenia:**
    *   **Co robi to ustawienie:** Określa, w jaki sposób dane są wysyłane do TikTok. Możesz wybrać między Pikselem (po stronie przeglądarki), Events API (po stronie serwera) lub Trybem podwójnym (oba).
    *   **Efekt zmiany tego ustawienia:**
        *   *Tylko Piksel:* Aktywne jest tylko śledzenie po stronie przeglądarki.
        *   *Tylko Events API:* Aktywne jest tylko śledzenie po stronie serwera.
        *   *Tryb podwójny (zalecany):* Aktywne są zarówno Piksel, jak i Events API. Moduł inteligentnie wykorzystuje współdzielony `event_id` do deduplikacji zdarzeń w TikTok, zapewniając dokładność.
    *   **Zalecana wartość:** `Tryb podwójny` dla maksymalnej dokładności danych i odporności na blokery reklam.
    *   **Scenariusz / przykład dla sprzedawcy:** Chcesz uzyskać najbardziej niezawodne śledzenie. Wybierasz „Tryb podwójny”, aby jeśli klient użyje blokera reklam, Events API po stronie serwera nadal mogło przechwycić konwersję, a TikTok nie policzy jej dwukrotnie, jeśli obie metody się powiodą.
-   **Włącz tryb debugowania:**
    *   **Co robi to ustawienie:** Aktywuje specjalny tryb, który wyświetla szczegółowe informacje o wysyłanych zdarzeniach TikTok, bezpośrednio w konsoli programisty Twojej przeglądarki. Jest to nieocenione przy rozwiązywaniu problemów.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po włączeniu:* Programiści i zaawansowani użytkownicy mogą zobaczyć dokładnie, jakie dane są wysyłane do TikTok w czasie rzeczywistym, co pomaga zweryfikować poprawną konfigurację.
        *   *Po wyłączeniu:* Nie są wyświetlane żadne informacje debugowania.
    *   **Zalecana wartość:** `Nie` dla działających sklepów produkcyjnych. Włączaj tylko tymczasowo do testowania i debugowania.
    *   **Scenariusz / przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz upewnić się, że zdarzenia `AddToCart` są wyzwalane poprawnie. Włączasz tryb debugowania, dodajesz przedmiot do koszyka i sprawdzasz konsolę przeglądarki pod kątem danych zdarzeń TikTok.

#### **Ustawienia zaawansowane**

-   **Zarządzanie zgodami (RODO/CCPA):**
    *   **Co robi to ustawienie:** Integruje się z rozwiązaniem do zarządzania zgodami na pliki cookie Twojego sklepu (jeśli jest dostępne), aby zapewnić, że śledzenie TikTok aktywuje się tylko po wyrażeniu zgody przez klienta.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po włączeniu:* TikTok Pixel/Events API załaduje i wyśle dane tylko wtedy, gdy klient zaakceptował pliki cookie.
        *   *Po wyłączeniu:* Śledzenie będzie odbywać się niezależnie od zgody na pliki cookie, co może nie być zgodne z przepisami o ochronie prywatności, takimi jak RODO czy CCPA.
    *   **Zalecana wartość:** `Tak`, jeśli Twój sklep działa w regionach z surowymi przepisami o ochronie prywatności (np. UE, Kalifornia).
    *   **Scenariusz / przykład dla sprzedawcy:** Twój sklep obsługuje klientów w Unii Europejskiej. Aby zachować zgodność z RODO, włączasz to ustawienie, zapewniając, że śledzenie TikTok szanuje wybory użytkowników dotyczące prywatności.
-   **Typ ID produktu:**
    *   **Co robi to ustawienie:** Określa, który identyfikator produktu (ID) jest wysyłany do TikTok. Opcje zazwyczaj obejmują wewnętrzny ID produktu PrestaShop, EAN13, UPC lub niestandardowy numer referencyjny. Jest to kluczowe dla dopasowania produktów w Twoim Katalogu Produktów TikTok.
    *   **Efekt zmiany tego ustawienia:**
        *   *Zmiana typu:* Zapewnia, że ID produktów wysyłane do TikTok pasują do ID używanych w Twoim Katalogu Produktów TikTok, umożliwiając dynamiczne reklamy produktów.
    *   **Zalecana wartość:** Wybierz typ ID, którego używasz w swoim Katalogu Produktów TikTok. Często `ID produktu` PrestaShop lub `EAN13` są popularnymi wyborami.
    *   **Scenariusz / przykład dla sprzedawcy:** Przesłałeś katalog produktów do TikTok, używając kodów EAN13 swoich produktów. Wybierasz `EAN13` tutaj, aby upewnić się, że TikTok może poprawnie zidentyfikować, które produkty klienci przeglądają lub kupują.
-   **Domeny łączące (dla śledzenia między domenami):**
    *   **Co robi to ustawienie:** Pozwala określić dodatkowe nazwy domen, jeśli podróż klienta obejmuje wiele domen (np. główny sklep i oddzielny blog na innej domenie). Pomaga to TikTok płynnie śledzić użytkowników między tymi domenami.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po dodaniu domen:* TikTok może utrzymać spójność śledzenia użytkowników na wymienionych domenach.
        *   *Po pozostawieniu pustego:* Śledzenie może zostać przerwane, jeśli klienci nawigują między różnymi domenami, które są częścią Twojej firmy.
    *   **Zalecana wartość:** Dodaj wszystkie odpowiednie subdomeny lub połączone domeny, które Twoi klienci mogą odwiedzić.
    *   **Scenariusz / przykład dla sprzedawcy:** Twój główny sklep to `moj-sklep.com`, ale masz blog pod adresem `blog.moj-sklep.com`, gdzie linkujesz do produktów. Dodanie `blog.moj-sklep.com` tutaj zapewnia, że TikTok może śledzić użytkowników z bloga do Twojego sklepu.

#### **Jakość danych i wynik zdrowia**

Ta sekcja dostarcza informacji na temat wydajności i dokładności śledzenia TikTok.

-   **Wynik zdrowia (Health Score):**
    *   **Co to robi:** Wyświetla wynik wskazujący ogólny stan i dokładność przesyłania danych do TikTok. Wyższy wynik oznacza lepszą jakość danych.
    *   **Efekt:** Pomaga szybko zidentyfikować, czy występują problemy z konfiguracją śledzenia, które mogą wpływać na wydajność reklam.
    *   **Zalecane:** Dąż do wysokiego wyniku. Moduł dostarczy rekomendacji, jeśli wynik jest niski.
-   **Radar odzyskiwania (Recovery Radar):**
    *   **Co to robi:** Monitoruje porzucone koszyki i dostarcza informacji na temat potencjalnych utraconych sprzedaży, pomagając zidentyfikować możliwości kampanii retargetingowych.
    *   **Efekt:** Daje szybki przegląd, ile koszyków zostało zainicjowanych w porównaniu do ukończonych, podkreślając obszary do poprawy w procesie płatności lub strategii retargetingu.
-   **Statystyki na żywo (Live Statistics):**
    *   **Co to robi:** Pokazuje dane w czasie rzeczywistym dotyczące zdarzeń wysyłanych do TikTok, pozwalając sprawdzić, czy zdarzenia są wyzwalane zgodnie z oczekiwaniami.
    *   **Efekt:** Zapewnia natychmiastową informację zwrotną podczas testowania i bieżącego monitorowania, potwierdzając, że śledzenie jest aktywne i dokładne.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł rozszerza Panel Administracyjny PrestaShop o kilka dedykowanych ekranów, które pomagają zarządzać i monitorować integrację z TikTok. Są one zazwyczaj dostępne ze strony konfiguracji modułu za pośrednictwem zakładek lub dedykowanych pozycji menu.

#### **AdminMytiktokAjaxController (Operacje Ajax)**

-   **Nazwa ekranu i lokalizacja w menu:** Ten kontroler obsługuje głównie żądania AJAX w tle ze strony konfiguracji modułu. Nie będziesz bezpośrednio nawigować do „ekranu” dla tego kontrolera, ale zasila on dynamiczne aktualizacje i pobieranie danych w głównych zakładkach konfiguracji modułu (np. Statystyki na żywo, Wynik zdrowia, Logi zdarzeń).
-   **Dostępne działania i ustawienia:** Przetwarza żądania dotyczące:
    *   Pobierania danych zdarzeń na żywo.
    *   Aktualizowania wyników zdrowia.
    *   Pobierania informacji diagnostycznych.
    *   Zapisywania konkretnych części konfiguracji bez pełnego przeładowania strony.
-   **Efekt zmian:** Interakcje na głównej stronie konfiguracji modułu (takie jak odświeżanie statystyk na żywo lub uruchamianie diagnostyki) wyzwalają ten kontroler do pobierania i wyświetlania odpowiednich danych.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Interagujesz z tym pośrednio, używając różnych narzędzi diagnostycznych i monitorujących dostępnych na głównej stronie konfiguracji modułu.

#### **index.php (Główny punkt wejścia modułu)**

-   **Nazwa ekranu i lokalizacja w menu:** To jest główny punkt wejścia do konfiguracji modułu, dostępny poprzez **Panel Administracyjny > Moduły > Menedżer modułów > Konfiguruj (dla TikTok Pixel / Events API)**.
-   **Dostępne działania i ustawienia:** Ten ekran przedstawia wszystkie ogólne i zaawansowane ustawienia opisane w sekcji 4.1, zorganizowane w logiczne zakładki lub sekcje. Zawiera również różne narzędzia diagnostyczne, takie jak Wynik zdrowia, Statystyki na żywo i Radar odzyskiwania.
-   **Efekt zmian:** Wszelkie zmiany zapisane na tym ekranie bezpośrednio wpływają na to, jak Twój TikTok Pixel i Events API działają w Twoim sklepie.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Początkowa konfiguracja:** Skonfiguruj swój ID Piksela, Token dostępu i Tryb śledzenia.
    2.  **Regularne monitorowanie:** Okresowo sprawdzaj zakładki „Wynik zdrowia” i „Statystyki na żywo”, aby zapewnić jakość danych i wyzwalanie zdarzeń.
    3.  **Rozwiązywanie problemów:** Użyj „Trybu debugowania” (tymczasowo) i „Statystyk na żywo”, aby zdiagnozować wszelkie problemy ze śledzeniem.
    4.  **Optymalizacja:** Przejrzyj wnioski z „Radaru odzyskiwania”, aby informować swoje strategie retargetingu.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | ID Piksela TikTok | Twój ID Piksela | Łączy Twój sklep z kontem reklamowym TikTok do śledzenia w przeglądarce. |
| Konfiguracja modułu | Token dostępu TikTok | Twój Token dostępu | Autoryzuje śledzenie po stronie serwera za pośrednictwem Events API. |
| Konfiguracja modułu | Tryb śledzenia | Tryb podwójny | Określa, czy do śledzenia używany jest Piksel, Events API, czy oba. Tryb podwójny jest zalecany dla dokładności. |
| Konfiguracja modułu | Włącz tryb debugowania | Nie (dla produkcji) | Pokazuje szczegółowe dane zdarzeń w konsoli przeglądarki do rozwiązywania problemów. |
| Konfiguracja modułu | Zarządzanie zgodami | Tak (dla RODO/CCPA) | Zapewnia, że śledzenie szanuje zgodę użytkownika na pliki cookie. |
| Konfiguracja modułu | Typ ID produktu | Dopasowany do Twojego katalogu | Wybiera identyfikator produktu wysyłany do TikTok w celu dopasowania katalogu. |
| Konfiguracja modułu | Domeny łączące | Puste (dodaj w razie potrzeby) | Umożliwia śledzenie między domenami dla złożonych struktur witryn. |
| Konfiguracja modułu | Wynik zdrowia | Wysoki wynik | Wskazuje ogólną jakość danych i dokładność śledzenia. |
| Konfiguracja modułu | Radar odzyskiwania | Monitoruj | Wnioski dotyczące porzuconych koszyków do retargetingu. |
| Konfiguracja modułu | Statystyki na żywo | Monitoruj | Widok zdarzeń wysyłanych do TikTok w czasie rzeczywistym. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Zainstalowałem moduł, ale nie widzę żadnych danych w moim TikTok Ads Manager. Co powinienem zrobić?**

-   **O:** Najpierw dokładnie sprawdź, czy Twój **ID Piksela TikTok** i **Token dostępu** są poprawnie wprowadzone w konfiguracji modułu. Upewnij się, że nie ma literówek.
-   Następnie sprawdź, czy Twój **Tryb śledzenia** jest ustawiony na „Tryb podwójny” lub „Piksel” (jeśli używasz tylko Piksela).
-   Włącz **Tryb debugowania** w ustawieniach modułu, a następnie odwiedź front-office swojego sklepu, wykonaj kilka działań (takich jak przeglądanie produktu, dodawanie do koszyka) i sprawdź konsolę programisty swojej przeglądarki (zazwyczaj F12 > zakładka Konsola) pod kątem komunikatów o zdarzeniach TikTok.
-   Na koniec wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**).

**P2: Mój Wynik zdrowia TikTok jest niski. Jak mogę go poprawić?**

-   **O:** Niski Wynik zdrowia często wskazuje na problemy z jakością danych lub dostarczaniem zdarzeń.
-   **Sprawdź brakujące dane:** Upewnij się, że wszystkie wymagane informacje o produkcie (cena, waluta, nazwa) są kompletne dla Twoich produktów.
-   **Zweryfikuj zgodę:** Jeśli masz włączone „Zarządzanie zgodami”, upewnij się, że Twój baner zgody na pliki cookie działa poprawnie i użytkownicy akceptują pliki cookie.
-   **Przejrzyj Statystyki na żywo:** Poszukaj błędów lub brakujących zdarzeń w sekcji „Statystyki na żywo” modułu.
-   Sam moduł często dostarcza konkretnych rekomendacji w sekcji Wynik zdrowia, aby Cię pokierować.

**P3: Czy ten moduł spowolni moją stronę internetową?**

-   **O:** Moduł został zaprojektowany tak, aby był lekki i wydajny. Śledzenie Piksela po stronie przeglądarki może dodać niewielkie, pomijalne obciążenie, podobne do każdego innego skryptu analitycznego. Events API po stronie serwera praktycznie nie ma wpływu na czasy ładowania front-office, ponieważ dane są wysyłane bezpośrednio z Twojego serwera. Zalecamy używanie „Trybu podwójnego” dla optymalnej wydajności i dokładności danych.

**P4: Mam niestandardowy motyw. Czy moduł będzie działał poprawnie?**

-   **O:** Tak, moduł został zaprojektowany tak, aby bezproblemowo integrować się ze standardowymi motywami PrestaShop i większością niestandardowych motywów. Wykorzystuje oficjalny system hooków PrestaShop do wstrzykiwania swoich skryptów i kodu śledzenia.
-   Jeśli napotkasz jakiekolwiek problemy z bardzo spersonalizowanym motywem, zwłaszcza jeśli znacząco zmienia on podstawowe szablony PrestaShop dla stron produktów lub płatności, może być konieczne skonsultowanie się z programistą, aby upewnić się, że hooki są nadal obecne i poprawnie renderowane.

**P5: Jak moduł obsługuje sklepy wielojęzyczne i wielowalutowe?**

-   **O:** Moduł jest w pełni kompatybilny z funkcjami wielojęzyczności i wielowalutowości PrestaShop. Automatycznie wykrywa aktywny język i walutę w front-office i wysyła te informacje do TikTok, zapewniając, że dane zdarzeń są dokładne i zlokalizowane. Nazwy produktów i wartości będą wysyłane w kontekście wybranego przez klienta języka i waluty.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu TikTok Pixel / Events API, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł `mytiktok` jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując wzorzec MVC tam, gdzie jest to stosowne. Działa głównie jako tracker zdarzeń, wstrzykując JavaScript do śledzenia po stronie klienta (Pixel) i wykorzystując logikę po stronie serwera dla Events API. Kluczowe komponenty obejmują:

-   **Główna klasa modułu (`index.php`):** Obsługuje instalację, deinstalację, konfigurację i rejestrację hooków.
-   **Kontrolery:** Kontrolery front-end dla żądań AJAX i kontrolery admin dla zarządzania w panelu administracyjnym.
-   **Klasy podstawowe:** Solidny zestaw klas (`classes/`) do zarządzania komunikacją API, mapowaniem zdarzeń, jakością danych, zgodą i różnymi strategiami śledzenia (Pixel, CAPI, Hybrid).
-   **Szablony:** Szablony Smarty zarówno do wstrzykiwania hooków we front-office, jak i do widoków konfiguracji w panelu administracyjnym.
-   **Zasoby:** Dedykowane pliki JS i CSS dla interfejsów administracyjnych oraz debugowania/śledzenia we front-office.

Moduł implementuje `MytiktokTrackerInterface` i używa `MytiktokTrackerFactory` do abstrakcji różnych trybów śledzenia (Pixel, CAPI, Hybrid), promując czysty i rozszerzalny projekt. Zawiera również zaawansowane narzędzia do monitorowania jakości danych i stanu zdrowia.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `mytiktok/controllers/front/ajax.php`
    *   **Nazwa klasy i klasa nadrzędna:** `MytiktokAjaxModuleFrontController` rozszerza `ModuleFrontController`.
    *   **Odpowiedzialność:** Obsługuje asynchroniczne żądania z front-office, głównie do śledzenia zdarzeń po stronie serwera (Events API) lub zbierania danych, które nie wymagają pełnego przeładowania strony. Może przetwarzać dane przesłane przez JavaScript i przekazywać je do TikTok Events API.
-   `mytiktok/controllers/front/index.php`
    *   **Nazwa klasy i klasa nadrzędna:** `MytiktokIndexModuleFrontController` rozszerza `ModuleFrontController`.
    *   **Odpowiedzialność:** Ten kontroler może służyć jako rezerwowy lub specyficzny punkt końcowy dla niektórych interakcji front-office, chociaż `ajax.php` jest zazwyczaj bardziej aktywny w obsłudze zdarzeń. Może być używany do specyficznych przekierowań lub inicjalizacji, jeśli jest to potrzebne.

#### Kontrolery administracyjne Back-Office

-   `mytiktok/controllers/admin/AdminMytiktokAjaxController.php`
    *   **Nazwa klasy i klasa nadrzędna:** `AdminMytiktokAjaxController` rozszerza `ModuleAdminController`.
    *   **Nazwa zakładki i zarządzana encja:** Ten kontroler nie jest bezpośrednio dostępny jako zakładka menu. Obsługuje żądania AJAX pochodzące z głównej strony konfiguracji modułu (`index.php`) w panelu administracyjnym. Jest odpowiedzialny za dynamiczne aktualizacje, pobieranie statystyk na żywo, wyników zdrowia, logów zdarzeń i innych danych diagnostycznych bez konieczności pełnego odświeżania strony.
-   `mytiktok/controllers/admin/index.php`
    *   **Nazwa klasy i klasa nadrzędna:** `AdminMytiktokController` rozszerza `ModuleAdminController`.
    *   **Nazwa zakładki i zarządzana encja:** To jest główny kontroler administracyjny dla konfiguracji modułu. Jest to kontroler, do którego `index.php` (główny plik modułu) przekierowuje po kliknięciu przycisku „Konfiguruj”. Zarządza wyświetlaniem wszystkich formularzy konfiguracji, zakładek (np. Ustawienia ogólne, Jakość danych, Statystyki na żywo) i obsługuje zapisywanie ustawień modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `mytiktok/classes/autoload.php`: Standardowy plik autoload PrestaShop, zapewniający prawidłowe ładowanie klas modułu.
-   `mytiktok/classes/index.php`: Pusty plik, często używany do zapobiegania listowaniu katalogów.
-   `mytiktok/classes/MytiktokCapiClient.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Obsługuje komunikację z TikTok Events API (CAPI). Zawiera metody do wysyłania danych zdarzeń, zarządzania uwierzytelnianiem za pomocą Tokenu dostępu i obsługi odpowiedzi API.
-   `mytiktok/classes/MytiktokCapiTracker.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Implementuje `MytiktokTrackerInterface`. Odpowiedzialny za przygotowywanie i wysyłanie zdarzeń po stronie serwera do TikTok za pośrednictwem `MytiktokCapiClient`.
-   `mytiktok/classes/MytiktokCatalogDoctor.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Dostarcza narzędzia diagnostyczne i rekomendacje związane z danymi katalogu produktów, zapewniając, że ID produktów i atrybuty są poprawnie sformatowane dla TikTok.
-   `mytiktok/classes/MytiktokConsent.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Zarządza logiką zgody na pliki cookie, integrując się z mechanizmami zgody PrestaShop lub niestandardowymi modułami zgody, aby zapewnić zgodność z RODO/CCPA.
-   `mytiktok/classes/MytiktokCurrencyHelper.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Klasa narzędziowa do obsługi formatowania i konwersji walut, zapewniająca, że wartości zdarzeń są wysyłane do TikTok w prawidłowym formacie i walucie.
-   `mytiktok/classes/MytiktokDataQualityCoach.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Analizuje jakość i kompletność danych wysyłanych do TikTok, dostarczając spostrzeżeń i sugestii dotyczących poprawy.
-   `mytiktok/classes/MytiktokEventId.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Generuje i zarządza unikalnymi wartościami `event_id` dla zdarzeń, kluczowymi dla deduplikacji w śledzeniu w trybie podwójnym.
-   `mytiktok/classes/MytiktokEventMap.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Mapuje działania i dane PrestaShop na standardowe nazwy i właściwości zdarzeń TikTok (np. `ViewContent`, `AddToCart`, `CompletePayment`).
-   `mytiktok/classes/MytiktokEvents.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Centralna klasa do wyzwalania i zarządzania różnymi zdarzeniami TikTok na podstawie działań użytkownika w PrestaShop.
-   `mytiktok/classes/MytiktokHealthScore.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Oblicza i wyświetla ogólny wynik zdrowia integracji TikTok na podstawie jakości danych, dostarczania zdarzeń i konfiguracji.
-   `mytiktok/classes/MytiktokHybridTracker.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Implementuje `MytiktokTrackerInterface`. Koordynuje śledzenie w trybie podwójnym, wysyłając zdarzenia zarówno za pośrednictwem Piksela, jak i CAPI z deduplikacją `event_id`.
-   `mytiktok/classes/MytiktokLiveStats.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Zbieranie i wyświetlanie statystyk w czasie rzeczywistym zdarzeń wysyłanych do TikTok w celach monitorowania.
-   `mytiktok/classes/MytiktokPixelTracker.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Implementuje `MytiktokTrackerInterface`. Odpowiedzialny za wstrzykiwanie i zarządzanie zdarzeniami TikTok Pixel po stronie przeglądarki.
-   `mytiktok/classes/MytiktokProductIdResolver.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Rozwiązuje prawidłowy ID produktu na podstawie konfiguracji modułu (np. ID PrestaShop, EAN13, UPC) do wysyłania do TikTok.
-   `mytiktok/classes/MytiktokPropertyRules.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Definiuje i egzekwuje zasady dla właściwości zdarzeń, zapewniając, że dane wysyłane do TikTok są zgodne z jego specyfikacjami.
-   `mytiktok/classes/MytiktokTrackerFactory.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Wzorzec fabryki do tworzenia instancji odpowiedniej klasy trackera (`MytiktokPixelTracker`, `MytiktokCapiTracker` lub `MytiktokHybridTracker`) na podstawie konfiguracji „Trybu śledzenia” modułu.
-   `mytiktok/classes/MytiktokTrackerInterface.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Definiuje kontrakt dla wszystkich klas trackera, zapewniając spójny interfejs do wysyłania zdarzeń.
-   `mytiktok/classes/MytiktokTrans.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Klasa narzędziowa do obsługi tłumaczeń modułu.
-   `mytiktok/classes/MytiktokUserData.php`:
    *   **Tabela bazy danych:** Brak bezpośrednio.
    *   **Rozszerza ObjectModel:** Nie.
    *   **Kluczowe metody publiczne:** Zbieranie i formatowanie danych użytkownika (np. e-mail, telefon, adres IP) w celu lepszego dopasowania w TikTok Events API.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `mytiktok/views/js/mytiktok-admin.js`:
    *   **Zakres:** Panel administracyjny.
    *   **Opis:** Obsługuje interaktywne elementy i wywołania AJAX w ramach stron administracyjnych modułu. Obejmuje to zarządzanie zakładkami, aktualizowanie statystyk na żywo, obsługę przesyłania formularzy i kroków kreatora.
-   `mytiktok/views/js/mytiktok-debug.js`:
    *   **Zakres:** Front-office (gdy tryb debugowania jest włączony).
    *   **Opis:** Wstrzykuje informacje debugowania do konsoli przeglądarki, logując zdarzenia TikTok, ich właściwości i potencjalne problemy. Niezbędny do weryfikacji prawidłowego wyzwalania zdarzeń.
-   `mytiktok/views/js/mytiktok-ghost.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Potencjalnie obsługuje „duchowe” lub ukryte mechanizmy śledzenia, prawdopodobnie związane z inicjacją zdarzeń po stronie serwera lub specyficznymi interakcjami użytkownika, które muszą być przechwycone bez bezpośredniej interakcji z pikselem.
-   `mytiktok/views/js/mytiktok-live.js`:
    *   **Zakres:** Panel administracyjny.
    *   **Opis:** Zasila funkcję „Statystyki na żywo” w panelu administracyjnym, okresowo pobierając i wyświetlając dane zdarzeń w czasie rzeczywistym.
-   `mytiktok/views/js/mytiktok-tcf.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Integruje się z Transparency and Consent Framework (TCF) lub innymi rozwiązaniami do zarządzania zgodą na pliki cookie, aby zarządzać zgodą użytkownika przed inicjalizacją TikTok Pixel.
-   `mytiktok/views/js/mytiktok-wizard.js`:
    *   **Zakres:** Panel administracyjny.
    *   **Opis:** Zarządza kreatorem konfiguracji krok po kroku dla początkowej konfiguracji modułu, prowadząc sprzedawcę przez niezbędne ustawienia.
-   `mytiktok/views/js/mytiktok.js`:
    *   **Zakres:** Front-office.
    *   **Opis:** Główny plik JavaScript front-office. Inicjalizuje TikTok Pixel, wyzwala standardowe zdarzenia (PageView, ViewContent, AddToCart, InitiateCheckout) i zbiera niezbędne dane z DOM do wysłania do TikTok. Obsługuje również generowanie `event_id` do deduplikacji.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `mytiktok/views/css/mytiktok-admin.css`:
    *   **Zakres:** Stylizacja formularzy administracyjnych w panelu administracyjnym.
    *   **Opis:** Stylizuje stronę konfiguracji modułu, w tym zakładki, pola wprowadzania, przyciski i wyświetlacze diagnostyczne (Wynik zdrowia, Statystyki na żywo itp.), aby zapewnić spójny i przyjazny dla użytkownika interfejs w panelu administracyjnym PrestaShop.
-   `mytiktok/views/css/mytiktok-debug.css`:
    *   **Zakres:** Stylizacja klienta front-office (tylko gdy tryb debugowania jest aktywny).
    *   **Opis:** Zapewnia minimalną stylizację dla wszelkich wizualnych elementów debugowania, które mogą pojawić się w front-office, gdy tryb debugowania jest włączony (np. mała nakładka lub baner wskazujący status debugowania).

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `mytiktok/views/templates/hook/capi-pageview.tpl`:
    *   **Hook:** Potencjalnie `displayHeader` lub `displayBeforeBodyClosingTag`.
    *   **Wyjście:** Renderuje zdarzenie `PageView` po stronie serwera dla Events API. Ten szablon może zawierać ukryte pola lub struktury danych używane przez logikę po stronie serwera do inicjowania zdarzenia CAPI PageView.
-   `mytiktok/views/templates/hook/debug.tpl`:
    *   **Hook:** `displayHeader` lub `displayBeforeBodyClosingTag`.
    *   **Wyjście:** Renderuje mały blok HTML lub tag skryptu do celów debugowania, często zawierający `mytiktok-debug.js` i początkowe dane debugowania.
-   `mytiktok/views/templates/hook/displayOrderConfirmation.tpl`:
    *   **Hook:** `displayOrderConfirmation`.
    *   **Wyjście:** Renderuje dane zdarzenia `CompletePayment`, w tym wartość zamówienia, walutę i szczegóły produktu, które mają być wysłane do TikTok Pixel i/lub Events API po udanym zakupie.
-   `mytiktok/views/templates/hook/ghost.tpl`:
    *   **Hook:** Różne hooki front-office.
    *   **Wyjście:** Renderuje ukryte elementy lub skrypty do śledzenia „duchowego”, potencjalnie związane z wyzwalaczami zdarzeń po stronie serwera lub zaawansowanym zbieraniem danych.
-   `mytiktok/views/templates/hook/header.tpl`:
    *   **Hook:** `displayHeader`.
    *   **Wyjście:** Wstrzykuje główny kod bazowy TikTok Pixel, `mytiktok.js` i początkowe zmienne konfiguracyjne do sekcji `<head>` wszystkich stron front-office. To tutaj Piksel jest inicjalizowany.
-   `mytiktok/views/templates/hook/payment.tpl`:
    *   **Hook:** Potencjalnie `displayPaymentTop` lub `displayPaymentOptions`.
    *   **Wyjście:** Może renderować dane zdarzenia `InitiateCheckout` lub powiązane skrypty, gdy klient osiągnie krok wyboru płatności podczas realizacji zamówienia.
-   `mytiktok/views/templates/hook/product-details.tpl`:
    *   **Hook:** `displayProductAdditionalInfo` lub podobny hook strony produktu.
    *   **Wyjście:** Renderuje dane zdarzenia `ViewContent`, w tym ID produktu, nazwę, cenę i kategorię, dla aktualnie przeglądanego produktu.

#### Szablony administracyjne (`views/templates/admin/`)

-   `mytiktok/views/templates/admin/consent-guide.tpl`: Wyświetla wskazówki dotyczące konfiguracji zgody na pliki cookie.
-   `mytiktok/views/templates/admin/doctor.tpl`: Renderuje interfejs diagnostyczny „Catalog Doctor”.
-   `mytiktok/views/templates/admin/dq.tpl`: Wyświetla informacje i rekomendacje dotyczące jakości danych.
-   `mytiktok/views/templates/admin/health.tpl`: Renderuje pulpit nawigacyjny „Wynik zdrowia”.
-   `mytiktok/views/templates/admin/linker-domains.tpl`: Pole formularza do konfiguracji domen łączących.
-   `mytiktok/views/templates/admin/live-maintain.tpl`: Widok zastępczy lub konserwacyjny dla statystyk na żywo.
-   `mytiktok/views/templates/admin/live.tpl`: Wyświetla pulpit nawigacyjny „Statystyki na żywo”.
-   `mytiktok/views/templates/admin/mode-context.tpl`: Informacje kontekstowe o wybranym trybie śledzenia.
-   `mytiktok/views/templates/admin/mode-note-both.tpl`: Uwaga/wyjaśnienie dla śledzenia w „Trybie podwójnym”.
-   `mytiktok/views/templates/admin/mode-note-capi.tpl`: Uwaga/wyjaśnienie dla śledzenia „Tylko Events API”.
-   `mytiktok/views/templates/admin/mode-note-pixel.tpl`: Uwaga/wyjaśnienie dla śledzenia „Tylko Piksel”.
-   `mytiktok/views/templates/admin/mode-picker.tpl`: Interfejs do wyboru trybu śledzenia (Pixel, CAPI, Dual).
-   `mytiktok/views/templates/admin/properties-list.tpl`: Wyświetla listę właściwości zdarzeń.
-   `mytiktok/views/templates/admin/recent-events.tpl`: Pokazuje dziennik ostatnio wysłanych zdarzeń.
-   `mytiktok/views/templates/admin/tabs.tpl`: Struktura interfejsu z zakładkami na stronie konfiguracji modułu.
-   `mytiktok/views/templates/admin/tag-chips.tpl`: Komponenty wizualne do wyświetlania tagów lub ID.
-   `mytiktok/views/templates/admin/tag-ids.tpl`: Pola wprowadzania dla ID Piksela TikTok i Tokenu dostępu.
-   `mytiktok/views/templates/admin/wizard.tpl`: Interfejs kreatora konfiguracji krok po kroku.

#### Szablony front-office (`views/templates/front/`)

-   Nie ma wymienionych dedykowanych szablonów stron, ponieważ moduł głównie wstrzykuje skrypty i dane za pośrednictwem hooków.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł przechowuje swoje ustawienia konfiguracyjne głównie w tabeli `ps_configuration` PrestaShop.

-   `ps_configuration`: Przechowuje pary klucz-wartość dla ustawień modułu, takie jak `MYTIKTOK_PIXEL_ID`, `MYTIKTOK_ACCESS_TOKEN`, `MYTIKTOK_TRACKING_MODE` itp.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Inicjalizuje podstawowy kod TikTok Pixel, ładuje `mytiktok.js` i ustawia globalne zmienne konfiguracyjne. |
| `displayBeforeBodyClosingTag` | Tuż przed tagiem `</body>`. | Może wstrzykiwać dodatkowe skrypty lub dane, które muszą zostać wykonane po załadowaniu DOM, lub dla zdarzeń CAPI PageView. |
| `displayProductAdditionalInfo` | Na stronie produktu, zazwyczaj w pobliżu szczegółów produktu. | Wyzwala zdarzenie `ViewContent`, przekazując dane specyficzne dla produktu do TikTok. |
| `displayShoppingCartFooter` | Na stronie koszyka, zazwyczaj poniżej podsumowania koszyka. | Wyzwala zdarzenie `AddToCart` (jeśli nie zostało już obsłużone przez AJAX) i potencjalnie `InitiateCheckout`. |
| `displayPaymentTop` | Na górze strony wyboru płatności podczas realizacji zamówienia. | Wyzwala zdarzenie `InitiateCheckout`. |
| `displayOrderConfirmation` | Na stronie potwierdzenia zamówienia po udanym zakupie. | Wyzwala kluczowe zdarzenie `CompletePayment`, wysyłając pełne szczegóły zamówienia (wartość, produkty, waluta) do TikTok. |
| `actionFrontControllerSetMedia` | Gdy kontroler front-end ustawia swoje zasoby multimedialne. | Wstrzykuje pliki JS/CSS specyficzne dla modułu do front-office. |
| `actionAdminControllerSetMedia` | Gdy kontroler admin ustawia swoje zasoby multimedialne. | Wstrzykuje pliki JS/CSS specyficzne dla modułu do panelu administracyjnego. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Wyzwalacz po stronie serwera dla zdarzenia `CompletePayment` za pośrednictwem Events API, zapewniający niezawodne śledzenie konwersji. |
| `actionCartSave` | Gdy koszyk jest aktualizowany (np. dodanie/usunięcie produktu). | Wyzwalacz po stronie serwera dla zdarzeń `AddToCart` lub `RemoveFromCart` za pośrednictwem Events API. |
| `actionProductUpdate` | Gdy produkt jest aktualizowany w panelu administracyjnym. | Potencjalnie używane do synchronizacji katalogu lub kontroli jakości danych. |
| `actionObjectProductAddAfter` | Po dodaniu nowego produktu. | Potencjalnie używane do synchronizacji katalogu lub kontroli jakości danych. |
| `actionObjectProductUpdateAfter` | Po zaktualizowaniu produktu. | Potencjalnie używane do synchronizacji katalogu lub kontroli jakości danych. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „TikTok Pixel / Events API”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz dedykowany zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
