---
title: "Walidacja VAT w VIES i ustawienie 0% VAT - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla deweloperów modułu PrestaShop „Walidacja VAT w VIES i ustawienie 0% VAT” od MyPresta.eu."
sidebar:
  label: "Walidacja VAT w VIES i ustawienie 0% VAT"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Validate VAT in VIES and set 0% VAT na MyPresta.eu](https://mypresta.eu/modules/ordering-process/validate-vat-in-vies-and-set-0-vat.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/validate-vat-in-vies-and-set-0-vat/)
>
> ---


# Walidacja VAT w VIES i ustawienie 0% VAT

## 1. Wymagania i kompatybilność

Aby zapewnić płynne działanie modułu „Walidacja VAT w VIES i ustawienie 0% VAT”, prosimy o zapoznanie się z poniższymi wymaganiami:

*   **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
*   **Kompatybilność z PHP**: PHP 7.1 - 8.5
*   **Wymagania hostingowe**: Twoje środowisko hostingowe musi obsługiwać standardowe rozszerzenia PHP, takie jak `cURL` (do komunikacji z systemem VIES), `JSON` i `OpenSSL`. Są one zazwyczaj domyślnie włączone u większości nowoczesnych dostawców hostingu.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny obszar konfiguracji modułu, w którym kontrolujesz jego zachowanie i wygląd. Przejdź do **Moduły > Menedżer modułów**, wyszukaj „Walidacja VAT w VIES i ustawienie 0% VAT” i kliknij „Konfiguruj”.

#### **Ustawienia ogólne**

*   **Twój kraj:**
    *   **Co robi to ustawienie:** Definiuje kraj, w którym zarejestrowana jest Twoja firma. Jest to kluczowe dla określenia, czy numer VAT klienta kwalifikuje się do 0% VAT (tj. czy pochodzi z *innego* kraju UE).
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na Twój kraj:* Moduł poprawnie zidentyfikuje sprzedaż wewnątrzwspólnotową.
        *   *Gdy ustawione niepoprawnie:* Logika walidacji VAT może zawieść lub niepoprawnie zastosować 0% VAT.
    *   **Zalecana wartość:** Oficjalny kraj rejestracji Twojego sklepu (np. „Polska”).
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój sklep ma siedzibę w Niemczech, wybierzesz „Niemcy”. Klient z Francji z ważnym francuskim numerem VAT będzie wtedy uprawniony do 0% VAT.
*   **Kraje uprawnione:**
    *   **Co robi to ustawienie:** Pozwala wybrać, które kraje UE są uprawnione do zasady 0% VAT. Możesz wybrać konkretne kraje lub wszystkie kraje UE.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy wybrane są konkretne kraje:* Tylko klienci z tych krajów (z ważnym VAT) otrzymają 0% VAT.
        *   *Gdy wybrane są wszystkie kraje UE:* Wszystkie kraje UE (z wyjątkiem Twojego) będą uprawnione.
    *   **Zalecana wartość:** Wybierz wszystkie kraje UE, chyba że masz konkretne powody biznesowe, aby niektóre wykluczyć.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz oferować 0% VAT tylko firmom we Francji, Niemczech i Hiszpanii, wybierzesz tylko te kraje.
*   **Wybierz regułę podatkową:**
    *   **Co robi to ustawienie:** Określa, która reguła podatkowa PrestaShop powinna zostać zastosowana, gdy VAT klienta zostanie zweryfikowany jako 0%. Powinieneś mieć ustawioną regułę podatkową w PrestaShop dla 0% VAT.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy wybrana jest reguła podatkowa 0%:* Moduł zastosuje tę regułę do kwalifikujących się zamówień.
        *   *Gdy wybrana jest nieprawidłowa reguła podatkowa:* Może zostać zastosowana niewłaściwa stawka podatku lub moduł może nie działać zgodnie z oczekiwaniami.
    *   **Zalecana wartość:** Reguła podatkowa, którą utworzyłeś w PrestaShop ze stawką 0% VAT.
    *   **Scenariusz / przykład dla sprzedawcy:** Utworzysz regułę podatkową o nazwie „UE B2B 0% VAT” ze stawką 0% i wybierzesz ją tutaj.
*   **Wyłącz moduł dla wybranych języków:**
    *   **Co robi to ustawienie:** Pozwala wyłączyć funkcjonalność walidacji VAT dla określonych języków w Twoim sklepie. Może to być przydatne, jeśli działasz w krajach spoza UE z innymi przepisami podatkowymi, ale nadal używasz tej samej instancji PrestaShop.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy wybrane są języki:* Formularz walidacji VAT i logika nie pojawią się ani nie zostaną zastosowane dla klientów przeglądających w tych językach.
        *   *Gdy nie wybrano żadnych języków:* Moduł będzie aktywny dla wszystkich języków.
    *   **Zalecana wartość:** Pozostaw puste, chyba że masz specyficzne wymagania podatkowe oparte na języku.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz angielską wersję swojego sklepu skierowaną zarówno do klientów z UE, jak i z USA, ale chcesz walidacji VAT tylko dla klientów z UE, możesz jej nie wyłączać. Jeśli jednak masz oddzielny widok sklepu dla kraju spoza UE (np. „Japonia”), możesz wyłączyć go dla języka japońskiego.

#### **Ustawienia wyświetlania (widoczność w Front-Office)**

Te ustawienia kontrolują, gdzie formularz wprowadzania VAT i komunikaty o statusie pojawiają się Twoim klientom.

*   **Pokaż formularz zmiany VAT w pasku nagłówka:**
    *   **Co robi to ustawienie:** Wyświetla mały formularz lub powiadomienie w obszarze nagłówka Twojego sklepu, zachęcając klientów do wprowadzenia numeru VAT.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* Pasek pojawia się na górze Twojej witryny.
        *   *Gdy wyłączone:* Brak formularza/powiadomienia VAT w nagłówku.
    *   **Zalecana wartość:** „Wyłączone”, chyba że chcesz wysokiej widoczności dla klientów B2B.
    *   **Scenariusz / przykład dla sprzedawcy:** Możesz to włączyć, jeśli Twój sklep jest głównie B2B i chcesz natychmiast poinformować klientów biznesowych o 0% VAT.
*   **Pokaż formularz zmiany VAT w displayCustomhtml1 (niestandardowy motyw sp_topdeals):**
    *   **Co robi to ustawienie:** Jest to specyficzny hook często używany przez niestandardowe motywy (takie jak 'sp_topdeals') do wyświetlania niestandardowej zawartości. Włączenie tego spowoduje umieszczenie formularza VAT w tym konkretnym obszarze.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* Formularz VAT pojawia się w obszarze hooka `displayCustomhtml1`.
        *   *Gdy wyłączone:* Formularz nie pojawi się w tym konkretnym niestandardowym obszarze.
    *   **Zalecana wartość:** „Wyłączone”, chyba że Twój motyw używa tego hooka i chcesz, aby formularz tam był.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój motyw ma widoczny obszar banerowy na górze i chcesz tam umieścić formularz VAT, włączysz to.
*   **Pokaż pasek statusu VAT dla zalogowanych klientów:**
    *   **Co robi to ustawienie:** Wyświetla pasek lub komunikat dla zalogowanych klientów, wskazujący ich aktualny status VAT (np. „Twój VAT jest ważny, zastosowano 0%”).
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* Zalogowani klienci widzą swój status VAT.
        *   *Gdy wyłączone:* Brak specyficznego paska statusu VAT dla zalogowanych użytkowników.
    *   **Zalecana wartość:** „Włączone”, aby zapewnić przejrzystość i pewność klientom B2B.
    *   **Scenariusz / przykład dla sprzedawcy:** Powracający klient biznesowy loguje się i natychmiast widzi „Twój VAT jest ważny, zastosowano 0% VAT do Twojego koszyka”, co poprawia jego doświadczenie zakupowe.
*   **Pokaż pasek VAT na kroku danych osobowych w kasie:**
    *   **Co robi to ustawienie:** Wyświetla pole wprowadzania VAT i status walidacji na pierwszym kroku procesu realizacji zamówienia (gdzie klienci wprowadzają swoje imię, adres itp.). Jest to najczęstsza i zalecana lokalizacja.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* Pole VAT jest widoczne i interaktywne na kroku danych osobowych.
        *   *Gdy wyłączone:* Pole VAT nie pojawi się na tym kroku, co może utrudnić klientom zastosowanie 0% VAT.
    *   **Zalecana wartość:** „Włączone” (Wysoce zalecane).
    *   **Scenariusz / przykład dla sprzedawcy:** Klient dociera do kasy, wprowadza adres swojej firmy, a następnie wprowadza swój numer VAT w dedykowanym polu. Moduł weryfikuje go, a cena aktualizuje się.
*   **Pokaż pasek VAT w podsumowaniu kasy:**
    *   **Co robi to ustawienie:** Wyświetla status VAT (np. „VAT: 0%”) na stronie podsumowania kasy, przed ostateczną płatnością.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci widzą swój status VAT w podsumowaniu.
        *   *Gdy wyłączone:* Brak specyficznego statusu VAT w podsumowaniu.
    *   **Zalecana wartość:** „Włączone” dla przejrzystości.
    *   **Scenariusz / przykład dla sprzedawcy:** Klient przegląda swoje zamówienie przed płatnością i widzi wyraźne potwierdzenie, że zastosowano 0% VAT.
*   **Pokaż pasek VAT na kroku płatności:**
    *   **Co robi to ustawienie:** Wyświetla status VAT na ostatnim kroku płatności w kasie.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* Klienci widzą swój status VAT na kroku płatności.
        *   *Gdy wyłączone:* Brak specyficznego statusu VAT na kroku płatności.
    *   **Zalecana wartość:** „Włączone” dla ostatecznego potwierdzenia.
    *   **Scenariusz / przykład dla sprzedawcy:** Tuż przed kliknięciem „Zapłać teraz” klient widzi „Suma: 100,00 € (VAT 0%)”, potwierdzając prawidłowe zastosowanie podatku.
*   **Pokaż pasek zmiany VAT na stronie produktu:**
    *   **Co robi to ustawienie:** Wyświetla formularz wprowadzania VAT lub komunikat o statusie bezpośrednio na poszczególnych stronach produktów.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* Formularz/komunikat VAT pojawia się na stronach produktów.
        *   *Gdy wyłączone:* Brak formularza/komunikatu VAT na stronach produktów.
    *   **Zalecana wartość:** „Wyłączone”, aby uniknąć bałaganu, chyba że masz silne ukierunkowanie na B2B i chcesz wcześnie pokazywać ceny bez VAT.
    *   **Scenariusz / przykład dla sprzedawcy:** Klient biznesowy przeglądający stronę produktu może wprowadzić swój numer VAT, aby natychmiast zobaczyć cenę bez VAT, co pomaga mu w podejmowaniu decyzji zakupowych.
*   **Pokaż formularz zmiany VAT w displayProductAdditionalInfo:**
    *   **Co robi to ustawienie:** Jest to standardowy hook PrestaShop na stronie produktu, zazwyczaj używany do dodatkowych informacji. Włączenie tego spowoduje umieszczenie formularza VAT w tym obszarze.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* Formularz VAT pojawia się w obszarze hooka `displayProductAdditionalInfo`.
        *   *Gdy wyłączone:* Formularz nie pojawi się w tym konkretnym obszarze.
    *   **Zalecana wartość:** „Wyłączone”, chyba że konkretnie chcesz, aby tam był.
    *   **Scenariusz / przykład dla sprzedawcy:** Podobnie jak w przypadku ustawienia „Pokaż pasek zmiany VAT na stronie produktu”, ale dotyczy konkretnego hooka.
*   **Pokaż formularz zmiany VAT w displayBanner:**
    *   **Co robi to ustawienie:** Wyświetla formularz VAT lub status w hooku `displayBanner`, który jest często używany do górnych banerów lub komunikatów promocyjnych.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* Formularz/status VAT pojawia się w obszarze banera.
        *   *Gdy wyłączone:* Brak formularza/statusu VAT w obszarze banera.
    *   **Zalecana wartość:** „Wyłączone”, aby uniknąć bałaganu, chyba że masz konkretny projekt banera do tego celu.
    *   **Scenariusz / przykład dla sprzedawcy:** Możesz użyć tego do wyświetlenia komunikatu „Jesteś firmą? Wprowadź swój numer VAT, aby uzyskać 0% podatku!” w widocznym banerze.
*   **Pokaż formularz zmiany VAT w displayCustomhtml1 (niestandardowy motyw sp_topdeals):** (Duplikat, już omówiony powyżej)
*   **Pokaż pasek statusu VAT dla zalogowanych klientów:** (Duplikat, już omówiony powyżej)
*   **Pokaż pasek VAT na kroku danych osobowych w kasie:** (Duplikat, już omówiony powyżej)
*   **Pokaż pasek VAT w podsumowaniu kasy:** (Duplikat, już omówiony powyżej)
*   **Pokaż pasek VAT na kroku płatności:** (Duplikat, już omówiony powyżej)
*   **Adnotacja o odwrotnym obciążeniu na fakturze:**
    *   **Co robi to ustawienie:** Gdy zastosowano 0% VAT z powodu prawidłowej weryfikacji VIES, to ustawienie zapewnia, że adnotacja „Odwrotne obciążenie” zostanie automatycznie dodana do faktury klienta. Jest to wymóg prawny dla wewnątrzwspólnotowej sprzedaży B2B.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* Faktury dla zamówień z 0% VAT będą zawierać adnotację o odwrotnym obciążeniu.
        *   *Gdy wyłączone:* Faktury nie będą zawierać adnotacji, co może prowadzić do niezgodności z przepisami.
    *   **Zalecana wartość:** „Włączone” (Wysoce zalecane dla zgodności z prawem).
    *   **Scenariusz / przykład dla sprzedawcy:** Niemiecki klient biznesowy kupuje w Twoim polskim sklepie z ważnym numerem VAT. Faktura automatycznie zawiera informację „Odwrotne obciążenie – VAT nie ma zastosowania zgodnie z art. 196 dyrektywy Rady 2006/112/WE”.

#### **Ustawienia zaawansowane**

*   **Ponownie waliduj numer VAT klienta przy każdym zamówieniu:**
    *   **Co robi to ustawienie:** Jeśli włączone, moduł ponownie sprawdzi numer VAT klienta w VIES za każdym razem, gdy złoży zamówienie, nawet jeśli został wcześniej zweryfikowany.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* Zapewnia, że numer VAT jest zawsze aktualny i ważny, ale dodaje niewielkie opóźnienie do realizacji zamówienia.
        *   *Gdy wyłączone:* Opiera się na początkowej walidacji, która jest szybsza, ale może przeoczyć zmiany w statusie VAT.
    *   **Zalecana wartość:** „Włączone” dla maksymalnej zgodności i dokładności.
    *   **Scenariusz / przykład dla sprzedawcy:** Numer VAT klienta biznesowego może z czasem stać się nieważny. Ponowna walidacja zapewnia, że nie zastosujesz błędnie 0% VAT do nieważnego numeru.
*   **Zapobiegaj zalewowi żądań VIES (blokuj na X minut):**
    *   **Co robi to ustawienie:** Jeśli klient wielokrotnie wprowadza nieprawidłowe numery VAT, to ustawienie tymczasowo blokuje dalsze próby walidacji na określony czas, aby zapobiec nadużyciom lub przeciążeniu systemu VIES.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* Po wielu nieudanych próbach klient jest tymczasowo blokowany przed ponowną próbą.
        *   *Gdy wyłączone:* Brak ochrony przed zalewem, co pozwala na nieograniczone próby.
    *   **Zalecana wartość:** „Włączone” z rozsądnym czasem blokady (np. 5-10 minut).
    *   **Scenariusz / przykład dla sprzedawcy:** Bot lub złośliwy użytkownik próbuje odgadnąć numery VAT. To ustawienie zapobiega ciągłemu uderzaniu w API VIES.
*   **Buforuj wyniki walidacji VIES na X godzin:**
    *   **Co robi to ustawienie:** Przechowuje wyniki udanych walidacji VIES przez określoną liczbę godzin. Zmniejsza to liczbę bezpośrednich wywołań do systemu VIES, przyspieszając proces i zmniejszając wykorzystanie zewnętrznego API.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* Szybsza walidacja dla powracających klientów lub w okresie buforowania.
        *   *Gdy wyłączone:* Każda walidacja to wywołanie VIES na żywo, co może być wolniejsze.
    *   **Zalecana wartość:** „Włączone” z czasem buforowania 24-72 godziny (np. 48 godzin).
    *   **Scenariusz / przykład dla sprzedawcy:** Klient weryfikuje swój numer VAT. Jeśli wróci na Twoją stronę w ciągu 48 godzin, moduł użyje buforowanego wyniku zamiast wykonywać nowe żądanie VIES.
*   **Ponownie sprawdzaj status VAT koszyka co X sekund:**
    *   **Co robi to ustawienie:** Definiuje, jak często moduł ponownie sprawdza status VAT koszyka w tle, szczególnie przydatne, jeśli ceny są dynamiczne lub jeśli klient zmienia swój adres/numer VAT podczas realizacji zamówienia.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na niską wartość:* Częstsze aktualizacje, potencjalnie płynniejsze doświadczenie, ale większe obciążenie serwera.
        *   *Gdy ustawione na wysoką wartość:* Rzadsze aktualizacje, może wymagać ręcznego odświeżenia strony, aby zmiany VAT zostały odzwierciedlone.
    *   **Zalecana wartość:** 5-10 sekund.
    *   **Scenariusz / przykład dla sprzedawcy:** Klient wprowadza swój numer VAT, a w ciągu 5 sekund suma koszyka aktualizuje się, aby odzwierciedlić 0% VAT bez przeładowania strony.
*   **Włącz automatyczną ponowną walidację numeru VAT (Cron Job):**
    *   **Co robi to ustawienie:** Aktywuje zadanie w tle (cron job), które okresowo ponownie weryfikuje wszystkie przechowywane numery VAT klientów w VIES. Zapewnia to, że nawet stare numery VAT pozostają ważne.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy włączone:* Numery VAT są okresowo sprawdzane pod kątem ważności, zapewniając zgodność.
        *   *Gdy wyłączone:* Numery VAT są sprawdzane tylko w momencie wprowadzenia lub zamówienia, co może prowadzić do nieaktualnych informacji.
    *   **Zalecana wartość:** „Włączone” (Wysoce zalecane dla długoterminowej zgodności).
    *   **Scenariusz / przykład dla sprzedawcy:** Klient złożył zamówienie 6 miesięcy temu z ważnym numerem VAT. Zadanie cron ponownie sprawdza go i stwierdza, że jest teraz nieważny, co pozwala oznaczyć go dla przyszłych zamówień.
*   **Interwał ponownej walidacji Cron Job (dni):**
    *   **Co robi to ustawienie:** Określa, jak często zadanie cron jest uruchamiane w celu ponownej walidacji numerów VAT.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy ustawione na niską liczbę:* Częstsze ponowne walidacje, większa dokładność, ale więcej żądań VIES.
        *   *Gdy ustawione na wysoką liczbę:* Rzadsze ponowne walidacje, mniejsza dokładność, mniej żądań VIES.
    *   **Zalecana wartość:** 30-90 dni (np. 60 dni).
    *   **Scenariusz / przykład dla sprzedawcy:** Ustawienie na 30 dni oznacza, że wszystkie numery VAT są ponownie sprawdzane raz w miesiącu.
*   **Klucz API VIES (opcjonalnie):**
    *   **Co robi to ustawienie:** Pozwala używać alternatywnych interfejsów API do walidacji VAT (takich jak Apilayer, AbstractAPI, VATStack) zamiast domyślnego systemu VIES. Mogą one czasami oferować bardziej rozbudowane funkcje lub opcje awaryjne.
    *   **Wpływ zmiany tego ustawienia:**
        *   *Gdy wprowadzono klucz:* Moduł spróbuje użyć określonego zewnętrznego API do walidacji.
        *   *Gdy puste:* Moduł domyślnie używa oficjalnego systemu VIES.
    *   **Zalecana wartość:** Pozostaw puste, chyba że masz problemy z VIES lub potrzebujesz specyficznych funkcji od zewnętrznego API. Jeśli używasz jednego, wprowadź klucz dostarczony przez tę usługę.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli system VIES często nie działa lub jest wolny, możesz zasubskrybować usługę walidacji VAT Apilayer i wprowadzić swój klucz API tutaj jako niezawodną alternatywę.

#### **Klucze API (opcjonalnie - dla alternatywnych usług walidacji VAT)**

*   **Klucz API Apilayer:**
    *   **Co robi to ustawienie:** Wprowadź swój klucz API, jeśli subskrybujesz usługę walidacji VAT Apilayer.
    *   **Wpływ zmiany tego ustawienia:** Włącza walidację za pośrednictwem Apilayer.
    *   **Zalecana wartość:** Pozostaw puste, chyba że masz konto Apilayer.
*   **Klucz API AbstractAPI:**
    *   **Co robi to ustawienie:** Wprowadź swój klucz API, jeśli subskrybujesz usługę walidacji VAT AbstractAPI.
    *   **Wpływ zmiany tego ustawienia:** Włącza walidację za pośrednictwem AbstractAPI.
    *   **Zalecana wartość:** Pozostaw puste, chyba że masz konto AbstractAPI.
*   **Klucz API VATStack:**
    *   **Co robi to ustawienie:** Wprowadź swój klucz API, jeśli subskrybujesz usługę walidacji VATStack.
    *   **Wpływ zmiany tego ustawienia:** Włącza walidację za pośrednictwem VATStack.
    *   **Zalecana wartość:** Pozostaw puste, chyba że masz konto VATStack.

#### **Tabela szybkiego odniesienia do konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Główna konfiguracja | Twój kraj | Kraj Twojego sklepu | Definiuje kraj Twojej firmy dla sprzedaży wewnątrzwspólnotowej. |
| Główna konfiguracja | Kraje uprawnione | Wszystkie kraje UE | Wybiera kraje UE, w których obowiązuje 0% VAT. |
| Główna konfiguracja | Wybierz regułę podatkową | Twoja reguła podatkowa 0% | Określa regułę podatkową PrestaShop dla 0% VAT. |
| Główna konfiguracja | Wyłącz moduł dla wybranych języków | Puste | Wyłącza moduł dla określonych języków. |
| Główna konfiguracja | Pokaż formularz zmiany VAT w pasku nagłówka | Wyłączone | Wyświetla formularz VAT w nagłówku. |
| Główna konfiguracja | Pokaż formularz zmiany VAT w displayCustomhtml1 | Wyłączone | Wyświetla formularz VAT w niestandardowym hooku motywu. |
| Główna konfiguracja | Pokaż pasek statusu VAT dla zalogowanych klientów | Włączone | Pokazuje status VAT zalogowanym użytkownikom. |
| Główna konfiguracja | Pokaż pasek VAT na kroku danych osobowych w kasie | Włączone (Wysoce zalecane) | Wyświetla pole VAT na pierwszym kroku realizacji zamówienia. |
| Główna konfiguracja | Pokaż pasek VAT w podsumowaniu kasy | Włączone | Wyświetla status VAT w podsumowaniu kasy. |
| Główna konfiguracja | Pokaż pasek VAT na kroku płatności | Włączone | Wyświetla status VAT na kroku płatności. |
| Główna konfiguracja | Pokaż pasek zmiany VAT na stronie produktu | Wyłączone | Wyświetla formularz VAT na stronach produktów. |
| Główna konfiguracja | Pokaż formularz zmiany VAT w displayProductAdditionalInfo | Wyłączone | Wyświetla formularz VAT w hooku dodatkowych informacji o produkcie. |
| Główna konfiguracja | Pokaż formularz zmiany VAT w displayBanner | Wyłączone | Wyświetla formularz VAT w hooku banera. |
| Główna konfiguracja | Adnotacja o odwrotnym obciążeniu na fakturze | Włączone (Wysoce zalecane) | Dodaje prawną adnotację „Odwrotne obciążenie” do faktur. |
| Główna konfiguracja | Ponownie waliduj numer VAT klienta przy każdym zamówieniu | Włączone | Ponownie sprawdza VAT dla każdego nowego zamówienia. |
| Główna konfiguracja | Zapobiegaj zalewowi żądań VIES (blokuj na X minut) | Włączone (5-10 minut) | Blokuje powtarzające się nieprawidłowe próby VAT. |
| Główna konfiguracja | Buforuj wyniki walidacji VIES na X godzin | Włączone (24-72 godziny) | Buforuje wyniki VIES, aby przyspieszyć walidację. |
| Główna konfiguracja | Ponownie sprawdzaj status VAT koszyka co X sekund | 5-10 sekund | Jak często aktualizowany jest status VAT koszyka. |
| Główna konfiguracja | Włącz automatyczną ponowną walidację numeru VAT (Cron Job) | Włączone (Wysoce zalecane) | Aktywuje ponowną walidację wszystkich numerów VAT w tle. |
| Główna konfiguracja | Interwał ponownej walidacji Cron Job (dni) | 30-90 dni (np. 60) | Częstotliwość ponownej walidacji przez cron job. |
| Główna konfiguracja | Klucz API Apilayer | Puste | Klucz do usługi walidacji VAT Apilayer. |
| Główna konfiguracja | Klucz API AbstractAPI | Puste | Klucz do usługi walidacji VAT AbstractAPI. |
| Główna konfiguracja | Klucz API VATStack | Puste | Klucz do usługi walidacji VAT VATStack. |

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### **Audyt walidacji VAT (Panel administracyjny > Klienci > Audyt walidacji VAT)**

Ta dedykowana sekcja pozwala przeglądać i zarządzać wszystkimi próbami walidacji VAT dokonanymi za pośrednictwem Twojego sklepu.

*   **Nazwa ekranu i lokalizacja w menu:** **Klienci > Audyt walidacji VAT** (Ten nowy element menu jest dodawany przez moduł).
*   **Dostępne akcje i ustawienia:**
    *   **Widok siatki / zarządzania:** Ten ekran przedstawia tabelę (siatkę) wszystkich prób walidacji VAT. Dla każdego wpisu zazwyczaj zobaczysz:
        *   **Nazwa klienta:** Nazwa klienta powiązanego z walidacją.
        *   **Numer VAT:** Wprowadzony numer VAT.
        *   **Kraj:** Kod kraju powiązany z numerem VAT.
        *   **Status walidacji:** Czy numer VAT był „Ważny”, „Nieważny” czy „Błąd” (np. system VIES niedostępny).
        *   **Data walidacji:** Kiedy nastąpiła próba walidacji.
        *   **ID zamówienia:** Jeśli walidacja doprowadziła do zamówienia, powiązane ID zamówienia.
        *   **Źródło:** Gdzie odbyła się walidacja (np. „Kasa”, „Konto klienta”).
        *   **Szczegóły/Powód:** Więcej informacji o wyniku walidacji, zwłaszcza dla nieprawidłowych wpisów.
    *   **Filtrowanie i sortowanie:** Zazwyczaj możesz filtrować listę według klienta, numeru VAT, statusu lub zakresu dat, aby znaleźć konkretne wpisy. Sortowanie pozwala organizować dane.
    *   **Eksport:** Moduł może oferować opcję eksportu tego dziennika audytu, co jest przydatne do celów księgowych i podatkowych.
*   **Wpływ zmian:** Ten ekran służy głównie do audytu i raportowania. Nie możesz bezpośrednio zmienić statusu VAT klienta tutaj, ale możesz przeglądać historię walidacji. Dane te są kluczowe do udowodnienia zgodności podczas kontroli podatkowych.
*   **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**
    1.  Okresowo przeglądaj ten dziennik audytu, zwłaszcza jeśli zauważysz rozbieżności w zastosowaniu VAT lub otrzymasz zapytania klientów dotyczące VAT.
    2.  Szukaj statusów „Nieważny” lub „Błąd”, aby zidentyfikować potencjalne problemy z danymi wejściowymi klienta lub dostępnością systemu VIES.
    3.  Użyj funkcji eksportu, aby dostarczyć dane swojemu księgowemu lub organom podatkowym, jeśli zostaną o to poproszone.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Audyt walidacji VAT | Widok siatki | N/A | Wyświetla historyczny dziennik wszystkich prób walidacji VAT. |
| Audyt walidacji VAT | Filtry i sortowanie | N/A | Pomaga zlokalizować konkretne wpisy walidacji. |
| Audyt walidacji VAT | Eksport danych | N/A | Umożliwia eksport dziennika audytu do celów ewidencji i podatkowych. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moi klienci wprowadzają ważne numery VAT, ale 0% VAT nie jest stosowane.**
*   **Odp.:**
    1.  **Sprawdź ustawienie „Twój kraj”:** Upewnij się, że jest ono poprawnie ustawione na kraj Twojego sklepu w konfiguracji modułu.
    2.  **Zweryfikuj „Kraje uprawnione”:** Upewnij się, że kraj klienta jest wybrany na liście krajów uprawnionych.
    3.  **Potwierdź „Wybierz regułę podatkową”:** Upewnij się, że masz utworzoną regułę podatkową 0% w PrestaShop (**Międzynarodowe > Podatki > Reguły podatkowe**) i że jest ona poprawnie wybrana w ustawieniach modułu.
    4.  **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Czasami stara pamięć podręczna może uniemożliwić zastosowanie nowych ustawień.
    5.  **Sprawdź dostępność VIES:** System VIES może być czasami tymczasowo niedostępny. Możesz sprawdzić jego status na oficjalnej stronie Komisji Europejskiej.

**P2: Formularz walidacji VAT nie pojawia się na mojej stronie kasy.**
*   **Odp.:**
    1.  **Sprawdź ustawienia wyświetlania:** W konfiguracji modułu upewnij się, że opcja „Pokaż pasek VAT na kroku danych osobowych w kasie” (i inne odpowiednie opcje wyświetlania) jest ustawiona na „Włączone”.
    2.  **Kompatybilność motywu:** Jeśli używasz bardzo spersonalizowanego motywu, może on nadpisywać standardowe hooki PrestaShop. Sprawdź, czy Twój motyw ma określone obszary dla `displayProductAdditionalInfo`, `displayCustomhtml1` lub innych hooków, w których próbowałeś umieścić formularz. Może być konieczne skonsultowanie się z twórcą motywu.
    3.  **Konflikty modułów:** Tymczasowo wyłącz inne moduły związane z kasą, aby sprawdzić, czy występuje konflikt.

**P3: Widzę komunikaty „Błąd” lub „VIES niedostępny” podczas walidacji.**
*   **Odp.:**
    1.  **Status systemu VIES:** System VIES może doświadczać przestojów. Sprawdź oficjalną stronę VIES, aby uzyskać aktualny status.
    2.  **Rozszerzenie cURL:** Upewnij się, że Twój dostawca hostingu ma włączone rozszerzenie PHP `cURL`. Jest to niezbędne, aby moduł mógł komunikować się z zewnętrznymi interfejsami API, takimi jak VIES. Skontaktuj się ze swoim hostem, jeśli nie masz pewności.
    3.  **Zapora ogniowa/bezpieczeństwo:** Zapora ogniowa lub ustawienia bezpieczeństwa Twojego serwera mogą blokować połączenia wychodzące do serwera VIES. Ponownie skontaktuj się ze swoim dostawcą hostingu.
    4.  **Klucze API:** Jeśli próbujesz użyć zewnętrznego API (Apilayer, AbstractAPI, VATStack), upewnij się, że klucz API jest poprawnie wprowadzony i aktywny w tej usłudze.

**P4: Jak upewnić się, że zadanie cron do ponownej walidacji działa?**
*   **Odp.:**
    1.  **Włącz zadanie Cron:** W konfiguracji modułu upewnij się, że opcja „Włącz automatyczną ponowną walidację numeru VAT (Cron Job)” jest ustawiona na „Włączone”.
    2.  **Moduł Cron PrestaShop:** Potrzebujesz oddzielnego modułu zadań cron PrestaShop (np. „Menedżer zadań cron” od PrestaShop) zainstalowanego i skonfigurowanego do okresowego wyzwalania zadania cron modułu.
    3.  **Cron hostingu:** Alternatywnie, możesz skonfigurować zadanie cron na poziomie serwera (za pośrednictwem cPanel, Plesk lub SSH), aby wywołać adres URL cron modułu. Konfiguracja modułu zazwyczaj dostarcza dokładny adres URL do użycia.
    4.  **Sprawdź dziennik audytu:** Po uruchomieniu zadania cron sprawdź ekran „Audyt walidacji VAT” w Panelu administracyjnym. Powinieneś zobaczyć nowe wpisy walidacji ze źródłem „Cron”.

**P5: Dlaczego niektóre kraje UE nie pojawiają się na liście „Kraje uprawnione”?**
*   **A:** Moduł opiera się na liście krajów PrestaShop. Upewnij się, że wszystkie pożądane kraje UE są włączone w Twoim sklepie PrestaShop (**Międzynarodowe > Lokalizacje > Kraje**) i że są oznaczone jako „Jest krajem UE” i „Zawiera stany” (jeśli dotyczy).

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy opis struktury technicznej modułu „Walidacja VAT w VIES i ustawienie 0% VAT”, przeznaczony dla deweloperów i webmasterów.

### 4.1 Przegląd architektury

Moduł wykorzystuje standardowy wzorzec PrestaShop MVC (Model-View-Controller), intensywnie wykorzystując hooki do integracji z front-office i back-office. Wprowadza kilka niestandardowych klas dla logiki biznesowej, interakcji z API i zarządzania danymi. Kluczowe komponenty to:

*   **Główna klasa modułu (`eurovat.php`):** Obsługuje instalację, deinstalację, rejestrację hooków i główny formularz konfiguracji (`getContent()`).
*   **Kontrolery front-office:** Zarządzają żądaniami AJAX do walidacji VAT i przesyłania formularzy.
*   **Kontrolery administracyjne:** Zapewniają dedykowane interfejsy do audytu walidacji VAT.
*   **Klasy podstawowe:** Hermetyzują logikę biznesową dla interakcji z VIES, zarządzania podatkami, analityki i trwałości danych (często rozszerzając `ObjectModel` lub używając wzorca repozytorium).
*   **Szablony:** Szablony Smarty do renderowania formularzy front-office, konfiguracji back-office i widoków audytu.
*   **Hooki:** Obszerne wykorzystanie hooków do wstrzykiwania funkcjonalności w różnych punktach cyklu życia PrestaShop (np. strona produktu, kasa, przetwarzanie zamówień, widok klienta w panelu administracyjnym).

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

*   `controllers/front/cron.php`
    *   **Nazwa klasy:** `EurovatCronModuleFrontController` (rozszerza `ModuleFrontController`)
    *   **Odpowiedzialność:** Obsługuje wykonanie zadania cron modułu. Ten kontroler jest zazwyczaj wywoływany przez zewnętrzną usługę cron (np. cron serwera lub moduł `Cron tasks manager` PrestaShop) w celu wyzwolenia zadań w tle, takich jak ponowna walidacja numerów VAT. Przetwarza hook `ActionCronJob`.
*   `controllers/front/form.php`
    *   **Nazwa klasy:** `EurovatFormModuleFrontController` (rozszerza `ModuleFrontController`)
    *   **Odpowiedzialność:** Prawdopodobnie obsługuje wyświetlanie i przesyłanie formularza wprowadzania VAT w różnych kontekstach front-office (np. strona produktu, niestandardowe bloki HTML). Może renderować `views/templates/front/form.tpl`.
*   `controllers/front/index.php`
    *   **Nazwa klasy:** `EurovatIndexModuleFrontController` (rozszerza `ModuleFrontController`)
    *   **Odpowiedzialność:** Ogólny kontroler front-office, potencjalnie używany do awaryjnego lub prostego wyświetlania logiki. Często `index.php` w katalogu kontrolera służy jako symbol zastępczy lub podstawa dla innych kontrolerów.
*   `controllers/front/validate.php`
    *   **Nazwa klasy:** `EurovatValidateModuleFrontController` (rozszerza `ModuleFrontController`)
    *   **Odpowiedzialność:** Główny punkt końcowy AJAX do walidacji numeru VAT w czasie rzeczywistym. Odbiera numer VAT i dane kraju, wchodzi w interakcję z klientem VIES i zwraca odpowiedź JSON wskazującą ważność i potencjalnie aktualizując status podatkowy koszyka.

#### Kontrolery administracyjne Back-Office

*   `controllers/admin/AdminEurovatVatValidationAuditController.php`
    *   **Nazwa klasy:** `AdminEurovatVatValidationAuditController` (rozszerza `ModuleAdminController`)
    *   **Nazwa zakładki:** „Audyt walidacji VAT” (w menu Klienci)
    *   **Zarządzana encja:** `EurovatValidation` (niestandardowa tabela `ps_eurovat_validation`)
    *   **Odpowiedzialność:** Zapewnia interfejs administracyjny do przeglądania, filtrowania i zarządzania dziennikiem audytu wszystkich prób walidacji VAT. Wykorzystuje komponenty `HelperList` lub `Grid` PrestaShop do wyświetlania danych z tabeli `ps_eurovat_validation`.
*   `controllers/admin/index.php`
    *   **Nazwa klasy:** `EurovatIndexAdminController` (rozszerza `ModuleAdminController`)
    *   **Odpowiedzialność:** Podobnie jak `index.php` w front-office, jest to prawdopodobnie symbol zastępczy lub kontroler bazowy. Może przekierowywać do głównej konfiguracji lub kontrolera audytu.

### 4.3 Klasy podstawowe i modele (`classes/`)

*   `classes/EurovatAlertService.php`
    *   **Odpowiedzialność:** Zarządza i wyświetla alerty lub powiadomienia w module, prawdopodobnie związane ze statusem VIES, problemami z kluczem API lub problemami z konfiguracją.
*   `classes/EurovatAlertsHelper.php`
    *   **Odpowiedzialność:** Klasa pomocnicza dla `EurovatAlertService`, dostarczająca funkcje narzędziowe do zarządzania alertami.
*   `classes/EurovatAnalyticsService.php`
    *   **Odpowiedzialność:** Gromadzi i przetwarza dane związane z walidacją VAT, takie jak wskaźniki sukcesu, typy błędów i wykorzystanie API, potencjalnie do wyświetlania w widżecie pulpitu nawigacyjnego.
*   `classes/EurovatApiUsageHelper.php`
    *   **Odpowiedzialność:** Śledzi i zarządza wykorzystaniem zewnętrznych interfejsów API do walidacji VAT (VIES, Apilayer itp.), potencjalnie implementując ograniczanie szybkości lub monitorowanie.
*   `classes/EurovatAuditHelper.php`
    *   **Odpowiedzialność:** Pomaga `AdminEurovatVatValidationAuditController` w zarządzaniu i wysyłaniu zapytań do tabeli `ps_eurovat_validation`.
*   `classes/EurovatConfiguration.php`
    *   **Odpowiedzialność:** Klasa statyczna lub singleton do centralizacji dostępu do wartości konfiguracyjnych modułu (`Configuration::get('EUROVAT_...')`). Zapewnia czystszy sposób pobierania ustawień.
*   `classes/EurovatCronHelper.php`
    *   **Odpowiedzialność:** Zawiera logikę wykonywaną przez zadanie cron, taką jak iterowanie po numerach VAT klientów i inicjowanie ponownej walidacji.
*   `classes/EurovatErrorClassifier.php`
    *   **Odpowiedzialność:** Kategoryzuje i dostarcza przyjazne dla użytkownika komunikaty dla różnych typów błędów walidacji VAT (np. nieprawidłowy format, VIES niedostępny, niezgodność kraju).
*   `classes/EurovatExportService.php`
    *   **Odpowiedzialność:** Obsługuje eksport danych audytu walidacji VAT, prawdopodobnie do formatu CSV lub Excel.
*   `classes/EurovatOrderProofHelper.php`
    *   **Odpowiedzialność:** Gromadzi i przygotowuje dane związane z walidacją VAT dla konkretnego zamówienia, używane do generowania dowodu zastosowania 0% VAT.
*   `classes/EurovatOrderTaxNormalizer.php`
    *   **Odpowiedzialność:** Dostosowuje szczegóły podatkowe zamówienia, gdy zastosowano 0% VAT, zapewniając spójność w koszyku, zamówieniu i fakturze.
*   `classes/EurovatProofPackService.php`
    *   **Odpowiedzialność:** Potencjalnie tworzy „pakiet dowodowy” (np. dokument PDF) zawierający wszystkie niezbędne dowody dla transakcji z 0% VAT.
*   `classes/EurovatTaxManager.php`
    *   **Odpowiedzialność:** Centralna klasa do stosowania i zarządzania zmianami podatkowymi na podstawie wyników walidacji VAT, wchodząca w interakcję z systemem podatkowym PrestaShop.
*   `classes/EurovatTaxService.php`
    *   **Odpowiedzialność:** Dostarcza metody narzędziowe związane z obliczeniami i zastosowaniem podatków w module.
*   `classes/EurovatValidationRepository.php`
    *   **Z jaką tabelą bazy danych wchodzi w interakcję:** `ps_eurovat_validation`
    *   **Czy rozszerza `ObjectModel`:** Prawdopodobnie nie bezpośrednio, ale zarządza obiektami `EurovatValidation` lub surowymi zapytaniami do bazy danych.
    *   **Kluczowe metody publiczne i hermetyzowana logika biznesowa:** Operacje CRUD dla rekordów walidacji VAT, zapytania o historię walidacji, przechowywanie wyników walidacji.
*   `classes/EurovatViesClient.php`
    *   **Odpowiedzialność:** Główny interfejs do komunikacji z systemem VIES (lub alternatywnymi interfejsami API, takimi jak Apilayer, AbstractAPI, VATStack). Obsługuje żądania API, odpowiedzi i obsługę błędów.
*   `classes/index.php`
    *   **Odpowiedzialność:** Zabezpieczenie przed listowaniem katalogów.

### 4.4 Zasoby JavaScript (`views/js/`)

*   `eurovat/views/js/adminEurovatAlerts.js`
    *   **Zakres:** Back-office
    *   **Opis:** Obsługuje wyświetlanie i interakcję z alertami w panelu administracyjnym, potencjalnie dynamiczne aktualizacje lub komunikaty, które można zamknąć.
*   `eurovat/views/js/adminEurovatCountries.js`
    *   **Zakres:** Back-office
    *   **Opis:** Zarządza interfejsem wyboru kraju w konfiguracji modułu, prawdopodobnie z funkcją wielokrotnego wyboru lub dynamicznego filtrowania.
*   `eurovat/views/js/adminEurovatCron.js`
    *   **Zakres:** Back-office
    *   **Opis:** Zapewnia logikę interfejsu użytkownika dla ustawień zadania cron, potencjalnie wyświetlając czasy ostatniego uruchomienia, następne zaplanowane uruchomienie lub opcje ręcznego wyzwalania.
*   `eurovat/views/js/adminEurovatDashboard.js`
    *   **Zakres:** Back-office
    *   **Opis:** Obsługuje widżet pulpitu nawigacyjnego (jeśli istnieje), wyświetlający analitykę lub kluczowe metryki związane z walidacją VAT. Wykorzystuje AJAX do pobierania danych i potencjalnie biblioteki do tworzenia wykresów.
*   `eurovat/views/js/adminEurovatTooltips.js`
    *   **Zakres:** Back-office
    *   **Opis:** Inicjuje i zarządza podpowiedziami dla opcji konfiguracyjnych w panelu administracyjnym, dostarczając pomocny kontekst.
*   `eurovat/views/js/eurovat.js`
    *   **Zakres:** Front-office
    *   **Opis:** Główny JavaScript front-office.
        *   **Słuchacze zdarzeń:** Wiąże się ze zdarzeniami wejściowymi w polu numeru VAT (np. `keyup`, `change`), przesyłaniem formularzy i potencjalnie `prestashop.on('updateCart')` lub podobnymi zdarzeniami.
        *   **Manipulacja DOM:** Dynamicznie wyświetla komunikaty o statusie walidacji (ważny/nieważny), aktualizuje sumy koszyka, pokazuje/ukrywa elementy na podstawie statusu VAT.
        *   **Wywołania AJAX:** Wysyła numer VAT i dane kraju do `controllers/front/validate.php` w celu walidacji w czasie rzeczywistym.
        *   **Inne:** Implementuje interwał „ponownego sprawdzania statusu VAT koszyka”, logikę ochrony przed zalewem.
*   `eurovat/views/js/eurovatBoMockConsole.js`
    *   **Zakres:** Back-office (rozwój/debugowanie)
    *   **Opis:** Prawdopodobnie narzędzie do symulowania danych wyjściowych konsoli lub dostarczania rozszerzonych możliwości debugowania w Panelu administracyjnym PrestaShop, zazwyczaj nieużywane w produkcji.

### 4.5 Arkusze stylów CSS (`views/css/`)

*   `eurovat/views/css/admin_eurovat.css`
    *   **Zakres:** Stylizacja formularza administracyjnego back-office.
    *   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Elementy strony konfiguracji, tabela listy audytu, widżety pulpitu nawigacyjnego, alerty i podpowiedzi w interfejsie administracyjnym modułu.
    *   **Kluczowe selektory klas CSS, które deweloperzy mogą nadpisać:** `.eurovat-admin-config`, `.eurovat-alert`, `.eurovat-dashboard-widget`, `.eurovat-audit-table`.
*   `eurovat/views/css/eurovat.css`
    *   **Zakres:** Stylizacja klienta front-office.
    *   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Pola wprowadzania VAT, komunikaty o statusie walidacji (sukces/błąd), paski statusu VAT w nagłówku/stronie produktu/kasie, adnotacje o odwrotnym obciążeniu.
    *   **Kluczowe selektory klas CSS, które deweloperzy mogą nadpisać:** `.eurovat-vat-form`, `.eurovat-status-message.valid`, `.eurovat-status-message.invalid`, `.eurovat-header-bar`, `.eurovat-product-vat-info`, `.eurovat-checkout-vat-status`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

#### Szablony hooków (`views/templates/hook/`)

*   `eurovat/views/templates/hook/adminDashboardWidget.tpl`
    *   **Hook:** Potencjalnie `displayAdminHomeQuickview` lub niestandardowy hook pulpitu nawigacyjnego.
    *   **Wyjścia:** Widżet dla pulpitu nawigacyjnego administratora PrestaShop, wyświetlający analitykę lub szybkie statystyki związane z walidacją VAT.
*   `eurovat/views/templates/hook/adminOrderProofPack.tpl`
    *   **Hook:** `displayAdminOrder` lub `displayAdminOrderTabContent` (na stronie widoku zamówienia).
    *   **Wyjścia:** Blok lub zakładka w szczegółach zamówienia administratora, umożliwiająca administratorom przeglądanie lub generowanie dokumentów potwierdzających VAT dla konkretnego zamówienia.
*   `eurovat/views/templates/hook/customerHistory.tpl`
    *   **Hook:** `displayCustomerAccount` lub `displayMyAccountBlock`.
    *   **Wyjścia:** Informacje o historii walidacji VAT klienta lub aktualnym statusie w jego osobistym obszarze konta.
*   `eurovat/views/templates/hook/displayBanner.tpl`
    *   **Hook:** `displayBanner` (lub podobny globalny hook banera).
    *   **Wyjścia:** Formularz wprowadzania VAT lub komunikat promocyjny o 0% VAT, zazwyczaj wyświetlany na górze sklepu.

#### Szablony administracyjne (`views/templates/admin/`)

*   `eurovat/views/templates/admin/alerts.tpl`
    *   **Wyjścia:** Struktura HTML do wyświetlania różnych alertów i powiadomień w Panelu administracyjnym.
*   `eurovat/views/templates/admin/audit.tpl`
    *   **Wyjścia:** Główny szablon dla `AdminEurovatVatValidationAuditController`, renderujący listę audytu walidacji VAT.
*   `eurovat/views/templates/admin/configure.tpl`
    *   **Wyjścia:** Główny formularz konfiguracji modułu, renderowany przez `getContent()` w `eurovat.php`. Zawiera wszystkie ustawienia opisane w sekcji 4.1.
*   `eurovat/views/templates/admin/countriesSelector.tpl`
    *   **Wyjścia:** Szablon wielokrotnego użytku dla interfejsu wyboru kraju w konfiguracji.
*   `eurovat/views/templates/admin/cron.tpl`
    *   **Wyjścia:** Sekcja konfiguracji związana z ustawieniami zadania cron, w tym interwałem i aktywacją.
*   `eurovat/views/templates/admin/dashboard.tpl`
    *   **Wyjścia:** Pełny widok pulpitu nawigacyjnego, potencjalnie integrujący `adminDashboardWidget.tpl` i inne analizy.
*   `eurovat/views/templates/admin/hooksRepair.tpl`
    *   **Wyjścia:** Szablon narzędziowy, prawdopodobnie do diagnozowania i naprawiania brakujących lub niepoprawnie zarejestrowanych hooków.
*   `eurovat/views/templates/admin/proof_pack_view.tpl`
    *   **Wyjścia:** Szczegółowy widok pakietu dowodowego VAT, prawdopodobnie na stronie szczegółów zamówienia.
*   `eurovat/views/templates/admin/vat_audit_list_settings.tpl`
    *   **Wyjścia:** Ustawienia lub filtry specyficzne dla wyświetlania listy audytu VAT.
*   `eurovat/views/templates/admin/vat_audit_tabs.tpl`
    *   **Wyjścia:** Nawigacja po zakładkach dla sekcji audytu VAT, jeśli istnieje wiele podsekcji (np. dziennik audytu, analityka).

#### Szablony front-office (`views/templates/front/`)

*   `eurovat/views/templates/front/form.tpl`
    *   **Wyjścia:** Podstawowa struktura HTML dla formularza wprowadzania numeru VAT, używana w różnych hookach front-office (strona produktu, kasa, nagłówek).

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

*   `ps_eurovat_validation`
    *   **Cel:** Przechowuje historyczny dziennik wszystkich prób walidacji VAT.
    *   **Kluczowe pola (oczekiwane):**
        *   `id_eurovat_validation` (Klucz podstawowy)
        *   `id_customer` (Klucz obcy do `ps_customer`)
        *   `id_cart` (Klucz obcy do `ps_cart`)
        *   `id_order` (Klucz obcy do `ps_order`)
        *   `vat_number` (Wprowadzony numer VAT)
        *   `country_code` (Kraj powiązany z numerem VAT)
        *   `validation_status` (np. 'valid', 'invalid', 'error')
        *   `validation_response` (Surowa odpowiedź z VIES/API)
        *   `validation_date` (Sygnatura czasowa walidacji)
        *   `source` (np. 'checkout', 'customer_account', 'cron')
        *   `ip_address` (Adres IP użytkownika, który przeprowadził walidację)

*   `ps_configuration`
    *   **Cel:** Przechowuje wszystkie ustawienia konfiguracyjne modułu.
    *   **Kluczowe klucze konfiguracyjne:**
        *   `EUROVAT_YOUR_COUNTRY`
        *   `EUROVAT_ELIGIBLE_COUNTRIES`
        *   `EUROVAT_TAX_RULE`
        *   `EUROVAT_DISPLAY_HEADER`
        *   `EUROVAT_DISPLAY_CUSTOMHTML1`
        *   `EUROVAT_DISPLAY_LOGGED_STATUS`
        *   `EUROVAT_DISPLAY_CHECKOUT_PERSONAL`
        *   `EUROVAT_DISPLAY_CHECKOUT_SUMMARY`
        *   `EUROVAT_DISPLAY_CHECKOUT_PAYMENT`
        *   `EUROVAT_DISPLAY_PRODUCT_PAGE`
        *   `EUROVAT_REVERSE_CHARGE_NOTE`
        *   `EUROVAT_REVALIDATE_ON_ORDER`
        *   `EUROVAT_FLOOD_OFF_MINUTES`
        *   `EUROVAT_CACHE_TTL_HOURS`
        *   `EUROVAT_CART_RECHECK_INTERVAL`
        *   `EUROVAT_CRON_REVALIDATE_ENABLED`
        *   `EUROVAT_CRON_INTERVAL_DAYS`
        *   `EUROVAT_APILAYER_KEY`
        *   `EUROVAT_ABSTRACTAPI_KEY`
        *   `EUROVAT_VATSTACK_KEY`
        *   `EUROVAT_DISABLED_LANGS`

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Wstrzykiwanie CSS/JS lub wyświetlanie globalnego paska statusu VAT. |
| `displayProductAdditionalInfo` | Na stronie produktu, zazwyczaj poniżej opisu produktu. | Wyświetlanie formularza wprowadzania VAT lub statusu na stronach produktów. |
| `displayCustomhtml1` | Niestandardowy hook, często w górnej sekcji motywu (np. `sp_topdeals`). | Wyświetlanie formularza wprowadzania VAT w określonych obszarach motywu. |
| `displayPaymentTop` | Na górze kroku płatności w kasie. | Wyświetlanie statusu VAT lub formularza przed płatnością. |
| `displayBanner` | W obszarze banera, zazwyczaj na górze witryny. | Wyświetlanie formularza wprowadzania VAT lub komunikatu promocyjnego. |
| `displayAdminCustomers` | Na liście klientów lub stronie szczegółów klienta w BO. | Dodawanie informacji lub działań związanych z VAT dla klientów. |
| `ActionDispatcher` | Przed wysłaniem kontrolera. | Modyfikowanie routingu lub kontekstu na podstawie statusu VAT. |
| `ActionGetProductPropertiesAfter` | Po pobraniu właściwości produktu. | Dostosowywanie cen produktów na podstawie statusu VAT klienta. |
| `ActionProductPriceCalculation` | Podczas obliczania ceny produktu. | Stosowanie 0% VAT do cen produktów, jeśli kwalifikują się. |
| `ActionBeforeValidateOrder` | Tuż przed walidacją zamówienia. | Wykonywanie ostatecznej walidacji VAT, dostosowywanie podatków zamówienia. |
| `ActionCronJob` | Wyzwalane przez moduł cron PrestaShop. | Wykonywanie zadań w tle, takich jak ponowna walidacja VAT. |
| `ActionObjectAddressUpdateAfter` | Po zaktualizowaniu obiektu adresu (np. na koncie klienta). | Ponowna walidacja VAT, jeśli dane adresowe ulegną zmianie. |
| `ActionTaxManager` | Gdy reguły podatkowe są zarządzane lub stosowane. | Przechwytywanie i modyfikowanie zastosowania podatku na podstawie walidacji VAT. |
| `ActionPresentCart` | Przed wyświetleniem koszyka. | Aktualizowanie sum koszyka i wyświetlanie statusu VAT. |
| `ActionFilterDeliveryOptionList` | Filtruje dostępne opcje dostawy. | Potencjalne dostosowanie kosztów dostawy na podstawie statusu VAT (mniej powszechne). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół jest zaangażowany w zapewnienie optymalnego działania modułu i jego kompatybilności z najnowszymi wersjami PrestaShop.

*   **MyPresta.eu Historia zamówień i pobieranie:** [https://mypresta.eu/my-account/orders/](https://mypresta.eu/my-account/orders/)
*   **Wsparcie MyPresta.eu:** [https://mypresta.eu/contact](https://mypresta.eu/contact)
