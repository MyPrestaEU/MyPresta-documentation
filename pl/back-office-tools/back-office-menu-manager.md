---
title: "Menedżer menu Panelu administracyjnego - Instrukcja dla sprzedawcy i Przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Menedżer menu Panelu administracyjnego” od MyPresta.eu."
sidebar:
  label: "Menedżer menu Panelu administracyjnego - Instrukcja dla sprzedawcy i Przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Back office menu manager na MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-menu-manager.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/back-office-tools/back-office-menu-manager/)
>
> ---


# Menedżer menu Panelu administracyjnego

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji, kliknięcie „Konfiguruj” przeniesie Cię do głównego ekranu konfiguracji modułu „Menedżer menu Panelu administracyjnego”.

Ten ekran zazwyczaj zawiera standardowe ustawienia modułu, które mogą obejmować:

- **Włącz/Wyłącz moduł:**

  - **Co robi to ustawienie:** Jest to główny przełącznik do aktywacji lub dezaktywacji funkcjonalności modułu.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączony:* Funkcje modułu, w tym nowe opcje zarządzania menu, będą aktywne w Twoim Panelu administracyjnym.
    - *Gdy wyłączony:* Moduł przestanie wpływać na menu Panelu administracyjnego, a domyślne zachowanie menu PrestaShop zostanie przywrócone.
  - **Zalecana wartość:** **TAK** (Włączony), aby używać modułu.
  - **Scenariusz/przykład dla sprzedawcy:** Jeśli testujesz moduł lub tymczasowo chcesz wrócić do domyślnego menu PrestaShop, możesz go tutaj wyłączyć.
- **Resetuj ustawienia modułu:**

  - **Co robi to ustawienie:** Ta opcja pozwala przywrócić wszystkie ustawienia specyficzne dla modułu i potencjalnie wszelkie niestandardowe konfiguracje menu do ich domyślnego stanu.
  - **Efekt zmiany tego ustawienia:**
    - *Po kliknięciu:* Wszystkie Twoje niestandardowe układy menu i preferencje modułu zostaną usunięte, a moduł będzie działał tak, jakby został właśnie zainstalowany po raz pierwszy.
  - **Zalecana wartość:** Używaj z ostrożnością. Kliknij tylko, jeśli chcesz całkowicie zrestartować konfigurację menu.
  - **Scenariusz/przykład dla sprzedawcy:** Jeśli wprowadziłeś wiele zmian i chcesz zacząć od nowa, lub jeśli napotkasz nieoczekiwany problem i chcesz wykluczyć problemy z konfiguracją, może to być przydatny krok rozwiązywania problemów.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

Ten moduł wprowadza nową, dedykowaną sekcję w Twoim Panelu administracyjnym PrestaShop do zarządzania zakładkami menu.

#### Nazwa ekranu i lokalizacja w menu: AdminMenuTabsController

- **Lokalizacja w menu:** Po zainstalowaniu modułu znajdziesz nową pozycję menu, zazwyczaj w sekcji **Zaawansowane** lub podobnej sekcji administracyjnej, o nazwie takiej jak **„Menedżer menu”** lub **„Menu Panelu administracyjnego”**. Kliknięcie jej przeniesie Cię do ekranu `AdminMenuTabsController`.
- **Dostępne akcje i ustawienia:**
  Ten ekran zapewnia kompleksowy widok siatki (tabeli) wszystkich zakładek menu aktualnie dostępnych w Twoim Panelu administracyjnym PrestaShop. Dla każdej zakładki menu zazwyczaj zobaczysz:

  - **ID:** Unikalny identyfikator zakładki menu.
  - **Nazwa:** Nazwa wyświetlana zakładki menu (np. „Zamówienia”, „Produkty”, „Klienci”).
  - **Zakładka nadrzędna:** Do której głównej pozycji menu należy ta zakładka (np. „Zamówienia” jest nadrzędne dla „Zamówień”, „Faktur”, „Korekt”).
  - **Pozycja:** Numeryczna kolejność zakładki w jej grupie nadrzędnej.
  - **Przełącznik Aktywny/Nieaktywny:** Przełącznik do włączania lub wyłączania widoczności zakładki menu.
  - **Akcje Edytuj/Usuń:** Przyciski do modyfikowania szczegółów konkretnej zakładki lub jej usuwania (używaj usuwania z niezwykłą ostrożnością, ponieważ może to usunąć podstawową funkcjonalność).

  **Kluczowe funkcjonalności, które możesz tutaj wykonać:**

  - **Zmień kolejność pozycji menu:** Zazwyczaj możesz przeciągać i upuszczać wiersze w siatce lub ręcznie zmieniać wartość „Pozycja”, aby zmienić kolejność wyświetlania pozycji menu.
  - **Ukryj/Pokaż pozycje menu:** Użyj przełącznika aktywne/nieaktywne, aby ukryć pozycje menu, których nie używasz lub które chcesz ograniczyć dla niektórych ról personelu (jeśli połączone z natywnymi uprawnieniami PrestaShop).
  - **Edytuj szczegóły pozycji menu:** Możesz zmienić nazwę wyświetlaną pozycji menu, jej ikonę lub jej powiązanie z elementem nadrzędnym (chociaż zmiana powiązań z elementami nadrzędnymi dla podstawowych zakładek jest ogólnie niezalecana bez zaawansowanej wiedzy).
  - **Dodaj nowe pozycje menu:** Chociaż mniej powszechne dla tego konkretnego modułu (który koncentruje się na zarządzaniu *istniejącymi* zakładkami), niektóre zaawansowane wersje mogą pozwalać na dodawanie niestandardowych linków menu.
- **Efekt zmian:**

  - **Ukrycie zakładki:** Zakładka natychmiast zniknie z menu Panelu administracyjnego dla wszystkich użytkowników (chyba że istnieją specyficzne nadpisania uprawnień).
  - **Zmiana kolejności zakładek:** Kolejność pozycji menu zmieni się natychmiast w nawigacji Panelu administracyjnego.
  - **Edycja nazwy zakładki:** Nazwa wyświetlana w menu Panelu administracyjnego zostanie zaktualizowana.
- **Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

  1. **Początkowa konfiguracja:** Przejrzyj wszystkie główne pozycje menu i ich podpozycje. Zdecyduj, które z nich Twój zespół używa regularnie, rzadko lub nigdy.
  2. **Uporządkuj:** Dla rzadko lub nigdy nieużywanych pozycji, użyj przełącznika „Aktywny/Nieaktywny”, aby je ukryć. To znacznie upraszcza menu.
  3. **Ustal priorytety:** Zmień kolejność często używanych pozycji, aby znajdowały się na górze odpowiednich sekcji. Na przykład, jeśli spędzasz większość czasu na „Zamówieniach”, upewnij się, że „Zamówienia” jest pierwszą podpozycją w głównym menu „Zamówienia”.
  4. **Regularnie przeglądaj:** W miarę ewolucji operacji Twojego sklepu lub instalacji nowych modułów (które często dodają własne pozycje menu), ponownie odwiedź ten ekran, aby utrzymać zoptymalizowane menu.

#### Nazwa ekranu i lokalizacja w menu: index.php (adminmenu/controllers/admin/index.php)

Ten plik, `index.php` w katalogu kontrolera administracyjnego, zazwyczaj służy jako symbol zastępczy lub punkt wejścia dla funkcjonalności kontrolera, a nie jako samodzielny ekran z konfigurowalnymi opcjami. W PrestaShop rzeczywista logika i wyświetlanie dla kontrolera administracyjnego są obsługiwane przez główną klasę (np. `AdminMenuTabsController.php`).

Dlatego nie będziesz bezpośrednio wchodzić w interakcje z ekranem „index.php”. Jego obecność jest częścią wewnętrznej struktury modułu, zapewniając prawidłowe działanie `AdminMenuTabsController`. Wszystkie Twoje interakcje będą odbywać się za pośrednictwem interfejsu `AdminMenuTabsController` opisanego powyżej.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz/Wyłącz moduł | Włączony | Aktywuje/dezaktywuje funkcje zarządzania menu modułu. |
| Konfiguracja modułu | Resetuj ustawienia modułu | N/A (Akcja) | Resetuje wszystkie ustawienia modułu i konfiguracje menu do domyślnych. Używaj z ostrożnością. |
| AdminMenuTabsController | Nazwa zakładki (np. „Zamówienia”) | Oryginalna nazwa PrestaShop | Wyświetla nazwę pozycji menu. Można edytować. |
| AdminMenuTabsController | Zakładka nadrzędna | Oryginalna zakładka nadrzędna PrestaShop | Pokazuje główną kategorię menu dla tej pozycji. |
| AdminMenuTabsController | Pozycja | Różna | Kontroluje kolejność wyświetlania pozycji menu w jej elemencie nadrzędnym. Można zmienić przez przeciąganie i upuszczanie lub bezpośrednie wprowadzanie. |
| AdminMenuTabsController | Przełącznik Aktywny/Nieaktywny | Aktywny | Przełącza widoczność pozycji menu w Panelu administracyjnym. |
| AdminMenuTabsController | Akcje Edytuj/Usuń | N/A (Akcja) | Pozwala na modyfikację szczegółów zakładki lub jej usunięcie (usuwaj z ostrożnością). |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Ukryłem pozycję menu, ale nadal jest widoczna dla niektórych użytkowników. Dlaczego?**
O: Ten moduł zarządza *widocznością* i *kolejnością* pozycji menu. Natywne uprawnienia użytkowników PrestaShop (w **Zaawansowane > Zespół > Profile** i **Uprawnienia**) określają, *kto ma dostęp do czego*. Jeśli profil użytkownika ma jawne uprawnienia do zakładki, może ją nadal widzieć, nawet jeśli oznaczyłeś ją jako nieaktywną w tym module. Zawsze sprawdzaj zarówno ustawienia tego modułu, jak i uprawnienia PrestaShop.

**P: Wprowadziłem zmiany, ale menu się nie zaktualizowało. Co powinienem zrobić?**
O:

1. **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność**. Kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Jest to często konieczne, aby zmiany w Panelu administracyjnym zaczęły obowiązywać.
2. **Odśwież przeglądarkę:** Czasami konieczne jest twarde odświeżenie przeglądarki (Ctrl+F5 lub Cmd+Shift+R), aby wyczyścić lokalną pamięć podręczną przeglądarki.
3. **Sprawdź status modułu:** Upewnij się, że moduł „Menedżer menu Panelu administracyjnego” jest nadal włączony w **Moduły > Menedżer modułów**.

**P: Czy mogę dodać całkowicie nowe niestandardowe linki do menu Panelu administracyjnego za pomocą tego modułu?**
O: Ten moduł koncentruje się głównie na zarządzaniu *istniejącymi* zakładkami menu PrestaShop. Chociaż niektóre zaawansowane wersje mogą oferować tworzenie niestandardowych linków, jego głównym celem jest umożliwienie zarządzania domyślną strukturą menu PrestaShop. Jeśli potrzebujesz dodać złożone niestandardowe linki, możesz potrzebować bardziej zaawansowanego modułu lub niestandardowego rozwoju.

**P: Przypadkowo usunąłem podstawową pozycję menu PrestaShop. Jak ją odzyskać?**
O: Usuwanie podstawowych pozycji menu jest ogólnie niezalecane. Jeśli to zrobiłeś, najbezpieczniejszym sposobem na jej przywrócenie jest:

1. **Wyłącz i ponownie włącz moduł:** Przejdź do **Moduły > Menedżer modułów**, znajdź „Menedżer menu Panelu administracyjnego”, wyłącz go, a następnie ponownie włącz. To często wyzwala ponowną inicjalizację domyślnych wpisów menu.
2. **Resetuj ustawienia modułu:** Jeśli powyższe nie zadziała, przejdź do strony konfiguracji modułu i użyj opcji „Resetuj ustawienia modułu”. Pamiętaj, że to usunie WSZYSTKIE Twoje niestandardowe konfiguracje menu.
3. **Przywróć z kopii zapasowej:** W ostateczności, jeśli brakuje krytycznych pozycji menu, może być konieczne przywrócenie bazy danych z kopii zapasowej wykonanej *przed* usunięciem.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera przegląd techniczny dla programistów i webmasterów pracujących z modułem „Menedżer menu Panelu administracyjnego”.

### 4.1 Przegląd architektury

Moduł „Menedżer menu Panelu administracyjnego” przede wszystkim rozszerza podstawową funkcjonalność Panelu administracyjnego PrestaShop poprzez nadpisywanie specyficznych klas pomocniczych w celu ponownego wprowadzenia możliwości zarządzania menu. Wykorzystuje wzorzec MVC PrestaShop, z dedykowanym kontrolerem administracyjnym (`AdminMenuTabsController`), aby zapewnić interfejs użytkownika do zarządzania zakładkami menu. Moduł współdziała z tabelą bazy danych `ps_tab`, która przechowuje informacje o pozycjach menu Panelu administracyjnego. Kluczową decyzją architektoniczną jest użycie nadpisań do modyfikacji podstawowego zachowania PrestaShop bez bezpośredniej zmiany podstawowych plików, co zapewnia lepszą kompatybilność i ścieżki aktualizacji.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**:
  Ten moduł nie zawiera żadnych kontrolerów front-office, ponieważ jego funkcjonalność jest przeznaczona wyłącznie dla Panelu administracyjnego PrestaShop.
- **Kontrolery administracyjne Back-Office**:

  - `adminmenu/controllers/admin/AdminMenuTabs.php`

    - **Nazwa klasy i klasa nadrzędna**: `AdminMenuTabsController` rozszerza `ModuleAdminController`.
    - **Nazwa zakładki i zarządzana encja**: Ten kontroler zarządza encją `Tab` (reprezentującą pozycje menu Panelu administracyjnego). Tworzy dedykowany wpis menu w Panelu administracyjnym dla „Menedżera menu”.
    - **Odpowiedzialność**: Jest to główny kontroler interfejsu użytkownika modułu. Obsługuje wyświetlanie listy wszystkich zakładek Panelu administracyjnego, umożliwiając administratorom ich przeglądanie, edytowanie, włączanie/wyłączanie i zmienianie kolejności. Zazwyczaj używa `HelperList` do wyświetlania siatki i `HelperForm` do wszelkich formularzy edycji. Przetwarza żądania POST do zapisywania zmian (np. aktualizacji pozycji, przełączania statusu).
  - `adminmenu/controllers/admin/index.php`

    - **Odpowiedzialność**: Ten plik jest standardowym symbolem zastępczym w strukturze kontrolerów PrestaShop. Zazwyczaj zawiera prostą instrukcję `die('No direct script access allowed');`, aby zapobiec bezpośredniemu dostępowi do katalogu i zapewnić, że żądania są kierowane przez dispatcher PrestaShop. Nie zawiera żadnej logiki funkcjonalnej dla samego modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Moduł używa nadpisań do modyfikacji podstawowego zachowania PrestaShop.

- `adminmenu/override/classes/helper/HelperList.php`

  - **Nazwa klasy i klasa nadrzędna**: `HelperList` (nadpisuje podstawową klasę `HelperList`).
  - **Co robi**: To nadpisanie prawdopodobnie modyfikuje zachowanie `HelperList` specjalnie podczas renderowania listy encji `Tab` w Panelu administracyjnym. Jest to kluczowe dla ponownego włączenia funkcji, takich jak przeciąganie i upuszczanie w celu zmiany kolejności lub specyficzne wyświetlanie kolumn, które zostały usunięte z domyślnej implementacji `HelperList` dla `Tab` w nowszych wersjach PrestaShop. Może wstrzykiwać niestandardowe akcje lub modyfikować sposób pobierania lub wyświetlania danych dla zakładek menu.
- `adminmenu/override/classes/helper/index.php`

  - **Odpowiedzialność**: Podobnie jak `controllers/admin/index.php`, jest to plik zastępczy, aby zapobiec bezpośredniemu wyświetlaniu lub dostępowi do katalogu.
- `adminmenu/override/classes/index.php`

  - **Odpowiedzialność**: Kolejny plik zastępczy, aby zapobiec bezpośredniemu wyświetlaniu lub dostępowi do katalogu.

### 4.4 Zasoby JavaScript (`views/js/`)

Dostarczony spis nie wskazuje na żadne niestandardowe pliki JavaScript w module. Sugeruje to, że funkcjonalność zarządzania menu, w tym funkcje takie jak przeciąganie i upuszczanie w celu zmiany kolejności, jest obsługiwana przez:

1. Natywny JavaScript `HelperList` PrestaShop (który nadpisanie modułu może ponownie włączyć lub skonfigurować).
2. Przetwarzanie po stronie serwera dla aktualizacji pozycji.
3. Minimalny wbudowany JS generowany przez klasy `HelperList` lub `HelperForm`.

Programiści powinni sprawdzić wygenerowany kod HTML i żądania sieciowe na stronie `AdminMenuTabsController`, aby zrozumieć dokładną implementację JS dla elementów interaktywnych.

### 4.5 Arkusze stylów CSS (`views/css/`)

Dostarczony spis nie wskazuje na żadne niestandardowe pliki CSS w module. Oznacza to, że moduł opiera się całkowicie na domyślnych stylach Panelu administracyjnego PrestaShop. Wszelkie niestandardowe style dla interfejsu menedżera menu byłyby:

1. Wstrzykiwane wbudowane za pośrednictwem szablonów Smarty lub PHP.
2. Wykorzystujące istniejące klasy CSS PrestaShop.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Dostarczony spis nie wskazuje na żadne niestandardowe pliki szablonów Smarty (`.tpl`) w module. Jest to silny wskaźnik, że moduł opiera się przede wszystkim na domyślnych szablonach `HelperList` i `HelperForm` do renderowania swojego interfejsu Panelu administracyjnego.

`AdminMenuTabsController` tworzyłby instancje obiektów `HelperList` i `HelperForm`, przekazując im tablice konfiguracyjne, a te pomocniki renderowałyby interfejs użytkownika za pomocą podstawowych szablonów PrestaShop (np. `_partials/helpers/list_action_enable.tpl`, `helpers/list/list_content.tpl`, `helpers/form/form.tpl`).

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  Ten moduł przede wszystkim współdziała z istniejącą podstawową tabelą PrestaShop:

  - `ps_tab`: Ta tabela przechowuje wszystkie wpisy menu Panelu administracyjnego, w tym ich nazwy, identyfikatory nadrzędne, pozycje i status aktywności. Kontroler `AdminMenuTabsController` modułu i nadpisanie `HelperList` bezpośrednio odczytują i zapisują do tej tabeli, aby zarządzać menu.
  - `ps_configuration`: Standardowa tabela konfiguracji PrestaShop. Główne ustawienia konfiguracji modułu (np. status włączenia/wyłączenia) byłyby przechowywane tutaj (np. `PS_ADMINMENU_MANAGER_ENABLED`).
- **Tabela zarejestrowanych hooków**:
  Na podstawie opisu i funkcjonalności modułu, nie rejestruje on jawnie żadnych hooków wyświetlania front-office ani back-office (`displayHeader`, `actionValidateOrder` itp.) w tradycyjnym sensie. Jego funkcjonalność jest osiągana poprzez:

  1. **Rejestracja kontrolera administracyjnego**: Moduł rejestruje `AdminMenuTabsController` jako nową zakładkę Panelu administracyjnego, czyniąc ją dostępną za pośrednictwem menu Panelu administracyjnego.
  2. **Nadpisywanie klas**: Podstawowy mechanizm opiera się na nadpisywaniu `classes/helper/HelperList.php` w celu modyfikacji sposobu zarządzania i wyświetlania zakładek menu w Panelu administracyjnym. Nie jest to „hook”, ale bezpośrednia modyfikacja podstawowego zachowania.

  Dlatego tabela zarejestrowanych hooków nie ma zastosowania w typowym sensie dla tego modułu. Jego wpływ dotyczy wewnętrznego działania renderowania menu Panelu administracyjnego.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i profesjonalne wsparcie dla modułu „Menedżer menu Panelu administracyjnego”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
