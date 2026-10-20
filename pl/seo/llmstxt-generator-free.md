---
title: "LLMS.txt Generator Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracyjny"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop LLMS.txt Generator Free od MyPresta.eu."
sidebar:
  label: "LLMS.txt Generator Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracyjny"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł LLMS.txt Generator Free na MyPresta.eu](https://mypresta.eu/modules/seo/llmstxt-generator-free.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/seo/llmstxt-generator-free/)
>
> ---


# LLMS.txt Generator Free

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL). Twój serwer musi zezwalać na zapisywanie plików w katalogu głównym instalacji PrestaShop, aby plik `llms.txt` mógł zostać utworzony i zaktualizowany.

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj”, aby uzyskać dostęp do głównej strony ustawień modułu. Tutaj zdefiniujesz, jaka zawartość trafi do Twojego pliku `llms.txt`.

#### Ustawienia ogólne

-   **Profil sklepu (dla każdego aktywnego języka)**
    -   **Co robi to ustawienie:** Pozwala napisać krótki, zwięzły opis Twojego sklepu w każdym języku obsługiwanym przez Twój sklep. Ten profil zostanie uwzględniony w pliku `llms.txt`, dając modelom AI szybki przegląd tego, czym zajmuje się Twoja firma.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wypełnieniu:* Podany tekst zostanie dodany do pliku `llms.txt`, pomagając modelom AI zrozumieć cel i ofertę Twojego sklepu w określonych językach.
        -   *Po pozostawieniu pustego:* Profil sklepu nie zostanie uwzględniony dla tego języka, co potencjalnie utrudni AI zrozumienie istoty Twojego sklepu.
    -   **Zalecana wartość:** Wypełnij to dla każdego aktywnego języka. Zachowaj krótki (1-2 zdania) i opisowy charakter.
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój sklep sprzedaje ekologiczną karmę dla zwierząt, możesz napisać: „MójSklep oferuje szeroki wybór wysokiej jakości ekologicznej karmy dla zwierząt i naturalnych artykułów dla psów i kotów. Priorytetem jest dla nas zdrowie, zrównoważony rozwój i szczęśliwe zwierzęta.”

#### Wybór treści

-   **Promowane kategorie**

    -   **Co robi to ustawienie:** Pozwala wybrać konkretne kategorie produktów z Twojego sklepu, które chcesz wyróżnić dla crawlerów AI. Te kategorie zostaną wyraźnie wymienione w pliku `llms.txt`.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wybraniu kategorii:* Modele AI zostaną skierowane do tych kategorii, sygnalizując ich ważność i potencjalnie zwiększając ich widoczność w wyszukiwaniach opartych na AI.
        -   *Po niewybraniu kategorii:* Modele AI nie otrzymają konkretnych wskazówek, które kategorie mają priorytetowo traktować z Twojego pliku `llms.txt`.
    -   **Zalecana wartość:** Wybierz 3-5 najważniejszych lub najlepiej sprzedających się kategorii.
    -   **Scenariusz/przykład dla sprzedawcy:** Jeśli specjalizujesz się w „Sukienkach damskich”, „Butach męskich” i „Zabawkach dla dzieci”, wybierz te kategorie, aby poinformować AI, że są to kluczowe oferty.
-   **Uwzględnij 5 najlepszych bestsellerów z cenami**

    -   **Co robi to ustawienie:** Po włączeniu moduł automatycznie zidentyfikuje 5 najlepiej sprzedających się produktów i uwzględni ich nazwy, linki i aktualne ceny w pliku `llms.txt`.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po włączeniu:* Modele AI uzyskają bezpośredni dostęp do informacji o Twoich najpopularniejszych produktach, w tym ich cenach, co może być kluczowe dla rekomendacji zakupowych opartych na AI.
        -   *Po wyłączeniu:* Twoje bestsellery nie zostaną wyraźnie wyróżnione z ich cenami w pliku `llms.txt`.
    -   **Zalecana wartość:** TAK. Jest to potężna funkcja do prezentowania najpopularniejszych produktów.
    -   **Scenariusz/przykład dla sprzedawcy:** Klient pyta AI: „Jakie są najlepiej sprzedające się produkty w [Nazwa Twojego Sklepu]?” Po włączeniu tej funkcji AI może udzielić bezpośredniej odpowiedzi z aktualnymi cenami.
-   **Uwzględnij strony CMS**

    -   **Co robi to ustawienie:** Pozwala wybrać ważne statyczne strony treści (takie jak „O nas”, „Kontakt”, „Polityka prywatności”, „Informacje o dostawie”), o których chcesz, aby modele AI wiedziały.
    -   **Efekt zmiany tego ustawienia:**
        -   *Po wybraniu stron CMS:* Modele AI zostaną skierowane do tych stron informacyjnych, pomagając im zrozumieć politykę Twojego sklepu, tło i sposób kontaktu.
        -   *Po niewybraniu stron CMS:* Modele AI mogą musieć odkryć te strony poprzez ogólne indeksowanie, co może być mniej efektywne.
    -   **Zalecana wartość:** Wybierz wszystkie niezbędne strony informacyjne, które budują zaufanie i dostarczają szczegółów obsługi klienta.
    -   **Scenariusz/przykład dla sprzedawcy:** Upewnij się, że strony „Polityka zwrotów” i „FAQ” są uwzględnione, aby AI mogła dokładnie odpowiadać na pytania klientów dotyczące tych tematów.

#### Akcja

-   **Zapisz i wygeneruj ponownie plik llms.txt**
    -   **Co robi ten przycisk:** Ten przycisk zapisuje wszystkie skonfigurowane ustawienia na tej stronie i natychmiast regeneruje plik `llms.txt` w katalogu głównym Twojego sklepu z zaktualizowanymi informacjami.
    -   **Efekt kliknięcia tego przycisku:** Twój plik `llms.txt` zostanie zaktualizowany o najnowsze wybory. Ta akcja jest również wyzwalana automatycznie po aktualizacji produktów lub kategorii w Twoim sklepie.
    -   **Zalecana wartość:** Zawsze klikaj ten przycisk po wprowadzeniu jakichkolwiek zmian, aby upewnić się, że plik `llms.txt` jest aktualny.
    -   **Scenariusz/przykład dla sprzedawcy:** Po dodaniu nowego opisu „Profilu sklepu” kliknij ten przycisk, aby upewnić się, że crawlery AI otrzymają nowe informacje.

#### Uaktualnij do wersji Pro (blok upsellowy)

Ta sekcja to blok informacyjny promujący wersję Pro modułu. Podkreśla dodatkowe funkcje dostępne w płatnej wersji, takie jak pełny eksport katalogu, analityka crawlerów, filtry i obsługa zadań cron. Nie jest to ustawienie konfigurowalne, ale sugestia dla zaawansowanych potrzeb.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Profil sklepu (na język) | Wypełnij dla wszystkich języków | Dostarcza modelom AI krótki, ustrukturyzowany opis Twojego sklepu. |
| Konfiguracja modułu | Promowane kategorie | Wybierz 3-5 kluczowych kategorii | Kieruje crawlery AI do najważniejszych kategorii produktów. |
| Konfiguracja modułu | Uwzględnij 5 najlepszych bestsellerów z cenami | TAK | Wyróżnia Twoje najpopularniejsze produkty z aktualnymi cenami dla AI. |
| Konfiguracja modułu | Uwzględnij strony CMS | Wybierz wszystkie niezbędne strony | Kieruje AI do ważnych stron informacyjnych (np. O nas, Kontakt). |
| Konfiguracja modułu | Zapisz i wygeneruj ponownie plik llms.txt | Kliknij po każdej zmianie | Zapisuje ustawienia i aktualizuje plik `llms.txt` w katalogu głównym Twojego sklepu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Skonfigurowałem moduł, ale nie widzę żadnych zmian na mojej stronie internetowej. Czy działa?**
O1: Tak, prawdopodobnie działa poprawnie! Plik `llms.txt` to plik techniczny dla crawlerów AI, a nie dla odwiedzających ludzi. Nie zobaczysz żadnych wizualnych zmian w front-office Twojego sklepu. Aby sprawdzić, czy działa, możesz spróbować uzyskać dostęp do `twojasklep.com/llms.txt` w przeglądarce. Powinieneś tam zobaczyć wygenerowaną zawartość.

**P2: Otrzymuję błąd, że moduł nie może zapisać pliku `llms.txt`.**
O2: Zazwyczaj oznacza to problem z uprawnieniami do plików na Twoim serwerze. Moduł potrzebuje uprawnień do tworzenia i aktualizowania pliku `llms.txt` w katalogu głównym Twojego PrestaShop.
- **Rozwiązanie:** Skontaktuj się ze swoim dostawcą hostingu i poproś go o upewnienie się, że aplikacja PrestaShop ma uprawnienia do zapisu (np. chmod 755 lub 775 dla katalogów, 644 lub 664 dla plików) w katalogu głównym Twojego sklepu.

**P3: Jak często aktualizowany jest plik `llms.txt`?**
O3: Plik `llms.txt` jest automatycznie regenerowany za każdym razem, gdy:
- Klikniesz przycisk „Zapisz i wygeneruj ponownie plik llms.txt” w konfiguracji modułu.
- Zaktualizujesz produkt (np. zmienisz cenę, nazwę, opis).
- Zaktualizujesz kategorię (np. zmienisz nazwę, opis).
Zapewnia to, że plik jest zawsze świeży z najnowszymi danymi Twojego sklepu.

**P4: Mój niestandardowy motyw nie wydaje się być dotknięty przez ten moduł. Czy występuje konflikt?**
O4: Nie, nie powinno być żadnego konfliktu. Ten moduł działa całkowicie w tle, generując plik tekstowy. Nie modyfikuje projektu Twojego motywu, CSS ani JavaScript. Jego celem jest dostarczanie ustrukturyzowanych danych crawlerom AI, a nie zmienianie wyglądu wizualnego Twojego sklepu.

**P5: Czy mogę ręcznie edytować plik `llms.txt`?**
O5: Zdecydowanie zaleca się **nie** edytować pliku `llms.txt` bezpośrednio. Wszelkie wprowadzone zmiany zostaną nadpisane przy następnym wygenerowaniu pliku przez moduł (np. po zapisaniu ustawień lub aktualizacji produktów/kategorii). Zawsze używaj interfejsu konfiguracji modułu do kontrolowania jego zawartości.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `LLMS.txt Generator Free` to lekki moduł PrestaShop, skupiający się głównie na generowaniu statycznego pliku tekstowego (`llms.txt`) w katalogu głównym sklepu. Przestrzega standardowej struktury modułu PrestaShop, wykorzystując klasę `Module` do instalacji, deinstalacji i konfiguracji. Główna logika znajduje się w głównym pliku modułu, obsługującym trwałość konfiguracji i generowanie plików. Wykorzystuje klasę `Configuration` PrestaShop do ustawień i hooki do automatycznej regeneracji.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała logika jest obsługiwana w metodzie `getContent()` głównego pliku modułu dla konfiguracji oraz za pośrednictwem hooków dla operacji w tle.

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł **nie** zawiera żadnych niestandardowych klas ani definicji `ObjectModel` w katalogu `classes/`. Bezpośrednio wykorzystuje podstawowe klasy PrestaShop, takie jak `Configuration`, `Product`, `Category`, `CMS`, `Language` i `Shop`.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`llmstxtfree/views/css/admin-config.css`**
    -   **Zakres:** Stylizacja formularza administracyjnego Back-office.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Zapewnia podstawową stylizację strony konfiguracji modułu, prawdopodobnie dla układu, odstępów i potencjalnie niektórych wskazówek wizualnych dla bloku upsellowego.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim motywie:** Zazwyczaj celuje w elementy w ramach wyjścia `getContent()` modułu, takie jak `.panel`, `.form-group` lub niestandardowe klasy zdefiniowane w `configure.tpl`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   **`llmstxtfree/views/templates/admin/configure.tpl`**
        -   **Cel:** Jest to główny szablon Smarty renderowany przez metodę `getContent()` modułu. Definiuje strukturę i pola dla strony konfiguracji modułu w Panelu Administracyjnym PrestaShop.
        -   **Zawartość:** Zawiera formularz HTML dla wszystkich ustawień opisanych w Sekcji 4.1, w tym pola wejściowe dla profilu sklepu, wyboru kategorii, przełącznika bestsellerów, wyboru strony CMS i przycisku zapisu. Zawiera również szablon `pro-upsell.tpl`.
    -   **`llmstxtfree/views/templates/admin/pro-upsell.tpl`**
        -   **Cel:** Ten szablon jest dołączony do `configure.tpl` i wyświetla treści promocyjne dla wersji Pro modułu.
        -   **Zawartość:** Zazwyczaj zawiera tekst, obrazy i linki zachęcające sprzedawcę do uaktualnienia do płatnej wersji, podkreślając dodatkowe funkcje.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Ten moduł **nie** tworzy żadnych niestandardowych tabel SQL.
    -   Przechowuje swoje ustawienia konfiguracyjne (np. wybrane kategorie, strony CMS, profile sklepów, przełącznik bestsellerów) w standardowej tabeli PrestaShop `ps_configuration`. Klucze konfiguracji zazwyczaj mają wzorzec `LLMSTXTFREE_SETTING_NAME`.
-   **Zarejestrowane hooki**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Renderuje zawartość w sekcji `<head>` stron front-office. | Nie jest bezpośrednio używany do wyświetlania treści, ale często rejestrowany przez moduły do ładowania zasobów lub początkowej konfiguracji. W tym module prawdopodobnie służy do ogólnej inicjalizacji modułu lub potencjalnie do przyszłych funkcji. |
| `displayRightColumn` | Renderuje zawartość w prawej kolumnie stron front-office. | Nie jest używany do wyświetlania treści w tym module. |
| `displayLeftColumn` | Renderuje zawartość w lewej kolumnie stron front-office. | Nie jest używany do wyświetlania treści w tym module. |
| `displayFooter` | Renderuje zawartość w stopce stron front-office. | Nie jest używany do wyświetlania treści w tym module. |
| `displayProductExtraContent` | Renderuje dodatkową zawartość na stronie produktu. | Nie jest używany do wyświetlania treści w tym module. |
| `actionProductUpdate` | Wykonywany po zaktualizowaniu produktu w Panelu Administracyjnym. | **Kluczowy dla tego modułu:** Wyzwala automatyczną regenerację pliku `llms.txt`, aby zapewnić aktualność danych bestsellerów i linków do produktów. |
| `actionCategoryUpdate` | Wykonywany po zaktualizowaniu kategorii w Panelu Administracyjnym. | **Kluczowy dla tego modułu:** Wyzwala automatyczną regenerację pliku `llms.txt`, aby zapewnić aktualność promowanych linków i nazw kategorii. |
| `actionObjectCmsUpdateAfter` | Wykonywany po zaktualizowaniu strony CMS. | Wyzwala automatyczną regenerację pliku `llms.txt`, aby zapewnić aktualność wybranych linków i tytułów stron CMS. |
| `actionObjectCmsAddAfter` | Wykonywany po dodaniu nowej strony CMS. | Wyzwala automatyczną regenerację pliku `llms.txt`. |
| `actionObjectCmsDeleteAfter` | Wykonywany po usunięciu strony CMS. | Wyzwala automatyczną regenerację pliku `llms.txt`. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego oraz zapoznania się z dodatkowymi modułami i usługami, odwiedź swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu LLMS.txt Generator Free.
