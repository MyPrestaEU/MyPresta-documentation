---
title: "Zalando Fashion Connector Importer (FCI) - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów dla modułu PrestaShop Zalando Fashion Connector Importer (FCI) od MyPresta.eu."
sidebar:
  label: "Zalando Fashion Connector Importer (FCI) - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Zalando Fashion Connector Importer (FCI) na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/zalando-fashion-connector-importer-fci.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/zalando-fashion-connector-importer-fci/)
>
> ---


# Zalando Fashion Connector Importer (FCI)

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla większości modułów PrestaShop i są zazwyczaj dostępne w każdym nowoczesnym środowisku hostingowym.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Zalando Fashion Connector Importer (FCI))

Jest to główny ekran konfiguracji, na którym ustawiasz podstawowe parametry dla swojego pliku Zalando.

-   **Co robi to ustawienie:** Ta sekcja pozwala zdefiniować podstawowe informacje, które zostaną uwzględnione w Twoim pliku produktowym Zalando.
-   **Wpływ zmiany tego ustawienia:** Wartości, które tu ustawisz, będą bezpośrednio wpływać na dane, które Zalando otrzymuje o Twoich produktach, wpływając na sposób ich wyświetlania i zarządzania na ich platformie.

| Ustawienie / Opcja | Co robi to ustawienie | Wpływ zmiany tego ustawienia | Zalecana wartość | Scenariusz / przykład sprzedawcy |
| --- | --- | --- | --- | --- |
| **Sklep** | Określa nazwę Twojego sklepu, tak jak powinna się pojawić na Zalando. Pomaga to Zalando zidentyfikować Twój konkretny punkt sprzedaży detalicznej. | *Po ustawieniu:* Twoja określona nazwa sklepu zostanie uwzględniona w pliku produktowym. *Po pozostawieniu pustego:* Zalando może użyć domyślnego identyfikatora lub odrzucić plik, jeśli nazwa sklepu jest obowiązkowa. | Twoja rzeczywista nazwa sklepu (np. „Moja Butikowa Moda”) | Jeśli masz wiele sklepów fizycznych lub marek, pomaga to Zalando rozróżnić Twój asortyment. |
| **EAN (Europejski Numer Artykułu)** | Określa, czy EAN (kod kreskowy) Twoich produktów powinien być uwzględniony w pliku. EAN-y są kluczowe dla identyfikacji produktu. | *Po włączeniu:* EAN-y będą częścią pliku, umożliwiając Zalando dokładne dopasowanie Twoich produktów. *Po wyłączeniu:* Produkty mogą nie być poprawnie zidentyfikowane lub mogą zostać odrzucone przez Zalando, jeśli EAN jest polem obowiązkowym. | TAK | Niezbędne dla większości ofert produktów, zwłaszcza w modzie, aby zapewnić unikalną identyfikację. |
| **Cena** | Kontroluje, czy cena sprzedaży produktu jest uwzględniona w pliku. | *Po włączeniu:* Aktualna cena sprzedaży z Twojego sklepu PrestaShop zostanie wysłana do Zalando. *Po wyłączeniu:* Zalando nie otrzyma aktualizacji cen, co może prowadzić do nieaktualnych cen na ich platformie. | TAK | Kluczowe dla zapewnienia, że klienci widzą poprawną cenę na Zalando. |
| **Cena detaliczna** | Określa, czy oryginalna cena detaliczna (często cena „przekreślona” dla rabatów) jest uwzględniona. | *Po włączeniu:* Oryginalna cena zostanie wysłana, umożliwiając Zalando wyświetlanie oszczędności lub promocji. *Po wyłączeniu:* Zostanie wysłana tylko aktualna cena sprzedaży, potencjalnie ukrywając informacje o rabatach. | TAK (jeśli używasz cen detalicznych do promocji) | Jeśli prowadzisz wyprzedaże, uwzględnienie ceny detalicznej pomaga podkreślić rabat dla klientów na Zalando. |
| **Ilość** | Określa, czy aktualna ilość magazynowa Twoich produktów jest uwzględniona w pliku. | *Po włączeniu:* Twoje stany magazynowe produktów zostaną zaktualizowane na Zalando, zapobiegając nadmiernej sprzedaży. *Po wyłączeniu:* Zalando nie otrzyma aktualizacji stanów magazynowych, co prowadzi do potencjalnych rozbieżności i niezadowolenia klientów, jeśli produkt jest niedostępny. | TAK | Absolutnie kluczowe, aby uniknąć sprzedaży produktów, których już nie masz. |
| **Nazwa produktu** | Kontroluje, czy nazwa produktu jest uwzględniona w pliku. | *Po włączeniu:* Nazwa produktu z Twojego sklepu PrestaShop zostanie wysłana do Zalando. *Po wyłączeniu:* Produkty mogą być wyświetlane bez nazw lub odrzucone, jeśli jest to pole obowiązkowe. | TAK | Niezbędne dla klientów, aby identyfikować i wyszukiwać Twoje produkty na Zalando. |
| **ID klienta (zf\_client)** | Twój unikalny identyfikator klienta dostarczony przez Zalando do dostępu do API. | *Po poprawnym wprowadzeniu:* Umożliwia modułowi uwierzytelnienie się w systemach Zalando. *Po nieprawidłowym lub pustym:* Generowanie i aktualizacje pliku nie powiodą się. | ID dostarczone przez Zalando | Musisz uzyskać to od swojego menedżera konta Zalando Connected Retail. |
| **Klucz API (zf\_api)** | Twój unikalny klucz API dostarczony przez Zalando do bezpiecznej komunikacji. | *Po poprawnym wprowadzeniu:* Umożliwia bezpieczny transfer danych między Twoim sklepem a Zalando. *Po nieprawidłowym lub pustym:* Generowanie i aktualizacje pliku nie powiodą się z powodu problemów z uwierzytelnieniem. | Klucz dostarczony przez Zalando | Jest to poświadczenie bezpieczeństwa; zachowaj je w tajemnicy i uzyskaj je od Zalando. |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 Konfiguracja eksportu produktów (Panel administracyjny > Zalando FCI > Eksport produktów)

Ten ekran, dostępny poprzez menu panelu administracyjnego PrestaShop, służy do definiowania szczegółowych parametrów generowania pliku produktowego dla Zalando. Pozwala na precyzyjne dostosowanie, jakie dane są uwzględniane i jak są formatowane.

-   **Nazwa ekranu i lokalizacja w menu:** **Zalando FCI > Eksport produktów** (Pojawi się to jako nowa pozycja menu w nawigacji panelu administracyjnego PrestaShop).
-   **Dostępne działania i ustawienia:** Ten ekran przedstawia formularz z licznymi opcjami dostosowywania eksportu produktów. Znajdziesz pola do wyboru sklepów, walut, atrybutów produktów i opcji filtrowania.
-   **Wpływ zmian:** Zmiany tutaj bezpośrednio wpływają na zawartość i strukturę generowanego pliku produktowego. Nieprawidłowe ustawienia mogą spowodować odrzucenie pliku przez Zalando lub wyświetlanie nieprawidłowych informacji o produkcie.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Początkowo skonfiguruj wszystkie ustawienia ostrożnie, zgodnie ze specyfikacjami Zalando i potrzebami Twojego sklepu.
    2.  Wygeneruj plik testowy i zweryfikuj go z Zalando (jeśli to możliwe), aby upewnić się, że wszystkie dane są poprawne.
    3.  Po skonfigurowaniu, będziesz głównie używać tego ekranu do ręcznego generowania pliku, gdy zajdzie taka potrzeba, lub skonfigurujesz zadanie cron (zaplanowane zadanie) do automatyzacji generowania pliku na podstawie tych ustawień.

| Ustawienie / Opcja | Co robi to ustawienie | Wpływ zmiany tego ustawienia | Zalecana wartość | Scenariusz / przykład sprzedawcy |
| --- | --- | --- | --- | --- |
| **Zapamiętaj ustawienia (zf\_remember\_settings)** | Jeśli włączone, moduł zapamięta ostatnio wybrane ustawienia eksportu dla wygody. | *Po włączeniu:* Twoje wybory na tej stronie będą zachowane dla przyszłych eksportów. *Po wyłączeniu:* Ustawienia powrócą do domyślnych za każdym razem, gdy odwiedzisz stronę. | TAK | Oszczędza czas, jeśli często generujesz pliki z tymi samymi parametrami. |
| **Format pliku eksportu (zf\_export\_file\_format)** | Wybiera format wyjściowy dla pliku produktowego (np. CSV, XML). | *Po ustawieniu:* Wygenerowany plik będzie w wybranym formacie. *Po nieprawidłowym:* Zalando może nie być w stanie przetworzyć pliku. | Sprawdź wymagania Zalando (zazwyczaj CSV lub XML) | Zalando określi wymagany format dla swojego systemu importu. |
| **Typ eksportu (zf\_export\_type)** | Definiuje, jaki rodzaj produktów ma być eksportowany (np. wszystkie produkty, tylko aktywne, tylko określone kategorie). | *Po ustawieniu:* Uwzględnione zostaną tylko produkty spełniające kryteria. *Po nieprawidłowym:* Możesz wyeksportować zbyt wiele lub zbyt mało produktów. | Wszystkie aktywne produkty, lub zgodnie z onboardingiem Zalando | Jeśli chcesz wyświetlić tylko podzbiór swojego katalogu na Zalando. |
| **Sklep (zf\_export\_store)** | Pozwala wybrać, z którego sklepu PrestaShop (w konfiguracji multi-store) eksportować produkty. | *Po wybraniu:* Produkty z tego konkretnego sklepu zostaną wyeksportowane. *Po nieprawidłowym:* Mogą zostać uwzględnione produkty z niewłaściwego sklepu. | Twój główny sklep lub odpowiedni sklep dla Zalando | Dla sprzedawców prowadzących wiele odrębnych sklepów z jednej instalacji PrestaShop. |
| **Separator (zf\_export\_delimiter)** | Określa znak używany do oddzielania pól danych w pliku eksportu (np. przecinek, średnik). | *Po ustawieniu:* Użyty zostanie wybrany separator. *Po nieprawidłowym:* Plik będzie nieczytelny dla Zalando. | Sprawdź wymagania Zalando (często przecinek lub średnik) | Kluczowe dla plików CSV, aby zapewnić poprawne parsowanie danych. |
| **Waluta (zf\_export\_currency)** | Wybiera walutę dla cen produktów w pliku eksportu. | *Po wybraniu:* Ceny zostaną przeliczone lub wyświetlone w tej walucie. *Po nieprawidłowym:* Zalando może wyświetlać błędne ceny lub odrzucić plik. | Waluta wymagana przez Zalando (np. EUR) | Jeśli Twój sklep działa w wielu walutach, upewnij się, że eksportujesz w tej, której oczekuje Zalando. |
| **Format nazwy produktu (zf\_export\_product\_name\_format)** | Definiuje, jak formatowane są nazwy produktów (np. uwzględnij producenta, atrybuty). | *Po ustawieniu:* Nazwy produktów będą zgodne z tym formatem. *Po nieprawidłowym:* Nazwy mogą być niejasne lub nie spełniać wytycznych Zalando. | Zgodnie z zaleceniami Zalando dla jasności | Aby zapewnić, że nazwy produktów są informacyjne i spójne na Zalando. |
| **Uwzględnij podatek (zf\_export\_tax)** | Określa, czy ceny produktów w pliku powinny zawierać podatek. | *Po włączeniu:* Ceny będą zawierać podatek. *Po wyłączeniu:* Ceny będą bez podatku. | Sprawdź wymagania Zalando dotyczące wyświetlania cen | Ważne dla zgodności podatkowej i poprawnego wyświetlania cen na Zalando. |
| **Eksportuj ceny krajowe (zf\_export\_country\_prices)** | Jeśli włączone, ceny specyficzne dla różnych krajów zostaną uwzględnione (jeśli skonfigurowano w PrestaShop). | *Po włączeniu:* Ceny specyficzne dla kraju zostaną wyeksportowane. *Po wyłączeniu:* Wyeksportowane zostaną tylko ceny domyślne. | TAK (jeśli masz ceny specyficzne dla kraju) | Dla sprzedawców międzynarodowych z różnymi strategiami cenowymi dla regionu. |
| **Domyślny kraj (PS\_COUNTRY\_DEFAULT)** | Domyślny kraj dla Twojego sklepu PrestaShop, używany jako rezerwowy dla niektórych ustawień. | *Po ustawieniu:* Zapewnia podstawowy kraj dla obliczeń cen i podatków. | Główny kraj Twojego sklepu | Zapewnia spójne domyślne zachowanie dla ustawień międzynarodowych. |
| **Eksportuj tylko aktywne produkty (zf\_export\_active)** | Jeśli włączone, eksportowane będą tylko produkty aktualnie oznaczone jako „aktywne” w PrestaShop. | *Po włączeniu:* Wysyłane są tylko dostępne produkty. *Po wyłączeniu:* Mogą zostać uwzględnione nieaktywne produkty, co prowadzi do błędów na Zalando. | TAK | Zapobiega wyświetlaniu produktów, których nie chcesz sprzedawać lub które nie są już dostępne. |
| **Eksportuj producentów (zf\_export\_manufacturers)** | Jeśli włączone, informacje o producencie zostaną uwzględnione w pliku. | *Po włączeniu:* Dane producenta są wysyłane. *Po wyłączeniu:* Dane producenta są pomijane. | TAK | Przydatne dla klientów do filtrowania według marki na Zalando. |
| **Eksportuj dostawców (zf\_export\_suppliers)** | Jeśli włączone, informacje o dostawcy zostaną uwzględnione w pliku. | *Po włączeniu:* Dane dostawcy są wysyłane. *Po wyłączeniu:* Dane dostawcy są pomijane. | NIE (chyba że wymagane przez Zalando) | Mniej powszechne dla plików skierowanych do klienta, bardziej dla wewnętrznego śledzenia. |
| **Eksportuj kategorię (zf\_export\_category)** | Jeśli włączone, informacje o kategorii produktu zostaną uwzględnione. | *Po włączeniu:* Dane kategorii są wysyłane. *Po wyłączeniu:* Dane kategorii są pomijane. | TAK | Pomaga Zalando poprawnie kategoryzować Twoje produkty i ułatwia nawigację klientom. |
| **Eksportuj tylko produkty dostępne w magazynie (zf\_export\_instock)** | Jeśli włączone, eksportowane będą tylko produkty z dostępnym stanem magazynowym. | *Po włączeniu:* Wysyłane są tylko produkty, które możesz zrealizować. *Po wyłączeniu:* Mogą zostać uwzględnione produkty niedostępne w magazynie, co prowadzi do problemów z nadmierną sprzedażą. | TAK | Kluczowe dla zapobiegania rozczarowaniu klientów z powodu niedostępnych produktów. |
| **Wyklucz cenę maksymalną (zf\_export\_exclude\_price\_max)** | Jeśli włączone, produkty powyżej określonego progu cenowego zostaną wykluczone z pliku. | *Po włączeniu:* Produkty przekraczające maksymalną cenę nie zostaną wyeksportowane. *Po wyłączeniu:* Wszystkie produkty, niezależnie od ceny, są eksportowane. | NIE (chyba że masz konkretne, drogie produkty do wykluczenia) | Przydatne, jeśli Zalando ma limity cenowe lub jeśli chcesz sprzedawać tylko określone przedziały cenowe na ich platformie. |
| **Wartość wykluczenia ceny maksymalnej (zf\_export\_exclude\_price\_max\_v)** | Maksymalna wartość ceny dla ustawienia „Wyklucz cenę maksymalną”. | *Po ustawieniu:* Definiuje górny limit cenowy dla eksportowanych produktów. | Pozostaw puste, jeśli nie wykluczasz według ceny maksymalnej | Jeśli chcesz sprzedawać na Zalando tylko produkty poniżej 500 €, ustaw to na 500. |

#### 2.2.2 Ekran indeksu administracyjnego (Panel administracyjny > Zalando FCI > Indeks)

Ten ekran prawdopodobnie służy jako strona docelowa lub prosty widok zarządzania modułem, potencjalnie wyświetlając informacje lub zapewniając szybkie linki.

-   **Nazwa ekranu i lokalizacja w menu:** **Zalando FCI > Indeks** (Pojawi się to jako nowa pozycja menu w nawigacji panelu administracyjnego PrestaShop, często jako pierwsza pozycja pod głównym menu modułu).
-   **Dostępne działania i ustawienia:** Ten ekran zazwyczaj wyświetla siatkę lub prosty panel informacyjny. Może pokazywać datę ostatniego eksportu, link do generowania pliku lub ogólny status modułu. Zazwyczaj nie jest to ekran do szczegółowej konfiguracji, ale raczej do przeglądu lub szybkich działań.
-   **Wpływ zmian:** Zazwyczaj nie ma bezpośrednich „ustawień” do zmiany na tym ekranie. Jego celem jest bardziej informacyjny lub nawigacyjny.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Używaj tego jako szybkiego punktu wejścia do modułu, aby sprawdzić status ostatniego eksportu lub nawigować do ekranu „Eksport produktów” w celu szczegółowej konfiguracji i generowania pliku.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Sklep | Nazwa Twojego sklepu | Identyfikuje Twój sklep na Zalando. |
| **Konfiguracja modułu** | EAN | TAK | Niezbędne do identyfikacji produktu. |
| **Konfiguracja modułu** | Cena | TAK | Zapewnia prawidłowe ceny na Zalando. |
| **Konfiguracja modułu** | Cena detaliczna | TAK (jeśli używana) | Wyświetla oryginalną cenę dla promocji. |
| **Konfiguracja modułu** | Ilość | TAK | Kluczowe dla dokładnych stanów magazynowych, zapobiega nadmiernej sprzedaży. |
| **Konfiguracja modułu** | Nazwa produktu | TAK | Niezbędne do identyfikacji i wyszukiwania produktu. |
| **Konfiguracja modułu** | ID klienta (zf\_client) | Dostarczone przez Zalando | Uwierzytelnia się w API Zalando. |
| **Konfiguracja modułu** | Klucz API (zf\_api) | Dostarczone przez Zalando | Zabezpiecza komunikację z API Zalando. |
| **Eksport produktów** | Zapamiętaj ustawienia | TAK | Oszczędza czas, zachowując wybory eksportu. |
| **Eksport produktów** | Format pliku eksportu | Sprawdź wymagania Zalando | Definiuje typ pliku wyjściowego. |
| **Eksport produktów** | Typ eksportu | Wszystkie aktywne produkty | Kontroluje, które produkty są uwzględniane. |
| **Eksport produktów** | Sklep | Twój główny sklep | Wybiera produkty z określonego sklepu (multi-store). |
| **Eksport produktów** | Separator | Sprawdź wymagania Zalando | Oddziela pola w plikach CSV. |
| **Eksport produktów** | Waluta | Wymagana przez Zalando (np. EUR) | Ustawia walutę dla eksportowanych cen. |
| **Eksport produktów** | Format nazwy produktu | Zgodnie z zaleceniami Zalando | Formatuje nazwy produktów dla jasności. |
| **Eksport produktów** | Uwzględnij podatek | Sprawdź wymagania Zalando | Określa, czy ceny zawierają podatek. |
| **Eksport produktów** | Eksportuj ceny krajowe | TAK (jeśli dotyczy) | Uwzględnia ceny specyficzne dla kraju. |
| **Eksport produktów** | Domyślny kraj | Główny kraj Twojego sklepu | Rezerwowy dla ustawień związanych z krajem. |
| **Eksport produktów** | Eksportuj tylko aktywne produkty | TAK | Zapobiega wyświetlaniu nieaktywnych produktów. |
| **Eksport produktów** | Eksportuj producentów | TAK | Uwzględnia informacje o marce. |
| **Eksport produktów** | Eksportuj dostawców | NIE (chyba że wymagane) | Uwzględnia informacje o dostawcy. |
| **Eksport produktów** | Eksportuj kategorię | TAK | Pomaga Zalando kategoryzować produkty. |
| **Eksport produktów** | Eksportuj tylko produkty dostępne w magazynie | TAK | Zapobiega wyświetlaniu produktów niedostępnych w magazynie. |
| **Eksport produktów** | Wyklucz cenę maksymalną | NIE (chyba że potrzebne) | Wyklucza produkty powyżej ustalonej ceny. |
| **Eksport produktów** | Wartość wykluczenia ceny maksymalnej | Pozostaw puste, jeśli nie wykluczasz | Ustawia maksymalną cenę do wykluczenia. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje produkty nie pojawiają się na Zalando, lub plik jest odrzucany. Co powinienem sprawdzić w pierwszej kolejności?**
O1:

-   **Sprawdź konfigurację modułu:** Przejdź do **Moduły > Menedżer modułów > Zalando Fashion Connector Importer (FCI) > Konfiguruj**. Upewnij się, że Twoje „ID klienta” i „Klucz API” są poprawnie wprowadzone, zgodnie z informacjami dostarczonymi przez Zalando.
-   **Sprawdź ustawienia eksportu:** Przejdź do **Zalando FCI > Eksport produktów**. Zweryfikuj, czy „Format pliku eksportu” i „Separator” dokładnie odpowiadają wymaganiom Zalando. Upewnij się również, że „Eksportuj tylko aktywne produkty” i „Eksportuj tylko produkty dostępne w magazynie” są włączone, jeśli chcesz wysyłać tylko dostępne produkty.
-   **Zweryfikuj dane produktu:** Upewnij się, że Twoje produkty w PrestaShop mają prawidłowe EAN-y, nazwy, ceny i stany magazynowe. Brakujące lub nieprawidłowe dane są częstą przyczyną odrzuceń.
-   **Wyczyść pamięć podręczną:** Czasami stare dane mogą się utrzymywać. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).

**P2: Ceny lub stany magazynowe na Zalando nie aktualizują się poprawnie.**
O2:

-   **Sprawdź częstotliwość eksportu:** Jak często generujesz plik? Jeśli robisz to ręcznie, musisz to robić regularnie. Jeśli skonfigurowałeś zadanie cron, upewnij się, że działa z pożądaną częstotliwością (np. co godzinę).
-   **Konfiguracja modułu:** Sprawdź dwukrotnie, czy „Cena” i „Ilość” są włączone na głównym ekranie konfiguracji modułu.
-   **Czas przetwarzania Zalando:** Pamiętaj, że nawet po wygenerowaniu i wysłaniu pliku, systemy Zalando potrzebują czasu na przetworzenie i aktualizację danych. Może to potrwać od kilku minut do kilku godzin, w zależności od ich obciążenia.

**P3: Mam niestandardowy motyw, a interfejs administracyjny modułu wygląda trochę dziwnie.**
O3:

-   Interfejs administracyjny modułu wykorzystuje standardowe style PrestaShop, ale drobne niespójności wizualne mogą wystąpić w przypadku bardzo niestandardowych motywów panelu administracyjnego. Zazwyczaj nie wpływa to na funkcjonalność.
-   Jeśli jest to poważny problem, skontaktuj się z pomocą techniczną MyPresta.eu. W przypadku drobnych poprawek, programista internetowy może często dostosować plik `zalandofci/views/admin-theme.css` lub dodać niestandardowy CSS do panelu administracyjnego PrestaShop.

**P4: Jak skonfigurować zadanie cron do automatyzacji generowania pliku?**
O4:

-   Dokładne kroki zależą od Twojego dostawcy hostingu. Zazwyczaj znajdziesz sekcję „Zadania Cron” lub „Zaplanowane zadania” w panelu sterowania hostingu (np. cPanel, Plesk).
-   Będziesz potrzebować adresu URL, który uruchamia generowanie pliku. Ten adres URL jest zazwyczaj podany na stronie konfiguracji „Eksport produktów” modułu po zapisaniu ustawień, lub można go skonstruować za pomocą ścieżki kontrolera frontowego (np. `twojskep.com/module/zalandofci/feed`).
-   Ustaw zadanie cron tak, aby wykonywało ten adres URL w pożądanym interwale (np. `wget -q -O /dev/null "http://twojskep.com/module/zalandofci/feed"`). Jeśli nie jesteś pewien, zapoznaj się z dokumentacją lub wsparciem swojego dostawcy hostingu.

**P5: Moduł jest zainstalowany, ale nie widzę „Zalando FCI” w menu mojego panelu administracyjnego.**
O5:

-   **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i wyczyść pamięć podręczną. Czasami menu nie odświeża się natychmiast po instalacji modułu.
-   **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i wyszukaj „Zalando Fashion Connector Importer (FCI)”. Upewnij się, że jest on wymieniony jako „Zainstalowany” i „Włączony”.
-   **Uprawnienia:** W rzadkich przypadkach uprawnienia pracowników mogą ograniczać widoczność menu. Sprawdź **Administracja > Uprawnienia** dla swojego profilu pracownika.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł Zalando Fashion Connector Importer (FCI) jest zgodny ze standardową architekturą modułów PrestaShop, wykorzystując zasady MVC tam, gdzie ma to zastosowanie. Koncentruje się przede wszystkim na eksporcie danych, wykorzystując kombinację kontrolerów frontowych i administracyjnych. Główna logika znajduje się w głównym pliku modułu i kontrolerach administracyjnych do konfiguracji i generowania pliku. Nie wydaje się, aby używał niestandardowych klas `ObjectModel`, zamiast tego bezpośrednio odpytuje bazę danych PrestaShop o dane produktów. Główną funkcją modułu jest generowanie pliku danych, który jest zazwyczaj konsumowany przez zewnętrzny system (Zalando) za pośrednictwem zaplanowanego zadania (cron job) trafiającego do kontrolera frontowego.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery są dostępne z adresu URL front-office i są zazwyczaj używane do generowania pliku produktowego, często wywoływanego przez zadanie cron.

-   `controllers/front/feed.php`
    -   **Nazwa klasy i klasa nadrzędna**: `ZalandofciFeedModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność**: Jest to główny punkt końcowy do generowania pliku produktowego. Odpowiada na żądania (zazwyczaj z zadań cron) i dynamicznie generuje dane produktów na podstawie konfiguracji modułu. Prawdopodobnie pobiera informacje o produkcie (EAN, cena, ilość, nazwa) i formatuje je do określonego wyjścia (np. CSV, XML) dla Zalando. Ten kontroler nie renderuje strony wizualnej, ale wyprowadza surowe dane.
-   `controllers/front/index.php`
    -   **Nazwa klasy i klasa nadrzędna**: `ZalandofciIndexModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność**: Ten kontroler prawdopodobnie służy jako rezerwowy lub prosty punkt wejścia, potencjalnie przekierowując lub wyświetlając minimalną wiadomość. W wielu modułach kontroler frontowy `index.php` jest obecny, aby zapobiec listowaniu katalogów lub zapewnić domyślne działanie, jeśli nie zażądano konkretnego działania.

#### Kontrolery administracyjne Back-Office

Te kontrolery zarządzają konfiguracją modułu i ustawieniami eksportu produktów w panelu administracyjnym PrestaShop.

-   `controllers/admin/AdminExportProductsFci.php`
    -   **Nazwa zakładki i zarządzana encja**: „Eksport produktów” w menu „Zalando FCI”. Ten kontroler zarządza szczegółową konfiguracją eksportu produktów.
    -   **Odpowiedzialność**: Ten kontroler obsługuje wyświetlanie i przesyłanie formularza eksportu produktów. Pobiera ustawienia konfiguracji (np. `zf_export_file_format`, `zf_export_type`, `zf_export_currency`, `zf_export_tax`, `zf_export_active` itp.) z `ps_configuration`, przetwarza dane wejściowe użytkownika i uruchamia rzeczywistą logikę pobierania i formatowania danych produktów do generowania pliku. Prawdopodobnie używa metod `AdminController` do renderowania formularza (`renderForm`) i zapisywania (`postProcess`).
-   `controllers/admin/index.php`
    -   **Nazwa zakładki i zarządzana encja**: „Indeks” w menu „Zalando FCI”.
    -   **Odpowiedzialność**: Podobnie jak jego odpowiednik front-office, ten kontroler administracyjny prawdopodobnie służy jako strona docelowa lub prosty przegląd. Może wyświetlać ogólne informacje o module, szybkie linki do innych stron administracyjnych lub komunikat o statusie. Zazwyczaj nie jest zaangażowany w złożone zarządzanie danymi, ale raczej w nawigację i wyświetlanie informacji.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu wskazuje brak niestandardowych klas lub modeli w katalogu `classes/`. Sugeruje to, że moduł bezpośrednio współdziała z podstawowymi klasami `ObjectModel` PrestaShop, takimi jak `Product` i `ProductSupplier` (lub podobnymi), oraz klasą `Configuration` dla ustawień. Pobieranie danych jest prawdopodobnie obsługiwane bezpośrednio w kontrolerach lub głównym pliku modułu za pomocą `Db::getInstance()->executeS()` lub obiektów `DbQuery`.

### 4.4 Zasoby JavaScript (`views/js/`)

Dossier modułu wskazuje brak niestandardowych plików JavaScript. Oznacza to, że konfiguracja i funkcjonalność modułu są przede wszystkim sterowane po stronie serwera, z minimalnymi lub żadnymi dynamicznymi interakcjami front-end w panelu administracyjnym lub front-office, które wymagałyby niestandardowego JS.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `zalandofci/views/admin-theme.css`
    -   **Zakres**: Stylizacja formularzy administracyjnych Back-office.
    -   **Główne komponenty i kontenery interfejsu użytkownika, które stylizuje**: Ten arkusz stylów jest odpowiedzialny za wizualną prezentację formularzy konfiguracyjnych modułu i potencjalnie wszelkich niestandardowych siatek lub paneli informacyjnych w panelu administracyjnym PrestaShop. Zapewnia, że interfejs modułu wizualnie integruje się z motywem administracyjnym PrestaShop.
    -   **Kluczowe selektory klas CSS, które deweloperzy mogą nadpisać**: Deweloperzy mogą sprawdzić strony administracyjne modułu, aby zidentyfikować konkretne klasy (np. `.zalandofci-form`, `.zalandofci-panel`, `.zalandofci-alert`) i nadpisać je w swoim niestandardowym motywie administracyjnym lub dodając CSS za pomocą haka `displayBackOfficeHeader`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony haków (`views/templates/hook/`)**:
    -   Dossier modułu nie wymienia jawnie szablonów w podkatalogu `hook/`, ale rejestruje haki takie jak `displayHeader`, `displayRightColumn`, `displayProduct`, `displayFooter`. Gdyby jakikolwiek wizualny wynik był przeznaczony dla tych haków, szablony zazwyczaj znajdowałyby się tutaj. Biorąc pod uwagę cel modułu (plik danych backendu), jest prawdopodobne, że te haki są używane do celów technicznych (np. dodawanie JS/CSS, lub wcale nie są używane do wizualnego wyniku).
-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `zalandofci/views/how-it-works.tpl`
        -   **Cel**: Ten szablon prawdopodobnie dostarcza treści informacyjnych w panelu administracyjnym, być może na głównej stronie konfiguracji lub ekranie „Indeks”, wyjaśniając, jak działa moduł lub dostarczając instrukcje konfiguracji.
    -   `zalandofci/views/returnAlert.tpl`
        -   **Cel**: Ten szablon jest prawdopodobnie używany do wyświetlania komunikatów o sukcesie lub błędach (alertów) w panelu administracyjnym po wykonaniu akcji (np. zapisaniu konfiguracji, wygenerowaniu pliku).
    -   `zalandofci/views/script.tpl`
        -   **Cel**: Ten szablon może zawierać wbudowany kod JavaScript lub być używany do warunkowego dołączania zewnętrznych plików JS w panelu administracyjnym. Może być używany do dynamicznego zachowania formularzy lub do wyzwalania określonych działań.
-   **Szablony front-office (`views/templates/front/`)**:
    -   Dossier modułu nie wymienia żadnych konkretnych szablonów front-office, co potwierdza ideę, że moduł nie ma bezpośredniej wizualnej obecności po stronie sklepu skierowanej do klienta.

### 4.7 Schemat bazy danych i mapa haków

-   **Tabele bazy danych**:

    -   Moduł nie wydaje się tworzyć niestandardowych tabel SQL podczas instalacji (metoda `install()`).
    -   Wszystkie ustawienia konfiguracyjne specyficzne dla modułu (np. `zf_client`, `zf_api`, `zf_export_file_format`, `zf_remember_settings` itp.) są przechowywane w standardowej tabeli `ps_configuration` PrestaShop. Te klucze są poprzedzone prefiksem `zf_` lub `PS_` (dla podstawowych ustawień PrestaShop używanych przez moduł).
-   **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` wszystkich stron front-office. | Potencjalnie używany do dołączania CSS lub JS specyficznych dla modułu, chociaż nie ma niestandardowego JS/CSS wymienionego dla front-office. Może być również używany do meta tagów lub innych niewizualnych elementów. |
| `displayRightColumn` | Renderuje się w prawej kolumnie stron, które ją posiadają. | Mało prawdopodobne, aby był używany do wizualnego wyniku, biorąc pod uwagę cel modułu. Może być to hak dziedziczony lub używany do bardzo specyficznego, niewizualnego wstrzykiwania danych. |
| `displayProduct` | Renderuje się na stronie produktu. | Mało prawdopodobne, aby był używany do wizualnego wyniku. Może być używany do dodawania ukrytych atrybutów danych do elementów produktu dla zewnętrznych skryptów, chociaż nie ma niestandardowego JS wymienionego. |
| `displayFooter` | Renderuje się w sekcji stopki wszystkich stron front-office. | Podobnie jak `displayHeader`, może być używany do dołączania JS/CSS lub innych niewizualnych elementów na końcu ładowania strony. |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje media (JS/CSS). | Używany przez `AdminExportProductsFci` do ładowania `zalandofci/views/admin-theme.css` dla swoich formularzy konfiguracyjnych. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego oraz pobrania najnowszych wersji modułu Zalando Fashion Connector Importer (FCI), odwiedź swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
