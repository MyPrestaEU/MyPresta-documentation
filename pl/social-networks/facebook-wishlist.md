---
title: "Facebook Wishlist - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Facebook Wishlist od MyPresta.eu."
sidebar:
  label: "Facebook Wishlist - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook Wishlist na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-wishlist.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-wishlist/)
>
> ---


# Facebook Wishlist

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zwykle dostępne domyślnie. Brak specjalnych wymagań hostingowych poza standardową konfiguracją PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu Facebook Wishlist w Menedżerze modułów. Spowoduje to przejście do głównego ekranu konfiguracji.

#### **Identyfikator aplikacji Facebooka (Facebook App ID)**

- **Co robi to ustawienie:** Jest to unikalny identyfikator dostarczony przez Facebooka dla Twojej konkretnej aplikacji (w tym przypadku integracji Twojego sklepu PrestaShop z Facebookiem). Informuje Facebooka, która aplikacja żąda akcji listy życzeń.
- **Wpływ zmiany tego ustawienia:**
  - *Po poprawnym wprowadzeniu:* Przycisk „Dodaj do listy życzeń na Facebooku” będzie działał poprawnie, umożliwiając dodawanie produktów do osi czasu na Facebooku.
  - *Po niepoprawnym lub pustym wprowadzeniu:* Przycisk prawdopodobnie nie będzie działał lub Facebook wyświetli błąd, uniemożliwiając klientom dodawanie produktów do ich list życzeń.
- **Zalecana wartość:** To pole *musi* zawierać Twój prawidłowy identyfikator aplikacji Facebooka. Będziesz musiał utworzyć aplikację Facebooka na stronie [Facebook dla programistów](https://developers.facebook.com/), aby uzyskać ten identyfikator.
- **Scenariusz / przykład dla sprzedawcy:** Utworzyłeś aplikację Facebooka dla swojego sklepu, a Facebook nadał Ci identyfikator aplikacji, np. `123456789012345`. Wprowadziłbyś ten dokładny numer tutaj. Bez niego Facebook nie będzie wiedział, który sklep próbuje udostępniać treści.

#### **Sekret aplikacji Facebooka (Facebook App Secret)**

- **Co robi to ustawienie:** Jest to tajny klucz powiązany z Twoim identyfikatorem aplikacji Facebooka. Służy do bezpiecznej komunikacji między Twoim sklepem PrestaShop a serwerami Facebooka. Pomaga zweryfikować, czy żądania pochodzą z Twojej legalnej aplikacji.
- **Wpływ zmiany tego ustawienia:**
  - *Po poprawnym wprowadzeniu:* Nawiązana jest bezpieczna komunikacja, a moduł działa zgodnie z przeznaczeniem.
  - *Po niepoprawnym lub pustym wprowadzeniu:* Komunikacja z Facebookiem może się nie powieść, co prowadzi do błędów lub niedziałających funkcji listy życzeń.
- **Zalecana wartość:** To pole *musi* zawierać Twój prawidłowy sekret aplikacji Facebooka. Podobnie jak identyfikator aplikacji, uzyskujesz go z ustawień swojej aplikacji Facebooka na stronie [Facebook dla programistów](https://developers.facebook.com/). Zachowaj ten sekret w bezpiecznym miejscu i nigdy nie udostępniaj go publicznie.
- **Scenariusz / przykład dla sprzedawcy:** Po utworzeniu aplikacji Facebooka znajdziesz zarówno identyfikator aplikacji, jak i sekret aplikacji w panelu swojej aplikacji. Sekret może wyglądać jak długi ciąg liter i cyfr (np. `abcdef1234567890abcdef1234567890`). Wprowadź go dokładnie tak, jak podał Facebook.

#### **Adres URL strony Facebooka (Facebook Page URL)**

- **Co robi to ustawienie:** Umożliwia to połączenie oficjalnej strony Facebooka Twojego sklepu z funkcjonalnością listy życzeń. Kiedy klienci wchodzą w interakcję z listą życzeń, może ona czasami odwoływać się lub linkować do Twojej głównej strony Facebooka.
- **Wpływ zmiany tego ustawienia:**
  - *Po poprawnym wprowadzeniu:* Zwiększa widoczność marki na Facebooku i zapewnia bezpośredni link do Twojej oficjalnej strony.
  - *Po niepoprawnym lub pustym wprowadzeniu:* Moduł nadal będzie działał, ale możesz stracić okazję do skierowania użytkowników do Twojej głównej obecności na Facebooku.
- **Zalecana wartość:** Wprowadź pełny adres URL oficjalnej strony Facebooka Twojego sklepu (np. `https://www.facebook.com/TwojaNazwaSklepu`). Jeśli nie masz oficjalnej strony, możesz pozostawić to pole puste.
- **Scenariusz / przykład dla sprzedawcy:** Twój sklep ma stronę na Facebooku pod adresem `https://www.facebook.com/MyPrestaEu`. Wprowadzenie tego adresu URL tutaj zapewnia, że wszelkie udostępnianie w mediach społecznościowych związane z listą życzeń może potencjalnie skierować użytkowników do Twojej głównej strony marki na Facebooku.

#### **Pozycja przycisku (Position of the button)**

- **Co robi to ustawienie:** Kontroluje, gdzie przycisk „Dodaj do listy życzeń na Facebooku” pojawia się na stronach produktów.
- **Wpływ zmiany tego ustawienia:**
  - *Po ustawieniu na „Strona produktu” (Product page):* Przycisk zostanie wyświetlony w widocznym miejscu na stronie szczegółów produktu, zazwyczaj w pobliżu przycisku „Dodaj do koszyka”. Jest to najczęstsze i zalecane umiejscowienie.
  - *Po ustawieniu na inne opcje (np. „Nagłówek” (Header), „Kolumny” (Columns), „Stopka” (Footer)):* Moduł może próbować wyświetlić przycisk w tych obszarach, ale jego funkcjonalność jest przede wszystkim związana z konkretnymi informacjami o produkcie, co sprawia, że „Strona produktu” jest najbardziej logicznym wyborem. Inne pozycje mogą nie wyświetlać przycisku lub mogą nie działać poprawnie bez konkretnego kontekstu produktu.
- **Zalecana wartość:** **Strona produktu (Product page)**. Zapewnia to widoczność przycisku, gdy klienci aktywnie przeglądają produkt, który mogą chcieć dodać do listy życzeń.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby klienci łatwo znaleźli przycisk listy życzeń, gdy tylko rozważają zakup produktu. Ustawienie tego na „Strona produktu” umieszcza go logicznie obok innych działań związanych z zakupem.

#### **Pokaż przycisk na stronie produktu (Show button on product page)**

- **Co robi to ustawienie:** Jest to prosty przełącznik WŁ./WYŁ. do włączania lub wyłączania wyświetlania przycisku „Dodaj do listy życzeń na Facebooku” na stronach produktów.
- **Wpływ zmiany tego ustawienia:**
  - *Po włączeniu (TAK):* Przycisk będzie widoczny i funkcjonalny na wszystkich stronach produktów.
  - *Po wyłączeniu (NIE):* Przycisk zostanie ukryty, a klienci nie będą mogli dodawać produktów do swoich list życzeń na Facebooku za pośrednictwem Twojego sklepu.
- **Zalecana wartość:** **TAK**. Aby korzystać z podstawowej funkcjonalności modułu, powinno to być zawsze włączone.
- **Scenariusz / przykład dla sprzedawcy:** Ukończyłeś całą konfigurację i chcesz, aby Twoi klienci zaczęli korzystać z tej funkcji. Ustawisz to na TAK. Jeśli tymczasowo chcesz ukryć tę funkcję w celu konserwacji lub kampanii, możesz ustawić ją na NIE.

#### **Pokaż przycisk na stronie kategorii (Show button on category page)**

- **Co robi to ustawienie:** Kontroluje, czy przycisk „Dodaj do listy życzeń na Facebooku” pojawia się na listach produktów na stronach kategorii.
- **Wpływ zmiany tego ustawienia:**
  - *Po włączeniu (TAK):* Przycisk listy życzeń pojawi się obok każdego produktu na stronach kategorii i list. Może to być przydatne do szybkiego dodawania do listy życzeń, ale może zaśmiecać układ w zależności od Twojego motywu.
  - *Po wyłączeniu (NIE):* Przycisk pojawi się tylko na poszczególnych stronach produktów, utrzymując strony kategorii w czystości.
- **Zalecana wartość:** **NIE**. Chociaż potencjalnie przydatne, wyświetlanie przycisku na stronach kategorii może czasami prowadzić do mniej optymalnego doświadczenia użytkownika lub wizualnego bałaganu. Zazwyczaj jest to bardziej skuteczne na dedykowanej stronie produktu.
- **Scenariusz / przykład dla sprzedawcy:** Masz bardzo czysty projekt strony kategorii i chcesz zminimalizować rozpraszacze. Ustawisz to na NIE, zapewniając, że akcja listy życzeń jest dostępna tylko wtedy, gdy klient skupia się na jednym produkcie.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Identyfikator aplikacji Facebooka | Twój identyfikator aplikacji Facebooka | Unikalny identyfikator integracji Twojego sklepu z Facebookiem. **Krytyczny dla funkcjonalności.** |
| Konfiguracja modułu | Sekret aplikacji Facebooka | Twój sekret aplikacji Facebooka | Bezpieczny klucz do komunikacji z Facebookiem. **Krytyczny dla funkcjonalności.** |
| Konfiguracja modułu | Adres URL strony Facebooka | `https://www.facebook.com/TwojaNazwaSklepu` (jeśli dotyczy) | Linkuje do Twojej oficjalnej strony Facebooka, zwiększając widoczność marki. |
| Konfiguracja modułu | Pozycja przycisku | Strona produktu | Określa, gdzie pojawia się przycisk listy życzeń. **Zalecana: Strona produktu.** |
| Konfiguracja modułu | Pokaż przycisk na stronie produktu | TAK | Włącza/wyłącza przycisk na poszczególnych stronach produktów. **Zalecane: TAK.** |
| Konfiguracja modułu | Pokaż przycisk na stronie kategorii | NIE | Włącza/wyłącza przycisk na listach produktów na stronach kategorii. **Zalecane: NIE.** |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Przycisk „Dodaj do listy życzeń na Facebooku” nie pojawia się na moich stronach produktów.**
O:

- **Sprawdź status modułu:** Upewnij się, że moduł jest zainstalowany i włączony w **Moduły > Menedżer modułów**.
- **Ustawienia konfiguracji:** Przejdź do strony konfiguracji modułu i sprawdź, czy „Pokaż przycisk na stronie produktu” jest ustawione na **TAK**.
- **Identyfikator/sekret aplikacji Facebooka:** Sprawdź dokładnie, czy Twój identyfikator aplikacji Facebooka i sekret aplikacji są poprawnie wprowadzone. Nieprawidłowe dane uwierzytelniające uniemożliwią załadowanie lub działanie przycisku.
- **Kompatybilność z motywem:** Niektóre wysoce spersonalizowane motywy mogą wymagać drobnych korekt. Jeśli przycisk nadal się nie pojawia, spróbuj tymczasowo przełączyć się na domyślny motyw PrestaShop (Classic), aby wykluczyć konflikt z motywem. Jeśli pojawi się na Classic, Twój deweloper motywu może potrzebować go zintegrować.
- **Wyczyść pamięć podręczną:** Zawsze wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**) i pamięć podręczną przeglądarki po wprowadzeniu zmian w konfiguracji.

**P2: Przycisk pojawia się, ale nic się nie dzieje po kliknięciu lub otrzymuję błąd Facebooka.**
O:

- **Identyfikator/sekret aplikacji Facebooka:** Jest to prawie zawsze spowodowane nieprawidłowym lub brakującym identyfikatorem aplikacji Facebooka lub sekretem aplikacji. Ponownie sprawdź ustawienia swojej aplikacji na Facebook dla programistów i upewnij się, że wartości są dokładnie skopiowane.
- **Ustawienia aplikacji Facebooka:** Na platformie Facebook dla programistów upewnij się, że Twoja aplikacja jest „Aktywna” (nie w trybie deweloperskim) i że platforma „Strona internetowa” jest dodana z poprawnie skonfigurowanym adresem URL Twojego sklepu.
- **Biała lista domen:** W ustawieniach aplikacji Facebooka, w sekcji „Ustawienia > Podstawowe”, upewnij się, że domena Twojej witryny jest wymieniona w polu „Domeny aplikacji”.
- **Tagi Open Graph:** Moduł opiera się na domyślnych meta tagach Open Graph PrestaShop dla informacji o produkcie. Upewnij się, że Twój sklep PrestaShop generuje je poprawnie (możesz sprawdzić kod źródłowy strony produktu pod kątem tagów `<meta property="og:..."`).

**P3: Jak uzyskać identyfikator aplikacji Facebooka i sekret aplikacji?**
O:

1. Przejdź do [Facebook dla programistów](https://developers.facebook.com/) i zaloguj się na swoje konto Facebook.
2. Kliknij „Moje aplikacje” > „Utwórz aplikację”.
3. Wybierz typ aplikacji (np. „Konsumencka” lub „Biznesowa”) i postępuj zgodnie z instrukcjami, aby nazwać swoją aplikację.
4. Po utworzeniu przejdź do „Ustawienia > Podstawowe” w panelu nowej aplikacji.
5. Znajdziesz tam swój **Identyfikator aplikacji** i **Sekret aplikacji**.
6. Upewnij się, że dodałeś domenę swojej witryny (np. `twojskep.com`) do pola „Domeny aplikacji” i zapisz zmiany.
7. Dodaj platformę „Strona internetowa” do swojej aplikacji i wprowadź adres URL swojej witryny.
8. Na koniec upewnij się, że Twoja aplikacja jest ustawiona na tryb „Aktywny” (zazwyczaj znajduje się przełącznik na górze panelu).

**P4: Czy ten moduł spowolni moją witrynę?**
O: Sam moduł jest bardzo lekki. Główna interakcja to mały przycisk i wyskakujące okienko hostowane przez Facebooka, które ładuje treści bezpośrednio z serwerów Facebooka. Wszelkie zauważalne spowolnienie jest bardziej prawdopodobne związane z własnymi czasami ładowania Facebooka lub ogólnymi problemami z wydajnością witryny, a nie z samym modułem.

**P5: Czy mogę dostosować wygląd przycisku?**
O: Moduł zazwyczaj używa standardowej stylizacji przycisków Facebooka lub integruje się z istniejącymi stylami przycisków Twojego motywu. Chociaż w module nie ma bezpośredniego ustawienia do zmiany jego wyglądu, programista stron internetowych może dostosować go za pomocą CSS, celując w konkretne klasy CSS lub identyfikatory elementu przycisku.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł Facebook Wishlist (`facebook-wishlist`) to prosty moduł PrestaShop, zaprojektowany przede wszystkim do wstrzykiwania funkcjonalności „Dodaj do listy życzeń” opartej na Open Graph do front-office. Wykorzystuje system hooków PrestaShop do renderowania swojego przycisku na stronach produktów i opiera się na Facebook JavaScript SDK oraz protokole Open Graph dla swojej podstawowej funkcjonalności. Konfiguracja modułu jest zarządzana za pomocą standardowej metody `getContent()` w głównym pliku modułu, przechowując ustawienia w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie używa niestandardowych kontrolerów front-office ani back-office. Cała logika jest hermetyzowana w głównym pliku modułu i jego konfiguracji.

### 4.3 Główne klasy i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani `ObjectModel`s. Cała konfiguracja jest obsługiwana za pomocą `Configuration::get()` i `Configuration::updateValue()`.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera niestandardowych plików JavaScript. Opiera się na Facebook JavaScript SDK, który jest zazwyczaj ładowany asynchronicznie i zarządzany przez samego Facebooka, gdy obecne są prawidłowe meta tagi Open Graph i identyfikator aplikacji.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera niestandardowych plików CSS. Wygląd przycisku jest obsługiwany przez domyślną stylizację Facebooka dla jego wtyczek społecznościowych lub dziedziczy style z aktywnego motywu PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie zawiera katalogu `views/templates`. Kod HTML przycisku jest prawdopodobnie generowany bezpośrednio w metodach hooków głównego pliku modułu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych. Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `FACEBOOK_WISHLIST_APP_ID`, `FACEBOOK_WISHLIST_APP_SECRET`, `FACEBOOK_WISHLIST_PAGE_URL`, `FACEBOOK_WISHLIST_BUTTON_POSITION`, `FACEBOOK_WISHLIST_SHOW_PRODUCT_PAGE` i `FACEBOOK_WISHLIST_SHOW_CATEGORY_PAGE`.
- **Zarejestrowane hooki**:
  Moduł rejestruje i wykorzystuje następujące hooki PrestaShop:

  | Nazwa hooka | Czas wykonania | Cel techniczny |
  | --- | --- | --- |
  | `displayHeader` | W sekcji `<head>` każdej strony. | Służy do wstrzykiwania kodu inicjalizacyjnego Facebook JavaScript SDK i meta tagów Open Graph (jeśli nie są już obecne w rdzeniu PrestaShop). Jest to kluczowe dla Facebooka, aby rozpoznać Twoją witrynę i aplikację. |
  | `displayProductButtons` | Na stronie produktu, zazwyczaj w pobliżu przycisku „Dodaj do koszyka”. | Renderuje przycisk „Dodaj do listy życzeń na Facebooku”. Jest to główny hook dla wyświetlania modułu we front-office. |
  | `displayProductListFunctionalButtons` | Na stronach kategorii/list, obok każdego produktu. | Renderuje przycisk „Dodaj do listy życzeń na Facebooku” dla produktów na listach, jeśli jest włączony w konfiguracji. |
  | `displayFooter` | W stopce każdej strony. | Potencjalnie używany do ładowania dodatkowych skryptów lub umieszczania przycisku awaryjnego, chociaż `displayProductButtons` jest głównym. |
  | `displayLeftColumn` | W lewej kolumnie stron. | Alternatywna pozycja dla przycisku, jeśli skonfigurowana. |
  | `displayRightColumn` | W prawej kolumnie stron. | Alternatywna pozycja dla przycisku, jeśli skonfigurowana. |

  Podstawowa funkcjonalność modułu opiera się na hooku `displayHeader`, aby zapewnić załadowanie Facebook SDK, oraz na hooku `displayProductButtons` (lub `displayProductListFunctionalButtons`), aby renderować interaktywny przycisk. Sam przycisk, po kliknięciu, wyzwala akcję Facebook Open Graph `og:product:wishlist`, która wymaga obecności w kodzie HTML strony produktu specyficznych meta tagów Open Graph (takich jak `og:title`, `og:description`, `og:image`, `og:url`, `og:type=product`). PrestaShop zazwyczaj generuje te tagi domyślnie.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu Facebook Wishlist, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
"""
