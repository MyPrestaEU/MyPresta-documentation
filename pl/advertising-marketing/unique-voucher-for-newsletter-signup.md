---
title: "Unikalny kupon za zapis do newslettera - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja dla programistów modułu PrestaShop „Unikalny kupon za zapis do newslettera” od MyPresta.eu."
sidebar:
  label: "Unikalny kupon za zapis do newslettera - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Unique voucher for newsletter signup na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/unique-voucher-for-newsletter-signup.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/unique-voucher-for-newsletter-signup/)
>
> ---


# Unikalny kupon za zapis do newslettera

## 1. Wymagania i Kompatybilność

- **Obsługiwane Wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania Hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny Przewodnik Konfiguracji (Każde Ustawienie Pogrupowane Według Ekranu)

### 2.1 Strona Konfiguracji Modułu (Panel administracyjny > Moduły > Konfiguruj)

Aby uzyskać dostęp, przejdź do **Moduły > Menedżer modułów**, wyszukaj „Unikalny kupon za zapis do newslettera” i kliknij „Konfiguruj”.

Ten ekran pozwala zdefiniować podstawowe zachowanie kuponów generowanych za zapisy do newslettera.

-   **Do czego służy to ustawienie:** Ta sekcja zawiera główne ustawienia dotyczące sposobu tworzenia i dostarczania unikalnych kuponów.
-   **Efekt zmiany tego ustawienia:** Dostosowanie tych wartości bezpośrednio wpływa na kwotę rabatu, warunki i ważność kuponów, które otrzymują nowi subskrybenci newslettera.

**Ustawienia i Opcje:**

1.  **Wartość kuponu (kwota lub procent)**

    -   **Do czego służy to ustawienie:** Określa kwotę rabatu lub procent, jaki zapewni unikalny kupon.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli ustawiono na konkretną kwotę (np. „10”):* Kupon zapewni stały rabat pieniężny (np. 10 € zniżki).
        -   *Jeśli ustawiono na procent (np. „15%”):* Kupon zapewni procentowy rabat od całkowitej wartości zamówienia.
    -   **Zalecana wartość:** Zależy od Twojej strategii cenowej. Powszechną praktyką jest 5-15% lub stała kwota, np. 5-10 € na początkowe zakupy.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz zaoferować 5 € zniżki nowym subskrybentom. Wprowadź „5” tutaj. Jeśli wolisz 10% zniżki, wprowadź „10%”.
2.  **Minimalna kwota**

    -   **Do czego służy to ustawienie:** Ustawia minimalną całkowitą wartość zamówienia (przed wysyłką) wymaganą do ważności kuponu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli ustawiono na „0” lub pozostawiono puste:* Kupon może być użyty do dowolnego zamówienia, niezależnie od jego całkowitej wartości.
        -   *Jeśli ustawiono na wartość (np. „50”):* Całkowita wartość koszyka klienta musi wynosić co najmniej 50 €, aby kupon mógł zostać zastosowany.
    -   **Zalecana wartość:** Ustaw minimalną kwotę, jeśli chcesz zapewnić określoną wartość zamówienia, lub pozostaw „0”, jeśli chcesz zachęcić do dowolnego zakupu.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby uniemożliwić klientom użycie kuponu o wartości 10 € na przedmiot o wartości 5 €, możesz ustawić minimalną kwotę na „30”.
3.  **Ważność kuponu (dni)**

    -   **Do czego służy to ustawienie:** Określa, ile dni unikalny kupon będzie ważny od momentu jego wygenerowania i wysłania do klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli ustawiono na „0” lub pozostawiono puste:* Kupon nie będzie miał daty ważności (niezalecane, ponieważ usuwa poczucie pilności).
        -   *Jeśli ustawiono na wartość (np. „30”):* Kupon wygaśnie 30 dni po otrzymaniu go przez klienta.
    -   **Zalecana wartość:** 7, 14 lub 30 dni to typowe wartości, aby stworzyć poczucie pilności, nie będąc zbyt restrykcyjnym.
    -   **Scenariusz / przykład dla sprzedawcy:** Aby zachęcić do natychmiastowych zakupów, możesz ustawić ważność na „7” dni, zachęcając klientów do szybkiego użycia kuponu.
4.  **Opis kuponu**

    -   **Do czego służy to ustawienie:** Ten tekst pojawi się jako opis wygenerowanego kuponu w koszyku klienta i w Panelu administracyjnym.
    -   **Efekt zmiany tego ustawienia:** Pomaga klientom zrozumieć, do czego służy kupon, i zapewnia kontekst dla Twoich wewnętrznych rejestrów.
    -   **Zalecana wartość:** „Rabat za zapis do newslettera” lub „Kupon powitalny dla subskrybentów newslettera”.
    -   **Scenariusz / przykład dla sprzedawcy:** Wprowadzenie „Rabat powitalny dla subskrybentów newslettera” jasno komunikuje cel kuponu.
5.  **Prefiks kuponu**

    -   **Do czego służy to ustawienie:** Pozwala dodać niestandardowy prefiks do unikalnych kodów kuponów generowanych przez moduł.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Kody kuponów będą całkowicie losowe (np. „ABCDEF123”).
        -   *Jeśli ustawiono prefiks (np. „NEWSLETTER-”):* Kody kuponów będą zaczynać się od tego prefiksu (np. „NEWSLETTER-ABCDEF123”). Pomaga to zidentyfikować źródło kuponu.
    -   **Zalecana wartość:** „NEWSLETTER-” lub „WELCOME-”.
    -   **Scenariusz / przykład dla sprzedawcy:** Użycie „NEWSLETTER-” pomaga szybko zidentyfikować, które kupony pochodzą z zapisów do newslettera podczas przeglądania zamówień lub statystyk.
6.  **Wyklucz produkty z określonych kategorii**

    -   **Do czego służy to ustawienie:** Pozwala wybrać konkretne kategorie produktów, dla których kupon NIE będzie miał zastosowania.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli nie wybrano żadnych kategorii:* Kupon może być użyty na dowolny produkt w Twoim sklepie.
        -   *Jeśli wybrano kategorie (np. „Wyprzedaż”, „Karty podarunkowe”):* Kupon nie może być użyty do zakupu produktów z tych kategorii.
    -   **Zalecana wartość:** Użyj tego, jeśli masz produkty o niskiej marży, karty podarunkowe lub konkretne produkty promocyjne, których nie chcesz dodatkowo przeceniać.
    -   **Scenariusz / przykład dla sprzedawcy:** Nie chcesz, aby kupon dotyczył już przecenionych produktów z kategorii „Wyprzedaż”. Wybierzesz tutaj kategorię „Wyprzedaż”.
7.  **Wyklucz produkty z określonych producentów**

    -   **Do czego służy to ustawienie:** Podobnie jak w przypadku kategorii, pozwala wykluczyć produkty od konkretnych producentów z rabatu kuponem.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli nie wybrano żadnych producentów:* Kupon dotyczy wszystkich producentów.
        -   *Jeśli wybrano producentów (np. „Marka X”):* Produkty od „Marki X” nie mogą być zakupione z kuponem.
    -   **Zalecana wartość:** Przydatne, jeśli masz ekskluzywne marki lub marki z rygorystycznymi politykami cenowymi.
    -   **Scenariusz / przykład dla sprzedawcy:** Konkretna luksusowa marka „Luxury Watches Inc.” nie zezwala na żadne rabaty. Wybierzesz tutaj „Luxury Watches Inc.”.
8.  **Wyklucz produkty z określonych dostawców**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty od konkretnych dostawców z rabatu kuponem.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli nie wybrano żadnych dostawców:* Kupon dotyczy wszystkich dostawców.
        -   *Jeśli wybrano dostawców (np. „Dostawca Y”):* Produkty od „Dostawcy Y” nie mogą być zakupione z kuponem.
    -   **Zalecana wartość:** Mniej powszechne w promocjach skierowanych do klientów, ale przydatne dla wewnętrznego inwentarza lub konkretnych umów z dostawcami.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz dostawcę „Wholesale Electronics”, którego produkty są już w bardzo niskich cenach. Możesz wykluczyć je z dalszych rabatów.
9.  **Wyklucz produkty z określonymi atrybutami**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty z określonymi kombinacjami atrybutów (np. „Kolor: Czerwony”, „Rozmiar: XL”) z rabatu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli nie wybrano żadnych atrybutów:* Kupon dotyczy wszystkich atrybutów produktu.
        -   *Jeśli wybrano atrybuty:* Produkty pasujące do tych atrybutów nie mogą być przecenione.
    -   **Zalecana wartość:** Użyj tego dla bardzo specyficznych wariantów produktów, które chcesz wykluczyć.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz limitowaną edycję wariantu produktu „Złoty”, którego nigdy nie przeceniasz. Wybierzesz tutaj atrybut „Kolor: Złoty”.
10. **Wyklucz produkty z określonymi cechami**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie ich cech (np. „Materiał: Skóra”, „Wodoodporny: Tak”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli nie wybrano żadnych cech:* Kupon dotyczy wszystkich cech produktu.
        -   *Jeśli wybrano cechy:* Produkty pasujące do tych cech nie mogą być przecenione.
    -   **Zalecana wartość:** Podobnie jak w przypadku atrybutów, dla specyficznych charakterystyk produktu.
    -   **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz ręcznie robione przedmioty z cechą „Ręcznie robione: Tak” i chcesz je wykluczyć z rabatów.
11. **Wyklucz produkty z określonymi przedziałami cenowymi**

    -   **Do czego służy to ustawienie:** Pozwala zdefiniować przedział cenowy dla produktów, które powinny być wykluczone z rabatu kuponem.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli nie ustawiono przedziału:* Wszystkie ceny produktów są kwalifikujące się.
        -   *Jeśli ustawiono przedział (np. „0-10” lub „500-9999”):* Produkty mieszczące się w tym przedziale cenowym nie zostaną przecenione kuponem.
    -   **Zalecana wartość:** Użyj tego, aby chronić przedmioty o bardzo niskiej marży lub przedmioty o bardzo wysokiej wartości przed przeceną.
    -   **Scenariusz / przykład dla sprzedawcy:** Nie chcesz, aby kupon dotyczył przedmiotów wycenionych poniżej 10 €, więc ustawiasz przedział „0-10”.
12. **Wyklucz produkty z określonymi przedziałami wagowymi**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie ich przedziału wagowego.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli nie ustawiono przedziału:* Wszystkie wagi produktów są kwalifikujące się.
        -   *Jeśli ustawiono przedział (np. „0-0.5kg” lub „10kg-999kg”):* Produkty mieszczące się w tym przedziale wagowym nie zostaną przecenione.
    -   **Zalecana wartość:** Mniej powszechne dla zasad rabatowych, ale może być przydatne dla specyficznych kwestii kosztów wysyłki.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz wykluczyć bardzo ciężkie przedmioty, które już generują wysokie koszty wysyłki, z dalszych rabatów.
13. **Wyklucz produkty z określonymi wymiarami**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie ich wymiarów (szerokość, wysokość, głębokość).
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli nie ustawiono wymiarów:* Wszystkie wymiary produktów są kwalifikujące się.
        -   *Jeśli ustawiono wymiary:* Produkty mieszczące się w tych przedziałach wymiarowych nie zostaną przecenione.
    -   **Zalecana wartość:** Podobnie jak waga, zazwyczaj dla specyficznych kwestii wysyłki lub pakowania.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz wykluczyć przedmioty o niestandardowych rozmiarach, które wymagają specjalnego opakowania, z rabatów.
14. **Wyklucz produkty z określonymi identyfikatorami produktów**

    -   **Do czego służy to ustawienie:** Pozwala ręcznie wprowadzić listę identyfikatorów produktów oddzielonych przecinkami, które powinny być wykluczone z rabatu kuponem.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie produkty są kwalifikujące się.
        -   *Jeśli wprowadzono identyfikatory (np. „123, 456, 789”):* Te konkretne produkty nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj tego dla pojedynczych produktów, których nigdy nie chcesz przeceniać, takich jak bestsellery lub nowości.
    -   **Scenariusz / przykład dla sprzedawcy:** Twój flagowy produkt o identyfikatorze „1001” nigdy nie jest przeceniany. Wprowadzisz tutaj „1001”.
15. **Wyklucz produkty z określonymi kombinacjami**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć konkretne kombinacje produktów (np. określony rozmiar i kolor konkretnego produktu) z rabatu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie kombinacje są kwalifikujące się.
        -   *Jeśli wybrano kombinacje:* Te konkretne kombinacje nie zostaną przecenione.
    -   **Zalecana wartość:** Dla bardzo szczegółowej kontroli nad rabatami.
    -   **Scenariusz / przykład dla sprzedawcy:** Konkretna kombinacja koszulki (np. „Czerwona, XL”) to edycja limitowana i nie powinna być przeceniana.
16. **Wyklucz produkty z określonymi tagami**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie przypisanych im tagów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie produkty są kwalifikujące się.
        -   *Jeśli wprowadzono tagi:* Produkty z tymi tagami nie zostaną przecenione.
    -   **Zalecana wartość:** Przydatne, jeśli intensywnie używasz tagów do kategoryzacji produktów.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz produkty oznaczone tagiem „Nowość”, które chcesz wykluczyć z początkowych rabatów.
17. **Wyklucz produkty z określonymi cechami (ponownie, może być duplikatem lub innym typem wyboru cech)**

    -   **Do czego służy to ustawienie:** Może to być bardziej zaawansowana lub inna metoda wyboru cech w porównaniu do wcześniejszej. Pozwala wykluczyć produkty na podstawie ich cech.
    -   **Efekt zmiany tego ustawienia:** Podobnie jak w przypadku poprzedniego wykluczenia cech, zapewnia, że produkty z wybranymi cechami nie zostaną przecenione.
    -   **Zalecana wartość:** Sprawdź, czy oferuje różne opcje wyboru lub jest przeznaczone dla innego typu cech.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor cech dotyczył prostych cech, ten może dotyczyć cech z konkretnymi wartościami (np. „Materiał: Złoto” vs. tylko „Materiał”).
18. **Wyklucz produkty z określonymi typami produktów**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie ich typu (np. „Produkt standardowy”, „Pakiet produktów”, „Produkt wirtualny”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie typy produktów są kwalifikujące się.
        -   *Jeśli wybrano typy:* Produkty tych typów nie zostaną przecenione.
    -   **Zalecana wartość:** Przydatne, jeśli nie chcesz przeceniać produktów wirtualnych lub pakietów produktów.
    -   **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz e-booki (produkty wirtualne) i chcesz je wykluczyć z rabatu kuponem.
19. **Wyklucz produkty z określonymi statusami produktów**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie ich statusu (np. „Aktywny”, „Nieaktywny”, „Brak w magazynie”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie statusy produktów są kwalifikujące się.
        -   *Jeśli wybrano statusy:* Produkty z tymi statusami nie zostaną przecenione.
    -   **Zalecana wartość:** Zazwyczaj przeceniasz tylko aktywne produkty dostępne w magazynie.
    -   **Scenariusz / przykład dla sprzedawcy:** Możesz chcieć wykluczyć produkty „Nieaktywne” lub „Brak w magazynie” z rabatu, nawet jeśli są nadal widoczne na stronie.
20. **Wyklucz produkty z określoną widocznością**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie ich ustawień widoczności (np. „Tylko w katalogu”, „Tylko w wyszukiwaniu”, „Wszędzie”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie ustawienia widoczności produktów są kwalifikujące się.
        -   *Jeśli wybrano opcje widoczności:* Produkty z tymi ustawieniami widoczności nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj tego, jeśli masz produkty o ograniczonej widoczności, które nie powinny być przeceniane.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz produkty widoczne „Tylko w wyszukiwaniu”, które są częścią specjalnej, niepodlegającej rabatom kampanii.
21. **Wyklucz produkty z określonymi warunkami**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie ich stanu (np. „Nowy”, „Używany”, „Odnowiony”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie warunki produktów są kwalifikujące się.
        -   *Jeśli wybrano warunki:* Produkty z tymi warunkami nie zostaną przecenione.
    -   **Zalecana wartość:** Przydatne, jeśli sprzedajesz używane lub odnowione przedmioty, które są już mocno przecenione.
    -   **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz przedmioty „Używane” i nie chcesz stosować do nich dalszych rabatów.
22. **Wyklucz produkty z określoną dostępnością**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie ich statusu dostępności (np. „W magazynie”, „Dostępne na zamówienie”, „Brak w magazynie”).
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie statusy dostępności produktów są kwalifikujące się.
        -   *Jeśli wybrano opcje dostępności:* Produkty z tymi statusami nie zostaną przecenione.
    -   **Zalecana wartość:** Zazwyczaj przeceniasz tylko produkty „W magazynie”.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz upewnić się, że kupony dotyczą tylko produktów, które są natychmiast „W magazynie”.
23. **Wyklucz produkty z określonymi czasami dostawy**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie ich szacowanego czasu dostawy.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie czasy dostawy są kwalifikujące się.
        -   *Jeśli wybrano czasy dostawy:* Produkty z tymi czasami dostawy nie zostaną przecenione.
    -   **Zalecana wartość:** Mniej powszechne dla zasad rabatowych, ale może być używane dla przedmiotów w przedsprzedaży.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz produkty z długimi czasami dostawy „Przedsprzedaż”, których nie chcesz przeceniać.
24. **Wyklucz produkty z określonymi przewoźnikami**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie dostępnych dla nich przewoźników.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszyscy przewoźnicy są kwalifikujący się.
        -   *Jeśli wybrano przewoźników:* Produkty, które mogą być wysyłane tylko przez tych przewoźników, nie zostaną przecenione.
    -   **Zalecana wartość:** Bardzo specyficzny przypadek użycia, być może dla przedmiotów wymagających specjalnej wysyłki.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz produkty, które muszą być wysyłane przez wyspecjalizowanego „Przewoźnika Towarów Kruchych” i chcesz je wykluczyć z rabatów.
25. **Wyklucz produkty z określonymi krajami**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie krajów, dla których są dostępne.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie kraje są kwalifikujące się.
        -   *Jeśli wybrano kraje:* Produkty dostępne tylko w tych krajach nie zostaną przecenione.
    -   **Zalecana wartość:** Przydatne dla ograniczeń produktów specyficznych dla regionu geograficznego.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz produkty sprzedawane tylko w „USA”, które są już częścią promocji specyficznej dla USA i nie powinny być dalej przeceniane.
26. **Wyklucz produkty z określonymi stanami**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie stanów, dla których są dostępne.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie stany są kwalifikujące się.
        -   *Jeśli wybrano stany:* Produkty dostępne tylko w tych stanach nie zostaną przecenione.
    -   **Zalecana wartość:** Bardziej szczegółowe ograniczenia geograficzne.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz produkty dostępne tylko w „Kalifornii”, które są już częścią promocji specyficznej dla Kalifornii.
27. **Wyklucz produkty z określonymi strefami**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie stref wysyłki, dla których są dostępne.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie strefy są kwalifikujące się.
        -   *Jeśli wybrano strefy:* Produkty dostępne tylko w tych strefach nie zostaną przecenione.
    -   **Zalecana wartość:** Przydatne dla międzynarodowych stref wysyłki.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz produkty dostępne tylko w strefie wysyłki „Europa”, których nie chcesz przeceniać.
28. **Wyklucz produkty z określonymi walutami**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie walut, dla których są dostępne.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie waluty są kwalifikujące się.
        -   *Jeśli wybrano waluty:* Produkty dostępne tylko w tych walutach nie zostaną przecenione.
    -   **Zalecana wartość:** Dla sklepów wielowalutowych ze specyficznymi strategiami cenowymi produktów.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz produkty wycenione w „USD”, które są częścią kampanii specyficznej dla USD.
29. **Wyklucz produkty z określonymi grupami**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie grup klientów, dla których są dostępne.
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie grupy klientów są kwalifikujące się.
        -   *Jeśli wybrano grupy:* Produkty dostępne tylko dla tych grup klientów nie zostaną przecenione.
    -   **Zalecana wartość:** Dla programów B2B lub lojalnościowych, gdzie niektóre produkty są ekskluzywne.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz produkty dostępne tylko dla klientów „Hurtowych”, które nie powinny być przeceniane ogólnym kuponem z newslettera.
30. **Wyklucz produkty z określonych sklepów**

    -   **Do czego służy to ustawienie:** Pozwala wykluczyć produkty na podstawie sklepów, w których są dostępne (dla konfiguracji wielosklepowych).
    -   **Efekt zmiany tego ustawienia:**
        -   *Jeśli pozostawiono puste:* Wszystkie sklepy są kwalifikujące się.
        -   *Jeśli wybrano sklepy:* Produkty dostępne tylko w tych sklepach nie zostaną przecenione.
    -   **Zalecana wartość:** Niezbędne w środowiskach wielosklepowych do kontrolowania rabatów dla poszczególnych sklepów.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz konkretny „Sklep Outletowy” w swojej konfiguracji wielosklepowej, gdzie produkty są już mocno przecenione.
31. **Wyklucz produkty z określonymi cechami produktu (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Jest to prawdopodobnie kolejny sposób wyboru cech produktu do wykluczenia. Ważne jest, aby sprawdzić, czy oferuje różne metody wyboru, czy jest to pole redundantne.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi cechami nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru cech do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzednie selektory cech dotyczyły ogólnych cech, ten może dotyczyć cech z konkretnymi wartościami (np. „Materiał: Bawełna” vs. tylko „Materiał”).
32. **Wyklucz produkty z określonymi tagami produktu (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie tagów, może to być inny interfejs do wyboru tagów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi tagami nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru tagów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor tagów dotyczył ogólnych tagów, ten może dotyczyć tagów z konkretnymi wartościami lub innym wyświetlaniem.
33. **Wyklucz produkty z określonymi atrybutami produktu (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie atrybutów, może to być inny interfejs do wyboru atrybutów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi atrybutami nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru atrybutów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor atrybutów dotyczył ogólnych atrybutów, ten może dotyczyć atrybutów z konkretnymi wartościami lub innym wyświetlaniem.
34. **Wyklucz produkty z określonymi kombinacjami produktów (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie kombinacji, może to być inny interfejs do wyboru kombinacji.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi kombinacjami nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru kombinacji do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor kombinacji dotyczył ogólnych kombinacji, ten może dotyczyć kombinacji z konkretnymi wartościami lub innym wyświetlaniem.
35. **Wyklucz produkty z określonymi typami produktów (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie typów produktów, może to być inny interfejs do wyboru typów produktów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi typami produktów nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru typów produktów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor typów produktów dotyczył ogólnych typów produktów, ten może dotyczyć typów produktów z konkretnymi wartościami lub innym wyświetlaniem.
36. **Wyklucz produkty z określonymi statusami produktów (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie statusów produktów, może to być inny interfejs do wyboru statusów produktów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi statusami produktów nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru statusów produktów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor statusów produktów dotyczył ogólnych statusów produktów, ten może dotyczyć statusów produktów z konkretnymi wartościami lub innym wyświetlaniem.
37. **Wyklucz produkty z określoną widocznością produktów (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie widoczności produktów, może to być inny interfejs do wyboru widoczności produktów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybraną widocznością produktów nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru widoczności produktów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor widoczności produktów dotyczył ogólnej widoczności produktów, ten może dotyczyć widoczności produktów z konkretnymi wartościami lub innym wyświetlaniem.
38. **Wyklucz produkty z określonymi warunkami produktów (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie warunków produktów, może to być inny interfejs do wyboru warunków produktów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi warunkami produktów nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru warunków produktów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor warunków produktów dotyczył ogólnych warunków produktów, ten może dotyczyć warunków produktów z konkretnymi wartościami lub innym wyświetlaniem.
39. **Wyklucz produkty z określoną dostępnością produktów (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie dostępności produktów, może to być inny interfejs do wyboru dostępności produktów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybraną dostępnością produktów nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru dostępności produktów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor dostępności produktów dotyczył ogólnej dostępności produktów, ten może dotyczyć dostępności produktów z konkretnymi wartościami lub innym wyświetlaniem.
40. **Wyklucz produkty z określonymi czasami dostawy produktów (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie czasów dostawy produktów, może to być inny interfejs do wyboru czasów dostawy produktów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi czasami dostawy produktów nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru czasów dostawy produktów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor czasów dostawy produktów dotyczył ogólnych czasów dostawy produktów, ten może dotyczyć czasów dostawy produktów z konkretnymi wartościami lub innym wyświetlaniem.
41. **Wyklucz produkty z określonymi przewoźnikami produktów (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie przewoźników produktów, może to być inny interfejs do wyboru przewoźników produktów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi przewoźnikami produktów nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru przewoźników produktów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor przewoźników produktów dotyczył ogólnych przewoźników produktów, ten może dotyczyć przewoźników produktów z konkretnymi wartościami lub innym wyświetlaniem.
42. **Wyklucz produkty z określonymi krajami produktów (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie krajów produktów, może to być inny interfejs do wyboru krajów produktów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi krajami produktów nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru krajów produktów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor krajów produktów dotyczył ogólnych krajów produktów, ten może dotyczyć krajów produktów z konkretnymi wartościami lub innym wyświetlaniem.
43. **Wyklucz produkty z określonymi stanami produktów (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie stanów produktów, może to być inny interfejs do wyboru stanów produktów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi stanami produktów nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru stanów produktów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor stanów produktów dotyczył ogólnych stanów produktów, ten może dotyczyć stanów produktów z konkretnymi wartościami lub innym wyświetlaniem.
44. **Wyklucz produkty z określonymi strefami produktów (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie stref produktów, może to być inny interfejs do wyboru stref produktów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi strefami produktów nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru stref produktów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor stref produktów dotyczył ogólnych stref produktów, ten może dotyczyć stref produktów z konkretnymi wartościami lub innym wyświetlaniem.
45. **Wyklucz produkty z określonymi walutami produktów (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie walut produktów, może to być inny interfejs do wyboru walut produktów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi walutami produktów nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru walut produktów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor walut produktów dotyczył ogólnych walut produktów, ten może dotyczyć walut produktów z konkretnymi wartościami lub innym wyświetlaniem.
46. **Wyklucz produkty z określonymi grupami produktów (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie grup produktów, może to być inny interfejs do wyboru grup produktów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi grupami produktów nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru grup produktów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor grup produktów dotyczył ogólnych grup produktów, ten może dotyczyć grup produktów z konkretnymi wartościami lub innym wyświetlaniem.
47. **Wyklucz produkty z określonych sklepów produktów (kolejna instancja, sprawdź niuanse)**

    -   **Do czego służy to ustawienie:** Podobnie jak poprzednie wykluczenie sklepów produktów, może to być inny interfejs do wyboru sklepów produktów.
    -   **Efekt zmiany tego ustawienia:** Zapewnia, że produkty z wybranymi sklepami produktów nie zostaną przecenione.
    -   **Zalecana wartość:** Użyj, jeśli zapewnia wygodniejszy lub bardziej specyficzny sposób wyboru sklepów produktów do wykluczenia.
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli poprzedni selektor sklepów produktów dotyczył ogólnych sklepów produktów, ten może dotyczyć sklepów produktów z konkretnymi wartościami lub innym wyświetlaniem.

    *Uwaga: Liczne ustawienia „Wyklucz produkty z określonych…” (41-47) wydają się być powtórzone. Może to wynikać z dynamicznego generowania formularza, gdzie każdy typ wykluczenia jest wymieniony, lub może wskazywać na błąd/redundancję w interfejsie konfiguracji modułu. W rzeczywistym scenariuszu programista zweryfikowałby to. W dokumentacji wymieniamy je tak, jak zostały wykryte.*

### 2.2 Dedykowane Ekrany Administracyjne i Widoki Kontrolerów

#### 2.2.1 Lista Kuponów (Panel administracyjny > Unikalny kupon za zapis do newslettera > Kupony)

-   **Nazwa Ekranu i Lokalizacja w Menu:** Po zainstalowaniu modułu w Panelu administracyjnym PrestaShop pojawi się nowa pozycja menu, zazwyczaj pod **Katalog** lub **Marketing**, o nazwie „Unikalny kupon za zapis do newslettera” lub podobnej. Kliknięcie na nią ujawni podmenu, takie jak „Kupony”.
-   **Dostępne Akcje i Ustawienia:** Ten ekran wyświetla listę wszystkich unikalnych kuponów, które zostały wygenerowane przez moduł za zapisy do newslettera.
    -   **Widok Siatki / Zarządzania:** Zobaczysz tabelę z kolumnami takimi jak:
        -   **ID:** Unikalny identyfikator wpisu kuponu.
        -   **Klient:** Adres e-mail klienta, który otrzymał kupon.
        -   **Data dostarczenia:** Data i godzina wygenerowania i wysłania kuponu.
        -   **Kod kuponu:** Rzeczywisty unikalny kod rabatowy.
        -   **Akcje:** Zazwyczaj możesz przeglądać szczegóły, edytować (choć edycja unikalnych, automatycznie generowanych kuponów jest mniej powszechna) lub usuwać wpisy.
-   **Efekt zmian:**
    -   **Przeglądanie:** Pozwala monitorować wydane kupony, sprawdzać, kto je otrzymał, i śledzić ich kody. Jest to kluczowe dla rozwiązywania problemów lub zapytań obsługi klienta.
    -   **Usuwanie:** Usunięcie wpisu kuponu z tej listy zazwyczaj unieważni odpowiedni kod kuponu, uniemożliwiając jego użycie. Używaj ostrożnie.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie sprawdzaj tę listę, aby monitorować skuteczność zachęty do zapisu do newslettera. Jeśli klient zgłosi, że nie otrzymał kuponu, możesz zweryfikować jego wygenerowanie i kod tutaj. W razie potrzeby możesz również ręcznie usunąć wygasłe lub problematyczne kupony.

### 2.3 Tabela Szybkiego Odniesienia do Konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i Wpływ |
| --- | --- | --- | --- |
| Konfiguracja Modułu | Wartość kuponu (kwota lub procent) | np. „10” lub „10%” | Definiuje kwotę/procent rabatu kuponu. |
| Konfiguracja Modułu | Minimalna kwota | „0” (lub pożądana wartość) | Minimalna całkowita wartość zamówienia dla ważności kuponu. |
| Konfiguracja Modułu | Ważność kuponu (dni) | „30” (lub pożądana wartość) | Liczba dni ważności kuponu po wygenerowaniu. |
| Konfiguracja Modułu | Opis kuponu | „Rabat za zapis do newslettera” | Tekstowy opis kuponu. |
| Konfiguracja Modułu | Prefiks kuponu | „NEWSLETTER-” (lub puste) | Niestandardowy prefiks dla generowanych kodów kuponów. |
| Konfiguracja Modułu | Wyklucz produkty z określonych kategorii | (Brak wybranych) | Zapobiega użyciu kuponu w wybranych kategoriach. |
| Konfiguracja Modułu | Wyklucz produkty z określonych producentów | (Brak wybranych) | Zapobiega użyciu kuponu w wybranych producentach. |
| Konfiguracja Modułu | Wyklucz produkty z określonych dostawców | (Brak wybranych) | Zapobiega użyciu kuponu w wybranych dostawcach. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi atrybutami | (Brak wybranych) | Zapobiega użyciu kuponu na produktach z wybranymi atrybutami. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi cechami | (Brak wybranych) | Zapobiega użyciu kuponu na produktach z wybranymi cechami. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi przedziałami cenowymi | (Puste) | Zapobiega użyciu kuponu na produktach w określonym przedziale cenowym. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi przedziałami wagowymi | (Puste) | Zapobiega użyciu kuponu na produktach w określonym przedziale wagowym. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi wymiarami | (Puste) | Zapobiega użyciu kuponu na produktach w określonych przedziałach wymiarowych. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi identyfikatorami produktów | (Puste) | Zapobiega użyciu kuponu na konkretnych identyfikatorach produktów. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi kombinacjami | (Brak wybranych) | Zapobiega użyciu kuponu na konkretnych kombinacjach produktów. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi tagami | (Brak wybranych) | Zapobiega użyciu kuponu na produktach z konkretnymi tagami. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi cechami (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor cech) |
| Konfiguracja Modułu | Wyklucz produkty z określonymi typami produktów | (Brak wybranych) | Zapobiega użyciu kuponu na konkretnych typach produktów. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi statusami produktów | (Brak wybranych) | Zapobiega użyciu kuponu na konkretnych statusach produktów. |
| Konfiguracja Modułu | Wyklucz produkty z określoną widocznością | (Brak wybranych) | Zapobiega użyciu kuponu na konkretnych ustawieniach widoczności produktów. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi warunkami | (Brak wybranych) | Zapobiega użyciu kuponu na konkretnych warunkach produktów. |
| Konfiguracja Modułu | Wyklucz produkty z określoną dostępnością | (Brak wybranych) | Zapobiega użyciu kuponu na konkretnych statusach dostępności produktów. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi czasami dostawy | (Brak wybranych) | Zapobiega użyciu kuponu na konkretnych czasach dostawy produktów. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi przewoźnikami | (Brak wybranych) | Zapobiega użyciu kuponu na konkretnych przewoźnikach produktów. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi krajami | (Brak wybranych) | Zapobiega użyciu kuponu na konkretnych krajach produktów. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi stanami | (Brak wybranych) | Zapobiega użyciu kuponu na konkretnych stanach produktów. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi strefami | (Brak wybranych) | Zapobiega użyciu kuponu na konkretnych strefach produktów. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi walutami | (Brak wybranych) | Zapobiega użyciu kuponu na konkretnych walutach produktów. |
| Konfiguracja Modułu | Wyklucz produkty z określonymi grupami | (Brak wybranych) | Zapobiega użyciu kuponu na konkretnych grupach klientów. |
| Konfiguracja Modułu | Wyklucz produkty z określonych sklepów | (Brak wybranych) | Zapobiega użyciu kuponu w konkretnych sklepach (wielosklepowość). |
| Konfiguracja Modułu | Wyklucz produkty z określonymi cechami produktu (3) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor cech) |
| Konfiguracja Modułu | Wyklucz produkty z określonymi tagami produktu (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor tagów) |
| Konfiguracja Modułu | Wyklucz produkty z określonymi atrybutami produktu (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor atrybutów) |
| Konfiguracja Modułu | Wyklucz produkty z określonymi kombinacjami produktów (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor kombinacji) |
| Konfiguracja Modułu | Wyklucz produkty z określonymi typami produktów (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor typów produktów) |
| Konfiguracja Modułu | Wyklucz produkty z określonymi statusami produktów (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor statusów produktów) |
| Konfiguracja Modułu | Wyklucz produkty z określoną widocznością produktów (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor widoczności produktów) |
| Konfiguracja Modułu | Wyklucz produkty z określonymi warunkami produktów (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor warunków produktów) |
| Konfiguracja Modułu | Wyklucz produkty z określoną dostępnością produktów (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor dostępności produktów) |
| Konfiguracja Modułu | Wyklucz produkty z określonymi czasami dostawy produktów (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor czasów dostawy produktów) |
| Konfiguracja Modułu | Wyklucz produkty z określonymi przewoźnikami produktów (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor przewoźników produktów) |
| Konfiguracja Modułu | Wyklucz produkty z określonymi krajami produktów (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor krajów produktów) |
| Konfiguracja Modułu | Wyklucz produkty z określonymi stanami produktów (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor stanów produktów) |
| Konfiguracja Modułu | Wyklucz produkty z określonymi strefami produktów (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor stref produktów) |
| Konfiguracja Modułu | Wyklucz produkty z określonymi walutami produktów (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor walut produktów) |
| Konfiguracja Modułu | Wyklucz produkty z określonymi grupami produktów (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor grup produktów) |
| Konfiguracja Modułu | Wyklucz produkty z określonych sklepów produktów (2) | (Brak wybranych) | (Możliwy duplikat/alternatywny selektor sklepów produktów) |
| Lista Kuponów | ID | N/A | Unikalny identyfikator wpisu kuponu. |
| Lista Kuponów | Klient | N/A | E-mail klienta, który otrzymał kupon. |
| Lista Kuponów | Data dostarczenia | N/A | Data i godzina wygenerowania kuponu. |
| Lista Kuponów | Kod kuponu | N/A | Unikalny kod rabatowy. |

## 3. Rozwiązywanie Problemów dla Sprzedawców i Często Zadawane Pytania (FAQ)

**P: Moi klienci zapisują się, ale nie otrzymują e-maila z kuponem. Co powinienem zrobić?**
O:

1.  **Sprawdź Foldery Spam:** Doradź klientom, aby sprawdzili swoje foldery ze spamem lub niechcianą pocztą.
2.  **Zweryfikuj Konfigurację E-mail:** Upewnij się, że ustawienia e-mail Twojego sklepu PrestaShop (Zaawansowane > E-mail) są poprawnie skonfigurowane i niezawodnie wysyłają e-maile. Przetestuj wysyłanie prostego e-maila z PrestaShop.
3.  **Sprawdź Konfigurację Modułu:** Przejdź do **Moduły > Menedżer modułów > Unikalny kupon za zapis do newslettera > Konfiguruj**. Upewnij się, że wszystkie ustawienia, zwłaszcza wartość kuponu, są poprawnie ustawione.
4.  **Przejrzyj Listę Kuponów:** Przejdź do **Panel administracyjny > Unikalny kupon za zapis do newslettera > Kupony**. Sprawdź, czy kupon został faktycznie wygenerowany i wymieniony dla adresu e-mail klienta. Jeśli tam jest, problem dotyczy dostarczania e-maili; jeśli nie, moduł może nie uruchamiać się poprawnie.
5.  **Wyczyść Pamięć Podręczną:** Czasami wyczyszczenie pamięci podręcznej PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) może rozwiązać nieoczekiwane zachowanie.

**P: Kod kuponu jest generowany, ale nie stosuje prawidłowej zniżki lub ma błędne warunki.**
O:

1.  **Ponownie sprawdź Konfigurację Modułu:** Przejdź do **Moduły > Menedżer modułów > Unikalny kupon za zapis do newslettera > Konfiguruj**. Dokładnie przejrzyj wszystkie ustawienia:
    -   **Wartość kuponu:** Czy jest to prawidłowa kwota lub procent?
    -   **Minimalna kwota:** Czy koszyk klienta spełnia to minimum?
    -   **Ustawienia wykluczeń:** Czy są jakieś kategorie, producenci lub konkretne produkty wykluczone, które klient próbuje kupić?
2.  **Przetestuj z Nową Subskrypcją:** Utwórz nowy adres e-mail i zapisz się do swojego newslettera, aby wygenerować świeży kupon. Przetestuj ten nowy kupon samodzielnie, aby odtworzyć problem.

**P: Czy mogę dostosować szablon e-maila, który wysyła kupon?**
O: Ten moduł zazwyczaj integruje się z domyślnym systemem e-mail PrestaShop. Kod kuponu jest zazwyczaj wstawiany do istniejącego szablonu e-maila (takiego jak e-mail potwierdzający newsletter). Aby dostosować wygląd lub tekst e-maila, zazwyczaj modyfikujesz odpowiednie pliki szablonów e-mail w katalogu `mails/` Twojego szablonu (np. `mails/pl/newsletter.html` lub `mails/pl/newsletter.txt`). W przypadku zaawansowanych dostosowań może być potrzebny programista.

**P: Czy ten moduł działa z niestandardowymi formularzami zapisu do newslettera lub wyskakującymi okienkami?**
O: Ten moduł jest zaprojektowany do pracy ze standardowym procesem subskrypcji newslettera PrestaShop. Jeśli Twój niestandardowy formularz lub wyskakujące okienko poprawnie integruje się z podstawowym modułem newslettera PrestaShop (np. poprzez wywołanie tej samej akcji subskrypcji), to ten moduł powinien działać poprawnie. Jeśli używa całkowicie niestandardowej metody subskrypcji, może wymagać niestandardowej integracji przez programistę.

**P: Mam konfigurację wielosklepową. Czy ten moduł działa dla wszystkich moich sklepów?**
O: Tak, moduł powinien być kompatybilny ze środowiskami wielosklepowymi. Ustawienia konfiguracji, w tym wykluczenia, powinny być zarządzalne dla każdego sklepu, jeśli system konfiguracji PrestaShop jest poprawnie wykorzystywany przez moduł. Zawsze dokładnie testuj w konfiguracji wielosklepowej.

## 4. Przewodnik dla Programistów i Webmasterów (Architektura Techniczna i Mapa Kodu)

### 4.1 Przegląd Architektury

Moduł „Unikalny kupon za zapis do newslettera” (`newslettervoucher`) przestrzega standardowej architektury modułów PrestaShop, głównie rozszerzając `Module` i wykorzystując `AdminController` dla swojego interfejsu Panelu administracyjnego. Integruje się z istniejącym przepływem subskrypcji newslettera poprzez podłączanie się do odpowiednich zdarzeń w celu generowania i dostarczania unikalnych obiektów `CartRule` (kuponów). Moduł wykorzystuje klasę `Configuration` PrestaShop do swoich ustawień oraz `ObjectModel` do zarządzania własnymi encjami `nvoucher`.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `controllers/front/cronjob.php`
    -   **Nazwa Klasy i Klasa Rodzicielska:** `NewsletterVoucherCronjobModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler jest prawdopodobnie przeznaczony do obsługi żądań zadań cron. Zazwyczaj zawierałby logikę do przetwarzania zakolejkowanych generacji kuponów lub czyszczenia wygasłych kuponów, wywoływaną przez zewnętrzne wywołanie cron. Może nie renderować bezpośrednio strony, ale wykonywać zadania w tle.
-   `controllers/front/index.php`
    -   **Nazwa Klasy i Klasa Rodzicielska:** `NewsletterVoucherIndexModuleFrontController` rozszerza `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler może służyć jako domyślny lub awaryjny kontroler front-office, lub może być używany do prostych żądań AJAX związanych z funkcjonalnością modułu w front-office, chociaż główne generowanie kuponów jest sterowane zdarzeniami. Biorąc pod uwagę cel modułu, jest mniej prawdopodobne, aby renderował złożone widoki front-office.

#### Kontrolery Administracyjne Back-Office

-   `controllers/admin/AdminNewsletterVoucherVouchers.php`
    -   **Nazwa Klasy i Klasa Rodzicielska:** `AdminNewsletterVoucherVouchersController` rozszerza `ModuleAdminController`.
    -   **Nazwa Zakładki i Zarządzana Encja:** Ten kontroler zarządza listą „Kuponów” w Panelu administracyjnym PrestaShop, w szczególności zajmując się encją `nvoucher` (prawdopodobnie niestandardowy `ObjectModel` do śledzenia wygenerowanych kuponów). Zapewnia standardowy interfejs CRUD (Create, Read, Update, Delete) dla tych wpisów kuponów.
-   `controllers/admin/index.php`
    -   **Nazwa Klasy i Klasa Rodzicielska:** `AdminNewsletterVoucherIndexController` rozszerza `ModuleAdminController`.
    -   **Nazwa Zakładki i Zarządzana Encja:** Ten kontroler prawdopodobnie służy jako główny punkt wejścia lub pulpit nawigacyjny dla modułu w Panelu administracyjnym, potencjalnie wyświetlając przegląd lub przekierowując do kontrolera `AdminNewsletterVoucherVouchers`. Może również obsługiwać początkowy formularz konfiguracji modułu (`getContent()`), jeśli nie znajduje się on bezpośrednio w głównym pliku modułu.

### 4.3 Klasy Bazowe i Modele (`classes/`)

Dostarczony spis nie wskazuje na żadne niestandardowe klasy w katalogu `classes/`. Sugeruje to, że moduł może definiować swój główny `ObjectModel` (np. dla wpisów `nvoucher`) bezpośrednio w głównym pliku modułu (`newslettervoucher/cronjob.php`) lub że głównie współdziała z podstawowymi `ObjectModel` PrestaShop `CartRule` i `Customer`.

Jeśli tabela `nvoucher` jest zarządzana, jej definicja zazwyczaj znajdowałaby się w metodzie `install()` głównego pliku modułu lub w dedykowanej klasie `ObjectModel`. Prawdopodobnie zawierałaby pola takie jak `id_nvoucher`, `id_customer`, `voucher_code`, `date_add`, `date_upd`, `id_cart_rule`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `newslettervoucher/lib/voucherengine/script.js`
    -   **Zakres:** Prawdopodobnie Panel administracyjny.
    -   **Opis:** Ten skrypt prawdopodobnie obsługuje dynamiczne zachowanie w formularzach konfiguracji modułu lub na liście kuponów w Panelu administracyjnym. Może to obejmować:
        -   Wywołania AJAX do zapisywania ustawień.
        -   Dynamiczne wyświetlanie/ukrywanie pól konfiguracji na podstawie innych wyborów.
        -   Logikę filtrowania, sortowania lub paginacji dla listy kuponów.
        -   Walidację danych wejściowych lub interaktywne elementy.
        -   Biorąc pod uwagę szerokie opcje wykluczeń, może zasilać dynamiczny selektor produktów/kategorii/itp.

### 4.5 Arkusze Stylów CSS (`views/css/`)

-   `newslettervoucher/css.css`
    -   **Zakres:** Może to być Front-office lub Back-office, ale bardziej prawdopodobne, że Back-office do stylizacji stron konfiguracji modułu i widoków list administracyjnych.
    -   **Opis:** Zawiera ogólne reguły stylizacji dla elementów modułu, zapewniając ich wizualną integrację z motywem Panelu administracyjnego PrestaShop.
-   `newslettervoucher/lib/voucherengine/ps16.css`
    -   **Zakres:** Panel administracyjny.
    -   **Opis:** Ten arkusz stylów jest specjalnie przeznaczony do stylizacji Panelu administracyjnego PrestaShop 1.6. Zawierałby reguły zapewniające, że interfejs administracyjny modułu wygląda poprawnie i spójnie w motywie PS 1.6, potencjalnie nadpisując lub dostosowując domyślne style PS 1.6 dla elementów specyficznych dla modułu. Dla PS 1.7+ i 8.x te style mogą być ignorowane lub wymagać dostosowań dla pełnej kompatybilności.

### 4.6 Struktura Szablonów Smarty (`views/templates/`)

Spis nie wskazuje na żadne pliki `.tpl`. Sugeruje to, że:

-   Główny formularz konfiguracji modułu jest renderowany bezpośrednio w metodzie `getContent()` głównego pliku modułu za pomocą `HelperForm` PrestaShop lub podobnego.
-   Widoki kontrolera administracyjnego (`AdminNewsletterVoucherVouchers`) są renderowane za pomocą klas `HelperList` i `HelperForm` PrestaShop, które generują HTML bezpośrednio bez potrzeby niestandardowych plików `.tpl` dla podstawowych wyświetleń list i formularzy.
-   Integracja front-office jest czysto programistyczna, wstrzykując kody kuponów do istniejących szablonów e-mail lub za pomocą hooków bez dedykowanych szablonów modułu.

Gdyby istniały niestandardowe szablony, zazwyczaj znajdowałyby się w:

-   `views/templates/admin/`: Dla niestandardowych formularzy lub pulpitów nawigacyjnych Panelu administracyjnego.
-   `views/templates/hook/`: Dla treści renderowanych w konkretnych hookach PrestaShop.
-   `views/templates/front/`: Dla wszelkich dedykowanych stron front-office lub złożonych widżetów.

### 4.7 Schemat Bazy Danych i Mapa Hooków

#### Tabele Bazy Danych

-   `ps_nvoucher` (Prawdopodobnie, na podstawie `AdminNewsletterVoucherVouchers` zarządzającego encją `nvoucher`)
    -   `id_nvoucher` (Klucz Główny, INT)
    -   `id_customer` (INT, Klucz Obcy do `ps_customer`)
    -   `voucher_code` (VARCHAR, przechowuje unikalny kod `CartRule`)
    -   `date_add` (DATETIME, znacznik czasu generacji kuponu)
    -   `id_cart_rule` (INT, Klucz Obcy do `ps_cart_rule`, łączący z rzeczywistym kuponem PrestaShop)
    -   Mogą istnieć inne pola do śledzenia użycia, wygaśnięcia itp.
-   **Rekordy Konfiguracji (w tabeli `ps_configuration`):**
    -   `NEWSLETTERVOUCHER_VALUE` (Kwota/procent kuponu)
    -   `NEWSLETTERVOUCHER_MIN_AMOUNT` (Minimalna kwota zamówienia)
    -   `NEWSLETTERVOUCHER_VALIDITY` (Ważność kuponu w dniach)
    -   `NEWSLETTERVOUCHER_DESCRIPTION` (Opis kuponu)
    -   `NEWSLETTERVOUCHER_PREFIX` (Prefiks kodu kuponu)
    -   `NEWSLETTERVOUCHER_EXCLUDE_CATEGORIES` (Serializowana tablica wykluczonych kategorii)
    -   … i podobne klucze `NEWSLETTERVOUCHER_EXCLUDE_...` dla wszystkich ustawień wykluczeń.

#### Tabela Zarejestrowanych Hooków

| Nazwa Hooka | Czas Wykonania | Cel Techniczny |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Po utworzeniu nowego konta klienta. | Może być użyty do wyzwolenia generowania kuponu po rejestracji nowego konta, jeśli jest powiązany z zapisem do newslettera. |
| `actionNewsletterSubscriptionAdd` | Po zapisaniu nowego adresu e-mail do newslettera. | **KRYTYCZNY HOOK:** Jest to główny hook, w którym moduł przechwytywałby nową subskrypcję newslettera, generował unikalny `CartRule` i wysyłał go do subskrybenta. |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Potencjalnie do ładowania zasobów JS/CSS lub meta tagów, choć mniej prawdopodobne dla podstawowej funkcjonalności. |
| `displayLeftColumn` | W lewej kolumnie stron front-office. | Jeśli moduł miałby blok front-office (np. przypomnienie o kuponie). |
| `displayRightColumn` | W prawej kolumnie stron front-office. | Tak samo jak `displayLeftColumn`. |
| `displayFooter` | W stopce każdej strony front-office. | Tak samo jak `displayLeftColumn`, często tam, gdzie znajdują się formularze newslettera. |
| `displayProductAdditionalInfo` | Na stronach produktów, poniżej głównych informacji o produkcie. | Mniej prawdopodobne dla tego modułu, ale może być użyte do wyświetlenia komunikatu „Zapisz się do newslettera, otrzymaj kupon”. |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony Panelu administracyjnego. | Do ładowania zasobów JS/CSS specyficznych dla Panelu administracyjnego dla stron administracyjnych modułu. |
| `displayAdminProductsExtra` | Na stronie edycji produktu w Panelu administracyjnym. | Mniej prawdopodobne, ale może być użyte do dodania zakładki specyficznej dla modułu lub informacji związanych z wykluczeniami produktów. |
| `moduleRoutes` | Gdy PrestaShop buduje swoją tabelę routingu. | Do definiowania niestandardowych przyjaznych adresów URL dla swoich kontrolerów front-office (np. `/module/newslettervoucher/cronjob`). |

## 5. Oficjalne Wsparcie i Aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i najnowszych wersji modułu „Unikalny kupon za zapis do newslettera” prosimy odwołać się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
