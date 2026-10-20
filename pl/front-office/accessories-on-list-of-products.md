---
title: "Akcesoria na liście produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop „Akcesoria na liście produktów” od MyPresta.eu."
sidebar:
  label: "Akcesoria na liście produktów - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Accessories on list of products na MyPresta.eu](https://mypresta.eu/modules/front-office-features/accessories-on-list-of-products.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/accessories-on-list-of-products/)
>
> ---


# Akcesoria na liście produktów

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane przez sam PrestaShop i są wystarczające dla tego modułu.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Po instalacji kliknij przycisk „Konfiguruj” obok modułu „Akcesoria na liście produktów” w Menedżerze modułów. Spowoduje to przejście do głównego ekranu konfiguracji.

| Ustawienie / Opcja | Co robi to ustawienie | Efekt zmiany tego ustawienia | Zalecana wartość | Scenariusz/przykład dla sprzedawcy |
| --- | --- | --- | --- | --- |
| **Napraw błąd motywu classic** | To ustawienie rozwiązuje konkretny problem z wyświetlaniem, który może wystąpić w domyślnym motywie PrestaShop Classic lub motywach na nim opartych, gdzie akcesoria mogą nie renderować się poprawnie. | *Gdy włączone:* Moduł stosuje poprawkę, aby zapewnić prawidłowe wyświetlanie akcesoriów na listach produktów, zwłaszcza z motywem Classic. *Gdy wyłączone:* Poprawka nie jest stosowana. Jeśli używasz motywu Classic lub jego pochodnej, akcesoria mogą nie wyświetlać się poprawnie lub mogą mieć problemy z układem. | **TAK** (Jeśli używasz motywu Classic lub motywu na nim opartego) / **NIE** (Jeśli używasz całkowicie niestandardowego motywu i nie doświadczasz problemów) | Jeśli zainstalowałeś moduł, a akcesoria nie pojawiają się lub wyglądają na uszkodzone na stronach kategorii, włączenie tego ustawienia jest pierwszym krokiem do rozwiązania problemu, zwłaszcza jeśli używasz motywu Classic. Jeśli Twój motyw jest mocno dostosowany i nie wykazuje tego błędu, możesz pozostawić go wyłączonym, aby uniknąć potencjalnych konfliktów, chociaż zazwyczaj bezpiecznie jest go włączyć. |
| **Włączony / Wyłączony** | To jest główny przełącznik do aktywacji lub dezaktywacji funkcjonalności modułu w całym Twoim sklepie. | *Gdy włączone:* Moduł będzie aktywnie wyświetlał akcesoria na stronach z listą produktów, zgodnie z opisem. *Gdy wyłączone:* Funkcjonalność modułu jest całkowicie wyłączona, a żadne akcesoria nie pojawią się na listach produktów. | **Włączony** | Zakończyłeś konfigurację akcesoriów dla produktów i chcesz, aby pojawiły się w Twoim sklepie. Włączyłbyś to. Jeśli musisz tymczasowo ukryć akcesoria w celu konserwacji lub specjalnej kampanii, wyłączyłbyś to. |

### 2.2 Tabela szybkiego odniesienia konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | Napraw błąd motywu classic | TAK (dla użytkowników motywu Classic) | Rozwiązuje problemy z wyświetlaniem akcesoriów na listach produktów z motywem Classic. |
| Strona konfiguracji modułu | Włączony / Wyłączony | Włączony | Włącza lub wyłącza podstawową funkcjonalność modułu. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Akcesoria nie wyświetlają się na moich stronach z listą produktów.**
O:

1. **Sprawdź status modułu**: Upewnij się, że moduł jest „Włączony” w jego konfiguracji.
2. **Sprawdź przypisanie akcesoriów**: Zweryfikuj, czy główne produkty faktycznie mają przypisane akcesoria na stronie edycji produktu PrestaShop (w zakładce „Akcesoria”).
3. **Kompatybilność z motywem**: Jeśli używasz niestandardowego motywu, może on nadpisywać standardowy szablon listy produktów w sposób, który uniemożliwia poprawne podłączenie modułu. Spróbuj włączyć ustawienie „Napraw błąd motywu classic”, nawet jeśli nie używasz motywu Classic, ponieważ może to rozwiązać niektóre ogólne problemy z wyświetlaniem.
4. **Wyczyść pamięć podręczną**: Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach). Czasami pamięć podręczna PrestaShop wymaga odświeżenia, aby odzwierciedlić nowe zmiany modułu.

**P: Akcesoria wyglądają dziwnie lub są źle wyrównane w moim sklepie.**
O:

1. **„Napraw błąd motywu classic”**: Spróbuj włączyć to ustawienie w konfiguracji modułu. Specjalnie rozwiązuje problemy z układem.
2. **Konflikt CSS motywu**: CSS Twojego motywu może kolidować ze stylami modułu. Często wymaga to od webmastera lub programisty sprawdzenia CSS i wprowadzenia poprawek.
3. **Wyczyść pamięć podręczną**: Zawsze wyczyść pamięć podręczną PrestaShop po wprowadzeniu zmian w konfiguracji.

**P: Czy mogę kontrolować, które akcesoria pojawiają się dla konkretnych produktów?**
O: Tak, moduł wykorzystuje natywną funkcję przypisywania akcesoriów PrestaShop. Aby dodać lub usunąć akcesoria dla produktu, przejdź do **Katalog > Produkty**, edytuj żądany produkt i przejdź do zakładki „Akcesoria”. Tutaj możesz wyszukać i dodać/usunąć powiązane produkty.

**P: Czy ten moduł spowalnia mój sklep?**
O: Moduł został zaprojektowany tak, aby był wydajny. Wykorzystuje istniejące dane akcesoriów PrestaShop. Jednak jeśli masz tysiące produktów, z których każdy ma dziesiątki akcesoriów, a zasoby Twojego serwera są ograniczone, każde dodatkowe ładowanie danych może mieć niewielki wpływ. Dla większości sklepów wpływ na wydajność jest znikomy.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Akcesoria na liście produktów” (`accol`) to standardowy moduł PrestaShop, skupiający się głównie na wyświetlaniu w front-office. Rozszerza `Module` i wykorzystuje system hooków PrestaShop do wstrzykiwania danych akcesoriów i renderowania do istniejących szablonów list produktów. Nie wprowadza nowych tabel baz danych ani złożonych niestandardowych kontrolerów, co czyni go lekkim i skoncentrowanym na celu wyświetlania. Logika modułu jest zawarta w jego głównym pliku PHP, z powiązanymi plikami JS i CSS do stylizacji i interakcji.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Moduł wstrzykuje swoją zawartość bezpośrednio do istniejących szablonów list produktów za pomocą hooków.
- **Kontrolery Back-Office Admin**: Brak. Konfiguracja jest obsługiwana bezpośrednio za pomocą metody `getContent()` w głównym pliku modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

- Moduł nie definiuje żadnych niestandardowych klas w katalogu `classes/`. Cała podstawowa logika znajduje się w głównym pliku modułu `accol.php`.
- Współpracuje ze standardowymi metodami PrestaShop `Product` i `Product::getAccessories()` w celu pobierania danych akcesoriów.

### 4.4 Zasoby JavaScript (`views/js/`)

- **`accol/js/accol.js`**
  - **Zakres**: Front-office.
  - **Cel**: Ten skrypt jest odpowiedzialny za obsługę dynamicznego wyświetlania i potencjalnych interakcji z listami akcesoriów. Może zawierać logikę dla responsywnych karuzel (jeśli zaimplementowane), pokazywania/ukrywania bloków akcesoriów lub wywołań AJAX do dodawania akcesoriów do koszyka (chociaż główną funkcją modułu jest wyświetlanie, a nie bezpośrednie dodawanie do koszyka za pomocą AJAX). Prawdopodobnie jest ładowany za pomocą hooka `displayHeader` lub `header`.
  - **Szczegóły**: Może wiązać słuchaczy zdarzeń z elementami akcesoriów, zarządzać ich widocznością lub inicjalizować wszelkie biblioteki stron trzecich używane do karuzel lub sliderów, jeśli moduł implementuje takie funkcje do wyświetlania akcesoriów.

### 4.5 Arkusze stylów CSS (`views/css/`)

- **`accol/css/accol.css`**
  - **Zakres**: Stylizacja front-office dla klienta.
  - **Cel**: Ten arkusz stylów zapewnia niezbędną stylizację wizualną dla list akcesoriów wyświetlanych na stronach produktów.
  - **Główne komponenty i kontenery interfejsu użytkownika**: Stylizuje kontener dla akcesoriów, pojedyncze elementy akcesoriów (obrazy, nazwy, ceny) i potencjalnie wszelkie elementy nawigacyjne (takie jak strzałki dla karuzel).
  - **Kluczowe selektory klas CSS**: Programiści mogą spodziewać się selektorów takich jak `.accol-accessories-list`, `.accol-accessory-item`, `.accol-accessory-image`, `.accol-accessory-name` itp., które można nadpisać w pliku `custom.css` lub `theme.css` niestandardowego motywu, aby dopasować je do estetyki motywu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony hooków (`views/templates/hook/`)**:
  - `accol/accol.tpl`: To jest główny szablon front-office odpowiedzialny za renderowanie listy akcesoriów dla danego produktu. Prawdopodobnie jest podłączony do `displayProductListReviews` lub podobnego hooka, który pozwala na wstrzykiwanie treści do pętli elementów listy produktów. Otrzymuje tablicę produktów akcesoriów i iteruje przez nie, aby wyświetlić ich obrazy, nazwy i potencjalnie ceny.
- **Szablony administracyjne (`views/templates/admin/`)**:
  - `accol/admin.tpl`: Ten szablon jest używany do strony konfiguracji modułu w Panelu administracyjnym PrestaShop. Zawiera elementy formularza HTML dla ustawień „Napraw błąd motywu classic” i „Włączony/Wyłączony”, wraz z wszelkimi komunikatami informacyjnymi lub przyciskami zapisu.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele baz danych**: Moduł nie tworzy żadnych niestandardowych tabel baz danych. Opiera się na natywnej tabeli PrestaShop `ps_product_accessory` (która łączy produkty z ich akcesoriami) i `ps_configuration` dla własnych ustawień (`ACCOL_FIX`).
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony front-office. | Służy do ładowania zasobów CSS (`accol.css`) i JavaScript (`accol.js`) dla wyświetlania w front-office. |
| `displayProductListReviews` | W pętli elementów listy produktów, zazwyczaj poniżej głównych informacji o produkcie. | Główny hook używany do wstrzykiwania szablonu `accol.tpl`, renderującego akcesoria dla każdego produktu na liście. Ten hook jest często dostępny w `product-list.tpl` lub podobnych szablonach. |
| `header` | (Alias dla `displayHeader` w wielu kontekstach, zwłaszcza w starszych wersjach PrestaShop). | Ten sam cel co `displayHeader` – ładowanie zasobów. |
| `actionFrontControllerSetMedia` | Wykonywany, gdy kontroler front-office ustawia swoje zasoby mediów. | Może być używany do warunkowego dodawania CSS/JS w oparciu o bieżący kontekst strony, zapewniając ładowanie zasobów tylko wtedy, gdy są potrzebne. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Akcesoria na liście produktów”, zapoznaj się ze swoim kontem klienta na MyPresta.eu. Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności i kompatybilności modułu.
