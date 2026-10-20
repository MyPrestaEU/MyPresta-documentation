---
title: "Zopim Chat Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop Zopim Chat Free od MyPresta.eu."
sidebar:
  label: "Zopim Chat Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Zopim Chat Free na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/zopim-chat-free.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/zopim-chat-free/)
>
> ---


# Zopim Chat Free

## 1. Wymagania i Kompatybilność

- **Obsługiwane Wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania Hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i wszelkich zewnętrznych integracji API, w tym Zendesk Chat.

## 2. Kompletny Przewodnik Konfiguracji (Każde Ustawienie Pogrupowane Według Ekranu)

### 2.1 Strona Konfiguracji Modułu (Panel Administracyjny > Moduły > Konfiguruj > Zopim Chat Free)

Jest to główny i jedyny ekran konfiguracji modułu Zopim Chat Free. Tutaj wprowadzisz swój klucz konta Zendesk Chat (Zopim) i zdecydujesz, gdzie skrypt widżetu czatu powinien być ładowany w Twoim sklepie.

#### **Klucz Konta Zopim**

- **Co robi to ustawienie:** Jest to najważniejsze ustawienie. Tutaj wprowadzasz unikalny identyfikator dostarczony przez Zendesk Chat (Zopim) dla Twojego widżetu czatu na żywo. Ten klucz informuje moduł, który widżet czatu ma załadować na Twojej stronie internetowej. Klucz ten znajdziesz w swoim panelu Zendesk Chat (zazwyczaj w Ustawieniach > Widżet > Kod do osadzenia).
- **Efekt zmiany tego ustawienia:**
  - *Po wprowadzeniu prawidłowego klucza:* Widżet czatu Zopim powiązany z Twoim kontem Zendesk Chat pojawi się w front-office Twojego sklepu, umożliwiając klientom inicjowanie czatów.
  - *Po pozostawieniu pustego lub wprowadzeniu nieprawidłowego klucza:* Widżet czatu Zopim nie pojawi się w Twoim sklepie, a funkcja czatu na żywo będzie niedostępna.
- **Zalecana wartość:** Twój unikalny klucz konta Zendesk Chat (Zopim).
- **Scenariusz / przykład dla sprzedawcy:** Po zarejestrowaniu się w Zendesk Chat otrzymasz fragment kodu. W tym kodzie znajdziesz konkretny ciąg znaków (np. `zopim.setAndDefer('account', 'YOUR_ACCOUNT_KEY');`). Skopiuj `YOUR_ACCOUNT_KEY` i wklej go tutaj.

#### **Załaduj Zopim Chat w Hooku**

- **Co robi to ustawienie:** Ta opcja określa, gdzie w kodzie Twojego sklepu PrestaShop zostanie wstrzyknięty skrypt czatu Zopim. Chociaż sam widżet czatu zazwyczaj unosi się na ekranie, umieszczenie skryptu może czasami wpływać na szybkość ładowania lub kompatybilność z konkretnymi motywami.
- **Efekt zmiany tego ustawienia:**
  - *Po ustawieniu na `displayHeader` (Nagłówek):* Skrypt czatu zostanie załadowany bardzo wcześnie, zazwyczaj przed większością treści strony. Może to sprawić, że widżet czatu pojawi się szybko.
  - *Po ustawieniu na `displayRightColumn` (Prawa Kolumna):* Skrypt zostanie załadowany wraz z zawartością prawej kolumny. Jest to mniej powszechne dla widżetów czatu i może nie być idealne, jeśli Twój motyw nie zawsze wyświetla prawą kolumnę.
  - *Po ustawieniu na `displayLeftColumn` (Lewa Kolumna):* Podobnie jak w przypadku prawej kolumny, skrypt ładuje się wraz z zawartością lewej kolumny.
  - *Po ustawieniu na `displayProductButtons` (Przyciski Strony Produktu):* Skrypt zostanie załadowany specjalnie na stronach produktów, w pobliżu obszaru przycisku „Dodaj do koszyka”. Może to być przydatne, jeśli głównie chcesz wsparcia czatu na stronach produktów.
  - *Po ustawieniu na `displayFooter` (Stopka):* Skrypt zostanie załadowany na samym końcu treści strony. Może to poprawić początkową szybkość ładowania strony postrzeganą przez użytkownika, ponieważ najpierw ładuje się główna treść, a następnie widżet czatu.
- **Zalecana wartość:** `displayHeader` lub `displayFooter`. Dla większości sklepów `displayHeader` zapewnia szybkie ładowanie czatu. Jeśli doświadczasz jakichkolwiek konfliktów lub chcesz priorytetyzować ładowanie treści, `displayFooter` jest dobrą alternatywą.
- **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoi klienci często zadają pytania *zanim* zaczną przeglądać produkty, załadowanie czatu w `displayHeader` zapewnia jego natychmiastową dostępność. Jeśli zauważysz, że Twoja strona ładuje się wolno i podejrzewasz skrypt czatu, przełączenie na `displayFooter` może pomóc, ponieważ czat załaduje się po głównej treści strony.

#### Tabela Szybkiego Odniesienia Konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i Wpływ |
| --- | --- | --- | --- |
| Strona Konfiguracji Modułu | Klucz Konta Zopim | Twój unikalny klucz Zendesk Chat | Łączy Twój sklep z kontem Zendesk Chat. Niezbędny do pojawienia się widżetu. |
| Strona Konfiguracji Modułu | Załaduj Zopim Chat w Hooku | `displayHeader` lub `displayFooter` | Określa, gdzie skrypt czatu jest wstrzykiwany (Nagłówek, Kolumny, Produkt, Stopka). Wpływa na kolejność ładowania i potencjalną kompatybilność z motywem. |

## 3. Rozwiązywanie Problemów dla Sprzedawców i Często Zadawane Pytania (FAQ)

**P1: Widżet czatu Zopim nie pojawia się w moim sklepie. Co powinienem zrobić?**
O1:

1. **Sprawdź swój Klucz Konta Zopim:** Przejdź do strony konfiguracji modułu i upewnij się, że Twój Klucz Konta Zopim jest poprawnie wprowadzony. Nawet pojedyncza literówka uniemożliwi jego załadowanie.
2. **Zweryfikuj Status Zendesk Chat:** Zaloguj się do swojego panelu Zendesk Chat. Czy Twój widżet jest aktywny? Czy Twoi agenci są online?
3. **Wyczyść Pamięć Podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stare pliki pamięci podręcznej uniemożliwiają pojawienie się nowych zmian modułu.
4. **Sprawdź Konflikty Motywu:** Tymczasowo przełącz się na domyślny motyw PrestaShop (np. Classic) i sprawdź, czy widżet się pojawi. Jeśli tak, Twój niestandardowy motyw może powodować konflikt. Skontaktuj się z deweloperem motywu lub webmasterem.
5. **Sprawdź Konsolę Przeglądarki:** Otwórz narzędzia deweloperskie przeglądarki (F12) i sprawdź zakładkę „Konsola” pod kątem błędów JavaScript. Może to dostarczyć wskazówek, jeśli skrypt nie ładuje się.

**P2: Widżet czatu ładuje się, ale wygląda dziwnie lub jest nieprawidłowo umieszczony.**
O2: Moduł wstrzykuje skrypt Zopim, ale wizualne stylizowanie i dokładne pozycjonowanie widżetu są w dużej mierze kontrolowane przez ustawienia Twojego konta Zendesk Chat i CSS Twojego sklepu.

1. **Panel Zendesk Chat:** Zaloguj się do swojego panelu Zendesk Chat i przejrzyj ustawienia wyglądu widżetu (np. pozycja, kolory, rozmiar).
2. **CSS Motywu:** CSS Twojego niestandardowego motywu może nadpisywać niektóre domyślne style Zopim. Webmaster może zbadać element za pomocą narzędzi deweloperskich przeglądarki i zidentyfikować sprzeczne reguły CSS.

**P3: Czy mogę przetłumaczyć tekst widżetu czatu na różne języki?**
O3: Sam moduł Zopim Chat Free nie obsługuje tłumaczeń interfejsu widżetu. Ta funkcjonalność jest zarządzana bezpośrednio w ustawieniach Twojego konta Zendesk Chat. Zendesk Chat obsługuje wiele języków i możesz skonfigurować widżet tak, aby wyświetlał się w preferowanym języku klienta na podstawie ustawień jego przeglądarki lub konfiguracji Zendesk Chat.

**P4: Czy ten moduł spowolni moją stronę internetową?**
O4: Moduł Zopim Chat Free wstrzykuje tylko niezbędny skrypt Zendesk Chat. Wpływ na wydajność zależy głównie od samej usługi Zendesk Chat i Twojego połączenia internetowego. Możesz spróbować ustawić opcję „Załaduj Zopim Chat w Hooku” na `displayFooter`, aby upewnić się, że główna treść Twojej strony ładuje się przed skryptem czatu, co może poprawić postrzeganą początkową szybkość ładowania strony.

## 4. Przewodnik dla Deweloperów i Webmasterów (Architektura Techniczna i Mapa Kodu)

Ta sekcja zawiera techniczny przegląd dla deweloperów i webmasterów pracujących z modułem Zopim Chat Free.

### 4.1 Przegląd Architektury

Moduł `ZopimFree` to prosty moduł PrestaShop zaprojektowany do integracji widżetu Zendesk Chat (dawniej Zopim). Działa głównie poprzez wstrzykiwanie skryptu osadzania Zendesk Chat do front-office sklepu PrestaShop. Moduł przestrzega standardowej struktury modułu PrestaShop, wykorzystując klasę `Module` do instalacji, deinstalacji i obsługi konfiguracji za pomocą `getContent()`. Rejestruje pojedynczy hook (`displayHeader` domyślnie, ale konfigurowalny) do wyprowadzania niezbędnego kodu JavaScript.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Moduł bezpośrednio wstrzykuje zawartość do hooków.
- **Kontrolery Administracyjne Back-Office**: Brak. Cała konfiguracja jest obsługiwana w głównej metodzie `getContent()` modułu.

### 4.3 Klasy Rdzeniowe i Modele (`classes/`)

- W tym module nie ma niestandardowych klas ani definicji `ObjectModel`. Cała logika znajduje się w głównym pliku `zopimfree.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

- W tym module nie ma niestandardowych plików JavaScript. Moduł wyprowadza skrypt osadzania Zendesk Chat bezpośrednio do szablonu, który następnie ładuje niezbędny JS z CDN Zendesk.

### 4.5 Arkusze Stylów CSS (`views/css/`)

- W tym module nie ma niestandardowych plików CSS. Stylizacja widżetu czatu jest obsługiwana przez samą usługę Zendesk Chat, z potencjalnymi nadpisaniami z aktywnego motywu PrestaShop.

### 4.6 Struktura Szablonów Smarty (`views/templates/`)

- **Szablony Hooków (`views/templates/hook/`)**:
  - `zopimfree/header-new-widget.tpl`
    - **Hook:** Ten szablon jest przeznaczony do renderowania w ramach hooka PrestaShop, konkretnie tego wybranego w konfiguracji modułu (np. `displayHeader`, `displayFooter`).
    - **Cel:** Zawiera tag `<script>` odpowiedzialny za osadzanie widżetu Zendesk Chat. Dynamicznie wstawia `ZOPIMFREE_ACCOUNT_KEY` z konfiguracji modułu do skryptu inicjalizacji Zendesk Chat.
    - **Wyjście:** Wyprowadza standardowy kod osadzania Zendesk Chat, który następnie ładuje widżet czatu z serwerów Zendesk.

### 4.7 Schemat Bazy Danych i Mapa Hooków

- **Tabele Bazy Danych**:

  - Moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration`:
    - `ZOPIMFREE_ACCOUNT_KEY`: Przechowuje klucz konta Zendesk Chat.
    - `ZOPIMFREE_HOOK`: Przechowuje nazwę hooka, w którym skrypt powinien zostać wstrzyknięty (np. `displayHeader`, `displayFooter`).
- **Tabela Zarejestrowanych Hooków**:

| Nazwa Hooka | Czas Wykonania | Cel Techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony. | Domyślny hook do wstrzykiwania skryptu Zendesk Chat wcześnie podczas ładowania strony. |
| `displayRightColumn` | Wykonywany w prawej kolumnie stron, na których jest aktywny. | Alternatywny hook do wstrzykiwania skryptu, mniej powszechny dla widżetów czatu. |
| `displayLeftColumn` | Wykonywany w lewej kolumnie stron, na których jest aktywny. | Alternatywny hook do wstrzykiwania skryptu, mniej powszechny dla widżetów czatu. |
| `displayProductButtons` | Wykonywany na stronach produktów, zazwyczaj w pobliżu przycisku dodawania do koszyka. | Specyficzny hook do wstrzykiwania skryptu czatu tylko na stronach produktów. |
| `displayFooter` | Wykonywany tuż przed zamykającym tagiem `</body>`. | Alternatywny hook do wstrzykiwania skryptu Zendesk Chat później podczas ładowania strony, potencjalnie poprawiający postrzeganą początkową szybkość strony. |

Moduł rejestruje te hooki dynamicznie na podstawie wartości konfiguracyjnej `ZOPIMFREE_HOOK`. Metoda `install()` rejestruje wszystkie potencjalne hooki, a `uninstall()` je wyrejestrowuje. Metoda `hook{HookName}` następnie sprawdza konfigurację, aby zdecydować, czy powinna renderować szablon.

## 5. Oficjalne Wsparcie i Aktualizacje

W celu uzyskania oficjalnych aktualizacji, poprawek błędów i wsparcia deweloperskiego dla modułu Zopim Chat Free, prosimy odnieść się do swojego konta klienta na [MyPresta.eu](https://mypresta.eu/). Upewnij się, że pobierasz najnowszą wersję kompatybilną z Twoją instalacją PrestaShop.
