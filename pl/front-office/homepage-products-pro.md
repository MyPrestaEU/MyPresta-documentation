---
title: "Homepage Products Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop Homepage Products Pro od MyPresta.eu."
sidebar:
  label: "Homepage Products Pro - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Homepage Products Pro na MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-products-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/homepage-products-pro/)
>
> ---


# Homepage Products Pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony ustawień modułu „Homepage Products Pro”. Tutaj będziesz kontrolować globalne zachowanie i funkcje bloków produktów.

#### Ustawienia ogólne

- **Włącz wewnętrzne zakładki**

  - **Co robi to ustawienie:** Kontroluje, czy moduł może tworzyć własne niestandardowe zakładki na stronie głównej, podobne do domyślnych zakładek PrestaShop „Popularne produkty” lub „Nowe produkty”.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone (Tak):* Będziesz mógł tworzyć nowe bloki produktów, które pojawią się jako klikalne zakładki na Twojej stronie głównej, umożliwiając klientom przełączanie się między różnymi kolekcjami produktów.
    - *Gdy wyłączone (Nie):* Moduł będzie wyświetlał bloki produktów tylko jako samodzielne sekcje (np. poziome karuzele lub bloki kolumn), bez interfejsu zakładek.
  - **Zalecana wartość:** **Tak** (aby wykorzystać pełną moc modułu do dynamicznej zawartości strony głównej).
  - **Scenariusz / przykład sprzedawcy:** Chcesz pokazać „Nowości”, „Bestsellery” i „Sezonowe wybory” na swojej stronie głównej, nie czyniąc jej zbyt długą. Włączenie wewnętrznych zakładek pozwala umieścić każdy z tych elementów w osobnej zakładce.
- **Użyj edytora tekstu sformatowanego**

  - **Co robi to ustawienie:** Określa, czy wizualny edytor (WYSIWYG) jest dostępny podczas tworzenia lub edytowania opisów lub tytułów bloków produktów, ułatwiając formatowanie tekstu.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone (Tak):* Otrzymasz przyjazny dla użytkownika edytor (jak TinyMCE) z opcjami formatowania (pogrubienie, kursywa, linki itp.) dla pól tekstowych w module.
    - *Gdy wyłączone (Nie):* Będziesz miał pole do wprowadzania zwykłego tekstu, wymagające użycia podstawowego HTML, jeśli chcesz zastosować jakiekolwiek formatowanie.
  - **Zalecana wartość:** **Tak** (dla łatwiejszego tworzenia treści i lepszej kontroli wizualnej).
  - **Scenariusz / przykład sprzedawcy:** Chcesz dodać krótkie, stylizowane wprowadzenie nad blokiem produktów, np. „Odkryj naszą **ekskluzywną** kolekcję!”. Edytor tekstu sformatowanego sprawia, że jest to proste.
- **Załaduj lightslider**

  - **Co robi to ustawienie:** Kontroluje, czy moduł ładuje bibliotekę JavaScript LightSlider, która jest używana do tworzenia responsywnych karuzel i sliderów treści.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone (Tak):* Biblioteka LightSlider zostanie załadowana, umożliwiając wyświetlanie bloków produktów jako interaktywnych, dotykowych karuzel. Jest to zazwyczaj wymagane dla efektów wizualnych modułu.
    - *Gdy wyłączone (Nie):* Biblioteka LightSlider nie zostanie załadowana. Jeśli Twój motyw lub inny moduł zapewnia podobną funkcjonalność karuzeli, możesz to wyłączyć, aby uniknąć konfliktów lub zbędnego ładowania. Jednak jeśli nie ma innego rozwiązania karuzeli, Twoje bloki produktów mogą być wyświetlane jako statyczne siatki lub listy.
  - **Zalecana wartość:** **Tak** (chyba że masz konkretny powód lub konflikt, ponieważ jest to niezbędne dla funkcji karuzeli modułu).
  - **Scenariusz / przykład sprzedawcy:** Chcesz, aby Twój blok „Nowe produkty” był elegancką, przewijaną poziomo karuzelą. To ustawienie zapewnia załadowanie niezbędnego skryptu dla tej funkcjonalności.
- **Włącz analitykę**

  - **Co robi to ustawienie:** Aktywuje lub dezaktywuje wewnętrzne śledzenie wydajności bloków produktów przez moduł, takie jak wyświetlenia i kliknięcia.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone (Włączone):* Moduł będzie zbierał dane o tym, jak często Twoje bloki produktów są wyświetlane i klikane, dostarczając informacji o ich skuteczności.
    - *Gdy wyłączone (Wyłączone):* Żadne dane dotyczące wydajności nie będą zbierane ani wyświetlane w panelu modułu.
  - **Zalecana wartość:** **Włączone** (aby uzyskać cenne informacje o tym, które bloki produktów działają najlepiej).
  - **Scenariusz / przykład sprzedawcy:** Chcesz wiedzieć, czy Twój blok „Bestsellery” generuje większe zaangażowanie niż Twój blok „W promocji”. Włączenie analityki dostarcza tych danych.
- **Okres analityki**

  - **Co robi to ustawienie:** Definiuje ramy czasowe, dla których dane analityczne modułu będą wyświetlane.
  - **Wpływ zmiany tego ustawienia:** Zmienia zakres danych wyświetlanych w raportach analitycznych.
  - **Opcje:** Ostatnie 7 dni, Ostatnie 30 dni, Ostatnie 90 dni, Ostatnie 180 dni, Ostatnie 365 dni.
  - **Zalecana wartość:** **Ostatnie 30 dni** (dobra równowaga dla ostatnich trendów, ale dostosuj w zależności od potrzeb raportowania).
  - **Scenariusz / przykład sprzedawcy:** Chcesz przejrzeć wydajność bloków produktów na stronie głównej z ostatniego miesiąca, aby sprawdzić, czy ostatnia promocja miała wpływ.
- **Włącz buforowanie bloków**

  - **Co robi to ustawienie:** Aktywuje mechanizm buforowania dla bloków produktów generowanych przez moduł. Buforowanie przechowuje tymczasową wersję bloku, więc nie musi być on odbudowywany za każdym razem, gdy klient odwiedza stronę.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone (Tak):* Bloki produktów będą ładować się szybciej dla klientów, ponieważ serwer serwuje wersję z pamięci podręcznej. Może to znacznie poprawić czasy ładowania strony i wydajność serwera, zwłaszcza w sklepach o dużym ruchu.
    - *Gdy wyłączone (Nie):* Bloki produktów będą generowane dynamicznie przy każdym ładowaniu strony, co może być wolniejsze, ale zapewnia, że zawsze wyświetlane są najnowsze dane produktów (np. poziomy zapasów, ceny).
  - **Zalecana wartość:** **Tak** (dla korzyści z wydajności, chyba że masz bardzo szybko zmieniające się dane produktów, które muszą być w czasie rzeczywistym).
  - **Scenariusz / przykład sprzedawcy:** Twoja strona główna ma duży ruch i chcesz zapewnić jej jak najszybsze ładowanie. Włączenie buforowania przyspieszy wyświetlanie bloków produktów.
- **TTL pamięci podręcznej (sekundy)**

  - **Co robi to ustawienie:** Definiuje, jak długo (w sekundach) buforowana wersja bloku produktów pozostaje ważna, zanim zostanie odświeżona. (TTL oznacza „Time To Live”).
  - **Wpływ zmiany tego ustawienia:**
    - *Wyższa wartość:* Bloki są buforowane dłużej, co prowadzi do lepszej wydajności, ale potencjalnie pokazuje nieco nieaktualne informacje o produktach (np. jeśli cena się zmieni, może nie zaktualizować się na stronie głównej, dopóki pamięć podręczna nie wygaśnie).
    - *Niższa wartość:* Bloki są odświeżane częściej, zapewniając bardziej aktualne informacje, ale z nieco mniejszym wzrostem wydajności.
  - **Zalecana wartość:** **3600** (1 godzina) lub **7200** (2 godziny) to dobry punkt wyjścia. Dostosuj w zależności od tego, jak często zmieniają się dane Twoich produktów i jak krytyczne są aktualizacje w czasie rzeczywistym.
  - **Scenariusz / przykład sprzedawcy:** Masz błyskawiczną wyprzedaż, gdzie ceny zmieniają się co godzinę. Możesz ustawić Cache TTL na 3600 sekund (1 godzina), aby zapewnić stosunkowo szybką aktualizację cen na stronie głównej.
- **Automatyczne wykrywanie motywu**

  - **Co robi to ustawienie:** Próbuje automatycznie wykryć aktywny motyw PrestaShop, aby zastosować odpowiednie style i nadpisać szablony dla lepszej integracji wizualnej.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone (Tak):* Moduł próbuje dostosować swoje wyjście do struktury i stylizacji Twojego motywu, potencjalnie używając szablonów specyficznych dla motywu (np. `firezy-products17.tpl`). Często skutkuje to bardziej płynnym wyglądem.
    - *Gdy wyłączone (Nie):* Moduł będzie używał swoich domyślnych, ogólnych szablonów i stylizacji, które mogą nie pasować idealnie do projektu Twojego motywu. Może być konieczne ręczne wybranie motywu lub zastosowanie niestandardowego CSS.
  - **Zalecana wartość:** **Tak** (dla najlepszej integracji wizualnej od razu po instalacji).
  - **Scenariusz / przykład sprzedawcy:** Zainstalowałeś moduł, a bloki produktów nie wyglądają do końca dobrze z Twoim niestandardowym motywem. Włączenie tego może automatycznie naprawić stylizację.

#### Ukryte/Zaawansowane ustawienia (wewnętrzne klucze konfiguracyjne)

Te ustawienia zazwyczaj nie są bezpośrednio dostępne dla użytkownika, ale są wartościami konfiguracyjnymi, których moduł używa wewnętrznie. Są one wymienione tutaj dla kompletności i zrozumienia przez programistów.

- `update_`, `mypresta_updates`: Związane z kontrolą aktualizacji modułu i powiadomieniami z MyPresta.eu.
- `hpp_analytics_enabled`: Odpowiada ustawieniu „Włącz analitykę”.
- `hpp_cache_enabled`: Odpowiada ustawieniu „Włącz buforowanie bloków”.
- `hpp_cache_ttl`: Odpowiada ustawieniu „TTL pamięci podręcznej (sekundy)”.
- `hpp_theme_auto_detect`: Odpowiada ustawieniu „Automatyczne wykrywanie motywu”.
- `hpp_analytics_period`: Odpowiada ustawieniu „Okres analityki”.
- `hpp_carousel_native`: Prawdopodobnie wewnętrzna flaga dla typu karuzeli, być może związana z LightSlider.
- `PS_NB_DAYS_NEW_PRODUCT`: Domyślne ustawienie PrestaShop określające, przez ile dni produkt jest uważany za „nowy”. Moduł może używać tego dla bloków „Nowe produkty”.
- `PS_CURRENCY_DEFAULT`: Domyślny identyfikator waluty PrestaShop.
- `hpp_internal_tabs`: Odpowiada ustawieniu „Włącz wewnętrzne zakładki”.
- `hpp_bxslider`: Starsza biblioteka karuzeli, prawdopodobnie ustawienie dziedziczone lub awaryjne.
- `PS_LANG_DEFAULT`: Domyślny identyfikator języka PrestaShop.
- `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Ustawienie PrestaShop zezwalające pracownikom na zmianę języka formularza.
- `hpp_rich_text`: Odpowiada ustawieniu „Użyj edytora tekstu sformatowanego”.
- `hpp_theme`: Przechowuje wykrytą lub ręcznie wybraną nazwę motywu.
- `hpp_customtplpath`: Pozwala określić niestandardową ścieżkę dla szablonów, przydatne do zaawansowanej integracji motywu.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł „Homepage Products Pro” rozszerza Panel administracyjny PrestaShop, dodając dedykowaną sekcję do zarządzania blokami produktów.

- **Nazwa ekranu i lokalizacja w menu:**

  - Znajdziesz nową pozycję menu, zazwyczaj pod **Moduły > Homepage Products Pro** lub podobną nazwą, która prowadzi do panelu modułu.
  - Ten panel to miejsce, w którym tworzysz, edytujesz, usuwasz i organizujesz swoje bloki produktów.
- **Dostępne akcje i ustawienia:**

  - **Tabela listy bloków produktów:** Ten główny widok wyświetli listę wszystkich utworzonych bloków produktów. Każdy wpis pokaże:
    - **Nazwa:** Wewnętrzna nazwa, którą nadałeś blokowi (np. „Bestsellery na stronie głównej”).
    - **Tytuł:** Publiczny tytuł wyświetlany klientom (np. „Nasze najlepsze wybory!”).
    - **Hook:** Gdzie blok jest wyświetlany (np. `displayHome`, `displayHomeTabContent`, `displayLeftColumn`).
    - **Status:** Czy blok jest włączony, czy wyłączony.
    - **Pozycja:** Kolejność, w jakiej bloki pojawiają się w tym samym haku.
    - **Akcje:** Przyciski do **Edytowania**, **Duplikowania** lub **Usuwania** bloku.
  - **Przycisk „Dodaj nowy blok”:** Kliknięcie tego otworzy formularz do tworzenia zupełnie nowego bloku produktów.
  - **Formularz „Edytuj blok”:** Podczas dodawania lub edytowania bloku zazwyczaj konfigurujesz:
    - **Nazwa bloku:** Wewnętrzny identyfikator (np. „KolekcjaLetnia2023”).
    - **Tytuł wyświetlania:** Tytuł, który widzą klienci (np. „Kolekcja Letnia”).
    - **Opis:** Krótki tekst, który pojawia się nad produktami (edytor tekstu sformatowanego dostępny, jeśli włączony).
    - **Wybór haka:** Wybierz, gdzie blok się pojawi (np. `displayHome`, `displayHomeTabContent` dla zakładek, `displayLeftColumn`).
    - **Wybór produktu:** To jest kluczowe. Zdefiniujesz, *które* produkty pojawią się w bloku. Opcje zazwyczaj obejmują:
      - **Konkretne produkty:** Ręcznie wybierz pojedyncze produkty za pomocą narzędzia wyszukiwania.
      - **Produkty z kategorii:** Wybierz jedną lub więcej kategorii, a moduł wyświetli produkty z nich.
      - **Nowe produkty:** Automatycznie wyświetlaj najnowsze produkty dodane do Twojego sklepu.
      - **Bestsellery:** Automatycznie wyświetlaj najlepiej sprzedające się produkty w Twoim sklepie.
      - **Produkty w promocji:** Automatycznie wyświetlaj produkty aktualnie w promocji.
      - **Wyróżnione produkty:** Produkty oznaczone jako wyróżnione.
    - **Liczba produktów do wyświetlenia:** Ogranicz, ile produktów jest wyświetlanych.
    - **Typ wyświetlania:** Wybierz między karuzelą/sliderem a statyczną siatką/listą.
    - **Ustawienia karuzeli:** Jeśli używasz karuzeli, ustawienia dla elementów na slajd, automatycznego odtwarzania, strzałek nawigacyjnych itp.
    - **Wybór widoczności/odbiorców:** Zdefiniuj, kto widzi blok (np. wszyscy klienci, konkretne grupy klientów, konkretne kraje).
    - **Specyfika językowa:** Skonfiguruj tytuły i opisy dla różnych języków.
    - **Status:** Włącz/Wyłącz pojedynczy blok.
    - **Pozycja:** Ustaw kolejność wyświetlania względem innych bloków w tym samym haku.
- **Wpływ zmian:**

  - **Dodanie nowego bloku:** Nowe wyświetlanie produktów pojawi się w Twoim front-office w wybranym haku, prezentując wybrane produkty zgodnie z Twoimi ustawieniami.
  - **Edycja bloku:** Zmiany w tytułach, opisach, wyborze produktów, typie wyświetlania lub ustawieniach zostaną natychmiast odzwierciedlone w front-office (z zastrzeżeniem TTL pamięci podręcznej, jeśli buforowanie jest włączone).
  - **Usunięcie bloku:** Wyświetlanie produktów zostanie usunięte z Twojego front-office.
  - **Zmiana pozycji:** Kolejność bloków w określonym haku zostanie zaktualizowana w front-office.
  - **Włączanie/Wyłączanie:** Przełącza widoczność bloku w Twoim sklepie.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

  1.  **Zaplanuj układ strony głównej:** Zdecyduj, jakie typy produktów chcesz wyróżnić (nowe, bestsellery, konkretne kategorie, promocje).
  2.  **Utwórz nowe bloki:** Dla każdej zaplanowanej sekcji przejdź do panelu modułu i kliknij „Dodaj nowy blok”.
  3.  **Skonfiguruj każdy blok:**
      *   Nadaj mu jasną wewnętrzną nazwę (np. „HP\_Nowości”).
      *   Napisz angażujący tytuł wyświetlania i opis.
      *   Wybierz odpowiedni hak (np. `displayHome` dla głównej zawartości, `displayHomeTabContent` dla zakładek).
      *   Wybierz metodę wyboru produktu (ręcznie, kategoria, nowe, itp.).
      *   Dostosuj ustawienia wyświetlania i karuzeli.
      *   Ustaw pozycję, aby kontrolować jej kolejność.
  4.  **Przejrzyj w front-office:** Zawsze sprawdzaj stronę główną swojego sklepu po wprowadzeniu zmian, aby upewnić się, że wszystko wygląda i działa zgodnie z oczekiwaniami.
  5.  **Monitoruj analitykę:** Regularnie sprawdzaj analitykę modułu (jeśli włączona), aby zrozumieć, które bloki działają dobrze i odpowiednio dostosować swoją strategię.
  6.  **Utrzymuj i aktualizuj:** W miarę pojawiania się nowych produktów lub zmian w promocjach, aktualizuj istniejące bloki lub twórz nowe, aby Twoja strona główna była świeża i aktualna.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Główna konfiguracja | Włącz wewnętrzne zakładki | Tak | Umożliwia tworzenie zakładek produktów na stronie głównej. |
| Główna konfiguracja | Użyj edytora tekstu sformatowanego | Tak | Zapewnia wizualny edytor dla pól tekstowych. |
| Główna konfiguracja | Załaduj lightslider | Tak | Włącza karuzele/slidery produktów. |
| Główna konfiguracja | Włącz analitykę | Włączone | Śledzi wyświetlenia i kliknięcia bloków produktów. |
| Główna konfiguracja | Okres analityki | Ostatnie 30 dni | Ustawia ramy czasowe dla raportów analitycznych. |
| Główna konfiguracja | Włącz buforowanie bloków | Tak | Poprawia szybkość ładowania strony poprzez buforowanie bloków. |
| Główna konfiguracja | TTL pamięci podręcznej (sekundy) | 3600 (1 godzina) | Jak długo buforowane bloki pozostają ważne. |
| Główna konfiguracja | Automatyczne wykrywanie motywu | Tak | Dostosowuje wyjście modułu do Twojego motywu. |
| Zarządzanie blokami | Nazwa bloku | N/A (definiowane przez użytkownika) | Wewnętrzny identyfikator dla Twojego bloku produktów. |
| Zarządzanie blokami | Tytuł wyświetlania | N/A (definiowane przez użytkownika) | Publiczny tytuł wyświetlany klientom. |
| Zarządzanie blokami | Opis | N/A (definiowane przez użytkownika) | Tekst wyświetlany nad blokiem produktów. |
| Zarządzanie blokami | Wybór haka | `displayHome` / `displayHomeTabContent` | Określa, gdzie blok pojawia się w sklepie. |
| Zarządzanie blokami | Wybór produktu | N/A (definiowane przez użytkownika) | Definiuje, które produkty są wyświetlane (ręcznie, kategoria, nowe, bestsellery itp.). |
| Zarządzanie blokami | Liczba produktów | N/A (definiowane przez użytkownika) | Ogranicza ilość wyświetlanych produktów. |
| Zarządzanie blokami | Typ wyświetlania | Karuzela / Siatka | Sposób wizualnej prezentacji produktów. |
| Zarządzanie blokami | Widoczność/Odbiorcy | Wszyscy klienci | Ogranicza widoczność bloku do określonych grup/krajów. |
| Zarządzanie blokami | Status | Włączone | Przełącza widoczność bloku w front-office. |
| Zarządzanie blokami | Pozycja | N/A (definiowane przez użytkownika) | Ustawia kolejność wyświetlania bloków w haku. |

## 3. Rozwiązywanie problemów przez sprzedawców i często zadawane pytania (FAQ)

**P1: Moje bloki produktów nie wyświetlają się na stronie głównej lub wyglądają na uszkodzone.**

- **O:**
  1.  **Sprawdź status modułu:** Upewnij się, że moduł „Homepage Products Pro” jest włączony w **Moduły > Menedżer modułów**.
  2.  **Sprawdź status bloku:** Przejdź do panelu konfiguracji modułu i sprawdź, czy utworzone bloki produktów są „Włączone”.
  3.  **Wybór haka:** Sprawdź dokładnie, czy przypisałeś bloki do prawidłowych haków front-office (np. `displayHome` dla głównej zawartości, `displayHomeTabContent` dla zakładek, `displayLeftColumn` dla kolumn).
  4.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Czasami stara zawartość z pamięci podręcznej uniemożliwia wyświetlanie nowych danych modułu.
  5.  **Kompatybilność motywu:** Jeśli masz niestandardowy motyw, spróbuj włączyć „Automatyczne wykrywanie motywu” w głównej konfiguracji modułu. Jeśli problemy nadal występują, Twój motyw może wymagać drobnych poprawek CSS (patrz P3).

**P2: Moje bloki produktów wyświetlają się, ale produkty nie są aktualizowane (np. stare ceny, nadal widoczne produkty niedostępne w magazynie).**

- **O:** Jest to zazwyczaj problem z buforowaniem.
  1.  **Pamięć podręczna modułu:** W głównej konfiguracji modułu sprawdź „Włącz buforowanie bloków” i „TTL pamięci podręcznej (sekundy)”. Jeśli buforowanie jest włączone, blok może wyświetlać starszą, buforowaną wersję. Możesz tymczasowo wyłączyć buforowanie, zapisać, a następnie ponownie je włączyć, lub po prostu poczekać, aż TTL wygaśnie.
  2.  **Pamięć podręczna PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Spowoduje to wyczyszczenie wszystkich pamięci podręcznych na poziomie PrestaShop.
  3.  **Pamięć podręczna przeglądarki:** Wyczyść pamięć podręczną i pliki cookie przeglądarki lub wyświetl swoją witrynę w trybie incognito/prywatnym, aby upewnić się, że nie widzisz lokalnie buforowanej wersji.

**P3: Bloki produktów pojawiają się, ale stylizacja jest nieprawidłowa (np. złe czcionki, źle wyrównane elementy, uszkodzona karuzela).**

- **O:**
  1.  **Automatyczne wykrywanie motywu:** W głównej konfiguracji modułu upewnij się, że „Automatyczne wykrywanie motywu” jest włączone. Pomaga to modułowi używać stylizacji specyficznej dla motywu.
  2.  **Załaduj LightSlider:** Jeśli karuzele są uszkodzone, upewnij się, że „Załaduj lightslider” jest włączone w konfiguracji modułu.
  3.  **Konflikty motywu:** Niestandardowe motywy czasami mają sprzeczne CSS lub JavaScript. Jeśli podejrzewasz to, spróbuj tymczasowo przełączyć się na domyślny motyw PrestaShop (np. Classic), aby sprawdzić, czy problem zostanie rozwiązany. Jeśli tak, Twój niestandardowy motyw wymaga poprawek.
  4.  **Niestandardowy CSS:** Może być konieczne dodanie niestandardowego CSS do arkusza stylów Twojego motywu, aby nadpisać domyślne style modułu i dopasować je do Twojego motywu. Deweloper stron internetowych może w tym pomóc.

**P4: Utworzyłem nowy blok produktów, ale nie pojawia się on jako zakładka na stronie głównej.**

- **O:**
  1.  **Włącz wewnętrzne zakładki:** W głównej konfiguracji modułu upewnij się, że „Włącz wewnętrzne zakładki” jest ustawione na „Tak”.
  2.  **Prawidłowy hak:** Upewnij się, że **Wybór haka** bloku produktów jest ustawiony na `displayHomeTabContent`. Bloki ustawione na `displayHome` lub kolumny nie pojawią się jako zakładki.
  3.  **Pozycjonowanie:** Sprawdź pozycję bloków z zakładkami. Jeśli są bardzo nisko w kolejności, mogą się nie pojawić, jeśli inne moduły zajmują miejsce.

**P5: Mój edytor tekstu sformatowanego nie działa lub nie mogę formatować tekstu.**

- **O:**
  1.  **Włącz edytor tekstu sformatowanego:** W głównej konfiguracji modułu upewnij się, że „Użyj edytora tekstu sformatowanego” jest ustawione na „Tak”.
  2.  **Problemy z przeglądarką:** Spróbuj innej przeglądarki internetowej lub wyczyść pamięć podręczną bieżącej przeglądarki.
  3.  **Konflikty JavaScript:** Czasami inne moduły lub skrypty motywu mogą zakłócać działanie edytora tekstu sformatowanego. Jeśli problem nadal występuje, skonsultuj się z deweloperem.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd architektury technicznej i bazy kodu modułu „Homepage Products Pro”, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł „Homepage Products Pro” (`hpp`) stosuje standardową architekturę modułu PrestaShop, głównie wykorzystując haki do wyświetlania w front-office i metodę `getContent()` do konfiguracji w back-office. Implementuje niestandardowy panel do zarządzania blokami produktów, które są przechowywane jako wartości konfiguracyjne lub potencjalnie w niestandardowych tabelach bazy danych (chociaż w dostarczonym spisie nie zidentyfikowano jawnych klas `ObjectModel`, złożone dane są często serializowane do `ps_configuration` lub zarządzane za pomocą klas pomocniczych). Moduł w dużym stopniu opiera się na szablonach Smarty do renderowania różnych bloków produktów i interfejsów administracyjnych. Integruje zewnętrzne biblioteki, takie jak LightSlider do karuzel i TinyMCE do edycji tekstu sformatowanego. Mechanizmy analityczne i buforowania są wbudowane w celu zapewnienia wydajności i wglądu.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

- `hpp/controllers/front/index.php`
  - **Nazwa klasy:** `HppIndexModuleFrontController` (prawdopodobnie, na podstawie konwencji nazewnictwa plików)
  - **Klasa nadrzędna:** `ModuleFrontController`
  - **Odpowiedzialność:** Ten kontroler prawdopodobnie służy jako ogólny punkt wejścia dla akcji modułu front-office, które nie pasują do konkretnych kategorii AJAX lub śledzenia. Może obsługiwać początkowe ładowanie danych lub renderowanie określonych typów bloków, jeśli nie są one całkowicie sterowane hakami.
- `hpp/controllers/front/lazyblock.php`
  - **Nazwa klasy:** `HppLazyblockModuleFrontController`
  - **Klasa nadrzędna:** `ModuleFrontController`
  - **Odpowiedzialność:** Ten kontroler jest przeznaczony do obsługi żądań AJAX do leniwego ładowania bloków produktów. Gdy użytkownik przewija stronę lub wchodzi w interakcję z zakładką, ten kontroler zostanie wywołany w celu pobrania danych produktów i renderowania kodu HTML dla określonego bloku, poprawiając początkowe czasy ładowania strony. Prawdopodobnie przyjmuje parametry, takie jak ID bloku, numer strony lub kryteria filtrowania.
- `hpp/controllers/front/track.php`
  - **Nazwa klasy:** `HppTrackModuleFrontController`
  - **Klasa nadrzędna:** `ModuleFrontController`
  - **Odpowiedzialność:** Ten kontroler jest odpowiedzialny za obsługę żądań śledzenia analityki. Gdy blok produktów jest wyświetlany lub produkt w bloku jest klikany, żądanie jest wysyłane do tego kontrolera w celu zarejestrowania zdarzenia, przyczyniając się do wewnętrznych danych analitycznych modułu.

#### Kontrolery administracyjne Back-Office

W dostarczonym spisie nie zidentyfikowano dedykowanych plików `AdminController`. Sugeruje to, że zarządzanie back-office modułu (tworzenie/edycja bloków produktów) jest obsługiwane bezpośrednio w metodzie `getContent()` pliku `hpp.php`, potencjalnie przy użyciu klas `HelperForm` i `HelperList` PrestaShop lub niestandardowego podejścia do renderowania na głównej stronie konfiguracji modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

W katalogu `classes/` nie wymieniono jawnie żadnych niestandardowych klas PHP rozszerzających `ObjectModel` ani inne podstawowe funkcjonalności. Oznacza to, że:

- Złożone dane (takie jak konfiguracje poszczególnych bloków produktów) są prawdopodobnie przechowywane jako serializowane tablice lub ciągi JSON w tabeli `ps_configuration`, zarządzane bezpośrednio przez plik modułu `hpp.php`.
- Alternatywnie, moduł może używać bardziej proceduralnego podejścia lub polegać na klasach pomocniczych zdefiniowanych bezpośrednio w `hpp.php` lub jego dołączonych bibliotekach.
- Katalog `lib/` zawiera różne klasy pomocnicze i zewnętrzne biblioteki (np. `searchTool`, `smartyTemplatesManager`, `src`). Są one prawdopodobnie używane do konkretnych funkcjonalności, takich jak wyszukiwanie produktów, zarządzanie szablonami lub implementacja karuzeli, a nie do definiowania podstawowych jednostek biznesowych.

### 4.4 Zasoby JavaScript (`views/js/`)

- `hpp/js/script.js`
  - **Zakres:** Front-office.
  - **Szczegóły:** Prawdopodobnie zawiera główną logikę front-office do inicjalizacji karuzel produktów (LightSlider), obsługi przełączania zakładek i ogólnych interakcji UI związanych z blokami produktów. Może również zawierać logikę do leniwego ładowania lub podstawowego śledzenia analityki.
- `hpp/js/tinymce16-force-urls.inc.js`
  - **Zakres:** Back-office.
  - **Szczegóły:** Specyficzny skrypt dla edytora tekstu sformatowanego TinyMCE, prawdopodobnie w celu zapewnienia prawidłowego obsługi i formatowania adresów URL w edytorze, zwłaszcza w starszych kontekstach PrestaShop 1.6.
- `hpp/lib/searchTool/views/js/autocomplete.js`
  - **Zakres:** Back-office.
  - **Szczegóły:** Zapewnia funkcjonalność JavaScript dla pola wyszukiwania z autouzupełnianiem, używanego podczas wybierania konkretnych produktów dla bloku produktów w konfiguracji back-office. Prawdopodobnie wykonuje wywołania AJAX w celu pobrania sugestii produktów.
- `hpp/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`
  - **Zakres:** Back-office.
  - **Szczegóły:** Zarządza dynamicznym tworzeniem, edytowaniem i wybieraniem szablonów Smarty w interfejsie back-office, prawdopodobnie dla zaawansowanych użytkowników w celu dostosowania układów bloków.
- `hpp/lib/src/js/lightslider.js`
  - **Zakres:** Front-office.
  - **Szczegóły:** Podstawowa biblioteka LightSlider, odpowiedzialna za tworzenie responsywnych, dotykowych karuzel treści dla bloków produktów. Obsługuje przejścia slajdów, nawigację i responsywność.
- `hpp/views/js/admin-audience-picker.js`
  - **Zakres:** Back-office.
  - **Szczegóły:** Zapewnia interaktywną logikę dla interfejsu „Wybór odbiorców” w back-office, umożliwiając administratorom wybieranie konkretnych grup klientów lub krajów dla widoczności bloku.
- `hpp/views/js/adminHppDashboard.js`
  - **Zakres:** Back-office.
  - **Szczegóły:** Główny JavaScript dla panelu back-office modułu, obsługujący interakcje, takie jak dodawanie/edycja bloków, przeciąganie i upuszczanie w celu zmiany kolejności oraz ogólne zarządzanie interfejsem użytkownika.
- `hpp/views/js/adminHppDashboardDemo.js`
  - **Zakres:** Back-office.
  - **Szczegóły:** Prawdopodobnie zawiera JavaScript specyficzny dla demonstracji panelu back-office, być może do początkowej konfiguracji lub prezentacji funkcji, i może nie być aktywny w środowisku produkcyjnym.
- `hpp/views/js/hpp-analytics.js`
  - **Zakres:** Front-office.
  - **Szczegóły:** Obsługuje stronę front-office śledzenia analityki, wysyłając dane (np. wyświetlenia bloków, kliknięcia produktów) do kontrolera `track.php` za pośrednictwem AJAX.
- `hpp/views/js/hpp-lazyload.js`
  - **Zakres:** Front-office.
  - **Szczegóły:** Implementuje leniwe ładowanie bloków produktów lub ich zawartości, wykonując wywołania AJAX do `lazyblock.php`, gdy bloki wchodzą w obszar widoku lub zakładki są aktywowane.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `hpp/css/global.css`
  - **Zakres:** Front-office.
  - **Szczegóły:** Zawiera ogólne, globalne style dla wyjścia front-office modułu, zapewniając podstawową spójność wizualną.
- `hpp/css/homefeaturedslider.css`
  - **Zakres:** Front-office.
  - **Szczegóły:** Specyficzne style dla komponentu slidera wyróżnionych produktów na stronie głównej, prawdopodobnie dla starszych wersji PrestaShop lub konkretnych implementacji karuzeli.
- `hpp/css/hpp.css`
  - **Zakres:** Front-office.
  - **Szczegóły:** Główny arkusz stylów front-office dla modułu, definiujący wygląd i działanie bloków produktów, siatek i karuzel.
- `hpp/css/internal-tabs.css`
  - **Zakres:** Front-office.
  - **Szczegóły:** Style specyficzne dla wewnętrznego interfejsu zakładek na stronie głównej, w tym nawigacji po zakładkach i obszarów treści.
- `hpp/css.css`
  - **Zakres:** Front-office.
  - **Szczegóły:** Potencjalnie dziedziczny lub dodatkowy ogólny arkusz stylów.
- `hpp/lib/searchTool/views/css/autocomplete.css`
  - **Zakres:** Back-office.
  - **Szczegóły:** Style dla pola wyszukiwania z autouzupełnianiem używanego w back-office do wyboru produktów.
- `hpp/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`
  - **Zakres:** Back-office.
  - **Szczegóły:** Style dla interfejsu menedżera szablonów Smarty w back-office.
- `hpp/lib/src/css/lightslider.css`
  - **Zakres:** Front-office.
  - **Szczegóły:** Podstawowy CSS dla biblioteki LightSlider, zapewniający podstawową stylizację dla komponentu karuzeli.
- `hpp/views/css/admin-audience-picker.css`
  - **Zakres:** Back-office.
  - **Szczegóły:** Style dla interfejsu wyboru odbiorców w back-office.
- `hpp/views/css/admin-searchtool.css`
  - **Zakres:** Back-office.
  - **Szczegóły:** Dodatkowe style dla narzędzia wyszukiwania w panelu administracyjnym.
- `hpp/views/css/admin_hpp.css`
  - **Zakres:** Back-office.
  - **Szczegóły:** Główny arkusz stylów dla konfiguracji i panelu modułu w back-office.
- `hpp/views/templates/admin/css/css.css`
  - **Zakres:** Back-office.
  - **Szczegóły:** Arkusz stylów umieszczony specjalnie w katalogu szablonów administracyjnych, prawdopodobnie dla bardzo specyficznych potrzeb stylizacji w tych szablonach.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony haków (`views/templates/hook/`)

Te szablony są renderowane, gdy moduł jest podłączony do określonych pozycji w front-office. Wiele z nich to nadpisania specyficzne dla motywu.

- `hpp/views/templates/hook/column17.tpl`
  - **Hak:** `displayLeftColumn`, `displayRightColumn` (PrestaShop 1.7.x+).
  - **Wyjście:** Renderuje blok produktów zaprojektowany dla lewej lub prawej kolumny, zazwyczaj pionową listę lub małą siatkę.
- `hpp/views/templates/hook/firezy-column17.tpl`
  - **Hak:** `displayLeftColumn`, `displayRightColumn` (PrestaShop 1.7.x+ dla motywu Firezy).
  - **Wyjście:** Nadpisanie specyficzne dla motywu dla bloków produktów w kolumnach, dostosowane do motywu Firezy.
- `hpp/views/templates/hook/firezy-homeTab.tpl`
  - **Hak:** `displayHomeTab` (dla motywu Firezy).
  - **Wyjście:** Renderuje rzeczywisty link nawigacyjny zakładki (np. „Kolekcja letnia”) dla motywu Firezy.
- `hpp/views/templates/hook/firezy-homeTabContent.tpl`
  - **Hak:** `displayHomeTabContent` (dla motywu Firezy).
  - **Wyjście:** Renderuje zawartość (sam blok produktów), która pojawia się, gdy aktywna jest określona zakładka, dostosowana do motywu Firezy.
- `hpp/views/templates/hook/firezy-internal-tabs.tpl`
  - **Hak:** `displayHome` (dla motywu Firezy).
  - **Wyjście:** Renderuje cały wewnętrzny interfejs zakładek (zarówno nawigację, jak i opakowanie treści) dla motywu Firezy.
- `hpp/views/templates/hook/firezy-products17.tpl`
  - **Hak:** `displayHome` (dla motywu Firezy).
  - **Wyjście:** Renderuje ogólny blok produktów (karuzelę lub siatkę) dla głównego obszaru treści strony głównej, dostosowany do motywu Firezy.
- `hpp/views/templates/hook/homeTab.tpl`
  - **Hak:** `displayHomeTab`.
  - **Wyjście:** Renderuje ogólny link nawigacyjny zakładki.
- `hpp/views/templates/hook/homeTabContent.tpl`
  - **Hak:** `displayHomeTabContent`.
  - **Wyjście:** Renderuje ogólną zawartość dla bloku produktów z zakładkami.
- `hpp/views/templates/hook/hummingbird-column17.tpl`, `hummingbird-homeTab.tpl`, `hummingbird-homeTabContent.tpl`, `hummingbird-internal-tabs.tpl`, `hummingbird-products17.tpl`
  - **Hak:** Podobnie jak Firezy, są to nadpisania specyficzne dla motywu Hummingbird, zapewniające dostosowane układy dla kolumn, nawigacji po zakładkach, zawartości zakładek, wewnętrznych opakowań zakładek i ogólnych bloków produktów.
- `hpp/views/templates/hook/internal-tabs.tpl`
  - **Hak:** `displayHome`.
  - **Wyjście:** Renderuje ogólny wewnętrzny interfejs zakładek (nawigacja i opakowanie treści).
- `hpp/views/templates/hook/products17.tpl`
  - **Hak:** `displayHome`, `displayTopColumn`.
  - **Wyjście:** Renderuje ogólny blok produktów (karuzelę lub siatkę) dla głównej strony głównej lub górnego obszaru treści kolumny (PrestaShop 1.7.x+).
- `hpp/views/templates/hook/warehouse-column17.tpl`, `warehouse-homeTab.tpl`, `warehouse-homeTabContent.tpl`, `warehouse-internal-tabs.tpl`, `warehouse-products17.tpl`
  - **Hak:** Podobnie jak Firezy i Hummingbird, są to nadpisania specyficzne dla motywu Warehouse, zapewniające dostosowane układy dla kolumn, nawigacji po zakładkach, zawartości zakładek, wewnętrznych opakowań zakładek i ogólnych bloków produktów.

#### Szablony administracyjne (`views/templates/admin/`)

Te szablony są używane dla interfejsu back-office modułu.

- `hpp/views/templates/admin/audience-picker.tpl`
  - **Wyjście:** Renderuje kod HTML dla interfejsu wyboru grupy klientów i kraju.
- `hpp/views/templates/admin/country-priority-picker.tpl`
  - **Wyjście:** Renderuje kod HTML do wyboru i priorytetyzacji krajów.
- `hpp/views/templates/admin/menu.tpl`
  - **Wyjście:** Renderuje specyficzne menu lub nawigację modułu w jego panelu back-office.
- `hpp/views/templates/admin/scripts.tpl`
  - **Wyjście:** Zawiera pliki JavaScript lub skrypty inline specjalnie dla interfejsu administracyjnego.
- `hpp/views/templates/admin/ul-li.tpl`
  - **Wyjście:** Ogólny szablon listy, prawdopodobnie używany do wyświetlania list elementów lub opcji w formularzach administracyjnych.

#### Szablony bibliotek (`hpp/lib/`)

Te szablony są częścią zintegrowanych bibliotek.

- `hpp/lib/searchTool/views/scripts.tpl`
  - **Wyjście:** Zawiera pliki JavaScript lub skrypty inline dla funkcjonalności narzędzia wyszukiwania.
- `hpp/lib/smartyTemplatesManager/tpl/example.tpl`
  - **Wyjście:** Przykładowy szablon dla Smarty Templates Manager, prawdopodobnie do demonstracji lub jako podstawa.
- `hpp/lib/smartyTemplatesManager/views/buttonManager.tpl`
  - **Wyjście:** Renderuje przyciski lub kontrolki do zarządzania szablonami.
- `hpp/lib/smartyTemplatesManager/views/createTemplateForm.tpl`
  - **Wyjście:** Renderuje formularz do tworzenia nowych niestandardowych szablonów.
- `hpp/lib/smartyTemplatesManager/views/editTemplateForm.tpl`
  - **Wyjście:** Renderuje formularz do edycji istniejących niestandardowych szablonów.
- `hpp/lib/smartyTemplatesManager/views/mainForm.tpl`
  - **Wyjście:** Główny formularz dla interfejsu Smarty Templates Manager.
- `hpp/lib/smartyTemplatesManager/views/selectInput.tpl`
  - **Wyjście:** Renderuje ogólne pole wyboru/rozwijane.

### 4.7 Schemat bazy danych i mapa haków

#### Tabele bazy danych

Nie zidentyfikowano niestandardowych plików SQL (`.sql`) ani nie wymieniono klas `ObjectModel`. To silnie sugeruje, że moduł przechowuje swoje dane konfiguracyjne i definicje bloków produktów głównie w tabeli `ps_configuration` PrestaShop.

- **`ps_configuration`**: Ta tabela będzie zawierać wpisy z kluczami takimi jak `HPP_ANALYTICS_ENABLED`, `HPP_CACHE_TTL`, `HPP_BLOCKS_DATA` (lub podobne, gdzie `HPP_BLOCKS_DATA` zawierałoby serializowaną tablicę lub ciąg JSON wszystkich konfiguracji bloków produktów).

#### Tabela zarejestrowanych haków

Moduł rejestruje się w różnych hakach PrestaShop, aby wstrzykiwać swoją zawartość i funkcjonalność.

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykiwanie zasobów CSS i JS (np. LightSlider, `hpp.css`, `script.js`). |
| `actionFrontControllerSetMedia` | Przed renderowaniem wyjścia przez kontroler front-office. | Dodawanie specyficznych zasobów CSS/JS warunkowo, w zależności od strony lub kontrolera. |
| `displayHome` | Główny obszar treści strony głównej. | Renderowanie ogólnych bloków produktów (karuzel, siatek) bezpośrednio na stronie głównej. |
| `displayHomeTab` | W obszarze nawigacji po zakładkach na stronie głównej. | Renderowanie linków nawigacyjnych dla niestandardowych zakładek produktów. |
| `displayHomeTabContent` | W obszarze treści zakładek na stronie głównej. | Renderowanie rzeczywistych bloków produktów, które pojawiają się, gdy aktywna jest niestandardowa zakładka. |
| `displayLeftColumn` | W lewej kolumnie stron, na których jest aktywny. | Renderowanie pionowych bloków produktów w lewym pasku bocznym. |
| `displayRightColumn` | W prawej kolumnie stron, na których jest aktywny. | Renderowanie pionowych bloków produktów w prawym pasku bocznym. |
| `displayTopColumn` | W górnym obszarze treści, zazwyczaj poniżej nagłówka. | Renderowanie bloków produktów w górnej sekcji strony głównej. |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony back-office. | Wstrzykiwanie zasobów CSS i JS dla stron konfiguracji modułu w back-office. |
| `actionAdminControllerSetMedia` | Przed renderowaniem wyjścia przez kontroler administracyjny. | Dodawanie specyficznych zasobów CSS/JS dla stron administracyjnych modułu. |
| `actionProductUpdate` | Po zaktualizowaniu produktu w back-office. | Potencjalne czyszczenie pamięci podręcznej dla bloków zawierających ten produkt lub ponowne indeksowanie danych produktu. |
| `actionProductDelete` | Po usunięciu produktu w back-office. | Potencjalne czyszczenie pamięci podręcznej dla bloków zawierających ten produkt lub usunięcie go z konfiguracji bloków. |
| `actionCategoryUpdate` | Po zaktualizowaniu kategorii w back-office. | Potencjalne czyszczenie pamięci podręcznej dla bloków wyświetlających produkty z tej kategorii. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Homepage Products Pro”, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz dedykowany zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów technicznych lub pytań.

- **MyPresta.eu Historia zamówień i pobieranie:** <https://mypresta.eu/my-account/orders/>
- **MyPresta.eu Kontakt z pomocą techniczną:** <https://mypresta.eu/contact>
