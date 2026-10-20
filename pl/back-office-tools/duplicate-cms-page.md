---
title: "Duplikowanie strony CMS - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Duplikowanie strony CMS” od MyPresta.eu."
sidebar:
  label: "Duplikowanie strony CMS - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Duplicate CMS page na MyPresta.eu](https://mypresta.eu/modules/administration-tools/duplicate-cms-page.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/duplicate-cms-page/)
>
> ---


# Duplikowanie strony CMS

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Duplikowanie strony CMS” w Menedżerze modułów. Spowoduje to przejście do głównego ekranu konfiguracji modułu.

#### Ustawienia ogólne

- **Aktualizacje MyPresta.eu (mypresta\_updates)**

  - **Co robi to ustawienie:** To ustawienie kontroluje, czy moduł sprawdza dostępność aktualizacji z MyPresta.eu. Włączenie tej opcji zapewnia powiadomienia o nowych wersjach, poprawkach błędów i ulepszeniach funkcji.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Moduł będzie okresowo sprawdzał dostępność aktualizacji. Jeśli aktualizacja zostanie znaleziona, w Panelu administracyjnym PrestaShop może pojawić się powiadomienie.
    - *Gdy wyłączone:* Moduł nie będzie sprawdzał aktualizacji, a Ty nie będziesz automatycznie powiadamiany o nowych wersjach. Musiałbyś ręcznie sprawdzać aktualizacje na MyPresta.eu.
  - **Zalecana wartość:** **TAK** (Włączone).
  - **Scenariusz/przykład dla sprzedawcy:** Chcesz mieć pewność, że Twój moduł jest zawsze aktualny z najnowszymi poprawkami bezpieczeństwa i funkcjami, bez ręcznego sprawdzania strony MyPresta.eu co tydzień.
- **Aktualizacja (update\_)**

  - **Co robi to ustawienie:** Jest to zazwyczaj pole wyświetlania lub przycisk związany ze sprawdzaniem aktualizacji, pokazujący bieżący status lub umożliwiający ręczne sprawdzenie. Działa w połączeniu z ustawieniem „Aktualizacje MyPresta.eu”.
  - **Efekt zmiany tego ustawienia:** Kliknięcie przycisku tutaj (jeśli jest obecny) zainicjowałoby natychmiastowe sprawdzenie aktualizacji.
  - **Zalecana wartość:** N/A (Oparte na interakcji).
  - **Scenariusz/przykład dla sprzedawcy:** Po włączeniu „Aktualizacji MyPresta.eu” możesz kliknąć to, aby natychmiast sprawdzić, czy dostępna jest nowa wersja, zamiast czekać na następne automatyczne sprawdzenie.
- **Wersja aktualizacji (updatev\_)**

  - **Co robi to ustawienie:** To pole zazwyczaj wyświetla najnowszą dostępną wersję modułu wykrytą przez sprawdzanie aktualizacji.
  - **Efekt zmiany tego ustawienia:** Jest to pole tylko do wyświetlania i nie można go bezpośrednio zmienić. Dostarcza informacji o najnowszej wersji.
  - **Zalecana wartość:** N/A (Tylko do wyświetlania).
  - **Scenariusz/przykład dla sprzedawcy:** Widzisz tutaj „1.2.3”, co oznacza, że dostępna jest nowsza wersja niż Twoja obecna (np. 1.2.2).
- **Najnowsza wersja (dupcms\_LATEST)**

  - **Co robi to ustawienie:** Podobnie jak „Wersja aktualizacji”, to pole wyświetla najnowszą dostępną wersję modułu.
  - **Efekt zmiany tego ustawienia:** Jest to pole tylko do wyświetlania.
  - **Zalecana wartość:** N/A (Tylko do wyświetlania).
  - **Scenariusz/przykład dla sprzedawcy:** Możesz szybko sprawdzić, czy zainstalowany moduł jest najnowszy, porównując tę wartość z zainstalowaną wersją.
- **Miniatury (dupcms\_MINIATURES)**

  - **Co robi to ustawienie:** To ustawienie prawdopodobnie kontroluje, czy miniaturowe obrazy lub ikony są wyświetlane w interfejsie modułu, być może związane ze sprawdzaniem aktualizacji lub innymi elementami wizualnymi w panelu administracyjnym modułu.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone:* Możesz zobaczyć małe ikony lub obrazy w konfiguracji modułu lub powiadomieniach o aktualizacjach.
    - *Gdy wyłączone:* Te elementy wizualne byłyby ukryte, co skutkowałoby bardziej tekstowym interfejsem.
  - **Zalecana wartość:** **TAK** (Włączone).
  - **Scenariusz/przykład dla sprzedawcy:** Preferujesz bardziej wizualnie bogaty interfejs w swoim Panelu administracyjnym, więc pozostawiasz to włączone, aby widzieć wszelkie odpowiednie ikony.
- **ID Kategorii CMS (dupcms\_ID\_CMSCAT)**

  - **Co robi to ustawienie:** To ustawienie jest kluczowe dla podstawowej funkcjonalności modułu. Pozwala wybrać domyślną kategorię CMS, w której będą umieszczane zduplikowane strony CMS.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy wybrana jest konkretna kategoria:* Wszystkie nowe zduplikowane strony CMS zostaną automatycznie przypisane do tej kategorii. Pomaga to w organizacji treści.
    - *Gdy nie wybrano żadnej kategorii (lub domyślnej):* Moduł może domyślnie ustawić tę samą kategorię co oryginalna strona lub kategorię główną, w zależności od jego wewnętrznej logiki. Ustawienie konkretnej kategorii daje większą kontrolę.
  - **Zalecana wartość:** Wybierz logiczną kategorię domyślną, taką jak „Informacje” lub konkretną kategorię, której używasz do nowych stron.
  - **Scenariusz/przykład dla sprzedawcy:** Często duplikujesz strony „Informacji prawnej” dla różnych regionów. Możesz ustawić to na swoją kategorię CMS „Strony prawne”, aby wszystkie nowe duplikaty automatycznie tam trafiały, co ułatwia ich znajdowanie i zarządzanie.

#### Jak korzystać z funkcji duplikowania

Rzeczywista akcja duplikowania odbywa się na standardowej liście stron CMS PrestaShop:

1. Przejdź do **Ulepszenia > Wygląd > Strony** w Panelu administracyjnym PrestaShop.
2. Zobaczysz listę swoich istniejących stron CMS.
3. Zlokalizuj stronę CMS, którą chcesz zduplikować.
4. W kolumnie „Akcje” (zazwyczaj reprezentowanej przez trzy kropki lub menu rozwijane) dla tej konkretnej strony CMS znajdziesz nową opcję dodaną przez ten moduł: **„Duplikuj”** (lub podobną ikonę/tekst).
5. Kliknij „Duplikuj”.
6. Moduł utworzy dokładną kopię strony, w tym jej zawartość, informacje meta, przyjazny URL i status aktywności. Nowa strona będzie zazwyczaj miała nazwę taką jak „Kopia [Nazwa oryginalnej strony]” lub podobną, którą możesz następnie edytować.
7. Zduplikowana strona zostanie umieszczona w kategorii CMS wybranej w konfiguracji modułu (jeśli `dupcms_ID_CMSCAT` jest ustawione) lub w tej samej kategorii co oryginał.
8. Następnie możesz edytować nowo zduplikowaną stronę, aby zmienić jej tytuł, zawartość, URL i inne ustawienia według potrzeb.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Aktualizacje MyPresta.eu | TAK | Włącza automatyczne sprawdzanie aktualizacji modułu. |
| Konfiguracja modułu | Aktualizacja | N/A (Przycisk) | Inicjuje ręczne sprawdzanie aktualizacji modułu. |
| Konfiguracja modułu | Wersja aktualizacji | N/A (Wyświetlanie) | Pokazuje najnowszą dostępną wersję modułu. |
| Konfiguracja modułu | Najnowsza wersja | N/A (Wyświetlanie) | Wyświetla najnowszą wykrytą wersję modułu. |
| Konfiguracja modułu | Miniatury | TAK | Kontroluje wyświetlanie elementów wizualnych/ikon w interfejsie modułu. |
| Konfiguracja modułu | ID Kategorii CMS | Wybierz kategorię | Ustawia domyślną kategorię CMS dla zduplikowanych stron. |
| Lista stron CMS (Wygląd > Strony) | Akcja Duplikuj | N/A (Przycisk) | Tworzy dokładną kopię wybranej strony CMS. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zduplikowałem stronę, ale nie mogę jej znaleźć.**
O: Sprawdź kategorię CMS, którą wybrałeś w konfiguracji modułu (`dupcms_ID_CMSCAT`). Jeśli nie ustawiłeś żadnej, może znajdować się w tej samej kategorii co oryginalna strona lub w głównej kategorii CMS. Upewnij się również, że szukasz „Kopia [Nazwa oryginalnej strony]” lub podobnego, ponieważ moduł dodaje prefiks do tytułu zduplikowanej strony.

**P: Zduplikowana strona ma ten sam przyjazny URL co oryginał. Czy to problem?**
O: Tak, może to powodować konflikty i problemy z SEO. Po zduplikowaniu strony **zawsze natychmiast edytuj nową stronę** i zmień jej przyjazny URL (znany również jako „Przepisanie URL” lub „Slug”) na coś unikalnego i opisowego dla nowej treści. PrestaShop zazwyczaj dodaje numer (np. `-1`) do URL-a, ale najlepiej jest dostosować go samodzielnie.

**P: Nie widzę opcji „Duplikuj” na liście stron CMS.**
O:

1. Przejdź do **Moduły > Menedżer modułów** i upewnij się, że moduł „Duplikowanie strony CMS” jest zainstalowany i włączony.
2. Wyczyść pamięć podręczną PrestaShop: Przejdź do **Zaawansowane > Wydajność**, przewiń w dół i kliknij „Wyczyść pamięć podręczną”.
3. Jeśli nadal się nie pojawia, spróbuj ponownie zainstalować moduł (po wykonaniu kopii zapasowej sklepu). Jeśli problem nadal występuje, skontaktuj się z pomocą techniczną MyPresta.eu.

**P: Czy ten moduł duplikuje obrazy i pliki połączone w treści strony CMS?**
O: Tak, moduł duplikuje całą zawartość HTML strony. Jeśli Twoje obrazy są połączone za pomocą ścieżek względnych w treści, będą nadal działać. Jeśli zostały przesłane bezpośrednio za pomocą edytora tekstu sformatowanego, odniesienia zostaną skopiowane. Jednak moduł nie duplikuje rzeczywistych *plików* obrazów na Twoim serwerze; duplikuje *odniesienia* do nich. Jest to zazwyczaj pożądane zachowanie.

**P: Czy mogę zduplikować kategorię CMS?**
O: Nie, ten moduł jest specjalnie zaprojektowany do duplikowania pojedynczych *stron* CMS, a nie całych *kategorii* CMS.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera techniczny przegląd dla programistów i webmasterów, którzy chcą zrozumieć, debugować lub rozszerzyć moduł „Duplikowanie strony CMS”.

### 4.1 Przegląd architektury

Moduł „Duplikowanie strony CMS” to lekki moduł PrestaShop, skupiający się głównie na rozszerzaniu funkcjonalności istniejącego `AdminCmsController`. Wykorzystuje system hooków PrestaShop (`actionAdminControllerSetMedia`) do wstrzykiwania JavaScriptu, który modyfikuje domyślną tabelę listy stron CMS, dodając akcję „Duplikuj”. Podstawowa logika duplikowania jest obsługiwana przez plik `dupcms.php` modułu, który przechwytuje żądania AJAX w celu wykonania operacji bazodanowych wymaganych do kopiowania danych strony CMS. Nie wprowadza nowych tabel bazodanowych ani złożonych modeli obiektów, opierając się zamiast tego na bezpośredniej manipulacji istniejącymi tabelami `ps_cms` i `ps_cms_lang`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wprowadza żadnych niestandardowych kontrolerów front-office ani back-office. Jego funkcjonalność jest zintegrowana z istniejącym `AdminCmsController` za pośrednictwem hooków i AJAX.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas ani definicji `ObjectModel`. Bezpośrednio współpracuje z podstawowymi klasami PrestaShop `CMS` i `CMSCategory` oraz ich powiązanymi tabelami bazodanowymi.

### 4.4 Zasoby JavaScript (`views/js/`)

- **`dupcms/views/js/dupcms.js`**
  - **Zakres:** Panel administracyjny (konkretnie strona `AdminCms`).
  - **Odpowiedzialność:**
    - Ten skrypt jest wstrzykiwany na stronę `AdminCmsController` (Ulepszenia > Wygląd > Strony) za pośrednictwem hooka `actionAdminControllerSetMedia`.
    - Czeka na gotowość DOM.
    - Identyfikuje kolumnę „Akcje” w tabeli listy stron CMS.
    - Dla każdego wiersza strony CMS dynamicznie dodaje nowy przycisk lub link akcji „Duplikuj” do istniejącego menu rozwijanego akcji.
    - Dołącza słuchacz zdarzeń (np. `click`) do tych nowo dodanych elementów „Duplikuj”.
    - Po kliknięciu akcji „Duplikuj” wyodrębnia `id_cms` strony do zduplikowania.
    - Następnie wysyła żądanie AJAX do głównego pliku PHP modułu (`dupcms/dupcms.php`) z `id_cms` i parametrem akcji (np. `action=duplicateCms`).
    - Obsługuje odpowiedź AJAX, zazwyczaj wyświetlając komunikat o sukcesie lub błędzie i potencjalnie odświeżając listę stron CMS, aby pokazać nowo zduplikowaną stronę.
    - Może również zawierać logikę powiadomień o aktualizacjach lub innych dynamicznych elementów interfejsu użytkownika związanych z konfiguracją modułu.

### 4.5 Arkusze stylów CSS (`views/css/`)

- **`dupcms/views/css/dupcms.css`**
  - **Zakres:** Panel administracyjny (konkretnie strona `AdminCms`).
  - **Odpowiedzialność:**
    - Zapewnia stylizację dla dynamicznie dodanego linku/przycisku akcji „Duplikuj”, aby zapewnić jego wizualną integrację z motywem Panelu administracyjnego PrestaShop.
    - Może zawierać style dla wszelkich powiadomień specyficznych dla modułu lub elementów interfejsu użytkownika w kontekście `AdminCms`.
    - Kluczowe selektory klas CSS, które programiści mogą nadpisać: Szukaj klas takich jak `.dupcms-duplicate-action` lub podobnych w wstrzykniętym kodzie HTML, aby dostosować jego wygląd.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł nie używa żadnych niestandardowych plików szablonów Smarty (`.tpl`). Wszystkie jego modyfikacje interfejsu użytkownika w Panelu administracyjnym są wykonywane dynamicznie za pomocą JavaScriptu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele baz danych**:

  - Moduł nie tworzy żadnych nowych niestandardowych tabel baz danych.
  - Działa na istniejących tabelach PrestaShop:
    - `ps_cms`: Przechowuje ogólne informacje o stronie CMS (status aktywności, pozycja itp.).
    - `ps_cms_lang`: Przechowuje treści strony CMS specyficzne dla języka (tytuł, meta opis, treść, przyjazny URL).
    - `ps_cms_shop`: Łączy strony CMS z konkretnymi sklepami w środowisku wielosklepowym.
    - `ps_configuration`: Przechowuje ustawienia konfiguracyjne modułu (np. `dupcms_ID_CMSCAT`, `mypresta_updates`).
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler Panelu administracyjnego ustawia swoje media (JS/CSS). | Jest to główny hook używany przez moduł. Wstrzykuje `dupcms.js` i `dupcms.css` na stronę `AdminCmsController`, umożliwiając modułowi modyfikację listy stron CMS i dodanie akcji „Duplikuj”. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnego wsparcia, aktualizacji i pobrania najnowszej wersji modułu „Duplikowanie strony CMS”, zaloguj się na swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu.
