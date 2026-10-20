---
title: "Block IP free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Block IP free od MyPresta.eu."
sidebar:
  label: "Block IP free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Block IP free na MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-free.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/block-ip-free/)
>
> ---


# Block IP free

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Brak specjalnych wymagań poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Block IP free)

Jest to główny i jedyny ekran konfiguracji modułu „Block IP free”. Znajdziesz tutaj wszystkie ustawienia do zarządzania zablokowanymi adresami IP i wyświetlanym im komunikatem.

**Nazwa ekranu i lokalizacja w menu:**

- **Ścieżka menu:** Panel administracyjny > Moduły > Menedżer modułów > Block IP free > Konfiguruj

#### Ustawienia i opcje:

1.  **Adres IP (Pole wprowadzania)**

    *   **Co robi to ustawienie:** Tutaj wprowadzasz adres IP, który chcesz zablokować przed dostępem do Twojego sklepu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy IP zostanie dodane do listy:* Każdy odwiedzający próbujący uzyskać dostęp do Twojego sklepu z tego konkretnego adresu IP zostanie mu odmówiony dostęp i zostanie wyświetlony „Komunikat o zablokowanym dostępie”.
        *   *Gdy IP zostanie usunięte z listy:* Odwiedzający z tego adresu IP odzyskają pełny dostęp do Twojego sklepu.
    *   **Zalecana wartość:** Wprowadź dokładny adres IP, który chcesz zablokować. Możesz dodać wiele adresów IP, jeden po drugim, wprowadzając każdy i klikając „Dodaj”.
    *   **Scenariusz / przykład dla sprzedawcy:** Jeśli zauważysz, że konkretny adres IP (np. `192.168.1.100`) wielokrotnie próbuje składać fałszywe zamówienia lub zbierać dane o Twoich produktach, wprowadź `192.168.1.100` tutaj i kliknij „Dodaj”, aby go zablokować.
2.  **Komunikat o zablokowanym dostępie (Obszar tekstowy)**

    *   **Co robi to ustawienie:** Pozwala dostosować komunikat, który zablokowani odwiedzający zobaczą, gdy spróbują uzyskać dostęp do Twojego sklepu.
    *   **Efekt zmiany tego ustawienia:**
        *   *Gdy zostanie wprowadzony niestandardowy komunikat:* Zablokowani odwiedzający zobaczą Twój spersonalizowany komunikat zamiast domyślnego. Pozwala to być uprzejmym, informacyjnym lub stanowczym.
        *   *Gdy pozostawiono domyślne:* Zostanie wyświetlony standardowy komunikat „Dostęp zabroniony”.
    *   **Zalecana wartość:** Jasny i zwięzły komunikat. Coś w stylu: „Dostęp do tego sklepu został zablokowany z Twojego adresu IP. Jeśli uważasz, że to błąd, skontaktuj się z obsługą.”
    *   **Scenariusz / przykład dla sprzedawcy:** Możesz chcieć wyświetlić komunikat taki jak „Z powodu podejrzanej aktywności, dostęp z Twojego adresu IP został tymczasowo ograniczony. Skontaktuj się z naszym zespołem wsparcia, jeśli uważasz, że to błąd.” Zapewnia to lepsze wrażenia użytkownika niż ogólny błąd.

#### Zarządzanie listą zablokowanych adresów IP:

Poniżej pola wprowadzania „Adres IP” zobaczysz listę wszystkich aktualnie zablokowanych adresów IP.

-   **Aby dodać IP:** Wpisz adres IP w polu „Adres IP” i kliknij przycisk „Dodaj”.
-   **Aby usunąć IP:** Obok każdego wymienionego adresu IP znajdzie się przycisk „Usuń” (często reprezentowany przez ikonę kosza). Kliknij ten przycisk, aby odblokować ten konkretny adres IP.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Adres IP | Puste (dodaj adresy IP w razie potrzeby) | Dodaje/usuwa konkretne adresy IP z listy blokowanych. Zablokowane adresy IP nie mogą uzyskać dostępu do sklepu. |
| Strona konfiguracji modułu | Komunikat o zablokowanym dostępie | „Dostęp zabroniony” (lub podobny) | Dostosowuje komunikat wyświetlany odwiedzającym z zablokowanych adresów IP. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zablokowałem adres IP, ale użytkownik nadal może uzyskać dostęp do mojego sklepu. Dlaczego?**
O:

1.  **Buforowanie:** Twój sklep PrestaShop lub serwer może mieć włączone buforowanie. Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**) i wszelkie pamięci podręczne po stronie serwera (takie jak Varnish, LiteSpeed cache, Cloudflare), jeśli ma to zastosowanie.
2.  **Dynamiczny adres IP:** Użytkownik może mieć dynamiczny adres IP, który zmienił się od czasu zablokowania poprzedniego.
3.  **Proxy/VPN:** Użytkownik może używać serwera VPN lub proxy, który maskuje jego prawdziwy adres IP. Musiałbyś zablokować adres IP serwera VPN/proxy, jeśli możesz go zidentyfikować.
4.  **Nieprawidłowy adres IP:** Sprawdź dokładnie, czy wprowadziłeś prawidłowy adres IP.

**P: Przypadkowo zablokowałem swój własny adres IP i teraz nie mogę uzyskać dostępu do Panelu administracyjnego! Co mam zrobić?**
O: To krytyczna sytuacja, ale możliwa do naprawienia. Musisz uzyskać bezpośredni dostęp do swojego serwera:

1.  **Przez FTP/SFTP:** Połącz się z serwerem swojego sklepu za pomocą klienta FTP (np. FileZilla).
2.  **Przejdź do folderu modułów:** Przejdź do `twój_katalog_główny_prestashop/modules/`.
3.  **Zmień nazwę folderu modułu:** Znajdź folder `banipfree` i zmień jego nazwę na coś w stylu `banipfree_DISABLED`. Spowoduje to efektywne wyłączenie modułu.
4.  **Dostęp do Panelu administracyjnego:** Powinieneś teraz móc zalogować się do Panelu administracyjnego PrestaShop.
5.  **Ponowne włączenie i konfiguracja:** Zmień nazwę folderu z powrotem na `banipfree`, a następnie przejdź do **Moduły > Menedżer modułów**, znajdź „Block IP free” i kliknij „Konfiguruj”, aby usunąć swój adres IP z listy zablokowanych.

**P: Czy mogę zablokować zakres adresów IP zamiast tylko jednego?**
O: Obecna wersja modułu „Block IP free” pozwala na blokowanie pojedynczych adresów IP. Aby zablokować całe zakresy (np. `192.168.1.0/24`), zazwyczaj potrzebna jest konfiguracja na poziomie serwera (np. reguły `.htaccess` lub ustawienia zapory sieciowej) lub bardziej zaawansowany moduł bezpieczeństwa.

**P: Czy ten moduł spowolni mój sklep?**
O: Nie, moduł jest bardzo lekki. Sprawdza adres IP odwiedzającego bardzo wcześnie w procesie ładowania PrestaShop. Jeśli adres IP jest zablokowany, zawartość sklepu w ogóle nie jest ładowana, co może faktycznie zaoszczędzić zasoby serwera, zapobiegając pełnemu przetwarzaniu żądań przez niechciany ruch.

**P: Jak znaleźć adres IP problematycznego odwiedzającego?**
O: Adresy IP można znaleźć w kilku miejscach:

-   **Logi dostępu serwera:** Panel sterowania Twojego hostingu (cPanel, Plesk) zazwyczaj zapewnia dostęp do surowych logów dostępu, które zawierają listę adresów IP każdego odwiedzającego.
-   **Szczegóły zamówienia PrestaShop:** W przypadku zamówień adres IP klienta jest zazwyczaj rejestrowany na stronie szczegółów zamówienia w Panelu administracyjnym.
-   **Narzędzia analityczne:** Niektóre zaawansowane narzędzia analityczne mogą wyświetlać adresy IP odwiedzających, choć często są one anonimizowane.
-   **Moduły bezpieczeństwa innych firm:** Inne moduły bezpieczeństwa mogą rejestrować podejrzaną aktywność wraz z adresami IP.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów pracujących z modułem „Block IP free”.

### 4.1 Przegląd architektury

Moduł „Block IP free” to prosty, jednoplikowy moduł PrestaShop (`banipfree.php`), który wykorzystuje głównie hook `actionDispatcher`. Ten hook jest wykonywany bardzo wcześnie w cyklu życia żądania PrestaShop, co pozwala modułowi sprawdzić adres IP odwiedzającego przed jakimkolwiek znaczącym przetwarzaniem lub renderowaniem zawartości sklepu. Jeśli adres IP zostanie znaleziony na liście zablokowanych, moduł natychmiast przerywa żądanie i wyświetla niestandardowy komunikat, skutecznie działając jako wczesny etap zapory sieciowej. Konfiguracja jest obsługiwana za pomocą standardowej metody `getContent()`, przechowując ustawienia w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

-   Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office. Cała logika jest hermetyzowana w głównym pliku modułu.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

-   Ten moduł **nie** zawiera żadnych niestandardowych klas ani definicji `ObjectModel` w katalogu `classes/`. Cała obsługa danych odbywa się bezpośrednio za pomocą `Configuration::get()` i `Configuration::updateValue()`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   Ten moduł **nie** zawiera żadnych niestandardowych plików CSS. Komunikat o zablokowanym dostępie jest wyświetlany z minimalnym, wbudowanym stylem lub domyślnym stylem przeglądarki.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   Ten moduł **nie** zawiera żadnych niestandardowych plików szablonów Smarty. Komunikat o zablokowanym dostępie jest wyprowadzany bezpośrednio jako surowy HTML/tekst w metodzie `hookActionDispatcher`.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoje ustawienia konfiguracyjne w standardowej tabeli `ps_configuration`:

-   `BANIPFREE_LIST`: Przechowuje ciąg znaków z adresami IP oddzielonymi przecinkami.
-   `BANIPFREE_MSG`: Przechowuje niestandardowy komunikat wyświetlany zablokowanym użytkownikom.
-   `mypresta_updates`, `update_`, `updatev_`: Wewnętrzne klucze używane przez MyPresta.eu do sprawdzania aktualizacji modułów.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionDispatcher` | Wykonywany bardzo wcześnie w cyklu życia żądania PrestaShop, przed wysłaniem kontrolera. | Jest to główny hook używany przez moduł. Pobiera adres IP odwiedzającego, sprawdza go na liście `BANIPFREE_LIST`, a jeśli zostanie znalezione dopasowanie, wyprowadza `BANIPFREE_MSG` i przerywa wykonywanie skryptu (`die()`), zapobiegając dalszemu ładowaniu sklepu. |

### 4.8 Główny plik modułu (`banipfree/banipfree.php`)

To jest rdzeń modułu.

-   **`__construct()`**: Inicjalizuje metadane modułu (nazwa, zakładka, wersja, autor itp.).
-   **`install()`**:
    *   Wywołuje `parent::install()`.
    *   Rejestruje hook `actionDispatcher`.
    *   Ustawia początkowe wartości konfiguracyjne dla `BANIPFREE_LIST` (pusta) i `BANIPFREE_MSG` (domyślny komunikat).
-   **`uninstall()`**:
    *   Wywołuje `parent::uninstall()`.
    *   Wyrejestrowuje hook `actionDispatcher`.
    *   Usuwa wartości konfiguracyjne (`BANIPFREE_LIST`, `BANIPFREE_MSG`).
-   **`getContent()`**:
    *   Obsługuje przesyłanie formularza w celu zapisania adresów IP i niestandardowego komunikatu.
    *   Pobiera i wyświetla bieżącą listę zablokowanych adresów IP.
    *   Renderuje formularz konfiguracyjny za pomocą standardowych elementów `HelperForm` PrestaShop (pole tekstowe dla IP, obszar tekstowy dla komunikatu, lista zablokowanych adresów IP z przyciskami usuwania).
-   **`hookActionDispatcher()`**:
    *   Jest to krytyczna metoda blokowania.
    *   Pobiera adres IP odwiedzającego (`$_SERVER['REMOTE_ADDR']`).
    *   Pobiera `BANIPFREE_LIST` z `Configuration`.
    *   Sprawdza, czy bieżący adres IP znajduje się na liście oddzielonej przecinkami.
    *   Jeśli adres IP jest zablokowany, pobiera `BANIPFREE_MSG`, wyprowadza prostą stronę HTML z komunikatem i wywołuje `die()`, aby zatrzymać dalsze wykonywanie.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Block IP free”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu.
"""
