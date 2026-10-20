---
title: "Dodaj do koszyka tylko dla zalogowanych - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Dodaj do koszyka tylko dla zalogowanych” od MyPresta.eu."
sidebar:
  label: "Dodaj do koszyka tylko dla zalogowanych - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Add to cart for logged only na MyPresta.eu](https://mypresta.eu/modules/ordering-process/add-to-cart-for-logged-only.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/ordering-process/add-to-cart-for-logged-only/)
>
> ---


# Dodaj do koszyka tylko dla zalogowanych

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Zazwyczaj nie są potrzebne żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Dodaj do koszyka tylko dla zalogowanych”, aby uzyskać dostęp do jego ustawień.

#### **Pokaż**

- **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania podstawowej funkcjonalności modułu.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (Tak):* Moduł będzie aktywny. Niezalogowani użytkownicy nie będą mogli dodawać produktów do koszyka, a zostanie wyświetlona wiadomość z prośbą o zalogowanie się.
  - *Gdy wyłączone (Nie):* Moduł będzie nieaktywny. Wszyscy użytkownicy, niezależnie od tego, czy są zalogowani, czy nie, będą mogli dodawać produkty do koszyka zgodnie ze standardowym zachowaniem PrestaShop.
- **Zalecana wartość:** **Tak**, jeśli chcesz wymusić zasadę koszyka „tylko dla zalogowanych”. **Nie**, jeśli chcesz tymczasowo wyłączyć funkcję bez odinstalowywania modułu.
- **Scenariusz sprzedawcy / przykład:** Jeśli prowadzisz sklep B2B i chcesz, aby tylko Twoi zarejestrowani klienci biznesowi składali zamówienia, ustaw to na „Tak”. Jeśli tymczasowo otwierasz swój sklep na publiczne przeglądanie i dodawanie do koszyka w ramach specjalnej promocji, możesz ustawić to na „Nie” na ten okres.

#### **Tabela szybkiego odniesienia konfiguracji**

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Pokaż | Tak | Włącza/wyłącza podstawową funkcjonalność modułu, ograniczając „Dodaj do koszyka” do zalogowanych użytkowników. |

## 3. Rozwiązywanie problemów sprzedawcy i często zadawane pytania (FAQ)

**P: Włączyłem moduł, ale niezalogowani użytkownicy nadal mogą dodawać produkty do koszyka. Co jest nie tak?**
O:

1. **Wyczyść pamięć podręczną:** Najczęstszym problemem jest buforowanie. Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
2. **Pozycja modułu:** Upewnij się, że moduł jest prawidłowo podpięty. Chociaż moduł obsługuje to automatycznie, czasami konflikty motywów mogą przeszkadzać. Sprawdź konfigurację modułu i upewnij się, że jest aktywny.
3. **Kompatybilność z motywem:** Bardzo rzadko, wysoce dostosowany motyw może nadpisywać standardowe zachowania przycisków PrestaShop. Jeśli wyczyszczenie pamięci podręcznej nie działa, tymczasowo przełącz się na domyślny motyw PrestaShop (np. Classic), aby sprawdzić, czy problem nadal występuje. Jeśli problem zostanie rozwiązany, Twój motyw prawdopodobnie powoduje konflikt i może być konieczne, aby programista to zbadał.

**P: Czy mogę dostosować wiadomość wyświetlaną niezalogowanym użytkownikom?**
O: Tak, wiadomość jest zazwyczaj możliwa do przetłumaczenia. Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym. Wybierz „Tłumaczenia zainstalowanych modułów”, wybierz swój motyw, a następnie wybierz „Dodaj do koszyka tylko dla zalogowanych”. Powinieneś tam znaleźć ciąg tekstowy do modyfikacji dla każdego języka.

**P: Czy ten moduł wpłynie na moje SEO?**
O: Nie, ten moduł wpływa głównie na funkcjonalność przycisku „Dodaj do koszyka” dla użytkowników front-endu. Nie blokuje on robotów wyszukiwarek przed indeksowaniem stron produktów ani treści. Twoje produkty będą nadal widoczne i możliwe do znalezienia.

**P: Co się stanie, jeśli klient wyloguje się po dodaniu produktów do koszyka?**
O: Moduł zapobiega *dodawaniu* do koszyka, gdy użytkownik jest niezalogowany. Jeśli klient zaloguje się, doda produkty, a następnie wyloguje się, produkty zazwyczaj pozostają w jego koszyku (powiązane z jego kontem) na wypadek ponownego zalogowania. Ograniczenie modułu dotyczy czynności dodawania nowych produktów, gdy użytkownik nie jest zalogowany.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Dodaj do koszyka tylko dla zalogowanych” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł „Dodaj do koszyka tylko dla zalogowanych” to lekki moduł PrestaShop zaprojektowany przede wszystkim do przechwytywania i modyfikowania zachowania akcji „Dodaj do koszyka” w oparciu o status logowania użytkownika. Osiąga to poprzez wykorzystanie systemu hooków PrestaShop i wstrzykiwanie JavaScriptu w celu wyłączenia lub zmodyfikowania przycisku „Dodaj do koszyka” oraz wyświetlenia wiadomości dla niezalogowanych użytkowników. Nie wprowadza nowych tabel baz danych ani złożonych modeli obiektów, skupiając się zamiast tego na interakcji front-endowej i istniejących podstawowych funkcjonalnościach PrestaShop.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie wprowadza żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Jego logika jest głównie zawarta w głównym pliku `cartforlogged.php`.

### 4.4 Zasoby JavaScript (`views/js/`)

- **`cartforlogged/views/js/cfl-17500.js`**

  - **Zakres:** Front-office.
  - **Cel:** Ten skrypt jest prawdopodobnie przeznaczony dla wersji PrestaShop 1.7.x i 8.x (wskazuje na to `17500`). Celuje w przycisk „Dodaj do koszyka” (`#add_to_cart button`, `.add-to-cart`) i potencjalnie inne elementy, takie jak pola ilości.
  - **Funkcjonalność:**
    - Sprawdza, czy użytkownik jest zalogowany (`isLogged`).
    - Jeśli nie jest zalogowany, wyłącza przycisk „Dodaj do koszyka”, zmienia jego tekst (np. na „Tylko zalogowani użytkownicy…”) i potencjalnie dodaje klasę CSS, aby wizualnie oznaczyć go jako wyłączony.
    - Może również zapobiegać wysyłaniu formularzy lub wywołaniom AJAX związanym z dodawaniem produktów do koszyka.
    - Prawdopodobnie używa `prestashop.on('updateCart', ...)` lub podobnych słuchaczy zdarzeń, aby ponownie zastosować swoją logikę po aktualizacjach koszyka lub zmianach strony (np. gdy zmieniane są atrybuty produktu).
- **`cartforlogged/views/js/cfl.js`**

  - **Zakres:** Front-office.
  - **Cel:** Ten skrypt jest prawdopodobnie bardziej ogólną lub awaryjną wersją, potencjalnie dla starszych wersji PrestaShop (1.5.x, 1.6.x) lub jako podstawa dla bardziej specyficznego `cfl-17500.js`.
  - **Funkcjonalność:** Podobnie jak `cfl-17500.js`, identyfikuje przycisk „Dodaj do koszyka” (np. `#add_to_cart button`, `.exclusive button`), sprawdza status logowania i wyłącza przycisk dla niezalogowanych użytkowników. Może używać `$(document).ready()` jQuery i delegowania zdarzeń do obsługi dynamicznej zawartości.

### 4.5 Arkusze stylów CSS (`views/css/`)

- **`cartforlogged/views/css/cfl.css`**
  - **Zakres:** Stylizacja klienta front-office.
  - **Cel:** Zapewnia podstawową stylizację dla wyłączonego przycisku „Dodaj do koszyka” lub wiadomości wyświetlanej niezalogowanym użytkownikom.
  - **Kluczowe selektory klas CSS, które programiści mogą nadpisać:**
    - `.cfl_disabled_button`: Prawdopodobnie stosowany do przycisku „Dodaj do koszyka”, gdy jest on wyłączony przez moduł. Programiści mogą użyć tego do zmiany koloru tła, kursora, przezroczystości itp., aby wyraźnie wskazać, że jest nieaktywny.
    - `.cfl_message`: Jeśli moduł wstrzykuje konkretny element wiadomości, ta klasa będzie go stylizować.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **`cartforlogged/views/templates/admin/json.tpl`**
  - **Zakres:** Szablony administratora.
  - **Cel:** Ten szablon jest prawdopodobnie używany wewnętrznie przez metodę `getContent()` modułu do wyprowadzania danych JSON, prawdopodobnie dla żądań AJAX na stronie konfiguracji lub do dynamicznych aktualizacji treści. Nie jest to szablon widoczny w front-office. Może być używany do zwracania statusu konfiguracji lub innych danych do JavaScriptu na stronie administratora.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele baz danych**: Ten moduł nie tworzy żadnych niestandardowych tabel baz danych. Przechowuje swoje ustawienia konfiguracyjne (np. `CFL_LOGIN`) w standardowej tabeli `ps_configuration`.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Służy do dołączania zasobów CSS i JavaScript (`cfl.css`, `cfl.js`, `cfl-17500.js`), które modyfikują zachowanie przycisku „Dodaj do koszyka”. |
| `actionCartSave` | Po zapisaniu lub zaktualizowaniu koszyka. | Ten hook mógłby potencjalnie być używany do ponownej oceny zawartości koszyka lub stosowania ograniczeń, ale biorąc pod uwagę opis modułu, jego główną funkcją jest prawdopodobnie wstrzykiwanie JS po stronie front-endu za pośrednictwem `displayHeader`. Może to być rozwiązanie awaryjne lub sposób na zapewnienie walidacji po stronie serwera, chociaż opis modułu kładzie nacisk na stronę klienta. |
| `actionAdminControllerSetMedia` | Gdy kontroler administratora jest ładowany, a jego media (JS/CSS) są ustawiane. | Służy do dołączania wszelkich niezbędnych JavaScriptu lub CSS dla strony konfiguracji modułu w Panelu administracyjnym. |
| `header` | Podobnie jak `displayHeader`, często używane zamiennie lub dla konkretnych starszych motywów. | Służy do dołączania zasobów CSS i JavaScript, zapewniając kompatybilność z różnymi wersjami i motywami PrestaShop. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Dodaj do koszyka tylko dla zalogowanych”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
