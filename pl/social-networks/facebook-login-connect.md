---
title: "Facebook Login Connect - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku i referencje dla programistów dla modułu PrestaShop Facebook Login Connect od MyPresta.eu."
sidebar:
  label: "Facebook Login Connect - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Facebook Login Connect na MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-login-connect.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/facebook-login-connect/)
>
> ---


# Facebook Login Connect

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do komunikacji z API Facebooka. Są one prawie zawsze dostępne na każdym nowoczesnym hostingu.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji, na którym ustawisz, jak działa przycisk logowania Facebooka i gdzie się pojawia.

#### Ustawienia ogólne

- **Identyfikator aplikacji Facebook (App ID):**
  - **Co robi to ustawienie:** Jest to unikalny identyfikator dostarczony przez Facebook dla Twojej konkretnej aplikacji. Jest kluczowy dla komunikacji Twojego sklepu z systemem logowania Facebooka.
  - **Efekt zmiany tego ustawienia:** Bez prawidłowego identyfikatora aplikacji przycisk logowania Facebooka nie będzie działać, ponieważ Twój sklep nie będzie mógł uwierzytelnić się na Facebooku.
  - **Zalecana wartość:** Identyfikator aplikacji, który uzyskasz z konta deweloperskiego Facebooka. To pole nie może być puste.
  - **Scenariusz/przykład dla sprzedawcy:** Musisz utworzyć aplikację Facebook na [developers.facebook.com](https://developers.facebook.com/), aby uzyskać ten identyfikator. Postępuj zgodnie z instrukcjami Facebooka, aby skonfigurować podstawową aplikację i włączyć logowanie przez Facebooka.
- **Domyślna grupa klientów dla nowych kont:**
  - **Co robi to ustawienie:** Gdy nowy klient zarejestruje się za pomocą Facebooka, zostanie automatycznie przypisany do tej grupy klientów.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy ustawione na „Klient” (domyślnie):* Nowi użytkownicy Facebooka stają się zwykłymi klientami, podlegającymi standardowym cenom i rabatom Twojego sklepu.
    - *Gdy ustawione na niestandardową grupę (np. „Hurtownik”):* Nowi użytkownicy Facebooka mogą natychmiast uzyskać dostęp do specjalnych cen lub treści, jeśli ta grupa ma określone zasady.
  - **Zalecana wartość:** `Klient` (lub Twoja domyślna grupa klientów dla nowych rejestracji).
  - **Scenariusz/przykład dla sprzedawcy:** Jeśli masz grupę klientów „VIP” ze specjalnymi rabatami, możesz rozważyć przypisanie nowych użytkowników Facebooka najpierw do standardowej grupy „Klient”, a następnie ręczne uaktualnienie ich, jeśli spełniają kryteria VIP.
- **Wyślij e-mail powitalny do nowych klientów:**
  - **Co robi to ustawienie:** Kontroluje, czy PrestaShop wysyła standardowy e-mail powitalny do klientów, którzy zarejestrują się przez Facebooka.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (Tak):* Nowi użytkownicy Facebooka otrzymują e-mail potwierdzający utworzenie konta.
    - *Gdy wyłączone (Nie):* Nie jest wysyłany e-mail powitalny.
  - **Zalecana wartość:** `Tak`. Dobrą praktyką jest witanie nowych klientów i dostarczanie im danych logowania (nawet jeśli używają Facebooka, mogą chcieć później ustawić hasło).
  - **Scenariusz/przykład dla sprzedawcy:** Włączenie tej opcji zapewnia, że nowi klienci czują się mile widziani i mają zapis swojego konta, nawet jeśli nie muszą natychmiast pamiętać hasła.
- **Włącz logowanie w przeglądarce w aplikacji (dla aplikacji mobilnych):**
  - **Co robi to ustawienie:** To ustawienie jest przeznaczone głównie dla sklepów dostępnych za pośrednictwem dedykowanej aplikacji mobilnej (nie tylko przeglądarki mobilnej). Optymalizuje przepływ logowania Facebooka dla przeglądarek w aplikacji.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Poprawia doświadczenie logowania dla użytkowników uzyskujących dostęp do Twojego sklepu za pośrednictwem WebView w aplikacji mobilnej.
    - *Gdy wyłączone:* Używany jest standardowy przepływ logowania w przeglądarce, który może być mniej płynny w dedykowanej aplikacji.
  - **Zalecana wartość:** `Nie`, chyba że masz konkretną aplikację mobilną, która osadza Twój sklep PrestaShop.
  - **Scenariusz/przykład dla sprzedawcy:** Jeśli opracowałeś natywną aplikację iOS lub Android, która wyświetla zawartość Twojego sklepu PrestaShop, włączenie tej opcji może być konieczne dla płynnego logowania przez Facebooka w tej aplikacji.
- **Wyświetl logowanie przez Facebooka w wyskakującym oknie:**
  - **Co robi to ustawienie:** Jeśli Twój motyw używa wyskakującego okna do logowania, ta opcja pozwala na wyświetlenie przycisku logowania Facebooka w tym wyskakującym oknie.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Przycisk logowania Facebooka będzie dostępny w wyskakującym oknie logowania Twojego motywu.
    - *Gdy wyłączone:* Przycisk pojawi się tylko na standardowych stronach logowania lub w innych pozycjach zaczepienia.
  - **Zalecana wartość:** `Tak`, jeśli Twój motyw używa wyskakującego okna logowania.
  - **Scenariusz/przykład dla sprzedawcy:** Wiele nowoczesnych motywów używa szybkiego wyskakującego okna logowania dostępnego z nagłówka. Włączenie tej opcji sprawia, że opcja logowania przez Facebooka jest tam natychmiast widoczna.
- **Język przycisku logowania Facebooka:**
  - **Co robi to ustawienie:** Pozwala określić język przycisku logowania Facebooka i powiązanych komunikatów.
  - **Efekt zmiany tego ustawienia:** Tekst przycisku i wszelkie generowane przez Facebooka monity pojawią się w wybranym języku.
  - **Zalecana wartość:** `Domyślny język PrestaShop` (aby pasował do głównego języka Twojego sklepu) lub `Auto-wykrywanie`, jeśli dostępne.
  - **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój sklep działa w wielu językach, możesz ustawić to tak, aby pasowało do bieżącego języka front-office dla spójnego doświadczenia użytkownika.
- **Zezwól Facebookowi na identyfikację użytkowników (Zaawansowane):**
  - **Co robi to ustawienie:** Jest to zaawansowane ustawienie związane ze śledzeniem tożsamości przez Facebooka. Pozwala Facebookowi potencjalnie śledzić użytkowników na Twojej stronie w celach reklamowych.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Może dostarczyć więcej danych do reklam na Facebooku, ale może mieć konsekwencje dla prywatności w zależności od lokalnych przepisów (np. RODO).
    - *Gdy wyłączone:* Ogranicza zdolność Facebooka do śledzenia użytkowników na Twojej stronie.
  - **Zalecana wartość:** `Nie`, chyba że masz konkretną strategię marketingową, która tego wymaga i zajęłaś się zgodnością z przepisami o ochronie prywatności.
  - **Scenariusz/przykład dla sprzedawcy:** Skonsultuj się ze swoim zespołem marketingowym i doradcą prawnym przed włączeniem tej opcji, zwłaszcza jeśli działasz w regionach z surowymi przepisami o ochronie danych.

#### Opcje wyświetlania (Gdzie wyświetlać przycisk logowania Facebooka)

Te ustawienia kontrolują, w których konkretnych obszarach (hookach) Twojego sklepu PrestaShop będzie wyświetlany przycisk logowania Facebooka. Możesz włączyć lub wyłączyć każdy hook indywidualnie.

- **Wyświetl w górnej części (fbl\_displayTop):**
  - **Co robi to ustawienie:** Pokazuje przycisk w samej górnej sekcji Twojego sklepu, często w pobliżu paska wyszukiwania lub logo.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się w nagłówku.
    - *Wyłączone:* Przycisk jest ukryty z nagłówka.
  - **Zalecana wartość:** `Tak`, dla wysokiej widoczności.
- **Wyświetl w górnej kolumnie (fbl\_displaytopColumn):**
  - **Co robi to ustawienie:** Pokazuje przycisk w głównym obszarze treści, zazwyczaj nad głównymi listami produktów lub treścią na stronie głównej.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się w górnym obszarze treści.
    - *Wyłączone:* Przycisk jest ukryty z tego obszaru.
  - **Zalecana wartość:** `Nie`, chyba że chcesz bardzo widoczny przycisk na stronie głównej.
- **Wyświetl na stronie głównej (fbl\_displayHome):**
  - **Co robi to ustawienie:** Pokazuje przycisk specjalnie na stronie głównej Twojego sklepu.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się na stronie głównej.
    - *Wyłączone:* Przycisk jest ukryty ze strony głównej.
  - **Zalecana wartość:** `Tak`, aby zachęcić do natychmiastowej rejestracji.
- **Wyświetl w nawigacji (fbl\_displayNav):**
  - **Co robi to ustawienie:** Pokazuje przycisk w głównym pasku nawigacyjnym, często obok linków „Moje konto” lub „Kontakt”.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się w nawigacji.
    - *Wyłączone:* Przycisk jest ukryty z nawigacji.
  - **Zalecana wartość:** `Tak`, dla łatwego dostępu z każdej strony.
- **Wyświetl w nawigacji 1 (fbl\_displayNav1):**
  - **Co robi to ustawienie:** Podobnie jak `displayNav`, ale celuje w konkretny hook nawigacji, którego używają niektóre motywy (często dla samego górnego paska).
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się w pierwszym obszarze nawigacji.
    - *Wyłączone:* Przycisk jest ukryty z tego obszaru.
  - **Zalecana wartość:** `Tak`, jeśli Twój motyw używa tego hooka i chcesz tam umieścić przycisk.
- **Wyświetl w nawigacji 2 (fbl\_displayNav2):**
  - **Co robi to ustawienie:** Podobnie jak `displayNav`, ale celuje w drugi hook nawigacji, którego używają niektóre motywy (często dla głównego paska nawigacyjnego).
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się w drugim obszarze nawigacji.
    - *Wyłączone:* Przycisk jest ukryty z tego obszaru.
  - **Zalecana wartość:** `Tak`, jeśli Twój motyw używa tego hooka i chcesz tam umieścić przycisk.
- **Wyświetl w koszyku (fbl\_displayShoppingCart):**
  - **Co robi to ustawienie:** Pokazuje przycisk na stronie podsumowania koszyka.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się na stronie koszyka, umożliwiając szybkie logowanie przed realizacją zamówienia.
    - *Wyłączone:* Przycisk jest ukryty ze strony koszyka.
  - **Zalecana wartość:** `Tak`, aby uprościć realizację zamówienia dla powracających klientów.
- **Wyświetl po formularzu logowania klienta (fbl\_displayCustomerLoginFormAfter):**
  - **Co robi to ustawienie:** Pokazuje przycisk bezpośrednio pod standardowym formularzem logowania PrestaShop.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się jako alternatywna metoda logowania na stronie logowania.
    - *Wyłączone:* Przycisk jest ukryty z tego obszaru.
  - **Zalecana wartość:** `Tak`, jest to doskonała lokalizacja dla alternatywnych opcji logowania.
- **Wyświetl w górnej części informacji osobistych (fbl\_displayPersonalInformationTop):**
  - **Co robi to ustawienie:** Pokazuje przycisk w górnej części sekcji „Informacje osobiste” podczas tworzenia lub edycji konta.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się na stronie informacji osobistych.
    - *Wyłączone:* Przycisk jest ukryty z tego obszaru.
  - **Zalecana wartość:** `Tak`, aby oferować logowanie przez Facebooka jako alternatywę dla wypełniania formularza.
- **Wyświetl w dodatkowym koszyku (fbl\_displayShoppingCartExtra):**
  - **Co robi to ustawienie:** Pokazuje przycisk w dodatkowym obszarze na stronie koszyka, często używanym dla dodatkowych modułów lub informacji.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się w dodatkowym obszarze koszyka.
    - *Wyłączone:* Przycisk jest ukryty z tego obszaru.
  - **Zalecana wartość:** `Nie`, chyba że Twój motyw specjalnie używa tego hooka dla opcji logowania.
- **Wyświetl w lewej kolumnie (fbl\_displayLeftColumn):**
  - **Co robi to ustawienie:** Pokazuje przycisk w lewym pasku bocznym Twojego sklepu (jeśli Twój motyw go posiada).
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się w lewej kolumnie.
    - *Wyłączone:* Przycisk jest ukryty z lewej kolumny.
  - **Zalecana wartość:** `Nie`, chyba że chcesz, aby był widoczny w pasku bocznym.
- **Wyświetl w prawej kolumnie (fbl\_displayRightColumn):**
  - **Co robi to ustawienie:** Pokazuje przycisk w prawym pasku bocznym Twojego sklepu (jeśli Twój motyw go posiada).
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się w prawej kolumnie.
    - *Wyłączone:* Przycisk jest ukryty z prawej kolumny.
  - **Zalecana wartość:** `Nie`, chyba że chcesz, aby był widoczny w pasku bocznym.
- **Wyświetl w formularzu tworzenia konta (fbl\_displayCreateAccountForm):**
  - **Co robi to ustawienie:** Pokazuje przycisk bezpośrednio w standardowym formularzu tworzenia konta PrestaShop.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się jako alternatywna metoda rejestracji na stronie tworzenia konta.
    - *Wyłączone:* Przycisk jest ukryty z tego obszaru.
  - **Zalecana wartość:** `Tak`, jest to kluczowa lokalizacja do uproszczenia rejestracji.
- **Wyświetl w górnej części tworzenia konta (fbl\_displayCreateAccountTop):**
  - **Co robi to ustawienie:** Pokazuje przycisk w samej górnej części strony tworzenia konta, nad polami formularza.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się w górnej części strony tworzenia konta.
    - *Wyłączone:* Przycisk jest ukryty z tego obszaru.
  - **Zalecana wartość:** `Tak`, dla maksymalnej widoczności na stronie rejestracji.
- **Wyświetl w stopce (fbl\_displayFooter):**
  - **Co robi to ustawienie:** Pokazuje przycisk w sekcji stopki Twojego sklepu.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się w stopce.
    - *Wyłączone:* Przycisk jest ukryty ze stopki.
  - **Zalecana wartość:** `Nie`, zazwyczaj nie jest to główna lokalizacja dla przycisków logowania.
- **Wyświetl w nagłówku (fbl\_displayHeader):**
  - **Co robi to ustawienie:** Pokazuje przycisk w sekcji nagłówka Twojego sklepu. Jest to bardzo powszechne i skuteczne umiejscowienie.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się w nagłówku.
    - *Wyłączone:* Przycisk jest ukryty z nagłówka.
  - **Zalecana wartość:** `Tak`, dla wysokiej widoczności na wszystkich stronach.
- **Wyświetl w strefie pierwszej pulpitu nawigacyjnego (fbl\_displayDashboardZoneOne):**
  - **Co robi to ustawienie:** Ten hook jest zazwyczaj przeznaczony do wyświetlania treści na pulpicie nawigacyjnym konta klienta.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się na pulpicie nawigacyjnym klienta.
    - *Wyłączone:* Przycisk jest ukryty z tego obszaru.
  - **Zalecana wartość:** `Nie`, ponieważ klienci są już zalogowani, gdy widzą swój pulpit nawigacyjny.
- **Wyświetl w wyskakującym logowaniu (fbl\_popuplogin):**
  - **Co robi to ustawienie:** Specjalnie celuje w motywy, które używają wyskakującego okna modalnego do logowania.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się w wyskakującym oknie logowania.
    - *Wyłączone:* Przycisk jest ukryty z wyskakującego okna logowania.
  - **Zalecana wartość:** `Tak`, jeśli Twój motyw używa wyskakującego okna logowania.
- **Wyświetl logowanie przez Facebooka (fbl\_fblogin):**
  - **Co robi to ustawienie:** Jest to ogólny hook dla przycisku logowania Facebooka. Może być używany wewnętrznie przez moduł lub przez motywy do niestandardowego umiejscowienia.
  - **Efekt zmiany tego ustawienia:**
    - *Włączone:* Przycisk pojawia się w tym ogólnym hooku.
    - *Wyłączone:* Przycisk jest ukryty z tego hooka.
  - **Zalecana wartość:** `Tak`, jeśli inne konkretne hooki nie działają lub jeśli chcesz mieć opcję awaryjną.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Identyfikator aplikacji Facebook (App ID) | *Twój identyfikator aplikacji Facebook* | Niezbędny do połączenia z Facebookiem; przycisk nie będzie działać bez niego. |
| Konfiguracja modułu | Domyślna grupa klientów dla nowych kont | Klient | Przypisuje nowych użytkowników Facebooka do określonej grupy klientów. |
| Konfiguracja modułu | Wyślij e-mail powitalny do nowych klientów | Tak | Określa, czy nowi użytkownicy Facebooka otrzymają e-mail powitalny. |
| Konfiguracja modułu | Włącz logowanie w przeglądarce w aplikacji | Nie | Optymalizuje logowanie dla dedykowanych aplikacji mobilnych (nie przeglądarek mobilnych). |
| Konfiguracja modułu | Wyświetl logowanie przez Facebooka w wyskakującym oknie | Tak (jeśli motyw używa wyskakującego okna) | Pokazuje przycisk w wyskakującym oknie logowania motywu. |
| Konfiguracja modułu | Język przycisku logowania Facebooka | Domyślny język PrestaShop | Ustawia język dla przycisku Facebooka i monitów. |
| Konfiguracja modułu | Zezwól Facebookowi na identyfikację użytkowników | Nie | Zaawansowana opcja śledzenia; skonsultuj się z prawnikiem/marketingiem. |
| Konfiguracja modułu | Wyświetl w górnej części (fbl\_displayTop) | Tak | Pokazuje przycisk w nagłówku. |
| Konfiguracja modułu | Wyświetl w górnej kolumnie (fbl\_displaytopColumn) | Nie | Pokazuje przycisk w głównym obszarze treści, zazwyczaj nad listami. |
| Konfiguracja modułu | Wyświetl na stronie głównej (fbl\_displayHome) | Tak | Pokazuje przycisk specjalnie na stronie głównej. |
| Konfiguracja modułu | Wyświetl w nawigacji (fbl\_displayNav) | Tak | Pokazuje przycisk w głównym pasku nawigacyjnym. |
| Konfiguracja modułu | Wyświetl w nawigacji 1 (fbl\_displayNav1) | Tak (jeśli motyw używa) | Pokazuje przycisk w określonym górnym obszarze nawigacji. |
| Konfiguracja modułu | Wyświetl w nawigacji 2 (fbl\_displayNav2) | Tak (jeśli motyw używa) | Pokazuje przycisk w określonym głównym obszarze nawigacji. |
| Konfiguracja modułu | Wyświetl w koszyku (fbl\_displayShoppingCart) | Tak | Pokazuje przycisk na stronie podsumowania koszyka. |
| Konfiguracja modułu | Wyświetl po formularzu logowania klienta | Tak | Pokazuje przycisk pod standardowym formularzem logowania. |
| Konfiguracja modułu | Wyświetl w górnej części informacji osobistych | Tak | Pokazuje przycisk w górnej części strony informacji osobistych. |
| Konfiguracja modułu | Wyświetl w dodatkowym koszyku | Nie | Pokazuje przycisk w dodatkowym obszarze koszyka. |
| Konfiguracja modułu | Wyświetl w lewej kolumnie (fbl\_displayLeftColumn) | Nie | Pokazuje przycisk w lewym pasku bocznym. |
| Konfiguracja modułu | Wyświetl w prawej kolumnie (fbl\_displayRightColumn) | Nie | Pokazuje przycisk w prawym pasku bocznym. |
| Konfiguracja modułu | Wyświetl w formularzu tworzenia konta | Tak | Pokazuje przycisk w formularzu tworzenia konta. |
| Konfiguracja modułu | Wyświetl w górnej części tworzenia konta | Tak | Pokazuje przycisk w górnej części strony tworzenia konta. |
| Konfiguracja modułu | Wyświetl w stopce (fbl\_displayFooter) | Nie | Pokazuje przycisk w stopce. |
| Konfiguracja modułu | Wyświetl w nagłówku (fbl\_displayHeader) | Tak | Pokazuje przycisk w sekcji nagłówka. |
| Konfiguracja modułu | Wyświetl w strefie pierwszej pulpitu nawigacyjnego | Nie | Pokazuje przycisk na pulpicie nawigacyjnym konta klienta. |
| Konfiguracja modułu | Wyświetl w wyskakującym logowaniu (fbl\_popuplogin) | Tak (jeśli motyw używa wyskakującego okna) | Pokazuje przycisk w wyskakującym oknie modalnym logowania. |
| Konfiguracja modułu | Wyświetl logowanie przez Facebooka (fbl\_fblogin) | Tak | Ogólny hook dla przycisku logowania Facebooka. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Przycisk logowania Facebooka pojawia się, ale nic się nie dzieje po kliknięciu lub wyświetla błąd.**
O1: To prawie zawsze wskazuje na problem z Twoim identyfikatorem aplikacji Facebook lub samą konfiguracją aplikacji Facebook.
- **Sprawdź swój identyfikator aplikacji Facebook:** Przejdź do konfiguracji modułu w PrestaShop i sprawdź, czy „Identyfikator aplikacji Facebook” jest poprawnie wprowadzony.
- **Sprawdź ustawienia swojej aplikacji Facebook:** Zaloguj się na [developers.facebook.com](https://developers.facebook.com/).
- Upewnij się, że Twoja aplikacja jest „Aktywna” (nie w trybie deweloperskim).
- Przejdź do „Logowanie przez Facebooka” > „Ustawienia” i upewnij się, że „Logowanie OAuth klienta” i „Logowanie OAuth w sieci” są włączone.
- W sekcji „Prawidłowe identyfikatory URI przekierowania OAuth” *musisz* dodać pełną domenę swojego sklepu (np. `https://www.twoj-sklep.com/`). Czasami może być również konieczne dodanie `https://www.twoj-sklep.com/module/fblogin/index` lub `https://www.twoj-sklep.com/module/fblogin/loginloader` w zależności od wersji PrestaShop i struktury URL.
- Upewnij się, że „Adres URL polityki prywatności” i „Adres URL warunków świadczenia usług” są ustawione w „Podstawowych ustawieniach” Twojej aplikacji Facebook.
- **Wyczyść pamięć podręczną:** Po wprowadzeniu jakichkolwiek zmian wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną).

**P2: Nowi klienci rejestrują się przez Facebooka, ale ich imiona, nazwiska lub adresy e-mail nie pojawiają się poprawnie.**
O2: Moduł pobiera publiczne informacje profilowe z Facebooka.
- Upewnij się, że klient udzielił Twojej aplikacji pozwolenia na dostęp do jego podstawowego profilu i adresu e-mail.
- API Facebooka dostarcza imię, nazwisko i adres e-mail. Jeśli brakuje tych danych lub są one nieprawidłowe, zazwyczaj jest to problem z ustawieniami prywatności profilu Facebooka klienta lub rzadka usterka API.
- Moduł tworzy nowe konto, jeśli nie znajdzie pasującego adresu e-mail. Jeśli adres e-mail już istnieje w bazie danych PrestaShop, moduł powinien próbować zalogować użytkownika na to istniejące konto.

**P3: Przycisk Facebooka nie pojawia się w oczekiwanym miejscu, nawet po włączeniu hooka.**
O3:
- **Wyczyść pamięć podręczną:** Zawsze wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) po zmianie ustawień hooka.
- **Kompatybilność motywu:** Niektóre niestandardowe motywy mogą nadpisywać standardowe hooki PrestaShop lub mieć unikalne struktury. Jeśli przycisk się nie pojawia, Twój motyw może nie wyświetlać aktywnie tego konkretnego hooka. Może być konieczne skonsultowanie się z deweloperem motywu lub webmasterem w celu ręcznej integracji go z plikami `.tpl` Twojego motywu.
- **Sprawdź pozycje modułów:** Przejdź do Wygląd > Pozycje (lub Moduły > Pozycje w starszych wersjach) i wyszukaj `fblogin`. Upewnij się, że moduł jest „zahaczony” do żądanych pozycji. Jeśli nie, możesz ręcznie „Przeszczepić moduł” do prawidłowego hooka.

**P4: Czy klienci, którzy zarejestrowali się przez Facebooka, mogą później ustawić hasło, aby logować się bezpośrednio?**
O4: Tak. Po utworzeniu konta przez Facebooka jest to standardowe konto klienta PrestaShop.
- Klienci mogą użyć linku „Nie pamiętasz hasła?” na stronie logowania Twojego sklepu. Otrzymają e-mail z prośbą o ustawienie nowego hasła, co pozwoli im zalogować się bezpośrednio za pomocą swojego adresu e-mail i nowego hasła, nawet bez Facebooka.

**P5: Czy ten moduł obsługuje wiele języków dla przycisku?**
O5: Tak, moduł ma ustawienie „Język przycisku logowania Facebooka”. Możesz ustawić go tak, aby pasował do domyślnego języka Twojego sklepu, lub w niektórych przypadkach SDK Facebooka może automatycznie wykryć język przeglądarki użytkownika.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł `Facebook Login Connect` integruje JavaScript SDK Facebooka, aby ułatwić uwierzytelnianie użytkowników. Działa głównie poprzez zaczepianie się w różnych punktach wyświetlania front-office w celu renderowania przycisku logowania Facebooka. Po udanym logowaniu przez Facebooka, kontroler frontowy obsługuje wywołanie zwrotne, pobiera dane użytkownika z Facebooka i albo loguje istniejącego klienta PrestaShop, albo tworzy nowego. Następnie przekierowuje użytkownika na jego stronę konta lub stronę główną. Moduł wykorzystuje klasę `Module` PrestaShop do konfiguracji i zarządzania hookami, z minimalną liczbą niestandardowych klas, opierając się w dużej mierze na głównym pliku `fblogin.php` dla podstawowej logiki.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:

  - `controllers/front/index.php`
    - **Nazwa klasy:** `FbloginIndexModuleFrontController`
    - **Klasa nadrzędna:** `ModuleFrontController`
    - **Odpowiedzialność:** Ten kontroler działa jako główny punkt końcowy wywołania zwrotnego dla procesu uwierzytelniania Facebooka. Po pomyślnym zalogowaniu się użytkownika przez Facebooka, Facebook przekierowuje do tego kontrolera. Obsługuje pobieranie tokena dostępu Facebooka, pobiera dane profilu użytkownika (imię, nazwisko, e-mail), a następnie loguje istniejącego klienta PrestaShop lub tworzy nowego. Następnie przekierowuje użytkownika na jego stronę konta lub stronę główną.
  - `controllers/front/loginloader.php`
    - **Nazwa klasy:** `FbloginLoginloaderModuleFrontController`
    - **Klasa nadrzędna:** `ModuleFrontController`
    - **Odpowiedzialność:** Ten kontroler jest prawdopodobnie awaryjnym lub alternatywnym punktem wejścia dla procesu logowania Facebooka, potencjalnie używanym w określonych scenariuszach lub starszych wersjach PrestaShop. Wykonywałby podobne zadania uwierzytelniania i zarządzania użytkownikami jak `index.php`.
- **Kontrolery administracyjne Back-Office**:

  - Brak. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

- Brak. Moduł nie definiuje żadnych niestandardowych klas `ObjectModel` ani innych klas logiki biznesowej w katalogu `classes/`. Cała podstawowa logika jest hermetyzowana w klasie `Fblogin` w `fblogin.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

- `views/js/fblogin4.js`
  - **Zakres:** Front-office.
  - **Odpowiedzialność:** Ten skrypt jest odpowiedzialny za inicjalizację JavaScript SDK Facebooka. Ładuje SDK, konfiguruje `FB.init` (w tym identyfikator aplikacji i żądane uprawnienia) oraz obsługuje wywołanie `FB.login` po kliknięciu przycisku logowania Facebooka. Prawdopodobnie nasłuchuje zdarzenia `auth.statusChange`, aby wykryć stany logowania/wylogowania i przekierowuje użytkownika do odpowiedniego kontrolera frontowego PrestaShop (`index.php` lub `loginloader.php`) po pomyślnym uwierzytelnieniu. Zarządza również wyświetlaniem przycisku logowania Facebooka i jego interakcją.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `css.css`
  - **Zakres:** Front-office.
  - **Odpowiedzialność:** Jest to prawdopodobnie ogólny arkusz stylów dla modułu, zapewniający podstawowe style dla przycisku logowania Facebooka i wszelkich powiązanych elementów interfejsu użytkownika.
- `views/css/fblogin.css`
  - **Zakres:** Front-office.
  - **Odpowiedzialność:** Zapewnia specyficzne reguły stylów dla przycisku logowania Facebooka i jego kontenera, zapewniając spójny wygląd w różnych motywach. Może zawierać style dla rozmiaru przycisku, koloru, efektów najechania i wyrównania.
- `views/css/fblogin17.css`
  - **Zakres:** Front-office.
  - **Odpowiedzialność:** Ten arkusz stylów prawdopodobnie zawiera specyficzne nadpisania lub dodatkowe style dostosowane do PrestaShop 1.7.x i nowszych wersji, uwzględniające potencjalne różnice w układzie lub stylach w nowszych strukturach motywów.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:

  - `createAccountForm.tpl`: Renderuje przycisk logowania Facebooka w standardowym formularzu tworzenia konta.
  - `createAccountTop.tpl`: Renderuje przycisk logowania Facebooka w górnej części strony tworzenia konta.
  - `dashboardZoneOne.tpl`: Renderuje przycisk logowania Facebooka w pierwszej strefie pulpitu nawigacyjnego klienta (mniej typowe dla logowania, ale dostępne).
  - `displayCustomerLoginFormAfter.tpl`: Renderuje przycisk logowania Facebooka bezpośrednio po standardowym formularzu logowania klienta.
  - `displayNav.tpl`: Renderuje przycisk logowania Facebooka w głównym pasku nawigacyjnym.
  - `displayPersonalInformationTop.tpl`: Renderuje przycisk logowania Facebooka w górnej części strony informacji osobistych.
  - `displayPopUpLogin.tpl`: Renderuje przycisk logowania Facebooka w wyskakującym oknie modalnym logowania motywu.
  - `fblogin.tpl`: Ogólny szablon dla przycisku logowania Facebooka, potencjalnie używany przez `displayfblogin` lub jako awaryjny.
  - `footer.tpl`: Renderuje przycisk logowania Facebooka w stopce sklepu.
  - `header.tpl`: Renderuje przycisk logowania Facebooka w nagłówku sklepu.
  - `home.tpl`: Renderuje przycisk logowania Facebooka na stronie głównej.
  - `leftcolumn.tpl`: Renderuje przycisk logowania Facebooka w lewym pasku bocznym.
  - `rightcolumn.tpl`: Renderuje przycisk logowania Facebooka w prawym pasku bocznym.
  - `shoppingCart.tpl`: Renderuje przycisk logowania Facebooka na stronie koszyka.
  - `shoppingCartExtra.tpl`: Renderuje przycisk logowania Facebooka w dodatkowym obszarze strony koszyka.
  - `top.tpl`: Renderuje przycisk logowania Facebooka w samej górnej sekcji sklepu.
  - `topColumn.tpl`: Renderuje przycisk logowania Facebooka w głównym obszarze treści, zazwyczaj nad listami produktów.
- **Szablony administracyjne (`views/templates/admin/`)**:

  - Brak. Konfiguracja modułu jest renderowana bezpośrednio za pomocą `getContent()` w `fblogin.php` przy użyciu standardowych pomocników formularzy PrestaShop.
- **Szablony Front-office (`views/templates/front/`)**:

  - Brak. Całe wyświetlanie front-office jest obsługiwane za pomocą szablonów hooków.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration` przy użyciu kluczy takich jak `FBL_APPID`, `FBL_GROUPID`, `FBL_POPUP_LOGIN`, `FBL_DISPLAYTOP` itp.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayRightColumn` | Renderuje zawartość w prawym pasku bocznym. | Wyświetla przycisk logowania Facebooka w prawej kolumnie. |
| `displaypopuplogin` | Renderuje zawartość w wyskakującym oknie logowania motywu. | Wyświetla przycisk logowania Facebooka w wyskakującym oknie logowania. |
| `displayCreateAccountForm` | Renderuje zawartość w formularzu tworzenia konta klienta. | Wyświetla przycisk logowania Facebooka jako alternatywną metodę rejestracji. |
| `displayPersonalInformationTop` | Renderuje zawartość w górnej części strony informacji osobistych. | Wyświetla przycisk logowania Facebooka do szybkiej rejestracji/logowania. |
| `displayTop` | Renderuje zawartość w samej górnej sekcji sklepu. | Wyświetla przycisk logowania Facebooka w górnym pasku nagłówka. |
| `displayCreateAccountTop` | Renderuje zawartość w górnej części strony tworzenia konta. | Wyświetla przycisk logowania Facebooka nad formularzem rejestracji. |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` HTML i potencjalnie widocznych elementach nagłówka. | Wstrzykuje JavaScript SDK Facebooka i wyświetla przycisk logowania w nagłówku. |
| `displayNav` | Renderuje zawartość w głównym pasku nawigacyjnym. | Wyświetla przycisk logowania Facebooka w nawigacji. |
| `displayDashboardZoneOne` | Renderuje zawartość w pierwszej strefie pulpitu nawigacyjnego klienta. | Wyświetla przycisk logowania Facebooka (mniej typowe dla zalogowanych użytkowników). |
| `displayNav2` | Renderuje zawartość w drugim pasku nawigacyjnym (zależne od motywu). | Wyświetla przycisk logowania Facebooka w drugiej nawigacji. |
| `displayShoppingCart` | Renderuje zawartość na stronie podsumowania koszyka. | Wyświetla przycisk logowania Facebooka do szybkiego logowania przed realizacją zamówienia. |
| `displayTopColumn` | Renderuje zawartość w głównym obszarze treści, zazwyczaj nad listami. | Wyświetla przycisk logowania Facebooka w górnej kolumnie treści. |
| `displayFooter` | Renderuje zawartość w stopce sklepu. | Wyświetla przycisk logowania Facebooka w stopce. |
| `displayfblogin` | Niestandardowy hook zdefiniowany przez sam moduł. | Zapewnia elastyczny punkt dla motywów do integracji przycisku logowania Facebooka. |
| `displayHome` | Renderuje zawartość na stronie głównej sklepu. | Wyświetla przycisk logowania Facebooka na stronie głównej. |
| `displayLeftColumn` | Renderuje zawartość w lewym pasku bocznym. | Wyświetla przycisk logowania Facebooka w lewej kolumnie. |
| `displayCustomerLoginFormAfter` | Renderuje zawartość bezpośrednio po standardowym formularzu logowania klienta. | Wyświetla przycisk logowania Facebooka jako alternatywną metodę logowania. |
| `displayShoppingCartExtra` | Renderuje zawartość w dodatkowym obszarze strony koszyka. | Wyświetla przycisk logowania Facebooka w dodatkowym obszarze koszyka. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu „Facebook Login Connect”.
