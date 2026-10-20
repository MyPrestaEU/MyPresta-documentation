---
title: "Zakładka bestsellerów na stronie głównej - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop 'Zakładka bestsellerów na stronie głównej' od MyPresta.eu."
sidebar:
  label: "Zakładka bestsellerów na stronie głównej - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Homepage tab best sellers na MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-best-sellers.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/homepage-tab-best-sellers/)
>
> ---


# Zakładka bestsellerów na stronie głównej

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane dla samego PrestaShop i są zazwyczaj dostępne w każdym nowoczesnym środowisku hostingowym.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij „Konfiguruj” obok modułu „Zakładka bestsellerów na stronie głównej” w Menedżerze modułów. Zostaniesz przeniesiony na jego stronę konfiguracji.

#### Liczba produktów do wyświetlenia

- **Co robi to ustawienie:** To ustawienie kontroluje, ile najlepiej sprzedających się produktów zostanie wyświetlonych w zakładce „Bestsellery” na Twojej stronie głównej.
- **Wpływ zmiany tego ustawienia:**
  - *Ustawienie na wyższą liczbę (np. 12):* W zakładce zostanie wyświetlonych więcej produktów, co da klientom szerszy wybór Twoich bestsellerów do przeglądania. Może to być korzystne dla sklepów z wieloma popularnymi produktami.
  - *Ustawienie na niższą liczbę (np. 4):* Zostanie wyświetlonych mniej produktów, co stworzy bardziej zwięzłą i skoncentrowaną prezentację. Może to być korzystne dla sklepów z mniejszą liczbą bestsellerów lub gdy chcesz podkreślić kilka wybranych.
- **Zalecana wartość:** Dobrym punktem wyjścia jest zazwyczaj od **8 do 12** produktów. Zapewnia to wystarczającą różnorodność, nie przytłaczając klienta ani nie sprawiając, że strona jest zbyt długa.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli masz duży katalog i wiele produktów, które konsekwentnie dobrze się sprzedają, możesz ustawić tę wartość na 10 lub 12, aby zaprezentować więcej swoich popularnych produktów. Jeśli wolisz czystszą, bardziej minimalistyczną stronę główną, możesz ustawić ją na 6.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ ## 5. Praktyczne zastosowania i najlepsze praktyki (Wskazówki dla profesjonalistów)

1.  **Wykorzystaj dowód społeczny dla nowych odwiedzających:**
    - **Scenariusz:** Nowy klient wchodzi na Twoją stronę główną. Nie zna Twojej marki ani Twoich produktów.
    - **Wskazówka dla profesjonalistów:** Zakładka „Bestsellery” natychmiast dostarcza dowodu społecznego, pokazując, co kupują i co lubią inni klienci. Upewnij się, że Twoje bestsellery mają dobre zdjęcia produktów i jasne opisy. Rozważ uruchomienie tymczasowej promocji (np. „Nasze 5 najlepszych bestsellerów - 10% zniżki w tym tygodniu!”), aby jeszcze bardziej zwrócić uwagę na tę sekcję.
2.  **Optymalizuj pod kątem produktów sezonowych i trendowych:**
    - **Scenariusz:** Twój sklep doświadcza sezonowych wzrostów sprzedaży (np. prezenty świąteczne, odzież letnia) lub ma produkty, które nagle stają się modne.
    - **Wskazówka dla profesjonalistów:** Chociaż moduł automatycznie identyfikuje bestsellery, możesz pośrednio na to wpływać, strategicznie promując niektóre produkty. Na przykład, latem, jeśli chcesz, aby Twoje stroje kąpielowe pojawiły się w „Bestsellerach”, upewnij się, że są dobrze zaopatrzone, mają konkurencyjne ceny i być może są prezentowane w innych działaniach marketingowych. W miarę jak będą się lepiej sprzedawać, naturalnie wzrosną w rankingach bestsellerów i pojawią się w zakładce.
3.  **Promuj krzyżowo z innymi sekcjami strony głównej:**
    - **Scenariusz:** Masz inne sekcje produktów na stronie głównej (np. „Nowe produkty”, „Polecane produkty”).
    - **Wskazówka dla profesjonalistów:** Użyj zakładki „Bestsellery” jako sekcji uzupełniającej. Jeśli produkt jest nowy i sprzedaje się wyjątkowo dobrze, może pojawić się zarówno w „Nowych produktach”, jak i w „Bestsellerach”, wzmacniając jego popularność. Unikaj zbyt wielu nakładających się produktów, jeśli to możliwe, aby zapewnić klientom większą różnorodność, ale nie ukrywaj prawdziwie najlepiej sprzedającego się nowego produktu tylko dla samej różnorodności. Automatyczny charakter modułu naturalnie to obsłuży.

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Moja zakładka „Bestsellery” nie wyświetla się na stronie głównej.**

- **O:** Najpierw upewnij się, że moduł jest zainstalowany i włączony w **Moduły > Menedżer modułów**. Następnie sprawdź jego konfigurację. Jeśli zakładka nadal się nie pojawia, może to być problem z pamięcią podręczną. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Jeśli Twój szablon jest mocno dostosowany, może nie być poprawnie podłączony do `displayHomeTab` i `displayHomeTabContent`. W takim przypadku może być konieczne skonsultowanie się z twórcą szablonu lub ekspertem PrestaShop.

**P2: Produkty w zakładce „Bestsellery” nie wydają się być moimi rzeczywistymi bestsellerami.**

- **O:** Moduł opiera się na wewnętrznych danych sprzedażowych PrestaShop do określania bestsellerów.
  - Upewnij się, że masz rzeczywiste dane sprzedażowe dla produktów. Nowe sklepy lub sklepy z bardzo małą liczbą sprzedaży mogą nie mieć wystarczających danych do stworzenia sensownej listy „bestsellerów”.
  - Obliczenia „bestsellerów” są zazwyczaj oparte na liczbie sprzedanych jednostek w danym okresie. Może minąć trochę czasu, zanim ostatnie sprzedaże odzwierciedlą się na liście.
  - Wyczyść pamięć podręczną PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**), aby upewnić się, że pobierane są najnowsze dane.

**P3: Jak często aktualizuje się lista „Bestsellerów”?**

- **O:** Lista bestsellerów jest dynamicznie generowana przez PrestaShop na podstawie danych sprzedażowych. Aktualizuje się automatycznie w miarę składania i przetwarzania zamówień. Jednak aby zmiany były widoczne w front office, może być konieczne wyczyszczenie pamięci podręcznej PrestaShop, zwłaszcza jeśli masz włączone agresywne buforowanie.

**P4: Czy mogę zmienić tytuł zakładki (np. z „Bestsellery” na „Nasze najlepsze propozycje”)?**

- **O:** Tak, możesz. Tytuł zakładki jest zazwyczaj przetłumaczalnym ciągiem znaków w module.
  1. Przejdź do **Lokalizacja > Tłumaczenia**.
  2. Wybierz „Tłumaczenia zainstalowanych modułów”.
  3. Wybierz swój szablon.
  4. Wybierz swój język.
  5. Znajdź moduł „Zakładka bestsellerów na stronie głównej” na liście.
  6. Zlokalizuj ciąg tekstowy dla tytułu zakładki (np. „Bestsellery”) i zmień go na żądany tekst. Pamiętaj, aby zapisać zmiany.

**P5: Produkty wyglądają dziwnie lub są źle wyrównane w zakładce.**

- **O:** Jest to zazwyczaj konflikt stylów CSS z Twoim szablonem PrestaShop. Moduł dostarcza dane produktu, ale Twój szablon jest odpowiedzialny za sposób wyświetlania tych danych (układ, czcionki, kolory, rozmiary obrazów).
  - Upewnij się, że Twój szablon jest aktualny.
  - Spróbuj wyczyścić pamięć podręczną PrestaShop (**Zaawansowane > Wydajność**).
  - Jeśli problem nadal występuje, może być konieczne dodanie niestandardowego CSS do Twojego szablonu, aby nadpisać domyślne style modułu lub szablonu. Zazwyczaj wymaga to pomocy programisty stron internetowych.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny modułu „Zakładka bestsellerów na stronie głównej” dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł `Homepage tab best sellers` to prosty moduł PrestaShop zaprojektowany do bezproblemowej integracji z systemem zakładek na stronie głównej. Wykorzystuje klasyczną strukturę modułu PrestaShop, głównie klasę `Module` i zaczepy front-office. Nie wprowadza niestandardowych kontrolerów, modeli ani złożonego JavaScript/CSS, opierając się zamiast tego na podstawowych funkcjonalnościach PrestaShop do pobierania danych produktów i istniejącym stylom szablonu do prezentacji. Jego główna logika znajduje się w pliku `homebestsellerstab.php`, obsługując konfigurację i rejestrację zaczepów.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Zawartość front-office modułu jest renderowana bezpośrednio za pomocą szablonów Smarty podłączonych do `displayHomeTab` i `displayHomeTabContent`.
- **Kontrolery Back-Office Admin**: Brak. Konfiguracja modułu jest obsługiwana przez metodę `getContent()` w głównej klasie modułu.

### 4.3 Klasy i modele podstawowe (`classes/`)

- Brak. Moduł nie definiuje żadnych niestandardowych klas ani nie rozszerza `ObjectModel`. Wykorzystuje podstawowe klasy PrestaShop `Product` i `ProductSale` (lub podobne wewnętrzne mechanizmy) do pobierania danych o najlepiej sprzedających się produktach.

### 4.4 Zasoby JavaScript (`views/js/`)

- Brak. Moduł nie zawiera żadnych niestandardowych plików JavaScript. Oczekuje się, że wszelkie interaktywne zachowania (takie jak przełączanie zakładek) będą obsługiwane przez istniejący JavaScript szablonu PrestaShop.

### 4.5 Arkusze stylów CSS (`views/css/`)

- Brak. Moduł nie zawiera żadnych niestandardowych plików CSS. Stylizacja zakładki i list produktów w niej jest całkowicie zależna od aktywnego szablonu PrestaShop. Programiści powinni sprawdzić wygenerowany kod HTML i celować w odpowiednie klasy/ID w CSS swojego szablonu, aby dostosować wygląd.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa dwóch plików szablonów Smarty, oba znajdujące się w katalogu `views/templates/hook/`, do renderowania swojej zawartości w front office.

-   **`views/templates/hook/tab.tpl`**

    -   **Zaczep**: `displayHomeTab`
    -   **Cel**: Ten szablon jest odpowiedzialny za renderowanie rzeczywistego klikalnego elementu zakładki na stronie głównej. Zazwyczaj zawiera tag `<li>` lub `<a>`, który reprezentuje zakładkę „Bestsellery”, w tym jej przetłumaczalny tytuł.
    -   **Wynik**: Element zakładki, który po kliknięciu ujawnia zawartość renderowaną przez `homebestsellerstab.tpl`.
-   **`views/templates/hook/homebestsellerstab.tpl`**

    -   **Zaczep**: `displayHomeTabContent`
    -   **Cel**: Ten szablon renderuje rzeczywistą listę lub siatkę najlepiej sprzedających się produktów, gdy zakładka „Bestsellery” jest aktywna. Otrzymuje tablicę danych produktów z logiki PHP modułu.
    -   **Wynik**: Kod HTML do wyświetlania produktów (np. kontenery `div`, zdjęcia produktów, nazwy, ceny, przyciski dodawania do koszyka). Zazwyczaj iteruje po zmiennej `$products` przekazanej do niego.

### 4.7 Schemat bazy danych i mapa zaczepów

-   **Tabele bazy danych**: Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoją konfigurację (np. `HOME_BEST_NBR`) w tabeli `ps_configuration` PrestaShop.
-   **Tabela zarejestrowanych zaczepów**:

| Nazwa zaczepu | Czas wykonania | Cel techniczny Klucz konfiguracyjny `HOME_BEST_NBR` służy do przechowywania liczby produktów do wyświetlenia.
`PS_LANG_DEFAULT` i `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` to klucze konfiguracyjne rdzenia PrestaShop używane do zarządzania domyślnym językiem i ustawieniami języka formularza pracownika. Nie są one bezpośrednio konfigurowane przez moduł, ale są dostępne w kontekście.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Zakładka bestsellerów na stronie głównej”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu). Najnowszą wersję modułu możesz pobrać z historii zamówień. W celu uzyskania pomocy technicznej lub zapytań, skorzystaj z kanałów wsparcia dostępnych na stronie MyPresta.eu.
