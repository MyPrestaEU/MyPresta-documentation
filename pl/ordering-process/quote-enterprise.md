---
title: "Quote Enterprise - instrukcja handlowa"
sidebar:
  label: "Quote Enterprise - instrukcja handlowa"
description: "Jak skonfigurować Quote Enterprise, prowadzić cały proces wyceny do zamówienia i rozwiązywać typowe problemy."
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Quote Enterprise na MyPresta.eu](https://mypresta.eu/modules/ordering-process/quote-enterprise.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/quote-enterprise/)
>
> ---


## 1. Wymagania

Moduł działa na PrestaShop 1.7, 8 i 9 oraz na PHP od 7.1 do 8.5.

Serwer potrzebuje cURL i JSON. Nie wymaga innego modułu.

Klucze Google reCAPTCHA zakładacie sami tylko wtedy, gdy włączacie reCAPTCHA. Webhooki Slack lub Teams są opcjonalne i służą tylko do digestów dla personelu. Przypomnienia e-mail i digesty wymagają crona na URL crona modułu.

## 2. Instalacja

1. Wgrajcie moduł w **Moduły**, **Menadżer modułów** i włączcie go.
2. Po instalacji w **Zamówienia** pojawiają się **Wyceny** i **Dziennik audytu**.
3. Moduł nie czyści cache podczas instalacji.
4. Instalacja tworzy tabele wycen i ukryty produkt wirtualny na pozycje usługowe oraz zapisuje domyślne ustawienia opisane poniżej.

Odinstalowanie usuwa pozycje menu, tabele modułu i klucze konfiguracji. Ukryty produkt opłat w katalogu nie jest usuwany przy odinstalowaniu.

## 3. Konfiguracja i praca w zapleczu

Otwórzcie **Moduły**, **Menadżer modułów**, **Quote Enterprise**, **Konfiguruj**. Moduł otwiera się na **Pulpicie**. Pasek górny: **Pulpit**, **Wyceny**, **Dziennik audytu**, **Ustawienia**, **PDF**, **E-maile**, **API**, **Powiadomienia**, **Aktualizacje**.

Zrzuty w tej instrukcji pochodzą z angielskiego zaplecza.

Codzienna praca z wycenami jest też w **Zamówienia**, **Wyceny** (pełna lista i edytor) oraz **Zamówienia**, **Dziennik audytu**.

### 3.1 Pełny proces wyceny

Traktujcie ten przebieg jak mapę. Sekcje poniżej opisują każdy ekran.

1. Klient prosi o wycenę ze strony produktu, listy produktów, koszyka albo listy wieloproduktowej. Goście mogą widzieć przyciski, jeśli na to pozwolicie, ale zapisanie wniosku zawsze wymaga konta klienta.
2. Wniosek trafia jako wycena w statusie **Oczekuje na weryfikację** albo personel tworzy **Szkic** w zapleczu.
3. Personel otwiera wycenę w **Zamówienia**, **Wyceny**, ustawia ceny, rabaty, wysyłkę i komunikaty, potem **Zapisz** albo **Zapisz i wyślij**.
4. **Zapisz i wyślij** wysyła e-mail do klienta i ustawia status **Wysłana** (przy ponownym wysłaniu działa też przebieg negocjacji).
5. Klient otwiera **Moje wyceny**, ogląda ofertę, może pobrać PDF, zaakceptować, odrzucić albo poprosić o zmiany (**Negocjacja**).
6. Po **Zaakceptowana** klient może przejść do kasy. Kasa buduje koszyk z wyceny i może powstać zamówienie (**Przekształcona**). Wycena się blokuje.
7. Po dacie ważności wyceny wysłane lub w negocjacji stają się **Wygasła** przy otwarciu albo przy cronie. Przypomnienia e-mail wymagają crona.

Statusy: **Szkic**, **Oczekuje na weryfikację**, **Wysłana**, **Negocjacja**, **Zaakceptowana**, **Przekształcona**, **Wygasła**, **Odrzucona**, **Anulowana**.

Klient może zaakceptować tylko **Wysłaną** i **Negocjację**. Status zmieniajcie ręcznie w edytorze, gdy trzeba.

### 3.2 Pulpit

Pulpit pokazuje lejek wycen. Otwórzcie **Parametry analityki**, ustawcie okres KPI i zakresy wykresów, potem **Zapisz parametry analityki**. Potwierdzenie: **Tracking parameters updated.** (lub lokalny odpowiednik).

![Pulpit](https://mypresta.eu/docs/images/docs/quoteenterprise-dashboard.webp)

![Tabele pulpitu](https://mypresta.eu/docs/images/docs/quoteenterprise-dashboard-b.webp)

| Pole | Na start | Co robi |
|---|---|---|
| **Okres KPI** | **Ostatnie 90 dni** | Okno czasu dla kart KPI, tabeli lejka, top klientów i personelu. Wybierzcie 30, 90, 180 lub 365 dni i zapiszcie. Liczy utworzone, wysłane, zaakceptowane, przekształcone i odrzucone w tym okresie. |
| **Zakres wykresu tygodniowego** | 12 | Liczba tygodni na wykresie tygodniowym (4–52). Zakładka Weekly: utworzone, wysłane, zaakceptowane, przekształcone na tydzień ISO. |
| **Zakres wykresu miesięcznego** | 12 | Liczba miesięcy na wykresie miesięcznym (3–24). |
| **Zakres wykresu rocznego** | 5 | Liczba lat na wykresie rocznym (2–10). |
| **Domyślna zakładka wykresu** | **Monthly** | Która zakładka otwiera się pierwsza: Weekly, Monthly lub Yearly. Można przełączać bez zapisu. |
| **Okno „wygasa wkrótce”** | 7 | Ile dni do przodu oznaczać wyceny jako wygasające. Zwykle 7 lub 14. Tylko wysłane i w negocjacji z datą ważności w tym oknie. |

Karty KPI: wartość otwartego pipeline’u, oczekujące na weryfikację, wygasające, wartość przekształconych, konwersja, win rate. Niżej: utworzone, wysłane, zaakceptowane, przekształcone, odrzucone, średnia liczba dni do przekształcenia, średnia wartość wyceny. Wykresy: lejek w czasie. Tabele: lejek okresu, starzenie otwartego pipeline’u, wygasające, ostatnia aktywność, top klienci i personel. Otwarty pipeline to wyceny wysłane, w negocjacji lub zaakceptowane.

### 3.3 Zakładka Wyceny w konfiguracji modułu

To skrócony przegląd. Pełne filtry, akcje masowe i edytor są w **Zamówienia**, **Wyceny**.

![Przegląd wycen](https://mypresta.eu/docs/images/docs/quoteenterprise-quotes.webp)

Cel ekranu: szybka lista ostatnich wycen z konfiguracji. **View** otwiera pełny edytor. **Manage all quotes** — filtry, eksport, operacje masowe. Efekt: ustawienia zostają lekkie, a pełna praca dzieje się na dedykowanym ekranie.

**Utwórz wycenę:** wybierzcie klienta (wyszukiwanie), opcjonalnie **Notatka wewnętrzna**, kliknijcie **Create draft quote**. Przekierowanie do pełnego edytora. Bez klienta: **Please select a customer.**

**Szablony wycen** (gdy istnieją): wybierzcie szablon i klienta, potem **Create from template**.

Kolumny **Recent quotes**: Reference, Customer, Status, Total. Pusto: **No quotes yet.** Linki: **Manage all quotes**, **CSV**, **XML**, **Open full quotes list**.

### 3.4 Lista wycen (menu Zamówienia)

Otwórzcie **Zamówienia**, **Wyceny**. To główny ekran zarządzania.

Kolumny: **ID**, **Reference**, **Customer**, **Status**, **Total**, **Valid until**, **Assigned**, **Created**. Akcje wiersza: edycja i duplikacja. Nie dodacie pustej wyceny z paska listy — twórzcie z przeglądu modułu, ze szablonu albo przez duplikację. Błąd: **Create quotes from module configuration or duplicate an existing quote.**

Akcje masowe:

| Akcja | Co robi |
|---|---|
| **Assign to employee** | Przypisuje pracownika do zaznaczonych wycen. |
| **Extend validity** | Przedłuża ważność zaznaczonych. |
| **Send expiry reminder** | Wysyła przypomnienia do klientów (dialog potwierdzenia). |
| **Export CSV** | Pobiera CSV zaznaczenia. |
| **Export XML** | Pobiera XML zaznaczenia. |

Filtrujcie po statusie i szukajcie jak na standardowej liście PrestaShop. Otwórzcie wiersz, aby edytować.

### 3.5 Edytor wyceny — jak zarządzać wnioskiem

Otwórzcie wycenę z listy. Legenda pokazuje numer i status, np. `Q-2026-00001 — Pending review`.

**Typowa ścieżka personelu dla nowego wniosku klienta**

1. Filtrujcie lub otwórzcie wyceny **Pending review**.
2. Sprawdźcie **Messages from customer** (tekst wniosku, później prośby o zmianę lub powody odmowy). Tylko do odczytu.
3. Dodajcie lub poprawcie **Line items** (produkty katalogowe i usługi własne).
4. Ustawcie **Global discount %** / **Global discount amount**, **Shipping label** i kwoty wysyłki.
5. Napiszcie **General message to customer** i opcjonalnie **Internal note**.
6. Ustawcie **Validity period** i **Validity unit**, sprawdźcie aktualną datę ważności.
7. W razie potrzeby ustawcie **Status**, potem **Save** (**Quote saved.**) albo **Save & send** (**Quote sent to customer by e-mail.**).

**Blokada.** Zaakceptowane lub przekształcone wyceny są zablokowane. Wygasła: **This quote has expired. Click Unlock to extend validity and send an updated offer.** Przekształcona: **This quote is locked because it was converted to an order.** Zaakceptowana: **This quote is locked because the customer accepted it. Click Unlock to make changes.** Odblokowanie: **Quote unlocked for editing.** Ponowna blokada: **Quote locked again.**

| Pole | Co robi (z opisów pól) |
|---|---|
| **Status** | Etap procesu sprzedaży. Draft: tylko wewnętrznie. Pending review: klient złożył wniosek, czekacie na wycenę. Sent: wysłana e-mailem. Accepted: klient zgodził się. Converted: powstało zamówienie. Tylko Sent i Negotiation klient może zaakceptować. Status zmieniajcie ręcznie, gdy trzeba. |
| **Validity period** | Jak długo klient ma na akceptację, licząc od zapisu/wysyłki. Przykłady: 15 z Minutes, 1 z Hours, 30 z Days. Zapis przelicza wygaśnięcie od teraz. Po terminie klient nie zaakceptuje. Krótkie okresy mogą wygasnąć przed dziennym cronem przypomnień. |
| **Validity unit** | Minuty, godziny lub dni wraz z liczbą ważności. |
| **Payment hint** | Krótka notatka o płatności, np. „przelew 30 dni”. Na widoku klienta i PDF. Nie wymusza modułu płatności. |
| **Global discount %** | Dodatkowy rabat 0–100 na wszystkie pozycje produktowe przed wysyłką. Przy kasie może wejść jako reguła koszyka. |
| **Global discount amount (tax excl.)** | Stały rabat od podsumy produktów. Przy obu wartościach najpierw procent. |
| **Shipping label** | Nazwa na PDF, np. „Express delivery”. |
| **Shipping (tax excl.)** / **Shipping (tax incl.)** | Koszt dostawy. Brutto liczy się z netto przy regule podatkowej w ustawieniach. Wchodzi do sumy i do kasy jako stała wysyłka. |
| **Messages from customer** | Wszystko, co napisał klient (wniosek, prośba o zmianę, odmowa). Tylko odczyt. Odpowiedź w polach poniżej. |
| **General message to customer** | Stały komunikat zawsze widoczny dla klienta (zakres, lead time, warunki). Na widoku, PDF i w e-mailach. |
| **Internal note** | Notatka dla zespołu. Nigdy nie widoczna dla klienta. |
| **Line items** | Pozycje produktowe i usługi. Dodajcie produkt katalogowy (kombinacja gdy wymagana). Usługa: opis, ilość, cena netto, VAT %. Usługi na PDF; przy kasie trafiają do produktu fee. Komunikaty: **Product line added.**, **Custom line added.**, **Line removed.**, **Select a product to add.**, **Please select a product combination.**, **Enter a service line description.** |
| **Comment for this send** | Jednorazowa notatka tylko dla tego **Save & send**. Wyjaśnia zmiany. Czyści się po wysyłce. W timeline, opcjonalnej historii PDF i e-mailu tej wysyłki. |
| **Version history** | Migawki poprzednich wersji. |
| **Save as template** | Nazwa szablonu i zapis. Potem nowe wyceny z szablonu dla innego klienta. **Please enter a template name.**, **Template "…" saved.** |
| **Quote timeline** | Chronologia zdarzeń personelu i klienta. |

Duplikacja z listy lub edytora: przy błędzie **Unable to duplicate quote.** Po duplikacji edytujecie kopię.

### 3.6 Dziennik audytu

Zakładka modułu: ostatnia aktywność (wnioski, wysyłki, akceptacja/odrzucenie, negocjacje). **View** — pełny kontekst. **Zamówienia**, **Dziennik audytu** — filtry, eksport, pełna historia.

Cel: dziennik tylko do dopisywania (compliance i diagnostyka). Wpisy nie do edycji ani usuwania. Wiersz przechowuje nazwę i ID aktora (pracownik lub klient) w momencie akcji. Odznaki: Employee, Customer, System.

### 3.7 Ustawienia — Motyw i wygląd

Otwórzcie **Ustawienia**. Po zmianach **Zapisz** na dole.

![Motyw i wygląd](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-theme.webp)

| Pole | Na start | Co robi |
|---|---|---|
| **Front theme template** | **Auto-detect (recommended)** | Który zestaw szablonów i CSS dla Moje wyceny, podglądu i linku w koncie. Zostawcie Auto-detect, chyba że fork motywu jest źle wykrywany — wtedy wymuście Classic lub Hummingbird. |
| **Quantity display format** | **Integer (e.g. 1, 2)** | Jak ilości widać na froncie, w BO, PDF i e-mailach. Albo **Fixed decimals (e.g. 1.000, 2.500)**. Pola formularza używają tego samego formatu. |
| **Quantity decimal places** | 3 | Cyfry po przecinku przy fixed decimals. Typowo 3 B2B lub 2 retail. Ignorowane w trybie integer. |

### 3.8 Ustawienia — Ogólne

![Ogólne](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-general.webp)

| Pole | Na start | Co robi |
|---|---|---|
| **Module enabled** | **Yes** | Główny włącznik całego procesu wycena→zamówienie. Yes: klienci proszą o wyceny, personel zarządza ofertami. No: ukrywa wszystkie przyciski i linki w koncie bez odinstalowania. Wyłączony: brak nowych wniosków i przycisków na koszyku, produkcie i kategoriach. Istniejące wyceny zostają w zapleczu. |
| **Product page quote button** | **Yes** | Pokazuje **Request a quote** na stronie produktu. Dla B2B, gdy kupujący pyta o cenę jednego SKU. Klient zalogowany (lub dozwolony flow gościa) i w dozwolonej grupie. Instant otwiera formularz produktu. List dodaje ilość i kombinację do pływającej listy. |
| **Cart quote button** | **Yes** | **Request a quote** w koszyku. Gdy klienci proszą o ofertę na kilka produktów naraz. Szanuje minimalną wartość koszyka poniżej. Zawartość koszyka staje się podstawą nowego wniosku po potwierdzeniu. |
| **Category / list quote button** | **Yes** | Zwarty **Request quote** na listach (kategoria, wyszukiwanie, nowości). Te same reguły uprawnień. Instant: flow produktu. List: produkt (domyślna kombinacja, qty 1) do listy. |
| **Product quote mode** | **Instant — open form for this product** | Instant: formularz bieżącego produktu. List: koszyk wycen; pływający przycisk otwiera jeden formularz ze wszystkimi produktami. Wnioski z koszyka pozostają osobne. Pływający przycisk tylko w trybie List, gdy lista niepusta. |
| **Floating quote button position** | **Bottom right** | Albo **Bottom left**. Tylko przy trybie List. Badge z liczbą produktów; otwiera formularz wieloproduktowy. |
| **Allow guests** | **No** | Czy osoby bez konta mogą zacząć wniosek. Wyłączone przy ścisłym B2B. Włączone: gość widzi przycisk, ale i tak loguje się lub rejestruje przed zapisem. Nie tworzy anonimowych wycen. |

### 3.9 Ustawienia — Widoczność przycisku wyceny

![Widoczność](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-visibility.webp)

| Pole | Na start | Co robi |
|---|---|---|
| Grupy klientów | wszystkie | Kto widzi przyciski. Wszystkie grupy albo wybrane (np. Wholesale). Poza wybranymi grupami przycisków nie widać nawet przy włączonym module. |
| **Enable catalog visibility rules** | **No** | Włącza reguły katalogowe. Ogranicza wyceny do produktów, kategorii, marek lub dostawców. Wyłączone: każdy produkt (reguły grup nadal). Włączone: whitelist/blacklist i filtry poniżej. |
| **Catalog rule mode** | **Whitelist — only matching products** | Whitelist: przyciski tylko na pasujących. Blacklist: ukryj na pasujących. Produkt pasuje, jeśli jest na liście produktów albo należy do wybranej kategorii, producenta lub dostawcy. |
| Selektory katalogu | puste | Kategorie (drzewo), produkty (szukaj), producenci i dostawcy. Puste = tylko filtry pomocnicze. Reguły łączą się OR — wystarczy jedno dopasowanie. |
| **Minimum product price** | 0 | Ukryj przyciski poniżej tej ceny brutto na sklepie. 0 wyłącza. Przy włączonych regułach katalogowych. |
| **Exclude virtual products** | **No** | Blokuj wyceny produktów wirtualnych / do pobrania przy regułach katalogowych. |
| **Exclude out-of-stock products** | **No** | Ukryj przyciski, gdy produktu nie można zamówić przy braku stocku (zachowanie PrestaShop). |
| **Mixed cart (eligible + excluded items)** | **Hide cart quote button** | Koszyk miesza wycenialne i niewycenialne: Show = przycisk widoczny, import tylko eligible; Hide = ukryty, aż koszyk będzie tylko wycenialny. Wszystko eligible → zawsze Show. Wszystko excluded → zawsze Hide. |

### 3.10 Ustawienia — Formularz wniosku o wycenę produktu

| Pole | Na start | Co robi |
|---|---|---|
| **Require privacy policy acceptance** | **Yes** | Obowiązkowy checkbox prywatności w modalu wniosku (RODO). Klient musi zaakceptować przed wysłaniem. |
| **Privacy policy CMS page** | brak | Strona CMS w linku checkboxa. Puste = tekst bez linku. |
| **Enable reCAPTCHA** | **No** | Chroni formularz Google reCAPTCHA v2. Przy włączeniu wymagane klucze poniżej. |
| **reCAPTCHA site key** | puste | Publiczny site key z panelu Google (v2 checkbox). |
| **reCAPTCHA secret key** | puste | Secret key. W konfiguracji sklepu. |
| **Minimum cart total** | 0 | Minimalna wartość koszyka przed pokazaniem przycisku w koszyku. Waluta sklepu. 0 = bez minimum. Tylko przycisk koszyka, nie pojedynczy produkt. |

### 3.11 Ustawienia — Oferty i numery

| Pole | Na start | Co robi |
|---|---|---|
| **Default validity** | 30 | Domyślny czas ważności po utworzeniu. Liczba + jednostka: minuty (flash), godziny (tego dnia), dni (standard B2B). Ustawia valid_until przy nowych wycenach ze sklepu, BO i duplikatów. Nadpisanie w edytorze. |
| **Default validity unit** | **Days** | Minutes, hours lub days z liczbą powyżej. Przypomnienia i automatyczny Expired nadal zależą od crona przy przypomnieniach. |
| **Expiry reminder (days before)** | 3 | E-mail przed wygaśnięciem. Tylko dzienny cron. Każda kwalifikująca się wycena co najwyżej jedno przypomnienie z linkiem. Bez crona brak przypomnień. |
| URL crona | token | Automatyczne przypomnienia i statusy. Dodajcie URL do crontab raz dziennie (np. 08:00). Regenerujcie token przy wycieku. Wygaśnięcie też przy otwarciu wyceny; e-maile przypomnień nadal wymagają crona. |
| **Reference prefix** | Q | Prefiks numerów. Moduł dokłada rok i sekwencję, np. Q-2026-00042. Łatwiejsze rozpoznanie w e-mailu i PDF. |
| **Notify staff on new request** | **Yes** | E-mail do personelu przy nowym wniosku. Preferencje > Kontakt. Szablon qe-request-staff w zakładce E-maile. |

Żółta notatka: cron potrzebny do automatyzacji ważności; wygaśnięcie też przy otwarciu; przypomnienia używają URL crona.

### 3.12 Ustawienia — Kasa

| Pole | Na start | Co robi |
|---|---|---|
| **Shipping / service tax rule** | domyślna reguła sklepu | VAT dla wysyłki i usług przy kwotach netto. Grupa reguł z Katalog → Produkty. Po wyborze zapis wyceny przelicza shipping brutto z netto. |
| **Fee product (custom lines)** | tworzony przy instalacji | Ukryty produkt wirtualny na pozycje usługowe w kasie. Tworzony automatycznie — zmieniajcie tylko, gdy musicie wskazać inny produkt. Przy kasie suma usług = jedna pozycja koszyka z zablokowaną ceną. |

### 3.13 PDF

Zakładka **PDF**. Legenda: **PDF documents**. Przy wyłączonym PDF przyciski pobierania znikają, URL PDF zwraca not found.

| Pole | Na start | Co robi |
|---|---|---|
| **Enable PDF** | **Yes** | Główny włącznik generowania PDF i linków. Wyłączcie, jeśli nie chcecie proform PDF. Wyłączone: brak przycisków w BO, sklepie i na zamówieniu; bezpośrednie URL PDF = not found. Szablony e-mail nadal mają pusty placeholder URL PDF. |
| **Use shop logo on PDF** | **Yes** | Logo sklepu z Preferencje > Motywy. No: tylko własne logo poniżej (jeśli jest). Logo na górze PDF / proformy. |
| **Add negotiation history to PDF** | **No** | Dopisuje krótki log komunikacji (prośby o zmianę, ponowne wysyłki, akceptacja, odmowa). Zwarta tabela przed warunkami. Pusto bez aktywności negocjacyjnej. |
| **Custom PDF logo** | puste | Opcjonalne PNG/JPG tylko na PDF wycen. Nadpisuje logo sklepu. |
| **PDF terms & conditions** | puste | Warunki prawne/handlowe na dole każdego PDF. |
| **Authorized signature** | puste | Podpis, np. „Jan Kowalski, Dyrektor sprzedaży”. Puste = pominięte. |

### 3.14 E-maile

Zakładka **E-maile**. Transakcyjne maile cyklu wyceny. Edytujcie temat i treść per język. Placeholdery z sidebara (imię klienta, numer, link, sumy). Klucze: qe-request-staff, qe-quote-sent, qe-quote-accepted, qe-quote-rejected, qe-quote-negotiation, qe-quote-reminder, qe-staff-digest. Klienci i personel dostają je przy wniosku, wysyłce, akceptacji lub przed wygaśnięciem. Po zmianach testujcie.

### 3.15 API

Zakładka **API**. Połączenie CRM, ERP lub automatyki. Etykieta klucza i **Generate new API key**. Skopiujcie klucz. **Revoke** wyłącza (potwierdzenie). Pusto: **No API keys yet.** **API documentation**: list, get, pending, stats, update_status. Wywołujcie URL API modułu z kluczem.

### 3.16 Powiadomienia

Zakładka **Powiadomienia** (**Staff digest notifications**). Okresowe podsumowanie, gdy wyceny czekają na akcję, bez jednego maila na zdarzenie.

Co liczy się jako oczekujące: **Pending review** (nowy wniosek) lub **Negotiation** (klient prosi o zmiany). Sent, accepted, expired, converted nie wchodzą. Cron według harmonogramu. Gdy digest włączony, jest przynajmniej jedna oczekująca wycena i minął interwał — wiadomość na każdy skonfigurowany kanał. Personel widzi skrót z numerami, statusem, klientem i linkami do BO (do 20 wycen).

| Pole | Na start | Co robi |
|---|---|---|
| **Enable digest** | **No** | Główny włącznik. Włączcie po ustawieniu co najmniej jednego kanału. Cron musi być zaplanowany — digesty nie idą z wizyt stron. Wyłączony: cron nadal robi przypomnienia i statusy, bez digestu. |
| **Interval (hours)** | 24 | Minimalny czas między digestami (1–168). Uruchamiajcie cron co najmniej tak często. Po udanym digescie następny czeka ten czas. |
| **E-mail recipients** | puste | Przecinki lub średniki. Puste = e-mail sklepu z Preferencje > Kontakt. Szablon qe-staff-digest. |
| **Slack webhook URL** | puste | Incoming webhook. Puste = bez Slack. |
| **Teams webhook URL** | puste | Connector webhook. Puste = bez Teams. |

**Zapisz** zapisuje. **Send test digest now** — test, gdy są oczekujące wyceny. Ten sam URL crona co w Ustawieniach.

### 3.17 Aktualizacje

Zakładka **Aktualizacje**. **Check Now** sprawdza nową wersję. **Automatic Notifications** włączone lub wyłączone. **Zapisz** zapisuje ustawienia aktualizacji.

### 3.18 Blok wyceny na zamówieniu

Na zamówieniu z wyceny zaplecze pokazuje **Source quote** z linkiem do wyceny i opcjonalnie **View quote PDF**.

## 4. Front sklepu

Klienci widzą narzędzia wycen, gdy moduł jest włączony i ich grupa jest dozwolona.

**Strona produktu.** **Request a quote** otwiera formularz (instant) albo dodaje do listy (list). Checkbox prywatności i reCAPTCHA według ustawień.

**Lista produktów.** **Request quote** — te same reguły.

**Koszyk.** **Request a quote** — minimum koszyka i reguły mixed cart. Potwierdzony koszyk → wycena oczekująca.

**Tryb list.** Pływający przycisk z liczbą otwiera formularz wieloproduktowy.

**Konto klienta.** Link **Moje wyceny**: historia, status, ważność, **View**, PDF gdy włączone, **Checkout** po akceptacji, **Request re-opening** przy wygasłej/zablokowanej. Pusto: **You have no quotes yet…** Po wysłaniu: **Your quote request has been submitted…**

**Widok wyceny.** Akceptacja, odrzucenie, prośba o zmiany, PDF, kasa po akceptacji. Zablokowana wygasła: **Locked — validity expired**.

Goście mogą widzieć przyciski przy **Allow guests** = **Yes**, ale zapis tylko dla zalogowanego klienta.

W tym pakiecie nie ma zrzutu frontu — sklep testowy był niedostępny przy kończeniu screenów.

## 5. Typowe problemy

**Brak przycisku na produkcie lub w koszyku.** Sprawdźcie **Module enabled**, właściwy włącznik przycisku, grupę klienta i widoczność katalogu. Dla koszyka: **Minimum cart total** i **Mixed cart**.

**Gość nie kończy wniosku.** Zapis zawsze wymaga konta.

**Wycena zablokowana / brak edycji.** Odblokujcie przy accepted lub expired (przedłużcie ważność). Przekształcone zostają zablokowane względem zamówienia.

**Klient nie może zaakceptować.** Status musi być Sent lub Negotiation, a ważność w przyszłości.

**Przypomnienia nie dochodzą.** Zaplanujcie cron i trzymajcie **Expiry reminder** powyżej zera. Otwarcie wyceny może ją wygasić bez crona; przypomnienia nadal potrzebują crona.

**Brak przycisków PDF.** Włączcie **Enable PDF**.

**reCAPTCHA blokuje formularz.** Wyłączcie albo wpiszcie oba klucze.

**Digest personelu nie dochodzi.** Włączcie digest, ustawcie kanał, uruchamiajcie cron co najmniej tak często jak interwał.

**Po odinstalowaniu zniknęło menu.** Zainstalujcie ponownie. Odinstalowanie kasuje tabele wycen. Produkt fee może zostać w katalogu.

## 6. Przewodnik dewelopera

### 6.1 Przegląd

Nazwa techniczna `quoteenterprise`, wersja 1.7.6, klasa `quoteenterprise` extends `Module`. Display name przez `$this->l('Quote Enterprise')`. Autor MyPresta.eu. Tab `checkout`. URL produktu w `$this->mypresta_link`.

Przepływ: wniosek → wiersz `quote` → edycja/wysyłka → akceptacja/negocjacja → kasa → zamówienie. Teksty pomocy dla merchantów: `QuoteSettingDescTrait` i metody `desc*` edytora.

### 6.2 Pliki

- `quoteenterprise.php` — instalacja, hooki, wejście do konfiguracji, URL crona.
- `classes/QuoteAdmin.php` — zakładki konfiguracji i formularze ustawień.
- `classes/QuoteAdminQuoteForm.php` — edytor wyceny.
- `classes/QuoteQuotesManager.php` — przegląd, save/send/linie/szablony.
- `classes/QuoteDashboard.php`, `QuoteVisibility.php`, `QuoteListHelper.php`, `QuoteRequestHelper.php`, `QuoteMailer.php`, `QuotePdf.php`, `QuoteApi.php`, `QuoteNotifyDigest.php`, `QuoteExpiry.php`, `QuoteConverter.php`, `QuoteFeeProduct.php`, `QuoteSettingDescTrait.php`.
- `controllers/admin/AdminQuoteEnterpriseQuotes.php`, `AdminQuoteEnterpriseAuditLog.php`.
- `controllers/front/` — `list`, `view`, `request`, `quoteList`, `pdf`, `cron`, `api`.
- `models/` — `quote`, `quotedetail`, `quoteauditlog`, `quoterevision`, `quoteapikey`.
- `views/templates/`, `lib/updateChecker.php`, `lib/emailTemplatesManager/`, `lib/searchTool/`.

### 6.3 Kontrolery

Admin pod **Zamówienia** (`AdminParentOrders`). Front w `$this->controllers`. Cron: `QE_CRON_TOKEN`. API: aktywny klucz i nazwa akcji.

### 6.4 Hooki

Zarejestrowane: `displayHeader`, `displayShoppingCart`, `displayCustomerAccount`, `displayProductAdditionalInfo`, `displayProductActions`, `displayFooterProduct`, `displayFooter`, `actionProductPriceCalculation`, `actionValidateOrder`, `actionAdminControllerSetMedia`, `displayProductListFunctionalButtons`, `displayProductListReviews`, `displayProductPriceBlock`, `displayAdminOrderMain`, `displayAdminOrderSide`, `displayAdminOrder`, `actionCartGetPackageShippingCost`. Brak własnych hooków zewnętrznych.

### 6.5 Override’y

Moduł nie dostarcza override’ów klas ani kontrolerów.

### 6.6 Baza

| Tabela | Zawartość |
|---|---|
| `quote` | Nagłówek wyceny. |
| `quote_detail` | Pozycje. |
| `quote_revision` | Migawki wersji. |
| `quote_audit_log` | Aktywność tylko do dopisywania. |
| `quote_api_key` | Klucze API. |
| `qe_cart_quote` | Powiązanie koszyk–wycena. |

Odinstalowanie kasuje te tabele. `QuoteSchema::ensure` i `inconsistency()` naprawiają braki przy otwarciu konfiguracji.

### 6.7 Klucze i tłumaczenia

Klucze `QE_*`. Domyślne w `installDefaults()`. Nowy język: `translations/{iso}.php`. Pomoc pól: `QuoteSettingDescTrait` i `desc*` edytora. Stringi: `$this->l()` i `{l s=... mod='quoteenterprise'}`.

### 6.8 Rozszerzanie

Nadpiszcie szablony frontu w `modules/quoteenterprise/` w motywie. Classic i Hummingbird. Inny układ PDF = zmiana szablonu PDF lub kodu.

## 7. Support

Strona modułu: [Quote Enterprise](https://mypresta.eu/modules/ordering-process/quote-enterprise.html).

Aby napisać w sprawie tego modułu, zalogujcie się na konto klienta na [mypresta.eu](https://mypresta.eu/), otwórzcie [Kontakt](https://mypresta.eu/contact.html) i wybierzcie temat **Support for paid modules**. Formularz wymaga logowania. Po zalogowaniu wybierzcie ten moduł z historii zakupów.
