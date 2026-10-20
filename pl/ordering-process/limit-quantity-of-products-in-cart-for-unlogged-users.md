---
title: "Limit ilości produktów w koszyku dla niezalogowanych użytkowników - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów modułu PrestaShop „Limit ilości produktów w koszyku dla niezalogowanych użytkowników” od MyPresta.eu."
sidebar:
  label: "Limit ilości produktów w koszyku dla niezalogowanych użytkowników - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Limit quantity of products in cart for unlogged users na MyPresta.eu](https://mypresta.eu/modules/ordering-process/limit-quantity-of-products-in-cart-for-unlogged-users.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/limit-quantity-of-products-in-cart-for-unlogged-users/)
>
> ---


# Limit ilości produktów w koszyku dla niezalogowanych użytkowników

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (Każda grupa ustawień pogrupowana według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny i jedyny ekran konfiguracji modułu. Znajdziesz go, przechodząc do **Moduły > Menedżer modułów**, wyszukując „Limit ilości produktów w koszyku dla niezalogowanych użytkowników” i klikając „Konfiguruj”.

#### **Maksymalna ilość produktów w koszyku dla niezalogowanych użytkowników**

-   **Co robi to ustawienie:** Jest to kluczowe ustawienie modułu. Definiuje absolutną maksymalną całkowitą ilość pozycji, jaką niezalogowany klient może mieć w swoim koszyku.
-   **Efekt zmiany tego ustawienia:**
    -   *Jeśli ustawiono na 0:* Moduł zostanie skutecznie wyłączony, a niezalogowani użytkownicy będą mogli dodawać nieograniczoną ilość produktów do koszyka, tak jak zalogowani użytkownicy.
    -   *Jeśli ustawiono na liczbę większą niż 0 (np. 5):* Niezalogowany klient będzie mógł dodawać przedmioty do koszyka, dopóki całkowita ilość wszystkich przedmiotów nie osiągnie tej liczby. Jeśli spróbuje dodać kolejny przedmiot, który przekroczyłby ten limit, moduł zapobiegnie dodaniu i wyświetli ostrzegawczy popup.
-   **Zalecana wartość:** Zależy to całkowicie od Twojej strategii biznesowej.
    -   *Dla sklepów B2C, które chcą delikatnie zachęcić do logowania:* Wartość taka jak `3` lub `5` może być skuteczna.
    -   *Dla sklepów B2B lub sklepów z przedmiotami o wysokiej wartości:* Niższa wartość, taka jak `1` lub `2`, może być odpowiednia, aby zapewnić, że tylko poważni, zalogowani kupujący mogą rezerwować towar.
    -   *Jeśli nie chcesz żadnych limitów:* Ustaw na `0`.
-   **Scenariusz/przykład dla sprzedawcy:** Sprzedajesz koszulki z własnym nadrukiem. Chcesz, aby przypadkowi przeglądający widzieli kilka wzorów w swoim koszyku, ale aby złożyli większe zamówienie, wolisz, aby się zalogowali. Ustawiasz to na `3`. Niezalogowany klient dodaje koszulkę (ilość 1), następnie kolejną (ilość 1), a następnie trzecią (ilość 1). Ich koszyk ma teraz 3 przedmioty. Jeśli spróbują dodać czwartą koszulkę, zobaczą wiadomość popup, zachęcającą ich do zalogowania się.

#### **Wiadomość dla niezalogowanych użytkowników**

-   **Co robi to ustawienie:** Pozwala dostosować tekst wiadomości popup, która pojawia się, gdy niezalogowany użytkownik próbuje przekroczyć zdefiniowany limit ilości w koszyku.
-   **Efekt zmiany tego ustawienia:**
    -   *Jeśli pozostawisz domyślne:* Zostanie wyświetlona standardowa wiadomość „Jako niezalogowany klient nie możesz dodać więcej produktów do koszyka. Zaloguj się, aby kontynuować proces dodawania do koszyka.”
    -   *Jeśli dostosujesz:* Zamiast tego zostanie wyświetlona Twoja niestandardowa wiadomość. Pozwala to dostosować ton, dodać konkretne instrukcje, a nawet dołączyć link (chociaż bezpośrednie linki w popupach mogą być trudne bez dalszej personalizacji).
-   **Zalecana wartość:** Domyślna wiadomość jest jasna i skuteczna. Zmień ją tylko, jeśli masz konkretny styl marki lub dodatkowe instrukcje, które chcesz przekazać. Zachowaj zwięzłość.
-   **Scenariusz/przykład dla sprzedawcy:** Chcesz nieco łagodniejszego tonu. Zmieniasz wiadomość na: „Aby dodać więcej przedmiotów do koszyka, zaloguj się lub utwórz konto. Chcielibyśmy, abyś dołączył do naszej społeczności!”

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | **Maksymalna ilość produktów w koszyku dla niezalogowanych użytkowników** | `0` (wyłączone) / `3-5` (zalecane dla B2C) | Ustawia całkowitą liczbę przedmiotów, które niezalogowany klient może dodać do koszyka. Zapobiega dalszym dodawaniom i wyświetla popup, jeśli limit zostanie przekroczony. |
| Konfiguracja modułu | **Wiadomość dla niezalogowanych użytkowników** | „Jako niezalogowany klient nie możesz dodać więcej produktów do koszyka. Zaloguj się, aby kontynuować proces dodawania do koszyka.” | Dostosowuje tekst wyświetlany w popupie, gdy niezalogowany użytkownik osiągnie limit koszyka. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Ustawiłem limit, ale niezalogowani użytkownicy nadal mogą dodawać nieograniczoną liczbę produktów. Co jest nie tak?**
O:

1.  **Sprawdź ustawienie „Maksymalna ilość”:** Upewnij się, że jest ustawione na liczbę większą niż `0`. Jeśli jest `0`, moduł jest wyłączony.
2.  **Wyczyść pamięć podręczną przeglądarki:** Twoja przeglądarka może wyświetlać starą wersję strony. Spróbuj wyczyścić pamięć podręczną i pliki cookie przeglądarki lub przetestuj w oknie incognito/prywatnym.
3.  **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” w prawym górnym rogu.
4.  **Upewnij się, że jesteś naprawdę niezalogowany:** Sprawdź dwukrotnie, czy nie jesteś zalogowany na konto klienta w swojej przeglądarce. Najłatwiejszym sposobem testowania jest otwarcie nowego okna incognito/prywatnego.

**P: Wiadomość popup nie wyświetla się lub wygląda dziwnie.**
O:

1.  **Sprawdź ustawienie modułu „Wiadomość dla niezalogowanych użytkowników”:** Upewnij się, że nie jest puste, jeśli oczekujesz niestandardowej wiadomości.
2.  **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany tak, aby był kompatybilny, bardzo mocno dostosowane motywy mogą czasami kolidować z JavaScriptem lub CSS. Jeśli popup w ogóle się nie pojawia, sprawdź konsolę programisty przeglądarki pod kątem błędów JavaScript (klawisz F12, następnie zakładka Konsola). Jeśli wygląda dziwnie, może to być konflikt CSS. Skontaktuj się z pomocą techniczną MyPresta.eu, podając szczegóły swojego motywu.

**P: Czy ten moduł wpływa na zalogowanych klientów?**
O: Nie, ten moduł jest skierowany konkretnie do *niezalogowanych* użytkowników. Gdy klient zaloguje się na swoje konto, limit ilości nałożony przez ten moduł przestaje go dotyczyć.

**P: Czy mogę ustawić różne limity dla różnych kategorii produktów?**
O: Nie, ten moduł stosuje jeden, globalny limit ilości dla wszystkich produktów w koszyku dla niezalogowanych użytkowników. Nie obsługuje limitów specyficznych dla kategorii ani produktów.

**P: Co się stanie, jeśli niezalogowany użytkownik doda 3 przedmioty, następnie się zaloguje, a następnie spróbuje dodać więcej?**
O: Gdy użytkownik się zaloguje, nie jest już uważany za „niezalogowanego”. Ograniczenie modułu zostaje zniesione i może on kontynuować dodawanie produktów do koszyka bez żadnego limitu ilości z tego modułu.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Limit ilości produktów w koszyku dla niezalogowanych użytkowników” (`lqfu`) to lekki moduł PrestaShop zaimplementowany głównie poprzez główną klasę modułu (`lqfu/index.php`) i niestandardowy plik JavaScript (`lqfu/views/js/lqfu.js`). Wykorzystuje system hooków PrestaShop do wstrzykiwania swojego JavaScriptu do front office i używa AJAX do komunikacji z logiką po stronie serwera w celu sprawdzenia i egzekwowania limitu ilości w koszyku dla użytkowników-gości. Moduł przechowuje swoją konfigurację w `ps_configuration`.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**: Brak. Logika front-office modułu jest obsługiwana bezpośrednio za pośrednictwem pliku głównego modułu `hookDisplayHeader` i żądań AJAX, które są przetwarzane przez podstawowy `CartController` lub `ProductController` PrestaShop i przechwytywane przez logikę modułu.
-   **Kontrolery Back-Office Admin**: Brak. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego modułu.

### 4.3 Główne klasy i modele (`classes/`)

-   W tym module nie są zdefiniowane żadne niestandardowe klasy rozszerzające `ObjectModel`. Cała logika znajduje się w głównej klasie `Lqfu` w `index.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   **`lqfu/views/js/lqfu.js`**
    -   **Zakres:** Front-office.
    -   **Cel:** Ten skrypt jest odpowiedzialny za przechwytywanie akcji „Dodaj do koszyka”, sprawdzanie aktualnej ilości w koszyku dla niezalogowanych użytkowników i wyświetlanie niestandardowej wiadomości popup, jeśli limit zostanie przekroczony.
    -   **Kluczowa funkcjonalność:**
        -   Wiąże słuchaczy zdarzeń z przyciskami „Dodaj do koszyka” (lub formularzami) w całym sklepie (np. strona produktu, listy kategorii).
        -   Przy próbie „Dodaj do koszyka” najpierw sprawdza, czy użytkownik jest zalogowany.
        -   Jeśli użytkownik nie jest zalogowany, pobiera aktualną ilość w koszyku (albo z ukrytego elementu, albo wykonując wywołanie AJAX, jeśli to konieczne).
        -   Porównuje aktualną ilość w koszyku + dodawaną ilość z skonfigurowanym maksymalnym limitem.
        -   Jeśli limit zostanie przekroczony, zapobiega domyślnej akcji „Dodaj do koszyka”, wyświetla niestandardowy modal/popup ze skonfigurowaną wiadomością i potencjalnie tymczasowo wyłącza przycisk „Dodaj do koszyka”.
        -   Skrypt prawdopodobnie używa jQuery do manipulacji DOM i obsługi zdarzeń, co jest powszechne w front-office PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

-   **`lqfu/views/css/lqfu.css`**
    -   **Zakres:** Stylizacja klienta front-office.
    -   **Cel:** Zapewnia podstawową stylizację wiadomości popup, która pojawia się, gdy niezalogowany użytkownik przekroczy limit ilości w koszyku.
    -   **Kluczowe selektory klas CSS:** Programiści mogą oczekiwać klas związanych z kontenerem popup, tekstem wiadomości i ewentualnie przyciskami zamykania. Można je nadpisać w pliku `custom.css` lub `theme.css` niestandardowego motywu, aby dopasować je do brandingu sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**: Żadne nie są jawnie wymienione, ale moduł może niejawnie renderować zawartość za pośrednictwem `displayHeader` lub podobnych hooków, jeśli musi wstrzyknąć ukryte dane lub początkowe zmienne JS.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   **`lqfu/views/templates/admin/json.tpl`**: Ten szablon jest prawdopodobnie używany do renderowania danych JSON w ustrukturyzowany sposób w Panelu administracyjnym, być może do debugowania lub konkretnych odpowiedzi AJAX ze strony konfiguracji modułu, chociaż jego bezpośrednie użycie do głównej konfiguracji jest mniej powszechne. Może to być pozostałość lub być używane do konkretnej wewnętrznej funkcji modułu.
-   **Szablony front-office (`views/templates/front/`)**: Brak. Popup jest prawdopodobnie generowany dynamicznie za pomocą JavaScriptu.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:
    -   Moduł nie tworzy żadnych niestandardowych tabel SQL.
    -   Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration`:
        -   `PS_LQFU_MAX_QUANTITY`: Przechowuje wartość całkowitą dla maksymalnej ilości produktów dla niezalogowanych użytkowników.
        -   `PS_LQFU_MESSAGE`: Przechowuje wartość ciągu znaków dla niestandardowej wiadomości wyświetlanej w popupie.
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Wstrzykuje pliki CSS (`lqfu.css`) i JavaScript (`lqfu.js`) modułu do front office. Może również przekazywać zmienne konfiguracyjne (takie jak maksymalna ilość i wiadomość) do JavaScriptu. |
| `actionCartSave` | Po zapisaniu koszyka (np. dodaniu/usunięciu produktu). | Moduł prawdopodobnie przechwytuje ten hook (lub podobny, taki jak `actionObjectCartAddAfter`), aby ponownie ocenić ilość w koszyku i potencjalnie zapobiec dodawaniu przedmiotów, jeśli limit zostanie przekroczony dla niezalogowanego użytkownika. To tutaj nastąpi walidacja po stronie serwera, zanim zostanie uruchomiony popup JS. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i dalszej pomocy z modułem „Limit ilości produktów w koszyku dla niezalogowanych użytkowników” prosimy odwiedzić swoje konto klienta na stronie [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań.
