---
title: Ban IP Pro - dokumentacja i instrukcja sprzedawcy
sidebar:
  label: Ban IP Pro - dokumentacja i instrukcja sprzedawcy
description: Instrukcja konfiguracji i rozwiązywania problemów dla sklepów, które mają już Ban IP Pro.
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Block IP address Pro na MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/block-ip-address-pro/)
>
> ---


## 1. Wymagania

Ban IP Pro działa wewnątrz PrestaShop. Nie potrzebuje innego modułu.

- PrestaShop od 1.7.1.0 do PrestaShop 9.
- PHP 7.1 albo nowszy i co najmniej taka wersja PHP, jakiej wymaga ta wersja PrestaShop. Instalacja staje na PHP starszym niż 7.1.
- Ustalanie kraju i blokada krajów potrzebują PHP 7.2 albo nowszego oraz pliku krajów MaxMind, który wgrywasz sam. Bany, biała lista, sprawdzanie logowań i limit żądań działają bez tego pliku, także na PHP 7.1.
- Żadne dodatkowe rozszerzenie PHP nie jest wymagane. Sprawdzenie aktualizacji używa cURL, gdy serwer go ma. Gdy cURL nie ma, sprawdzenie czyta adres tylko wtedy, gdy serwer pozwala czytać zdalne adresy.
- Żaden inny moduł nie jest wymagany. Konto MaxMind jest potrzebne tylko wtedy, gdy chcesz plik krajów. Moduł sam tego pliku nie pobiera.
- Import przyjmuje do 5000 linii i plik do 2 MB. Długa lista reguł jest czytana z pliku cache przy każdej wizycie, więc bardzo duża lista powiększa ten plik. Po dużym imporcie użyj **Przebuduj cache** w **Narzędziach**, gdy liczniki wyglądają na nieodświeżone.

## 2. Instalacja

1. W zapleczu otwórz **Moduły**, potem **Menedżer modułów**.
2. Wgraj zip modułu i kliknij **Instaluj**.
3. Otwórz **Konfiguruj** przy **Ban IP pro**. Strona otwiera się na **Pulpit**. Na pasku są też **Statystyki**, **Zachowanie**, **Automatyzacja**, **Sieć**, **Narzędzia** i **Aktualizacje**.
4. W lewym menu pojawia się **Banowanie IP** w **Zaawansowane**. To lista reguł. **Zarządzaj regułami** na stronie modułu prowadzi do tej samej listy.

Instalacja zapisuje pusty cache reguł. Nie czyści cache PrestaShop. Gdy po aktualizacji brakuje pozycji menu, otwórz **Konfiguruj** raz. Strona uzupełnia tabele modułu. Gdy to się nie uda, widać **Nie udało się zaktualizować bazy modułu.**

Wyłączenie robisz przełącznikiem w **Menedżerze modułów**. Sprawdzanie staje. Reguły, logi i ustawienia zostają. Włącz moduł ponownie, a te same reguły wracają do użycia. Moduł nie ma własnego osobnego przycisku włączania i wyłączania.

Usunięcie: kliknij **Odinstaluj** i potwierdź. Odinstalowanie zabiera pozycję **Banowanie IP** i odłącza sprawdzanie. Reguły, log blokad, sumy dzienne, liczniki nieudanych logowań, lista działań pracowników i ustawienia zostają w bazie. Wgrany plik krajów zostaje w katalogu modułu. Ponowna instalacja zachowuje te reguły i uzupełnia tylko puste ustawienia.

## 3. Konfiguracja i praca w zapleczu

Gość otwiera sklep. Zanim powstanie strona, moduł czyta jego adres IP. Reguła **Pozwól** wygrywa z banem. Gdy ban pasuje do sklepu, kraj gościa jest na liście blokady, gość otworzył ścieżkę skanera albo adres przekroczył limit żądań, gość dostaje stronę blokady albo przekierowanie, które ustawisz. Blokada trafia do logu. Praca sprzedawcy zaczyna się na **Pulpicie** albo w **Zaawansowane**, **Banowanie IP**. Dodajesz regułę, importujesz listę albo zostawiasz **Automatyzację**, żeby tworzyła bany. Ban może wygasnąć. Przy pierwszym żądaniu każdego dnia wygasłe reguły są wyłączane, a stare linie logu usuwane. Ścieżka kończy się, gdy gość jest zablokowany, przekierowany albo przepuszczony.

Otwórz **Moduły**, **Menedżer modułów**, **Ban IP pro**, **Konfiguruj**.

### 3.1 Pulpit

![Pulpit](https://mypresta.eu/docs/images/docs/banippro-configure-dashboard.webp)

Ekran jest po angielsku. W tej instrukcji ta część nazywa się **Pulpit**.

**Pulpit** to pierwsza zakładka. **Zarządzaj regułami** otwiera listę reguł.

Siedem liczników tylko pokazuje liczby. Niczego nie zapisują.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Zarządzaj regułami** | przycisk | Otwiera **Banowanie IP** w **Zaawansowane**. |
| **Aktywne bany** | 0 | Bany, które są włączone. Reguły **Pozwól** nie wchodzą do tej liczby. |
| **Zablokowane dziś** | 0 | Zablokowane żądania od północy, z sum dziennych. |
| **Zablokowane w 7 dni** | 0 | Zablokowane żądania z ostatnich 7 dni, łącznie z dzisiaj. |
| **Zablokowane w 30 dni** | 0 | Zablokowane żądania z ostatnich 30 dni, łącznie z dzisiaj. |
| **Unikalne IP dziś** | 0 | Różne adresy IP w dzisiejszym logu blokad. |
| **Wygasają w 48 godzin** | 0 | Aktywne bany, których koniec mieści się w najbliższych 48 godzinach. |
| **Aktywne auto-bany** | 0 | Aktywne bany z powodu nieudanego logowania, ścieżki skanera albo limitu żądań. |

**Zablokowane żądania** to wykres ostatnich 30 dni. Czyta sumy dzienne. Niczego nie zapisuje.

**Ostatnie blokady** pokazują najnowsze zablokowane żądania: datę, adres IP, kraj, ścieżkę i powód. Kraj zostaje pusty, dopóki nie wgrasz pliku krajów w **Sieć**. Pusta lista mówi **Nie było jeszcze blokad.**

**Twój aktualny adres IP** pokazuje adres widziany przez to zaplecze. **Dodaj do białej listy** zapisuje ten adres jako regułę **Pozwól** dla sklepu i panelu. Strona mówi wtedy **Twój aktualny adres IP jest na białej liście.** Gdy adresu nie da się odczytać, widać **Nie udało się wykryć Twojego aktualnego adresu IP.** Gdy wiersza nie da się zapisać, widać **Nie udało się dodać adresu do białej listy.**

**Stan modułu** ma cztery linie.

| Linia | Na starcie | Co robi |
|---|---|---|
| **Hook witryny** | **Zarejestrowany** po zwykłej instalacji | **Zarejestrowany** oznacza, że sklep wykonuje sprawdzenie. **Brak** oznacza, że sprawdzenie nie jest podpięte. Zainstaluj moduł ponownie albo otwórz **Konfiguruj** po aktualizacji. |
| **Reguły w cache** | 0 | Ile aktywnych reguł cache przyjął. |
| **Nieczytelne reguły** | 0 | Aktywne wiersze, których cache nie odczytał jako adresu. |
| PHP i PrestaShop | wersje na tym serwerze | Widać je, żeby porównać z wymaganiami. |

**Szybki ban** zapisuje jeden ban. Zasięg bierze z **Domyślny zasięg nowych banów** w **Zachowanie**. Ban dodany tutaj nie wysyła e-maila z alertem.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Adres IP** | puste | Jeden adres, wzorzec taki jak `192.168.1.*`, sieć taka jak `10.0.0.0/8` albo zakres taki jak `192.168.1.10-192.168.1.20`. |
| **Powód** | **Ręcznie** | **Ręcznie**, **Oszustwo**, **Spam**, **Skaner**, **Chargeback** albo **Konkurencja**. Statystyki używają tej etykiety. |
| **Czas** | **Na stałe** | **1 godzina**, **24 godziny**, **7 dni**, **30 dni** albo **Na stałe**, aż usuniesz regułę. |
| **Komentarz** | pusty | Prywatna notatka. Gość jej nie widzi. |
| **Potwierdzam blokadę własnego adresu IP** | wyłączone | Wymagane tylko wtedy, gdy ban objąłby adres, z którego jesteś w panelu, a zasięg obejmuje panel. |
| **Zbanuj ten adres** | przycisk | Zapisuje ban i pokazuje **Adres został zbanowany.** |

**Sprawdź adres** niczego nie tworzy i niczego nie kasuje.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Adres IP** | puste | Adres, który chcesz sprawdzić. |
| **Sprawdź** | przycisk | Pokazuje wynik dla sklepu, wynik dla panelu i kraj. |
| **Witryna sklepu** | ukryte do sprawdzenia | **Brak pasującej reguły.**, **Dozwolone przez regułę #…** albo **Zablokowane przez regułę #…**. |
| **Panel administracyjny** | ukryte do sprawdzenia | Te same trzy wyniki dla panelu. |
| Dopisek pod linią panelu | gdy ochrona jest wyłączona | **Ochrona panelu jest wyłączona, więc bany panelu nie są egzekwowane.** |
| **Kraj** | **Nieznany**, gdy nie ma pliku | Kod kraju oraz **Zablokowane regułą kraju**, gdy ten kraj jest na liście blokady. |

**Ostatnie działania w panelu** pokazują ostatnie działania pracowników, na przykład utworzenie, import, białą listę, odblokowanie i przebudowę cache. Pusta lista mówi **Nie było jeszcze działań w panelu.**

### 3.2 Statystyki

![Statystyki](https://mypresta.eu/docs/images/docs/banippro-configure-stats.webp)

Ekran jest po angielsku. W tej instrukcji ta część nazywa się **Statystyki**.

**Statystyki** czytają log blokad. **24h**, **7 dni** i **30 dni** przeładowują stronę dla tego okresu. Przy pierwszym wejściu wybrany jest okres **30 dni**.

| Pole | Na starcie | Co robi |
|---|---|---|
| **24h** | przycisk | Ostatnie 24 godziny. Wykres ma jeden punkt na godzinę. |
| **7 dni** | przycisk | Ostatnie 7 dni, łącznie z dzisiaj. Wykres ma jeden punkt na dzień. |
| **30 dni** | przycisk, wybrany na starcie | Ostatnie 30 dni, łącznie z dzisiaj. |
| **Eksport CSV** | przycisk | Pobiera `banippro-hits.csv` dla okresu na ekranie. Nie zmienia reguł. |
| **Od** | pierwszy dzień otwartego okresu | Używane z **Do** i **Zastosuj**. |
| **Do** | dzisiaj | Używane z **Od** i **Zastosuj**. Gdy **Od** jest późniejsze niż **Do**, dni zamieniają się miejscami. |
| **Zastosuj** | przycisk | Przeładowuje zakładkę dla tych dni. Niczego nie zapisuje. |
| **Zablokowane żądania** | 0 | Ile blokad wpada w ten okres. |
| **Unikalne IP** | 0 | Ile różnych adresów zablokowano w tym okresie. |

Wykres **Zablokowane żądania** podąża za przyciskami powyżej. Pod nim:

| Blok | Co pokazuje |
|---|---|
| **Najczęstsze adresy IP** | Wykres słupkowy 10 adresów z największą liczbą blokad w okresie. |
| **Najczęstsze ścieżki** | 10 ścieżek blokowanych najczęściej, z liczbą. |
| **Najczęstsze powody** | 10 powodów na pasujących regułach, z liczbą. |
| **Najczęstsze kraje** | 10 kodów krajów, z liczbą. Puste, dopóki nie ma pliku krajów. |
| **Log blokad** | Data, adres IP, kraj, ścieżka, adres reguły i powód. Do 100 wierszy. |

Puste zestawienie mówi **Brak danych w tym okresie.** Pusty log mówi **Brak zablokowanych żądań w tym okresie.**

Sumy dzienne za wykresem na pulpicie zostają, gdy skrócisz **Przechowuj logi przez dni**. To ustawienie kasuje log linia po linii i listę działań pracowników. Nie kasuje sum dziennych.

### 3.3 Zachowanie

![Zachowanie](https://mypresta.eu/docs/images/docs/banippro-configure-behavior.webp)

Ekran jest po angielsku. W tej instrukcji ta część nazywa się **Zachowanie**.

Kliknij **Zapisz**. Strona pokazuje **Ustawienia zapisane**.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Wiadomość dla zablokowanych** | **You are blocked** po angielsku. Sklep po polsku, hiszpańsku i portugalsku dostaje też zdanie w tym języku. Każdy inny język dostaje zdanie angielskie. Po polsku startowe zdanie to **Dostęp został zablokowany.** | Tekst na stronie blokady. Uzupełnij każdy język sklepu. Gość widzi zdanie dla języka strony. |
| **Przekieruj zablokowanych** | **Nie** | **Tak** wysyła zablokowanych na **Adres przekierowania** zamiast wiadomości. **Nie** zostawia stronę blokady. |
| **Adres przekierowania** | pusty | Pełny link `http` albo `https`. Pomijany, gdy przełącznik powyżej jest **Nie**. Zły link wraca przełącznik na **Nie** i pokazuje **Podaj prawidłowy adres http lub https do przekierowania.** |
| **Domyślny zasięg nowych banów** | **Witryna sklepu** | Używany przez **Szybki ban** i **Importuj**, gdy te ekrany nie pytają o zasięg. **Witryna sklepu** to sklep. **Panel administracyjny** to ten panel. **Witryna i panel** to oba. |
| **Chroń panel administracyjny** | **Nie** | **Tak** egzekwuje bany także w tym panelu. Zapis odrzuca **Tak**, dopóki Twój aktualny adres IP nie jest na białej liście, i pokazuje **Dodaj swój aktualny adres IP do białej listy, zanim włączysz ochronę panelu.** Przełącznik zostaje **Nie**. |

Formularz pokazuje też tę informację: **Ochrona panelu pozostaje wyłączona, dopóki Twój aktualny adres IP nie jest na białej liście. Reguły domyślnie dotyczą witryny sklepu.**

### 3.4 Automatyzacja

![Automatyzacja](https://mypresta.eu/docs/images/docs/banippro-configure-automation.webp)

Ekran jest po angielsku. W tej instrukcji ta część nazywa się **Automatyzacja**.

Kliknij **Zapisz**. Strona pokazuje **Ustawienia zapisane**. Automatyczne bany dotyczą witryny sklepu, we wszystkich sklepach tej instalacji. Nie włączają **Chroń panel administracyjny**. Adres, który już pasuje do reguły **Pozwól**, nie jest banowany. Adres, który już ma aktywny ban, zostaje bez zmian.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Blokuj znane ścieżki skanerów** | **Tak** | **Tak** banuje gościa sklepu, który otworzy ścieżkę z listy poniżej. Folder panelu nigdy nie jest tak banowany. **Nie** wyłącza to sprawdzenie. |
| **Czas bana za skanowanie (godziny)** | 24 | Jak długo trwa ten ban. 24 to jedna doba. 0 zostawia go, aż go usuniesz. |
| **Ścieżki skanerów** | `/.env`, `/wp-login.php`, `/wp-admin`, `/xmlrpc.php`, `/vendor/phpunit`, `/phpmyadmin`, `/.git/`, `/boaform`, `/cgi-bin/`, jedna w linii | Żądanie, którego ścieżka zawiera jedną z tych linii, jest banowane od razu. Pusta lista przy zapisie wraca do tej listy domyślnej. Linia składająca się tylko z `/` oraz linia będąca folderem panelu są odrzucane. |
| **Banuj klientów po nieudanych logowaniach** | **Nie** | **Tak** liczy złe hasła klienta. Udane logowanie klienta zeruje licznik. |
| **Banuj pracowników po nieudanych logowaniach** | **Nie** | Ten sam licznik przy formularzu logowania pracownika. Zanim to włączysz, dodaj swój adres IP do białej listy. Ban i tak dotyczy witryny sklepu, nie panelu, chyba że ten adres obejmuje też ban, którego zasięg zawiera panel. |
| **Nieudane logowania przed banem** | 5 | Przy 5 kolejna pomyłka w oknie tworzy ban. Najmniejsza zapisana wartość to 1. |
| **Okno nieudanych logowań (minuty)** | 15 | Starsze pomyłki są zapominane. Najmniejsza zapisana wartość to 1. |
| **Czas bana za logowanie (godziny)** | 24 | Jak długo trwa ban za logowanie. 0 zostawia go, aż go usuniesz. |
| **Ogranicz liczbę żądań z adresu IP** | **Nie** | **Tak** liczy żądania stron sklepu. Obrazki i inne pliki, które nie wchodzą do PrestaShop, nie są liczone. Zostaw **Nie** przy zwykłym ruchu. W ruchliwym sklepie niski limit zbanuje prawdziwych klientów. |
| **Dozwolone żądania w oknie** | 120 | Ile żądań stron jeden adres IP może wykonać w oknie. Najmniejsza zapisana wartość to 1. |
| **Okno limitu (minuty)** | 1 | Długość tego okna. 1 oznacza, że limit powyżej liczy się na minutę. |
| **Czas bana za limit (minuty)** | 15 | Jak długo trwa ban po przekroczeniu limitu. Najmniejsza zapisana wartość to 1. |
| **Wyślij e-mail, gdy powstanie automatyczny ban** | **Nie** | **Tak** wysyła jeden e-mail, gdy moduł sam utworzy ban. Bany dodane ręcznie go nie wysyłają. Wychodzi co najwyżej jeden e-mail na godzinę. |
| **E-mail do alertów** | pusty | Skrzynka, na którą przychodzi alert. Zostaw puste, aby użyć e-maila sklepu. Wartość, która nie jest adresem e-mail, jest czyszczona, a strona pokazuje **Podaj prawidłowy adres e-mail do alertów.** |

Temat wiadomości to **Ban IP Pro alert**. Treść podaje adres IP, powód (`auto-login`, `auto-honeypot` albo `auto-rate`), godzinę końca albo słowo `permanent` oraz nazwę sklepu.

### 3.5 Sieć

![Sieć](https://mypresta.eu/docs/images/docs/banippro-configure-network.webp)

Ekran jest po angielsku. W tej instrukcji ta część nazywa się **Sieć**.

Kliknij **Zapisz**. Strona pokazuje **Ustawienia zapisane**.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Ufaj Cloudflare** | **Nie** | Włącz tylko wtedy, gdy domena sklepu przechodzi przez Cloudflare. Moduł czyta wtedy adres gościa z Cloudflare i tylko wtedy, gdy połączenie naprawdę pochodzi z Cloudflare. Zostaw **Nie**, gdy nie masz pewności, inaczej każdy gość może wyglądać jak proxy. |
| **Zaufane proxy** | puste | Gdy przed sklepem stoi proxy albo load balancer, wpisz tu jego adres IP albo sieć, jeden w linii. Moduł czyta adres gościa z tego proxy tylko dla tych adresów. Zostaw puste, gdy nie masz pewności. |
| **Blokuj wybrane kraje** | **Nie** | **Tak** blokuje każdego gościa, którego kraj jest na liście poniżej. Zadziała to po wgraniu bazy krajów. Nie wpisuj własnego kraju. Blokada kraju nie dodaje wiersza w **Banowanie IP**. Blokuje to żądanie i zapisuje linię logu z powodem **Kraj**. |
| **Kody krajów** | puste | Kody dwuliterowe, na przykład `PL`, `DE` albo `US`. Rozdziel je przecinkami, spacjami albo nowymi liniami. Wszystko, co nie ma dwóch liter, jest odrzucane. |
| **Przechowuj logi przez dni** | 90 | Ile dni trzymana jest historia blokad i lista działań pracowników. Starsze wiersze znikają przy pierwszym żądaniu kolejnego dnia. Najmniejsza zapisana wartość to 1. Wartości powyżej 3650 są zapisywane jako 3650. |
| **Baza krajów GeoLite2** | brak pliku | Opcjonalnie. Wybierz plik, którego nazwa kończy się na `.mmdb`. Po **Zapisz** statystyki mogą pokazywać kraj, a blokada krajów zaczyna działać. Reszta modułu nie potrzebuje tego pliku. |

Nad polem pliku strona pokazuje jedną z tych linii:

| Co widać | Co zrobić |
|---|---|
| **Baza GeoIP jest gotowa.** | Nic. Ustalanie kraju działa. |
| **Ustalanie kraju wymaga PHP 7.2 lub nowszego. Reszta modułu działa dalej.** | Bany nadal działają. Statystyki krajów i blokada krajów zostają wyłączone, dopóki PHP nie jest 7.2 albo nowsze. |
| **Wgraj GeoLite2-Country.mmdb, aby włączyć statystyki krajów i blokadę krajów. Plik udostępnia MaxMind.** | Wgraj plik i kliknij **Zapisz**. |

Zły plik pokazuje **Wgraj plik GeoLite2 Country z rozszerzeniem .mmdb.** Gdy pliku nie da się zapisać, widać **Nie udało się zapisać bazy GeoIP.** Dobry zapis pokazuje **Baza GeoIP została wgrana.**

### 3.6 Narzędzia

![Narzędzia](https://mypresta.eu/docs/images/docs/banippro-configure-tools.webp)

Ekran jest po angielsku. W tej instrukcji ta część nazywa się **Narzędzia**.

**Import reguł** tworzy bany. Zasięg to **Domyślny zasięg nowych banów**. Każdy nowy wiersz jest aktywny, trwały i ma powód **Ręcznie**, chyba że linia mówi inaczej.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Adresy** | puste, z przykładem w podpowiedzi | Jeden adres w linii. Linia CSV może być adres, komentarz, powód. Linie zaczynające się od `#` są pomijane. Adres, który już istnieje, też jest pomijany. |
| **Plik** | pusty | Plik tekstowy. Jego linie dochodzą do pola powyżej. Plik większy niż 2 MB pokazuje **Plik importu jest większy niż 2 MB.** i nic nie jest importowane. |
| **Importuj** | przycisk | Tworzy bany i pokazuje **Zaimportowano reguł: %d.** Pominięte linie pokazują też **Pominięto linii: %d.** Import staje po 5000 liniach. |
| **Eksportuj reguły CSV** | przycisk | Pobiera `banippro-rules.csv` dla każdej reguły. Nie zmienia listy. |

**Fragment konfiguracji serwera** pokazuje dwa pola, Apache 2.4 i nginx. W nagłówku jest liczba wyeksportowanych adresów. Wchodzą tylko aktywne, trwałe bany będące pojedynczym IP albo siecią. Wzorzec taki jak `192.168.1.*` jest zapisany jako sieć. Zakresy i bany czasowe są pomijane. **Kopiuj** kopiuje pole. Moduł nie edytuje plików serwera. Tekst wklejasz do konfiguracji serwera sam. Gdy nie ma czego eksportować, oba pola mówią, że nie ma czego eksportować.

**Awaryjne odblokowanie** pokazuje adres. Otwórz go w przeglądarce, która jest zablokowana. Moduł dodaje adres IP tej przeglądarki do białej listy, dla sklepu i panelu, i przepuszcza to żądanie.

| Przycisk | Co robi |
|---|---|
| **Kopiuj** | Kopiuje adres odblokowania. Klucz zostaje ten sam. |
| **Utwórz nowy klucz** | Podmienia klucz. Strona mówi **Utworzono nowy klucz awaryjny. Poprzedni link odblokowania już nie działa.** |
| **Przebuduj cache** | Przepisuje cache reguł z bieżącej listy. Strona mówi **Cache reguł został przebudowany.** |

Trzymaj adres odblokowania poza sklepem. Każdy, kto go otworzy, trafia na białą listę.

### 3.7 Aktualizacje

![Aktualizacje](https://mypresta.eu/docs/images/docs/banippro-configure-updates.webp)

Ekran jest po angielsku. W tej instrukcji ta część nazywa się **Aktualizacje**.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Sprawdź teraz** | przycisk | Pyta MyPresta, czy jest nowsza wersja. **Nowa wersja dostępna!** albo **Moduł jest aktualny!** Witryna sklepu nigdy tego nie woła. |
| **Powiadomienia o aktualizacjach** | **Wyłącz** | **Włącz** robi to samo sprawdzenie przy otwarciu tej zakładki, najwyżej raz na trzy dni. Nowsza wersja pokazuje też informację na stronie modułu: **Dostępna jest nowa wersja, szczegóły na MyPresta.eu**, z linkiem **Więcej w changelogu**. |
| **Zapisz** | przycisk | Zapisuje **Włącz** albo **Wyłącz**. Nie pobiera pliku. Strona mówi **Ustawienia zapisane**. |

Link pod formularzem otwiera stronę modułu na mypresta.eu, gdzie jest changelog. Ta instrukcja nie wymienia wersji.

### 3.8 Banowanie IP, lista reguł

![Banowanie IP, lista reguł](https://mypresta.eu/docs/images/docs/banippro-rules-list.webp)

Ekran jest po angielsku. W tej instrukcji ta część nazywa się **Banowanie IP, lista reguł**.

Otwórz **Zaawansowane**, **Banowanie IP**, albo **Zarządzaj regułami** na **Pulpicie**. Linia nad listą mówi, że pulpit, statystyki i automatyzacja są na stronie konfiguracji modułu, i daje **Otwórz pulpit**.

**Dodaj nowy** otwiera pustą regułę. Przy nowej regule możesz wkleić kilka adresów, jeden w linii. Mają wspólny komentarz, powód, typ reguły, zasięg, wygaśnięcie, flagę aktywności i sklep.

Kolumny listy to **ID**, **Adres IP**, **Dopasowanie**, **Reguła**, **Zasięg**, **Trafienia**, **Ostatnie trafienie**, **Wygasa**, **Powód** i **Aktywne**. Gdy sklep ma więcej niż jeden sklep, dochodzi **Sklep**.

| Kolumna | Co widać |
|---|---|
| **Dopasowanie** | **Dokładny**, **Wildcard**, **CIDR** albo **Zakres**. |
| **Reguła** | **Ban** albo **Pozwól**. |
| **Zasięg** | **Witryna sklepu**, **Panel administracyjny** albo **Witryna i panel**. |
| **Trafienia** | Ile zablokowanych żądań zapisano przy tej regule. |
| **Ostatnie trafienie** | Data ostatniego. |
| **Wygasa** | Data i godzina albo **Na stałe**. |
| **Powód** | **Ręcznie**, **Oszustwo**, **Spam**, **Skaner**, **Chargeback**, **Konkurencja**, **Auto-ban (logowanie)**, **Auto-ban (skaner)**, **Auto-ban (limit żądań)** albo **Kraj**. |
| **Aktywne** | Ikona stanu. Kliknięcie włącza albo wyłącza wiersz. Nieaktywna reguła zostaje na liście i nikogo nie dotyczy. |
| **Sklep** | **Wszystkie sklepy** albo nazwa jednego sklepu. Widać tylko przy wielu sklepach. |

Wiersz filtrów służy do szukania. Filtrowanie nikogo nie blokuje i nikogo nie przepuszcza.

Akcje wiersza:

| Akcja | Co robi |
|---|---|
| **Edytuj** | Otwiera regułę. W istniejącym wierszu da się zapisać tylko jeden adres. |
| **Biała lista** | Widać przy banie. Zmienia ten wiersz na **Pozwól** i przebudowuje cache. Ukryte przy wierszu, który już jest **Pozwól**. |
| **Usuń** | Usuwa wiersz i przebudowuje cache. |

Akcje masowe, po zaznaczeniu wierszy:

| Akcja | Co robi |
|---|---|
| **Włącz wybrane** | Włącza zaznaczone wiersze i przebudowuje cache. |
| **Wyłącz wybrane** | Wyłącza zaznaczone wiersze i przebudowuje cache. Zostają na liście. |
| **Usuń wybrane** | Pyta **Usunąć wybrane?** i potem usuwa zaznaczone wiersze oraz przebudowuje cache. |

Reguła **Pozwól** jest sprawdzana przed banami. Pasująca reguła **Pozwól** przepuszcza gościa nawet wtedy, gdy ban też by pasował.

Reguła, której czas końca minął, przestaje pasować od razu. Przy pierwszym żądaniu kolejnego dnia jest też przełączana na nieaktywną.

### 3.9 Formularz reguły

![Formularz reguły](https://mypresta.eu/docs/images/docs/banippro-rule-form.webp)

Ekran jest po angielsku. W tej instrukcji ta część nazywa się **Formularz reguły**.

**Zapisz** zapisuje regułę, przebudowuje cache i wraca do listy, gdy każda linia jest poprawna.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Adres IP** | pusty | Przy nowej regule jeden adres w linii. Przy edycji jeden adres. Pojedyncze IP, wzorzec taki jak `192.168.1.*`, sieć taka jak `10.0.0.0/8` albo zakres taki jak `192.168.1.10-192.168.1.20`. Wzorce są IPv4, a gwiazdki muszą być na końcu. IPv6 działa dla pojedynczego adresu, sieci i zakresu. |
| **Komentarz** | pusty | Prywatna notatka widoczna tylko na tej liście. Goście jej nie widzą. |
| **Powód** | **Ręcznie** | Dlaczego ten adres jest na liście. Statystyki używają tego, żeby odróżnić ban ręczny od automatycznego. Powodów automatycznych nie ma na tej liście. Moduł wpisuje je sam. |
| **Reguła** | **Ban** | **Ban** blokuje adres. **Pozwól** zawsze go przepuszcza, nawet gdy inna reguła miałaby go zablokować. |
| **Zasięg** | wartość **Domyślny zasięg nowych banów** | **Witryna sklepu** to sklep widziany przez klientów. **Panel administracyjny** to ten panel. **Witryna i panel** oznacza, że reguła działa w sklepie i w panelu. |
| **Wygasa** | puste | Zostaw puste, aby reguła działała, aż ją usuniesz. Albo wpisz datę i godzinę wyłączenia, na przykład `2026-12-31 18:00`. Zła wartość pokazuje **Data wygaśnięcia jest nieprawidłowa.** |
| **Aktywne** | **Tak** | **Nie** zostawia regułę na liście, ale nikogo nie blokuje i nikogo nie przepuszcza. |
| **Potwierdzam blokadę własnego adresu IP** | **Nie** | Linia pomocy pokazuje Twój aktualny adres IP albo **nieznany**. Potwierdzenie jest wymagane, gdy ban objąłby ten adres w panelu. |
| **Sklep** | **Wszystkie sklepy** | Widać tylko przy wielu sklepach. **Wszystkie sklepy** oznaczają, że reguła działa w każdym sklepie tej instalacji. Wybierz jeden sklep, aby ograniczyć regułę do niego. |
| **Zapisz** | przycisk | Zapisuje wiersze. |

Puste pole pokazuje **Podaj adres IP.** Wzorzec, który objąłby każdy adres, taki jak `*.*.*.*` albo sieć z prefiksem `0`, pokazuje **Ta reguła zablokowałaby każdy adres.** Zły adres pokazuje **Ten adres IP lub zakres jest nieprawidłowy.** Druga aktywna reguła z tym samym adresem i tym samym typem ban albo pozwolenie pokazuje **Taka reguła już istnieje.** Ban, który obejmuje Twój aktualny adres IP w panelu, bez przełącznika potwierdzenia, pokazuje **Ten ban obejmuje Twój aktualny adres IP w panelu. Potwierdź zapis.** Więcej niż jedna linia przy edycji pokazuje **Podczas edycji podaj jeden adres.** Zła linia przy nowej regule jest pomijana z **Linia … została pominięta:** i powodem. Zdublowana linia jest pomijana z **Linia pominięta, bo reguła już istnieje:** i adresem. Gdy część linii się zapisała, a część nie, strona pokazuje też **Zapisano reguł: %d.** i zostaje na formularzu. Gdy wiersza nie da się zapisać, widać **Nie udało się zapisać reguły.** Brakujący wiersz pokazuje **Nie znaleziono reguły.**

## 4. Front sklepu

Motyw sklepu nie drukuje bloku, plakietki ani widżetu tego modułu. Na zwykłej stronie produktu, koszyka albo strony głównej nie ma czego fotografować.

Gość, który nie jest zablokowany, widzi sklep jak zwykle. Zablokowany gość widzi prostą stronę: logo sklepu, gdy sklep je ma, nagłówek 403, **Wiadomość dla zablokowanych** w języku strony i adres IP gościa. Strona prosi wyszukiwarki, żeby jej nie indeksowały. Gdy **Przekieruj zablokowanych** jest **Tak**, a **Adres przekierowania** jest poprawnym linkiem `http` albo `https`, gość trafia na ten adres i nie widzi wiadomości.

Ta sama strona blokady jest używana w panelu, gdy **Chroń panel administracyjny** jest **Tak**, a adres IP pracownika pasuje tam do bana i nie pasuje do reguły **Pozwól**.

Te sprawdzenia działają tylko na żądaniach, które wchodzą do PrestaShop. Pliki serwowane wprost przez serwer WWW, na przykład obrazki, nie są sprawdzane i nie są liczone przez **Ogranicz liczbę żądań z adresu IP**.

Nie ma strony konta klienta ani formularza odwołania. Gość albo przechodzi, albo widzi stronę blokady, albo ląduje na przekierowaniu.

| Co widzi gość | Co robisz |
|---|---|
| Sklep, jak zwykle | Żaden ban nie pasuje albo pasuje reguła **Pozwól**. |
| Strona blokady z Twoją wiadomością i jego adresem IP | Pasuje ban, kraj jest zablokowany, otwarto ścieżkę skanera albo przekroczono limit żądań. Przekierowanie jest **Nie**. |
| Inna strona, bez wiadomości | Przekierowanie jest **Tak** i adres jest poprawny. |
| Panel, jak zwykle | **Chroń panel administracyjny** jest **Nie** albo ten adres IP jest na białej liście. |

## 5. Problemy

**Strona modułu mówi Ban IP Pro wymaga PHP 7.1 lub nowszego.**  
Serwer ma PHP starsze niż 7.1. Instalacja jest odrzucana, a **Konfiguruj** pokazuje tylko to zdanie. Przenieś sklep na PHP 7.1 albo nowsze i zainstaluj ponownie.

**Konfiguruj mówi Nie udało się zaktualizować bazy modułu.**  
Tabel nie dało się utworzyć albo zaktualizować. Poproś hosting o prawo użytkownika bazy do tworzenia i zmiany tabel, potem otwórz **Konfiguruj** jeszcze raz.

**Hook witryny mówi Brak.**  
Sprawdzenie nie jest podpięte. Zainstaluj moduł ponownie albo wyłącz go i włącz z **Menedżera modułów**. Istniejące reguły zostają.

**Zapis w Zachowanie odrzuca Chroń panel administracyjny.**  
Strona mówi **Dodaj swój aktualny adres IP do białej listy, zanim włączysz ochronę panelu.** Na **Pulpicie** kliknij **Dodaj do białej listy**, potem ustaw przełącznik na **Tak** i zapisz jeszcze raz.

**Odciąłeś sobie dostęp do panelu.**  
Otwórz adres awaryjny z **Narzędzia**, **Awaryjne odblokowanie**, w przeglądarce, która nadal dochodzi do sklepu. Adres IP tej przeglądarki trafia na białą listę, a żądanie jest przepuszczane. Gdy nie możesz otworzyć **Narzędzi**, użyj kopii adresu zapisanej wcześniej. **Utwórz nowy klucz** unieważnia stary adres, więc po użyciu zaktualizuj kopię.

**Ban własnego adresu IP jest odrzucany.**  
Strona mówi **Ten ban obejmuje Twój aktualny adres IP w panelu. Potwierdź zapis.** Włącz **Potwierdzam blokadę własnego adresu IP** albo zmień zasięg na **Witryna sklepu**, gdy chcesz zablokować ten adres tylko w sklepie.

**Import mówi Plik importu jest większy niż 2 MB.**  
Podziel plik. Każdy import staje po 5000 liniach i wtedy pokazuje, że import się zatrzymał. Resztę wgraj następnym importem. Pominięte linie pokazują **Pominięto linii: %d.** Istniejące adresy są pomijane celowo.

**Adres został zapisany, a sklep nadal go przepuszcza.**  
Sprawdź **Aktywne**, **Zasięg** i **Wygasa**. Reguła panelu nie dotyczy sklepu. Reguła **Pozwól** dla tego adresu wygrywa. Na **Pulpicie** użyj **Sprawdź adres**. Potem kliknij **Przebuduj cache** w **Narzędziach**.

**Bany panelu nic nie robią.**  
**Sprawdź adres** dopisuje **Ochrona panelu jest wyłączona, więc bany panelu nie są egzekwowane.** Włącz **Chroń panel administracyjny** w **Zachowanie**, gdy Twój adres IP jest już na białej liście.

**Blokada krajów nic nie robi.**  
**Blokuj wybrane kraje** musi być **Tak**, kody muszą mieć dwie litery, a strona musi mówić **Baza GeoIP jest gotowa.** Na PHP starszym niż 7.2 strona mówi, że ustalanie kraju wymaga PHP 7.2 albo nowszego. Nie wpisuj własnego kraju.

**Klienci są banowani podczas zwykłej wyprzedaży.**  
**Ogranicz liczbę żądań z adresu IP** jest włączone, a limit jest za niski dla tego sklepu. Ustaw **Nie** albo podnieś **Dozwolone żądania w oknie**. Usuń automatyczne bany w **Banowanie IP**. Ich powód to **Auto-ban (limit żądań)**.

**Nieudane logowanie pracownika nie zablokowało panelu.**  
Ten automatyczny ban dotyczy witryny sklepu. Panel jest blokowany tylko wtedy, gdy **Chroń panel administracyjny** jest **Tak** i pasuje ban, którego zasięg obejmuje panel.

**E-mail z alertem nie przychodzi.**  
**Wyślij e-mail, gdy powstanie automatyczny ban** musi być **Tak**. Bany ręczne nie wysyłają poczty. Drugi automatyczny ban w tej samej godzinie nie wysyła kolejnego listu. Skrzynka to **E-mail do alertów** albo e-mail sklepu, gdy pole jest puste. Sklep musi już umieć wysyłać pocztę.

**Wykres nadal pokazuje stare dni po skróceniu logu.**  
**Przechowuj logi przez dni** usuwa log linia po linii i działania pracowników. Sumy dzienne używane przez wykres na pulpicie zostają.

**Dostępna jest nowa wersja, szczegóły na MyPresta.eu.**  
Otwórz **Aktualizacje** i użyj linku albo kliknij **Sprawdź teraz**. Ta instrukcja nie wymienia zmian.

## 6. Dla developera

### 6.1 Przegląd

Nazwa techniczna `banippro`, wersja 2.0.0, klasa `banippro`, nazwa na liście **Ban IP pro**, autor MyPresta.eu, zakładka `administration`. Strona produktu: `https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html`.

`actionDispatcherBefore` woła `BanIpGuard::protect()`. Guard ustala IP, stosuje awaryjne odblokowanie, potem `BanIpMatcher::decide()` na cache z `cache/rules.php`. Pozwolenie wygrywa z banem. Blokada kraju, ban za ścieżkę skanera i limit żądań działają na witrynie. Blokada zapisuje trafienie i albo przekierowuje, albo renderuje `blocked.tpl` ze statusem 403 i kończy żądanie. `actionDispatcherAfter` woła `BanIpAutoBan::evaluate()` dla logowania uzbrojonego wcześniej. Ustawienia to globalne wartości konfiguracji czytane przez `BanIpInstaller`. Kontroler menu `AdminBanIpPro` edytuje tabelę `ban`.

Nie ma nadpisania `enable()` ani `disable()`. Wyłączenie PrestaShop odpina hooki, więc guard nie działa. Dane zostają.

### 6.2 Pliki

| Plik | Rola |
|---|---|
| `banippro.php` | Instalacja, hooki, zakładki konfiguracji, szybki ban, import, test. |
| `controllers/admin/AdminBanIpProController.php` | Lista reguł, formularz, eksport CSV, akcja białej listy. |
| `models/banip.php` | Model obiektu `ban` oraz `storeRule()` i `importLines()`. |
| `classes/BanIpGuard.php` | Sprawdzenie żądania, strona blokady, codzienna konserwacja. |
| `classes/BanIpMatcher.php` | Parsowanie exact, wildcard, CIDR i range. Decyzja: najpierw allow, potem ban. |
| `classes/BanIpClientIp.php` | Adres zdalny, Cloudflare, zaufane proxy. |
| `classes/BanIpCache.php` | Buduje i include'uje `cache/rules.php`. |
| `classes/BanIpAutoBan.php` | Skaner, nieudane logowanie, limit, e-mail alertu. |
| `classes/BanIpStats.php` | Pulpit, raport, CSV, fragmenty serwera. |
| `classes/BanIpGeo.php` | Czyta `geo/GeoLite2-Country.mmdb` bez biblioteki MaxMind. |
| `classes/BanIpInstaller.php` | Tabele i domyślna konfiguracja. |
| `classes/BanIpUpdate.php` | Sprawdzenie wersji na `dev.mypresta.eu`. |
| `views/templates/admin/*.tpl` | Pulpit, statystyki, narzędzia, skorupa. |
| `views/templates/front/blocked.tpl` | Strona blokady. |
| `views/js/dashboard.js` | Wykresy i przyciski kopiowania. |
| `mails/en/banippro_alert.txt`, `mails/pl/banippro_alert.txt` | Treść alertu. Temat jest na sztywno w `BanIpAutoBan::alert()`. |
| `upgrade/upgrade-2.0.0.php` | Woła `BanIpInstaller::upgrade()`, podmienia stare hooki na zestaw 2.0.0, przebudowuje cache. |
| `lib/searchTool/` | Ładowany na stronie konfiguracji. Żadne pole konfiguracji go nie woła. |
| `tests/matcher_test.php` | Testy CLI matchera. |

### 6.3 Kontrolery

`AdminBanIpPro` rozszerza `ModuleAdminController`. Rodzic w menu to `AdminAdvancedParameters`. Nazwa klasy `AdminBanIpPro`. Tabela `ban`, identyfikator `id_ban`, obiekt `banip`.

Filtry listy używają standardowych nazw helpera (`banFilter_ip` i pozostałe pola listy). Akcje wiersza: edycja, `displayWhitelistLink` (`banippro_whitelist`), usuwanie. Masowo: delete, enable, disable. `exportHits` strumieniuje CSV trafień. `exportRules` strumieniuje CSV reguł.

Nie ma kontrolera frontu. Odpowiedź blokady jest renderowana w hooku dispatchera i żądanie się kończy.

`?banippro_unlock=` czyta `BanIpGuard::tryUnlock()`. Wartość musi zgadzać się z `banippro_emergency_key` przez `hash_equals`. Trafienie woła `BanIpAutoBan::ensureAllow()` z zasięgiem witryny i panelu (`apply_to` 3, `id_shop` 0) i zapisuje audyt `unlock`.

### 6.4 Hooki

Rejestrowane przy instalacji:

| Hook | Wywołanie |
|---|---|
| `actionDispatcherBefore` | `BanIpGuard::protect()`. |
| `actionDispatcherAfter` | `BanIpAutoBan::evaluate()`. Rejestrowany też po głównym sprawdzeniu instalacji. |
| `actionFrontControllerSetMedia` | `BanIpAutoBan::arm('customer')`. |
| `actionAuthentication` | `BanIpAutoBan::markSuccess('customer')`. |
| `actionAdminControllerInitAfter` | `BanIpAutoBan::arm('employee')`. |

`upgrade-2.0.0.php` wyrejestrowuje `header`, `displayHeader`, `home`, `displayHome`, `actionFrontControllerAfterInit` i `actionAdminControllerSetMedia`.

Moduł nie wystawia własnego hooka. Uzbrajanie logowania szuka `submitLogin` w żądaniu. Udane logowanie klienta czyści licznik pomyłek klienta. Sukces pracownika jest wykrywany, gdy pracownik jest zalogowany w `evaluate()`.

### 6.5 Nadpisania

Moduł nie nadpisuje klasy ani kontrolera PrestaShop.

### 6.6 Baza

Odinstalowanie nie kasuje tych tabel i nie kasuje kluczy konfiguracji. `BanIpInstaller::ensure()` dopisuje brakujące kolumny w `{prefix}ban` przy otwarciu **Konfiguruj**, więc starsza tabela `ban` zostaje i jest rozszerzana. Ponowna instalacja nie czyści wierszy.

| Tabela | Zawartość |
|---|---|
| `{prefix}ban` | `id_ban`, `ip`, `ip_end`, `match_type` (`exact`, `wildcard`, `cidr`, `range`), `rule_type` (1 ban, 2 allow), `apply_to` (1 witryna, 2 panel, 3 oba), `views`, `comment`, `reason`, `active`, `date_add`, `date_upd`, `date_end`, `last_hit`, `id_employee`, `id_shop` (0 oznacza wszystkie sklepy), `range_start`, `range_end`. |
| `{prefix}banippro_hit` | Jeden wiersz na blokadę: `id_ban`, `ip`, `request_uri`, `user_agent`, `country_iso`, `id_shop`, `date_add`. |
| `{prefix}banippro_daily` | `day`, `id_shop`, `blocked`, `auto_banned`. Nie jest kasowana przy czyszczeniu logów. |
| `{prefix}banippro_fail` | `ip`, `context` (`customer`, `employee`, `rate`), `hits`, `window_start`. |
| `{prefix}banippro_audit` | `id_employee`, `action`, `details`, `date_add`. |

`BanIpGuard::dailyMaintenance()` działa raz na dzień kalendarzowy. Ustawia `active` na 0 przy regułach, których `date_end` jest w przeszłości, przebudowuje cache, gdy jakiś wiersz się zmienił, i kasuje wiersze hit oraz audit starsze niż `banippro_log_days`.

### 6.7 Klucze i tłumaczenia

Wszystkie klucze są globalne (`id_shop` 0). Brak klucza wraca do wartości domyślnej w nawiasie.

| Klucz | Domyślnie |
|---|---|
| `banippro_emergency_key` | 32 znaki hex z `random_bytes`, albo OpenSSL, albo `md5` |
| `banippro_msg` | Na język. `en` You are blocked. `pl` Dostęp został zablokowany. `es` El acceso ha sido bloqueado. `pt` i `br` O acesso foi bloqueado. Inne języki dostają zdanie angielskie. W zapisie dozwolony jest HTML. |
| `banippro_redirect` | 0 |
| `banippro_url` | puste |
| `banippro_default_apply` | 1 |
| `banippro_protect_admin` | 0 |
| `banippro_honeypot` | 1 |
| `banippro_honeypot_hours` | 24 |
| `banippro_honeypot_paths` | `BanIpInstaller::defaultHoneypotPaths()` |
| `banippro_autoban_customer` | 0 |
| `banippro_autoban_employee` | 0 |
| `banippro_autoban_threshold` | 5 |
| `banippro_autoban_window` | 15 |
| `banippro_autoban_hours` | 24 |
| `banippro_ratelimit` | 0 |
| `banippro_ratelimit_max` | 120 |
| `banippro_ratelimit_window` | 1 |
| `banippro_ratelimit_ban_minutes` | 15 |
| `banippro_alert` | 0 |
| `banippro_alert_email` | puste |
| `banippro_alert_last` | czas unix ostatniego maila, zapisywany przy wysyłce |
| `banippro_cloudflare` | 0 |
| `banippro_trusted_proxies` | puste |
| `banippro_countries_enabled` | 0 |
| `banippro_countries` | puste |
| `banippro_log_days` | 90 |
| `banippro_last_maintenance` | `Y-m-d` ostatniej konserwacji |
| `mypresta_updates` | nie jest seedowany; formularz traktuje brak jako 0 |
| `update_banippro` | 0, potem czas unix ostatniego sprawdzenia |
| `updatev_banippro` | zdalny numer wersji z ostatniego sprawdzenia |

`BanIpInstaller::seedConfig()` kopiuje stare, sklepowe `banippro_redirect` i `banippro_url` do kluczy globalnych, gdy wartość globalna jest pusta. Niepuste stare `banippro_msg` jest kopiowane do każdego języka, zanim użyte zostaną zdania domyślne.

Napisy zaplecza idą przez `$this->l()` / `$this->module->l()`. Pliki tłumaczeń leżą w `translations/{iso}.php`. Wiadomość strony blokady to wartość konfiguracji, nie klucz tłumaczenia. Temat maila `Ban IP Pro alert` jest literałem w `BanIpAutoBan::alert()`. Opisy pól to `desc` przy inputach HelperForm w `banippro.php` i `AdminBanIpProController.php`.

Automatyczne wartości `reason` zapisywane przez moduł to `auto-login`, `auto-honeypot` i `auto-rate`. Blokada kraju loguje `country` i nie wstawia wiersza `ban`. `banip::importLines()` staje po 5000 niepustych liniach, które nie są komentarzem. Wgrania powyżej 2097152 bajtów są odrzucane. `BanIpMatcher` odrzuca pustą wartość, sieć `/0` i wildcard z czterech gwiazdek (`too_broad`). Duplikat to aktywny wiersz z tym samym zapisanym IP i tym samym `rule_type`.

`BanIpAutoBan::ensureBan()` zawsze zapisuje `apply_to` 1 i `id_shop` 0. `ensureAllow()` zapisuje `apply_to` 3 i `id_shop` 0.

### 6.8 Rozszerzanie

Motyw może nadpisać `views/templates/front/blocked.tpl`. Moduł woła `$module->fetch('blocked.tpl')`. Przypisane zmienne to `banippro_message`, `banippro_shop`, `banippro_logo`, `banippro_year`, `banippro_ip` i `banippro_lang`. Gdy fetch się nie uda, guard drukuje minimalną stronę HTML z tą samą wiadomością i nadal kończy ze statusem 403.

Nie jest renderowany szablon produktu, koszyka ani strony głównej. Nie ma hooka, w którym motyw dodałby widżet na witrynie. Szablony zaplecza leżą w `views/templates/admin/` i nie należą do motywu.

## 7. Pomoc

Strona modułu: [Ban IP pro](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html).

Zaloguj się na konto klienta na [mypresta.eu](https://mypresta.eu), otwórz kontakt i wybierz temat **Support for paid modules**. Formularz podaje, że przy tym temacie logowanie jest wymagane. Po zalogowaniu wybierz ten moduł z historii zakupów.
