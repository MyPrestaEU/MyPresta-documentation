---
title: "Zmiana numeru faktury - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz dokumentacja deweloperska dla modułu PrestaShop „Zmiana numeru faktury” od MyPresta.eu."
sidebar:
  label: "Zmiana numeru faktury - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Invoice number change na MyPresta.eu](https://mypresta.eu/modules/administration-tools/invoice-number-change.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/invoice-number-change/)
>
> ---


# Zmiana numeru faktury

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji przejdź do **Moduły > Menedżer modułów** i wyszukaj „Zmiana numeru faktury”. Kliknij przycisk „Konfiguruj”.

Ten moduł nie posiada oddzielnego ekranu konfiguracji z wieloma ustawieniami. Jego funkcjonalność jest zintegrowana bezpośrednio ze stroną szczegółów zamówienia w Twoim Panelu administracyjnym. Przycisk „Konfiguruj” po prostu potwierdzi, że moduł jest zainstalowany i gotowy do użycia.

Główną funkcjonalnością tego modułu jest dodanie nowego pola lub zmodyfikowanie istniejącego wyświetlania na stronie szczegółów zamówienia, umożliwiając bezpośrednią edycję numeru faktury.

**Jak używać modułu:**

1.  **Przejdź do zamówienia:** W Panelu administracyjnym PrestaShop przejdź do **Zamówienia > Zamówienia**.
2.  **Wybierz zamówienie:** Kliknij dowolne zamówienie, aby wyświetlić jego szczegóły.
3.  **Znajdź sekcję faktur:** Przewiń stronę szczegółów zamówienia, aż znajdziesz sekcję „Dokumenty” lub „Faktury”.
4.  **Edytuj numer faktury:** Zobaczysz teraz edytowalne pole lub przycisk obok numeru faktury, który pozwala go zmienić.
    - **Co robi to ustawienie:** Ta funkcja pozwala bezpośrednio wpisać nowy numer faktury dla konkretnej faktury powiązanej z bieżącym zamówieniem.
    - **Efekt zmiany tego ustawienia:**
        - *Po wprowadzeniu nowego numeru i zapisaniu:* Numer faktury dla tej konkretnej faktury zamówienia zostanie zaktualizowany w Twojej bazie danych i odzwierciedlony w samym dokumencie faktury (jeśli zostanie ponownie wygenerowany lub wyświetlony). Ta zmiana jest trwała i wpływa na Twoje zapisy finansowe.
    - **Zalecana wartość:** Zmieniaj numery faktur tylko wtedy, gdy jest to absolutnie konieczne i zawsze dokładnie sprawdzaj poprawność. Upewnij się, że nowy numer jest zgodny z Twoim wewnętrznym schematem numeracji lub wymogami prawnymi.
    - **Scenariusz/przykład dla sprzedawcy:** Zamówienie zostało początkowo zafakturowane jako INV00123. Z powodu migracji danych, potrzebujesz, aby ta faktura miała numer INV2024-005. Przejdziesz do zamówienia, znajdziesz INV00123, klikniesz, aby edytować, wpiszesz INV2024-005 i zapiszesz.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona szczegółów zamówienia (sekcja Dokumenty/Faktury) | Numer faktury (pole edytowalne) | N/A (zależy od istniejącej faktury) | Umożliwia bezpośrednią modyfikację numeru faktury dla konkretnego zamówienia. Kluczowe dla korekt, zgodności lub integracji z systemami zewnętrznymi. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Zainstalowałem moduł, ale nie widzę żadnej nowej strony ustawień. Czy działa?**
O1: Tak, moduł działa zgodnie z przeznaczeniem. Ten moduł nie dodaje oddzielnej strony konfiguracji. Jego funkcjonalność jest zintegrowana bezpośrednio ze stroną szczegółów zamówienia. Przejdź do **Zamówienia > Zamówienia**, wybierz zamówienie, a w sekcji „Dokumenty” lub „Faktury” powinieneś znaleźć edytowalne pole lub opcję zmiany numeru faktury.

**P2: Zmieniłem numer faktury, ale stary numer nadal pojawia się na fakturze PDF.**
O2: Po zmianie numeru faktury w Panelu administracyjnym, może być konieczne ponowne wygenerowanie faktury PDF dla tego zamówienia, aby odzwierciedlić nowy numer. PrestaShop często buforuje zawartość PDF. Pobierz fakturę ponownie ze strony szczegółów zamówienia, a powinna wyświetlić zaktualizowany numer.

**P3: Czy mogę cofnąć zmianę numeru faktury?**
O3: Moduł pozwala zmienić numer na dowolny, jaki sobie życzysz. Jeśli chcesz cofnąć zmianę, po prostu ponownie edytuj pole i wprowadź oryginalny numer (jeśli go pamiętasz lub masz go zanotowanego). Moduł sam w sobie nie przechowuje historii zmian, dlatego zaleca się staranne prowadzenie dziennika.

**P4: Czy zmiana numeru faktury wpłynie na moje raporty księgowe w PrestaShop?**
O4: Tak, zmiana numeru faktury zaktualizuje pole `invoice_number` w Twojej bazie danych dla tej konkretnej faktury. Wszelkie raporty PrestaShop, które pobierają numery faktur bezpośrednio z bazy danych, będą odzwierciedlać nowy numer. Upewnij się, że Twoje zmiany są zgodne z Twoimi praktykami księgowymi.

**P5: Moduł wydaje się nieaktywny w moim niestandardowym motywie. Co powinienem zrobić?**
O5: Ten moduł wykorzystuje system nadpisywania PrestaShop do modyfikowania podstawowego zachowania i włącza się w standardowe szablony administracyjne. Powinien działać z większością niestandardowych motywów bez problemów, ponieważ wpływa tylko na Panel administracyjny. Jeśli napotkasz problemy, najpierw wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**). Jeśli problem nadal występuje, może to być konflikt z innym modułem lub wysoce dostosowanym szablonem administracyjnym. Skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojego motywu i wszelkich innych istotnych modułów.

## 4. Przewodnik dla deweloperów i webmasterów (architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Zmiana numeru faktury” (`invoicenb`) został zaprojektowany w celu rozszerzenia podstawowej funkcjonalności zarządzania fakturami w PrestaShop bez zmiany schematu bazy danych. Osiąga to głównie poprzez `override` klasy `OrderInvoice` i podłączenie się do strony szczegółów zamówienia w Panelu administracyjnym, aby zapewnić edytowalny interfejs dla numeru faktury. Takie podejście zapewnia minimalny wpływ na podstawowy system, jednocześnie dostarczając pożądaną funkcję.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Cała funkcjonalność jest zintegrowana za pośrednictwem głównego pliku modułu, nadpisań i hooków szablonów.

### 4.3 Klasy i modele podstawowe (`classes/`)

-   **`invoicenb/override/classes/order/OrderInvoice.php`**
    -   **Nazwa klasy**: `OrderInvoice` (nadpisuje podstawową klasę `OrderInvoice`)
    -   **Klasa nadrzędna**: `OrderInvoiceCore`
    -   **Odpowiedzialność**: To nadpisanie jest rdzeniem funkcjonalności modułu. Modyfikuje zachowanie klasy `OrderInvoice`, w szczególności sposób obsługi i potencjalnego zapisywania numerów faktur. Nadpisanie jest odpowiedzialne za umożliwienie aktualizacji numeru faktury z Panelu administracyjnego. Prawdopodobnie dodaje lub modyfikuje metodę ułatwiającą zapisanie nowego numeru faktury po przesłaniu go za pośrednictwem interfejsu administratora.
    -   **Tabela bazy danych**: `ps_order_invoice` (lub Twój prefiks tabeli)
    -   **Pola `$definition`**: To nadpisanie działa z istniejącą `$definition` `OrderInvoiceCore`, w szczególności z polem `number`.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Funkcjonalność interaktywnej edycji jest obsługiwana bezpośrednio w szablonach Smarty i potencjalnie poprzez standardowe mechanizmy AJAX PrestaShop, jeśli involved jest przesyłanie formularza.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł nie zawiera żadnych niestandardowych plików CSS. Stylizacja edytowalnego pola lub przycisku na stronie zamówienia będzie opierać się na domyślnym CSS Panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł używa szablonów do wstrzyknięcia edytowalnego pola numeru faktury na stronę szczegółów zamówienia w Panelu administracyjnym.

-   **Szablony hooków (`views/templates/hook/`)**:
    -   **`invoicenb/views/templates/hook/displayAdminOrder16.tpl`**
        -   **Hook**: `displayAdminOrder` (dla PrestaShop 1.6.x)
        -   **Cel**: Ten szablon jest renderowany na stronie szczegółów zamówienia w PrestaShop 1.6.x. Wstrzykuje elementy formularza HTML (np. pole wejściowe i przycisk zapisu), które umożliwiają administratorowi przeglądanie i modyfikowanie numeru faktury dla konkretnego zamówienia. Prawdopodobnie zawiera logikę wyświetlania bieżącego numeru faktury i obsługi przesyłania nowego.
    -   **`invoicenb/views/templates/hook/displayAdminOrder17.tpl`**
        -   **Hook**: `displayAdminOrder` (dla PrestaShop 1.7.x, 8.x, 9.x)
        -   **Cel**: Podobnie jak `displayAdminOrder16.tpl`, ale dostosowany do struktury szablonów i potencjalnie różnych parametrów hooków PrestaShop 1.7.x i nowszych wersji. Zapewnia tę samą funkcjonalność: wyświetlanie edytowalnego pola numeru faktury na stronie szczegółów zamówienia.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy żadnych nowych niestandardowych tabel bazy danych. Współpracuje z istniejącą tabelą `ps_order_invoice` (lub Twoim prefiksem tabeli) w celu aktualizacji kolumny `number`.
    -   Rekordy konfiguracji są przechowywane w `ps_configuration` dla wewnętrznych ustawień modułu (jeśli takie istnieją, choć ten moduł wydaje się mieć minimalne jawne ustawienia).
-   **Tabela zarejestrowanych hooków**:

    | Nazwa hooka | Czas wykonania | Cel techniczny |
    | --- | --- | --- |
    | `displayAdminOrder` | Renderuje zawartość na stronie szczegółów zamówienia w Panelu administracyjnym. | Używany do wstrzyknięcia formularza HTML do edycji numeru faktury bezpośrednio w widoku zamówienia. Moduł dostarcza oddzielne szablony dla PrestaShop 1.6 i 1.7+ dla tego hooka. |
    | `actionObjectOrderInvoiceUpdateAfter` | Wykonywany po zaktualizowaniu obiektu `OrderInvoice`. | (Niejawne, jeśli nadpisanie tego używa) Może być używany do wyzwalania dodatkowych działań lub logowania po pomyślnej zmianie numeru faktury. |
    | `actionObjectOrderInvoiceAddAfter` | Wykonywany po dodaniu obiektu `OrderInvoice`. | (Niejawne, jeśli nadpisanie tego używa) Może być używany do modyfikowania początkowego numeru faktury po utworzeniu, chociaż główny nacisk kładziony jest na zmianę istniejących. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Zmiana numeru faktury”, zapoznaj się ze swoim kontem klienta MyPresta.eu. Możesz pobrać najnowsze wersje z historii zamówień i uzyskać dostęp do naszych dedykowanych kanałów wsparcia w przypadku jakiejkolwiek pomocy technicznej lub zapytań.
