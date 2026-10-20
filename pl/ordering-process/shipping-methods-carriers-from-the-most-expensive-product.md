---
title: "Metody wysyłki (przewoźnicy) z najdroższego produktu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Metody wysyłki (przewoźnicy) z najdroższego produktu” od MyPresta.eu."
sidebar:
  label: "Metody wysyłki (przewoźnicy) z najdroższego produktu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Shipping methods (carriers) from the most expensive product na MyPresta.eu](https://mypresta.eu/modules/ordering-process/shipping-methods-carriers-from-the-most-expensive-product.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/shipping-methods-carriers-from-the-most-expensive-product/)
>
> ---


# Metody wysyłki (przewoźnicy) z najdroższego produktu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu, aby uzyskać dostęp do jego ustawień.

#### **Włącz / Wyłącz moduł**

- **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji podstawowej funkcjonalności modułu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączony:* Moduł zmodyfikuje domyślną logikę wyboru przewoźnika w PrestaShop, zapewniając, że podczas realizacji zamówienia wyświetlane będą tylko przewoźnicy powiązani z najdroższym produktem w koszyku.
  - *Gdy wyłączony:* PrestaShop powróci do swojego domyślnego zachowania, gdzie przewoźnicy są wyświetlani tylko wtedy, gdy mogą wysłać *wszystkie* produkty w koszyku.
- **Zalecana wartość:** „Włączony”, jeśli chcesz korzystać z funkcjonalności modułu.
- **Scenariusz / przykład sprzedawcy:** Jeśli testujesz moduł lub tymczasowo chcesz wrócić do domyślnego zachowania PrestaShop bez odinstalowywania, możesz go tutaj wyłączyć.

#### **Jak uzyskać przewoźników?**

- **Co robi to ustawienie:** To kluczowe ustawienie definiuje, *jak* moduł identyfikuje „najdroższy produkt” i następnie określa dostępnych przewoźników. Oferuje dwie odrębne metody.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawione na „Z najdroższego produktu (według ceny)”:* Moduł obliczy całkowitą cenę każdego unikalnego produktu w koszyku (ilość * cena jednostkowa) i zidentyfikuje produkt z najwyższą całkowitą ceną. Przewoźnicy powiązani z *tym konkretnym produktem* zostaną następnie użyci do filtrowania dostępnych opcji wysyłki.
  - *Gdy ustawione na „Z najdroższego produktu (według ceny) - DARMOWA WYSYŁKA”:* Ta opcja działa podobnie do pierwszej, ale bierze również pod uwagę, czy najdroższy produkt kwalifikuje się do darmowej wysyłki. Jeśli najdroższy produkt ma włączoną darmową wysyłkę, wówczas opcje darmowej wysyłki zostaną priorytetowo potraktowane lub udostępnione zgodnie z Twoimi ustawieniami przewoźnika.
  - *Gdy ustawione na „Z najdroższego produktu (według ceny) - KOSZT”:* Ta opcja również identyfikuje najdroższy produkt według ceny, ale skupia się konkretnie na *koszcie* związanym z wysyłką tego produktu. Zapewnia, że prezentowane koszty wysyłki i opcje są bezpośrednio związane z konfiguracją wysyłki najdroższego przedmiotu.
- **Zalecana wartość:**
  - „Z najdroższego produktu (według ceny)” jest najczęstszym i zalecanym wyborem do ogólnego użytku, ponieważ bezpośrednio implementuje podstawową obietnicę modułu.
  - Wybierz „Z najdroższego produktu (według ceny) - DARMOWA WYSYŁKA”, jeśli często oferujesz darmową wysyłkę na przedmioty o wysokiej wartości i chcesz, aby było to głównym czynnikiem przy wyborze przewoźnika.
  - Wybierz „Z najdroższego produktu (według ceny) - KOSZT”, jeśli masz złożone zasady kosztów wysyłki powiązane z konkretnymi produktami o wysokiej wartości i chcesz, aby te zasady dyktowały dostępnych przewoźników.
- **Scenariusz / przykład sprzedawcy:**
  - Sprzedajesz telewizor za 1000 USD i pilota za 10 USD. Jeśli telewizor jest skonfigurowany z konkretnymi przewoźnikami (np. ubezpieczony fracht), a pilot ze standardową usługą pocztową, wybranie „Z najdroższego produktu (według ceny)” zapewni wyświetlenie przewoźników telewizora.
  - Jeśli Twój telewizor za 1000 USD jest objęty darmową wysyłką, wybranie „Z najdroższego produktu (według ceny) - DARMOWA WYSYŁKA” zapewniłoby, że opcje darmowej wysyłki zostaną przedstawione, jeśli są dostępne dla telewizora.

#### **Tabela szybkiego odniesienia konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Włącz / Wyłącz moduł | Włączony | Aktywuje/dezaktywuje logikę modułu dla wyboru przewoźnika na podstawie najdroższego produktu. |
| Strona konfiguracji modułu | Jak uzyskać przewoźników? | Z najdroższego produktu (według ceny) | Definiuje metodę identyfikacji „najdroższego produktu” i powiązanych z nim przewoźników. Opcje: „według ceny”, „według ceny - DARMOWA WYSYŁKA”, „według ceny - KOSZT”. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Włączyłem moduł, ale nadal widzę stare opcje przewoźników lub wcale ich nie widzę.**
O:

1.  **Wyczyść pamięć podręczną:** Zawsze wyczyść pamięć podręczną PrestaShop po wprowadzeniu zmian w konfiguracji modułu. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
2.  **Sprawdź powiązania przewoźników z produktami:** Upewnij się, że Twoje produkty, zwłaszcza te najdroższe, są poprawnie powiązane z pożądanymi przewoźnikami w ich ustawieniach produktu (**Katalog > Produkty > Edytuj produkt > zakładka Wysyłka**).
3.  **Sprawdź, czy moduł jest włączony:** Sprawdź dwukrotnie, czy ustawienie „Włącz / Wyłącz moduł” jest ustawione na „Włączony” w konfiguracji modułu.
4.  **Kompatybilność z motywem:** Chociaż rzadko zdarza się w przypadku tego typu modułu, wysoce spersonalizowany motyw może powodować zakłócenia. Tymczasowo przełącz się na domyślny motyw PrestaShop, aby to wykluczyć.

**P: Jak moduł radzi sobie z dwoma produktami o dokładnie tej samej najwyższej cenie?**
O: W przypadkach, gdy dwa lub więcej produktów ma dokładnie tę samą najwyższą cenę, moduł zazwyczaj wybierze jeden z nich na podstawie wewnętrznego porządku identyfikatorów produktów PrestaShop lub kolejności, w jakiej zostały dodane do koszyka. Następnie użyje przewoźników powiązanych z tym wybranym produktem. Dla spójności najlepiej jest upewnić się, że Twoje konfiguracje przewoźników są wystarczająco solidne, aby obejmować podobne przedmioty o wysokiej wartości.

**P: Czy ten moduł wpływa na koszty wysyłki, czy tylko na dostępność przewoźników?**
O: Ten moduł wpływa przede wszystkim na *dostępność przewoźników*. Określa, *którzy* przewoźnicy są wyświetlani. Rzeczywiste koszty wysyłki dla wybranego przewoźnika będą nadal obliczane przez standardowe mechanizmy PrestaShop (na podstawie wagi, ceny, strefy itp.) dla *całego koszyka*, ale tylko dla przewoźników, którzy zostaną udostępnieni przez logikę tego modułu.

**P: Co się stanie, jeśli najdroższy produkt nie ma z nim powiązanych żadnych przewoźników?**
O: Jeśli najdroższy produkt w koszyku nie ma z nim wyraźnie powiązanych żadnych przewoźników w jego ustawieniach produktu, wówczas podczas realizacji zamówienia nie zostaną wyświetleni żadni przewoźnicy, co potencjalnie doprowadzi do komunikatu „brak dostępnej metody wysyłki”. Zawsze upewnij się, że Twoje produkty o wysokiej wartości mają przypisanych odpowiednich przewoźników.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł „Metody wysyłki (przewoźnicy) z najdroższego produktu” osiąga swoją funkcjonalność poprzez nadpisanie podstawowej klasy PrestaShop, `Cart`. Jest to powszechna i potężna metoda w PrestaShop do zmiany fundamentalnych zachowań bez bezpośredniej modyfikacji plików rdzenia. Nadpisując `Cart::getAvailableCarriers()`, moduł wstrzykuje swoją niestandardową logikę do filtrowania przewoźników na podstawie najdroższego produktu, zamiast domyślnej zasady „wszystkie produkty muszą być kompatybilne”.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Moduł działa poprzez nadpisanie klasy rdzenia, a nie poprzez wprowadzanie nowych tras lub stron front-office.
- **Kontrolery Back-Office Admin**: Brak. Konfiguracja modułu jest obsługiwana bezpośrednio w metodzie `getContent()` głównej klasy modułu.

### 4.3 Klasy rdzenia i modele (`classes/`)

Główna logika modułu znajduje się w nadpisaniu klasy `Cart`.

- **`cfep/override/classes/Cart.php`**

  - **Nazwa klasy**: `Cart` (nadpisuje `PrestaShop\Classes\Cart\Cart` lub `CartCore` w zależności od wersji PrestaShop i kontekstu).
  - **Klasa nadrzędna**: `CartCore`
  - **Odpowiedzialność**: Ten plik zawiera nadpisaną metodę `getAvailableCarriers()`. Ta metoda jest kluczowa do określania, którzy przewoźnicy wysyłkowi są prezentowani klientowi podczas realizacji zamówienia. Nadpisanie wprowadza logikę do:
    1. Identyfikacji najdroższego produktu w bieżącym koszyku na podstawie konfiguracji modułu (`CFEP`, `CFEP_FREE`, `CFEP_COST`).
    2. Pobrania przewoźników specjalnie powiązanych z tym najdroższym produktem.
    3. Filtrowania listy wszystkich dostępnych przewoźników, aby uwzględnić tylko tych kompatybilnych z najdroższym produktem.
    4. Zwrócenia tej przefiltrowanej listy przewoźników.
  - **Kluczowe metody publiczne**:
    - `getAvailableCarriers(bool $return_full_list = false, int $id_zone = null, bool $use_cache = true)`: Jest to nadpisana metoda. Rozszerza oryginalną `CartCore::getAvailableCarriers` w celu zaimplementowania niestandardowej logiki filtrowania przewoźników. Najpierw wywołuje metodę nadrzędną, aby uzyskać wszystkich potencjalnie dostępnych przewoźników, a następnie stosuje własne filtrowanie na podstawie najdroższego produktu.
- **`cfep/override/classes/index.php`**

  - **Odpowiedzialność**: Jest to standardowy pusty plik `index.php`, zazwyczaj umieszczany w katalogach, aby zapobiec listowaniu katalogów po bezpośrednim dostępie przez przeglądarkę internetową. Nie ma on funkcjonalnego wpływu na logikę modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

- Brak. Moduł nie dodaje żadnego niestandardowego kodu JavaScript do front-office ani back-office.

### 4.5 Arkusze stylów CSS (`views/css/`)

- Brak. Moduł nie dodaje żadnego niestandardowego kodu CSS do front-office ani back-office.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- Brak. Moduł nie używa żadnych niestandardowych szablonów Smarty. Jego interfejs konfiguracyjny jest generowany dynamicznie przez `getContent()` w głównym pliku modułu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoje ustawienia konfiguracyjne w standardowej tabeli `ps_configuration`.

  - Wpisy `ps_configuration`:
    - `CFEP`: Przechowuje wybraną metodę pobierania przewoźników (np. 'price', 'free', 'cost').
    - `mypresta_updates`: Używane do wewnętrznych kontroli aktualizacji MyPresta.eu.
    - `update_`: Używane do wewnętrznych kontroli aktualizacji MyPresta.eu.
    - `updatev_`: Używane do wewnętrznych kontroli aktualizacji MyPresta.eu.
- **Tabela zarejestrowanych hooków**:
  Moduł nie rejestruje jawnie żadnych hooków w tabeli `ps_hook_module`. Jego funkcjonalność jest zaimplementowana poprzez nadpisanie klasy, co jest bardziej bezpośrednim sposobem na zmianę podstawowego zachowania PrestaShop bez polegania na konkretnych punktach wykonania hooków.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Metody wysyłki (przewoźnicy) z najdroższego produktu”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
