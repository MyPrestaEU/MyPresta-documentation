---
title: "Kupony dla Fanów Facebooka - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Kupony dla Fanów Facebooka od MyPresta.eu."
sidebar:
  label: "Kupony dla Fanów Facebooka - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook Fan Coupons na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-fan-coupons.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-fan-coupons/)
>
> ---


# Kupony dla Fanów Facebooka

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Twój serwer musi być w stanie komunikować się z API Facebooka.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu Kupony dla Fanów Facebooka, gdzie definiujesz, jak generowane są kupony i jak zachowuje się moduł.

#### Ustawienia ogólne

- **Co robi to ustawienie:** Te ustawienia kontrolują ogólne zachowanie modułu, w tym aktualizacje i podstawową funkcjonalność.
- **Wpływ zmiany tego ustawienia:**
  - `mypresta_updates`, `update_`, `updatev_`: Są to wewnętrzne ustawienia związane z aktualizacjami modułu i sprawdzaniem wersji przez MyPresta.eu. Zazwyczaj nie musisz ich zmieniać.
- **Zalecana wartość:** Pozostaw te wartości domyślne.
- **Scenariusz / przykład sprzedawcy:** Te ustawienia zapewniają, że Twój moduł jest aktualny i kompatybilny z usługami MyPresta.eu.

#### Ustawienia generowania kuponów

- **FANCOUPON\_FONTSTYLE**

  - **Co robi to ustawienie:** Definiuje styl czcionki używany dla wygenerowanego kodu kuponu wyświetlanego klientowi na Twojej zakładce Facebooka. Jest to wyłącznie kwestia prezentacji wizualnej.
  - **Wpływ zmiany tego ustawienia:**
    - *Po ustawieniu na konkretną czcionkę:* Kod kuponu zostanie wyświetlony tą czcionką, co sprawi, że będzie bardziej atrakcyjny wizualnie lub dopasowany do Twojej marki.
    - *Po pozostawieniu domyślnego:* Zostanie użyta standardowa, czytelna czcionka.
  - **Zalecana wartość:** Wybierz wyraźną, czytelną czcionkę, która pasuje do estetyki Twojej marki.
  - **Scenariusz / przykład sprzedawcy:** Jeśli Twoja marka używa konkretnej stylowej czcionki, możesz wpisać jej nazwę tutaj (np. „Arial Black”, „Verdana”), aby kupon wyglądał bardziej spójnie.
- **FANCOUPON\_VOUCHERCODE**

  - **Co robi to ustawienie:** Jest to *prefiks* dla automatycznie generowanych kodów voucherów. Każdy kod będzie zaczynał się od tego tekstu, po którym nastąpią losowe znaki.
  - **Wpływ zmiany tego ustawienia:**
    - *Po ustawieniu na „FANCOUPON”:* Wszystkie wygenerowane kody będą wyglądać jak „FANCOUPONABCD123”.
    - *Po ustawieniu na „FBPROMO”:* Wszystkie wygenerowane kody będą wyglądać jak „FBPROMOXYZ789”.
  - **Zalecana wartość:** Krótki, łatwy do zapamiętania prefiks związany z Facebookiem lub Twoją promocją (np. „FBPROMO”, „FAN2024”, „MYFAN”).
  - **Scenariusz / przykład sprzedawcy:** Użycie „FBPROMO” pomaga łatwo zidentyfikować, które zamówienia pochodziły z tej kampanii na Facebooku w historii zamówień PrestaShop.
- **FANCOUPON\_MODE**

  - **Co robi to ustawienie:** Określa rodzaj rabatu, jaki zapewni wygenerowany kod vouchera (np. procentowy, stała kwota, darmowa wysyłka).
  - **Wpływ zmiany tego ustawienia:**
    - *Rabat procentowy:* Kupon zmniejszy całkowitą kwotę zamówienia o procent (np. 10% zniżki).
    - *Rabat o stałej kwocie:* Kupon zmniejszy całkowitą kwotę zamówienia o stałą wartość pieniężną (np. 10 zł zniżki).
    - *Darmowa wysyłka:* Kupon sprawi, że wysyłka będzie darmowa dla zamówienia.
  - **Zalecana wartość:** Zależy to od Twojej strategii marketingowej. Rabaty procentowe są często popularne w przypadku ogólnych promocji.
  - **Scenariusz / przykład sprzedawcy:** Aby zaoferować 15% zniżki dla nowych fanów Facebooka, należy wybrać tutaj „Rabat procentowy”, a następnie określić „15” w odpowiednim polu wartości (które pojawi się po wybraniu trybu).
- **FANCOUPON\_CHARS**

  - **Co robi to ustawienie:** Określa typy znaków (litery, cyfry), które będą używane w *losowej części* wygenerowanego kodu vouchera.
  - **Wpływ zmiany tego ustawienia:**
    - *Litery i cyfry:* Kody będą mieszanką znaków alfanumerycznych (np. „ABC123”).
    - *Tylko cyfry:* Kody będą zawierać tylko cyfry (np. „123456”).
    - *Tylko litery:* Kody będą zawierać tylko litery (np. „ABCDEF”).
  - **Zalecana wartość:** „Litery i cyfry” dla maksymalnej unikalności i bezpieczeństwa.
  - **Scenariusz / przykład sprzedawcy:** Aby kody były łatwiejsze do odczytania, możesz wybrać „Tylko litery”, ale to zmniejsza liczbę możliwych unikalnych kombinacji dla danej długości.
- **FANCOUPON\_LENGTH**

  - **Co robi to ustawienie:** Definiuje długość *losowej części* wygenerowanego kodu vouchera (bez prefiksu).
  - **Wpływ zmiany tego ustawienia:**
    - *Krótsza długość (np. 4):* Kody są szybsze do wpisania, ale mniej unikalne (np. „FBPROMOABCD”).
    - *Dłuższa długość (np. 8):* Kody są bezpieczniejsze i bardziej unikalne, ale ich wpisanie zajmuje więcej czasu (np. „FBPROMOABCD12345”).
  - **Zalecana wartość:** 6-8 znaków dla dobrej równowagi unikalności i użyteczności.
  - **Scenariusz / przykład sprzedawcy:** Jeśli spodziewasz się bardzo dużej liczby generowanych kuponów, dłuższa długość zapewnia, że każdy kod jest naprawdę unikalny i zapobiega przypadkowym duplikatom.
- **FANCOUPON\_VOUCHER\_CAT**

  - **Co robi to ustawienie:** Pozwala ograniczyć zastosowanie wygenerowanego kodu vouchera tylko do produktów w określonych kategoriach w Twoim sklepie.
  - **Wpływ zmiany tego ustawienia:**
    - *Po wybraniu konkretnych kategorii:* Kupon będzie działał tylko wtedy, gdy klient ma w koszyku produkty z tych kategorii.
    - *Po niewybraniu żadnych kategorii:* Kupon będzie dotyczył wszystkich produktów w sklepie.
  - **Zalecana wartość:** Pozostaw puste, jeśli kupon ma dotyczyć całego sklepu. Wybierz kategorie, jeśli chcesz promować konkretne linie produktów.
  - **Scenariusz / przykład sprzedawcy:** Jeśli prowadzisz promocję specjalnie dla swojej „Kolekcji Letniej”, wybierzesz tę kategorię tutaj, aby kupon działał tylko na te produkty.
- **PS\_LANG\_DEFAULT**

  - **Co robi to ustawienie:** Jest to domyślny identyfikator języka Twojego sklepu PrestaShop. Jest używany wewnętrznie przez moduł, aby zapewnić prawidłowe tworzenie opisów kuponów i innych elementów zależnych od języka.
  - **Wpływ zmiany tego ustawienia:** Nieprawidłowa zmiana tego ustawienia może prowadzić do problemów z tworzeniem kuponów w domyślnym języku Twojego sklepu.
  - **Zalecana wartość:** Pozostaw jako wartość domyślną automatycznie wykrytą przez PrestaShop.
  - **Scenariusz / przykład sprzedawcy:** Zapewnia to, że po wygenerowaniu kuponu jego wewnętrzny opis (np. „Kupon dla Fana Facebooka”) jest poprawnie ustawiony w Twoim głównym języku sklepu.

#### Ustawienia bloków reklamowych (Opcjonalne)

- **FANCOUPON\_ADV\_POS1**

  - **Co robi to ustawienie:** Kontroluje obraz/baner wyświetlany w **lewej kolumnie** Twojego sklepu PrestaShop w celu promowania oferty kuponowej na Facebooku.
  - **Wpływ zmiany tego ustawienia:**
    - *Po wprowadzeniu adresu URL obrazu:* Określony obraz pojawi się w lewej kolumnie.
    - *Po pozostawieniu pustego:* W lewej kolumnie nie zostanie wyświetlony żaden obraz.
  - **Zalecana wartość:** Atrakcyjny obraz banera (np. o szerokości 200px), który wyraźnie reklamuje ofertę „Polub nas na Facebooku, odbierz kupon!”.
  - **Scenariusz / przykład sprzedawcy:** Przesyłasz niestandardowy obraz banera na swój serwer (np. `img/cms/fb-coupon-left.jpg`) i wprowadzasz tutaj jego pełny adres URL.
- **FANCOUPON\_ADV\_POS2**

  - **Co robi to ustawienie:** Kontroluje obraz/baner wyświetlany w **prawej kolumnie** Twojego sklepu PrestaShop w celu promowania oferty kuponowej na Facebooku.
  - **Wpływ zmiany tego ustawienia:**
    - *Po wprowadzeniu adresu URL obrazu:* Określony obraz pojawi się w prawej kolumnie.
    - *Po pozostawieniu pustego:* W prawej kolumnie nie zostanie wyświetlony żaden obraz.
  - **Zalecana wartość:** Podobnie jak w przypadku `FANCOUPON_ADV_POS1`, atrakcyjny obraz banera (np. o szerokości 200px).
  - **Scenariusz / przykład sprzedawcy:** Możesz użyć innego projektu dla banera w prawej kolumnie lub po prostu zduplikować ten z lewej kolumny.
- **FANCOUPON\_ADV\_POS3**

  - **Co robi to ustawienie:** Kontroluje obraz/baner wyświetlany w **stopce** Twojego sklepu PrestaShop w celu promowania oferty kuponowej na Facebooku.
  - **Wpływ zmiany tego ustawienia:**
    - *Po wprowadzeniu adresu URL obrazu:* Określony obraz pojawi się w stopce.
    - *Po pozostawieniu pustego:* W stopce nie zostanie wyświetlony żaden obraz.
  - **Zalecana wartość:** Atrakcyjny obraz banera odpowiedni dla obszaru stopki.
  - **Scenariusz / przykład sprzedawcy:** Szerszy, krótszy baner (np. o szerokości 900px, wysokości 100px), który dobrze pasuje do stopki.
- **FANCOUPON\_ADV\_URL**

  - **Co robi to ustawienie:** Jest to adres URL, do którego będą prowadzić wszystkie banery reklamowe (`FANCOUPON_ADV_POS1`, `POS2`, `POS3`) po kliknięciu. Powinien to być bezpośredni adres URL do zakładki Twojej Strony Fanowskiej na Facebooku, gdzie można wygenerować kupon.
  - **Wpływ zmiany tego ustawienia:**
    - *Po ustawieniu na adres URL zakładki Facebooka:* Kliknięcie dowolnego banera przeniesie klienta bezpośrednio do zakładki generowania kuponów na Twojej stronie na Facebooku.
    - *Po pozostawieniu pustego lub nieprawidłowego:* Banery nie będą klikalne lub będą prowadzić do nieprawidłowej strony.
  - **Zalecana wartość:** Dokładny adres URL zakładki Twojej Strony Fanowskiej na Facebooku, gdzie osadzony jest moduł kuponów.
  - **Scenariusz / przykład sprzedawcy:** Po skonfigurowaniu zakładki Facebooka otrzymasz dla niej unikalny adres URL (np. `https://www.facebook.com/TWOJASTRO/app_1234567890`). Wprowadź ten adres URL tutaj.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | `FANCOUPON_FONTSTYLE` | Domyślna czcionka systemowa | Styl czcionki dla wyświetlanego kodu kuponu na Facebooku. |
| Konfiguracja modułu | `FANCOUPON_VOUCHERCODE` | `FANCOUPON` | Prefiks dla generowanych kodów voucherów. Pomaga zidentyfikować kampanię. |
| Konfiguracja modułu | `FANCOUPON_MODE` | Rabat procentowy | Rodzaj rabatu (procentowy, stała kwota, darmowa wysyłka). |
| Konfiguracja modułu | `FANCOUPON_CHARS` | Litery i cyfry | Zestaw znaków dla losowej części kodu. |
| Konfiguracja modułu | `FANCOUPON_LENGTH` | 6-8 znaków | Długość losowej części kodu. Wpływa na unikalność. |
| Konfiguracja modułu | `FANCOUPON_VOUCHER_CAT` | Puste (wszystkie produkty) | Ogranicza użycie kuponu do określonych kategorii produktów. |
| Konfiguracja modułu | `FANCOUPON_ADV_POS1` | Puste | Adres URL obrazu banera dla lewej kolumny. |
| Konfiguracja modułu | `FANCOUPON_ADV_POS2` | Puste | Adres URL obrazu banera dla prawej kolumny. |
| Konfiguracja modułu | `FANCOUPON_ADV_POS3` | Puste | Adres URL obrazu banera dla stopki. |
| Konfiguracja modułu | `FANCOUPON_ADV_URL` | Puste | Docelowy adres URL dla wszystkich banerów reklamowych (Twoja zakładka Facebooka). |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P: Moje kupony nie działają po wygenerowaniu.**
O: Sprawdź następujące elementy:
1. **Reguły koszyka PrestaShop:** Przejdź do **Katalog > Rabaty > Reguły koszyka** w panelu administracyjnym PrestaShop. Wyszukaj kupony z zdefiniowanym prefiksem (`FANCOUPON_VOUCHERCODE`). Upewnij się, że są aktywne i nie wygasły. Moduł tworzy je automatycznie, ale czasami może wystąpić ręczna interwencja lub konflikt.
2. **Konfiguracja modułu:** Sprawdź ponownie ustawienia `FANCOUPON_MODE` i `FANCOUPON_VOUCHER_CAT`. Jeśli ograniczyłeś kupon do kategorii, upewnij się, że klient próbuje go użyć na produktach z tej kategorii.
3. **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**) i pamięć podręczną przeglądarki.

**P: Banery reklamowe nie wyświetlają się w moim sklepie.**
O:
1. **Haki modułu:** Upewnij się, że moduł jest poprawnie podpięty. W **Moduły > Menedżer modułów** znajdź „Kupony dla Fanów Facebooka” i kliknij „Konfiguruj”. Sprawdź zakładkę „Pozycje” (lub „Haki” w starszych wersjach), aby sprawdzić, czy jest przypisany do `displayLeftColumn`, `displayRightColumn` lub `displayFooter`. Jeśli nie, może być konieczne ręczne podpięcie go za pomocą **Wygląd > Pozycje** (lub **Moduły > Pozycje**).
2. **Adresy URL obrazów:** Sprawdź, czy adresy URL wprowadzone dla `FANCOUPON_ADV_POS1`, `POS2`, `POS3` są poprawne i czy obrazy istnieją w tych lokalizacjach.
3. **Kompatybilność z motywem:** Niektóre niestandardowe motywy mogą nadpisywać standardowe pozycje haków. Jeśli banery nadal się nie pojawiają, może być konieczne, aby webmaster sprawdził pliki szablonów Twojego motywu.

**P: Zakładka Facebooka nie działa lub nie wyświetla generatora kuponów.**
O: Ten moduł zapewnia logikę backendu do generowania kuponów. Rzeczywista konfiguracja zakładki Facebooka odbywa się *w narzędziach deweloperskich Facebooka* lub w aplikacji innej firmy, która osadza niestandardową zawartość.
1. **Konfiguracja aplikacji Facebooka:** Upewnij się, że poprawnie skonfigurowałeś aplikację Facebooka i połączyłeś ją ze swoją Stroną Fanowską, wskazując adres URL modułu (który zazwyczaj jest domeną Twojego sklepu PrestaShop z określoną ścieżką lub dedykowaną stroną, którą skonfigurowałeś do hostowania danych wyjściowych modułu). Ten moduł zapewnia *logikę* kuponu, ale *wyświetlanie na Facebooku* wymaga prawidłowej konfiguracji aplikacji Facebooka.
2. **Uprawnienia strony na Facebooku:** Upewnij się, że Twoja strona na Facebooku ma niezbędne uprawnienia do niestandardowych zakładek.
3. **Bezpieczne połączenie (HTTPS):** Facebook wymaga, aby wszystkie osadzone aplikacje działały przez HTTPS. Upewnij się, że Twój sklep PrestaShop jest w pełni zabezpieczony certyfikatem SSL.

**P: Jak przetłumaczyć tekst modułu?**
O: Możesz przetłumaczyć frazy modułu za pośrednictwem panelu administracyjnego PrestaShop:
1. Przejdź do **Lokalizacja > Tłumaczenia** (lub **Lokalizacja > Tłumaczenia** w starszych wersjach).
2. Wybierz „Tłumaczenia zainstalowanych modułów”.
3. Wybierz swój motyw, swój język, a następnie wybierz „Kupony dla Fanów Facebooka” z listy modułów.
4. Możesz następnie edytować dowolne przetłumaczalne ciągi znaków używane przez moduł.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł Kupony dla Fanów Facebooka (`fancoupon`) to standardowy moduł PrestaShop, skupiający się głównie na logice backendu do generowania kuponów i podstawowej reklamie w front-office. Wykorzystuje klasę `Module` i klasę `Configuration` PrestaShop do przechowywania ustawień. Podstawowa funkcjonalność obejmuje dynamiczne tworzenie obiektów `CartRule` (voucherów) na podstawie interakcji użytkownika na zakładce Facebooka (która jest zewnętrzna wobec PrestaShop, ale współdziała z logiką modułu). Komponenty front-office ograniczają się do prostych banerów graficznych podpiętych do standardowych pozycji wyświetlania.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych dedykowanych kontrolerów front-office ani back-office. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównej klasy modułu. Wszelkie interakcje związane z generowaniem kuponów byłyby zazwyczaj obsługiwane przez zewnętrzną aplikację Facebooka, która wskazuje na adres URL w witrynie PrestaShop, co następnie wyzwala logikę modułu (prawdopodobnie za pośrednictwem haka lub niestandardowego punktu wejścia, który nie jest jawnie zdefiniowany jako `ModuleFrontController` w dostarczonym spisie, ale raczej obsługiwany przez podstawową logikę modułu po wywołaniu).

### 4.3 Główne klasy i modele (`classes/`)

Ten moduł **nie** zawiera żadnych niestandardowych klas ani modeli w katalogu `classes/`. Bezpośrednio wykorzystuje podstawowe klasy PrestaShop `CartRule` i `Configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

- `fancoupon/lib/voucherengine/script.js`
  - **Zakres:** Prawdopodobnie Front-office (przeznaczony dla interfejsu zakładki Facebooka).
  - **Odpowiedzialność:** Ten skrypt ma obsługiwać logikę po stronie klienta dla procesu generowania kuponów. Obejmowałoby to:
    - Wykrywanie, czy użytkownik „polubił” stronę na Facebooku (za pośrednictwem API Facebooka).
    - Wyzwalanie żądania AJAX do backendu PrestaShop (lub punktu wejścia modułu) w celu wygenerowania kuponu.
    - Wyświetlanie wygenerowanego kodu kuponu użytkownikowi.
    - Potencjalnie obsługę elementów interfejsu użytkownika, takich jak wskaźniki ładowania lub komunikaty o sukcesie/błędzie.
- `fancoupon/views/js/voucherengine/script.js`
  - **Zakres:** Prawdopodobnie Front-office (przeznaczony dla interfejsu zakładki Facebooka).
  - **Odpowiedzialność:** Wydaje się, że jest to duplikat lub wersja skryptu w `lib/`. Służyłby temu samemu celowi, co opisano powyżej, obsługując interaktywne elementy generowania kuponów na zakładce Facebooka. Programiści powinni zweryfikować, który `script.js` jest faktycznie ładowany i używany.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `fancoupon/lib/voucherengine/ps16.css`
  - **Zakres:** Stylizacja klienta w Front-office.
  - **Odpowiedzialność:** Zapewnia podstawową stylizację interfejsu generowania kuponów, prawdopodobnie w zakładce Facebooka. `ps16` w nazwie pliku sugeruje, że może zawierać style specjalnie dostosowane do domyślnej struktury motywu PrestaShop 1.6, ale powinien być ogólnie kompatybilny lub łatwo adaptowalny.
  - **Kluczowe selektory klas CSS:** Zazwyczaj obejmowałyby style dla przycisków, pól wejściowych, obszarów wyświetlania tekstu dla kodu kuponu i ogólnego układu generatora kuponów. Programiści mogą sprawdzić renderowany kod HTML na zakładce Facebooka, aby zidentyfikować konkretne selektory do nadpisania.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony haków (`views/templates/advert-*.tpl`)**:
  - `fancoupon/views/templates/advert-footer.tpl`
    - **Hak:** `displayFooter` (lub `footer` w starszych wersjach).
    - **Wyjście:** Renderuje baner reklamowy/obraz w stopce sklepu, linkujący do zakładki Strony Fanowskiej na Facebooku. Używa `FANCOUPON_ADV_POS3` jako źródła obrazu i `FANCOUPON_ADV_URL` jako linku.
  - `fancoupon/views/templates/advert-left.tpl`
    - **Hak:** `displayLeftColumn` (lub `leftcolumn` w starszych wersjach).
    - **Wyjście:** Renderuje baner reklamowy/obraz w lewej kolumnie sklepu, linkujący do zakładki Strony Fanowskiej na Facebooku. Używa `FANCOUPON_ADV_POS1` jako źródła obrazu i `FANCOUPON_ADV_URL` jako linku.
  - `fancoupon/views/templates/advert-right.tpl`
    - **Hak:** `displayRightColumn` (lub `rightcolumn` w starszych wersjach).
    - **Wyjście:** Renderuje baner reklamowy/obraz w prawej kolumnie sklepu, linkujący do zakładki Strony Fanowskiej na Facebooku. Używa `FANCOUPON_ADV_POS2` jako źródła obrazu i `FANCOUPON_ADV_URL` jako linku.
- **Szablony administracyjne (`views/templates/admin/`)**: Brak zidentyfikowanych.
- **Szablony front-office (`views/templates/front/`)**: Brak zidentyfikowanych. Główny interfejs użytkownika generowania kuponów jest prawdopodobnie renderowany dynamicznie za pomocą JavaScript lub bezpośrednio w logice `fancoupon.php` po wywołaniu z Facebooka.

### 4.7 Schemat bazy danych i mapa haków

- **Tabele bazy danych**:
  - Ten moduł nie tworzy niestandardowych tabel SQL.
  - Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop, używając kluczy takich jak `FANCOUPON_FONTSTYLE`, `FANCOUPON_VOUCHERCODE` itp.
  - Tworzy wpisy w `ps_cart_rule` i powiązanych tabelach (`ps_cart_rule_lang`, `ps_cart_rule_product_rule_group` itp.) dla każdego wygenerowanego kuponu.
- **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayLeftColumn` | Renderuje zawartość w lewym pasku bocznym sklepu. | Wyświetla baner reklamowy w lewej kolumnie. |
| `displayRightColumn` | Renderuje zawartość w prawym pasku bocznym sklepu. | Wyświetla baner reklamowy w prawej kolumnie. |
| `displayFooter` | Renderuje zawartość w sekcji stopki sklepu. | Wyświetla baner reklamowy w stopce. |
| `leftcolumn` | (PrestaShop 1.6.x i starsze) Renderuje zawartość w lewym pasku bocznym. | Starszy hak dla banera reklamowego w lewej kolumnie. |
| `rightcolumn` | (PrestaShop 1.6.x i starsze) Renderuje zawartość w prawym pasku bocznym. | Starszy hak dla banera reklamowego w prawej kolumnie. |
| `footer` | (PrestaShop 1.6.x i starsze) Renderuje zawartość w sekcji stopki. | Starszy hak dla banera reklamowego w stopce. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, wsparcie techniczne i wszelkie zapytania dotyczące modułu Kupony dla Fanów Facebooka, prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz dedykowany zespół wsparcia jest dostępny, aby pomóc sprzedawcom i programistom w przypadku wszelkich problemów lub pytań.
