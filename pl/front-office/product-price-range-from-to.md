---
title: "Zakres cen produktu - od / do - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Zakres cen produktu - od / do” firmy MyPresta.eu."
sidebar:
  label: "Zakres cen produktu - od / do - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Product price range - from / to na MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-price-range-from-to.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/product-price-range-from-to/)
>
> ---


# Zakres cen produktu - od / do

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające dla modułów PrestaShop. Brak specjalnych wymagań hostingowych poza standardowym środowiskiem kompatybilnym z PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po zainstalowaniu modułu przejdź do **Moduły > Menedżer modułów** i kliknij „Konfiguruj” obok „Zakres cen produktu - od / do”. Zostanie wyświetlony główny ekran konfiguracji.

#### Ustawienia ogólne

Ta sekcja kontroluje podstawowe zachowanie modułu.

- **Wyświetl zakres cen na liście produktów:**

  - **Co robi to ustawienie:** Ten przełącznik określa, czy zakres „od [najniższa cena] do [najwyższa cena]” jest wyświetlany na stronach, które zawierają listy wielu produktów, takich jak strony kategorii, wyniki wyszukiwania lub moduły takie jak „Nowe produkty” lub „Polecane produkty”.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (TAK):* Produkty z kombinacjami i różnymi cenami będą wyświetlać zakres cen na wszystkich stronach z listami produktów.
    - *Gdy wyłączone (NIE):* Na stronach z listami produktów będzie wyświetlana tylko jedna cena (zazwyczaj cena bazowa lub najniższa cena kombinacji), zgodnie z domyślnym zachowaniem PrestaShop.
  - **Zalecana wartość:** TAK
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz koszulki, które kosztują 10 € za małe i 15 € za duże, włączenie tej opcji spowoduje wyświetlenie „od 10,00 € do 15,00 €” na stronie kategorii koszulek, dając klientom szybki przegląd opcji cenowych.
- **Wyświetl zakres cen na stronie produktu:**

  - **Co robi to ustawienie:** Ten przełącznik kontroluje, czy zakres cen jest wyświetlany na samej stronie pojedynczego produktu, zazwyczaj w pobliżu głównej ceny produktu.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (TAK):* Strona produktu będzie wyświetlać zakres cen dla produktów z kombinacjami, informując klienta o wariantach cenowych, zanim wybierze opcje.
    - *Gdy wyłączone (NIE):* Strona produktu będzie wyświetlać tylko jedną cenę (zazwyczaj cena bazowa lub najniższa cena kombinacji), zgodnie z domyślnym zachowaniem PrestaShop.
  - **Zalecana wartość:** TAK
  - **Scenariusz / przykład dla sprzedawcy:** Na stronie produktu dla niestandardowego komputera, włączenie tej opcji spowoduje wyświetlenie „od 800,00 € do 2500,00 €” zanim klient zacznie wybierać opcje procesora, pamięci RAM i pamięci masowej, ustalając jasne oczekiwania.
- **Uwzględnij rabaty ilościowe:**

  - **Co robi to ustawienie:** To kluczowe ustawienie określa, czy moduł powinien uwzględniać wszelkie obniżki cen oparte na ilości (konkretne ceny dla ilości) podczas obliczania *najniższej* ceny w zakresie.
  - **Efekt zmiany tego ustawienia:**
    - *Gdy włączone (TAK):* Moduł obliczy absolutnie najniższą możliwą cenę, włączając wszelkie rabaty ilościowe, dla części „od” zakresu. Na przykład, jeśli produkt kosztuje 10 €, ale 8 €, jeśli kupisz 10 sztuk, cena „od” wyniesie 8 €.
    - *Gdy wyłączone (NIE):* Rabaty ilościowe zostaną zignorowane, a cena „od” będzie oparta wyłącznie na najniższej cenie kombinacji bez uwzględniania oszczędności przy zakupach hurtowych.
  - **Zalecana wartość:** TAK (aby zapewnić wyświetlanie najbardziej atrakcyjnej i dokładnej najniższej ceny).
  - **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz długopisy po 1 € za sztukę, ale oferujesz je po 0,80 €, jeśli kupisz je w opakowaniach po 100 sztuk, włączenie tej opcji zapewni, że cena „od” na liście produktów będzie wynosić 0,80 €, co sprawi, że produkt będzie wydawał się jeszcze bardziej przystępny cenowo.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyświetl zakres cen na liście produktów | TAK | Pokazuje cenę „od/do” na stronach kategorii, wyszukiwania i list produktów. |
| Konfiguracja modułu | Wyświetl zakres cen na stronie produktu | TAK | Pokazuje cenę „od/do” na stronie szczegółów pojedynczego produktu. |
| Konfiguracja modułu | Uwzględnij rabaty ilościowe | TAK | Uwzględnia obniżki cen oparte na ilości podczas obliczania najniższej ceny w zakresie. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Zakres cen nie wyświetla się na moich stronach produktów/listach.**
O:

1. **Sprawdź konfigurację modułu:** Przejdź do **Moduły > Menedżer modułów > Zakres cen produktu - od / do > Konfiguruj**. Upewnij się, że opcje „Wyświetl zakres cen na liście produktów” i „Wyświetl zakres cen na stronie produktu” są ustawione na **TAK**.
2. **Wyczyść pamięć podręczną:** PrestaShop używa pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
3. **Kombinacje produktów:** Czy produkt faktycznie ma kombinacje z *różnymi* cenami? Jeśli wszystkie kombinacje mają tę samą cenę, moduł prawdopodobnie wyświetli pojedynczą cenę, ponieważ nie ma zakresu do pokazania.
4. **Kompatybilność z motywem:** Chociaż moduł jest zaprojektowany z myślą o szerokiej kompatybilności, bardzo mocno dostosowane motywy mogą wymagać drobnych korekt. Jeśli problem nadal występuje po sprawdzeniu powyższych punktów, skontaktuj się z pomocą techniczną MyPresta.eu.

**P2: Cena „od” nie wydaje się uwzględniać moich rabatów ilościowych.**
O:

1. **Sprawdź konfigurację modułu:** Przejdź do **Moduły > Menedżer modułów > Zakres cen produktu - od / do > Konfiguruj**. Upewnij się, że opcja „Uwzględnij rabaty ilościowe” jest ustawiona na **TAK**.
2. **Zweryfikuj rabaty ilościowe:** Sprawdź dokładnie, czy Twoje rabaty ilościowe (konkretne ceny) są poprawnie skonfigurowane dla produktu i jego kombinacji w panelu administracyjnym PrestaShop.
3. **Wyczyść pamięć podręczną:** Zawsze wyczyść pamięć podręczną PrestaShop po wprowadzeniu zmian w konfiguracji.

**P3: Zakres cen wygląda trochę dziwnie lub jest źle wyrównany z projektem mojego motywu.**
O:
Moduł stara się integrować płynnie, ale każdy motyw jest unikalny.

1. **Wyczyść pamięć podręczną:** Czasami problemy ze stylami wynikają ze starych plików pamięci podręcznej.
2. **Niestandardowy CSS:** Może być konieczne dodanie niestandardowego kodu CSS do motywu, aby dostosować wygląd. Klasy CSS modułu są zazwyczaj dobrze zdefiniowane (patrz sekcja 7.5). Webmaster może pomóc Ci w celowaniu w te klasy, aby dopasować je do Twojego motywu.
3. **Skontaktuj się z pomocą techniczną:** Jeśli nie czujesz się komfortowo z CSS, pomoc techniczna MyPresta.eu często może udzielić wskazówek lub małych fragmentów CSS, aby pomóc.

**P4: Czy ten moduł spowolni mój sklep?**
O:
Moduł jest zoptymalizowany pod kątem wydajności. Efektywnie oblicza ceny. Chociaż każdy moduł dodaje niewielki narzut, ten jest zaprojektowany tak, aby był lekki. Jeśli zauważysz znaczne spowolnienia, upewnij się, że Twój serwer spełnia zalecane specyfikacje PrestaShop i że inne moduły nie powodują konfliktów. Regularne czyszczenie pamięci podręcznej również pomaga.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera szczegółowy przegląd techniczny dla programistów i webmasterów.

### 4.1 Przegląd architektury

Moduł „Zakres cen produktu - od / do” (`prange`) to standardowy moduł PrestaShop zgodny z wzorcem MVC. Działa głównie poprzez zaczepianie się w różnych punktach wyświetlania (`displayProductPriceBlock`, `displayProductListReviews` itp.) w celu wstrzyknięcia obliczonego zakresu cen. Główna logika znajduje się w pliku `index.php`, który działa jako punkt wejścia modułu i obsługuje konfigurację, instalację i rejestrację zaczepów. Wykorzystuje klasy PrestaShop `Product` i `SpecificPrice` do obliczania zakresu cen, w tym rabatów ilościowych.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje niestandardowych kontrolerów front-office ani back-office. Cała logika jest hermetyzowana w głównej klasie modułu i wykonywana za pośrednictwem zaczepów.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Ten moduł nie definiuje niestandardowych klas ani nie rozszerza `ObjectModel`. Wszystkie niezbędne manipulacje danymi i obliczenia cen są wykonywane przy użyciu natywnych klas PrestaShop `Product` i `SpecificPrice` w głównym pliku modułu.

### 4.4 Zasoby JavaScript (`views/js/`)

- **`prange/views/js/prange-hide-p.js`**
  - **Zakres:** Front-office (strona produktu)
  - **Cel:** Ten skrypt prawdopodobnie zawiera logikę do ukrywania lub modyfikowania domyślnego wyświetlania ceny produktu na stronie pojedynczego produktu, gdy aktywny jest zakres cen modułu. Może nasłuchiwać zmian w DOM lub zdarzeń ładowania strony, aby upewnić się, że zakres modułu jest główną wyświetlaną ceną.
- **`prange/views/js/prange-hide-pl.js`**
  - **Zakres:** Front-office (strony z listami produktów)
  - **Cel:** Podobnie jak `prange-hide-p.js`, ale specjalnie dla stron z listami produktów (kategorie, wyniki wyszukiwania). Jest zaprojektowany do ukrywania lub dostosowywania domyślnego wyświetlania pojedynczej ceny na tych stronach, aby zrobić miejsce dla zakresu cen modułu.
- **`prange/views/js/prange.js`**
  - **Zakres:** Front-office
  - **Cel:** Jest to prawdopodobnie główny plik JavaScript dla modułu. Może zawierać:
    - Logikę do dynamicznego aktualizowania zakresu cen, jeśli atrybuty produktu są zmieniane za pomocą AJAX (np. wybieranie kombinacji).
    - Nasłuchiwacze zdarzeń dla zdarzeń `prestashop.on` związanych z aktualizacjami danych produktu.
    - Wszelkie renderowanie po stronie klienta lub manipulacje wymagane do wyświetlania zakresu cen.

### 4.5 Arkusze stylów CSS (`views/css/`)

- **`prange/views/css/prange.css`**
  - **Zakres:** Stylizacja front-office dla klienta.
  - **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Ten arkusz stylów zapewnia domyślną prezentację wizualną tekstu zakresu cen. Zdefiniuje style dla kontenera zawierającego tekst „od/do”, rozmiary czcionek, kolory, marginesy i potencjalnie responsywne dostosowania.
  - **Kluczowe selektory klas CSS, które programiści mogą nadpisać:** Programiści powinni sprawdzić renderowany kod HTML, aby zidentyfikować konkretne klasy (np. `.prange-price-range`, `.prange-from`, `.prange-to`) używane przez moduł. Można je następnie docelowo użyć w pliku `custom.css` lub `theme.css` niestandardowego motywu, aby dostosować wygląd.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony zaczepów (`views/templates/hook/`)**: Ten moduł nie definiuje jawnie szablonów w podkatalogu `hook/` na podstawie dostarczonego spisu, ale szablony wymienione poniżej są efektywnie renderowane za pośrednictwem zaczepów.
- **Szablony administracyjne (`views/templates/admin/`)**: Ten moduł nie ma niestandardowych szablonów administracyjnych poza standardowym formularzem `getContent()`.
- **Szablony front-office (`views/templates/front/`)**:
  - **`prange/views/templates/prange-oneprice.tpl`**
    - **Cel:** Ten szablon jest prawdopodobnie używany, gdy produkt *nie* ma kombinacji z różnymi cenami lub gdy moduł ustali, że należy wyświetlić tylko jedną cenę (np. jeśli ceny „od” i „do” są identyczne). Zapewnia spójne formatowanie nawet dla produktów z jedną ceną, jeśli moduł jest aktywny.
    - **Renderowany za pośrednictwem:** Prawdopodobnie zaczepiony w `displayProductPriceBlock` lub podobnym.
  - **`prange/views/templates/prange.tpl`**
    - **Cel:** Jest to główny szablon do wyświetlania rzeczywistego zakresu „od [najniższa cena] do [najwyższa cena]”. Otrzymuje obliczone najniższe i najwyższe ceny z logiki PHP modułu i formatuje je do wyświetlenia.
    - **Renderowany za pośrednictwem:** Ten szablon zostanie wyrenderowany, gdy moduł zaczepi się w `displayProductPriceBlock` (dla strony produktu) i potencjalnie w innych zaczepach dla stron z listami produktów (np. `displayProductListReviews`, `displayProductPriceBlock` w kontekście listy produktów lub poprzez nadpisanie szablonów rdzeniowych).

### 4.7 Schemat bazy danych i mapa zaczepów

- **Tabele bazy danych**:

  - Ten moduł nie tworzy niestandardowych tabel SQL.
  - Przechowuje swoje ustawienia konfiguracyjne (np. `PRANGE_DISPLAY_LIST`, `PRANGE_DISPLAY_PRODUCT`, `PRANGE_QUANTITY_DISCOUNT`) w standardowej tabeli `ps_configuration`.
- **Tabela zarejestrowanych zaczepów**:

| Nazwa zaczepu | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Służy do dołączania plików CSS (`prange.css`) i JavaScript (`prange.js`, `prange-hide-p.js`, `prange-hide-pl.js`) modułu w celu stylizacji i funkcjonalności front-office. |
| `displayProductPriceBlock` | Renderuje zawartość w bloku ceny produktu na stronach produktów i potencjalnie na listach produktów. | Jest to główny zaczep do wstrzykiwania obliczonego zakresu cen do wyświetlania ceny produktu. Moduł prawdopodobnie sprawdza parametr `type` tego zaczepu, aby określić kontekst (strona produktu vs. lista). |
| `displayProductListReviews` | Renderuje zawartość w pobliżu recenzji produktów na stronach z listami produktów. | Chociaż nazwany dla recenzji, ten zaczep jest często używany przez moduły do wstrzykiwania dodatkowych informacji (takich jak zakresy cen) do elementów listy produktów. |
| `displayProductExtraContent` | Renderuje dodatkowe bloki treści na stronie produktu. | Może być używany jako alternatywna lub uzupełniająca lokalizacja dla zakresu cen na stronie produktu. |
| `displayAfterProductThumbs` | Renderuje zawartość po miniaturach produktów na stronie produktu. | Kolejna potencjalna lokalizacja do wyświetlania zakresu cen na stronie produktu. |
| `displayProductButtons` | Renderuje zawartość w pobliżu przycisków akcji produktu (np. Dodaj do koszyka). | Mniej prawdopodobne dla zakresu cen, ale możliwe dla informacji kontekstowych. |
| `displayFooterProduct` | Renderuje zawartość w sekcji stopki strony produktu. | Awaryjna lub alternatywna lokalizacja dla zakresu cen na stronie produktu. |
| `displayProductAdditionalInfo` | Renderuje dodatkowe informacje na stronie produktu. | Częsty zaczep do wstrzykiwania niestandardowych szczegółów produktu. |
| `displayProductPrice` | Renderuje samą cenę produktu. | Ten zaczep jest często nadpisywany lub rozszerzany przez moduły, które modyfikują wyświetlanie ceny. |
| `actionProductUpdate` | Wykonywany po aktualizacji produktu w panelu administracyjnym. | Może być używany do czyszczenia pamięci podręcznej specyficznej dla modułu lub ponownego indeksowania zakresów cen, jeśli moduł utrzymywał własną pamięć podręczną. |
| `actionProductAdd` | Wykonywany po dodaniu nowego produktu. | Podobnie jak `actionProductUpdate`. |
| `actionProductDelete` | Wykonywany po usunięciu produktu. | Podobnie jak `actionProductUpdate`. |

*Uwaga: Dokładne używane zaczepy mogą się nieznacznie różnić między wersjami modułu i wersjami PrestaShop. Powyższa lista przedstawia typowe zaczepy dla funkcjonalności tego modułu na podstawie jego opisu.*

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, poprawek błędów i dedykowanego wsparcia dla programistów modułu „Zakres cen produktu - od / do”, prosimy zapoznać się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Upewnij się, że używasz najnowszej wersji modułu, aby zapewnić optymalną wydajność i kompatybilność ze swoim sklepem PrestaShop.
