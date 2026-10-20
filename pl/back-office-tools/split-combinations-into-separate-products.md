---
title: "Podziel kombinacje na osobne produkty - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: ""
sidebar:
  label: "Podziel kombinacje na osobne produkty - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Split combinations into separate products na MyPresta.eu](https://mypresta.eu/modules/administration-tools/split-combinations-into-separate-products.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/split-combinations-into-separate-products/)
>
> ---


# Podziel kombinacje na osobne produkty

## 1. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 1.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu, dostępny po kliknięciu „Konfiguruj” po instalacji.

#### Ustawienia ogólne

- **Włącz moduł:**

  - **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji funkcjonalności modułu.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączony:* Funkcje modułu, w tym możliwość dzielenia produktów i jego logika wyświetlania, stają się aktywne.
    - *Gdy wyłączony:* Funkcjonalność modułu jest całkowicie wyłączona. Żadne kombinacje nie zostaną podzielone, a wszelkie istniejące podzielone produkty powrócą do swojego pierwotnego stanu lub będą zarządzane jako zwykłe produkty, w zależności od wewnętrznej logiki modułu.
  - **Zalecana wartość:** TAK (gdy jesteś gotowy do użycia modułu).
  - **Scenariusz/przykład sprzedawcy:** Konfigurujesz moduł po raz pierwszy i chcesz go przetestować. Włączasz go, aby zobaczyć jego efekty. Jeśli musisz tymczasowo go wyłączyć do celów konserwacji, możesz to zrobić.
- **Tryb podziału:**

  - **Co robi to ustawienie:** Określa, w jaki sposób moduł obsługuje kombinacje produktów. Możesz wybrać między tworzeniem rzeczywistych nowych produktów dla każdej kombinacji lub tylko zmianą sposobu ich wyświetlania na stronach list.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawione na „Utwórz osobne produkty dla każdej kombinacji”:* Moduł fizycznie utworzy nowe wpisy produktów w Twojej bazie danych dla każdej kombinacji. Każdy nowy produkt będzie miał własny identyfikator, URL, stan magazynowy, cenę itp. Jest to najpotężniejsza opcja dla SEO i szczegółowej kontroli.
    - *Gdy ustawione na „Pokaż jedną kafelkę na kombinację na listach kategorii, marek, dostawców, wyszukiwania i bestsellerów (wirtualny podział)”:* Moduł *nie* utworzy nowych produktów. Zamiast tego zmodyfikuje sposób wyświetlania istniejących produktów z kombinacjami na stronach list, sprawiając, że będzie *wyglądać*, jakby każda kombinacja była osobnym produktem. Rzeczywisty katalog produktów pozostaje niezmieniony. Jest to mniej wpływowe dla SEO, ale może poprawić doświadczenie przeglądania.
  - **Zalecana wartość:** „Utwórz osobne produkty dla każdej kombinacji” dla maksymalnego SEO i kontroli, lub „Pokaż jedną kafelkę na kombinację…” dla prostszego ulepszenia wyświetlania.
  - **Scenariusz/przykład sprzedawcy:** Chcesz, aby każdy kolor i rozmiar Twojego T-shirtu miał własną stronę produktu i pozycjonował się w Google. Wybierasz „Utwórz osobne produkty”. Jeśli chcesz tylko, aby Twoje strony kategorii wyglądały czyściej, pokazując każdą wariację bez tworzenia nowych produktów, wybierasz „Pokaż jedną kafelkę na kombinację”.
- **Dziel tylko aktywne produkty:**

  - **Co robi to ustawienie:** Kontroluje, czy moduł powinien przetwarzać tylko produkty, które są aktualnie włączone w Twoim sklepie, czy wszystkie produkty niezależnie od ich statusu aktywności.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączony:* Tylko produkty, które są aktualnie ustawione jako „aktywne” w Twoim katalogu PrestaShop, będą miały podzielone kombinacje. Nieaktywne produkty zostaną zignorowane.
    - *Gdy wyłączony:* Moduł spróbuje podzielić kombinacje dla wszystkich produktów, w tym tych, które są aktualnie nieaktywne.
  - **Zalecana wartość:** TAK (aby uniknąć tworzenia niepotrzebnych produktów dla przedmiotów, których nie sprzedajesz).
  - **Scenariusz/przykład sprzedawcy:** Masz wiele starych, nieaktywnych produktów w swoim katalogu. Chcesz podzielić kombinacje tylko dla swojego aktualnego, aktywnego asortymentu, aby utrzymać porządek w sklepie. Włączasz to ustawienie.
- **Akcja produktu źródłowego po podziale:**

  - **Co robi to ustawienie:** Definiuje, co dzieje się z oryginalnym produktem (tym z kombinacjami) po tym, jak jego kombinacje zostały podzielone na nowe, indywidualne produkty.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawione na „Wyłącz produkt źródłowy”:* Oryginalny produkt zostanie oznaczony jako nieaktywny w Twoim katalogu. Nie będzie już widoczny w front office.
    - *Gdy ustawione na „Zachowaj produkt źródłowy aktywny”:* Oryginalny produkt pozostanie aktywny i widoczny w Twoim sklepie. Może być konieczne ręczne dostosowanie jego wyświetlania lub zawartości, aby uniknąć zamieszania z nowymi podzielonymi produktami.
    - *Gdy ustawione na „Usuń produkt źródłowy”:* Oryginalny produkt zostanie trwale usunięty z Twojego katalogu. Używaj z najwyższą ostrożnością!
  - **Zalecana wartość:** „Wyłącz produkt źródłowy” lub „Zachowaj produkt źródłowy aktywny” (w zależności od Twojej strategii). „Usuń produkt źródłowy” jest ogólnie niezalecane, chyba że jesteś absolutnie pewien.
  - **Scenariusz/przykład sprzedawcy:** Podzieliłeś produkt „T-shirt” na „T-shirt - Czerwony - S”, „T-shirt - Niebieski - M” itp. Chcesz, aby klienci widzieli tylko indywidualne wariacje, więc wybierasz „Wyłącz produkt źródłowy” dla oryginalnego „T-shirtu”.
- **Kopiuj obrazy produktów:**

  - **Co robi to ustawienie:** Określa, czy obrazy związane z oryginalnym produktem i jego kombinacjami powinny zostać skopiowane do nowo utworzonych podzielonych produktów.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączony:* Obrazy z oryginalnego produktu i jego konkretnej kombinacji zostaną zduplikowane i przypisane do nowego podzielonego produktu. Zapewnia to, że każdy nowy produkt ma odpowiednie wizualizacje.
    - *Gdy wyłączony:* Nowe podzielone produkty zostaną utworzone bez żadnych obrazów. Wówczas musiałbyś ręcznie przesłać obrazy dla każdego nowego produktu, co jest bardzo czasochłonne.
  - **Zalecana wartość:** TAK.
  - **Scenariusz/przykład sprzedawcy:** Masz kombinację „Czerwony T-shirt” z konkretnym obrazem. Kiedy dzielisz ją na „T-shirt - Czerwony - Mały”, chcesz, aby ten obraz czerwonego T-shirtu został automatycznie przypisany do nowego produktu.
- **Minimalna liczba kombinacji do podziału:**

  - **Co robi to ustawienie:** Ustawia próg dla liczby kombinacji, jaką produkt musi mieć, zanim moduł rozważy jego podział. Produkty z mniejszą liczbą kombinacji niż ta wartość zostaną zignorowane.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawione na wartość (np. 2):* Przetwarzane będą tylko produkty, które mają 2 lub więcej kombinacji. Produkty z tylko 1 kombinacją (lub bez kombinacji) zostaną pominięte.
    - *Gdy ustawione na 0 lub 1:* Wszystkie produkty z co najmniej jedną kombinacją zostaną rozważone do podziału.
  - **Zalecana wartość:** 2 (aby uniknąć dzielenia prostych produktów, które mogą na tym nie skorzystać).
  - **Scenariusz/przykład sprzedawcy:** Masz kilka produktów z tylko jedną kombinacją (np. T-shirt „Jeden rozmiar”). Nie chcesz ich dzielić, ale chcesz podzielić produkty z wieloma kolorami i rozmiarami. Ustawiasz to na 2.

#### Ustawienia kreatora nazw

Te ustawienia kontrolują sposób generowania nazw nowych podzielonych produktów.

- **Szablon kreatora nazw:**

  - **Co robi to ustawienie:** Pozwala zdefiniować niestandardowy szablon do generowania nazw nowych podzielonych produktów. Możesz używać symboli zastępczych dla nazwy produktu, nazw grup atrybutów i nazw atrybutów.
  - **Efekt zmiany tego ustawienia:** Moduł użyje tego szablonu do skonstruowania pola `name` dla każdego nowego produktu.
  - **Zalecana wartość:** `[product_name] - [attribute_group_name]: [attribute_name]` (lub podobna, w zależności od stylu Twojej marki).
  - **Scenariusz/przykład sprzedawcy:** Twój oryginalny produkt to „Fantazyjna Sukienka”. Ma kombinacje takie jak „Kolor: Czerwony” i „Rozmiar: Mały”. Jeśli Twój szablon to `[product_name] - [attribute_name]`, nowa nazwa produktu będzie „Fantazyjna Sukienka - Czerwony”.
- **Szablon kreatora URL:**

  - **Co robi to ustawienie:** Podobnie jak Kreator nazw, pozwala zdefiniować niestandardowy szablon do generowania przyjaznych adresów URL (slugów) nowych podzielonych produktów.
  - **Efekt zmiany tego ustawienia:** Moduł użyje tego szablonu do skonstruowania pola `link_rewrite` dla każdego nowego produktu.
  - **Zalecana wartość:** `[product_name]-[attribute_name]` (lub podobna, zapewniająca przyjazność dla SEO i unikalność).
  - **Scenariusz/przykład sprzedawcy:** Używając przykładu „Fantazyjna Sukienka”, jeśli Twój szablon URL to `[product_name]-[attribute_name]`, nowy URL może wyglądać tak: `/fantazyjna-sukienka-czerwona`.
- **Separator dla wielu atrybutów:**

  - **Co robi to ustawienie:** Określa znak lub ciąg znaków używany do oddzielania wielu nazw atrybutów, gdy są one łączone w nazwie produktu lub URL.
  - **Efekt zmiany tego ustawienia:** Ten znak zostanie wstawiony między nazwami atrybutów, jeśli produkt ma kombinacje z wielu grup atrybutów (np. Kolor i Rozmiar).
  - **Zalecana wartość:** `-` (łącznik) dla adresów URL, `,` (przecinek ze spacją) dla nazw.
  - **Scenariusz/przykład sprzedawcy:** Jeśli produkt to „T-shirt - Czerwony - Mały”, łącznik jest separatorem. Możesz zmienić go na ukośnik `/`, jeśli wolisz.

#### Ustawienia zaawansowane

- **Przekieruj stare adresy URL:**

  - **Co robi to ustawienie:** Jeśli włączone, moduł utworzy przekierowania 301 z adresu URL oryginalnego produktu (i potencjalnie adresów URL specyficznych dla kombinacji) do adresu URL nowego podzielonego produktu. Jest to kluczowe dla SEO.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączony:* Wyszukiwarki i użytkownicy uzyskujący dostęp do starych adresów URL zostaną automatycznie przekierowani na poprawną nową stronę produktu, zachowując wartość SEO i zapobiegając uszkodzonym linkom.
    - *Gdy wyłączony:* Stare adresy URL będą prowadzić do błędów 404 „Strona nie znaleziona”, szkodząc Twojemu SEO i doświadczeniu użytkownika.
  - **Zalecana wartość:** TAK.
  - **Scenariusz/przykład sprzedawcy:** Podzieliłeś „T-shirt” na „T-shirt - Czerwony - Mały”. Jeśli klient lub wyszukiwarka spróbuje uzyskać dostęp do starej strony „T-shirtu”, zostanie automatycznie przekierowany na najbardziej odpowiednią nową stronę podzielonego produktu.
- **Wyczyść pamięć podręczną po podziale:**

  - **Co robi to ustawienie:** Automatycznie czyści pamięć podręczną PrestaShop po wykonaniu operacji podziału.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączony:* Zapewnia, że zmiany wprowadzone przez moduł (nowe produkty, przekierowania) są natychmiast widoczne w front office bez ręcznego czyszczenia pamięci podręcznej.
    - *Gdy wyłączony:* Może być konieczne ręczne wyczyszczenie pamięci podręcznej (Zaawansowane > Wydajność), aby zmiany były widoczne.
  - **Zalecana wartość:** TAK.
  - **Scenariusz/przykład sprzedawcy:** Właśnie podzieliłeś dużą liczbę produktów. Włączenie tego zapewnia, że Twoi klienci od razu zobaczą nowe listy produktów, bez konieczności ręcznego czyszczenia pamięci podręcznej.

### 1.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### AdminMySplitProductsController (Panel administracyjny > Moduły > Podziel kombinacje na osobne produkty > Zarządzaj podziałami)

Ten ekran zapewnia interfejs do inicjowania, zarządzania i cofania operacji podziału produktów.

- **Nazwa ekranu i lokalizacja w menu:** „Zarządzaj podziałami” (dostępne z głównej strony konfiguracji modułu lub potencjalnie nowej pozycji menu w „Katalogu” lub „Modułach”).
- **Dostępne akcje i ustawienia:**
  - **Wyszukiwanie i wybór produktu:** Pasek wyszukiwania i funkcja autouzupełniania do znajdowania konkretnych produktów, które chcesz podzielić.
  - **Przycisk „Podziel produkt”:** Inicjuje proces podziału dla wybranego produktu.
  - **Przycisk „Cofnij”:** Pozwala cofnąć poprzednią operację podziału dla konkretnego produktu, przywracając oryginalny produkt i usuwając podzielone.
  - **Tabela historii:** Lista wszystkich produktów, które zostały podzielone, pokazująca:
    - Oryginalna nazwa produktu
    - Data podziału
    - Liczba podzielonych kombinacji
    - Status (np. „Zakończono”, „Cofnięto”)
    - Przyciski akcji (np. „Cofnij”, „Wyświetl podzielone produkty”)
- **Efekt zmian:**
  - **Dzielenie produktu:** Tworzy nowe wpisy produktów w Twoim katalogu na podstawie kombinacji wybranego produktu i ustawień konfiguracji modułu (nazwy, adresy URL, obrazy itp.). Status oryginalnego produktu może ulec zmianie (np. zostanie wyłączony).
  - **Cofanie podziału:** Usuwa produkty utworzone podczas podziału i przywraca oryginalny produkt do stanu sprzed podziału (np. ponownie go włącza, przywraca jego kombinacje). Jest to potężna funkcja cofania.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. Użyj paska wyszukiwania, aby znaleźć produkt, który chcesz podzielić.
  2. Przejrzyj proponowane nazwy i adresy URL (jeśli dostępny jest podgląd).
  3. Kliknij „Podziel produkt”.
  4. Monitoruj tabelę historii pod kątem statusu.
  5. Jeśli popełnisz błąd lub zmienisz zdanie, użyj funkcji „Cofnij” z tabeli historii.

#### index.php (mysplitproducts/controllers/admin/index.php)

Ten plik prawdopodobnie służy jako symbol zastępczy lub podstawa dla kontrolerów administracyjnych modułu, zapewniając najlepsze praktyki bezpieczeństwa PrestaShop poprzez zapobieganie bezpośredniemu listowaniu katalogów. Nie reprezentuje on odrębnego ekranu dla użytkownika, ale jest częścią wewnętrznej struktury modułu.

### 1.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Włącz moduł | TAK | Główny przełącznik funkcjonalności modułu. |
|  | Tryb podziału | „Utwórz osobne produkty” | Jak obsługiwane są kombinacje (nowe produkty vs. wirtualne wyświetlanie). |
|  | Dziel tylko aktywne produkty | TAK | Przetwarzaj tylko aktywne produkty. |
|  | Akcja produktu źródłowego po podziale | „Wyłącz produkt źródłowy” | Co dzieje się z oryginalnym produktem. |
|  | Kopiuj obrazy produktów | TAK | Duplikuj obrazy do nowych podzielonych produktów. |
|  | Minimalna liczba kombinacji do podziału | 2 | Próg dla podziału produktów. |
|  | Szablon kreatora nazw | `[product_name] - [attribute_group_name]: [attribute_name]` | Definiuje nazwy nowych produktów. |
|  | Szablon kreatora URL | `[product_name]-[attribute_name]` | Definiuje przyjazne adresy URL nowych produktów. |
|  | Separator dla wielu atrybutów | `-` (dla URL), `,` (dla nazwy) | Znak do oddzielania wielu atrybutów. |
|  | Przekieruj stare adresy URL | TAK | Tworzy przekierowania 301 dla SEO. |
|  | Wyczyść pamięć podręczną po podziale | TAK | Automatycznie czyści pamięć podręczną PrestaShop. |
| **Zarządzaj podziałami (AdminMySplitProductsController)** | Wyszukiwanie i podział produktów | N/A | Znajdź i zainicjuj podział produktów. |
|  | Cofnij podział | N/A | Cofnij poprzednią operację podziału. |
|  | Tabela historii | N/A | Przeglądaj i zarządzaj przeszłymi operacjami podziału. |

## 2. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Po podzieleniu produktów nie widzę nowych produktów w moich kategoriach ani wynikach wyszukiwania.**

- **O:** Najczęstszą przyczyną jest buforowanie.
  - **Rozwiązanie:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop. Kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” i „Wyczyść pamięć podręczną” dla wszystkich pamięci podręcznych). Jeśli ustawienie modułu „Wyczyść pamięć podręczną po podziale” jest włączone, powinno to nastąpić automatycznie, ale czasami konieczne jest ręczne wyczyszczenie. Upewnij się również, że nowe produkty są ustawione jako „aktywne” i powiązane z kategoriami.

**P2: Moje stare adresy URL produktów pokazują teraz „Strona nie znaleziona” (błędy 404).**

- **O:** Zazwyczaj oznacza to, że funkcja przekierowania nie jest aktywna lub nie działa poprawnie.
  - **Rozwiązanie:** Przejdź do strony konfiguracji modułu i upewnij się, że „Przekieruj stare adresy URL” jest ustawione na TAK. Jeśli jest już włączone, wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność). Jeśli problem nadal występuje, sprawdź plik `.htaccess` serwera pod kątem wszelkich sprzecznych reguł przepisywania lub skontaktuj się z pomocą techniczną.

**P3: Nazwy lub adresy URL moich nowych podzielonych produktów wyglądają dziwnie lub nie są takie, jakich się spodziewałem.**

- **O:** Jest to kontrolowane przez ustawienia „Szablon kreatora nazw” i „Szablon kreatora URL”.
  - **Rozwiązanie:** Przejdź do strony konfiguracji modułu i przejrzyj te szablony. Upewnij się, że używasz poprawnych symboli zastępczych (`[product_name]`, `[attribute_name]`, `[attribute_group_name]`) i że separatory są odpowiednie. Najpierw możesz przetestować różne szablony na pojedynczym produkcie. Pamiętaj, aby wyczyścić pamięć podręczną po wprowadzeniu zmian w szablonach.

**P4: Niektóre produkty z kombinacjami nie zostały podzielone, mimo że zainicjowałem proces.**

- **O:** Sprawdź ustawienie „Minimalna liczba kombinacji do podziału” w konfiguracji modułu.
  - **Rozwiązanie:** Jeśli produkt ma mniej kombinacji niż ten próg, zostanie pominięty. Dostosuj to ustawienie, jeśli chcesz podzielić produkty z mniejszą liczbą wariacji. Upewnij się również, że „Dziel tylko aktywne produkty” nie uniemożliwia przetwarzania nieaktywnych produktów, jeśli taki jest Twój zamiar.

**P5: Co dzieje się z koszykami klientów, jeśli podzielę produkt, który już dodali?**

- **O:** Moduł jest zaprojektowany tak, aby radzić sobie z tym elegancko. Istniejące otwarte koszyki, które zawierają kombinację produktu, który został podzielony, zostaną zazwyczaj zaktualizowane, aby odzwierciedlić nowy, odrębny identyfikator produktu. Oznacza to, że koszyk klienta nadal będzie zawierał prawidłowy przedmiot, teraz połączony z jego nowym, indywidualnym wpisem produktu. Zawsze jednak najlepiej jest przeprowadzać podziały w okresach niskiego ruchu lub dokładnie testować.

## 3. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 3.1 Przegląd architektury

Moduł „Podziel kombinacje na osobne produkty” (`mysplitproducts`) jest zbudowany zgodnie z wzorcem MVC (Model-View-Controller) PrestaShop. W dużym stopniu wykorzystuje `ObjectModel` do trwałości danych, niestandardowy `AdminController` do interfejsu Panelu administracyjnego oraz zestaw dedykowanych klas usługowych do hermetyzacji złożonej logiki dzielenia produktów, nazywania i przekierowywania. Moduł rozszerza podstawową funkcjonalność PrestaShop poprzez dynamiczne tworzenie i zarządzanie encjami produktów, obsługę przepisywania adresów URL i integrację z menedżerem modułów. Opiera się na solidnym wewnętrznym systemie logowania i wzorcu wyszukiwania dla efektywnego pobierania danych.

### 3.2 Kontrolery (`controllers/`)

- **Kontrolery Front Office**: Brak jawnie zdefiniowanych w dostarczonym spisie. Logika wyświetlania w Front Office dla wirtualnych podziałów lub przekierowań jest prawdopodobnie obsługiwana za pomocą hooków w głównym pliku `mysplitproducts.php` lub poprzez nadpisywanie.
- **Kontrolery Panelu administracyjnego**:

  - `controllers/admin/AdminMySplitProductsController.php`
    - **Nazwa klasy i klasa nadrzędna:** `AdminMySplitProductsController` rozszerza `ModuleAdminController`.
    - **Nazwa zakładki i zarządzana encja:** Ten kontroler zarządza podstawową funkcjonalnością dzielenia i cofania produktów. Prezentuje widok siatki/zarządzania dla przetworzonych produktów i pozwala administratorom inicjować nowe podziały lub cofać istniejące. Współpracuje z klasami `MspSplitEngine`, `MspLogger` i `MspRedirector`.
    - **Odpowiedzialność:** Obsługuje wyświetlanie interfejsu „Zarządzaj podziałami”, przetwarza żądania AJAX dotyczące wyszukiwania produktów, inicjuje proces dzielenia produktów i zarządza operacjami cofania. Jest to centralny punkt dla zadań administracyjnych modułu.
  - `controllers/admin/index.php`
    - **Nazwa klasy i klasa nadrzędna:** N/A (nie jest plikiem klasy).
    - **Odpowiedzialność:** Jest to standardowy pusty plik `index.php` umieszczony w podkatalogach, aby zapobiec listowaniu katalogów, zwiększając bezpieczeństwo. Nie zawiera żadnej logiki funkcjonalnej dla modułu.

### 3.3 Klasy podstawowe i modele (`classes/`)

- `classes/index.php`
  - **Odpowiedzialność:** Standardowy pusty `index.php` dla bezpieczeństwa, zapobiegający listowaniu katalogów.
- `classes/MspAliasStore.php`
  - **Z jaką tabelą bazy danych współdziała:** Prawdopodobnie `ps_mysplitproducts_alias` (niestandardowa tabela) lub `ps_configuration` do przechowywania aliasów/przekierowań.
  - **Czy rozszerza ObjectModel:** Mało prawdopodobne, aby bezpośrednio rozszerzało `ObjectModel`, ale zarządza danymi związanymi z aliasami.
  - **Kluczowe metody publiczne i hermetyzowana logika biznesowa:** Zarządza mapowaniem między oryginalnymi identyfikatorami produktów/kombinacji a nowo utworzonymi identyfikatorami podzielonych produktów. Kluczowe dla funkcjonalności przekierowania i cofania.
- `classes/MspCatalog.php`
  - **Z jaką tabelą bazy danych współdziała:** `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_image`, `ps_image_shop`, `ps_stock_available` itp. (podstawowe tabele produktów PrestaShop).
  - **Czy rozszerza ObjectModel:** Nie, prawdopodobnie klasa usługowa.
  - **Kluczowe metody publiczne i hermetyzowana logika biznesowa:** Udostępnia metody do zapytywania i manipulowania podstawowymi danymi produktów PrestaShop. Używana przez `MspSplitEngine` do pobierania szczegółów produktów, kombinacji i aktualizowania statusów produktów.
- `classes/MspCombinationSearchProvider.php`
  - **Z jaką tabelą bazy danych współdziała:** `ps_product`, `ps_product_lang`, `ps_product_attribute`, `ps_attribute`, `ps_attribute_lang`, `ps_attribute_group`, `ps_attribute_group_lang`.
  - **Czy rozszerza ObjectModel:** Nie, prawdopodobnie klasa usługowa.
  - **Kluczowe metody publiczne i hermetyzowana logika biznesowa:** Zapewnia funkcjonalność wyszukiwania produktów i ich kombinacji, często używaną do funkcji autouzupełniania w kontrolerze administracyjnym.
- `classes/MspFinder.php`
  - **Z jaką tabelą bazy danych współdziała:** Różne tabele PrestaShop, w zależności od kontekstu wyszukiwania.
  - **Czy rozszerza ObjectModel:** Nie, prawdopodobnie klasa narzędziowa/usługowa.
  - **Kluczowe metody publiczne i hermetyzowana logika biznesowa:** Klasa ogólnego przeznaczenia do pobierania danych, abstrahująca wspólne zapytania do bazy danych dla produktów, atrybutów i innych encji potrzebnych modułowi.
- `classes/MspLogger.php`
  - **Z jaką tabelą bazy danych współdziała:** Prawdopodobnie `ps_mysplitproducts_log` (niestandardowa tabela).
  - **Czy rozszerza ObjectModel:** Tak, lub zarządza niestandardową tabelą bezpośrednio.
  - **Kluczowe metody publiczne i hermetyzowana logika biznesowa:** Rejestruje wszystkie operacje dzielenia i cofania, w tym znaczniki czasu, dotknięte produkty i status. Niezbędne dla tabeli historii w `AdminMySplitProductsController` i do debugowania.
- `classes/MspNameBuilder.php`
  - **Z jaką tabelą bazy danych współdziała:** N/A (czysta logika).
  - **Czy rozszerza ObjectModel:** Nie, klasa narzędziowa.
  - **Kluczowe metody publiczne i hermetyzowana logika biznesowa:** Implementuje logikę generowania nowych nazw produktów i przyjaznych adresów URL na podstawie skonfigurowanych szablonów (`MSP_NAME_BUILDER_TEMPLATE`, `MSP_URL_BUILDER_TEMPLATE`) i danych atrybutów.
- `classes/MspProductCloner.php`
  - **Z jaką tabelą bazy danych współdziała:** `ps_product`, `ps_product_lang`, `ps_product_shop`, `ps_category_product`, `ps_image`, `ps_image_shop`, `ps_stock_available` itp.
  - **Czy rozszerza ObjectModel:** Nie, klasa usługowa.
  - **Kluczowe metody publiczne i hermetyzowana logika biznesowa:** Główna klasa odpowiedzialna za duplikowanie produktu i jego powiązanych danych (obrazów, stanu magazynowego, kategorii, cech itp.) w celu utworzenia nowego, odrębnego produktu dla konkretnej kombinacji. Obsługuje złożony proces kopiowania danych między wieloma tabelami PrestaShop.
- `classes/MspRedirector.php`
  - **Z jaką tabelą bazy danych współdziała:** `ps_mysplitproducts_redirect` (niestandardowa tabela) lub `ps_url_rewrite` (podstawowa PrestaShop).
  - **Czy rozszerza ObjectModel:** Nie, klasa usługowa.
  - **Kluczowe metody publiczne i hermetyzowana logika biznesowa:** Zarządza tworzeniem i usuwaniem przekierowań 301 z oryginalnych adresów URL produktów/kombinacji do nowych adresów URL podzielonych produktów. Integruje się z systemem przepisywania adresów URL PrestaShop lub implementuje własną logikę przekierowań.
- `classes/MspSplitEngine.php`
  - **Z jaką tabelą bazy danych współdziała:** Koordynuje interakcje z `MspCatalog`, `MspProductCloner`, `MspNameBuilder`, `MspRedirector`, `MspLogger`.
  - **Czy rozszerza ObjectModel:** Nie, główna klasa usługowa orkiestratora.
  - **Kluczowe metody publiczne i hermetyzowana logika biznesowa:** Centralna klasa, która koordynuje cały proces dzielenia. Przyjmuje identyfikator produktu, pobiera jego kombinacje, używa `MspNameBuilder` do generowania nowych szczegółów, `MspProductCloner` do tworzenia nowych produktów, `MspRedirector` do adresów URL i `MspLogger` do rejestrowania operacji. Obsługuje również logikę cofania.

### 3.4 Zasoby JavaScript (`views/js/`)

- `lib/searchTool/views/js/autocomplete.js`
  - **Zakres:** Panel administracyjny.
  - **Jakie nasłuchiwacze zdarzeń wiąże:** Zdarzenia wejściowe na polach wyszukiwania.
  - **Jakie manipulacje DOM, wyskakujące okienka modalne, animacje lub wywołania zewnętrznych SDK stron trzecich wykonuje:** Zapewnia funkcję autouzupełniania dla pól wyszukiwania produktów w interfejsie administracyjnym, prawdopodobnie używając wywołań AJAX do `AdminMySplitProductsController` w celu pobrania sugestii produktów.
- `views/js/admin.js`
  - **Zakres:** Panel administracyjny.
  - **Jakie nasłuchiwacze zdarzeń wiąże:** Zdarzenia kliknięcia na przyciskach (np. „Podziel produkt”, „Cofnij”), wysyłanie formularzy.
  - **Jakie manipulacje DOM, wyskakujące okienka modalne, animacje lub wywołania zewnętrznych SDK stron trzecich wykonuje:** Obsługuje interaktywne elementy pulpitu `AdminMySplitProductsController`, w tym inicjowanie akcji podziału/cofania, aktualizowanie tabeli historii i wyświetlanie wskaźników ładowania lub komunikatów o sukcesie/błędzie.
- `views/js/configure.js`
  - **Zakres:** Panel administracyjny.
  - **Jakie nasłuchiwacze zdarzeń wiąże:** Zdarzenia zmiany na polach konfiguracji, wysyłanie formularzy.
  - **Jakie manipulacje DOM, wyskakujące okienka modalne, animacje lub wywołania zewnętrznych SDK stron trzecich wykonuje:** Zarządza głównym formularzem konfiguracji modułu. Może zawierać logikę pokazywania/ukrywania pól w zależności od innych wyborów (np. trybu podziału), walidacji formularza i zapisywania ustawień konfiguracji za pomocą AJAX.
- `views/js/listing.js`
  - **Zakres:** Front Office (dla trybu wirtualnego podziału).
  - **Jakie nasłuchiwacze zdarzeń wiąże:** Potencjalnie zdarzenia `prestashop.on` dla aktualizacji listy produktów, gotowości DOM.
  - **Jakie manipulacje DOM, wyskakujące okienka modalne, animacje lub wywołania zewnętrznych SDK stron trzecich wykonuje:** Jeśli tryb „wirtualnego podziału” jest aktywny, ten skrypt dynamicznie modyfikowałby listy produktów na stronach kategorii, wyszukiwania i innych, aby wyświetlać pojedyncze kafelki kombinacji. Może to obejmować klonowanie istniejących elementów produktu, aktualizowanie ich zawartości (nazwy, obrazu, ceny) i ponowne renderowanie części siatki produktów.

### 3.5 Arkusze stylów CSS (`views/css/`)

- `lib/searchTool/views/css/autocomplete.css`
  - **Zakres:** Stylizacja formularza administracyjnego w Panelu administracyjnym.
  - **Główne komponenty i kontenery interfejsu użytkownika, które stylizuje:** Style dla rozwijanej listy autouzupełniania, pól wprowadzania wyszukiwania i list sugestii w panelu administracyjnym.
  - **Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim motywie:** `.autocomplete-suggestions`, `.autocomplete-suggestion`, `.autocomplete-selected`.
- `views/css/admin.css`
  - **Zakres:** Stylizacja formularza administracyjnego w Panelu administracyjnym.
  - **Główne komponenty i kontenery interfejsu użytkownika, które stylizuje:** Ogólna stylizacja stron konfiguracji modułu i pulpitu „Zarządzaj podziałami”, w tym tabel, przycisków, elementów formularzy i wskaźników statusu.
  - **Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim motywie:** `.mysplitproducts-config`, `.mysplitproducts-dashboard`, `.mysplitproducts-table`, `.mysplitproducts-status-success`, `.mysplitproducts-status-error`.

### 3.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**: Brak jawnie wymienionych, ale moduł może używać hooków do wyświetlania w Front Office w trybie wirtualnego podziału (np. `displayProductList`, `displayProductExtraContent`), które byłyby obsługiwane przez główny plik `mysplitproducts.php`.
- **Szablony administracyjne (`views/templates/admin/`)**:
  - `views/templates/admin/configure_shell.tpl`
    - **Cel:** Ten szablon prawdopodobnie służy jako główny wrapper lub powłoka dla strony konfiguracji modułu, w tym ustawień ogólnych i ewentualnie zakładek lub sekcji dla innych ustawień. Zapewnia ogólny układ dla `getContent()`.
  - `views/templates/admin/dashboard.tpl`
    - **Cel:** Ten szablon renderuje pulpit „Zarządzaj podziałami”, w tym pole wyszukiwania produktów, przycisk „Podziel produkt” i tabelę historii operacji podziału. Jest to widok dla `AdminMySplitProductsController`.
- **Szablony Front Office (`views/templates/front/`)**: Brak jawnie wymienionych. Renderowanie Front Office dla wirtualnych podziałów prawdopodobnie obejmowałoby modyfikację istniejących szablonów motywu za pomocą hooków lub nadpisywania, lub dynamiczne wstrzykiwanie treści za pomocą JavaScript (`listing.js`).

### 3.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - `ps_mysplitproducts_log`: Przechowuje historię wszystkich operacji podziału i cofania, w tym `id_product_original`, `id_product_split`, `action` (podziel/cofnij), `date_add`, `status`.
  - `ps_mysplitproducts_redirect`: Przechowuje mapowania przekierowań 301 ze starych adresów URL na nowe adresy URL podzielonych produktów, w tym `old_url`, `new_url`, `id_product_original`, `id_product_split`.
  - `ps_mysplitproducts_alias`: Przechowuje mapowania między oryginalnymi identyfikatorami produktów/kombinacji a nowymi identyfikatorami podzielonych produktów, kluczowe dla wewnętrznych wyszukiwań i cofania.
  - Rekordy konfiguracji przechowywane w `ps_configuration`:
    - `MSP_MODE`: (int) 0 dla wirtualnego, 1 dla rzeczywistego podziału.
    - `MSP_ACTIVE_ONLY`: (bool) Dziel tylko aktywne produkty.
    - `MSP_SOURCE_ACTION`: (int) Akcja dla produktu źródłowego (wyłącz, zachowaj aktywny, usuń).
    - `MSP_IMAGE_COPY`: (bool) Kopiuj obrazy do nowych produktów.
    - `MSP_MIN_COMBINATIONS`: (int) Minimalna liczba kombinacji do podziału.
    - `MSP_NAME_BUILDER_TEMPLATE`: (string) Szablon dla nazw nowych produktów.
    - `MSP_URL_BUILDER_TEMPLATE`: (string) Szablon dla adresów URL nowych produktów.
    - `MSP_SEPARATOR_MULTIPLE_ATTRIBUTES`: (string) Separator dla wielu atrybutów.
    - `MSP_REDIRECT_OLD_URLS`: (bool) Włącz przekierowania 301.
    - `MSP_CLEAR_CACHE_AFTER_SPLIT`: (bool) Automatycznie czyść pamięć podręczną.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Potencjalnie wstrzykuje CSS/JS dla wirtualnego podziału w Front Office lub metatagi dla SEO. |
| `displayBackOfficeHeader` | W sekcji `<head>` każdej strony Panelu administracyjnego. | Wstrzykuje CSS/JS dla stron administracyjnych modułu (`admin.css`, `admin.js`, `autocomplete.css`, `autocomplete.js`). |
| `actionProductUpdate` | Po zaktualizowaniu produktu. | Potencjalnie wyzwala ponowną ocenę podziału lub aktualizacje związane z podzielonymi produktami. |
| `actionProductDelete` | Po usunięciu produktu. | Obsługuje czyszczenie podzielonych produktów lub przekierowań, jeśli oryginalny produkt zostanie usunięty. |
| `actionProductSave` | Przed lub po zapisaniu produktu. | Przechwytuje zapisy produktów w celu zarządzania podzielonymi produktami lub powiązanymi danymi. |
| `actionObjectProductAddAfter` | Po dodaniu nowego produktu. | Potencjalnie wyzwala podział dla nowo dodanych produktów, jeśli skonfigurowano. |
| `actionObjectProductUpdateAfter` | Po zaktualizowaniu produktu. | Aktualizuje powiązane podzielone produkty lub przekierowania. |
| `actionObjectProductDeleteAfter` | Po usunięciu produktu. | Czyści powiązane podzielone produkty i przekierowania. |
| `displayProductList` | Gdy renderowana jest lista produktów (kategoria, wyszukiwanie itp.). | **Kluczowe dla trybu wirtualnego podziału.** Modyfikuje listę produktów, aby wyświetlać pojedyncze kafelki kombinacji. |
| `displayProductExtraContent` | Na stronie produktu, poniżej głównej zawartości. | Może być używany do wyświetlania linków do innych kombinacji lub komunikatu o podzielonych produktach. |
| `displayAdminProductsExtra` | Na stronie edycji produktu w Panelu administracyjnym. | Dodaje niestandardową zakładkę lub sekcję do strony edycji produktu w celu zarządzania podziałami związanymi z tym konkretnym produktem. |
| `actionAdminProductsListingResultsModifier` | Modyfikuje wyniki listy produktów w Panelu administracyjnym. | Dostosowuje listę produktów, aby pokazać/ukryć oryginalne produkty lub wyróżnić podzielone produkty. |
| `actionFrontControllerSetMedia` | Przed renderowaniem szablonu przez kontroler Front Office. | Rejestruje JavaScript (`listing.js`) i CSS Front Office dla trybu wirtualnego podziału. |
| `moduleRoutes` | Podczas inicjalizacji routingu URL. | Rejestruje niestandardowe trasy dla podzielonych produktów lub przekierowań. |

## 4. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i kompleksowe wsparcie, zapoznaj się ze swoim kontem klienta na MyPresta.eu.

- **Aktualizacje modułu:** Zaloguj się na swoje konto pod adresem [MyPresta.eu Historia zamówień i pobieranie](https://mypresta.eu/my-account/orders/), aby pobrać najnowszą wersję modułu „Podziel kombinacje na osobne produkty”.
- **Wsparcie techniczne:** Jeśli napotkasz jakiekolwiek problemy lub masz pytania, które nie zostały omówione w tym przewodniku, otwórz zgłoszenie do pomocy technicznej za pośrednictwem swojego konta klienta MyPresta.eu. Nasz zespół ekspertów jest gotowy do pomocy.
