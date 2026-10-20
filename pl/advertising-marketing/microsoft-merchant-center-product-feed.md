---
title: "Microsoft Merchant Center Product Feed - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop Microsoft Merchant Center Product Feed od MyPresta.eu."
sidebar:
  label: "Microsoft Merchant Center Product Feed - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Microsoft Merchant Center Product Feed na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-merchant-center-product-feed.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/microsoft-merchant-center-product-feed/)
>
> ---


# Microsoft Merchant Center Product Feed

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Twój serwer musi być w stanie wykonywać zadania cron do automatycznego generowania pliku danych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony konfiguracji modułu. Tutaj ustawisz ogólne zachowanie i uzyskasz dostęp do narzędzi zarządzania plikami danych.

#### Ustawienia ogólne

Ta sekcja zazwyczaj obejmuje ustawienia globalne, które wpływają na działanie modułu i generowanie plików danych.

- **Do czego służy to ustawienie:** Są to podstawowe ustawienia, które definiują sposób przygotowania danych produktów dla Microsoft Merchant Center. Zazwyczaj znajdziesz opcje wyboru języka, waluty i kraju dla pliku danych, a także ogólne preferencje eksportu.
- **Efekt zmiany tego ustawienia:**
  - *Język:* Określa, która wersja językowa nazw produktów, opisów i kategorii zostanie uwzględniona w pliku danych. Kluczowe dla targetowania na konkretne rynki międzynarodowe.
  - *Waluta:* Ustawia walutę dla wszystkich cen w pliku danych. Musi odpowiadać walucie skonfigurowanej na Twoim koncie Microsoft Merchant Center dla kraju docelowego.
  - *Kraj:* Określa kraj docelowy dla pliku danych. Wpływa to na zasady podatkowe, ustawienia wysyłki i inne wymagania specyficzne dla kraju w Microsoft Merchant Center.
  - *Inne opcje eksportu:* Mogą obejmować ustawienia dotyczące obsługi wariantów produktów, wykluczania niektórych kategorii lub definiowania sposobu eksportowania określonych atrybutów (takich jak rozmiar lub kolor).
- **Zalecana wartość:**
  - *Język, Waluta, Kraj:* Wybierz podstawowy język, walutę i kraj, na które kierujesz swoje reklamy Microsoft Shopping Ads. Jeśli reklamujesz się w wielu krajach/językach, prawdopodobnie utworzysz oddzielne pliki danych dla każdego z nich.
  - *Inne opcje:* Postępuj zgodnie z zaleceniami modułu lub dostosuj je w oparciu o swój konkretny katalog produktów i strategię reklamową.
- **Scenariusz/przykład sprzedawcy:** Jeśli sprzedajesz we Francji, a domyślny język Twojego sklepu to francuski, wybierzesz francuski dla języka, EUR dla waluty i Francję dla kraju. Jeśli sprzedajesz również w Niemczech, utworzysz oddzielny plik danych skonfigurowany dla języka niemieckiego, waluty EUR i Niemiec jako kraju.

#### Zarządzanie i generowanie plików danych

Ta sekcja zapewnia dostęp do tworzenia, zarządzania i generowania plików danych produktów.

- **Do czego służy to ustawienie:** To serce modułu, umożliwiające definiowanie i generowanie rzeczywistych plików danych produktów. Zazwyczaj znajdziesz opcje tworzenia nowych plików danych, przeglądania istniejących i wyzwalania procesu generowania.
- **Efekt zmiany tego ustawienia:**
  - *Tworzenie nowego pliku danych:* Inicjuje proces konfiguracji nowego pliku danych produktów z własnymi specyficznymi ustawieniami (język, waluta, kategorie itp.).
  - *Generowanie pliku danych:* Przetwarza dane produktów z PrestaShop i tworzy plik CSV, XML lub TSV, który prześlesz do Microsoft Merchant Center. Ten plik zawiera wszystkie atrybuty produktów w formacie wymaganym przez Microsoft.
  - *URL Cron:* Udostępnia specjalny adres internetowy, który po odwiedzeniu automatycznie wyzwala generowanie pliku danych. Jest to niezbędne do ustawienia automatycznych codziennych lub godzinowych aktualizacji pliku danych produktów bez ręcznej interwencji.
- **Zalecana wartość:**
  - Utwórz co najmniej jeden plik danych dla swojego głównego rynku docelowego.
  - Skonfiguruj zadanie cron za pomocą podanego adresu URL, aby zapewnić regularne aktualizowanie pliku danych produktów (np. codziennie) o najnowsze informacje o produktach (poziomy zapasów, ceny, nowe produkty).
- **Scenariusz/przykład sprzedawcy:** Właśnie wprowadziłeś nową linię produktów. Dzięki codziennemu zadaniu cron, Twoje reklamy Microsoft Shopping Ads automatycznie odzwierciedlą te nowe produkty i ich aktualne poziomy zapasów następnego dnia, bez konieczności ręcznego ponownego przesyłania pliku danych.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### AdminExportProductsFeedMicrosoftController (Panel administracyjny > Microsoft Merchant Center > Eksportuj plik danych produktów)

Jest to główny dedykowany ekran do zarządzania szczegółami plików danych produktów. Uzyskasz do niego dostęp poprzez nową pozycję menu dodaną przez moduł, prawdopodobnie w sekcji „Katalog” lub nowej sekcji „Microsoft Merchant Center”.

- **Nazwa ekranu i lokalizacja w menu:** **Panel administracyjny > Microsoft Merchant Center > Eksportuj plik danych produktów** (lub podobnie, w zależności od wersji modułu i struktury menu PrestaShop).
- **Dostępne działania i ustawienia:** Ten ekran służy do definiowania konkretnej zawartości i mapowania dla każdego z plików danych produktów. Zazwyczaj zobaczysz listę istniejących plików danych, z opcjami „Dodaj nowy plik danych” lub „Edytuj” istniejący. Podczas dodawania/edycji skonfigurujesz:
  - **Nazwa pliku danych:** Opisowa nazwa dla Twojego pliku danych (np. „Francja - plik francuski”, „USA - plik angielski”).
  - **Kraj docelowy:** Kraj, dla którego przeznaczony jest ten plik danych (np. Francja, Stany Zjednoczone). Wpływa to na walutę, język i zasady podatkowe.
  - **Język treści:** Język danych produktów w tym pliku danych (np. francuski, angielski).
  - **Waluta:** Waluta używana dla cen w tym pliku danych (np. EUR, USD).
  - **Format pliku:** Wybierz między CSV, XML lub TSV, zgodnie z wymaganiami Microsoft Merchant Center.
  - **Mapowanie kategorii:** Jest to kluczowa sekcja, w której mapujesz kategorie PrestaShop do taksonomii produktów Microsoftu. Pomaga to firmie Microsoft zrozumieć, czym są Twoje produkty i wyświetlać je w odpowiednich wyszukiwaniach.
  - **Filtrowanie produktów:** Opcje włączania/wykluczania konkretnych produktów lub całych kategorii z pliku danych.
  - **Mapowanie atrybutów:** Mapuj atrybuty produktów PrestaShop (takie jak rozmiar, kolor, materiał) do wymaganych atrybutów Microsoftu (np. `size`, `color`, `material`).
  - **Etykiety niestandardowe:** Zdefiniuj do 5 etykiet niestandardowych (`custom_label_0` do `custom_label_4`), aby segmentować produkty dla strategii licytacji w reklamach Microsoft Ads.
  - **Dostępność i stan:** Ustawienia definiujące sposób eksportowania dostępności produktów (w magazynie, brak w magazynie, przedsprzedaż) i stanu (nowy, używany, odnowiony).
  - **GTIN (Globalny Numer Jednostki Handlowej):** Ustawienia eksportu kodów EAN/UPC jako GTIN.
  - **Marka:** Sposób eksportowania marek produktów.
  - **Opis:** Opcje eksportu opisów produktów, często z konwersją na zwykły tekst.
  - **Linki do zdjęć:** Sposób linkowania zdjęć produktów.
  - **Cena i cena promocyjna:** Sposób eksportowania cen regularnych i promocyjnych, w tym kwestie podatkowe.
  - **URL Cron:** Unikalny adres URL dla tego konkretnego pliku danych, którego użyjesz do automatycznych aktualizacji.
- **Efekt zmian:**
  - Zmiany tutaj bezpośrednio wpływają na zawartość i strukturę wygenerowanego pliku danych produktów. Nieprawidłowe ustawienia mogą prowadzić do odrzucenia produktów w Microsoft Merchant Center.
  - Prawidłowe mapowanie kategorii zapewnia, że Twoje produkty pojawiają się w odpowiednich kategoriach zakupowych w Bing.
  - Dokładne dane o cenach i dostępności zapobiegają frustracji klientów i odrzucaniu reklam.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. **Początkowa konfiguracja:** Utwórz plik danych dla każdej kombinacji kraju docelowego/języka, w której się reklamujesz. Ostrożnie mapuj swoje kategorie do taksonomii Microsoftu.
  2. **Przegląd atrybutów:** Upewnij się, że wszystkie krytyczne atrybuty (GTIN, marka, cena, dostępność, linki do zdjęć) są poprawnie zmapowane i wyeksportowane.
  3. **Konfiguracja zadań Cron:** Wdróż dostarczone adresy URL Cron na swoim serwerze hostingowym, aby zautomatyzować codzienne (lub częstsze) generowanie plików danych. Jest to kluczowe dla utrzymania świeżości danych produktów.
  4. **Monitorowanie Microsoft Merchant Center:** Regularnie sprawdzaj swoje konto Microsoft Merchant Center pod kątem odrzuceń produktów lub ostrzeżeń i dostosuj ustawienia modułu w PrestaShop w razie potrzeby.
  5. **Aktualizacje produktów:** Podczas dodawania nowych produktów lub wprowadzania znaczących zmian w istniejących, upewnij się, że zadanie cron działa, lub ręcznie wygeneruj plik danych, jeśli wymagana jest natychmiastowa aktualizacja.

#### index.php (mmcfeed/controllers/admin/index.php)

Ten kontroler prawdopodobnie służy jako pulpit nawigacyjny lub ogólny widok zarządzania modułem w Panelu administracyjnym PrestaShop.

- **Nazwa ekranu i lokalizacja w menu:** Prawdopodobnie część głównej sekcji menu „Microsoft Merchant Center”, być może domyślna strona docelowa.
- **Dostępne działania i ustawienia:** Ten ekran prawdopodobnie wyświetla przegląd skonfigurowanych plików danych, datę ich ostatniego wygenerowania, status i szybkie linki do ich edycji lub generowania. Może również wyświetlać ogólny status modułu lub ważne alerty.
- **Efekt zmian:** Ten widok zapewnia szybki przegląd konfiguracji pliku danych. Działania tutaj (takie jak kliknięcie „Generuj plik danych”) wyzwolą proces generowania pliku danych.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Użyj tego ekranu jako szybkiego pulpitu nawigacyjnego do monitorowania stanu plików danych produktów. Jeśli musisz ręcznie wyzwolić aktualizację pliku danych, to właśnie tutaj to zrobisz.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Język docelowy | Twój podstawowy język sklepu | Określa język nazw produktów, opisów itp. |
| | Waluta docelowa | Twoja podstawowa waluta sklepu | Ustawia walutę dla wszystkich cen w pliku danych. |
| | Kraj docelowy | Twój główny rynek docelowy | Wpływa na podatki, wysyłkę i zasady specyficzne dla kraju. |
| | URL Cron | Dostarczony przez moduł | Automatyzuje generowanie pliku danych w zaplanowanych odstępach czasu. |
| **AdminExportProductsFeedMicrosoftController** | Nazwa pliku danych | Opisowa (np. „Francja - FR”) | Identyfikuje konkretny plik danych. |
| | Format pliku | CSV, XML lub TSV | Wybierz na podstawie wymagań Microsoft Merchant Center. |
| | Mapowanie kategorii | Mapuj PrestaShop do taksonomii Microsoftu | Zapewnia, że produkty pojawiają się w prawidłowych kategoriach zakupowych. |
| | Filtrowanie produktów | Na podstawie Twojej strategii | Włączaj/wykluczaj konkretne produkty lub kategorie. |
| | Mapowanie atrybutów | Mapuj atrybuty PrestaShop do atrybutów Microsoftu | Dostarcza szczegółowych informacji o produktach dla reklam. |
| | Etykiety niestandardowe (0-4) | W razie potrzeby dla kampanii reklamowych | Segmentuj produkty dla strategii licytacji. |
| | Eksport GTIN | Włączony, jeśli dostępny | Eksportuje EAN/UPC do identyfikacji produktu. |
| | Data dostępności | Włączona, jeśli dotyczy | Eksportuje datę dostępności produktu dla zamówień przedpremierowych. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje produkty nie pojawiają się w reklamach Microsoft Shopping Ads. Co powinienem sprawdzić?**
O:

1. **Status przesyłania pliku danych:** Najpierw sprawdź swoje konto Microsoft Merchant Center, aby upewnić się, że plik danych został pomyślnie przesłany i przetworzony bez większych błędów.
2. **Odrzucenia produktów:** Poszukaj wszelkich odrzuceń produktów w sekcji „Diagnostyka” w Microsoft Merchant Center. Pokażą Ci one dokładnie, dlaczego produkty się nie wyświetlają. Typowe przyczyny to brak GTIN, nieprawidłowe linki do zdjęć lub naruszenia zasad.
3. **Konfiguracja modułu:** Sprawdź, czy ustawienia modułu (język, waluta, kraj, mapowanie kategorii) są poprawne i zgodne z ustawieniami Twojego konta Microsoft Merchant Center.
4. **Generowanie pliku danych:** Upewnij się, że plik danych jest poprawnie generowany przez moduł. Spróbuj ręcznie go wygenerować i sprawdzić plik wyjściowy.
5. **Kampanie reklamowe:** Potwierdź, że Twoje kampanie Microsoft Ads są aktywne, prawidłowo ukierunkowane i połączone z prawidłowym plikiem danych produktów.

**P: Moje ceny produktów lub poziomy zapasów są nieaktualne w reklamach Microsoft Shopping Ads.**
O: Zazwyczaj oznacza to, że Twój plik danych produktów nie jest aktualizowany wystarczająco często.

1. **Zadanie Cron:** Upewnij się, że zadanie cron jest poprawnie skonfigurowane na Twoim serwerze hostingowym i działa z żądaną częstotliwością (np. codziennie). Moduł udostępnia unikalny adres URL do tego celu.
2. **Ręczne generowanie:** Jeśli wprowadziłeś pilne zmiany, możesz ręcznie wygenerować plik danych ze strony konfiguracji modułu i ponownie przesłać go do Microsoft Merchant Center (jeśli nie używasz zaplanowanych pobrań).

**P: Niektóre z moich produktów brakuje w pliku danych.**
O:

1. **Wykluczenie kategorii:** Sprawdź, czy kategorie zawierające te produkty nie zostały przypadkowo wykluczone w ustawieniach modułu.
2. **Status produktu:** Upewnij się, że produkty są aktywne, widoczne i dostępne w magazynie w Twoim sklepie PrestaShop. Produkty oznaczone jako „wyłączone” lub „brak w magazynie” (w zależności od Twoich ustawień) mogą zostać wykluczone.
3. **Specyficzne filtry:** Przejrzyj wszelkie specyficzne filtry produktów, które mogłeś zastosować w konfiguracji modułu.

**P: Jak mapować kategorie PrestaShop do taksonomii produktów Microsoftu?**
O: Na ekranie konfiguracji pliku danych modułu znajdzie się sekcja „Mapowanie kategorii”. Zazwyczaj zobaczysz listę swoich kategorii PrestaShop. Dla każdej z nich będziesz musiał wybrać najbardziej odpowiednią kategorię z predefiniowanej listy taksonomii Microsoftu. Jest to kluczowy krok dla trafności reklam. Poświęć czas, aby zrobić to poprawnie.

**P: Mój niestandardowy motyw powoduje problemy z wyświetlaniem interfejsu administracyjnego modułu.**
O: Chociaż moduł nie ma wpływu na front-office, jego interfejs back-office może czasami kolidować z mocno dostosowanymi motywami administracyjnymi.

1. **Wyczyść pamięć podręczną:** Najpierw spróbuj wyczyścić pamięć podręczną Smarty w PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).
2. **Domyślny motyw:** Tymczasowo przełącz motyw back-office na domyślny motyw PrestaShop, aby sprawdzić, czy problem nadal występuje. Jeśli problem zostanie rozwiązany, konflikt dotyczy Twojego niestandardowego motywu administracyjnego.
3. **Skontaktuj się z pomocą techniczną:** Jeśli problem nadal występuje, zbierz zrzuty ekranu i szczegóły i skontaktuj się z pomocą techniczną MyPresta.eu.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Microsoft Merchant Center Product Feed` (`mmcfeed`) stosuje standardową architekturę modułu PrestaShop, wykorzystując głównie kontrolery administracyjne do zarządzania back-office oraz kontrolery front-office do generowania pliku danych produktów za pomocą zadań cron. Nie wprowadza nowych klas `ObjectModel`, ale raczej odpytuje istniejące dane produktów PrestaShop i formatuje je zgodnie ze specyfikacjami Microsoft Merchant Center. Moduł w dużym stopniu opiera się na wartościach konfiguracyjnych przechowywanych w `ps_configuration` i wykorzystuje szablony Smarty do renderowania zarówno interfejsów administracyjnych, jak i potencjalnie części logiki generowania pliku danych (chociaż pliki danych są zazwyczaj generowane programowo).

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

- `mmcfeed/controllers/front/feed.php`
  - **Nazwa klasy i klasa nadrzędna:** `MmcfeedFeedModuleFrontController` rozszerzający `ModuleFrontController`.
  - **Odpowiedzialność:** Ten kontroler jest głównym punktem końcowym do generowania pliku danych produktów. Jest zaprojektowany do wywoływania za pomocą unikalnego adresu URL („URL cron”) do automatycznego generowania pliku danych. Obsługuje logikę odpytywania danych produktów, stosowania reguł filtrowania i mapowania zdefiniowanych w back-office oraz wyprowadzania pliku danych produktów w określonym formacie (CSV, XML, TSV). Zazwyczaj nie renderuje strony wizualnej, ale wyprowadza surowe dane.
- `mmcfeed/controllers/front/index.php`
  - **Nazwa klasy i klasa nadrzędna:** `MmcfeedIndexModuleFrontController` rozszerzający `ModuleFrontController`.
  - **Odpowiedzialność:** Jest to kontroler front-office zastępczy lub awaryjny. W wielu modułach `index.php` w katalogu kontrolera służy jako domyślny lub prosty punkt wejścia. Może przekierowywać lub po prostu zwracać pustą odpowiedź, jeśli nie zdefiniowano żadnej konkretnej akcji. Jego bezpośrednia rola funkcjonalna w generowaniu pliku danych jest prawdopodobnie minimalna w porównaniu do `feed.php`.

#### Kontrolery administracyjne Back-Office

- `mmcfeed/controllers/admin/AdminExportProductsFeedMicrosoft.php`
  - **Nazwa zakładki i zarządzana encja:** Zarządza konfiguracją i generowaniem poszczególnych plików danych produktów Microsoft Merchant Center. Tworzy nową pozycję menu w panelu administracyjnym PrestaShop.
  - **Odpowiedzialność:** Ten kontroler obsługuje operacje CRUD dla konfiguracji plików danych produktów. Wyświetla listę skonfigurowanych plików danych, umożliwia dodawanie nowych plików danych, edytowanie istniejących i wyzwalanie ich generowania. Przetwarza przesyłanie formularzy w celu zdefiniowania ustawień specyficznych dla pliku danych, takich jak kraj docelowy, język, waluta, format pliku, mapowanie kategorii, filtrowanie produktów i mapowanie atrybutów (np. `gtin`, `identifier_exists`, `title`, `availability`, `brand`, `link`, `image_link`, `description`, `product_type`, `condition`, `price`, `sale_price`, `tax rate`, `custom_label_0`, `google_product_category`). Współdziała z `ps_configuration` w celu przechowywania tych ustawień i orkiestruje pobieranie i formatowanie danych dla procesu generowania pliku danych.
- `mmcfeed/controllers/admin/index.php`
  - **Nazwa zakładki i zarządzana encja:** Prawdopodobnie pulpit nawigacyjny lub strona przeglądu modułu w panelu administracyjnym PrestaShop.
  - **Odpowiedzialność:** Ten kontroler prawdopodobnie służy jako główny punkt wejścia do interfejsu administracyjnego modułu, zapewniając podsumowanie skonfigurowanych plików danych, ich statusu i szybkich działań. Może renderować szablon podobny do pulpitu nawigacyjnego (`dashboard.tpl`), aby zapewnić przegląd aktywności modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dostarczone informacje wskazują, że w katalogu `classes/` nie ma niestandardowych klas ani modeli. Sugeruje to, że moduł działa głównie poprzez bezpośrednie odpytywanie podstawowych klas `ObjectModel` PrestaShop, takich jak `Product`, `Category`, `Language`, `Currency` itp., oraz `ps_configuration` dla swoich ustawień. Logika przetwarzania danych i generowania pliku danych jest prawdopodobnie hermetyzowana w głównym pliku modułu `mmcfeed.php` oraz w kontrolerach administracyjnych/front-office.

### 4.4 Zasoby JavaScript (`views/js/`)

- `mmcfeed/lib/searchTool/views/js/autocomplete.js`
  - **Zakres:** Back-office.
  - **Odpowiedzialność:** Zapewnia funkcjonalność autouzupełniania, prawdopodobnie do wyszukiwania produktów, kategorii lub atrybutów w formularzach konfiguracyjnych modułu. Zwiększa to komfort użytkowania podczas mapowania kategorii lub filtrowania produktów. Wiąże się z polami wejściowymi i wykonuje żądania AJAX w celu pobrania sugestii.
- `mmcfeed/views/js/admin-app.js`
  - **Zakres:** Back-office.
  - **Odpowiedzialność:** Jest to główny plik JavaScript dla interfejsu back-office modułu. Obsługuje różne elementy interaktywne, walidacje formularzy, dynamiczne ładowanie treści (np. modale Fancybox do wyboru kategorii) i wywołania AJAX związane z zapisywaniem konfiguracji lub wyzwalaniem generowania pliku danych. Prawdopodobnie wiąże słuchaczy zdarzeń z przyciskami, selektorami i polami wejściowymi w formularzach kontrolera `AdminExportProductsFeedMicrosoft`.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `mmcfeed/lib/searchTool/views/css/autocomplete.css`
  - **Zakres:** Stylizacja formularzy administracyjnych back-office.
  - **Odpowiedzialność:** Stylizuje rozwijane listy autouzupełniania i pola wejściowe używane przez skrypt `autocomplete.js`, zapewniając spójny i przyjazny dla użytkownika wygląd w panelu administracyjnym PrestaShop.
- `mmcfeed/views/admin-theme.css`
  - **Zakres:** Stylizacja formularzy administracyjnych back-office.
  - **Odpowiedzialność:** Zapewnia ogólne dostosowania stylów i nadpisania dla stron back-office modułu, aby bezproblemowo integrować się z motywem administracyjnym PrestaShop. Może definiować style dla układu, przycisków, tabel i elementów formularzy specyficznych dla modułu.
- `mmcfeed/views/css/admin-app.css`
  - **Zakres:** Stylizacja formularzy administracyjnych back-office.
  - **Odpowiedzialność:** Zawiera specyficzne style dla niestandardowych komponentów interfejsu użytkownika modułu i układów w panelu administracyjnym, takich jak interfejsy mapowania kategorii, listy wykluczeń produktów lub elementy pulpitu nawigacyjnego. Działa w połączeniu z `admin-theme.css`, aby zapewnić wizualną tożsamość modułu w back-office.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**: Brak wyraźnie wymienionych, co wskazuje, że moduł nie renderuje treści bezpośrednio w standardowych hookach front-office.
- **Szablony administracyjne (`views/templates/admin/`)**:
  - `mmcfeed/views/templates/admin/dashboard.tpl`: Prawdopodobnie główny szablon pulpitu nawigacyjnego renderowany przez `controllers/admin/index.php`, zapewniający przegląd modułu i jego skonfigurowanych plików danych.
  - `mmcfeed/views/templates/admin/feeds.tpl`: Prawdopodobnie renderuje listę plików danych produktów zarządzanych przez `AdminExportProductsFeedMicrosoftController`, pokazując ich status, datę ostatniego wygenerowania i działania.
  - `mmcfeed/views/templates/admin/form-chrome.tpl`: Ogólny szablon do opakowywania formularzy w interfejsie administracyjnym PrestaShop, zapewniający spójną stylizację i strukturę (np. nagłówek, stopka, przyciski zapisu).
  - `mmcfeed/views/templates/admin/layout.tpl`: Podstawowy szablon układu dla stron administracyjnych modułu, definiujący ogólną strukturę, w tym nagłówki, menu i obszary treści.
- **Inne szablony (`views/`)**:
  - `mmcfeed/lib/searchTool/views/scripts.tpl`: Zawiera kod JavaScript lub włączenia skryptów związane z narzędziem wyszukiwania/funkcją autouzupełniania.
  - `mmcfeed/views/categories-fancybox.tpl`: Renderuje zawartość modalu Fancybox używanego do wyboru lub mapowania kategorii, prawdopodobnie zapewniając strukturę drzewiastą dla łatwej nawigacji.
  - `mmcfeed/views/category_taxonomy.tpl`: Częściowy szablon używany w `categories-fancybox.tpl` lub głównym formularzu konfiguracji pliku danych do wyświetlania i zarządzania mapowaniem kategorii PrestaShop do taksonomii Microsoftu.
  - `mmcfeed/views/exclude-products.tpl`: Renderuje interfejs do wybierania i zarządzania produktami, które mają zostać wykluczone z pliku danych.
  - `mmcfeed/views/google_lang_links.tpl`: Ta nazwa szablonu jest intrygująca dla modułu Microsoftu. Może to być pozostałość po module Google Merchant Center lub ogólny komponent do obsługi linków specyficznych dla języka, potencjalnie dla samych adresów URL plików danych.
  - `mmcfeed/views/returnAlert.tpl`: Ogólny szablon do wyświetlania komunikatów o sukcesie lub błędach użytkownikowi w back-office.
  - `mmcfeed/views/script-fancybox.tpl`: Zawiera kod JavaScript lub włączenia skryptów specjalnie dla biblioteki Fancybox, używanej do wyskakujących okien modalnych.
  - `mmcfeed/views/script.tpl`: Ogólny szablon włączenia skryptu, potencjalnie dla zmiennych JavaScript lub inicjalizacji w całym module.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy niestandardowych tabel SQL na podstawie dostarczonych informacji.
  - Wszystkie konfiguracje modułu są przechowywane w tabeli `ps_configuration`, używając kluczy z prefiksem `mmc_` (np. `mmc_pf_tree`, `mmc_mmcfeed_products`, `mmc_export_size_attribute`, `mmc_export_exclude_categories`, `mmc_export_availability_date`).
  - Współdziała ze standardowymi tabelami PrestaShop, takimi jak `ps_product`, `ps_product_lang`, `ps_category`, `ps_category_lang`, `ps_image`, `ps_stock_available`, `ps_attribute_group`, `ps_attribute`, `ps_feature`, `ps_feature_value`, `ps_manufacturer`, `ps_tax_rule` itp., w celu pobierania danych produktów.
- **Tabela zarejestrowanych hooków**:
  Moduł wykorzystuje głównie hooki back-office dla swojego interfejsu administracyjnego i potencjalnie hooki `action` dla logiki wewnętrznej. Hooki front-office nie są używane do renderowania treści, ale kontroler front-office modułu `feed.php` działa jako bezpośredni punkt końcowy dla usług zewnętrznych (takich jak zadania cron).

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` stron front-office. | *Nie używany do renderowania treści.* Jeśli zarejestrowany, prawdopodobnie do wewnętrznego ładowania JS/CSS, ale główną funkcją modułu jest generowanie pliku danych, a nie wyświetlanie front-office. |
| `displayRightColumn` | W prawej kolumnie stron front-office. | *Nie używany do renderowania treści.* |
| `displayLeftColumn` | W lewej kolumnie stron front-office. | *Nie używany do renderowania treści.* |
| `displayFooter` | W stopce stron front-office. | *Nie używany do renderowania treści.* |
| `displayAdminProductsExtra` | Na stronie edycji produktu w back-office. | *Potencjalnie używany* do dodania zakładki lub sekcji dla wykluczeń lub nadpisań specyficznych dla produktu w pliku danych. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny jest inicjowany i przed załadowaniem jego mediów (JS/CSS). | Używany do rejestrowania specyficznych dla modułu JavaScript (`admin-app.js`, `autocomplete.js`) i CSS (`admin-app.css`, `admin-theme.css`, `autocomplete.css`) dla interfejsu back-office. |
| `actionModuleInstall` | Podczas instalacji modułu. | Do tworzenia wpisów konfiguracyjnych w `ps_configuration` i potencjalnie rejestrowania zakładek administracyjnych. |
| `actionModuleUninstall` | Podczas deinstalacji modułu. | Do czyszczenia wpisów konfiguracyjnych i usuwania zakładek administracyjnych. |
| `actionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | *Mało prawdopodobne dla tego modułu.* Jeśli obecny, służyłby do śledzenia konwersji lub aktualizowania danych pliku danych na podstawie sprzedaży, ale nie jest to podstawowa funkcja generatora pliku danych. |
| `actionProductUpdate` | Po zaktualizowaniu produktu. | *Potencjalnie używany* do wyzwolenia flagi do regeneracji pliku danych lub do aktualizacji wewnętrznych pamięci podręcznych, jeśli moduł takie utrzymuje. |
| `actionProductAdd` | Po dodaniu nowego produktu. | *Potencjalnie używany* do wyzwolenia flagi do regeneracji pliku danych lub do aktualizacji wewnętrznych pamięci podręcznych. |
| `displayAdminNavBarBefore` | Przed głównym paskiem nawigacyjnym w back-office. | *Potencjalnie używany* do dodania szybkiego linku lub powiadomienia związanego z modułem. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). MyPresta.eu zapewnia dedykowane wsparcie dla wszystkich zakupionych modułów, zapewniając, że Twój sklep pozostaje aktualny i funkcjonalny.
"""
