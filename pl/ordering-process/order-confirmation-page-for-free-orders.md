---
title: "Strona potwierdzenia zamówienia dla darmowych zamówień - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Strona potwierdzenia zamówienia dla darmowych zamówień” od MyPresta.eu."
sidebar:
  label: "Strona potwierdzenia zamówienia dla darmowych zamówień - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Order confirmation page for free orders na MyPresta.eu](https://mypresta.eu/modules/ordering-process/order-confirmation-page-for-free-orders.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/order-confirmation-page-for-free-orders/)
>
> ---


# Strona potwierdzenia zamówienia dla darmowych zamówień

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Strona potwierdzenia zamówienia dla darmowych zamówień)

Jest to główny i jedyny ekran konfiguracji modułu. Jest prosty i pozwala włączyć lub wyłączyć podstawową funkcjonalność modułu.

![Zastępczy zrzut ekranu konfiguracji modułu]

- **Włącz stronę potwierdzenia zamówienia**
  - **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji funkcjonalności modułu. Kontroluje, czy darmowe zamówienia wyświetlają standardową stronę potwierdzenia, czy wracają do domyślnego zachowania PrestaShop (przekierowanie do historii zamówień).
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (wybrane „Włączone”):* Wszystkie zamówienia, w tym te o łącznej wartości 0,00 €, będą wyświetlać standardową stronę „Potwierdzenie zamówienia” po zakończeniu realizacji zamówienia.
    - *Gdy wyłączone (wybrane „Wyłączone”):* Darmowe zamówienia powrócą do domyślnego zachowania PrestaShop, przekierowując klientów bezpośrednio do ich historii zamówień zamiast wyświetlać stronę potwierdzenia.
  - **Zalecana wartość:** **Włączone**. Jest to główny cel modułu i zapewnia lepsze doświadczenie klienta.
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli oferujesz darmowy e-book do pobrania, włączenie tej opcji zapewnia, że klienci zobaczą stronę potwierdzenia z linkiem do pobrania, zamiast być zdezorientowanymi bezpośrednim przekierowaniem do historii zamówień. Jeśli tymczasowo chcesz wrócić do domyślnego zachowania PrestaShop dla darmowych zamówień (np. do konkretnych testów), możesz to wyłączyć.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Włącz stronę potwierdzenia zamówienia | Włączone | Kontroluje, czy darmowe zamówienia wyświetlają standardową stronę potwierdzenia zamówienia (Włączone) czy przekierowują do historii zamówień (Wyłączone). |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje darmowe zamówienia nadal przekierowują do strony historii zamówień, nawet po włączeniu modułu. Co powinienem zrobić?**
O:

1. **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Strona potwierdzenia zamówienia dla darmowych zamówień” jest zainstalowana i włączona.
2. **Sprawdź konfigurację modułu:** Przejdź do **Moduły > Menedżer modułów > Konfiguruj** dla tego modułu i upewnij się, że ustawienie „Włącz stronę potwierdzenia zamówienia” jest ustawione na **„Włączone”**.
3. **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Jest to często konieczne po zmianach konfiguracji modułu.
4. **Pamięć podręczna przeglądarki:** Spróbuj wyczyścić pamięć podręczną przeglądarki lub przetestować w oknie incognito/prywatnym, aby wykluczyć problemy z lokalną pamięcią podręczną.

**P: Czy ten moduł wpłynie na moje płatne zamówienia?**
O: Nie, ten moduł dotyczy konkretnie zachowania zamówień o łącznej wartości 0,00 €. Płatne zamówienia będą nadal wyświetlać standardową stronę potwierdzenia zamówienia, tak jak zawsze.

**P: Czy ten moduł wymaga specjalnych modyfikacji szablonu?**
O: Nie, moduł działa poprzez nadpisanie podstawowego kontrolera PrestaShop. Wykorzystuje istniejący szablon strony potwierdzenia zamówienia Twojego motywu. Nie są wymagane żadne modyfikacje motywu. Jeśli Twoja strona potwierdzenia zamówienia wygląda dobrze dla płatnych zamówień, będzie wyglądać dobrze również dla darmowych zamówień.

**P: Co jeśli chcę wyświetlać inną zawartość na stronie potwierdzenia dla darmowych zamówień niż dla płatnych zamówień?**
O: Ten moduł zapewnia wyświetlanie *tej samej* strony potwierdzenia. Aby wyświetlać inną zawartość, musiałbyś dostosować swój szablon `order-confirmation.tpl` (zazwyczaj znajdujący się w `themes/your-theme/templates/checkout/`), aby zawierał logikę warunkową opartą na łącznej kwocie zamówienia lub metodzie płatności. Wymagałoby to pomocy programisty.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych, które utrzymują lub rozszerzają sklep.

### 4.1 Przegląd architektury

Moduł „Strona potwierdzenia zamówienia dla darmowych zamówień” osiąga swoją funkcjonalność poprzez nadpisanie podstawowego kontrolera front-office PrestaShop. W szczególności, celuje w `OrderConfirmationController`, aby zmodyfikować logikę przekierowania, która następuje po złożeniu darmowego zamówienia. Jest to standardowy mechanizm nadpisywania PrestaShop, zapewniający minimalny wpływ na pliki rdzenia i umożliwiający łatwe odinstalowanie.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:
  - `freeorderconfirmation/override/controllers/front/index.php`
    - Ten plik jest zastępczy lub artefaktem procesu nadpisywania. W PrestaShop 1.7+ nadpisywanie jest zazwyczaj obsługiwane przez umieszczenie nadpisanej klasy bezpośrednio w katalogu `override/classes` lub `override/controllers`, a autoloader PrestaShop zajmuje się resztą. Sam ten plik `index.php` nie zawiera definicji klasy ani bezpośredniej logiki funkcjonalności modułu. Jego obecność zapewnia, że mechanizm nadpisywania jest poprawnie wyzwalany dla `OrderConfirmationController`.
  - `freeorderconfirmation/override/controllers/front/OrderConfirmationController.php`
    - **Nazwa klasy i klasa nadrzędna**: `OrderConfirmationController` (nadpisuje podstawową klasę `OrderConfirmationController`).
    - **Odpowiedzialność**: To jest rdzeń funkcjonalności modułu. Nadpisuje metodę `initContent()` (lub podobną logikę w cyklu życia kontrolera) oryginalnego `OrderConfirmationController`. Oryginalna logika PrestaShop sprawdza, czy łączna kwota zamówienia wynosi zero i, jeśli tak, przekierowuje klienta do jego historii zamówień. Ten nadpisany kontroler usuwa lub modyfikuje to warunkowe przekierowanie, zapewniając, że standardowa metoda `initContent()` `OrderConfirmationController` (która renderuje stronę potwierdzenia) jest zawsze wykonywana, nawet dla darmowych zamówień. Skutecznie zapobiega wywołaniu `Tools::redirect()` dla zamówień o wartości zerowej.

### 4.3 Klasy rdzenia i modele (`classes/`)

W tym module nie ma niestandardowych klas ani definicji `ObjectModel`. Moduł działa wyłącznie poprzez nadpisanie podstawowego kontrolera PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera niestandardowych plików CSS. Moduł opiera się na istniejącym stylu motywu dla strony potwierdzenia zamówienia.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie zawiera niestandardowych plików szablonów Smarty. Moduł zapewnia, że *standardowy* szablon potwierdzenia zamówienia PrestaShop (zazwyczaj `themes/your-theme/templates/checkout/order-confirmation.tpl`) jest renderowany dla darmowych zamówień, tak samo jak dla płatnych zamówień.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Przechowuje swoje ustawienia konfiguracyjne (np. `freeorderconfirmation_oc`) w tabeli `ps_configuration`.
  - Przechowuje również `mypresta_updates`, `update_`, `updatev_` do wewnętrznego śledzenia aktualizacji przez MyPresta.eu.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje media (CSS/JS). | Używany przez moduł do potencjalnego włączenia własnych zasobów dla strony konfiguracji w panelu administracyjnym. W przypadku tego modułu, prawdopodobnie służy do zapewnienia poprawnego renderowania formularza konfiguracji modułu w interfejsie administracyjnym PrestaShop, nawet jeśli żadne niestandardowe zasoby nie są jawnie ładowane. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i wsparcie techniczne, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół jest dostępny, aby pomóc w wszelkich problemach lub pytaniach dotyczących modułu „Strona potwierdzenia zamówienia dla darmowych zamówień”.
