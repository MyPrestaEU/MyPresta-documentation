---
title: "Tabela kombinacji na stronie produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Tabela kombinacji na stronie produktu” od MyPresta.eu."
sidebar:
  label: "Tabela kombinacji na stronie produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product page combinations table na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-combinations-table.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-page-combinations-table/)
>
> ---


# Tabela kombinacji na stronie produktu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji, na którym kontrolujesz wygląd i zachowanie tabeli kombinacji na stronach produktów.

#### Ustawienia ogólne

-   **Aktywuj funkcję filtrów**

    -   **Co robi to ustawienie:** Włącza lub wyłącza system filtrowania nad tabelą kombinacji, umożliwiając klientom szybkie zawężenie opcji na podstawie określonych wartości atrybutów (np. „Pokaż tylko czerwone koszulki”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Nad tabelą pojawi się pasek filtrów, ułatwiając klientom znajdowanie konkretnych kombinacji w dużych listach.
        -   *Po wyłączeniu:* Pasek filtrów nie będzie wyświetlany, a wszystkie kombinacje zostaną pokazane bez opcji filtrowania.
    -   **Zalecana wartość:** TAK (jeśli masz wiele kombinacji na produkt lub jeśli klienci często szukają konkretnych atrybutów).
    -   **Scenariusz / przykład dla sprzedawcy:** Sklep odzieżowy z dziesiątkami rozmiarów i kolorów dla jednej koszulki. Filtry pomagają klientom szybko znaleźć koszulki „Duże Niebieskie”.
-   **Podświetl najlepszą cenę**

    -   **Co robi to ustawienie:** Wizualnie podkreśla kombinację z najniższą ceną w tabeli, zwracając uwagę klienta na najbardziej przystępną opcję.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Wiersz odpowiadający najtańszej kombinacji zostanie podświetlony (np. innym kolorem tła).
        -   *Po wyłączeniu:* Brak specjalnego podświetlenia dla najniższej ceny.
    -   **Zalecana wartość:** TAK (może zachęcać do zakupów, podkreślając wartość).
    -   **Scenariusz / przykład dla sprzedawcy:** Produkt z różnymi pakietami lub konfiguracjami, gdzie jedna kombinacja oferuje znacznie lepszą ofertę.
-   **Wyświetl kolumnę oszczędności**

    -   **Co robi to ustawienie:** Dodaje dodatkową kolumnę do tabeli, która pokazuje kwotę lub procent, jaki klient oszczędza przy zakupie konkretnej kombinacji, szczególnie przydatne przy rabatach ilościowych lub specjalnych cenach.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Pojawi się kolumna „Oszczędności”, wyświetlająca rabat dla każdej kombinacji, jeśli ma to zastosowanie.
        -   *Po wyłączeniu:* Ta kolumna nie będzie wyświetlana.
    -   **Zalecana wartość:** TAK (jeśli często oferujesz rabaty lub masz ceny oparte na ilości).
    -   **Scenariusz / przykład dla sprzedawcy:** Sprzedaż produktu z ceną podstawową, ale niektóre kombinacje (np. kombinacja „pakietu”) mają obniżoną cenę, a Ty chcesz pokazać oszczędność.
-   **Wskazówka dotycząca progu rabatu ilościowego**

    -   **Co robi to ustawienie:** Wyświetla małą podpowiedź lub wiadomość wskazującą ilość wymaganą do odblokowania określonego rabatu, zachęcając klientów do zakupu większej ilości.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Gdy klient najedzie kursorem na pole ilości lub wejdzie w interakcję z nim, może pojawić się wskazówka „Kup 5, aby otrzymać 10% zniżki!”.
        -   *Po wyłączeniu:* Takie wskazówki nie będą wyświetlane.
    -   **Zalecana wartość:** TAK (jeśli używasz funkcji rabatów ilościowych PrestaShop).
    -   **Scenariusz / przykład dla sprzedawcy:** Sklep sprzedający artykuły biurowe, gdzie zakup 10 długopisów daje 5% zniżki, a ta wskazówka przypomina o tym klientowi.
-   **Układ kart mobilnych**

    -   **Co robi to ustawienie:** Określa, jak tabela kombinacji jest wyświetlana na urządzeniach mobilnych. Zamiast szerokiej tabeli, może przełączyć się na bardziej przyjazny dla użytkownika układ „kart”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Na smartfonach każda kombinacja będzie prezentowana jako oddzielna, ułożona pionowo karta, co ułatwia czytanie i interakcję.
        -   *Po wyłączeniu:* Moduł spróbuje wyświetlić pełną tabelę, co może wymagać przewijania poziomego na urządzeniach mobilnych, potencjalnie utrudniając użyteczność.
    -   **Zalecana wartość:** TAK (kluczowe dla responsywności mobilnej i dobrego doświadczenia użytkownika).
    -   **Scenariusz / przykład dla sprzedawcy:** Klient przegląda Twój sklep na telefonie. Układ kart zapewnia, że może łatwo zobaczyć i wybrać kombinacje bez powiększania lub nadmiernego przewijania.
-   **Kolejność kolumn**

    -   **Co robi to ustawienie:** Pozwala dostosować kolejność kolumn (np. Obraz, Numer referencyjny, Cena, Ilość) w tabeli kombinacji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Kolumny zostaną przestawione w tabeli front-office zgodnie z określoną przez Ciebie kolejnością.
    -   **Zalecana wartość:** Uporządkuj kolumny w intuicyjnej kolejności, która ma sens dla Twoich produktów (np. Obraz, Atrybuty, Cena, Ilość, Dodaj do koszyka).
    -   **Scenariusz / przykład dla sprzedawcy:** W sklepie odzieżowym możesz chcieć najpierw „Obraz”, potem „Kolor”, potem „Rozmiar”, a potem „Cena”. W przypadku elektroniki „Numer referencyjny” może być ważniejszy.
-   **Kliknij i przełącz kombinację**

    -   **Co robi to ustawienie:** Kontroluje, czy kliknięcie wiersza kombinacji w tabeli automatycznie aktualizuje główny obraz produktu, cenę i inne szczegóły na stronie produktu, aby odzwierciedlić tę konkretną kombinację.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Kliknięcie wiersza dynamicznie zaktualizuje główny wyświetlacz produktu, dając klientowi wizualne potwierdzenie jego wyboru.
        -   *Po wyłączeniu:* Główny wyświetlacz produktu nie zmieni się po kliknięciu wiersza; aktywne są tylko pole ilości i przycisk „Dodaj do koszyka” dla tego wiersza.
    -   **Zalecana wartość:** TAK (poprawia doświadczenie użytkownika, zapewniając wizualną informację zwrotną).
    -   **Scenariusz / przykład dla sprzedawcy:** Klient klika kombinację „Czerwony, Duży”, a główny obraz produktu natychmiast przełącza się na czerwoną wersję produktu.

#### Ustawienia obrazów

-   **Wyświetl obraz**

    -   **Co robi to ustawienie:** Określa, czy w tabeli ma być wyświetlana miniatura obrazu dla każdej kombinacji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Pojawi się kolumna obrazu, pokazująca konkretny obraz powiązany z każdą kombinacją (jeśli jest dostępny).
        -   *Po wyłączeniu:* Kolumna obrazu nie będzie wyświetlana.
    -   **Zalecana wartość:** TAK (wizualizacje są potężne przy wyborze produktu).
    -   **Scenariusz / przykład dla sprzedawcy:** Sklep odzieżowy, gdzie każda wariacja kolorystyczna ma odrębny obraz.
-   **Wyświetl kolumnę obrazu, jeśli istnieje co najmniej jedna kombinacja ze zdjęciem**

    -   **Co robi to ustawienie:** Kontroluje widoczność kolumny obrazu w zależności od tego, czy jakakolwiek kombinacja ma przypisany konkretny obraz.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Jeśli choć jedna kombinacja ma obraz, kolumna obrazu pojawi się dla wszystkich kombinacji (pokazując domyślny obraz produktu dla tych bez specyficznych obrazów kombinacji).
        -   *Po wyłączeniu:* Kolumna obrazu pojawi się tylko wtedy, gdy *wszystkie* kombinacje mają specyficzne obrazy, lub może nie pojawić się wcale, jeśli ostrożnie używasz również opcji „Użyj domyślnego obrazu produktu”.
    -   **Zalecana wartość:** TAK (zapobiega pustej kolumnie obrazu, jeśli tylko kilka kombinacji ma obrazy).
    -   **Scenariusz / przykład dla sprzedawcy:** Masz 20 kombinacji, ale tylko 5 ma unikalne obrazy. To zapewnia, że kolumna obrazu nadal się pojawia, używając głównego obrazu produktu dla pozostałych 15.
-   **Użyj domyślnego obrazu produktu**

    -   **Co robi to ustawienie:** Jeśli konkretna kombinacja nie ma własnego obrazu, to ustawienie określa, czy główny obraz produktu powinien być użyty jako zamiennik.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Kombinacje bez specyficznych obrazów będą wyświetlać główny obraz produktu.
        -   *Po wyłączeniu:* Kombinacje bez specyficznych obrazów będą wyświetlać symbol zastępczy lub brak obrazu.
    -   **Zalecana wartość:** TAK (zapewnia, że wszystkie kombinacje mają wizualną reprezentację).
    -   **Scenariusz / przykład dla sprzedawcy:** Produkt z wieloma wariantami rozmiarów, ale tylko jednym obrazem na kolor. To zapewnia, że wszystkie rozmiary danego koloru pokazują prawidłowy obraz koloru.
-   **Włącz powiększenie Fancybox**

    -   **Co robi to ustawienie:** Pozwala klientom klikać obrazy kombinacji w tabeli, aby wyświetlić większą, powiększoną wersję w wyskakującym okienku (Fancybox).
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Kliknięcie obrazu kombinacji otworzy go w wyskakującym okienku Fancybox.
        -   *Po wyłączeniu:* Obrazy nie będą klikalne w celu powiększenia.
    -   **Zalecana wartość:** TAK (poprawia doświadczenie przeglądania obrazów).
    -   **Scenariusz / przykład dla sprzedawcy:** Klient chce dokładniej zobaczyć teksturę lub szczegóły konkretnej wariacji kolorystycznej.
-   **Typ obrazu do wyświetlenia**

    -   **Co robi to ustawienie:** Wybiera rozmiar/typ obrazu (np. `small_default`, `medium_default`) do wyświetlenia jako miniatury w tabeli kombinacji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Rozmiar obrazów w tabeli zostanie zaktualizowany do wybranego typu obrazu.
    -   **Zalecana wartość:** `small_default` lub `medium_default` (wybierz taki, który dobrze pasuje do układu tabeli, nie będąc ani za dużym, ani za małym).
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby obrazy w tabeli były nieco większe niż maleńkie `small_default`, ale nie tak duże jak `large_default`.
-   **Typ obrazu używany do powiększania miniatury**

    -   **Co robi to ustawienie:** Wybiera rozmiar/typ obrazu, który ma być używany, gdy funkcja powiększenia Fancybox jest aktywna.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Obraz wyświetlany w wyskakującym okienku Fancybox będzie miał wybrany rozmiar.
    -   **Zalecana wartość:** `large_default` lub `thickbox_default` (wybierz największy, najwyższej jakości typ obrazu do powiększania).
    -   **Scenariusz / przykład dla sprzedawcy:** Klient powiększa obraz i oczekuje, że zobaczy wersję o wysokiej rozdzielczości.

#### Ustawienia wyświetlania atrybutów

-   **Metoda wyświetlania atrybutów**

    -   **Co robi to ustawienie:** Kontroluje sposób wyświetlania nazw atrybutów (np. „Rozmiar”, „Kolor”) w nagłówku tabeli.
    -   **Efekt zmiany tego ustawienia:**
        -   *Opcje (np. „Pełna nazwa”, „Krótka nazwa”, „ID”):* Zmienia sposób wyświetlania nagłówków atrybutów.
    -   **Zalecana wartość:** „Pełna nazwa” (najbardziej opisowa dla klientów).
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby „Rozmiar” pojawiał się jako „Rozmiar”, a nie „S” lub „ID: 1”.
-   **Powiązania atrybutów ze sklepem (multistore)**

    -   **Co robi to ustawienie:** W środowisku multistore pozwala określić, które grupy atrybutów są istotne dla których sklepów, zapobiegając pojawianiu się nieistotnych atrybutów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po skonfigurowaniu:* W tabeli będą wyświetlane tylko atrybuty powiązane z bieżącym kontekstem sklepu.
    -   **Zalecana wartość:** Skonfiguruj ostrożnie, jeśli prowadzisz multistore z różnymi katalogami produktów.
    -   **Scenariusz / przykład dla sprzedawcy:** Sklep A sprzedaje ubrania (Rozmiar, Kolor), Sklep B sprzedaje elektronikę (Pamięć, RAM). To zapobiega pojawianiu się „Pamięci” w tabeli kombinacji Sklepu A.
-   **Dołącz etykietę do nazwy atrybutu**

    -   **Co robi to ustawienie:** Dodaje nazwę grupy atrybutów jako prefiks do wartości atrybutu (np. „Rozmiar: S”, „Kolor: Czerwony”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Wartości atrybutów będą bardziej opisowe.
        -   *Po wyłączeniu:* Wyświetlana będzie tylko wartość atrybutu (np. „S”, „Czerwony”).
    -   **Zalecana wartość:** TAK (poprawia przejrzystość, zwłaszcza jeśli wartości atrybutów nie są oczywiste).
    -   **Scenariusz / przykład dla sprzedawcy:** Produkt ma wartość atrybutu „Standard”. Czy to standardowy rozmiar, standardowy kolor czy standardowe wykończenie? „Wykończenie: Standard” to wyjaśnia.
-   **Atrybut koloru**

    -   **Co robi to ustawienie:** Pozwala określić, która grupa atrybutów reprezentuje „kolor” w Twoim sklepie. Jest to ważne, aby moduł poprawnie wyświetlał próbki kolorów lub logikę specyficzną dla koloru.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wybraniu:* Moduł będzie traktował wartości z tej grupy atrybutów jako kolory, potencjalnie wyświetlając je jako próbki kolorów zamiast tekstu.
    -   **Zalecana wartość:** Wybierz swoją główną grupę atrybutów „Kolor”.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz grupę atrybutów o nazwie „Kolor” z wartościami takimi jak „Czerwony”, „Niebieski”, „Zielony”. Wybranie tej grupy zapewnia, że są one wyświetlane jako rzeczywiste próbki kolorów.

#### Opcje wyświetlania

-   **Ukryj nagłówek tabeli**

    -   **Co robi to ustawienie:** Usuwa wiersz nagłówka z tabeli kombinacji (np. „Obraz | Rozmiar | Kolor | Cena | Ilość”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Tabela rozpocznie się bezpośrednio od wierszy kombinacji, bez tytułów kolumn.
        -   *Po wyłączeniu:* Wiersz nagłówka będzie widoczny.
    -   **Zalecana wartość:** NIE (nagłówki są zazwyczaj ważne dla przejrzystości, chyba że Twoja tabela jest bardzo prosta i oczywista).
    -   **Scenariusz / przykład dla sprzedawcy:** Dla bardzo prostego produktu z tylko jednym atrybutem (np. „Rozmiar opakowania”) możesz ukryć nagłówek, jeśli zawartość kolumny jest oczywista.
-   **Ukryj kombinacje niedostępne w magazynie**

    -   **Co robi to ustawienie:** Zapobiega wyświetlaniu w tabeli kombinacji, które są obecnie niedostępne w magazynie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Widoczne będą tylko kombinacje dostępne w magazynie, co zmniejsza bałagan i zapobiega frustracji klientów.
        -   *Po wyłączeniu:* Kombinacje niedostępne w magazynie będą nadal wyświetlane, często z etykietą „Wyprzedane” lub wyłączonym przyciskiem „Dodaj do koszyka”.
    -   **Zalecana wartość:** TAK (ogólnie lepsze dla doświadczenia użytkownika, chyba że chcesz pokazać wszystkie opcje dla zamówień przedpremierowych lub powiadomień o ponownej dostępności).
    -   **Scenariusz / przykład dla sprzedawcy:** Popularny model butów wyprzedał się w rozmiarze 10. Ukrycie go zapobiega próbom jego wyboru przez klientów.
-   **Ukryj kombinacje z ceną = 0**

    -   **Co robi to ustawienie:** Wyklucza z wyświetlania w tabeli kombinacje, które mają cenę zero.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Kombinacje z ceną zero nie pojawią się.
        -   *Po wyłączeniu:* Kombinacje z ceną zero zostaną wyświetlone.
    -   **Zalecana wartość:** TAK (chyba że celowo oferujesz darmowe kombinacje, co jest rzadkie).
    -   **Scenariusz / przykład dla sprzedawcy:** Czasami, z powodu błędnej konfiguracji, kombinacja może mieć cenę zero. Ukrycie ich zapobiega zamieszaniu.
-   **Pokaż tylko kombinacje ze zdjęciami**

    -   **Co robi to ustawienie:** Filtruje tabelę, aby wyświetlać tylko kombinacje, które mają przypisany konkretny obraz.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Wyświetlane będą tylko kombinacje z unikalnymi obrazami.
        -   *Po wyłączeniu:* Wyświetlane będą wszystkie kombinacje, niezależnie od tego, czy mają konkretny obraz.
    -   **Zalecana wartość:** NIE (zazwyczaj lepiej jest pokazywać wszystkie kombinacje, używając domyślnych obrazów, jeśli to konieczne, chyba że wizualne rozróżnienie jest najważniejsze).
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz pokazać tylko kombinacje, które mają wyraźne różnice wizualne, a nie przesłałeś obrazów dla wszystkich z nich.
-   **Wyświetl cenę**

    -   **Co robi to ustawienie:** Kontroluje, czy cena dla każdej kombinacji jest wyświetlana w tabeli.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Kolumna „Cena” będzie widoczna.
        -   *Po wyłączeniu:* Kolumna ceny zostanie ukryta.
    -   **Zalecana wartość:** TAK (cena jest kluczowym czynnikiem dla klientów).
    -   **Scenariusz / przykład dla sprzedawcy:** Klient chce porównać ceny różnych rozmiarów lub materiałów produktu.
-   **Wyświetl cenę jednostkową**

    -   **Co robi to ustawienie:** Pokazuje cenę jednostkową (np. cenę za kg, za litr) dla każdej kombinacji, jeśli ma to zastosowanie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Pojawi się dodatkowa kolumna „Cena jednostkowa”.
        -   *Po wyłączeniu:* Ta kolumna nie będzie wyświetlana.
    -   **Zalecana wartość:** TAK (jeśli Twoje produkty są sprzedawane na wagę/objętość, a ceny jednostkowe są istotne).
    -   **Scenariusz / przykład dla sprzedawcy:** Sprzedaż ziaren kawy w różnych rozmiarach opakowań, a klienci chcą porównać cenę za 100g.
-   **Wyświetl cenę tylko dla zalogowanych klientów**

    -   **Co robi to ustawienie:** Ukrywa ceny kombinacji przed odwiedzającymi, którzy nie są zalogowani na swoje konta klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Goście nie zobaczą cen; mogą zobaczyć wiadomość z prośbą o zalogowanie się.
        -   *Po wyłączeniu:* Ceny są widoczne dla wszystkich.
    -   **Zalecana wartość:** NIE (chyba że prowadzisz sklep B2B lub masz specyficzne strategie cenowe wymagające logowania).
    -   **Scenariusz / przykład dla sprzedawcy:** Sklep hurtowy, gdzie ceny są negocjowane lub specyficzne dla zarejestrowanych kont biznesowych.
-   **Pokaż etykietę podatku**

    -   **Co robi to ustawienie:** Wyświetla etykietę wskazującą, czy wyświetlane ceny zawierają podatek, czy go nie zawierają (np. „Cena brutto”, „Cena netto”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Status podatku będzie wyraźnie wskazany obok cen.
        -   *Po wyłączeniu:* Etykieta podatku nie będzie wyświetlana.
    -   **Zalecana wartość:** TAK (poprawia przejrzystość i jest zgodne z wymogami prawnymi w wielu regionach).
    -   **Scenariusz / przykład dla sprzedawcy:** Klienci w Europie oczekują cen „Cena brutto”, podczas gdy klienci B2B mogą preferować „Cena netto”.

#### Inne klucze konfiguracyjne (zaawansowane/wewnętrzne)

Te ustawienia są zazwyczaj zarządzane wewnętrznie przez moduł lub są rzadziej dostosowywane przez sprzedawców.

-   `mypresta_updates`, `update_`, `updatev_`: Wewnętrzne klucze do aktualizacji modułu i śledzenia wersji.
-   `ctp_position`: Kontroluje pozycję haka, w którym wyświetlana jest tabela.
-   `ctp_lasttab`: Związane z wyświetlaniem tabeli w zakładce produktu.
-   `ctp_reference`, `ctp_ean`, `ctp_mpn`: Kontrolują wyświetlanie kolumn Numer referencyjny, EAN13/JAN i MPN.
-   `ctp_cname`: Kontroluje wyświetlanie nazwy kombinacji.
-   `ctp_atc`, `ctp_atcq`: Kontrolują przycisk „Dodaj do koszyka” i pole ilości.
-   `ctp_ajax`: Określa, czy AJAX jest używany do dodawania do koszyka.
-   `ctp_sort`: Opcje sortowania kombinacji w tabeli.
-   `ctp_quantity`, `ctp_quantity_sum`: Wyświetlanie ilości zapasów i sumy ilości.
-   `ctp_availability`, `ctp_availability_d`: Wyświetlanie statusu dostępności i daty.
-   `ctp_imagetype`, `ctp_imagetype_zoom`, `ctp_grid_imagetype`, `ctp_grid_defimg`: Ustawienia typu obrazu (omówione powyżej).
-   `ctp_attributes_method`: Metoda wyświetlania atrybutów (omówiona powyżej).
-   `ctp_prices_tax`: Ustawienia wyświetlania podatku (omówione powyżej).
-   `ctp_color_method`: Sposób wyświetlania atrybutów koloru (np. próbki).
-   `ctp_hide_default`, `ctp_hide_r`: Ukryj domyślną kombinację, ukryj kombinacje z zerową ceną (omówione powyżej).
-   `ctp_where`, `ctp_tabtype`: Umiejscowienie tabeli (hak, typ zakładki).
-   `ctp_quantity_pm`: Przyciski plus/minus dla pola ilości.
-   `ctp_view_mode`: Ogólny tryb widoku tabeli (tabela, siatka itp.).
-   `ctp_grid_row_attr`, `ctp_grid_col_attr`: Ustawienia dla układu siatki (które atrybuty tworzą wiersze/kolumny).

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### AdminCombinationstabSearchController (Panel administracyjny > Moduły > Tabela kombinacji na stronie produktu > Wyszukaj)

Ten kontroler zapewnia dedykowany interfejs w panelu administracyjnym PrestaShop, prawdopodobnie do zarządzania lub wyszukiwania kombinacji, potencjalnie dla wielu produktów, lub do zaawansowanej konfiguracji związanej z wyświetlaniem kombinacji.

-   **Nazwa ekranu i lokalizacja w menu:** Zazwyczaj znajdziesz nową pozycję menu w **Moduły > Tabela kombinacji na stronie produktu** (lub podobnie, w zależności od wersji PrestaShop) oznaczoną jako „Wyszukaj” lub „Wyszukiwanie kombinacji”.
-   **Dostępne akcje i ustawienia:** Ten ekran prawdopodobnie przedstawia siatkę lub widok zarządzania kombinacjami produktów. Może pozwalać na:
    -   Wyszukiwanie konkretnych kombinacji według atrybutów, numeru referencyjnego, EAN lub nazwy produktu.
    -   Przeglądanie szczegółów kombinacji, takich jak stan magazynowy, cena i powiązany produkt.
    -   Potencjalnie wykonywanie działań masowych, takich jak aktualizacja stanu magazynowego lub ceny dla wielu kombinacji (chociaż jest to często obsługiwane przez podstawową stronę produktu PrestaShop).
    -   Ten ekran służy przede wszystkim do *zarządzania* i *przeglądania* danych kombinacji w ustrukturyzowany sposób, oddzielnie od głównej strony edycji produktu.
-   **Efekt zmian:** Wszelkie zmiany wprowadzone tutaj (jeśli edycja jest włączona) bezpośrednio zaktualizują dane kombinacji w Twojej bazie danych PrestaShop, wpływając na ceny, stan magazynowy i dostępność w front-office.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj tego ekranu, aby szybko sprawdzić dane kombinacji, znaleźć konkretne kombinacje lub zweryfikować poziomy zapasów bez przechodzenia do poszczególnych stron produktów. Jest to potężne narzędzie dla sklepów z dużym katalogiem produktów i kombinacji.

#### index.php (combinationstab/controllers/admin/index.php)

Ten plik zazwyczaj służy jako symbol zastępczy lub przekierowanie do głównego kontrolera administracyjnego modułu. Może po prostu ładować `AdminCombinationstabSearchController` lub prezentować podstawową stronę docelową dla sekcji administracyjnej modułu. Zazwyczaj nie ma bezpośrednich ustawień konfigurowalnych, ale działa jako punkt wejścia.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Aktywuj funkcję filtrów | TAK | Włącza filtry atrybutów dla tabeli kombinacji. |
| | Podświetl najlepszą cenę | TAK | Wizualnie podświetla kombinację z najniższą ceną. |
| | Wyświetl kolumnę oszczędności | TAK | Pokazuje kwotę/procent rabatu w dedykowanej kolumnie. |
| | Wskazówka dotycząca progu rabatu ilościowego | TAK | Wyświetla wskazówki dotyczące rabatów ilościowych. |
| | Układ kart mobilnych | TAK | Optymalizuje wyświetlanie tabeli dla urządzeń mobilnych. |
| | Kolejność kolumn | Możliwość dostosowania | Definiuje kolejność kolumn w tabeli. |
| | Kliknij i przełącz kombinację | TAK | Aktualizuje główny obraz produktu/szczegóły po kliknięciu wiersza. |
| | Wyświetl obraz | TAK | Pokazuje obrazy kombinacji w tabeli. |
| | Wyświetl kolumnę obrazu, jeśli istnieje co najmniej jedna kombinacja ze zdjęciem | TAK | Zapewnia, że kolumna obrazu pojawi się, jeśli jakakolwiek kombinacja ma obraz. |
| | Użyj domyślnego obrazu produktu | TAK | Powrót do głównego obrazu produktu, jeśli kombinacja nie ma specyficznego obrazu. |
| | Włącz powiększenie Fancybox | TAK | Umożliwia powiększanie obrazów kombinacji. |
| | Typ obrazu do wyświetlenia | `medium_default` | Ustawia rozmiar miniatury w tabeli. |
| | Typ obrazu używany do powiększania miniatury | `large_default` | Ustawia rozmiar obrazu powiększonego. |
| | Metoda wyświetlania atrybutów | Pełna nazwa | Jak są etykietowane nagłówki atrybutów (np. „Rozmiar”). |
| | Powiązania atrybutów ze sklepem (multistore) | Skonfiguruj według potrzeb | Filtruje atrybuty według sklepu w multistore. |
| | Dołącz etykietę do nazwy atrybutu | TAK | Dodaje nazwę grupy atrybutów do wartości (np. „Rozmiar: S”). |
| | Atrybut koloru | Wybierz swój atrybut Kolor | Identyfikuje atrybut koloru dla specjalnego wyświetlania. |
| | Ukryj nagłówek tabeli | NIE | Utrzymuje widoczność tytułów kolumn dla przejrzystości. |
| | Ukryj kombinacje niedostępne w magazynie | TAK | Usuwa niedostępne kombinacje z tabeli. |
| | Ukryj kombinacje z ceną = 0 | TAK | Usuwa kombinacje z zerową ceną. |
| | Pokaż tylko kombinacje ze zdjęciami | NIE | Wyświetla wszystkie kombinacje, używając domyślnych obrazów, jeśli to konieczne. |
| | Wyświetl cenę | TAK | Pokazuje cenę dla każdej kombinacji. |
| | Wyświetl cenę jednostkową | TAK (jeśli dotyczy) | Pokazuje cenę za jednostkę (np. za kg). |
| | Wyświetl cenę tylko dla zalogowanych klientów | NIE | Sprawia, że ceny są widoczne dla wszystkich odwiedzających. |
| | Pokaż etykietę podatku | TAK | Wskazuje, czy ceny zawierają/nie zawierają podatku. |
| **AdminCombinationstabSearchController** | Widok siatki / zarządzania | N/A | Wyszukuj, przeglądaj i potencjalnie zarządzaj kombinacjami dla wielu produktów. |

## 3. Rozwiązywanie problemów przez sprzedawcę i często zadawane pytania (FAQ)

**P1: Tabela kombinacji nie wyświetla się na mojej stronie produktu.**
O1:

-   **Sprawdź pozycję modułu:** Przejdź do **Wygląd > Pozycje** (lub **Moduły > Pozycje** w starszych wersjach PrestaShop) w Panelu administracyjnym. Wyszukaj moduł „Tabela kombinacji na stronie produktu”. Upewnij się, że jest on podpięty do odpowiedniego haka wyświetlania, takiego jak `displayProductFooter`, `displayProductExtraContent` lub `displayProductTabContent`. Jeśli nie, kliknij „Przeszczep moduł” i dodaj go do żądanego haka.
-   **Konfiguracja modułu:** Dokładnie sprawdź stronę konfiguracji modułu, aby upewnić się, że jest włączony i nie jest ukryty przez inne ustawienia (np. „Ukryj kombinacje z ceną = 0” może ukryć wszystkie, jeśli wszystkie są zerowe).
-   **Produkt ma kombinacje:** Upewnij się, że przeglądany produkt faktycznie ma zdefiniowane kombinacje w swoich ustawieniach produktu.
-   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Czasami stare, buforowane treści uniemożliwiają wyświetlanie nowych modułów.

**P2: Moje obrazy kombinacji nie pojawiają się lub mają niewłaściwy rozmiar.**
O2:

-   **Ustawienia obrazów:** Przejrzyj ustawienia „Typ obrazu do wyświetlenia” i „Typ obrazu używany do powiększania miniatury” w konfiguracji modułu. Upewnij się, że wybrałeś odpowiednie typy obrazów, które istnieją w Twoim motywie PrestaShop.
-   **Przesłane obrazy kombinacji:** Sprawdź, czy faktycznie przesłałeś konkretne obrazy dla swoich kombinacji produktów w zakładce „Kombinacje” produktu w Panelu administracyjnym. Jeśli nie, moduł powróci do głównego obrazu produktu (jeśli włączono „Użyj domyślnego obrazu produktu”).
-   **Wygeneruj ponownie miniatury:** Jeśli zmieniłeś typy obrazów lub przesłałeś nowe obrazy, przejdź do **Wygląd > Ustawienia obrazów** (lub **Preferencje > Obrazy**) i kliknij „Wygeneruj ponownie miniatury” dla odpowiednich typów obrazów (np. `medium_default`, `large_default`).

**P3: Tabela wygląda dziwnie lub jest źle wyrównana w moim niestandardowym motywie.**
O3:

-   **Konflikty CSS:** Niestandardowe motywy czasami mają sprzeczne style CSS. Ten moduł stara się być kompatybilny, ale mogą być potrzebne drobne korekty.
-   **Skontaktuj się z pomocą techniczną:** Jeśli czujesz się komfortowo z CSS, możesz zbadać elementy za pomocą narzędzi deweloperskich przeglądarki i spróbować nadpisać sprzeczne style. W przeciwnym razie skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojego motywu i zrzut ekranu; często mogą oni zapewnić szybkie rozwiązanie.
-   **Aktualizacje modułu:** Upewnij się, że używasz najnowszej wersji modułu, ponieważ ulepszenia kompatybilności są często uwzględniane w aktualizacjach.

**P4: Ceny nie wyświetlają się poprawnie lub są ukryte.**
O4:

-   **Ustawienia wyświetlania cen:** Sprawdź „Wyświetl cenę” i „Wyświetl cenę tylko dla zalogowanych klientów” w konfiguracji modułu. Jeśli to drugie jest włączone, upewnij się, że jesteś zalogowany jako klient, aby zobaczyć ceny.
-   **Podstawowe ceny PrestaShop:** Sprawdź, czy ceny dla Twoich kombinacji są poprawnie ustawione w zakładce „Kombinacje” produktu.
-   **Ustawienia podatków:** Sprawdź „Pokaż etykietę podatku” i ogólne ustawienia podatków PrestaShop (**Międzynarodowe > Podatki**), aby upewnić się, że ceny są obliczane i wyświetlane zgodnie z oczekiwaniami (z podatkiem/bez podatku).

**P5: Jak zmienić kolejność atrybutów w tabeli?**
O5:

-   Ustawienie „Kolejność kolumn” modułu pozwala na zmianę kolejności kolumn. Jeśli chodzi o kolejność samych atrybutów (np. „Rozmiar” przed „Kolorem”), jest to zazwyczaj zarządzane w podstawowej konfiguracji PrestaShop: **Katalog > Atrybuty i cechy > Atrybuty** oraz **Grupy atrybutów**. Ustawiona tam kolejność zazwyczaj wpływa na to, jak pojawiają się one w tabeli modułu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Tabela kombinacji na stronie produktu” (`combinationstab`) jest zgodny ze standardową architekturą modułów PrestaShop, w dużym stopniu wykorzystując haki do wyświetlania w front-office i niestandardowe kontrolery administracyjne do zaawansowanej konfiguracji i zarządzania danymi. Głęboko integruje się z podstawowymi danymi produktów i kombinacji PrestaShop, dynamicznie renderując tabele HTML lub siatki za pomocą szablonów Smarty. AJAX jest używany do funkcji takich jak „Dodaj do koszyka” i przełączanie kombinacji, zapewniając płynne doświadczenie użytkownika. Moduł nie wprowadza niestandardowych klas `ObjectModel`, ale pracuje bezpośrednio z istniejącymi obiektami `Product` i `Combination`.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery obsługują specyficzne żądania AJAX lub dedykowane funkcjonalności front-office.

-   `controllers/front/BackInStock.php`
    -   **Nazwa klasy i klasa nadrzędna:** `CombinationstabBackInStockModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Prawdopodobnie obsługuje żądania AJAX związane z powiadomieniami „o ponownej dostępności” dla konkretnych kombinacji. Może to obejmować przesłanie formularza w celu zarejestrowania się do powiadomień, gdy niedostępna kombinacja stanie się dostępna.
-   `controllers/front/CsvImport.php`
    -   **Nazwa klasy i klasa nadrzędna:** `CombinationstabCsvImportModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Sugeruje funkcjonalność importowania danych kombinacji za pośrednictwem CSV z front-office, prawdopodobnie dla określonych grup użytkowników lub scenariuszy B2B. Obejmowałoby to parsowanie plików CSV i aktualizowanie kombinacji produktów.
-   `controllers/front/Export.php`
    -   **Nazwa klasy i klasa nadrzędna:** `CombinationstabExportModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Zapewnia funkcjonalność eksportowania danych kombinacji, potencjalnie dla konkretnych produktów lub filtrowanych zestawów, prawdopodobnie w formacie CSV lub podobnym. Przydatne dla B2B lub analizy danych.
-   `controllers/front/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `CombinationstabIndexModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Często symbol zastępczy lub domyślny dispatcher. Może obsługiwać ogólne żądania AJAX związane z tabelą kombinacji, które nie pasują do bardziej specyficznych kontrolerów, lub po prostu przekierowywać.
-   `controllers/front/PriceCalculator.php`
    -   **Nazwa klasy i klasa nadrzędna:** `CombinationstabPriceCalculatorModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Obsługuje żądania AJAX w celu dynamicznego obliczania i zwracania cen dla kombinacji, szczególnie istotne dla rabatów ilościowych lub złożonych zasad cenowych, zapewniając aktualizacje cen w czasie rzeczywistym bez przeładowywania strony.
-   `controllers/front/Reorder.php`
    -   **Nazwa klasy i klasa nadrzędna:** `CombinationstabReorderModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Prawdopodobnie ułatwia ponowne zamawianie wcześniej zakupionych kombinacji, potencjalnie ze strony konta klienta lub dedykowanej listy „ponownych zamówień”.
-   `controllers/front/Wishlist.php`
    -   **Nazwa klasy i klasa nadrzędna:** `CombinationstabWishlistModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Zarządza interakcjami AJAX z funkcją listy życzeń zintegrowaną z tabelą kombinacji, umożliwiając klientom dodawanie konkretnych kombinacji do swojej listy życzeń.

#### Kontrolery administracyjne Back-Office

Te kontrolery zapewniają interfejs administracyjny dla modułu.

-   `controllers/admin/AdminCombinationstabSearchController.php`
    -   **Nazwa zakładki i zarządzana encja:** „Wyszukiwanie kombinacji” (lub podobnie, dostępne za pośrednictwem menu modułu). Zarządza kombinacjami `Product`.
    -   **Odpowiedzialność:** Implementuje interfejs wyszukiwania i zarządzania kombinacjami produktów. Ten kontroler prawdopodobnie używa `HelperList` lub `HelperForm` do wyświetlania filtrowalnej i sortowalnej siatki kombinacji, umożliwiając administratorom szybkie znajdowanie i potencjalnie edytowanie danych kombinacji (np. stan magazynowy, cena, numer referencyjny) bez przechodzenia do poszczególnych stron produktów. Może również obsługiwać działania masowe.
-   `controllers/admin/index.php`
    -   **Nazwa zakładki i zarządzana encja:** N/A (punkt wejścia).
    -   **Odpowiedzialność:** Typowy wzorzec dla katalogów kontrolerów administracyjnych. Ten plik zazwyczaj służy jako domyślny punkt wejścia lub przekierowanie do głównego `AdminCombinationstabSearchController`. Zazwyczaj nie zawiera bezpośredniej logiki, ale zapewnia, że pozycja menu administracyjnego wskazuje na prawidłowy kontroler.

### 4.3 Klasy i modele podstawowe (`classes/`)

Dossier modułu nie wskazuje na niestandardowe klasy w katalogu `classes/`. Sugeruje to, że moduł przede wszystkim rozszerza istniejące podstawowe funkcjonalności i obiekty PrestaShop (`Product`, `Combination`, `Attribute`, `AttributeGroup`), zamiast wprowadzać nowe modele danych. Cała logika biznesowa jest prawdopodobnie hermetyzowana w głównym pliku `combinationstab.php` i jego kontrolerach.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł wykorzystuje różne pliki JavaScript do zapewnienia dynamicznej funkcjonalności front-office i back-office.

-   `combinationstab/js/admin.js`
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Obsługuje logikę JavaScript dla stron administracyjnych modułu, w tym interakcje z formularzami, wywołania AJAX dla aktualizacji konfiguracji i potencjalnie dynamiczne elementy w interfejsie `AdminCombinationstabSearchController`.
-   `combinationstab/js/atc.js`
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Zarządza funkcjonalnością „Dodaj do koszyka” dla tabeli kombinacji. Wiąże zdarzenia kliknięcia z przyciskami „Dodaj do koszyka”, obsługuje pola ilości i wysyła żądania AJAX do kontrolera koszyka PrestaShop w celu dodania wybranych kombinacji (potencjalnie wielu naraz) bez przeładowywania strony.
-   `combinationstab/js/combinationstab-switch.js`
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Implementuje funkcję „Kliknij i przełącz kombinację”. Nasłuchuje kliknięć w wierszach kombinacji w tabeli i dynamicznie aktualizuje główny obraz produktu, cenę i inne szczegóły produktu na stronie, aby odzwierciedlić wybraną kombinację.
-   `combinationstab/js/combinationstab.js`
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Główny plik JavaScript front-office dla tabeli kombinacji. Inicjalizuje tabelę, obsługuje ogólne interakcje, potencjalnie zarządza wyświetlaniem stanu magazynowego, dostępności i aktualizacji cen na podstawie danych wejściowych lub wyborów użytkownika.
-   `combinationstab/js/ctp-extras.js`
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Zawiera dodatkowe, niepodstawowe funkcjonalności JavaScript dla tabeli kombinacji, takie jak wyświetlanie podpowiedzi, drobne ulepszenia interfejsu użytkownika lub specyficzne interakcje nieobjęte głównymi skryptami.
-   `combinationstab/js/ctp-filters.js`
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Implementuje logikę filtrowania dla tabeli kombinacji. Nasłuchuje zmian w rozwijanych listach filtrów lub polach wejściowych, dynamicznie ukrywa/pokazuje wiersze tabeli na podstawie wybranych wartości atrybutów i aktualizuje widoczne kombinacje.
-   `combinationstab/js/ctp-mobile.js`
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Obsługuje responsywne zachowanie tabeli kombinacji, w szczególności implementując funkcję „Układ kart mobilnych”. Wykrywa rozmiar ekranu i przekształca tabelę w układ oparty na kartach dla lepszej użyteczności mobilnej.
-   `combinationstab/js/ctp-wishlist-toast.js`
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Zapewnia wizualną informację zwrotną (np. powiadomienie typu „toast”) po dodaniu kombinacji do listy życzeń, poprawiając doświadczenie użytkownika.
-   `combinationstab/lib/searchTool/views/js/autocomplete.js`
    -   **Zakres:** Back-office (prawdopodobnie).
    -   **Szczegóły:** Zapewnia funkcjonalność autouzupełniania, prawdopodobnie dla pól wyszukiwania produktów lub kombinacji w interfejsach administracyjnych modułu (np. `AdminCombinationstabSearchController`).
-   `combinationstab/views/js/wishlist.js`
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Dedykowany JavaScript do integracji listy życzeń, obsługujący wywołania AJAX w celu dodawania/usuwania elementów z listy życzeń bezpośrednio z tabeli kombinacji.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zawiera kilka plików CSS do stylizacji front-office i administracji back-office.

-   `combinationstab/css/admin.css`
    -   **Zakres:** Stylizacja formularzy administracyjnych back-office.
    -   **Szczegóły:** Stylizuje stronę konfiguracji modułu i wszelkie niestandardowe interfejsy administracyjne (takie jak `AdminCombinationstabSearchController`), zapewniając spójny wygląd w panelu administracyjnym PrestaShop.
-   `combinationstab/css/combinationstab.css`
    -   **Zakres:** Stylizacja front-office dla klienta.
    -   **Szczegóły:** Zawiera podstawową stylizację tabeli kombinacji, w tym układ tabeli, wypełnienie komórek, wyrównanie tekstu i podstawową responsywność.
-   `combinationstab/css.css`
    -   **Zakres:** Stylizacja front-office dla klienta.
    -   **Szczegóły:** Potencjalnie starszy lub uzupełniający arkusz stylów dla front-office, lub specyficzne nadpisania.
-   `combinationstab/lib/searchTool/views/css/autocomplete.css`
    -   **Zakres:** Back-office (prawdopodobnie).
    -   **Szczegóły:** Style dla pól wyszukiwania z autouzupełnianiem używanych w panelu administracyjnym.
-   `combinationstab/views/css/ctp-admin.css`
    -   **Zakres:** Stylizacja formularzy administracyjnych back-office.
    -   **Szczegóły:** Dodatkowa lub specyficzna stylizacja administracyjna, potencjalnie dla nowszych funkcji lub nadpisań do `admin.css`.
-   `combinationstab/views/css/wishlist.css`
    -   **Zakres:** Stylizacja front-office dla klienta.
    -   **Szczegóły:** Style dla przycisku listy życzeń i wszelkich powiązanych elementów w tabeli kombinacji.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł wykorzystuje szablony Smarty do renderowania wszystkich swoich widoków front-office i back-office.

#### Szablony haków (`views/templates/hook/`)

Te szablony są zaprojektowane do renderowania, gdy wykonywane są określone haki PrestaShop.

-   `views/templates/hook/columns/cells.tpl`
    -   **Hak:** Prawdopodobnie renderowany w głównym szablonie tabeli kombinacji.
    -   **Wynik:** Definiuje strukturę i zawartość poszczególnych komórek danych w wierszach tabeli (np. wyświetlanie wartości atrybutów, ceny, pola ilości).
-   `views/templates/hook/columns/headers.tpl`
    -   **Hak:** Prawdopodobnie renderowany w głównym szablonie tabeli kombinacji.
    -   **Wynik:** Definiuje komórki nagłówka dla tabeli kombinacji, wyświetlając tytuły kolumn, takie jak „Obraz”, „Rozmiar”, „Cena”.
-   `views/templates/hook/columns/_wishlist_btn.tpl`
    -   **Hak:** Zintegrowany z wierszami kombinacji.
    -   **Wynik:** Renderuje przycisk lub ikonę „Dodaj do listy życzeń” dla każdej kombinacji w tabeli.
-   `views/templates/hook/customer_account.tpl`
    -   **Hak:** `displayCustomerAccount`
    -   **Wynik:** Dodaje link lub blok do strony konta klienta, potencjalnie w celu uzyskania dostępu do list ponownych zamówień, wyeksportowanych danych lub zarządzania listą życzeń.
-   `views/templates/hook/grid/_axis_label.tpl`
    -   **Hak:** Używany wewnętrznie, gdy `ctp_view_mode` jest ustawiony na układ siatki.
    -   **Wynik:** Renderuje etykiety dla osi (wierszy/kolumn) wyświetlania kombinacji w stylu siatki.
-   `views/templates/hook/grid/_cell.tpl`
    -   **Hak:** Używany wewnętrznie, gdy `ctp_view_mode` jest ustawiony na układ siatki.
    -   **Wynik:** Renderuje pojedyncze komórki w wyświetlaniu kombinacji w stylu siatki, zawierające szczegóły kombinacji.
-   `views/templates/hook/productfooter.tpl`
    -   **Hak:** `displayProductFooter`
    -   **Wynik:** Główny szablon do renderowania tabeli kombinacji, gdy jest umieszczony poniżej głównej treści produktu. Jest to często domyślne lub najczęstsze umiejscowienie.
-   `views/templates/hook/productfooter_grid.tpl`
    -   **Hak:** `displayProductFooter` (warunkowo w zależności od trybu widoku).
    -   **Wynik:** Alternatywny szablon dla `displayProductFooter` specjalnie do renderowania kombinacji w układzie siatki zamiast tradycyjnej tabeli.
-   `views/templates/hook/quickViewScripts.tpl`
    -   **Hak:** Potencjalnie `displayHeader` lub `actionFrontControllerSetMedia` (dla modalnych okien szybkiego podglądu).
    -   **Wynik:** Zawiera niezbędny kod JavaScript lub inicjalizuje funkcjonalność modułu specjalnie dla modalnych okien szybkiego podglądu produktu, zapewniając, że tabela kombinacji działa w tych wyskakujących okienkach.
-   `views/templates/hook/tab.tpl`
    -   **Hak:** `displayProductTabContent` (lub podobny dla zakładek produktu).
    -   **Wynik:** Renderuje tabelę kombinacji w dedykowanej zakładce produktu na stronie produktu.
-   `views/templates/hook/volume_discounts.tpl`
    -   **Hak:** Zintegrowany z wierszami kombinacji lub jako podpowiedź.
    -   **Wynik:** Wyświetla informacje o rabatach ilościowych dla konkretnych kombinacji.
-   `views/templates/hook/_filters.tpl`
    -   **Hak:** Renderowany nad tabelą kombinacji.
    -   **Wynik:** Renderuje interfejs filtrowania atrybutów dla tabeli kombinacji.
-   `views/templates/hook/_toolbar.tpl`
    -   **Hak:** Renderowany nad tabelą kombinacji.
    -   **Wynik:** Renderuje pasek narzędzi, potencjalnie zawierający filtry, wyszukiwanie lub inne interaktywne elementy dla tabeli kombinacji.

#### Szablony administracyjne (`views/templates/admin/`)

Te szablony są używane do konfiguracji back-office modułu i ekranów zarządzania.

-   `views/templates/admin/b2b.tpl`
    -   **Wynik:** Szablon dla ustawień lub funkcji specyficznych dla B2B w panelu administracyjnym.
-   `views/templates/admin/b2b_groups.tpl`
    -   **Wynik:** Szablon do zarządzania grupami klientów B2B lub ich specyficznymi ustawieniami cen/widoczności.
-   `views/templates/admin/column_editor.tpl`
    -   **Wynik:** Zapewnia interfejs dla administratorów do dostosowywania kolejności i widoczności kolumn w tabeli kombinacji front-office.
-   `views/templates/admin/getCombinations.tpl`
    -   **Wynik:** Używany przez `AdminCombinationstabSearchController` do wyświetlania listy lub siatki kombinacji.
-   `views/templates/admin/getProducts.tpl`
    -   **Wynik:** Używany przez `AdminCombinationstabSearchController` lub inne narzędzia administracyjne do wyświetlania listy produktów.
-   `views/templates/admin/grid_block_editor.tpl`
    -   **Wynik:** Interfejs do konfigurowania wyświetlania kombinacji w stylu siatki, potencjalnie definiujący, które atrybuty tworzą wiersze i kolumny.
-   `views/templates/admin/menu.tpl`
    -   **Wynik:** Renderuje podmenu modułu w panelu administracyjnym PrestaShop.
-   `views/templates/admin/overrides_entity.tpl`
    -   **Wynik:** Szablon do zarządzania nadpisaniami specyficznymi dla encji (np. ustawienia tabeli specyficzne dla produktu).
-   `views/templates/admin/overrides_fields.tpl`
    -   **Wynik:** Szablon do zarządzania nadpisaniami specyficznymi dla pól.
-   `views/templates/admin/overrides_list.tpl`
    -   **Wynik:** Szablon do wyświetlania i zarządzania różnymi nadpisaniami skonfigurowanymi dla modułu.
-   `views/templates/admin/presets.tpl`
    -   **Wynik:** Interfejs do zapisywania i ładowania predefiniowanych ustawień konfiguracji dla tabeli kombinacji.
-   `views/templates/admin/selectedProducts.tpl`
    -   **Wynik:** Wyświetla listę produktów, które zostały wybrane dla konkretnych konfiguracji modułu lub nadpisań.
-   `views/templates/admin/subtabs.tpl`
    -   **Wynik:** Renderuje podzakładki nawigacyjne w interfejsie konfiguracji modułu.
-   `views/templates/admin/tabs.tpl`
    -   **Wynik:** Renderuje główne zakładki nawigacyjne dla konfiguracji modułu.
-   `views/templates/admin/tabstype.tpl`
    -   **Wynik:** Opcje konfiguracji związane z tym, jak tabela kombinacji jest wyświetlana w zakładkach produktu.

#### Szablony front-office (`views/templates/front/`)

-   `views/templates/front/wishlist.tpl`
    -   **Wynik:** Renderuje interfejs listy życzeń front-office, potencjalnie dedykowaną stronę lub modalne okno, pokazujące elementy dodane do listy życzeń za pośrednictwem tabeli kombinacji.

#### Inne szablony

-   `combinationstab/lib/searchTool/views/scripts.tpl`
    -   **Wynik:** Zawiera fragmenty JavaScript lub inicjalizuje skrypty dla funkcjonalności narzędzia wyszukiwania.

### 4.7 Schemat bazy danych i mapa haków

#### Tabele bazy danych

Dossier modułu nie wskazuje na niestandardowe pliki SQL. Oznacza to, że moduł przede wszystkim używa tabeli `ps_configuration` PrestaShop do przechowywania swoich ustawień i opiera się na istniejących podstawowych tabelach, takich jak `ps_product_attribute`, `ps_product_attribute_combination`, `ps_product_attribute_shop`, `ps_stock_available` itp., dla danych kombinacji.

-   **`ps_configuration`**: Przechowuje wszystkie ustawienia modułu (np. `CTP_POSITION`, `CTP_IMAGE`, `CTP_PRICE_LOGGED`, `CTP_MOBILE_CARD_LAYOUT`).

#### Tabela zarejestrowanych haków

Moduł rejestruje się w różnych hakach PrestaShop, aby wstrzyknąć swoją zawartość i funkcjonalność.

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `ActionAdminControllerSetMedia` | Gdy kontroler administracyjny jest inicjalizowany i ustawiane są media (JS/CSS). | Wstrzykuje JS/CSS specyficzne dla modułu do Panelu administracyjnego. |
| `displayRightColumn` | Renderuje zawartość w prawej kolumnie front-office. | Wyświetla tabelę kombinacji w prawej kolumnie (rzadziej dla tabel). |
| `displayProductFooter` | Renderuje zawartość poniżej głównych informacji o produkcie na stronie produktu. | Główny hak do wyświetlania tabeli kombinacji poniżej produktu. |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` front-office. | Wstrzykuje JS/CSS specyficzne dla modułu, metatagi lub inne elementy nagłówka dla funkcjonalności front-office. |
| `displayProductExtraContent` | Renderuje dodatkowe bloki treści na stronie produktu. | Zapewnia elastyczność w umieszczaniu tabeli kombinacji w niestandardowym bloku treści. |
| `displayRightColumnProduct` | Renderuje zawartość w prawej kolumnie specjalnie na stronie produktu. | Podobnie jak `displayRightColumn`, ale skierowany do stron produktów. |
| `displayCustomerAccount` | Renderuje zawartość na stronie konta klienta. | Dodaje linki lub informacje związane z ponownym zamawianiem, listami życzeń lub eksportami. |
| `actionUpdateQuantity` | Po zaktualizowaniu ilości (stanu magazynowego) produktu. | Potencjalnie wyzwala aktualizacje wyświetlania tabeli kombinacji (np. status „niedostępny w magazynie”). |
| `displayProductListFunctionalButtons` | Renderuje przyciski w listach produktów (np. na stronach kategorii). | Może dodawać przyciski szybkiego podglądu lub porównania związane z kombinacjami. |
| `displayExtraLeft` | Renderuje zawartość w dodatkowej lewej kolumnie (jeśli motyw obsługuje). | Kolejna opcja umieszczenia tabeli kombinacji. |
| `CombinationsTable` | **Niestandardowy hak** | Niestandardowy hak zdefiniowany przez sam moduł, umożliwiający innym modułom lub motywom integrację z jego wyjściem tabeli lub jego nadpisanie. |
| `displayLeftColumnProduct` | Renderuje zawartość w lewej kolumnie specjalnie na stronie produktu. | Podobnie jak `displayRightColumnProduct`, ale dla lewej kolumny. |
| `displayCombinationsTable` | **Niestandardowy hak** | Kolejny niestandardowy hak, prawdopodobnie do głównego renderowania tabeli kombinacji, oferujący alternatywę dla `displayProductFooter`. |
| `displayProductActions` | Renderuje zawartość w pobliżu przycisku „Dodaj do koszyka” na stronie produktu. | Może być używany do kompaktowego selektora kombinacji lub przycisków szybkiego dodawania. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, wsparcie techniczne i wszelkie pytania dotyczące modułu „Tabela kombinacji na stronie produktu”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest gotowy do pomocy.
