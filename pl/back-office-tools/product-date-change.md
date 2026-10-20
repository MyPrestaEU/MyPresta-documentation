---
title: "Zmiana daty produktu - Instrukcja dla sprzedawcy i Przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop „Zmiana daty produktu” od MyPresta.eu."
sidebar:
  label: "Zmiana daty produktu - Instrukcja dla sprzedawcy i Przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product date change na MyPresta.eu](https://mypresta.eu/modules/administration-tools/product-date-change.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/product-date-change/)
>
> ---


# Zmiana daty produktu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknięcie „Konfiguruj” przeniesie Cię do głównej strony konfiguracji modułu „Zmiana daty produktu”. Tutaj będziesz wybierać produkty i modyfikować ich daty.

#### **Wybór produktu**

-   **Co robi to ustawienie:** Ta sekcja pozwala wyszukiwać i wybierać konkretne produkty, których daty chcesz zmodyfikować.
-   **Efekt zmiany tego ustawienia:**
    *   *Wyszukiwanie produktu:* Wpisanie tekstu w polu wyszukiwania przefiltruje listę produktów, ułatwiając znalezienie dokładnie tego produktu, którego potrzebujesz.
    *   *Wybór produktu:* Po wybraniu produktu, jego aktualne daty utworzenia i aktualizacji zostaną wyświetlone, a Ty będziesz mógł wprowadzić nowe daty.
-   **Zalecana wartość:** Użyj paska wyszukiwania, aby szybko zlokalizować produkty według nazwy lub ID.
-   **Scenariusz / przykład sprzedawcy:** Chcesz zmienić datę dla „Sukienki letniej 2023”. Wpisujesz „Sukienka letnia” w polu wyszukiwania, a moduł wyświetla pasujące produkty. Następnie klikasz „Sukienka letnia 2023”, aby ją wybrać.

#### **Zmień datę utworzenia produktu**

-   **Co robi to ustawienie:** To pole pozwala ustawić nową `date_add` (datę utworzenia) dla wybranego produktu. Data ta jest często używana przez PrestaShop do określenia, czy produkt jest „nowy”.
-   **Efekt zmiany tego ustawienia:**
    *   *Po wprowadzeniu i zapisaniu nowej daty:* Data utworzenia produktu w Twojej bazie danych zostanie zaktualizowana. Może to spowodować ponowne pojawienie się produktu w blokach „Nowe produkty” lub zmianę jego pozycji podczas sortowania według „Daty dodania”.
    *   *Gdy pozostawiono bez zmian:* Oryginalna data utworzenia produktu zostanie zachowana.
-   **Zalecana wartość:** Ustaw datę, która odzwierciedla, kiedy chcesz, aby produkt był uważany za „nowy” lub kiedy został faktycznie dodany do Twojego katalogu. Do ponownego wyróżniania idealna jest niedawna data (dzisiaj lub wczoraj).
-   **Scenariusz / przykład sprzedawcy:** Twój produkt „Płaszcz zimowy” został dodany w zeszłym roku. Chcesz promować go jako „nowość” na nadchodzący sezon zimowy. Wybierasz produkt, a następnie ustawiasz „Zmień datę utworzenia produktu” na dzisiejszą datę. Teraz pojawi się on w sekcji „Nowe produkty”.

#### **Zmień datę aktualizacji produktu**

-   **Co robi to ustawienie:** To pole pozwala ustawić nową `date_upd` (datę ostatniej aktualizacji) dla wybranego produktu. Data ta jest używana do wewnętrznego śledzenia i może również wpływać na sortowanie produktów.
-   **Efekt zmiany tego ustawienia:**
    *   *Po wprowadzeniu i zapisaniu nowej daty:* Data ostatniej aktualizacji produktu w Twojej bazie danych zostanie zmodyfikowana. Może to wpłynąć na opcje sortowania, gdzie klienci sortują według „Daty aktualizacji”.
    *   *Gdy pozostawiono bez zmian:* Oryginalna data aktualizacji produktu zostanie zachowana.
-   **Zalecana wartość:** Ustaw datę, która odzwierciedla ostatni raz, kiedy wprowadziłeś znaczące zmiany w produkcie (np. zaktualizowany opis, cena, zdjęcia) lub jeśli chcesz przenieść go na górę list „ostatnio aktualizowanych”.
-   **Scenariusz / przykład sprzedawcy:** Właśnie zaktualizowałeś opis i dodałeś nowe zdjęcia dla swojego produktu „Organiczne ziarna kawy”. Chcesz, aby ten produkt pojawiał się wyżej, gdy klienci sortują według „ostatnio aktualizowanych”. Wybierasz produkt i ustawiasz „Zmień datę aktualizacji produktu” na dzisiejszą datę.

#### **Przycisk Zapisz**

-   **Co robi to ustawienie:** Ten przycisk stosuje wszystkie zmiany dat, które wprowadziłeś dla wybranego produktu.
-   **Efekt zmiany tego ustawienia:** Kliknięcie „Zapisz” zatwierdzi nowe daty utworzenia i/lub aktualizacji w Twojej bazie danych PrestaShop. Zazwyczaj zobaczysz komunikat o sukcesie.
-   **Zalecana wartość:** Zawsze klikaj „Zapisz” po wprowadzeniu jakichkolwiek modyfikacji dat.
-   **Scenariusz / przykład sprzedawcy:** Po ustawieniu dat utworzenia i aktualizacji dla swoich „Limitowanych edycji sneakersów”, klikasz „Zapisz”, aby zastosować te zmiany w swoim sklepie.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Pole wyszukiwania produktu | N/A | Znajdź produkty według nazwy lub ID, aby zmodyfikować ich daty. |
| Strona konfiguracji modułu | Zmień datę utworzenia produktu | Bieżąca `date_add` produktu | Ustawia nową datę utworzenia. Wpływa na widoczność „Nowych produktów” i sortowanie według „Daty dodania”. Zalecane: Niedawna data do ponownego wyróżniania. |
| Strona konfiguracji modułu | Zmień datę aktualizacji produktu | Bieżąca `date_upd` produktu | Ustawia nową datę ostatniej aktualizacji. Wpływa na sortowanie według „Daty aktualizacji”. Zalecane: Niedawna data po znaczących zmianach produktu. |
| Strona konfiguracji modułu | Przycisk Zapisz | N/A | Stosuje wszystkie wybrane zmiany dat do produktu w bazie danych. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Zmieniłem datę, ale produkt nie wyświetla się jako „nowy” na mojej stronie głównej. Co jest nie tak?**
O1:

-   **Wyczyść pamięć podręczną:** PrestaShop w dużym stopniu opiera się na pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). To najczęstsze rozwiązanie.
-   **Konfiguracja modułu:** Sprawdź ustawienia modułu „Nowe produkty” (np. „Blok nowych produktów” lub „Strona nowych produktów”). Upewnij się, że jest skonfigurowany do wyświetlania produktów na podstawie daty ich utworzenia i że liczba dni dla „nowych” produktów jest odpowiednio ustawiona (np. 30 dni). Jeśli ustawisz datę utworzenia produktu na starszą niż ten próg, nie pojawi się on jako nowy.
-   **Specyfika szablonu:** Niektóre szablony mogą mieć własne buforowanie lub niestandardową logikę dla „nowych produktów”. Jeśli wyczyszczenie pamięci podręcznej nie działa, zapoznaj się z dokumentacją lub wsparciem swojego szablonu.

**P2: Czy zmiana daty produktu wpłynie na moje SEO?**
O2: Bezpośrednio, nie. Wyszukiwarki takie jak Google koncentrują się przede wszystkim na treści Twojej strony produktu (opis, zdjęcia, recenzje) i linkach zewnętrznych, a nie na wewnętrznych datach produktów PrestaShop. Jednak pośrednio, jeśli zmiana daty sprawi, że produkt pojawi się jako „nowy” i zwiększy ruch wewnętrzny lub sprzedaż, to zwiększone zaangażowanie *może* pozytywnie wpłynąć na SEO w czasie. Chodzi bardziej o doświadczenie użytkownika i merchandising niż o bezpośrednią manipulację SEO.

**P3: Czy mogę zmieniać daty dla wielu produktów jednocześnie (edycja masowa)?**
O3: Ten moduł jest przeznaczony do indywidualnych zmian dat produktów. Jeśli potrzebujesz masowo edytować daty dla dużej liczby produktów, zazwyczaj potrzebujesz bardziej zaawansowanego narzędzia do importu/eksportu lub niestandardowego skryptu. W przypadku kilku produktów, wykonywanie ich pojedynczo za pomocą tego modułu jest wydajne.

**P4: Co się stanie, jeśli ustawię datę przyszłą?**
O4: PrestaShop zaakceptuje datę przyszłą. Jednak praktyczny efekt może być ograniczony. Produkt z ustawioną przyszłą datą utworzenia może nie pojawić się na listach „nowych produktów” do momentu nadejścia tej daty. Ogólnie zaleca się używanie dat bieżących lub przeszłych.

**P5: Zmieniłem datę, ale gdy edytuję produkt w Panelu administracyjnym, stara data nadal tam jest.**
O5: Ten moduł bezpośrednio modyfikuje pola `date_add` i `date_upd` w bazie danych. Kiedy przeglądasz produkt na standardowej stronie edycji produktu PrestaShop, powinien on odzwierciedlać te zmiany. Jeśli tak nie jest, upewnij się, że kliknąłeś „Zapisz” w konfiguracji modułu, wyczyściłeś pamięć podręczną PrestaShop i ponownie załadowałeś stronę edycji produktu. Jeśli problem nadal występuje, może istnieć konflikt z innym modułem lub głębszy problem z buforowaniem.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Product date change` (`pdc`) to prosty moduł PrestaShop zaprojektowany do bezpośredniej interakcji z `Product` ObjectModel. Wykorzystuje standardową metodę `getContent()` do konfiguracji w Panelu administracyjnym, zapewniając prosty formularz do wyboru produktu i modyfikacji jego pól `date_add` i `date_upd`. Nie wprowadza nowych tabel baz danych, złożonych kontrolerów ani rozbudowanej logiki front-office, co czyni go lekkim i skoncentrowanym na swoim podstawowym zadaniu administracyjnym.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych niestandardowych kontrolerów front-office ani back-office. Cała logika jest hermetyzowana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas ani ObjectModels w katalogu `classes/`. Bezpośrednio współdziała z podstawowym ObjectModelem `Product` PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Stylizacja ma być obsługiwana przez domyślne style Panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`pdc/views/pdc.tpl`**:
    *   **Zakres**: Konfiguracja administracyjna Panelu administracyjnego.
    *   **Cel**: Ten szablon renderuje główny formularz konfiguracji modułu. Zawiera:
        *   Pole wyszukiwania do znajdowania produktów.
        *   Obszary wyświetlania bieżących `date_add` i `date_upd` wybranego produktu.
        *   Pola wejściowe (prawdopodobnie selektory dat) do ustawiania nowych wartości `date_add` i `date_upd`.
        *   Przycisk wysyłania do zapisywania zmian.
    *   **Użycie**: Ten szablon jest renderowany przez metodę `getContent()` modułu `pdc`.
    *   **Kluczowe selektory**: Programiści mogą sprawdzić wygenerowany kod HTML pod kątem konkretnych identyfikatorów lub klas, aby w razie potrzeby nadpisać stylizację, chociaż zazwyczaj nie jest to wymagane dla prostego formularza administracyjnego.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    *   Ten moduł nie tworzy żadnych niestandardowych tabel baz danych.
    *   Bezpośrednio modyfikuje kolumny `date_add` i `date_upd` w istniejącej tabeli `ps_product` (i potencjalnie `ps_product_shop`, jeśli zarządzane są daty specyficzne dla kontekstu, chociaż opis modułu sugeruje bezpośrednią modyfikację obiektu produktu).
    *   Wartości konfiguracyjne (jeśli istnieją, chociaż żadne nie są wyraźnie wymienione poza bezpośrednią manipulacją produktem) byłyby przechowywane w `ps_configuration`.
-   **Tabela zarejestrowanych hooków**:
    Ten moduł nie rejestruje żadnych konkretnych hooków do wyświetlania w front-office ani akcji w back-office poza standardowymi `displayBackOfficeHeader` (dla zasobów, jeśli istnieją) i `moduleRoutes` (jeśli potrzebne byłyby niestandardowe adresy URL, co nie ma miejsca w tym module). Jego główna interakcja odbywa się za pośrednictwem metody `getContent()`.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayBackOfficeHeader` | Renderuje się w sekcji `<head>` stron Panelu administracyjnego. | (Potencjalnie) Do włączenia wszelkich niezbędnych JS/CSS dla strony konfiguracji modułu, chociaż w tym module ich nie ma. |
| `actionProductUpdate` | Wykonywany po aktualizacji produktu. | Wewnętrzna logika modułu do aktualizacji dat produktów może wywołać ten hook, ale sam moduł nie rejestruje się jawnie, aby go nasłuchiwać ani wykonywać na jego podstawie działań. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Zmiana daty produktu”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
