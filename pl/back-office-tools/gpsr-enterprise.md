---
title: "GPSR Enterprise - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop GPSR Enterprise od MyPresta.eu."
sidebar:
  label: "GPSR Enterprise"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł GPSR Enterprise na MyPresta.eu](https://mypresta.eu/modules/administration-tools/gpsr-enterprise.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/gpsr-enterprise/)
>
> ---


# GPSR Enterprise

## 1. Wymagania i kompatybilność

*   **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
*   **Kompatybilność z PHP**: PHP 7.1 - 8.5
*   **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości nowoczesnych środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

Moduł GPSR Enterprise oferuje kompleksowy zestaw opcji konfiguracyjnych, rozmieszczonych na głównej stronie konfiguracji i kilku dedykowanych ekranach administracyjnych.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Menedżer modułów > GPSR Enterprise > Konfiguruj)

Jest to główny ekran konfiguracji modułu, na którym kontrolujesz jego ogólne zachowanie i wyświetlanie w front-office.

*   **Moduł włączony**
    *   **Co robi to ustawienie:** Jest to główny przełącznik dla całego modułu GPSR Enterprise.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączony (Tak):* Moduł będzie aktywny, wyświetlając informacje GPSR na stronach produktów, umożliwiając zarządzanie podmiotami, ostrzeżeniami i mapowaniami, a także włączając API i zadania cron.
        *   *Gdy wyłączony (Nie):* Moduł będzie całkowicie nieaktywny. Żadne informacje GPSR nie będą wyświetlane w front-office, a funkcje zarządzania w backendzie będą niedostępne lub niefunkcjonalne.
    *   **Zalecana wartość:** **Tak** (aby korzystać z funkcji modułu).
    *   **Scenariusz / przykład sprzedawcy:** Jeśli konfigurujesz moduł po raz pierwszy, pozostaw go wyłączonym, dopóki wszystkie konfiguracje nie zostaną zakończone, a następnie włącz go, aby uruchomić.

*   **Profil szablonu sklepu**
    *   **Co robi to ustawienie:** Pozwala wybrać profil stylu wizualnego dla bloku informacyjnego GPSR na stronach produktów, zoptymalizowany dla różnych szablonów PrestaShop.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy ustawiony na 'Classic':* Moduł będzie używał stylizacji zoptymalizowanej dla domyślnego szablonu PrestaShop Classic (i wielu kompatybilnych szablonów).
        *   *Gdy ustawiony na 'Hummingbird':* Moduł będzie używał stylizacji zoptymalizowanej dla nowszego szablonu PrestaShop Hummingbird (PrestaShop 8.1+).
    *   **Zalecana wartość:** Wybierz profil, który najlepiej pasuje do Twojego obecnego szablonu PrestaShop. Jeśli nie jesteś pewien, spróbuj najpierw 'Classic'.
    *   **Scenariusz / przykład sprzedawcy:** Jeśli Twój sklep używa PrestaShop 8.1+ z domyślnym szablonem, wybierz 'Hummingbird' dla najlepszej integracji wizualnej. Jeśli używasz PrestaShop 1.7 lub 8.0 z szablonem Classic, wybierz 'Classic'.

*   **Tryb wyświetlania**
    *   **Co robi to ustawienie:** Kontroluje sposób prezentacji bloku informacyjnego GPSR na stronie produktu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Opcje różnią się (np. 'Zakładka', 'Akordeon', 'Blok'):*
            *   **Zakładka:** Informacje GPSR pojawią się jako nowa zakładka obok „Opis”, „Szczegóły produktu” itp.
            *   **Akordeon:** Informacje zostaną przedstawione w rozwijanej/zwijanej sekcji akordeonu.
            *   **Blok:** Informacje zostaną wyświetlone jako statyczny blok w przepływie treści strony produktu.
    *   **Zalecana wartość:** **Zakładka** lub **Akordeon** dla czystszego układu strony produktu, zwłaszcza jeśli masz dużo informacji.
    *   **Scenariusz / przykład sprzedawcy:** Jeśli Twoje strony produktów są już bardzo długie, użycie trybu „Zakładka” lub „Akordeon” utrzymuje porządek na stronie, jednocześnie czyniąc informacje dostępnymi.

*   **Styl wizualny**
    *   **Co robi to ustawienie:** Definiuje ogólną estetykę bloku informacyjnego GPSR.
    *   **Efekt zmiany tego ustawienia:**
        *   *Opcje różnią się (np. 'Domyślny', 'Minimalny', 'Szczegółowy'):* Zmieni to gęstość wizualną, użycie ikon i ogólną prezentację informacji.
    *   **Zalecana wartość:** **Domyślny** lub **Minimalny** dla czystego wyglądu. Eksperymentuj, aby zobaczyć, co najlepiej pasuje do Twojego szablonu.
    *   **Scenariusz / przykład sprzedawcy:** Jeśli Twój szablon jest bardzo minimalistyczny, wybranie „Minimalnego” stylu wizualnego dla bloku GPSR zapewni lepszą integrację.

*   **Pokaż tytuł bloku**
    *   **Co robi to ustawienie:** Określa, czy tytuł jest wyświetlany nad blokiem informacyjnym GPSR na stronie produktu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączony (Tak):* Tekst określony w „Tekst tytułu bloku” pojawi się jako nagłówek.
        *   *Gdy wyłączony (Nie):* Tytuł nie zostanie wyświetlony, co sprawi, że blok będzie bardziej płynnie się wtapiał lub polegał na kontekście.
    *   **Zalecana wartość:** **Tak** dla jasności, aby klienci od razu rozumieli, co zawiera blok.
    *   **Scenariusz / przykład sprzedawcy:** Włączenie tego z tytułem takim jak „Informacje o bezpieczeństwie produktu” jasno komunikuje klientom, co oglądają.

*   **Tekst tytułu bloku**
    *   **Co robi to ustawienie:** Pozwala dostosować tytuł bloku informacyjnego GPSR. To ustawienie ma zastosowanie tylko wtedy, gdy „Pokaż tytuł bloku” jest włączone.
    *   **Efekt zmiany tego ustawienia:** Wprowadzony tutaj tekst zostanie wyświetlony jako nagłówek bloku informacyjnego GPSR na stronie produktu.
    *   **Zalecana wartość:** Jasny, opisowy tytuł, taki jak „Bezpieczeństwo i zgodność produktu”, „Informacje o bezpieczeństwie UE” lub „Szczegóły paszportu produktu”.
    *   **Scenariusz / przykład sprzedawcy:** Możesz ustawić to na „Informacje o bezpieczeństwie produktu UE”, aby jasno komunikować cel bloku swoim europejskim klientom.

*   **Ukryj blok, gdy dane są niekompletne**
    *   **Co robi to ustawienie:** Kontroluje, czy blok informacyjny GPSR jest wyświetlany na stronie produktu, jeśli nie wszystkie wymagane dane (producent, osoba odpowiedzialna w UE, ostrzeżenia, dokumenty) zostały w pełni skonfigurowane dla tego produktu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączony (Tak):* Jeśli brakuje jakichkolwiek danych GPSR dla produktu, cały blok nie zostanie wyświetlony w front-office. Zapobiega to wyświetlaniu niekompletnych lub wprowadzających w błąd informacji.
        *   *Gdy wyłączony (Nie):* Blok będzie zawsze wyświetlany, nawet jeśli niektóre sekcje są puste. Może to pokazać częściowo wypełniony blok, co może być mylące.
    *   **Zalecana wartość:** **Tak**, aby zachować profesjonalny wygląd i uniknąć wyświetlania półpustych sekcji.
    *   **Scenariusz / przykład sprzedawcy:** Nadal dodajesz dane GPSR do wszystkich swoich produktów. Włączenie tej opcji zapewnia, że tylko w pełni zgodne strony produktów wyświetlają blok, zapobiegając dezorientacji klientów w przypadku produktów, które są nadal aktualizowane.

*   **Pokaż podmiot producenta**
    *   **Co robi to ustawienie:** Określa, czy szczegóły podmiotu GPSR producenta są wyświetlane w bloku front-office.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączony (Tak):* Nazwa producenta, adres i inne skonfigurowane szczegóły będą widoczne.
        *   *Gdy wyłączony (Nie):* Sekcja producenta zostanie ukryta.
    *   **Zalecana wartość:** **Tak**, ponieważ jest to podstawowy wymóg GPSR.
    *   **Scenariusz / przykład sprzedawcy:** Aby w pełni przestrzegać GPSR, musisz pokazać szczegóły producenta. Pozostaw to włączone.

*   **Pokaż osobę odpowiedzialną w UE**
    *   **Co robi to ustawienie:** Określa, czy szczegóły podmiotu GPSR osoby odpowiedzialnej w UE są wyświetlane w bloku front-office.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączony (Tak):* Nazwa, adres i inne skonfigurowane szczegóły osoby odpowiedzialnej w UE będą widoczne.
        *   *Gdy wyłączony (Nie):* Sekcja osoby odpowiedzialnej w UE zostanie ukryta.
    *   **Zalecana wartość:** **Tak**, ponieważ jest to podstawowy wymóg GPSR dla produktów sprzedawanych w UE.
    *   **Scenariusz / przykład sprzedawcy:** Jeśli Twoje produkty wymagają osoby odpowiedzialnej w UE, włączenie tej opcji zapewnia wyświetlanie jej danych.

*   **Pokaż ostrzeżenia dotyczące bezpieczeństwa**
    *   **Co robi to ustawienie:** Określa, czy wszelkie powiązane ostrzeżenia dotyczące bezpieczeństwa są wyświetlane w bloku front-office.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączony (Tak):* Skonfigurowane ostrzeżenia dotyczące bezpieczeństwa dla produktu będą widoczne.
        *   *Gdy wyłączony (Nie):* Sekcja ostrzeżeń dotyczących bezpieczeństwa zostanie ukryta.
    *   **Zalecana wartość:** **Tak**, aby informować klientów o potencjalnych zagrożeniach.
    *   **Scenariusz / przykład sprzedawcy:** W przypadku produktów ze specyficznymi instrukcjami bezpieczeństwa (np. „Przechowywać poza zasięgiem dzieci”), włączenie tej opcji zapewnia, że te ostrzeżenia są wyraźnie wyświetlane.

*   **Pokaż powiązane dokumenty**
    *   **Co robi to ustawienie:** Określa, czy linki do powiązanych dokumentów (takich jak instrukcje, deklaracje) są wyświetlane w bloku front-office.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączony (Tak):* Linki do przesłanych dokumentów będą widoczne.
        *   *Gdy wyłączony (Nie):* Sekcja powiązanych dokumentów zostanie ukryta.
    *   **Zalecana wartość:** **Tak**, aby zapewnić klientom dostęp do niezbędnej dokumentacji produktu.
    *   **Scenariusz / przykład sprzedawcy:** Jeśli musisz dostarczyć „Deklarację zgodności” lub szczegółową instrukcję obsługi, włączenie tej opcji umożliwia klientom łatwy dostęp do tych plików.

*   **Pokaż przycisk paszportu produktu**
    *   **Co robi to ustawienie:** Kontroluje widoczność przycisku „Pobierz paszport produktu” na stronie produktu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączony (Tak):* Pojawi się przycisk, umożliwiający klientom pobranie pliku PDF zawierającego wszystkie informacje GPSR dla produktu.
        *   *Gdy wyłączony (Nie):* Przycisk nie zostanie wyświetlony.
    *   **Zalecana wartość:** **Tak**, ponieważ paszport produktu jest kluczową funkcją GPSR.
    *   **Scenariusz / przykład sprzedawcy:** Aby zaoferować klientom kompleksowe, możliwe do pobrania podsumowanie wszystkich informacji dotyczących bezpieczeństwa i zgodności, pozostaw to włączone.

*   **Udostępniaj mapowania we wszystkich sklepach**
    *   **Co robi to ustawienie:** (Widoczne tylko w konfiguracji wielosklepowej) Określa, czy mapowania GPSR (sposób przypisywania podmiotów, ostrzeżeń i dokumentów do produktów, kategorii lub producentów) są udostępniane we wszystkich Twoich sklepach PrestaShop.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy włączony (Tak):* Wszystkie utworzone mapowania GPSR będą miały zastosowanie do wszystkich sklepów w Twoim środowisku wielosklepowym. Upraszcza to zarządzanie, jeśli Twój katalog produktów i potrzeby zgodności są podobne we wszystkich sklepach.
        *   *Gdy wyłączony (Nie):* Każdy sklep będzie miał swój własny, niezależny zestaw mapowań GPSR, co pozwala na konfiguracje zgodności specyficzne dla sklepu.
    *   **Zalecana wartość:** **Tak**, jeśli Twoje potrzeby zgodności są spójne we wszystkich sklepach; w przeciwnym razie **Nie**.
    *   **Scenariusz / przykład sprzedawcy:** Jeśli prowadzisz wiele sklepów specyficznych dla krajów, ale sprzedajesz te same produkty z tymi samymi wymaganiami zgodności, włączenie tej opcji oszczędza dużo czasu, zarządzając mapowaniami tylko raz.

*   **Akcja przy włączaniu udostępniania**
    *   **Co robi to ustawienie:** (Widoczne tylko w konfiguracji wielosklepowej, pojawia się, gdy „Udostępniaj mapowania we wszystkich sklepach” jest włączone) Definiuje, co dzieje się z istniejącymi mapowaniami specyficznymi dla sklepu, gdy przełączasz się na udostępnione mapowania.
    *   **Efekt zmiany tego ustawienia:**
        *   *Opcje różnią się (np. 'Scal', 'Nadpisz', 'Zachowaj bieżący sklep'):*
            *   **Scal:** Próbuje połączyć istniejące mapowania ze wszystkich sklepów w jeden wspólny zestaw.
            *   **Nadpisz:** Zastępuje wszystkie istniejące mapowania specyficzne dla sklepu mapowaniami z aktualnie aktywnego sklepu.
            *   **Zachowaj bieżący sklep:** Używa mapowań z aktualnie aktywnego sklepu jako mapowań udostępnionych, odrzucając inne.
    *   **Zalecana wartość:** Wybierz ostrożnie w oparciu o swoje dane. **Wykonaj kopię zapasową bazy danych** przed zmianą tego!
    *   **Scenariusz / przykład sprzedawcy:** Jeśli zarządzałeś danymi GPSR oddzielnie dla każdego sklepu i teraz chcesz je scentralizować, musisz zdecydować, czy chcesz połączyć wszystkie dane, czy też dane jednego sklepu powinny stać się głównymi.

*   **Akcja przy wyłączaniu udostępniania**
    *   **Co robi to ustawienie:** (Widoczne tylko w konfiguracji wielosklepowej, pojawia się, gdy „Udostępniaj mapowania we wszystkich sklepach” jest wyłączone) Definiuje, co dzieje się z udostępnionymi mapowaniami, gdy przełączasz się z powrotem na mapowania specyficzne dla sklepu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Opcje różnią się (np. 'Duplikuj do wszystkich sklepów', 'Zachowaj tylko dla bieżącego sklepu'):*
            *   **Duplikuj do wszystkich sklepów:** Bieżące udostępnione mapowania są kopiowane do każdego indywidualnego sklepu, umożliwiając ich późniejszą niezależną edycję.
            *   **Zachowaj tylko dla bieżącego sklepu:** Udostępnione mapowania są przypisywane tylko do aktualnie aktywnego sklepu, a inne sklepy rozpoczną bez mapowań GPSR.
    *   **Zalecana wartość:** Wybierz ostrożnie w oparciu o swoje dane. **Wykonaj kopię zapasową bazy danych** przed zmianą tego!
    *   **Scenariusz / przykład sprzedawcy:** Jeśli zdecydujesz się przejść z udostępnionych mapowań z powrotem na indywidualne zarządzanie sklepem, musisz zdecydować, czy udostępnione dane powinny zostać skopiowane do wszystkich sklepów jako punkt wyjścia, czy też tylko bieżący sklep powinien je zachować.

*   **Niestandardowy CSS**
    *   **Co robi to ustawienie:** Udostępnia pole tekstowe, w którym możesz dodać niestandardowe reguły CSS, aby dalej stylizować blok informacyjny GPSR w Twoim sklepie.
    *   **Efekt zmiany tego ustawienia:** Każdy prawidłowy kod CSS wprowadzony tutaj zostanie zastosowany do elementów front-office modułu GPSR, umożliwiając precyzyjne dostosowanie kolorów, czcionek, odstępów itp., aby idealnie pasowały do Twojego szablonu.
    *   **Zalecana wartość:** Pozostaw puste, chyba że masz specyficzne potrzeby stylizacyjne i znasz się na CSS.
    *   **Scenariusz / przykład sprzedawcy:** Twój szablon używa określonego odcienia niebieskiego dla nagłówków. Możesz dodać tutaj CSS, aby upewnić się, że tytuł bloku GPSR również używa tego samego niebieskiego, zachowując spójność wizualną.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł GPSR Enterprise dodaje kilka nowych pozycji menu pod głównym menu „GPSR Enterprise” w Twoim Panelu Administracyjnym PrestaShop. Te ekrany służą do zarządzania wszystkimi szczegółowymi danymi dotyczącymi zgodności.

#### 2.2.1 Pulpit GPSR Enterprise (Panel administracyjny > GPSR Enterprise > Pulpit)

Ten ekran zapewnia przegląd statusu zgodności z GPSR i szybki dostęp do kluczowych obszarów zarządzania.

*   **Dostępne akcje i ustawienia:**
    *   **Statystyki podsumowujące:** Może wyświetlać liczbę skonfigurowanych podmiotów, ostrzeżeń, zmapowanych produktów itp.
    *   **Szybkie linki:** Przyciski lub linki do bezpośredniego zarządzania podmiotami, ostrzeżeniami, mapowaniami, dokumentami itp.
    *   **Status zadania Cron:** Informacje o ostatnim uruchomieniu i wyniku zadania cron GPSR (do ponownego indeksowania lub synchronizacji danych).
    *   **Token API:** Wyświetla unikalny token API do integracji zewnętrznych.
    *   **Token Cron:** Wyświetla unikalny token zadania cron do bezpiecznego wykonania.
*   **Efekt zmian:** Ten ekran służy głównie do monitorowania i nawigacji. Zmiany tutaj (np. generowanie nowych tokenów API/Cron) bezpośrednio wpływają na bezpieczeństwo i funkcjonalność integracji zewnętrznych oraz zadań automatycznych.
*   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Okresowo sprawdzaj ten pulpit, aby monitorować status zgodności i upewnić się, że zadania cron działają poprawnie.

#### 2.2.2 Podmioty (Panel administracyjny > GPSR Enterprise > Podmioty)

Ten ekran służy do definiowania i zarządzania „podmiotami” wymaganymi przez GPSR, takimi jak producenci i osoby odpowiedzialne w UE.

*   **Dostępne akcje i ustawienia:**
    *   **Lista podmiotów:** Tabela wyświetlająca wszystkie skonfigurowane podmioty, z kolumnami dla nazwy, typu (Producent, Osoba odpowiedzialna w UE), adresu, kontaktu itp.
    *   **Dodaj nowy podmiot:** Przycisk do tworzenia nowego podmiotu.
    *   **Edytuj/Usuń:** Akcje dla każdego podmiotu na liście.
    *   **Formularz podmiotu:** Podczas dodawania/edycji znajdziesz pola dla:
        *   **Nazwa:** Oficjalna nazwa podmiotu.
        *   **Typ:** Wybierz, czy jest to Producent, czy Osoba odpowiedzialna w UE.
        *   **Adres:** Pełny adres pocztowy.
        *   **Informacje kontaktowe:** E-mail, telefon, strona internetowa.
        *   **Pola wielojęzyczne:** Niektóre pola mogą być tłumaczone na różne języki.
*   **Efekt zmian:** Tworzenie lub aktualizowanie podmiotów tutaj sprawia, że są one dostępne do wyboru podczas mapowania danych GPSR do produktów. Nieprawidłowe lub niekompletne dane podmiotu doprowadzą do niezgodności.
*   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Przed mapowaniem produktów upewnij się, że wszyscy Twoi producenci i osoby odpowiedzialne w UE są tutaj dokładnie wprowadzone. Niezwłocznie aktualizuj szczegóły, jeśli się zmienią.

#### 2.2.3 Ostrzeżenia (Panel administracyjny > GPSR Enterprise > Ostrzeżenia)

Ten ekran umożliwia definiowanie i zarządzanie różnymi ostrzeżeniami dotyczącymi bezpieczeństwa, które mogą być powiązane z Twoimi produktami.

*   **Dostępne akcje i ustawienia:**
    *   **Lista ostrzeżeń:** Tabela wyświetlająca wszystkie utworzone ostrzeżenia, z kolumnami dla tytułu, ikony i treści.
    *   **Dodaj nowe ostrzeżenie:** Przycisk do tworzenia nowego ostrzeżenia.
    *   **Edytuj/Usuń:** Akcje dla każdego ostrzeżenia na liście.
    *   **Formularz ostrzeżenia:** Podczas dodawania/edycji znajdziesz pola dla:
        *   **Tytuł:** Krótki, opisowy tytuł ostrzeżenia.
        *   **Ikona:** Opcja wyboru ikony wizualnej towarzyszącej ostrzeżeniu (np. symbol zagrożenia).
        *   **Treść:** Pełny tekst ostrzeżenia dotyczącego bezpieczeństwa (wielojęzyczny).
        *   **Waga/Typ:** (Jeśli dostępne) Kategoryzuj ostrzeżenie.
*   **Efekt zmian:** Utworzone tutaj ostrzeżenia stają się dostępne do wyboru podczas mapowania danych GPSR do produktów. Następnie pojawią się na stronie produktu w front-office.
*   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Najpierw utwórz tutaj wszystkie niezbędne ostrzeżenia dotyczące bezpieczeństwa. Upewnij się, że treść jest dokładna i zgodna z prawem dla wszystkich obsługiwanych języków.

#### 2.2.4 Dokumenty (Panel administracyjny > GPSR Enterprise > Dokumenty)

Ten ekran służy do przesyłania i zarządzania dokumentami, które muszą być powiązane z produktami, takimi jak deklaracje zgodności, instrukcje obsługi lub karty charakterystyki.

*   **Dostępne akcje i ustawienia:**
    *   **Lista dokumentów:** Tabela wyświetlająca przesłane dokumenty, z kolumnami dla nazwy, typu pliku i powiązanych produktów.
    *   **Prześlij nowy dokument:** Przycisk do przesyłania nowego pliku.
    *   **Edytuj/Usuń:** Akcje dla każdego dokumentu.
    *   **Formularz dokumentu:** Podczas przesyłania/edycji znajdziesz pola dla:
        *   **Nazwa:** Opisowa nazwa dokumentu (wielojęzyczna).
        *   **Przesyłanie pliku:** Rzeczywisty plik (np. PDF).
        *   **Typ:** (Jeśli dostępne) Kategoryzuj dokument (np. „Instrukcja”, „Deklaracja”).
*   **Efekt zmian:** Przesłane dokumenty stają się dostępne do wyboru podczas mapowania danych GPSR do produktów. Linki do tych dokumentów pojawią się na stronie produktu w front-office.
*   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Prześlij tutaj całą odpowiednią dokumentację produktu. Upewnij się, że dokumenty są aktualne i poprawnie nazwane dla łatwej identyfikacji.

#### 2.2.5 Mapowania (Panel administracyjny > GPSR Enterprise > Mapowania)

Jest to rdzeń automatyzacji modułu, umożliwiający definiowanie sposobu przypisywania danych GPSR do produktów na podstawie różnych kryteriów. Ta sekcja prawdopodobnie zawiera kilka podsekcji dla różnych typów mapowań.

*   **Dostępne akcje i ustawienia:**
    *   **Mapowania globalne:** Domyślnie stosuj dane GPSR do wszystkich produktów.
    *   **Mapowania kategorii:** Stosuj dane GPSR do wszystkich produktów w określonej kategorii.
    *   **Mapowania producentów:** Stosuj dane GPSR do wszystkich produktów od określonego producenta.
    *   **Mapowania produktów/kombinacji:** Stosuj dane GPSR do pojedynczych produktów lub konkretnych kombinacji produktów (wariantów).
    *   **Formularze mapowania:** Dla każdego typu mapowania skonfigurujesz:
        *   **Przypisany podmiot producenta:** Wybierz podmiot zdefiniowany w sekcji „Podmioty”.
        *   **Przypisana osoba odpowiedzialna w UE:** Wybierz podmiot zdefiniowany w sekcji „Podmioty”.
        *   **Przypisane ostrzeżenia:** Wybierz jedno lub więcej ostrzeżeń zdefiniowanych w sekcji „Ostrzeżenia”.
        *   **Przypisane dokumenty:** Wybierz jeden lub więcej dokumentów przesłanych w sekcji „Dokumenty”.
        *   **Zasady priorytetu/nadpisywania:** (Jeśli dostępne) Zdefiniuj, jak mapowania z różnych poziomów (globalne, kategoria, producent, produkt) współdziałają i nadpisują się nawzajem.
*   **Efekt zmian:** Zmiany tutaj bezpośrednio określają, jakie informacje GPSR są wyświetlane na stronach Twoich produktów. Dobrze ustrukturyzowana strategia mapowania znacznie redukuje pracę ręczną.
*   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Zacznij od mapowań globalnych, a następnie doprecyzuj mapowania kategorii i producentów. Używaj mapowań produktów/kombinacji tylko dla wyjątków lub unikalnych produktów. Regularnie przeglądaj swoje mapowania, zwłaszcza podczas dodawania nowych produktów lub kategorii.

#### 2.2.6 Akcje masowe (Panel administracyjny > GPSR Enterprise > Akcje masowe)

Ten ekran udostępnia narzędzia do jednoczesnego stosowania danych GPSR do wielu produktów lub do wykonywania operacji masowych.

*   **Dostępne akcje i ustawienia:**
    *   **Siatka produktów:** Lista produktów z możliwością filtrowania i wyszukiwania.
    *   **Masowe przypisywanie:** Wybierz wiele produktów, a następnie przypisz podmiot producenta, osobę odpowiedzialną w UE, ostrzeżenia lub dokumenty do wszystkich wybranych produktów.
    *   **Masowe usuwanie:** Usuń dane GPSR z wybranych produktów.
    *   **Import/Eksport:** (Jeśli dostępne) Narzędzia do importowania danych GPSR z pliku CSV lub eksportowania istniejących danych.
*   **Efekt zmian:** Akcje masowe mogą szybko aktualizować dane GPSR dla dużej liczby produktów, oszczędzając znaczny czas. Używaj ostrożnie, ponieważ zmiany są stosowane szeroko.
*   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj tego po początkowej konfiguracji, aby szybko zastosować wspólne dane GPSR do dużych zestawów produktów. Przydatne również do aktualizowania danych w wielu produktach, jeśli zmienią się przepisy.

#### 2.2.7 Dopasowywacz (Panel administracyjny > GPSR Enterprise > Dopasowywacz)

Ten ekran pomaga identyfikować produkty, którym mogą brakować danych GPSR lub sugeruje potencjalne mapowania.

*   **Zarządzana tabela / Podmiot:** `gpsr_match_suggestion`
*   **Dostępne akcje i ustawienia:**
    *   **Lista sugestii:** Wyświetla produkty lub grupy produktów, które moduł identyfikuje jako potencjalnie wymagające danych GPSR lub posiadające niekompletne dane.
    *   **Reguły dopasowywania:** (Jeśli dostępne) Skonfiguruj reguły, w jaki sposób moduł sugeruje dopasowania (np. na podstawie słów kluczowych w nazwie produktu, istniejących atrybutów).
    *   **Zastosuj/Odrzuć sugestie:** Akcje do zastosowania sugerowanych danych GPSR lub odrzucenia sugestii.
*   **Efekt zmian:** Zastosowanie sugestii zaktualizuje dane GPSR dla zidentyfikowanych produktów. Pomaga to zapewnić kompleksową zgodność.
*   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Okresowo sprawdzaj ten ekran, aby wychwycić wszelkie produkty, które mogły prześlizgnąć się przez Twoją strategię mapowania.

#### 2.2.8 Dziennik audytu (Panel administracyjny > GPSR Enterprise > Dziennik audytu)

Ten ekran zawiera historyczny zapis zmian wprowadzonych w danych GPSR w module.

*   **Zarządzana tabela / Podmiot:** `gpsr_audit_log`
*   **Dostępne akcje i ustawienia:**
    *   **Siatka dziennika:** Tabela wyświetlająca wpisy ze szczegółami, takimi jak:
        *   **Data/Godzina:** Kiedy nastąpiła zmiana.
        *   **Użytkownik:** Który administrator dokonał zmiany.
        *   **Akcja:** Jaka akcja została wykonana (np. „Utworzono podmiot”, „Zmapowano produkt”, „Zaktualizowano ostrzeżenie”).
        *   **Szczegóły:** Konkretne informacje o zmianie.
*   **Efekt zmian:** Ten ekran służy do audytu i monitorowania. Nie wprowadza się tutaj bezpośrednich zmian w danych GPSR, ale zapewnia kluczowy zapis dla odpowiedzialności i rozwiązywania problemów.
*   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj tego dziennika do przeglądania zmian, zwłaszcza jeśli masz wielu administratorów zarządzających danymi GPSR, lub jeśli musisz rozwiązać problem, dlaczego pewne dane pojawiają się (lub nie pojawiają się) w front-office.

#### 2.2.9 Księga (Panel administracyjny > GPSR Enterprise > Księga)

Ten ekran prawdopodobnie zapewnia bardziej szczegółowy, „cichy” zapis wszystkich danych GPSR zastosowanych do produktów, potencjalnie obejmujący wersje historyczne lub kompleksowy przegląd do celów regulacyjnych.

*   **Dostępne akcje i ustawienia:**
    *   **Widok zorientowany na produkt:** Sposób przeglądania wszystkich danych GPSR powiązanych z konkretnym produktem, prawdopodobnie obejmujący sposób ich uzyskania (np. z mapowania kategorii lub bezpośrednio przypisane).
    *   **Opcje eksportu:** (Jeśli dostępne) Eksportuj pełną księgę do zewnętrznego przeglądu lub archiwizacji.
*   **Efekt zmian:** Ten ekran służy głównie do raportowania i szczegółowego przeglądu. Nie zmienia bezpośrednio danych front-office, ale dostarcza podstawowy zapis zgodności.
*   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj tego do szczegółowych kontroli zgodności lub podczas przygotowywania się do audytów regulacyjnych.

#### 2.2.10 API (Panel administracyjny > GPSR Enterprise > API)

Ten ekran zawiera informacje i ustawienia związane z API modułu do integracji zewnętrznych.

*   **Dostępne akcje i ustawienia:**
    *   **Token API:** Wyświetla unikalny token wymagany do uwierzytelniania żądań API.
    *   **Generuj nowy token:** Przycisk do generowania nowego tokenu API (przydatny dla bezpieczeństwa, jeśli token zostanie naruszony).
    *   **Link do dokumentacji API:** Link do dokumentacji technicznej dla programistów dotyczącej korzystania z API.
*   **Efekt zmian:** Wygenerowanie nowego tokenu unieważni stary, wymagając aktualizacji wszystkich systemów zewnętrznych korzystających z API o nowy token.
*   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Dostęp do tego tylko wtedy, gdy integrujesz moduł GPSR z systemami zewnętrznymi (np. ERP, PIM). Zachowaj swój token API w bezpiecznym miejscu.

#### 2.2.11 Cron (Panel administracyjny > GPSR Enterprise > Cron)

Ten ekran zarządza zaplanowanymi zadaniami modułu, takimi jak ponowne indeksowanie danych GPSR lub synchronizacja informacji.

*   **Dostępne akcje i ustawienia:**
    *   **URL zadania Cron:** Adres URL do zewnętrznego wyzwalania zadania cron (np. za pośrednictwem usługi cron Twojego dostawcy hostingu).
    *   **Token Cron:** Unikalny token do bezpiecznego wykonania zadania cron.
    *   **Włącz/Wyłącz Cron:** Przełącznik do aktywacji lub dezaktywacji zadania cron.
    *   **Ostatnie uruchomienie/Wynik:** Informacje o ostatnim uruchomieniu zadania cron i jego wyniku.
    *   **Ustawienia ponownego indeksowania:** Opcje dotyczące częstotliwości i liczby produktów do ponownego indeksowania na uruchomienie (np. `GPSR_CRON_REINDEX_OFFSET`, `GPSR_CRON_REINDEX_LIMIT`).
*   **Efekt zmian:** Włączenie zadania cron zapewnia regularne przetwarzanie i aktualizowanie danych GPSR w tle, utrzymując aktualność informacji w front-office. Nieprawidłowe ustawienia cron mogą prowadzić do nieaktualnych danych lub problemów z obciążeniem serwera.
*   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Upewnij się, że zadanie cron jest włączone i poprawnie skonfigurowane na Twoim serwerze hostingowym, aby zautomatyzować przetwarzanie danych. Monitoruj jego status na pulpicie.

### 2.3 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| :------------ | :--------------- | :-------------------- | :--------------- |
| **Konfiguracja modułu** | Moduł włączony | Tak | Główny przełącznik funkcjonalności modułu. |
| | Profil szablonu sklepu | Dopasuj do swojego szablonu | Optymalizuje styl wizualny dla szablonów Classic lub Hummingbird. |
| | Tryb wyświetlania | Zakładka / Akordeon | Sposób wyświetlania bloku GPSR (Zakładka, Akordeon, Blok). |
| | Styl wizualny | Domyślny / Minimalny | Estetyka bloku informacyjnego GPSR. |
| | Pokaż tytuł bloku | Tak | Wyświetla tytuł nad blokiem GPSR. |
| | Tekst tytułu bloku | "Bezpieczeństwo i zgodność produktu" | Niestandardowy tekst dla tytułu bloku. |
| | Ukryj blok, gdy dane są niekompletne | Tak | Zapobiega wyświetlaniu niekompletnych informacji GPSR. |
| | Pokaż podmiot producenta | Tak | Wyświetla szczegóły producenta. |
| | Pokaż osobę odpowiedzialną w UE | Tak | Wyświetla szczegóły osoby odpowiedzialnej w UE. |
| | Pokaż ostrzeżenia dotyczące bezpieczeństwa | Tak | Wyświetla ostrzeżenia dotyczące bezpieczeństwa produktu. |
| | Pokaż powiązane dokumenty | Tak | Wyświetla linki do dokumentów produktu. |
| | Pokaż przycisk paszportu produktu | Tak | Wyświetla przycisk do pobierania paszportu produktu PDF. |
| | Udostępniaj mapowania we wszystkich sklepach | Tak (jeśli wielosklepowy) | Centralizuje mapowania GPSR dla wielu sklepów. |
| | Akcja przy włączaniu udostępniania | (Ostrożny wybór) | Definiuje obsługę danych przy włączaniu udostępnionych mapowań. |
| | Akcja przy wyłączaniu udostępniania | (Ostrożny wybór) | Definiuje obsługę danych przy wyłączaniu udostępnionych mapowań. |
| | Niestandardowy CSS | Puste | Dodaj niestandardowy CSS do stylizacji front-office. |
| **Podmioty** | Dodaj/Edytuj podmiot | N/A | Definiuj producentów i osoby odpowiedzialne w UE. |
| **Ostrzeżenia** | Dodaj/Edytuj ostrzeżenie | N/A | Twórz i zarządzaj ostrzeżeniami dotyczącymi bezpieczeństwa. |
| **Dokumenty** | Prześlij/Zarządzaj dokumentem | N/A | Prześlij i połącz dokumenty związane z produktem. |
| **Mapowania** | Mapowania globalne/kategorii/producenta/produktu | N/A | Przypisz dane GPSR na podstawie kryteriów produktu. |
| **Akcje masowe** | Masowe przypisywanie/usuwanie | N/A | Zastosuj/usuń dane GPSR dla wielu produktów. |
| **Dopasowywacz** | Przeglądaj sugestie | N/A | Identyfikuje produkty wymagające danych GPSR. |
| **Dziennik audytu** | Wyświetl dziennik | N/A | Śledzi zmiany wprowadzone w danych GPSR. |
| **Księga** | Wyświetl/Eksportuj dane | N/A | Kompleksowy zapis danych GPSR produktu. |
| **API** | Token API, Generuj nowy token | N/A | Zarządzaj dostępem do API dla integracji zewnętrznych. |
| **Cron** | URL zadania Cron, Włącz/Wyłącz | Włączone | Automatyzuje przetwarzanie danych GPSR w tle. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem wszystko, ale blok GPSR nie wyświetla się na moich stronach produktów.**
O:
1.  **Sprawdź „Moduł włączony”:** Przejdź do **Moduły > Menedżer modułów > GPSR Enterprise > Konfiguruj** i upewnij się, że „Moduł włączony” jest ustawione na „Tak”.
2.  **Sprawdź „Ukryj blok, gdy dane są niekompletne”:** Jeśli jest to ustawione na „Tak”, blok nie zostanie wyświetlony, jeśli brakuje jakichkolwiek wymaganych danych (producent, osoba odpowiedzialna w UE, ostrzeżenia, dokumenty) dla tego konkretnego produktu. Upewnij się, że produkt ma kompletne dane GPSR przypisane za pomocą mapowań lub bezpośrednich edycji produktu.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stara zawartość pamięci podręcznej uniemożliwia wyświetlanie nowych elementów modułu.
4.  **Kompatybilność szablonu:** Upewnij się, że ustawienie „Profil szablonu sklepu” odpowiada Twojemu szablonowi (Classic lub Hummingbird). Jeśli masz mocno dostosowany szablon, może wystąpić konflikt CSS. Spróbuj dodać niestandardowy CSS, aby wymusić widoczność lub skontaktuj się z pomocą techniczną.

**P: Mój blok informacyjny GPSR wygląda dziwnie lub jest źle wyrównany na mojej stronie internetowej.**
O:
1.  **Profil szablonu:** Sprawdź ponownie ustawienie „Profil szablonu sklepu” w konfiguracji modułu. Upewnij się, że jest ustawiony na prawidłowy profil dla Twojego szablonu PrestaShop (Classic lub Hummingbird).
2.  **Niestandardowy CSS:** Jeśli masz niestandardowy CSS w swoim szablonie lub w polu „Niestandardowy CSS” modułu, może on powodować konflikt. Spróbuj tymczasowo usunąć niestandardowy CSS, aby sprawdzić, czy problem zostanie rozwiązany.
3.  **Pamięć podręczna przeglądarki:** Wyczyść pamięć podręczną przeglądarki (Ctrl+F5 lub Cmd+R), aby upewnić się, że widzisz najnowszą stylizację.
4.  **Skontaktuj się z pomocą techniczną:** Jeśli problem nadal występuje, Twój szablon może mieć unikalną stylizację, która wymaga specyficznych dostosowań. Skontaktuj się z pomocą techniczną MyPresta.eu, przesyłając zrzuty ekranu i nazwę swojego szablonu.

**P: Jak upewnić się, że moje dane GPSR są przetłumaczone dla klientów międzynarodowych?**
O:
1.  **Pola wielojęzyczne:** Podczas tworzenia **Podmiotów** i **Ostrzeżeń** upewnij się, że wypełniasz treść dla wszystkich języków włączonych w Twoim sklepie. Szukaj flag językowych obok pól wprowadzania.
2.  **Tłumaczenia PrestaShop:** Dla domyślnych fraz modułu (takich jak „Pobierz paszport produktu” lub tytuł bloku) przejdź do **Lokalizacja > Tłumaczenia**, wybierz „Tłumaczenia zainstalowanych modułów”, wybierz „GPSR Enterprise” i wybierz swój język docelowy. Przetłumacz tam wszelkie brakujące frazy.
3.  **Paszport produktu:** Wygenerowany paszport produktu PDF będzie odzwierciedlał język danych produktu i ostrzeżeń, które wprowadziłeś.

**P: Zadanie cron wydaje się nie działać lub moje dane nie aktualizują się automatycznie.**
O:
1.  **Cron włączony:** Na ekranie **Cron** modułu (Panel administracyjny > GPSR Enterprise > Cron) upewnij się, że zadanie cron jest włączone.
2.  **Konfiguracja Cron hostingu:** Sprawdź, czy poprawnie skonfigurowałeś zadanie cron na swoim serwerze hostingowym, używając podanego „URL zadania Cron” i „Tokenu Cron”. Zazwyczaj odbywa się to w panelu sterowania hostingu (cPanel, Plesk itp.). Zadanie cron musi być wyzwalane okresowo (np. co godzinę).
3.  **Status ostatniego uruchomienia:** Sprawdź „Ostatnie uruchomienie” i „Ostatni wynik” na ekranie Cron. Jeśli pokazuje błędy lub nie uruchomiło się ostatnio, występuje problem z konfiguracją cron lub problem po stronie serwera.
4.  **Logi serwera:** Sprawdź logi błędów PHP swojego serwera pod kątem wszelkich komunikatów związanych z wykonaniem zadania cron.

**P: Popełniłem błąd w akcji masowej i teraz wiele produktów ma nieprawidłowe dane GPSR.**
A:
1.  **Dziennik audytu:** Natychmiast sprawdź **Dziennik audytu** (Panel administracyjny > GPSR Enterprise > Dziennik audytu), aby dokładnie zidentyfikować, jakie zmiany zostały wprowadzone i przez kogo.
2.  **Cofnij ręcznie/za pomocą akcji masowych:** W zależności od zakresu błędu, może być konieczne ponowne użycie ekranu **Akcje masowe** w celu skorygowania danych lub ręczna edycja indywidualnych mapowań produktów, jeśli dotyczyło to tylko kilku.
3.  **Kopia zapasowa bazy danych:** Jeśli błąd jest poważny i szeroko rozpowszechniony, a masz aktualną kopię zapasową bazy danych z *przed* błędu, przywrócenie tej kopii zapasowej może być najszybszym rozwiązaniem. Dlatego regularne kopie zapasowe są kluczowe.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu GPSR Enterprise, przeznaczony dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł GPSR Enterprise jest zgodny z wzorcem MVC (Model-View-Controller) PrestaShop, rozszerzając podstawowe funkcjonalności i wprowadzając niestandardowe encje. Wykorzystuje `ObjectModel` do interakcji z bazą danych, `ModuleFrontController` do dostarczania danych front-office (API, cron, generowanie paszportów) oraz `AdminController` do kompleksowego zarządzania back-office. Moduł w dużym stopniu opiera się na hookach do integracji ze stronami produktów i interfejsami administracyjnymi, zapewniając nieinwazyjne, ale potężne rozwiązanie. Mapowanie danych jest hierarchiczne, co pozwala na globalne, kategoryzowane, producenta i specyficzne dla produktu nadpisywanie.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

*   `controllers/front/api.php`
    *   **Nazwa klasy:** `GpsrEnterpriseApiModuleFrontController`
    *   **Klasa nadrzędna:** `ModuleFrontController`
    *   **Odpowiedzialność:** Obsługuje żądania API dla danych GPSR. Udostępnia punkty końcowe dla systemów zewnętrznych do wysyłania zapytań o informacje dotyczące bezpieczeństwa produktów, podmiotów, ostrzeżeń i dokumentów. Wymaga uwierzytelnienia za pomocą `GPSR_API_TOKEN`. Zwraca ładunki JSON.
*   `controllers/front/cron.php`
    *   **Nazwa klasy:** `GpsrEnterpriseCronModuleFrontController`
    *   **Klasa nadrzędna:** `ModuleFrontController`
    *   **Odpowiedzialność:** Służy jako punkt końcowy dla zaplanowanych zadań (zadań cron). Wyzwala procesy w tle, takie jak ponowne indeksowanie danych GPSR, synchronizacja mapowań lub czyszczenie danych. Wymaga uwierzytelnienia za pomocą `GPSR_CRON_TOKEN`.
*   `controllers/front/data.php`
    *   **Nazwa klasy:** `GpsrEnterpriseDataModuleFrontController`
    *   **Klasa nadrzędna:** `ModuleFrontController`
    *   **Odpowiedzialność:** Udostępnia punkty końcowe AJAX do dynamicznego pobierania danych GPSR na stronie produktu w front-office. Ten kontroler prawdopodobnie pobiera konkretnego producenta, osobę odpowiedzialną w UE, ostrzeżenia i dokumenty dla danego identyfikatora produktu lub identyfikatora kombinacji.
*   `controllers/front/index.php`
    *   **Nazwa klasy:** `GpsrEnterpriseIndexModuleFrontController`
    *   **Klasa nadrzędna:** `ModuleFrontController`
    *   **Odpowiedzialność:** Kontroler frontowy zastępczy lub rezerwowy. Często używany do podstawowego routingu modułu lub do zapobiegania listowaniu katalogów.
*   `controllers/front/passport.php`
    *   **Nazwa klasy:** `GpsrEnterprisePassportModuleFrontController`
    *   **Klasa nadrzędna:** `ModuleFrontController`
    *   **Odpowiedzialność:** Generuje i udostępnia paszport produktu PDF dla określonego produktu. Gromadzi wszystkie istotne dane GPSR dla produktu i renderuje je w postaci pliku PDF do pobrania.

#### Kontrolery administracyjne Back-Office

Wszystkie kontrolery administracyjne rozszerzają `GpsrAdminController` (niestandardową klasę bazową w module), która z kolei rozszerza `ModuleAdminController`.

*   `controllers/admin/AdminGpsrAuditController.php`
    *   **Nazwa zakładki:** GPSR Enterprise > Dziennik audytu
    *   **Zarządzany podmiot:** `GpsrAuditLogEntry`
    *   **Odpowiedzialność:** Zarządza wyświetlaniem i filtrowaniem tabeli `gpsr_audit_log`, rejestrując wszystkie znaczące zmiany wprowadzone w module GPSR.
*   `controllers/admin/AdminGpsrController.php`
    *   **Nazwa zakładki:** GPSR Enterprise (główny punkt wejścia)
    *   **Odpowiedzialność:** Prawdopodobnie służy jako główny pulpit nawigacyjny lub przekierowanie do głównego ekranu konfiguracji/pulpitu modułu.
*   `controllers/admin/AdminGpsrDocumentsController.php`
    *   **Nazwa zakładki:** GPSR Enterprise > Dokumenty
    *   **Zarządzany podmiot:** `GpsrDocument` (domyślnie, ponieważ nie podano konkretnej klasy, ale zarządza dokumentami)
    *   **Odpowiedzialność:** Obsługuje przesyłanie, listowanie i zarządzanie dokumentami związanymi z GPSR (np. plikami PDF).
*   `controllers/admin/AdminGpsrEnterpriseController.php`
    *   **Nazwa zakładki:** GPSR Enterprise > Pulpit (lub główna konfiguracja)
    *   **Odpowiedzialność:** Zarządza głównymi ustawieniami konfiguracji modułu, w tym tokenami API/Cron, globalnymi opcjami wyświetlania i udostępnianiem w wielu sklepach.
*   `controllers/admin/AdminGpsrEntitiesController.php`
    *   **Nazwa zakładki:** GPSR Enterprise > Podmioty
    *   **Zarządzany podmiot:** `GpsrEntity`
    *   **Odpowiedzialność:** Zarządza tworzeniem, edycją i usuwaniem podmiotów GPSR (producentów, osób odpowiedzialnych w UE).
*   `controllers/admin/AdminGpsrLedgerController.php`
    *   **Nazwa zakładki:** GPSR Enterprise > Księga
    *   **Odpowiedzialność:** Zapewnia kompleksowy widok i interfejs zarządzania „cichą księgą” danych GPSR powiązanych z produktami, potencjalnie obejmujący dane historyczne.
*   `controllers/admin/AdminGpsrMapBrandsController.php`
    *   **Nazwa zakładki:** GPSR Enterprise > Mapowania > Marki
    *   **Zarządzany podmiot:** `Manufacturer` (rdzeń PrestaShop)
    *   **Odpowiedzialność:** Zarządza mapowaniami danych GPSR na podstawie producentów PrestaShop.
*   `controllers/admin/AdminGpsrMapCategoriesController.php`
    *   **Nazwa zakładki:** GPSR Enterprise > Mapowania > Kategorie
    *   **Zarządzany podmiot:** `Category` (rdzeń PrestaShop)
    *   **Odpowiedzialność:** Zarządza mapowaniami danych GPSR na podstawie kategorii PrestaShop.
*   `controllers/admin/AdminGpsrMapCombinationsController.php`
    *   **Nazwa zakładki:** GPSR Enterprise > Mapowania > Kombinacje
    *   **Zarządzany podmiot:** `ProductCombination` (domyślnie)
    *   **Odpowiedzialność:** Zarządza mapowaniami danych GPSR dla konkretnych kombinacji atrybutów produktu.
*   `controllers/admin/AdminGpsrMapGlobalController.php`
    *   **Nazwa zakładki:** GPSR Enterprise > Mapowania > Globalne
    *   **Odpowiedzialność:** Zarządza globalnymi mapowaniami danych GPSR, które są stosowane jako domyślne dla wszystkich produktów.
*   `controllers/admin/AdminGpsrMassController.php`
    *   **Nazwa zakładki:** GPSR Enterprise > Akcje masowe
    *   **Odpowiedzialność:** Udostępnia narzędzia do masowego przypisywania i usuwania danych GPSR do wielu produktów.
*   `controllers/admin/AdminGpsrMatcherController.php`
    *   **Nazwa zakładki:** GPSR Enterprise > Dopasowywacz
    *   **Zarządzany podmiot:** `GpsrMatchSuggestion`
    *   **Odpowiedzialność:** Zarządza sugestiami dla produktów, które mogą wymagać danych GPSR lub mają niekompletne mapowania.
*   `controllers/admin/AdminGpsrWarningsController.php`
    *   **Nazwa zakładki:** GPSR Enterprise > Ostrzeżenia
    *   **Zarządzany podmiot:** `GpsrWarning`
    *   **Odpowiedzialność:** Zarządza tworzeniem, edycją i usuwaniem ostrzeżeń dotyczących bezpieczeństwa.
*   `controllers/admin/index.php`
    *   **Odpowiedzialność:** Standardowy pusty plik `index.php` PrestaShop zapobiegający listowaniu katalogów.

### 4.3 Klasy i modele podstawowe (`classes/`)

*   `classes/GpsrAdminController.php`
    *   **Odpowiedzialność:** Niestandardowa klasa bazowa dla wszystkich kontrolerów administracyjnych w module GPSR. Prawdopodobnie udostępnia wspólne metody, właściwości i zmienne szablonów używane w interfejsach back-office modułu, zapewniając spójność i redukując duplikację kodu.
*   `classes/GpsrAuditLogEntry.php`
    *   **Rozszerza:** `ObjectModel`
    *   **Tabela bazy danych:** `ps_gpsr_audit_log`
    *   **Pola `$definition`:** `id_gpsr_audit_log`, `id_employee`, `action`, `object_type`, `object_id`, `details`, `date_add`
    *   **Kluczowe metody publiczne:** Metody do logowania wpisów audytu, pobierania danych dziennika.
    *   **Logika biznesowa:** Rejestruje każdą znaczącą akcję wykonaną w module GPSR do celów audytu i zgodności.
*   `classes/GpsrCompatibility.php`
    *   **Odpowiedzialność:** Obsługuje warstwy kompatybilności dla różnych wersji PrestaShop (1.7.x, 8.x, 9.x). Ta klasa prawdopodobnie zawiera statyczne metody do abstrakcji różnic specyficznych dla wersji w wywołaniach API, nazwach hooków lub renderowaniu szablonów, zapewniając płynne działanie modułu we wszystkich obsługiwanych wersjach.
*   `classes/GpsrEntity.php`
    *   **Rozszerza:** `ObjectModel`
    *   **Tabela bazy danych:** `ps_gpsr_entity` (i `ps_gpsr_entity_lang` dla pól wielojęzycznych)
    *   **Pola `$definition`:** `id_gpsr_entity`, `type`, `name`, `address`, `contact_email`, `contact_phone`, `contact_website`, `active`, `date_add`, `date_upd` (i pola wielojęzyczne, takie jak `name_lang`, `address_lang` itp.)
    *   **Kluczowe metody publiczne:** Metody do operacji CRUD na podmiotach, pobierania podmiotów według typu, kojarzenia podmiotów z produktami/mapowaniami.
    *   **Logika biznesowa:** Zarządza danymi dla producentów i osób odpowiedzialnych w UE.
*   `classes/GpsrWarning.php`
    *   **Rozszerza:** `ObjectModel`
    *   **Tabela bazy danych:** `ps_gpsr_warning` (i `ps_gpsr_warning_lang` dla pól wielojęzycznych)
    *   **Pola `$definition`:** `id_gpsr_warning`, `icon`, `active`, `date_add`, `date_upd` (i pola wielojęzyczne, takie jak `title`, `content`)
    *   **Kluczowe metody publiczne:** Metody do operacji CRUD na ostrzeżeniach, pobierania ostrzeżeń według ID, kojarzenia ostrzeżeń z produktami/mapowaniami.
    *   **Logika biznesowa:** Zarządza danymi dla ostrzeżeń dotyczących bezpieczeństwa.
*   `classes/index.php`
    *   **Odpowiedzialność:** Standardowy pusty plik `index.php` PrestaShop zapobiegający listowaniu katalogów.

### 4.4 Zasoby JavaScript (`views/js/`)

*   `gpsrenterprise/lib/searchTool/views/js/autocomplete.js`
    *   **Zakres:** Prawdopodobnie Back-office.
    *   **Odpowiedzialność:** Zapewnia funkcjonalność autouzupełniania dla pól wyszukiwania w interfejsie administracyjnym, prawdopodobnie do wybierania produktów, kategorii lub podmiotów na ekranach mapowania.
*   `gpsrenterprise/views/js/admin-api.js`
    *   **Zakres:** Back-office (AdminGpsrEnterpriseController, zakładka API).
    *   **Odpowiedzialność:** Obsługuje interakcje AJAX dla ekranu konfiguracji API, takie jak generowanie nowych tokenów API lub wyświetlanie modalnych okien dokumentacji API.
*   `gpsrenterprise/views/js/admin-combination-map.js`
    *   **Zakres:** Back-office (AdminGpsrMapCombinationsController).
    *   **Odpowiedzialność:** Zarządza interfejsem użytkownika i wywołaniami AJAX do mapowania danych GPSR na konkretne kombinacje produktów. Prawdopodobnie obejmuje to dynamiczne ładowanie list kombinacji i obsługę przypisań.
*   `gpsrenterprise/views/js/admin-combination-picker.js`
    *   **Zakres:** Back-office (zakładka strony produktu, formularze mapowania).
    *   **Odpowiedzialność:** Udostępnia komponent interfejsu użytkownika do wybierania kombinacji produktów, często używany w formularzach mapowania lub zakładce edycji produktu.
*   `gpsrenterprise/views/js/admin-country-rules.js`
    *   **Zakres:** Back-office (Potencjalnie w formularzach podmiotów lub ostrzeżeń).
    *   **Odpowiedzialność:** Zarządza logiką interfejsu użytkownika do stosowania reguł GPSR na podstawie konkretnych krajów, jeśli moduł obsługuje zgodność specyficzną dla kraju.
*   `gpsrenterprise/views/js/admin-entity-picker.js`
    *   **Zakres:** Back-office (Formularze mapowania, zakładka strony produktu).
    *   **Odpowiedzialność:** Udostępnia komponent interfejsu użytkownika do wybierania instancji `GpsrEntity` (producentów, osób odpowiedzialnych w UE) z listy rozwijanej lub interfejsu wyszukiwania.
*   `gpsrenterprise/views/js/admin-icon-picker-data.js`
    *   **Zakres:** Back-office (Formularze ostrzeżeń).
    *   **Odpowiedzialność:** Zawiera dane (np. tablicę nazw/ścieżek ikon) używane przez `admin-icon-picker.js`.
*   `gpsrenterprise/views/js/admin-icon-picker.js`
    *   **Zakres:** Back-office (Formularze ostrzeżeń).
    *   **Odpowiedzialność:** Implementuje komponent interfejsu użytkownika do wizualnego wybierania ikony do skojarzenia z `GpsrWarning`.
*   `gpsrenterprise/views/js/admin-identifier-shortcodes.js`
    *   **Zakres:** Back-office (Pola tekstowe w formularzach, np. dla szablonów paszportów produktów).
    *   **Odpowiedzialność:** Zapewnia funkcjonalność wstawiania predefiniowanych „shortcode'ów” lub symboli zastępczych do pól tekstowych, które zostaną dynamicznie zastąpione danymi produktu podczas renderowania.
*   `gpsrenterprise/views/js/admin-item-picker.js`
    *   **Zakres:** Back-office (Ogólne formularze mapowania).
    *   **Odpowiedzialność:** Ogólny komponent interfejsu użytkownika do wybierania różnych elementów (produktów, kategorii, dokumentów, ostrzeżeń) z listy lub wyszukiwania.
*   `gpsrenterprise/views/js/admin-mass-grid.js`
    *   **Zakres:** Back-office (AdminGpsrMassController).
    *   **Odpowiedzialność:** Zarządza interaktywną siatką produktów i funkcjonalnością akcji masowych na ekranie „Akcje masowe”.
*   `gpsrenterprise/views/js/admin-product-tab.js`
    *   **Zakres:** Back-office (Strona edycji produktu).
    *   **Odpowiedzialność:** Wstrzykuje i zarządza niestandardową zakładką GPSR na stronie edycji produktu PrestaShop, umożliwiając bezpośrednie przypisywanie danych GPSR do poszczególnych produktów.
*   `gpsrenterprise/views/js/adminGpsrDashboard.js`
    *   **Zakres:** Back-office (Pulpit AdminGpsrController/AdminGpsrEnterpriseController).
    *   **Odpowiedzialność:** Obsługuje dynamiczne elementy i aktualizacje AJAX na pulpicie modułu, takie jak odświeżanie statusu cron lub wyświetlanie statystyk.
*   `gpsrenterprise/views/js/front.js`
    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Główny JavaScript dla bloku informacyjnego GPSR w front-office. Obsługuje dynamiczne ładowanie danych (za pośrednictwem kontrolera `data.php`), funkcjonalność zakładek/akordeonu i potencjalnie interakcje z przyciskiem Paszportu Produktu.
*   `gpsrenterprise/views/js/gpsr-barcode.js`
    *   **Zakres:** Front-office lub Back-office (Generowanie paszportu produktu).
    *   **Odpowiedzialność:** Prawdopodobnie skrypt narzędziowy do generowania lub wyświetlania kodów kreskowych, potencjalnie używany w paszporcie produktu PDF lub do identyfikacji produktu.

### 4.5 Arkusze stylów CSS (`views/css/`)

*   `gpsrenterprise/lib/searchTool/views/css/autocomplete.css`
    *   **Zakres:** Back-office.
    *   **Odpowiedzialność:** Style dla pól wyszukiwania autouzupełniania używanych w interfejsie administracyjnym.
*   `gpsrenrterprise/views/css/admin-api.css`
    *   **Zakres:** Back-office (AdminGpsrEnterpriseController, zakładka API).
    *   **Odpowiedzialność:** Style specyficzne dla konfiguracji API i wyświetlania dokumentacji.
*   `gpsrenterprise/views/css/admin-combination-map.css`
    *   **Zakres:** Back-office (AdminGpsrMapCombinationsController).
    *   **Odpowiedzialność:** Style dla interfejsu mapowania kombinacji.
*   `gpsrenterprise/views/css/admin-combination-picker.css`
    *   **Zakres:** Back-office.
    *   **Odpowiedzialność:** Style dla komponentu wyboru kombinacji produktów.
*   `gpsrenterprise/views/css/admin-config.css`
    *   **Zakres:** Back-office (Strona konfiguracji modułu).
    *   **Odpowiedzialność:** Ogólne style dla głównego formularza konfiguracji modułu.
*   `gpsrenterprise/views/css/admin-country-rules.css`
    *   **Zakres:** Back-office.
    *   **Odpowiedzialność:** Style dla interfejsów konfiguracji reguł specyficznych dla kraju.
*   `gpsrenterprise/views/css/admin-dashboard.css`
    *   **Zakres:** Back-office (Pulpit AdminGpsrController/AdminGpsrEnterpriseController).
    *   **Odpowiedzialność:** Style dla pulpitu administracyjnego modułu.
*   `gpsrenterprise/views/css/admin-help.css`
    *   **Zakres:** Back-office.
    *   **Odpowiedzialność:** Style dla tekstów pomocy, podpowiedzi lub sekcji dokumentacji w panelu administracyjnym.
*   `gpsrenterprise/views/css/admin-item-picker.css`
    *   **Zakres:** Back-office.
    *   **Odpowiedzialność:** Style dla ogólnego komponentu wyboru elementów.
*   `gpsrenterprise/views/css/admin-list-enhanced.css`
    *   **Zakres:** Back-office.
    *   **Odpowiedzialność:** Ulepszenia domyślnej stylizacji listy/siatki PrestaShop dla lepszej czytelności lub funkcjonalności.
*   `gpsrenterprise/views/css/admin-mass-grid.css`
    *   **Zakres:** Back-office (AdminGpsrMassController).
    *   **Odpowiedzialność:** Style dla siatki produktów akcji masowych.
*   `gpsrenterprise/views/css/admin-nav.css`
    *   **Zakres:** Back-office.
    *   **Odpowiedzialność:** Style dla niestandardowych zakładek nawigacyjnych lub pozycji menu modułu w panelu administracyjnym.
*   `gpsrenterprise/views/css/admin-product-tab.css`
    *   **Zakres:** Back-office (Strona edycji produktu).
    *   **Odpowiedzialność:** Style dla zakładki GPSR dodanej do strony edycji produktu PrestaShop.
*   `gpsrenterprise/views/css/front-classic.css`
    *   **Zakres:** Front-office (szablon Classic).
    *   **Odpowiedzialność:** Specyficzna stylizacja dla bloku GPSR, gdy wybrany jest profil szablonu Classic.
*   `gpsrenterprise/views/css/front-hummingbird.css`
    *   **Zakres:** Front-office (szablon Hummingbird).
    *   **Odpowiedzialność:** Specyficzna stylizacja dla bloku GPSR, gdy wybrany jest profil szablonu Hummingbird.
*   `gpsrenterprise/views/css/front.css`
    *   **Zakres:** Front-office.
    *   **Odpowiedzialność:** Ogólna, podstawowa stylizacja dla bloku informacyjnego GPSR w sklepie, stosowana niezależnie od profilu szablonu, która jest następnie potencjalnie nadpisywana przez `front-classic.css` lub `front-hummingbird.css`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

*   `gpsrenterprise/views/templates/hook/product-gpsr-classic.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (w zależności od konfiguracji)
    *   **Wyjście:** Główny blok informacyjny GPSR dla strony produktu w front-office, stylizowany specjalnie dla profilu szablonu Classic.
*   `gpsrenterprise/views/templates/hook/product-gpsr-hummingbird.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (w zależności od konfiguracji)
    *   **Wyjście:** Główny blok informacyjny GPSR dla strony produktu w front-office, stylizowany specjalnie dla profilu szablonu Hummingbird.
*   `gpsrenterprise/views/templates/hook/product-gpsr.tpl`
    *   **Hook:** `displayProductAdditionalInfo`, `displayProductExtraContent`, `displayFooterProduct`, `displayReassurance` (w zależności od konfiguracji)
    *   **Wyjście:** Ogólny lub podstawowy szablon dla bloku informacyjnego GPSR, który może zawierać logikę ładowania szablonów specyficznych dla Classic lub Hummingbird na podstawie konfiguracji modułu.
*   `gpsrenterprise/views/templates/hook/_product-gpsr-attrs.tpl`
    *   **Hook:** Wewnętrzny szablon częściowy.
    *   **Wyjście:** Renderuje specyficzne atrybuty lub szczegóły w głównym bloku produktu GPSR, takie jak indywidualne ostrzeżenia, szczegóły podmiotów lub linki do dokumentów. Jest to prawdopodobnie dołączane przez `product-gpsr.tpl` lub jego warianty specyficzne dla szablonu.

#### Szablony administracyjne (`views/templates/admin/`)

*   `gpsrenterprise/lib/searchTool/views/scripts.tpl`
    *   **Wyjście:** Zawiera logikę JavaScript lub Smarty dla funkcjonalności narzędzia wyszukiwania, prawdopodobnie dołączaną na różnych stronach administracyjnych.
*   `gpsrenterprise/views/templates/admin/api.tpl`
    *   **Wyjście:** Renderuje zawartość ekranu konfiguracji API, w tym wyświetlanie tokena, przycisk generowania i link do dokumentacji.
*   `gpsrenterprise/views/templates/admin/back-office.tpl`
    *   **Wyjście:** Ogólny szablon back-office, prawdopodobnie dla głównego pulpitu modułu lub jako opakowanie dla innych widoków administracyjnych.
*   `gpsrenterprise/views/templates/admin/combination-list.tpl`
    *   **Wyjście:** Wyświetla listę kombinacji produktów, używaną w interfejsach mapowania lub wyboru.
*   `gpsrenterprise/views/templates/admin/combination-picker.tpl`
    *   **Wyjście:** Renderuje interfejs użytkownika do wybierania kombinacji produktów.
*   `gpsrenterprise/views/templates/admin/combination-script.tpl`
    *   **Wyjście:** Zawiera JavaScript specyficzny dla zarządzania kombinacjami, prawdopodobnie dołączany na stronach dotyczących kombinacji produktów.
*   `gpsrenterprise/views/templates/admin/configure.tpl`
    *   **Wyjście:** Renderuje główny formularz konfiguracji modułu (dostępny przez Moduły > Konfiguruj).
*   `gpsrenterprise/views/templates/admin/country-rules-panel.tpl`
    *   **Wyjście:** Renderuje panel do zarządzania regułami GPSR specyficznymi dla kraju.
*   `gpsrenterprise/views/templates/admin/cron.tpl`
    *   **Wyjście:** Renderuje zawartość ekranu konfiguracji i statusu zadania Cron.
*   `gpsrenterprise/views/templates/admin/dashboard.tpl`
    *   **Wyjście:** Renderuje główny pulpit modułu ze statystykami i szybkimi linkami.
*   `gpsrenterprise/views/templates/admin/documents.tpl`
    *   **Wyjście:** Renderuje listę i interfejs zarządzania dokumentami GPSR.
*   `gpsrenterprise/views/templates/admin/entities-list.tpl`
    *   **Wyjście:** Wyświetla listę skonfigurowanych podmiotów GPSR.
*   `gpsrenterprise/views/templates/admin/entities.tpl`
    *   **Wyjście:** Główny szablon opakowujący dla ekranu zarządzania podmiotami.
*   `gpsrenterprise/views/templates/admin/entity-form.tpl`
    *   **Wyjście:** Renderuje formularz do dodawania lub edytowania `GpsrEntity`.
*   `gpsrenterprise/views/templates/admin/entity-picker.tpl`
    *   **Wyjście:** Renderuje interfejs użytkownika do wybierania `GpsrEntity`.
*   `gpsrenterprise/views/templates/admin/getCombinations.tpl`
    *   **Wyjście:** Szablon prawdopodobnie używany do odpowiedzi AJAX w celu dynamicznego ładowania kombinacji produktów.
*   `gpsrenterprise/views/templates/admin/item-picker.tpl`
    *   **Wyjście:** Renderuje ogólny komponent interfejsu użytkownika do wybierania elementów.
*   `gpsrenterprise/views/templates/admin/ledger.tpl`
    *   **Wyjście:** Renderuje szczegółowy widok księgi GPSR.
*   `gpsrenterprise/views/templates/admin/map-fields.tpl`
    *   **Wyjście:** Szablon częściowy zawierający wspólne pola dla mapowań GPSR (np. selektory podmiotów, selektory ostrzeżeń).
*   `gpsrenterprise/views/templates/admin/map-form-category.tpl`
    *   **Wyjście:** Renderuje formularz do tworzenia/edycji mapowań GPSR na poziomie kategorii.
*   `gpsrenterprise/views/templates/admin/map-form-combination.tpl`
    *   **Wyjście:** Renderuje formularz do tworzenia/edycji mapowań GPSR na poziomie kombinacji produktów.
*   `gpsrenterprise/views/templates/admin/map-form-global.tpl`
    *   **Wyjście:** Renderuje formularz do tworzenia/edycji globalnych mapowań GPSR.
*   `gpsrenterprise/views/templates/admin/map-form-manufacturer.tpl`
    *   **Wyjście:** Renderuje formularz do tworzenia/edycji mapowań GPSR na poziomie producenta.
*   `gpsrenterprise/views/templates/admin/mappings.tpl`
    *   **Wyjście:** Główny szablon opakowujący dla sekcji Mapowania, prawdopodobnie zawierający nawigację dla różnych typów mapowań.
*   `gpsrenterprise/views/templates/admin/mass-grid.tpl`
    *   **Wyjście:** Renderuje siatkę produktów i kontrolki akcji masowych dla ekranu „Akcje masowe”.
*   `gpsrenterprise/views/templates/admin/matcher.tpl`
    *   **Wyjście:** Renderuje interfejs dla Dopasowywacza GPSR, wyświetlając sugestie.
*   `gpsrenterprise/views/templates/admin/nav-tabs.tpl`
    *   **Wyjście:** Renderuje zakładki nawigacyjne dla sekcji back-office modułu (Pulpit, Podmioty, Ostrzeżenia, Mapowania itp.).
*   `gpsrenterprise/views/templates/admin/product-preview-card.tpl`
    *   **Wyjście:** Renderuje małą kartę podglądu produktu, prawdopodobnie używaną w komponentach wyboru lub siatkach akcji masowych.
*   `gpsrenterprise/views/templates/admin/product-tab.tpl`
    *   **Wyjście:** Renderuje zawartość niestandardowej zakładki GPSR na stronie edycji produktu PrestaShop.
*   `gpsrenterprise/views/templates/admin/warning-form.tpl`
    *   **Wyjście:** Renderuje formularz do dodawania lub edytowania `GpsrWarning`.
*   `gpsrenterprise/views/templates/admin/warnings-list.tpl`
    *   **Wyjście:** Wyświetla listę skonfigurowanych ostrzeżeń GPSR.
*   `gpsrenterprise/views/templates/admin/_api_documentation_modal.tpl`
    *   **Wyjście:** Renderuje zawartość okna modalnego wyświetlającego dokumentację API.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

*   `ps_gpsr_audit_log`: Przechowuje wpisy dziennika audytu dla zmian wprowadzonych w module.
    *   `id_gpsr_audit_log` (PK)
    *   `id_employee` (FK do `ps_employee`)
    *   `action` (np. 'add', 'edit', 'delete', 'map')
    *   `object_type` (np. 'entity', 'warning', 'product_mapping')
    *   `object_id`
    *   `details` (JSON lub tekst dla dodatkowych informacji)
    *   `date_add`
*   `ps_gpsr_entity`: Przechowuje szczegóły dla producentów i osób odpowiedzialnych w UE.
    *   `id_gpsr_entity` (PK)
    *   `type` (np. 'manufacturer', 'eu_responsible')
    *   `active`
    *   `date_add`, `date_upd`
*   `ps_gpsr_entity_lang`: Pola wielojęzyczne dla `ps_gpsr_entity`.
    *   `id_gpsr_entity` (FK)
    *   `id_lang` (FK)
    *   `name`
    *   `address`
    *   `contact_email`
    *   `contact_phone`
    *   `contact_website`
*   `ps_gpsr_warning`: Przechowuje definicje ostrzeżeń dotyczących bezpieczeństwa.
    *   `id_gpsr_warning` (PK)
    *   `icon`
    *   `active`
    *   `date_add`, `date_upd`
*   `ps_gpsr_warning_lang`: Pola wielojęzyczne dla `ps_gpsr_warning`.
    *   `id_gpsr_warning` (FK)
    *   `id_lang` (FK)
    *   `title`
    *   `content`
*   `ps_gpsr_document`: Przechowuje szczegóły przesłanych dokumentów.
    *   `id_gpsr_document` (PK)
    *   `filename`
    *   `mime_type`
    *   `file_size`
    *   `date_add`, `date_upd`
*   `ps_gpsr_document_lang`: Pola wielojęzyczne dla `ps_gpsr_document` (np. `name`).
*   `ps_gpsr_product_mapping`: Bezpośrednie przypisania danych GPSR na poziomie produktu.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK, dla kombinacji)
    *   `id_gpsr_entity_manufacturer` (FK do `ps_gpsr_entity`)
    *   `id_gpsr_entity_eu_responsible` (FK do `ps_gpsr_entity`)
    *   `date_add`, `date_upd`
*   `ps_gpsr_product_warning`: Tabela łącząca dla relacji produkt-ostrzeżenie.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK)
    *   `id_gpsr_warning` (FK)
*   `ps_gpsr_product_document`: Tabela łącząca dla relacji produkt-dokument.
    *   `id_product` (FK)
    *   `id_product_attribute` (FK)
    *   `id_gpsr_document` (FK)
*   `ps_gpsr_category_mapping`: Przypisania danych GPSR na poziomie kategorii.
    *   `id_category` (FK)
    *   `id_gpsr_entity_manufacturer`
    *   `id_gpsr_entity_eu_responsible`
*   `ps_gpsr_category_warning`: Tabela łącząca dla relacji kategoria-ostrzeżenie.
*   `ps_gpsr_category_document`: Tabela łącząca dla relacji kategoria-dokument.
*   `ps_gpsr_manufacturer_mapping`: Przypisania danych GPSR na poziomie producenta.
    *   `id_manufacturer` (FK)
    *   `id_gpsr_entity_manufacturer`
    *   `id_gpsr_entity_eu_responsible`
*   `ps_gpsr_manufacturer_warning`: Tabela łącząca dla relacji producent-ostrzeżenie.
*   `ps_gpsr_manufacturer_document`: Tabela łącząca dla relacji producent-dokument.
*   `ps_gpsr_global_mapping`: Przechowuje globalne domyślne dane GPSR.
*   `ps_gpsr_match_suggestion`: Przechowuje sugestie generowane przez dopasowywacz.
    *   `id_gpsr_match_suggestion` (PK)
    *   `id_product`
    *   `suggestion_type`
    *   `suggested_data` (JSON)
    *   `date_add`
*   `ps_configuration`: Ustawienia modułu są przechowywane tutaj z kluczami takimi jak `GPSR_ENABLED`, `GPSR_CUSTOM_CSS`, `GPSR_API_TOKEN`, `GPSR_CRON_TOKEN` itp.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| :-------- | :--------------- | :---------------- |
| `actionProductSave` | Po zapisaniu produktu (dodanie lub aktualizacja). | Wyzwala ponowną ocenę danych GPSR dla produktu, aktualizuje mapowania lub rejestruje zmiany. |
| `actionAfterUpdateProductFormHandler` | Po zaktualizowaniu formularza produktu w BO. | Odświeża dane GPSR wyświetlane w zakładce produktu lub wyzwala powiązane aktualizacje. |
| `actionObjectProductDeleteAfter` | Po usunięciu obiektu produktu. | Czyści powiązane dane GPSR i mapowania dla usuniętego produktu. |
| `actionAfterCreateProductFormHandler` | Po utworzeniu formularza produktu w BO. | Inicjalizuje dane GPSR dla nowego produktu, potencjalnie stosując domyślne mapowania. |
| `displayAfterProductThumbs` | Na stronie produktu, po zdjęciach produktu. | Renderuje blok informacyjny GPSR w front-office. (Umiejscowienie zależy od szablonu/konfiguracji) |
| `actionObjectProductAddAfter` | Po dodaniu nowego obiektu produktu. | Wyzwala początkowe przypisanie danych GPSR dla nowego produktu. |
| `displayProductAdditionalInfo` | Na stronie produktu, w sekcji „Dodatkowe informacje”. | Renderuje blok informacyjny GPSR w front-office, często jako zakładkę. |
| `displayAdminProductsExtra` | Na stronie edycji produktu w Panelu Administracyjnym. | Wstrzykuje niestandardową zakładkę GPSR do zarządzania danymi specyficznymi dla produktu. |
| `displayBackOfficeHeader` | W nagłówku każdej strony Panelu Administracyjnego. | Ładuje CSS/JS specyficzne dla modułu dla interfejsów administracyjnych, dodaje pozycje menu. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny ustawia swoje media (CSS/JS). | Ładuje CSS/JS specyficzne dla modułu dla odpowiednich stron administracyjnych. |
| `displayProductExtraContent` | Na stronie produktu, dla dodatkowych bloków treści. | Renderuje blok informacyjny GPSR w front-office, oferując elastyczne umiejscowienie. |
| `displayFooterProduct` | W sekcji stopki strony produktu. | Renderuje blok informacyjny GPSR w front-office, często jako blok poniżej głównej treści. |
| `displayReassurance` | W bloku potwierdzenia produktu (np. darmowa wysyłka, bezpieczna płatność). | Renderuje blok informacyjny GPSR w front-office, potencjalnie jako mała, uspokajająca odznaka lub link. |
| `actionProductAttributeUpdate` | Po zaktualizowaniu kombinacji produktu (atrybutu). | Wyzwala ponowną ocenę danych GPSR dla konkretnej kombinacji. |
| `actionFrontControllerSetMedia` | Gdy kontroler frontowy ustawia swoje media (CSS/JS). | Ładuje CSS/JS specyficzne dla modułu dla stron front-office, na których wyświetlane są dane GPSR. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu GPSR Enterprise, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności lub integracji modułu.
