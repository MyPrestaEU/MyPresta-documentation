---
title: "Metody płatności według produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Metody płatności według produktów” od MyPresta.eu."
sidebar:
  label: "Metody płatności według produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Payment methods by products na MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/payment/payment-methods-by-products/)
>
> ---


# Metody płatności według produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

Ten moduł ma dwa główne obszary konfiguracji: początkową stronę konfiguracji modułu i dedykowany ekran zarządzania do tworzenia powiązań produkt-płatność.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Metody płatności według produktów)

Po kliknięciu „Konfiguruj” po instalacji, znajdziesz się na głównej stronie konfiguracji modułu. Ta strona zazwyczaj zawiera ogólne ustawienia modułu.

**Obecnie na tej głównej stronie konfiguracji nie wykryto żadnych konkretnych ustawień poza standardowymi informacjami o module. Podstawowa funkcjonalność jest zarządzana za pośrednictwem dedykowanego ekranu „Powiązania płatności z produktami”.**

Jeśli przyszłe wersje wprowadzą tutaj ustawienia, pojawią się one jako przełączniki, pola wprowadzania lub listy rozwijane. Na razie możesz przejść bezpośrednio do dedykowanego ekranu zarządzania.

### 2.2 Dedykowany ekran administracyjny: Powiązania płatności z produktami (Panel administracyjny > Moduły > Metody płatności według produktów > Powiązania płatności z produktami)

To jest centralne miejsce do zarządzania ograniczeniami płatności dla produktów. Ten ekran znajdziesz, przechodząc do **Moduły > Menedżer modułów**, znajdując „Metody płatności według produktów”, klikając „Konfiguruj”, a następnie szukając zakładki lub linku oznaczonego „Powiązania płatności z produktami” (lub podobnego, w zależności od nawigacji modułu).

**Nazwa ekranu i lokalizacja w menu:**

- **Ścieżka menu:** Panel administracyjny > Moduły > Menedżer modułów > Metody płatności według produktów > Konfiguruj > **Powiązania płatności z produktami** (lub podobna zakładka/link na stronie konfiguracji).
- Ten ekran umożliwia przeglądanie, dodawanie, edytowanie i usuwanie powiązań między produktami a metodami płatności.

**Dostępne działania i ustawienia:**

#### 2.2.1 Widok listy „Powiązania płatności z produktami”

Ten widok przedstawia tabelę wszystkich istniejących ograniczeń płatności dla produktów, które ustawiłeś.

| Nazwa kolumny | Cel i wpływ |
| --- | --- |
| **ID** | Unikalny identyfikator dla każdego powiązania. |
| **Produkt** | Nazwa produktu objętego ograniczeniem. |
| **Płatność** | Nazwa metody płatności, która jest ograniczona lub dozwolona dla tego produktu. |
| **Kraj** | (Jeśli dotyczy) Kraj, dla którego obowiązuje to ograniczenie. Jeśli pozostawione puste, obowiązuje globalnie. |
| **Działania** | Ikony do **Edycji** (ikona ołówka) lub **Usunięcia** (ikona kosza) istniejącego powiązania. |

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

- **Przeglądaj istniejące zasady:** Regularnie sprawdzaj tę listę, aby upewnić się, że Twoje ograniczenia są aktualne z katalogiem produktów i potrzebami biznesowymi.
- **Identyfikuj konflikty:** Szukaj wszelkich nakładających się lub sprzecznych zasad, zwłaszcza jeśli masz wiele produktów i metod płatności.
- **Użyj wyszukiwania/filtrowania:** Jeśli lista stanie się długa, użyj dostępnych opcji wyszukiwania lub filtrowania, aby szybko znaleźć konkretne ograniczenia dotyczące produktów lub płatności.

#### 2.2.2 Dodawanie lub edytowanie „Powiązania płatności z produktami”

Aby dodać nowe ograniczenie, zazwyczaj znajdziesz przycisk „Dodaj nowe” w widoku listy. Podczas edycji klikasz ikonę ołówka obok istniejącego wpisu. Spowoduje to otwarcie formularza z następującymi polami:

| Pole formularza | Co robi to ustawienie | Efekt zmiany tego ustawienia | Zalecana wartość | Scenariusz/przykład sprzedawcy |
| --- | --- | --- | --- | --- |
| **ID Produktu** | To pole pozwala wybrać konkretny produkt, który chcesz powiązać z ograniczeniami płatności. | Po wybraniu produktu moduł zastosuje wybrane ograniczenia płatności, gdy ten produkt znajdzie się w koszyku klienta. | Wybierz dokładny produkt z katalogu. Użyj funkcji wyszukiwania, jeśli masz wiele produktów. | Sprzedajesz „Ebook cyfrowy: Przewodnik marketingowy”. Chcesz mieć pewność, że jest on opłacany tylko przez PayPal lub kartę kredytową, a nie za pobraniem. Wybierasz ten produkt tutaj. |
| **Metody płatności** | To jest lista wszystkich aktywnych metod płatności w Twoim sklepie PrestaShop. Wybierasz, które metody płatności są **dozwolone** dla wybranego produktu. | - *Gdy wybierzesz jedną lub więcej metod płatności:* Tylko te wybrane metody będą dostępne przy kasie, jeśli powiązany produkt znajduje się w koszyku. Wszystkie inne metody płatności zostaną ukryte.   - *Gdy nie wybierzesz ŻADNYCH metod płatności:* Oznacza to, że produktu nie można kupić, lub odziedziczy on zasady z innych produktów w koszyku. Ogólnie nie zaleca się pozostawiania tego pola pustego, chyba że masz bardzo specyficzny przypadek użycia. | Wybierz wszystkie metody płatności, które są akceptowalne dla wybranego produktu. | Dla „Ebooka cyfrowego: Przewodnik marketingowy” zaznaczasz „PayPal” i „Karta kredytowa”. Jeśli klient kupi ten ebook, przy kasie pojawią się tylko te dwie opcje. |
| **Kraj** | (Opcjonalnie) To pole pozwala określić kraj, dla którego obowiązuje to konkretne ograniczenie produkt-płatność. | - *Gdy kraj jest wybrany:* Ograniczenie (produkt + dozwolone płatności) będzie obowiązywać tylko wtedy, gdy adres wysyłki klienta znajduje się w wybranym kraju.   - *Gdy pozostawione puste:* Ograniczenie obowiązuje globalnie, niezależnie od kraju klienta. | Pozostaw puste dla zastosowania globalnego lub wybierz konkretny kraj, jeśli ograniczenie jest geograficznie ograniczone. | Sprzedajesz „Kruchą szklaną rzeźbę”, którą można opłacić tylko „Przelewem bankowym” we Francji ze względu na wymagania ubezpieczenia przesyłki. Wybierasz rzeźbę, „Przelew bankowy” i „Francja”. Dla klientów spoza Francji inne metody płatności mogą być nadal dostępne dla tego produktu (jeśli nie obowiązują inne globalne zasady). |
| **Zapisz** | Ten przycisk zapisuje Twoje nowe lub zaktualizowane powiązanie produkt-płatność. | Zmiany są natychmiast stosowane w procesie realizacji zamówienia w Twoim sklepie. | Zawsze kliknij „Zapisz” po dokonaniu jakichkolwiek zmian. | Po ustawieniu zasad dla Twojego „Ebooka cyfrowego” klikasz „Zapisz”, aby je aktywować. |

### 2.3 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | (Nie wykryto żadnych konkretnych ustawień) | N/A | Ogólne informacje o module. |
| Powiązania płatności z produktami (Lista) | ID | N/A | Unikalny identyfikator powiązania. |
| Powiązania płatności z produktami (Lista) | Produkt | N/A | Nazwa produktu w powiązaniu. |
| Powiązania płatności z produktami (Lista) | Płatność | N/A | Nazwa metody płatności w powiązaniu. |
| Powiązania płatności z produktami (Lista) | Kraj | N/A | Kraj, dla którego obowiązuje ograniczenie (jeśli istnieje). |
| Powiązania płatności z produktami (Formularz dodawania/edycji) | ID Produktu | Wybierz produkt | Określa produkt, dla którego metody płatności zostaną ograniczone. |
| Powiązania płatności z produktami (Formularz dodawania/edycji) | Metody płatności | Wybierz wszystkie akceptowalne metody | Definiuje, które metody płatności są **dozwolone** dla wybranego produktu. |
| Powiązania płatności z produktami (Formularz dodawania/edycji) | Kraj | Pozostaw puste dla globalnego lub wybierz konkretny | Ogranicza ograniczenie do konkretnego kraju. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Ustawiłem ograniczenie, ale wszystkie metody płatności nadal wyświetlają się przy kasie. Co jest nie tak?**
O:

1. **Pamięć podręczna:** Zawsze wyczyść pamięć podręczną PrestaShop po wprowadzeniu zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
2. **Produkt w koszyku:** Upewnij się, że konkretny produkt, który ograniczyłeś, faktycznie znajduje się w koszyku klienta podczas testowania. Moduł stosuje zasady tylko wtedy, gdy produkt jest obecny.
3. **Włączona metoda płatności:** Sprawdź dwukrotnie, czy metody płatności, które *oczekujesz* zobaczyć, są faktycznie włączone w **Moduły > Płatność > Metody płatności**. Ten moduł filtruje *włączone* metody, sam ich nie włącza.
4. **Konfliktujące zasady:** Jeśli masz wiele produktów w koszyku, a każdy z nich ma ograniczenia, moduł wyświetli tylko te metody płatności, które są dozwolone przez *wszystkie* ograniczone produkty. Jeśli nie ma wspólnej dozwolonej metody, może się wydawać, że żadne metody nie są wyświetlane. Dokładnie przejrzyj swoje powiązania.

**P: Ustawiłem ograniczenie, a teraz ŻADNE metody płatności nie wyświetlają się przy kasie!**
O: Zazwyczaj dzieje się tak, jeśli:

1. **Brak wspólnych metod:** Masz wiele ograniczonych produktów w koszyku i nie ma metod płatności, które są dozwolone przez *wszystkie* z nich. Na przykład, Produkt A pozwala na PayPal, Produkt B pozwala na kartę kredytową. Jeśli oba są w koszyku, żadne z nich się nie wyświetli. Musisz upewnić się, że istnieje co najmniej jedna wspólna dozwolona metoda.
2. **Pusta lista dozwolonych:** Utworzyłeś powiązanie dla produktu, ale nie wybrałeś *żadnych* metod płatności jako dozwolonych. Moduł ukryje wtedy wszystkie metody dla tego produktu. Edytuj powiązanie i wybierz odpowiednie metody płatności.

**P: Czy ten moduł wpływa na metody płatności dla produktów, które NIE są w żadnym powiązaniu?**
O: Nie. Jeśli produkt nie jest częścią żadnego „Powiązania płatności z produktami”, nie nakłada żadnych ograniczeń. Moduł działa tylko na produkty, dla których wyraźnie zdefiniowałeś zasady. Jeśli koszyk zawiera tylko nieograniczone produkty, wszystkie standardowe włączone metody płatności Twojego sklepu zostaną wyświetlone.

**P: Jak ten moduł współdziała z innymi modułami ograniczeń płatności (np. według grupy klientów, według całkowitej kwoty)?**
O: Ten moduł zazwyczaj działa poprzez nadpisywanie podstawowej klasy PrestaShop `PaymentOptionsFinder` (jak widać w folderze `override`). Oznacza to, że ma pierwszeństwo lub integruje się na fundamentalnym poziomie. Ogólnie rzecz biorąc, zastosowana zostanie najbardziej restrykcyjna zasada. Jeśli inny moduł ogranicza metodę płatności, a ten moduł zezwala na nią dla produktu, metoda płatności prawdopodobnie nadal będzie ograniczona przez inny moduł. Kluczowe jest dokładne testowanie, jeśli używasz wielu modułów ograniczeń.

**P: Czy mogę ograniczyć metody płatności na podstawie kraju bez ograniczania ich według produktu?**
O: Główną funkcją tego modułu jest ograniczenie oparte na produkcie. Chociaż ma pole „Kraj”, dotyczy ono *powiązania produkt-płatność*. Jeśli potrzebujesz czysto krajowych ograniczeń płatności (niezależnie od produktu), możesz potrzebować oddzielnego modułu zaprojektowanego do tego celu lub sprawdzić, czy Twoje bramki płatności oferują bezpośrednie ograniczenia krajowe.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółową analizę techniczną modułu „Metody płatności według produktów” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł przede wszystkim rozszerza podstawowy mechanizm wykrywania opcji płatności w PrestaShop. Wykorzystuje `override` do modyfikacji klasy `PaymentOptionsFinder`, która jest odpowiedzialna za określanie dostępnych metod płatności podczas realizacji zamówienia. Pozwala to modułowi wstrzyknąć logikę filtrowania opartą na produkcie bezpośrednio do procesu pobierania opcji płatności, zapewniając bezproblemową integrację z przepływem realizacji zamówienia w PrestaShop.
Moduł stosuje standardowy wzorzec MVC PrestaShop dla zarządzania w Panelu administracyjnym, używając `AdminController` do zarządzania encją `pobp` (Powiązanie Produkt-Płatność).

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Funkcjonalność front-office modułu jest obsługiwana poprzez nadpisanie klasy podstawowej, a nie dedykowany kontroler front-office.
- **Kontrolery administracyjne Back-Office**:

  - `pobp/controllers/admin/AdminPobpController.php`
    - **Nazwa klasy i klasa nadrzędna**: `AdminPobpController` rozszerza `ModuleAdminController`.
    - **Nazwa zakładki**: Ten kontroler zarządza encją „Powiązania płatności z produktami”. Prawdopodobnie jest zarejestrowany jako podzakładka pod główną konfiguracją modułu.
    - **Odpowiedzialność**: Jest to główny kontroler CRUD (Create, Read, Update, Delete) dla powiązań produkt-płatność. Obsługuje:
      - Wyświetlanie listy istniejących powiązań (ID, Produkt, Płatność, Kraj).
      - Udostępnianie formularza do dodawania nowych powiązań lub edytowania istniejących.
      - Przetwarzanie przesłanych formularzy w celu zapisania nowych lub zaktualizowanych powiązań w bazie danych.
      - Obsługę usuwania powiązań.
      - Pola formularza „ID Produktu”, „Metody płatności” i „Kraj” są zarządzane tutaj.
  - `pobp/controllers/admin/index.php`
    - Ten plik jest zazwyczaj pustym miejscem lub zawiera podstawowe środki bezpieczeństwa (np. `<?php header("Expires: Mon, 26 Jul 1997 05:00:00 GMT"); header("Last-Modified: ".gmdate("D, d M Y H:i:s")." GMT"); header("Cache-Control: no-store, no-cache, must-revalidate"); header("Cache-Control: post-check=0, pre-check=0", false); header("Pragma: no-cache"); header("Location: ../"); exit;`). Nie reprezentuje on samej funkcjonalnej widoku kontrolera, ale zapewnia, że bezpośredni dostęp do katalogu `controllers/admin` jest przekierowywany.

### 4.3 Klasy podstawowe i modele (`classes/`)

- `pobp/override/classes/checkout/PaymentOptionsFinder.php`
  - **Cel**: Jest to krytyczny plik nadpisujący. Modyfikuje podstawową klasę PrestaShop odpowiedzialną za znajdowanie i zwracanie dostępnych opcji płatności podczas realizacji zamówienia.
  - **Nazwa klasy i klasa nadrzędna**: `PaymentOptionsFinder` (nadpisuje oryginalną klasę `PaymentOptionsFinder`).
  - **Kluczowa logika**: Nadpisana metoda `getPaymentOptions()` (lub podobna metoda) będzie zawierać podstawową logikę modułu.
    - Pobiera produkty aktualnie znajdujące się w koszyku klienta.
    - Dla każdego produktu sprawdza, czy w bazie danych modułu istnieją zdefiniowane „Powiązania płatności z produktami”.
    - Następnie filtruje początkowo dostępne opcje płatności (zwracane przez nadrzędną metodę `getPaymentOptions()`) na podstawie tych powiązań.
    - Logika filtrowania zapewnia, że zwracane są tylko metody płatności wyraźnie dozwolone dla *wszystkich* ograniczonych produktów w koszyku. Jeśli produkt nie ma powiązania, niczego nie ogranicza. Jeśli wiele produktów ma powiązania, używane jest przecięcie dozwolonych metod płatności.
  - **Interakcja z bazą danych**: Ta klasa będzie wysyłać zapytania do niestandardowej tabeli bazy danych modułu (prawdopodobnie `ps_pobp` lub podobnej), aby pobrać powiązania produkt-płatność.

### 4.4 Zasoby JavaScript (`views/js/`)

W dostarczonym inwentarzu nie wykryto żadnych konkretnych plików JavaScript. Wszelkie dynamiczne zachowania w Panelu administracyjnym (takie jak wyszukiwanie produktów w formularzu powiązania) są prawdopodobnie obsługiwane przez podstawowy JS PrestaShop lub minimalny skrypt inline.

### 4.5 Arkusze stylów CSS (`views/css/`)

W dostarczonym inwentarzu nie wykryto żadnych konkretnych plików CSS. Stylizacja formularzy i list w Panelu administracyjnym jest prawdopodobnie dziedziczona z domyślnego motywu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**: Brak wyraźnie wymienionych, ponieważ moduł działa poprzez nadpisanie, a nie bezpośrednie renderowanie hooków w front-office.
- **Szablony administracyjne (`views/templates/admin/`)**:
  - `pobp/lib/searchTool/views/scripts.tpl`
    - **Cel**: Ten szablon prawdopodobnie zawiera logikę JavaScript lub Smarty związaną z narzędziem wyszukiwania używanym w Panelu administracyjnym, być może do wyszukiwania produktów podczas tworzenia lub edytowania powiązania. Może zawierać wywołania AJAX lub dynamiczne filtrowanie do wyboru produktu.
- **Szablony front-office (`views/templates/front/`)**: Brak.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Moduł utworzy co najmniej jedną niestandardową tabelę podczas swojej metody `install()` (zdefiniowanej w `pobp/index.php`).
  - **`ps_pobp` (lub podobna nazwa, np. `ps_payment_by_product_association`)**:
    - Ta tabela przechowuje rzeczywiste powiązania produkt-płatność.
    - Oczekiwane kolumny:
      - `id_pobp` (klucz główny, INT)
      - `id_product` (INT, klucz obcy do `ps_product`)
      - `id_payment_module` (INT, klucz obcy do `ps_module` lub `ps_payment_module`, jeśli taka tabela istnieje, lub po prostu przechowuje nazwę/ID modułu)
      - `id_country` (INT, klucz obcy do `ps_country`, może być null dla zasad globalnych)
      - Inne potencjalne kolumny dla ustawień lub znaczników czasu.
  - Wartości konfiguracyjne (jeśli były obecne w `getContent()`) byłyby przechowywane w `ps_configuration`.
- **Tabela zarejestrowanych hooków**:
  Podstawowa funkcjonalność modułu opiera się na mechanizmie `override`, a nie na bezpośrednim wykonywaniu hooków dla jego głównego filtrowania. Jednak dla integracji z Panelu administracyjnym i potencjalnie dla przyszłych funkcji, może rejestrować standardowe hooki.

  | Nazwa hooka | Czas wykonania | Cel techniczny |
  | --- | --- | --- |
  | `displayAdminProductsExtra` | Na stronie edycji produktu w Panelu administracyjnym. | Może być używany do wyświetlania szybkiego linku lub podsumowania ograniczeń płatności dla bieżącego produktu. (Nie wykryto wyraźnie, ale jest to wspólny punkt integracji). |
  | `actionPaymentOptionsModifier` | Podczas procesu pobierania opcji płatności. | Ten hook jest specjalnie zaprojektowany dla modułów do modyfikowania listy opcji płatności. Nadpisanie `PaymentOptionsFinder` skutecznie osiąga podobny rezultat na niższym poziomie. |
  | `actionModuleInstall` | Podczas instalacji modułu. | Do tworzenia tabel bazy danych i rejestrowania niezbędnych hooków. |
  | `actionModuleUninstall` | Podczas deinstalacji modułu. | Do czyszczenia tabel bazy danych i wyrejestrowywania hooków. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i zapewnienia posiadania najnowszej kompatybilnej wersji modułu „Metody płatności według produktów”, prosimy o zapoznanie się z kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
