---
title: "Aktualności na stronie głównej - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku i odniesienie dla programistów dla modułu PrestaShop „Aktualności na stronie głównej” od MyPresta.eu."
sidebar:
  label: "Aktualności na stronie głównej - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Homepage news na MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-news.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/homepage-news/)
>
> ---


# Aktualności na stronie głównej

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Aktualności na stronie głównej”, gdzie kontrolujesz sposób wyświetlania artykułów informacyjnych na stronie głównej.

#### **Wybierz kategorię stron CMS**

- **Co robi to ustawienie:** Ta lista rozwijana pozwala wybrać, która konkretna kategoria CMS będzie używana jako źródło aktualności na stronie głównej. Tylko strony CMS należące do tej wybranej kategorii będą brane pod uwagę do wyświetlenia przez moduł.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy kategoria jest wybrana:* Moduł będzie pobierał i wyświetlał artykuły informacyjne tylko ze stron CMS w tej kategorii.
  - *Gdy żadna kategoria nie jest wybrana (lub niewłaściwa):* Moduł może nie wyświetlać żadnych wiadomości lub może wyświetlać strony, które nie miały być artykułami informacyjnymi.
- **Zalecana wartość:** Wybierz kategorię CMS, którą specjalnie utworzyłeś lub przeznaczyłeś na swoje artykuły informacyjne (np. „Aktualności”, „Blog”, „Aktualizacje”).
- **Scenariusz / przykład dla sprzedawcy:** Utworzyłeś kategorię CMS o nazwie „Aktualności firmowe” i dodałeś do niej kilka stron CMS, takich jak „Premiera nowego produktu”, „Ogłoszono letnią wyprzedaż” i „Godziny otwarcia w święta”. Wybierając tutaj „Aktualności firmowe”, tylko te strony pojawią się jako aktualności na Twojej stronie głównej.

#### **Pokaż pełną zawartość najnowszej strony CMS**

- **Co robi to ustawienie:** Ten przełącznik określa, czy najnowszy artykuł informacyjny (strona CMS) z wybranej kategorii zostanie wyświetlony z pełną treścią bezpośrednio na stronie głównej.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Pełna treść najnowszego artykułu informacyjnego będzie widoczna na Twojej stronie głównej, dostarczając natychmiastowych informacji bez konieczności klikania.
  - *Gdy wyłączone (NIE):* Wyświetlony zostanie tylko tytuł, miniatura i krótki opis (jeśli skonfigurowano) najnowszego artykułu informacyjnego, podobnie jak w przypadku innych miniatur. Klienci będą musieli kliknąć, aby przeczytać pełną treść.
- **Zalecana wartość:** „TAK”, jeśli chcesz natychmiast wyróżnić najważniejsze wiadomości; „NIE”, jeśli wolisz bardziej kompaktową sekcję wiadomości, gdzie wszystkie artykuły wymagają kliknięcia.
- **Scenariusz / przykład dla sprzedawcy:** Masz ważne ogłoszenie, takie jak otwarcie nowego sklepu. Włączenie tej opcji zapewnia, że klienci od razu zobaczą pełne szczegóły. Jeśli wolisz czystszą stronę główną, możesz ją wyłączyć i wyświetlać tylko fragmenty.

#### **Pokaż miniatury stron CMS**

- **Co robi to ustawienie:** Ten przełącznik kontroluje, czy mniejsze, skrócone wersje (miniatury) Twoich artykułów informacyjnych są wyświetlane na stronie głównej. Miniatury te zazwyczaj zawierają tytuł, mały obraz i krótki opis.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Moduł wyświetli serię miniaturowych bloków wiadomości, z których każdy reprezentuje ostatnią stronę CMS z wybranej kategorii.
  - *Gdy wyłączone (NIE):* Nie zostaną wyświetlone żadne miniatury. Jeśli opcja „Pokaż pełną zawartość najnowszej strony CMS” jest również wyłączona, żadne wiadomości nie pojawią się w ogóle.
- **Zalecana wartość:** „TAK”, aby zapewnić przegląd wielu artykułów informacyjnych i zachęcić do eksploracji.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz pokazać 3-5 najnowszych artykułów informacyjnych, aby klienci mogli szybko zapoznać się z ostatnimi aktualizacjami. Włączenie miniatur to umożliwia.

#### **Liczba miniatur do wyświetlenia**

- **Co robi to ustawienie:** Jeśli opcja „Pokaż miniatury stron CMS” jest włączona, to pole wejściowe określa, ile najnowszych miniatur artykułów informacyjnych zostanie wyświetlonych na Twojej stronie głównej.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawione na wyższą liczbę (np. 5):* Będzie widocznych więcej miniatur artykułów informacyjnych, co zapewni szerszy przegląd.
  - *Gdy ustawione na niższą liczbę (np. 2):* Wyświetlonych zostanie mniej miniatur, co sprawi, że sekcja wiadomości będzie bardziej zwięzła.
- **Zalecana wartość:** 3 do 5, w zależności od układu strony głównej i ilości miejsca, które chcesz przeznaczyć na wiadomości.
- **Scenariusz / przykład dla sprzedawcy:** Masz dużo wiadomości, ale chcesz, aby Twoja strona główna była czysta. Ustawienie tej wartości na „3” zapewnia, że wyróżnione zostaną tylko trzy najnowsze artykuły.

#### **Liczba znaków użytych w opisie dla miniatur**

- **Co robi to ustawienie:** To pole wejściowe kontroluje długość krótkiego opisu (fragmentu) wyświetlanego w każdej miniaturze wiadomości.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawione na wyższą liczbę (np. 200):* Opisy w miniaturach będą dłuższe, dostarczając więcej kontekstu.
  - *Gdy ustawione na niższą liczbę (np. 50):* Opisy będą krótsze, co sprawi, że miniatury będą bardziej kompaktowe.
- **Zalecana wartość:** 100 do 150 znaków, wystarczająco, aby dać dobre podsumowanie bez przeciążania miniatury.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz dać klientom wystarczająco dużo informacji w miniaturze, aby wzbudzić ich zainteresowanie. Ustawienie tej wartości na „120” zapewnia zwięzły, ale informacyjny fragment.

#### **Styl miniatur**

- **Co robi to ustawienie:** Ta opcja (prawdopodobnie lista rozwijana lub przyciski radiowe) pozwala wybrać wizualny układ lub styl, w jakim miniatury wiadomości są prezentowane na Twojej stronie głównej. Dostępne style mogą obejmować opcje takie jak siatka, lista lub karuzela.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy ustawione na „Siatka”:* Miniatury mogą pojawiać się w wierszach i kolumnach, odpowiednie do kompaktowego wyświetlania kilku elementów.
  - *Gdy ustawione na „Lista”:* Miniatury mogą pojawiać się jedna pod drugą, dobre dla bardziej szczegółowych opisów.
  - *Gdy ustawione na „Karuzela”:* Miniatury mogą przesuwać się poziomo, oszczędzając miejsce i pozwalając użytkownikom przeglądać więcej elementów.
- **Zalecana wartość:** Eksperymentuj z dostępnymi stylami, aby zobaczyć, który najlepiej pasuje do projektu Twojego motywu i pożądanej estetyki strony głównej.
- **Scenariusz / przykład dla sprzedawcy:** Twoja strona główna ma ograniczoną przestrzeń poziomą. Wybór stylu „Karuzela” pozwala wyświetlić wiele elementów wiadomości bez zbytniego wydłużania strony. Jeśli masz dużo miejsca, „Siatka” może wyglądać bardziej atrakcyjnie.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wybierz kategorię stron CMS | Twoja wyznaczona kategoria CMS „Aktualności” | Definiuje, które strony CMS są źródłem wiadomości. |
| Konfiguracja modułu | Pokaż pełną zawartość najnowszej strony CMS | TAK | Wyświetla pełną treść najnowszego artykułu bezpośrednio na stronie głównej. |
| Konfiguracja modułu | Pokaż miniatury stron CMS | TAK | Włącza wyświetlanie skróconych bloków wiadomości. |
| Konfiguracja modułu | Liczba miniatur do wyświetlenia | 3-5 | Kontroluje, ile ostatnich miniatur wiadomości jest wyświetlanych. |
| Konfiguracja modułu | Liczba znaków użytych w opisie dla miniatur | 100-150 | Ustawia długość fragmentu tekstu w miniaturach. |
| Konfiguracja modułu | Styl miniatur | Różne (np. Siatka, Lista, Karuzela) | Określa wizualny układ miniatur wiadomości. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moja sekcja wiadomości nie wyświetla się na stronie głównej. Co powinienem sprawdzić?**
O:

1.  **Moduł włączony:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że „Aktualności na stronie głównej” jest zainstalowany i włączony.
2.  **Wybrana kategoria CMS:** W konfiguracji modułu sprawdź, czy wybrałeś prawidłową kategorię CMS w sekcji „Wybierz kategorię stron CMS”.
3.  **Strony CMS istnieją:** Upewnij się, że w wybranej kategorii istnieją rzeczywiste strony CMS.
4.  **Ustawienia widoczności:** Sprawdź, czy opcje „Pokaż miniatury stron CMS” i/lub „Pokaż pełną zawartość najnowszej strony CMS” są włączone w konfiguracji modułu. Jeśli obie są wyłączone, nic się nie wyświetli.
5.  **Pamięć podręczna:** Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**).

**P: Obrazy dla moich miniatur wiadomości nie pojawiają się.**
O: Moduł zazwyczaj próbuje wyodrębnić pierwszy obraz z treści Twojej strony CMS.

1.  **Obraz na stronie CMS:** Upewnij się, że treść Twojej strony CMS faktycznie zawiera obraz.
2.  **Ścieżka obrazu:** Sprawdź, czy ścieżka obrazu na Twojej stronie CMS jest poprawna i czy plik obrazu istnieje na Twoim serwerze.
3.  **Kompatybilność z motywem:** Niektóre niestandardowe motywy mogą zakłócać renderowanie obrazów. Jeśli wszystko inne zawiedzie, skonsultuj się z twórcą motywu lub wsparciem MyPresta.eu.

**P: Jak przetłumaczyć tytuły i opisy wiadomości?**
O: Tytuły i treści wiadomości pochodzą bezpośrednio z Twoich stron CMS.

1.  **Tłumaczenia stron CMS:** Przejdź do **Wygląd > Strony** (lub **CMS** w starszych wersjach), edytuj swoją stronę CMS z wiadomościami.
2.  **Edytuj we wszystkich językach:** Dla każdego obsługiwanego języka upewnij się, że podałeś przetłumaczony tytuł i treść dla tej konkretnej strony CMS. Moduł automatycznie wyświetli prawidłowy język na podstawie wybranego przez klienta języka sklepu.

**P: Sekcja wiadomości wygląda dziwnie lub jest źle wyrównana na mojej stronie głównej.**
O: Jest to często konflikt CSS z motywem Twojego sklepu.

1.  **Wyczyść pamięć podręczną:** Zawsze zaczynaj od wyczyszczenia pamięci podręcznej PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**).
2.  **Konfiguracja modułu:** Sprawdź, czy zmiana ustawienia „Styl miniatur” pomaga.
3.  **Dostosowanie motywu:** CSS Twojego motywu może nadpisywać style modułu. Może być konieczne skonsultowanie się z programistą stron internetowych w celu dodania niestandardowego CSS do Twojego motywu, aby dostosować wygląd. Wsparcie MyPresta.eu może zaoferować wskazówki, ale nie może zapewnić niestandardowego rozwoju motywu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Aktualności na stronie głównej” (`hnews`) to prosty moduł PrestaShop, zaprojektowany głównie do wyświetlania treści z istniejących stron CMS na stronie głównej front-office. Wykorzystuje klasę `Module` PrestaShop i standardowe haki. Logika modułu znajduje się głównie w jego głównym pliku PHP, `hnews.php`, który obsługuje konfigurację, rejestrację haków i pobieranie danych. Nie wprowadza niestandardowych kontrolerów ani złożonych ObjectModels, opierając się zamiast tego na natywnych klasach `CMSCategory` i `CMS` PrestaShop do obsługi danych.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Logika wyświetlania front-office modułu jest w całości obsługiwana przez metodę `hookDisplayHome` w `hnews.php` i renderowana za pomocą szablonu Smarty.
- **Kontrolery Back-Office Admin**: Brak. Cała konfiguracja jest zarządzana za pomocą metody `getContent()` głównej klasy modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

- Ten moduł nie wprowadza żadnych niestandardowych klas ani ObjectModels. Bezpośrednio wysyła zapytania do bazy danych lub używa podstawowych klas `CMSCategory` i `CMS` PrestaShop do pobierania danych.

### 4.4 Zasoby JavaScript (`views/js/`)

- W tym module nie ma niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `hnews/views/admin/css/hnews.css`:
  - **Zakres:** Stylizacja formularzy administracyjnych back-office.
  - **Główne komponenty interfejsu użytkownika:** Prawdopodobnie zawiera style specyficzne dla strony konfiguracji modułu, zapewniając spójny i czytelny układ w panelu administracyjnym PrestaShop.
  - **Kluczowe selektory klas CSS:** Może zawierać style dla elementów formularza, etykiet i konkretnych kontenerów używanych w `getContent()`.
- `hnews/views/css/hnews.css`:
  - **Zakres:** Stylizacja klienta front-office.
  - **Główne komponenty interfejsu użytkownika:** Stylizuje sekcję wiadomości wyświetlaną na stronie głównej, w tym główny artykuł informacyjny (jeśli wyświetlana jest pełna treść) i poszczególne miniatury wiadomości.
  - **Kluczowe selektory klas CSS:** Będzie zawierać selektory dla głównego kontenera wiadomości, poszczególnych bloków miniatur, tytułów, opisów i obrazów. Programiści mogą nadpisać te klasy w pliku `custom.css` lub `theme.css` swojego motywu, aby dopasować je do projektu sklepu.

### 4.6 Struktura szablonu Smarty (`views/templates/`)

- **Szablony haków (`views/templates/hook/`)**:
  - `hnews/views/hnews.tpl`: Jest to główny szablon front-office.
    - **Hak:** Renderowany w `displayHome`.
    - **Blok wizualny:** Wyświetla całą sekcję wiadomości na stronie głównej, w tym pełną treść najnowszego artykułu informacyjnego (jeśli włączono) i listę miniatur wiadomości. Iteruje przez artykuły informacyjne przekazane z logiki PHP modułu.
- **Szablony administracyjne (`views/templates/admin/`)**:
  - `hnews/views/admin/elements.tpl`:
    - **Hak:** Nie jest bezpośrednio zahaczony, ale jest dołączany/renderowany przez metodę `getContent()` w `hnews.php`.
    - **Blok wizualny:** Renderuje elementy formularza konfiguracji modułu w panelu administracyjnym PrestaShop. Zazwyczaj obejmuje to listę rozwijaną dla kategorii CMS, przełączniki dla opcji wyświetlania i pola wejściowe dla liczników i limitów znaków.

### 4.7 Schemat bazy danych i mapa haków

- **Tabele bazy danych**:
  - Moduł nie tworzy żadnych niestandardowych tabel SQL.
  - Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` za pomocą kluczy takich jak `HNEWS_ID_CMSCAT`, `HNEWS_NB_MIN`, `HNEWS_LATEST`, `HNEWS_SIZE_MIN`, `HNEWS_CHR_MIN`, `HNEWS_MINIATURES`.
- **Tabela zarejestrowanych haków**:

| Nazwa haka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHome` | Renderuje zawartość w głównym obszarze strony głównej. | Wyświetla sekcję wiadomości z najnowszymi stronami CMS. |
| `displayHeader` | Wykonywany w sekcji `<head>` strony front-office. | Potencjalnie używany do ładowania zasobów CSS lub JS front-office (chociaż nie ma JS, CSS jest ładowany). |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje media (CSS/JS). | Używany do ładowania CSS back-office dla strony konfiguracji modułu. |
| `header` | Podobny do `displayHeader`, często używany do ładowania zasobów. | Potencjalnie używany do ładowania zasobów CSS lub JS front-office. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Aktualności na stronie głównej”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich zapytań lub problemów związanych z modułem.
