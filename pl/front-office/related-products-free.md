---
title: "Related Products Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz odniesienie dla programistów dla modułu PrestaShop Related Products Free od MyPresta.eu."
sidebar:
  label: "Related Products Free - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Related Products Free na MyPresta.eu](https://mypresta.eu/modules/front-office-features/related-products-free.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/related-products-free/)
>
> ---


# Related Products Free

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 7.1 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL), które są zazwyczaj dostępne w większości środowisk hostingowych kompatybilnych z PrestaShop.

## 2. Kompletny przewodnik konfiguracji (każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj > Related Products Free)

To jest główny i jedyny ekran konfiguracji modułu „Related Products Free”. Tutaj zdefiniujesz, jak zachowuje się blok powiązanych produktów i jakie produkty wyświetla.

#### **Wyświetl powiązane produkty z kategorii**

- **Co robi to ustawienie:** To kluczowe ustawienie określa, *które* produkty będą wyświetlane jako „powiązane”. Zamiast ręcznie wybierać produkty dla każdego elementu, ten moduł upraszcza sprawę, pozwalając wybrać konkretną kategorię. Wszystkie produkty należące do tej wybranej kategorii będą następnie wyświetlane jako powiązane produkty na *każdej* stronie produktu w Twoim sklepie.
- **Efekt zmiany tego ustawienia:**
  - *Gdy kategoria jest wybrana (np. „Akcesoria”):* Na każdej stronie produktu w Twoim sklepie pojawi się blok pokazujący produkty należące do kategorii „Akcesoria”.
  - *Gdy wybrano „Brak” lub nie wybrano żadnej kategorii:* Moduł nie wyświetli żadnych powiązanych produktów, ponieważ nie wie, które produkty ma pokazać.
- **Zalecana wartość:** Wybierz kategorię, która zawiera ogólne, komplementarne lub najlepiej sprzedające się produkty, które mogą być istotne dla szerokiej gamy Twoich głównych produktów. Na przykład, jeśli sprzedajesz odzież, „Akcesoria” lub „Produkty na wyprzedaży” mogą być dobrymi wyborami.
- **Scenariusz / przykład dla sprzedawcy:** Sprzedajesz różne rodzaje elektroniki. Tworzysz kategorię o nazwie „Niezbędne akcesoria do gadżetów” i dodajesz do niej takie elementy jak uniwersalne ładowarki, ochraniacze ekranu i słuchawki. Wybierając tę kategorię tutaj, każda strona produktu (np. dla smartfona, laptopa lub tabletu) będzie wyświetlać te „Niezbędne akcesoria do gadżetów” jako powiązane produkty, zachęcając do sprzedaży krzyżowej.

#### **Liczba produktów do wyświetlenia**

- **Co robi to ustawienie:** Kontroluje, ile powiązanych produktów zostanie wyświetlonych w bloku na stronach produktów.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiono na ‘4’:* Moduł wyświetli cztery produkty z wybranej kategorii.
  - *Gdy ustawiono na ‘8’:* Moduł wyświetli osiem produktów.
- **Zalecana wartość:** 4 lub 5. Zbyt wiele produktów może przytłoczyć klienta lub sprawić, że strona będzie wyglądać na zagraconą, zwłaszcza na urządzeniach mobilnych. Mniejszy, starannie dobrany wybór jest często bardziej skuteczny.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz pokazać zwięzły wybór powiązanych produktów, nie wydłużając zbytnio strony produktu. Ustawienie tej wartości na ‘4’ zapewnia przejrzysty układ, jednocześnie oferując dobre możliwości sprzedaży krzyżowej.

#### **Wyświetlaj produkty tylko z wybranej kategorii**

- **Co robi to ustawienie:** To ustawienie określa, czy wyświetlane powiązane produkty pochodzą *tylko* z wybranej powyżej kategorii, czy też mogą również obejmować produkty z *własnej kategorii bieżącego produktu*.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Wyświetlane będą tylko produkty z kategorii wybranej w „Wyświetl powiązane produkty z kategorii”.
  - *Gdy wyłączone (NIE):* Moduł będzie wyświetlał produkty z wybranej kategorii *oraz* potencjalnie produkty z kategorii produktu, który klient aktualnie przegląda. Może to prowadzić do bardziej trafnych sugestii, jeśli kategoria bieżącego produktu również zawiera dobre produkty do sprzedaży krzyżowej.
- **Zalecana wartość:** „TAK”, jeśli wybrana kategoria „powiązanych produktów” jest bardzo ogólna (jak „Akcesoria”). „NIE”, jeśli chcesz mieszać bardziej specyficzne powiązane produkty z kategorii bieżącego produktu. Przetestuj obie opcje, aby zobaczyć, co działa najlepiej dla Twojego sklepu.
- **Scenariusz / przykład dla sprzedawcy:** Wybrałeś „Akcesoria” jako kategorię powiązanych produktów. Jeśli ustawisz to na „TAK”, wyświetlą się tylko akcesoria. Jeśli ustawisz to na „NIE”, a klient przegląda „T-shirt” (który znajduje się w kategorii „Topy”), moduł może wyświetlić zarówno „Akcesoria”, jak i inne „Topy” jako powiązane.

#### **Hook do wyświetlania powiązanych produktów**

- **Co robi to ustawienie:** Tutaj decydujesz, *gdzie* na stronie produktu pojawi się blok powiązanych produktów. PrestaShop używa „hooków” jako specyficznych punktów w kodzie strony, gdzie moduły mogą wstawiać swoją zawartość.
- **Efekt zmiany tego ustawienia:**
  - *Gdy ustawiono na `displayFooterProduct` (Zalecane):* Blok powiązanych produktów pojawi się na dole sekcji informacji o produkcie, zazwyczaj powyżej stopki całej strony. Jest to powszechne i skuteczne umiejscowienie.
  - *Gdy ustawiono na `displayProductExtraContent` (PrestaShop 1.7+):* Blok może pojawić się w zakładce lub w konkretnej sekcji głównej treści strony produktu, w zależności od Twojego szablonu.
  - *Inne hooki (np. `displayLeftColumnProduct`, `displayRightColumnProduct`):* Blok pojawi się w lewym lub prawym pasku bocznym strony produktu, jeśli Twój szablon obsługuje paski boczne na stronach produktów.
- **Zalecana wartość:** `displayFooterProduct`. Ten hook jest szeroko obsługiwany przez szablony i zapewnia wyraźne, nienachalne umiejscowienie dla powiązanych produktów. Eksperymentuj z innymi, jeśli masz na myśli konkretny projekt.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz, aby powiązane produkty były widoczne, ale nie kolidowały z głównym opisem produktu i przyciskiem „Dodaj do koszyka”. Wybór `displayFooterProduct` umieszcza je schludnie poniżej głównej treści, umożliwiając klientom przewijanie w dół i odkrywanie więcej.

#### **Wyświetlaj produkty w karuzeli**

- **Co robi to ustawienie:** Określa, czy powiązane produkty są wyświetlane w statycznej siatce (wszystkie widoczne jednocześnie) czy w dynamicznej, przewijanej karuzeli (gdzie klienci mogą klikać strzałki lub przesuwać, aby zobaczyć więcej).
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Powiązane produkty pojawią się w formacie karuzeli, co pozwala wyświetlić więcej produktów w kompaktowej przestrzeni.
  - *Gdy wyłączone (NIE):* Produkty będą wyświetlane w statycznej siatce, pokazując wszystkie wybrane produkty jednocześnie (do limitu „Liczba produktów do wyświetlenia”).
- **Zalecana wartość:** „TAK”, jeśli chcesz zaoszczędzić miejsce lub wyświetlić więcej produktów, niż zmieści się wygodnie w jednym rzędzie. „NIE”, jeśli wolisz, aby wszystkie produkty były natychmiast widoczne bez interakcji.
- **Scenariusz / przykład dla sprzedawcy:** Chcesz pokazać 8 powiązanych produktów, ale wyświetlanie ich wszystkich w siatce sprawia, że strona jest zbyt długa. Włączenie karuzeli pozwala wyświetlić 8 produktów, zajmując jednocześnie miejsce tylko 4, a klienci przewijają, aby zobaczyć resztę.

#### **Wyświetlaj produkty w losowej kolejności**

- **Co robi to ustawienie:** Kontroluje kolejność, w jakiej wyświetlane są powiązane produkty z wybranej kategorii.
- **Efekt zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Za każdym razem, gdy klient odwiedza stronę produktu, powiązane produkty pojawią się w innej, losowej kolejności.
  - *Gdy wyłączone (NIE):* Produkty pojawią się w stałej kolejności, zazwyczaj opartej na ich ID lub pozycji w wybranej kategorii.
- **Zalecana wartość:** „TAK”. Losowanie kolejności zapewnia, że wszystkie produkty w wybranej kategorii mają szansę być widziane w czasie, zapobiegając temu, aby te same kilka produktów zawsze znajdowało się na górze.
- **Scenariusz / przykład dla sprzedawcy:** Masz 20 produktów w kategorii „Akcesoria”, ale wyświetlasz tylko 5. Jeśli kolejność jest zawsze taka sama, tylko pierwsze 5 zostanie kiedykolwiek zobaczone. Włączenie losowej kolejności sprawi, że za każdym razem pojawią się różne akcesoria, zwiększając ich ekspozycję.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Wyświetl powiązane produkty z kategorii | Wybierz odpowiednią kategorię | Definiuje kategorię źródłową dla powiązanych produktów. |
| Konfiguracja modułu | Liczba produktów do wyświetlenia | 4-5 | Kontroluje, ile powiązanych produktów jest wyświetlanych. |
| Konfiguracja modułu | Wyświetlaj produkty tylko z wybranej kategorii | TAK / NIE (Przetestuj obie) | Określa, czy wyświetlane są tylko produkty z wybranej kategorii, czy też kategoria bieżącego produktu może również wnosić swój wkład. |
| Konfiguracja modułu | Hook do wyświetlania powiązanych produktów | `displayFooterProduct` | Określa lokalizację bloku powiązanych produktów na stronie produktu. |
| Konfiguracja modułu | Wyświetlaj produkty w karuzeli | TAK | Pokazuje powiązane produkty w przewijanej karuzeli dla kompaktowego wyświetlania. |
| Konfiguracja modułu | Wyświetlaj produkty w losowej kolejności | TAK | Losuje kolejność wyświetlanych powiązanych produktów dla zróżnicowanej ekspozycji. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Skonfigurowałem moduł, ale nie widzę żadnych powiązanych produktów na moich stronach produktów.**
O:

1.  **Sprawdź wybór kategorii:** Upewnij się, że wybrałeś prawidłową kategorię w ustawieniu „Wyświetl powiązane produkty z kategorii” i że ta kategoria faktycznie zawiera produkty.
2.  **Sprawdź status produktu:** Upewnij się, że produkty w wybranej kategorii są aktywne, dostępne w magazynie i widoczne w Twoim sklepie.
3.  **Wyczyść pamięć podręczną:** Przejdź do **Zaawansowane > Wydajność** w Panelu administracyjnym PrestaShop i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty”). Czasami PrestaShop wymaga odświeżenia pamięci podręcznej, aby wyświetlić nową zawartość modułu.
4.  **Kompatybilność z szablonem:** Chociaż moduł używa standardowych hooków PrestaShop, niektóre wysoce spersonalizowane szablony mogą mieć specyficzne nadpisania. Spróbuj tymczasowo przełączyć się na domyślny szablon PrestaShop, aby sprawdzić, czy blok się pojawi. Jeśli tak, Twój szablon może wymagać drobnych dostosowań.

**P: Blok powiązanych produktów wygląda dziwnie lub jest niestylizowany na mojej stronie.**
O: Jest to zazwyczaj konflikt CSS (stylizacji) z Twoim szablonem.

1.  **Wyczyść pamięć podręczną:** Zawsze zaczynaj od wyczyszczenia pamięci podręcznej PrestaShop.
2.  **Nadpisania szablonu:** Twój szablon może mieć własną stylizację dla list produktów lub karuzel, która powoduje konflikt. Może być konieczne, aby programista internetowy sprawdził CSS i zastosował niestandardowe style, aby dopasować go do projektu Twojego szablonu. Moduł zapewnia podstawową stylizację, ale style Twojego szablonu często mają pierwszeństwo.

**P: Czy mogę mieć różne powiązane produkty dla różnych głównych produktów?**
O: Moduł „Related Products Free” został zaprojektowany z myślą o prostocie, wyświetlając produkty z *jednej wybranej kategorii* na wszystkich stronach produktów. Aby uzyskać bardziej zaawansowane, specyficzne dla produktu przypisania powiązanych produktów, potrzebny byłby bardziej kompleksowy (płatny) moduł.

**P: Karuzela nie działa lub nie wyświetla się poprawnie.**
O:

1.  **Sprawdź konflikty JavaScript:** Inny moduł lub Twój szablon może mieć konfliktujący JavaScript, który uniemożliwia inicjalizację karuzeli. Sprawdź konsolę programisty w przeglądarce pod kątem błędów JavaScript.
2.  **Wyczyść pamięć podręczną:** Ponownie, wyczyść pamięć podręczną PrestaShop.
3.  **Wyłącz i włącz ponownie:** Spróbuj wyłączyć ustawienie „Wyświetlaj produkty w karuzeli”, zapisać, a następnie włączyć je ponownie i ponownie zapisać.

**P: Jak przetłumaczyć tytuł modułu (np. „Powiązane produkty”) na inne języki?**
O:

1.  Przejdź do **Lokalizacja > Tłumaczenia** w Panelu administracyjnym PrestaShop.
2.  Wybierz „Tłumaczenia zainstalowanych modułów” dla „Typu tłumaczenia”.
3.  Wybierz swój szablon (lub „Rdzeń”, jeśli Twój szablon nie jest wymieniony).
4.  Wybierz język, na który chcesz przetłumaczyć.
5.  Znajdź moduł „relatedfree” na liście i przetłumacz odpowiednie ciągi znaków.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

Ta sekcja zawiera techniczny przegląd dla programistów i webmasterów pracujących z modułem „Related Products Free”.

### 4.1 Przegląd architektury

Moduł „Related Products Free” to prosty moduł PrestaShop, który stosuje podstawowy wzorzec podobny do MVC w zakresie modułu. Wykorzystuje głównie metodę `getContent()` klasy `Module` do konfiguracji w Panelu administracyjnym i rejestruje pojedynczy hook (`displayFooterProduct` domyślnie, ale konfigurowalny) do wstrzykiwania swojego szablonu front-office. Nie wprowadza niestandardowych kontrolerów, ObjectModels ani złożonych zasobów JavaScript/CSS poza swoją podstawową funkcjonalnością.

### 4.2 Kontrolery (`controllers/`)

- Ten moduł **nie** zawiera żadnych niestandardowych kontrolerów Front-Office ani Back-Office. Cała konfiguracja jest obsługiwana w metodzie `getContent()` głównego pliku modułu.

### 4.3 Klasy podstawowe i modele (`classes/`)

- Ten moduł **nie** zawiera żadnych niestandardowych klas ani ObjectModels w katalogu `classes/`. Cała logika jest hermetyzowana w głównej klasie `RelatedFree` (zdefiniowanej w `index.php`).

### 4.4 Zasoby JavaScript (`views/js/`)

- Ten moduł **nie** zawiera żadnych niestandardowych plików JavaScript. Jeśli opcja karuzeli jest włączona, opiera się na podstawowych bibliotekach JavaScript PrestaShop (np. Owl Carousel, jeśli jest dostępny w szablonie, lub prosta niestandardowa implementacja w TPL, jeśli nie).

### 4.5 Arkusze stylów CSS (`views/css/`)

- Ten moduł **nie** zawiera żadnych niestandardowych plików CSS. Stylizacja jest oczekiwana do obsługi przez szablon lub opiera się na podstawowych stylach/strukturze inline, które szablony zazwyczaj stylizują. Programiści powinni zastosować niestandardowy CSS, aby dopasować go do estetyki swojego szablonu.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **Szablony administracyjne (`views/templates/admin/`)**:

  - `views/templates/admin/tabs.tpl`: Ten szablon służy do renderowania formularza konfiguracji modułu w Panelu administracyjnym. Definiuje strukturę ustawień, w tym pola wejściowe do wyboru kategorii, liczby produktów, wyboru hooka oraz przełączników dla karuzeli i losowej kolejności. Jest renderowany przez `getContent()` w `index.php`.
- **Szablony hooków (`views/templates/hook/`)**:

  - `views/templates/hook/productFooter.tpl`: To jest główny szablon front-office. Jest renderowany, gdy moduł jest zahaczone (np. `displayFooterProduct`). Ten szablon zawiera strukturę HTML dla bloku powiązanych produktów, w tym tytuł, i iteruje przez zmienną `$products` (przekazaną z modułu), aby wyświetlić obraz, nazwę i cenę każdego powiązanego produktu. Zawiera również logikę renderowania karuzeli, jeśli odpowiednia opcja konfiguracji jest włączona.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:
  Moduł nie tworzy żadnych niestandardowych tabel bazy danych. Wszystkie ustawienia konfiguracyjne są przechowywane w tabeli `ps_configuration` przy użyciu standardowych kluczy konfiguracyjnych PrestaShop.

  - `PS_RELATEDFREE_CATEGORY`: Przechowuje ID wybranej kategorii dla powiązanych produktów.
  - `PS_RELATEDFREE_NUMBER`: Przechowuje liczbę produktów do wyświetlenia.
  - `PS_RELATEDFREE_ONLY_SELECTED`: Przechowuje wartość logiczną (0/1) dla wyświetlania tylko produktów z wybranej kategorii.
  - `PS_RELATEDFREE_HOOK`: Przechowuje nazwę hooka, w którym moduł jest wyświetlany.
  - `PS_RELATEDFREE_CAROUSEL`: Przechowuje wartość logiczną (0/1) dla włączenia karuzeli.
  - `PS_RELATEDFREE_RANDOM`: Przechowuje wartość logiczną (0/1) dla wyświetlania produktów w losowej kolejności.
- **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `displayHeader` | W sekcji `<head>` każdej strony. | Używany do rejestrowania zasobów (chociaż ten moduł nie używa go do zasobów). |
| `displayLeftColumn` | W lewym pasku bocznym stron, które go posiadają. | Alternatywne umiejscowienie dla bloku powiązanych produktów. |
| `displayRightColumn` | W prawym pasku bocznym stron, które go posiadają. | Alternatywne umiejscowienie dla bloku powiązanych produktów. |
| `displayFooter` | Na dole każdej strony, przed zamykającym tagiem `</body>`. | Alternatywne umiejscowienie dla bloku powiązanych produktów. |
| `displayProductExtraContent` | W głównym obszarze treści produktu, często w zakładkach (PrestaShop 1.7+). | Alternatywne umiejscowienie dla bloku powiązanych produktów. |
| `displayFooterProduct` | Na dole sekcji informacji o produkcie na stronach produktów. | **Główny hook używany przez moduł** do wyświetlania powiązanych produktów. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i oficjalne wsparcie dla modułu „Related Products Free”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nasz zespół wsparcia jest dostępny, aby pomóc w przypadku wszelkich problemów lub pytań dotyczących funkcjonalności modułu.
