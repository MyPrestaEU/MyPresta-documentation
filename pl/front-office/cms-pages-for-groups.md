---
title: "Strony CMS dla grup - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla programistów dla modułu PrestaShop „Strony CMS dla grup” od MyPresta.eu."
sidebar:
  label: "Strony CMS dla grup - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł CMS pages for groups na MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-pages-for-groups.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/cms-pages-for-groups/)
>
> ---


# Strony CMS dla grup

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Strony CMS dla grup)

Jest to główny ekran konfiguracji, na którym będziesz zarządzać tym, które grupy klientów mogą uzyskiwać dostęp do określonych stron CMS.

Po pierwszym wejściu na stronę konfiguracji zobaczysz listę wszystkich istniejących stron CMS. Dla każdej strony CMS znajdziesz opcje kontroli jej widoczności.

**Ogólna struktura strony:**
Strona konfiguracji wyświetla tabelę. Każdy wiersz w tabeli reprezentuje jedną z Twoich stron CMS. Dla każdej strony CMS zobaczysz:

-   **Nazwa strony:** Tytuł Twojej strony CMS (np. „O nas”, „Regulamin”).
-   **Grupy klientów:** Lista pól wyboru, po jednym dla każdej grupy klientów zdefiniowanej w Twoim sklepie PrestaShop (np. „Gość”, „Klient”, „Hurtownik”).

**Co robi to ustawienie:**
Dla każdej strony CMS wybierasz grupy klientów, które są **uprawnione** do przeglądania tej konkretnej strony. Jeśli klient nie należy do żadnej z wybranych grup dla danej strony, zostanie mu odmówiony dostęp do tej strony.

**Efekt zmiany tego ustawienia:**

-   **Gdy grupa jest zaznaczona dla strony CMS:** Klienci należący do tej grupy będą mogli normalnie przeglądać stronę CMS.
-   **Gdy grupa jest odznaczona dla strony CMS:** Klienci należący do tej grupy **nie** będą mogli przeglądać strony CMS. Jeśli spróbują uzyskać do niej dostęp, zostaną przekierowani na stronę błędu „Nie znaleziono strony”.
-   **Jeśli żadna grupa nie jest wybrana dla strony CMS:** Oznacza to, że strona jest faktycznie ukryta przed *wszystkimi* klientami, ponieważ żadna grupa nie ma uprawnień do jej przeglądania. Może to być przydatne dla stron w budowie lub treści przeznaczonych tylko do użytku wewnętrznego.
-   **Jeśli wszystkie grupy są wybrane dla strony CMS:** Oznacza to, że strona jest widoczna dla wszystkich, co skutecznie przywraca domyślne zachowanie PrestaShop dla tej konkretnej strony.

**Zalecana wartość:**
Zależy to całkowicie od Twoich potrzeb biznesowych.

-   Dla standardowych stron, takich jak „O nas” lub „Kontakt”, prawdopodobnie zaznaczysz wszystkie grupy.
-   Dla specyficznych warunków prawnych dla B2B, możesz zaznaczyć tylko swoją grupę „Hurtownik”.
-   Dla strony „Korzyści Klubu VIP”, możesz zaznaczyć tylko swoją grupę „Klient VIP”.

**Scenariusz/przykład dla sprzedawcy:**
Załóżmy, że masz trzy grupy klientów: „Gość” (niezalogowany), „Klient” (standardowi zarejestrowani użytkownicy) i „Hurtownik” (klienci B2B).

1.  **Scenariusz 1: Strona „O nas”**

    *   **Cel:** Ogólne informacje dla wszystkich.
    *   **Działanie:** Zaznacz „Gość”, „Klient” i „Hurtownik” dla strony „O nas”.
    *   **Wynik:** Wszyscy mogą zobaczyć stronę „O nas”.
2.  **Scenariusz 2: Strona „Regulamin dla Hurtowników”**

    *   **Cel:** Specyficzne warunki prawne tylko dla Twoich klientów B2B.
    *   **Działanie:** Zaznacz tylko „Hurtownik” dla strony „Regulamin dla Hurtowników”.
    *   **Wynik:** Tylko klienci z grupy „Hurtownik” mogą przeglądać tę stronę. Grupom „Gość” i „Klient” zostanie odmówiony dostęp.
3.  **Scenariusz 3: Strona „Szczegóły Programu Lojalnościowego”**

    *   **Cel:** Informacje dla zarejestrowanych klientów o ich punktach lojalnościowych.
    *   **Działanie:** Zaznacz „Klient” i „Hurtownik” (zakładając, że klienci hurtowi również mogą być częścią programu lojalnościowego) dla strony „Szczegóły Programu Lojalnościowego”.
    *   **Wynik:** Tylko zalogowani klienci (standardowi lub hurtowi) mogą przeglądać tę stronę. Gościom zostanie odmówiony dostęp.

**Zapisywanie zmian:**
Po dokonaniu wyborów dla wszystkich stron CMS, pamiętaj, aby kliknąć przycisk **„Zapisz”** (zazwyczaj na dole strony), aby zastosować zmiany.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | **Nazwa strony CMS** (np. „O nas”) | Różni się w zależności od strony | Kontroluje, które grupy klientów mogą przeglądać tę konkretną stronę CMS. |
| | Pole wyboru dla grupy **„Gość”** | Różni się | Jeśli zaznaczone, niezalogowani użytkownicy mogą przeglądać stronę. |
| | Pole wyboru dla grupy **„Klient”** | Różni się | Jeśli zaznaczone, użytkownicy, którzy dokonali zakupu jako gość, mogą przeglądać stronę. |
| | Pole wyboru dla grupy **„Zarejestrowany klient”** | Różni się | Jeśli zaznaczone, standardowi zarejestrowani klienci mogą przeglądać stronę. |
| | Pole wyboru dla grupy **„Hurtownik”** (lub dowolnej niestandardowej grupy) | Różni się | Jeśli zaznaczone, klienci z tej konkretnej grupy mogą przeglądać stronę. |
| | **Przycisk Zapisz** | N/A | Stosuje wszystkie wybrane ustawienia widoczności do stron CMS. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Ograniczyłem stronę CMS, ale nadal pojawia się w moim menu stopki/nagłówka. Dlaczego?**
O1: Ten moduł kontroluje *dostęp* do treści strony, a nie jej widoczność w menu nawigacyjnych. Jeśli chcesz ukryć sam link przed niektórymi grupami, musisz:
\* Ręcznie usunąć link z plików szablonu Twojego motywu (np. `footer.tpl`, `header.tpl`).
\* Użyć modułu do zarządzania menu, który oferuje widoczność elementów menu w oparciu o grupy.
\* Jeśli klient kliknie ograniczony link, nadal zostanie mu odmówiony dostęp do treści strony.

**P2: Klient jest zalogowany, ale nadal nie widzi strony, którą zezwoliłem dla jego grupy. Co jest nie tak?**
O2:
\* **Wyczyść pamięć podręczną:** Zawsze zacznij od wyczyszczenia pamięci podręcznej PrestaShop. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
\* **Zweryfikuj przypisanie do grupy:** Sprawdź dokładnie, czy klient jest rzeczywiście przypisany do prawidłowej grupy(grup) klientów, dla której zezwoliłeś na dostęp do strony CMS. Możesz to sprawdzić w **Klienci > Klienci**, edytując profil klienta.
\* **Konfiguracja modułu:** Ponownie sprawdź stronę konfiguracji modułu i upewnij się, że prawidłowe pole wyboru grupy jest zaznaczone dla tej konkretnej strony CMS.
\* **Pamięć podręczna przeglądarki:** Poproś klienta o wyczyszczenie pamięci podręcznej przeglądarki lub spróbowanie dostępu do strony w oknie incognito/prywatnym.

**P3: Czy mogę wyświetlić niestandardową wiadomość zamiast błędu „Nie znaleziono strony”, gdy dostęp jest zabroniony?**
O3: Ten moduł, w swojej obecnej wersji, przekierowuje do standardowej strony PrestaShop „Nie znaleziono strony”. Dostosowanie tego wymagałoby modyfikacji motywu lub dodatkowego modułu, który specjalnie obsługuje niestandardowe strony błędów w oparciu o odmowę dostępu.

**P4: Czy ten moduł spowolni mój sklep?**
O4: Nie, moduł jest bardzo lekki. Nadpisuje on podstawowy kontroler PrestaShop, aby sprawdzić uprawnienia grupy klientów przed załadowaniem strony CMS. To sprawdzenie jest wydajne i nie powinno zauważalnie wpływać na wydajność Twojego sklepu.

**P5: Zaktualizowałem PrestaShop i teraz moduł nie działa. Co powinienem zrobić?**
O5:
\* **Sprawdź wersję modułu:** Upewnij się, że masz najnowszą wersję modułu „Strony CMS dla grup” ze swojego konta MyPresta.eu, kompatybilną z Twoją nową wersją PrestaShop.
\* **Zainstaluj ponownie/Skonfiguruj ponownie:** Czasami po dużej aktualizacji PrestaShop moduły mogą wymagać ponownej instalacji lub rekonfiguracji. Spróbuj odinstalować, a następnie ponownie zainstalować moduł (Twoje ustawienia powinny zostać zachowane, ale zawsze najpierw wykonaj kopię zapasową). Następnie ponownie sprawdź swoje ustawienia na stronie konfiguracji modułu.
\* **Wyczyść pamięć podręczną:** Zawsze wyczyść pamięć podręczną PrestaShop po każdej aktualizacji lub zmianie modułu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Strony CMS dla grup” działa poprzez nadpisanie podstawowego `CmsController` w front office PrestaShop. Pozwala to na przechwytywanie żądań stron CMS *przed* ich renderowaniem i stosowanie niestandardowej logiki dostępu w oparciu o uprawnienia grup klientów skonfigurowane w panelu administracyjnym modułu. Moduł przechowuje swoją konfigurację bezpośrednio w tabeli `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `groupscms/override/controllers/front/CmsController.php`
        -   **Nazwa klasy i klasa nadrzędna**: `CmsController` (nadpisuje podstawowy `CmsController`)
        -   **Odpowiedzialność**: Jest to krytyczny komponent. Rozszerza oryginalny `CmsController` o metodę `init()`. Wewnątrz `init()` pobiera ID bieżącej strony CMS i sprawdza konfigurację modułu (`Configuration::get('CMSG_CMS_ID_' . (int)$cms->id)`) w celu określenia, które grupy klientów mają do niej dostęp. Jeśli bieżący klient (lub gość) nie należy do dozwolonej grupy, przekierowuje go na stronę „Nie znaleziono strony” (`$this->redirect_after = '404';`). Zapewnia to, że nieautoryzowani użytkownicy nie mogą przeglądać ograniczonych treści CMS.
-   **Kontrolery administracyjne Back-Office**: Brak. Konfiguracja modułu jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

Brak. Moduł nie definiuje niestandardowych klas `ObjectModel`. Bezpośrednio współdziała z istniejącymi obiektami PrestaShop `CMS` i `Group` oraz przechowuje swoją konfigurację w `ps_configuration`.

### 4.4 Zasoby JavaScript (`views/js/`)

Brak. Moduł nie zawiera żadnych niestandardowych plików JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   `groupscms/css.css`
    -   **Zakres**: Stylizacja formularza administracyjnego Back-Office.
    -   **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje**: Ten arkusz stylów jest prawdopodobnie używany do stylizacji tabeli konfiguracji modułu w panelu administracyjnym PrestaShop, zapewniając jej spójny wygląd z motywem administracyjnym PrestaShop. Może definiować style dla wierszy tabeli, pól wyboru lub etykiet w formularzu konfiguracji modułu.
    -   **Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim motywie**: Konkretne selektory znajdowałyby się w pliku, ale zazwyczaj dotyczyłyby elementów w wyjściu `getContent()` modułu, takich jak `table.groupscms_table`, `tr.groupscms_row`, `input[type="checkbox"].groupscms_checkbox` itp.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**: Brak. Moduł nie renderuje treści za pomocą standardowych hooków front-office.
-   **Szablony administracyjne (`views/templates/admin/`)**:

    -   `groupscms/admin.tpl`
        -   **Cel**: Ten szablon jest renderowany przez metodę `getContent()` głównego pliku modułu (`groupscms.php`). Generuje cały interfejs konfiguracji modułu w panelu administracyjnym PrestaShop. Obejmuje to tabelę zawierającą wszystkie strony CMS i pola wyboru dla każdej grupy klientów.
    -   `groupscms/cms.tpl`
        -   **Cel**: Ten szablon jest prawdopodobnie dołączany lub jest częścią używaną w `admin.tpl` do renderowania poszczególnych wierszy lub sekcji związanych ze stronami CMS w tabeli konfiguracji. Zawierałby pętlę do wyświetlania każdej strony CMS i powiązanych z nią pól wyboru grup.
-   **Szablony front-office (`views/templates/front/`)**: Brak. Moduł nie dodaje nowych szablonów front-office. Kontroluje dostęp do istniejących szablonów stron CMS.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    Moduł nie tworzy żadnych niestandardowych tabel SQL. Wszystkie dane konfiguracyjne są przechowywane w tabeli `ps_configuration`.

    -   **Klucze konfiguracyjne**:
        -   `CMSG_CMS_ID_[CMS_ID]`: Przechowuje ciąg wartości `group_id` oddzielonych przecinkami dla każdej strony CMS. Na przykład, `CMSG_CMS_ID_12` może przechowywać `"1,2,3"`, wskazując, że grupy o ID 1, 2 i 3 mają dostęp do strony CMS o ID 12.
        -   `groupscms_many_page`: (Prawdopodobnie wewnętrzna flaga lub starsze ustawienie, niekonfigurowalne bezpośrednio przez użytkownika).
        -   `mypresta_updates`, `update_`, `updatev_`: Są to wspólne klucze używane przez moduły MyPresta.eu do sprawdzania aktualizacji i śledzenia wersji.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Wykonywany, gdy kontroler administracyjny ustawia swoje media (CSS/JS). | Używany przez moduł do dołączania arkusza stylów `css.css` dla strony konfiguracji w panelu administracyjnym. |
| `displayBackOfficeHeader` | Wykonywany w sekcji `<head>` panelu administracyjnego. | Często używany do dołączania globalnych stylów CSS/JS administratora lub do sprawdzania aktualizacji. Moduł może używać tego do swojego mechanizmu aktualizacji. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego oraz pobrania najnowszych wersji modułu „Strony CMS dla grup”, odwiedź swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
