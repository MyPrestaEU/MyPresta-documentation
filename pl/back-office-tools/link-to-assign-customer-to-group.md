---
title: "Link do przypisania klienta do grupy - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Link do przypisania klienta do grupy” od MyPresta.eu."
sidebar:
  label: "Link do przypisania klienta do grupy"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Link to assign customer to group na MyPresta.eu](https://mypresta.eu/modules/administration-tools/link-to-assign-customer-to-group.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/link-to-assign-customer-to-group/)
>
> ---


# Link do przypisania klienta do grupy

## 1. Wymagania i kompatybilność
-   **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Kompatybilność z PHP**: PHP 5.6 - 8.5
-   **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Menedżer modułów > Konfiguruj Link do przypisania klienta do grupy)

Jest to główny i jedyny ekran konfiguracji modułu. Tutaj możesz zdefiniować, jak moduł zachowuje się podczas przypisywania klientów do grup.

#### **Zmień grupę na domyślną**
-   **Co robi to ustawienie:** To ustawienie określa, czy moduł powinien również przypisać klienta do „Domyślnej” grupy klientów, oprócz grupy określonej w adresie URL.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone (TAK):* Jeśli klient kliknie link, aby zostać przypisanym do „Grupy X”, zostanie również przypisany do grupy „Domyślnej”. Oznacza to, że będzie częścią zarówno „Grupy X”, jak i „Domyślnej”. Może to być przydatne, jeśli Twoja grupa „Domyślna” ma pewne podstawowe uprawnienia lub rabaty, które zawsze chcesz, aby klienci mieli, niezależnie od innych grup, do których dołączają.
    -   *Gdy wyłączone (NIE):* Klient zostanie przypisany tylko do grupy określonej w adresie URL (np. „Grupa X”). Nie zostanie automatycznie dodany do grupy „Domyślnej”, chyba że już do niej należy lub inny mechanizm go doda.
-   **Zalecana wartość:** **NIE**. W większości przypadków chcesz przypisać klientów do *konkretnej* grupy bez konieczności dodawania ich do grupy „Domyślnej”, zwłaszcza jeśli Twoja grupa „Domyślna” nie ma specjalnego znaczenia lub jeśli chcesz precyzyjniej zarządzać grupami. Włącz to tylko, jeśli masz konkretny powód, aby zawsze uwzględniać grupę „Domyślną”.
-   **Scenariusz / przykład dla sprzedawcy:** Masz grupę „VIP” ze specjalnymi rabatami. Jeśli to włączysz, klient klikający link VIP będzie zarówno w „VIP”, jak i „Domyślnej”. Jeśli „Domyślna” ma 5% rabatu na cały sklep, a „VIP” ma 15% rabatu na konkretne produkty, klient skorzysta z obu, gdzie ma to zastosowanie. Jeśli wyłączone, otrzymałby tylko korzyści „VIP”.

#### **Odłącz klienta od innych grup**
-   **Co robi to ustawienie:** To ustawienie kontroluje, czy moduł powinien usunąć klienta ze *wszystkich innych* grup klientów, gdy zostanie przypisany do nowej grupy za pomocą specjalnego linku.
-   **Efekt zmiany tego ustawienia:**
    -   *Gdy włączone (TAK):* Jeśli klient jest obecnie w „Grupie A” i „Grupie B”, a następnie kliknie link, aby zostać przypisanym do „Grupy X”, zostanie usunięty z „Grupy A” i „Grupy B” i pozostanie tylko w „Grupie X” (i potencjalnie „Domyślnej”, jeśli poprzednie ustawienie jest włączone). Zapewnia to, że klient jest *tylko* w grupie docelowej.
    -   *Gdy wyłączone (NIE):* Klient zostanie *dodany* do nowej grupy („Grupa X”), ale *pozostanie* we wszystkich innych grupach, do których już należał (np. „Grupa A”, „Grupa B”). Pozwala to klientom być członkami wielu grup jednocześnie.
-   **Zalecana wartość:** **NIE**. Pozwalanie klientom na przynależność do wielu grup oferuje większą elastyczność dla złożonej segmentacji. Włącz to tylko, jeśli potrzebujesz ścisłych, wzajemnie wykluczających się grup (np. klient może być tylko „Detaliczny” LUB „Hurtowy”, nigdy obu).
-   **Scenariusz / przykład dla sprzedawcy:**
    -   *Włączone (TAK):* Masz grupy „Standardowy klient” i „Klient hurtowy”. Klient klika link, aby stać się „Hurtowym”. Jeśli włączone, zostaje usunięty z „Standardowego klienta” i pozostaje tylko „Hurtowy”. Jest to idealne dla jasnych, odrębnych typów klientów.
    -   *Wyłączone (NIE):* Masz grupy „Subskrybent newslettera” i „Członek programu lojalnościowego”. Klient klika link, aby dołączyć do „Programu lojalnościowego”. Jeśli wyłączone, pozostaje „Subskrybentem newslettera” *i* staje się „Członkiem programu lojalnościowego”. Jest to idealne dla korzyści addytywnych.

#### **Jak stworzyć specjalny link**
Moduł działa poprzez dodanie specjalnego parametru do dowolnego adresu URL w Twoim sklepie. Format parametru to: `?asg={group_id}`

1.  **Znajdź ID grupy:**
    -   Przejdź do **Klienci > Grupy** w Panelu administracyjnym PrestaShop.
    -   Zanotuj numer ID obok grupy, do której chcesz przypisać klientów. Na przykład, jeśli „Hurt” ma ID `3`, to `3` jest Twoim `group_id`.
2.  **Skonstruuj link:**
    -   Weź dowolny adres URL ze swojego sklepu (np. `https://twoj-sklep.com/`)
    -   Dołącz do niego `?asg={group_id}`.
    -   **Przykład:** Aby przypisać klienta do grupy o ID `3` (np. „Hurt”) i przekierować go na stronę główną: `https://twoj-sklep.com/?asg=3`
    -   **Przykład:** Aby przypisać klienta do grupy o ID `5` (np. „VIP”) i przekierować go na konkretną stronę produktu: `https://twoj-sklep.com/pl/produkt/123-niesamowity-produkt?asg=5`

:::warning
Parametr `asg` musi być *pierwszym* parametrem, jeśli w adresie URL nie ma innych parametrów (tzn. użyj `?`). Jeśli adres URL ma już parametry (np. `https://twoj-sklep.com/kategoria/1-odziez?id_category=1`), musisz użyć `&`, aby dodać parametr `asg`: `https://twoj-sklep.com/kategoria/1-odziez?id_category=1&asg=3`.
:::

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Konfiguracja modułu | Zmień grupę na domyślną | NIE | Jeśli TAK, klient jest również dodawany do grupy „Domyślnej”. Jeśli NIE, tylko do określonej grupy. |
| Konfiguracja modułu | Odłącz klienta od innych grup | NIE | Jeśli TAK, klient jest usuwany ze wszystkich innych grup. Jeśli NIE, klient pozostaje w istniejących grupach i jest dodawany do nowej. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Klient kliknął link, ale nie został przypisany do grupy. Co jest nie tak?**
O:
1.  **Klient nie jest zalogowany:** Moduł działa tylko dla *zalogowanych* klientów. Jeśli nie byli zalogowani, zostaną po prostu przekierowani na stronę bez przypisania do grupy.
2.  **Nieprawidłowe ID grupy:** Dokładnie sprawdź `group_id` w swoim adresie URL z rzeczywistym ID w **Klienci > Grupy**.
3.  **Nieprawidłowy parametr URL:** Upewnij się, że używasz `?asg=` dla pierwszego parametru i `&asg=` dla kolejnych parametrów.
4.  **Moduł nie jest włączony:** Sprawdź, czy moduł jest zainstalowany i włączony w **Moduły > Menedżer modułów**.
5.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (Zaawansowane > Wydajność > Wyczyść pamięć podręczną) i pamięć podręczną przeglądarki.

**P: Czy mogę przypisać klienta do wielu grup za pomocą jednego linku?**
O: Nie, parametr `asg` obsługuje przypisywanie tylko do jednej grupy naraz. Jednak jeśli opcja „Odłącz klienta od innych grup” jest ustawiona na NIE, klient zostanie *dodany* do nowej grupy, zachowując członkostwo w swoich istniejących grupach.

**P: Czy ten moduł wpływa na SEO?**
O: Nie, ten moduł nie ma bezpośredniego wpływu na SEO Twojego sklepu. Parametr `asg` jest dynamicznym parametrem, który wyszukiwarki zazwyczaj ignorują.

**P: Co się stanie, jeśli klient kliknie link wielokrotnie?**
O: Jeśli klient jest już w grupie docelowej, nic się nie zmieni. Jeśli nie jest, zostanie do niej przypisany. Moduł jest zaprojektowany tak, aby obsługiwać to płynnie, bez błędów.

**P: Chcę usunąć klienta z grupy za pomocą linku. Czy to możliwe?**
O: Nie, ten moduł jest przeznaczony tylko do *przypisywania* klientów do grup. Nie zapewnia funkcjonalności usuwania klientów z grup za pomocą adresu URL. Musiałbyś to zrobić ręcznie w Panelu administracyjnym lub użyć innego modułu/niestandardowego rozwiązania.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury
Moduł „Link do przypisania klienta do grupy” (`assigntogroup`) to lekki moduł PrestaShop, zaprojektowany głównie do przechwytywania żądań z panelu klienta i modyfikowania przypisań grup klientów na podstawie parametru URL. Wykorzystuje system hooków PrestaShop (`displayHeader`) do wykonania swojej logiki wcześnie w procesie ładowania strony, zapewniając, że zmiany grup są stosowane przed renderowaniem zawartości strony. Nie wprowadza niestandardowych kontrolerów, modeli ani złożonego JavaScriptu/CSS. Jego podstawowa funkcjonalność znajduje się w głównej klasie modułu.

### 4.2 Kontrolery (`controllers/`)
-   **Kontrolery panelu klienta**: Brak. Logika modułu jest wykonywana za pomocą hooka, a nie dedykowanego kontrolera front-office.
-   **Kontrolery panelu administracyjnego**: Brak. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego modułu.

### 4.3 Główne klasy i modele (`classes/`)
-   W katalogu `classes/` nie są zdefiniowane żadne niestandardowe klasy ani ObjectModels. Moduł bezpośrednio współdziała z podstawowymi ObjectModels PrestaShop `Customer` i `Group`.

### 4.4 Zasoby JavaScript (`views/js/`)
-   Ten moduł nie zawiera żadnych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)
-   Ten moduł nie zawiera żadnych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**:
    *   `assigntogroup/views/templates/hook/form.tpl`
        *   **Cel**: Ten szablon służy do renderowania formularza konfiguracji modułu w Panelu administracyjnym PrestaShop. Jest renderowany przez metodę `getContent()` głównej klasy modułu.
        *   **Zawartość**: Zawiera strukturę HTML dla dwóch przełączników konfiguracji (`asg_unassign`, `asg_default`) i przycisku wysyłania formularza. Wykorzystuje standardowe elementy formularza pomocniczego PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    *   Moduł nie tworzy żadnych niestandardowych tabel SQL.
    *   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration`:
        *   `PS_ASG_UNASSIGN`: Przechowuje wartość ustawienia „Odłącz klienta od innych grup” (0 lub 1).
        *   `PS_ASG_DEFAULT`: Przechowuje wartość ustawienia „Zmień grupę na domyślną” (0 lub 1).

-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | Wykonywany wcześnie podczas ładowania strony w panelu klienta, w sekcji `<head>`. | Jest to główny hook używany przez moduł. Sprawdza parametr URL `asg`, weryfikuje, czy klient jest zalogowany, a następnie wykonuje logikę przypisania grupy na podstawie ustawień konfiguracyjnych modułu (`PS_ASG_UNASSIGN`, `PS_ASG_DEFAULT`). |

### 4.8 Główny plik PHP modułu (`assigntogroup/assigntogroup.php`)

Jest to centralny plik modułu, zawierający jego instalację, deinstalację, konfigurację i podstawową logikę.

-   **Nazwa klasy**: `Assigntogroup`
-   **Klasa nadrzędna**: `Module`
-   **Kluczowe metody**:
    *   `__construct()`: Inicjalizuje metadane modułu (nazwa, zakładka, wersja, autor itp.).
    *   `install()`:
        *   Rejestruje hook `displayHeader`.
        *   Ustawia domyślne wartości konfiguracyjne dla `PS_ASG_UNASSIGN` (0) i `PS_ASG_DEFAULT` (0) w `ps_configuration`.
        *   Zwraca `true` w przypadku sukcesu.
    *   `uninstall()`:
        *   Wyrejestrowuje hook `displayHeader`.
        *   Usuwa wartości konfiguracyjne `PS_ASG_UNASSIGN` i `PS_ASG_DEFAULT` z `ps_configuration`.
        *   Zwraca `true` w przypadku sukcesu.
    *   `getContent()`:
        *   Obsługuje przesyłanie formularza konfiguracji modułu w Panelu administracyjnym.
        *   Aktualizuje `PS_ASG_UNASSIGN` i `PS_ASG_DEFAULT` w `ps_configuration` na podstawie danych wejściowych użytkownika.
        *   Renderuje formularz konfiguracji za pomocą `display(__FILE__, 'views/templates/hook/form.tpl')`.
    *   `hookDisplayHeader()`:
        *   **Główna logika**: Ta metoda jest wykonywana przy każdym ładowaniu strony w panelu klienta.
        *   Sprawdza, czy parametr GET `asg` jest obecny i jest prawidłową liczbą całkowitą reprezentującą `id_group`.
        *   Weryfikuje, czy klient jest zalogowany (`$this->context->customer->isLogged()`).
        *   Pobiera docelowy obiekt `Group`.
        *   Pobiera bieżący obiekt `Customer`.
        *   Na podstawie konfiguracji `PS_ASG_UNASSIGN` i `PS_ASG_DEFAULT`:
            *   Zarządza powiązaniami grup klienta (`$customer->updateGroup()`).
            *   Dodaje klienta do określonej grupy.
            *   Opcjonalnie usuwa klienta z innych grup.
            *   Opcjonalnie dodaje klienta do grupy domyślnej.
        *   Przekierowuje użytkownika na bieżący adres URL bez parametru `asg`, aby zapobiec ponownemu przetwarzaniu przy odświeżeniu.

## 5. Oficjalne wsparcie i aktualizacje
Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Link do przypisania klienta do grupy”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu.
