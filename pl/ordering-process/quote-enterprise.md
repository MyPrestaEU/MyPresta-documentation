---
title: "Quote Enterprise - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Quote Enterprise od MyPresta.eu."
sidebar:
  label: "Quote Enterprise - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Quote Enterprise na MyPresta.eu](https://mypresta.eu/modules/ordering-process/quote-enterprise.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/quote-enterprise/)
>
> ---


# Quote Enterprise

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Upewnij się, że Twój serwer spełnia minimalne wymagania PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel Administracyjny > Moduły > Konfiguruj > Quote Enterprise)

Jest to główny ekran konfiguracji, na którym definiujesz podstawowe zachowanie i wygląd modułu Quote Enterprise.

#### Zakładka Ustawienia ogólne

-   **Włącz Quote Enterprise:**
    -   **Co robi to ustawienie:** Jest to główny przełącznik dla całego modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* System wycen staje się aktywny w Twoim sklepie, a klienci mogą zacząć prosić o wyceny.
        -   *Gdy wyłączone:* Cała funkcjonalność wycen jest ukryta z front-office, i nie można prosić o nowe wyceny. Istniejące wyceny w panelu administracyjnym pozostają dostępne do zarządzania.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Włącz to, gdy jesteś gotowy do oferowania usług wycen. Wyłącz tymczasowo podczas konserwacji lub jeśli zdecydujesz się zaprzestać oferowania wycen.
-   **Zezwól na zapytania o wycenę z koszyka:**
    -   **Co robi to ustawienie:** Określa, czy klienci mogą przekształcić cały swój koszyk w zapytanie o wycenę.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Przycisk lub link „Poproś o wycenę” pojawi się w podsumowaniu koszyka, umożliwiając klientom przesłanie wszystkich pozycji w koszyku do wyceny.
        -   *Gdy wyłączone:* Klienci mogą prosić o wyceny tylko ze stron poszczególnych produktów lub za pomocą pływającego przycisku (jeśli włączony), a nie bezpośrednio z koszyka.
    -   **Zalecana wartość:** TAK (dla większości scenariuszy B2B i zamówień hurtowych)
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli głównie zajmujesz się dużymi zamówieniami wieloprzedmiotowymi, gdzie ceny są często negocjowane, włącz to. Jeśli Twoje wyceny dotyczą zazwyczaj pojedynczych, niestandardowych produktów, możesz to wyłączyć.
-   **Zezwól na zapytania o wycenę ze strony produktu:**
    -   **Co robi to ustawienie:** Kontroluje, czy przycisk „Poproś o wycenę” pojawia się na stronach poszczególnych produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Klienci mogą dodać konkretny produkt do zapytania o wycenę bezpośrednio z jego strony, zamiast dodawać go do koszyka.
        -   *Gdy wyłączone:* Opcja zapytania o wycenę jest usuwana ze stron produktów.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Niezbędne dla produktów niestandardowych, przedmiotów o wysokiej wartości lub gdy chcesz zaoferować alternatywę dla bezpośredniego zakupu dowolnego produktu.
-   **Wyświetl pływający przycisk wyceny:**
    -   **Co robi to ustawienie:** Dodaje stały, pływający przycisk do front-office Twojego sklepu, umożliwiając klientom zainicjowanie zapytania o wycenę z prawie każdej strony.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Pojawi się mały, klikalny przycisk (często w rogu ekranu), otwierający formularz zapytania o wycenę lub listę istniejących wycen.
        -   *Gdy wyłączone:* Pływający przycisk nie będzie widoczny.
    -   **Zalecana wartość:** TAK (dla wysokiej widoczności i łatwości dostępu)
    -   **Scenariusz / przykład dla sprzedawcy:** Użyj tego, aby opcja wyceny była bardzo widoczna w całym sklepie, zachęcając do większej liczby zapytań.
-   **Minimalna wartość zamówienia dla zapytania o wycenę:**
    -   **Co robi to ustawienie:** Ustawia minimalną całkowitą wartość (w Twojej domyślnej walucie), którą musi spełnić zapytanie o wycenę, aby zostało przesłane.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na wartość (np. 100):* Klienci nie mogą przesłać zapytania o wycenę, jeśli całkowita wartość pozycji w ich zapytaniu jest niższa od tej kwoty. Zostanie wyświetlony komunikat o błędzie.
        -   *Gdy ustawione na 0 lub pozostawione puste:* Nie jest egzekwowana żadna minimalna wartość.
    -   **Zalecana wartość:** 0 (lub wartość, która odfiltrowuje trywialne zapytania)
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz przetwarzać wyceny tylko dla znaczących zamówień, ustaw minimalną wartość (np. 500 zł), aby zmniejszyć obciążenie administracyjne dla małych zapytań.
-   **Domyślna ważność wyceny (dni):**
    -   **Co robi to ustawienie:** Domyślnie określa, ile dni nowo utworzona wycena będzie ważna.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na liczbę (np. 30):* Wszystkie nowe wyceny utworzone przez Twój zespół automatycznie będą miały datę ważności 30 dni od ich utworzenia.
        -   *Gdy ustawione na 0 lub pozostawione puste:* Wyceny nie będą miały domyślnego okresu ważności, a Twój zespół będzie musiał ręcznie ustawić jeden lub zarządzać nimi bez wygaśnięcia.
    -   **Zalecana wartość:** 30 (lub okres typowy dla Twojej branży)
    -   **Scenariusz / przykład dla sprzedawcy:** Ustawienie 30-dniowej ważności zachęca klientów do działania w rozsądnym terminie i chroni Cię przed wahaniami cen.

#### Zakładka Szablony e-mail

Ta sekcja umożliwia dostosowanie powiadomień e-mail wysyłanych przez moduł.

-   **Menedżer szablonów e-mail:**
    -   **Co robi to ustawienie:** Zapewnia wizualny interfejs do edycji zawartości różnych szablonów e-mail związanych z wycenami (np. nowe zapytanie o wycenę, zaktualizowana wycena, zaakceptowana wycena).
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy edytujesz szablon:* Odpowiedni e-mail wysłany do klientów lub Twojego zespołu będzie odzwierciedlał Twoje zmiany, w tym tekst, branding i układ.
    -   **Zalecana wartość:** Dostosuj, aby pasowały do głosu Twojej marki i zawierały jasne instrukcje.
    -   **Scenariusz / przykład dla sprzedawcy:** Zmień e-mail „Nowe zapytanie o wycenę”, aby zawierał konkretne instrukcje dla Twojego zespołu sprzedaży lub dodaj spersonalizowane powitanie dla klientów.

#### Zakładka Ustawienia zaawansowane

-   **Włącz REST API:**
    -   **Co robi to ustawienie:** Aktywuje programistyczny interfejs (API) dla modułu, umożliwiając zewnętrznym systemom lub niestandardowym aplikacjom interakcję z Twoimi wycenami.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł udostępnia punkty końcowe, które mogą być używane przez programistów do programowego tworzenia, odczytywania, aktualizowania i usuwania wycen.
        -   *Gdy wyłączone:* API jest nieaktywne i nie można uzyskać do niego dostępu.
    -   **Zalecana wartość:** NIE (chyba że masz specyficzne potrzeby integracyjne)
    -   **Scenariusz / przykład dla sprzedawcy:** Jeśli integrujesz się z systemem CRM, ERP lub niestandardową aplikacją mobilną, włączenie API pozwala tym systemom automatycznie tworzyć lub aktualizować wyceny w PrestaShop. Wymaga wiedzy programistycznej.
-   **Zarządzanie kluczami API:**
    -   **Co robi to ustawienie:** Umożliwia generowanie i zarządzanie kluczami API, które są niezbędne do uwierzytelniania żądań do REST API modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy tworzysz klucz:* Otrzymujesz unikalny identyfikator, którego zewnętrzne aplikacje muszą używać do uzyskania dostępu do API.
        -   *Gdy cofasz klucz:* Każda aplikacja używająca tego klucza straci dostęp do API.
    -   **Zalecana wartość:** Generuj klucze tylko wtedy, gdy są potrzebne do konkretnych integracji.
    -   **Scenariusz / przykład dla sprzedawcy:** Utwórz nowy klucz API dla swojego systemu CRM, aby przesyłać nowe leady jako zapytania o wycenę do PrestaShop.
-   **URL zadania Cron dla wygaśnięcia i podsumowania:**
    -   **Co robi to ustawienie:** Udostępnia adres URL, który po uzyskaniu dostępu wyzwala zadania w tle, takie jak sprawdzanie wygaśnięcia wycen i wysyłanie codziennych podsumowań do Twojego zespołu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy skonfigurowane na Twoim serwerze:* Moduł będzie automatycznie wykonywał te zadania w regularnych odstępach czasu (np. codziennie), zapewniając, że wyceny są oznaczane jako wygasłe, a Twój zespół otrzymuje terminowe podsumowania.
        -   *Gdy nie skonfigurowane:* Sprawdzanie wygaśnięcia i e-maile z podsumowaniem nie będą zautomatyzowane.
    -   **Zalecana wartość:** Skonfiguruj ten adres URL jako codzienne zadanie cron na swoim serwerze hostingowym.
    -   **Scenariusz / przykład dla sprzedawcy:** Skonfiguruj zadanie cron, aby uruchamiać ten adres URL raz dziennie, aby upewnić się, że klienci są powiadamiani o wygasających wycenach, a Twój zespół sprzedaży otrzymuje codzienne podsumowanie nowych zapytań.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 Zarządzanie wycenami (Panel Administracyjny > Quote Enterprise > Wyceny)

Jest to centralne centrum dla Twojego zespołu sprzedaży do zarządzania wszystkimi zapytaniami o wycenę.

-   **Nazwa ekranu i lokalizacja w menu:** **Quote Enterprise > Wyceny**
-   **Dostępne działania i ustawienia:**
    -   **Tabela listy wycen:** Wyświetla wszystkie przesłane wyceny z kluczowymi informacjami, takimi jak nazwa klienta, status, całkowita wartość i data utworzenia.
    -   **Filtrowanie i wyszukiwanie:** Narzędzia do znajdowania konkretnych wycen według klienta, statusu, zakresu dat itp.
    -   **Wyświetl/Edytuj wycenę:** Kliknij dowolną wycenę, aby otworzyć szczegółowy widok, w którym możesz:
        -   **Dostosuj produkty i ilości:** Modyfikuj pozycje, ilości i ceny w ramach wyceny.
        -   **Dodaj/Usuń produkty:** Wyszukuj i dodawaj nowe produkty do wyceny lub usuwaj istniejące.
        -   **Zastosuj rabaty:** Oferuj konkretne rabaty na całkowitą kwotę wyceny lub poszczególne pozycje.
        -   **Ustaw ważność:** Zdefiniuj datę wygaśnięcia wyceny.
        -   **Dodaj notatki/wiadomości:** Komunikuj się z klientem bezpośrednio za pośrednictwem interfejsu wyceny.
        -   **Zmień status:** Zaktualizuj status wyceny (np. Oczekująca, Wysłana, Zaakceptowana, Odrzucona, Wygasła).
        -   **Generuj PDF:** Utwórz profesjonalną fakturę proforma PDF dla klienta.
        -   **Przekształć w zamówienie:** Jednym kliknięciem przekształć zaakceptowaną wycenę w standardowe zamówienie PrestaShop, gotowe do realizacji.
        -   **Wyślij e-mail:** Wyślij zaktualizowane szczegóły wyceny lub wiadomości do klienta.
    -   **Działania masowe:** Wybierz wiele wycen, aby wykonać działania takie jak zmiana statusu, usunięcie lub eksport.
-   **Efekt zmian:**
    -   Modyfikacja wyceny aktualizuje jej szczegóły w bazie danych i może wywołać powiadomienia e-mail do klienta.
    -   Przekształcenie w zamówienie tworzy nowe zamówienie w standardowym systemie zarządzania zamówieniami PrestaShop, wstępnie wypełnione wycenionymi pozycjami i cenami.
    -   Zmiana statusu aktualizuje widok klienta na jego koncie i może wywołać określone szablony e-mail.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Regularnie sprawdzaj listę „Wyceny” pod kątem nowych żądań „Oczekujących”.
    2.  Otwórz każde nowe żądanie, przejrzyj pozycje, dostosuj ceny/ilości, jeśli to konieczne, i dodaj wszelkie wewnętrzne notatki.
    3.  Ustaw okres ważności i wygeneruj proformę PDF.
    4.  Zmień status na „Wysłana” i wyślij wycenę e-mailem do klienta.
    5.  Monitoruj wyceny „Wysłane”. Jeśli zaakceptowane, przekształć w zamówienie. Jeśli odrzucone lub wygasłe, odpowiednio zaktualizuj status.

#### 2.2.2 Dziennik audytu (Panel Administracyjny > Quote Enterprise > Dziennik audytu)

Ten ekran zapewnia szczegółową historię wszystkich działań wykonanych na wycenach.

-   **Nazwa ekranu i lokalizacja w menu:** **Quote Enterprise > Dziennik audytu**
-   **Dostępne działania i ustawienia:**
    -   **Tabela listy dziennika:** Wyświetla chronologiczną listę zdarzeń związanych z wycenami, w tym kto wykonał działanie, jakie działanie zostało podjęte (np. „Wycena utworzona”, „Cena zmieniona”, „Status zaktualizowany”) i kiedy to nastąpiło.
    -   **Filtrowanie:** Filtruj dziennik według daty, użytkownika lub typu działania, aby znaleźć konkretne zdarzenia.
-   **Efekt zmian:** Jest to dziennik tylko do odczytu; nie możesz tu wprowadzać zmian. Służy jako zapis historyczny.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    -   Użyj dziennika audytu do śledzenia zmian, rozwiązywania problemów lub przeglądania aktywności zespołu w zakresie wycen. Jest to nieocenione dla odpowiedzialności i zrozumienia cyklu życia każdej wyceny.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz Quote Enterprise | TAK | Główny przełącznik funkcjonalności modułu. |
| | Zezwól na zapytania o wycenę z koszyka | TAK | Dodaje przycisk wyceny do strony koszyka. |
| | Zezwól na zapytania o wycenę ze strony produktu | TAK | Dodaje przycisk wyceny do stron produktów. |
| | Wyświetl pływający przycisk wyceny | TAK | Pokazuje stały przycisk wyceny w front-office. |
| | Minimalna wartość zamówienia dla zapytania o wycenę | 0 | Ustawia minimalną wartość dla przesłanych wycen. |
| | Domyślna ważność wyceny (dni) | 30 | Ustawia domyślne wygaśnięcie dla nowych wycen. |
| | Menedżer szablonów e-mail | Dostosuj | Edytuj zawartość e-maili dla różnych zdarzeń wyceny. |
| | Włącz REST API | NIE | Aktywuje API dla integracji zewnętrznych (tylko dla programistów). |
| | Zarządzanie kluczami API | N/A | Zarządzaj kluczami API dla bezpiecznego dostępu do API (tylko dla programistów). |
| | URL zadania Cron dla wygaśnięcia i podsumowania | Skonfiguruj | Automatyzuje sprawdzanie wygaśnięcia wycen i podsumowania dla zespołu. |
| **Zarządzanie wycenami** | Lista wycen | N/A | Przeglądaj, filtruj i zarządzaj wszystkimi wycenami. |
| | Wyświetl/Edytuj wycenę | N/A | Dostosuj pozycje, ceny, status, generuj PDF, przekształcaj w zamówienie. |
| | Działania masowe | N/A | Stosuj działania do wielu wybranych wycen. |
| **Dziennik audytu** | Lista dziennika | N/A | Przeglądaj historyczne działania na wszystkich wycenach. |

## 3. Rozwiązywanie problemów dla sprzedawcy i często zadawane pytania (FAQ)

**P: Moje przyciski „Poproś o wycenę” nie wyświetlają się w front-office.**
O:

1.  **Sprawdź status modułu:** Upewnij się, że „Włącz Quote Enterprise” jest ustawione na TAK w konfiguracji modułu.
2.  **Sprawdź konkretne ustawienia:** Zweryfikuj, czy „Zezwól na zapytania o wycenę z koszyka” i „Zezwól na zapytania o wycenę ze strony produktu” są włączone zgodnie z potrzebami.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i wyczyść pamięć podręczną PrestaShop (pamięć podręczna Smarty, pamięć podręczna systemu plików). Czasami zmiany nie pojawiają się, dopóki pamięć podręczna nie zostanie odświeżona.
4.  **Kompatybilność z motywem:** Jeśli używasz niestandardowego motywu, może występować problem z kompatybilnością. Skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojego motywu.

**P: Klienci nie otrzymują e-maili z powiadomieniami o wycenach.**
O:

1.  **Sprawdź szablony e-mail:** W konfiguracji modułu przejdź do zakładki „Szablony e-mail” i upewnij się, że szablony są poprawnie skonfigurowane i zapisane.
2.  **Ustawienia e-mail PrestaShop:** Zweryfikuj ogólne ustawienia e-mail PrestaShop (SMTP, PHP mail) w **Zaawansowane > E-mail**. Wyślij stamtąd testowy e-mail, aby potwierdzić, że system pocztowy Twojego sklepu działa.
3.  **Foldery spamu:** Doradź klientom, aby sprawdzili swoje foldery spamu lub wiadomości-śmieci.
4.  **Zadanie Cron (dla podsumowań/przypomnień):** Jeśli chodzi o przypomnienia o wygaśnięciu lub codzienne podsumowania, upewnij się, że adres URL zadania cron jest poprawnie skonfigurowany na Twoim serwerze, aby działał regularnie.

**P: Czy mogę dostosować wygląd formularza zapytania o wycenę lub przycisków?**
O: Tak, moduł używa standardowego szablonowania PrestaShop. W przypadku podstawowych zmian stylów (kolory, czcionki) często można nadpisać CSS modułu w niestandardowym pliku CSS Twojego motywu. W przypadku bardziej złożonych zmian układu, musiałbyś nadpisać pliki TPL modułu w swoim motywie. Zazwyczaj wymaga to pomocy programisty.

**P: Jak przekształcić zaakceptowaną wycenę w regularne zamówienie?**
O: W Panelu Administracyjnym PrestaShop przejdź do **Quote Enterprise > Wyceny**. Otwórz konkretną wycenę, którą chcesz przekształcić. W widoku szczegółów wyceny znajdzie się przycisk (np. „Przekształć w zamówienie” lub „Utwórz zamówienie”). Kliknięcie go wygeneruje nowe zamówienie na Twojej standardowej liście zamówień PrestaShop, wstępnie wypełnione wycenionymi pozycjami i cenami.

**P: Co się dzieje, jeśli wycena wygaśnie?**
O: Jeśli zadanie cron jest skonfigurowane, moduł automatycznie oznaczy wygasłe wyceny jako „Wygasłe”. Klienci nie będą już mogli zaakceptować ani przekształcić wygasłej wyceny w zamówienie. Twój zespół sprzedaży nadal może przeglądać wygasłe wyceny i potencjalnie je reaktywować lub utworzyć nową wycenę, jeśli to konieczne.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł Quote Enterprise przestrzega solidnej architektury PrestaShop MVC (Model-View-Controller), w dużym stopniu wykorzystując `ObjectModel` do trwałości danych. Bezproblemowo integruje się z systemem hooków PrestaShop dla wyświetlania w front-office i działań w back-office. Moduł zawiera dedykowane kontrolery administracyjne do zarządzania wycenami i dziennikami audytu, kontrolery front-office do interakcji z klientem (żądanie, lista, widok, API) oraz kompleksowy zestaw klas pomocniczych do logiki biznesowej, generowania PDF, obsługi e-maili i wielu innych. Dostępne jest również REST API do integracji z systemami zewnętrznymi.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `controllers/front/api.php`
    -   Nazwa klasy: `QuoteenterpriseApiModuleFrontController` (rozszerza `ModuleFrontController`)
    -   Odpowiedzialność: Obsługuje żądania API z front-office, prawdopodobnie dla specyficznych integracji skierowanych do klienta lub dynamicznego ładowania treści.
-   `controllers/front/cron.php`
    -   Nazwa klasy: `QuoteenterpriseCronModuleFrontController` (rozszerza `ModuleFrontController`)
    -   Odpowiedzialność: Służy jako punkt końcowy dla zadania cron, wyzwalając zadania w tle, takie jak sprawdzanie wygaśnięcia wycen i wysyłanie e-maili z podsumowaniem.
-   `controllers/front/index.php`
    -   Nazwa klasy: `QuoteenterpriseIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    -   Odpowiedzialność: Prawdopodobnie kontroler zastępczy lub bazowy, lub obsługuje domyślną trasę dla sekcji front-office modułu.
-   `controllers/front/list.php`
    -   Nazwa klasy: `QuoteenterpriseListModuleFrontController` (rozszerza `ModuleFrontController`)
    -   Odpowiedzialność: Wyświetla listę wycen dla zalogowanego klienta w obszarze jego konta.
-   `controllers/front/pdf.php`
    -   Nazwa klasy: `QuoteenterprisePdfModuleFrontController` (rozszerza `ModuleFrontController`)
    -   Odpowiedzialność: Generuje i udostępnia klientom wersje PDF wycen do pobrania.
-   `controllers/front/quoteList.php`
    -   Nazwa klasy: `QuoteenterpriseQuoteListModuleFrontController` (rozszerza `ModuleFrontController`)
    -   Odpowiedzialność: Podobnie jak `list.php`, potencjalnie alternatywny lub specyficzny widok dla list wycen, być może do ładowania AJAX.
-   `controllers/front/request.php`
    -   Nazwa klasy: `QuoteenterpriseRequestModuleFrontController` (rozszerza `ModuleFrontController`)
    -   Odpowiedzialność: Obsługuje wyświetlanie i przesyłanie formularza zapytania o wycenę ze stron produktów, koszyka lub pływającego przycisku. Przetwarza dane formularza i tworzy nowe wpisy wycen.
-   `controllers/front/view.php`
    -   Nazwa klasy: `QuoteenterpriseViewModuleFrontController` (rozszerza `ModuleFrontController`)
    -   Odpowiedzialność: Wyświetla szczegółowy widok pojedynczej wyceny dla klienta, pokazując pozycje, ceny, status i wiadomości.

#### Kontrolery administracyjne Back-Office

-   `controllers/admin/AdminQuoteEnterpriseAuditLog.php`
    -   Nazwa klasy: `AdminQuoteEnterpriseAuditLogController` (rozszerza `ModuleAdminController`)
    -   Nazwa zakładki: Quote Enterprise > Dziennik audytu
    -   Zarządzana encja: `quote_audit_log` (prawdopodobnie niestandardowy `ObjectModel` dla wpisów audytu)
    -   Odpowiedzialność: Zapewnia widok siatki dla administratorów do przeglądania wszystkich historycznych działań i zmian związanych z wycenami.
-   `controllers/admin/AdminQuoteEnterpriseQuotes.php`
    -   Nazwa klasy: `AdminQuoteEnterpriseQuotesController` (rozszerza `ModuleAdminController`)
    -   Nazwa zakładki: Quote Enterprise > Wyceny
    -   Zarządzana encja: `quote` (prawdopodobnie niestandardowy `ObjectModel` dla wycen)
    -   Odpowiedzialność: Główny interfejs do zarządzania wycenami, w tym listowanie, przeglądanie, edytowanie, przekształcanie w zamówienie i wysyłanie komunikatów.
-   `controllers/admin/index.php`
    -   Nazwa klasy: `QuoteenterpriseAdminIndexModuleFrontController` (rozszerza `ModuleAdminController`)
    -   Odpowiedzialność: Prawdopodobnie kontroler zastępczy lub bazowy dla administratora, potencjalnie przekierowujący do głównej listy wycen lub pulpitu nawigacyjnego.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   `classes/index.php`: Pusty plik, powszechna praktyka zapobiegania listowaniu katalogów.
-   `classes/QuoteAdmin.php`: Zawiera logikę dla zadań specyficznych dla administratora, potencjalnie związanych z konfiguracją modułu lub ogólnymi narzędziami administracyjnymi.
-   `classes/QuoteAdminAjax.php`: Obsługuje żądania AJAX pochodzące z back-office, takie jak dynamiczne wyszukiwanie produktów do dodania do wyceny.
-   `classes/QuoteAdminQuoteForm.php`: Zarządza złożoną logiką formularza do edycji i tworzenia wycen w back-office.
-   `classes/QuoteApi.php`: Główna klasa dla REST API modułu, obsługująca uwierzytelnianie, routing i serializację danych.
-   `classes/QuoteApiDocumentation.php`: Udostępnia metody do generowania lub wyświetlania dokumentacji dla punktów końcowych API modułu.
-   `classes/QuoteBulkActions.php`: Implementuje logikę do wykonywania działań na wielu wybranych wycenach na liście administratora (np. masowa zmiana statusu).
-   `classes/QuoteConverter.php`: Obsługuje kluczową logikę przekształcania zaakceptowanej wyceny w standardowe zamówienie PrestaShop.
-   `classes/QuoteDashboard.php`: Udostępnia dane i logikę dla widoku pulpitu nawigacyjnego modułu w back-office (jeśli istnieje), podsumowując aktywność wycen.
-   `classes/QuoteDuplicator.php`: Logika do duplikowania istniejących wycen.
-   `classes/QuoteenterpriseModuleFrontController.php`: Klasa bazowa dla kontrolerów front-office, udostępniająca wspólne metody i właściwości.
-   `classes/QuoteExpiry.php`: Zarządza logiką sprawdzania ważności wycen, oznaczania wycen jako wygasłych i wysyłania powiązanych powiadomień.
-   `classes/QuoteExporter.php`: Obsługuje eksport danych wycen (np. CSV, Excel).
-   `classes/QuoteFeeProduct.php`: Prawdopodobnie `ObjectModel` lub pomocnik do zarządzania specjalnymi „produktami opłatowymi”, które można dodawać do wycen (np. za usługi, niestandardowe opłaty).
-   `classes/QuoteListHelper.php`: Udostępnia metody pomocnicze do wyświetlania i filtrowania list wycen zarówno w front-office, jak i back-office.
-   `classes/QuoteMailer.php`: Scentralizowana klasa do wysyłania różnych powiadomień e-mail związanych z wycenami.
-   `classes/QuoteNotifyDigest.php`: Logika do kompilowania i wysyłania codziennych lub okresowych podsumowań aktywności wycen do administratorów.
-   `classes/QuotePdf.php`: Obsługuje generowanie faktur proforma PDF dla wycen.
-   `classes/QuoteProductHelper.php`: Metody pomocnicze do interakcji z produktami PrestaShop w kontekście wyceny.
-   `classes/QuoteQtyHelper.php`: Pomaga w zarządzaniu i walidacji ilości w wycenach.
-   `classes/QuoteQuotesManager.php`: Główna logika biznesowa do zarządzania wycenami, w tym tworzenia, aktualizacji i zmian statusu.
-   `classes/QuoteReference.php`: Zarządza generowaniem i unikalnością numerów referencyjnych wycen.
-   `classes/QuoteRequestHelper.php`: Pomaga w przetwarzaniu i walidacji zapytań o wycenę przesłanych przez klientów.
-   `classes/QuoteSchema.php`: Definiuje schemat bazy danych dla niestandardowych tabel używanych przez moduł (np. `ps_quote`, `ps_quote_product`, `ps_quote_audit_log`).
-   `classes/QuoteSettingDescTrait.php`: Cecha PHP prawdopodobnie używana do dostarczania wspólnych opisów lub metadanych dla ustawień modułu.
-   `classes/QuoteTaxHelper.php`: Obsługuje obliczenia podatkowe specyficzne dla wycen.
-   `classes/QuoteThemeCompat.php`: Zawiera logikę zapewniającą kompatybilność z różnymi motywami PrestaShop, potencjalnie poprzez wykrywanie funkcji motywu lub dostarczanie nadpisań.
-   `classes/QuoteTimeline.php`: Zarządza i wyświetla oś czasu zdarzeń dla konkretnej wyceny (podobnie do historii zamówień).
-   `classes/QuoteValidityHelper.php`: Metody pomocnicze do obliczania i walidacji dat wygaśnięcia wycen.
-   `classes/QuoteVisibility.php`: Kontroluje widoczność elementów związanych z wycenami w front-office (np. kto może prosić o wycenę, gdzie pojawiają się przyciski).

### 4.4 Zasoby JavaScript (`views/js/`)

-   `lib/emailTemplatesManager/js/emailTemplatesManager.js`: Logika front-end dla edytora szablonów e-mail w back-office.
-   `lib/searchTool/views/js/autocomplete.js`: Zapewnia funkcjonalność autouzupełniania dla wyszukiwania produktów lub klientów w edytorze wycen w back-office.
-   `views/js/admin-audience-picker.js`: Obsługuje logikę wyboru grup klientów lub konkretnych klientów dla widoczności lub targetowania wycen w panelu administracyjnym.
-   `views/js/adminQuoteApi.js`: JavaScript dla ekranu konfiguracji API w panelu administracyjnym, potencjalnie obsługujący generowanie kluczy lub wyświetlanie dokumentacji API.
-   `views/js/adminQuoteDashboard.js`: Skrypty dla interaktywnych elementów lub wizualizacji danych na pulpicie nawigacyjnym administratora.
-   `views/js/adminQuoteDetail.js`: Obsługuje dynamiczne interakcje w szczegółowym widoku wyceny w back-office (np. dodawanie produktów, stosowanie rabatów, zmiany statusu).
-   `views/js/adminQuoteEditor.js`: Główny JavaScript dla formularza tworzenia/edycji wycen w back-office, w tym wybór produktów, aktualizacje ilości i korekty cen.
-   `views/js/adminQuoteSelector.js`: Używany do wybierania wycen, prawdopodobnie w oknie modalnym lub powiązanym kontekście.
-   `views/js/adminQuotesList.js`: Skrypty dla listy wycen administratora, w tym filtrowanie, sortowanie i działania masowe.
-   `views/js/front.js`: Ogólny JavaScript front-office dla modułu, obsługujący kliknięcia przycisków, wyskakujące okienka modalne dla zapytań o wycenę, przesyłanie formularzy i dynamiczne aktualizacje.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `lib/emailTemplatesManager/css/emailTemplatesManager.css`: Stylizacja dla edytora szablonów e-mail w back-office.
-   `lib/searchTool/views/css/autocomplete.css`: Style dla wyników wyszukiwania autouzupełniania (np. wyszukiwanie produktów).
-   `views/css/admin-audience-picker.css`: Stylizacja dla interfejsu wyboru klienta/grupy w panelu administracyjnym.
-   `views/css/admin_quoteenterprise.css`: Główny arkusz stylów dla interfejsów back-office modułu (lista wycen, szczegóły, dziennik audytu).
-   `views/css/front-hummingbird.css`: Specyficzne dostosowania stylów front-office dla domyślnego motywu PrestaShop „Hummingbird”.
-   `views/css/front.css`: Ogólna stylizacja front-office dla przycisków wycen, formularzy i widoków konta klienta. Programiści mogą nadpisywać klasy takie jak `.quoteenterprise-button`, `.quoteenterprise-form`, `.quoteenterprise-list` w swoim motywie.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `hook/adminOrderQuote.tpl`: Renderuje blok związany z wyceną na standardowej stronie szczegółów zamówienia PrestaShop w panelu administracyjnym.
-   `hook/cartQuoteButton.tpl`: Wyświetla przycisk lub link „Poproś o wycenę” na stronie koszyka.
-   `hook/customerAccount-hummingbird.tpl`: Renderuje link do listy wycen w obszarze konta klienta dla motywu Hummingbird.
-   `hook/customerAccount.tpl`: Renderuje link do listy wycen w obszarze konta klienta dla klasycznych motywów.
-   `hook/productListQuote.tpl`: Wyświetla przycisk lub opcję wyceny na stronach listy produktów (kategoria, wyniki wyszukiwania).
-   `hook/quoteFloatButton.tpl`: Renderuje stały pływający przycisk wyceny w front-office.
-   `hook/quoteListModal.tpl`: Szablon dla okna modalnego wyświetlającego listę wycen.
-   `hook/quoteRequestButton.tpl`: Wyświetla przycisk „Poproś o wycenę” na stronach poszczególnych produktów.
-   `hook/quoteRequestModal.tpl`: Szablon dla okna modalnego, które otwiera formularz zapytania o wycenę.

#### Szablony administracyjne (`views/templates/admin/`)

-   `admin/api.tpl`: Renderuje interfejs konfiguracji API i zarządzania kluczami.
-   `admin/audience-picker.tpl`: Szablon dla narzędzia wyboru klienta/grupy w panelu administracyjnym.
-   `admin/audit.tpl`: Wyświetla tabelę dziennika audytu w back-office.
-   `admin/dashboard.tpl`: Renderuje przegląd pulpitu nawigacyjnego modułu w back-office.
-   `admin/notifications.tpl`: Wyświetla powiadomienia administracyjne związane z wycenami.
-   `admin/quoteDetail.tpl`: Kompleksowy szablon do przeglądania i edytowania pojedynczej wyceny w back-office.
-   `admin/quotes.tpl`: Renderuje główną tabelę listy wycen w back-office.
-   `admin/quotesOverview.tpl`: Sekcja podsumowania lub przeglądu wycen, prawdopodobnie na pulpicie nawigacyjnym.
-   `admin/scopeSelector.tpl`: Szablon do wyboru zakresu (np. sklep, język) w panelu administracyjnym.
-   `admin/visibilityConfigurator.tpl`: Szablon do konfigurowania reguł widoczności wycen.
-   `admin/_api_documentation_modal.tpl`: Renderuje okno modalne z dokumentacją API dla programistów.
-   `admin/_bulk_options.tpl`: Szablon dla rozwijanych list działań masowych w listach administracyjnych.

#### Szablony Front-office (`views/templates/front/`)

-   `front/list.tpl`: Wyświetla listę wycen klienta na jego koncie.
-   `front/request.tpl`: Główny szablon dla formularza zapytania o wycenę klienta.
-   `front/view.tpl`: Wyświetla szczegółowy widok pojedynczej wyceny dla klienta.
-   `front/_requestComplianceFields.tpl`: Częściowy szablon dla dodatkowych pól związanych z zgodnością w formularzu zapytania o wycenę.
-   `front/_requestLinesTable.tpl`: Częściowy szablon do wyświetlania linii produktów w formularzu zapytania o wycenę.

#### Szablony PDF (`views/templates/pdf/`)

-   `pdf/quote.tpl`: Szablon używany do generowania zawartości faktury proforma PDF.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł tworzy niestandardowe tabele, zazwyczaj z prefiksem `ps_` (lub Twoim niestandardowym prefiksem). Kluczowe tabele to:

-   `ps_quote`: Przechowuje główne szczegóły wyceny (ID klienta, status, suma, ważność, referencja itp.).
-   `ps_quote_product`: Przechowuje poszczególne produkty i ich ilości/ceny związane z każdą wyceną.
-   `ps_quote_audit_log`: Rejestruje wszystkie zmiany i działania wykonane na wycenach do celów audytu.
-   `ps_quote_api_key`: Przechowuje klucze API dla integracji zewnętrznych.
-   `ps_configuration`: Ustawienia modułu są przechowywane tutaj z kluczami takimi jak `QUOTEENTERPRISE_ENABLE`, `QUOTEENTERPRISE_MIN_VALUE` itp.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykiwanie zasobów CSS/JS, meta tagów lub globalna inicjalizacja modułu. |
| `displayRightColumn` | W prawej kolumnie Twojego sklepu (jeśli włączone przez motyw). | Wyświetlanie pływającego przycisku wyceny lub statycznego bloku zapytania o wycenę. |
| `displayLeftColumn` | W lewej kolumnie Twojego sklepu (jeśli włączone przez motyw). | Wyświetlanie pływającego przycisku wyceny lub statycznego bloku zapytania o wycenę. |
| `displayFooter` | W sekcji stopki każdej strony. | Wyświetlanie pływającego przycisku wyceny lub statycznego bloku zapytania o wycenę. |
| `displayProductButtons` | Na stronie produktu, w pobliżu przycisku „Dodaj do koszyka”. | Wyświetlanie przycisku „Poproś o wycenę” na stronach produktów. |
| `displayShoppingCartFooter` | W podsumowaniu koszyka, poniżej listy produktów. | Wyświetlanie przycisku „Poproś o wycenę” w celu przekształcenia koszyka w wycenę. |
| `displayCustomerAccount` | Na stronie „Moje konto” klienta. | Dodawanie linku do listy wycen klienta. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Potencjalnie używane do powiązania wyceny z wynikowym zamówieniem lub aktualizacji statusu wyceny. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny ładuje swoje zasoby. | Wstrzykiwanie CSS/JS specyficznych dla modułu dla stron back-office. |
| `displayAdminOrder` | Na stronie szczegółów zamówienia administratora PrestaShop. | Wyświetlanie bloku z informacjami o wycenie, jeśli zamówienie pochodziło z wyceny. |
| `actionObjectProductUpdateAfter` | Po zaktualizowaniu produktu. | Potencjalnie do aktualizacji cen wycen, jeśli ceny produktów ulegną zmianie (funkcja zaawansowana). |
| `actionObjectProductDeleteAfter` | Po usunięciu produktu. | Do obsługi produktów usuniętych z wycen. |
| `actionObjectCustomerDeleteAfter` | Po usunięciu klienta. | Do obsługi wycen związanych z usuniętym klientem. |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony back-office. | Ogólne wstrzykiwanie zasobów back-office lub globalna konfiguracja modułu administracyjnego. |
| `displayBackOfficeTop` | Na górze obszaru zawartości back-office. | Wyświetlanie alertów specyficznych dla modułu lub widżetów pulpitu nawigacyjnego. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu Quote Enterprise.
