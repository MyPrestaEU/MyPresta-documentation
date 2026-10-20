---
title: "Eksport produktów do Delcampe Lister - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
description: "Kompletna instrukcja obsługi, przewodnik konfiguracji krok po kroku oraz referencje dla deweloperów modułu PrestaShop „Eksport produktów do Delcampe Lister” od MyPresta.eu."
sidebar:
  label: "Eksport produktów do Delcampe Lister - Instrukcja dla Sprzedawcy i Przewodnik Konfiguracji"
---

> ⚠️ **Notice:** This is the oficjalna dokumentacja modułu PrestaShop.
> - 🛒 **Pełną specyfikację handlową, changelog oraz możliwość zakupu znajdziesz na oficjalnej karcie produktu na MyPresta.eu:** [Kup moduł Export products to Delcampe Lister na MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/export-products-to-delcampe-lister.html)
> - 🌐 **Oficjalny hub dokumentacyjny online:** [Czytaj interaktywną dokumentację na MyPresta.eu](https://mypresta.eu/docs/pl/advertising-marketing/export-products-to-delcampe-lister/)
>
> ---


# Eksport produktów do Delcampe Lister

## 1. Wymagania i kompatybilność

- **Obsługiwane wersje PrestaShop**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Kompatybilność z PHP**: PHP 5.6 - 8.5
- **Wymagania hostingowe**: Standardowe rozszerzenia PHP (cURL, JSON, OpenSSL) są zazwyczaj wymagane do prawidłowego działania PrestaShop i powinny być dostępne w większości środowisk hostingowych.

## 2. Kompletny przewodnik konfiguracji (Każde ustawienie pogrupowane według ekranu)

### 2.1 Strona konfiguracji modułu (Panel administracyjny > Moduły > Konfiguruj)

Możesz uzyskać dostęp do tego ekranu, przechodząc do **Moduły > Menedżer modułów** i klikając „Konfiguruj” obok „Eksport produktów do Delcampe Lister”.

Ten ekran obsługuje głównie ogólne ustawienia modułu, w tym sprawdzanie aktualizacji.

-   **MyPresta.eu Sprawdzanie aktualizacji na żywo:**
    -   **Co robi to ustawienie:** Ta opcja kontroluje, czy moduł automatycznie sprawdza dostępność nowych wersji i aktualizacji z MyPresta.eu.
    -   **Efekt zmiany tego ustawienia:**
        -   *Gdy włączone:* Moduł będzie okresowo łączyć się z MyPresta.eu, aby sprawdzić, czy dostępna jest nowsza wersja. Pomaga to być na bieżąco z poprawkami błędów i nowymi funkcjami.
        -   *Gdy wyłączone:* Moduł nie będzie automatycznie sprawdzać aktualizacji. Musiałbyś ręcznie sprawdzać aktualizacje na swoim koncie MyPresta.eu.
    -   **Zalecana wartość:** TAK
    -   **Scenariusz / przykład dla sprzedawcy:** Utrzymywanie tej opcji włączonej zapewnia, że zawsze używasz najbardziej stabilnej i bogatej w funkcje wersji modułu, bez konieczności pamiętania o ręcznym sprawdzaniu.

### 2.2 Dedykowane ekrany administracyjne i widoki kontrolerów

#### 2.2.1 Zarządzanie produktami Delcampe (Panel administracyjny > Katalog > Produkty Delcampe)

To jest główny ekran zarządzania eksportem produktów Delcampe. Możesz uzyskać do niego dostęp, przechodząc do **Katalog > Produkty Delcampe** w menu Panelu administracyjnego PrestaShop.

Ten ekran przedstawia widok siatki Twoich produktów i umożliwia zarządzanie ich ustawieniami eksportu dla Delcampe. Możesz dodawać nowe produkty do listy eksportu, edytować istniejące i generować plik eksportu.

**Dostępne akcje i ustawienia:**

-   **Tabela listy produktów:** Ta tabela wyświetla wszystkie produkty, które są już skonfigurowane do eksportu Delcampe lub są dostępne do konfiguracji. Zobaczysz kolumny takie jak ID produktu, nazwa i potencjalnie ich ustawienia specyficzne dla Delcampe.
-   **Dodaj nowy produkt / Edytuj produkt:**
    -   Kliknięcie „Dodaj nowy” lub edycja istniejącego produktu otworzy formularz, w którym możesz zdefiniować specyficzne parametry ogłoszenia Delcampe dla tego produktu.
    -   **`category_id` (ID kategorii Delcampe):**
        -   **Co robi to ustawienie:** Jest to specyficzny ID kategorii na Delcampe, w której Twój produkt zostanie wystawiony. Delcampe ma własną strukturę kategorii, która może różnić się od PrestaShop.
        -   **Efekt zmiany tego ustawienia:** Nieprawidłowe ID kategorii spowodują, że Twój produkt zostanie wystawiony w niewłaściwej sekcji na Delcampe lub potencjalnie nie zostanie wystawiony.
        -   **Zalecana wartość:** Dokładny numeryczny ID docelowej kategorii Delcampe.
        -   **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz rzadki znaczek, znajdziesz odpowiedni ID kategorii „Znaczki” na Delcampe i wprowadzisz go tutaj.
    -   **`title` (Tytuł ogłoszenia Delcampe):**
        -   **Co robi to ustawienie:** Tytuł, który pojawi się dla Twojego produktu na Delcampe. Może różnić się od nazwy produktu w PrestaShop.
        -   **Efekt zmiany tego ustawienia:** Przekonujący i bogaty w słowa kluczowe tytuł może znacznie poprawić widoczność na Delcampe.
        -   **Zalecana wartość:** Opisowy, zwięzły tytuł zoptymalizowany pod kątem wyszukiwań na Delcampe.
        -   **Scenariusz / przykład dla sprzedawcy:** Zamiast „Stary znaczek”, możesz użyć „Rzadki znaczek francuski z 1920 r. - Nieużywany - Stan doskonały”.
    -   **`description` (Opis ogłoszenia Delcampe):**
        -   **Co robi to ustawienie:** Szczegółowy opis produktu, który zostanie wyświetlony w Twoim ogłoszeniu na Delcampe.
        -   **Efekt zmiany tego ustawienia:** Dokładny opis ze wszystkimi istotnymi szczegółami pomaga kupującym podejmować świadome decyzje i buduje zaufanie.
        -   **Zalecana wartość:** Kompleksowy opis, potencjalnie zawierający kontekst historyczny, stan i wymiary.
        -   **Scenariusz / przykład dla sprzedawcy:** Skopiuj opis z PrestaShop, ale rozważ dodanie szczegółów lub formatowania specyficznych dla Delcampe.
    -   **`personal_reference` (Twoja wewnętrzna referencja):**
        -   **Co robi to ustawienie:** Opcjonalne pole dla Twojego własnego wewnętrznego numeru śledzenia lub referencyjnego dla produktu na Delcampe.
        -   **Efekt zmiany tego ustawienia:** Pomaga dopasować sprzedaż z Delcampe do Twojego wewnętrznego systemu inwentaryzacji.
        -   **Zalecana wartość:** Referencja produktu PrestaShop lub SKU.
        -   **Scenariusz / przykład dla sprzedawcy:** Użycie tutaj SKU z PrestaShop pozwala szybko zidentyfikować produkt w Twoim sklepie, gdy pojawi się zamówienie z Delcampe.
    -   **`currency` (Waluta ogłoszenia):**
        -   **Co robi to ustawienie:** Waluta, w której produkt zostanie wystawiony na Delcampe.
        -   **Efekt zmiany tego ustawienia:** Musi odpowiadać walucie obsługiwanej przez Delcampe.
        -   **Zalecana wartość:** Twoja podstawowa waluta sprzedaży (np. EUR, USD).
        -   **Scenariusz / przykład dla sprzedawcy:** Jeśli sprzedajesz głównie w euro, ustaw to na EUR.
    -   **`selling_type` (Typ sprzedaży Delcampe):**
        -   **Co robi to ustawienie:** Definiuje, w jaki sposób produkt jest sprzedawany na Delcampe (np. aukcja, stała cena).
        -   **Efekt zmiany tego ustawienia:** Określa proces zakupu dla klientów na Delcampe.
        -   **Zalecana wartość:** Wybierz typ, który najlepiej pasuje do Twojego produktu i strategii sprzedaży (np. „Stała cena” dla standardowych przedmiotów, „Aukcja” dla rzadkich przedmiotów).
        -   **Scenariusz / przykład dla sprzedawcy:** Dla popularnego przedmiotu kolekcjonerskiego odpowiednia może być „Stała cena”. Dla naprawdę unikalnego przedmiotu „Aukcja” może przynieść wyższe oferty.
    -   **`price` (Cena początkowa / Cena stała):**
        -   **Co robi to ustawienie:** Cena początkowa dla aukcji lub stała cena za sprzedaż bezpośrednią.
        -   **Efekt zmiany tego ustawienia:** Bezpośrednio wpływa na koszt dla kupującego.
        -   **Zalecana wartość:** Twoja pożądana cena sprzedaży.
        -   **Scenariusz / przykład dla sprzedawcy:** Dla przedmiotu o stałej cenie byłaby to Twoja cena detaliczna. Dla aukcji jest to minimalna oferta.
    -   **`initial_quantity` (Dostępna ilość):**
        -   **Co robi to ustawienie:** Liczba jednostek tego produktu, które udostępniasz na Delcampe.
        -   **Efekt zmiany tego ustawienia:** Określa, ile przedmiotów kupujący może kupić.
        -   **Zalecana wartość:** Twój aktualny poziom zapasów dla produktu.
        -   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz 5 sztuk konkretnego znaczka, ustaw to na 5.
    -   **`minimum_bid_step` (Krok licytacji aukcyjnej):**
        -   **Co robi to ustawienie:** Dla ogłoszeń w stylu aukcji, definiuje minimalną kwotę, o jaką oferta musi wzrosnąć.
        -   **Efekt zmiany tego ustawienia:** Wpływa na zachowanie licytujących.
        -   **Zalecana wartość:** Rozsądny przyrost (np. 0.50, 1.00).
        -   **Scenariusz / przykład dla sprzedawcy:** Jeśli ustawiono na 1.00, oferta 10.00 wymagałaby, aby następna oferta wynosiła co najmniej 11.00.
    -   **`renew_duration` (Czas automatycznego odnawiania):**
        -   **Co robi to ustawienie:** Jeśli włączone, określa, jak długo niewystawione ogłoszenie będzie automatycznie odnawiane.
        -   **Efekt zmiany tego ustawienia:** Utrzymuje Twój produkt na Delcampe bez ręcznej interwencji.
        -   **Zalecana wartość:** Czas trwania zgodny z Twoim cyklem sprzedaży (np. 7 dni, 14 dni).
        -   **Scenariusz / przykład dla sprzedawcy:** Jeśli przedmiot nie sprzeda się w ciągu 7 dni, zostanie automatycznie ponownie wystawiony na kolejne 7 dni.
    -   **`renew_total_count` (Limit automatycznego odnawiania):**
        -   **Co robi to ustawienie:** Maksymalna liczba razy, ile niewystawione ogłoszenie zostanie automatycznie odnowione.
        -   **Efekt zmiany tego ustawienia:** Zapobiega niekończącemu się ponownemu wystawianiu niepopularnych przedmiotów.
        -   **Zalecana wartość:** Rozsądny limit (np. 3, 5).
        -   **Scenariusz / przykład dla sprzedawcy:** Jeśli przedmiot nie sprzeda się po 3 odnowieniach, zostanie usunięty z Delcampe.
    -   **`shipping_model` (Model wysyłki Delcampe):**
        -   **Co robi to ustawienie:** Metoda lub model wysyłki, którego używasz na Delcampe. Musi odpowiadać Twoim wstępnie skonfigurowanym ustawieniom wysyłki na Delcampe.
        -   **Efekt zmiany tego ustawienia:** Określa, jak koszty wysyłki są obliczane i prezentowane kupującemu.
        -   **Zalecana wartość:** ID lub nazwa Twojego preferowanego modelu wysyłki Delcampe.
        -   **Scenariusz / przykład dla sprzedawcy:** Jeśli masz skonfigurowany model „Standardowa wysyłka międzynarodowa” na Delcampe, wprowadzisz jego identyfikator tutaj.
    -   **`weight` (Waga produktu):**
        -   **Co robi to ustawienie:** Waga produktu, używana do obliczania kosztów wysyłki na Delcampe.
        -   **Efekt zmiany tego ustawienia:** Kluczowe dla dokładnego oszacowania kosztów wysyłki.
        -   **Zalecana wartość:** Rzeczywista waga produktu.
        -   **Scenariusz / przykład dla sprzedawcy:** Wprowadź „0.1” dla lekkiego znaczka.
    -   **`lister_sale_end_time` (Godzina zakończenia sprzedaży):**
        -   **Co robi to ustawienie:** Konkretna godzina zakończenia ogłoszenia.
        -   **Efekt zmiany tego ustawienia:** Pozwala zaplanować zakończenie Twoich ogłoszeń.
        -   **Zalecana wartość:** Godzina, o której Twoja grupa docelowa jest najbardziej prawdopodobna online (np. 20:00).
        -   **Scenariusz / przykład dla sprzedawcy:** Zakończenie aukcji o 20:00 w niedzielę może przyciągnąć więcej ofert w ostatniej chwili.
    -   **`lister_sale_end_day` (Dzień zakończenia sprzedaży):**
        -   **Co robi to ustawienie:** Konkretny dzień tygodnia, w którym ogłoszenie się zakończy.
        -   **Efekt zmiany tego ustawienia:** Pozwala zaplanować zakończenie Twoich ogłoszeń.
        -   **Zalecana wartość:** Dzień, w którym Twoja grupa docelowa jest najbardziej prawdopodobna online (np. niedziela).
        -   **Scenariusz / przykład dla sprzedawcy:** Zakończenie aukcji w niedzielę może przyciągnąć więcej ofert w ostatniej chwili.
    -   **`option_last_minute_extension` (Przedłużenie w ostatniej chwili):**
        -   **Co robi to ustawienie:** Jeśli włączone, przedłuża czas trwania aukcji, jeśli oferta zostanie złożona w ostatnich minutach.
        -   **Efekt zmiany tego ustawienia:** Zapobiega „snajperstwu” i zachęca do wyższych ofert.
        -   **Zalecana wartość:** TAK (dla aukcji).
        -   **Scenariusz / przykład dla sprzedawcy:** Oferta złożona 30 sekund przed zakończeniem aukcji przedłuży aukcję o kilka minut, dając innym szansę na kontrofertę.
    -   **`option_anonymous_buyer` (Anonimowy kupujący):**
        -   **Co robi to ustawienie:** Ukrywa tożsamość kupującego przed innymi licytującymi w aukcji.
        -   **Efekt zmiany tego ustawienia:** Może zwiększyć prywatność licytujących.
        -   **Zalecana wartość:** NIE (chyba że kwestie prywatności są najważniejsze).
        -   **Scenariusz / przykład dla sprzedawcy:** Jeśli chcesz chronić prywatność kupującego, włącz tę opcję.
    -   **`option_strong_title` (Mocny tytuł / Pogrubiony tytuł):**
        -   **Co robi to ustawienie:** Sprawia, że tytuł Twojego ogłoszenia jest pogrubiony na Delcampe, zwiększając jego widoczność.
        -   **Efekt zmiany tego ustawienia:** Twoje ogłoszenie bardziej wyróżnia się w wynikach wyszukiwania.
        -   **Zalecana wartość:** TAK.
        -   **Scenariusz / przykład dla sprzedawcy:** Użycie pogrubionego tytułu pomaga Twojemu ogłoszeniu o rzadkim znaczku przyciągnąć uwagę kolekcjonerów przeglądających wiele podobnych przedmiotów.
    -   **`option_background_color` (Kolor tła):**
        -   **Co robi to ustawienie:** Ustawia niestandardowy kolor tła dla Twojego ogłoszenia na Delcampe.
        -   **Efekt zmiany tego ustawienia:** Może sprawić, że Twoje ogłoszenie będzie bardziej atrakcyjne wizualnie lub dopasowane do Twojej marki.
        -   **Zalecana wartość:** Pozostaw puste lub użyj subtelnego koloru.
        -   **Scenariusz / przykład dla sprzedawcy:** Użycie jasnoniebieskiego tła może sprawić, że Twoje ogłoszenie będzie się wyróżniać, nie będąc rozpraszającym.
    -   **`option_border_color` (Kolor ramki):**
        -   **Co robi to ustawienie:** Ustawia niestandardowy kolor ramki dla Twojego ogłoszenia na Delcampe.
        -   **Efekt zmiany tego ustawienia:** Może sprawić, że Twoje ogłoszenie będzie bardziej atrakcyjne wizualnie lub dopasowane do Twojej marki.
        -   **Zalecana wartość:** Pozostaw puste lub użyj subtelnego koloru.
        -   **Scenariusz / przykład dla sprzedawcy:** Cienka, ciemna ramka może nadać Twojemu ogłoszeniu bardziej profesjonalny wygląd.

**Zalecany przepływ pracy dla codziennego zarządzania sklepem:**

1.  **Zidentyfikuj produkty dla Delcampe:** Zdecyduj, które z Twoich produktów PrestaShop nadają się na rynek Delcampe.
2.  **Dodaj/Edytuj produkty:** Przejdź do **Katalog > Produkty Delcampe**. Użyj przycisku „Dodaj nowy” lub edytuj istniejące wpisy, aby skonfigurować ustawienia specyficzne dla Delcampe dla każdego produktu. Zwróć szczególną uwagę na ID kategorii Delcampe, ceny i typ sprzedaży.
3.  **Generuj eksport:** Po skonfigurowaniu produktów moduł umożliwi wygenerowanie pliku eksportu. Ten plik będzie zawierał wszystkie niezbędne dane w formacie, który Delcampe Lister może zaimportować.
4.  **Importuj do Delcampe Lister:** Pobierz wygenerowany plik i zaimportuj go do narzędzia Delcampe Lister.
5.  **Monitoruj i aktualizuj:** Obserwuj swoje ogłoszenia na Delcampe i aktualizuj konfiguracje produktów w PrestaShop w razie potrzeby (np. w przypadku zmian cen, aktualizacji zapasów).

#### 2.2.2 AdminDelcampeProductsController (delcampeproducts/controllers/admin/AdminDelcampeProducts.php)

Ten kontroler jest odpowiedzialny za zarządzanie listami produktów Delcampe w panelu administracyjnym PrestaShop. Obsługuje wyświetlanie listy produktów, a także tworzenie, edytowanie i usuwanie indywidualnych konfiguracji produktów Delcampe.

#### 2.2.3 index.php (delcampeproducts/controllers/admin/index.php)

Ten plik prawdopodobnie służy jako symbol zastępczy lub proste przekierowanie w strukturze kontrolera administracyjnego, zapewniając prawidłową inicjalizację lub routing sekcji administracyjnej modułu. Zazwyczaj nie zawiera bezpośrednich opcji konfiguracji dla sprzedawcy.

### 2.3 Tabela szybkiego odniesienia do konfiguracji

| Ekran / Widok | Ustawienie / Opcja | Domyślne / Zalecane | Cel i wpływ |
| --- | --- | --- | --- |
| Strona konfiguracji modułu | MyPresta.eu Sprawdzanie aktualizacji na żywo | TAK | Kontroluje automatyczne sprawdzanie aktualizacji modułu. |
| Zarządzanie produktami Delcampe | ID kategorii Delcampe (`category_id`) | (Specyficzny ID Delcampe) | Mapuje produkt PrestaShop do kategorii Delcampe. |
| Zarządzanie produktami Delcampe | Tytuł ogłoszenia Delcampe (`title`) | (Niestandardowy) | Tytuł produktu wyświetlany na Delcampe. |
| Zarządzanie produktami Delcampe | Opis ogłoszenia Delcampe (`description`) | (Niestandardowy) | Szczegółowy opis produktu dla Delcampe. |
| Zarządzanie produktami Delcampe | Twoja wewnętrzna referencja (`personal_reference`) | (SKU PrestaShop) | Wewnętrzne śledzenie Twoich produktów. |
| Zarządzanie produktami Delcampe | Waluta ogłoszenia (`currency`) | (Twoja podstawowa waluta) | Waluta dla ogłoszenia Delcampe. |
| Zarządzanie produktami Delcampe | Typ sprzedaży Delcampe (`selling_type`) | (Stała cena / Aukcja) | Sposób sprzedaży produktu na Delcampe. |
| Zarządzanie produktami Delcampe | Cena początkowa / Cena stała (`price`) | (Twoja pożądana cena) | Cena za sprzedaż bezpośrednią lub początek aukcji. |
| Zarządzanie produktami Delcampe | Dostępna ilość (`initial_quantity`) | (Twój poziom zapasów) | Liczba jednostek dostępnych na Delcampe. |
| Zarządzanie produktami Delcampe | Krok licytacji aukcyjnej (`minimum_bid_step`) | (np. 0.50, 1.00) | Minimalna kwota, o jaką oferty muszą wzrosnąć. |
| Zarządzanie produktami Delcampe | Czas automatycznego odnawiania (`renew_duration`) | (np. 7 dni) | Jak długo niewystawione ogłoszenie jest odnawiane. |
| Zarządzanie produktami Delcampe | Limit automatycznego odnawiania (`renew_total_count`) | (np. 3, 5) | Maksymalna liczba automatycznych odnowień niewystawionego ogłoszenia. |
| Zarządzanie produktami Delcampe | Model wysyłki Delcampe (`shipping_model`) | (ID/Nazwa modelu Delcampe) | Metoda wysyłki używana na Delcampe. |
| Zarządzanie produktami Delcampe | Waga produktu (`weight`) | (Rzeczywista waga produktu) | Waga produktu do obliczania kosztów wysyłki. |
| Zarządzanie produktami Delcampe | Godzina zakończenia sprzedaży (`lister_sale_end_time`) | (np. 20:00) | Konkretna godzina zakończenia ogłoszenia. |
| Zarządzanie produktami Delcampe | Dzień zakończenia sprzedaży (`lister_sale_end_day`) | (np. niedziela) | Konkretny dzień tygodnia zakończenia ogłoszenia. |
| Zarządzanie produktami Delcampe | Przedłużenie w ostatniej chwili (`option_last_minute_extension`) | TAK (dla aukcji) | Przedłuża aukcję, jeśli oferta złożona w ostatnich minutach. |
| Zarządzanie produktami Delcampe | Anonimowy kupujący (`option_anonymous_buyer`) | NIE | Ukrywa tożsamość kupującego w aukcjach. |
| Zarządzanie produktami Delcampe | Mocny tytuł / Pogrubiony tytuł (`option_strong_title`) | TAK | Sprawia, że tytuł ogłoszenia jest pogrubiony na Delcampe. |
| Zarządzanie produktami Delcampe | Kolor tła (`option_background_color`) | (Pozostaw puste lub subtelne) | Niestandardowy kolor tła dla ogłoszenia. |
| Zarządzanie produktami Delcampe | Kolor ramki (`option_border_color`) | (Pozostaw puste lub subtelne) | Niestandardowy kolor ramki dla ogłoszenia. |

## 3. Rozwiązywanie problemów dla sprzedawców i często zadawane pytania (FAQ)

**P: Moje produkty nie pojawiają się na Delcampe po eksporcie. Co powinienem sprawdzić?**
O:

1.  **Czy zakończyłeś import w Delcampe Lister?** Ten moduł tylko *eksportuje* dane. Nadal musisz pobrać wygenerowany plik i *zaimportować* go do narzędzia Delcampe Lister.
2.  **Sprawdź ID kategorii Delcampe:** Upewnij się, że `category_id`, które wprowadziłeś dla każdego produktu, jest poprawne i istnieje na Delcampe. Nieprawidłowe ID mogą powodować błędy importu.
3.  **Przejrzyj błędy Delcampe Lister:** Kiedy importujesz plik do Delcampe Lister, zazwyczaj dostarcza on informacji zwrotnych lub komunikatów o błędach, jeśli coś poszło nie tak. Sprawdź te komunikaty w poszukiwaniu wskazówek.
4.  **Status produktu:** Upewnij się, że produkty są aktywne i dostępne w Twoim sklepie PrestaShop, jeśli skonfigurowałeś moduł tak, aby eksportował tylko aktywne/dostępne w magazynie pozycje.

**P: Jak obsługiwać aktualizacje produktów (zmiany cen, zmiany stanów magazynowych) na Delcampe?**
O: Będziesz musiał ponownie wyeksportować i ponownie zaimportować zaktualizowane dane produktu do Delcampe Lister. Moduł generuje nowy plik eksportu na podstawie Twoich aktualnych danych produktów PrestaShop i skonfigurowanych ustawień specyficznych dla Delcampe. Delcampe Lister zazwyczaj obsługuje aktualizacje istniejących ogłoszeń, gdy importujesz plik z pasującymi identyfikatorami produktów.

**P: Plik eksportu wydaje się pusty lub niekompletny.**
O:

1.  **Konfiguracja produktu:** Sprawdź dokładnie, czy faktycznie skonfigurowałeś produkty do eksportu Delcampe w **Katalog > Produkty Delcampe**. Jeśli żadne produkty nie są skonfigurowane, eksport będzie pusty.
2.  **Ustawienia modułu:** Przejrzyj wszelkie ogólne ustawienia modułu (jeśli istnieją), które mogą filtrować produkty, takie jak „eksportuj tylko aktywne produkty” lub „eksportuj tylko produkty dostępne w magazynie”.
3.  **Pamięć podręczna PrestaShop:** Czasami wyczyszczenie pamięci podręcznej PrestaShop (**Zaawansowane > Wydajność > Wyczyść pamięć podręczną**) może rozwiązać nieoczekiwane zachowanie związane z generowaniem danych.

**P: Mój niestandardowy szablon powoduje problemy z wyświetlaniem w konfiguracji panelu administracyjnego modułu.**
O: Interfejs panelu administracyjnego tego modułu wykorzystuje standardowe komponenty PrestaShop, więc powinien być ogólnie kompatybilny. Jeśli napotkasz problemy ze stylizacją, prawdopodobnie jest to konflikt z nadpisaniami panelu administracyjnego Twojego niestandardowego szablonu.

1.  **Sprawdź nadpisania:** Jeśli Twój szablon ma folder `admin` z nadpisaniami szablonów, tymczasowo zmień jego nazwę, aby sprawdzić, czy problem zostanie rozwiązany.
2.  **Skontaktuj się z deweloperem szablonu:** Jeśli problem nadal występuje, skontaktuj się z deweloperem szablonu w celu uzyskania pomocy, ponieważ może być konieczne dostosowanie ich CSS do standardowych interfejsów modułów.

## 4. Przewodnik dla deweloperów i webmasterów (Architektura techniczna i mapa kodu)

### 4.1 Przegląd architektury

Moduł „Eksport produktów do Delcampe Lister” wykorzystuje standardową architekturę modułu PrestaShop, głównie opierając się na kontrolerach administracyjnych dla swojego interfejsu panelu administracyjnego i zarządzania danymi. Nie opiera się on w dużym stopniu na komponentach front-office do bezpośredniej interakcji z klientem, ale wykorzystuje hooki do integracji z cyklem życia PrestaShop. Podstawowa funkcjonalność koncentruje się na zarządzaniu ustawieniami eksportu Delcampe specyficznymi dla produktu i generowaniu kanału danych dla narzędzia Delcampe Lister.

### 4.2 Kontrolery (`controllers/`)

-   **Kontrolery Front-Office**:

    -   `controllers/front/feed.php`
        -   **Nazwa klasy i klasa nadrzędna**: `DelcampeproductsFeedModuleFrontController` rozszerzający `ModuleFrontController`.
        -   **Odpowiedzialność**: Ten kontroler jest prawdopodobnie odpowiedzialny za generowanie rzeczywistego kanału produktów Delcampe (np. XML, CSV), który sprzedawca pobierałby. Odpytywałby skonfigurowane produkty i formatował ich dane zgodnie ze specyfikacjami Delcampe. Odpowiada na konkretną trasę front-office, chociaż nie jest bezpośrednio widoczny dla użytkownika końcowego przeglądającego sklep.
    -   `controllers/front/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: `DelcampeproductsIndexModuleFrontController` rozszerzający `ModuleFrontController`.
        -   **Odpowiedzialność**: Może służyć jako domyślny lub awaryjny kontroler front-office, lub może być używany do prostego przekierowania. W wielu modułach, jeśli `feed.php` obsługuje główną interakcję front-office (generowanie kanału), `index.php` może być minimalny lub nieużywany.
-   **Kontrolery administracyjne Back-Office**:

    -   `controllers/admin/AdminDelcampeProducts.php`
        -   **Nazwa klasy i klasa nadrzędna**: `AdminDelcampeProductsController` rozszerzający `ModuleAdminController`.
        -   **Nazwa zakładki i zarządzana encja**: Ten kontroler zarządza sekcją „Produkty Delcampe” w menu „Katalog” w Panelu administracyjnym PrestaShop. Jest odpowiedzialny za listowanie, dodawanie, edytowanie i usuwanie konfiguracji specyficznych dla Delcampe dla każdego produktu. Wykorzystuje `HelperList` i `HelperForm` PrestaShop do wyświetlania siatki produktów i szczegółowego formularza konfiguracji.
    -   `controllers/admin/index.php`
        -   **Nazwa klasy i klasa nadrzędna**: Nie jest to pełna klasa kontrolera, zazwyczaj prosty plik `index.php` zapobiegający listowaniu katalogów lub włączający główny plik modułu dla kontekstu. Nie definiuje odrębnej klasy kontrolera administracyjnego.

### 4.3 Klasy rdzeniowe i modele (`classes/`)

Dossier modułu wskazuje brak niestandardowych klas w katalogu `classes/`. Sugeruje to, że moduł może przechowywać swoje niestandardowe ustawienia eksportu produktów bezpośrednio w tabeli `ps_configuration` lub dynamicznie rozszerzać istniejące klasy `ObjectModel` PrestaShop (takie jak `Product`), lub używać bardziej bezpośredniej interakcji z bazą danych w kontrolerze. Biorąc pod uwagę szczegółowe pola formularza, jest bardzo prawdopodobne, że ustawienia Delcampe specyficzne dla produktu są przechowywane w `ps_configuration` z kluczami takimi jak `dp_export_categories` lub bezpośrednio w logice `AdminDelcampeProductsController`.

### 4.4 Zasoby JavaScript (`views/js/`)

-   `delcampeproducts/lib/js/admin/delcampeproducts.js`
    -   **Zakres**: Panel administracyjny.
    -   **Szczegóły**: Ten skrypt jest ładowany w Panelu administracyjnym PrestaShop, szczególnie dla kontrolera `AdminDelcampeProducts`. Prawdopodobnie obsługuje:
        -   Dynamiczne zachowanie formularza (np. pokazywanie/ukrywanie pól na podstawie `selling_type`).
        -   Wywołania AJAX do zapisywania ustawień lub generowania pliku eksportu.
        -   Walidację danych wejściowych lub formatowanie dla pól takich jak `category_id`, `price`, `weight`.
        -   Wszelkie interaktywne elementy w formularzach konfiguracji produktów lub siatce listingu.
        -   Potencjalnie używa jQuery do manipulacji DOM i obsługi zdarzeń.

### 4.5 Arkusze stylów CSS (`views/css/`)

Dossier modułu wskazuje brak niestandardowych plików CSS. Oznacza to, że moduł opiera się całkowicie na domyślnej stylizacji Panelu administracyjnego PrestaShop dla swoich formularzy konfiguracji i list, zapewniając spójny wygląd i działanie z resztą panelu administracyjnego. Deweloperzy chcący stylizować interfejs administracyjny modułu musieliby celować w istniejące klasy CSS PrestaShop lub wstrzykiwać niestandardowy CSS za pomocą hooka `actionAdminControllerSetMedia`.

### 4.6 Struktura szablonów Smarty (`views/templates/`)

-   **Szablony hooków (`views/templates/hook/`)**: Brak wyraźnie wymienionych, ale moduły często używają `displayAdminProductsExtra` lub podobnych dla zakładek na stronie produktu.
-   **Szablony administracyjne (`views/templates/admin/`)**:
    -   `delcampeproducts/script.tpl`
        -   **Zakres**: Panel administracyjny.
        -   **Szczegóły**: Ten szablon jest prawdopodobnie używany do wyprowadzania zmiennych JavaScript lub skryptów inline, które są potrzebne przez `delcampeproducts.js`. Może przekazywać wartości konfiguracyjne z PHP do JavaScript lub definiować globalne obiekty JS. Jest często renderowany za pomocą hooka `actionAdminControllerSetMedia`.
-   **Szablony front-office (`views/templates/front/`)**: Brak wyraźnie wymienionych, co jest zgodne z charakterem modułu do eksportu w tle.

### 4.7 Schemat bazy danych i mapa hooków

-   **Tabele bazy danych**:

    -   Moduł prawdopodobnie przechowuje swoje ustawienia konfiguracyjne w tabeli `ps_configuration` używając kluczy takich jak `dp_export_categories`, `dp_remember_settings`, `dp_option_homepage_promotion`, `dp_lister_status`, `dp_lister_creation_date`, `dp_lister_sending_date`, `dp_llister_sending_date`, `dp_lister_edit_date`, `dp_export_format`, `dp_export_active`, `dp_export_instock`, `dp_export_identification`, `dp_export_category`, `dp_export_manufacturers_default`.
    -   Dla ustawień Delcampe specyficznych dla produktu (takich jak `category_id`, `title`, `price` itp.), biorąc pod uwagę, że nie ma wymienionego niestandardowego `ObjectModel`, są one prawdopodobnie przechowywane jako serializowane dane w `ps_configuration` (mniej idealne dla ustawień na produkt) lub, co bardziej prawdopodobne, `AdminDelcampeProductsController` bezpośrednio zarządza niestandardową tabelą bazy danych (np. `ps_delcampe_product_settings`), która nie została wyraźnie zidentyfikowana w dossier, ale byłoby to standardowe podejście do tak szczegółowych danych na produkt. Jeśli nie istnieje niestandardowa tabela, może używać `Product::addFeature` lub `Product::addCustomization` w niestandardowy sposób, lub przechowywać dane w `ps_product_lang` lub `ps_product_shop` poprzez nadpisania. **(Uwaga dla dewelopera: Sprawdź bazę danych pod kątem `ps_delcampe_product_settings` lub podobnej tabeli po instalacji.)**
-   **Tabela zarejestrowanych hooków**:

| Nazwa hooka | Czas wykonania | Cel techniczny |
| --- | --- | --- |
| `actionProductUpdate` | Po zaktualizowaniu produktu w Panelu administracyjnym. | Pozwala modułowi reagować na zmiany produktów (np. aktualizować wewnętrzne dane eksportu Delcampe, oznaczać produkt do ponownego eksportu). |
| `actionAdminControllerSetMedia` | Gdy kontroler administracyjny jest ładowany i ustawiane są jego media (JS/CSS). | Służy do wstrzykiwania niestandardowego JavaScriptu modułu (`delcampeproducts.js`) i potencjalnie skryptów inline (`script.tpl`) do stron Panelu administracyjnego, zwłaszcza dla kontrolera `AdminDelcampeProducts`. |
| `displayAdminProductsExtra` | (Implicitne, często używane dla zakładek produktów) | Jeśli moduł dodaje zakładkę do strony edycji produktu dla ustawień Delcampe, ten hook byłby używany. (Nie jest wyraźnie wymieniony jako hook, ale jest powszechny dla takiej funkcjonalności). |
| `displayBackOfficeHeader` | W nagłówku każdej strony Panelu administracyjnego. | Może być używany do globalnego JS/CSS po stronie administratora lub do wyświetlania powiadomień. |
| `moduleRoutes` | Podczas generowania tras dla modułu. | Służy do definiowania niestandardowych adresów URL front-office dla kontrolerów takich jak `feed.php`. |

## 5. Oficjalne wsparcie i aktualizacje

Aby uzyskać najnowsze aktualizacje, poprawki błędów i kompleksowe wsparcie dla modułu „Eksport produktów do Delcampe Lister”, zapoznaj się ze swoim kontem klienta na [MyPresta.eu](https://mypresta.eu/). Nasz dedykowany zespół wsparcia jest dostępny, aby pomóc Ci w przypadku wszelkich problemów technicznych lub pytań dotyczących funkcjonalności modułu.
