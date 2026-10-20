---
title: "Sugerowana/zalecana cena detaliczna producenta (MSRP) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kro kroku oraz dokumentacja dla programistów modułu PrestaShop „Sugerowana/zalecana cena detaliczna producenta (MSRP)” od MyPresta.eu."
sidebar:
  label: "Sugerowana/zalecana cena detaliczna producenta (MSRP) - Instrukcja dla sprzedawcy i przewodnik konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Manufacturer suggested / recommended retail price (MSRP) na MyPresta.eu](https://mypresta.eu/modules/front-office-features/manufacturer-suggested-recommended-retail-price-msrp.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/front-office/manufacturer-suggested-recommended-retail-price-msrp/)
>
> ---


# Sugerowana/zalecana cena detaliczna producenta (MSRP)

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL).

## 2. Kompletny przewodnik konfiguracji (każda grupa ustawień według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Jest to główny ekran konfiguracji modułu MSRP, dostępny po instalacji poprzez kliknięcie przycisku „Konfiguruj”. Tutaj zdefiniujesz, w jaki sposób MSRP są wyświetlane i zarządzane w Twoim sklepie.

#### **Włącz wyświetlanie MSRP**

- **Co robi to ustawienie:** Jest to główny przełącznik do włączania lub wyłączania funkcji MSRP dla całego sklepu.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Moduł zacznie wyświetlać informacje o MSRP na stronach produktów i listach produktów, pod warunkiem, że wprowadziłeś MSRP dla swoich produktów.
  - *Gdy wyłączone (NIE):* Funkcja MSRP będzie całkowicie nieaktywna, a żadne informacje o MSRP nie będą wyświetlane klientom, nawet jeśli wprowadziłeś wartości.
- **Zalecana wartość:** TAK (aby korzystać z funkcji modułu).
- **Scenariusz/przykład dla sprzedawcy:** Jeśli konfigurujesz moduł po raz pierwszy, włącz go, aby zobaczyć zmiany. Jeśli musisz tymczasowo ukryć MSRP dla promocji lub konserwacji, możesz go tutaj wyłączyć.

#### **Wyświetl MSRP na stronie produktu**

- **Co robi to ustawienie:** Kontroluje, czy MSRP jest wyświetlane na poszczególnych stronach szczegółów produktu.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* MSRP, Twoja cena i informacje „Oszczędzasz” pojawią się na stronie produktu.
  - *Gdy wyłączone (NIE):* MSRP nie będzie wyświetlane na stronie produktu, nawet jeśli jest włączone globalnie.
- **Zalecana wartość:** TAK (Jest to główne miejsce, w którym klienci widzą wartość).
- **Scenariusz/przykład dla sprzedawcy:** Możesz to wyłączyć, jeśli wolisz podkreślać oszczędności tylko na stronach kategorii lub jeśli projekt Twojej strony produktu jest już bardzo zatłoczony.

#### **Wyświetl MSRP na liście produktów**

- **Co robi to ustawienie:** Kontroluje, czy MSRP jest wyświetlane na stronach wyświetlających wiele produktów, takich jak strony kategorii, wyniki wyszukiwania lub bloki polecanych produktów.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* MSRP, Twoja cena i informacje „Oszczędzasz” pojawią się dla każdego produktu na listach produktów.
  - *Gdy wyłączone (NIE):* MSRP nie będzie wyświetlane na stronach list produktów.
- **Zalecana wartość:** TAK (Świetne do szybkich porównań i podkreślania wartości podczas przeglądania).
- **Scenariusz/przykład dla sprzedawcy:** Włączenie tej opcji pomaga klientom szybko zidentyfikować dobre oferty podczas przeglądania kategorii, potencjalnie zwiększając współczynnik klikalności na strony produktów.

#### **Pokaż cenę z podatkiem**

- **Co robi to ustawienie:** Określa, czy wyświetlane MSRP powinno zawierać podatki, czy być wyświetlane jako cena bez podatku.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* MSRP zostanie wyświetlone z już dodanymi odpowiednimi podatkami, odzwierciedlając ostateczną cenę, jaką zapłaciłby klient.
  - *Gdy wyłączone (NIE):* MSRP zostanie wyświetlone bez podatków.
- **Zalecana wartość:** TAK (Ogólnie klienci wolą widzieć ceny końcowe, zwłaszcza w kontekście B2C).
- **Scenariusz/przykład dla sprzedawcy:** Jeśli Twój sklep obsługuje głównie klientów B2C, wyświetlanie cen z podatkiem jest jaśniejsze. W przypadku sklepów B2B preferowane mogą być ceny bez podatku.

#### **Pokaż cenę bez podatku**

- **Co robi to ustawienie:** Określa, czy wyświetlane MSRP powinno wykluczać podatki, czy być wyświetlane jako cena z podatkiem.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* MSRP zostanie wyświetlone bez podatków.
  - *Gdy wyłączone (NIE):* MSRP zostanie wyświetlone z już dodanymi odpowiednimi podatkami.
- **Zalecana wartość:** NIE (Chyba że celujesz w klientów B2B lub działasz w regionie, gdzie ceny bez podatku są standardem dla początkowego wyświetlania).
- **Scenariusz/przykład dla sprzedawcy:** Jeśli włączysz „Pokaż cenę z podatkiem”, zazwyczaj wyłączysz tę opcję, aby uniknąć zamieszania. Włącz obie tylko wtedy, gdy chcesz pokazać obie wartości obok siebie (co może być mylące dla klientów).

#### **Wyświetl informacje „Oszczędzasz”**

- **Co robi to ustawienie:** Kontroluje, czy moduł oblicza i wyświetla różnicę pieniężną między MSRP a ceną sprzedaży Twojego sklepu.
- **Wpływ zmiany tego ustawienia:**
  - *Gdy włączone (TAK):* Moduł wyświetli komunikat typu „Oszczędzasz X,XX zł” lub „Oszczędzasz X%” obok MSRP i Twojej ceny.
  - *Gdy wyłączone (NIE):* Wyświetlone zostanie tylko MSRP i Twoja cena, bez jawnego obliczenia oszczędności.
- **Zalecana wartość:** TAK (Jest to kluczowa korzyść z korzystania z modułu, silnie motywująca do zakupów).
- **Scenariusz/przykład dla sprzedawcy:** Ta funkcja bezpośrednio podkreśla propozycję wartości. Jeśli Twoje ceny są konsekwentnie niższe niż MSRP, włączenie tej opcji znacznie zwiększy postrzeganą wartość.

#### **Pole MSRP dla produktów**

- **Co robi to ustawienie:** To ustawienie definiuje, gdzie będziesz wprowadzać MSRP dla każdego produktu w Panelu administracyjnym PrestaShop.
- **Wpływ zmiany tego ustawienia:**
  - *Po wybraniu:* Moduł użyje wybranego pola produktu do pobrania wartości MSRP. Będziesz musiał ręcznie wprowadzić MSRP dla każdego produktu w określonym polu.
- **Zalecana wartość:** Moduł zazwyczaj tworzy niestandardowe pole lub sugeruje użycie istniejącego. Postępuj zgodnie z instrukcjami modułu, aby zidentyfikować właściwe pole.
- **Scenariusz/przykład dla sprzedawcy:** Po zainstalowaniu modułu przejdziesz do **Katalog > Produkty**, edytujesz produkt i znajdziesz nowe pole wprowadzania (lub istniejące, które zostało ponownie wykorzystane), w którym możesz wpisać MSRP dla tego konkretnego produktu.

### 2.2 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Konfiguracja modułu | Włącz wyświetlanie MSRP | TAK | Główny przełącznik do aktywacji/dezaktywacji funkcji MSRP w całym sklepie. |
| Konfiguracja modułu | Wyświetl MSRP na stronie produktu | TAK | Pokaż MSRP na indywidualnych stronach szczegółów produktu. |
| Konfiguracja modułu | Wyświetl MSRP na liście produktów | TAK | Pokaż MSRP na stronach kategorii/wyników wyszukiwania. |
| Konfiguracja modułu | Pokaż cenę z podatkiem | TAK | Wyświetl MSRP z wliczonymi podatkami (przyjazne dla B2C). |
| Konfiguracja modułu | Pokaż cenę bez podatku | NIE | Wyświetl MSRP bez podatków (przyjazne dla B2B, unikaj konfliktu z „Cena z podatkiem”). |
| Konfiguracja modułu | Wyświetl informacje „Oszczędzasz” | TAK | Pokaż obliczone oszczędności (MSRP - Twoja cena). |
| Konfiguracja modułu | Pole MSRP dla produktów | (Specyficzne dla modułu) | Definiuje, które pole produktu w Panelu administracyjnym przechowuje wartość MSRP. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P1: Włączyłem moduł i wprowadziłem MSRP, ale nic nie wyświetla się w moim sklepie. Co jest nie tak?**
O1:

- **Sprawdź globalne włączenie:** Upewnij się, że „Włącz wyświetlanie MSRP” jest ustawione na TAK w konfiguracji modułu.
- **Sprawdź konkretne ustawienia wyświetlania:** Sprawdź, czy „Wyświetl MSRP na stronie produktu” i „Wyświetl MSRP na liście produktów” są również ustawione na TAK dla obszarów, w których spodziewasz się ich zobaczyć.
- **Wyczyść pamięć podręczną:** PrestaShop używa pamięci podręcznej. Przejdź do **Zaawansowane > Wydajność** i kliknij „Wyczyść pamięć podręczną” (lub „Wyczyść pamięć podręczną Smarty” w starszych wersjach).
- **MSRP specyficzne dla produktu:** Sprawdź dokładnie, czy faktycznie wprowadziłeś wartość MSRP dla konkretnych produktów, które testujesz.
- **Kompatybilność z motywem:** Czasami bardzo dostosowane motywy mogą wymagać drobnych korekt, aby wyświetlać nowe elementy. Jeśli po wyczyszczeniu pamięci podręcznej nadal się nie pojawia, skontaktuj się z pomocą techniczną MyPresta.eu.

**P2: Kwota „Oszczędzasz” wydaje się nieprawidłowa lub nie pojawia się.**
O2:

- **Włącz „Oszczędzasz”:** Upewnij się, że „Wyświetl informacje „Oszczędzasz”” jest włączone w ustawieniach modułu.
- **MSRP vs. Twoja cena:** Obliczenie „Oszczędzasz” zależy zarówno od MSRP, jak i ceny sprzedaży Twojego produktu. Upewnij się, że obie wartości są poprawnie ustawione dla produktu. Jeśli Twoja cena sprzedaży jest wyższa lub równa MSRP, oszczędności nie zostaną wyświetlone.
- **Ustawienia podatkowe:** Na obliczenia mogą mieć wpływ ustawienia dotyczące wyświetlania cen z podatkiem lub bez podatku. Upewnij się, że Twoje ustawienia podatkowe są spójne.

**P3: Jak wprowadzić MSRP dla każdego produktu?**
O3: Po zainstalowaniu modułu przejdź do **Katalog > Produkty** w Panelu administracyjnym PrestaShop. Edytuj istniejący produkt lub utwórz nowy. W interfejsie edycji produktu powinieneś znaleźć nowe pole specjalnie dla „MSRP” (lub ponownie wykorzystane istniejące pole, zgodnie z konfiguracją modułu). Wprowadź tam sugerowaną cenę detaliczną producenta i zapisz produkt.

**P4: Tekst MSRP nie pasuje do projektu/czcionki mojego sklepu. Jak mogę to zmienić?**
O4: Moduł używa własnego CSS do stylizacji. W przypadku drobnych korekt (takich jak rozmiar czcionki, kolor) często można nadpisać te style w niestandardowym pliku CSS motywu (np. `themes/yourtheme/assets/css/custom.css` lub `themes/yourtheme/css/custom.css`). W przypadku bardziej rozbudowanych zmian może być konieczne, aby programista internetowy zbadał CSS modułu i zastosował bardziej szczegółowe nadpisania.

## 4. Przewodnik dla programistów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Sugerowana/zalecana cena detaliczna producenta (MSRP)” to standardowy moduł PrestaShop zaprojektowany w celu rozszerzenia funkcji wyświetlania produktów w front office. Działa głównie poprzez podłączanie się do istniejących punktów wyświetlania PrestaShop (takich jak strony produktów i listy produktów) w celu wstrzyknięcia informacji o MSRP. Wykorzystuje system konfiguracji PrestaShop dla swoich ustawień i szablony Smarty do renderowania danych wyjściowych w front office. Podstawowa logika modułu znajduje się w jego głównym pliku PHP, obsługującym instalację, deinstalację, konfigurację i rejestrację hooków.

### 4.2 Kontrolery (`controllers/`)

Ten moduł nie wykorzystuje niestandardowych kontrolerów Front-Office ani Back-Office Admin. Cała konfiguracja jest obsługiwana za pomocą metody `getContent()` w głównym pliku modułu, a wyświetlanie w front office jest zarządzane za pomocą hooków i renderowania szablonów.

### 4.3 Klasy podstawowe i modele (`classes/`)

Ten moduł nie definiuje żadnych niestandardowych klas ani instancji `ObjectModel` w katalogu `classes/`. Bezpośrednio współdziała z istniejącymi danymi produktów i konfiguracją PrestaShop.

### 4.4 Zasoby JavaScript (`views/js/`)

- **`msrp/views/admin/js/msrp.js`**

  - **Zakres:** Panel administracyjny.
  - **Cel:** Ten skrypt prawdopodobnie obsługuje wszelkie dynamiczne zachowania lub walidację w formularzu konfiguracji modułu w Panelu administracyjnym PrestaShop. Może to obejmować pokazywanie/ukrywanie pól na podstawie innych wyborów, wywołania AJAX do zapisywania ustawień lub walidację po stronie klienta.
  - **Szczegóły:** Wiąże słuchaczy zdarzeń z elementami formularza konfiguracji, obsługuje przesyłanie formularzy i potencjalnie aktualizuje interfejs użytkownika na podstawie danych wejściowych użytkownika.
- **`msrp/views/js/msrp.js`**

  - **Zakres:** Front Office.
  - **Cel:** Ten skrypt jest odpowiedzialny za wszelkie interakcje po stronie klienta lub dynamiczne aktualizacje związane z wyświetlaniem MSRP w front office. Może to obejmować dynamiczną aktualizację kwoty „Oszczędzasz”, jeśli atrybuty produktu ulegną zmianie (np. wybranie innego rozmiaru/koloru, który wpływa na cenę), lub obsługę logiki wyświetlania.
  - **Szczegóły:** Wiąże się ze zdarzeniami `prestashop.on` (np. `updatedProduct` dla zmian cen na stronie produktu), manipuluje elementami DOM w celu aktualizacji wyświetlania MSRP lub oszczędności i zapewnia responsywność.

### 4.5 Arkusze stylów CSS (`views/css/`)

- **`msrp/views/admin/css/msrp.css`**

  - **Zakres:** Stylizacja formularza administracyjnego w Panelu administracyjnym.
  - **Cel:** Zapewnia specyficzną stylizację strony konfiguracji modułu w Panelu administracyjnym PrestaShop, zapewniając spójny i przyjazny dla użytkownika interfejs.
  - **Kluczowe selektory:** Celuje w elementy w danych wyjściowych `getContent()` modułu, takie jak pola formularza, etykiety i sekcje.
- **`msrp/views/css/msrp.css`**

  - **Zakres:** Stylizacja dla klientów w Front Office.
  - **Cel:** Stylizuje wyświetlane MSRP, Twoją cenę i informacje „Oszczędzasz” na stronach produktów i listach produktów. Zapewnia to, że informacje są wyraźnie widoczne i dobrze integrują się z ogólnym projektem sklepu.
  - **Kluczowe selektory:** Celuje w konkretne elementy `div` lub `span` generowane przez szablony Smarty modułu (np. `.msrp-price`, `.msrp-you-save`, `.msrp-old-price`). Programiści mogą nadpisać te klasy w pliku `custom.css` swojego motywu, aby dopasować je do swojej marki.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

- **`msrp/views/admin/msrp.tpl`**

  - **Zakres:** Szablony administracyjne.
  - **Cel:** Ten szablon renderuje formularz konfiguracji modułu w Panelu administracyjnym PrestaShop. Zawiera strukturę HTML dla wszystkich ustawień opisanych w sekcji 4.1.
  - **Szczegóły:** Używa komponentów formularza pomocniczego PrestaShop (np. `helperForm`) do tworzenia pól wprowadzania, przełączników i przycisków dla ustawień modułu.
- **`msrp/views/templates/msrp-product-list.tpl`**

  - **Zakres:** Szablony hooków (np. `displayProductPriceBlock` lub podobne dla list produktów).
  - **Cel:** Ten szablon jest odpowiedzialny za wyświetlanie informacji o MSRP na stronach list produktów (kategorie, wyniki wyszukiwania itp.). Zazwyczaj otrzymuje dane produktu i ustawienia konfiguracji modułu, aby renderować MSRP, aktualną cenę i komunikat „Oszczędzasz”.
  - **Szczegóły:** Zawiera logikę sprawdzającą, czy MSRP jest dostępne, czy „Oszczędzasz” powinno być wyświetlane, i formatuje ceny zgodnie z ustawieniami podatkowymi.
- **`msrp/views/templates/msrp-product-page.tpl`**

  - **Zakres:** Szablony hooków (np. `displayProductPriceBlock` lub `displayProductButtons` na stronach produktów).
  - **Cel:** Ten szablon renderuje informacje o MSRP na indywidualnych stronach szczegółów produktu. Został zaprojektowany tak, aby płynnie integrować się w pobliżu głównego bloku ceny produktu.
  - **Szczegóły:** Podobnie jak `msrp-product-list.tpl`, obsługuje warunkowe wyświetlanie MSRP, aktualnej ceny i oszczędności, stosując zasady podatkowe i formatowanie.

### 4.7 Schemat bazy danych i mapa hooków

- **Tabele bazy danych**:

  - Ten moduł nie tworzy niestandardowych tabel SQL.
  - Ustawienia konfiguracji są przechowywane w tabeli `ps_configuration`, zazwyczaj z kluczami poprzedzonymi `MSRP_` (np. `MSRP_ENABLE`, `MSRP_DISPLAY_PRODUCT_PAGE`).
  - Wartości MSRP dla produktów są przechowywane w istniejącym polu produktu, zgodnie z konfiguracją w module (np. `ps_product_lang.description_short` lub niestandardowe pole produktu, jeśli zostało utworzone przez moduł).
- **Tabela zarejestrowanych hooków**:
  Moduł rejestruje hooki, aby wstrzykiwać swoją zawartość do front office i zarządzać swoim cyklem życia.

  | Nazwa hooka | Czas wykonania | Cel techniczny |
  | --- | --- | --- |
  | `install()` | Podczas instalacji modułu | Tworzy wpisy konfiguracyjne, rejestruje hooki, potencjalnie dodaje pola produktu. |
  | `uninstall()` | Podczas deinstalacji modułu | Czyści wpisy konfiguracyjne, wyrejestrowuje hooki, usuwa pola produktu. |
  | `displayHeader` | W sekcji `<head>` każdej strony | Wstrzykuje pliki CSS i JS modułu do wyświetlania w front office. |
  | `displayProductPriceBlock` | W bloku ceny produktu na stronach produktów i listach | Główny hook do renderowania MSRP, aktualnej ceny i informacji „Oszczędzasz”. Ten hook jest wywoływany wielokrotnie z różnymi parametrami (np. `type='after_price'`). |
  | `actionProductUpdate` | Po zaktualizowaniu produktu w Panelu administracyjnym | Potencjalnie używany do zapewnienia poprawnego zapisania lub przetworzenia danych MSRP. |
  | `actionProductSave` | Po zapisaniu produktu w Panelu administracyjnym | Podobnie jak `actionProductUpdate`, zapewnia integralność danych MSRP. |
  | `actionProductDelete` | Po usunięciu produktu | Czyści wszelkie powiązane dane MSRP, jeśli są przechowywane oddzielnie. |
  | `displayAdminProductsExtra` | Na stronie edycji produktu w Panelu administracyjnym | Dodaje pole wprowadzania MSRP do formularza produktu. |

## 5. Oficjalne wsparcie i aktualizacje

W celu uzyskania oficjalnych aktualizacji, wsparcia technicznego i wszelkiej dalszej pomocy dotyczącej modułu „Sugerowana/zalecana cena detaliczna producenta (MSRP)” prosimy o zapoznanie się z kontem klienta na stronie [MyPresta.eu](https://mypresta.eu/). Nasz zespół wsparcia i programiści są gotowi pomóc Ci zmaksymalizować potencjał tego modułu dla Twojego sklepu PrestaShop.
"""
