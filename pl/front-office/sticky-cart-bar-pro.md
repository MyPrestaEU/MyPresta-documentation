---
title: "Sticky Cart Bar PRO - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop Sticky Cart Bar PRO od MyPresta.eu."
sidebar:
  label: "Sticky Cart Bar PRO - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Sticky Cart Bar PRO na MyPresta.eu](https://mypresta.eu/modules/front-office-features/sticky-cart-bar-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/sticky-cart-bar-pro/)
>
> ---


# Sticky Cart Bar PRO

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł Sticky Cart Bar PRO oferuje potężny zestaw opcji konfiguracyjnych, podzielonych na kilka kluczowych obszarów do zarządzania paskami i testami A/B.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po pierwszym kliknięciu „Konfiguruj” modułu, trafisz na pulpit nawigacyjny, który zapewnia przegląd i dostęp do głównych sekcji. Ta strona działa jako centralny hub.

Główna strona konfiguracji Sticky Cart Bar PRO jest zbudowana z zakładek lub sekcji do zarządzania różnymi aspektami modułu.

#### Ustawienia ogólne / Przegląd pulpitu nawigacyjnego

Ta sekcja zazwyczaj przedstawia podsumowanie aktywnych pasków, testów A/B i szybkie linki do głównych ekranów zarządzania.

-   **Co robi ta sekcja:** Zapewnia ogólny przegląd statusu modułu i szybką nawigację do tworzenia nowych pasków, zarządzania istniejącymi lub konfigurowania testów A/B.
-   **Wpływ zmiany tego ustawienia:** Jest to przede wszystkim ekran nawigacyjny i informacyjny. Zmiany tutaj polegają na klikaniu linków do innych dedykowanych ekranów zarządzania.
-   **Zalecana wartość:** Regularnie przeglądaj ten pulpit nawigacyjny, aby monitorować swoje paski i eksperymenty.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł zawiera dedykowane kontrolery administracyjne do zarządzania paskami i testami A/B, oferując kompleksowy interfejs do projektowania, targetowania i analizy.

#### 2.2.1 Zarządzanie paskami Sticky Cart (Panel administracyjny > Moduły > Sticky Cart Bar PRO > **Zarządzaj paskami**)

Ten ekran służy do tworzenia, edytowania i zarządzania wszystkimi paskami sticky cart.

-   **Nazwa ekranu i lokalizacja w menu:** Znajdziesz to w **Moduły > Sticky Cart Bar PRO > Zarządzaj paskami** (lub podobny wpis w menu bezpośrednio w konfiguracji modułu).
-   **Dostępne akcje i ustawienia:**
    -   **Tabela z listą pasków:** Wyświetla wszystkie utworzone paski sticky z kluczowymi informacjami, takimi jak nazwa, status (aktywny/nieaktywny) i przypisane eksperymenty.
        -   *Efekt:* Zapewnia uporządkowany widok wszystkich pasków sticky.
        -   *Zalecane:* Utrzymuj opisowe nazwy pasków dla łatwej identyfikacji.
    -   **Przycisk Dodaj nowy pasek:** Rozpoczyna proces tworzenia nowego paska sticky.
        -   *Efekt:* Otwiera „Layout Studio”, gdzie projektujesz swój pasek.
        -   *Zalecane:* Rozpocznij z jasnym celem dla nowego paska (np. „Dolny pasek strony produktu - Darmowa wysyłka”).
    -   **Przycisk Edytuj (dla istniejących pasków):** Umożliwia modyfikację istniejącego paska sticky.
        -   *Efekt:* Ponownie otwiera Layout Studio z aktualnymi ustawieniami paska.
        -   *Zalecane:* Regularnie przeglądaj i aktualizuj paski na podstawie wydajności lub promocji.
    -   **Przycisk Duplikuj:** Tworzy dokładną kopię istniejącego paska.
        -   *Efekt:* Oszczędza czas podczas tworzenia podobnych pasków lub wariantów do testów A/B.
        -   *Zalecane:* Użyj tego, aby szybko stworzyć nowy pasek na podstawie udanego projektu, a następnie wprowadź drobne poprawki.
    -   **Przełącz status (Aktywny/Nieaktywny):** Przełącznik do włączania lub wyłączania paska bez jego usuwania.
        -   *Efekt:* Aktywny pasek pojawi się w Twoim front office zgodnie z jego regułami targetowania; nieaktywny pasek nie.
        -   *Zalecane:* Wyłącz paski, które są sezonowe lub nieistotne, zamiast je usuwać, na wypadek gdybyś ich ponownie potrzebował.
    -   **Przycisk Usuń:** Trwale usuwa pasek sticky.
        -   *Efekt:* Pasek nie będzie już wyświetlany w Twoim sklepie.
        -   *Zalecane:* Usuwaj tylko paski, których na pewno nigdy więcej nie użyjesz.
    -   **Layout Studio (podczas dodawania/edycji paska):** To jest główny interfejs projektowy.
        -   **Edytor przeciągnij i upuść:** Pozwala wizualnie budować pasek sticky poprzez dodawanie i układanie elementów.
            -   *Efekt:* Możesz dostosować układ, zawartość i wygląd paska bez kodowania.
            -   *Zalecane:* Eksperymentuj z różnymi kombinacjami elementów, aby znaleźć to, co najlepiej pasuje do Twoich produktów i odbiorców.
        -   **Opcje elementów:** Każdy element (np. „Przycisk Dodaj do koszyka”, „Obraz produktu”, „Licznik czasu”, „Niestandardowy tekst”) ma własne ustawienia dotyczące stylu, zawartości i zachowania.
            -   *Efekt:* Dostosuj wygląd i funkcjonalność każdej części paska.
            -   *Zalecane:* Zwróć uwagę na kolory, czcionki i rozmiary, aby pasowały do brandingu Twojego sklepu.
        -   **Presety:** Wybierz z biblioteki gotowych układów pasków sticky.
            -   *Efekt:* Szybko rozpocznij pracę z profesjonalnie wyglądającym paskiem.
            -   *Zalecane:* Użyj presetów jako punktu wyjścia, a następnie dostosuj je do swoich konkretnych potrzeb.
        -   **Reguły targetowania:** Zdefiniuj *gdzie* i *komu* pasek sticky ma być wyświetlany.
            -   *Efekt:* Zapewnia, że pasek jest wyświetlany tylko odpowiednim klientom na określonych stronach.
            -   *Zalecane:* Targetuj konkretne kategorie produktów, marki lub grupy klientów, aby uzyskać maksymalny efekt. Przykłady:
                -   *Wyświetl na:* Wszystkich stronach produktów, konkretnych identyfikatorach produktów, konkretnych kategoriach.
                -   *Grupach klientów:* Tylko zalogowani klienci, nowi odwiedzający, konkretne grupy klientów.
                -   *Lokalizacji geograficznej:* Tylko klienci z określonych krajów.
                -   *Typie urządzenia:* Komputer stacjonarny, mobilny lub oba.
        -   **Pozycja wyświetlania:** Wybierz, czy pasek ma pojawić się na górze, czy na dole ekranu.
            -   *Efekt:* Kontroluje wizualne umiejscowienie paska sticky.
            -   *Zalecane:* Paski dolne są często mniej inwazyjne, podczas gdy paski górne mogą być bardziej widoczne. Przetestuj oba!
        -   **Ustawienia widoczności:** Kontroluj, kiedy pasek się pojawia (np. po przewinięciu na określoną odległość, po opóźnieniu).
            -   *Efekt:* Zapobiega zbyt wczesnemu lub zbyt późnemu pojawianiu się paska, optymalizując doświadczenie użytkownika.
            -   *Zalecane:* Niewielkie opóźnienie lub próg przewijania może sprawić, że pasek będzie mniej agresywny.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Planuj:** Zdecyduj o celu nowego paska sticky (np. promowanie konkretnego produktu, oferowanie darmowej wysyłki, zmniejszenie porzuceń koszyka).
    2.  **Twórz:** Użyj przycisku „Dodaj nowy pasek” i Layout Studio, aby zaprojektować swój pasek. Zacznij od presetu, jeśli nie jesteś pewien.
    3.  **Targetuj:** Ostrożnie ustaw reguły targetowania, aby upewnić się, że pasek pojawia się dla właściwej grupy odbiorców na właściwych stronach.
    4.  **Aktywuj:** Ustaw pasek na „Aktywny”, gdy będziesz zadowolony z jego projektu i targetowania.
    5.  **Monitoruj:** Użyj pulpitu nawigacyjnego analityki (patrz następna sekcja), aby śledzić jego wydajność.
    6.  **Optymalizuj:** Na podstawie analityki edytuj pasek, aby poprawić jego skuteczność.

#### 2.2.2 Zarządzanie testami A/B (Panel administracyjny > Moduły > Sticky Cart Bar PRO > **Testy A/B**)

Ten ekran umożliwia konfigurowanie i zarządzanie testami A/B dla pasków sticky, porównując różne wersje, aby zobaczyć, która działa najlepiej.

-   **Nazwa ekranu i lokalizacja w menu:** Znajdziesz to w **Moduły > Sticky Cart Bar PRO > Testy A/B**.
-   **Dostępne akcje i ustawienia:**
    -   **Tabela z listą eksperymentów:** Pokazuje wszystkie aktywne i zakończone testy A/B, w tym ich status, daty rozpoczęcia/zakończenia i metryki wydajności.
        -   *Efekt:* Zapewnia przegląd Twoich działań testowych.
        -   *Zalecane:* Regularnie sprawdzaj status swoich eksperymentów.
    -   **Przycisk Dodaj nowy eksperyment:** Rozpoczyna proces tworzenia nowego testu A/B.
        -   *Efekt:* Prowadzi Cię przez wybór paska kontrolnego i jednego lub więcej pasków wariantowych.
        -   *Zalecane:* Miej przygotowane co najmniej dwa paski sticky (jeden kontrolny, jeden wariantowy) przed rozpoczęciem eksperymentu.
    -   **Konfiguracja eksperymentu (podczas dodawania/edycji):**
        -   **Nazwa:** Opisowa nazwa dla Twojego testu A/B.
            -   *Efekt:* Pomaga zidentyfikować eksperyment później.
            -   *Zalecane:* Używaj nazw takich jak „Dolny pasek strony produktu - Test koloru przycisku” lub „Pasek górny vs. pasek dolny”.
        -   **Pasek kontrolny:** Oryginalny lub domyślny pasek sticky, który chcesz przetestować.
            -   *Efekt:* To jest Twoja linia bazowa do porównania.
            -   *Zalecane:* Wybierz swój aktualnie najlepiej działający pasek lub standardowy projekt.
        -   **Paski wariantowe:** Jeden lub więcej alternatywnych pasków sticky, które chcesz przetestować.
            -   *Efekt:* To są wersje ze zmianami, które Twoim zdaniem mogą poprawić wydajność.
            -   *Zalecane:* Skup się na testowaniu jednej głównej zmiany na wariant (np. inny kolor przycisku, inna wiadomość, inna pozycja).
        -   **Rozkład ruchu:** Zdefiniuj, jaki procent Twojej publiczności widzi każdy pasek (kontrolny vs. warianty).
            -   *Efekt:* Zapewnia uczciwe porównanie poprzez równomierne lub pożądane rozłożenie ruchu.
            -   *Zalecane:* Zacznij od równego rozkładu (np. 50/50 dla dwóch pasków, 33/33/33 dla trzech).
        -   **Cel:** Zdefiniuj metrykę, którą chcesz zoptymalizować (np. kliknięcia „Dodaj do koszyka”, współczynnik konwersji, przychody).
            -   *Efekt:* Moduł będzie śledził tę metrykę dla każdego paska.
            -   *Zalecane:* Wybierz jasny, mierzalny cel bezpośrednio związany z Twoim celem biznesowym.
        -   **Reguły targetowania:** Podobnie jak targetowanie pasków, ale dla samego eksperymentu. Zapewnia, że test A/B działa tylko dla określonych segmentów.
            -   *Efekt:* Pozwala na przeprowadzanie ukierunkowanych eksperymentów bez wpływu na całą publiczność.
            -   *Zalecane:* Jeśli testujesz pasek dla konkretnej kategorii, zastosuj to samo targetowanie do eksperymentu.
    -   **Przycisk Wyświetl analitykę:** Dostęp do szczegółowych danych wydajności dla konkretnego eksperymentu.
        -   *Efekt:* Pokazuje, który pasek działał najlepiej na podstawie zdefiniowanego celu.
        -   *Zalecane:* Pozwól eksperymentom działać wystarczająco długo, aby zebrać statystycznie istotne dane przed podjęciem decyzji.
    -   **Przycisk Zatrzymaj eksperyment:** Kończy aktywny test A/B.
        -   *Efekt:* Moduł przestanie wyświetlać paski wariantowe, a Ty możesz wybrać, aby zwycięski pasek stał się stały.
        *Zalecane:* Zatrzymaj eksperyment, gdy zostanie zidentyfikowany wyraźny zwycięzca lub jeśli nie przynosi on użytecznych wyników.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Hipoteza:** Zidentyfikuj obszar do poprawy (np. „Myślę, że czerwony przycisk ‘Dodaj do koszyka’ będzie działał lepiej niż zielony”).
    2.  **Utwórz warianty:** Zduplikuj istniejący pasek sticky i wprowadź konkretną zmianę, którą chcesz przetestować (np. zmień kolor przycisku).
    3.  **Skonfiguruj eksperyment:** Przejdź do ekranu Testy A/B, kliknij „Dodaj nowy eksperyment” i skonfiguruj kontrolę, warianty, ruch i cel.
    4.  **Uruchom i monitoruj:** Rozpocznij eksperyment i regularnie sprawdzaj pulpit nawigacyjny analityki pod kątem postępów.
    5.  **Analizuj i implementuj:** Po zakończeniu eksperymentu lub pojawieniu się wyraźnego zwycięzcy, zaimplementuj zwycięski pasek jako domyślny.

#### 2.2.3 Pulpit nawigacyjny analityki (Panel administracyjny > Moduły > Sticky Cart Bar PRO > **Analityka**)

Ten ekran dostarcza szczegółowych metryk wydajności dla pasków sticky i testów A/B.

-   **Nazwa ekranu i lokalizacja w menu:** Znajdziesz to w **Moduły > Sticky Cart Bar PRO > Analityka**.
-   **Dostępne akcje i ustawienia:**
    -   **Widok pulpitu nawigacyjnego:** Wyświetla wykresy i grafiki pokazujące kluczowe metryki, takie jak wyświetlenia, kliknięcia, współczynniki klikalności (CTR) i konwersje dla pasków sticky.
        -   *Efekt:* Daje jasne wizualne przedstawienie tego, jak działają Twoje paski.
        -   *Zalecane:* Użyj tych danych, aby zrozumieć, które paski są skuteczne, a które wymagają poprawy.
    -   **Opcje filtrowania:** Filtruj dane według zakresu dat, konkretnego paska sticky lub eksperymentu.
        -   *Efekt:* Pozwala zagłębić się w konkretne okresy lub porównać wydajność poszczególnych pasków.
        -   *Zalecane:* Porównaj wydajność przed i po dużej zmianie lub promocji.
    -   **Wyniki testów A/B:** Dla aktywnych lub zakończonych eksperymentów, ta sekcja wyraźnie pokaże, który wariant działa lepiej w porównaniu do kontrolnego, często ze wskaźnikami istotności statystycznej.
        -   *Efekt:* Dostarcza dowodów potrzebnych do podejmowania decyzji opartych na danych dotyczących projektów pasków sticky.
        -   *Zalecane:* Nie podejmuj decyzji na podstawie małych próbek; poczekaj na istotność statystyczną.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  **Regularny przegląd:** Sprawdzaj pulpit nawigacyjny analityki co tydzień lub co miesiąc, aby zrozumieć ogólne trendy wydajności.
    2.  **Głęboka analiza:** Jeśli pasek działa słabo, użyj filtrów, aby zbadać konkretne okresy lub porównać go z innymi paskami.
    3.  **Podejmowanie decyzji:** Użyj wyników testów A/B, aby pewnie wybrać zwycięskie projekty i wdrożyć je w całym sklepie.

#### 2.2.4 AdminStickyCartBarAbController (stickycartbarpro/controllers/admin/AdminStickyCartBarAbController.php)

Ten kontroler zarządza eksperymentami testów A/B. Obsługuje tworzenie, edytowanie, listowanie i usuwanie encji `stickycartbar_experiment`.

#### 2.2.5 AdminStickyCartBarProController (stickycartbarpro/controllers/admin/AdminStickyCartBarProController.php)

Ten kontroler zarządza poszczególnymi paskami sticky cart. Obsługuje tworzenie, edytowanie, listowanie i usuwanie encji `stickycartbar_bar`, w tym dostęp do Layout Studio do projektowania.

#### 2.2.6 index.php (stickycartbarpro/controllers/admin/index.php)

Jest to plik-zapełniacz, zazwyczaj używany do zapobiegania bezpośredniemu listowaniu katalogów i nie reprezentuje sam w sobie konfigurowalnego ekranu.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Zarządzaj paskami** | Nazwa paska | Opisowa | Identyfikuje pasek w panelu administracyjnym. |
|  | Layout Studio | N/A | Edytor przeciągnij i upuść dla zawartości i stylu paska. |
|  | Opcje elementów | Różne | Dostosowuje poszczególne elementy (przyciski, tekst, obrazy). |
|  | Presety | N/A | Szablony szybkiego startu do projektowania pasków. |
|  | Reguły targetowania | Wszystkie strony produktów | Definiuje, gdzie i komu pasek jest wyświetlany. |
|  | Pozycja wyświetlania | Dół | Kontroluje, czy pasek jest na górze, czy na dole ekranu. |
|  | Ustawienia widoczności | Po przewinięciu | Kontroluje, kiedy pasek się pojawia (opóźnienie, przewinięcie). |
|  | Status (Aktywny/Nieaktywny) | Nieaktywny (początkowo) | Włącza/wyłącza wyświetlanie paska w front office. |
| **Testy A/B** | Nazwa eksperymentu | Opisowa | Identyfikuje test A/B. |
|  | Pasek kontrolny | Istniejący pasek | Pasek bazowy do porównania. |
|  | Paski wariantowe | Nowy/Zmodyfikowany pasek(i) | Alternatywne wersje poddawane testom. |
|  | Rozkład ruchu | Równy podział | Jak publiczność jest dzielona między paski. |
|  | Cel | Kliknięcia Dodaj do koszyka | Metryka do optymalizacji (np. kliknięcia, konwersje). |
|  | Reguły targetowania | Wszystkie strony produktów | Definiuje, gdzie eksperyment jest uruchamiany. |
|  | Status (Aktywny/Zatrzymany) | Aktywny | Kontroluje, czy eksperyment jest uruchomiony. |
| **Analityka** | Filtr zakresu dat | Ostatnie 30 dni | Filtruje dane wydajności według czasu. |
|  | Filtr paska/eksperymentu | Wszystkie | Filtruje dane dla konkretnych pasków lub testów. |
|  | Wyświetlanie metryk | Wyświetlenia, kliknięcia, CTR | Pokazuje dane wydajności dla pasków/eksperymentów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Mój pasek sticky nie wyświetla się na stronach produktów. Co powinienem sprawdzić?**
**O1:**

-   **Czy pasek jest „Aktywny”?** Przejdź do **Moduły > Sticky Cart Bar PRO > Zarządzaj paskami** i upewnij się, że przełącznik dla Twojego paska jest ustawiony na „Aktywny”.
-   **Sprawdź reguły targetowania:** Edytuj swój pasek i przejrzyj „Reguły targetowania”. Upewnij się, że jest ustawiony na wyświetlanie na właściwych stronach (np. „Wszystkie strony produktów” lub konkretne kategorie/produkty) i dla właściwych grup klientów.
-   **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami pamięć podręczna PrestaShop uniemożliwia natychmiastowe pojawienie się nowych zmian modułu.
-   **Pozycja modułu:** Upewnij się, że moduł jest poprawnie podpięty. Chociaż moduł zazwyczaj sam to obsługuje, jeśli ręcznie go odpiąłeś, nie pojawi się. Sprawdź **Wygląd > Pozycje** i wyszukaj „Sticky Cart Bar PRO”, aby upewnić się, że jest podpięty do `displayHeader` lub `displayFooter` (w zależności od pozycji paska).

**P2: Pasek sticky wygląda dziwnie lub nie pasuje do projektu mojego motywu.**
**O2:**

-   **Stylizacja w Layout Studio:** Przejdź do **Moduły > Sticky Cart Bar PRO > Zarządzaj paskami**, edytuj swój pasek i użyj opcji stylizacji w Layout Studio. Możesz dostosować kolory, czcionki, rozmiary, marginesy i wiele więcej dla każdego elementu i samego paska.
-   **Konflikty z motywem:** Czasami CSS Twojego niestandardowego motywu może nadpisywać stylizację modułu. Jeśli podstawowe opcje stylizacji w Layout Studio nie rozwiązują problemu, może być konieczne, aby webmaster sprawdził CSS (patrz sekcja dla programistów).
-   **Kompatybilność modułu:** Upewnij się, że pobrałeś poprawną wersję modułu dla swojej wersji PrestaShop.

**P3: Jak mogę przetłumaczyć tekst w moim pasku sticky na inne języki?**
**O3:**

-   **Tłumaczenia modułu:** Dla statycznych tekstów w module (takich jak etykiety przycisków, jeśli nie są dostosowane), przejdź do **Lokalizacja > Tłumaczenia**. Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, wybierz „Sticky Cart Bar PRO”, a następnie język, na który chcesz przetłumaczyć.
-   **Niestandardowe elementy tekstowe:** Jeśli dodałeś niestandardowe elementy tekstowe za pomocą Layout Studio, będziesz musiał edytować pasek dla każdego języka. Podczas edycji paska powinieneś zobaczyć opcję przełączania języków dla pól tekstowych, co pozwoli Ci wprowadzać tłumaczenia bezpośrednio w Layout Studio.

**P4: Mój test A/B nie pokazuje wyraźnych wyników lub wydaje się zablokowany.**
**O4:**

-   **Czas trwania i ruch:** Testy A/B potrzebują wystarczającego czasu i ruchu, aby zebrać statystycznie istotne dane. Upewnij się, że Twój eksperyment działał wystarczająco długo (przynajmniej kilka tygodni) i otrzymał wystarczającą liczbę odwiedzających, aby wyciągnąć wnioski.
-   **Jasny cel:** Sprawdź dokładnie, czy Twój test A/B ma jasno zdefiniowany „Cel” (np. kliknięcia „Dodaj do koszyka”). Bez celu moduł nie może mierzyć sukcesu.
-   **Brak dużych zmian w sklepie:** Unikaj wprowadzania znaczących zmian w swoim sklepie (np. nowy motyw, duże promocje) podczas trwania testu A/B, ponieważ może to zniekształcić wyniki.

**P5: Czy mogę mieć jednocześnie aktywne wiele pasków sticky?**
**O5:** Tak, możesz tworzyć i aktywować wiele pasków sticky. Musisz jednak ostrożnie skonfigurować ich **Reguły targetowania**, aby uniknąć konfliktów. Na przykład, możesz mieć jeden pasek dla „Wszystkich stron produktów” na dole i inny, specyficzny pasek dla „Produktów kategorii X” na górze. Moduł będzie priorytetowo traktował paski na podstawie ich specyficzności i wewnętrznej logiki, ale najlepszą praktyką jest upewnienie się, że Twoje reguły targetowania nie nakładają się w sposób, który spowodowałby próbę wyświetlenia dwóch pasków w tej samej pozycji na tej samej stronie.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł Sticky Cart Bar PRO opiera się na solidnej architekturze PrestaShop MVC (Model-View-Controller), intensywnie wykorzystując `ObjectModel` do trwałości danych oraz `ModuleFrontController`/`AdminController` do obsługi żądań. Wykorzystuje zaawansowany system do budowania układu, testów A/B i analityki, z dedykowanymi klasami do konfiguracji, stylizacji, targetowania i rozwiązywania eksperymentów. Moduł stosuje podejście modułowe, rozdzielając odpowiedzialności na odrębne klasy dla lepszej utrzymywalności i rozszerzalności. Renderowanie front-office jest głównie oparte na hookach, z AJAX-em do dynamicznych interakcji.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `controllers/front/ajax.php`
    -   **Nazwa klasy:** `StickyCartBarProAjaxModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Obsługuje wszystkie żądania AJAX z paska sticky w front-office. Obejmuje to:
        -   Śledzenie wyświetleń i kliknięć dla analityki.
        -   Dynamiczne aktualizowanie informacji o koszyku (np. dodawanie produktów, zmiana ilości).
        -   Rozstrzyganie, który wariant paska sticky ma być wyświetlony dla testów A/B.
        -   Pobieranie danych produktów dla selektorów wariantów lub sugestii cross-sell.
        -   Zwraca odpowiedzi JSON.
-   `controllers/front/index.php`
    -   **Nazwa klasy:** `StickyCartBarProIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    -   **Odpowiedzialność:** Kontroler front-office pełniący rolę miejsca docelowego. Zazwyczaj może być używany dla domyślnej strony modułu, ale w tym module renderowanie front-office jest głównie obsługiwane za pomocą hooków i AJAX. Może służyć jako fallback lub podstawa dla przyszłych funkcji.

#### Kontrolery administracyjne Back-Office

-   `controllers/admin/AdminStickyCartBarAbController.php`
    -   **Nazwa klasy:** `AdminStickyCartBarAbController` (rozszerza `AdminController`)
    -   **Nazwa zakładki:** Testy A/B (w głównym menu modułu)
    -   **Zarządzana encja:** `StickyCartBarExperiment` (mapowana na tabelę `ps_stickycartbar_experiment`).
    -   **Odpowiedzialność:** Zarządza operacjami CRUD dla eksperymentów testów A/B. Obejmuje to:
        -   Wyświetlanie wszystkich eksperymentów w `HelperList`.
        -   Dostarczanie `HelperForm` do tworzenia i edytowania szczegółów eksperymentu (nazwa, pasek kontrolny, paski wariantowe, rozkład ruchu, cel, reguły targetowania).
        -   Obsługa aktywacji/dezaktywacji eksperymentów i przeglądania wyników.
-   `controllers/admin/AdminStickyCartBarProController.php`
    -   **Nazwa klasy:** `AdminStickyCartBarProController` (rozszerza `AdminController`)
    -   **Nazwa zakładki:** Zarządzaj paskami (w głównym menu modułu)
    -   **Zarządzana encja:** `StickyCartBarLayout` (mapowana na tabelę `ps_stickycartbar_bar`).
    -   **Odpowiedzialność:** Zarządza operacjami CRUD dla poszczególnych pasków sticky cart. Ten kontroler integruje się z „Layout Studio” do wizualnego projektowania.
        -   Wyświetlanie wszystkich pasków sticky w `HelperList`.
        -   Dostarczanie interfejsu dla Layout Studio typu „przeciągnij i upuść”, w tym konfiguracji elementów, stylizacji i reguł targetowania.
        -   Obsługa zapisywania i ładowania konfiguracji pasków, w tym struktury HTML, CSS i ustawień JavaScript.
-   `controllers/admin/index.php`
    -   **Nazwa klasy:** N/A (plik-zapełniacz)
    -   **Odpowiedzialność:** Zapobiega bezpośredniemu listowaniu katalogów ze względów bezpieczeństwa.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

-   `classes/index.php`: Plik-zapełniacz zapobiegający listowaniu katalogów.
-   `classes/ScbpCompatibility.php`: Obsługuje warstwy kompatybilności dla różnych wersji PrestaShop (np. różnice w `Context`, specyficzne metody pomocnicze).
-   `classes/StickyCartBarAdminUi.php`: Klasa narzędziowa do generowania wspólnych elementów interfejsu użytkownika lub obsługi specyficznej logiki interfejsu użytkownika w panelu administracyjnym.
-   `classes/StickyCartBarAnalytics.php`: Zarządza gromadzeniem, przechowywaniem i pobieraniem danych analitycznych dla pasków sticky i testów A/B (wyświetlenia, kliknięcia, konwersje).
-   `classes/StickyCartBarConfig.php`: Obsługuje ustawienia konfiguracyjne specyficzne dla modułu przechowywane w `ps_configuration` (np. globalne włączanie/wyłączanie modułu, ustawienia domyślne).
-   `classes/StickyCartBarElementStyles.php`: Zarządza właściwościami stylizacji i generowaniem CSS dla poszczególnych elementów w pasku sticky.
-   `classes/StickyCartBarExperiment.php`
    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `ps_stickycartbar_experiment`
    -   **Pola `$definition`:** `id_stickycartbar_experiment`, `name`, `id_control_bar`, `id_variant_bars` (JSON), `traffic_distribution` (JSON), `goal`, `targeting_rules` (JSON), `active`, `date_add`, `date_upd`.
    -   **Kluczowe metody publiczne:** Operacje CRUD, metody do pobierania pasków kontrolnych/wariantowych, obliczania wyników eksperymentów.
-   `classes/StickyCartBarExperimentMatcher.php`: Określa, czy reguły targetowania danego eksperymentu pasują do bieżącego kontekstu (klient, strona, urządzenie).
-   `classes/StickyCartBarExperimentResolver.php`: Biorąc pod uwagę zestaw aktywnych eksperymentów, określa, który pasek sticky (kontrolny lub wariantowy) powinien być wyświetlony bieżącemu odwiedzającemu na podstawie rozkładu ruchu i reguł eksperymentu.
-   `classes/StickyCartBarExperimentRule.php`: Reprezentuje pojedynczą regułę targetowania w eksperymencie.
-   `classes/StickyCartBarExperimentVariant.php`: Reprezentuje wariant paska sticky w teście A/B.
-   `classes/StickyCartBarLayout.php`
    -   **Rozszerza:** `ObjectModel`
    -   **Tabela bazy danych:** `ps_stickycartbar_bar`
    -   **Pola `$definition`:** `id_stickycartbar_bar`, `name`, `content` (JSON dla elementów, stylów, ustawień), `targeting_rules` (JSON), `position`, `active`, `date_add`, `date_upd`.
    -   **Kluczowe metody publiczne:** Operacje CRUD, metody do renderowania paska, pobierania jego elementów, stosowania stylów.
-   `classes/StickyCartBarLayoutInstances.php`: Zarządza instancjami układów pasków sticky, potencjalnie do buforowania lub dostępu w czasie rzeczywistym.
-   `classes/StickyCartBarLayoutPreset.php`: Reprezentuje pojedynczy, wstępnie zaprojektowany układ paska sticky.
-   `classes/StickyCartBarLayoutPresets.php`: Zarządza kolekcją dostępnych presetów układów.
-   `classes/StickyCartBarLayoutPresetsBuiltin.php`: Zawiera definicje dla domyślnych, wbudowanych presetów układów modułu.
-   `classes/StickyCartBarListPresenter.php`: Klasa pomocnicza do formatowania i prezentowania danych w listach administracyjnych (np. `HelperList`).
-   `classes/StickyCartBarMatcher.php`: Określa, czy reguły targetowania paska sticky (dla paska niebędącego eksperymentem) pasują do bieżącego kontekstu.
-   `classes/StickyCartBarRule.php`: Reprezentuje pojedynczą regułę targetowania dla paska sticky.
-   `classes/StickyCartBarTargeting.php`: Centralna klasa do oceny wszystkich reguł targetowania (zarówno dla pasków, jak i eksperymentów) względem bieżącego kontekstu front-office.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`: Zapewnia funkcjonalność autouzupełniania, prawdopodobnie używaną w panelu administracyjnym do wybierania produktów, kategorii lub producentów dla reguł targetowania.
-   `views/js/admin-ab-dashboard.js`: Obsługuje interaktywne elementy i wizualizację danych na pulpicie nawigacyjnym testów A/B w panelu administracyjnym.
-   `views/js/admin-analytics-dashboard.js`: Zarządza wykresami, filtrami i wyświetlaniem danych na pulpicie nawigacyjnym analityki.
-   `views/js/admin-audience-picker.js`: Obsługuje interaktywny interfejs do definiowania reguł targetowania odbiorców (np. wybieranie grup klientów, krajów).
-   `views/js/admin-element-editor.js`: Dostarcza logikę JavaScript do edytowania poszczególnych elementów w Layout Studio (np. otwieranie modalu do wprowadzania tekstu, selektory kolorów).
-   `views/js/admin-layout-builder.js`: Główny JavaScript dla Layout Studio typu „przeciągnij i upuść”, obsługujący umieszczanie, zmienianie rozmiaru i interakcję elementów.
-   `views/js/admin-layout-preview.js`: Zarządza podglądem paska sticky w czasie rzeczywistym w Layout Studio.
-   `views/js/admin-layout-studio.js`: Koordynuje wszystkie komponenty Layout Studio, łącząc funkcjonalności konstruktora, edytora i podglądu.
-   `views/js/admin.js`: Ogólny JavaScript dla stron back-office modułu, w tym globalne słuchacze zdarzeń, przesyłanie formularzy i wywołania AJAX.
-   `views/js/front.js`: Główny JavaScript front-office dla paska sticky.
    -   **Zakres:** Front-office.
    -   **Słuchacze zdarzeń:** Przewijanie (do wykrywania, kiedy pokazać/ukryć pasek), kliknięcia przycisków „Dodaj do koszyka” w pasku, kliknięcia selektorów wariantów, przesyłanie formularzy.
    -   **Manipulacja DOM:** Wstawia HTML paska sticky do DOM, aktualizuje ilości w koszyku, zmienia warianty produktów, pokazuje/ukrywa elementy (np. liczniki FOMO).
    -   **Wywołania AJAX:** Komunikuje się z `controllers/front/ajax.php` w celu śledzenia zdarzeń, aktualizowania koszyka i pobierania dynamicznej zawartości.
    -   **Zestawy SDK stron trzecich:** Brak wyraźnie wymienionych, ale potencjalnie może integrować się z platformami analitycznymi, jeśli jest skonfigurowany.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css`: Style dla narzędzia wyszukiwania autouzupełniania w panelu administracyjnym.
-   `views/css/admin-audience-picker.css`: Style dla interfejsu targetowania odbiorców w panelu administracyjnym.
-   `views/css/admin-bars-list.css`: Style dla listy pasków sticky w panelu administracyjnym.
-   `views/css/admin-config.css`: Ogólne style dla głównej strony konfiguracji modułu.
-   `views/css/admin-dashboard.css`: Style dla głównego pulpitu nawigacyjnego modułu i potencjalnie przeglądów analityki/testów A/B.
-   `views/css/admin-element-editor.css`: Style dla modalnych/panelowych edycji elementów w Layout Studio.
-   `views/css/admin-layout-builder.css`: Główne style dla interfejsu konstruktora układu typu „przeciągnij i upuść”.
-   `views/css/admin-layout-preview.css`: Style dla obszaru podglądu w czasie rzeczywistym w Layout Studio.
-   `views/css/admin-layout-studio.css`: Ogólne style dla Layout Studio, łączące wszystkie jego komponenty.
-   `views/css/admin-searchtool.css`: Specyficzne style dla narzędzia wyszukiwania używanego w panelu administracyjnym.
-   `views/css/front-classic.css`: Specyficzne style front-office dla motywu „Classic” PrestaShop.
    -   **Główne komponenty interfejsu użytkownika:** Nadpisuje lub dodaje style, aby zapewnić dobrą integrację paska sticky z domyślnymi elementami motywu Classic.
    -   **Kluczowe selektory klas CSS:** `.scbp-bar`, `.scbp-button`, `.scbp-product-info` itp., potencjalnie z nadpisaniami specyficznymi dla motywu.
-   `views/css/front-hummingbird.css`: Specyficzne style front-office dla motywu „Hummingbird” PrestaShop (PrestaShop 8.1+).
    -   **Główne komponenty interfejsu użytkownika:** Podobnie jak `front-classic.css`, ale dostosowane do struktury i projektu motywu Hummingbird.
    -   **Kluczowe selektory klas CSS:** `.scbp-bar`, `.scbp-button` itp., z dostosowaniami specyficznymi dla Hummingbird.
-   `views/css/front.css`: Ogólne style front-office dla paska sticky, stosowane do wszystkich motywów.
    -   **Główne komponenty interfejsu użytkownika:** Podstawowa stylizacja kontenera paska sticky, jego elementów (przycisków, tekstu, obrazów, liczników czasu) i pozycjonowania (stałe góra/dół).
    -   **Kluczowe selektory klas CSS:** `.scbp-bar`, `.scbp-element`, `.scbp-add-to-cart`, `.scbp-product-name`, `.scbp-price`, `.scbp-quantity-selector`, `.scbp-countdown`, `.scbp-stock-indicator`. Programiści mogą nadpisywać te klasy w niestandardowym CSS swojego motywu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `sticky-cart-bar-classic.tpl`: Renderuje pasek sticky specjalnie dla motywu Classic. Ten szablon prawdopodobnie zawiera strukturę HTML lub nazwy klas specyficzne dla motywu, aby zapewnić płynną integrację.
    -   **Hook:** `displayHeader` lub `displayFooter` (w zależności od pozycji paska i wewnętrznej logiki modułu).
    -   **Wyjście:** Główna struktura HTML dla paska sticky, w tym miejsca docelowe dla dynamicznej zawartości.
-   `sticky-cart-bar-element-inner.tpl`: Renderuje wewnętrzną zawartość pojedynczego elementu w pasku sticky. Jest to komponent wielokrotnego użytku.
    -   **Hook:** N/A (dołączany przez inne szablony).
    -   **Wyjście:** HTML dla określonego typu elementu (np. nazwa produktu, cena, pole ilości).
-   `sticky-cart-bar-element.tpl`: Renderuje pojedynczy element (np. przycisk, obraz, blok tekstowy) paska sticky, opakowując `sticky-cart-bar-element-inner.tpl` wspólnymi opakowaniami elementów.
    -   **Hook:** N/A (dołączany przez inne szablony).
    -   **Wyjście:** HTML dla pojedynczego, stylizowanego komponentu paska sticky.
-   `sticky-cart-bar-hummingbird.tpl`: Renderuje pasek sticky specjalnie dla motywu Hummingbird. Podobnie jak `sticky-cart-bar-classic.tpl`, ale dostosowany do nowszego motywu.
    -   **Hook:** `displayHeader` lub `displayFooter`.
    -   **Wyjście:** Główna struktura HTML dla paska sticky, zoptymalizowana dla Hummingbird.
-   `sticky-cart-bar-inner.tpl`: Renderuje wewnętrzną zawartość całego paska sticky, zawierającą wszystkie poszczególne elementy.
    -   **Hook:** N/A (dołączany przez `sticky-cart-bar.tpl`).
    -   **Wyjście:** Połączony HTML wszystkich skonfigurowanych elementów dla paska sticky.
-   `sticky-cart-bar.tpl`: Główny szablon odpowiedzialny za renderowanie paska sticky cart w front office. Określa, który szablon specyficzny dla motywu (classic/hummingbird) ma zostać dołączony lub używa ogólnej struktury.
    -   **Hook:** `displayHeader` lub `displayFooter` (moduł rejestruje się do tych hooków).
    -   **Wyjście:** Kompletny, wyrenderowany pasek sticky cart, w tym jego kontener, elementy i niezbędne atrybuty danych dla JavaScript.

#### Szablony administracyjne (`views/templates/admin/`)

-   `ab-test-dashboard.tpl`: Renderuje główny pulpit nawigacyjny dla testów A/B, pokazując listy eksperymentów i dane podsumowujące.
-   `ab-tests-tab.tpl`: Renderuje zawartość zakładki „Testy A/B” w konfiguracji modułu.
-   `analytics-dashboard.tpl`: Renderuje pulpit nawigacyjny analityki z wykresami i metrykami wydajności.
-   `audience-picker.tpl`: Renderuje HTML dla interfejsu wyboru targetowania odbiorców (np. selektory krajów, grup klientów).
-   `bars-tab.tpl`: Renderuje zawartość zakładki „Zarządzaj paskami”, w tym listę pasków sticky.
-   `configure.tpl`: Główny szablon konfiguracyjny dla modułu, działający jako opakowanie dla wszystkich innych szablonów administracyjnych i zakładek.
-   `country-priority-picker.tpl`: Renderuje specyficzny komponent interfejsu użytkownika do wybierania i priorytetyzowania krajów w regułach targetowania.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

-   `ps_stickycartbar_bar`: Przechowuje konfigurację dla każdego pojedynczego paska sticky cart.
    -   `id_stickycartbar_bar` (PK, INT)
    -   `name` (VARCHAR)
    -   `content` (TEXT, zakodowany w JSON: zawiera elementy, style, pozycję, ustawienia widoczności)
    -   `targeting_rules` (TEXT, zakodowany w JSON: warunki wyświetlania)
    -   `active` (TINYINT)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_stickycartbar_experiment`: Przechowuje konfigurację dla każdego eksperymentu testów A/B.
    -   `id_stickycartbar_experiment` (PK, INT)
    -   `name` (VARCHAR)
    -   `id_control_bar` (INT, FK do `ps_stickycartbar_bar`)
    -   `id_variant_bars` (TEXT, zakodowana w JSON tablica FK do `ps_stickycartbar_bar`)
    -   `traffic_distribution` (TEXT, zakodowany w JSON: procent dla każdego paska)
    -   `goal` (VARCHAR: np. ‘add\_to\_cart’, ‘conversion’)
    -   `targeting_rules` (TEXT, zakodowany w JSON)
    -   `active` (TINYINT)
    -   `date_add` (DATETIME)
    -   `date_upd` (DATETIME)
-   `ps_stickycartbar_analytics`: Przechowuje dane analityczne (wyświetlenia, kliknięcia, konwersje) dla pasków i eksperymentów.
    -   `id_stickycartbar_analytics` (PK, INT)
    -   `id_stickycartbar_bar` (INT, FK)
    -   `id_stickycartbar_experiment` (INT, FK, NULLABLE)
    -   `type` (VARCHAR: ‘impression’, ‘click’, ‘add\_to\_cart’, ‘conversion’)
    -   `id_customer` (INT, NULLABLE)
    -   `id_guest` (INT, NULLABLE)
    -   `date_add` (DATETIME)
-   **`ps_configuration`**: Przechowuje globalne ustawienia modułu (np. `STICKYCARTBARPRO_ENABLED`, `STICKYCARTBARPRO_ANALYTICS_ENABLED`).

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykuje pliki CSS i JavaScript dla paska sticky, a potencjalnie początkową strukturę HTML, jeśli pasek jest umieszczony na górze. |
| `displayFooter` | Przed zamykającym tagiem `</body>` na każdej stronie. | Wstrzykuje strukturę HTML dla pasków sticky umieszczonych na dole oraz wszelkie niezbędne inicjalizacje JavaScript. |
| `actionFrontControllerSetMedia` | Po ustawieniu zasobów multimedialnych przez kontroler front-office. | Pozwala modułowi warunkowo dodawać swoje JS/CSS na podstawie bieżącego kontekstu strony (np. tylko na stronach produktów). |
| `actionProductUpdate` | Po zaktualizowaniu produktu w panelu administracyjnym. | Potencjalnie używane do czyszczenia pamięci podręcznej związanej z danymi produktu, które mogą być wyświetlane w paskach sticky. |
| `actionObjectProductAddAfter` | Po dodaniu nowego produktu. | Podobnie jak `actionProductUpdate`. |
| `actionObjectProductUpdateAfter` | Po zaktualizowaniu istniejącego produktu. | Podobnie jak `actionProductUpdate`. |
| `actionObjectProductDeleteAfter` | Po usunięciu produktu. | Potencjalnie używane do usuwania wszelkich odniesień do usuniętego produktu w konfiguracjach pasków sticky. |
| `actionCartSave` | Po zapisaniu lub zaktualizowaniu koszyka. | Używane do śledzenia zdarzeń „Dodaj do koszyka” dla analityki i celów testów A/B. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Używane do śledzenia zdarzeń konwersji dla analityki i celów testów A/B. |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony panelu administracyjnego. | Wstrzykuje CSS i JavaScript dla interfejsów administracyjnych modułu (Layout Studio, pulpity nawigacyjne). |
| `moduleRoutes` | Podczas inicjalizacji routingu URL. | Rejestruje niestandardowe trasy front-office dla kontrolerów AJAX, jeśli jest to potrzebne. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu Sticky Cart Bar PRO, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
"""
