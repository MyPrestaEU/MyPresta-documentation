---
title: "Maksymalna wartość zakupu według grup - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Maksymalna wartość zakupu według grup” od MyPresta.eu."
sidebar:
  label: "Maksymalna wartość zakupu według grup - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Maximum purchase value by groups na MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-groups.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/maximum-purchase-value-by-groups/)
>
> ---


# Maksymalna wartość zakupu według grup

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po zainstalowaniu modułu przejdź do **Moduły > Menedżer modułów** i wyszukaj „Maksymalna wartość zakupu według grup”. Kliknij przycisk „Konfiguruj”, aby uzyskać dostęp do jego ustawień.

Strona konfiguracji wyświetli listę wszystkich Twoich grup klientów, umożliwiając ustawienie maksymalnej wartości zakupu dla każdej z nich.

#### **Ustawienie: Maksymalna wartość zakupu dla [Nazwa Grupy Klientów]**

- **Co robi to ustawienie:** To pole wejściowe pozwala zdefiniować najwyższą całkowitą wartość zamówienia (z podatkiem lub bez, w zależności od ustawienia „Zastosuj podatek do maksymalnej wartości zakupu”), jaką mogą złożyć klienci należący do określonej grupy.
- **Efekt zmiany tego ustawienia:**
  - *Po wprowadzeniu wartości (np. 500):* Klienci z tej grupy nie będą mogli zrealizować zamówienia, jeśli suma ich koszyka przekroczy tę kwotę. Wiadomość ostrzegawcza pojawi się w koszyku i podczas realizacji zamówienia.
  - *Po pozostawieniu pustego lub ustawieniu na 0:* Nie będzie limitu maksymalnej wartości zakupu dla tej konkretnej grupy klientów. Mogą zamawiać dowolną kwotę.
- **Zalecana wartość:** Zależy to całkowicie od Twojego modelu biznesowego i segmentacji klientów.
  - Dla **Grup Hurtowych** możesz ustawić wysoki limit (np. 5000) lub pozostawić go pustym, jeśli im ufasz.
  - Dla **Grup Nowych Klientów** możesz ustawić niższy limit (np. 200), aby zarządzać ryzykiem.
  - Dla **Domyślnych Grup Klientów** możesz pozostawić go pustym, chyba że masz konkretny powód, aby ograniczyć ogólnych klientów.
- **Scenariusz / przykład dla sprzedawcy:** Masz grupę „Hurtownia Poziom 1”. Chcesz upewnić się, że żadne pojedyncze zamówienie z tej grupy nie przekroczy 10 000 € bez wcześniejszej zgody. Wprowadziłbyś `10000` w polu obok „Hurtownia Poziom 1”. Jeśli klient z tej grupy spróbuje zamówić za 10 001 €, zostanie zablokowany.

#### **Ustawienie: Zastosuj podatek do maksymalnej wartości zakupu**

- **Co robi to ustawienie:** Ten przełącznik określa, czy maksymalna wartość zakupu, którą ustawiasz dla każdej grupy, powinna być obliczana na podstawie sumy koszyka *z podatkami* czy *bez podatków*.
- **Efekt zmiany tego ustawienia:**
  - *Po włączeniu (TAK):* Moduł porówna sumę koszyka klienta *wraz ze wszystkimi obowiązującymi podatkami* z maksymalną wartością, którą zdefiniowałeś. Jest to zazwyczaj sposób, w jaki klienci postrzegają swój całkowity koszt.
  - *Po wyłączeniu (NIE):* Moduł porówna sumę koszyka klienta *bez podatków* z maksymalną wartością, którą zdefiniowałeś. Może to być przydatne, jeśli Twoje wewnętrzne rozliczenia lub umowy hurtowe są oparte na wartościach przed opodatkowaniem.
- **Zalecana wartość:** **TAK**. Większość sprzedawców i klientów myśli w kategoriach ceny końcowej, wliczając podatek. Włączenie tej opcji zapewnia, że limit dotyczy rzeczywistej kwoty, którą klient zapłaci.
- **Scenariusz / przykład dla sprzedawcy:** Ustawiasz maksymalną wartość 500 € dla grupy.
  - Jeśli „Zastosuj podatek” jest TAK: Klient z sumą koszyka 450 € (produkty) + 50 € (podatek) = 500 € zostanie dopuszczony. Koszyk o wartości 460 € (produkty) + 50 € (podatek) = 510 € zostanie zablokowany.
  - Jeśli „Zastosuj podatek” jest NIE: Klient z sumą koszyka 500 € (produkty) + 50 € (podatek) = 550 € zostanie dopuszczony, ponieważ suma produktów wynosi dokładnie 500 €.

#### **Ustawienie: Wyświetl wiadomość o ograniczeniach**

- **Co robi to ustawienie:** Ten przełącznik kontroluje, czy informacyjna wiadomość o przekroczeniu maksymalnej wartości zakupu jest wyświetlana klientowi w front-office.
- **Efekt zmiany tego ustawienia:**
  - *Po włączeniu (TAK):* Klienci zobaczą wyraźną, przyjazną dla użytkownika wiadomość na stronach koszyka i realizacji zamówienia, jeśli suma ich zamówienia przekroczy limit dla ich grupy. Pomaga im to zrozumieć, dlaczego nie mogą kontynuować.
  - *Po wyłączeniu (NIE):* Ograniczenie nadal będzie egzekwowane (klienci zostaną zablokowani przed złożeniem zamówienia), ale żadna wyraźna wiadomość nie zostanie wyświetlona. Może to prowadzić do zamieszania i złego doświadczenia klienta, ponieważ nie będą wiedzieć, *dlaczego* nie mogą dokończyć zamówienia.
- **Zalecana wartość:** **TAK**. Zawsze informuj swoich klientów jasno. Ukrywanie wiadomości doprowadzi tylko do frustracji i zgłoszeń do wsparcia.
- **Scenariusz / przykład dla sprzedawcy:** Klient próbuje zamówić za dużo. Jeśli ta opcja jest włączona, widzi: „Twoje zamówienie przekracza maksymalną dozwoloną wartość dla Twojej grupy klientów (500 €). Zmniejsz sumę koszyka, aby kontynuować.” Jeśli wyłączona, widzi tylko błąd lub przycisk „Przejdź do kasy” pozostaje nieaktywny bez wyjaśnienia.

#### **Ustawienie: Wiadomość do wyświetlenia**

- **Co robi to ustawienie:** To pole tekstowe pozwala dostosować wiadomość, którą klienci widzą, gdy przekroczą maksymalną wartość zakupu dla swojej grupy. Możesz uczynić ją bardziej specyficzną dla marki lub zasad Twojego sklepu.
- **Efekt zmiany tego ustawienia:**
  - *Po wprowadzeniu niestandardowej wiadomości:* Ta wiadomość zostanie wyświetlona klientom zamiast domyślnej wiadomości modułu. Możesz użyć HTML do podstawowego formatowania.
  - *Po pozostawieniu pustego:* Moduł wyświetli domyślną, ogólną wiadomość (np. „Twoje zamówienie przekracza maksymalną dozwoloną wartość dla Twojej grupy klientów.”).
- **Zalecana wartość:** Dostosuj ją tak, aby była przyjazna i pomocna. Uwzględnij symbole zastępcze, takie jak `{max_value}` i `{currency_sign}`, jeśli moduł je obsługuje (sprawdź rzeczywiste zachowanie modułu, ponieważ ten konkretny moduł może nie używać symboli zastępczych bezpośrednio, ale dynamicznie wstawiać wartość). Dobra domyślna wartość jest często wystarczająca.
- **Scenariusz / przykład dla sprzedawcy:** Zamiast ogólnej wiadomości, możesz chcieć powiedzieć: „Szanowny kliencie, Twoja obecna suma zamówienia przekracza maksymalną dozwoloną wartość zakupu {max_value} {currency_sign} dla Twojego typu konta. Prosimy o dostosowanie koszyka lub skontaktowanie się z naszym zespołem sprzedaży w przypadku większych zamówień.”

Pamiętaj, aby kliknąć przycisk **„Zapisz”** na dole strony konfiguracji po wprowadzeniu jakichkolwiek zmian.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Maksymalna wartość zakupu dla [Nazwa Grupy] | Puste / Różne | Ustawia górny limit wydatków dla konkretnej grupy klientów. Puste oznacza brak limitu. |
| Konfiguracja modułu | Zastosuj podatek do maksymalnej wartości zakupu | TAK | Określa, czy limit dotyczy sumy koszyka z podatkami czy bez. Zalecane: TAK (cena końcowa). |
| Konfiguracja modułu | Wyświetl wiadomość o ograniczeniach | TAK | Kontroluje, czy klienci widzą wyjaśnienie, gdy są zablokowani. Zalecane: TAK (dla jasności). |
| Konfiguracja modułu | Wiadomość do wyświetlenia | Domyślna wiadomość | Dostosowuje wiadomość ostrzegawczą wyświetlaną klientom. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Ustawiłem limit, ale klienci nadal mogą zamawiać więcej. Co jest nie tak?**
O:

1. **Sprawdź grupę klienta:** Upewnij się, że klient, którego testujesz, faktycznie należy do grupy, dla której ustawiłeś limit.
2. **Ustawienie „Zastosuj podatek”:** Dokładnie sprawdź, czy ustawienie „Zastosuj podatek do maksymalnej wartości zakupu” jest poprawnie skonfigurowane. Jeśli Twój limit wynosi 500 i jest ustawiony na „NIE” (wyklucz podatek), klient może być w stanie zamówić produkty za 500 + podatek, co wydaje się przekraczać 500.
3. **Moduł włączony:** Upewnij się, że moduł jest faktycznie włączony w Menedżerze modułów.
4. **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) i pamięć podręczną przeglądarki.

**P: Wiadomość o ograniczeniu nie jest wyświetlana, ale klienci nadal są blokowani.**
O: Sprawdź ustawienie „Wyświetl wiadomość o ograniczeniach” w konfiguracji modułu. Upewnij się, że jest ustawione na „TAK”. Jeśli jest ustawione na „NIE”, moduł będzie egzekwował limit cicho, co może być mylące dla klientów.

**P: Czy mogę ustawić różne wiadomości dla różnych grup klientów?**
O: Nie, moduł obecnie używa jednego ustawienia „Wiadomość do wyświetlenia”, które dotyczy wszystkich grup. Jeśli potrzebujesz wiadomości specyficznych dla grupy, wymagałoby to niestandardowego rozwoju.

**P: Czy ten moduł wpływa na rabaty lub koszty wysyłki?**
O: Moduł zazwyczaj ocenia *ostateczną sumę koszyka* w momencie realizacji zamówienia, która zazwyczaj obejmuje rabaty, koszty wysyłki i podatki (w zależności od ustawienia „Zastosuj podatek”). Zatem limit dotyczy ostatecznej kwoty, którą klient ma zapłacić.

**P: Mój niestandardowy motyw nie wyświetla wiadomości poprawnie.**
O: Może się to zdarzyć, jeśli Twój motyw ma bardzo dostosowane szablony koszyka lub realizacji zamówienia.

1. **Wyczyść pamięć podręczną Smarty:** Przejdź do **Zaawansowane > Wydajność**, ustaw „Kompilacja szablonów” na „Wymuś kompilację” i „Pamięć podręczna” na „Nie”, a następnie wyczyść pamięć podręczną. Przetestuj ponownie. Po zakończeniu przywróć ustawienia.
2. **Konflikt CSS:** CSS Twojego motywu może nadpisywać stylizację modułu. Może być potrzebny programista stron internetowych, aby zbadać element i zastosować niestandardowy CSS, aby upewnić się, że wiadomość jest widoczna i poprawnie ostylowana.
3. **Problem z hookiem:** Upewnij się, że Twój motyw poprawnie wywołuje standardowe hooki PrestaShop, w których moduł wstrzykuje swoją zawartość (np. `displayShoppingCart`, `displayPaymentTop`).

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Maximum purchase value by groups` (`cgmaxa`) to standardowy moduł PrestaShop implementujący wzorzec MVC. Działa głównie poprzez podłączanie się do kluczowych zdarzeń front-office podczas procesu koszyka i realizacji zamówienia w celu walidacji bieżącej sumy koszyka względem limitów specyficznych dla grupy, przechowywanych w tabeli `ps_configuration`. Wykorzystuje kontroler frontowy do żądań AJAX w celu zapewnienia dynamicznej informacji zwrotnej oraz główną klasę modułu do konfiguracji i rejestracji hooków.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

- `cgmaxa/controllers/front/ajax.php`
  - **Nazwa klasy**: `CgmaxaAjaxModuleFrontController` (rozszerza `ModuleFrontController`)
  - **Odpowiedzialność**: Ten kontroler obsługuje żądania AJAX z front-office, prawdopodobnie w celu walidacji sumy koszyka w czasie rzeczywistym, gdy elementy są dodawane/usuwane lub podczas kroków realizacji zamówienia. Zazwyczaj otrzymywałby dane koszyka, wykonywałby sprawdzenie limitu i zwracałby odpowiedź JSON wskazującą, czy limit został przekroczony i odpowiednią wiadomość.
- `cgmaxa/controllers/front/index.php`
  - **Nazwa klasy**: `CgmaxaIndexModuleFrontController` (rozszerza `ModuleFrontController`)
  - **Odpowiedzialność**: Ten kontroler może być miejscem zastępczym lub używanym do specyficznego routingu, który nie pasuje do głównego rozsyłania modułu. Biorąc pod uwagę jego nazwę, mógłby potencjalnie być domyślnym punktem wejścia lub obsługiwać interakcje front-office inne niż AJAX, gdyby moduł miał dedykowaną stronę, chociaż jego podstawowa funkcja dla tego modułu jest prawdopodobnie minimalna lub służy jako fallback.

#### Kontrolery administracyjne Back-Office

Ten moduł nie wydaje się używać żadnych dedykowanych kontrolerów administracyjnych. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

Ten moduł nie wydaje się definiować żadnych niestandardowych klas ani `ObjectModel` w katalogu `classes/`. Cała logika jest hermetyzowana w głównym pliku modułu (`cgmaxa.php`) i jego kontrolerach. Wartości konfiguracyjne są przechowywane bezpośrednio w `ps_configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

- `cgmaxa/views/js/cgmaxa.js`
  - **Zakres**: Front-office.
  - **Szczegóły**: Ten skrypt jest odpowiedzialny za interakcje po stronie klienta. Prawdopodobnie wiąże się ze zdarzeniami takimi jak zmiany ilości w koszyku, dodawanie/usuwanie produktów lub nawigacja po krokach realizacji zamówienia. Wysyłałby żądania AJAX do `cgmaxa/controllers/front/ajax.php` w celu walidacji sumy koszyka w czasie rzeczywistym. Po otrzymaniu odpowiedzi dynamicznie wyświetlałby wiadomość ostrzegawczą (jeśli limit został przekroczony) i potencjalnie wyłączałby przyciski „Przejdź do kasy” lub „Płatność”, aby zapobiec finalizacji zamówienia. Może również dynamicznie aktualizować wiadomość z bieżącą wartością koszyka i maksymalną dozwoloną wartością.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `cgmaxa/css.css`
  - **Zakres**: Front-office.
  - **Szczegóły**: Ten arkusz stylów zapewnia podstawowe stylizowanie wiadomości ostrzegawczej wyświetlanej klientom, gdy przekroczą limit zakupu. Prawdopodobnie definiuje klasy dla kontenera wiadomości, koloru tekstu, tła i ewentualnie ikon, aby alert wyróżniał się. Programiści mogą nadpisać te style w pliku `custom.css` swojego motywu lub używając bardziej specyficznych selektorów.
- `cgmaxa/views/css/cgmaxa.css`
  - **Zakres**: Front-office.
  - **Szczegóły**: Podobnie jak `cgmaxa/css.css`, ten plik zapewnia stylizację dla elementów front-office. Może zawierać bardziej specyficzne lub zaktualizowane style w porównaniu do `cgmaxa/css.css`, lub jeden z nich może być plikiem starszym. Programiści powinni zbadać oba, aby zrozumieć pełne zastosowane stylizacje. Kluczowe selektory będą celować w kontener wiadomości i jego zawartość.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

- `cgmaxa/views/templates/front/displayShoppingCart.tpl`
  - **Hook**: `displayShoppingCart` (i potencjalnie `displayPaymentTop`, `stepBeforePaymentOPC`, `displaystepBeforePaymentOPC`).
  - **Wyjście**: Ten szablon jest odpowiedzialny za renderowanie wiadomości ostrzegawczej na stronie koszyka i potencjalnie na innych krokach realizacji zamówienia. Zawierałby strukturę HTML dla pola alertu, dynamicznie wstawiając niestandardową wiadomość i maksymalną dozwoloną wartość, jeśli limit zostanie przekroczony. Prawdopodobnie używa zmiennych Smarty przekazanych z metod hooków modułu, aby określić, czy wiadomość powinna być wyświetlona i jaką zawartość powinna zawierać.

#### Szablony administracyjne (`views/templates/admin/`)

- `cgmaxa/admin.tpl`
  - **Zakres**: Konfiguracja Back-office.
  - **Wyjście**: Ten szablon jest używany przez metodę `getContent()` modułu do renderowania formularza konfiguracji w Panelu administracyjnym PrestaShop. Zawiera pola wejściowe dla maksymalnej wartości każdej grupy klientów, przełącznik „Zastosuj podatek”, przełącznik „Wyświetl wiadomość” i pole tekstowe niestandardowej wiadomości. Iteruje przez dostępne grupy klientów, aby utworzyć dynamiczne pola wejściowe.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Wszystkie ustawienia konfiguracyjne (maksymalne wartości na grupę, ustawienie podatku, wyświetlanie wiadomości, niestandardowa wiadomość) są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `CGMAXA_GROUP_[ID_GROUP]`, `CGMAXA_TAX`, `CGMAXA_DISPLAY_MESSAGE`, `CGMAXA_MESSAGE`.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Aby dołączyć niezbędne pliki CSS i JavaScript (`cgmaxa.js`, `cgmaxa.css`) dla funkcjonalności front-office i walidacji AJAX. |
| `displayShoppingCart` | Na stronie podsumowania koszyka. | Aby wyświetlić wiadomość ostrzegawczą, jeśli suma koszyka przekracza limit grupy i potencjalnie wyłączyć przycisk „Przejdź do kasy”. |
| `displayPaymentTop` | Na górze kroku wyboru płatności w procesie realizacji zamówienia. | Aby ponownie zweryfikować sumę koszyka przed płatnością i wyświetlić wiadomość ostrzegawczą, blokując dalszy postęp, jeśli limit zostanie przekroczony. |
| `stepBeforePaymentOPC` | Przed krokiem płatności w One-Page Checkout (OPC). | Podobnie jak `displayPaymentTop`, ten hook zapewnia, że walidacja następuje tuż przed tym, jak klient może wybrać metodę płatności, co jest kluczowe dla przepływów OPC. |
| `displaystepBeforePaymentOPC` | Kolejny hook związany z krokiem przed płatnością w OPC. | Zapewnia dodatkowy punkt do walidacji i wyświetlania wiadomości w specyficznych motywach lub konfiguracjach OPC. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Maksymalna wartość zakupu według grup”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i konfiguracji modułu.
