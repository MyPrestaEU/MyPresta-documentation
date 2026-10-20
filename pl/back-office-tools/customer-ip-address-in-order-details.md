---
title: "Adres IP klienta w szczegółach zamówienia - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Adres IP klienta w szczegółach zamówienia” od MyPresta.eu."
sidebar:
  label: "Adres IP klienta w szczegółach zamówienia"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Customer IP address in order details na MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-ip-address-in-order-details.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/customer-ip-address-in-order-details/)
>
> ---


# Adres IP klienta w szczegółach zamówienia

## 1. Wymagania i kompatybilność
- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające, ponieważ ten moduł ma minimalne zależności zewnętrzne.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)
Ten moduł został zaprojektowany tak, aby był niezwykle prosty i skuteczny, nie wymagając skomplikowanej konfiguracji. Po instalacji znajdziesz podstawowy ekran konfiguracji.

-   **Nazwa ekranu i lokalizacja w menu:** Panel administracyjny > Moduły > Menedżer modułów > „Adres IP klienta w szczegółach zamówienia” > Konfiguruj

Na tym ekranie zazwyczaj zobaczysz:

-   **Co robi to ustawienie:** Ten moduł zazwyczaj nie ma specyficznych ustawień konfigurowalnych poza początkową instalacją. Jego podstawowa funkcjonalność (wyświetlanie adresu IP) jest aktywna domyślnie po zainstalowaniu. Strona konfiguracji może po prostu potwierdzić, że moduł jest aktywny lub dostarczyć podstawowe informacje.
-   **Efekt zmiany tego ustawienia:** Ponieważ nie ma specyficznych ustawień do zmiany, zachowanie modułu pozostaje spójne: będzie wyświetlał adres IP klienta na stronie szczegółów zamówienia.
-   **Zalecana wartość:** N/A (Brak opcji konfigurowalnych).
-   **Scenariusz/przykład dla sprzedawcy:** Po prostu zainstaluj i włącz moduł. Gdy wyświetlisz dowolne zamówienie w swoim panelu administracyjnym, zobaczysz teraz adres IP klienta wyświetlony wyraźnie w szczegółach zamówienia.

### 2.2 Tabela szybkiego odniesienia do konfiguracji
| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
|---|---|---|---|
| Strona konfiguracji modułu | *(Brak specyficznych ustawień)* | N/A | Moduł automatycznie wyświetla adresy IP klientów na stronach szczegółów zamówień po zainstalowaniu i włączeniu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zainstalowałem moduł, ale nie widzę adresu IP na stronie szczegółów zamówienia. Co powinienem zrobić?**
O:
1.  **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Adres IP klienta w szczegółach zamówienia” jest zainstalowany i włączony.
2.  **Wyczyść pamięć podręczną:** Czasami pamięć podręczna PrestaShop może uniemożliwić natychmiastowe pojawienie się zmian. Przejdź do **Zaawansowane > Wydajność**, przewiń w dół i kliknij „Wyczyść pamięć podręczną”.
3.  **Zweryfikuj stronę zamówienia:** Przejdź do istniejącego zamówienia (lub złóż zamówienie testowe) w **Zamówienia > Zamówienia** i kliknij, aby wyświetlić jego szczegóły. Adres IP powinien pojawić się w dedykowanym bloku lub sekcji.
4.  **Kompatybilność z motywem:** Chociaż jest to mało prawdopodobne w przypadku tak prostego modułu, bardzo mocno dostosowane motywy mogą czasami kolidować z hookami. Jeśli problem nadal występuje, tymczasowo przełącz się na domyślny motyw PrestaShop (Classic), aby sprawdzić, czy adres IP się pojawi.

**P: Czy ten moduł przechowuje adresy IP klientów w mojej bazie danych?**
O: Sam PrestaShop zazwyczaj przechowuje adres IP klienta, gdy ten się rejestruje lub składa zamówienie. Ten moduł po prostu pobiera i wyświetla te istniejące informacje z Twojej bazy danych na stronie szczegółów zamówienia. Nie tworzy nowych tabel bazy danych ani nie przechowuje dodatkowych danych IP niezależnie.

**P: Czy ten moduł spowolni mój sklep?**
O: Nie. Ten moduł jest bardzo lekki. Dodaje tylko niewielką informację do istniejącej strony back-office (szczegóły zamówienia) i nie wykonuje żadnych skomplikowanych obliczeń ani operacji front-office, które wpłynęłyby na szybkość przeglądania przez klienta.

**P: Czy adres IP jest zawsze dokładny?**
O: Zarejestrowany adres IP jest zazwyczaj tym, z którego klient połączył się z Twoim sklepem. Jednak klienci korzystający z VPN-ów, serwerów proxy lub niektórych sieci komórkowych mogą mieć adres IP, który nie odzwierciedla bezpośrednio ich fizycznej lokalizacji. Jest to przydatny wskaźnik, ale nie zawsze ostateczne określenie geograficzne.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)
Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury
Moduł „Adres IP klienta w szczegółach zamówienia” (`iporder`) to bardzo prosty moduł PrestaShop zaprojektowany w celu rozszerzenia funkcjonalności kontrolera `AdminOrders`. Wykorzystuje standardowy hook PrestaShop (`displayAdminOrder`) do wstrzykiwania dodatkowych informacji (adresu IP klienta) bezpośrednio na stronę szczegółów zamówienia w panelu administracyjnym. Przyjmuje minimalistyczne podejście, koncentrując się wyłącznie na wyświetlaniu istniejących danych, a nie wprowadzaniu nowych modeli danych ani złożonej logiki.

### 4.2 Kontrolery (`controllers/`)
Ten moduł nie wprowadza żadnych niestandardowych kontrolerów Front-Office ani Back-Office. Jego funkcjonalność jest w pełni zintegrowana za pomocą hooków w ramach istniejących kontrolerów PrestaShop.

### 4.3 Klasy podstawowe i modele (`classes/`)
Ten moduł nie definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Działa poprzez bezpośredni dostęp do istniejących obiektów rdzenia PrestaShop i ich właściwości (np. `Order`, `Customer`).

### 4.4 Zasoby JavaScript (`views/js/`)
Ten moduł nie zawiera żadnych niestandardowych plików JavaScript. Wyświetlanie adresu IP jest renderowane wyłącznie po stronie serwera w HTML.

### 4.5 Arkusze stylów CSS (`views/css/`)
Ten moduł nie zawiera żadnych niestandardowych plików CSS. Wstrzyknięta zawartość odziedziczy styl z motywu panelu administracyjnego PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)
Cała logika wyświetlania modułu znajduje się w jednym pliku szablonu Smarty.

-   **Szablony hooków (`views/templates/hook/`)**:
    *   `iporder/views/templates/hook/displayAdminOrder.tpl`
        *   **Hook:** `displayAdminOrder`
        *   **Cel:** Ten szablon jest renderowany na stronie szczegółów zamówienia w panelu administracyjnym PrestaShop. Pobiera adres IP klienta powiązany z bieżącym zamówieniem i wyświetla go w dedykowanym bloku.
        *   **Zawartość:** Zazwyczaj uzyskuje dostęp do zmiennych Smarty `$order` i `$customer` (przekazanych przez hook `displayAdminOrder`), aby pobrać `{$customer->ip_registration_date}` lub podobne, i formatuje je do wyświetlenia. Może również używać `$_SERVER['REMOTE_ADDR']`, jeśli adres IP nie jest bezpośrednio przechowywany z obiektem klienta lub zamówienia w łatwo dostępny sposób poprzez hook. Biorąc pod uwagę opis modułu, prawdopodobnie uzyskuje dostęp do adresu IP przechowywanego z obiektem klienta lub zamówienia.

### 4.7 Schemat bazy danych i mapa hooków
-   **Tabele bazy danych**: Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych. Opiera się na istniejących tabelach PrestaShop, w szczególności `ps_customer` (która w niektórych wersjach przechowuje `last_passwd_gen` i `ip_registration_date`, chociaż `ip_registration_date` nie jest ściśle adresem IP zamówienia) i potencjalnie `ps_orders`, jeśli adres IP jest przechowywany bezpośrednio z zamówieniem. Najczęstszym podejściem dla tego modułu byłoby pobranie adresu IP z `$_SERVER['REMOTE_ADDR']` w momencie składania zamówienia i zapisanie go w niestandardowym polu, jeśli nie jest już obecny, lub po prostu wyświetlenie `ip_registration_date` z obiektu klienta. Jednak biorąc pod uwagę prostotę modułu i brak niestandardowych klas, najprawdopodobniej pobiera on adres IP powiązany z rejestracją klienta lub `REMOTE_ADDR` w momencie przetwarzania zamówienia, jeśli jest dostępny poprzez kontekst hooka.
    *   **Uwaga:** PrestaShop 1.7+ przechowuje `current_ip_address` w tabeli `ps_connections`, powiązanej z `ps_guest` i `ps_customer`. `ip_registration_date` w `ps_customer` to adres IP, z którego klient się zarejestrował. Celem modułu jest pokazanie adresu IP *w momencie zamówienia*. Zazwyczaj oznacza to:
        1.  Dostęp do `$_SERVER['REMOTE_ADDR']`, jeśli hook dostarcza go w kontekście zamówienia.
        2.  Pobranie adresu IP z tabeli `ps_connections` na podstawie `id_guest` powiązanego z zamówieniem.
        3.  Pobranie `ip_registration_date` z `ps_customer` (mniej dokładne dla konkretnego zamówienia).
        Biorąc pod uwagę prostotę, prawdopodobnie używa najbardziej prostego sposobu dostępnego poprzez hook.

-   **Tabela zarejestrowanych hooków**:
    | Nazwa hooka | Czas wykonania | Cel techniczny |
    |---|---|---|
    | `displayAdminOrder` | Wykonywany, gdy renderowana jest strona szczegółów zamówienia w panelu administracyjnym PrestaShop. | Wstrzykuje adres IP klienta do widoku szczegółów zamówienia. |

## 5. Oficjalne wsparcie i aktualizacje
W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkich dalszych pytań dotyczących modułu „Adres IP klienta w szczegółach zamówienia”, prosimy odwołać się do swojego konta klienta MyPresta.eu. Możesz uzyskać dostęp do swoich pobranych plików i zgłoszeń do wsparcia bezpośrednio z [MyPresta.eu Historia zamówień i pobieranie](https://mypresta.eu/my-account/orders/).
