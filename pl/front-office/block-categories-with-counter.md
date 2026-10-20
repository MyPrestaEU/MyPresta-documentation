---
title: "Blok kategorii z licznikiem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Blok kategorii z licznikiem” od MyPresta.eu."
sidebar:
  label: "Blok kategorii z licznikiem - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Block categories with counter na MyPresta.eu](https://mypresta.eu/modules/front-office-features/block-categories-with-counter.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/block-categories-with-counter/)
>
> ---


# Blok kategorii z licznikiem

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne specjalne konfiguracje serwera poza standardowym środowiskiem hostingowym PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

Moduł „Blok kategorii z licznikiem” oferuje prostą konfigurację, skupioną głównie na włączaniu lub wyłączaniu jego podstawowej funkcjonalności.

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji, kliknięcie „Konfiguruj” dla modułu „Blok kategorii z licznikiem” przeniesie Cię do jego głównego ekranu konfiguracji.

#### **Wyświetl licznik produktów**

- **Co robi to ustawienie:** Jest to główny przełącznik, który kontroluje, czy licznik produktów jest wyświetlany obok każdej nazwy kategorii w bloku.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Moduł pobierze i wyświetli liczbę aktywnych produktów dla każdej kategorii w bloku kategorii, np. „Elektronika (125)”. Jest to podstawowa funkcja modułu.
  - *Gdy wyłączone (NIE):* Moduł będzie zachowywał się jak standardowy blok kategorii, wyświetlając tylko nazwy kategorii bez liczników produktów. Moduł nadal będzie wyświetlał drzewo kategorii, ale unikalna funkcja licznika będzie nieaktywna.
- **Zalecana wartość:** **TAK**. Aby wykorzystać główną korzyść modułu, należy włączyć to ustawienie.
- **Scenariusz/przykład dla sprzedawcy:** Jeśli chcesz, aby Twoi klienci szybko widzieli, które kategorie są popularne lub dobrze zaopatrzone, włącz to ustawienie. Jeśli wolisz minimalistyczną listę kategorii bez liczb, możesz je wyłączyć, choć to zniweczyłoby cel instalacji tego konkretnego modułu.

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Główna konfiguracja | Wyświetl licznik produktów | TAK | Kontroluje, czy licznik produktów jest wyświetlany obok nazw kategorii. Włączenie aktywuje podstawową funkcję modułu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Liczniki produktów nie wyświetlają się lub wydają się nieprawidłowe.**
O:

1.  **Sprawdź konfigurację modułu:** Przejdź do **Moduły > Menedżer modułów**, znajdź „Blok kategorii z licznikiem”, kliknij „Konfiguruj” i upewnij się, że „Wyświetl licznik produktów” jest ustawione na **TAK**.
2.  **Wyczyść pamięć podręczną PrestaShop:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami stare, buforowane treści uniemożliwiają natychmiastowe pojawienie się zmian.
3.  **Status produktu:** Upewnij się, że produkty, które mają być liczone, są „aktywne” i „dostępne do zamówienia” w ustawieniach produktu. Moduł liczy tylko aktywne, widoczne produkty.
4.  **Powiązanie kategorii:** Sprawdź dokładnie, czy produkty są prawidłowo powiązane z odpowiednimi kategoriami.

**P: Blok kategorii wygląda dziwnie lub nie pasuje do mojego motywu.**
O: Moduł dziedziczy stylizację z aktywnego motywu PrestaShop.

1.  **Kompatybilność z motywem:** Chociaż moduł jest kompatybilny z wersjami PrestaShop, specyficzne projekty motywów mogą czasami powodować drobne wizualne niedopasowania.
2.  **Niestandardowy CSS:** Jeśli masz niestandardowy motyw lub specyficzne potrzeby stylizacyjne, może być konieczne dodanie niestandardowych reguł CSS do pliku `custom.css` motywu (lub równoważnego), aby dostosować wygląd bloku kategorii i licznika. Deweloper stron internetowych może Ci w tym pomóc.

**P: Czy mogę zmienić pozycję bloku kategorii?**
O: Tak, jest to standardowa funkcja PrestaShop.

1.  Przejdź do **Wygląd > Pozycje** (lub **Wygląd > Motyw i logo > Pozycje** w starszych wersjach).
2.  Wyszukaj zaczep, w którym moduł „Blok kategorii z licznikiem” jest aktualnie wyświetlany (np. `displayLeftColumn`, `displayRightColumn`).
3.  Możesz przeciągnąć i upuścić moduł, aby zmienić jego kolejność w ramach tego zaczepu, lub użyć przycisku „Przeszczep moduł”, aby przenieść go do zupełnie innego zaczepu.

**P: Czy ten moduł spowalnia mój sklep?**
O: Moduł został zaprojektowany tak, aby był wydajny. Odpytuje bazę danych o liczniki produktów, co jest standardową operacją. W przypadku bardzo dużych sklepów z dziesiątkami tysięcy produktów i kategorii, może wystąpić minimalny wpływ, ale dla większości sklepów powinien być on pomijalny. Upewnij się, że Twój serwer spełnia zalecane specyfikacje PrestaShop dla optymalnej wydajności.

**P: Jak przetłumaczyć moduł, jeśli mój sklep jest wielojęzyczny?**
O: Ten moduł wyświetla głównie nazwy kategorii i liczby, które są już obsługiwane przez podstawowy system tłumaczeń PrestaShop dla kategorii. Gdyby sam moduł miał jakieś specyficzne ciągi tekstowe (np. tytuł bloku), przetłumaczyłbyś je za pomocą **Lokalizacja > Tłumaczenia > Tłumaczenia modułów**. Jednak w przypadku tego konkretnego modułu większość treści jest dynamiczna z Twoich kategorii.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowe informacje na temat struktury technicznej modułu „Blok kategorii z licznikiem”, przeznaczone dla programistów, webmasterów i agencji technicznych.

### 4.1 Przegląd architektury

Moduł „Blok kategorii z licznikiem” to lekki, jednoplikowy moduł PrestaShop (`block-categories-with-counter.php`). Rozszerza on podstawową klasę `Module` i wykorzystuje głównie system zaczepów PrestaShop do integracji swojej funkcjonalności. Jego podstawowa logika polega na nadpisywaniu lub rozszerzaniu domyślnego zachowania bloku kategorii w celu wstrzyknięcia liczników produktów. Wykorzystuje on obiekty `Category` i `Product` z PrestaShop do pobierania danych.

### 4.2 Kontrolery (`controllers/`)

Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana bezpośrednio w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł **nie** wprowadza żadnych niestandardowych klas ani obiektów w katalogu `classes/`. Bezpośrednio wykorzystuje podstawowe obiekty `Category` i `Product` z PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript. Jego funkcjonalność jest renderowana wyłącznie po stronie serwera.

### 4.5 Arkusze stylów CSS (`views/css/`)

Ten moduł **nie** zawiera żadnych niestandardowych plików CSS. W całości opiera się na stylizacji dostarczonej przez aktywny motyw PrestaShop dla domyślnego bloku kategorii.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Ten moduł **nie** zawiera niestandardowych plików szablonów w `views/templates/`. Prawdopodobnie nadpisuje lub modyfikuje wyjście szablonu domyślnego modułu `blockcategories` lub bezpośrednio renderuje swoją zawartość w metodach `hook`. Biorąc pod uwagę jego prostotę, jest bardzo prawdopodobne, że używa metody `display` do bezpośredniego renderowania treści, lub może być zaprojektowany do zastępowania wyjścia domyślnego modułu `blockcategories` poprzez zaczepianie się w tych samych pozycjach i dostarczanie własnego kodu HTML.

### 4.7 Schemat bazy danych i mapa zaczepów

- **Tabele bazy danych**: Ten moduł **nie** tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoją konfigurację (konkretnie ustawienie `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT`) w standardowej tabeli `ps_configuration`.
- **Tabela zarejestrowanych zaczepów**:

| Nazwa zaczepu | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayLeftColumn` | Renderuje blok kategorii w lewej kolumnie. |
| `displayRightColumn` | Renderuje blok kategorii w prawej kolumnie. |
| `displayHome` | Renderuje blok kategorii na stronie głównej. |
| `displayFooter` | Renderuje blok kategorii w stopce. |
| `displayHeader` | Renderuje blok kategorii w nagłówku. |

Moduł dynamicznie generuje kod HTML dla drzewa kategorii i liczników produktów w ramach tych metod zaczepów, zazwyczaj używając funkcji rekurencyjnej do budowania zagnieżdżonej struktury listy.

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, oficjalne wsparcie i pobrać nowe wersje modułu „Blok kategorii z licznikiem”, odwiedź swoje konto klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
