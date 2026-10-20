---
title: "Automatyczna zmiana statusu zamówienia - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Automatyczna zmiana statusu zamówienia” od MyPresta.eu."
sidebar:
  label: "Automatyczna zmiana statusu zamówienia - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Auto order status change na MyPresta.eu](https://mypresta.eu/modules/administration-tools/auto-order-status-change.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/auto-order-status-change/)
>
> ---


# Automatyczna zmiana statusu zamówienia

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne nietypowe konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Automatyczna zmiana statusu zamówienia)

Jest to główny i jedyny ekran konfiguracji modułu „Automatyczna zmiana statusu zamówienia”. Tutaj zdefiniujesz reguły, w jaki sposób statusy zamówień automatycznie się zmieniają.

Strona konfiguracji przedstawi Ci listę Twoich aktualnych statusów zamówień. Dla każdego statusu będziesz mógł zdefiniować, na jaki nowy status powinien się on automatycznie zmienić.

**Jak skonfigurować regułę:**

1. **Zidentyfikuj status „Od”:** Po lewej stronie tabeli konfiguracji zobaczysz listę wszystkich Twoich istniejących statusów zamówień (np. „Oczekiwanie na przelew bankowy”, „Płatność zaakceptowana”, „Wysłane” itp.). Jest to *status początkowy*, który wyzwala automatyczną zmianę.
2. **Wybierz status „Do”:** Obok każdego statusu „Od” znajdziesz rozwijane menu. To menu zawiera wszystkie dostępne statusy zamówień w Twoim sklepie. Wybierz status, na który zamówienie ma się *automatycznie zmienić*, gdy wejdzie w status „Od”.
3. **Zapisz zmiany:** Po ustawieniu pożądanych przejść, upewnij się, że klikniesz przycisk **„Zapisz”** (zazwyczaj na dole strony), aby zastosować swoje reguły.

Przyjrzyjmy się typowym ustawieniom, które napotkasz:

#### **Grupa ustawień: Automatyczne przejścia statusów**

Ta sekcja wyświetli tabelę lub serię rozwijanych list, umożliwiając mapowanie statusów „Od” na statusy „Do”.

- **Co robi to ustawienie:** Jest to podstawowa funkcjonalność modułu. Dla każdego istniejącego statusu zamówienia w Twoim sklepie możesz określić *status docelowy*, na który zamówienie automatycznie przejdzie, *jeśli* jego status zmieni się na status „Od”.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy status „Do” jest wybrany dla statusu „Od”:* Za każdym razem, gdy status zamówienia zostanie zaktualizowany do statusu „Od” (ręcznie przez administratora, przez bramkę płatności lub przez inny moduł), moduł natychmiast spróbuje zmienić go na wybrany status „Do”.
  - *Gdy wybrano „Brak zmiany” lub podobne (lub pozostawiono puste):* Jeśli nie wybierzesz statusu „Do” dla konkretnego statusu „Od”, żadna automatyczna zmiana nie nastąpi dla zamówień wchodzących w ten konkretny status „Od”. Zamówienie po prostu pozostanie w statusie „Od” do momentu ręcznej zmiany lub działania innej reguły/modułu.
- **Zalecana wartość:** Zależy to całkowicie od Twojego procesu pracy w sklepie.
  - **Przykład 1 (Płatność zaakceptowana na W realizacji):**
    - **Status Od:** `Płatność zaakceptowana`
    - **Status Do:** `W realizacji` (lub `Przygotowanie w toku`)
    - **Cel i wpływ:** Jest to bardzo powszechne i wysoce zalecane ustawienie. Gdy klient płaci, a płatność jest potwierdzona (np. przez PayPal, Stripe, moduł karty kredytowej), status zamówienia automatycznie aktualizuje się na „Płatność zaakceptowana”. Ta reguła natychmiast przenosi je do „W realizacji”, sygnalizując Twojemu magazynowi lub zespołowi realizacji, aby rozpoczął przygotowywanie zamówienia bez żadnej ręcznej interwencji. To oszczędza czas i zapewnia szybką realizację.
  - **Przykład 2 (Wysłane na Dostarczone):**
    - **Status Od:** `Wysłane`
    - **Status Do:** `Dostarczone`
    - **Cel i wpływ:** Podczas gdy „Wysłane” wskazuje, że przedmiot opuścił Twój magazyn, „Dostarczone” potwierdza, że dotarł do klienta. Jeśli Twoja integracja z przewoźnikiem nie aktualizuje automatycznie statusu na „Dostarczone”, możesz ustawić tę regułę. Należy jednak zachować ostrożność: zakłada to, że wszystkie zamówienia „Wysłane” są ostatecznie „Dostarczone”. Często lepiej jest polegać na śledzeniu przesyłek przez przewoźnika w celu uzyskania statusu „Dostarczone”, jeśli to możliwe. Użyj tego, jeśli chcesz szybko usunąć zamówienia „Wysłane” z aktywnej listy po rozsądnym czasie dostawy, ale pamiętaj, że może to nie odzwierciedlać faktycznej dostawy.
  - **Przykład 3 (Oczekiwanie na przelew bankowy na Anulowane - z ostrożnością):**
    - **Status Od:** `Oczekiwanie na przelew bankowy`
    - **Status Do:** `Anulowane`
    - **Cel i wpływ:** Jeśli masz ścisłą politykę, że płatności przelewem bankowym muszą zostać odebrane w określonym czasie, a ręcznie zmieniasz zaległe zamówienia na „Anulowane”, ten moduł mógłby to zautomatyzować. Jednak moduł wyzwala się *gdy status zmienia się na* „Oczekiwanie na przelew bankowy”. Jeśli chcesz anulować *po opóźnieniu*, sam ten moduł tego nie zrobi. Potrzebowałbyś innego mechanizmu (np. zadania crona lub innego modułu), aby zmienić status na „Oczekiwanie na przelew bankowy” *po* opóźnieniu, co następnie wyzwoliłoby ten moduł do zmiany go na „Anulowane”. Ten konkretny przypadek użycia jest mniej bezpośredni dla natychmiastowego wyzwalania tego modułu.
- **Scenariusz / przykład dla sprzedawcy:**
  - „Chcę, aby wszystkie zamówienia, które pomyślnie zakończyły płatność, automatycznie przechodziły do 'Przygotowanie w toku', aby mój zespół pakujący wiedział, że ma natychmiast rozpocząć pracę nad nimi.”
  - „Gdy klient prosi o zwrot pieniędzy i zmieniam status zamówienia na 'Zwrócone', chcę, aby automatycznie przechodziło do 'Zamknięte', aby nie było już na mojej aktywnej liście zamówień.”

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | `Status Od` (np. Płatność zaakceptowana) | Zależy od procesu pracy | Początkowy status, który wyzwala automatyczną zmianę. |
| Konfiguracja modułu | `Status Do` (rozwijana lista dla każdego `Statusu Od`) | `W realizacji` (dla `Płatność zaakceptowana`) | Status docelowy, na który zamówienie automatycznie przejdzie, gdy wejdzie w `Status Od`. Automatyzuje proces pracy, oszczędza czas. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moje statusy zamówień nie zmieniają się automatycznie. Co powinienem sprawdzić?**

- **O:** Najpierw przejdź do **Moduły > Menedżer modułów > Automatyczna zmiana statusu zamówienia > Konfiguruj** i upewnij się, że poprawnie ustawiłeś statusy „Od” i „Do”.
- **O:** Sprawdź, czy początkowa zmiana statusu (status „Od”) faktycznie następuje. Na przykład, jeśli oczekujesz, że „Płatność zaakceptowana” wywoła zmianę, upewnij się, że zamówienie najpierw osiągnie status „Płatność zaakceptowana”.
- **O:** Wyczyść pamięć podręczną PrestaShop. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Czasami konfiguracje modułów wymagają odświeżenia pamięci podręcznej, aby zaczęły działać.

**P2: Czy ten moduł może zmieniać statusy na podstawie opóźnienia czasowego (np. anulować zamówienie, jeśli nie zostanie opłacone w ciągu 24 godzin)?**

- **O:** Nie, ten moduł wyzwala się *natychmiast*, gdy status zamówienia *zmienia się* na określony status „Od”. Nie posiada wbudowanej funkcjonalności dla opóźnień czasowych ani zadań crona. W przypadku działań opartych na czasie, potrzebowałbyś oddzielnego modułu lub niestandardowego rozwiązania, które zmienia status zamówienia po opóźnieniu, co następnie wyzwoliłoby ten moduł.

**P3: Czy ten moduł będzie kolidował z aktualizacjami statusu mojej bramki płatności?**

- **O:** Nie, działa *z* nimi. Bramki płatności zazwyczaj aktualizują zamówienie do statusu takiego jak „Płatność zaakceptowana” lub „Oczekiwanie na płatność”. Ten moduł przejmuje kontrolę *po* tej początkowej aktualizacji, stosując Twoją następną regułę. Nie zapobiega on ustawieniu przez bramkę płatności jej początkowego statusu.

**P4: Mam niestandardowy szablon. Czy ten moduł będzie działał?**

- **O:** Tak, absolutnie. Ten moduł działa całkowicie w panelu administracyjnym PrestaShop i na logice przetwarzania zamówień. Nie posiada żadnych wizualnych komponentów front-office ani stylów specyficznych dla szablonu, więc jest w pełni kompatybilny z każdym szablonem PrestaShop.

**P5: Jak przetłumaczyć ustawienia modułu, jeśli mój panel administracyjny jest w innym języku?**

- **O:** PrestaShop automatycznie obsługuje tłumaczenie statusów zamówień. Moduł używa nazw Twoich istniejących statusów zamówień. Jeśli musisz przetłumaczyć własne elementy interfejsu modułu (takie jak przycisk „Zapisz” lub tytuły sekcji), możesz to zrobić za pomocą **Lokalizacja > Tłumaczenia** w panelu administracyjnym PrestaShop. Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój szablon, swój język, a następnie znajdź moduł „schange”.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem „Automatyczna zmiana statusu zamówienia”.

### 4.1 Przegląd architektury

Moduł „Automatyczna zmiana statusu zamówienia” (`schange`) to prosty moduł PrestaShop, zaprojektowany przede wszystkim do podłączenia się do zdarzenia `actionOrderStatusPostUpdate`. Podąża on za standardową strukturą modułu PrestaShop, wykorzystując klasę `Module` do instalacji, deinstalacji i konfiguracji. Jego podstawowa logika znajduje się w głównym pliku modułu, przetwarzając zmiany statusu na podstawie konfiguracji przechowywanych w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł **nie** definiuje żadnych niestandardowych klas ani instancji `ObjectModel` w katalogu `classes/`. Cała logika jest hermetyzowana w głównej klasie `schange`.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików CSS. Stylizacja strony konfiguracji jest obsługiwana przez domyślne style CSS panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa jednego szablonu Smarty dla swojego interfejsu konfiguracji.

- **Szablony administratora (`views/templates/admin/`)**:
  - `schange/views/tpl/selectedProducts.tpl`: Ten szablon jest używany w metodzie `getContent()` do renderowania formularza konfiguracji modułu. Zazwyczaj wyświetla listę statusów zamówień „Od” i odpowiadające im rozwijane listy statusów „Do”. Programiści mogą zbadać ten plik, aby zrozumieć strukturę formularza konfiguracji i sposób prezentacji mapowania statusów.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Ten moduł **nie** tworzy żadnych niestandardowych tabel SQL.
  - Wszystkie ustawienia konfiguracji (mapowania statusów „Od” na „Do”) są przechowywane w tabeli `ps_configuration`. Każde mapowanie jest prawdopodobnie przechowywane jako oddzielny klucz konfiguracji lub serializowana tablica pod jednym kluczem, używając nazwy modułu jako prefiksu (np. `SCHANGE_STATUS_FROM_X_TO_Y` lub `SCHANGE_STATUS_MAP`).
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionOrderStatusPostUpdate` | Wyzwalany natychmiast po pomyślnej aktualizacji statusu zamówienia. | Jest to główny hook używany przez moduł. Gdy status zamówienia zmienia się (np. z „Oczekiwanie na płatność” na „Płatność zaakceptowana”), ten hook jest wywoływany. Moduł następnie sprawdza, czy nowy status (status „Od”) ma skonfigurowany status „Do”. Jeśli istnieje mapowanie, moduł programowo aktualizuje zamówienie do wyznaczonego statusu „Do”. |

### 4.8 Główny plik modułu (`schange/index.php`)

- **Nazwa klasy**: `schange`
- **Klasa nadrzędna**: `Module`
- **Kluczowe metody**:
  - `__construct()`: Inicjalizuje metadane modułu (nazwa, zakładka, wersja, autor itp.).
  - `install()`: Rejestruje hook `actionOrderStatusPostUpdate` i potencjalnie ustawia domyślne wartości konfiguracji.
  - `uninstall()`: Wyrejestrowuje hook i usuwa wartości konfiguracji z `ps_configuration`.
  - `getContent()`: Renderuje stronę konfiguracji modułu w Panelu administracyjnym. Ta metoda obsługuje przesyłanie formularzy, zapisuje ustawienia do `ps_configuration` i wyświetla interfejs mapowania statusów za pomocą `selectedProducts.tpl`.
  - `hookActionOrderStatusPostUpdate($params)`: Jest to główny handler logiki.
    - Odbiera `$params` zawierające `newOrderStatus` i `id_order`.
    - Pobiera skonfigurowane mapowania statusów z `ps_configuration`.
    - Jeśli `newOrderStatus` pasuje do skonfigurowanego statusu „Od”, ładuje obiekt `Order` dla `id_order`.
    - Następnie próbuje zaktualizować status zamówienia do odpowiadającego statusu „Do” za pomocą `Order->setCurrentState()`.
    - Zapewnia, że zmiana statusu jest prawidłowa i obsługuje potencjalne błędy.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Automatyczna zmiana statusu zamówienia”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
