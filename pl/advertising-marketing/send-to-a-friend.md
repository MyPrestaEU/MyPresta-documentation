---
title: "Wyślij do znajomego - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku i odniesienie dla programistów dla modułu PrestaShop 'Wyślij do znajomego' od MyPresta.eu."
sidebar:
  label: "Wyślij do znajomego - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Send to a friend na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/send-to-a-friend.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/send-to-a-friend/)
>
> ---


# Wyślij do znajomego

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do instalacji PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu „Wyślij do znajomego”. Tutaj możesz kontrolować, jak funkcja działa i wygląda na stronach produktów.

#### Ustawienia ogólne

-   **Co robi to ustawienie:** Ta sekcja zawiera podstawowe ustawienia do włączania lub wyłączania modułu i kontrolowania jego podstawowej funkcjonalności.
-   **Wpływ zmiany tego ustawienia:**
    -   *Po włączeniu:* Link/przycisk „Wyślij do znajomego” i funkcjonalność pojawią się na stronach produktów zgodnie z konfiguracją.
    -   *Po wyłączeniu:* Funkcja zostanie całkowicie ukryta w Twoim sklepie, a żadne e-maile nie będą mogły być wysyłane za jej pośrednictwem.
-   **Zalecana wartość:** **TAK** (Włączone), aby umożliwić klientom korzystanie z funkcji.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz tymczasowo wyłączyć funkcję z powodu konserwacji lub konkretnej kampanii marketingowej, przełącz to na „NIE”. W przeciwnym razie pozostaw „TAK”, aby wykorzystać marketing szeptany.

#### Opcje wyświetlania

-   **Co robi to ustawienie:** Te opcje kontrolują, gdzie link lub przycisk „Wyślij do znajomego” pojawi się na stronach produktów. Moduł wykorzystuje system hooków PrestaShop do umieszczania funkcji w różnych obszarach.
-   **Wpływ zmiany tego ustawienia:**
    -   *Wybór hooka (np. `displayProductButtons`):* Link „Wyślij do znajomego” zostanie wyrenderowany w tym konkretnym obszarze strony produktu.
    -   *Brak wyboru hooka:* Funkcja może w ogóle się nie pojawić lub może pojawić się w domyślnej lokalizacji, jeśli Twój szablon ma specyficzne renderowanie awaryjne.
-   **Zalecana wartość:** `displayProductButtons` lub `displayProductActions` to popularne i zalecane hooki, ponieważ umieszczają link blisko przycisku „Dodaj do koszyka”, co ułatwia jego odkrycie. Możesz również rozważyć `displayFooterProduct`, jeśli wolisz, aby znajdował się na dole szczegółów produktu.
-   **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz, aby link „Wyślij do znajomego” był bardzo widoczny i znajdował się w pobliżu głównego wezwania do działania, wybierz `displayProductButtons`. Jeśli wolisz, aby był mniej widoczny, być może na dole informacji o produkcie, wybierz `displayFooterProduct`. Eksperymentuj z różnymi hookami, aby zobaczyć, co najlepiej wygląda z Twoim szablonem.

#### Szablon i treść e-maila

-   **Co robi to ustawienie:** Ta sekcja umożliwia dostosowanie tematu i treści e-maila wysyłanego do znajomego.
-   **Wpływ zmiany tego ustawienia:**
    -   *Zmiana tematu:* Temat e-maila będzie odzwierciedlał Twój niestandardowy tekst, czyniąc go bardziej angażującym lub markowym.
    -   *Zmiana treści:* Treść e-maila będzie zawierać Twoją niestandardową wiadomość, umożliwiając personalizację rekomendacji. Możesz używać symboli zastępczych, takich jak `{product_name}` i `{product_link}`, które zostaną automatycznie zastąpione rzeczywistymi szczegółami produktu.
-   **Zalecana wartość:** Użyj jasnego, zachęcającego tematu (np. „Sprawdź ten produkt z {nazwa\_Twojego\_sklepu}!”) i przyjaznej, informacyjnej wiadomości w treści. Zawsze dołączaj `{product_name}` i `{product_link}`, aby upewnić się, że znajomy wie, co jest polecane i jak to znaleźć.
-   **Scenariusz/przykład dla sprzedawcy:** Możesz dostosować e-mail, aby brzmiał: „Cześć {imię\_znajomego}, {imię\_klienta} pomyślał, że może Ci się spodobać ten produkt z Mojego Niesamowitego Sklepu! Nazywa się {product\_name} i możesz go znaleźć tutaj: {product\_link}. Udanych zakupów!”

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz/Wyłącz moduł | Włączony | Kontroluje, czy funkcja „Wyślij do znajomego” jest aktywna w Twoim sklepie. |
| Konfiguracja modułu | Hook wyświetlania | `displayProductButtons` | Określa, gdzie link „Wyślij do znajomego” pojawia się na stronach produktów. |
| Konfiguracja modułu | Temat e-maila | „Sprawdź ten produkt!” | Dostosowuje temat e-maila wysyłanego do znajomego. |
| Konfiguracja modułu | Treść e-maila | „Cześć {imię\_znajomego}, {imię\_klienta} pomyślał, że może Ci się spodobać ten produkt: {product\_name}. Możesz go znaleźć tutaj: {product\_link}” | Dostosowuje treść e-maila, w tym dynamiczne szczegóły produktu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Link „Wyślij do znajomego” nie pojawia się na moich stronach produktów. Co powinienem zrobić?**
O:

1.  **Sprawdź status modułu:** Przejdź do **Moduły > Menedżer modułów** i upewnij się, że moduł „Wyślij do znajomego” jest zainstalowany i włączony.
2.  **Zweryfikuj konfigurację:** Przejdź do strony konfiguracji modułu i upewnij się, że moduł jest „Włączony” i że wybrałeś co najmniej jeden „Hook wyświetlania” (np. `displayProductButtons`).
3.  **Wyczyść pamięć podręczną:** PrestaShop często buforuje zawartość. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
4.  **Kompatybilność z szablonem:** Jeśli używasz niestandardowego szablonu, może on nie być wyraźnie zaprojektowany do renderowania wszystkich hooków PrestaShop. Spróbuj tymczasowo przełączyć się na domyślny szablon PrestaShop, aby sprawdzić, czy link się pojawi. Jeśli tak, Twój szablon może wymagać niewielkiej modyfikacji przez webmastera, aby wyświetlić wybrany hook.

**P: Moi klienci wysyłają e-maile, ale ich znajomi ich nie otrzymują.**
O:

1.  **Sprawdź foldery spamu:** Poproś znajomego, aby sprawdził swój folder spamu lub wiadomości-śmieci.
2.  **Zweryfikuj ustawienia e-mail:** Upewnij się, że ustawienia e-mail Twojego sklepu PrestaShop są poprawnie skonfigurowane w **Zaawansowane > E-mail**. Przetestuj wysyłanie ogólnego e-maila z PrestaShop, aby potwierdzić, że Twój serwer pocztowy działa.
3.  **Logi modułu (sprawdzenie przez programistę):** Programista może sprawdzić logi poczty PrestaShop (jeśli są włączone) lub logi błędów serwera pod kątem problemów związanych z wysyłaniem e-maili.

**P: Czy mogę zmienić tekst linku „Wyślij do znajomego” lub pól formularza?**
O: Tak, możesz przetłumaczyć lub zmodyfikować ciągi tekstowe (etykiety, tekst przycisku itp.) modułu za pomocą narzędzia tłumaczeń PrestaShop. Przejdź do **Lokalizacja > Tłumaczenia**, wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój szablon, a następnie wybierz moduł „Wyślij do znajomego”. Następnie możesz edytować cały widoczny tekst.

**P: Formularz pop-up wygląda dziwnie lub nie jest poprawnie ostylowany na moim urządzeniu mobilnym.**
O:

1.  **Wyczyść pamięć podręczną przeglądarki:** Poproś klienta, aby wyczyścił pamięć podręczną przeglądarki na swoim urządzeniu mobilnym.
2.  **Konflikty szablonów:** Niestandardowe szablony mogą czasami nadpisywać lub kolidować ze stylami modułu. Chociaż moduł zawiera własny CSS (`send2friend.css`), CSS Twojego szablonu może mieć pierwszeństwo. Webmaster może zbadać stronę za pomocą narzędzi deweloperskich przeglądarki, aby zidentyfikować i rozwiązać konflikty CSS.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł „Wyślij do znajomego” (`send2friend`) to standardowy moduł PrestaShop implementujący wzorzec MVC. Wykorzystuje głównie kontrolery frontowe do żądań AJAX, szablony Smarty do renderowania formularza i hooki do integracji ze stroną produktu. Nie wprowadza niestandardowych tabel baz danych ani złożonych ObjectModels, opierając się na podstawowej funkcjonalności poczty PrestaShop.

### 4.2 Kontrolery (`controllers/`)

#### Kontrolery Front-Office

-   **`controllers/front/AjaxSend.php`**
    -   **Nazwa klasy:** `Send2FriendAjaxSendModuleFrontController`
    -   **Klasa nadrzędna:** `ModuleFrontController`
    -   **Odpowiedzialność:** Ten kontroler obsługuje żądanie AJAX inicjowane, gdy użytkownik przesyła formularz „Wyślij do znajomego”. Odbiera imię nadawcy, imię znajomego, adres e-mail znajomego i identyfikator produktu. Następnie konstruuje i wysyła e-mail za pomocą metody `Mail::Send()` PrestaShop. Zwraca odpowiedź JSON wskazującą sukces lub porażkę.
-   **`controllers/front/index.php`**
    -   **Nazwa klasy:** `Send2FriendIndexModuleFrontController`
    -   **Klasa nadrzędna:** `ModuleFrontController`
    -   **Odpowiedzialność:** Jest to kontroler zastępczy lub domyślny kontroler frontowy. W wielu modułach może on obsługiwać dedykowaną stronę front-office. Dla „Wyślij do znajomego” jego główną rolą może być zapewnienie ładowania zasobów front-office modułu lub służyć jako podstawa dla innych kontrolerów frontowych. Biorąc pod uwagę funkcjonalność modułu, kontroler `AjaxSend` jest bardziej aktywny.

### 4.3 Klasy i modele podstawowe (`classes/`)

Moduł nie zawiera żadnych niestandardowych klas ani modeli w katalogu `classes/`. Wykorzystuje podstawowe funkcjonalności PrestaShop, w szczególności `Mail` do wysyłania e-maili i `Product` do pobierania informacji o produkcie.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`views/js/send2friend.js`**
    -   **Zakres:** Front-office.
    -   **Szczegóły:** Ten skrypt odpowiada za interakcję front-endową funkcji „Wyślij do znajomego”.
        -   Prawdopodobnie dołącza słuchacza zdarzeń do linku/przycisku „Wyślij do znajomego”, aby otworzyć modalne okno lub wyświetlić formularz.
        -   Obsługuje przesyłanie formularza, zbierając dane (imię nadawcy, imię znajomego, e-mail znajomego, identyfikator produktu).
        -   Wysyła żądanie AJAX do kontrolera frontowego `AjaxSend.php`.
        -   Przetwarza odpowiedź JSON z serwera (sukces/błąd) i dostarcza użytkownikowi informację zwrotną (np. „E-mail wysłany pomyślnie!” lub „Błąd podczas wysyłania e-maila.”).
        -   Może zawierać logikę walidacji formularza (np. sprawdzanie poprawnych formatów e-mail).
        -   Wykorzystuje jQuery do manipulacji DOM i wywołań AJAX, co jest powszechne w front-office PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`views/css/send2friend.css`**
    -   **Zakres:** Stylizacja klienta front-office.
    -   **Szczegóły:** Ten arkusz stylów zapewnia podstawową stylizację wizualną dla linku „Wyślij do znajomego”, modalnego okna pop-up (jeśli jest używane) i pól formularza w nim.
        -   Definiuje style dla przycisku/linku, pól wejściowych, etykiet i wszelkich komunikatów o sukcesie/błędzie.
        -   Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim szablonie, zazwyczaj obejmują klasy takie jak `.send2friend-button`, `.send2friend-modal`, `.send2friend-form`, `.send2friend-input` itp. Programiści mogą sprawdzić wyrenderowany kod HTML, aby znaleźć dokładne używane klasy.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **`views/templates/hook/send2friend-extra.tpl`**
    -   **Zakres:** Front-office.
    -   **Renderowanie hooka:** Ten szablon jest przeznaczony do renderowania w różnych hookach strony produktu (np. `displayProductButtons`, `displayProductActions`, `displayFooterProduct`).
    -   **Blok wizualny:** Wyświetla strukturę HTML dla linku/przycisku „Wyślij do znajomego” oraz powiązanego modalnego okna lub formularza wbudowanego. Obejmuje to pola wejściowe dla imion i adresów e-mail oraz przycisk wysyłania. Zawiera również niezbędne ukryte pola (takie jak `product_id`) i potencjalnie strukturę do wyświetlania komunikatów o sukcesie/błędzie.

### 4.7 Schemat bazy danych i mapa hooków

#### Tabele baz danych

Moduł „Wyślij do znajomego” nie tworzy żadnych niestandardowych tabel baz danych. Przechowuje swoje ustawienia konfiguracyjne (takie jak status włączenia, wybrany hook, temat i treść e-maila) w tabeli `ps_configuration` PrestaShop.

-   **`ps_configuration`**: Przechowuje ustawienia modułu z kluczami zazwyczaj poprzedzonymi prefiksem `SEND2FRIEND_`.

#### Tabela zarejestrowanych hooków

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Służy do globalnego ładowania zasobów CSS i JavaScript modułu. |
| `displayProductButtons` | W pobliżu przycisku „Dodaj do koszyka” na stronach produktów. | Częste umiejscowienie linku „Wyślij do znajomego”. |
| `displayProductActions` | Inny często używany hook w pobliżu akcji produktu. | Alternatywne umiejscowienie linku „Wyślij do znajomego”. |
| `displayFooterProduct` | Na dole bloku informacji o produkcie. | Mniej widoczne umiejscowienie linku „Wyślij do znajomego”. |
| `displayRightColumnProduct` | W prawej kolumnie strony produktu (jeśli włączone przez szablon). | Możliwe umiejscowienie linku „Wyślij do znajomego”. |
| `displayLeftColumnProduct` | W lewej kolumnie strony produktu (jeśli włączone przez szablon). | Możliwe umiejscowienie linku „Wyślij do znajomego”. |

Metoda `install()` modułu rejestruje te hooki, a metoda `uninstall()` je wyrejestrowuje. Konkretny hook wybrany przez sprzedawcę w konfiguracji określa, który z nich jest aktywnie używany do wyświetlania szablonu.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Wyślij do znajomego”, zapoznaj się ze swoim kontem klienta MyPresta.eu. Możesz pobrać najnowsze wersje i uzyskać dostęp do zasobów wsparcia bezpośrednio z [MyPresta.eu](https://mypresta.eu).
