---
title: "Order reference change free - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop „Order reference change free” od MyPresta.eu."
sidebar:
  label: "Order reference change free - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Order reference change free na MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-reference-change-free.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/order-reference-change-free/)
>
> ---


# Order reference change free

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Brak specjalnych wymagań poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Order reference change free”. Zostanie wyświetlony główny ekran konfiguracji.

#### **Format referencji zamówienia**

Jest to kluczowe ustawienie modułu, pozwalające zdefiniować wzorzec dla numerów referencyjnych zamówień.

-   **Co robi to ustawienie:** To pole wejściowe pozwala określić szablon, według którego będą generowane nowe numery referencyjne zamówień. Możesz użyć kombinacji znaków specjalnych i symboli zastępczych, aby stworzyć pożądany format.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po ustawieniu na określony format (np. `[0-9]{6}`):* Wszystkie nowe zamówienia otrzymają numer referencyjny, który ściśle przestrzega tego wzorca. Na przykład, `[0-9]{6}` wygenerowałoby 6-cyfrowy numer referencyjny, taki jak `123456`.
    -   *Po pozostawieniu domyślnego (domyślne zachowanie PrestaShop):* Moduł nie zmieni generowania referencji zamówienia, a PrestaShop użyje swojego standardowego formatu alfanumerycznego (np. `ABCDEF123`).
-   **Zalecana wartość:** Zależy to całkowicie od potrzeb Twojej firmy.
    -   Jeśli potrzebujesz prostego, wyłącznie numerycznego numeru referencyjnego, spróbuj `[0-9]{6}` dla 6-cyfrowego numeru.
    -   Jeśli chcesz mieszankę wielkich liter i cyfr, `[A-Z0-9]{8}` da Ci 8-znakowy numer referencyjny alfanumeryczny.
    -   Możesz również uwzględnić statyczne prefiksy, np. `MYSTORE-[0-9]{5}` wygenerowałoby `MYSTORE-12345`.
-   **Scenariusz/przykład dla sprzedawcy:**
    -   **Scenariusz 1: Wyłącznie numeryczne referencje dla księgowości.** Twoje oprogramowanie księgowe wymaga, aby wszystkie referencje zamówień były wyłącznie numeryczne i miały 8 cyfr. Ustawisz to na `[0-9]{8}`.
    -   **Scenariusz 2: Krótsze, łatwe do zapamiętania referencje.** Chcesz krótszych, 6-znakowych referencji używających tylko wielkich liter i cyfr dla łatwiejszej komunikacji z klientami. Ustawisz to na `[A-Z0-9]{6}`.
    -   **Scenariusz 3: Referencje z marką.** Chcesz, aby wszystkie referencje zaczynały się od inicjału Twojej marki, a następnie 5-cyfrowego numeru. Ustawisz to na `M-[0-9]{5}`.

**Dostępne symbole zastępcze i znaki:**
Moduł używa składni podobnej do wyrażeń regularnych do definiowania formatu:

-   `[0-9]`: Reprezentuje dowolną pojedynczą cyfrę od 0 do 9.
-   `[a-z]`: Reprezentuje dowolną pojedynczą małą literę od a do z.
-   `[A-Z]`: Reprezentuje dowolną pojedynczą wielką literę od A do Z.
-   `[a-zA-Z]`: Reprezentuje dowolną pojedynczą literę (wielką lub małą).
-   `[A-Z0-9]`: Reprezentuje dowolną pojedynczą wielką literę lub cyfrę.
-   `{n}`: Określa, że poprzedzający znak lub grupa powinna być powtórzona dokładnie `n` razy. Na przykład, `[0-9]{6}` oznacza 6 cyfr.
-   `{n,m}`: Określa, że poprzedzający znak lub grupa powinna być powtórzona od `n` do `m` razy.
-   Każdy inny znak (np. `-`, `_`, `MYSTORE-`) zostanie dosłownie uwzględniony w referencji.

**Ważna uwaga:** Moduł zapewnia unikalność generowanej referencji. Jeśli wygenerowana referencja już istnieje, spróbuje wygenerować nową, aż znajdzie unikalną referencję.

#### **Przycisk Zapisz**

-   **Co robi to ustawienie:** Ten przycisk zapisuje wszystkie zmiany wprowadzone na stronie konfiguracji.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po kliknięciu:* Twój nowy format referencji zamówienia zostanie natychmiast zastosowany do wszystkich *nowych* zamówień złożonych w Twoim sklepie. Istniejące referencje zamówień nie zostaną zmienione.
-   **Zalecana wartość:** Zawsze kliknij „Zapisz” po wprowadzeniu jakichkolwiek zmian, aby upewnić się, że zostały zastosowane.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Format referencji zamówienia | Domyślny PrestaShop (alfanumeryczny) | Definiuje wzorzec dla nowych numerów referencyjnych zamówień (np. `[0-9]{6}`, `MYSTORE-[A-Z0-9]{5}`). Wpływa na sposób odwoływania się do nowych zamówień w Twoim sklepie i na dokumentach klienta. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zmieniłem format, ale stare zamówienia nadal mają starą referencję. Dlaczego?**
O: Ten moduł dotyczy tylko *nowych* zamówień złożonych po zapisaniu konfiguracji. Nie zmienia on wstecznie istniejących referencji zamówień, ponieważ mogłoby to spowodować niespójności danych z poprzednimi zapisami, fakturami i komunikacją z klientami.

**P: Moje nowe referencje zamówień nie są zgodne z ustawionym przeze mnie formatem.**
O:

1.  **Czy kliknąłeś „Zapisz”?** Upewnij się, że kliknąłeś przycisk „Zapisz” po wprowadzeniu zmian na stronie konfiguracji modułu.
2.  **Sprawdź składnię formatu:** Dokładnie sprawdź ciąg `Format referencji zamówienia` pod kątem literówek lub nieprawidłowych znaków. Zapoznaj się z sekcją „Dostępne symbole zastępcze i znaki” powyżej.
3.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe zastosowanie zmian. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
4.  **Konflikty modułów:** Chociaż rzadkie, inny moduł, który mocno modyfikuje proces zamówienia, może powodować konflikt. Spróbuj tymczasowo wyłączyć inne ostatnio zainstalowane moduły, aby sprawdzić, czy problem zostanie rozwiązany.

**P: Czy mogę skrócić lub wydłużyć referencję zamówienia?**
O: Tak, absolutnie! Użyj składni `{n}` lub `{n,m}`, aby określić dokładną długość lub zakres. Na przykład, `[0-9]{4}` dla 4-cyfrowego numeru lub `[A-Z0-9]{10}` dla 10-znakowego numeru alfanumerycznego.

**P: Co się stanie, jeśli moduł wygeneruje referencję, która już istnieje?**
O: Moduł jest zaprojektowany tak, aby zapewnić unikalność. Jeśli wygeneruje referencję, która jest już używana, automatycznie spróbuje wygenerować inną, aż znajdzie unikalną referencję. Ten proces jest zazwyczaj natychmiastowy i zapewnia, że żadne dwa zamówienia nie mają tej samej referencji.

**P: Czy ten moduł wpływa na SEO lub wydajność mojego sklepu?**
O: Nie, ten moduł działa wyłącznie na logice backendu generowania referencji zamówień. Nie ma bezpośredniego wpływu na SEO Twojego sklepu ani wydajność front-office.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Order reference change free” osiąga swoją funkcjonalność poprzez nadpisanie podstawowej klasy `Order` PrestaShop. Zamiast bezpośrednio podłączać się do słuchaczy zdarzeń, modyfikuje domyślne zachowanie metody `Order::generateReference()`, która jest odpowiedzialna za tworzenie unikalnej referencji zamówienia. Takie podejście zapewnia, że niestandardowa logika generowania referencji jest stosowana za każdym razem, gdy tworzone jest nowe zamówienie, niezależnie od konkretnego przepływu front-office.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   **`refchange/override/classes/order/Order.php`**
    -   **Cel**: Ten plik zawiera nadpisanie podstawowej klasy `Order` PrestaShop. Jego główną funkcją jest zastąpienie domyślnej metody `generateReference()` niestandardową logiką, która stosuje format zdefiniowany w konfiguracji modułu.
    -   **Klasa nadrzędna**: Rozszerza `OrderCore`.
    -   **Kluczowe metody**:
        -   `generateReference()`: Ta nadpisana metoda jest sercem modułu.
            -   Pobiera niestandardowy format referencji z `Configuration::get('REFCHANGE_FORMAT')`.
            -   Jeśli zdefiniowano niestandardowy format, używa pętli do generowania ciągu referencji na podstawie skonfigurowanego wzorca (używając `preg_match` i `rand` do wyboru znaków).
            -   Następnie sprawdza tabelę `ps_orders`, aby upewnić się, że wygenerowana referencja jest unikalna. Jeśli nie jest unikalna, generuje ponownie, aż znajdzie unikalną.
            -   Jeśli nie zdefiniowano niestandardowego formatu, wraca do metody `OrderCore::generateReference()` klasy nadrzędnej.
    -   **Interakcja z bazą danych**: Współdziała z tabelą `ps_orders` w celu sprawdzenia istniejących referencji.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie zawiera żadnych niestandardowych plików szablonów Smarty. Interfejs konfiguracji jest renderowany bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    -   `ps_configuration`: Przechowuje ustawienie konfiguracji modułu:
        -   `REFCHANGE_FORMAT`: Ciąg niestandardowego formatu referencji zamówienia (np. `[0-9]{6}`).
-   **Tabela zarejestrowanych hooków**:
    Ten moduł nie rejestruje jawnie żadnych hooków w tabeli `ps_hook_module`. Jego funkcjonalność jest zaimplementowana poprzez nadpisanie klasy, co oznacza, że modyfikuje on bezpośrednio podstawowe zachowanie, zamiast reagować na konkretne zdarzenia hooków.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Order reference change free”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu). Nasz zespół dba o to, aby moduł działał optymalnie z Twoim sklepem PrestaShop.
"""
