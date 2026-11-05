---
title: "Microsoft Advertising UET Tag & Conversions API - dokumentacja i instrukcja obsługi"
description: "Skonfiguruj śledzenie, zweryfikuj zdarzenia za pomocą diagnostyki na żywo i rozwiaz problemy po instalacji modułu."
sidebar:
  label: "Microsoft Advertising UET Tag & Conversions API - dokumentacja i instrukcja obsługi"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Microsoft Advertising UET Tag & Conversions API na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/microsoft-advertising-uet-tag-conversions-api/)
>
> ---


## 1. Wymagania

Przed konfiguracją przygotuj sklep, konto Microsoft Advertising i zaplanowane zadanie.

- Użyj PrestaShop 1.7, 8 lub 9.
- Użyj PHP 7.1–8.x, zgodnie z wersją PHP wymaganą przez Twoja instalacje PrestaShop.
- Włącz rozszerzenia PHP cURL, JSON, OpenSSL i hash.
- Posiadaj konto Microsoft Advertising i identyfikator tagu UET. Uzyskaj także token nosnika Conversions API dla **Conversions API** lub **UET + CAPI**.
- Miej dostęp do CRON podczas korzystania z CAPI, ponieważ jego kolejka musi działać regularnie.
- Skonfiguruj zewnętrzny moduł CMP lub plik cookie przed zmiana **Require marketing / analytics consent** na **Yes**.
- żaden inny moduł PrestaShop nie jest wymagany. Moduł kanału Microsoft Merchant Center jest opcjonalny i może pomóc w dostosowaniu identyfikatorów katalogów.

## 2. Instalacja

1. Otwórz **Modules > Module Manager**.
2. Kliknij **Upload a module** i prześlij plik ZIP.
3. Zainstaluj **Microsoft Advertising UET / Conversions API**.
4. Znajdź go w **Module Manager** i kliknij **Configure**.
5. Wypełnij **Setup Wizard** lub skonfiguruj wszystkie karty ręcznie.

Moduł nie tworzy widocznej pozycji menu **Catalog**. Jego punktem koncowym danych jest ukrytą karta zaplecza używana wewnetrznie.

Instalacja nie czyści pamięci podręcznej PrestaShop. Wyczysc go w obszarze **Advanced Parameters > Performance** tylko wtedy, gdy stare zasoby lub stary ekran konfiguracji pozostają widoczne.

Odinstalowanie usuwa dziennik zdarzeń modułu, reguły wielotagowe, kolejkę CAPI, ukryty punkt końcowy i klucze konfiguracyjne modułu. Klucze modułu sprawdzania aktualizacji mogą pozostać. Ponowna instalacja rozpoczyna się od ustawień domyślnych i nie przywraca usuniętych zdarzeń ani reguł.

## 3. Konfiguracja i prace back-office

Otwórz **Modules > Module Manager**, znajdź **Microsoft Advertising UET / Conversions API** i kliknij **Configure**.

Postepuj zgodnie z tym procesem:

1. Ukończ **Setup Wizard**.
2. Potwierdź kanał i poświadczenia w **Tracking mode**.
3. Wybierz sygnały w **Events**.
4. Dopasuj identyfikatory produktów wydarzen do swojego pliku danych w **Catalog IDs**.
5. Skonfiguruj **Privacy & consent**.
6. Zdefiniuj zachowanie dotyczące płatności i zwrotów w **Order lifecycle**.
7. Dodaj **Multi-tag rules** tylko dla poswiadczen specyficznych dla kontekstu.
8. Zaplanuj wyświetlanie adresu URL CRON co 1–5 minut, gdy aktywny jest CAPI.
9. Przegladaj witryne sklepowa i zweryfikuj zdarzenia w **Live Statistics** i **Health & diagnostics**.
10. Potwierdź wydarzenia w Microsoft Advertising.

Zrzuty ekranu w tej instrukcji pochodz? z angielskiego panelu administracyjnego.

### 3.1 Kreator konfiguracji

Użyj kreatora do pierwszej konfiguracji. Prowadzi Cię przez **Mode**, **Tag ID**, **CAPI token**, **Test** i **Done**.

![Setup Wizard](https://mypresta.eu/docs/images/docs/mybing-wizard.webp)

| Pole | Na poczatku | Co to robi |
|---|---|---|
| **Mode** | Nie wybrano | Wybierz **UET Tag** do śledzenia przeglądarki, **Conversions API** do śledzenia serwera lub **UET + CAPI** do obu. Tryb podwójny wykorzystuje wspóldzielony identyfikator zdarzenia do deduplikacji. |
| **Tag ID** | Pusty | Wklej identyfikator z Microsoft Advertising w obszarze Tag UET lub śledzenie konwersji. Jest to wymagane w kazdym trybie. |
| **CAPI token** | Pusty | W trybie CAPI lub podwójnym wklej token okaziciela z sekcji Conversions API tagu UET. Potraktuj to jako hasło. |
| **Enable Ghost Collector (msclkid / anonymousId sync)** | Tak | Zbieraj identyfikatory kliknięć Microsoft i anonimowych gości w trybach obsługujących CAPI bez wykonywania wywołań śledzących UET. Pozostaw te opcje wlaczona, aby zapewnić lepsze dopasowanie i ciaglosc sesji. |
| **Test** | Nie prowadzony | W trybie UET sprawdz identyfikator tagu, a następnie zweryfikuj odsłonę strony sklepu. W trybach obsługujących CAPI kliknij **Send test purchase**, aby wysłać zakup testowy o wartości 1 €. Poczekaj 10–30 minut, az reklama Microsoft Advertising wyświetli ja. |
| **Done** | Niekompletne | Zakończ konfiguracja i otwórz skróty do **Tracking mode**, **Health & Data Quality Coach** lub **Live Statistics**. |

Użyj **Start over**, aby ponownie uruchomić kreatora. Istniejące dane uwierzytelniające pozostają wstępnie wypełnione do czasu ich zmiany.

### 3.2 Tryb śledzenia i dane uwierzytelniające

Wybierz sposób, w jaki wszystkie zdarzenia docierają do Microsoft Advertising, wypełnij poła wyświetlane dla tego trybu i kliknij **Save**.

![Tracking mode and credentials](https://mypresta.eu/docs/images/docs/mybing-tracking-mode.webp)

| Pole | Na poczatku | Co to robi |
|---|---|---|
| **Tracking mode** | Nie wybrano | **UET Tag** wysyła z przeglądarki. **Conversions API** kolejkuje zdarzenia serwera. **UET + CAPI** wysyła oba z tym samym identyfikatorem zdarzenia, aby Microsoft mógl je deduplikowac. |
| **Tag ID(s)** | Pusty | Wpisz identyfikator znacznika UET i nacisnij przecinek lub Enter. Identyfikator jest wymagany w przypadku UET, CAPI i trybu podwójnego. |
| **Conversions API token** | Pusty | Wklej token okaziciela z **Microsoft Advertising > UET tag > Use Conversions API > Copy Token**. |
| **CAPI endpoint override (advanced)** | Pusty | Pozostaw puste, aby użyć standardowego miejsca docelowego Microsoft. Ustaw te opcje tylko wtedy, gdy firma Microsoft dokumentuje niestandardowego hosta dla Twojego konta. |
| **Ghost collector (CAPI)** | Tak | Przechwyć `msclkid` i anonimowy identyfikator gościa w celu dopasowania CAPI. Nie wywołuje śledzenia UET. |
| **Bing ID Sync (remarketing)** | Tak | Gdy UET jest aktywny, wyślij anonimowy identyfikator gościa za pośrednictwem Bing ID Sync, aby poprawić dopasowanie odbiorców remarketingu. |

W przypadku trybu CAPI lub podwójnego skopiuj wyświetlony plik **CRON URL** do harmonogramu i uruchamiaj go co 1–5 minut.

### 3.3 Wydarzenia

Najpierw wybierz i zapisz tryb śledzenia. Następnie włącz tylko te sygnały, których potrzebujesz i kliknij **Save**.

![Tracked events](https://mypresta.eu/docs/images/docs/mybing-events.webp)

| Pole | Na poczatku | Co to robi |
|---|---|---|
| **PAGE_VIEW** | Tak | Rejestruj każde zaladowanie strony sklepu. Obsluguje raportowanie i atrybucję ruchu; wyłączenie go nie powoduje zatrzymania innych zdarzeń. |
| **view_item (+ select_item)** | Tak | Wyślij `view_item` na stronach produktów i `select_item`, gdy produkt zostanie klikniety w kategorii, wyszukiwaniu lub na listach bestsellerów. |
| **view_item_list** | Tak | Wyślij około pierwszych 20 produktów z list kategorii, wyszukiwania i list bestsellerów z identyfikatorami, nazwami, cenami i pozycjami. Posiada własny wylacznik. |
| **add_to_cart** | Tak | Rekordowe dodanie koszyka. UET i tryb podwójny wykorzystuja natywne zdarzenie koszyka oraz opcjonalną rezerwe CSS. Tryb tylko CAPI wykorzystuje sciezke serwera i nie potrzebuje selektorów CSS. |
| **REMOVE_FROM_CART (Microsoft: Other)** | Tak | Rejestruj usunięcia koszyka jako **Other**, ponieważ firma Microsoft nie ma natywnego typu usuwania z koszyka. |
| **CHECKOUT** | Tak | Uruchom, gdy klient wejdzie do koszyka lub przeplywu zamówienia i zaznacz zamiar zakupu. |
| **CHECKOUT details** | Tak | Dodaj wartość, waluta i dane produktu do **CHECKOUT**. Wyłączenie powoduje wyslanie minimalnych parametrów. |
| **ADD_PAYMENT_INFO (Microsoft: Other)** | Tak | Uruchom etap płatności jako **Other**. Użyj go jako opcjonalnego sygnalu na koniec sciezki dla statystyk na żywo. |
| **purchase** | Tak | Wyślij **OffMicrosoftPurchases** z wartoscia zamówienia, waluta i liniami produktów. Stabilny identyfikator deduplikacji klienta sprawia, że odświeżanie jest bezpieczne. Użyj **Order lifecycle**, aby opóznic płatność do czasu płatności. |
| **SEARCH** | Tak | Rejestruj wyszukiwania w sklepach za pomocą wyszukiwanego hasla. |
| **ADD_TO_WISHLIST (Microsoft: Other)** | Tak | Nagraj dodatki do listy życzeń jako **Other**, gdy motyw udostępnia kompatybilne elementy sterujące. |
| **SIGN_UP (Signup)** | Tak | Wyślij **Signup** po utworzeniu konta klienta. |
| **LEAD / SUBSCRIBE (newsletter)** | Tak | Wyślij **Lead**, aby zapisać się na biuletyn. Wyłącz te opcje, jeśli inne narzędzie śledzi te sama konwersje. |
| **LEAD (legacy product interest)** | Nie | Zachowaj stare zachowanie potencjalnych klientów zainteresowanych produktem. Zostaw to, chyba że wymaga tego kampania historyczna; użycie go z `view_item` może spowodować napompowanie leadów. |
| **CONTACT** | Tak | Uruchamiaj po przeslaniu formularza kontaktowego, korzystajac z wykrywania rezerwowego serwera i przeglądarki. |
| **REFUND (Microsoft: Other)** | Tak | Uruchomiony, gdy zamówienie osiagnie skonfigurowany stań zwrotu lub anulowania. Microsoft otrzymuje go jako **Other** dla lokalnej korekty i statystyk. |
| **Rich product payloads (productId / items)** | Tak | Podaj identyfikatory produktów, ilości i ceny. Wyłączenie tej opcji pozostawia minimalne dane dotyczące wartości/waluty, z wyjątkiem sytuacji, gdy zdarzenia listy lub klikniecia wymagają identyfikatorów. Zachowaj te opcje, aby dopasować katalog. |
| **Add to cart CSS selector** | `.add-to-cart` | W trybie UET i trybie podwójnym zidentyfikuj przycisk strony produktu, gdy motyw nie uruchamia natywnego zdarzenia koszyka. |
| **Product price CSS selector** | `.current-price span` | W trybie UET i dualnym odczytaj widoczną cenę awaryjna. Zły selektor wysyła zero; w razie potrzeby połącz go z **Reformat price string**. |

W przypadku CAPI włącz **Advanced matching (email / phone)** i **Ghost collector (CAPI)**, aby uzyskać lepsze dopasowanie.

### 3.4 Identyfikatory katalogowe i Doktor ID katalogu

Upewnij się, że identyfikatory produktów związanych z wydarzeniami dokładnie odpowiadają Twojemu kanałowi Microsoft Merchant Center, kliknij **Save**, a następnie przejrzyj **Catalog ID Doctor**.

![Catalog IDs and Catalog ID Doctor](https://mypresta.eu/docs/images/docs/mybing-catalog.webp)

| Pole | Na poczatku | Co to robi |
|---|---|---|
| **Product identification** | `id_product` | Wybierz identyfikator produktu, identyfikator kombinacji lub identyfikator produktu plus separator i identyfikator kombinacji. Połączone identyfikatory pasują do kanałów zawierających listę wariantów. Inny format pliku danych uniemożliwia dopasowanie. |
| **Separator** | `-` | Oddzielne identyfikatory produktów i kombinacji w trybie laczonym. Produkt 12 i kombinacja 5 staja się `12-5`. Użyj tego samego separatora w pliku danych. |
| **Product ID prefix** | Puste według języka | Dodaj wartość specyficzna dla języka przed kazdym identyfikatorem tylko wtedy, gdy kanał również z niej korzysta. |
| **Product ID suffix** | Puste według języka | Dodaj wartość specyficzna dla języka po kazdym identyfikatorze tylko wtedy, gdy kanał tez z niej korzysta. |
| **Exclude free products** | Nie | Pomin produkty o zerowej cenie z koszyka i kupuj linie produktów oraz kalkulacje wartości. |
| **Force currency conversion** | Nie | Konwertuj wszystkie wartości pieniezne na jedna waluta docelowa. Włącz tylko wtedy, gdy waluta sklepu nie jest akceptowana przez Microsoft Advertising. |
| **Target currency** | Wybór zależny od sklepu | Wybierz waluta docelowa. Jest ignorowany, gdy wymuszona konwersja jest wylaczona. |
| **Reformat price string** | Nie | W trybie UET lub trybie podwójnym wyczysc sformatowane ceny motywów, zanim zostanie odczytane przez funkcje zastepcza „Dodaj do koszyka” CSS. Nie jest uzywany w trybie tylko CAPI. |

**Catalog ID Doctor** pokazuje wygenerowane przyklady z aktywnego produktu i kombinacji, najnowsze identyfikatory znalezione w danych zdarzeń oraz wskazówki dotyczące wybranego identyfikatora podstawowego, separatora, przedrostka i sufiksu. Jeśli zglasza **No active products found to validate catalog productId values**, aktywuj produkt i otwórz ponownie kartę.

### 3.5 Prywatność i zgoda

Najpierw skonfiguruj zewnętrzne źródło zgody. Moduł nie wyswietla banera cookie.

![Privacy and consent](https://mypresta.eu/docs/images/docs/mybing-privacy.webp)

| Pole | Na poczatku | Co to robi |
|---|---|---|
| **Require marketing / analytics consent** | Nie | Blokuj UET, CAPI i Ghost do czasu uzyskania zgody. Bez podlaczonego CMP śledzenie pozostaje ciche. |
| **Default consent state** | `auto` | `auto` czeka na zgoda na pliki cookie, TCF lub zdarzenie przeglądarki; `grant` pozwala natychmiast; `revoke` blokuje do czasu przyznania. Używaj `auto` z banerem, a `grant` tylko na odpowiedniej podstawie prawnej. |
| **IAB TCF 2.x (__tcfapi)** | Tak | Posluchaj certyfikowanego CMP. Cel 1 plus jeden z celów 2, 3 lub 4 odblokowuje reklamy i aktualizuje zgoda na przechowywanie reklam Microsoft UET. |
| **Include logged-in customer ID** | Nie | Dodaj identyfikator klienta PrestaShop do kontekstu logowania i diagnostyki jako opcjonalny sygnał zewnetrznego identyfikatora. Ujawnij to w polityce prywatności. |
| **Advanced matching (email / phone)** | Nie | Wyślij e-mail i dostępne zaszyfrowane pola e-mail/telefon, aby poprawić atrybucję UET i CAPI. Upewnij się, że obejmuje to polityka prywatności. Jest to zdecydowanie zalecane w przypadku CAPI. |
| **Ignore admin / employee traffic** | Tak | Pomin śledzenie witryny sklepowej po wykryciu sesji pracownika. |
| **Simple bot filter** | Nie | Pomin żądania, których identyfikacja przeglądarki przypomina bota lub robota. To jest heurystyka. |

W przypadku konfiguracji UE skonfiguruj CMP, użyj `auto`, włącz wymaganą zgoda i pozostaw wlaczona obsługę TCF, jeśli jest obsługiwana. Przetestuj opcje akceptacji i odrzucenia w prywatnej przegladarce. Przewodnik rozpoznaje popularne pliki cookie służące do celów marketingowych/statystycznych, własny plik cookie dotyczący zgody oraz wynik TCF. Wywołania zwrotne Cookiebot są obsługiwane bezpośrednio; inne CMP mogą wywołać zdarzenie zgody modułu.

### 3.6 Cykl życia zamówienia

Kontroluj, kiedy sprzedaż i zwroty są uwzgledniane w raportach konwersji.

![Order lifecycle](https://mypresta.eu/docs/images/docs/mybing-orders.webp)

| Pole | Na poczatku | Co to robi |
|---|---|---|
| **Purchase only when paid** | Nie | Opóznij zakup do momentu oplacenia stanu zamówienia. Włącz te opcje, gdy nieopłacony przelew bankowy lub zamówienia z pobraniem zawyzaja liczbe konwersji. |
| **Paid statuses** | Pusty | Wybierz opcjonalną biała listę płatnych stanów. Pozostaw puste, aby użyć wbudowanej płatnej flagi PrestaShop. Wypelniona lista jest używana, gdy włączone jest śledzenie tylko płatne. |
| **Refund / cancel statuses** | Pusty | Wybierz stany, które uruchamiaja zwrot pieniedzy. Puste wykorzystuje automatyczne wykrywanie na podstawie nazw statusów zawierających zwrot pieniedzy lub anulowanie. Zdarzenie Zwrot również musi być włączone. |

W przypadku opóznionej płatności włącz śledzenie tylko płatności, przenieś zamówienie testowe do stanu opłaconego i sprawdz, czy zakup pojawił się raz.

### 3.7 Reguły dotyczące wielu tagów

Używaj reguł, gdy sklep, język, kraj lub waluta wymagają różnych danych uwierzytelniajacych. Pierwsza pasująca aktywna reguła wygrywa w rosnącej kolejności **Position**. W przypadku braku dopasowania używane są poświadczenia globalne.

![Multi-tag rules](https://mypresta.eu/docs/images/docs/mybing-multitag.webp)

Lista **Active rules** zawiera **Tag ID**, źródło tokenu CAPI, **Shop**, **Language**, **Country**, **Currency**, **Active** i **Actions**. Kliknij **Delete** i potwierdź usunięcie reguły. Nie ma żadnych akcji edycji ani zbiorczych; utwórz ponownie regułę, aby ja zmienić.

| Pole | Na poczatku | Co to robi |
|---|---|---|
| **Tag ID (UET)** | Pusty | Ustaw tag UET dla pasujacego ruchu. Może być pusty tylko w przypadku zastapienia CAPI za pomocą tylko tokenu. |
| **Conversions API token** | Pusty | Zastap token globalny. Pusty dziedziczy token z **Tracking mode**. |
| **Shop** | **All shops** | Ogranicz reguła do jednego sklepu wielosklepowego lub wszystkich sklepów. |
| **Language** | **All languages** | Ogranicz to do jednego języka witryny sklepowej lub wszystkich języków. |
| **Country** | **All countries** | Ogranicz to do biezacego kontekstu kraju klienta. |
| **Currency** | **All currencies** | Ogranicz to do biezacej waluty. |
| **Active** | Tak | Włącz lub wyłącz reguła. Nieaktywne reguły są ignorowane. |
| **Position** | `0` | Ustaw kolejnosc oceny. Niższe liczby wygrywają, gdy pasuje kilka reguł. |

Kliknij **Add rule**. **Property rule saved** potwierdza sukces. Jeśli pojawi się **Could not save rule — provide a valid Tag ID and/or Conversions API token.**, popraw identyfikator znacznika lub podaj token.

### 3.8 Statystyki na żywo

Otwórz te zakladke w jednym oknie i przegladaj witryne sklepowa w innym. Wydarzenia pojawiaja się na 30-minutowej osi czasu czasu rzeczywistego.

![Live Statistics](https://mypresta.eu/docs/images/docs/mybing-live.webp)

**Recovery Radar** pokazuje zakupy bez dodania do koszyka, dodanie do koszyka bez wyswietlania szczególów produktu, zwroty w porównaniu z zakupami oraz odzyskiwanie CAPI/Ghost. Użyj pól wyboru zdarzeń, aby filtrować os czasu; PageView jest domyślnie ukryty. **Pause** zatrzymuje odpytywanie bez zatrzymywania śledzenia, a **Refresh** pobiera aktualne dane.

| Pole | Na poczatku | Co to robi |
|---|---|---|
| **Enable live dashboard** | Tak | Włącz lub wyłącz odpytywanie na osi czasu. Wyłączenie tej opcji wstrzymuje transmisje, podczas gdy śledzenie i rejestracja stanu zdrowia/radaru są kontynuowane. |
| **Also log PageView into the event database** | Nie | Dodaj halasliwe wiersze PageView do lokalnego dziennika. Nie kontroluje uruchamiania programu Microsoft PageView ani rejestrowania innych zdarzeń. Włącz tylko do debugowania. |
| **Keep events for (days)** | `14` | Usuń wiersze starsze niż ten wiek. Akceptowane wartości to 1–365; Typowe jest 7–30. |
| **Live poll interval (seconds)** | `5` | Ankieta co 2–60 sekund. Niższe wartości są szybsze, ale generują więcej zadań zaplecza. |

Użyj **Purge older than retention**, **Delete failed only** lub **Clear entire event log** do natychmiastowego czyszczenia. Wyczyszczenie wszystkiego wymaga potwierdzenia i nie można tego cofnac. **Export recent events (CSV)** pobiera najnowsze rekordy inne niż PageView.

### 3.9 Zdrowie i diagnostyka

Użyj tej karty po konfiguracji i zawsze, gdy brakuje konwersji.

![Health and diagnostics](https://mypresta.eu/docs/images/docs/mybing-health.webp)

**Health Score** sprawdza tryb audytu, dane logowania, aktualność kolejki, Ghost, PageView, zgoda, TCF, zakup, deduplikację, ostatnie błędy, format katalogu i jakość danych. Przeczytaj każdą nieudana kontrolę, a nie tylko etykietę **Excellent**, **Good**, **Fair** lub **Needs work**.

W przypadku CAPI zaplanuj **CAPI CRON URL** co 1–5 minut. Przejrzyj **Last CAPI flush**, przetworzone, wysłane, oczekujące, zakończone niepowodzeniem, sumy kolejek i wiersze starsze niż 10 minut.

**Data Quality Coach** szacuje pasujacy zasięg na podstawie ostatnich ladunków serwera lub próbki biezacego zakupu. Zawiera listę obecnych i brakujacych identyfikatorów, oczekiwanych wzrostów, srednich według zdarzeń i poprawek na poziomie sklepu. Ulepsz anonimowy identyfikator, `msclkid`, zaawansowane dopasowywanie poczty e-mail/telefonu i opcjonalny identyfikator klienta, jeśli to konieczne. Potwierdź ostateczna diagnostyka w Microsoft Advertising.

| Pole | Na poczatku | Co to robi |
|---|---|---|
| **Enable front debug inspector** | Nie | Pokaz pływającą nakładkę sklepu ze zdarzeniami, ładunkami, miejscem docelowym CAPI, stanem kolejki i bledami. Wyłącz go po przetestowaniu. Tymczasowo dołącz `?mybing_debug=1` do adresu URL witryny sklepowej, aby włączyć te funkcje bez zapisywania. |

Pod **Test & queue**:

- **Send test purchase** wysyła konwersje testowa; sprawdz Microsoft Advertising po 10–30 minutach.
- **Test CAPI token** sprawdza, czy identyfikator tagu i token są obecne.
- **Process CAPI queue** uruchamia te sama sciezke kolejki co CRON.

**Recent events log** pokazuje zdarzenie, identyfikator, kanał, status, odpowiedź/błąd, datę i wynik. Użyj **Re-send** do natychmiastowej próby lub **Re-add to queue** do nastepnego uruchomienia CRON.

**Recent queue rows** pokazuje szczególy zdarzenia, status, próby, ostatni błąd i czas aktualizacji. Użyj akcji dla poszczególnych wierszy lub **Re-send all failed now** i **Re-add all failed to queue**.

### 3.10 Aktualizacje

Sprawdz, czy jest nowsza wersja modułu tutaj.

![Updates](https://mypresta.eu/docs/images/docs/mybing-updates.webp)

| Pole | Na poczatku | Co to robi |
|---|---|---|
| **Manual Check** | Brak wyniku | Kliknij **Check Now**, aby jednokrotnie skontaktować się z usługa aktualizacji. Pokazuje **Module is up to date!** lub **New version available!**. |
| **Automatic Notifications** | Istniejące preferencje dotyczące udostepnianej aktualizacji | **Enabled** sprawdza mniej więcej co trzy dni i może ostrzec pracowników. **Disabled** pozostawia instrukcje zarządzania aktualizacjami. |
| **Product Page** | Wyświetlony link | Otwórz oficjalną stronę modułu, aby uzyskać informacje o wydaniu, dokumentację i uzyskać dostęp do pomocy technicznej. |

Po zmianie powiadomien kliknij **Save**.

## 4. Witryna sklepowa

Moduł nie dodaje widocznego bloku witryny sklepowej, formularza, przycisku ani strony konta klienta. Klienci korzystaja że zwyklych ekranów produktu, koszyka, kasy, rejestracji, biuletynu, kontaktu i potwierdzenia.

Strony produktów zawieraja ukryty błok danych produktu uzywany do śledzenia. Nie zmienia widocznego motywu. Po wlaczeniu debugowania widoczny staje się plywajacy inspektor; wyłącz go po przetestowaniu, ponieważ ujawnia szczególy śledzenia.

W przypadku CAPI skopiuj **CAPI CRON URL** z **Tracking mode** lub **Health & diagnostics** do harmonogramu hostingu i uruchamiaj go co 1–5 minut. Chroniony adres URL przetwarza zdarzenia w kolejce i przechowywanie. Nie publikuj go, ponieważ zawiera klucz dostępu.

Punkt końcowy danych witryny sklepowej jest wywoływany automatycznie w celu uzyskania zgody, identyfikatorów gości, koszyka, wyświetlenia strony, realizacji transakcji, kontaktu i działań debugowania. Nie konstruuj ani nie otwieraj go ręcznie.

| Widoczną wiadomosc | Co robić |
|---|---|
| Inspektor debugowania pokazuje odmowe zgody | Zaakceptuj zgoda marketingowa za pośrednictwem CMP lub napraw poręczenie CMP. |
| Inspektor debugowania pokazuje, że znajduje się w kolejce | Uruchom CRON lub **Process CAPI queue**, a następnie sprawdz **Health & diagnostics**. |
| Inspektor debugowania pokazuje błąd | Read the response in **Health & diagnostics**, correct credentials or connectivity, and click **Re-send**. |

## 5. Problemy

| Objaw | Przyczyna i działanie |
|---|---|
| Kreator pozostaje niekompletny | Zapisz prawidłowy tryb, identyfikator tagu i token, jeśli ma to zastosowanie; uruchom **Test** i zakończ **Done**. |
| Nie pojawiaja się zadne zdarzenia UET | Zapisz prawidłowy identyfikator tagu, włącz UET w trybie, włącz wydarzenie, przejrzyj zgoda i przetestuj w prywatnej sesji klienta. |
| **Missing Tag ID and/or Conversions API token** | Wprowadz oba w **Tracking mode**, zapisz i uruchom ponownie **Test CAPI token**. |
| Zdarzenia CAPI pozostają w kolejce | Zaplanuj **CAPI CRON URL** co 1–5 minut, kliknij raz **Process CAPI queue** i sprawdz **Last CAPI flush**. |
| Test CAPI lub ponowne wyslanie nie powiodlo się | Przeczytaj **Response / error**, popraw identyfikator znacznika/token/lacznosc, pozostaw puste pole zastapienia punktu koncowego, chyba że firma Microsoft je dostarczyla, i spróbuj ponownie. |
| śledzenie zatrzymuje się, gdy wymaganą jest zgoda | Skonfiguruj zewnętrzny CMP, użyj `auto`, podłącz TCF lub jego wywołania zwrotne, a następnie zaakceptuj zgodę marketingowa i przetestuj ponownie. |
| Produkty z katalogu nie pasują | Dopasuj **Product identification**, separator, przedrostek i przyrostek do źródła danych i przejrzyj **Catalog ID Doctor**. |
| Zakupy pojawiaja się przed dokonaniem płatności | Włącz **Purchase only when paid** i opcjonalnie wybierz dokładnie płatne stany. |
| Zamówienia oplacone nie tworza zakupu | Włącz **purchase** i upewnij się, że stań zamówienia jest oplacony lub uwzgledniony w **Paid statuses**. |
| Zwroty nie pojawiaja się | Włącz opcje Zwrot pieniedzy i wybierz wlasciwy **Refund / cancel statuses**. |
| Twoje testy są ignorowane | Użyj prywatnej przeglądarki bez sesji pracownika lub tymczasowo wyłącz **Ignore admin / employee traffic**. |
| Brak ruchu testowego podobnego do bota | Wyłącz **Simple bot filter** na potrzeby testu, a następnie przywróc go w razie potrzeby. |
| Brak dodatku do koszyka UET | Zaktualizuj selektory CSS przycisku i ceny, aby pasowaly do motywu. |
| Wartość dodana do koszyka wynosi zero lub jest znieksztalcona | Popraw selektor cen i w razie potrzeby włącz **Reformat price string**. |
| Krok płatności Inne zdarzenie jest nieobecne, chociaż jego przelacznik ma wartość Tak | Motyw lub etap płatności nie uruchomil sciezki modułu. Potraktuj ten sygnał jako opcjonalny i zweryfikuj pozostały lejek. |
| Statystyki na żywo czekaja na wydarzenia | Włącz panel, wznów go, wyczysc filtry, kliknij **Refresh** i przegladaj witryne sklepowa jako klient. |
| PageView dociera do Microsoftu, ale jest nieobecny lokalnie | Włącz tymczasowo lokalne rejestrowanie PageView; jest domyślnie wyłączony. |
| Użyto nieprawidłowego uwierzytelnienia wielotagowego | Usuń/utwórz ponownie nakładające się reguły i nadaj najbardziej szczególowej najniższą pozycję. |
| Nie można zapisać reguły | Podaj prawidłowy identyfikator znacznika i/lub token, a następnie kliknij **Add rule**. |
| Health ostrzega o jakosci danych | Postepuj zgodnie z **Highest-impact fixes**, włącz dopasowywanie Ghost i Advanced, jeśli jest to zgodne z prawem, i zbieraj prawidlowe dane telefonu przy kasie. |
| Ekran modułu wyglada na nieaktualny | Wyczysc pamięć podręczna pod **Advanced Parameters > Performance** i zaladuj ponownie. |

## 6. Informacje dla programistów

### 6.1 Architektura

Nazwa techniczna to `mybing`, wersja `1.4.0`. Glówna klasa jest `mybing extends Module`; nazwa listy to **Microsoft Advertising UET / Conversions API**, autor `MyPresta.eu`, kategoria `front_office_features`.

`MybingTrackerFactory` wybiera `MybingUetTracker`, `MybingCapiTracker` lub `MybingHybridTracker`. `MybingEvents` buduje wydarzenia; `MybingEventId` generuje i utrwala identyfikatory deduplikacji. `MybingProductIdResolver`, `MybingCurrencyHelper` i `MybingUserData` normalizuja dane katalogowe, pieniezne i tozsamosciowe. `MybingCapiClient` tworzy żądania, wysyła je i zarzadza ponownymi próbami. Diagnostyka zasilania `MybingLiveStats`, `MybingHealthScore`, `MybingDataQualityCoach` i `MybingCatalogDoctor`.

Tryb podwójny udostępnia identyfikator zdarzenia pomiędzy kanałami przeglądarki i serwera. Domyślny punkt końcowy to `https://capi.uet.microsoft.com/v1/{tagId}/events`. Każde wywołanie CRON przetwarza do 50 wierszy kolejki i stosuje przechowywanie.

### 6.2 Pliki i klasy

| Plik lub klasa | Odpowiedzialnosc |
|---|---|
| `mybing.php` | Zainstaluj/odinstaluj, ustawienia domyslne, formularze, akcje, CRON, konfiguracja frontowa i hooki. |
| `classes/MybingTrackerInterface.php` | Umowa na śledzenie. |
| `classes/MybingTrackerFactory.php` | Tryb i rozdzielczosc przelaczania zdarzeń. |
| `classes/MybingUetTracker.php` | Ladunki przeglądarki i lokalne rekordy UET. |
| `classes/MybingCapiTracker.php` | Dostawa serwera i kolejkowanie. |
| `classes/MybingHybridTracker.php` | Podwójne wyjscie i deduplikacja. |
| `classes/MybingCapiClient.php` | Ladunki, cURL, odpowiedzi, kolejka, ponowne próby i podsumowania opróżniania. |
| `classes/MybingEvents.php` | Realizacja wydarzen handlowych. |
| `classes/MybingEventMap.php` | Mapa zdarzeń wewnetrzna do firmy Microsoft. |
| `classes/MybingEventId.php` | Identyfikatory zdarzeń, deduplikacja i naprawa tabeli zdarzeń. |
| `classes/MybingUserData.php` | Identyfikatory kliknięć/gości, dane klientów, normalizacja i haszowanie. |
| `classes/MybingConsent.php` | Wymóg zgody, ustawienia domyslne, pliki cookie i TCF. |
| `classes/MybingPropertyRules.php` | Schemat reguły kontekstu, dopasowanie i rozpoznawanie poswiadczen. |
| `classes/MybingProductIdResolver.php` | Generowanie identyfikatora katalogu. |
| `classes/MybingCurrencyHelper.php` | Kontekst walutowy i konwersja. |
| `classes/MybingLiveStats.php` | Kanał, podsumowania, radar, przechowywanie i czyszczenie. |
| `classes/MybingHealthScore.php` | Wazone kontrolę stanu i diagnostyka kolejek. |
| `classes/MybingDataQualityCoach.php` | Szacunki zasiegu tozsamosci. |
| `classes/MybingCatalogDoctor.php` | Przykladowe i najnowsze identyfikatory produktów. |
| `controllers/admin/AdminMybingAjaxController.php` | Uwierzytelniony most zaplecza JSON. |
| `controllers/front/ajax.php` | Punkt końcowy JSON śledzenia chroniony tokenem. |
| `controllers/front/cron.php` | Punkt końcowy JSON kolejki chroniony kluczem. |
| `views/js/mybing.js` | Glówne wiazania przednie i wysyłka. |
| `views/js/mybing-tcf.js` | Most zgody TCF. |
| `views/js/mybing-ghost.js` | Synchronizacja identyfikatora gościa/kliku. |
| `views/js/mybing-debug.js` | Inspektor frontowy. |
| `views/js/mybing-admin.js`, `mybing-wizard.js`, `mybing-live.js` | Formularze zaplecza, kreator i pulpit nawigacyjny na żywo. |
| `views/templates/hook/header.tpl` | UET, zgoda, dopasowanie, odsłona strony, zdarzenia, skrypt i synchronizacja ID. |
| `views/templates/hook/product-details.tpl` | Ukryty produkt JSON. |
| `views/templates/hook/displayOrderConfirmation.tpl` | Dane wyjściowe zakupu przeglądarki. |
| `views/templates/hook/capi-pageview.tpl`, `ghost.tpl`, `debug.tpl` | Widok strony CAPI, Ghost i dane wyjściowe inspektora. |
| `views/templates/hook/payment.tpl` | Szablon zdarzenia płatności nie zostal wywolany przez procedure obsługi haka w wersji 1.4.0. |
| `sql/install.php`, `sql/uninstall.php` | Twórz/naprawiaj i upuszczaj niestandardowe tabele. |
| `lib/updateChecker.php` | Reczne i okresowe kontrolę aktualizacji. |

### 6.3 Kontrolery

`AdminMybingAjaxController extends ModuleAdminController` jest instalowany jako ukrytą zakładka `AdminMybingAjax` z rodzicem `-1`. Wymaga pracownika i emituje JSON. Akcje: `liveFeed`, `liveRadar`, `liveClear`, `wizardSave`, `wizardTest`, `wizardComplete`, `wizardReset`, `dqReport`/`emqReport` i `exportCsv`.

`MybingAjaxModuleFrontController extends ModuleFrontController` obsluguje tylko SSL i JSON. Akceptuje bezpieczny klucz lub wygenerowany token frontowy. Akcje: `ghost`, `consent`, `addToCart`, `removeFromCart`, `wishlist`, `selectItem`, `contact`, `beginCheckout`, `recalculate`, `pageview`, `ping` i tylko debugowanie `inspect`. Błędy obejmuja `invalid_token`, `disabled`, `empty_cart`, `invalid_currency`, `disabled_or_consent`, `debug_off` i `unknown_action`.

`MybingCronModuleFrontController` akceptuje `key` lub `secure_key`, zwraca JSON, emituje HTTP 403 z `access_denied` w przypadku nieprawidłowego dostępu i wywołuje `runCapiCron()`.

`controllers/front/index.php` wysyła tylko naglówki bez pamięci podręcznej i przekierowuje w górę.

### 6.4 Haki

| Zarejestrowany hak | Wdrożenie |
|---|---|
| `displayHeader` | Filtruje ruch; wysyła sygnały dotyczące strony, listy, produktu, kasy, wyszukiwania, kontaktu i biuletynu; renderuje dane wyjściowe UET/Ghost/CAPI. |
| `displayOrderConfirmation` | Rozwiazuje porzadek, śledzi dozwolone zakupy, renderuje dane wyjściowe przeglądarki. |
| `actionValidateOrder` | śledzi zakup w momencie jego utworzenia, chyba że opcja „tylko platna” go opózni. |
| `actionOrderStatusPostUpdate` | śledzi opóźnione płatne zakupy i zwroty/anulowanie przejsc. |
| `actionCustomerAccountAdd` | śledzi rejestracje i przechowuje dane wyjściowe przeglądarki dla następnej strony. |
| `actionFrontControllerSetMedia` | Dodaje konfiguracja frontowa oraz zasoby glówne, TCF, Ghost i debugowanie. |
| `displayPaymentTop` | Zarejestrowano, ale `hookDisplayPaymentTop()` nie jest zaimplementowany w wersji 1.4.0. |
| `displayFooter` | Renderuje inspektora debugowania i ładowanie kolejki, gdy jest włączone. |
| `actionCartUpdateQuantityBefore`, `actionBeforeCartUpdateQty` | Śledź zmiany ilości koszyka serwera; ten drugi deleguje do pierwszego. |
| `actionObjectProductInCartDeleteBefore`, `actionObjectProductInCartDeleteAfter` | Zrób migawkę, a następnie śledź usunięcie całego koszyka. |
| `displayProductAdditionalInfo` | Renderuje ukryte szczególy produktu. |
| `actionNewsletterRegistrationAfter` | śledzi leady biuletynu. |
| `displayContactContent` | Dodaje ukryty znacznik kontaktu. |

Nie ma niestandardowych metod `enable()` ani `disable()`.

### 6.5 Baza danych

Rzeczywisty prefiks PrestaShop zastepuje `ps_`.

| Tabela | Spis tresci |
|---|---|
| `ps_mybing_events` | Nazwa/identyfikator zdarzenia, zamówienie/koszyk/sklep, kanał, ładunek, status, kod HTTP, odpowiedź, data, indeksy wyszukiwania i unikalny klucz deduplikacji zdarzenia/nazwy/sklepu. |
| `ps_mybing_properties` | Tag, token, selektory sklepu/języka/kraju/waluty, aktywne, pozycja i data. |
| `ps_mybing_queue` | Ładunek, próby, status, ostatni błąd, daty utworzenia/aktualizacji. |

Jeśli `utf8mb4` zakonczy się niepowodzeniem, instalacja zostanie ponowiona za pomocą `utf8`. `MybingPropertyRules::ensureSchema()` może dodać `tag_id` i `access_token` po otwarciu konfiguracji i migrować starszy token odświeżania. Programowy schemat zdarzeń dodaje swój unikalny indeks. Odinstalowanie powoduje usunięcie wszystkich trzech tabel.

### 6.6 Klucze konfiguracyjne

| Klucze | Wartości domyslne i cel |
|---|---|
| `MYBING_MODE` | Pusty; tryb śledzenia. |
| `MYBING_TAG_ID`, `MYBING_CAPI_TOKEN`, `MYBING_CAPI_ENDPOINT` | Pusty; globalne dane uwierzytelniające/miejsce docelowe. |
| `MYBING_MSCLKID_DAYS`, `MYBING_ID_SYNC` | `90`, `1`; Click-ID life i ID Sync. |
| `MYBING_PAGEVIEW`, `MYBING_PURCHASE`, `MYBING_PURCHASE_PAID_ONLY` | `1`, `1`, `0`. |
| `MYBING_LEAD`, `MYBING_LEAD_N`, `MYBING_INITIATE`, `MYBING_INITIATE_D` | `0`, `1`, `1`, `1`. |
| `MYBING_SEARCH`, `MYBING_ADDTOCART`, `MYBING_REMOVECART`, `MYBING_WISHLIST` | Wszystkie `1`. |
| `MYBING_ADDPAYMENT`, `MYBING_CONTACT`, `MYBING_REFUND` | Wszystkie `1`. |
| `MYBING_DPA`, `MYBING_VCONTENT`, `MYBING_VIEW_ITEM_LIST`, `MYBING_REG` | Wszystkie `1`. |
| `MYBING_ATTRID`, `MYBING_SEPSIGN`, `MYBING_PREFIX`, `MYBING_SUFIX` | `0`, `-`, puste dla kazdego języka, puste dla kazdego języka. |
| `MYBING_EXFREE`, `MYBING_ATC_B`, `MYBING_ATC_PPP`, `MYBING_PREPRICE` | `0`, `.add-to-cart`, `.current-price span`, `0`. |
| `MYBING_CONCURR`, `MYBING_CURRSELECT` | `0`, `0`. |
| `MYBING_CONSENT_REQUIRED`, `MYBING_CONSENT_MODE`, `MYBING_TCF` | `0`, `auto`, `1`. |
| `MYBING_GHOST`, `MYBING_USER_ID`, `MYBING_ENHANCED_CONV` | `1`, `0`, `0`. |
| `MYBING_IGNORE_ADMIN`, `MYBING_BOT_FILTER`, `MYBING_DEBUG` | `1`, `0`, `0`. |
| `MYBING_PAID_STATUSES`, `MYBING_REFUND_STATUSES` | Puste identyfikatory stanów oddzielone przecinkami. |
| `MYBING_STATS_ENABLED`, `MYBING_STATS_RETENTION`, `MYBING_STATS_POLL`, `MYBING_STATS_LOG_PV` | `1`, `14`, `5`, `0`. |
| `MYBING_WIZARD_DONE`, `MYBING_WIZARD_REDO` | `0`, `0`. |
| `MYBING_INSTALL_SQL_WARN`, `MYBING_INSTALL_ERROR` | Diagnostyka instalacji w czasie wykonywania. |
| `MYBING_LAST_FLUSH` | Podsumowanie opróżniania JSON środowiska wykonawczego; nie na liście kluczy deinstalacyjnych. |

Instalacja/odinstalowanie usuwa również starsze `MYBING_CAPI_AUTH_CLIENT_ID`, `MYBING_CAPI_AUTH_CLIENT_SECRET`, `MYBING_CAPI_AUTH_REFRESH_TOKEN`, `MYBING_CAPI_AUTH_ACCESS_TOKEN`, `MYBING_CAPI_AUTH_ACCESS_EXPIRES`, `MYBING_PROFILE_ID`, `MYBING_CAPI_REGION`, `MYBING_CAPI_COUNTRY`, `MYBING_ATC_PC`, `MYBING_ATC_PP`, `MYBING_LINKER_DOMAINS` i `MYBING_ADS_ID`. `MYBING_DEBUG_MODE` jest usuwany podczas instalacji, ale nie ma go na liście dezinstalacji.

Aktualizator wykorzystuje `mypresta_updates`, `update_mybing` i `updatev_mybing`; mogą one pozostać po odinstalowaniu. `mypresta_updates` jest wspóldzielony.

### 6.7 Odinstaluj, tłumaczenia i rozszerzenia

`uninstall()` usuwa ukrytą kartę, usuwa wszystkie tabele modułów, usuwa wartości `getConfigurationKeys()` i diagnostykę instalacji, a następnie wywołuje `parent::uninstall()`. Nie usuwa kluczy aktualizacyjnych ani `MYBING_LAST_FLUSH`.

Nie ma żadnych zastąpień PrestaShop. Tłumaczenia są dostępne w `translations/{iso}.php`; większość ciągów interfejsu użytkownika używa `$this->l()` lub Smarty `{l}`, podczas gdy nazwy zdarzeń i niektóre diagnostyki klas pozostają w języku angielskim.

Motywy mogą zmieniać położenie obslugiwanych haków i stylizować inspektora, ale błok produktu jest celowo ukryty. Zachowaj atrybuty danych i skrypty podczas zastepowania szablonów haków. Niestandardowy CMP może wysłać `mybing.consent` z przyznaniem `1` lub `0` lub dostarczyć sygnał rozpoznawany przez `MybingConsent`.

## 7. Pomoc

Otwórz stronę modułu: https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html

Zaloguj się na swoje konto klienta na mypresta.eu, otwórz stronę kontaktową i wybierz **Support for paid modules**. Wymagane jest logowanie; następnie wybierz ten moduł z historii zakupów i podaj tryb śledzenia, widoczny błąd i wynik diagnostyki.
