---
title: "Social tabs slider - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Social tabs slider od MyPresta.eu."
sidebar:
  label: "Social tabs slider - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Social tabs slider na MyPresta.eu](https://mypresta.eu/modules/social-networks/social-tabs-slider.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/social-networks/social-tabs-slider/)
>
> ---


# Social tabs slider

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i zapewniają prawidłową komunikację z API mediów społecznościowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

To jest główny ekran, na którym ustawisz wszystkie opcje dla swojego Social tabs slider.

#### Ustawienia ogólne

- **Szablon:**

  - **Co robi to ustawienie:** Pozwala wybrać styl wizualny i projekt zakładek społecznościowych. Moduł zawiera kilka wstępnie zaprojektowanych szablonów.
  - **Efekt zmiany tego ustawienia:**
    - *Po ustawieniu na Szablon 1, 2, 3 itd.:* Wygląd ikon społecznościowych, projekt zakładki i potencjalnie styl animacji zmienią się w Twoim front office.
  - **Zalecana wartość:** Eksperymentuj, aby znaleźć ten, który najlepiej pasuje do motywu Twojego sklepu.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój sklep ma minimalistyczny design, możesz wybrać szablon z czystymi, płaskimi ikonami. Jeśli wolisz bardziej żywy wygląd, inny szablon może oferować kolorowe, błyszczące ikony.
- **Pozycja:**

  - **Co robi to ustawienie:** Określa, gdzie suwak zakładek społecznościowych pojawi się na Twojej stronie internetowej.
  - **Efekt zmiany tego ustawienia:**
    - *Po ustawieniu na „Lewo”:* Suwak zostanie przypięty do lewej strony okna przeglądarki.
    - *Po ustawieniu na „Prawo”:* Suwak zostanie przypięty do prawej strony okna przeglądarki.
  - **Zalecana wartość:** „Lewo” lub „Prawo” w zależności od układu Twojego motywu i tego, gdzie powoduje mniej zakłóceń z innymi elementami.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twój motyw ma lewy pasek boczny, możesz wybrać „Prawo”, aby uniknąć bałaganu. Jeśli Twój motyw jest szeroki i wyśrodkowany, zarówno „Lewo”, jak i „Prawo” mogą działać dobrze.
- **Ostatnia zakładka otwarta domyślnie:**

  - **Co robi to ustawienie:** Kontroluje, czy jedna z zakładek społecznościowych powinna automatycznie otwierać się, gdy odwiedzający po raz pierwszy wyląduje na Twojej stronie.
  - **Efekt zmiany tego ustawienia:**
    - *Po ustawieniu na „TAK”:* Ostatnia zakładka społecznościowa, która została otwarta przez poprzedniego odwiedzającego (lub domyślna, jeśli brak historii), automatycznie wysunie się, gdy pojawi się nowy odwiedzający.
    - *Po ustawieniu na „NIE”:* Wszystkie zakładki społecznościowe pozostaną zamknięte, dopóki odwiedzający aktywnie nie kliknie lub nie najedzie na jedną z nich.
  - **Zalecana wartość:** „NIE”, aby uniknąć potencjalnego irytowania odwiedzających automatycznie otwierającą się zakładką.
  - **Scenariusz / przykład dla sprzedawcy:** Możesz ustawić na „TAK” tymczasowo, jeśli prowadzisz specjalną kampanię w jednej sieci społecznościowej i chcesz natychmiast zwrócić na nią uwagę, ale ogólnie „NIE” zapewnia lepsze wrażenia użytkownika.

#### Ustawienia pola „Lubię to” na Facebooku

- **Wyświetl pole „Lubię to” na Facebooku:**

  - **Co robi to ustawienie:** Przełącza widoczność zakładki Facebooka i osadzonego pola „Lubię to”.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu (TAK):* Zakładka Facebooka pojawi się w suwaku, a po otwarciu wyświetli pole „Lubię to” Twojej strony fanowskiej na Facebooku.
    - *Po wyłączeniu (NIE):* Zakładka Facebooka nie będzie wyświetlana w suwaku.
  - **Zalecana wartość:** „TAK”, jeśli masz aktywną stronę na Facebooku, którą chcesz promować.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli Facebook jest głównym kanałem interakcji z klientami i marketingu, z pewnością będziesz chciał to włączyć.
- **Wysokość pola „Lubię to” na Facebooku:**

  - **Co robi to ustawienie:** Ustawia pionowy rozmiar obszaru zawartości pola „Lubię to” na Facebooku, gdy zakładka jest otwarta.
  - **Efekt zmiany tego ustawienia:**
    - *Po ustawieniu na wyższą wartość (np. 500px):* Więcej treści (postów, twarzy) z Twojej strony na Facebooku będzie widocznych w zakładce.
    - *Po ustawieniu na niższą wartość (np. 200px):* Mniej treści będzie widocznych, co wymaga przewijania, jeśli kanał jest długi.
  - **Zalecana wartość:** Zacznij od `280px` i dostosuj w zależności od tego, ile treści chcesz pokazać i jak wygląda to na Twojej stronie.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli często publikujesz i chcesz, aby odwiedzający widzieli więcej Twojej ostatniej aktywności, zwiększ wysokość.
- **Schemat kolorów pola „Lubię to” na Facebooku:**

  - **Co robi to ustawienie:** Zmienia motyw kolorystyczny samego pola „Lubię to” na Facebooku (nie ikony zakładki).
  - **Efekt zmiany tego ustawienia:**
    - *Po ustawieniu na „Jasny”:* Tło i tekst pola „Lubię to” będą używać jaśniejszych kolorów.
    - *Po ustawieniu na „Ciemny”:* Tło i tekst pola „Lubię to” będą używać ciemniejszych kolorów.
  - **Zalecana wartość:** Wybierz „Jasny” lub „Ciemny”, aby najlepiej pasował do ogólnego projektu Twojego sklepu.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja strona internetowa ma ciemne tło, ciemny schemat kolorów dla pola „Lubię to” może lepiej integrować się wizualnie.
- **Pokaż twarze w polu „Lubię to” na Facebooku:**

  - **Co robi to ustawienie:** Określa, czy zdjęcia profilowe osób, które lubią Twoją stronę, są wyświetlane w polu „Lubię to”.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu (TAK):* Zostanie wyświetlony rząd zdjęć profilowych fanów Twojej strony.
    - *Po wyłączeniu (NIE):* Zdjęcia profilowe nie będą wyświetlane.
  - **Zalecana wartość:** „TAK”, ponieważ dodaje element dowodu społecznego, pokazując, że prawdziwi ludzie lubią Twoją stronę.
  - **Scenariusz / przykład dla sprzedawcy:** Pokazywanie twarzy może zachęcić innych do polubienia Twojej strony, ponieważ demonstruje popularność.
- **Kolor obramowania pola „Lubię to” na Facebooku:**

  - **Co robi to ustawienie:** Ustawia kolor obramowania wokół pola „Lubię to” na Facebooku.
  - **Efekt zmiany tego ustawienia:**
    - *Po ustawieniu na konkretny kolor (np. #CCCCCC):* Obramowanie pojawi się w tym kolorze.
  - **Zalecana wartość:** Kolor, który uzupełnia projekt Twojej strony internetowej lub jest przezroczysty/niewidoczny, jeśli wolisz.
  - **Scenariusz / przykład dla sprzedawcy:** Możesz użyć głównego koloru swojej marki dla obramowania, aby wzmocnić branding.
- **Pokaż strumień w polu „Lubię to” na Facebooku:**

  - **Co robi to ustawienie:** Kontroluje, czy Twoje ostatnie posty na Facebooku („strumień”) są wyświetlane w polu „Lubię to”.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu (TAK):* Twoje najnowsze posty na Facebooku będą widoczne w zakładce.
    - *Po wyłączeniu (NIE):* Wyświetlony zostanie tylko przycisk „Lubię to” i potencjalnie twarze, bez strumienia postów.
  - **Zalecana wartość:** „TAK”, aby dostarczać świeże treści i zachęcać do zaangażowania.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli regularnie udostępniasz wiadomości, promocje lub aktualizacje produktów na Facebooku, wyświetlanie strumienia informuje odwiedzających.
- **Pokaż nagłówek pola „Lubię to” na Facebooku:**

  - **Co robi to ustawienie:** Przełącza widoczność nagłówka „Znajdź nas na Facebooku” u góry pola „Lubię to”.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu (TAK):* Nagłówek zostanie wyświetlony.
    - *Po wyłączeniu (NIE):* Nagłówek zostanie ukryty, co sprawi, że pole „Lubię to” będzie bardziej kompaktowe.
  - **Zalecana wartość:** „TAK” dla jasności, lub „NIE”, jeśli chcesz uzyskać czystszy wygląd i zakładasz, że użytkownicy rozumieją, że to Facebook.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli przestrzeń jest ograniczona, ukrycie nagłówka może zaoszczędzić miejsce w pionie.
- **Adres URL strony fanowskiej na Facebooku:**

  - **Co robi to ustawienie:** To jest najważniejsze ustawienie dla Facebooka. Musisz wprowadzić pełny adres URL swojej strony fanowskiej na Facebooku.
  - **Efekt zmiany tego ustawienia:**
    - *Po prawidłowym wprowadzeniu:* Zakładka Facebooka wyświetli pole „Lubię to” dla określonej strony.
    - *Po nieprawidłowym lub pustym wprowadzeniu:* Zakładka Facebooka może nie wyświetlać się poprawnie lub wyświetli błąd.
  - **Zalecana wartość:** Dokładny adres URL Twojej strony fanowskiej na Facebooku (np. `https://www.facebook.com/MyPresta`).
  - **Scenariusz / przykład dla sprzedawcy:** Skopiuj i wklej adres URL bezpośrednio z przeglądarki podczas przeglądania swojej strony na Facebooku, aby zapewnić dokładność.

#### Ustawienia Google+

- **Wyświetl obserwowanie Google+:**

  - **Co robi to ustawienie:** Przełącza widoczność zakładki Google+ i osadzonego przycisku obserwowania/profilu.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu (TAK):* Zakładka Google+ pojawi się w suwaku.
    - *Po wyłączeniu (NIE):* Zakładka Google+ nie będzie wyświetlana.
  - **Zalecana wartość:** „TAK”, jeśli aktywnie używasz Google+ (chociaż jego użycie spadło, nadal może być istotne dla niektórych nisz).
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja firma ma silną obecność w Google Moja Firma lub specyficzne lokalne strategie SEO związane z Google+, może to być korzystne.
- **ID profilu Google+:**

  - **Co robi to ustawienie:** Musisz podać swój ID profilu Google+ (ciąg cyfr), aby moduł wyświetlał prawidłowy profil.
  - **Efekt zmiany tego ustawienia:**
    - *Po prawidłowym wprowadzeniu:* Zakładka Google+ wyświetli przycisk obserwowania/profil dla określonego ID.
    - *Po nieprawidłowym lub pustym wprowadzeniu:* Zakładka Google+ może nie wyświetlać się poprawnie.
  - **Zalecana wartość:** Twój ID profilu Google+.
  - **Scenariusz / przykład dla sprzedawcy:** Znajdź swój ID Google+, przechodząc do strony swojego profilu Google+ i patrząc na adres URL (zazwyczaj jest to długi ciąg cyfr).

#### Ustawienia Twittera

- **Wyświetl oś czasu użytkownika Twittera:**

  - **Co robi to ustawienie:** Przełącza widoczność zakładki Twittera i osadzonego widżetu osi czasu użytkownika.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu (TAK):* Zakładka Twittera pojawi się w suwaku, pokazując Twoje ostatnie tweety.
    - *Po wyłączeniu (NIE):* Zakładka Twittera nie będzie wyświetlana.
  - **Zalecana wartość:** „TAK”, jeśli masz aktywne konto Twitter dla swojej firmy.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli używasz Twittera do obsługi klienta, ogłoszeń lub szybkich wyprzedaży, to świetny sposób na bieżąco informowanie odwiedzających.
- **Nazwa użytkownika Twittera:**

  - **Co robi to ustawienie:** Określa konto Twittera, którego oś czasu będzie wyświetlana.
  - **Efekt zmiany tego ustawienia:**
    - *Po prawidłowym wprowadzeniu (np. MyPresta):* Zakładka Twittera pokaże tweety z tej nazwy użytkownika.
    - *Po nieprawidłowym lub pustym wprowadzeniu:* Zakładka Twittera może nie wyświetlać się poprawnie.
  - **Zalecana wartość:** Twoja nazwa użytkownika Twittera (bez symbolu „@”).
  - **Scenariusz / przykład dla sprzedawcy:** Wprowadź `MyPresta`, jeśli Twój uchwyt Twittera to `@MyPresta`.
- **ID widżetu Twittera:**

  - **Co robi to ustawienie:** Jest to unikalny ID generowany przez Twittera, gdy tworzysz osadzony widżet osi czasu. Jest to kluczowe dla funkcjonowania widżetu.
  - **Efekt zmiany tego ustawienia:**
    - *Po prawidłowym wprowadzeniu:* Oś czasu Twittera załaduje się i wyświetli poprawnie.
    - *Po nieprawidłowym lub pustym wprowadzeniu:* Zakładka Twittera prawdopodobnie wyświetli błąd lub pozostanie pusta.
  - **Zalecana wartość:** Twój ID widżetu Twittera.
  - **Scenariusz / przykład dla sprzedawcy:** Aby to uzyskać, przejdź do [Twitter Publish](https://publish.twitter.com/), wybierz „Osadzona oś czasu”, wprowadź adres URL swojego profilu i skopiuj `data-widget-id` z wygenerowanego kodu.

#### Ustawienia YouTube

- **Wyświetl konto YouTube:**

  - **Co robi to ustawienie:** Przełącza widoczność zakładki YouTube i osadzonego kanału/kanału użytkownika.
  - **Efekt zmiany tego ustawienia:**
    - *Po włączeniu (TAK):* Zakładka YouTube pojawi się w suwaku.
    - *Po wyłączeniu (NIE):* Zakładka YouTube nie będzie wyświetlana.
  - **Zalecana wartość:** „TAK”, jeśli masz kanał YouTube z filmami produktowymi, samouczkami lub treściami marki.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz produkty, które korzystają z demonstracji wideo, to doskonały sposób na ich prezentację.
- **Nazwa użytkownika YouTube:**

  - **Co robi to ustawienie:** Określa kanał YouTube lub użytkownika, którego filmy będą wyświetlane.
  - **Efekt zmiany tego ustawienia:**
    - *Po prawidłowym wprowadzeniu:* Zakładka YouTube wyświetli treści z tego kanału/użytkownika.
    - *Po nieprawidłowym lub pustym wprowadzeniu:* Zakładka YouTube może nie wyświetlać się poprawnie.
  - **Zalecana wartość:** Niestandardowa nazwa URL Twojego kanału YouTube lub starsza nazwa użytkownika.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli adres URL Twojego kanału YouTube to `youtube.com/user/MyPrestaVideos`, Twoja nazwa użytkownika to `MyPrestaVideos`. Jeśli to `youtube.com/c/MyPresta`, być może będziesz musiał znaleźć starszą nazwę użytkownika lub ID kanału.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Szablon** | (Wybierz najlepiej pasujący) | Zmienia styl wizualny zakładek społecznościowych. |
| | **Pozycja** | Prawo | Określa, czy zakładki pojawiają się po lewej czy prawej stronie przeglądarki. |
| | **Ostatnia zakładka otwarta domyślnie** | NIE | Kontroluje, czy zakładka automatycznie otwiera się po załadowaniu strony. |
| | **Wyświetl pole „Lubię to” na Facebooku** | TAK | Pokazuje/ukrywa zakładkę Facebooka. |
| | **Wysokość pola „Lubię to” na Facebooku** | 280px | Ustawia wysokość obszaru treści Facebooka. |
| | **Schemat kolorów pola „Lubię to” na Facebooku** | Jasny | Zmienia schemat kolorów pola „Lubię to” na Facebooku. |
| | **Pokaż twarze w polu „Lubię to” na Facebooku** | TAK | Wyświetla zdjęcia profilowe fanów. |
| | **Kolor obramowania pola „Lubię to” na Facebooku** | (puste/przezroczyste) | Ustawia kolor obramowania pola „Lubię to”. |
| | **Pokaż strumień w polu „Lubię to” na Facebooku** | TAK | Wyświetla ostatnie posty na Facebooku. |
| | **Pokaż nagłówek pola „Lubię to” na Facebooku** | TAK | Pokazuje/ukrywa nagłówek „Znajdź nas na Facebooku”. |
| | **Adres URL strony fanowskiej na Facebooku** | (Twój adres URL Facebooka) | **KRYTYCZNE:** Adres URL Twojej strony fanowskiej na Facebooku. |
| | **Wyświetl obserwowanie Google+** | NIE | Pokazuje/ukrywa zakładkę Google+. |
| | **ID profilu Google+** | (Twój ID Google+) | **KRYTYCZNE:** Twój numeryczny ID profilu Google+. |
| | **Wyświetl oś czasu użytkownika Twittera** | TAK | Pokazuje/ukrywa zakładkę Twittera. |
| | **Nazwa użytkownika Twittera** | (Twój uchwyt Twittera) | **KRYTYCZNE:** Twoja nazwa użytkownika Twittera (np. `MyPresta`). |
| | **ID widżetu Twittera** | (Twój ID widżetu Twittera) | **KRYTYCZNE:** Unikalny ID dla widżetu osi czasu Twittera. |
| | **Wyświetl konto YouTube** | TAK | Pokazuje/ukrywa zakładkę YouTube. |
| | **Nazwa użytkownika YouTube** | (Twoja nazwa użytkownika YouTube) | **KRYTYCZNE:** Nazwa użytkownika lub starszy ID Twojego kanału YouTube. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Zakładki społecznościowe nie pojawiają się w moim sklepie lub wyświetlają się tylko niektóre z nich.**
**O1:**

- **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Social tabs slider” jest zainstalowany i włączony.
- **Zweryfikuj konfigurację:** Przejdź do strony konfiguracji modułu. Upewnij się, że „Wyświetl pole „Lubię to” na Facebooku”, „Wyświetl obserwowanie Google+” itp. są ustawione na „TAK” dla zakładek, które chcesz wyświetlić.
- **Poprawne ID/URL:** Dokładnie sprawdź, czy adres URL Twojej strony fanowskiej na Facebooku, ID profilu Google+, nazwa użytkownika/ID widżetu Twittera i nazwa użytkownika YouTube są wprowadzone *dokładnie* tak, jak wymagane. Pojedyncza literówka uniemożliwi załadowanie zakładki.
- **Kompatybilność z motywem:** Niektóre wysoce spersonalizowane motywy mogą mieć problemy z hookami modułów. Spróbuj tymczasowo przełączyć się na domyślny motyw PrestaShop, aby sprawdzić, czy zakładki się pojawiają. Jeśli tak, Twój motyw może wymagać drobnych poprawek.
- **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stare pliki pamięci podręcznej uniemożliwiają wyświetlanie nowej zawartości modułu.

**P2: Moja zakładka Facebooka/Twittera/YouTube wyświetla błąd lub jest pusta po otwarciu.**
**O2:**

- **Nieprawidłowe ID/URL:** To jest najczęstszy powód. Ponownie zweryfikuj każdy znak adresu URL Twojej strony fanowskiej na Facebooku, ID profilu Google+, nazwy użytkownika Twittera, ID widżetu Twittera i nazwy użytkownika YouTube. Nawet brakujący ukośnik lub dodatkowa spacja mogą powodować problemy.
- **Zmiany API:** Platformy mediów społecznościowych od czasu do czasu aktualizują swoje API lub kody osadzania. Upewnij się, że Twoja wersja modułu jest aktualna z MyPresta.eu.
- **Ustawienia prywatności:** Upewnij się, że Twoje strony/profile w mediach społecznościowych są publiczne i dostępne. Jeśli są ustawione jako prywatne, moduł nie będzie w stanie wyświetlić ich zawartości.
- **Problemy z siecią:** Tymczasowo wyłącz wszelkie blokery reklam lub rozszerzenia przeglądarki, które mogą zakłócać działanie widżetów mediów społecznościowych.

**P3: Zakładki społecznościowe wyglądają dziwnie lub są źle wyrównane na moim urządzeniu mobilnym.**
**O3:**

- **Responsywność motywu:** Chociaż moduł jest zaprojektowany tak, aby był responsywny, jego wygląd może być zależny od ogólnej responsywności motywu PrestaShop.
- **Konflikty CSS:** CSS Twojego motywu może nadpisywać stylizację modułu. Jeśli masz webmastera, może on zbadać elementy za pomocą narzędzi deweloperskich przeglądarki, aby zidentyfikować konflikty.
- **Szablon modułu:** Spróbuj przełączyć się na inny „Szablon” w konfiguracji modułu, aby sprawdzić, czy któryś lepiej dostosowuje się do urządzeń mobilnych.
- **Wyczyść pamięć podręczną:** Zawsze czyść pamięć podręczną PrestaShop po wprowadzeniu zmian w konfiguracji.

**P4: Jak uzyskać mój ID widżetu Twittera?**
**O4:**

1. Przejdź do [Twitter Publish](https://publish.twitter.com/).
2. Wybierz „Osadzona oś czasu”.
3. Wprowadź pełny adres URL swojego profilu na Twitterze (np. `https://twitter.com/MyPresta`).
4. Kliknij strzałkę, a następnie wybierz „Osadzona oś czasu”.
5. Twitter wygeneruje kod. Poszukaj `data-widget-id="TWÓJ_ID_WIDŻETU_TUTAJ"` w tym kodzie. Skopiuj tylko numeryczny ID.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Social tabs slider” to klasyczny moduł PrestaShop zaimplementowany jako pojedynczy plik PHP (`socialslider.php`) zgodnie ze strukturą modułów PrestaShop. Wykorzystuje system hooków PrestaShop do wstrzykiwania swojego CSS, JavaScript i treści HTML do front office. Konfiguracja jest zarządzana za pomocą metody `getContent()` w głównej klasie modułu, przechowując ustawienia w `ps_configuration`. Moduł używa zewnętrznych bibliotek JavaScript (jscolor) i niestandardowych skryptów do obsługi animacji przesuwania i ładowania widżetów mediów społecznościowych.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** wykorzystuje niestandardowych kontrolerów Front Office ani Back Office Admin. Cała logika jest hermetyzowana w głównym pliku modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

Ten moduł **nie** definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Cała logika rdzenia znajduje się w klasie `Socialslider` w `socialslider.php`. Wartości konfiguracyjne są przechowywane bezpośrednio w tabeli `ps_configuration` za pomocą `Configuration::get()` i `Configuration::updateValue()`.

### 4.4 Zasoby JavaScript (`views/js/`)

Moduł zawiera kilka plików JavaScript do zarządzania swoją funkcjonalnością:

- `socialslider/jscolor/jscolor.js`
  - **Zakres:** Back office (używany w `getContent()` do wprowadzania selektora kolorów).
  - **Odpowiedzialność:** Zapewnia funkcjonalność selektora kolorów JavaScript dla pól wejściowych, w szczególności dla ustawienia koloru obramowania Facebooka.
- `socialslider/left.js`
  - **Zakres:** Front office.
  - **Odpowiedzialność:** Zawiera logikę JavaScript dla animacji przesuwania i interakcji z zakładkami, gdy suwak jest umieszczony po **lewej** stronie ekranu. Obsługuje otwieranie/zamykanie zakładek, dynamiczne ładowanie treści mediów społecznościowych i potencjalnie zarządzanie plikami cookie dla funkcji „ostatnia otwarta zakładka”.
- `socialslider/right.js`
  - **Zakres:** Front office.
  - **Odpowiedzialność:** Zawiera logikę JavaScript dla animacji przesuwania i interakcji z zakładkami, gdy suwak jest umieszczony po **prawej** stronie ekranu. Podobnie jak `left.js`, ale dostosowany do pozycjonowania po prawej stronie.

### 4.5 Arkusze stylów CSS (`views/css/`)

Moduł wykorzystuje podejście oparte na szablonach do swojej stylizacji, z oddzielnymi plikami CSS dla każdego szablonu i pozycji.

- `socialslider/templates/1/css/left.css`
  - **Zakres:** Front office (dla Szablonu 1, pozycja Lewa).
  - **Odpowiedzialność:** Definiuje style wizualne dla zakładek społecznościowych, ikon i kontenera suwaka, gdy wybrany jest Szablon 1, a suwak znajduje się po lewej stronie.
  - **Kluczowe selektory:** `.socialslider_left`, `.socialslider_tab`, `.socialslider_tab_icon`, `.socialslider_content`.
- `socialslider/templates/1/css/right.css`
  - **Zakres:** Front office (dla Szablonu 1, pozycja Prawa).
  - **Odpowiedzialność:** Definiuje style wizualne dla zakładek społecznościowych, ikon i kontenera suwaka, gdy wybrany jest Szablon 1, a suwak znajduje się po prawej stronie.
  - **Kluczowe selektory:** `.socialslider_right`, `.socialslider_tab`, `.socialslider_tab_icon`, `.socialslider_content`.
- `socialslider/templates/2/css/left.css`
  - **Zakres:** Front office (dla Szablonu 2, pozycja Lewa).
  - **Odpowiedzialność:** Stylizacja dla Szablonu 2, pozycja Lewa.
- `socialslider/templates/2/css/right.css`
  - **Zakres:** Front office (dla Szablonu 2, pozycja Prawa).
  - **Odpowiedzialność:** Stylizacja dla Szablonu 2, pozycja Prawa.
- `socialslider/templates/3/css/left.css`
  - **Zakres:** Front office (dla Szablonu 3, pozycja Lewa).
  - **Odpowiedzialność:** Stylizacja dla Szablonu 3, pozycja Lewa.
- `socialslider/templates/3/css/right.css`
  - **Zakres:** Front office (dla Szablonu 3, pozycja Prawa).
  - **Odpowiedzialność:** Stylizacja dla Szablonu 3, pozycja Prawa.
- `socialslider/templates/4/css/left.css`
  - **Zakres:** Front office (dla Szablonu 4, pozycja Lewa).
  - **Odpowiedzialność:** Stylizacja dla Szablonu 4, pozycja Lewa.
- `socialslider/templates/4/css/right.css`
  - **Zakres:** Front office (dla Szablonu 4, pozycja Prawa).
  - **Odpowiedzialność:** Stylizacja dla Szablonu 4, pozycja Prawa.
- `socialslider/templates/5/css/left.css`
  - **Zakres:** Front office (dla Szablonu 5, pozycja Lewa).
  - **Odpowiedzialność:** Stylizacja dla Szablonu 5, pozycja Lewa.
- `socialslider/templates/5/css/right.css`
  - **Zakres:** Front office (dla Szablonu 5, pozycja Prawa).
  - **Odpowiedzialność:** Stylizacja dla Szablonu 5, pozycja Prawa.
- `socialslider/templates/6/css/left.css`
  - **Zakres:** Front office (dla Szablonu 6, pozycja Lewa).
  - **Odpowiedzialność:** Stylizacja dla Szablonu 6, pozycja Lewa.
- `socialslider/templates/6/css/right.css`
  - **Zakres:** Front office (dla Szablonu 6, pozycja Prawa).
  - **Odpowiedzialność:** Stylizacja dla Szablonu 6, pozycja Prawa.

Programiści mogą nadpisywać te style w pliku `custom.css` swojego motywu lub tworząc motyw potomny.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa szablonów Smarty do renderowania treści front office i formularza konfiguracji back office.

- **Szablony hooków (`views/templates/hook/`)**:
  - `socialslider/header.tpl`
    - **Hook:** `displayHeader`
    - **Wyjście:** Ten szablon jest odpowiedzialny za dynamiczne dołączanie niezbędnych plików CSS i JavaScript w oparciu o konfigurację modułu (np. ładowanie `left.js` lub `right.js` oraz prawidłowego CSS specyficznego dla szablonu). Dołącza również SDK/widżety Facebooka, Twittera i Google+, jeśli są włączone.
  - `socialslider/top.tpl`
    - **Hook:** `displayTop`
    - **Wyjście:** To jest główny szablon, który renderuje strukturę HTML samego suwaka zakładek społecznościowych. Generuje elementy `div` dla kontenera suwaka, poszczególnych zakładek (Facebook, Google+, Twitter, YouTube) i ich odpowiednich obszarów treści, wypełniając je wartościami konfiguracyjnymi.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  Moduł nie tworzy żadnych niestandardowych tabel SQL. Wszystkie ustawienia konfiguracyjne są przechowywane w standardowej tabeli PrestaShop `ps_configuration`.

  - `ps_configuration` (lub `_configuration` z Twoim prefiksem): Przechowuje pary klucz-wartość dla ustawień modułu, np. `SS_TEMPLATE`, `SS_POSITION`, `SS_FCB_FANPAGEURL`.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front office. | Wstrzykuje pliki CSS i JavaScript modułu oraz skrypty SDK/widżetów platform mediów społecznościowych (SDK Facebooka, skrypt widżetu Twittera, skrypt Google+). |
| `displayTop` | Zazwyczaj na samym szczycie obszaru treści, poniżej głównego nagłówka. | Renderuje główną strukturę HTML suwaka zakładek społecznościowych (stały kontener, poszczególne zakładki i ich obszary treści). |
| `header` | (Alias dla `displayHeader` w niektórych wersjach PrestaShop lub używany dla starszych motywów) | To samo co `displayHeader`, zapewnia kompatybilność dla wstrzykiwania zasobów. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, poprawek błędów i wsparcia deweloperskiego dla modułu „Social tabs slider” prosimy o zapoznanie się z kontem klienta MyPresta.eu. Najnowsze wersje i zasoby wsparcia można pobrać bezpośrednio z historii zamówień.
