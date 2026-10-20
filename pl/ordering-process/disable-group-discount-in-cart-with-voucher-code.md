---
title: "Wyłącz rabat grupowy w koszyku z kodem kuponu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop „Wyłącz rabat grupowy w koszyku z kodem kuponu” od MyPresta.eu."
sidebar:
  label: "Wyłącz rabat grupowy w koszyku z kodem kuponu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Disable group discount in cart with voucher code na MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-group-discount-in-cart-with-voucher-code.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/disable-group-discount-in-cart-with-voucher-code/)
>
> ---


# Wyłącz rabat grupowy w koszyku z kodem kuponu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu, aby uzyskać dostęp do jego ustawień.

#### Ustawienie: Wyłącz rabat grupowy w koszyku z regułą koszyka

Jest to główny przełącznik kontrolny dla funkcjonalności modułu.

- **Co robi to ustawienie:** To ustawienie określa, czy moduł aktywnie interweniuje, aby wyłączyć rabaty grupowe, gdy w koszyku znajduje się kod kuponu.
- **Efekt zmiany tego ustawienia:**
  - ***Gdy Włączone:*** Jeśli klient należy do grupy ze specjalnym rabatem (np. 10% zniżki dla „Klientów Hurtowych”) ORAZ zastosuje kod kuponu (regułę koszyka) do swojego koszyka, rabat grupowy zostanie zignorowany. Do całkowitej kwoty zamówienia zostanie zastosowany tylko rabat z kuponu. Zapobiega to otrzymywaniu przez klienta obu rabatów jednocześnie.
  - ***Gdy Wyłączone:*** Moduł nie będzie interweniował. Zostanie zastosowane domyślne zachowanie PrestaShop, co oznacza, że jeśli klient jest uprawniony zarówno do rabatu grupowego, jak i rabatu z kuponu, oba mogą zostać zastosowane, potencjalnie nakładając się na siebie.
- **Zalecana wartość:** **Włączone**. Jest to podstawowa funkcjonalność modułu i jest ogólnie zalecana, aby zapobiec niezamierzonemu nakładaniu się rabatów i chronić Twoje marże zysku podczas kampanii kuponowych.
- **Scenariusz / przykład dla sprzedawcy:**
  - *Scenariusz 1 (Włączone):* Masz grupę „Klientów VIP”, która otrzymuje 5% zniżki na wszystkie produkty. Prowadzisz również kod kuponu „LATO20” na 20% zniżki. Klient VIP dodaje produkty do koszyka i stosuje „LATO20”. Gdy moduł jest **Włączony**, otrzyma tylko 20% zniżki z kuponu, a nie 5% + 20%.
  - *Scenariusz 2 (Wyłączone):* Używając tego samego przykładu, jeśli moduł jest **Wyłączony**, klient VIP może otrzymać zarówno 5% rabatu grupowego, jak i 20% rabatu z kuponu, co prowadzi do całkowitego rabatu 25% (lub bardziej złożonej kalkulacji w zależności od wewnętrznej kolejności stosowania rabatów w PrestaShop).

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyłącz rabat grupowy w koszyku z regułą koszyka | Włączone | Gdy włączone, rabaty grupowe są ignorowane, jeśli w koszyku znajduje się kod kuponu, zapewniając, że zastosowany zostanie tylko rabat z kuponu. Zapobiega nakładaniu się rabatów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Włączyłem moduł, ale klienci nadal otrzymują oba rabaty. Co jest nie tak?**
O1: Po pierwsze, upewnij się, że moduł jest rzeczywiście „Włączony” w jego konfiguracji. Po drugie, wyczyść pamięć podręczną PrestaShop (Przejdź do **Zaawansowane > Wydajność**, a następnie kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu). Czasami stare dane z pamięci podręcznej mogą uniemożliwić natychmiastowe wejście zmian w życie. Sprawdź również z nowym koszykiem i nową sesją klienta (np. w oknie incognito przeglądarki).

**P2: Czy ten moduł wpłynie na moje ceny specyficzne lub reguły cen katalogowych?**
O2: Nie, ten moduł dotyczy konkretnie *rabatów grupowych* i *reguł koszyka (kodów kuponów)*. Nie ingeruje w ceny specyficzne ustawione dla poszczególnych produktów, kombinacji produktów ani reguł cen katalogowych, które stosują się na podstawie ilości lub innych warunków. Modyfikuje jedynie interakcję między rabatami dla grup klientów a kodami kuponów.

**P3: Czy ten moduł działa ze wszystkimi rodzajami kodów kuponów (procentowe, stała kwota, darmowa wysyłka)?**
O3: Tak, logika modułu jest zaprojektowana do wykrywania obecności *dowolnej* aktywnej reguły koszyka (kodu kuponu) w koszyku. Po wykryciu reguły koszyka, wyłączy ona rabat grupowy, niezależnie od rodzaju rabatu, jaki zapewnia kupon (procentowy, stała kwota, darmowa wysyłka itp.).

**P4: Co jeśli chcę zezwolić na rabaty grupowe ORAZ kod kuponu dla konkretnej promocji?**
O4: Jeśli masz konkretną promocję, w której *chcesz* zezwolić na nakładanie się obu rabatów, musisz tymczasowo **Wyłączyć** ten moduł w jego konfiguracji. Pamiętaj, aby ponownie go włączyć po zakończeniu tej konkretnej promocji, jeśli chcesz wrócić do zachowania rabatu „tylko kupon”.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Ten moduł działa głównie poprzez nadpisanie podstawowej klasy PrestaShop. Zamiast używać hooków, bezpośrednio modyfikuje zachowanie klasy `Product`, aby dostosować sposób obliczania cen, gdy występuje rabat dla grupy klientów i aktywna jest reguła koszyka. Takie podejście zapewnia, że logika rabatowa jest stosowana na fundamentalnym poziomie podczas pobierania ceny produktu.

### 4.2 Kontrolery (`controllers/`)

- Ten moduł nie zawiera żadnych niestandardowych kontrolerów front-office ani back-office. Jego funkcjonalność jest zaimplementowana poprzez nadpisania klas.

### 4.3 Klasy i modele podstawowe (`classes/`)

- **Ścieżka pliku**: `exgcr/override/classes/Product.php`

  - **Nazwa klasy**: `Product` (nadpisuje podstawową klasę `Product`)
  - **Klasa nadrzędna**: `ProductCore`
  - **Odpowiedzialność**: To nadpisanie modyfikuje metodę `getPriceStatic` klasy `Product`. Metoda `getPriceStatic` jest kluczowa, ponieważ odpowiada za obliczanie końcowej ceny produktu, biorąc pod uwagę różne czynniki, takie jak podatki, ceny specyficzne, grupy klientów i reguły koszyka.
  - **Kluczowa logika**:
    - Nadpisanie sprawdza, czy moduł `exgcr` jest włączony.
    - Następnie sprawdza, czy do bieżącego koszyka zastosowano aktywną `CartRule` (kod kuponu).
    - Jeśli oba warunki są spełnione (moduł włączony ORAZ kupon obecny), modyfikuje parametry przekazywane do nadrzędnej metody `getPriceStatic`, aby skutecznie zignorować rabat dla grupy klientów. W szczególności ustawia parametr `$use_group_reduction` na `false` podczas wywoływania metody nadrzędnej, zapobiegając w ten sposób zastosowaniu rabatu grupowego.
    - Zapewnia to, że gdy używany jest kupon, obliczanie ceny odbywa się tak, jakby klient nie należał do grupy z rabatem, co zapobiega nakładaniu się rabatów grupowych z rabatami z kuponów.
- **Ścieżka pliku**: `exgcr/override/classes/index.php`

  - **Cel**: Jest to standardowy pusty plik `index.php` umieszczany w katalogach w celu zapobiegania listowaniu katalogów (środek bezpieczeństwa). Nie zawiera kodu funkcjonalnego.

### 4.4 Zasoby JavaScript (`views/js/`)

- Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

- Ten moduł nie zawiera żadnych niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- Ten moduł nie zawiera żadnych niestandardowych plików szablonów Smarty. Jego konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych.
  - Przechowuje swoje ustawienie konfiguracyjne (`exgcr`) w standardowej tabeli `ps_configuration`.
    - Wpis `PS_CONFIGURATION`: `EXGCR_ENABLED` (przechowuje `1` dla włączonego, `0` dla wyłączonego).
- **Tabela zarejestrowanych hooków**:

  - Ten moduł nie rejestruje żadnych specyficznych hooków w tabeli `ps_hook_module`. Jego funkcjonalność jest zaimplementowana poprzez nadpisanie klasy, co jest bardziej bezpośrednim sposobem modyfikacji podstawowego zachowania bez polegania na wykonaniu hooków.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Wyłącz rabat grupowy w koszyku z kodem kuponu”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu i integracji z Twoim sklepem PrestaShop.
