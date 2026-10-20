---
title: "Voucher za komentarz do produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Voucher za komentarz do produktu” od MyPresta.eu."
sidebar:
  label: "Voucher za komentarz do produktu - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Voucher for product comment na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-for-product-comment.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/voucher-for-product-comment/)
>
> ---


# Voucher za komentarz do produktu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do prawidłowego działania PrestaShop. Dla tego modułu nie są potrzebne żadne dodatkowe rozszerzenia.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny obszar konfiguracji modułu „Voucher za komentarz do produktu”. Znajdziesz tu wszystkie ustawienia dotyczące przypomnień o komentarzach i generowania kuponów.

#### **Ustawienia przypomnień o komentarzach**

- **Poproś o zgodę na wysyłanie przypomnień**

  - **Co robi to ustawienie:** Jeśli włączone, na formularzach rejestracji klienta i aktualizacji tożsamości (Moje konto > Informacje) pojawi się pole wyboru z pytaniem, czy klienci zgadzają się na otrzymywanie przypomnień o komentarzach. Jest to ważne dla zgodności z RODO i poszanowania prywatności klientów.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone:* Klienci muszą wyraźnie wyrazić zgodę na otrzymywanie przypomnień. Tylko klienci, którzy zaznaczą to pole, otrzymają e-maile z przypomnieniami.
    - *Gdy wyłączone:* Wszyscy klienci, którzy spełniają inne kryteria (np. zakupili produkty, nie skomentowali), otrzymają przypomnienia, bez wyraźnej zgody.
  - **Zalecana wartość:** TAK (Wysoce zalecane dla zgodności z RODO i lepszych relacji z klientami).
  - **Scenariusz/przykład dla sprzedawcy:** Chcesz upewnić się, że Twoje praktyki marketingowe są zgodne z przepisami o ochronie danych. Włączenie tej opcji daje klientom kontrolę nad ich preferencjami komunikacyjnymi.
- **Wyślij przypomnienie o komentarzu**

  - **Co robi to ustawienie:** Jest to główny przełącznik funkcji przypomnień o komentarzach. Jeśli wyłączone, żadne e-maile z przypomnieniami o komentarzach nie zostaną wysłane, niezależnie od innych ustawień.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone:* Moduł będzie aktywnie wysyłać e-maile z przypomnieniami na podstawie innych ustawień.
    - *Gdy wyłączone:* Żadne e-maile z przypomnieniami nie zostaną wysłane.
  - **Zalecana wartość:** TAK
  - **Scenariusz/przykład dla sprzedawcy:** Zdecydowałeś się aktywnie zbierać więcej recenzji i chcesz zacząć wysyłać przypomnienia.
- **Przypomnij o komentarzach po:**

  - **Co robi to ustawienie:** Definiuje liczbę dni po osiągnięciu przez zamówienie określonego statusu (zdefiniowanego poniżej), po których zostanie wysłany pierwszy e-mail z przypomnieniem o komentarzu.
  - **Wpływ zmiany tego ustawienia:**
    - *Zmiana liczby:* Określa opóźnienie. Krótsze opóźnienie oznacza, że klienci otrzymują przypomnienia szybciej; dłuższe opóźnienie daje im więcej czasu przed otrzymaniem monitu.
  - **Zalecana wartość:** 7 dni (Daje klientom wystarczająco dużo czasu na otrzymanie i użycie produktu).
  - **Scenariusz/przykład dla sprzedawcy:** Chcesz dać klientom tydzień na otrzymanie produktu i wyrobienie sobie opinii, zanim poprosisz o recenzję.
- **Powtórz przypomnienie**

  - **Co robi to ustawienie:** Jeśli klient nadal nie zostawił komentarza po początkowym przypomnieniu, to ustawienie określa, czy i kiedy należy wysłać drugie przypomnienie.
  - **Wpływ zmiany tego ustawienia:**
    - *Ustawienie liczby (np. 14):* Drugie przypomnienie zostanie wysłane 14 dni po *pierwszym* przypomnieniu, jeśli nie został pozostawiony żaden komentarz.
    - *Ustawienie na 0 lub pozostawienie pustego:* Drugie przypomnienie nie zostanie wysłane.
  - **Zalecana wartość:** 14 (Zapewnia delikatne przypomnienie bez bycia zbyt agresywnym).
  - **Scenariusz/przykład dla sprzedawcy:** Niektórzy klienci mogą przegapić pierwszy e-mail lub po prostu zapomnieć. Drugie przypomnienie po dwóch tygodniach może ponownie przyciągnąć ich uwagę.
- **Tytuł e-maila**

  - **Co robi to ustawienie:** Pozwala dostosować temat e-maili z przypomnieniami o komentarzach. Jest to kluczowe dla wskaźników otwarć e-maili.
  - **Wpływ zmiany tego ustawienia:**
    - *Zmiana tekstu:* Bezpośrednio zmienia temat, który klienci widzą w swojej skrzynce odbiorczej.
  - **Zalecana wartość:** „Chcielibyśmy poznać Twoje zdanie na temat ostatniego zakupu!” lub „Podziel się swoim doświadczeniem i pomóż innym kupującym!”
  - **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby temat e-maila był angażujący i jasny, zachęcając klientów do jego otwarcia.
- **Wybierz statusy zamówień**

  - **Co robi to ustawienie:** Określa, które statusy zamówień wyzwalają proces przypomnień o komentarzach. Przypomnienia będą wysyłane tylko dla produktów z zamówień, które osiągnęły jeden z wybranych statusów.
  - **Wpływ zmiany tego ustawienia:**
    - *Wybór statusów (np. „Dostarczone”):* Przypomnienia będą wysyłane tylko dla zamówień oznaczonych jako dostarczone.
    - *Brak wyboru odpowiedniego statusu:* Przypomnienia mogą nie być wysyłane w odpowiednim czasie (np. jeśli wybierzesz tylko „Płatność zaakceptowana”, ale produkty jeszcze nie zostały wysłane).
  - **Zalecana wartość:** „Dostarczone” (Zapewnia to, że klienci otrzymali swoje produkty, zanim zostaną poproszeni o ich recenzję).
  - **Scenariusz/przykład dla sprzedawcy:** Chcesz prosić o recenzje dopiero po tym, jak klient faktycznie otrzymał swoje zamówienie, więc wybierasz „Dostarczone” i „Wysłane”.
- **Grupa klientów (dla przypomnień)**

  - **Co robi to ustawienie:** Pozwala na kierowanie przypomnień o komentarzach do określonych grup klientów. Tylko klienci należący do wybranych grup otrzymają przypomnienia.
  - **Wpływ zmiany tego ustawienia:**
    - *Wybór grup (np. „Klienci”):* Tylko klienci z grupy „Klienci” otrzymają przypomnienia.
    - *Brak wyboru żadnej grupy:* Przypomnienia zostaną wysłane do wszystkich klientów (chyba że zastosowano inne filtry).
  - **Zalecana wartość:** „Klienci” (Zazwyczaj chcesz przypominać wszystkim swoim stałym klientom).
  - **Scenariusz/przykład dla sprzedawcy:** Masz specjalną grupę klientów „VIP” i chcesz wysyłać im spersonalizowane przypomnienia, lub chcesz wykluczyć klientów hurtowych z przypomnień.
- **Wysyłaj przypomnienia o komentarzach do produktów z zamówień:**

  - **Co robi to ustawienie:** Jest to filtr daty. Przypomnienia będą wysyłane tylko dla produktów zakupionych w zamówieniach złożonych *po* tej określonej dacie.
  - **Wpływ zmiany tego ustawienia:**
    - *Ustawienie daty:* Zapobiega wysyłaniu przypomnień dla bardzo starych zamówień, koncentrując się na ostatnich zakupach.
    - *Pozostawienie pustego:* Przypomnienia mogą potencjalnie być wysyłane dla wszystkich poprzednich zamówień, co może nie być pożądane.
  - **Zalecana wartość:** Ustaw na niedawną datę lub datę instalacji modułu, aby uniknąć spamowania starych klientów.
  - **Scenariusz/przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i nie chcesz wysyłać przypomnień o zamówieniach sprzed roku; interesują Cię tylko zamówienia z ostatnich 3 miesięcy.
- **Rozmiar obrazu dla zdjęć produktów**

  - **Co robi to ustawienie:** Określa rozmiar zdjęć produktów zawartych w e-mailach z przypomnieniami.
  - **Wpływ zmiany tego ustawienia:**
    - *Wybór rozmiaru (np. „home\_default”):* Zdjęcia produktów w e-mailu zostaną wyrenderowane w tym konkretnym rozmiarze, wpływając na układ e-maila i czas ładowania.
  - **Zalecana wartość:** „home\_default” lub „small\_default” (Obraz średniej wielkości, który dobrze wygląda, nie czyniąc e-maila zbyt ciężkim).
  - **Scenariusz/przykład dla sprzedawcy:** Chcesz, aby zdjęcia produktów w e-mailach z przypomnieniami były wyraźne, ale nie nadmiernie duże, więc wybierasz odpowiedni rozmiar obrazu zdefiniowany w Twoim szablonie.

#### **Ustawienia generowania kuponów**

- **Wyślij kod kuponu za komentarz**

  - **Co robi to ustawienie:** Jest to główny przełącznik funkcji generowania kuponów. Jeśli wyłączone, żadne kupony nie zostaną wygenerowane ani wysłane, nawet jeśli komentarze zostaną pozostawione.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone:* Moduł wygeneruje i wyśle unikalny kod kuponu klientom, którzy zostawią komentarz do produktu.
    - *Gdy wyłączone:* Żadne kupony nie zostaną wysłane.
  - **Zalecana wartość:** TAK (Jest to kluczowa funkcja do zachęcania do komentarzy).
  - **Scenariusz/przykład dla sprzedawcy:** Chcesz nagrodzić klientów za ich wysiłek w pozostawieniu recenzji, zachęcając ich do ponownych zakupów.
- **Wyślij kupon tylko dla klientów, którzy zakupili produkt**

  - **Co robi to ustawienie:** Jeśli włączone, kupon zostanie wysłany *tylko* wtedy, gdy klient, który zostawił komentarz, również zakupił produkt. Zapobiega to otrzymywaniu kuponów przez osoby, które nie kupiły w Twoim sklepie, tylko poprzez pozostawianie komentarzy.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone:* Kupony są ograniczone do zweryfikowanych nabywców.
    - *Gdy wyłączone:* Każdy, kto zostawi komentarz (np. gość lub ktoś, kto nie kupił produktu), może otrzymać kupon.
  - **Zalecana wartość:** TAK (Wysoce zalecane, aby upewnić się, że kupony są przyznawane faktycznym klientom i zapobiegać nadużyciom).
  - **Scenariusz/przykład dla sprzedawcy:** Chcesz nagrodzić lojalnych klientów, którzy już dokonali zakupu, a nie tylko każdego, kto zostawi komentarz.
- **Kiedy wygenerować kupon?**

  - **Co robi to ustawienie:** Określa, kiedy kupon jest generowany i wysyłany do klienta.
  - **Wpływ zmiany tego ustawienia:**
    - *Opcja 1 (np. „Po dodaniu komentarza”):* Kupon jest wysyłany natychmiast po przesłaniu komentarza przez klienta.
    - *Opcja 2 (np. „Po zatwierdzeniu komentarza”):* Kupon jest wysyłany dopiero po ręcznym zatwierdzeniu komentarza przez administratora w Panelu administracyjnym.
  - **Zalecana wartość:** „Po zatwierdzeniu komentarza” (Zapobiega przyznawaniu kuponów za spam lub nieodpowiednie komentarze).
  - **Scenariusz/przykład dla sprzedawcy:** Moderujesz wszystkie komentarze do produktów, aby utrzymać jakość. Chcesz mieć pewność, że tylko zatwierdzone, wartościowe komentarze otrzymają kupon.
- **Generuj kupony za komentarze:**

  - **Co robi to ustawienie:** Ta sekcja pozwala zdefiniować właściwości kuponu, który zostanie wygenerowany. Obejmuje to typ rabatu (procentowy, kwotowy), wartość, minimalny zakup, ważność i inne.
  - **Wpływ zmiany tego ustawienia:**
    - *Każde pole tutaj (np. „Typ rabatu”, „Wartość”, „Minimalna kwota”):* Bezpośrednio konfiguruje zasady i korzyści generowanego kuponu rabatowego.
    - *Pozostawienie pól pustych lub nieprawidłowo skonfigurowanych:* Może prowadzić do nieprawidłowych kuponów lub kuponów, które nie spełniają Twoich celów marketingowych.
  - **Zalecana wartość:**
    - **Typ rabatu:** Procentowy (np. 10%) lub Kwotowy (np. 5 zł).
    - **Wartość:** Rozsądna zachęta (np. 5, 10, 15).
    - **Minimalna kwota:** Ustaw minimalny zakup, aby zapewnić rentowność (np. 50 zł).
    - **Ważność:** 30 dni (Zachęca do szybkiego użycia).
    - **Opis:** „Dziękujemy za recenzję produktu!”
  - **Scenariusz/przykład dla sprzedawcy:** Chcesz zaoferować 10% rabatu na kolejne zamówienie, ważny przez 30 dni, z minimalnym zakupem 50 zł, jako podziękowanie za recenzję.
- **Grupa klientów (dla kuponów)**

  - **Co robi to ustawienie:** Podobnie jak w przypadku ustawienia przypomnień, pozwala to ograniczyć generowanie kuponów do określonych grup klientów.
  - **Wpływ zmiany tego ustawienia:**
    - *Wybór grup:* Tylko klienci z wybranych grup otrzymają kupony.
    - *Brak wyboru żadnej grupy:* Kupony zostaną wysłane do wszystkich klientów (chyba że zastosowano inne filtry).
  - **Zalecana wartość:** „Klienci”
  - **Scenariusz/przykład dla sprzedawcy:** Chcesz przyznawać kupony tylko swojej standardowej grupie „Klienci”, a nie „Gościom” ani „Hurtownikom”.
- **Ogranicz liczbę e-maili**

  - **Co robi to ustawienie:** Jest to funkcja bezpieczeństwa, która zapobiega wysyłaniu przez serwer zbyt wielu e-maili w krótkim czasie, co mogłoby spowodować oznaczenie Twoich e-maili jako spam lub nałożenie limitów przez dostawcę hostingu.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone:* Moduł będzie przestrzegał ustawienia „Limit e-maili”.
    - *Gdy wyłączone:* Sam moduł nie zastosuje limitu wysyłania e-maili.
  - **Zalecana wartość:** TAK
  - **Scenariusz/przykład dla sprzedawcy:** Masz dużą liczbę oczekujących przypomnień i chcesz wysyłać je stopniowo, aby uniknąć przeciążenia serwera pocztowego.
- **Limit e-maili:**

  - **Co robi to ustawienie:** Określa maksymalną liczbę e-maili (przypomnień lub kuponów), które moduł może wysłać w jednym cyklu wykonania (np. gdy uruchamia się zadanie cron).
  - **Wpływ zmiany tego ustawienia:**
    - *Ustawienie liczby (np. 50):* Moduł wyśle maksymalnie 50 e-maili na jedno uruchomienie zadania cron. Jeśli jest ich więcej, zostaną wysłane w kolejnych uruchomieniach.
  - **Zalecana wartość:** 50-100 (Dostosuj w oparciu o limity wysyłania e-maili przez dostawcę hostingu i pojemność serwera).
  - **Scenariusz/przykład dla sprzedawcy:** Twój dostawca hostingu pozwala na 100 e-maili na godzinę. Ustawiasz ten limit na 50, aby pozostać w ich wytycznych.

#### **Filtry produktów (dla przypomnień i kuponów)**

- **Włącz filtry**

  - **Co robi to ustawienie:** Aktywuje dodatkowe opcje filtrowania zarówno dla przypomnień, jak i kuponów, pozwalając określić, które produkty lub producenci są kwalifikowani.
  - **Wpływ zmiany tego ustawienia:**
    - *Gdy włączone:* Filtr „Producenci” staje się aktywny.
    - *Gdy wyłączone:* Nie zostaną zastosowane żadne filtry specyficzne dla produktów.
  - **Zalecana wartość:** NIE (Chyba że masz konkretną potrzebę filtrowania).
  - **Scenariusz/przykład dla sprzedawcy:** Chcesz wysyłać przypomnienia lub kupony tylko dla produktów od określonych producentów.
- **Producenci**

  - **Co robi to ustawienie:** Jeśli „Włącz filtry” jest aktywne, pozwala to wybrać konkretnych producentów. Przypomnienia i kupony będą wysyłane tylko dla produktów od wybranych producentów.
  - **Wpływ zmiany tego ustawienia:**
    - *Wybór producentów:* Zwęża zakres działania modułu tylko do produktów tych marek.
  - **Zalecana wartość:** Pozostaw wszystkie niezaznaczone (chyba że masz konkretną potrzebę).
  - **Scenariusz/przykład dla sprzedawcy:** Prowadzisz promocję z konkretną marką i chcesz zachęcać do komentarzy tylko dla ich produktów.

#### **Tabela szybkiego odniesienia do konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Poproś o zgodę na wysyłanie przypomnień | TAK | Zapewnia zgodność z RODO; klienci wyrażają zgodę na przypomnienia. |
| Konfiguracja modułu | Wyślij przypomnienie o komentarzu | TAK | Główny przełącznik do wysyłania e-maili z przypomnieniami. |
| Konfiguracja modułu | Przypomnij o komentarzach po: | 7 dni | Opóźnienie (w dniach) po zmianie statusu zamówienia dla pierwszego przypomnienia. |
| Konfiguracja modułu | Powtórz przypomnienie | 14 dni | Opóźnienie (w dniach) po pierwszym przypomnieniu dla drugiego (0 dla braku). |
| Konfiguracja modułu | Tytuł e-maila (Przypomnienie) | Możliwość dostosowania | Temat e-maili z przypomnieniami. |
| Konfiguracja modułu | Wybierz statusy zamówień | Dostarczone | Statusy zamówień, które wyzwalają proces przypomnień. |
| Konfiguracja modułu | Grupa klientów (Przypomnienie) | Klienci | Ogranicza przypomnienia do wybranych grup klientów. |
| Konfiguracja modułu | Wysyłaj przypomnienia o komentarzach do produktów z zamówień: | Niedawna data / Puste | Filtr daty dla kwalifikujących się zamówień. |
| Konfiguracja modułu | Rozmiar obrazu dla zdjęć produktów | `home_default` | Rozmiar zdjęć produktów w e-mailach z przypomnieniami. |
| Konfiguracja modułu | Wyślij kod kuponu za komentarz | TAK | Główny przełącznik do generowania i wysyłania kuponów. |
| Konfiguracja modułu | Wyślij kupon tylko dla klientów, którzy zakupili produkt | TAK | Ogranicza kupony do faktycznych nabywców. |
| Konfiguracja modułu | Kiedy wygenerować kupon? | Po zatwierdzeniu komentarza | Czas generowania kuponu (po przesłaniu lub zatwierdzeniu). |
| Konfiguracja modułu | Generuj kupony za komentarze: (Właściwości kuponu) | Możliwość dostosowania | Definiuje typ rabatu, wartość, ważność itp. kuponu. |
| Konfiguracja modułu | Grupa klientów (Kupon) | Klienci | Ogranicza kupony do wybranych grup klientów. |
| Konfiguracja modułu | Ogranicz liczbę e-maili | TAK | Włącza ograniczanie szybkości wysyłania e-maili. |
| Konfiguracja modułu | Limit e-maili: | 50-100 | Maksymalna liczba e-maili wysłanych na jedno uruchomienie zadania cron. |
| Konfiguracja modułu | Włącz filtry | NIE | Aktywuje filtrowanie produktów/producentów. |
| Konfiguracja modułu | Producenci | Wszystkie niezaznaczone | Filtruje kwalifikujące się produkty według producenta. |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Moduł dodaje kilka dedykowanych ekranów do Twojego Panelu administracyjnego PrestaShop do zarządzania przypomnieniami, kuponami i klientami, którzy zrezygnowali z subskrypcji. Możesz je znaleźć pod pozycją menu **„Voucher za komentarz”**, zazwyczaj znajdującą się pod **„Katalog”** lub **„Marketing”**.

#### **4.2.1 AdminComRemCommentsController: Zarządzanie przypomnieniami o komentarzach**

- **Nazwa ekranu i lokalizacja w menu:** **Voucher za komentarz > Przypomnienia o komentarzach**
- **Dostępne akcje i ustawienia:** Ten ekran wyświetla listę wszystkich oczekujących, wysłanych lub nieudanych przypomnień o komentarzach. Zobaczysz szczegóły, takie jak imię i nazwisko klienta, adres e-mail, produkt, który musi skomentować, identyfikator zamówienia, datę wysłania (lub zaplanowania) przypomnienia oraz jego aktualny status.
  - **Widok siatki / zarządzania:** Możesz przeglądać, filtrować i wyszukiwać listę przypomnień. Pozwala to monitorować aktywność modułu.
  - **Działania zbiorcze:** W zależności od wersji modułu, możesz mieć możliwość ręcznego wysyłania przypomnień lub usuwania wpisów.
- **Wpływ zmian:** Ten ekran służy głównie do monitorowania. Usunięcie wpisu tutaj zapobiegłoby wysłaniu zaplanowanego przypomnienia. Ręczne wysłanie przypomnienia spowodowałoby wysłanie e-maila do klienta.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Okresowo sprawdzaj ten ekran, aby upewnić się, że przypomnienia są wysyłane zgodnie z oczekiwaniami. Jeśli zauważysz, że klient nie otrzymał przypomnienia, możesz zbadać sprawę lub ręcznie je wywołać.

#### **4.2.2 AdminComUnsubController: Klienci, którzy zrezygnowali z subskrypcji**

- **Nazwa ekranu i lokalizacja w menu:** **Voucher za komentarz > Klienci, którzy zrezygnowali z subskrypcji**
- **Dostępne akcje i ustawienia:** Ten ekran wyświetla listę klientów, którzy zrezygnowali z otrzymywania przypomnień o komentarzach (jeśli włączono ustawienie „Poproś o zgodę”). Zobaczysz ich identyfikator klienta i adres e-mail.
  - **Widok siatki / zarządzania:** Pozwala przeglądać i zarządzać listą klientów, którzy zrezygnowali z subskrypcji.
- **Wpływ zmian:** Usunięcie klienta z tej listy sprawiłoby, że ponownie kwalifikowałby się do otrzymywania przypomnień (zakładając, że spełnia inne kryteria i nie zrezygnował z subskrypcji w innym miejscu).
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Jest to ekran związany z zgodnością. Zazwyczaj nie będziesz musiał z nim codziennie wchodzić w interakcje, ale ważne jest, aby wiedzieć, gdzie znaleźć i zarządzać preferencjami rezygnacji klientów.

#### **4.2.3 AdminComVouCommentsController: Zarządzanie kuponami za komentarze**

- **Nazwa ekranu i lokalizacja w menu:** **Voucher za komentarz > Kupony za komentarze**
- **Dostępne akcje i ustawienia:** Ten ekran zawiera kompleksową listę wszystkich kuponów wygenerowanych przez moduł w odpowiedzi na komentarze do produktów. Zobaczysz szczegóły, takie jak klient, który otrzymał kupon, produkt, który skomentował, wygenerowany kod kuponu, jego wartość, ważność i czy został użyty.
  - **Widok siatki / zarządzania:** Możesz filtrować, wyszukiwać i sortować kupony. Jest to przydatne do śledzenia skuteczności programu zachęt.
  - **Powiązane klucze konfiguracyjne:** Opcje wyświetlania i filtrowania tutaj mogą być pod wpływem `cvo_filters` i `cvo_fil_manuf` z głównej konfiguracji.
- **Wpływ zmian:** Ten ekran służy głównie do monitorowania. Możesz zobaczyć, które kupony zostały wydane i czy zostały zrealizowane.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:** Przejrzyj ten ekran, aby śledzić, ile kuponów jest wydawanych i ich wskaźniki realizacji. Te dane mogą pomóc Ci ocenić sukces Twojego programu zachęt do recenzji.

#### **4.2.4 index.php (Placeholder kontrolera administracyjnego)**

- **Nazwa ekranu i lokalizacja w menu:** Ten plik `index.php` zazwyczaj służy jako placeholder lub przekierowanie w katalogu `controllers/admin` modułu, zapewniając, że bezpośredni dostęp do katalogu nie ujawnia poufnych informacji. Nie reprezentuje on ekranu widocznego dla użytkownika w Panelu administracyjnym PrestaShop.

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci nie otrzymują e-maili z przypomnieniami. Co powinienem sprawdzić?**
O1:

-   **Moduł włączony:** Upewnij się, że opcja „Wyślij przypomnienie o komentarzu” jest ustawiona na TAK w konfiguracji modułu.
-   **Statusy zamówień:** Sprawdź, czy dane zamówienia osiągnęły jeden z wybranych przez Ciebie „Statusów zamówień” (np. „Dostarczone”).
-   **Opóźnienie przypomnienia:** Sprawdź „Przypomnij o komentarzach po:”, aby upewnić się, że minęło wystarczająco dużo dni od zmiany statusu zamówienia.
-   **Zadanie Cron:** Moduł opiera się na zadaniu cron PrestaShop do wysyłania e-maili. Upewnij się, że Twoje zadanie cron jest poprawnie skonfigurowane i regularnie uruchamiane na Twoim serwerze. Instrukcje dotyczące zadania cron zazwyczaj znajdziesz w panelu hostingowym lub w sekcji „Zaawansowane > Informacje” w PrestaShop.
-   **Konfiguracja e-maila:** Sprawdź ustawienia e-maila w PrestaShop (Zaawansowane > E-mail), aby upewnić się, że e-maile są ogólnie wysyłane poprawnie z Twojego sklepu.
-   **Zgoda klienta:** Jeśli opcja „Poproś o zgodę na wysyłanie przypomnień” jest włączona, upewnij się, że klienci faktycznie wyrazili zgodę.
-   **Limity e-maili:** Sprawdź ustawienia „Ogranicz liczbę e-maili” i „Limit e-maili”. Jeśli limit zostanie osiągnięty, e-maile zostaną wysłane w następnym uruchomieniu cron.
-   **Foldery spamowe:** Poproś klientów o sprawdzenie folderów ze spamem lub niechcianymi wiadomościami.

**P2: Kupony nie są wysyłane po pozostawieniu komentarzy.**
O2:

-   **Moduł włączony:** Upewnij się, że opcja „Wyślij kod kuponu za komentarz” jest ustawiona na TAK.
-   **Czas generowania kuponu:** Sprawdź „Kiedy wygenerować kupon?”. Jeśli jest ustawione na „Po zatwierdzeniu komentarza”, upewnij się, że komentarze zostały faktycznie zatwierdzone w Twoim Panelu administracyjnym PrestaShop (Katalog > Komentarze do produktów, jeśli używasz domyślnego modułu lub modułu recenzji innej firmy).
-   **Tylko dla kupujących:** Jeśli opcja „Wyślij kupon tylko dla klientów, którzy zakupili produkt” jest włączona, sprawdź, czy klient, który zostawił komentarz, faktycznie zakupił ten konkretny produkt.
-   **Konfiguracja kuponu:** Dokładnie sprawdź wszystkie ustawienia w sekcji „Generuj kupony za komentarze”, aby upewnić się, że można utworzyć prawidłowy kupon (np. wartość rabatu, ważność).
-   **Konfiguracja e-maila i zadanie Cron:** Podobnie jak w przypadku problemów z przypomnieniami, upewnij się, że Twoje ustawienia e-maila i zadanie cron działają.

**P3: Moduł wysyła zbyt wiele e-maili lub e-maile są opóźnione.**
O3:

-   **Limit e-maili:** Przejdź do konfiguracji modułu i upewnij się, że opcja „Ogranicz liczbę e-maili” jest włączona, a „Limit e-maili” jest ustawiony na rozsądną liczbę (np. 50-100). Zapobiega to przeciążeniu serwera.
-   **Częstotliwość zadania Cron:** Jeśli Twoje zadanie cron uruchamia się bardzo często (np. co minutę) i masz wysoki limit e-maili, może wysyłać wiele e-maili szybko. Dostosuj częstotliwość zadania cron lub limit e-maili.
-   **Limity hostingu:** Skontaktuj się z dostawcą hostingu, aby zrozumieć ich limity wysyłania e-maili na godzinę/dzień. Dostosuj „Limit e-maili” modułu odpowiednio.

**P4: Jak przetłumaczyć teksty modułu lub szablony e-maili?**
O4:

-   **Tłumaczenie Panelu administracyjnego:** Przejdź do **Lokalizacja > Tłumaczenia**.
-   **Typ tłumaczenia:** Wybierz „Tłumaczenia zainstalowanych modułów”.
-   **Wybierz swój szablon:** Wybierz swój aktualny szablon.
-   **Wybierz swój język:** Wybierz język, na który chcesz przetłumaczyć.
-   **Moduł:** Znajdź „Voucher za komentarz do produktu” na liście.
-   Możesz następnie edytować ciągi tekstowe dla konfiguracji modułu, elementów front-office (takich jak pole wyboru zgody) i szablonów e-maili. Pamiętaj, aby zapisać zmiany.

**P5: Pole wyboru modułu w front-office (dla uprawnień) nie wygląda poprawnie w moim szablonie.**
O5:

-   **Kompatybilność z szablonem:** Niestandardowe szablony czasami wymagają drobnych korekt CSS dla nowych elementów modułu.
-   **Wyczyść pamięć podręczną:** Najpierw spróbuj wyczyścić pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).
-   **Skontaktuj się z pomocą techniczną:** Jeśli problem nadal występuje, może to wymagać niewielkiej poprawki CSS. Skontaktuj się z pomocą techniczną MyPresta.eu, przesyłając zrzuty ekranu i nazwę swojego szablonu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Voucher za komentarz do produktu” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł stosuje standardową architekturę modułów PrestaShop, wykorzystując wzorce MVC tam, gdzie jest to stosowne. Integruje się z rdzeniem PrestaShop poprzez hooki dla wyświetlania w front-office i działań w back-office. Wykorzystuje niestandardowe `AdminController` do zarządzania swoimi encjami danych (przypomnienia, kupony, rezygnacje z subskrypcji) oraz `FrontController` do wykonywania zadań cron. Konfiguracja jest zarządzana za pomocą `Configuration::get()` i `Configuration::updateValue()`. Moduł nie wydaje się używać niestandardowych klas `ObjectModel`, zamiast tego prawdopodobnie zarządza swoimi danymi bezpośrednio lub poprzez istniejące encje PrestaShop (takie jak `CartRule` dla kuponów).

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   `comvou/controllers/front/CronJob.php`
    -   **Nazwa klasy i klasa nadrzędna:** `ComvouCronJobModuleFrontController` rozszerzający `ModuleFrontController`.
    -   **Odpowiedzialność:** Ten kontroler jest przeznaczony do wykonywania za pomocą zadania cron. Obsługuje zadania w tle modułu, takie jak sprawdzanie kwalifikujących się zamówień, wysyłanie przypomnień o komentarzach oraz generowanie/wysyłanie kuponów na podstawie nowych komentarzy. Zazwyczaj nie renderuje wizualnej strony, ale wykonuje działania i kończy działanie. Jest sercem automatyzacji modułu.

#### Kontrolery administracyjne Back-Office

-   `comvou/controllers/admin/AdminComRemComments.php`

    -   **Nazwa zakładki i zarządzana encja:** „Przypomnienia o komentarzach” (w menu „Voucher za komentarz”). Zarządza encjami `cvor` (Comment Voucher Order Reminder), które reprezentują zaplanowane lub wysłane przypomnienia.
    -   **Odpowiedzialność:** Zapewnia listę (widok siatki) wszystkich przypomnień o komentarzach. Pozwala administratorom przeglądać status przypomnień, filtrować je i potencjalnie wykonywać działania, takie jak ręczne wysyłanie przypomnienia lub usuwanie wpisu. Rozszerza `AdminController` i używa `HelperList` do wyświetlania.
-   `comvou/controllers/admin/AdminComUnsub.php`

    -   **Nazwa zakładki i zarządzana encja:** „Klienci, którzy zrezygnowali z subskrypcji” (w menu „Voucher za komentarz”). Zarządza encjami `cunsub` (Comment Unsubscribe).
    -   **Odpowiedzialność:** Wyświetla listę klientów, którzy zrezygnowali z otrzymywania przypomnień o komentarzach. Ten kontroler zapewnia interfejs do przeglądania i zarządzania tymi preferencjami rezygnacji, zazwyczaj za pomocą `HelperList`.
-   `comvou/controllers/admin/AdminComVouComments.php`

    -   **Nazwa zakładki i zarządzana encja:** „Kupony za komentarze” (w menu „Voucher za komentarz”). Zarządza encjami `cvov` (Comment Voucher Order Voucher), reprezentującymi wygenerowane kupony.
    -   **Odpowiedzialność:** Przedstawia listę wszystkich kuponów wygenerowanych przez moduł, szczegółowo opisując, który klient go otrzymał, dla którego produktu, kod kuponu, jego wartość i status użycia. Używa `HelperList` do wyświetlania i pozwala na filtrowanie. Wyświetlanie może zawierać logikę opartą na kluczach konfiguracyjnych `cvo_filters` i `cvo_fil_manuf`.
-   `comvou/controllers/admin/index.php`

    -   **Nazwa zakładki i zarządzana encja:** Nie jest to bezpośredni ekran widoczny dla użytkownika.
    -   **Odpowiedzialność:** Jest to standardowy środek bezpieczeństwa w PrestaShop. Zazwyczaj zawiera `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../../../"); exit;` aby zapobiec listowaniu katalogów i przekierować do katalogu głównego sklepu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Sugeruje to, że moduł może obsługiwać swoje dane bezpośrednio w głównym pliku `comvou.php` lub w swoich kontrolerach, potencjalnie używając istniejących `ObjectModel` PrestaShop (takich jak `Order`, `Customer`, `Product`, `CartRule`) i bezpośrednich zapytań do bazy danych dla swojego niestandardowego przechowywania danych (np. dla przypomnień i rekordów kuponów).

### 4.4 Zasoby JavaScript (`views/js/`)

-   `comvou/lib/voucherengine/script.js`
    -   **Zakres:** Prawdopodobnie Back-office.
    -   **Szczegóły:** Ten skrypt jest prawdopodobnie powiązany z ustawieniami generowania kuponów w konfiguracji modułu lub kontrolerze `AdminComVouComments`. Może obsługiwać dynamiczne elementy formularzy, walidację lub interakcje AJAX związane z parametrami tworzenia kuponów (np. pokazywanie/ukrywanie pól na podstawie typu rabatu, obliczanie wartości). Może być również używany do ogólnych ulepszeń interfejsu użytkownika na stronach administracyjnych modułu.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `comvou/lib/voucherengine/ps16.css`
    -   **Zakres:** Stylizacja formularzy administracyjnych Back-office.
    -   **Szczegóły:** Ten arkusz stylów zapewnia specyficzną stylizację dla strony konfiguracji modułu i potencjalnie jego niestandardowych widoków kontrolerów administracyjnych, zapewniając ich spójny wygląd z projektem back-office PrestaShop 1.6. Może zawierać reguły dla układów formularzy, pól wejściowych, przycisków i wyświetlania siatki. Programiści nadpisujący to będą celować w konkretne identyfikatory lub klasy używane przez szablony administracyjne modułu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

-   `comvou/views/templates/hook/form.tpl`

    -   **Hook:** Potencjalnie `displayAdditionalCustomerFormFields` lub `displayCustomerAccountForm`.
    -   **Wyjście:** Ten szablon prawdopodobnie renderuje pole wyboru „Poproś o zgodę na wysyłanie przypomnień” na formularzach rejestracji klienta lub aktualizacji tożsamości w front office. Zawierałby kod HTML dla pola wyboru i powiązanej z nim etykiety.
-   `comvou/views/templates/hook/header.tpl`

    -   **Hook:** `displayHeader`
    -   **Wyjście:** Ten szablon jest zazwyczaj używany do dołączania plików CSS lub JavaScript, które muszą być załadowane w sekcji `<head>` stron front-office. Może warunkowo ładować zasoby na podstawie ustawień modułu lub bieżącej strony.
-   `comvou/views/templates/hook/identity.tpl`

    -   **Hook:** Potencjalnie `displayCustomerAccountForm` lub podobne hooki na stronie tożsamości klienta.
    -   **Wyjście:** Podobnie jak `form.tpl`, ten szablon prawdopodobnie renderuje pole wyboru zgody specjalnie na stronie „Moje konto > Informacje” klienta, umożliwiając istniejącym klientom zarządzanie swoimi preferencjami przypomnień.

#### Szablony administracyjne (`views/templates/admin/`)

-   `comvou/views/templates/admin/com_rem_comments/helpers/form/form.tpl`

    -   **Cel:** Ten szablon jest używany przez `AdminComRemCommentsController` do renderowania formularza (jeśli istnieje) do dodawania/edycji przypomnienia o komentarzu, lub bardziej prawdopodobnie, do dostosowania wyświetlania pomocnika listy.
-   `comvou/views/templates/admin/com_vou_comments/helpers/form/form.tpl`

    -   **Cel:** Ten szablon jest używany przez `AdminComVouCommentsController` do renderowania formularza (jeśli istnieje) do dodawania/edycji wpisu kuponu, lub do dostosowania wyświetlania pomocnika listy dla wygenerowanych kuponów.
-   `comvou/views/templates/admin/orderstates.tpl`

    -   **Cel:** Ten szablon jest prawdopodobnie używany w głównej konfiguracji modułu (`getContent()`) do renderowania listy wielokrotnego wyboru statusów zamówień, umożliwiając sprzedawcy wybór, które statusy wyzwalają przypomnienia.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Opis modułu i analiza kodu sugerują, że moduł przechowuje swoje niestandardowe dane (przypomnienia, kupony, rezygnacje z subskrypcji) w dedykowanych tabelach bazy danych. Chociaż konkretne pliki SQL nie są wymienione, `AdminComRemCommentsController`, `AdminComUnsubController` i `AdminComVouCommentsController` implikują istnienie tabel takich jak:

-   `ps_cvor`: Przechowuje rekordy związane z przypomnieniami o komentarzach (np. ID klienta, ID produktu, ID zamówienia, status przypomnienia, data ostatniego wysłania).
-   `ps_cunsub`: Przechowuje rekordy klientów, którzy zrezygnowali z przypomnień (np. ID klienta, e-mail).
-   `ps_cvov`: Przechowuje rekordy wygenerowanych kuponów (np. ID klienta, ID produktu, wygenerowany `id_cart_rule`, kod kuponu, status).
-   Wartości konfiguracyjne są przechowywane w `ps_configuration` z kluczami takimi jak `cvo_r_d`, `cvo_r`, `cvo_repeat`, `cvo_orderstates`, `CR_ALLOWED`, `cvo_v`, `cvo_v_fn`, `cvo_v_t`, `cvo_filters`, `cvo_fil_manuf`, `CVOR_TITLE`, `CVOV_TITLE`, `cvo_customergroups_reminder`, `cvo_customergroups_voucher`, `cvo_r_fn`, `cvo_r_date`, `cvo_vonlycust`, `cvo_v_date`, `cvo_img_type`, `CVO_LIM_M_V`, `CVO_LIM_M`.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Gdy `AdminController` jest inicjowany i ustawiane są jego media (JS/CSS). | Do wstrzykiwania specyficznych dla modułu JS/CSS do Back Office. |
| `actionOrderStatusUpdate` | Po zaktualizowaniu statusu zamówienia. | Do wykrywania, kiedy zamówienie osiąga status „dostarczone” lub inny odpowiedni status, wyzwalając proces przypomnień. |
| `actionCustomerAccountAdd` | Po utworzeniu nowego konta klienta. | Do sprawdzania początkowych preferencji zgody dla nowych klientów. |
| `displayHeader` | W sekcji `<head>` stron front-office. | Do dołączania CSS/JS front-office lub meta tagów. |
| `displayCustomerAccountForm` | Na stronie „Moje konto > Informacje” klienta. | Do wyświetlania pola wyboru zgody dla istniejących klientów. |
| `displayAdditionalCustomerFormFields` | Na formularzu rejestracji klienta. | Do wyświetlania pola wyboru zgody dla nowych rejestracji klientów. |
| `validateCustomerFormFields` | Gdy formularz klienta (rejestracja/tożsamość) jest przesyłany. | Do przetwarzania wyboru pola wyboru zgody i zapisywania preferencji klienta. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i profesjonalne wsparcie techniczne, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Upewnij się, że używasz najnowszej kompatybilnej wersji modułu dla swojego sklepu PrestaShop, aby korzystać ze wszystkich ulepszeń i poprawek bezpieczeństwa.
