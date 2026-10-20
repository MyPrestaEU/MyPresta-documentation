---
title: "Masowa zmiana cen pro - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Masowa zmiana cen pro” od MyPresta.eu."
sidebar:
  label: "Masowa zmiana cen pro - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Mass price change pro na MyPresta.eu](https://mypresta.eu/modules/administration-tools/mass-price-change-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/mass-price-change-pro/)
>
> ---


# Masowa zmiana cen pro

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.0.0 - 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do ogólnego działania PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

Moduł „Masowa zmiana cen pro” zapewnia kompleksowy interfejs w Panelu administracyjnym PrestaShop do definiowania i wykonywania zmian cen. Wszystkie ustawienia są dostępne za pośrednictwem głównej strony konfiguracji modułu.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Menedżer modułów > Masowa zmiana cen pro > Konfiguruj)

Po wejściu na stronę konfiguracji modułu znajdziesz serię zakładek lub sekcji zaprojektowanych tak, aby poprowadzić Cię przez proces definiowania operacji zmiany cen.

#### **Główne zakładki / sekcje:**

Konfiguracja modułu jest zazwyczaj zorganizowana w kilka kluczowych sekcji, często prezentowanych jako zakładki lub odrębne bloki na stronie głównej. Chociaż dokładne etykiety mogą się nieznacznie różnić między wersjami, podstawowa funkcjonalność pozostaje spójna:

1.  **Co zrobić (WTD):** Zdefiniuj typ zmiany ceny.
2.  **Produkty docelowe:** Wybierz, które produkty zostaną objęte zmianą.
3.  **Ograniczenia:** Dodaj dodatkowe warunki do targetowania.
4.  **Reguły:** Zdefiniuj konkretne reguły cenowe.
5.  **Podgląd:** Zobacz wpływ przed zastosowaniem.
6.  **Historia:** Przejrzyj poprzednie operacje.
7.  **Harmonogram:** Zaplanuj przyszłe zmiany cen.
8.  **Import/Eksport CSV:** Zarządzaj cenami za pomocą CSV.
9.  **Konfiguracja Cron:** Skonfiguruj zautomatyzowane zadania.

Przejdźmy przez każdą sekcję szczegółowo:

#### **4.1.1 Co zrobić (WTD)**

Ta sekcja służy do definiowania głównej akcji zmiany ceny.

-   **Co robi to ustawienie:** Określa, w jaki sposób ceny produktów zostaną zmodyfikowane. Wybierasz między zwiększeniem, zmniejszeniem lub ustawieniem nowej ceny, a także czy dotyczy to ceny podstawowej, ceny specyficznej czy wpływu na kombinacje.
-   **Wpływ zmiany tego ustawienia:**
    -   *Zwiększ o procent:* Dodaje procent bieżącej ceny do produktu.
    -   *Zmniejsz o procent:* Odejmuje procent bieżącej ceny od produktu.
    -   *Zwiększ o stałą kwotę:* Dodaje określoną wartość pieniężną do ceny produktu.
    -   *Zmniejsz o stałą kwotę:* Odejmuje określoną wartość pieniężną od ceny produktu.
    -   *Ustaw nową cenę na:* Nadpisuje bieżącą cenę nową, określoną wartością.
    -   *Zastosuj do ceny podstawowej:* Modyfikuje główną cenę produktu.
    -   *Zastosuj do ceny specyficznej:* Modyfikuje ceny ustawione za pomocą reguł „Cen specyficznych” (np. dla grup, krajów lub ilości).
    -   *Zastosuj do wpływu na kombinacje:* Modyfikuje korektę ceny dla kombinacji produktów (atrybutów).
-   **Zalecana wartość:** Zależy całkowicie od Twojego celu biznesowego. Zacznij od jasnego celu (np. „zwiększ wszystkie ceny o 5%”) przed dokonaniem wyboru.
-   **Scenariusz / przykład sprzedawcy:**
    -   *Scenariusz 1 (Inflacja):* „Muszę zwiększyć wszystkie ceny moich produktów o 3% z powodu rosnących kosztów dostawców.” -> Wybierz „Zwiększ o procent”, wprowadź „3” i wybierz „Zastosuj do ceny podstawowej”.
    -   *Scenariusz 2 (Wyprzedaż):* „Chcę obniżyć cenę wszystkich produktów w kategorii ‘Kolekcja letnia’ o 5 USD.” -> Wybierz „Zmniejsz o stałą kwotę”, wprowadź „5” i wybierz „Zastosuj do ceny podstawowej”.

#### **4.1.2 Produkty docelowe**

Tutaj precyzyjnie wybierasz, *które* produkty zostaną objęte zmianą ceny.

-   **Co robi to ustawienie:** Pozwala filtrować produkty na podstawie różnych kryteriów, takich jak kategorie, producenci, dostawcy, konkretne identyfikatory produktów, a nawet produkty bez ceny specyficznej.
-   **Wpływ zmiany tego ustawienia:**
    -   *Wybór kategorii:* Uwzględnione zostaną tylko produkty z wybranych kategorii.
    -   *Wybór producentów/dostawców:* Dotknięte zostaną tylko produkty tych marek/źródeł.
    -   *Wprowadzanie identyfikatorów produktów:* Celowane będą tylko dokładnie te produkty, które wymienisz.
    -   *Filtrowanie według „Produktów bez ceny specyficznej”:* Przydatne do upewnienia się, że nie nadpiszesz przypadkowo istniejących reguł cen specyficznych.
-   **Zalecana wartość:** Bądź jak najbardziej precyzyjny, aby uniknąć niezamierzonych zmian. W razie potrzeby użyj wielu filtrów.
-   **Scenariusz / przykład sprzedawcy:**
    -   *Scenariusz 1 (Aktualizacja marki):* „Mój główny dostawca, ‘Fashionista Co.’, podniósł ceny. Muszę zaktualizować wszystkie produkty tego producenta.” -> Wybierz „Producent”, a następnie wybierz „Fashionista Co.”.
    -   *Scenariusz 2 (Zapasy sezonowe):* „Chcę przecenić wszystkie produkty w kategorii ‘Odzież zimowa’.” -> Wybierz „Kategoria”, a następnie wybierz „Odzież zimowa”.

#### **4.1.3 Ograniczenia**

Ta sekcja pozwala dodać jeszcze bardziej szczegółowe warunki do targetowania produktów.

-   **Co robi to ustawienie:** Zapewnia zaawansowane opcje filtrowania, takie jak targetowanie produktów w określonym przedziale cenowym, produktów z konkretnymi cechami lub atrybutami, lub produktów, które są aktualnie na stanie.
-   **Wpływ zmiany tego ustawienia:**
    -   *Przedział cenowy:* Uwzględnione zostaną tylko produkty, których bieżąca cena mieści się w określonym minimum i maksimum.
    -   *Cechy/Atrybuty:* Celuj w produkty, które mają określoną cechę (np. „Kolor: Czerwony”) lub atrybut (np. „Rozmiar: XL”).
    -   *Tylko na stanie:* Zapewnia, że dotknięte zostaną tylko produkty aktualnie dostępne do zakupu.
-   **Zalecana wartość:** Użyj ich, aby jeszcze bardziej doprecyzować listę docelową, zwłaszcza w przypadku złożonych promocji lub korekt opartych na inwentarzu.
-   **Scenariusz / przykład sprzedawcy:**
    -   *Scenariusz 1 (Wyprzedaż produktów premium):* „Chcę zaoferować zniżkę na produkty o wysokiej wartości. Obniż ceny o 10% dla wszystkich produktów powyżej 100 USD w kategorii ‘Elektronika’.” -> W „Produktach docelowych” wybierz „Elektronika”. W „Ograniczeniach” ustaw „Przedział cenowy” od „100 USD” do „Maks.”.
    -   *Scenariusz 2 (Wyprzedaż konkretnego towaru):* „Muszę wyprzedać wszystkie koszule w kolorze ‘Niebieskim’, które są aktualnie na stanie.” -> W „Produktach docelowych” wybierz „Koszule”. W „Ograniczeniach” wybierz „Atrybut: Kolor > Niebieski” i „Tylko na stanie”.

#### **4.1.4 Reguły**

Ta sekcja pozwala zdefiniować bardziej złożoną logikę cenową, potencjalnie nadpisując lub dodając do ogólnej akcji „Co zrobić”.

-   **Co robi to ustawienie:** Umożliwia tworzenie warunkowych korekt cen. Na przykład: „Jeśli produkt jest w Kategorii A, zwiększ jego cenę o 5%, ale jeśli jest w Kategorii B, zmniejsz ją o 10%.”
-   **Wpływ zmiany tego ustawienia:** Pozwala na bardzo zniuansowane strategie cenowe, gdzie różne grupy produktów otrzymują różne korekty w ramach jednej operacji.
-   **Zalecana wartość:** Użyj tego, gdy pojedyncza, jednolita zmiana ceny nie jest wystarczająca dla wszystkich docelowych produktów.
-   **Scenariusz / przykład sprzedawcy:**
    -   *Scenariusz (Zniżka warstwowa):* „Dla produktów w kategorii ‘Akcesoria’, jeśli ich cena wynosi od 10 do 50 USD, zmniejsz o 5%. Jeśli ich cena przekracza 50 USD, zmniejsz o 10%.” -> Tutaj skonfigurujesz wiele reguł, każda z własnym przedziałem cenowym i korektą.

#### **4.1.5 Podgląd**

Przed zatwierdzeniem jakichkolwiek zmian, ta kluczowa sekcja pozwala przejrzeć proponowane modyfikacje.

-   **Co robi to ustawienie:** Wyświetla listę produktów, które zostaną objęte zmianą, pokazując ich bieżącą cenę i jaka będzie ich nowa cena po operacji.
-   **Wpływ zmiany tego ustawienia:** Jest to sekcja tylko do odczytu. Stanowi zabezpieczenie, pozwalając wychwycić wszelkie błędy w targetowaniu lub regułach, zanim zostaną zastosowane w Twoim sklepie.
-   **Zalecana wartość:** **ZAWSZE** dokładnie przeglądaj podgląd przed przystąpieniem do faktycznej zmiany ceny.
-   **Scenariusz / przykład sprzedawcy:**
    -   *Scenariusz (Podwójne sprawdzenie):* „Ustawiłem 10% zniżki na wszystkie ‘Sukienki letnie’. Podgląd pokazuje sukienkę, o której wiem, że nie powinna być przeceniona. Mogę wrócić do ‘Produktów docelowych’ lub ‘Ograniczeń’, aby doprecyzować mój wybór.”

#### **4.1.6 Historia**

Ta sekcja przechowuje zapis wszystkich poprzednich operacji zmiany cen.

-   **Co robi to ustawienie:** Pokazuje dziennik, kto wykonał jaką zmianę ceny, kiedy to zostało zrobione i jaki był typ operacji.
-   **Wpływ zmiany tego ustawienia:** Jest to dziennik tylko do odczytu. Jest nieoceniony do audytu, rozwiązywania problemów i zrozumienia poprzednich decyzji cenowych.
-   **Zalecana wartość:** Regularnie sprawdzaj historię, zwłaszcza jeśli wiele osób zarządza sklepem, aby upewnić się, że wszystkie zmiany są celowe i śledzone.
-   **Scenariusz / przykład sprzedawcy:**
    -   *Scenariusz (Audyt):* „Klient zgłosił nieprawidłową cenę. Mogę sprawdzić historię, aby zobaczyć, czy niedawna masowa zmiana ceny mogła to spowodować i kto zainicjował zmianę.”

#### **4.1.7 Harmonogram**

Zaplanuj automatyczne wykonanie zmian cen w przyszłym terminie i godzinie.

-   **Co robi to ustawienie:** Pozwala zdefiniować operację zmiany ceny i ustawić ją tak, aby uruchamiała się automatycznie w określonym dniu i godzinie. Możesz również ustawić, aby ceny wróciły do poprzedniego stanu po określonym czasie, idealne do tymczasowych wyprzedaży.
-   **Wpływ zmiany tego ustawienia:**
    -   *Zaplanowane wykonanie:* Zmiana ceny zostanie zastosowana bez ręcznej interwencji w wybranym czasie.
    -   *Przywróć ceny:* Produkty wrócą do swoich oryginalnych cen (lub innej określonej ceny) po zakończeniu okresu wyprzedaży.
-   **Zalecana wartość:** Niezbędne do zarządzania promocjami, wyprzedażami sezonowymi lub wszelkimi zmianami cen, które muszą wejść w życie poza godzinami pracy.
-   **Scenariusz / przykład sprzedawcy:**
    -   *Scenariusz (Wyprzedaż Black Friday):* „Chcę zastosować 20% zniżki na wszystkie produkty o 00:00 w Black Friday i przywrócić oryginalne ceny o 23:59 w Cyber Monday.” -> Skonfiguruj operację zniżki, zaplanuj ją na Black Friday i dodaj harmonogram przywracania na Cyber Monday.

#### **4.1.8 Import/Eksport CSV**

Zarządzaj cenami produktów za pomocą plików CSV w celu zaawansowanej kontroli lub zewnętrznej manipulacji danymi.

-   **Co robi to ustawienie:**
    -   *Eksport:* Pozwala wyeksportować listę produktów (na podstawie kryteriów targetowania) z ich bieżącymi cenami do pliku CSV.
    -   *Import:* Pozwala przesłać plik CSV zawierający identyfikatory produktów i nowe ceny, stosując te zmiany w Twoim sklepie.
-   **Wpływ zmiany tego ustawienia:**
    -   *Eksport:* Zapewnia arkusz kalkulacyjny docelowych produktów i ich cen, który można edytować zewnętrznie.
    -   *Import:* Nadpisuje lub aktualizuje ceny dla produktów wymienionych w CSV, oferując potężny sposób zarządzania dużymi, złożonymi listami cen.
-   **Zalecana wartość:** Użyj eksportu do szczegółowej analizy lub gdy musisz dokonać bardzo specyficznych, nienumerycznych korekt cen, które łatwiej jest zarządzać w arkuszu kalkulacyjnym. Użyj importu, gdy masz predefiniowaną listę nowych cen od dostawcy lub z zewnętrznego systemu.
-   **Scenariusz / przykład sprzedawcy:**
    -   *Scenariusz (Lista cen dostawcy):* „Mój dostawca wysłał mi nową listę cen dla 500 produktów. Zamiast ręcznie aktualizować każdy z nich, mogę wyeksportować moją bieżącą listę produktów, dopasować ją do listy dostawcy, dostosować ceny w CSV, a następnie zaimportować ją z powrotem.”

#### **4.1.9 Konfiguracja Cron**

Skonfiguruj zadanie cron modułu dla zautomatyzowanych zadań, zwłaszcza dla zaplanowanych zmian cen.

-   **Co robi to ustawienie:** Zapewnia niezbędne polecenie lub adres URL do skonfigurowania zadania cron na Twoim serwerze. To zadanie cron jest niezbędne do działania funkcji „Harmonogram”, ponieważ okresowo sprawdza i wykonuje zaplanowane zmiany cen.
-   **Wpływ zmiany tego ustawienia:**
    -   *Prawidłowa konfiguracja Cron:* Zapewnia, że zaplanowane zmiany cen uruchamiają się automatycznie w określonych godzinach. Bez prawidłowo skonfigurowanego zadania cron, zaplanowane zadania nie zostaną wykonane.
-   **Zalecana wartość:** Postępuj zgodnie z instrukcjami dostarczonymi przez moduł, aby skonfigurować zadanie cron na swoim serwerze hostingowym. Zazwyczaj polega to na dodaniu wiersza do pliku crontab serwera. Moduł zazwyczaj dostarcza dokładne polecenie.
-   **Scenariusz / przykład sprzedawcy:**
    -   *Scenariusz (Zautomatyzowane wyprzedaże):* „Zaplanowałem błyskawiczną wyprzedaż na przyszły tydzień. Aby upewnić się, że rozpocznie się dokładnie na czas, muszę upewnić się, że zadanie cron jest prawidłowo skonfigurowane i działa co 5-15 minut.” -> Skopiuj dostarczone polecenie cron i dodaj je do menedżera cron serwera.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Co zrobić** | Typ operacji (Zwiększ/Zmniejsz/Ustaw) | N/A (zależy od celu) | Definiuje, jak zmieniają się ceny (np. +5%, -10 USD, ustaw na 25 USD). |
| | Wartość (Procent/Stała) | N/A (zależy od celu) | Kwota lub procent korekty ceny. |
| | Zastosuj do (Podstawowa/Specyficzna/Kombinacje) | Cena podstawowa | Określa, który typ ceny jest objęty zmianą. |
| **Produkty docelowe** | Kategorie | Wybierz konkretne | Filtruje produkty według kategorii. |
| | Producenci | Wybierz konkretnych | Filtruje produkty według marki. |
| | Dostawcy | Wybierz konkretnych | Filtruje produkty według dostawcy. |
| | Identyfikatory produktów | Wprowadź listę | Celuje w konkretne produkty według ID. |
| | Produkty bez ceny specyficznej | Tak/Nie | Wyklucza produkty z istniejącymi cenami specyficznymi. |
| **Ograniczenia** | Przedział cenowy (Min/Max) | N/A (opcjonalnie) | Filtruje produkty w określonym przedziale cenowym. |
| | Cechy / Atrybuty | Wybierz konkretne | Filtruje produkty według ich cech lub atrybutów. |
| | Tylko na stanie | Tak/Nie | Dotyczy tylko produktów aktualnie na stanie. |
| **Reguły** | Dodaj regułę | N/A (opcjonalnie) | Definiuje warunkowe korekty cen na podstawie kryteriów. |
| **Podgląd** | (Tabela tylko do odczytu) | N/A | Pokazuje bieżące vs. nowe ceny dla objętych produktów. **Zawsze przeglądaj!** |
| **Historia** | (Dziennik tylko do odczytu) | N/A | Rejestruje wszystkie poprzednie operacje zmiany cen. |
| **Harmonogram** | Zaplanuj operację | N/A (opcjonalnie) | Ustawia przyszłą datę/godzinę automatycznego uruchomienia zmian cen. |
| | Przywróć ceny | N/A (opcjonalnie) | Planuje przywrócenie cen po określonym czasie. |
| **Import/Eksport CSV** | Eksportuj produkty | N/A (opcjonalnie) | Pobiera dane docelowych produktów do edycji zewnętrznej. |
| | Importuj ceny | N/A (opcjonalnie) | Przesyła plik CSV w celu zastosowania nowych cen do produktów. |
| **Konfiguracja Cron** | Polecenie Cron | Skopiuj z modułu | Niezbędne do automatycznych zadań zaplanowanych. |

## 3. Rozwiązywanie problemów przez sprzedawców i często zadawane pytania (FAQ)

**P1: Moje ceny nie zmieniły się po zastosowaniu operacji. Co poszło nie tak?**
O1:

-   **Sprawdź zakładkę Historia:** Zweryfikuj, czy operacja została zarejestrowana i zakończona pomyślnie.
-   **Wyczyść pamięć podręczną:** PrestaShop używa pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Twoja przeglądarka również może przechowywać stare dane w pamięci podręcznej, więc spróbuj wyczyścić pamięć podręczną przeglądarki lub wyświetlić sklep w trybie incognito.
-   **Sprawdź targetowanie:** Ponownie sprawdź ustawienia „Produkty docelowe” i „Ograniczenia”. Czy przypadkowo wykluczyłeś produkty, które zamierzałeś zmienić?
-   **Ceny specyficzne:** Jeśli próbowałeś zmienić ceny podstawowe, ale produkty mają ceny specyficzne, ceny specyficzne mogą je nadpisywać. Sprawdź, czy Twoja operacja została ustawiona tak, aby dotyczyła „Cen specyficznych” czy „Ceny podstawowej”.

**P2: Moja zaplanowana zmiana ceny nie uruchomiła się o określonej godzinie.**
O2:

-   **Zadanie Cron:** Najczęstszą przyczyną jest nieprawidłowo skonfigurowane lub niedziałające zadanie cron. Przejdź do zakładki **Konfiguracja Cron** w konfiguracji modułu. Upewnij się, że dostarczone polecenie cron jest prawidłowo dodane do pliku crontab Twojego serwera i działa z zalecaną częstotliwością (np. co 5-15 minut). Jeśli nie wiesz, jak to zrobić, skontaktuj się z dostawcą hostingu lub webmasterem.
-   **Moduł włączony:** Upewnij się, że moduł „Masowa zmiana cen pro” jest nadal włączony w Menedżerze modułów.

**P3: Przypadkowo zmieniłem niewłaściwe ceny. Czy mogę cofnąć zmiany?**
O3:

-   **Zakładka Historia:** Zakładka „Historia” modułu często oferuje opcję cofnięcia poprzedniej operacji. Poszukaj przycisku „Cofnij” lub „Anuluj” obok konkretnej operacji, którą chcesz cofnąć.
-   **Kopia zapasowa bazy danych:** Jeśli opcja cofnięcia nie jest dostępna lub nie działa zgodnie z oczekiwaniami, podkreśla to znaczenie posiadania aktualnej kopii zapasowej bazy danych. Musiałbyś przywrócić bazę danych do punktu sprzed błędnej zmiany ceny. **Zawsze wykonuj kopię zapasową przed ważnymi operacjami!**

**P4: Moduł nie wyświetla się poprawnie lub powoduje błędy po instalacji.**
O4:

-   **Wersja PrestaShop:** Upewnij się, że pobrałeś i zainstalowałeś prawidłową wersję modułu dla Twojej konkretnej instalacji PrestaShop (np. PrestaShop 8.x, 1.7.x).
-   **Kompatybilność z PHP:** Zweryfikuj, czy wersja PHP Twojego serwera mieści się w obsługiwanym zakresie modułu (PHP 5.6 - 8.5).
-   **Konflikty szablonów:** Czasami niestandardowe szablony mogą powodować konflikty. Tymczasowo przełącz się na domyślny szablon PrestaShop, aby sprawdzić, czy problem zostanie rozwiązany. Jeśli tak, Twój szablon może wymagać dostosowania.
-   **Logi błędów:** Sprawdź tryb debugowania PrestaShop (jeśli jest włączony) lub logi błędów PHP Twojego serwera pod kątem konkretnych komunikatów o błędach. Mogą one dostarczyć wskazówek dla programistów.

**P5: Jak przetłumaczyć tekst modułu na inne języki?**
O5:

-   W Panelu administracyjnym PrestaShop przejdź do **Lokalizacja > Tłumaczenia**.
-   Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój szablon, a następnie wybierz „Masowa zmiana cen pro” z rozwijanej listy modułów.
-   Możesz wtedy przetłumaczyć wszystkie ciągi tekstowe modułu na wybrane języki.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem „Masowa zmiana cen pro”.

### 4.1 Przegląd architektury

Moduł „Masowa zmiana cen pro” jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując głównie klasę `Module` do swojej podstawowej funkcjonalności i `ModuleFrontController` do specyficznych zadań front-office, takich jak wykonywanie zadań cron. Moduł w dużym stopniu opiera się na swoim pliku `index.php` (główny plik modułu) do konfiguracji i przetwarzania w back-office, używając szablonów Smarty do renderowania różnych sekcji konfiguracyjnych. Integruje niestandardowy JavaScript dla ulepszonych elementów interfejsu użytkownika, takich jak targetowanie produktów i autouzupełnianie, oraz CSS do stylizacji. Chociaż nie definiuje jawnie klas `ObjectModel` w dostarczonym inwentarzu, prawdopodobnie bezpośrednio współdziała z podstawowymi tabelami PrestaShop `Product`, `SpecificPrice` i `Configuration`.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `controllers/front/cron.php`
    -   **Nazwa klasy:** `MassPriceProCronModuleFrontController` (prawdopodobnie, na podstawie konwencji nazewnictwa plików)
    -   **Klasa nadrzędna:** `ModuleFrontController`
    -   **Odpowiedzialność:** Ten kontroler jest przeznaczony do wywoływania przez zadanie cron po stronie serwera. Jego główną rolą jest wykonywanie zaplanowanych operacji zmiany cen zdefiniowanych w konfiguracji back-office modułu. Przetwarza zadania takie jak stosowanie zaplanowanych rabatów, przywracanie cen lub uruchamianie innych zautomatyzowanych korekt cen. Zazwyczaj zwraca prosty komunikat o sukcesie/porażce lub loguje swoją aktywność.
-   `controllers/front/index.php`
    -   **Nazwa klasy:** `MassPriceProIndexModuleFrontController` (prawdopodobnie)
    -   **Klasa nadrzędna:** `ModuleFrontController`
    -   **Odpowiedzialność:** Ten kontroler może służyć jako ogólny punkt wejścia dla akcji modułu front-office, które nie pasują do konkretnej kategorii, lub może być miejscem zastępczym. Biorąc pod uwagę charakter modułu, jest mniej prawdopodobne, aby miał bezpośrednią funkcjonalność skierowaną do klienta, a bardziej prawdopodobne jest, że będzie obsługiwał żądania AJAX w tle lub specyficzne pobieranie danych, jeśli będzie to potrzebne przez skrypty front-end.

#### Kontrolery administracyjne Back-Office

Moduł nie wydaje się używać dedykowanych plików `AdminController` na podstawie dostarczonego inwentarza. Cała konfiguracja i przetwarzanie w back-office są prawdopodobnie obsługiwane bezpośrednio w metodzie `getContent()` głównego pliku `masspricepro/index.php`.

### 4.3 Klasy i modele podstawowe (`classes/`)

Na podstawie dostarczonego inwentarza, w katalogu `classes/` nie ma niestandardowych klas ani definicji `ObjectModel`. Sugeruje to, że moduł bezpośrednio współdziała z podstawowymi klasami `ObjectModel` PrestaShop `Product`, `SpecificPrice`, `Category`, `Manufacturer`, `Supplier`, `Configuration` i potencjalnie innymi powiązanymi klasami `ObjectModel` oraz ich powiązanymi tabelami bazy danych. Logika zmiany cen jest prawdopodobnie hermetyzowana w metodach głównej klasy `MassPricePro` (w `index.php`).

### 4.4 Zasoby JavaScript (`views/js/`)

-   `masspricepro/lib/searchTool/views/js/autocomplete.js`
    -   **Zakres:** Prawdopodobnie zarówno Front-office (jeśli używany do wyszukiwania produktów), jak i Back-office (do targetowania produktów).
    -   **Szczegóły:** Zapewnia ogólną funkcjonalność autouzupełniania. Nasłuchuje danych wprowadzanych przez użytkownika w polach tekstowych, wysyła żądania AJAX do punktu końcowego backendu (prawdopodobnie `controllers/front/index.php` lub dedykowanego handlera AJAX w głównym pliku modułu) i wyświetla sugestie na liście rozwijanej.
-   `masspricepro/views/js/jquery.autocomplete.js`
    -   **Zakres:** Prawdopodobnie Back-office.
    -   **Szczegóły:** Wtyczka autouzupełniania oparta na jQuery. Może to być konkretna implementacja lub zależność dla interfejsów wyboru produktów modułu w back-office, np. podczas targetowania produktów według nazwy lub ID. Obsługuje renderowanie interfejsu użytkownika sugestii i zdarzeń wyboru.
-   `masspricepro/views/js/mpp_pro.js`
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Jest to prawdopodobnie główny plik JavaScript dla konfiguracji back-office modułu. Zawierałby:
        -   Słuchacze zdarzeń dla przesyłania formularzy, zmian zakładek, kliknięć przycisków (np. „Zastosuj zmiany”, „Podgląd”, „Dodaj regułę”).
        -   Wywołania AJAX do metody `getContent()` lub kontrolera front-end do przetwarzania danych (np. generowanie podglądów, zapisywanie ustawień, wykonywanie zmian cen).
        -   Manipulację DOM w celu dynamicznego pokazywania/ukrywania sekcji, aktualizowania tabel podglądu lub zarządzania danymi wejściowymi reguł.
        -   Logikę walidacji dla pól formularza.
-   `masspricepro/views/js/mpp_target_products.js`
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Specjalnie obsługuje logikę dla sekcji „Produkty docelowe” modułu. Obejmowałoby to:
        -   Zarządzanie wyborem kategorii, producentów, dostawców (np. za pomocą rozwijanych list wielokrotnego wyboru lub widoków drzewa).
        -   Obsługę wprowadzania identyfikatorów produktów, potencjalnie z walidacją.
        -   Interakcję ze skryptami autouzupełniania, aby umożliwić administratorom wyszukiwanie i wybieranie produktów.
        -   Dynamiczne aktualizowanie listy wybranych produktów docelowych.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `masspricepro/lib/searchTool/views/css/autocomplete.css`
    -   **Zakres:** Zarówno Front-office, jak i Back-office.
    -   **Szczegóły:** Zapewnia stylizację dla rozwijanych list sugestii autouzupełniania i pól wprowadzania, zapewniając ich spójność wizualną i łatwość obsługi.
-   `masspricepro/views/css/mpp_admin.css`
    -   **Zakres:** Stylizacja formularza administracyjnego Back-office.
    -   **Szczegóły:** Jest to główny arkusz stylów dla interfejsu konfiguracji modułu w Panelu administracyjnym PrestaShop. Stylizuje:
        -   Układ zakładek/sekcji konfiguracji.
        -   Elementy formularza (pola wprowadzania, przyciski, listy rozwijane, pola wyboru).
        -   Tabele (np. dla historii, podglądu).
        -   Wszelkie niestandardowe komponenty interfejsu użytkownika specyficzne dla modułu.
        -   Kluczowe selektory klas CSS, które programiści mogą nadpisać: `.mpp-container`, `.mpp-tab-content`, `.mpp-form-group`, `.mpp-table` itp.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony administracyjne (`views/templates/admin/`)

Te szablony są renderowane w metodzie `getContent()` głównego pliku modułu w celu zbudowania interfejsu konfiguracji back-office.

-   `constraints.tpl`: Renderuje sekcję do definiowania dodatkowych ograniczeń (np. przedział cenowy, cechy, atrybuty).
-   `cron_setup.tpl`: Wyświetla instrukcje i polecenie do konfiguracji zadania cron serwera.
-   `csv.tpl`: Renderuje interfejs dla funkcji importu CSV.
-   `csv_export_target.tpl`: Renderuje interfejs dla funkcji eksportu CSV, specjalnie dla produktów docelowych.
-   `history.tpl`: Wyświetla tabelę i szczegóły poprzednich operacji zmiany cen.
-   `mpp_operation_block.tpl`: Prawdopodobnie blok wielokrotnego użytku do definiowania pojedynczej operacji zmiany ceny (zwiększ/zmniejsz/ustaw).
-   `mpp_target_block.tpl`: Prawdopodobnie blok wielokrotnego użytku do definiowania kryteriów targetowania produktów.
-   `mpp_target_products_full.tpl`: Renderuje kompletny interfejs do wyboru produktów docelowych, prawdopodobnie zawierający pola autouzupełniania i listy wybranych produktów.
-   `preview.tpl`: Wyświetla tabelę pokazującą bieżące i proponowane nowe ceny przed wykonaniem.
-   `rules.tpl`: Renderuje interfejs do definiowania warunkowych reguł cenowych.
-   `scheduler.tpl`: Wyświetla formularz do planowania przyszłych zmian cen i przywracania.
-   `target_products.tpl`: Bardziej zwięzły lub alternatywny szablon do targetowania produktów, potencjalnie używany w innych sekcjach.
-   `wtd.tpl`: Renderuje sekcję „Co zrobić”, gdzie wybierany jest główny typ korekty ceny.

#### Szablony hooków (`views/templates/hook/`)

-   `form.tpl`: Ten szablon jest prawdopodobnie używany do renderowania głównego formularza konfiguracji lub jego konkretnej części, gdy moduł jest podłączony do ogólnego hooka wyświetlania (chociaż moduł głównie używa `getContent()` do swojej głównej konfiguracji). Biorąc pod uwagę cel modułu, jest mało prawdopodobne, aby wyświetlał cokolwiek bezpośrednio w front-office za pośrednictwem hooków takich jak `displayHeader` lub `displayFooter`, ale raczej używa tych hooków do ładowania zasobów lub wewnętrznego przetwarzania.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł nie tworzy niestandardowych tabel SQL na podstawie dostarczonego inwentarza. Opiera się głównie na podstawowych tabelach PrestaShop:

-   `ps_product`: Dla podstawowych cen produktów.
-   `ps_product_shop`: Dla cen produktów specyficznych dla sklepu.
-   `ps_specific_price`: Dla reguł cen specyficznych.
-   `ps_product_attribute`, `ps_product_attribute_shop`: Dla cen i wpływów kombinacji.
-   `ps_category_product`, `ps_manufacturer`, `ps_supplier`: Do targetowania produktów.
-   `ps_configuration`: Do przechowywania ustawień modułu i wartości konfiguracyjnych (np. `MPP_LAST_OPERATION_DATE`, `MPP_CRON_TOKEN`, `MPP_SCHEDULED_TASKS`).

#### Tabela zarejestrowanych hooków

Moduł prawdopodobnie rejestruje hooki, aby zintegrować się z cyklem życia PrestaShop i wyświetlać zasoby.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Aby załadować CSS specyficzny dla modułu (`mpp_admin.css`, jeśli z jakiegoś powodu jest potrzebny, choć mało prawdopodobne dla front-office) i JavaScript (`autocomplete.js`, `jquery.autocomplete.js`, jeśli używany do wyszukiwania w front-endzie). |
| `actionModuleInstall` | Podczas instalacji modułu. | Aby wykonać początkową konfigurację, utworzyć wpisy konfiguracyjne i zarejestrować inne hooki. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Aby wyczyścić wpisy konfiguracyjne i wyrejestrować hooki. |
| `actionAdminControllerSetMedia` | Po załadowaniu kontrolera administracyjnego. | Aby załadować CSS specyficzny dla back-office (`mpp_admin.css`) i JavaScript (`mpp_pro.js`, `mpp_target_products.js`, `autocomplete.js`) dla strony konfiguracji modułu. |
| `actionScheduler` (lub podobny niestandardowy hook) | Wywoływany przez zadanie cron modułu. | Aby wykonać zaplanowane zmiany cen i operacje przywracania. Jest to niestandardowy wewnętrzny hook lub metoda wywoływana przez kontroler `cron.php`. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Masowa zmiana cen pro”, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Możesz pobrać najnowsze wersje z historii zamówień i uzyskać dostęp do zasobów wsparcia bezpośrednio za pośrednictwem platformy.
