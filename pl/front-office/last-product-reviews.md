---
title: "Ostatnie recenzje produktów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Ostatnie recenzje produktów” od MyPresta.eu."
sidebar:
  label: "Ostatnie recenzje produktów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Last product reviews na MyPresta.eu](https://mypresta.eu/modules/front-office-features/last-product-reviews.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/last-product-reviews/)
>
> ---


# Ostatnie recenzje produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest główny ekran konfiguracji modułu „Ostatnie recenzje produktów”. Znajdziesz tutaj wszystkie ustawienia, aby kontrolować, jak i gdzie wyświetlane są Twoje recenzje.

#### **Wyświetl recenzje w**

- **Co robi to ustawienie:** Ta opcja określa, gdzie blok „Ostatnie recenzje produktów” pojawi się na Twojej stronie internetowej. Możesz wybrać spośród kilku standardowych pozycji hooków PrestaShop.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na „Nagłówek” (Header):* Blok recenzji pojawi się na samej górze Twojego sklepu, często powyżej lub poniżej głównej nawigacji. Oferuje to maksymalną widoczność.
  - *Gdy ustawione na „Lewa kolumna” (Left Column):* Blok recenzji pojawi się w lewym pasku bocznym Twojego sklepu, jeśli Twój szablon go posiada.
  - *Gdy ustawione na „Prawa kolumna” (Right Column):* Blok recenzji pojawi się w prawym pasku bocznym Twojego sklepu, jeśli Twój szablon go posiada.
  - *Gdy ustawione na „Strona produktu” (Product page):* Blok recenzji pojawi się na poszczególnych stronach produktów. Jest to świetne do cross-sellingu lub pokazywania ogólnego dowodu społecznego, gdy klient rozważa zakup.
  - *Gdy ustawione na „Stopka” (Footer):* Blok recenzji pojawi się na dole każdej strony, zazwyczaj powyżej informacji o prawach autorskich.
- **Zalecana wartość:** „Lewa kolumna” lub „Prawa kolumna” dla ogólnej widoczności, lub „Strona produktu”, jeśli chcesz podkreślić recenzje podczas procesu podejmowania decyzji o zakupie. „Nagłówek” może być bardzo efektowny, ale może zajmować zbyt dużo cennego miejsca, w zależności od Twojego szablonu.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz, aby klienci widzieli ostatnie recenzje bez względu na to, gdzie przeglądają, wybierz „Lewa kolumna”. Jeśli chcesz zachęcić do zakupów na stronach produktów, wybierz „Strona produktu”.

#### **Liczba recenzji do wyświetlenia**

- **Co robi to ustawienie:** Kontroluje, ile pojedynczych recenzji produktów zostanie wyświetlonych w bloku „Ostatnie recenzje produktów”.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na niską liczbę (np. 3):* Blok będzie kompaktowy, pokazując tylko kilka recenzji. Jest to dobre do oszczędzania miejsca, ale może nie przekazywać tak dużo dowodu społecznego.
  - *Gdy ustawione na wyższą liczbę (np. 10):* Blok będzie większy, wyświetlając więcej recenzji. Oferuje to więcej dowodu społecznego, ale wymaga więcej miejsca na ekranie.
- **Zalecana wartość:** 3-5 dla kolumn, 5-8 dla nagłówka/stopki, w zależności od układu Twojego szablonu i dostępnego miejsca.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja lewa kolumna jest wąska, ustaw to na 3, aby blok nie stał się zbyt długi. Jeśli masz szeroką stopkę, możesz ustawić to na 6, aby zaprezentować więcej opinii.

#### **Wyświetl imię klienta**

- **Co robi to ustawienie:** Ten przełącznik określa, czy imię klienta, który zostawił recenzję, będzie widoczne w bloku recenzji.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Każda recenzja pokaże imię klienta (np. „Recenzja od Jan K.”). Dodaje to autentyczności i personalizacji.
  - *Gdy wyłączone (NIE):* Imię klienta zostanie ukryte, a wyświetlona zostanie tylko treść recenzji i produkt. Może to być preferowane ze względu na prywatność lub bardziej minimalistyczny design.
- **Zalecana wartość:** TAK. Wyświetlanie imion klientów dodaje wiarygodności i sprawia, że recenzje wydają się bardziej autentyczne.
- **Scenariusz / przykład dla sprzedawcy:** Aby zmaksymalizować zaufanie, włącz to. Jeśli obawiasz się o prywatność klientów lub preferujesz bardzo czysty wygląd, możesz to wyłączyć.

#### **Wyświetl nazwę produktu**

- **Co robi to ustawienie:** Ten przełącznik kontroluje, czy nazwa recenzowanego produktu będzie wyświetlana obok tekstu recenzji.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Każda recenzja wyraźnie określi, którego produktu dotyczy (np. „Produkt: Super Gadżet”). Pomaga to klientom zrozumieć kontekst recenzji.
  - *Gdy wyłączone (NIE):* Wyświetlony zostanie tylko tekst recenzji i imię klienta (jeśli włączone), bez wyraźnego wspomnienia o produkcie. Sprawia to, że blok jest bardziej ogólny.
- **Zalecana wartość:** TAK. Kluczowe jest, aby klienci wiedzieli, który produkt jest recenzowany.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli klient widzi świetną recenzję, będzie chciał wiedzieć, którego produktu dotyczy. Włączenie tej opcji pozwala mu kliknąć i potencjalnie kupić ten konkretny przedmiot.

#### **Wyświetl treść recenzji**

- **Co robi to ustawienie:** Ten przełącznik określa, czy rzeczywisty tekst recenzji klienta zostanie wyświetlony w bloku.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Wyświetlony zostanie pełny lub skrócony tekst recenzji. Zapewnia to szczegółowe informacje zwrotne potencjalnym kupującym.
  - *Gdy wyłączone (NIE):* Wyświetlona zostanie tylko ocena (gwiazdki), imię klienta i nazwa produktu, bez pisemnej recenzji. Tworzy to bardzo kompaktowy blok, skupiający się tylko na ocenach gwiazdkowych.
- **Zalecana wartość:** TAK. Treść recenzji jest najcenniejszą częścią dowodu społecznego.
- **Scenariusz / przykład dla sprzedawcy:** Aby dać klientom szybki przegląd tego, co mówią inni, włącz to. Jeśli chcesz pokazać tylko oceny gwiazdkowe jako szybki sygnał zaufania, możesz to wyłączyć.

#### **Wyświetl gwiazdki recenzji**

- **Co robi to ustawienie:** Ten przełącznik kontroluje, czy ocena gwiazdkowa (np. 5 na 5 gwiazdek) związana z każdą recenzją będzie widoczna.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Ocena gwiazdkowa będzie wyraźnie wyświetlana dla każdej recenzji. Jest to szybki wizualny wskaźnik jakości produktu.
  - *Gdy wyłączone (NIE):* Ocena gwiazdkowa zostanie ukryta, a wyświetlona zostanie tylko treść tekstowa (jeśli włączona). Jest to ogólnie niezalecane, ponieważ oceny gwiazdkowe są uniwersalnym sygnałem zaufania.
- **Zalecana wartość:** TAK. Oceny gwiazdkowe są niezwykle skuteczne w szybkim przekazywaniu zadowolenia z produktu.
- **Scenariusz / przykład dla sprzedawcy:** Zawsze włączaj to, aby dać klientom natychmiastową wizualną wskazówkę dotyczącą jakości produktu i zadowolenia klienta.

#### **Wyświetl zdjęcie produktu**

- **Co robi to ustawienie:** Ten przełącznik określa, czy główne zdjęcie recenzowanego produktu zostanie wyświetlone obok jego recenzji.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Mała miniatura zdjęcia produktu pojawi się przy każdej recenzji. Sprawia to, że blok jest bardziej atrakcyjny wizualnie i pomaga klientom szybko zidentyfikować produkt.
  - *Gdy wyłączone (NIE):* Nie zostanie wyświetlone żadne zdjęcie produktu, co sprawi, że blok będzie bardziej skoncentrowany na tekście.
- **Zalecana wartość:** TAK. Zdjęcia produktów znacznie zwiększają atrakcyjność wizualną i przejrzystość bloku recenzji.
- **Scenariusz / przykład dla sprzedawcy:** Aby Twój blok recenzji był bardziej angażujący i pomagał klientom szybko kojarzyć recenzje z konkretnymi produktami, włącz zdjęcia produktów.

#### **Wyświetl cenę produktu**

- **Co robi to ustawienie:** Ten przełącznik kontroluje, czy aktualna cena recenzowanego produktu zostanie wyświetlona w bloku recenzji.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Cena produktu zostanie wyświetlona. Może to być przydatne dla klientów, którzy są wrażliwi na cenę lub chcą szybko sprawdzić, czy recenzowany produkt mieści się w ich budżecie.
  - *Gdy wyłączone (NIE):* Cena nie zostanie wyświetlona, utrzymując skupienie wyłącznie na recenzji i szczegółach produktu.
- **Zalecana wartość:** NIE, chyba że wyraźnie chcesz podkreślić ceny produktów w bloku recenzji. Czasami może to zaśmiecać wyświetlacz.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli prowadzisz wyprzedaż i chcesz wyróżnić recenzowane produkty, które są obecnie przecenione, możesz to włączyć. W przeciwnym razie często lepiej jest skupić się na samej recenzji.

#### **Wyświetl link do produktu**

- **Co robi to ustawienie:** Ten przełącznik określa, czy nazwa produktu (lub obraz, jeśli włączony) w bloku recenzji będzie klikalnym linkiem, który przeniesie klienta bezpośrednio na stronę produktu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Klienci mogą kliknąć nazwę/obraz produktu, aby przejść do pełnej strony produktu, gdzie mogą dowiedzieć się więcej i potencjalnie dokonać zakupu. Jest to kluczowe dla kierowania ruchu na strony produktów.
  - *Gdy wyłączone (NIE):* Nazwa/obraz produktu będzie statycznym tekstem/obrazem, a klienci nie będą mogli kliknąć. Zmniejsza to zdolność modułu do napędzania konwersji.
- **Zalecana wartość:** TAK. Zawsze włączaj to, aby umożliwić klientom łatwe przeglądanie recenzowanych produktów.
- **Scenariusz / przykład dla sprzedawcy:** Klient widzi świetną recenzję „Głośnika Bluetooth”. Jeśli nazwa produktu jest klikalna, może natychmiast przejść na stronę głośnika, aby go kupić.

#### **Wyświetl datę recenzji**

- **Co robi to ustawienie:** Ten przełącznik kontroluje, czy data przesłania recenzji zostanie wyświetlona.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Data (np. „Zrecenzowano 2023-10-26”) zostanie wyświetlona. Dodaje to przejrzystości i zapewnia klientów, że recenzje są aktualne i istotne.
  - *Gdy wyłączone (NIE):* Data zostanie ukryta.
- **Zalecana wartość:** TAK. Ostatnie recenzje są bardziej wpływowe i godne zaufania.
- **Scenariusz / przykład dla sprzedawcy:** Pokazywanie daty pomaga klientom zobaczyć, że Twój sklep jest aktywny i stale otrzymuje nowe opinie, budując zaufanie.

#### **Wyświetl tytuł recenzji**

- **Co robi to ustawienie:** Ten przełącznik określa, czy tytuł recenzji (jeśli klienci go podają) zostanie wyświetlony.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Jeśli recenzja ma tytuł (np. „Niesamowity produkt!”), zostanie on wyświetlony, często pogrubioną czcionką, zapewniając szybkie podsumowanie sentymentu recenzji.
  - *Gdy wyłączone (NIE):* Wyświetlona zostanie tylko główna treść recenzji, bez osobnego tytułu.
- **Zalecana wartość:** TAK. Tytuły recenzji są doskonałe do szybkiego przyciągania uwagi i podsumowywania istoty recenzji.
- **Scenariusz / przykład dla sprzedawcy:** Klient szybko skanujący recenzje może zrozumieć ich sens z tytułów takich jak „Świetna wartość” lub „Rozczarowany” przed przeczytaniem pełnego tekstu.

#### **Minimalna ocena do wyświetlenia**

- **Co robi to ustawienie:** Ten filtr pozwala ustawić minimalną ocenę gwiazdkową dla recenzji, które mają być uwzględnione w bloku „Ostatnie recenzje produktów”.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na 1 gwiazdkę:* Wyświetlone zostaną wszystkie recenzje (1-5 gwiazdek).
  - *Gdy ustawione na 3 gwiazdki:* Wyświetlone zostaną tylko recenzje z 3, 4 lub 5 gwiazdkami. Recenzje z 1 lub 2 gwiazdkami zostaną wykluczone.
  - *Gdy ustawione na 5 gwiazdek:* Wyświetlone zostaną tylko idealne recenzje z 5 gwiazdkami.
- **Zalecana wartość:** 3 lub 4 gwiazdki. Chociaż przejrzystość jest dobra, możesz chcieć wyróżnić głównie pozytywne opinie w tym widocznym bloku.
- **Scenariusz / przykład dla sprzedawcy:** Aby upewnić się, że Twój blok „Ostatnie recenzje produktów” zawsze prezentuje pozytywne opinie, ustaw to na 4 gwiazdki. Pomaga to utrzymać pozytywny wizerunek, jednocześnie będąc autentycznym.

#### **Wyświetlaj tylko recenzje z wybranej kategorii**

- **Co robi to ustawienie:** Ta opcja pozwala filtrować wyświetlane recenzje, aby pokazywać tylko te, które są związane z produktami z określonej kategorii.
- **Efekt zmiany tego ustawienia:**
  - *Gdy wybrano „Nie”:* Recenzje ze wszystkich kategorii będą brane pod uwagę do wyświetlenia.
  - *Gdy wybrano konkretną kategorię (np. „Elektronika”):* Wyświetlone zostaną tylko recenzje produktów z kategorii „Elektronika” (i jej podkategorii).
- **Zalecana wartość:** „Nie” dla ogólnego dowodu społecznego. Wybierz kategorię, jeśli blok recenzji jest umieszczony w kontekście, gdzie istotne są tylko określone typy produktów (np. na stronie kategorii).
- **Scenariusz / przykład dla sprzedawcy:** Jeśli umieścisz blok recenzji na stronie kategorii „Koszulki”, możesz wybrać tutaj kategorię „Koszulki”, aby upewnić się, że wyświetlane są tylko odpowiednie recenzje, co poprawia doświadczenie klienta.

#### **Wyświetlaj tylko recenzje z wybranego produktu**

- **Co robi to ustawienie:** Ta opcja pozwala filtrować wyświetlane recenzje, aby pokazywać tylko te, które są związane z konkretnym produktem.
- **Efekt zmiany tego ustawienia:**
  - *Gdy wybrano „Nie”:* Recenzje dla wszystkich produktów będą brane pod uwagę do wyświetlenia.
  - *Gdy wybrano konkretny produkt (np. „Mój Niesamowity Gadżet”):* Wyświetlone zostaną tylko recenzje dla „Mojego Niesamowitego Gadżetu”.
- **Zalecana wartość:** „Nie” dla ogólnego dowodu społecznego. Wybierz produkt, jeśli blok recenzji jest umieszczony w kontekście, gdzie istotne są tylko recenzje jednego produktu (np. na niestandardowej stronie docelowej dla tego produktu).
- **Scenariusz / przykład dla sprzedawcy:** Jeśli masz specjalną stronę promocyjną dla swojego „Najlepiej sprzedającego się ekspresu do kawy”, możesz skonfigurować ten blok tak, aby wyświetlał tylko recenzje dla tego konkretnego ekspresu do kawy na tej stronie.

#### **Wyświetl recenzje jako suwak**

- **Co robi to ustawienie:** Ten przełącznik włącza lub wyłącza dynamiczny suwak (karuzelę) dla bloku recenzji.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Recenzje będą automatycznie przewijać się lub pozwalać klientom na nawigację za pomocą strzałek/kropek. Jest to świetne do wyświetlania wielu recenzji w kompaktowej przestrzeni.
  - *Gdy wyłączone (NIE):* Recenzje będą wyświetlane jako statyczna lista, jedna po drugiej.
- **Zalecana wartość:** TAK, zwłaszcza jeśli wyświetlasz więcej niż 3-4 recenzje lub jeśli blok znajduje się w wąskiej kolumnie.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz wyświetlić 8 recenzji w lewej kolumnie, ale nie chcesz, aby kolumna stała się zbyt długa, włączenie suwaka sprawi, że będzie on kompaktowy i interaktywny.

#### **Automatyczne odtwarzanie suwaka**

- **Co robi to ustawienie:** Jeśli włączono „Wyświetl recenzje jako suwak”, to ustawienie kontroluje, czy suwak automatycznie przechodzi do następnej recenzji bez interakcji użytkownika.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Suwak będzie automatycznie przechodził między recenzjami po ustalonym opóźnieniu.
  - *Gdy wyłączone (NIE):* Suwak będzie poruszał się tylko wtedy, gdy klient kliknie strzałki nawigacyjne lub kropki.
- **Zalecana wartość:** TAK, ale upewnij się, że „Prędkość automatycznego odtwarzania suwaka” jest ustawiona na rozsądny czas trwania.
- **Scenariusz / przykład dla sprzedawcy:** Aby blok recenzji był dynamiczny i zapewniał widoczność wszystkim recenzjom, włącz automatyczne odtwarzanie.

#### **Prędkość automatycznego odtwarzania suwaka (w ms)**

- **Co robi to ustawienie:** Jeśli włączono „Automatyczne odtwarzanie suwaka”, to ustawienie określa, jak długo (w milisekundach) każda recenzja jest wyświetlana, zanim suwak automatycznie przejdzie do następnej.
- **Efekt zmiany tego ustawienia:**
  - *Niższa liczba (np. 2000ms = 2 sekundy):* Recenzje będą zmieniać się szybko.
  - *Wyższa liczba (np. 5000ms = 5 sekund):* Recenzje pozostaną widoczne dłużej, dając klientom więcej czasu na przeczytanie.
- **Zalecana wartość:** 4000-6000 (4-6 sekund), aby dać klientom wystarczająco dużo czasu na przeczytanie recenzji bez poczucia pośpiechu.
- **Scenariusz / przykład dla sprzedawcy:** Ustaw to na 5000ms, aby klienci mieli wystarczająco dużo czasu na przeczytanie każdej recenzji, gdy się przewija.

#### **Sterowanie suwakiem**

- **Co robi to ustawienie:** Jeśli włączono „Wyświetl recenzje jako suwak”, to kontroluje, czy strzałki nawigacyjne (lewo/prawo) są widoczne dla klientów, aby ręcznie przeglądać recenzje.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Strzałki pojawią się na suwaku, umożliwiając ręczną nawigację.
  - *Gdy wyłączone (NIE):* Nie zostaną wyświetlone żadne strzałki. Klienci mogą polegać tylko na automatycznym odtwarzaniu (jeśli włączone) lub gestach dotykowych/przesuwania.
- **Zalecana wartość:** TAK. Zapewnienie kontroli poprawia doświadczenie użytkownika, nawet przy automatycznym odtwarzaniu.
- **Scenariusz / przykład dla sprzedawcy:** Aby dać klientom pełną kontrolę nad przeglądaniem recenzji, włącz sterowanie suwakiem.

#### **Paginacja suwaka**

- **Co robi to ustawienie:** Jeśli włączono „Wyświetl recenzje jako suwak”, to kontroluje, czy małe kropki (paginacja) są widoczne, wskazując całkowitą liczbę recenzji i aktualnie wyświetlaną recenzję.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Pojawią się kropki, pokazując postęp i umożliwiając bezpośrednie przejście do konkretnych recenzji.
  - *Gdy wyłączone (NIE):* Nie zostaną wyświetlone żadne kropki.
- **Zalecana wartość:** TAK. Paginacja zapewnia wyraźną wizualną wskazówkę, ile recenzji jest dostępnych i gdzie klient znajduje się w sekwencji.
- **Scenariusz / przykład dla sprzedawcy:** Aby pomóc klientom zrozumieć, ile recenzji znajduje się w suwaku i łatwo przejść do konkretnej, włącz paginację suwaka.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyświetl recenzje w | Lewa kolumna / Prawa kolumna | Kontroluje pozycję bloku recenzji w Twoim sklepie. |
| Konfiguracja modułu | Liczba recenzji do wyświetlenia | 3-5 (kolumny), 5-8 (nagłówek/stopka) | Określa, ile recenzji jest widocznych w bloku. |
| Konfiguracja modułu | Wyświetl imię klienta | TAK | Pokazuje imię recenzenta dla autentyczności. |
| Konfiguracja modułu | Wyświetl nazwę produktu | TAK | Wyraźnie łączy recenzję z produktem. |
| Konfiguracja modułu | Wyświetl treść recenzji | TAK | Pokazuje rzeczywisty tekst recenzji. |
| Konfiguracja modułu | Wyświetl gwiazdki recenzji | TAK | Wizualny wskaźnik oceny produktu. |
| Konfiguracja modułu | Wyświetl zdjęcie produktu | TAK | Sprawia, że blok jest bardziej atrakcyjny wizualnie i łatwiejszy do zidentyfikowania. |
| Konfiguracja modułu | Wyświetl cenę produktu | NIE | Pokazuje cenę produktu (może zaśmiecać, zazwyczaj niepotrzebne). |
| Konfiguracja modułu | Wyświetl link do produktu | TAK | Pozwala klientom kliknąć, aby przejść na stronę produktu. |
| Konfiguracja modułu | Wyświetl datę recenzji | TAK | Pokazuje, kiedy recenzja została przesłana, dowodząc aktualności. |
| Konfiguracja modułu | Wyświetl tytuł recenzji | TAK | Wyświetla tytuł recenzji dla szybkich podsumowań. |
| Konfiguracja modułu | Minimalna ocena do wyświetlenia | 3 lub 4 gwiazdki | Filtruje recenzje z niższą oceną, aby wyświetlać pozytywne. |
| Konfiguracja modułu | Wyświetlaj tylko recenzje z wybranej kategorii | Nie | Filtruje recenzje według kategorii produktu. |
| Konfiguracja modułu | Wyświetlaj tylko recenzje z wybranego produktu | Nie | Filtruje recenzje według konkretnego produktu. |
| Konfiguracja modułu | Wyświetl recenzje jako suwak | TAK | Prezentuje recenzje w dynamicznej, przewijanej karuzeli. |
| Konfiguracja modułu | Automatyczne odtwarzanie suwaka | TAK | Automatycznie przewija suwak. |
| Konfiguracja modułu | Prędkość automatycznego odtwarzania suwaka (w ms) | 4000-6000 | Ustawia czas wyświetlania każdej recenzji w suwaku. |
| Konfiguracja modułu | Sterowanie suwakiem | TAK | Pokazuje strzałki nawigacyjne do ręcznego sterowania suwakiem. |
| Konfiguracja modułu | Paginacja suwaka | TAK | Pokazuje kropki do paginacji suwaka. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem moduł, ale blok recenzji nie wyświetla się w moim sklepie.**
O:

1. **Sprawdź pozycję modułu:** Przejdź do **Wygląd > Pozycje** (lub **Moduły > Pozycje** w starszych wersjach PrestaShop) w swoim Panelu administracyjnym. Wyszukaj `displayLastReviews` (lub hook, który wybrałeś w konfiguracji modułu). Upewnij się, że moduł „Ostatnie recenzje produktów” jest tam wymieniony i włączony dla tego hooka. Jeśli nie, kliknij „Przeszczep moduł” i dodaj go do żądanego hooka.
2. **Wyczyść pamięć podręczną:** PrestaShop często buforuje zawartość. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub przyciski „Wyczyść pamięć podręczną Smarty” i „Wyczyść pamięć podręczną”).
3. **Sprawdź recenzje:** Upewnij się, że faktycznie masz zatwierdzone recenzje produktów w swoim sklepie. Moduł może wyświetlać tylko istniejące i widoczne recenzje.
4. **Kompatybilność z szablonem:** Chociaż moduł jest zaprojektowany tak, aby był kompatybilny, niektóre wysoce spersonalizowane szablony mogą wymagać drobnych korekt CSS. Sprawdź konsolę programisty swojej przeglądarki pod kątem błędów JavaScript.

**P: Recenzje są wyświetlane, ale nie wyglądają prawidłowo (np. złe style, zbyt duże obrazy).**
O:

1. **Konflikty szablonu:** CSS Twojego szablonu może nadpisywać style modułu. Możesz spróbować dodać niestandardowy CSS do pliku `custom.css` Twojego szablonu (jeśli taki posiada) lub bezpośrednio edytować `lastreviews/views/css/lastreviews.css` (chociaż nie jest to bezpieczne podczas aktualizacji).
2. **Rozmiary obrazów:** Jeśli obrazy produktów są zbyt duże, sprawdź ustawienia obrazów w swoim szablonie lub CSS modułu. Moduł używa standardowego rozmiaru obrazu, ale Twój szablon może renderować go inaczej.
3. **Problemy z suwakiem:** Jeśli suwak nie działa, upewnij się, że włączono „Wyświetl recenzje jako suwak”. Sprawdź konsolę przeglądarki pod kątem błędów JavaScript, ponieważ inne moduły lub skrypty szablonu mogą powodować konflikty.

**P: Czy mogę wyświetlać recenzje tylko z konkretnego produktu lub kategorii?**
O: Tak! W konfiguracji modułu masz opcje „Wyświetlaj tylko recenzje z wybranej kategorii” i „Wyświetlaj tylko recenzje z wybranego produktu”. Użyj tych rozwijanych list, aby filtrować recenzje wyświetlane w bloku.

**P: Moje recenzje są w wielu językach. Czy moduł wyświetli je poprawnie?**
O: Moduł opiera się na standardowym systemie recenzji PrestaShop. Jeśli Twoje recenzje są poprawnie powiązane z językami w PrestaShop, moduł powinien wyświetlać recenzje w aktywnym języku front-office. Upewnij się, że Twój szablon i PrestaShop są poprawnie skonfigurowane dla treści wielojęzycznych.

**P: Jak uzyskać więcej recenzji do wyświetlenia?**
O: Ten moduł tylko *wyświetla* istniejące recenzje. Aby uzyskać więcej recenzji, musisz zachęcić klientów do ich pozostawiania. Rozważ użycie oddzielnego modułu do przypominania o recenzjach, oferowanie zachęt lub maksymalne ułatwienie procesu przesyłania recenzji na stronach produktów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Ostatnie recenzje produktów” to standardowy moduł PrestaShop, zgodny z wzorcem MVC. Działa głównie jako funkcja front-office, włączając się w różne punkty wyświetlania, aby renderować blok ostatnich recenzji produktów. Wykorzystuje podstawową funkcjonalność PrestaShop `ProductComment` (lub podobną) do pobierania danych recenzji. Główna logika modułu znajduje się w `index.php`, obsługując konfigurację i rejestrację hooków, podczas gdy szablony i zasoby zarządzają wyświetlaniem front-end. Wykorzystuje zewnętrzną bibliotekę JavaScript, `lightslider.js`, do funkcji karuzeli.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównej klasy modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani `ObjectModel` w katalogu `classes/`. Opiera się na podstawowym `ProductComment` PrestaShop (lub odpowiedniku, w zależności od wersji PrestaShop i tego, czy zainstalowany jest oficjalny moduł Komentarze do produktów) do pobierania danych recenzji.

### 4.4 Zasoby JavaScript (`views/js/`)

- **`lastreviews/lib/src/js/lightslider.js`**
  - **Zakres:** Front-office.
  - **Cel:** Jest to podstawowa biblioteka JavaScript do tworzenia responsywnych suwaków/karuzel treści. Zapewnia funkcjonalność dla funkcji „Wyświetl recenzje jako suwak”.
  - **Funkcjonalność:** Wiąże się z elementem `<ul>` (lub podobnym kontenerem), aby przekształcić go w responsywny suwak. Obsługuje automatyczne odtwarzanie, sterowanie nawigacją (strzałki), paginację (kropki), gesty dotykowe/przesuwania i responsywne skalowanie.
  - **Zależności:** Zazwyczaj wymaga jQuery.

### 4.5 Arkusze stylów CSS (`views/css/`)

- **`lastreviews/lib/src/css/lightslider.css`**

  - **Zakres:** Stylizacja klienta front-office.
  - **Cel:** Zapewnia domyślną stylizację dla biblioteki `lightslider.js`, w tym podstawowy układ, strzałki nawigacyjne, kropki paginacji i style animacji dla suwaka.
  - **Kluczowe selektory:** `.lightSlider`, `.lSAction > .lSPrev`, `.lSAction > .lSNext`, `.lSPager` itp. Programiści mogą je nadpisać, aby dopasować je do estetyki swojego szablonu.
- **`lastreviews/views/css/lastreviews.css`**

  - **Zakres:** Stylizacja klienta front-office.
  - **Cel:** Zawiera niestandardową stylizację specyficzną dla bloku wyświetlania modułu „Ostatnie recenzje produktów”. Obejmuje to stylizację dla kontenera recenzji, poszczególnych elementów recenzji, zdjęć produktów, ocen gwiazdkowych i elementów tekstowych.
  - **Kluczowe selektory:** `.last-reviews-block`, `.last-review-item`, `.review-product-image`, `.review-stars`, `.review-customer-name`, `.review-product-name` itp. Te selektory są zaprojektowane tak, aby można je było łatwo nadpisać przez CSS niestandardowego szablonu w celu integracji.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:
  - **`lastreviews/views/templates/hook/admin-tips.tpl`**
    - **Cel:** Ten szablon jest prawdopodobnie używany na stronie konfiguracji Panelu administracyjnego (`getContent()`) do wyświetlania wskazówek administracyjnych lub instrukcji dla sprzedawcy. Nie jest renderowany we front office.
    - **Treść:** Zazwyczaj zawiera kod HTML dla komunikatów informacyjnych, linków do dokumentacji lub ostrzeżeń.
  - **`lastreviews/views/templates/hook/last-reviews.tpl`**
    - **Cel:** Jest to główny szablon front-office odpowiedzialny za renderowanie bloku „Ostatnie recenzje produktów”. Jest on podłączony do różnych punktów wyświetlania (np. `displayLeftColumn`, `displayFooter`).
    - **Dane:** Otrzymuje tablicę danych recenzji (imię klienta, nazwa produktu, ocena, treść, data, obraz, link) z logiki PHP modułu.
    - **Struktura:** Iteruje przez dostarczone recenzje, warunkowo wyświetlając elementy na podstawie konfiguracji modułu (np. imię klienta, zdjęcie produktu, suwak). Zawiera niezbędną strukturę HTML do inicjalizacji `lightslider.js`, jeśli opcja suwaka jest włączona.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Ten moduł nie tworzy własnych niestandardowych tabel bazy danych. Opiera się na podstawowych tabelach PrestaShop dla recenzji produktów, zazwyczaj `ps_product_comment` i powiązanych tabelach (jeśli oficjalny moduł Komentarze do produktów jest zainstalowany i aktywny).
  - Ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration`, z kluczami zazwyczaj poprzedzonymi `LASTREVIEWS_` (np. `LASTREVIEWS_DISPLAY_IN`, `LASTREVIEWS_NUM_REVIEWS`).
- **Tabela zarejestrowanych hooków**:

  | Nazwa hooka | Czas wykonania | Cel techniczny |
  | --- | --- | --- |
  | `displayHeader` | W sekcji `<head>` wszystkich stron front-office. | Służy do dołączania zasobów CSS/JS i potencjalnie renderowania bloku recenzji na górze strony. |
  | `displayLeftColumn` | W lewym pasku bocznym stron front-office. | Renderuje blok recenzji w lewej kolumnie. |
  | `displayRightColumn` | W prawym pasku bocznym stron front-office. | Renderuje blok recenzji w prawej kolumnie. |
  | `displayFooter` | W sekcji stopki wszystkich stron front-office. | Renderuje blok recenzji w stopce. |
  | `displayProductAdditionalInfo` (lub podobny hook strony produktu) | Na stronie produktu, zazwyczaj poniżej głównych informacji o produkcie. | Renderuje blok recenzji na poszczególnych stronach produktów. |
  | `actionFrontControllerSetMedia` | Wykonywane, gdy kontroler front-end ustawia swoje media (CSS/JS). | Służy do rejestrowania plików CSS i JavaScript modułu (`lightslider.js`, `lastreviews.css`), które mają być ładowane we front office. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Ostatnie recenzje produktów”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
