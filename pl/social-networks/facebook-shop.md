---
title: "Facebook Shop - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu Facebook Shop PrestaShop od MyPresta.eu."
sidebar:
  label: "Facebook Shop - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook Shop na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-shop.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-shop/)
>
> ---


# Facebook Shop

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).
- **Strona fanowska na Facebooku**: Musisz mieć aktywną stronę fanowską na Facebooku (nie profil osobisty), której jesteś administratorem.
- **Certyfikat SSL**: Twój sklep PrestaShop musi posiadać aktywny certyfikat SSL (HTTPS), aby Facebook Shop działał poprawnie, ponieważ Facebook wymaga bezpiecznych połączeń dla osadzonych aplikacji.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest główny ekran konfiguracji Twojego modułu Facebook Shop. Znajdziesz tu serię zakładek lub sekcji, aby dostosować wygląd i działanie Twojego sklepu na Facebooku.

#### Zakładka Ustawienia ogólne (lub podobny widok początkowy)

-   **Wyświetlaj aktualizacje MyPresta.eu:**

    *   **Co robi to ustawienie:** Kontroluje, czy widzisz powiadomienia o aktualizacjach z MyPresta.eu bezpośrednio w konfiguracji modułu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Będziesz otrzymywać alerty o nowych wersjach lub ważnych wiadomościach z MyPresta.eu, co pomoże Ci utrzymać moduł w aktualnym stanie.
        *   *Gdy wyłączone:* Nie będziesz widzieć tych powiadomień, co może oznaczać, że przegapisz ważne aktualizacje lub poprawki błędów.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Pozostaw to włączone, aby zawsze być świadomym najnowszych ulepszeń i poprawek bezpieczeństwa dla Twojego modułu Facebook Shop.
-   **Wyświetlanie języka sklepu na Facebooku:** (`faceshop_lang_disp`)

    *   **Co robi to ustawienie:** Określa, czy selektor języka jest widoczny w Twoim sklepie na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci mogą zmieniać język Twojego sklepu na Facebooku, co jest przydatne dla sklepów międzynarodowych.
        *   *Gdy wyłączone:* Sklep będzie wyświetlany w domyślnym języku lub w języku wykrytym przez Facebooka, bez jawnego selektora.
    *   **Zalecana wartość:** TAK (jeśli masz włączonych wiele języków w PrestaShop)
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz klientom w różnych krajach i przetłumaczyłeś swój sklep PrestaShop, włącz to, aby umożliwić im przeglądanie w preferowanym języku.
-   **Wyświetlanie waluty sklepu na Facebooku:** (`faceshop_curr_disp`)

    *   **Co robi to ustawienie:** Określa, czy selektor waluty jest widoczny w Twoim sklepie na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci mogą zmieniać walutę wyświetlaną w Twoim sklepie na Facebooku, co jest przydatne dla sklepów międzynarodowych.
        *   *Gdy wyłączone:* Sklep będzie wyświetlał ceny w Twojej domyślnej walucie.
    *   **Zalecana wartość:** TAK (jeśli masz włączonych wiele walut w PrestaShop)
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli akceptujesz płatności w USD, EUR i GBP, włącz to, aby klienci mogli widzieć ceny w swojej lokalnej walucie.
-   **Włącz przepisywanie modułu (przyjazne adresy URL dla SEO):** (`faceshop_modrew`)

    *   **Co robi to ustawienie:** Kontroluje, czy moduł używa przyjaznych adresów URL dla SEO w sklepie na Facebooku, podobnie jak w Twoim głównym sklepie PrestaShop.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Adresy URL dla produktów i kategorii w sklepie na Facebooku będą czyste i opisowe (np. `twojasklep.com/produkt/moj-super-produkt`). Jest to ogólnie lepsze dla SEO i doświadczenia użytkownika.
        *   *Gdy wyłączone:* Adresy URL mogą być mniej czytelne (np. `twojasklep.com/index.php?id_product=123`).
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Zawsze włączaj to dla lepszej widoczności w wyszukiwarkach i bardziej profesjonalnego wyglądu linków do produktów udostępnianych z Facebooka.

#### Zakładka Ustawienia strony głównej

-   **Wyświetlaj liczbę elementów na stronie głównej:** (`faceshop_homepage_itemcount`)

    *   **Co robi to ustawienie:** Ustawia liczbę produktów do wyświetlenia na stronie głównej Twojego sklepu na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawione na 10:* Strona główna Twojego sklepu na Facebooku pokaże 10 produktów.
        *   *Gdy ustawione na 20:* Strona główna Twojego sklepu na Facebooku pokaże 20 produktów.
    *   **Zalecana wartość:** 12-24 (wystarczająco, aby pokazać różnorodność bez przytłaczania strony).
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz od razu zaprezentować szeroką gamę produktów, ustaw wyższą liczbę. Jeśli wolisz czystszy wygląd z mniejszą liczbą, bardziej widocznych elementów, ustaw niższą liczbę.
-   **Wyświetlaj produkty objęte rabatem na stronie głównej:** (`faceshop_homepage_disphot`)

    *   **Co robi to ustawienie:** Kontroluje, czy produkty objęte rabatem (w promocji) są wyróżniane na stronie głównej Twojego sklepu na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Produkty aktualnie w promocji będą widocznie wyświetlane, zachęcając do zakupów impulsywnych.
        *   *Gdy wyłączone:* Na stronie głównej pojawią się tylko produkty w regularnej cenie (chyba że inne opcje wyświetlania są włączone).
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Użyj tego, aby zwrócić uwagę na swoje promocje i wyczyścić magazyn.
-   **Wyświetlaj nowe produkty na stronie głównej:** (`faceshop_homepage_dispnew`)

    *   **Co robi to ustawienie:** Kontroluje, czy Twoje najnowsze produkty są wyróżniane na stronie głównej Twojego sklepu na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Niedawno dodane produkty zostaną zaprezentowane, utrzymując Twój sklep świeżym i ekscytującym dla powracających odwiedzających.
        *   *Gdy wyłączone:* Nowe produkty nie będą miały dedykowanej sekcji na stronie głównej.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli często dodajesz nowe pozycje, jest to świetny sposób, aby je wyróżnić i zachęcić do ponownych odwiedzin.
-   **Wyświetlaj kategorię główną na stronie głównej:** (`faceshop_homepage_root`)

    *   **Co robi to ustawienie:** Pozwala wybrać konkretną kategorię główną, z której produkty będą wyświetlane na stronie głównej Twojego sklepu na Facebooku. Jeśli pozostawione puste, wyświetli produkty z domyślnej kategorii głównej PrestaShop.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy wybrana jest konkretna kategoria:* Na stronie głównej pojawią się tylko produkty z tej kategorii i jej podkategorii.
        *   *Gdy pozostawione puste:* Produkty z domyślnej kategorii głównej całego sklepu będą brane pod uwagę do wyświetlenia na stronie głównej.
    *   **Zalecana wartość:** Pozostaw puste, chyba że masz konkretną strategię marketingową.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli prowadzisz specjalną kampanię dla „Kolekcji Letniej” i chcesz, aby tylko te produkty były na stronie głównej Twojego sklepu na Facebooku, wybierz tutaj kategorię „Kolekcja Letnia”.

#### Zakładka Ustawienia nagłówka

-   **Wyświetlaj nagłówek w sklepie na Facebooku:** (`faceshop_header_disp`)
    *   **Co robi to ustawienie:** Kontroluje, czy sekcja nagłówka Twojego sklepu PrestaShop (logo, pasek wyszukiwania, podsumowanie koszyka) jest widoczna w osadzonym sklepie na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Twój sklep na Facebooku będzie miał znajomy nagłówek, sprawiając, że będzie bardziej przypominał Twój główny sklep.
        *   *Gdy wyłączone:* Nagłówek zostanie ukryty, zapewniając bardziej minimalistyczny wygląd.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Utrzymywanie widocznego nagłówka pomaga zachować spójność marki i zapewnia podstawowe elementy nawigacyjne, takie jak pasek wyszukiwania.

#### Zakładka Ustawienia strony kategorii

-   **Kategoria główna dla sklepu na Facebooku:** (`faceshop_cat_root`)

    *   **Co robi to ustawienie:** Definiuje główną kategorię, od której Twój sklep na Facebooku zacznie wyświetlać produkty i kategorie. Działa to jako „korzeń” nawigacji Twojego sklepu na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy wybrane jest „Strona główna” (domyślny korzeń PrestaShop):* Wszystkie kategorie i produkty z całego Twojego sklepu będą dostępne.
        *   *Gdy wybrana jest konkretna kategoria (np. „Odzież”):* Tylko „Odzież” i jej podkategorie/produkty będą widoczne w sklepie na Facebooku.
    *   **Zalecana wartość:** „Strona główna” (lub kategoria główna Twojego głównego sklepu), chyba że chcesz ograniczyć zakres swojego sklepu na Facebooku.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz sprzedawać tylko konkretną linię produktów (np. „Elektronika”) na Facebooku, ustaw to na swoją kategorię „Elektronika”.
-   **Wyświetlaj nowe produkty na stronach kategorii:** (`faceshop_cat_dispnew`)

    *   **Co robi to ustawienie:** Kontroluje, czy nowe produkty są wyróżniane lub mają dedykowaną sekcję na stronach list kategorii w Twoim sklepie na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci przeglądający kategorie łatwo zauważą niedawno dodane pozycje.
        *   *Gdy wyłączone:* Nowe produkty po prostu pojawią się w regularnej liście bez specjalnego wyróżnienia.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Pomaga klientom odkrywać Twoje najnowsze produkty, nawet gdy przeglądają konkretne typy produktów.
-   **Wyświetlaj produkty objęte rabatem na stronach kategorii:** (`faceshop_cat_disphot`)

    *   **Co robi to ustawienie:** Kontroluje, czy produkty objęte rabatem są wyróżniane lub mają dedykowaną sekcję na stronach list kategorii w Twoim sklepie na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci przeglądający kategorie łatwo zauważą pozycje w promocji.
        *   *Gdy wyłączone:* Produkty objęte rabatem po prostu pojawią się w regularnej liście bez specjalnego wyróżnienia.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Zachęca do zakupów, czyniąc produkty w promocji bardziej widocznymi w odpowiednich kategoriach.
-   **Liczba elementów na stronie kategorii:** (`faceshop_cat_itemcount`)

    *   **Co robi to ustawienie:** Ustawia liczbę produktów do wyświetlenia na stronie, gdy klienci przeglądają kategorie w Twoim sklepie na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawione na 12:* Każda strona kategorii pokaże 12 produktów przed paginacją.
        *   *Gdy ustawione na 30:* Każda strona kategorii pokaże 30 produktów.
    *   **Zalecana wartość:** 12-24 (standard dla większości witryn e-commerce).
    *   **Scenariusz / przykład dla sprzedawcy:** Wyższa liczba zmniejsza liczbę kliknięć, ale może spowolnić ładowanie stron. Niższa liczba wymaga więcej kliknięć, ale może wydawać się mniej przytłaczająca.
-   **Styl wyświetlania kategorii:** (`faceshop_cat_dispstyle`)

    *   **Co robi to ustawienie:** Określa, jak kategorie są prezentowane w sklepie na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Opcja A (np. „Widok siatki”):* Kategorie są wyświetlane jako siatka obrazów/nazw.
        *   *Opcja B (np. „Widok listy”):* Kategorie są wyświetlane jako lista pionowa.
    *   **Zalecana wartość:** Widok siatki (często bardziej atrakcyjny wizualnie).
    *   **Scenariusz / przykład dla sprzedawcy:** Wybierz styl, który najlepiej pasuje do estetyki Twojej marki i sposobu, w jaki chcesz, aby klienci nawigowali po Twojej ofercie produktów.

#### Zakładka Ustawienia suwaka

-   **Wyświetlaj suwak w sklepie na Facebooku:** (`faceshop_slider_disp`)

    *   **Co robi to ustawienie:** Kontroluje, czy suwak obrazów (karuzela) jest wyświetlany w Twoim sklepie na Facebooku. Ten suwak zazwyczaj prezentuje polecane produkty, promocje lub banery.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Pojawi się obracający się baner lub suwak produktów, przyciągając uwagę.
        *   *Gdy wyłączone:* Suwak nie zostanie wyświetlony, co skutkuje statycznym układem.
    *   **Zalecana wartość:** TAK (jeśli masz atrakcyjne obrazy do suwaka).
    *   **Scenariusz / przykład dla sprzedawcy:** Użyj suwaka, aby wyróżnić swoją najnowszą kolekcję, sezonowe wyprzedaże lub bestsellery tuż na górze Twojego sklepu na Facebooku.
-   **Czas przejścia suwaka (w milisekundach):** (`faceshop_slider_time`)

    *   **Co robi to ustawienie:** Ustawia, jak długo każdy slajd pozostaje widoczny przed przejściem do następnego.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawione na 3000 (3 sekundy):* Slajdy będą zmieniać się co 3 sekundy.
        *   *Gdy ustawione na 5000 (5 sekund):* Slajdy będą zmieniać się co 5 sekund.
    *   **Zalecana wartość:** 4000-6000 (4-6 sekund), aby użytkownicy mieli wystarczająco dużo czasu na przeczytanie.
    *   **Scenariusz / przykład dla sprzedawcy:** Dostosuj to w zależności od ilości informacji na slajdach. Krótsze czasy dla slajdów tylko z obrazami, dłuższe dla slajdów z tekstem.
-   **Umiejscowienie suwaka:** (`faceshop_slider_place`)

    *   **Co robi to ustawienie:** Określa, gdzie suwak pojawia się w Twoim sklepie na Facebooku (np. na górze strony, poniżej kategorii).
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawione na „Góra” (Top):* Suwak będzie pierwszą rzeczą, którą zobaczą klienci.
        *   *Gdy ustawione na „Poniżej produktów” (Below Products):* Suwak pojawi się dalej na stronie.
    *   **Zalecana wartość:** Góra (dla maksymalnej widoczności).
    *   **Scenariusz / przykład dla sprzedawcy:** Umieść suwak na górze, aby natychmiast przyciągnąć uwagę najważniejszymi promocjami.

#### Zakładka Ustawienia menu

-   **Wyświetlaj link do nowych produktów w menu:** (`faceshop_menu_newproducts`)

    *   **Co robi to ustawienie:** Dodaje link do „Nowych produktów” w menu nawigacyjnym Twojego sklepu na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci mogą łatwo kliknąć, aby zobaczyć wszystkie Twoje najnowsze dodatki.
        *   *Gdy wyłączone:* Ten konkretny link nie pojawi się w menu.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Niezbędne dla sklepów, które często aktualizują swój asortyment, aby pomóc klientom odkrywać świeże pozycje.
-   **Wyświetlaj link do produktów w promocji w menu:** (`faceshop_menu_saleproducts`)

    *   **Co robi to ustawienie:** Dodaje link do „Produktów w promocji” lub „Rabatów” w menu nawigacyjnym Twojego sklepu na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci mogą szybko znaleźć wszystkie Twoje produkty objęte rabatem.
        *   *Gdy wyłączone:* Ten konkretny link nie pojawi się w menu.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Świetne do kierowania ruchu na Twoje promocje i zwiększania sprzedaży.
-   **Wyświetlaj link do stron informacyjnych w menu:** (`faceshop_menu_informations`)

    *   **Co robi to ustawienie:** Dodaje link do Twoich stron CMS (Informacje) PrestaShop (np. O nas, Dostawa, Regulamin) w menu nawigacyjnym.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci mogą bezpośrednio uzyskać dostęp do ważnych informacji niezwiązanych z produktami.
        *   *Gdy wyłączone:* Te linki nie pojawią się w menu.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Kluczowe dla budowania zaufania i dostarczania niezbędnych informacji obsługi klienta.
-   **Wyświetlaj link do strony kontaktowej w menu:** (`faceshop_menu_contact`)

    *   **Co robi to ustawienie:** Dodaje link do Twojej strony Kontakt PrestaShop w menu nawigacyjnym.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci mogą łatwo znaleźć sposób, aby się z Tobą skontaktować.
        *   *Gdy wyłączone:* Ten konkretny link nie pojawi się w menu.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Zapewnia bezpośredni kanał do zapytań klientów, poprawiając wsparcie.
-   **Styl wyświetlania kategorii w menu:** (`faceshop_menu_catstyle`)

    *   **Co robi to ustawienie:** Określa, jak kategorie są wyświetlane w głównym menu nawigacyjnym Twojego sklepu na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Opcja A (np. „Rozwijane”):* Kategorie pojawiają się w rozwijanym menu.
        *   *Opcja B (np. „Lista pozioma”):* Kategorie pojawiają się jako lista pozioma.
    *   **Zalecana wartość:** Rozwijane (dla wielu kategorii) lub Lista pozioma (dla niewielu kategorii).
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz wiele kategorii produktów, rozwijane menu utrzymuje nawigację w czystości. Jeśli masz tylko kilka głównych kategorii, lista pozioma może być bardziej bezpośrednia.
-   **Wyświetlaj link do producentów w menu:** (`faceshop_menu_manuf`)

    *   **Co robi to ustawienie:** Dodaje link do Twojej strony Producentów PrestaShop w menu nawigacyjnym.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci mogą przeglądać produkty według marki lub producenta.
        *   *Gdy wyłączone:* Ten konkretny link nie pojawi się w menu.
    *   **Zalecana wartość:** TAK (jeśli sprzedajesz produkty wielu różnych marek).
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli jesteś sprzedawcą różnych marek, pomaga to klientom znaleźć produkty od ich ulubionych producentów.

#### Zakładka Ustawienia strony produktu

-   **Wyświetlaj nawigację okruszkową (breadcrumb):** (`faceshop_display_breadcrumb`)

    *   **Co robi to ustawienie:** Kontroluje, czy nawigacja „okruszkowa” (np. Strona główna > Kategoria > Podkategoria > Produkt) jest wyświetlana na stronach produktów.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Pomaga klientom zrozumieć ich położenie w hierarchii sklepu i łatwo wrócić do kategorii nadrzędnych.
        *   *Gdy wyłączone:* Ścieżka nawigacyjna zostanie ukryta.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Poprawia doświadczenie użytkownika, zapewniając jasne ścieżki nawigacji, zwłaszcza dla sklepów z głębokimi strukturami kategorii.
-   **Przycinaj opis produktu:** (`faceshop_pdisp_trim`)

    *   **Co robi to ustawienie:** Jeśli włączone, skróci długie opisy produktów na stronie produktu, często wyświetlając link „Czytaj więcej”.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Strony produktów wyglądają czyściej, a użytkownicy mogą rozwinąć opis, jeśli są zainteresowani.
        *   *Gdy wyłączone:* Zawsze wyświetlane są pełne opisy produktów, co może sprawić, że strony będą bardzo długie.
    *   **Zalecana wartość:** TAK (dla produktów z bardzo długimi opisami).
    *   **Scenariusz / przykład dla sprzedawcy:** Zapobiega zbyt długim stronom produktów, zwłaszcza na urządzeniach mobilnych, pokazując najpierw zwięzłe podsumowanie.
-   **Wyświetlaj cenę produktu:** (`faceshop_pdisp_price`)

    *   **Co robi to ustawienie:** Kontroluje, czy cena produktu jest widoczna na stronach produktów.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Cena zostanie wyraźnie wyświetlona.
        *   *Gdy wyłączone:* Cena zostanie ukryta.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Ukrywanie cen jest ogólnie niezalecane dla sklepu e-commerce, chyba że masz konkretną strategię B2B wymagającą wycen. Dla większości handlu detalicznego ceny są niezbędne.
-   **Wyświetlaj nazwę produktu:** (`faceshop_pdisp_name`)

    *   **Co robi to ustawienie:** Kontroluje, czy nazwa produktu jest widoczna na stronach produktów.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Nazwa produktu zostanie wyświetlona.
        *   *Gdy wyłączone:* Nazwa produktu zostanie ukryta.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Nazwa produktu jest fundamentalna dla identyfikacji; zawsze pozostaw to włączone.
-   **Wyświetlaj obraz produktu:** (`faceshop_pdisp_image`)

    *   **Co robi to ustawienie:** Kontroluje, czy obraz produktu jest widoczny na stronach produktów.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Główny obraz produktu i dodatkowe obrazy zostaną wyświetlone.
        *   *Gdy wyłączone:* Obrazy produktów zostaną ukryte.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Obrazy produktów są kluczowe dla sprzedaży online; zawsze pozostaw to włączone.

#### Zakładka Ustawienia udostępniania społecznościowego

-   **Wyświetlaj przycisk udostępniania na Facebooku:** (`faceshop_social_facebook`)

    *   **Co robi to ustawienie:** Dodaje przycisk „Udostępnij” na Facebooku do stron produktów w Twoim sklepie na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci mogą łatwo udostępniać produkty swoim znajomym na Facebooku, zwiększając marketing wirusowy.
        *   *Gdy wyłączone:* Przycisk udostępniania na Facebooku nie pojawi się.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Zachęcaj klientów do rozpowszechniania informacji o Twoich produktach na ich własnych osiach czasu.
-   **Wyświetlaj przycisk udostępniania na Pintereście:** (`faceshop_social_pinterest`)

    *   **Co robi to ustawienie:** Dodaje przycisk „Przypnij” na Pintereście do stron produktów w Twoim sklepie na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci mogą łatwo przypinać obrazy produktów do swoich tablic na Pintereście, kierując ruch z Pinteresta.
        *   *Gdy wyłączone:* Przycisk udostępniania na Pintereście nie pojawi się.
    *   **Zalecana wartość:** TAK (zwłaszcza jeśli Twoje produkty są atrakcyjne wizualnie).
    *   **Scenariusz / przykład dla sprzedawcy:** Świetne dla mody, wystroju wnętrz, rękodzieła i innych produktów wizualnych, aby wykorzystać publiczność Pinteresta.
-   **Wyświetlaj przycisk udostępniania na Google+:** (`faceshop_social_google`)

    *   **Co robi to ustawienie:** Dodaje przycisk udostępniania na Google+ do stron produktów w Twoim sklepie na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci mogą udostępniać produkty na Google+.
        *   *Gdy wyłączone:* Przycisk udostępniania na Google+ nie pojawi się.
    *   **Zalecana wartość:** NIE (Google+ zostało wycofane).
    *   **Scenariusz / przykład dla sprzedawcy:** Ta platforma nie jest już aktywna, więc włączanie jej jest niepotrzebne.

#### Zakładka Ustawienia stopki

-   **Wyświetlaj stopkę w sklepie na Facebooku:** (`faceshop_footer_disp`)
    *   **Co robi to ustawienie:** Kontroluje, czy sekcja stopki Twojego sklepu PrestaShop (prawa autorskie, linki, ikony płatności) jest widoczna w osadzonym sklepie na Facebooku.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączone:* Twój sklep na Facebooku będzie miał znajomą stopkę, utrzymując spójność marki i zapewniając dodatkowe linki.
        *   *Gdy wyłączone:* Stopka zostanie ukryta.
    *   **Zalecana wartość:** TAK
    *   **Scenariusz / przykład dla sprzedawcy:** Stopka często zawiera ważne linki prawne (polityka prywatności, warunki świadczenia usług) i informacje kontaktowe, które warto zachować widoczne dla zaufania i zgodności.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Ustawienia ogólne** | Wyświetlaj aktualizacje MyPresta.eu | TAK | Otrzymuj powiadomienia o aktualizacjach modułu. |
| | Wyświetlanie języka sklepu na Facebooku (`faceshop_lang_disp`) | TAK | Zezwalaj klientom na zmianę języka sklepu. |
| | Wyświetlanie waluty sklepu na Facebooku (`faceshop_curr_disp`) | TAK | Zezwalaj klientom na zmianę waluty sklepu. |
| | Włącz przepisywanie modułu (przyjazne adresy URL dla SEO) (`faceshop_modrew`) | TAK | Używaj czystych, opisowych adresów URL dla lepszego SEO i UX. |
| **Ustawienia strony głównej** | Wyświetlaj liczbę elementów na stronie głównej (`faceshop_homepage_itemcount`) | 12-24 | Liczba produktów wyświetlanych na stronie głównej. |
| | Wyświetlaj produkty objęte rabatem na stronie głównej (`faceshop_homepage_disphot`) | TAK | Wyróżniaj produkty w promocji na stronie głównej. |
| | Wyświetlaj nowe produkty na stronie głównej (`faceshop_homepage_dispnew`) | TAK | Wyróżniaj nowości na stronie głównej. |
| | Wyświetlaj kategorię główną na stronie głównej (`faceshop_homepage_root`) | Puste (domyślna kategoria główna) | Wybierz konkretną kategorię dla produktów na stronie głównej. |
| **Ustawienia nagłówka** | Wyświetlaj nagłówek w sklepie na Facebooku (`faceshop_header_disp`) | TAK | Pokaż nagłówek swojego sklepu (logo, wyszukiwarka, koszyk). |
| **Ustawienia strony kategorii** | Kategoria główna dla sklepu na Facebooku (`faceshop_cat_root`) | Strona główna (domyślna kategoria główna) | Definiuje początkową kategorię dla sklepu na Facebooku. |
| | Wyświetlaj nowe produkty na stronach kategorii (`faceshop_cat_dispnew`) | TAK | Wyróżniaj nowe produkty w kategoriach. |
| | Wyświetlaj produkty objęte rabatem na stronach kategorii (`faceshop_cat_disphot`) | TAK | Wyróżniaj produkty w promocji w kategoriach. |
| | Liczba elementów na stronie kategorii (`faceshop_cat_itemcount`) | 12-24 | Liczba produktów wyświetlanych na stronie kategorii. |
| | Styl wyświetlania kategorii (`faceshop_cat_dispstyle`) | Widok siatki | Sposób prezentacji kategorii (siatka/lista). |
| **Ustawienia suwaka** | Wyświetlaj suwak w sklepie na Facebooku (`faceshop_slider_disp`) | TAK | Pokaż suwak obrazów/produktów. |
| | Czas przejścia suwaka (w milisekundach) (`faceshop_slider_time`) | 4000-6000 | Szybkość przejść slajdów. |
| | Umiejscowienie suwaka (`faceshop_slider_place`) | Góra | Pozycja suwaka (np. na górze strony). |
| **Ustawienia menu** | Wyświetlaj link do nowych produktów w menu (`faceshop_menu_newproducts`) | TAK | Dodaj „Nowe produkty” do menu nawigacyjnego. |
| | Wyświetlaj link do produktów w promocji w menu (`faceshop_menu_saleproducts`) | TAK | Dodaj „Produkty w promocji” do menu nawigacyjnego. |
| | Wyświetlaj link do stron informacyjnych w menu (`faceshop_menu_informations`) | TAK | Dodaj linki do stron CMS (O nas itp.). |
| | Wyświetlaj link do strony kontaktowej w menu (`faceshop_menu_contact`) | TAK | Dodaj link „Kontakt”. |
| | Styl wyświetlania kategorii w menu (`faceshop_menu_catstyle`) | Rozwijane | Sposób wyświetlania kategorii w menu (rozwijane/lista). |
| | Wyświetlaj link do producentów w menu (`faceshop_menu_manuf`) | TAK | Dodaj link do producentów/marek. |
| **Ustawienia strony produktu** | Wyświetlaj nawigację okruszkową (breadcrumb) (`faceshop_display_breadcrumb`) | TAK | Pokaż ścieżkę nawigacji (Strona główna > Kategoria > Produkt). |
| | Przycinaj opis produktu (`faceshop_pdisp_trim`) | TAK | Skróć długie opisy produktów. |
| | Wyświetlaj cenę produktu (`faceshop_pdisp_price`) | TAK | Pokaż cenę produktu. |
| | Wyświetlaj nazwę produktu (`faceshop_pdisp_name`) | TAK | Pokaż nazwę produktu. |
| | Wyświetlaj obraz produktu (`faceshop_pdisp_image`) | TAK | Pokaż obrazy produktów. |
| **Ustawienia udostępniania społecznościowego** | Wyświetlaj przycisk udostępniania na Facebooku (`faceshop_social_facebook`) | TAK | Zezwalaj na udostępnianie na Facebooku. |
| | Wyświetlaj przycisk udostępniania na Pintereście (`faceshop_social_pinterest`) | TAK | Zezwalaj na udostępnianie na Pintereście. |
| | Wyświetlaj przycisk udostępniania na Google+ (`faceshop_social_google`) | NIE | Google+ zostało wycofane. |
| **Ustawienia stopki** | Wyświetlaj stopkę w sklepie na Facebooku (`faceshop_footer_disp`) | TAK | Pokaż stopkę swojego sklepu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Mój sklep na Facebooku nie wyświetla się lub widzę komunikat o błędzie.**
O1:

-   **Sprawdź SSL:** Upewnij się, że Twój sklep PrestaShop ma ważny certyfikat SSL (HTTPS). Facebook wymaga bezpiecznych połączeń dla osadzonych aplikacji. Jeśli Twój sklep nie używa HTTPS, sklep na Facebooku nie zostanie załadowany.
-   **Ustawienia strony na Facebooku:** Sprawdź dwukrotnie, czy jesteś administratorem strony fanowskiej na Facebooku i czy zakładka „Sklep” jest poprawnie dodana i skonfigurowana na samym Facebooku.
-   **Konfiguracja modułu:** Wróć do konfiguracji modułu w PrestaShop i upewnij się, że wszystkie ustawienia są poprawnie zapisane.
-   **Wyczyść pamięć podręczną:** W PrestaShop przejdź do **Zaawansowane > Wydajność** i wyczyść pamięć podręczną Smarty, pamięć podręczną przeglądarki i wszelkie inne pamięci podręczne.

**P2: Produkty nie wyświetlają się poprawnie lub brakuje obrazów.**
O2:

-   **Ustawienia produktu:** Sprawdź, czy produkty, które mają być widoczne, są aktywne i widoczne w Twoim głównym sklepie PrestaShop.
-   **Ścieżki obrazów:** Upewnij się, że obrazy produktów mają poprawne ścieżki i są publicznie dostępne.
-   **Ustawienia modułu:** Sprawdź ustawienia `faceshop_pdisp_image`, `faceshop_pdisp_name`, `faceshop_pdisp_price`, aby upewnić się, że są włączone.
-   **Kategoria główna:** Potwierdź, że ustawienia `faceshop_cat_root` i `faceshop_homepage_root` poprawnie wskazują na kategorie zawierające produkty.

**P3: Moduł wygląda inaczej na urządzeniach mobilnych w obrębie Facebooka.**
O3:

-   **Aplikacja Facebook vs. przeglądarka:** Doświadczenie może się nieznacznie różnić między aplikacją mobilną Facebooka a dostępem do Facebooka za pośrednictwem przeglądarki mobilnej. Moduł jest zaprojektowany tak, aby był responsywny, ale własna otoczka Facebooka może wpływać na ostateczny wygląd.
-   **Sprawdź responsywność:** Przetestuj swój główny sklep PrestaShop na urządzeniach mobilnych, aby upewnić się, że jest w pełni responsywny. Sklep na Facebooku dziedziczy wiele ze swojego stylu z Twojego głównego sklepu.
-   **Niestandardowy CSS:** Jeśli masz niestandardowy CSS w swoim motywie PrestaShop, może on zakłócać działanie. Skonsultuj się z programistą stron internetowych, aby sprawdzić CSS w ramce iframe Facebooka.

**P4: Jak przetłumaczyć sklep na Facebooku na inne języki?**
O4:

-   **Tłumaczenia PrestaShop:** Moduł Facebook Shop pobiera zawartość (nazwy produktów, opisy, nazwy kategorii) bezpośrednio z Twojego sklepu PrestaShop. Upewnij się, że cała zawartość produktów i kategorii jest przetłumaczona w samym PrestaShop.
-   **Tekst modułu:** W przypadku tekstu interfejsu modułu (np. link „Nowe produkty”) przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop. Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, swój język, a następnie znajdź moduł „Facebook Shop”, aby przetłumaczyć jego konkretne ciągi znaków.
-   **Selektor języka:** Upewnij się, że `faceshop_lang_disp` jest włączony w konfiguracji modułu, aby umożliwić klientom zmianę języka.

**P5: Mój sklep na Facebooku wolno się ładuje.**
O5:

-   **Optymalizacja obrazów:** Upewnij się, że obrazy produktów są zoptymalizowane do użytku w sieci (skompresowane, odpowiednie wymiary). Duże obrazy są częstą przyczyną wolnego ładowania.
-   **Wydajność hostingu:** Sprawdź wydajność swojego hostingu. Wolny serwer wpłynie zarówno na Twój główny sklep, jak i na Twój sklep na Facebooku.
-   **Liczba produktów:** Jeśli wyświetlasz bardzo dużą liczbę produktów na stronie głównej lub stronach kategorii (`faceshop_homepage_itemcount`, `faceshop_cat_itemcount`), rozważ zmniejszenie tych liczb.
-   **Buforowanie:** Upewnij się, że mechanizmy buforowania PrestaShop są poprawnie skonfigurowane (**Zaawansowane > Wydajność**).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł Facebook Shop (`faceshop`) został zaprojektowany jako standardowy moduł PrestaShop, głównie rozszerzający klasę `Module`. Wykorzystuje system konfiguracji PrestaShop (`Configuration::get()`, `Configuration::updateValue()`) do przechowywania swoich ustawień. Podstawowa funkcjonalność modułu polega na renderowaniu uproszczonej wersji front-office PrestaShop w ramce iframe na stronie fanowskiej na Facebooku. Osiąga to poprzez dynamiczne dostosowywanie wyświetlania w oparciu o konkretny parametr URL (`?fc=module&module=faceshop&controller=shop`). Moduł nie wprowadza niestandardowych tabel baz danych ani złożonych ObjectModels, ale raczej manipuluje istniejącym wyświetlaniem front-office PrestaShop za pomocą hooków i nadpisywania szablonów.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera dedykowanych kontrolerów front-office ani back-office w katalogu `controllers/`.
Jego funkcjonalność front-office jest głównie obsługiwana przez główny plik `faceshop.php`, który przechwytuje żądania za pomocą niestandardowego parametru kontrolera `shop` (np. `index.php?fc=module&module=faceshop&controller=shop`). Takie podejście pozwala modułowi renderować zmodyfikowaną wersję standardowego front-office PrestaShop w ramce iframe Facebooka, zamiast tworzyć całkowicie nowe struktury stron.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł **nie** wprowadza żadnych niestandardowych klas ani ObjectModels w katalogu `classes/`. Cała podstawowa logika jest hermetyzowana w głównym pliku `faceshop/faceshop.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł zawiera kilka plików JavaScript, głównie w celu ulepszenia wyświetlania front-office w ramce iframe Facebooka.

-   `faceshop/jscolor/jscolor.js`
    *   **Zakres:** Back-office (prawdopodobnie używany w formularzu konfiguracji modułu).
    *   **Opis:** Biblioteka JavaScript do wyboru kolorów. Pozwala administratorom łatwo wybierać kolory dla ustawień modułu, chociaż w kluczach konfiguracyjnych nie zidentyfikowano żadnych jawnych ustawień kolorów, jest to powszechne narzędzie do dostosowywania interfejsu użytkownika.
-   `faceshop/js/advajax.js`
    *   **Zakres:** Front-office (w ramce iframe Facebooka).
    *   **Opis:** Prawdopodobnie niestandardowy skrypt narzędziowy AJAX. Obsługiwałby asynchroniczne żądania ładowania danych produktów, paginacji lub innych dynamicznych treści w sklepie na Facebooku bez pełnego przeładowywania strony. Poprawia to doświadczenie użytkownika, sprawiając, że sklep wydaje się bardziej responsywny.
-   `faceshop/js/jquery.nivo.slider.pack.js`
    *   **Zakres:** Front-office (w ramce iframe Facebooka).
    *   **Opis:** Spakowana wersja wtyczki jQuery Nivo Slider. Ten skrypt odpowiada za funkcjonalność suwaka obrazów (`faceshop_slider_disp`) na stronie głównej sklepu na Facebooku, obsługując przejścia, nawigację i automatyczne odtwarzanie.
-   `faceshop/js/shop2.js`
    *   **Zakres:** Front-office (w ramce iframe Facebooka).
    *   **Opis:** Jest to prawdopodobnie główny niestandardowy plik JavaScript dla logiki front-end sklepu na Facebooku. Zawierałby kod do:
        *   Inicjalizacji Nivo Slidera.
        *   Obsługi dynamicznego ładowania treści (np. przyciski „Wczytaj więcej” dla produktów).
        *   Dostosowywania układu lub zachowania specjalnie dla środowiska ramki iframe Facebooka.
        *   Potencjalnie obsługi interakcji z Facebook SDK (chociaż nie jest to wyraźnie wspomniane, jest to typowe dla aplikacji Facebooka).
        *   Wszelkich niestandardowych ulepszeń interfejsu użytkownika lub słuchaczy zdarzeń specyficznych dla osadzonego sklepu.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł zawiera kilka plików CSS do stylizacji osadzonego sklepu na Facebooku, zapewniając jego spójny wygląd i prawidłowe działanie w ramce iframe.

-   `faceshop/css.css`
    *   **Zakres:** Front-office (w ramce iframe Facebooka).
    *   **Opis:** Ogólny arkusz stylów dla sklepu na Facebooku. Prawdopodobnie zawiera podstawowe zasady układu, typografię i podstawową stylizację dla wspólnych elementów (przyciski, linki, formularze), aby zapewnić spójny wygląd.
-   `faceshop/css/style.css`
    *   **Zakres:** Front-office (w ramce iframe Facebooka).
    *   **Opis:** Może to być bardziej szczegółowy arkusz stylów, potencjalnie nadpisujący lub rozszerzający `css.css`. Może zawierać style dla konkretnych funkcji modułu lub dostosowania układu, aby lepiej pasowały do środowiska Facebooka.
-   `faceshop/default/default.css`
    *   **Zakres:** Front-office (w ramce iframe Facebooka).
    *   **Opis:** Ten arkusz stylów jest prawdopodobnie częścią wtyczki Nivo Slider, zapewniając domyślną stylizację nawigacji suwaka, podpisów i ogólnego wyglądu. Programiści mogą nadpisać te style, aby dopasować je do motywu sklepu.
-   `faceshop/style.css`
    *   **Zakres:** Front-office (w ramce iframe Facebooka).
    *   **Opis:** Podobnie jak `faceshop/css/style.css`, może to być inny główny arkusz stylów lub plik zapasowy/historyczny. Określałby wizualną prezentację elementów sklepu, zapewniając ich prawidłowe renderowanie w ramce iframe Facebooka.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Dossier modułu wskazuje, że w `views/templates/` nie znaleziono żadnych konkretnych plików `.tpl`. Sugeruje to, że moduł działa głównie poprzez:

1.  **Przechwytywanie standardowych żądań front-office PrestaShop:** Po uzyskaniu dostępu za pośrednictwem adresu URL sklepu na Facebooku, moduł prawdopodobnie modyfikuje globalne zmienne Smarty lub ścieżki szablonów, aby renderować istniejące szablony motywu PrestaShop.
2.  **Używanie metod `display` w `faceshop.php`:** Metody `display()` modułu mogą bezpośrednio renderować HTML lub zawierać fragmenty z głównego motywu PrestaShop, dynamicznie dodając lub usuwając elementy w oparciu o jego konfigurację.
3.  **Renderowanie sterowane JavaScriptem:** Niektóre elementy mogą być dynamicznie wstrzykiwane lub modyfikowane przez pliki JavaScript po początkowym załadowaniu strony.

Gdyby istniały niestandardowe szablony, znajdowałyby się one zazwyczaj w:

-   `views/templates/hook/`: Dla treści renderowanych w konkretnych hookach PrestaShop.
-   `views/templates/admin/`: Dla niestandardowych formularzy lub wyświetlaczy back-office.
-   `views/templates/front/`: Dla samodzielnych stron front-office lub konkretnych treści modułu.

Brak jawnych plików `.tpl` oznacza bardziej bezpośrednią manipulację istniejącym procesem renderowania front-office PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł nie tworzy żadnych niestandardowych tabel baz danych. Wszystkie jego ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` (lub `_configuration` w zależności od prefiksu tabeli) przy użyciu kluczy konfiguracyjnych wymienionych w sekcji 4.1.
-   **Tabela zarejestrowanych hooków**:
    Moduł głównie współdziała z wyświetlaniem front-office PrestaShop. Chociaż dossier wymienia „Nagłówek, Kolumny, Produkt lub Stopka” jako hooki front-office, podstawową funkcjonalnością modułu jest osadzenie *całego* front-office. Prawdopodobnie używa kombinacji:

    *   **`hookDisplayHeader`**: Do wstrzykiwania swoich zasobów CSS i JavaScript, a potencjalnie do modyfikowania sekcji `<head>` dla kompatybilności z ramką iframe Facebooka.
    *   **`hookDisplayFooter`**: Do wstrzykiwania dodatkowych skryptów lub treści na dole strony.
    *   **`actionFrontControllerSetMedia`**: (PrestaShop 1.7+) Do rejestrowania swoich plików CSS i JS.
    *   **Wewnętrzna logika renderowania sklepu**: Moduł prawdopodobnie ma wewnętrzną logikę, która, po wykryciu, że jest ładowany w ramce iframe Facebooka, modyfikuje standardowe wyjście front-office PrestaShop, aby ukrywać/pokazywać elementy w oparciu o jego ustawienia konfiguracyjne (np. `faceshop_header_disp`, `faceshop_footer_disp`). Osiąga się to często poprzez nadpisywanie lub manipulowanie zmiennymi Smarty i przypisaniami szablonów w metodach `display()` lub `hook` modułu.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Przed główną zawartością strony, w sekcji `<head>`. | Wstrzykiwanie plików CSS i JavaScript modułu, potencjalnie modyfikowanie meta tagów dla ramki iframe Facebooka. |
| `displayFooter` | Na końcu zawartości strony, przed zamykającym tagiem `</body>`. | Wstrzykiwanie dodatkowych skryptów lub kodów śledzących, lub modyfikowanie zawartości stopki, jeśli `faceshop_footer_disp` jest włączony. |
| `actionFrontControllerSetMedia` (PS 1.7+) | Podczas fazy ustawiania mediów kontrolera front-end. | Rejestrowanie plików CSS i JS dla optymalnego ładowania. |
| (Implicit) Product Page Hooks | Na stronach szczegółów produktu. | Modyfikowanie wyświetlania strony produktu w oparciu o `faceshop_pdisp_trim`, `faceshop_pdisp_price` itp. oraz wstrzykiwanie przycisków udostępniania społecznościowego. |
| (Implicit) Category Page Hooks | Na stronach list kategorii. | Modyfikowanie wyświetlania strony kategorii w oparciu o `faceshop_cat_dispnew`, `faceshop_cat_disphot` itp. |
| (Implicit) Homepage Hooks | Na stronie głównej sklepu. | Renderowanie suwaka, polecanych produktów, nowych produktów i produktów objętych rabatem w oparciu o ustawienia modułu. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu Facebook Shop, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół jest zaangażowany w zapewnienie optymalnego działania Twojego modułu i pomoc w maksymalizacji sprzedaży online.

-   **MyPresta.eu Historia zamówień i pobieranie:** <https://mypresta.eu/my-account/orders/>
-   **MyPresta.eu Kontakt z pomocą techniczną:** <https://mypresta.eu/contact>
