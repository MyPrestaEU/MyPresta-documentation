---
title: "Kod kuponu za polubienie na Facebooku - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop 'Kod kuponu za polubienie na Facebooku' od MyPresta.eu."
sidebar:
  label: "Kod kuponu za polubienie na Facebooku"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook like voucher code na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-voucher-code.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-like-voucher-code/)
>
> ---


# Kod kuponu za polubienie na Facebooku

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i każdego modułu wchodzącego w interakcje z zewnętrznymi API, takimi jak Facebook.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Jest to główny ekran konfiguracji modułu „Kod kuponu za polubienie na Facebooku”, dostępny po instalacji poprzez kliknięcie przycisku „Konfiguruj”. Tutaj zdefiniujesz, jak pojawi się przycisk „Lubię to” na Facebooku i jak będą generowane kody kuponów.

#### **Adres URL strony na Facebooku**
- **Co robi to ustawienie:** Jest to najważniejsze ustawienie. Informuje moduł, którą stronę na Facebooku klienci powinni „Polubić”, aby otrzymać kupon.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawiono na adres URL Twojej strony na Facebooku (np. `https://www.facebook.com/MyPresta.eu`):* Przycisk „Lubię to” w Twoim sklepie będzie bezpośrednio linkował do tej konkretnej strony na Facebooku i śledził polubienia dla niej.
  - *Gdy pozostawiono puste lub ustawiono nieprawidłowo:* Przycisk „Lubię to” nie będzie działał poprawnie lub może linkować do nieistniejącej strony, uniemożliwiając klientom otrzymywanie kuponów.
- **Zalecana wartość:** Wprowadź pełny adres URL swojej oficjalnej strony biznesowej na Facebooku.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoja strona na Facebooku to `https://www.facebook.com/myawesomestore`, wpisz dokładnie ten adres URL tutaj.

#### **Prefiks kodu kuponu**
- **Co robi to ustawienie:** Pozwala dodać niestandardowy prefiks do wszystkich kodów kuponów generowanych przez ten moduł. Pomaga to łatwo zidentyfikować, które kupony pochodzą z Twojej promocji na Facebooku.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawiono na „FB”:* Wszystkie wygenerowane kody kuponów będą zaczynać się od „FB” (np. FB123456).
  - *Gdy pozostawiono puste:* Kody kuponów będą generowane bez określonego prefiksu, co utrudni ich odróżnienie od innych typów kuponów.
- **Zalecana wartość:** Krótki, łatwy do zapamiętania prefiks, taki jak „FB”, „LIKE” lub „SOCIAL”.
- **Scenariusz/przykład dla sprzedawcy:** Użycie „FB” pozwala szybko filtrować kody kuponów w Panelu administracyjnym PrestaShop, aby zobaczyć, ile zostało wygenerowanych za pośrednictwem tego modułu.

#### **Wartość kodu kuponu**
- **Co robi to ustawienie:** Definiuje wartość rabatu kodu kuponu. Może to być stała kwota lub procent.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawiono na „10” i „Procent”:* Klienci otrzymują 10% zniżki.
  - *Gdy ustawiono na „5” i „Kwota”:* Klienci otrzymują zniżkę w wysokości 5 USD (lub Twojej domyślnej waluty).
- **Zalecana wartość:** Wartość, która jest wystarczająco atrakcyjna, aby zachęcić do zakupu, ale także zrównoważona dla Twoich marż zysku (np. 5, 10, 15).
- **Scenariusz/przykład dla sprzedawcy:** Oferowanie „10” i „Procent” dla 10% zniżki to powszechna i skuteczna strategia zachęcania nowych klientów.

#### **Typ kodu kuponu**
- **Co robi to ustawienie:** Określa, czy kod kuponu oferuje rabat procentowy, czy rabat o stałej kwocie.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawiono na „Procent”:* „Wartość kodu kuponu” będzie interpretowana jako procent (np. 10% zniżki).
  - *Gdy ustawiono na „Kwota”:* „Wartość kodu kuponu” będzie interpretowana jako stała kwota pieniężna (np. 10 USD zniżki).
- **Zalecana wartość:** „Procent” jest często bardziej atrakcyjny, ponieważ skaluje się z wartością zamówienia, ale „Kwota” może być skuteczna dla tańszych produktów lub konkretnych promocji.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz dać stałą zniżkę 5 USD niezależnie od wielkości zamówienia, wybierz „Kwota”. Jeśli chcesz dać zniżkę, która rośnie wraz z wartością zamówienia, wybierz „Procent”.

#### **Minimalna kwota kodu kuponu**
- **Co robi to ustawienie:** Ustawia minimalną łączną kwotę zamówienia (przed wysyłką), którą klient musi osiągnąć, aby móc użyć kodu kuponu.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawiono na „50”:* Kupon może być użyty tylko wtedy, gdy łączna kwota koszyka wynosi 50 USD lub więcej.
  - *Gdy pozostawiono puste lub ustawiono na „0”:* Kupon może być użyty dla dowolnej kwoty zamówienia.
- **Zalecana wartość:** Wartość, która zachęca klientów do dodawania większej liczby produktów do koszyka, zwiększając średnią wartość zamówienia (np. 25, 50).
- **Scenariusz/przykład dla sprzedawcy:** Jeśli Twoja średnia wartość zamówienia wynosi 40 USD, ustawienie minimalnej kwoty 50 USD dla kuponu 10% zachęca klientów do dodania dodatkowego produktu, aby zakwalifikować się do zniżki.

#### **Dni ważności kodu kuponu**
- **Co robi to ustawienie:** Definiuje, ile dni wygenerowany kod kuponu będzie ważny od momentu jego wydania.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawiono na „7”:* Kod kuponu wygaśnie 7 dni po otrzymaniu go przez klienta.
  - *Gdy pozostawiono puste lub ustawiono na „0”:* Kod kuponu nie będzie miał daty ważności (lub bardzo długą domyślną ustawioną przez PrestaShop).
- **Zalecana wartość:** Rozsądny przedział czasowy, aby stworzyć poczucie pilności, nie będąc zbyt restrykcyjnym (np. 7, 14, 30 dni).
- **Scenariusz/przykład dla sprzedawcy:** Ustawienie na „7” dni zachęca klientów do dokonania zakupu wcześniej, a nie później, zapobiegając zapomnieniu o kuponie.

#### **Opis kodu kuponu**
- **Co robi to ustawienie:** Pozwala dodać niestandardowy opis do wygenerowanego kodu kuponu w Panelu administracyjnym PrestaShop. Pomaga to śledzić cel kuponu.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawiono na „Promocja Polubienia na Facebooku”:* Ten opis będzie widoczny podczas przeglądania szczegółów kuponu w Panelu administracyjnym PrestaShop, jasno wskazując, skąd pochodzi kupon.
  - *Gdy pozostawiono puste:* Kupon nie będzie miał konkretnego opisu, co utrudni identyfikację jego źródła.
- **Zalecana wartość:** Jasny, zwięzły opis, taki jak „Kupon za polubienie na Facebooku” lub „Promocja w mediach społecznościowych”.
- **Scenariusz/przykład dla sprzedawcy:** Użycie „Promocja Polubienia na Facebooku” pomaga Twojemu zespołowi obsługi klienta zrozumieć kontekst kuponu, jeśli klient ma pytania na jego temat.

#### **Wyświetl blok w**
- **Co robi to ustawienie:** Określa, gdzie blok przycisku „Lubię to” na Facebooku pojawi się w części front office Twojego sklepu.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy wybrano „Nagłówek”:* Blok pojawia się u góry każdej strony.
  - *Gdy wybrano „Lewa kolumna”:* Blok pojawia się w lewym pasku bocznym.
  - *Gdy wybrano „Prawa kolumna”:* Blok pojawia się w prawym pasku bocznym.
  - *Gdy wybrano „Strona produktu”:* Blok pojawia się na poszczególnych stronach produktów.
  - *Gdy wybrano „Stopka”:* Blok pojawia się na dole każdej strony.
- **Zalecana wartość:** „Nagłówek” lub „Strona produktu” dla maksymalnej widoczności i wpływu, lub „Lewa/Prawa kolumna”, jeśli wolisz mniej inwazyjne umieszczenie.
- **Scenariusz/przykład dla sprzedawcy:** Umieszczenie go w „Nagłówku” zapewnia, że każdy odwiedzający go zobaczy. Umieszczenie go na „Stronie produktu” celuje w klientów, którzy są już zainteresowani dokonaniem zakupu.

#### **Wiadomość w wyskakującym okienku kodu kuponu**
- **Co robi to ustawienie:** Jest to wiadomość, którą klienci zobaczą w wyskakującym okienku wraz z kodem kuponu po „Polubieniu” Twojej strony na Facebooku.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawiono na „Dziękujemy za polubienie nas! Oto Twój kod rabatowy: {voucher_code}”:* Klient zobaczy dokładnie tę wiadomość z wstawionym unikalnym kodem.
  - *Gdy pozostawiono puste:* Klient może zobaczyć tylko kod bez towarzyszącego tekstu, co może być mylące.
- **Zalecana wartość:** Przyjazna, jasna wiadomość, która dziękuje klientowi i wyraźnie informuje, że kod jest na zniżkę. **Zawsze dołączaj `{voucher_code}`**, aby wyświetlić rzeczywisty kod.
- **Scenariusz/przykład dla sprzedawcy:** „Dziękujemy za dołączenie do naszej społeczności! Oto specjalna niespodzianka dla Ciebie: {voucher_code}. Życzymy udanych zakupów!”

#### **Tytuł wyskakującego okienka kodu kuponu**
- **Co robi to ustawienie:** Ustawia tytuł wyskakującego okienka, które wyświetla kod kuponu.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawiono na „Twój Ekskluzywny Rabat!”:* Ten tytuł pojawi się u góry wyskakującego okienka.
  - *Gdy pozostawiono puste:* Wyskakujące okienko może mieć ogólny lub brak tytułu, co jest mniej profesjonalne.
- **Zalecana wartość:** Chwytliwy i jasny tytuł, który wzmacnia nagrodę (np. „Twój darmowy kupon!”, „Dziękujemy za polubienie nas!”).
- **Scenariusz/przykład dla sprzedawcy:** „Twój Ekskluzywny Rabat!” natychmiast informuje klienta, że otrzymał cenną nagrodę.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja        | Domyślne / Zalecane | Cel i wpływ
