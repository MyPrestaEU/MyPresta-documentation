---
title: "TikTok Catalog Feed - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop TikTok Catalog Feed od MyPresta.eu."
sidebar:
  label: "TikTok Catalog Feed - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł TikTok Catalog Feed na MyPresta.eu](https://mypresta.eu/modules/social-networks/tiktok-catalog-feed.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/tiktok-catalog-feed/)
>
> ---


# TikTok Catalog Feed

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Upewnij się, że Twój serwer może obsłużyć generowanie potencjalnie dużych plików XML/CSV, jeśli masz bardzo obszerny katalog.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł TikTok Catalog Feed udostępnia dedykowaną sekcję w Panelu administracyjnym PrestaShop do zarządzania kanałami produktów.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Ten początkowy ekran konfiguracji pozwala ustawić podstawowe parametry dla Twojego kanału TikTok.

-   **Włącz moduł:**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji funkcjonalności modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Moduł będzie aktywny, umożliwiając generowanie i zarządzanie kanałami produktów TikTok.
        -   *Gdy wyłączony:* Moduł przestanie działać, a żadne kanały nie będą mogły być generowane ani dostępne.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz/przykład dla sprzedawcy:** Włączysz to, gdy będziesz gotowy do rozpoczęcia korzystania z reklam TikTok. Możesz tymczasowo wyłączyć, jeśli musisz przeprowadzić konserwację lub zatrzymać kampanie reklamowe TikTok.
-   **Typ generowania kanału:**

    -   **Co robi to ustawienie:** Określa, czy moduł generuje plik CSV (Comma Separated Values) czy XML (Extensible Markup Language) dla Twojego kanału produktów. TikTok zazwyczaj obsługuje oba.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na CSV:* Wygenerowany URL kanału będzie dostarczał plik CSV.
        -   *Gdy ustawione na XML:* Wygenerowany URL kanału będzie dostarczał plik XML.
    -   **Zalecana wartość:** XML (często preferowany ze względu na swoją ustrukturyzowaną naturę, ale CSV działa równie dobrze dla TikTok).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli dokumentacja TikTok lub Twoja agencja reklamowa zaleca konkretny format, wybierz go. W przeciwnym razie oba działają.
-   **Domyślny język dla kanału:**

    -   **Co robi to ustawienie:** Wybiera podstawowy język dla danych produktów w Twoim kanale. Jest to kluczowe dla targetowania konkretnych rynków na TikTok.
    -   **Efekt zmiany tego ustawienia:** Tytuły produktów, opisy i inne pola zależne od języka w kanale będą pobierane z Twojego sklepu PrestaShop w wybranym języku.
    -   **Zalecana wartość:** Język Twojej głównej grupy docelowej na TikTok (np. angielski dla rynku amerykańskiego, francuski dla rynku francuskiego).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli targetujesz klientów w Niemczech, wybierzesz tutaj „Niemiecki”, aby upewnić się, że informacje o Twoich produktach są poprawnie wyświetlane w ich języku na TikTok.
-   **Domyślna waluta dla kanału:**

    -   **Co robi to ustawienie:** Wybiera walutę używaną dla wszystkich cen produktów w Twoim kanale. Powinna ona odpowiadać walucie Twojego rynku docelowego.
    -   **Efekt zmiany tego ustawienia:** Wszystkie ceny w kanale zostaną przeliczone lub wyświetlone w wybranej walucie.
    -   **Zalecana wartość:** Waluta Twojej głównej grupy docelowej na TikTok (np. USD dla rynku amerykańskiego, EUR dla rynku europejskiego).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoje reklamy TikTok są skierowane do klientów w Wielkiej Brytanii, wybierzesz „GBP”, aby upewnić się, że ceny są wyświetlane w funtach brytyjskich.
-   **Domyślny kraj wysyłki:**

    -   **Co robi to ustawienie:** Ustawia domyślny kraj używany do obliczania kosztów wysyłki i dostępności w kanale. Jest to ważne, aby TikTok zrozumiał, gdzie Twoje produkty mogą być wysyłane.
    -   **Efekt zmiany tego ustawienia:** Informacje o wysyłce w kanale będą oparte na zasadach wysyłki wybranego kraju skonfigurowanych w Twoim sklepie PrestaShop.
    -   **Zalecana wartość:** Twój główny kraj docelowy wysyłki.
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli większość Twojej sprzedaży odbywa się we Francji, wybierzesz tutaj „Francja”.
-   **Uwzględnij produkty niedostępne w magazynie:**

    -   **Co robi to ustawienie:** Określa, czy produkty aktualnie oznaczone jako „brak w magazynie” w Twoim sklepie PrestaShop powinny być uwzględnione w kanale TikTok.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Produkty niedostępne w magazynie pojawią się w kanale, zazwyczaj ze statusem „niedostępne”.
        -   *Gdy wyłączone:* Produkty niedostępne w magazynie zostaną całkowicie wykluczone z kanału.
    -   **Zalecana wartość:** NIE (chyba że masz konkretną strategię dla zamówień przedpremierowych lub powiadomień o powrocie do magazynu).
    -   **Scenariusz/przykład dla sprzedawcy:** Zazwyczaj chcesz wyświetlać tylko dostępne produkty w swoich reklamach, aby uniknąć frustracji klientów. Jeśli masz długi czas realizacji dla produktów niestandardowych, możesz je uwzględnić, ale oznaczyć jako „zamówienie przedpremierowe”.
-   **Wyklucz określone kategorie:**

    -   **Co robi to ustawienie:** Pozwala wybrać konkretne kategorie produktów z Twojego sklepu PrestaShop, których NIE chcesz, aby pojawiały się w kanale TikTok.
    -   **Efekt zmiany tego ustawienia:** Produkty należące do wybranych kategorii zostaną pominięte w wygenerowanym kanale.
    -   **Zalecana wartość:** Zależy od Twojego sklepu.
    -   **Scenariusz/przykład dla sprzedawcy:** Możesz wykluczyć kategorie takie jak „Karty podarunkowe” lub „Usługi”, jeśli nie są to produkty fizyczne odpowiednie do reklam katalogowych TikTok. Lub, jeśli masz kategorię tylko dla B2B, wykluczysz ją z reklam skierowanych do konsumentów.
-   **Wyklucz określone produkty:**

    -   **Co robi to ustawienie:** Umożliwia ręczne wybranie pojedynczych produktów, które powinny zostać wykluczone z kanału TikTok, niezależnie od ich kategorii.
    -   **Efekt zmiany tego ustawienia:** Wybrane produkty nie zostaną uwzględnione w kanale.
    -   **Zalecana wartość:** Zależy od Twojego sklepu.
    -   **Scenariusz/przykład dla sprzedawcy:** Możesz wykluczyć produkt, który jest częścią ograniczonej czasowo wyprzedaży błyskawicznej, której nie chcesz reklamować na TikTok, lub produkt, który ma ograniczenia prawne dotyczące reklamy w niektórych regionach.
-   **Użyj krótkiego opisu produktu:**

    -   **Co robi to ustawienie:** Określa, czy w kanale TikTok używany jest krótki opis, czy pełny opis Twoich produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Użyty zostanie krótszy, bardziej zwięzły opis produktu.
        -   *Gdy wyłączone:* Użyty zostanie dłuższy, pełny opis produktu.
    -   **Zalecana wartość:** TAK (krótkie opisy są często lepsze dla reklam, ponieważ użytkownicy mają ograniczony czas uwagi).
    -   **Scenariusz/przykład dla sprzedawcy:** Reklamy TikTok korzystają z zwięzłych informacji. Użycie krótkiego opisu zapewnia, że tekst reklamy jest zwięzły i na temat.
-   **Eksportuj cechy produktu jako atrybuty:**

    -   **Co robi to ustawienie:** Jeśli włączone, cechy Twoich produktów PrestaShop (takie jak „Materiał”, „Kolor”, „Rozmiar”) zostaną wyeksportowane jako dodatkowe atrybuty w kanale TikTok, dostarczając bardziej szczegółowych informacji o produkcie.
    -   **Efekt zmiany tego ustawienia:** Bardziej szczegółowe informacje o produkcie będą dostępne dla TikTok w celu lepszego targetowania i wyświetlania reklam.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz odzież, eksportowanie „Koloru” i „Rozmiaru” jako atrybutów pozwala TikTok wyświetlać bardziej szczegółowe reklamy (np. „Czerwona sukienka, rozmiar M”).
-   **Eksportuj kombinacje produktów (warianty):**

    -   **Co robi to ustawienie:** Kluczowe dla sklepów z produktami, które mają warianty (np. koszulka dostępna w różnych rozmiarach i kolorach). To ustawienie zapewnia, że każda unikalna kombinacja jest eksportowana jako osobna pozycja w kanale.
    -   **Efekt zmiany tego ustawienia:** Każdy wariant produktu będzie miał swój własny wpis w kanale, z jego specyficzną ceną, stanem magazynowym i obrazem, co pozwoli TikTok wyświetlać dokładnie reklamowany wariant.
    -   **Zalecana wartość:** TAK (prawie zawsze, chyba że sprzedajesz tylko proste produkty bez wariantów).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli sprzedajesz buty dostępne w rozmiarach 7, 8 i 9, włączenie tego zapewnia, że TikTok widzi trzy odrębne produkty, każdy z własnym SKU i dostępnością.
-   **Eksportuj atrybut rozmiaru:**

    -   **Co robi to ustawienie:** Specjalnie dla produktów z kombinacjami, to ustawienie zapewnia, że atrybut „rozmiar” każdej kombinacji jest wyraźnie uwzględniony w kanale, co jest ważne dla odzieży i obuwia.
    -   **Efekt zmiany tego ustawienia:** Rozmiar każdego wariantu produktu będzie wyraźnie wymieniony w kanale.
    -   **Zalecana wartość:** TAK (szczególnie dla mody, obuwia lub wszelkich produktów zależnych od rozmiaru).
    -   **Scenariusz/przykład dla sprzedawcy:** Dla sklepu odzieżowego, to zapewnia, że „Duża niebieska koszulka” jest poprawnie identyfikowana przez TikTok, a nie tylko „Niebieska koszulka”.
-   **Eksportuj datę dostępności:**

    -   **Co robi to ustawienie:** Uwzględnia datę „dostępności do zamówienia” dla produktów, co jest przydatne dla pozycji zamówień przedpremierowych lub produktów z przyszłymi datami premiery.
    -   **Efekt zmiany tego ustawienia:** TikTok otrzyma informacje o tym, kiedy produkt będzie dostępny.
    -   **Zalecana wartość:** TAK (jeśli używasz tej funkcji w PrestaShop).
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli wprowadzasz nowy produkt w przyszłym miesiącu, to pozwala TikTok wyświetlać reklamy „zamówienia przedpremierowego” z poprawną datą dostępności.
-   **Mapowanie kategorii produktów Google:**

    -   **Co robi to ustawienie:** TikTok często wykorzystuje obszerną taksonomię produktów Google. Ta sekcja pozwala mapować Twoje kategorie PrestaShop do najbardziej odpowiednich kategorii produktów Google. Poprawia to trafność i targetowanie reklam.
    -   **Efekt zmiany tego ustawienia:** Twoje produkty zostaną poprawnie skategoryzowane zgodnie z taksonomią Google w kanale, którą TikTok wykorzystuje do lepszego zrozumienia i targetowania.
    -   **Zalecana wartość:** Zmapuj jak najwięcej kategorii.
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli masz kategorię PrestaShop „Sukienki letnie”, zmapujesz ją do kategorii produktów Google, takiej jak „Odzież i akcesoria > Odzież > Sukienki”.
-   **Generuj URL kanału:**

    -   **Co robi to ustawienie:** Po skonfigurowaniu wszystkich ustawień, ten przycisk generuje unikalny URL dla Twojego kanału produktów TikTok. Ten URL jest tym, co podasz w Menedżerze reklam TikTok.
    -   **Efekt zmiany tego ustawienia:** Kliknięcie tego spowoduje wyświetlenie URL. Kanał pod tym URL będzie odzwierciedlał wszystkie wybrane ustawienia.
    -   **Zalecana wartość:** Kliknij to po sfinalizowaniu wszystkich innych ustawień.
    -   **Scenariusz/przykład dla sprzedawcy:** Po skonfigurowaniu wszystkiego, kliknij to, skopiuj URL i wklej go do Menedżera reklam TikTok podczas konfigurowania katalogu.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolera

Moduł udostępnia dedykowaną sekcję w Panelu administracyjnym PrestaShop do zarządzania i generowania kanałów produktów TikTok.

**Nazwa ekranu i lokalizacja w menu:**
Możesz uzyskać dostęp do tej sekcji za pośrednictwem głównego menu PrestaShop: **Katalog > Kanał TikTok**.

Ta sekcja zazwyczaj przedstawia pulpit nawigacyjny lub listę wygenerowanych kanałów, umożliwiając zarządzanie różnymi konfiguracjami kanałów, jeśli moduł obsługuje wiele kanałów (np. dla różnych języków lub walut).

#### 2.2.1 Pulpit nawigacyjny kanału TikTok (Panel administracyjny > Katalog > Kanał TikTok)

Jest to główny punkt wejścia do zarządzania kanałami TikTok.

-   **Dostępne działania i ustawienia:**

    -   **Lista kanałów:** Zobaczysz tabelę lub listę wszystkich skonfigurowanych kanałów TikTok. Każdy wpis zazwyczaj będzie zawierał:
        -   **Nazwa kanału:** Opisowa nazwa Twojego kanału (np. „Kanał angielski US”, „Kanał francuski EU”).
        -   **Język:** Język produktów w tym kanale.
        -   **Waluta:** Waluta cen w tym kanale.
        -   **Ostatnio wygenerowany:** Sygnatura czasowa ostatniej aktualizacji kanału.
        -   **URL kanału:** Bezpośredni link do wygenerowanego pliku kanału (CSV lub XML).
        -   **Działania:** Przyciski „Edytuj”, „Generuj teraz” lub „Usuń” kanał.
    -   **Przycisk „Dodaj nowy kanał”:** Pozwala utworzyć nową konfigurację kanału, potencjalnie dla innego języka, waluty lub zestawu wykluczeń produktów.
    -   **Przycisk „Generuj wszystkie kanały”:** Wygodna opcja do jednoczesnego odświeżania wszystkich skonfigurowanych kanałów.
-   **Efekt zmian:**

    -   **Dodawanie nowego kanału:** Tworzy nową instancję konfiguracji, umożliwiając zdefiniowanie oddzielnego zestawu reguł (język, waluta, wykluczenia) dla odrębnego kanału TikTok. Jest to przydatne dla sklepów wielokrajowych lub wielojęzycznych.
    -   **Edytowanie kanału:** Przenosi Cię do formularza konfiguracji (podobnego do głównej konfiguracji modułu, ale specyficznego dla tej instancji kanału), gdzie możesz dostosować jego ustawienia.
    -   **Generowanie kanału:** Uruchamia moduł do przetwarzania katalogu produktów na podstawie ustawień kanału i tworzenia/aktualizowania pliku kanału pod jego unikalnym URL. Jest to kluczowe dla zapewnienia, że TikTok zawsze ma najbardziej aktualne informacje o produktach.
    -   **Usuwanie kanału:** Usuwa konfigurację kanału i powiązany z nim wygenerowany plik.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

    1.  **Początkowa konfiguracja:** Utwórz co najmniej jeden kanał dla swojego głównego rynku docelowego (np. angielski, USD).
    2.  **Konfiguracja dla wielu rynków:** Jeśli targetujesz wiele krajów lub języków, utwórz oddzielny kanał dla każdego, odpowiednio konfigurując ustawienia języka, waluty i kraju.
    3.  **Regularne generowanie:** TikTok zazwyczaj pobiera kanały zgodnie z harmonogramem (np. codziennie). Możesz ręcznie kliknąć „Generuj teraz”, jeśli wprowadziłeś znaczące zmiany w produktach (nowe produkty, aktualizacje cen, zmiany stanów magazynowych) i chcesz, aby TikTok natychmiast je odzwierciedlił. W przeciwnym razie moduł często ma mechanizm automatycznego generowania lub konfigurację zadania cron (patrz sekcja dla deweloperów).
    4.  **Monitorowanie stanu kanału:** Regularnie sprawdzaj Menedżera reklam TikTok pod kątem błędów lub ostrzeżeń dotyczących kanału. Jeśli pojawią się problemy, przejrzyj ustawienia modułu i ponownie wygeneruj kanał.

#### 2.2.2 Formularz konfiguracji kanału (dostępny poprzez „Dodaj nowy kanał” lub „Edytuj” kanał)

Ten ekran służy do definiowania konkretnych parametrów dla indywidualnego kanału produktów TikTok. Odzwierciedla wiele ustawień znajdujących się na głównej stronie konfiguracji modułu, ale stosuje je do pojedynczej instancji kanału.

-   **Pola i kolumny formularza:**

    -   **Nazwa kanału:** Unikalna, opisowa nazwa dla tego konkretnego kanału (np. „Katalog angielski US”, „Katalog niemiecki DE”).
    -   **Język:** Wybierz język dla tego kanału.
    -   **Waluta:** Wybierz walutę dla tego kanału.
    -   **Kraj:** Wybierz domyślny kraj wysyłki dla tego kanału.
    -   **Uwzględnij produkty niedostępne w magazynie:** (Tak samo jak powyżej, ale specyficzne dla tego kanału).
    -   **Wyklucz określone kategorie:** (Tak samo jak powyżej, ale specyficzne dla tego kanału).
    -   **Wyklucz określone produkty:** (Tak samo jak powyżej, ale specyficzne dla tego kanału).
    -   **Użyj krótkiego opisu produktu:** (Tak samo jak powyżej, ale specyficzne dla tego kanału).
    -   **Eksportuj cechy produktu jako atrybuty:** (Tak samo jak powyżej, ale specyficzne dla tego kanału).
    -   **Eksportuj kombinacje produktów (warianty):** (Tak samo jak powyżej, ale specyficzne dla tego kanału).
    -   **Eksportuj atrybut rozmiaru:** (Tak samo jak powyżej, ale specyficzne dla tego kanału).
    -   **Eksportuj datę dostępności:** (Tak samo jak powyżej, ale specyficzne dla tego kanału).
    -   **Mapowanie kategorii produktów Google:** (Tak samo jak powyżej, ale specyficzne dla tego kanału).
-   **Efekt zmian:** Zapisanie zmian w tym formularzu aktualizuje konfigurację dla konkretnego edytowanego kanału. Następnie musisz kliknąć „Generuj teraz” dla tego kanału, aby zastosować zmiany w rzeczywistym pliku kanału.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Włącz moduł | TAK | Aktywuje/dezaktywuje funkcjonalność modułu. |
| | Typ generowania kanału | XML | Wybierz format CSV lub XML dla kanału. |
| | Domyślny język dla kanału | Główny język sklepu | Ustawia język dla danych produktów. |
| | Domyślna waluta dla kanału | Główna waluta sklepu | Ustawia walutę dla cen produktów. |
| | Domyślny kraj wysyłki | Główny kraj wysyłki | Ustawia domyślny kraj dla informacji o wysyłce. |
| | Uwzględnij produkty niedostępne w magazynie | NIE | Wyklucza produkty niedostępne w magazynie z kanału. |
| | Wyklucz określone kategorie | (Brak) | Pomija produkty z wybranych kategorii. |
| | Wyklucz określone produkty | (Brak) | Pomija określone produkty z kanału. |
| | Użyj krótkiego opisu produktu | TAK | Używa krótkich opisów dla zwięzłości. |
| | Eksportuj cechy produktu jako atrybuty | TAK | Uwzględnia cechy produktu jako atrybuty. |
| | Eksportuj kombinacje produktów (warianty) | TAK | Eksportuje każdy wariant produktu jako osobną pozycję. |
| | Eksportuj atrybut rozmiaru | TAK | Uwzględnia atrybut rozmiaru dla wariantów. |
| | Eksportuj datę dostępności | TAK | Uwzględnia datę dostępności produktu. |
| | Mapowanie kategorii produktów Google | Zmapuj wszystkie odpowiednie | Mapuje kategorie PrestaShop do taksonomii Google dla TikTok. |
| | Generuj URL kanału | Kliknij po konfiguracji | Tworzy/aktualizuje unikalny URL dla kanału. |
| **Pulpit nawigacyjny kanału TikTok** | Dodaj nowy kanał | N/A | Tworzy nową, oddzielną konfigurację kanału. |
| | Edytuj kanał | N/A | Modyfikuje ustawienia dla istniejącego kanału. |
| | Generuj teraz (dla konkretnego kanału) | N/A | Ręcznie aktualizuje pojedynczy plik kanału. |
| | Generuj wszystkie kanały | N/A | Ręcznie aktualizuje wszystkie skonfigurowane pliki kanałów. |
| | Usuń kanał | N/A | Usuwa konfigurację kanału i jego plik. |
| **Formularz konfiguracji kanału** | Nazwa kanału | Opisowa nazwa | Identyfikuje konkretny kanał. |
| | (Wszystkie inne ustawienia) | (Jak powyżej) | Konfiguruje parametry dla tej indywidualnej instancji kanału. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje reklamy TikTok pokazują nieaktualne ceny lub produkty niedostępne w magazynie. Co powinienem zrobić?**
**O1:** Zazwyczaj oznacza to, że Twój kanał TikTok nie jest aktualizowany wystarczająco często.
1.  Przejdź do **Katalog > Kanał TikTok** w Panelu administracyjnym PrestaShop.
2.  Znajdź odpowiedni kanał i kliknij przycisk „Generuj teraz”.
3.  Upewnij się, że masz skonfigurowane zadanie cron do automatycznej codziennej aktualizacji kanałów (zalecane). Skontaktuj się z administratorem swojej strony lub dostawcą hostingu, aby potwierdzić, że zadanie cron działa poprawnie.
4.  Sprawdź ustawienie „Uwzględnij produkty niedostępne w magazynie” w konfiguracji kanału. Jeśli jest włączone, a nie chcesz wyświetlać produktów niedostępnych w magazynie, wyłącz je.

**P2: Niektóre z moich produktów brakuje w kanale TikTok.**
**O2:** Sprawdź następujące ustawienia dla konkretnego kanału:
1.  **„Wyklucz określone kategorie”:** Upewnij się, że kategorie brakujących produktów nie są tutaj wybrane.
2.  **„Wyklucz określone produkty”:** Upewnij się, że poszczególne produkty nie są ręcznie wykluczone.
3.  **„Uwzględnij produkty niedostępne w magazynie”:** Jeśli produkty są niedostępne w magazynie, a to ustawienie jest wyłączone, nie pojawią się.
4.  **Widoczność produktu:** Upewnij się, że produkty są aktywne i widoczne w Twoim sklepie PrestaShop.

**P3: Moje opisy produktów wyglądają zbyt długo lub zbyt krótko w kanale TikTok.**
**O3:** Przejdź do konfiguracji kanału i dostosuj ustawienie „Użyj krótkiego opisu produktu”:
-   Jeśli opisy są zbyt długie, włącz to ustawienie, aby użyć krótszego opisu.
-   Jeśli opisy są zbyt krótkie i chcesz więcej szczegółów, wyłącz to ustawienie, aby użyć pełnego opisu.

**P4: Jak skutecznie mapować moje kategorie do kategorii produktów Google?**
**O4:**
1.  Uzyskaj dostęp do sekcji „Mapowanie kategorii produktów Google” w konfiguracji kanału.
2.  Dla każdej z Twoich kategorii PrestaShop wyszukaj najbardziej odpowiednią kategorię produktów Google. Bądź jak najbardziej precyzyjny.
3.  Jeśli nie możesz znaleźć dokładnego dopasowania, wybierz najbliższą szerszą kategorię.
4.  To mapowanie pomaga TikTok lepiej zrozumieć Twoje produkty w celu targetowania.

**P5: Wprowadziłem zmiany, ale URL kanału nadal pokazuje stare dane. Co jest nie tak?**
**O5:** Po wprowadzeniu jakichkolwiek zmian w ustawieniach modułu lub konfiguracji konkretnego kanału, **musisz** ponownie wygenerować kanał. Przejdź do **Katalog > Kanał TikTok**, znajdź zmodyfikowany kanał i kliknij „Generuj teraz”. Jeśli zmieniłeś ustawienia globalne, być może będziesz musiał ponownie wygenerować wszystkie kanały.

**P6: Mój niestandardowy motyw powoduje problemy z wyświetlaniem modułu w Panelu administracyjnym.**
**O6:** Chociaż komponenty front-office modułu są niewidoczne, jego interfejs Panelu administracyjnego może kolidować z mocno dostosowanymi motywami administracyjnymi.
1.  **Wyczyść pamięć podręczną Smarty:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop. Kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). To często rozwiązuje drobne problemy z wyświetlaniem.
2.  **Sprawdź błędy JavaScript:** Otwórz konsolę deweloperską przeglądarki (F12) w Panelu administracyjnym. Poszukaj błędów JavaScript. Jeśli znajdziesz błędy, skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły błędu.
3.  **Tymczasowa zmiana motywu:** Jeśli to możliwe, tymczasowo przełącz motyw Panelu administracyjnego na domyślny motyw PrestaShop, aby sprawdzić, czy problem nadal występuje. Jeśli problem zostanie rozwiązany, konflikt dotyczy Twojego niestandardowego motywu administracyjnego.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu TikTok Catalog Feed, przeznaczony dla deweloperów i webmasterów.

### 4.1 Przegląd architektury

Moduł TikTok Catalog Feed jest zgodny ze standardowym wzorcem PrestaShop MVC (Model-View-Controller), skupiając się głównie na administracji Panelu administracyjnego i dostarczaniu danych do front-office. Wykorzystuje klasę `Module` PrestaShop do instalacji/deinstalacji i konfiguracji oraz `AdminController` do zarządzania ustawieniami kanału. Podstawowa logika polega na dynamicznym generowaniu danych produktów w ustrukturyzowanym formacie CSV lub XML, dostępnym za pośrednictwem dedykowanego `ModuleFrontController`. Nie wprowadza niestandardowych klas `ObjectModel`, ale bezpośrednio odpytuje podstawowe dane produktów i kategorii PrestaShop.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery są odpowiedzialne za dostarczanie rzeczywistego kanału produktów do TikTok.

-   `controllers/front/feed.php`
    -   **Nazwa klasy i klasa nadrzędna:** `TiktokfeedFeedModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Jest to główny punkt końcowy, z którego TikTok pobiera katalog produktów. Dynamicznie generuje kanał produktów (CSV lub XML) na podstawie parametrów konfiguracyjnych (język, waluta, wykluczenia) powiązanych z konkretnym ID kanału. Obsługuje pobieranie danych, formatowanie i wyprowadzanie jako plik do pobrania lub bezpośredni strumień. Jest zaprojektowany jako bezstanowy, przetwarzający żądanie i zwracający kanał.
-   `controllers/front/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `TiktokfeedIndexModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler jest zazwyczaj miejscem zastępczym lub awaryjnym. W wielu modułach `index.php` w katalogu kontrolerów front-office może obsługiwać domyślne routowanie lub po prostu przekierowywać. Dla tego modułu `feed.php` jest krytycznym kontrolerem front-office. Ten `index.php` może nie mieć specyficznej logiki lub może być używany do ogólnej strony front-office modułu, gdyby taka była zaimplementowana (co nie ma miejsca w przypadku modułu kanału).

#### Kontrolery administracyjne Back-Office

Te kontrolery zarządzają konfiguracją modułu i ustawieniami generowania kanału w Panelu administracyjnym PrestaShop.

-   `controllers/admin/AdminExportProductsFeedTiktok.php`
    -   **Nazwa klasy i klasa nadrzędna:** `AdminExportProductsFeedTiktokController` rozszerza `ModuleAdminController`.
    -   **Nazwa zakładki i zarządzana encja:** Ten kontroler jest odpowiedzialny za główną sekcję „Kanał TikTok” w **Katalog > Kanał TikTok**. Zarządza tworzeniem, edycją i usuwaniem indywidualnych konfiguracji kanałów. Wyświetla listę skonfigurowanych kanałów i udostępnia formularze do ich szczegółowych ustawień.
    -   **Kluczowe funkcjonalności:**
        -   `renderList()`: Wyświetla tabelę istniejących kanałów.
        -   `renderForm()`: Renderuje formularz dodawania/edycji kanału, w tym pola dla języka, waluty, wykluczeń kategorii/produktów, mapowania kategorii Google itp.
        -   Obsługuje zapisywanie i aktualizowanie konfiguracji kanałów (`postProcess()`).
        -   Uruchamia proces generowania kanału dla konkretnych kanałów.
-   `controllers/admin/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `AdminTiktokfeedIndexController` rozszerza `ModuleAdminController`.
    -   **Nazwa zakładki i zarządzana encja:** Ten kontroler prawdopodobnie służy jako główny punkt wejścia do sekcji administracyjnej modułu, potencjalnie przekierowując do `AdminExportProductsFeedTiktokController` lub udostępniając pulpit nawigacyjny wysokiego poziomu. Biorąc pod uwagę strukturę modułu, `AdminExportProductsFeedTiktokController` jest miejscem, gdzie znajduje się główna logika zarządzania kanałem. Ten `index.php` może służyć do ogólnego przeglądu modułu lub prostego przekierowania.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu nie wskazuje na niestandardowe klasy w katalogu `classes/`. Sugeruje to, że moduł opiera się głównie na podstawowych klasach `Product`, `Category`, `Language`, `Currency`, `Carrier` `ObjectModel` PrestaShop i `Configuration` do przechowywania i pobierania danych. Logika generowania kanału jest prawdopodobnie hermetyzowana w głównym pliku modułu (`tiktokfeed/index.php`) i `AdminExportProductsFeedTiktokController`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `tiktokfeed/lib/searchTool/views/js/autocomplete.js`
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Zapewnia funkcjonalność autouzupełniania, prawdopodobnie używaną do wybierania produktów lub kategorii do wykluczenia, lub do mapowania kategorii Google. Wiąże słuchaczy zdarzeń z polami wejściowymi, wykonuje żądania AJAX w celu uzyskania sugestii wyszukiwania i aktualizuje DOM wynikami.
-   `tiktokfeed/views/js/admin-app.js`
    -   **Zakres:** Panel administracyjny.
    -   **Cel:** Jest to główny plik JavaScript dla interfejsu Panelu administracyjnego modułu. Obsługuje różne interaktywne elementy w formularzach konfiguracji kanału i na pulpicie nawigacyjnym. Może to obejmować:
        -   Walidację formularzy.
        -   Dynamiczne aktualizacje na podstawie wybranych opcji (np. pokazywanie/ukrywanie pól).
        -   Wywołania AJAX do zapisywania ustawień lub uruchamiania generowania kanału.
        -   Interakcje z modalnymi oknami fancybox (np. do wyboru kategorii/produktów).

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `tiktokfeed/lib/searchTool/views/css/autocomplete.css`
    -   **Zakres:** Stylizacja Panelu administracyjnego.
    -   **Cel:** Stylizuje rozwijane listy autouzupełniania i pola wejściowe używane przez skrypt `autocomplete.js`, zapewniając spójne i przyjazne dla użytkownika doświadczenie wyszukiwania w formularzach administracyjnych.
-   `tiktokfeed/views/admin-theme.css`
    -   **Zakres:** Stylizacja Panelu administracyjnego.
    -   **Cel:** Zapewnia ogólne dostosowania stylów dla interfejsu Panelu administracyjnego modułu, aby bezproblemowo integrować się z motywem administracyjnym PrestaShop. Może to obejmować dostosowania układu, stylizację przycisków lub formatowanie tabel.
-   `tiktokfeed/views/css/admin-app.css`
    -   **Zakres:** Stylizacja Panelu administracyjnego.
    -   **Cel:** Zawiera specyficzne style dla niestandardowych komponentów modułu, formularzy i elementów pulpitu nawigacyjnego w Panelu administracyjnym PrestaShop. Może to obejmować style dla tabeli listy kanałów, paneli konfiguracyjnych i modalnych okien fancybox.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

Dossier modułu nie wymienia jawnie szablonów w podkatalogu `hook/`, co oznacza, że moduł nie renderuje treści bezpośrednio w hookach front-office. Jego główną funkcją jest generowanie danych, a nie wyświetlanie na front-endzie.

#### Szablony administracyjne (`views/templates/admin/`)

Te szablony są używane do renderowania interfejsu Panelu administracyjnego modułu.

-   `tiktokfeed/views/templates/admin/dashboard.tpl`
    -   **Cel:** Prawdopodobnie główny szablon pulpitu nawigacyjnego dla sekcji Kanał TikTok, potencjalnie pokazujący przegląd kanałów, status i szybkie działania.
-   `tiktokfeed/views/templates/admin/feeds.tpl`
    -   **Cel:** Renderuje listę skonfigurowanych kanałów TikTok, zazwyczaj tabelę z kolumnami dla nazwy kanału, języka, waluty, URL i przycisków akcji (edytuj, generuj, usuń). Jest to prawdopodobnie renderowane przez `AdminExportProductsFeedTiktokController::renderList()`.
-   `tiktokfeed/views/templates/admin/form-chrome.tpl`
    -   **Cel:** Wrapper lub częściowy szablon używany do zapewnienia spójnej stylizacji i struktury dla formularzy konfiguracyjnych modułu, potencjalnie zawierający nagłówek, stopkę i ogólne elementy układu dla formularza.
-   `tiktokfeed/views/templates/admin/layout.tpl`
    -   **Cel:** Podstawowy szablon układu dla stron administracyjnych modułu, definiujący ogólną strukturę, w tym nagłówek, nawigację i obszary treści.

#### Inne szablony związane z administracją

Te szablony są prawdopodobnie używane jako częściowe lub dla konkretnych komponentów interfejsu użytkownika w formularzach administracyjnych.

-   `tiktokfeed/lib/searchTool/views/scripts.tpl`
    -   **Cel:** Zawiera JavaScript dla narzędzia wyszukiwania, prawdopodobnie skrypt `autocomplete.js` i jego inicjalizację.
-   `tiktokfeed/views/categories-fancybox.tpl`
    -   **Cel:** Renderuje zawartość modalnego okna Fancybox używanego do wyboru kategorii do wykluczenia lub mapowania.
-   `tiktokfeed/views/exclude-products.tpl`
    -   **Cel:** Renderuje interfejs użytkownika do wybierania i zarządzania produktami, które mają zostać wykluczone z kanału, prawdopodobnie w Fancyboxie lub w dedykowanej sekcji formularza.
-   `tiktokfeed/views/google_lang_links.tpl`
    -   **Cel:** Renderuje linki lub elementy interfejsu użytkownika związane z mapowaniem kategorii produktów Google, potencjalnie dla różnych języków.
-   `tiktokfeed/views/returnAlert.tpl`
    -   **Cel:** Ogólny szablon do wyświetlania komunikatów/alertów o sukcesie lub błędach w Panelu administracyjnym.
-   `tiktokfeed/views/script-fancybox.tpl`
    -   **Cel:** Zawiera JavaScript do integracji Fancybox, prawdopodobnie do otwierania modalnych okien do wyboru kategorii/produktów.
-   `tiktokfeed/views/script.tpl`
    -   **Cel:** Ogólny szablon skryptu, prawdopodobnie do inicjalizacji JavaScript w całym module lub małych skryptów wbudowanych.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie wydaje się tworzyć niestandardowych tabel SQL na podstawie dossier.
    -   Przechowuje swoje ustawienia konfiguracyjne (np. typ kanału, domyślny język/waluta, listy wykluczeń, mapowania kategorii Google) w tabeli `ps_configuration` PrestaShop. Klucze konfiguracyjne zazwyczaj będą zgodne ze wzorcem, takim jak `TTF_FEED_TYPE`, `TTF_DEFAULT_LANG`, `TTF_EXCLUDE_CATEGORIES` itp.
    -   Indywidualne konfiguracje kanałów (jeśli obsługiwane jest wiele kanałów) mogą być przechowywane jako serializowane tablice w `ps_configuration` lub potencjalnie w niestandardowej tabeli, gdyby moduł taką wprowadził (co nie jest wskazane).
-   **Tabela zarejestrowanych hooków**:
    Główną funkcją modułu jest generowanie danych, a nie wyświetlanie na front-office, więc nie rejestruje on hooków do wyświetlania treści w witrynie (np. `displayHeader`, `displayRightColumn`).
    Zarejestruje jednak następujące hooki dla swojej podstawowej funkcjonalności:

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `actionModuleInstall` | Podczas instalacji modułu | Tworzy wpisy konfiguracyjne, rejestruje zakładki administracyjne. |
    | `actionModuleUninstall` | Podczas deinstalacji modułu | Czyści wpisy konfiguracyjne, wyrejestrowuje zakładki administracyjne. |
    | `actionAdminControllerSetMedia` | Po załadowaniu kontrolera administracyjnego | Dodaje specyficzne dla modułu JS i CSS do Panelu administracyjnego. |
    | `displayBackOfficeHeader` | Renderuje zawartość w nagłówku Panelu administracyjnego | Potencjalnie dla globalnego JS/CSS administracyjnego lub powiadomień. |
    | `actionSchedulerCron` (lub podobny) | Gdy uruchamia się zadanie cron PrestaShop | Uruchamia automatyczne generowanie kanału, jeśli jest skonfigurowane. |

### Konfiguracja zadania Cron do automatycznego generowania kanału

Aby zautomatyzować aktualizacje kanału, musisz skonfigurować zadanie cron na swoim serwerze, aby wywoływało określony URL lub skrypt dostarczony przez moduł. Ten URL zazwyczaj wskazuje na kontroler front-office, który uruchamia generowanie kanału.

**Przykład polecenia zadania Cron (skonsultuj się z dostawcą hostingu w celu uzyskania dokładnej składni):**

Terminal window

```
0 3 \* \* \* wget -q -O /dev/null "https://yourstore.com/module/tiktokfeed/feed?action=generate\_all&token=YOUR\_SECURE\_TOKEN" >/dev/null 2>&1
```

-   `0 3 * * *`: To planuje uruchomienie zadania codziennie o 3:00 rano.
-   `wget -q -O /dev/null`: Cicho pobiera URL i odrzuca dane wyjściowe.
-   `https://yourstore.com/module/tiktokfeed/feed?action=generate_all&token=YOUR_SECURE_TOKEN`: Jest to URL, który uruchamia generowanie kanału. Parametr `token` jest kluczowy dla bezpieczeństwa, aby zapobiec nieautoryzowanemu dostępowi. Moduł powinien dostarczyć ten token w swojej konfiguracji lub dokumentacji.
-   `>/dev/null 2>&1`: Przekierowuje wszystkie dane wyjściowe do null, zapobiegając niepotrzebnym powiadomieniom e-mail.

**Ważne:** Dokładny URL i token zostaną dostarczone przez moduł po konfiguracji. Zawsze używaj bezpiecznego tokena, aby chronić swój punkt końcowy generowania kanału.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji modułu, poprawek błędów i oficjalnego wsparcia deweloperskiego, prosimy odwołać się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Upewnij się, że używasz najnowszej kompatybilnej wersji modułu dla swojego sklepu PrestaShop.
