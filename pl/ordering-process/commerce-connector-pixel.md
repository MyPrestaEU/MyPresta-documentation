---
title: "Piksel Commerce Connector - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Piksel Commerce Connector” od MyPresta.eu."
sidebar:
  label: "Piksel Commerce Connector - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Commerce Connector pixel na MyPresta.eu](https://mypresta.eu/modules/ordering-process/commerce-connector-pixel.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/commerce-connector-pixel/)
>
> ---


# Piksel Commerce Connector

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające dla modułów PrestaShop. Dla tego modułu zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Piksel Commerce Connector”, aby uzyskać dostęp do jego ustawień.

#### **Identyfikator sklepu**

- **Do czego służy to ustawienie:** Jest to unikalny identyfikator dostarczony przez Commerce Connector dla Twojego konkretnego sklepu lub konta sprzedawcy. Jest on kluczowy dla Commerce Connector, aby prawidłowo przypisać dane sprzedażowe do Twojego konta.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawiony jest prawidłowy identyfikator sklepu:* Piksel zostanie uruchomiony z Twoim unikalnym identyfikatorem, umożliwiając Commerce Connector dokładne śledzenie sprzedaży dla Twojego sklepu.
  - *Gdy jest nieprawidłowy lub pusty:* Piksel może nie uruchomić się prawidłowo, lub dane sprzedażowe mogą zostać przypisane do niewłaściwego konta, co prowadzi do niedokładnego śledzenia i potencjalnie utraconych informacji marketingowych.
- **Zalecana wartość:** Wprowadź dokładny ciąg znaków „Identyfikator sklepu” dostarczony przez Commerce Connector. Zazwyczaj jest to kombinacja liter i cyfr.
- **Scenariusz / przykład dla sprzedawcy:** Commerce Connector informuje Cię, że Twój identyfikator sklepu to „MYSTORE12345”. Wprowadzasz „MYSTORE12345” w to pole. Bez tego Commerce Connector nie będzie wiedział, z którego sklepu pochodzi sprzedaż.

#### **Logowanie uruchomień piksela**

- **Do czego służy to ustawienie:** To ustawienie kontroluje, czy moduł rejestruje dziennik każdego uruchomienia piksela Commerce Connector (tj. za każdym razem, gdy klient dotrze do strony potwierdzenia zamówienia, a piksel próbuje się uruchomić). Ten dziennik może być przydatny do rozwiązywania problemów.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone („Włączone”):* Moduł utworzy plik dziennika (zazwyczaj w katalogu modułu) szczegółowo opisujący każde uruchomienie piksela, w tym szczegóły zamówienia. Może to pomóc zweryfikować, czy piksel działa zgodnie z oczekiwaniami.
  - *Gdy wyłączone („Wyłączone”):* Nie zostanie wygenerowany żaden plik dziennika, co jest standardowym ustawieniem dla sklepu produkcyjnego w celu oszczędzania miejsca na dysku i przetwarzania.
- **Zalecana wartość:** „Wyłączone” dla działającego sklepu produkcyjnego. Włącz „Włączone” tylko tymczasowo, jeśli rozwiązujesz problemy i musisz zweryfikować aktywność piksela.
- **Scenariusz / przykład dla sprzedawcy:** Podejrzewasz, że piksel nie śledzi wszystkich sprzedaży. Włączasz „Logowanie uruchomień piksela” na „Włączone”, składasz zamówienie testowe, a następnie sprawdzasz plik dziennika, aby zobaczyć, czy Twoje zamówienie testowe zostało zarejestrowane, potwierdzając uruchomienie piksela. Po potwierdzeniu przełączasz je z powrotem na „Wyłączone”.

#### **Włącz / Wyłącz moduł**

- **Do czego służy to ustawienie:** Jest to standardowy przełącznik modułu PrestaShop, który pozwala globalnie włączyć lub wyłączyć cały moduł piksela Commerce Connector.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone:* Moduł będzie aktywny, a piksel Commerce Connector zostanie wstrzyknięty na stronę potwierdzenia zamówienia, śledząc sprzedaż.
  - *Gdy wyłączone:* Moduł będzie nieaktywny, a piksel Commerce Connector NIE będzie obecny na stronie potwierdzenia zamówienia, co oznacza, że żadna sprzedaż nie będzie śledzona za pośrednictwem tego modułu.
- **Zalecana wartość:** „Włączone”, jeśli aktywnie używasz Commerce Connector do śledzenia sprzedaży.
- **Scenariusz / przykład dla sprzedawcy:** Zakończyłeś integrację z Commerce Connector i chcesz rozpocząć śledzenie sprzedaży. Upewniasz się, że to ustawienie jest „Włączone”. Jeśli tymczasowo wstrzymasz swoje kampanie Commerce Connector, możesz przełączyć je na „Wyłączone”, aby zapobiec niepotrzebnemu uruchamianiu piksela.

#### Inne klucze konfiguracyjne (wewnętrzne)

Moduł używa również wewnętrznych kluczy konfiguracyjnych, takich jak `mypresta_updates`, `update_`, `updatev_`, `COMCONN_SIDENT_`, `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`. Są one zazwyczaj przeznaczone do wewnętrznego zarządzania modułem, sprawdzania aktualizacji i obsługi języków w panelu administracyjnym PrestaShop. Sprzedawcy zazwyczaj nie muszą z nimi bezpośrednio wchodzić w interakcje.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Identyfikator sklepu | Twój unikalny identyfikator Commerce Connector | Kluczowe dla przypisywania danych sprzedażowych do Twojego konkretnego konta Commerce Connector. |
| Konfiguracja modułu | Logowanie uruchomień piksela | Wyłączone | Kontroluje, czy moduł tworzy plik dziennika uruchomień piksela. Włącz dla rozwiązywania problemów, wyłącz dla produkcji. |
| Konfiguracja modułu | Włącz / Wyłącz moduł | Włączone | Globalnie aktywuje lub dezaktywuje cały moduł i jego śledzenie pikseli. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zainstalowałem moduł, ale Commerce Connector nie pokazuje żadnych sprzedaży. Co powinienem zrobić?**
O:

1.  **Sprawdź „Identyfikator sklepu”:** Przejdź do konfiguracji modułu i upewnij się, że Twój „Identyfikator sklepu” jest wprowadzony prawidłowo i dokładnie odpowiada temu, co dostarczył Commerce Connector.
2.  **Moduł włączony:** Upewnij się, że moduł jest włączony na stronie konfiguracji.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym PrestaShop i wyczyść pamięć podręczną Smarty oraz wszystkie pamięci podręczne.
4.  **Zakup testowy:** Wykonaj pełny zakup testowy w swoim sklepie, przechodząc aż do strony potwierdzenia zamówienia.
5.  **Włącz logowanie:** Tymczasowo włącz „Logowanie uruchomień piksela” w konfiguracji modułu, wykonaj kolejny zakup testowy, a następnie sprawdź plik `logFile.tpl` (lub podobny plik dziennika) w katalogu modułu za pośrednictwem FTP, aby sprawdzić, czy uruchomienie piksela zostało zarejestrowane.
6.  **Skontaktuj się z pomocą techniczną:** Jeśli problemy nadal występują, skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojej konfiguracji i wszelkie wpisy z dziennika.

**P: Czy ten moduł spowolni moją witrynę?**
O: Nie. Piksel Commerce Connector to bardzo lekki skrypt, który ładuje się tylko na stronie potwierdzenia zamówienia. Strona ta jest zazwyczaj osiągana po głównym doświadczeniu zakupowym, a wykonanie piksela jest minimalne, więc nie wpłynie zauważalnie na wydajność ani szybkość ładowania Twojego sklepu dla klientów.

**P: Czy mogę używać tego modułu z innymi pikselami śledzącymi (np. Google Analytics, Facebook Pixel)?**
O: Tak, absolutnie. Ten moduł jest zaprojektowany do integracji specjalnie z Commerce Connector. Działa niezależnie i nie będzie kolidował z innymi pikselami śledzącymi ani skryptami analitycznymi zainstalowanymi w Twoim sklepie PrestaShop.

**P: Gdzie mogę znaleźć plik dziennika, jeśli włączę „Logowanie uruchomień piksela”?**
O: Jeśli jest włączony, plik dziennika jest zazwyczaj generowany w katalogu modułu. Będziesz potrzebować dostępu FTP do swojego serwera, aby przejść do `your_prestashop_root/modules/comconn/views/templates/hook/logFile.tpl` (lub podobnej ścieżki) i wyświetlić jego zawartość. Pamiętaj, aby wyłączyć logowanie po zakończeniu rozwiązywania problemów.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł piksela Commerce Connector (`comconn`) to prosty moduł PrestaShop zaprojektowany do wstrzykiwania specyficznego piksela JavaScript na stronę potwierdzenia zamówienia. Przestrzega architektury modułów PrestaShop, głównie wykorzystując hook `displayOrderConfirmation` do renderowania swojego skryptu śledzącego. Logika modułu jest zawarta w jego głównym pliku PHP, a konfiguracja jest zarządzana za pomocą `getContent()` i szablonów do renderowania piksela oraz opcjonalnego dziennika.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Moduł bezpośrednio podłącza się do `displayOrderConfirmation` i renderuje swoją zawartość za pośrednictwem szablonu.
- **Kontrolery Back-Office Admin**: Brak. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Główne klasy i modele (`classes/`)

- Brak. Moduł nie definiuje żadnych niestandardowych klas ani instancji `ObjectModel`. Cała logika jest zawarta w `comconn.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

- Brak. Moduł bezpośrednio osadza skrypt piksela Commerce Connector w swoim szablonie Smarty, zamiast linkować do zewnętrznych plików `.js`.

### 4.5 Arkusze stylów CSS (`views/css/`)

- Brak. Moduł nie dodaje żadnych niestandardowych stylów do front-office ani back-office.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa szablonów Smarty do renderowania swojego wyjścia.

- **Szablony hooków (`views/templates/hook/`)**:

  - `comconn/views/templates/hook/displayOrderConfirmation.tpl`
    - **Hook**: `displayOrderConfirmation`
    - **Cel**: Jest to główny szablon odpowiedzialny za renderowanie skryptu piksela Commerce Connector. Dynamicznie wstawia `Identyfikator sklepu` (z konfiguracji `COMCONN_SIDENT`) oraz szczegóły zamówienia (ID zamówienia, suma, waluta, produkty) do kodu JavaScript, który uruchamia piksel. Ten szablon jest kluczowy dla podstawowej funkcjonalności modułu.
  - `comconn/views/templates/hook/logFile.tpl`
    - **Hook**: Nie jest bezpośrednio podłączony, ale używany przez wewnętrzny mechanizm logowania modułu.
    - **Cel**: Ten szablon służy do formatowania i przechowywania wpisów dziennika, gdy opcja „Logowanie uruchomień piksela” jest włączona. Rejestruje szczegóły każdego uruchomienia piksela, w tym znacznik czasu, ID zamówienia i dane wysłane do Commerce Connector. Programiści mogą sprawdzić ten plik za pośrednictwem FTP w celu rozwiązywania problemów.
- **Szablony administracyjne (`views/templates/admin/`)**: Brak.
- **Szablony front-office (`views/templates/front/`)**: Brak.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**: Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoje ustawienia konfiguracyjne w standardowej tabeli `ps_configuration`.

  - Wpisy `PS_CONFIGURATION`:
    - `COMCONN_SIDENT`: Przechowuje identyfikator sklepu Commerce Connector sprzedawcy.
    - `COMCONN_LOG`: Przechowuje wartość logiczną (0 lub 1) dla włączania/wyłączania logowania uruchomień piksela.
    - `mypresta_updates`, `update_`, `updatev_`: Wewnętrzne klucze do aktualizacji modułu i wersjonowania.
- **Tabela zarejestrowanych hooków**:

  | Nazwa hooka | Czas wykonania | Cel techniczny |
  | --- | --- | --- |
  | `displayOrderConfirmation` | Po pomyślnym zakończeniu zamówienia przez klienta i dotarciu do strony potwierdzenia. | Wstrzykuje skrypt piksela Commerce Connector do strony w celu śledzenia zakończonego zakupu. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dalszej pomocy z modułem „Piksel Commerce Connector” prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i integracji modułu.
