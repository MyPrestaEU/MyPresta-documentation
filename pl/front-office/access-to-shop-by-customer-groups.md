---
title: "Dostęp do sklepu według grup klientów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Dostęp do sklepu według grup klientów” od MyPresta.eu."
sidebar:
  label: "Dostęp do sklepu według grup klientów - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Access to shop by customer groups na MyPresta.eu](https://mypresta.eu/modules/front-office-features/access-to-shop-by-customer-groups.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/access-to-shop-by-customer-groups/)
>
> ---


# Dostęp do sklepu według grup klientów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zwykle dostępne w każdym nowoczesnym środowisku hostingowym.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok nazwy modułu, aby uzyskać dostęp do jego ustawień.

#### **Grupy klientów bez dostępu do sklepu**

To jest najważniejsze ustawienie. Określa, które grupy klientów zostaną zablokowane przed przeglądaniem Twojego sklepu.

-   **Co robi to ustawienie:** Ta sekcja wyświetla listę wszystkich grup klientów zdefiniowanych w Twoim sklepie PrestaShop. Możesz wybrać jedną lub więcej grup z tej listy.
-   **Wpływ zmiany tego ustawienia:**
    *   *Gdy wybrano jedną lub więcej grup:* Każdy klient należący do *którejkolwiek* z wybranych grup zostanie zablokowany przed dostępem do front-office sklepu. Zamiast tego zobaczy niestandardową zawartość, którą zdefiniujesz poniżej.
    *   *Gdy nie wybrano żadnych grup:* Moduł nie zablokuje żadnych klientów na podstawie ich przynależności do grupy. Wszyscy klienci będą mieli dostęp do sklepu (chyba że włączysz opcję „Zablokuj dostęp dla niezalogowanych klientów”).
-   **Zalecana wartość:** Wybierz konkretne grupy, które chcesz ograniczyć. Na przykład, jeśli masz grupę „Hurt – Oczekujące na zatwierdzenie”, możesz ją tutaj wybrać.
-   **Scenariusz / przykład dla sprzedawcy:** Utworzyłeś nową grupę klientów o nazwie „Nowe rejestracje – Oczekujące na weryfikację”. Wybierasz tę grupę tutaj. Teraz każdy nowy klient, który się zarejestruje, zostanie automatycznie umieszczony w tej grupie i nie będzie mógł przeglądać Twojego sklepu, dopóki ręcznie nie przeniesiesz go do grupy „Zatwierdzeni klienci”.

#### **Zablokuj dostęp dla niezalogowanych klientów**

To ustawienie kontroluje dostęp dla odwiedzających, którzy nie są zalogowani do Twojego sklepu.

-   **Co robi to ustawienie:** To jest prosty przełącznik WŁ./WYŁ.
-   **Wpływ zmiany tego ustawienia:**
    *   *Gdy włączone (TAK):* Wszyscy odwiedzający, którzy nie są zalogowani na konto klienta, zostaną zablokowani przed dostępem do sklepu. Zobaczą stronę z niestandardową zawartością. Po zalogowaniu (i jeśli należą do dozwolonej grupy) uzyskają dostęp.
    *   *Gdy wyłączone (NIE):* Niezalogowani odwiedzający będą mieli dostęp do sklepu, chyba że zostaną wyraźnie zablokowani przez przynależność do „Grup klientów bez dostępu do sklepu”.
-   **Zalecana wartość:**
    *   **TAK:** Jeśli chcesz, aby cały Twój sklep był prywatny, wymagając od wszystkich odwiedzających najpierw zalogowania się (np. sklep B2B, klub tylko dla członków).
    *   **NIE:** Jeśli chcesz, aby Twój sklep był publicznie widoczny, ale ograniczał dostęp tylko dla określonych grup klientów.
-   **Scenariusz / przykład dla sprzedawcy:** Prowadzisz sklep wyłącznie hurtowy. Włączasz to ustawienie. Teraz każdy, kto odwiedza Twoją witrynę, musi najpierw się zalogować, aby zobaczyć Twoje produkty i ceny.

#### **Pokaż formularz logowania na zablokowanej stronie**

To ustawienie określa, czy formularz logowania pojawi się na stronie wyświetlanej zablokowanym klientom.

-   **Co robi to ustawienie:** To jest prosty przełącznik WŁ./WYŁ.
-   **Wpływ zmiany tego ustawienia:**
    *   *Gdy włączone (TAK):* Standardowy formularz logowania PrestaShop zostanie wyświetlony na stronie z niestandardową zawartością, umożliwiając zablokowanym klientom próbę zalogowania się.
    *   *Gdy wyłączone (NIE):* Nie zostanie wyświetlony żaden formularz logowania. Klienci zobaczą tylko Twoją niestandardową wiadomość.
-   **Zalecana wartość:**
    *   **TAK:** Jeśli oczekujesz, że zablokowani klienci to istniejący klienci, którzy po prostu muszą się zalogować, aby uzyskać dostęp. Poprawia to doświadczenie użytkownika.
    *   **NIE:** Jeśli chcesz zmusić klientów do najpierw rejestracji lub jeśli ograniczenie dostępu jest stałe dla niektórych grup.
-   **Scenariusz / przykład dla sprzedawcy:** Zablokowałeś dostęp dla niezalogowanych użytkowników. Włączając to, klienci mogą łatwo zalogować się bezpośrednio ze strony z ograniczonym dostępem, bez konieczności przechodzenia na osobną stronę logowania.

#### **Zezwól na rejestrację na zablokowanej stronie**

To ustawienie określa, czy link do rejestracji pojawi się na stronie wyświetlanej zablokowanym klientom.

-   **Co robi to ustawienie:** To jest prosty przełącznik WŁ./WYŁ.
-   **Wpływ zmiany tego ustawienia:**
    *   *Gdy włączone (TAK):* Link do strony rejestracji klienta zostanie wyświetlony na stronie z niestandardową zawartością.
    *   *Gdy wyłączone (NIE):* Nie zostanie wyświetlony żaden link do rejestracji.
-   **Zalecana wartość:**
    *   **TAK:** Jeśli chcesz zezwolić nowym klientom na rejestrację ze strony z ograniczonym dostępem.
    *   **NIE:** Jeśli chcesz kontrolować rejestrację oddzielnie lub jeśli Twój sklep jest przeznaczony wyłącznie dla wstępnie zatwierdzonych klientów.
-   **Scenariusz / przykład dla sprzedawcy:** Prowadzisz sklep B2B, który wymaga rejestracji. Włączasz to ustawienie, aby potencjalni nowi klienci mogli łatwo założyć konto bezpośrednio ze strony z ograniczonym dostępem.

#### **Niestandardowa zawartość do wyświetlenia**

Tutaj definiujesz wiadomość i zawartość wyświetlaną zablokowanym klientom.

-   **Co robi to ustawienie:** To jest edytor tekstu sformatowanego (WYSIWYG), w którym możesz wprowadzać tekst, obrazy, HTML, a nawet filmy. Obsługuje treści wielojęzyczne, więc możesz dostarczyć różne wiadomości dla różnych języków zainstalowanych w Twoim sklepie.
-   **Wpływ zmiany tego ustawienia:** Wprowadzona tutaj zawartość zostanie wyświetlona każdemu klientowi, który ma zablokowany dostęp do Twojego sklepu.
-   **Zalecana wartość:** Podaj jasną, uprzejmą i informacyjną wiadomość.
-   **Scenariusz / przykład dla sprzedawcy:**
    *   *Dla sklepu B2B:* „Witaj w naszym Portalu Hurtowym! Zaloguj się swoimi danymi uwierzytelniającymi lub zarejestruj nowe konto, aby przeglądać nasz katalog produktów.”
    *   *Dla tymczasowego ograniczenia:* „Nasz sklep jest obecnie w trakcie konserwacji. Wkrótce wrócimy online! Dziękujemy za cierpliwość.”
    *   *Dla ekskluzywnego dostępu:* „Ta sekcja naszego sklepu jest zarezerwowana dla członków VIP. Zaloguj się lub skontaktuj się z obsługą, aby uzyskać dostęp.”

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Grupy klientów bez dostępu do sklepu** | Brak wybranych | Wybierz grupy, które mają być zablokowane przed przeglądaniem sklepu. Klienci w tych grupach widzą niestandardową zawartość. |
| Konfiguracja modułu | **Zablokuj dostęp dla niezalogowanych klientów** | NIE | TAK: Wszyscy niezalogowani odwiedzający są blokowani. NIE: Niezalogowani odwiedzający mają dostęp (chyba że są w zablokowanej grupie). |
| Konfiguracja modułu | **Pokaż formularz logowania na zablokowanej stronie** | TAK | TAK: Wyświetla formularz logowania na stronie z ograniczonym dostępem. NIE: Nie wyświetla formularza logowania. |
| Konfiguracja modułu | **Zezwól na rejestrację na zablokowanej stronie** | TAK | TAK: Wyświetla link do rejestracji na stronie z ograniczonym dostępem. NIE: Nie wyświetla linku do rejestracji. |
| Konfiguracja modułu | **Niestandardowa zawartość do wyświetlenia** | Puste | Definiuje wiadomość/zawartość HTML wyświetlaną zablokowanym klientom. Obsługuje wiele języków. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Mój sklep jest całkowicie zablokowany, nawet dla mnie! Co mam zrobić?**
O1: Dzieje się tak zazwyczaj, jeśli włączyłeś „Zablokuj dostęp dla niezalogowanych klientów” i nie jesteś zalogowany, lub jeśli Twoje konto administratora jest w jakiś sposób powiązane z zablokowaną grupą klientów.
\* **Rozwiązanie 1 (zalecane):** Zaloguj się do Panelu administracyjnego PrestaShop. Moduł blokuje tylko front-office. Po zalogowaniu do BO przejdź do Moduły > Menedżer modułów, znajdź „Dostęp do sklepu według grup klientów” i kliknij „Konfiguruj”. Dostosuj ustawienia, aby zezwolić na swój dostęp.
\* **Rozwiązanie 2 (jeśli nie możesz uzyskać dostępu do BO):** Jeśli jesteś całkowicie zablokowany, może być konieczne tymczasowe wyłączenie modułu przez FTP. Przejdź do `modules/asg/` i zmień nazwę pliku `asg.php` (np. na `asg.php.bak`). Spowoduje to wyłączenie modułu. Następnie możesz zalogować się do swojego BO i ponownie go włączyć/skonfigurować. Pamiętaj, aby później zmienić nazwę pliku z powrotem na `asg.php`.

**P2: Niestandardowa zawartość wygląda prosto lub nie pasuje do mojego motywu.**
O2: Obszar niestandardowej zawartości używa podstawowego szablonu.
\* **Rozwiązanie:** Możesz użyć edytora tekstu sformatowanego, aby dodać HTML, wbudowany CSS lub obrazy, aby stylizować swoją wiadomość. W przypadku bardziej zaawansowanego stylizowania, webmaster może zmodyfikować plik `custom.css` lub szablon `custom-contents.tpl` (patrz sekcja dla programistów). Upewnij się, że Twoja niestandardowa zawartość jest dobrze sformatowana i responsywna.

**P3: Dlaczego formularz logowania/rejestracji się nie wyświetla?**
O3: Sprawdź konfigurację modułu:
\* Upewnij się, że „Pokaż formularz logowania na zablokowanej stronie” jest ustawione na TAK.
\* Upewnij się, że „Zezwól na rejestrację na zablokowanej stronie” jest ustawione na TAK.
\* Upewnij się również, że rejestracja klienta jest ogólnie włączona w ustawieniach PrestaShop (Klienci > Ustawienia > Włącz tworzenie konta).

**P4: Wprowadziłem zmiany, ale nie pojawiają się w front-office.**
O4: PrestaShop używa buforowania, co czasami może opóźniać wyświetlanie zmian.
\* **Rozwiązanie:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop. Kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Powinno to odświeżyć Twój front-office.

**P5: Jak zarządzać tym, którzy klienci należą do których grup?**
O5: Grupami klientów zarządzasz za pomocą standardowego interfejsu PrestaShop:
\* Przejdź do **Klienci > Klienci**, aby edytować poszczególne konta klientów i przypisywać je do grup.
\* Przejdź do **Klienci > Grupy**, aby tworzyć nowe grupy lub edytować istniejące.
\* Pamiętaj, że klient może należeć do wielu grup. Jeśli klient należy do *jakiejkolwiek* grupy, którą oznaczyłeś jako „bez dostępu”, zostanie zablokowany.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Dostęp do sklepu według grup klientów” (`asg`) działa głównie poprzez podłączenie się do zdarzenia `displayHeader`. Pozwala to na wykonanie jego logiki bardzo wcześnie w procesie ładowania strony, zanim jakakolwiek zawartość zostanie wyrenderowana. Jeśli klient zostanie uznany za ograniczonego, moduł przejmuje kontrolę, zapobiega dalszemu renderowaniu standardowej strony PrestaShop i zamiast tego wyświetla swoją niestandardową stronę dostępu. Wykorzystuje system konfiguracji PrestaShop do ustawień i Smarty do szablonowania.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie używa dedykowanych kontrolerów front-office ani back-office. Cała logika jest hermetyzowana w głównym pliku modułu (`asg.php`) i wykonywana za pomocą hooków lub metody `getContent()` do konfiguracji.

### 4.3 Klasy i modele rdzenia (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani encji `ObjectModel`. Bezpośrednio współdziała z podstawowymi klasami PrestaShop: `Customer`, `Group` i `Configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`asg/views/css/custom.css`**
    *   **Zakres:** Stylizacja klienta front-office dla strony z ograniczonym dostępem.
    *   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Ten plik zapewnia podstawową stylizację dla niestandardowego opakowania treści, formularza logowania i linku do rejestracji na stronie z ograniczonym dostępem. Zapewnia, że wyświetlana zawartość jest wyśrodkowana i czytelna.
    *   **Kluczowe selektory klas CSS, które programiści mogą nadpisać:**
        *   `.asg_wrapper`: Główny kontener dla całej ograniczonej zawartości.
        *   `.asg_content`: Div zawierający niestandardową wiadomość HTML.
        *   `.asg_login_form`: Kontener dla formularza logowania.
        *   `.asg_registration_link`: Kontener dla linku do rejestracji.
        *   Standardowe elementy formularza PrestaShop w formularzu logowania.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**: Brak wyraźnie zdefiniowanych jako szablony hooków. Moduł bezpośrednio renderuje szablony na podstawie swojej wewnętrznej logiki.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    *   **`asg/views/admin.tpl`**: Ten szablon jest renderowany przez metodę `getContent()` w `asg.php`. Zawiera strukturę HTML dla formularza konfiguracji modułu w Panelu administracyjnym PrestaShop. Obejmuje wybór grupy klientów, przełączniki dla logowania/rejestracji oraz edytor tekstu sformatowanego dla niestandardowej zawartości.
-   **Szablony front-office (`views/templates/front/`)**:
    *   **`asg/views/custom-contents.tpl`**: To jest główny szablon renderowany, gdy klient jest zablokowany. Wyświetla niestandardową zawartość zdefiniowaną w konfiguracji modułu. Warunkowo zawiera `login-form.tpl` i `registration-link.tpl` na podstawie ustawień modułu.
    *   **`asg/views/login-form.tpl`**: Ten szablon zawiera HTML dla standardowego formularza logowania klienta PrestaShop. Jest on dołączany do `custom-contents.tpl`, jeśli opcja „Pokaż formularz logowania” jest włączona.
    *   **`asg/views/registration-link.tpl`**: Ten szablon zawiera HTML dla linku do strony rejestracji klienta. Jest on dołączany do `custom-contents.tpl`, jeśli opcja „Zezwól na rejestrację” jest włączona.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    *   Ten moduł nie tworzy żadnych niestandardowych tabel SQL.
    *   Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` (lub `_configuration` w zależności od prefiksu) używając kluczy takich jak:
        *   `ASG_ALLOWREGAUTH`: Wartość logiczna dla zezwolenia na rejestrację.
        *   `ASG_SHOWLOGINFORM`: Wartość logiczna dla wyświetlania formularza logowania.
        *   `ASG_CCONTENTS`: Pole wielojęzyczne dla niestandardowej zawartości (HTML).
        *   `ASG_WHATTOSHOW`: Serializowana tablica identyfikatorów grup klientów, które są zablokowane.
        *   `ASG_BLOCK_NOT_LOGGED`: Wartość logiczna dla blokowania niezalogowanych użytkowników.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | Wykonywany bardzo wcześnie w procesie ładowania strony front-office, w sekcji `<head>`. | Jest to główny hook używany przez moduł. Sprawdza status logowania klienta i przynależność do grupy. Jeśli klient ma ograniczony dostęp, natychmiast przerywa standardowy proces renderowania PrestaShop i wyświetla niestandardową stronę dostępu (`custom-contents.tpl`). |
| `actionCustomerGroupsUpdate` | Wykonywany, gdy grupy klientów są aktualizowane. | Służy do czyszczenia wewnętrznej pamięci podręcznej modułu związanej z grupami klientów, zapewniając natychmiastowe odzwierciedlenie zmian w przypisaniach grup. |
| `actionObjectCustomerAddAfter` | Wykonywany po dodaniu nowego klienta. | Służy do czyszczenia wewnętrznej pamięci podręcznej modułu związanej z grupami klientów, zapewniając prawidłową ocenę dostępu dla nowych klientów. |
| `actionObjectCustomerUpdateAfter` | Wykonywany po aktualizacji istniejącego klienta. | Służy do czyszczenia wewnętrznej pamięci podręcznej modułu związanej z grupami klientów, zapewniając natychmiastowe odzwierciedlenie zmian w przypisaniach grup klientów. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, poprawek błędów i dedykowanego wsparcia dla programistów dla modułu „Dostęp do sklepu według grup klientów”, prosimy o zapoznanie się z kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół zobowiązuje się do terminowego świadczenia pomocy i zapewnienia kompatybilności modułu z najnowszymi wersjami PrestaShop.
