---
title: "Pixel śledzenia konwersji Fb - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Pixel śledzenia konwersji Fb” od MyPresta.eu."
sidebar:
  label: "Pixel śledzenia konwersji Fb - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Fb conversion tracking pixel na MyPresta.eu](https://mypresta.eu/modules/social-networks/fb-conversion-tracking-pixel.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/fb-conversion-tracking-pixel/)
>
> ---


# Pixel śledzenia konwersji Fb

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP, takie jak cURL, JSON i OpenSSL, są wymagane do prawidłowego działania modułu, zwłaszcza dla funkcji Conversions API (CAPI). Są one zazwyczaj dostępne we wszystkich nowoczesnych środowiskach hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji znajdziesz się na głównej stronie konfiguracji. Tutaj połączysz swój sklep z Facebookiem i dostosujesz sposób śledzenia zdarzeń.

#### Zakładka Ustawienia ogólne

-   **Identyfikator(y) piksela:**

    -   **Co robi to ustawienie:** Jest to unikalny identyfikator Twojego Piksela Facebooka. Możesz go znaleźć w Menedżerze Firmy Facebooka lub Menedżerze Zdarzeń. Możesz wprowadzić wiele identyfikatorów pikseli oddzielonych przecinkami, jeśli zarządzasz kilkoma pikselami.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wypełnieniu:* Moduł osadzi kod Piksela Facebooka w panelu front-office Twojego sklepu, wysyłając dane do określonego(ych) identyfikatora(ów) piksela.
        -   *Po pozostawieniu pustego:* Nie będzie śledzenia Piksela Facebooka.
    -   **Zalecana wartość:** Twój główny identyfikator Piksela Facebooka.
    -   **Scenariusz / przykład sprzedawcy:** Masz główny piksel dla swojej marki i dodatkowy piksel dla konkretnej linii produktów. Wprowadź oba tutaj: `1234567890,9876543210`.
-   **Token dostępu CAPI:**

    -   **Co robi to ustawienie:** Ten token umożliwia Facebook Conversions API (CAPI), które wysyła dane konwersji bezpośrednio z Twojego serwera do Facebooka, omijając ograniczenia przeglądarki (takie jak blokery reklam lub ograniczenia plików cookie). Poprawia to dokładność danych.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wypełnieniu:* Moduł spróbuje wysłać zdarzenia po stronie serwera do Facebooka za pomocą CAPI, dodatkowo lub zamiast zdarzeń piksela po stronie przeglądarki, w zależności od innych ustawień.
        -   *Po pozostawieniu pustego:* Będzie miało miejsce tylko śledzenie piksela po stronie przeglądarki (jeśli ustawiono identyfikator piksela).
    -   **Zalecana wartość:** Zdecydowanie zaleca się używanie CAPI dla lepszej dokładności danych. Wygeneruj ten token w Menedżerze Zdarzeń Facebooka.
    -   **Scenariusz / przykład sprzedawcy:** Chcesz zapewnić maksymalną dokładność danych dla zdarzeń zakupu, nawet jeśli klienci używają blokerów reklam. Generujesz token dostępu w Menedżerze Zdarzeń Facebooka i wklejasz go tutaj.
-   **Kod zdarzenia testowego:**

    -   **Co robi to ustawienie:** Ten kod służy do testowania konfiguracji CAPI w Menedżerze Zdarzeń Facebooka. Po wprowadzeniu moduł wyśle zdarzenia testowe, umożliwiając weryfikację prawidłowego działania śledzenia po stronie serwera.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wypełnieniu:* Zdarzenia CAPI będą zawierać ten kod testowy, dzięki czemu będą widoczne w zakładce „Testuj zdarzenia” w Menedżerze Zdarzeń Facebooka.
        -   *Po pozostawieniu pustego:* Zdarzenia CAPI będą wysyłane jako zdarzenia na żywo.
    -   **Zalecana wartość:** Używaj tylko podczas aktywnego testowania konfiguracji CAPI. Usuń go po zakończeniu testowania.
    -   **Scenariusz / przykład sprzedawcy:** Właśnie skonfigurowałeś CAPI i chcesz potwierdzić, że wysyła dane. Kopiujesz kod testowy z Menedżera Zdarzeń Facebooka, wklejasz go tutaj, wykonujesz testowy zakup na swojej stronie, a następnie sprawdzasz zakładkę „Testuj zdarzenia” na Facebooku.
-   **Tryb zgody:**

    -   **Co robi to ustawienie:** Ta opcja integruje się z rozwiązaniem do zarządzania zgodą na pliki cookie w Twoim sklepie (np. moduły RODO). Określa, czy zdarzenia Piksela Facebooka są wyzwalane tylko po wyrażeniu zgody przez klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zdarzenia piksela będą wyzwalane tylko wtedy, gdy klient zaakceptował pliki cookie.
        -   *Po wyłączeniu:* Zdarzenia piksela będą wyzwalane niezależnie od zgody na pliki cookie (używaj ostrożnie, w zależności od lokalnych przepisów dotyczących prywatności).
    -   **Zalecana wartość:** „Tak”, jeśli działasz w regionach z surowymi przepisami dotyczącymi prywatności (takimi jak RODO w Europie).
    -   **Scenariusz / przykład sprzedawcy:** Twój sklep jest skierowany do klientów w UE. Włączasz to ustawienie, aby zachować zgodność z RODO, zapewniając, że dane piksela są zbierane tylko od użytkowników, którzy wyraźnie zgadzają się na użycie plików cookie.
-   **Statusy opłacone:**

    -   **Co robi to ustawienie:** Wybiera, które statusy zamówień w PrestaShop powinny wyzwalać zdarzenie „Purchase” na Facebooku. Zazwyczaj obejmuje to statusy takie jak „Płatność zaakceptowana” lub „Dostarczono”.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wybraniu:* Zamówienia osiągające te statusy wyślą zdarzenie „Purchase” na Facebooka.
        -   *Po niewybraniu:* Zamówienia nie wyślą zdarzenia „Purchase” po osiągnięciu tych statusów.
    -   **Zalecana wartość:** Wybierz wszystkie statusy, które faktycznie reprezentują zakończone i opłacone zamówienie.
    -   **Scenariusz / przykład sprzedawcy:** Uważasz zamówienie za „opłacone”, gdy jest „Płatność zaakceptowana” i „Wysłane”. Wybierasz oba te statusy.
-   **Statusy zwrotu / anulowania:**

    -   **Co robi to ustawienie:** Wybiera, które statusy zamówień wskazują na zwrot lub anulowanie. Pozwala to modułowi potencjalnie wysłać zdarzenie „Refund” lub „Cancel” (jeśli jest obsługiwane przez API Facebooka i wersję modułu) lub zapobiec fałszywym pozytywnym śledzeniom zakupu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wybraniu:* Moduł rozpozna te zamówienia jako niezakupowe lub zwrócone.
        -   *Po niewybraniu:* Te zamówienia mogą nadal być liczone jako zakupy, jeśli wcześniej osiągnęły „Status opłacony”.
    -   **Zalecana wartość:** Wybierz statusy takie jak „Anulowano”, „Zwrócono”, „Błąd płatności”.
    -   **Scenariusz / przykład sprzedawcy:** Klient anuluje zamówienie. Chcesz upewnić się, że nie zostanie to policzone jako udany zakup. Wybierasz tutaj „Anulowano” i „Zwrócono”.

#### Zakładka Ustawienia zaawansowane

-   **Selektor CSS „Dodaj do koszyka”:**

    -   **Co robi to ustawienie:** Jest to ustawienie techniczne, które pomaga modułowi zidentyfikować przycisk „Dodaj do koszyka” na stronach produktów. Jeśli Twój motyw używa niestandardowego przycisku, może być konieczne określenie jego selektora CSS.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po poprawnym ustawieniu:* Zdarzenie „AddToCart” zostanie niezawodnie wyzwolone, gdy klient kliknie przycisk.
        -   *Po niepoprawnym lub pustym (i niepowodzeniu automatycznego wykrywania):* Zdarzenie „AddToCart” może nie zostać wyzwolone, co prowadzi do brakujących danych.
    -   **Zalecana wartość:** Najpierw pozostaw puste; moduł często automatycznie wykrywa. Jeśli brakuje zdarzeń „AddToCart”, skonsultuj się z twórcą motywu lub użyj inspektora przeglądarki, aby znaleźć prawidłowy selektor CSS (np. `.add-to-cart-button`).
    -   **Scenariusz / przykład sprzedawcy:** Twój niestandardowy motyw ma unikalny przycisk „Dodaj do koszyka”. Sprawdzasz przycisk w przeglądarce i znajdujesz jego klasę `my-custom-add-button`. Wprowadzasz `.my-custom-add-button` tutaj.
-   **Selektor CSS ceny produktu:**

    -   **Co robi to ustawienie:** Podobnie jak selektor „Dodaj do koszyka”, pomaga modułowi dokładnie znaleźć cenę produktu na stronie, zwłaszcza w przypadku dynamicznych cen lub specyficznych układów motywu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po poprawnym ustawieniu:* Parametr „value” dla zdarzeń takich jak „ViewContent” i „AddToCart” będzie dokładnie odzwierciedlał cenę produktu.
        -   *Po niepoprawnym lub pustym (i niepowodzeniu automatycznego wykrywania):* Parametr „value” może być brakujący lub niepoprawny, co wpływa na optymalizację reklam.
    -   **Zalecana wartość:** Najpierw pozostaw puste. Jeśli wartości cen są niepoprawne w Menedżerze Zdarzeń Facebooka, znajdź prawidłowy selektor CSS (np. `.current-price span[itemprop="price"]`).
    -   **Scenariusz / przykład sprzedawcy:** Twoja strona produktu wyświetla ceny w niestandardowy sposób. Identyfikujesz selektor CSS dla elementu ceny, aby upewnić się, że Facebook otrzymuje prawidłową wartość.
-   **Identyfikacja produktu:**

    -   **Co robi to ustawienie:** Określa, który identyfikator produktu (ID) Twój sklep wysyła do Facebooka. Opcje zazwyczaj obejmują `ID` (wewnętrzny identyfikator produktu PrestaShop), `Reference` (SKU Twojego produktu) lub `EAN13` / `UPC` (numery kodów kreskowych). Jest to kluczowe dla dopasowania produktów w Twoim Katalogu Produktów Facebooka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po ustawieniu:* Facebook otrzyma wybrany typ identyfikatora, który powinien pasować do identyfikatorów w Twoim Katalogu Produktów Facebooka, aby dynamiczne reklamy działały.
        -   *Po niedopasowaniu do Twojego katalogu:* Dynamiczne reklamy mogą nie wyświetlać prawidłowych produktów lub mogą w ogóle się nie wyświetlać.
    -   **Zalecana wartość:** Wybierz identyfikator, którego konsekwentnie używasz w swoim Katalogu Produktów Facebooka. `Reference` (SKU) jest często dobrym wyborem, jeśli jest unikalny.
    -   **Scenariusz / przykład sprzedawcy:** Twój Katalog Produktów Facebooka używa SKU Twojego produktu jako unikalnego identyfikatora. Wybierasz tutaj „Reference”, aby zapewnić idealne dopasowanie.
-   **Separator:**

    -   **Co robi to ustawienie:** Jeśli używasz kombinacji identyfikatora produktu i identyfikatora atrybutu (np. dla różnych rozmiarów/kolorów), definiuje to znak używany do ich oddzielenia w identyfikatorze Facebooka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po ustawieniu:* Identyfikator produktu wysyłany do Facebooka będzie `ProductID` + `Separator` + `AttributeID`.
        -   *Po pozostawieniu pustego:* Może być wysyłany tylko podstawowy identyfikator produktu, co potencjalnie powoduje problemy ze śledzeniem konkretnych wariantów produktu.
    -   **Zalecana wartość:** Powszechny separator, taki jak `-` lub `_`.
    -   **Scenariusz / przykład sprzedawcy:** Sprzedajesz koszulkę (ID 123) w różnych rozmiarach (ID atrybutu 10 dla S, 11 dla M). Jeśli ustawisz separator na `-`, Facebook otrzyma `123-10` dla małej koszulki.
-   **Prefiks ID produktu / Sufiks ID produktu:**

    -   **Co robi to ustawienie:** Pozwala dodać tekst przed lub po identyfikatorze produktu wysyłanym do Facebooka. Jest to przydatne, jeśli identyfikatory w Twoim Katalogu Produktów Facebooka mają określony format, który różni się od identyfikatorów PrestaShop.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po ustawieniu:* Ostateczny identyfikator produktu wysyłany do Facebooka będzie `Prefiks` + `ProductID` + `Sufiks`.
        -   *Po pozostawieniu pustego:* Wysyłany jest tylko surowy identyfikator produktu (i separator/identyfikator atrybutu, jeśli dotyczy).
    -   **Zalecana wartość:** Pozostaw puste, chyba że wymaga tego Twój Katalog Produktów Facebooka.
    -   **Scenariusz / przykład sprzedawcy:** Twój Katalog Produktów Facebooka wymaga, aby wszystkie identyfikatory produktów zaczynały się od „PS\_”. Wprowadzasz `PS_` w polu „Prefiks ID produktu”.
-   **Waluta docelowa:**

    -   **Co robi to ustawienie:** Określa walutę, w której wartości zdarzeń (takie jak kwota zakupu) są wysyłane do Facebooka. Jest to kluczowe dla dokładnego raportowania i optymalizacji reklam, zwłaszcza w przypadku sklepów wielowalutowych.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po ustawieniu:* Wszystkie wartości zdarzeń zostaną przeliczone i wysłane w tej walucie docelowej.
        -   *Po pozostawieniu pustego:* Moduł spróbuje użyć waluty bieżącego kontekstu sklepu lub wybranej waluty klienta.
    -   **Zalecana wartość:** Twoja główna waluta reklamowa (np. USD, EUR).
    -   **Scenariusz / przykład sprzedawcy:** Twój sklep sprzedaje w EUR, USD i GBP, ale wszystkie Twoje reklamy na Facebooku są zarządzane w USD. Ustawiasz „Walutę docelową” na „USD”, aby zapewnić spójne raportowanie wszystkich wartości konwersji w USD.

#### Zakładka Ustawienia śledzenia zdarzeń

Ta sekcja pozwala włączyć lub wyłączyć konkretne zdarzenia Piksela Facebooka. Włączaj tylko te zdarzenia, które aktywnie chcesz śledzić.

-   **Zdarzenie Pageview:**

    -   **Co robi to ustawienie:** Śledzi, kiedy klient przegląda dowolną stronę w Twojej witrynie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zdarzenie `PageView` jest wysyłane przy każdym załadowaniu strony.
        -   *Po wyłączeniu:* Nie są wysyłane żadne zdarzenia `PageView`.
    -   **Zalecana wartość:** Tak. Jest to podstawowe zdarzenie dla wszystkich śledzeń.
-   **Zdarzenie Purchase:**

    -   **Co robi to ustawienie:** Śledzi, kiedy klient dokonuje zakupu. Jest to najważniejsze zdarzenie konwersji.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zdarzenie `Purchase` jest wysyłane na stronie potwierdzenia zamówienia i/lub za pośrednictwem CAPI, gdy zamówienie osiągnie „Status opłacony”.
        -   *Po wyłączeniu:* Nie są wysyłane żadne zdarzenia `Purchase`.
    -   **Zalecana wartość:** Tak. Absolutnie niezbędne dla reklamy e-commerce.
-   **Zdarzenie ViewContent:**

    -   **Co robi to ustawienie:** Śledzi, kiedy klient przegląda stronę produktu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zdarzenie `ViewContent` jest wysyłane po załadowaniu strony produktu.
        -   *Po wyłączeniu:* Nie są wysyłane żadne zdarzenia `ViewContent`.
    -   **Zalecana wartość:** Tak. Ważne dla dynamicznych reklam produktów i remarketingu.
-   **Zdarzenie AddToCart:**

    -   **Co robi to ustawienie:** Śledzi, kiedy klient dodaje przedmiot do koszyka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zdarzenie `AddToCart` jest wysyłane po dodaniu przedmiotu do koszyka.
        -   *Po wyłączeniu:* Nie są wysyłane żadne zdarzenia `AddToCart`.
    -   **Zalecana wartość:** Tak. Kluczowe dla kampanii odzyskiwania porzuconych koszyków.
-   **Zdarzenie RemoveFromCart:**

    -   **Co robi to ustawienie:** Śledzi, kiedy klient usuwa przedmiot z koszyka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zdarzenie `RemoveFromCart` jest wysyłane po usunięciu przedmiotu.
        -   *Po wyłączeniu:* Nie są wysyłane żadne zdarzenia `RemoveFromCart`.
    -   **Zalecana wartość:** Tak. Może dostarczyć wglądu w zachowania klientów i zainteresowanie produktami.
-   **Zdarzenie InitiateCheckout:**

    -   **Co robi to ustawienie:** Śledzi, kiedy klient rozpoczyna proces realizacji zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zdarzenie `InitiateCheckout` jest wysyłane, gdy klient wchodzi w pierwszy krok realizacji zamówienia.
        -   *Po wyłączeniu:* Nie są wysyłane żadne zdarzenia `InitiateCheckout`.
    -   **Zalecana wartość:** Tak. Przydatne do zrozumienia wydajności lejka realizacji zamówienia.
-   **Zdarzenie Search:**

    -   **Co robi to ustawienie:** Śledzi, kiedy klient używa wewnętrznej funkcji wyszukiwania w Twoim sklepie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zdarzenie `Search` jest wysyłane z zapytaniem wyszukiwania.
        -   *Po wyłączeniu:* Nie są wysyłane żadne zdarzenia `Search`.
    -   **Zalecana wartość:** Tak. Dostarcza cennych danych o tym, czego szukają klienci.
-   **Zdarzenie AddToWishlist:**

    -   **Co robi to ustawienie:** Śledzi, kiedy klient dodaje produkt do swojej listy życzeń.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zdarzenie `AddToWishlist` jest wysyłane.
        -   *Po wyłączeniu:* Nie są wysyłane żadne zdarzenia `AddToWishlist`.
    -   **Zalecana wartość:** Tak, jeśli Twój sklep korzysta z funkcji listy życzeń.
-   **Zdarzenie AddPaymentInfo:**

    -   **Co robi to ustawienie:** Śledzi, kiedy klient wybiera metodę płatności podczas realizacji zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zdarzenie `AddPaymentInfo` jest wysyłane.
        -   *Po wyłączeniu:* Nie są wysyłane żadne zdarzenia `AddPaymentInfo`.
    -   **Zalecana wartość:** Tak. Pomaga analizować preferencje dotyczące metod płatności i potencjalne porzucenia.
-   **Zdarzenie Contact:**

    -   **Co robi to ustawienie:** Śledzi, kiedy klient odwiedza Twoją stronę kontaktową.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zdarzenie `Contact` jest wysyłane.
        -   *Po wyłączeniu:* Nie są wysyłane żadne zdarzenia `Contact`.
    -   **Zalecana wartość:** Tak. Przydatne do śledzenia zapytań obsługi klienta.
-   **Zdarzenie Lead:**

    -   **Co robi to ustawienie:** Śledzi, kiedy klient wykonuje działanie, które wskazuje na zainteresowanie Twoimi produktami lub usługami, ale nie jest bezpośrednim zakupem (np. zapis do newslettera, utworzenie konta).
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zdarzenie `Lead` jest wysyłane przy rejestracji do newslettera i/lub utworzeniu konta.
        -   *Po wyłączeniu:* Nie są wysyłane żadne zdarzenia `Lead`.
    -   **Zalecana wartość:** Tak. Ważne dla kampanii generowania leadów.
-   **Zdarzenie CompleteRegistration:**

    -   **Co robi to ustawienie:** Śledzi, kiedy klient pomyślnie tworzy konto w Twoim sklepie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Zdarzenie `CompleteRegistration` jest wysyłane.
        -   *Po wyłączeniu:* Nie są wysyłane żadne zdarzenia `CompleteRegistration`.
    -   **Zalecana wartość:** Tak. Przydatne do śledzenia pozyskiwania nowych klientów.

#### Zakładka Statystyki na żywo

Ta zakładka dostarcza wglądu w czasie rzeczywistym w zdarzenia wysyłane z Twojego sklepu do Facebooka, pomagając monitorować stan Twojego piksela.

-   **Przechowuj zdarzenia przez (dni):**

    -   **Co robi to ustawienie:** Określa, jak długo moduł przechowuje dane zdarzeń lokalnie do wyświetlenia w zakładce Statystyki na żywo.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po ustawieniu:* Dane zdarzeń starsze niż ta liczba dni zostaną automatycznie usunięte.
        -   *Po ustawieniu na 0:* Zdarzenia nie są przechowywane lokalnie (a Statystyki na żywo nie będą wyświetlać danych).
    -   **Zalecana wartość:** 7-30 dni, w zależności od tego, ile danych historycznych chcesz przeglądać.
    -   **Scenariusz / przykład sprzedawcy:** Chcesz przejrzeć zdarzenia z ostatniego tygodnia. Ustawiasz to na `7`.
-   **Interwał odświeżania na żywo (sekundy):**

    -   **Co robi to ustawienie:** Kontroluje, jak często zakładka Statystyki na żywo odświeża się, aby pokazać nowe zdarzenia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po ustawieniu:* Tabela Statystyk na żywo będzie aktualizowana co X sekund.
        -   *Po ustawieniu na 0:* Statystyki na żywo nie będą się automatycznie odświeżać.
    -   **Zalecana wartość:** 5-10 sekund dla aktywnego monitorowania.
    -   **Scenariusz / przykład sprzedawcy:** Aktywnie testujesz swój piksel i chcesz, aby zdarzenia pojawiały się niemal natychmiast. Ustawiasz to na `5`.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Ustawienia ogólne | Identyfikator(y) piksela | Twój identyfikator Piksela Facebooka | Łączy Twój sklep z Pikselem Facebooka w celu śledzenia. |
| Ustawienia ogólne | Token dostępu CAPI | Twój token dostępu CAPI | Umożliwia śledzenie po stronie serwera dla lepszej dokładności danych. |
| Ustawienia ogólne | Kod zdarzenia testowego | Puste (używaj tylko do testowania) | Wysyła zdarzenia testowe do Menedżera Zdarzeń Facebooka. |
| Ustawienia ogólne | Tryb zgody | Tak (dla zgodności z RODO) | Wyzwala zdarzenia piksela tylko po zgodzie klienta. |
| Ustawienia ogólne | Statusy opłacone | Płatność zaakceptowana, Dostarczono | Definiuje, które statusy zamówień wyzwalają zdarzenie „Purchase”. |
| Ustawienia ogólne | Statusy zwrotu / anulowania | Anulowano, Zwrócono | Definiuje, które statusy zamówień są uważane za niezakupowe. |
| Ustawienia zaawansowane | Selektor CSS „Dodaj do koszyka” | Puste (auto-wykrywanie) | Pomaga zidentyfikować przycisk „Dodaj do koszyka” do śledzenia. |
| Ustawienia zaawansowane | Selektor CSS ceny produktu | Puste (auto-wykrywanie) | Pomaga zidentyfikować cenę produktu dla wartości zdarzeń. |
| Ustawienia zaawansowane | Identyfikacja produktu | Reference (SKU) | Określa, który identyfikator produktu jest wysyłany do Facebooka. |
| Ustawienia zaawansowane | Separator | - (myślnik) | Separator dla identyfikatora produktu i identyfikatora atrybutu. |
| Ustawienia zaawansowane | Prefiks ID produktu | Puste | Dodaje prefiks do identyfikatora produktu wysyłanego do Facebooka. |
| Ustawienia zaawansowane | Sufiks ID produktu | Puste | Dodaje sufiks do identyfikatora produktu wysyłanego do Facebooka. |
| Ustawienia zaawansowane | Waluta docelowa | Twoja główna waluta reklamowa | Konwertuje wartości zdarzeń na określoną walutę. |
| Śledzenie zdarzeń | Zdarzenie Pageview | Tak | Śledzi wszystkie wyświetlenia stron. |
| Śledzenie zdarzeń | Zdarzenie Purchase | Tak | Śledzi zakończone zakupy. |
| Śledzenie zdarzeń | Zdarzenie ViewContent | Tak | Śledzi wyświetlenia stron produktów. |
| Śledzenie zdarzeń | Zdarzenie AddToCart | Tak | Śledzi przedmioty dodane do koszyka. |
| Śledzenie zdarzeń | Zdarzenie RemoveFromCart | Tak | Śledzi przedmioty usunięte z koszyka. |
| Śledzenie zdarzeń | Zdarzenie InitiateCheckout | Tak | Śledzi rozpoczęcie realizacji zamówienia. |
| Śledzenie zdarzeń | Zdarzenie Search | Tak | Śledzi wewnętrzne wyszukiwania w witrynie. |
| Śledzenie zdarzeń | Zdarzenie AddToWishlist | Tak (jeśli używana jest lista życzeń) | Śledzi przedmioty dodane do listy życzeń. |
| Śledzenie zdarzeń | Zdarzenie AddPaymentInfo | Tak | Śledzi dodanie informacji o płatności podczas realizacji zamówienia. |
| Śledzenie zdarzeń | Zdarzenie Contact | Tak | Śledzi wizyty na stronie kontaktowej. |
| Śledzenie zdarzeń | Zdarzenie Lead | Tak | Śledzi zapisy do newslettera/tworzenie kont. |
| Śledzenie zdarzeń | Zdarzenie CompleteRegistration | Tak | Śledzi pomyślne rejestracje kont. |
| Statystyki na żywo | Przechowuj zdarzenia przez (dni) | 7-30 | Okres przechowywania lokalnych danych zdarzeń. |
| Statystyki na żywo | Interwał odświeżania na żywo (sekundy) | 5-10 | Częstotliwość odświeżania wyświetlania Statystyk na żywo. |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### AdminFbpixelAjaxController (Panel administracyjny > Moduły > Pixel śledzenia konwersji Fb > Zakładka Statystyki na żywo)

Ten kontroler zasila zakładkę „Statystyki na żywo” w konfiguracji modułu. Nie ma on oddzielnego elementu menu, ale jest integralną częścią interfejsu konfiguracji modułu.

-   **Nazwa ekranu i lokalizacja w menu:** Dostęp poprzez **Moduły > Menedżer modułów > Pixel śledzenia konwersji Fb > Konfiguruj**, a następnie kliknięcie zakładki **„Statystyki na żywo”**.
-   **Dostępne działania i ustawienia:** Ten ekran wyświetla siatkę lub tabelę ostatnich zdarzeń Piksela Facebooka, które zostały wyzwolone z Twojego sklepu. Pokazuje szczegóły, takie jak nazwa zdarzenia (np. `PageView`, `AddToCart`, `Purchase`), sygnatura czasowa, powiązany identyfikator piksela i często parametry wysłane ze zdarzeniem (np. identyfikator produktu, wartość, waluta).
-   **Efekt zmian:** Na tym ekranie nie ma bezpośrednich „ustawień” do zmiany. Jest to narzędzie monitorujące. Wyświetlane dane są zależne od ustawień „Przechowuj zdarzenia przez (dni)” i „Interwał odświeżania na żywo (sekundy)” na tej samej stronie konfiguracji.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Regularnie sprawdzaj tę zakładkę, zwłaszcza po wprowadzeniu zmian w sklepie lub uruchomieniu nowych produktów, aby upewnić się, że Twój Piksel Facebooka działa prawidłowo i wysyła dokładne dane. Jest to Twoja pierwsza linia obrony w rozwiązywaniu problemów z pikselem, zanim sprawdzisz Menedżera Zdarzeń Facebooka.

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje rozszerzenie Facebook Pixel Helper Chrome nie pokazuje piksela lub wyświetla błędy. Co powinienem zrobić?**

-   **O:** Najpierw upewnij się, że poprawnie wprowadziłeś „Identyfikator(y) piksela” w konfiguracji modułu.
-   **O:** Sprawdź, czy włączony jest „Tryb zgody”. Jeśli tak, może być konieczne zaakceptowanie plików cookie w Twoim sklepie, aby piksel się uruchomił.
-   **O:** Wyczyść pamięć podręczną PrestaShop (Parametry zaawansowane > Wydajność > Wyczyść pamięć podręczną).
-   **O:** Jeśli używasz niestandardowego motywu, mogą występować konflikty. Tymczasowo przełącz się na domyślny motyw PrestaShop, aby to wykluczyć.
-   **O:** Użyj narzędzia „Testuj zdarzenia” Facebooka w Menedżerze Zdarzeń, aby sprawdzić, czy zdarzenia są odbierane.

**P2: Moje zdarzenia zakupu nie wyświetlają się poprawnie w Menedżerze Zdarzeń Facebooka.**

-   **O:** Sprawdź, czy Twoje „Statusy opłacone” są poprawnie wybrane w konfiguracji modułu. Tylko zamówienia osiągające te statusy wyzwolą zdarzenie zakupu.
-   **O:** Jeśli używasz CAPI, upewnij się, że Twój „Token dostępu CAPI” jest poprawny i przetestuj go za pomocą funkcji „Kod zdarzenia testowego”.
-   **O:** Sprawdź, czy Twoja „Waluta docelowa” jest poprawnie ustawiona, zwłaszcza w przypadku sklepów wielowalutowych.
-   **O:** Przejrzyj zakładkę „Statystyki na żywo” w konfiguracji modułu, aby sprawdzić, czy moduł wewnętrznie rejestruje zdarzenia zakupu.

**P3: Dynamiczne reklamy produktów nie wyświetlają prawidłowych produktów lub w ogóle żadnych produktów.**

-   **O:** Najczęstszą przyczyną jest niedopasowanie między ustawieniem „Identyfikacja produktu” w module a identyfikatorami w Twoim Katalogu Produktów Facebooka. Upewnij się, że są identyczne (np. jeśli Twój katalog używa SKU, ustaw moduł na „Reference”).
-   **O:** Upewnij się, że Twój Katalog Produktów Facebooka jest aktualny i wolny od błędów.
-   **O:** Sprawdź, czy zdarzenia „ViewContent” i „AddToCart” są prawidłowo wyzwalane z parametrem `content_ids` pasującym do identyfikatorów Twojego katalogu.

**P4: Jak zapewnić zgodność z RODO lub innymi przepisami dotyczącymi prywatności za pomocą tego modułu?**

-   **O:** Włącz ustawienie „Tryb zgody” w module. Zintegruje się to z Twoim istniejącym modułem zgody na pliki cookie (jeśli jest prawidłowo skonfigurowany), aby wyzwalać piksel tylko po wyraźnej zgodzie użytkownika.
-   **O:** Upewnij się, że polityka prywatności Twojego sklepu jasno określa, że używasz Piksela Facebooka do celów reklamowych i analitycznych, oraz jak użytkownicy mogą zrezygnować lub zarządzać swoimi preferencjami dotyczącymi plików cookie.

**P5: Zdarzenie „Dodaj do koszyka” nie jest wyzwalane na mojej stronie produktu.**

-   **O:** Twój motyw może mieć niestandardowy przycisk „Dodaj do koszyka”, którego moduł nie może automatycznie wykryć. Spróbuj zbadać przycisk „Dodaj do koszyka” na stronie produktu za pomocą narzędzi deweloperskich przeglądarki (prawy przycisk myszy > Zbadaj), aby znaleźć jego klasę CSS lub ID. Następnie wprowadź to w polu „Selektor CSS „Dodaj do koszyka”” w konfiguracji modułu (np. `.my-custom-atc-button` lub `#add_to_cart_button`).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Fb conversion tracking pixel` stosuje standardową architekturę modułu PrestaShop, wykorzystując hooki do wstrzykiwania zdarzeń do front-office oraz AdminController do interakcji AJAX w back-office (Statystyki na żywo). W dużym stopniu opiera się na wzorcu fabryki (`FbpixelTrackerFactory`) do zarządzania różnymi mechanizmami śledzenia (piksel po stronie przeglądarki, CAPI po stronie serwera). Dane zdarzeń są zbierane i przetwarzane przez dedykowane klasy (`FbpixelEvents`, `FbpixelPixelTracker`, `FbpixelCapiTracker`), a następnie wysyłane. Konfiguracja jest przechowywana w `ps_configuration`. Moduł zawiera również solidne narzędzia do debugowania i sprawdzania stanu.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/ajax.php`
        -   **Nazwa klasy:** `FbpixelAjaxModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność:** Obsługuje żądania AJAX z front-office, głównie do zbierania i logowania danych zdarzeń w czasie rzeczywistym dla funkcji Statystyk na żywo. Może być również używany do konkretnych wyzwalaczy zdarzeń, których nie można obsłużyć wyłącznie po stronie klienta (np. `RemoveFromCart` po aktualizacji koszyka).
    -   `controllers/front/cron.php`
        -   **Nazwa klasy:** `FbpixelCronModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność:** Zaprojektowany do wywoływania przez zadanie cron. Ten kontroler jest prawdopodobnie odpowiedzialny za przetwarzanie zdarzeń CAPI w kolejce, wykonywanie czyszczenia danych (np. usuwanie starych wpisów Statystyk na żywo) lub innych zaplanowanych zadań.
    -   `controllers/front/index.php`
        -   **Nazwa klasy:** `FbpixelIndexModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność:** Kontroler zastępczy lub awaryjny, często używany do zapobiegania listowaniu katalogów lub dostarczania domyślnej odpowiedzi dla tras specyficznych dla modułu.
    -   `controllers/front/sync.php`
        -   **Nazwa klasy:** `FbpixelSyncModuleFrontController` (rozszerza `ModuleFrontController`)
        -   **Odpowiedzialność:** Potencjalnie obsługuje zadania synchronizacji, takie jak przesyłanie aktualizacji katalogu produktów lub innych danych do Facebooka, lub odbieranie danych z Facebooka.
-   **Kontrolery administracyjne Back-Office**:

    -   `controllers/admin/AdminFbpixelAjaxController.php`
        -   **Nazwa klasy:** `AdminFbpixelAjaxController` (rozszerza `ModuleAdminController`)
        -   **Nazwa zakładki:** Nie jest to samodzielna zakładka, ale zintegrowana z konfiguracją modułu.
        -   **Zarządzana encja:** Zarządza żądaniami AJAX ze strony konfiguracji back-office modułu, w szczególności do pobierania i wyświetlania danych zdarzeń „Statystyk na żywo”. Dostarcza dane dla szablonu `recent-events.tpl`.

### 4.3 Klasy i modele rdzenia (`classes/`)

-   `fbpixel/classes/autoload.php`: Obsługuje niestandardowe ładowanie klas dla modułu.
-   `fbpixel/classes/FbpixelCapiClient.php`:
    -   **Odpowiedzialność:** Hermetyzuje logikę do wykonywania żądań HTTP do Facebook Conversions API. Obsługuje uwierzytelnianie, formatowanie żądań i obsługę błędów.
-   `fbpixel/classes/FbpixelCapiTracker.php`:
    -   **Odpowiedzialność:** Implementuje `FbpixelTrackerInterface` do śledzenia zdarzeń po stronie serwera. Formatuje dane zdarzeń zgodnie ze specyfikacjami CAPI i wysyła je za pośrednictwem `FbpixelCapiClient`.
-   `fbpixel/classes/FbpixelCatalogDoctor.php`:
    -   **Odpowiedzialność:** Dostarcza narzędzia i logikę do diagnozowania problemów związanych z dopasowaniem katalogu produktów i spójnością danych między PrestaShop a Facebookiem.
-   `fbpixel/classes/FbpixelConsent.php`:
    -   **Odpowiedzialność:** Zarządza i sprawdza status zgody użytkownika, integrując się z mechanizmami zgody na pliki cookie PrestaShop (jeśli są dostępne), aby zapewnić zgodność z RODO.
-   `fbpixel/classes/FbpixelCurrencyHelper.php`:
    -   **Odpowiedzialność:** Klasa narzędziowa do konwersji i formatowania walut, zapewniająca, że wartości zdarzeń są wysyłane w prawidłowej walucie docelowej.
-   `fbpixel/classes/FbpixelEmqCoach.php`:
    -   **Odpowiedzialność:** Prawdopodobnie dostarcza wskazówek lub zaleceń dotyczących poprawy jakości dopasowania zdarzeń (EMQ) dla zdarzeń Facebooka.
-   `fbpixel/classes/FbpixelEventId.php`:
    -   **Odpowiedzialność:** Generuje i zarządza unikalnymi identyfikatorami zdarzeń, kluczowymi do deduplikacji między zdarzeniami po stronie przeglądarki i po stronie serwera.
-   `fbpixel/classes/FbpixelEvents.php`:
    -   **Odpowiedzialność:** Centralna klasa do definiowania i zarządzania różnymi typami zdarzeń Piksela Facebooka (PageView, Purchase, AddToCart itp.) i ich standardowymi parametrami.
-   `fbpixel/classes/FbpixelHealthScore.php`:
    -   **Odpowiedzialność:** Oblicza i wyświetla „wynik zdrowia” konfiguracji piksela, identyfikując potencjalne problemy lub obszary do poprawy.
-   `fbpixel/classes/FbpixelLiveStats.php`:
    -   **Tabela bazy danych:** `ps_fbpixel_events` (prawdopodobnie, na podstawie funkcjonalności)
    -   **Rozszerza:** Prawdopodobnie `ObjectModel`
    -   **Odpowiedzialność:** Przechowuje i pobiera dane zdarzeń lokalnie dla funkcji „Statystyki na żywo” w back-office. Obsługuje przechowywanie i usuwanie danych.
-   `fbpixel/classes/FbpixelPixelRules.php`:
    -   **Odpowiedzialność:** Definiuje zasady i warunki, kiedy konkretne zdarzenia piksela powinny być wyzwalane, potencjalnie na podstawie typu strony, działań użytkownika lub konfiguracji.
-   `fbpixel/classes/FbpixelPixelTracker.php`:
    -   **Odpowiedzialność:** Implementuje `FbpixelTrackerInterface` do śledzenia zdarzeń po stronie przeglądarki. Generuje kod JavaScript dla wywołań `fbq()` i wstrzykuje go do front-office.
-   `fbpixel/classes/FbpixelProductIdResolver.php`:
    -   **Odpowiedzialność:** Rozwiązuje prawidłowy identyfikator produktu i identyfikator atrybutu na podstawie konfiguracji modułu (prefiks, sufiks, separator, wybrany typ identyfikatora) do wysyłania do Facebooka.
-   `fbpixel/classes/FbpixelTrackerFactory.php`:
    -   **Odpowiedzialność:** Klasa fabryczna, która tworzy odpowiedni tracker (np. `FbpixelPixelTracker` dla przeglądarki, `FbpixelCapiTracker` dla serwera) na podstawie konfiguracji modułu i kontekstu.
-   `fbpixel/classes/FbpixelTrackerInterface.php`:
    -   **Odpowiedzialność:** Definiuje wspólny interfejs dla wszystkich klas śledzących, zapewniając spójne sygnatury metod dla wysyłania zdarzeń.
-   `fbpixel/classes/FbpixelUserData.php`:
    -   **Odpowiedzialność:** Zbieranie i formatowanie danych użytkownika (np. e-mail, telefon, adres IP) do wysyłania ze zdarzeniami CAPI, kluczowe dla jakości dopasowania zdarzeń.
-   `fbpixel/classes/index.php`: Pusty plik, zazwyczaj używany do zapobiegania listowaniu katalogów.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `fbpixel/lib/searchTool/views/js/autocomplete.js`:
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Zapewnia funkcjonalność autouzupełniania dla pól wejściowych, prawdopodobnie używaną w konfiguracji modułu do wyboru produktów, kategorii lub innych encji.
-   `fbpixel/views/js/fbpixel-admin.js`:
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Obsługuje ogólną logikę administracyjną dla strony konfiguracji modułu, w tym przesyłanie formularzy, przełączanie zakładek i potencjalnie wywołania AJAX do `AdminFbpixelAjaxController`.
-   `fbpixel/views/js/fbpixel-debug.js`:
    -   **Zakres:** Front-office (warunkowo).
    -   **Szczegóły:** Dostarcza informacji debugowania w konsoli przeglądarki lub wizualnej nakładce, pokazując, które zdarzenia piksela są wyzwalane i ich parametry. Aktywowany przez ustawienie trybu debugowania.
-   `fbpixel/views/js/fbpixel-ghost.js`:
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Prawdopodobnie skrypt po stronie klienta, który pomaga wykrywać i śledzić zdarzenia, które w przeciwnym razie mogłyby zostać pominięte przez standardową obserwację DOM, takie jak dynamiczne ładowanie treści lub specyficzne interakcje AJAX.
-   `fbpixel/views/js/fbpixel-live.js`:
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Zasila zakładkę „Statystyki na żywo”, wykonując żądania AJAX do `AdminFbpixelAjaxController` w celu pobierania i wyświetlania danych zdarzeń w czasie rzeczywistym oraz obsługując interwał odpytywania.
-   `fbpixel/views/js/fbpixel-wizard.js`:
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Zarządza kreatorem konfiguracji krok po kroku, prowadząc sprzedawcę przez początkową konfigurację.
-   `fbpixel/views/js/fbpixel.js`:
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Główny skrypt JavaScript po stronie klienta dla Piksela Facebooka. Inicjalizuje funkcję `fbq()`, obsługuje nasłuchiwacze zdarzeń dla `AddToCart`, `RemoveFromCart`, `Search`, `InitiateCheckout` itp. i wysyła zdarzenia do Facebooka. Zarządza również selektorami CSS dla dynamicznych elementów.
-   `fbpixel/views/js/mp-collect.js`:
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Prawdopodobnie skrypt narzędziowy do zbierania konkretnych punktów danych z front-office, prawdopodobnie związanych z zachowaniem użytkownika lub czynnikami środowiskowymi, w celu ulepszenia parametrów zdarzeń.
-   `fbpixel/views/js/mp-front.js`:
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Ogólne narzędzia JavaScript lub funkcje pomocnicze front-office używane przez moduł.
-   `fbpixel/views/js/mp-inspect.js`:
    -   **Zakres:** Front-office (warunkowo).
    -   **Szczegóły:** Dostarcza narzędzie inspekcji, prawdopodobnie wizualną nakładkę, aby pomóc debugować i weryfikować zdarzenia piksela bezpośrednio w sklepie.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `fbpixel/lib/searchTool/views/css/autocomplete.css`:
    -   **Zakres:** Back-office.
    -   **Szczegóły:** Style dla rozwijanych list autouzupełniania i pól wejściowych używanych w interfejsie administracyjnym.
-   `fbpixel/views/css/fbpixel-admin.css`:
    -   **Zakres:** Stylizacja formularza administracyjnego back-office.
    -   **Szczegóły:** Stylizuje stronę konfiguracji modułu, zakładki, pola wejściowe i tabelę Statystyk na żywo.
-   `fbpixel/views/css/fbpixel-debug.css`:
    -   **Zakres:** Front-office (warunkowo).
    -   **Szczegóły:** Style dla nakładki debugowania lub wyjścia konsoli, czyniąc informacje debugowania bardziej czytelnymi.
-   `fbpixel/views/css/mp-inspect.css`:
    -   **Zakres:** Front-office (warunkowo).
    -   **Szczegóły:** Style dla narzędzia inspekcji front-office, jeśli jest włączone.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:

    -   `fbpixel/views/templates/hook/capi-pageview.tpl`: Renderowany w hooku (prawdopodobnie `displayHeader` lub `actionFrontControllerSetMedia`) w celu wyzwolenia zdarzenia `PageView` po stronie serwera za pośrednictwem CAPI.
    -   `fbpixel/views/templates/hook/debug.tpl`: Renderuje nakładkę debugowania lub wyjście konsoli do debugowania front-office.
    -   `fbpixel/views/templates/hook/displayOrderConfirmation.tpl`: Renderuje zdarzenie `Purchase` po stronie przeglądarki na stronie potwierdzenia zamówienia.
    -   `fbpixel/views/templates/hook/ghost.tpl`: Renderuje ukryty element lub skrypt dla funkcjonalności `fbpixel-ghost.js`.
    -   `fbpixel/views/templates/hook/header.tpl`: Renderuje podstawowy kod inicjalizacji Piksela Facebooka (`fbq('init', ...)` i `fbq('track', 'PageView')`) w sekcji `<head>`, zazwyczaj za pośrednictwem `displayHeader` lub `actionFrontControllerSetMedia`.
    -   `fbpixel/views/templates/hook/payment.tpl`: Potencjalnie używany do śledzenia zdarzeń `AddPaymentInfo` lub innych interakcji związanych z płatnościami.
    -   `fbpixel/views/templates/hook/product-details.tpl`: Renderuje skrypty lub dane specyficzne dla stron produktów, głównie dla zdarzeń `ViewContent` i `AddToCart`, prawdopodobnie wstrzykiwane za pośrednictwem `displayProductFooter` lub `displayProductAdditionalInfo`.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `fbpixel/lib/searchTool/views/scripts.tpl`: Zawiera JavaScript dla narzędzia wyszukiwania/autouzupełniania w panelu administracyjnym.
    -   `fbpixel/views/templates/admin/configure.tpl`: Główny szablon strony konfiguracji modułu, orkiestrujący wszystkie inne szablony administracyjne.
    -   `fbpixel/views/templates/admin/doctor.tpl`: Wyświetla wyniki `FbpixelCatalogDoctor` do diagnozowania problemów z katalogiem.
    -   `fbpixel/views/templates/admin/emq.tpl`: Wyświetla informacje lub zalecenia z `FbpixelEmqCoach` dotyczące jakości dopasowania zdarzeń.
    -   `fbpixel/views/templates/admin/health.tpl`: Wyświetla wynik zdrowia piksela z `FbpixelHealthScore`.
    -   `fbpixel/views/templates/admin/live-maintain.tpl`: Szablon do zarządzania ustawieniami statystyk na żywo (retencja, interwał odpytywania).
    -   `fbpixel/views/templates/admin/live.tpl`: Szablon kontenera dla zakładki „Statystyki na żywo”.
    -   `fbpixel/views/templates/admin/mode-context.tpl`: Wyświetla informacje specyficzne dla kontekstu na podstawie trybu działania piksela.
    -   `fbpixel/views/templates/admin/mode-note-capi.tpl`: Wyświetla uwagi lub ostrzeżenia specyficzne dla konfiguracji CAPI.
    -   `fbpixel/views/templates/admin/mode-note-pixel.tpl`: Wyświetla uwagi lub ostrzeżenia specyficzne dla konfiguracji piksela po stronie przeglądarki.
    -   `fbpixel/views/templates/admin/mode-picker.tpl`: Pozwala sprzedawcy wybrać tryb działania piksela (np. standardowy, debugowanie).
    -   `fbpixel/views/templates/admin/pixels-list.tpl`: Wyświetla listę skonfigurowanych identyfikatorów pikseli.
    -   `fbpixel/views/templates/admin/recent-events.tpl`: Renderuje tabelę ostatnich zdarzeń dla zakładki „Statystyki na żywo”, wypełnianą przez `AdminFbpixelAjaxController`.
    -   `fbpixel/views/templates/admin/tabs.tpl`: Renderuje nawigację po zakładkach dla strony konfiguracji modułu.
    -   `fbpixel/views/templates/admin/wizard.tpl`: Renderuje interfejs kreatora konfiguracji krok po kroku.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_configuration`: Przechowuje wszystkie ustawienia modułu (np. `FBPIXEL_ID`, `FBPIXEL_CAPI_TOKEN`, `FBPIXEL_PAID_STATUSES`).
    -   `ps_fbpixel_events` (prawdopodobnie): Niestandardowa tabela utworzona przez moduł do przechowywania lokalnych logów zdarzeń dla funkcji „Statystyki na żywo”. Kolumny zazwyczaj obejmowałyby `id_fbpixel_event`, `pixel_id`, `event_name`, `event_data` (JSON), `timestamp`, `ip_address`, `user_agent`.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Przed renderowaniem kontrolera front-office, w celu dodania JS/CSS. | Wstrzykuje podstawowy JS Piksela Facebooka, skrypty śledzenia zdarzeń i CAPI PageView. |
| `displayContactContent` | Na stronie kontaktowej. | Wyzwala zdarzenie `Contact`. |
| `displayOrderConfirmation` | Na stronie potwierdzenia zamówienia. | Wyzwala zdarzenie `Purchase` po stronie przeglądarki. |
| `actionNewsletterRegistrationAfter` | Po zapisie do newslettera. | Wyzwala zdarzenie `Lead` (i potencjalnie `CompleteRegistration`, jeśli połączone). |
| `displayProductFooter` | Na dole stron produktów. | Wstrzykuje dane specyficzne dla produktu i zdarzenie `ViewContent`. |
| `displayHeader` | W sekcji `<head>` wszystkich stron front-office. | Wstrzykuje podstawowy kod Piksela Facebooka i zdarzenie `PageView`. |
| `DisplayProductButtons` | W pobliżu przycisków akcji produktu (np. Dodaj do koszyka). | Może wstrzykiwać JS dla nasłuchiwacza zdarzeń `AddToCart`. |
| `ActionObjectProductInCartDeleteBefore` | Przed usunięciem produktu z koszyka. | Potencjalnie wyzwala zdarzenie `RemoveFromCart`. |
| `DisplayProductAdditionalInfo` | W bloku informacji o produkcie. | Dodatkowe wstrzykiwanie danych produktu lub wyzwalacze zdarzeń. |
| `ActionCronJob` | Podczas zaplanowanego wykonania crona. | Wyzwala przetwarzanie zdarzeń CAPI, czyszczenie danych. |
| `ActionObjectProductInCartDeleteAfter` | Po usunięciu produktu z koszyka. | Wyzwala zdarzenie `RemoveFromCart`. |
| `ActionValidateOrder` | Po pomyślnym zatwierdzeniu zamówienia. | Wyzwala zdarzenie `Purchase` po stronie serwera za pośrednictwem CAPI. |
| `DisplayLeftColumnProduct` | W lewej kolumnie stron produktów. | Mniej powszechne dla piksela, być może dla konkretnych zdarzeń związanych z produktem. |
| `displayExtraLeft` | W dodatkowej lewej kolumnie. | Mniej powszechne dla piksela, być może dla konkretnych zdarzeń związanych z produktem. |
| `ActionCartUpdateQuantityBefore` | Przed aktualizacją ilości w koszyku. | Potencjalnie używane do śledzenia zmian, które mogą prowadzić do `RemoveFromCart`. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów lub pytań dotyczących modułu „Pixel śledzenia konwersji Fb”.
