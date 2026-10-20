---
title: "Kursy walut Europejskiego Banku Centralnego - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Kursy walut Europejskiego Banku Centralnego” od MyPresta.eu."
sidebar:
  label: "Kursy walut Europejskiego Banku Centralnego - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł European Central Bank currency rates na MyPresta.eu](https://mypresta.eu/modules/administration-tools/european-central-bank-currency-rates.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/european-central-bank-currency-rates/)
>
> ---


# Kursy walut Europejskiego Banku Centralnego

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do pobierania danych zewnętrznych, które są niemal powszechnie dostępne w nowoczesnych środowiskach hostingowych.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj”, aby uzyskać dostęp do głównych ustawień modułu. To tutaj kontrolujesz, jak i kiedy aktualizowane są kursy walut.

Ekran konfiguracji zazwyczaj przedstawia formularz z opcjami włączania/wyłączania funkcjonalności modułu oraz potencjalnie sposób ręcznego wywołania aktualizacji lub ustawienia zadania cron.

**Adres URL zadania cron:**

- **Co robi to ustawienie:** Wyświetla unikalny adres URL, który po wywołaniu powoduje, że moduł pobiera najnowsze kursy walut z Europejskiego Banku Centralnego i aktualizuje je w Twoim sklepie PrestaShop. Jest to podstawowy mechanizm automatycznych aktualizacji.
- **Wpływ zmiany tego ustawienia:** Jest to adres URL tylko do odczytu, generowany przez moduł. Nie zmieniasz go bezpośrednio.
  - *Gdy używany w zadaniu cron:* Twoje kursy walut będą automatycznie aktualizowane w regularnych odstępach czasu bez żadnej ręcznej interwencji.
  - *Gdy nie używany:* Kursy będą aktualizowane tylko, jeśli ręcznie klikniesz przycisk „Aktualizuj teraz” (jeśli dostępny) lub jeśli zostanie użyty domyślny, mniej niezawodny mechanizm aktualizacji walut PrestaShop.
- **Zalecana wartość:** Skopiuj ten adres URL i ustaw go jako zadanie cron na swoim serwerze hostingowym. Jest to najbardziej efektywny i niezawodny sposób na utrzymanie aktualnych kursów.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby kursy walut aktualizowały się codziennie o 3 rano. Kopiujesz ten adres URL i dodajesz go do harmonogramu zadań cron w panelu sterowania hostingu, ustawiając go na codzienne uruchamianie o 3 rano.

**Przycisk „Aktualizuj teraz” (jeśli obecny):**

- **Co robi to ustawienie:** Jest to ręczny wyzwalacz do natychmiastowego pobrania i aktualizacji wszystkich kursów walut z EBC.
- **Wpływ zmiany tego ustawienia:**
  - *Po kliknięciu:* Moduł natychmiast połączy się z EBC, pobierze najnowsze kursy wymiany i zastosuje je do walut Twojego sklepu. Jest to przydatne do natychmiastowych aktualizacji lub testowania.
- **Zalecana wartość:** Użyj tego do początkowego testowania konfiguracji lub jeśli potrzebujesz natychmiastowej aktualizacji poza zaplanowanymi zadaniami cron. Do regularnych aktualizacji polegaj na zadaniu cron.
- **Scenariusz / przykład dla sprzedawcy:** Właśnie zainstalowałeś moduł i chcesz upewnić się, że działa poprawnie. Klikasz „Aktualizuj teraz”, a następnie sprawdzasz kursy walut w PrestaShop, aby potwierdzić, że się zmieniły.

**Ogólna konfiguracja modułu (jeśli obecna, np. Włącz/Wyłącz):**

- **Co robi to ustawienie:** Jest to standardowy przełącznik modułu PrestaShop do aktywacji lub dezaktywacji podstawowej funkcjonalności modułu.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączony:* Moduł będzie aktywny, a jego adres URL zadania cron będzie działać, umożliwiając automatyczne aktualizacje walut.
  - *Gdy wyłączony:* Moduł nie będzie wykonywał żadnych aktualizacji, a adres URL zadania cron nie będzie działać. Kursy walut nie będą aktualizowane przez ten moduł.
- **Zalecana wartość:** **TAK** (Włączony), aby zapewnić automatyczną aktualizację kursów walut.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby moduł zarządzał kursami walut, więc upewniasz się, że jest włączony. Jeśli z jakiegoś powodu chciałbyś tymczasowo zatrzymać automatyczne aktualizacje, wyłączyłbyś go.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Ten moduł nie wprowadza żadnych dedykowanych nowych ekranów administracyjnych ani niestandardowych kontrolerów poza swoją główną stroną konfiguracji. Wszystkie interakcje odbywają się bezpośrednio w formularzu konfiguracji modułu.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Adres URL zadania cron | Skopiuj i ustaw na hostingu | Wyzwala automatyczne aktualizacje kursów walut z EBC. Niezbędne do bezobsługowej pracy. |
| Strona konfiguracji modułu | Przycisk „Aktualizuj teraz” | Użyj do testowania/ręcznej aktualizacji | Natychmiast pobiera i stosuje najnowsze kursy EBC. |
| Strona konfiguracji modułu | Moduł włączony/wyłączony | Włączony (TAK) | Aktywuje lub dezaktywuje funkcjonalność aktualizacji walut modułu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje kursy walut nie aktualizują się automatycznie. Co powinienem sprawdzić?**
O:

1. **Konfiguracja zadania Cron:** Najczęstszym problemem jest nieprawidłowo skonfigurowane zadanie cron. Dokładnie sprawdź adres URL, którego użyłeś w panelu hostingowym, i upewnij się, że harmonogram jest aktywny i poprawny.
2. **Moduł włączony:** Upewnij się, że moduł „Kursy walut Europejskiego Banku Centralnego” jest włączony w Panelu administracyjnym PrestaShop (**Moduły > Menedżer modułów**).
3. **Wersja PHP:** Upewnij się, że Twoja wersja PHP mieści się w zakresie kompatybilności modułu (PHP 5.6 - 8.5).
4. **Logi serwera:** Sprawdź logi zadań cron na swoim serwerze (jeśli Twój host je udostępnia) pod kątem błędów, gdy zadanie cron próbuje się uruchomić.
5. **Ręczna aktualizacja:** Spróbuj kliknąć przycisk „Aktualizuj teraz” na stronie konfiguracji modułu. Jeśli to zadziała, problem na pewno leży w konfiguracji zadania cron.

**P: Kursy zostały zaktualizowane, ale wydają się nieprawidłowe lub inne niż się spodziewałem.**
O:

1. **Źródło EBC:** Ten moduł pobiera kursy bezpośrednio z Europejskiego Banku Centralnego. Są to oficjalne kursy międzybankowe, które mogą nieznacznie różnić się od kursów konsumenckich, które widzisz w Google lub na innych stronach finansowych, z powodu opłat bankowych, spreadów lub różnych czasów aktualizacji.
2. **Waluta bazowa:** Upewnij się, że domyślna waluta Twojego PrestaShop jest poprawnie skonfigurowana. Moduł aktualizuje kursy względem waluty bazowej.
3. **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**) po aktualizacji, aby upewnić się, że widzisz najświeższe dane.

**P: Czy ten moduł działa z niestandardowymi motywami?**
O: Tak, absolutnie. Ten moduł działa w tle, aby aktualizować dane (kursy walut) w Twojej bazie danych. Nie wyświetla żadnych elementów wizualnych ani nie modyfikuje wyglądu Twojego motywu, więc jest w pełni kompatybilny z każdym motywem PrestaShop.

**P: Jak często powinienem aktualizować kursy walut?**
O: Dla większości sklepów e-commerce wystarczy codzienna aktualizacja. Jeśli zajmujesz się przedmiotami o wysokiej wartości lub działasz na bardzo zmiennych rynkach, możesz rozważyć aktualizację dwa razy dziennie. EBC zazwyczaj publikuje swoje referencyjne kursy raz dziennie, około godziny 16:00 CET.

**P: Widzę „Błąd serwera wewnętrznego 500” podczas próby bezpośredniego dostępu do adresu URL zadania cron.**
O: Zazwyczaj wskazuje to na błąd PHP. Sprawdź logi błędów PHP na swoim serwerze, aby uzyskać bardziej szczegółowe informacje. Częste przyczyny to nieprawidłowe uprawnienia do plików, brakujące rozszerzenie PHP lub konflikt z innym modułem. Skontaktuj się ze swoim dostawcą hostingu lub programistą, podając szczegóły z logów błędów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł „Kursy walut Europejskiego Banku Centralnego” (`ecbrates`) to lekki moduł PrestaShop, zaprojektowany przede wszystkim do automatyzacji aktualizacji kursów wymiany `ps_currency`. Przyjmuje prosty wzorzec projektowy:

- Pojedynczy główny plik modułu (`cronjob.php`) obsługuje instalację, deinstalację i podstawową logikę pobierania i aktualizacji kursów walut.
- Moduł udostępnia metodę `getContent()` dla swojej konfiguracji w Panelu administracyjnym, która renderuje podstawowy szablon.
- Podstawowa funkcjonalność jest wyzwalana poprzez bezpośrednie wywołanie pliku `cronjob.php` modułu, zazwyczaj przez zadanie cron po stronie serwera, omijając standardowe routowanie kontrolerów front/admin PrestaShop dla efektywności.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje standardowych kontrolerów Front-Office ani Back-Office Admin PrestaShop. Jego podstawowa logika aktualizacji jest bezpośrednio dostępna za pośrednictwem pliku `cronjob.php`, który działa jako samodzielny skrypt po wywołaniu przez adres URL cron.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Cała logika zawarta jest w głównym pliku `ecbrates/cronjob.php`. Bezpośrednio współdziała z podstawową klasą `Currency` i klasą `Configuration` PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony administracyjne (`views/templates/admin/`)**:
  - `ecbrates/views/admin.tpl`: Ten szablon jest renderowany przez metodę `getContent()` głównego pliku modułu. Wyświetla formularz konfiguracji modułu, w tym adres URL zadania cron i potencjalnie przycisk ręcznej aktualizacji. Jest to prosty szablon dla ustawień modułu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych.
  - Współdziała ze standardową tabelą `ps_currency` PrestaShop, aby zaktualizować kolumnę `conversion_rate` dla aktywnych walut.
  - Przechowuje swoją konfigurację (np. status włączenia modułu) w tabeli `ps_configuration`, używając kluczy takich jak `ECBRATES_LAST_UPDATE` lub podobnych, chociaż konkretne klucze nie są wyraźnie wyszczególnione w dostarczonych informacjach.
- **Tabela zarejestrowanych hooków**:
  Ten moduł nie rejestruje się jawnie do żadnych standardowych hooków PrestaShop w tradycyjnym sensie (np. `displayHeader`, `actionValidateOrder`) dla swojej podstawowej funkcjonalności. Jego głównym mechanizmem jest bezpośrednie wywołanie pliku `cronjob.php`.

  Jednak jako moduł PrestaShop, pośrednio używa:

  | Nazwa hooka | Czas wykonania | Cel techniczny |
  | --- | --- | --- |
  | `install()` | Podczas instalacji modułu | Tworzy wpisy konfiguracyjne, potencjalnie ustawia początkowe kursy. |
  | `uninstall()` | Podczas deinstalacji modułu | Czyści wpisy konfiguracyjne. |
  | `getContent()` | Podczas dostępu do konfiguracji modułu w BO | Renderuje formularz konfiguracji modułu. |

  Podstawowa funkcjonalność modułu (pobieranie i aktualizacja kursów) jest wyzwalana przez bezpośredni dostęp HTTP do `cronjob.php`, a nie przez hook PrestaShop.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dalszej pomocy z modułem „Kursy walut Europejskiego Banku Centralnego” prosimy o zapoznanie się z kontem klienta na [MyPresta.eu](https://mypresta.eu/). Najnowsze wersje modułu można pobrać z historii zamówień. W celu uzyskania wsparcia prosimy o korzystanie z dedykowanych kanałów wsparcia dostępnych na stronie MyPresta.eu.
