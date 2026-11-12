---
title: Contact page - spam protection PRO - dokumentacja i instrukcja użytkownika
sidebar:
  label: Contact page - spam protection PRO - dokumentacja i instrukcja użytkownika
description: Instrukcja konfiguracji i rozwiązywania problemów dla sklepów, które mają już ochronę strony kontaktowej przed spamem.
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Contact page - spam protection PRO na MyPresta.eu](https://mypresta.eu/modules/administration-tools/contact-page-spam-protection-pro.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/contact-page-spam-protection-pro/)
>
> ---


## 1. Wymagania

Moduł działa w PrestaShop od 1.7.7 do 9. PHP ma być w wersji wymaganej przez tę wersję PrestaShop. Wystarczy własna strona kontaktowa sklepu. Żaden inny moduł nie jest potrzebny.

Konto Google reCAPTCHA jest potrzebne tylko wtedy, gdy chcesz pole wyboru albo niewidoczną ocenę wizyty. Po instalacji przełącznik reCAPTCHA jest włączony, ale captcha stoi, dopóki nie zapiszesz obu kluczy.

Konto CleanTalk jest potrzebne tylko do płatnego API. Darmowe sprawdzenie idzie przez proxy MyPresta i konta CleanTalk nie wymaga. Darmowy CleanTalk potrzebuje funkcji OpenSSL w PHP. Gdy ich nie ma, to jedno sprawdzenie jest pomijane i wiadomość przechodzi.

StopForumSpam to publiczne sprawdzenie. Konto i klucz API są opcjonalne. Zapisany klucz nie jest używany przy sprawdzaniu.

Zapytania używają cURL, gdy PHP je ma. Bez cURL StopForumSpam, CleanTalk i sprawdzenie aktualizacji czytają adres zwykłym odczytem, gdy serwer na to pozwala. Weryfikacja reCAPTCHA używa cURL, gdy jest dostępne.

## 2. Instalacja

Otwórz **Moduły**, potem **Menedżer modułów**. Wgraj paczkę zip i kliknij **Zainstaluj**.

W lewym menu pojawia się **Ochrona formularza kontaktowego**. Wejście w nią otwiera konfigurację. Pod spodem są **Próby wysłania wiadomości** i **Zablokowane adresy IP**.

Instalacja nie czyści cache osobnym krokiem.

Wyłączenie robisz przełącznikiem w Menedżerze modułów. Strona kontaktowa przestaje być sprawdzana. Ustawienia, próby i blokady zostają. Po ponownym włączeniu są używane dalej. Pozycje menu są schowane, gdy moduł jest wyłączony.

Usunięcie: kliknij **Odinstaluj** i potwierdź **Czy na pewno chcesz odinstalować ten moduł?** Odinstalowanie zabiera pozycje menu, zapisane ustawienia i obie listy. Pliki modułu zostają na serwerze, dopóki nie usuniesz modułu. Kolejna instalacja startuje z pustymi listami i ustawieniami świeżej instalacji. Stare próby i blokady nie wracają.

## 3. Konfiguracja i praca w zapleczu

Zrzuty w tym rozdziale są z angielskiego zaplecza. Nazwy poniżej są z polskiego panelu.

Otwórz **Ochrona formularza kontaktowego**. Zakładki to **Przegląd**, **Anty-flood**, **CleanTalk**, **StopForumSpam**, **reCAPTCHA**, **Filtry wiadomości**, **Biała lista**, **Ochrona** i **E-mail**. **Aktualizacje** są na końcu tego rzędu. **Zapisz** na zakładce zapisuje ją i potwierdza **Ustawienia zostały zapisane.** Zakładka aktualizacji potwierdza **Ustawienia aktualizacji zostały zapisane.**

Dopóki warunek trwa, na stronie konfiguracji może wisieć:

**reCAPTCHA jest włączona, ale klucz witryny lub klucz tajny jest pusty. Captcha pozostaje wyłączona, dopóki oba klucze nie zostaną zapisane.**

**Płatne API CleanTalk jest włączone, ale klucz dostępu jest pusty.**

Drugie ostrzeżenie widać, gdy płatny przełącznik jest włączony, a klucz pusty. Po świeżej instalacji płatny przełącznik jest wyłączony, więc tego ostrzeżenia nie ma, dopóki nie włączysz płatnego API bez klucza.

Wiadomość jest sprawdzana w tej kolejności. Decyduje pierwsze trafienie.

1. Adres z białej listy oraz zalogowany klient, gdy włączone jest **Pomiń kontrole dla zalogowanych klientów**, idzie dalej do formularza. Próba nie trafia na listę **Próby wysłania wiadomości**.
2. Gdy wszystkie kontrole są wyłączone i adres nie jest na liście blokad, wiadomość idzie dalej i nie jest zapisywana. Sam przełącznik reCAPTCHA nie liczy się jako kontrola, dopóki oba klucze są puste.
3. Potem kolejność jest taka: aktywna blokada IP, honeypot, minimalny czas, pusty identyfikator przeglądarki, anty-flood, duplikat wiadomości o długości co najmniej 20 znaków, zbyt wiele linków, zablokowane słowo, jednorazowy e-mail, reCAPTCHA (tylko gdy oba klucze są zapisane), StopForumSpam, darmowy CleanTalk, płatny CleanTalk.
4. Gdy nic nie pasuje, próba jest zapisana jako dopuszczona i formularz wysyła wiadomość.
5. Blokada **Zbyt szybko** albo **reCAPTCHA** zatrzymuje tylko tę wiadomość. Nie blokuje adresu, nie wysyła e-maila do sklepu i nie przekierowuje. Przy reCAPTCHA klient widzi **Weryfikacja captcha nie powiodła się. Spróbuj ponownie.** Przy zbyt szybkim wysłaniu widzi **Nie udało się wysłać wiadomości. Spróbuj ponownie za kilka minut.**
6. Każda inna blokada może zablokować adres, wysłać e-mail do sklepu i przekierować, według pól na **Ochronie**. Gdy zaznaczysz kilka przekierowań, najpierw jest strona główna, potem strona CMS, na końcu Google. Bez przekierowania odwiedzający zostaje na stronie kontaktowej i widzi **Nie udało się wysłać wiadomości. Spróbuj ponownie za kilka minut.**

Anty-flood liczy każdą próbę w przedziale czasu, także już zablokowane. Kilka ponownych prób captchy może więc dobić do limitu wiadomości.

Duplikat patrzy na wcześniejsze próby z tym samym tekstem. Próby, które odpadły tylko jako **Zbyt szybko** albo **reCAPTCHA**, nie liczą się jako wcześniejsza kopia.

StopForumSpam i oba sprawdzenia CleanTalk przepuszczają wiadomość, gdy usługa nie odpowiada. reCAPTCHA robi odwrotnie: gdy Google nie odpowiada, wiadomość jest blokowana.

### 3.1 Przegląd

![Przegląd](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-overview.webp)

**Przegląd** liczy wiadomości kontaktowe, zablokowane wiadomości i aktywne blokady dla dat z **Parametrów analityki**. Klient, który przejdzie, jest liczony jako wiadomość. Odwiedzający, który nie przejdzie kontroli, jest liczony jako zablokowany i pokazany niżej z powodem.

Karty to **Wiadomości**, **Dopuszczone**, **Zablokowane**, **Wskaźnik blokad**, **Zablokowane adresy IP** i **Aktywne blokady**.

Wykres **Zablokowane i dopuszczone** pokazuje **Dziennie** i **Tygodniowo**, gdy okres ma więcej niż 7 dni. **Tygodniowo** grupuje dni po siedem od początku okresu. Ostatnia grupa może być krótsza. Legenda to **Dopuszczone**, **Zablokowane** i **Łącznie**. Gdy w okresie nie ma wierszy, wykres mówi **Brak wiadomości w tym okresie.**

**Blokady według powodu** pokazują, ile blokad dała każda kontrola. Nazwy na tej stronie to **Zablokowany adres IP**, **Honeypot**, **Zbyt szybko**, **Pusty user agent**, **Anty-flood**, **Zduplikowana wiadomość**, **Zbyt wiele linków**, **Zablokowane słowo**, **Jednorazowy e-mail**, **reCAPTCHA**, **StopForumSpam** i **CleanTalk**. Pusty powód jest pokazany jako **Nieznany**.

**Ostatnio zablokowane wiadomości** mają kolumny **Data**, **IP**, **E-mail** i **Powód**. Gdy nic nie zostało zablokowane, tabela mówi **W tym okresie nic nie zostało zablokowane.**

Przyciski **Próby wysłania wiadomości** i **Zablokowane adresy IP** otwierają te listy.

Kolorowe plakietki pod wykresem pokazują, które kontrole są włączone. **reCAPTCHA** jest zielona tylko wtedy, gdy oba klucze są zapisane. Sam przełącznik tej plakietki nie zapala. Po instalacji włączone są **Anty-flood**, **Honeypot**, **Minimalny czas** i **Limit linków**.

Linia pod plakietkami ma postać **Wiadomości: 0 w okresie od 2026-10-13 do 2026-11-11. Zablokowane: 0, dopuszczone: 0. Nowe blokady IP w tym okresie: 0.** Daty wynikają z wybranego okresu. Okres kroczący kończy się dzisiaj. To okno tego sklepu, nie stała wartość modułu.

### 3.2 Parametry analityki

![Parametry analityki](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-overview-analytics.webp)

Otwórz zwinięty panel **Parametry analityki** na **Przeglądzie**.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Okres statystyk** | Ostatnie 30 dni | **Ostatnie 7 dni**, **Ostatnie 30 dni**, **Ostatnie 90 dni**, **Ostatnie 180 dni**, **Ostatnie 365 dni** albo **Własny zakres**. Karty, wykres i ostatnia lista biorą to okno. Start to ostatnie 30 dni. Ostatnie 7 dni pokazuje krótki atak i zdejmuje starsze blokady z wykresu. Ostatnie 365 dni obejmuje rok, więc jeden intensywny dzień jest małym kawałkiem. Własny zakres używa **Od** i **Do**. Pozostałe opcje ignorują te daty i zawsze kończą się dzisiaj. |
| **Od** | początek bieżącego okna | Data w formacie RRRR-MM-DD. Używana, gdy **Okres statystyk** to **Własny zakres**. Data późniejsza niż **Do** jest z nią zamieniana. Zakres dłuższy niż 366 dni jest skracany od tej strony. Data z przyszłości wraca do dzisiaj. Pusta albo nieprawidłowa data jest zastępowana datą sprzed 30 dni. Okresy kroczące to pole ignorują. |
| **Do** | dzisiaj | Data w formacie RRRR-MM-DD. Używana, gdy **Okres statystyk** to **Własny zakres**. Data z przyszłości wraca do dzisiaj. Gdy **Do** jest wcześniejsza niż **Od**, daty są zamieniane. Pusta albo nieprawidłowa data jest zastępowana dzisiejszą. Okresy kroczące to pole ignorują i zawsze kończą się dzisiaj. |

**Zapisz** zapisuje okres. Strona potwierdza **Ustawienia zostały zapisane.**

### 3.3 Anty-flood

![Anty-flood](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-antiflood.webp)

Anty-flood liczy, ile wiadomości kontaktowych wysyła jeden adres IP w przedziale czasu. Klient, który napisze kilka razy, nadal przejdzie. Kolejna wiadomość po limicie jest odrzucana, a **Ochrona** może zablokować ten adres, gdy blokada jest zaznaczona.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Włącz anty-flood** | Tak | Włączone: każdy adres IP jest liczony w przedziale, a kolejna wiadomość po limicie jest blokowana. Wyłączone: skrypt może wysyłać z tego samego IP bez limitu tej kontroli. Niski limit blokuje też klienta, który wysyła poprawkę z tego samego biura. Zostaw włączone na publicznej stronie kontaktowej. Wyłącz tylko na czas wiadomości testowych z jednego adresu. |
| **Przedział czasu** | 10 minut | Minuty. Do limitu liczą się wiadomości z ostatnich X minut. 1 albo 2 minuty łapią nagły wzrost i potem o nim zapominają, więc wolny skrypt może jechać dalej. 60 minut albo więcej liczy też klienta, który pisze, czeka i pisze ponownie z tego samego IP. Zapisane 0 jest traktowane jak 1. |
| **Dozwolone wiadomości** | 5 | Ile wiadomości kontaktowych jeden adres IP może wysłać w przedziale. Następna jest blokowana. 5 pozwala poprawić wiadomość i wysłać ją jeszcze raz. 1 blokuje drugie wysłanie, więc zatrzymuje skrypty i klienta, który kliknie wyślij dwa razy. Wysoka wartość, na przykład 20, przepuszcza wiele wiadomości. Licznik obejmuje wcześniejsze wysłania z tego IP, także zablokowane, więc kilka ponownych prób captchy może dojść do limitu. Zapisane 0 jest traktowane jak 1. |

### 3.4 CleanTalk

![CleanTalk](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-cleantalk.webp)

CleanTalk sprawdza adres IP i e-mail w bazie spamu. Włącz opcję darmową, żeby iść przez proxy MyPresta bez konta CleanTalk, albo płatną, gdy masz własny klucz. Nieznany adres jest akceptowany. Adres już zgłoszony jako spam jest odrzucany. Gdy usługa nie odpowiada, wiadomość przechodzi.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Włącz darmowy CleanTalk** | Nie | Pyta proxy CleanTalk MyPresta, czy ten IP albo e-mail jest już znany jako spam. Konto CleanTalk nie jest potrzebne. Wyłączenie pomija to sprawdzenie. Gdy proxy nie odpowiada albo PHP nie ma funkcji szyfrowania OpenSSL, wiadomość przechodzi. Bot, którego nie ma w bazie, też przechodzi. Włącz, gdy nie masz płatnego klucza. |
| **Włącz płatne API CleanTalk** | Nie | Używa klucza z Twojego konta CleanTalk. Włącz po wklejeniu klucza. Zostaw wyłączone, gdy nie masz subskrypcji. Pusty albo odrzucony klucz nikogo nie blokuje, więc spam, który złapałaby tylko ta kontrola, przechodzi. Adres z listy jest odrzucany, a klient na tym samym IP też może zostać odrzucony. |
| **Klucz dostępu** | pusty | Wklej klucz z konta CleanTalk, bez dodatkowych spacji. Płatne sprawdzenie działa tylko wtedy, gdy to pole ma klucz. Puste, przy włączonym płatnym przełączniku, oznacza brak płatnego sprawdzenia, a strona pokazuje **Płatne API CleanTalk jest włączone, ale klucz dostępu jest pusty.** Unieważniony klucz jest traktowany jak nieudane sprawdzenie i wiadomość przechodzi. |
| **Próg wskaźnika spamu** | 1 | Wynik od 0.0 do 1.0. Wskaźnik CleanTalk równy tej wartości albo wyższy jest spamem. Adres, który CleanTalk oznacza jako występujący w spamie, jest blokowany przy każdej wartości. 1 blokuje adresy, co do których CleanTalk ma pewność. Niższa wartość, na przykład 0.5, blokuje też niepewne wyniki i może zatrzymać prawdziwego klienta na współdzielonym IP. Zapisane 0 jest traktowane jak 1, więc kontrola zostaje ostra. |

Link **Otwórz stronę konta CleanTalk** otwiera stronę konta w nowej karcie.

### 3.5 StopForumSpam

![StopForumSpam](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-stopforumspam.webp)

StopForumSpam to darmowa baza adresów IP i e-mail zgłoszonych za spam. Sprawdzenie nie wymaga klucza API. Klient, który nigdy nie był zgłoszony, przechodzi. Adres z wystarczającą liczbą zgłoszeń jest odrzucany. Gdy usługa nie odpowiada, wiadomość przechodzi.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Włącz StopForumSpam** | Nie | Sprawdzany jest IP odwiedzającego i e-mail z formularza. Wyłączenie pomija sprawdzenie. Gdy usługa nie odpowiada, wiadomość przechodzi: problem z siecią nie blokuje klientów, ale przechodzi też spam, który ta kontrola by złapała. Zostaw włączone na publicznej stronie kontaktowej. |
| **Minimalna liczba zgłoszeń** | 1 | Blokuj, gdy StopForumSpam ma ten IP albo e-mail co najmniej tyle razy. Przy 1 jedno zgłoszenie blokuje adres, także klienta zgłoszonego raz przez pomyłkę. Przy 5 albo więcej adresy z nielicznymi zgłoszeniami przechodzą, więc dociera więcej spamu. Zapisane 0 jest traktowane jak 1. |
| **Klucz API** | pusty | Opcjonalny. Publiczne sprawdzenie działa bez klucza. Zostaw puste albo zapisz klucz, jeśli masz już konto StopForumSpam. Moduł i tak używa publicznego sprawdzenia, więc zły klucz nie zmienia tego, kto jest blokowany. |

Link **Zarejestruj się** otwiera rejestrację StopForumSpam.

### 3.6 reCAPTCHA

![reCAPTCHA](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-recaptcha.webp)

Google reCAPTCHA działa w przeglądarce na stronie kontaktowej. Użyj jej, gdy boty wysyłają wiadomości wyglądające jak zwykły tekst, i wybierz ten sam typ, który jest przy kluczu w konsoli Google. v2 pokazuje pole, które klient zaznacza. v3 ocenia wizytę bez wyzwania: dobry wynik przechodzi, zły odrzuca wiadomość i nie blokuje IP.

Tekst **Jak uzyskać klucz witryny i klucz tajny** mówi: utwórz klucz w panelu Google, potem wklej poniżej klucz witryny i klucz tajny. Typ wybrany tutaj ma być taki sam jak typ tego klucza. Niezgodny typ sprawia, że każdy odwiedzający odpada, także prawdziwy klient.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Włącz reCAPTCHA** | Tak | Strona kontaktowa wymaga przejścia reCAPTCHA, zanim wiadomość zostanie przyjęta. Przy pustych kluczach captcha zostaje wyłączona, nawet gdy ten przełącznik jest włączony, i widać **reCAPTCHA jest włączona, ale klucz witryny lub klucz tajny jest pusty. Captcha pozostaje wyłączona, dopóki oba klucze nie zostaną zapisane.** Klient, któremu się nie uda, może spróbować ponownie. Ta porażka nie blokuje IP. |
| **Typ reCAPTCHA** | reCAPTCHA v2 | **reCAPTCHA v2** pokazuje pole wyboru. **reCAPTCHA v3** ocenia wizytę w tle i nie pokazuje wyzwania. Użyj typu wybranego dla klucza w konsoli Google. Niezgodność sprawia, że każde wysłanie odpada, także u prawdziwych klientów. v2 jest czytelniejsze, gdy chcesz widoczną weryfikację. v3 jest mniej widoczne i używa progu wyniku poniżej. |
| **Klucz witryny** | pusty | Klucz publiczny z panelu Google reCAPTCHA dla domeny tego sklepu. Wklej klucz witryny należący do typu wybranego wyżej, bez spacji. Oba klucze są wymagane. Pusty klucz witryny zostawia captchę wyłączoną. Klucz innej domeny albo innego typu sprawia, że prawdziwi klienci nie przechodzą. |
| **Klucz tajny** | pusty | Klucz tajny zostaje na serwerze. Nie jest wysyłany do przeglądarki. Użyj klucza tajnego z tej samej pary co klucz witryny. Pusty klucz tajny zostawia captchę wyłączoną. Klucz tajny z innej witryny sprawia, że Google odrzuca każdą wizytę i klienci nie wyślą formularza. |
| **Motyw v2** | Jasny | **Jasny** albo **Ciemny** kolor pola v2. Jasny na białej stronie kontaktowej, ciemny na ciemnej. v3 to ustawienie ignoruje i używa standardowej plakietki Google. Motyw nie zmienia tego, kto jest blokowany. Ciemny widżet na białej stronie gorzej widać, więc więcej osób pomija pole i wiadomość jest odrzucana. |
| **Próg wyniku v3** | 0.5 | Wynik od 0.0 do 1.0. Używany, gdy typ to v3. Google ocenia wizytę, a wynik poniżej tej wartości jest odrzucany. Start to 0.5. Wyższa wartość, na przykład 0.9, jest ostrzejsza i może odrzucać klientów ze współdzielonej albo nietypowej sieci. Niższa, na przykład 0.1, przepuszcza więcej automatycznych wizyt. Odrzucenie nie blokuje IP. Gdy zapisanej wartości nie ma, używane jest 0.5. |

### 3.7 Filtry wiadomości

![Filtry wiadomości, pierwsze pola](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-filters.webp)

![Filtry wiadomości, dalsze pola](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-filters-content.webp)

Filtry działają w sklepie, przed zewnętrzną usługą antyspamową. Na publicznej stronie zostaw honeypot i minimalny czas, a linki, słowa, jednorazowe e-maile albo duplikaty dodaj, gdy na liście blokad widać powtarzający się wzorzec. Klient, który wypełnia formularz zwyczajnie, przechodzi. Skrypt jest odrzucany. Nieudana captcha albo zbyt szybkie wysłanie nie blokuje IP. Pozostałe filtry mogą je zablokować, gdy na **Ochronie** zaznaczysz blokadę adresu.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Pole honeypot** | Tak | Dodaje ukryte pole, którego ludzie nie widzą. Klient zostawia je puste i wiadomość idzie dalej. Skrypt, który wypełnia każde pole, jest blokowany, a **Ochrona** może zablokować ten IP. Wyłącz, gdy autouzupełnianie wypełnia ukryte pole i blokuje Twoich klientów. |
| **Minimalny czas na stronie** | Tak | Blokuje wysłanie szybsze niż limit od startu skryptu strony. Klient, który czyta i pisze, potrzebuje więcej niż kilku sekund. Skrypt, który wysyła od razu, jest blokowany. Brak licznika jest akceptowany, więc przeglądarka bez JavaScript nadal może wysłać. Ta blokada nie blokuje IP. Wyłączenie przepuszcza natychmiastowe wysyłki przez tę kontrolę. |
| **Minimalna liczba sekund** | 3 | Sekundy. Używane, gdy minimalny czas jest włączony. 1 sekunda nadal łapie natychmiastowy skrypt i rzadko dotyka klienta. 15 sekund albo więcej blokuje klienta, który zna treść i szybko wysyła. Licznik startuje, gdy ruszy skrypt strony. Zapisane 0 jest traktowane jak 1. |
| **Ogranicz liczbę linków w wiadomości** | Tak | Liczy http://, https:// i www. w wiadomości. Włącz, gdy spam to głównie linki. Wyłącz, gdy klienci często wklejają adres produktu. Wyłączenie przyjmuje wiadomość pełną linków. Włączenie z niskim maksimum blokuje też klienta, który wkleja kilka adresów. |
| **Maksymalna liczba linków** | 3 | Wiadomość z większą liczbą linków jest blokowana. Liczone tylko, gdy limit linków jest włączony. 3 pozwala wkleić kilka adresów. 0 blokuje każdą wiadomość z linkiem, nawet do jednej strony produktu. Wysoka wartość, na przykład 20, przepuszcza typowy spam linkowy. |
| **Zablokowane słowa** | Nie | Szukanie bez wielkości liter w e-mailu i w treści. Włącz po dodaniu fraz, które widziałeś w spamie. Wyłączenie albo włączenie z pustą listą nic nie blokuje. Krótkie, popularne słowo blokuje też prawdziwego klienta, który go użył. |
| **Słowa i frazy** | puste | Jedno słowo albo fraza w wierszu. Używane, gdy zablokowane słowa są włączone. Zostaw puste, dopóki nie skopiujesz fraz z prawdziwego spamu. Fraza pasuje w dowolnym miejscu e-maila albo wiadomości, więc krótki kawałek, na przykład win, pasuje też do window i blokuje zwykłe pytanie. Długa, konkretna fraza blokuje tylko ten tekst. |
| **Blokuj jednorazowe adresy e-mail** | Nie | Blokuje wbudowaną listę domen tymczasowych skrzynek i domeny dodane poniżej. Włącz, gdy nie chcesz wiadomości z jednorazowych skrzynek. Zwykły adres przechodzi. Skrzynka z listy jest blokowana, a **Ochrona** może zablokować ten IP. Domeny spoza listy przechodzą, dopóki ich nie dodasz. Wyłączenie przyjmuje każdą domenę. |
| **Dodatkowe domeny jednorazowe** | puste | Jedna domena w wierszu, na przykład dropmail.test. Używane, gdy blokowanie jednorazowych e-maili jest włączone. Zostaw puste, dopóki domena nie pojawi się na liście prób. Domena wpisana tutaj blokuje też swoje subdomeny. Nie wpisuj @. Wpisanie prawdziwego dostawcy poczty blokuje każdego klienta, który z niego korzysta. |
| **Blokuj zduplikowane wiadomości** | Nie | Blokuje ponowne wysłanie tej samej treści w przedziale, z dowolnego IP. Włącz, gdy ta sama reklama idzie z wielu adresów. Wiadomości krótsze niż 20 znaków są pomijane, więc krótkie powitanie można wysłać ponownie. Ponowna próba captchy nie jest duplikatem. Klient, który wyśle to samo długie pytanie dwa razy w oknie, jest blokowany za drugim razem. Wyłączenie pozwala wysłać ten sam tekst ponownie. |
| **Okno duplikatów** | 60 minut | Jak długo treść jest pamiętana. Krótkie okno, na przykład 5 minut, szybko zapomina tekst, więc ten sam spam może wrócić. Długie okno, na przykład 1440 minut (jeden dzień), blokuje też klienta, który wyśle to samo pytanie później tego samego dnia. Używane tylko, gdy blokowanie duplikatów jest włączone. Zapisane 0 jest traktowane jak 1. |
| **Blokuj pusty user agent** | Nie | Blokuje żądanie bez identyfikatora przeglądarki. Zostaw wyłączone, chyba że próby pokazują spam z pustym identyfikatorem. Prawdziwe przeglądarki go wysyłają. Włączenie blokuje też narzędzia prywatności, które identyfikator usuwają, więc tacy klienci nie wyślą wiadomości. Wyłączenie ignoruje pusty identyfikator. |
| **Pomiń kontrole dla zalogowanych klientów** | Nie | Zalogowany klient pomija wszystkie kontrole, także aktywną blokadę. Zostaw wyłączone w sklepie, w którym każdy może się zarejestrować. Włącz, gdy klienci mają konta, którym ufasz. Goście są nadal sprawdzani. Włączenie przepuszcza zalogowanego bota. Wyłączenie sprawdza zalogowanych tak samo jak gości, więc zablokowany adres biura zostaje zablokowany także dla konta. |

### 3.8 Biała lista

![Biała lista](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-whitelist.webp)

Biała lista to adresy IP, które pomijają wszystkie kontrole, także aktywną blokadę. Dodaj biuro, agencję albo narzędzie monitorujące, które wysyła wiadomość testową. Wszyscy pozostali są sprawdzani. Pusta lista oznacza, że żaden adres nie jest pomijany. Wiersz dodany przez pomyłkę przepuszcza ten adres, także bota, który z niego korzysta.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Adresy IP** | puste | Jeden adres w wierszu. Wiersz zakończony * pasuje do początku adresu, na przykład 192.168.1.*. Zostaw puste, chyba że jakiś adres zawsze musi móc pisać, na przykład Twoje biuro. Pełny adres pomija kontrole tylko dla tego IP. Prefiks z gwiazdką pomija cały zakres, łącznie z każdym botem z tego zakresu. Literówka niczego nie dopasowuje, więc ten odwiedzający zostaje chroniony. Porównuj IPv4 i IPv6 dokładnie tak, jak widzi je sklep. |

### 3.9 Ochrona

![Ochrona](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-protection.webp)

Nieudana kontrola zawsze odrzuca wiadomość. Pola pod **Co zrobić ze spamem** to dodatkowe kroki dla blokady IP, honeypota, floodu, filtrów wiadomości, StopForumSpam i CleanTalk. Nie działają, gdy jedynym problemem jest captcha albo zbyt szybkie wysłanie. Klient, który przejdzie kontrole, nie jest tym dotknięty.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Dodatkowe działania** | nic nie zaznaczone | **Zablokuj adres IP**: włącz, gdy ten sam adres wraca. Kolejna wiadomość z tego IP jest odrzucana, dopóki nie wyłączysz blokady. Współdzielone IP biura blokuje wtedy każdego klienta, który z niego korzysta. **Powiadom sklep e-mailem**: włącz, gdy chcesz wiadomość w skrzynce. Jeden e-mail na IP, potem cisza przez 30 minut. Wyłączenie zostawia zablokowany spam tylko na liście prób. **Przekieruj na stronę główną**, **Przekieruj na stronę CMS** i **Przekieruj do Google**: zostaw wyłączone, żeby odwiedzający został na stronie kontaktowej i przeczytał błąd. Gdy zaznaczysz kilka przekierowań, najpierw jest strona główna, potem strona CMS, na końcu Google. |
| **Strona CMS** | pierwsza strona z listy sklepu | Używana, gdy zaznaczono **Przekieruj na stronę CMS**. Wybierz krótką stronę, która mówi, że wiadomość nie została wysłana. Gdy sklep nie ma stron CMS, na liście jest **Brak strony CMS**. Bez wybranej strony przekierowanie CMS jest pomijane. Gdy zaznaczono też **Przekieruj do Google**, potem używane jest Google. W przeciwnym razie odwiedzający zostaje na stronie kontaktowej z komunikatem. Klient, który przejdzie kontrole, tej strony z powodu modułu nie zobaczy. Strony na liście są stronami CMS tego sklepu. Gdy sklep już ma strony, pusta zapisana wartość nie jest na liście, więc widać pierwszą stronę. Kliknij **Zapisz** tylko wtedy, gdy to jest strona, której chcesz. |

### 3.10 E-mail

![E-mail](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-mail.webp)

Panel **E-mail do sklepu** ustawia temat wiadomości wysyłanej na adres sklepu, gdy wiadomość zostanie zablokowana. E-mail idzie tylko wtedy, gdy na **Ochronie** zaznaczono **Powiadom sklep e-mailem**, i tylko dla blokad innych niż nieudana captcha albo zbyt szybkie wysłanie. Jeden e-mail idzie przy pierwszej blokadzie z danego IP. Kolejne blokady z tego IP przez 30 minut nie wysyłają poczty. Przyjęty klient tego e-maila nie wywołuje. Gdy e-mail sklepu w Parametrach sklepu jest pusty, poczta nie idzie.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Temat** | Contact form spam blocked | Temat powiadomienia dla sklepu. Na końcu dopisywana jest krótka nazwa kontroli, na przykład [flood]. Wiadomość idzie na e-mail sklepu z Parametrów sklepu. Daj krótki temat, który rozpoznają reguły skrzynki, uzupełniony dla każdego języka sklepu. Pusty temat jest zastępowany tekstem Contact form spam blocked. Temat nie zmienia tego, kto jest blokowany. |

Przycisk języka przełącza temat na inny język sklepu. Treść e-maila bierze się z szablonu modułu dla tego języka. Polska treść zaczyna się od **Formularz kontaktowy zablokowany**, a potem podaje kontrolę, IP, e-mail, datę i początek wiadomości.

### 3.11 Aktualizacje

![Aktualizacje](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-updates.webp)

Ta strona pyta MyPresta.eu, czy jest nowsza wersja modułu. Ustawienia tutaj dotyczą tylko sprawdzania aktualizacji. Nie zmieniają ochrony strony kontaktowej.

| Pole | Na starcie | Co robi |
|---|---|---|
| **Sprawdź aktualizacje** | — | **Sprawdź teraz** od razu pyta MyPresta.eu, czy jest nowsza wersja. Użyj po instalacji i ponownie przed okresem dużego ruchu. Przycisk nie pobiera i nie instaluje pliku. Gdy serwer sklepu nie połączy się z MyPresta.eu, kliknięcie nie pokaże nowej wersji. |
| **Powiadomienia o aktualizacjach** | Włącz | **Włącz** sprawdza MyPresta.eu i pokazuje komunikat w zapleczu, gdy wyjdzie nowsza wersja. Automatyczne sprawdzenie idzie mniej więcej co 3 dni, gdy pracujesz w zapleczu. **Wyłącz** zatrzymuje to sprawdzenie i komunikat. Nowa wersja zostaje wtedy niezauważona, dopóki nie klikniesz **Sprawdź teraz**. Ten wybór nie zmienia ochrony formularza. |
| **Strona modułu** | Contact page - spam protection PRO | Bezpośredni link do strony modułu na MyPresta.eu. Historia zmian na tej stronie pokazuje, co się zmieniło. Otwórz ją przed aktualizacją. Link nie instaluje pliku. Gdy strona się nie ładuje, otwórz adres w nowej karcie. |

**Zapisz** potwierdza **Ustawienia aktualizacji zostały zapisane.**

Gdy jest nowsza wersja, zaplecze może pokazać **Dostępna jest nowa wersja, sprawdź http://MyPresta.eu, aby uzyskać więcej informacji** oraz **Więcej szczegółów w historii zmian**. **Sprawdź teraz** odpowiada **Dostępna jest nowa wersja!** albo **Moduł jest aktualny!**

### 3.12 Próby wysłania wiadomości

![Próby wysłania wiadomości](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-attempts.webp)

Otwórz **Próby wysłania wiadomości** pod **Ochroną formularza kontaktowego** albo przycisk o tej nazwie na **Przeglądzie**.

Sklep zapisuje wiersz, gdy wiadomość kontaktowa jest sprawdzana. Nie ma przycisku dodawania. Z tej listy nie edytujesz wiersza. Możesz go usunąć.

Kolumny to **ID**, **IP**, **E-mail**, **Powód**, **Zablokowane** i **Data**. Najnowszy wiersz jest pierwszy. Pusta lista na angielskim zrzucie mówi **No records found**.

**Powód** na tej liście to krótka nazwa, nie długa nazwa z **Przeglądu**:

| Na przeglądzie | Na tej liście |
|---|---|
| **Zablokowany adres IP** | ban |
| **Honeypot** | honeypot |
| **Zbyt szybko** | timing |
| **Pusty user agent** | user-agent |
| **Anty-flood** | flood |
| **Zduplikowana wiadomość** | duplicate |
| **Zbyt wiele linków** | links |
| **Zablokowane słowo** | keyword |
| **Jednorazowy e-mail** | disposable |
| **reCAPTCHA** | recaptcha |
| **StopForumSpam** | stopforumspam |
| **CleanTalk** | cleantalk |

Dopuszczona wiadomość ma pusty powód, a **Zablokowane** ustawione na nie.

Akcja wiersza to usuwanie. Zaznacz wiersze i użyj **Usuń zaznaczone**. Sklep pyta **Usunąć zaznaczone elementy?**

### 3.13 Zablokowane adresy IP

![Zablokowane adresy IP](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-bans.webp)

Otwórz **Zablokowane adresy IP** pod **Ochroną formularza kontaktowego** albo przycisk o tej nazwie na **Przeglądzie**.

Kolumny to **ID**, **IP**, **Data** i **Aktywna**. Najnowszy wiersz jest pierwszy. Pusta lista na angielskim zrzucie mówi **No records found**.

Plus otwiera dodawanie. Tytuł formularza to **Zablokowany adres IP**.

![Nowy zablokowany adres IP](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-ban-form.webp)

| Pole | Na starcie | Co robi |
|---|---|---|
| **Adres IP** | pusty | Jeden adres IP. Wymagany. Dopóki blokada jest aktywna, wiadomości kontaktowe z tego IP są odrzucane. Wklej adres z listy prób, dokładnie tak, jak został zapisany. Błędna cyfra blokuje innego odwiedzającego albo nikogo. Współdzielony adres biura blokuje też prawdziwych klientów na tym IP, dopóki nie wyłączysz blokady. |
| **Aktywna** | Nie | **Tak** utrzymuje blokadę, a formularz odrzuca ten IP. **Nie** zostawia wiersz i przestaje blokować, więc adres może znów pisać, chyba że zatrzyma go inna kontrola. Wybierz **Tak**, dopóki ten adres nadal wysyła spam. Wybierz **Nie**, gdy klient z tego IP ma się dodzwonić, a wpis chcesz zachować. Blokada utworzona z **Ochrony** jest zapisywana już jako aktywna. |

**Zapisz** zapisuje wiersz. Anulowanie wraca do listy bez zapisu.

Na istniejącym wierszu **Edytuj** otwiera ten sam formularz, usuwanie zabiera wiersz, a ikona **Aktywna** włącza albo wyłącza blokadę. Zaznacz wiersze i użyj **Usuń zaznaczone**. Sklep pyta **Usunąć zaznaczone elementy?**

Blokada z **Ochrony** odrzuca następną wiadomość z tego IP z powodem **Zablokowany adres IP** (krótko ban) i nie zakłada drugiej blokady dla tego samego trafienia.

## 4. Front sklepu

Moduł działa tylko na stronie kontaktowej sklepu. Na innych stronach nic nie dokłada.

Przy ustawieniach z instalacji, zanim zapiszesz oba klucze reCAPTCHA, klient widzi zwykły formularz kontaktowy motywu. Na stronie nie ma dodatkowego elementu do zrzutu: honeypot jest poza ekranem, licznik jest ukryty, a pola reCAPTCHA nie ma.

Gdy zapiszesz oba klucze i zostawisz **Włącz reCAPTCHA** na Tak:

- **reCAPTCHA v2** dodaje pole wyboru. Gdy klient wyśle bez zaznaczenia, strona mówi **Potwierdź, że nie jesteś robotem.** i formularz nie idzie.
- **reCAPTCHA v3** nie pokazuje wyzwania. Może pojawić się plakietka Google. Wynik poniżej progu jest odrzucany na serwerze.

| Co się stało | Co widzi klient |
|---|---|
| Pole v2 nie jest zaznaczone | **Potwierdź, że nie jesteś robotem.** Formularz zostaje na stronie. |
| Captcha nie przeszła albo Google nie odpowiedziało | **Weryfikacja captcha nie powiodła się. Spróbuj ponownie.** |
| Inna blokada i żadne przekierowanie nie jest zaznaczone | **Nie udało się wysłać wiadomości. Spróbuj ponownie za kilka minut.** |
| Zaznaczone przekierowanie na stronę główną | Strona główna sklepu. Na stronie kontaktowej nie ma błędu. |
| Zaznaczone przekierowanie na CMS, strona jest wybrana, a przekierowanie na stronę główną nie | Ta strona CMS. |
| Zaznaczone przekierowanie do Google, a pozostałe nie są użyte | https://www.google.com |

Wiadomość, która przejdzie, wysyła formularz kontaktowy jak zwykle. Moduł tego potwierdzenia nie zmienia.

Motyw może podmienić arkusz i skrypt modułu od strony sklepu. Nie podmieni szablonu formularza modułu, bo formularz jest formularzem kontaktowym sklepu. Gdy motyw usunie przycisk wysyłki tego formularza, honeypot, licznik i captcha się nie dopną.

## 5. Problemy

**Klient widzi „Potwierdź, że nie jesteś robotem.”**

Pole v2 nie było zaznaczone. Poproś, żeby je zaznaczył i wysłał ponownie. To nie blokuje IP.

**Klient widzi „Weryfikacja captcha nie powiodła się. Spróbuj ponownie.”**

Captcha nie przeszła albo sklep nie połączył się z Google. Sprawdź, czy **Typ reCAPTCHA** zgadza się z kluczem w konsoli Google, czy **Klucz witryny** i **Klucz tajny** są parą dla tej domeny i czy serwer sklepu łączy się z Google. Nieudana captcha nie blokuje IP. Klient może spróbować ponownie.

**Klient widzi „Nie udało się wysłać wiadomości. Spróbuj ponownie za kilka minut.”**

Inna kontrola odrzuciła wiadomość, a przekierowanie nie jest zaznaczone. Otwórz **Próby wysłania wiadomości**, znajdź IP albo e-mail i przeczytaj **Powód**. Potem:

- flood: podnieś **Dozwolone wiadomości** albo **Przedział czasu**, albo poczekaj, aż okno minie.
- honeypot: skrypt wypełnił ukryte pole albo zrobiło to autouzupełnianie. Wyłącz **Pole honeypot**, gdy blokowani są Twoi klienci.
- timing: formularz poszedł szybciej niż **Minimalna liczba sekund**. Podnoś tę liczbę tylko wtedy, gdy blokowani są prawdziwi klienci. Ta blokada nie blokuje IP.
- user-agent: wyłącz **Blokuj pusty user agent**, gdy w grę wchodzi narzędzie prywatności.
- duplicate: ten sam tekst o długości co najmniej 20 znaków poszedł ponownie w **Oknie duplikatów**.
- links: wiadomość ma więcej linków niż **Maksymalna liczba linków**.
- keyword: wiersz w **Słowach i frazach** pasuje do e-maila albo wiadomości.
- disposable: domena e-maila jest na wbudowanej liście albo w **Dodatkowych domenach jednorazowych**.
- stopforumspam albo cleantalk: adres jest w tej usłudze. Podnieś **Minimalną liczbę zgłoszeń** albo **Próg wskaźnika spamu**, albo dodaj adres do **Białej listy**, gdy to klient.
- ban: adres jest na **Zablokowanych adresach IP** z **Aktywna** ustawioną na **Tak**. Ustaw **Nie** albo usuń wiersz.

**Klient ląduje na stronie głównej, stronie CMS albo w Google.**

Była twarda blokada i na **Ochronie** jest zaznaczone przekierowanie. Odznacz **Przekieruj na stronę główną**, **Przekieruj na stronę CMS** i **Przekieruj do Google**, gdy błąd ma zostać na stronie kontaktowej. Gdy zaznaczonych jest kilka, wygrywa strona główna, potem CMS, potem Google.

**Całe biuro nie może pisać.**

Biuro ma jeden adres IP. Ten IP jest zablokowany, przekroczył anty-flood albo jest w usłudze. Otwórz **Zablokowane adresy IP** i ustaw **Aktywna** na **Nie**, albo dodaj adres na **Białej liście**. Wiersz białej listy pomija wszystkie kontrole, także blokadę.

**reCAPTCHA zostaje wyłączona.**

Ostrzeżenie mówi **reCAPTCHA jest włączona, ale klucz witryny lub klucz tajny jest pusty. Captcha pozostaje wyłączona, dopóki oba klucze nie zostaną zapisane.** Wklej oba klucze i kliknij **Zapisz**.

**Płatny CleanTalk nikogo nie blokuje.**

Ostrzeżenie mówi **Płatne API CleanTalk jest włączone, ale klucz dostępu jest pusty.** Wklej **Klucz dostępu** i kliknij **Zapisz**. Odrzucony klucz też przepuszcza wiadomość. Gdy usługa nie odpowiada, wiadomość przechodzi.

**Do sklepu nie przychodzi e-mail.**

**Powiadom sklep e-mailem** musi być zaznaczone. Blokada musi być czymś innym niż captcha albo zbyt szybkie wysłanie. Ten sam IP wysyła tylko jeden e-mail na 30 minut. E-mail sklepu w Parametrach sklepu musi być wypełniony. Temat dostaje krótką nazwę kontroli, na przykład [flood].

**Sprawdź teraz nic nowego nie pokazuje.**

Serwer sklepu nie połączył się z MyPresta.eu albo moduł jest już aktualny. Odpowiedź **Moduł jest aktualny!** znaczy, że nowszej wersji nie zgłoszono. **Sprawdź teraz** nie pobiera pliku.

**Listy są puste po ponownej instalacji.**

Odinstalowanie kasuje próby i blokady. Nowa instalacja ich nie przywraca.

## 6. Dla developera

### 6.1 Przegląd

Klasa główna `mycontactprotectionpro`, wersja `1.0.0`, autor MyPresta.eu, zakładka `administration`. Nazwa na liście to **Contact page - spam protection PRO**. Zgodność w pliku to PrestaShop 1.7.7.0 do 9.99.99.

Ustawienia są czytane przez `Configuration::get` w kontekście sklepu aktywnym przy **Zapisz**. POST strony kontaktowej z `submitMessage` uruchamia `hookActionFrontControllerInitAfter`. Przejście zapisuje wiersz dopuszczony i pozwala formularzowi wysłać wiadomość. Blokada zapisuje wiersz zablokowany, a twardy powód może dodać ban, wysłać e-mail do sklepu i przekierować.

`install()` woła instalację rodzica, zapisuje konfigurację, tworzy dwie tabele, tworzy menu i rejestruje trzy hooki. Cache nie czyści. Nie ma własnego `enable()` ani `disable()`. `uninstall()` kasuje klucze z 6.7 oraz `update_mycontactprotectionpro` i `updatev_mycontactprotectionpro`, kasuje zakładki menu, robi DROP obu tabel i woła odinstalowanie rodzica. Nie kasuje `mypresta_updates`. Pliki zostają, dopóki nie zniknie katalog modułu.

### 6.2 Pliki

| Plik | Rola |
|---|---|
| mycontactprotectionpro.php | install, uninstall, hooki, formularze, kolejność kontroli, pulpit, e-mail do sklepu |
| controllers/admin/AdminMycontactprotectionpro.php | rodzic menu; przekierowanie do konfiguracji modułu |
| controllers/admin/AdminMycontactprotectionproAttempts.php | lista prób i usuwanie |
| controllers/admin/AdminMycontactprotectionproBans.php | lista blokad, dodawanie, edycja, usuwanie, przełącznik active |
| models/attempt.php | tabela prób i liczniki |
| models/ban.php | tabela blokad i `banIp()` |
| lib/sfs.php | zapytanie StopForumSpam |
| lib/ctalk.php | darmowy i płatny CleanTalk |
| lib/updatesChecker.php | sprawdzenie aktualizacji, klasa `mycontactprotectionproUpdate` |
| lib/recaptcha/ | biblioteka reCAPTCHA używana przez moduł |
| views/templates/admin/configure.tpl | pasek zakładek i znaczniki przeglądu |
| views/css/admin.css | układ konfiguracji w zapleczu |
| views/css/front.css | honeypot poza ekranem |
| views/js/front.js | honeypot, licznik, pole v2 i token v3 na formularzu |
| mails/{iso}/mcpp_merchant.html | treść HTML powiadomienia; nie przechodzi przez `$this->l()` |
| mails/{iso}/mcpp_merchant.txt | treść tekstowa powiadomienia |
| translations/{iso}.php | napisy zaplecza i klienta |
| key.php | wartość wysyłana z darmowym zapytaniem CleanTalk |

Nie ma kontrolera frontu ani szablonu frontu formularza kontaktowego.

### 6.3 Kontrolery

| Klasa | Rodzic w menu | Co przyjmuje |
|---|---|---|
| AdminMycontactprotectionproController | id 0, ikona security, tytuł Contact protection | przekierowanie do AdminModules z `configure=mycontactprotectionpro` |
| AdminMycontactprotectionproAttemptsController | AdminMycontactprotectionpro | tabela `mcpp_attempt`, kolejność `id_mcpp_attempt` DESC, `list_no_link`, usuwanie wiersza, usuwanie masowe. Bez dodawania. |
| AdminMycontactprotectionproBansController | AdminMycontactprotectionpro | tabela `mcpp_ban`, kolejność `id_mcpp_ban` DESC, edycja i usuwanie wiersza, usuwanie masowe, status na `active`. Formularz: `ip` (wymagane) i `active`. |

Konfiguracja jest w `getContent()` modułu, nie w osobnym kontrolerze. Zakładka idzie w `mcpp_tab`. Nazwy wysłania to `submitMcppAntiFlood`, `submitMcppCleanTalk`, `submitMcppStopForumSpam`, `submitMcppRecaptcha`, `submitMcppFilters`, `submitMcppWhitelist`, `submitMcppProtection`, `submitMcppMail`. Formularz aktualizacji wysyła `submit_settings_updates` i `submit_settings_updates_now`.

Kontrolera frontu nie ma. Strona kontaktowa to `ContactController` sklepu.

### 6.4 Hooki

| Hook | Kiedy działa |
|---|---|
| actionFrontControllerSetMedia | na stronie kontaktowej, gdy włączony jest honeypot, licznik albo gotowa reCAPTCHA; dokłada front.css i front.js oraz przekazuje skryptowi ustawienia publiczne |
| actionFrontControllerInitAfter | przy POST strony kontaktowej z submitMessage; robi kontrole i albo wraca, albo zatrzymuje formularz, albo przekierowuje |
| displayBackOfficeHeader | dokłada views/css/admin.css |

Moduł nie rejestruje własnego hooka wyświetlania. Strona kontaktowa jest rozpoznawana po `php_self` równym `contact` albo po klasie `ContactController` lub `ContactControllerCore`.

W zapleczu konstruktor woła `runUpdateSetUp()`. Ta metoda pyta MyPresta mniej więcej co 259200 sekund, gdy `mypresta_updates` nie jest 0, zapisuje wynik w `updatev_mycontactprotectionpro` i dopisuje ostrzeżenie kontrolera, gdy zapisana wersja jest nowsza.

### 6.5 Nadpisania

Moduł nie nadpisuje klas ani kontrolerów.

### 6.6 Baza

Prefiks jest prefiksem sklepu. Wejście na stronę nie dopisuje kolumny. Odinstalowanie kasuje obie tabele.

| Tabela | Zawartość |
|---|---|
| mcpp_attempt | `id_mcpp_attempt` int, klucz główny, `ip` varchar 64, `email` varchar 255, `message_hash` varchar 64 (MD5 wiadomości małymi literami), `reason` varchar 255 (krótka nazwa, pusta gdy dopuszczono), `blocked` tinyint, `date_add` datetime. Klucze `ip_date` (`ip`, `date_add`) i `hash_date` (`message_hash`, `date_add`). |
| mcpp_ban | `id_mcpp_ban` int, klucz główny, `ip` varchar 64, `date_add` datetime, `active` tinyint, domyślnie 1. Klucz `ip_active` (`ip`, `active`). Formularz dodawania otwiera się z Aktywna = Nie. `banIp()` wstawia albo aktualizuje wiersz z `active` 1. |

### 6.7 Klucze i tłumaczenia

Wartość, gdy klucza nie ma:

| Klucz | Gdy brak |
|---|---|
| mcpp_af | 1 |
| mcpp_time | 10 |
| mcpp_atmpt | 5 |
| mcpp_ct | 0 |
| mcpp_ct_paid | 0 |
| mcpp_ct_key | pusty |
| mcpp_ct_rate | 1, a zapisane 0 też jest traktowane jak 1 |
| mcpp_sfs | 0 |
| mcpp_sfs_key | pusty |
| mcpp_sfs_freq | 1, a zapisane 0 też jest traktowane jak 1 |
| mcpp_rc | 1 |
| mcpp_rc_type | 0, czyli v2; 1 to v3 |
| mcpp_rc_site | pusty |
| mcpp_rc_secret | pusty |
| mcpp_rc_theme | light, chyba że zapisane jest dark |
| mcpp_rc_score | 0.5 |
| mcpp_hp | 1 |
| mcpp_tg | 1 |
| mcpp_tg_sec | 3, a zapisane 0 jest traktowane jak 1 |
| mcpp_links | 1 |
| mcpp_links_max | 3 |
| mcpp_kw | 0 |
| mcpp_kw_list | pusty |
| mcpp_disp | 0 |
| mcpp_disp_extra | pusty |
| mcpp_dup | 0 |
| mcpp_dup_min | 60, a zapisane 0 jest traktowane jak 1 |
| mcpp_ua | 0 |
| mcpp_bypass | 0 |
| mcpp_ptype_1 | 0, blokada IP |
| mcpp_ptype_4 | 0, e-mail do sklepu |
| mcpp_ptype_7 | 0, przekierowanie na stronę główną |
| mcpp_ptype_6 | 0, przekierowanie na CMS |
| mcpp_ptype_5 | 0, przekierowanie do Google |
| mcpp_cms | 0 |
| mcpp_wh_ip | pusty |
| mcpp_mtitle | Contact form spam blocked, na język; pusty temat używa tego angielskiego zdania |
| mcpp_dash_preset | 30; inna wartość niż 7, 30, 90, 180, 365 albo custom wraca do 30 |
| mcpp_dash_from | puste, dopóki przegląd nie zbuduje okna |
| mcpp_dash_to | puste, dopóki przegląd nie zbuduje okna |

`mypresta_updates` jest wspólny. Gdy go nie ma, powiadomienia są traktowane jako włączone. Odinstalowanie go nie kasuje. `key.php` ustawia `mkey`. Gdy jest puste, darmowe zapytanie CleanTalk używa `nlc`. Sprawdzenie aktualizacji używa `nokey`, gdy wartości nie ma.

Wbudowane domeny jednorazowe, dopasowywane na domenie i subdomenach: mailinator.com, guerrillamail.com, guerrillamail.info, guerrillamail.biz, guerrillamail.de, guerrillamail.net, guerrillamail.org, guerrillamailblock.com, sharklasers.com, grr.la, yopmail.com, yopmail.fr, yopmail.net, trashmail.com, trashmail.de, trash-mail.com, tempmail.com, temp-mail.org, 10minutemail.com, 10minutemail.net, throwawaymail.com, getnada.com, dispostable.com, maildrop.cc, fakeinbox.com, mailnesia.com, mohmal.com, emailondeck.com, tempail.com, moakt.com, spam4.me, byom.de, mintemail.com, mytemp.email, tmpmail.net, tmpmail.org, discard.email, discardmail.com, inboxkitten.com, getairmail.com, generator.email, mailcatch.com. Domeny z `mcpp_disp_extra` dochodzą tak samo.

Etykiety, opisy pól i trzy zdania dla klienta to `$this->l()` w `mycontactprotectionpro.php`, `lib/updatesChecker.php` (źródło `updatesChecker`), `AdminMycontactprotectionproAttempts.php` (źródło `AdminMycontactprotectionproAttempts`) i `AdminMycontactprotectionproBans.php` (źródło `AdminMycontactprotectionproBans`). Język dodajesz plikiem `translations/{iso}.php`. Opisy pól są w `desc` pól HelperForm w klasie głównej i w kontrolerze blokad.

Treści `mails/{iso}/mcpp_merchant.html` i `mails/{iso}/mcpp_merchant.txt` nie idą przez `$this->l()`. Angielski tekst zaczyna się od `Contact form blocked.` Polski od `Formularz kontaktowy zablokowany`. Temat to `mcpp_mtitle` dla języka wiadomości, z dopisanym krótkim powodem, na przykład ` [flood]`. Poczta idzie na `PS_SHOP_EMAIL`. Pusty e-mail sklepu nic nie wysyła. W treści jest pierwsze 500 znaków wiadomości po zdjęciu znaczników.

### 6.8 Rozszerzanie

Motyw może nadpisać `views/css/front.css` i `views/js/front.js`. Szablonu frontu formularza nie ma, więc motyw nie ma szablonu formularza modułu do nadpisania. Znaczniki formularza należą do formularza kontaktowego sklepu. `front.js` szuka `form [name=submitMessage]`. Gdy tego przycisku nie ma, skrypt wraca i nic nie dodaje.

Nazwa pola honeypot to `mcpp_website`. Nazwa licznika to `mcpp_ts`. Wypełniony honeypot to trafienie. Brak licznika nie jest trafieniem. Licznik z przyszłości jest trafieniem. reCAPTCHA v3 używa akcji `contact`.

Kolejność kontroli jest stała: ban, honeypot, timing, pusty user agent, flood, duplicate, links, keyword, disposable, recaptcha, stopforumspam, darmowy CleanTalk, płatny CleanTalk. Wygrywa pierwsze trafienie. Biała lista i pominięcie zalogowanego wracają, zanim powstanie wiersz. Gdy `protectionEnabled()` jest fałszem i IP nie jest zbanowane, hook wraca bez zapisu. `protectionEnabled()` jest prawdą, gdy którekolwiek z `mcpp_af`, `mcpp_ct`, `mcpp_ct_paid`, `mcpp_sfs`, `mcpp_hp`, `mcpp_tg`, `mcpp_links`, `mcpp_kw`, `mcpp_disp`, `mcpp_dup`, `mcpp_ua` jest 1, albo gdy reCAPTCHA jest gotowa (przełącznik włączony i oba klucze niepuste).

Twarde powody to każdy powód poza `timing` i `recaptcha`. Tylko twardy powód może założyć ban, wysłać e-mail do sklepu i przekierować. Kolejność przekierowania: `mcpp_ptype_7` (strona główna), potem `mcpp_ptype_6`, gdy `mcpp_cms` jest większe od 0, potem `mcpp_ptype_5` (`https://www.google.com`). W przeciwnym razie moduł zdejmuje `submitMessage` i dodaje błąd. Blokada recaptcha używa zdania o captcha. Każda inna blokada, która zostaje na stronie, używa zdania o kilku minutach.

Darmowy CleanTalk jest pomijany, gdy nie ma `openssl_encrypt`. StopForumSpam i CleanTalk przepuszczają wiadomość, gdy zdalne wywołanie padnie. reCAPTCHA blokuje wiadomość, gdy zdalne wywołanie padnie. Flood używa `countByIpSince`, które liczy każdą próbę w oknie. Duplikat używa `countDuplicateSince`, które pomija wiersze z powodem `timing` albo `recaptcha`, i działa tylko gdy długość wiadomości wynosi co najmniej 20.

Wywołania PHP: `curl_init`, gdy istnieje, w przeciwnym razie `file_get_contents` dla StopForumSpam, CleanTalk i sprawdzenia aktualizacji, gdy `allow_url_fopen` jest włączone. `openssl_encrypt` dla darmowego CleanTalk. `json_decode` dla odpowiedzi StopForumSpam, płatnego CleanTalk i reCAPTCHA. Żaden inny moduł nie jest wymagany.

## 7. Pomoc

Strona modułu: https://mypresta.eu/modules/administration-tools/contact-page-spam-protection-pro.html

W sprawie tego modułu zaloguj się na konto klienta na [https://mypresta.eu/](https://mypresta.eu/) i przejdź do kontaktu. Wybierz temat **Support for paid modules**. Formularz podaje, że logowanie jest wymagane. Po zalogowaniu wybierz ten moduł z historii zakupów. Strona to [https://mypresta.eu/contact-form](https://mypresta.eu/contact-form).
