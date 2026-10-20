---
title: "Wyróżnione produkty - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Wyróżnione produkty od MyPresta.eu."
sidebar:
  label: "Wyróżnione produkty - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Featured Products na MyPresta.eu](https://mypresta.eu/modules/front-office-features/featured-products.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/featured-products/)
>
> ---


# Wyróżnione produkty

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wystarczające. Nie są wymagane żadne specjalne konfiguracje serwera.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Aby uzyskać dostęp do konfiguracji, przejdź do **Moduły > Menedżer modułów**, wyszukaj „Wyróżnione produkty” i kliknij „Konfiguruj”.

Ten ekran pozwala zdefiniować, które produkty są wyświetlane i jak pojawiają się na Twojej stronie głównej.

#### Ustawienia i opcje:

1. **ID kategorii źródłowej**

   - **Co robi to ustawienie:** Jest to najważniejsze ustawienie. Określa, *które* produkty z kategorii będą wyświetlane jako „wyróżnione” na Twojej stronie głównej. Musisz wprowadzić numeryczne ID kategorii, którą chcesz zaprezentować.
   - **Efekt zmiany tego ustawienia:**
     - *Po ustawieniu na prawidłowe ID kategorii (np. `3` dla „Ubrań”):* Moduł pobierze i wyświetli produkty należące do kategorii o tym ID.
     - *Po ustawieniu na nieprawidłowe lub nieistniejące ID:* Nie zostaną wyświetlone żadne produkty, lub może wystąpić błąd, jeśli ID jest źle sformułowane.
   - **Zalecana wartość:** ID kategorii, którą chcesz promować.
   - **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz wyróżnić kategorię „Nowości” (która ma ID, powiedzmy, `12`), wprowadź tutaj `12`. Aby znaleźć ID kategorii, przejdź do **Katalog > Kategorie** w Panelu administracyjnym, kliknij „Edytuj” przy kategorii i spójrz na adres URL w przeglądarce (np. `id_category=12`).
2. **Liczba produktów**

   - **Co robi to ustawienie:** Kontroluje, ile produktów z wybranej „Kategorii źródłowej” zostanie wyświetlonych na stronie głównej.
   - **Efekt zmiany tego ustawienia:**
     - *Po ustawieniu na `5`:* Zostanie wyświetlonych tylko pierwszych 5 produktów z wybranej kategorii.
     - *Po ustawieniu na `10`:* Zostanie wyświetlonych do 10 produktów.
   - **Zalecana wartość:** Rozsądna liczba, taka jak `8` lub `12`, aby uniknąć przeciążenia strony głównej, ale wystarczająca do zaprezentowania różnorodności. Weź pod uwagę układ swojego szablonu.
   - **Scenariusz / przykład dla sprzedawcy:** Jeśli Twoja kategoria „Nowości” ma 50 produktów, ale chcesz wyświetlić tylko najnowsze 8 na stronie głównej, ustaw to na `8`.
3. **Pozycja umieszczenia**

   - **Co robi to ustawienie:** Określa, *jak* wyróżnione produkty są wyświetlane na Twojej stronie głównej: bezpośrednio w głównym obszarze zawartości (`displayHome`) lub w zakładce (`displayHomeTabContent`).
   - **Efekt zmiany tego ustawienia:**
     - *Po ustawieniu na `Zakładka na stronie głównej`:* Produkty pojawią się pod nową zakładką na Twojej stronie głównej (np. „Wyróżnione produkty”). Wymaga to, aby Twój szablon obsługiwał zakładki na stronie głównej.
     - *Po ustawieniu na `Strona główna`:* Produkty zostaną wyświetlone jako samodzielna sekcja bezpośrednio na Twojej stronie głównej, bez ukrywania za zakładką.
   - **Zalecana wartość:**
     - Wybierz `Zakładka na stronie głównej`, jeśli Twój szablon używa zakładek do list produktów (jak często robią to domyślne szablony PrestaShop) i chcesz zachować porządek na stronie głównej.
     - Wybierz `Strona główna`, jeśli chcesz maksymalnej widoczności dla tych produktów, a Twój szablon ma wystarczająco dużo miejsca w głównym obszarze zawartości.
   - **Scenariusz / przykład dla sprzedawcy:** Jeśli prowadzisz specjalną promocję i chcesz, aby produkty były natychmiast widoczne bez konieczności klikania zakładki przez klientów, wybierz `Strona główna`. Jeśli masz wiele typów produktów prezentowanych na stronie głównej i chcesz je schludnie uporządkować, `Zakładka na stronie głównej` jest lepszym wyborem.

#### Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | ID kategorii źródłowej | (ID Twojej kategorii) | Określa, które produkty z kategorii są wyświetlane. |
| Konfiguracja modułu | Liczba produktów | 8-12 | Ogranicza liczbę wyświetlanych produktów z wybranej kategorii. |
| Konfiguracja modułu | Pozycja umieszczenia | Zakładka na stronie głównej / Strona główna | Określa, czy produkty pojawiają się w zakładce, czy bezpośrednio na stronie głównej. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje wyróżnione produkty nie pojawiają się na stronie głównej.**
O:

1. **Sprawdź „ID kategorii źródłowej”:** Upewnij się, że wprowadziłeś prawidłowe, istniejące ID kategorii. Przejdź do **Katalog > Kategorie**, edytuj żądaną kategorię i znajdź jej ID w adresie URL przeglądarki (np. `id_category=X`).
2. **Sprawdź „Liczbę produktów”:** Upewnij się, że jest ustawiona na wartość większą niż 0.
3. **Sprawdź „Pozycję umieszczenia”:** Jeśli ustawiono na „Zakładka na stronie głównej”, upewnij się, że Twój szablon faktycznie obsługuje i wyświetla zakładki na stronie głównej. Niektóre niestandardowe szablony mogą tego nie robić. Spróbuj przełączyć na „Strona główna”, aby sprawdzić, czy pojawiają się jako bezpośrednia sekcja.
4. **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną”. Czasami pamięć podręczna PrestaShop uniemożliwia natychmiastowe pojawienie się zmian.

**P: Produkty się wyświetlają, ale wyglądają na źle wyrównane lub mają nieprawidłowe style.**
O: Jest to zazwyczaj problem związany z szablonem.

1. **Kompatybilność z szablonem:** Chociaż moduł jest kompatybilny z wersjami PrestaShop, jego wizualny wygląd może kolidować z mocno dostosowanymi szablonami.
2. **Konflikt CSS:** CSS Twojego szablonu może nadpisywać lub kolidować z domyślnym stylem modułu. Może być konieczne, aby programista internetowy sprawdził CSS i zastosował niestandardowe style do `featuredcategory.css` lub niestandardowego pliku CSS Twojego szablonu.

**P: Czy mogę wyróżnić produkty z wielu kategorii?**
O: Nie bezpośrednio za pomocą tego modułu. Moduł „Wyróżnione produkty” jest zaprojektowany do wyświetlania produktów z *jednej* wybranej kategorii naraz. Jeśli musisz wyróżnić produkty z wielu kategorii jednocześnie, musisz albo:
a) Utworzyć nową kategorię „Główne wyróżnione” i dodać do niej produkty z różnych kategorii.
b) Zainstalować wiele instancji tego modułu (jeśli Twój szablon na to pozwala) lub użyć innego modułu zaprojektowanego do wyświetlania wielu kategorii.

**P: Jak przetłumaczyć tytuł zakładki „Wyróżnione produkty”?**
O: Jeśli używasz umieszczenia „Zakładka na stronie głównej”, tytuł zakładki jest zazwyczaj generowany przez moduł.

1. Przejdź do **Lokalizacja > Tłumaczenia**.
2. Wybierz „Tłumaczenia zainstalowanych modułów”, swój szablon i swój język.
3. Wyszukaj moduł „Wyróżnione produkty”. Powinieneś znaleźć tam ciąg tekstowy dla tytułu zakładki i możesz go przetłumaczyć.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja jest przeznaczona wyłącznie dla programistów, webmasterów sklepów i agencji technicznych utrzymujących lub rozszerzających sklep.

### 4.1 Przegląd architektury

Moduł `Featured Products` to prosty moduł PrestaShop, zaprojektowany głównie do wyświetlania listy produktów z określonej kategorii na stronie głównej. Wykorzystuje system hooków PrestaShop (`displayHome`, `displayHomeTab`, `displayHomeTabContent`) do wstrzykiwania swojej zawartości. Logika modułu znajduje się w jego głównym pliku PHP, `featuredcategory.php`, który obsługuje konfigurację, instalację i renderowanie zawartości. Nie wprowadza niestandardowych kontrolerów, modeli ani złożonego JavaScriptu, co czyni go lekkim i łatwym w utrzymaniu rozwiązaniem.

### 4.2 Kontrolery (`controllers/`)

- **Kontrolery Front-Office**: Brak. Całe renderowanie zawartości front-office jest obsługiwane bezpośrednio za pomocą hooków w głównym pliku `featuredcategory.php` i powiązanych szablonach Smarty.
- **Kontrolery administracyjne Back-Office**: Brak. Konfiguracja modułu jest zarządzana za pomocą standardowej metody `getContent()` w głównym pliku modułu.

### 4.3 Klasy i modele rdzenia (`classes/`)

- W tym module nie ma niestandardowych klas ani definicji `ObjectModel`. Wszystkie pobieranie danych (produktów, kategorii) odbywa się za pomocą podstawowych klas PrestaShop `Product` i `Category`.

### 4.4 Zasoby JavaScript (`views/js/`)

- Z tym modułem nie są dołączone żadne niestandardowe pliki JavaScript.

### 4.5 Arkusze stylów CSS (`views/css/`)

- `featuredcategory/css/featuredcategory.css`
  - **Zakres:** Stylizacja front-office dla klienta.
  - **Główne komponenty interfejsu użytkownika i kontenery, które stylizuje:** Ten arkusz stylów zapewnia podstawową stylizację listy produktów generowanej przez moduł, zapewniając jej estetyczny wygląd w kontekście strony głównej. Prawdopodobnie celuje w ogólne kontenery list produktów i poszczególne elementy produktów.
  - **Kluczowe selektory klas CSS, które programiści mogą nadpisać w swoim szablonie:** Programiści mogą sprawdzić wyjście HTML modułu, aby zidentyfikować konkretne klasy (np. `.featuredcategory-products`, `.product-item`, `.product-name`) i nadpisać je w niestandardowym pliku CSS swojego szablonu, aby dopasować je do ogólnego projektu sklepu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

Moduł używa szablonów Smarty do renderowania swojej zawartości, głównie dla hooków strony głównej.

- **Szablony hooków (`views/templates/hook/`)**:
  - `featuredcategory/views/templates/hook/featuredcategory17-tabContents.tpl`
    - **Hook:** `displayHomeTabContent`
    - **Cel:** Ten szablon jest odpowiedzialny za renderowanie rzeczywistej listy wyróżnionych produktów, gdy „Pozycja umieszczenia” jest ustawiona na „Zakładka na stronie głównej”. Zazwyczaj zawiera pętlę do iteracji przez produkty i wyświetlania ich szczegółów (obraz, nazwa, cena, przycisk dodania do koszyka).
  - `featuredcategory/views/templates/hook/featuredcategory17.tpl`
    - **Hook:** `displayHome`
    - **Cel:** Ten szablon renderuje listę wyróżnionych produktów, gdy „Pozycja umieszczenia” jest ustawiona na „Strona główna” (tj. nie w zakładce). Wygeneruje tę samą strukturę listy produktów co `featuredcategory17-tabContents.tpl`, ale bezpośrednio do głównego hooka `displayHome`.
  - `featuredcategory/views/templates/hook/tab.tpl`
    - **Hook:** `displayHomeTab`
    - **Cel:** Ten szablon renderuje rzeczywisty tytuł zakładki (np. „Wyróżnione produkty”), który pojawia się na stronie głównej, gdy „Pozycja umieszczenia” jest ustawiona na „Zakładka na stronie głównej”. Zapewnia klikalny element, który ujawnia zawartość z `featuredcategory17-tabContents.tpl`.
- **Szablony administracyjne (`views/templates/admin/`)**: Brak.
- **Szablony front-office (`views/templates/front/`)**: Brak.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**: Ten moduł nie tworzy żadnych niestandardowych tabel bazy danych. Przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` PrestaShop.

  - Wpisy `ps_configuration`:
    - `CFEATURED_NBR`: Przechowuje ustawienie „Liczba produktów”.
    - `CFEATURED_ID`: Przechowuje ustawienie „ID kategorii źródłowej”.
    - `CFEATURED_WHERE`: Przechowuje ustawienie „Pozycja umieszczenia” (np. 'tab' lub 'home').
    - `mypresta_updates`: Używane do sprawdzania aktualizacji modułu przez MyPresta.eu.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHomeTab` | Renderuje zawartość dla nowej zakładki na stronie głównej. | Wyświetla HTML dla tytułu zakładki „Wyróżnione produkty”. |
| `displayHomeTabContent` | Renderuje zawartość dla wybranej zakładki na stronie głównej. | Wyświetla HTML dla listy wyróżnionych produktów, gdy zakładka jest aktywna. |
| `displayHome` | Renderuje zawartość bezpośrednio w głównym obszarze strony głównej. | Wyświetla HTML dla listy wyróżnionych produktów, gdy nie używa się zakładek. |
| `displayHeader` | Wykonywany w sekcji `<head>` każdej strony. | Używany do dołączenia arkusza stylów CSS modułu (`featuredcategory.css`) do wyświetlania w front-office. |
| `actionProductDelete` | Wyzwalany po usunięciu produktu. | Potencjalnie używany do czyszczenia pamięci podręcznej lub ponownej oceny wyróżnionych produktów, jeśli usunięty produkt znajdował się w wyróżnionej kategorii. |
| `actionProductUpdate` | Wyzwalany po aktualizacji produktu. | Potencjalnie używany do czyszczenia pamięci podręcznej lub ponownej oceny wyróżnionych produktów, jeśli zaktualizowany produkt znajduje się w wyróżnionej kategorii. |
| `actionProductAdd` | Wyzwalany po dodaniu nowego produktu. | Potencjalnie używany do czyszczenia pamięci podręcznej lub ponownej oceny wyróżnionych produktów, jeśli nowy produkt znajduje się w wyróżnionej kategorii. |
| `actionCategoryUpdate` | Wyzwalany po aktualizacji kategorii. | Potencjalnie używany do czyszczenia pamięci podręcznej lub ponownej oceny wyróżnionych produktów, jeśli sama wyróżniona kategoria zostanie zaktualizowana. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje modułu, poprawki błędów i oficjalne wsparcie, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących modułu „Wyróżnione produkty”.
