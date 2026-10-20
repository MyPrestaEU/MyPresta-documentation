---
title: "Zwiększenie limitu znaków w opisie produktu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop „Zwiększenie limitu znaków w opisie produktu” od MyPresta.eu."
sidebar:
  label: "Zwiększenie limitu znaków w opisie produktu - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Increase characters limit in product description na MyPresta.eu](https://mypresta.eu/modules/administration-tools/increase-characters-limit-in-product-description.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/increase-characters-limit-in-product-description/)
>
> ---


# Zwiększenie limitu znaków w opisie produktu

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5 (Zawsze rozszerzane do PHP 8.5 w celu zapewnienia przyszłościowej kompatybilności)
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu, aby uzyskać dostęp do jego ustawień. Jest to główny i jedyny ekran konfiguracji dla tego modułu.

#### Ustawienia i opcje:

1. **Długość opisu produktu**

   - **Co robi to ustawienie:** To pole kontroluje maksymalną liczbę znaków dozwolonych w głównym polu „Opis” dla wszystkich Twoich produktów w Panelu administracyjnym PrestaShop. Domyślny limit PrestaShop to 21 844 znaki.
   - **Efekt zmiany tego ustawienia:**
     - *Po ustawieniu na wyższą liczbę:* Będziesz mógł wprowadzić więcej znaków do pola opisu produktu podczas edycji produktów. Pozwala to na bardziej szczegółową treść.
     - *Po ustawieniu na niższą liczbę (niezalecane):* Ograniczyłoby to Twoją zdolność do dodawania szczegółowych treści, potencjalnie obcinając istniejące dłuższe opisy.
   - **Zalecana wartość:** Znacznie wyższa liczba, taka jak `65535` lub `16777215` (co odpowiada limitom `MEDIUMTEXT` lub `LONGTEXT` w MySQL, skutecznie usuwając praktyczne limity dla większości treści). Możesz również ustawić `0` lub pozostawić puste, aby całkowicie usunąć limit i użyć maksymalnej możliwej wartości.
   - **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz zaawansowane technologicznie gadżety i musisz uwzględnić obszerne specyfikacje techniczne, listy kompatybilności i instrukcje obsługi bezpośrednio w opisie produktu. Ustawienie tej wartości na `65535` zapewnia Ci wystarczającą przestrzeń.
2. **Długość nazwy produktu**

   - **Co robi to ustawienie:** To pole kontroluje maksymalną liczbę znaków dozwolonych dla pola „Nazwa produktu” dla wszystkich Twoich produktów. Domyślny limit PrestaShop to zazwyczaj 128 lub 255 znaków, w zależności od wersji.
   - **Efekt zmiany tego ustawienia:**
     - *Po ustawieniu na wyższą liczbę:* Możesz używać dłuższych nazw produktów, co może być przydatne dla bardzo specyficznych produktów, włączając numery modeli, lub dla celów SEO, gdzie dłuższe, opisowe tytuły są korzystne.
     - *Po ustawieniu na niższą liczbę (niezalecane):* Ograniczyłoby to nazewnictwo produktów, potencjalnie powodując problemy z istniejącymi produktami lub utrudniając rozróżnianie pozycji.
   - **Zalecana wartość:** Wyższa liczba, taka jak `512` lub `1024`, jeśli potrzebujesz bardzo długich nazw produktów. Dla większości sklepów domyślna wartość jest wystarczająca, ale jeśli masz specyficzne potrzeby (np. włączenie pełnych numerów części lub szczegółowych opisów modeli), zwiększenie tej wartości jest pomocne.
   - **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz sprzęt przemysłowy, a nazwy produktów często zawierają producenta, model, specyficzne cechy i numery wersji (np. „Mieszalnik przemysłowy XYZ Corp. Heavy Duty Model 5000-A z regulacją prędkości i lejem ze stali nierdzewnej”). Zwiększenie tego limitu do `512` pozwala na umieszczenie pełnej, opisowej nazwy.
3. **PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG** (Jest to standardowe ustawienie PrestaShop, niekontrolowane bezpośrednio przez moduł, ale często istotne dla edycji treści)

   - **Co robi to ustawienie:** To podstawowe ustawienie PrestaShop określa, czy pracownicy mogą wybrać język dla pola formularza bezpośrednio w formularzu, czy też język formularza jest określany przez język panelu administracyjnego pracownika. Nie jest to ustawienie modułu, ale jest często widoczne lub istotne podczas pracy z treściami wielojęzycznymi.
   - **Efekt zmiany tego ustawienia:**
     - *Po włączeniu:* Pracownicy mogą przełączać język dla pól tekstowych (takich jak opisy produktów) bezpośrednio na stronie edycji produktu, co pozwala im wprowadzać treści w różnych językach bez zmiany całego języka panelu administracyjnego.
     - *Po wyłączeniu:* Język pól tekstowych będzie odpowiadał aktualnemu językowi panelu administracyjnego pracownika. Aby edytować treści w innym języku, pracownik musi zmienić język swojego panelu administracyjnego.
   - **Zalecana wartość:** Generalnie **TAK** dla sklepów wielojęzycznych z wieloma edytorami treści, ponieważ poprawia to przepływ pracy.
   - **Scenariusz / przykład dla sprzedawcy:** Masz francuskojęzycznego edytora treści i anglojęzycznego edytora treści. Jeśli to ustawienie jest włączone, francuski edytor może napisać francuski opis, a następnie przełączyć rozwijaną listę języków na angielski, aby napisać angielski opis, wszystko na tej samej stronie produktu.

#### 2.1.1 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Długość opisu produktu | `65535` lub `0` (bez limitu) | Zwiększa maksymalną liczbę znaków dla opisów produktów. Pozwala na bardziej szczegółową treść i lepsze SEO. |
| Konfiguracja modułu | Długość nazwy produktu | `512` lub `1024` | Zwiększa maksymalną liczbę znaków dla nazw produktów. Przydatne dla bardzo specyficznych lub opisowych tytułów produktów. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Zwiększyłem limit znaków, ale moje opisy produktów nadal wydają się być obcięte na stronie głównej. Co jest nie tak?**
O: Jest to zazwyczaj problem związany z motywem, a nie z modułem.
- **Sprawdź ustawienia wyświetlania swojego motywu:** Niektóre motywy mogą mieć własne CSS lub JavaScript, które obcina długi tekst, aby dopasować go do określonego układu. Może być konieczne skonsultowanie się z dokumentacją motywu lub programistą internetowym w celu dostosowania tych ustawień.
- **Wyczyść pamięć podręczną Smarty:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop, przewiń w dół do „Wyczyść pamięć podręczną” i kliknij „Wyczyść pamięć podręczną”. Czasami stare pliki szablonów są buforowane.
- **Zweryfikuj w Panelu administracyjnym:** Sprawdź dokładnie, czy pełny opis jest poprawnie zapisany na stronie edycji produktu w Panelu administracyjnym. Jeśli jest tam obcięty, moduł mógł nie zostać poprawnie zastosowany (choć jest to rzadkie).

**P: Czy ten moduł wpływa na SEO?**
O: Pośrednio tak, w bardzo pozytywny sposób. Pozwalając na pisanie dłuższych, bardziej szczegółowych i bogatych w słowa kluczowe opisów produktów, dostarczasz więcej treści do indeksowania przez wyszukiwarki. Może to prowadzić do lepszych pozycji w rankingach dla odpowiednich zapytań wyszukiwania i przyciągnąć więcej ruchu organicznego na Twoje strony produktów.

**P: Czy ten moduł spowolni mój sklep?**
O: Nie, ten moduł ma znikomy wpływ na wydajność sklepu. Głównie modyfikuje definicje kolumn bazy danych podczas instalacji/konfiguracji. Po skonfigurowaniu nie dodaje żadnych złożonych procesów ani skryptów front-office, które spowolniłyby czas ładowania strony. Jedynym potencjalnym „spowolnieniem” może być pisanie niezwykle długich opisów, których załadowanie z bazy danych zajmuje więcej czasu, ale jest to zazwyczaj minimalne i rekompensowane przez korzyści SEO.

**P: Zmieniłem limity, ale nie widzę zmian na stronie edycji produktu. Co powinienem zrobić?**
O:
- **Zapisz konfigurację modułu:** Upewnij się, że kliknąłeś przycisk „Zapisz” po zmianie limitów znaków na stronie konfiguracji modułu.
- **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”.
- **Odśwież przeglądarkę:** Czasami przeglądarka buforuje stare formularze. Wykonaj twarde odświeżenie (Ctrl+F5 lub Cmd+Shift+R).
- **Wyloguj się i zaloguj ponownie:** W przypadku niektórych zmian administracyjnych, wylogowanie się i ponowne zalogowanie do Panelu administracyjnego może zapewnić odświeżenie wszystkich danych sesji.

**P: Czy istnieje maksymalny limit, który mogę ustawić?**
O: Chociaż moduł pozwala ustawić praktycznie dowolną liczbę, praktyczny limit jest określany przez możliwości Twojej bazy danych. Dla pól `TEXT` w MySQL maksymalna liczba znaków to `65 535`. Dla `MEDIUMTEXT` to `16 777 215` znaków, a dla `LONGTEXT` to `4 294 967 295` znaków. Ustawienie `0` lub pozostawienie pola pustego zazwyczaj domyślnie ustawi największy możliwy typ `TEXT`, skutecznie usuwając wszelkie praktyczne limity dla większości treści. Dla nazw produktów `255` lub `512` znaków jest zazwyczaj więcej niż wystarczające.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Zwiększenie limitu znaków w opisie produktu” to lekki moduł PrestaShop zaprojektowany przede wszystkim do modyfikacji schematu bazy danych dla pól tekstowych związanych z produktami. Działa poprzez zmianę `type` i `size` określonych kolumn w tabeli `ps_product_lang` (dla opisów) oraz tabelach `ps_product` / `ps_product_lang` (dla nazw) podczas instalacji i konfiguracji. Nie wprowadza żadnych kontrolerów front-office, niestandardowych klas ani złożonego JavaScript/CSS. Jego podstawowa funkcjonalność jest wykonywana za pomocą metod `install()` i `getContent()` głównej klasy modułu.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł **nie** wprowadza żadnych niestandardowych klas ani definicji `ObjectModel`. Bezpośrednio współdziała z istniejącymi podstawowymi tabelami bazy danych PrestaShop i ustawieniami konfiguracji.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików CSS.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików szablonów Smarty. Formularz konfiguracji jest renderowany bezpośrednio w metodzie `getContent()` za pomocą standardowych komponentów `HelperForm` PrestaShop.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele bazy danych

Moduł przede wszystkim współdziała z następującymi podstawowymi tabelami PrestaShop:

- `ps_product_lang`:
  - Kolumna **`description`**: Zmodyfikowana na większy typ `TEXT` (np. `MEDIUMTEXT` lub `LONGTEXT`), aby pomieścić więcej znaków.
  - Kolumna **`description_short`**: Nie jest bezpośrednio modyfikowana przez ten moduł, ale często jest powiązana.
  - Kolumna **`name`**: Zmodyfikowana na większy typ `VARCHAR` (np. `VARCHAR(512)`), aby pomieścić więcej znaków.
- `ps_configuration`:
  - `chr_max_description_length`: Przechowuje skonfigurowaną maksymalną długość dla opisów produktów.
  - `chr_max_name_length`: Przechowuje skonfigurowaną maksymalną długość dla nazw produktów.
  - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Standardowy klucz konfiguracji PrestaShop, nie utworzony przez moduł, ale często odwoływany w kontekście edycji treści.

Metoda `install()` modułu zawiera zapytania SQL do zmiany tych kolumn tabel. Metoda `uninstall()` próbuje przywrócić te zmiany, chociaż w zależności od stanu bazy danych może być wymagana ręczna weryfikacja.

#### Tabela zarejestrowanych hooków

Ten moduł **nie** rejestruje żadnych hooków wyświetlania front-office ani back-office. Jego funkcjonalność jest całkowicie oparta na backendzie poprzez modyfikację schematu bazy danych.

Metoda `install()` modułu może niejawnie używać `Configuration::updateValue()`, co nie rejestruje bezpośrednio hooków, ale przechowuje wartości.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Zwiększenie limitu znaków w opisie produktu”, zapoznaj się ze swoim kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
