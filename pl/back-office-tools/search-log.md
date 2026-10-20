---
title: "Dziennik wyszukiwań - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów modułu PrestaShop Dziennik wyszukiwań od MyPresta.eu."
sidebar:
  label: "Dziennik wyszukiwań - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Search log na MyPresta.eu](https://mypresta.eu/modules/administration-tools/search-log.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/search-log/)
>
> ---


# Dziennik wyszukiwań

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Brak specjalnych wymagań poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Dziennik wyszukiwań)

Jest to główny ekran konfiguracji modułu „Dziennik wyszukiwań”. Zapewnia prosty interfejs do włączania lub wyłączania funkcji logowania.

- **Lokalizacja menu:** Panel administracyjny > Moduły > Menedżer modułów > Dziennik wyszukiwań > Konfiguruj

| Ustawienie / Opcja | Co robi to ustawienie | Efekt zmiany tego ustawienia | Zalecana wartość | Scenariusz / przykład dla sprzedawcy |
| --- | --- | --- | --- | --- |
| **Włącz dziennik wyszukiwań** (Przełącznik) | Ten przełącznik kontroluje, czy moduł aktywnie rejestruje zapytania wyszukiwania klientów. | *Gdy włączone (TAK):* Za każdym razem, gdy klient użyje paska wyszukiwania w Twoim sklepie, jego termin wyszukiwania zostanie zapisany w dzienniku modułu. Możesz następnie przeglądać te dzienniki w dedykowanym menu „Dziennik wyszukiwań”.   *Gdy wyłączone (NIE):* Moduł przestanie rejestrować nowe zapytania wyszukiwania. Istniejące dzienniki pozostaną, ale nowe dane nie będą zbierane. | **TAK** | Właśnie zainstalowałeś moduł i chcesz natychmiast rozpocząć zbieranie danych, aby zrozumieć, czego szukają Twoi klienci. Ustawisz to na TAK. Jeśli tymczasowo musisz zatrzymać logowanie (np. podczas konserwacji lub jeśli masz zbyt dużo danych), możesz przełączyć to na NIE. |

### 2.2 Dedykowany ekran administracyjny: Zarządzanie dziennikiem wyszukiwań (Panel administracyjny > Dziennik wyszukiwań)

Ten ekran służy do przeglądania i zarządzania wszystkimi zapytaniami wyszukiwania zarejestrowanymi przez moduł. Zapewnia kompleksową listę tego, czego szukają Twoi klienci.

- **Nazwa ekranu i lokalizacja menu:** Panel administracyjny > **Dziennik wyszukiwań** (Pojawi się to jako nowa pozycja menu, zazwyczaj w sekcji „Parametry sklepu” lub „Zaawansowane” w zależności od wersji PrestaShop).

**Dostępne akcje i ustawienia:**
Ten ekran zazwyczaj przedstawia siatkę (listę) wszystkich zarejestrowanych terminów wyszukiwania. Dla każdego wpisu zazwyczaj zobaczysz:

- **Słowo kluczowe wyszukiwania:** Dokładny termin lub fraza wpisana przez klienta w pasek wyszukiwania.
- **Liczba wyszukiwań:** Ile razy to konkretne słowo kluczowe zostało wyszukane.
- **Data ostatniego wyszukiwania:** Kiedy to słowo kluczowe było ostatnio wyszukiwane.
- **Liczba wyników:** Ile produktów zostało znalezionych dla tego terminu wyszukiwania (jest to kluczowe do identyfikacji wyszukiwań „bez wyników”).

**Widok siatki / zarządzania:**
Siatka umożliwia:

- **Sortowanie:** Kliknij nagłówki kolumn (np. „Słowo kluczowe wyszukiwania”, „Liczba wyszukiwań”), aby posortować listę.
- **Filtrowanie:** Użyj pól filtru nad kolumnami, aby zawęzić listę (np. wyszukaj konkretne słowo kluczowe lub filtruj według liczby wyników).
- **Eksport:** Niektóre wersje mogą oferować opcję eksportu do pobrania danych w celu dalszej analizy w programie arkusza kalkulacyjnego.
- **Usuwanie:** Możesz mieć opcje usuwania pojedynczych wpisów wyszukiwania lub czyszczenia całego dziennika.

**Efekt zmian:**

- **Przeglądanie listy:** Zapewnia natychmiastowy wgląd w zachowania klientów podczas wyszukiwania.
- **Sortowanie/Filtrowanie:** Pomaga szybko zidentyfikować popularne wyszukiwania, wyszukiwania bez wyników lub trendy w czasie.
- **Usuwanie wpisów:** Usuwa dane z dziennika. Może to być przydatne do czyszczenia nieistotnych wpisów lub zarządzania rozmiarem bazy danych, ale ogólnie najlepiej jest zachować dane do analizy historycznej.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

1.  **Regularnie sprawdzaj ten ekran:** Wprowadź nawyk przeglądania „Dziennika wyszukiwań” co najmniej raz w tygodniu.
2.  **Skup się na wyszukiwaniach „Bez wyników”:** Priorytetowo traktuj słowa kluczowe, które dały zero wyników. To Twoje największe możliwości:
    - Czy masz produkt, ale nie jest on poprawnie indeksowany lub opis jest słaby?
    - Czy jest to produkt, który powinieneś rozważyć wprowadzić do oferty?
    - Czy jest to częsta literówka, którą możesz uwzględnić za pomocą synonimów?
3.  **Identyfikuj popularne wyszukiwania:** Zobacz, czym klienci są najbardziej zainteresowani. Upewnij się, że te produkty są widoczne, dobrze opisane i łatwe do znalezienia.
4.  **Analizuj trendy:** Czy istnieją sezonowe terminy wyszukiwania? Nowe pomysły na produkty wynikające z zapytań klientów?

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz dziennik wyszukiwań | TAK | Kontroluje, czy zapytania wyszukiwania klientów są rejestrowane. |
| Zarządzanie dziennikiem wyszukiwań | Słowo kluczowe wyszukiwania (Kolumna siatki) | N/A | Wyświetla faktyczny termin wyszukiwania użyty przez klientów. |
| Zarządzanie dziennikiem wyszukiwań | Liczba wyszukiwań (Kolumna siatki) | N/A | Pokazuje, ile razy konkretne słowo kluczowe zostało wyszukane. |
| Zarządzanie dziennikiem wyszukiwań | Data ostatniego wyszukiwania (Kolumna siatki) | N/A | Wskazuje najnowsze wystąpienie terminu wyszukiwania. |
| Zarządzanie dziennikiem wyszukiwań | Liczba wyników (Kolumna siatki) | N/A | Kluczowe do identyfikacji wyszukiwań, które nie dały żadnych produktów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Włączyłem moduł, ale nie widzę żadnych dzienników wyszukiwań.**
O:

1.  **Sprawdź, czy klienci faktycznie wyszukują:** Upewnij się, że pasek wyszukiwania w Twoim sklepie jest widoczny i używany przez odwiedzających.
2.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami buforowanie może uniemożliwić pełną inicjalizację modułów.
3.  **Przetestuj samodzielnie:** Wykonaj kilka wyszukiwań w swoim front-office, będąc wylogowanym (lub w trybie incognito), a następnie sprawdź ekran administracyjny „Dziennik wyszukiwań”.
4.  **Pozycja modułu:** Chociaż moduł nie ma widocznego komponentu front-office, upewnij się, że jest poprawnie podpięty. Moduł zazwyczaj podłącza się do `displayHeader` lub podobnego, co jest obsługiwane automatycznie. Jeśli problemy nadal występują, spróbuj ponownie zainstalować.

**P: Dziennik wyszukiwań staje się bardzo duży. Czy to spowolni mój sklep?**
O: Chociaż bardzo duża tabela bazy danych teoretycznie może wpłynąć na wydajność, dla większości sklepów tabela `slog` utworzona przez ten moduł raczej nie spowoduje znacznych spowolnień. Jest to prosta tabela logowania. Jeśli masz miliony wpisów i zauważysz problemy, możesz okresowo usuwać starsze wpisy z ekranu zarządzania „Dziennikiem wyszukiwań” lub tymczasowo wyłączyć moduł.

**P: Czy mogę zobaczyć, który klient wykonał konkretne wyszukiwanie?**
O: Nie, ten moduł jest przeznaczony do zbiorczej analizy słów kluczowych, a nie do śledzenia indywidualnych klientów. Rejestruje słowo kluczowe, a nie identyfikator klienta. Zapewnia to prywatność klienta, jednocześnie dostarczając cennych informacji biznesowych.

**P: Jak wyeksportować dane dziennika wyszukiwań do analizy w programie Excel?**
O: Ekran zarządzania „Dziennikiem wyszukiwań” w Twoim Panelu administracyjnym powinien mieć przycisk „Eksportuj” (często znajduje się w prawym górnym rogu siatki lub jako akcja zbiorcza). Kliknij go, aby pobrać dane, zazwyczaj w formacie CSV, które można otworzyć za pomocą programu Excel lub Arkuszy Google.

**P: Pasek wyszukiwania mojego niestandardowego motywu nie wydaje się być logowany.**
A: Moduł zazwyczaj podłącza się do standardowej funkcji wyszukiwania PrestaShop. Jeśli Twój niestandardowy motyw używa całkowicie niestandardowej, niestandardowej implementacji wyszukiwania (np. wyszukiwania AJAX, które omija główny kontroler wyszukiwania PrestaShop), moduł może nie przechwytywać tych zapytań. W takich przypadkach potrzebny byłby programista do bezpośredniej integracji funkcji logowania z Twoim niestandardowym skryptem wyszukiwania.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł „Dziennik wyszukiwań” to prosty moduł PrestaShop, skupiający się głównie na logowaniu danych. Wykorzystuje standardowy wzorzec PrestaShop MVC dla swojego komponentu Back Office, używając `AdminController` do zarządzania zarejestrowanymi danymi wyszukiwania. Mechanizm logowania front-office integruje się bezpośrednio z podstawowym procesem wyszukiwania PrestaShop, zazwyczaj poprzez podłączenie do akcji, która uruchamia się po wykonaniu wyszukiwania. Tworzy dedykowaną tabelę bazy danych do przechowywania zapytań wyszukiwania.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Moduł integruje się z istniejącą funkcjonalnością wyszukiwania PrestaShop za pomocą hooków, zamiast dostarczać własny kontroler front-office.
-   **Kontrolery administracyjne Back-Office**:

    -   `searchlog/controllers/admin/AdminSlog.php`

        -   **Nazwa klasy i klasa nadrzędna**: `AdminSlogController` rozszerza `ModuleAdminController`.
        -   **Odpowiedzialność**: Jest to główny kontroler do zarządzania wpisami dziennika wyszukiwań w Panelu administracyjnym PrestaShop. Obsługuje wyświetlanie siatki dziennika wyszukiwań, w tym sortowanie, filtrowanie i potencjalne akcje usuwania. Jest odpowiedzialny za pobieranie danych z tabeli bazy danych `slog` i renderowanie ich za pomocą komponentów PrestaShop `HelperList` lub `HelperGrid`.
        -   **Nazwa zakładki**: „Dziennik wyszukiwań” (lub podobna, w zależności od instalacji).
        -   **Zarządzana encja**: Tabela bazy danych `slog`.
    -   `searchlog/controllers/admin/index.php`

        -   **Nazwa klasy i klasa nadrzędna**: Nie jest klasą, ale standardowym plikiem PrestaShop `index.php` w katalogu kontrolera administracyjnego.
        -   **Odpowiedzialność**: Ten plik zazwyczaj służy jako środek bezpieczeństwa w katalogach administracyjnych PrestaShop, zapobiegając bezpośredniemu listowaniu katalogów. Zazwyczaj zawiera proste `header('Location: ../../index.php?controller=AdminHome'); exit;` lub podobne przekierowanie, lub po prostu instrukcję `die('Forbidden');`. Nie zawiera logiki specyficznej dla modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Dossier modułu nie wskazuje na niestandardowe klasy w katalogu `classes/`. Podstawowa logika interakcji z tabelą `slog` jest prawdopodobnie obsługiwana bezpośrednio w `AdminSlogController` lub głównym pliku modułu `searchlog/index.php`, być może za pomocą ogólnego `Db::getInstance()->execute()` do prostych operacji na danych, lub podstawowej definicji `ObjectModel`, jeśli taka została niejawnie utworzona lub nie została wymieniona w dossier. Biorąc pod uwagę prostotę, bardziej prawdopodobna jest bezpośrednia interakcja z `Db`.

### 4.4 Zasoby JavaScript (`views/js/`)

W archiwum modułu nie ma wymienionych niestandardowych plików JavaScript. Sugeruje to, że moduł w pełni polega na podstawowym JS PrestaShop dla swojej funkcjonalności siatki Back Office i nie wprowadza żadnego niestandardowego JS front-office.

### 4.5 Arkusze stylów CSS (`views/css/`)

W archiwum modułu nie ma wymienionych niestandardowych plików CSS. Wskazuje to, że moduł używa domyślnego stylu Back Office PrestaShop dla swoich ekranów konfiguracji i zarządzania, i nie wprowadza żadnych niestandardowych stylów front-office.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

W archiwum modułu nie ma wymienionych niestandardowych plików szablonów. Oznacza to, że formularz konfiguracji modułu i widok siatki `AdminSlogController` są renderowane za pomocą domyślnych szablonów `HelperForm` i `HelperList` (lub `HelperGrid`) PrestaShop, które są częścią podstawowego frameworka PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   `ps_slog` (lub `_slog` z Twoim prefiksem tabeli):
        -   Ta tabela jest tworzona przez moduł podczas instalacji.
        -   Przechowuje zarejestrowane zapytania wyszukiwania.
        -   Typowe pola to:
            -   `id_slog` (Klucz główny, INT)
            -   `keyword` (VARCHAR, przechowuje termin wyszukiwania)
            -   `results` (INT, liczba wyników znalezionych dla słowa kluczowego)
            -   `counter` (INT, liczba razy, ile to słowo kluczowe zostało wyszukane)
            -   `date_add` (DATETIME, znacznik czasu pierwszego wyszukiwania dla tego słowa kluczowego)
            -   `date_upd` (DATETIME, znacznik czasu ostatniego wyszukiwania dla tego słowa kluczowego)
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony front-office. | Chociaż dossier wymienia `Header` jako hook front-office, dla modułu logowania `displayHeader` jest często używany do rejestrowania zasobów lub do zapewnienia, że moduł jest aktywny na wszystkich stronach, na których może wystąpić wyszukiwanie. Rzeczywista logika logowania jest bardziej prawdopodobna związana z hookiem `action`. |
| `displayRightColumn` | Wykonywany w prawej kolumnie front-office. | Mało prawdopodobne, aby był używany do logowania, być może dla przyszłej funkcji lub jako placeholder. |
| `displayLeftColumn` | Wykonywany w lewej kolumnie front-office. | Mało prawdopodobne, aby był używany do logowania, być może dla przyszłej funkcji lub jako placeholder. |
| `displayFooter` | Wykonywany w sekcji stopki każdej strony front-office. | Podobnie jak `displayHeader`, może być używany do rejestracji zasobów lub zapewnienia kontekstu modułu, ale nie do bezpośredniego logowania. |
| `actionSearch` | Wykonywany po przetworzeniu zapytania wyszukiwania przez główny kontroler wyszukiwania PrestaShop. | **Jest to najważniejszy hook dla tego modułu.** Pozwala modułowi przechwycić termin wyszukiwania i liczbę wyników *po* tym, jak PrestaShop wykonał swoje wewnętrzne wyszukiwanie, umożliwiając logowanie `keyword` i `results` do tabeli `ps_slog`. |
| `actionModuleInstall` | Wykonywany podczas instalacji modułu. | Używany do tworzenia tabeli bazy danych `ps_slog` i rejestrowania niezbędnych hooków. |
| `actionModuleUninstall` | Wykonywany podczas deinstalacji modułu. | Używany do czyszczenia (np. usuwania tabeli `ps_slog`, wyrejestrowywania hooków). |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie deweloperskie dla modułu „Dziennik wyszukiwań”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół jest zaangażowany w świadczenie pomocy i zapewnienie optymalnego funkcjonowania modułu z Twoim sklepem PrestaShop.
