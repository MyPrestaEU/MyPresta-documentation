---
title: "Rabaty kumulacyjne - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Rabaty kumulacyjne” od MyPresta.eu."
sidebar:
  label: "Rabaty kumulacyjne - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Cumulative discounts na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cumulative-discounts.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/cumulative-discounts/)
>
> ---


# Rabaty kumulacyjne

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości środowisk hostingowych kompatybilnych z PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji, na którym definiujesz, jak działa Twój program rabatów kumulacyjnych.

#### **Aktywuj program**

- **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania całego programu rabatów kumulacyjnych.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone:* Moduł będzie aktywnie śledzić wydatki klientów, przypisywać grupy i wyświetlać informacje o rabatach w Twoim front-office.
  - *Gdy wyłączone:* Moduł zaprzestanie wszystkich operacji, żadne rabaty nie zostaną zastosowane, a żadne informacje nie zostaną wyświetlone.
- **Zalecana wartość:** TAK (aby aktywować program).
- **Scenariusz / przykład dla sprzedawcy:** Jeśli konfigurujesz moduł po raz pierwszy, włącz go po skonfigurowaniu wszystkich innych ustawień. Jeśli musisz tymczasowo wstrzymać program (np. podczas dużej wyprzedaży, gdzie obowiązują inne rabaty), możesz go tutaj wyłączyć.

#### **Wyłącz program rabatów kumulacyjnych dla wybranych grup klientów**

- **Co robi to ustawienie:** Pozwala wybrać konkretne grupy klientów, które *nie* powinny być częścią programu rabatów kumulacyjnych. Klienci w tych wybranych grupach nie otrzymają rabatów kumulacyjnych, niezależnie od ich wydatków.
- **Efekt zmiany tego ustawienia:**
  - *Gdy grupa jest wybrana:* Klienci należący do tej grupy zostaną wykluczeni z programu.
  - *Gdy żadne grupy nie są wybrane:* Wszystkie grupy klientów są domyślnie uprawnione do programu.
- **Zalecana wartość:** Wybierz grupy takie jak „Goście” lub „Odwiedzający”, jeśli chcesz, aby uczestniczyli tylko zarejestrowani klienci. Możesz również wykluczyć grupę „Hurtową”, jeśli mają oddzielną strukturę cenową.
- **Scenariusz / przykład dla sprzedawcy:** Możesz mieć grupę klientów „Hurtowych”, która już otrzymuje specjalne ceny. Aby uniknąć konfliktów lub podwójnych rabatów, wybierzesz tutaj grupę „Hurtową”, aby wykluczyć ich z programu rabatów kumulacyjnych.

#### **Ramy czasowe**

- **Co robi to ustawienie:** Definiuje okres, w którym zamówienia klientów są brane pod uwagę przy obliczaniu ich całkowitych wydatków.
- **Efekt zmiany tego ustawienia:**
  - *Wszystkie zamówienia:* Uwzględnia każde zamówienie złożone przez klienta.
  - *Zamówienia z ostatniego roku / Zamówienia z ostatniego półrocza / Zamówienia z ostatniego kwartału / Zamówienia z ostatniego miesiąca / Zamówienia z ostatniego tygodnia / Zamówienia z ostatniego dnia:* Ogranicza obliczenia do zamówień złożonych w określonym, niedawnym okresie.
  - *Tylko ostatnie ważne zamówienie:* Uwzględnia tylko ostatnie zrealizowane zamówienie.
- **Zalecana wartość:** „Zamówienia z ostatniego roku” lub „Wszystkie zamówienia” to typowe wybory dla programów lojalnościowych. „Zamówienia z ostatniego miesiąca” mogą być używane do bardziej agresywnego, krótkoterminowego programu lojalnościowego.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz nagradzać długoterminową lojalność, wybierz „Wszystkie zamówienia”. Jeśli chcesz zachęcić do niedawnych, częstych zakupów, „Zamówienia z ostatniego półrocza” mogą być bardziej odpowiednie.

#### **Typ ceny**

- **Co robi to ustawienie:** Określa, czy obliczenia wydatków kumulacyjnych powinny używać „Ceny netto” (ceny przed podatkami) czy „Ceny brutto” (ceny zawierającej podatki) produktów w zamówieniach.
- **Efekt zmiany tego ustawienia:**
  - *Cena netto:* Całkowite wydatki zostaną obliczone na podstawie cen produktów bez podatków.
  - *Cena brutto:* Całkowite wydatki zostaną obliczone na podstawie cen produktów zawierających podatki.
- **Zalecana wartość:** „Cena brutto” jest często bardziej intuicyjna dla klientów, ponieważ odzwierciedla to, co faktycznie zapłacili. Jednak „Cena netto” może być preferowana dla sklepów B2B lub dla wewnętrznej spójności księgowej.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja grupa docelowa to głównie konsumenci, użycie „Ceny brutto” ma największy sens, ponieważ jest zgodne z ostateczną ceną, którą widzą i płacą.

#### **Wybierz statusy zamówień**

- **Co robi to ustawienie:** Pozwala określić, które statusy zamówień powinny być uwzględnione przy obliczaniu całkowitych wydatków klienta. Tylko zamówienia z wybranymi statusami będą wliczane do sumy kumulacyjnej.
- **Efekt zmiany tego ustawienia:**
  - *Gdy wybrane są „Płatność zaakceptowana” i „Dostarczone”:* Tylko zamówienia, które zostały pomyślnie opłacone i dostarczone, przyczynią się do całkowitych wydatków klienta.
  - *Gdy „Anulowane” lub „Zwrócone” NIE są wybrane:* Te zamówienia nie będą się liczyć, zapobiegając zdobywaniu punktów lojalnościowych przez klientów za niezrealizowane zakupy.
- **Zalecana wartość:** Wybierz statusy, które wskazują na zakończoną i udaną transakcję, takie jak „Płatność zaakceptowana”, „Dostarczone”. Wyklucz statusy takie jak „Anulowane”, „Zwrócone”, „Błąd płatności” itp.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz mieć pewność, że tylko rzeczywiste, zakończone zakupy przyczyniają się do lojalności. Wybierzesz „Płatność zaakceptowana” i „Dostarczone”, aby zapewnić, że klienci zdobywają rabaty tylko za zamówienia, za które faktycznie zapłacili i które otrzymali.

#### **Wyklucz zamówienia złożone z kodem kuponu**

- **Co robi to ustawienie:** Jeśli włączone, zamówienia, w których użyto kuponu lub kodu rabatowego, nie będą wliczane do całkowitych wydatków kumulacyjnych klienta.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone:* Zamówienia z kuponami są ignorowane w obliczeniach lojalnościowych.
  - *Gdy wyłączone:* Zamówienia z kuponami *są* wliczane do sumy kumulacyjnej.
- **Zalecana wartość:** TAK, jeśli chcesz mocniej nagradzać zakupy w pełnej cenie. NIE, jeśli chcesz, aby każdy zakup, nawet ten z rabatem, przyczyniał się do lojalności.
- **Scenariusz / przykład dla sprzedawcy:** Prowadzisz specjalną promocję z kuponem -20%. Jeśli włączysz to ustawienie, klienci używający tego kuponu nie będą mieli tego zamówienia wliczonego do postępu rabatu kumulacyjnego, zapewniając, że zdobywają lojalność za zakupy w pełnej cenie.

#### **Wyklucz produkty z cenami specjalnymi**

- **Co robi to ustawienie:** Jeśli włączone, produkty, które mają „cenę specjalną” (np. specjalną cenę promocyjną ustawioną na ograniczony czas lub dla konkretnej grupy klientów), nie będą wliczane do obliczeń wydatków kumulacyjnych.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone:* Produkty z cenami specjalnymi są ignorowane w obliczeniach lojalnościowych.
  - *Gdy wyłączone:* Produkty z cenami specjalnymi *są* wliczane do sumy kumulacyjnej.
- **Zalecana wartość:** TAK, jeśli chcesz nagradzać zakupy produktów w regularnej cenie. NIE, jeśli chcesz, aby wszystkie zakupy produktów przyczyniały się.
- **Scenariusz / przykład dla sprzedawcy:** Masz błyskawiczną wyprzedaż na niektóre produkty, używając funkcji cen specjalnych PrestaShop. Jeśli to włączysz, zakup tych produktów z wyprzedaży nie pomoże klientowi osiągnąć kolejnego progu lojalności, zachęcając go do zakupu produktów w regularnej cenie.

#### **Wyklucz produkty z rabatami ilościowymi**

- **Co robi to ustawienie:** Jeśli włączone, produkty, które zostały zakupione z rabatem ilościowym (np. „Kup 3, otrzymaj 10% zniżki”), nie będą wliczane do obliczeń wydatków kumulacyjnych.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone:* Produkty kupione z rabatami ilościowymi są ignorowane w obliczeniach lojalnościowych.
  - *Gdy wyłączone:* Produkty kupione z rabatami ilościowymi *są* wliczane do sumy kumulacyjnej.
- **Zalecana wartość:** TAK, jeśli chcesz nagradzać zakupy pojedynczych produktów w pełnej cenie. NIE, jeśli chcesz zachęcać do zakupów hurtowych, aby przyczyniały się do lojalności.
- **Scenariusz / przykład dla sprzedawcy:** Oferujesz ofertę „kup 5, otrzymaj 15% zniżki”. Jeśli to włączysz, klienci korzystający z tej oferty nie będą mieli tych konkretnych produktów wliczonych do postępu rabatu kumulacyjnego.

#### **Domyślna grupa klientów**

- **Co robi to ustawienie:** Definiuje domyślną grupę klientów, do której klienci zostaną przypisani, jeśli nie spełniają kryteriów wydatków dla żadnej innej grupy rabatów kumulacyjnych. Jest to zazwyczaj Twoja standardowa grupa „Klient”.
- **Efekt zmiany tego ustawienia:** Zapewnia, że klienci zawsze należą do ważnej grupy, nawet jeśli nie wydali wystarczająco, aby kwalifikować się do specjalnego progu rabatowego.
- **Zalecana wartość:** Twoja standardowa grupa „Klient” (często ID 3).
- **Scenariusz / przykład dla sprzedawcy:** Nowy klient rejestruje się. Nie dokonał jeszcze żadnych zakupów, więc moduł przypisuje go do „Domyślnej grupy klientów” (np. „Klient”), która może mieć 0% rabatu. W miarę wydawania pieniędzy zostanie przeniesiony do grup „Brązowa”, „Srebrna” itp.

#### **Informacje dla zalogowanych klientów (Strona produktu)**

- **Co robi to ustawienie:** Jest to edytor tekstu, w którym możesz dostosować wiadomość wyświetlaną *zalogowanym klientom* na stronach produktów. Ta wiadomość zazwyczaj informuje ich o ich aktualnym statusie rabatowym lub postępie.
- **Efekt zmiany tego ustawienia:** Wprowadzony tutaj tekst pojawi się na stronach produktów dla klientów, którzy są zalogowani na swoje konto. Możesz używać zmiennych Smarty (takich jak `{$total_spent}`, `{$discount_value}`, `{$next_group_name}`, `{$next_group_value}`) do personalizacji wiadomości.
- **Zalecana wartość:** Powitalna wiadomość, taka jak: „Witaj {$customer\_name}! Jesteś obecnie w grupie {$current\_group\_name} i otrzymujesz {$discount\_value}% rabatu. Wydaj jeszcze {$to\_next\_group}, aby osiągnąć grupę {$next\_group\_name} i otrzymać {$next\_group\_value}% zniżki!”
- **Scenariusz / przykład dla sprzedawcy:** Chcesz zmotywować zalogowanych klientów. Możesz im dokładnie powiedzieć, ile jeszcze muszą wydać, aby uzyskać wyższy rabat, tworząc jasną zachętę.

#### **Informacje dla niezalogowanych klientów (Strona produktu)**

- **Co robi to ustawienie:** Jest to edytor tekstu, w którym możesz dostosować wiadomość wyświetlaną *gościom lub niezalogowanym klientom* na stronach produktów. Ta wiadomość zazwyczaj zachęca ich do rejestracji i udziału w programie lojalnościowym.
- **Efekt zmiany tego ustawienia:** Wprowadzony tutaj tekst pojawi się na stronach produktów dla klientów, którzy nie są zalogowani na swoje konto.
- **Zalecana wartość:** Zachęcająca wiadomość, taka jak: „Zarejestruj się teraz i zacznij zdobywać rabaty kumulacyjne! Im więcej wydajesz, tym więcej oszczędzasz!”
- **Scenariusz / przykład dla sprzedawcy:** Nowy odwiedzający trafia na stronę produktu. Ta wiadomość może zachęcić go do utworzenia konta, podkreślając korzyści z Twojego programu lojalnościowego, potencjalnie przekształcając go w zarejestrowanego klienta.

#### **Informacje dla zalogowanych klientów (Strona koszyka)**

- **Co robi to ustawienie:** Jest to edytor tekstu, w którym możesz dostosować wiadomość wyświetlaną *zalogowanym klientom* na stronie koszyka. Ta wiadomość może wzmocnić ich status rabatowy lub pokazać, jak ich obecny koszyk przyczynia się do ich lojalności.
- **Efekt zmiany tego ustawienia:** Wprowadzony tutaj tekst pojawi się na stronie koszyka dla zalogowanych klientów. Możesz używać zmiennych Smarty.
- **Zalecana wartość:** Podobnie jak wiadomość na stronie produktu, ale być może podkreślająca wkład obecnego koszyka: „Wartość Twojego obecnego koszyka to {$cart\_value}. Dzięki rabatowi {$current\_group\_name} oszczędzasz {$discount\_value}%! Wydaj jeszcze {$to\_next\_group}, aby osiągnąć grupę {$next\_group\_name}!”
- **Scenariusz / przykład dla sprzedawcy:** Klient jest gotowy do realizacji zamówienia. Ta wiadomość przypomina mu o korzyściach z lojalności i może nawet zachęcić go do dodania małego przedmiotu, aby osiągnąć kolejny próg rabatowy.

#### **Informacje dla niezalogowanych klientów (Strona koszyka)**

- **Co robi to ustawienie:** Jest to edytor tekstu, w którym możesz dostosować wiadomość wyświetlaną *gościom lub niezalogowanym klientom* na stronie koszyka. Ta wiadomość zachęca ich do rejestracji przed sfinalizowaniem zakupu, aby zacząć zdobywać lojalność.
- **Efekt zmiany tego ustawienia:** Wprowadzony tutaj tekst pojawi się na stronie koszyka dla niezalogowanych klientów.
- **Zalecana wartość:** „Nie przegap rabatów lojalnościowych! Zarejestruj się przed dokonaniem płatności, aby zacząć zdobywać nagrody za swoje zakupy!”
- **Scenariusz / przykład dla sprzedawcy:** Klient-gość ma produkty w koszyku. Ta wiadomość stanowi ostatni impuls do zarejestrowania konta, przekształcając jednorazowego kupującego w potencjalnego lojalnego klienta.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### AdminCudiListController (Panel administracyjny > Rabaty kumulacyjne > Zarządzaj rabatami)

- **Nazwa ekranu i lokalizacja w menu:** Ten ekran można znaleźć, przechodząc do **Katalog > Rabaty kumulacyjne** (lub podobnej lokalizacji w zależności od wersji PrestaShop i dostosowania menu). Dokładna etykieta może brzmieć „Zarządzaj rabatami” lub „Zasady rabatów kumulacyjnych”.
- **Dostępne akcje i ustawienia:** Ten ekran przedstawia siatkę (listę) zdefiniowanych zasad rabatów kumulacyjnych. Każda zasada określa:
  - **Minimalna kwota wydatków:** Całkowita kwota, jaką klient musi wydać, aby kwalifikować się do tej grupy.
  - **Grupa klientów:** Grupa klientów PrestaShop, do której zostaną przypisani klienci spełniający kryteria wydatków.
  - **Procent rabatu:** Procent rabatu związany z tą grupą klientów.
  - **Akcje:** Możesz „Dodaj nową” zasadę, „Edytuj” istniejące zasady lub „Usuń” zasady.
- **Efekt zmian:**
  - **Dodanie nowej zasady:** Tworzy nowy poziom w Twoim programie lojalnościowym. Na przykład: „Wydaj 500 zł, aby dołączyć do grupy Złotej i otrzymać 15% zniżki.”
  - **Edycja zasady:** Modyfikuje próg wydatków lub przypisaną grupę/rabat dla istniejącego poziomu. Zmiany wpłyną na przyszłe przypisania grup i ponowne obliczenia.
  - **Usunięcie zasady:** Usuwa poziom lojalności. Klienci wcześniej w tej grupie zostaną ponownie przypisani na podstawie pozostałych zasad.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
  1. **Zaplanuj swoje poziomy:** Zdecyduj o progach wydatków i odpowiadających im grupach rabatowych (np. Brązowa: 100 zł za 5%, Srebrna: 500 zł za 10%, Złota: 1000 zł za 15%).
  2. **Utwórz grupy klientów:** Upewnij się, że masz odpowiednie grupy klientów w PrestaShop (Panel administracyjny > Klienci > Grupy) dla każdego poziomu (np. „Klient Brązowy”, „Klient Srebrny”, „Klient Złoty”). Przypisz odpowiedni globalny procent rabatu do każdej z tych grup.
  3. **Dodaj zasady:** Użyj przycisku „Dodaj nową”, aby utworzyć każdy poziom, łącząc kwotę wydatków z prawidłową grupą klientów.
  4. **Uporządkuj zasady:** Moduł przetwarza zasady od najniższych do najwyższych wydatków. Upewnij się, że Twoje zasady są logicznie uporządkowane.
  5. **Przeglądaj i dostosowuj:** Okresowo przeglądaj swoje poziomy, aby upewnić się, że są nadal skuteczne i opłacalne.

#### index.php (cudi/controllers/admin/index.php)

Ten plik jest zazwyczaj placeholderem lub przekierowaniem w ramach struktury kontrolera administracyjnego i nie reprezentuje bezpośredniego, konfigurowalnego ekranu dla sprzedawcy. Jest częścią wewnętrznego routingu modułu dla panelu administracyjnego. Cała konfiguracja rabatów kumulacyjnych dla sprzedawcy odbywa się albo na głównej stronie konfiguracji modułu, albo za pośrednictwem `AdminCudiListController`.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| **Strona konfiguracji modułu** | Aktywuj program | TAK | Główny przełącznik programu lojalnościowego. |
|  | Wyłącz program rabatów kumulacyjnych dla wybranych grup klientów | Wybierz „Gość”, „Odwiedzający” | Wyklucza określone grupy klientów z programu. |
|  | Ramy czasowe | Zamówienia z ostatniego roku / Wszystkie zamówienia | Definiuje okres dla obliczania całkowitych wydatków. |
|  | Typ ceny | Cena brutto | Określa, czy do obliczania wydatków używane są ceny netto czy brutto. |
|  | Wybierz statusy zamówień | Płatność zaakceptowana, Dostarczone | Określa, które statusy zamówień wliczają się do całkowitych wydatków. |
|  | Wyklucz zamówienia złożone z kodem kuponu | TAK | Zapobiega wliczaniu zamówień z kuponami do lojalności. |
|  | Wyklucz produkty z cenami specjalnymi | TAK | Zapobiega wliczaniu produktów z promocjami cen specjalnych. |
|  | Wyklucz produkty z rabatami ilościowymi | TAK | Zapobiega wliczaniu produktów z rabatami ilościowymi. |
|  | Domyślna grupa klientów | Twoja standardowa grupa „Klient” | Grupa przypisana, jeśli żaden poziom lojalności nie zostanie osiągnięty. |
|  | Informacje dla zalogowanych klientów (Strona produktu) | Tekst do dostosowania ze zmiennymi Smarty | Wiadomość dla zalogowanych użytkowników na stronach produktów. |
|  | Informacje dla niezalogowanych klientów (Strona produktu) | Tekst do dostosowania | Wiadomość dla gości na stronach produktów, zachęcająca do rejestracji. |
|  | Informacje dla zalogowanych klientów (Strona koszyka) | Tekst do dostosowania ze zmiennymi Smarty | Wiadomość dla zalogowanych użytkowników na stronach koszyka. |
|  | Informacje dla niezalogowanych klientów (Strona koszyka) | Tekst do dostosowania | Wiadomość dla gości na stronach koszyka, zachęcająca do rejestracji. |
| **AdminCudiListController** | Minimalna kwota wydatków | Różni się w zależności od poziomu | Próg kwalifikacji do określonej grupy rabatowej. |
|  | Grupa klientów | Twoje niestandardowe grupy lojalnościowe (np. Brązowa, Srebrna) | Grupa PrestaShop przypisana po osiągnięciu progu wydatków. |
|  | Procent rabatu | Różni się w zależności od poziomu | Rabat zastosowany do przypisanej grupy klientów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci nie są przypisywani do prawidłowych grup, lub rabaty nie są stosowane.**
O1:

- **Sprawdź „Aktywuj program”:** Upewnij się, że główny przełącznik w konfiguracji modułu jest ustawiony na TAK.
- **Zweryfikuj „Ramy czasowe” i „Wybierz statusy zamówień”:** Upewnij się, że zamówienia, które mają się liczyć, mieszczą się w wybranym przedziale czasowym i mają prawidłowe statusy zamówień (np. „Dostarczone”, „Płatność zaakceptowana”).
- **Przejrzyj ustawienia „Wyklucz”:** Sprawdź, czy „Wyklucz zamówienia złożone z kodem kuponu”, „Wyklucz produkty z cenami specjalnymi” lub „Wyklucz produkty z rabatami ilościowymi” są włączone i mogą uniemożliwiać wliczanie zamówień.
- **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe zastosowanie zmian.
- **Sprawdź grupy klientów:** Upewnij się, że grupy klientów, które połączyłeś w `AdminCudiListController`, faktycznie istnieją w PrestaShop (Klienci > Grupy) i mają przypisany prawidłowy globalny procent rabatu.
- **Kolejność zasad:** Upewnij się, że Twoje zasady w `AdminCudiListController` są logicznie uporządkowane od najniższego do najwyższego progu wydatków.

**P2: Informacje o rabacie nie pojawiają się na moich stronach produktów ani w koszyku.**
O2:

- **Sprawdź zaczepy modułu:** Upewnij się, że moduł jest podłączony do `displayProductAdditionalInfo` i `displayShoppingCart`. Możesz to sprawdzić w **Wygląd > Pozycje** (lub **Moduły > Pozycje** w starszych wersjach PS). Poszukaj „Rabaty kumulacyjne” pod tymi zaczepami. Jeśli nie, spróbuj ponownie zainstalować moduł lub ręcznie go podłączyć.
- **Tekst konfiguracji modułu:** Upewnij się, że wprowadziłeś tekst w polach „Informacje dla zalogowanych klientów” i „Informacje dla niezalogowanych klientów” zarówno dla stron produktów, jak i koszyka. Jeśli te pola są puste, nic się nie wyświetli.
- **Kompatybilność z motywem:** Twój niestandardowy motyw może nadpisywać standardowe pozycje zaczepów. Jeśli informacje nadal się nie pojawiają, możesz potrzebować programisty, aby dostosował pliki `.tpl` Twojego motywu, aby jawnie uwzględnić zaczepy modułu.

**P3: Jak przetłumaczyć wiadomości modułu na inne języki?**
O3:

- Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
- Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz „Rabaty kumulacyjne” z rozwijanej listy modułów.
- Następnie możesz przetłumaczyć wszystkie statyczne ciągi modułu. W przypadku niestandardowych wiadomości, które wprowadziłeś w konfiguracji (np. „Informacje dla zalogowanych klientów”), musisz użyć selektora języka w prawym górnym rogu strony konfiguracji modułu, aby przełączyć języki i wprowadzić przetłumaczony tekst dla każdego języka.

**P4: Czy mogę ręcznie przypisać klienta do grupy rabatów kumulacyjnych?**
O4: Tak, możesz ręcznie zmienić grupę klienta w jego profilu klienta (Panel administracyjny > Klienci > Klienci > Edytuj klienta). Jednak moduł automatycznie ponownie oceni ich grupę na podstawie historii wydatków podczas następnej aktualizacji statusu zamówienia lub gdy zostanie uruchomiona logika modułu. Jeśli chcesz, aby klient *na stałe* pozostał w określonej grupie niezależnie od wydatków, możesz wykluczyć tę grupę z programu rabatów kumulacyjnych (za pomocą ustawienia „Wyłącz program rabatów kumulacyjnych dla wybranych grup klientów”) i zarządzać nimi ręcznie.

**P5: Co się stanie, jeśli całkowite wydatki klienta spadną poniżej progu (np. z powodu zwrotu)?**
O5: Moduł przelicza całkowite wydatki klienta na podstawie skonfigurowanych „Ram czasowych” i „Wybranych statusów zamówień” za każdym razem, gdy status zamówienia jest aktualizowany. Jeśli zwrot spowoduje spadek ich sumy poniżej progu, moduł automatycznie przypisze ich do odpowiedniej grupy niższego poziomu podczas następnego przeliczenia, zapewniając dokładność.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Rabaty kumulacyjne” (`cudi`) stosuje standardową architekturę modułu PrestaShop, wykorzystując zasady MVC. Działa głównie poprzez podłączanie się do różnych zdarzeń front-office i back-office w celu obliczania wydatków klienta i dynamicznego przypisywania ich do odpowiednich grup klientów. Konfiguracja jest zarządzana za pomocą głównej metody `getContent()` i dedykowanego `AdminCudiListController` do zarządzania poziomami rabatów. Nie wprowadza niestandardowych tabel baz danych, ale opiera się na `ps_configuration` PrestaShop dla ustawień i `ps_customer_group` dla przypisań grup.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

- `cudi/controllers/front/index.php`
  - **Nazwa klasy i klasa nadrzędna:** `CudiIndexModuleFrontController` rozszerza `ModuleFrontController`.
  - **Odpowiedzialność:** Ten kontroler prawdopodobnie służy jako domyślny lub awaryjny dla routingu front-office modułu. Może obsługiwać początkową konfigurację lub przekierowanie, chociaż `mydiscount.php` jest bardziej specyficzny dla treści skierowanych do klienta.
- `cudi/controllers/front/mydiscount.php`
  - **Nazwa klasy i klasa nadrzędna:** `CudiMydiscountModuleFrontController` rozszerza `ModuleFrontController`.
  - **Odpowiedzialność:** Ten kontroler jest odpowiedzialny za renderowanie dedykowanej strony „Moje rabaty” w obszarze konta klienta. Pobiera całkowite wydatki klienta, aktualną grupę i postęp w kierunku kolejnego poziomu, a następnie przekazuje te dane do szablonu `myDiscount.tpl` w celu wyświetlenia. Odpowiada na trasę taką jak `twojskep.com/module/cudi/mydiscount`.

#### Kontrolery administracyjne Back-Office

- `cudi/controllers/admin/AdminCudiList.php`
  - **Nazwa zakładki i zarządzana encja:** „Rabaty kumulacyjne” (lub podobna, dostępna poprzez menu Katalog). Zarządza encją `cudi`, która reprezentuje zasady rabatów kumulacyjnych (progi wydatków powiązane z grupami klientów).
  - **Odpowiedzialność:** Jest to główny kontroler administracyjny do zarządzania poziomami rabatów. Rozszerza `AdminController` i używa `HelperList` do wyświetlania siatki oraz `HelperForm` do dodawania/edycji poszczególnych zasad. Obsługuje operacje CRUD dla zasad rabatów kumulacyjnych, w tym definiowanie minimalnych wydatków, docelowej grupy klientów i powiązanego rabatu.
- `cudi/controllers/admin/index.php`
  - **Odpowiedzialność:** Ten plik zazwyczaj służy jako punkt wejścia lub przekierowanie w katalogu kontrolerów administracyjnych. W wielu modułach może zawierać proste `header('Location: ...')` w celu przekierowania do głównego kontrolera administracyjnego (`AdminCudiList.php` w tym przypadku) lub być placeholderem. Nie reprezentuje bezpośredniego, konfigurowalnego ekranu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Dossier modułu nie wskazuje na niestandardowe klasy w katalogu `classes/`. Główna logika obliczania wydatków kumulacyjnych i przypisywania grup jest prawdopodobnie zawarta w samym głównym pliku modułu `cudi.php`, w szczególności w jego metodach zaczepów i potencjalnie funkcjach pomocniczych. Bezpośrednio współdziała z `ObjectModel` PrestaShop: `Customer`, `Order`, `OrderState` i `Group`.

### 4.4 Zasoby JavaScript (`views/js/`)

- `cudi/views/admin/js/cudi.js`
  - **Zakres:** Back-office.
  - **Odpowiedzialność:** Ten skrypt prawdopodobnie obsługuje interakcje po stronie klienta na stronie konfiguracji modułu lub w `AdminCudiListController`. Może to obejmować:
    - Dynamiczną widoczność pól formularza na podstawie wybranych opcji (np. pokazywanie/ukrywanie opcji wykluczeń).
    - Wywołania AJAX do zapisywania ustawień bez pełnego przeładowania strony.
    - Walidację danych wejściowych lub interaktywne elementy specyficzne dla interfejsu administracyjnego modułu.
    - Nasłuchiwanie zdarzeń zmian formularza lub kliknięć przycisków w panelu administracyjnym.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `cudi/views/admin/css/cudi.css`
  - **Zakres:** Stylizacja formularza administracyjnego back-office.
  - **Odpowiedzialność:** Zapewnia stylizację strony konfiguracji modułu i interfejsu `AdminCudiListController`, zapewniając wizualną integrację z motywem panelu administracyjnego PrestaShop.
  - **Kluczowe selektory klas CSS:** Prawdopodobnie celuje w konkretne identyfikatory lub klasy w szablonach administracyjnych modułu (np. `.cudi-settings-panel`, `.cudi-list-table`).
- `cudi/views/css/cudi.css`
  - **Zakres:** Stylizacja klienta front-office.
  - **Odpowiedzialność:** Stylizuje informacje wyświetlane klientom na stronach produktów, stronach koszyka i stronie „Moje rabaty”.
  - **Kluczowe selektory klas CSS:** Będzie celować w elementy generowane przez szablony front-office modułu (np. `.cudi-info-block`, `.cudi-discount-message`, `.cudi-progress-bar`). Programiści mogą je nadpisać w pliku `custom.css` swojego motywu lub tworząc motyw potomny.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony zaczepów (`views/templates/hook/`)

- `cudi/views/templates/hook/displayProductAdditionalInfo-unlogged.tpl`
  - **Zaczep:** `displayProductAdditionalInfo` (specjalnie dla niezalogowanych użytkowników).
  - **Wyjście:** Wyświetla dostosowywalną wiadomość dla niezalogowanych klientów na stronach produktów, zachęcającą do rejestracji i podkreślającą program lojalnościowy.
- `cudi/views/templates/hook/displayProductAdditionalInfo.tpl`
  - **Zaczep:** `displayProductAdditionalInfo` (dla zalogowanych użytkowników).
  - **Wyjście:** Wyświetla dostosowywalną wiadomość dla zalogowanych klientów na stronach produktów, pokazując ich aktualny status rabatowy i postęp w kierunku kolejnego poziomu.
- `cudi/views/templates/hook/myAccount.tpl`
  - **Zaczep:** `displayCustomerAccount`.
  - **Wyjście:** Renderuje link lub blok w sekcji „Moje konto” klienta, zazwyczaj oznaczony jako „Moje rabaty”, który prowadzi do dedykowanej strony `mydiscount`.

#### Szablony administracyjne (`views/templates/admin/`)

- `cudi/views/admin/assignButton.tpl`
  - **Zakres:** Back-office.
  - **Wyjście:** Prawdopodobnie renderuje przycisk lub link akcji w interfejsie administracyjnym, być może do wyzwalania ręcznego przeliczania lub przypisywania grup klientów.
- `cudi/views/admin/orderstates.tpl`
  - **Zakres:** Back-office.
  - **Wyjście:** Używane w głównym formularzu konfiguracji modułu (`getContent()`) do renderowania rozwijanej listy wielokrotnego wyboru lub pól wyboru dla „Wybierz statusy zamówień”.

#### Szablony front-office (`views/templates/front/`)

- `cudi/views/templates/front/myDiscount.tpl`
  - **Zakres:** Front-office.
  - **Wyjście:** Jest to dedykowany szablon strony dla `CudiMydiscountModuleFrontController`. Wyświetla kompleksowy przegląd statusu lojalnościowego klienta, w tym całkowite wydatki, aktualną grupę, procent rabatu i postęp w kierunku wyższych poziomów.

### 4.7 Schemat bazy danych i mapa zaczepów

#### Tabele bazy danych

Moduł nie tworzy niestandardowych tabel SQL. Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop, używając kluczy takich jak `CUDI_ACTIVE`, `CUDI_ORDERSDATE`, `CUDI_PRICETYPE`, `CUDI_ORDERSTATES`, `CUDI_EX_SP`, `CUDI_EX_SP_QTY`, `CUDI_ORDERCOUPON`, `CUDI_DEFGROUP`, `CUDI_GROUPSNOT`, `CUDI_SHOWINFO_PRODUCT`, `CUDI_SHOWINFO_CART`, `logged_cudi_contents`, `unlogged_cudi_contents`.
Zasady rabatów kumulacyjnych (progi wydatków i powiązane grupy klientów) są prawdopodobnie przechowywane jako serializowane dane w wpisie `ps_configuration` lub zarządzane bezpośrednio przez `AdminCudiListController`, który może używać niestandardowej tabeli (chociaż nie jest to jawnie wymienione w `classes/` ani `sql/`). *Autokorekta: Biorąc pod uwagę `AdminCudiListController` i jego zarządzanie encją `cudi`, jest bardzo prawdopodobne, że istnieje niestandardowa tabela `ps_cudi`, nawet jeśli nie jest jawnie wymieniona w `classes/` ani `sql/` w dostarczonym dossier. Tabela ta przechowywałaby `id_cudi`, `min_spend`, `id_group`, `discount_percentage` dla każdej zasady.*

#### Tabela zarejestrowanych zaczepów

| Nazwa zaczepu | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje się w sekcji `<head>` wszystkich stron front-office. | Służy do dołączania zasobów CSS/JS modułu dla front-office lub do inicjalizacji globalnych zmiennych JS. |
| `displayProductAdditionalInfo` | Na stronach produktów, zazwyczaj poniżej opisu produktu lub przycisku „dodaj do koszyka”. | Wyświetla klientom informacje o programie lojalnościowym (aktualny rabat, postęp). |
| `displayCustomerAccount` | Na stronie „Moje konto” klienta. | Dodaje link do dedykowanej strony „Moje rabaty”. |
| `displayShoppingCart` | Na stronie podsumowania koszyka. | Wyświetla klientom informacje o programie lojalnościowym (aktualny rabat, wkład koszyka). |
| `updateOrderStatus` | Wyzwalany, gdy status zamówienia zostanie zmieniony w back-office. | **Kluczowy dla ponownego obliczania całkowitych wydatków klienta i ponownego przypisywania jego grupy.** |
| `actionOrderStatusUpdate` | Podobny do `updateOrderStatus`, zapewnia bardziej szczegółową kontrolę po aktualizacji statusu zamówienia. | **Również kluczowy dla ponownego obliczania całkowitych wydatków klienta i ponownego przypisywania jego grupy.** |
| `actionAdminControllerSetMedia` | W back-office, gdy kontroler administracyjny jest ładowany. | Służy do dołączania zasobów CSS/JS modułu dla back-office (np. `cudi.js`, `cudi.css`). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zaloguj się na swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Znajdziesz tam zakupione moduły i linki do ich pobrania. Aby uzyskać pomoc techniczną, skorzystaj z kanałów wsparcia dostępnych na MyPresta.eu.
"""
