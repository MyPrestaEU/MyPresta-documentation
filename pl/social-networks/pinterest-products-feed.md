---
title: "Kanał produktów Pinterest - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów modułu PrestaShop „Kanał produktów Pinterest” od MyPresta.eu."
sidebar:
  label: "Kanał produktów Pinterest - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Pinterest products feed na MyPresta.eu](https://mypresta.eu/modules/social-networks/pinterest-products-feed.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/pinterest-products-feed/)
>
> ---


# Kanał produktów Pinterest

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i zapewniają płynne działanie modułów. Twoje środowisko hostingowe powinno również zapewniać wystarczającą ilość pamięci i czasu wykonania do generowania dużych kanałów produktów, zwłaszcza jeśli masz wiele produktów.

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

Moduł „Kanał produktów Pinterest” posiada główny ekran konfiguracji oraz dedykowany ekran administracyjny do zarządzania kanałami produktów.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Menedżer modułów > Konfiguruj Kanał produktów Pinterest)

Jest to główny ekran konfiguracji, na którym definiujesz podstawowe parametry dla swojego kanału produktów Pinterest.

#### Zakładka Ustawienia ogólne

Ta zakładka zawiera podstawowe ustawienia do generowania kanału produktów.

-   **Włącz kanał Pinterest:**
    *   **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji funkcjonalności modułu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po włączeniu (TAK):* Moduł wygeneruje kanał produktów i udostępni go za pośrednictwem adresu URL.
        *   *Po wyłączeniu (NIE):* Moduł nie będzie generować ani aktualizować kanału, a adres URL kanału stanie się nieaktywny.
    *   **Zalecana wartość:** TAK (po skonfigurowaniu innych ustawień).
    *   **Scenariusz/przykład dla sprzedawcy:** Jesteś gotowy, aby rozpocząć sprzedaż na Pintereście, więc włączasz to po ustawieniu filtrów produktów.
-   **Typ pliku kanału:**
    *   **Co robi to ustawienie:** Określa format pliku kanału produktów. Pinterest obsługuje zarówno CSV (wartości oddzielone przecinkami), jak i XML (rozszerzalny język znaczników).
    *   **Efekt zmiany tego ustawienia:**
        *   *Po ustawieniu na CSV:* Kanał będzie plikiem tekstowym z danymi produktów oddzielonymi przecinkami.
        *   *Po ustawieniu na XML:* Kanał będzie plikiem strukturalnym używającym znaczników XML.
    *   **Zalecana wartość:** XML (ogólnie bardziej niezawodny dla złożonych danych, ale oba działają z Pinteresta).
    *   **Scenariusz/przykład dla sprzedawcy:** Pinterest często zaleca XML dla bogatszych danych, więc możesz wybrać XML dla lepszej kompatybilności i przyszłości.
-   **Domyślny język dla kanału:**
    *   **Co robi to ustawienie:** Wybiera język, w którym nazwy produktów, opisy i inne dane tekstowe zostaną wyeksportowane w kanale.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po ustawieniu na angielski:* Cały tekst produktu będzie w języku angielskim.
        *   *Po ustawieniu na francuski:* Cały tekst produktu będzie w języku francuskim.
    *   **Zalecana wartość:** Główny język Twojej grupy docelowej na Pintereście.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli kierujesz reklamy do klientów we Francji, wybierzesz francuski. Jeśli kierujesz reklamy do globalnej anglojęzycznej publiczności, wybierzesz angielski.
-   **Domyślna waluta dla kanału:**
    *   **Co robi to ustawienie:** Wybiera walutę, w której ceny produktów zostaną wyeksportowane w kanale.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po ustawieniu na USD:* Wszystkie ceny będą w dolarach amerykańskich.
        *   *Po ustawieniu na EUR:* Wszystkie ceny będą w euro.
    *   **Zalecana wartość:** Główna waluta Twojego rynku docelowego na Pintereście.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój główny rynek używa euro, ustaw to na EUR, aby zapewnić prawidłowe wyświetlanie cen na Pintereście.
-   **Domyślny kraj dla kanału:**
    *   **Co robi to ustawienie:** Wybiera kraj powiązany z Twoimi produktami w kanale. Może to wpływać na obliczenia kosztów wysyłki i podatków po stronie Pinteresta.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po ustawieniu na Stany Zjednoczone:* Produkty są powiązane z rynkiem amerykańskim.
        *   *Po ustawieniu na Francję:* Produkty są powiązane z rynkiem francuskim.
    *   **Zalecana wartość:** Twój główny kraj działalności lub rynek docelowy.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoja firma ma siedzibę w Niemczech i sprzedaje głównie klientom niemieckim, wybierzesz Niemcy.
-   **Domyślny przewoźnik dla kanału:**
    *   **Co robi to ustawienie:** Określa domyślnego przewoźnika, który ma być powiązany z produktami w kanale. Może to być używane przez Pinterest do szacowania kosztów wysyłki.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po ustawieniu na „Mój przewoźnik”:* Pinterest może używać ogólnych zasad wysyłki tego przewoźnika (jeśli są dostępne) do wyświetlania.
    *   **Zalecana wartość:** Twój najczęściej używany lub domyślny przewoźnik.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli wysyłasz głównie z FedEx, wybierzesz tutaj FedEx.
-   **Uwzględnij kombinacje produktów (wariacje):**
    *   **Co robi to ustawienie:** Określa, czy poszczególne wariacje produktów (takie jak różne rozmiary lub kolory koszulki) są uwzględniane jako osobne pozycje w kanale.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po włączeniu (TAK):* Każda kombinacja (np. „Czerwona koszulka - Mała”, „Czerwona koszulka - Średnia”) będzie osobnym wpisem w kanale.
        *   *Po wyłączeniu (NIE):* W kanale zostanie uwzględniony tylko główny produkt, bez poszczególnych wariacji.
    *   **Zalecana wartość:** TAK (jeśli chcesz, aby klienci widzieli i klikali konkretne wariacje na Pintereście).
    *   **Scenariusz/przykład dla sprzedawcy:** Sprzedajesz koszulki w różnych rozmiarach i kolorach. Włączenie tej opcji zapewnia, że każda unikalna kombinacja rozmiaru/koloru otrzyma swój własny pin na Pintereście, umożliwiając klientom znalezienie dokładnie tego, czego szukają.
-   **Eksportuj produkty z określonym atrybutem (np. Rozmiar):**
    *   **Co robi to ustawienie:** Pozwala określić konkretny atrybut (np. „Rozmiar” lub „Kolor”), który powinien zostać uwzględniony w kanale produktów, często używany do bogatych danych produktów.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po wybraniu (np. „Rozmiar”):* Atrybut rozmiaru Twoich produktów zostanie wyraźnie uwzględniony w danych kanału.
        *   *Po niewybraniu:* Ten konkretny atrybut nie zostanie wyraźnie wyeksportowany.
    *   **Zalecana wartość:** Wybierz atrybut, który jest kluczowy dla różnicowania produktów, np. „Rozmiar” lub „Kolor”.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz odzież, wybranie „Rozmiaru” zapewnia, że Pinterest może wyświetlać informacje o rozmiarze bezpośrednio na pinie, poprawiając doświadczenie zakupowe.
-   **Eksportuj produkty z określoną cechą (np. Materiał):**
    *   **Co robi to ustawienie:** Podobnie jak atrybuty, pozwala to na uwzględnienie konkretnej cechy produktu (np. „Materiał” lub „Marka”) w kanale.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po wybraniu (np. „Materiał”):* Cecha materiału Twoich produktów zostanie wyraźnie uwzględniona w danych kanału.
        *   *Po niewybraniu:* Ta konkretna cecha nie zostanie wyraźnie wyeksportowana.
    *   **Zalecana wartość:** Wybierz cechę, która dodaje cenne informacje dla kupujących, np. „Materiał”, „Marka” lub „Styl”.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz meble, wybranie „Materiału” (np. „Dąb”, „Sosna”) pomaga klientom filtrować i znajdować produkty na podstawie ich preferencji.
-   **Eksportuj produkty z określoną etykietą niestandardową (np. Bestseller):**
    *   **Co robi to ustawienie:** Pozwala na uwzględnienie niestandardowej etykiety (jeśli zdefiniowałeś je w PrestaShop) w kanale. Mogą być one używane do konkretnych kampanii marketingowych na Pintereście.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po wybraniu (np. „Bestseller”):* Produkty z tą niestandardową etykietą będą miały ją uwzględnioną w danych kanału.
        *   *Po niewybraniu:* Etykiety niestandardowe nie zostaną wyeksportowane.
    *   **Zalecana wartość:** Użyj, jeśli masz konkretne etykiety do celów marketingowych lub kategoryzacji na Pintereście.
    *   **Scenariusz/przykład dla sprzedawcy:** Oznaczyłeś niektóre produkty jako „Bestsellery” w PrestaShop. Eksportowanie tej etykiety pozwala tworzyć kampanie reklamowe na Pintereście, skierowane specjalnie na te wysokowydajne produkty.
-   **Wyklucz produkty według kategorii:**
    *   **Co robi to ustawienie:** Udostępnia selektor w formie drzewa do wyboru całych kategorii produktów, których NIE chcesz uwzględniać w swoim kanale Pinterest.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po wybraniu kategorii:* Wszystkie produkty w tych kategoriach (i ich podkategoriach) zostaną wykluczone z wygenerowanego kanału.
        *   *Po niewybraniu żadnych kategorii:* Wszystkie produkty ze wszystkich kategorii zostaną uwzględnione do eksportu (chyba że zostaną wykluczone przez inne ustawienia).
    *   **Zalecana wartość:** Wyklucz kategorie, które nie są odpowiednie dla Pinteresta (np. usługi, produkty cyfrowe, lub produkty, których nie chcesz reklamować).
    *   **Scenariusz/przykład dla sprzedawcy:** Sprzedajesz zarówno produkty fizyczne, jak i cyfrowe karty podarunkowe. Wykluczyłbyś kategorię „Cyfrowe karty podarunkowe” z kanału, ponieważ Pinterest jest głównie dla produktów fizycznych.
-   **Wyklucz konkretne produkty:**
    *   **Co robi to ustawienie:** Pozwala wyszukać i wybrać pojedyncze produkty, które chcesz wyraźnie wykluczyć z kanału Pinterest.
    *   **Efekt zmiany tego ustawienia:**
        *   *Po wybraniu produktów:* Te konkretne produkty nie pojawią się w wygenerowanym kanale.
        *   *Po niewybraniu żadnych produktów:* Wszystkie produkty (nie wykluczone przez kategorię) zostaną uwzględnione do eksportu.
    *   **Zalecana wartość:** Wyklucz konkretne produkty, które są niedostępne w nieskończoność, wycofane z produkcji lub z jakiegokolwiek innego powodu nie chcesz ich na Pintereście.
    *   **Scenariusz/przykład dla sprzedawcy:** Konkretny produkt jest tymczasowo niedostępny z powodu problemu z dostawcą, więc wykluczasz go, dopóki nie wróci do magazynu.
-   **Generuj URL kanału:**
    *   **Co robi to ustawienie:** Wyświetla unikalny adres URL, pod którym można uzyskać dostęp do Twojego kanału produktów Pinterest. Jest to adres URL, który udostępnisz Pinterestowi.
    *   **Efekt zmiany tego ustawienia:** Jest to pole tylko do wyświetlania. Adres URL zmienia się, jeśli zmienisz domenę sklepu lub ustawienia SSL.
    *   **Zalecana wartość:** Skopiuj ten adres URL i wklej go do ustawień konta biznesowego Pinterest podczas konfigurowania katalogu produktów.
    *   **Scenariusz/przykład dla sprzedawcy:** Po skonfigurowaniu wszystkich ustawień kopiujesz ten adres URL i przechodzisz do swojego konta biznesowego Pinterest, aby skonfigurować katalog produktów, wklejając ten adres URL w polu „Źródło danych”.
-   **Generuj kanał (przycisk):**
    *   **Co robi to ustawienie:** Ręcznie uruchamia proces generowania pliku kanału produktów.
    *   **Efekt zmiany tego ustawienia:** Kliknięcie tego przycisku natychmiast utworzy lub zaktualizuje plik kanału na podstawie Twoich bieżących ustawień. Może to zająć trochę czasu w przypadku dużych katalogów.
    *   **Zalecana wartość:** Kliknij to po wprowadzeniu jakichkolwiek zmian w ustawieniach kanału lub gdy chcesz wymusić natychmiastową aktualizację.
    *   **Scenariusz/przykład dla sprzedawcy:** Właśnie dodałeś 50 nowych produktów i chcesz, aby jak najszybciej pojawiły się na Pintereście, więc klikasz „Generuj kanał”.

#### Zakładka Ustawienia Cron Job

Ta zakładka zawiera informacje dotyczące automatyzacji procesu generowania kanału.

-   **URL zadania Cron:**
    *   **Co robi to ustawienie:** Wyświetla specjalny adres URL, który po odwiedzeniu automatycznie uruchamia proces generowania kanału bez konieczności klikania przycisku „Generuj kanał” w panelu administracyjnym.
    *   **Efekt zmiany tego ustawienia:** Jest to pole tylko do wyświetlania.
    *   **Zalecana wartość:** Skopiuj ten adres URL i skonfiguruj go jako „zadanie cron” na swoim serwerze hostingowym.
    *   **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby Twój kanał Pinterest aktualizował się każdej nocy o 3:00. Kopiujesz ten adres URL i konfigurujesz zadanie cron na swoim serwerze, aby odwiedzało ten adres URL codziennie o 3:00.
-   **Jak skonfigurować zadanie Cron:**
    *   **Co robi to ustawienie:** Zawiera instrukcje dotyczące konfiguracji zautomatyzowanego zadania (zadania cron) na Twoim serwerze WWW w celu regularnej aktualizacji kanału produktów.
    *   **Efekt zmiany tego ustawienia:** Jest to sekcja informacyjna.
    *   **Zalecana wartość:** Postępuj zgodnie z tymi instrukcjami lub przekaż je swojemu webmasterowi/wsparciu hostingowemu, aby upewnić się, że Twój kanał jest zawsze aktualny.
    *   **Scenariusz/przykład dla sprzedawcy:** Nie wiesz, jak skonfigurować zadanie cron. Ta sekcja zawiera dokładne kroki lub informacje do przekazania dostawcy hostingu.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### Panel kanałów Pinterest (Panel administracyjny > Sprzedaż > Kanały Pinterest)

Ta dedykowana sekcja panelu administracyjnego PrestaShop zapewnia przegląd i interfejs zarządzania dla Twoich kanałów produktów Pinterest. Znajdziesz ją w menu „Sprzedaż” w PrestaShop 1.7/8/9.

-   **Nazwa ekranu i lokalizacja w menu:** Kanały Pinterest (w menu głównym „Sprzedaż”).
-   **Dostępne działania i ustawienia:**
    *   **Tabela listingu kanałów:** Ta tabela wyświetla wszystkie wygenerowane kanały (jeśli moduł obsługuje wiele kanałów, w przeciwnym razie pokaże główny). Zazwyczaj zawiera:
        *   **Nazwa/ID kanału:** Unikalny identyfikator kanału.
        *   **Język:** Język produktów w kanale.
        *   **Waluta:** Waluta cen w kanale.
        *   **Ostatnio wygenerowano:** Data i godzina ostatniej aktualizacji kanału.
        *   **URL kanału:** Bezpośredni link do wygenerowanego pliku kanału.
        *   **Działania:** Przyciski do przeglądania, pobierania lub ponownego generowania kanału.
    *   **Dodaj nowy kanał / Edytuj kanał:** Chociaż moduł koncentruje się głównie na jednym głównym kanale, ten interfejs może umożliwiać przyszłe rozszerzenia lub specyficzne konfiguracje kanałów. Na razie w dużej mierze odzwierciedla ustawienia z głównej strony konfiguracji.
    *   **Widok siatki / zarządzania:** Ten ekran zapewnia przejrzysty przegląd statusu Twojego kanału i szybki dostęp do jego adresu URL oraz opcji ponownego generowania.
-   **Efekt zmian:**
    *   *Ponowne generowanie kanału:* Aktualizuje plik kanału najnowszymi danymi produktów z Twojego sklepu, odzwierciedlając wszelkie zmiany w informacjach o produkcie, cenach lub poziomach zapasów.
    *   *Wyświetlanie adresu URL kanału:* Pozwala szybko skopiować adres URL potrzebny dla Pinteresta.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Okresowo sprawdzaj ten panel, aby upewnić się, że Twój kanał jest regularnie generowany (jeśli skonfigurowałeś zadanie cron) i że znacznik czasu „Ostatnio wygenerowano” jest aktualny.
    2.  Jeśli wprowadzasz znaczące zmiany w produktach (np. masowe aktualizacje cen, wprowadzanie nowych produktów), możesz ręcznie ponownie wygenerować kanał z tego ekranu lub konfiguracji modułu, aby upewnić się, że Pinterest szybko otrzyma najnowsze dane.
    3.  Skopiuj adres URL kanału stąd podczas początkowej konfiguracji konta biznesowego Pinterest.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Włącz kanał Pinterest | TAK | Aktywuje/dezaktywuje generowanie kanału. |
| | Typ pliku kanału | XML | Ustawia format wyjściowy dla kanału (CSV lub XML). |
| | Domyślny język dla kanału | Twój główny język | Język dla nazw/opisów produktów. |
| | Domyślna waluta dla kanału | Twoja główna waluta | Waluta dla cen produktów. |
| | Domyślny kraj dla kanału | Twój główny kraj | Powiązanie kraju dla produktów. |
| | Domyślny przewoźnik dla kanału | Twój domyślny przewoźnik | Przewoźnik do szacowania kosztów wysyłki przez Pinterest. |
| | Uwzględnij kombinacje produktów | TAK | Eksportuje indywidualne wariacje produktów. |
| | Eksportuj produkty z określonym atrybutem | Wybierz odpowiedni atrybut (np. Rozmiar) | Uwzględnia konkretne atrybuty produktów w kanale. |
| | Eksportuj produkty z określoną cechą | Wybierz odpowiednią cechę (np. Materiał) | Uwzględnia konkretne cechy produktów w kanale. |
| | Eksportuj produkty z określoną etykietą niestandardową | Wybierz odpowiednią etykietę (np. Bestseller) | Uwzględnia niestandardowe etykiety do celów marketingowych. |
| | Wyklucz produkty według kategorii | Wybierz kategorie do wykluczenia | Zapobiega pojawianiu się produktów z wybranych kategorii w kanale. |
| | Wyklucz konkretne produkty | Wybierz pojedyncze produkty do wykluczenia | Zapobiega pojawianiu się konkretnych produktów w kanale. |
| | Generuj URL kanału | (Tylko wyświetlanie) | Adres URL do udostępnienia Pinterestowi w celu pobrania Twojego kanału. |
| | Generuj kanał (przycisk) | Kliknij po zmianach | Ręcznie uruchamia natychmiastowe generowanie kanału. |
| **Zakładka Ustawienia Cron Job** | URL zadania Cron | (Tylko wyświetlanie) | Adres URL do automatycznego generowania kanału za pośrednictwem crona serwera. |
| | Jak skonfigurować zadanie Cron | Postępuj zgodnie z instrukcjami | Przewodnik po konfiguracji automatycznych aktualizacji kanału. |
| **Panel kanałów Pinterest** | Tabela listingu kanałów | (Widok) | Przegląd wygenerowanych kanałów, statusu i adresów URL. |
| | Ponownie wygeneruj kanał (akcja) | Kliknij w razie potrzeby | Aktualizuje kanał najnowszymi danymi sklepu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje produkty nie pojawiają się na Pintereście po skonfigurowaniu kanału. Co powinienem zrobić?**
O1: Najpierw upewnij się, że ustawienie „Włącz kanał Pinterest” w konfiguracji modułu jest ustawione na TAK. Następnie ręcznie kliknij przycisk „Generuj kanał”, aby utworzyć początkowy plik kanału. Następnie dokładnie sprawdź, czy poprawnie skopiowałeś i wkleiłeś „URL kanału” do ustawień katalogu produktów na swoim koncie biznesowym Pinterest. Pinterest może potrzebować trochę czasu (do 24-48 godzin) na przetworzenie nowego kanału. Sprawdź również swoje konto biznesowe Pinterest pod kątem wszelkich komunikatów o błędach związanych z kanałem.

**P2: Ceny lub poziomy zapasów na Pintereście są nieaktualne. Jak to naprawić?**
O2: Zazwyczaj oznacza to, że Twój kanał nie jest regularnie aktualizowany. Upewnij się, że skonfigurowałeś zadanie cron na swoim serwerze hostingowym, używając „URL zadania Cron” podanego w module. Jeśli zadanie cron jest skonfigurowane, sprawdź, czy działa poprawnie (Twój dostawca hostingu może w tym pomóc). Możesz również ręcznie ponownie wygenerować kanał, klikając przycisk „Generuj kanał” w konfiguracji modułu, aby wymusić natychmiastową aktualizację.

**P3: Brakuje niektórych moich produktów w kanale Pinterest.**
O3: Przejdź do strony konfiguracji modułu i sprawdź ustawienia „Wyklucz produkty według kategorii” oraz „Wyklucz konkretne produkty”. Mogłeś nieumyślnie wykluczyć kategorie lub pojedyncze produkty. Upewnij się również, że produkty mają prawidłowe zdjęcia, ceny i są ustawione jako „aktywne” i „dostępne do zamówienia” w Twoim sklepie PrestaShop, ponieważ moduł zazwyczaj eksportuje tylko aktywne, możliwe do zakupu produkty.

**P4: Proces generowania kanału trwa bardzo długo lub kończy się błędem przekroczenia limitu czasu.**
O4: Jeśli masz bardzo duży katalog (tysiące produktów), generowanie kanału może być zasobochłonne.
\* **Rozwiązanie 1:** Zwiększ ustawienia `memory_limit` i `max_execution_time` PHP w pliku `php.ini` Twojego serwera. Twój dostawca hostingu może w tym pomóc.
\* **Rozwiązanie 2:** Upewnij się, że zadanie cron jest ustawione na uruchamianie w godzinach poza szczytem, aby zminimalizować wpływ na wydajność sklepu.
\* **Rozwiązanie 3:** Rozważ wykluczenie mniej ważnych kategorii lub produktów, jeśli rozmiar kanału jest stale problemem.

**P5: Moje niestandardowe style motywu nie są stosowane do interfejsu administracyjnego modułu.**
O5: Interfejs administracyjny modułu używa własnych plików CSS (`admin-app.css`, `admin-theme.css`). Są one oddzielone od Twojego motywu front-office. Jeśli chcesz dostosować wygląd stron panelu administracyjnego modułu, musiałbyś nadpisać te konkretne pliki CSS lub dodać niestandardowy CSS do panelu administracyjnego PrestaShop. Jest to zazwyczaj zadanie dla programisty stron internetowych.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu „Kanał produktów Pinterest” dla deweloperów i webmasterów.

### 4.1 Przegląd architektury

Moduł `pinterestfeed` stosuje standardowy wzorzec PrestaShop MVC (Model-View-Controller), z dedykowanymi kontrolerami front-office do generowania kanału i wykonywania zadań cron, oraz kontrolerami administracyjnymi do konfiguracji i zarządzania. Wykorzystuje `ObjectModel` do potencjalnej trwałości danych (chociaż koncentruje się głównie na dynamicznym generowaniu kanału) i używa szablonów Smarty do renderowania zarówno konfiguracji panelu administracyjnego, jak i widoków informacyjnych. Podstawowa logika generowania kanału zgodnie ze specyfikacjami Pinteresta jest hermetyzowana w dedykowanych klasach pomocniczych.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery obsługują publiczne żądania, głównie dla samego kanału i wykonywania zadań cron.

-   `controllers/front/cron.php`
    *   **Nazwa klasy i klasa nadrzędna:** `PinterestFeedCronModuleFrontController` rozszerzająca `ModuleFrontController`.
    *   **Odpowiedzialność:** Ten kontroler jest przeznaczony do wywoływania przez zadanie cron po stronie serwera. Po uzyskaniu dostępu, uruchamia klasę `PinterestFeedGenerator` w celu ponownego wygenerowania kanału produktów na podstawie bieżącej konfiguracji modułu. Zazwyczaj zwraca prostą wiadomość o sukcesie/porażce lub loguje proces. Nie renderuje strony wizualnej.
-   `controllers/front/feed.php`
    *   **Nazwa klasy i klasa nadrzędna:** `PinterestFeedFeedModuleFrontController` rozszerzająca `ModuleFrontController`.
    *   **Odpowiedzialność:** Ten kontroler obsługuje rzeczywisty plik kanału produktów. Po uzyskaniu dostępu za pośrednictwem „URL kanału”, odczytuje wstępnie wygenerowany plik kanału (lub generuje go, jeśli nie istnieje/jest nieaktualny, w zależności od implementacji) i wyprowadza jego zawartość (CSV lub XML) z odpowiednimi nagłówkami HTTP (`Content-Type`).

#### Kontrolery administracyjne Back-Office

Te kontrolery zarządzają konfiguracją modułu i zapewniają interfejsy administracyjne.

-   `controllers/admin/AdminExportProductsFeedPinterest.php`
    *   **Nazwa klasy i klasa nadrzędna:** `AdminExportProductsFeedPinterestController` rozszerzająca `ModuleAdminController`.
    *   **Nazwa zakładki i zarządzana encja:** Ten kontroler jest odpowiedzialny za panel „Kanały Pinterest” znajdujący się w menu „Sprzedaż”. Zarządza wyświetlaniem i działaniami związanymi z wygenerowanymi kanałami produktów. Nie zarządza bezpośrednio konkretną encją `ObjectModel`, ale raczej orkiestruje generowanie i wyświetlanie danych związanych z kanałem.
    *   **Kluczowe wykorzystywane klucze konfiguracji:** `PS_LANG_DEFAULT`, `PS_CARRIER_DEFAULT`, `PS_COUNTRY_DEFAULT`, `PS_CURRENCY_DEFAULT` (dla wartości domyślnych w formularzach), `pm_pinterestfeed_products`, `pm_export_size_attribute` (dla ustawień specyficznych dla modułu). Wykorzystuje również `pf_tree` do wyboru kategorii i `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` do wyboru języka w formularzach.
-   `controllers/admin/index.php`
    *   **Nazwa klasy i klasa nadrzędna:** Ten plik prawdopodobnie służy jako symbol zastępczy lub proste przekierowanie/punkt wejścia dla sekcji administracyjnej, a nie jako pełnoprawny kontroler. W PrestaShop pliki `index.php` w podkatalogach często zapobiegają bezpośredniemu listowaniu katalogów. Jego główną rolą jest zapewnienie bezpieczeństwa poprzez zapobieganie bezpośredniemu dostępowi do zawartości katalogu.

### 4.3 Klasy podstawowe i modele (`classes/`)

-   `classes/index.php`
    *   **Cel:** Standardowy plik bezpieczeństwa PrestaShop zapobiegający bezpośredniemu listowaniu katalogów.
-   `classes/PinterestFeedGenerator.php`
    *   **Odpowiedzialność:** Jest to podstawowa klasa logiczna do konstruowania kanału produktów.
    *   **Interakcja z bazą danych:** Współpracuje z różnymi podstawowymi tabelami PrestaShop (np. `ps_product`, `ps_product_lang`, `ps_image`, `ps_category`, `ps_attribute`, `ps_feature`, `ps_stock_available`) w celu pobierania danych produktów.
    *   **Rozszerzenie ObjectModel:** Nie rozszerza bezpośrednio `ObjectModel`, ponieważ jego celem jest agregacja i formatowanie danych, a nie trwałość pojedynczej encji.
    *   **Kluczowe metody publiczne:** Zawiera metody do pobierania produktów, obsługi kombinacji, stosowania filtrów (kategorie, konkretne produkty), formatowania danych zgodnie ze specyfikacjami Pinteresta i zapisywania danych wyjściowych do wybranego typu pliku (CSV/XML).
-   `classes/PinterestFeedSpec.php`
    *   **Odpowiedzialność:** Ta klasa prawdopodobnie definiuje wymagane i opcjonalne pola dla specyfikacji kanału produktów Pinterest. Działa jako warstwa mapowania lub walidacji, aby zapewnić, że wygenerowany kanał jest zgodny z wytycznymi Pinteresta.
    *   **Interakcja z bazą danych:** Brak bezpośredniej.
    *   **Rozszerzenie ObjectModel:** Nie rozszerza `ObjectModel`.
    *   **Kluczowe metody publiczne:** Może zawierać metody do pobierania listy wymaganych/opcjonalnych pól, ich typów danych i wszelkich specyficznych reguł formatowania.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    *   **Zakres:** Panel administracyjny.
    *   **Cel:** Zapewnia funkcjonalność autouzupełniania, prawdopodobnie do wyszukiwania i wybierania produktów lub kategorii w formularzach konfiguracji administratora (np. dla „Wyklucz konkretne produkty”).
    *   **Słuchacze zdarzeń:** Wiąże się ze zdarzeniami `keyup` lub `input` pól wejściowych, aby wyzwalać wyszukiwania AJAX.
    *   **Manipulacja DOM:** Wyświetla wyniki wyszukiwania na liście rozwijanej, umożliwia wybór i aktualizuje ukryte pola wejściowe.
-   `views/js/admin-app.js`
    *   **Zakres:** Panel administracyjny.
    *   **Cel:** Główny JavaScript dla konfiguracji panelu administracyjnego modułu i pulpitu nawigacyjnego. Obsługuje przesyłanie formularzy, dynamiczne aktualizacje i potencjalnie wywołania AJAX dla statusu generowania kanału.
    *   **Słuchacze zdarzeń:** Wiąże się ze zdarzeniami `submit` formularzy, zdarzeniami `click` przycisków (np. „Generuj kanał”) i potencjalnie zdarzeniami `change` pól wyboru.
    *   **Manipulacja DOM:** Zarządza wyświetlaniem zakładek konfiguracji, aktualizuje komunikaty o statusie i współdziała z komponentem autouzupełniania.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`
    *   **Zakres:** Stylizacja formularzy administracyjnych panelu administracyjnego.
    *   **Cel:** Stylizuje pole wyszukiwania autouzupełniania i jego wyniki rozwijane, zapewniając spójny wygląd i działanie w panelu administracyjnym PrestaShop.
    *   **Kluczowe selektory klas CSS:** `.autocomplete-container`, `.autocomplete-results`, `.autocomplete-item`.
-   `views/admin-theme.css`
    *   **Zakres:** Stylizacja formularzy administracyjnych panelu administracyjnego.
    *   **Cel:** Zapewnia ogólną stylizację stron konfiguracji panelu administracyjnego modułu, zapewniając dobrą integrację z motywem administracyjnym PrestaShop.
    *   **Kluczowe selektory klas CSS:** `.panel`, `.form-group`, `.control-label`, `.help-block`.
-   `views/css/admin-app.css`
    *   **Zakres:** Stylizacja formularzy administracyjnych panelu administracyjnego.
    *   **Cel:** Specyficzna stylizacja dla niestandardowych elementów i układu modułu w interfejsie administracyjnym, takich jak nawigacja po zakładkach, niestandardowe przyciski lub unikalne bloki informacyjne.
    *   **Kluczowe selektory klas CSS:** `.pinterestfeed-tabs`, `.pinterestfeed-panel`, `.pinterestfeed-alert`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**: Opis modułu nie wymienia jawnie szablonów hooków, co sugeruje, że jego obecność w front-office jest przede wszystkim za pośrednictwem adresu URL kanału, a nie bezpośredniego wyświetlania. Jeśli jakiekolwiek istnieją, służyłyby do bloków informacyjnych.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   `views/templates/admin/dashboard.tpl`: Prawdopodobnie główny szablon dla panelu „Kanały Pinterest”, wyświetlający listę kanałów, ich status i działania.
    *   `views/templates/admin/feeds.tpl`: Może być częściowym szablonem używanym w `dashboard.tpl` do renderowania tabeli kanałów.
    *   `views/templates/admin/form-chrome.tpl`: Ogólny szablon opakowujący dla formularzy administracyjnych, zapewniający standardowy panel PrestaShop i strukturę formularza.
    *   `views/templates/admin/layout.tpl`: Główny szablon układu dla sekcji administracyjnej modułu, definiujący ogólną strukturę, w tym nagłówek, zakładki i obszar zawartości.
-   **Szablony konfiguracji i narzędzi (`views/`)**:
    *   `views/categories-fancybox.tpl`: Szablon dla modalnego okna Fancybox używanego do wyboru kategorii (np. do wykluczenia).
    *   `views/custom-labels.tpl`: Szablon do wyświetlania lub zarządzania niestandardowymi etykietami.
    *   `views/exclude-products.tpl`: Szablon dla interfejsu wyszukiwania i wyboru produktów do wykluczenia.
    *   `views/google_lang_links.tpl`: Potencjalnie do wyświetlania linków lub informacji specyficznych dla języka, chociaż jego bezpośrednie użycie w module kanału Pinterest może być w celach informacyjnych.
    *   `views/returnAlert.tpl`: Ogólny szablon do wyświetlania alertów sukcesu lub błędu w panelu administracyjnym.
    *   `views/script-fancybox.tpl`: Zawiera JavaScript do inicjalizacji i zarządzania modalnymi oknami Fancybox.
    *   `views/script.tpl`: Ogólne fragmenty JavaScript lub skrypty inicjalizacyjne dla stron administracyjnych modułu.
    *   `lib/searchTool/views/scripts.tpl`: Zawiera JavaScript dla narzędzia wyszukiwania autouzupełniania.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Moduł nie wydaje się tworzyć własnych niestandardowych tabel SQL na podstawie dostarczonego spisu.
    *   W dużej mierze opiera się na istniejących podstawowych tabelach PrestaShop: `ps_product`, `ps_product_lang`, `ps_image`, `ps_category`, `ps_category_product`, `ps_attribute_group`, `ps_attribute`, `ps_feature`, `ps_feature_product`, `ps_stock_available`, `ps_configuration` (dla ustawień modułu, takich jak `PINTERESTFEED_ENABLED`, `PINTERESTFEED_FILE_TYPE` itp.).
-   **Tabela zarejestrowanych hooków**:
    Główną funkcją modułu jest generowanie kanału, które jest zazwyczaj wyzwalane przez bezpośredni dostęp do kontrolera (URL kanału, URL crona) lub działania administratora. Chociaż opis modułu wspomina o „Hookach Front-Office: Nagłówek, Kolumny, Produkt lub Stopka”, dostarczony spis plików i opis funkcji sugerują, że *ten konkretny moduł* nie używa ich aktywnie do wyświetlania wizualnego. Zamiast tego moduł prawdopodobnie rejestruje hooki dla procesów wewnętrznych lub potencjalnych przyszłych rozszerzeń.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Przy każdym ładowaniu strony w front office. | Potencjalnie do dodawania niestandardowych JS/CSS, gdyby moduł miał komponent front-office, lub do wewnętrznego śledzenia. (Mało prawdopodobne, aby był używany do wizualnego wyjścia przez ten moduł). |
| `displayRightColumn` | W prawej kolumnie front office. | (Mało prawdopodobne, aby był używany do wizualnego wyjścia przez ten moduł). |
| `displayLeftColumn` | W lewej kolumnie front office. | (Mało prawdopodobne, aby był używany do wizualnego wyjścia przez ten moduł). |
| `displayFooter` | W stopce każdej strony w front office. | (Mało prawdopodobne, aby był używany do wizualnego wyjścia przez ten moduł). |
| `displayProductExtraContent` | Na stronie produktu, poniżej głównej zawartości. | (Mało prawdopodobne, aby był używany do wizualnego wyjścia przez ten moduł). |
| `actionProductUpdate` | Po zaktualizowaniu produktu w panelu administracyjnym. | Potencjalnie do oznaczenia kanału jako wymagającego ponownego wygenerowania lub do wyzwolenia częściowej aktualizacji. |
| `actionProductAdd` | Po dodaniu nowego produktu. | Podobnie jak `actionProductUpdate`. |
| `actionProductDelete` | Po usunięciu produktu. | Podobnie jak `actionProductUpdate`. |
| `actionUpdateQuantity` | Po zmianie ilości produktu w magazynie. | Potencjalnie do wyzwolenia ponownego generowania kanału, jeśli zmiany stanu magazynowego są krytyczne dla kanału. |
| `actionModuleInstall` | Podczas instalacji modułu. | Aby utworzyć wpisy konfiguracyjne i potencjalnie początkowy plik kanału. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Aby usunąć wpisy konfiguracyjne i wygenerowane pliki. |
| `displayAdminProductsExtra` | Na stronie edycji produktu w panelu administracyjnym. | Może być używany do dodawania konkretnej zakładki lub pola związanego z ustawieniami kanału Pinterest dla poszczególnych produktów. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Kanał produktów Pinterest”, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół jest zaangażowany w zapewnienie doskonałego działania modułu i pomoc w osiągnięciu celów e-commerce.

-   **MyPresta.eu Historia zamówień i pobieranie:** <https://mypresta.eu/my-account/orders/>
-   **MyPresta.eu Kontakt z pomocą techniczną:** <https://mypresta.eu/contact>
