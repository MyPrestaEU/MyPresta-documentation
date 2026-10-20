---
title: "Wyłączanie cen specyficznych dla wybranych grup - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów dla modułu PrestaShop „Wyłączanie cen specyficznych dla wybranych grup” od MyPresta.eu."
sidebar:
  label: "Wyłączanie cen specyficznych dla wybranych grup - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Disable specific prices for selected groups na MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-specific-prices-for-selected-groups.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/disable-specific-prices-for-selected-groups/)
>
> ---


# Wyłączanie cen specyficznych dla wybranych grup

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu „Wyłączanie cen specyficznych dla wybranych grup”. Znajdziesz go, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Wyłączanie cen specyficznych dla wybranych grup” i klikając „Konfiguruj”.

#### **1. Wyłącz rabaty cen specyficznych dla wybranych grup**

To jest kluczowe ustawienie modułu. Określa, które grupy klientów *nie* otrzymają rabatów cen specyficznych.

- **Co robi to ustawienie:** Ta sekcja przedstawia listę wszystkich grup klientów zdefiniowanych w Twoim sklepie PrestaShop. Możesz wybrać jedną lub więcej grup z tej listy.
- **Efekt zmiany tego ustawienia:**
  - *Gdy wybrano jedną lub więcej grup:* Klienci należący do którejkolwiek z wybranych grup *nie* zobaczą ani nie skorzystają z żadnych rabatów cen specyficznych skonfigurowanych dla produktów. Zawsze zobaczą i zapłacą standardową cenę produktu.
  - *Gdy nie wybrano żadnych grup:* Moduł nie wyłączy cen specyficznych dla żadnej grupy. Wszyscy klienci otrzymają rabaty cen specyficznych zgodnie z konfiguracją w ustawieniach produktu.
- **Zalecana wartość:** Wybierz konkretne grupy klientów, dla których chcesz wyłączyć rabaty cen specyficznych. Na przykład, jeśli masz grupę „Hurtownia”, która ma zawsze płacić standardową cenę, wybierz tę grupę.
- **Scenariusz / przykład sprzedawcy:** Masz grupę klientów „Gość” i grupę „Nowi Klienci”. Chcesz zarezerwować rabaty cen specyficznych (takie jak ceny hurtowe lub tymczasowe promocje) tylko dla grupy „Lojalni Klienci”. Wybierając tutaj „Gość” i „Nowi Klienci”, te dwie grupy zawsze zobaczą regularną cenę, podczas gdy „Lojalni Klienci” nadal będą korzystać z wszelkich ustawionych cen specyficznych.

#### **2. Włączony**

To jest globalny przełącznik włącz/wyłącz dla funkcjonalności modułu.

- **Co robi to ustawienie:** Jest to prosty przełącznik do aktywacji lub dezaktywacji podstawowej logiki modułu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączony (TAK):* Moduł będzie aktywnie wyłączał ceny specyficzne dla grup wybranych w sekcji „Wyłącz rabaty cen specyficznych dla wybranych grup”.
  - *Gdy wyłączony (NIE):* Moduł będzie nieaktywny. Wszystkie ceny specyficzne będą działać zgodnie ze standardowym zachowaniem PrestaShop, niezależnie od grup wybranych w powyższej sekcji. Skutecznie wyłącza to wpływ modułu bez jego odinstalowywania.
- **Zalecana wartość:** **TAK**, jeśli zamierzasz korzystać z funkcjonalności modułu. **NIE**, jeśli chcesz tymczasowo go wyłączyć bez utraty wybranych grup.
- **Scenariusz / przykład sprzedawcy:** Skonfigurowałeś moduł tak, aby wyłączał ceny specyficzne dla Twojej grupy klientów „Detal”. Jeśli chcesz przeprowadzić tymczasową promocję, w której *wszystkie* grupy, w tym „Detal”, powinny otrzymywać rabaty cen specyficznych, możesz po prostu ustawić „Włączony” na **NIE**. Po zakończeniu promocji, przełącz go z powrotem na **TAK**, aby ponownie włączyć wyłączanie cen specyficznych dla klientów „Detal”.

#### **3. Zawsze zwracaj najniższą cenę**

To ustawienie oferuje dodatkową warstwę kontroli, zwłaszcza gdy ceny specyficzne mogą wchodzić w interakcje z innymi zasadami cenowymi.

- **Co robi to ustawienie:** Ten przełącznik określa, czy moduł powinien ściśle egzekwować standardową cenę dla wybranych grup, czy też powinien nadal brać pod uwagę *najniższą możliwą cenę* (która może obejmować inne rodzaje rabatów niezarządzanych przez ceny specyficzne), jeśli okaże się ona niższa niż cena standardowa.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączony (TAK):* Dla wybranych grup ceny specyficzne zostaną zignorowane. Jednakże, jeśli istnieje *inny* mechanizm (np. reguła koszyka, globalny rabat lub inny rodzaj obniżki ceny), który skutkuje ceną niższą niż cena standardowa, moduł pozwoli na zastosowanie tej najniższej ceny. Zapewnia to, że klienci zawsze otrzymują absolutnie najniższą dostępną cenę *poza* cenami specyficznymi.
  - *Gdy wyłączony (NIE):* Dla wybranych grup ceny specyficzne zostaną zignorowane, a moduł będzie ściśle egzekwował *standardową cenę produktu*. Żadne inne potencjalne niższe ceny (chyba że są częścią samej ceny podstawowej) nie będą brane pod uwagę. Zapewnia to najbardziej rygorystyczną kontrolę nad cenami dla wybranych grup.
- **Zalecana wartość:** **NIE** dla ścisłej kontroli, zapewniając, że wybrane grupy zawsze płacą standardową cenę. **TAK**, jeśli chcesz wyłączyć ceny specyficzne, ale nadal zezwolić na stosowanie innych rabatów niezwiązanych z cenami specyficznymi, jeśli skutkują one niższą ceną.
- **Scenariusz / przykład sprzedawcy:**
  - *Scenariusz 1 (Zalecane: NIE):* Chcesz, aby Twoja grupa „Hurtownia” *zawsze* płaciła pełną, standardową cenę i nigdy nie korzystała z żadnych rabatów cen specyficznych ani innych potencjalnych obniżek cen. Ustawisz to na **NIE**.
  - *Scenariusz 2 (Zalecane: TAK):* Chcesz wyłączyć ceny specyficzne dla grupy „Gość”, ale masz również ogólną regułę koszyka „5% zniżki na wszystkie produkty”, która dotyczy wszystkich. Jeśli ustawisz „Zawsze zwracaj najniższą cenę” na **TAK**, goście nie otrzymają rabatów cen specyficznych, ale *nadal* otrzymają 5% rabatu z reguły koszyka, jeśli obniży to cenę poniżej ceny standardowej. Jeśli ustawisz na **NIE**, zapłacą pełną cenę standardową, ignorując nawet 5% rabatu z reguły koszyka.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyłącz rabaty cen specyficznych dla wybranych grup | Wybierz grupy według potrzeb | Wybierz grupy klientów, dla których rabaty cen specyficznych zostaną zignorowane. |
| Konfiguracja modułu | Włączony | TAK | Globalny przełącznik WŁ./WYŁ. dla funkcjonalności modułu. |
| Konfiguracja modułu | Zawsze zwracaj najniższą cenę | NIE (dla ścisłej kontroli) / TAK (dla elastyczności) | Określa, czy inne rabaty niezwiązane z cenami specyficznymi mogą nadal obowiązywać, jeśli skutkują niższą ceną dla dotkniętych grup. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem moduł, ale klienci w wybranej grupie nadal widzą ceny specyficzne. Co jest nie tak?**
O:

1. **Sprawdź ustawienie „Włączony”:** Upewnij się, że przełącznik „Włączony” w konfiguracji modułu jest ustawiony na **TAK**.
2. **Zweryfikuj wybór grupy:** Dokładnie sprawdź, czy prawidłowe grupy klientów są wybrane w sekcji „Wyłącz rabaty cen specyficznych dla wybranych grup”.
3. **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. PrestaShop często buforuje informacje o cenach.
4. **Sprawdź grupę klienta:** Upewnij się, że klient, którego testujesz, jest faktycznie przypisany do grupy wybranej w module. Możesz to sprawdzić w **Klienci > Klienci** w Panelu administracyjnym.
5. **Kompatybilność z motywem:** Chociaż rzadko, niektóre mocno dostosowane motywy mogą powodować zakłócenia. Jeśli problem nadal występuje, spróbuj tymczasowo przełączyć się na domyślny motyw PrestaShop, aby wykluczyć konflikty motywu.

**P: Co się stanie, jeśli klient należy do wielu grup, a jedna grupa jest wybrana do wyłączenia cen specyficznych, a inna nie?**
O: Podstawowa logika PrestaShop zazwyczaj priorytetyzuje najniższą cenę. Nadpisanie tego modułu będzie próbowało usunąć ceny specyficzne dla *każdej* wybranej grupy. Jeśli klient należy do grupy, która *powinna* mieć wyłączone ceny specyficzne, moduł spróbuje wymusić standardową cenę. Ustawienie „Zawsze zwracaj najniższą cenę” określi wtedy, czy inne rabaty niezwiązane z cenami specyficznymi są nadal brane pod uwagę.

**P: Czy ten moduł wpływa na inne rodzaje rabatów, takie jak reguły koszyka lub reguły cen katalogowych?**
O: Ten moduł dotyczy konkretnie „cen specyficznych” zdefiniowanych w PrestaShop (rabaty ustawione bezpośrednio na stronach produktów lub poprzez import CSV).

- Jeśli „Zawsze zwracaj najniższą cenę” jest ustawione na **NIE**, moduł będzie ściśle egzekwował standardową cenę dla wybranych grup, potencjalnie nadpisując inne rabaty, jeśli skutkują one niższą ceną niż cena standardowa.
- Jeśli „Zawsze zwracaj najniższą cenę” jest ustawione na **TAK**, moduł wyłączy ceny specyficzne, ale nadal pozwoli na stosowanie innych rodzajów rabatów (takich jak reguły koszyka lub reguły cen katalogowych), jeśli skutkują one niższą ceną niż cena standardowa.

**P: Chcę tymczasowo wyłączyć moduł bez utraty moich ustawień. Jak to zrobić?**
O: Po prostu przejdź do strony konfiguracji modułu i ustaw przełącznik „Włączony” na **NIE**. Wszystkie wybrane grupy i inne ustawienia zostaną zachowane, a możesz je ponownie włączyć w dowolnym momencie, przełączając go z powrotem na **TAK**.

**P: Jak przetłumaczyć tekst modułu na inne języki?**
O: Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop. Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz „Wyłączanie cen specyficznych dla wybranych grup”. Możesz wtedy przetłumaczyć dowolne widoczne ciągi tekstowe.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla deweloperów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Wyłączanie cen specyficznych dla wybranych grup” działa głównie poprzez nadpisywanie podstawowych klas PrestaShop związanych z cenami produktów, w szczególności `Product.php` i `SpecificPrice.php`. Pozwala to na przechwytywanie i modyfikowanie logiki, która określa, czy ceny specyficzne są stosowane do produktu, w oparciu o grupę bieżącego klienta i konfigurację modułu. Moduł ma standardową strukturę modułu PrestaShop z głównym plikiem modułu i nadpisaniami klas.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównej klasy modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Podstawowa funkcjonalność modułu jest zaimplementowana poprzez nadpisania klas.

- **`exsdis/override/classes/index.php`**:

  - Jest to standardowy pusty plik `index.php`, zazwyczaj umieszczany w katalogach w celu zapobiegania listowaniu katalogów. Nie ma on żadnego wpływu funkcjonalnego na logikę modułu.
- **`exsdis/override/classes/Product.php`**:

  - **Oryginalna klasa**: `classes/Product.php`
  - **Cel**: To nadpisanie modyfikuje klasę `Product`, która jest centralna dla sposobu pobierania i obliczania informacji o produkcie, w tym cen, w PrestaShop. Logika modułu w tym nadpisaniu przechwytuje wywołania w celu pobrania cen specyficznych dla produktu.
  - **Kluczowa logika**: Sprawdza, czy moduł jest włączony i czy grupa bieżącego klienta jest wśród tych wybranych do wyłączenia cen specyficznych. Jeśli tak, manipuluje procesem pobierania cen specyficznych, aby upewnić się, że żadne ceny specyficzne nie są zwracane dla tego klienta. Bierze również pod uwagę konfigurację `exsdis_lowest`, aby określić, czy absolutnie najniższa cena (z wyłączeniem cen specyficznych) powinna być nadal zwracana.
- **`exsdis/override/classes/SpecificPrice.php`**:

  - **Oryginalna klasa**: `classes/SpecificPrice.php`
  - **Cel**: To nadpisanie dotyczy klasy `SpecificPrice`, która jest odpowiedzialna za zarządzanie i stosowanie reguł cen specyficznych.
  - **Kluczowa logika**: Prawdopodobnie modyfikuje metody w tej klasie (np. `getSpecificPrice()`, `getSpecificPrices()`), aby zapobiec tworzeniu lub zwracaniu obiektów cen specyficznych dla klientów w wyznaczonych grupach. Działa to w połączeniu z nadpisaniem `Product.php`, aby zapewnić skuteczne ignorowanie cen specyficznych.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie zawiera żadnych niestandardowych plików szablonów Smarty. Formularz konfiguracji jest renderowany dynamicznie przez metodę `getContent()` w `exsdis.php`.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoje ustawienia konfiguracyjne w standardowej tabeli `ps_configuration`.

  - Wpisy `ps_configuration`:
    - `exsdis_`: (Prefiks dla ogólnych ustawień modułu)
    - `exsdis_groups`: Przechowuje serializowaną tablicę lub ciąg identyfikatorów grup klientów oddzielonych przecinkami, dla których ceny specyficzne są wyłączone.
    - `exsdis_lowest`: Przechowuje wartość (0 lub 1) dla ustawienia „Zawsze zwracaj najniższą cenę”.
    - `mypresta_updates`, `update_`, `updatev_`: Związane z kontrolą aktualizacji MyPresta.eu.
- **Tabela zarejestrowanych hooków**:
  Moduł nie rejestruje jawnie żadnych standardowych hooków PrestaShop w swojej metodzie `install()`. Jego funkcjonalność jest osiągana głównie poprzez nadpisania klas, które modyfikują bezpośrednio podstawowe zachowanie PrestaShop, zamiast reagować na zdarzenia hooków.
  Opis modułu wspomina o „Hookach Front-Office: Nagłówek, Kolumny, Produkt lub Stopka”, ale jest to prawdopodobnie ogólne stwierdzenie dotyczące miejsca, w którym *ceny* mogą być wyświetlane, a nie miejsca, w którym sam moduł wstrzykuje zawartość za pośrednictwem hooków. Nadpisania obsługują logikę cenową na niższym poziomie.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Wyłączanie cen specyficznych dla wybranych grup”, zapoznaj się ze swoim kontem klienta MyPresta.eu. Możesz pobrać najnowsze wersje z historii zamówień i uzyskać dostęp do dedykowanych kanałów wsparcia zapewnianych przez MyPresta.eu.
