---
title: "Wyślij e-mail z kuponem - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Wyślij e-mail z kuponem” od MyPresta.eu."
sidebar:
  label: "Wyślij e-mail z kuponem - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Send email with voucher na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/send-email-with-voucher.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/send-email-with-voucher/)
>
> ---


# Wyślij e-mail z kuponem

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zwykle dostępne w każdym nowoczesnym środowisku hostingowym.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Wyślij e-mail z kuponem)

Jest to główny ekran konfiguracji, na którym zarządzasz ustawieniami wysyłania e-maili z kuponami.

#### **Sekcja Menedżer szablonów e-mail**

Ta sekcja służy do definiowania treści i wyglądu e-maili, które będą zawierać kody kuponów.

-   **Co robi ta sekcja:** To potężne narzędzie pozwala tworzyć, edytować i zarządzać różnymi szablonami e-maili. Każdy szablon może mieć własny temat i treść, co ułatwia wysyłanie różnych typów ofert kuponowych (np. „Rabat powitalny”, „Prezent urodzinowy”, „Oferta odzyskiwania porzuconego koszyka”).
-   **Wpływ zmiany ustawień:**
    -   *Tworzenie nowego szablonu:* Definiujesz nowy projekt e-maila i temat, które możesz później wybrać podczas wysyłania kuponów.
    -   *Edytowanie istniejącego szablonu:* Zmiany w temacie lub treści zostaną zastosowane do wszystkich przyszłych e-maili wysyłanych przy użyciu tego konkretnego szablonu.
    -   *Usuwanie szablonu:* Szablon nie będzie już dostępny do wyboru.
-   **Zalecany przepływ pracy:** Zacznij od utworzenia kilku standardowych szablonów dla najczęstszych kampanii kuponowych. Na przykład, szablon „Powitanie” dla nowych klientów, szablon „Lojalność” dla stałych klientów i szablon „Oferta specjalna” dla promocji.

#### **Sekcja Silnik kuponów**

Ta sekcja służy do faktycznego generowania i wysyłania kodów kuponów.

-   **Co robi ta sekcja:** Jest to podstawowa funkcjonalność do tworzenia reguł rabatowych (kuponów) i wysyłania ich na określone adresy e-mail. Możesz zdefiniować typ rabatu (procentowy, stała kwota), wartość, warunki (minimalny zakup, konkretne produkty) i okres ważności.
-   **Wpływ zmiany ustawień:**
    -   *Tworzenie nowego kuponu:* W Twoim katalogu PrestaShop tworzona jest nowa reguła rabatowa i generowany jest unikalny kod.
    -   *Wysyłanie kuponu:* E-mail zawierający unikalny kod i treść wybranego szablonu jest wysyłany do określonych odbiorców.
    -   *Powiązanie z klientem:* Kupon może być powiązany z kontem konkretnego klienta, co oznacza, że tylko ten klient może go użyć.
-   **Zalecany przepływ pracy:**
    1.  Najpierw utwórz lub wybierz odpowiedni szablon e-maila z sekcji „Menedżer szablonów e-mail”.
    2.  Następnie użyj „Silnika kuponów”, aby zdefiniować parametry rabatu (np. 10% zniżki, ważne przez 30 dni, minimalny zakup 50 USD).
    3.  Określ adres(y) e-mail odbiorcy.
    4.  Wybierz, czy powiązać kupon z istniejącym kontem klienta.
    5.  Kliknij „Wyślij”, aby wygenerować i wysłać spersonalizowany kupon.

#### **Specyficzne ustawienia na stronie konfiguracji**

Chociaż główny interfejs modułu odbywa się za pośrednictwem sekcji „Menedżer szablonów e-mail” i „Silnik kuponów”, istnieją podstawowe klucze konfiguracyjne, które kontrolują domyślne zachowanie. Są one często zarządzane niejawnie przez interfejs modułu, ale warto zrozumieć ich cel.

-   **Tytuł wiadomości e-mail**

    -   **Co robi to ustawienie:** Jest to domyślny temat e-maili wysyłanych z kuponami, jeśli nie zostanie zastąpiony przez konkretny szablon.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy ustawione na „Twój specjalny rabat”*: E-maile będą domyślnie miały ten temat.
        -   *Gdy zmienione na „Ekskluzywna oferta od [Nazwa Twojego Sklepu]”*: Wszystkie nowe e-maile (bez konkretnego szablonu zastępującego go) będą używać tego nowego tematu.
    -   **Zalecana wartość:** Coś jasnego i zachęcającego, np. „Twój ekskluzywny kupon od [Nazwa Twojego Sklepu]”.
    -   **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby wszystkie Twoje e-maile z kuponami miały spójny komunikat marki w temacie.
-   **Plik szablonu e-mail**

    -   **Co robi to ustawienie:** Odnosi się do domyślnego pliku szablonu e-mail używanego do wysyłania kuponów. Sekcja „Menedżer szablonów e-mail” zapewnia bardziej przyjazny dla użytkownika sposób zarządzania i wybierania szablonów.
    -   **Wpływ zmiany tego ustawienia:**
        -   *Gdy ustawione na `voucher_email.html`*: Moduł użyje tego konkretnego pliku dla treści e-maila, jeśli nie zostanie wybrany żaden inny szablon.
    -   **Zalecana wartość:** Użyj interfejsu „Menedżer szablonów e-mail” do tworzenia i wybierania szablonów, ponieważ jest to bardziej elastyczne i nie wymaga bezpośredniej manipulacji plikami.
    -   **Scenariusz / przykład dla sprzedawcy:** Masz niestandardowy plik szablonu e-mail HTML, którego chcesz użyć jako podstawy dla wszystkich swoich e-maili z kuponami.

#### **Inne klucze konfiguracyjne (wewnętrzne)**

Są to wewnętrzne klucze konfiguracyjne PrestaShop, do których moduł może się odwoływać w swoich operacjach, ale zazwyczaj nie będziesz ich bezpośrednio konfigurować w interfejsie modułu.

-   `PS_SHOP_EMAIL`: Główny adres e-mail kontaktowy Twojego sklepu. Używany jako adres e-mail nadawcy dla kuponów.
-   `PS_SHOP_NAME`: Nazwa Twojego sklepu. Używana w tematach lub treściach e-maili.
-   `PS_LANG_DEFAULT`: Domyślny język Twojego sklepu.
-   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Ustawienie związane z językiem pracownika w panelu administracyjnym.
-   `mypresta_updates`, `update_`, `updatev_`: Wewnętrzne klucze używane przez moduły MyPresta.eu do sprawdzania aktualizacji i zarządzania wersjami.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | **Menedżer szablonów e-mail** | N/A (twórz w miarę potrzeb) | Twórz i zarządzaj niestandardowymi szablonami e-maili dla wiadomości z kuponami. |
| Strona konfiguracji modułu | **Silnik kuponów** | N/A (twórz w miarę potrzeb) | Generuj unikalne kody kuponów z określonymi regułami i wysyłaj je e-mailem. |
| Strona konfiguracji modułu | Tytuł wiadomości e-mail | „Twój specjalny rabat” (przykład) | Domyślny temat wiadomości e-mail z kuponami. |
| Strona konfiguracji modułu | Plik szablonu e-mail | `voucher_email.html` (przykład) | Domyślny plik HTML używany do treści wiadomości e-mail. Użyj Menedżera szablonów e-mail dla lepszej kontroli. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moi klienci nie otrzymują e-maili z kuponami. Co powinienem sprawdzić?**
O:

1.  **Sprawdź ustawienia e-maila w swoim sklepie:** Przejdź do **Zaawansowane > E-mail** w panelu administracyjnym PrestaShop. Upewnij się, że konfiguracja e-maila (SMTP lub PHP mail) jest poprawna i przetestuj wysyłanie ogólnego e-maila.
2.  **Foldery spamu:** Poproś klientów o sprawdzenie folderów spamu lub wiadomości-śmieci.
3.  **Treść szablonu e-maila:** Upewnij się, że Twoje szablony e-maili nie są zbyt „spamowe” (np. nadmierne użycie wielkich liter, zbyt wiele wykrzykników).
4.  **Logi modułu:** Sprawdź, czy moduł dostarcza jakiekolwiek logi lub komunikaty o błędach podczas procesu wysyłania. (Może to wymagać pomocy programisty).

**P: Kod kuponu został wysłany, ale klient twierdzi, że nie działa.**
O:

1.  **Sprawdź ważność kuponu:** W panelu administracyjnym PrestaShop przejdź do **Katalog > Rabaty > Reguły koszyka**. Znajdź kod kuponu i sprawdź daty ważności, minimalną kwotę, ograniczenia dla klientów oraz czy został już użyty.
2.  **Powiązanie z klientem:** Jeśli kupon był powiązany z konkretnym klientem, upewnij się, że klient jest zalogowany na właściwe konto, próbując go użyć.
3.  **Błędy typograficzne:** Poproś klienta o dwukrotne sprawdzenie, czy nie ma błędów typograficznych podczas wprowadzania kodu.

**P: Czy mogę wysłać ten sam kod kuponu do wielu klientów?**
O: Tak, możesz wygenerować jeden kod kuponu i wysłać go na wiele adresów e-mail. Jednak dla lepszego śledzenia i zapobiegania nadużyciom, zazwyczaj zaleca się generowanie unikalnych kodów dla każdego odbiorcy, zwłaszcza w przypadku spersonalizowanych ofert. „Silnik kuponów” modułu jest zaprojektowany do generowania unikalnych kodów.

**P: Jak dostosować wygląd szablonów e-maili?**
O: Użyj sekcji „Menedżer szablonów e-mail” w konfiguracji modułu. Zapewnia ona interfejs do edycji tematu i treści szablonów e-maili. W przypadku zaawansowanej personalizacji HTML/CSS, może być konieczna edycja podstawowych plików szablonów (patrz Sekcja 7 dla programistów).

**P: Moduł nie wyświetla się poprawnie po instalacji lub widzę pustą stronę.**
O:

1.  **Wyczyść pamięć podręczną Smarty:** Przejdź do **Zaawansowane > Wydajność** w panelu administracyjnym PrestaShop. Ustaw „Kompilacja szablonów” na „Ponownie kompiluj szablony, jeśli pliki zostały zaktualizowane”, a „Pamięć podręczna” na „Nie”. Następnie kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu. Po sprawdzeniu możesz przywrócić „Pamięć podręczną” na „Tak”, a „Kompilacja szablonów” na „Nigdy nie kompiluj ponownie…” dla wydajności.
2.  **Sprawdź wersję PHP:** Upewnij się, że Twoja wersja PHP mieści się w obsługiwanym zakresie (PHP 5.6 - 8.5).
3.  **Logi błędów serwera:** Sprawdź logi błędów PHP na swoim serwerze pod kątem konkretnych komunikatów o błędach. Zazwyczaj wymaga to dostępu do panelu sterowania hostingu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Wyślij e-mail z kuponem” stosuje standardową architekturę modułu PrestaShop, wykorzystując głównie klasę `Module` do swojej podstawowej funkcjonalności i konfiguracji. Integruje niestandardowy JavaScript i CSS dla swojego interfejsu panelu administracyjnego, w szczególności dla narzędzi do zarządzania szablonami e-mail i generowania kuponów. Moduł nie wprowadza niestandardowych kontrolerów front-office ani złożonych encji `ObjectModel`, ale raczej współdziała z wbudowanymi klasami PrestaShop `CartRule` (rabat) i `Mail`.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie zawiera żadnych niestandardowych kontrolerów front-office ani back-office w katalogu `controllers/`. Cała logika administracyjna i konfiguracja są obsługiwane w metodzie `getContent()` głównego pliku modułu (`sendvouchers.php`).

### 4.3 Klasy i modele podstawowe (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani modeli w katalogu `classes/`. Opiera się na podstawowych klasach PrestaShop, takich jak `CartRule` do zarządzania rabatami i `Mail` do wysyłania e-maili.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`sendvouchers/lib/emailTemplatesManager/js/emailTemplatesManager.js`**

    -   **Zakres:** Panel administracyjny (strona konfiguracji modułu).
    -   **Odpowiedzialność:** Zarządza interaktywnymi elementami interfejsu tworzenia, edycji i usuwania szablonów e-mail. Ten skrypt prawdopodobnie obsługuje wywołania AJAX do zapisywania/aktualizowania danych szablonów, dynamicznie renderuje formularze i zarządza interakcjami użytkownika w sekcji „Menedżer szablonów e-mail”. Może używać jQuery do manipulacji DOM i wiązania zdarzeń.
-   **`sendvouchers/lib/voucherengine/script.js`**

    -   **Zakres:** Panel administracyjny (strona konfiguracji modułu).
    -   **Odpowiedzialność:** Obsługuje sekcję „Silnik kuponów”. Ten skrypt jest odpowiedzialny za obsługę generowania kodów kuponów, ustawianie reguł rabatowych (np. procent, stała kwota, warunki), wybieranie szablonów e-mail i inicjowanie procesu wysyłania kuponów. Prawdopodobnie wykonuje walidację po stronie klienta i żądania AJAX do metody `getContent()` modułu w celu przetwarzania po stronie serwera.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`sendvouchers/lib/emailTemplatesManager/css/emailTemplatesManager.css`**

    -   **Zakres:** Stylizacja formularza administracyjnego panelu.
    -   **Odpowiedzialność:** Zapewnia stylizację interfejsu „Menedżera szablonów e-mail”, w tym formularzy do tworzenia/edycji szablonów, przycisków i potencjalnie widoków list.
    -   **Kluczowe selektory klas CSS:** Programiści mogą sprawdzić wyjście HTML modułu w panelu administracyjnym, aby zidentyfikować konkretne klasy (np. `.email-template-form`, `.template-list-item`) do nadpisania w swoich niestandardowych motywach administracyjnych lub za pośrednictwem `override.css`.
-   **`sendvouchers/lib/voucherengine/ps16.css`**

    -   **Zakres:** Stylizacja formularza administracyjnego panelu, specjalnie dla kompatybilności z PrestaShop 1.6.
    -   **Odpowiedzialność:** Zapewnia stylizację sekcji „Silnik kuponów”, potencjalnie obejmując układy formularzy, pola wejściowe i przyciski, z dostosowaniami do motywu panelu administracyjnego PrestaShop 1.6. Ten plik może być również ładowany w nowszych wersjach PS dla kompatybilności wstecznej, ale jego głównym celem jest PS 1.6.
    -   **Kluczowe selektory klas CSS:** Podobnie jak w przypadku `emailTemplatesManager.css`, programiści powinni sprawdzić wygenerowany HTML pod kątem konkretnych selektorów do nadpisania.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Wszystkie szablony znajdują się w katalogu `sendvouchers/lib/emailTemplatesManager/views/`, co wskazuje, że są one używane głównie do renderowania interfejsu panelu administracyjnego menedżera szablonów e-mail.

-   **`sendvouchers/lib/emailTemplatesManager/views/buttonManager.tpl`**

    -   **Zakres:** Szablon administracyjny.
    -   **Cel:** Prawdopodobnie renderuje przyciski lub kontrolki związane z zarządzaniem szablonami e-mail (np. „Dodaj nowy szablon”, „Zarządzaj szablonami”).
-   **`sendvouchers/lib/emailTemplatesManager/views/createTemplateForm.tpl`**

    -   **Zakres:** Szablon administracyjny.
    -   **Cel:** Renderuje formularz HTML do tworzenia nowego szablonu e-mail, w tym pola na temat, treść i potencjalnie wybór języka.
-   **`sendvouchers/lib/emailTemplatesManager/views/editTemplateForm.tpl`**

    -   **Zakres:** Szablon administracyjny.
    -   **Cel:** Renderuje formularz HTML do edycji istniejącego szablonu e-mail, wstępnie wypełniając pola bieżącymi danymi szablonu.
-   **`sendvouchers/lib/emailTemplatesManager/views/mainForm.tpl`**

    -   **Zakres:** Szablon administracyjny.
    -   **Cel:** Jest to prawdopodobnie główny szablon opakowujący dla sekcji „Menedżer szablonów e-mail”, orkiestrujący wyświetlanie listy szablonów, formularza tworzenia i formularza edycji.
-   **`sendvouchers/lib/emailTemplatesManager/views/selectInput.tpl`**

    -   **Zakres:** Szablon administracyjny.
    -   **Cel:** Wielokrotnego użytku fragment szablonu do renderowania pola wejściowego HTML `<select>`, prawdopodobnie do wyboru języka lub wyboru istniejącego szablonu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł nie tworzy jawnie niestandardowych tabel SQL podczas `install()`.
    -   Przechowuje swoje ustawienia konfiguracyjne (takie jak `sendvouchersTemplate`, `sendvouchersTitle`) w tabeli `ps_configuration` PrestaShop.
    -   Współdziała z podstawowymi tabelami PrestaShop `ps_cart_rule` i `ps_cart_rule_lang` podczas tworzenia i zarządzania kuponami rabatowymi.
-   **Tabela zarejestrowanych hooków**:
    Główna funkcjonalność modułu jest wykonywana za pośrednictwem jego metody `getContent()` w panelu administracyjnym. Chociaż opis modułu wspomina o „Hookach Front-Office: Nagłówek, Kolumny, Produkt lub Stopka”, dostarczony spis kodu nie pokazuje odpowiednich plików szablonów ani jawnych metod `hook` w `sendvouchers.php`, które renderowałyby zawartość w tych hookach front-office. Sugeruje to, że jeśli jakiekolwiek hooki front-office są zarejestrowane, służą one albo do wewnętrznego przetwarzania (np. `actionFrontControllerSetMedia` do ładowania zasobów), albo są pozostałościami z poprzednich wersji i nie są aktywnie używane do wyświetlania treści wizualnych.

    Podstawowa funkcjonalność wysyłania e-maili z kuponami jest wyzwalana przez działanie użytkownika w panelu administracyjnym, a nie przez ładowanie stron front-office.

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayBackOfficeHeader` | Przy każdym ładowaniu strony panelu administracyjnego. | Potencjalnie używany do ładowania specyficznych dla modułu CSS/JS dla jego strony konfiguracji. |
| `moduleRoutes` | Podczas inicjalizacji routingu URL. | (Jeśli zaimplementowano) Do definiowania niestandardowych przyjaznych adresów URL dla stron modułu. (Nie wykryto jawnie w tym module). |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny jest ładowany. | Do dodawania specyficznych dla modułu plików JavaScript i CSS do strony konfiguracji panelu administracyjnego. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego oraz pobrania najnowszych wersji modułu „Wyślij e-mail z kuponem”, odwiedź swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
"""
