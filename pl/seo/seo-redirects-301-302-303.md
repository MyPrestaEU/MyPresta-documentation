---
title: "Seo Redirects 301, 302, 303 - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracyjny"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów modułu PrestaShop Seo Redirects 301, 302, 303 od MyPresta.eu."
sidebar:
  label: "Seo Redirects 301, 302, 303 - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracyjny"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Seo Redirects 301, 302, 303 na MyPresta.eu](https://mypresta.eu/modules/seo/seo-redirects-301-302-303.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/seo/seo-redirects-301-302-303/)
>
> ---


# Seo Redirects 301, 302, 303

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Seo Redirects 301, 302, 303” oferuje kompleksowy zestaw narzędzi, dostępnych poprzez dedykowane menu w Panelu administracyjnym PrestaShop. Po instalacji znajdziesz nową pozycję menu, zazwyczaj w sekcji **„SEO i SEM”** lub **„Zaawansowane”**, o nazwie **„Seo Redirects”** lub podobnej. To menu będzie zawierać kilka podpunktów, z których każdy prowadzi do konkretnego ekranu konfiguracji.

### 2.1 Główna strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Ten początkowy ekran konfiguracji (dostępny po kliknięciu „Konfiguruj” po instalacji) zawiera ogólne ustawienia modułu.

-   **Co robi to ustawienie:** Ten ekran zazwyczaj zawiera podstawową aktywację modułu i być może niektóre ustawienia globalne.
-   **Wpływ zmiany tego ustawienia:**
    -   *Włączenie modułu:* Aktywuje logikę przekierowań w całym sklepie.
    -   *Wyłączenie modułu:* Zatrzymuje wszystkie przekierowania zarządzane przez ten moduł.
-   **Zalecana wartość:** **Włączony**, aby moduł działał.
-   **Scenariusz sprzedawcy / przykład:** Po instalacji będziesz chciał upewnić się, że moduł jest aktywny, aby mógł rozpocząć zarządzanie Twoimi przekierowaniami.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł organizuje swoje potężne funkcje w kilka odrębnych sekcji, z których każda jest zarządzana przez dedykowany kontroler administracyjny. Znajdziesz je w głównym menu „Seo Redirects” w Panelu administracyjnym PrestaShop.

#### 2.2.1 Pulpit (AdminSeoRedirectDashboardController)

**Nazwa ekranu i lokalizacja w menu:** **Seo Redirects > Pulpit**
Ten ekran przedstawia przegląd wydajności i statusu Twoich przekierowań. To Twoje centralne centrum do szybkiego zrozumienia, jak działają Twoje przekierowania.

-   **Dostępne akcje i ustawienia:**
    -   **Przegląd przekierowań:** Pokazuje statystyki, takie jak całkowita liczba aktywnych przekierowań, utworzonych przekierowań i być może liczba razy, gdy przekierowania zostały uruchomione.
    -   **Historia/Aktywność przekierowań:** Może wyświetlać ostatnie próby przekierowań, w tym wykryte błędy 404 i pomyślnie przekierowane adresy URL.
    -   **SEOR\_DASHBOARD\_PERIOD:** To ustawienie prawdopodobnie kontroluje okres, dla którego wyświetlane są statystyki pulpitu (np. ostatnie 7 dni, ostatnie 30 dni, cały czas).
-   **Wpływ zmian:** Zmiana okresu pulpitu zaktualizuje wyświetlane statystyki, aby odzwierciedlić wybrany przedział czasowy, pomagając analizować trendy w różnych okresach.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie sprawdzaj ten pulpit, aby monitorować stan swoich przekierowań, identyfikować wszelkie nowe błędy 404, które wymagają uwagi, i upewnić się, że Twoje wysiłki SEO przynoszą rezultaty.

#### 2.2.2 Lista przekierowań (AdminSeoRedirectListController)

**Nazwa ekranu i lokalizacja w menu:** **Seo Redirects > Lista przekierowań**
To jest rdzeń modułu, gdzie tworzysz, edytujesz i zarządzasz indywidualnymi regułami przekierowań.

-   **Dostępne akcje i ustawienia:**
    -   **Dodaj nowe przekierowanie:** Formularz do tworzenia nowej reguły przekierowania.
        -   **Stary URL (URL źródłowy):** Dokładny URL, który nie jest już ważny lub z którego chcesz przekierować.
        -   **Nowy URL (URL docelowy):** Dokładny URL, na który powinni zostać wysłani odwiedzający i wyszukiwarki.
        -   **Typ przekierowania:**
            -   **301 Przekierowanie stałe:** Informuje wyszukiwarki, że strona została przeniesiona na stałe. Jest to najczęstszy i najbardziej przyjazny dla SEO typ, przekazujący prawie całą „wartość linku”. Użyj tego, gdy strona zniknęła na zawsze i została zastąpiona inną.
            -   **302 Znaleziono / Przekierowanie tymczasowe:** Informuje wyszukiwarki, że przeniesienie jest tymczasowe. Użyj tego, jeśli spodziewasz się, że stary URL ponownie stanie się aktywny w przyszłości (np. dla produktów sezonowych, testów A/B). Przekazywana jest mniejsza wartość SEO.
            -   **303 Zobacz inne:** Podobne do 302, często używane po żądaniu POST do przekierowania na nową stronę, aby zapobiec ponownemu przesłaniu. Mniej powszechne dla ogólnych przekierowań SEO.
        -   **Status (Włączony/Wyłączony):** Pozwala aktywować lub dezaktywować konkretną regułę przekierowania bez jej usuwania.
    -   **Edytuj/Usuń przekierowania:** Modyfikuj istniejące reguły lub usuwaj je.
    -   **Szukaj/Filtruj:** Znajdź konkretne przekierowania według starego lub nowego URL.
    -   **Akcje zbiorcze:** Zastosuj akcje (włącz, wyłącz, usuń) do wielu wybranych przekierowań.
-   **Wpływ zmian:**
    -   *Dodanie przekierowania:* Natychmiast rozpoczyna przekierowywanie ruchu ze starego URL na nowy zgodnie z określonym typem.
    -   *Edycja przekierowania:* Aktualizuje zachowanie przekierowania.
    -   *Usunięcie przekierowania:* Usuwa regułę, potencjalnie prowadząc do błędów 404, jeśli stary URL jest nadal dostępny.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Za każdym razem, gdy usuwasz produkt, zmieniasz URL kategorii lub aktualizujesz adres strony, natychmiast utwórz przekierowanie 301 ze starego URL na nowy.
    2.  Regularnie sprawdzaj swoje logi błędów 404 (np. w Google Search Console lub sekcji Audyt modułu) i dodawaj przekierowania dla często napotykanych uszkodzonych linków.

#### 2.2.3 Import przekierowań (AdminSeoRedirectImportController)

**Nazwa ekranu i lokalizacja w menu:** **Seo Redirects > Import**
Ten ekran pozwala przesłać plik (zazwyczaj CSV) zawierający wiele reguł przekierowań, co ułatwia zarządzanie dużą liczbą przekierowań.

-   **Dostępne akcje i ustawienia:**
    -   **Prześlij plik CSV:** Wybierz plik z komputera. Plik powinien zawierać kolumny dla „Starego URL”, „Nowego URL” i „Typu przekierowania”.
    -   **IV\_COL\_DELIMITER:** To ustawienie definiuje znak używany do oddzielania kolumn w pliku CSV (np. przecinek, średnik, tabulator).
    -   **SEOR\_SAFE\_ROLLOUT:** To ustawienie prawdopodobnie kontroluje „tryb bezpieczny” dla importów, być może pozwalając na podgląd zmian lub stopniowe włączanie przekierowań, aby zapobiec przypadkowym problemom.
-   **Wpływ zmian:**
    -   *Importowanie pliku:* Tworzy wiele reguł przekierowań zbiorczo, oszczędzając znaczący wysiłek ręczny.
    -   *Zmiana separatora:* Zapewnia, że moduł poprawnie analizuje Twój plik CSV.
    -   *Bezpieczne wdrożenie:* Jeśli włączone, może pozwolić na etapowe wdrażanie przekierowań, dając czas na weryfikację przed ich uruchomieniem.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj tej funkcji podczas migracji sklepu, przeprowadzania dużej restrukturyzacji witryny lub czyszczenia dużej liczby nagromadzonych błędów 404. Zawsze najpierw przetestuj małą partię, jeśli to możliwe.

#### 2.2.4 Audyt (AdminSeoRedirectAuditController)

**Nazwa ekranu i lokalizacja w menu:** **Seo Redirects > Audyt**
Narzędzie audytu pomaga identyfikować uszkodzone linki (błędy 404) na Twojej stronie internetowej, które są głównymi kandydatami do przekierowania.

-   **Dostępne akcje i ustawienia:**
    -   **Skanuj w poszukiwaniu błędów 404:** Inicjuje skanowanie Twojej witryny (lub jej konkretnej części) w celu znalezienia stron, które zwracają status 404.
    -   **Lista błędów 404:** Wyświetla tabelę wykrytych uszkodzonych linków, często z odsyłającą stroną (gdzie znaleziono uszkodzony link) i liczbą razy, gdy została ona odwiedzona.
    -   **Opcja Utwórz przekierowanie:** Bezpośrednio utwórz regułę przekierowania dla wykrytego błędu 404 z tego ekranu.
-   **Wpływ zmian:** Przeprowadzenie audytu pomaga proaktywnie znajdować i naprawiać problemy, które szkodzą SEO i doświadczeniu użytkownika.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Przeprowadzaj audyt okresowo (np. co miesiąc), aby wychwycić nowe uszkodzone linki, które mogą pojawić się z powodu zmian treści lub linków zewnętrznych. Priorytetowo naprawiaj błędy 404, które są często odwiedzane lub linkowane z ważnych stron.

#### 2.2.5 Historia (AdminSeoRedirectHistoryController)

**Nazwa ekranu i lokalizacja w menu:** **Seo Redirects > Historia**
Ten ekran rejestruje wszystkie zdarzenia przekierowań, zapewniając jasny zapis, kiedy i jak przekierowania są używane.

-   **Dostępne akcje i ustawienia:**
    -   **Tabela zdarzeń przekierowań:** Pokazuje szczegóły, takie jak oryginalny żądany URL, nowy URL, na który został przekierowany, typ przekierowania, data/godzina i potencjalnie agent użytkownika lub adres IP.
    -   **Szukaj/Filtruj:** Pomaga znaleźć konkretne zdarzenia przekierowań.
-   **Wpływ zmian:** Jest to narzędzie do raportowania i diagnostyki. Nie zmienia zachowania sklepu, ale dostarcza cennych informacji o tym, jak działają Twoje przekierowania.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj historii, aby zweryfikować, czy konkretne przekierowania działają zgodnie z oczekiwaniami, rozwiązać nieoczekiwane pętle przekierowań lub analizować wzorce ruchu na przekierowane strony.

#### 2.2.6 Ustawienia (AdminSeoRedirectSettingsController)

**Nazwa ekranu i lokalizacja w menu:** **Seo Redirects > Ustawienia**
Ta sekcja zawiera zaawansowane opcje konfiguracji, które kontrolują globalne zachowanie modułu.

-   **Dostępne akcje i ustawienia:**
    -   **seor\_pos\_exclude:**
        -   **Co robi to ustawienie:** Pozwala wykluczyć określone adresy URL lub wzorce z automatycznego przekierowywania lub audytu. Jest to przydatne dla stron, które celowo mają zwracać błąd 404 (np. stare strony testowe).
        -   **Wpływ zmiany tego ustawienia:**
            -   *Dodawanie adresów URL:* Moduł zignoruje te adresy URL podczas wykonywania przekierowań lub audytów.
            -   *Usuwanie adresów URL:* Te adresy URL będą podlegać logice przekierowań modułu.
        -   **Zalecana wartość:** Utrzymuj tę listę aktualną z wszelkimi adresami URL, które powinny być prawdziwymi błędami 404 i nie powinny być przekierowywane.
        -   **Scenariusz sprzedawcy / przykład:** Możesz mieć tymczasową stronę docelową, którą chcesz całkowicie usunąć, i nie chcesz, aby moduł próbował ją przekierować.
    -   **seor\_unavorder:**
        -   **Co robi to ustawienie:** Prawdopodobnie kontroluje, jak moduł obsługuje przekierowania dla niedostępnych produktów lub produktów wyczerpanych.
        -   **Wpływ zmiany tego ustawienia:**
            -   *Włączone:* Moduł może automatycznie przekierowywać strony niedostępnych produktów na stronę kategorii lub niestandardową stronę „produkt nie znaleziony”.
            -   *Wyłączone:* Strony niedostępnych produktów zwrócą standardowy błąd 404.
        -   **Zalecana wartość:** **Włączone**, aby poprawić doświadczenie użytkownika i SEO dla wycofanych produktów.
        -   **Scenariusz sprzedawcy / przykład:** Gdy produkt zostanie usunięty z Twojego katalogu, możesz automatycznie przekierować jego stary URL na jego kategorię nadrzędną lub podobny produkt, zamiast wyświetlać błąd 404.
    -   **seor\_pos\_category, seor\_pins\_category, seor\_pos\_exclude\_cat, seor\_oos\_cat\_include, seor\_emptycat\_exclusions, seor\_pos, seor\_emptycat:**
        -   **Co robią te ustawienia:** Jest to prawdopodobnie grupa ustawień związanych z tym, jak moduł obsługuje przekierowania dla kategorii, zwłaszcza pustych kategorii, produktów wyczerpanych w kategoriach lub konkretnych wykluczeń kategorii.
            -   `seor_pos_category`: Ogólne ustawienie dla przekierowań kategorii.
            -   `seor_pins_category`: Może dotyczyć „przypiętych” kategorii lub specyficznego zachowania przekierowań kategorii.
            -   `seor_pos_exclude_cat`: Wyklucza konkretne kategorie z automatycznej logiki przekierowań.
            -   `seor_oos_cat_include`: Uwzględnia produkty wyczerpane w logice przekierowań kategorii.
            -   `seor_emptycat_exclusions`: Wyklucza konkretne puste kategorie z przekierowywania.
            -   `seor_pos`: Ogólne ustawienie dla przekierowań pozycji produktu/kategorii.
            -   `seor_emptycat`: Kontroluje automatyczne przekierowania dla pustych kategorii.
        -   **Wpływ zmiany tych ustawień:** Te ustawienia pozwalają na precyzyjną kontrolę nad tym, jak zarządzane są adresy URL kategorii, gdy kategorie są puste, produkty są wyczerpane lub kategorie są usuwane. Mogą zapobiegać błędom 404 dla dynamicznej treści.
        -   **Zalecana wartość:** Przejrzyj je w oparciu o specyficzne potrzeby Twojego sklepu. Na przykład, automatyczne przekierowywanie pustych kategorii do ich nadrzędnej może być korzystne.
        -   **Scenariusz sprzedawcy / przykład:** Jeśli kategoria staje się pusta, ponieważ wszystkie produkty zostały wyprzedane, możesz chcieć automatycznie przekierować jej URL do kategorii nadrzędnej, aby uniknąć błędu 404.

#### 2.2.7 Narzędzia (AdminSeoRedirectToolsController)

**Nazwa ekranu i lokalizacja w menu:** **Seo Redirects > Narzędzia**
Ta sekcja zawiera funkcje narzędziowe, potencjalnie obejmujące integrację z usługami zewnętrznymi.

-   **Dostępne akcje i ustawienia:**
    -   **SEOR\_GSC\_TOKEN, SEOR\_GSC\_SITE:** Te ustawienia sugerują integrację z Google Search Console (GSC).
        -   **Co robią te ustawienia:** Pozwalają połączyć Twój sklep PrestaShop z kontem Google Search Console. Może to umożliwić modułowi automatyczne pobieranie błędów 404 zgłaszanych przez Google lub przesyłanie map witryn/przekierowań do GSC.
        -   **Wpływ zmiany tego ustawienia:**
            -   *Konfiguracja GSC:* Umożliwia wymianę danych między Twoim sklepem a Google Search Console, potencjalnie automatyzując wykrywanie uszkodzonych linków i poprawiając Twój przepływ pracy SEO.
            -   *Brak konfiguracji:* Będziesz musiał ręcznie sprawdzać GSC pod kątem błędów 404 i dodawać przekierowania.
        -   **Zalecana wartość:** Skonfiguruj, jeśli aktywnie używasz Google Search Console do SEO swojego sklepu.
        -   **Scenariusz sprzedawcy / przykład:** Zamiast ręcznie sprawdzać Google Search Console pod kątem nowych błędów 404, moduł mógłby je pobierać bezpośrednio, co pozwoliłoby szybciej tworzyć przekierowania.

#### 2.2.8 Statystyki (AdminSeoRedirectStatsController)

**Nazwa ekranu i lokalizacja w menu:** **Seo Redirects > Statystyki**
Ten ekran dostarcza statystyk związanych z ogólnym stanem Twojego sklepu, potencjalnie obejmując wpływ przekierowań.

-   **Dostępne akcje i ustawienia:**
    -   **PS\_SHOP\_ENABLE:** Jest to standardowy klucz konfiguracji PrestaShop, który wskazuje, czy Twój sklep jest aktualnie włączony, czy w trybie konserwacji. Moduł może wyświetlać to jako szybkie sprawdzenie statusu.
    -   **Metryki wydajności przekierowań:** Może pokazywać zagregowane dane o tym, ile przekierowań miało miejsce, które typy są najczęstsze i ich ogólny wpływ.
-   **Wpływ zmian:** Jest to przede wszystkim ekran informacyjny. Pomaga zrozumieć ogólną wydajność i wykorzystanie modułu.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Okresowo przeglądaj te statystyki, aby zrozumieć wolumen przekierowań i upewnić się, że moduł aktywnie przyczynia się do zdrowej witryny.

#### 2.2.9 Kontroler API (AdminSeoRedirectApiController)

**Nazwa ekranu i lokalizacja w menu:** **Seo Redirects > API** (lub podobne, może być sekcja techniczna)
Ten ekran jest przeznaczony dla zaawansowanych użytkowników lub programistów, którzy chcą programowo wchodzić w interakcje z funkcjonalnością przekierowań modułu.

-   **Dostępne akcje i ustawienia:**
    -   **Dokumentacja API:** Dostarcza informacji o tym, jak używać API modułu do tworzenia, pobierania, aktualizowania lub usuwania przekierowań z zewnętrznych aplikacji lub niestandardowych skryptów.
    -   **Zarządzanie kluczami API:** Pozwala generować i zarządzać kluczami API dla bezpiecznego dostępu.
-   **Wpływ zmian:** Konfiguracja dostępu do API pozwala systemom zewnętrznym (np. niestandardowemu systemowi zarządzania zapasami, narzędziu SEO innej firmy) na interakcję z Twoimi przekierowaniami.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Używaj tego tylko, jeśli masz specyficzne potrzeby integracyjne i wiedzę techniczną.

#### 2.2.10 Kontroler CLI (AdminSeoRedirectCliController)

**Nazwa ekranu i lokalizacja w menu:** **Seo Redirects > CLI** (lub podobne, może być sekcja techniczna)
Ten ekran dostarcza informacji i narzędzi do operacji interfejsu wiersza poleceń (CLI) związanych z modułem.

-   **Dostępne akcje i ustawienia:**
    -   **Dokumentacja poleceń CLI:** Wyjaśnia, jak uruchamiać zadania specyficzne dla modułu z wiersza poleceń serwera (np. `php bin/console seoredirect:audit`).
    -   **Konfiguracja zadań Cron:** Dostarcza instrukcji dotyczących konfiguracji zadań cron w celu automatyzacji zadań, takich jak regularne audyty lub czyszczenie przekierowań.
-   **Wpływ zmian:** Używanie narzędzi CLI pozwala na automatyzację zadań, co jest szczególnie przydatne dla dużych sklepów lub złożonych operacji.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Skonsultuj tę sekcję, jeśli chcesz zautomatyzować zadania, takie jak codzienne audyty 404 lub okresowe sprawdzanie stanu przekierowań za pomocą zadań cron serwera.

#### 2.2.11 Kontroler wyszukiwania (AdminSeoredirectSearchController)

**Nazwa ekranu i lokalizacja w menu:** **Seo Redirects > Szukaj** (lub zintegrowane z innymi ekranami)
Ten kontroler prawdopodobnie obsługuje zaawansowane funkcje wyszukiwania w różnych siatkach i listach modułu, pomagając szybko znaleźć konkretne przekierowania, błędy 404 lub wpisy historii.

-   **Dostępne akcje i ustawienia:**
    -   **Zaawansowane filtry wyszukiwania:** Zapewnia bardziej szczegółowe opcje wyszukiwania poza prostym wyszukiwaniem tekstowym, być może obejmujące zakresy dat, typy przekierowań lub status.
-   **Wpływ zmian:** Poprawia Twoją zdolność do nawigacji i zarządzania dużymi zbiorami danych w module.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj tego, gdy musisz szybko zlokalizować konkretną regułę przekierowania lub przeanalizować podzbiór swoich danych.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Pulpit** | `SEOR_DASHBOARD_PERIOD` | Ostatnie 30 dni | Kontroluje okres dla statystyk pulpitu. |
| **Lista przekierowań** | Stary URL | N/A | URL, z którego ma nastąpić przekierowanie. |
| | Nowy URL | N/A | URL, na który ma nastąpić przekierowanie. |
| | Typ przekierowania | 301 Stałe | Typ przekierowania (301, 302, 303). 301 jest najlepsze dla SEO. |
| | Status | Włączony | Aktywuje/dezaktywuje konkretną regułę przekierowania. |
| **Import** | `IV_COL_DELIMITER` | Przecinek (`,`) | Znak oddzielający kolumny w pliku importu CSV. |
| | `SEOR_SAFE_ROLLOUT` | Nie | Włącza tryb bezpieczny dla importów (np. etapowe wdrożenie). |
| **Ustawienia** | `seor_pos_exclude` | Puste | Lista adresów URL/wzorców do wykluczenia z przekierowania/audytu. |
| | `seor_unavorder` | Tak | Automatycznie przekierowuje niedostępne produkty. |
| | `seor_pos_category` | Tak | Ogólne ustawienie dla przekierowań kategorii. |
| | `seor_pins_category` | Nie | Specyficzne zachowanie przekierowań kategorii. |
| | `seor_pos_exclude_cat` | Puste | Wyklucza konkretne kategorie z automatycznego przekierowania. |
| | `seor_oos_cat_include` | Tak | Uwzględnia produkty wyczerpane w logice przekierowań kategorii. |
| | `seor_emptycat_exclusions` | Puste | Wyklucza konkretne puste kategorie z przekierowywania. |
| | `seor_pos` | Tak | Ogólne ustawienie dla przekierowań pozycji produktu/kategorii. |
| | `seor_emptycat` | Tak | Kontroluje automatyczne przekierowania dla pustych kategorii. |
| **Narzędzia** | `SEOR_GSC_TOKEN` | Puste | Token API Google Search Console do integracji. |
| | `SEOR_GSC_SITE` | Puste | Adres URL Twojej witryny zarejestrowany w Google Search Console. |
| **Statystyki** | `PS_SHOP_ENABLE` | Tak | Wyświetla aktualny status sklepu (włączony/konserwacja). |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Dodałem przekierowanie, ale nie działa. Co powinienem zrobić?**
O1:

-   **Sprawdź błędy typograficzne:** Upewnij się, że „Stary URL” i „Nowy URL” są wpisane dokładnie poprawnie na Liście przekierowań.
-   **Wyczyść pamięć podręczną:** PrestaShop używa pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Wyczyść również pamięć podręczną przeglądarki.
-   **Status modułu:** Upewnij się, że moduł „Seo Redirects 301, 302, 303” jest włączony w **Moduły > Menedżer modułów**.
-   **Kolejność przekierowań:** Jeśli masz wiele modułów przekierowań lub reguł `.htaccess`, może wystąpić konflikt. Ten moduł zazwyczaj ma pierwszeństwo, ale sprawdź plik `.htaccess` swojego serwera pod kątem wszelkich sprzecznych reguł.
-   **Pełny URL vs. względny URL:** Upewnij się, że używasz prawidłowego formatu dla swoich adresów URL (np. `/old-page.html` dla ścieżek względnych lub `https://www.yourstore.com/old-page.html` dla pełnych ścieżek, w zależności od tego, jak moduł ich oczekuje).

**P2: Czy ten moduł spowolni mój sklep?**
O2: Moduł został zaprojektowany tak, aby był wydajny. Przekierowania odbywają się na bardzo wczesnym etapie procesu żądania, minimalizując wpływ. Jednak posiadanie dziesiątek tysięcy przekierowań może dodać niewielki narzut. Regularne audytowanie i usuwanie niepotrzebnych przekierowań (np. starych tymczasowych 302) może pomóc w utrzymaniu wydajności.

**P3: Jak obsługiwać przekierowania dla produktów, które są tymczasowo niedostępne?**
O3:

-   W sytuacjach tymczasowych odpowiednie jest **302 tymczasowe przekierowanie** na odpowiednią stronę kategorii lub stronę „powiadom mnie, gdy będzie dostępne”. Informuje to wyszukiwarki, że produkt może powrócić.
-   Sprawdź ekran **Ustawienia** pod kątem opcji takich jak `seor_unavorder` lub `seor_oos_cat_include`, które mogą oferować automatyczną obsługę produktów wyczerpanych.

**P4: Czy mogę używać symboli wieloznacznych w moich regułach przekierowań (np. przekierowywanie wszystkich stron w starym katalogu)?**
O4: Dokumentacja lub interfejs modułu określi, czy obsługuje on wyrażenia regularne lub symbole wieloznaczne (takie jak `*`). Jeśli tak, możesz tworzyć potężne reguły, takie jak `/old-category/*` do `/new-category/$1` (gdzie `$1` przechwytuje resztę URL). Jeśli nie, będziesz musiał wymienić każde przekierowanie indywidualnie lub użyć funkcji importu. Zawsze ostrożnie testuj przekierowania z symbolami wieloznacznymi!

**P5: Mój niestandardowy motyw nie wyświetla poprawnie funkcji modułu (np. w modalnym oknie audytu).**
O5: Interfejsy panelu administracyjnego modułu są zazwyczaj niezależne od Twojego motywu front-office. Jeśli doświadczasz problemów z wyświetlaniem w panelu administracyjnym, może to być konflikt z innym modułem administracyjnym lub modyfikacją pliku rdzenia PrestaShop.

-   **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i wyczyść pamięć podręczną.
-   **Sprawdź konsolę przeglądarki:** Otwórz narzędzia deweloperskie przeglądarki (F12) i poszukaj błędów JavaScript lub ostrzeżeń CSS w zakładce Konsola, gdy jesteś na stronach konfiguracji modułu. Może to dać wskazówki dotyczące konfliktów.
-   **Skontaktuj się z pomocą techniczną:** Jeśli problem będzie się utrzymywał, dostarcz zrzuty ekranu i wszelkie błędy konsoli do wsparcia MyPresta.eu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Seo Redirects 301, 302, 303” jest zbudowany zgodnie z wzorcem MVC (Model-View-Controller) PrestaShop, z silnym naciskiem na kontrolę administracyjną i zarządzanie danymi. Wykorzystuje `ModuleAdminController` dla swojego rozbudowanego interfejsu panelu administracyjnego, `ObjectModel` do zarządzania danymi przekierowań oraz nadpisuje `FrontController` w celu wczesnego przechwytywania żądań i stosowania logiki przekierowań. Moduł zawiera również kontrolery API i CLI do programowego i zautomatyzowanego zarządzania.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front Office

Te kontrolery obsługują żądania po stronie klienta sklepu.

-   `seoredirect/controllers/front/api.php`
    -   **Nazwa klasy i klasa nadrzędna:** `SeoredirectApiModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler prawdopodobnie służy jako punkt końcowy API front-office, potencjalnie dla usług zewnętrznych do zapytań o status przekierowania lub dla wewnętrznych wywołań AJAX związanych z logiką przekierowania front-office (chociaż większość przekierowań jest obsługiwana poprzez nadpisanie `FrontController`). Odpowiadałby na specyficzne trasy zdefiniowane przez moduł.
-   `seoredirect/controllers/front/cronjob.php`
    -   **Nazwa klasy i klasa nadrzędna:** `SeoredirectCronjobModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Zapewnia dostępny z front-office punkt końcowy do uruchamiania zadań cron. Pozwala to na wyzwalanie funkcji modułu, takich jak audytowanie, czyszczenie lub synchronizacja danych, za pomocą zadań cron po stronie serwera (np. polecenia `wget` lub `curl`) bez konieczności uwierzytelniania w panelu administracyjnym.
-   `seoredirect/controllers/front/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `SeoredirectIndexModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Zastępczy lub domyślny kontroler front-office. W wielu modułach może on obsługiwać prostą domyślną trasę lub służyć jako podstawa dla innych kontrolerów front-office. Biorąc pod uwagę charakter modułu, jego główna logika front-office prawdopodobnie znajduje się w nadpisaniu `FrontController`.

#### Kontrolery administracyjne Back Office

Te kontrolery zarządzają interfejsem i danymi modułu w Panelu administracyjnym PrestaShop.

-   `seoredirect/controllers/admin/AdminSeoRedirectApiController.php`
    -   **Nazwa zakładki i zarządzana encja:** „API” (lub podobna, w menu Seo Redirects). Zarządza kluczami API i dostarcza dokumentację API.
    -   **Odpowiedzialność:** Obsługuje wyświetlanie i zarządzanie poświadczeniami API oraz dokumentacją do programowej interakcji z modułem.
-   `seoredirect/controllers/admin/AdminSeoRedirectAuditController.php`
    -   **Nazwa zakładki i zarządzana encja:** „Audyt” (w menu Seo Redirects). Zarządza procesem audytu błędów 404.
    -   **Odpowiedzialność:** Zapewnia interfejs do skanowania sklepu w poszukiwaniu błędów 404, wyświetlania wyników i oferowania opcji tworzenia przekierowań z wykrytych uszkodzonych linków.
-   `seoredirect/controllers/admin/AdminSeoRedirectCliController.php`
    -   **Nazwa zakładki i zarządzana encja:** „CLI” (lub podobna, w menu Seo Redirects). Dostarcza dokumentację poleceń CLI.
    -   **Odpowiedzialność:** Wyświetla informacje i instrukcje dotyczące korzystania z narzędzi interfejsu wiersza poleceń modułu, przydatnych do automatyzacji i zaawansowanych zadań.
-   `seoredirect/controllers/admin/AdminSeoRedirectDashboardController.php`
    -   **Nazwa zakładki i zarządzana encja:** „Pulpit” (w menu Seo Redirects). Wyświetla statystyki i przegląd modułu.
    -   **Odpowiedzialność:** Przedstawia kluczowe metryki i przegląd aktywności przekierowań, potencjalnie obejmując wykresy i grafiki. Zarządza konfiguracją `SEOR_DASHBOARD_PERIOD`.
-   `seoredirect/controllers/admin/AdminSeoRedirectHistoryController.php`
    -   **Nazwa zakładki i zarządzana encja:** „Historia” (w menu Seo Redirects). Zarządza rekordami `seor_history`.
    -   **Odpowiedzialność:** Wyświetla dziennik wszystkich zdarzeń przekierowań, w tym źródło, cel, typ i znacznik czasu.
-   `seoredirect/controllers/admin/AdminSeoRedirectImport.php`
    -   **Nazwa zakładki i zarządzana encja:** „Import” (w menu Seo Redirects). Zarządza masowym importem przekierowań.
    -   **Odpowiedzialność:** Zapewnia interfejs do przesyłania plików CSV w celu tworzenia wielu reguł przekierowań. Zarządza konfiguracjami `IV_COL_DELIMITER` i `SEOR_SAFE_ROLLOUT`.
-   `seoredirect/controllers/admin/AdminSeoRedirectListController.php`
    -   **Nazwa zakładki i zarządzana encja:** „Lista przekierowań” (w menu Seo Redirects). Zarządza rekordami `seor` (przekierowań).
    -   **Odpowiedzialność:** Główny interfejs do dodawania, edytowania, usuwania i listowania indywidualnych reguł przekierowań 301, 302, 303.
-   `seoredirect/controllers/admin/AdminSeoredirectSearchController.php`
    -   **Nazwa zakładki i zarządzana encja:** „Szukaj” (lub zintegrowane). Obsługuje funkcjonalność wyszukiwania.
    -   **Odpowiedzialność:** Prawdopodobnie zapewnia zaawansowane możliwości wyszukiwania i filtrowania używane w różnych siatkach administracyjnych w module.
-   `seoredirect/controllers/admin/AdminSeoRedirectSettings.php`
    -   **Nazwa zakładki i zarządzana encja:** „Ustawienia” (w menu Seo Redirects). Zarządza ustawieniami `ps_configuration` związanymi z modułem.
    -   **Odpowiedzialność:** Zapewnia interfejs do konfigurowania globalnego zachowania modułu, takiego jak wykluczenia, automatyczne przekierowania dla niedostępnych produktów/pustych kategorii i inne zaawansowane opcje. Zarządza `seor_pos_exclude`, `seor_unavorder`, `seor_pos_category`, `seor_pins_category`, `seor_pos_exclude_cat`, `seor_oos_cat_include`, `seor_emptycat_exclusions`, `seor_pos`, `seor_emptycat`.
-   `seoredirect/controllers/admin/AdminSeoRedirectStats.php`
    -   **Nazwa zakładki i zarządzana encja:** „Statystyki” (w menu Seo Redirects). Wyświetla ogólne statystyki sklepu i modułu.
    -   **Odpowiedzialność:** Zapewnia przegląd statusu sklepu (`PS_SHOP_ENABLE`) i potencjalnie zagregowane dane dotyczące wydajności przekierowań.
-   `seoredirect/controllers/admin/AdminSeoRedirectToolsController.php`
    -   **Nazwa zakładki i zarządzana encja:** „Narzędzia” (w menu Seo Redirects). Zapewnia funkcje narzędziowe.
    -   **Odpowiedzialność:** Zawiera narzędzia takie jak integracja z Google Search Console (`SEOR_GSC_TOKEN`, `SEOR_GSC_SITE`) i inne funkcje narzędziowe.
-   `seoredirect/controllers/admin/index.php`
    -   **Nazwa zakładki i zarządzana encja:** Nie jest to bezpośredni kontroler, zazwyczaj pusty plik lub środek bezpieczeństwa zapobiegający listowaniu katalogów.

### 4.3 Klasy rdzenia i modele (`classes/`)

-   `seoredirect/override/classes/controller/FrontController.php`
    -   **Co robi:** Jest to krytyczne nadpisanie. Rozszerza podstawową klasę `FrontController` PrestaShop.
    -   **Kluczowe metody publiczne i logika biznesowa:** Nadpisanie prawdopodobnie przechwytuje metodę `init()` lub `postProcess()` klasy `FrontController`. Zanim PrestaShop przekaże żądanie do konkretnego kontrolera strony, to nadpisanie sprawdza żądany URL pod kątem reguł przekierowań przechowywanych w module. Jeśli znaleziono dopasowanie, wysyła odpowiedni nagłówek HTTP przekierowania 301, 302 lub 303 i kończy żądanie, zapobiegając błędowi 404 i wysyłając użytkownika na nowy URL. To tutaj znajduje się podstawowa logika przekierowań.
-   `seoredirect/override/classes/controller/index.php`
    -   **Co robi:** Plik zastępczy, zazwyczaj dla bezpieczeństwa.
-   `seoredirect/override/classes/index.php`
    -   **Co robi:** Plik zastępczy, zazwyczaj dla bezpieczeństwa.

*(Uwaga: Dokumentacja modułu nie wymieniała jawnie niestandardowych klas `ObjectModel`, takich jak `SeoRedirect` lub `SeoRedirectHistory`. Jednak biorąc pod uwagę obecność `AdminSeoRedirectListController` zarządzającego `seor` i `AdminSeoRedirectHistoryController` zarządzającego `seor_history`, jest bardzo prawdopodobne, że istnieją odpowiadające im klasy `SeoRedirect` i `SeoRedirectHistory` (lub podobne nazwy) rozszerzające `ObjectModel` w głównym katalogu modułu lub podkatalogu `classes/` nie wymienionym jawnie w spisie. Definiowałyby one schemat bazy danych dla przekierowań i wpisów historii.)*

### 4.4 Zasoby JavaScript (`views/js/`)

-   `seoredirect/examples/console-mock-dashboard-audit.js`
    -   **Zakres:** Prawdopodobnie do rozwoju/testowania, nie do produkcji.
    -   **Szczegóły:** Przykład lub makieta danych/logiki dla funkcji pulpitu i audytu, prawdopodobnie używana do debugowania konsoli lub demonstracji.
-   `seoredirect/views/js/adminSeoRedirectApi.js`
    -   **Zakres:** Panel administracyjny (AdminSeoRedirectApiController).
    -   **Szczegóły:** Obsługuje interakcje po stronie klienta na ekranie konfiguracji API, takie jak generowanie kluczy API, kopiowanie kluczy do schowka lub wyświetlanie modalnych okien dokumentacji API.
-   `seoredirect/views/js/adminSeoRedirectAudit.js`
    -   **Zakres:** Panel administracyjny (AdminSeoRedirectAuditController).
    -   **Szczegóły:** Zarządza procesem audytu, w tym wywołaniami AJAX do wyzwalania skanów, aktualizowania wskaźników postępu, wyświetlania wyników audytu w dynamicznej tabeli i obsługi działań, takich jak tworzenie przekierowań z wyników audytu. Może zawierać wyskakujące okienka modalne do podglądu lub potwierdzania przekierowań.
-   `seoredirect/views/js/adminSeoRedirectConfig.js`
    -   **Zakres:** Panel administracyjny (Główna konfiguracja modułu lub AdminSeoRedirectSettingsController).
    -   **Szczegóły:** Ogólny JavaScript dla głównych formularzy konfiguracji modułu. Może to obejmować walidację formularzy, dynamiczną widoczność pól w oparciu o inne ustawienia lub wywołania AJAX do zapisywania konfiguracji.
-   `seoredirect/views/js/adminSeoRedirectDashboard.js`
    -   **Zakres:** Panel administracyjny (AdminSeoRedirectDashboardController).
    -   **Szczegóły:** Obsługuje interaktywne elementy pulpitu, takie jak ładowanie danych za pomocą AJAX, renderowanie wykresów (jeśli istnieją) i obsługę zmian wyboru okresu (`SEOR_DASHBOARD_PERIOD`).
-   `seoredirect/views/js/adminSeoRedirectImport.js`
    -   **Zakres:** Panel administracyjny (AdminSeoRedirectImportController).
    -   **Szczegóły:** Zarządza procesem importu CSV, w tym wyborem plików, wskaźnikami postępu, wyświetlaniem wyników/błędów importu i potencjalnie obsługą logiki `SEOR_SAFE_ROLLOUT` po stronie klienta.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `seoredirect/views/css/seoredirect-admin.css`
    -   **Zakres:** Stylizacja formularzy administracyjnych w panelu administracyjnym.
    -   **Szczegóły:** Zawiera specyficzne style dla różnych ekranów administracyjnych modułu, zapewniając spójny i przyjazny dla użytkownika interfejs w panelu administracyjnym PrestaShop. Obejmowałoby to stylizację siatek, formularzy, przycisków, okien modalnych i elementów pulpitu.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Szukaj klas z prefiksem `seor-` lub `admin-seoredirect-` dla konkretnych elementów modułu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   Opis modułu wspomina o hookach front-office (Nagłówek, Kolumny, Produkt, Stopka), ale spis plików nie wymienia konkretnych szablonów hooków w `views/templates/hook/`. Sugeruje to, że interakcja front-office jest przede wszystkim obsługiwana przez nadpisanie `FrontController` dla przekierowań, a nie przez renderowanie widocznej treści w hookach. Jeśli istnieją jakiekolwiek szablony hooków, byłyby one przeznaczone dla bardzo specyficznych, niezwiązanych z przekierowaniami elementów wyświetlania.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `seoredirect/lib/searchTool/views/scripts.tpl`: Prawdopodobnie zawiera logikę JavaScript lub Smarty dla ogólnego narzędzia wyszukiwania używanego na wielu ekranach administracyjnych.
    -   `seoredirect/views/admin/adminSearch.tpl`: Szablon dla ogólnego interfejsu wyszukiwania w panelu administracyjnym.
    -   `seoredirect/views/admin/adminSearchCategory.tpl`: Szablon do wyszukiwania/wybierania kategorii w panelu administracyjnym.
    -   `seoredirect/views/admin/adminSearchCategoryToMove.tpl`: Szablon do wyszukiwania przenoszenia kategorii.
    -   `seoredirect/views/admin/adminSearchCategoryToMoveInStock.tpl`: Szablon do wyszukiwania przenoszenia kategorii, specjalnie dla pozycji dostępnych w magazynie.
    -   `seoredirect/views/admin/adminSeoRedirectImport.tpl`: Główny szablon dla ekranu importu (AdminSeoRedirectImportController).
    -   `seoredirect/views/admin/stats.tpl`: Szablon dla ekranu statystyk (AdminSeoRedirectStatsController).
    -   `seoredirect/views/templates/admin/api.tpl`: Szablon dla ekranu konfiguracji API (AdminSeoRedirectApiController).
    -   `seoredirect/views/templates/admin/audit.tpl`: Szablon dla ekranu audytu (AdminSeoRedirectAuditController).
    -   `seoredirect/views/templates/admin/cli.tpl`: Szablon dla ekranu dokumentacji CLI (AdminSeoRedirectCliController).
    -   `seoredirect/views/templates/admin/dashboard.tpl`: Szablon dla pulpitu modułu (AdminSeoRedirectDashboardController).
    -   `seoredirect/views/templates/admin/employee_permissions.tpl`: Szablon do zarządzania uprawnieniami pracowników związanymi z zakładkami administracyjnymi modułu.
    -   `seoredirect/views/templates/admin/import.tpl`: Inny szablon dla funkcji importu (może być opakowaniem lub konkretną częścią procesu importu).
    -   `seoredirect/views/templates/admin/seo_redirect_settings/helpers/options/options.tpl`: Częściowy szablon do renderowania opcji na ekranie ustawień (AdminSeoRedirectSettingsController).
    -   `seoredirect/views/templates/admin/tools.tpl`: Szablon dla ekranu narzędzi (AdminSeoRedirectToolsController).
    -   `seoredirect/views/templates/admin/_api_documentation_modal.tpl`: Szablon modalny do wyświetlania dokumentacji API.
    -   `seoredirect/views/templates/admin/_audit_preview_modal.tpl`: Szablon modalny do podglądu wyników audytu lub tworzenia przekierowań.
    -   `seoredirect/views/templates/admin/_cli_documentation_modal.tpl`: Szablon modalny do wyświetlania dokumentacji CLI.
-   **Szablony Front Office (`views/templates/front/`)**:

    -   Nie wymieniono żadnych konkretnych szablonów front-office, co potwierdza, że działanie front-end modułu odbywa się przede wszystkim poprzez nadpisanie `FrontController` dla przekierowań, a nie widoczną treść.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_seor`: Przechowuje główne reguły przekierowań (Stary URL, Nowy URL, Typ przekierowania, Status itp.). Ta tabela jest zarządzana przez `AdminSeoRedirectListController` i `ObjectModel` `SeoRedirect` (implikowane).
    -   `ps_seor_history`: Przechowuje dziennik wszystkich uruchomionych przekierowań (Oryginalne żądanie, Przekierowano do, Typ, Znacznik czasu itp.). Ta tabela jest zarządzana przez `AdminSeoRedirectHistoryController` i `ObjectModel` `SeoRedirectHistory` (implikowane).
    -   `ps_configuration`: Przechowuje globalne ustawienia specyficzne dla modułu, takie jak `SEOR_DASHBOARD_PERIOD`, `IV_COL_DELIMITER`, `SEOR_SAFE_ROLLOUT`, `seor_pos_exclude`, `seor_unavorder`, `seor_pos_category`, `seor_pins_category`, `seor_pos_exclude_cat`, `seor_oos_cat_include`, `seor_emptycat_exclusions`, `seor_pos`, `seor_emptycat`, `SEOR_GSC_TOKEN`, `SEOR_GSC_SITE`.
-   **Tabela zarejestrowanych hooków**:

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `actionFrontControllerSetMedia` | Przed renderowaniem treści przez kontroler front-office | Potencjalnie ładuje JS/CSS front-office, jeśli takie istnieją, choć mało prawdopodobne dla modułu przekierowań. |
    | `actionDispatcherBefore` | Bardzo wcześnie w cyklu życia żądania, przed przekazaniem do kontrolera. | **KRYTYCZNE:** Jest to najbardziej prawdopodobny hook dla nadpisania `FrontController` w celu przechwycenia żądania i zastosowania logiki przekierowania. Pozwala modułowi przekierować, zanim PrestaShop nawet spróbuje znaleźć oryginalną stronę. |
    | `displayAdminProductsExtra` | Na stronie edycji produktu w panelu administracyjnym. | Może być używany do wyświetlania statusu przekierowania dla produktu lub sugerowania utworzenia przekierowania, jeśli URL produktu zostanie zmieniony. |
    | `displayAdminCategoriesExtra` | Na stronie edycji kategorii w panelu administracyjnym. | Podobnie jak w przypadku produktów, może wyświetlać status przekierowania lub sugerować przekierowania dla zmian URL kategorii. |
    | `displayHeader` | W sekcji `<head>` każdej strony front-office. | Mało prawdopodobne dla podstawowej logiki przekierowań, ale może być używane do dodawania meta tagów lub kanonicznych związanych z przekierowaniami, jeśli to konieczne. |
    | `displayRightColumn` | W prawej kolumnie stron front-office. | Mało prawdopodobne dla tego modułu. |
    | `displayFooter` | W stopce każdej strony front-office. | Mało prawdopodobne dla tego modułu. |
    | `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Może być używany do logowania lub audytu przekierowań związanych z procesami realizacji zamówienia, choć mniej bezpośrednio. |
    | `actionModuleInstall` | Podczas instalacji modułu. | Tworzy tabele bazy danych, rejestruje hooki, ustawia domyślne wartości konfiguracji. |
    | `actionModuleUninstall` | Podczas deinstalacji modułu. | Czyści tabele bazy danych, wyrejestrowuje hooki, usuwa wartości konfiguracji. |
    | `actionAdminControllerSetMedia` | Przed renderowaniem treści przez kontroler administracyjny. | Ładuje JS/CSS panelu administracyjnego dla stron administracyjnych modułu. |
    | `actionAdminSeoRedirectSave` | Niestandardowy hook, prawdopodobnie wyzwalany po zapisaniu reguły przekierowania w panelu administracyjnym. | Pozwala innym modułom lub niestandardowemu kodowi reagować na zmiany przekierowań. |
    | `actionAdminSeoRedirectDelete` | Niestandardowy hook, prawdopodobnie wyzwalany po usunięciu reguły przekierowania. | Pozwala innym modułom lub niestandardowemu kodowi reagować na usunięcia przekierowań. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu „Seo Redirects 301, 302, 303”.
