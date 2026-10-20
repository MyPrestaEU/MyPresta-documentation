---
title: "Przesyłanie obrazów do zamówień - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów modułu PrestaShop „Przesyłanie obrazów do zamówień” od MyPresta.eu."
sidebar:
  label: "Przesyłanie obrazów do zamówień - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Order images uploader na MyPresta.eu](https://mypresta.eu/modules/ordering-process/order-images-uploader.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/order-images-uploader/)
>
> ---


# Przesyłanie obrazów do zamówień

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Upewnij się, że Twój serwer ma odpowiednio skonfigurowane limity przesyłania plików w `php.ini` (np. `upload_max_filesize`, `post_max_size`), aby pomieścić rozmiar plików, które mogą przesyłać Twoi klienci.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Przesyłanie obrazów do zamówień)

Jest to główny ekran konfiguracji, na którym kontrolujesz ogólne zachowanie i wygląd modułu.

#### Ustawienia ogólne

-   **Włącz moduł:**

    -   **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania całej funkcjonalności modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Funkcje modułu (formularze przesyłania, zarządzanie plikami) będą aktywne w Twoim front office i back office.
        -   *Gdy wyłączony:* Cała funkcjonalność modułu będzie ukryta przed klientami i administratorami, skutecznie wstrzymując jego działanie.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli konfigurujesz moduł po raz pierwszy, włącz go do testowania. Jeśli musisz tymczasowo wyłączyć przesyłanie plików w celu konserwacji, ustaw na NIE.
-   **Zezwól klientom na przesyłanie plików:**

    -   **Co robi to ustawienie:** Określa, czy klienci mogą w ogóle przesyłać pliki.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Klienci będą widzieć formularze przesyłania i będą mogli przesyłać pliki.
        -   *Gdy wyłączony:* Klienci nie będą widzieć żadnych opcji przesyłania, nawet jeśli moduł jest włączony.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz używać modułu tylko do wewnętrznego zarządzania plikami (np. administratorzy przesyłający pliki do zamówień), możesz to wyłączyć. W większości przypadków klienci muszą przesyłać pliki, więc pozostaw to włączone.
-   **Zezwól klientom-gościom na przesyłanie plików:**

    -   **Co robi to ustawienie:** Kontroluje, czy niezalogowani klienci (goście) mogą przesyłać pliki.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Goście mogą przesyłać pliki, zazwyczaj związane z ich koszykiem lub zamówieniem podczas realizacji transakcji.
        -   *Gdy wyłączony:* Tylko zarejestrowani i zalogowani klienci mogą przesyłać pliki.
    -   **Zalecana wartość:** TAK (jeśli zezwalasz na zakupy bez rejestracji i potrzebujesz plików od gości)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój sklep zezwala na zakupy bez rejestracji i wymaga przesyłania plików dla zamówień gości (np. szybkie zlecenie druku), włącz to. Jeśli chcesz zmusić klientów do rejestracji, aby mogli przesyłać pliki, wyłącz to.
-   **Zezwól klientom na usuwanie plików:**

    -   **Co robi to ustawienie:** Daje klientom możliwość usuwania wcześniej przesłanych plików.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Klienci zobaczą opcję „Usuń” obok swoich przesłanych plików na swoim koncie.
        -   *Gdy wyłączony:* Klienci mogą przesyłać, ale nie mogą usuwać plików. Tylko administratorzy mogą je usuwać.
    -   **Zalecana wartość:** NIE (chyba że ufasz klientom, że doskonale zarządzają swoimi plikami)
    -   **Scenariusz/przykład dla sprzedawcy:** W przypadku niestandardowych zamówień druku możesz chcieć to wyłączyć, aby zapobiec przypadkowemu usunięciu pliku, który jest już w produkcji. Jeśli pliki są tymczasowe lub łatwo wymienialne, możesz to włączyć dla wygody klienta.
-   **Zezwól klientom na pobieranie plików:**

    -   **Co robi to ustawienie:** Określa, czy klienci mogą pobierać pliki, które oni (lub Ty) przesłali do ich zamówień.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Klienci mogą kliknąć, aby pobrać swoje pliki z historii zamówień.
        -   *Gdy wyłączony:* Klienci nie mogą pobierać plików.
    -   **Zalecana wartość:** TAK (dla przejrzystości i dostępu klienta)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli przesyłasz projekt lub ostateczny projekt do wglądu klienta, włączenie tej opcji pozwala mu go pobrać.
-   **Zezwól klientom na przesyłanie plików do zamówień:**

    -   **Co robi to ustawienie:** Specjalnie kontroluje, czy klienci mogą przesyłać pliki *po* złożeniu zamówienia, ze strony historii zamówień.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Opcja przesyłania pojawi się na indywidualnej stronie szczegółów zamówienia klienta w „Moim koncie”.
        -   *Gdy wyłączony:* Klienci mogą przesyłać pliki tylko podczas procesu koszyka/realizacji transakcji lub na stronach produktów, a nie do istniejących zamówień.
    -   **Zalecana wartość:** TAK (wysoce zalecane dla elastyczności)
    -   **Scenariusz/przykład dla sprzedawcy:** Klient zapomniał przesłać konkretne logo po złożeniu zamówienia na niestandardowe koszulki. Dzięki tej opcji może łatwo dodać je później.
-   **Zezwól klientom na przesyłanie plików do koszyków:**

    -   **Co robi to ustawienie:** Kontroluje, czy klienci mogą przesyłać pliki, gdy ich przedmioty są nadal w koszyku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Opcja przesyłania pojawi się na stronie koszyka.
        -   *Gdy wyłączony:* Klienci nie mogą przesyłać plików do swojego koszyka.
    -   **Zalecana wartość:** TAK (wygodne dla klientów)
    -   **Scenariusz/przykład dla sprzedawcy:** Klient tworzy niestandardowy album ze zdjęciami. Może przesyłać zdjęcia bezpośrednio do koszyka przed przejściem do realizacji transakcji.
-   **Zezwól klientom na przesyłanie plików do produktów:**

    -   **Co robi to ustawienie:** Kontroluje, czy klienci mogą przesyłać pliki bezpośrednio na poszczególnych stronach produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Opcja przesyłania pojawi się na stronach produktów.
        -   *Gdy wyłączony:* Klienci nie mogą przesyłać plików na stronach produktów.
    -   **Zalecana wartość:** TAK (dla produktów o wysokim stopniu personalizacji)
    -   **Scenariusz/przykład dla sprzedawcy:** W przypadku spersonalizowanego kubka, klient może przesłać swoje pożądane zdjęcie bezpośrednio na stronie produktu kubka przed dodaniem go do koszyka.
-   **Zezwól klientom na przesyłanie plików do konta klienta:**

    -   **Co robi to ustawienie:** Włącza dedykowaną sekcję „Moje pliki” na koncie klienta, umożliwiając im przesyłanie i zarządzanie plikami, które niekoniecznie są powiązane z konkretnym zamówieniem lub koszykiem.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Nowa pozycja menu „Moje pliki” pojawi się w panelu „Moje konto” klienta.
        -   *Gdy wyłączony:* Ta sekcja jest ukryta.
    -   **Zalecana wartość:** NIE (chyba że masz konkretną potrzebę ogólnego przechowywania plików)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz, aby klienci wstępnie przesyłali wspólne zasoby (np. logo swojej firmy), które mogą wykorzystać w wielu przyszłych zamówieniach, może to być przydatne. W przeciwnym razie może to dodać niepotrzebnej złożoności.
-   **Wymuś na klientach przesyłanie plików do zamówień:**

    -   **Co robi to ustawienie:** Sprawia, że przesyłanie plików jest obowiązkowe do zakończenia zamówienia. Jeśli nie zostaną przesłane żadne pliki, klient nie może kontynuować.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Klienci zostaną zablokowani przed zakończeniem realizacji transakcji, dopóki nie prześlą co najmniej jednego pliku.
        -   *Gdy wyłączony:* Przesyłanie plików jest opcjonalne.
    -   **Zalecana wartość:** NIE (włącz tylko wtedy, gdy jest to absolutnie krytyczne dla każdego zamówienia)
    -   **Scenariusz/przykład dla sprzedawcy:** W przypadku drukarni, gdzie *każde* zamówienie wymaga pliku projektowego, włączenie tej opcji zapewnia, że żadne zamówienie nie zostanie zrealizowane bez niezbędnych zasobów. Zachowaj ostrożność, ponieważ może to wpłynąć na współczynniki konwersji, jeśli nie każdy produkt wymaga pliku.
-   **Wymuś na klientach przesyłanie plików do produktów:**

    -   **Co robi to ustawienie:** Sprawia, że przesyłanie plików jest obowiązkowe, aby produkt mógł zostać dodany do koszyka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Klienci nie mogą dodać produktu do koszyka, dopóki nie prześlą co najmniej jednego pliku dla tego produktu.
        -   *Gdy wyłączony:* Przesyłanie plików jest opcjonalne na stronie produktu.
    -   **Zalecana wartość:** NIE (włącz tylko dla produktów, które są *zawsze* personalizowane)
    -   **Scenariusz/przykład dla sprzedawcy:** W przypadku produktu „Zaprojektuj własną koszulkę” zapewnia to, że klient dostarczy swój projekt przed dodaniem go do koszyka.
-   **Wymuś na klientach przesyłanie plików do koszyków:**

    -   **Co robi to ustawienie:** Sprawia, że przesyłanie plików jest obowiązkowe do przetworzenia całego koszyka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Klienci nie mogą przejść z koszyka do realizacji transakcji, dopóki nie prześlą co najmniej jednego pliku dla koszyka.
        -   *Gdy wyłączony:* Przesyłanie plików jest opcjonalne na stronie koszyka.
    -   **Zalecana wartość:** NIE (używaj z najwyższą ostrożnością, może poważnie wpłynąć na konwersję)
    -   **Scenariusz/przykład dla sprzedawcy:** Jest to rzadko zalecane, chyba że *każde pojedyncze zamówienie* w Twoim sklepie wymaga ogólnego przesyłania plików. Zazwyczaj lepiej jest wymusić przesyłanie na poziomie produktu lub zamówienia, jeśli jest to konieczne.
-   **Dozwolone rozszerzenia plików (oddzielone przecinkami):**

    -   **Co robi to ustawienie:** Definiuje, jakie typy plików klienci mogą przesyłać.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Akceptowane będą tylko pliki z określonymi rozszerzeniami (np. `jpg,png,gif,pdf`). Każdy inny typ pliku zostanie odrzucony.
    -   **Zalecana wartość:** `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt` (dostosuj do swoich potrzeb)
    -   **Scenariusz/przykład dla sprzedawcy:** Drukarnia może zezwalać na `jpg,png,pdf,ai,eps`. Sklep z biżuterią na zamówienie może potrzebować tylko `jpg,png`. Ograniczenie rozszerzeń poprawia bezpieczeństwo i zapewnia otrzymywanie użytecznych plików.
-   **Maksymalny rozmiar pliku (w MB):**

    -   **Co robi to ustawienie:** Ustawia górny limit rozmiaru pojedynczego pliku, który klient może przesłać.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Pliki większe niż ten limit zostaną odrzucone.
    -   **Zalecana wartość:** `10` (lub więcej, jeśli spodziewasz się dużych plików projektowych)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli klienci przesyłają obrazy o wysokiej rozdzielczości lub duże pliki projektowe, możesz ustawić to na `50` lub `100`. Pamiętaj, że bardzo duże pliki mogą spowalniać przesyłanie i zużywać miejsce na serwerze. Upewnij się, że `upload_max_filesize` i `post_max_size` w `php.ini` Twojego serwera są również skonfigurowane tak, aby obsługiwały tę wartość.
-   **Maksymalna liczba plików na zamówienie:**

    -   **Co robi to ustawienie:** Ogranicza liczbę pojedynczych plików, które klient może przesłać dla jednego zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Klienci zostaną zablokowani przed przesłaniem większej liczby plików po osiągnięciu tego limitu dla danego zamówienia.
    -   **Zalecana wartość:** `5` (lub więcej, jeśli spodziewasz się wielu plików)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli klient zamawia 10 różnych spersonalizowanych przedmiotów, a każdy potrzebuje pliku, możesz ustawić to na `10` lub `20`. Jeśli zazwyczaj potrzebne są tylko jeden lub dwa pliki, niższa liczba zapobiega bałaganowi.
-   **Maksymalna liczba plików na produkt:**

    -   **Co robi to ustawienie:** Ogranicza liczbę pojedynczych plików, które klient może przesłać dla jednego produktu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Klienci zostaną zablokowani przed przesłaniem większej liczby plików po osiągnięciu tego limitu dla danego produktu.
    -   **Zalecana wartość:** `1` (jeśli każdy produkt potrzebuje jednego projektu) lub `5` (jeśli potrzebne są wiele kątów/wersji)
    -   **Scenariusz/przykład dla sprzedawcy:** W przypadku niestandardowego portretu możesz zezwolić na `3` pliki (zdjęcia referencyjne z przodu, z boku, z tyłu). W przypadku prostego druku logo wystarczy `1` plik.
-   **Maksymalna liczba plików na koszyk:**

    -   **Co robi to ustawienie:** Ogranicza liczbę pojedynczych plików, które klient może przesłać dla całego koszyka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po zmianie:* Klienci zostaną zablokowani przed przesłaniem większej liczby plików po osiągnięciu tego limitu dla koszyka.
    -   **Zalecana wartość:** `5` (lub więcej, jeśli spodziewasz się wielu ogólnych plików)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli klient przesyła ogólny dokument instrukcji, który dotyczy całego koszyka, możesz ustawić to na `1`.
-   **Wyświetl formularz przesyłania na stronie produktu:**

    -   **Co robi to ustawienie:** Kontroluje, gdzie formularz przesyłania pojawia się na stronie produktu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na „W zakładce produktu”:* Formularz przesyłania pojawi się w nowej zakładce na stronie produktu (np. obok „Opis” lub „Karta danych”).
        -   *Gdy ustawione na „Pod opisem produktu”:* Formularz przesyłania pojawi się bezpośrednio pod głównym opisem produktu.
        -   *Gdy ustawione na „Pod ceną produktu”:* Formularz przesyłania pojawi się w pobliżu ceny produktu, zazwyczaj nad przyciskiem „Dodaj do koszyka”.
    -   **Zalecana wartość:** „W zakładce produktu” (dla mniej inwazyjnego wyświetlania) lub „Pod ceną produktu” (dla wysokiej widoczności)
    -   **Scenariusz/przykład dla sprzedawcy:** W przypadku produktu, dla którego przesyłanie plików jest krytyczne, umieszczenie go „Pod ceną produktu” sprawia, że jest bardzo widoczny. W przypadku mniej krytycznych przesyłań, „zakładka produktu” utrzymuje główną informację o produkcie w czystości.
-   **Wyświetl formularz przesyłania na stronie koszyka:**

    -   **Co robi to ustawienie:** Kontroluje, gdzie formularz przesyłania pojawia się na stronie koszyka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na „W bloku podsumowania”:* Formularz przesyłania pojawi się w głównym obszarze podsumowania koszyka.
        -   *Gdy ustawione na „Pod podsumowaniem koszyka”:* Formularz przesyłania pojawi się pod całym podsumowaniem koszyka.
    -   **Zalecana wartość:** „Pod podsumowaniem koszyka” (często zapewnia więcej miejsca)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli klienci muszą przesłać ogólny plik dla całego zamówienia, umieszczenie go wyraźnie na stronie koszyka zapewnia, że nie przegapią go przed realizacją transakcji.
-   **Wyświetl formularz przesyłania na stronie historii zamówień:**

    -   **Co robi to ustawienie:** Kontroluje, gdzie formularz przesyłania pojawia się na indywidualnej stronie szczegółów zamówienia klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy ustawione na „W bloku szczegółów zamówienia”:* Formularz przesyłania pojawi się w głównej sekcji szczegółów zamówienia.
        -   *Gdy ustawione na „Pod szczegółami zamówienia”:* Formularz przesyłania pojawi się pod szczegółami zamówienia.
    -   **Zalecana wartość:** „W bloku szczegółów zamówienia” (dla bliższego powiązania z zamówieniem)
    -   **Scenariusz/przykład dla sprzedawcy:** Po złożeniu zamówienia przez klienta, może on łatwo znaleźć opcję przesyłania na stronie historii zamówień, aby dodać brakujące pliki.
-   **Wyświetl formularz przesyłania na stronie mojego konta:**

    -   **Co robi to ustawienie:** Kontroluje, czy dedykowany link „Moje pliki” pojawia się w panelu „Moje konto” klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Pojawi się link prowadzący do strony, na której klienci mogą zarządzać ogólnymi plikami.
        -   *Gdy wyłączony:* Link nie pojawi się.
    -   **Zalecana wartość:** NIE (chyba że włączyłeś „Zezwól klientom na przesyłanie plików do konta klienta” i potrzebujesz tej funkcji)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz, aby klienci mieli centralne miejsce dla wszystkich swoich przesłanych plików, niezależnie od konkretnych zamówień, włącz to.
-   **Wyświetl formularz przesyłania w stopce:**

    -   **Co robi to ustawienie:** Dodaje link do menedżera przesyłania plików w stopce Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Link pojawi się w stopce, zapewniając kolejny punkt dostępu do menedżera plików.
        -   *Gdy wyłączony:* Brak linku w stopce.
    -   **Zalecana wartość:** NIE (chyba że chcesz wysokiej widoczności dla menedżera plików)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli przesyłanie plików jest kluczową częścią Twojej działalności, link w stopce może sprawić, że będzie łatwo dostępny z każdej strony.
-   **Wyświetl formularz przesyłania w lewej kolumnie:**

    -   **Co robi to ustawienie:** Dodaje link do menedżera przesyłania plików w lewej kolumnie Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Link pojawi się w lewej kolumnie.
        -   *Gdy wyłączony:* Brak linku w lewej kolumnie.
    -   **Zalecana wartość:** NIE (chyba że chcesz wysokiej widoczności dla menedżera plików)
    -   **Scenariusz/przykład dla sprzedawcy:** Podobnie jak w stopce, zapewnia to kolejny widoczny punkt dostępu.
-   **Wyświetl formularz przesyłania w prawej kolumnie:**

    -   **Co robi to ustawienie:** Dodaje link do menedżera przesyłania plików w prawej kolumnie Twojego sklepu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Link pojawi się w prawej kolumnie.
        -   *Gdy wyłączony:* Brak linku w prawej kolumnie.
    -   **Zalecana wartość:** NIE (chyba że chcesz wysokiej widoczności dla menedżera plików)
    -   **Scenariusz/przykład dla sprzedawcy:** Podobnie jak w stopce i lewej kolumnie, zapewnia to kolejny widoczny punkt dostępu.
-   **Wyślij e-mail do klienta o nowym pliku:**

    -   **Co robi to ustawienie:** Kontroluje, czy powiadomienie e-mail jest wysyłane do klienta, gdy administrator prześle nowy plik do jego zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Klienci otrzymują powiadomienie e-mail.
        -   *Gdy wyłączony:* Powiadomienie e-mail nie jest wysyłane.
    -   **Zalecana wartość:** TAK (dla dobrej komunikacji z klientem)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli przesyłasz projekt do wglądu klienta, zostanie on powiadomiony e-mailem.
-   **Wyślij e-mail do właściciela sklepu o nowym pliku:**

    -   **Co robi to ustawienie:** Kontroluje, czy powiadomienie e-mail jest wysyłane do właściciela sklepu (lub skonfigurowanego adresu e-mail sklepu), gdy klient prześle nowy plik.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Ty (właściciel sklepu) otrzymujesz powiadomienie e-mail.
        -   *Gdy wyłączony:* Powiadomienie e-mail nie jest wysyłane.
    -   **Zalecana wartość:** TAK (wysoce zalecane dla terminowego przetwarzania)
    -   **Scenariusz/przykład dla sprzedawcy:** Klient przesyła krytyczny plik projektowy. Otrzymujesz e-mail natychmiast, co pozwala Ci rozpocząć przetwarzanie zamówienia bez opóźnień.
-   **Dołącz pliki do e-maila z potwierdzeniem zamówienia:**

    -   **Co robi to ustawienie:** Określa, czy pliki przesłane przez klienta są dołączane do standardowego e-maila z potwierdzeniem zamówienia PrestaShop.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Pliki zostaną dołączone jako załączniki do e-maila z potwierdzeniem zamówienia wysłanego do klienta.
        -   *Gdy wyłączony:* Pliki nie są dołączane do e-maila.
    -   **Zalecana wartość:** NIE (chyba że pliki są małe i nieliczne, ponieważ duże załączniki mogą powodować problemy z dostarczaniem e-maili)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli klienci przesyłają bardzo małe, niekrytyczne pliki, możesz to włączyć. W przypadku większych lub licznych plików lepiej jest pozwolić klientom pobierać je z ich konta, aby uniknąć problemów z serwerem pocztowym.
-   **Dołącz pliki do e-maila obsługi klienta:**

    -   **Co robi to ustawienie:** Określa, czy pliki przesłane przez klienta są dołączane do e-maila wysyłanego do klienta, gdy administrator prześle nowy plik.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Pliki zostaną dołączone jako załączniki do e-maila.
        -   *Gdy wyłączony:* Pliki nie są dołączane do e-maila.
    -   **Zalecana wartość:** NIE (podobnie jak w przypadku potwierdzenia zamówienia, unikaj dużych załączników)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli przesyłasz mały projekt do klienta, możesz to włączyć. W przypadku większych plików, skieruj ich do pobierania z ich konta.
-   **Dołącz pliki do e-maila właściciela sklepu:**

    -   **Co robi to ustawienie:** Określa, czy pliki przesłane przez klienta są dołączane do e-maila wysyłanego do właściciela sklepu, gdy klient prześle nowy plik.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Pliki zostaną dołączone jako załączniki do otrzymanego powiadomienia e-mail.
        -   *Gdy wyłączony:* Pliki nie są dołączane do e-maila.
    -   **Zalecana wartość:** NIE (chyba że pliki są małe i nieliczne, ponieważ duże załączniki mogą zapchać Twoją skrzynkę odbiorczą)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli wolisz pobierać pliki bezpośrednio z panelu administracyjnego, wyłącz to. Jeśli spodziewasz się tylko bardzo małych plików i chcesz je natychmiast w swojej skrzynce odbiorczej, włącz to.
-   **Włącz komentarze do plików:**

    -   **Co robi to ustawienie:** Pozwala klientom i administratorom dodawać komentarze do każdego przesłanego pliku.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Obok każdego pliku pojawi się pole tekstowe do dodawania notatek lub instrukcji.
        -   *Gdy wyłączony:* Pola komentarzy nie będą dostępne.
    -   **Zalecana wartość:** TAK (dla lepszej komunikacji i kontekstu)
    -   **Scenariusz/przykład dla sprzedawcy:** Klient przesyła logo i dodaje komentarz: „Użyj tego logo, ale zmień kolor na niebieski.” Zapewnia to kluczowy kontekst.
-   **Włącz komentarze do koszyków:**

    -   **Co robi to ustawienie:** Pozwala klientom dodawać ogólny komentarz do ich koszyka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Na stronie koszyka pojawi się pole tekstowe na ogólne komentarze do koszyka.
        -   *Gdy wyłączony:* Brak ogólnego pola komentarzy do koszyka.
    -   **Zalecana wartość:** TAK (przydatne do ogólnych instrukcji)
    -   **Scenariusz/przykład dla sprzedawcy:** Klient może dodać komentarz, np.: „Proszę upewnić się, że wszystkie przedmioty są razem zapakowane na prezent.”
-   **Włącz komentarze do zamówień:**

    -   **Co robi to ustawienie:** Pozwala klientom dodawać ogólny komentarz do ich zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Na stronie szczegółów zamówienia pojawi się pole tekstowe na ogólne komentarze do zamówienia.
        -   *Gdy wyłączony:* Brak ogólnego pola komentarzy do zamówienia.
    -   **Zalecana wartość:** TAK (przydatne do instrukcji po złożeniu zamówienia)
    -   **Scenariusz/przykład dla sprzedawcy:** Klient może dodać komentarz po złożeniu zamówienia: „Potrzebuję tego dostarczonego do piątku, proszę.”
-   **Włącz komentarze do produktów:**

    -   **Co robi to ustawienie:** Pozwala klientom dodawać komentarz specyficzny dla produktu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Na stronie produktu pojawi się pole tekstowe na komentarze specyficzne dla produktu.
        -   *Gdy wyłączony:* Brak pola komentarzy specyficznych dla produktu.
    -   **Zalecana wartość:** TAK (przydatne do instrukcji personalizacji produktu)
    -   **Scenariusz/przykład dla sprzedawcy:** Klient zamawiający niestandardowy grawer może dodać komentarz: „Wygraweruj ‘Wszystkiego najlepszego John’ czcionką skryptową.”
-   **Włącz zakładkę „Moje pliki” na koncie klienta:**

    -   **Co robi to ustawienie:** Dodaje dedykowaną zakładkę „Moje pliki” do panelu konta klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Pojawi się nowa zakładka, umożliwiająca klientom przeglądanie i zarządzanie wszystkimi przesłanymi plikami w jednym miejscu.
        -   *Gdy wyłączony:* Zakładka jest ukryta.
    -   **Zalecana wartość:** TAK (poprawia doświadczenie klienta poprzez centralizację plików)
    -   **Scenariusz/przykład dla sprzedawcy:** Klienci mogą łatwo znaleźć wszystkie swoje przesłane projekty, dowody lub dokumenty w jednej wygodnej lokalizacji.
-   **Włącz zakładkę „Moje pliki” na stronie historii zamówień:**

    -   **Co robi to ustawienie:** Dodaje dedykowaną sekcję „Moje pliki” na stronie historii zamówień dla każdego konkretnego zamówienia.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Sekcja pojawi się na stronie szczegółów każdego zamówienia, pokazując pliki związane z tym konkretnym zamówieniem.
        -   *Gdy wyłączony:* Ta sekcja jest ukryta.
    -   **Zalecana wartość:** TAK (kluczowe dla zarządzania plikami specyficznymi dla zamówienia)
    -   **Scenariusz/przykład dla sprzedawcy:** Gdy klient przegląda poprzednie zamówienie, może natychmiast zobaczyć wszystkie pliki, które przesłał dla tego zamówienia.
-   **Włącz zakładkę „Moje pliki” na stronie produktu:**

    -   **Co robi to ustawienie:** Dodaje dedykowaną sekcję „Moje pliki” na stronie produktu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Sekcja pojawi się na stronie produktu, pokazując pliki związane z tym konkretnym produktem.
        -   *Gdy wyłączony:* Ta sekcja jest ukryta.
    -   **Zalecana wartość:** NIE (chyba że masz bardzo specyficzny przypadek użycia, ponieważ może to zaśmiecać strony produktów)
    -   **Scenariusz/przykład dla sprzedawcy:** Może to być przydatne, jeśli klienci często ponownie zamawiają ten sam spersonalizowany produkt i muszą odwoływać się do wcześniej przesłanych plików dla tego produktu.
-   **Włącz zakładkę „Moje pliki” na stronie koszyka:**

    -   **Co robi to ustawienie:** Dodaje dedykowaną sekcję „Moje pliki” na stronie koszyka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Sekcja pojawi się na stronie koszyka, pokazując pliki związane z przedmiotami w koszyku.
        -   *Gdy wyłączony:* Ta sekcja jest ukryta.
    -   **Zalecana wartość:** NIE (chyba że masz bardzo specyficzny przypadek użycia, ponieważ może to zaśmiecać strony koszyka)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli klienci tworzą złożone zamówienie z wieloma plikami, może to zapewnić przegląd wszystkich plików aktualnie powiązanych z koszykiem.
-   **Pokaż przycisk przesyłania plików na stronie produktu:**

    -   **Co robi to ustawienie:** Kontroluje widoczność przycisku „Prześlij plik” na stronach produktów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Przycisk będzie widoczny.
        -   *Gdy wyłączony:* Przycisk będzie ukryty.
    -   **Zalecana wartość:** TAK (jeśli zezwalasz na przesyłanie plików produktów)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz, aby klienci przesyłali pliki do personalizacji produktu, ten przycisk musi być widoczny.
-   **Pokaż przycisk przesyłania plików na stronie koszyka:**

    -   **Co robi to ustawienie:** Kontroluje widoczność przycisku „Prześlij plik” na stronie koszyka.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Przycisk będzie widoczny.
        -   *Gdy wyłączony:* Przycisk będzie ukryty.
    -   **Zalecana wartość:** TAK (jeśli zezwalasz na przesyłanie plików koszyka)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli klienci muszą przesłać ogólny plik dla całego zamówienia, ten przycisk musi być widoczny na stronie koszyka.
-   **Pokaż przycisk przesyłania plików na stronie historii zamówień:**

    -   **Co robi to ustawienie:** Kontroluje widoczność przycisku „Prześlij plik” na stronie szczegółów zamówienia klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Przycisk będzie widoczny.
        -   *Gdy wyłączony:* Przycisk będzie ukryty.
    -   **Zalecana wartość:** TAK (jeśli zezwalasz na przesyłanie plików po złożeniu zamówienia)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli klienci mogą potrzebować dodać pliki po złożeniu zamówienia, ten przycisk musi być widoczny na stronie historii zamówień.
-   **Pokaż przycisk przesyłania plików na stronie mojego konta:**

    -   **Co robi to ustawienie:** Kontroluje widoczność przycisku „Prześlij plik” na stronie „Moje konto” klienta.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Przycisk będzie widoczny.
        -   *Gdy wyłączony:* Przycisk będzie ukryty.
    -   **Zalecana wartość:** NIE (chyba że włączyłeś „Zezwól klientom na przesyłanie plików do konta klienta” i potrzebujesz tej funkcji)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz, aby klienci przesyłali ogólne pliki na swoje konto, ten przycisk musi być widoczny.
-   **Pokaż przycisk przesyłania plików w stopce:**

    -   **Co robi to ustawienie:** Kontroluje widoczność przycisku „Prześlij plik” w stopce.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Przycisk będzie widoczny.
        -   *Gdy wyłączony:* Przycisk będzie ukryty.
    -   **Zalecana wartość:** NIE (chyba że chcesz wysokiej widoczności dla menedżera plików)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli przesyłanie plików jest kluczową częścią Twojej działalności, przycisk w stopce może sprawić, że będzie łatwo dostępny z każdej strony.
-   **Pokaż przycisk przesyłania plików w lewej kolumnie:**

    -   **Co robi to ustawienie:** Kontroluje widoczność przycisku „Prześlij plik” w lewej kolumnie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Przycisk będzie widoczny.
        -   *Gdy wyłączony:* Przycisk będzie ukryty.
    -   **Zalecana wartość:** NIE (chyba że chcesz wysokiej widoczności dla menedżera plików)
    -   **Scenariusz/przykład dla sprzedawcy:** Podobnie jak w stopce, zapewnia to kolejny widoczny punkt dostępu.
-   **Pokaż przycisk przesyłania plików w prawej kolumnie:**

    -   **Co robi to ustawienie:** Kontroluje widoczność przycisku „Prześlij plik” w prawej kolumnie.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Przycisk będzie widoczny.
        -   *Gdy wyłączony:* Przycisk będzie ukryty.
    -   **Zalecana wartość:** NIE (chyba że chcesz wysokiej widoczności dla menedżera plików)
    -   **Scenariusz/przykład dla sprzedawcy:** Podobnie jak w stopce i lewej kolumnie, zapewnia to kolejny widoczny punkt dostępu.

#### Ustawienia zaawansowane

-   **Włącz tryb debugowania:**

    -   **Co robi to ustawienie:** Aktywuje specjalny tryb, który wyświetla dodatkowe informacje i komunikaty o błędach, głównie w celu rozwiązywania problemów.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Bardziej szczegółowe komunikaty o błędach i informacje debugowania mogą pojawić się na ekranie lub w logach.
        -   *Gdy wyłączony:* Normalne działanie, błędy są tłumione lub logowane cicho.
    -   **Zalecana wartość:** NIE (włącz tylko podczas rozwiązywania problemów z pomocą techniczną)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli napotkasz problem i musisz dostarczyć więcej informacji do pomocy technicznej MyPresta.eu, mogą poprosić Cię o włączenie trybu debugowania.
-   **Usuń pliki po usunięciu zamówienia:**

    -   **Co robi to ustawienie:** Automatycznie usuwa wszystkie powiązane przesłane pliki po usunięciu zamówienia z panelu administracyjnego PrestaShop.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Pliki są trwale usuwane z serwera po usunięciu zamówienia.
        -   *Gdy wyłączony:* Pliki pozostają na serwerze, nawet jeśli powiązane zamówienie zostanie usunięte.
    -   **Zalecana wartość:** TAK (aby utrzymać serwer w czystości i uniknąć osieroconych plików)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli często usuwasz zamówienia testowe, włączenie tej opcji zapobiega gromadzeniu się niepotrzebnych plików na serwerze.
-   **Usuń pliki po usunięciu produktu:**

    -   **Co robi to ustawienie:** Automatycznie usuwa wszystkie powiązane przesłane pliki po usunięciu produktu z panelu administracyjnego PrestaShop.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Pliki są trwale usuwane z serwera po usunięciu produktu.
        -   *Gdy wyłączony:* Pliki pozostają na serwerze, nawet jeśli powiązany produkt zostanie usunięty.
    -   **Zalecana wartość:** TAK (aby utrzymać serwer w czystości i uniknąć osieroconych plików)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli usuwasz stare lub wycofane produkty, zapewnia to również usunięcie powiązanych z nimi plików.
-   **Usuń pliki po usunięciu koszyka:**

    -   **Co robi to ustawienie:** Automatycznie usuwa wszystkie powiązane przesłane pliki po usunięciu koszyka z panelu administracyjnego PrestaShop.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Pliki są trwale usuwane z serwera po usunięciu koszyka.
        -   *Gdy wyłączony:* Pliki pozostają na serwerze, nawet jeśli powiązany koszyk zostanie usunięty.
    -   **Zalecana wartość:** TAK (aby utrzymać serwer w czystości i uniknąć osieroconych plików)
    -   **Scenariusz/przykład dla sprzedawcy:** Koszyki są często tymczasowe. Włączenie tej opcji zapobiega gromadzeniu się plików z porzuconych koszyków na serwerze.
-   **Usuń pliki po usunięciu klienta:**

    -   **Co robi to ustawienie:** Automatycznie usuwa wszystkie powiązane przesłane pliki po usunięciu konta klienta z panelu administracyjnego PrestaShop.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Pliki są trwale usuwane z serwera po usunięciu klienta.
        -   *Gdy wyłączony:* Pliki pozostają na serwerze, nawet jeśli powiązany klient zostanie usunięty.
    -   **Zalecana wartość:** TAK (dla prywatności danych i higieny serwera)
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli klient prosi o usunięcie swoich danych (zgodność z RODO), zapewnia to również usunięcie jego przesłanych plików.
-   **Usuń pliki po usunięciu pliku klienta:**

    -   **Co robi to ustawienie:** Gdy administrator lub klient usunie konkretny plik, to ustawienie kontroluje, czy rzeczywisty plik zostanie usunięty z serwera.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony:* Plik jest trwale usuwany z serwera.
        -   *Gdy wyłączony:* Rekord pliku jest usuwany z bazy danych, ale rzeczywisty plik pozostaje na serwerze (osierocony).
    -   **Zalecana wartość:** TAK (zawsze, aby zapobiec osieroconym plikom i zaoszczędzić miejsce na dysku)
    -   **Scenariusz/przykład dla sprzedawcy:** Gdy klient zdecyduje, że nie potrzebuje już pliku, jego usunięcie zwalnia również miejsce na serwerze.
-   **Włącz niestandardowy CSS:**

    -   **Co robi to ustawienie:** Udostępnia obszar tekstowy, w którym możesz dodać własne reguły CSS, aby dostosować wygląd elementów modułu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączony i dodano CSS:* Twoje niestandardowe style zastąpią lub uzupełnią domyślne style modułu.
        -   *Gdy wyłączony lub pusty:* Moduł używa swoich domyślnych stylów.
    -   **Zalecana wartość:** NIE (chyba że masz specyficzne potrzeby projektowe i wiedzę CSS)
    -   **Scenariusz/przykład dla sprzedawcy:** Chcesz zmienić kolor przycisku przesyłania, aby pasował do głównego koloru Twojej marki. Tutaj dodasz reguły CSS.
-   **Niestandardowy CSS:**

    -   **Co robi to ustawienie:** Jest to obszar tekstowy, w którym wpisujesz lub wklejasz swój niestandardowy kod CSS.
    -   **Efekt zmiany tego ustawienia:** Wygląd elementów modułu zmieni się zgodnie z Twoimi regułami CSS.
    -   **Zalecana wartość:** Pozostaw puste, chyba że znasz CSS.
    -   **Scenariusz/przykład dla sprzedawcy:** `button.upload-btn { background-color: #ff0000; color: white; }`

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł dodaje nowe sekcje do panelu administracyjnego PrestaShop do zarządzania przesłanymi plikami.

#### 2.2.1 Menedżer plików klienta (Panel administracyjny > Zamówienia > Pliki klienta)

Ten ekran zapewnia scentralizowane miejsce do przeglądania i zarządzania wszystkimi plikami przesłanymi przez Twoich klientów.

-   **Nazwa ekranu i lokalizacja w menu:** **Pliki klienta** (znajduje się w menu **Zamówienia** w PrestaShop 1.7/8/9. W starszych wersjach może być bezpośrednio pod głównym menu Moduły lub niestandardową zakładką).
-   **Dostępne akcje i ustawienia:**
    -   **Tabela listy plików:** Zobaczysz tabelę zawierającą listę wszystkich przesłanych plików. Każdy wiersz zazwyczaj pokazuje:
        -   **Nazwa pliku:** Nazwa przesłanego pliku.
        -   **Klient:** Nazwa klienta, który przesłał plik (lub „Gość”, jeśli dotyczy).
        -   **ID zamówienia:** ID zamówienia, z którym plik jest powiązany.
        -   **Produkt:** Nazwa produktu, jeśli plik jest powiązany z konkretnym produktem.
        -   **ID koszyka:** ID koszyka, z którym plik jest powiązany.
        -   **Data przesłania:** Kiedy plik został przesłany.
        -   **Rozmiar:** Rozmiar pliku.
        -   **Akcje:** Przyciski do **Pobrania** pliku, **Wyświetlenia szczegółów** (w tym komentarzy) lub **Usunięcia** pliku.
    -   **Filtrowanie i wyszukiwanie:** Zazwyczaj możesz filtrować listę według klienta, ID zamówienia lub wyszukiwać według nazwy pliku, aby szybko znaleźć konkretne pliki.
    -   **Akcje masowe:** Opcje wyboru wielu plików i wykonywania akcji, takich jak masowe usuwanie.
-   **Efekt zmian:**
    -   **Pobieranie pliku:** Zapisuje plik na komputerze w celu przeglądu lub przetwarzania.
    -   **Usuwanie pliku:** Usuwa plik z listy i, jeśli skonfigurowano, z serwera.
    -   **Wyświetlanie szczegółów:** Otwiera wyskakujące okienko lub nową stronę z większą ilością informacji o pliku, w tym o wszelkich powiązanych komentarzach.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Regularnie sprawdzaj tę sekcję, zwłaszcza jeśli otrzymujesz powiadomienia e-mail o nowych przesyłkach.
    2.  Użyj filtrów, aby szybko znaleźć pliki dla konkretnych zamówień, które przetwarzasz.
    3.  Pobierz niezbędne pliki do produkcji, projektowania lub przeglądu.
    4.  Dodaj komentarze do plików, jeśli musisz komunikować się z klientem lub swoim zespołem na ich temat.
    5.  Usuń stare lub niepotrzebne pliki, aby utrzymać serwer w czystości.

#### 2.2.2 Integracja strony szczegółów zamówienia (Panel administracyjny > Zamówienia > Zamówienia > Wyświetl zamówienie)

Moduł integruje się również bezpośrednio ze standardową stroną szczegółów zamówienia PrestaShop.

-   **Nazwa ekranu i lokalizacja w menu:** Gdy przeglądasz dowolne konkretne zamówienie w **Panel administracyjny > Zamówienia > Zamówienia**, znajdziesz nową sekcję lub zakładkę związaną z „Plikami klienta” lub „Przesłanymi plikami”.
-   **Dostępne akcje i ustawienia:**
    -   **Pliki dla tego zamówienia:** Lista wszystkich plików przesłanych specjalnie dla bieżącego zamówienia przez klienta lub przez administratora.
    -   **Prześlij nowy plik:** Opcja samodzielnego przesłania pliku jako administrator, powiązując go bezpośrednio z tym zamówieniem. Jest to przydatne do przesyłania projektów, ostatecznych projektów lub dokumentów wewnętrznych.
    -   **Dodaj komentarze:** Możesz dodawać komentarze do poszczególnych plików lub ogólny komentarz do zamówienia.
    -   **Pobierz/Usuń:** Opcje pobierania lub usuwania poszczególnych plików powiązanych z tym zamówieniem.
-   **Efekt zmian:**
    -   **Przesyłanie pliku jako administrator:** Plik staje się częścią załączników zamówienia, widoczną dla klienta w jego historii zamówień (jeśli skonfigurowano).
    -   **Dodawanie komentarzy:** Zapewnia kontekst dla pliku lub zamówienia, widoczny dla klienta i innych administratorów.
-   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Podczas przetwarzania zamówienia, które wymaga plików klienta, przejdź do strony szczegółów zamówienia.
    2.  Przejrzyj przesłane pliki w dedykowanej sekcji.
    3.  Pobierz pliki zgodnie z potrzebami do produkcji.
    4.  Jeśli tworzysz projekt lub ostateczny projekt, prześlij go tutaj, aby klient mógł uzyskać do niego dostęp.
    5.  Użyj pól komentarzy do komunikacji z klientem lub pozostawiania wewnętrznych notatek.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Konfiguracja modułu** | Włącz moduł | TAK | Główny przełącznik funkcjonalności modułu. |
| | Zezwól klientom na przesyłanie plików | TAK | Zezwól klientom na przesyłanie plików. |
| | Zezwól klientom-gościom na przesyłanie plików | TAK | Zezwól niezalogowanym użytkownikom na przesyłanie. |
| | Zezwól klientom na usuwanie plików | NIE | Zapobiegaj usuwaniu plików przez klientów. |
| | Zezwól klientom na pobieranie plików | TAK | Zezwól klientom na pobieranie ich plików. |
| | Zezwól klientom na przesyłanie plików do zamówień | TAK | Włącz przesyłanie po złożeniu zamówienia poprzez historię zamówień. |
| | Zezwól klientom na przesyłanie plików do koszyków | TAK | Włącz przesyłanie na stronie koszyka. |
| | Zezwól klientom na przesyłanie plików do produktów | TAK | Włącz przesyłanie na stronach poszczególnych produktów. |
| | Zezwól klientom na przesyłanie plików do konta klienta | NIE | Włącz ogólne przechowywanie plików w „Moim koncie”. |
| | Wymuś na klientach przesyłanie plików do zamówień | NIE | Uczyń przesyłanie plików obowiązkowym do zakończenia zamówienia. |
| | Wymuś na klientach przesyłanie plików do produktów | NIE | Uczyń przesyłanie plików obowiązkowym do dodania produktu do koszyka. |
| | Wymuś na klientach przesyłanie plików do koszyków | NIE | Uczyń przesyłanie plików obowiązkowym do przejścia z koszyka. |
| | Dozwolone rozszerzenia plików | `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt` | Ogranicz typy plików dla bezpieczeństwa i użyteczności. |
| | Maksymalny rozmiar pliku (MB) | `10` | Ogranicz rozmiar pojedynczego pliku. |
| | Maksymalna liczba plików na zamówienie | `5` | Ogranicz liczbę plików na zamówienie. |
| | Maksymalna liczba plików na produkt | `1` | Ogranicz liczbę plików na produkt. |
| | Maksymalna liczba plików na koszyk | `5` | Ogranicz liczbę plików na koszyk. |
| | Wyświetl formularz przesyłania na stronie produktu | „W zakładce produktu” lub „Pod ceną produktu” | Pozycja formularza przesyłania na stronie produktu. |
| | Wyświetl formularz przesyłania na stronie koszyka | „Pod podsumowaniem koszyka” | Pozycja formularza przesyłania na stronie koszyka. |
| | Wyświetl formularz przesyłania na stronie historii zamówień | „W bloku szczegółów zamówienia” | Pozycja formularza przesyłania na stronie historii zamówień. |
| | Wyświetl formularz przesyłania na stronie mojego konta | NIE | Pokaż/ukryj link „Moje pliki” na koncie klienta. |
| | Wyświetl formularz przesyłania w stopce | NIE | Pokaż/ukryj link „Moje pliki” w stopce. |
| | Wyświetl formularz przesyłania w lewej kolumnie | NIE | Pokaż/ukryj link „Moje pliki” w lewej kolumnie. |
| | Wyświetl formularz przesyłania w prawej kolumnie | NIE | Pokaż/ukryj link „Moje pliki” w prawej kolumnie. |
| | Wyślij e-mail do klienta o nowym pliku | TAK | Powiadom klienta, gdy administrator prześle plik. |
| | Wyślij e-mail do właściciela sklepu o nowym pliku | TAK | Powiadom właściciela sklepu, gdy klient prześle plik. |
| | Dołącz pliki do e-maila z potwierdzeniem zamówienia | NIE | Dołącz przesłane pliki do potwierdzenia zamówienia. |
| | Dołącz pliki do e-maila obsługi klienta | NIE | Dołącz przesłane pliki do e-maila obsługi klienta. |
| | Dołącz pliki do e-maila właściciela sklepu | NIE | Dołącz przesłane pliki do powiadomienia właściciela sklepu. |
| | Włącz komentarze do plików | TAK | Zezwól na komentarze do poszczególnych plików. |
| | Włącz komentarze do koszyków | TAK | Zezwól na ogólne komentarze do koszyków. |
| | Włącz komentarze do zamówień | TAK | Zezwól na ogólne komentarze do zamówień. |
| | Włącz komentarze do produktów | TAK | Zezwól na komentarze do poszczególnych produktów. |
| | Włącz zakładkę „Moje pliki” na koncie klienta | TAK | Pokaż dedykowaną zakładkę „Moje pliki” na koncie klienta. |
| | Włącz zakładkę „Moje pliki” na stronie historii zamówień | TAK | Pokaż sekcję plików na stronie historii zamówień. |
| | Włącz zakładkę „Moje pliki” na stronie produktu | NIE | Pokaż sekcję plików na stronie produktu. |
| | Włącz zakładkę „Moje pliki” na stronie koszyka | NIE | Pokaż sekcję plików na stronie koszyka. |
| | Pokaż przycisk przesyłania plików na stronie produktu | TAK | Kontroluj widoczność przycisku przesyłania na stronie produktu. |
| | Pokaż przycisk przesyłania plików na stronie koszyka | TAK | Kontroluj widoczność przycisku przesyłania na stronie koszyka. |
| | Pokaż przycisk przesyłania plików na stronie historii zamówień | TAK | Kontroluj widoczność przycisku przesyłania na stronie historii zamówień. |
| | Pokaż przycisk przesyłania plików na stronie mojego konta | NIE | Kontroluj widoczność przycisku przesyłania na stronie mojego konta. |
| | Pokaż przycisk przesyłania plików w stopce | NIE | Kontroluj widoczność przycisku przesyłania w stopce. |
| | Pokaż przycisk przesyłania plików w lewej kolumnie | NIE | Kontroluj widoczność przycisku przesyłania w lewej kolumnie. |
| | Pokaż przycisk przesyłania plików w prawej kolumnie | NIE | Kontroluj widoczność przycisku przesyłania w prawej kolumnie. |
| **Ustawienia zaawansowane** | Włącz tryb debugowania | NIE | Wyświetl szczegółowe komunikaty o błędach. |
| | Usuń pliki po usunięciu zamówienia | TAK | Usuń pliki po usunięciu powiązanego zamówienia. |
| | Usuń pliki po usunięciu produktu | TAK | Usuń pliki po usunięciu powiązanego produktu. |
| | Usuń pliki po usunięciu koszyka | TAK | Usuń pliki po usunięciu powiązanego koszyka. |
| | Usuń pliki po usunięciu klienta | TAK | Usuń pliki po usunięciu powiązanego klienta. |
| | Usuń pliki po usunięciu pliku klienta | TAK | Usuń rzeczywisty plik z serwera po usunięciu. |
| | Włącz niestandardowy CSS | NIE | Aktywuj wprowadzanie niestandardowego CSS. |
| | Niestandardowy CSS | Pozostaw puste | Obszar tekstowy na niestandardowe reguły CSS. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci nie mogą przesyłać plików lub otrzymują komunikat o błędzie.**
O1:

-   **Sprawdź status modułu:** Upewnij się, że „Włącz moduł” i „Zezwól klientom na przesyłanie plików” są ustawione na TAK w konfiguracji modułu.
-   **Typ i rozmiar pliku:** Sprawdź, czy typ pliku (rozszerzenie) i rozmiar mieszczą się w ustawionych przez Ciebie limitach „Dozwolone rozszerzenia plików” i „Maksymalny rozmiar pliku”.
-   **Limity serwera:** Twój dostawca hostingu może mieć niższe limity przesyłania PHP (`upload_max_filesize`, `post_max_size` w `php.ini`) niż ustawienia modułu. Skontaktuj się z hostem lub webmasterem, aby je zwiększyć, jeśli to konieczne.
-   **Uprawnienia:** Upewnij się, że katalog przesyłania modułu (zazwyczaj `modules/orderfiles/uploads/`) ma uprawnienia do zapisu (np. 755 lub 777, chociaż 777 jest ogólnie niezalecane ze względów bezpieczeństwa).
-   **Tryb debugowania:** Tymczasowo włącz „Tryb debugowania” w zaawansowanych ustawieniach modułu i sprawdź, czy pojawiają się jakieś konkretne komunikaty o błędach.

**P2: Formularz przesyłania nie pojawia się na mojej stronie produktu/koszyka/zamówienia.**
O2:

-   **Konfiguracja modułu:** Sprawdź ponownie ustawienia „Wyświetl formularz przesyłania na…” dla konkretnej strony (produktu, koszyka, historii zamówień) w konfiguracji modułu.
-   **Konflikty hooków:** Inny moduł może kolidować z hookami wyświetlania. Spróbuj tymczasowo wyłączyć inne moduły, które modyfikują strony produktów, koszyków lub zamówień, aby sprawdzić, czy formularz się pojawi.
-   **Kompatybilność z motywem:** Niestandardowe motywy mogą niepoprawnie renderować standardowe hooki PrestaShop. Jeśli używasz niestandardowego motywu, może być konieczne ręczne zintegrowanie hooków modułu z plikami motywu przez webmastera.
-   **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) i pamięć podręczną przeglądarki.

**P3: Nie otrzymuję powiadomień e-mail, gdy klienci przesyłają pliki.**
O3:

-   **Konfiguracja modułu:** Upewnij się, że „Wyślij e-mail do właściciela sklepu o nowym pliku” jest ustawione na TAK.
-   **E-mail sklepu:** Sprawdź, czy adres e-mail Twojego sklepu (PS\_SHOP\_EMAIL w Zaawansowane > E-mail) jest poprawnie skonfigurowany i działa.
-   **Ustawienia e-mail:** Sprawdź ustawienia e-mail PrestaShop (Zaawansowane > E-mail) i upewnij się, że e-maile są wysyłane pomyślnie (np. spróbuj wysłać testowy e-mail).
-   **Folder spamu:** Sprawdź folder spamu lub wiadomości-śmieci pod kątem powiadomień.
-   **Serwer pocztowy:** Funkcja poczty Twojego serwera może być nieprawidłowo skonfigurowana. Skonsultuj się z dostawcą hostingu.

**P4: Jak przetłumaczyć tekst modułu na inne języki?**
O4:

-   W panelu administracyjnym PrestaShop przejdź do **Lokalizacja > Tłumaczenia**.
-   Wybierz „Tłumaczenia zainstalowanych modułów”.
-   Wybierz swój motyw, język, na który chcesz przetłumaczyć, a następnie wybierz „Przesyłanie obrazów do zamówień” z listy modułów.
-   Możesz wtedy przetłumaczyć wszystkie widoczne ciągi tekstowe modułu.

**P5: Moje przesłane pliki nie są usuwane, gdy usuwam zamówienie/produkt/klienta.**
O5:

-   **Konfiguracja modułu:** Upewnij się, że odpowiednie ustawienia „Usuń pliki po…” (np. „Usuń pliki po usunięciu zamówienia”) są ustawione na TAK w zaawansowanych ustawieniach modułu.
-   **Ręczne usuwanie:** Jeśli te ustawienia były wyłączone, pliki mogły się nagromadzić. Może być konieczne ręczne wyczyszczenie katalogu `modules/orderfiles/uploads/` na serwerze z starych, osieroconych plików.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Przesyłanie obrazów do zamówień” opiera się na standardowej architekturze modułów PrestaShop, wykorzystując zasady MVC. Rozszerza klasę `Module` dla swojej podstawowej funkcjonalności i używa `ModuleFrontController` oraz `AdminController` do obsługi odpowiednio żądań front-office i back-office. Przesyłanie plików jest zarządzane za pomocą dedykowanych kontrolerów i JavaScript, zapewniając płynne doświadczenie użytkownika. Konfiguracja jest przechowywana w `ps_configuration`, a niestandardowe dane (rekordy plików) są zarządzane poprzez bezpośrednią interakcję z bazą danych lub potencjalnie niestandardowy `ObjectModel` (chociaż żaden nie został wyraźnie wymieniony w inwentarzu, moduł prawdopodobnie używa bezpośredniego SQL dla rekordów plików).

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

Te kontrolery obsługują interakcje klienta i zarządzanie plikami w witrynie sklepu.

-   `controllers/front/customerfiles.php`
    -   **Nazwa klasy i klasa nadrzędna:** `OrderFilesCustomerfilesModuleFrontController` rozszerzający `ModuleFrontController`
    -   **Odpowiedzialność:** Zarządza sekcją „Moje pliki” klienta, wyświetlając listę przesłanych plików, umożliwiając ich przeglądanie, pobieranie i potencjalne usuwanie. Prawdopodobnie obsługuje żądania AJAX dotyczące operacji na plikach w tym kontekście.
-   `controllers/front/download.php`
    -   **Nazwa klasy i klasa nadrzędna:** `OrderFilesDownloadModuleFrontController` rozszerzający `ModuleFrontController`
    -   **Odpowiedzialność:** Obsługuje bezpieczne pobieranie plików. Weryfikuje uprawnienia użytkownika (np. czy plik należy do zalogowanego klienta lub czy użytkownik jest administratorem) przed udostępnieniem pliku, zapobiegając nieautoryzowanemu dostępowi.
-   `controllers/front/filesmanager.php`
    -   **Nazwa klasy i klasa nadrzędna:** `OrderFilesFilesmanagerModuleFrontController` rozszerzający `ModuleFrontController`
    -   **Odpowiedzialność:** Jest to prawdopodobnie centralny kontroler dla głównego interfejsu zarządzania plikami, potencjalnie używany do ogólnego przesyłania plików niepowiązanych z konkretnym zamówieniem/produktem, lub jako centrum dla wszystkich plików klienta.
-   `controllers/front/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `OrderFilesIndexModuleFrontController` rozszerzający `ModuleFrontController`
    -   **Odpowiedzialność:** Zastępczy lub domyślny kontroler front-office. W PrestaShop `index.php` w katalogu kontrolera często służy jako awaryjny lub prosty przekierowanie.
-   `controllers/front/myfiles.php`
    -   **Nazwa klasy i klasa nadrzędna:** `OrderFilesMyfilesModuleFrontController` rozszerzający `ModuleFrontController`
    -   **Odpowiedzialność:** Podobnie jak `customerfiles.php`, ten kontroler prawdopodobnie obsługuje sekcję „Moje pliki” na koncie klienta, zapewniając interfejs do przeglądania i zarządzania osobistymi plikami.
-   `controllers/front/thumb.php`
    -   **Nazwa klasy i klasa nadrzędna:** `OrderFilesThumbModuleFrontController` rozszerzający `ModuleFrontController`
    -   **Odpowiedzialność:** Generuje i udostępnia miniatury dla przesłanych plików graficznych, poprawiając wydajność i wyświetlanie na listach plików.
-   `controllers/front/upload.php`
    -   **Nazwa klasy i klasa nadrzędna:** `OrderFilesUploadModuleFrontController` rozszerzający `ModuleFrontController`
    -   **Odpowiedzialność:** Główny kontroler do obsługi wszystkich żądań przesyłania plików z front-office (strona produktu, strona koszyka, historia zamówień, „Moje pliki”). Przetwarza przesłany plik, waliduje jego typ i rozmiar, przechowuje go na serwerze i zapisuje jego szczegóły w bazie danych. Prawdopodobnie obsługuje odpowiedzi AJAX dotyczące postępu i statusu przesyłania.

#### Kontrolery administracyjne Back-Office

Te kontrolery zapewniają interfejs administracyjny do zarządzania przesłanymi plikami.

-   `controllers/admin/customerFiles.php`
    -   **Nazwa zakładki i zarządzana encja:** „Pliki klienta” (w menu Zamówienia). Zarządza listowaniem, przeglądaniem, pobieraniem i usuwaniem wszystkich plików przesłanych przez klientów w całym sklepie. Zapewnia kompleksowy widok siatki z opcjami filtrowania.
-   `controllers/admin/index.php`
    -   **Nazwa klasy i klasa nadrzędna:** `AdminOrderFilesIndexController` rozszerzający `ModuleAdminController`
    -   **Nazwa zakładki i zarządzana encja:** Podobnie jak `index.php` w front-office, może to być zastępczy lub prosty przekierowanie dla sekcji administracyjnej. Główne zarządzanie plikami jest obsługiwane przez `AdminCustomerFilesController`.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dostarczony spis wskazuje brak niestandardowych klas w katalogu `classes/`. Sugeruje to, że moduł może używać bezpośrednich zapytań do bazy danych do zarządzania plikami lub przechowywać informacje o plikach bezpośrednio w `ps_configuration` lub niestandardowej tabeli bez dedykowanego `ObjectModel`. Biorąc pod uwagę złożoność zarządzania plikami, bardziej prawdopodobne jest, że rekordy plików są przechowywane w niestandardowej tabeli bazy danych i zarządzane za pomocą bezpośredniego SQL lub prostej klasy pomocniczej w głównym pliku modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

Te skrypty poprawiają doświadczenie użytkownika podczas przesyłania i zarządzania plikami.

-   `orderfiles/js/jquery.form.js`
    -   **Zakres:** Front-office i Back-office (wszędzie tam, gdzie formularze są przesyłane za pomocą AJAX).
    -   **Opis:** Wtyczka jQuery do łatwego przesyłania formularzy HTML za pomocą AJAX, w tym przesyłania plików. Obsługuje śledzenie postępu i upraszcza asynchroniczne przesyłanie formularzy.
-   `orderfiles/js/orders.js`
    -   **Zakres:** Back-office (szczególnie na stronach szczegółów zamówienia).
    -   **Opis:** Prawdopodobnie obsługuje funkcjonalność AJAX do przesyłania plików bezpośrednio ze strony szczegółów zamówienia administratora, wyświetlania plików powiązanych z zamówieniem i zarządzania komentarzami w kontekście zamówienia.
-   `orderfiles/js/script-customers.js`
    -   **Zakres:** Front-office (strony konta klienta, sekcja „Moje pliki”).
    -   **Opis:** Zarządza interaktywnymi elementami w sekcji „Moje pliki” klienta, w tym wyświetlaniem list plików, obsługą akcji pobierania/usuwania i potencjalnie aktualizacjami AJAX dla statusu plików lub komentarzy.
-   `orderfiles/js/script.js`
    -   **Zakres:** Front-office (strony produktów, strony koszyka, ogólne formularze przesyłania).
    -   **Opis:** Główny skrypt JavaScript front-office do obsługi przesyłania plików. Prawdopodobnie inicjalizuje formularze przesyłania, obsługuje funkcjonalność przeciągania i upuszczania, wyświetla postęp przesyłania, waliduje typy/rozmiary plików po stronie klienta i wysyła żądania AJAX do `upload.php`.

### 4.5 Arkusze stylów CSS (`views/css/`)

Te arkusze stylów kontrolują wizualną prezentację elementów modułu.

-   `orderfiles/css/ajaxuploader.css`
    -   **Zakres:** Front-office i Back-office (wszędzie tam, gdzie używany jest interfejs AJAX uploader).
    -   **Opis:** Style dla samego widżetu przesyłania plików, w tym pasków postępu, obszarów przeciągania i upuszczania oraz elementów podglądu plików.
    -   **Kluczowe selektory klas CSS:** `.ajax-uploader-container`, `.upload-drop-zone`, `.file-list`, `.progress-bar`
-   `orderfiles/css/backoffice.css`
    -   **Zakres:** Back-office (kontrolery administracyjne).
    -   **Opis:** Specyficzne style dla interfejsów administracyjnych modułu, takich jak lista „Pliki klienta” i integracja na stronie szczegółów zamówienia.
    -   **Kluczowe selektory klas CSS:** `.orderfiles-admin-table`, `.orderfiles-order-details-block`
-   `orderfiles/css/orderfiles.css`
    -   **Zakres:** Front-office (ogólne elementy modułu).
    -   **Opis:** Ogólne style dla komponentów front-office modułu, w tym przycisków, list plików i sekcji komentarzy na stronach produktów, koszyka i historii zamówień.
    -   **Kluczowe selektory klas CSS:** `.orderfiles-upload-form`, `.orderfiles-file-item`, `.orderfiles-comments`
-   `orderfiles/css.css`
    -   **Zakres:** Potencjalnie globalne lub awaryjne style.
    -   **Opis:** Może to być starszy lub ogólny arkusz stylów. Programiści powinni sprawdzić jego zawartość, aby zrozumieć jego konkretny wpływ, ponieważ `orderfiles.css` jest bardziej opisowy.
    -   **Kluczowe selektory klas CSS:** (Wymaga inspekcji)

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

Te szablony są renderowane za pomocą hooków PrestaShop w celu wstrzyknięcia zawartości modułu do różnych części sklepu.

-   `displayProductPageUploadFormSmall.tpl`: Renderuje kompaktowy formularz przesyłania na stronie produktu.
-   `filesmanager-orderhistory.tpl`: Wyświetla interfejs menedżera plików na stronie historii zamówień klienta.
-   `force-redirect.tpl`: Szablon narzędziowy, prawdopodobnie używany do przekierowań po pewnych akcjach lub do wymuszania przesyłania plików.
-   `header.tpl`: Wstrzykuje zasoby CSS/JS lub inny niezbędny kod do sekcji `<head>` front-office.
-   `my-account-17.tpl`: Renderuje link/zakładkę „Moje pliki” dla PrestaShop 1.7.x i nowszych paneli konta klienta.
-   `my-account.tpl`: Renderuje link/zakładkę „Moje pliki” dla starszych wersji PrestaShop (np. 1.6.x) paneli konta klienta.
-   `orderConfirmation.tpl`: Wyświetla opcje przesyłania plików lub podsumowanie na stronie potwierdzenia zamówienia.
-   `product-files-button.tpl`: Renderuje przycisk „Prześlij plik” na stronie produktu.
-   `product-files.tpl`: Wyświetla listę plików powiązanych z produktem, potencjalnie z opcjami przesyłania.
-   `shopping-cart-force-files-alert.tpl`: Wyświetla komunikat ostrzegawczy, jeśli przesyłanie plików jest obowiązkowe na stronie koszyka i nie przesłano żadnych plików.
-   `shopping-cart-qty-infos-alert.tpl`: Prawdopodobnie wyświetla komunikat ostrzegawczy związany z informacjami o ilości w koszyku, prawdopodobnie powiązany z przesyłaniem plików.
-   `shopping-cart.tpl`: Integruje funkcjonalność przesyłania plików lub listy plików na stronie koszyka.
-   `tab.tpl`: Ogólny szablon zakładki, prawdopodobnie używany do tworzenia nowych zakładek na stronach produktów lub na koncie klienta.

#### Szablony administracyjne (`views/templates/admin/`)

Te szablony są używane do interfejsów back-office modułu.

-   `admin.tpl`: Główny szablon konfiguracji dla metody `getContent()` modułu, renderujący formularz ustawień.
-   `adminOrderDetailUpload.tpl`: Integruje interfejs przesyłania i zarządzania plikami bezpośrednio na stronie szczegółów zamówienia PrestaShop w back-office.
-   `boscript.tpl`: Zawiera kod JavaScript specjalnie dla back-office, prawdopodobnie zawarty na stronach administracyjnych.
-   `bulk-delete-files.tpl`: Szablon dla interfejsu lub potwierdzenia masowego usuwania plików.
-   `comments_cartfiles.tpl`: Renderuje sekcję komentarzy dla plików powiązanych z koszykiem.
-   `comments_orderfiles.tpl`: Renderuje sekcję komentarzy dla plików powiązanych z zamówieniem.
-   `comments_productfiles.tpl`: Renderuje sekcję komentarzy dla plików powiązanych z produktem.
-   `customerfilesmanager.tpl`: Główny szablon dla `AdminCustomerFilesController`, wyświetlający siatkę wszystkich przesłanych plików.
-   `_configure/helpers/list/list_action_details.tpl`: Szablon pomocniczy do wyświetlania przycisku akcji „szczegóły” na liście.
-   `_configure/helpers/list/list_content.tpl`: Szablon pomocniczy do renderowania wierszy zawartości listy.
-   `_configure/prestashopbug/helpers/list/*.tpl`: Te szablony wydają się być specyficznymi nadpisaniami lub poprawkami dla domyślnych pomocników list PrestaShop, prawdopodobnie w celu rozwiązania problemów z kompatybilnością lub dostosowania wyświetlania listy dla siatek administracyjnych modułu. Obejmują one `list.tpl`, `list_action_delete.tpl`, `list_action_details.tpl`, `list_content.tpl`, `list_footer.tpl`, `list_header.tpl`.

#### Szablony Front-office (`views/templates/front/`)

Są to samodzielne szablony dla dedykowanych stron front-office.

-   `access-denied.tpl`: Wyświetla komunikat, gdy klient próbuje uzyskać dostęp do pliku lub strony bez odpowiednich uprawnień.
-   `customerfilesmanager.tpl`: Główny szablon dla strony „Moje pliki” klienta, wyświetlający jego przesłane pliki.
-   `filesmanager.tpl`: Ogólny szablon menedżera plików, potencjalnie używany dla szerszej strony zarządzania plikami.
-   `my-files.tpl`: Inny szablon dla sekcji „Moje pliki”, prawdopodobnie podobny do `customerfilesmanager.tpl` lub konkretnego widoku w nim.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł prawdopodobnie tworzy co najmniej jedną niestandardową tabelę bazy danych do przechowywania informacji o przesłanych plikach.

-   **`ps_orderfiles_files` (lub podobna):**
    -   `id_order_file` (Klucz główny)
    -   `id_customer` (Link do `ps_customer`)
    -   `id_order` (Link do `ps_order`)
    -   `id_cart` (Link do `ps_cart`)
    -   `id_product` (Link do `ps_product`)
    -   `filename` (Oryginalna nazwa pliku)
    -   `filepath` (Ścieżka do przechowywanego pliku na serwerze)
    -   `file_extension`
    -   `file_size`
    -   `comment` (Komentarze użytkownika/administratora)
    -   `date_add`
    -   `date_upd`
    -   `is_admin_upload` (Wartość logiczna, aby rozróżnić przesyłanie przez klienta a przez administratora)
-   **`ps_configuration`:** Przechowuje wszystkie ustawienia modułu (np. `OF_ALLOW_CUSTOMER_UPLOAD`, `OF_MAX_FILE_SIZE`, `OF_ALLOWED_EXTENSIONS`, `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH` itp.). Te klucze są poprzedzone prefiksem `OF_` (Order Files).

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Wstrzykuje pliki CSS (`orderfiles.css`, `ajaxuploader.css`) i JavaScript (`jquery.form.js`, `script.js`, `script-customers.js`) modułu. |
| `displayProductAdditionalInfo` (lub podobny hook strony produktu) | Na stronie produktu, zazwyczaj poniżej głównych szczegółów produktu. | Renderuje `product-files.tpl` lub `displayProductPageUploadFormSmall.tpl` dla przesyłania plików specyficznych dla produktu. |
| `displayShoppingCartFooter` (lub podobny hook strony koszyka) | Na dole podsumowania koszyka. | Renderuje `shopping-cart.tpl` dla przesyłania plików w całym koszyku i alertów. |
| `displayCustomerAccount` | W panelu „Moje konto” klienta. | Renderuje `my-account.tpl` lub `my-account-17.tpl`, aby dodać link „Moje pliki”. |
| `displayMyAccountBlock` | W panelu „Moje konto” klienta (alternatywa dla niektórych motywów). | Renderuje `my-account.tpl` lub `my-account-17.tpl`, aby dodać link „Moje pliki”. |
| `displayOrderConfirmation` | Na stronie potwierdzenia zamówienia po udanym zakupie. | Renderuje `orderConfirmation.tpl`, aby wyświetlić opcje przesyłania lub podsumowania plików. |
| `displayOrderDetail` | Na stronie szczegółów zamówienia klienta w „Moim koncie”. | Renderuje `filesmanager-orderhistory.tpl`, aby wyświetlić pliki związane z konkretnym zamówieniem. |
| `displayLeftColumn` | W lewej kolumnie front-office. | Renderuje `tab.tpl` (lub podobny), aby wyświetlić link do menedżera plików. |
| `displayRightColumn` | W prawej kolumnie front-office. | Renderuje `tab.tpl` (lub podobny), aby wyświetlić link do menedżera plików. |
| `displayFooter` | W stopce front-office. | Renderuje `tab.tpl` (lub podobny), aby wyświetlić link do menedżera plików. |
| `actionObjectOrderAddAfter` | Po pomyślnym dodaniu nowego zamówienia do bazy danych. | Wyzwala powiadomienia e-mail do właściciela sklepu, jeśli klient przesłał pliki podczas realizacji transakcji. |
| `actionObjectOrderDeleteAfter` | Po usunięciu zamówienia z bazy danych. | Wyzwala usunięcie plików z serwera, jeśli włączono „Usuń pliki po usunięciu zamówienia”. |
| `actionObjectProductDeleteAfter` | Po usunięciu produktu z bazy danych. | Wyzwala usunięcie plików z serwera, jeśli włączono „Usuń pliki po usunięciu produktu”. |
| `actionObjectCartDeleteAfter` | Po usunięciu koszyka z bazy danych. | Wyzwala usunięcie plików z serwera, jeśli włączono „Usuń pliki po usunięciu koszyka”. |
| `actionObjectCustomerDeleteAfter` | Po usunięciu klienta z bazy danych. | Wyzwala usunięcie plików z serwera, jeśli włączono „Usuń pliki po usunięciu klienta”. |
| `actionAdminOrdersControllerSaveAfter` | Po zapisaniu/aktualizacji zamówienia w back-office. | Potencjalnie obsługuje przesyłanie plików przez administratora lub aktualizacje komentarzy ze strony szczegółów zamówienia. |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny jest ładowany i jego zasoby multimedialne są ustawiane. | Wstrzykuje pliki CSS (`backoffice.css`) i JavaScript (`orders.js`, `jquery.form.js`, `boscript.tpl`) modułu dla funkcjonalności back-office. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i wsparcie techniczne, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów lub pytań dotyczących modułu „Przesyłanie obrazów do zamówień”.
