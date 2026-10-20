---
title: "Zmiana daty faktury - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dotyczące modułu PrestaShop „Zmiana daty faktury” od MyPresta.eu."
sidebar:
  label: "Zmiana daty faktury - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Invoice date change na MyPresta.eu](https://mypresta.eu/modules/administration-tools/invoice-date-change.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/invoice-date-change/)
>
> ---


# Zmiana daty faktury

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Zmiana daty faktury”. Spowoduje to przejście do głównego ekranu konfiguracji.

Na tym ekranie znajdziesz podstawową funkcjonalność modułu, która pozwala ustawić żądaną datę faktury dla zamówienia.

**Jak używać:**

1. **Przejdź do zamówienia:**
   - Przejdź do **Zamówienia > Zamówienia** w Panelu administracyjnym PrestaShop.
   - Kliknij istniejące zamówienie, aby wyświetlić jego szczegóły.
2. **Znajdź sekcję daty faktury:**
   - Na stronie szczegółów zamówienia przewiń w dół. Znajdziesz nową sekcję lub blok związany ze „Zmianą daty faktury”.
   - Ta sekcja zazwyczaj pojawi się w bloku „Dokumenty” lub podobnym obszarze, w którym zarządzane są faktury.
3. **Wybierz żądaną datę:**
   - Zobaczysz pole wyboru daty. Kliknij to pole, aby otworzyć kalendarz.
   - Wybierz dokładną datę, która ma pojawić się na fakturze. Może to być data przeszła lub przyszła.
4. **Zapisz zmiany:**
   - Po wybraniu daty w tej sekcji pojawi się przycisk „Zapisz” lub „Aktualizuj”. Kliknij go, aby zastosować nową datę faktury do zamówienia.
5. **Wygeneruj lub ponownie wygeneruj fakturę:**
   - Po zapisaniu daty, jeśli wygenerujesz nową fakturę dla tego zamówienia (lub ponownie wygenerujesz istniejącą), plik PDF będzie odzwierciedlał właśnie ustawioną datę.

**Co robi to ustawienie:** Ten moduł nie ma globalnego przełącznika „włącz/wyłącz” ani złożonych ustawień. Jego główną funkcją jest wstrzyknięcie selektora daty bezpośrednio na strony szczegółów zamówienia w Panelu administracyjnym. Ten selektor daty pozwala ręcznie nadpisać domyślną datę generowania faktury dla poszczególnych zamówień.

**Efekt zmiany tego ustawienia:**

- *Po wybraniu daty i zapisaniu:* Wybrana data jest przechowywana dla tego konkretnego zamówienia. Każda faktura wygenerowana dla tego zamówienia *po* ustawieniu tej daty będzie używać wybranej daty zamiast bieżącej daty systemowej.
- *Gdy nie używasz selektora daty modułu:* PrestaShop będzie nadal generować faktury z bieżącą datą, tak jak robi to domyślnie.

**Zalecana wartość:** Użyj selektora daty, aby wybrać dokładną datę wymaganą dla każdej konkretnej faktury. Nie ma globalnej „zalecanej wartości”, ponieważ data będzie się różnić w zależności od zamówienia.

**Scenariusz / przykład dla sprzedawcy:**
Wyobraź sobie, że klient złożył zamówienie 15 stycznia, ale z powodu opóźnienia w magazynie produkt został wysłany i zafakturowany dopiero 25 stycznia. Jednak do celów księgowych potrzebujesz, aby data faktury odzwierciedlała pierwotną datę zamówienia, czyli 15 stycznia.

1. Przechodzisz do strony szczegółów tego konkretnego zamówienia.
2. W sekcji „Zmiana daty faktury” otwierasz kalendarz i wybierasz 15 stycznia.
3. Klikasz „Zapisz”.
4. Teraz, gdy wygenerujesz fakturę PDF dla tego zamówienia, wyświetli ona „15 stycznia” jako datę faktury, mimo że wygenerowałeś ją 25 stycznia.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona szczegółów zamówienia (Panel administracyjny) | Selektor daty (w sekcji „Zmiana daty faktury”) | Różni się w zależności od zamówienia | Umożliwia ręczny wybór daty wystawienia faktury dla konkretnego zamówienia. Wybrana data pojawi się na wygenerowanej fakturze PDF, nadpisując domyślną bieżącą datę. |
| Strona szczegółów zamówienia (Panel administracyjny) | Przycisk Zapisz/Aktualizuj | N/A | Stosuje wybraną datę faktury do bieżącego zamówienia. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zmieniłem datę, ale faktura nadal pokazuje starą datę. Co jest nie tak?**
O: Upewnij się, że kliknąłeś przycisk „Zapisz” lub „Aktualizuj” po wybraniu nowej daty na stronie szczegółów zamówienia. Upewnij się również, że generujesz *nową* fakturę lub *ponownie generujesz* istniejącą *po* zapisaniu nowej daty. Jeśli przeglądasz już pobrany plik PDF, nie zaktualizuje się on magicznie. Musisz pobrać go ponownie.

**P: Selektor daty nie pojawia się na mojej stronie zamówienia.**
O:

1. **Sprawdź instalację modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Zmiana daty faktury” jest zainstalowany i włączony.
2. **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami PrestaShop potrzebuje odświeżenia pamięci podręcznej, aby wyświetlić nowe elementy modułu.
3. **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany do bezproblemowej integracji, bardzo mocno dostosowane motywy mogą czasami zakłócać jego działanie. Jeśli wyczyszczenie pamięci podręcznej nie pomoże, tymczasowo przełącz się na domyślny motyw PrestaShop, aby sprawdzić, czy selektor daty się pojawi. Jeśli tak, Twój motyw może wymagać niewielkiej korekty.

**P: Czy mogę zmienić datę dla wielu faktur jednocześnie?**
O: Nie, ten moduł jest przeznaczony do indywidualnych zmian daty faktury dla zamówienia. Musisz przejść do strony szczegółów każdego zamówienia, aby ustawić jego konkretną datę faktury. Nie ma funkcji edycji masowej.

**P: Czy ten moduł wpływa na inne daty w PrestaShop, takie jak data zamówienia lub data płatności?**
O: Nie, ten moduł zmienia *tylko* datę wystawienia, która pojawia się na wygenerowanej fakturze PDF. Nie zmienia daty utworzenia zamówienia, daty płatności ani żadnych innych znaczników czasu związanych z zamówieniem w Twojej bazie danych.

**P: Czy ten moduł będzie działał z moim niestandardowym szablonem faktury?**
O: Tak, moduł wstrzykuje wybraną datę do standardowego procesu generowania faktur PrestaShop. Tak długo, jak Twój niestandardowy szablon faktury poprawnie używa standardowych zmiennych dla daty faktury, powinien wyświetlać datę ustawioną przez moduł.

## 4. Przewodnik dla programistów i webmasterów (architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Zmiana daty faktury” to lekki moduł PrestaShop, zaprojektowany przede wszystkim do rozszerzania funkcjonalności zarządzania zamówieniami w Panelu administracyjnym. Wykorzystuje system hooków PrestaShop do wstrzykiwania niestandardowego pola wprowadzania daty na stronę szczegółów zamówienia. Gdy nowa data zostanie wybrana i zapisana, aktualizuje pole `invoice_date` obiektu `OrderInvoice`, zapewniając, że kolejne generowanie faktur PDF odzwierciedla datę zdefiniowaną przez użytkownika. Przyjmuje proste, bezpośrednie podejście bez złożonych struktur MVC lub niestandardowych tabel baz danych, opierając się na istniejących podstawowych funkcjonalnościach PrestaShop.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Cała logika jest obsługiwana w głównym pliku modułu (`invoicedate/index.php`) i poprzez system hooków PrestaShop.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas ani modeli w katalogu `classes/`. Bezpośrednio współdziała z podstawowym obiektem `OrderInvoice` i jego właściwościami.

### 4.4 Zasoby JavaScript (`views/js/`)

W tym module nie ma niestandardowych plików JavaScript. Funkcjonalność selektora daty jest zazwyczaj dostarczana przez podstawowe biblioteki JavaScript PrestaShop (np. jQuery UI Datepicker), które są już załadowane w Panelu administracyjnym.

### 4.5 Arkusze stylów CSS (`views/css/`)

W tym module nie ma niestandardowych plików CSS. Stylizacja selektora daty i otaczających elementów opiera się na domyślnym CSS Panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa dwóch konkretnych szablonów do wyświetlania pola wprowadzania daty na stronie szczegółów zamówienia, w zależności od wersji PrestaShop.

- **Szablony hooków (`views/templates/hook/`)**:
  - `invoicedate/views/templates/hook/displayAdminOrder16.tpl`
    - **Hook**: Ten szablon jest renderowany w hooku `displayAdminOrder`, specjalnie dla wersji PrestaShop 1.6.x.
    - **Cel**: Wyświetla strukturę HTML dla pola wprowadzania daty faktury (selektora daty) i przycisku przesyłania na stronie szczegółów zamówienia w Panelu administracyjnym PrestaShop 1.6. Umożliwia administratorowi wybranie i zapisanie niestandardowej daty faktury dla bieżącego zamówienia.
  - `invoicedate/views/templates/hook/displayAdminOrder17.tpl`
    - **Hook**: Ten szablon jest renderowany w hooku `displayAdminOrder`, specjalnie dla wersji PrestaShop 1.7.x i nowszych.
    - **Cel**: Podobnie jak w wersji 1.6, ten szablon dostarcza HTML dla pola wprowadzania daty faktury i przycisku przesyłania, dostosowany do różnic strukturalnych i stylistycznych strony zamówienia w Panelu administracyjnym PrestaShop 1.7+.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  Ten moduł nie tworzy żadnych nowych niestandardowych tabel baz danych. Modyfikuje pole `invoice_date` istniejącej tabeli `ps_order_invoice` (lub `_order_invoice` w zależności od Twojego prefiksu), gdy data faktury jest aktualizowana za pośrednictwem interfejsu modułu.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayAdminOrder` | Wykonywany na stronie szczegółów zamówienia w Panelu administracyjnym PrestaShop. | Ten hook jest używany do wstrzykiwania niestandardowego kodu HTML modułu (selektora daty i przycisku zapisu) do widoku szczegółów zamówienia, umożliwiając sprzedawcy interakcję z ustawieniem daty faktury. Moduł używa szablonów specyficznych dla wersji (`displayAdminOrder16.tpl` lub `displayAdminOrder17.tpl`) dla tego hooka. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania najnowszych aktualizacji, poprawek błędów i oficjalnego wsparcia dla modułu „Zmiana daty faktury” prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
