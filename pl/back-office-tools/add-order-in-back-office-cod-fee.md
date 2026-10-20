---
title: "Dodaj zamówienie w panelu administracyjnym + opłata za pobranie - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Dodaj zamówienie w panelu administracyjnym + opłata za pobranie” od MyPresta.eu."
sidebar:
  label: "Dodaj zamówienie w panelu administracyjnym + opłata za pobranie - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Add order in back office + cod fee na MyPresta.eu](https://mypresta.eu/modules/administration-tools/add-order-in-back-office-cod-fee.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/add-order-in-back-office-cod-fee/)
>
> ---


# Dodaj zamówienie w panelu administracyjnym + opłata za pobranie

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).
- **Wymagany moduł**: Ten moduł wymaga zainstalowania i skonfigurowania w Twoim sklepie modułu płatności „Płatność za pobraniem z opłatą”. Ten moduł *rozszerza* funkcjonalność takiego modułu płatności w Panelu administracyjnym.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Ten moduł ma bardzo prostą stronę konfiguracji. Jego główną funkcją jest włączanie lub wyłączanie podstawowej funkcjonalności modułu.

**Dostęp:** Panel administracyjny > Moduły > Menedżer modułów > Wyszukaj „Dodaj zamówienie w panelu administracyjnym + opłata za pobranie” > Kliknij „Konfiguruj”

#### **Włącz / Wyłącz funkcjonalność modułu**

- **Co robi to ustawienie:** Jest to standardowy przełącznik, który kontroluje, czy funkcjonalność modułu jest aktywna, czy nieaktywna. Po włączeniu moduł automatycznie doda opłaty za pobranie do ręcznie tworzonych zamówień w Panelu administracyjnym. Po wyłączeniu ta funkcjonalność zostanie zatrzymana.
- **Efekt zmiany tego ustawienia:**
  - *Po włączeniu (TAK):* Moduł będzie aktywnie monitorował proces tworzenia zamówień w Panelu administracyjnym. Jeśli wybierzesz metodę płatności „Płatność za pobraniem z opłatą” podczas tworzenia zamówienia, powiązana opłata zostanie automatycznie obliczona i dodana do sumy zamówienia.
  - *Po wyłączeniu (NIE):* Moduł nie będzie ingerował w proces tworzenia zamówień w Panelu administracyjnym. Jeśli wybierzesz metodę płatności „Płatność za pobraniem z opłatą”, opłata *nie* zostanie automatycznie dodana, a Ty będziesz musiał ręcznie dostosować sumę zamówienia, jeśli chcesz ją uwzględnić.
- **Zalecana wartość:** **TAK**. Aby skorzystać z głównego celu modułu, jakim jest automatyzacja włączania opłaty za pobranie, powinien on być włączony.
- **Scenariusz / przykład sprzedawcy:** Przyjmujesz zamówienie telefoniczne od klienta, który chce zapłacić za pobraniem. Przechodzisz do Panel administracyjny > Zamówienia > Dodaj nowe zamówienie. Po dodaniu produktów i wybraniu klienta, wybierasz swoją metodę płatności „Płatność za pobraniem z opłatą”. Jeśli ten moduł jest włączony, opłata za pobraniem natychmiast pojawi się w podsumowaniu zamówienia, zapewniając, że klient zostanie prawidłowo obciążony. Jeśli jest wyłączony, opłata będzie brakować, co może prowadzić do nieprawidłowej sumy zamówienia.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz / Wyłącz moduł | TAK | Kontroluje, czy moduł automatycznie dodaje opłaty za pobraniem do ręcznie tworzonych zamówień w Panelu administracyjnym. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zainstalowałem moduł, ale opłata za pobraniem nie pojawia się, gdy tworzę zamówienie w Panelu administracyjnym.**
O:

1.  **Sprawdź status modułu:** Przejdź do Moduły > Menedżer modułów i upewnij się, że „Dodaj zamówienie w panelu administracyjnym + opłata za pobraniem” jest zainstalowany i **włączony**.
2.  **Sprawdź wymagania wstępne:** Ten moduł *wymaga* zainstalowania i skonfigurowania oddzielnego modułu płatności „Płatność za pobraniem z opłatą”. Upewnij się, że masz taki moduł i jest on prawidłowo skonfigurowany z jego opłatami. Ten moduł *rozszerza* tę funkcjonalność, sam nie zapewnia mechanizmu opłaty za pobraniem.
3.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe pojawienie się nowej funkcjonalności modułu. Przejdź do Zaawansowane > Wydajność i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
4.  **Zweryfikuj metodę płatności:** Upewnij się, że wybierasz *konkretną* metodę płatności „Płatność za pobraniem z opłatą”, którą zapewnia Twój inny moduł, a nie ogólną opcję „Płatność za pobraniem” bez opłaty.

**P: Czy ten moduł wpłynie na zamówienia składane przez klientów w front-office mojego sklepu?**
O: Nie, ten moduł wpływa tylko na proces *ręcznego* tworzenia zamówień w Panelu administracyjnym PrestaShop. Nie zmienia sposobu, w jaki klienci składają zamówienia ani sposobu obliczania opłat w procesie realizacji zamówienia w front-endzie.

**P: Co jeśli mam wiele modułów „Płatność za pobraniem z opłatą”?**
O: Ten moduł został zaprojektowany do integracji ze standardowym sposobem, w jaki PrestaShop obsługuje moduły płatności i związane z nimi opłaty. Powinien działać z każdym modułem „Płatność za pobraniem z opłatą”, który prawidłowo rejestruje swoje obliczenia opłat w ramach płatności PrestaShop. Jeśli napotkasz problemy, skontaktuj się z pomocą techniczną MyPresta.eu.

**P: Czy ten moduł sam tworzy opcję płatności „Płatność za pobraniem z opłatą”?**
O: Nie, nie tworzy. Ten moduł jest *rozszerzeniem* istniejącego modułu płatności „Płatność za pobraniem z opłatą”. Musisz mieć zainstalowany oddzielny moduł płatności, który zapewnia rzeczywistą metodę płatności za pobraniem i jej konfigurację opłat.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Dodaj zamówienie w panelu administracyjnym + opłata za pobranie” to lekki moduł PrestaShop, zaprojektowany przede wszystkim do rozszerzania funkcjonalności `AdminOrdersController`. Osiąga swój cel, włączając się w określone akcje w procesie tworzenia zamówień w Panelu administracyjnym, w szczególności, gdy metoda płatności jest wybierana lub aktualizowana. Jego podstawowa logika znajduje się w głównym pliku modułu, wykorzystując system hooków PrestaShop do modyfikowania istniejącego zachowania bez bezpośredniej modyfikacji plików rdzenia. Opiera się na obecności oddzielnego modułu płatności „Płatność za pobraniem z opłatą”, aby zapewnić rzeczywistą logikę obliczania opłat.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów Front-Office ani Back-Office. Jego funkcjonalność jest wstrzykiwana do istniejącego `AdminOrdersController` za pośrednictwem hooków.

### 4.3 Klasy rdzenia i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani instancji `ObjectModel`. Cała logika zawarta jest w głównym pliku modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Funkcjonalność jest obsługiwana po stronie serwera.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie zawiera żadnych niestandardowych plików szablonów Smarty. Jego konfiguracja jest obsługiwana przez standardową metodę `getContent()`, która zazwyczaj używa formularzy pomocniczych PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

**Tabele bazy danych**:
Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoją konfigurację (np. status włączenia/wyłączenia) w standardowej tabeli `ps_configuration`, używając klucza takiego jak `ADDORDERINBACKOFFICECODFEE_ENABLED`.

**Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje zasoby multimedialne. | Używany do potencjalnego wstrzykiwania JS/CSS, jeśli jest to potrzebne, chociaż ten moduł nie używa go do tego celu. Jest to wspólny hook do modyfikacji po stronie administratora. |
| `actionAdminOrdersControllerSaveAfter` | Wykonywany po zapisaniu zamówienia w `AdminOrdersController`. | Jest to główny hook używany przez moduł. Pozwala modułowi sprawdzić nowo zapisane zamówienie, sprawdzić wybraną metodę płatności, a jeśli jest to płatność za pobraniem z opłatą, zastosować opłatę. |
| `displayAdminOrder` | Wykonywany na stronie szczegółów zamówienia w Panelu administracyjnym. | Może być używany do wyświetlania dodatkowych informacji związanych z opłatą za pobraniem w widoku zamówienia, chociaż podstawową funkcją modułu jest *dodawanie* opłaty, a nie tylko jej wyświetlanie. |

**Kluczowa logika w `add-order-in-back-office-cod-fee.php`:**

Podstawowa funkcjonalność modułu jest prawdopodobnie zaimplementowana w metodzie `hookActionAdminOrdersControllerSaveAfter`. Ta metoda będzie:

1.  Pobierać obiekt `Order`, który został właśnie zapisany.
2.  Identyfikować `PaymentModule` użyty do zamówienia.
3.  Sprawdzać, czy wybrany moduł płatności jest typu „Płatność za pobraniem z opłatą” (zazwyczaj wiąże się to ze sprawdzeniem nazwy modułu lub konkretnej właściwości/metody, którą udostępnia).
4.  Jeśli tak, wywoła metodę w tym module płatności (lub bezpośrednio obliczy na podstawie jego konfiguracji), aby uzyskać opłatę za pobraniem.
5.  Na koniec zaktualizuje sumę zamówienia, doda nowy szczegół `OrderInvoice` (lub zmodyfikuje istniejący), aby odzwierciedlić opłatę za pobraniem, i utrwali te zmiany w bazie danych. Może to obejmować utworzenie nowego wpisu `OrderPayment` lub dostosowanie pól `total_paid_tax_incl` i `total_paid_tax_excl` obiektu `Order`.

Deweloperzy powinni być świadomi, że ten moduł w dużym stopniu opiera się na wewnętrznej strukturze i zachowaniu modułu płatności „Płatność za pobraniem z opłatą”, z którym współpracuje. Wszelkie niestandardowe moduły płatności za pobraniem mogą wymagać dostosowań lub specyficznych kontroli kompatybilności.

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnego wsparcia, aktualizacji i dalszych informacji dotyczących modułu „Dodaj zamówienie w panelu administracyjnym + opłata za pobranie”, odwiedź swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/) lub skontaktuj się bezpośrednio z pomocą techniczną MyPresta.eu.
