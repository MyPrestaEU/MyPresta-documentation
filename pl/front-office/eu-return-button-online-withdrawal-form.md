---
title: "Return Button Pro - dokumentacja i instrukcja obsługi"
description: "Skonfiguruj formularz odstąpienia od umowy, zarządzaj sprawami w panelu administracyjnym i rozwiązuj typowe problemy w sklepie z Return Button Pro."
sidebar:
  label: "Return Button Pro - dokumentacja i instrukcja obsługi"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł EU Return Button – Online Withdrawal Form na MyPresta.eu](https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/eu-return-button-online-withdrawal-form/)
>
> ---



Zrzuty ekranu w tej instrukcji pokazują angielski panel administracyjny. Używaj tych samych nazw menu i etykiet, co w tekście poniżej.

## 1. Wymagania

Return Button Pro działa na PrestaShop 1.6, 1.7, 8 i 9. Użyj paczki dopasowanej do sklepu: dedykowana wersja pod PrestaShop 1.6 dla sklepów 1.6 oraz paczka pod PrestaShop 1.7–9 dla nowszych. Gdy w historii zamówień MyPresta.eu są obie paczki, pobierz właściwy ZIP.

- PrestaShop: 1.6.x, 1.7.x, 8.x i 9.x
- PHP: wersje, na których już działa Wasz PrestaShop, w tym starsze środowiska przy PrestaShop 1.6 (PHP 5.6 i PHP 7.x) oraz wersje wymagane przez PrestaShop 1.7–9 (PHP 7.1+ / PHP 8.x według hostingu i sklepu). Moduł jest utrzymywany także pod PHP 7.x oraz bieżące PHP sklepu.
- Rozszerzenia PHP używane przez moduł: JSON, curl (sprawdzanie aktualizacji), fileinfo (kontrola MIME załączników), hash (tokeny i bezpieczeństwo gości)
- Inne moduły: nie są wymagane. Jeśli darmowy moduł Return Button jest zainstalowany i włączony, wyłącz go przed konfiguracją lub użyciem Return Button Pro. Oba nie mogą działać jednocześnie.
- Konta zewnętrzne: brak. Opcjonalne sprawdzanie aktualizacji MyPresta.eu korzysta z internetu w zakładce **Updates**.

## 2. Instalacja

1. Prześlij ZIP modułu w **Modules** → **Module Manager**, następnie zainstaluj i włącz **Return Button Pro**.
2. Po instalacji pod **Customers** pojawia się pozycja **Withdrawals**. Otwórz konfigurację z **Module Manager** → **Return Button Pro** → **Configure** (zakładki: **Dashboard**, **Settings**, **Updates**).
3. Instalacja nie czyści cache PrestaShop. Wyczyść cache samodzielnie po zmianach motywu lub hooków, jeśli front sklepu nadal wygląda źle.

Odinstalowanie: pozycja menu **Withdrawals** znika, a wartości konfiguracji są usuwane. Tabele odstąpień i rekordy spraw zostają w bazie jako dowód prawny. Ponowna instalacja nie kasuje tych rekordów; moduł może z nich korzystać, gdy tabele już istnieją. Przesłane załączniki personelu w folderze modułu nie są usuwane przy odinstalowaniu.

Jeśli aktualizujesz z darmowego Return Button, Pro może skopiować zgodne ustawienia i przenieść dane do pustych tabel Pro z danych darmowego modułu, gdy Pro nie ma jeszcze wierszy. Najpierw wyłącz darmowy moduł.

## 3. Konfiguracja i praca w panelu

### 3.1 Pełny proces odstąpienia

Przebieg od frontu sklepu do obsługi przez personel:

1. Klient znajduje wejście do odstąpienia: przycisk w stopce, link w My Account, przycisk na stronie zamówienia albo adres formularza, gdy dostęp dla gości jest włączony.
2. **Step 1 – order:** zalogowani klienci widzą swoje zamówienia z podpowiedziami kwalifikacji (pozostałe dni, powody niedostępności). Goście wpisują numer referencyjny zamówienia i e-mail. Klient wybiera kwalifikujące się zamówienie, wybiera **Full order** lub **Partial** (z ilościami na dozwolonych pozycjach), opcjonalnie dodaje wiadomość i IBAN, potem przechodzi dalej.
3. **Step 2 – confirm:** klient przegląda podsumowanie oświadczenia. Gdy **Require legal confirmation checkbox** jest włączone, musi zaznaczyć tekst prawny, a następnie wysłać formularz.
4. Moduł zapisuje sprawę, ustawia status **Registered** i wysyła klientowi potwierdzenie (trwały nośnik) oraz powiadomienie do sklepu (i na **Notification email**, gdy jest ustawiony). Strona sukcesu pokazuje numer referencyjny odstąpienia.
5. Personel otwiera **Customers** → **Withdrawals** (lub panel boczny zamówienia), otwiera **View**, ustawia status (**In progress**, **Refunded**, **Rejected** itd.) i wpisuje wiadomość do klienta, gdy jest wymagana.
6. Klient śledzi status przez **Track withdrawal status**, stronę statusu oraz **Print / save PDF**. Wiadomości personelu ze zmian statusu pojawiają się w historii odstąpienia klienta.

Statusy używane przez moduł:

| Pole | Na start | Co robi |
|---|---|---|
| **Pending** | Krótki stan przy pierwszym zapisie oświadczenia | Otwarta sprawa przed zakończeniem potwierdzenia prawnego przez klienta albo gdy personel ustawi ten status później. Liczy się do blokady duplikatów wraz z innymi otwartymi statusami. |
| **Registered** | Po potwierdzeniu przez klienta w kroku 2 | Oświadczenie zapisane; próba wysyłki e-maili potwierdzających. Domyślny status po wysłaniu formularza. |
| **In progress** | Akcja personelu | Sklep obsługuje sprawę (zwroty, kontrole, przygotowanie refundacji). Nadal blokuje drugi aktywny wniosek, gdy blokada duplikatów jest włączona. |
| **Refunded** | Akcja personelu | Sprawa zamknięta z wynikiem refundacji. Widoczne na stronie statusu klienta. |
| **Rejected** | Akcja personelu | Sprawa zamknięta bez refundacji. Użyj jasnej wiadomości do klienta, gdy ustawienie tego wymaga. |

Zakres na formularzu: **Full order** lub **Partial**. Typ: **Contract withdrawal** (opłacone) lub **Contract cancellation (unpaid order)**, gdy zamówienie nigdy nie było opłacone.

### 3.2 Dashboard

Otwórz **Modules** → **Module Manager** → **Return Button Pro** → **Configure** → **Dashboard**.

![Dashboard](https://mypresta.eu/docs/images/docs/rbpro-dashboard.webp)

Filtruj przez **From** / **To** i **Apply** albo zresetuj przez **Last 30 days**. Panel pokazuje sumy od początku, zaległości oczekujące, wykryty profil motywu, aktywny hook stopki, KPI (odstąpienia w okresie, wskaźnik względem zamówień, udział potwierdzeń e-mail, średnia liczba dni od zamówienia do odstąpienia, udział częściowych/pełnych, anulowania, udział refundowanych wśród zamkniętych spraw, wskaźnik odrzuceń), wykres dziennych zgłoszeń, rozkład statusów, najczęściej odstępowane produkty oraz najstarsze oczekujące sprawy z **Open**.

Użyj **Manage all withdrawals**, aby przejść do listy pod **Customers**, albo **Export CSV**, aby pobrać sprawy bieżącego sklepu.

### 3.3 Settings

Otwórz zakładkę **Settings** i po zmianach kliknij **Save**.

![Settings](https://mypresta.eu/docs/images/docs/rbpro-settings.webp)

#### Integracja z motywem

Dopasuj moduł do Classic, Hummingbird lub własnego motywu. Dostosuj te pola, jeśli przyciski lub formularze wyglądają nieostylowane po aktualizacji motywu.

| Pole | Na start | Co robi |
|---|---|---|
| **Storefront theme profile** | Auto-detect | Wybiera, które szablony front-office i CSS ładuje moduł (Classic vs Hummingbird). Poprawny wygląd przycisków, układ formularza i linku w My Account. Zostaw Auto-detect, chyba że przycisk wygląda źle po zmianie motywu; wtedy wymuś Classic-type lub Hummingbird-type zgodnie z aktywnym motywem. Po zmianie wyczyść cache PrestaShop i odśwież front. |
| **Footer button hook** | Auto (by theme profile) | Określa, gdzie w stopce strony wstrzykiwany jest przycisk odstąpienia. Auto podąża za profilem motywu (Hummingbird → displayFooterBefore, Classic → displayFooter). Jeśli przycisku brakuje lub jest źle wyrównany, wypróbuj ręcznie displayFooterBefore lub displayFooter, zapisz, wyczyść cache i sprawdź stopkę sklepu. Przy ręcznym umieszczeniu wstaw własny hook w szablonie motywu i wybierz tu displayRbproButton; zostaw **Footer button** włączone, aby przycisk pokazywał się tylko w tym szablonie. |

#### Ogólne i dostęp

| Pole | Na start | Co robi |
|---|---|---|
| **Module enabled** | Yes | Główny przełącznik całego modułu. Gdy wyłączony, przyciski odstąpienia, formularz, dostęp gościa i śledzenie są ukryte na froncie; istniejące rekordy w panelu zostają. Użyj tego przy konserwacji lub przeglądzie prawnym bez odinstalowywania. |
| **Public status tracking page** | Yes | Włącza publiczną stronę, na której klienci sprawdzają status odstąpienia po numerze referencyjnym + e-mailu (bez logowania). Ogranicza zgłoszenia „gdzie jest mój zwrot?”. Włącz, jeśli chcesz link **Track withdrawal status** obok przycisku w stopce; podawaj numer referencyjny z e-maila potwierdzającego. Wyłącz, jeśli status obsługujesz tylko mailowo lub telefonicznie. |
| **Guest access (order ref + email)** | Yes | Pozwala niezalogowanym klientom otworzyć formularz po wpisaniu numeru referencyjnego zamówienia i e-maila w kroku 1. Zalecane dla B2C sprzedaży na odległość w UE. Wyłącz, jeśli odstępować mogą tylko zalogowani. Sesje gościa używają podpisanego cookie. |
| **Block duplicate active requests** | Yes | Blokuje drugie otwarte odstąpienie dla tego samego zamówienia, gdy już jest **Pending**, **Registered** lub **In progress**. Unika duplikatów spraw i sprzecznych refundacji. Zostaw włączone na produkcji. Wyłącz tylko do testów lub nietypowych procesów częściowych roszczeń. |
| **Require legal confirmation checkbox (step 2)** | Yes | Wymusza zaznaczenie prawnie sformułowanego checkboxa przed wysłaniem. Jawny zapis zgody zgodny z regułami odstąpienia UE. Edytuj tekst checkboxa per język w Texts & SEO. Gdy wyłączone, zgłoszenie i tak jest logowane bez obowiązkowego zaznaczenia. |
| **Require message to customer when changing status** | Yes | Personel musi wpisać wiadomość do klienta przed aktualizacją statusu. Wiadomość trafia do ścieżki audytu i na stronę statusu klienta. Wyłącz tylko, gdy potrzebujesz szybkich zmian statusu bez pisania za każdym razem. |
| **Show deadline countdown to customer** | Yes | Pokazuje, ile dni pozostało w ustawowym terminie odstąpienia (lista zamówień i formularz). Wymaga poprawnego mapowania **Order state = delivered** i okresu odstąpienia. Jeśli daty wyglądają źle, sprawdź historię zamówienia i status dostarczenia. |
| **Optional IBAN field** | No | Dodaje opcjonalne pole IBAN na formularzu do wypłat refundacji. Włącz tylko, gdy refundujesz przelewem, a polityka prywatności to obejmuje. Zostaw wyłączone, gdy refundujesz wyłącznie na oryginalną metodę płatności. |
| **Notification email** | Empty | Dodatkowy adres otrzymujący powiadomienia o nowych odstąpieniach (oprócz kontaktu sklepu). Przykład: returns@yourshop.com. Zostaw puste, aby używać tylko domyślnego przepływu poczty PrestaShop bez tego odbiorcy. |

#### Reguły odstąpienia

| Pole | Na start | Co robi |
|---|---|---|
| **Withdrawal period (days from delivery)** | 14 | Dni kalendarzowe, w których klient może odstąpić po uznaniu zamówienia za dostarczone. Domyślnie 14 dla umów na odległość w UE. Zmieniaj tylko, gdy prawo lub regulamin wymaga innej wartości. Odliczanie startuje od daty dostawy z historii zamówienia i **Order state = delivered**. |
| **Order state = delivered** | Auto | Status zamówienia oznaczający dostarczenie towaru (start okresu odstąpienia). Wybierz status ustawiany przy dostarczeniu paczki (np. Delivered albo Shipped, jeśli to Twój stan końcowy). Auto bierze rozsądną domyślną wartość ze sklepu; nadpisz, jeśli terminy liczą się od złej daty. |
| **Allowed order statuses** | All order statuses | Steruje, kiedy klient może złożyć odstąpienie na podstawie bieżącego statusu zamówienia. Wybierz **All order statuses**, aby pominąć filtr, albo **Only selected statuses** i przenieś statusy z lewej kolumny do **Allowed for withdrawal**. Zamówienia poza listą pokazują się jako niedostępne na liście zamówień w koncie. |
| **Excluded products** | Empty | Konkretne produkty wyłączone z odstąpienia (towary zapieczętowane, spersonalizowane itd.). Szukaj po nazwie lub trzymaj ID; wykluczone pozycje pokazują komunikat wykluczenia na formularzu. |
| **Excluded product variants** | Empty | Konkretne warianty wyłączone z odstąpienia. Wyszukaj produkt, potem wybierz wariant. |
| **Excluded categories** | Empty | Wszystkie produkty z tych kategorii są niedostępne do odstąpienia. |
| **Excluded manufacturers** | Empty | Produkty tych producentów nie mogą być odstąpione. |
| **Excluded suppliers** | Empty | Produkty powiązane z tymi dostawcami nie mogą być odstąpione. |
| **Excluded customer groups** | Empty | Klienci z tych grup w ogóle nie mogą korzystać z odstąpienia (brak dostępu do formularza, ukryte przyciski). |

#### Stopka i wygląd

| Pole | Na start | Co robi |
|---|---|---|
| **Footer button** | Yes | Pokazuje główne wezwanie do odstąpienia w stopce sklepu (hook skonfigurowany wyżej). Wyłącz, jeśli chcesz tylko linki w My Account i na szczegółach zamówienia. Wymaga **Module enabled** i poprawnego hooka stopki. |
| **Footer theme** | Light footer (dark text) | Schemat kolorów tekstu i linków w stopce (nie tła przycisku). Wybierz Light na jasnych stopkach, Dark na czarnych/ciemnych, aby **Track withdrawal status** pozostał czytelny. Po zmianie wyczyść cache. |
| **Footer alignment** | Center | Wyrównanie poziome bloku przycisku w stopce: Left, Center lub Right. Dotyczy tylko wyjścia hooka stopki. |
| **Button color** | #2563eb | Kolor tła przycisków odstąpienia (stopka, szczegóły zamówienia itd.). Wybierz hex z wystarczającym kontrastem względem białego tekstu. Nie zmienia globalnie koloru primary motywu. |
| **Custom CSS** | Empty | Dodatkowy CSS na stronach, na których pojawiają się przyciski modułu. Używaj do marginesów, fontów lub ukrywania elementów bez edycji plików motywu. Najpierw testuj na stagingu. |
| **Link in customer account** | Yes | Dodaje wejście do odstąpienia w My Account. Zalecane włączone. Wyłącz tylko, gdy polegasz wyłącznie na stopce lub linkach zamówienia. |
| **Link on order detail** | Yes | Pokazuje akcję odstąpienia na stronie szczegółów zamówienia, gdy zamówienie kwalifikuje się. Zablokowane zamówienia pokazują krótki powód zamiast przycisku. |

#### Teksty i SEO

Wypełnij każdy aktywny język sklepu.

| Pole | Na start | Co robi |
|---|---|---|
| **Noindex on form page** | Yes | Dodaje robots noindex,nofollow na URL formularza odstąpienia, aby strony prawne/formularz nie trafiały do wyników wyszukiwania. Wyłącz tylko, jeśli celowo chcesz indeksować formularz. |
| **Button label** | Withdraw from contract | Tekst na wszystkich przyciskach i linkach odstąpienia. Krótka etykieta najlepiej działa w stopce. Główna fraza widoczna dla klienta. |
| **Exclusion message** | This product is excluded from the statutory right of withdrawal. | Pokazywany przy wykluczonych produktach na formularzu. Wyjaśnij, dlaczego pozycji nie da się wybrać; w razie potrzeby wspomnij regulamin. |
| **SEO title** | Withdraw from contract | Tytuł HTML strony formularza (karta przeglądarki). Trzymaj poniżej ok. 60 znaków na język. |
| **SEO description** | Online withdrawal form for distance contracts. | Meta description formularza. Przy włączonym noindex zwykle bez wpływu na ranking. Zostaw puste, aby pominąć. |
| **Legal confirmation checkbox text** | I confirm that I am submitting a withdrawal statement and understand the legal consequences. | Etykieta obok obowiązkowego checkboxa w kroku 2. Użyj jasnego, krajowo adekwatnego brzmienia. Wymagane, gdy **Require legal confirmation checkbox** jest włączone. |

### 3.4 Updates

Otwórz zakładkę **Updates**.

| Pole | Na start | Co robi |
|---|---|---|
| **Manual Check** | — | Sprawdza na MyPresta.eu nowszą wersję modułu. Zobaczysz **New version available!** lub **Module is up to date!**. Wymaga curl i wychodzącego HTTPS. |
| **Automatic Notifications** | Enabled (module default for update prefs) | Gdy włączone, panel może pokazać powiadomienie o nowej wersji. Zapisz przez **Save**. |
| **Product Page** | Link on form | Otwiera oficjalną stronę produktu z informacjami o wydaniach. Pomoc do płatnego modułu: Support (§7) po zalogowaniu. |

Jeśli darmowy Return Button jest nadal włączony, ustawienia i akcje aktualizacji są zablokowane, dopóki go nie wyłączysz.

### 3.5 Lista Withdrawals

Przejdź do **Customers** → **Withdrawals**.

![Withdrawals list](https://mypresta.eu/docs/images/docs/rbpro-withdrawals.webp)

Domyślne sortowanie: najnowsze zgłoszenie na górze. Kolumny:

| Pole | Na start | Co robi |
|---|---|---|
| **ID** | Auto | Wewnętrzny identyfikator sprawy. |
| **Submitted** | From form | Data i godzina wysłania przez klienta. |
| **Order** | From order | Numer referencyjny zamówienia PrestaShop. |
| **First name** / **Last name** / **Email** | From customer | Tożsamość kontaktowa w sprawie. |
| **Scope** | Full order or Partial | Czy odstąpiono całe zamówienie, czy wybrane pozycje. |
| **Type** | Contract withdrawal or cancellation | Odstąpienie od umowy płatnej vs anulowanie nieopłaconego zamówienia. |
| **Status** | Registered after confirm | Bieżący status sprawy (**Pending**, **Registered**, **In progress**, **Refunded**, **Rejected**). |
| **Email** | Yes/No | Czy e-mail potwierdzający został zapisany jako wysłany. |

Używaj wyszukiwania i sortowania na liście. Otwórz sprawę przez **View**. Nie ma akcji **Add new**: wnioski tworzą wyłącznie klienci na froncie. Jeśli ktoś próbuje utworzyć sprawę w panelu, ostrzeżenie wyjaśnia, że odstąpień nie można tworzyć ręcznie, i ponownie pokazuje listę.

Eksportuj CSV z **Dashboard** (**Export CSV**), gdy potrzebujesz arkusza spraw dla sklepu.

### 3.6 Widok sprawy odstąpienia

Otwórz wiersz przez **View**.

Nagłówek pokazuje numer referencyjny, ID, datę zgłoszenia, status, typ, zakres, flagę i czas wysyłki e-maila, termin, IP, user-agent, imię i e-mail klienta oraz link do zamówienia PrestaShop. Blok produktów wymienia każdą odstąpioną pozycję z ilością i ceną jednostkową. IBAN i wiadomość klienta pojawiają się, gdy klient je podał.

**Update status**

1. Wybierz **New status**.
2. Wpisz **Message to customer** (wymagane, gdy to ustawienie jest włączone; w przeciwnym razie opcjonalne). Tekst pomocy wyjaśnia, że wiadomość pojawia się w historii odstąpienia na froncie.
3. Kliknij **Update status**.

Sukces: **Status updated.** Inne komunikaty: **Please enter a message for the customer when changing the status.**, **Status is already set to this value.**, **Invalid status.**, **Could not update status.**

**Resend confirmation email** ponownie wysyła potwierdzenie do klienta, aktualizuje flagę wysyłki przy sukcesie i loguje zdarzenie. Sukces: **Confirmation email sent.** Błąd: **Could not send email.**

**Internal notes** są tylko dla personelu. Wpisz tekst i kliknij **Add note**. Notatki pojawiają się pod **Internal notes** i w ścieżce audytu; nie zastępują wiadomości do klienta przy zmianie statusu.

**Attachments** przyjmują uploady personelu (PDF i typowe obrazy, max 10 MB). Pobierz, klikając nazwę pliku. Komunikaty: **Attachment uploaded.**, **Invalid file or size over 10 MB.**, **File type not allowed.**, **Upload failed.**

**Audit trail** wymienia datę, zdarzenie, pracownika i szczegóły (przejścia statusów i wiadomości). Typowe zdarzenia: klient wysłał oświadczenie, klient potwierdził oświadczenie prawne, zaktualizowano status, wysłano e-mail potwierdzający, dodano dokument, dodano notatkę wewnętrzną.

Użyj **Back to list**, aby wrócić do **Withdrawals**.

### 3.7 Panel boczny zamówienia w panelu administracyjnym

Na PrestaShop 1.7.7 i nowszych otwórz zamówienie w panelu. Gdy zamówienie ma sprawy odstąpienia, boczny blok **Withdrawal requests** wymienia każdy numer referencyjny, odznakę statusu, datę oraz **View** (otwiera sprawę). Na starszych buildach 1.7 bez hooka bocznego zamówienia użyj **Customers** → **Withdrawals** i filtruj po numerze referencyjnym zamówienia.

Oczekujące sprawy mogą też wywołać ostrzeżenie w panelu z liczbą wniosków do przeglądu i linkiem do listy.

## 4. Front sklepu

Tu nie ma zrzutów frontu; podepnij motyw i sprawdź żywy sklep po zapisaniu **Settings** i wyczyszczeniu cache.

### 4.1 Stopka

Przy włączonym **Footer button** i poprawnym hooku strony pokazują przycisk odstąpienia (etykieta z **Button label**) w stylu **Button color** oraz **Track withdrawal status**, gdy publiczne śledzenie jest włączone. **Footer alignment** i **Footer theme** sterują układem i kontrastem tekstu. Jeśli motyw nigdy nie wywołuje wybranego hooka stopki, zmień hook albo umieść własny hook w szablonie i wybierz tę opcję w **Footer button hook**.

### 4.2 Konto klienta

Przy włączonym **Link in customer account** My Account pokazuje wejście do odstąpienia (oraz link śledzenia, gdy szablon konta go zawiera). Wykluczone grupy klientów nie widzą punktów wejścia.

### 4.3 Szczegóły zamówienia

Przy włączonym **Link on order detail** kwalifikujące się zamówienia pokazują przycisk odstąpienia wstępnie wypełniony dla tego zamówienia. Istniejące sprawy dla zamówienia są wymienione ze statusem. Niekwalifikujące się zamówienia pokazują krótki powód zamiast przycisku, np. koniec okresu, niedozwolony status, aktywny duplikat albo brak kwalifikujących się produktów.

### 4.4 Dostęp gościa

Gdy **Guest access** jest włączone, gość otwiera formularz, wpisuje numer referencyjny zamówienia i e-mail, potem kontynuuje jak zalogowany klient dla tego zamówienia. Gdy dostęp gościa jest wyłączony, goście widzą, że muszą się zalogować (albo włączyć dostęp gościa w **Settings**). Nieprawidłowe tokeny bezpieczeństwa i zbyt wiele prób pokazują jasne komunikaty o oczekiwaniu / ponowieniu.

### 4.5 Śledzenie statusu

**Track withdrawal status** prosi o numer referencyjny odstąpienia (format jak RBP-…) i e-mail, potem pokazuje status, datę zgłoszenia, zakres, stan e-maila potwierdzającego oraz linki do szczegółów i druku. Zła para: **No withdrawal found for these details.**

### 4.6 Strona statusu i druk

Po wysłaniu **Withdrawal submitted** pokazuje numer referencyjny, checklistę (oświadczenie zapisane, e-mail potwierdzający, sklep przetworzy sprawę), potem **View withdrawal details**, **Track status** oraz **Print / save PDF**. Strona statusu wymienia produkty, ilości, ceny, sumy oraz **Withdrawal history** z wiadomościami personelu ze zmian statusu. Druk otwiera stronę dowodu do wydruku z bezpiecznym tokenem z przepływu potwierdzenia.

## 5. Problemy

### 5.1 Darmowy Return Button nadal włączony

**Objaw:** konfiguracja zablokowana; alert, że włączony jest inny moduł zwrotów; zapis może pokazać, że zmiany nie zostały zapisane, dopóki ten moduł nie zostanie wyłączony.

**Co zrobić:** **Modules** → **Module Manager** → znajdź darmowy Return Button → **Disable**. Potem otwórz ponownie Return Button Pro.

### 5.2 Brak przycisku w stopce

**Objaw:** brak przycisku odstąpienia w stopce.

**Co zrobić:** potwierdź, że **Module enabled** i **Footer button** są włączone. W **Settings** ustaw **Footer button hook** na Auto albo wypróbuj kolejno inne pozycje stopki. Wyczyść cache i twardo odśwież sklep. Przy własnych motywach umieść własny hook modułu w szablonie i wybierz tę opcję w **Footer button hook**. Otwórz **Dashboard**: pokazuje wykryty profil motywu i nazwę aktywnego hooka stopki do porównania z motywem.

### 5.3 „Return not available — the withdrawal period has ended.”

**Objaw:** szczegóły zamówienia lub formularz blokują odstąpienie tym komunikatem.

**Co zrobić:** sprawdź **Withdrawal period** i **Order state = delivered**. Popraw historię zamówienia, jeśli dostawa nigdy nie została zapisana. Wydłuż okres tylko, jeśli pozwala na to regulamin.

### 5.4 „An active withdrawal request already exists for this order.”

**Objaw:** klient nie może otworzyć drugiej sprawy.

**Co zrobić:** zakończ lub zamknij istniejącą sprawę (**Refunded** / **Rejected**) albo tymczasowo wyłącz **Block duplicate active requests** tylko, gdy proces naprawdę dopuszcza wiele otwartych roszczeń.

### 5.5 „This order status does not allow withdrawal.”

**Objaw:** zamówienie poza filtrem dozwolonych statusów.

**Co zrobić:** w **Settings** ustaw **Allowed order statuses** na **All order statuses** albo dodaj bieżący status zamówienia do **Allowed for withdrawal**.

### 5.6 „No products in this order are eligible for withdrawal.” / komunikat wykluczenia przy pozycjach

**Objaw:** wszystkie pozycje wykluczone albo wybrane częściowe pozycje nieprawidłowe.

**Co zrobić:** przejrzyj wykluczone produkty, warianty, kategorie, producentów i dostawców. Dostosuj **Exclusion message**, aby klienci rozumieli powód.

### 5.7 „Withdrawal is not available for your customer account.”

**Objaw:** formularz lub przyciski ukryte dla zalogowanego klienta.

**Co zrobić:** usuń grupę klienta z **Excluded customer groups** albo przenieś klienta do dozwolonej grupy.

### 5.8 „Please enter a message for the customer when changing the status.”

**Objaw:** aktualizacja statusu w widoku sprawy kończy się niepowodzeniem.

**Co zrobić:** wypełnij **Message to customer** albo wyłącz **Require message to customer when changing status**, jeśli proces dopuszcza puste wiadomości.

### 5.9 E-mail potwierdzający nie wysłany

**Objaw:** sprawa pokazuje niewysłany e-mail; klient nie ma trwałego potwierdzenia.

**Co zrobić:** popraw ustawienia poczty PrestaShop, sprawdź spam, użyj **Resend confirmation email**. Ustaw **Notification email** dla kopii dla personelu. Potwierdź, że kontaktowy e-mail sklepu działa.

### 5.10 Gość nie znajduje zamówienia

**Objaw:** **No order found for the given details.** albo oczekiwanie po limicie prób.

**Co zrobić:** dopasuj dokładny numer referencyjny zamówienia i e-mail zamówienia. Poczekaj przy zbyt wielu próbach. Potwierdź, że **Guest access** jest włączone.

### 5.11 Sprawdzanie aktualizacji nie działa lub milczy

**Objaw:** ręczne sprawdzenie nie raportuje wersji.

**Co zrobić:** upewnij się, że curl działa i serwer dociera do MyPresta.eu. Wyłącz darmowy moduł, jeśli Pro jest zablokowany. Ponów **Manual Check** w zakładce **Updates**.

## 6. Dla programistów

### 6.1 Przegląd

- Technical name: `rbpro`
- Version: bieżąca paczka 1.7–9 (np. 1.4.6); PrestaShop 1.6 ma osobną paczkę (np. 1.4.5) z `ps_versions_compliancy` min `1.6.0.0`
- Display name: Return Button Pro
- Author: MyPresta.eu
- Tab: `front_office_features`
- Main class: `Rbpro`
- `ps_versions_compliancy` w paczce 1.7–9: min `1.7.0.0`; w paczce 1.6: min `1.6.0.0`
- Service layer: `RbpWithdrawalService`; security: `RbpSecurity`; theme/hooks: `RbpCompatibility`; analytics: `RbpStatsService`
- Flow: Configuration keys → hooks / front controllers → `rbp_withdrawal*` tables → admin `AdminRbpWithdrawal` → customer status/track/print

### 6.2 Ważne pliki

| Path | Role |
|---|---|
| `rbpro.php` | Bootstrap modułu, install/uninstall, zakładki konfiguracji, hooki, wartości domyślne |
| `classes/RbpWithdrawal.php` | Model obiektu sprawy i statusy |
| `classes/RbpWithdrawalService.php` | Kwalifikacja, terminy, create/confirm, e-maile, aktualizacje statusu |
| `classes/RbpSecurity.php` | CSRF, grant gościa, rate limit, sanityzacja IBAN |
| `classes/RbpCompatibility.php` | Profil motywu, rozwiązywanie hooka stopki, URL-e admina, wymagane hooki |
| `controllers/admin/AdminRbpWithdrawalController.php` | Lista i widok sprawy |
| `controllers/front/form.php` | Formularz dwuetapowy |
| `controllers/front/confirm.php` | Strona sukcesu |
| `controllers/front/track.php` | Publiczne śledzenie |
| `controllers/front/status.php` | Szczegóły sprawy dla klienta |
| `controllers/front/print.php` | Wydrukowalny dowód |
| `sql/install.sql` | Tworzy tabele `rbp_*` |
| `sql/uninstall.sql` | Tylko komentarz — tabele zostają |
| `lib/updateChecker.php` | UI aktualizacji MyPresta (`rbproUpdate`) |
| `views/templates/admin/*` | **Dashboard**, powłoka konfiguracji, widok sprawy, powiadomienie boczne zamówienia |
| `views/templates/front/*` | Formularz, confirm, track, status, print, error |
| `views/templates/hook/*` | Przyciski stopki/konta/zamówienia (classic / hummingbird) |
| `mails/*` | Szablony `rbf_withdrawal_customer` / `rbf_withdrawal_admin` |
| `translations/*.php` | Tłumaczenia paczki |

### 6.3 Kontrolery

| Controller | Parent / entry | Notes |
|---|---|---|
| Configure (`getContent`) | Module Manager | Zakładki `rbp_tab`: `dashboard`, `settings`, `updates` |
| `AdminRbpWithdrawal` | Customers → Withdrawals | `add`/`edit` false; ścieżka create tylko do podglądu; eksport CSV; pobieranie załączników |
| Front `form` | Module link | Kroki 1–2; lookup gościa; cookie draftu |
| Front `confirm` | Module link | Sukces po wysłaniu |
| Front `track` | Module link | Numer referencyjny + e-mail |
| Front `status` | Module link | Oś czasu + produkty |
| Front `print` | Module link | Token HMAC na numerze referencyjnym |

Uprawnienia wynikają z zakładki admina. Kontrolery frontu wymagają włączonego modułu dla formularza; śledzenie respektuje `RBP_ENABLE_STATUS_TRACK`.

### 6.4 Hooki

Zarejestrowane: `displayHeader`, `actionFrontControllerSetMedia`, `displayCustomerAccount`, `displayOrderDetail`, `actionPresentOrder`, `displayFooter`, `displayFooterBefore`, `displayFooterAfter`, `displayRbproButton`; na PS ≥ 1.7.7 także `displayBackOfficeHeader`, `displayAdminOrderSide`.

Wykonywane przez moduł: `actionRbpWithdrawalCreated`, `actionRbpWithdrawalConfirmed` (oraz hooki związane ze statusem z serwisu, gdzie zdefiniowane).

Wyjście stopki działa tylko dla nazwy hooka rozwiązanej przez `RbpCompatibility::getFooterHookName()`.

### 6.5 Override

Brak override klas ani kontrolerów. Integracja z motywem tylko przez hooki i wybieralne szablony.

### 6.6 Baza danych

| Table | Content |
|---|---|
| `PREFIX_rbp_withdrawal` | Nagłówek sprawy: sklep, zamówienie, klient, numer referencyjny, zakres, typ, status, IBAN, wiadomość, IP, UA, język, flagi e-mail, termin, daty |
| `PREFIX_rbp_withdrawal_product` | Wybrane pozycje i ilości |
| `PREFIX_rbp_withdrawal_note` | Wewnętrzne notatki personelu |
| `PREFIX_rbp_withdrawal_attachment` | Metadane uploadów personelu |
| `PREFIX_rbp_withdrawal_history` | Zdarzenia audytu |

Odinstalowanie **nie** usuwa tych tabel. `ensureDatabase()` tworzy brakujące tabele i może migrować z `rbf_*`, gdy tabele Pro są puste, a darmowe mają wiersze.

### 6.7 Klucze konfiguracji i tłumaczenia

Domyślne z `Rbpro::CONFIG`:

| Key | Default |
|---|---|
| `RBP_ENABLED` | 1 |
| `RBP_GUEST_ENABLED` | 1 |
| `RBP_IBAN_ENABLED` | 0 |
| `RBP_WITHDRAWAL_DAYS` | 14 |
| `RBP_DELIVERED_STATUS` | 0 (Auto) |
| `RBP_EXCLUDED_PRODUCTS` / `_COMBINATIONS` / `_CATEGORIES` / `_MANUFACTURERS` / `_SUPPLIERS` / `_CUSTOMER_GROUPS` | empty |
| `RBP_ALLOWED_ORDER_STATES` | empty |
| `RBP_ALLOWED_ORDER_STATES_RESTRICT` | 0 |
| `RBP_FOOTER_ENABLED` | 1 |
| `RBP_FOOTER_THEME` | light |
| `RBP_FOOTER_POSITION` | center |
| `RBP_BUTTON_COLOR` | `#2563eb` |
| `RBP_CUSTOM_CSS` | empty |
| `RBP_SHOW_ACCOUNT` / `RBP_SHOW_ORDER` | 1 |
| `RBP_SEO_NOINDEX` | 1 |
| `RBP_ADMIN_EMAIL` | empty |
| `RBP_BLOCK_DUPLICATE` | 1 |
| `RBP_SHOW_DEADLINE` | 1 |
| `RBP_REQUIRE_CHECKBOX` | 1 |
| `RBP_REQUIRE_STATUS_MESSAGE` | 1 |
| `RBP_THEME_TYPE` | auto |
| `RBP_FOOTER_HOOK` | auto |
| `RBP_ENABLE_STATUS_TRACK` | 1 |

Wielojęzyczne (poza tablicą `CONFIG`, instalowane domyślnie): `RBP_BUTTON_TEXT`, `RBP_EXCLUSION_MSG`, `RBP_SEO_TITLE`, `RBP_SEO_DESC`, `RBP_LEGAL_CHECKBOX`. Runtime: `RBP_ADMIN_FOLDER`. Preferencje aktualizacji używają kluczy MyPresta update checker. Migracja z darmowego mapuje `RBF_*` → `RBP_*`, gdy klucze Pro są puste.

Tłumaczenia: `translations/{iso}.php`. Stringi `desc` pól są w `renderConfigurationForm()` przez `$this->l()`.

Statusy: `pending`, `confirmed` (etykieta **Registered**), `processing`, `refunded`, `rejected`.

### 6.8 Rozszerzanie

Nadpisuj hook TPL/CSS w motywie dla `modules/rbpro/...` bez edycji modułu. Umieść `{hook h='displayRbproButton'}` dla własnego umieszczenia przycisku. Nasłuchuj `actionRbpWithdrawalCreated` / `actionRbpWithdrawalConfirmed`. Nie polegaj na override — nie ma żadnych do kaskadowania.

## 7. Wsparcie

Strona produktu: https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html

Pomoc do tego płatnego modułu: zaloguj się na konto klienta na mypresta.eu, otwórz Contact i wybierz **Support for paid modules**. Formularz wymaga logowania dla płatnych modułów; po zalogowaniu wybierz Return Button Pro z historii zakupów.