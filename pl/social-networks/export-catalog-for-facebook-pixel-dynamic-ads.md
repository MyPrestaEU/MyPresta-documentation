---
title: "Eksport katalogu dla reklam dynamicznych Facebook Pixel - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Eksport katalogu dla reklam dynamicznych Facebook Pixel” od MyPresta.eu."
sidebar:
  label: "Eksport katalogu dla reklam dynamicznych Facebook Pixel - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Export catalog for facebook pixel dynamic ads na MyPresta.eu](https://mypresta.eu/modules/social-networks/export-catalog-for-facebook-pixel-dynamic-ads.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/export-catalog-for-facebook-pixel-dynamic-ads/)
>
> ---


# Eksport katalogu dla reklam dynamicznych Facebook Pixel

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Upewnij się, że Twój serwer ma wystarczającą ilość pamięci i czasu wykonania, aby generować duże kanały produktów, jeśli masz wiele produktów.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

Konfiguracja modułu jest głównie obsługiwana za pośrednictwem dedykowanego ekranu administracyjnego, który pozwala zdefiniować sposób eksportowania katalogu produktów.

### 2.1 Główny ekran konfiguracji modułu (Panel administracyjny > Moduły > Menedżer modułów > Konfiguruj)

Ten ekran zawiera główne ustawienia modułu, umożliwiając generowanie i zarządzanie kanałami produktów.

**Lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > Wyszukaj „Eksport katalogu dla reklam dynamicznych Facebook Pixel” > Kliknij „Konfiguruj”.

#### Ustawienia ogólne i generowanie kanału

Ta sekcja służy do definiowania podstawowych parametrów kanału produktów.

-   **Wybierz język eksportu:**

    *   **Co robi to ustawienie:** Określa, które nazwy produktów, opisy i inne pola tekstowe w danym języku zostaną uwzględnione w eksportowanym kanale.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawione na angielski:* Twój kanał będzie zawierał szczegóły produktów w języku angielskim.
        *   *Gdy ustawione na francuski:* Twój kanał będzie zawierał szczegóły produktów w języku francuskim.
    *   **Zalecana wartość:** Główny język Twojej docelowej grupy odbiorców dla reklam na Facebooku. Jeśli prowadzisz reklamy w wielu językach, będziesz musiał wygenerować oddzielne kanały dla każdego języka.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli głównie celujesz w klientów w USA, wybierzesz „Angielski”. Jeśli celujesz również w klientów we Francji, wygenerujesz oddzielny kanał z wybranym „Francuskim”.
-   **Wybierz walutę eksportu:**

    *   **Co robi to ustawienie:** Określa, które ceny w danej walucie zostaną uwzględnione w eksportowanym kanale.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawione na USD:* Wszystkie ceny produktów w kanale będą w dolarach amerykańskich.
        *   *Gdy ustawione na EUR:* Wszystkie ceny produktów w kanale będą w euro.
    *   **Zalecana wartość:** Główna waluta Twojej docelowej grupy odbiorców dla reklam na Facebooku. Podobnie jak w przypadku języka, jeśli celujesz w wiele walut, będziesz potrzebować oddzielnych kanałów.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój sklep sprzedaje zarówno w USD, jak i CAD, i chcesz prowadzić reklamy na Facebooku dla swoich kanadyjskich klientów, wybierzesz „Dolar kanadyjski” dla tego konkretnego kanału.
-   **Eksportuj tylko aktywne produkty:**

    *   **Co robi to ustawienie:** Kontroluje, czy tylko produkty aktualnie włączone i widoczne w Twoim sklepie są uwzględniane w kanale.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone (TAK):* Eksportowane będą tylko produkty aktywne w Twoim sklepie PrestaShop. Zapobiega to wyświetlaniu reklam dla produktów niedostępnych w magazynie lub wycofanych.
        *   *Gdy wyłączone (NIE):* Wszystkie produkty, w tym nieaktywne, mogą być eksportowane. Zazwyczaj nie jest to zalecane dla aktywnych kampanii reklamowych.
    *   **Zalecana wartość:** **TAK**. Zapewnia to, że Twoje reklamy są zawsze trafne i prowadzą do dostępnych produktów.
    *   **Scenariusz/przykład dla sprzedawcy:** Masz produkty sezonowe, które są obecnie nieaktywne. Włączenie tej opcji zapewnia, że nie pojawią się one w Twoich reklamach na Facebooku, dopóki ich nie aktywujesz ponownie.
-   **Eksportuj tylko produkty dostępne w magazynie:**

    *   **Co robi to ustawienie:** Określa, czy w kanale uwzględniane są tylko produkty z dostępnym stanem magazynowym.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone (TAK):* Eksportowane będą tylko produkty, które są aktualnie dostępne w magazynie.
        *   *Gdy wyłączone (NIE):* Produkty, które są niedostępne w magazynie, mogą być eksportowane, co potencjalnie prowadzi do złego doświadczenia klienta, jeśli kliknie on reklamę niedostępnego produktu.
    *   **Zalecana wartość:** **TAK**. Zapobiega to klikaniu przez klientów reklam produktów, których nie mogą kupić, zmniejszając frustrację i marnowanie budżetu reklamowego.
    *   **Scenariusz/przykład dla sprzedawcy:** Popularny artykuł właśnie się wyczerpał. Dzięki włączeniu tej opcji zostanie on automatycznie usunięty z Twojego kanału na Facebooku, dopóki nie zostanie ponownie uzupełniony.
-   **Eksportuj kombinacje produktów (wariacje):**

    *   **Co robi to ustawienie:** Kontroluje, czy poszczególne kombinacje produktów (np. T-shirt w różnych rozmiarach i kolorach) są eksportowane jako oddzielne elementy w kanale.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone (TAK):* Każda kombinacja (np. „Czerwony T-shirt - Mały”, „Czerwony T-shirt - Średni”) pojawi się jako unikalny element w kanale, z własnym obrazem, ceną i linkiem. Jest to kluczowe dla reklam dynamicznych, aby pokazać dokładnie ten wariant, który klient oglądał.
        *   *Gdy wyłączone (NIE):* Eksportowany będzie tylko główny produkt, bez indywidualnych kombinacji. Ogranicza to szczegółowość Twoich reklam dynamicznych.
    *   **Zalecana wartość:** **TAK**. Jest to wysoce zalecane dla większości sklepów, zwłaszcza tych sprzedających odzież, elektronikę lub inne produkty z wariantami, aby zapewnić najbardziej dokładne i spersonalizowane doświadczenie reklamowe.
    *   **Scenariusz/przykład dla sprzedawcy:** Klient ogląda „Niebieską sukienkę - Dużą” na Twojej stronie. Jeśli kombinacje są eksportowane, Facebook może pokazać mu reklamę specjalnie dla tej „Niebieskiej sukienki - Dużej”.
-   **Identyfikacja produktu (pole ID):**

    *   **Co robi to ustawienie:** Określa, które pole ID PrestaShop powinno być używane jako unikalny identyfikator dla produktów w kanale Facebooka (pole `id`).
    *   **Efekt zmiany tego ustawienia:**
        *   *ID produktu:* Używa standardowego `id_product` z PrestaShop.
        *   *EAN13:* Używa kodu kreskowego EAN13.
        *   *UPC:* Używa kodu kreskowego UPC.
        *   *Referencja:* Używa wewnętrznego kodu referencyjnego produktu.
    *   **Zalecana wartość:** **ID produktu** jest zazwyczaj najbezpieczniejszą i najbardziej niezawodną opcją, ponieważ jest zawsze unikalne i wewnętrzne dla PrestaShop. Jeśli konsekwentnie używasz EAN13/UPC dla wszystkich produktów i kombinacji, te również mogą działać.
    *   **Scenariusz/przykład dla sprzedawcy:** Masz niestandardową integrację, która opiera się na `id_product` do śledzenia. Użycie „ID produktu” tutaj zapewnia spójność.
-   **Pole kategorii produktu:**

    *   **Co robi to ustawienie:** Określa, które informacje o kategorii są wysyłane do Facebooka.
    *   **Efekt zmiany tego ustawienia:**
        *   *Domyślna kategoria PrestaShop:* Używa nazwy głównej kategorii produktu.
        *   *Kategoria produktu Google:* Używa kategorii produktu Google (jeśli przypisana). Jest to często preferowane przez Facebooka dla lepszego dopasowania.
    *   **Zalecana wartość:** **Kategoria produktu Google**, jeśli masz je przypisane. W przeciwnym razie „Domyślna kategoria PrestaShop”.
    *   **Scenariusz/przykład dla sprzedawcy:** Sprzedajesz „T-shirty” w PrestaShop, ale kategoria produktu Google to „Odzież i akcesoria > Odzież > Koszule i topy > T-shirty”. Użycie kategorii Google dostarcza Facebookowi bardziej szczegółowych danych.
-   **Pole marki produktu:**

    *   **Co robi to ustawienie:** Wybiera, które pole z danych produktu powinno być używane dla atrybutu `brand` w kanale Facebooka.
    *   **Efekt zmiany tego ustawienia:**
        *   *Nazwa producenta:* Używa producenta przypisanego do produktu w PrestaShop.
        *   *Nazwa dostawcy:* Używa dostawcy przypisanego do produktu.
    *   **Zalecana wartość:** **Nazwa producenta**. Jest to najczęstsze i najbardziej logiczne pole dla „marki”.
    *   **Scenariusz/przykład dla sprzedawcy:** Sprzedajesz buty Nike. Wybranie „Nazwa producenta” prawidłowo wypełni „Nike” jako markę w Twoim kanale.
-   **Pole typu produktu:**

    *   **Co robi to ustawienie:** Określa, jakie informacje powinny być używane dla pola `product_type` w kanale Facebooka.
    *   **Efekt zmiany tego ustawienia:**
        *   *Domyślna kategoria PrestaShop:* Używa nazwy głównej kategorii produktu.
        *   *Kategoria produktu Google:* Używa kategorii produktu Google (jeśli przypisana).
    *   **Zalecana wartość:** **Kategoria produktu Google**, jeśli dostępna, w przeciwnym razie „Domyślna kategoria PrestaShop”. Pomaga to Facebookowi zrozumieć typ produktu.
    *   **Scenariusz/przykład dla sprzedawcy:** Dla produktu w „Elektronika > Smartfony”, kategoria produktu Google może być „Elektronika > Komunikacja > Telefonia > Telefony komórkowe”.
-   **Pole obrazu produktu:**

    *   **Co robi to ustawienie:** Określa, który adres URL obrazu jest używany dla `image_link` w kanale.
    *   **Efekt zmiany tego ustawienia:**
        *   *Domyślny obraz produktu:* Używa głównego obrazu przypisanego do produktu.
        *   *Obraz kombinacji (jeśli dostępny):* Jeśli eksportujesz kombinacje, użyje to konkretnego obrazu przypisanego do tej kombinacji, w przeciwnym razie domyślnego obrazu produktu.
    *   **Zalecana wartość:** **Obraz kombinacji (jeśli dostępny)**. Zapewnia to, że jeśli klient ogląda czerwoną koszulę, reklama pokazuje czerwoną koszulę, a nie tylko ogólny obraz produktu.
    *   **Scenariusz/przykład dla sprzedawcy:** Masz produkt z wieloma kombinacjami kolorów, każda z własnym obrazem. To ustawienie zapewnia wyświetlanie prawidłowego obrazu koloru w reklamie.
-   **Pole opisu produktu:**

    *   **Co robi to ustawienie:** Wybiera, które pole opisu z PrestaShop (`description` lub `short_description`) jest używane dla atrybutu `description` w kanale Facebooka.
    *   **Efekt zmiany tego ustawienia:**
        *   *Opis:* Eksportuje pełny, szczegółowy opis produktu.
        *   *Krótki opis:* Eksportuje krótkie podsumowanie produktu.
    *   **Zalecana wartość:** **Opis**. Facebook zazwyczaj preferuje bardziej szczegółowy opis dla lepszego kontekstu reklamy.
    *   **Scenariusz/przykład dla sprzedawcy:** Chcesz dostarczyć jak najwięcej informacji w swoich reklamach. Użycie pełnego opisu to zapewnia.
-   **Pole krótkiego opisu produktu:**

    *   **Co robi to ustawienie:** Wybiera, które pole opisu z PrestaShop (`description` lub `short_description`) jest używane dla atrybutu `short_description` w kanale Facebooka.
    *   **Efekt zmiany tego ustawienia:**
        *   *Opis:* Eksportuje pełny, szczegółowy opis produktu.
        *   *Krótki opis:* Eksportuje krótkie podsumowanie produktu.
    *   **Zalecana wartość:** **Krótki opis**. Jest to przydatne, jeśli kanał Facebooka wymaga zarówno długiego, jak i krótkiego opisu, lub jeśli wolisz zwięzłe podsumowanie dla niektórych formatów reklam.
    *   **Scenariusz/przykład dla sprzedawcy:** Chcesz mieć zwięzłe podsumowanie dla pola `short_description` w swoim kanale.
-   **Separator CSV:**

    *   **Co robi to ustawienie:** Określa znak używany do oddzielania wartości w generowanym pliku CSV (np. przecinek, średnik).
    *   **Efekt zmiany tego ustawienia:**
        *   *Przecinek (,):* Standardowy format CSV.
        *   *Średnik (;):* Powszechny w niektórych europejskich lokalizacjach.
    *   **Zalecana wartość:** **Przecinek (,)**. Jest to najszerzej akceptowany separator dla plików CSV, w tym przez Facebooka.
    *   **Scenariusz/przykład dla sprzedawcy:** Jeśli narzędzie importu Facebooka określa separator średnika, zmienisz go tutaj. W przeciwnym razie trzymaj się przecinka.
-   **Usuń obrazy z kanału:**

    *   **Co robi to ustawienie:** Jeśli włączone, moduł usunie linki do obrazów z generowanego kanału.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone (TAK):* Kolumny `image_link` i `additional_image_link` w kanale będą puste. Jest to generalnie NIE zalecane, ponieważ obrazy są kluczowe dla reklam dynamicznych.
        *   *Gdy wyłączone (NIE):* Linki do obrazów zostaną uwzględnione w kanale.
    *   **Zalecana wartość:** **NIE**. Obrazy są podstawą reklam wizualnych.
    *   **Scenariusz/przykład dla sprzedawcy:** To ustawienie jest rzadko przydatne, chyba że masz bardzo specyficzną, zaawansowaną konfigurację, w której obrazy są obsługiwane całkowicie oddzielnie.

#### Wyklucz produkty

Ta sekcja pozwala zapobiec włączeniu określonych produktów do Twojego kanału Facebooka.

-   **Wyklucz produkty według ID:**
    *   **Co robi to ustawienie:** Pozwala wprowadzić listę identyfikatorów produktów oddzielonych przecinkami, których nie chcesz, aby pojawiały się w Twoim katalogu produktów na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Produkty wymienione tutaj:* Zostaną całkowicie pominięte w generowanym kanale.
    *   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne produkty, których nigdy nie chcesz reklamować (np. wewnętrzne produkty testowe, usługi nieodpowiednie dla reklam dynamicznych).
    *   **Scenariusz/przykład dla sprzedawcy:** Sprzedajesz zarówno produkty fizyczne, jak i usługi cyfrowe. Możesz wykluczyć produkty usług cyfrowych z kanału, ponieważ nie pasują do formatu reklam dynamicznych.

#### Przycisk Generuj kanał

-   **Co robi ten przycisk:** Inicjuje proces generowania pliku CSV katalogu produktów na podstawie wszystkich skonfigurowanych powyżej ustawień.
-   **Efekt kliknięcia tego przycisku:** Moduł przetworzy Twoje produkty i utworzy plik CSV do pobrania. W zależności od liczby produktów, może to zająć trochę czasu.
-   **Zalecane działanie:** Kliknij ten przycisk po przejrzeniu i zapisaniu wszystkich pożądanych ustawień.
-   **Scenariusz/przykład dla sprzedawcy:** Po wprowadzeniu zmian w opisach produktów lub dodaniu nowych produktów, klikniesz ten przycisk, aby wygenerować zaktualizowany kanał dla Facebooka.

#### Przycisk Pobierz kanał

-   **Co robi ten przycisk:** Pozwala pobrać najnowszy wygenerowany plik CSV katalogu produktów na Twój komputer.
-   **Efekt kliknięcia tego przycisku:** Twoja przeglądarka pobierze plik `facebook_products.csv`.
-   **Zalecane działanie:** Pobierz plik po wygenerowaniu, a następnie prześlij go do swojego Menedżera Firmy na Facebooku.
-   **Scenariusz/przykład dla sprzedawcy:** Po wygenerowaniu kanału, pobierasz go, a następnie przechodzisz do Menedżera Firmy na Facebooku > Katalogi > Źródła danych, aby przesłać plik CSV.

### 2.2 Dedykowany ekran administracyjny: AdminExportProductsFeedController

Jest to główny ekran administracyjny, na którym zarządzasz rzeczywistym generowaniem kanału produktów i przeglądasz dane, które zostaną wyeksportowane.

**Lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > Konfiguruj „Eksport katalogu dla reklam dynamicznych Facebook Pixel” > (Ten ekran jest samym głównym interfejsem konfiguracji, często dostępnym bezpośrednio po kliknięciu „Konfiguruj”).

Ten ekran przedstawia interfejs przypominający siatkę lub formularz z różnymi opcjami kontrolującymi wyjście kanału produktów. Poniższe pola reprezentują punkty danych, które mogą być uwzględnione w Twoim katalogu produktów na Facebooku.

-   **ID:** Unikalny identyfikator produktu (na podstawie ustawienia „Identyfikacja produktu”).
-   **item\_group\_id:** Używane dla kombinacji produktów do grupowania ich pod jednym produktem nadrzędnym.
-   **Tytuł:** Nazwa produktu.
-   **Krótki opis:** Krótkie podsumowanie produktu.
-   **Opis:** Pełny opis produktu.
-   **Override:** (Prawdopodobnie wewnętrzne ustawienie modułu, nie eksportowane bezpośrednio do Facebooka).
-   **Dostępność:** Wskazuje, czy produkt jest dostępny w magazynie (`in stock`, `out of stock`).
-   **Stan magazynowy:** Aktualna ilość w magazynie.
-   **Stan:** Stan produktu (np. `new`, `used`, `refurbished`).
-   **Link do obrazu:** Adres URL głównego obrazu produktu.
-   **Additional\_image\_link:** Adresy URL dodatkowych obrazów produktu.
-   **Cena:** Aktualna cena produktu.
-   **sale\_price:** Cena promocyjna produktu (jeśli dotyczy).
-   **Marka:** Marka produktu (producent).
-   **Link:** Bezpośredni adres URL do strony produktu w Twoim sklepie.
-   **Kategoria produktu Google:** Kategoria produktu Google przypisana do produktu.
-   **product\_type:** Typ produktu (np. nazwa kategorii).
-   **gender:** Dla odzieży, docelowa płeć (np. `male`, `female`, `unisex`).
-   **size:** Dla odzieży, rozmiar produktu.
-   **age\_group:** Dla odzieży, docelowa grupa wiekowa (np. `newborn`, `infant`, `toddler`, `kids`, `adult`).

**Dostępne działania i ustawienia:**
Na tym ekranie znajdziesz różne opcje konfiguracji szczegółowo opisane w sekcji 4.1. „Zarządzana tabela / encja” odnosi się tutaj do wirtualnej tabeli danych produktów, którą moduł konstruuje przed eksportem. Nie ma bezpośredniej tabeli bazy danych zarządzanej przez ten konkretny kontroler, ale raczej przetwarza i przygotowuje dane z istniejących tabel produktów PrestaShop.

**Efekt zmian:**
Wszelkie zmiany wprowadzone w ustawieniach na tym ekranie (np. wybór innego języka, włączenie/wyłączenie eksportu kombinacji) bezpośrednio zmienią zawartość i format pliku CSV generowanego po kliknięciu przycisku „Generuj kanał”.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

1.  Okresowo (np. codziennie lub co tydzień, w zależności od tego, jak często zmienia się Twój katalog produktów) odwiedzaj tę stronę konfiguracji.
2.  Upewnij się, że ustawienia języka, waluty i produktów w magazynie/aktywnych są prawidłowe.
3.  Kliknij „Generuj kanał”, aby utworzyć zaktualizowany plik CSV.
4.  Pobierz wygenerowany plik CSV.
5.  Prześlij ten nowy plik CSV do swojego Menedżera Firmy na Facebooku, aby odświeżyć katalog produktów. Facebook oferuje również opcje planowania automatycznego pobierania z adresu URL, które można skonfigurować, gdy masz stabilny adres URL kanału (często dostarczany przez moduł lub konfigurację serwera).

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Wybierz język eksportu | Twój główny język | Określa język nazw/opisów produktów w kanale. |
| | Wybierz walutę eksportu | Twoja główna waluta | Określa walutę cen w kanale. |
| | Eksportuj tylko aktywne produkty | TAK | Uwzględnia tylko aktywne produkty, zapobiegając reklamom niedostępnych pozycji. |
| | Eksportuj tylko produkty dostępne w magazynie | TAK | Uwzględnia tylko produkty dostępne w magazynie, zapobiegając reklamom produktów wyprzedanych. |
| | Eksportuj kombinacje produktów | TAK | Eksportuje każdą wariację produktu (rozmiar, kolor) jako unikalną pozycję dla szczegółowych reklam. |
| | Identyfikacja produktu (pole ID) | ID produktu | Definiuje unikalny identyfikator dla produktów w kanale. |
| | Pole kategorii produktu | Kategoria produktu Google (jeśli dostępna) | Określa dane kategorii dla Facebooka. |
| | Pole marki produktu | Nazwa producenta | Określa dane marki dla Facebooka. |
| | Pole typu produktu | Kategoria produktu Google (jeśli dostępna) | Określa dane typu produktu dla Facebooka. |
| | Pole obrazu produktu | Obraz kombinacji (jeśli dostępny) | Zapewnia prawidłowy obraz dla wariacji produktu. |
| | Pole opisu produktu | Opis | Używa pełnego opisu produktu dla kanału. |
| | Pole krótkiego opisu produktu | Krótki opis | Używa krótkiego opisu produktu dla kanału. |
| | Separator CSV | Przecinek (,) | Znak oddzielający wartości w pliku CSV. |
| | Usuń obrazy z kanału | NIE | Uwzględnia linki do obrazów w kanale (niezbędne dla reklam). |
| | Wyklucz produkty według ID | Puste | Lista identyfikatorów produktów oddzielonych przecinkami do wykluczenia z kanału. |
| | Przycisk Generuj kanał | Kliknij po sfinalizowaniu ustawień | Tworzy plik CSV katalogu produktów. |
| | Przycisk Pobierz kanał | Kliknij po wygenerowaniu | Pobiera plik CSV na Twój komputer. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Mój wygenerowany plik kanału jest pusty lub zawiera bardzo mało produktów.**
O:

-   **Sprawdź „Eksportuj tylko aktywne produkty” i „Eksportuj tylko produkty dostępne w magazynie”:** Upewnij się, że te ustawienia nie są zbyt restrykcyjne, jeśli spodziewasz się wielu produktów.
-   **Sprawdź wybrany język i walutę:** Upewnij się, że produkty istnieją dla wybranego języka i mają ceny w wybranej walucie.
-   **Zweryfikuj widoczność produktu:** Czy Twoje produkty są faktycznie widoczne w wybranym kontekście sklepu (jeśli masz włączony tryb multi-store)?
-   **Wyczyść pamięć podręczną Smarty:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Czasami stare dane mogą zakłócać działanie.

**P: Facebook odrzuca mój kanał lub wyświetla błędy.**
O:

-   **Sprawdź separator CSV:** Upewnij się, że odpowiada on temu, czego oczekuje Facebook (zazwyczaj przecinek).
-   **Przejrzyj komunikaty o błędach Facebooka:** Menedżer Firmy na Facebooku dostarcza szczegółowe raporty błędów. Zwróć szczególną uwagę na to, które pola powodują problemy (np. brakujące linki do obrazów, nieprawidłowe ceny).
-   **Zweryfikuj linki do obrazów:** Upewnij się, że obrazy produktów są publicznie dostępne, a adresy URL są poprawne. Jeśli masz SSL (HTTPS), upewnij się, że linki do obrazów również są HTTPS.
-   **Sprawdź, czy nie ma znaków specjalnych:** Czasami nietypowe znaki w nazwach lub opisach produktów mogą powodować problemy z parsowaniem.
-   **Upewnij się, że identyfikatory są unikalne:** Ustawienie „Identyfikacja produktu” jest kluczowe. Każdy element w kanale (zwłaszcza kombinacje) potrzebuje unikalnego `id`.

**P: Moje obrazy produktów nie wyświetlają się w kanale Facebooka.**
O:

-   **Sprawdź ustawienie „Usuń obrazy z kanału”:** Upewnij się, że jest ustawione na **NIE**.
-   **Zweryfikuj adresy URL obrazów:** Otwórz kilka linków do obrazów z wygenerowanego pliku CSV w swojej przeglądarce. Czy ładują się poprawnie? Czy są dostępne spoza Twojej sieci?
-   **Obrazy kombinacji:** Jeśli używasz obrazów kombinacji, upewnij się, że są one poprawnie przypisane do kombinacji produktów w PrestaShop.

**P: Jak często powinienem generować i przesyłać nowy kanał?**
O:

-   Zależy to od tego, jak często zmienia się Twój katalog produktów.
-   **Codziennie:** Zalecane dla większości sklepów, zwłaszcza jeśli często zmieniają się stany magazynowe, aktualizacje cen lub dodawane są nowe produkty.
-   **Co tydzień:** Akceptowalne dla sklepów z bardzo stabilnym katalogiem.
-   **Automatyczne pobieranie:** Najlepszą praktyką jest skonfigurowanie Facebooka do automatycznego pobierania kanału z adresu URL. Ten moduł generuje kanał na żądanie, więc możesz potrzebować zadania cron, aby wywołać generowanie i udostępnić plik pod stałym adresem URL, aby Facebook mógł go pobrać.

**P: Moduł nie pojawia się na mojej liście modułów lub nie mogę go skonfigurować.**
O:

-   **Ponowne przesłanie:** Spróbuj ponownie przesłać plik ZIP modułu za pośrednictwem Menedżera modułów.
-   **Sprawdź uprawnienia:** Upewnij się, że folder modułu (`/modules/pixelfeed/`) i jego zawartość mają prawidłowe uprawnienia do plików (zazwyczaj 755 dla folderów, 644 dla plików).
-   **Logi błędów:** Sprawdź tryb debugowania PrestaShop i logi błędów serwera pod kątem wszelkich błędów PHP podczas instalacji lub konfiguracji.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Eksport katalogu dla reklam dynamicznych Facebook Pixel” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł stosuje standardowy wzorzec PrestaShop MVC (Model-View-Controller), koncentrując się głównie na funkcjonalności administracyjnej w celu generowania kanału produktów. Wykorzystuje podstawowe klasy PrestaShop `Product` i `Combination` do ekstrakcji danych, a następnie formatuje te dane do pliku CSV zgodnego ze specyfikacją katalogu reklam dynamicznych Facebooka. Główny plik modułu (`index.php`) działa jako punkt wejścia do konfiguracji, podczas gdy dedykowane kontrolery administracyjne obsługują złożoną logikę ekstrakcji danych i generowania kanału. Kontrolery front-office są obecne, prawdopodobnie do obsługi wygenerowanego kanału lub do konkretnych żądań AJAX.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `controllers/front/feed.php`
    *   **Nazwa klasy:** `PixelfeedFeedModuleFrontController` (lub podobna, rozszerzająca `ModuleFrontController`)
    *   **Odpowiedzialność:** Ten kontroler jest prawdopodobnie odpowiedzialny za udostępnianie wygenerowanego pliku kanału CSV za pośrednictwem publicznego adresu URL. Obsługiwałby żądania do określonej trasy (np. `twojasklep.com/module/pixelfeed/feed`) i bezpośrednio wyprowadzałby zawartość CSV. Jest to kluczowe dla zaplanowanych pobrań przez Facebooka.
-   `controllers/front/index.php`
    *   **Nazwa klasy:** `PixelfeedIndexModuleFrontController` (lub podobna, rozszerzająca `ModuleFrontController`)
    *   **Odpowiedzialność:** Może to być symbol zastępczy lub kontroler dla bardzo specyficznej, niezwiązanej z kanałem akcji front-office, chociaż główną funkcją modułu jest generowanie kanału w back-office. Potencjalnie mógłby obsługiwać żądania AJAX związane ze statusem kanału lub innymi drobnymi interakcjami.

#### Kontrolery administracyjne Back-Office

-   `controllers/admin/AdminExportProductsFeed.php`
    *   **Nazwa klasy:** `AdminExportProductsFeedController` (rozszerzająca `ModuleAdminController`)
    *   **Nazwa zakładki:** Ten kontroler jest sercem interfejsu administracyjnego modułu. Jest to główny ekran konfiguracji, na którym sprzedawcy wchodzą w interakcje z ustawieniami i wywołują generowanie kanału.
    *   **Zarządzana encja:** Nie zarządza bezpośrednio pojedynczą encją `ObjectModel`, ale raczej orkiestruje pobieranie i przetwarzanie danych `Product` i `Combination` z rdzenia PrestaShop.
    *   **Kluczowa funkcjonalność:**
        *   Obsługuje wyświetlanie formularza konfiguracji (`renderForm`).
        *   Przetwarza przesłane formularze (`postProcess`) w celu zapisania ustawień modułu (np. język, waluta, opcje eksportu).
        *   Wywołuje logikę ekstrakcji danych i generowania CSV.
        *   Zarządza wykluczaniem produktów.
        *   Pola formularza i kolumny wymienione w dokumentacji modułu (`ID`, `item_group_id`, `Title` itp.) reprezentują *strukturę wyjściową* kanału, a niekoniecznie bezpośrednie pola wejściowe w formularzu administracyjnym, chociaż wiele ustawień wpływa na te kolumny wyjściowe.
        *   Powiązane klucze konfiguracyjne: `pf_tree`, `PS_LANG_DEFAULT`, `PS_CURRENCY_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `pf_pixelfeed_products`, `pf_remember_settings`, `pf_export_not_group_combinations`, `pf_export_active`, `pf_export_instock`, `pf_export_identification`, `pf_export_category`, `pf_export_manufacturers_default`, `pf_export_type`, `pf_export_img`, `pf_export_manufacturers`, `pf_export_description_what`, `pf_export_short_description_what`, `pf_export_suppliers`, `pf_export_delimiter`, `pf_delete_images`. Są to klucze `Configuration` używane do przechowywania ustawień modułu.
-   `controllers/admin/index.php`
    *   **Nazwa klasy:** `PixelfeedAdminIndexController` (lub podobna, rozszerzająca `ModuleAdminController`)
    *   **Nazwa zakładki:** Może to być dodatkowy kontroler administracyjny, potencjalnie dla pulpitu nawigacyjnego lub prostszego widoku zarządzania, lub może to być plik dziedziczony. Biorąc pod uwagę, że `AdminExportProductsFeedController` obsługuje główną logikę, ten `index.php` może być przekierowaniem lub bardzo podstawową stroną docelową w sekcji administracyjnej.

### 4.3 Klasy i modele podstawowe (`classes/`)

Dokumentacja modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Oznacza to, że główna logika ekstrakcji danych i generowania kanału jest prawdopodobnie zawarta w głównym pliku modułu (`pixelfeed/index.php`) i `AdminExportProductsFeedController`. Bezpośrednio wykorzystuje podstawowe klasy PrestaShop `Product`, `Combination`, `Category`, `Manufacturer`, `Image` i `Tools`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `pixelfeed/lib/searchTool/views/js/autocomplete.js`
    *   **Zakres:** Back-office.
    *   **Funkcjonalność:** Prawdopodobnie zapewnia funkcję autouzupełniania dla pól wejściowych w konfiguracji administracyjnej, takich jak pole „Wyklucz produkty według ID”. Wiązałoby się to z elementami wejściowymi, wykonywałoby wywołania AJAX w celu wyszukiwania produktów i wyświetlało sugestie.
-   `pixelfeed/views/js/admin-app.js`
    *   **Zakres:** Back-office.
    *   **Funkcjonalność:** Jest to główny plik JavaScript dla interfejsu administracyjnego modułu. Obsługiwałby:
        *   Walidację i przesyłanie formularzy.
        *   Żądania AJAX do generowania kanału (do `AdminExportProductsFeedController`).
        *   Wyświetlanie wskaźników ładowania lub komunikatów o sukcesie/błędzie.
        *   Potencjalnie dynamiczne aktualizacje interfejsu użytkownika na podstawie wybranych opcji.
        *   Interakcje z Fancybox (jeśli używane do wyboru kategorii lub podobnych).

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `pixelfeed/lib/searchTool/views/css/autocomplete.css`
    *   **Zakres:** Stylizacja administracyjna back-office.
    *   **Funkcjonalność:** Stylizuje rozwijane menu autouzupełniania i pola wejściowe, zapewniając spójny wygląd i działanie w panelu administracyjnym PrestaShop.
-   `pixelfeed/views/admin-theme.css`
    *   **Zakres:** Stylizacja administracyjna back-office.
    *   **Funkcjonalność:** Zapewnia ogólną stylizację strony konfiguracji modułu, zapewniając jej dobrą integrację z motywem panelu administracyjnego PrestaShop. Może to obejmować układ, style przycisków i stylizację elementów formularza.
-   `pixelfeed/views/css/admin-app.css`
    *   **Zakres:** Stylizacja administracyjna back-office.
    *   **Funkcjonalność:** Specyficzna stylizacja dla niestandardowych elementów interfejsu użytkownika modułu, takich jak postęp generowania kanału, alerty lub wszelkie niestandardowe widżety na stronie konfiguracji.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł wykorzystuje głównie szablony Smarty dla swojego interfejsu Back Office.

#### Szablony administracyjne (`views/templates/admin/`)

-   `pixelfeed/views/templates/admin/dashboard.tpl`
    *   **Cel:** Może to być przegląd modułu przypominający pulpit nawigacyjny, potencjalnie pokazujący status kanału, datę ostatniego generowania lub szybkie linki.
-   `pixelfeed/views/templates/admin/feeds.tpl`
    *   **Cel:** Prawdopodobnie główny szablon do wyświetlania opcji generowania kanału i wyników, być może zawierający listę wygenerowanych kanałów lub dziennik.
-   `pixelfeed/views/templates/admin/form-chrome.tpl`
    *   **Cel:** Ogólny wrapper lub szablon strukturalny dla formularzy w interfejsie administracyjnym, zapewniający spójny układ i stylizację.
-   `pixelfeed/views/templates/admin/layout.tpl`
    *   **Cel:** Nadrzędny szablon układu dla stron administracyjnych modułu, definiujący ogólną strukturę, nagłówek i stopkę.

#### Inne szablony (`views/`)

-   `pixelfeed/lib/searchTool/views/scripts.tpl`
    *   **Cel:** Zawiera JavaScript dla narzędzia wyszukiwania, prawdopodobnie renderowany na końcu treści HTML lub w określonej sekcji.
-   `pixelfeed/views/categories-fancybox.tpl`
    *   **Cel:** Szablon dla modalu Fancybox, prawdopodobnie używany do wybierania kategorii do włączenia/wykluczenia z kanału lub do wyświetlania drzew kategorii.
-   `pixelfeed/views/exclude-products.tpl`
    *   **Cel:** Szablon dla sekcji, w której produkty mogą być wykluczane według ID, potencjalnie zawierający pole wejściowe autouzupełniania.
-   `pixelfeed/views/google_lang_links.tpl`
    *   **Cel:** Może być związany z wyświetlaniem linków lub informacji specyficznych dla języka, prawdopodobnie dla kategorii produktów Google.
-   `pixelfeed/views/returnAlert.tpl`
    *   **Cel:** Szablon do wyświetlania komunikatów o sukcesie, błędzie lub ostrzeżeniu dla użytkownika w interfejsie administracyjnym.
-   `pixelfeed/views/script-fancybox.tpl`
    *   **Cel:** Zawiera JavaScript do integracji Fancybox, często dla wyskakujących okien modalnych.
-   `pixelfeed/views/script.tpl`
    *   **Cel:** Ogólne włączenia JavaScript dla stron administracyjnych modułu, potencjalnie dla zmiennych globalnych lub inicjalizacji.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Dokumentacja modułu wskazuje brak niestandardowych plików SQL, co sugeruje, że nie tworzy on własnych dedykowanych tabel bazy danych. Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` PrestaShop przy użyciu kluczy z prefiksem `pf_` (np. `pf_export_active`, `pf_export_delimiter`).

#### Tabela zarejestrowanych hooków

Główną funkcją modułu jest eksport danych, a nie wyświetlanie w front-office. Wymienione hooki front-office (Header, Columns, Product, Footer) prawdopodobnie *nie* są używane do bezpośredniego wizualnego wyjścia przez ten moduł. Zamiast tego mogą być zarejestrowane dla:

-   **`displayHeader`**: Aby dołączyć niezbędne zasoby JavaScript lub CSS dla kontrolera kanału front-office modułu (jeśli bezpośrednio obsługuje kanał).
-   **Hooki `action*`**: Moduł prawdopodobnie używa hooków `action` (np. `actionProductUpdate`, `actionProductAdd`) wewnętrznie do czyszczenia pamięci podręcznej lub wywoływania monitów o ponowne generowanie w back-office, gdy dane produktu ulegają zmianie, chociaż nie są one wyraźnie wymienione w dokumentacji. Podstawowa logika modułu do generowania kanału jest zazwyczaj wywoływana ręcznie lub za pośrednictwem zadania cron, a nie bezpośrednio przez hook front-office.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` stron front-office. | Potencjalnie do ładowania JS/CSS dla obsługi kanału front-office, lub dla bardzo specyficznych, niewizualnych integracji. |
| `displayRightColumn` / `displayLeftColumn` | W bocznych kolumnach stron front-office. | Mało prawdopodobne, aby było używane do podstawowej funkcji tego modułu; ewentualnie do bloku debugowania lub bardzo niszowej funkcji niecentralnej dla generowania kanału. |
| `displayProductAdditionalInfo` / `displayProductButtons` (Strona produktu) | Na stronach produktów. | Mało prawdopodobne, aby było używane do podstawowej funkcji tego modułu. |
| `displayFooter` | W stopce stron front-office. | Mało prawdopodobne, aby było używane do podstawowej funkcji tego modułu. |
| (Implicit) `actionProductUpdate` / `actionProductAdd` / `actionProductDelete` | Po zmianie danych produktu w BO. | Do unieważnienia danych kanału w pamięci podręcznej lub monitowania administratora o ponowne wygenerowanie kanału. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Eksport katalogu dla reklam dynamicznych Facebook Pixel”, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
