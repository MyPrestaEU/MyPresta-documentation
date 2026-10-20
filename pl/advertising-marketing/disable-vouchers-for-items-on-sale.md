---
title: "Wyłącz kupony dla produktów w promocji - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Wyłącz kupony dla produktów w promocji” od MyPresta.eu."
sidebar:
  label: "Wyłącz kupony dla produktów w promocji - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Disable vouchers for items on sale na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/disable-vouchers-for-items-on-sale.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/disable-vouchers-for-items-on-sale/)
>
> ---


# Wyłącz kupony dla produktów w promocji

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Wymagane są standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w każdym nowoczesnym środowisku hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu „Wyłącz kupony dla produktów w promocji”. Możesz uzyskać do niego dostęp, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Wyłącz kupony dla produktów w promocji”, a następnie klikając przycisk „Konfiguruj”.

#### **Ustawienia ogólne**

- **Wyłącz kupony dla produktów w promocji:**

  - **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji podstawowej funkcjonalności modułu.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (TAK):* Jeśli koszyk klienta zawiera *jakikolwiek* produkt, który jest aktualnie w promocji (ma specjalną cenę), zostanie mu uniemożliwione zastosowanie *jakiegokolwiek* kodu kuponu.
    - *Gdy wyłączone (NIE):* Moduł będzie nieaktywny. Klienci będą mogli stosować kody kuponów, nawet jeśli ich koszyk zawiera produkty w promocji, co pozwoli na „podwójne rabatowanie”.
  - **Zalecana wartość:** **TAK**, jeśli chcesz zapobiec podwójnemu rabatowaniu i chronić swoje marże.
  - **Scenariusz / przykład dla sprzedawcy:** Prowadzisz „Letnią Wyprzedaż” z 20% zniżką na wybrane produkty. Masz również kupon „Welcome10” dla nowych klientów. Jeśli to ustawienie jest **TAK**, nowy klient nie może użyć „Welcome10”, jeśli jego koszyk zawiera jakikolwiek produkt z Letniej Wyprzedaży.
- **Wyłącz moduł dla kodów, które zaczynają się od:**

  - **Co robi to ustawienie:** Pozwala to na utworzenie wyjątku. Jeśli kod kuponu zaczyna się od określonego ciągu znaków, który tutaj zdefiniujesz, ograniczenie modułu *nie* będzie miało zastosowania do tego kuponu, nawet jeśli w koszyku znajdują się produkty w promocji.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy wprowadzono ciąg znaków (np. „FREESHIP”):* Każdy kod kuponu zaczynający się od „FREESHIP” (np. „FREESHIP2023”, „FREESHIPNOW”) ominie ograniczenie modułu. Klienci mogą używać tych konkretnych kuponów nawet z produktami w promocji w koszyku.
    - *Gdy pozostawiono puste:* Nie są tworzone żadne wyjątki na podstawie prefiksów kodów kuponów. Wszystkie kupony podlegają zasadzie „Wyłącz kupony dla produktów w promocji”.
  - **Zalecana wartość:** Pozostaw puste, chyba że masz konkretne kupony, które *zawsze* chcesz zezwolić, niezależnie od produktów w promocji.
  - **Scenariusz / przykład dla sprzedawcy:** Masz specjalny kupon „FREESHIP”, który daje darmową wysyłkę. Decydujesz, że darmowa wysyłka powinna być zawsze dozwolona, nawet na produkty w promocji, aby zachęcić do większych zamówień. Wprowadziłbyś „FREESHIP” w tym polu.
- **Wiadomość dla klienta:**

  - **Co robi to ustawienie:** Jest to niestandardowa wiadomość, którą klienci zobaczą w swoim koszyku, gdy spróbują zastosować kod kuponu, ale zostaną zablokowani z powodu produktów w promocji.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy wprowadzono wiadomość (np. „Kuponów nie można używać z produktami w promocji.”):* Dokładnie ta wiadomość zostanie wyświetlona klientowi.
    - *Gdy pozostawiono puste:* Moduł prawdopodobnie wyświetli domyślny lub ogólny komunikat o błędzie, który może być mniej jasny dla klienta.
  - **Zalecana wartość:** Jasna, uprzejma i informacyjna wiadomość.
  - **Scenariusz / przykład dla sprzedawcy:** Chcesz jasno poinformować klientów: „Tego kuponu nie można zastosować, ponieważ Twój koszyk zawiera produkty już w promocji. Usuń produkty w promocji lub użyj innego kuponu.”

#### **Tabela szybkiego odniesienia do konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyłącz kupony dla produktów w promocji | TAK | Aktywuje/dezaktywuje podstawową funkcjonalność blokowania kuponów na produkty w promocji. |
| Konfiguracja modułu | Wyłącz moduł dla kodów, które zaczynają się od: | Pozostaw puste | Pozwala określonym kodom kuponów (według prefiksu) ominąć ograniczenia modułu. |
| Konfiguracja modułu | Wiadomość dla klienta | „Kuponów nie można używać z produktami w promocji.” (lub podobna) | Dostosowuje komunikat o błędzie wyświetlany klientom, gdy kupon jest zablokowany. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Włączyłem moduł, ale klienci nadal mogą używać kuponów na produkty w promocji. Co jest nie tak?**
O:

1. **Sprawdź ustawienie „Wyłącz kupony dla produktów w promocji”:** Upewnij się, że jest ustawione na **TAK** w konfiguracji modułu.
2. **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Zmiany w module czasami wymagają odświeżenia pamięci podręcznej.
3. **Zweryfikuj status promocji:** Sprawdź dokładnie, czy produkty, na których testujesz, są rzeczywiście oznaczone jako „w promocji” w PrestaShop (np. mają zdefiniowaną specjalną cenę, która czyni je tańszymi niż ich regularna cena).
4. **Sprawdź wyjątek prefiksu kodu kuponu:** Jeśli wprowadziłeś ciąg znaków w polu „Wyłącz moduł dla kodów, które zaczynają się od:”, upewnij się, że testowany kupon nie zaczyna się od tego ciągu.

**P: Moduł blokuje kupony, ale wiadomość się nie wyświetla lub wyświetla ogólny błąd.**
O:

1. **Dostosuj wiadomość:** Przejdź do konfiguracji modułu i upewnij się, że wprowadziłeś niestandardową wiadomość w polu „Wiadomość dla klienta”.
2. **Kompatybilność z motywem:** Chociaż moduł stara się integrować bezproblemowo, niektóre wysoce dostosowane motywy mogą nadpisywać domyślne mechanizmy wyświetlania błędów PrestaShop. Jeśli wiadomość się nie pojawia, może to być problem z motywem front-office. Skontaktuj się z twórcą motywu lub webmasterem w celu uzyskania pomocy.

**P: Czy mogę wyłączyć ten moduł dla określonych grup klientów lub pojedynczych produktów?**
O: Nie, ten moduł działa globalnie na podstawie obecności *jakiegokolwiek* produktu w promocji w koszyku. Nie oferuje szczegółowej kontroli dla określonych grup klientów ani wykluczeń produktów poza wyjątkiem prefiksu kodu kuponu. Jeśli potrzebujesz bardziej zaawansowanej logiki, może być wymagane niestandardowe opracowanie.

**P: Czy ten moduł wpłynie na moje SEO lub listy produktów?**
O: Nie, ten moduł działa wyłącznie na logice stosowania kuponów w koszyku. Nie zmienia cen produktów, opisów, adresów URL ani żadnych innych elementów front-office, które miałyby wpływ na SEO.

**P: Zaktualizowałem moją wersję PrestaShop i teraz moduł nie działa.**
O:

1. **Sprawdź kompatybilność modułu:** Upewnij się, że pobrałeś i zainstalowałeś wersję modułu specjalnie zaprojektowaną dla Twojej wersji PrestaShop z Twojego konta MyPresta.eu.
2. **Zainstaluj ponownie/skonfiguruj ponownie:** Czasami po dużej aktualizacji PrestaShop moduły mogą wymagać ponownej instalacji lub rekonfiguracji. Spróbuj odinstalować, a następnie ponownie zainstalować moduł (pamiętaj o wykonaniu kopii zapasowej ustawień, jeśli to możliwe, chociaż ten moduł ma minimalną ilość danych).
3. **Wyczyść pamięć podręczną:** Zawsze czyść pamięć podręczną PrestaShop po każdej aktualizacji lub zmianie modułu.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Wyłącz kupony dla produktów w promocji” (`dvfis`) działa głównie poprzez nadpisywanie podstawowego `CartController` w celu przechwycenia procesu stosowania kuponów. Wykorzystuje mechanizm nadpisywania PrestaShop do wstrzyknięcia swojej logiki przed walidacją i zastosowaniem kuponu. Konfiguracja modułu jest przechowywana w `ps_configuration` i dostępna za pośrednictwem głównej klasy modułu.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery front-office**:

  - `dvfis/override/controllers/front/CartController.php`
    - **Nazwa klasy i klasa nadrzędna**: `CartController` (nadpisuje podstawową klasę `CartController`)
    - **Odpowiedzialność**: Jest to najważniejszy plik. Rozszerza podstawowy `CartController` w celu modyfikacji metody `postProcess()`. W szczególności przechwytuje logikę, gdy klient próbuje dodać kupon (`addDiscount()`). Sprawdza, czy moduł jest włączony i czy koszyk zawiera produkty ze specjalną ceną. Jeśli oba warunki są spełnione (i kod kuponu nie pasuje do prefiksu wykluczenia), zapobiega dodaniu kuponu i wyświetla niestandardowy komunikat o błędzie.
  - `dvfis/override/controllers/front/index.php`
    - **Nazwa klasy i klasa nadrzędna**: Nie jest to plik klasy, zazwyczaj pusty plik lub plik z podstawowym `<?php exit;` w celu zapobieżenia bezpośredniemu listowaniu katalogów. Jest to standardowa praktyka dla katalogów nadpisywania PrestaShop.
- **Kontrolery administracyjne back-office**: Brak. Moduł używa standardowej metody `getContent()` w swoim głównym pliku modułu do konfiguracji.

### 4.3 Podstawowe klasy i modele (`classes/`)

Brak. Moduł nie definiuje żadnych niestandardowych klas `ObjectModel` ani innych samodzielnych klas PHP w katalogu `classes/`. Cała logika jest zawarta w głównym pliku modułu i nadpisaniu `CartController`.

### 4.4 Zasoby JavaScript (`views/js/`)

Brak. Moduł nie zawiera żadnych niestandardowych plików JavaScript. Wszystkie interakcje front-office są obsługiwane po stronie serwera przez nadpisanie `CartController`.

### 4.5 Arkusze stylów CSS (`views/css/`)

Brak. Moduł nie zawiera żadnych niestandardowych plików CSS. Wszelkie komunikaty wyświetlane klientowi będą dziedziczyć styl z komunikatów o błędach/powiadomieniach aktywnego motywu PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Brak. Moduł nie używa niestandardowych plików szablonów Smarty. Komunikaty o błędach są przekazywane bezpośrednio do tablicy `errors` `CartController`, które są następnie renderowane przez standardowy mechanizm wyświetlania błędów motywu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Wszystkie jego ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration`:

  - `DVFIS_MESSAGE`: Przechowuje niestandardową wiadomość dla klientów.
  - `DVFIS_ENABLED`: Przechowuje wartość logiczną (0 lub 1) dla włączania/wyłączania modułu.
  - `DVFIS_STR`: Przechowuje prefiks ciągu znaków dla wyjątków kodów kuponów.
  - `DVFIS_STRV`: (Prawdopodobnie klucz dziedziczny lub wewnętrzny do wersjonowania, niekonfigurowalny bezpośrednio przez użytkownika).
  - `mypresta_updates`, `update_`, `updatev_`: Klucze związane z systemem aktualizacji MyPresta.eu.
  - `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Standardowe klucze konfiguracyjne PrestaShop używane do obsługi języków w metodzie `getContent()` modułu.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Podczas inicjalizacji kontrolera Back Office | Używany przez moduł do dołączania własnych plików CSS/JS (jeśli istnieją) w Back Office. W przypadku tego modułu jest prawdopodobnie używany do systemu aktualizacji MyPresta.eu lub ogólnej konfiguracji modułu, a nie do niestandardowego stylizowania/skryptowania. |
| `actionFrontControllerInitAfter` | Po zainicjalizowaniu kontrolera Front Office | Używany przez moduł do potencjalnego wykonywania akcji lub modyfikowania zachowania kontrolera na wczesnym etapie cyklu żądania. W przypadku tego modułu jest prawdopodobnie używany do zapewnienia prawidłowego załadowania i aktywacji nadpisania `CartController`. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Wyłącz kupony dla produktów w promocji”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
