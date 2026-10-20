---
title: "Presta Speed Cache - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu Presta Speed Cache PrestaShop od MyPresta.eu."
sidebar:
  label: "Presta Speed Cache - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Presta Speed Cache na MyPresta.eu](https://mypresta.eu/modules/administration-tools/presta-speed-cache.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/presta-speed-cache/)
>
> ---


# Presta Speed Cache

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5 (Moduł jest zaprojektowany do pracy w tym zakresie, zapewniając szeroką kompatybilność przy jednoczesnym wspieraniu najnowszych stabilnych wersji PHP.)
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP, takie jak cURL, JSON i OpenSSL, które są zazwyczaj dostępne w większości nowoczesnych środowisk hostingowych. W przypadku zaawansowanych metod buforowania, takich jak Redis lub Memcached, usługi te muszą być zainstalowane i skonfigurowane na Twoim serwerze.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny obszar konfiguracji dla Presta Speed Cache. Znajdziesz tu różne ustawienia, aby precyzyjnie dostroić działanie pamięci podręcznej Twojego sklepu.

#### Zakładka Ustawienia ogólne

-   **Włącz pamięć podręczną:**

    -   **Co robi to ustawienie:** Jest to główny przełącznik dla modułu. Włącza lub wyłącza funkcję buforowania dla całego Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł zacznie buforować strony i szybko je serwować. Wydajność Twojego sklepu znacznie się poprawi.
        -   *Gdy wyłączone:* Moduł przestanie buforować, a Twój sklep powróci do domyślnej prędkości PrestaShop, która jest zazwyczaj wolniejsza.
    -   **Zalecana wartość:** **TAK**. Jest to podstawowa funkcja modułu.
    -   **Scenariusz / przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz aktywować korzyści związane z szybkością. Ustaw to na TAK. Jeśli rozwiązujesz problem z innym modułem i podejrzewasz, że buforowanie może przeszkadzać, możesz tymczasowo je wyłączyć.
-   **Czas życia pamięci podręcznej (minuty):**

    -   **Co robi to ustawienie:** Określa, jak długo buforowana strona pozostaje ważna, zanim moduł uzna ją za „nieaktualną” i przebuduje.
    -   **Efekt zmiany tego ustawienia:**
        -   *Wyższa wartość (np. 1440 dla 24 godzin):* Strony są serwowane z pamięci podręcznej dłużej, zmniejszając obciążenie serwera, ale potencjalnie pokazując nieco nieaktualną zawartość, jeśli często wprowadzasz zmiany (np. aktualizacje cen).
        -   *Niższa wartość (np. 60 dla 1 godziny):* Strony są przebudowywane częściej, zapewniając świeższą zawartość, ale nieco zwiększając obciążenie serwera.
    -   **Zalecana wartość:** Zacznij od **1440** (24 godziny). Dostosuj w zależności od tego, jak często zmieniają się dane Twoich produktów.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli codziennie aktualizujesz ceny lub opisy produktów, 24-godzinny czas życia jest w porządku. Jeśli prowadzisz błyskawiczne wyprzedaże ze zmianami cen co godzinę, możesz zmniejszyć tę wartość do 60 lub 120 minut, lub polegać na funkcjach automatycznej unieważniania.
-   **Metoda przechowywania pamięci podręcznej:**

    -   **Co robi to ustawienie:** Wybiera miejsce przechowywania buforowanych stron. Różne metody oferują różne poziomy wydajności i wymagają specyficznych konfiguracji serwera.
    -   **Efekt zmiany tego ustawienia:**
        -   *System plików (domyślnie):* Buforuje strony jako pliki na dysku serwera. Najłatwiejszy w konfiguracji, dobry dla większości sklepów.
        -   *Redis:* Przechowuje pamięć podręczną w pamięci za pomocą serwera Redis. Znacznie szybszy niż system plików, idealny dla sklepów o dużym ruchu. Wymaga zainstalowania i skonfigurowania Redis na Twoim serwerze.
        -   *Memcached:* Przechowuje pamięć podręczną w pamięci za pomocą serwera Memcached. Podobny do Redis pod względem korzyści wydajnościowych, również wymaga konfiguracji serwera.
    -   **Zalecana wartość:** Zacznij od **Systemu plików**. Jeśli masz sklep o dużym ruchu i Twój hosting to obsługuje, rozważ **Redis** lub **Memcached** dla maksymalnej wydajności.
    -   **Scenariusz / przykład dla sprzedawcy:** Twój sklep szybko rośnie i doświadczasz sporadycznych spowolnień. Twój host oferuje Redis. Przełączenie na Redis może znacznie poprawić wydajność.
-   **Wyklucz adresy URL z pamięci podręcznej:**

    -   **Co robi to ustawienie:** Pozwala określić konkretne strony lub sekcje Twojego sklepu, które *nigdy* nie powinny być buforowane. Jest to przydatne dla stron z bardzo dynamiczną lub wrażliwą zawartością.
    -   **Efekt zmiany tego ustawienia:**
        -   *Dodanie adresów URL:* Te strony będą zawsze generowane na nowo przez PrestaShop, zapewniając, że ich zawartość jest zawsze aktualna, ale poświęcając szybkość dla tych konkretnych stron.
        -   *Pozostawienie pustego:* Wszystkie kwalifikujące się strony zostaną buforowane.
    -   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne potrzeby. Używaj z ostrożnością.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz niestandardową stronę „Zapytanie o wycenę”, która generuje unikalne formularze na podstawie danych wejściowych użytkownika, lub stronę z aktualizacjami stanów magazynowych w czasie rzeczywistym z zewnętrznego API. Dodałbyś `/module/yourmodule/quotepage` lub `/stock-updates` do tej listy.
-   **Rozgrzewka pamięci podręcznej:**

    -   **Co robi to ustawienie:** Automatycznie „odwiedza” strony Twojego sklepu w tle, aby wstępnie wypełnić pamięć podręczną, zapewniając, że nawet pierwszy odwiedzający stronę doświadczy korzyści związanych z szybkością.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Twoja pamięć podręczna zostanie proaktywnie wypełniona, co prowadzi do szybszego ładowania dla wszystkich odwiedzających, nawet tych, którzy odwiedzają stronę po raz pierwszy po unieważnieniu pamięci podręcznej. Może to nieznacznie zwiększyć obciążenie serwera podczas procesu rozgrzewki.
        -   *Gdy wyłączone:* Strony będą buforowane dopiero po pierwszej wizycie klienta.
    -   **Zalecana wartość:** **TAK**. Zapewnia to maksymalne korzyści z szybkości dla wszystkich użytkowników.
    -   **Scenariusz / przykład dla sprzedawcy:** Właśnie wyczyściłeś pamięć podręczną lub zaktualizowałeś wiele produktów. Włączenie rozgrzewki zapewni, że Twój sklep będzie natychmiast szybki dla klientów, zamiast czekać, aż odwiedzą każdą stronę.
-   **Optymalizacja HTML:**

    -   **Co robi to ustawienie:** Minimalizuje wyjście HTML Twoich stron poprzez usunięcie niepotrzebnych spacji, komentarzy i łamania wierszy. Zmniejsza to rozmiar pliku strony, co prowadzi do szybszego pobierania.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Kod HTML Twojej strony będzie bardziej kompaktowy, zmniejszając zużycie przepustowości i nieznacznie przyspieszając renderowanie strony. Jest to ogólnie bezpieczne.
        -   *Gdy wyłączone:* HTML będzie serwowany tak, jak został wygenerowany przez PrestaShop, bez minifikacji.
    -   **Zalecana wartość:** **TAK**. Jest to proste, bezpieczne zwiększenie wydajności.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz wycisnąć każdą odrobinę wydajności ze swojego sklepu. Włączenie tego sprawi, że Twój HTML będzie bardziej zwięzły.

#### Zakładka Bloki dynamiczne

Ta sekcja pozwala zdefiniować części strony, które *nie* powinny być buforowane, ale zamiast tego ładowane dynamicznie po załadowaniu głównej strony. Jest to kluczowe dla spersonalizowanej zawartości, takiej jak koszyk, status logowania lub wyjścia konkretnych modułów.

-   **Włącz bloki dynamiczne:**

    -   **Co robi to ustawienie:** Aktywuje możliwość definiowania konkretnych obszarów Twojej strony, które będą ładowane oddzielnie i dynamicznie, nawet gdy reszta strony jest serwowana z pamięci podręcznej.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Możesz skonfigurować konkretne moduły lub obszary treści, aby pozostały dynamiczne, zapewniając, że spersonalizowana zawartość jest zawsze świeża.
        -   *Gdy wyłączone:* Cała zawartość zostanie buforowana, co potencjalnie prowadzi do nieaktualnej zawartości dynamicznej (np. wyświetlanie pustego koszyka, nawet jeśli dodano produkty).
    -   **Zalecana wartość:** **TAK**. Jest to niezbędne dla funkcjonalnego sklepu z buforowaniem.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby koszyk Twojego klienta zawsze pokazywał prawidłową liczbę produktów, nawet jeśli sama strona produktu jest buforowana.
-   **Lista modułów dynamicznych:**

    -   **Co robi to ustawienie:** Jest to lista, na której wybierasz, które moduły powinny *zawsze* być renderowane dynamicznie, nawet jeśli są podpięte do buforowanej strony.
    -   **Efekt zmiany tego ustawienia:**
        -   *Dodanie modułu:* Wyjście tego modułu będzie pobierane na nowo dla każdego użytkownika, zapewniając, że jego zawartość jest zawsze aktualna (np. blok koszyka, blok informacji o użytkowniku).
        -   *Usunięcie modułu:* Wyjście modułu zostanie buforowane wraz z resztą strony, potencjalnie pokazując nieaktualne dane.
    -   **Zalecana wartość:** Uwzględnij moduły takie jak `ps_shoppingcart`, `ps_customeraccountlinks`, `ps_languageselector`, `ps_currencyselector` i wszelkie inne moduły, które wyświetlają informacje specyficzne dla użytkownika lub w czasie rzeczywistym.
    -   **Scenariusz / przykład dla sprzedawcy:** Instalujesz nowy moduł „Czat na żywo”, który musi wyświetlać dostępność w czasie rzeczywistym. Dodałbyś go do tej listy, aby upewnić się, że jest zawsze dynamiczny.

#### Zakładka Unieważnianie i czyszczenie

Ta sekcja zarządza sposobem i czasem czyszczenia lub aktualizowania pamięci podręcznej, zapewniając, że Twoi klienci zawsze widzą najnowsze informacje o produktach.

-   **Automatyczne unieważnianie pamięci podręcznej:**

    -   **Co robi to ustawienie:** Gdy włączone, moduł automatycznie czyści odpowiednie buforowane strony, gdy wprowadzasz zmiany w panelu administracyjnym PrestaShop (np. aktualizujesz produkt, kategorię lub stronę CMS).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Nie musisz ręcznie czyścić pamięci podręcznej po każdej zmianie. Moduł inteligentnie czyści tylko zmienione strony, zapewniając, że klienci szybko widzą aktualizacje.
        -   *Gdy wyłączone:* Musiałbyś ręcznie czyścić całą pamięć podręczną po każdej znaczącej zmianie, w przeciwnym razie klienci mogą widzieć nieaktualną zawartość, dopóki czas życia pamięci podręcznej nie wygaśnie.
    -   **Zalecana wartość:** **TAK**. Jest to kluczowa funkcja „ustaw i zapomnij” dla świeżości danych.
    -   **Scenariusz / przykład dla sprzedawcy:** Aktualizujesz cenę produktu. Dzięki automatycznemu unieważnianiu, buforowana wersja tej strony produktu (i potencjalnie jej stron kategorii) jest czyszczona, więc klienci natychmiast widzą nową cenę.
-   **Wyczyść pamięć podręczną przy aktualizacji produktu:**

    -   **Co robi to ustawienie:** Specjalnie kontroluje, czy pamięć podręczna związana z produktem jest czyszczona, gdy ten produkt jest aktualizowany.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Zapewnia, że każda strona wyświetlająca zaktualizowany produkt (strona produktu, strona kategorii, wyniki wyszukiwania) jest odświeżana w pamięci podręcznej.
        -   *Gdy wyłączone:* Aktualizacje produktów mogą nie być widoczne na buforowanych stronach, dopóki czas życia pamięci podręcznej nie wygaśnie lub nie wyczyścisz jej ręcznie.
    -   **Zalecana wartość:** **TAK**. Niezbędne dla dokładnych informacji o produkcie.
    -   **Scenariusz / przykład dla sprzedawcy:** Zmieniasz obraz produktu. To ustawienie zapewnia, że nowy obraz natychmiast pojawi się na stronie produktu.
-   **Wyczyść pamięć podręczną przy aktualizacji kategorii:**

    -   **Co robi to ustawienie:** Kontroluje, czy pamięć podręczna związana z kategorią jest czyszczona, gdy ta kategoria jest aktualizowana.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Zapewnia, że strony kategorii i potencjalnie strony produktów w tej kategorii są odświeżane.
        -   *Gdy wyłączone:* Aktualizacje kategorii (np. nazwa, opis, przypisane produkty) mogą nie być widoczne na buforowanych stronach.
    -   **Zalecana wartość:** **TAK**. Ważne dla nawigacji i dokładności treści kategorii.
    -   **Scenariusz / przykład dla sprzedawcy:** Zmieniasz nazwę kategorii. To zapewnia, że nowa nazwa pojawi się w Twojej nawigacji i na stronie kategorii.
-   **Wyczyść pamięć podręczną przy aktualizacji strony CMS:**

    -   **Co robi to ustawienie:** Kontroluje, czy pamięć podręczna związana ze stroną CMS jest czyszczona, gdy ta strona jest aktualizowana.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Zapewnia, że zaktualizowane strony CMS (np. „O nas”, „Warunki i zasady”) są natychmiast odświeżane.
        -   *Gdy wyłączone:* Aktualizacje stron CMS mogą nie być widoczne dla klientów, dopóki pamięć podręczna nie wygaśnie.
    -   **Zalecana wartość:** **TAK**. Ważne dla dokładności treści statycznych.
    -   **Scenariusz / przykład dla sprzedawcy:** Aktualizujesz stronę „Polityka wysyłki”. To zapewnia, że klienci widzą najnowszą wersję.

#### Zakładka Ustawienia zaawansowane

-   **Włącz tryb debugowania:**

    -   **Co robi to ustawienie:** Aktywuje specjalny tryb, który wyświetla informacje o statusie pamięci podręcznej bezpośrednio na stronach Twojego front-office (widoczne tylko dla Ciebie jako administratora).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Zobaczysz małą nakładkę na stronach Twojego sklepu wskazującą, czy strona została serwowana z pamięci podręcznej, kiedy została buforowana i inne szczegóły diagnostyczne. Jest to nieocenione przy rozwiązywaniu problemów.
        -   *Gdy wyłączone:* Nie są wyświetlane żadne informacje debugowania.
    -   **Zalecana wartość:** **NIE** dla działających sklepów produkcyjnych. **TAK** podczas konfiguracji lub rozwiązywania problemów.
    -   **Scenariusz / przykład dla sprzedawcy:** Właśnie skonfigurowałeś moduł i chcesz sprawdzić, czy strony są rzeczywiście poprawnie buforowane. Włącz tryb debugowania, przeglądaj swój sklep i sprawdź nakładkę.
-   **Włącz debugowanie na żywo:**

    -   **Co robi to ustawienie:** Zapewnia pulpit nawigacyjny w czasie rzeczywistym w panelu administracyjnym do monitorowania trafień, pomyłek pamięci podręcznej i innych metryk wydajności.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Uzyskujesz dostęp do potężnego narzędzia monitorowania, aby zobaczyć, jak skutecznie działa Twoja pamięć podręczna.
        -   *Gdy wyłączone:* Nie są zbierane ani wyświetlane żadne statystyki pamięci podręcznej na żywo.
    -   **Zalecana wartość:** **TAK**, jeśli chcesz aktywnie monitorować wydajność. Można wyłączyć, jeśli preferujesz minimalne obciążenie.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz zobaczyć wpływ swojej strategii buforowania w czasie, obserwując, ile żądań jest serwowanych z pamięci podręcznej w porównaniu do generowanych na nowo.
-   **Włącz SWR (Stale-While-Revalidate):**

    -   **Co robi to ustawienie:** Zaawansowana strategia buforowania, w której, jeśli buforowana strona wygasła, moduł natychmiast serwuje użytkownikowi *nieaktualną* (wygasłą) wersję, jednocześnie odbudowując świeżą wersję w tle.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Użytkownicy prawie zawsze otrzymują natychmiastowe ładowanie strony, nawet jeśli pamięć podręczna wygasła. Strona może być przez chwilę nieco nieaktualna, ale jest niesamowicie szybka. Świeża wersja zastępuje nieaktualną dla kolejnych odwiedzających.
        -   *Gdy wyłączone:* Gdy buforowana strona wygaśnie, następny odwiedzający będzie czekał na przebudowanie strony, co może spowodować niewielkie opóźnienie.
    -   **Zalecana wartość:** **TAK**. Oferuje to najlepszą równowagę szybkości i świeżości dla większości sklepów.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz mieć pewność, że Twoi klienci nigdy nie doświadczą wolnego ładowania, nawet jeśli pamięć podręczna wymaga aktualizacji. SWR zapewnia to „zawsze szybkie” doświadczenie.
-   **Pamięć podręczna dla zalogowanych użytkowników:**

    -   **Co robi to ustawienie:** Określa, czy strony powinny być buforowane nawet dla klientów, którzy są zalogowani na swoje konta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Zalogowani użytkownicy również skorzystają z buforowanych stron, ale moduł musi być bardzo inteligentny w kwestii bloków dynamicznych, aby zapewnić, że spersonalizowana zawartość (takie jak linki „Moje konto”, historia zamówień) pozostaje poprawna.
        -   *Gdy wyłączone:* Zalogowani użytkownicy zawsze otrzymają świeże, niebuforowane strony. Zapewnia to doskonałą personalizację, ale poświęca szybkość dla tych użytkowników.
    -   **Zalecana wartość:** **TAK**, ale upewnij się, że Twoje bloki dynamiczne są poprawnie skonfigurowane dla modułów takich jak `ps_customeraccountlinks`.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby Twoi powracający, zalogowani klienci również cieszyli się superszybkim doświadczeniem, a nie tylko goście.
-   **Pamięć podręczna dla urządzeń mobilnych:**

    -   **Co robi to ustawienie:** Kontroluje, czy oddzielne buforowane wersje stron są generowane i serwowane dla urządzeń mobilnych.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł utworzy i będzie serwował zoptymalizowane buforowane strony specjalnie dla użytkowników mobilnych, co jest kluczowe, jeśli Twój motyw ma znaczące różnice między układami dla komputerów stacjonarnych i mobilnych.
        -   *Gdy wyłączone:* Użytkownicy mobilni otrzymają buforowaną wersję dla komputerów stacjonarnych (jeśli dotyczy) lub niebuforowane strony, co potencjalnie prowadzi do wolniejszego lub niepoprawnie renderowanego treści.
    -   **Zalecana wartość:** **TAK**, jeśli Twój motyw jest responsywny i renderuje się inaczej dla urządzeń mobilnych.
    -   **Scenariusz / przykład dla sprzedawcy:** Twój motyw używa różnych szablonów lub CSS dla urządzeń mobilnych. Buforowanie dla urządzeń mobilnych zapewnia, że otrzymają poprawną, szybką wersję.
-   **Włącz czyszczenie krawędzi (Varnish/CDN):**

    -   **Co robi to ustawienie:** Integruje się z zewnętrznymi systemami buforowania, takimi jak Varnish lub sieci dostarczania treści (CDN), aby wysyłać żądania czyszczenia, gdy pamięć podręczna PrestaShop jest unieważniana. Zapewnia to, że CDN również czyści swoją starą zawartość.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Twój CDN zawsze będzie serwował najświeższą zawartość po wprowadzeniu aktualizacji, zapobiegając wyświetlaniu klientom starych wersji przechowywanych przez CDN.
        -   *Gdy wyłączone:* Twój CDN może nadal serwować starą zawartość nawet po wyczyszczeniu pamięci podręcznej PrestaShop, co prowadzi do niespójności.
    -   **Zalecana wartość:** **TAK**, jeśli używasz Varnish lub CDN (takiego jak Cloudflare, Akamai itp.), który obsługuje czyszczenie pamięci podręcznej za pośrednictwem API.
    -   **Scenariusz / przykład dla sprzedawcy:** Używasz Cloudflare dla wydajności. Kiedy aktualizujesz produkt, to ustawienie informuje Cloudflare, aby wyczyścił swoją pamięć podręczną dla tego produktu, dzięki czemu wszyscy użytkownicy natychmiast widzą aktualizację.

#### Zakładka Narzędzia

Ta zakładka zawiera ręczne działania do zarządzania pamięcią podręczną.

-   **Wyczyść całą pamięć podręczną:**

    -   **Co robi to ustawienie:** Ten przycisk natychmiast usuwa wszystkie buforowane strony wygenerowane przez Presta Speed Cache.
    -   **Efekt zmiany tego ustawienia:** Cała buforowana zawartość zostaje usunięta. Następnym razem, gdy strona zostanie odwiedzona, zostanie wygenerowana na nowo przez PrestaShop, a następnie ponownie buforowana. Spowoduje to tymczasowe spowolnienie Twojej witryny, dopóki pamięć podręczna się nie odbuduje.
    -   **Zalecana wartość:** Używaj tylko wtedy, gdy jest to konieczne (np. po dużej aktualizacji motywu, instalacji modułu lub jeśli podejrzewasz problemy z pamięcią podręczną).
    -   **Scenariusz / przykład dla sprzedawcy:** Wprowadziłeś obszerne zmiany w CSS swojego motywu i chcesz mieć pewność, że wszyscy odwiedzający natychmiast zobaczą nowy projekt. Kliknij „Wyczyść całą pamięć podręczną”.
-   **Uruchom rozgrzewkę pamięci podręcznej:**

    -   **Co robi to ustawienie:** Ręcznie uruchamia proces rozgrzewki pamięci podręcznej, który odwiedza strony Twojego sklepu, aby wstępnie wypełnić pamięć podręczną.
    -   **Efekt zmiany tego ustawienia:** Moduł zacznie generować buforowane wersje Twoich stron w tle. Może to zająć trochę czasu w zależności od rozmiaru Twojego sklepu i może zużywać zasoby serwera podczas tego procesu.
    -   **Zalecana wartość:** Użyj po wyczyszczeniu pamięci podręcznej lub po dużych importach produktów/kategorii, aby szybko odbudować pamięć podręczną.
    -   **Scenariusz / przykład dla sprzedawcy:** Właśnie wyczyściłeś pamięć podręczną i chcesz, aby Twój sklep był jak najszybszy dla klientów.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 Zarządzanie pamięcią podręczną (Panel administracyjny > Presta Speed Cache > Zarządzanie pamięcią podręczną)

Ten ekran zapewnia szczegółowy przegląd i interfejs zarządzania dla Twoich buforowanych stron.

-   **Nazwa ekranu i lokalizacja w menu:** Możesz to znaleźć, przechodząc do **Presta Speed Cache** w głównym menu panelu administracyjnego PrestaShop, a następnie wybierając **Zarządzanie pamięcią podręczną**.
-   **Dostępne działania i ustawienia:**
    -   **Siatka listy pamięci podręcznej:** Ta tabela wyświetla listę aktualnie buforowanych stron, w tym szczegóły, takie jak adres URL, kiedy ostatnio została buforowana, jej rozmiar i aktualny status (np. aktywna, wygasła).
    -   **Filtrowanie i wyszukiwanie:** Możesz filtrować listę według adresu URL, statusu lub innych kryteriów, aby znaleźć konkretne wpisy w pamięci podręcznej.
    -   **Wyczyść wybraną pamięć podręczną:** Pozwala wybrać konkretne buforowane strony z listy i wyczyścić je indywidualnie.
    -   **Wyczyść całą pamięć podręczną (przycisk):** Widoczny przycisk do czyszczenia całej pamięci podręcznej, podobny do tego na głównej stronie konfiguracji.
    -   **Uruchom rozgrzewkę (przycisk):** Widoczny przycisk do ręcznego inicjowania procesu rozgrzewki pamięci podręcznej.
-   **Efekt zmian:**
    -   *Czyszczenie pojedynczych wpisów:* Tylko wybrane strony zostaną usunięte z pamięci podręcznej, co pozwoli na ich odbudowanie przy następnej wizycie. Jest to przydatne do ukierunkowanych aktualizacji bez wpływu na cały sklep.
    -   *Czyszczenie całej pamięci podręcznej:* Resetuje całą pamięć podręczną, wymuszając odbudowanie wszystkich stron.
    -   *Uruchamianie rozgrzewki:* Proaktywnie wypełnia pamięć podręczną, zapewniając szybsze ładowanie dla kolejnych odwiedzających.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Używaj tego ekranu do monitorowania pamięci podręcznej, identyfikowania stron, które mogą nie być poprawnie buforowane, lub do przeprowadzania ukierunkowanych czyszczeń pamięci podręcznej, jeśli wprowadziłeś bardzo specyficzną aktualizację, której automatyczne unieważnianie mogło nie objąć.

#### 2.2.2 Pulpit nawigacyjny (Panel administracyjny > Presta Speed Cache > Pulpit nawigacyjny)

Ten ekran zapewnia wizualny przegląd wydajności i statystyk pamięci podręcznej.

-   **Nazwa ekranu i lokalizacja w menu:** Możesz to znaleźć, przechodząc do **Presta Speed Cache** w głównym menu panelu administracyjnego PrestaShop, a następnie wybierając **Pulpit nawigacyjny**.
-   **Dostępne działania i ustawienia:**
    -   **Metryki wydajności:** Wyświetla wykresy i statystyki dotyczące trafień w pamięci podręcznej, pomyłek pamięci podręcznej, średnich czasów ładowania stron (z pamięcią podręczną i bez) oraz innych istotnych wskaźników wydajności.
    -   **Status kondycji pamięci podręcznej:** Zapewnia szybki przegląd kondycji systemu pamięci podręcznej, wskazując, czy występują jakieś problemy lub czy działa optymalnie.
    -   **Ostatnie zdarzenia unieważniania:** Pokazuje dziennik ostatnich unieważnień pamięci podręcznej, pomagając śledzić, kiedy i dlaczego części pamięci podręcznej zostały wyczyszczone.
-   **Efekt zmian:** Ten ekran służy głównie do monitorowania i raportowania. Nie wprowadza się tu bezpośrednich zmian w konfiguracji pamięci podręcznej, ale pomaga zrozumieć wpływ Twoich ustawień.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie sprawdzaj pulpit nawigacyjny, aby upewnić się, że pamięć podręczna działa zgodnie z oczekiwaniami. Szukaj wysokich współczynników trafień w pamięci podręcznej i niskich czasów ładowania. Jeśli zauważysz nagły spadek trafień w pamięci podręcznej lub wzrost czasów ładowania, może to wskazywać na problem z konfiguracją lub problem z Twoim serwerem.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz pamięć podręczną | TAK | Główny przełącznik dla buforowania. TAK = szybszy sklep. |
| | Czas życia pamięci podręcznej (minuty) | 1440 (24 godziny) | Jak długo strona pozostaje w pamięci podręcznej. Wyższa = mniejsze obciążenie serwera, potencjalnie starsza zawartość. |
| | Metoda przechowywania pamięci podręcznej | System plików | Gdzie przechowywana jest pamięć podręczna. System plików (łatwy), Redis/Memcached (szybszy, wymaga konfiguracji serwera). |
| | Wyklucz adresy URL z pamięci podręcznej | Puste | Adresy URL, które nigdy nie powinny być buforowane (np. bardzo dynamiczne strony). |
| | Rozgrzewka pamięci podręcznej | TAK | Proaktywnie buduje pamięć podręczną w tle. TAK = szybsze dla pierwszych odwiedzających. |
| | Optymalizacja HTML | TAK | Minimalizuje HTML dla mniejszych rozmiarów stron. TAK = niewielkie przyspieszenie. |
| | Włącz bloki dynamiczne | TAK | Pozwala na dynamiczne pozostawanie określonych treści (koszyk, logowanie). TAK = niezbędne dla spersonalizowanej zawartości. |
| | Lista modułów dynamicznych | `ps_shoppingcart`, `ps_customeraccountlinks`, itp. | Moduły, które zawsze powinny być dynamiczne. |
| | Automatyczne unieważnianie pamięci podręcznej | TAK | Czyści odpowiednią pamięć podręczną przy zmianach w panelu administracyjnym. TAK = świeża zawartość bez ręcznej interwencji. |
| | Wyczyść pamięć podręczną przy aktualizacji produktu | TAK | Czyści pamięć podręczną związaną z produktem, gdy produkty są aktualizowane. |
| | Wyczyść pamięć podręczną przy aktualizacji kategorii | TAK | Czyści pamięć podręczną związaną z kategorią, gdy kategorie są aktualizowane. |
| | Wyczyść pamięć podręczną przy aktualizacji strony CMS | TAK | Czyści pamięć podręczną związaną ze stroną CMS, gdy strony CMS są aktualizowane. |
| | Włącz tryb debugowania | NIE (TAK do rozwiązywania problemów) | Pokazuje informacje o pamięci podręcznej na front office. |
| | Włącz debugowanie na żywo | TAK | Zapewnia statystyki pamięci podręcznej w czasie rzeczywistym w BO. |
| | Włącz SWR (Stale-While-Revalidate) | TAK | Serwuje nieaktualną pamięć podręczną podczas odbudowywania świeżej. TAK = zawsze szybko. |
| | Pamięć podręczna dla zalogowanych użytkowników | TAK | Buforuje strony dla zalogowanych użytkowników. |
| | Pamięć podręczna dla urządzeń mobilnych | TAK | Buforuje oddzielne wersje dla urządzeń mobilnych. |
| | Włącz czyszczenie krawędzi (Varnish/CDN) | NIE (TAK, jeśli używasz CDN) | Integruje się z zewnętrznym CDN/Varnish do czyszczenia pamięci podręcznej. |
| | Wyczyść całą pamięć podręczną (przycisk) | Użyj w razie potrzeby | Ręcznie czyści całą pamięć podręczną. |
| | Uruchom rozgrzewkę pamięci podręcznej (przycisk) | Użyj w razie potrzeby | Ręcznie uruchamia wstępne wypełnianie pamięci podręcznej. |
| **Ekran zarządzania pamięcią podręczną** | Siatka listy pamięci podręcznej | N/A | Wyświetla i pozwala zarządzać poszczególnymi buforowanymi stronami. |
| | Wyczyść wybraną pamięć podręczną | N/A | Czyści określone wpisy w pamięci podręcznej. |
| **Ekran pulpitu nawigacyjnego** | Metryki wydajności | N/A | Wizualizuje trafienia, pomyłki i czasy ładowania pamięci podręcznej. |
| | Status kondycji pamięci podręcznej | N/A | Pokazuje ogólny stan systemu buforowania. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Mój sklep wygląda na uszkodzony lub wyświetla starą zawartość po włączeniu pamięci podręcznej. Co powinienem zrobić?**
O: Najpierw spróbuj wyczyścić całą pamięć podręczną za pomocą przycisku „Wyczyść całą pamięć podręczną” w konfiguracji modułu lub na ekranie „Zarządzanie pamięcią podręczną”. Wyczyść również pamięć podręczną przeglądarki. Jeśli problem nadal występuje, sprawdź „Listę modułów dynamicznych”, aby upewnić się, że wszystkie moduły wyświetlające spersonalizowaną zawartość lub zawartość w czasie rzeczywistym są uwzględnione. Tymczasowo wyłącz „Optymalizację HTML”, aby sprawdzić, czy nie powoduje ona konfliktów.

**P: Mój koszyk nie aktualizuje się poprawnie, lub użytkownicy czasami wydają się wylogowani.**
O: Jest to prawie zawsze spowodowane tym, że zawartość dynamiczna nie jest prawidłowo wykluczona z buforowania. Przejdź do zakładki „Bloki dynamiczne” i upewnij się, że moduły takie jak `ps_shoppingcart`, `ps_customeraccountlinks`, `ps_languageselector` i `ps_currencyselector` są dodane do „Listy modułów dynamicznych”. Jeśli masz inne niestandardowe moduły, które wyświetlają dane specyficzne dla użytkownika, dodaj je również.

**P: Moja witryna nadal jest wolna, nawet po włączeniu modułu.**
O:

1.  **Sprawdź tryb debugowania:** Włącz „Tryb debugowania” (w Ustawieniach zaawansowanych) i przeglądaj swój front office. Czy pokazuje, że strony są serwowane z pamięci podręcznej („Cache HIT”)? Jeśli widzisz „Cache MISS”, strony nie są buforowane.
2.  **Zweryfikuj współczynnik trafień w pamięci podręcznej:** Sprawdź „Pulpit nawigacyjny” pod kątem współczynnika trafień w pamięci podręcznej. Jeśli jest niski, przejrzyj ustawienia „Czas życia pamięci podręcznej” i „Wyklucz adresy URL”.
3.  **Zasoby serwera:** Chociaż buforowanie zmniejsza obciążenie, Twój serwer nadal potrzebuje odpowiednich zasobów. Sprawdź swój plan hostingowy i logi serwera pod kątem innych wąskich gardeł.
4.  **Inne optymalizacje:** Buforowanie to tylko jedna część szybkości. Upewnij się, że Twoje obrazy są zoptymalizowane, Twój motyw jest wydajny i nie uruchamiasz zbyt wielu ciężkich, niezoptymalizowanych modułów.

**P: Jak upewnić się, że mój sklep wielojęzyczny lub wielowalutowy działa poprawnie z buforowaniem?**
O: Presta Speed Cache jest zaprojektowany do obsługi sklepów wielojęzycznych i wielowalutowych poprzez generowanie oddzielnych wpisów w pamięci podręcznej dla każdej kombinacji. Upewnij się, że moduły selektora języka i waluty są dodane do „Listy modułów dynamicznych”. Jeśli zauważysz problemy, włącz „Pamięć podręczną dla zalogowanych użytkowników” i „Pamięć podręczną dla urządzeń mobilnych”, jeśli dotyczy, ponieważ mogą one również wpływać na sposób buforowania różnych wersji stron.

**P: Zaktualizowałem produkt, ale stare informacje nadal są wyświetlane na front office.**
O:

1.  **Automatyczne unieważnianie:** Upewnij się, że „Automatyczne unieważnianie pamięci podręcznej” i „Wyczyść pamięć podręczną przy aktualizacji produktu” są włączone w zakładce „Unieważnianie i czyszczenie”.
2.  **Ręczne czyszczenie:** Jeśli ustawienia są poprawne, spróbuj ręcznie wyczyścić pamięć podręczną dla tej konkretnej strony produktu z ekranu „Zarządzanie pamięcią podręczną” lub wyczyść całą pamięć podręczną.
3.  **CDN/Varnish:** Jeśli używasz CDN lub Varnish, upewnij się, że „Włącz czyszczenie krawędzi” jest poprawnie skonfigurowane, ponieważ Twój CDN może serwować starą wersję.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Presta Speed Cache to wysoce zoptymalizowane rozwiązanie buforowania dla PrestaShop, wykorzystujące zaawansowaną architekturę do zapewnienia szybkości bez kompromisów w zakresie zawartości dynamicznej. Wykorzystuje wzorzec MVC PrestaShop, nadpisując klasy rdzenia (`Controller`, `FrontController`, `Dispatcher`, `Hook`), aby przechwytywać żądania i odpowiedzi, serwując buforowany HTML, gdy jest dostępny. Wykorzystuje elastyczny silnik przechowywania (Plik, Redis, Memcached) i implementuje zaawansowane funkcje, takie jak SWR (Stale-While-Revalidate), dynamiczne renderowanie bloków za pośrednictwem AJAX i inteligentne unieważnianie pamięci podręcznej. Projekt modułu koncentruje się na minimalnym narzucie i maksymalnej kompatybilności, zapewniając solidną i rozszerzalną warstwę buforowania.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery obsługują specyficzne żądania AJAX lub zadania w tle związane z buforowaniem.

-   `prestaspeedcache/controllers/front/api.php`
    -   **Nazwa klasy i klasa nadrzędna:** `PrestaSpeedCacheApiModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Obsługuje żądania API, głównie do pobierania zawartości dynamicznej. Gdy buforowana strona jest serwowana i zawiera bloki dynamiczne, ten kontroler jest odpowiedzialny za dostarczanie świeżego HTML dla tych bloków za pośrednictwem AJAX. Otrzymuje parametry identyfikujące moduł i hook, renderuje moduł i zwraca HTML.
-   `prestaspeedcache/controllers/front/cron.php`
    -   **Nazwa klasy i klasa nadrzędna:** `PrestaSpeedCacheCronModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Zaprojektowany do wywoływania przez zadanie cron po stronie serwera. Uruchamia zadania w tle, takie jak rozgrzewka pamięci podręcznej, przetwarzanie kolejki unieważniania i inne operacje konserwacyjne. Odciąża to ciężkie przetwarzanie z żądań użytkowników.
-   `prestaspeedcache/controllers/front/dynamic.php`
    -   **Nazwa klasy i klasa nadrzędna:** `PrestaSpeedCacheDynamicModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Podobnie jak `api.php`, ten kontroler specjalnie obsługuje żądania dotyczące dynamicznych bloków treści, które są ładowane asynchronicznie na buforowanych stronach. Zapewnia, że spersonalizowane elementy, takie jak koszyk lub informacje o użytkowniku, są zawsze aktualne.
-   `prestaspeedcache/controllers/front/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `PrestaSpeedCacheIndexModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Kontroler frontowy zastępczy lub awaryjny. W wielu modułach `index.php` w `controllers/front` służy jako domyślny punkt wejścia, jeśli żaden inny konkretny kontroler nie zostanie dopasowany. Może obsługiwać podstawowe routowanie na poziomie modułu lub po prostu przekierowywać.

#### Kontrolery administracyjne Back-Office

Te kontrolery zarządzają konfiguracją i danymi modułu w panelu administracyjnym PrestaShop.

-   `prestaspeedcache/controllers/admin/AdminPrestaSpeedCacheController.php`
    -   **Nazwa klasy i klasa nadrzędna:** `AdminPrestaSpeedCacheController` rozszerza `ModuleAdminController`.
    -   **Nazwa zakładki i zarządzana encja:** Jest to główny kontroler administracyjny modułu, zarządzający wpisami pamięci podręcznej i udostępniający widoki „Zarządzanie pamięcią podręczną” i „Pulpit nawigacyjny”. Obsługuje listowanie, filtrowanie i usuwanie wpisów pamięci podręcznej. Nie zarządza bezpośrednio konkretną encją `ObjectModel`, ale raczej wchodzi w interakcje z `PscCacheRepository` w celu operacji na pamięci podręcznej.
-   `prestaspeedcache/controllers/admin/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `AdminPrestaSpeedCacheIndexController` rozszerza `ModuleAdminController`.
    -   **Nazwa zakładki i zarządzana encja:** Podobnie jak `index.php` w front-office, jest to prawdopodobnie kontroler zastępczy lub domyślny dla sekcji administracyjnej modułu, zapewniający prawidłowy punkt wejścia, jeśli nie zażądano żadnej konkretnej akcji.

### 4.3 Klasy rdzenia i modele (`classes/`)

Katalog `classes/` modułu zawiera podstawową logikę, usługi i struktury danych.

-   `prestaspeedcache/classes/PscAdminChips.php`: Zarządza komponentami interfejsu użytkownika dla interfejsu administracyjnego.
-   `prestaspeedcache/classes/PscAfterDefaults.php`: Obsługuje domyślne ustawienia lub konfiguracje po instalacji.
-   `prestaspeedcache/classes/PscAutoload.php`: Niestandardowy autoloader dla klas modułu.
-   `prestaspeedcache/classes/PscCacheEngine.php`: Główny silnik buforowania, orkiestrujący operacje na pamięci podręcznej.
-   `prestaspeedcache/classes/PscCacheInvalidator.php`: Zarządza logiką unieważniania buforowanych stron na podstawie działań w panelu administracyjnym.
-   `prestaspeedcache/classes/PscCacheKey.php`: Generuje unikalne klucze dla buforowanych wpisów na podstawie adresu URL, kontekstu itp.
-   `prestaspeedcache/classes/PscCacheLock.php`: Implementuje mechanizmy blokowania, aby zapobiec warunkom wyścigu podczas generowania pamięci podręcznej.
-   `prestaspeedcache/classes/PscCacheRepository.php`: Zarządza interakcją z magazynem pamięci podręcznej, zapewniając warstwę abstrakcji.
-   `prestaspeedcache/classes/PscCacheStorage.php`: Abstrakcyjna klasa bazowa lub interfejs dla implementacji magazynów pamięci podręcznej.
-   `prestaspeedcache/classes/PscCacheTags.php`: Zarządza tagami pamięci podręcznej dla granularnego unieważniania (np. wszystkie strony związane z ID produktu 123).
-   `prestaspeedcache/classes/PscConfig.php`: Obsługuje ustawienia konfiguracji modułu (odczytuje i zapisuje do `ps_configuration`).
-   `prestaspeedcache/classes/PscDynamicBlocks.php`: Logika do identyfikowania i obsługi dynamicznych bloków treści.
-   `prestaspeedcache/classes/PscDynamicModules.php`: Zarządza listą modułów, których wyjście powinno być zawsze dynamiczne.
-   `prestaspeedcache/classes/PscEdgePurge.php`: Obsługuje integrację z zewnętrznymi systemami buforowania (Varnish, CDN) w celu czyszczenia.
-   `prestaspeedcache/classes/PscFrontAssign.php`: Zarządza przypisaniami zmiennych Smarty dla szablonów front-office.
-   `prestaspeedcache/classes/PscFrontDebug.php`: Logika do wyświetlania informacji debugowania na front office.
-   `prestaspeedcache/classes/PscHealth.php`: Udostępnia metody sprawdzania kondycji i statusu systemu buforowania.
-   `prestaspeedcache/classes/PscHtmlOptimizer.php`: Implementuje logikę minifikacji HTML.
-   `prestaspeedcache/classes/PscHttpProbe.php`: Używany do wewnętrznych żądań HTTP, np. do rozgrzewki pamięci podręcznej.
-   `prestaspeedcache/classes/PscInstaller.php`: Obsługuje procedury instalacji i deinstalacji modułu (tabele bazy danych, hooki, domyślne konfiguracje).
-   `prestaspeedcache/classes/PscInvalidationQueue.php`: Zarządza kolejką stron do unieważnienia, często przetwarzaną przez crona.
-   `prestaspeedcache/classes/PscLiveDebug.php`: Zapewnia możliwości debugowania i monitorowania w czasie rzeczywistym.
-   `prestaspeedcache/classes/PscMetrics.php`: Zbieranie i raportowanie metryk wydajności dla pulpitu nawigacyjnego.
-   `prestaspeedcache/classes/PscOps.php`: Ogólne metody narzędziowe.
-   `prestaspeedcache/classes/PscPresets.php`: Zarządza predefiniowanymi konfiguracjami buforowania lub presetami.
-   `prestaspeedcache/classes/PscRequestGuard.php`: Chroni przed złośliwymi żądaniami lub zapewnia prawidłową obsługę żądań.
-   `prestaspeedcache/classes/PscTiming.php`: Narzędzie do mierzenia czasów wykonania.
-   `prestaspeedcache/classes/PscTranslate.php`: Obsługuje tłumaczenia modułu.
-   `prestaspeedcache/classes/PscWarmup.php`: Implementuje logikę rozgrzewki pamięci podręcznej.
-   `prestaspeedcache/classes/PscWizard.php`: Prowadzi użytkowników przez początkową konfigurację.
-   `prestaspeedcache/classes/storage/PscFileStorage.php`: Konkretna implementacja dla przechowywania pamięci podręcznej opartej na plikach.
-   `prestaspeedcache/classes/storage/PscMemcachedStorage.php`: Konkretna implementacja dla przechowywania pamięci podręcznej Memcached.
-   `prestaspeedcache/classes/storage/PscRedisStorage.php`: Konkretna implementacja dla przechowywania pamięci podręcznej Redis.
-   `prestaspeedcache/classes/storage/PscStorageFactory.php`: Wzorzec fabryki do tworzenia odpowiednich instancji magazynów pamięci podręcznej.
-   `prestaspeedcache/classes/storage/PscStorageInterface.php`: Interfejs definiujący metody dla implementacji magazynów pamięci podręcznej.

#### Nadpisania (Overrides)

Moduł wykorzystuje nadpisania do głębokiej integracji z podstawowym zachowaniem PrestaShop.

-   `prestaspeedcache/override/classes/controller/Controller.php`: Nadpisuje podstawową klasę `Controller`, umożliwiając modułowi przechwytywanie procesu renderowania zarówno dla front-office, jak i back-office, potencjalnie wstrzykując logikę buforowania lub znaczniki bloków dynamicznych.
-   `prestaspeedcache/override/classes/controller/FrontController.php`: Nadpisuje `FrontController`, aby specjalnie obsługiwać żądania stron front-office, umożliwiając modułowi serwowanie buforowanej zawartości lub przygotowywanie stron do buforowania.
-   `prestaspeedcache/override/classes/Dispatcher.php`: Nadpisuje `Dispatcher`, aby kontrolować sposób routowania i przetwarzania adresów URL, potencjalnie przekierowując do buforowanej zawartości lub wyzwalając generowanie pamięci podręcznej.
-   `prestaspeedcache/override/classes/Hook.php`: Nadpisuje klasę `Hook`, aby umożliwić dynamiczne renderowanie modułów na buforowanych stronach, zapewniając, że określone hooki są zawsze wykonywane na nowo.

### 4.4 Zasoby JavaScript (`views/js/`)

Te skrypty poprawiają doświadczenie użytkownika zarówno w front-office, jak i back-office.

-   `prestaspeedcache/views/js/admin.js`:
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Obsługuje interaktywne elementy w konfiguracji administracyjnej modułu, takie jak przełączanie zakładek, przesyłanie formularzy, wywołania AJAX do czyszczenia pamięci podręcznej, uruchamiania rozgrzewki i dynamicznych aktualizacji pulpitu nawigacyjnego lub listy pamięci podręcznej.
-   `prestaspeedcache/views/js/after/lang-currency.js`:
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Prawdopodobnie mały skrypt wykonywany po załadowaniu głównej strony, specjalnie zaprojektowany w celu zapewnienia, że selektory języka i waluty (które często są dynamiczne) działają poprawnie w kontekście buforowanej strony. Może ponownie inicjalizować ich zachowanie lub zapewniać spójność ich stanu.
-   `prestaspeedcache/views/js/dynamic.js`:
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Jest to krytyczny skrypt dla bloków dynamicznych. Identyfikuje symbole zastępcze dla zawartości dynamicznej na buforowanej stronie, wysyła żądania AJAX (do kontrolerów `api.php` lub `dynamic.php`) w celu pobrania świeżego HTML dla tych bloków, a następnie wstrzykuje zawartość z powrotem do DOM. Zapewnia, że elementy takie jak koszyk, status logowania itp. są zawsze aktualne.
-   `prestaspeedcache/views/js/fo_debug.js`:
    -   **Zakres:** Front-office (tylko dla administratora, gdy tryb debugowania jest włączony).
    -   **Szczegóły:** Wyświetla nakładkę debugowania pamięci podręcznej na front office. Pobiera informacje o statusie pamięci podręcznej (trafienie/pomyłka, znacznik czasu itp.) i renderuje je w widocznym, nieinwazyjnym elemencie dla administratorów.
-   `prestaspeedcache/views/js/psc-dom-mock.js`:
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Potencjalnie skrypt narzędziowy, który zapewnia lekką warstwę manipulacji lub mockowania DOM, prawdopodobnie używany podczas procesu wstrzykiwania bloków dynamicznych w celu zapewnienia kompatybilności lub optymalizacji renderowania.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `prestaspeedcache/views/css/admin.css`:
    -   **Zakres:** Stylizacja formularzy administracyjnych back-office.
    -   **Szczegóły:** Stylizuje strony konfiguracji modułu, pulpit nawigacyjny i siatki zarządzania pamięcią podręczną. Zapewnia spójny i przyjazny dla użytkownika interfejs w panelu administracyjnym PrestaShop.
    -   **Kluczowe selektory klas CSS:** `prestaspeedcache-dashboard`, `prestaspeedcache-config-form`, `prestaspeedcache-table`, `psc-debug-overlay`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony administracyjne (`views/templates/admin/`)

Te szablony są używane dla interfejsu back-office modułu.

-   `prestaspeedcache/views/templates/admin/cache_list.tpl`: Renderuje tabelę i interfejs do listowania i zarządzania buforowanymi stronami.
-   `prestaspeedcache/views/templates/admin/configure.tpl`: Główny formularz konfiguracji modułu, zawierający wszystkie ustawienia opisane w Sekcji 4.1.
-   `prestaspeedcache/views/templates/admin/dashboard.tpl`: Wyświetla metryki wydajności, wykresy i status kondycji pamięci podręcznej.
-   `prestaspeedcache/views/templates/admin/dynamic_modules.tpl`: Interfejs do wybierania i zarządzania modułami, które powinny być renderowane dynamicznie.
-   `prestaspeedcache/views/templates/admin/live_debug.tpl`: Renderuje panel debugowania w czasie rzeczywistym w panelu administracyjnym.
-   `prestaspeedcache/views/templates/admin/ops.tpl`: Prawdopodobnie zawiera szablony dla narzędzi operacyjnych lub działań (np. ręczne czyszczenie pamięci podręcznej, rozgrzewka).
-   `prestaspeedcache/views/templates/admin/tabs.tpl`: Renderuje strukturę nawigacji po zakładkach dla stron konfiguracji modułu.
-   `prestaspeedcache/views/templates/admin/wizard.tpl`: Szablon dla początkowego kreatora konfiguracji, prowadzący użytkowników przez podstawową konfigurację.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł wykorzystuje głównie tabelę `ps_configuration` PrestaShop do swoich ustawień. Do przechowywania pamięci podręcznej używa systemu plików lub zewnętrznych usług (Redis/Memcached). Może tworzyć niestandardowe tabele dla:

-   `ps_prestaspeedcache_cache_tags`: Przechowuje relacje między buforowanymi stronami a ich powiązanymi tagami (np. ID produktów, ID kategorii) dla efektywnego unieważniania.
-   `ps_prestaspeedcache_invalidation_queue`: Przechowuje listę stron lub tagów, które muszą zostać unieważnione, przetwarzane asynchronicznie.
-   `ps_prestaspeedcache_metrics`: Przechowuje metryki wydajności dla pulpitu nawigacyjnego.

#### Tabela zarejestrowanych hooków

Moduł rejestruje różne hooki, aby zintegrować się z cyklem życia PrestaShop.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Przed renderowaniem zawartości strony w nagłówku. | Wstrzykiwanie JavaScriptu front-office (np. `dynamic.js`, `fo_debug.js`), ustawianie początkowego kontekstu pamięci podręcznej. |
| `displayFooter` | Przed zamykającym tagiem `</body>`. | Wstrzykiwanie dodatkowych skryptów, informacji debugowania lub finalizowanie operacji na pamięci podręcznej. |
| `displayLeftColumn` | W lewej kolumnie motywu. | Potencjalnie używane do dynamicznego renderowania modułów, jeśli moduł w lewej kolumnie jest oznaczony jako dynamiczny. |
| `displayRightColumn` | W prawej kolumnie motywu. | Potencjalnie używane do dynamicznego renderowania modułów, jeśli moduł w prawej kolumnie jest oznaczony jako dynamiczny. |
| `displayProductAdditionalInfo` | Na stronie produktu, poniżej opisu produktu. | Jeśli moduł podpięty tutaj jest dynamiczny, jego zawartość zostanie pobrana oddzielnie. |
| `actionFrontControllerSetMedia` | Po ustawieniu mediów (JS/CSS) przez kontroler frontowy. | Dodawanie JS/CSS specyficznego dla modułu do strony. |
| `actionFrontControllerInit` | Na początku wykonania kontrolera frontowego. | Przechwytywanie żądań w celu sprawdzenia buforowanej zawartości lub przygotowania do buforowania. |
| `actionDispatcherBefore` | Zanim dispatcher przetworzy żądanie. | Wczesne przechwytywanie w celu serwowania buforowanej zawartości lub pominięcia dispatchingu. |
| `actionDispatcherAfter` | Po przetworzeniu żądania przez dispatcher. | Finalizowanie generowania pamięci podręcznej dla bieżącej strony. |
| `actionObjectUpdate` | Gdy dowolny `ObjectModel` jest aktualizowany (np. Produkt, Kategoria, CMS). | Wyzwalanie unieważniania pamięci podręcznej dla zmienionych stron. |
| `actionObjectAdd` | Gdy dowolny `ObjectModel` jest dodawany. | Wyzwalanie unieważniania pamięci podręcznej dla potencjalnie zmienionych stron. |
| `actionObjectDelete` | Gdy dowolny `ObjectModel` jest usuwany. | Wyzwalanie unieważniania pamięci podręcznej dla zmienionych stron. |
| `actionProductUpdate` | Specyficzne dla aktualizacji produktów. | Granularne unieważnianie pamięci podręcznej dla stron produktów. |
| `actionCategoryUpdate` | Specyficzne dla aktualizacji kategorii. | Granularne unieważnianie pamięci podręcznej dla stron kategorii. |
| `actionCmsUpdate` | Specyficzne dla aktualizacji stron CMS. | Granularne unieważnianie pamięci podręcznej dla stron CMS. |
| `actionClearCache` | Gdy natywna pamięć podręczna PrestaShop jest czyszczona. | Synchronizacja czyszczenia pamięci podręcznej modułu z PrestaShop. |
| `actionModuleInstall` | Gdy moduł jest instalowany. | Potencjalne czyszczenie pamięci podręcznej lub aktualizacja listy modułów dynamicznych. |
| `actionModuleUninstall` | Gdy moduł jest odinstalowywany. | Czyszczenie pamięci podręcznej lub usuwanie modułu z listy dynamicznej. |
| `actionAdminControllerSetMedia` | W kontrolerach administracyjnych, po ustawieniu mediów. | Wstrzykiwanie JS/CSS specyficznego dla administratora. |
| `actionAdminControllerPreProcess` | Przed przetworzeniem żądania przez kontroler administracyjny. | Ustawianie kontekstu administratora dla modułu. |
| `actionAdminControllerPostProcess` | Po przetworzeniu żądania przez kontroler administracyjny. | Obsługa post-processingu dla działań administracyjnych. |
| `actionOutputHTMLBefore` | Przed wysłaniem końcowego wyjścia HTML do przeglądarki. | Wykonywanie optymalizacji HTML (minifikacja). |
| `actionOutputHTMLAfter` | Po wysłaniu końcowego wyjścia HTML. | Finalizowanie przechowywania pamięci podręcznej. |
| `actionAjaxDie` | Gdy żądanie AJAX wywołuje `die()`. | Zapewnienie prawidłowej obsługi pamięci podręcznej dla odpowiedzi AJAX. |
| `actionGetContent` | Dla głównej strony konfiguracji modułu. | Renderowanie formularza konfiguracji modułu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w zapewnienie kompleksowej pomocy, aby Twój moduł Presta Speed Cache działał optymalnie.
